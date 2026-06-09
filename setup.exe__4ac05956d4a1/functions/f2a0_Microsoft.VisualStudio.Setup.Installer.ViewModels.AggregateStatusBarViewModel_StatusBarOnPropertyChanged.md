# Microsoft.VisualStudio.Setup.Installer.ViewModels.AggregateStatusBarViewModel::StatusBarOnPropertyChanged

- ea: `0xf2a0`
- end: `0xf346`
- name: `Microsoft.VisualStudio.Setup.Installer.ViewModels.AggregateStatusBarViewModel::StatusBarOnPropertyChanged`
- size: `166`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: `installer_update, broker_com_uri`

## callees

- `0xf2a0`
- `0xf360`
- `0x116a0`
- `0x11700`
- `0x11790`
- `0x117c0`
- `0x117d0`

## string_xrefs

- `0xf2b5`: `IsCheckingForUpdates`
- `0xf2c2`: `ShowUpdateAllButton`

## pseudocode

```c

```

## disassembly

```asm
0xf2a0  ldarg.2
0xf2a1  callvirt instance string [System]System.ComponentModel.PropertyChangedEventArgs::get_PropertyName()
0xf2a6  stloc.1
0xf2a7  ldloc.1
0xf2a8  ldstr    aShowstatusbar// "ShowStatusBar"
0xf2ad  call     bool [mscorlib]System.String::op_Equality(string, string)
0xf2b2  brtrue.s loc_F2CF
0xf2b4  ldloc.1
0xf2b5  ldstr    aIscheckingforu// "IsCheckingForUpdates"
0xf2ba  call     bool [mscorlib]System.String::op_Equality(string, string)
0xf2bf  brtrue.s loc_F2CF
0xf2c1  ldloc.1
0xf2c2  ldstr    aShowupdateallb// "ShowUpdateAllButton"
0xf2c7  call     bool [mscorlib]System.String::op_Equality(string, string)
0xf2cc  brtrue.s loc_F2CF
0xf2ce  ret
0xf2cf  ldarg.0
0xf2d0  ldfld    class Microsoft.VisualStudio.Setup.Installer.ViewModels.IStatusBarViewModel Microsoft.VisualStudio.Setup.Installer.ViewModels.AggregateStatusBarViewModel::statusBar
0xf2d5  callvirt instance bool Microsoft.VisualStudio.Setup.Installer.ViewModels.IStatusBarViewModel::get_ShowStatusBar()
0xf2da  brtrue.s loc_F2E9
0xf2dc  ldarg.0
0xf2dd  ldarg.0
0xf2de  ldfld    class Microsoft.VisualStudio.Setup.Installer.ViewModels.IStatusBarViewModel Microsoft.VisualStudio.Setup.Installer.ViewModels.AggregateStatusBarViewModel::statusBar
0xf2e3  call     instance void Microsoft.VisualStudio.Setup.Installer.ViewModels.AggregateStatusBarViewModel::set_ActiveStatusBarViewModel(class Microsoft.VisualStudio.Setup.Installer.ViewModels.IViewModel value)
0xf2e8  ret
0xf2e9  ldarg.0
0xf2ea  ldfld    class Microsoft.VisualStudio.Setup.Installer.ViewModels.IRemoteStatusBarViewModel Microsoft.VisualStudio.Setup.Installer.ViewModels.AggregateStatusBarViewModel::remoteStatusBar
0xf2ef  callvirt instance bool Microsoft.VisualStudio.Setup.Installer.ViewModels.IRemoteStatusBarViewModel::get_ShowRemoteStatusBar()
0xf2f4  brfalse.s loc_F328
0xf2f6  ldarg.0
0xf2f7  ldfld    class Microsoft.VisualStudio.Setup.Installer.ViewModels.IRemoteStatusBarViewModel Microsoft.VisualStudio.Setup.Installer.ViewModels.AggregateStatusBarViewModel::remoteStatusBar
0xf2fc  callvirt instance int32 Microsoft.VisualStudio.Setup.Installer.ViewModels.IRemoteStatusBarViewModel::get_Precedence()
0xf301  ldc.i4.s 0x64
0xf303  blt.s    loc_F325
0xf305  ldarg.0
0xf306  ldfld    class Microsoft.VisualStudio.Setup.Installer.ViewModels.IStatusBarViewModel Microsoft.VisualStudio.Setup.Installer.ViewModels.AggregateStatusBarViewModel::statusBar
0xf30b  stloc.2
0xf30c  ldloc.2
0xf30d  brfalse.s loc_F322
0xf30f  ldloc.2
0xf310  callvirt instance bool Microsoft.VisualStudio.Setup.Installer.ViewModels.IStatusBarViewModel::get_IsCheckingForUpdates()
0xf315  brtrue.s loc_F322
0xf317  ldloc.2
0xf318  callvirt instance bool Microsoft.VisualStudio.Setup.Installer.ViewModels.IStatusBarViewModel::get_ShowUpdateAllButton()
0xf31d  ldc.i4.0
0xf31e  ceq
0xf320  br.s     loc_F329
0xf322  ldc.i4.0
0xf323  br.s     loc_F329
0xf325  ldc.i4.1
0xf326  br.s     loc_F329
0xf328  ldc.i4.0
0xf329  stloc.0
0xf32a  ldarg.0
0xf32b  ldloc.0
0xf32c  brtrue.s loc_F338
0xf32e  ldarg.0
0xf32f  ldfld    class Microsoft.VisualStudio.Setup.Installer.ViewModels.IStatusBarViewModel Microsoft.VisualStudio.Setup.Installer.ViewModels.AggregateStatusBarViewModel::statusBar
0xf334  stloc.3
0xf335  ldloc.3
0xf336  br.s     loc_F340
0xf338  ldarg.0
0xf339  ldfld    class Microsoft.VisualStudio.Setup.Installer.ViewModels.IRemoteStatusBarViewModel Microsoft.VisualStudio.Setup.Installer.ViewModels.AggregateStatusBarViewModel::remoteStatusBar
0xf33e  stloc.3
0xf33f  ldloc.3
0xf340  call     instance void Microsoft.VisualStudio.Setup.Installer.ViewModels.AggregateStatusBarViewModel::set_ActiveStatusBarViewModel(class Microsoft.VisualStudio.Setup.Installer.ViewModels.IViewModel value)
0xf345  ret
```
