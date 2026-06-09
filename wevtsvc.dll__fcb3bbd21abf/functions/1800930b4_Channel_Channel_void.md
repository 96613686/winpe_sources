# Channel::~Channel(void)

- ea: `0x1800930b4`
- end: `0x180093284`
- name: `??1Channel@@EEAA@XZ`
- size: `464`
- prototype: `void __fastcall(Channel *__hidden this)`
- caller_count: `1`
- callee_count: `14`
- tags: `file_ops, registry_config`

## callers

- `0x18009eb20`

## callees

- `0x180003de0`
- `0x180017b60`
- `0x18001c320`
- `0x180031cc8`
- `0x180047194`
- `0x180047fd8`
- `0x1800660ac`
- `0x18006bc90`
- `0x180076788`
- `0x180092104`
- `0x1800930b4`
- `0x18009328c`
- `0x18009eac0`
- `0x18009eaf0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18009326b`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18009326b`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800930d3`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800930d3`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall Channel::~Channel(Channel *this)
{
  __int64 v2; // rcx
  _QWORD *v3; // rsi
  _QWORD *v4; // rdi
  void **v5; // rax
  _QWORD *v6; // rdx
  _QWORD *v7; // rdi
  _QWORD *v8; // rsi
  void **v9; // rax
  void *v10; // rcx
  __int64 **v11; // rsi
  __int64 *v12; // rdi
  __int64 *v13; // rdx
  __int64 v14; // rax
  __int64 v15; // rcx
  utl::_RefCountBase *v16; // rcx
  char *v17; // [rsp+20h] [rbp-38h] BYREF
  char v18; // [rsp+28h] [rbp-30h]

  *(_QWORD *)this = &Channel::`vftable';
  v17 = (char *)this + 56;
  AcquireSRWLockExclusive((PSRWLOCK)this + 7);
  v18 = 1;
  utl::unique_lock<utl::shared_mutex>::~unique_lock<utl::shared_mutex>(&v17);
  v3 = (_QWORD *)((char *)this + 840);
  v4 = (_QWORD *)*((_QWORD *)this + 107);
  if ( v4 == (_QWORD *)((char *)this + 840) )
    goto LABEL_9;
  while ( 1 )
  {
    v5 = (void **)v4[1];
    if ( v5 != &utl::_TreeSentinel )
      goto LABEL_7;
LABEL_3:
    v5 = (void **)v4[2];
    if ( v5 == &utl::_TreeSentinel )
      break;
LABEL_7:
    v4 = v5;
  }
  while ( 1 )
  {
    v6 = v4;
    v4 = (_QWORD *)(*v4 & 0xFFFFFFFFFFFFFFFEuLL);
    utl::_ContainerBase<utl::pair<Channel::ContainerChannelEventConvertersKey const,utl::shared_ptr<PublishedEventRecordToBinXmlConverter>>,utl::allocator<utl::pair<Channel::ContainerChannelEventConvertersKey const,utl::shared_ptr<PublishedEventRecordToBinXmlConverter>>>>::_DeleteNode<utl::_TreeNode<utl::pair<Channel::ContainerChannelEventConvertersKey const,utl::shared_ptr<PublishedEventRecordToBinXmlConverter>>>>(
      v2,
      v6);
    if ( v4 == v3 )
      break;
    if ( (void **)v4[1] != &utl::_TreeSentinel )
    {
      v4[1] = &utl::_TreeSentinel;
      goto LABEL_3;
    }
  }
  *v3 = v3;
  *((_QWORD *)this + 106) = (char *)this + 840;
  *((_QWORD *)this + 107) = (char *)this + 840;
  *((_QWORD *)this + 108) = 0;
LABEL_9:
  v7 = (_QWORD *)((char *)this + 800);
  v8 = (_QWORD *)*((_QWORD *)this + 102);
  if ( v8 == (_QWORD *)((char *)this + 800) )
    goto LABEL_17;
  while ( 2 )
  {
    v9 = (void **)v8[1];
    if ( v9 != &utl::_TreeSentinel )
    {
LABEL_15:
      v8 = v9;
      continue;
    }
    break;
  }
