# CTokenInfo::WriteTokenBlob(ushort const *,ushort const *,ushort const *,ushort const *,ulong,ulong,_CERTSTORE_PERSISTANT_LOCATION)

- ea: `0x1800dd85c`
- end: `0x1800ddd79`
- name: `?WriteTokenBlob@CTokenInfo@@KAJPEBG000KKW4_CERTSTORE_PERSISTANT_LOCATION@@@Z`
- size: `1309`
- prototype: ``
- caller_count: `2`
- callee_count: `22`
- tags: `file_ops, service_task, broker_com_uri`

## callers

- `0x180098518`
- `0x1800dd500`

## callees

- `0x180005ee4`
- `0x18000c050`
- `0x18000ed04`
- `0x180013fb4`
- `0x1800151c4`
- `0x180017af0`
- `0x180018f80`
- `0x18001a9c0`
- `0x18001ad00`
- `0x18001cf20`
- `0x180025c68`
- `0x1800268d0`
- `0x180030120`
- `0x180050d4c`
- `0x18006558c`
- `0x1800a3b60`
- `0x1800a400c`
- `0x1800a4718`
- `0x1800a4778`
- `0x1800a6650`
- `0x1800dd340`
- `0x1800dd85c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ddc56`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ddc56`
- `ext-ms-win-msa-device-l1-1-0!MsaDevice_OverrideTokenPersistence` at `0x1800dda33`
- `ext-ms-win-msa-device-l1-1-0!MsaDevice_OverrideTokenPersistence` at `0x1800dda33`

## string_xrefs

- `0x1800dd8d9`: `onecoreuap\ds\ext\live\identity\ntservice\lib\svccommon\singleidentity.cpp`
- `0x1800dd98a`: `onecoreuap\ds\ext\live\identity\ntservice\lib\svccommon\singleidentity.cpp`
- `0x1800dd9d7`: `onecoreuap\ds\ext\live\identity\ntservice\lib\svccommon\singleidentity.cpp`
- `0x1800ddaa0`: `onecoreuap\ds\ext\live\identity\ntservice\lib\svccommon\singleidentity.cpp`
- `0x1800ddb5b`: `onecoreuap\ds\ext\live\identity\ntservice\lib\svccommon\singleidentity.cpp`
- `0x1800ddc8c`: `onecoreuap\ds\ext\live\identity\ntservice\lib\svccommon\singleidentity.cpp`
- `0x1800ddcb6`: `onecoreuap\ds\ext\live\identity\ntservice\lib\svccommon\singleidentity.cpp`
- `0x1800dd97d`: `dwTokenLen <= CRED_MAX_ATTRIBUTES * CRED_MAX_VALUE_SIZE`
- `0x1800dd8b1`: `CTokenInfo::WriteTokenBlob`
- `0x1800dda99`: `CTokenInfo::WriteTokenBlob`
- `0x1800ddb54`: `CTokenInfo::WriteTokenBlob`
- `0x1800ddc85`: `CTokenInfo::WriteTokenBlob`
- `0x1800ddcaf`: `CTokenInfo::WriteTokenBlob`
- `0x1800dd9c2`: `hr = WriteSharedToken(wstrUserName, wstrTargetName, wstrTokenBlob, wstrKeyword, dwType, eStoreLocation)`
- `0x1800ddc9a`: `hr = StringCchCopyW( pKeyword, dwKeyword, (LPCWSTR)wstrSampleKeyword)`

## pseudocode

```c
// Hidden C++ exception states: #wind=9
__int64 __fastcall CTokenInfo::WriteTokenBlob(
        WCHAR *a1,
        WCHAR *a2,
        __int64 a3,
        _WORD *a4,
        __int64 a5,
        __int64 a6,
        int a7)
{
  unsigned __int16 *v11; // rdi
  unsigned int v12; // r14d
  int v13; // r9d
  const char *v14; // rax
  unsigned int v15; // r8d
  int v16; // eax
  DWORD v17; // esi
  void *v18; // rbx
  unsigned int v19; // edx
  unsigned __int16 *v20; // rcx
  void *v21; // rcx
  __int64 *v22; // rax
  __int64 v23; // rax
  unsigned __int16 *v24; // r10
  _DWORD *v25; // rax
  unsigned int v26; // r15d
  __int64 v27; // r13
  int v28; // ecx
  int v29; // eax
  __int64 v30; // r10
  __int64 v31; // r11
  signed int LastError; // eax
  unsigned int v33; // ebx
  char *v35; // [rsp+20h] [rbp-E0h]
  int v36; // [rsp+30h] [rbp-D0h] BYREF
  unsigned __int16 *v37; // [rsp+38h] [rbp-C8h] BYREF
  void *v38; // [rsp+40h] [rbp-C0h] BYREF
  char *v39; // [rsp+48h] [rbp-B8h] BYREF
  unsigned __int16 *v40; // [rsp+50h] [rbp-B0h] BYREF
  unsigned __int64 v41; // [rsp+58h] [rbp-A8h]
  __int64 v42; // [rsp+60h] [rbp-A0h]
  unsigned __int16 *v43; // [rsp+68h] [rbp-98h] BYREF
  WCHAR *v44; // [rsp+70h] [rbp-90h] BYREF
  __int64 v45; // [rsp+78h] [rbp-88h] BYREF
  _QWORD v46[4]; // [rsp+80h] [rbp-80h] BYREF
  struct _CREDENTIALW Credential; // [rsp+A0h] [rbp-60h] BYREF
  void *Block; // [rsp+F0h] [rbp-10h] BYREF
  _BYTE v49[136]; // [rsp+F8h] [rbp-8h] BYREF

  v11 = 0;
  v36 = 0;
  ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v45);
  ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v44);
  v46[0] = "CTokenInfo::WriteTokenBlob";
  v46[1] = &v36;
  v46[2] = 0;
  v46[3] = 0;
  MsaTracingInternal::TraceFunctionEnter(
    (MsaTracingInternal *)"onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\singleidentity.cpp",
    "CTokenInfo::WriteTokenBlob",
    (const char *)0x1174,
    0,
    (const unsigned __int16 *)v35);
  if ( !a1 || !*a1 )
  {
    v13 = -2147188701;
    v14 = "wstrUserName != nullptr && *wstrUserName != L'\\0'";
    v15 = 4470;
    goto LABEL_41;
  }
  if ( !a2 || !*a2 )
  {
    v13 = -2147186545;
    v14 = "wstrTargetName != nullptr && *wstrTargetName != L'\\0'";
    v15 = 4471;
    goto LABEL_41;
  }
  if ( !a4 || !*a4 )
  {
    v13 = -2147024809;
    v14 = "wstrKeyword != nullptr && *wstrKeyword != L'\\0'";
    v15 = 4473;
    goto LABEL_41;
  }
  Block = v49;
  ATL::CW2AEX<128>::Init(&Block, a3, 65001);
  ATL::CSimpleStringT<char,0>::SetString(&v45, Block);
  if ( Block != v49 )
    free(Block);
  v42 = v45;
  v12 = *(_DWORD *)(v45 - 16);
  if ( v12 > 0x4000 )
  {
    v13 = -2147186554;
    v14 = "dwTokenLen <= CRED_MAX_ATTRIBUTES * CRED_MAX_VALUE_SIZE";
    v15 = 4481;
LABEL_41:
    v36 = v13;
    Telemetry::IfFailExit(
      "onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\singleidentity.cpp",
      "CTokenInfo::WriteTokenBlob",
      v15,
      v13,
      v14);
    goto LABEL_42;
  }
  if ( a7 == 1 )
  {
    v17 = 0;
    memset_0(&Credential, 0, sizeof(Credential));
    v18 = 0;
    v38 = 0;
    v43 = 0;
    if ( v12 )
      v17 = (v12 + 255) >> 8;
    Credential.Type = 1;
    Credential.TargetName = a2;
    Credential.Persist = 2;
    Credential.UserName = a1;
    if ( (unsigned __int8)IsMsaDevice_FreeDeviceAuthXTokenPresent() )
      MsaDevice_OverrideTokenPersistence(&Credential.Persist);
    if ( v17 )
    {
      ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v37);
      ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::Format(
        &v44,
        L"%s%-d",
        a4,
        v12);
      Credential.Comment = v44;
      if ( !(unsigned __int8)ATL::CAutoVectorPtr<_CREDENTIAL_ATTRIBUTEW>::Allocate(&v38, v17) )
      {
        v36 = -2147024882;
        Telemetry::IfFailExit(
          "onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\singleidentity.cpp",
          "CTokenInfo::WriteTokenBlob",
          0x11B9u,
          -2147024882,
          "pAttri.Allocate(dwAttris)");
        ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v37);
        v20 = 0;
LABEL_21:
        operator delete(v20);
        v21 = v38;
LABEL_22:
        operator delete(v21);
        goto LABEL_42;
      }
      v22 = ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
              (__int64 *)&v39,
              a4);
      v23 = ATL::operator+(&v40, v22, L"000");
      ATL::CSimpleStringT<unsigned short,0>::operator=(&v37, v23);
      ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v40);
      ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v39);
      LODWORD(v41) = *((_DWORD *)v37 - 4);
      if ( !(unsigned __int8)ATL::CAutoVectorPtr<unsigned short>::Allocate(&v43, v17 * (unsigned int)v41) )
      {
        v36 = -2147024882;
        Telemetry::IfFailExit(
          "onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\singleidentity.cpp",
          "CTokenInfo::WriteTokenBlob",
          0x11BEu,
          -2147024882,
          "pAttriKeywords.Allocate(dwAttris * dwKeyword)");
        ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v37);
        v20 = v43;
        goto LABEL_21;
      }
      v11 = v43;
      v24 = v43;
      v40 = v43;
      Credential.AttributeCount = v17;
      v18 = v38;
      Credential.Attributes = (PCREDENTIAL_ATTRIBUTEW)v38;
      v25 = v38;
      v39 = (char *)v38;
      v26 = 0;
      v27 = v42;
      while ( 1 )
      {
        v25[2] = 0;
        *((_QWORD *)v25 + 2) = v27;
        v28 = v12;
        if ( v12 >= 0x100 )
          v28 = 256;
        LODWORD(v42) = v28;
        v25[3] = v28;
        *(_QWORD *)v25 = v24;
        ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::Format(
          &v37,
          L"%s%-d",
          a4,
          v26);
        v29 = StringCchCopyW(v40, (unsigned int)v41, v37);
        v36 = v29;
        if ( v29 < 0 )
          break;
        v12 -= v42;
        v25 = v39 + 24;
        v39 += 24;
        v27 += 256;
        v24 = (unsigned __int16 *)(v30 + 2 * v31);
        v40 = v24;
        if ( ++v26 >= v17 )
        {
          ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v37);
          goto LABEL_31;
        }
      }
      Telemetry::IfFailExit(
        "onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\singleidentity.cpp",
        "CTokenInfo::WriteTokenBlob",
        0x11D3u,
        v29,
        "hr = StringCchCopyW( pKeyword, dwKeyword, (LPCWSTR)wstrSampleKeyword)");
      ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v37);
    }
    else
    {
LABEL_31:
      if ( !(unsigned int)CredmanUtility::CredWriteW(&Credential, v19) )
      {
        LastError = GetLastError();
        if ( LastError > 0 )
          LastError = (unsigned __int16)LastError | 0x80070000;
        v36 = LastError;
        if ( LastError < 0 )
          Telemetry::IfFailExit(
            "onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\singleidentity.cpp",
            "CTokenInfo::WriteTokenBlob",
            0x11DBu,
            LastError,
            "hr = HRESULT_FROM_WIN32(GetLastError())");
      }
    }
    operator delete(v11);
    v21 = v18;
    goto LABEL_22;
  }
  v16 = CTokenInfo::WriteSharedToken(a1, a2, a3, a4);
  v36 = v16;
  if ( v16 < 0 )
    Telemetry::IfFailExit(
      "onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\singleidentity.cpp",
      "CTokenInfo::WriteTokenBlob",
      0x118Eu,
      v16,
      "hr = WriteSharedToken(wstrUserName, wstrTargetName, wstrTokenBlob, wstrKeyword, dwType, eStoreLocation)");
