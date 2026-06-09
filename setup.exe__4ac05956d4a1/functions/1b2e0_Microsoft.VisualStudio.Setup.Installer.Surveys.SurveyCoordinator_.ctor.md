# Microsoft.VisualStudio.Setup.Installer.Surveys.SurveyCoordinator::.ctor

- ea: `0x1b2e0`
- end: `0x1b31d`
- name: `Microsoft.VisualStudio.Setup.Installer.Surveys.SurveyCoordinator::.ctor`
- size: `61`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x27630`

## string_xrefs

- `0x1b2e7`: `serviceOptions`
- `0x1b2fd`: `openUrlCommand`

## pseudocode

```c

```

## disassembly

```asm
0x1b2e0  ldarg.0
0x1b2e1  call     instance void [mscorlib]System.Object::.ctor()
0x1b2e6  ldarg.1
0x1b2e7  ldstr    aServiceoptions// "serviceOptions"
0x1b2ec  call     void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Validate::IsNotNull(object, string)
0x1b2f1  ldarg.2
0x1b2f2  ldstr    aSurveysettings// "surveySettingsRepository"
0x1b2f7  call     void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Validate::IsNotNull(object, string)
0x1b2fc  ldarg.3
0x1b2fd  ldstr    aOpenurlcommand// "openUrlCommand"
0x1b302  call     void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Validate::IsNotNull(object, string)
0x1b307  ldarg.0
0x1b308  ldarg.1
0x1b309  stfld    class Microsoft.VisualStudio.Setup.Installer.ServiceOptions.SurveysServiceOptions Microsoft.VisualStudio.Setup.Installer.Surveys.SurveyCoordinator::serviceOptions
0x1b30e  ldarg.0
0x1b30f  ldarg.2
0x1b310  stfld    class Microsoft.VisualStudio.Setup.Installer.Surveys.ISurveySettingsRepository Microsoft.VisualStudio.Setup.Installer.Surveys.SurveyCoordinator::surveySettingsRepository
0x1b315  ldarg.0
0x1b316  ldarg.3
0x1b317  stfld    class Microsoft.VisualStudio.Setup.Installer.Commands.ICommandHandler`1<class Microsoft.VisualStudio.Setup.Installer.RichUri> Microsoft.VisualStudio.Setup.Installer.Surveys.SurveyCoordinator::openUrlCommand
0x1b31c  ret
```
