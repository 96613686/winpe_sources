# CFileSystem::GetFullPathNameW(ushort const *,ulong,ushort *,ushort * *)

- ea: `0x18001da50`
- end: `0x18001da6b`
- name: `?GetFullPathNameW@CFileSystem@@UEAAKPEBGKPEAGPEAPEAG@Z`
- size: `27`
- prototype: `unsigned int __fastcall(CFileSystem *__hidden this, const unsigned __int16 *, unsigned int, unsigned __int16 *, unsigned __int16 **)`
- caller_count: `0`
- callee_count: `0`
- tags: ``

## import_xrefs

- `api-ms-win-core-file-l1-1-0!GetFullPathNameW` at `0x18001da64`

## pseudocode

```c
DWORD __fastcall CFileSystem::GetFullPathNameW(
        CFileSystem *this,
        const unsigned __int16 *a2,
        DWORD a3,
        unsigned __int16 *a4,
        unsigned __int16 **a5)
{
  return GetFullPathNameW(a2, a3, a4, a5);
}

```

## disassembly

```asm
0x18001da50  mov     rax, r9
0x18001da53  mov     r10d, r8d
0x18001da56  mov     r9, [rsp+arg_20]
0x18001da5b  mov     rcx, rdx
0x18001da5e  mov     r8, rax
0x18001da61  mov     edx, r10d
0x18001da64  jmp     cs:__imp_GetFullPathNameW
```
