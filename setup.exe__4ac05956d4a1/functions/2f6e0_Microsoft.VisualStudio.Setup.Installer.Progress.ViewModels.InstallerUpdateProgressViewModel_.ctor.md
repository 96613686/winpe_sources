# Microsoft.VisualStudio.Setup.Installer.Progress.ViewModels.InstallerUpdateProgressViewModel::.ctor

- ea: `0x2f6e0`
- end: `0x2f72e`
- name: `Microsoft.VisualStudio.Setup.Installer.Progress.ViewModels.InstallerUpdateProgressViewModel::.ctor`
- size: `78`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `installer_update, broker_com_uri`

## callers

- `0x11440`
- `0x75360`

## callees

- `0x13b20`

## string_xrefs

- `0x2f707`: `ShowInstallProgressBar`
- `0x2f723`: `ShowDownloadThenInstallText`

## pseudocode

```c

```

## disassembly

```asm
0x2f6e0  ldarg.0
0x2f6e1  ldarg.1
0x2f6e2  call     instance void Microsoft.VisualStudio.Setup.Installer.ViewModels.ViewModelBase::.ctor(class Microsoft.VisualStudio.Setup.Installer.ServiceOptions.ViewModelBaseServiceOptions options)
0x2f6e7  ldarg.0
0x2f6e8  ldarg.2
0x2f6e9  stfld    class Microsoft.VisualStudio.Setup.Installer.Progress.ViewModels.IProgressBarViewModel Microsoft.VisualStudio.Setup.Installer.Progress.ViewModels.InstallerUpdateProgressViewModel::<InstallerUpdateProgressBarViewModel>k__BackingField
0x2f6ee  ldarg.0
0x2f6ef  ldarg.3
0x2f6f0  stfld    class Microsoft.VisualStudio.Setup.Installer.Progress.ViewModels.IProgressViewModel Microsoft.VisualStudio.Setup.Installer.Progress.ViewModels.InstallerUpdateProgressViewModel::operationProgressViewModel
0x2f6f5  ldarg.0
0x2f6f6  ldfld    class Microsoft.VisualStudio.Setup.Installer.Progress.ViewModels.IProgressViewModel Microsoft.VisualStudio.Setup.Installer.Progress.ViewModels.InstallerUpdateProgressViewModel::operationProgressViewModel
0x2f6fb  ldarg.0
0x2f6fc  ldftn    instance void Microsoft.VisualStudio.Setup.Installer.Progress.ViewModels.InstallerUpdateProgressViewModel::OnShowInstallProgressBarChanged(object sender, class [System]System.ComponentModel.PropertyChangedEventArgs e)
0x2f702  newobj   instance void class [mscorlib]System.EventHandler`1<class [System]System.ComponentModel.PropertyChangedEventArgs>::.ctor(object, native int)
0x2f707  ldstr    aShowinstallpro// "ShowInstallProgressBar"
0x2f70c  call     void [WindowsBase]System.ComponentModel.PropertyChangedEventManager::AddHandler(class [System]System.ComponentModel.INotifyPropertyChanged, class [mscorlib]System.EventHandler`1<class [System]System.ComponentModel.PropertyChangedEventArgs>, string)
0x2f711  ldarg.0
0x2f712  ldfld    class Microsoft.VisualStudio.Setup.Installer.Progress.ViewModels.IProgressViewModel Microsoft.VisualStudio.Setup.Installer.Progress.ViewModels.InstallerUpdateProgressViewModel::operationProgressViewModel
0x2f717  ldarg.0
0x2f718  ldftn    instance void Microsoft.VisualStudio.Setup.Installer.Progress.ViewModels.InstallerUpdateProgressViewModel::OnShowDownloadThenInstallText(object sender, class [System]System.ComponentModel.PropertyChangedEventArgs e)
0x2f71e  newobj   instance void class [mscorlib]System.EventHandler`1<class [System]System.ComponentModel.PropertyChangedEventArgs>::.ctor(object, native int)
0x2f723  ldstr    aShowdownloadth// "ShowDownloadThenInstallText"
0x2f728  call     void [WindowsBase]System.ComponentModel.PropertyChangedEventManager::AddHandler(class [System]System.ComponentModel.INotifyPropertyChanged, class [mscorlib]System.EventHandler`1<class [System]System.ComponentModel.PropertyChangedEventArgs>, string)
0x2f72d  ret
```
