# ATL::CSecurityDesc::Clear(void)

- ea: `0x18004c550`
- end: `0x18004c667`
- name: `?Clear@CSecurityDesc@ATL@@MEAAXXZ`
- size: `279`
- prototype: `void __fastcall(ATL::CSecurityDesc *__hidden this)`
- caller_count: `3`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800265fc`
- `0x18006ae88`
- `0x18006b090`

## callees

- `0x18004c550`

## import_xrefs

- `msvcrt!free` at `0x18004c5e0`
- `msvcrt!free` at `0x18004c5fc`
- `msvcrt!free` at `0x18004c622`
- `msvcrt!free` at `0x18004c648`
- `msvcrt!free` at `0x18004c652`
- `msvcrt!free` at `0x18004c5e0`
- `msvcrt!free` at `0x18004c5fc`
- `msvcrt!free` at `0x18004c622`
- `msvcrt!free` at `0x18004c648`
- `msvcrt!free` at `0x18004c652`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorGroup` at `0x18004c5f2`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorGroup` at `0x18004c5f2`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorControl` at `0x18004c57f`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorControl` at `0x18004c57f`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorOwner` at `0x18004c5d6`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorOwner` at `0x18004c5d6`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorDacl` at `0x18004c612`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorDacl` at `0x18004c612`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorSacl` at `0x18004c638`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorSacl` at `0x18004c638`

## pseudocode

```c
void __fastcall ATL::CSecurityDesc::Clear(ATL::CSecurityDesc *this)
{
  void *v2; // rcx
  void *v3; // rcx
  PSID pGroup; // [rsp+20h] [rbp-28h] BYREF
  PACL pDacl; // [rsp+28h] [rbp-20h] BYREF
  PACL pSacl; // [rsp+30h] [rbp-18h] BYREF
  WORD pControl; // [rsp+60h] [rbp+18h] BYREF
  DWORD dwRevision; // [rsp+68h] [rbp+20h] BYREF
  WINBOOL bDaclPresent; // [rsp+70h] [rbp+28h] BYREF
  PSID pOwner; // [rsp+78h] [rbp+30h] BYREF

  v2 = (void *)*((_QWORD *)this + 1);
  if ( v2 )
  {
    dwRevision = 0;
    pControl = 0;
    if ( GetSecurityDescriptorControl(v2, &pControl, &dwRevision) && (pControl & 0x8000u) == 0 )
    {
      v3 = (void *)*((_QWORD *)this + 1);
      pOwner = 0;
      pGroup = 0;
      pDacl = 0;
      pSacl = 0;
      dwRevision = 0;
      bDaclPresent = 0;
      GetSecurityDescriptorOwner(v3, &pOwner, (LPBOOL)&dwRevision);
      free(pOwner);
      GetSecurityDescriptorGroup(*((PSECURITY_DESCRIPTOR *)this + 1), &pGroup, (LPBOOL)&dwRevision);
      free(pGroup);
      GetSecurityDescriptorDacl(*((PSECURITY_DESCRIPTOR *)this + 1), &bDaclPresent, &pDacl, (LPBOOL)&dwRevision);
      if ( bDaclPresent )
        free(pDacl);
      GetSecurityDescriptorSacl(*((PSECURITY_DESCRIPTOR *)this + 1), &bDaclPresent, &pSacl, (LPBOOL)&dwRevision);
      if ( bDaclPresent )
        free(pSacl);
    }
    free(*((void **)this + 1));
    *((_QWORD *)this + 1) = 0;
  }
}

```

## disassembly

```asm
0x18004c550  push    rbp
0x18004c552  push    rbx
0x18004c553  mov     rbp, rsp
0x18004c556  sub     rsp, 48h
0x18004c55a  mov     rbx, rcx
0x18004c55d  mov     rcx, [rcx+8]; pSecurityDescriptor
0x18004c561  test    rcx, rcx
0x18004c564  jz      loc_18004C660
0x18004c56a  xor     eax, eax
0x18004c56c  mov     [rbp+dwRevision], 0
0x18004c573  lea     r8, [rbp+dwRevision]; lpdwRevision
0x18004c577  mov     [rbp+pControl], ax
0x18004c57b  lea     rdx, [rbp+pControl]; pControl
0x18004c57f  call    cs:__imp_GetSecurityDescriptorControl
0x18004c585  test    eax, eax
0x18004c587  jz      loc_18004C64E
0x18004c58d  mov     eax, 8000h
0x18004c592  test    [rbp+pControl], ax
0x18004c596  jnz     loc_18004C64E
0x18004c59c  mov     rcx, [rbx+8]; pSecurityDescriptor
0x18004c5a0  lea     r8, [rbp+dwRevision]; lpbOwnerDefaulted
0x18004c5a4  lea     rdx, [rbp+pOwner]; pOwner
0x18004c5a8  mov     [rbp+pOwner], 0
0x18004c5b0  mov     [rbp+pGroup], 0
0x18004c5b8  mov     [rbp+pDacl], 0
0x18004c5c0  mov     [rbp+pSacl], 0
0x18004c5c8  mov     [rbp+dwRevision], 0
0x18004c5cf  mov     [rbp+bDaclPresent], 0
0x18004c5d6  call    cs:__imp_GetSecurityDescriptorOwner
0x18004c5dc  mov     rcx, [rbp+pOwner]; Block
0x18004c5e0  call    cs:__imp_free
0x18004c5e6  mov     rcx, [rbx+8]; pSecurityDescriptor
0x18004c5ea  lea     r8, [rbp+dwRevision]; lpbGroupDefaulted
0x18004c5ee  lea     rdx, [rbp+pGroup]; pGroup
0x18004c5f2  call    cs:__imp_GetSecurityDescriptorGroup
0x18004c5f8  mov     rcx, [rbp+pGroup]; Block
0x18004c5fc  call    cs:__imp_free
0x18004c602  mov     rcx, [rbx+8]; pSecurityDescriptor
0x18004c606  lea     r9, [rbp+dwRevision]; lpbDaclDefaulted
0x18004c60a  lea     r8, [rbp+pDacl]; pDacl
0x18004c60e  lea     rdx, [rbp+bDaclPresent]; lpbDaclPresent
0x18004c612  call    cs:__imp_GetSecurityDescriptorDacl
0x18004c618  cmp     [rbp+bDaclPresent], 0
0x18004c61c  jz      short loc_18004C628
0x18004c61e  mov     rcx, [rbp+pDacl]; Block
0x18004c622  call    cs:__imp_free
0x18004c628  mov     rcx, [rbx+8]; pSecurityDescriptor
0x18004c62c  lea     r9, [rbp+dwRevision]; lpbSaclDefaulted
0x18004c630  lea     r8, [rbp+pSacl]; pSacl
0x18004c634  lea     rdx, [rbp+bDaclPresent]; lpbSaclPresent
0x18004c638  call    cs:__imp_GetSecurityDescriptorSacl
0x18004c63e  cmp     [rbp+bDaclPresent], 0
0x18004c642  jz      short loc_18004C64E
0x18004c644  mov     rcx, [rbp+pSacl]; Block
0x18004c648  call    cs:__imp_free
0x18004c64e  mov     rcx, [rbx+8]; Block
0x18004c652  call    cs:__imp_free
0x18004c658  mov     qword ptr [rbx+8], 0
0x18004c660  add     rsp, 48h
0x18004c664  pop     rbx
0x18004c665  pop     rbp
0x18004c666  retn
```
