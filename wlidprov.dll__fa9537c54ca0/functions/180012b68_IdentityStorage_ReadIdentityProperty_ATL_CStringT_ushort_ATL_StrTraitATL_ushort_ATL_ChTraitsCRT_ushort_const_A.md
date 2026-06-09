# IdentityStorage::ReadIdentityProperty(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,_ModernIdentityType,ulong &,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> &)

- ea: `0x180012b68`
- end: `0x180012e6c`
- name: `?ReadIdentityProperty@IdentityStorage@@QEAAJAEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@0W4_ModernIdentityType@@AEAKAEAV23@@Z`
- size: `772`
- prototype: `__int64 __usercall@<rax>(IdentityStorage *this@<rcx>, __int64, __int64)`
- caller_count: `1`
- callee_count: `19`
- tags: `authz_impersonation, service_task`

## callers

- `0x180012b30`

## callees

- `0x180003990`
- `0x180003cf0`
- `0x180004824`
- `0x180004910`
- `0x180004b00`
- `0x180004b44`
- `0x180004dd4`
- `0x1800061a8`
- `0x180006aa4`
- `0x1800090c0`
- `0x180009630`
- `0x18000a400`
- `0x180010adc`
- `0x180010b80`
- `0x180012b68`
- `0x180012f5c`
- `0x180013130`
- `0x180014ac4`
- `0x1800161d0`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180012cd9`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180012cd9`

## string_xrefs

