# CheckTokenForAccessThroughCapability(void *,void *,void *,void *,uchar,uchar,uchar *)

- ea: `0x18000c4f0`
- end: `0x18000c6c3`
- name: `?CheckTokenForAccessThroughCapability@@YAKPEAX000EEPEAE@Z`
- size: `467`
- prototype: `unsigned int __usercall@<eax>(HANDLE ClientToken@<rcx>, void *@<rdx>, void *@<r8>, void *@<r9>, unsigned __int8, unsigned __int8, unsigned __int8 *)`
- caller_count: `5`
- callee_count: `2`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x1800092a0`
- `0x18000a4a0`
- `0x18000ad00`
- `0x1800376bc`
- `0x1800d494c`

## callees

- `0x18000c4f0`
- `0x1800de450`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18000c566`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18000c566`
- `api-ms-win-security-base-l1-1-0!PrivilegeCheck` at `0x18000c629`
- `api-ms-win-security-base-l1-1-0!PrivilegeCheck` at `0x18000c629`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c635`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c635`
- `api-ms-win-security-base-l1-2-0!CheckTokenCapability` at `0x18000c699`
- `api-ms-win-security-base-l1-2-0!CheckTokenCapability` at `0x18000c699`
- `api-ms-win-security-base-l1-2-0!CheckTokenMembershipEx` at `0x18000c59a`
- `api-ms-win-security-base-l1-2-0!CheckTokenMembershipEx` at `0x18000c64a`
- `api-ms-win-security-base-l1-2-0!CheckTokenMembershipEx` at `0x18000c67d`
- `api-ms-win-security-base-l1-2-0!CheckTokenMembershipEx` at `0x18000c59a`
- `api-ms-win-security-base-l1-2-0!CheckTokenMembershipEx` at `0x18000c64a`
- `api-ms-win-security-base-l1-2-0!CheckTokenMembershipEx` at `0x18000c67d`
- `ntdll!RtlIsMultiSessionSku` at `0x18000c5ba`
- `ntdll!RtlIsMultiSessionSku` at `0x18000c5ba`

## pseudocode

```c
DWORD __fastcall CheckTokenForAccessThroughCapability(
        __int64 ClientToken,
        void *a2,
        void *a3,
        void *a4,
        unsigned __int8 a5,
        unsigned __int8 a6,
        unsigned __int8 *a7)
{
  __int64 v10; // rsi
  __int64 v12; // rcx
  WINBOOL pfResult; // [rsp+30h] [rbp-38h] BYREF
  int TokenInformation; // [rsp+34h] [rbp-34h] BYREF
  DWORD ReturnLength; // [rsp+38h] [rbp-30h] BYREF
  struct _PRIVILEGE_SET RequiredPrivileges; // [rsp+40h] [rbp-28h] BYREF

  RequiredPrivileges.Privilege[0].Attributes = 0;
  pfResult = 0;
  TokenInformation = 0;
  *a7 = 0;
  ReturnLength = 0;
  v10 = -6;
  if ( ClientToken )
    v10 = ClientToken;
  *(_OWORD *)&RequiredPrivileges.PrivilegeCount = 0;
  if ( !GetTokenInformation((HANDLE)v10, TokenIsAppContainer, &TokenInformation, 4u, &ReturnLength) )
    return GetLastError();
  if ( a2 )
  {
    if ( !(unsigned int)CheckTokenMembershipEx(v10, a2, 0, &pfResult) )
      return GetLastError();
  }
  if ( !pfResult )
  {
    if ( !(unsigned int)CheckTokenMembershipEx(v10, a3, TokenInformation != 0, &pfResult) )
      return GetLastError();
    if ( !pfResult )
    {
      if ( !a5 )
        goto LABEL_18;
      if ( !(unsigned __int8)RtlIsMultiSessionSku(v12)
        && !(unsigned int)CheckTokenMembershipEx(v10, &DefaultAliasWellKnownSid, TokenInformation != 0, &pfResult) )
      {
        return GetLastError();
      }
      if ( !pfResult )
      {
LABEL_18:
        if ( !a6 )
          return 0;
        RequiredPrivileges.PrivilegeCount = 1;
        RequiredPrivileges.Control = 1;
        RequiredPrivileges.Privilege[0].Luid = (LUID)29LL;
        RequiredPrivileges.Privilege[0].Attributes = 0;
        if ( !PrivilegeCheck((HANDLE)v10, &RequiredPrivileges, &pfResult) )
          return GetLastError();
        if ( !pfResult )
          return 0;
      }
    }
  }
  if ( !TokenInformation )
  {
LABEL_12:
    *a7 = 1;
    return 0;
  }
  if ( (unsigned int)CheckTokenCapability(v10, a4, &pfResult) )
  {
    if ( !pfResult )
      return 0;
    goto LABEL_12;
  }
  return GetLastError();
}

