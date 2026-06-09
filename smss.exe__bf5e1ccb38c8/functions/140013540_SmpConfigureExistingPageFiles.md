# SmpConfigureExistingPageFiles

- ea: `0x140013540`
- end: `0x14001355f`
- name: `SmpConfigureExistingPageFiles`
- size: `31`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config`

## callees

- `0x1400182cc`

## pseudocode

```c
__int64 __fastcall SmpConfigureExistingPageFiles(
        __int64 a1,
        __int64 a2,
        const WCHAR *a3,
        __int64 a4,
        __int64 a5,
        struct _UNICODE_STRING **a6)
{
  return SmpSaveRegistryValue(a6, a3, 0, 1, 0);
}

```

## disassembly

```asm
0x140013540  mov     rcx, [rsp+arg_28]
0x140013545  mov     rdx, r8
0x140013548  xor     r8d, r8d
0x14001354b  mov     [rsp+arg_20], 0
0x140013554  mov     r9d, 1
0x14001355a  jmp     SmpSaveRegistryValue
```
