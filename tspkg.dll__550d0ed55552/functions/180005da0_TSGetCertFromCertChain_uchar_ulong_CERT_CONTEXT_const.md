# TSGetCertFromCertChain(uchar *,ulong,_CERT_CONTEXT const * *)

- ea: `0x180005da0`
- end: `0x180005ec5`
- name: `?TSGetCertFromCertChain@@YAJPEAEKPEAPEBU_CERT_CONTEXT@@@Z`
- size: `293`
- prototype: `__int64 __fastcall(unsigned __int8 *, unsigned int, const struct _CERT_CONTEXT **)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x1800059a8`

## callees

- `0x180005da0`

## import_xrefs

- `CRYPT32!CertFreeCertificateContext` at `0x180005e55`
- `CRYPT32!CertFreeCertificateContext` at `0x180005e97`
- `CRYPT32!CertFreeCertificateContext` at `0x180005ea5`
- `CRYPT32!CertFreeCertificateContext` at `0x180005e55`
- `CRYPT32!CertFreeCertificateContext` at `0x180005e97`
- `CRYPT32!CertFreeCertificateContext` at `0x180005ea5`
- `CRYPT32!CertOpenStore` at `0x180005dd9`
- `CRYPT32!CertOpenStore` at `0x180005dd9`
- `CRYPT32!CertCloseStore` at `0x180005e80`
- `CRYPT32!CertCloseStore` at `0x180005e80`
- `CRYPT32!CertAddEncodedCertificateToStore` at `0x180005e2c`
- `CRYPT32!CertAddEncodedCertificateToStore` at `0x180005e2c`

## pseudocode

