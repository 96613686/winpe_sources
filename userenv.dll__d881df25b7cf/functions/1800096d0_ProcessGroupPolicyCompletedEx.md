# ProcessGroupPolicyCompletedEx

- ea: `0x1800096d0`
- end: `0x180009717`
- name: `ProcessGroupPolicyCompletedEx`
- size: `71`
- prototype: `DWORD __stdcall(REFGPEXTENSIONID extensionId, ASYNCCOMPLETIONHANDLE pAsyncHandle, DWORD dwStatus, HRESULT RsopStatus)`
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x1800096d0`
- `0x18000f670`

## import_xrefs

- `ext-ms-win-profile-userenv-l1-1-0!ProcessGroupPolicyCompletedExWorker` at `0x1800096fa`
- `ext-ms-win-profile-userenv-l1-1-0!ProcessGroupPolicyCompletedExWorker` at `0x1800096fa`

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
0x1800096d0  push    rbx
0x1800096d2  push    rbp
0x1800096d3  push    rsi
0x1800096d4  push    rdi
0x1800096d5  sub     rsp, 28h
0x1800096d9  mov     ebx, r9d
0x1800096dc  mov     edi, r8d
0x1800096df  mov     rsi, rdx
0x1800096e2  mov     rbp, rcx
0x1800096e5  call    IsDeleteLinkFileWorkerPresent
0x1800096ea  test    al, al
0x1800096ec  jz      short loc_180009710
0x1800096ee  mov     r9d, ebx
0x1800096f1  mov     r8d, edi
0x1800096f4  mov     rdx, rsi
0x1800096f7  mov     rcx, rbp
0x1800096fa  call    cs:__imp_ProcessGroupPolicyCompletedExWorker
0x180009701  nop     dword ptr [rax+rax+00h]
0x180009706  add     rsp, 28h
0x18000970a  pop     rdi
0x18000970b  pop     rsi
0x18000970c  pop     rbp
0x18000970d  pop     rbx
0x18000970e  retn
0x180009710  mov     eax, 7Fh
0x180009715  jmp     short loc_180009706
```
