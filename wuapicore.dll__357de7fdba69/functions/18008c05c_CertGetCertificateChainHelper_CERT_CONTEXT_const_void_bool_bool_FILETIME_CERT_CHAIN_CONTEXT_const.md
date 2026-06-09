# CertGetCertificateChainHelper(_CERT_CONTEXT const *,void *,bool,bool,_FILETIME *,_CERT_CHAIN_CONTEXT const * *)

- ea: `0x18008c05c`
- end: `0x18008c3a8`
- name: `?CertGetCertificateChainHelper@@YAJPEBU_CERT_CONTEXT@@PEAX_N2PEAU_FILETIME@@PEAPEBU_CERT_CHAIN_CONTEXT@@@Z`
- size: `844`
- prototype: `__int64 __usercall@<rax>(PCCERT_CONTEXT pCertContext@<rcx>, void *@<rdx>, bool@<r8b>, bool@<r9b>, struct _FILETIME *, const struct _CERT_CHAIN_CONTEXT **)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x18008b990`

## callees

- `0x18008c05c`
- `0x18008c3b0`
- `0x18008e3dc`
- `0x180090bc8`
- `0x18009ae75`
- `0x18009b050`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008c162`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008c17b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008c2a6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008c2bf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008c162`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008c17b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008c2a6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008c2bf`
- `CRYPT32!CertGetCertificateChain` at `0x18008c158`
- `CRYPT32!CertGetCertificateChain` at `0x18008c29c`
- `CRYPT32!CertGetCertificateChain` at `0x18008c158`
- `CRYPT32!CertGetCertificateChain` at `0x18008c29c`
- `CRYPT32!CertFreeCertificateChainEngine` at `0x18008c244`
- `CRYPT32!CertFreeCertificateChainEngine` at `0x18008c378`
- `CRYPT32!CertFreeCertificateChainEngine` at `0x18008c244`
- `CRYPT32!CertFreeCertificateChainEngine` at `0x18008c378`
- `CRYPT32!CertCreateCertificateChainEngine` at `0x18008c257`
- `CRYPT32!CertCreateCertificateChainEngine` at `0x18008c257`
- `CRYPT32!CertCloseStore` at `0x18008c1ef`
- `CRYPT32!CertCloseStore` at `0x18008c365`
- `CRYPT32!CertCloseStore` at `0x18008c1ef`
- `CRYPT32!CertCloseStore` at `0x18008c365`
- `CRYPT32!CertFreeCertificateChain` at `0x18008c215`
- `CRYPT32!CertFreeCertificateChain` at `0x18008c26a`
- `CRYPT32!CertFreeCertificateChain` at `0x18008c2df`
- `CRYPT32!CertFreeCertificateChain` at `0x18008c337`
- `CRYPT32!CertFreeCertificateChain` at `0x18008c353`
- `CRYPT32!CertFreeCertificateChain` at `0x18008c215`
- `CRYPT32!CertFreeCertificateChain` at `0x18008c26a`
- `CRYPT32!CertFreeCertificateChain` at `0x18008c2df`
- `CRYPT32!CertFreeCertificateChain` at `0x18008c337`
- `CRYPT32!CertFreeCertificateChain` at `0x18008c353`

## string_xrefs

- `0x18008c0fc`: `SOFTWARE\Policies\Microsoft\Windows\WindowsUpdate`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall CertGetCertificateChainHelper(
        PCCERT_CONTEXT pCertContext,
        void *a2,
        __int64 a3,
        __int64 a4,
        struct _FILETIME *pTime,
        const struct _CERT_CHAIN_CONTEXT **ppChainContext)
{
  signed int SubCAStore; // ebx
  DWORD dwFlags; // esi
  HKEY v9; // rcx
  const wchar_t *v10; // r8
  signed int LastError; // eax
  signed int v12; // ecx
  signed int v13; // eax
  signed int v14; // eax
  signed int v15; // ecx
  signed int v16; // eax
  const CERT_CHAIN_CONTEXT *v17; // rcx
  PCCERT_CHAIN_CONTEXT v18; // rax
  const struct _CERT_CHAIN_CONTEXT *v19; // rax
  PCERT_CHAIN_PARA pChainPara; // [rsp+20h] [rbp-E0h]
  int v22; // [rsp+40h] [rbp-C0h] BYREF
  _DWORD v23[2]; // [rsp+48h] [rbp-B8h] BYREF
  const char *v24; // [rsp+50h] [rbp-B0h]
  _CERT_CHAIN_ENGINE_CONFIG pConfig; // [rsp+60h] [rbp-A0h] BYREF
  int v26; // [rsp+B0h] [rbp-50h]
  struct _CERT_CHAIN_PARA v27; // [rsp+C0h] [rbp-40h] BYREF
  _DWORD *v28; // [rsp+110h] [rbp+10h]
  PCCERT_CHAIN_CONTEXT pChainContext[2]; // [rsp+120h] [rbp+20h] BYREF
  HCERTSTORE hCertStore[2]; // [rsp+130h] [rbp+30h] BYREF
  HCERTCHAINENGINE hChainEngine[2]; // [rsp+140h] [rbp+40h] BYREF

  SubCAStore = 0;
  hChainEngine[0] = 0;
  hChainEngine[1] = 0;
  *(_OWORD *)hCertStore = 0u;
  memset_0(&v27, 0, 0x60u);
  v27.cbSize = 96;
  v23[0] = 16;
  v23[1] = 2;
  v24 = "1.3.6.1.4.1.311.72.1.1";
  v28 = v23;
  dwFlags = 0x40000000;
  v22 = 0;
  ReadDwordPolicyAsBool(v9, L"SOFTWARE\\Policies\\Microsoft\\Windows\\WindowsUpdate", v10, &v22);
  if ( v22 )
  {
    dwFlags = 0;
    WUTrace(0, 0, 32, 4, 0, L"CertGetCertificateChain - revocation checking was disabled by policy.");
  }
  if ( !CertGetCertificateChain(0, pCertContext, pTime, 0, &v27, dwFlags, 0, ppChainContext) )
  {
    LastError = GetLastError();
    v12 = (unsigned __int16)LastError | 0x80070000;
    if ( LastError <= 0 )
      v12 = LastError;
    if ( v12 >= 0 )
    {
      SubCAStore = -2147467259;
    }
    else
    {
      v13 = GetLastError();
      SubCAStore = (unsigned __int16)v13 | 0x80070000;
      if ( v13 <= 0 )
        SubCAStore = v13;
    }
    goto LABEL_32;
  }
  if ( ((*ppChainContext)->TrustStatus.dwErrorStatus & 4) == 0 )
    goto LABEL_38;
  memset_0(&pConfig, 0, 0x58u);
  pChainContext[0] = 0;
  pChainContext[1] = 0;
  WUTrace(0, 0, 32, 4, 0, L"CertGetCertificateChain failed. Retrying with pinned SubCAs set.");
  if ( hCertStore[1] )
  {
    CertCloseStore(hCertStore[1], 0);
    hCertStore[1] = 0;
  }
  SubCAStore = CreateSubCAStore(&hCertStore[1]);
  if ( SubCAStore < 0 )
  {
    if ( pChainContext[1] )
      CertFreeCertificateChain(pChainContext[1]);
LABEL_33:
    LODWORD(pChainPara) = SubCAStore;
    WUTrace(0, 0, 32, 1, pChainPara, L"CertGetCertificateChain failed. SSL : %ws, StrongSign : %ws", L"No", L"Yes");
    goto LABEL_38;
  }
  pConfig.cbSize = 88;
  pConfig.dwFlags = 0x2000;
  pConfig.hExclusiveRoot = hCertStore[1];
  v26 |= 1u;
  if ( hChainEngine[1] )
  {
    CertFreeCertificateChainEngine(hChainEngine[1]);
    hChainEngine[1] = 0;
  }
  if ( !CertCreateCertificateChainEngine(&pConfig, &hChainEngine[1]) )
    goto LABEL_23;
  if ( pChainContext[1] )
  {
    CertFreeCertificateChain(pChainContext[1]);
    pChainContext[1] = 0;
  }
  if ( !CertGetCertificateChain(hChainEngine[1], pCertContext, pTime, 0, &v27, dwFlags, 0, &pChainContext[1]) )
  {
LABEL_23:
    v14 = GetLastError();
    v15 = (unsigned __int16)v14 | 0x80070000;
    if ( v14 <= 0 )
      v15 = v14;
    if ( v15 >= 0 )
    {
      SubCAStore = -2147467259;
    }
    else
    {
      v16 = GetLastError();
      SubCAStore = (unsigned __int16)v16 | 0x80070000;
      if ( v16 <= 0 )
        SubCAStore = v16;
    }
    if ( pChainContext[1] )
      CertFreeCertificateChain(pChainContext[1]);
LABEL_32:
    if ( SubCAStore >= 0 )
      goto LABEL_38;
    goto LABEL_33;
  }
  v17 = pChainContext[1];
  v18 = pChainContext[1];
  if ( (pChainContext[1]->TrustStatus.dwInfoStatus & 0x2000) != 0 )
  {
    CertFreeCertificateChain(*ppChainContext);
    v19 = pChainContext[1];
    v17 = 0;
    pChainContext[1] = 0;
    *ppChainContext = v19;
    v18 = 0;
  }
  if ( v18 )
    CertFreeCertificateChain(v17);
LABEL_38:
  if ( hCertStore[1] )
  {
    CertCloseStore(hCertStore[1], 0);
    hCertStore[1] = 0;
  }
  if ( hChainEngine[1] )
    CertFreeCertificateChainEngine(hChainEngine[1]);
  return (unsigned int)SubCAStore;
}

```

