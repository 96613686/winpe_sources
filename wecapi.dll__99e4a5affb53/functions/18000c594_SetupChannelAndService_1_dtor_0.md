# _SetupChannelAndService_::_1_::dtor$0

- ea: `0x18000c594`
- end: `0x18000c5a0`
- name: `_SetupChannelAndService_::_1_::dtor$0`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, installer_update`

## callees

- `0x18000625c`

## pseudocode

```c
__int64 __fastcall SetupChannelAndService_::_1_::dtor_0(__int64 a1, __int64 a2)
{
  return std::vector<unsigned char>::_Tidy(a2 + 184);
}

```

## disassembly

```asm
0x18000c594  lea     rcx, [rdx+0B8h]
0x18000c59b  jmp     ?_Tidy@?$vector@EV?$allocator@E@std@@@std@@IEAAXXZ; std::vector<uchar>::_Tidy(void)
```
