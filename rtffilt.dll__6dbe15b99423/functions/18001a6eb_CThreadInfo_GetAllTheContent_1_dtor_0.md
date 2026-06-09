# _CThreadInfo::GetAllTheContent_::_1_::dtor$0

- ea: `0x18001a6eb`
- end: `0x18001a6f7`
- name: `_CThreadInfo::GetAllTheContent_::_1_::dtor$0`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x18000fd60`

## pseudocode

```c
__int64 __fastcall CThreadInfo::GetAllTheContent_::_1_::dtor_0(__int64 a1, __int64 a2)
{
  return std::shared_ptr<std::vector<winrt::com_ptr<IStream>>>::~shared_ptr<std::vector<winrt::com_ptr<IStream>>>(*(_QWORD *)(a2 + 248));
}

```

## disassembly

```asm
0x18001a6eb  mov     rcx, [rdx+0F8h]
0x18001a6f2  jmp     ??1?$shared_ptr@V?$vector@U?$com_ptr@UIStream@@@winrt@@V?$allocator@U?$com_ptr@UIStream@@@winrt@@@std@@@std@@@std@@QEAA@XZ; std::shared_ptr<std::vector<winrt::com_ptr<IStream>>>::~shared_ptr<std::vector<winrt::com_ptr<IStream>>>(void)
```
