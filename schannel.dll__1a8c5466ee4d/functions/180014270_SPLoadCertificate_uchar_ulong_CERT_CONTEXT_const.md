# SPLoadCertificate(uchar *,ulong,_CERT_CONTEXT const * *)

- ea: `0x180014270`
- end: `0x1800144b4`
- name: `?SPLoadCertificate@@YAKPEAEKPEAPEBU_CERT_CONTEXT@@@Z`
- size: `580`
- prototype: `unsigned int __fastcall(unsigned __int8 *, unsigned int, const struct _CERT_CONTEXT **)`
- caller_count: `8`
- callee_count: `2`
- tags: ``

## callers

- `0x180013740`
- `0x180013a00`
- `0x180026d30`
- `0x180046c18`
- `0x18004a610`
- `0x18006f530`
- `0x18006f634`
- `0x18006f984`

## callees

- `0x180014270`
- `0x180021da8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180014374`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800143d9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180014424`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001446e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180014374`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800143d9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180014424`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001446e`
- `CRYPT32!CertOpenStore` at `0x1800142c0`
- `CRYPT32!CertOpenStore` at `0x1800142c0`
- `CRYPT32!CertCloseStore` at `0x1800143e6`
- `CRYPT32!CertCloseStore` at `0x18001441c`
- `CRYPT32!CertCloseStore` at `0x180014443`
- `CRYPT32!CertCloseStore` at `0x1800143e6`
- `CRYPT32!CertCloseStore` at `0x18001441c`
- `CRYPT32!CertCloseStore` at `0x180014443`
- `CRYPT32!CertFreeCertificateContext` at `0x1800143b4`
- `CRYPT32!CertFreeCertificateContext` at `0x180014457`
- `CRYPT32!CertFreeCertificateContext` at `0x180014463`
- `CRYPT32!CertFreeCertificateContext` at `0x18008ae92`
- `CRYPT32!CertFreeCertificateContext` at `0x1800143b4`
- `CRYPT32!CertFreeCertificateContext` at `0x180014457`
- `CRYPT32!CertFreeCertificateContext` at `0x180014463`
- `CRYPT32!CertFreeCertificateContext` at `0x18008ae92`
- `CRYPT32!CertGetCertificateContextProperty` at `0x18001436a`
- `CRYPT32!CertGetCertificateContextProperty` at `0x18001436a`
- `CRYPT32!CertAddEncodedCertificateToStore` at `0x18001433f`
- `CRYPT32!CertAddEncodedCertificateToStore` at `0x18001433f`
- `CRYPT32!CertSetCertificateContextProperty` at `0x180014397`
- `CRYPT32!CertSetCertificateContextProperty` at `0x180014397`

## pseudocode

```c
DWORD __fastcall SPLoadCertificate(unsigned __int8 *a1, unsigned int a2, const struct _CERT_CONTEXT **a3)
{
  HCERTSTORE v6; // rbp
  int v7; // r12d
  __int64 v8; // rdi
  unsigned int v9; // ebx
  DWORD LastError; // ebx
  PCCERT_CONTEXT pCertContext; // [rsp+30h] [rbp-58h] BYREF
  _QWORD pvData[3]; // [rsp+38h] [rbp-50h] BYREF
  int v14; // [rsp+A0h] [rbp+18h] BYREF
  DWORD pcbData; // [rsp+A8h] [rbp+20h] BYREF

  pCertContext = 0;
  if ( !a3 )
    return -2146893052;
  if ( *a3 )
    CertFreeCertificateContext(*a3);
  *a3 = 0;
  v6 = CertOpenStore((LPCSTR)2, 0, 0, 4u, 0);
  if ( !v6 )
    return GetLastError();
  v7 = 1;
  pvData[1] = &v14;
  v14 = 0;
  pvData[0] = 4;
  while ( 1 )
  {
    if ( a2 < 4 || (v8 = *(unsigned int *)a1, v9 = a2 - 4, (unsigned int)v8 > v9) )
    {
      LastError = -2146893052;
      CertCloseStore(v6, 0);
      goto LABEL_25;
    }
    if ( !CertAddEncodedCertificateToStore(v6, 1u, a1 + 4, v8, 2u, &pCertContext) )
    {
LABEL_18:
      LastError = GetLastError();
      goto LABEL_19;
    }
    pcbData = 0;
    if ( !CertGetCertificateContextProperty(pCertContext, 0xE697u, 0, &pcbData) )
      break;
LABEL_13:
    a2 = v9 - v8;
    if ( v7 )
    {
      v7 = 0;
      *a3 = pCertContext;
    }
    else
    {
      CertFreeCertificateContext(pCertContext);
    }
    pCertContext = 0;
    if ( !a2 )
    {
      LastError = 0;
      CertCloseStore(v6, 0);
      return LastError;
    }
    a1 += v8 + 4;
  }
  if ( GetLastError() == -2146885628 )
  {
    if ( !CertSetCertificateContextProperty(pCertContext, 0xE697u, 0, pvData) )
      goto LABEL_18;
    ++v14;
    goto LABEL_13;
  }
  LastError = GetLastError();
  if ( WPP_GLOBAL_Control != (CCipherMill *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, WPP_97ce1caa02e33ff6a1f9fe6c11ed93b7_Traceguids, LastError);
LABEL_19:
  CertCloseStore(v6, 0);
  if ( !LastError )
    return LastError;
LABEL_25:
  if ( pCertContext )
    CertFreeCertificateContext(pCertContext);
  if ( *a3 )
  {
    CertFreeCertificateContext(*a3);
    *a3 = 0;
  }
  return LastError;
}

```

