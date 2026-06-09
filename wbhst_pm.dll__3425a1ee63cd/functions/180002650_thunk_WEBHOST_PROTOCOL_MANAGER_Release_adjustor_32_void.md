# [thunk]:WEBHOST_PROTOCOL_MANAGER::Release`adjustor{32}' (void)

- ea: `0x180002650`
- end: `0x180002659`
- name: `?Release@WEBHOST_PROTOCOL_MANAGER@@WCA@EAAKXZ`
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
  return WEBHOST_PROTOCOL_MANAGER::Release((WEBHOST_PROTOCOL_MANAGER *)(a1 - 32));
}

```

## disassembly

```asm
0x180002650  sub     rcx, 20h ; ' '; this
0x180002654  jmp     ?Release@WEBHOST_PROTOCOL_MANAGER@@UEAAKXZ; WEBHOST_PROTOCOL_MANAGER::Release(void)
```
