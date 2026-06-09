# _CollectorService::DeleteSubscription_::_1_::dtor$5

- ea: `0x1800205f0`
- end: `0x1800205fc`
- name: `_CollectorService::DeleteSubscription_::_1_::dtor$5`
- size: `12`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `service_task`

## callees

- `0x180003b34`

## pseudocode

```c
__int64 __fastcall CollectorService::DeleteSubscription_::_1_::dtor_5(__int64 a1, __int64 a2)
{
  return std::wstring::~wstring(a2 + 168, a2);
}

```

## disassembly

```asm
0x1800205f0  lea     rcx, [rdx+0A8h]
0x1800205f7  jmp     ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
```
