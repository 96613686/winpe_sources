# _CollectorService::CollectorService_::_1_::dtor$1

- ea: `0x180020504`
- end: `0x180020514`
- name: `_CollectorService::CollectorService_::_1_::dtor$1`
- size: `16`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, service_task`

## callees

- `0x180003ad4`

## pseudocode

```c
__int64 __fastcall CollectorService::CollectorService_::_1_::dtor_1(__int64 a1, __int64 a2)
{
  return wmi::AutoRef<SubscriptionConfigSnapshot>::~AutoRef<SubscriptionConfigSnapshot>(*(_QWORD *)(a2 + 160) + 8LL);
}

```

## disassembly

```asm
0x180020504  mov     rcx, [rdx+0A0h]
0x18002050b  add     rcx, 8
0x18002050f  jmp     ??1?$AutoRef@VSubscriptionConfigSnapshot@@@wmi@@QEAA@XZ
```
