# Microsoft.VisualStudio.Setup.Installer.Views.ThemedWindow::.ctor

- ea: `0xec20`
- end: `0xec84`
- name: `Microsoft.VisualStudio.Setup.Installer.Views.ThemedWindow::.ctor`
- size: `100`
- prototype: ``
- caller_count: `5`
- callee_count: `5`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0xea90`
- `0x190a0`
- `0x1a2e0`
- `0x4c290`
- `0x5bf60`

## callees

- `0xe910`
- `0xecf0`
- `0xedd0`
- `0xef30`
- `0xf000`

## string_xrefs

- `0xec28`: `serviceOptions`

## pseudocode

```c

```

## disassembly

```asm
0xec20  ldarg.0
0xec21  ldarg.1
0xec22  call     instance void Microsoft.VisualStudio.Setup.Installer.Views.InstallerWindowBase::.ctor(class Microsoft.VisualStudio.Setup.Installer.ServiceOptions.AppInitializerServiceOptions serviceOptions)
0xec27  ldarg.1
0xec28  ldstr    aServiceoptions// "serviceOptions"
0xec2d  call     void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Validate::IsNotNull(object, string)
0xec32  ldarg.2
0xec33  ldstr    aVm// "vm"
0xec38  call     void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Validate::IsNotNull(object, string)
0xec3d  ldarg.0
0xec3e  ldarg.2
0xec3f  call     instance void [PresentationFramework]System.Windows.FrameworkElement::set_DataContext(object)
0xec44  ldarg.0
0xec45  ldarg.2
0xec46  stfld    class Microsoft.VisualStudio.Setup.Installer.ViewModels.IApplicationViewModel Microsoft.VisualStudio.Setup.Installer.Views.ThemedWindow::viewModel
0xec4b  ldarg.0
0xec4c  ldarg.1
0xec4d  stfld    class Microsoft.VisualStudio.Setup.Installer.ServiceOptions.AppInitializerServiceOptions Microsoft.VisualStudio.Setup.Installer.Views.ThemedWindow::serviceOptions
0xec52  ldarg.0
0xec53  ldarg.3
0xec54  stfld    valuetype [mscorlib]System.Nullable`1<int32> Microsoft.VisualStudio.Setup.Installer.Views.ThemedWindow::parentHandle
0xec59  ldarg.0
0xec5a  call     instance void Microsoft.VisualStudio.Setup.Installer.Views.ThemedWindow::InitializeComponent()
0xec5f  ldarg.0
0xec60  call     instance void Microsoft.VisualStudio.Setup.Installer.Views.ThemedWindow::AddTaskbarItem()
0xec65  ldarg.0
0xec66  ldarg.0
0xec67  ldftn    instance void Microsoft.VisualStudio.Setup.Installer.Views.ThemedWindow::OnLoaded(object sender, class [PresentationCore]System.Windows.RoutedEventArgs e)
0xec6d  newobj   instance void [PresentationCore]System.Windows.RoutedEventHandler::.ctor(object, native int)
0xec72  call     instance void [PresentationFramework]System.Windows.FrameworkElement::add_Loaded(class [PresentationCore]System.Windows.RoutedEventHandler)
0xec77  ldarg.0
0xec78  call     instance void Microsoft.VisualStudio.Setup.Installer.Views.ThemedWindow::SetDimensionsImpl()
0xec7d  ldarg.0
0xec7e  call     instance void Microsoft.VisualStudio.Setup.Installer.Views.ThemedWindow::SetWindowPosition()
0xec83  ret
```
