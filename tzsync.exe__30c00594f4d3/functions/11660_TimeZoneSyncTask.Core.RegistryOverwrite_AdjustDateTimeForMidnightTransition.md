# TimeZoneSyncTask.Core.RegistryOverwrite::AdjustDateTimeForMidnightTransition

- ea: `0x11660`
- end: `0x116c7`
- name: `TimeZoneSyncTask.Core.RegistryOverwrite::AdjustDateTimeForMidnightTransition`
- size: `103`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, service_task`

## callers

- `0x116d0`

## callees

- `0x11660`
- `0x14550`

## pseudocode

```c

```

## disassembly

```asm
0x11660  newobj   instance void <>c__DisplayClass4_0::.ctor()
0x11665  stloc.0
0x11666  ldloc.0
0x11667  ldarg.0
0x11668  stfld    valuetype [mscorlib]System.DateTime <>c__DisplayClass4_0::dt
0x1166d  ldarg.1
0x1166e  ldloc.0
0x1166f  ldftn    instance bool <>c__DisplayClass4_0::<AdjustDateTimeForMidnightTransition>b__0(class TimeZoneSyncTask.Data.Transition t)
0x11675  newobj   instance void class [mscorlib]System.Func`2<class TimeZoneSyncTask.Data.Transition, bool>::.ctor(object, native int)
0x1167a  call     T0x2B00002B
0x1167f  ldsfld   class [mscorlib]System.Func`2<class TimeZoneSyncTask.Data.Transition, valuetype TimeZoneSyncTask.Data.MidnightTransitionType> <>c::<>9__4_1
0x11684  dup
0x11685  brtrue.s loc_1169E
0x11687  pop
0x11688  ldsfld   class <>c <>c::<>9
0x1168d  ldftn    instance valuetype TimeZoneSyncTask.Data.MidnightTransitionType <>c::<AdjustDateTimeForMidnightTransition>b__4_1(class TimeZoneSyncTask.Data.Transition t)
0x11693  newobj   instance void class [mscorlib]System.Func`2<class TimeZoneSyncTask.Data.Transition, valuetype TimeZoneSyncTask.Data.MidnightTransitionType>::.ctor(object, native int)
0x11698  dup
0x11699  stsfld   class [mscorlib]System.Func`2<class TimeZoneSyncTask.Data.Transition, valuetype TimeZoneSyncTask.Data.MidnightTransitionType> <>c::<>9__4_1
0x1169e  call     T0x2B00002C
0x116a3  call     T0x2B00002D
0x116a8  ldc.i4.2
0x116a9  bne.un.s loc_116C0
0x116ab  ldloc.0
0x116ac  ldflda   valuetype [mscorlib]System.DateTime <>c__DisplayClass4_0::dt
0x116b1  ldc.r8   -1.0
0x116ba  call     instance valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::AddMilliseconds(float64)
0x116bf  ret
0x116c0  ldloc.0
0x116c1  ldfld    valuetype [mscorlib]System.DateTime <>c__DisplayClass4_0::dt
0x116c6  ret
```
