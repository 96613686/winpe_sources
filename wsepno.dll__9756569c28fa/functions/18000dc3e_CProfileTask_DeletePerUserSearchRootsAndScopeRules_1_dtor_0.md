# _CProfileTask::DeletePerUserSearchRootsAndScopeRules_::_1_::dtor$0

- ea: `0x18000dc3e`
- end: `0x18000dc4a`
- name: `_CProfileTask::DeletePerUserSearchRootsAndScopeRules_::_1_::dtor$0`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callees

- `0x180004ad4`

## pseudocode

```c
__int64 __fastcall CProfileTask::DeletePerUserSearchRootsAndScopeRules_::_1_::dtor_0(__int64 a1, __int64 a2)
{
  return ATL::CComPtr<ISearchCrawlScopeManager>::~CComPtr<ISearchCrawlScopeManager>((__int64 *)(a2 + 104));
}

```

## disassembly

```asm
0x18000dc3e  lea     rcx, [rdx+68h]
0x18000dc45  jmp     ??1?$CComPtr@UISearchCrawlScopeManager@@@ATL@@QEAA@XZ; ATL::CComPtr<ISearchCrawlScopeManager>::~CComPtr<ISearchCrawlScopeManager>(void)
```
