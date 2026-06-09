# IdentityStorage::DeleteIdentityData(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,bool,bool,bool &)

- ea: `0x18003c9cc`
- end: `0x18003cf9f`
- name: `?DeleteIdentityData@IdentityStorage@@QEAAJAEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@_N1AEA_N@Z`
- size: `1491`
- prototype: `__int64 __usercall@<rax>(IdentityStorage *this@<rcx>, __int64)`
- caller_count: `1`
- callee_count: `21`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18003b120`

## callees

- `0x180002eb4`
- `0x180003054`
- `0x1800034c0`
- `0x1800035cc`
- `0x180003990`
- `0x180004824`
- `0x180004910`
- `0x180004e30`
- `0x1800050f8`
- `0x1800061a8`
- `0x1800090c0`
- `0x180009630`
- `0x18000a400`
- `0x180010b80`
- `0x180013434`
- `0x180016c0c`
- `0x1800185c8`
- `0x18003c9cc`
- `0x18003cfa8`
- `0x18003dfd4`
- `0x180052338`

## string_xrefs

- `0x18003cc15`: `DeleteBufferFromRegistry failed = 0x%x`
- `0x18003ccd9`: `DeleteBufferFromRegistry failed = 0x%x`
- `0x18003ce46`: `DeleteBufferFromRegistry failed = 0x%x`
- `0x18003cae9`: `DeleteBufferFromRegistry (Applicationflags) failed. hr = 0x%X`
- `0x18003cb0d`: `DeleteBufferFromRegistry (Applicationflags) failed. hr = 0x%X`
- `0x18003ca47`: `IdentityStorage::DeleteIdentityData`
- `0x18003ca9c`: `IdentityStorage::DeleteIdentityData`
- `0x18003cf33`: `IdentityStorage::DeleteIdentityData`
- `0x18003cbaa`: `hr = registryHelper.WriteBufferToRegistry( nullptr, registryKey, ApplicationFlags, REG_DWORD, reinterpret_cast<BYTE*>(&applicationFlags), sizeof(applicationFlags))`
- `0x18003cddc`: `hr = registryHelper.DeleteSubkeyFromRegistry(nullptr, GetEnvironmentSpecificRegistryKey(ModernDataTokenRootKey) + applicationId)`
- `0x18003cd65`: `ReadBufferFromRegistry failed = 0x%x`
- `0x18003cf17`: `hr = registryHelper.DeleteSubkeyFromRegistry(nullptr, GetEnvironmentSpecificRegistryKey(ModernDataPropertyRootKey) + L"\\" + applicationId)`
- `0x18003ce98`: `hr = DeletePairwiseId(userId, applicationId)`
- `0x18003ca04`: `Software\Microsoft\IdentityCRL\Immersive\%s\Token\`
- `0x18003cd90`: `Software\Microsoft\IdentityCRL\Immersive\%s\Token\`

## pseudocode

```c
// Hidden C++ exception states: #wind=13
__int64 __fastcall IdentityStorage::DeleteIdentityData(
        IdentityStorage *this,
        const unsigned __int16 **a2,
        char a3,
        char a4,
        char *a5)
{
  __int64 EnvironmentSpecificRegistryKey; // rax
  char v10; // r14
  int v11; // eax
  int v12; // r9d
  const char *v13; // rax
  unsigned int v14; // r8d
  unsigned int v15; // eax
  int v16; // eax
  char *v17; // r15
  int v18; // eax
  int v19; // ecx
  int v20; // ecx
  int v21; // eax
  unsigned __int16 *v22; // rbx
  int IsAssociatedToOtherApplication; // eax
  const char *v24; // rcx
  unsigned int v25; // r8d
  __int64 v26; // rax
  const unsigned __int16 **v27; // rax
  HKEY v28; // rdx
  int v29; // edi
  const unsigned __int16 **v30; // rax
  __int64 v31; // rax
  __int64 v32; // rax
  const unsigned __int16 **v33; // rax
  HKEY v34; // rdx
  int v35; // ebx
  unsigned int v36; // ebx
  char *v38; // [rsp+20h] [rbp-71h]
  char *v39; // [rsp+20h] [rbp-71h]
  char *v40; // [rsp+20h] [rbp-71h]
  unsigned int v41; // [rsp+40h] [rbp-51h] BYREF
  __int64 v42; // [rsp+48h] [rbp-49h] BYREF
  unsigned __int16 *v43; // [rsp+50h] [rbp-41h] BYREF
  unsigned __int16 *v44; // [rsp+58h] [rbp-39h] BYREF
  unsigned __int8 *v45; // [rsp+60h] [rbp-31h] BYREF
  char v46[8]; // [rsp+68h] [rbp-29h] BYREF
  char v47[8]; // [rsp+70h] [rbp-21h] BYREF
  int *v48[4]; // [rsp+78h] [rbp-19h] BYREF
  _QWORD v49[5]; // [rsp+98h] [rbp+7h] BYREF
  int v50; // [rsp+F0h] [rbp+5Fh] BYREF
  char v51; // [rsp+100h] [rbp+6Fh] BYREF

  v50 = 0;
  v42 = *(_QWORD *)this;
  EnvironmentSpecificRegistryKey = IdentityStorage::GetEnvironmentSpecificRegistryKey(
                                     this,
                                     &v45,
                                     L"Software\\Microsoft\\IdentityCRL\\Immersive\\%s\\Token\\");
  ATL::operator+(&v43, EnvironmentSpecificRegistryKey, a2);
  ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v45);
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(&v44);
  v10 = 1;
  v51 = 1;
  v45 = 0;
  v49[0] = "IdentityStorage::DeleteIdentityData";
  v49[1] = &v50;
  v49[2] = 0;
  v49[3] = 0;
  MsaTracingInternal::TraceFunctionEnter(
    (MsaTracingInternal *)"onecoreuap\\ds\\ext\\live\\identity\\lib\\immersiveidentitystorage\\identitystorage.cpp",
    "IdentityStorage::DeleteIdentityData",
    (const char *)0x4C6,
    0,
    (const unsigned __int16 *)v38);
  ErrorVerifier::ErrorVerifier(
    (ErrorVerifier *)v48,
    "IdentityStorage::DeleteIdentityData",
    &v50,
    0xBu,
    &qword_18006F700);
  if ( a3 == 1 )
  {
    v11 = RegistryHelper::DeleteBufferFromRegistry((RegistryHelper *)&v42, 0, v43, L"ApplicationFlags");
    v50 = v11;
    if ( v11 < 0 )
    {
      if ( v11 == -2147024894 || v11 == -2147023878 )
      {
        LODWORD(v39) = v11;
        TracePrintW(
          4u,
          "onecoreuap\\ds\\ext\\live\\identity\\lib\\immersiveidentitystorage\\identitystorage.cpp",
          0x4D5u,
          L"DeleteBufferFromRegistry (Applicationflags) failed. hr = 0x%X",
          v39);
        v12 = 0;
        v50 = 0;
      }
      else
      {
        LODWORD(v39) = v11;
        TracePrintW(
          2u,
          "onecoreuap\\ds\\ext\\live\\identity\\lib\\immersiveidentitystorage\\identitystorage.cpp",
          0x4DAu,
          L"DeleteBufferFromRegistry (Applicationflags) failed. hr = 0x%X",
          v39);
        v12 = v50;
      }
      if ( v12 < 0 )
      {
        v13 = "hr";
        v14 = 1246;
LABEL_48:
        Telemetry::IfFailExit(
          "onecoreuap\\ds\\ext\\live\\identity\\lib\\immersiveidentitystorage\\identitystorage.cpp",
          "IdentityStorage::DeleteIdentityData",
          v14,
          v12,
          v13);
        goto LABEL_49;
      }
    }
  }
  else
  {
    v41 = 0;
    RegistryHelper::ReadValueFromRegistry<unsigned long>(
      (unsigned int)&v42,
      0,
      (_DWORD)v43,
      (unsigned int)L"ApplicationFlags",
      (_DWORD)v39,
      (__int64)&v41);
    if ( a4 == 1 )
      v15 = v41 | 2;
    else
      v15 = v41 & 0xFFFFFFFD;
    v41 = v15;
    v16 = RegistryHelper::WriteBufferToRegistry(
            (RegistryHelper *)&v42,
            0,
            v43,
            L"ApplicationFlags",
            4u,
            (unsigned __int8 *)&v41,
            4u);
    v50 = v16;
    if ( v16 < 0 )
    {
      Telemetry::IfFailExit(
        "onecoreuap\\ds\\ext\\live\\identity\\lib\\immersiveidentitystorage\\identitystorage.cpp",
        "IdentityStorage::DeleteIdentityData",
        0x4F7u,
        v16,
        "hr = registryHelper.WriteBufferToRegistry( nullptr, registryKey, ApplicationFlags, REG_DWORD, reinterpret_cast<B"
        "YTE*>(&applicationFlags), sizeof(applicationFlags))");
      goto LABEL_49;
    }
  }
  v17 = a5;
  *a5 = 1;
  v18 = RegistryHelper::DeleteBufferFromRegistry((RegistryHelper *)&v42, 0, v43, L"UserTicket");
  v19 = v18;
  v50 = v18;
  if ( v18 == -2147024894 || v18 == -2147023878 )
  {
    LODWORD(v39) = v18;
    TracePrintW(
      3u,
      "onecoreuap\\ds\\ext\\live\\identity\\lib\\immersiveidentitystorage\\identitystorage.cpp",
      0x4FFu,
      L"DeleteBufferFromRegistry failed = 0x%x",
      v39);
    v50 = 0;
  }
  else if ( v18 < 0 )
  {
    v13 = "hr";
    v12 = v19;
    v14 = 1283;
    goto LABEL_48;
  }
  v20 = RegistryHelper::ReadBufferFromRegistry((RegistryHelper *)&v42, 0, v43, L"UserId", 2u, &v45, &v41);
  v50 = v20;
  if ( v20 < 0 )
  {
    if ( v20 != -2147024894 && v20 != -2147023878 )
    {
      v14 = 1312;
      goto LABEL_24;
    }
    LODWORD(v40) = v20;
    TracePrintW(
      3u,
      "onecoreuap\\ds\\ext\\live\\identity\\lib\\immersiveidentitystorage\\identitystorage.cpp",
      0x51Cu,
      L"ReadBufferFromRegistry failed = 0x%x",
      v40);
    v50 = 0;
    v22 = v44;
  }
  else
  {
    ATL::CSimpleStringT<unsigned short,0>::SetString(&v44, v45);
    v21 = RegistryHelper::DeleteBufferFromRegistry((RegistryHelper *)&v42, 0, v43, L"UserId");
    v20 = v21;
    v50 = v21;
    if ( v21 == -2147024894 || v21 == -2147023878 )
    {
      LODWORD(v40) = v21;
      TracePrintW(
        3u,
        "onecoreuap\\ds\\ext\\live\\identity\\lib\\immersiveidentitystorage\\identitystorage.cpp",
        0x50Du,
        L"DeleteBufferFromRegistry failed = 0x%x",
        v40);
      v50 = 0;
    }
    else if ( v21 < 0 )
    {
      v14 = 1297;
LABEL_24:
      v12 = v20;
      v13 = "hr";
      goto LABEL_48;
    }
    v22 = v44;
    if ( *((_DWORD *)v44 - 4) )
    {
      IsAssociatedToOtherApplication = IdentityStorage::IsAssociatedToOtherApplication(this, &v44, &v51);
      v50 = IsAssociatedToOtherApplication;
      if ( IsAssociatedToOtherApplication < 0 )
      {
        v24 = "hr = IsAssociatedToOtherApplication(userId, isUserAssociatedLocal)";
        v25 = 1301;
LABEL_29:
        Telemetry::IfFailExit(
          "onecoreuap\\ds\\ext\\live\\identity\\lib\\immersiveidentitystorage\\identitystorage.cpp",
          "IdentityStorage::DeleteIdentityData",
          v25,
          IsAssociatedToOtherApplication,
          v24);
        goto LABEL_49;
      }
      v10 = v51;
    }
  }
  if ( a3 == 1 )
  {
    v26 = IdentityStorage::GetEnvironmentSpecificRegistryKey(
            this,
            v46,
            L"Software\\Microsoft\\IdentityCRL\\Immersive\\%s\\Token\\");
    v27 = (const unsigned __int16 **)ATL::operator+(&v41, v26, a2);
    v29 = RegistryHelper::DeleteSubkeyFromRegistry((RegistryHelper *)&v42, v28, *v27);
    v50 = v29;
    ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v41);
    ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(v46);
    if ( v29 < 0 )
    {
      v13 = "hr = registryHelper.DeleteSubkeyFromRegistry(nullptr, GetEnvironmentSpecificRegistryKey(ModernDataTokenRootK"
            "ey) + applicationId)";
      v12 = v29;
      v14 = 1318;
      goto LABEL_48;
    }
  }
  if ( !v10 )
  {
    v30 = (const unsigned __int16 **)IdentityStorage::GetEnvironmentSpecificRegistryKey(
                                       this,
                                       v46,
                                       L"Software\\Microsoft\\IdentityCRL\\Immersive\\%s\\Property");
    v50 = RegistryHelper::DeleteBufferFromRegistry((RegistryHelper *)&v42, 0, *v30, v22);
    ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(v46);
    v12 = v50;
    if ( v50 == -2147024894 || v50 == -2147023878 )
    {
      LODWORD(v40) = v50;
      TracePrintW(
        3u,
        "onecoreuap\\ds\\ext\\live\\identity\\lib\\immersiveidentitystorage\\identitystorage.cpp",
        0x52Fu,
        L"DeleteBufferFromRegistry failed = 0x%x",
        v40);
      v12 = 0;
      v50 = 0;
    }
    if ( v12 < 0 )
    {
      v13 = "hr";
      v14 = 1331;
      goto LABEL_48;
    }
  }
  IsAssociatedToOtherApplication = IdentityStorage::DeletePairwiseId(this, v22, *a2);
  v50 = IsAssociatedToOtherApplication;
  if ( IsAssociatedToOtherApplication < 0 )
  {
    v24 = "hr = DeletePairwiseId(userId, applicationId)";
    v25 = 1335;
    goto LABEL_29;
  }
  *v17 = v10;
  v31 = IdentityStorage::GetEnvironmentSpecificRegistryKey(
          this,
          v47,
          L"Software\\Microsoft\\IdentityCRL\\Immersive\\%s\\Property");
  v32 = ATL::operator+(&v41, v31, L"\\");
  v33 = (const unsigned __int16 **)ATL::operator+(v46, v32, a2);
  v35 = RegistryHelper::DeleteSubkeyFromRegistry((RegistryHelper *)&v42, v34, *v33);
  v50 = v35;
  ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(v46);
  ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v41);
  ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(v47);
  if ( v35 < 0 )
  {
    v13 = "hr = registryHelper.DeleteSubkeyFromRegistry(nullptr, GetEnvironmentSpecificRegistryKey(ModernDataPropertyRoot"
          "Key) + L\"\\\\\" + applicationId)";
    v12 = v35;
    v14 = 1340;
    goto LABEL_48;
  }
