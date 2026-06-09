# <HandleQuietOrPassiveAsync>d__83::MoveNext

- ea: `0x68a50`
- end: `0x68be0`
- name: `<HandleQuietOrPassiveAsync>d__83::MoveNext`
- size: `400`
- prototype: ``
- caller_count: `0`
- callee_count: `9`
- tags: `installer_update, broker_com_uri`

## callees

- `0x17cf0`
- `0x17d00`
- `0x18780`
- `0x187c0`
- `0x229c0`
- `0x2c890`
- `0x2d6b0`
- `0x3a8c0`
- `0x68a50`

## string_xrefs

- `0x68b72`: `'{0}' is already set to channel '{1}' for updates.`
- `0x68acb`: `'{0}' changed to channel '{1}' for updates.`
- `0x68b22`: `Failed to change channel for installation: {0}. New channel uri: {1}`

## pseudocode

```c

```

## disassembly

```asm
0x68a50  ldarg.0
0x68a51  ldfld    int32 <HandleQuietOrPassiveAsync>d__83::<>1__state
0x68a56  stloc.0
0x68a57  ldarg.0
0x68a58  ldfld    class Microsoft.VisualStudio.Setup.Installer.ChangeChannel.ViewModels.UpdateSettingsPageViewModel <HandleQuietOrPassiveAsync>d__83::<>4__this
0x68a5d  stloc.1
0x68a5e  ldloc.0
0x68a5f  brfalse.s loc_68A6C
0x68a61  ldloc.1
0x68a62  call     instance bool Microsoft.VisualStudio.Setup.Installer.ChangeChannel.ViewModels.UpdateSettingsPageViewModel::EnableAcceptButton()
0x68a67  brfalse  loc_68B72
0x68a6c  nop
0x68a6d  ldloc.0
0x68a6e  brfalse.s loc_68AA8
0x68a70  ldloc.1
0x68a71  call     instance class [mscorlib]System.Threading.Tasks.Task Microsoft.VisualStudio.Setup.Installer.ChangeChannel.ViewModels.UpdateSettingsPageViewModel::UpdateSettings()
0x68a76  callvirt instance valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter [mscorlib]System.Threading.Tasks.Task::GetAwaiter()
0x68a7b  stloc.3
0x68a7c  ldloca.s 3
0x68a7e  call     instance bool [mscorlib]System.Runtime.CompilerServices.TaskAwaiter::get_IsCompleted()
0x68a83  brtrue.s loc_68AC4
0x68a85  ldarg.0
0x68a86  ldc.i4.0
0x68a87  dup
0x68a88  stloc.0
0x68a89  stfld    int32 <HandleQuietOrPassiveAsync>d__83::<>1__state
0x68a8e  ldarg.0
0x68a8f  ldloc.3
0x68a90  stfld    valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter <HandleQuietOrPassiveAsync>d__83::<>u__1
0x68a95  ldarg.0
0x68a96  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder <HandleQuietOrPassiveAsync>d__83::<>t__builder
0x68a9b  ldloca.s 3
0x68a9d  ldarg.0
0x68a9e  call     T0x2B000437
0x68aa3  leave    loc_68BDF
0x68aa8  ldarg.0
0x68aa9  ldfld    valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter <HandleQuietOrPassiveAsync>d__83::<>u__1
0x68aae  stloc.3
0x68aaf  ldarg.0
0x68ab0  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter <HandleQuietOrPassiveAsync>d__83::<>u__1
0x68ab5  initobj  [mscorlib]System.Runtime.CompilerServices.TaskAwaiter
0x68abb  ldarg.0
0x68abc  ldc.i4.m1
0x68abd  dup
0x68abe  stloc.0
0x68abf  stfld    int32 <HandleQuietOrPassiveAsync>d__83::<>1__state
0x68ac4  ldloca.s 3
0x68ac6  call     instance void [mscorlib]System.Runtime.CompilerServices.TaskAwaiter::GetResult()
0x68acb  ldstr    a0ChangedToChan// "'{0}' changed to channel '{1}' for upda"...
0x68ad0  ldloc.1
0x68ad1  ldfld    class Microsoft.VisualStudio.Setup.Installer.ChangeChannel.UpdateSettingsPageOptions Microsoft.VisualStudio.Setup.Installer.ChangeChannel.ViewModels.UpdateSettingsPageViewModel::options
0x68ad6  callvirt instance class Microsoft.VisualStudio.Setup.Installer.Models.Products.IInstalledProductBaseModel Microsoft.VisualStudio.Setup.Installer.ChangeChannel.UpdateSettingsPageOptions::get_Product()
0x68adb  callvirt instance string Microsoft.VisualStudio.Setup.Installer.Models.Products.IInstalledProductIdentityModel::get_InstallationPath()
0x68ae0  ldloc.1
0x68ae1  ldfld    class Microsoft.VisualStudio.Setup.Installer.ChangeChannel.UpdateSettingsPageOptions Microsoft.VisualStudio.Setup.Installer.ChangeChannel.ViewModels.UpdateSettingsPageViewModel::options
0x68ae6  callvirt instance class [System]System.Uri Microsoft.VisualStudio.Setup.Installer.ChangeChannel.UpdateSettingsPageOptions::get_ChannelUri()
0x68aeb  callvirt instance string [mscorlib]System.Object::ToString()
0x68af0  call     string [mscorlib]System.String::Format(string, object, object)
0x68af5  stloc.2
0x68af6  ldloc.1
0x68af7  ldfld    class Microsoft.VisualStudio.Setup.Installer.ServiceOptions.UpdateSettingsServiceOptions Microsoft.VisualStudio.Setup.Installer.ChangeChannel.ViewModels.UpdateSettingsPageViewModel::serviceOptions
0x68afc  callvirt instance class Microsoft.VisualStudio.Setup.Installer.Services.IShutdownRequestService Microsoft.VisualStudio.Setup.Installer.ServiceOptions.InstallerViewModelServiceOptions::get_ShutdownService()
0x68b01  ldc.i4.0
0x68b02  ldloc.2
0x68b03  callvirt instance void Microsoft.VisualStudio.Setup.Installer.Services.IShutdownRequestService::Shutdown(int32 exitCode, string message)
0x68b08  leave    loc_68BB1
0x68b0d  stloc.s  4
0x68b0f  ldloc.1
0x68b10  ldfld    class Microsoft.VisualStudio.Setup.Installer.ServiceOptions.UpdateSettingsServiceOptions Microsoft.VisualStudio.Setup.Installer.ChangeChannel.ViewModels.UpdateSettingsPageViewModel::serviceOptions
0x68b15  callvirt instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger Microsoft.VisualStudio.Setup.Installer.ServiceOptions.ViewModelBaseServiceOptions::get_Logger()
0x68b1a  dup
0x68b1b  brtrue.s loc_68B20
0x68b1d  pop
0x68b1e  br.s     loc_68B58
0x68b20  ldloc.s  4
0x68b22  ldstr    aFailedToChange_1// "Failed to change channel for installati"...
0x68b27  ldc.i4.2
0x68b28  newarr   [mscorlib]System.Object
0x68b2d  dup
0x68b2e  ldc.i4.0
0x68b2f  ldloc.1
0x68b30  ldfld    class Microsoft.VisualStudio.Setup.Installer.ChangeChannel.UpdateSettingsPageOptions Microsoft.VisualStudio.Setup.Installer.ChangeChannel.ViewModels.UpdateSettingsPageViewModel::options
0x68b35  callvirt instance class Microsoft.VisualStudio.Setup.Installer.Models.Products.IInstalledProductBaseModel Microsoft.VisualStudio.Setup.Installer.ChangeChannel.UpdateSettingsPageOptions::get_Product()
0x68b3a  callvirt instance string Microsoft.VisualStudio.Setup.Installer.Models.Products.IInstalledProductIdentityModel::get_InstallationPath()
0x68b3f  stelem.ref
0x68b40  dup
0x68b41  ldc.i4.1
0x68b42  ldloc.1
0x68b43  ldfld    class Microsoft.VisualStudio.Setup.Installer.ChangeChannel.UpdateSettingsPageOptions Microsoft.VisualStudio.Setup.Installer.ChangeChannel.ViewModels.UpdateSettingsPageViewModel::options
0x68b48  callvirt instance class [System]System.Uri Microsoft.VisualStudio.Setup.Installer.ChangeChannel.UpdateSettingsPageOptions::get_ChannelUri()
0x68b4d  callvirt instance string [mscorlib]System.Object::ToString()
0x68b52  stelem.ref
0x68b53  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger::WriteError(class [mscorlib]System.Exception, string, object[])
0x68b58  ldloc.1
0x68b59  ldfld    class Microsoft.VisualStudio.Setup.Installer.ServiceOptions.UpdateSettingsServiceOptions Microsoft.VisualStudio.Setup.Installer.ChangeChannel.ViewModels.UpdateSettingsPageViewModel::serviceOptions
0x68b5e  callvirt instance class Microsoft.VisualStudio.Setup.Installer.Services.IShutdownRequestService Microsoft.VisualStudio.Setup.Installer.ServiceOptions.InstallerViewModelServiceOptions::get_ShutdownService()
0x68b63  ldc.i4.1
0x68b64  ldloc.s  4
0x68b66  callvirt instance string [mscorlib]System.Exception::get_Message()
0x68b6b  callvirt instance void Microsoft.VisualStudio.Setup.Installer.Services.IShutdownRequestService::Shutdown(int32 exitCode, string message)
0x68b70  leave.s  loc_68BB1
0x68b72  ldstr    a0IsAlreadySetT// "'{0}' is already set to channel '{1}' f"...
0x68b77  ldloc.1
0x68b78  ldfld    class Microsoft.VisualStudio.Setup.Installer.ChangeChannel.UpdateSettingsPageOptions Microsoft.VisualStudio.Setup.Installer.ChangeChannel.ViewModels.UpdateSettingsPageViewModel::options
0x68b7d  callvirt instance class Microsoft.VisualStudio.Setup.Installer.Models.Products.IInstalledProductBaseModel Microsoft.VisualStudio.Setup.Installer.ChangeChannel.UpdateSettingsPageOptions::get_Product()
0x68b82  callvirt instance string Microsoft.VisualStudio.Setup.Installer.Models.Products.IInstalledProductIdentityModel::get_InstallationPath()
0x68b87  ldloc.1
0x68b88  ldfld    class Microsoft.VisualStudio.Setup.Installer.ChangeChannel.UpdateSettingsPageOptions Microsoft.VisualStudio.Setup.Installer.ChangeChannel.ViewModels.UpdateSettingsPageViewModel::options
0x68b8d  callvirt instance class [System]System.Uri Microsoft.VisualStudio.Setup.Installer.ChangeChannel.UpdateSettingsPageOptions::get_ChannelUri()
0x68b92  callvirt instance string [mscorlib]System.Object::ToString()
0x68b97  call     string [mscorlib]System.String::Format(string, object, object)
0x68b9c  stloc.s  5
0x68b9e  ldloc.1
0x68b9f  ldfld    class Microsoft.VisualStudio.Setup.Installer.ServiceOptions.UpdateSettingsServiceOptions Microsoft.VisualStudio.Setup.Installer.ChangeChannel.ViewModels.UpdateSettingsPageViewModel::serviceOptions
0x68ba4  callvirt instance class Microsoft.VisualStudio.Setup.Installer.Services.IShutdownRequestService Microsoft.VisualStudio.Setup.Installer.ServiceOptions.InstallerViewModelServiceOptions::get_ShutdownService()
0x68ba9  ldc.i4.0
0x68baa  ldloc.s  5
0x68bac  callvirt instance void Microsoft.VisualStudio.Setup.Installer.Services.IShutdownRequestService::Shutdown(int32 exitCode, string message)
0x68bb1  leave.s  loc_68BCC
0x68bb3  stloc.s  6
0x68bb5  ldarg.0
0x68bb6  ldc.i4.s 0xFE
0x68bb8  stfld    int32 <HandleQuietOrPassiveAsync>d__83::<>1__state
0x68bbd  ldarg.0
0x68bbe  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder <HandleQuietOrPassiveAsync>d__83::<>t__builder
0x68bc3  ldloc.s  6
0x68bc5  call     instance void [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder::SetException(class [mscorlib]System.Exception)
0x68bca  leave.s  loc_68BDF
0x68bcc  ldarg.0
0x68bcd  ldc.i4.s 0xFE
0x68bcf  stfld    int32 <HandleQuietOrPassiveAsync>d__83::<>1__state
0x68bd4  ldarg.0
0x68bd5  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder <HandleQuietOrPassiveAsync>d__83::<>t__builder
0x68bda  call     instance void [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder::SetResult()
0x68bdf  ret
```
