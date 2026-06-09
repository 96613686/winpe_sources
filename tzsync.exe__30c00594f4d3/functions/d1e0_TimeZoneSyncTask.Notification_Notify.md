# TimeZoneSyncTask.Notification::Notify

- ea: `0xd1e0`
- end: `0xd244`
- name: `TimeZoneSyncTask.Notification::Notify`
- size: `100`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `service_task`

## callers

- `0xc470`

## callees

- `0x1050`
- `0xcfb0`
- `0xd190`
- `0xd1e0`

## pseudocode

```c

```

## disassembly

```asm
0xd1e0  ldloca.s 0
0xd1e2  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype Type, unsigned int32[]> TimeZoneSyncTask.Notification::WNFStateNames
0xd1e7  ldarg.0
0xd1e8  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype Type, unsigned int32[]>::get_Item(void)
0xd1ed  stfld    unsigned int32[] TimeZoneSyncTask.WNF_STATE_NAME::Data
0xd1f2  ldloc.0
0xd1f3  ldsfld   native int [mscorlib]System.IntPtr::Zero
0xd1f8  ldsfld   native int [mscorlib]System.IntPtr::Zero
0xd1fd  ldc.i4.0
0xd1fe  ldsfld   native int [mscorlib]System.IntPtr::Zero
0xd203  call     int32 TimeZoneSyncTask.NativeMethods::RtlPublishWnfStateData(valuetype TimeZoneSyncTask.WNF_STATE_NAME StateName, native int TypeId, native int StateData, unsigned int32 StateDataLength, native int ExplicitScope)
0xd208  stloc.1
0xd209  call     bool Microsoft.Windows.Staging.Features.Feature_FixBug2886555_TryTraceCatch::get_IsEnabled()
0xd20e  brfalse.s loc_D22A
0xd210  ldstr    aRtlpublishwnfs// "RtlPublishWnfStateData() returned with "...
0xd215  ldc.i4.1
0xd216  newarr   [mscorlib]System.Object
0xd21b  dup
0xd21c  ldc.i4.0
0xd21d  ldloc.1
0xd21e  box      [mscorlib]System.Int32
0xd223  stelem.ref
0xd224  call     void TimeZoneSyncTask.TimeZoneSyncTelemetryLogs::TraceInfo(string format, object[] args)
0xd229  ret
0xd22a  ldstr    aRtlpublishwnfs// "RtlPublishWnfStateData() returned with "...
0xd22f  ldc.i4.1
0xd230  newarr   [mscorlib]System.Object
0xd235  dup
0xd236  ldc.i4.0
0xd237  ldloc.1
0xd238  box      [mscorlib]System.Int32
0xd23d  stelem.ref
0xd23e  call     void [System]System.Diagnostics.Trace::TraceInformation(string, object[])
0xd243  ret
```
