# IdentityStorage::WriteProperties(ushort const *,ATL::CAtlArray<IdentityProperty,ATL::CElementTraits<IdentityProperty>> const &)

- ea: `0x18003f5c0`
- end: `0x18003f7fa`
- name: `?WriteProperties@IdentityStorage@@AEAAJPEBGAEBV?$CAtlArray@UIdentityProperty@@V?$CElementTraits@UIdentityProperty@@@ATL@@@ATL@@@Z`
- size: `570`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18003ea04`

## callees

- `0x1800035cc`
- `0x1800061a8`
- `0x1800090c0`
- `0x180009630`
- `0x180010b80`
- `0x180012e74`
- `0x180013434`
- `0x180016c0c`
- `0x18003c0dc`
- `0x18003c3b0`
- `0x18003e99c`
- `0x18003f5c0`

## string_xrefs

- `0x18003f5ee`: `IdentityStorage::WriteProperties`
- `0x18003f6fb`: `IdentityStorage::WriteProperties`
- `0x18003f7a9`: `IdentityStorage::WriteProperties`
- `0x18003f693`: `tempPropertyList.SetCount(identityPropertyArray.GetCount())`
- `0x18003f794`: `hr = registryHelper.WriteBufferToRegistry(nullptr, GetEnvironmentSpecificRegistryKey(ModernDataPropertyRootKey), pDefaultId, REG_BINARY, apIdentityPropertyBuffer, encodedSize)`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall IdentityStorage::WriteProperties(__int64 *a1, const unsigned __int16 *a2, __int64 a3)
{
  __int64 v6; // rdx
  int v7; // r8d
  unsigned int i; // r14d
  __int64 v9; // rbx
  __int64 v10; // rbx
  int v11; // eax
  unsigned int v12; // ebx
  unsigned __int8 *v13; // rdi
  const unsigned __int16 **EnvironmentSpecificRegistryKey; // rax
  int v15; // ebx
  unsigned int v16; // ebx
  char *v18; // [rsp+20h] [rbp-59h]
  unsigned __int8 *v19; // [rsp+40h] [rbp-39h] BYREF
  __int64 v20; // [rsp+48h] [rbp-31h] BYREF
  __int64 v21; // [rsp+50h] [rbp-29h] BYREF
  __int128 v22; // [rsp+58h] [rbp-21h] BYREF
  _QWORD v23[3]; // [rsp+68h] [rbp-11h] BYREF
  int v24; // [rsp+80h] [rbp+7h]
  _QWORD v25[5]; // [rsp+88h] [rbp+Fh] BYREF
  int v26; // [rsp+F0h] [rbp+77h] BYREF
  unsigned int v27; // [rsp+F8h] [rbp+7Fh] BYREF

  v26 = 0;
  v25[0] = "IdentityStorage::WriteProperties";
  v25[1] = &v26;
  v25[2] = 0;
  v25[3] = 0;
  MsaTracingInternal::TraceFunctionEnter(
    (MsaTracingInternal *)"onecoreuap\\ds\\ext\\live\\identity\\lib\\immersiveidentitystorage\\identitystorage.cpp",
    "IdentityStorage::WriteProperties",
    (const char *)0xE6,
    0,
    (const unsigned __int16 *)v18);
  v6 = *(_QWORD *)(a3 + 8);
  if ( v6 )
  {
    v20 = *a1;
    v21 = v20;
    memset(v23, 0, sizeof(v23));
    v24 = 0;
    v22 = 0;
    v19 = 0;
    v27 = 0;
    LODWORD(v22) = v6;
    if ( (unsigned __int8)ATL::CAtlArray<_ModernIdentityProperty,ATL::CElementTraits<_ModernIdentityProperty>>::SetCount(v23) )
    {
      for ( i = 0; i < (unsigned int)v22; ++i )
      {
        v9 = *(_QWORD *)ATL::CAtlArray<_ModernIdentityProperty,ATL::CElementTraits<_ModernIdentityProperty>>::operator[](
                          a3,
                          i);
        *(_QWORD *)ATL::CAtlArray<_ModernIdentityProperty,ATL::CElementTraits<_ModernIdentityProperty>>::operator[](
                     v23,
                     i) = v9;
        v10 = *(_QWORD *)(ATL::CAtlArray<_ModernIdentityProperty,ATL::CElementTraits<_ModernIdentityProperty>>::operator[](
                            a3,
                            i)
                        + 8);
        *(_QWORD *)(ATL::CAtlArray<_ModernIdentityProperty,ATL::CElementTraits<_ModernIdentityProperty>>::operator[](
                      v23,
                      i)
                  + 8) = v10;
      }
      *((_QWORD *)&v22 + 1) = v23[0];
      v11 = SerializeObjectWithVersion<ModernIdentityPropertyBagSerializer,_ModernIdentityPropertyBag>(
              (unsigned int)&v20,
              (unsigned int)&v22,
              v7,
              (unsigned int)&v19,
              (__int64)&v27);
      v26 = v11;
      if ( v11 >= 0 )
      {
        v12 = v27;
        v13 = v19;
        EnvironmentSpecificRegistryKey = (const unsigned __int16 **)IdentityStorage::GetEnvironmentSpecificRegistryKey(
                                                                      a1,
                                                                      &v27,
                                                                      (__int64)L"Software\\Microsoft\\IdentityCRL\\Immersi"
                                                                                "ve\\%s\\Property");
        v15 = RegistryHelper::WriteBufferToRegistry(
                (RegistryHelper *)&v21,
                0,
                *EnvironmentSpecificRegistryKey,
                a2,
                3u,
                v13,
                v12);
        v26 = v15;
        ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v27);
        if ( v15 < 0 )
          Telemetry::IfFailExit(
            "onecoreuap\\ds\\ext\\live\\identity\\lib\\immersiveidentitystorage\\identitystorage.cpp",
            "IdentityStorage::WriteProperties",
            0x108u,
            v15,
            "hr = registryHelper.WriteBufferToRegistry(nullptr, GetEnvironmentSpecificRegistryKey(ModernDataPropertyRootK"
            "ey), pDefaultId, REG_BINARY, apIdentityPropertyBuffer, encodedSize)");
      }
      else
      {
        Telemetry::IfFailExit(
          "onecoreuap\\ds\\ext\\live\\identity\\lib\\immersiveidentitystorage\\identitystorage.cpp",
          "IdentityStorage::WriteProperties",
          0x101u,
          v11,
          "hr = SerializeObjectWithVersion( propertybagSerializer, identityPropertyBag, CurrentSerializationVersion, &apI"
          "dentityPropertyBuffer, &encodedSize)");
      }
    }
    else
    {
      v26 = -2147024882;
      Telemetry::IfFailExit(
        "onecoreuap\\ds\\ext\\live\\identity\\lib\\immersiveidentitystorage\\identitystorage.cpp",
        "IdentityStorage::WriteProperties",
        0xF3u,
        -2147024882,
        "tempPropertyList.SetCount(identityPropertyArray.GetCount())");
    }
    CMIDLPtr<unsigned short *>::Clear(&v19);
    ATL::CAtlArray<_ModernIdentityProperty,ATL::CElementTraits<_ModernIdentityProperty>>::~CAtlArray<_ModernIdentityProperty,ATL::CElementTraits<_ModernIdentityProperty>>(v23);
  }
  v16 = v26;
  CTraceFuncW<long>::~CTraceFuncW<long>(v25);
  return v16;
}

```