## disassembly

```asm
0x180014270  push    rbx
0x180014272  push    rsi
0x180014273  push    r13
0x180014275  push    r14
0x180014277  sub     rsp, 68h
0x18001427b  xor     r13d, r13d
0x18001427e  mov     r14, r8
0x180014281  mov     [rsp+88h+pCertContext], r13
0x180014286  mov     ebx, edx
0x180014288  mov     rsi, rcx
0x18001428b  test    r8, r8
0x18001428e  jz      loc_18001442C
0x180014294  mov     rcx, [r8]; pCertContext
0x180014297  mov     [rsp+88h+arg_0], rbp
0x18001429f  test    rcx, rcx
0x1800142a2  jnz     loc_180014463
0x1800142a8  mov     r9d, 4; dwFlags
0x1800142ae  mov     [r14], r13
0x1800142b1  xor     r8d, r8d; hCryptProv
0x1800142b4  mov     [rsp+88h+pvPara], r13; pvPara
0x1800142b9  xor     edx, edx; dwEncodingType
0x1800142bb  mov     ecx, 2; lpszStoreProvider
0x1800142c0  call    cs:__imp_CertOpenStore
0x1800142c6  mov     rbp, rax
0x1800142c9  test    rax, rax
0x1800142cc  jz      loc_180014424
0x1800142d2  mov     [rsp+88h+var_30], r12
0x1800142d7  lea     rax, [rsp+88h+arg_10]
0x1800142df  mov     [rsp+88h+var_28], rdi
0x1800142e4  mov     r12d, 1
0x1800142ea  mov     [rsp+88h+var_48], rax
0x1800142ef  mov     [rsp+88h+var_38], r15
0x1800142f4  mov     [rsp+88h+arg_10], r13d
0x1800142fc  mov     [rsp+88h+pvData], 4
0x180014305  mov     rcx, rbp; hCertStore
0x180014308  cmp     ebx, 4
0x18001430b  jb      loc_18001443C
0x180014311  mov     edi, [rsi]
0x180014313  add     ebx, 0FFFFFFFCh
0x180014316  cmp     edi, ebx
0x180014318  ja      loc_18001443C
0x18001431e  lea     rax, [rsp+88h+pCertContext]
0x180014323  mov     r9d, edi; cbCertEncoded
0x180014326  mov     [rsp+88h+ppCertContext], rax; ppCertContext
0x18001432b  lea     r15, [rsi+4]
0x18001432f  mov     r8, r15; pbCertEncoded
0x180014332  mov     dword ptr [rsp+88h+pvPara], 2; dwAddDisposition
0x18001433a  mov     edx, 1; dwCertEncodingType
0x18001433f  call    cs:__imp_CertAddEncodedCertificateToStore
0x180014345  test    eax, eax
0x180014347  jz      loc_1800143D9
0x18001434d  mov     rcx, [rsp+88h+pCertContext]; pCertContext
0x180014352  lea     r9, [rsp+88h+pcbData]; pcbData
0x18001435a  xor     r8d, r8d; pvData
0x18001435d  mov     [rsp+88h+pcbData], r13d
0x180014365  mov     edx, 0E697h; dwPropId
0x18001436a  call    cs:__imp_CertGetCertificateContextProperty
0x180014370  test    eax, eax
0x180014372  jnz     short loc_1800143A8
0x180014374  call    cs:__imp_GetLastError
0x18001437a  cmp     eax, 80092004h
0x18001437f  jnz     loc_18001446E
0x180014385  mov     rcx, [rsp+88h+pCertContext]; pCertContext
0x18001438a  lea     r9, [rsp+88h+pvData]; pvData
0x18001438f  xor     r8d, r8d; dwFlags
0x180014392  mov     edx, 0E697h; dwPropId
0x180014397  call    cs:__imp_CertSetCertificateContextProperty
0x18001439d  test    eax, eax
0x18001439f  jz      short loc_1800143D9
0x1800143a1  inc     [rsp+88h+arg_10]
0x1800143a8  sub     ebx, edi
0x1800143aa  test    r12d, r12d
0x1800143ad  jnz     short loc_1800143CC
0x1800143af  mov     rcx, [rsp+88h+pCertContext]; pCertContext
0x1800143b4  call    cs:__imp_CertFreeCertificateContext
0x1800143ba  mov     [rsp+88h+pCertContext], r13
0x1800143bf  test    ebx, ebx
0x1800143c1  jz      short loc_180014414
0x1800143c3  lea     rsi, [r15+rdi]
0x1800143c7  jmp     loc_180014305
0x1800143cc  mov     rax, [rsp+88h+pCertContext]
0x1800143d1  mov     r12d, r13d
0x1800143d4  mov     [r14], rax
0x1800143d7  jmp     short loc_1800143BA
0x1800143d9  call    cs:__imp_GetLastError
0x1800143df  mov     ebx, eax
0x1800143e1  xor     edx, edx; dwFlags
0x1800143e3  mov     rcx, rbp; hCertStore
0x1800143e6  call    cs:__imp_CertCloseStore
0x1800143ec  test    ebx, ebx
0x1800143ee  jnz     short loc_180014449
0x1800143f0  mov     r15, [rsp+88h+var_38]
0x1800143f5  mov     eax, ebx
0x1800143f7  mov     r12, [rsp+88h+var_30]
0x1800143fc  mov     rdi, [rsp+88h+var_28]
0x180014401  mov     rbp, [rsp+88h+arg_0]
0x180014409  add     rsp, 68h
0x18001440d  pop     r14
0x18001440f  pop     r13
0x180014411  pop     rsi
0x180014412  pop     rbx
0x180014413  retn
0x180014414  xor     edx, edx; dwFlags
0x180014416  mov     rcx, rbp; hCertStore
0x180014419  mov     ebx, r13d
0x18001441c  call    cs:__imp_CertCloseStore
0x180014422  jmp     short loc_1800143F0
0x180014424  call    cs:__imp_GetLastError
0x18001442a  jmp     short loc_180014401
0x18001442c  mov     eax, 80090304h
0x180014431  add     rsp, 68h
0x180014435  pop     r14
0x180014437  pop     r13
0x180014439  pop     rsi
0x18001443a  pop     rbx
0x18001443b  retn
0x18001443c  xor     edx, edx; dwFlags
0x18001443e  mov     ebx, 80090304h
0x180014443  call    cs:__imp_CertCloseStore
0x180014449  mov     rcx, [rsp+88h+pCertContext]; pCertContext
0x18001444e  test    rcx, rcx
0x180014451  jz      loc_18008AE86
0x180014457  call    cs:__imp_CertFreeCertificateContext
0x18001445d  nop
0x18001445e  jmp     loc_18008AE86
0x180014463  call    cs:__imp_CertFreeCertificateContext
0x180014469  jmp     loc_1800142A8
0x18001446e  call    cs:__imp_GetLastError
0x180014474  mov     ebx, eax
0x180014476  mov     rcx, cs:WPP_GLOBAL_Control
0x18001447d  lea     rax, WPP_GLOBAL_Control
0x180014484  cmp     rcx, rax
0x180014487  jz      loc_1800143E1
0x18001448d  test    byte ptr [rcx+1Ch], 1
0x180014491  jz      loc_1800143E1
0x180014497  mov     rcx, [rcx+10h]
0x18001449b  lea     r8, WPP_97ce1caa02e33ff6a1f9fe6c11ed93b7_Traceguids
0x1800144a2  mov     edx, 0Ah
0x1800144a7  mov     r9d, ebx
0x1800144aa  call    WPP_SF_d
0x1800144af  jmp     loc_1800143E1
0x18008ae86  mov     rcx, [r14]; pCertContext
0x18008ae89  test    rcx, rcx
0x18008ae8c  jz      loc_1800143F0
0x18008ae92  call    cs:__imp_CertFreeCertificateContext
0x18008ae98  mov     [r14], r13
0x18008ae9b  jmp     loc_1800143F0
```
