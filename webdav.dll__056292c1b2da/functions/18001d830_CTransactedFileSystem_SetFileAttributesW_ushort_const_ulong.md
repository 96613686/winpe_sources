# CTransactedFileSystem::SetFileAttributesW(ushort const *,ulong)

- ea: `0x18001d830`
- end: `0x18001d846`
- name: `?SetFileAttributesW@CTransactedFileSystem@@UEAAHPEBGK@Z`
- size: `22`
- prototype: `__int64 __fastcall(CTransactedFileSystem *__hidden this, const unsigned __int16 *, unsigned int)`
- caller_count: `0`
- callee_count: `0`
- tags: `file_ops`

## import_xrefs

- `KERNEL32!SetFileAttributesTransactedW` at `0x18001d83f`

## pseudocode

```c
BOOL __fastcall CTransactedFileSystem::SetFileAttributesW(HANDLE *this, const unsigned __int16 *a2, DWORD a3)
{
  return SetFileAttributesTransactedW(a2, a3, this[1]);
}

```

## disassembly

```asm
0x18001d830  mov     eax, r8d
0x18001d833  mov     r9, rdx
0x18001d836  mov     r8, [rcx+8]
0x18001d83a  mov     edx, eax
0x18001d83c  mov     rcx, r9
0x18001d83f  jmp     cs:__imp_SetFileAttributesTransactedW
```
