# [thunk]:WEBHOST_PROTOCOL_MANAGER::AddRef`adjustor{16}' (void)

- ea: `0x180001ad0`
- end: `0x180001ad9`
- name: `?AddRef@WEBHOST_PROTOCOL_MANAGER@@WBA@EAAKXZ`
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
  return WEBHOST_PROTOCOL_MANAGER::AddRef((WEBHOST_PROTOCOL_MANAGER *)(a1 - 16));
}

```

## disassembly

```asm
0x180001ad0  sub     rcx, 10h; this
0x180001ad4  jmp     ?AddRef@WEBHOST_PROTOCOL_MANAGER@@UEAAKXZ; WEBHOST_PROTOCOL_MANAGER::AddRef(void)
```
