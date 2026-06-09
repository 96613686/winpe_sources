# ClusWmi::TaskManager::~TaskManager(void)

- ea: `0x18001d398`
- end: `0x18001d612`
- name: `??1TaskManager@ClusWmi@@QEAA@XZ`
- size: `634`
- prototype: `void __fastcall(ClusWmi::TaskManager *__hidden this)`
- caller_count: `1`
- callee_count: `20`
- tags: `service_task`

## callers

- `0x180018730`

## callees

- `0x18000c85c`
- `0x180014620`
- `0x180017f7c`
- `0x180017fcc`
- `0x180018690`
- `0x1800189bc`
- `0x180018b40`
- `0x18001aef0`
- `0x18001af54`
- `0x18001c8d4`
- `0x18001cad4`
- `0x18001d0e4`
- `0x18001d114`
- `0x18001d144`
- `0x18001d1c0`
- `0x18001d398`
- `0x18001e98c`
- `0x18001eb34`
- `0x18001f18c`
- `0x18008e010`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolCleanupGroupMembers` at `0x18001d4fd`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolCleanupGroupMembers` at `0x18001d4fd`

## pseudocode

```c
// Hidden C++ exception states: #wind=17
void __fastcall ClusWmi::TaskManager::~TaskManager(RTL_SRWLOCK *this)
{
  RTL_SRWLOCK *v1; // rdi
  PVOID Ptr; // rcx
  __int64 v3; // rax
  __int64 v4; // r14
  __int64 v5; // rbx
  char v6; // bl
  _QWORD *v7; // rbx
  PVOID v8; // rcx
  PVOID v9; // rcx
  struct cxl::TextWriter *v10; // rbx
  const cxl::Exception *v11; // [rsp+20h] [rbp-78h] BYREF
  _BYTE v12[16]; // [rsp+28h] [rbp-70h] BYREF
  _BYTE v13[16]; // [rsp+38h] [rbp-60h] BYREF
  _BYTE v14[16]; // [rsp+48h] [rbp-50h] BYREF
  _BYTE v15[64]; // [rsp+58h] [rbp-40h] BYREF
  __int64 v18; // [rsp+A8h] [rbp+10h] BYREF
  __int64 v19; // [rsp+B0h] [rbp+18h]

  v1 = this;
  cxl::AcquireWriteLock::AcquireWriteLock((cxl::AcquireWriteLock *)v15, this + 15);
  LOBYTE(v1[24].Ptr) = 0;
  while ( v1[4].Ptr )
    std::deque<cxl::counted_ptr<ClusWmi::TaskManager::ScheduledTask>>::pop_front(v1);
  Ptr = v1[25].Ptr;
  if ( Ptr )
    (*(void (__fastcall **)(PVOID))(*(_QWORD *)Ptr + 24LL))(Ptr);
  cxl::AcquireWriteLock::AcquireWriteLock((cxl::AcquireWriteLock *)v14, v1 + 19);
  if ( v1[5].Ptr != v1[6].Ptr )
  {
    ((void (*)(void))std::_Destroy_range<std::allocator<std::shared_ptr<Wsp::Facade::IStorageHealth>>>)();
    v1[6].Ptr = v1[5].Ptr;
  }
  cxl::AcquireWriteLock::AcquireWriteLock((cxl::AcquireWriteLock *)v13, v1 + 17);
  v3 = *(_QWORD *)v1[8].Ptr;
  v18 = v3;
  while ( !*(_BYTE *)(v3 + 25) )
  {
    v19 = v3 + 32;
    v4 = *(_QWORD *)(v3 + 64);
    v5 = *(_QWORD *)(v4 + 32);
    cxl::AcquireReadLock::AcquireReadLock((cxl::AcquireReadLock *)v12, (struct cxl::NonReentrantRWLock *)(v5 + 344));
    v6 = *(_BYTE *)(v5 + 296);
    cxl::ScopedResOwner<cxl::NonReentrantRWLock,cxl::AcquireSharedTraits<cxl::NonReentrantRWLock>>::Release(v12);
    try
    {
      if ( v6 )
        ClusWmi::Task::Stop(*(ClusWmi::Task **)(v4 + 32));
    }
    catch ( const cxl::Exception *v11 )
    {
      v10 = (struct cxl::TraceManager *)((char *)cxl::TraceManager::Instance() + 40);
      ClusWmi::TaskManager::ScheduledTask::get_id(*(_QWORD *)(v19 + 32));
      cxl::TextWriter::WriteLine<char,std::wstring,cxl::Exception>(
        v10,
        "The task '{0}' could not be canceled due to {1}.");
      v1 = this;
    }
    std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::wstring>>,std::_Iterator_base0>::operator++(&v18);
    v3 = v18;
  }
  v7 = v1[8].Ptr;
  std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const,cxl::counted_ptr<ClusWmi::TaskManager::ScheduledTask>>>>::_Erase_tree<std::allocator<std::_Tree_node<std::pair<std::wstring const,cxl::counted_ptr<ClusWmi::TaskManager::ScheduledTask>>,void *>>>(
    &v1[8],
    &v1[8],
    v7[1]);
  v7[1] = v7;
  *v7 = v7;
  v7[2] = v7;
  v1[9].Ptr = 0;
  v8 = v1[26].Ptr;
  if ( v8 )
    (*(void (__fastcall **)(PVOID))(*(_QWORD *)v8 + 24LL))(v8);
  CloseThreadpoolCleanupGroupMembers(*((PTP_CLEANUP_GROUP *)v1[27].Ptr + 3), 1, v1[27].Ptr);
  if ( v1[14].Ptr )
    ClusApi::EventThread::Stop((ClusApi::EventThread *)v1[14].Ptr);
  cxl::ScopedResOwner<cxl::NonReentrantRWLock,cxl::AcquireExclusiveTraits<cxl::NonReentrantRWLock>>::Release(v13);
  cxl::ScopedResOwner<cxl::NonReentrantRWLock,cxl::AcquireExclusiveTraits<cxl::NonReentrantRWLock>>::Release(v14);
  cxl::ScopedResOwner<cxl::NonReentrantRWLock,cxl::AcquireExclusiveTraits<cxl::NonReentrantRWLock>>::Release(v15);
  cxl::Token::Clear((cxl::Token *)&v1[28]);
  cxl::counted_ptr<cxl::tp2::ThreadPool>::~counted_ptr<cxl::tp2::ThreadPool>(&v1[27]);
  cxl::counted_ptr<cxl::tp2::ThreadPool>::~counted_ptr<cxl::tp2::ThreadPool>(&v1[26]);
  cxl::counted_ptr<cxl::tp2::ThreadPool>::~counted_ptr<cxl::tp2::ThreadPool>(&v1[25]);
  cxl::NonReentrantRWLock::~NonReentrantRWLock((cxl::NonReentrantRWLock *)&v1[21]);
  cxl::NonReentrantRWLock::~NonReentrantRWLock((cxl::NonReentrantRWLock *)&v1[19]);
  cxl::NonReentrantRWLock::~NonReentrantRWLock((cxl::NonReentrantRWLock *)&v1[17]);
  cxl::NonReentrantRWLock::~NonReentrantRWLock((cxl::NonReentrantRWLock *)&v1[15]);
  std::unique_ptr<ClusApi::EventThread>::~unique_ptr<ClusApi::EventThread>(&v1[14]);
  std::_Tree<std::_Tmap_traits<std::wstring,std::shared_ptr<ClusWmi::INotificationWorkItem>,cxl::CaseInsensitive_LessThan,std::allocator<std::pair<std::wstring const,std::shared_ptr<ClusWmi::INotificationWorkItem>>>,0>>::~_Tree<std::_Tmap_traits<std::wstring,std::shared_ptr<ClusWmi::INotificationWorkItem>,cxl::CaseInsensitive_LessThan,std::allocator<std::pair<std::wstring const,std::shared_ptr<ClusWmi::INotificationWorkItem>>>,0>>(&v1[12]);
  std::_Tree<std::_Tmap_traits<std::wstring,std::shared_ptr<ClusWmi::INotificationWorkItem>,cxl::CaseInsensitive_LessThan,std::allocator<std::pair<std::wstring const,std::shared_ptr<ClusWmi::INotificationWorkItem>>>,0>>::~_Tree<std::_Tmap_traits<std::wstring,std::shared_ptr<ClusWmi::INotificationWorkItem>,cxl::CaseInsensitive_LessThan,std::allocator<std::pair<std::wstring const,std::shared_ptr<ClusWmi::INotificationWorkItem>>>,0>>(&v1[10]);
  std::_Tree<std::_Tmap_traits<std::wstring,cxl::counted_ptr<Wsp::Health2::CHealthConnection>,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,cxl::counted_ptr<Wsp::Health2::CHealthConnection>>>,0>>::~_Tree<std::_Tmap_traits<std::wstring,cxl::counted_ptr<Wsp::Health2::CHealthConnection>,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,cxl::counted_ptr<Wsp::Health2::CHealthConnection>>>,0>>(&v1[8]);
  v9 = v1[5].Ptr;
  if ( v9 )
  {
    std::_Destroy_range<std::allocator<std::shared_ptr<Wsp::Facade::IStorageHealth>>>(v9, v1[6].Ptr);
    std::_Deallocate<16>(v1[5].Ptr, ((char *)v1[7].Ptr - (char *)v1[5].Ptr) & 0xFFFFFFFFFFFFFFF0uLL);
    v1[5].Ptr = 0;
    v1[6].Ptr = 0;
    v1[7].Ptr = 0;
  }
  std::deque<cxl::counted_ptr<ClusWmi::TaskManager::ScheduledTask>>::~deque<cxl::counted_ptr<ClusWmi::TaskManager::ScheduledTask>>(v1);
}

```

