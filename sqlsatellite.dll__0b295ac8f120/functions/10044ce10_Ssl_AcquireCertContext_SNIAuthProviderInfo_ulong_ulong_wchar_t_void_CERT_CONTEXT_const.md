# Ssl::AcquireCertContext(SNIAuthProviderInfo *,ulong *,ulong,wchar_t *,void * *,_CERT_CONTEXT const * *)

- ea: `0x10044ce10`
- end: `0x10044cfe1`
- name: `?AcquireCertContext@Ssl@@CAKPEAVSNIAuthProviderInfo@@PEAKKPEA_WPEAPEAXPEAPEBU_CERT_CONTEXT@@@Z`
- size: `465`
- prototype: `unsigned int __fastcall(struct SNIAuthProviderInfo *, unsigned int *, unsigned int, wchar_t *, void **, const struct _CERT_CONTEXT **)`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x10044b2b0`
- `0x10044b5e0`

## callees

- `0x10044ce10`
- `0x10044cff0`
- `0x100486af0`

## import_xrefs

- `KERNEL32!GetLastError` at `0x10044ce90`
- `KERNEL32!GetLastError` at `0x10044cf22`
- `KERNEL32!GetLastError` at `0x10044cf83`
- `KERNEL32!GetLastError` at `0x10044ce90`
- `KERNEL32!GetLastError` at `0x10044cf22`
- `KERNEL32!GetLastError` at `0x10044cf83`
- `CRYPT32!CertOpenSystemStoreA` at `0x10044cf3d`
- `CRYPT32!CertOpenSystemStoreA` at `0x10044cf3d`
- `CRYPT32!CryptStringToBinaryW` at `0x10044ce86`
- `CRYPT32!CryptStringToBinaryW` at `0x10044ce86`
- `CRYPT32!CertOpenStore` at `0x10044ceda`
- `CRYPT32!CertOpenStore` at `0x10044ceda`
- `CRYPT32!CertCloseStore` at `0x10044cf15`
- `CRYPT32!CertCloseStore` at `0x10044cf74`
- `CRYPT32!CertCloseStore` at `0x10044cf15`
- `CRYPT32!CertCloseStore` at `0x10044cf74`

## pseudocode

```c
DWORD __fastcall Ssl::AcquireCertContext(
        struct SNIAuthProviderInfo *a1,
        unsigned int *a2,
        int a3,
        wchar_t *a4,
        void **a5,
        struct _CERT_CONTEXT **a6)
{
  WCHAR *p_pvFindPara; // r14
  DWORD v11; // ebp
  HCERTSTORE v12; // rax
  int Certificate; // ebx
  HCERTSTORE v14; // rax
  __int64 (__fastcall *v15)(_QWORD, _QWORD, _QWORD, struct _CERT_CONTEXT **, unsigned int *, int, wchar_t *); // rax
  DWORD pcbBinary; // [rsp+40h] [rbp-88h] BYREF
  wchar_t *v17; // [rsp+48h] [rbp-80h]
  int pvFindPara; // [rsp+50h] [rbp-78h] BYREF
  BYTE *v19; // [rsp+58h] [rbp-70h]
  BYTE pbBinary[24]; // [rsp+60h] [rbp-68h] BYREF

  p_pvFindPara = (WCHAR *)*((_QWORD *)a1 + 7);
  v17 = a4;
  if ( *((_DWORD *)a1 + 16) )
  {
    pcbBinary = 20;
    if ( !CryptStringToBinaryW(p_pvFindPara, 0, 4u, pbBinary, &pcbBinary, 0, 0) )
      return GetLastError();
    pvFindPara = 20;
    v19 = pbBinary;
    p_pvFindPara = (WCHAR *)&pvFindPara;
    v11 = 0x10000;
  }
  else
  {
    v11 = 524295;
  }
  v12 = CertOpenStore((LPCSTR)0xA, 1u, 0, 0x28000u, L"MY");
  *a5 = v12;
  if ( v12 )
  {
    Certificate = Ssl::FindAndLoadCertificate(v12, v11, p_pvFindPara, (const struct _CERT_CONTEXT **)a6, 0, 0, 0);
    if ( !Certificate )
      return Certificate;
    CertCloseStore(*a5, 0);
    *a5 = 0;
  }
  else
  {
    Certificate = GetLastError();
    if ( !Certificate )
      return Certificate;
  }
  v14 = CertOpenSystemStoreA(0, "MY");
  *a5 = v14;
  if ( v14 )
  {
    Certificate = Ssl::FindAndLoadCertificate(v14, v11, p_pvFindPara, (const struct _CERT_CONTEXT **)a6, 0, 0, 0);
    if ( Certificate )
    {
      CertCloseStore(*a5, 0);
      *a5 = 0;
      goto LABEL_14;
    }
  }
  else
  {
    Certificate = GetLastError();
    if ( Certificate )
    {
LABEL_14:
      v15 = (__int64 (__fastcall *)(_QWORD, _QWORD, _QWORD, struct _CERT_CONTEXT **, unsigned int *, int, wchar_t *))*((_QWORD *)a1 + 10);
      if ( v15 )
        return v15(*((_QWORD *)a1 + 9), *((unsigned int *)a1 + 16), *((_QWORD *)a1 + 7), a6, a2, a3, v17);
    }
  }
  return Certificate;
}

