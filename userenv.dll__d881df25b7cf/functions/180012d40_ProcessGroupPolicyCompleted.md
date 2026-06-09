# ProcessGroupPolicyCompleted

- ea: `0x180012d40`
- end: `0x180012d8e`
- name: `ProcessGroupPolicyCompleted`
- size: `78`
- prototype: `DWORD __stdcall(REFGPEXTENSIONID extensionId, ASYNCCOMPLETIONHANDLE pAsyncHandle, DWORD dwStatus)`
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x18000f670`
- `0x180012d40`

## import_xrefs

- `ext-ms-win-profile-userenv-l1-1-0!ProcessGroupPolicyCompletedWorker` at `0x180012d6a`
- `ext-ms-win-profile-userenv-l1-1-0!ProcessGroupPolicyCompletedWorker` at `0x180012d6a`

## pseudocode

```c
DWORD __stdcall ProcessGroupPolicyCompleted(
        REFGPEXTENSIONID extensionId,
        ASYNCCOMPLETIONHANDLE pAsyncHandle,
        DWORD dwStatus)
{
  if ( (unsigned __int8)IsDeleteLinkFileWorkerPresent() )
    return ProcessGroupPolicyCompletedWorker(extensionId, pAsyncHandle, dwStatus);
  else
    return 127;
}

```

## disassembly

```asm
0x180012d40  mov     [rsp+arg_0], rbx
0x180012d45  mov     [rsp+arg_8], rsi
0x180012d4a  push    rdi
0x180012d4b  sub     rsp, 20h
0x180012d4f  mov     ebx, r8d
0x180012d52  mov     rdi, rdx
0x180012d55  mov     rsi, rcx
0x180012d58  call    IsDeleteLinkFileWorkerPresent
0x180012d5d  test    al, al
0x180012d5f  jz      short loc_180012D78
0x180012d61  mov     r8d, ebx
0x180012d64  mov     rdx, rdi
0x180012d67  mov     rcx, rsi
0x180012d6a  call    cs:__imp_ProcessGroupPolicyCompletedWorker
0x180012d71  nop     dword ptr [rax+rax+00h]
0x180012d76  jmp     short loc_180012D7D
0x180012d78  mov     eax, 7Fh
0x180012d7d  mov     rbx, [rsp+28h+arg_0]
0x180012d82  mov     rsi, [rsp+28h+arg_8]
0x180012d87  add     rsp, 20h
0x180012d8b  pop     rdi
0x180012d8c  retn
```
