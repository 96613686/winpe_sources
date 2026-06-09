# TimeZoneSyncTask.OneSettings.OneSettingsDSTJsonParser::StringToByteArray

- ea: `0xe410`
- end: `0xe469`
- name: `TimeZoneSyncTask.OneSettings.OneSettingsDSTJsonParser::StringToByteArray`
- size: `89`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, service_task`

## callers

- `0xe310`

## callees

- `0xe410`
- `0x14260`

## pseudocode

```c

```

## disassembly

```asm
0xe410  newobj   instance void <>c__DisplayClass8_0::.ctor()
0xe415  stloc.0
0xe416  ldloc.0
0xe417  ldarg.1
0xe418  stfld    string <>c__DisplayClass8_0::hex
0xe41d  ldc.i4.0
0xe41e  ldloc.0
0xe41f  ldfld    string <>c__DisplayClass8_0::hex
0xe424  callvirt instance int32 [mscorlib]System.String::get_Length()
0xe429  call     class [mscorlib]System.Collections.Generic.IEnumerable`1<int32> [System.Core]System.Linq.Enumerable::Range(int32, int32)
0xe42e  ldsfld   class [mscorlib]System.Func`2<int32, bool> <>c::<>9__8_0
0xe433  dup
0xe434  brtrue.s loc_E44D
0xe436  pop
0xe437  ldsfld   class <>c <>c::<>9
0xe43c  ldftn    instance bool <>c::<StringToByteArray>b__8_0(int32 x)
0xe442  newobj   instance void class [mscorlib]System.Func`2<int32, bool>::.ctor(object, native int)
0xe447  dup
0xe448  stsfld   class [mscorlib]System.Func`2<int32, bool> <>c::<>9__8_0
0xe44d  call     T0x2B000012
0xe452  ldloc.0
0xe453  ldftn    instance unsigned int8 <>c__DisplayClass8_0::<StringToByteArray>b__1(int32 x)
0xe459  newobj   instance void class [mscorlib]System.Func`2<int32, unsigned int8>::.ctor(object, native int)
0xe45e  call     T0x2B000013
0xe463  call     T0x2B000014
0xe468  ret
```
