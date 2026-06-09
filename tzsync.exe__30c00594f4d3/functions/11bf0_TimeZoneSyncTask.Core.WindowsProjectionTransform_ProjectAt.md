# TimeZoneSyncTask.Core.WindowsProjectionTransform::ProjectAt

- ea: `0x11bf0`
- end: `0x11c63`
- name: `TimeZoneSyncTask.Core.WindowsProjectionTransform::ProjectAt`
- size: `115`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `service_task`

## callers

- `0x140e0`

## callees

- `0x10770`
- `0x14650`

## pseudocode

```c

```

## disassembly

```asm
0x11bf0  newobj   instance void <>c__DisplayClass0_0::.ctor()
0x11bf5  stloc.0
0x11bf6  ldloc.0
0x11bf7  ldarg.0
0x11bf8  stfld    valuetype [mscorlib]System.DateTime <>c__DisplayClass0_0::dtSync
0x11bfd  ldloc.0
0x11bfe  ldarg.2
0x11bff  stfld    int32 <>c__DisplayClass0_0::year
0x11c04  ldloc.0
0x11c05  ldarg.1
0x11c06  stfld    valuetype [mscorlib]System.DateTime <>c__DisplayClass0_0::dtSyncUtc
0x11c0b  ldloc.0
0x11c0c  ldarg.s  4
0x11c0e  stfld    class [mscorlib]System.Collections.Generic.IEnumerable`1<class TimeZoneSyncTask.Data.Transition> <>c__DisplayClass0_0::transitions
0x11c13  ldloc.0
0x11c14  ldarg.3
0x11c15  stfld    class TimeZoneSyncTask.Data.WindowsProjectionSet <>c__DisplayClass0_0::projectionSet
0x11c1a  ldloc.0
0x11c1b  ldfld    class TimeZoneSyncTask.Data.WindowsProjectionSet <>c__DisplayClass0_0::projectionSet
0x11c20  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerable`1<valuetype TimeZoneSyncTask.Data.WindowsProjection> TimeZoneSyncTask.Data.WindowsProjectionSet::EnumerateWindowsProjectionByYear()
0x11c25  ldloc.0
0x11c26  ldftn    instance bool <>c__DisplayClass0_0::<ProjectAt>b__0(valuetype TimeZoneSyncTask.Data.WindowsProjection w)
0x11c2c  newobj   instance void class [mscorlib]System.Func`2<valuetype TimeZoneSyncTask.Data.WindowsProjection, bool>::.ctor(object, native int)
0x11c31  call     T0x2B000030
0x11c36  ldloc.0
0x11c37  ldftn    instance bool <>c__DisplayClass0_0::<ProjectAt>b__1(valuetype TimeZoneSyncTask.Data.WindowsProjection w)
0x11c3d  newobj   instance void class [mscorlib]System.Func`2<valuetype TimeZoneSyncTask.Data.WindowsProjection, bool>::.ctor(object, native int)
0x11c42  call     T0x2B000030
0x11c47  ldloc.0
0x11c48  ldftn    instance valuetype [mscorlib]System.TimeSpan <>c__DisplayClass0_0::<ProjectAt>b__2(valuetype TimeZoneSyncTask.Data.WindowsProjection w)
0x11c4e  newobj   instance void class [mscorlib]System.Func`2<valuetype TimeZoneSyncTask.Data.WindowsProjection, valuetype [mscorlib]System.TimeSpan>::.ctor(object, native int)
0x11c53  call     T0x2B000031
0x11c58  call     T0x2B000032
0x11c5d  newobj   instance void valuetype [mscorlib]System.Nullable`1<valuetype TimeZoneSyncTask.Data.WindowsProjection>::.ctor(var<u1>)
0x11c62  ret
```
