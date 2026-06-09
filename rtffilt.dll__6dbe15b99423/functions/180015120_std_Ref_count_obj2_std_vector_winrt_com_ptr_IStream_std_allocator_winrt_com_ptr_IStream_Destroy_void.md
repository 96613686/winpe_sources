# std::_Ref_count_obj2<std::vector<winrt::com_ptr<IStream>,std::allocator<winrt::com_ptr<IStream>>>>::_Destroy(void)

- ea: `0x180015120`
- end: `0x180015129`
- name: `?_Destroy@?$_Ref_count_obj2@V?$vector@U?$com_ptr@UIStream@@@winrt@@V?$allocator@U?$com_ptr@UIStream@@@winrt@@@std@@@std@@@std@@EEAAXXZ`
- size: `9`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x18001003c`

## pseudocode

```c
void __fastcall std::_Ref_count_obj2<std::vector<winrt::com_ptr<IStream>>>::_Destroy(__int64 a1)
{
  std::vector<winrt::com_ptr<IStream>>::~vector<winrt::com_ptr<IStream>>(a1 + 16);
}

```

## disassembly

```asm
0x180015120  add     rcx, 10h
0x180015124  jmp     ??1?$vector@U?$com_ptr@UIStream@@@winrt@@V?$allocator@U?$com_ptr@UIStream@@@winrt@@@std@@@std@@QEAA@XZ; std::vector<winrt::com_ptr<IStream>>::~vector<winrt::com_ptr<IStream>>(void)
```
