# SmpConfigureDosDevices

- ea: `0x140013340`
- end: `0x14001335c`
- name: `SmpConfigureDosDevices`
- size: `28`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config`

## callees

- `0x1400182cc`

## pseudocode

```c
__int64 __fastcall SmpConfigureDosDevices(
        const WCHAR *a1,
        __int64 a2,
        const WCHAR *a3,
        __int64 a4,
        __int64 a5,
        struct _UNICODE_STRING **a6)
{
  return SmpSaveRegistryValue(a6, a1, a3, 1, 0);
}

```

## disassembly

```asm
0x140013340  mov     rdx, rcx
0x140013343  mov     [rsp+arg_20], 0
0x14001334c  mov     rcx, [rsp+arg_28]
0x140013351  mov     r9d, 1
0x140013357  jmp     SmpSaveRegistryValue
```
