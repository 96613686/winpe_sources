# TimeZoneSyncTask.OneSettings.TimeZoneDSTSettings::SyncDSTDataWithRegistry

- ea: `0xe6e0`
- end: `0xe716`
- name: `TimeZoneSyncTask.OneSettings.TimeZoneDSTSettings::SyncDSTDataWithRegistry`
- size: `54`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, service_task`

## callers

- `0xcee0`

## callees

- `0xde10`
- `0xe6e0`

## pseudocode

```c

```

## disassembly

```asm
0xe6e0  ldarg.0
0xe6e1  ldfld    class [mscorlib]System.Collections.Generic.List`1<class TimeZoneSyncTask.OneSettings.DynamicDSTRules> TimeZoneSyncTask.OneSettings.TimeZoneDSTSettings::allDSTRules
0xe6e6  callvirt instance valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<var<u1>> class [mscorlib]System.Collections.Generic.List`1<class TimeZoneSyncTask.OneSettings.DynamicDSTRules>::GetEnumerator()
0xe6eb  stloc.0
0xe6ec  br.s     loc_E6FC
0xe6ee  ldloca.s 0
0xe6f0  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class TimeZoneSyncTask.OneSettings.DynamicDSTRules>::get_Current()
0xe6f5  ldarg.1
0xe6f6  callvirt instance bool TimeZoneSyncTask.OneSettings.DynamicDSTRules::ApplyDSTRuleToRegistry(class [mscorlib]Microsoft.Win32.RegistryKey rkTimeZoneRoot)
0xe6fb  pop
0xe6fc  ldloca.s 0
0xe6fe  call     instance bool valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class TimeZoneSyncTask.OneSettings.DynamicDSTRules>::MoveNext()
0xe703  brtrue.s loc_E6EE
0xe705  leave.s  loc_E715
0xe707  ldloca.s 0
0xe709  constrained. valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class TimeZoneSyncTask.OneSettings.DynamicDSTRules>
0xe70f  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xe714  endfinally
0xe715  ret
```
