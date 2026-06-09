# _CProfileNotifyHandler::OnCreate_::_1_::dtor$1

- ea: `0x18000dd4c`
- end: `0x18000dd58`
- name: `_CProfileNotifyHandler::OnCreate_::_1_::dtor$1`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, service_task`

## callees

- `0x180004cbc`

## pseudocode

```c
__int64 __fastcall CProfileNotifyHandler::OnCreate_::_1_::dtor_1(__int64 a1, __int64 a2)
{
  return std::unique_ptr<CProfileTask_OnCreate>::~unique_ptr<CProfileTask_OnCreate>((__int64 (__fastcall ****)(_QWORD, __int64))(a2 + 32));
}

```

## disassembly

```asm
0x18000dd4c  lea     rcx, [rdx+20h]
0x18000dd53  jmp     ??1?$unique_ptr@VCProfileTask_OnCreate@@U?$default_delete@VCProfileTask_OnCreate@@@std@@@std@@QEAA@XZ; std::unique_ptr<CProfileTask_OnCreate>::~unique_ptr<CProfileTask_OnCreate>(void)
```
