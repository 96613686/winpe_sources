# CFileSystem::GetCompressedFileSizeW(ushort const *,ulong *)

- ea: `0x18001da10`
- end: `0x18001da1d`
- name: `?GetCompressedFileSizeW@CFileSystem@@UEAAKPEBGPEAK@Z`
- size: `13`
- prototype: `unsigned int __fastcall(CFileSystem *__hidden this, const unsigned __int16 *, unsigned int *)`
- caller_count: `0`
- callee_count: `0`
- tags: `broker_com_uri`

## import_xrefs

- `api-ms-win-core-file-l1-2-1!GetCompressedFileSizeW` at `0x18001da16`

## pseudocode

```c
DWORD __fastcall CFileSystem::GetCompressedFileSizeW(CFileSystem *this, const unsigned __int16 *a2, unsigned int *a3)
{
  return GetCompressedFileSizeW(a2, a3);
}

```

## disassembly

```asm
0x18001da10  mov     rcx, rdx
0x18001da13  mov     rdx, r8
0x18001da16  jmp     cs:__imp_GetCompressedFileSizeW
```
