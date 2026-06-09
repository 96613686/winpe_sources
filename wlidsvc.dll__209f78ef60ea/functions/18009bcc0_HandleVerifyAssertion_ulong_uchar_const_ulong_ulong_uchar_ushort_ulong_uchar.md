# HandleVerifyAssertion(ulong,uchar const *,ulong *,ulong,uchar *,ushort * *,ulong *,uchar * *)

- ea: `0x18009bcc0`
- end: `0x18009c399`
- name: `?HandleVerifyAssertion@@YAJKPEBEPEAKKPEAEPEAPEAG1PEAPEAE@Z`
- size: `1753`
- prototype: `__int64 __usercall@<rax>(DWORD cbCertEncoded@<ecx>, BYTE *pbCertEncoded@<rdx>, unsigned int *@<r8>, unsigned int@<r9d>, unsigned __int8 *, unsigned __int16 **, unsigned int *, unsigned __int8 **)`
- caller_count: `1`
- callee_count: `18`
- tags: `service_task, broker_com_uri`

## callers

- `0x18009bb40`

## callees

- `0x18000c050`
- `0x18000ed04`
- `0x180013510`
- `0x1800151c4`
- `0x180019690`
- `0x18001a9c0`
- `0x18001ad00`
- `0x180026c18`
- `0x180030120`
- `0x180033218`
- `0x180035920`
- `0x180037e48`
- `0x18004ff98`
- `0x18009bcc0`
- `0x1800adb90`
- `0x1800c5604`
- `0x1800e2098`
- `0x1800f4ed0`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x18009c0db`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x18009c1ba`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x18009c0db`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x18009c1ba`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009be36`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009c2bd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009be36`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009c2bd`
- `CRYPT32!CertVerifySubjectCertificateContext` at `0x18009bf24`
- `CRYPT32!CertVerifySubjectCertificateContext` at `0x18009bf24`
- `CRYPT32!CertCreateCertificateContext` at `0x18009be19`
- `CRYPT32!CertCreateCertificateContext` at `0x18009be19`

## string_xrefs

- `0x18009bd1f`: `onecoreuap\ds\ext\live\identity\ntservice\lib\svccommon\svcapi.cpp`
- `0x18009bdcb`: `onecoreuap\ds\ext\live\identity\ntservice\lib\svccommon\svcapi.cpp`
- `0x18009be60`: `onecoreuap\ds\ext\live\identity\ntservice\lib\svccommon\svcapi.cpp`
- `0x18009bf70`: `onecoreuap\ds\ext\live\identity\ntservice\lib\svccommon\svcapi.cpp`
- `0x18009c2e7`: `onecoreuap\ds\ext\live\identity\ntservice\lib\svccommon\svcapi.cpp`
- `0x18009c354`: `onecoreuap\ds\ext\live\identity\ntservice\lib\svccommon\svcapi.cpp`
- `0x18009bdbe`: `VerifyCertificate: verifying already initialized failed with hr=0x%x`
- `0x18009be53`: `AssociateCert: failed to CertCreateCertificateContext 0x%X`
- `0x18009c15c`: `hr = StringCchCopyW(*pwszCID, wstrCID.GetLength() + 1, wstrCID.GetBuffer())`
- `0x18009c228`: `hr = SafeCopyMemory(*ppbCACert, pCACertContextLocal->cbCertEncoded, pCACertContextLocal->pbCertEncoded, pCACertContextLocal->cbCertEncoded)`

## pseudocode

```c
// Hidden C++ exception states: #wind=5 #try_helpers=1
__int64 __fastcall HandleVerifyAssertion(
        DWORD cbCertEncoded,
        BYTE *pbCertEncoded,
        unsigned int *a3,
        unsigned int a4,
        unsigned __int8 *a5,
        unsigned __int16 **a6,
        unsigned int *a7,
        unsigned __int8 **a8)
{
  unsigned int v12; // edi
  unsigned __int8 **v13; // r13
  int v14; // eax
  PCCERT_CONTEXT CertificateContext; // rax
  signed int LastError; // eax
  int v17; // edi
  int v18; // eax
  int SubjectName; // eax
  unsigned __int16 *v20; // rax
  unsigned __int16 **v21; // rdi
  const unsigned __int16 *Buffer; // rax
  int v23; // eax
  unsigned __int8 *v24; // rax
  int v25; // eax
  signed int v26; // eax
  unsigned int v27; // edi
  char *v29; // [rsp+20h] [rbp-C8h]
  char *v30; // [rsp+20h] [rbp-C8h]
  char *v31; // [rsp+20h] [rbp-C8h]
  __int64 v32; // [rsp+30h] [rbp-B8h] BYREF
  __int64 v33; // [rsp+38h] [rbp-B0h] BYREF
  void **v34; // [rsp+40h] [rbp-A8h] BYREF
  PCCERT_CONTEXT pSubject; // [rsp+48h] [rbp-A0h]
  void **v36; // [rsp+50h] [rbp-98h] BYREF
  PCCERT_CONTEXT pIssuer; // [rsp+58h] [rbp-90h]
  DWORD pdwFlags; // [rsp+60h] [rbp-88h] BYREF
  unsigned int v39; // [rsp+64h] [rbp-84h] BYREF
  int v40; // [rsp+68h] [rbp-80h]
  _QWORD v41[15]; // [rsp+70h] [rbp-78h] BYREF
  int IssuerCertificate; // [rsp+F8h] [rbp+10h] BYREF

  IssuerCertificate = 0;
  v40 = 0;
  v41[0] = "HandleVerifyAssertion";
  v41[1] = &IssuerCertificate;
  v41[2] = 0;
  v41[3] = 0;
  MsaTracingInternal::TraceFunctionEnter(
    (MsaTracingInternal *)"onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\svcapi.cpp",
    "HandleVerifyAssertion",
    (const char *)0x1A01,
    0,
    (const unsigned __int16 *)v29);
  if ( !pbCertEncoded || !a3 || (v12 = *a3) == 0 )
  {
    IssuerCertificate = -2147024809;
    TracePrintW(
      5u,
      "onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\svcapi.cpp",
      0x1A06u,
      L"pCert context passed to VerifyCertificate is nullptr, or pdwTTL is nullptr or 0.");
    goto LABEL_36;
  }
  v39 = *a3;
  *a3 = 0;
  *a7 = 0;
  v13 = a8;
  *a8 = 0;
  pSubject = 0;
  v34 = &SmartPCCERT_CONTEXT::`vftable';
  pIssuer = 0;
  v36 = &SmartPCCERT_CONTEXT::`vftable';
  ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v33);
  ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v32);
  v14 = CPassportClientLibrary::VerifyInitialized(g_pPPCRL);
  IssuerCertificate = v14;
  if ( v14 < 0 )
  {
    LODWORD(v30) = v14;
    TracePrintW(
      5u,
      "onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\svcapi.cpp",
      0x1A1Du,
      L"VerifyCertificate: verifying already initialized failed with hr=0x%x",
      v30);
    ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v32);
    ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v33);
    SmartPCCERT_CONTEXT::~SmartPCCERT_CONTEXT((SmartPCCERT_CONTEXT *)&v36);
    SmartPCCERT_CONTEXT::~SmartPCCERT_CONTEXT((SmartPCCERT_CONTEXT *)&v34);
    goto LABEL_36;
  }
  CertificateContext = CertCreateCertificateContext(0x10001u, pbCertEncoded, cbCertEncoded);
  SmartPtr<void *>::Attach(&v34, CertificateContext);
  if ( !pSubject )
  {
    LastError = GetLastError();
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
    IssuerCertificate = LastError;
    LODWORD(v30) = LastError;
    TracePrintW(
      5u,
      "onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\svcapi.cpp",
      0x1A28u,
      L"AssociateCert: failed to CertCreateCertificateContext 0x%X",
      v30);
    ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v32);
    ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v33);
    SmartPCCERT_CONTEXT::~SmartPCCERT_CONTEXT((SmartPCCERT_CONTEXT *)&v36);
    SmartPCCERT_CONTEXT::~SmartPCCERT_CONTEXT((SmartPCCERT_CONTEXT *)&v34);
    goto LABEL_36;
  }
  IssuerCertificate = GetIssuerCertificate(pSubject, 0, (struct SmartPCCERT_CONTEXT *)&v36);
  if ( IssuerCertificate < 0 )
  {
    IssuerCertificate = GetIssuerCertificate(pSubject, 1, (struct SmartPCCERT_CONTEXT *)&v36);
    if ( IssuerCertificate >= 0 )
      IssuerCertificate = -2147186540;
    goto LABEL_13;
  }
  pdwFlags = 1;
  if ( CertVerifySubjectCertificateContext(pSubject, pIssuer, &pdwFlags) && !pdwFlags )
  {
    IssuerCertificate = 0;
    v17 = CCertObject::CheckCertTTL(pSubject, v12, &v39);
    v40 = v17;
    LODWORD(v30) = v17;
    TracePrintW(
      2u,
      "onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\svcapi.cpp",
      0x1A4Fu,
      L"CheckCertTTL returned 0x%x.",
      v30);
    if ( v17 < 0 )
    {
      IssuerCertificate = v17;
      ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v32);
      ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v33);
      SmartPCCERT_CONTEXT::~SmartPCCERT_CONTEXT((SmartPCCERT_CONTEXT *)&v36);
      SmartPCCERT_CONTEXT::~SmartPCCERT_CONTEXT((SmartPCCERT_CONTEXT *)&v34);
      goto LABEL_36;
    }
    *a3 = v39;
    if ( a5 )
    {
      if ( a4 )
      {
        v18 = WlidsvcUtil::VerifyPOPMessage(pSubject, a5, a4);
        IssuerCertificate = v18;
        if ( v18 < 0 )
        {
          LODWORD(v31) = v18;
          TracePrintW(
            2u,
            "onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\svcapi.cpp",
            0x1A5Fu,
            L"POP verification failed with 0x%x.",
            v31);
          IssuerCertificate = -2147186560;
          ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v32);
          ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v33);
          SmartPCCERT_CONTEXT::~SmartPCCERT_CONTEXT((SmartPCCERT_CONTEXT *)&v36);
          SmartPCCERT_CONTEXT::~SmartPCCERT_CONTEXT((SmartPCCERT_CONTEXT *)&v34);
          goto LABEL_36;
        }
      }
    }
    SubjectName = CertGetSubjectName(pSubject);
    IssuerCertificate = SubjectName;
    if ( SubjectName < 0 )
    {
      Telemetry::IfFailExit(
        "onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\svcapi.cpp",
        "HandleVerifyAssertion",
        0x1A66u,
        SubjectName,
        "hr = CertGetSubjectName(pCertContext, strCID)");
      ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v32);
      ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v33);
      SmartPCCERT_CONTEXT::~SmartPCCERT_CONTEXT((SmartPCCERT_CONTEXT *)&v36);
      SmartPCCERT_CONTEXT::~SmartPCCERT_CONTEXT((SmartPCCERT_CONTEXT *)&v34);
      goto LABEL_36;
    }
    ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::operator=(
      &v32,
      v33);
    v20 = (unsigned __int16 *)malloc(2LL * (*(_DWORD *)(v32 - 16) + 1));
    v21 = a6;
    *a6 = v20;
    if ( !v20 )
      goto LABEL_25;
    Buffer = (const unsigned __int16 *)ATL::CSimpleStringT<unsigned short,0>::GetBuffer(&v32);
    v23 = StringCchCopyW(*v21, *(_DWORD *)(v32 - 16) + 1, Buffer);
    IssuerCertificate = v23;
    if ( v23 < 0 )
    {
      Telemetry::IfFailExit(
        "onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\svcapi.cpp",
        "HandleVerifyAssertion",
        0x1A6Au,
        v23,
        "hr = StringCchCopyW(*pwszCID, wstrCID.GetLength() + 1, wstrCID.GetBuffer())");
      ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v32);
      ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v33);
      SmartPCCERT_CONTEXT::~SmartPCCERT_CONTEXT((SmartPCCERT_CONTEXT *)&v36);
      SmartPCCERT_CONTEXT::~SmartPCCERT_CONTEXT((SmartPCCERT_CONTEXT *)&v34);
      goto LABEL_36;
    }
    v24 = (unsigned __int8 *)malloc(pIssuer->cbCertEncoded);
    *v13 = v24;
    if ( !v24 )
    {
LABEL_25:
      IssuerCertificate = -2147024882;
      ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v32);
      ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v33);
      SmartPCCERT_CONTEXT::~SmartPCCERT_CONTEXT((SmartPCCERT_CONTEXT *)&v36);
      SmartPCCERT_CONTEXT::~SmartPCCERT_CONTEXT((SmartPCCERT_CONTEXT *)&v34);
      goto LABEL_36;
    }
    v25 = SafeCopyMemory(v24, pIssuer->cbCertEncoded, pIssuer->pbCertEncoded, pIssuer->cbCertEncoded);
    IssuerCertificate = v25;
    if ( v25 >= 0 )
      *a7 = pIssuer->cbCertEncoded;
    else
      Telemetry::IfFailExit(
        "onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\svcapi.cpp",
        "HandleVerifyAssertion",
        0x1A6Fu,
        v25,
        "hr = SafeCopyMemory(*ppbCACert, pCACertContextLocal->cbCertEncoded, pCACertContextLocal->pbCertEncoded, pCACertC"
        "ontextLocal->cbCertEncoded)");