```c
__int64 __fastcall TSGetCertFromCertChain(unsigned __int8 *a1, unsigned int a2, const struct _CERT_CONTEXT **a3)
{
  HCERTSTORE v6; // r15
  int v8; // ebx
  int v9; // r12d
  __int64 v10; // rbp
  unsigned int v11; // edi
  PCCERT_CONTEXT pCertContext; // [rsp+98h] [rbp+20h] BYREF

  pCertContext = 0;
  v6 = CertOpenStore((LPCSTR)2, 0, 0, 4u, 0);
  if ( !v6 )
    return 3221225626LL;
  v8 = 0;
  v9 = 1;
  while ( a2 >= 4 )
  {
    v10 = *(unsigned int *)a1;
    v11 = a2 - 4;
    if ( (unsigned int)v10 > v11 )
      break;
    if ( !CertAddEncodedCertificateToStore(v6, 1u, a1 + 4, v10, 2u, &pCertContext) )
    {
      v8 = -2146893017;
      goto LABEL_14;
    }
    a2 = v11 - v10;
    if ( v9 )
    {
      v9 = 0;
      *a3 = pCertContext;
    }
    else
    {
      CertFreeCertificateContext(pCertContext);
    }
    pCertContext = 0;
    if ( !a2 )
      goto LABEL_14;
    a1 += v10 + 4;
  }
  v8 = -2146893048;
LABEL_14:
  CertCloseStore(v6, 0);
  if ( v8 < 0 )
  {
    if ( pCertContext )
      CertFreeCertificateContext(pCertContext);
    if ( *a3 )
    {
      CertFreeCertificateContext(*a3);
      *a3 = 0;
    }
  }
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x180005da0  mov     rax, rsp
0x180005da3  push    rbx
0x180005da4  push    rbp
0x180005da5  push    rsi
0x180005da6  push    rdi
0x180005da7  push    r12
0x180005da9  push    r13
0x180005dab  push    r14
0x180005dad  push    r15
0x180005daf  sub     rsp, 38h
0x180005db3  mov     edi, edx
0x180005db5  mov     qword ptr [rax+20h], 0
0x180005dbd  xor     edx, edx; dwEncodingType
0x180005dbf  mov     qword ptr [rax-58h], 0
0x180005dc7  mov     r14, r8
0x180005dca  mov     rsi, rcx
0x180005dcd  mov     r9d, 4; dwFlags
0x180005dd3  xor     r8d, r8d; hCryptProv
0x180005dd6  lea     ecx, [rdx+2]; lpszStoreProvider
0x180005dd9  call    cs:__imp_CertOpenStore
0x180005ddf  mov     r15, rax
0x180005de2  test    rax, rax
0x180005de5  jnz     short loc_180005DF1
0x180005de7  mov     eax, 0C000009Ah
0x180005dec  jmp     loc_180005EB4
0x180005df1  xor     ebx, ebx
0x180005df3  lea     r12d, [rbx+1]
0x180005df7  cmp     edi, 4
0x180005dfa  jb      short loc_180005E76
0x180005dfc  mov     ebp, [rsi]
0x180005dfe  add     edi, 0FFFFFFFCh
0x180005e01  cmp     ebp, edi
0x180005e03  ja      short loc_180005E76
0x180005e05  lea     rax, [rsp+78h+pCertContext]
0x180005e0d  mov     r9d, ebp; cbCertEncoded
0x180005e10  mov     [rsp+78h+ppCertContext], rax; ppCertContext
0x180005e15  lea     r13, [rsi+4]
0x180005e19  mov     r8, r13; pbCertEncoded
0x180005e1c  mov     [rsp+78h+dwAddDisposition], 2; dwAddDisposition
0x180005e24  mov     edx, 1; dwCertEncodingType
0x180005e29  mov     rcx, r15; hCertStore
0x180005e2c  call    cs:__imp_CertAddEncodedCertificateToStore
0x180005e32  test    eax, eax
0x180005e34  jz      short loc_180005E6F
0x180005e36  sub     edi, ebp
0x180005e38  test    r12d, r12d
0x180005e3b  jz      short loc_180005E4D
0x180005e3d  mov     rax, [rsp+78h+pCertContext]
0x180005e45  xor     r12d, r12d
0x180005e48  mov     [r14], rax
0x180005e4b  jmp     short loc_180005E5B
0x180005e4d  mov     rcx, [rsp+78h+pCertContext]; pCertContext
0x180005e55  call    cs:__imp_CertFreeCertificateContext
0x180005e5b  mov     [rsp+78h+pCertContext], rbx
0x180005e63  test    edi, edi
0x180005e65  jz      short loc_180005E7B
0x180005e67  mov     rsi, rbp
0x180005e6a  add     rsi, r13
0x180005e6d  jmp     short loc_180005DF7
0x180005e6f  mov     ebx, 80090327h
0x180005e74  jmp     short loc_180005E7B
0x180005e76  mov     ebx, 80090308h
0x180005e7b  xor     edx, edx; dwFlags
0x180005e7d  mov     rcx, r15; hCertStore
0x180005e80  call    cs:__imp_CertCloseStore
0x180005e86  test    ebx, ebx
0x180005e88  jns     short loc_180005EB2
0x180005e8a  mov     rcx, [rsp+78h+pCertContext]; pCertContext
0x180005e92  test    rcx, rcx
0x180005e95  jz      short loc_180005E9D
0x180005e97  call    cs:__imp_CertFreeCertificateContext
0x180005e9d  mov     rcx, [r14]; pCertContext
0x180005ea0  test    rcx, rcx
0x180005ea3  jz      short loc_180005EB2
0x180005ea5  call    cs:__imp_CertFreeCertificateContext
0x180005eab  mov     qword ptr [r14], 0
0x180005eb2  mov     eax, ebx
0x180005eb4  add     rsp, 38h
0x180005eb8  pop     r15
0x180005eba  pop     r14
0x180005ebc  pop     r13
0x180005ebe  pop     r12
0x180005ec0  pop     rdi
0x180005ec1  pop     rsi
0x180005ec2  pop     rbp
0x180005ec3  pop     rbx
0x180005ec4  retn
```
