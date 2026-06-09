# Properties::.cctor

- ea: `0x90640`
- end: `0x9067d`
- name: `Properties::.cctor`
- size: `61`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `installer_update`

## string_xrefs

- `0x90645`: `vsupdaterbootstrapper.`
- `0x90659`: `isInstalled`

## pseudocode

```c

```

## disassembly

```asm
0x90640  ldsfld   string Microsoft.VisualStudio.Setup.Installer.CommonInstallerTelemetryConstants::SetupEnginePropertyPrefix
0x90645  ldstr    aVsupdaterboots_0// "vsupdaterbootstrapper."
0x9064a  call     string [mscorlib]System.String::Concat(string, string)
0x9064f  stsfld   string Properties::Prefix
0x90654  ldsfld   string Properties::Prefix
0x90659  ldstr    aIsinstalled_0// "isInstalled"
0x9065e  call     string [mscorlib]System.String::Concat(string, string)
0x90663  stsfld   string Properties::IsInstalled
0x90668  ldsfld   string Properties::Prefix
0x9066d  ldstr    aFailurereason// "failureReason"
0x90672  call     string [mscorlib]System.String::Concat(string, string)
0x90677  stsfld   string Properties::FailureReason
0x9067c  ret
```
