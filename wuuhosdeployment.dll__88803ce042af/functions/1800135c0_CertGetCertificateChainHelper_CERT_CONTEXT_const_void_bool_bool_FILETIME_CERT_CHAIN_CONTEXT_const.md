# CertGetCertificateChainHelper(_CERT_CONTEXT const *,void *,bool,bool,_FILETIME *,_CERT_CHAIN_CONTEXT const * *)

- ea: `0x1800135c0`
- end: `0x18001390c`
- name: `?CertGetCertificateChainHelper@@YAJPEBU_CERT_CONTEXT@@PEAX_N2PEAU_FILETIME@@PEAPEBU_CERT_CHAIN_CONTEXT@@@Z`
- size: `844`
- prototype: `__int64 __usercall@<rax>(PCCERT_CONTEXT pCertContext@<rcx>, void *@<rdx>, bool@<r8b>, bool@<r9b>, struct _FILETIME *, const struct _CERT_CHAIN_CONTEXT **)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x180013058`

## callees

- `0x18000956c`
- `0x1800135c0`
- `0x180013914`
- `0x18003e5ac`
- `0x180042630`
- `0x1800492e0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800136c6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800136df`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001380a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180013823`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800136c6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800136df`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001380a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180013823`
- `CRYPT32!CertCreateCertificateChainEngine` at `0x1800137bb`
- `CRYPT32!CertCreateCertificateChainEngine` at `0x1800137bb`
- `CRYPT32!CertFreeCertificateChain` at `0x180013779`
- `CRYPT32!CertFreeCertificateChain` at `0x1800137ce`
- `CRYPT32!CertFreeCertificateChain` at `0x180013843`
- `CRYPT32!CertFreeCertificateChain` at `0x18001389b`
- `CRYPT32!CertFreeCertificateChain` at `0x1800138b7`
- `CRYPT32!CertFreeCertificateChain` at `0x180013779`
- `CRYPT32!CertFreeCertificateChain` at `0x1800137ce`
- `CRYPT32!CertFreeCertificateChain` at `0x180013843`
- `CRYPT32!CertFreeCertificateChain` at `0x18001389b`
- `CRYPT32!CertFreeCertificateChain` at `0x1800138b7`
- `CRYPT32!CertCloseStore` at `0x180013753`
- `CRYPT32!CertCloseStore` at `0x1800138c9`
- `CRYPT32!CertCloseStore` at `0x180013753`
- `CRYPT32!CertCloseStore` at `0x1800138c9`
- `CRYPT32!CertFreeCertificateChainEngine` at `0x1800137a8`
- `CRYPT32!CertFreeCertificateChainEngine` at `0x1800138dc`
- `CRYPT32!CertFreeCertificateChainEngine` at `0x1800137a8`
- `CRYPT32!CertFreeCertificateChainEngine` at `0x1800138dc`
- `CRYPT32!CertGetCertificateChain` at `0x1800136bc`
- `CRYPT32!CertGetCertificateChain` at `0x180013800`
- `CRYPT32!CertGetCertificateChain` at `0x1800136bc`
- `CRYPT32!CertGetCertificateChain` at `0x180013800`

## string_xrefs

- `0x180013660`: `SOFTWARE\Policies\Microsoft\Windows\WindowsUpdate`

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
  int v21; // [rsp+40h] [rbp-C0h] BYREF
  _DWORD v22[2]; // [rsp+48h] [rbp-B8h] BYREF
  const char *v23; // [rsp+50h] [rbp-B0h]
  _BYTE pConfig[88]; // [rsp+60h] [rbp-A0h] BYREF
  struct _CERT_CHAIN_PARA pChainPara[3]; // [rsp+C0h] [rbp-40h] BYREF
  PCCERT_CHAIN_CONTEXT pChainContext[2]; // [rsp+120h] [rbp+20h] BYREF
  HCERTSTORE hCertStore[2]; // [rsp+130h] [rbp+30h] BYREF
  HCERTCHAINENGINE hChainEngine[2]; // [rsp+140h] [rbp+40h] BYREF

  SubCAStore = 0;
  hChainEngine[0] = 0;
  hChainEngine[1] = 0;
  *(_OWORD *)hCertStore = 0u;
  memset(pChainPara, 0, sizeof(pChainPara));
  pChainPara[0].cbSize = 96;
  v22[0] = 16;
  v22[1] = 2;
  v23 = "1.3.6.1.4.1.311.72.1.1";
  *(_QWORD *)&pChainPara[2].RequestedUsage.Usage.cUsageIdentifier = v22;
  dwFlags = 0x40000000;
  v21 = 0;
  ReadDwordPolicyAsBool(v9, L"SOFTWARE\\Policies\\Microsoft\\Windows\\WindowsUpdate", v10, &v21);
  if ( v21 )
  {
    dwFlags = 0;
    WUTrace(0, 0, 32, 4);
  }
  if ( !CertGetCertificateChain(0, pCertContext, pTime, 0, pChainPara, dwFlags, 0, ppChainContext) )
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
  memset(pConfig, 0, sizeof(pConfig));
  pChainContext[0] = 0;
  pChainContext[1] = 0;
  WUTrace(0, 0, 32, 4);
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
    WUTrace(0, 0, 32, 1);
    goto LABEL_38;
  }
  *(_DWORD *)pConfig = 88;
  *(_DWORD *)&pConfig[48] = 0x2000;
  *(HCERTSTORE *)&pConfig[64] = hCertStore[1];
  *(_DWORD *)&pConfig[80] |= 1u;
  if ( hChainEngine[1] )
  {
    CertFreeCertificateChainEngine(hChainEngine[1]);
    hChainEngine[1] = 0;
  }
  if ( !CertCreateCertificateChainEngine((PCERT_CHAIN_ENGINE_CONFIG)pConfig, &hChainEngine[1]) )
    goto LABEL_23;
  if ( pChainContext[1] )
  {
    CertFreeCertificateChain(pChainContext[1]);
    pChainContext[1] = 0;
  }
  if ( !CertGetCertificateChain(hChainEngine[1], pCertContext, pTime, 0, pChainPara, dwFlags, 0, &pChainContext[1]) )
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
0x1800135c0  mov     [rsp-8+arg_8], rbx
0x1800135c5  mov     [rsp-8+arg_10], rsi
0x1800135ca  push    rbp
0x1800135cb  push    rdi
0x1800135cc  push    r12
0x1800135ce  push    r14
0x1800135d0  push    r15
0x1800135d2  lea     rbp, [rsp-60h]
0x1800135d7  sub     rsp, 160h
0x1800135de  mov     rax, cs:__security_cookie
0x1800135e5  xor     rax, rsp
0x1800135e8  mov     [rbp+80h+var_30], rax
0x1800135ec  mov     r14, rcx
0x1800135ef  mov     r15, [rbp+80h+pTime]
0x1800135f6  mov     rdi, [rbp+80h+arg_28]
0x1800135fd  xor     r12d, r12d
0x180013600  mov     ebx, r12d
0x180013603  xorps   xmm0, xmm0
0x180013606  movups  xmmword ptr [rbp+80h+hChainEngine], xmm0
0x18001360a  mov     [rbp+80h+hChainEngine+8], r12
0x18001360e  movups  xmmword ptr [rbp+80h+hCertStore], xmm0
0x180013612  mov     [rbp+80h+hCertStore+8], r12
0x180013616  lea     esi, [r12+60h]
0x18001361b  mov     r8d, esi; Size
0x18001361e  xor     edx, edx; Val
0x180013620  lea     rcx, [rbp+80h+var_C0]; void *
0x180013624  call    memset
0x180013629  mov     [rbp+80h+var_C0.cbSize], esi
0x18001362c  mov     [rsp+180h+var_138], 10h
0x180013634  mov     [rsp+180h+var_134], 2
0x18001363c  lea     rax, a1361413117211; "1.3.6.1.4.1.311.72.1.1"
0x180013643  mov     [rsp+180h+var_130], rax
0x180013648  lea     rax, [rsp+180h+var_138]
0x18001364d  mov     [rbp+80h+var_70], rax
0x180013651  mov     esi, 40000000h
0x180013656  mov     [rsp+180h+var_140], r12d
0x18001365b  lea     r9, [rsp+180h+var_140]; int *
0x180013660  lea     rdx, aSoftwarePolici; "SOFTWARE\\Policies\\Microsoft\\Windows"...
0x180013667  call    ?ReadDwordPolicyAsBool@@YAJPEAUHKEY__@@PEB_W1PEAH@Z; ReadDwordPolicyAsBool(HKEY__ *,wchar_t const *,wchar_t const *,int *)
0x18001366c  cmp     [rsp+180h+var_140], r12d
0x180013671  jz      short loc_18001369A
0x180013673  mov     esi, r12d
0x180013676  lea     rax, aCertgetcertifi_3; "CertGetCertificateChain - revocation ch"...
0x18001367d  mov     qword ptr [rsp+180h+dwFlags], rax
0x180013682  mov     [rsp+180h+pChainPara], r12
0x180013687  xor     edx, edx
0x180013689  xor     ecx, ecx
0x18001368b  lea     r9d, [r12+4]
0x180013690  lea     r8d, [r12+20h]
0x180013695  call    ?WUTrace@@YAXPEBDKW4WUTraceLoggingCategory@@IJPEB_WZZ; WUTrace(char const *,ulong,WUTraceLoggingCategory,uint,long,wchar_t const *,...)
0x18001369a  mov     [rsp+180h+ppChainContext], rdi; ppChainContext
0x18001369f  mov     [rsp+180h+pvReserved], r12; pvReserved
0x1800136a4  mov     [rsp+180h+dwFlags], esi; dwFlags
0x1800136a8  lea     rax, [rbp+80h+var_C0]
0x1800136ac  mov     [rsp+180h+pChainPara], rax; pChainPara
0x1800136b1  xor     r9d, r9d; hAdditionalStore
0x1800136b4  mov     r8, r15; pTime
0x1800136b7  mov     rdx, r14; pCertContext
0x1800136ba  xor     ecx, ecx; hChainEngine
0x1800136bc  call    cs:__imp_CertGetCertificateChain
0x1800136c2  test    eax, eax
0x1800136c4  jnz     short loc_1800136FE
0x1800136c6  call    cs:__imp_GetLastError
0x1800136cc  movzx   ecx, ax
0x1800136cf  mov     edi, 80070000h
0x1800136d4  or      ecx, edi
0x1800136d6  test    eax, eax
0x1800136d8  cmovle  ecx, eax
0x1800136db  test    ecx, ecx
0x1800136dd  jns     short loc_1800136F4
0x1800136df  call    cs:__imp_GetLastError
0x1800136e5  movzx   ebx, ax
0x1800136e8  or      ebx, edi
0x1800136ea  test    eax, eax
0x1800136ec  cmovle  ebx, eax
0x1800136ef  jmp     loc_180013849
0x1800136f4  mov     ebx, 80004005h
0x1800136f9  jmp     loc_180013849
0x1800136fe  mov     rax, [rdi]
0x180013701  test    byte ptr [rax+4], 4
0x180013705  jz      loc_1800138BE
0x18001370b  xor     edx, edx; Val
0x18001370d  lea     r8d, [rdx+58h]; Size
0x180013711  lea     rcx, [rsp+180h+pConfig]; void *
0x180013716  call    memset
0x18001371b  xorps   xmm0, xmm0
0x18001371e  movups  xmmword ptr [rbp+80h+pChainContext], xmm0
0x180013722  mov     [rbp+80h+pChainContext+8], r12
0x180013726  lea     rax, aCertgetcertifi_4; "CertGetCertificateChain failed. Retryin"...
0x18001372d  mov     qword ptr [rsp+180h+dwFlags], rax
0x180013732  mov     [rsp+180h+pChainPara], r12
0x180013737  xor     edx, edx
0x180013739  xor     ecx, ecx
0x18001373b  lea     r9d, [rdx+4]
0x18001373f  lea     r8d, [rdx+20h]
0x180013743  call    ?WUTrace@@YAXPEBDKW4WUTraceLoggingCategory@@IJPEB_WZZ; WUTrace(char const *,ulong,WUTraceLoggingCategory,uint,long,wchar_t const *,...)
0x180013748  mov     rcx, [rbp+80h+hCertStore+8]; hCertStore
0x18001374c  test    rcx, rcx
0x18001374f  jz      short loc_18001375D
0x180013751  xor     edx, edx; dwFlags
0x180013753  call    cs:__imp_CertCloseStore
0x180013759  mov     [rbp+80h+hCertStore+8], r12
0x18001375d  lea     rcx, [rbp+80h+hCertStore+8]; void **
0x180013761  call    ?CreateSubCAStore@@YAJPEAPEAX@Z; CreateSubCAStore(void * *)
0x180013766  mov     ebx, eax
0x180013768  test    eax, eax
0x18001376a  jns     short loc_180013784
0x18001376c  mov     rcx, [rbp+80h+pChainContext+8]; pChainContext
0x180013770  test    rcx, rcx
0x180013773  jz      loc_18001384D
0x180013779  call    cs:__imp_CertFreeCertificateChain
0x18001377f  jmp     loc_18001384D
0x180013784  mov     [rsp+180h+pConfig.cbSize], 58h ; 'X'
0x18001378c  mov     [rbp+80h+pConfig.dwFlags], 2000h
0x180013793  mov     rax, [rbp+80h+hCertStore+8]
0x180013797  mov     [rbp+80h+pConfig.hExclusiveRoot], rax
0x18001379b  or      [rbp+80h+var_D0], 1
0x18001379f  mov     rcx, [rbp+80h+hChainEngine+8]; hChainEngine
0x1800137a3  test    rcx, rcx
0x1800137a6  jz      short loc_1800137B2
0x1800137a8  call    cs:__imp_CertFreeCertificateChainEngine
0x1800137ae  mov     [rbp+80h+hChainEngine+8], r12
0x1800137b2  lea     rdx, [rbp+80h+hChainEngine+8]; phChainEngine
0x1800137b6  lea     rcx, [rsp+180h+pConfig]; pConfig
0x1800137bb  call    cs:__imp_CertCreateCertificateChainEngine
0x1800137c1  test    eax, eax
0x1800137c3  jz      short loc_18001380A
0x1800137c5  mov     rcx, [rbp+80h+pChainContext+8]; pChainContext
0x1800137c9  test    rcx, rcx
0x1800137cc  jz      short loc_1800137D8
0x1800137ce  call    cs:__imp_CertFreeCertificateChain
0x1800137d4  mov     [rbp+80h+pChainContext+8], r12
0x1800137d8  lea     rax, [rbp+80h+pChainContext+8]
0x1800137dc  mov     [rsp+180h+ppChainContext], rax; ppChainContext
0x1800137e1  mov     [rsp+180h+pvReserved], r12; pvReserved
0x1800137e6  mov     [rsp+180h+dwFlags], esi; dwFlags
0x1800137ea  lea     rax, [rbp+80h+var_C0]
0x1800137ee  mov     [rsp+180h+pChainPara], rax; pChainPara
0x1800137f3  xor     r9d, r9d; hAdditionalStore
0x1800137f6  mov     r8, r15; pTime
0x1800137f9  mov     rdx, r14; pCertContext
0x1800137fc  mov     rcx, [rbp+80h+hChainEngine+8]; hChainEngine
0x180013800  call    cs:__imp_CertGetCertificateChain
0x180013806  test    eax, eax
0x180013808  jnz     short loc_180013888
0x18001380a  call    cs:__imp_GetLastError
0x180013810  movzx   ecx, ax
0x180013813  mov     edi, 80070000h
0x180013818  or      ecx, edi
0x18001381a  test    eax, eax
0x18001381c  cmovle  ecx, eax
0x18001381f  test    ecx, ecx
0x180013821  jns     short loc_180013835
0x180013823  call    cs:__imp_GetLastError
0x180013829  movzx   ebx, ax
0x18001382c  or      ebx, edi
0x18001382e  test    eax, eax
0x180013830  cmovle  ebx, eax
0x180013833  jmp     short loc_18001383A
0x180013835  mov     ebx, 80004005h
0x18001383a  mov     rcx, [rbp+80h+pChainContext+8]; pChainContext
0x18001383e  test    rcx, rcx
0x180013841  jz      short loc_180013849
0x180013843  call    cs:__imp_CertFreeCertificateChain
0x180013849  test    ebx, ebx
0x18001384b  jns     short loc_1800138BE
0x18001384d  lea     rax, aYes_0; "Yes"
0x180013854  mov     [rsp+180h+ppChainContext], rax
0x180013859  lea     rax, aNo_0; "No"
0x180013860  mov     [rsp+180h+pvReserved], rax
0x180013865  lea     rax, aCertgetcertifi_2; "CertGetCertificateChain failed. SSL : %"...
0x18001386c  mov     qword ptr [rsp+180h+dwFlags], rax
0x180013871  mov     dword ptr [rsp+180h+pChainPara], ebx
0x180013875  xor     edx, edx
0x180013877  xor     ecx, ecx
0x180013879  lea     r9d, [rdx+1]
0x18001387d  lea     r8d, [rdx+20h]
0x180013881  call    ?WUTrace@@YAXPEBDKW4WUTraceLoggingCategory@@IJPEB_WZZ; WUTrace(char const *,ulong,WUTraceLoggingCategory,uint,long,wchar_t const *,...)
0x180013886  jmp     short loc_1800138BE
0x180013888  mov     rcx, [rbp+80h+pChainContext+8]
0x18001388c  mov     rax, rcx
0x18001388f  test    dword ptr [rcx+8], 2000h
0x180013896  jz      short loc_1800138B2
0x180013898  mov     rcx, [rdi]; pChainContext
0x18001389b  call    cs:__imp_CertFreeCertificateChain
0x1800138a1  mov     rax, [rbp+80h+pChainContext+8]
0x1800138a5  mov     rcx, r12; pChainContext
0x1800138a8  mov     [rbp+80h+pChainContext+8], rcx
0x1800138ac  mov     [rdi], rax
0x1800138af  mov     rax, r12
0x1800138b2  test    rax, rax
0x1800138b5  jz      short loc_1800138BE
0x1800138b7  call    cs:__imp_CertFreeCertificateChain
0x1800138bd  nop
0x1800138be  mov     rcx, [rbp+80h+hCertStore+8]; hCertStore
0x1800138c2  test    rcx, rcx
0x1800138c5  jz      short loc_1800138D3
0x1800138c7  xor     edx, edx; dwFlags
0x1800138c9  call    cs:__imp_CertCloseStore
0x1800138cf  mov     [rbp+80h+hCertStore+8], r12
0x1800138d3  mov     rcx, [rbp+80h+hChainEngine+8]; hChainEngine
0x1800138d7  test    rcx, rcx
0x1800138da  jz      short loc_1800138E2
0x1800138dc  call    cs:__imp_CertFreeCertificateChainEngine
0x1800138e2  mov     eax, ebx
0x1800138e4  mov     rcx, [rbp+80h+var_30]
0x1800138e8  xor     rcx, rsp; StackCookie
0x1800138eb  call    __security_check_cookie
0x1800138f0  lea     r11, [rsp+180h+var_20]
0x1800138f8  mov     rbx, [r11+38h]
0x1800138fc  mov     rsi, [r11+40h]
0x180013900  mov     rsp, r11
0x180013903  pop     r15
0x180013905  pop     r14
0x180013907  pop     r12
0x180013909  pop     rdi
0x18001390a  pop     rbp
0x18001390b  retn
```
