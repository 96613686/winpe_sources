# TimeZoneSyncTask.OneSettings.OneSettingsWrapperFile::ReadOneSettingsDataFromFile

- ea: `0xe4b0`
- end: `0xe4f8`
- name: `TimeZoneSyncTask.OneSettings.OneSettingsWrapperFile::ReadOneSettingsDataFromFile`
- size: `72`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0xe490`

## callees

- `0xe4b0`

## string_xrefs

- `0xe4b0`: `%ProgramData%\\Microsoft\\Windows\\OneSettings\DSTTZSYNC.json`

## pseudocode

```c

```

## disassembly

```asm
0xe4b0  ldstr    aProgramdataMic// "%ProgramData%\\\\Microsoft\\\\Windows\\"...
0xe4b5  call     string [mscorlib]System.Environment::ExpandEnvironmentVariables(string)
0xe4ba  stloc.0
0xe4bb  ldloc.0
0xe4bc  newobj   instance void [mscorlib]System.IO.StreamReader::.ctor(string)
0xe4c1  stloc.1
0xe4c2  ldloc.1
0xe4c3  callvirt instance string [mscorlib]System.IO.TextReader::ReadToEnd()
0xe4c8  stloc.2
0xe4c9  ldarg.0
0xe4ca  ldloc.2
0xe4cb  call     class [Windows]Windows.Data.Json.JsonObject [Windows]Windows.Data.Json.JsonObject::Parse(string)
0xe4d0  stfld    class [Windows]Windows.Data.Json.JsonObject TimeZoneSyncTask.OneSettings.OneSettingsWrapperFile::oneSettingsData
0xe4d5  leave.s  loc_E4E1
0xe4d7  ldloc.1
0xe4d8  brfalse.s loc_E4E0
0xe4da  ldloc.1
0xe4db  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xe4e0  endfinally
0xe4e1  leave.s  loc_E4F7
0xe4e3  pop
0xe4e4  ldarg.0
0xe4e5  ldnull
0xe4e6  stfld    class [Windows]Windows.Data.Json.JsonObject TimeZoneSyncTask.OneSettings.OneSettingsWrapperFile::oneSettingsData
0xe4eb  ldstr    aOnesettingsFil// "OneSettings file not found"
0xe4f0  call     void [System]System.Diagnostics.Trace::TraceError(string)
0xe4f5  rethrow
0xe4f7  ret
```
