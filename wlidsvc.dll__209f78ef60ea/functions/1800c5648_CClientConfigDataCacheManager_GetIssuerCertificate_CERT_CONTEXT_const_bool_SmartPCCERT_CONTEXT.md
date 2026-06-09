# CClientConfigDataCacheManager::GetIssuerCertificate(_CERT_CONTEXT const *,bool,SmartPCCERT_CONTEXT &)

- ea: `0x1800c5648`
- end: `0x1800c5a66`
- name: `?GetIssuerCertificate@CClientConfigDataCacheManager@@QEAAJPEBU_CERT_CONTEXT@@_NAEAVSmartPCCERT_CONTEXT@@@Z`
- size: `1054`
- prototype: `int(CClientConfigDataCacheManager *__hidden this, const struct _CERT_CONTEXT *, bool, struct SmartPCCERT_CONTEXT *)`
- caller_count: `1`
- callee_count: `11`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1800c5604`

## callees

- `0x18000c050`
- `0x18000ed04`
- `0x1800151c4`
- `0x180019690`
- `0x18001a530`
- `0x18001a9c0`
- `0x180033218`
- `0x18004ff98`
- `0x1800c5648`
- `0x1800f352c`
- `0x180128010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c58b7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c5943`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c5982`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c58b7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c5943`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c5982`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1800c56e3`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1800c5a25`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1800c56e3`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1800c5a25`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800c56b9`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800c56f0`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800c56b9`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800c56f0`
- `CRYPT32!CertVerifySubjectCertificateContext` at `0x1800c58a3`
- `CRYPT32!CertVerifySubjectCertificateContext` at `0x1800c58a3`
- `CRYPT32!CertGetIssuerCertificateFromStore` at `0x1800c57ce`
- `CRYPT32!CertGetIssuerCertificateFromStore` at `0x1800c57ce`
- `CRYPT32!CertDuplicateCertificateContext` at `0x1800c5878`
- `CRYPT32!CertDuplicateCertificateContext` at `0x1800c5878`

## string_xrefs

- `0x1800c5721`: `onecoreuap\ds\ext\live\identity\ntservice\lib\svccommon\clientconfig.cpp`
- `0x1800c5821`: `onecoreuap\ds\ext\live\identity\ntservice\lib\svccommon\clientconfig.cpp`
- `0x1800c584f`: `onecoreuap\ds\ext\live\identity\ntservice\lib\svccommon\clientconfig.cpp`
- `0x1800c58dd`: `onecoreuap\ds\ext\live\identity\ntservice\lib\svccommon\clientconfig.cpp`
- `0x1800c5919`: `onecoreuap\ds\ext\live\identity\ntservice\lib\svccommon\clientconfig.cpp`
- `0x1800c5969`: `onecoreuap\ds\ext\live\identity\ntservice\lib\svccommon\clientconfig.cpp`
- `0x1800c59c2`: `onecoreuap\ds\ext\live\identity\ntservice\lib\svccommon\clientconfig.cpp`
- `0x1800c59f6`: `onecoreuap\ds\ext\live\identity\ntservice\lib\svccommon\clientconfig.cpp`
- `0x1800c570b`: `CClientConfigDataCacheManager::GetIssuerCertificate`
- `0x1800c59e6`: `CClientConfigDataCacheManager::GetIssuerCertificate`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall CClientConfigDataCacheManager::GetIssuerCertificate(
        HANDLE *this,
        const struct _CERT_CONTEXT *a2,
        char a3,
        struct SmartPCCERT_CONTEXT *a4)
{
  volatile signed __int32 *v7; // rdi
  volatile signed __int32 *v8; // rbx
  int v9; // r9d
  const char *v10; // rax
  unsigned int v11; // r8d
  char v12; // r14
  void *v13; // rdi
  PCCERT_CONTEXT v14; // rax
  const CERT_CONTEXT *v15; // r8
  PCCERT_CONTEXT IssuerCertificateFromStore; // rax
  PCCERT_CONTEXT v17; // rax
  const CERT_CONTEXT *v18; // rcx
  signed int v19; // eax
  signed int v20; // eax
  signed int LastError; // eax
  unsigned int v22; // ecx
  unsigned int v23; // edi
  char *v25; // [rsp+20h] [rbp-69h]
  __int64 v26; // [rsp+28h] [rbp-61h]
  DWORD v27; // [rsp+40h] [rbp-49h] BYREF
  _QWORD v28[2]; // [rsp+48h] [rbp-41h] BYREF
  void **v29; // [rsp+58h] [rbp-31h] BYREF
  PCCERT_CONTEXT pCertContext; // [rsp+60h] [rbp-29h]
  void **v31; // [rsp+68h] [rbp-21h] BYREF
  PCCERT_CONTEXT pPrevIssuerContext; // [rsp+70h] [rbp-19h]
  _QWORD v33[2]; // [rsp+78h] [rbp-11h] BYREF
  const char *v34[11]; // [rsp+88h] [rbp-1h] BYREF
  int v35; // [rsp+F0h] [rbp+67h] BYREF
  DWORD pdwFlags; // [rsp+F8h] [rbp+6Fh] BYREF
  char v37; // [rsp+100h] [rbp+77h]

