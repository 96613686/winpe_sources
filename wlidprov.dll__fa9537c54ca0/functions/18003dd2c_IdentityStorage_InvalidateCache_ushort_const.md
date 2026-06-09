# IdentityStorage::InvalidateCache(ushort const *)

- ea: `0x18003dd2c`
- end: `0x18003dfcc`
- name: `?InvalidateCache@IdentityStorage@@QEAAJPEBG@Z`
- size: `672`
- prototype: `__int64 __fastcall(IdentityStorage *__hidden this, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `19`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18003b180`

## callees

- `0x180003054`
- `0x1800034c0`
- `0x1800035cc`
- `0x180003990`
- `0x180004824`
- `0x180004910`
- `0x180004fdc`
- `0x1800050f8`
- `0x18000535c`
- `0x1800061a8`
- `0x1800090c0`
- `0x180009630`
- `0x18000a400`
- `0x180010b80`
- `0x180013434`
- `0x1800185c8`
- `0x18003d0d0`
- `0x18003dd2c`
- `0x180058010`

## string_xrefs

- `0x18003defd`: `DeleteBufferFromRegistry failed = 0x%x`
- `0x18003de51`: `hr = registryHelper.GetRootKey(pRegistryFunctions, HKEY_CURRENT_USER, &useKeyCurrentUser, &hkeyCurrentUser)`
- `0x18003dea1`: `hr = registryHelper.ReadBufferFromRegistry(hkeyCurrentUser, registryKey, UserId, RRF_RT_REG_SZ, &apUserIdBuffer, &userIdBufferSize)`
- `0x18003ddc2`: `IdentityStorage::InvalidateCache`
- `0x18003df31`: `hr = DeleteTicketsForUser(userIdToClear)`
- `0x18003dd79`: `Software\Microsoft\IdentityCRL\Immersive\%s\Token\`

## pseudocode

```c
// Hidden C++ exception states: #wind=10
__int64 __fastcall IdentityStorage::InvalidateCache(IdentityStorage *this, const unsigned __int16 *a2)
{
  struct IRegistryFunctions *v4; // rdi
  void *EnvironmentSpecificRegistryKey; // rax
  RegistryHelper *v6; // rcx
  int RootKey; // eax
  int v8; // eax
  const char *v9; // rcx
  unsigned int v10; // r8d
  unsigned int v11; // ebx
  HKEY *v13; // [rsp+20h] [rbp-69h]
  HKEY *v14; // [rsp+20h] [rbp-69h]
  _BYTE v15[8]; // [rsp+40h] [rbp-49h] BYREF
  unsigned __int16 *v16; // [rsp+48h] [rbp-41h] BYREF
  __int64 v17; // [rsp+50h] [rbp-39h] BYREF
  HKEY v18[3]; // [rsp+58h] [rbp-31h] BYREF
  HKEY v19; // [rsp+70h] [rbp-19h] BYREF
  _BYTE v20[8]; // [rsp+78h] [rbp-11h] BYREF
  int *v21[4]; // [rsp+80h] [rbp-9h] BYREF
  _QWORD v22[8]; // [rsp+A0h] [rbp+17h] BYREF
  unsigned int v23; // [rsp+F0h] [rbp+67h] BYREF
  int v24; // [rsp+100h] [rbp+77h] BYREF
  unsigned __int8 *v25; // [rsp+108h] [rbp+7Fh] BYREF

  v24 = 0;
  v4 = (struct IRegistryFunctions *)(*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)this + 8LL))(*(_QWORD *)this);
  v18[0] = 0;
  v18[2] = (HKEY)v4;
  v18[1] = 0;
  v17 = *(_QWORD *)this;
  EnvironmentSpecificRegistryKey = IdentityStorage::GetEnvironmentSpecificRegistryKey(
                                     (__int64 *)this,
                                     &v23,
                                     (__int64)L"Software\\Microsoft\\IdentityCRL\\Immersive\\%s\\Token\\");
  ATL::operator+(&v16, EnvironmentSpecificRegistryKey, a2);
  ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v23);
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(v20);
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(v15);
  v25 = 0;
  v22[0] = "IdentityStorage::InvalidateCache";
  v22[1] = &v24;
  v22[2] = 0;
  v22[3] = 0;
  MsaTracingInternal::TraceFunctionEnter(
    (MsaTracingInternal *)"onecoreuap\\ds\\ext\\live\\identity\\lib\\immersiveidentitystorage\\identitystorage.cpp",
    "IdentityStorage::InvalidateCache",
    (const char *)0x5AD,
    0,
    (const unsigned __int16 *)v13);
  ErrorVerifier::ErrorVerifier((ErrorVerifier *)v21, "IdentityStorage::InvalidateCache", &v24, 0xCu, &qword_18006F6A0);
  v19 = HKEY_CURRENT_USER;
  RootKey = RegistryHelper::GetRootKey(v6, v4, &v19, (bool *)&v23, v18);
  v24 = RootKey;
  if ( RootKey >= 0 )
  {
    v8 = RegistryHelper::ReadBufferFromRegistry((RegistryHelper *)&v17, v18[0], v16, L"UserId", 2u, &v25, &v23);
    v24 = v8;
    if ( v8 >= 0 )
    {
      ATL::CSimpleStringT<unsigned short,0>::SetString(v15, v25);
      v8 = RegistryHelper::DeleteBufferFromRegistry((RegistryHelper *)&v17, v18[0], v16, L"UserTicket");
      v24 = v8;
      if ( v8 == -2147024894 || v8 == -2147023878 )
      {
        LODWORD(v14) = v8;
        TracePrintW(
          3u,
          "onecoreuap\\ds\\ext\\live\\identity\\lib\\immersiveidentitystorage\\identitystorage.cpp",
          0x5C3u,
          L"DeleteBufferFromRegistry failed = 0x%x",
          v14);
        v24 = 0;
      }
      else if ( v8 < 0 )
      {
        v9 = "hr";
        v10 = 1479;
        goto LABEL_12;
      }
      v8 = IdentityStorage::DeleteTicketsForUser(this, v15);
      v24 = v8;
      if ( v8 >= 0 )
        goto LABEL_13;
      v9 = "hr = DeleteTicketsForUser(userIdToClear)";
      v10 = 1480;
    }
    else
    {
      v9 = "hr = registryHelper.ReadBufferFromRegistry(hkeyCurrentUser, registryKey, UserId, RRF_RT_REG_SZ, &apUserIdBuff"
           "er, &userIdBufferSize)";
      v10 = 1465;
    }
LABEL_12:
    Telemetry::IfFailExit(
      "onecoreuap\\ds\\ext\\live\\identity\\lib\\immersiveidentitystorage\\identitystorage.cpp",
      "IdentityStorage::InvalidateCache",
      v10,
      v8,
      v9);
    goto LABEL_13;
  }
  Telemetry::IfFailExit(
    "onecoreuap\\ds\\ext\\live\\identity\\lib\\immersiveidentitystorage\\identitystorage.cpp",
    "IdentityStorage::InvalidateCache",
    0x5B5u,
    RootKey,
    "hr = registryHelper.GetRootKey(pRegistryFunctions, HKEY_CURRENT_USER, &useKeyCurrentUser, &hkeyCurrentUser)");
