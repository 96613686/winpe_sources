# [thunk]:CWsmLogConfig::Release`adjustor{8}' (void)

- ea: `0x14000b4f0`
- end: `0x14000b4f9`
- name: `?Release@CWsmLogConfig@@W7EAAXXZ`
- size: `9`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config`

## callees

- `0x14000b4b0`

## pseudocode

```c
void __fastcall CWsmLogConfig::Release(__int64 a1)
{
  CWsmLogConfig::Release((CWsmLogConfig *)(a1 - 8));
}

```

## disassembly

```asm
0x14000b4f0  sub     rcx, 8; P
0x14000b4f4  jmp     ?Release@CWsmLogConfig@@UEAAXXZ; CWsmLogConfig::Release(void)
```