LABEL_13:
    ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v32);
    ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v33);
    SmartPCCERT_CONTEXT::~SmartPCCERT_CONTEXT((SmartPCCERT_CONTEXT *)&v36);
    SmartPCCERT_CONTEXT::~SmartPCCERT_CONTEXT((SmartPCCERT_CONTEXT *)&v34);
    goto LABEL_36;
  }
  v26 = GetLastError();
  if ( v26 > 0 )
    v26 = (unsigned __int16)v26 | 0x80070000;
  IssuerCertificate = v26;
  LODWORD(v30) = v26;
  TracePrintW(
    5u,
    "onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\svcapi.cpp",
    0x1A43u,
    L"VerifyCertificate: CertVerifySubjectCertificateContext failed with hr=0x%x",
    v30);
  IssuerCertificate = -2147186570;
  ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v32);
  ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v33);
  SmartPCCERT_CONTEXT::~SmartPCCERT_CONTEXT((SmartPCCERT_CONTEXT *)&v36);
  SmartPCCERT_CONTEXT::~SmartPCCERT_CONTEXT((SmartPCCERT_CONTEXT *)&v34);
LABEL_36:
  v27 = IssuerCertificate;
  if ( !IssuerCertificate )
  {
    v27 = v40;
    IssuerCertificate = v40;
  }
  CTraceFuncW<long>::~CTraceFuncW<long>((__int64)v41);
  return v27;
}

