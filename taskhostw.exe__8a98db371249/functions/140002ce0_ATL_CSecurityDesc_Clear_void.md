# ATL::CSecurityDesc::Clear(void)

- ea: `0x140002ce0`
- end: `0x140002dde`
- name: `?Clear@CSecurityDesc@ATL@@MEAAXXZ`
- size: `254`
- prototype: `void __fastcall(ATL::CSecurityDesc *__hidden this)`
- caller_count: `3`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1400022d0`
- `0x1400073ec`
- `0x140009540`

## callees

- `0x140002ce0`

## import_xrefs

- `msvcrt!free` at `0x140002d1a`
- `msvcrt!free` at `0x140002d67`
- `msvcrt!free` at `0x140002d83`
- `msvcrt!free` at `0x140002dc7`
- `msvcrt!free` at `0x140002dd6`
- `msvcrt!free` at `0x140002d1a`
- `msvcrt!free` at `0x140002d67`
- `msvcrt!free` at `0x140002d83`
- `msvcrt!free` at `0x140002dc7`
- `msvcrt!free` at `0x140002dd6`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorOwner` at `0x140002d5d`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorOwner` at `0x140002d5d`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorGroup` at `0x140002d79`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorGroup` at `0x140002d79`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorDacl` at `0x140002d99`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorDacl` at `0x140002d99`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorSacl` at `0x140002db4`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorSacl` at `0x140002db4`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorControl` at `0x140002d0c`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorControl` at `0x140002d0c`

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
0x140002ce0  push    rbp
0x140002ce2  push    rbx
0x140002ce3  mov     rbp, rsp
0x140002ce6  sub     rsp, 48h
0x140002cea  mov     rbx, rcx
0x140002ced  mov     rcx, [rcx+8]; pSecurityDescriptor
0x140002cf1  test    rcx, rcx
0x140002cf4  jz      short loc_140002D29
0x140002cf6  mov     [rsp+48h+var_8], rdi
0x140002cfb  lea     r8, [rbp+dwRevision]; lpdwRevision
0x140002cff  xor     edi, edi
0x140002d01  lea     rdx, [rbp+pControl]; pControl
0x140002d05  mov     [rbp+dwRevision], edi
0x140002d08  mov     [rbp+pControl], di
0x140002d0c  call    cs:__imp_GetSecurityDescriptorControl
0x140002d12  test    eax, eax
0x140002d14  jnz     short loc_140002D30
0x140002d16  mov     rcx, [rbx+8]; Block
0x140002d1a  call    cs:__imp_free
0x140002d20  mov     [rbx+8], rdi
0x140002d24  mov     rdi, [rsp+48h+var_8]
0x140002d29  add     rsp, 48h
0x140002d2d  pop     rbx
0x140002d2e  pop     rbp
0x140002d2f  retn
0x140002d30  mov     eax, 8000h
0x140002d35  test    [rbp+pControl], ax
0x140002d39  jnz     short loc_140002D16
0x140002d3b  mov     rcx, [rbx+8]; pSecurityDescriptor
0x140002d3f  lea     r8, [rbp+dwRevision]; lpbOwnerDefaulted
0x140002d43  lea     rdx, [rbp+pOwner]; pOwner
0x140002d47  mov     [rbp+pOwner], rdi
0x140002d4b  mov     [rbp+pGroup], rdi
0x140002d4f  mov     [rbp+pDacl], rdi
0x140002d53  mov     [rbp+pSacl], rdi
0x140002d57  mov     [rbp+dwRevision], edi
0x140002d5a  mov     [rbp+bDaclPresent], edi
0x140002d5d  call    cs:__imp_GetSecurityDescriptorOwner
0x140002d63  mov     rcx, [rbp+pOwner]; Block
0x140002d67  call    cs:__imp_free
0x140002d6d  mov     rcx, [rbx+8]; pSecurityDescriptor
0x140002d71  lea     r8, [rbp+dwRevision]; lpbGroupDefaulted
0x140002d75  lea     rdx, [rbp+pGroup]; pGroup
0x140002d79  call    cs:__imp_GetSecurityDescriptorGroup
0x140002d7f  mov     rcx, [rbp+pGroup]; Block
0x140002d83  call    cs:__imp_free
0x140002d89  mov     rcx, [rbx+8]; pSecurityDescriptor
0x140002d8d  lea     r9, [rbp+dwRevision]; lpbDaclDefaulted
0x140002d91  lea     r8, [rbp+pDacl]; pDacl
0x140002d95  lea     rdx, [rbp+bDaclPresent]; lpbDaclPresent
0x140002d99  call    cs:__imp_GetSecurityDescriptorDacl
0x140002d9f  cmp     [rbp+bDaclPresent], edi
0x140002da2  jnz     short loc_140002DD2
0x140002da4  mov     rcx, [rbx+8]; pSecurityDescriptor
0x140002da8  lea     r9, [rbp+dwRevision]; lpbSaclDefaulted
0x140002dac  lea     r8, [rbp+pSacl]; pSacl
0x140002db0  lea     rdx, [rbp+bDaclPresent]; lpbSaclPresent
0x140002db4  call    cs:__imp_GetSecurityDescriptorSacl
0x140002dba  cmp     [rbp+bDaclPresent], edi
0x140002dbd  jz      loc_140002D16
0x140002dc3  mov     rcx, [rbp+pSacl]; Block
0x140002dc7  call    cs:__imp_free
0x140002dcd  jmp     loc_140002D16
0x140002dd2  mov     rcx, [rbp+pDacl]; Block
0x140002dd6  call    cs:__imp_free
0x140002ddc  jmp     short loc_140002DA4
```
