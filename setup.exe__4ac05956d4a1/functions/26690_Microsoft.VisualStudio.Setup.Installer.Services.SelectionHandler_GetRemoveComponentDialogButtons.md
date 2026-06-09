# Microsoft.VisualStudio.Setup.Installer.Services.SelectionHandler::GetRemoveComponentDialogButtons

- ea: `0x26690`
- end: `0x266da`
- name: `Microsoft.VisualStudio.Setup.Installer.Services.SelectionHandler::GetRemoveComponentDialogButtons`
- size: `74`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x90bb0`

## callees

- `0x4fe70`
- `0x4ff70`

## string_xrefs

- `0x2669a`: `RemoveButtonText`
- `0x266a4`: `remove`

## pseudocode

```c

```

## disassembly

```asm
0x26690  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.VisualStudio.Setup.Installer.Dialogs.IDialogButton>::.ctor()
0x26695  call     class [mscorlib]System.Resources.ResourceManager [Microsoft.VisualStudio.Setup.InstallerResources]Microsoft.VisualStudio.Setup.Installer.Resources::get_ResourceManager()
0x2669a  ldstr    aRemovebuttonte// "RemoveButtonText"
0x2669f  newobj   instance void Microsoft.VisualStudio.Setup.Installer.Dialogs.ButtonResources::.ctor(class [mscorlib]System.Resources.ResourceManager resources, string resourceId)
0x266a4  ldstr    aRemove// "remove"
0x266a9  ldc.i4.0
0x266aa  newobj   instance void Microsoft.VisualStudio.Setup.Installer.Dialogs.DialogButton::.ctor(class Microsoft.VisualStudio.Setup.Installer.Dialogs.ButtonResources resources, string buttonId, [opt] valuetype Microsoft.VisualStudio.Setup.Installer.Dialogs.DialogButtonType buttonType)
0x266af  stloc.0
0x266b0  dup
0x266b1  ldloc.0
0x266b2  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.VisualStudio.Setup.Installer.Dialogs.IDialogButton>::Add(var<u1>)
0x266b7  call     class [mscorlib]System.Resources.ResourceManager [Microsoft.VisualStudio.Setup.InstallerResources]Microsoft.VisualStudio.Setup.Installer.Resources::get_ResourceManager()
0x266bc  ldstr    aCancelbuttonte// "CancelButtonText"
0x266c1  newobj   instance void Microsoft.VisualStudio.Setup.Installer.Dialogs.ButtonResources::.ctor(class [mscorlib]System.Resources.ResourceManager resources, string resourceId)
0x266c6  ldstr    aCancel// "cancel"
0x266cb  ldc.i4.3
0x266cc  newobj   instance void Microsoft.VisualStudio.Setup.Installer.Dialogs.DialogButton::.ctor(class Microsoft.VisualStudio.Setup.Installer.Dialogs.ButtonResources resources, string buttonId, [opt] valuetype Microsoft.VisualStudio.Setup.Installer.Dialogs.DialogButtonType buttonType)
0x266d1  stloc.1
0x266d2  dup
0x266d3  ldloc.1
0x266d4  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.VisualStudio.Setup.Installer.Dialogs.IDialogButton>::Add(var<u1>)
0x266d9  ret
```
