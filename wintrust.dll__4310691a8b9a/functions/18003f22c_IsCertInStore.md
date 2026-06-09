# _IsCertInStore

- ea: `0x18003f22c`
- end: `0x18003f2d4`
- name: `_IsCertInStore`
- size: `168`
- prototype: `__int64 __fastcall(void *pvFindPara, int)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x18003f0e8`

## callees

- `0x18003f22c`

## import_xrefs

- `CRYPT32!CertCloseStore` at `0x18003f2bc`
- `CRYPT32!CertCloseStore` at `0x18003f2bc`
- `CRYPT32!CertOpenStore` at `0x18003f270`
- `CRYPT32!CertOpenStore` at `0x18003f270`
- `CRYPT32!CertFreeCertificateContext` at `0x18003f2aa`
- `CRYPT32!CertFreeCertificateContext` at `0x18003f2aa`
- `CRYPT32!CertFindCertificateInStore` at `0x18003f29a`
- `CRYPT32!CertFindCertificateInStore` at `0x18003f29a`

## pseudocode

```c
__int64 __fastcall IsCertInStore(void *pvFindPara, int a2)
{
  unsigned int v3; // ebx
  int v4; // edx
  const unsigned __int16 *pvPara; // rax
  HCERTSTORE v6; // rax
  void *v7; // rdi
  const CERT_CONTEXT *CertificateInStore; // rax

  v3 = -2147467259;
  v4 = a2 - 1;
  if ( v4 )
  {
    if ( v4 != 1 )
      return v3;
    pvPara = L"TrustedPublisher";
  }
  else
  {
    pvPara = L"Disallowed";
  }
  v6 = CertOpenStore((LPCSTR)0xA, 0, 0, 0x11080u, pvPara);
  v7 = v6;
  if ( v6 )
  {
    CertificateInStore = CertFindCertificateInStore(v6, 0, 0, 0xE0000u, pvFindPara, 0);
    if ( CertificateInStore )
    {
      v3 = 0;
      CertFreeCertificateContext(CertificateInStore);
    }
    else
    {
      v3 = 1;
    }
    CertCloseStore(v7, 0);
  }
  return v3;
}

```

## disassembly

```asm
0x18003f22c  mov     [rsp+arg_0], rbx
0x18003f231  mov     [rsp+arg_8], rsi
0x18003f236  push    rdi
0x18003f237  sub     rsp, 30h
0x18003f23b  mov     rsi, rcx
0x18003f23e  mov     ebx, 80004005h
0x18003f243  sub     edx, 1
0x18003f246  jz      short loc_18003F256
0x18003f248  cmp     edx, 1
0x18003f24b  jnz     short loc_18003F2C2
0x18003f24d  lea     rax, aTrustedpublish; "TrustedPublisher"
0x18003f254  jmp     short loc_18003F25D
0x18003f256  lea     rax, pvPara; "Disallowed"
0x18003f25d  xor     edx, edx; dwEncodingType
0x18003f25f  mov     [rsp+38h+pvPara], rax; pvPara
0x18003f264  mov     r9d, 11080h; dwFlags
0x18003f26a  xor     r8d, r8d; hCryptProv
0x18003f26d  lea     ecx, [rdx+0Ah]; lpszStoreProvider
0x18003f270  call    cs:__imp_CertOpenStore
0x18003f276  mov     rdi, rax
0x18003f279  test    rax, rax
0x18003f27c  jz      short loc_18003F2C2
0x18003f27e  mov     [rsp+38h+pPrevCertContext], 0; pPrevCertContext
0x18003f287  mov     r9d, 0E0000h; dwFindType
0x18003f28d  xor     r8d, r8d; dwFindFlags
0x18003f290  mov     [rsp+38h+pvPara], rsi; pvFindPara
0x18003f295  xor     edx, edx; dwCertEncodingType
0x18003f297  mov     rcx, rax; hCertStore
0x18003f29a  call    cs:__imp_CertFindCertificateInStore
0x18003f2a0  test    rax, rax
0x18003f2a3  jz      short loc_18003F2B2
0x18003f2a5  xor     ebx, ebx
0x18003f2a7  mov     rcx, rax; pCertContext
0x18003f2aa  call    cs:__imp_CertFreeCertificateContext
0x18003f2b0  jmp     short loc_18003F2B7
0x18003f2b2  mov     ebx, 1
0x18003f2b7  xor     edx, edx; dwFlags
0x18003f2b9  mov     rcx, rdi; hCertStore
0x18003f2bc  call    cs:__imp_CertCloseStore
0x18003f2c2  mov     rsi, [rsp+38h+arg_8]
0x18003f2c7  mov     eax, ebx
0x18003f2c9  mov     rbx, [rsp+38h+arg_0]
0x18003f2ce  add     rsp, 30h
0x18003f2d2  pop     rdi
0x18003f2d3  retn
```
