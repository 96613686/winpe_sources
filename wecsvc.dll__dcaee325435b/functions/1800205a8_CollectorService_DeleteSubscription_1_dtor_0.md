# _CollectorService::DeleteSubscription_::_1_::dtor$0

- ea: `0x1800205a8`
- end: `0x1800205b4`
- name: `_CollectorService::DeleteSubscription_::_1_::dtor$0`
- size: `12`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `service_task`

## callees

- `0x180003b50`

## pseudocode

```c
__int64 __fastcall CollectorService::DeleteSubscription_::_1_::dtor_0(__int64 a1, __int64 a2)
{
  return std::vector<std::wstring>::~vector<std::wstring>(a2 + 144);
}

```

## disassembly

```asm
0x1800205a8  lea     rcx, [rdx+90h]
0x1800205af  jmp     ??1?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@QEAA@XZ; std::vector<std::wstring>::~vector<std::wstring>(void)
```
