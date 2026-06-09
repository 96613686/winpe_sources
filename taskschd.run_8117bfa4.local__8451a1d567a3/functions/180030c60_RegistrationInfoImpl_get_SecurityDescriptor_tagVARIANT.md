# RegistrationInfoImpl::get_SecurityDescriptor(tagVARIANT *)

- ea: `0x180030c60`
- end: `0x180030cdf`
- name: `?get_SecurityDescriptor@RegistrationInfoImpl@@UEAAJPEAUtagVARIANT@@@Z`
- size: `127`
- prototype: `int(RegistrationInfoImpl *__hidden this, struct tagVARIANT *)`
- caller_count: `0`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x180030c60`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180030cb9`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180030cb9`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180030c8d`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180030c8d`
- `OLEAUT32!__imp_VariantCopy` at `0x180030ca3`
- `OLEAUT32!__imp_VariantCopy` at `0x180030ca3`

## pseudocode

```c
__int64 __fastcall RegistrationInfoImpl::get_SecurityDescriptor(const VARIANTARG *this, struct tagVARIANT *a2)
{
  unsigned __int64 v4; // rbx
  __int64 v5; // rdi
  unsigned int v6; // esi

  if ( !a2 )
    return 2147500035LL;
  v4 = (unsigned __int64)&this->ullVal & -(__int64)(this != 0);
  if ( v4 )
  {
    v5 = v4 + 8;
    EnterCriticalSection((LPCRITICAL_SECTION)(v4 + 8));
  }
  else
  {
    v5 = 8;
  }
  v6 = VariantCopy(a2, this + 6);
  if ( v4 )
    LeaveCriticalSection((LPCRITICAL_SECTION)v5);
  return v6;
}

```

## disassembly

```asm
0x180030c60  push    rbx
0x180030c62  push    rbp
0x180030c63  push    rsi
0x180030c64  push    rdi
0x180030c65  sub     rsp, 28h
0x180030c69  mov     rbp, rdx
0x180030c6c  mov     rsi, rcx
0x180030c6f  test    rdx, rdx
0x180030c72  jz      short loc_180030CD1
0x180030c74  mov     rax, rcx
0x180030c77  add     rcx, 8
0x180030c7b  neg     rax
0x180030c7e  sbb     rbx, rbx
0x180030c81  and     rbx, rcx
0x180030c84  jz      short loc_180030CD8
0x180030c86  lea     rdi, [rbx+8]
0x180030c8a  mov     rcx, rdi; lpCriticalSection
0x180030c8d  call    cs:__imp_EnterCriticalSection
0x180030c94  nop     dword ptr [rax+rax+00h]
0x180030c99  lea     rdx, [rsi+90h]; pvargSrc
0x180030ca0  mov     rcx, rbp; pvargDest
0x180030ca3  call    cs:__imp_VariantCopy
0x180030caa  nop     dword ptr [rax+rax+00h]
0x180030caf  mov     esi, eax
0x180030cb1  test    rbx, rbx
0x180030cb4  jz      short loc_180030CC5
0x180030cb6  mov     rcx, rdi; lpCriticalSection
0x180030cb9  call    cs:__imp_LeaveCriticalSection
0x180030cc0  nop     dword ptr [rax+rax+00h]
0x180030cc5  mov     eax, esi
0x180030cc7  add     rsp, 28h
0x180030ccb  pop     rdi
0x180030ccc  pop     rsi
0x180030ccd  pop     rbp
0x180030cce  pop     rbx
0x180030ccf  retn
0x180030cd1  mov     eax, 80004003h
0x180030cd6  jmp     short loc_180030CC7
0x180030cd8  mov     edi, 8
0x180030cdd  jmp     short loc_180030C99
```