## disassembly

```asm
0x18008c05c  mov     [rsp-8+arg_8], rbx
0x18008c061  mov     [rsp-8+arg_10], rsi
0x18008c066  push    rbp
0x18008c067  push    rdi
0x18008c068  push    r12
0x18008c06a  push    r14
0x18008c06c  push    r15
0x18008c06e  lea     rbp, [rsp-60h]
0x18008c073  sub     rsp, 160h
0x18008c07a  mov     rax, cs:__security_cookie
0x18008c081  xor     rax, rsp
0x18008c084  mov     [rbp+80h+var_30], rax
0x18008c088  mov     r14, rcx
0x18008c08b  mov     r15, [rbp+80h+pTime]
0x18008c092  mov     rdi, [rbp+80h+arg_28]
0x18008c099  xor     r12d, r12d
0x18008c09c  mov     ebx, r12d
0x18008c09f  xorps   xmm0, xmm0
0x18008c0a2  movups  xmmword ptr [rbp+80h+hChainEngine], xmm0
0x18008c0a6  mov     [rbp+80h+hChainEngine+8], r12
0x18008c0aa  movups  xmmword ptr [rbp+80h+hCertStore], xmm0
0x18008c0ae  mov     [rbp+80h+hCertStore+8], r12
0x18008c0b2  lea     esi, [r12+60h]
0x18008c0b7  mov     r8d, esi; Size
0x18008c0ba  xor     edx, edx; Val
0x18008c0bc  lea     rcx, [rbp+80h+var_C0]; void *
0x18008c0c0  call    memset_0
0x18008c0c5  mov     [rbp+80h+var_C0.cbSize], esi
0x18008c0c8  mov     [rsp+180h+var_138], 10h
0x18008c0d0  mov     [rsp+180h+var_134], 2
0x18008c0d8  lea     rax, a1361413117211; "1.3.6.1.4.1.311.72.1.1"
0x18008c0df  mov     [rsp+180h+var_130], rax
0x18008c0e4  lea     rax, [rsp+180h+var_138]
0x18008c0e9  mov     [rbp+80h+var_70], rax
0x18008c0ed  mov     esi, 40000000h
0x18008c0f2  mov     [rsp+180h+var_140], r12d
0x18008c0f7  lea     r9, [rsp+180h+var_140]; int *
0x18008c0fc  lea     rdx, aSoftwarePolici; "SOFTWARE\\Policies\\Microsoft\\Windows"...
0x18008c103  call    ?ReadDwordPolicyAsBool@@YAJPEAUHKEY__@@PEB_W1PEAH@Z; ReadDwordPolicyAsBool(HKEY__ *,wchar_t const *,wchar_t const *,int *)
0x18008c108  cmp     [rsp+180h+var_140], r12d
0x18008c10d  jz      short loc_18008C136
0x18008c10f  mov     esi, r12d
0x18008c112  lea     rax, aCertgetcertifi_3; "CertGetCertificateChain - revocation ch"...
0x18008c119  mov     qword ptr [rsp+180h+dwFlags], rax
0x18008c11e  mov     [rsp+180h+pChainPara], r12
0x18008c123  xor     edx, edx
0x18008c125  xor     ecx, ecx
0x18008c127  lea     r9d, [r12+4]
0x18008c12c  lea     r8d, [r12+20h]
0x18008c131  call    ?WUTrace@@YAXPEBDKW4WUTraceLoggingCategory@@IJPEB_WZZ; WUTrace(char const *,ulong,WUTraceLoggingCategory,uint,long,wchar_t const *,...)
0x18008c136  mov     [rsp+180h+ppChainContext], rdi; ppChainContext
0x18008c13b  mov     [rsp+180h+pvReserved], r12; pvReserved
0x18008c140  mov     [rsp+180h+dwFlags], esi; dwFlags
0x18008c144  lea     rax, [rbp+80h+var_C0]
0x18008c148  mov     [rsp+180h+pChainPara], rax; pChainPara
0x18008c14d  xor     r9d, r9d; hAdditionalStore
0x18008c150  mov     r8, r15; pTime
0x18008c153  mov     rdx, r14; pCertContext
0x18008c156  xor     ecx, ecx; hChainEngine
0x18008c158  call    cs:__imp_CertGetCertificateChain
0x18008c15e  test    eax, eax
0x18008c160  jnz     short loc_18008C19A
0x18008c162  call    cs:__imp_GetLastError
0x18008c168  movzx   ecx, ax
0x18008c16b  mov     edi, 80070000h
0x18008c170  or      ecx, edi
0x18008c172  test    eax, eax
0x18008c174  cmovle  ecx, eax
0x18008c177  test    ecx, ecx
0x18008c179  jns     short loc_18008C190
0x18008c17b  call    cs:__imp_GetLastError
0x18008c181  movzx   ebx, ax
0x18008c184  or      ebx, edi
0x18008c186  test    eax, eax
0x18008c188  cmovle  ebx, eax
0x18008c18b  jmp     loc_18008C2E5
0x18008c190  mov     ebx, 80004005h
0x18008c195  jmp     loc_18008C2E5
0x18008c19a  mov     rax, [rdi]
0x18008c19d  test    byte ptr [rax+4], 4
0x18008c1a1  jz      loc_18008C35A
0x18008c1a7  xor     edx, edx; Val
0x18008c1a9  lea     r8d, [rdx+58h]; Size
0x18008c1ad  lea     rcx, [rsp+180h+pConfig]; void *
0x18008c1b2  call    memset_0
0x18008c1b7  xorps   xmm0, xmm0
0x18008c1ba  movups  xmmword ptr [rbp+80h+pChainContext], xmm0
0x18008c1be  mov     [rbp+80h+pChainContext+8], r12
0x18008c1c2  lea     rax, aCertgetcertifi_4; "CertGetCertificateChain failed. Retryin"...
0x18008c1c9  mov     qword ptr [rsp+180h+dwFlags], rax
0x18008c1ce  mov     [rsp+180h+pChainPara], r12
0x18008c1d3  xor     edx, edx
0x18008c1d5  xor     ecx, ecx
0x18008c1d7  lea     r9d, [rdx+4]
0x18008c1db  lea     r8d, [rdx+20h]
0x18008c1df  call    ?WUTrace@@YAXPEBDKW4WUTraceLoggingCategory@@IJPEB_WZZ; WUTrace(char const *,ulong,WUTraceLoggingCategory,uint,long,wchar_t const *,...)
0x18008c1e4  mov     rcx, [rbp+80h+hCertStore+8]; hCertStore
0x18008c1e8  test    rcx, rcx
0x18008c1eb  jz      short loc_18008C1F9
0x18008c1ed  xor     edx, edx; dwFlags
0x18008c1ef  call    cs:__imp_CertCloseStore
0x18008c1f5  mov     [rbp+80h+hCertStore+8], r12
0x18008c1f9  lea     rcx, [rbp+80h+hCertStore+8]; void **
0x18008c1fd  call    ?CreateSubCAStore@@YAJPEAPEAX@Z; CreateSubCAStore(void * *)
0x18008c202  mov     ebx, eax
0x18008c204  test    eax, eax
0x18008c206  jns     short loc_18008C220
0x18008c208  mov     rcx, [rbp+80h+pChainContext+8]; pChainContext
0x18008c20c  test    rcx, rcx
0x18008c20f  jz      loc_18008C2E9
0x18008c215  call    cs:__imp_CertFreeCertificateChain
0x18008c21b  jmp     loc_18008C2E9
0x18008c220  mov     [rsp+180h+pConfig.cbSize], 58h ; 'X'
0x18008c228  mov     [rbp+80h+pConfig.dwFlags], 2000h
0x18008c22f  mov     rax, [rbp+80h+hCertStore+8]
0x18008c233  mov     [rbp+80h+pConfig.hExclusiveRoot], rax
0x18008c237  or      [rbp+80h+var_D0], 1
0x18008c23b  mov     rcx, [rbp+80h+hChainEngine+8]; hChainEngine
0x18008c23f  test    rcx, rcx
0x18008c242  jz      short loc_18008C24E
0x18008c244  call    cs:__imp_CertFreeCertificateChainEngine
0x18008c24a  mov     [rbp+80h+hChainEngine+8], r12
0x18008c24e  lea     rdx, [rbp+80h+hChainEngine+8]; phChainEngine
0x18008c252  lea     rcx, [rsp+180h+pConfig]; pConfig
0x18008c257  call    cs:__imp_CertCreateCertificateChainEngine
0x18008c25d  test    eax, eax
0x18008c25f  jz      short loc_18008C2A6
0x18008c261  mov     rcx, [rbp+80h+pChainContext+8]; pChainContext
0x18008c265  test    rcx, rcx
0x18008c268  jz      short loc_18008C274
0x18008c26a  call    cs:__imp_CertFreeCertificateChain
0x18008c270  mov     [rbp+80h+pChainContext+8], r12
0x18008c274  lea     rax, [rbp+80h+pChainContext+8]
0x18008c278  mov     [rsp+180h+ppChainContext], rax; ppChainContext
0x18008c27d  mov     [rsp+180h+pvReserved], r12; pvReserved
0x18008c282  mov     [rsp+180h+dwFlags], esi; dwFlags
0x18008c286  lea     rax, [rbp+80h+var_C0]
0x18008c28a  mov     [rsp+180h+pChainPara], rax; pChainPara
0x18008c28f  xor     r9d, r9d; hAdditionalStore
0x18008c292  mov     r8, r15; pTime
0x18008c295  mov     rdx, r14; pCertContext
0x18008c298  mov     rcx, [rbp+80h+hChainEngine+8]; hChainEngine
0x18008c29c  call    cs:__imp_CertGetCertificateChain
0x18008c2a2  test    eax, eax
0x18008c2a4  jnz     short loc_18008C324
0x18008c2a6  call    cs:__imp_GetLastError
0x18008c2ac  movzx   ecx, ax
0x18008c2af  mov     edi, 80070000h
0x18008c2b4  or      ecx, edi
0x18008c2b6  test    eax, eax
0x18008c2b8  cmovle  ecx, eax
0x18008c2bb  test    ecx, ecx
0x18008c2bd  jns     short loc_18008C2D1
0x18008c2bf  call    cs:__imp_GetLastError
0x18008c2c5  movzx   ebx, ax
0x18008c2c8  or      ebx, edi
0x18008c2ca  test    eax, eax
0x18008c2cc  cmovle  ebx, eax
0x18008c2cf  jmp     short loc_18008C2D6
0x18008c2d1  mov     ebx, 80004005h
0x18008c2d6  mov     rcx, [rbp+80h+pChainContext+8]; pChainContext
0x18008c2da  test    rcx, rcx
0x18008c2dd  jz      short loc_18008C2E5
0x18008c2df  call    cs:__imp_CertFreeCertificateChain
0x18008c2e5  test    ebx, ebx
0x18008c2e7  jns     short loc_18008C35A
0x18008c2e9  lea     rax, aYes_2; "Yes"
0x18008c2f0  mov     [rsp+180h+ppChainContext], rax
0x18008c2f5  lea     rax, aNo_2; "No"
0x18008c2fc  mov     [rsp+180h+pvReserved], rax
0x18008c301  lea     rax, aCertgetcertifi_2; "CertGetCertificateChain failed. SSL : %"...
0x18008c308  mov     qword ptr [rsp+180h+dwFlags], rax
0x18008c30d  mov     dword ptr [rsp+180h+pChainPara], ebx
0x18008c311  xor     edx, edx
0x18008c313  xor     ecx, ecx
0x18008c315  lea     r9d, [rdx+1]
0x18008c319  lea     r8d, [rdx+20h]
0x18008c31d  call    ?WUTrace@@YAXPEBDKW4WUTraceLoggingCategory@@IJPEB_WZZ; WUTrace(char const *,ulong,WUTraceLoggingCategory,uint,long,wchar_t const *,...)
0x18008c322  jmp     short loc_18008C35A
0x18008c324  mov     rcx, [rbp+80h+pChainContext+8]
0x18008c328  mov     rax, rcx
0x18008c32b  test    dword ptr [rcx+8], 2000h
0x18008c332  jz      short loc_18008C34E
0x18008c334  mov     rcx, [rdi]; pChainContext
0x18008c337  call    cs:__imp_CertFreeCertificateChain
0x18008c33d  mov     rax, [rbp+80h+pChainContext+8]
0x18008c341  mov     rcx, r12; pChainContext
0x18008c344  mov     [rbp+80h+pChainContext+8], rcx
0x18008c348  mov     [rdi], rax
0x18008c34b  mov     rax, r12
0x18008c34e  test    rax, rax
0x18008c351  jz      short loc_18008C35A
0x18008c353  call    cs:__imp_CertFreeCertificateChain
0x18008c359  nop
0x18008c35a  mov     rcx, [rbp+80h+hCertStore+8]; hCertStore
0x18008c35e  test    rcx, rcx
0x18008c361  jz      short loc_18008C36F
0x18008c363  xor     edx, edx; dwFlags
0x18008c365  call    cs:__imp_CertCloseStore
0x18008c36b  mov     [rbp+80h+hCertStore+8], r12
0x18008c36f  mov     rcx, [rbp+80h+hChainEngine+8]; hChainEngine
0x18008c373  test    rcx, rcx
0x18008c376  jz      short loc_18008C37E
0x18008c378  call    cs:__imp_CertFreeCertificateChainEngine
0x18008c37e  mov     eax, ebx
0x18008c380  mov     rcx, [rbp+80h+var_30]
0x18008c384  xor     rcx, rsp; StackCookie
0x18008c387  call    __security_check_cookie
0x18008c38c  lea     r11, [rsp+180h+var_20]
0x18008c394  mov     rbx, [r11+38h]
0x18008c398  mov     rsi, [r11+40h]
0x18008c39c  mov     rsp, r11
0x18008c39f  pop     r15
0x18008c3a1  pop     r14
0x18008c3a3  pop     r12
0x18008c3a5  pop     rdi
0x18008c3a6  pop     rbp
0x18008c3a7  retn
```
