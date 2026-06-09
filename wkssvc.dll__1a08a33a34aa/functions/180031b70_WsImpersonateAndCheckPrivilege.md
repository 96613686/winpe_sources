# WsImpersonateAndCheckPrivilege

- ea: `0x180031b70`
- end: `0x180031c6a`
- name: `WsImpersonateAndCheckPrivilege`
- size: `250`
- prototype: ``
- caller_count: `3`
- callee_count: `5`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x1800012a0`
- `0x180001750`
- `0x1800308e0`

## callees

- `0x1800081b0`
- `0x180009010`
- `0x180009090`
- `0x18001fbd0`
- `0x180031b70`

## import_xrefs

- `ntdll!NtOpenThreadToken` at `0x180031bc5`
- `ntdll!NtOpenThreadToken` at `0x180031bc5`
- `ntdll!NtClose` at `0x180031c3d`
- `ntdll!NtClose` at `0x180031c3d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180031c15`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180031c15`
- `api-ms-win-security-base-l1-1-0!PrivilegeCheck` at `0x180031c05`
- `api-ms-win-security-base-l1-1-0!PrivilegeCheck` at `0x180031c05`

## pseudocode

```c
__int64 __fastcall WsImpersonateAndCheckPrivilege(DWORD a1)
{
  __int64 result; // rax
  int v3; // ebx
  DWORD v4; // edi
  DWORD LastError; // eax
  WINBOOL pfResult; // [rsp+20h] [rbp-38h] BYREF
  void *TokenHandle; // [rsp+28h] [rbp-30h] BYREF
  _PRIVILEGE_SET RequiredPrivileges; // [rsp+30h] [rbp-28h] BYREF

  TokenHandle = (void *)-1LL;
  pfResult = 0;
  memset(&RequiredPrivileges, 0, sizeof(RequiredPrivileges));
  result = WsImpersonateClient2(0, 0);
  if ( !(_DWORD)result )
  {
    v3 = NtOpenThreadToken((HANDLE)0xFFFFFFFFFFFFFFFELL, 8u, 1u, &TokenHandle);
    v4 = NetpNtStatusToApiStatus(v3);
    if ( v3 < 0 )
    {
LABEL_10:
      WsRevertToSelf2(0, 0);
      return v4;
    }
    RequiredPrivileges.Control = 1;
    RequiredPrivileges.PrivilegeCount = 1;
    *(_QWORD *)&RequiredPrivileges.Privilege[0].Luid.HighPart = 0;
    RequiredPrivileges.Privilege[0].Luid.LowPart = a1;
    if ( PrivilegeCheck(TokenHandle, &RequiredPrivileges, &pfResult) )
    {
      if ( pfResult )
      {
        v4 = 0;
        goto LABEL_9;
      }
      LastError = NetpNtStatusToApiStatus(-1073741727);
    }
    else
    {
      LastError = GetLastError();
    }
    v4 = LastError;
LABEL_9:
    NtClose(TokenHandle);
    goto LABEL_10;
  }
  return result;
}

```

## disassembly

```asm
0x180031b70  push    rbp
0x180031b72  push    rbx
0x180031b73  push    rsi
0x180031b74  push    rdi
0x180031b75  mov     rbp, rsp
0x180031b78  sub     rsp, 58h
0x180031b7c  mov     rax, cs:__security_cookie
0x180031b83  xor     rax, rsp
0x180031b86  mov     [rbp+var_10], rax
0x180031b8a  xor     eax, eax
0x180031b8c  mov     [rbp+TokenHandle], 0FFFFFFFFFFFFFFFFh
0x180031b94  mov     esi, ecx
0x180031b96  mov     [rbp+RequiredPrivileges.Privilege.Attributes], eax
0x180031b99  xorps   xmm0, xmm0
0x180031b9c  mov     [rbp+pfResult], eax
0x180031b9f  xor     ecx, ecx
0x180031ba1  xor     edx, edx
0x180031ba3  movups  xmmword ptr [rbp+RequiredPrivileges.PrivilegeCount], xmm0
0x180031ba7  call    WsImpersonateClient2
0x180031bac  test    eax, eax
0x180031bae  jnz     loc_180031C54
0x180031bb4  lea     r9, [rbp+TokenHandle]; TokenHandle
0x180031bb8  mov     r8b, 1; OpenAsSelf
0x180031bbb  lea     edx, [rax+8]; DesiredAccess
0x180031bbe  mov     rcx, 0FFFFFFFFFFFFFFFEh; ThreadHandle
0x180031bc5  call    cs:__imp_NtOpenThreadToken
0x180031bcc  nop     dword ptr [rax+rax+00h]
0x180031bd1  mov     ecx, eax; Status
0x180031bd3  mov     ebx, eax
0x180031bd5  call    NetpNtStatusToApiStatus
0x180031bda  mov     edi, eax
0x180031bdc  test    ebx, ebx
0x180031bde  js      short loc_180031C49
0x180031be0  mov     rcx, [rbp+TokenHandle]; ClientToken
0x180031be4  lea     r8, [rbp+pfResult]; pfResult
0x180031be8  lea     rdx, [rbp+RequiredPrivileges]; RequiredPrivileges
0x180031bec  mov     [rbp+RequiredPrivileges.Control], 1
0x180031bf3  mov     [rbp+RequiredPrivileges.PrivilegeCount], 1
0x180031bfa  mov     qword ptr [rbp+RequiredPrivileges.Privilege.Luid.HighPart], 0
0x180031c02  mov     [rbp+RequiredPrivileges.Privilege.Luid.LowPart], esi
0x180031c05  call    cs:__imp_PrivilegeCheck
0x180031c0c  nop     dword ptr [rax+rax+00h]
0x180031c11  test    eax, eax
0x180031c13  jnz     short loc_180031C25
0x180031c15  call    cs:__imp_GetLastError
0x180031c1c  nop     dword ptr [rax+rax+00h]
0x180031c21  mov     edi, eax
0x180031c23  jmp     short loc_180031C39
0x180031c25  cmp     [rbp+pfResult], 0
0x180031c29  jnz     short loc_180031C37
0x180031c2b  mov     ecx, 0C0000061h; Status
0x180031c30  call    NetpNtStatusToApiStatus
0x180031c35  jmp     short loc_180031C21
0x180031c37  xor     edi, edi
0x180031c39  mov     rcx, [rbp+TokenHandle]; Handle
0x180031c3d  call    cs:__imp_NtClose
0x180031c44  nop     dword ptr [rax+rax+00h]
0x180031c49  xor     edx, edx
0x180031c4b  xor     ecx, ecx
0x180031c4d  call    WsRevertToSelf2
0x180031c52  mov     eax, edi
0x180031c54  mov     rcx, [rbp+var_10]
0x180031c58  xor     rcx, rsp; StackCookie
0x180031c5b  call    __security_check_cookie
0x180031c60  add     rsp, 58h
0x180031c64  pop     rdi
0x180031c65  pop     rsi
0x180031c66  pop     rbx
0x180031c67  pop     rbp
0x180031c68  retn
```
