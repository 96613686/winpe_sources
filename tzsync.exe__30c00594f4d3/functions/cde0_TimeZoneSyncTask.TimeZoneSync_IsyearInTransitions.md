# TimeZoneSyncTask.TimeZoneSync::IsyearInTransitions

- ea: `0xcde0`
- end: `0xce23`
- name: `TimeZoneSyncTask.TimeZoneSync::IsyearInTransitions`
- size: `67`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `service_task`

## callers

- `0xc6e0`

## callees

- `0xcde0`
- `0xf760`

## pseudocode

```c

```

## disassembly

```asm
0xcde0  ldarg.1
0xcde1  callvirt instance valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<var<u1>> class [mscorlib]System.Collections.Generic.List`1<class TimeZoneSyncTask.Data.Transition>::GetEnumerator()
0xcde6  stloc.0
0xcde7  br.s     loc_CE06
0xcde9  ldloca.s 0
0xcdeb  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class TimeZoneSyncTask.Data.Transition>::get_Current()
0xcdf0  stloc.1
0xcdf1  ldarg.0
0xcdf2  ldloc.1
0xcdf3  callvirt instance valuetype [mscorlib]System.DateTime TimeZoneSyncTask.Data.Transition::get_TransitionTime()
0xcdf8  stloc.2
0xcdf9  ldloca.s 2
0xcdfb  call     instance int32 [mscorlib]System.DateTime::get_Year()
0xce00  bne.un.s loc_CE06
0xce02  ldc.i4.1
0xce03  stloc.3
0xce04  leave.s  loc_CE21
0xce06  ldloca.s 0
0xce08  call     instance bool valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class TimeZoneSyncTask.Data.Transition>::MoveNext()
0xce0d  brtrue.s loc_CDE9
0xce0f  leave.s  loc_CE1F
0xce11  ldloca.s 0
0xce13  constrained. valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class TimeZoneSyncTask.Data.Transition>
0xce19  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xce1e  endfinally
0xce1f  ldc.i4.0
0xce20  ret
0xce21  ldloc.3
0xce22  ret
```
