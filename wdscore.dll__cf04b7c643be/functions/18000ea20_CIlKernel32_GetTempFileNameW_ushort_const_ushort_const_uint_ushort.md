# CIlKernel32::GetTempFileNameW(ushort const *,ushort const *,uint,ushort *)

- ea: `0x18000ea20`
- end: `0x18000ea3b`
- name: `?GetTempFileNameW@CIlKernel32@@UEAAIPEBG0IPEAG@Z`
- size: `27`
- prototype: `unsigned int __fastcall(CIlKernel32 *__hidden this, const unsigned __int16 *, const unsigned __int16 *, unsigned int, unsigned __int16 *)`
- caller_count: `0`
- callee_count: `0`
- tags: ``

## import_xrefs

- `api-ms-win-core-file-l1-1-0!GetTempFileNameW` at `0x18000ea34`

## pseudocode

```c
UINT __fastcall CIlKernel32::GetTempFileNameW(
        CIlKernel32 *this,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        UINT a4,
        unsigned __int16 *a5)
{
  return GetTempFileNameW(a2, a3, a4, a5);
}

```

## disassembly

```asm
0x18000ea20  mov     eax, r9d
0x18000ea23  mov     r10, r8
0x18000ea26  mov     r9, [rsp+arg_20]
0x18000ea2b  mov     rcx, rdx
0x18000ea2e  mov     r8d, eax
0x18000ea31  mov     rdx, r10
0x18000ea34  jmp     cs:__imp_GetTempFileNameW
```
