# TimeZoneSyncTask.OneSettings.OneSettingsWrapperDLL::ReadOneSetingsDataFromDLL

- ea: `0xe550`
- end: `0xe5bd`
- name: `TimeZoneSyncTask.OneSettings.OneSettingsWrapperDLL::ReadOneSetingsDataFromDLL`
- size: `109`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, loader_planting, service_task`

## callers

- `0xe530`

## callees

- `0xe520`
- `0xe550`
- `0x141d0`

## string_xrefs

- `0xe569`: `Failed to read OneSettings data from DLL Error: {0}`

## pseudocode

```c

```

## disassembly

```asm
0xe550  ldc.i4.0
0xe551  ldsfld   native int [mscorlib]System.IntPtr::Zero
0xe556  stloc.0
0xe557  ldloca.s 0
0xe559  call     int64 TimeZoneSyncTask.OneSettings.OneSettingsWrapperDLL::ReadOneSettingsData(bool flag, [out] native int& data)
0xe55e  stloc.1
0xe55f  ldloc.1
0xe560  brfalse.s loc_E57F
0xe562  ldarg.0
0xe563  ldnull
0xe564  stfld    class [Windows]Windows.Data.Json.JsonObject TimeZoneSyncTask.OneSettings.OneSettingsWrapperDLL::oneSettingsData
0xe569  ldstr    aFailedToReadOn// "Failed to read OneSettings data from DL"...
0xe56e  ldloc.1
0xe56f  box      [mscorlib]System.Int64
0xe574  call     string [mscorlib]System.String::Format(string, object)
0xe579  newobj   instance void OneSettingsClientException::.ctor(string msg)
0xe57e  throw
0xe57f  ldloc.0
0xe580  call     string [mscorlib]System.Runtime.InteropServices.Marshal::PtrToStringAuto(native int)
0xe585  stloc.2
0xe586  ldstr    aDataFromOneset// "Data From OneSettings:: {0}"
0xe58b  ldc.i4.1
0xe58c  newarr   [mscorlib]System.Object
0xe591  dup
0xe592  ldc.i4.0
0xe593  ldloc.2
0xe594  stelem.ref
0xe595  call     void [System]System.Diagnostics.Trace::TraceInformation(string, object[])
0xe59a  ldarg.0
0xe59b  ldloc.2
0xe59c  call     class [Windows]Windows.Data.Json.JsonObject [Windows]Windows.Data.Json.JsonObject::Parse(string)
0xe5a1  stfld    class [Windows]Windows.Data.Json.JsonObject TimeZoneSyncTask.OneSettings.OneSettingsWrapperDLL::oneSettingsData
0xe5a6  leave.s  loc_E5BC
0xe5a8  ldloc.0
0xe5a9  ldsfld   native int [mscorlib]System.IntPtr::Zero
0xe5ae  call     bool [mscorlib]System.IntPtr::op_Inequality(native int, native int)
0xe5b3  brfalse.s loc_E5BB
0xe5b5  ldloc.0
0xe5b6  call     void [mscorlib]System.Runtime.InteropServices.Marshal::FreeHGlobal(native int)
0xe5bb  endfinally
0xe5bc  ret
```
