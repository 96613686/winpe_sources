# CIlKernel32::DeleteFileW(ushort const *)

- ea: `0x18000e570`
- end: `0x18000e57a`
- name: `?DeleteFileW@CIlKernel32@@UEAAHPEBG@Z`
- size: `10`
- prototype: `__int64 __fastcall(CIlKernel32 *__hidden this, const unsigned __int16 *)`
- caller_count: `0`
- callee_count: `0`
- tags: `file_ops`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x18000e573`

## pseudocode

```c
BOOL __fastcall CIlKernel32::DeleteFileW(CIlKernel32 *this, const unsigned __int16 *a2)
{
  return DeleteFileW(a2);
}

```

## disassembly

```asm
0x18000e570  mov     rcx, rdx
0x18000e573  jmp     cs:__imp_DeleteFileW
```
