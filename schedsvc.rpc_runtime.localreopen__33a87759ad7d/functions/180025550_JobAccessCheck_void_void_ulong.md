# JobAccessCheck(void *,void *,ulong)

- ea: `0x180025550`
- end: `0x1800256c7`
- name: `?JobAccessCheck@@YAJPEAX0K@Z`
- size: `375`
- prototype: `__int64 __fastcall(HANDLE ClientToken, PSECURITY_DESCRIPTOR pSecurityDescriptor, DWORD DesiredAccess)`
- caller_count: `5`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180024ce0`
- `0x18002506c`
- `0x180029978`
- `0x180045df0`
- `0x18004d868`

## callees

- `0x180025550`
- `0x18007e6d0`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!PrivilegeCheck` at `0x1800255c7`
- `api-ms-win-security-base-l1-1-0!PrivilegeCheck` at `0x1800256a8`
- `api-ms-win-security-base-l1-1-0!PrivilegeCheck` at `0x1800255c7`
- `api-ms-win-security-base-l1-1-0!PrivilegeCheck` at `0x1800256a8`
- `api-ms-win-security-base-l1-1-0!AccessCheck` at `0x18002566e`
- `api-ms-win-security-base-l1-1-0!AccessCheck` at `0x18002566e`

## pseudocode

```c
__int64 __fastcall JobAccessCheck(HANDLE ClientToken, PSECURITY_DESCRIPTOR pSecurityDescriptor, DWORD DesiredAccess)
{
  DWORD v3; // ebx
  WINBOOL pfResult; // [rsp+40h] [rbp-40h] BYREF
  DWORD GrantedAccess; // [rsp+44h] [rbp-3Ch] BYREF
  DWORD PrivilegeSetLength; // [rsp+48h] [rbp-38h] BYREF
  struct _PRIVILEGE_SET RequiredPrivileges; // [rsp+50h] [rbp-30h] BYREF
  struct _GENERIC_MAPPING GenericMapping; // [rsp+68h] [rbp-18h] BYREF

  v3 = DesiredAccess;
  pfResult = 0;
  RequiredPrivileges.Privilege[0].Luid = 0;
  if ( !ClientToken || !pSecurityDescriptor || !DesiredAccess )
    return 2147942405LL;
  RequiredPrivileges.Control = 1;
  RequiredPrivileges.PrivilegeCount = 1;
  RequiredPrivileges.Privilege[0].Attributes = 2;
  if ( (DesiredAccess & 1) != 0 )
  {
    RequiredPrivileges.Privilege[0].Luid = (LUID)17LL;
    if ( !PrivilegeCheck(ClientToken, &RequiredPrivileges, &pfResult) )
      return 2147942405LL;
    if ( pfResult )
      v3 &= ~1u;
  }
  if ( (v3 & 0xD0006) != 0 )
  {
    RequiredPrivileges.Privilege[0].Luid = (LUID)18LL;
    if ( !PrivilegeCheck(ClientToken, &RequiredPrivileges, &pfResult) )
      return 2147942405LL;
    if ( pfResult )
      v3 &= 0xFFF2FFF9;
  }
  if ( !v3 )
    return 0;
  GenericMapping.GenericRead = 1179785;
  GenericMapping.GenericWrite = 1179926;
  GenericMapping.GenericExecute = 1179808;
  GenericMapping.GenericAll = 2032127;
  PrivilegeSetLength = 20;
  memset(&RequiredPrivileges, 0, sizeof(RequiredPrivileges));
  GrantedAccess = 0;
  if ( AccessCheck(
         pSecurityDescriptor,
         ClientToken,
         v3,
         &GenericMapping,
         &RequiredPrivileges,
         &PrivilegeSetLength,
         &GrantedAccess,
         &pfResult) )
  {
    if ( pfResult && (GrantedAccess & v3) == v3 )
      return 0;
  }
  return 2147942405LL;
}

```

## disassembly

