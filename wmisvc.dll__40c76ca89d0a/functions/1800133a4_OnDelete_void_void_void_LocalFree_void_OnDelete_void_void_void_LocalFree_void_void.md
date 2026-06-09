# OnDelete<void *,void * (*)(void *),&LocalFree(void *)>::~OnDelete<void *,void * (*)(void *),&LocalFree(void *)>(void)

- ea: `0x1800133a4`
- end: `0x1800133b7`
- name: `??1?$OnDelete@PEAXP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z@@QEAA@XZ`
- size: `19`
- prototype: `HLOCAL __fastcall(HLOCAL *)`
- caller_count: `1`
- callee_count: `0`
- tags: ``

## callers

- `0x18001e9af`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800133ab`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800133ab`

## pseudocode

```c
HLOCAL __fastcall OnDelete<void *,void * (*)(void *),&void * LocalFree(void *)>::~OnDelete<void *,void * (*)(void *),&void * LocalFree(void *)>(
        HLOCAL *a1)
{
  return LocalFree(*a1);
}

```

## disassembly

```asm
0x1800133a4  sub     rsp, 28h
0x1800133a8  mov     rcx, [rcx]; hMem
0x1800133ab  call    cs:__imp_LocalFree
0x1800133b1  nop
0x1800133b2  add     rsp, 28h
0x1800133b6  retn
```
