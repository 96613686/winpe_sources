# ScCallerHasTcbPrivilege(void)

- ea: `0x1400254d4`
- end: `0x14002559d`
- name: `?ScCallerHasTcbPrivilege@@YAHXZ`
- size: `201`
- prototype: `int(void)`
- caller_count: `2`
- callee_count: `3`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x140025360`
- `0x1400717a0`

## callees

- `0x1400254d4`
- `0x14004401c`
- `0x1400575b0`

## import_xrefs

- `RPCRT4!RpcImpersonateClient` at `0x14002550b`
- `RPCRT4!RpcImpersonateClient` at `0x14002550b`
- `RPCRT4!RpcRevertToSelf` at `0x140025530`
- `RPCRT4!RpcRevertToSelf` at `0x140025530`
- `ntdll!NtPrivilegeCheck` at `0x140025582`
- `ntdll!NtPrivilegeCheck` at `0x140025582`
- `ntdll!NtOpenThreadToken` at `0x140025526`
- `ntdll!NtOpenThreadToken` at `0x140025526`
- `ntdll!NtClose` at `0x14002555d`
- `ntdll!NtClose` at `0x14002555d`

## pseudocode

```c
_BOOL8 ScCallerHasTcbPrivilege(void)
{
  BOOL v0; // ebx
  RPC_STATUS v1; // eax
  unsigned __int8 Result[8]; // [rsp+20h] [rbp-30h] BYREF
  void *TokenHandle; // [rsp+28h] [rbp-28h] BYREF
  _PRIVILEGE_SET RequiredPrivileges; // [rsp+30h] [rbp-20h] BYREF

  v0 = 0;
  Result[0] = 0;
  TokenHandle = 0;
  memset(&RequiredPrivileges, 0, sizeof(RequiredPrivileges));
  v1 = RpcImpersonateClient(0);
  if ( v1 )
  {
    ScLogImpersonateFailureEvent(v1);
  }
  else
  {
    if ( NtOpenThreadToken((HANDLE)0xFFFFFFFFFFFFFFFELL, 8u, 1u, &TokenHandle) >= 0 )
    {
      RequiredPrivileges.PrivilegeCount = 1;
      RequiredPrivileges.Control = 1;
      RequiredPrivileges.Privilege[0].Luid = (LUID)7LL;
      RequiredPrivileges.Privilege[0].Attributes = 0;
      if ( NtPrivilegeCheck(TokenHandle, &RequiredPrivileges, Result) >= 0 )
        v0 = Result[0] != 0;
    }
    RpcRevertToSelf();
  }
  if ( TokenHandle )
    NtClose(TokenHandle);
  return v0;
}

```

## disassembly

```asm
0x1400254d4  mov     [rsp-8+arg_0], rbx
0x1400254d9  mov     [rsp-8+arg_8], rsi
0x1400254de  push    rbp
0x1400254df  mov     rbp, rsp
0x1400254e2  sub     rsp, 50h
0x1400254e6  mov     rax, cs:__security_cookie
0x1400254ed  xor     rax, rsp
0x1400254f0  mov     [rbp+var_8], rax
0x1400254f4  xor     ebx, ebx
0x1400254f6  xorps   xmm0, xmm0
0x1400254f9  xor     eax, eax
0x1400254fb  mov     [rbp+Result], bl
0x1400254fe  xor     ecx, ecx; BindingHandle
0x140025500  mov     [rbp+TokenHandle], rbx
0x140025504  movups  xmmword ptr [rbp+RequiredPrivileges.PrivilegeCount], xmm0
0x140025508  mov     [rbp+RequiredPrivileges.Privilege.Attributes], eax
0x14002550b  call    cs:__imp_RpcImpersonateClient
0x140025511  test    eax, eax
0x140025513  jnz     short loc_140025594
0x140025515  lea     esi, [rbx+1]
0x140025518  mov     r8b, sil; OpenAsSelf
0x14002551b  lea     r9, [rbp+TokenHandle]; TokenHandle
0x14002551f  lea     edx, [rbx+8]; DesiredAccess
0x140025522  lea     rcx, [rbx-2]; ThreadHandle
0x140025526  call    cs:__imp_NtOpenThreadToken
0x14002552c  test    eax, eax
0x14002552e  jns     short loc_140025565
0x140025530  call    cs:__imp_RpcRevertToSelf
0x140025536  mov     rcx, [rbp+TokenHandle]; Handle
0x14002553a  test    rcx, rcx
0x14002553d  jnz     short loc_14002555D
0x14002553f  mov     eax, ebx
0x140025541  mov     rcx, [rbp+var_8]
0x140025545  xor     rcx, rsp; StackCookie
0x140025548  call    __security_check_cookie
0x14002554d  mov     rbx, [rsp+50h+arg_0]
0x140025552  mov     rsi, [rsp+50h+arg_8]
0x140025557  add     rsp, 50h
0x14002555b  pop     rbp
0x14002555c  retn
0x14002555d  call    cs:__imp_NtClose
0x140025563  jmp     short loc_14002553F
0x140025565  mov     rcx, [rbp+TokenHandle]; ClientToken
0x140025569  lea     r8, [rbp+Result]; Result
0x14002556d  lea     rdx, [rbp+RequiredPrivileges]; RequiredPrivileges
0x140025571  mov     [rbp+RequiredPrivileges.PrivilegeCount], esi
0x140025574  mov     [rbp+RequiredPrivileges.Control], esi
0x140025577  mov     qword ptr [rbp+RequiredPrivileges.Privilege.Luid.LowPart], 7
0x14002557f  mov     [rbp+RequiredPrivileges.Privilege.Attributes], ebx
0x140025582  call    cs:__imp_NtPrivilegeCheck
0x140025588  test    eax, eax
0x14002558a  js      short loc_140025530
0x14002558c  cmp     [rbp+Result], bl
0x14002558f  cmovnz  ebx, esi
0x140025592  jmp     short loc_140025530
0x140025594  mov     ecx, eax; int
0x140025596  call    ?ScLogImpersonateFailureEvent@@YAXJ@Z; ScLogImpersonateFailureEvent(long)
0x14002559b  jmp     short loc_140025536
```
