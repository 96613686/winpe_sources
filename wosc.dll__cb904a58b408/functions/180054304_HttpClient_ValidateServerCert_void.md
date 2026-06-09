# HttpClient::ValidateServerCert(void *)

- ea: `0x180054304`
- end: `0x180054454`
- name: `?ValidateServerCert@HttpClient@@CAJPEAX@Z`
- size: `336`
- prototype: `__int64 __fastcall(void *)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180054270`

## callees

- `0x18000e5ac`
- `0x18001e06c`
- `0x180052fdc`
- `0x180052ffc`
- `0x180054304`

## import_xrefs

- `CRYPT32!CertVerifyCertificateChainPolicy` at `0x1800543fc`
- `CRYPT32!CertVerifyCertificateChainPolicy` at `0x1800543fc`
- `CRYPT32!CertGetCertificateChain` at `0x180054399`
- `CRYPT32!CertGetCertificateChain` at `0x180054399`
- `WINHTTP!WinHttpQueryOption` at `0x18005432e`
- `WINHTTP!WinHttpQueryOption` at `0x18005432e`

## string_xrefs

- `0x18005433c`: `onecore\base\flighting\common\httpclient\httpclient.cpp`
- `0x1800543ac`: `onecore\base\flighting\common\httpclient\httpclient.cpp`
- `0x180054416`: `onecore\base\flighting\common\httpclient\httpclient.cpp`

## pseudocode

```c
__int64 __fastcall HttpClient::ValidateServerCert(void *a1)
{
  unsigned int LastError; // ebx
  const char *v2; // r9
  const char *v3; // r9
  __int64 v4; // rdx
  int pChainPara; // [rsp+20h] [rbp-19h]
  _CERT_CHAIN_POLICY_PARA pPolicyPara; // [rsp+40h] [rbp+7h] BYREF
  _CERT_CHAIN_POLICY_STATUS pPolicyStatus; // [rsp+50h] [rbp+17h] BYREF
  struct _CERT_CHAIN_PARA v9; // [rsp+68h] [rbp+2Fh] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+5Fh]
  DWORD dwBufferLength; // [rsp+A8h] [rbp+6Fh] BYREF
  PCCERT_CHAIN_CONTEXT pChainContext; // [rsp+B0h] [rbp+77h] BYREF
  PCCERT_CONTEXT Buffer; // [rsp+B8h] [rbp+7Fh] BYREF

  LastError = 0;
  dwBufferLength = 8;
  Buffer = 0;
  if ( WinHttpQueryOption(a1, 0x4Eu, &Buffer, &dwBufferLength) )
  {
    memset(&v9, 0, sizeof(v9));
    v9.cbSize = 32;
    v9.RequestedUsage.dwType = 1;
    pChainContext = 0;
    if ( !CertGetCertificateChain(0, Buffer, 0, Buffer->hCertStore, &v9, 0, 0, &pChainContext) )
    {
      v4 = 375;
LABEL_5:
      LastError = wil::details::in1diag3::Return_GetLastError(
                    retaddr,
                    (void *)v4,
                    (unsigned int)"onecore\\base\\flighting\\common\\httpclient\\httpclient.cpp",
                    v3);
LABEL_12:
      wil::details::unique_storage<wil::details::resource_policy<_CERT_CHAIN_CONTEXT const *,void (*)(_CERT_CHAIN_CONTEXT const *),&void CertFreeCertificateChain(_CERT_CHAIN_CONTEXT const *),wistd::integral_constant<unsigned __int64,0>,_CERT_CHAIN_CONTEXT const *,_CERT_CHAIN_CONTEXT const *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_CERT_CHAIN_CONTEXT const *,void (*)(_CERT_CHAIN_CONTEXT const *),&void CertFreeCertificateChain(_CERT_CHAIN_CONTEXT const *),wistd::integral_constant<unsigned __int64,0>,_CERT_CHAIN_CONTEXT const *,_CERT_CHAIN_CONTEXT const *,0,std::nullptr_t>>(&pChainContext);
      goto LABEL_13;
    }
    if ( !pChainContext->TrustStatus.dwErrorStatus && (pChainContext->TrustStatus.dwInfoStatus & 8) == 0 )
    {
      pPolicyPara.pvExtraPolicyPara = 0;
      memset(&pPolicyStatus, 0, sizeof(pPolicyStatus));
      pPolicyPara.cbSize = 16;
      pPolicyStatus.cbSize = 24;
      pPolicyPara.dwFlags = 0x20000;
      if ( !CertVerifyCertificateChainPolicy((LPCSTR)7, pChainContext, &pPolicyPara, &pPolicyStatus) )
      {
        v4 = 386;
        goto LABEL_5;
      }
      if ( !pPolicyStatus.dwError )
        goto LABEL_12;
    }
    LastError = -2147012721;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x187,
      (unsigned int)"onecore\\base\\flighting\\common\\httpclient\\httpclient.cpp",
      (const char *)0x80072F8FLL,
      pChainPara);
    goto LABEL_12;
  }
  LastError = wil::details::in1diag3::Return_GetLastError(
                retaddr,
                (void *)0x16E,
                (unsigned int)"onecore\\base\\flighting\\common\\httpclient\\httpclient.cpp",
                v2);
LABEL_13:
  wil::details::unique_storage<wil::details::resource_policy<_CERT_CONTEXT const *,int (*)(_CERT_CONTEXT const *),&int CertFreeCertificateContext(_CERT_CONTEXT const *),wistd::integral_constant<unsigned __int64,0>,_CERT_CONTEXT const *,_CERT_CONTEXT const *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_CERT_CONTEXT const *,int (*)(_CERT_CONTEXT const *),&int CertFreeCertificateContext(_CERT_CONTEXT const *),wistd::integral_constant<unsigned __int64,0>,_CERT_CONTEXT const *,_CERT_CONTEXT const *,0,std::nullptr_t>>(&Buffer);
  return LastError;
}

```

