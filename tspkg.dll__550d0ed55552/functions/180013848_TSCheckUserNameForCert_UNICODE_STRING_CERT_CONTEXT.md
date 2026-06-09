# TSCheckUserNameForCert(_UNICODE_STRING *,_CERT_CONTEXT * *)

- ea: `0x180013848`
- end: `0x1800139c9`
- name: `?TSCheckUserNameForCert@@YAJPEAU_UNICODE_STRING@@PEAPEAU_CERT_CONTEXT@@@Z`
- size: `385`
- prototype: `__int64 __fastcall(struct _UNICODE_STRING *, struct _CERT_CONTEXT **)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180013468`

## callees

- `0x18000b550`
- `0x180013848`
- `0x18001c63c`
- `0x18001d010`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180013988`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180013988`
- `CRYPT32!CertOpenStore` at `0x18001391c`
- `CRYPT32!CertOpenStore` at `0x18001391c`
- `CRYPT32!CertFindCertificateInStore` at `0x18001396a`
- `CRYPT32!CertFindCertificateInStore` at `0x18001396a`
- `CRYPT32!CertCloseStore` at `0x180013982`
- `CRYPT32!CertCloseStore` at `0x180013982`
- `api-ms-win-security-credentials-l1-1-0!CredFree` at `0x18001399f`
- `api-ms-win-security-credentials-l1-1-0!CredFree` at `0x18001399f`
- `api-ms-win-security-credentials-l1-1-0!CredUnmarshalCredentialW` at `0x1800138cf`
- `api-ms-win-security-credentials-l1-1-0!CredUnmarshalCredentialW` at `0x1800138cf`

## pseudocode

