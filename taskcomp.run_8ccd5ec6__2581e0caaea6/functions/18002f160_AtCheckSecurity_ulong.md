# AtCheckSecurity(ulong)

- ea: `0x18002f160`
- end: `0x18002f275`
- name: `?AtCheckSecurity@@YAKK@Z`
- size: `277`
- prototype: `unsigned int __fastcall(ACCESS_MASK DesiredAccess)`
- caller_count: `4`
- callee_count: `3`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180016ab0`
- `0x180016bf0`
- `0x180016ea0`
- `0x1800174c0`

## callees

- `0x180017f64`
- `0x18002f160`
- `0x180030700`

## import_xrefs

- `ntdll!NtOpenThreadToken` at `0x18002f1b4`
- `ntdll!NtOpenThreadToken` at `0x18002f1b4`
- `ntdll!NtAccessCheck` at `0x18002f218`
- `ntdll!NtAccessCheck` at `0x18002f218`
- `ntdll!NtClose` at `0x18002f230`
- `ntdll!NtClose` at `0x18002f230`
- `RPCRT4!RpcRevertToSelf` at `0x18002f23c`
- `RPCRT4!RpcRevertToSelf` at `0x18002f23c`
- `RPCRT4!RpcImpersonateClient` at `0x18002f18f`
- `RPCRT4!RpcImpersonateClient` at `0x18002f18f`

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
0x18002f160  mov     [rsp-8+arg_8], rbx
0x18002f165  mov     [rsp-8+arg_10], rdi
0x18002f16a  push    rbp
0x18002f16b  mov     rbp, rsp
0x18002f16e  sub     rsp, 80h
0x18002f175  mov     rax, cs:__security_cookie
0x18002f17c  xor     rax, rsp
0x18002f17f  mov     [rbp+var_10], rax
0x18002f183  mov     edi, ecx
0x18002f185  mov     [rbp+TokenHandle], 0FFFFFFFFFFFFFFFFh
0x18002f18d  xor     ecx, ecx; BindingHandle
0x18002f18f  call    cs:__imp_RpcImpersonateClient
0x18002f196  nop     dword ptr [rax+rax+00h]
0x18002f19b  test    eax, eax
0x18002f19d  jnz     loc_18002F253
0x18002f1a3  lea     r9, [rbp+TokenHandle]; TokenHandle
0x18002f1a7  mov     r8b, 1; OpenAsSelf
0x18002f1aa  lea     edx, [rax+8]; DesiredAccess
0x18002f1ad  mov     rcx, 0FFFFFFFFFFFFFFFEh; ThreadHandle
0x18002f1b4  call    cs:__imp_NtOpenThreadToken
0x18002f1bb  nop     dword ptr [rax+rax+00h]
0x18002f1c0  mov     ebx, eax
0x18002f1c2  test    eax, eax
0x18002f1c4  jnz     short loc_18002F23C
0x18002f1c6  mov     rdx, [rbp+TokenHandle]; ClientToken
0x18002f1ca  lea     r9, ?AtGlobalInformationMapping@@3U_GENERIC_MAPPING@@A; GenericMapping
0x18002f1d1  mov     rcx, cs:?AtGlobalSecurityDescriptor@@3PEAXEA; SecurityDescriptor
0x18002f1d8  xor     eax, eax
0x18002f1da  mov     [rbp+var_28.Privilege.Attributes], eax
0x18002f1dd  xorps   xmm0, xmm0
0x18002f1e0  mov     [rbp+var_3C], eax
0x18002f1e3  mov     r8d, edi; DesiredAccess
0x18002f1e6  mov     [rbp+var_40], eax
0x18002f1e9  lea     rax, [rbp+var_40]
0x18002f1ed  mov     [rsp+80h+AccessStatus], rax; AccessStatus
0x18002f1f2  lea     rax, [rbp+var_3C]
0x18002f1f6  mov     [rsp+80h+GrantedAccess], rax; GrantedAccess
0x18002f1fb  lea     rax, [rbp+var_38]
0x18002f1ff  mov     [rsp+80h+ReturnLength], rax; ReturnLength
0x18002f204  lea     rax, [rbp+var_28]
0x18002f208  mov     [rsp+80h+PrivilegeSet], rax; PrivilegeSet
0x18002f20d  movups  xmmword ptr [rbp+var_28.PrivilegeCount], xmm0
0x18002f211  mov     [rbp+var_38], 14h
0x18002f218  call    cs:__imp_NtAccessCheck
0x18002f21f  nop     dword ptr [rax+rax+00h]
0x18002f224  mov     rcx, [rbp+TokenHandle]; Handle
0x18002f228  test    eax, eax
0x18002f22a  mov     ebx, eax
0x18002f22c  cmovz   ebx, [rbp+var_40]
0x18002f230  call    cs:__imp_NtClose
0x18002f237  nop     dword ptr [rax+rax+00h]
0x18002f23c  call    cs:__imp_RpcRevertToSelf
0x18002f243  nop     dword ptr [rax+rax+00h]
0x18002f248  test    eax, eax
0x18002f24a  jnz     short loc_18002F253
0x18002f24c  mov     ecx, ebx
0x18002f24e  call    NetpNtStatusToApiStatus
0x18002f253  mov     rcx, [rbp+var_10]
0x18002f257  xor     rcx, rsp; StackCookie
0x18002f25a  call    __security_check_cookie
0x18002f25f  lea     r11, [rsp+80h+var_s0]
0x18002f267  mov     rbx, [r11+18h]
0x18002f26b  mov     rdi, [r11+20h]
0x18002f26f  mov     rsp, r11
0x18002f272  pop     rbp
0x18002f273  retn
```
