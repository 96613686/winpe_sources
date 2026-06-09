# pSetupCloseKey

- ea: `0x1800101d8`
- end: `0x1800101e1`
- name: `pSetupCloseKey`
- size: `9`
- prototype: `NTSTATUS __fastcall(unsigned int)`
- caller_count: `8`
- callee_count: `0`
- tags: `loader_planting, installer_update`

## callers

- `0x18000bb04`
- `0x1800101e8`
- `0x1800164e0`
- `0x180016ee8`
- `0x180016f7c`
- `0x180017058`
- `0x1800170f0`
- `0x180017500`

## import_xrefs

- `ntdll!NtClose` at `0x1800101da`

## pseudocode

```c
NTSTATUS __fastcall pSetupCloseKey(unsigned int a1)
{
  return NtClose((HANDLE)a1);
}

```

## disassembly

```asm
0x1800101d8  mov     ecx, ecx
0x1800101da  jmp     cs:__imp_NtClose
```
