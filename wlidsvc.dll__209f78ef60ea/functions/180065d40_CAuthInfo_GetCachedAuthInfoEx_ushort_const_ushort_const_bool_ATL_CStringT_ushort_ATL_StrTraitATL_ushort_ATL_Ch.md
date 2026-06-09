# CAuthInfo::GetCachedAuthInfoEx(ushort const *,ushort const *,bool,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> &,CAutoZeroMemoryStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> &,CAutoZeroMemoryStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> &,bool &)

- ea: `0x180065d40`
- end: `0x18006618c`
- name: `?GetCachedAuthInfoEx@CAuthInfo@@SAJPEBG0_NAEAV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@AEAV?$CAutoZeroMemoryStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@@3AEA_N@Z`
- size: `1100`
- prototype: `__int64 __usercall@<rax>(void *Src@<rcx>, __int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `26`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180065c0c`

## callees

- `0x18000c050`
- `0x18000ed04`
- `0x180013488`
- `0x18001353c`
- `0x1800151c4`
- `0x180015860`
- `0x180019690`
- `0x180019780`
- `0x18001a530`
- `0x18001a9c0`
- `0x18001b3b0`
- `0x18001bbb4`
- `0x18001bd78`
- `0x180021b28`
- `0x180021bbc`
- `0x180029d54`
- `0x18002eed0`
- `0x1800396e8`
- `0x18003a398`
- `0x18004d988`
- `0x180065110`
- `0x180065d40`
- `0x180079554`
- `0x1800d5fac`
- `0x180108734`
- `0x180116c1c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180065e8a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180065e9e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180065eb4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180065e8a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180065e9e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180065eb4`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x180065f2f`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x180065f2f`

## string_xrefs

