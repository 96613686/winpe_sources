# GetCertificateFromStoreForSha256Hash

- ea: `0x180004300`
- end: `0x180004498`
- name: `GetCertificateFromStoreForSha256Hash`
- size: `408`
- prototype: `__int64 __fastcall(HCERTSTORE hCertStore)`
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x180003e10`

## callees

- `0x180004300`
- `0x180004f10`
- `0x1800070f0`
- `0x180007408`
- `0x18000a014`
- `0x18000ae36`
- `0x18000ae80`
- `0x18000c010`

## import_xrefs

- `CRYPT32!CertEnumCertificatesInStore` at `0x180004339`
- `CRYPT32!CertEnumCertificatesInStore` at `0x180004481`
- `CRYPT32!CertEnumCertificatesInStore` at `0x180004339`
- `CRYPT32!CertEnumCertificatesInStore` at `0x180004481`
- `CRYPT32!CertDuplicateCertificateContext` at `0x1800043f4`
- `CRYPT32!CertDuplicateCertificateContext` at `0x1800043f4`
- `CRYPT32!CertFreeCertificateContext` at `0x180004405`
- `CRYPT32!CertFreeCertificateContext` at `0x180004405`

## pseudocode

```c
__int64 __fastcall GetCertificateFromStoreForSha256Hash(
        HCERTSTORE hCertStore,
        __int64 a2,
        const void *a3,
        PCCERT_CONTEXT *a4)
{
  const CERT_CONTEXT *v7; // rbx
  __int64 v8; // rdx
  const wchar_t *v9; // r8
  int v11; // [rsp+20h] [rbp-48h] BYREF
  _OWORD Buf2[2]; // [rsp+28h] [rbp-40h] BYREF

  memset(Buf2, 0, sizeof(Buf2));
  v7 = CertEnumCertificatesInStore(hCertStore, 0);
  if ( v7 )
  {
    while ( (unsigned __int8)IsPrivateKeyPresent(v7) )
    {
      v11 = 0;
      IsCertificateEKUServerAuth(v7, &v11);
      if ( (unsigned int)(v11 - 1) > 1 )
      {
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) )
        {
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 0x25u);
        }
        v8 = xmmword_1800146E0;
        if ( !(_QWORD)xmmword_1800146E0 )
          goto LABEL_21;
        v9 = L"Skipping certificate as it is not for All purpose or Server Auth";
        goto LABEL_20;
      }
      GetHashFromCertificate((__int64)v7, 2, 0, (BYTE *)Buf2);
      if ( !memcmp_0(a3, Buf2, 0x20u) )
      {
        *a4 = CertDuplicateCertificateContext(v7);
        CertFreeCertificateContext(v7);
        return 0;
      }
LABEL_21:
      v7 = CertEnumCertificatesInStore(hCertStore, v7);
      if ( !v7 )
        return 0;
    }
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 0x26u);
    }
    v8 = xmmword_1800146E0;
    if ( !(_QWORD)xmmword_1800146E0 )
      goto LABEL_21;
    v9 = L"Skipping certificate as it doesn't have private key";
LABEL_20:
    ((void (__fastcall *)(__int64, __int64, const wchar_t *))gSstpCfgTemplateFunc)(gSstpCfgEtwContext, v8, v9);
    goto LABEL_21;
  }
  return 0;
}

