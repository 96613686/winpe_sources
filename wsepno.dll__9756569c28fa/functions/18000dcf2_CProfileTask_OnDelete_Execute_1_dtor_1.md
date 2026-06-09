# _CProfileTask_OnDelete::Execute_::_1_::dtor$1

- ea: `0x18000dcf2`
- end: `0x18000dcfe`
- name: `_CProfileTask_OnDelete::Execute_::_1_::dtor$1`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callees

- `0x180004af8`

## pseudocode

```c
_QWORD *__fastcall CProfileTask_OnDelete::Execute_::_1_::dtor_1(__int64 a1, __int64 a2)
{
  return Microsoft::WRL::ComPtr<IWsPlatform>::~ComPtr<IWsPlatform>((_QWORD *)(a2 + 104));
}

```

## disassembly

```asm
0x18000dcf2  lea     rcx, [rdx+68h]
0x18000dcf9  jmp     ??1?$ComPtr@UIWsPlatform@@@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::ComPtr<IWsPlatform>::~ComPtr<IWsPlatform>(void)
```
