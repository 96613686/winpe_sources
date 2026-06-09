# IsSmartCardCert_Helper(ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>> const &,int &)

- ea: `0x180058428`
- end: `0x180058629`
- name: `?IsSmartCardCert_Helper@@YAJAEBV?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@AEAH@Z`
- size: `513`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: ``

## callers

- `0x18005831c`

## callees

- `0x18000a914`
- `0x18000ba8c`
- `0x18000cc9c`
- `0x18000cd80`
- `0x18000cdd8`
- `0x18000d194`
- `0x18000e870`
- `0x1800103d0`
- `0x180053890`
- `0x180058428`
- `0x180058630`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180058501`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005856f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180058501`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005856f`
- `CRYPT32!CertFindCertificateInStore` at `0x180058561`
- `CRYPT32!CertFindCertificateInStore` at `0x180058561`
- `CRYPT32!CertOpenStore` at `0x1800584e6`
- `CRYPT32!CertOpenStore` at `0x1800584e6`

## string_xrefs

- `0x1800584b6`: `onecoreuap\ds\ext\live\identity\lib\utilities\certtoken.cpp`
- `0x1800585d0`: `onecoreuap\ds\ext\live\identity\lib\utilities\certtoken.cpp`

## pseudocode

```c
__int64 __fastcall IsSmartCardCert_Helper(_QWORD *a1, int *a2)
{
  HCERTSTORE v4; // rax
  HCERTSTORE v5; // rcx
  signed int LastError; // eax
  PCCERT_CONTEXT CertificateInStore; // rbx
  signed int v8; // eax
  int v9; // eax
  unsigned int v10; // ebx
  const unsigned __int16 *pvPara; // [rsp+20h] [rbp-29h]
  void **v13; // [rsp+30h] [rbp-19h] BYREF
  PCCERT_CONTEXT pCert; // [rsp+38h] [rbp-11h]
  __int128 pvFindPara; // [rsp+40h] [rbp-9h] BYREF
  void **v16; // [rsp+50h] [rbp+7h] BYREF
  HCERTSTORE hCertStore; // [rsp+58h] [rbp+Fh]
  int v18; // [rsp+60h] [rbp+17h]
  _QWORD v19[7]; // [rsp+68h] [rbp+1Fh] BYREF
  signed int v20; // [rsp+B8h] [rbp+6Fh] BYREF
  __int64 v21; // [rsp+C0h] [rbp+77h] BYREF
  __int64 v22; // [rsp+C8h] [rbp+7Fh] BYREF

  v20 = 0;
  hCertStore = 0;
  v18 = 1;
  v16 = &SmartHCERTSTORE::`vftable';
  pCert = 0;
  v13 = &SmartPCCERT_CONTEXT::`vftable';
  ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>((__int64)&v22);
  v21 = 0;
  v19[0] = "IsSmartCardCert_Helper";
  v19[2] = 0;
  v19[1] = &v20;
  v19[3] = 0;
  pvFindPara = 0;
  MsaTracingInternal::TraceFunctionEnter(
    (MsaTracingInternal *)"onecoreuap\\ds\\ext\\live\\identity\\lib\\utilities\\certtoken.cpp",
    "IsSmartCardCert_Helper",
    (const char *)0x1DA,
    0,
    pvPara);
  *a2 = 0;
  v4 = CertOpenStore((LPCSTR)0xA, 0, 0, 0x1C000u, L"MY");
  SmartPtr<void *>::Attach(&v16, v4);
  v5 = hCertStore;
  if ( !hCertStore )
  {
    LastError = GetLastError();
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
    v20 = LastError;
    if ( LastError < 0 )
    {
      Telemetry::IfFailExit(
        "onecoreuap\\ds\\ext\\live\\identity\\lib\\utilities\\certtoken.cpp",
        "IsSmartCardCert_Helper",
        0x1E7u,
        LastError,
        "hr = HRESULT_FROM_WIN32(GetLastError())");
      goto LABEL_14;
    }
    v5 = hCertStore;
  }
  *((_QWORD *)&pvFindPara + 1) = *a1;
  LODWORD(pvFindPara) = *(_DWORD *)(*((_QWORD *)&pvFindPara + 1) - 16LL);
  CertificateInStore = CertFindCertificateInStore(v5, 0x10001u, 0, 0x10000u, &pvFindPara, 0);
  if ( CertificateInStore )
    goto LABEL_12;
  v8 = GetLastError();
  if ( v8 > 0 )
    v8 = (unsigned __int16)v8 | 0x80070000;
  v20 = v8;
  if ( v8 >= 0 )
  {
LABEL_12:
    SmartPtr<void *>::Attach(&v13, CertificateInStore);
    v9 = IsSmartCardCert_Helper(pCert, a2);
    v20 = v9;
    if ( v9 < 0 )
      Telemetry::IfFailExit(
        "onecoreuap\\ds\\ext\\live\\identity\\lib\\utilities\\certtoken.cpp",
        "IsSmartCardCert_Helper",
        0x1F5u,
        v9,
        "hr = IsSmartCardCert_Helper(pCertContext, fSmartCardCert)");
  }
  else
  {
    Telemetry::IfFailExit(
      "onecoreuap\\ds\\ext\\live\\identity\\lib\\utilities\\certtoken.cpp",
      "IsSmartCardCert_Helper",
      0x1F1u,
      v8,
      "hr = HRESULT_FROM_WIN32(GetLastError())");
  }
LABEL_14:
  v10 = v20;
  CTraceFuncW<long>::~CTraceFuncW<long>((__int64)v19);
  ATL::CCryptProv::Release((ATL::CCryptProv *)&v21);
  ATL::CStringData::Release((ATL::CStringData *)(v22 - 24));
  SmartPCCERT_CONTEXT::~SmartPCCERT_CONTEXT((SmartPCCERT_CONTEXT *)&v13);
  SmartHCERTSTORE::~SmartHCERTSTORE((SmartHCERTSTORE *)&v16);
  return v10;
}

