# CFileSystem::RemoveDirectoryW(ushort const *)

- ea: `0x18001dad0`
- end: `0x18001dada`
- name: `?RemoveDirectoryW@CFileSystem@@UEAAHPEBG@Z`
- size: `10`
- prototype: `__int64 __fastcall(CFileSystem *__hidden this, const unsigned __int16 *)`
- caller_count: `0`
- callee_count: `0`
- tags: `file_ops`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!RemoveDirectoryW` at `0x18001dad3`

## pseudocode

```c
BOOL __fastcall CFileSystem::RemoveDirectoryW(CFileSystem *this, const unsigned __int16 *a2)
{
  return RemoveDirectoryW(a2);
}

```

## disassembly

```asm
0x18001dad0  mov     rcx, rdx
0x18001dad3  jmp     cs:__imp_RemoveDirectoryW
```
