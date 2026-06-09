# ATL::CSecurityDesc::Clear(void)

- ea: `0x1400610a0`
- end: `0x1400611a9`
- name: `?Clear@CSecurityDesc@ATL@@MEAAXXZ`
- size: `265`
- prototype: `void __fastcall(ATL::CSecurityDesc *__hidden this)`
- caller_count: `3`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x14005f478`
- `0x14005f9f0`
- `0x140062ce8`

## callees

- `0x1400610a0`
- `0x140061e9c`

## import_xrefs

- `ADVAPI32!GetSecurityDescriptorSacl` at `0x14006117a`
- `ADVAPI32!GetSecurityDescriptorSacl` at `0x14006117a`
- `ADVAPI32!GetSecurityDescriptorDacl` at `0x140061154`
- `ADVAPI32!GetSecurityDescriptorDacl` at `0x140061154`
- `ADVAPI32!GetSecurityDescriptorGroup` at `0x140061134`
- `ADVAPI32!GetSecurityDescriptorGroup` at `0x140061134`
- `ADVAPI32!GetSecurityDescriptorOwner` at `0x140061118`
- `ADVAPI32!GetSecurityDescriptorOwner` at `0x140061118`
- `msvcrt!free` at `0x140061122`
- `msvcrt!free` at `0x14006113e`
- `msvcrt!free` at `0x140061164`
- `msvcrt!free` at `0x14006118a`
- `msvcrt!free` at `0x140061194`
- `msvcrt!free` at `0x140061122`
- `msvcrt!free` at `0x14006113e`
- `msvcrt!free` at `0x140061164`
- `msvcrt!free` at `0x14006118a`
- `msvcrt!free` at `0x140061194`

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
0x1400610a0  push    rbp
0x1400610a2  push    rbx
0x1400610a3  mov     rbp, rsp
0x1400610a6  sub     rsp, 48h
0x1400610aa  cmp     qword ptr [rcx+8], 0
0x1400610af  mov     rbx, rcx
0x1400610b2  jz      loc_1400611A2
0x1400610b8  xor     eax, eax
0x1400610ba  lea     rdx, [rbp+arg_0]; unsigned __int16 *
0x1400610be  mov     [rbp+arg_0], ax
0x1400610c2  call    ?GetControl@CSecurityDesc@ATL@@QEBA_NPEAG@Z; ATL::CSecurityDesc::GetControl(ushort *)
0x1400610c7  test    al, al
0x1400610c9  jz      loc_140061190
0x1400610cf  mov     eax, 8000h
0x1400610d4  test    [rbp+arg_0], ax
0x1400610d8  jnz     loc_140061190
0x1400610de  mov     rcx, [rbx+8]; pSecurityDescriptor
0x1400610e2  lea     r8, [rbp+bOwnerDefaulted]; lpbOwnerDefaulted
0x1400610e6  lea     rdx, [rbp+pOwner]; pOwner
0x1400610ea  mov     [rbp+pOwner], 0
0x1400610f2  mov     [rbp+pGroup], 0
0x1400610fa  mov     [rbp+pDacl], 0
0x140061102  mov     [rbp+pSacl], 0
0x14006110a  mov     [rbp+bOwnerDefaulted], 0
0x140061111  mov     [rbp+bDaclPresent], 0
0x140061118  call    cs:__imp_GetSecurityDescriptorOwner
0x14006111e  mov     rcx, [rbp+pOwner]; Block
0x140061122  call    cs:__imp_free
0x140061128  mov     rcx, [rbx+8]; pSecurityDescriptor
0x14006112c  lea     r8, [rbp+bOwnerDefaulted]; lpbGroupDefaulted
0x140061130  lea     rdx, [rbp+pGroup]; pGroup
0x140061134  call    cs:__imp_GetSecurityDescriptorGroup
0x14006113a  mov     rcx, [rbp+pGroup]; Block
0x14006113e  call    cs:__imp_free
0x140061144  mov     rcx, [rbx+8]; pSecurityDescriptor
0x140061148  lea     r9, [rbp+bOwnerDefaulted]; lpbDaclDefaulted
0x14006114c  lea     r8, [rbp+pDacl]; pDacl
0x140061150  lea     rdx, [rbp+bDaclPresent]; lpbDaclPresent
0x140061154  call    cs:__imp_GetSecurityDescriptorDacl
0x14006115a  cmp     [rbp+bDaclPresent], 0
0x14006115e  jz      short loc_14006116A
0x140061160  mov     rcx, [rbp+pDacl]; Block
0x140061164  call    cs:__imp_free
0x14006116a  mov     rcx, [rbx+8]; pSecurityDescriptor
0x14006116e  lea     r9, [rbp+bOwnerDefaulted]; lpbSaclDefaulted
0x140061172  lea     r8, [rbp+pSacl]; pSacl
0x140061176  lea     rdx, [rbp+bDaclPresent]; lpbSaclPresent
0x14006117a  call    cs:__imp_GetSecurityDescriptorSacl
0x140061180  cmp     [rbp+bDaclPresent], 0
0x140061184  jz      short loc_140061190
0x140061186  mov     rcx, [rbp+pSacl]; Block
0x14006118a  call    cs:__imp_free
0x140061190  mov     rcx, [rbx+8]; Block
0x140061194  call    cs:__imp_free
0x14006119a  mov     qword ptr [rbx+8], 0
0x1400611a2  add     rsp, 48h
0x1400611a6  pop     rbx
0x1400611a7  pop     rbp
0x1400611a8  retn
```
