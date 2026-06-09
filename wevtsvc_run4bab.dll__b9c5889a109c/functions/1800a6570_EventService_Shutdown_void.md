# EventService::Shutdown(void)

- ea: `0x1800a6570`
- end: `0x1800a676b`
- name: `?Shutdown@EventService@@AEAAXXZ`
- size: `507`
- prototype: `void __fastcall(EventService *__hidden this)`
- caller_count: `1`
- callee_count: `14`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800a1ea4`

## callees

- `0x180003de0`
- `0x180043a88`
- `0x180046938`
- `0x18005c628`
- `0x18005d7d0`
- `0x180063194`
- `0x180077820`
- `0x180087160`
- `0x180087af0`
- `0x1800a1fcc`
- `0x1800a1ffc`
- `0x1800a6570`
- `0x1800c71fc`
- `0x1800c9034`

## import_xrefs

- `api-ms-win-core-perfcounters-l1-1-0!PerfDeleteInstance` at `0x1800a6752`
- `api-ms-win-core-perfcounters-l1-1-0!PerfDeleteInstance` at `0x1800a6752`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800a65fa`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800a663b`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800a669c`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800a66ce`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800a65fa`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800a663b`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800a669c`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800a66ce`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800a660e`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800a6665`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800a66c1`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800a66e7`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800a660e`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800a6665`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800a66c1`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800a66e7`

## pseudocode

```c
void __fastcall EventService::Shutdown(EventService *this, __int64 *a2)
{
  RTL_SRWLOCK *v2; // r14
  _BYTE *v3; // rbx
  RTL_SRWLOCK *v4; // r12
  ContainerListener *Ptr; // rcx
  RTL_SRWLOCK *v6; // r15
  ContainerForwarder *v7; // rcx
  _QWORD *v8; // rbx
  _QWORD *v9; // rsi
  PVOID v10; // rdx
  PVOID v11; // rdx
  FormatContext *v12; // rcx
  __int64 v13; // [rsp+0h] [rbp-58h] BYREF
  const EvtException *v14; // [rsp+20h] [rbp-38h] BYREF
  char *v17; // [rsp+68h] [rbp+10h]

  v2 = (RTL_SRWLOCK *)this;
  v3 = (char *)this + 484;
  v17 = (char *)this + 484;
  if ( !*((_BYTE *)this + 484) )
  {
    try
    {
      PublisherManager::DirectEventWrite((EventService *)((char *)this + 232), &EVENT_SHUTDOWN, 0, 0);
    }
    catch ( const EvtException *v14 )
    {
      a2 = &v13;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
      {
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          37,
          &WPP_4ca14dff85cd3471ba70228bb878e517_Traceguids,
          *((unsigned int *)v14 + 6));
      }
      v2 = (RTL_SRWLOCK *)this;
      v3 = v17;
    }
  }
  v4 = v2 + 57;
  Ptr = (ContainerListener *)v2[57].Ptr;
  if ( Ptr )
    ContainerListener::WaitUntilShutdownIsComplete(Ptr, (unsigned int)a2);
  v6 = v2 + 58;
  v7 = (ContainerForwarder *)v2[58].Ptr;
  if ( v7 )
    ContainerForwarder::WaitUntilDisconnectIsComplete(v7, (unsigned int)a2);
  AcquireSRWLockExclusive(&stru_180111D68);
  byte_18010F654 = 1;
  ReleaseSRWLockExclusive(&stru_180111D68);
  if ( !*v3 )
    ChannelManager::StopProcessingEvents(v2 + 45);
  AcquireSRWLockExclusive(v2 + 6);
  v8 = v2[3].Ptr;
  v9 = v2[4].Ptr;
  while ( v8 != v9 )
    File::FullFlush(*v8++, 2);
  ReleaseSRWLockExclusive(v2 + 6);
  v10 = v4->Ptr;
  v4->Ptr = 0;
  if ( v10 )
    utl::default_delete<ContainerManager>::operator()();
  v11 = v6->Ptr;
  v6->Ptr = 0;
  if ( v11 )
    utl::default_delete<ContainerForwarder>::operator()();
  AcquireSRWLockExclusive(&stru_1801114C0);
  utl::_Tree<_GUID,utl::pair<_GUID const,wmi::AutoRef<REG_CACHE_PROVIDERNODE>>,GuidLess,utl::allocator<utl::pair<_GUID const,wmi::AutoRef<REG_CACHE_PROVIDERNODE>>>,0>::clear(&qword_1801114C8);
  utl::_Tree<utl::basic_string_view<wchar_t,utl::char_traits<wchar_t>>,utl::pair<utl::basic_string_view<wchar_t,utl::char_traits<wchar_t>> const,wmi::AutoRef<REG_CACHE_PROVIDERNODE>>,tlx::istring_less_ordinal,utl::allocator<utl::pair<utl::basic_string_view<wchar_t,utl::char_traits<wchar_t>> const,wmi::AutoRef<REG_CACHE_PROVIDERNODE>>>,0>::clear(&qword_1801114E8);
  ReleaseSRWLockExclusive(&stru_1801114C0);
  AcquireSRWLockExclusive(&stru_180111508);
  utl::set<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>,utl::less<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>>,utl::allocator<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>>>::~set<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>,utl::less<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>>,utl::allocator<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>>>(&qword_180111510);
  ReleaseSRWLockExclusive(&stru_180111508);
  v12 = (FormatContext *)v2[2].Ptr;
  if ( v12 )
  {
    CloseTraceDecodingHandle(v12);
    v2[2].Ptr = 0;
  }
  utl::set<void *,utl::less<void *>,utl::allocator<void *>>::~set<void *,utl::less<void *>,utl::allocator<void *>>(&g_reservedLevels);
  utl::set<void *,utl::less<void *>,utl::allocator<void *>>::~set<void *,utl::less<void *>,utl::allocator<void *>>(&g_reservedTasks);
  utl::set<void *,utl::less<void *>,utl::allocator<void *>>::~set<void *,utl::less<void *>,utl::allocator<void *>>(&g_reservedOpcodes);
  utl::set<void *,utl::less<void *>,utl::allocator<void *>>::~set<void *,utl::less<void *>,utl::allocator<void *>>(&g_reservedKeywords);
  wmi::AutoRef<PublisherMetadata>::Release(&g_winmetaPublisherMetadata);
  if ( g_WevtCounterInstance )
    PerfDeleteInstance(WevtEventLogCounterProvider, g_WevtCounterInstance);
}

