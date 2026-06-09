# NtDll::RtlQueryAllFeatureConfigurations

- ea: `0x13920`
- end: `0x13a21`
- name: `NtDll::RtlQueryAllFeatureConfigurations`
- size: `257`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config, loader_planting`

## callees

- `0x13920`
- `0x13ca0`
- `0x152c0`
- `0x154d0`

## pseudocode

```c

```

## disassembly

```asm
0x13920  ldarg.2
0x13921  ldnull
0x13922  stind.ref
0x13923  ldsfld   native unsigned int [mscorlib]System.UIntPtr::Zero
0x13928  stloc.0
0x13929  ldsfld   native int [mscorlib]System.IntPtr::Zero
0x1392e  stloc.1
0x1392f  call     class RtlQueryAllFeatureConfigurationsFn NativeMethods::get_RtlQueryAllFeatureConfigurations()
0x13934  ldarg.0
0x13935  ldarg.1
0x13936  ldloc.1
0x13937  ldloca.s 0
0x13939  callvirt instance valuetype NTSTATUS RtlQueryAllFeatureConfigurationsFn::Invoke([in] valuetype RTL_FEATURE_CONFIGURATION_TYPE ConfigurationType, [out] valuetype RTL_FEATURE_CHANGE_STAMP& ChangeStamp, [in] [out] native int Configurations, [in] [out] native unsigned int& ConfigurationCount)
0x1393e  stloc.2
0x1393f  ldloca.s 0
0x13941  call     instance unsigned int64 [mscorlib]System.UIntPtr::ToUInt64()
0x13946  stloc.3
0x13947  ldloc.2
0x13948  brtrue.s loc_13951
0x1394a  ldarg.2
0x1394b  call     T0x2B00004A
0x13950  stind.ref
0x13951  ldc.i4.2
0x13952  stloc.s  4
0x13954  br       loc_13A0A
0x13959  ldloc.s  4
0x1395b  ldc.i4.1
0x1395c  sub
0x1395d  stloc.s  4
0x1395f  call     int32 RTL_FEATURE_CONFIGURATION::get_StructSize()
0x13964  conv.ovf.u4.un
0x13965  ldloc.3
0x13966  mul.ovf.un
0x13967  conv.ovf.i4
0x13968  call     native int [mscorlib]System.Runtime.InteropServices.Marshal::AllocHGlobal(int32)
0x1396d  stloc.1
0x1396e  call     class RtlQueryAllFeatureConfigurationsFn NativeMethods::get_RtlQueryAllFeatureConfigurations()
0x13973  ldarg.0
0x13974  ldarg.1
0x13975  ldloc.1
0x13976  ldloca.s 0
0x13978  callvirt instance valuetype NTSTATUS RtlQueryAllFeatureConfigurationsFn::Invoke([in] valuetype RTL_FEATURE_CONFIGURATION_TYPE ConfigurationType, [out] valuetype RTL_FEATURE_CHANGE_STAMP& ChangeStamp, [in] [out] native int Configurations, [in] [out] native unsigned int& ConfigurationCount)
0x1397d  stloc.2
0x1397e  ldloca.s 0
0x13980  call     instance unsigned int64 [mscorlib]System.UIntPtr::ToUInt64()
0x13985  stloc.3
0x13986  ldloc.2
0x13987  brtrue.s loc_13A01
0x13989  ldloc.1
0x1398a  ldsfld   native int [mscorlib]System.IntPtr::Zero
0x1398f  call     bool [mscorlib]System.IntPtr::op_Inequality(native int, native int)
0x13994  brfalse.s loc_13A01
0x13996  ldloc.3
0x13997  ldc.i4.0
0x13998  conv.i8
0x13999  ble.un.s loc_13A01
0x1399b  ldloc.3
0x1399c  conv.ovf.i8.un
0x1399d  newarr   RTL_FEATURE_CONFIGURATION
0x139a2  stloc.s  5
0x139a4  ldloc.1
0x139a5  stloc.s  6
0x139a7  ldc.i4.0
0x139a8  conv.i8
0x139a9  stloc.s  7
0x139ab  br.s     loc_139F8
0x139ad  nop
0x139ae  ldloc.s  5
0x139b0  ldloc.s  7
0x139b2  conv.ovf.i8.un
0x139b3  ldloc.s  6
0x139b5  ldtoken  RTL_FEATURE_CONFIGURATION
0x139ba  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x139bf  call     object [mscorlib]System.Runtime.InteropServices.Marshal::PtrToStructure(native int, class [mscorlib]System.Type)
0x139c4  unbox.any RTL_FEATURE_CONFIGURATION
0x139c9  stelem   RTL_FEATURE_CONFIGURATION
0x139ce  leave.s  loc_139E3
0x139d0  pop
0x139d1  ldloc.s  5
0x139d3  ldloc.s  7
0x139d5  conv.ovf.i8.un
0x139d6  ldelema  RTL_FEATURE_CONFIGURATION
0x139db  initobj  RTL_FEATURE_CONFIGURATION
0x139e1  leave.s  loc_139E3
0x139e3  ldloc.s  7
0x139e5  ldc.i4.1
0x139e6  conv.i8
0x139e7  add
0x139e8  stloc.s  7
0x139ea  ldloc.s  6
0x139ec  call     int32 RTL_FEATURE_CONFIGURATION::get_StructSize()
0x139f1  call     native int [mscorlib]System.IntPtr::op_Addition(native int, int32)
0x139f6  stloc.s  6
0x139f8  ldloc.s  7
0x139fa  ldloc.3
0x139fb  blt.un.s loc_139AD
0x139fd  ldarg.2
0x139fe  ldloc.s  5
0x13a00  stind.ref
0x13a01  leave.s  loc_13A0A
0x13a03  ldloc.1
0x13a04  call     void [mscorlib]System.Runtime.InteropServices.Marshal::FreeHGlobal(native int)
0x13a09  endfinally
0x13a0a  ldloc.2
0x13a0b  ldc.i4   0x80000005
0x13a10  bne.un.s loc_13A1F
0x13a12  ldloc.3
0x13a13  ldc.i4.0
0x13a14  conv.i8
0x13a15  ble.un.s loc_13A1F
0x13a17  ldloc.s  4
0x13a19  ldc.i4.0
0x13a1a  bgt      loc_13959
0x13a1f  ldloc.2
0x13a20  ret
```