## disassembly

```asm
0x18001d398  mov     [rsp+arg_0], rcx
0x18001d39d  push    rbx
0x18001d39e  push    rdi
0x18001d39f  push    r12
0x18001d3a1  push    r14
0x18001d3a3  push    r15
0x18001d3a5  sub     rsp, 70h
0x18001d3a9  mov     rdi, rcx
0x18001d3ac  lea     rdx, [rcx+78h]; struct cxl::NonReentrantRWLock *
0x18001d3b0  lea     rcx, [rsp+98h+var_40]; this
0x18001d3b5  call    ??0AcquireWriteLock@cxl@@QEAA@AEAVNonReentrantRWLock@1@@Z; cxl::AcquireWriteLock::AcquireWriteLock(cxl::NonReentrantRWLock &)
0x18001d3ba  nop
0x18001d3bb  mov     byte ptr [rdi+0C0h], 0
0x18001d3c2  cmp     qword ptr [rdi+20h], 0
0x18001d3c7  jz      short loc_18001D3D3
0x18001d3c9  mov     rcx, rdi
0x18001d3cc  call    ?pop_front@?$deque@U?$counted_ptr@VScheduledTask@TaskManager@ClusWmi@@@cxl@@V?$allocator@U?$counted_ptr@VScheduledTask@TaskManager@ClusWmi@@@cxl@@@std@@@std@@QEAAXXZ; std::deque<cxl::counted_ptr<ClusWmi::TaskManager::ScheduledTask>>::pop_front(void)
0x18001d3d1  jmp     short loc_18001D3C2
0x18001d3d3  mov     rcx, [rdi+0C8h]
0x18001d3da  test    rcx, rcx
0x18001d3dd  jz      short loc_18001D3EB
0x18001d3df  mov     rax, [rcx]
0x18001d3e2  mov     rax, [rax+18h]
0x18001d3e6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d3eb  lea     rdx, [rdi+98h]; struct cxl::NonReentrantRWLock *
0x18001d3f2  lea     rcx, [rsp+98h+var_50]; this
0x18001d3f7  call    ??0AcquireWriteLock@cxl@@QEAA@AEAVNonReentrantRWLock@1@@Z; cxl::AcquireWriteLock::AcquireWriteLock(cxl::NonReentrantRWLock &)
0x18001d3fc  nop
0x18001d3fd  mov     rdx, [rdi+30h]
0x18001d401  mov     rcx, [rdi+28h]
0x18001d405  cmp     rcx, rdx
0x18001d408  jz      short loc_18001D417
0x18001d40a  call    ??$_Destroy_range@V?$allocator@V?$shared_ptr@UIStorageHealth@Facade@Wsp@@@std@@@std@@@std@@YAXPEAV?$shared_ptr@UIStorageHealth@Facade@Wsp@@@0@QEAV10@AEAV?$allocator@V?$shared_ptr@UIStorageHealth@Facade@Wsp@@@std@@@0@@Z; std::_Destroy_range<std::allocator<std::shared_ptr<Wsp::Facade::IStorageHealth>>>(std::shared_ptr<Wsp::Facade::IStorageHealth> *,std::shared_ptr<Wsp::Facade::IStorageHealth> * const,std::allocator<std::shared_ptr<Wsp::Facade::IStorageHealth>> &)
0x18001d40f  mov     rax, [rdi+28h]
0x18001d413  mov     [rdi+30h], rax
0x18001d417  lea     rdx, [rdi+88h]; struct cxl::NonReentrantRWLock *
0x18001d41e  lea     rcx, [rsp+98h+var_60]; this
0x18001d423  call    ??0AcquireWriteLock@cxl@@QEAA@AEAVNonReentrantRWLock@1@@Z; cxl::AcquireWriteLock::AcquireWriteLock(cxl::NonReentrantRWLock &)
0x18001d428  nop
0x18001d429  mov     rax, [rdi+40h]
0x18001d42d  mov     rax, [rax]
0x18001d430  mov     [rsp+98h+arg_8], rax
0x18001d438  cmp     byte ptr [rax+19h], 0
0x18001d43c  jnz     short loc_18001D4A2
0x18001d43e  add     rax, 20h ; ' '
0x18001d442  mov     [rsp+98h+arg_10], rax
0x18001d44a  mov     r14, [rax+20h]
0x18001d44e  mov     rbx, [r14+20h]
0x18001d452  lea     rdx, [rbx+158h]; struct cxl::NonReentrantRWLock *
0x18001d459  lea     rcx, [rsp+98h+var_70]; this
0x18001d45e  call    ??0AcquireReadLock@cxl@@QEAA@AEAVNonReentrantRWLock@1@@Z; cxl::AcquireReadLock::AcquireReadLock(cxl::NonReentrantRWLock &)
0x18001d463  mov     bl, [rbx+128h]
0x18001d469  lea     rcx, [rsp+98h+var_70]
0x18001d46e  call    ?Release@?$ScopedResOwner@VNonReentrantRWLock@cxl@@V?$AcquireSharedTraits@VNonReentrantRWLock@cxl@@@2@@cxl@@QEBAXXZ; cxl::ScopedResOwner<cxl::NonReentrantRWLock,cxl::AcquireSharedTraits<cxl::NonReentrantRWLock>>::Release(void)
0x18001d473  test    bl, bl
0x18001d475  jz      short loc_18001D481
0x18001d477  mov     rcx, [r14+20h]; this
0x18001d47b  call    ?Stop@Task@ClusWmi@@QEAAXXZ; ClusWmi::Task::Stop(void)
0x18001d480  nop
0x18001d481  jmp     short loc_18001D48B
0x18001d483  mov     rdi, [rsp+98h+arg_0]
0x18001d48b  lea     rcx, [rsp+98h+arg_8]
0x18001d493  call    ??E?$_Tree_unchecked_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@std@@@std@@U_Iterator_base0@2@@std@@QEAAAEAV01@XZ; std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::wstring>>,std::_Iterator_base0>::operator++(void)
0x18001d498  mov     rax, [rsp+98h+arg_8]
0x18001d4a0  jmp     short loc_18001D438
0x18001d4a2  lea     r14, [rdi+40h]
0x18001d4a6  mov     rbx, [r14]
0x18001d4a9  mov     r8, [rbx+8]
0x18001d4ad  mov     rdx, r14
0x18001d4b0  mov     rcx, r14
0x18001d4b3  call    ??$_Erase_tree@V?$allocator@U?$_Tree_node@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@U?$counted_ptr@VScheduledTask@TaskManager@ClusWmi@@@cxl@@@std@@PEAX@std@@@std@@@?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@U?$counted_ptr@VScheduledTask@TaskManager@ClusWmi@@@cxl@@@std@@@std@@@std@@QEAAXAEAV?$allocator@U?$_Tree_node@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@U?$counted_ptr@VScheduledTask@TaskManager@ClusWmi@@@cxl@@@std@@PEAX@std@@@1@PEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@U?$counted_ptr@VScheduledTask@TaskManager@ClusWmi@@@cxl@@@std@@PEAX@1@@Z; std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const,cxl::counted_ptr<ClusWmi::TaskManager::ScheduledTask>>>>::_Erase_tree<std::allocator<std::_Tree_node<std::pair<std::wstring const,cxl::counted_ptr<ClusWmi::TaskManager::ScheduledTask>>,void *>>>(std::allocator<std::_Tree_node<std::pair<std::wstring const,cxl::counted_ptr<ClusWmi::TaskManager::ScheduledTask>>,void *>> &,std::_Tree_node<std::pair<std::wstring const,cxl::counted_ptr<ClusWmi::TaskManager::ScheduledTask>>,void *> *)
0x18001d4b8  mov     [rbx+8], rbx
0x18001d4bc  mov     [rbx], rbx
0x18001d4bf  mov     [rbx+10h], rbx
0x18001d4c3  mov     qword ptr [r14+8], 0
0x18001d4cb  lea     r12, [rdi+0D0h]
0x18001d4d2  mov     rcx, [r12]
0x18001d4d6  test    rcx, rcx
0x18001d4d9  jz      short loc_18001D4E7
0x18001d4db  mov     rax, [rcx]
0x18001d4de  mov     rax, [rax+18h]
0x18001d4e2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d4e7  lea     rbx, [rdi+0D8h]
0x18001d4ee  mov     rcx, [rbx]
0x18001d4f1  mov     r8, rcx; pvCleanupContext
0x18001d4f4  mov     edx, 1; fCancelPendingCallbacks
0x18001d4f9  mov     rcx, [rcx+18h]; ptpcg
0x18001d4fd  call    cs:__imp_CloseThreadpoolCleanupGroupMembers
0x18001d504  nop     dword ptr [rax+rax+00h]
0x18001d509  lea     r15, [rdi+70h]
0x18001d50d  cmp     qword ptr [r15], 0
0x18001d511  jz      short loc_18001D51C
0x18001d513  mov     rcx, [r15]; this
0x18001d516  call    ?Stop@EventThread@ClusApi@@QEAAXXZ; ClusApi::EventThread::Stop(void)
0x18001d51b  nop
0x18001d51c  lea     rcx, [rsp+98h+var_60]
0x18001d521  call    ?Release@?$ScopedResOwner@VNonReentrantRWLock@cxl@@V?$AcquireExclusiveTraits@VNonReentrantRWLock@cxl@@@2@@cxl@@QEBAXXZ; cxl::ScopedResOwner<cxl::NonReentrantRWLock,cxl::AcquireExclusiveTraits<cxl::NonReentrantRWLock>>::Release(void)
0x18001d526  nop
0x18001d527  lea     rcx, [rsp+98h+var_50]
0x18001d52c  call    ?Release@?$ScopedResOwner@VNonReentrantRWLock@cxl@@V?$AcquireExclusiveTraits@VNonReentrantRWLock@cxl@@@2@@cxl@@QEBAXXZ; cxl::ScopedResOwner<cxl::NonReentrantRWLock,cxl::AcquireExclusiveTraits<cxl::NonReentrantRWLock>>::Release(void)
0x18001d531  nop
0x18001d532  lea     rcx, [rsp+98h+var_40]
0x18001d537  call    ?Release@?$ScopedResOwner@VNonReentrantRWLock@cxl@@V?$AcquireExclusiveTraits@VNonReentrantRWLock@cxl@@@2@@cxl@@QEBAXXZ; cxl::ScopedResOwner<cxl::NonReentrantRWLock,cxl::AcquireExclusiveTraits<cxl::NonReentrantRWLock>>::Release(void)
0x18001d53c  nop
0x18001d53d  lea     rcx, [rdi+0E0h]; this
0x18001d544  call    ?Clear@Token@cxl@@QEAAXXZ; cxl::Token::Clear(void)
0x18001d549  nop
0x18001d54a  mov     rcx, rbx
0x18001d54d  call    ??1?$counted_ptr@VThreadPool@tp2@cxl@@@cxl@@QEAA@XZ; cxl::counted_ptr<cxl::tp2::ThreadPool>::~counted_ptr<cxl::tp2::ThreadPool>(void)
0x18001d552  nop
0x18001d553  mov     rcx, r12
0x18001d556  call    ??1?$counted_ptr@VThreadPool@tp2@cxl@@@cxl@@QEAA@XZ; cxl::counted_ptr<cxl::tp2::ThreadPool>::~counted_ptr<cxl::tp2::ThreadPool>(void)
0x18001d55b  nop
0x18001d55c  lea     rcx, [rdi+0C8h]
0x18001d563  call    ??1?$counted_ptr@VThreadPool@tp2@cxl@@@cxl@@QEAA@XZ; cxl::counted_ptr<cxl::tp2::ThreadPool>::~counted_ptr<cxl::tp2::ThreadPool>(void)
0x18001d568  nop
0x18001d569  lea     rcx, [rdi+0A8h]; this
0x18001d570  call    ??1NonReentrantRWLock@cxl@@QEAA@XZ; cxl::NonReentrantRWLock::~NonReentrantRWLock(void)
0x18001d575  nop
0x18001d576  lea     rcx, [rdi+98h]; this
0x18001d57d  call    ??1NonReentrantRWLock@cxl@@QEAA@XZ; cxl::NonReentrantRWLock::~NonReentrantRWLock(void)
0x18001d582  nop
0x18001d583  lea     rcx, [rdi+88h]; this
0x18001d58a  call    ??1NonReentrantRWLock@cxl@@QEAA@XZ; cxl::NonReentrantRWLock::~NonReentrantRWLock(void)
0x18001d58f  nop
0x18001d590  lea     rcx, [rdi+78h]; this
0x18001d594  call    ??1NonReentrantRWLock@cxl@@QEAA@XZ; cxl::NonReentrantRWLock::~NonReentrantRWLock(void)
0x18001d599  nop
0x18001d59a  mov     rcx, r15
0x18001d59d  call    ??1?$unique_ptr@VEventThread@ClusApi@@U?$default_delete@VEventThread@ClusApi@@@std@@@std@@QEAA@XZ; std::unique_ptr<ClusApi::EventThread>::~unique_ptr<ClusApi::EventThread>(void)
0x18001d5a2  nop
0x18001d5a3  lea     rcx, [rdi+60h]
0x18001d5a7  call    ??1?$_Tree@V?$_Tmap_traits@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$shared_ptr@UINotificationWorkItem@ClusWmi@@@2@UCaseInsensitive_LessThan@cxl@@V?$allocator@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$shared_ptr@UINotificationWorkItem@ClusWmi@@@2@@std@@@2@$0A@@std@@@std@@QEAA@XZ; std::_Tree<std::_Tmap_traits<std::wstring,std::shared_ptr<ClusWmi::INotificationWorkItem>,cxl::CaseInsensitive_LessThan,std::allocator<std::pair<std::wstring const,std::shared_ptr<ClusWmi::INotificationWorkItem>>>,0>>::~_Tree<std::_Tmap_traits<std::wstring,std::shared_ptr<ClusWmi::INotificationWorkItem>,cxl::CaseInsensitive_LessThan,std::allocator<std::pair<std::wstring const,std::shared_ptr<ClusWmi::INotificationWorkItem>>>,0>>(void)
0x18001d5ac  nop
0x18001d5ad  lea     rcx, [rdi+50h]
0x18001d5b1  call    ??1?$_Tree@V?$_Tmap_traits@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$shared_ptr@UINotificationWorkItem@ClusWmi@@@2@UCaseInsensitive_LessThan@cxl@@V?$allocator@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$shared_ptr@UINotificationWorkItem@ClusWmi@@@2@@std@@@2@$0A@@std@@@std@@QEAA@XZ; std::_Tree<std::_Tmap_traits<std::wstring,std::shared_ptr<ClusWmi::INotificationWorkItem>,cxl::CaseInsensitive_LessThan,std::allocator<std::pair<std::wstring const,std::shared_ptr<ClusWmi::INotificationWorkItem>>>,0>>::~_Tree<std::_Tmap_traits<std::wstring,std::shared_ptr<ClusWmi::INotificationWorkItem>,cxl::CaseInsensitive_LessThan,std::allocator<std::pair<std::wstring const,std::shared_ptr<ClusWmi::INotificationWorkItem>>>,0>>(void)
0x18001d5b6  nop
0x18001d5b7  mov     rcx, r14
0x18001d5ba  call    ??1?$_Tree@V?$_Tmap_traits@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@U?$counted_ptr@VCHealthConnection@Health2@Wsp@@@cxl@@U?$less@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@U?$counted_ptr@VCHealthConnection@Health2@Wsp@@@cxl@@@std@@@2@$0A@@std@@@std@@QEAA@XZ; std::_Tree<std::_Tmap_traits<std::wstring,cxl::counted_ptr<Wsp::Health2::CHealthConnection>,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,cxl::counted_ptr<Wsp::Health2::CHealthConnection>>>,0>>::~_Tree<std::_Tmap_traits<std::wstring,cxl::counted_ptr<Wsp::Health2::CHealthConnection>,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,cxl::counted_ptr<Wsp::Health2::CHealthConnection>>>,0>>(void)
0x18001d5bf  nop
0x18001d5c0  mov     rcx, [rdi+28h]
0x18001d5c4  test    rcx, rcx
0x18001d5c7  jz      short loc_18001D5FE
0x18001d5c9  mov     rdx, [rdi+30h]
0x18001d5cd  call    ??$_Destroy_range@V?$allocator@V?$shared_ptr@UIStorageHealth@Facade@Wsp@@@std@@@std@@@std@@YAXPEAV?$shared_ptr@UIStorageHealth@Facade@Wsp@@@0@QEAV10@AEAV?$allocator@V?$shared_ptr@UIStorageHealth@Facade@Wsp@@@std@@@0@@Z; std::_Destroy_range<std::allocator<std::shared_ptr<Wsp::Facade::IStorageHealth>>>(std::shared_ptr<Wsp::Facade::IStorageHealth> *,std::shared_ptr<Wsp::Facade::IStorageHealth> * const,std::allocator<std::shared_ptr<Wsp::Facade::IStorageHealth>> &)
0x18001d5d2  mov     rcx, [rdi+28h]
0x18001d5d6  mov     rdx, [rdi+38h]
0x18001d5da  sub     rdx, rcx
0x18001d5dd  and     rdx, 0FFFFFFFFFFFFFFF0h
0x18001d5e1  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x18001d5e6  mov     qword ptr [rdi+28h], 0
0x18001d5ee  mov     qword ptr [rdi+30h], 0
0x18001d5f6  mov     qword ptr [rdi+38h], 0
0x18001d5fe  mov     rcx, rdi
0x18001d601  add     rsp, 70h
0x18001d605  pop     r15
0x18001d607  pop     r14
0x18001d609  pop     r12
0x18001d60b  pop     rdi
0x18001d60c  pop     rbx
0x18001d60d  jmp     ??1?$deque@U?$counted_ptr@VScheduledTask@TaskManager@ClusWmi@@@cxl@@V?$allocator@U?$counted_ptr@VScheduledTask@TaskManager@ClusWmi@@@cxl@@@std@@@std@@QEAA@XZ; std::deque<cxl::counted_ptr<ClusWmi::TaskManager::ScheduledTask>>::~deque<cxl::counted_ptr<ClusWmi::TaskManager::ScheduledTask>>(void)
```
