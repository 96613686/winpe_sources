# _CProfileTask_OnDelete::_CleanupCDPLCatalog_::_1_::dtor$0

- ea: `0x18000dcaa`
- end: `0x18000dcb6`
- name: `_CProfileTask_OnDelete::_CleanupCDPLCatalog_::_1_::dtor$0`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callees

- `0x180004af8`

## pseudocode

```c
_QWORD *__fastcall CProfileTask_OnDelete::_CleanupCDPLCatalog_::_1_::dtor_0(__int64 a1, __int64 a2)
{
  return Microsoft::WRL::ComPtr<IWsPlatform>::~ComPtr<IWsPlatform>((_QWORD *)(a2 + 72));
}

```

## disassembly

```asm
0x18000dcaa  lea     rcx, [rdx+48h]
0x18000dcb1  jmp     ??1?$ComPtr@UIWsPlatform@@@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::ComPtr<IWsPlatform>::~ComPtr<IWsPlatform>(void)
```
