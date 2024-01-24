# rzctl
Compilable version of: https://github.com/Sadmeme/rzctl

ChatGPT was used to rewrite rzctl.h (I don't know C++ yet sorry)

Once compiled, implementation is easy as such:

1. Put rzctl.dll in your directory

2. Put these outside of loading:
```c#
[DllImport("rzctl.dll", CallingConvention = CallingConvention.Cdecl)]
public static extern bool init();
```
```c#
[DllImport("rzctl.dll", CallingConvention = CallingConvention.Cdecl)]
public static extern void mouse_move(int x, int y, bool starting_point);
```
```c#
[DllImport("rzctl.dll", CallingConvention = CallingConvention.Cdecl)]
public static extern void mouse_click(int up_down);
```

3. Call the functions

Initialize and check if rzctl can be used
```c#
if (init())
{
  System.Windows.MessageBox.Show(":joesus:");
}
else if (!init())
{
  System.Windows.MessageBox.Show(":joesad:");
}
```
Move mouse left/right by x amount, up/down by y amount
```c#
mouse_move(0, 0, true);
```
Click Mouse Down:
```c#
mouse_click(1);
```
Click Mouse Up:
```c#
mouse_click(2);
```

Hope you enjoy 😊
