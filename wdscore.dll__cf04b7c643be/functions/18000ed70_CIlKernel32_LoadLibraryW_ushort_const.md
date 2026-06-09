# CIlKernel32::LoadLibraryW(ushort const *)

- ea: `0x18000ed70`
- end: `0x18000ed7f`
- name: `?LoadLibraryW@CIlKernel32@@UEAAPEAUHINSTANCE__@@PEBG@Z`
- size: `15`
- prototype: `HINSTANCE __fastcall(CIlKernel32 *__hidden this, const unsigned __int16 *)`
- caller_count: `0`
- callee_count: `0`
- tags: `loader_planting`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-1-0!LoadLibraryExW` at `0x18000ed78`

## pseudocode

```c
HINSTANCE __fastcall CIlKernel32::LoadLibraryW(CIlKernel32 *this, const unsigned __int16 *a2)
{
  return LoadLibraryExW(a2, 0, 0);
}

```

## disassembly

```asm
0x18000ed70  mov     rcx, rdx
0x18000ed73  xor     r8d, r8d
0x18000ed76  xor     edx, edx
0x18000ed78  jmp     cs:__imp_LoadLibraryExW
```
