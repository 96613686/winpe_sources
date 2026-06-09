# CTransactedFileSystem::DeleteFileW(ushort const *)

- ea: `0x18001d5d0`
- end: `0x18001d5e1`
- name: `?DeleteFileW@CTransactedFileSystem@@UEAAHPEBG@Z`
- size: `17`
- prototype: `__int64 __fastcall(CTransactedFileSystem *__hidden this, const unsigned __int16 *)`
- caller_count: `0`
- callee_count: `0`
- tags: `file_ops`

## import_xrefs

- `KERNEL32!DeleteFileTransactedW` at `0x18001d5da`

## pseudocode

```c
BOOL __fastcall CTransactedFileSystem::DeleteFileW(HANDLE *this, const unsigned __int16 *a2)
{
  return DeleteFileTransactedW(a2, this[1]);
}

```

## disassembly

```asm
0x18001d5d0  mov     rax, rdx
0x18001d5d3  mov     rdx, [rcx+8]
0x18001d5d7  mov     rcx, rax
0x18001d5da  jmp     cs:__imp_DeleteFileTransactedW
```