```

## disassembly

```asm
0x180058428  mov     [rsp-8+arg_0], rbx
0x18005842d  push    rbp
0x18005842e  push    rdi
0x18005842f  push    r14
0x180058431  lea     rbp, [rsp-47h]
0x180058436  sub     rsp, 90h
0x18005843d  xor     eax, eax
0x18005843f  mov     [rbp+57h+arg_8], 0
0x180058446  mov     [rbp+57h+hCertStore], rax
0x18005844a  mov     rbx, rcx
0x18005844d  lea     rax, ??_7SmartHCERTSTORE@@6B@; const SmartHCERTSTORE::`vftable'
0x180058454  mov     [rbp+57h+var_40], 1
0x18005845b  mov     [rbp+57h+var_50], rax
0x18005845f  lea     rcx, [rbp+57h+arg_18]
0x180058463  xor     eax, eax
0x180058465  mov     rdi, rdx
0x180058468  mov     [rbp+57h+pCert], rax
0x18005846c  lea     rax, ??_7SmartPCCERT_CONTEXT@@6B@; const SmartPCCERT_CONTEXT::`vftable'
0x180058473  mov     [rbp+57h+var_70], rax
0x180058477  call    ??0?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(void)
0x18005847c  lea     r14, aIssmartcardcer; "IsSmartCardCert_Helper"
0x180058483  mov     [rbp+57h+arg_10], 0
0x18005848b  xorps   xmm0, xmm0
0x18005848e  mov     [rbp+57h+var_38], r14
0x180058492  lea     rax, [rbp+57h+arg_8]
0x180058496  mov     [rbp+57h+var_28], 0
0x18005849e  mov     rdx, r14; char *
0x1800584a1  mov     [rbp+57h+var_30], rax
0x1800584a5  xor     r9d, r9d; unsigned int
0x1800584a8  mov     [rbp+57h+var_20], 0
0x1800584b0  mov     r8d, 1DAh; char *
0x1800584b6  lea     rcx, aOnecoreuapDsEx_9; "onecoreuap\\ds\\ext\\live\\identity\\li"...
0x1800584bd  movups  [rbp+57h+pvFindPara], xmm0
0x1800584c1  call    ?TraceFunctionEnter@MsaTracingInternal@@YAKPEBD0KPEBG@Z; MsaTracingInternal::TraceFunctionEnter(char const *,char const *,ulong,ushort const *)
0x1800584c6  xor     edx, edx; dwEncodingType
0x1800584c8  mov     dword ptr [rdi], 0
0x1800584ce  lea     rax, aMy; "MY"
0x1800584d5  mov     r9d, 1C000h; dwFlags
0x1800584db  xor     r8d, r8d; hCryptProv
0x1800584de  mov     [rsp+0A0h+pvPara], rax; pvPara
0x1800584e3  lea     ecx, [rdx+0Ah]; lpszStoreProvider
0x1800584e6  call    cs:__imp_CertOpenStore
0x1800584ec  mov     rdx, rax
0x1800584ef  lea     rcx, [rbp+57h+var_50]
0x1800584f3  call    ?Attach@?$SmartPtr@PEAX@@QEAAXPEAX@Z; SmartPtr<void *>::Attach(void *)
0x1800584f8  mov     rcx, [rbp+57h+hCertStore]
0x1800584fc  test    rcx, rcx
0x1800584ff  jnz     short loc_180058535
0x180058501  call    cs:__imp_GetLastError
0x180058507  test    eax, eax
0x180058509  jle     short loc_180058513
0x18005850b  movzx   eax, ax
0x18005850e  or      eax, 80070000h
0x180058513  mov     [rbp+57h+arg_8], eax
0x180058516  test    eax, eax
0x180058518  jns     short loc_180058531
0x18005851a  lea     r8, aHrHresultFromW; "hr = HRESULT_FROM_WIN32(GetLastError())"
0x180058521  mov     [rsp+0A0h+pvPara], r8
0x180058526  mov     r8d, 1E7h
0x18005852c  jmp     loc_1800585CD
0x180058531  mov     rcx, [rbp+57h+hCertStore]; hCertStore
0x180058535  mov     rax, [rbx]
0x180058538  mov     r9d, 10000h; dwFindType
0x18005853e  mov     qword ptr [rbp+57h+pvFindPara+8], rax
0x180058542  xor     r8d, r8d; dwFindFlags
0x180058545  mov     [rsp+0A0h+pPrevCertContext], 0; pPrevCertContext
0x18005854e  mov     eax, [rax-10h]
0x180058551  lea     edx, [r9+1]; dwCertEncodingType
0x180058555  mov     dword ptr [rbp+57h+pvFindPara], eax
0x180058558  lea     rax, [rbp+57h+pvFindPara]
0x18005855c  mov     [rsp+0A0h+pvPara], rax; pvFindPara
0x180058561  call    cs:__imp_CertFindCertificateInStore
0x180058567  mov     rbx, rax
0x18005856a  test    rax, rax
0x18005856d  jnz     short loc_18005859C
0x18005856f  call    cs:__imp_GetLastError
0x180058575  test    eax, eax
0x180058577  jle     short loc_180058581
0x180058579  movzx   eax, ax
0x18005857c  or      eax, 80070000h
0x180058581  mov     [rbp+57h+arg_8], eax
0x180058584  test    eax, eax
0x180058586  jns     short loc_18005859C
0x180058588  lea     r8, aHrHresultFromW; "hr = HRESULT_FROM_WIN32(GetLastError())"
0x18005858f  mov     [rsp+0A0h+pvPara], r8
0x180058594  mov     r8d, 1F1h
0x18005859a  jmp     short loc_1800585CD
0x18005859c  mov     rdx, rbx
0x18005859f  lea     rcx, [rbp+57h+var_70]
0x1800585a3  call    ?Attach@?$SmartPtr@PEAX@@QEAAXPEAX@Z; SmartPtr<void *>::Attach(void *)
0x1800585a8  mov     rcx, [rbp+57h+pCert]; pCert
0x1800585ac  mov     rdx, rdi; int *
0x1800585af  call    ?IsSmartCardCert_Helper@@YAJPEBU_CERT_CONTEXT@@AEAH@Z; IsSmartCardCert_Helper(_CERT_CONTEXT const *,int &)
0x1800585b4  mov     [rbp+57h+arg_8], eax
0x1800585b7  test    eax, eax
0x1800585b9  jns     short loc_1800585DF
0x1800585bb  lea     rcx, aHrIssmartcardc_0; "hr = IsSmartCardCert_Helper(pCertContex"...
0x1800585c2  mov     r8d, 1F5h; unsigned int
0x1800585c8  mov     [rsp+0A0h+pvPara], rcx; char *
0x1800585cd  mov     r9d, eax; int
0x1800585d0  lea     rcx, aOnecoreuapDsEx_9; "onecoreuap\\ds\\ext\\live\\identity\\li"...
0x1800585d7  mov     rdx, r14; char *
0x1800585da  call    ?IfFailExit@Telemetry@@SAXPEBD0KJ0@Z; Telemetry::IfFailExit(char const *,char const *,ulong,long,char const *)
0x1800585df  mov     ebx, [rbp+57h+arg_8]
0x1800585e2  lea     rcx, [rbp+57h+var_38]
0x1800585e6  call    ??1?$CTraceFuncW@J@@QEAA@XZ; CTraceFuncW<long>::~CTraceFuncW<long>(void)
0x1800585eb  lea     rcx, [rbp+57h+arg_10]; this
0x1800585ef  call    ?Release@CCryptProv@ATL@@QEAAJXZ; ATL::CCryptProv::Release(void)
0x1800585f4  mov     rcx, [rbp+57h+arg_18]
0x1800585f8  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x1800585fc  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x180058601  lea     rcx, [rbp+57h+var_70]; this
0x180058605  call    ??1SmartPCCERT_CONTEXT@@UEAA@XZ; SmartPCCERT_CONTEXT::~SmartPCCERT_CONTEXT(void)
0x18005860a  lea     rcx, [rbp+57h+var_50]; this
0x18005860e  call    ??1SmartHCERTSTORE@@UEAA@XZ; SmartHCERTSTORE::~SmartHCERTSTORE(void)
0x180058613  mov     eax, ebx
0x180058615  mov     rbx, [rsp+0A0h+arg_0]
0x18005861d  add     rsp, 90h
0x180058624  pop     r14
0x180058626  pop     rdi
0x180058627  pop     rbp
0x180058628  retn
```
