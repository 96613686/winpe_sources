# ContainerManager::OnConnectionOpen(std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const &,std::unique_ptr<ContainerStateBase,std::default_delete<ContainerStateBase>> &)

- ea: `0x180098890`
- end: `0x180098aad`
- name: `?OnConnectionOpen@ContainerManager@@MEAAJAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAV?$unique_ptr@VContainerStateBase@@U?$default_delete@VContainerStateBase@@@std@@@3@@Z`
- size: `541`
- prototype: ``
- caller_count: `0`
- callee_count: `8`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callees

- `0x180016250`
- `0x180043878`
- `0x18004f5a0`
- `0x180058750`
- `0x18008d8a8`
- `0x180098890`
- `0x180098c50`
- `0x1800ade50`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800989d5`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800989d5`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800989e4`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180098a4b`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800989e4`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180098a4b`

## string_xrefs

- `0x18009898f`: `<Event xmlns='http://schemas.microsoft.com/win/2004/08/events/event'><System><Provider Name='%%15' Guid='%%16' /><EventID Qualifiers='%%5'>%%4</EventID><Version>%%12</Version><Level>%%1</Level><Task>%%3</Task><Opcode>%%2</Opcode><Keywords>%%6</Keywords><TimeCreated SystemTime='%%7'/><EventRecordID> %%11 </EventRecordID><Correlation ActivityID='%%8' RelatedActivityID='%%14'/><Execution ProcessID='%%9' ThreadID='%%10'/><Channel>%%17</Channel><Computer>%s</Computer><Security UserID='%%13'/><Contain`
- `0x180098980`: `<Event xmlns='http://schemas.microsoft.com/win/2004/08/events/event'><System><Provider Name='%%15' Guid='%%16' /><EventID Qualifiers='%%5'>%%4</EventID><Version>%%12</Version><Level>%%1</Level><Task>%%3</Task><Opcode>%%2</Opcode><Keywords>%%6</Keywords><TimeCreated SystemTime='%%7'/><EventRecordID> %%11 </EventRecordID><Correlation ActivityID='%%8' RelatedActivityID='%%14'/><Execution ProcessID='%%9' ThreadID='%%10'/><Channel>%%17</Channel><Computer>%s</Computer><Security UserID='%%13'/><Contain`

## pseudocode

```c

```
