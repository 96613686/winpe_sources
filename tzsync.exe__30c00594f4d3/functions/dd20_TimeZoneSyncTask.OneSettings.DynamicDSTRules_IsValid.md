# TimeZoneSyncTask.OneSettings.DynamicDSTRules::IsValid

- ea: `0xdd20`
- end: `0xde07`
- name: `TimeZoneSyncTask.OneSettings.DynamicDSTRules::IsValid`
- size: `231`
- prototype: ``
- caller_count: `2`
- callee_count: `7`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0xde10`
- `0xe310`

## callees

- `0xdc00`
- `0xdc20`
- `0xdc40`
- `0xdc60`
- `0xdc80`
- `0xdd20`
- `0xfe80`

## pseudocode

```c

```

## disassembly

```asm
0xdd20  ldarg.0
0xdd21  call     instance string TimeZoneSyncTask.OneSettings.DynamicDSTRules::get_zoneID()
0xdd26  brfalse.s loc_DD7A
0xdd28  ldarg.0
0xdd29  call     instance string TimeZoneSyncTask.OneSettings.DynamicDSTRules::get_minYear()
0xdd2e  brfalse.s loc_DD7A
0xdd30  ldarg.0
0xdd31  call     instance string TimeZoneSyncTask.OneSettings.DynamicDSTRules::get_maxYear()
0xdd36  brfalse.s loc_DD7A
0xdd38  ldarg.0
0xdd39  call     instance unsigned int32 TimeZoneSyncTask.OneSettings.DynamicDSTRules::get_tzVersion()
0xdd3e  brfalse.s loc_DD7A
0xdd40  ldarg.0
0xdd41  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<string, valuetype TimeZoneSyncTask.Data.RegistryTimeZoneData> TimeZoneSyncTask.OneSettings.DynamicDSTRules::DSTRules
0xdd46  callvirt instance int32 class [mscorlib]System.Collections.Generic.Dictionary`2<string, valuetype TimeZoneSyncTask.Data.RegistryTimeZoneData>::get_Count()
0xdd4b  brfalse.s loc_DD7A
0xdd4d  ldarg.0
0xdd4e  call     instance string TimeZoneSyncTask.OneSettings.DynamicDSTRules::get_minYear()
0xdd53  ldarg.0
0xdd54  call     instance string TimeZoneSyncTask.OneSettings.DynamicDSTRules::get_maxYear()
0xdd59  call     bool [mscorlib]System.String::op_Equality(string, string)
0xdd5e  brtrue.s loc_DD7A
0xdd60  ldarg.0
0xdd61  call     instance string TimeZoneSyncTask.OneSettings.DynamicDSTRules::get_minYear()
0xdd66  callvirt instance int32 [mscorlib]System.String::get_Length()
0xdd6b  brfalse.s loc_DD7A
0xdd6d  ldarg.0
0xdd6e  call     instance string TimeZoneSyncTask.OneSettings.DynamicDSTRules::get_maxYear()
0xdd73  callvirt instance int32 [mscorlib]System.String::get_Length()
0xdd78  brtrue.s loc_DD7C
0xdd7a  ldc.i4.0
0xdd7b  ret
0xdd7c  ldarg.0
0xdd7d  call     instance string TimeZoneSyncTask.OneSettings.DynamicDSTRules::get_minYear()
0xdd82  call     int32 [mscorlib]System.Int32::Parse(string)
0xdd87  stloc.0
0xdd88  ldarg.0
0xdd89  call     instance string TimeZoneSyncTask.OneSettings.DynamicDSTRules::get_maxYear()
0xdd8e  call     int32 [mscorlib]System.Int32::Parse(string)
0xdd93  stloc.1
0xdd94  ldloc.0
0xdd95  ldloc.1
0xdd96  blt.s    loc_DDA0
0xdd98  ldloc.1
0xdd99  brfalse.s loc_DDA0
0xdd9b  ldloc.0
0xdd9c  brfalse.s loc_DDA0
0xdd9e  ldc.i4.0
0xdd9f  ret
0xdda0  ldarg.0
0xdda1  call     instance valuetype TimeZoneSyncTask.Data.RegistryTimeZoneData TimeZoneSyncTask.OneSettings.DynamicDSTRules::get_tzi()
0xdda6  stloc.2
0xdda7  ldloca.s 2
0xdda9  call     instance bool TimeZoneSyncTask.Data.RegistryTimeZoneData::IsValid()
0xddae  brtrue.s loc_DDC4
0xddb0  ldloc.0
0xddb1  ldloc.1
0xddb2  sub
0xddb3  ldc.i4.1
0xddb4  add
0xddb5  ldarg.0
0xddb6  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<string, valuetype TimeZoneSyncTask.Data.RegistryTimeZoneData> TimeZoneSyncTask.OneSettings.DynamicDSTRules::DSTRules
0xddbb  callvirt instance int32 class [mscorlib]System.Collections.Generic.Dictionary`2<string, valuetype TimeZoneSyncTask.Data.RegistryTimeZoneData>::get_Count()
0xddc0  beq.s    loc_DDC4
0xddc2  ldc.i4.0
0xddc3  ret
0xddc4  ldloc.0
0xddc5  stloc.3
0xddc6  br.s     loc_DE01
0xddc8  ldarg.0
0xddc9  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<string, valuetype TimeZoneSyncTask.Data.RegistryTimeZoneData> TimeZoneSyncTask.OneSettings.DynamicDSTRules::DSTRules
0xddce  ldloca.s 3
0xddd0  call     instance string [mscorlib]System.Int32::ToString()
0xddd5  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<string, valuetype TimeZoneSyncTask.Data.RegistryTimeZoneData>::ContainsKey(var<u1>)
0xddda  brtrue.s loc_DDDE
0xdddc  ldc.i4.0
0xdddd  ret
0xddde  ldarg.0
0xdddf  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<string, valuetype TimeZoneSyncTask.Data.RegistryTimeZoneData> TimeZoneSyncTask.OneSettings.DynamicDSTRules::DSTRules
0xdde4  ldloca.s 3
0xdde6  call     instance string [mscorlib]System.Int32::ToString()
0xddeb  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<string, valuetype TimeZoneSyncTask.Data.RegistryTimeZoneData>::get_Item(void)
0xddf0  stloc.s  4
0xddf2  ldloca.s 4
0xddf4  call     instance bool TimeZoneSyncTask.Data.RegistryTimeZoneData::IsValid()
0xddf9  brtrue.s loc_DDFD
0xddfb  ldc.i4.0
0xddfc  ret
0xddfd  ldloc.3
0xddfe  ldc.i4.1
0xddff  add
0xde00  stloc.3
0xde01  ldloc.3
0xde02  ldloc.1
0xde03  ble.s    loc_DDC8
0xde05  ldc.i4.1
0xde06  ret
```