```asm
0x180025550  push    rbp
0x180025552  push    rbx
0x180025553  push    rsi
0x180025554  push    rdi
0x180025555  push    r14
0x180025557  mov     rbp, rsp
0x18002555a  sub     rsp, 80h
0x180025561  mov     rax, cs:__security_cookie
0x180025568  xor     rax, rsp
0x18002556b  mov     [rbp+var_8], rax
0x18002556f  xor     r14d, r14d
0x180025572  mov     ebx, r8d
0x180025575  mov     [rbp+pfResult], r14d
0x180025579  mov     rsi, rdx
0x18002557c  mov     qword ptr [rbp+RequiredPrivileges.Privilege.Luid.LowPart], r14
0x180025580  mov     rdi, rcx
0x180025583  test    rcx, rcx
0x180025586  jz      loc_18002568B
0x18002558c  test    rdx, rdx
0x18002558f  jz      loc_18002568B
0x180025595  test    ebx, ebx
0x180025597  jz      loc_18002568B
0x18002559d  mov     [rbp+RequiredPrivileges.Control], 1
0x1800255a4  mov     [rbp+RequiredPrivileges.PrivilegeCount], 1
0x1800255ab  mov     [rbp+RequiredPrivileges.Privilege.Attributes], 2
0x1800255b2  test    bl, 1
0x1800255b5  jz      short loc_1800255DE
0x1800255b7  lea     r8, [rbp+pfResult]; pfResult
0x1800255bb  mov     qword ptr [rbp+RequiredPrivileges.Privilege.Luid.LowPart], 11h
0x1800255c3  lea     rdx, [rbp+RequiredPrivileges]; RequiredPrivileges
0x1800255c7  call    cs:__imp_PrivilegeCheck
0x1800255cd  test    eax, eax
0x1800255cf  jz      loc_18002568B
0x1800255d5  cmp     [rbp+pfResult], r14d
0x1800255d9  jz      short loc_1800255DE
0x1800255db  and     ebx, 0FFFFFFFEh
0x1800255de  test    ebx, 0D0006h
0x1800255e4  jnz     loc_180025695
0x1800255ea  test    ebx, ebx
0x1800255ec  jnz     short loc_18002560A
0x1800255ee  xor     eax, eax
0x1800255f0  mov     rcx, [rbp+var_8]
0x1800255f4  xor     rcx, rsp; StackCookie
0x1800255f7  call    __security_check_cookie
0x1800255fc  add     rsp, 80h
0x180025603  pop     r14
0x180025605  pop     rdi
0x180025606  pop     rsi
0x180025607  pop     rbx
0x180025608  pop     rbp
0x180025609  retn
0x18002560a  xor     eax, eax
0x18002560c  mov     [rbp+GenericMapping.GenericRead], 120089h
0x180025613  mov     [rbp+RequiredPrivileges.Privilege.Attributes], eax
0x180025616  lea     r9, [rbp+GenericMapping]; GenericMapping
0x18002561a  lea     rax, [rbp+pfResult]
0x18002561e  mov     [rbp+GenericMapping.GenericWrite], 120116h
0x180025625  mov     [rsp+80h+AccessStatus], rax; AccessStatus
0x18002562a  xorps   xmm0, xmm0
0x18002562d  lea     rax, [rbp+var_3C]
0x180025631  mov     [rbp+GenericMapping.GenericExecute], 1200A0h
0x180025638  mov     [rsp+80h+GrantedAccess], rax; GrantedAccess
0x18002563d  mov     r8d, ebx; DesiredAccess
0x180025640  lea     rax, [rbp+var_38]
0x180025644  mov     [rbp+GenericMapping.GenericAll], 1F01FFh
0x18002564b  mov     [rsp+80h+PrivilegeSetLength], rax; PrivilegeSetLength
0x180025650  mov     rdx, rdi; ClientToken
0x180025653  lea     rax, [rbp+RequiredPrivileges]
0x180025657  mov     [rbp+var_38], 14h
0x18002565e  mov     rcx, rsi; pSecurityDescriptor
0x180025661  mov     [rsp+80h+PrivilegeSet], rax; PrivilegeSet
0x180025666  movups  xmmword ptr [rbp+RequiredPrivileges.PrivilegeCount], xmm0
0x18002566a  mov     [rbp+var_3C], r14d
0x18002566e  call    cs:__imp_AccessCheck
0x180025674  test    eax, eax
0x180025676  jz      short loc_18002568B
0x180025678  cmp     [rbp+pfResult], r14d
0x18002567c  jz      short loc_18002568B
0x18002567e  mov     eax, ebx
0x180025680  and     eax, [rbp+var_3C]
0x180025683  cmp     eax, ebx
0x180025685  jz      loc_1800255EE
0x18002568b  mov     eax, 80070005h
0x180025690  jmp     loc_1800255F0
0x180025695  lea     r8, [rbp+pfResult]; pfResult
0x180025699  mov     qword ptr [rbp+RequiredPrivileges.Privilege.Luid.LowPart], 12h
0x1800256a1  lea     rdx, [rbp+RequiredPrivileges]; RequiredPrivileges
0x1800256a5  mov     rcx, rdi; ClientToken
0x1800256a8  call    cs:__imp_PrivilegeCheck
0x1800256ae  test    eax, eax
0x1800256b0  jz      short loc_18002568B
0x1800256b2  cmp     [rbp+pfResult], r14d
0x1800256b6  jz      loc_1800255EA
0x1800256bc  and     ebx, 0FFF2FFF9h
0x1800256c2  jmp     loc_1800255EA
```
