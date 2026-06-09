# Details::wil_details_StagingConfig_Load

- ea: `0x128f0`
- end: `0x12c70`
- name: `Details::wil_details_StagingConfig_Load`
- size: `896`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0xa10`

## callees

- `0x128f0`
- `0x13a40`
- `0x13dc0`
- `0x13dd0`

## pseudocode

```c

```

## disassembly

```asm
0x128f0  ldarg.1
0x128f1  ldc.i4.2
0x128f2  bne.un.s loc_128FF
0x128f4  ldstr    aStore// "store"
0x128f9  newobj   instance void [mscorlib]System.ArgumentOutOfRangeException::.ctor(string)
0x128fe  throw
0x128ff  ldarg.2
0x12900  brtrue.s loc_12912
0x12902  ldsfld   string [mscorlib]System.String::Empty
0x12907  ldstr    aBuffersize// "bufferSize"
0x1290c  newobj   instance void [mscorlib]System.ArgumentException::.ctor(string, string)
0x12911  throw
0x12912  ldarg.0
0x12913  ldloca.s 6
0x12915  initobj  wil_details_StagingConfig
0x1291b  ldloca.s 6
0x1291d  ldarg.1
0x1291e  stfld    valuetype wil_FeatureStore wil_details_StagingConfig::Store
0x12923  ldloca.s 6
0x12925  ldarg.s  4
0x12927  stfld    bool wil_details_StagingConfig::ForUpdate
0x1292c  ldloc.s  6
0x1292e  stobj    wil_details_StagingConfig
0x12933  ldarg.3
0x12934  ldsfld   native int [mscorlib]System.IntPtr::Zero
0x12939  call     bool [mscorlib]System.IntPtr::op_Inequality(native int, native int)
0x1293e  brtrue.s loc_12943
0x12940  ldc.i4.0
0x12941  br.s     loc_12944
0x12943  ldarg.2
0x12944  stloc.0
0x12945  ldsfld   native int [mscorlib]System.IntPtr::Zero
0x1294a  stloc.1
0x1294b  ldsfld   native int [mscorlib]System.IntPtr::Zero
0x12950  stloc.2
0x12951  ldarg.1
0x12952  brfalse.s loc_1295B
0x12954  ldsfld   valuetype WIL_WNF_STATE_NAME WIL_WNF_STATE_NAME::WIL_WNF_WIL_USER_FEATURE_STORE
0x12959  br.s     loc_12960
0x1295b  ldsfld   valuetype WIL_WNF_STATE_NAME WIL_WNF_STATE_NAME::WIL_WNF_WIL_MACHINE_FEATURE_STORE
0x12960  stloc.3
0x12961  ldarg.3
0x12962  ldsfld   native int [mscorlib]System.IntPtr::Zero
0x12967  call     bool [mscorlib]System.IntPtr::op_Inequality(native int, native int)
0x1296c  brtrue.s loc_12971
0x1296e  ldc.i4.0
0x1296f  br.s     loc_12972
0x12971  ldarg.2
0x12972  stloc.s  4
0x12974  ldloca.s 3
0x12976  ldsfld   native int [mscorlib]System.IntPtr::Zero
0x1297b  ldsfld   native int [mscorlib]System.IntPtr::Zero
0x12980  ldarg.0
0x12981  ldflda   int32 wil_details_StagingConfig::ReadChangeStamp
0x12986  ldarg.3
0x12987  ldarga.s 2
0x12989  call     valuetype NTSTATUS NtDll::NtQueryWnfStateData(valuetype WIL_WNF_STATE_NAME& StateName, native int TypeId, native int ExplicitScope, int32& ChangeStamp, native int Buffer, int32& BufferSize)
0x1298e  stloc.s  5
0x12990  ldloc.s  5
0x12992  brtrue   loc_12A24
0x12997  ldarg.3
0x12998  ldsfld   native int [mscorlib]System.IntPtr::Zero
0x1299d  call     bool [mscorlib]System.IntPtr::op_Equality(native int, native int)
0x129a2  brfalse.s loc_129AD
0x129a4  ldc.i4   0xC0000023
0x129a9  stloc.s  5
0x129ab  br.s     loc_12A24
0x129ad  ldarg.3
0x129ae  stloc.2
0x129af  br.s     loc_12A24
0x129b1  ldloc.0
0x129b2  ldarg.2
0x129b3  blt.s    loc_129B8
0x129b5  ldloc.0
0x129b6  br.s     loc_129B9
0x129b8  ldarg.2
0x129b9  stloc.0
0x129ba  ldloc.0
0x129bb  ldloc.s  4
0x129bd  blt.s    loc_129C2
0x129bf  ldloc.0
0x129c0  br.s     loc_129C4
0x129c2  ldloc.s  4
0x129c4  stloc.0
0x129c5  ldloc.0
0x129c6  call     T0x2B000040
0x129cb  blt.s    loc_129D0
0x129cd  ldloc.0
0x129ce  br.s     loc_129D5
0x129d0  call     T0x2B000040
0x129d5  stloc.0
0x129d6  ldloc.1
0x129d7  ldsfld   native int [mscorlib]System.IntPtr::Zero
0x129dc  call     bool [mscorlib]System.IntPtr::op_Inequality(native int, native int)
0x129e1  brfalse.s loc_129EF
0x129e3  ldloc.1
0x129e4  call     void [mscorlib]System.Runtime.InteropServices.Marshal::FreeHGlobal(native int)
0x129e9  ldsfld   native int [mscorlib]System.IntPtr::Zero
0x129ee  stloc.1
0x129ef  ldloc.1
0x129f0  ldsfld   native int [mscorlib]System.IntPtr::Zero
0x129f5  call     bool [mscorlib]System.IntPtr::op_Equality(native int, native int)
0x129fa  brfalse.s loc_12A03
0x129fc  ldloc.0
0x129fd  call     native int [mscorlib]System.Runtime.InteropServices.Marshal::AllocHGlobal(int32)
0x12a02  stloc.1
0x12a03  ldloc.0
0x12a04  stloc.s  4
0x12a06  ldloca.s 3
0x12a08  ldsfld   native int [mscorlib]System.IntPtr::Zero
0x12a0d  ldsfld   native int [mscorlib]System.IntPtr::Zero
0x12a12  ldarg.0
0x12a13  ldflda   int32 wil_details_StagingConfig::ReadChangeStamp
0x12a18  ldloc.1
0x12a19  ldloca.s 4
0x12a1b  call     valuetype NTSTATUS NtDll::NtQueryWnfStateData(valuetype WIL_WNF_STATE_NAME& StateName, native int TypeId, native int ExplicitScope, int32& ChangeStamp, native int Buffer, int32& BufferSize)
0x12a20  stloc.s  5
0x12a22  ldloc.1
0x12a23  stloc.2
0x12a24  ldloc.s  5
0x12a26  ldc.i4   0xC0000023
0x12a2b  beq.s    loc_129B1
0x12a2d  ldloc.s  5
0x12a2f  brtrue   loc_12C5A
0x12a34  ldloc.2
0x12a35  ldsfld   native int [mscorlib]System.IntPtr::Zero
0x12a3a  call     bool [mscorlib]System.IntPtr::op_Inequality(native int, native int)
0x12a3f  brfalse  loc_12C5A
0x12a44  ldloc.2
0x12a45  call     T0x2B000041
0x12a4a  stloc.s  7
0x12a4c  ldloc.s  4
0x12a4e  ldc.i4.4
0x12a4f  ble.s    loc_12A5E
0x12a51  ldarg.0
0x12a52  ldloc.s  7
0x12a54  ldfld    unsigned int8 wil_details_StagingConfigHeader::Version
0x12a59  stfld    unsigned int8 wil_details_StagingConfig::ReadVersion
0x12a5e  ldloc.s  4
0x12a60  call     T0x2B000040
0x12a65  blt.s    loc_12AA7
0x12a67  ldarg.0
0x12a68  ldfld    unsigned int8 wil_details_StagingConfig::ReadVersion
0x12a6d  ldc.i4.2
0x12a6e  bne.un.s loc_12AA7
0x12a70  ldloc.s  7
0x12a72  ldfld    unsigned int16 wil_details_StagingConfigHeader::HeaderSizeBytes
0x12a77  call     T0x2B000040
0x12a7c  blt.s    loc_12AA7
0x12a7e  ldloc.s  4
0x12a80  ldloc.s  7
0x12a82  ldfld    unsigned int16 wil_details_StagingConfigHeader::HeaderSizeBytes
0x12a87  call     T0x2B000042
0x12a8c  ldloc.s  7
0x12a8e  ldfld    unsigned int16 wil_details_StagingConfigHeader::FeatureCount
0x12a93  mul.ovf
0x12a94  add.ovf
0x12a95  call     T0x2B000043
0x12a9a  ldloc.s  7
0x12a9c  ldfld    unsigned int16 wil_details_StagingConfigHeader::FeatureUsageTriggerCount
0x12aa1  mul.ovf
0x12aa2  add.ovf
0x12aa3  clt
0x12aa5  br.s     loc_12AA8
0x12aa7  ldc.i4.1
0x12aa8  stloc.s  8
0x12aaa  ldloc.s  8
0x12aac  brfalse  loc_12B36
0x12ab1  call     T0x2B000040
0x12ab6  stloc.s  4
0x12ab8  ldloca.s 7
0x12aba  initobj  wil_details_StagingConfigHeader
0x12ac0  ldloca.s 7
0x12ac2  call     T0x2B000040
0x12ac7  conv.u2
0x12ac8  stfld    unsigned int16 wil_details_StagingConfigHeader::HeaderSizeBytes
0x12acd  ldloca.s 7
0x12acf  ldc.i4.2
0x12ad0  stfld    unsigned int8 wil_details_StagingConfigHeader::Version
0x12ad5  ldloca.s 7
0x12ad7  ldc.i4.2
0x12ad8  stfld    unsigned int8 wil_details_StagingConfigHeader::VersionMinor
0x12add  ldloc.s  7
0x12adf  ldloc.2
0x12ae0  ldc.i4.0
0x12ae1  call     T0x2B000044
0x12ae6  ldarg.0
0x12ae7  ldloc.2
0x12ae8  stfld    native int wil_details_StagingConfig::Header
0x12aed  ldarg.0
0x12aee  ldarg.0
0x12aef  ldflda   native int wil_details_StagingConfig::Header
0x12af4  call     instance int64 [mscorlib]System.IntPtr::ToInt64()
0x12af9  ldloc.s  7
0x12afb  ldfld    unsigned int16 wil_details_StagingConfigHeader::HeaderSizeBytes
0x12b00  conv.u8
0x12b01  add.ovf
0x12b02  newobj   instance void [mscorlib]System.IntPtr::.ctor(int64)
0x12b07  stfld    native int wil_details_StagingConfig::Features
0x12b0c  ldarg.0
0x12b0d  ldarg.0
0x12b0e  ldflda   native int wil_details_StagingConfig::Features
0x12b13  call     instance int64 [mscorlib]System.IntPtr::ToInt64()
0x12b18  call     T0x2B000042
0x12b1d  ldloc.s  7
0x12b1f  ldfld    unsigned int16 wil_details_StagingConfigHeader::FeatureCount
0x12b24  mul.ovf
0x12b25  conv.i8
0x12b26  add.ovf
0x12b27  newobj   instance void [mscorlib]System.IntPtr::.ctor(int64)
0x12b2c  stfld    native int wil_details_StagingConfig::Triggers
0x12b31  br       loc_12C07
0x12b36  ldc.i4.0
0x12b37  call     valuetype WIL_WNF_CHANGE_STAMP WIL_WNF_CHANGE_STAMP::op_Implicit(int32 changeStamp)
0x12b3c  stloc.s  9
0x12b3e  ldloc.s  7
0x12b40  ldfld    unsigned int16 wil_details_StagingConfigHeader::FeatureCount
0x12b45  ldc.i4.0
0x12b46  ble.s    loc_12B7C
0x12b48  ldc.i4.0
0x12b49  stloc.s  0xA
0x12b4b  ldarg.1
0x12b4c  brfalse.s loc_12B55
0x12b4e  ldsfld   valuetype WIL_WNF_STATE_NAME WIL_WNF_STATE_NAME::WIL_WNF_WIL_USER_FEATURE_STORE_MODIFIED
0x12b53  br.s     loc_12B5A
0x12b55  ldsfld   valuetype WIL_WNF_STATE_NAME WIL_WNF_STATE_NAME::WIL_WNF_WIL_MACHINE_FEATURE_STORE_MODIFIED
0x12b5a  stloc.s  0xB
0x12b5c  ldloca.s 0xB
0x12b5e  ldsfld   native int [mscorlib]System.IntPtr::Zero
0x12b63  ldsfld   native int [mscorlib]System.IntPtr::Zero
0x12b68  ldloca.s 9
0x12b6a  ldflda   int32 WIL_WNF_CHANGE_STAMP::ChangeStamp
0x12b6f  ldsfld   native int [mscorlib]System.IntPtr::Zero
0x12b74  ldloca.s 0xA
0x12b76  call     valuetype NTSTATUS NtDll::NtQueryWnfStateData(valuetype WIL_WNF_STATE_NAME& StateName, native int TypeId, native int ExplicitScope, int32& ChangeStamp, native int Buffer, int32& BufferSize)
0x12b7b  pop
0x12b7c  ldarg.0
0x12b7d  ldloc.2
0x12b7e  stfld    native int wil_details_StagingConfig::Header
0x12b83  ldarg.0
0x12b84  ldarg.0
0x12b85  ldfld    native int wil_details_StagingConfig::Header
0x12b8a  call     T0x2B000040
0x12b8f  call     native int [mscorlib]System.IntPtr::op_Addition(native int, int32)
0x12b94  stfld    native int wil_details_StagingConfig::Features
0x12b99  ldarg.0
0x12b9a  ldarg.0
0x12b9b  ldfld    native int wil_details_StagingConfig::Features
0x12ba0  ldloc.s  7
0x12ba2  ldfld    unsigned int16 wil_details_StagingConfigHeader::FeatureCount
0x12ba7  call     T0x2B000042
0x12bac  mul
0x12bad  call     native int [mscorlib]System.IntPtr::op_Addition(native int, int32)
0x12bb2  stfld    native int wil_details_StagingConfig::Triggers
0x12bb7  ldarg.0
0x12bb8  ldloc.s  9
0x12bba  call     int32 WIL_WNF_CHANGE_STAMP::op_Implicit(valuetype WIL_WNF_CHANGE_STAMP changeStamp)
0x12bbf  ldc.i4.0
0x12bc0  cgt.un
0x12bc2  stfld    bool wil_details_StagingConfig::ChangedInSession
0x12bc7  ldloc.s  7
0x12bc9  ldfld    unsigned int8 wil_details_StagingConfigHeader::Version
0x12bce  ldc.i4.2
0x12bcf  bne.un.s loc_12C07
0x12bd1  ldloc.s  7
0x12bd3  ldfld    unsigned int8 wil_details_StagingConfigHeader::VersionMinor
0x12bd8  ldc.i4.2
0x12bd9  bne.un.s loc_12C07
0x12bdb  ldloc.s  7
0x12bdd  ldfld    unsigned int16 wil_details_StagingConfigHeader::HeaderSizeBytes
0x12be2  call     T0x2B000042
0x12be7  ldloc.s  7
0x12be9  ldfld    unsigned int16 wil_details_StagingConfigHeader::FeatureCount
0x12bee  mul.ovf
0x12bef  add.ovf
0x12bf0  call     T0x2B000043
0x12bf5  ldloc.s  7
0x12bf7  ldfld    unsigned int16 wil_details_StagingConfigHeader::FeatureUsageTriggerCount
0x12bfc  mul.ovf
0x12bfd  add.ovf
0x12bfe  stloc.s  4
0x12c00  ldarg.0
0x12c01  ldc.i4.1
0x12c02  stfld    bool wil_details_StagingConfig::Modified
0x12c07  ldarg.0
0x12c08  ldloc.2
0x12c09  stfld    native int wil_details_StagingConfig::Buffer
0x12c0e  ldarg.0
0x12c0f  ldloc.s  4
0x12c11  newobj   instance void [mscorlib]System.IntPtr::.ctor(int32)
0x12c16  stfld    native int wil_details_StagingConfig::BufferSize
0x12c1b  ldarg.0
0x12c1c  ldloc.1
0x12c1d  ldsfld   native int [mscorlib]System.IntPtr::Zero
0x12c22  call     bool [mscorlib]System.IntPtr::op_Inequality(native int, native int)
0x12c27  brtrue.s loc_12C31
0x12c29  ldarg.2
0x12c2a  newobj   instance void [mscorlib]System.IntPtr::.ctor(int32)
0x12c2f  br.s     loc_12C37
0x12c31  ldloc.0
  ... truncated ...
```