LABEL_49:
  v36 = v50;
  ErrorVerifier::CheckAgainstList((const char *)v48[3], *v48[2], (unsigned __int64)v48[1], v48[0]);
  CTraceFuncW<long>::~CTraceFuncW<long>(v49);
  CMIDLPtr<unsigned short *>::Clear(&v45);
  ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v44);
  ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v43);
  return v36;
}

```

## disassembly

```asm
0x18003c9cc  mov     [rsp-8+arg_8], rbx
0x18003c9d1  mov     [rsp-8+arg_18], rsi
0x18003c9d6  push    rbp
0x18003c9d7  push    rdi
0x18003c9d8  push    r12
0x18003c9da  push    r14
0x18003c9dc  push    r15
0x18003c9de  lea     rbp, [rsp-2Fh]
0x18003c9e3  sub     rsp, 0C0h
0x18003c9ea  mov     bl, r9b
0x18003c9ed  mov     dil, r8b
0x18003c9f0  mov     r12, rdx
0x18003c9f3  mov     rsi, rcx
0x18003c9f6  mov     [rbp+4Fh+arg_0], 0
0x18003c9fd  mov     rax, [rcx]
0x18003ca00  mov     [rbp+4Fh+var_98], rax
0x18003ca04  lea     r8, aSoftwareMicros_5; "Software\\Microsoft\\IdentityCRL\\Immer"...
0x18003ca0b  lea     rdx, [rbp+4Fh+var_80]
0x18003ca0f  call    ?GetEnvironmentSpecificRegistryKey@IdentityStorage@@AEAA?AV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@PEBG@Z; IdentityStorage::GetEnvironmentSpecificRegistryKey(ushort const *)
0x18003ca14  nop
0x18003ca15  mov     r8, r12
0x18003ca18  mov     rdx, rax
0x18003ca1b  lea     rcx, [rbp+4Fh+var_90]
0x18003ca1f  call    ??HATL@@YA?AV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@0@AEBV10@0@Z; ATL::operator+(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &)
0x18003ca24  nop
0x18003ca25  lea     rcx, [rbp+4Fh+var_80]; void *
0x18003ca29  call    ??1?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(void)
0x18003ca2e  lea     rcx, [rbp+4Fh+var_88]; void *
0x18003ca32  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(void)
0x18003ca37  nop
0x18003ca38  mov     r14b, 1
0x18003ca3b  mov     [rbp+4Fh+arg_10], r14b
0x18003ca3f  mov     [rbp+4Fh+var_80], 0
0x18003ca47  lea     rcx, aIdentitystorag_4; "IdentityStorage::DeleteIdentityData"
0x18003ca4e  mov     [rbp+4Fh+var_48], rcx
0x18003ca52  lea     rax, [rbp+4Fh+arg_0]
0x18003ca56  mov     [rbp+4Fh+var_40], rax
0x18003ca5a  mov     [rbp+4Fh+var_38], 0
0x18003ca62  mov     [rbp+4Fh+var_30], 0
0x18003ca6a  xor     r9d, r9d; unsigned int
0x18003ca6d  mov     r8d, 4C6h; char *
0x18003ca73  mov     rdx, rcx; char *
0x18003ca76  lea     r15, aOnecoreuapDsEx_0; "onecoreuap\\ds\\ext\\live\\identity\\li"...
0x18003ca7d  mov     rcx, r15; this
0x18003ca80  call    ?TraceFunctionEnter@MsaTracingInternal@@YAKPEBD0KPEBG@Z; MsaTracingInternal::TraceFunctionEnter(char const *,char const *,ulong,ushort const *)
0x18003ca85  nop
0x18003ca86  lea     rax, qword_18006F700
0x18003ca8d  mov     [rsp+0E0h+var_C0], rax; int *
0x18003ca92  mov     r9d, 0Bh; unsigned __int64
0x18003ca98  lea     r8, [rbp+4Fh+arg_0]; int *
0x18003ca9c  lea     rdx, aIdentitystorag_4; "IdentityStorage::DeleteIdentityData"
0x18003caa3  lea     rcx, [rbp+4Fh+var_68]; this
0x18003caa7  call    ??0ErrorVerifier@@QEAA@PEBDPEAJ_KPEBJ@Z; ErrorVerifier::ErrorVerifier(char const *,long *,unsigned __int64,long const *)
0x18003caac  nop
0x18003caad  lea     r9, aApplicationfla_0; "ApplicationFlags"
0x18003cab4  mov     r8, [rbp+4Fh+var_90]; unsigned __int16 *
0x18003cab8  xor     edx, edx; HKEY
0x18003caba  lea     rcx, [rbp+4Fh+var_98]; this
0x18003cabe  cmp     dil, r14b
0x18003cac1  jnz     loc_18003CB4C
0x18003cac7  call    ?DeleteBufferFromRegistry@RegistryHelper@@QEAAJPEAUHKEY__@@PEBG1@Z; RegistryHelper::DeleteBufferFromRegistry(HKEY__ *,ushort const *,ushort const *)
0x18003cacc  mov     [rbp+4Fh+arg_0], eax
0x18003cacf  test    eax, eax
0x18003cad1  jns     loc_18003CBC7
0x18003cad7  cmp     eax, 80070002h
0x18003cadc  jz      short loc_18003CB09
0x18003cade  cmp     eax, 800703FAh
0x18003cae3  jz      short loc_18003CB09
0x18003cae5  mov     dword ptr [rsp+0E0h+var_C0], eax
0x18003cae9  lea     r9, aDeletebufferfr; "DeleteBufferFromRegistry (Applicationfl"...
0x18003caf0  mov     r8d, 4DAh; unsigned int
0x18003caf6  mov     rdx, r15; char *
0x18003caf9  mov     ecx, 2; unsigned __int8
0x18003cafe  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x18003cb03  mov     r9d, [rbp+4Fh+arg_0]
0x18003cb07  jmp     short loc_18003CB2E
0x18003cb09  mov     dword ptr [rsp+0E0h+var_C0], eax
0x18003cb0d  lea     r9, aDeletebufferfr; "DeleteBufferFromRegistry (Applicationfl"...
0x18003cb14  mov     r8d, 4D5h; unsigned int
0x18003cb1a  mov     rdx, r15; char *
0x18003cb1d  mov     ecx, 4; unsigned __int8
0x18003cb22  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x18003cb27  xor     r9d, r9d
0x18003cb2a  mov     [rbp+4Fh+arg_0], r9d
0x18003cb2e  test    r9d, r9d
0x18003cb31  jns     loc_18003CBC7
0x18003cb37  lea     rax, aHr; "hr"
0x18003cb3e  mov     r8d, 4DEh
0x18003cb44  mov     rcx, r15
0x18003cb47  jmp     loc_18003CF2E
0x18003cb4c  mov     [rbp+4Fh+var_A0], 0
0x18003cb53  lea     rax, [rbp+4Fh+var_A0]
0x18003cb57  mov     [rsp+0E0h+var_B8], rax
0x18003cb5c  call    ??$ReadValueFromRegistry@K@RegistryHelper@@AEAAJPEAUHKEY__@@PEBG1KPEAK@Z; RegistryHelper::ReadValueFromRegistry<ulong>(HKEY__ *,ushort const *,ushort const *,ulong,ulong *)
0x18003cb61  mov     eax, [rbp+4Fh+var_A0]
0x18003cb64  cmp     bl, 1
0x18003cb67  jnz     short loc_18003CB6E
0x18003cb69  or      eax, 2
0x18003cb6c  jmp     short loc_18003CB71
0x18003cb6e  and     eax, 0FFFFFFFDh
0x18003cb71  mov     [rbp+4Fh+var_A0], eax
0x18003cb74  mov     dword ptr [rsp+0E0h+var_B0], 4; unsigned int
0x18003cb7c  lea     rax, [rbp+4Fh+var_A0]
0x18003cb80  mov     [rsp+0E0h+var_B8], rax; unsigned __int8 *
0x18003cb85  mov     dword ptr [rsp+0E0h+var_C0], 4; unsigned int
0x18003cb8d  lea     r9, aApplicationfla_0; "ApplicationFlags"
0x18003cb94  mov     r8, [rbp+4Fh+var_90]; unsigned __int16 *
0x18003cb98  xor     edx, edx; HKEY
0x18003cb9a  lea     rcx, [rbp+4Fh+var_98]; this
0x18003cb9e  call    ?WriteBufferToRegistry@RegistryHelper@@QEAAJPEAUHKEY__@@PEBG1KPEAEK@Z; RegistryHelper::WriteBufferToRegistry(HKEY__ *,ushort const *,ushort const *,ulong,uchar *,ulong)
0x18003cba3  mov     [rbp+4Fh+arg_0], eax
0x18003cba6  test    eax, eax
0x18003cba8  jns     short loc_18003CBC7
0x18003cbaa  lea     rcx, aHrRegistryhelp_12; "hr = registryHelper.WriteBufferToRegist"...
0x18003cbb1  mov     [rsp+0E0h+var_C0], rcx
0x18003cbb6  mov     r9d, eax
0x18003cbb9  mov     r8d, 4F7h
0x18003cbbf  mov     rcx, r15
0x18003cbc2  jmp     loc_18003CF33
0x18003cbc7  mov     r15, [rbp+4Fh+arg_20]
0x18003cbcb  mov     byte ptr [r15], 1
0x18003cbcf  lea     r9, aUserticket; "UserTicket"
0x18003cbd6  mov     r8, [rbp+4Fh+var_90]; unsigned __int16 *
0x18003cbda  xor     edx, edx; HKEY
0x18003cbdc  lea     rcx, [rbp+4Fh+var_98]; this
0x18003cbe0  call    ?DeleteBufferFromRegistry@RegistryHelper@@QEAAJPEAUHKEY__@@PEBG1@Z; RegistryHelper::DeleteBufferFromRegistry(HKEY__ *,ushort const *,ushort const *)
0x18003cbe5  mov     ecx, eax
0x18003cbe7  mov     [rbp+4Fh+arg_0], eax
0x18003cbea  cmp     eax, 80070002h
0x18003cbef  jz      short loc_18003CC11
0x18003cbf1  cmp     eax, 800703FAh
0x18003cbf6  jz      short loc_18003CC11
0x18003cbf8  test    eax, eax
0x18003cbfa  jns     short loc_18003CC3F
0x18003cbfc  lea     rax, aHr; "hr"
0x18003cc03  mov     r9d, ecx
0x18003cc06  mov     r8d, 503h
0x18003cc0c  jmp     loc_18003CF27
0x18003cc11  mov     dword ptr [rsp+0E0h+var_C0], ecx
0x18003cc15  lea     r9, aDeletebufferfr_0; "DeleteBufferFromRegistry failed = 0x%x"
0x18003cc1c  mov     r8d, 4FFh; unsigned int
0x18003cc22  lea     rbx, aOnecoreuapDsEx_0; "onecoreuap\\ds\\ext\\live\\identity\\li"...
0x18003cc29  mov     rdx, rbx; char *
0x18003cc2c  mov     ecx, 3; unsigned __int8
0x18003cc31  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x18003cc36  mov     [rbp+4Fh+arg_0], 0
0x18003cc3d  jmp     short loc_18003CC46
0x18003cc3f  lea     rbx, aOnecoreuapDsEx_0; "onecoreuap\\ds\\ext\\live\\identity\\li"...
0x18003cc46  lea     rax, [rbp+4Fh+var_A0]
0x18003cc4a  mov     [rsp+0E0h+var_B0], rax; unsigned int *
0x18003cc4f  lea     rax, [rbp+4Fh+var_80]
0x18003cc53  mov     [rsp+0E0h+var_B8], rax; unsigned __int8 **
0x18003cc58  mov     dword ptr [rsp+0E0h+var_C0], 2; unsigned int
0x18003cc60  lea     r9, aUserid; "UserId"
0x18003cc67  mov     r8, [rbp+4Fh+var_90]; unsigned __int16 *
0x18003cc6b  xor     edx, edx; HKEY
0x18003cc6d  lea     rcx, [rbp+4Fh+var_98]; this
0x18003cc71  call    ?ReadBufferFromRegistry@RegistryHelper@@QEAAJPEAUHKEY__@@PEBG1KPEAPEAEPEAK@Z; RegistryHelper::ReadBufferFromRegistry(HKEY__ *,ushort const *,ushort const *,ulong,uchar * *,ulong *)
0x18003cc76  mov     ecx, eax
0x18003cc78  mov     [rbp+4Fh+arg_0], eax
0x18003cc7b  test    eax, eax
0x18003cc7d  js      loc_18003CD46
0x18003cc83  mov     rdx, [rbp+4Fh+var_80]
0x18003cc87  lea     rcx, [rbp+4Fh+var_88]
0x18003cc8b  call    ?SetString@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBG@Z; ATL::CSimpleStringT<ushort,0>::SetString(ushort const *)
0x18003cc90  lea     r9, aUserid; "UserId"
0x18003cc97  mov     r8, [rbp+4Fh+var_90]; unsigned __int16 *
0x18003cc9b  xor     edx, edx; HKEY
0x18003cc9d  lea     rcx, [rbp+4Fh+var_98]; this
0x18003cca1  call    ?DeleteBufferFromRegistry@RegistryHelper@@QEAAJPEAUHKEY__@@PEBG1@Z; RegistryHelper::DeleteBufferFromRegistry(HKEY__ *,ushort const *,ushort const *)
0x18003cca6  mov     ecx, eax
0x18003cca8  mov     [rbp+4Fh+arg_0], eax
0x18003ccab  cmp     eax, 80070002h
0x18003ccb0  jz      short loc_18003CCD5
0x18003ccb2  cmp     eax, 800703FAh
0x18003ccb7  jz      short loc_18003CCD5
0x18003ccb9  test    eax, eax
0x18003ccbb  jns     short loc_18003CCFA
0x18003ccbd  mov     r8d, 511h
0x18003ccc3  mov     r9d, ecx
0x18003ccc6  lea     rax, aHr; "hr"
0x18003cccd  mov     rcx, rbx
0x18003ccd0  jmp     loc_18003CF2E
0x18003ccd5  mov     dword ptr [rsp+0E0h+var_C0], ecx
0x18003ccd9  lea     r9, aDeletebufferfr_0; "DeleteBufferFromRegistry failed = 0x%x"
0x18003cce0  mov     r8d, 50Dh; unsigned int
0x18003cce6  mov     rdx, rbx; char *
0x18003cce9  mov     ecx, 3; unsigned __int8
0x18003ccee  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x18003ccf3  mov     [rbp+4Fh+arg_0], 0
0x18003ccfa  mov     rbx, [rbp+4Fh+var_88]
0x18003ccfe  cmp     dword ptr [rbx-10h], 0
0x18003cd02  jz      loc_18003CD8A
0x18003cd08  lea     r8, [rbp+4Fh+arg_10]
0x18003cd0c  lea     rdx, [rbp+4Fh+var_88]
0x18003cd10  mov     rcx, rsi
0x18003cd13  call    ?IsAssociatedToOtherApplication@IdentityStorage@@AEAAJAEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@AEA_N@Z; IdentityStorage::IsAssociatedToOtherApplication(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,bool &)
0x18003cd18  mov     [rbp+4Fh+arg_0], eax
0x18003cd1b  test    eax, eax
0x18003cd1d  jns     short loc_18003CD40
0x18003cd1f  lea     rcx, aHrIsassociated; "hr = IsAssociatedToOtherApplication(use"...
0x18003cd26  mov     r8d, 515h
0x18003cd2c  mov     r9d, eax
0x18003cd2f  mov     [rsp+0E0h+var_C0], rcx
0x18003cd34  lea     rcx, aOnecoreuapDsEx_0; "onecoreuap\\ds\\ext\\live\\identity\\li"...
0x18003cd3b  jmp     loc_18003CF33
0x18003cd40  mov     r14b, [rbp+4Fh+arg_10]
0x18003cd44  jmp     short loc_18003CD8A
0x18003cd46  cmp     ecx, 80070002h
0x18003cd4c  jz      short loc_18003CD61
0x18003cd4e  cmp     ecx, 800703FAh
0x18003cd54  jz      short loc_18003CD61
0x18003cd56  mov     r8d, 520h
0x18003cd5c  jmp     loc_18003CCC3
0x18003cd61  mov     dword ptr [rsp+0E0h+var_C0], ecx
0x18003cd65  lea     r9, aReadbufferfrom; "ReadBufferFromRegistry failed = 0x%x"
0x18003cd6c  mov     r8d, 51Ch; unsigned int
0x18003cd72  mov     rdx, rbx; char *
0x18003cd75  mov     ecx, 3; unsigned __int8
0x18003cd7a  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x18003cd7f  mov     [rbp+4Fh+arg_0], 0
0x18003cd86  mov     rbx, [rbp+4Fh+var_88]
0x18003cd8a  cmp     dil, 1
0x18003cd8e  jnz     short loc_18003CDF1
0x18003cd90  lea     r8, aSoftwareMicros_5; "Software\\Microsoft\\IdentityCRL\\Immer"...
0x18003cd97  lea     rdx, [rbp+4Fh+var_78]
0x18003cd9b  mov     rcx, rsi
0x18003cd9e  call    ?GetEnvironmentSpecificRegistryKey@IdentityStorage@@AEAA?AV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@PEBG@Z; IdentityStorage::GetEnvironmentSpecificRegistryKey(ushort const *)
0x18003cda3  nop
0x18003cda4  mov     r8, r12
0x18003cda7  mov     rdx, rax
0x18003cdaa  lea     rcx, [rbp+4Fh+var_A0]
0x18003cdae  call    ??HATL@@YA?AV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@0@AEBV10@0@Z; ATL::operator+(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &)
0x18003cdb3  nop
0x18003cdb4  mov     r8, [rax]; unsigned __int16 *
0x18003cdb7  lea     rcx, [rbp+4Fh+var_98]; this
0x18003cdbb  call    ?DeleteSubkeyFromRegistry@RegistryHelper@@QEAAJPEAUHKEY__@@PEBG@Z; RegistryHelper::DeleteSubkeyFromRegistry(HKEY__ *,ushort const *)
0x18003cdc0  mov     edi, eax
0x18003cdc2  mov     [rbp+4Fh+arg_0], eax
0x18003cdc5  lea     rcx, [rbp+4Fh+var_A0]; void *
0x18003cdc9  call    ??1?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(void)
0x18003cdce  nop
0x18003cdcf  lea     rcx, [rbp+4Fh+var_78]; void *
0x18003cdd3  call    ??1?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(void)
0x18003cdd8  test    edi, edi
0x18003cdda  jns     short loc_18003CDF1
0x18003cddc  lea     rax, aHrRegistryhelp_13; "hr = registryHelper.DeleteSubkeyFromReg"...
0x18003cde3  mov     r9d, edi
0x18003cde6  mov     r8d, 526h
0x18003cdec  jmp     loc_18003CF27
0x18003cdf1  test    r14b, r14b
0x18003cdf4  jnz     loc_18003CE82
0x18003cdfa  lea     r8, aSoftwareMicros_4; "Software\\Microsoft\\IdentityCRL\\Immer"...
0x18003ce01  lea     rdx, [rbp+4Fh+var_78]
0x18003ce05  mov     rcx, rsi
0x18003ce08  call    ?GetEnvironmentSpecificRegistryKey@IdentityStorage@@AEAA?AV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@PEBG@Z; IdentityStorage::GetEnvironmentSpecificRegistryKey(ushort const *)
0x18003ce0d  nop
0x18003ce0e  mov     r9, rbx; unsigned __int16 *
0x18003ce11  mov     r8, [rax]; unsigned __int16 *
0x18003ce14  xor     edx, edx; HKEY
0x18003ce16  lea     rcx, [rbp+4Fh+var_98]; this
0x18003ce1a  call    ?DeleteBufferFromRegistry@RegistryHelper@@QEAAJPEAUHKEY__@@PEBG1@Z; RegistryHelper::DeleteBufferFromRegistry(HKEY__ *,ushort const *,ushort const *)
0x18003ce1f  mov     [rbp+4Fh+arg_0], eax
0x18003ce22  lea     rcx, [rbp+4Fh+var_78]; void *
0x18003ce26  call    ??1?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(void)
0x18003ce2b  mov     r9d, [rbp+4Fh+arg_0]
0x18003ce2f  cmp     r9d, 80070002h
0x18003ce36  jz      short loc_18003CE41
0x18003ce38  cmp     r9d, 800703FAh
0x18003ce3f  jnz     short loc_18003CE6B
0x18003ce41  mov     dword ptr [rsp+0E0h+var_C0], r9d
0x18003ce46  lea     r9, aDeletebufferfr_0; "DeleteBufferFromRegistry failed = 0x%x"
0x18003ce4d  mov     r8d, 52Fh; unsigned int
0x18003ce53  lea     rdx, aOnecoreuapDsEx_0; "onecoreuap\\ds\\ext\\live\\identity\\li"...
0x18003ce5a  mov     ecx, 3; unsigned __int8
0x18003ce5f  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x18003ce64  xor     r9d, r9d
0x18003ce67  mov     [rbp+4Fh+arg_0], r9d
0x18003ce6b  test    r9d, r9d
0x18003ce6e  jns     short loc_18003CE82
0x18003ce70  lea     rax, aHr; "hr"
0x18003ce77  mov     r8d, 533h
0x18003ce7d  jmp     loc_18003CF27
0x18003ce82  mov     r8, [r12]; unsigned __int16 *
0x18003ce86  mov     rdx, rbx; unsigned __int16 *
0x18003ce89  mov     rcx, rsi; this
0x18003ce8c  call    ?DeletePairwiseId@IdentityStorage@@AEAAJPEBG0@Z; IdentityStorage::DeletePairwiseId(ushort const *,ushort const *)
0x18003ce91  mov     [rbp+4Fh+arg_0], eax
0x18003ce94  test    eax, eax
0x18003ce96  jns     short loc_18003CEAA
0x18003ce98  lea     rcx, aHrDeletepairwi; "hr = DeletePairwiseId(userId, applicati"...
0x18003ce9f  mov     r8d, 537h
0x18003cea5  jmp     loc_18003CD2C
0x18003ceaa  mov     [r15], r14b
0x18003cead  lea     r8, aSoftwareMicros_4; "Software\\Microsoft\\IdentityCRL\\Immer"...
0x18003ceb4  lea     rdx, [rbp+4Fh+var_70]
0x18003ceb8  mov     rcx, rsi
0x18003cebb  call    ?GetEnvironmentSpecificRegistryKey@IdentityStorage@@AEAA?AV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@PEBG@Z; IdentityStorage::GetEnvironmentSpecificRegistryKey(ushort const *)
0x18003cec0  nop
0x18003cec1  lea     r8, asc_18006B824; "\\"
  ... truncated ...
```