- `0x180065de0`: `onecoreuap\ds\ext\live\identity\ntservice\lib\svccommon\singleidentity.cpp`
- `0x180065f0b`: `onecoreuap\ds\ext\live\identity\ntservice\lib\svccommon\singleidentity.cpp`
- `0x180065fbf`: `onecoreuap\ds\ext\live\identity\ntservice\lib\svccommon\singleidentity.cpp`
- `0x18006601e`: `onecoreuap\ds\ext\live\identity\ntservice\lib\svccommon\singleidentity.cpp`
- `0x180066087`: `onecoreuap\ds\ext\live\identity\ntservice\lib\svccommon\singleidentity.cpp`
- `0x1800660fd`: `onecoreuap\ds\ext\live\identity\ntservice\lib\svccommon\singleidentity.cpp`
- `0x180065dc7`: `CAuthInfo::GetCachedAuthInfoEx`
- `0x180066017`: `CAuthInfo::GetCachedAuthInfoEx`
- `0x1800660e3`: `CAuthInfo::GetCachedAuthInfoEx`
- `0x180066002`: `hr = CTokenInfo::AssembleTokenBlob(pTheCred, PPCRL_CRED_AUTHSTATE_KEYWORD, wstrAuthInfoBlob)`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
__int64 __fastcall CAuthInfo::GetCachedAuthInfoEx(
        _WORD *Src,
        __int64 a2,
        char a3,
        __int64 a4,
        __int64 a5,
        _QWORD *a6,
        _BYTE *a7)
{
  unsigned __int8 v11; // dl
  PPTraceStatus *v12; // rcx
  bool v13; // zf
  char v14; // cl
  char v15; // al
  const unsigned __int16 *String; // rax
  _QWORD *v17; // r14
  unsigned int v18; // r8d
  _BYTE *v19; // r15
  unsigned int v20; // edx
  signed int LastError; // eax
  struct _CREDENTIALW **v22; // rbx
  int v23; // edi
  struct _CREDENTIALW *v24; // rbx
  int v25; // eax
  int v26; // eax
  __int64 v27; // r8
  const char *v28; // rdx
  int v29; // edx
  int v30; // ecx
  const wchar_t *Comment; // rcx
  const char *v32; // rcx
  unsigned int v33; // ebx
  char *v35; // [rsp+20h] [rbp-E0h]
  char *v36; // [rsp+20h] [rbp-E0h]
  LPCWSTR Filter; // [rsp+40h] [rbp-C0h] BYREF
  void **v38; // [rsp+48h] [rbp-B8h] BYREF
  struct _CREDENTIALW **v39[2]; // [rsp+50h] [rbp-B0h] BYREF
  void **v40; // [rsp+60h] [rbp-A0h] BYREF
  _WORD *CredentialBlob; // [rsp+68h] [rbp-98h]
  __int64 v42; // [rsp+70h] [rbp-90h]
  char v43; // [rsp+78h] [rbp-88h]
  const char *v44[4]; // [rsp+80h] [rbp-80h] BYREF
  _BYTE v45[224]; // [rsp+A0h] [rbp-60h] BYREF
  int v46; // [rsp+1B0h] [rbp+B0h] BYREF
  const unsigned __int8 *v47; // [rsp+1B8h] [rbp+B8h] BYREF

  v46 = 0;
  if ( !PPTraceShouldRedact() || (LOBYTE(v12) = 1, v13 = !PPTraceStatus::TraceOnFlag(v12, v11), v15 = v14, v13) )
    v15 = 0;
  CredentialBlob = Src;
  v42 = 0;
  v43 = v15;
  v40 = &PPRedactedStringW::`vftable';
  String = PPRedactedStringW::GetString((PPRedactedStringW *)&v40);
  CTraceFuncW<long>::CTraceFuncW<long>(
    v44,
    "onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\singleidentity.cpp",
    3595,
    (const char *)&v46,
    "CAuthInfo::GetCachedAuthInfoEx",
    L"wszUserName=%ls, wszVirtualAppName=%ls",
    String,
    a2);
  PPRedactedStringW::~PPRedactedStringW((PPRedactedStringW *)&v40);
  ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&Filter);
  *(_OWORD *)v39 = 0;
  v38 = &SmartCredManArrayMem::`vftable';
  v17 = a6;
  if ( (!Src || !*Src) && !a3 )
  {
    v36 = "parametersValid";
    v18 = 3606;
LABEL_48:
    v46 = -2147186553;
    Telemetry::IfFailExit(
      "onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\singleidentity.cpp",
      "CAuthInfo::GetCachedAuthInfoEx",
      v18,
      -2147186553,
      v36);
    goto LABEL_49;
  }
  v19 = a7;
  *a7 = 0;
  if ( a3 )
    CAuthInfo::GetVirtualAppTargetName(a2, &Filter);
  else
    CAuthInfo::GetUserTargetName(Src);
  if ( !(unsigned int)CredmanUtility::CredEnumerateW(Filter, v20, (unsigned int *)v39, &v39[1]) )
  {
    if ( GetLastError() == 1168 )
    {
      LastError = -2147186553;
    }
    else if ( GetLastError() == 1312 )
    {
      LastError = -2147186500;
    }
    else
    {
      LastError = GetLastError();
      if ( LastError > 0 )
        LastError = (unsigned __int16)LastError | 0x80070000;
    }
    v46 = LastError;
    goto LABEL_49;
  }
  v22 = v39[1];
  if ( !v39[1] || !LODWORD(v39[0]) )
  {
    v32 = "credentialsArrayValid";
    v18 = 3646;
LABEL_47:
    v36 = (char *)v32;
    goto LABEL_48;
  }
  v23 = 0;
  while ( 1 )
  {
    v24 = v22[v23];
    if ( !v24 )
    {
      LODWORD(v35) = v23;
      TracePrintW(
        2u,
        "onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\singleidentity.cpp",
        0xE48u,
        L"CredEnumerateW returned a null cred pointer index =%d.",
        v35);
      goto LABEL_28;
    }
    if ( !Src || !*Src || !lstrcmpiW(Src, v24->UserName) )
      break;
LABEL_28:
    if ( (unsigned int)++v23 >= LODWORD(v39[0]) )
    {
      v32 = "pTheCred != nullptr";
      v18 = 3671;
      goto LABEL_47;
    }
    v22 = v39[1];
  }
  ATL::CSimpleStringT<unsigned short,0>::SetString(a4, v24->UserName);
  if ( v24->CredentialBlob )
  {
    ServiceExecutionContext::ServiceExecutionContext((ServiceExecutionContext *)v45);
    HIDWORD(v40) = 0;
    LODWORD(v40) = v24->CredentialBlobSize;
    CredentialBlob = v24->CredentialBlob;
    v25 = CAuthInfo::DecryptSystemContextCredentials<CAutoZeroMemoryStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,unsigned short>(
            (__int64)v45,
            (__int64)&v40,
            a5);
    v46 = v25;
    if ( v25 < 0 )
    {
      LODWORD(v35) = v25;
      TracePrintW(
        2u,
        "onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\singleidentity.cpp",
        0xE64u,
        L"Failure - CryptProtectData, HRESULT: 0x%08X\n",
        v35);
      ServiceExecutionContext::~ServiceExecutionContext((ServiceExecutionContext *)v45);
      goto LABEL_49;
    }
    ServiceExecutionContext::~ServiceExecutionContext((ServiceExecutionContext *)v45);
  }
  v26 = CTokenInfo::AssembleTokenBlob(v24, L"Microsoft_WindowsLive:authstate:", v17);
  v46 = v26;
  if ( v26 >= 0 )
  {
    if ( (byte_1801C36C4 & 0x20) != 0 )
    {
      ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v47);
      LOBYTE(v27) = PPTraceShouldRedact();
      if ( (int)RedactSensitiveXMLElements(v17, &v47, v27) >= 0 )
      {
        ReduceXmlForTracing(&v47, v28);
        if ( (byte_1801C36C4 & 0x20) != 0 )
          McTemplateU0sqs_EventWriteTransfer(
            v30,
            v29,
            (unsigned int)"onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\singleidentity.cpp",
            3701,
            (__int64)v47);
      }
      ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v47);
    }
    Comment = v24->Comment;
    if ( Comment && !wcscmp_0(Comment, L"PersistedCredential") && *(int *)(*v17 - 16LL) > 0 )
      *v19 = 1;
  }
  else
  {
    Telemetry::IfFailExit(
      "onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\singleidentity.cpp",
      "CAuthInfo::GetCachedAuthInfoEx",
      0xE68u,
      v26,
      "hr = CTokenInfo::AssembleTokenBlob(pTheCred, PPCRL_CRED_AUTHSTATE_KEYWORD, wstrAuthInfoBlob)");
  }
