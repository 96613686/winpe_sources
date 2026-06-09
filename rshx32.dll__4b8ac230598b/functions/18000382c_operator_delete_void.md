# operator delete(void *)

- ea: `0x18000382c`
- end: `0x180003833`
- name: `??3@YAXPEAX@Z`
- size: `7`
- prototype: `HLOCAL __stdcall(HLOCAL hMem)`
- caller_count: `0`
- callee_count: `0`
- tags: `file_ops`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000382c`

## pseudocode

```c
// attributes: thunk
HLOCAL __stdcall operator delete(HLOCAL hMem)
{
  return LocalFree(hMem);
}

```

## disassembly

```asm
0x18000382c  jmp     cs:__imp_LocalFree
```
