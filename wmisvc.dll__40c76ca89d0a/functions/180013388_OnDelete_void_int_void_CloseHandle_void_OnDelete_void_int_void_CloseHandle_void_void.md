# OnDelete<void *,int (*)(void *),&CloseHandle(void *)>::~OnDelete<void *,int (*)(void *),&CloseHandle(void *)>(void)

- ea: `0x180013388`
- end: `0x18001339b`
- name: `??1?$OnDelete@PEAXP6AHPEAX@Z$1?CloseHandle@@YAH0@Z@@QEAA@XZ`
- size: `19`
- prototype: `BOOL __fastcall(HANDLE *)`
- caller_count: `1`
- callee_count: `0`
- tags: ``

## callers

- `0x18001e906`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001338f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001338f`

## pseudocode

```c
BOOL __fastcall OnDelete<void *,int (*)(void *),&int CloseHandle(void *)>::~OnDelete<void *,int (*)(void *),&int CloseHandle(void *)>(
        HANDLE *a1)
{
  return CloseHandle(*a1);
}

```

## disassembly

```asm
0x180013388  sub     rsp, 28h
0x18001338c  mov     rcx, [rcx]; hObject
0x18001338f  call    cs:__imp_CloseHandle
0x180013395  nop
0x180013396  add     rsp, 28h
0x18001339a  retn
```
