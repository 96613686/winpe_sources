# CreateDirectoryJunctionsForSystem

- ea: `0x180012a40`
- end: `0x180012a68`
- name: `CreateDirectoryJunctionsForSystem`
- size: `40`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `reparse_path`

## callees

- `0x18000f670`
- `0x180012a40`

## import_xrefs

- `ext-ms-win-profile-userenv-l1-1-0!CreateDirectoryJunctionsForSystemWorker` at `0x180012a51`

## pseudocode

```c
__int64 CreateDirectoryJunctionsForSystem()
{
  if ( (unsigned __int8)IsDeleteLinkFileWorkerPresent() )
    return CreateDirectoryJunctionsForSystemWorker();
  else
    return 2147500033LL;
}

```

## disassembly

```asm
0x180012a40  sub     rsp, 28h
0x180012a44  call    IsDeleteLinkFileWorkerPresent
0x180012a49  test    al, al
0x180012a4b  jz      short loc_180012A5D
0x180012a4d  add     rsp, 28h
0x180012a51  jmp     cs:__imp_CreateDirectoryJunctionsForSystemWorker
0x180012a5d  mov     eax, 80004001h
0x180012a62  add     rsp, 28h
0x180012a66  retn
```
