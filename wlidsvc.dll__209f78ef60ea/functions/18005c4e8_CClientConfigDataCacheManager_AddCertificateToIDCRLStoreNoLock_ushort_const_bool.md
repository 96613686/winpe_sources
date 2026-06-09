# CClientConfigDataCacheManager::AddCertificateToIDCRLStoreNoLock(ushort * const &,bool)

- ea: `0x18005c4e8`
- end: `0x18005c6f7`
- name: `?AddCertificateToIDCRLStoreNoLock@CClientConfigDataCacheManager@@QEAAJAEBQEAG_N@Z`
- size: `527`
- prototype: `__int64 __fastcall(CClientConfigDataCacheManager *__hidden this, unsigned __int16 *const *, bool)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18006e8b0`

## callees

- `0x18000c050`
- `0x18000ed04`
- `0x1800151c4`
- `0x180016938`
- `0x18001a9c0`
- `0x18001ad00`
- `0x180033218`
- `0x18004ff98`
- `0x18005c4e8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005c5be`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005c648`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005c68b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005c5be`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005c648`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005c68b`
- `OLEAUT32!__imp_SysStringLen` at `0x18005c55a`
- `OLEAUT32!__imp_SysStringLen` at `0x18005c5ee`
- `OLEAUT32!__imp_SysStringLen` at `0x18005c55a`
- `OLEAUT32!__imp_SysStringLen` at `0x18005c5ee`
- `CRYPT32!CertOpenStore` at `0x18005c5a6`
- `CRYPT32!CertOpenStore` at `0x18005c5a6`
- `CRYPT32!CertAddCertificateContextToStore` at `0x18005c681`
- `CRYPT32!CertAddCertificateContextToStore` at `0x18005c681`
- `CRYPT32!CertCreateCertificateContext` at `0x18005c62d`
- `CRYPT32!CertCreateCertificateContext` at `0x18005c62d`

## string_xrefs

