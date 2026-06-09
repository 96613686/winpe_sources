# ProcessGroupPolicyCompleted

- ea: `0x180011da0`
- end: `0x180011de7`
- name: `ProcessGroupPolicyCompleted`
- size: `71`
- prototype: `DWORD __stdcall(REFGPEXTENSIONID extensionId, ASYNCCOMPLETIONHANDLE pAsyncHandle, DWORD dwStatus)`
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x18000e9c0`
- `0x180011da0`

## import_xrefs

- `ext-ms-win-profile-userenv-l1-1-0!ProcessGroupPolicyCompletedWorker` at `0x180011dca`
- `ext-ms-win-profile-userenv-l1-1-0!ProcessGroupPolicyCompletedWorker` at `0x180011dca`

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
0x180011da0  mov     [rsp+arg_0], rbx
0x180011da5  mov     [rsp+arg_8], rsi
0x180011daa  push    rdi
0x180011dab  sub     rsp, 20h
0x180011daf  mov     ebx, r8d
0x180011db2  mov     rdi, rdx
0x180011db5  mov     rsi, rcx
0x180011db8  call    IsDeleteLinkFileWorkerPresent
0x180011dbd  test    al, al
0x180011dbf  jz      short loc_180011DD2
0x180011dc1  mov     r8d, ebx
0x180011dc4  mov     rdx, rdi
0x180011dc7  mov     rcx, rsi
0x180011dca  call    cs:__imp_ProcessGroupPolicyCompletedWorker
0x180011dd0  jmp     short loc_180011DD7
0x180011dd2  mov     eax, 7Fh
0x180011dd7  mov     rbx, [rsp+28h+arg_0]
0x180011ddc  mov     rsi, [rsp+28h+arg_8]
0x180011de1  add     rsp, 20h
0x180011de5  pop     rdi
0x180011de6  retn
```
