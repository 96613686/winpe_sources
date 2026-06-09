# _CProfileTask::DeletePerUserSearchRootsAndScopeRules_::_1_::dtor$8

- ea: `0x18000dcbc`
- end: `0x18000dcc8`
- name: `_CProfileTask::DeletePerUserSearchRootsAndScopeRules_::_1_::dtor$8`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callees

- `0x180004af8`

## pseudocode

```c
_QWORD *__fastcall CProfileTask::DeletePerUserSearchRootsAndScopeRules_::_1_::dtor_8(__int64 a1, __int64 a2)
{
  return Microsoft::WRL::ComPtr<IWsPlatform>::~ComPtr<IWsPlatform>((_QWORD *)(a2 + 48));
}

```

## disassembly

```asm
0x18000dcbc  lea     rcx, [rdx+30h]
0x18000dcc3  jmp     ??1?$ComPtr@UIWsPlatform@@@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::ComPtr<IWsPlatform>::~ComPtr<IWsPlatform>(void)
```
