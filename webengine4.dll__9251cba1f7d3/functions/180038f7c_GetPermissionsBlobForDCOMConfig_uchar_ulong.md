# GetPermissionsBlobForDCOMConfig(uchar * *,ulong *)

- ea: `0x180038f7c`
- end: `0x180039119`
- name: `?GetPermissionsBlobForDCOMConfig@@YAJPEAPEAEPEAK@Z`
- size: `413`
- prototype: `int(unsigned __int8 **, unsigned int *)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18003d858`

## callees

- `0x180038f7c`
- `0x18004d350`
- `0x18004d690`
- `0x18004d754`
- `0x18004eaa8`

## import_xrefs

- `KERNEL32!LocalFree` at `0x1800390eb`
- `KERNEL32!LocalFree` at `0x1800390eb`
- `ADVAPI32!InitializeSecurityDescriptor` at `0x180039034`
- `ADVAPI32!InitializeSecurityDescriptor` at `0x180039034`
- `ADVAPI32!SetSecurityDescriptorDacl` at `0x180039058`
- `ADVAPI32!SetSecurityDescriptorDacl` at `0x180039058`
- `ADVAPI32!MakeSelfRelativeSD` at `0x180039097`
- `ADVAPI32!MakeSelfRelativeSD` at `0x1800390c1`
- `ADVAPI32!MakeSelfRelativeSD` at `0x180039097`
- `ADVAPI32!MakeSelfRelativeSD` at `0x1800390c1`
- `ADVAPI32!SetEntriesInAclW` at `0x180039010`
- `ADVAPI32!SetEntriesInAclW` at `0x180039010`
- `ADVAPI32!SetSecurityDescriptorGroup` at `0x180039082`
- `ADVAPI32!SetSecurityDescriptorGroup` at `0x180039082`
- `ADVAPI32!SetSecurityDescriptorOwner` at `0x18003906d`
- `ADVAPI32!SetSecurityDescriptorOwner` at `0x18003906d`

## pseudocode

```c
__int64 __fastcall GetPermissionsBlobForDCOMConfig(unsigned __int8 **a1, unsigned int *a2)
{
  unsigned __int8 *v4; // rdi
  unsigned int PrincipalSID; // ebx
  signed int v6; // eax
  unsigned __int8 *v7; // rax
  _BYTE pSecurityDescriptor[40]; // [rsp+20h] [rbp-60h] BYREF
  struct _EXPLICIT_ACCESS_W pListOfExplicitEntries; // [rsp+48h] [rbp-38h] BYREF
  PSID pOwner; // [rsp+B0h] [rbp+30h] BYREF
  PACL NewAcl; // [rsp+C0h] [rbp+40h] BYREF

  if ( !a1 || !a2 )
    return 2147942487LL;
  NewAcl = 0;
  pOwner = 0;
  v4 = 0;
  PrincipalSID = GetPrincipalSID((char *)L"administrators", &pOwner);
  if ( !PrincipalSID )
  {
    memset(&pListOfExplicitEntries.grfInheritance + 1, 0, 20);
    *((_DWORD *)&pListOfExplicitEntries.Trustee.TrusteeType + 1) = 0;
    pListOfExplicitEntries.grfAccessPermissions = 1;
    pListOfExplicitEntries.grfAccessMode = GRANT_ACCESS;
    pListOfExplicitEntries.grfInheritance = 3;
    pListOfExplicitEntries.Trustee.TrusteeType = TRUSTEE_IS_GROUP;
    pListOfExplicitEntries.Trustee.ptstrName = (LPWCH)pOwner;
    v6 = SetEntriesInAclW(1u, &pListOfExplicitEntries, 0, &NewAcl);
    if ( v6 )
    {
      PrincipalSID = (unsigned __int16)v6 | 0x80070000;
      if ( v6 <= 0 )
        PrincipalSID = v6;
      goto LABEL_18;
    }
    if ( InitializeSecurityDescriptor(pSecurityDescriptor, 1u) )
    {
      if ( SetSecurityDescriptorDacl(pSecurityDescriptor, 1, NewAcl, 0) )
      {
        if ( SetSecurityDescriptorOwner(pSecurityDescriptor, pOwner, 0) )
        {
          if ( SetSecurityDescriptorGroup(pSecurityDescriptor, pOwner, 0) )
          {
            *a2 = 0;
            MakeSelfRelativeSD(pSecurityDescriptor, 0, a2);
            if ( *a2 )
            {
              v7 = (unsigned __int8 *)MemAlloc(*a2);
              v4 = v7;
              if ( !v7 )
              {
                PrincipalSID = -2147024882;
                goto LABEL_18;
              }
              if ( MakeSelfRelativeSD(pSecurityDescriptor, v7, a2) )
              {
                *a1 = v4;
                v4 = 0;
                goto LABEL_18;
              }
            }
          }
        }
      }
    }
    PrincipalSID = GetLastWin32Error();
  }
LABEL_18:
  if ( pOwner )
    MemFree(pOwner);
  if ( NewAcl )
    LocalFree(NewAcl);
  MemFree(v4);
  return PrincipalSID;
}

```

