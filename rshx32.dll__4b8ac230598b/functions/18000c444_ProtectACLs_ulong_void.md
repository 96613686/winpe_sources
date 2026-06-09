# ProtectACLs(ulong,void *)

- ea: `0x18000c444`
- end: `0x18000c572`
- name: `?ProtectACLs@@YAXKPEAX@Z`
- size: `302`
- prototype: `void __fastcall(int, void *)`
- caller_count: `2`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18000c230`
- `0x180015f8c`

## callees

- `0x18000c444`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorDacl` at `0x18000c4ce`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorDacl` at `0x18000c4ce`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorControl` at `0x18000c488`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorControl` at `0x18000c488`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorControl` at `0x18000c55e`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorControl` at `0x18000c55e`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorSacl` at `0x18000c525`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorSacl` at `0x18000c525`

## pseudocode

```c
void __fastcall ProtectACLs(int a1, void *a2)
{
  char v3; // di
  __int16 v4; // cx
  int AceCount; // edx
  PACL v6; // rcx
  int v7; // r8d
  PACL v8; // rcx
  DWORD dwRevision; // [rsp+20h] [rbp-10h] BYREF
  PACL pDacl; // [rsp+28h] [rbp-8h] BYREF
  WORD pControl; // [rsp+50h] [rbp+20h] BYREF
  WINBOOL bDaclDefaulted; // [rsp+60h] [rbp+30h] BYREF
  WINBOOL bDaclPresent; // [rsp+68h] [rbp+38h] BYREF

  pControl = 0;
  v3 = a1;
  dwRevision = 0;
  pDacl = 0;
  bDaclDefaulted = 0;
  bDaclPresent = 0;
  if ( a1 && a2 )
  {
    GetSecurityDescriptorControl(a2, &pControl, &dwRevision);
    v4 = pControl & 0x3000;
    pControl &= 0x3000u;
    if ( (v3 & 4) != 0 && (v4 & 0x1000) == 0 )
    {
      pDacl = 0;
      pControl = v4 | 0x1000;
      GetSecurityDescriptorDacl(a2, &bDaclPresent, &pDacl, &bDaclDefaulted);
      if ( pDacl )
      {
        AceCount = pDacl->AceCount;
        v6 = pDacl + 1;
        if ( pDacl->AceCount )
        {
          do
          {
            v6->Sbz1 &= ~0x10u;
            v6 = (PACL)((char *)v6 + v6->AclSize);
            --AceCount;
          }
          while ( AceCount );
        }
      }
    }
    if ( (v3 & 8) != 0 && (pControl & 0x2000) == 0 )
    {
      pControl |= 0x2000u;
      pDacl = 0;
      GetSecurityDescriptorSacl(a2, &bDaclPresent, &pDacl, &bDaclDefaulted);
      if ( pDacl )
      {
        v7 = pDacl->AceCount;
        v8 = pDacl + 1;
        if ( pDacl->AceCount )
        {
          do
          {
            v8->Sbz1 &= ~0x10u;
            v8 = (PACL)((char *)v8 + v8->AclSize);
            --v7;
          }
          while ( v7 );
        }
      }
    }
    SetSecurityDescriptorControl(a2, 0x3000u, pControl);
  }
}

