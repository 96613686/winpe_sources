# GetAppContainerFolderPath

- ea: `0x1800078d0`
- end: `0x180007907`
- name: `GetAppContainerFolderPath`
- size: `55`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x1800078d0`
- `0x18000e9c0`

## import_xrefs

- `ext-ms-win-profile-userenv-l1-1-0!GetAppContainerFolderPathWorker` at `0x1800078ef`
- `ext-ms-win-profile-userenv-l1-1-0!GetAppContainerFolderPathWorker` at `0x1800078ef`

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
0x1800078d0  mov     [rsp+arg_0], rbx
0x1800078d5  push    rdi
0x1800078d6  sub     rsp, 20h
0x1800078da  mov     rbx, rdx
0x1800078dd  mov     rdi, rcx
0x1800078e0  call    IsDeleteLinkFileWorkerPresent
0x1800078e5  test    al, al
0x1800078e7  jz      short loc_180007900
0x1800078e9  mov     rdx, rbx
0x1800078ec  mov     rcx, rdi
0x1800078ef  call    cs:__imp_GetAppContainerFolderPathWorker
0x1800078f5  mov     rbx, [rsp+28h+arg_0]
0x1800078fa  add     rsp, 20h
0x1800078fe  pop     rdi
0x1800078ff  retn
0x180007900  mov     eax, 80004001h
0x180007905  jmp     short loc_1800078F5
```