## disassembly

```asm
0x180038f7c  mov     [rsp-28h+arg_8], rbx
0x180038f81  push    rbp
0x180038f82  push    rsi
0x180038f83  push    rdi
0x180038f84  push    r12
0x180038f86  push    r14
0x180038f88  mov     rbp, rsp
0x180038f8b  sub     rsp, 80h
0x180038f92  mov     rsi, rdx
0x180038f95  mov     r14, rcx
0x180038f98  test    rcx, rcx
0x180038f9b  jz      loc_1800390FD
0x180038fa1  test    rdx, rdx
0x180038fa4  jz      loc_1800390FD
0x180038faa  and     [rbp+NewAcl], 0
0x180038faf  lea     rdx, [rbp+pOwner]; void **
0x180038fb3  and     [rbp+pOwner], 0
0x180038fb8  lea     rcx, aAdministrators; "administrators"
0x180038fbf  xor     edi, edi
0x180038fc1  call    ?GetPrincipalSID@@YAJPEBGPEAPEAX@Z; GetPrincipalSID(ushort const *,void * *)
0x180038fc6  mov     ebx, eax
0x180038fc8  test    eax, eax
0x180038fca  jnz     loc_1800390D4
0x180038fd0  mov     rax, [rbp+pOwner]
0x180038fd4  lea     r12d, [rdi+1]
0x180038fd8  and     dword ptr [rbp+pListOfExplicitEntries+0Ch], edi
0x180038fdb  lea     r9, [rbp+NewAcl]; NewAcl
0x180038fdf  and     dword ptr [rbp+pListOfExplicitEntries.Trustee+14h], edi
0x180038fe2  lea     rdx, [rbp+pListOfExplicitEntries]; pListOfExplicitEntries
0x180038fe6  and     [rbp+pListOfExplicitEntries.Trustee.pMultipleTrustee], rdi
0x180038fea  mov     ecx, r12d; cCountOfExplicitEntries
0x180038fed  and     [rbp+pListOfExplicitEntries.Trustee.MultipleTrusteeOperation], edi
0x180038ff0  xor     r8d, r8d; OldAcl
0x180038ff3  and     [rbp+pListOfExplicitEntries.Trustee.TrusteeForm], edi
0x180038ff6  mov     [rbp+pListOfExplicitEntries.grfAccessPermissions], r12d
0x180038ffa  mov     [rbp+pListOfExplicitEntries.grfAccessMode], r12d
0x180038ffe  mov     [rbp+pListOfExplicitEntries.grfInheritance], 3
0x180039005  mov     [rbp+pListOfExplicitEntries.Trustee.TrusteeType], 2
0x18003900c  mov     [rbp+pListOfExplicitEntries.Trustee.ptstrName], rax
0x180039010  call    cs:__imp_SetEntriesInAclW
0x180039016  test    eax, eax
0x180039018  jz      short loc_18003902D
0x18003901a  movzx   ebx, ax
0x18003901d  or      ebx, 80070000h
0x180039023  test    eax, eax
0x180039025  cmovle  ebx, eax
0x180039028  jmp     loc_1800390D4
0x18003902d  mov     edx, r12d; dwRevision
0x180039030  lea     rcx, [rbp+pSecurityDescriptor]; pSecurityDescriptor
0x180039034  call    cs:__imp_InitializeSecurityDescriptor
0x18003903a  test    eax, eax
0x18003903c  jnz     short loc_18003904A
0x18003903e  call    ?GetLastWin32Error@@YAJXZ; GetLastWin32Error(void)
0x180039043  mov     ebx, eax
0x180039045  jmp     loc_1800390D4
0x18003904a  mov     r8, [rbp+NewAcl]; pDacl
0x18003904e  lea     rcx, [rbp+pSecurityDescriptor]; pSecurityDescriptor
0x180039052  xor     r9d, r9d; bDaclDefaulted
0x180039055  mov     edx, r12d; bDaclPresent
0x180039058  call    cs:__imp_SetSecurityDescriptorDacl
0x18003905e  test    eax, eax
0x180039060  jz      short loc_18003903E
0x180039062  mov     rdx, [rbp+pOwner]; pOwner
0x180039066  lea     rcx, [rbp+pSecurityDescriptor]; pSecurityDescriptor
0x18003906a  xor     r8d, r8d; bOwnerDefaulted
0x18003906d  call    cs:__imp_SetSecurityDescriptorOwner
0x180039073  test    eax, eax
0x180039075  jz      short loc_18003903E
0x180039077  mov     rdx, [rbp+pOwner]; pGroup
0x18003907b  lea     rcx, [rbp+pSecurityDescriptor]; pSecurityDescriptor
0x18003907f  xor     r8d, r8d; bGroupDefaulted
0x180039082  call    cs:__imp_SetSecurityDescriptorGroup
0x180039088  test    eax, eax
0x18003908a  jz      short loc_18003903E
0x18003908c  and     [rsi], edi
0x18003908e  lea     rcx, [rbp+pSecurityDescriptor]; pAbsoluteSecurityDescriptor
0x180039092  mov     r8, rsi; lpdwBufferLength
0x180039095  xor     edx, edx; pSelfRelativeSecurityDescriptor
0x180039097  call    cs:__imp_MakeSelfRelativeSD
0x18003909d  cmp     [rsi], edi
0x18003909f  jz      short loc_18003903E
0x1800390a1  mov     ecx, [rsi]; unsigned __int64
0x1800390a3  call    ?MemAlloc@@YAPEAX_K@Z; MemAlloc(unsigned __int64)
0x1800390a8  mov     rdi, rax
0x1800390ab  test    rax, rax
0x1800390ae  jnz     short loc_1800390B7
0x1800390b0  mov     ebx, 8007000Eh
0x1800390b5  jmp     short loc_1800390D4
0x1800390b7  mov     r8, rsi; lpdwBufferLength
0x1800390ba  lea     rcx, [rbp+pSecurityDescriptor]; pAbsoluteSecurityDescriptor
0x1800390be  mov     rdx, rdi; pSelfRelativeSecurityDescriptor
0x1800390c1  call    cs:__imp_MakeSelfRelativeSD
0x1800390c7  test    eax, eax
0x1800390c9  jz      loc_18003903E
0x1800390cf  mov     [r14], rdi
0x1800390d2  xor     edi, edi
0x1800390d4  mov     rcx, [rbp+pOwner]; lpMem
0x1800390d8  test    rcx, rcx
0x1800390db  jz      short loc_1800390E2
0x1800390dd  call    ?MemFree@@YAXPEAX@Z; MemFree(void *)
0x1800390e2  mov     rcx, [rbp+NewAcl]; hMem
0x1800390e6  test    rcx, rcx
0x1800390e9  jz      short loc_1800390F1
0x1800390eb  call    cs:__imp_LocalFree
0x1800390f1  mov     rcx, rdi; lpMem
0x1800390f4  call    ?MemFree@@YAXPEAX@Z; MemFree(void *)
0x1800390f9  mov     eax, ebx
0x1800390fb  jmp     short loc_180039102
0x1800390fd  mov     eax, 80070057h
0x180039102  mov     rbx, [rsp+80h+arg_8]
0x18003910a  add     rsp, 80h
0x180039111  pop     r14
0x180039113  pop     r12
0x180039115  pop     rdi
0x180039116  pop     rsi
0x180039117  pop     rbp
0x180039118  retn
```
