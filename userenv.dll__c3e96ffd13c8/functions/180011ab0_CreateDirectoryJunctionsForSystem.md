# CreateDirectoryJunctionsForSystem

- ea: `0x180011ab0`
- end: `0x180011ad2`
- name: `CreateDirectoryJunctionsForSystem`
- size: `34`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `reparse_path`

## callees

- `0x18000e9c0`
- `0x180011ab0`

## import_xrefs

- `ext-ms-win-profile-userenv-l1-1-0!CreateDirectoryJunctionsForSystemWorker` at `0x180011ac1`

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
0x180011ab0  sub     rsp, 28h
0x180011ab4  call    IsDeleteLinkFileWorkerPresent
0x180011ab9  test    al, al
0x180011abb  jz      short loc_180011AC8
0x180011abd  add     rsp, 28h
0x180011ac1  jmp     cs:__imp_CreateDirectoryJunctionsForSystemWorker
0x180011ac8  mov     eax, 80004001h
0x180011acd  add     rsp, 28h
0x180011ad1  retn
```