- `0x180012ca2`: `hr = ReadIdentityData( packageSid, identityType, targets, localApplicationFlags, tokenArray, identityPropertyArray)`
- `0x180012bdd`: `IdentityStorage::ReadIdentityProperty`
- `0x180012d0c`: `IdentityStorage::ReadIdentityProperty`
- `0x180012df3`: `Property read from immersive cache: %ls=%ls.`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
__int64 __fastcall IdentityStorage::ReadIdentityProperty(
        IdentityStorage *this,
        __int64 a2,
        _QWORD *a3,
        __int64 a4,
        _DWORD *a5,
        _QWORD *a6)
{
  _DWORD *v8; // r12
  _QWORD *v9; // r14
  void *v10; // rax
  int IdentityData; // eax
  unsigned __int64 v12; // rdi
  __int64 v13; // rbx
  _QWORD *v14; // rax
  unsigned int v15; // ebx
  __int64 v17; // rdx
  __int64 v18; // rbx
  int *v19; // rdi
  __int64 v20; // rbx
  int *v21; // rdi
  __int64 v22; // rbx
  char *v23; // [rsp+20h] [rbp-E0h]
  int v24; // [rsp+50h] [rbp-B0h] BYREF
  _DWORD v25[3]; // [rsp+54h] [rbp-ACh] BYREF
  __int64 v26; // [rsp+60h] [rbp-A0h] BYREF
  unsigned __int64 v27; // [rsp+68h] [rbp-98h]
  __int64 v28; // [rsp+70h] [rbp-90h]
  int v29; // [rsp+78h] [rbp-88h]
  _QWORD v30[3]; // [rsp+80h] [rbp-80h] BYREF
  int v31; // [rsp+98h] [rbp-68h]
  __int64 v32[3]; // [rsp+A0h] [rbp-60h] BYREF
  int v33; // [rsp+B8h] [rbp-48h]
  __int64 v34; // [rsp+C0h] [rbp-40h]
  int *v35[4]; // [rsp+C8h] [rbp-38h] BYREF
  _QWORD v36[13]; // [rsp+E8h] [rbp-18h] BYREF

  v24 = 0;
  memset(v30, 0, sizeof(v30));
  v31 = 0;
  memset(v32, 0, sizeof(v32));
  v33 = 0;
  v34 = 0;
  v26 = 0;
  v27 = 0;
  v28 = 0;
  v29 = 0;
  v25[0] = 0;
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(&v25[1]);
  v36[0] = "IdentityStorage::ReadIdentityProperty";
  v36[1] = &v24;
  v36[2] = 0;
  v36[3] = 0;
  MsaTracingInternal::TraceFunctionEnter(
    (MsaTracingInternal *)"onecoreuap\\ds\\ext\\live\\identity\\lib\\immersiveidentitystorage\\identitystorage.cpp",
    "IdentityStorage::ReadIdentityProperty",
    (const char *)0x265,
    0,
    (const unsigned __int16 *)v23);
  ErrorVerifier::ErrorVerifier(
    (ErrorVerifier *)v35,
    "IdentityStorage::ReadIdentityProperty",
    &v24,
    0xCu,
    &qword_18006F760);
  v8 = a5;
  *a5 = 0;
  v9 = a6;
  ATL::CSimpleStringT<unsigned short,0>::Empty(a6);
  v10 = (void *)ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
                  &a5,
                  &qword_180063440);
  IdentityData = IdentityStorage::ReadIdentityData(this, (__int64)v25, (__int64)v32, (__int64)&v26, 0, v10);
  v24 = IdentityData;
  if ( IdentityData >= 0 )
  {
    v12 = v27;
    v13 = 0;
    if ( v27 )
    {
      while ( 1 )
      {
        v14 = (_QWORD *)ATL::CAtlArray<IdentityProperty,ATL::CElementTraits<IdentityProperty>>::operator[](&v26, v13);
        if ( !(unsigned int)_o__wcsicmp(*v14, *a3) )
          break;
        if ( ++v13 >= v12 )
          goto LABEL_6;
      }
      v17 = *(_QWORD *)(ATL::CAtlArray<IdentityProperty,ATL::CElementTraits<IdentityProperty>>::operator[](&v26, v13) + 8);
      v18 = *(_QWORD *)&v25[1];
      v19 = (int *)(*(_QWORD *)&v25[1] - 24LL);
      if ( v17 - 24 != *(_QWORD *)&v25[1] - 24LL )
      {
        if ( v19[4] >= 0 && *(_QWORD *)(v17 - 24) == *(_QWORD *)v19 )
        {
          v20 = ATL::CSimpleStringT<unsigned short,0>::CloneData();
          ATL::CStringData::Release((ATL::CStringData *)v19);
          v18 = v20 + 24;
          *(_QWORD *)&v25[1] = v18;
        }
        else
        {
          ATL::CSimpleStringT<unsigned short,0>::SetString(&v25[1], v17, *(unsigned int *)(v17 - 16));
          v18 = *(_QWORD *)&v25[1];
        }
      }
      TracePrintW(
        5u,
        "onecoreuap\\ds\\ext\\live\\identity\\lib\\immersiveidentitystorage\\identitystorage.cpp",
        0x27Fu,
        L"Property read from immersive cache: %ls=%ls.",
        *a3,
        *v9);
      *v8 = v25[0];
      v21 = (int *)(*v9 - 24LL);
      if ( (int *)(v18 - 24) != v21 )
      {
        if ( v21[4] >= 0 && *(_QWORD *)(v18 - 24) == *(_QWORD *)v21 )
        {
          v22 = ATL::CSimpleStringT<unsigned short,0>::CloneData();
          ATL::CStringData::Release((ATL::CStringData *)v21);
          *v9 = v22 + 24;
        }
        else
        {
          ATL::CSimpleStringT<unsigned short,0>::SetString(v9, v18, *(unsigned int *)(v18 - 16));
        }
      }
    }
    else
    {
LABEL_6:
      v24 = -2147023728;
      Telemetry::IfFailExit(
        "onecoreuap\\ds\\ext\\live\\identity\\lib\\immersiveidentitystorage\\identitystorage.cpp",
        "IdentityStorage::ReadIdentityProperty",
        0x285u,
        -2147023728,
        "propertyFound");
    }
  }
  else
  {
    Telemetry::IfFailExit(
      "onecoreuap\\ds\\ext\\live\\identity\\lib\\immersiveidentitystorage\\identitystorage.cpp",
      "IdentityStorage::ReadIdentityProperty",
      0x276u,
      IdentityData,
      "hr = ReadIdentityData( packageSid, identityType, targets, localApplicationFlags, tokenArray, identityPropertyArray)");
  }
  v15 = v24;
  ErrorVerifier::CheckAgainstList((const char *)v35[3], *v35[2], (unsigned __int64)v35[1], v35[0]);
  CTraceFuncW<long>::~CTraceFuncW<long>(v36);
  ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v25[1]);
  ATL::CAtlArray<IdentityProperty,ATL::CElementTraits<IdentityProperty>>::~CAtlArray<IdentityProperty,ATL::CElementTraits<IdentityProperty>>(&v26);
  ATL::CAtlArray<IdentityToken,ATL::CElementTraits<IdentityToken>>::~CAtlArray<IdentityToken,ATL::CElementTraits<IdentityToken>>(v32);
  ATL::CAtlArray<OnlineIdServiceTicketRequestInternal,ATL::CElementTraits<OnlineIdServiceTicketRequestInternal>>::~CAtlArray<OnlineIdServiceTicketRequestInternal,ATL::CElementTraits<OnlineIdServiceTicketRequestInternal>>(v30);
  return v15;
}

