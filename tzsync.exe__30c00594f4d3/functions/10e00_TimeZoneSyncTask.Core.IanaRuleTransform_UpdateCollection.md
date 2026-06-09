# TimeZoneSyncTask.Core.IanaRuleTransform::UpdateCollection

- ea: `0x10e00`
- end: `0x10e95`
- name: `TimeZoneSyncTask.Core.IanaRuleTransform::UpdateCollection`
- size: `149`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `service_task, installer_update`

## callers

- `0x10970`

## callees

- `0xf760`
- `0x10e00`

## pseudocode

```c

```

## disassembly

```asm
0x10e00  ldarg.1
0x10e01  callvirt instance valuetype [mscorlib]System.DateTime TimeZoneSyncTask.Data.Transition::get_TransitionTime()
0x10e06  stloc.0
0x10e07  ldloca.s 0
0x10e09  call     instance int32 [mscorlib]System.DateTime::get_Year()
0x10e0e  ldarg.2
0x10e0f  ldc.i4.1
0x10e10  sub
0x10e11  blt.s    loc_10E37
0x10e13  ldarg.0
0x10e14  callvirt instance valuetype [mscorlib]System.DateTime TimeZoneSyncTask.Data.Transition::get_TransitionTime()
0x10e19  stloc.0
0x10e1a  ldloca.s 0
0x10e1c  call     instance int32 [mscorlib]System.DateTime::get_Year()
0x10e21  ldarg.2
0x10e22  ldc.i4.1
0x10e23  sub
0x10e24  bge.s    loc_10E37
0x10e26  ldarg.s  4
0x10e28  ldarg.0
0x10e29  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class TimeZoneSyncTask.Data.Transition>::Add(var<u1>)
0x10e2e  ldarg.s  4
0x10e30  ldarg.1
0x10e31  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class TimeZoneSyncTask.Data.Transition>::Add(var<u1>)
0x10e36  ret
0x10e37  ldarg.1
0x10e38  callvirt instance valuetype [mscorlib]System.DateTime TimeZoneSyncTask.Data.Transition::get_TransitionTime()
0x10e3d  stloc.0
0x10e3e  ldloca.s 0
0x10e40  call     instance int32 [mscorlib]System.DateTime::get_Year()
0x10e45  ldarg.3
0x10e46  ldc.i4.1
0x10e47  add
0x10e48  ble.s    loc_10E66
0x10e4a  ldarg.0
0x10e4b  callvirt instance valuetype [mscorlib]System.DateTime TimeZoneSyncTask.Data.Transition::get_TransitionTime()
0x10e50  stloc.0
0x10e51  ldloca.s 0
0x10e53  call     instance int32 [mscorlib]System.DateTime::get_Year()
0x10e58  ldarg.3
0x10e59  ldc.i4.1
0x10e5a  add
0x10e5b  bgt.s    loc_10E66
0x10e5d  ldarg.s  4
0x10e5f  ldarg.1
0x10e60  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class TimeZoneSyncTask.Data.Transition>::Add(var<u1>)
0x10e65  ret
0x10e66  ldarg.1
0x10e67  callvirt instance valuetype [mscorlib]System.DateTime TimeZoneSyncTask.Data.Transition::get_TransitionTime()
0x10e6c  stloc.0
0x10e6d  ldloca.s 0
0x10e6f  call     instance int32 [mscorlib]System.DateTime::get_Year()
0x10e74  ldarg.2
0x10e75  ldc.i4.1
0x10e76  sub
0x10e77  blt.s    loc_10E94
0x10e79  ldarg.1
0x10e7a  callvirt instance valuetype [mscorlib]System.DateTime TimeZoneSyncTask.Data.Transition::get_TransitionTime()
0x10e7f  stloc.0
0x10e80  ldloca.s 0
0x10e82  call     instance int32 [mscorlib]System.DateTime::get_Year()
0x10e87  ldarg.3
0x10e88  ldc.i4.1
0x10e89  add
0x10e8a  bgt.s    loc_10E94
0x10e8c  ldarg.s  4
0x10e8e  ldarg.1
0x10e8f  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class TimeZoneSyncTask.Data.Transition>::Add(var<u1>)
0x10e94  ret
```
