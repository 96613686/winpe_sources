# GetAppContainerFolderPath

- ea: `0x180008980`
- end: `0x1800089be`
- name: `GetAppContainerFolderPath`
- size: `62`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x180008980`
- `0x18000f670`

## import_xrefs

- `ext-ms-win-profile-userenv-l1-1-0!GetAppContainerFolderPathWorker` at `0x18000899f`
- `ext-ms-win-profile-userenv-l1-1-0!GetAppContainerFolderPathWorker` at `0x18000899f`

## pseudocode

```c
__int64 __fastcall GetAppContainerFolderPath(__int64 a1, __int64 a2)
{
  if ( (unsigned __int8)IsDeleteLinkFileWorkerPresent() )
    return GetAppContainerFolderPathWorker(a1, a2);
  else
    return 2147500033LL;
}

```

## disassembly

```asm
0x180008980  mov     [rsp+arg_0], rbx
0x180008985  push    rdi
0x180008986  sub     rsp, 20h
0x18000898a  mov     rbx, rdx
0x18000898d  mov     rdi, rcx
0x180008990  call    IsDeleteLinkFileWorkerPresent
0x180008995  test    al, al
0x180008997  jz      short loc_1800089B7
0x180008999  mov     rdx, rbx
0x18000899c  mov     rcx, rdi
0x18000899f  call    cs:__imp_GetAppContainerFolderPathWorker
0x1800089a6  nop     dword ptr [rax+rax+00h]
0x1800089ab  mov     rbx, [rsp+28h+arg_0]
0x1800089b0  add     rsp, 20h
0x1800089b4  pop     rdi
0x1800089b5  retn
0x1800089b7  mov     eax, 80004001h
0x1800089bc  jmp     short loc_1800089AB
```
