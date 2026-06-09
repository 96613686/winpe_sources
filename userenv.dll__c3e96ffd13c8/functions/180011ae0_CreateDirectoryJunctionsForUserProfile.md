# CreateDirectoryJunctionsForUserProfile

- ea: `0x180011ae0`
- end: `0x180011b0c`
- name: `CreateDirectoryJunctionsForUserProfile`
- size: `44`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `reparse_path`

## callees

- `0x18000e9c0`
- `0x180011ae0`

## import_xrefs

- `ext-ms-win-profile-userenv-l1-1-0!CreateDirectoryJunctionsForUserProfileWorker` at `0x180011afa`

## pseudocode

```c
__int64 __fastcall CreateDirectoryJunctionsForUserProfile(__int64 a1)
{
  if ( (unsigned __int8)IsDeleteLinkFileWorkerPresent() )
    return CreateDirectoryJunctionsForUserProfileWorker(a1);
  else
    return 2147500033LL;
}

```

## disassembly

```asm
0x180011ae0  push    rbx
0x180011ae2  sub     rsp, 20h
0x180011ae6  mov     rbx, rcx
0x180011ae9  call    IsDeleteLinkFileWorkerPresent
0x180011aee  test    al, al
0x180011af0  jz      short loc_180011B01
0x180011af2  mov     rcx, rbx
0x180011af5  add     rsp, 20h
0x180011af9  pop     rbx
0x180011afa  jmp     cs:__imp_CreateDirectoryJunctionsForUserProfileWorker
0x180011b01  mov     eax, 80004001h
0x180011b06  add     rsp, 20h
0x180011b0a  pop     rbx
0x180011b0b  retn
```
