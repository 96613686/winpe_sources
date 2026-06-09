# TimeZoneSyncTask.OneSettings.TimeZoneDSTSettings::RemoveOlderVersions

- ea: `0xe640`
- end: `0xe6db`
- name: `TimeZoneSyncTask.OneSettings.TimeZoneDSTSettings::RemoveOlderVersions`
- size: `155`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, service_task`

## callers

- `0xe1b0`

## callees

- `0xe0f0`
- `0xe640`

## pseudocode

```c

```

## disassembly

```asm
0xe640  ldarg.0
0xe641  ldfld    class [mscorlib]System.Collections.Generic.List`1<class TimeZoneSyncTask.OneSettings.DynamicDSTRules> TimeZoneSyncTask.OneSettings.TimeZoneDSTSettings::allDSTRules
0xe646  callvirt instance int32 class [mscorlib]System.Collections.Generic.List`1<class TimeZoneSyncTask.OneSettings.DynamicDSTRules>::get_Count()
0xe64b  ldc.i4.2
0xe64c  bge.s    loc_E64F
0xe64e  ret
0xe64f  ldarg.0
0xe650  ldfld    class [mscorlib]System.Collections.Generic.List`1<class TimeZoneSyncTask.OneSettings.DynamicDSTRules> TimeZoneSyncTask.OneSettings.TimeZoneDSTSettings::allDSTRules
0xe655  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class TimeZoneSyncTask.OneSettings.DynamicDSTRules>::Sort()
0xe65a  ldarg.0
0xe65b  ldfld    class [mscorlib]System.Collections.Generic.List`1<class TimeZoneSyncTask.OneSettings.DynamicDSTRules> TimeZoneSyncTask.OneSettings.TimeZoneDSTSettings::allDSTRules
0xe660  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class TimeZoneSyncTask.OneSettings.DynamicDSTRules>::Reverse()
0xe665  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<class TimeZoneSyncTask.OneSettings.DynamicDSTRules>::.ctor()
0xe66a  stloc.0
0xe66b  ldloc.0
0xe66c  ldarg.0
0xe66d  ldfld    class [mscorlib]System.Collections.Generic.List`1<class TimeZoneSyncTask.OneSettings.DynamicDSTRules> TimeZoneSyncTask.OneSettings.TimeZoneDSTSettings::allDSTRules
0xe672  ldc.i4.0
0xe673  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.List`1<class TimeZoneSyncTask.OneSettings.DynamicDSTRules>::get_Item(!!T0)
0xe678  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class TimeZoneSyncTask.OneSettings.DynamicDSTRules>::Add(var<u1>)
0xe67d  ldarg.0
0xe67e  ldfld    class [mscorlib]System.Collections.Generic.List`1<class TimeZoneSyncTask.OneSettings.DynamicDSTRules> TimeZoneSyncTask.OneSettings.TimeZoneDSTSettings::allDSTRules
0xe683  ldc.i4.0
0xe684  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.List`1<class TimeZoneSyncTask.OneSettings.DynamicDSTRules>::get_Item(!!T0)
0xe689  stloc.1
0xe68a  ldc.i4.1
0xe68b  stloc.2
0xe68c  br.s     loc_E6C5
0xe68e  ldarg.0
0xe68f  ldfld    class [mscorlib]System.Collections.Generic.List`1<class TimeZoneSyncTask.OneSettings.DynamicDSTRules> TimeZoneSyncTask.OneSettings.TimeZoneDSTSettings::allDSTRules
0xe694  ldloc.2
0xe695  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.List`1<class TimeZoneSyncTask.OneSettings.DynamicDSTRules>::get_Item(!!T0)
0xe69a  ldloc.1
0xe69b  callvirt instance int32 TimeZoneSyncTask.OneSettings.DynamicDSTRules::CompareZoneID(class TimeZoneSyncTask.OneSettings.IDynamicDSTRules other)
0xe6a0  brfalse.s loc_E6C1
0xe6a2  ldloc.0
0xe6a3  ldarg.0
0xe6a4  ldfld    class [mscorlib]System.Collections.Generic.List`1<class TimeZoneSyncTask.OneSettings.DynamicDSTRules> TimeZoneSyncTask.OneSettings.TimeZoneDSTSettings::allDSTRules
0xe6a9  ldloc.2
0xe6aa  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.List`1<class TimeZoneSyncTask.OneSettings.DynamicDSTRules>::get_Item(!!T0)
0xe6af  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class TimeZoneSyncTask.OneSettings.DynamicDSTRules>::Add(var<u1>)
0xe6b4  ldarg.0
0xe6b5  ldfld    class [mscorlib]System.Collections.Generic.List`1<class TimeZoneSyncTask.OneSettings.DynamicDSTRules> TimeZoneSyncTask.OneSettings.TimeZoneDSTSettings::allDSTRules
0xe6ba  ldloc.2
0xe6bb  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.List`1<class TimeZoneSyncTask.OneSettings.DynamicDSTRules>::get_Item(!!T0)
0xe6c0  stloc.1
0xe6c1  ldloc.2
0xe6c2  ldc.i4.1
0xe6c3  add
0xe6c4  stloc.2
0xe6c5  ldloc.2
0xe6c6  ldarg.0
0xe6c7  ldfld    class [mscorlib]System.Collections.Generic.List`1<class TimeZoneSyncTask.OneSettings.DynamicDSTRules> TimeZoneSyncTask.OneSettings.TimeZoneDSTSettings::allDSTRules
0xe6cc  callvirt instance int32 class [mscorlib]System.Collections.Generic.List`1<class TimeZoneSyncTask.OneSettings.DynamicDSTRules>::get_Count()
0xe6d1  blt.s    loc_E68E
0xe6d3  ldarg.0
0xe6d4  ldloc.0
0xe6d5  stfld    class [mscorlib]System.Collections.Generic.List`1<class TimeZoneSyncTask.OneSettings.DynamicDSTRules> TimeZoneSyncTask.OneSettings.TimeZoneDSTSettings::allDSTRules
0xe6da  ret
```
