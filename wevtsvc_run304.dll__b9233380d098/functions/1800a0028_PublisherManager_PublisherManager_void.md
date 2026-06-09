# PublisherManager::~PublisherManager(void)

- ea: `0x1800a0028`
- end: `0x1800a00b9`
- name: `??1PublisherManager@@QEAA@XZ`
- size: `145`
- prototype: `void __fastcall(PSRWLOCK SRWLock)`
- caller_count: `2`
- callee_count: `4`
- tags: ``

## callers

- `0x1800a1ea4`
- `0x1800d98ec`

## callees

- `0x1800067a0`
- `0x180017b60`
- `0x1800a00e8`
- `0x1800d2530`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800a006b`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800a006b`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800a0084`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800a0084`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1800a007a`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1800a007a`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800a003a`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800a003a`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800a0047`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800a0047`

## pseudocode

```c
void __fastcall PublisherManager::~PublisherManager(PSRWLOCK SRWLock)
{
  AcquireSRWLockExclusive(SRWLock);
  LOBYTE(SRWLock[15].Ptr) = 1;
  ReleaseSRWLockExclusive(SRWLock);
  utl::map<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>,wmi::AutoRef<PublisherMetadata>,tlx::istring_less_ordinal,utl::allocator<utl::pair<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> const,wmi::AutoRef<PublisherMetadata>>>>::~map<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>,wmi::AutoRef<PublisherMetadata>,tlx::istring_less_ordinal,utl::allocator<utl::pair<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> const,wmi::AutoRef<PublisherMetadata>>>>(&SRWLock[7]);
  utl::_Tree<_GUID,utl::pair<_GUID const,PublisherManager::PublisherCacheNode>,GuidLess,utl::allocator<utl::pair<_GUID const,PublisherManager::PublisherCacheNode>>,0>::clear(&SRWLock[3]);
  SetThreadpoolTimer((PTP_TIMER)SRWLock[2].Ptr, 0, 0, 0);
  WaitForThreadpoolTimerCallbacks((PTP_TIMER)SRWLock[2].Ptr, 1);
  CloseThreadpoolTimer((PTP_TIMER)SRWLock[2].Ptr);
  TlgUnregisterAggregateProvider();
  utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(&SRWLock[11]);
  utl::map<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>,wmi::AutoRef<PublisherMetadata>,tlx::istring_less_ordinal,utl::allocator<utl::pair<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> const,wmi::AutoRef<PublisherMetadata>>>>::~map<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>,wmi::AutoRef<PublisherMetadata>,tlx::istring_less_ordinal,utl::allocator<utl::pair<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> const,wmi::AutoRef<PublisherMetadata>>>>(&SRWLock[7]);
  utl::_Tree<_GUID,utl::pair<_GUID const,PublisherManager::PublisherCacheNode>,GuidLess,utl::allocator<utl::pair<_GUID const,PublisherManager::PublisherCacheNode>>,0>::clear(&SRWLock[3]);
}

```

## disassembly

```asm
0x1800a0028  mov     [rsp+arg_0], rbx
0x1800a002d  mov     [rsp+arg_8], rsi
0x1800a0032  push    rdi
0x1800a0033  sub     rsp, 20h
0x1800a0037  mov     rsi, rcx
0x1800a003a  call    cs:__imp_AcquireSRWLockExclusive
0x1800a0040  mov     byte ptr [rsi+78h], 1
0x1800a0044  mov     rcx, rsi; SRWLock
0x1800a0047  call    cs:__imp_ReleaseSRWLockExclusive
0x1800a004d  lea     rcx, [rsi+38h]
0x1800a0051  call    ??1?$map@V?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@V?$AutoRef@VPublisherMetadata@@@wmi@@Uistring_less_ordinal@tlx@@V?$allocator@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@V?$AutoRef@VPublisherMetadata@@@wmi@@@utl@@@2@@utl@@QEAA@XZ; utl::map<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>,wmi::AutoRef<PublisherMetadata>,tlx::istring_less_ordinal,utl::allocator<utl::pair<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> const,wmi::AutoRef<PublisherMetadata>>>>::~map<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>,wmi::AutoRef<PublisherMetadata>,tlx::istring_less_ordinal,utl::allocator<utl::pair<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> const,wmi::AutoRef<PublisherMetadata>>>>(void)
0x1800a0056  lea     rcx, [rsi+18h]
0x1800a005a  call    ?clear@?$_Tree@U_GUID@@U?$pair@$$CBU_GUID@@UPublisherCacheNode@PublisherManager@@@utl@@VGuidLess@@V?$allocator@U?$pair@$$CBU_GUID@@UPublisherCacheNode@PublisherManager@@@utl@@@3@$0A@@utl@@QEAAXXZ; utl::_Tree<_GUID,utl::pair<_GUID const,PublisherManager::PublisherCacheNode>,GuidLess,utl::allocator<utl::pair<_GUID const,PublisherManager::PublisherCacheNode>>,0>::clear(void)
0x1800a005f  xor     r9d, r9d; msWindowLength
0x1800a0062  xor     r8d, r8d; msPeriod
0x1800a0065  xor     edx, edx; pftDueTime
0x1800a0067  mov     rcx, [rsi+10h]; pti
0x1800a006b  call    cs:__imp_SetThreadpoolTimer
0x1800a0071  mov     edx, 1; fCancelPendingCallbacks
0x1800a0076  mov     rcx, [rsi+10h]; pti
0x1800a007a  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x1800a0080  mov     rcx, [rsi+10h]; pti
0x1800a0084  call    cs:__imp_CloseThreadpoolTimer
0x1800a008a  call    TlgUnregisterAggregateProvider
0x1800a008f  lea     rcx, [rsi+58h]; void *
0x1800a0093  call    ?_Uninit@?$basic_string@DU?$char_traits@D@utl@@V?$allocator@D@2@@utl@@AEAAXXZ; utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(void)
0x1800a0098  lea     rcx, [rsi+38h]
0x1800a009c  call    ??1?$map@V?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@V?$AutoRef@VPublisherMetadata@@@wmi@@Uistring_less_ordinal@tlx@@V?$allocator@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@V?$AutoRef@VPublisherMetadata@@@wmi@@@utl@@@2@@utl@@QEAA@XZ; utl::map<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>,wmi::AutoRef<PublisherMetadata>,tlx::istring_less_ordinal,utl::allocator<utl::pair<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> const,wmi::AutoRef<PublisherMetadata>>>>::~map<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>,wmi::AutoRef<PublisherMetadata>,tlx::istring_less_ordinal,utl::allocator<utl::pair<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> const,wmi::AutoRef<PublisherMetadata>>>>(void)
0x1800a00a1  lea     rcx, [rsi+18h]
0x1800a00a5  mov     rbx, [rsp+28h+arg_0]
0x1800a00aa  mov     rsi, [rsp+28h+arg_8]
0x1800a00af  add     rsp, 20h
0x1800a00b3  pop     rdi
0x1800a00b4  jmp     ?clear@?$_Tree@U_GUID@@U?$pair@$$CBU_GUID@@UPublisherCacheNode@PublisherManager@@@utl@@VGuidLess@@V?$allocator@U?$pair@$$CBU_GUID@@UPublisherCacheNode@PublisherManager@@@utl@@@3@$0A@@utl@@QEAAXXZ; utl::_Tree<_GUID,utl::pair<_GUID const,PublisherManager::PublisherCacheNode>,GuidLess,utl::allocator<utl::pair<_GUID const,PublisherManager::PublisherCacheNode>>,0>::clear(void)
```