LABEL_11:
  v9 = (void **)v8[2];
  if ( v9 != &utl::_TreeSentinel )
    goto LABEL_15;
  while ( 1 )
  {
    v10 = v8;
    v8 = (_QWORD *)(*v8 & 0xFFFFFFFFFFFFFFFEuLL);
    operator delete(v10);
    if ( v8 == v7 )
      break;
    if ( (void **)v8[1] != &utl::_TreeSentinel )
    {
      v8[1] = &utl::_TreeSentinel;
      goto LABEL_11;
    }
  }
  *v7 = v7;
  *((_QWORD *)this + 101) = (char *)this + 800;
  *((_QWORD *)this + 102) = (char *)this + 800;
  *((_QWORD *)this + 103) = 0;
LABEL_17:
  v11 = (__int64 **)((char *)this + 776);
  while ( 1 )
  {
    v12 = *v11;
    if ( *v11 == (__int64 *)v11 )
      break;
    v13 = (__int64 *)v12[1];
    v14 = *v12;
    *v13 = *v12;
    *(_QWORD *)(v14 + 8) = v13;
    NotificationTarget::~NotificationTarget((NotificationTarget *)(v12 + 2));
    operator delete(v12);
  }
  *((_QWORD *)this + 99) = 0;
  if ( *((_QWORD *)this + 95) )
    utl::default_delete<EvtxFileEventSink>::operator()(v2);
  ChannelFilter::~ChannelFilter((PSRWLOCK)this + 60);
  if ( *((_QWORD *)this + 58) )
    utl::default_delete<EvtxFileEventSink>::operator()(v15);
  wmi::AutoRef<File>::Release((char *)this + 456);
  utl::unique_ptr<PublishedEventRecordToBinXmlConverter,utl::default_delete<PublishedEventRecordToBinXmlConverter>>::~unique_ptr<PublishedEventRecordToBinXmlConverter,utl::default_delete<PublishedEventRecordToBinXmlConverter>>((char *)this + 448);
  v16 = (utl::_RefCountBase *)*((_QWORD *)this + 55);
  if ( v16 )
    utl::_RefCountBase::_DecStrong(v16);
  utl::_OptionalData1<ChannelConfigSnapshot,0>::~_OptionalData1<ChannelConfigSnapshot,0>((char *)this + 168);
  utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit((char *)this + 136);
  utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit((char *)this + 104);
  wmi::AutoRef<PublisherMetadata>::Release((char *)this + 96);
  tlx::unique_any<tlx::handle_traits<void *,void * (void *),&void * LocalFree(void *),0>>::~unique_any<tlx::handle_traits<void *,void * (void *),&void * LocalFree(void *),0>>((char *)this + 88);
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 16));
  *(_QWORD *)this = &wmi::RefBase::`vftable';
}

```

## disassembly

