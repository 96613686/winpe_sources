# CleanupCertificateAuthority(ushort const *,ATL::CAtlArray<SmartPCCERT_CONTEXT,ATL::CElementTraits<SmartPCCERT_CONTEXT>> &)

- ea: `0x18006e6f0`
- end: `0x18006e89f`
- name: `?CleanupCertificateAuthority@@YAJPEBGAEAV?$CAtlArray@VSmartPCCERT_CONTEXT@@V?$CElementTraits@VSmartPCCERT_CONTEXT@@@ATL@@@ATL@@@Z`
- size: `431`
- prototype: `__int64 __fastcall(void *pvPara)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18006e8b0`

## callees

- `0x18000c050`
- `0x180019690`
- `0x18001a9c0`
- `0x18001ad00`
- `0x180034908`
- `0x18004f970`
- `0x18004ff98`
- `0x18006e6f0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006e789`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006e81b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006e83d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006e789`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006e81b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006e83d`
- `CRYPT32!CertEnumCertificatesInStore` at `0x18006e86c`
- `CRYPT32!CertEnumCertificatesInStore` at `0x18006e86c`
- `CRYPT32!CertOpenStore` at `0x18006e76e`
- `CRYPT32!CertOpenStore` at `0x18006e76e`
- `CRYPT32!CertDeleteCertificateFromStore` at `0x18006e833`
- `CRYPT32!CertDeleteCertificateFromStore` at `0x18006e833`
- `CRYPT32!CertDuplicateCertificateContext` at `0x18006e810`
- `CRYPT32!CertDuplicateCertificateContext` at `0x18006e810`
- `CRYPT32!CertCompareCertificate` at `0x18006e7f9`
- `CRYPT32!CertCompareCertificate` at `0x18006e7f9`

## string_xrefs

