# CSecurityDescriptor::AddAccessAllowedACEToACL(_ACL * *,CSecurityDescriptor::SecurityId const *,ulong)

- ea: `0x18002e998`
- end: `0x18002eb29`
- name: `?AddAccessAllowedACEToACL@CSecurityDescriptor@@SAJPEAPEAU_ACL@@PEBUSecurityId@1@K@Z`
- size: `401`
- prototype: `static int(struct _ACL **, const struct CSecurityDescriptor::SecurityId *, unsigned int)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x18002eb30`

## callees

- `0x18001b9b8`
- `0x18001ba04`
- `0x18001be10`
- `0x18002e998`
- `0x18002eb98`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!InitializeSid` at `0x18002e9f9`
- `api-ms-win-security-base-l1-1-0!InitializeSid` at `0x18002e9f9`
- `api-ms-win-security-base-l1-1-0!AddAccessAllowedAce` at `0x18002eae2`
- `api-ms-win-security-base-l1-1-0!AddAccessAllowedAce` at `0x18002eae2`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18002ea7d`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18002ea7d`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x18002ea48`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x18002ea48`
- `api-ms-win-security-base-l1-1-0!InitializeAcl` at `0x18002eaab`
- `api-ms-win-security-base-l1-1-0!InitializeAcl` at `0x18002eaab`
- `api-ms-win-security-base-l1-1-0!GetSidLengthRequired` at `0x18002e9d0`
- `api-ms-win-security-base-l1-1-0!GetSidLengthRequired` at `0x18002e9d0`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthority` at `0x18002ea36`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthority` at `0x18002ea36`
- `api-ms-win-security-base-l1-1-0!GetAclInformation` at `0x18002ea74`
- `api-ms-win-security-base-l1-1-0!GetAclInformation` at `0x18002ea74`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002ea0b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002ea0b`

## pseudocode

```c
int __fastcall CSecurityDescriptor::AddAccessAllowedACEToACL(
        struct _ACL **a1,
        struct _SID_IDENTIFIER_AUTHORITY *a2,
        DWORD a3)
{
  struct _ACL *v3; // r14
  UCHAR v5; // cl
  DWORD SidLengthRequired; // eax
  void *v9; // rax
  void *v10; // rdi
  int result; // eax
  unsigned __int64 v12; // rdx
  __int64 i; // rbp
  DWORD v14; // ebx
  PDWORD SidSubAuthority; // rax
  bool v16; // zf
  DWORD LengthSid; // eax
  signed int v18; // ebx
  struct _ACL *v19; // rax
  unsigned __int64 v20; // rdx
  struct _ACL *v21; // rsi
  int v22; // ebx
  BOOL v23; // eax
  struct _ACL *v24; // rcx
  unsigned __int64 v25; // rdx
  __int64 pAclInformation; // [rsp+20h] [rbp-58h] BYREF
  int v27; // [rsp+28h] [rbp-50h]

  v3 = *a1;
  pAclInformation = 0;
  v5 = a2[1].Value[2];
  v27 = 0;
  SidLengthRequired = GetSidLengthRequired(v5);
  v9 = operator new[](SidLengthRequired);
  v10 = v9;
  if ( !v9 )
    return -2147024882;
  if ( InitializeSid(v9, a2, a2[1].Value[2]) )
  {
    for ( i = 0; (unsigned int)i < *(_DWORD *)&a2[1].Value[2]; *SidSubAuthority = v14 )
    {
      v14 = *(_DWORD *)&a2[2].Value[4 * i];
      SidSubAuthority = GetSidSubAuthority(v10, i);
      i = (unsigned int)(i + 1);
    }
    if ( IsValidSid(v10) )
    {
      v16 = *a1 == 0;
      HIDWORD(pAclInformation) = 0;
      if ( !v16 )
        GetAclInformation(v3, &pAclInformation, 0xCu, AclSizeInformation);
      LengthSid = GetLengthSid(v10);
      v18 = LengthSid + HIDWORD(pAclInformation) + 16;
      v19 = (struct _ACL *)operator new[](v18);
      v21 = v19;
      if ( !v19 )
      {
        v22 = -2147024882;
LABEL_22:
        operator delete(v10, v20);
        return v22;
      }
      v23 = InitializeAcl(v19, v18, 2u);
      v24 = v21;
      if ( v23 )
      {
        v22 = CSecurityDescriptor::CopyACL(v21, v3);
        if ( v22 < 0 )
        {
          operator delete(v21, v25);
          goto LABEL_22;
        }
        if ( AddAccessAllowedAce(v21, 2u, a3, v10) )
        {
          *a1 = v21;
          if ( v3 )
            operator delete(v3, v20);
          v22 = 0;
          goto LABEL_22;
        }
        v24 = v21;
      }
      operator delete(v24, v20);
    }
  }
  operator delete(v10, v12);
  result = GetLastError();
  if ( result > 0 )
    return (unsigned __int16)result | 0x80070000;
  return result;
}

```

