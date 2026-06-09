# CIlKernel32::GetTempPathW(ulong,ushort *)

- ea: `0x18000ea50`
- end: `0x18000ea5c`
- name: `?GetTempPathW@CIlKernel32@@UEAAKKPEAG@Z`
- size: `12`
- prototype: `unsigned int __fastcall(CIlKernel32 *__hidden this, unsigned int, unsigned __int16 *)`
- caller_count: `0`
- callee_count: `0`
- tags: ``

## import_xrefs

- `api-ms-win-core-file-l1-2-0!GetTempPathW` at `0x18000ea55`

## pseudocode

```c
DWORD __fastcall CIlKernel32::GetTempPathW(CIlKernel32 *this, DWORD a2, unsigned __int16 *a3)
{
  return GetTempPathW(a2, a3);
}

```

## disassembly

```asm
0x18000ea50  mov     ecx, edx
0x18000ea52  mov     rdx, r8
0x18000ea55  jmp     cs:__imp_GetTempPathW
```
