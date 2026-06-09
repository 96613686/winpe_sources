# [thunk]:WEBHOST_PROTOCOL_MANAGER::Release`adjustor{8}' (void)

- ea: `0x180002620`
- end: `0x180002629`
- name: `?Release@WEBHOST_PROTOCOL_MANAGER@@W7EAAKXZ`
- size: `9`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x1800025e0`

## pseudocode

```c
__int64 __fastcall WEBHOST_PROTOCOL_MANAGER::Release(__int64 a1)
{
  return WEBHOST_PROTOCOL_MANAGER::Release((WEBHOST_PROTOCOL_MANAGER *)(a1 - 8));
}

```

## disassembly

```asm
0x180002620  sub     rcx, 8; this
0x180002624  jmp     ?Release@WEBHOST_PROTOCOL_MANAGER@@UEAAKXZ; WEBHOST_PROTOCOL_MANAGER::Release(void)
```