```

## disassembly

```asm
0x10044ce10  push    rbx
0x10044ce12  push    rbp
0x10044ce13  push    rsi
0x10044ce14  push    rdi
0x10044ce15  push    r12
0x10044ce17  push    r13
0x10044ce19  push    r14
0x10044ce1b  push    r15
0x10044ce1d  sub     rsp, 88h
0x10044ce24  mov     rax, cs:__security_cookie
0x10044ce2b  xor     rax, rsp
0x10044ce2e  mov     [rsp+0C8h+var_50], rax
0x10044ce33  mov     rdi, [rsp+0C8h+arg_20]
0x10044ce3b  xor     ebx, ebx
0x10044ce3d  mov     r13d, r8d
0x10044ce40  mov     r15, [rsp+0C8h+arg_28]
0x10044ce48  mov     r12, rdx
0x10044ce4b  mov     r14, [rcx+38h]
0x10044ce4f  mov     rsi, rcx
0x10044ce52  mov     [rsp+0C8h+var_80], r9
0x10044ce57  cmp     [rcx+40h], ebx
0x10044ce5a  jz      short loc_10044CEB9
0x10044ce5c  mov     [rsp+0C8h+pdwFlags], rbx; pdwFlags
0x10044ce61  lea     rax, [rsp+0C8h+var_88]
0x10044ce66  mov     [rsp+0C8h+pdwSkip], rbx; pdwSkip
0x10044ce6b  lea     r9, [rsp+0C8h+pbBinary]; pbBinary
0x10044ce70  xor     edx, edx; cchString
0x10044ce72  mov     [rsp+0C8h+pcbBinary], rax; pcbBinary
0x10044ce77  lea     r8d, [rbx+4]; dwFlags
0x10044ce7b  mov     [rsp+0C8h+var_88], 14h
0x10044ce83  mov     rcx, r14; pszString
0x10044ce86  call    cs:__imp_CryptStringToBinaryW
0x10044ce8c  test    eax, eax
0x10044ce8e  jnz     short loc_10044CE9B
0x10044ce90  call    cs:__imp_GetLastError
0x10044ce96  jmp     loc_10044CFC0
0x10044ce9b  lea     rax, [rsp+0C8h+pbBinary]
0x10044cea0  mov     [rsp+0C8h+pvFindPara], 14h
0x10044cea8  mov     [rsp+0C8h+var_70], rax
0x10044cead  lea     r14, [rsp+0C8h+pvFindPara]
0x10044ceb2  mov     ebp, 10000h
0x10044ceb7  jmp     short loc_10044CEBE
0x10044ceb9  mov     ebp, 80007h
0x10044cebe  xor     r8d, r8d; hCryptProv
0x10044cec1  lea     rax, aMy_0; "MY"
0x10044cec8  mov     r9d, 28000h; dwFlags
0x10044cece  mov     [rsp+0C8h+pcbBinary], rax; pvPara
0x10044ced3  lea     edx, [r8+1]; dwEncodingType
0x10044ced7  lea     ecx, [rdx+9]; lpszStoreProvider
0x10044ceda  call    cs:__imp_CertOpenStore
0x10044cee0  mov     [rdi], rax
0x10044cee3  test    rax, rax
0x10044cee6  jz      short loc_10044CF22
0x10044cee8  mov     [rsp+0C8h+pdwFlags], rbx; struct _SecHandle **
0x10044ceed  mov     r9, r15; struct _CERT_CONTEXT **
0x10044cef0  mov     [rsp+0C8h+pdwSkip], rbx; struct _SecHandle **
0x10044cef5  mov     r8, r14; pvFindPara
0x10044cef8  mov     edx, ebp; dwFindType
0x10044cefa  mov     dword ptr [rsp+0C8h+pcbBinary], ebx; int
0x10044cefe  mov     rcx, rax; hCertStore
0x10044cf01  call    ?FindAndLoadCertificate@Ssl@@CAKPEAXK0PEAPEBU_CERT_CONTEXT@@HPEAPEAU_SecHandle@@2@Z; Ssl::FindAndLoadCertificate(void *,ulong,void *,_CERT_CONTEXT const * *,int,_SecHandle * *,_SecHandle * *)
0x10044cf06  mov     ebx, eax
0x10044cf08  test    eax, eax
0x10044cf0a  jz      loc_10044CFBE
0x10044cf10  mov     rcx, [rdi]; hCertStore
0x10044cf13  xor     edx, edx; dwFlags
0x10044cf15  call    cs:__imp_CertCloseStore
0x10044cf1b  xor     ebx, ebx
0x10044cf1d  mov     [rdi], rbx
0x10044cf20  jmp     short loc_10044CF34
0x10044cf22  call    cs:__imp_GetLastError
0x10044cf28  mov     ebx, eax
0x10044cf2a  test    eax, eax
0x10044cf2c  jz      loc_10044CFBE
0x10044cf32  xor     ebx, ebx
0x10044cf34  lea     rdx, szSubsystemProtocol; "MY"
0x10044cf3b  xor     ecx, ecx; hProv
0x10044cf3d  call    cs:__imp_CertOpenSystemStoreA
0x10044cf43  mov     [rdi], rax
0x10044cf46  test    rax, rax
0x10044cf49  jz      short loc_10044CF83
0x10044cf4b  mov     [rsp+0C8h+pdwFlags], rbx; struct _SecHandle **
0x10044cf50  mov     r9, r15; struct _CERT_CONTEXT **
0x10044cf53  mov     [rsp+0C8h+pdwSkip], rbx; struct _SecHandle **
0x10044cf58  mov     r8, r14; pvFindPara
0x10044cf5b  mov     edx, ebp; dwFindType
0x10044cf5d  mov     dword ptr [rsp+0C8h+pcbBinary], ebx; int
0x10044cf61  mov     rcx, rax; hCertStore
0x10044cf64  call    ?FindAndLoadCertificate@Ssl@@CAKPEAXK0PEAPEBU_CERT_CONTEXT@@HPEAPEAU_SecHandle@@2@Z; Ssl::FindAndLoadCertificate(void *,ulong,void *,_CERT_CONTEXT const * *,int,_SecHandle * *,_SecHandle * *)
0x10044cf69  mov     ebx, eax
0x10044cf6b  test    eax, eax
0x10044cf6d  jz      short loc_10044CFBE
0x10044cf6f  mov     rcx, [rdi]; hCertStore
0x10044cf72  xor     edx, edx; dwFlags
0x10044cf74  call    cs:__imp_CertCloseStore
0x10044cf7a  mov     qword ptr [rdi], 0
0x10044cf81  jmp     short loc_10044CF8F
0x10044cf83  call    cs:__imp_GetLastError
0x10044cf89  mov     ebx, eax
0x10044cf8b  test    eax, eax
0x10044cf8d  jz      short loc_10044CFBE
0x10044cf8f  mov     rax, [rsi+50h]
0x10044cf93  test    rax, rax
0x10044cf96  jz      short loc_10044CFBE
0x10044cf98  mov     rcx, [rsp+0C8h+var_80]
0x10044cf9d  mov     r9, r15
0x10044cfa0  mov     r8, [rsi+38h]
0x10044cfa4  mov     edx, [rsi+40h]
0x10044cfa7  mov     [rsp+0C8h+pdwFlags], rcx
0x10044cfac  mov     rcx, [rsi+48h]
0x10044cfb0  mov     dword ptr [rsp+0C8h+pdwSkip], r13d
0x10044cfb5  mov     [rsp+0C8h+pcbBinary], r12
0x10044cfba  call    rax
0x10044cfbc  mov     ebx, eax
0x10044cfbe  mov     eax, ebx
0x10044cfc0  mov     rcx, [rsp+0C8h+var_50]
0x10044cfc5  xor     rcx, rsp; StackCookie
0x10044cfc8  call    __security_check_cookie
0x10044cfcd  add     rsp, 88h
0x10044cfd4  pop     r15
0x10044cfd6  pop     r14
0x10044cfd8  pop     r13
0x10044cfda  pop     r12
0x10044cfdc  pop     rdi
0x10044cfdd  pop     rsi
0x10044cfde  pop     rbp
0x10044cfdf  pop     rbx
0x10044cfe0  retn
```
