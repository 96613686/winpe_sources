# CTransactedFileSystem::RemoveDirectoryW(ushort const *)

- ea: `0x18001d7a0`
- end: `0x18001d7b1`
- name: `?RemoveDirectoryW@CTransactedFileSystem@@UEAAHPEBG@Z`
- size: `17`
- prototype: `__int64 __fastcall(CTransactedFileSystem *__hidden this, const unsigned __int16 *)`
- caller_count: `0`
- callee_count: `0`
- tags: `file_ops`

## import_xrefs

- `KERNEL32!RemoveDirectoryTransactedW` at `0x18001d7aa`

## pseudocode

```c
BOOL __fastcall CTransactedFileSystem::RemoveDirectoryW(HANDLE *this, const unsigned __int16 *a2)
{
  return RemoveDirectoryTransactedW(a2, this[1]);
}

```

## disassembly

```asm
0x18001d7a0  mov     rax, rdx
0x18001d7a3  mov     rdx, [rcx+8]
0x18001d7a7  mov     rcx, rax
0x18001d7aa  jmp     cs:__imp_RemoveDirectoryTransactedW
```