LABEL_13:
  if ( v24 == -2147024894 || v24 == -2147023878 )
    v24 = -2147023579;
  v11 = v24;
  ErrorVerifier::CheckAgainstList((const char *)v21[3], *v21[2], (unsigned __int64)v21[1], v21[0]);
  CTraceFuncW<long>::~CTraceFuncW<long>(v22);
  CMIDLPtr<unsigned short *>::Clear(&v25);
  ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(v15);
  ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(v20);
  ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v16);
  Auto<HKEY__ *,RegistryFunctor,IRegistryFunctions>::~Auto<HKEY__ *,RegistryFunctor,IRegistryFunctions>(v18);
  return v11;
}

```

## disassembly

```asm
0x18003dd2c  push    rbp
0x18003dd2e  push    rbx
0x18003dd2f  push    rsi
0x18003dd30  push    rdi
0x18003dd31  push    r15
0x18003dd33  lea     rbp, [rsp-37h]
0x18003dd38  sub     rsp, 0C0h
0x18003dd3f  mov     rbx, rdx
0x18003dd42  mov     rsi, rcx
0x18003dd45  mov     [rbp+57h+arg_10], 0
0x18003dd4c  mov     rcx, [rcx]
0x18003dd4f  mov     rax, [rcx]
0x18003dd52  mov     rax, [rax+8]
0x18003dd56  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003dd5b  mov     rdi, rax
0x18003dd5e  mov     [rbp+57h+var_88], 0
0x18003dd66  mov     [rbp+57h+var_78], rax
0x18003dd6a  mov     [rbp+57h+var_80], 0
0x18003dd72  mov     rcx, [rsi]
0x18003dd75  mov     [rbp+57h+var_90], rcx
0x18003dd79  lea     r8, aSoftwareMicros_5; "Software\\Microsoft\\IdentityCRL\\Immer"...
0x18003dd80  lea     rdx, [rbp+57h+arg_0]
0x18003dd84  mov     rcx, rsi
0x18003dd87  call    ?GetEnvironmentSpecificRegistryKey@IdentityStorage@@AEAA?AV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@PEBG@Z; IdentityStorage::GetEnvironmentSpecificRegistryKey(ushort const *)
0x18003dd8c  nop
0x18003dd8d  mov     r8, rbx
0x18003dd90  mov     rdx, rax
0x18003dd93  lea     rcx, [rbp+57h+var_98]
0x18003dd97  call    ??HATL@@YA?AV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@0@AEBV10@PEBG@Z; ATL::operator+(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,ushort const *)
0x18003dd9c  nop
0x18003dd9d  lea     rcx, [rbp+57h+arg_0]; void *
0x18003dda1  call    ??1?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(void)
0x18003dda6  lea     rcx, [rbp+57h+var_68]; void *
0x18003ddaa  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(void)
0x18003ddaf  nop
0x18003ddb0  lea     rcx, [rbp+57h+var_A0]; void *
0x18003ddb4  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(void)
0x18003ddb9  nop
0x18003ddba  mov     [rbp+57h+arg_18], 0
0x18003ddc2  lea     r15, aIdentitystorag_2; "IdentityStorage::InvalidateCache"
0x18003ddc9  mov     [rbp+57h+var_40], r15
0x18003ddcd  lea     rax, [rbp+57h+arg_10]
0x18003ddd1  mov     [rbp+57h+var_38], rax
0x18003ddd5  mov     [rbp+57h+var_30], 0
0x18003dddd  mov     [rbp+57h+var_28], 0
0x18003dde5  xor     r9d, r9d; unsigned int
0x18003dde8  mov     r8d, 5ADh; char *
0x18003ddee  mov     rdx, r15; char *
0x18003ddf1  lea     rbx, aOnecoreuapDsEx_0; "onecoreuap\\ds\\ext\\live\\identity\\li"...
0x18003ddf8  mov     rcx, rbx; this
0x18003ddfb  call    ?TraceFunctionEnter@MsaTracingInternal@@YAKPEBD0KPEBG@Z; MsaTracingInternal::TraceFunctionEnter(char const *,char const *,ulong,ushort const *)
0x18003de00  nop
0x18003de01  lea     rax, qword_18006F6A0
0x18003de08  mov     [rsp+0E0h+var_C0], rax; int *
0x18003de0d  mov     r9d, 0Ch; unsigned __int64
0x18003de13  lea     r8, [rbp+57h+arg_10]; int *
0x18003de17  mov     rdx, r15; char *
0x18003de1a  lea     rcx, [rbp+57h+var_60]; this
0x18003de1e  call    ??0ErrorVerifier@@QEAA@PEBDPEAJ_KPEBJ@Z; ErrorVerifier::ErrorVerifier(char const *,long *,unsigned __int64,long const *)
0x18003de23  nop
0x18003de24  mov     [rbp+57h+var_70], 0FFFFFFFF80000001h
0x18003de2c  lea     rax, [rbp+57h+var_88]
0x18003de30  mov     [rsp+0E0h+var_C0], rax; HKEY *
0x18003de35  lea     r9, [rbp+57h+arg_0]; bool *
0x18003de39  lea     r8, [rbp+57h+var_70]; HKEY *
0x18003de3d  mov     rdx, rdi; struct IRegistryFunctions *
0x18003de40  call    ?GetRootKey@RegistryHelper@@QEAAJPEAVIRegistryFunctions@@AEBQEAUHKEY__@@PEA_NPEAPEAU3@@Z; RegistryHelper::GetRootKey(IRegistryFunctions *,HKEY__ * const &,bool *,HKEY__ * *)
0x18003de45  mov     [rbp+57h+arg_10], eax
0x18003de48  mov     edi, 800703FAh
0x18003de4d  test    eax, eax
0x18003de4f  jns     short loc_18003DE68
0x18003de51  lea     r8, aHrRegistryhelp_15; "hr = registryHelper.GetRootKey(pRegistr"...
0x18003de58  mov     [rsp+0E0h+var_C0], r8
0x18003de5d  mov     r8d, 5B5h
0x18003de63  jmp     loc_18003DF43
0x18003de68  lea     rax, [rbp+57h+arg_0]
0x18003de6c  mov     [rsp+0E0h+var_B0], rax; unsigned int *
0x18003de71  lea     rax, [rbp+57h+arg_18]
0x18003de75  mov     [rsp+0E0h+var_B8], rax; unsigned __int8 **
0x18003de7a  mov     dword ptr [rsp+0E0h+var_C0], 2; unsigned int
0x18003de82  lea     r9, aUserid; "UserId"
0x18003de89  mov     r8, [rbp+57h+var_98]; unsigned __int16 *
0x18003de8d  mov     rdx, [rbp+57h+var_88]; HKEY
0x18003de91  lea     rcx, [rbp+57h+var_90]; this
0x18003de95  call    ?ReadBufferFromRegistry@RegistryHelper@@QEAAJPEAUHKEY__@@PEBG1KPEAPEAEPEAK@Z; RegistryHelper::ReadBufferFromRegistry(HKEY__ *,ushort const *,ushort const *,ulong,uchar * *,ulong *)
0x18003de9a  mov     [rbp+57h+arg_10], eax
0x18003de9d  test    eax, eax
0x18003de9f  jns     short loc_18003DEB3
0x18003dea1  lea     rcx, aHrRegistryhelp_0; "hr = registryHelper.ReadBufferFromRegis"...
0x18003dea8  mov     r8d, 5B9h
0x18003deae  jmp     loc_18003DF3E
0x18003deb3  mov     rdx, [rbp+57h+arg_18]
0x18003deb7  lea     rcx, [rbp+57h+var_A0]
0x18003debb  call    ?SetString@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBG@Z; ATL::CSimpleStringT<ushort,0>::SetString(ushort const *)
0x18003dec0  lea     r9, aUserticket; "UserTicket"
0x18003dec7  mov     r8, [rbp+57h+var_98]; unsigned __int16 *
0x18003decb  mov     rdx, [rbp+57h+var_88]; HKEY
0x18003decf  lea     rcx, [rbp+57h+var_90]; this
0x18003ded3  call    ?DeleteBufferFromRegistry@RegistryHelper@@QEAAJPEAUHKEY__@@PEBG1@Z; RegistryHelper::DeleteBufferFromRegistry(HKEY__ *,ushort const *,ushort const *)
0x18003ded8  mov     [rbp+57h+arg_10], eax
0x18003dedb  cmp     eax, 80070002h
0x18003dee0  jz      short loc_18003DEF9
0x18003dee2  cmp     eax, edi
0x18003dee4  jz      short loc_18003DEF9
0x18003dee6  test    eax, eax
0x18003dee8  jns     short loc_18003DF1E
0x18003deea  lea     rcx, aHr; "hr"
0x18003def1  mov     r8d, 5C7h
0x18003def7  jmp     short loc_18003DF3E
0x18003def9  mov     dword ptr [rsp+0E0h+var_C0], eax
0x18003defd  lea     r9, aDeletebufferfr_0; "DeleteBufferFromRegistry failed = 0x%x"
0x18003df04  mov     r8d, 5C3h; unsigned int
0x18003df0a  mov     rdx, rbx; char *
0x18003df0d  mov     ecx, 3; unsigned __int8
0x18003df12  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x18003df17  mov     [rbp+57h+arg_10], 0
0x18003df1e  lea     rdx, [rbp+57h+var_A0]
0x18003df22  mov     rcx, rsi
0x18003df25  call    ?DeleteTicketsForUser@IdentityStorage@@QEAAJAEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@Z; IdentityStorage::DeleteTicketsForUser(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &)
0x18003df2a  mov     [rbp+57h+arg_10], eax
0x18003df2d  test    eax, eax
0x18003df2f  jns     short loc_18003DF51
0x18003df31  lea     rcx, aHrDeleteticket; "hr = DeleteTicketsForUser(userIdToClear"...
0x18003df38  mov     r8d, 5C8h; unsigned int
0x18003df3e  mov     [rsp+0E0h+var_C0], rcx; char *
0x18003df43  mov     r9d, eax; int
0x18003df46  mov     rdx, r15; char *
0x18003df49  mov     rcx, rbx; char *
0x18003df4c  call    ?IfFailExit@Telemetry@@SAXPEBD0KJ0@Z; Telemetry::IfFailExit(char const *,char const *,ulong,long,char const *)
0x18003df51  cmp     [rbp+57h+arg_10], 80070002h
0x18003df58  jz      short loc_18003DF5F
0x18003df5a  cmp     [rbp+57h+arg_10], edi
0x18003df5d  jnz     short loc_18003DF66
0x18003df5f  mov     [rbp+57h+arg_10], 80070525h
0x18003df66  mov     ebx, [rbp+57h+arg_10]
0x18003df69  mov     r9, [rbp+57h+var_60]; int *
0x18003df6d  mov     r8, [rbp+57h+var_58]; unsigned __int64
0x18003df71  mov     rdx, [rbp+57h+var_50]
0x18003df75  mov     edx, [rdx]; int
0x18003df77  mov     rcx, [rbp+57h+var_48]; char *
0x18003df7b  call    ?CheckAgainstList@ErrorVerifier@@SAXPEBDJ_KPEBJ@Z; ErrorVerifier::CheckAgainstList(char const *,long,unsigned __int64,long const *)
0x18003df80  nop
0x18003df81  lea     rcx, [rbp+57h+var_40]
0x18003df85  call    ??1?$CTraceFuncW@J@@QEAA@XZ; CTraceFuncW<long>::~CTraceFuncW<long>(void)
0x18003df8a  nop
0x18003df8b  lea     rcx, [rbp+57h+arg_18]
0x18003df8f  call    ?Clear@?$CMIDLPtr@PEAG@@QEAAXXZ; CMIDLPtr<ushort *>::Clear(void)
0x18003df94  nop
0x18003df95  lea     rcx, [rbp+57h+var_A0]; void *
0x18003df99  call    ??1?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(void)
0x18003df9e  nop
0x18003df9f  lea     rcx, [rbp+57h+var_68]; void *
0x18003dfa3  call    ??1?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(void)
0x18003dfa8  nop
0x18003dfa9  lea     rcx, [rbp+57h+var_98]; void *
0x18003dfad  call    ??1?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(void)
0x18003dfb2  nop
0x18003dfb3  lea     rcx, [rbp+57h+var_88]
0x18003dfb7  call    ??1?$Auto@PEAUHKEY__@@VRegistryFunctor@@VIRegistryFunctions@@@@QEAA@XZ; Auto<HKEY__ *,RegistryFunctor,IRegistryFunctions>::~Auto<HKEY__ *,RegistryFunctor,IRegistryFunctions>(void)
0x18003dfbc  mov     eax, ebx
0x18003dfbe  add     rsp, 0C0h
0x18003dfc5  pop     r15
0x18003dfc7  pop     rdi
0x18003dfc8  pop     rsi
0x18003dfc9  pop     rbx
0x18003dfca  pop     rbp
0x18003dfcb  retn
```