```

## disassembly

```asm
0x180004300  mov     [rsp+arg_8], rbx
0x180004305  mov     [rsp+arg_10], rbp
0x18000430a  push    rsi
0x18000430b  push    rdi
0x18000430c  push    r14
0x18000430e  sub     rsp, 50h
0x180004312  mov     rax, cs:__security_cookie
0x180004319  xor     rax, rsp
0x18000431c  mov     [rsp+68h+var_20], rax
0x180004321  xorps   xmm0, xmm0
0x180004324  xor     edx, edx; pPrevCertContext
0x180004326  movups  [rsp+68h+Buf2], xmm0
0x18000432b  mov     rsi, r9
0x18000432e  mov     rbp, r8
0x180004331  movups  [rsp+68h+var_30], xmm0
0x180004336  mov     rdi, rcx
0x180004339  call    cs:__imp_CertEnumCertificatesInStore
0x18000433f  mov     rbx, rax
0x180004342  test    rax, rax
0x180004345  jz      loc_18000440B
0x18000434b  lea     r14, WPP_GLOBAL_Control
0x180004352  mov     rcx, rbx
0x180004355  call    IsPrivateKeyPresent
0x18000435a  test    al, al
0x18000435c  jz      loc_18000442F
0x180004362  lea     rdx, [rsp+68h+var_48]
0x180004367  mov     [rsp+68h+var_48], 0
0x18000436f  mov     rcx, rbx; pCertContext
0x180004372  call    IsCertificateEKUServerAuth
0x180004377  mov     eax, [rsp+68h+var_48]
0x18000437b  dec     eax
0x18000437d  cmp     eax, 1
0x180004380  jbe     short loc_1800043C4
0x180004382  mov     rcx, cs:WPP_GLOBAL_Control
0x180004389  cmp     rcx, r14
0x18000438c  jz      short loc_1800043A8
0x18000438e  test    byte ptr [rcx+1Ch], 40h
0x180004392  jz      short loc_1800043A8
0x180004394  cmp     byte ptr [rcx+19h], 1
0x180004398  jb      short loc_1800043A8
0x18000439a  mov     rcx, [rcx+10h]
0x18000439e  mov     edx, 25h ; '%'
0x1800043a3  call    WPP_SF_
0x1800043a8  mov     rdx, qword ptr cs:xmmword_1800146E0
0x1800043af  test    rdx, rdx
0x1800043b2  jz      loc_18000447B
0x1800043b8  lea     r8, aSkippingCertif_0; "Skipping certificate as it is not for A"...
0x1800043bf  jmp     loc_180004468
0x1800043c4  lea     r9, [rsp+68h+Buf2]
0x1800043c9  xor     r8d, r8d
0x1800043cc  mov     dl, 2
0x1800043ce  mov     rcx, rbx
0x1800043d1  call    GetHashFromCertificate
0x1800043d6  mov     r8d, 20h ; ' '; Size
0x1800043dc  lea     rdx, [rsp+68h+Buf2]; Buf2
0x1800043e1  mov     rcx, rbp; Buf1
0x1800043e4  call    memcmp_0
0x1800043e9  test    eax, eax
0x1800043eb  jnz     loc_18000447B
0x1800043f1  mov     rcx, rbx; pCertContext
0x1800043f4  call    cs:__imp_CertDuplicateCertificateContext
0x1800043fa  mov     [rsi], rax
0x1800043fd  test    rbx, rbx
0x180004400  jz      short loc_18000440B
0x180004402  mov     rcx, rbx; pCertContext
0x180004405  call    cs:__imp_CertFreeCertificateContext
0x18000440b  xor     eax, eax
0x18000440d  mov     rcx, [rsp+68h+var_20]
0x180004412  xor     rcx, rsp; StackCookie
0x180004415  call    __security_check_cookie
0x18000441a  lea     r11, [rsp+68h+var_18]
0x18000441f  mov     rbx, [r11+28h]
0x180004423  mov     rbp, [r11+30h]
0x180004427  mov     rsp, r11
0x18000442a  pop     r14
0x18000442c  pop     rdi
0x18000442d  pop     rsi
0x18000442e  retn
0x18000442f  mov     rcx, cs:WPP_GLOBAL_Control
0x180004436  cmp     rcx, r14
0x180004439  jz      short loc_180004455
0x18000443b  test    byte ptr [rcx+1Ch], 40h
0x18000443f  jz      short loc_180004455
0x180004441  cmp     byte ptr [rcx+19h], 1
0x180004445  jb      short loc_180004455
0x180004447  mov     rcx, [rcx+10h]
0x18000444b  mov     edx, 26h ; '&'
0x180004450  call    WPP_SF_
0x180004455  mov     rdx, qword ptr cs:xmmword_1800146E0
0x18000445c  test    rdx, rdx
0x18000445f  jz      short loc_18000447B
0x180004461  lea     r8, aSkippingCertif; "Skipping certificate as it doesn't have"...
0x180004468  mov     rcx, cs:gSstpCfgEtwContext
0x18000446f  mov     rax, cs:gSstpCfgTemplateFunc
0x180004476  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000447b  mov     rdx, rbx; pPrevCertContext
0x18000447e  mov     rcx, rdi; hCertStore
0x180004481  call    cs:__imp_CertEnumCertificatesInStore
0x180004487  mov     rbx, rax
0x18000448a  test    rax, rax
0x18000448d  jnz     loc_180004352
0x180004493  jmp     loc_18000440B
```
