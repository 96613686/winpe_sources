# ProcessGroupPolicyCompletedEx

- ea: `0x180008e30`
- end: `0x180008e70`
- name: `ProcessGroupPolicyCompletedEx`
- size: `64`
- prototype: `DWORD __stdcall(REFGPEXTENSIONID extensionId, ASYNCCOMPLETIONHANDLE pAsyncHandle, DWORD dwStatus, HRESULT RsopStatus)`
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x180008e30`
- `0x18000e9c0`

## import_xrefs

- `ext-ms-win-profile-userenv-l1-1-0!ProcessGroupPolicyCompletedExWorker` at `0x180008e5a`
- `ext-ms-win-profile-userenv-l1-1-0!ProcessGroupPolicyCompletedExWorker` at `0x180008e5a`

## pseudocode

```c
DWORD __stdcall ProcessGroupPolicyCompletedEx(
        REFGPEXTENSIONID extensionId,
        ASYNCCOMPLETIONHANDLE pAsyncHandle,
        DWORD dwStatus,
        HRESULT RsopStatus)
{
  if ( (unsigned __int8)IsDeleteLinkFileWorkerPresent() )
    return ProcessGroupPolicyCompletedExWorker(extensionId, pAsyncHandle, dwStatus, (unsigned int)RsopStatus);
  else
    return 127;
}

```

## disassembly

```asm
0x180008e30  push    rbx
0x180008e32  push    rbp
0x180008e33  push    rsi
0x180008e34  push    rdi
0x180008e35  sub     rsp, 28h
0x180008e39  mov     ebx, r9d
0x180008e3c  mov     edi, r8d
0x180008e3f  mov     rsi, rdx
0x180008e42  mov     rbp, rcx
0x180008e45  call    IsDeleteLinkFileWorkerPresent
0x180008e4a  test    al, al
0x180008e4c  jz      short loc_180008E69
0x180008e4e  mov     r9d, ebx
0x180008e51  mov     r8d, edi
0x180008e54  mov     rdx, rsi
0x180008e57  mov     rcx, rbp
0x180008e5a  call    cs:__imp_ProcessGroupPolicyCompletedExWorker
0x180008e60  add     rsp, 28h
0x180008e64  pop     rdi
0x180008e65  pop     rsi
0x180008e66  pop     rbp
0x180008e67  pop     rbx
0x180008e68  retn
0x180008e69  mov     eax, 7Fh
0x180008e6e  jmp     short loc_180008E60
```