LABEL_49:
  if ( v46 < 0 )
  {
    ATL::CSimpleStringT<unsigned short,0>::Truncate(a4, 0);
    CAutoZeroMemoryStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::SetZeroMemory(v17);
    ATL::CSimpleStringT<unsigned short,0>::Truncate(v17, 0);
    CAutoZeroMemoryStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::SetZeroMemory(a5);
    ATL::CSimpleStringT<unsigned short,0>::Truncate(a5, 0);
  }
  v33 = v46;
  SmartCredManArrayMem::~SmartCredManArrayMem((SmartCredManArrayMem *)&v38);
  ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&Filter);
  CTraceFuncW<long>::~CTraceFuncW<long>((__int64)v44);
  return v33;
}

```

## disassembly

```asm
0x180065d40  mov     [rsp-8+arg_10], rbx
0x180065d45  mov     [rsp-8+arg_18], rsi
0x180065d4a  push    rbp
0x180065d4b  push    rdi
0x180065d4c  push    r13
0x180065d4e  push    r14
0x180065d50  push    r15
0x180065d52  lea     rbp, [rsp-80h]
0x180065d57  sub     rsp, 180h
0x180065d5e  mov     r13, r9
0x180065d61  mov     bl, r8b
0x180065d64  mov     rdi, rdx
0x180065d67  mov     rsi, rcx
0x180065d6a  xor     r14d, r14d
0x180065d6d  mov     [rbp+0A0h+arg_0], r14d
0x180065d74  call    ?PPTraceShouldRedact@@YA_NXZ; PPTraceShouldRedact(void)
0x180065d79  test    al, al
0x180065d7b  jz      short loc_180065D8A
0x180065d7d  mov     cl, 1; this
0x180065d7f  call    ?TraceOnFlag@PPTraceStatus@@YA_NE@Z; PPTraceStatus::TraceOnFlag(uchar)
0x180065d84  test    al, al
0x180065d86  mov     al, cl
0x180065d88  jnz     short loc_180065D8D
0x180065d8a  mov     al, r14b
0x180065d8d  mov     qword ptr [rsp+1A0h+var_140+8], rsi
0x180065d92  mov     [rsp+1A0h+var_130], r14
0x180065d97  mov     [rsp+1A0h+var_128], al
0x180065d9b  lea     rax, ??_7PPRedactedStringW@@6B@; const PPRedactedStringW::`vftable'
0x180065da2  mov     qword ptr [rsp+1A0h+var_140], rax
0x180065da7  lea     rcx, [rsp+1A0h+var_140]; this
0x180065dac  call    ?GetString@PPRedactedStringW@@QEAAPEBGXZ; PPRedactedStringW::GetString(void)
0x180065db1  mov     [rsp+1A0h+var_168], rdi
0x180065db6  mov     [rsp+1A0h+var_170], rax
0x180065dbb  lea     rax, aWszusernameLsW; "wszUserName=%ls, wszVirtualAppName=%ls"
0x180065dc2  mov     [rsp+1A0h+var_178], rax
0x180065dc7  lea     r15, aCauthinfoGetca_3; "CAuthInfo::GetCachedAuthInfoEx"
0x180065dce  mov     [rsp+1A0h+var_180], r15
0x180065dd3  lea     r9, [rbp+0A0h+arg_0]
0x180065dda  mov     r8d, 0E0Bh
0x180065de0  lea     rdx, aOnecoreuapDsEx_24; "onecoreuap\\ds\\ext\\live\\identity\\nt"...
0x180065de7  lea     rcx, [rbp+0A0h+var_120]
0x180065deb  call    ??0?$CTraceFuncW@J@@QEAA@PEBDKAEAJ0PEBGZZ; CTraceFuncW<long>::CTraceFuncW<long>(char const *,ulong,long &,char const *,ushort const *,...)
0x180065df0  nop
0x180065df1  lea     rcx, [rsp+1A0h+var_140]; this
0x180065df6  call    ??1PPRedactedStringW@@QEAA@XZ; PPRedactedStringW::~PPRedactedStringW(void)
0x180065dfb  lea     rcx, [rsp+1A0h+Filter]
0x180065e00  call    ??0?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(void)
0x180065e05  nop
0x180065e06  xorps   xmm0, xmm0
0x180065e09  movups  xmmword ptr [rsp+1A0h+var_150], xmm0
0x180065e0e  lea     rax, ??_7SmartCredManArrayMem@@6B@; const SmartCredManArrayMem::`vftable'
0x180065e15  mov     [rsp+1A0h+var_158], rax
0x180065e1a  mov     r14, [rbp+0A0h+arg_28]
0x180065e21  xor     eax, eax
0x180065e23  test    rsi, rsi
0x180065e26  jz      short loc_180065E2D
0x180065e28  cmp     [rsi], ax
0x180065e2b  jnz     short loc_180065E4B
0x180065e2d  test    bl, bl
0x180065e2f  jnz     short loc_180065E4B
0x180065e31  lea     r8, aParametersvali; "parametersValid"
0x180065e38  mov     [rsp+1A0h+var_180], r8
0x180065e3d  mov     r8d, 0E16h
0x180065e43  mov     rdx, r15
0x180065e46  jmp     loc_1800660EF
0x180065e4b  mov     r15, [rbp+0A0h+arg_30]
0x180065e52  mov     [r15], al
0x180065e55  lea     rdx, [rsp+1A0h+Filter]
0x180065e5a  test    bl, bl
0x180065e5c  jz      short loc_180065E68
0x180065e5e  mov     rcx, rdi
0x180065e61  call    ?GetVirtualAppTargetName@CAuthInfo@@SAXPEBGAEAV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@Z; CAuthInfo::GetVirtualAppTargetName(ushort const *,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> &)
0x180065e66  jmp     short loc_180065E70
0x180065e68  mov     rcx, rsi; Src
0x180065e6b  call    ?GetUserTargetName@CAuthInfo@@SAXPEBGAEAV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@Z; CAuthInfo::GetUserTargetName(ushort const *,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> &)
0x180065e70  lea     r9, [rsp+1A0h+var_150+8]; struct _CREDENTIALW ***
0x180065e75  lea     r8, [rsp+1A0h+var_150]; unsigned int *
0x180065e7a  mov     rcx, [rsp+1A0h+Filter]; Filter
0x180065e7f  call    ?CredEnumerateW@CredmanUtility@@SAHPEBGKPEAKPEAPEAPEAU_CREDENTIALW@@@Z; CredmanUtility::CredEnumerateW(ushort const *,ulong,ulong *,_CREDENTIALW * * *)
0x180065e84  xor     ecx, ecx
0x180065e86  test    eax, eax
0x180065e88  jnz     short loc_180065ED3
0x180065e8a  call    cs:__imp_GetLastError
0x180065e90  cmp     eax, 490h
0x180065e95  jnz     short loc_180065E9E
0x180065e97  mov     eax, 80048887h
0x180065e9c  jmp     short loc_180065EB0
0x180065e9e  call    cs:__imp_GetLastError
0x180065ea4  cmp     eax, 520h
0x180065ea9  jnz     short loc_180065EB4
0x180065eab  mov     eax, 800488BCh
0x180065eb0  xor     edi, edi
0x180065eb2  jmp     short loc_180065EC8
0x180065eb4  call    cs:__imp_GetLastError
0x180065eba  xor     edi, edi
0x180065ebc  test    eax, eax
0x180065ebe  jle     short loc_180065EC8
0x180065ec0  movzx   eax, ax
0x180065ec3  or      eax, 80070000h
0x180065ec8  mov     [rbp+0A0h+arg_0], eax
0x180065ece  jmp     loc_18006610B
0x180065ed3  mov     rbx, [rsp+1A0h+var_150+8]
0x180065ed8  test    rbx, rbx
0x180065edb  jz      loc_1800660D6
0x180065ee1  mov     eax, dword ptr [rsp+1A0h+var_150]
0x180065ee5  test    eax, eax
0x180065ee7  jz      loc_1800660D6
0x180065eed  mov     edi, ecx
0x180065eef  mov     eax, edi
0x180065ef1  mov     rbx, [rbx+rax*8]
0x180065ef5  test    rbx, rbx
0x180065ef8  jnz     short loc_180065F1E
0x180065efa  mov     dword ptr [rsp+1A0h+var_180], edi
0x180065efe  lea     r9, aCredenumeratew_1; "CredEnumerateW returned a null cred poi"...
0x180065f05  mov     r8d, 0E48h; unsigned int
0x180065f0b  lea     rdx, aOnecoreuapDsEx_24; "onecoreuap\\ds\\ext\\live\\identity\\nt"...
0x180065f12  lea     ecx, [rbx+2]; unsigned __int8
0x180065f15  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x180065f1a  xor     ecx, ecx
0x180065f1c  jmp     short loc_180065F3B
0x180065f1e  test    rsi, rsi
0x180065f21  jz      short loc_180065F4E
0x180065f23  cmp     [rsi], cx
0x180065f26  jz      short loc_180065F4E
0x180065f28  mov     rdx, [rbx+48h]; lpString2
0x180065f2c  mov     rcx, rsi; lpString1
0x180065f2f  call    cs:__imp_lstrcmpiW
0x180065f35  xor     ecx, ecx
0x180065f37  test    eax, eax
0x180065f39  jz      short loc_180065F4E
0x180065f3b  inc     edi
0x180065f3d  cmp     edi, dword ptr [rsp+1A0h+var_150]
0x180065f41  jnb     loc_1800660C7
0x180065f47  mov     rbx, [rsp+1A0h+var_150+8]
0x180065f4c  jmp     short loc_180065EEF
0x180065f4e  mov     rdx, [rbx+48h]
0x180065f52  mov     rcx, r13
0x180065f55  call    ?SetString@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBG@Z; ATL::CSimpleStringT<ushort,0>::SetString(ushort const *)
0x180065f5a  xor     edi, edi
0x180065f5c  cmp     [rbx+28h], rdi
0x180065f60  jz      loc_180065FE6
0x180065f66  lea     rcx, [rbp+0A0h+var_100]; this
0x180065f6a  call    ??0ServiceExecutionContext@@QEAA@XZ; ServiceExecutionContext::ServiceExecutionContext(void)
0x180065f6f  nop
0x180065f70  mov     dword ptr [rsp+1A0h+var_140+4], edi
0x180065f74  mov     eax, [rbx+20h]
0x180065f77  mov     dword ptr [rsp+1A0h+var_140], eax
0x180065f7b  mov     rax, [rbx+28h]
0x180065f7f  mov     qword ptr [rsp+1A0h+var_140+8], rax
0x180065f84  movaps  xmm0, [rsp+1A0h+var_140]
0x180065f89  movdqa  [rsp+1A0h+var_140], xmm0
0x180065f8f  mov     r8, [rbp+0A0h+arg_20]
0x180065f96  lea     rdx, [rsp+1A0h+var_140]
0x180065f9b  lea     rcx, [rbp+0A0h+var_100]
0x180065f9f  call    ??$DecryptSystemContextCredentials@V?$CAutoZeroMemoryStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@@G@CAuthInfo@@SAJPEAVIServiceExecutionContext@@U_CRYPTOAPI_BLOB@@AEAV?$CAutoZeroMemoryStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@@@Z; CAuthInfo::DecryptSystemContextCredentials<CAutoZeroMemoryStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,ushort>(IServiceExecutionContext *,_CRYPTOAPI_BLOB,CAutoZeroMemoryStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> &)
0x180065fa4  mov     [rbp+0A0h+arg_0], eax
0x180065faa  test    eax, eax
0x180065fac  jns     short loc_180065FDD
0x180065fae  mov     dword ptr [rsp+1A0h+var_180], eax
0x180065fb2  lea     r9, aFailureCryptpr; "Failure - CryptProtectData, HRESULT: 0x"...
0x180065fb9  mov     r8d, 0E64h; unsigned int
0x180065fbf  lea     rdx, aOnecoreuapDsEx_24; "onecoreuap\\ds\\ext\\live\\identity\\nt"...
0x180065fc6  lea     ecx, [rdi+2]; unsigned __int8
0x180065fc9  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x180065fce  nop
0x180065fcf  lea     rcx, [rbp+0A0h+var_100]; this
0x180065fd3  call    ??1ServiceExecutionContext@@UEAA@XZ; ServiceExecutionContext::~ServiceExecutionContext(void)
0x180065fd8  jmp     loc_18006610B
0x180065fdd  lea     rcx, [rbp+0A0h+var_100]; this
0x180065fe1  call    ??1ServiceExecutionContext@@UEAA@XZ; ServiceExecutionContext::~ServiceExecutionContext(void)
0x180065fe6  mov     r8, r14
0x180065fe9  lea     rdx, aMicrosoftWindo_1; "Microsoft_WindowsLive:authstate:"
0x180065ff0  mov     rcx, rbx
0x180065ff3  call    ?AssembleTokenBlob@CTokenInfo@@SAJPEAU_CREDENTIALW@@PEBGAEAV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@Z; CTokenInfo::AssembleTokenBlob(_CREDENTIALW *,ushort const *,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> &)
0x180065ff8  mov     [rbp+0A0h+arg_0], eax
0x180065ffe  test    eax, eax
0x180066000  jns     short loc_18006602F
0x180066002  lea     rcx, aHrCtokeninfoAs; "hr = CTokenInfo::AssembleTokenBlob(pThe"...
0x180066009  mov     [rsp+1A0h+var_180], rcx; char *
0x18006600e  mov     r9d, eax; int
0x180066011  mov     r8d, 0E68h; unsigned int
0x180066017  lea     rdx, aCauthinfoGetca_3; "CAuthInfo::GetCachedAuthInfoEx"
0x18006601e  lea     rcx, aOnecoreuapDsEx_24; "onecoreuap\\ds\\ext\\live\\identity\\nt"...
0x180066025  call    ?IfFailExit@Telemetry@@SAXPEBD0KJ0@Z; Telemetry::IfFailExit(char const *,char const *,ulong,long,char const *)
0x18006602a  jmp     loc_18006610B
0x18006602f  test    cs:byte_1801C36C4, 20h
0x180066036  jz      short loc_1800660A0
0x180066038  lea     rcx, [rbp+0A0h+arg_8]
0x18006603f  call    ??0?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(void)
0x180066044  nop
0x180066045  call    ?PPTraceShouldRedact@@YA_NXZ; PPTraceShouldRedact(void)
0x18006604a  mov     r8b, al
0x18006604d  lea     rdx, [rbp+0A0h+arg_8]
0x180066054  mov     rcx, r14
0x180066057  call    ?RedactSensitiveXMLElements@@YAJAEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@AEAV?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@2@_N@Z; RedactSensitiveXMLElements(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>> &,bool)
0x18006605c  test    eax, eax
0x18006605e  js      short loc_180066094
0x180066060  lea     rcx, [rbp+0A0h+arg_8]
0x180066067  call    ?ReduceXmlForTracing@@YAJAEAV?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@@Z; ReduceXmlForTracing(ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>> &)
0x18006606c  test    cs:byte_1801C36C4, 20h
0x180066073  jz      short loc_180066094
0x180066075  mov     rax, [rbp+0A0h+arg_8]
0x18006607c  mov     [rsp+1A0h+var_180], rax
0x180066081  mov     r9d, 0E75h
0x180066087  lea     r8, aOnecoreuapDsEx_24; "onecoreuap\\ds\\ext\\live\\identity\\nt"...
0x18006608e  call    McTemplateU0sqs_EventWriteTransfer
0x180066093  nop
0x180066094  lea     rcx, [rbp+0A0h+arg_8]
0x18006609b  call    ??1?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(void)
0x1800660a0  mov     rcx, [rbx+10h]; String1
0x1800660a4  test    rcx, rcx
0x1800660a7  jz      short loc_18006610B
0x1800660a9  lea     rdx, aPersistedcrede; "PersistedCredential"
0x1800660b0  call    wcscmp_0
0x1800660b5  test    eax, eax
0x1800660b7  jnz     short loc_18006610B
0x1800660b9  mov     rax, [r14]
0x1800660bc  cmp     [rax-10h], edi
0x1800660bf  jle     short loc_18006610B
0x1800660c1  mov     byte ptr [r15], 1
0x1800660c5  jmp     short loc_18006610B
0x1800660c7  lea     rcx, aPthecredNullpt; "pTheCred != nullptr"
0x1800660ce  mov     r8d, 0E57h
0x1800660d4  jmp     short loc_1800660E3
0x1800660d6  lea     rcx, aCredentialsarr; "credentialsArrayValid"
0x1800660dd  mov     r8d, 0E3Eh; unsigned int
0x1800660e3  lea     rdx, aCauthinfoGetca_3; "CAuthInfo::GetCachedAuthInfoEx"
0x1800660ea  mov     [rsp+1A0h+var_180], rcx; char *
0x1800660ef  mov     eax, 80048887h
0x1800660f4  mov     [rbp+0A0h+arg_0], eax
0x1800660fa  mov     r9d, eax; int
0x1800660fd  lea     rcx, aOnecoreuapDsEx_24; "onecoreuap\\ds\\ext\\live\\identity\\nt"...
0x180066104  call    ?IfFailExit@Telemetry@@SAXPEBD0KJ0@Z; Telemetry::IfFailExit(char const *,char const *,ulong,long,char const *)
0x180066109  xor     edi, edi
0x18006610b  cmp     [rbp+0A0h+arg_0], edi
0x180066111  jge     short loc_180066149
0x180066113  xor     edx, edx
0x180066115  mov     rcx, r13
0x180066118  call    ?Truncate@?$CSimpleStringT@G$0A@@ATL@@QEAAXH@Z; ATL::CSimpleStringT<ushort,0>::Truncate(int)
0x18006611d  mov     rcx, r14
0x180066120  call    ?SetZeroMemory@?$CAutoZeroMemoryStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@@QEAAXXZ; CAutoZeroMemoryStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::SetZeroMemory(void)
0x180066125  xor     edx, edx
0x180066127  mov     rcx, r14
0x18006612a  call    ?Truncate@?$CSimpleStringT@G$0A@@ATL@@QEAAXH@Z; ATL::CSimpleStringT<ushort,0>::Truncate(int)
0x18006612f  mov     rcx, [rbp+0A0h+arg_20]
0x180066136  call    ?SetZeroMemory@?$CAutoZeroMemoryStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@@QEAAXXZ; CAutoZeroMemoryStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::SetZeroMemory(void)
0x18006613b  xor     edx, edx
0x18006613d  mov     rcx, [rbp+0A0h+arg_20]
0x180066144  call    ?Truncate@?$CSimpleStringT@G$0A@@ATL@@QEAAXH@Z; ATL::CSimpleStringT<ushort,0>::Truncate(int)
0x180066149  mov     ebx, [rbp+0A0h+arg_0]
0x18006614f  lea     rcx, [rsp+1A0h+var_158]; this
0x180066154  call    ??1SmartCredManArrayMem@@UEAA@XZ; SmartCredManArrayMem::~SmartCredManArrayMem(void)
0x180066159  nop
0x18006615a  lea     rcx, [rsp+1A0h+Filter]
0x18006615f  call    ??1?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(void)
0x180066164  nop
0x180066165  lea     rcx, [rbp+0A0h+var_120]
0x180066169  call    ??1?$CTraceFuncW@J@@QEAA@XZ; CTraceFuncW<long>::~CTraceFuncW<long>(void)
0x18006616e  mov     eax, ebx
0x180066170  lea     r11, [rsp+1A0h+var_20]
0x180066178  mov     rbx, [r11+40h]
0x18006617c  mov     rsi, [r11+48h]
0x180066180  mov     rsp, r11
0x180066183  pop     r15
0x180066185  pop     r14
0x180066187  pop     r13
0x180066189  pop     rdi
0x18006618a  pop     rbp
0x18006618b  retn
```