## disassembly

```asm
0x18003f5c0  mov     [rsp-8+arg_0], rbx
0x18003f5c5  mov     [rsp-8+arg_8], rsi
0x18003f5ca  push    rbp
0x18003f5cb  push    rdi
0x18003f5cc  push    r12
0x18003f5ce  push    r14
0x18003f5d0  push    r15
0x18003f5d2  lea     rbp, [rsp-37h]
0x18003f5d7  sub     rsp, 0B0h
0x18003f5de  mov     rsi, r8
0x18003f5e1  mov     r12, rdx
0x18003f5e4  mov     r15, rcx
0x18003f5e7  mov     [rbp+57h+arg_10], 0
0x18003f5ee  lea     rbx, aIdentitystorag_3; "IdentityStorage::WriteProperties"
0x18003f5f5  mov     [rbp+57h+var_48], rbx
0x18003f5f9  lea     rax, [rbp+57h+arg_10]
0x18003f5fd  mov     [rbp+57h+var_40], rax
0x18003f601  mov     [rbp+57h+var_38], 0
0x18003f609  mov     [rbp+57h+var_30], 0
0x18003f611  xor     r9d, r9d; unsigned int
0x18003f614  mov     r8d, 0E6h; char *
0x18003f61a  mov     rdx, rbx; char *
0x18003f61d  lea     rcx, aOnecoreuapDsEx_0; "onecoreuap\\ds\\ext\\live\\identity\\li"...
0x18003f624  call    ?TraceFunctionEnter@MsaTracingInternal@@YAKPEBD0KPEBG@Z; MsaTracingInternal::TraceFunctionEnter(char const *,char const *,ulong,ushort const *)
0x18003f629  nop
0x18003f62a  mov     rdx, [rsi+8]
0x18003f62e  test    rdx, rdx
0x18003f631  jz      loc_18003F7D0
0x18003f637  mov     rax, [r15]
0x18003f63a  mov     [rbp+57h+var_88], rax
0x18003f63e  mov     [rbp+57h+var_80], rax
0x18003f642  mov     [rbp+57h+var_68], 0
0x18003f64a  mov     [rbp+57h+var_60], 0
0x18003f652  mov     [rbp+57h+var_58], 0
0x18003f65a  mov     [rbp+57h+var_50], 0
0x18003f661  xorps   xmm0, xmm0
0x18003f664  movups  [rbp+57h+var_78], xmm0
0x18003f668  mov     [rbp+57h+var_90], 0
0x18003f670  mov     [rbp+57h+arg_18], 0
0x18003f677  mov     eax, edx
0x18003f679  mov     dword ptr [rbp+57h+var_78], edx
0x18003f67c  lea     rcx, [rbp+57h+var_68]
0x18003f680  call    ?SetCount@?$CAtlArray@U_ModernIdentityProperty@@V?$CElementTraits@U_ModernIdentityProperty@@@ATL@@@ATL@@QEAA_N_KH@Z; ATL::CAtlArray<_ModernIdentityProperty,ATL::CElementTraits<_ModernIdentityProperty>>::SetCount(unsigned __int64,int)
0x18003f685  test    al, al
0x18003f687  jnz     short loc_18003F6AD
0x18003f689  mov     r9d, 8007000Eh
0x18003f68f  mov     [rbp+57h+arg_10], r9d
0x18003f693  lea     rax, aTemppropertyli; "tempPropertyList.SetCount(identityPrope"...
0x18003f69a  mov     [rsp+0D0h+var_B0], rax
0x18003f69f  mov     r8d, 0F3h
0x18003f6a5  mov     rdx, rbx
0x18003f6a8  jmp     loc_18003F7B0
0x18003f6ad  xor     r14d, r14d
0x18003f6b0  cmp     dword ptr [rbp+57h+var_78], r14d
0x18003f6b4  jbe     short loc_18003F702
0x18003f6b6  mov     edx, r14d
0x18003f6b9  mov     rcx, rsi
0x18003f6bc  call    ??A?$CAtlArray@U_ModernIdentityProperty@@V?$CElementTraits@U_ModernIdentityProperty@@@ATL@@@ATL@@QEAAAEAU_ModernIdentityProperty@@_K@Z; ATL::CAtlArray<_ModernIdentityProperty,ATL::CElementTraits<_ModernIdentityProperty>>::operator[](unsigned __int64)
0x18003f6c1  mov     rbx, [rax]
0x18003f6c4  mov     edx, r14d
0x18003f6c7  lea     rcx, [rbp+57h+var_68]
0x18003f6cb  call    ??A?$CAtlArray@U_ModernIdentityProperty@@V?$CElementTraits@U_ModernIdentityProperty@@@ATL@@@ATL@@QEAAAEAU_ModernIdentityProperty@@_K@Z; ATL::CAtlArray<_ModernIdentityProperty,ATL::CElementTraits<_ModernIdentityProperty>>::operator[](unsigned __int64)
0x18003f6d0  mov     [rax], rbx
0x18003f6d3  mov     edx, r14d
0x18003f6d6  mov     rcx, rsi
0x18003f6d9  call    ??A?$CAtlArray@U_ModernIdentityProperty@@V?$CElementTraits@U_ModernIdentityProperty@@@ATL@@@ATL@@QEAAAEAU_ModernIdentityProperty@@_K@Z; ATL::CAtlArray<_ModernIdentityProperty,ATL::CElementTraits<_ModernIdentityProperty>>::operator[](unsigned __int64)
0x18003f6de  mov     rbx, [rax+8]
0x18003f6e2  mov     edx, r14d
0x18003f6e5  lea     rcx, [rbp+57h+var_68]
0x18003f6e9  call    ??A?$CAtlArray@U_ModernIdentityProperty@@V?$CElementTraits@U_ModernIdentityProperty@@@ATL@@@ATL@@QEAAAEAU_ModernIdentityProperty@@_K@Z; ATL::CAtlArray<_ModernIdentityProperty,ATL::CElementTraits<_ModernIdentityProperty>>::operator[](unsigned __int64)
0x18003f6ee  mov     [rax+8], rbx
0x18003f6f2  inc     r14d
0x18003f6f5  cmp     r14d, dword ptr [rbp+57h+var_78]
0x18003f6f9  jb      short loc_18003F6B6
0x18003f6fb  lea     rbx, aIdentitystorag_3; "IdentityStorage::WriteProperties"
0x18003f702  mov     rax, [rbp+57h+var_68]
0x18003f706  mov     qword ptr [rbp+57h+var_78+8], rax
0x18003f70a  lea     rax, [rbp+57h+arg_18]
0x18003f70e  mov     [rsp+0D0h+var_B0], rax
0x18003f713  lea     r9, [rbp+57h+var_90]
0x18003f717  lea     rdx, [rbp+57h+var_78]
0x18003f71b  lea     rcx, [rbp+57h+var_88]
0x18003f71f  call    ??$SerializeObjectWithVersion@VModernIdentityPropertyBagSerializer@@U_ModernIdentityPropertyBag@@@@YAJAEAVModernIdentityPropertyBagSerializer@@AEAU_ModernIdentityPropertyBag@@KPEAPEAEPEAK@Z; SerializeObjectWithVersion<ModernIdentityPropertyBagSerializer,_ModernIdentityPropertyBag>(ModernIdentityPropertyBagSerializer &,_ModernIdentityPropertyBag &,ulong,uchar * *,ulong *)
0x18003f724  mov     [rbp+57h+arg_10], eax
0x18003f727  test    eax, eax
0x18003f729  jns     short loc_18003F745
0x18003f72b  lea     rcx, aHrSerializeobj_1; "hr = SerializeObjectWithVersion( proper"...
0x18003f732  mov     [rsp+0D0h+var_B0], rcx
0x18003f737  mov     r9d, eax
0x18003f73a  mov     r8d, 101h
0x18003f740  jmp     loc_18003F6A5
0x18003f745  mov     ebx, [rbp+57h+arg_18]
0x18003f748  mov     rdi, [rbp+57h+var_90]
0x18003f74c  lea     r8, aSoftwareMicros_4; "Software\\Microsoft\\IdentityCRL\\Immer"...
0x18003f753  lea     rdx, [rbp+57h+arg_18]
0x18003f757  mov     rcx, r15
0x18003f75a  call    ?GetEnvironmentSpecificRegistryKey@IdentityStorage@@AEAA?AV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@PEBG@Z; IdentityStorage::GetEnvironmentSpecificRegistryKey(ushort const *)
0x18003f75f  nop
0x18003f760  mov     [rsp+0D0h+var_A0], ebx; unsigned int
0x18003f764  mov     [rsp+0D0h+var_A8], rdi; unsigned __int8 *
0x18003f769  mov     dword ptr [rsp+0D0h+var_B0], 3; unsigned int
0x18003f771  mov     r9, r12; unsigned __int16 *
0x18003f774  mov     r8, [rax]; unsigned __int16 *
0x18003f777  xor     edx, edx; HKEY
0x18003f779  lea     rcx, [rbp+57h+var_80]; this
0x18003f77d  call    ?WriteBufferToRegistry@RegistryHelper@@QEAAJPEAUHKEY__@@PEBG1KPEAEK@Z; RegistryHelper::WriteBufferToRegistry(HKEY__ *,ushort const *,ushort const *,ulong,uchar *,ulong)
0x18003f782  mov     ebx, eax
0x18003f784  mov     [rbp+57h+arg_10], eax
0x18003f787  lea     rcx, [rbp+57h+arg_18]; void *
0x18003f78b  call    ??1?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(void)
0x18003f790  test    ebx, ebx
0x18003f792  jns     short loc_18003F7BD
0x18003f794  lea     rax, aHrRegistryhelp_8; "hr = registryHelper.WriteBufferToRegist"...
0x18003f79b  mov     [rsp+0D0h+var_B0], rax; char *
0x18003f7a0  mov     r9d, ebx; int
0x18003f7a3  mov     r8d, 108h; unsigned int
0x18003f7a9  lea     rdx, aIdentitystorag_3; "IdentityStorage::WriteProperties"
0x18003f7b0  lea     rcx, aOnecoreuapDsEx_0; "onecoreuap\\ds\\ext\\live\\identity\\li"...
0x18003f7b7  call    ?IfFailExit@Telemetry@@SAXPEBD0KJ0@Z; Telemetry::IfFailExit(char const *,char const *,ulong,long,char const *)
0x18003f7bc  nop
0x18003f7bd  lea     rcx, [rbp+57h+var_90]
0x18003f7c1  call    ?Clear@?$CMIDLPtr@PEAG@@QEAAXXZ; CMIDLPtr<ushort *>::Clear(void)
0x18003f7c6  nop
0x18003f7c7  lea     rcx, [rbp+57h+var_68]
0x18003f7cb  call    ??1?$CAtlArray@U_ModernIdentityProperty@@V?$CElementTraits@U_ModernIdentityProperty@@@ATL@@@ATL@@QEAA@XZ; ATL::CAtlArray<_ModernIdentityProperty,ATL::CElementTraits<_ModernIdentityProperty>>::~CAtlArray<_ModernIdentityProperty,ATL::CElementTraits<_ModernIdentityProperty>>(void)
0x18003f7d0  mov     ebx, [rbp+57h+arg_10]
0x18003f7d3  lea     rcx, [rbp+57h+var_48]
0x18003f7d7  call    ??1?$CTraceFuncW@J@@QEAA@XZ; CTraceFuncW<long>::~CTraceFuncW<long>(void)
0x18003f7dc  mov     eax, ebx
0x18003f7de  lea     r11, [rsp+0D0h+var_20]
0x18003f7e6  mov     rbx, [r11+30h]
0x18003f7ea  mov     rsi, [r11+38h]
0x18003f7ee  mov     rsp, r11
0x18003f7f1  pop     r15
0x18003f7f3  pop     r14
0x18003f7f5  pop     r12
0x18003f7f7  pop     rdi
0x18003f7f8  pop     rbp
0x18003f7f9  retn
```
