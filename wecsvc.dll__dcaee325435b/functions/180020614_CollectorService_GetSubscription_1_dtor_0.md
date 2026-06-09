# _CollectorService::GetSubscription_::_1_::dtor$0

- ea: `0x180020614`
- end: `0x180020620`
- name: `_CollectorService::GetSubscription_::_1_::dtor$0`
- size: `12`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `service_task`

## callees

- `0x1800024f0`

## pseudocode

```c
__int64 __fastcall CollectorService::GetSubscription_::_1_::dtor_0(__int64 a1, __int64 a2)
{
  return wmi::ScopeGuardImpl0<long (*)(void)>::~ScopeGuardImpl0<long (*)(void)>(a2 + 88);
}

```

## disassembly

```asm
0x180020614  lea     rcx, [rdx+58h]
0x18002061b  jmp     ??1?$ScopeGuardImpl0@P6AJXZ@wmi@@QEAA@XZ; wmi::ScopeGuardImpl0<long (*)(void)>::~ScopeGuardImpl0<long (*)(void)>(void)
```
