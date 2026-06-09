# [thunk]:WEBHOST_PROTOCOL_MANAGER::Release`adjustor{40}' (void)

- ea: `0x180002660`
- end: `0x180002669`
- name: `?Release@WEBHOST_PROTOCOL_MANAGER@@WCI@EAAKXZ`
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
  return WEBHOST_PROTOCOL_MANAGER::Release((WEBHOST_PROTOCOL_MANAGER *)(a1 - 40));
}

```

## disassembly

```asm
0x180002660  sub     rcx, 28h ; '('; this
0x180002664  jmp     ?Release@WEBHOST_PROTOCOL_MANAGER@@UEAAKXZ; WEBHOST_PROTOCOL_MANAGER::Release(void)
```
