# CFileSystem::SetFileAttributesW(ushort const *,ulong)

- ea: `0x18001dae0`
- end: `0x18001daed`
- name: `?SetFileAttributesW@CFileSystem@@UEAAHPEBGK@Z`
- size: `13`
- prototype: `__int64 __fastcall(CFileSystem *__hidden this, const unsigned __int16 *, unsigned int)`
- caller_count: `0`
- callee_count: `0`
- tags: `file_ops`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x18001dae6`

## pseudocode

```c
BOOL __fastcall CFileSystem::SetFileAttributesW(CFileSystem *this, const unsigned __int16 *a2, DWORD a3)
{
  return SetFileAttributesW(a2, a3);
}

```

## disassembly

```asm
0x18001dae0  mov     rcx, rdx
0x18001dae3  mov     edx, r8d
0x18001dae6  jmp     cs:__imp_SetFileAttributesW
```
