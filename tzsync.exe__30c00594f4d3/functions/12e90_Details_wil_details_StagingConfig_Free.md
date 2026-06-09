# Details::wil_details_StagingConfig_Free

- ea: `0x12e90`
- end: `0x12eba`
- name: `Details::wil_details_StagingConfig_Free`
- size: `42`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0xa10`

## callees

- `0x12e90`

## pseudocode

```c

```

## disassembly

```asm
0x12e90  ldarg.0
0x12e91  ldfld    bool wil_details_StagingConfig::BufferOwned
0x12e96  brfalse.s loc_12EB9
0x12e98  ldarg.0
0x12e99  ldfld    native int wil_details_StagingConfig::Buffer
0x12e9e  call     void [mscorlib]System.Runtime.InteropServices.Marshal::FreeHGlobal(native int)
0x12ea3  ldarg.0
0x12ea4  ldsfld   native int [mscorlib]System.IntPtr::Zero
0x12ea9  stfld    native int wil_details_StagingConfig::Buffer
0x12eae  ldarg.0
0x12eaf  ldsfld   native int [mscorlib]System.IntPtr::Zero
0x12eb4  stfld    native int wil_details_StagingConfig::Header
0x12eb9  ret
```
