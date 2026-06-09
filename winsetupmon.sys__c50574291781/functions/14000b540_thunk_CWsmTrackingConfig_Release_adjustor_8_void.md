# [thunk]:CWsmTrackingConfig::Release`adjustor{8}' (void)

- ea: `0x14000b540`
- end: `0x14000b549`
- name: `?Release@CWsmTrackingConfig@@W7EAAXXZ`
- size: `9`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config`

## callees

- `0x14000b500`

## pseudocode

```c
void __fastcall CWsmTrackingConfig::Release(__int64 a1)
{
  CWsmTrackingConfig::Release((CWsmTrackingConfig *)(a1 - 8));
}

```

## disassembly

```asm
0x14000b540  sub     rcx, 8; P
0x14000b544  jmp     ?Release@CWsmTrackingConfig@@UEAAXXZ; CWsmTrackingConfig::Release(void)
```