```

## disassembly

```asm
0x1800a6570  mov     [rsp+arg_18], rbx
0x1800a6575  mov     [rsp+arg_0], rcx
0x1800a657a  push    rsi
0x1800a657b  push    rdi
0x1800a657c  push    r12
0x1800a657e  push    r14
0x1800a6580  push    r15
0x1800a6582  sub     rsp, 30h
0x1800a6586  mov     r14, rcx
0x1800a6589  lea     rbx, [rcx+1E4h]
0x1800a6590  mov     [rsp+58h+arg_8], rbx
0x1800a6595  cmp     byte ptr [rbx], 0
0x1800a6598  jnz     short loc_1800A65C0
0x1800a659a  add     rcx, 0E8h; this
0x1800a65a1  xor     r9d, r9d; unsigned __int8 *
0x1800a65a4  xor     r8d, r8d; unsigned int
0x1800a65a7  lea     rdx, EVENT_SHUTDOWN; struct _EVENT_DESCRIPTOR *
0x1800a65ae  call    ?DirectEventWrite@PublisherManager@@QEAAXAEBU_EVENT_DESCRIPTOR@@KPEBE@Z; PublisherManager::DirectEventWrite(_EVENT_DESCRIPTOR const &,ulong,uchar const *)
0x1800a65b3  nop
0x1800a65b4  jmp     short loc_1800A65C0
0x1800a65b6  mov     r14, [rsp+58h+arg_0]
0x1800a65bb  mov     rbx, [rsp+58h+arg_8]
0x1800a65c0  lea     r12, [r14+1C8h]
0x1800a65c7  mov     [rsp+58h+arg_10], r12
0x1800a65cc  mov     rcx, [r12]; this
0x1800a65d0  test    rcx, rcx
0x1800a65d3  jz      short loc_1800A65DA
0x1800a65d5  call    ?WaitUntilShutdownIsComplete@ContainerListener@@QEAAJK@Z; ContainerListener::WaitUntilShutdownIsComplete(ulong)
0x1800a65da  lea     r15, [r14+1D0h]
0x1800a65e1  mov     [rsp+58h+arg_8], r15
0x1800a65e6  mov     rcx, [r15]; this
0x1800a65e9  test    rcx, rcx
0x1800a65ec  jz      short loc_1800A65F3
0x1800a65ee  call    ?WaitUntilDisconnectIsComplete@ContainerForwarder@@QEAAJK@Z; ContainerForwarder::WaitUntilDisconnectIsComplete(ulong)
0x1800a65f3  lea     rcx, stru_180111D68; SRWLock
0x1800a65fa  call    cs:__imp_AcquireSRWLockExclusive
0x1800a6600  mov     cs:byte_18010F654, 1
0x1800a6607  lea     rcx, stru_180111D68; SRWLock
0x1800a660e  call    cs:__imp_ReleaseSRWLockExclusive
0x1800a6614  cmp     byte ptr [rbx], 0
0x1800a6617  jnz     short loc_1800A6637
0x1800a6619  lea     rcx, [r14+168h]; SRWLock
0x1800a6620  call    ?StopProcessingEvents@ChannelManager@@QEAAXXZ; ChannelManager::StopProcessingEvents(void)
0x1800a6625  nop
0x1800a6626  jmp     short loc_1800A6637
0x1800a6628  mov     r14, [rsp+58h+arg_0]
0x1800a662d  mov     r15, [rsp+58h+arg_8]
0x1800a6632  mov     r12, [rsp+58h+arg_10]
0x1800a6637  lea     rcx, [r14+30h]; SRWLock
0x1800a663b  call    cs:__imp_AcquireSRWLockExclusive
0x1800a6641  mov     rbx, [r14+18h]
0x1800a6645  mov     rsi, [r14+20h]
0x1800a6649  cmp     rbx, rsi
0x1800a664c  jz      short loc_1800A6661
0x1800a664e  mov     edx, 2
0x1800a6653  mov     rcx, [rbx]
0x1800a6656  call    ?FullFlush@File@@QEAAKW4FlushType@@@Z; File::FullFlush(FlushType)
0x1800a665b  add     rbx, 8
0x1800a665f  jmp     short loc_1800A6649
0x1800a6661  lea     rcx, [r14+30h]; SRWLock
0x1800a6665  call    cs:__imp_ReleaseSRWLockExclusive
0x1800a666b  mov     rdx, [r12]
0x1800a666f  mov     qword ptr [r12], 0
0x1800a6677  test    rdx, rdx
0x1800a667a  jz      short loc_1800A6681
0x1800a667c  call    ??R?$default_delete@VContainerManager@@@utl@@QEBAXPEAVContainerManager@@@Z; utl::default_delete<ContainerManager>::operator()(ContainerManager *)
0x1800a6681  mov     rdx, [r15]
0x1800a6684  mov     qword ptr [r15], 0
0x1800a668b  test    rdx, rdx
0x1800a668e  jz      short loc_1800A6695
0x1800a6690  call    ??R?$default_delete@VContainerForwarder@@@utl@@QEBAXPEAVContainerForwarder@@@Z; utl::default_delete<ContainerForwarder>::operator()(ContainerForwarder *)
0x1800a6695  lea     rcx, stru_1801114C0; SRWLock
0x1800a669c  call    cs:__imp_AcquireSRWLockExclusive
0x1800a66a2  lea     rcx, qword_1801114C8
0x1800a66a9  call    ?clear@?$_Tree@U_GUID@@U?$pair@$$CBU_GUID@@V?$AutoRef@UREG_CACHE_PROVIDERNODE@@@wmi@@@utl@@VGuidLess@@V?$allocator@U?$pair@$$CBU_GUID@@V?$AutoRef@UREG_CACHE_PROVIDERNODE@@@wmi@@@utl@@@3@$0A@@utl@@QEAAXXZ; utl::_Tree<_GUID,utl::pair<_GUID const,wmi::AutoRef<REG_CACHE_PROVIDERNODE>>,GuidLess,utl::allocator<utl::pair<_GUID const,wmi::AutoRef<REG_CACHE_PROVIDERNODE>>>,0>::clear(void)
0x1800a66ae  lea     rcx, qword_1801114E8
0x1800a66b5  call    ?clear@?$_Tree@V?$basic_string_view@_WU?$char_traits@_W@utl@@@utl@@U?$pair@$$CBV?$basic_string_view@_WU?$char_traits@_W@utl@@@utl@@V?$AutoRef@UREG_CACHE_PROVIDERNODE@@@wmi@@@2@Uistring_less_ordinal@tlx@@V?$allocator@U?$pair@$$CBV?$basic_string_view@_WU?$char_traits@_W@utl@@@utl@@V?$AutoRef@UREG_CACHE_PROVIDERNODE@@@wmi@@@utl@@@2@$0A@@utl@@QEAAXXZ; utl::_Tree<utl::basic_string_view<wchar_t,utl::char_traits<wchar_t>>,utl::pair<utl::basic_string_view<wchar_t,utl::char_traits<wchar_t>> const,wmi::AutoRef<REG_CACHE_PROVIDERNODE>>,tlx::istring_less_ordinal,utl::allocator<utl::pair<utl::basic_string_view<wchar_t,utl::char_traits<wchar_t>> const,wmi::AutoRef<REG_CACHE_PROVIDERNODE>>>,0>::clear(void)
0x1800a66ba  lea     rcx, stru_1801114C0; SRWLock
0x1800a66c1  call    cs:__imp_ReleaseSRWLockExclusive
0x1800a66c7  lea     rcx, stru_180111508; SRWLock
0x1800a66ce  call    cs:__imp_AcquireSRWLockExclusive
0x1800a66d4  lea     rcx, qword_180111510
0x1800a66db  call    ??1?$set@V?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@U?$less@V?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@@2@V?$allocator@V?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@@2@@utl@@QEAA@XZ; utl::set<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>,utl::less<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>>,utl::allocator<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>>>::~set<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>,utl::less<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>>,utl::allocator<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>>>(void)
0x1800a66e0  lea     rcx, stru_180111508; SRWLock
0x1800a66e7  call    cs:__imp_ReleaseSRWLockExclusive
0x1800a66ed  mov     rcx, [r14+10h]; this
0x1800a66f1  test    rcx, rcx
0x1800a66f4  jz      short loc_1800A6703
0x1800a66f6  call    CloseTraceDecodingHandle
0x1800a66fb  mov     qword ptr [r14+10h], 0
0x1800a6703  lea     rcx, ?g_reservedLevels@@3V?$set@KU?$less@K@utl@@V?$allocator@K@2@@utl@@A; utl::set<ulong,utl::less<ulong>,utl::allocator<ulong>> g_reservedLevels
0x1800a670a  call    ??1?$set@PEAXU?$less@PEAX@utl@@V?$allocator@PEAX@2@@utl@@QEAA@XZ; utl::set<void *,utl::less<void *>,utl::allocator<void *>>::~set<void *,utl::less<void *>,utl::allocator<void *>>(void)
0x1800a670f  lea     rcx, ?g_reservedTasks@@3V?$set@KU?$less@K@utl@@V?$allocator@K@2@@utl@@A; utl::set<ulong,utl::less<ulong>,utl::allocator<ulong>> g_reservedTasks
0x1800a6716  call    ??1?$set@PEAXU?$less@PEAX@utl@@V?$allocator@PEAX@2@@utl@@QEAA@XZ; utl::set<void *,utl::less<void *>,utl::allocator<void *>>::~set<void *,utl::less<void *>,utl::allocator<void *>>(void)
0x1800a671b  lea     rcx, ?g_reservedOpcodes@@3V?$set@KU?$less@K@utl@@V?$allocator@K@2@@utl@@A; utl::set<ulong,utl::less<ulong>,utl::allocator<ulong>> g_reservedOpcodes
0x1800a6722  call    ??1?$set@PEAXU?$less@PEAX@utl@@V?$allocator@PEAX@2@@utl@@QEAA@XZ; utl::set<void *,utl::less<void *>,utl::allocator<void *>>::~set<void *,utl::less<void *>,utl::allocator<void *>>(void)
0x1800a6727  lea     rcx, ?g_reservedKeywords@@3V?$set@_KU?$less@_K@utl@@V?$allocator@_K@2@@utl@@A; utl::set<unsigned __int64,utl::less<unsigned __int64>,utl::allocator<unsigned __int64>> g_reservedKeywords
0x1800a672e  call    ??1?$set@PEAXU?$less@PEAX@utl@@V?$allocator@PEAX@2@@utl@@QEAA@XZ; utl::set<void *,utl::less<void *>,utl::allocator<void *>>::~set<void *,utl::less<void *>,utl::allocator<void *>>(void)
0x1800a6733  lea     rcx, ?g_winmetaPublisherMetadata@@3V?$AutoRef@VPublisherMetadata@@@wmi@@A; wmi::AutoRef<PublisherMetadata> g_winmetaPublisherMetadata
0x1800a673a  call    ?Release@?$AutoRef@VPublisherMetadata@@@wmi@@QEAAXXZ; wmi::AutoRef<PublisherMetadata>::Release(void)
0x1800a673f  mov     rdx, cs:?g_WevtCounterInstance@@3PEAU_PERF_COUNTERSET_INSTANCE@@EA; InstanceBlock
0x1800a6746  test    rdx, rdx
0x1800a6749  jz      short loc_1800A6759
0x1800a674b  mov     rcx, cs:WevtEventLogCounterProvider; Provider
0x1800a6752  call    cs:__imp_PerfDeleteInstance
0x1800a6758  nop
0x1800a6759  mov     rbx, [rsp+58h+arg_18]
0x1800a675e  add     rsp, 30h
0x1800a6762  pop     r15
0x1800a6764  pop     r14
0x1800a6766  pop     r12
0x1800a6768  pop     rdi
0x1800a6769  pop     rsi
0x1800a676a  retn
```
