# SBESecurityHelpers::CopyACL(_ACL *,_ACL *,ulong *)

- ea: `0x18005f468`
- end: `0x18005f591`
- name: `?CopyACL@SBESecurityHelpers@@SAKPEAU_ACL@@0PEAK@Z`
- size: `297`
- prototype: `unsigned int __fastcall(PACL pAcl, PACL, unsigned int *)`
- caller_count: `2`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18005f598`
- `0x18005fa18`

## callees

- `0x180001c00`
- `0x18005f468`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18005f4b8`
- `KERNEL32!GetLastError` at `0x18005f4b8`
- `ADVAPI32!InitializeAcl` at `0x18005f4ec`
- `ADVAPI32!InitializeAcl` at `0x18005f589`
- `ADVAPI32!InitializeAcl` at `0x18005f4ec`
- `ADVAPI32!InitializeAcl` at `0x18005f589`
- `ADVAPI32!AddAce` at `0x18005f523`
- `ADVAPI32!AddAce` at `0x18005f523`
- `ADVAPI32!GetAce` at `0x18005f500`
- `ADVAPI32!GetAce` at `0x18005f500`
- `ADVAPI32!GetAclInformation` at `0x18005f4ae`
- `ADVAPI32!GetAclInformation` at `0x18005f53f`
- `ADVAPI32!GetAclInformation` at `0x18005f4ae`
- `ADVAPI32!GetAclInformation` at `0x18005f53f`

## pseudocode

```c
__int64 __fastcall SBESecurityHelpers::CopyACL(PACL pAcl, PACL a2, unsigned int *a3)
{
  unsigned int v6; // ecx
  unsigned int v7; // eax
  BOOL v8; // eax
  LPVOID pAce; // [rsp+30h] [rbp-38h] BYREF
  __int64 pAclInformation; // [rsp+38h] [rbp-30h] BYREF
  int v12; // [rsp+40h] [rbp-28h]

  pAclInformation = 0;
  v12 = 0;
  pAce = 0;
  if ( !pAcl )
  {
    if ( !a2 && a3 )
    {
      v6 = 8;
      *a3 = 8;
      return v6;
    }
    v8 = InitializeAcl(a2, *a3, 4u);
    goto LABEL_12;
  }
  if ( GetAclInformation(pAcl, &pAclInformation, 0xCu, AclSizeInformation) )
  {
    if ( !a2 && a3 )
    {
      v6 = 8;
LABEL_15:
      v7 = HIDWORD(pAclInformation);
      goto LABEL_16;
    }
    v7 = HIDWORD(pAclInformation);
    if ( HIDWORD(pAclInformation) > *a3 )
    {
      v6 = 8;
LABEL_16:
      *a3 = v7;
      return v6;
    }
    if ( !InitializeAcl(a2, *a3, pAcl->AclRevision) || !GetAce(pAcl, 0, &pAce) )
      return GetLastError();
    v8 = AddAce(a2, a2->AclRevision, 0, pAce, HIDWORD(pAclInformation) - 8);
LABEL_12:
    if ( !v8 || !GetAclInformation(pAcl, &pAclInformation, 0xCu, AclSizeInformation) )
      return GetLastError();
    v6 = 0;
    goto LABEL_15;
  }
  return GetLastError();
}

```

## disassembly

