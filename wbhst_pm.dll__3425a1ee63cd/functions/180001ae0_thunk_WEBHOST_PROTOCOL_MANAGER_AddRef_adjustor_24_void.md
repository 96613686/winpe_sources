# [thunk]:WEBHOST_PROTOCOL_MANAGER::AddRef`adjustor{24}' (void)

- ea: `0x180001ae0`
- end: `0x180001ae9`
- name: `?AddRef@WEBHOST_PROTOCOL_MANAGER@@WBI@EAAKXZ`
- size: `9`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180001aa0`

## pseudocode

```c
__int64 __fastcall WEBHOST_PROTOCOL_MANAGER::AddRef(__int64 a1)
{
  return WEBHOST_PROTOCOL_MANAGER::AddRef((WEBHOST_PROTOCOL_MANAGER *)(a1 - 24));
}

```

## disassembly

```asm
0x180001ae0  sub     rcx, 18h; this
0x180001ae4  jmp     ?AddRef@WEBHOST_PROTOCOL_MANAGER@@UEAAKXZ; WEBHOST_PROTOCOL_MANAGER::AddRef(void)
```