## disassembly

```asm
0x18002e998  push    rbx
0x18002e99a  push    rbp
0x18002e99b  push    rsi
0x18002e99c  push    rdi
0x18002e99d  push    r12
0x18002e99f  push    r14
0x18002e9a1  push    r15
0x18002e9a3  sub     rsp, 40h
0x18002e9a7  mov     rax, cs:__security_cookie
0x18002e9ae  xor     rax, rsp
0x18002e9b1  mov     [rsp+78h+var_48], rax
0x18002e9b6  mov     r14, [rcx]
0x18002e9b9  xor     eax, eax
0x18002e9bb  mov     r15, rcx
0x18002e9be  mov     [rsp+78h+pAclInformation], rax
0x18002e9c3  mov     cl, [rdx+8]; nSubAuthorityCount
0x18002e9c6  mov     r12d, r8d
0x18002e9c9  mov     [rsp+78h+var_50], eax
0x18002e9cd  mov     rsi, rdx
0x18002e9d0  call    cs:__imp_GetSidLengthRequired
0x18002e9d6  mov     ecx, eax; unsigned __int64
0x18002e9d8  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x18002e9dd  mov     rdi, rax
0x18002e9e0  test    rax, rax
0x18002e9e3  jnz     short loc_18002E9EF
0x18002e9e5  mov     eax, 8007000Eh
0x18002e9ea  jmp     loc_18002EB0D
0x18002e9ef  mov     r8b, [rsi+8]; nSubAuthorityCount
0x18002e9f3  mov     rdx, rsi; pIdentifierAuthority
0x18002e9f6  mov     rcx, rdi; Sid
0x18002e9f9  call    cs:__imp_InitializeSid
0x18002e9ff  test    eax, eax
0x18002ea01  jnz     short loc_18002EA26
0x18002ea03  mov     rcx, rdi; void *
0x18002ea06  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18002ea0b  call    cs:__imp_GetLastError
0x18002ea11  test    eax, eax
0x18002ea13  jle     loc_18002EB0D
0x18002ea19  movzx   eax, ax
0x18002ea1c  or      eax, 80070000h
0x18002ea21  jmp     loc_18002EB0D
0x18002ea26  xor     ebp, ebp
0x18002ea28  cmp     [rsi+8], ebp
0x18002ea2b  jbe     short loc_18002EA45
0x18002ea2d  mov     ebx, [rsi+rbp*4+0Ch]
0x18002ea31  mov     edx, ebp; nSubAuthority
0x18002ea33  mov     rcx, rdi; pSid
0x18002ea36  call    cs:__imp_GetSidSubAuthority
0x18002ea3c  inc     ebp
0x18002ea3e  mov     [rax], ebx
0x18002ea40  cmp     ebp, [rsi+8]
0x18002ea43  jb      short loc_18002EA2D
0x18002ea45  mov     rcx, rdi; pSid
0x18002ea48  call    cs:__imp_IsValidSid
0x18002ea4e  test    eax, eax
0x18002ea50  jz      short loc_18002EA03
0x18002ea52  cmp     qword ptr [r15], 0
0x18002ea56  mov     ebp, 2
0x18002ea5b  mov     dword ptr [rsp+78h+pAclInformation+4], 0
0x18002ea63  jz      short loc_18002EA7A
0x18002ea65  mov     r9d, ebp; dwAclInformationClass
0x18002ea68  lea     r8d, [rbp+0Ah]; nAclInformationLength
0x18002ea6c  lea     rdx, [rsp+78h+pAclInformation]; pAclInformation
0x18002ea71  mov     rcx, r14; pAcl
0x18002ea74  call    cs:__imp_GetAclInformation
0x18002ea7a  mov     rcx, rdi; pSid
0x18002ea7d  call    cs:__imp_GetLengthSid
0x18002ea83  mov     ebx, dword ptr [rsp+78h+pAclInformation+4]
0x18002ea87  add     ebx, 10h
0x18002ea8a  add     ebx, eax
0x18002ea8c  movsxd  rcx, ebx; unsigned __int64
0x18002ea8f  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x18002ea94  mov     rsi, rax
0x18002ea97  test    rax, rax
0x18002ea9a  jnz     short loc_18002EAA3
0x18002ea9c  mov     ebx, 8007000Eh
0x18002eaa1  jmp     short loc_18002EB03
0x18002eaa3  mov     r8d, ebp; dwAclRevision
0x18002eaa6  mov     edx, ebx; nAclLength
0x18002eaa8  mov     rcx, rsi; pAcl
0x18002eaab  call    cs:__imp_InitializeAcl
0x18002eab1  mov     rcx, rsi; pAcl
0x18002eab4  test    eax, eax
0x18002eab6  jnz     short loc_18002EAC2
0x18002eab8  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18002eabd  jmp     loc_18002EA03
0x18002eac2  mov     rdx, r14; PACL
0x18002eac5  call    ?CopyACL@CSecurityDescriptor@@SAJPEAU_ACL@@0@Z; CSecurityDescriptor::CopyACL(_ACL *,_ACL *)
0x18002eaca  mov     ebx, eax
0x18002eacc  mov     rcx, rsi; void *
0x18002eacf  test    eax, eax
0x18002ead1  jns     short loc_18002EADA
0x18002ead3  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18002ead8  jmp     short loc_18002EB03
0x18002eada  mov     r9, rdi; pSid
0x18002eadd  mov     r8d, r12d; AccessMask
0x18002eae0  mov     edx, ebp; dwAceRevision
0x18002eae2  call    cs:__imp_AddAccessAllowedAce
0x18002eae8  test    eax, eax
0x18002eaea  jnz     short loc_18002EAF1
0x18002eaec  mov     rcx, rsi
0x18002eaef  jmp     short loc_18002EAB8
0x18002eaf1  mov     [r15], rsi
0x18002eaf4  test    r14, r14
0x18002eaf7  jz      short loc_18002EB01
0x18002eaf9  mov     rcx, r14; void *
0x18002eafc  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18002eb01  xor     ebx, ebx
0x18002eb03  mov     rcx, rdi; void *
0x18002eb06  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18002eb0b  mov     eax, ebx
0x18002eb0d  mov     rcx, [rsp+78h+var_48]
0x18002eb12  xor     rcx, rsp; StackCookie
0x18002eb15  call    __security_check_cookie
0x18002eb1a  add     rsp, 40h
0x18002eb1e  pop     r15
0x18002eb20  pop     r14
0x18002eb22  pop     r12
0x18002eb24  pop     rdi
0x18002eb25  pop     rsi
0x18002eb26  pop     rbp
0x18002eb27  pop     rbx
0x18002eb28  retn
```
