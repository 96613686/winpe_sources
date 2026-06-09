# CFileSystem::DeleteFileW(ushort const *)

- ea: `0x18001d960`
- end: `0x18001d96a`
- name: `?DeleteFileW@CFileSystem@@UEAAHPEBG@Z`
- size: `10`
- prototype: `__int64 __fastcall(CFileSystem *__hidden this, const unsigned __int16 *)`
- caller_count: `0`
- callee_count: `0`
- tags: `file_ops`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x18001d963`

## pseudocode

```c
BOOL __fastcall CFileSystem::DeleteFileW(CFileSystem *this, const unsigned __int16 *a2)
{
  return DeleteFileW(a2);
}

```

## disassembly

```asm
0x18001d960  mov     rcx, rdx
0x18001d963  jmp     cs:__imp_DeleteFileW
```
