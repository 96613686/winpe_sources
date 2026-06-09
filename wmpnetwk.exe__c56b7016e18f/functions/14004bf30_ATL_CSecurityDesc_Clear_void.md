# ATL::CSecurityDesc::Clear(void)

- ea: `0x14004bf30`
- end: `0x14004c039`
- name: `?Clear@CSecurityDesc@ATL@@MEAAXXZ`
- size: `265`
- prototype: `void __fastcall(ATL::CSecurityDesc *__hidden this)`
- caller_count: `4`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x14004b0b8`
- `0x14004b4f0`
- `0x14004e7c0`
- `0x140051db0`

## callees

- `0x14004bf30`
- `0x14004d9bc`

## import_xrefs

- `ADVAPI32!GetSecurityDescriptorOwner` at `0x14004bfa8`
- `ADVAPI32!GetSecurityDescriptorOwner` at `0x14004bfa8`
- `ADVAPI32!GetSecurityDescriptorGroup` at `0x14004bfc4`
- `ADVAPI32!GetSecurityDescriptorGroup` at `0x14004bfc4`
- `ADVAPI32!GetSecurityDescriptorDacl` at `0x14004bfe4`
- `ADVAPI32!GetSecurityDescriptorDacl` at `0x14004bfe4`
- `ADVAPI32!GetSecurityDescriptorSacl` at `0x14004c00a`
- `ADVAPI32!GetSecurityDescriptorSacl` at `0x14004c00a`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x14004bfb2`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x14004bfce`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x14004bff4`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x14004c01a`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x14004c024`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x14004bfb2`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x14004bfce`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x14004bff4`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x14004c01a`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x14004c024`

## pseudocode

```c
void __fastcall ATL::CSecurityDesc::Clear(ATL::CSecurityDesc *this)
{
  void *v2; // rcx
  PSID pGroup; // [rsp+20h] [rbp-28h] BYREF
  PACL pDacl; // [rsp+28h] [rbp-20h] BYREF
  PACL pSacl; // [rsp+30h] [rbp-18h] BYREF
  unsigned __int16 v6; // [rsp+60h] [rbp+18h] BYREF
  WINBOOL bOwnerDefaulted; // [rsp+68h] [rbp+20h] BYREF
  WINBOOL bDaclPresent; // [rsp+70h] [rbp+28h] BYREF
  PSID pOwner; // [rsp+78h] [rbp+30h] BYREF

  if ( *((_QWORD *)this + 1) )
  {
    v6 = 0;
    if ( ATL::CSecurityDesc::GetControl(this, &v6) && (v6 & 0x8000u) == 0 )
    {
      v2 = (void *)*((_QWORD *)this + 1);
      pOwner = 0;
      pGroup = 0;
      pDacl = 0;
      pSacl = 0;
      bOwnerDefaulted = 0;
      bDaclPresent = 0;
      GetSecurityDescriptorOwner(v2, &pOwner, &bOwnerDefaulted);
      free(pOwner);
      GetSecurityDescriptorGroup(*((PSECURITY_DESCRIPTOR *)this + 1), &pGroup, &bOwnerDefaulted);
      free(pGroup);
      GetSecurityDescriptorDacl(*((PSECURITY_DESCRIPTOR *)this + 1), &bDaclPresent, &pDacl, &bOwnerDefaulted);
      if ( bDaclPresent )
        free(pDacl);
      GetSecurityDescriptorSacl(*((PSECURITY_DESCRIPTOR *)this + 1), &bDaclPresent, &pSacl, &bOwnerDefaulted);
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
0x14004bf30  push    rbp
0x14004bf32  push    rbx
0x14004bf33  mov     rbp, rsp
0x14004bf36  sub     rsp, 48h
0x14004bf3a  cmp     qword ptr [rcx+8], 0
0x14004bf3f  mov     rbx, rcx
0x14004bf42  jz      loc_14004C032
0x14004bf48  xor     eax, eax
0x14004bf4a  lea     rdx, [rbp+arg_0]; unsigned __int16 *
0x14004bf4e  mov     [rbp+arg_0], ax
0x14004bf52  call    ?GetControl@CSecurityDesc@ATL@@QEBA_NPEAG@Z; ATL::CSecurityDesc::GetControl(ushort *)
0x14004bf57  test    al, al
0x14004bf59  jz      loc_14004C020
0x14004bf5f  mov     eax, 8000h
0x14004bf64  test    [rbp+arg_0], ax
0x14004bf68  jnz     loc_14004C020
0x14004bf6e  mov     rcx, [rbx+8]; pSecurityDescriptor
0x14004bf72  lea     r8, [rbp+bOwnerDefaulted]; lpbOwnerDefaulted
0x14004bf76  lea     rdx, [rbp+pOwner]; pOwner
0x14004bf7a  mov     [rbp+pOwner], 0
0x14004bf82  mov     [rbp+pGroup], 0
0x14004bf8a  mov     [rbp+pDacl], 0
0x14004bf92  mov     [rbp+pSacl], 0
0x14004bf9a  mov     [rbp+bOwnerDefaulted], 0
0x14004bfa1  mov     [rbp+bDaclPresent], 0
0x14004bfa8  call    cs:__imp_GetSecurityDescriptorOwner
0x14004bfae  mov     rcx, [rbp+pOwner]; Block
0x14004bfb2  call    cs:__imp_free
0x14004bfb8  mov     rcx, [rbx+8]; pSecurityDescriptor
0x14004bfbc  lea     r8, [rbp+bOwnerDefaulted]; lpbGroupDefaulted
0x14004bfc0  lea     rdx, [rbp+pGroup]; pGroup
0x14004bfc4  call    cs:__imp_GetSecurityDescriptorGroup
0x14004bfca  mov     rcx, [rbp+pGroup]; Block
0x14004bfce  call    cs:__imp_free
0x14004bfd4  mov     rcx, [rbx+8]; pSecurityDescriptor
0x14004bfd8  lea     r9, [rbp+bOwnerDefaulted]; lpbDaclDefaulted
0x14004bfdc  lea     r8, [rbp+pDacl]; pDacl
0x14004bfe0  lea     rdx, [rbp+bDaclPresent]; lpbDaclPresent
0x14004bfe4  call    cs:__imp_GetSecurityDescriptorDacl
0x14004bfea  cmp     [rbp+bDaclPresent], 0
0x14004bfee  jz      short loc_14004BFFA
0x14004bff0  mov     rcx, [rbp+pDacl]; Block
0x14004bff4  call    cs:__imp_free
0x14004bffa  mov     rcx, [rbx+8]; pSecurityDescriptor
0x14004bffe  lea     r9, [rbp+bOwnerDefaulted]; lpbSaclDefaulted
0x14004c002  lea     r8, [rbp+pSacl]; pSacl
0x14004c006  lea     rdx, [rbp+bDaclPresent]; lpbSaclPresent
0x14004c00a  call    cs:__imp_GetSecurityDescriptorSacl
0x14004c010  cmp     [rbp+bDaclPresent], 0
0x14004c014  jz      short loc_14004C020
0x14004c016  mov     rcx, [rbp+pSacl]; Block
0x14004c01a  call    cs:__imp_free
0x14004c020  mov     rcx, [rbx+8]; Block
0x14004c024  call    cs:__imp_free
0x14004c02a  mov     qword ptr [rbx+8], 0
0x14004c032  add     rsp, 48h
0x14004c036  pop     rbx
0x14004c037  pop     rbp
0x14004c038  retn
```
