# Microsoft.VisualStudio.Setup.Installer.Commands.OperationResultHandlerBase::HandleNonInteractiveOperationCompletedAsync

- ea: `0x54d60`
- end: `0x54db5`
- name: `Microsoft.VisualStudio.Setup.Installer.Commands.OperationResultHandlerBase::HandleNonInteractiveOperationCompletedAsync`
- size: `85`
- prototype: ``
- caller_count: `4`
- callee_count: `5`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x319f0`
- `0x51440`
- `0x53980`
- `0x89cf0`

## callees

- `0x229c0`
- `0x2ba50`
- `0x54cd0`
- `0x54d60`
- `0x54dc0`

## string_xrefs

- `0x54d81`: `Install failed`
- `0x54d97`: `Extensions failed to install`

## pseudocode

```c

```

## disassembly

```asm
0x54d60  ldarg.0
0x54d61  ldarg.1
0x54d62  call     instance int32 Microsoft.VisualStudio.Setup.Installer.Commands.OperationResultHandlerBase::GetErrorCode(class [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Services.Installer.InstallOperationResult result)
0x54d67  stloc.0
0x54d68  ldnull
0x54d69  stloc.1
0x54d6a  ldarg.1
0x54d6b  callvirt instance class [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Services.Installer.ErrorInformation [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Services.Installer.InstallOperationResult::get_Error()
0x54d70  brfalse.s loc_54D89
0x54d72  ldarg.1
0x54d73  callvirt instance class [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Services.Installer.ErrorInformation [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Services.Installer.InstallOperationResult::get_Error()
0x54d78  callvirt instance string [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Services.Installer.ErrorInformation::get_NeutralMessage()
0x54d7d  dup
0x54d7e  brtrue.s loc_54D86
0x54d80  pop
0x54d81  ldstr    aInstallFailed// "Install failed"
0x54d86  stloc.1
0x54d87  br.s     loc_54D9D
0x54d89  ldarg.1
0x54d8a  callvirt instance class [mscorlib]System.Collections.Generic.IReadOnlyList`1<class [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Services.Installer.ExtensionDownloadFailure> [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Services.Installer.InstallOperationResult::get_FailedExtensionDownloads()
0x54d8f  callvirt instance int32 class [mscorlib]System.Collections.Generic.IReadOnlyCollection`1<class [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Services.Installer.ExtensionDownloadFailure>::get_Count()
0x54d94  ldc.i4.0
0x54d95  ble.s    loc_54D9D
0x54d97  ldstr    aExtensionsFail// "Extensions failed to install"
0x54d9c  stloc.1
0x54d9d  ldarg.0
0x54d9e  call     instance class Microsoft.VisualStudio.Setup.Installer.ServiceOptions.CommandHandlerServiceOptions Microsoft.VisualStudio.Setup.Installer.Commands.OperationResultHandlerBase::get_ServiceOptions()
0x54da3  callvirt instance class Microsoft.VisualStudio.Setup.Installer.Services.IShutdownRequestService Microsoft.VisualStudio.Setup.Installer.ServiceOptions.CommandHandlerServiceOptions::get_ShutdownService()
0x54da8  ldloc.0
0x54da9  ldloc.1
0x54daa  callvirt instance void Microsoft.VisualStudio.Setup.Installer.Services.IShutdownRequestService::Shutdown(int32 exitCode, string message)
0x54daf  call     class [mscorlib]System.Threading.Tasks.Task [mscorlib]System.Threading.Tasks.Task::get_CompletedTask()
0x54db4  ret
```
