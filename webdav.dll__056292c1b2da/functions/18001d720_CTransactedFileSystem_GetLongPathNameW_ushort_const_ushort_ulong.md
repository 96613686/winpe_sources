# CTransactedFileSystem::GetLongPathNameW(ushort const *,ushort *,ulong)

- ea: `0x18001d720`
- end: `0x18001d73d`
- name: `?GetLongPathNameW@CTransactedFileSystem@@UEAAKPEBGPEAGK@Z`
- size: `29`
- prototype: `unsigned int __fastcall(CTransactedFileSystem *__hidden this, const unsigned __int16 *, unsigned __int16 *, unsigned int)`
- caller_count: `0`
- callee_count: `0`
- tags: ``

## import_xrefs

- `KERNEL32!GetLongPathNameTransactedW` at `0x18001d736`

## pseudocode

```c
DWORD __fastcall CTransactedFileSystem::GetLongPathNameW(
        HANDLE *this,
        const unsigned __int16 *a2,
        unsigned __int16 *a3,
        DWORD a4)
{
  return GetLongPathNameTransactedW(a2, a3, a4, this[1]);
}

```

## disassembly

```asm
0x18001d720  mov     eax, r9d
0x18001d723  mov     r10, r8
0x18001d726  mov     r9, [rcx+8]
0x18001d72a  mov     r11, rdx
0x18001d72d  mov     r8d, eax
0x18001d730  mov     rdx, r10
0x18001d733  mov     rcx, r11
0x18001d736  jmp     cs:__imp_GetLongPathNameTransactedW
```