```

## disassembly

```asm
0x18009bcc0  mov     r11, rsp
0x18009bcc3  push    rsi
0x18009bcc4  push    rdi
0x18009bcc5  push    r12
0x18009bcc7  push    r13
0x18009bcc9  push    r14
0x18009bccb  push    r15
0x18009bccd  sub     rsp, 0B8h
0x18009bcd4  mov     r12d, r9d
0x18009bcd7  mov     rsi, r8
0x18009bcda  mov     r14, rdx
0x18009bcdd  mov     r15d, ecx
0x18009bce0  mov     dword ptr [r11+10h], 0
0x18009bce8  mov     [rsp+0E8h+var_80], 0
0x18009bcf0  lea     rcx, aHandleverifyas; "HandleVerifyAssertion"
0x18009bcf7  mov     [r11-78h], rcx
0x18009bcfb  lea     rax, [r11+10h]
0x18009bcff  mov     [r11-70h], rax
0x18009bd03  mov     qword ptr [r11-68h], 0
0x18009bd0b  mov     qword ptr [r11-60h], 0
0x18009bd13  xor     r9d, r9d; unsigned int
0x18009bd16  mov     r8d, 1A01h; char *
0x18009bd1c  mov     rdx, rcx; char *
0x18009bd1f  lea     rcx, aOnecoreuapDsEx_11; "onecoreuap\\ds\\ext\\live\\identity\\nt"...
0x18009bd26  call    ?TraceFunctionEnter@MsaTracingInternal@@YAKPEBD0KPEBG@Z; MsaTracingInternal::TraceFunctionEnter(char const *,char const *,ulong,ushort const *)
0x18009bd2b  nop
0x18009bd2c  test    r14, r14
0x18009bd2f  jz      loc_18009C33C
0x18009bd35  test    rsi, rsi
0x18009bd38  jz      loc_18009C33C
0x18009bd3e  mov     edi, [rsi]
0x18009bd40  test    edi, edi
0x18009bd42  jz      loc_18009C33C
0x18009bd48  mov     [rsp+0E8h+var_84], edi
0x18009bd4c  mov     dword ptr [rsi], 0
0x18009bd52  mov     rax, [rsp+0E8h+arg_30]
0x18009bd5a  mov     dword ptr [rax], 0
0x18009bd60  mov     r13, [rsp+0E8h+arg_38]
0x18009bd68  mov     qword ptr [r13+0], 0
0x18009bd70  xor     eax, eax
0x18009bd72  mov     [rsp+0E8h+pSubject], rax
0x18009bd77  lea     rcx, ??_7SmartPCCERT_CONTEXT@@6B@; const SmartPCCERT_CONTEXT::`vftable'
0x18009bd7e  mov     [rsp+0E8h+var_A8], rcx
0x18009bd83  mov     [rsp+0E8h+pIssuer], rax
0x18009bd88  mov     [rsp+0E8h+var_98], rcx
0x18009bd8d  lea     rcx, [rsp+0E8h+var_B0]
0x18009bd92  call    ??0?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(void)
0x18009bd97  nop
0x18009bd98  lea     rcx, [rsp+0E8h+var_B8]
0x18009bd9d  call    ??0?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(void)
0x18009bda2  nop
0x18009bda3  mov     rcx, cs:?g_pPPCRL@@3PEAVCPassportClientLibrary@@EA; this
0x18009bdaa  call    ?VerifyInitialized@CPassportClientLibrary@@QEBAJXZ; CPassportClientLibrary::VerifyInitialized(void)
0x18009bdaf  mov     [rsp+0E8h+arg_8], eax
0x18009bdb6  test    eax, eax
0x18009bdb8  jns     short loc_18009BE0E
0x18009bdba  mov     dword ptr [rsp+0E8h+var_C8], eax
0x18009bdbe  lea     r9, aVerifycertific; "VerifyCertificate: verifying already in"...
0x18009bdc5  mov     r8d, 1A1Dh; unsigned int
0x18009bdcb  lea     rdx, aOnecoreuapDsEx_11; "onecoreuap\\ds\\ext\\live\\identity\\nt"...
0x18009bdd2  mov     ecx, 5; unsigned __int8
0x18009bdd7  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x18009bddc  nop
0x18009bddd  lea     rcx, [rsp+0E8h+var_B8]
0x18009bde2  call    ??1?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(void)
0x18009bde7  nop
0x18009bde8  lea     rcx, [rsp+0E8h+var_B0]
0x18009bded  call    ??1?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(void)
0x18009bdf2  nop
0x18009bdf3  lea     rcx, [rsp+0E8h+var_98]; this
0x18009bdf8  call    ??1SmartPCCERT_CONTEXT@@UEAA@XZ; SmartPCCERT_CONTEXT::~SmartPCCERT_CONTEXT(void)
0x18009bdfd  nop
0x18009bdfe  lea     rcx, [rsp+0E8h+var_A8]; this
0x18009be03  call    ??1SmartPCCERT_CONTEXT@@UEAA@XZ; SmartPCCERT_CONTEXT::~SmartPCCERT_CONTEXT(void)
0x18009be08  nop
0x18009be09  jmp     loc_18009C365
0x18009be0e  mov     r8d, r15d; cbCertEncoded
0x18009be11  mov     rdx, r14; pbCertEncoded
0x18009be14  mov     ecx, 10001h; dwCertEncodingType
0x18009be19  call    cs:__imp_CertCreateCertificateContext
0x18009be1f  mov     rdx, rax
0x18009be22  lea     rcx, [rsp+0E8h+var_A8]
0x18009be27  call    ?Attach@?$SmartPtr@PEAX@@QEAAXPEAX@Z; SmartPtr<void *>::Attach(void *)
0x18009be2c  mov     rcx, [rsp+0E8h+pSubject]; struct _CERT_CONTEXT *
0x18009be31  test    rcx, rcx
0x18009be34  jnz     short loc_18009BEA3
0x18009be36  call    cs:__imp_GetLastError
0x18009be3c  test    eax, eax
0x18009be3e  jle     short loc_18009BE48
0x18009be40  movzx   eax, ax
0x18009be43  or      eax, 80070000h
0x18009be48  mov     [rsp+0E8h+arg_8], eax
0x18009be4f  mov     dword ptr [rsp+0E8h+var_C8], eax
0x18009be53  lea     r9, aAssociatecertF; "AssociateCert: failed to CertCreateCert"...
0x18009be5a  mov     r8d, 1A28h; unsigned int
0x18009be60  lea     rdx, aOnecoreuapDsEx_11; "onecoreuap\\ds\\ext\\live\\identity\\nt"...
0x18009be67  mov     ecx, 5; unsigned __int8
0x18009be6c  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x18009be71  nop
0x18009be72  lea     rcx, [rsp+0E8h+var_B8]
0x18009be77  call    ??1?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(void)
0x18009be7c  nop
0x18009be7d  lea     rcx, [rsp+0E8h+var_B0]
0x18009be82  call    ??1?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(void)
0x18009be87  nop
0x18009be88  lea     rcx, [rsp+0E8h+var_98]; this
0x18009be8d  call    ??1SmartPCCERT_CONTEXT@@UEAA@XZ; SmartPCCERT_CONTEXT::~SmartPCCERT_CONTEXT(void)
0x18009be92  nop
0x18009be93  lea     rcx, [rsp+0E8h+var_A8]; this
0x18009be98  call    ??1SmartPCCERT_CONTEXT@@UEAA@XZ; SmartPCCERT_CONTEXT::~SmartPCCERT_CONTEXT(void)
0x18009be9d  nop
0x18009be9e  jmp     loc_18009C365
0x18009bea3  lea     r8, [rsp+0E8h+var_98]; struct SmartPCCERT_CONTEXT *
0x18009bea8  xor     edx, edx; bool
0x18009beaa  call    ?GetIssuerCertificate@@YAJPEBU_CERT_CONTEXT@@_NAEAVSmartPCCERT_CONTEXT@@@Z; GetIssuerCertificate(_CERT_CONTEXT const *,bool,SmartPCCERT_CONTEXT &)
0x18009beaf  mov     [rsp+0E8h+arg_8], eax
0x18009beb6  mov     rcx, [rsp+0E8h+pSubject]; struct _CERT_CONTEXT *
0x18009bebb  test    eax, eax
0x18009bebd  jns     short loc_18009BF12
0x18009bebf  lea     r8, [rsp+0E8h+var_98]; struct SmartPCCERT_CONTEXT *
0x18009bec4  mov     dl, 1; bool
0x18009bec6  call    ?GetIssuerCertificate@@YAJPEBU_CERT_CONTEXT@@_NAEAVSmartPCCERT_CONTEXT@@@Z; GetIssuerCertificate(_CERT_CONTEXT const *,bool,SmartPCCERT_CONTEXT &)
0x18009becb  mov     [rsp+0E8h+arg_8], eax
0x18009bed2  test    eax, eax
0x18009bed4  js      short loc_18009BEE1
0x18009bed6  mov     [rsp+0E8h+arg_8], 80048894h
0x18009bee1  lea     rcx, [rsp+0E8h+var_B8]
0x18009bee6  call    ??1?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(void)
0x18009beeb  nop
0x18009beec  lea     rcx, [rsp+0E8h+var_B0]
0x18009bef1  call    ??1?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(void)
0x18009bef6  nop
0x18009bef7  lea     rcx, [rsp+0E8h+var_98]; this
0x18009befc  call    ??1SmartPCCERT_CONTEXT@@UEAA@XZ; SmartPCCERT_CONTEXT::~SmartPCCERT_CONTEXT(void)
0x18009bf01  nop
0x18009bf02  lea     rcx, [rsp+0E8h+var_A8]; this
0x18009bf07  call    ??1SmartPCCERT_CONTEXT@@UEAA@XZ; SmartPCCERT_CONTEXT::~SmartPCCERT_CONTEXT(void)
0x18009bf0c  nop
0x18009bf0d  jmp     loc_18009C365
0x18009bf12  mov     [rsp+0E8h+pdwFlags], 1
0x18009bf1a  lea     r8, [rsp+0E8h+pdwFlags]; pdwFlags
0x18009bf1f  mov     rdx, [rsp+0E8h+pIssuer]; pIssuer
0x18009bf24  call    cs:__imp_CertVerifySubjectCertificateContext
0x18009bf2a  test    eax, eax
0x18009bf2c  jz      loc_18009C2BD
0x18009bf32  cmp     [rsp+0E8h+pdwFlags], 0
0x18009bf37  jnz     loc_18009C2BD
0x18009bf3d  mov     [rsp+0E8h+arg_8], 0
0x18009bf48  lea     r8, [rsp+0E8h+var_84]; unsigned int *
0x18009bf4d  mov     edx, edi; unsigned int
0x18009bf4f  mov     rcx, [rsp+0E8h+pSubject]; struct _CERT_CONTEXT *
0x18009bf54  call    ?CheckCertTTL@CCertObject@@SAJPEBU_CERT_CONTEXT@@KAEAK@Z; CCertObject::CheckCertTTL(_CERT_CONTEXT const *,ulong,ulong &)
0x18009bf59  mov     edi, eax
0x18009bf5b  mov     [rsp+0E8h+var_80], eax
0x18009bf5f  mov     dword ptr [rsp+0E8h+var_C8], eax
0x18009bf63  lea     r9, aCheckcertttlRe; "CheckCertTTL returned 0x%x."
0x18009bf6a  mov     r8d, 1A4Fh; unsigned int
0x18009bf70  lea     r14, aOnecoreuapDsEx_11; "onecoreuap\\ds\\ext\\live\\identity\\nt"...
0x18009bf77  mov     rdx, r14; char *
0x18009bf7a  mov     r15d, 2
0x18009bf80  mov     ecx, r15d; unsigned __int8
0x18009bf83  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x18009bf88  test    edi, edi
0x18009bf8a  jns     short loc_18009BFC4
0x18009bf8c  mov     [rsp+0E8h+arg_8], edi
0x18009bf93  lea     rcx, [rsp+0E8h+var_B8]
0x18009bf98  call    ??1?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(void)
0x18009bf9d  nop
0x18009bf9e  lea     rcx, [rsp+0E8h+var_B0]
0x18009bfa3  call    ??1?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(void)
0x18009bfa8  nop
0x18009bfa9  lea     rcx, [rsp+0E8h+var_98]; this
0x18009bfae  call    ??1SmartPCCERT_CONTEXT@@UEAA@XZ; SmartPCCERT_CONTEXT::~SmartPCCERT_CONTEXT(void)
0x18009bfb3  nop
0x18009bfb4  lea     rcx, [rsp+0E8h+var_A8]; this
0x18009bfb9  call    ??1SmartPCCERT_CONTEXT@@UEAA@XZ; SmartPCCERT_CONTEXT::~SmartPCCERT_CONTEXT(void)
0x18009bfbe  nop
0x18009bfbf  jmp     loc_18009C365
0x18009bfc4  mov     eax, [rsp+0E8h+var_84]
0x18009bfc8  mov     [rsi], eax
0x18009bfca  mov     rdx, [rsp+0E8h+arg_20]; unsigned __int8 *
0x18009bfd2  test    rdx, rdx
0x18009bfd5  jz      short loc_18009C04C
0x18009bfd7  test    r12d, r12d
0x18009bfda  jz      short loc_18009C04C
0x18009bfdc  mov     r8d, r12d; unsigned int
0x18009bfdf  mov     rcx, [rsp+0E8h+pSubject]; struct _CERT_CONTEXT *
0x18009bfe4  call    ?VerifyPOPMessage@WlidsvcUtil@@SAJPEBU_CERT_CONTEXT@@PEAEK@Z; WlidsvcUtil::VerifyPOPMessage(_CERT_CONTEXT const *,uchar *,ulong)
0x18009bfe9  mov     [rsp+0E8h+arg_8], eax
0x18009bff0  test    eax, eax
0x18009bff2  jns     short loc_18009C04C
0x18009bff4  mov     dword ptr [rsp+0E8h+var_C8], eax
0x18009bff8  lea     r9, aPopVerificatio; "POP verification failed with 0x%x."
0x18009bfff  mov     r8d, 1A5Fh; unsigned int
0x18009c005  mov     rdx, r14; char *
0x18009c008  mov     ecx, r15d; unsigned __int8
0x18009c00b  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x18009c010  mov     [rsp+0E8h+arg_8], 80048880h
0x18009c01b  lea     rcx, [rsp+0E8h+var_B8]
0x18009c020  call    ??1?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(void)
0x18009c025  nop
0x18009c026  lea     rcx, [rsp+0E8h+var_B0]
0x18009c02b  call    ??1?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(void)
0x18009c030  nop
0x18009c031  lea     rcx, [rsp+0E8h+var_98]; this
0x18009c036  call    ??1SmartPCCERT_CONTEXT@@UEAA@XZ; SmartPCCERT_CONTEXT::~SmartPCCERT_CONTEXT(void)
0x18009c03b  nop
0x18009c03c  lea     rcx, [rsp+0E8h+var_A8]; this
0x18009c041  call    ??1SmartPCCERT_CONTEXT@@UEAA@XZ; SmartPCCERT_CONTEXT::~SmartPCCERT_CONTEXT(void)
0x18009c046  nop
0x18009c047  jmp     loc_18009C365
0x18009c04c  lea     rdx, [rsp+0E8h+var_B0]
0x18009c051  mov     rcx, [rsp+0E8h+pSubject]; pCertContext
0x18009c056  call    ?CertGetSubjectName@@YAJPEBU_CERT_CONTEXT@@AEAV?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@@Z; CertGetSubjectName(_CERT_CONTEXT const *,ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>> &)
0x18009c05b  mov     [rsp+0E8h+arg_8], eax
0x18009c062  test    eax, eax
0x18009c064  jns     short loc_18009C0BC
0x18009c066  lea     rcx, aHrCertgetsubje_0; "hr = CertGetSubjectName(pCertContext, s"...
0x18009c06d  mov     [rsp+0E8h+var_C8], rcx; char *
0x18009c072  mov     r9d, eax; int
0x18009c075  mov     r8d, 1A66h; unsigned int
0x18009c07b  lea     rdx, aHandleverifyas; "HandleVerifyAssertion"
0x18009c082  mov     rcx, r14; char *
0x18009c085  call    ?IfFailExit@Telemetry@@SAXPEBD0KJ0@Z; Telemetry::IfFailExit(char const *,char const *,ulong,long,char const *)
0x18009c08a  nop
0x18009c08b  lea     rcx, [rsp+0E8h+var_B8]
0x18009c090  call    ??1?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(void)
0x18009c095  nop
0x18009c096  lea     rcx, [rsp+0E8h+var_B0]
0x18009c09b  call    ??1?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(void)
0x18009c0a0  nop
0x18009c0a1  lea     rcx, [rsp+0E8h+var_98]; this
0x18009c0a6  call    ??1SmartPCCERT_CONTEXT@@UEAA@XZ; SmartPCCERT_CONTEXT::~SmartPCCERT_CONTEXT(void)
0x18009c0ab  nop
0x18009c0ac  lea     rcx, [rsp+0E8h+var_A8]; this
0x18009c0b1  call    ??1SmartPCCERT_CONTEXT@@UEAA@XZ; SmartPCCERT_CONTEXT::~SmartPCCERT_CONTEXT(void)
0x18009c0b6  nop
0x18009c0b7  jmp     loc_18009C365
0x18009c0bc  mov     rdx, [rsp+0E8h+var_B0]
0x18009c0c1  lea     rcx, [rsp+0E8h+var_B8]
0x18009c0c6  call    ??4?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAAEAV01@PEBD@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::operator=(char const *)
0x18009c0cb  mov     rax, [rsp+0E8h+var_B8]
0x18009c0d0  mov     ecx, [rax-10h]
0x18009c0d3  inc     ecx
0x18009c0d5  movsxd  rcx, ecx
0x18009c0d8  add     rcx, rcx; Size
0x18009c0db  call    cs:__imp_malloc
0x18009c0e1  mov     rdi, [rsp+0E8h+arg_28]
0x18009c0e9  mov     [rdi], rax
0x18009c0ec  test    rax, rax
0x18009c0ef  jnz     short loc_18009C12D
0x18009c0f1  mov     [rsp+0E8h+arg_8], 8007000Eh
0x18009c0fc  lea     rcx, [rsp+0E8h+var_B8]
0x18009c101  call    ??1?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(void)
0x18009c106  nop
0x18009c107  lea     rcx, [rsp+0E8h+var_B0]
0x18009c10c  call    ??1?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(void)
0x18009c111  nop
0x18009c112  lea     rcx, [rsp+0E8h+var_98]; this
0x18009c117  call    ??1SmartPCCERT_CONTEXT@@UEAA@XZ; SmartPCCERT_CONTEXT::~SmartPCCERT_CONTEXT(void)
0x18009c11c  nop
0x18009c11d  lea     rcx, [rsp+0E8h+var_A8]; this
0x18009c122  call    ??1SmartPCCERT_CONTEXT@@UEAA@XZ; SmartPCCERT_CONTEXT::~SmartPCCERT_CONTEXT(void)
0x18009c127  nop
0x18009c128  jmp     loc_18009C365
0x18009c12d  lea     rcx, [rsp+0E8h+var_B8]
0x18009c132  call    ?GetBuffer@?$CSimpleStringT@G$0A@@ATL@@QEAAPEAGXZ; ATL::CSimpleStringT<ushort,0>::GetBuffer(void)
0x18009c137  mov     rdx, [rsp+0E8h+var_B8]
0x18009c13c  mov     r8d, [rdx-10h]
0x18009c140  inc     r8d
0x18009c143  movsxd  rdx, r8d; unsigned __int64
0x18009c146  mov     r8, rax; unsigned __int16 *
0x18009c149  mov     rcx, [rdi]; unsigned __int16 *
0x18009c14c  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18009c151  mov     [rsp+0E8h+arg_8], eax
0x18009c158  test    eax, eax
0x18009c15a  jns     short loc_18009C1B2
0x18009c15c  lea     rcx, aHrStringcchcop_50; "hr = StringCchCopyW(*pwszCID, wstrCID.G"...
0x18009c163  mov     [rsp+0E8h+var_C8], rcx; char *
0x18009c168  mov     r9d, eax; int
0x18009c16b  mov     r8d, 1A6Ah; unsigned int
0x18009c171  lea     rdx, aHandleverifyas; "HandleVerifyAssertion"
0x18009c178  mov     rcx, r14; char *
0x18009c17b  call    ?IfFailExit@Telemetry@@SAXPEBD0KJ0@Z; Telemetry::IfFailExit(char const *,char const *,ulong,long,char const *)
0x18009c180  nop
0x18009c181  lea     rcx, [rsp+0E8h+var_B8]
0x18009c186  call    ??1?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(void)
0x18009c18b  nop
0x18009c18c  lea     rcx, [rsp+0E8h+var_B0]
0x18009c191  call    ??1?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(void)
0x18009c196  nop
0x18009c197  lea     rcx, [rsp+0E8h+var_98]; this
0x18009c19c  call    ??1SmartPCCERT_CONTEXT@@UEAA@XZ; SmartPCCERT_CONTEXT::~SmartPCCERT_CONTEXT(void)
0x18009c1a1  nop
0x18009c1a2  lea     rcx, [rsp+0E8h+var_A8]; this
0x18009c1a7  call    ??1SmartPCCERT_CONTEXT@@UEAA@XZ; SmartPCCERT_CONTEXT::~SmartPCCERT_CONTEXT(void)
0x18009c1ac  nop
0x18009c1ad  jmp     loc_18009C365
0x18009c1b2  mov     rax, [rsp+0E8h+pIssuer]
0x18009c1b7  mov     ecx, [rax+10h]; Size
  ... truncated ...
```
