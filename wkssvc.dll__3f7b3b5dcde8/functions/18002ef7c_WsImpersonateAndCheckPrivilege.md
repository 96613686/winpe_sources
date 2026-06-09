# WsImpersonateAndCheckPrivilege

- ea: `0x18002ef7c`
- end: `0x18002f05d`
- name: `WsImpersonateAndCheckPrivilege`
- size: `225`
- prototype: `RPC_STATUS __fastcall(DWORD)`
- caller_count: `3`
- callee_count: `5`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x1800012a0`
- `0x180001710`
- `0x18002de90`

## callees

- `0x180007c80`
- `0x180008950`
- `0x1800089d0`
- `0x18001e420`
- `0x18002ef7c`

## import_xrefs

- `ntdll!NtOpenThreadToken` at `0x18002efd1`
- `ntdll!NtOpenThreadToken` at `0x18002efd1`
- `ntdll!NtClose` at `0x18002f037`
- `ntdll!NtClose` at `0x18002f037`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002f015`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002f015`
- `api-ms-win-security-base-l1-1-0!PrivilegeCheck` at `0x18002f00b`
- `api-ms-win-security-base-l1-1-0!PrivilegeCheck` at `0x18002f00b`

## pseudocode

```c
RPC_STATUS __fastcall WsImpersonateAndCheckPrivilege(DWORD a1)
{
  RPC_STATUS result; // eax
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
  if ( !result )
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
0x18002ef7c  push    rbp
0x18002ef7e  push    rbx
0x18002ef7f  push    rsi
0x18002ef80  push    rdi
0x18002ef81  mov     rbp, rsp
0x18002ef84  sub     rsp, 58h
0x18002ef88  mov     rax, cs:__security_cookie
0x18002ef8f  xor     rax, rsp
0x18002ef92  mov     [rbp+var_10], rax
0x18002ef96  xor     eax, eax
0x18002ef98  mov     [rbp+TokenHandle], 0FFFFFFFFFFFFFFFFh
0x18002efa0  mov     esi, ecx
0x18002efa2  mov     [rbp+RequiredPrivileges.Privilege.Attributes], eax
0x18002efa5  xorps   xmm0, xmm0
0x18002efa8  mov     [rbp+pfResult], eax
0x18002efab  xor     ecx, ecx
0x18002efad  xor     edx, edx
0x18002efaf  movups  xmmword ptr [rbp+RequiredPrivileges.PrivilegeCount], xmm0
0x18002efb3  call    WsImpersonateClient2
0x18002efb8  test    eax, eax
0x18002efba  jnz     loc_18002F048
0x18002efc0  lea     r9, [rbp+TokenHandle]; TokenHandle
0x18002efc4  mov     r8b, 1; OpenAsSelf
0x18002efc7  lea     edx, [rax+8]; DesiredAccess
0x18002efca  mov     rcx, 0FFFFFFFFFFFFFFFEh; ThreadHandle
0x18002efd1  call    cs:__imp_NtOpenThreadToken
0x18002efd7  mov     ecx, eax; Status
0x18002efd9  mov     ebx, eax
0x18002efdb  call    NetpNtStatusToApiStatus
0x18002efe0  mov     edi, eax
0x18002efe2  test    ebx, ebx
0x18002efe4  js      short loc_18002F03D
0x18002efe6  mov     rcx, [rbp+TokenHandle]; ClientToken
0x18002efea  lea     r8, [rbp+pfResult]; pfResult
0x18002efee  lea     rdx, [rbp+RequiredPrivileges]; RequiredPrivileges
0x18002eff2  mov     [rbp+RequiredPrivileges.Control], 1
0x18002eff9  mov     [rbp+RequiredPrivileges.PrivilegeCount], 1
0x18002f000  mov     qword ptr [rbp+RequiredPrivileges.Privilege.Luid.HighPart], 0
0x18002f008  mov     [rbp+RequiredPrivileges.Privilege.Luid.LowPart], esi
0x18002f00b  call    cs:__imp_PrivilegeCheck
0x18002f011  test    eax, eax
0x18002f013  jnz     short loc_18002F01F
0x18002f015  call    cs:__imp_GetLastError
0x18002f01b  mov     edi, eax
0x18002f01d  jmp     short loc_18002F033
0x18002f01f  cmp     [rbp+pfResult], 0
0x18002f023  jnz     short loc_18002F031
0x18002f025  mov     ecx, 0C0000061h; Status
0x18002f02a  call    NetpNtStatusToApiStatus
0x18002f02f  jmp     short loc_18002F01B
0x18002f031  xor     edi, edi
0x18002f033  mov     rcx, [rbp+TokenHandle]; Handle
0x18002f037  call    cs:__imp_NtClose
0x18002f03d  xor     edx, edx
0x18002f03f  xor     ecx, ecx
0x18002f041  call    WsRevertToSelf2
0x18002f046  mov     eax, edi
0x18002f048  mov     rcx, [rbp+var_10]
0x18002f04c  xor     rcx, rsp; StackCookie
0x18002f04f  call    __security_check_cookie
0x18002f054  add     rsp, 58h
0x18002f058  pop     rdi
0x18002f059  pop     rsi
0x18002f05a  pop     rbx
0x18002f05b  pop     rbp
0x18002f05c  retn
```
