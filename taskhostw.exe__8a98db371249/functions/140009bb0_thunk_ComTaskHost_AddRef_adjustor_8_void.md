# [thunk]:ComTaskHost::AddRef`adjustor{8}' (void)

- ea: `0x140009bb0`
- end: `0x140009bb9`
- name: `?AddRef@ComTaskHost@@W7EAAKXZ`
- size: `9`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callees

- `0x140006e00`

## pseudocode

```c
__int64 __fastcall ComTaskHost::AddRef(__int64 a1)
{
  return ComTaskHost::AddRef((ComTaskHost *)(a1 - 8));
}

```

## disassembly

```asm
0x140009bb0  sub     rcx, 8; this
0x140009bb4  jmp     ?AddRef@ComTaskHost@@UEAAKXZ; ComTaskHost::AddRef(void)
```
