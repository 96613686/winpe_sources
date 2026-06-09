# CIlKernel32::GetFullPathNameW(ushort const *,ulong,ushort *,ushort * *)

- ea: `0x18000e860`
- end: `0x18000e87b`
- name: `?GetFullPathNameW@CIlKernel32@@UEAAKPEBGKPEAGPEAPEAG@Z`
- size: `27`
- prototype: `unsigned int __fastcall(CIlKernel32 *__hidden this, const unsigned __int16 *, unsigned int, unsigned __int16 *, unsigned __int16 **)`
- caller_count: `0`
- callee_count: `0`
- tags: ``

## import_xrefs

- `api-ms-win-core-file-l1-1-0!GetFullPathNameW` at `0x18000e874`

## pseudocode

```c
DWORD __fastcall CIlKernel32::GetFullPathNameW(
        CIlKernel32 *this,
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
0x18000e860  mov     rax, r9
0x18000e863  mov     r10d, r8d
0x18000e866  mov     r9, [rsp+arg_20]
0x18000e86b  mov     rcx, rdx
0x18000e86e  mov     r8, rax
0x18000e871  mov     edx, r10d
0x18000e874  jmp     cs:__imp_GetFullPathNameW
```
