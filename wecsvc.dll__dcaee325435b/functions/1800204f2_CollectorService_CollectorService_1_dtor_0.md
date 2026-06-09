# _CollectorService::CollectorService_::_1_::dtor$0

- ea: `0x1800204f2`
- end: `0x1800204fe`
- name: `_CollectorService::CollectorService_::_1_::dtor$0`
- size: `12`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, service_task`

## callees

- `0x180003ad4`

## pseudocode

```c
__int64 __fastcall CollectorService::CollectorService_::_1_::dtor_0(__int64 a1, __int64 a2)
{
  return wmi::AutoRef<SubscriptionConfigSnapshot>::~AutoRef<SubscriptionConfigSnapshot>(*(_QWORD *)(a2 + 160));
}

```

## disassembly

```asm
0x1800204f2  mov     rcx, [rdx+0A0h]
0x1800204f9  jmp     ??1?$AutoRef@VSubscriptionConfigSnapshot@@@wmi@@QEAA@XZ; wmi::AutoRef<SubscriptionConfigSnapshot>::~AutoRef<SubscriptionConfigSnapshot>(void)
```
