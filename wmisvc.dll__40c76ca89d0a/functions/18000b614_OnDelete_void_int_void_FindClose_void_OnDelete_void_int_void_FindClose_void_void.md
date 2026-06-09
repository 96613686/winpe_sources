# OnDelete<void *,int (*)(void *),&FindClose(void *)>::~OnDelete<void *,int (*)(void *),&FindClose(void *)>(void)

- ea: `0x18000b614`
- end: `0x18000b627`
- name: `??1?$OnDelete@PEAXP6AHPEAX@Z$1?FindClose@@YAH0@Z@@QEAA@XZ`
- size: `19`
- prototype: `BOOL __fastcall(HANDLE *)`
- caller_count: `1`
- callee_count: `0`
- tags: ``

## callers

- `0x18001e898`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!FindClose` at `0x18000b61b`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x18000b61b`

## pseudocode

```c
BOOL __fastcall OnDelete<void *,int (*)(void *),&int FindClose(void *)>::~OnDelete<void *,int (*)(void *),&int FindClose(void *)>(
        HANDLE *a1)
{
  return FindClose(*a1);
}

```

## disassembly

```asm
0x18000b614  sub     rsp, 28h
0x18000b618  mov     rcx, [rcx]; hFindFile
0x18000b61b  call    cs:__imp_FindClose
0x18000b621  nop
0x18000b622  add     rsp, 28h
0x18000b626  retn
```