```

## disassembly

```asm
0x18000c444  mov     [rsp-18h+arg_8], rbx
0x18000c449  push    rbp
0x18000c44a  push    rdi
0x18000c44b  push    r15
0x18000c44d  mov     rbp, rsp
0x18000c450  sub     rsp, 30h
0x18000c454  xor     eax, eax
0x18000c456  mov     rbx, rdx
0x18000c459  mov     [rbp+pControl], ax
0x18000c45d  mov     edi, ecx
0x18000c45f  mov     [rbp+dwRevision], eax
0x18000c462  mov     [rbp+pDacl], rax
0x18000c466  mov     [rbp+bDaclDefaulted], eax
0x18000c469  mov     [rbp+bDaclPresent], eax
0x18000c46c  test    ecx, ecx
0x18000c46e  jz      loc_18000C564
0x18000c474  test    rdx, rdx
0x18000c477  jz      loc_18000C564
0x18000c47d  lea     r8, [rbp+dwRevision]; lpdwRevision
0x18000c481  mov     rcx, rbx; pSecurityDescriptor
0x18000c484  lea     rdx, [rbp+pControl]; pControl
0x18000c488  call    cs:__imp_GetSecurityDescriptorControl
0x18000c48e  movzx   ecx, [rbp+pControl]
0x18000c492  mov     r15d, 3000h
0x18000c498  and     cx, r15w
0x18000c49c  mov     [rbp+pControl], cx
0x18000c4a0  test    dil, 4
0x18000c4a4  jz      short loc_18000C4F9
0x18000c4a6  mov     eax, 1000h
0x18000c4ab  test    ax, cx
0x18000c4ae  jnz     short loc_18000C4F9
0x18000c4b0  or      cx, ax
0x18000c4b3  mov     [rbp+pDacl], 0
0x18000c4bb  mov     [rbp+pControl], cx
0x18000c4bf  lea     r9, [rbp+bDaclDefaulted]; lpbDaclDefaulted
0x18000c4c3  mov     rcx, rbx; pSecurityDescriptor
0x18000c4c6  lea     r8, [rbp+pDacl]; pDacl
0x18000c4ca  lea     rdx, [rbp+bDaclPresent]; lpbDaclPresent
0x18000c4ce  call    cs:__imp_GetSecurityDescriptorDacl
0x18000c4d4  mov     rax, [rbp+pDacl]
0x18000c4d8  test    rax, rax
0x18000c4db  jz      short loc_18000C4F9
0x18000c4dd  movzx   edx, word ptr [rax+4]
0x18000c4e1  lea     rcx, [rax+8]
0x18000c4e5  test    edx, edx
0x18000c4e7  jz      short loc_18000C4F9
0x18000c4e9  and     byte ptr [rcx+1], 0EFh
0x18000c4ed  movzx   eax, word ptr [rcx+2]
0x18000c4f1  add     rcx, rax
0x18000c4f4  add     edx, 0FFFFFFFFh
0x18000c4f7  jnz     short loc_18000C4E9
0x18000c4f9  test    dil, 8
0x18000c4fd  jz      short loc_18000C553
0x18000c4ff  mov     eax, 2000h
0x18000c504  test    [rbp+pControl], ax
0x18000c508  jnz     short loc_18000C553
0x18000c50a  or      [rbp+pControl], ax
0x18000c50e  lea     r9, [rbp+bDaclDefaulted]; lpbSaclDefaulted
0x18000c512  lea     r8, [rbp+pDacl]; pSacl
0x18000c516  mov     [rbp+pDacl], 0
0x18000c51e  lea     rdx, [rbp+bDaclPresent]; lpbSaclPresent
0x18000c522  mov     rcx, rbx; pSecurityDescriptor
0x18000c525  call    cs:__imp_GetSecurityDescriptorSacl
0x18000c52b  mov     rax, [rbp+pDacl]
0x18000c52f  test    rax, rax
0x18000c532  jz      short loc_18000C553
0x18000c534  movzx   r8d, word ptr [rax+4]
0x18000c539  lea     rcx, [rax+8]
0x18000c53d  test    r8d, r8d
0x18000c540  jz      short loc_18000C553
0x18000c542  and     byte ptr [rcx+1], 0EFh
0x18000c546  movzx   eax, word ptr [rcx+2]
0x18000c54a  add     rcx, rax
0x18000c54d  add     r8d, 0FFFFFFFFh
0x18000c551  jnz     short loc_18000C542
0x18000c553  movzx   r8d, [rbp+pControl]; ControlBitsToSet
0x18000c558  mov     edx, r15d; ControlBitsOfInterest
0x18000c55b  mov     rcx, rbx; pSecurityDescriptor
0x18000c55e  call    cs:__imp_SetSecurityDescriptorControl
0x18000c564  mov     rbx, [rsp+30h+arg_8]
0x18000c569  add     rsp, 30h
0x18000c56d  pop     r15
0x18000c56f  pop     rdi
0x18000c570  pop     rbp
0x18000c571  retn
```
