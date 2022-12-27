#EitherType
By using dartz package, we always return Either from a repository method where left part is our own Failure class and right part is expected result if execution of the method ended with success. By using Either, caller of the repository methods doesn't have to wrap each call in try catch block and is just able to wait for the result of the method and fold it to be prepared for both outcomes, fail and success.\
This is the basic Either response we use ```Either<Failure, T>``` and because repository methods almost exclusively as async we use the following alias to this response\
```typedef EitherFailureOr<T> = Future<Either<Failure, T>>;```

Here is an example how this can be used when declaring a method and calling that same method:
```dart
  // method in repository
  EitherFailureOr<String> getYourString() async {
    try {
      final string = await apiClient.getString();
      return Right(string);
    } catch (error, stackTrace) {
      return Left(
        Failure.generic(
          title: 'Error while fetching string from API', 
          error: error, 
          stackTrace: stackTrace,
        ),
      );
    }
  }
  
  // calling repository method
  final result = await repository.getYourString();
  result.fold(
      (failure) {
        // do something with your failure
      },
      (yourString) {
        // do something with your string
      }
  );
```

In this example you can see how a method can throw some exception but it will be handled right away and the caller will just get a wrapped response with either failure or expected result.
