# CImpersonateEveryone::_GetToken(void * *)

- ea: `0x180017fd0`
- end: `0x1800180cf`
- name: `?_GetToken@CImpersonateEveryone@@MEAAJPEAPEAX@Z`
- size: `255`
- prototype: `int __fastcall(CImpersonateEveryone *this, void **)`
- caller_count: `0`
- callee_count: `2`
- tags: `authz_impersonation, loader_planting`

## callees

- `0x180017fd0`
- `0x180032c90`

## import_xrefs

- `ntdll!RtlFreeSid` at `0x18001809d`
- `ntdll!RtlFreeSid` at `0x18001809d`
- `ntdll!NtClose` at `0x180018093`
- `ntdll!NtClose` at `0x180018093`
- `ntdll!NtFilterToken` at `0x180018087`
- `ntdll!NtFilterToken` at `0x180018087`
- `ntdll!NtOpenProcessToken` at `0x18001804f`
- `ntdll!NtOpenProcessToken` at `0x18001804f`
- `ntdll!RtlAllocateAndInitializeSid` at `0x180018032`
- `ntdll!RtlAllocateAndInitializeSid` at `0x180018032`
- `ntdll!RtlNtStatusToDosError` at `0x1800180a5`
- `ntdll!RtlNtStatusToDosError` at `0x1800180a5`

## pseudocode

```c
int __fastcall CImpersonateEveryone::_GetToken(CImpersonateEveryone *this, void **a2)
{
  int v3; // ebx
  int result; // eax
  void *TokenHandle; // [rsp+60h] [rbp-9h] BYREF
  PSID Sid; // [rsp+68h] [rbp-1h] BYREF
  _SID_IDENTIFIER_AUTHORITY IdentifierAuthority; // [rsp+70h] [rbp+7h] BYREF
  _TOKEN_GROUPS SidsToDisable; // [rsp+78h] [rbp+Fh] BYREF

  *(_WORD *)&IdentifierAuthority.Value[4] = 1280;
  Sid = 0;
  *(_DWORD *)IdentifierAuthority.Value = 0;
  v3 = RtlAllocateAndInitializeSid(&IdentifierAuthority, 2u, 0x20u, 0x220u, 0, 0, 0, 0, 0, 0, &Sid);
  if ( v3 >= 0 )
  {
    TokenHandle = 0;
    v3 = NtOpenProcessToken((HANDLE)0xFFFFFFFFFFFFFFFFLL, 0xF01FFu, &TokenHandle);
    if ( v3 >= 0 )
    {
      SidsToDisable.Groups[0].Sid = Sid;
      *(_QWORD *)&SidsToDisable.GroupCount = 1;
      *(_QWORD *)&SidsToDisable.Groups[0].Attributes = 0;
      v3 = NtFilterToken(TokenHandle, 1u, &SidsToDisable, 0, 0, a2);
      NtClose(TokenHandle);
    }
    RtlFreeSid(Sid);
  }
  result = RtlNtStatusToDosError(v3);
  if ( result > 0 )
    return (unsigned __int16)result | 0x80070000;
  return result;
}

```

## disassembly

```asm
0x180017fd0  push    rbp
0x180017fd2  push    rbx
0x180017fd3  push    rsi
0x180017fd4  push    rdi
0x180017fd5  lea     rbp, [rsp-3Fh]
0x180017fda  sub     rsp, 0A8h
0x180017fe1  mov     rax, cs:__security_cookie
0x180017fe8  xor     rax, rsp
0x180017feb  mov     [rbp+57h+var_30], rax
0x180017fef  xor     esi, esi
0x180017ff1  mov     word ptr [rbp+57h+IdentifierAuthority.Value+4], 500h
0x180017ff7  lea     rax, [rbp+57h+var_58]
0x180017ffb  mov     [rbp+57h+var_58], rsi
0x180017fff  mov     [rsp+0C0h+Sid], rax; Sid
0x180018004  lea     rcx, [rbp+57h+IdentifierAuthority]; IdentifierAuthority
0x180018008  mov     [rsp+0C0h+SubAuthority7], esi; SubAuthority7
0x18001800c  mov     rdi, rdx
0x18001800f  mov     [rsp+0C0h+SubAuthority6], esi; SubAuthority6
0x180018013  lea     r8d, [rsi+20h]; SubAuthority0
0x180018017  mov     [rsp+0C0h+SubAuthority5], esi; SubAuthority5
0x18001801b  mov     r9d, 220h; SubAuthority1
0x180018021  mov     [rsp+0C0h+SubAuthority4], esi; SubAuthority4
0x180018025  mov     dl, 2; SubAuthorityCount
0x180018027  mov     [rsp+0C0h+SubAuthority3], esi; SubAuthority3
0x18001802b  mov     [rsp+0C0h+SubAuthority2], esi; SubAuthority2
0x18001802f  mov     dword ptr [rbp+57h+IdentifierAuthority.Value], esi
0x180018032  call    cs:__imp_RtlAllocateAndInitializeSid
0x180018038  mov     ebx, eax
0x18001803a  test    eax, eax
0x18001803c  js      short loc_1800180A3
0x18001803e  lea     r8, [rbp+57h+TokenHandle]; TokenHandle
0x180018042  mov     [rbp+57h+TokenHandle], rsi
0x180018046  mov     edx, 0F01FFh; DesiredAccess
0x18001804b  or      rcx, 0FFFFFFFFFFFFFFFFh; ProcessHandle
0x18001804f  call    cs:__imp_NtOpenProcessToken
0x180018055  mov     ebx, eax
0x180018057  test    eax, eax
0x180018059  js      short loc_180018099
0x18001805b  mov     rax, [rbp+57h+var_58]
0x18001805f  lea     edx, [rsi+1]; Flags
0x180018062  mov     rcx, [rbp+57h+TokenHandle]; ExistingTokenHandle
0x180018066  lea     r8, [rbp+57h+SidsToDisable]; SidsToDisable
0x18001806a  mov     qword ptr [rsp+0C0h+SubAuthority3], rdi; NewTokenHandle
0x18001806f  xor     r9d, r9d; PrivilegesToDelete
0x180018072  mov     [rbp+57h+SidsToDisable.Groups.Sid], rax
0x180018076  mov     qword ptr [rbp+57h+SidsToDisable.GroupCount], 1
0x18001807e  mov     qword ptr [rbp+57h+SidsToDisable.Groups.Attributes], rsi
0x180018082  mov     qword ptr [rsp+0C0h+SubAuthority2], rsi; RestrictedSids
0x180018087  call    cs:__imp_NtFilterToken
0x18001808d  mov     rcx, [rbp+57h+TokenHandle]; Handle
0x180018091  mov     ebx, eax
0x180018093  call    cs:__imp_NtClose
0x180018099  mov     rcx, [rbp+57h+var_58]; Sid
0x18001809d  call    cs:__imp_RtlFreeSid
0x1800180a3  mov     ecx, ebx; Status
0x1800180a5  call    cs:__imp_RtlNtStatusToDosError
0x1800180ab  test    eax, eax
0x1800180ad  jle     short loc_1800180B7
0x1800180af  movzx   eax, ax
0x1800180b2  or      eax, 80070000h
0x1800180b7  mov     rcx, [rbp+57h+var_30]
0x1800180bb  xor     rcx, rsp; StackCookie
0x1800180be  call    __security_check_cookie
0x1800180c3  add     rsp, 0A8h
0x1800180ca  pop     rdi
0x1800180cb  pop     rsi
0x1800180cc  pop     rbx
0x1800180cd  pop     rbp
0x1800180ce  retn
```
