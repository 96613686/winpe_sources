# CIlKernel32::GetShortPathNameW(ushort const *,ushort *,ulong)

- ea: `0x18000e9e0`
- end: `0x18000e9f3`
- name: `?GetShortPathNameW@CIlKernel32@@UEAAKPEBGPEAGK@Z`
- size: `19`
- prototype: `unsigned int __fastcall(CIlKernel32 *__hidden this, const unsigned __int16 *, unsigned __int16 *, unsigned int)`
- caller_count: `0`
- callee_count: `0`
- tags: ``

## import_xrefs

- `api-ms-win-core-file-l1-1-0!GetShortPathNameW` at `0x18000e9ec`

## pseudocode

```c
DWORD __fastcall CIlKernel32::GetShortPathNameW(
        CIlKernel32 *this,
        const unsigned __int16 *a2,
        unsigned __int16 *a3,
        DWORD a4)
{
  return GetShortPathNameW(a2, a3, a4);
}

```

## disassembly

```asm
0x18000e9e0  mov     rax, r8
0x18000e9e3  mov     rcx, rdx
0x18000e9e6  mov     rdx, rax
0x18000e9e9  mov     r8d, r9d
0x18000e9ec  jmp     cs:__imp_GetShortPathNameW
```
