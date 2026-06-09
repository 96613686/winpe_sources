# _CProfileTask::DeletePerUserSearchRootsAndScopeRules_::_1_::dtor$1

- ea: `0x18000dc50`
- end: `0x18000dc5c`
- name: `_CProfileTask::DeletePerUserSearchRootsAndScopeRules_::_1_::dtor$1`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callees

- `0x180004ad4`

## pseudocode

```c
__int64 __fastcall CProfileTask::DeletePerUserSearchRootsAndScopeRules_::_1_::dtor_1(__int64 a1, __int64 a2)
{
  return ATL::CComPtr<ISearchCrawlScopeManager>::~CComPtr<ISearchCrawlScopeManager>((__int64 *)(a2 + 96));
}

```

## disassembly

```asm
0x18000dc50  lea     rcx, [rdx+60h]
0x18000dc57  jmp     ??1?$CComPtr@UISearchCrawlScopeManager@@@ATL@@QEAA@XZ; ATL::CComPtr<ISearchCrawlScopeManager>::~CComPtr<ISearchCrawlScopeManager>(void)
```