```asm
0x18005f468  push    rbx
0x18005f46a  push    rsi
0x18005f46b  push    rdi
0x18005f46c  sub     rsp, 50h
0x18005f470  mov     rax, cs:__security_cookie
0x18005f477  xor     rax, rsp
0x18005f47a  mov     [rsp+68h+var_20], rax
0x18005f47f  xor     eax, eax
0x18005f481  mov     rbx, r8
0x18005f484  mov     [rsp+68h+pAclInformation], rax
0x18005f489  mov     rdi, rdx
0x18005f48c  mov     [rsp+68h+var_28], eax
0x18005f490  mov     rsi, rcx
0x18005f493  mov     [rsp+68h+pAce], rax
0x18005f498  test    rcx, rcx
0x18005f49b  jz      loc_18005F56C
0x18005f4a1  lea     r9d, [rax+2]; dwAclInformationClass
0x18005f4a5  lea     r8d, [rax+0Ch]; nAclInformationLength
0x18005f4a9  lea     rdx, [rsp+68h+pAclInformation]; pAclInformation
0x18005f4ae  call    cs:__imp_GetAclInformation
0x18005f4b4  test    eax, eax
0x18005f4b6  jnz     short loc_18005F4C5
0x18005f4b8  call    cs:__imp_GetLastError
0x18005f4be  mov     ecx, eax
0x18005f4c0  jmp     loc_18005F555
0x18005f4c5  test    rdi, rdi
0x18005f4c8  jnz     short loc_18005F4D4
0x18005f4ca  test    rbx, rbx
0x18005f4cd  jz      short loc_18005F4D4
0x18005f4cf  lea     ecx, [rdi+8]
0x18005f4d2  jmp     short loc_18005F54F
0x18005f4d4  mov     eax, dword ptr [rsp+68h+pAclInformation+4]
0x18005f4d8  cmp     eax, [rbx]
0x18005f4da  jbe     short loc_18005F4E3
0x18005f4dc  mov     ecx, 8
0x18005f4e1  jmp     short loc_18005F553
0x18005f4e3  movzx   r8d, byte ptr [rsi]; dwAclRevision
0x18005f4e7  mov     rcx, rdi; pAcl
0x18005f4ea  mov     edx, [rbx]; nAclLength
0x18005f4ec  call    cs:__imp_InitializeAcl
0x18005f4f2  test    eax, eax
0x18005f4f4  jz      short loc_18005F4B8
0x18005f4f6  lea     r8, [rsp+68h+pAce]; pAce
0x18005f4fb  xor     edx, edx; dwAceIndex
0x18005f4fd  mov     rcx, rsi; pAcl
0x18005f500  call    cs:__imp_GetAce
0x18005f506  test    eax, eax
0x18005f508  jz      short loc_18005F4B8
0x18005f50a  mov     eax, dword ptr [rsp+68h+pAclInformation+4]
0x18005f50e  xor     r8d, r8d; dwStartingAceIndex
0x18005f511  movzx   edx, byte ptr [rdi]; dwAceRevision
0x18005f514  add     eax, 0FFFFFFF8h
0x18005f517  mov     r9, [rsp+68h+pAce]; pAceList
0x18005f51c  mov     rcx, rdi; pAcl
0x18005f51f  mov     [rsp+68h+nAceListLength], eax; nAceListLength
0x18005f523  call    cs:__imp_AddAce
0x18005f529  test    eax, eax
0x18005f52b  jz      short loc_18005F4B8
0x18005f52d  mov     r9d, 2; dwAclInformationClass
0x18005f533  lea     rdx, [rsp+68h+pAclInformation]; pAclInformation
0x18005f538  mov     rcx, rsi; pAcl
0x18005f53b  lea     r8d, [r9+0Ah]; nAclInformationLength
0x18005f53f  call    cs:__imp_GetAclInformation
0x18005f545  test    eax, eax
0x18005f547  jz      loc_18005F4B8
0x18005f54d  xor     ecx, ecx
0x18005f54f  mov     eax, dword ptr [rsp+68h+pAclInformation+4]
0x18005f553  mov     [rbx], eax
0x18005f555  mov     eax, ecx
0x18005f557  mov     rcx, [rsp+68h+var_20]
0x18005f55c  xor     rcx, rsp; StackCookie
0x18005f55f  call    __security_check_cookie
0x18005f564  add     rsp, 50h
0x18005f568  pop     rdi
0x18005f569  pop     rsi
0x18005f56a  pop     rbx
0x18005f56b  retn
0x18005f56c  test    rdi, rdi
0x18005f56f  jnz     short loc_18005F57E
0x18005f571  test    rbx, rbx
0x18005f574  jz      short loc_18005F57E
0x18005f576  lea     ecx, [rdi+8]
0x18005f579  mov     [r8], ecx
0x18005f57c  jmp     short loc_18005F555
0x18005f57e  mov     edx, [rbx]; nAclLength
0x18005f580  mov     r8d, 4; dwAclRevision
0x18005f586  mov     rcx, rdi; pAcl
0x18005f589  call    cs:__imp_InitializeAcl
0x18005f58f  jmp     short loc_18005F529
```
