# CFileSystem::GetLongPathNameW(ushort const *,ushort *,ulong)

- ea: `0x18001da80`
- end: `0x18001da93`
- name: `?GetLongPathNameW@CFileSystem@@UEAAKPEBGPEAGK@Z`
- size: `19`
- prototype: `unsigned int __fastcall(CFileSystem *__hidden this, const unsigned __int16 *, unsigned __int16 *, unsigned int)`
- caller_count: `0`
- callee_count: `0`
- tags: ``

## import_xrefs

- `api-ms-win-core-file-l1-1-0!GetLongPathNameW` at `0x18001da8c`

## pseudocode

```c
DWORD __fastcall CFileSystem::GetLongPathNameW(
        CFileSystem *this,
        const unsigned __int16 *a2,
        unsigned __int16 *a3,
        DWORD a4)
{
  return GetLongPathNameW(a2, a3, a4);
}

```

## disassembly

```asm
0x18001da80  mov     rax, r8
0x18001da83  mov     rcx, rdx
0x18001da86  mov     rdx, rax
0x18001da89  mov     r8d, r9d
0x18001da8c  jmp     cs:__imp_GetLongPathNameW
```