```c
__int64 __fastcall TSCheckUserNameForCert(struct _UNICODE_STRING *a1, struct _CERT_CONTEXT **a2)
{
  PVOID v4; // rcx
  unsigned __int64 Length; // rdi
  int v6; // ebx
  HCERTSTORE v7; // rdi
  struct _CERT_CONTEXT *CertificateInStore; // rax
  enum _CRED_MARSHAL_TYPE CredType; // [rsp+30h] [rbp-D0h] BYREF
  PVOID Credential; // [rsp+38h] [rbp-C8h] BYREF
  __int128 pvFindPara; // [rsp+40h] [rbp-C0h] BYREF
  WCHAR MarshaledCredential[520]; // [rsp+50h] [rbp-B0h] BYREF

  CredType = 0;
  v4 = 0;
  Credential = 0;
  *a2 = 0;
  Length = a1->Length;
  pvFindPara = 0;
  if ( Length + 2 > 0x404 )
  {
    v6 = -1073741670;
  }
  else
  {
    v6 = 0;
    memcpy_0(MarshaledCredential, a1->Buffer, (unsigned int)Length);
    MarshaledCredential[Length >> 1] = 0;
    if ( CredUnmarshalCredentialW(MarshaledCredential, &CredType, &Credential) )
    {
      if ( CredType == CertCredential )
      {
        v6 = TSGlobalLsaFunctions->ImpersonateClient();
        if ( v6 >= 0 )
        {
          v7 = CertOpenStore((LPCSTR)0xA, 0, 0, 0x10000u, L"MY");
          if ( v7 )
          {
            *((_QWORD *)&pvFindPara + 1) = (char *)Credential + 4;
            LODWORD(pvFindPara) = 20;
            CertificateInStore = (struct _CERT_CONTEXT *)CertFindCertificateInStore(
                                                           v7,
                                                           0x10001u,
                                                           0,
                                                           0x10000u,
                                                           &pvFindPara,
                                                           0);
            *a2 = CertificateInStore;
            if ( !CertificateInStore )
              v6 = -2146893042;
            CertCloseStore(v7, 0);
          }
          else
          {
            v6 = -2146893042;
          }
          RevertToSelf();
        }
      }
    }
    v4 = Credential;
  }
  if ( v4 )
    CredFree(v4);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x180013848  mov     [rsp-8+arg_10], rbx
0x18001384d  push    rbp
0x18001384e  push    rsi
0x18001384f  push    rdi
0x180013850  lea     rbp, [rsp-370h]
0x180013858  sub     rsp, 470h
0x18001385f  mov     rax, cs:__security_cookie
0x180013866  xor     rax, rsp
0x180013869  mov     [rbp+380h+var_20], rax
0x180013870  mov     rsi, rdx
0x180013873  mov     [rsp+480h+CredType], 0
0x18001387b  mov     rdx, rcx
0x18001387e  xorps   xmm0, xmm0
0x180013881  xor     ecx, ecx; Buffer
0x180013883  mov     [rsp+480h+Credential], rcx
0x180013888  mov     [rsi], rcx
0x18001388b  movzx   edi, word ptr [rdx]
0x18001388e  movups  [rsp+480h+pvFindPara], xmm0
0x180013893  lea     rax, [rdi+2]
0x180013897  cmp     rax, 404h
0x18001389d  ja      loc_180013995
0x1800138a3  mov     rdx, [rdx+8]; Src
0x1800138a7  lea     rcx, [rsp+480h+MarshaledCredential]; void *
0x1800138ac  mov     r8d, edi; Size
0x1800138af  xor     ebx, ebx
0x1800138b1  call    memcpy_0
0x1800138b6  xor     eax, eax
0x1800138b8  shr     rdi, 1
0x1800138bb  lea     r8, [rsp+480h+Credential]; Credential
0x1800138c0  lea     rdx, [rsp+480h+CredType]; CredType
0x1800138c5  lea     rcx, [rsp+480h+MarshaledCredential]; MarshaledCredential
0x1800138ca  mov     [rsp+rdi*2+480h+MarshaledCredential], ax
0x1800138cf  call    cs:__imp_CredUnmarshalCredentialW
0x1800138d5  test    eax, eax
0x1800138d7  jz      loc_18001398E
0x1800138dd  cmp     [rsp+480h+CredType], 1
0x1800138e2  jnz     loc_18001398E
0x1800138e8  mov     rax, cs:?TSGlobalLsaFunctions@@3PEAU_LSA_SECPKG_FUNCTION_TABLE@@EA; _LSA_SECPKG_FUNCTION_TABLE * TSGlobalLsaFunctions
0x1800138ef  mov     rax, [rax+58h]
0x1800138f3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800138f8  mov     ebx, eax
0x1800138fa  test    eax, eax
0x1800138fc  js      loc_18001398E
0x180013902  xor     edx, edx; dwEncodingType
0x180013904  lea     rax, aMy; "MY"
0x18001390b  mov     r9d, 10000h; dwFlags
0x180013911  mov     [rsp+480h+pvPara], rax; pvPara
0x180013916  xor     r8d, r8d; hCryptProv
0x180013919  lea     ecx, [rdx+0Ah]; lpszStoreProvider
0x18001391c  call    cs:__imp_CertOpenStore
0x180013922  mov     rdi, rax
0x180013925  test    rax, rax
0x180013928  jnz     short loc_180013931
0x18001392a  mov     ebx, 8009030Eh
0x18001392f  jmp     short loc_180013988
0x180013931  mov     rax, [rsp+480h+Credential]
0x180013936  mov     r9d, 10000h; dwFindType
0x18001393c  add     rax, 4
0x180013940  mov     [rsp+480h+pPrevCertContext], 0; pPrevCertContext
0x180013949  mov     qword ptr [rsp+480h+pvFindPara+8], rax
0x18001394e  xor     r8d, r8d; dwFindFlags
0x180013951  lea     rax, [rsp+480h+pvFindPara]
0x180013956  mov     dword ptr [rsp+480h+pvFindPara], 14h
0x18001395e  lea     edx, [r9+1]; dwCertEncodingType
0x180013962  mov     [rsp+480h+pvPara], rax; pvFindPara
0x180013967  mov     rcx, rdi; hCertStore
0x18001396a  call    cs:__imp_CertFindCertificateInStore
0x180013970  mov     [rsi], rax
0x180013973  test    rax, rax
0x180013976  jnz     short loc_18001397D
0x180013978  mov     ebx, 8009030Eh
0x18001397d  xor     edx, edx; dwFlags
0x18001397f  mov     rcx, rdi; hCertStore
0x180013982  call    cs:__imp_CertCloseStore
0x180013988  call    cs:__imp_RevertToSelf
0x18001398e  mov     rcx, [rsp+480h+Credential]
0x180013993  jmp     short loc_18001399A
0x180013995  mov     ebx, 0C000009Ah
0x18001399a  test    rcx, rcx
0x18001399d  jz      short loc_1800139A5
0x18001399f  call    cs:__imp_CredFree
0x1800139a5  mov     eax, ebx
0x1800139a7  mov     rcx, [rbp+380h+var_20]
0x1800139ae  xor     rcx, rsp; StackCookie
0x1800139b1  call    __security_check_cookie
0x1800139b6  mov     rbx, [rsp+480h+arg_10]
0x1800139be  add     rsp, 470h
0x1800139c5  pop     rdi
0x1800139c6  pop     rsi
0x1800139c7  pop     rbp
0x1800139c8  retn
```
