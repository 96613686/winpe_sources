# Microsoft.VisualStudio.Setup.Installer.Feedback.FeedbackConfiguration::.ctor

- ea: `0x4d880`
- end: `0x4d915`
- name: `Microsoft.VisualStudio.Setup.Installer.Feedback.FeedbackConfiguration::.ctor`
- size: `149`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x85e20`

## callees

- `0x4d880`

## string_xrefs

- `0x4d888`: `feedbackExePath`
- `0x4d894`: `template`

## pseudocode

```c

```

## disassembly

```asm
0x4d880  ldarg.0
0x4d881  call     instance void [mscorlib]System.Object::.ctor()
0x4d886  ldarg.s  6
0x4d888  ldstr    aFeedbackexepat// "feedbackExePath"
0x4d88d  call     void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Validate::IsNotNullOrEmpty(string, string)
0x4d892  ldarg.s  7
0x4d894  ldstr    aTemplate// "template"
0x4d899  call     void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Validate::IsNotNull(object, string)
0x4d89e  ldarg.0
0x4d89f  ldarg.1
0x4d8a0  stfld    bool Microsoft.VisualStudio.Setup.Installer.Feedback.FeedbackConfiguration::<IsOptedInForDataCollection>k__BackingField
0x4d8a5  ldarg.0
0x4d8a6  ldarg.2
0x4d8a7  stfld    bool Microsoft.VisualStudio.Setup.Installer.Feedback.FeedbackConfiguration::<IsInternal>k__BackingField
0x4d8ac  ldarg.0
0x4d8ad  ldarg.3
0x4d8ae  stfld    bool Microsoft.VisualStudio.Setup.Installer.Feedback.FeedbackConfiguration::<IsRecordingDisabled>k__BackingField
0x4d8b3  ldarg.0
0x4d8b4  ldarg.s  4
0x4d8b6  stfld    bool Microsoft.VisualStudio.Setup.Installer.Feedback.FeedbackConfiguration::<IsWAMEnabledInVS>k__BackingField
0x4d8bb  ldarg.0
0x4d8bc  ldarg.s  5
0x4d8be  stfld    bool Microsoft.VisualStudio.Setup.Installer.Feedback.FeedbackConfiguration::<UseWAMEnabledClientId>k__BackingField
0x4d8c3  ldarg.0
0x4d8c4  ldarg.s  8
0x4d8c6  stfld    valuetype [mscorlib]System.Guid Microsoft.VisualStudio.Setup.Installer.Feedback.FeedbackConfiguration::<FeedbackSessionId>k__BackingField
0x4d8cb  ldarg.0
0x4d8cc  ldarg.s  9
0x4d8ce  stfld    valuetype Microsoft.VisualStudio.Setup.Installer.Feedback.FeedbackEntry Microsoft.VisualStudio.Setup.Installer.Feedback.FeedbackConfiguration::<Entry>k__BackingField
0x4d8d3  ldarg.0
0x4d8d4  ldarg.s  6
0x4d8d6  stfld    string Microsoft.VisualStudio.Setup.Installer.Feedback.FeedbackConfiguration::<FeedbackExePath>k__BackingField
0x4d8db  ldarg.0
0x4d8dc  ldarg.s  0xA
0x4d8de  stfld    string Microsoft.VisualStudio.Setup.Installer.Feedback.FeedbackConfiguration::<ScreenshotPath>k__BackingField
0x4d8e3  ldarg.0
0x4d8e4  ldarg.s  0xB
0x4d8e6  stfld    string Microsoft.VisualStudio.Setup.Installer.Feedback.FeedbackConfiguration::<ScreenshotThumbPath>k__BackingField
0x4d8eb  ldarg.0
0x4d8ec  ldarg.s  0xC
0x4d8ee  dup
0x4d8ef  brtrue.s loc_4D8F7
0x4d8f1  pop
0x4d8f2  call     T0x2B000032
0x4d8f7  stfld    class [mscorlib]System.Collections.Generic.IEnumerable`1<string> Microsoft.VisualStudio.Setup.Installer.Feedback.FeedbackConfiguration::<FilesToUpload>k__BackingField
0x4d8fc  ldarg.0
0x4d8fd  ldarg.s  7
0x4d8ff  stfld    class Microsoft.VisualStudio.Setup.Installer.Feedback.FeedbackTemplate Microsoft.VisualStudio.Setup.Installer.Feedback.FeedbackConfiguration::<ItemTemplate>k__BackingField
0x4d904  ldarg.0
0x4d905  ldarg.s  0xD
0x4d907  stfld    string Microsoft.VisualStudio.Setup.Installer.Feedback.FeedbackConfiguration::<InitialSearchText>k__BackingField
0x4d90c  ldarg.0
0x4d90d  ldarg.s  0xE
0x4d90f  stfld    string Microsoft.VisualStudio.Setup.Installer.Feedback.FeedbackConfiguration::<InitialReproText>k__BackingField
0x4d914  ret
```
