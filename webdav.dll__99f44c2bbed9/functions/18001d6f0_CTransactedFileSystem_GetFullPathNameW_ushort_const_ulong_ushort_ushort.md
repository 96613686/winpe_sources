# CTransactedFileSystem::GetFullPathNameW(ushort const *,ulong,ushort *,ushort * *)

- ea: `0x18001d6f0`
- end: `0x18001d71a`
- name: `?GetFullPathNameW@CTransactedFileSystem@@UEAAKPEBGKPEAGPEAPEAG@Z`
- size: `42`
- prototype: `unsigned int __fastcall(CTransactedFileSystem *__hidden this, const unsigned __int16 *, unsigned int, unsigned __int16 *, unsigned __int16 **)`
- caller_count: `0`
- callee_count: `0`
- tags: ``

## import_xrefs

- `KERNEL32!GetFullPathNameTransactedW` at `0x18001d713`

## pseudocode

```c
DWORD __fastcall CTransactedFileSystem::GetFullPathNameW(
        HANDLE *this,
        const unsigned __int16 *a2,
        DWORD a3,
        unsigned __int16 *a4,
        unsigned __int16 **a5)
{
  return GetFullPathNameTransactedW(a2, a3, a4, a5, this[1]);
}

```

## disassembly

```asm
0x18001d6f0  push    rbx
0x18001d6f2  mov     rax, [rcx+8]
0x18001d6f6  mov     r10, r9
0x18001d6f9  mov     r9, [rsp+8+arg_20]
0x18001d6fe  mov     r11d, r8d
0x18001d701  mov     rbx, rdx
0x18001d704  mov     [rsp+8+arg_20], rax
0x18001d709  mov     r8, r10
0x18001d70c  mov     edx, r11d
0x18001d70f  mov     rcx, rbx
0x18001d712  pop     rbx
0x18001d713  jmp     cs:__imp_GetFullPathNameTransactedW
```
