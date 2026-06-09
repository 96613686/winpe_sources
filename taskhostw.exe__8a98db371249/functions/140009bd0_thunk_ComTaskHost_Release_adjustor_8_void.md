# [thunk]:ComTaskHost::Release`adjustor{8}' (void)

- ea: `0x140009bd0`
- end: `0x140009bd9`
- name: `?Release@ComTaskHost@@W7EAAKXZ`
- size: `9`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callees

- `0x140006d00`

## pseudocode

```c
__int64 __fastcall ComTaskHost::Release(__int64 a1)
{
  return ComTaskHost::Release((ComTaskHost *)(a1 - 8));
}

```

## disassembly

```asm
0x140009bd0  sub     rcx, 8; this
0x140009bd4  jmp     ?Release@ComTaskHost@@UEAAKXZ; ComTaskHost::Release(void)
```
