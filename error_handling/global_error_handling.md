#Global error handling
By explaining how EitherType is being used and seeing what attributes and methods Failure class has, now we can examine how we can handle global error handling in the project. We define globalFailureProvider which is of type StateProvider and it is of Failure optional type.
```dart

final globalFailureProvider = StateProvider<Failure?>((_) => null);
```
Then we define globalFailureListener() method as an extension to WidgetRef class where globalFailureListener() method we can globally decide how we want to handle all the failures (snackbar, dialog, etc.):
```dart
void globalFailureListener() {
  listen<Failure?>(globalFailureProvider, (_, failure) {
    if (failure == null) return;
    //Show global error
    logger.i('''showing ${failure.isCritical ? '' : 'non-'}critical failure with title ${failure.title},
          error: ${failure.error},
          stackTrace: ${failure.stackTrace}
      ''');
  });
}
```
In BaseWidget ```ref.globalFailureListener();``` is called within build method. globalFailureProvider can be accessed directly with ```ref``` but also BaseStateNotifier and SimpleStateNotifier classes define setGlobalFailure() method to make it even more convenient:
```dart
  @protected
  void setGlobalFailure(Failure? failure) {
    clearGlobalLoading();
    ref
        .read(globalFailureProvider.notifier)
        .update((state) => failure?.copyWith(uniqueKey: UniqueKey()));
  }
```
Then in our notifier which extends BaseStateNotifier or SimpleStateNotifier we can simply call setGlobalFailure() whenever we want and pass our Failure object to show it to the user.