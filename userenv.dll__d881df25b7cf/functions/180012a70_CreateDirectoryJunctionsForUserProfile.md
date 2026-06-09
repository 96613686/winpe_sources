# CreateDirectoryJunctionsForUserProfile

- ea: `0x180012a70`
- end: `0x180012aa2`
- name: `CreateDirectoryJunctionsForUserProfile`
- size: `50`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `reparse_path`

## callees

- `0x18000f670`
- `0x180012a70`

## import_xrefs

- `ext-ms-win-profile-userenv-l1-1-0!CreateDirectoryJunctionsForUserProfileWorker` at `0x180012a8a`

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
0x180012a70  push    rbx
0x180012a72  sub     rsp, 20h
0x180012a76  mov     rbx, rcx
0x180012a79  call    IsDeleteLinkFileWorkerPresent
0x180012a7e  test    al, al
0x180012a80  jz      short loc_180012A96
0x180012a82  mov     rcx, rbx
0x180012a85  add     rsp, 20h
0x180012a89  pop     rbx
0x180012a8a  jmp     cs:__imp_CreateDirectoryJunctionsForUserProfileWorker
0x180012a96  mov     eax, 80004001h
0x180012a9b  add     rsp, 20h
0x180012a9f  pop     rbx
0x180012aa0  retn
```
