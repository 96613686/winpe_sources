# RegistrationInfoImpl::get_SecurityDescriptor(tagVARIANT *)

- ea: `0x18002e620`
- end: `0x18002e68c`
- name: `?get_SecurityDescriptor@RegistrationInfoImpl@@UEAAJPEAUtagVARIANT@@@Z`
- size: `108`
- prototype: `int(RegistrationInfoImpl *__hidden this, struct tagVARIANT *)`
- caller_count: `0`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x18002e620`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002e66d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002e66d`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002e64d`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002e64d`
- `OLEAUT32!__imp_VariantCopy` at `0x18002e65d`
- `OLEAUT32!__imp_VariantCopy` at `0x18002e65d`

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
0x18002e620  push    rbx
0x18002e622  push    rbp
0x18002e623  push    rsi
0x18002e624  push    rdi
0x18002e625  sub     rsp, 28h
0x18002e629  mov     rbp, rdx
0x18002e62c  mov     rsi, rcx
0x18002e62f  test    rdx, rdx
0x18002e632  jz      short loc_18002E67E
0x18002e634  mov     rax, rcx
0x18002e637  add     rcx, 8
0x18002e63b  neg     rax
0x18002e63e  sbb     rbx, rbx
0x18002e641  and     rbx, rcx
0x18002e644  jz      short loc_18002E685
0x18002e646  lea     rdi, [rbx+8]
0x18002e64a  mov     rcx, rdi; lpCriticalSection
0x18002e64d  call    cs:__imp_EnterCriticalSection
0x18002e653  lea     rdx, [rsi+90h]; pvargSrc
0x18002e65a  mov     rcx, rbp; pvargDest
0x18002e65d  call    cs:__imp_VariantCopy
0x18002e663  mov     esi, eax
0x18002e665  test    rbx, rbx
0x18002e668  jz      short loc_18002E673
0x18002e66a  mov     rcx, rdi; lpCriticalSection
0x18002e66d  call    cs:__imp_LeaveCriticalSection
0x18002e673  mov     eax, esi
0x18002e675  add     rsp, 28h
0x18002e679  pop     rdi
0x18002e67a  pop     rsi
0x18002e67b  pop     rbp
0x18002e67c  pop     rbx
0x18002e67d  retn
0x18002e67e  mov     eax, 80004003h
0x18002e683  jmp     short loc_18002E675
0x18002e685  mov     edi, 8
0x18002e68a  jmp     short loc_18002E653
```
