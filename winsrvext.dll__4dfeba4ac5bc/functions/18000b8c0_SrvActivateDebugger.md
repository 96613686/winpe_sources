# SrvActivateDebugger

- ea: `0x18000b8c0`
- end: `0x18000b9a2`
- name: `SrvActivateDebugger`
- size: `226`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `authz_impersonation, loader_planting`

## callees

- `0x18000b8c0`

## import_xrefs

- `ntdll!NtAlertThread` at `0x18000b962`
- `ntdll!NtAlertThread` at `0x18000b962`
- `ntdll!DbgUiIssueRemoteBreakin` at `0x18000b94d`
- `ntdll!DbgUiIssueRemoteBreakin` at `0x18000b94d`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18000b8e9`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18000b8e9`
- `CSRSRV!CsrUnlockThread` at `0x18000b975`
- `CSRSRV!CsrUnlockThread` at `0x18000b975`
- `CSRSRV!CsrLockThreadByClientId` at `0x18000b92e`
- `CSRSRV!CsrLockThreadByClientId` at `0x18000b92e`
- `CSRSRV!CsrImpersonateClient` at `0x18000b90a`
- `CSRSRV!CsrImpersonateClient` at `0x18000b90a`
- `CSRSRV!CsrRevertToSelf` at `0x18000b988`
- `CSRSRV!CsrRevertToSelf` at `0x18000b988`

## pseudocode

```c
__int64 __fastcall SrvActivateDebugger(__int64 a1)
{
  NTSTATUS v3; // edi
  __int64 v4; // [rsp+30h] [rbp+8h] BYREF

  v4 = 0;
  if ( *(HANDLE *)(a1 + 64) == NtCurrentTeb()->ClientId.UniqueProcess )
  {
    if ( IsDebuggerPresent() )
      __debugbreak();
    return 0;
  }
  else if ( *(_WORD *)(a1 + 4) != 1 || (unsigned __int8)CsrImpersonateClient(0) )
  {
    v3 = CsrLockThreadByClientId(*(_QWORD *)(a1 + 72), *(_QWORD *)(a1 + 64), &v4);
    if ( v3 >= 0 )
    {
      DbgUiIssueRemoteBreakin(*(HANDLE *)(*(_QWORD *)(v4 + 56) + 80LL));
      v3 = NtAlertThread(*(HANDLE *)(v4 + 64));
      CsrUnlockThread(v4);
    }
    if ( *(_WORD *)(a1 + 4) == 1 )
      CsrRevertToSelf();
    return (unsigned int)v3;
  }
  else
  {
    return 3221225473LL;
  }
}

```

## disassembly

```asm
0x18000b8c0  mov     [rsp+arg_8], rbx
0x18000b8c5  push    rdi
0x18000b8c6  sub     rsp, 20h
0x18000b8ca  mov     [rsp+28h+arg_0], 0
0x18000b8d3  mov     rbx, rcx
0x18000b8d6  mov     rax, gs:30h
0x18000b8df  mov     rdx, [rax+40h]
0x18000b8e3  cmp     [rcx+40h], rdx
0x18000b8e7  jnz     short loc_18000B901
0x18000b8e9  call    cs:__imp_IsDebuggerPresent
0x18000b8f0  nop     dword ptr [rax+rax+00h]
0x18000b8f5  test    eax, eax
0x18000b8f7  jz      short loc_18000B8FA
0x18000b8f9  int     3; Trap to Debugger
0x18000b8fa  xor     eax, eax
0x18000b8fc  jmp     loc_18000B996
0x18000b901  cmp     word ptr [rcx+4], 1
0x18000b906  jnz     short loc_18000B921
0x18000b908  xor     ecx, ecx
0x18000b90a  call    cs:__imp_CsrImpersonateClient
0x18000b911  nop     dword ptr [rax+rax+00h]
0x18000b916  test    al, al
0x18000b918  jnz     short loc_18000B921
0x18000b91a  mov     eax, 0C0000001h
0x18000b91f  jmp     short loc_18000B996
0x18000b921  mov     rdx, [rbx+40h]
0x18000b925  lea     r8, [rsp+28h+arg_0]
0x18000b92a  mov     rcx, [rbx+48h]
0x18000b92e  call    cs:__imp_CsrLockThreadByClientId
0x18000b935  nop     dword ptr [rax+rax+00h]
0x18000b93a  mov     edi, eax
0x18000b93c  test    eax, eax
0x18000b93e  js      short loc_18000B981
0x18000b940  mov     rax, [rsp+28h+arg_0]
0x18000b945  mov     rcx, [rax+38h]
0x18000b949  mov     rcx, [rcx+50h]; Process
0x18000b94d  call    cs:__imp_DbgUiIssueRemoteBreakin
0x18000b954  nop     dword ptr [rax+rax+00h]
0x18000b959  mov     rcx, [rsp+28h+arg_0]
0x18000b95e  mov     rcx, [rcx+40h]; ThreadHandle
0x18000b962  call    cs:__imp_NtAlertThread
0x18000b969  nop     dword ptr [rax+rax+00h]
0x18000b96e  mov     rcx, [rsp+28h+arg_0]
0x18000b973  mov     edi, eax
0x18000b975  call    cs:__imp_CsrUnlockThread
0x18000b97c  nop     dword ptr [rax+rax+00h]
0x18000b981  cmp     word ptr [rbx+4], 1
0x18000b986  jnz     short loc_18000B994
0x18000b988  call    cs:__imp_CsrRevertToSelf
0x18000b98f  nop     dword ptr [rax+rax+00h]
0x18000b994  mov     eax, edi
0x18000b996  mov     rbx, [rsp+28h+arg_8]
0x18000b99b  add     rsp, 20h
0x18000b99f  pop     rdi
0x18000b9a0  retn
```
