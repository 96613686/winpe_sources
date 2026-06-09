# CIlKernel32::GetComputerNameW(ushort *,ulong *)

- ea: `0x18000e6f0`
- end: `0x18000e6f9`
- name: `?GetComputerNameW@CIlKernel32@@UEAAHPEAGPEAK@Z`
- size: `9`
- prototype: `__int64 __fastcall(CIlKernel32 *__hidden this, unsigned __int16 *, unsigned int *)`
- caller_count: `0`
- callee_count: `0`
- tags: `broker_com_uri`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetComputerNameExW` at `0x18000e6f2`

## pseudocode

```c
BOOL __fastcall CIlKernel32::GetComputerNameW(CIlKernel32 *this, unsigned __int16 *a2, unsigned int *a3)
{
  return GetComputerNameExW(ComputerNameNetBIOS, a2, a3);
}

```

## disassembly

```asm
0x18000e6f0  xor     ecx, ecx
0x18000e6f2  jmp     cs:__imp_GetComputerNameExW
```