## disassembly

```asm
0x180054304  mov     [rsp-8+arg_0], rbx
0x180054309  push    rbp
0x18005430a  lea     rbp, [rsp-57h]
0x18005430f  sub     rsp, 90h
0x180054316  xor     ebx, ebx
0x180054318  mov     [rbp+57h+dwBufferLength], 8
0x18005431f  lea     r9, [rbp+57h+dwBufferLength]; lpdwBufferLength
0x180054323  mov     [rbp+57h+Buffer], rbx
0x180054327  lea     r8, [rbp+57h+Buffer]; lpBuffer
0x18005432b  lea     edx, [rbx+4Eh]; dwOption
0x18005432e  call    cs:__imp_WinHttpQueryOption
0x180054334  test    eax, eax
0x180054336  jnz     short loc_180054354
0x180054338  mov     rcx, [rbp+5Fh]; this
0x18005433c  lea     r8, aOnecoreBaseFli_31; "onecore\\base\\flighting\\common\\httpc"...
0x180054343  mov     edx, 16Eh; void *
0x180054348  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18005434d  mov     ebx, eax
0x18005434f  jmp     loc_180054438
0x180054354  mov     rdx, [rbp+57h+Buffer]; pCertContext
0x180054358  lea     rax, [rbp+57h+pChainContext]
0x18005435c  mov     [rsp+90h+ppChainContext], rax; ppChainContext
0x180054361  xorps   xmm0, xmm0
0x180054364  movups  xmmword ptr [rbp+57h+var_28.cbSize], xmm0
0x180054368  mov     [rbp+57h+var_28.cbSize], 20h ; ' '
0x18005436f  lea     rax, [rbp+57h+var_28]
0x180054373  movups  xmmword ptr [rbp+57h+var_28.RequestedUsage.Usage.cUsageIdentifier], xmm0
0x180054377  mov     [rbp+57h+var_28.RequestedUsage.dwType], 1
0x18005437e  xor     r8d, r8d; pTime
0x180054381  mov     [rbp+57h+pChainContext], rbx
0x180054385  xor     ecx, ecx; hChainEngine
0x180054387  mov     r9, [rdx+20h]; hAdditionalStore
0x18005438b  mov     [rsp+90h+pvReserved], rbx; pvReserved
0x180054390  mov     [rsp+90h+dwFlags], ebx; dwFlags
0x180054394  mov     [rsp+90h+pChainPara], rax; int
0x180054399  call    cs:__imp_CertGetCertificateChain
0x18005439f  test    eax, eax
0x1800543a1  jnz     short loc_1800543BC
0x1800543a3  mov     edx, 177h; void *
0x1800543a8  mov     rcx, [rbp+5Fh]; this
0x1800543ac  lea     r8, aOnecoreBaseFli_31; "onecore\\base\\flighting\\common\\httpc"...
0x1800543b3  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800543b8  mov     ebx, eax
0x1800543ba  jmp     short loc_18005442F
0x1800543bc  mov     rdx, [rbp+57h+pChainContext]; pChainContext
0x1800543c0  cmp     [rdx+4], ebx
0x1800543c3  jnz     short loc_180054412
0x1800543c5  test    byte ptr [rdx+8], 8
0x1800543c9  jnz     short loc_180054412
0x1800543cb  xor     eax, eax
0x1800543cd  mov     [rbp+57h+pPolicyPara.pvExtraPolicyPara], rbx
0x1800543d1  xorps   xmm0, xmm0
0x1800543d4  mov     [rbp+57h+pPolicyStatus.pvExtraPolicyStatus], rax
0x1800543d8  movups  xmmword ptr [rbp+57h+pPolicyStatus.cbSize], xmm0
0x1800543dc  lea     r9, [rbp+57h+pPolicyStatus]; pPolicyStatus
0x1800543e0  mov     [rbp+57h+pPolicyPara.cbSize], 10h
0x1800543e7  lea     ecx, [rax+7]; pszPolicyOID
0x1800543ea  mov     [rbp+57h+pPolicyStatus.cbSize], 18h
0x1800543f1  lea     r8, [rbp+57h+pPolicyPara]; pPolicyPara
0x1800543f5  mov     [rbp+57h+pPolicyPara.dwFlags], 20000h
0x1800543fc  call    cs:__imp_CertVerifyCertificateChainPolicy
0x180054402  test    eax, eax
0x180054404  jnz     short loc_18005440D
0x180054406  mov     edx, 182h
0x18005440b  jmp     short loc_1800543A8
0x18005440d  cmp     [rbp+57h+pPolicyStatus.dwError], ebx
0x180054410  jz      short loc_18005442F
0x180054412  mov     rcx, [rbp+5Fh]; this
0x180054416  lea     r8, aOnecoreBaseFli_31; "onecore\\base\\flighting\\common\\httpc"...
0x18005441d  mov     ebx, 80072F8Fh
0x180054422  mov     edx, 187h; void *
0x180054427  mov     r9d, ebx; char *
0x18005442a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005442f  lea     rcx, [rbp+57h+pChainContext]
0x180054433  call    ??1?$unique_storage@U?$resource_policy@PEBU_CERT_CHAIN_CONTEXT@@P6AXPEBU1@@Z$1?CertFreeCertificateChain@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEBU1@PEBU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_CERT_CHAIN_CONTEXT const *,void (*)(_CERT_CHAIN_CONTEXT const *),&CertFreeCertificateChain(_CERT_CHAIN_CONTEXT const *),wistd::integral_constant<unsigned __int64,0>,_CERT_CHAIN_CONTEXT const *,_CERT_CHAIN_CONTEXT const *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_CERT_CHAIN_CONTEXT const *,void (*)(_CERT_CHAIN_CONTEXT const *),&CertFreeCertificateChain(_CERT_CHAIN_CONTEXT const *),wistd::integral_constant<unsigned __int64,0>,_CERT_CHAIN_CONTEXT const *,_CERT_CHAIN_CONTEXT const *,0,std::nullptr_t>>(void)
0x180054438  lea     rcx, [rbp+57h+Buffer]
0x18005443c  call    ??1?$unique_storage@U?$resource_policy@PEBU_CERT_CONTEXT@@P6AHPEBU1@@Z$1?CertFreeCertificateContext@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEBU1@PEBU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_CERT_CONTEXT const *,int (*)(_CERT_CONTEXT const *),&CertFreeCertificateContext(_CERT_CONTEXT const *),wistd::integral_constant<unsigned __int64,0>,_CERT_CONTEXT const *,_CERT_CONTEXT const *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_CERT_CONTEXT const *,int (*)(_CERT_CONTEXT const *),&CertFreeCertificateContext(_CERT_CONTEXT const *),wistd::integral_constant<unsigned __int64,0>,_CERT_CONTEXT const *,_CERT_CONTEXT const *,0,std::nullptr_t>>(void)
0x180054441  mov     eax, ebx
0x180054443  mov     rbx, [rsp+90h+arg_0]
0x18005444b  add     rsp, 90h
0x180054452  pop     rbp
0x180054453  retn
```
