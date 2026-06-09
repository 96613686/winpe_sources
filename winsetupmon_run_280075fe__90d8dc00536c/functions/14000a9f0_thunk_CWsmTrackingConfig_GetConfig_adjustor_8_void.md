# [thunk]:CWsmTrackingConfig::GetConfig`adjustor{8}' (void)

- ea: `0x14000a9f0`
- end: `0x14000a9f9`
- name: `?GetConfig@CWsmTrackingConfig@@W7EBAQEAU_WSM_TRACKING_CONFIG@@XZ`
- size: `9`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config`

## callees

- `0x14000a9c0`

## pseudocode

```c
struct _WSM_TRACKING_CONFIG *__fastcall CWsmTrackingConfig::GetConfig(__int64 a1)
{
  return CWsmTrackingConfig::GetConfig((CWsmTrackingConfig *)(a1 - 8));
}

```

## disassembly

```asm
0x14000a9f0  sub     rcx, 8; this
0x14000a9f4  jmp     ?GetConfig@CWsmTrackingConfig@@UEBAQEAU_WSM_TRACKING_CONFIG@@XZ; CWsmTrackingConfig::GetConfig(void)
```