- `0x18005c547`: `onecoreuap\ds\ext\live\identity\ntservice\lib\svccommon\clientconfig.cpp`
- `0x18005c518`: `CClientConfigDataCacheManager::AddCertificateToIDCRLStoreNoLock`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall CClientConfigDataCacheManager::AddCertificateToIDCRLStoreNoLock(
        CClientConfigDataCacheManager *this,
        BSTR *a2,
        char a3)
{
  __int64 v5; // rbx
  char *v6; // rbx
  HCERTSTORE v7; // rax
  signed int LastError; // eax
  int v9; // eax
  PCCERT_CONTEXT CertificateContext; // rax
  const CERT_CONTEXT *v11; // rdx
  signed int v12; // eax
  signed int v13; // eax
  unsigned int v14; // ebx
  const unsigned __int16 *pvPara; // [rsp+20h] [rbp-40h]
  void **v17; // [rsp+30h] [rbp-30h] BYREF
  PCCERT_CONTEXT pCertContext; // [rsp+38h] [rbp-28h]
  _QWORD v19[4]; // [rsp+40h] [rbp-20h] BYREF
  signed int v20; // [rsp+A0h] [rbp+40h] BYREF
  BYTE *pbCertEncoded; // [rsp+A8h] [rbp+48h] BYREF

  v5 = a3 != 0 ? 928LL : 904LL;
  v20 = 0;
  v19[0] = "CClientConfigDataCacheManager::AddCertificateToIDCRLStoreNoLock";
  v19[1] = &v20;
  v19[2] = 0;
  v19[3] = 0;
  MsaTracingInternal::TraceFunctionEnter(
    (MsaTracingInternal *)"onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\clientconfig.cpp",
    "CClientConfigDataCacheManager::AddCertificateToIDCRLStoreNoLock",
    (const char *)0xA15,
    0,
    pvPara);
  if ( SysStringLen(*a2) )
  {
    v6 = (char *)this + v5;
    pCertContext = 0;
    v17 = &SmartPCCERT_CONTEXT::`vftable';
    ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&pbCertEncoded);
    if ( *((_QWORD *)v6 + 1) )
      goto LABEL_8;
    v7 = CertOpenStore((LPCSTR)2, 0, 0, 0, 0);
    SmartPtr<void *>::Attach(v6, v7);
    if ( *((_QWORD *)v6 + 1) )
      goto LABEL_8;
    LastError = GetLastError();
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
    v20 = LastError;
    if ( LastError >= 0 )
    {
LABEL_8:
      SysStringLen(*a2);
      v9 = PassportEncode::Base64Decode(*a2);
      v20 = v9;
      if ( v9 >= 0 )
      {
        CertificateContext = CertCreateCertificateContext(0x10001u, pbCertEncoded, *((_DWORD *)pbCertEncoded - 4));
        SmartPtr<void *>::Attach(&v17, CertificateContext);
        v11 = pCertContext;
        if ( !pCertContext )
        {
          v12 = GetLastError();
          if ( v12 > 0 )
            v12 = (unsigned __int16)v12 | 0x80070000;
          v20 = v12;
          if ( v12 < 0 )
          {
            Telemetry::IfFailExit(
              "onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\clientconfig.cpp",
              "CClientConfigDataCacheManager::AddCertificateToIDCRLStoreNoLock",
              0xA2Cu,
              v12,
              "hr = HRESULT_FROM_WIN32(GetLastError())");
            goto LABEL_21;
          }
          v11 = pCertContext;
        }
        if ( !CertAddCertificateContextToStore(*((HCERTSTORE *)v6 + 1), v11, 3u, 0) )
        {
          v13 = GetLastError();
          if ( v13 > 0 )
            v13 = (unsigned __int16)v13 | 0x80070000;
          v20 = v13;
          if ( v13 < 0 )
            Telemetry::IfFailExit(
              "onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\clientconfig.cpp",
              "CClientConfigDataCacheManager::AddCertificateToIDCRLStoreNoLock",
              0xA31u,
              v13,
              "hr = HRESULT_FROM_WIN32(GetLastError())");
        }
        goto LABEL_21;
      }
      Telemetry::IfFailExit(
        "onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\clientconfig.cpp",
        "CClientConfigDataCacheManager::AddCertificateToIDCRLStoreNoLock",
        0xA27u,
        v9,
        "hr = PassportEncode::Base64Decode(bstrValue, SysStringLen(bstrValue), strCertificate)");
    }
    else
    {
      Telemetry::IfFailExit(
        "onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\clientconfig.cpp",
        "CClientConfigDataCacheManager::AddCertificateToIDCRLStoreNoLock",
        0xA24u,
        LastError,
        "hr = HRESULT_FROM_WIN32(GetLastError())");
    }
LABEL_21:
    ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&pbCertEncoded);
    SmartPCCERT_CONTEXT::~SmartPCCERT_CONTEXT((SmartPCCERT_CONTEXT *)&v17);
  }
  v14 = v20;
  CTraceFuncW<long>::~CTraceFuncW<long>((__int64)v19);
  return v14;
}

```

## disassembly

```asm
0x18005c4e8  mov     [rsp-28h+arg_0], rbx
0x18005c4ed  push    rbp
0x18005c4ee  push    rsi
0x18005c4ef  push    rdi
0x18005c4f0  push    r12
0x18005c4f2  push    r15
0x18005c4f4  mov     rbp, rsp
0x18005c4f7  sub     rsp, 60h
0x18005c4fb  mov     rdi, rdx
0x18005c4fe  mov     rsi, rcx
0x18005c501  neg     r8b
0x18005c504  sbb     rbx, rbx
0x18005c507  and     ebx, 18h
0x18005c50a  add     rbx, 388h
0x18005c511  mov     [rbp+arg_10], 0
0x18005c518  lea     r15, aCclientconfigd_13; "CClientConfigDataCacheManager::AddCerti"...
0x18005c51f  mov     [rbp+var_20], r15
0x18005c523  lea     rax, [rbp+arg_10]
0x18005c527  mov     [rbp+var_18], rax
0x18005c52b  mov     [rbp+var_10], 0
0x18005c533  mov     [rbp+var_8], 0
0x18005c53b  xor     r9d, r9d; unsigned int
0x18005c53e  mov     r8d, 0A15h; char *
0x18005c544  mov     rdx, r15; char *
0x18005c547  lea     r12, aOnecoreuapDsEx_58; "onecoreuap\\ds\\ext\\live\\identity\\nt"...
0x18005c54e  mov     rcx, r12; this
0x18005c551  call    ?TraceFunctionEnter@MsaTracingInternal@@YAKPEBD0KPEBG@Z; MsaTracingInternal::TraceFunctionEnter(char const *,char const *,ulong,ushort const *)
0x18005c556  nop
0x18005c557  mov     rcx, [rdi]; pbstr
0x18005c55a  call    cs:__imp_SysStringLen
0x18005c560  test    eax, eax
0x18005c562  jz      loc_18005C6D5
0x18005c568  add     rbx, rsi
0x18005c56b  xor     eax, eax
0x18005c56d  mov     [rbp+pCertContext], rax
0x18005c571  lea     rax, ??_7SmartPCCERT_CONTEXT@@6B@; const SmartPCCERT_CONTEXT::`vftable'
0x18005c578  mov     [rbp+var_30], rax
0x18005c57c  lea     rcx, [rbp+pbCertEncoded]
0x18005c580  call    ??0?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(void)
0x18005c585  nop
0x18005c586  mov     esi, 80070000h
0x18005c58b  cmp     qword ptr [rbx+8], 0
0x18005c590  jnz     short loc_18005C5EB
0x18005c592  mov     [rsp+60h+pvPara], 0; pvPara
0x18005c59b  xor     r9d, r9d; dwFlags
0x18005c59e  xor     r8d, r8d; hCryptProv
0x18005c5a1  xor     edx, edx; dwEncodingType
0x18005c5a3  lea     ecx, [rdx+2]; lpszStoreProvider
0x18005c5a6  call    cs:__imp_CertOpenStore
0x18005c5ac  mov     rdx, rax
0x18005c5af  mov     rcx, rbx
0x18005c5b2  call    ?Attach@?$SmartPtr@PEAX@@QEAAXPEAX@Z; SmartPtr<void *>::Attach(void *)
0x18005c5b7  cmp     qword ptr [rbx+8], 0
0x18005c5bc  jnz     short loc_18005C5EB
0x18005c5be  call    cs:__imp_GetLastError
0x18005c5c4  test    eax, eax
0x18005c5c6  jle     short loc_18005C5CD
0x18005c5c8  movzx   eax, ax
0x18005c5cb  or      eax, esi
0x18005c5cd  mov     [rbp+arg_10], eax
0x18005c5d0  test    eax, eax
0x18005c5d2  jns     short loc_18005C5EB
0x18005c5d4  lea     r8, aHrHresultFromW_10; "hr = HRESULT_FROM_WIN32(GetLastError())"
0x18005c5db  mov     [rsp+60h+pvPara], r8
0x18005c5e0  mov     r8d, 0A24h
0x18005c5e6  jmp     loc_18005C6B3
0x18005c5eb  mov     rcx, [rdi]; pbstr
0x18005c5ee  call    cs:__imp_SysStringLen
0x18005c5f4  lea     r8, [rbp+pbCertEncoded]
0x18005c5f8  mov     edx, eax
0x18005c5fa  mov     rcx, [rdi]; Src
0x18005c5fd  call    ?Base64Decode@PassportEncode@@YAJPEBGKAEAV?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@@Z; PassportEncode::Base64Decode(ushort const *,ulong,ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>> &)
0x18005c602  mov     [rbp+arg_10], eax
0x18005c605  test    eax, eax
0x18005c607  jns     short loc_18005C620
0x18005c609  lea     rcx, aHrPassportenco_23; "hr = PassportEncode::Base64Decode(bstrV"...
0x18005c610  mov     [rsp+60h+pvPara], rcx
0x18005c615  mov     r8d, 0A27h
0x18005c61b  jmp     loc_18005C6B3
0x18005c620  mov     rdx, [rbp+pbCertEncoded]; pbCertEncoded
0x18005c624  mov     r8d, [rdx-10h]; cbCertEncoded
0x18005c628  mov     ecx, 10001h; dwCertEncodingType
0x18005c62d  call    cs:__imp_CertCreateCertificateContext
0x18005c633  mov     rdx, rax
0x18005c636  lea     rcx, [rbp+var_30]
0x18005c63a  call    ?Attach@?$SmartPtr@PEAX@@QEAAXPEAX@Z; SmartPtr<void *>::Attach(void *)
0x18005c63f  mov     rdx, [rbp+pCertContext]
0x18005c643  test    rdx, rdx
0x18005c646  jnz     short loc_18005C676
0x18005c648  call    cs:__imp_GetLastError
0x18005c64e  test    eax, eax
0x18005c650  jle     short loc_18005C657
0x18005c652  movzx   eax, ax
0x18005c655  or      eax, esi
0x18005c657  mov     [rbp+arg_10], eax
0x18005c65a  test    eax, eax
0x18005c65c  jns     short loc_18005C672
0x18005c65e  lea     r8, aHrHresultFromW_10; "hr = HRESULT_FROM_WIN32(GetLastError())"
0x18005c665  mov     [rsp+60h+pvPara], r8
0x18005c66a  mov     r8d, 0A2Ch
0x18005c670  jmp     short loc_18005C6B3
0x18005c672  mov     rdx, [rbp+pCertContext]; pCertContext
0x18005c676  xor     r9d, r9d; ppStoreContext
0x18005c679  lea     r8d, [r9+3]; dwAddDisposition
0x18005c67d  mov     rcx, [rbx+8]; hCertStore
0x18005c681  call    cs:__imp_CertAddCertificateContextToStore
0x18005c687  test    eax, eax
0x18005c689  jnz     short loc_18005C6C2
0x18005c68b  call    cs:__imp_GetLastError
0x18005c691  test    eax, eax
0x18005c693  jle     short loc_18005C69A
0x18005c695  movzx   eax, ax
0x18005c698  or      eax, esi
0x18005c69a  mov     [rbp+arg_10], eax
0x18005c69d  test    eax, eax
0x18005c69f  jns     short loc_18005C6C2
0x18005c6a1  lea     r8, aHrHresultFromW_10; "hr = HRESULT_FROM_WIN32(GetLastError())"
0x18005c6a8  mov     [rsp+60h+pvPara], r8; char *
0x18005c6ad  mov     r8d, 0A31h; unsigned int
0x18005c6b3  mov     r9d, eax; int
0x18005c6b6  mov     rdx, r15; char *
0x18005c6b9  mov     rcx, r12; char *
0x18005c6bc  call    ?IfFailExit@Telemetry@@SAXPEBD0KJ0@Z; Telemetry::IfFailExit(char const *,char const *,ulong,long,char const *)
0x18005c6c1  nop
0x18005c6c2  lea     rcx, [rbp+pbCertEncoded]
0x18005c6c6  call    ??1?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(void)
0x18005c6cb  nop
0x18005c6cc  lea     rcx, [rbp+var_30]; this
0x18005c6d0  call    ??1SmartPCCERT_CONTEXT@@UEAA@XZ; SmartPCCERT_CONTEXT::~SmartPCCERT_CONTEXT(void)
0x18005c6d5  mov     ebx, [rbp+arg_10]
0x18005c6d8  lea     rcx, [rbp+var_20]
0x18005c6dc  call    ??1?$CTraceFuncW@J@@QEAA@XZ; CTraceFuncW<long>::~CTraceFuncW<long>(void)
0x18005c6e1  mov     eax, ebx
0x18005c6e3  mov     rbx, [rsp+60h+arg_0]
0x18005c6eb  add     rsp, 60h
0x18005c6ef  pop     r15
0x18005c6f1  pop     r12
0x18005c6f3  pop     rdi
0x18005c6f4  pop     rsi
0x18005c6f5  pop     rbp
0x18005c6f6  retn
```
