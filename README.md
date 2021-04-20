# DLL Mod Menu
This is our old mod menu project including toast for Android DLL games which is easly moddable in C#. Most games today have been moved to Il2Cpp, so DLL are dead now

![](https://i.imgur.com/v7dvTJU.png)

# Adding menu to DLL

Pointless to explain much in details since it's dead, and there are already plenty of tutorials. Ours is a much simpler way which doesn't require adding to active classes

- Extract \assets\bin\Data\Managed folder from APK file using 7zip

- Open Assembly-Csharp.dll in dnSpy

- Add class to Assembly-Csharp.dll and save the file

- Open mscorlib.dll in dnSpy

- Edit `GetText(string msg)` in class `Locale`

- Add `ModMenu.StartMenu();` like below

```
public static string GetText(string msg)
{
	ModMenu.StartMenu();
	return msg;
}
```

- Save mscorlib.dll

- Put both DLL back to \assets\bin\Data\Managed in APK

- Sign APK

That's all!

# Credits

AndnixSH https://github.com/AndnixSH/ClassicUnityModMenuAndroid