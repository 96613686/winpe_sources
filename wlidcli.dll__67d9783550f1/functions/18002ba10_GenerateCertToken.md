# GenerateCertToken

- ea: `0x18002ba10`
- end: `0x18002c0b7`
- name: `GenerateCertToken`
- size: `1703`
- prototype: ``
- caller_count: `0`
- callee_count: `24`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x18000a870`
- `0x18000a914`
- `0x18000ba8c`
- `0x18000c538`
- `0x18000cb6c`
- `0x18000cc9c`
- `0x18000cd80`
- `0x18000cdd8`
- `0x18000d194`
- `0x18000fa70`
- `0x1800103d0`
- `0x18001b0f4`
- `0x18001b4a4`
- `0x18002126c`
- `0x180022f9c`
- `0x180024718`
- `0x18002615c`
- `0x180029788`
- `0x18002ba10`
- `0x1800530e4`
- `0x180054698`
- `0x1800558c0`
- `0x18005733c`
- `0x180057f40`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002bd79`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002bd79`
- `CRYPT32!CertOpenStore` at `0x18002bd59`
- `CRYPT32!CertOpenStore` at `0x18002bd59`

## string_xrefs

- `0x18002bf4c`: `<ps:AssertionFormat xmlns:ps="http://schemas.microsoft.com/Passport/SoapServices/PPCRL">EId</ps:AssertionFormat>`
- `0x18002bd96`: `CertOpenStore failed with hr=0x%x`
- `0x18002bad6`: `IDCRL::GenerateCertToken`
- `0x18002bf7f`: `BuildCertToken failed with hr=0x%x`

## pseudocode

```c
// Hidden C++ exception states: #wind=11
__int64 __fastcall GenerateCertToken(__int64 a1, int a2, unsigned __int16 **a3)
{
  int v6; // r14d
  __int64 v7; // r8
  __int64 v8; // rdi
  __int64 v9; // rax
  __int64 v10; // rax
  int v11; // eax
  int v12; // eax
  HCERTSTORE v13; // rax
  signed int LastError; // eax
  LPCWCH v15; // rbx
  const char *v16; // r9
  bool v17; // zf
  int v18; // ebx
  unsigned int v19; // esi
  const CERT_CONTEXT *v20; // r14
  __int64 *IdentityName; // rax
  int StringForExternal; // eax
  unsigned int v23; // ebx
  void *pvPara; // [rsp+20h] [rbp-118h]
  void *pvParaa; // [rsp+20h] [rbp-118h]
  void *pvParab; // [rsp+20h] [rbp-118h]
  void *pvParac; // [rsp+20h] [rbp-118h]
  __int64 v29; // [rsp+60h] [rbp-D8h] BYREF
  const char *v30; // [rsp+68h] [rbp-D0h] BYREF
  int v31; // [rsp+70h] [rbp-C8h] BYREF
  unsigned int v32; // [rsp+74h] [rbp-C4h] BYREF
  int v33[2]; // [rsp+78h] [rbp-C0h] BYREF
  LPCWCH lpWideCharStr; // [rsp+80h] [rbp-B8h] BYREF
  __int64 v35; // [rsp+88h] [rbp-B0h] BYREF
  unsigned __int8 *v36; // [rsp+90h] [rbp-A8h] BYREF
  unsigned __int16 *v37; // [rsp+98h] [rbp-A0h] BYREF
  unsigned __int64 v38; // [rsp+A0h] [rbp-98h] BYREF
  void **v39; // [rsp+A8h] [rbp-90h] BYREF
  PCCERT_CONTEXT pCertContext; // [rsp+B0h] [rbp-88h] BYREF
  char *v41[4]; // [rsp+B8h] [rbp-80h] BYREF
  void **v42; // [rsp+D8h] [rbp-60h] BYREF
  __int64 v43; // [rsp+E0h] [rbp-58h]
  int v44; // [rsp+E8h] [rbp-50h]
  int v45; // [rsp+F0h] [rbp-48h] BYREF
  CPassportException *v46; // [rsp+F8h] [rbp-40h] BYREF
  ATL::CAtlException *v47; // [rsp+100h] [rbp-38h] BYREF
  const wil::ResultException *v48; // [rsp+108h] [rbp-30h] BYREF
  int IdentityFromExternalHandle_Internal; // [rsp+140h] [rbp+8h] BYREF
  int v50; // [rsp+158h] [rbp+20h] BYREF

  IdentityFromExternalHandle_Internal = 0;
  v43 = 0;
  v42 = &SmartHCERTSTORE::`vftable';
  v44 = 1;
  pCertContext = 0;
  v39 = &SmartPCCERT_CONTEXT::`vftable';
  *(_QWORD *)v33 = 0;
  v32 = 0;
  ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>((__int64)&v37);
  v38 = 0;
  v50 = 0;
  ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>((__int64)&v36);
  ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>((__int64)&v35);
  ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>((__int64)&lpWideCharStr);
  v31 = 0;
  v29 = 0;
  CTraceFuncW<unsigned long>::CTraceFuncW<unsigned long>(
    v41,
    (MsaTracingInternal *)"clientcore\\ds\\ext\\live\\identity\\api\\classic\\ppcrl.cpp",
    0x135Fu,
    (char *)&IdentityFromExternalHandle_Internal,
    "IDCRL::GenerateCertToken",
    L"hExteralIdentity=0x%p, dwFlags=0x%x",
    a1,
    a2);
  if ( !a1 )
  {
    TracePrintW(
      2u,
      "clientcore\\ds\\ext\\live\\identity\\api\\classic\\ppcrl.cpp",
      0x1365u,
      L"some required arguments are NULL");
    IdentityFromExternalHandle_Internal = -2147024809;
    CTraceFuncW<long>::~CTraceFuncW<long>((__int64)v41);
    CAutoRefPtr<CAuthContext>::Deinit(&v29);
    goto LABEL_50;
  }
  if ( (a2 & 0xFFFFFFF8) != 0 )
  {
    IdentityFromExternalHandle_Internal = -2147188692;
    LODWORD(pvPara) = a2;
    TracePrintW(
      2u,
      "clientcore\\ds\\ext\\live\\identity\\api\\classic\\ppcrl.cpp",
      0x136Du,
      L"Unrecognized option id (%d)",
      pvPara);
    CTraceFuncW<long>::~CTraceFuncW<long>((__int64)v41);
    CAutoRefPtr<CAuthContext>::Deinit(&v29);
    goto LABEL_50;
  }
  v6 = a2 & 2;
  IdentityFromExternalHandle_Internal = VerifyInitialized();
  if ( IdentityFromExternalHandle_Internal < 0 )
  {
    CTraceFuncW<long>::~CTraceFuncW<long>((__int64)v41);
    CAutoRefPtr<CAuthContext>::Deinit(&v29);
    goto LABEL_50;
  }
  try
  {
    LOBYTE(v7) = 1;
    IdentityFromExternalHandle_Internal = CClientIdentityStore::GetIdentityFromExternalHandle_Internal(
                                            g_pPPCRL + 8,
                                            a1,
                                            v7,
                                            &v29);
    if ( IdentityFromExternalHandle_Internal >= 0 )
    {
      v8 = v29;
      v9 = ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
             (__int64)&v30,
             (__int64)L"ps:eid");
      IdentityFromExternalHandle_Internal = CClientIdentityCredentialBag::RetrieveCredential(v8 + 80, v9, &v35);
      if ( IdentityFromExternalHandle_Internal >= 0 )
      {
        v10 = ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
                (__int64)&v30,
                (__int64)L"ps:pin");
        v11 = CClientIdentityCredentialBag::RetrieveCredential(v8 + 80, v10, &lpWideCharStr);
        IdentityFromExternalHandle_Internal = v11;
        if ( v11 < 0 )
        {
          LODWORD(pvPara) = v11;
          TracePrintW(
            2u,
            "clientcore\\ds\\ext\\live\\identity\\api\\classic\\ppcrl.cpp",
            0x1383u,
            L"Could not retrieve certificate PIN. hr=0x%x",
            pvPara);
          IdentityFromExternalHandle_Internal = 0;
        }
        v12 = PassportEncode::Base64Decode(v35, *(unsigned int *)(v35 - 16), &v36);
        IdentityFromExternalHandle_Internal = v12;
        if ( v12 < 0 )
        {
          LODWORD(pvPara) = v12;
          TracePrintW(
            2u,
            "clientcore\\ds\\ext\\live\\identity\\api\\classic\\ppcrl.cpp",
            0x138Du,
            L"Base64Decode failed for the thumbprint. hr=0x%x.",
            pvPara);
          CTraceFuncW<long>::~CTraceFuncW<long>((__int64)v41);
          CAutoRefPtr<CAuthContext>::Deinit(&v29);
          goto LABEL_50;
        }
        v13 = CertOpenStore((LPCSTR)0xA, 0, 0, (a2 & 4) != 0 ? 180224 : 114688, L"MY");
        SmartPtr<void *>::Attach(&v42, v13);
        if ( !v43 )
        {
          LastError = GetLastError();
          if ( LastError > 0 )
            LastError = (unsigned __int16)LastError | 0x80070000;
          IdentityFromExternalHandle_Internal = LastError;
          LODWORD(pvParaa) = LastError;
          TracePrintW(
            3u,
            "clientcore\\ds\\ext\\live\\identity\\api\\classic\\ppcrl.cpp",
            0x139Du,
            L"CertOpenStore failed with hr=0x%x",
            pvParaa);
          CTraceFuncW<long>::~CTraceFuncW<long>((__int64)v41);
          CAutoRefPtr<CAuthContext>::Deinit(&v29);
          goto LABEL_50;
        }
        ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>((__int64)&v30);
        v15 = lpWideCharStr;
        if ( *((int *)lpWideCharStr - 4) <= 0 )
        {
          v16 = MultiByteStr;
          if ( v6 )
            v16 = 0;
        }
        else
        {
          ConvertW2A(lpWideCharStr);
          v16 = v30;
        }
        IdentityFromExternalHandle_Internal = GetCertContext(
                                                (struct SmartHCERTSTORE *)&v42,
                                                v36,
                                                *((_DWORD *)v36 - 4),
                                                v16,
                                                v6 == 0,
                                                v6 == 0,
                                                &pCertContext,
                                                &v32,
                                                &v38,
                                                &v50,
                                                &v31);
        CAutoZeroMemoryStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CAutoZeroMemoryStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v30);
        *(_QWORD *)v33 = v38;
        if ( v38 && !v50 )
          ATL::CCryptProv::AddRef((ATL::CCryptProv *)v33);
        if ( IdentityFromExternalHandle_Internal < 0 )
        {
          LODWORD(pvParab) = IdentityFromExternalHandle_Internal;
          TracePrintW(
            3u,
            "clientcore\\ds\\ext\\live\\identity\\api\\classic\\ppcrl.cpp",
            0x13BCu,
            L"GetCertContext failed with hr=0x%x",
            pvParab);
          CTraceFuncW<long>::~CTraceFuncW<long>((__int64)v41);
          CAutoRefPtr<CAuthContext>::Deinit(&v29);
          goto LABEL_50;
        }
        if ( !v31 || v6 || (v17 = *((_DWORD *)v15 - 4) == 0, v18 = 1, !v17) )
          v18 = 0;
        v19 = v32;
        v20 = pCertContext;
        IdentityName = (__int64 *)CClientSingleIdentity::GetIdentityName(v8, &v30);
        IdentityFromExternalHandle_Internal = BuildCertToken(
                                                *IdentityName,
                                                (__int64)L"<ps:AssertionFormat xmlns:ps=\"http://schemas.microsoft.com/Pas"
                                                          "sport/SoapServices/PPCRL\">EId</ps:AssertionFormat>",
                                                0,
                                                (__int64 *)v33,
                                                v20,
                                                v19,
                                                1,
                                                v18,
                                                (__int64)&v37);
        ATL::CStringData::Release((ATL::CStringData *)(v30 - 24));
        if ( IdentityFromExternalHandle_Internal < 0 )
        {
          LODWORD(pvParac) = IdentityFromExternalHandle_Internal;
          TracePrintW(
            3u,
            "clientcore\\ds\\ext\\live\\identity\\api\\classic\\ppcrl.cpp",
            0x13CEu,
            L"BuildCertToken failed with hr=0x%x",
            pvParac);
          CTraceFuncW<long>::~CTraceFuncW<long>((__int64)v41);
          CAutoRefPtr<CAuthContext>::Deinit(&v29);
          goto LABEL_50;
        }
        StringForExternal = CExternalMemoryManager::AllocateStringForExternal(
                              (CExternalMemoryManager *)(g_pPPCRL + 58),
                              v37,
                              a3);
        if ( StringForExternal < 0 )
          IdentityFromExternalHandle_Internal = StringForExternal;
      }
    }
    CTraceFuncW<long>::~CTraceFuncW<long>((__int64)v41);
    CAutoRefPtr<CAuthContext>::Deinit(&v29);
  }
  catch ( CPassportException *v46 )
  {
    IdentityFromExternalHandle_Internal = *((_DWORD *)v46 + 2);
    if ( IdentityFromExternalHandle_Internal >= 0 )
      IdentityFromExternalHandle_Internal = -2147418113;
  }
  catch ( ATL::CAtlException *v47 )
  {
    IdentityFromExternalHandle_Internal = *(_DWORD *)v47;
    if ( IdentityFromExternalHandle_Internal >= 0 )
      IdentityFromExternalHandle_Internal = -2147418113;
  }
  catch ( std::bad_alloc )
  {
    IdentityFromExternalHandle_Internal = -2147024882;
  }
  catch ( long v45 )
  {
    IdentityFromExternalHandle_Internal = v45;
    if ( v45 >= 0 )
      IdentityFromExternalHandle_Internal = -2147418113;
  }
  catch ( const wil::ResultException *v48 )
  {
    IdentityFromExternalHandle_Internal = *((_DWORD *)v48 + 8);
    if ( IdentityFromExternalHandle_Internal >= 0 )
      IdentityFromExternalHandle_Internal = -2147418113;
  }
