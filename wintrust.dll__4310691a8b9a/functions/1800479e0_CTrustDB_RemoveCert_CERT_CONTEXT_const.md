# CTrustDB::RemoveCert(_CERT_CONTEXT const *)

- ea: `0x1800479e0`
- end: `0x180047a46`
- name: `?RemoveCert@CTrustDB@@EEAAJPEBU_CERT_CONTEXT@@@Z`
- size: `102`
- prototype: `int(CTrustDB *__hidden this, const struct _CERT_CONTEXT *)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x180047860`
- `0x1800479e0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180047a22`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180047a22`
- `CRYPT32!CertDeleteCertificateFromStore` at `0x180047a14`
- `CRYPT32!CertDeleteCertificateFromStore` at `0x180047a14`
- `CRYPT32!CertDuplicateCertificateContext` at `0x1800479fa`
- `CRYPT32!CertDuplicateCertificateContext` at `0x1800479fa`

## pseudocode

```c
int __fastcall CTrustDB::RemoveCert(CTrustDB *this, const struct _CERT_CONTEXT *a2)
{
  const CERT_CONTEXT *CertificateInStore; // rax
  int result; // eax

  if ( !*((_QWORD *)this + 2) )
    return 1;
  CertDuplicateCertificateContext(a2);
  CertificateInStore = FindCertificateInStore(*((HCERTSTORE *)this + 2), a2);
  if ( CertificateInStore && CertDeleteCertificateFromStore(CertificateInStore) )
    return 0;
  result = GetLastError();
  if ( result > 0 )
    return (unsigned __int16)result | 0x80070000;
  return result;
}

```

## disassembly

```asm
0x1800479e0  mov     [rsp+arg_0], rbx
0x1800479e5  push    rdi
0x1800479e6  sub     rsp, 20h
0x1800479ea  cmp     qword ptr [rcx+10h], 0
0x1800479ef  mov     rdi, rdx
0x1800479f2  mov     rbx, rcx
0x1800479f5  jz      short loc_180047A36
0x1800479f7  mov     rcx, rdx; pCertContext
0x1800479fa  call    cs:__imp_CertDuplicateCertificateContext
0x180047a00  mov     rcx, [rbx+10h]; hCertStore
0x180047a04  mov     rdx, rdi; pCertContext
0x180047a07  call    ?FindCertificateInStore@@YAPEBU_CERT_CONTEXT@@PEAXPEBU1@@Z; FindCertificateInStore(void *,_CERT_CONTEXT const *)
0x180047a0c  test    rax, rax
0x180047a0f  jz      short loc_180047A22
0x180047a11  mov     rcx, rax; pCertContext
0x180047a14  call    cs:__imp_CertDeleteCertificateFromStore
0x180047a1a  test    eax, eax
0x180047a1c  jz      short loc_180047A22
0x180047a1e  xor     eax, eax
0x180047a20  jmp     short loc_180047A3B
0x180047a22  call    cs:__imp_GetLastError
0x180047a28  test    eax, eax
0x180047a2a  jle     short loc_180047A3B
0x180047a2c  movzx   eax, ax
0x180047a2f  or      eax, 80070000h
0x180047a34  jmp     short loc_180047A3B
0x180047a36  mov     eax, 1
0x180047a3b  mov     rbx, [rsp+28h+arg_0]
0x180047a40  add     rsp, 20h
0x180047a44  pop     rdi
0x180047a45  retn
```
