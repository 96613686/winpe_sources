# [thunk]:CWsmLogConfig::GetConfig`adjustor{8}' (void)

- ea: `0x14000a9b0`
- end: `0x14000a9b9`
- name: `?GetConfig@CWsmLogConfig@@W7EBAQEAU_WSM_LOG_CONFIG@@XZ`
- size: `9`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config`

## callees

- `0x14000a980`

## pseudocode

```c
struct _WSM_LOG_CONFIG *__fastcall CWsmLogConfig::GetConfig(__int64 a1)
{
  return CWsmLogConfig::GetConfig((CWsmLogConfig *)(a1 - 8));
}

```

## disassembly

```asm
0x14000a9b0  sub     rcx, 8; this
0x14000a9b4  jmp     ?GetConfig@CWsmLogConfig@@UEBAQEAU_WSM_LOG_CONFIG@@XZ; CWsmLogConfig::GetConfig(void)
```