LABEL_50:
  v23 = IdentityFromExternalHandle_Internal;
  CAutoZeroMemoryStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::~CAutoZeroMemoryStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(&lpWideCharStr);
  CAutoZeroMemoryStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::~CAutoZeroMemoryStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(&v35);
  ATL::CStringData::Release((ATL::CStringData *)(v36 - 24));
  ATL::CStringData::Release((ATL::CStringData *)(v37 - 12));
  ATL::CCryptProv::Release((ATL::CCryptProv *)v33);
  SmartPCCERT_CONTEXT::~SmartPCCERT_CONTEXT((SmartPCCERT_CONTEXT *)&v39);
  SmartHCERTSTORE::~SmartHCERTSTORE((SmartHCERTSTORE *)&v42);
  return v23;
}

```

## disassembly

```asm
0x18002ba10  mov     r11, rsp
0x18002ba13  mov     [r11+10h], rbx
0x18002ba17  mov     [r11+18h], rsi
0x18002ba1b  push    rdi
0x18002ba1c  push    r12
0x18002ba1e  push    r13
0x18002ba20  push    r14
0x18002ba22  push    r15
0x18002ba24  sub     rsp, 110h
0x18002ba2b  mov     r12, r8
0x18002ba2e  mov     ebx, edx
0x18002ba30  mov     rdi, rcx
0x18002ba33  xor     r13d, r13d
0x18002ba36  mov     [r11+8], r13d
0x18002ba3a  mov     [r11-58h], r13
0x18002ba3e  lea     rax, ??_7SmartHCERTSTORE@@6B@; const SmartHCERTSTORE::`vftable'
0x18002ba45  mov     [r11-60h], rax
0x18002ba49  mov     dword ptr [r11-50h], 1
0x18002ba51  mov     [r11-88h], r13
0x18002ba58  lea     rax, ??_7SmartPCCERT_CONTEXT@@6B@; const SmartPCCERT_CONTEXT::`vftable'
0x18002ba5f  mov     [r11-90h], rax
0x18002ba66  mov     qword ptr [rsp+138h+var_C0], r13
0x18002ba6b  mov     [rsp+138h+var_C4], r13d
0x18002ba70  lea     rcx, [r11-0A0h]
0x18002ba77  call    ??0?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(void)
0x18002ba7c  nop
0x18002ba7d  mov     [rsp+138h+var_98], r13
0x18002ba85  mov     [rsp+138h+arg_18], r13d
0x18002ba8d  lea     rcx, [rsp+138h+var_A8]
0x18002ba95  call    ??0?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(void)
0x18002ba9a  nop
0x18002ba9b  lea     rcx, [rsp+138h+var_B0]
0x18002baa3  call    ??0?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(void)
0x18002baa8  nop
0x18002baa9  lea     rcx, [rsp+138h+lpWideCharStr]
0x18002bab1  call    ??0?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(void)
0x18002bab6  nop
0x18002bab7  mov     [rsp+138h+var_C8], r13d
0x18002babc  mov     [rsp+138h+var_D8], r13
0x18002bac1  mov     dword ptr [rsp+138h+var_100], ebx
0x18002bac5  mov     [rsp+138h+var_108], rdi
0x18002baca  lea     rax, aHexteralidenti; "hExteralIdentity=0x%p, dwFlags=0x%x"
0x18002bad1  mov     qword ptr [rsp+138h+var_110], rax
0x18002bad6  lea     rax, aIdcrlGeneratec; "IDCRL::GenerateCertToken"
0x18002badd  mov     [rsp+138h+pvPara], rax
0x18002bae2  lea     r9, [rsp+138h+arg_0]
0x18002baea  mov     r8d, 135Fh
0x18002baf0  lea     rsi, aClientcoreDsEx_1; "clientcore\\ds\\ext\\live\\identity\\ap"...
0x18002baf7  mov     rdx, rsi
0x18002bafa  lea     rcx, [rsp+138h+var_80]
0x18002bb02  call    ??0?$CTraceFuncW@K@@QEAA@PEBDKAEAK0PEBGZZ; CTraceFuncW<ulong>::CTraceFuncW<ulong>(char const *,ulong,ulong &,char const *,ushort const *,...)
0x18002bb07  nop
0x18002bb08  test    rdi, rdi
0x18002bb0b  jnz     short loc_18002BB4E
0x18002bb0d  lea     r9, aSomeRequiredAr; "some required arguments are NULL"
0x18002bb14  mov     r8d, 1365h; unsigned int
0x18002bb1a  mov     rdx, rsi; char *
0x18002bb1d  lea     ecx, [rdi+2]; unsigned __int8
0x18002bb20  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x18002bb25  mov     [rsp+138h+arg_0], 80070057h
0x18002bb30  lea     rcx, [rsp+138h+var_80]
0x18002bb38  call    ??1?$CTraceFuncW@J@@QEAA@XZ; CTraceFuncW<long>::~CTraceFuncW<long>(void)
0x18002bb3d  nop
0x18002bb3e  lea     rcx, [rsp+138h+var_D8]
0x18002bb43  call    ?Deinit@?$CAutoRefPtr@VCAuthContext@@@@IEAAXXZ; CAutoRefPtr<CAuthContext>::Deinit(void)
0x18002bb48  nop
0x18002bb49  jmp     loc_18002C016
0x18002bb4e  test    ebx, 0FFFFFFF8h
0x18002bb54  jz      short loc_18002BB9E
0x18002bb56  mov     [rsp+138h+arg_0], 8004802Ch
0x18002bb61  mov     dword ptr [rsp+138h+pvPara], ebx
0x18002bb65  lea     r9, aUnrecognizedOp; "Unrecognized option id (%d)"
0x18002bb6c  mov     r8d, 136Dh; unsigned int
0x18002bb72  mov     rdx, rsi; char *
0x18002bb75  mov     ecx, 2; unsigned __int8
0x18002bb7a  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x18002bb7f  nop
0x18002bb80  lea     rcx, [rsp+138h+var_80]
0x18002bb88  call    ??1?$CTraceFuncW@J@@QEAA@XZ; CTraceFuncW<long>::~CTraceFuncW<long>(void)
0x18002bb8d  nop
0x18002bb8e  lea     rcx, [rsp+138h+var_D8]
0x18002bb93  call    ?Deinit@?$CAutoRefPtr@VCAuthContext@@@@IEAAXXZ; CAutoRefPtr<CAuthContext>::Deinit(void)
0x18002bb98  nop
0x18002bb99  jmp     loc_18002C016
0x18002bb9e  mov     r14d, ebx
0x18002bba1  and     r14d, 2
0x18002bba5  mov     r15d, r13d
0x18002bba8  setz    r15b
0x18002bbac  call    ?VerifyInitialized@@YAJXZ; VerifyInitialized(void)
0x18002bbb1  mov     [rsp+138h+arg_0], eax
0x18002bbb8  test    eax, eax
0x18002bbba  jns     short loc_18002BBDA
0x18002bbbc  lea     rcx, [rsp+138h+var_80]
0x18002bbc4  call    ??1?$CTraceFuncW@J@@QEAA@XZ; CTraceFuncW<long>::~CTraceFuncW<long>(void)
0x18002bbc9  nop
0x18002bbca  lea     rcx, [rsp+138h+var_D8]
0x18002bbcf  call    ?Deinit@?$CAutoRefPtr@VCAuthContext@@@@IEAAXXZ; CAutoRefPtr<CAuthContext>::Deinit(void)
0x18002bbd4  nop
0x18002bbd5  jmp     loc_18002C016
0x18002bbda  mov     rcx, cs:?g_pPPCRL@@3PEAVCClientPassportClientLibrary@@EA; CClientPassportClientLibrary * g_pPPCRL
0x18002bbe1  add     rcx, 20h ; ' '
0x18002bbe5  lea     r9, [rsp+138h+var_D8]
0x18002bbea  mov     r8b, 1
0x18002bbed  mov     rdx, rdi
0x18002bbf0  call    ?GetIdentityFromExternalHandle_Internal@CClientIdentityStore@@QEAAJPEAU_tagPIH@IDCRL@@_NAEAV?$CAutoRefPtr@VCClientSingleIdentity@@@@@Z; CClientIdentityStore::GetIdentityFromExternalHandle_Internal(IDCRL::_tagPIH *,bool,CAutoRefPtr<CClientSingleIdentity> &)
0x18002bbf5  mov     [rsp+138h+arg_0], eax
0x18002bbfc  test    eax, eax
0x18002bbfe  jns     short loc_18002BC1E
0x18002bc00  lea     rcx, [rsp+138h+var_80]
0x18002bc08  call    ??1?$CTraceFuncW@J@@QEAA@XZ; CTraceFuncW<long>::~CTraceFuncW<long>(void)
0x18002bc0d  nop
0x18002bc0e  lea     rcx, [rsp+138h+var_D8]
0x18002bc13  call    ?Deinit@?$CAutoRefPtr@VCAuthContext@@@@IEAAXXZ; CAutoRefPtr<CAuthContext>::Deinit(void)
0x18002bc18  nop
0x18002bc19  jmp     loc_18002C016
0x18002bc1e  mov     rdi, [rsp+138h+var_D8]
0x18002bc23  lea     rdx, aPsEid; "ps:eid"
0x18002bc2a  lea     rcx, [rsp+138h+var_D0]
0x18002bc2f  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ushort const *)
0x18002bc34  lea     r8, [rsp+138h+var_B0]
0x18002bc3c  mov     rdx, rax
0x18002bc3f  lea     rcx, [rdi+50h]
0x18002bc43  call    ?RetrieveCredential@CClientIdentityCredentialBag@@QEAAJV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@AEAV?$CAutoZeroMemoryStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@@@Z; CClientIdentityCredentialBag::RetrieveCredential(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,CAutoZeroMemoryStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> &)
0x18002bc48  mov     [rsp+138h+arg_0], eax
0x18002bc4f  test    eax, eax
0x18002bc51  jns     short loc_18002BC71
0x18002bc53  lea     rcx, [rsp+138h+var_80]
0x18002bc5b  call    ??1?$CTraceFuncW@J@@QEAA@XZ; CTraceFuncW<long>::~CTraceFuncW<long>(void)
0x18002bc60  nop
0x18002bc61  lea     rcx, [rsp+138h+var_D8]
0x18002bc66  call    ?Deinit@?$CAutoRefPtr@VCAuthContext@@@@IEAAXXZ; CAutoRefPtr<CAuthContext>::Deinit(void)
0x18002bc6b  nop
0x18002bc6c  jmp     loc_18002C016
0x18002bc71  lea     rdx, aPsPin; "ps:pin"
0x18002bc78  lea     rcx, [rsp+138h+var_D0]
0x18002bc7d  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ushort const *)
0x18002bc82  lea     r8, [rsp+138h+lpWideCharStr]
0x18002bc8a  mov     rdx, rax
0x18002bc8d  lea     rcx, [rdi+50h]
0x18002bc91  call    ?RetrieveCredential@CClientIdentityCredentialBag@@QEAAJV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@AEAV?$CAutoZeroMemoryStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@@@Z; CClientIdentityCredentialBag::RetrieveCredential(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,CAutoZeroMemoryStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> &)
0x18002bc96  mov     [rsp+138h+arg_0], eax
0x18002bc9d  test    eax, eax
0x18002bc9f  jns     short loc_18002BCCB
0x18002bca1  mov     dword ptr [rsp+138h+pvPara], eax
0x18002bca5  lea     r9, aCouldNotRetrie; "Could not retrieve certificate PIN. hr="...
0x18002bcac  mov     r8d, 1383h; unsigned int
0x18002bcb2  lea     rdx, aClientcoreDsEx_1; "clientcore\\ds\\ext\\live\\identity\\ap"...
0x18002bcb9  mov     ecx, 2; unsigned __int8
0x18002bcbe  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x18002bcc3  mov     [rsp+138h+arg_0], r13d
0x18002bccb  lea     r8, [rsp+138h+var_A8]
0x18002bcd3  mov     rcx, [rsp+138h+var_B0]
0x18002bcdb  mov     edx, [rcx-10h]
0x18002bcde  call    ?Base64Decode@PassportEncode@@YAJPEBGKAEAV?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@@Z; PassportEncode::Base64Decode(ushort const *,ulong,ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>> &)
0x18002bce3  mov     [rsp+138h+arg_0], eax
0x18002bcea  test    eax, eax
0x18002bcec  jns     short loc_18002BD2F
0x18002bcee  mov     dword ptr [rsp+138h+pvPara], eax
0x18002bcf2  lea     r9, aBase64decodeFa; "Base64Decode failed for the thumbprint."...
0x18002bcf9  mov     r8d, 138Dh; unsigned int
0x18002bcff  lea     rdx, aClientcoreDsEx_1; "clientcore\\ds\\ext\\live\\identity\\ap"...
0x18002bd06  mov     ecx, 2; unsigned __int8
0x18002bd0b  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x18002bd10  nop
0x18002bd11  lea     rcx, [rsp+138h+var_80]
0x18002bd19  call    ??1?$CTraceFuncW@J@@QEAA@XZ; CTraceFuncW<long>::~CTraceFuncW<long>(void)
0x18002bd1e  nop
0x18002bd1f  lea     rcx, [rsp+138h+var_D8]
0x18002bd24  call    ?Deinit@?$CAutoRefPtr@VCAuthContext@@@@IEAAXXZ; CAutoRefPtr<CAuthContext>::Deinit(void)
0x18002bd29  nop
0x18002bd2a  jmp     loc_18002C016
0x18002bd2f  and     bl, 4
0x18002bd32  neg     bl
0x18002bd34  sbb     r9d, r9d
0x18002bd37  and     r9d, 10000h
0x18002bd3e  add     r9d, 1C000h; dwFlags
0x18002bd45  lea     rax, aMy; "MY"
0x18002bd4c  mov     [rsp+138h+pvPara], rax; pvPara
0x18002bd51  xor     r8d, r8d; hCryptProv
0x18002bd54  xor     edx, edx; dwEncodingType
0x18002bd56  lea     ecx, [rdx+0Ah]; lpszStoreProvider
0x18002bd59  call    cs:__imp_CertOpenStore
0x18002bd5f  mov     rdx, rax
0x18002bd62  lea     rcx, [rsp+138h+var_60]
0x18002bd6a  call    ?Attach@?$SmartPtr@PEAX@@QEAAXPEAX@Z; SmartPtr<void *>::Attach(void *)
0x18002bd6f  cmp     [rsp+138h+var_58], r13
0x18002bd77  jnz     short loc_18002BDD3
0x18002bd79  call    cs:__imp_GetLastError
0x18002bd7f  test    eax, eax
0x18002bd81  jle     short loc_18002BD8B
0x18002bd83  movzx   eax, ax
0x18002bd86  or      eax, 80070000h
0x18002bd8b  mov     [rsp+138h+arg_0], eax
0x18002bd92  mov     dword ptr [rsp+138h+pvPara], eax
0x18002bd96  lea     r9, aCertopenstoreF; "CertOpenStore failed with hr=0x%x"
0x18002bd9d  mov     r8d, 139Dh; unsigned int
0x18002bda3  lea     rdx, aClientcoreDsEx_1; "clientcore\\ds\\ext\\live\\identity\\ap"...
0x18002bdaa  mov     ecx, 3; unsigned __int8
0x18002bdaf  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x18002bdb4  nop
0x18002bdb5  lea     rcx, [rsp+138h+var_80]
0x18002bdbd  call    ??1?$CTraceFuncW@J@@QEAA@XZ; CTraceFuncW<long>::~CTraceFuncW<long>(void)
0x18002bdc2  nop
0x18002bdc3  lea     rcx, [rsp+138h+var_D8]
0x18002bdc8  call    ?Deinit@?$CAutoRefPtr@VCAuthContext@@@@IEAAXXZ; CAutoRefPtr<CAuthContext>::Deinit(void)
0x18002bdcd  nop
0x18002bdce  jmp     loc_18002C016
0x18002bdd3  lea     rcx, [rsp+138h+var_D0]
0x18002bdd8  call    ??0?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(void)
0x18002bddd  nop
0x18002bdde  mov     rbx, [rsp+138h+lpWideCharStr]
0x18002bde6  cmp     [rbx-10h], r13d
0x18002bdea  jle     short loc_18002BE00
0x18002bdec  lea     rdx, [rsp+138h+var_D0]
0x18002bdf1  mov     rcx, rbx; lpWideCharStr
0x18002bdf4  call    ?ConvertW2A@@YAJPEBGAEAV?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@@Z; ConvertW2A(ushort const *,ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>> &)
0x18002bdf9  mov     r9, [rsp+138h+var_D0]
0x18002bdfe  jmp     short loc_18002BE0E
0x18002be00  lea     r9, MultiByteStr
0x18002be07  test    r14d, r14d
0x18002be0a  cmovnz  r9, r13; char *
0x18002be0e  lea     rax, [rsp+138h+var_C8]
0x18002be13  mov     [rsp+138h+var_E8], rax; int *
0x18002be18  lea     rax, [rsp+138h+arg_18]
0x18002be20  mov     [rsp+138h+var_F0], rax; int *
0x18002be25  lea     rax, [rsp+138h+var_98]
0x18002be2d  mov     [rsp+138h+var_F8], rax; unsigned __int64 *
0x18002be32  lea     rax, [rsp+138h+var_C4]
0x18002be37  mov     [rsp+138h+var_100], rax; unsigned int *
0x18002be3c  lea     rax, [rsp+138h+pCertContext]
0x18002be44  mov     [rsp+138h+var_108], rax; struct _CERT_CONTEXT **
0x18002be49  mov     [rsp+138h+var_110], r15d; int
0x18002be4e  mov     dword ptr [rsp+138h+pvPara], r15d; int
0x18002be53  mov     rdx, [rsp+138h+var_A8]; unsigned __int8 *
0x18002be5b  mov     r8d, [rdx-10h]; unsigned int
0x18002be5f  lea     rcx, [rsp+138h+var_60]; struct SmartHCERTSTORE *
0x18002be67  call    ?GetCertContext@@YAJAEAVSmartHCERTSTORE@@PEBEKPEBDHHPEAPEBU_CERT_CONTEXT@@AEAKPEA_KAEAH6@Z; GetCertContext(SmartHCERTSTORE &,uchar const *,ulong,char const *,int,int,_CERT_CONTEXT const * *,ulong &,unsigned __int64 *,int &,int &)
0x18002be6c  mov     [rsp+138h+arg_0], eax
0x18002be73  lea     rcx, [rsp+138h+var_D0]
0x18002be78  call    ??1?$CAutoZeroMemoryStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@@QEAA@XZ; CAutoZeroMemoryStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CAutoZeroMemoryStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(void)
0x18002be7d  mov     rax, [rsp+138h+var_98]
0x18002be85  mov     qword ptr [rsp+138h+var_C0], rax
0x18002be8a  test    rax, rax
0x18002be8d  jz      short loc_18002BEA3
0x18002be8f  cmp     [rsp+138h+arg_18], r13d
0x18002be97  jnz     short loc_18002BEA3
0x18002be99  lea     rcx, [rsp+138h+var_C0]; this
0x18002be9e  call    ?AddRef@CCryptProv@ATL@@QEAAJXZ; ATL::CCryptProv::AddRef(void)
0x18002bea3  mov     eax, [rsp+138h+arg_0]
0x18002beaa  test    eax, eax
0x18002beac  jns     short loc_18002BEEF
0x18002beae  mov     dword ptr [rsp+138h+pvPara], eax
0x18002beb2  lea     r9, aGetcertcontext_0; "GetCertContext failed with hr=0x%x"
0x18002beb9  mov     r8d, 13BCh; unsigned int
0x18002bebf  lea     rdx, aClientcoreDsEx_1; "clientcore\\ds\\ext\\live\\identity\\ap"...
0x18002bec6  mov     ecx, 3; unsigned __int8
0x18002becb  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x18002bed0  nop
0x18002bed1  lea     rcx, [rsp+138h+var_80]
0x18002bed9  call    ??1?$CTraceFuncW@J@@QEAA@XZ; CTraceFuncW<long>::~CTraceFuncW<long>(void)
0x18002bede  nop
0x18002bedf  lea     rcx, [rsp+138h+var_D8]
0x18002bee4  call    ?Deinit@?$CAutoRefPtr@VCAuthContext@@@@IEAAXXZ; CAutoRefPtr<CAuthContext>::Deinit(void)
0x18002bee9  nop
0x18002beea  jmp     loc_18002C016
0x18002beef  cmp     [rsp+138h+var_C8], r13d
0x18002bef4  jz      short loc_18002BF05
0x18002bef6  test    r14d, r14d
0x18002bef9  jnz     short loc_18002BF05
0x18002befb  cmp     [rbx-10h], r13d
0x18002beff  lea     ebx, [r14+1]
0x18002bf03  jz      short loc_18002BF08
0x18002bf05  mov     ebx, r13d
0x18002bf08  mov     esi, [rsp+138h+var_C4]
0x18002bf0c  mov     r14, [rsp+138h+pCertContext]
0x18002bf14  lea     rdx, [rsp+138h+var_D0]
0x18002bf19  mov     rcx, rdi
0x18002bf1c  call    ?GetIdentityName@CClientSingleIdentity@@QEBA?AV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@XZ; CClientSingleIdentity::GetIdentityName(void)
0x18002bf21  nop
0x18002bf22  lea     rcx, [rsp+138h+var_A0]
0x18002bf2a  mov     [rsp+138h+var_F8], rcx; __int64
0x18002bf2f  mov     dword ptr [rsp+138h+var_100], ebx; int
0x18002bf33  mov     dword ptr [rsp+138h+var_108], 1; int
0x18002bf3b  mov     [rsp+138h+var_110], esi; int
0x18002bf3f  mov     [rsp+138h+pvPara], r14; pCertContext
0x18002bf44  lea     r9, [rsp+138h+var_C0]; int
0x18002bf49  xor     r8d, r8d; int
0x18002bf4c  lea     rdx, aPsAssertionfor; "<ps:AssertionFormat xmlns:ps=\"http://s"...
0x18002bf53  mov     rcx, [rax]; int
0x18002bf56  call    ?BuildCertToken@@YAJPEBG00AEAVCCryptProv@ATL@@PEBU_CERT_CONTEXT@@KHHAEAV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@2@@Z; BuildCertToken(ushort const *,ushort const *,ushort const *,ATL::CCryptProv &,_CERT_CONTEXT const *,ulong,int,int,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> &)
0x18002bf5b  mov     [rsp+138h+arg_0], eax
0x18002bf62  mov     rcx, [rsp+138h+var_D0]
0x18002bf67  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x18002bf6b  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x18002bf70  mov     eax, [rsp+138h+arg_0]
0x18002bf77  test    eax, eax
0x18002bf79  jns     short loc_18002BFB9
0x18002bf7b  mov     dword ptr [rsp+138h+pvPara], eax
0x18002bf7f  lea     r9, aBuildcerttoken_0; "BuildCertToken failed with hr=0x%x"
0x18002bf86  mov     r8d, 13CEh; unsigned int
  ... truncated ...
```
