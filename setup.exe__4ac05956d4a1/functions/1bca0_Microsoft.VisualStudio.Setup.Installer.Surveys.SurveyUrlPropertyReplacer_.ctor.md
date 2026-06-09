# Microsoft.VisualStudio.Setup.Installer.Surveys.SurveyUrlPropertyReplacer::.ctor

- ea: `0x1bca0`
- end: `0x1bcf2`
- name: `Microsoft.VisualStudio.Setup.Installer.Surveys.SurveyUrlPropertyReplacer::.ctor`
- size: `82`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `installer_update, broker_com_uri`

## callers

- `0x6ac50`

## string_xrefs

- `0x1bcb2`: `startToken`
- `0x1bcbd`: `endToken`

## pseudocode

```c

```

## disassembly

```asm
0x1bca0  ldarg.0
0x1bca1  call     instance void [mscorlib]System.Object::.ctor()
0x1bca6  ldarg.1
0x1bca7  ldstr    aPropertyregex// "propertyRegex"
0x1bcac  call     void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Validate::IsNotNullOrEmpty(string, string)
0x1bcb1  ldarg.2
0x1bcb2  ldstr    aStarttoken// "startToken"
0x1bcb7  call     void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Validate::IsNotNullOrEmpty(string, string)
0x1bcbc  ldarg.3
0x1bcbd  ldstr    aEndtoken// "endToken"
0x1bcc2  call     void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Validate::IsNotNullOrEmpty(string, string)
0x1bcc7  ldstr    a01_1// "(?<{0}>{1})"
0x1bccc  ldsfld   string Microsoft.VisualStudio.Setup.Installer.Surveys.SurveyUrlPropertyReplacer::PropertyNameCaptureGroup
0x1bcd1  ldarg.1
0x1bcd2  call     string [mscorlib]System.String::Format(string, object, object)
0x1bcd7  stloc.0
0x1bcd8  ldarg.0
0x1bcd9  ldstr    a012_0// "{0}{1}{2}"
0x1bcde  ldarg.2
0x1bcdf  ldloc.0
0x1bce0  ldarg.3
0x1bce1  call     string [mscorlib]System.String::Format(string, object, object, object)
0x1bce6  ldc.i4.1
0x1bce7  newobj   instance void [System]System.Text.RegularExpressions.Regex::.ctor(string, valuetype [System]System.Text.RegularExpressions.RegexOptions)
0x1bcec  stfld    class [System]System.Text.RegularExpressions.Regex Microsoft.VisualStudio.Setup.Installer.Surveys.SurveyUrlPropertyReplacer::urlPropertyRegex
0x1bcf1  ret
```