LABEL_42:
  v33 = v36;
  CTraceFuncW<long>::~CTraceFuncW<long>((__int64)v46);
  ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v44);
  ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v45);
  return v33;
}

```

## disassembly

```asm
0x1800dd85c  push    rbp
0x1800dd85e  push    rbx
0x1800dd85f  push    rsi
0x1800dd860  push    rdi
0x1800dd861  push    r12
0x1800dd863  push    r13
0x1800dd865  push    r14
0x1800dd867  push    r15
0x1800dd869  lea     rbp, [rsp-98h]
0x1800dd871  sub     rsp, 198h
0x1800dd878  mov     rax, cs:__security_cookie
0x1800dd87f  xor     rax, rsp
0x1800dd882  mov     [rbp+0D0h+var_50], rax
0x1800dd889  mov     r12, r9
0x1800dd88c  mov     rbx, r8
0x1800dd88f  mov     r15, rdx
0x1800dd892  mov     r13, rcx
0x1800dd895  xor     edi, edi
0x1800dd897  mov     [rsp+1D0h+var_1A0], edi
0x1800dd89b  lea     rcx, [rsp+1D0h+var_158]
0x1800dd8a0  call    ??0?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(void)
0x1800dd8a5  nop
0x1800dd8a6  lea     rcx, [rsp+1D0h+var_160]
0x1800dd8ab  call    ??0?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(void)
0x1800dd8b0  nop
0x1800dd8b1  lea     rsi, aCtokeninfoWrit; "CTokenInfo::WriteTokenBlob"
0x1800dd8b8  mov     [rbp+0D0h+var_150], rsi
0x1800dd8bc  lea     rax, [rsp+1D0h+var_1A0]
0x1800dd8c1  mov     [rbp+0D0h+var_148], rax
0x1800dd8c5  mov     [rbp+0D0h+var_140], rdi
0x1800dd8c9  mov     [rbp+0D0h+var_138], rdi
0x1800dd8cd  xor     r9d, r9d; unsigned int
0x1800dd8d0  mov     r8d, 1174h; char *
0x1800dd8d6  mov     rdx, rsi; char *
0x1800dd8d9  lea     r14, aOnecoreuapDsEx_24; "onecoreuap\\ds\\ext\\live\\identity\\nt"...
0x1800dd8e0  mov     rcx, r14; this
0x1800dd8e3  call    ?TraceFunctionEnter@MsaTracingInternal@@YAKPEBD0KPEBG@Z; MsaTracingInternal::TraceFunctionEnter(char const *,char const *,ulong,ushort const *)
0x1800dd8e8  nop
0x1800dd8e9  test    r13, r13
0x1800dd8ec  jz      loc_1800DDD09
0x1800dd8f2  cmp     [r13+0], di
0x1800dd8f7  jz      loc_1800DDD09
0x1800dd8fd  test    r15, r15
0x1800dd900  jz      loc_1800DDCF4
0x1800dd906  cmp     [r15], di
0x1800dd90a  jz      loc_1800DDCF4
0x1800dd910  test    r12, r12
0x1800dd913  jz      loc_1800DDCDF
0x1800dd919  cmp     [r12], di
0x1800dd91e  jz      loc_1800DDCDF
0x1800dd924  lea     rax, [rbp+0D0h+var_D8]
0x1800dd928  mov     [rbp+0D0h+Block], rax
0x1800dd92c  mov     r8d, 0FDE9h
0x1800dd932  mov     rdx, rbx
0x1800dd935  lea     rcx, [rbp+0D0h+Block]
0x1800dd939  call    ?Init@?$CW2AEX@$0IA@@ATL@@AEAAXPEBGI@Z; ATL::CW2AEX<128>::Init(ushort const *,uint)
0x1800dd93e  nop
0x1800dd93f  mov     rdx, [rbp+0D0h+Block]
0x1800dd943  lea     rcx, [rsp+1D0h+var_158]
0x1800dd948  call    ?SetString@?$CSimpleStringT@D$0A@@ATL@@QEAAXPEBD@Z; ATL::CSimpleStringT<char,0>::SetString(char const *)
0x1800dd94d  nop
0x1800dd94e  mov     rcx, [rbp+0D0h+Block]; Block
0x1800dd952  lea     rax, [rbp+0D0h+var_D8]
0x1800dd956  cmp     rcx, rax
0x1800dd959  jz      short loc_1800DD960
0x1800dd95b  call    free
0x1800dd960  mov     rax, [rsp+1D0h+var_158]
0x1800dd965  mov     [rsp+1D0h+var_170], rax
0x1800dd96a  mov     r14d, [rax-10h]
0x1800dd96e  cmp     r14d, 4000h
0x1800dd975  jbe     short loc_1800DD996
0x1800dd977  mov     r9d, 80048886h
0x1800dd97d  lea     rax, aDwtokenlenCred; "dwTokenLen <= CRED_MAX_ATTRIBUTES * CRE"...
0x1800dd984  mov     r8d, 1181h
0x1800dd98a  lea     rcx, aOnecoreuapDsEx_24; "onecoreuap\\ds\\ext\\live\\identity\\nt"...
0x1800dd991  jmp     loc_1800DDD1F
0x1800dd996  mov     eax, [rbp+0D0h+arg_30]
0x1800dd99c  cmp     eax, 1
0x1800dd99f  jz      short loc_1800DD9E3
0x1800dd9a1  mov     [rsp+1D0h+var_1A8], eax
0x1800dd9a5  mov     r9, r12
0x1800dd9a8  mov     r8, rbx
0x1800dd9ab  mov     rdx, r15
0x1800dd9ae  mov     rcx, r13
0x1800dd9b1  call    ?WriteSharedToken@CTokenInfo@@KAJPEBG000KW4_CERTSTORE_PERSISTANT_LOCATION@@@Z; CTokenInfo::WriteSharedToken(ushort const *,ushort const *,ushort const *,ushort const *,ulong,_CERTSTORE_PERSISTANT_LOCATION)
0x1800dd9b6  mov     [rsp+1D0h+var_1A0], eax
0x1800dd9ba  test    eax, eax
0x1800dd9bc  jns     loc_1800DDD31
0x1800dd9c2  lea     rcx, aHrWritesharedt; "hr = WriteSharedToken(wstrUserName, wst"...
0x1800dd9c9  mov     [rsp+1D0h+var_1B0], rcx
0x1800dd9ce  mov     r9d, eax
0x1800dd9d1  mov     r8d, 118Eh
0x1800dd9d7  lea     rcx, aOnecoreuapDsEx_24; "onecoreuap\\ds\\ext\\live\\identity\\nt"...
0x1800dd9de  jmp     loc_1800DDD29
0x1800dd9e3  mov     esi, edi
0x1800dd9e5  xor     edx, edx; Val
0x1800dd9e7  lea     r8d, [rdx+50h]; Size
0x1800dd9eb  lea     rcx, [rbp+0D0h+Credential]; void *
0x1800dd9ef  call    memset_0
0x1800dd9f4  mov     rbx, rdi
0x1800dd9f7  mov     [rsp+1D0h+var_190], rbx
0x1800dd9fc  mov     [rsp+1D0h+var_168], rdi
0x1800dda01  test    r14d, r14d
0x1800dda04  jz      short loc_1800DDA10
0x1800dda06  lea     esi, [r14+0FFh]
0x1800dda0d  shr     esi, 8
0x1800dda10  mov     [rbp+0D0h+Credential.Type], 1
0x1800dda17  mov     [rbp+0D0h+Credential.TargetName], r15
0x1800dda1b  mov     [rbp+0D0h+Credential.Persist], 2
0x1800dda22  mov     [rbp+0D0h+Credential.UserName], r13
0x1800dda26  call    IsMsaDevice_FreeDeviceAuthXTokenPresent
0x1800dda2b  test    al, al
0x1800dda2d  jz      short loc_1800DDA39
0x1800dda2f  lea     rcx, [rbp+0D0h+Credential.Persist]
0x1800dda33  call    cs:__imp_MsaDevice_OverrideTokenPersistence
0x1800dda39  test    esi, esi
0x1800dda3b  jz      loc_1800DDC49
0x1800dda41  lea     rcx, [rsp+1D0h+var_198]
0x1800dda46  call    ??0?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(void)
0x1800dda4b  nop
0x1800dda4c  mov     r9d, r14d
0x1800dda4f  mov     r8, r12
0x1800dda52  lea     rdx, aSD_0; "%s%-d"
0x1800dda59  lea     rcx, [rsp+1D0h+var_160]
0x1800dda5e  call    ?Format@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAXPEBGZZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::Format(ushort const *,...)
0x1800dda63  mov     rax, [rsp+1D0h+var_160]
0x1800dda68  mov     [rbp+0D0h+Credential.Comment], rax
0x1800dda6c  mov     edx, esi
0x1800dda6e  lea     rcx, [rsp+1D0h+var_190]
0x1800dda73  call    ?Allocate@?$CAutoVectorPtr@U_CREDENTIAL_ATTRIBUTEW@@@ATL@@QEAA_N_K@Z; ATL::CAutoVectorPtr<_CREDENTIAL_ATTRIBUTEW>::Allocate(unsigned __int64)
0x1800dda78  test    al, al
0x1800dda7a  jnz     short loc_1800DDACF
0x1800dda7c  mov     r9d, 8007000Eh; int
0x1800dda82  mov     [rsp+1D0h+var_1A0], r9d
0x1800dda87  lea     rax, aPattriAllocate_0; "pAttri.Allocate(dwAttris)"
0x1800dda8e  mov     [rsp+1D0h+var_1B0], rax; char *
0x1800dda93  mov     r8d, 11B9h; unsigned int
0x1800dda99  lea     rdx, aCtokeninfoWrit; "CTokenInfo::WriteTokenBlob"
0x1800ddaa0  lea     rcx, aOnecoreuapDsEx_24; "onecoreuap\\ds\\ext\\live\\identity\\nt"...
0x1800ddaa7  call    ?IfFailExit@Telemetry@@SAXPEBD0KJ0@Z; Telemetry::IfFailExit(char const *,char const *,ulong,long,char const *)
0x1800ddaac  nop
0x1800ddaad  lea     rcx, [rsp+1D0h+var_198]
0x1800ddab2  call    ??1?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(void)
0x1800ddab7  nop
0x1800ddab8  xor     ecx, ecx; Block
0x1800ddaba  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800ddabf  nop
0x1800ddac0  mov     rcx, [rsp+1D0h+var_190]; Block
0x1800ddac5  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800ddaca  jmp     loc_1800DDD31
0x1800ddacf  mov     rdx, r12
0x1800ddad2  lea     rcx, [rsp+1D0h+var_188]
0x1800ddad7  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ushort const *)
0x1800ddadc  nop
0x1800ddadd  lea     r8, a000; "000"
0x1800ddae4  mov     rdx, rax
0x1800ddae7  lea     rcx, [rsp+1D0h+var_180]
0x1800ddaec  call    ??HATL@@YA?AV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@0@AEBV10@PEBG@Z; ATL::operator+(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,ushort const *)
0x1800ddaf1  nop
0x1800ddaf2  mov     rdx, rax
0x1800ddaf5  lea     rcx, [rsp+1D0h+var_198]
0x1800ddafa  call    ??4?$CSimpleStringT@G$0A@@ATL@@QEAAAEAV01@AEBV01@@Z; ATL::CSimpleStringT<ushort,0>::operator=(ATL::CSimpleStringT<ushort,0> const &)
0x1800ddaff  nop
0x1800ddb00  lea     rcx, [rsp+1D0h+var_180]
0x1800ddb05  call    ??1?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(void)
0x1800ddb0a  nop
0x1800ddb0b  lea     rcx, [rsp+1D0h+var_188]
0x1800ddb10  call    ??1?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(void)
0x1800ddb15  mov     rax, [rsp+1D0h+var_198]
0x1800ddb1a  mov     r13d, [rax-10h]
0x1800ddb1e  mov     dword ptr [rsp+1D0h+var_178], r13d
0x1800ddb23  mov     edx, r13d
0x1800ddb26  imul    edx, esi
0x1800ddb29  lea     rcx, [rsp+1D0h+var_168]
0x1800ddb2e  call    ?Allocate@?$CAutoVectorPtr@G@ATL@@QEAA_N_K@Z; ATL::CAutoVectorPtr<ushort>::Allocate(unsigned __int64)
0x1800ddb33  test    al, al
0x1800ddb35  jnz     short loc_1800DDB7D
0x1800ddb37  mov     r9d, 8007000Eh; int
0x1800ddb3d  mov     [rsp+1D0h+var_1A0], r9d
0x1800ddb42  lea     rax, aPattrikeywords_0; "pAttriKeywords.Allocate(dwAttris * dwKe"...
0x1800ddb49  mov     [rsp+1D0h+var_1B0], rax; char *
0x1800ddb4e  mov     r8d, 11BEh; unsigned int
0x1800ddb54  lea     rdx, aCtokeninfoWrit; "CTokenInfo::WriteTokenBlob"
0x1800ddb5b  lea     rcx, aOnecoreuapDsEx_24; "onecoreuap\\ds\\ext\\live\\identity\\nt"...
0x1800ddb62  call    ?IfFailExit@Telemetry@@SAXPEBD0KJ0@Z; Telemetry::IfFailExit(char const *,char const *,ulong,long,char const *)
0x1800ddb67  nop
0x1800ddb68  lea     rcx, [rsp+1D0h+var_198]
0x1800ddb6d  call    ??1?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(void)
0x1800ddb72  nop
0x1800ddb73  mov     rcx, [rsp+1D0h+var_168]
0x1800ddb78  jmp     loc_1800DDABA
0x1800ddb7d  mov     rdi, [rsp+1D0h+var_168]
0x1800ddb82  mov     r10, rdi
0x1800ddb85  mov     [rsp+1D0h+var_180], rdi
0x1800ddb8a  mov     [rbp+0D0h+Credential.AttributeCount], esi
0x1800ddb8d  mov     rbx, [rsp+1D0h+var_190]
0x1800ddb92  mov     [rbp+0D0h+Credential.Attributes], rbx
0x1800ddb96  mov     rax, rbx
0x1800ddb99  mov     [rsp+1D0h+var_188], rbx
0x1800ddb9e  xor     r15d, r15d
0x1800ddba1  test    esi, esi
0x1800ddba3  jz      loc_1800DDC3F
0x1800ddba9  mov     edx, 100h
0x1800ddbae  mov     r13, [rsp+1D0h+var_170]
0x1800ddbb3  mov     dword ptr [rax+8], 0
0x1800ddbba  mov     [rax+10h], r13
0x1800ddbbe  mov     ecx, r14d
0x1800ddbc1  cmp     r14d, edx
0x1800ddbc4  cmovnb  ecx, edx
0x1800ddbc7  mov     dword ptr [rsp+1D0h+var_170], ecx
0x1800ddbcb  mov     [rax+0Ch], ecx
0x1800ddbce  mov     [rax], r10
0x1800ddbd1  mov     r9d, r15d
0x1800ddbd4  mov     r8, r12
0x1800ddbd7  lea     rdx, aSD_0; "%s%-d"
0x1800ddbde  lea     rcx, [rsp+1D0h+var_198]
0x1800ddbe3  call    ?Format@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAXPEBGZZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::Format(ushort const *,...)
0x1800ddbe8  mov     r8, [rsp+1D0h+var_198]; unsigned __int16 *
0x1800ddbed  mov     eax, dword ptr [rsp+1D0h+var_178]
0x1800ddbf1  mov     r11d, eax
0x1800ddbf4  mov     edx, eax; unsigned __int64
0x1800ddbf6  mov     r10, [rsp+1D0h+var_180]
0x1800ddbfb  mov     rcx, r10; unsigned __int16 *
0x1800ddbfe  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800ddc03  mov     [rsp+1D0h+var_1A0], eax
0x1800ddc07  test    eax, eax
0x1800ddc09  js      loc_1800DDC9A
0x1800ddc0f  sub     r14d, dword ptr [rsp+1D0h+var_170]
0x1800ddc14  mov     rax, [rsp+1D0h+var_188]
0x1800ddc19  add     rax, 18h
0x1800ddc1d  mov     [rsp+1D0h+var_188], rax
0x1800ddc22  mov     edx, 100h
0x1800ddc27  add     r13, rdx
0x1800ddc2a  lea     r10, [r10+r11*2]
0x1800ddc2e  mov     [rsp+1D0h+var_180], r10
0x1800ddc33  inc     r15d
0x1800ddc36  cmp     r15d, esi
0x1800ddc39  jb      loc_1800DDBB3
0x1800ddc3f  lea     rcx, [rsp+1D0h+var_198]
0x1800ddc44  call    ??1?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(void)
0x1800ddc49  lea     rcx, [rbp+0D0h+Credential]; Credential
0x1800ddc4d  call    ?CredWriteW@CredmanUtility@@SAHPEAU_CREDENTIALW@@K@Z; CredmanUtility::CredWriteW(_CREDENTIALW *,ulong)
0x1800ddc52  test    eax, eax
0x1800ddc54  jnz     short loc_1800DDCCE
0x1800ddc56  call    cs:__imp_GetLastError
0x1800ddc5c  test    eax, eax
0x1800ddc5e  jle     short loc_1800DDC68
0x1800ddc60  movzx   eax, ax
0x1800ddc63  or      eax, 80070000h
0x1800ddc68  mov     [rsp+1D0h+var_1A0], eax
0x1800ddc6c  test    eax, eax
0x1800ddc6e  jns     short loc_1800DDCCE
0x1800ddc70  lea     rcx, aHrHresultFromW_10; "hr = HRESULT_FROM_WIN32(GetLastError())"
0x1800ddc77  mov     [rsp+1D0h+var_1B0], rcx; char *
0x1800ddc7c  mov     r9d, eax; int
0x1800ddc7f  mov     r8d, 11DBh; unsigned int
0x1800ddc85  lea     rdx, aCtokeninfoWrit; "CTokenInfo::WriteTokenBlob"
0x1800ddc8c  lea     rcx, aOnecoreuapDsEx_24; "onecoreuap\\ds\\ext\\live\\identity\\nt"...
0x1800ddc93  call    ?IfFailExit@Telemetry@@SAXPEBD0KJ0@Z; Telemetry::IfFailExit(char const *,char const *,ulong,long,char const *)
0x1800ddc98  jmp     short loc_1800DDCCE
0x1800ddc9a  lea     rcx, aHrStringcchcop_23; "hr = StringCchCopyW( pKeyword, dwKeywor"...
0x1800ddca1  mov     [rsp+1D0h+var_1B0], rcx; char *
0x1800ddca6  mov     r9d, eax; int
0x1800ddca9  mov     r8d, 11D3h; unsigned int
0x1800ddcaf  lea     rdx, aCtokeninfoWrit; "CTokenInfo::WriteTokenBlob"
0x1800ddcb6  lea     rcx, aOnecoreuapDsEx_24; "onecoreuap\\ds\\ext\\live\\identity\\nt"...
0x1800ddcbd  call    ?IfFailExit@Telemetry@@SAXPEBD0KJ0@Z; Telemetry::IfFailExit(char const *,char const *,ulong,long,char const *)
0x1800ddcc2  nop
0x1800ddcc3  lea     rcx, [rsp+1D0h+var_198]
0x1800ddcc8  call    ??1?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(void)
0x1800ddccd  nop
0x1800ddcce  mov     rcx, rdi; Block
0x1800ddcd1  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800ddcd6  nop
0x1800ddcd7  mov     rcx, rbx
0x1800ddcda  jmp     loc_1800DDAC5
0x1800ddcdf  mov     r9d, 80070057h
0x1800ddce5  lea     rax, aWstrkeywordNul; "wstrKeyword != nullptr && *wstrKeyword "...
0x1800ddcec  mov     r8d, 1179h
0x1800ddcf2  jmp     short loc_1800DDD1C
0x1800ddcf4  mov     r9d, 8004888Fh
0x1800ddcfa  lea     rax, aWstrtargetname; "wstrTargetName != nullptr && *wstrTarge"...
0x1800ddd01  mov     r8d, 1177h
0x1800ddd07  jmp     short loc_1800DDD1C
0x1800ddd09  mov     r9d, 80048023h; int
0x1800ddd0f  lea     rax, aWstrusernameNu; "wstrUserName != nullptr && *wstrUserNam"...
0x1800ddd16  mov     r8d, 1176h; unsigned int
0x1800ddd1c  mov     rcx, r14; char *
0x1800ddd1f  mov     [rsp+1D0h+var_1B0], rax; char *
0x1800ddd24  mov     [rsp+1D0h+var_1A0], r9d
0x1800ddd29  mov     rdx, rsi; char *
0x1800ddd2c  call    ?IfFailExit@Telemetry@@SAXPEBD0KJ0@Z; Telemetry::IfFailExit(char const *,char const *,ulong,long,char const *)
0x1800ddd31  mov     ebx, [rsp+1D0h+var_1A0]
0x1800ddd35  lea     rcx, [rbp+0D0h+var_150]
0x1800ddd39  call    ??1?$CTraceFuncW@J@@QEAA@XZ; CTraceFuncW<long>::~CTraceFuncW<long>(void)
0x1800ddd3e  nop
0x1800ddd3f  lea     rcx, [rsp+1D0h+var_160]
0x1800ddd44  call    ??1?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(void)
0x1800ddd49  nop
0x1800ddd4a  lea     rcx, [rsp+1D0h+var_158]
  ... truncated ...
```
