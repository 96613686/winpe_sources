# CTransactedFileSystem::GetCompressedFileSizeW(ushort const *,ulong *)

- ea: `0x18001d6a0`
- end: `0x18001d6b7`
- name: `?GetCompressedFileSizeW@CTransactedFileSystem@@UEAAKPEBGPEAK@Z`
- size: `23`
- prototype: `unsigned int __fastcall(CTransactedFileSystem *__hidden this, const unsigned __int16 *, unsigned int *)`
- caller_count: `0`
- callee_count: `0`
- tags: `broker_com_uri`

## import_xrefs

- `KERNEL32!GetCompressedFileSizeTransactedW` at `0x18001d6b0`

## pseudocode

```c
DWORD __fastcall CTransactedFileSystem::GetCompressedFileSizeW(
        HANDLE *this,
        const unsigned __int16 *a2,
        unsigned int *a3)
{
  return GetCompressedFileSizeTransactedW(a2, a3, this[1]);
}

```

## disassembly

```asm
0x18001d6a0  mov     rax, r8
0x18001d6a3  mov     r9, rdx
0x18001d6a6  mov     r8, [rcx+8]
0x18001d6aa  mov     rdx, rax
0x18001d6ad  mov     rcx, r9
0x18001d6b0  jmp     cs:__imp_GetCompressedFileSizeTransactedW
```