```asm
0x1800930b4  push    rbx
0x1800930b6  push    rbp
0x1800930b7  push    rsi
0x1800930b8  push    rdi
0x1800930b9  sub     rsp, 38h
0x1800930bd  mov     rbx, rcx
0x1800930c0  lea     rax, ??_7Channel@@6B@; const Channel::`vftable'
0x1800930c7  mov     [rcx], rax
0x1800930ca  add     rcx, 38h ; '8'; SRWLock
0x1800930ce  mov     [rsp+58h+var_38], rcx
0x1800930d3  call    cs:__imp_AcquireSRWLockExclusive
0x1800930d9  mov     [rsp+58h+var_30], 1
0x1800930de  lea     rcx, [rsp+58h+var_38]
0x1800930e3  call    ??1?$unique_lock@Vshared_mutex@utl@@@utl@@QEAA@XZ; utl::unique_lock<utl::shared_mutex>::~unique_lock<utl::shared_mutex>(void)
0x1800930e8  lea     rsi, [rbx+348h]
0x1800930ef  mov     rdi, [rsi+10h]
0x1800930f3  lea     rbp, ?_TreeSentinel@utl@@3PEAXEA; void * utl::_TreeSentinel
0x1800930fa  cmp     rdi, rsi
0x1800930fd  jz      short loc_180093149
0x1800930ff  mov     rax, [rdi+8]
0x180093103  cmp     rax, rbp
0x180093106  jnz     short loc_180093131
0x180093108  mov     rax, [rdi+10h]
0x18009310c  cmp     rax, rbp
0x18009310f  jnz     short loc_180093131
0x180093111  mov     rdx, rdi
0x180093114  mov     rdi, [rdi]
0x180093117  and     rdi, 0FFFFFFFFFFFFFFFEh
0x18009311b  call    ??$_DeleteNode@U?$_TreeNode@U?$pair@$$CBUContainerChannelEventConvertersKey@Channel@@V?$shared_ptr@VPublishedEventRecordToBinXmlConverter@@@utl@@@utl@@@utl@@@?$_ContainerBase@U?$pair@$$CBUContainerChannelEventConvertersKey@Channel@@V?$shared_ptr@VPublishedEventRecordToBinXmlConverter@@@utl@@@utl@@V?$allocator@U?$pair@$$CBUContainerChannelEventConvertersKey@Channel@@V?$shared_ptr@VPublishedEventRecordToBinXmlConverter@@@utl@@@utl@@@2@@utl@@IEAAXPEAU?$_TreeNode@U?$pair@$$CBUContainerChannelEventConvertersKey@Channel@@V?$shared_ptr@VPublishedEventRecordToBinXmlConverter@@@utl@@@utl@@@1@@Z; utl::_ContainerBase<utl::pair<Channel::ContainerChannelEventConvertersKey const,utl::shared_ptr<PublishedEventRecordToBinXmlConverter>>,utl::allocator<utl::pair<Channel::ContainerChannelEventConvertersKey const,utl::shared_ptr<PublishedEventRecordToBinXmlConverter>>>>::_DeleteNode<utl::_TreeNode<utl::pair<Channel::ContainerChannelEventConvertersKey const,utl::shared_ptr<PublishedEventRecordToBinXmlConverter>>>>(utl::_TreeNode<utl::pair<Channel::ContainerChannelEventConvertersKey const,utl::shared_ptr<PublishedEventRecordToBinXmlConverter>>> *)
0x180093120  cmp     rdi, rsi
0x180093123  jz      short loc_180093136
0x180093125  cmp     [rdi+8], rbp
0x180093129  jz      short loc_180093111
0x18009312b  mov     [rdi+8], rbp
0x18009312f  jmp     short loc_180093108
0x180093131  mov     rdi, rax
0x180093134  jmp     short loc_1800930FF
0x180093136  mov     [rsi], rsi
0x180093139  mov     [rsi+8], rsi
0x18009313d  mov     [rsi+10h], rsi
0x180093141  mov     qword ptr [rsi+18h], 0
0x180093149  lea     rdi, [rbx+320h]
0x180093150  mov     rsi, [rdi+10h]
0x180093154  cmp     rsi, rdi
0x180093157  jz      short loc_1800931A3
0x180093159  mov     rax, [rsi+8]
0x18009315d  cmp     rax, rbp
0x180093160  jnz     short loc_18009318B
0x180093162  mov     rax, [rsi+10h]
0x180093166  cmp     rax, rbp
0x180093169  jnz     short loc_18009318B
0x18009316b  mov     rcx, rsi; void *
0x18009316e  mov     rsi, [rsi]
0x180093171  and     rsi, 0FFFFFFFFFFFFFFFEh
0x180093175  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18009317a  cmp     rsi, rdi
0x18009317d  jz      short loc_180093190
0x18009317f  cmp     [rsi+8], rbp
0x180093183  jz      short loc_18009316B
0x180093185  mov     [rsi+8], rbp
0x180093189  jmp     short loc_180093162
0x18009318b  mov     rsi, rax
0x18009318e  jmp     short loc_180093159
0x180093190  mov     [rdi], rdi
0x180093193  mov     [rdi+8], rdi
0x180093197  mov     [rdi+10h], rdi
0x18009319b  mov     qword ptr [rdi+18h], 0
0x1800931a3  lea     rsi, [rbx+308h]
0x1800931aa  mov     rdi, [rsi]
0x1800931ad  cmp     rdi, rsi
0x1800931b0  jz      short loc_1800931D3
0x1800931b2  mov     rdx, [rdi+8]
0x1800931b6  mov     rax, [rdi]
0x1800931b9  mov     [rdx], rax
0x1800931bc  mov     [rax+8], rdx
0x1800931c0  lea     rcx, [rdi+10h]; this
0x1800931c4  call    ??1NotificationTarget@@QEAA@XZ; NotificationTarget::~NotificationTarget(void)
0x1800931c9  mov     rcx, rdi; void *
0x1800931cc  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800931d1  jmp     short loc_1800931AA
0x1800931d3  mov     qword ptr [rsi+10h], 0
0x1800931db  mov     rdx, [rbx+2F8h]
0x1800931e2  test    rdx, rdx
0x1800931e5  jz      short loc_1800931EC
0x1800931e7  call    ??R?$default_delete@VEvtxFileEventSink@@@utl@@QEBAXPEAVEvtxFileEventSink@@@Z; utl::default_delete<EvtxFileEventSink>::operator()(EvtxFileEventSink *)
0x1800931ec  lea     rcx, [rbx+1E0h]; SRWLock
0x1800931f3  call    ??1ChannelFilter@@QEAA@XZ; ChannelFilter::~ChannelFilter(void)
0x1800931f8  mov     rdx, [rbx+1D0h]
0x1800931ff  test    rdx, rdx
0x180093202  jz      short loc_180093209
0x180093204  call    ??R?$default_delete@VEvtxFileEventSink@@@utl@@QEBAXPEAVEvtxFileEventSink@@@Z; utl::default_delete<EvtxFileEventSink>::operator()(EvtxFileEventSink *)
0x180093209  lea     rcx, [rbx+1C8h]
0x180093210  call    ?Release@?$AutoRef@VFile@@@wmi@@QEAAXXZ; wmi::AutoRef<File>::Release(void)
0x180093215  lea     rcx, [rbx+1C0h]
0x18009321c  call    ??1?$unique_ptr@VPublishedEventRecordToBinXmlConverter@@U?$default_delete@VPublishedEventRecordToBinXmlConverter@@@utl@@@utl@@QEAA@XZ; utl::unique_ptr<PublishedEventRecordToBinXmlConverter,utl::default_delete<PublishedEventRecordToBinXmlConverter>>::~unique_ptr<PublishedEventRecordToBinXmlConverter,utl::default_delete<PublishedEventRecordToBinXmlConverter>>(void)
0x180093221  nop
0x180093222  mov     rcx, [rbx+1B8h]; this
0x180093229  test    rcx, rcx
0x18009322c  jz      short loc_180093234
0x18009322e  call    ?_DecStrong@_RefCountBase@utl@@QEAAXXZ; utl::_RefCountBase::_DecStrong(void)
0x180093233  nop
0x180093234  lea     rcx, [rbx+0A8h]
0x18009323b  call    ??1?$_OptionalData1@VChannelConfigSnapshot@@$0A@@utl@@QEAA@XZ; utl::_OptionalData1<ChannelConfigSnapshot,0>::~_OptionalData1<ChannelConfigSnapshot,0>(void)
0x180093240  lea     rcx, [rbx+88h]; void *
0x180093247  call    ?_Uninit@?$basic_string@DU?$char_traits@D@utl@@V?$allocator@D@2@@utl@@AEAAXXZ; utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(void)
0x18009324c  lea     rcx, [rbx+68h]; void *
0x180093250  call    ?_Uninit@?$basic_string@DU?$char_traits@D@utl@@V?$allocator@D@2@@utl@@AEAAXXZ; utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(void)
0x180093255  lea     rcx, [rbx+60h]
0x180093259  call    ?Release@?$AutoRef@VPublisherMetadata@@@wmi@@QEAAXXZ; wmi::AutoRef<PublisherMetadata>::Release(void)
0x18009325e  lea     rcx, [rbx+58h]
0x180093262  call    ??1?$unique_any@U?$handle_traits@PEAX$$A6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z$0A@@tlx@@@tlx@@QEAA@XZ; tlx::unique_any<tlx::handle_traits<void *,void * (void *),&LocalFree(void *),0>>::~unique_any<tlx::handle_traits<void *,void * (void *),&LocalFree(void *),0>>(void)
0x180093267  lea     rcx, [rbx+10h]; lpCriticalSection
0x18009326b  call    cs:__imp_DeleteCriticalSection
0x180093271  lea     rax, ??_7RefBase@wmi@@6B@; const wmi::RefBase::`vftable'
0x180093278  mov     [rbx], rax
0x18009327b  add     rsp, 38h
0x18009327f  pop     rdi
0x180093280  pop     rsi
0x180093281  pop     rbp
0x180093282  pop     rbx
0x180093283  retn
```