```

## disassembly

```asm
0x18000c4f0  push    rbp
0x18000c4f2  push    rbx
0x18000c4f3  push    rsi
0x18000c4f4  push    rdi
0x18000c4f5  push    r12
0x18000c4f7  push    r13
0x18000c4f9  push    r14
0x18000c4fb  push    r15
0x18000c4fd  mov     rbp, rsp
0x18000c500  sub     rsp, 68h
0x18000c504  mov     rax, cs:__security_cookie
0x18000c50b  xor     rax, rsp
0x18000c50e  mov     [rbp+var_10], rax
0x18000c512  mov     r14, [rbp+arg_30]
0x18000c516  xor     eax, eax
0x18000c518  xor     r13d, r13d
0x18000c51b  mov     [rbp+RequiredPrivileges.Privilege.Attributes], eax
0x18000c51e  test    rcx, rcx
0x18000c521  mov     [rbp+pfResult], r13d
0x18000c525  mov     r12, r9
0x18000c528  mov     [rbp+TokenInformation], r13d
0x18000c52c  mov     [r14], al
0x18000c52f  mov     r15, r8
0x18000c532  lea     rax, [rbp+var_30]
0x18000c536  mov     [rbp+var_30], r13d
0x18000c53a  mov     rdi, rdx
0x18000c53d  mov     [rsp+68h+ReturnLength], rax; ReturnLength
0x18000c542  xorps   xmm0, xmm0
0x18000c545  lea     r8, [rbp+TokenInformation]; TokenInformation
0x18000c549  mov     rsi, 0FFFFFFFFFFFFFFFAh
0x18000c550  mov     r9d, 4; TokenInformationLength
0x18000c556  cmovnz  rsi, rcx
0x18000c55a  mov     edx, 1Dh; TokenInformationClass
0x18000c55f  mov     rcx, rsi; TokenHandle
0x18000c562  movups  xmmword ptr [rbp+RequiredPrivileges.PrivilegeCount], xmm0
0x18000c566  call    cs:__imp_GetTokenInformation
0x18000c56c  mov     ebx, eax
0x18000c56e  test    eax, eax
0x18000c570  jz      loc_18000C635
0x18000c576  test    rdi, rdi
0x18000c579  jnz     loc_18000C63D
0x18000c57f  cmp     [rbp+pfResult], r13d
0x18000c583  jnz     short loc_18000C5D2
0x18000c585  cmp     [rbp+TokenInformation], r13d
0x18000c589  lea     r9, [rbp+pfResult]
0x18000c58d  mov     r8d, r13d
0x18000c590  mov     rdx, r15
0x18000c593  setnz   r8b
0x18000c597  mov     rcx, rsi
0x18000c59a  call    cs:__imp_CheckTokenMembershipEx
0x18000c5a0  mov     ebx, eax
0x18000c5a2  test    eax, eax
0x18000c5a4  jz      loc_18000C635
0x18000c5aa  cmp     [rbp+pfResult], r13d
0x18000c5ae  jnz     short loc_18000C5D2
0x18000c5b0  cmp     [rbp+arg_20], r13b
0x18000c5b4  jz      loc_18000C65C
0x18000c5ba  call    cs:__imp_RtlIsMultiSessionSku
0x18000c5c0  test    al, al
0x18000c5c2  jz      loc_18000C664
0x18000c5c8  cmp     [rbp+pfResult], r13d
0x18000c5cc  jz      loc_18000C65C
0x18000c5d2  cmp     [rbp+TokenInformation], r13d
0x18000c5d6  jnz     loc_18000C68F
0x18000c5dc  mov     byte ptr [r14], 1
0x18000c5e0  test    ebx, ebx
0x18000c5e2  jz      short loc_18000C635
0x18000c5e4  mov     eax, r13d
0x18000c5e7  mov     rcx, [rbp+var_10]
0x18000c5eb  xor     rcx, rsp; StackCookie
0x18000c5ee  call    __security_check_cookie
0x18000c5f3  add     rsp, 68h
0x18000c5f7  pop     r15
0x18000c5f9  pop     r14
0x18000c5fb  pop     r13
0x18000c5fd  pop     r12
0x18000c5ff  pop     rdi
0x18000c600  pop     rsi
0x18000c601  pop     rbx
0x18000c602  pop     rbp
0x18000c603  retn
0x18000c604  lea     r8, [rbp+pfResult]; pfResult
0x18000c608  mov     [rbp+RequiredPrivileges.PrivilegeCount], 1
0x18000c60f  lea     rdx, [rbp+RequiredPrivileges]; RequiredPrivileges
0x18000c613  mov     [rbp+RequiredPrivileges.Control], 1
0x18000c61a  mov     rcx, rsi; ClientToken
0x18000c61d  mov     qword ptr [rbp+RequiredPrivileges.Privilege.Luid.LowPart], 1Dh
0x18000c625  mov     [rbp+RequiredPrivileges.Privilege.Attributes], r13d
0x18000c629  call    cs:__imp_PrivilegeCheck
0x18000c62f  mov     ebx, eax
0x18000c631  test    eax, eax
0x18000c633  jnz     short loc_18000C6B4
0x18000c635  call    cs:__imp_GetLastError
0x18000c63b  jmp     short loc_18000C5E7
0x18000c63d  lea     r9, [rbp+pfResult]
0x18000c641  xor     r8d, r8d
0x18000c644  mov     rdx, rdi
0x18000c647  mov     rcx, rsi
0x18000c64a  call    cs:__imp_CheckTokenMembershipEx
0x18000c650  mov     ebx, eax
0x18000c652  test    eax, eax
0x18000c654  jnz     loc_18000C57F
0x18000c65a  jmp     short loc_18000C635
0x18000c65c  cmp     [rbp+arg_28], r13b
0x18000c660  jz      short loc_18000C5E4
0x18000c662  jmp     short loc_18000C604
0x18000c664  cmp     [rbp+TokenInformation], r13d
0x18000c668  lea     r9, [rbp+pfResult]
0x18000c66c  mov     r8d, r13d
0x18000c66f  lea     rdx, ?DefaultAliasWellKnownSid@@3PAEA; uchar near * DefaultAliasWellKnownSid
0x18000c676  setnz   r8b
0x18000c67a  mov     rcx, rsi
0x18000c67d  call    cs:__imp_CheckTokenMembershipEx
0x18000c683  mov     ebx, eax
0x18000c685  test    eax, eax
0x18000c687  jnz     loc_18000C5C8
0x18000c68d  jmp     short loc_18000C635
0x18000c68f  lea     r8, [rbp+pfResult]
0x18000c693  mov     rdx, r12
0x18000c696  mov     rcx, rsi
0x18000c699  call    cs:__imp_CheckTokenCapability
0x18000c69f  mov     ebx, eax
0x18000c6a1  test    eax, eax
0x18000c6a3  jz      short loc_18000C635
0x18000c6a5  cmp     [rbp+pfResult], r13d
0x18000c6a9  jnz     loc_18000C5DC
0x18000c6af  jmp     loc_18000C5E4
0x18000c6b4  cmp     [rbp+pfResult], r13d
0x18000c6b8  jz      loc_18000C5E4
0x18000c6be  jmp     loc_18000C5D2
```
