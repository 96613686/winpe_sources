# _CollectorService::DeleteSubscription_::_1_::dtor$4

- ea: `0x1800205de`
- end: `0x1800205ea`
- name: `_CollectorService::DeleteSubscription_::_1_::dtor$4`
- size: `12`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `service_task`

## callees

- `0x1800024f0`

## pseudocode

```c
__int64 __fastcall CollectorService::DeleteSubscription_::_1_::dtor_4(__int64 a1, __int64 a2)
{
  return wmi::ScopeGuardImpl0<long (*)(void)>::~ScopeGuardImpl0<long (*)(void)>(a2 + 120);
}

```

## disassembly

```asm
0x1800205de  lea     rcx, [rdx+78h]
0x1800205e5  jmp     ??1?$ScopeGuardImpl0@P6AJXZ@wmi@@QEAA@XZ; wmi::ScopeGuardImpl0<long (*)(void)>::~ScopeGuardImpl0<long (*)(void)>(void)
```