- `0x18006e74e`: `onecoreuap\ds\ext\live\identity\ntservice\lib\svccommon\configuration.cpp`
- `0x18006e7ba`: `onecoreuap\ds\ext\live\identity\ntservice\lib\svccommon\configuration.cpp`
- `0x18006e854`: `onecoreuap\ds\ext\live\identity\ntservice\lib\svccommon\configuration.cpp`
- `0x18006e843`: `CertDeleteCertificateFromStore failed with hr=0x%x`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CleanupCertificateAuthority(void *pvPara, __int64 a2)
{
  HCERTSTORE v4; // rax
  HCERTSTORE v5; // rcx
  signed int LastError; // eax
  const CERT_CONTEXT *v7; // rdx
  unsigned int v8; // edi
  __int64 v9; // rax
  const CERT_CONTEXT *v10; // rax
  DWORD v11; // eax
  const unsigned __int16 *v12; // r9
  unsigned int v13; // r8d
  PCCERT_CONTEXT v14; // rbx
  unsigned int v15; // ebx
  const unsigned __int16 *pvParaa; // [rsp+20h] [rbp-58h]
  void *pvParab; // [rsp+20h] [rbp-58h]
  void **v19; // [rsp+30h] [rbp-48h] BYREF
  HCERTSTORE hCertStore; // [rsp+38h] [rbp-40h]
  int v21; // [rsp+40h] [rbp-38h]
  _QWORD v22[6]; // [rsp+48h] [rbp-30h] BYREF
  signed int v23; // [rsp+B0h] [rbp+38h] BYREF

  v23 = 0;
  hCertStore = 0;
  v19 = &SmartHCERTSTORE::`vftable';
  v21 = 1;
  v22[0] = "CleanupCertificateAuthority";
  v22[1] = &v23;
  v22[2] = 0;
  v22[3] = 0;
  MsaTracingInternal::TraceFunctionEnter(
    (MsaTracingInternal *)"onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\configuration.cpp",
    "CleanupCertificateAuthority",
    (const char *)0x74,
    0,
    pvParaa);
  v4 = CertOpenStore((LPCSTR)0xA, 0, 0, 0x20000u, pvPara);
  SmartPtr<void *>::Attach(&v19, v4);
  v5 = hCertStore;
  if ( hCertStore )
    goto LABEL_7;
  LastError = GetLastError();
  if ( LastError > 0 )
    LastError = (unsigned __int16)LastError | 0x80070000;
  v23 = LastError;
  if ( LastError >= 0 )
  {
    v5 = hCertStore;
LABEL_7:
    v7 = 0;
    while ( 1 )
    {
      v14 = CertEnumCertificatesInStore(v5, v7);
      if ( !v14 )
        goto LABEL_18;
      v8 = 0;
      if ( *(_QWORD *)(a2 + 8) )
      {
        while ( 1 )
        {
          v9 = ATL::CAtlArray<SmartPCCERT_CONTEXT,ATL::CElementTraits<SmartPCCERT_CONTEXT>>::operator[](a2, v8);
          if ( CertCompareCertificate(0x10001u, v14->pCertInfo, *(PCERT_INFO *)(*(_QWORD *)(v9 + 8) + 24LL)) )
            break;
          if ( (unsigned __int64)++v8 >= *(_QWORD *)(a2 + 8) )
            goto LABEL_11;
        }
      }
      else
      {
LABEL_11:
        v10 = CertDuplicateCertificateContext(v14);
        if ( v10 )
        {
          if ( CertDeleteCertificateFromStore(v10) )
            goto LABEL_16;
          v11 = GetLastError();
          v12 = L"CertDeleteCertificateFromStore failed with hr=0x%x";
          v13 = 155;
        }
        else
        {
          v11 = GetLastError();
          v12 = L"CertDuplicateCertificateContext failed with hr=0x%x";
          v13 = 149;
        }
        LODWORD(pvParab) = v11;
        TracePrintW(
          2u,
          "onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\configuration.cpp",
          v13,
          v12,
          pvParab);
      }
LABEL_16:
      v7 = v14;
      v5 = hCertStore;
    }
  }
  Telemetry::IfFailExit(
    "onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\configuration.cpp",
    "CleanupCertificateAuthority",
    0x7Eu,
    LastError,
    "hr = HRESULT_FROM_WIN32(GetLastError())");
LABEL_18:
  v15 = v23;
  CTraceFuncW<long>::~CTraceFuncW<long>((__int64)v22);
  SmartHCERTSTORE::~SmartHCERTSTORE((SmartHCERTSTORE *)&v19);
  return v15;
}

```

## disassembly

```asm
0x18006e6f0  push    rbp
0x18006e6f2  push    rbx
0x18006e6f3  push    rsi
0x18006e6f4  push    rdi
0x18006e6f5  mov     rbp, rsp
0x18006e6f8  sub     rsp, 78h
0x18006e6fc  mov     rsi, rdx
0x18006e6ff  mov     rbx, rcx
0x18006e702  mov     [rbp+arg_10], 0
0x18006e709  xor     eax, eax
0x18006e70b  mov     [rbp+hCertStore], rax
0x18006e70f  lea     rax, ??_7SmartHCERTSTORE@@6B@; const SmartHCERTSTORE::`vftable'
0x18006e716  mov     [rbp+var_48], rax
0x18006e71a  mov     [rbp+var_38], 1
0x18006e721  lea     rdi, aCleanupcertifi; "CleanupCertificateAuthority"
0x18006e728  mov     [rbp+var_30], rdi
0x18006e72c  lea     rax, [rbp+arg_10]
0x18006e730  mov     [rbp+var_28], rax
0x18006e734  mov     [rbp+var_20], 0
0x18006e73c  mov     [rbp+var_18], 0
0x18006e744  xor     r9d, r9d; unsigned int
0x18006e747  lea     r8d, [r9+74h]; char *
0x18006e74b  mov     rdx, rdi; char *
0x18006e74e  lea     rcx, aOnecoreuapDsEx_16; "onecoreuap\\ds\\ext\\live\\identity\\nt"...
0x18006e755  call    ?TraceFunctionEnter@MsaTracingInternal@@YAKPEBD0KPEBG@Z; MsaTracingInternal::TraceFunctionEnter(char const *,char const *,ulong,ushort const *)
0x18006e75a  nop
0x18006e75b  mov     [rsp+78h+pvPara], rbx; pvPara
0x18006e760  mov     r9d, 20000h; dwFlags
0x18006e766  xor     r8d, r8d; hCryptProv
0x18006e769  xor     edx, edx; dwEncodingType
0x18006e76b  lea     ecx, [rdx+0Ah]; lpszStoreProvider
0x18006e76e  call    cs:__imp_CertOpenStore
0x18006e774  mov     rdx, rax
0x18006e777  lea     rcx, [rbp+var_48]
0x18006e77b  call    ?Attach@?$SmartPtr@PEAX@@QEAAXPEAX@Z; SmartPtr<void *>::Attach(void *)
0x18006e780  mov     rcx, [rbp+hCertStore]
0x18006e784  test    rcx, rcx
0x18006e787  jnz     short loc_18006E7CF
0x18006e789  call    cs:__imp_GetLastError
0x18006e78f  test    eax, eax
0x18006e791  jle     short loc_18006E79B
0x18006e793  movzx   eax, ax
0x18006e796  or      eax, 80070000h
0x18006e79b  mov     [rbp+arg_10], eax
0x18006e79e  test    eax, eax
0x18006e7a0  jns     short loc_18006E7CB
0x18006e7a2  lea     r8, aHrHresultFromW_10; "hr = HRESULT_FROM_WIN32(GetLastError())"
0x18006e7a9  mov     [rsp+78h+pvPara], r8; char *
0x18006e7ae  mov     r9d, eax; int
0x18006e7b1  mov     r8d, 7Eh ; '~'; unsigned int
0x18006e7b7  mov     rdx, rdi; char *
0x18006e7ba  lea     rcx, aOnecoreuapDsEx_16; "onecoreuap\\ds\\ext\\live\\identity\\nt"...
0x18006e7c1  call    ?IfFailExit@Telemetry@@SAXPEBD0KJ0@Z; Telemetry::IfFailExit(char const *,char const *,ulong,long,char const *)
0x18006e7c6  jmp     loc_18006E87E
0x18006e7cb  mov     rcx, [rbp+hCertStore]
0x18006e7cf  xor     edx, edx
0x18006e7d1  jmp     loc_18006E86C
0x18006e7d6  xor     edi, edi
0x18006e7d8  cmp     [rsi+8], rdi
0x18006e7dc  jbe     short loc_18006E80D
0x18006e7de  mov     edx, edi
0x18006e7e0  mov     rcx, rsi
0x18006e7e3  call    ??A?$CAtlArray@VSmartPCCERT_CONTEXT@@V?$CElementTraits@VSmartPCCERT_CONTEXT@@@ATL@@@ATL@@QEAAAEAVSmartPCCERT_CONTEXT@@_K@Z; ATL::CAtlArray<SmartPCCERT_CONTEXT,ATL::CElementTraits<SmartPCCERT_CONTEXT>>::operator[](unsigned __int64)
0x18006e7e8  mov     r8, [rax+8]
0x18006e7ec  mov     r8, [r8+18h]; pCertId2
0x18006e7f0  mov     rdx, [rbx+18h]; pCertId1
0x18006e7f4  mov     ecx, 10001h; dwCertEncodingType
0x18006e7f9  call    cs:__imp_CertCompareCertificate
0x18006e7ff  test    eax, eax
0x18006e801  jnz     short loc_18006E865
0x18006e803  inc     edi
0x18006e805  mov     eax, edi
0x18006e807  cmp     rax, [rsi+8]
0x18006e80b  jb      short loc_18006E7DE
0x18006e80d  mov     rcx, rbx; pCertContext
0x18006e810  call    cs:__imp_CertDuplicateCertificateContext
0x18006e816  test    rax, rax
0x18006e819  jnz     short loc_18006E830
0x18006e81b  call    cs:__imp_GetLastError
0x18006e821  lea     r9, aCertduplicatec_0; "CertDuplicateCertificateContext failed "...
0x18006e828  mov     r8d, 95h
0x18006e82e  jmp     short loc_18006E850
0x18006e830  mov     rcx, rax; pCertContext
0x18006e833  call    cs:__imp_CertDeleteCertificateFromStore
0x18006e839  test    eax, eax
0x18006e83b  jnz     short loc_18006E865
0x18006e83d  call    cs:__imp_GetLastError
0x18006e843  lea     r9, aCertdeletecert_0; "CertDeleteCertificateFromStore failed w"...
0x18006e84a  mov     r8d, 9Bh; unsigned int
0x18006e850  mov     dword ptr [rsp+78h+pvPara], eax
0x18006e854  lea     rdx, aOnecoreuapDsEx_16; "onecoreuap\\ds\\ext\\live\\identity\\nt"...
0x18006e85b  mov     ecx, 2; unsigned __int8
0x18006e860  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x18006e865  mov     rdx, rbx; pPrevCertContext
0x18006e868  mov     rcx, [rbp+hCertStore]; hCertStore
0x18006e86c  call    cs:__imp_CertEnumCertificatesInStore
0x18006e872  test    rax, rax
0x18006e875  mov     rbx, rax
0x18006e878  jnz     loc_18006E7D6
0x18006e87e  mov     ebx, [rbp+arg_10]
0x18006e881  lea     rcx, [rbp+var_30]
0x18006e885  call    ??1?$CTraceFuncW@J@@QEAA@XZ; CTraceFuncW<long>::~CTraceFuncW<long>(void)
0x18006e88a  nop
0x18006e88b  lea     rcx, [rbp+var_48]; this
0x18006e88f  call    ??1SmartHCERTSTORE@@UEAA@XZ; SmartHCERTSTORE::~SmartHCERTSTORE(void)
0x18006e894  mov     eax, ebx
0x18006e896  add     rsp, 78h
0x18006e89a  pop     rdi
0x18006e89b  pop     rsi
0x18006e89c  pop     rbx
0x18006e89d  pop     rbp
0x18006e89e  retn
```