  v37 = a3;
  v35 = 0;
  pCertContext = 0;
  v29 = &SmartPCCERT_CONTEXT::`vftable';
  pPrevIssuerContext = 0;
  v31 = &SmartPCCERT_CONTEXT::`vftable';
  v33[1] = 0;
  v33[0] = &SmartPCCERT_CONTEXT::`vftable';
  v28[1] = this + 104;
  v7 = (volatile signed __int32 *)this + 211;
  do
  {
    if ( *((int *)this + 210) > 0 )
    {
      v8 = v7;
      if ( WaitForSingleObject(this[107], 0xFFFFFFFF) )
        break;
    }
    v7 = (volatile signed __int32 *)this + 211;
    _InterlockedIncrement((volatile signed __int32 *)this + 211);
    v8 = (volatile signed __int32 *)this + 211;
    if ( *((int *)this + 210) <= 0 )
      break;
    if ( _InterlockedExchangeAdd(v7, 0xFFFFFFFF) == 1 )
      SetEvent(this[106]);
  }
  while ( !WaitForSingleObject(this[107], 0xFFFFFFFF) );
  CTraceFuncW<long>::CTraceFuncW<long>(
    v34,
    "onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\clientconfig.cpp",
    2416,
    (const char *)&v35,
    "CClientConfigDataCacheManager::GetIssuerCertificate",
    L"pCertContext: 0x%p",
    a2);
  if ( !a2 )
  {
    v9 = -2147024809;
    v10 = "pCertContext != nullptr";
    v11 = 2419;
LABEL_33:
    v35 = v9;
    Telemetry::IfFailExit(
      "onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\clientconfig.cpp",
      "CClientConfigDataCacheManager::GetIssuerCertificate",
      v11,
      v9,
      v10);
    goto LABEL_34;
  }
  v8 = (volatile signed __int32 *)this + 211;
  v12 = v37;
  v13 = *(HANDLE *)((char *)this + (v37 != 0 ? 0x18 : 0) + 912);
  if ( !v13 )
  {
    v9 = -2147186569;
    v10 = "hCertStore != nullptr";
    v11 = 2433;
    goto LABEL_33;
  }
  (*(void (__fastcall **)(struct SmartPCCERT_CONTEXT *))(*(_QWORD *)a4 + 8LL))(a4);
  v14 = pCertContext;
  do
  {
    pdwFlags = 1;
    pCertContext = 0;
    SmartPtr<void *>::Attach(&v31, v14);
    v15 = pPrevIssuerContext;
    pPrevIssuerContext = 0;
    IssuerCertificateFromStore = CertGetIssuerCertificateFromStore(v13, a2, v15, &pdwFlags);
    SmartPtr<void *>::Attach(&v29, IssuerCertificateFromStore);
    if ( !pCertContext )
    {
      LastError = GetLastError();
      v22 = LastError;
      if ( LastError > 0 )
        v22 = (unsigned __int16)LastError | 0x80070000;
      v35 = v22;
      LODWORD(v26) = v22;
      TracePrintW(
        5u,
        "onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\clientconfig.cpp",
        0x998u,
        L"CertGetIssuerCertificateFromStore failed to get issuer from hCertStore=0x%p certificate with hr=0x%x",
        (char *)this + (v12 != 0 ? 936LL : 912LL),
        v26);
      v11 = 2457;
      goto LABEL_32;
    }
    ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(v28);
    WlidsvcUtil::CertGetSKI(pCertContext);
    TracePrintW(
      5u,
      "onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\clientconfig.cpp",
      0x9A2u,
      L"IssuerCert Context=0x%p, IssuerCert SKI=%ls.",
      pCertContext,
      v28[0]);
    ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(v28);
    if ( (pdwFlags & 1) != 0 )
    {
      TracePrintW(
        5u,
        "onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\clientconfig.cpp",
        0x9A8u,
        L"CertGetIssuerCertificateFromStore. Certificate failed the CERT_STORE_SIGNATURE_FLAG check. Trying next cert...");
      goto LABEL_22;
    }
    (*(void (__fastcall **)(struct SmartPCCERT_CONTEXT *))(*(_QWORD *)a4 + 8LL))(a4);
    v17 = CertDuplicateCertificateContext(pCertContext);
    SmartPtr<void *>::Attach(a4, v17);
    v18 = (const CERT_CONTEXT *)*((_QWORD *)a4 + 1);
    if ( !v18 )
    {
      v20 = GetLastError();
      if ( v20 > 0 )
        v20 = (unsigned __int16)v20 | 0x80070000;
      v35 = v20;
      LODWORD(v25) = v20;
      TracePrintW(
        5u,
        "onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\clientconfig.cpp",
        0x9B7u,
        L"Failed CertDuplicateCertificateContext hr = %x",
        v25);
      v11 = 2488;
LABEL_32:
      v10 = "hr = PPCRL_E_CERT_INVALID_ISSUER";
      v9 = -2147186570;
      goto LABEL_33;
    }
    v27 = 2;
    if ( CertVerifySubjectCertificateContext(v18, 0, &v27) && (v27 & 2) == 0 )
    {
      v35 = 0;
      goto LABEL_34;
    }
    v19 = GetLastError();
    if ( v19 > 0 )
      v19 = (unsigned __int16)v19 | 0x80070000;
    v35 = v19;
    LODWORD(v25) = v19;
    TracePrintW(
      5u,
      "onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\clientconfig.cpp",
      0x9C6u,
      L"CertVerifySubjectCertificateContext. Certificate failed the CERT_STORE_TIME_VALIDITY_FLAG check. 0x%x. Trying next cert..",
      v25);
    v35 = 1;
LABEL_22:
    v14 = pCertContext;
  }
  while ( pCertContext );
  if ( !*((_QWORD *)a4 + 1) )
  {
    TracePrintW(
      (_BYTE)pCertContext + 2,
      "onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\clientconfig.cpp",
      0x9D6u,
      L"Could not find a good issuer cert.");
    v35 = -2147186570;
  }
LABEL_34:
  v23 = v35;
  CTraceFuncW<long>::~CTraceFuncW<long>((__int64)v34);
  if ( _InterlockedExchangeAdd(v8, 0xFFFFFFFF) == 1 && *((int *)this + 210) > 0 )
    SetEvent(this[106]);
  SmartPCCERT_CONTEXT::~SmartPCCERT_CONTEXT((SmartPCCERT_CONTEXT *)v33);
  SmartPCCERT_CONTEXT::~SmartPCCERT_CONTEXT((SmartPCCERT_CONTEXT *)&v31);
  SmartPCCERT_CONTEXT::~SmartPCCERT_CONTEXT((SmartPCCERT_CONTEXT *)&v29);
  return v23;
}

```

## disassembly

```asm
0x1800c5648  mov     [rsp-8+arg_18], rbx
0x1800c564d  mov     [rsp-8+arg_10], r8b
0x1800c5652  push    rbp
0x1800c5653  push    rsi
0x1800c5654  push    rdi
0x1800c5655  push    r12
0x1800c5657  push    r13
0x1800c5659  push    r14
0x1800c565b  push    r15
0x1800c565d  lea     rbp, [rsp-27h]
0x1800c5662  sub     rsp, 0B0h
0x1800c5669  mov     r15, r9
0x1800c566c  mov     r12, rdx
0x1800c566f  mov     r13, rcx
0x1800c5672  mov     [rbp+57h+arg_0], 0
0x1800c5679  xor     eax, eax
0x1800c567b  mov     [rbp+57h+pCertContext], rax
0x1800c567f  lea     rcx, ??_7SmartPCCERT_CONTEXT@@6B@; const SmartPCCERT_CONTEXT::`vftable'
0x1800c5686  mov     [rbp+57h+var_88], rcx
0x1800c568a  mov     [rbp+57h+pPrevIssuerContext], rax
0x1800c568e  mov     [rbp+57h+var_78], rcx
0x1800c5692  mov     [rbp+57h+var_60], rax
0x1800c5696  mov     [rbp+57h+var_68], rcx
0x1800c569a  lea     rsi, [r13+340h]
0x1800c56a1  mov     [rbp+57h+var_90], rsi
0x1800c56a5  lea     rdi, [rsi+0Ch]
0x1800c56a9  cmp     dword ptr [rsi+8], 0
0x1800c56ad  jle     short loc_1800C56C3
0x1800c56af  mov     rbx, rdi
0x1800c56b2  or      edx, 0FFFFFFFFh; dwMilliseconds
0x1800c56b5  mov     rcx, [rsi+18h]; hHandle
0x1800c56b9  call    cs:__imp_WaitForSingleObject
0x1800c56bf  test    eax, eax
0x1800c56c1  jnz     short loc_1800C56FA
0x1800c56c3  lea     rdi, [rsi+0Ch]
0x1800c56c7  lock inc dword ptr [rdi]
0x1800c56ca  mov     rbx, rdi
0x1800c56cd  cmp     dword ptr [rsi+8], 0
0x1800c56d1  jle     short loc_1800C56FA
0x1800c56d3  or      eax, 0FFFFFFFFh
0x1800c56d6  lock xadd [rdi], eax
0x1800c56da  cmp     eax, 1
0x1800c56dd  jnz     short loc_1800C56E9
0x1800c56df  mov     rcx, [rsi+10h]; hEvent
0x1800c56e3  call    cs:__imp_SetEvent
0x1800c56e9  or      edx, 0FFFFFFFFh; dwMilliseconds
0x1800c56ec  mov     rcx, [rsi+18h]; hHandle
0x1800c56f0  call    cs:__imp_WaitForSingleObject
0x1800c56f6  test    eax, eax
0x1800c56f8  jz      short loc_1800C56A9
0x1800c56fa  mov     [rsp+0E0h+var_B0], r12
0x1800c56ff  lea     rax, aPcertcontext0x_0; "pCertContext: 0x%p"
0x1800c5706  mov     [rsp+0E0h+var_B8], rax
0x1800c570b  lea     rdi, aCclientconfigd_16; "CClientConfigDataCacheManager::GetIssue"...
0x1800c5712  mov     [rsp+0E0h+var_C0], rdi
0x1800c5717  lea     r9, [rbp+57h+arg_0]
0x1800c571b  mov     r8d, 970h
0x1800c5721  lea     rdx, aOnecoreuapDsEx_58; "onecoreuap\\ds\\ext\\live\\identity\\nt"...
0x1800c5728  lea     rcx, [rbp+57h+var_58]
0x1800c572c  call    ??0?$CTraceFuncW@J@@QEAA@PEBDKAEAJ0PEBGZZ; CTraceFuncW<long>::CTraceFuncW<long>(char const *,ulong,long &,char const *,ushort const *,...)
0x1800c5731  nop
0x1800c5732  test    r12, r12
0x1800c5735  jnz     short loc_1800C5752
0x1800c5737  mov     r9d, 80070057h
0x1800c573d  lea     rax, aPcertcontextNu_0; "pCertContext != nullptr"
0x1800c5744  mov     r8d, 973h
0x1800c574a  mov     rdx, rdi
0x1800c574d  jmp     loc_1800C59ED
0x1800c5752  lea     rbx, [rsi+0Ch]
0x1800c5756  mov     r14b, [rbp+57h+arg_10]
0x1800c575a  mov     al, r14b
0x1800c575d  neg     al
0x1800c575f  sbb     rcx, rcx
0x1800c5762  and     ecx, 18h
0x1800c5765  mov     rdi, [rcx+r13+390h]
0x1800c576d  test    rdi, rdi
0x1800c5770  jnz     short loc_1800C578A
0x1800c5772  mov     r9d, 80048877h
0x1800c5778  lea     rax, aHcertstoreNull; "hCertStore != nullptr"
0x1800c577f  mov     r8d, 981h
0x1800c5785  jmp     loc_1800C59E6
0x1800c578a  mov     rax, [r15]
0x1800c578d  mov     rcx, r15
0x1800c5790  mov     rax, [rax+8]
0x1800c5794  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c5799  mov     rax, [rbp+57h+pCertContext]
0x1800c579d  mov     [rbp+57h+pdwFlags], 1
0x1800c57a4  mov     [rbp+57h+pCertContext], 0
0x1800c57ac  mov     rdx, rax
0x1800c57af  lea     rcx, [rbp+57h+var_78]
0x1800c57b3  call    ?Attach@?$SmartPtr@PEAX@@QEAAXPEAX@Z; SmartPtr<void *>::Attach(void *)
0x1800c57b8  mov     r8, [rbp+57h+pPrevIssuerContext]; pPrevIssuerContext
0x1800c57bc  mov     [rbp+57h+pPrevIssuerContext], 0
0x1800c57c4  lea     r9, [rbp+57h+pdwFlags]; pdwFlags
0x1800c57c8  mov     rdx, r12; pSubjectContext
0x1800c57cb  mov     rcx, rdi; hCertStore
0x1800c57ce  call    cs:__imp_CertGetIssuerCertificateFromStore
0x1800c57d4  mov     rdx, rax
0x1800c57d7  lea     rcx, [rbp+57h+var_88]
0x1800c57db  call    ?Attach@?$SmartPtr@PEAX@@QEAAXPEAX@Z; SmartPtr<void *>::Attach(void *)
0x1800c57e0  cmp     [rbp+57h+pCertContext], 0
0x1800c57e5  jz      loc_1800C5982
0x1800c57eb  lea     rcx, [rbp+57h+var_98]
0x1800c57ef  call    ??0?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(void)
0x1800c57f4  nop
0x1800c57f5  lea     rdx, [rbp+57h+var_98]
0x1800c57f9  mov     rcx, [rbp+57h+pCertContext]; pCertContext
0x1800c57fd  call    ?CertGetSKI@WlidsvcUtil@@SAJPEBU_CERT_CONTEXT@@AEAV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@Z; WlidsvcUtil::CertGetSKI(_CERT_CONTEXT const *,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> &)
0x1800c5802  mov     rax, [rbp+57h+var_98]
0x1800c5806  mov     rcx, [rbp+57h+pCertContext]
0x1800c580a  mov     [rsp+0E0h+var_B8], rax
0x1800c580f  mov     [rsp+0E0h+var_C0], rcx
0x1800c5814  lea     r9, aIssuercertCont; "IssuerCert Context=0x%p, IssuerCert SKI"...
0x1800c581b  mov     r8d, 9A2h; unsigned int
0x1800c5821  lea     rdx, aOnecoreuapDsEx_58; "onecoreuap\\ds\\ext\\live\\identity\\nt"...
0x1800c5828  mov     ecx, 5; unsigned __int8
0x1800c582d  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x1800c5832  nop
0x1800c5833  lea     rcx, [rbp+57h+var_98]
0x1800c5837  call    ??1?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(void)
0x1800c583c  test    byte ptr [rbp+57h+pdwFlags], 1
0x1800c5840  jz      short loc_1800C5865
0x1800c5842  lea     r9, aCertgetissuerc_1; "CertGetIssuerCertificateFromStore. Cert"...
0x1800c5849  mov     r8d, 9A8h; unsigned int
0x1800c584f  lea     rdx, aOnecoreuapDsEx_58; "onecoreuap\\ds\\ext\\live\\identity\\nt"...
0x1800c5856  mov     ecx, 5; unsigned __int8
0x1800c585b  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x1800c5860  jmp     loc_1800C58F5
0x1800c5865  mov     rax, [r15]
0x1800c5868  mov     rcx, r15
0x1800c586b  mov     rax, [rax+8]
0x1800c586f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c5874  mov     rcx, [rbp+57h+pCertContext]; pCertContext
0x1800c5878  call    cs:__imp_CertDuplicateCertificateContext
0x1800c587e  mov     rdx, rax
0x1800c5881  mov     rcx, r15
0x1800c5884  call    ?Attach@?$SmartPtr@PEAX@@QEAAXPEAX@Z; SmartPtr<void *>::Attach(void *)
0x1800c5889  mov     rcx, [r15+8]; pSubject
0x1800c588d  test    rcx, rcx
0x1800c5890  jz      loc_1800C5943
0x1800c5896  mov     [rbp+57h+var_A0], 2
0x1800c589d  lea     r8, [rbp+57h+var_A0]; pdwFlags
0x1800c58a1  xor     edx, edx; pIssuer
0x1800c58a3  call    cs:__imp_CertVerifySubjectCertificateContext
0x1800c58a9  test    eax, eax
0x1800c58ab  jz      short loc_1800C58B7
0x1800c58ad  test    byte ptr [rbp+57h+var_A0], 2
0x1800c58b1  jz      loc_1800C5937
0x1800c58b7  call    cs:__imp_GetLastError
0x1800c58bd  test    eax, eax
0x1800c58bf  jle     short loc_1800C58C9
0x1800c58c1  movzx   eax, ax
0x1800c58c4  or      eax, 80070000h
0x1800c58c9  mov     [rbp+57h+arg_0], eax
0x1800c58cc  mov     dword ptr [rsp+0E0h+var_C0], eax
0x1800c58d0  lea     r9, aCertverifysubj_0; "CertVerifySubjectCertificateContext. Ce"...
0x1800c58d7  mov     r8d, 9C6h; unsigned int
0x1800c58dd  lea     rdx, aOnecoreuapDsEx_58; "onecoreuap\\ds\\ext\\live\\identity\\nt"...
0x1800c58e4  mov     ecx, 5; unsigned __int8
0x1800c58e9  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x1800c58ee  mov     [rbp+57h+arg_0], 1
0x1800c58f5  mov     rax, [rbp+57h+pCertContext]
0x1800c58f9  test    rax, rax
0x1800c58fc  jnz     loc_1800C579D
0x1800c5902  cmp     [r15+8], rax
0x1800c5906  jnz     loc_1800C5A02
0x1800c590c  lea     r9, aCouldNotFindAG; "Could not find a good issuer cert."
0x1800c5913  mov     r8d, 9D6h; unsigned int
0x1800c5919  lea     rdx, aOnecoreuapDsEx_58; "onecoreuap\\ds\\ext\\live\\identity\\nt"...
0x1800c5920  lea     ecx, [rax+2]; unsigned __int8
0x1800c5923  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x1800c5928  mov     r9d, 80048876h
0x1800c592e  mov     [rbp+57h+arg_0], r9d
0x1800c5932  jmp     loc_1800C5A02
0x1800c5937  mov     [rbp+57h+arg_0], 0
0x1800c593e  jmp     loc_1800C5A02
0x1800c5943  call    cs:__imp_GetLastError
0x1800c5949  test    eax, eax
0x1800c594b  jle     short loc_1800C5955
0x1800c594d  movzx   eax, ax
0x1800c5950  or      eax, 80070000h
0x1800c5955  mov     [rbp+57h+arg_0], eax
0x1800c5958  mov     dword ptr [rsp+0E0h+var_C0], eax
0x1800c595c  lea     r9, aFailedCertdupl; "Failed CertDuplicateCertificateContext "...
0x1800c5963  mov     r8d, 9B7h; unsigned int
0x1800c5969  lea     rdx, aOnecoreuapDsEx_58; "onecoreuap\\ds\\ext\\live\\identity\\nt"...
0x1800c5970  mov     ecx, 5; unsigned __int8
0x1800c5975  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x1800c597a  mov     r8d, 9B8h
0x1800c5980  jmp     short loc_1800C59D9
0x1800c5982  call    cs:__imp_GetLastError
0x1800c5988  mov     ecx, eax
0x1800c598a  test    eax, eax
0x1800c598c  jle     short loc_1800C5997
0x1800c598e  movzx   ecx, ax
0x1800c5991  or      ecx, 80070000h
0x1800c5997  mov     [rbp+57h+arg_0], ecx
0x1800c599a  neg     r14b
0x1800c599d  sbb     rax, rax
0x1800c59a0  and     eax, 18h
0x1800c59a3  add     rax, 390h
0x1800c59a9  add     rax, r13
0x1800c59ac  mov     dword ptr [rsp+0E0h+var_B8], ecx
0x1800c59b0  mov     [rsp+0E0h+var_C0], rax
0x1800c59b5  lea     r9, aCertgetissuerc_0; "CertGetIssuerCertificateFromStore faile"...
0x1800c59bc  mov     r8d, 998h; unsigned int
0x1800c59c2  lea     rdx, aOnecoreuapDsEx_58; "onecoreuap\\ds\\ext\\live\\identity\\nt"...
0x1800c59c9  mov     ecx, 5; unsigned __int8
0x1800c59ce  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x1800c59d3  mov     r8d, 999h; unsigned int
0x1800c59d9  lea     rax, aHrPpcrlECertIn; "hr = PPCRL_E_CERT_INVALID_ISSUER"
0x1800c59e0  mov     r9d, 80048876h; int
0x1800c59e6  lea     rdx, aCclientconfigd_16; "CClientConfigDataCacheManager::GetIssue"...
0x1800c59ed  mov     [rsp+0E0h+var_C0], rax; char *
0x1800c59f2  mov     [rbp+57h+arg_0], r9d
0x1800c59f6  lea     rcx, aOnecoreuapDsEx_58; "onecoreuap\\ds\\ext\\live\\identity\\nt"...
0x1800c59fd  call    ?IfFailExit@Telemetry@@SAXPEBD0KJ0@Z; Telemetry::IfFailExit(char const *,char const *,ulong,long,char const *)
0x1800c5a02  mov     edi, [rbp+57h+arg_0]
0x1800c5a05  lea     rcx, [rbp+57h+var_58]
0x1800c5a09  call    ??1?$CTraceFuncW@J@@QEAA@XZ; CTraceFuncW<long>::~CTraceFuncW<long>(void)
0x1800c5a0e  nop
0x1800c5a0f  or      eax, 0FFFFFFFFh
0x1800c5a12  lock xadd [rbx], eax
0x1800c5a16  cmp     eax, 1
0x1800c5a19  jnz     short loc_1800C5A2C
0x1800c5a1b  cmp     dword ptr [rsi+8], 0
0x1800c5a1f  jle     short loc_1800C5A2C
0x1800c5a21  mov     rcx, [rsi+10h]; hEvent
0x1800c5a25  call    cs:__imp_SetEvent
0x1800c5a2b  nop
0x1800c5a2c  lea     rcx, [rbp+57h+var_68]; this
0x1800c5a30  call    ??1SmartPCCERT_CONTEXT@@UEAA@XZ; SmartPCCERT_CONTEXT::~SmartPCCERT_CONTEXT(void)
0x1800c5a35  nop
0x1800c5a36  lea     rcx, [rbp+57h+var_78]; this
0x1800c5a3a  call    ??1SmartPCCERT_CONTEXT@@UEAA@XZ; SmartPCCERT_CONTEXT::~SmartPCCERT_CONTEXT(void)
0x1800c5a3f  nop
0x1800c5a40  lea     rcx, [rbp+57h+var_88]; this
0x1800c5a44  call    ??1SmartPCCERT_CONTEXT@@UEAA@XZ; SmartPCCERT_CONTEXT::~SmartPCCERT_CONTEXT(void)
0x1800c5a49  mov     eax, edi
0x1800c5a4b  mov     rbx, [rsp+0E0h+arg_18]
0x1800c5a53  add     rsp, 0B0h
0x1800c5a5a  pop     r15
0x1800c5a5c  pop     r14
0x1800c5a5e  pop     r13
0x1800c5a60  pop     r12
0x1800c5a62  pop     rdi
0x1800c5a63  pop     rsi
0x1800c5a64  pop     rbp
0x1800c5a65  retn
```
