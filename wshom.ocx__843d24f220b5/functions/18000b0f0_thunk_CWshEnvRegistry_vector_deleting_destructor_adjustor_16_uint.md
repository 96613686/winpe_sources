# [thunk]:CWshEnvRegistry::`vector deleting destructor'`adjustor{16}' (uint)

- ea: `0x18000b0f0`
- end: `0x18000b0f9`
- name: `??_ECWshEnvRegistry@@GBA@EAAPEAXI@Z`
- size: `9`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config`

## callees

- `0x18000b158`

## pseudocode

```c
CWshEnvRegistry *__fastcall CWshEnvRegistry::`vector deleting destructor'(__int64 a1, char a2)
{
  return CWshEnvRegistry::`scalar deleting destructor'((CWshEnvRegistry *)(a1 - 16), a2);
}

```

## disassembly

```asm
0x18000b0f0  sub     rcx, 10h; this
0x18000b0f4  jmp     ??_GCWshEnvRegistry@@EEAAPEAXI@Z; CWshEnvRegistry::`scalar deleting destructor'(uint)
```
