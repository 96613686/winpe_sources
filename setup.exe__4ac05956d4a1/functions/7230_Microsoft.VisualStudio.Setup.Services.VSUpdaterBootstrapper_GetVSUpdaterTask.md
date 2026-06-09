# Microsoft.VisualStudio.Setup.Services.VSUpdaterBootstrapper::GetVSUpdaterTask

- ea: `0x7230`
- end: `0x72b7`
- name: `Microsoft.VisualStudio.Setup.Services.VSUpdaterBootstrapper::GetVSUpdaterTask`
- size: `135`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x71b0`
- `0x71f0`

## callees

- `0x7120`
- `0x7140`
- `0x7700`

## string_xrefs

- `0x725d`: `VSUpdater task to check for updates.`

## pseudocode

```c

```

## disassembly

```asm
0x7230  call     class [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Services.ScheduledTask.TaskDefinitionBuilder [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Services.ScheduledTask.TaskDefinitionBuilder::Create()
0x7235  ldsfld   string Microsoft.VisualStudio.Setup.Services.VSUpdaterBootstrapper::VSUpdaterTaskName
0x723a  callvirt instance class [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Services.ScheduledTask.TaskDefinitionBuilder [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Services.ScheduledTask.TaskDefinitionBuilder::WithName(string)
0x723f  ldsfld   string Microsoft.VisualStudio.Setup.Services.VSUpdaterBootstrapper::VSUpdaterTaskDirectory
0x7244  callvirt instance class [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Services.ScheduledTask.TaskDefinitionBuilder [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Services.ScheduledTask.TaskDefinitionBuilder::WithDirectory(string)
0x7249  callvirt instance class [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Services.ScheduledTask.TaskDefinitionBuilder [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Services.ScheduledTask.TaskDefinitionBuilder::RunOnlyIfNetworkAvailable()
0x724e  callvirt instance class [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Services.ScheduledTask.TaskDefinitionBuilder [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Services.ScheduledTask.TaskDefinitionBuilder::DisallowStartIfOnBatteries()
0x7253  callvirt instance class [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Services.ScheduledTask.TaskDefinitionBuilder [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Services.ScheduledTask.TaskDefinitionBuilder::WakeToRun()
0x7258  callvirt instance class [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Services.ScheduledTask.TaskDefinitionBuilder [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Services.ScheduledTask.TaskDefinitionBuilder::WithDefaultAuthor()
0x725d  ldstr    aVsupdaterTaskT// "VSUpdater task to check for updates."
0x7262  callvirt instance class [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Services.ScheduledTask.TaskDefinitionBuilder [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Services.ScheduledTask.TaskDefinitionBuilder::WithDescription(string)
0x7267  ldarg.0
0x7268  ldfld    class Microsoft.VisualStudio.Setup.ServiceOptions.VSUpdaterBootstrapperServiceOptions Microsoft.VisualStudio.Setup.Services.VSUpdaterBootstrapper::serviceOptions
0x726d  callvirt instance class [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Services.IAccountProfileService Microsoft.VisualStudio.Setup.ServiceOptions.VSUpdaterBootstrapperServiceOptions::get_AccountProfileService()
0x7272  callvirt instance class [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Services.ScheduledTask.TaskDefinitionBuilder [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Services.ScheduledTask.TaskDefinitionBuilder::RunAsCurrentUser(class [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Services.IAccountProfileService)
0x7277  ldarg.0
0x7278  ldfld    class Microsoft.VisualStudio.Setup.ServiceOptions.VSUpdaterBootstrapperServiceOptions Microsoft.VisualStudio.Setup.Services.VSUpdaterBootstrapper::serviceOptions
0x727d  callvirt instance class [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Services.IAccountProfileService Microsoft.VisualStudio.Setup.ServiceOptions.VSUpdaterBootstrapperServiceOptions::get_AccountProfileService()
0x7282  ldc.i4.1
0x7283  ldc.i4.3
0x7284  callvirt instance class [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Services.ScheduledTask.TaskDefinitionBuilder [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Services.ScheduledTask.TaskDefinitionBuilder::WithCurrentUserPrincipal(class [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Services.IAccountProfileService, valuetype [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Services.ScheduledTask.TaskRunLevel, valuetype [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Services.ScheduledTask.TaskLogonType)
0x7289  ldarg.0
0x728a  call     instance string Microsoft.VisualStudio.Setup.Services.VSUpdaterBootstrapper::GetVSUpdaterPath()
0x728f  ldsfld   string [mscorlib]System.String::Empty
0x7294  ldarg.0
0x7295  call     instance string Microsoft.VisualStudio.Setup.Services.VSUpdaterBootstrapper::GetInstallationDirectory()
0x729a  callvirt instance class [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Services.ScheduledTask.TaskDefinitionBuilder [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Services.ScheduledTask.TaskDefinitionBuilder::WithExecAction(string, string, string)
0x729f  ldc.i4.7
0x72a0  ldc.i4.0
0x72a1  ldc.i4.0
0x72a2  callvirt instance class [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Services.ScheduledTask.TaskDefinitionBuilder [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Services.ScheduledTask.TaskDefinitionBuilder::WithOffsetDailyTimeTrigger(int32, int32, int32)
0x72a7  ldc.i4.s 0x14
0x72a9  ldc.i4.s 0xF
0x72ab  ldc.i4.0
0x72ac  callvirt instance class [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Services.ScheduledTask.TaskDefinitionBuilder [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Services.ScheduledTask.TaskDefinitionBuilder::WithOffsetDailyTimeTrigger(int32, int32, int32)
0x72b1  callvirt instance class [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Services.ScheduledTask.TaskDefinition [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Services.ScheduledTask.TaskDefinitionBuilder::Build()
0x72b6  ret
```
