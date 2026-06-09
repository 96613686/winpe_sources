# ATL::CSecurityDesc::Clear(void)

- ea: `0x180097fa0`
- end: `0x1800980a9`
- name: `?Clear@CSecurityDesc@ATL@@MEAAXXZ`
- size: `265`
- prototype: `void __fastcall(ATL::CSecurityDesc *__hidden this)`
- caller_count: `3`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180097894`
- `0x1800e8c1c`
- `0x1800e8da0`

## callees

- `0x180097fa0`
- `0x1800e91bc`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180098022`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18009803e`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180098064`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18009808a`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180098094`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180098022`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18009803e`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180098064`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18009808a`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180098094`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorOwner` at `0x180098018`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorOwner` at `0x180098018`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorGroup` at `0x180098034`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorGroup` at `0x180098034`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorSacl` at `0x18009807a`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorSacl` at `0x18009807a`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorDacl` at `0x180098054`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorDacl` at `0x180098054`

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
0x180097fa0  push    rbp
0x180097fa2  push    rbx
0x180097fa3  mov     rbp, rsp
0x180097fa6  sub     rsp, 48h
0x180097faa  cmp     qword ptr [rcx+8], 0
0x180097faf  mov     rbx, rcx
0x180097fb2  jz      loc_1800980A2
0x180097fb8  xor     eax, eax
0x180097fba  lea     rdx, [rbp+arg_0]; unsigned __int16 *
0x180097fbe  mov     [rbp+arg_0], ax
0x180097fc2  call    ?GetControl@CSecurityDesc@ATL@@QEBA_NPEAG@Z; ATL::CSecurityDesc::GetControl(ushort *)
0x180097fc7  test    al, al
0x180097fc9  jz      loc_180098090
0x180097fcf  mov     eax, 8000h
0x180097fd4  test    [rbp+arg_0], ax
0x180097fd8  jnz     loc_180098090
0x180097fde  mov     rcx, [rbx+8]; pSecurityDescriptor
0x180097fe2  lea     r8, [rbp+bOwnerDefaulted]; lpbOwnerDefaulted
0x180097fe6  lea     rdx, [rbp+pOwner]; pOwner
0x180097fea  mov     [rbp+pOwner], 0
0x180097ff2  mov     [rbp+pGroup], 0
0x180097ffa  mov     [rbp+pDacl], 0
0x180098002  mov     [rbp+pSacl], 0
0x18009800a  mov     [rbp+bOwnerDefaulted], 0
0x180098011  mov     [rbp+bDaclPresent], 0
0x180098018  call    cs:__imp_GetSecurityDescriptorOwner
0x18009801e  mov     rcx, [rbp+pOwner]; Block
0x180098022  call    cs:__imp_free
0x180098028  mov     rcx, [rbx+8]; pSecurityDescriptor
0x18009802c  lea     r8, [rbp+bOwnerDefaulted]; lpbGroupDefaulted
0x180098030  lea     rdx, [rbp+pGroup]; pGroup
0x180098034  call    cs:__imp_GetSecurityDescriptorGroup
0x18009803a  mov     rcx, [rbp+pGroup]; Block
0x18009803e  call    cs:__imp_free
0x180098044  mov     rcx, [rbx+8]; pSecurityDescriptor
0x180098048  lea     r9, [rbp+bOwnerDefaulted]; lpbDaclDefaulted
0x18009804c  lea     r8, [rbp+pDacl]; pDacl
0x180098050  lea     rdx, [rbp+bDaclPresent]; lpbDaclPresent
0x180098054  call    cs:__imp_GetSecurityDescriptorDacl
0x18009805a  cmp     [rbp+bDaclPresent], 0
0x18009805e  jz      short loc_18009806A
0x180098060  mov     rcx, [rbp+pDacl]; Block
0x180098064  call    cs:__imp_free
0x18009806a  mov     rcx, [rbx+8]; pSecurityDescriptor
0x18009806e  lea     r9, [rbp+bOwnerDefaulted]; lpbSaclDefaulted
0x180098072  lea     r8, [rbp+pSacl]; pSacl
0x180098076  lea     rdx, [rbp+bDaclPresent]; lpbSaclPresent
0x18009807a  call    cs:__imp_GetSecurityDescriptorSacl
0x180098080  cmp     [rbp+bDaclPresent], 0
0x180098084  jz      short loc_180098090
0x180098086  mov     rcx, [rbp+pSacl]; Block
0x18009808a  call    cs:__imp_free
0x180098090  mov     rcx, [rbx+8]; Block
0x180098094  call    cs:__imp_free
0x18009809a  mov     qword ptr [rbx+8], 0
0x1800980a2  add     rsp, 48h
0x1800980a6  pop     rbx
0x1800980a7  pop     rbp
0x1800980a8  retn
```