```

## disassembly

```asm
0x180012b68  push    rbp
0x180012b6a  push    rbx
0x180012b6b  push    rsi
0x180012b6c  push    rdi
0x180012b6d  push    r12
0x180012b6f  push    r13
0x180012b71  push    r14
0x180012b73  push    r15
0x180012b75  lea     rbp, [rsp-18h]
0x180012b7a  sub     rsp, 118h
0x180012b81  mov     esi, r9d
0x180012b84  mov     r15, r8
0x180012b87  mov     rbx, rdx
0x180012b8a  mov     rdi, rcx
0x180012b8d  xor     r13d, r13d
0x180012b90  mov     [rsp+150h+var_100], r13d
0x180012b95  mov     [rbp+50h+var_D0], r13
0x180012b99  mov     [rbp+50h+var_C8], r13
0x180012b9d  mov     [rbp+50h+var_C0], r13
0x180012ba1  mov     [rbp+50h+var_B8], r13d
0x180012ba5  mov     [rbp+50h+var_B0], r13
0x180012ba9  mov     [rbp+50h+var_A8], r13
0x180012bad  mov     [rbp+50h+var_A0], r13
0x180012bb1  mov     [rbp+50h+var_98], r13d
0x180012bb5  mov     [rbp+50h+var_90], r13
0x180012bb9  mov     [rsp+150h+var_F0], r13
0x180012bbe  mov     [rsp+150h+var_E8], r13
0x180012bc3  mov     [rsp+150h+var_E0], r13
0x180012bc8  mov     [rsp+150h+var_D8], r13d
0x180012bcd  mov     dword ptr [rsp+150h+var_FC], r13d
0x180012bd2  lea     rcx, [rsp+150h+var_FC+4]; void *
0x180012bd7  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(void)
0x180012bdc  nop
0x180012bdd  lea     r14, aIdentitystorag_7; "IdentityStorage::ReadIdentityProperty"
0x180012be4  mov     [rbp+50h+var_68], r14
0x180012be8  lea     rax, [rsp+150h+var_100]
0x180012bed  mov     [rbp+50h+var_60], rax
0x180012bf1  mov     [rbp+50h+var_58], r13
0x180012bf5  mov     [rbp+50h+var_50], r13
0x180012bf9  xor     r9d, r9d; unsigned int
0x180012bfc  mov     r8d, 265h; char *
0x180012c02  mov     rdx, r14; char *
0x180012c05  lea     rcx, aOnecoreuapDsEx_0; "onecoreuap\\ds\\ext\\live\\identity\\li"...
0x180012c0c  call    ?TraceFunctionEnter@MsaTracingInternal@@YAKPEBD0KPEBG@Z; MsaTracingInternal::TraceFunctionEnter(char const *,char const *,ulong,ushort const *)
0x180012c11  nop
0x180012c12  lea     rax, qword_18006F760
0x180012c19  mov     [rsp+150h+var_130], rax; int *
0x180012c1e  lea     r9d, [r13+0Ch]; unsigned __int64
0x180012c22  lea     r8, [rsp+150h+var_100]; int *
0x180012c27  mov     rdx, r14; char *
0x180012c2a  lea     rcx, [rbp+50h+var_88]; this
0x180012c2e  call    ??0ErrorVerifier@@QEAA@PEBDPEAJ_KPEBJ@Z; ErrorVerifier::ErrorVerifier(char const *,long *,unsigned __int64,long const *)
0x180012c33  nop
0x180012c34  mov     r12, [rbp+50h+arg_20]
0x180012c3b  mov     [r12], r13d
0x180012c3f  mov     r14, [rbp+50h+arg_28]
0x180012c46  mov     rcx, r14
0x180012c49  call    ?Empty@?$CSimpleStringT@G$0A@@ATL@@QEAAXXZ; ATL::CSimpleStringT<ushort,0>::Empty(void)
0x180012c4e  lea     rdx, qword_180063440
0x180012c55  lea     rcx, [rbp+50h+arg_20]
0x180012c5c  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ushort const *)
0x180012c61  mov     [rsp+150h+var_110], rax; void *
0x180012c66  mov     [rsp+150h+var_118], r13b; char
0x180012c6b  lea     rax, [rsp+150h+var_F0]
0x180012c70  mov     [rsp+150h+var_120], rax; __int64
0x180012c75  lea     rax, [rbp+50h+var_B0]
0x180012c79  mov     [rsp+150h+var_128], rax; __int64
0x180012c7e  lea     rax, [rsp+150h+var_FC]
0x180012c83  mov     [rsp+150h+var_130], rax; __int64
0x180012c88  lea     r9, [rbp+50h+var_D0]
0x180012c8c  mov     r8d, esi
0x180012c8f  mov     rdx, rbx
0x180012c92  mov     rcx, rdi; this
0x180012c95  call    ?ReadIdentityData@IdentityStorage@@QEAAJAEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@W4_ModernIdentityType@@AEBV?$CAtlArray@UOnlineIdServiceTicketRequestInternal@@V?$CElementTraits@UOnlineIdServiceTicketRequestInternal@@@ATL@@@3@AEAKAEAVCIdentityTokenCacheArray@@AEAV?$CAtlArray@UIdentityProperty@@V?$CElementTraits@UIdentityProperty@@@ATL@@@3@_NV23@@Z; IdentityStorage::ReadIdentityData(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,_ModernIdentityType,ATL::CAtlArray<OnlineIdServiceTicketRequestInternal,ATL::CElementTraits<OnlineIdServiceTicketRequestInternal>> const &,ulong &,CIdentityTokenCacheArray &,ATL::CAtlArray<IdentityProperty,ATL::CElementTraits<IdentityProperty>> &,bool,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>)
0x180012c9a  mov     [rsp+150h+var_100], eax
0x180012c9e  test    eax, eax
0x180012ca0  jns     short loc_180012CB9
0x180012ca2  lea     r8, aHrReadidentity; "hr = ReadIdentityData( packageSid, iden"...
0x180012ca9  mov     [rsp+150h+var_130], r8
0x180012cae  mov     r9d, eax
0x180012cb1  mov     r8d, 276h
0x180012cb7  jmp     short loc_180012D0C
0x180012cb9  mov     rdi, [rsp+150h+var_E8]
0x180012cbe  mov     rbx, r13
0x180012cc1  test    rdi, rdi
0x180012cc4  jz      short loc_180012CEF
0x180012cc6  mov     rdx, rbx
0x180012cc9  lea     rcx, [rsp+150h+var_F0]
0x180012cce  call    ??A?$CAtlArray@UIdentityProperty@@V?$CElementTraits@UIdentityProperty@@@ATL@@@ATL@@QEAAAEAUIdentityProperty@@_K@Z; ATL::CAtlArray<IdentityProperty,ATL::CElementTraits<IdentityProperty>>::operator[](unsigned __int64)
0x180012cd3  mov     rdx, [r15]
0x180012cd6  mov     rcx, [rax]
0x180012cd9  call    cs:__imp__o__wcsicmp
0x180012cdf  test    eax, eax
0x180012ce1  jz      loc_180012D84
0x180012ce7  inc     rbx
0x180012cea  cmp     rbx, rdi
0x180012ced  jb      short loc_180012CC6
0x180012cef  mov     r9d, 80070490h; int
0x180012cf5  mov     [rsp+150h+var_100], r9d
0x180012cfa  lea     rax, aPropertyfound; "propertyFound"
0x180012d01  mov     [rsp+150h+var_130], rax; char *
0x180012d06  mov     r8d, 285h; unsigned int
0x180012d0c  lea     rdx, aIdentitystorag_7; "IdentityStorage::ReadIdentityProperty"
0x180012d13  lea     rcx, aOnecoreuapDsEx_0; "onecoreuap\\ds\\ext\\live\\identity\\li"...
0x180012d1a  call    ?IfFailExit@Telemetry@@SAXPEBD0KJ0@Z; Telemetry::IfFailExit(char const *,char const *,ulong,long,char const *)
0x180012d1f  mov     ebx, [rsp+150h+var_100]
0x180012d23  mov     r9, [rbp+50h+var_88]; int *
0x180012d27  mov     r8, [rbp+50h+var_80]; unsigned __int64
0x180012d2b  mov     rdx, [rbp+50h+var_78]
0x180012d2f  mov     edx, [rdx]; int
0x180012d31  mov     rcx, [rbp+50h+var_70]; char *
0x180012d35  call    ?CheckAgainstList@ErrorVerifier@@SAXPEBDJ_KPEBJ@Z; ErrorVerifier::CheckAgainstList(char const *,long,unsigned __int64,long const *)
0x180012d3a  nop
0x180012d3b  lea     rcx, [rbp+50h+var_68]
0x180012d3f  call    ??1?$CTraceFuncW@J@@QEAA@XZ; CTraceFuncW<long>::~CTraceFuncW<long>(void)
0x180012d44  nop
0x180012d45  lea     rcx, [rsp+150h+var_FC+4]; void *
0x180012d4a  call    ??1?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(void)
0x180012d4f  nop
0x180012d50  lea     rcx, [rsp+150h+var_F0]
0x180012d55  call    ??1?$CAtlArray@UIdentityProperty@@V?$CElementTraits@UIdentityProperty@@@ATL@@@ATL@@QEAA@XZ; ATL::CAtlArray<IdentityProperty,ATL::CElementTraits<IdentityProperty>>::~CAtlArray<IdentityProperty,ATL::CElementTraits<IdentityProperty>>(void)
0x180012d5a  nop
0x180012d5b  lea     rcx, [rbp+50h+var_B0]
0x180012d5f  call    ??1?$CAtlArray@UIdentityToken@@V?$CElementTraits@UIdentityToken@@@ATL@@@ATL@@QEAA@XZ; ATL::CAtlArray<IdentityToken,ATL::CElementTraits<IdentityToken>>::~CAtlArray<IdentityToken,ATL::CElementTraits<IdentityToken>>(void)
0x180012d64  nop
0x180012d65  lea     rcx, [rbp+50h+var_D0]
0x180012d69  call    ??1?$CAtlArray@UOnlineIdServiceTicketRequestInternal@@V?$CElementTraits@UOnlineIdServiceTicketRequestInternal@@@ATL@@@ATL@@QEAA@XZ; ATL::CAtlArray<OnlineIdServiceTicketRequestInternal,ATL::CElementTraits<OnlineIdServiceTicketRequestInternal>>::~CAtlArray<OnlineIdServiceTicketRequestInternal,ATL::CElementTraits<OnlineIdServiceTicketRequestInternal>>(void)
0x180012d6e  mov     eax, ebx
0x180012d70  add     rsp, 118h
0x180012d77  pop     r15
0x180012d79  pop     r14
0x180012d7b  pop     r13
0x180012d7d  pop     r12
0x180012d7f  pop     rdi
0x180012d80  pop     rsi
0x180012d81  pop     rbx
0x180012d82  pop     rbp
0x180012d83  retn
0x180012d84  mov     rdx, rbx
0x180012d87  lea     rcx, [rsp+150h+var_F0]
0x180012d8c  call    ??A?$CAtlArray@UIdentityProperty@@V?$CElementTraits@UIdentityProperty@@@ATL@@@ATL@@QEAAAEAUIdentityProperty@@_K@Z; ATL::CAtlArray<IdentityProperty,ATL::CElementTraits<IdentityProperty>>::operator[](unsigned __int64)
0x180012d91  mov     rdx, [rax+8]
0x180012d95  lea     rcx, [rdx-18h]
0x180012d99  mov     rbx, qword ptr [rsp+150h+var_FC+4]
0x180012d9e  lea     rdi, [rbx-18h]
0x180012da2  cmp     rcx, rdi
0x180012da5  jz      short loc_180012DE3
0x180012da7  cmp     [rdi+10h], r13d
0x180012dab  jl      short loc_180012DD0
0x180012dad  mov     rax, [rdi]
0x180012db0  cmp     [rcx], rax
0x180012db3  jnz     short loc_180012DD0
0x180012db5  call    ?CloneData@?$CSimpleStringT@G$0A@@ATL@@CAPEAUCStringData@2@PEAU32@@Z; ATL::CSimpleStringT<ushort,0>::CloneData(ATL::CStringData *)
0x180012dba  mov     rbx, rax
0x180012dbd  mov     rcx, rdi; this
0x180012dc0  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x180012dc5  add     rbx, 18h
0x180012dc9  mov     qword ptr [rsp+150h+var_FC+4], rbx
0x180012dce  jmp     short loc_180012DE3
0x180012dd0  mov     r8d, [rdx-10h]
0x180012dd4  lea     rcx, [rsp+150h+var_FC+4]
0x180012dd9  call    ?SetString@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBGH@Z; ATL::CSimpleStringT<ushort,0>::SetString(ushort const *,int)
0x180012dde  mov     rbx, qword ptr [rsp+150h+var_FC+4]
0x180012de3  mov     rax, [r14]
0x180012de6  mov     [rsp+150h+var_128], rax
0x180012deb  mov     rax, [r15]
0x180012dee  mov     [rsp+150h+var_130], rax
0x180012df3  lea     r9, aPropertyReadFr; "Property read from immersive cache: %ls"...
0x180012dfa  mov     r8d, 27Fh; unsigned int
0x180012e00  lea     rdx, aOnecoreuapDsEx_0; "onecoreuap\\ds\\ext\\live\\identity\\li"...
0x180012e07  mov     ecx, 5; unsigned __int8
0x180012e0c  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x180012e11  mov     eax, dword ptr [rsp+150h+var_FC]
0x180012e15  mov     [r12], eax
0x180012e19  lea     rcx, [rbx-18h]
0x180012e1d  mov     rdi, [r14]
0x180012e20  add     rdi, 0FFFFFFFFFFFFFFE8h
0x180012e24  cmp     rcx, rdi
0x180012e27  jz      loc_180012D1F
0x180012e2d  cmp     [rdi+10h], r13d
0x180012e31  jl      short loc_180012E57
0x180012e33  mov     rax, [rdi]
0x180012e36  cmp     [rcx], rax
0x180012e39  jnz     short loc_180012E57
0x180012e3b  call    ?CloneData@?$CSimpleStringT@G$0A@@ATL@@CAPEAUCStringData@2@PEAU32@@Z; ATL::CSimpleStringT<ushort,0>::CloneData(ATL::CStringData *)
0x180012e40  mov     rbx, rax
0x180012e43  mov     rcx, rdi; this
0x180012e46  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x180012e4b  lea     rax, [rbx+18h]
0x180012e4f  mov     [r14], rax
0x180012e52  jmp     loc_180012D1F
0x180012e57  mov     r8d, [rbx-10h]
0x180012e5b  mov     rdx, rbx
0x180012e5e  mov     rcx, r14
0x180012e61  call    ?SetString@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBGH@Z; ATL::CSimpleStringT<ushort,0>::SetString(ushort const *,int)
0x180012e66  jmp     loc_180012D1F
```
