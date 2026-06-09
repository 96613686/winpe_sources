# DeriveAppContainerSidFromAppContainerName

- ea: `0x180008450`
- end: `0x180008487`
- name: `DeriveAppContainerSidFromAppContainerName`
- size: `55`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x180008450`
- `0x18000e9c0`

## import_xrefs

- `ext-ms-win-profile-userenv-l1-1-0!DeriveAppContainerSidFromAppContainerNameWorker` at `0x18000846f`
- `ext-ms-win-profile-userenv-l1-1-0!DeriveAppContainerSidFromAppContainerNameWorker` at `0x18000846f`

## pseudocode

```c
__int64 __fastcall DeriveAppContainerSidFromAppContainerName(__int64 a1, __int64 a2)
{
  if ( (unsigned __int8)IsDeleteLinkFileWorkerPresent() )
    return DeriveAppContainerSidFromAppContainerNameWorker(a1, a2);
  else
    return 2147500033LL;
}

```

## disassembly

```asm
0x180008450  mov     [rsp+arg_0], rbx
0x180008455  push    rdi
0x180008456  sub     rsp, 20h
0x18000845a  mov     rbx, rdx
0x18000845d  mov     rdi, rcx
0x180008460  call    IsDeleteLinkFileWorkerPresent
0x180008465  test    al, al
0x180008467  jz      short loc_180008480
0x180008469  mov     rdx, rbx
0x18000846c  mov     rcx, rdi
0x18000846f  call    cs:__imp_DeriveAppContainerSidFromAppContainerNameWorker
0x180008475  mov     rbx, [rsp+28h+arg_0]
0x18000847a  add     rsp, 20h
0x18000847e  pop     rdi
0x18000847f  retn
0x180008480  mov     eax, 80004001h
0x180008485  jmp     short loc_180008475
```
