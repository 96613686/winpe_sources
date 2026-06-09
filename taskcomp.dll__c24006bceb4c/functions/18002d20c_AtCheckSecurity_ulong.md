# AtCheckSecurity(ulong)

- ea: `0x18002d20c`
- end: `0x18002d302`
- name: `?AtCheckSecurity@@YAKK@Z`
- size: `246`
- prototype: `RPC_STATUS __fastcall(ACCESS_MASK DesiredAccess)`
- caller_count: `4`
- callee_count: `3`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180015c50`
- `0x180015d80`
- `0x180016020`
- `0x1800165f0`

## callees

- `0x180016fa0`
- `0x18002d20c`
- `0x18002e5b0`

## import_xrefs

- `ntdll!NtOpenThreadToken` at `0x18002d25a`
- `ntdll!NtOpenThreadToken` at `0x18002d25a`
- `ntdll!NtAccessCheck` at `0x18002d2b8`
- `ntdll!NtAccessCheck` at `0x18002d2b8`
- `ntdll!NtClose` at `0x18002d2ca`
- `ntdll!NtClose` at `0x18002d2ca`
- `RPCRT4!RpcRevertToSelf` at `0x18002d2d0`
- `RPCRT4!RpcRevertToSelf` at `0x18002d2d0`
- `RPCRT4!RpcImpersonateClient` at `0x18002d23b`
- `RPCRT4!RpcImpersonateClient` at `0x18002d23b`

## pseudocode

```c
RPC_STATUS __fastcall AtCheckSecurity(ACCESS_MASK DesiredAccess)
{
  RPC_STATUS result; // eax
  unsigned int v3; // ebx
  int AccessStatus; // [rsp+40h] [rbp-40h] BYREF
  DWORD GrantedAccess; // [rsp+44h] [rbp-3Ch] BYREF
  ULONG ReturnLength; // [rsp+48h] [rbp-38h] BYREF
  void *TokenHandle; // [rsp+50h] [rbp-30h] BYREF
  struct _PRIVILEGE_SET PrivilegeSet; // [rsp+58h] [rbp-28h] BYREF

  TokenHandle = (void *)-1LL;
  result = RpcImpersonateClient(0);
  if ( !result )
  {
    v3 = NtOpenThreadToken((HANDLE)0xFFFFFFFFFFFFFFFELL, 8u, 1u, &TokenHandle);
    if ( !v3 )
    {
      GrantedAccess = 0;
      AccessStatus = 0;
      memset(&PrivilegeSet, 0, sizeof(PrivilegeSet));
      ReturnLength = 20;
      v3 = NtAccessCheck(
             AtGlobalSecurityDescriptor,
             TokenHandle,
             DesiredAccess,
             &AtGlobalInformationMapping,
             &PrivilegeSet,
             &ReturnLength,
             &GrantedAccess,
             &AccessStatus);
      if ( !v3 )
        v3 = AccessStatus;
      NtClose(TokenHandle);
    }
    result = RpcRevertToSelf();
    if ( !result )
      return NetpNtStatusToApiStatus(v3);
  }
  return result;
}

```

## disassembly

```asm
0x18002d20c  mov     [rsp-8+arg_8], rbx
0x18002d211  mov     [rsp-8+arg_10], rdi
0x18002d216  push    rbp
0x18002d217  mov     rbp, rsp
0x18002d21a  sub     rsp, 80h
0x18002d221  mov     rax, cs:__security_cookie
0x18002d228  xor     rax, rsp
0x18002d22b  mov     [rbp+var_10], rax
0x18002d22f  mov     edi, ecx
0x18002d231  mov     [rbp+TokenHandle], 0FFFFFFFFFFFFFFFFh
0x18002d239  xor     ecx, ecx; BindingHandle
0x18002d23b  call    cs:__imp_RpcImpersonateClient
0x18002d241  test    eax, eax
0x18002d243  jnz     loc_18002D2E1
0x18002d249  lea     r9, [rbp+TokenHandle]; TokenHandle
0x18002d24d  mov     r8b, 1; OpenAsSelf
0x18002d250  lea     edx, [rax+8]; DesiredAccess
0x18002d253  mov     rcx, 0FFFFFFFFFFFFFFFEh; ThreadHandle
0x18002d25a  call    cs:__imp_NtOpenThreadToken
0x18002d260  mov     ebx, eax
0x18002d262  test    eax, eax
0x18002d264  jnz     short loc_18002D2D0
0x18002d266  mov     rdx, [rbp+TokenHandle]; ClientToken
0x18002d26a  lea     r9, ?AtGlobalInformationMapping@@3U_GENERIC_MAPPING@@A; GenericMapping
0x18002d271  mov     rcx, cs:?AtGlobalSecurityDescriptor@@3PEAXEA; SecurityDescriptor
0x18002d278  xor     eax, eax
0x18002d27a  mov     [rbp+var_28.Privilege.Attributes], eax
0x18002d27d  xorps   xmm0, xmm0
0x18002d280  mov     [rbp+var_3C], eax
0x18002d283  mov     r8d, edi; DesiredAccess
0x18002d286  mov     [rbp+var_40], eax
0x18002d289  lea     rax, [rbp+var_40]
0x18002d28d  mov     [rsp+80h+AccessStatus], rax; AccessStatus
0x18002d292  lea     rax, [rbp+var_3C]
0x18002d296  mov     [rsp+80h+GrantedAccess], rax; GrantedAccess
0x18002d29b  lea     rax, [rbp+var_38]
0x18002d29f  mov     [rsp+80h+ReturnLength], rax; ReturnLength
0x18002d2a4  lea     rax, [rbp+var_28]
0x18002d2a8  mov     [rsp+80h+PrivilegeSet], rax; PrivilegeSet
0x18002d2ad  movups  xmmword ptr [rbp+var_28.PrivilegeCount], xmm0
0x18002d2b1  mov     [rbp+var_38], 14h
0x18002d2b8  call    cs:__imp_NtAccessCheck
0x18002d2be  mov     rcx, [rbp+TokenHandle]; Handle
0x18002d2c2  test    eax, eax
0x18002d2c4  mov     ebx, eax
0x18002d2c6  cmovz   ebx, [rbp+var_40]
0x18002d2ca  call    cs:__imp_NtClose
0x18002d2d0  call    cs:__imp_RpcRevertToSelf
0x18002d2d6  test    eax, eax
0x18002d2d8  jnz     short loc_18002D2E1
0x18002d2da  mov     ecx, ebx
0x18002d2dc  call    NetpNtStatusToApiStatus
0x18002d2e1  mov     rcx, [rbp+var_10]
0x18002d2e5  xor     rcx, rsp; StackCookie
0x18002d2e8  call    __security_check_cookie
0x18002d2ed  lea     r11, [rsp+80h+var_s0]
0x18002d2f5  mov     rbx, [r11+18h]
0x18002d2f9  mov     rdi, [r11+20h]
0x18002d2fd  mov     rsp, r11
0x18002d300  pop     rbp
0x18002d301  retn
```
