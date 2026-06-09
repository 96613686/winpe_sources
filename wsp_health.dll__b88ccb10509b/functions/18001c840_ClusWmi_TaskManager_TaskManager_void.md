# ClusWmi::TaskManager::~TaskManager(void)

- ea: `0x18001c840`
- end: `0x18001cab4`
- name: `??1TaskManager@ClusWmi@@QEAA@XZ`
- size: `628`
- prototype: `void __fastcall(ClusWmi::TaskManager *__hidden this)`
- caller_count: `1`
- callee_count: `20`
- tags: `service_task`

## callers

- `0x180017da4`

## callees

- `0x18000c4c4`
- `0x180013ec0`
- `0x180017640`
- `0x180017688`
- `0x180017d08`
- `0x180018030`
- `0x1800181a4`
- `0x18001a470`
- `0x18001a4c8`
- `0x18001bda4`
- `0x18001bfac`
- `0x18001c5a8`
- `0x18001c5d8`
- `0x18001c608`
- `0x18001c684`
- `0x18001c840`
- `0x18001ddd4`
- `0x18001df70`
- `0x18001e5b8`
- `0x18008c010`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolCleanupGroupMembers` at `0x18001c9a5`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolCleanupGroupMembers` at `0x18001c9a5`

## pseudocode

```c
// Hidden C++ exception states: #wind=17
void __fastcall ClusWmi::TaskManager::~TaskManager(RTL_SRWLOCK *this)
{
  RTL_SRWLOCK *v1; // rdi
  PVOID Ptr; // rcx
  __int64 v3; // r8
  __int64 v4; // r9
  PVOID v5; // rdx
  PVOID v6; // rcx
  __int64 v7; // rax
  __int64 v8; // r14
  __int64 v9; // rbx
  char v10; // bl
  __int64 v11; // rdx
  __int64 **v12; // rbx
  PVOID v13; // rcx
  __int64 v14; // r8
  __int64 v15; // r9
  PVOID v16; // rcx
  struct cxl::TextWriter *v17; // rbx
  const cxl::Exception *v18; // [rsp+20h] [rbp-78h] BYREF
  _BYTE v19[16]; // [rsp+28h] [rbp-70h] BYREF
  _BYTE v20[16]; // [rsp+38h] [rbp-60h] BYREF
  _BYTE v21[16]; // [rsp+48h] [rbp-50h] BYREF
  _BYTE v22[64]; // [rsp+58h] [rbp-40h] BYREF
  __int64 v25; // [rsp+A8h] [rbp+10h] BYREF
  __int64 v26; // [rsp+B0h] [rbp+18h]

  v1 = this;
  cxl::AcquireWriteLock::AcquireWriteLock((cxl::AcquireWriteLock *)v22, this + 15);
  LOBYTE(v1[24].Ptr) = 0;
  while ( v1[4].Ptr )
    std::deque<cxl::counted_ptr<ClusWmi::TaskManager::ScheduledTask>>::pop_front(v1);
  Ptr = v1[25].Ptr;
  if ( Ptr )
    (*(void (__fastcall **)(PVOID))(*(_QWORD *)Ptr + 24LL))(Ptr);
  cxl::AcquireWriteLock::AcquireWriteLock((cxl::AcquireWriteLock *)v21, v1 + 19);
  v5 = v1[6].Ptr;
  v6 = v1[5].Ptr;
  if ( v6 != v5 )
  {
    std::_Destroy_range<std::allocator<std::shared_ptr<Wsp::Facade::IStorageHealth>>>(v6, v5, v3, v4);
    v1[6].Ptr = v1[5].Ptr;
  }
  cxl::AcquireWriteLock::AcquireWriteLock((cxl::AcquireWriteLock *)v20, v1 + 17);
  v7 = *(_QWORD *)v1[8].Ptr;
  v25 = v7;
  while ( !*(_BYTE *)(v7 + 25) )
  {
    v26 = v7 + 32;
    v8 = *(_QWORD *)(v7 + 64);
    v9 = *(_QWORD *)(v8 + 32);
    cxl::AcquireReadLock::AcquireReadLock((cxl::AcquireReadLock *)v19, (struct cxl::NonReentrantRWLock *)(v9 + 344));
    v10 = *(_BYTE *)(v9 + 296);
    cxl::ScopedResOwner<cxl::NonReentrantRWLock,cxl::AcquireSharedTraits<cxl::NonReentrantRWLock>>::Release(v19, v11);
    try
    {
      if ( v10 )
        ClusWmi::Task::Stop(*(ClusWmi::Task **)(v8 + 32));
    }
    catch ( const cxl::Exception *v18 )
    {
      v17 = (struct cxl::TraceManager *)((char *)cxl::TraceManager::Instance() + 40);
      ClusWmi::TaskManager::ScheduledTask::get_id(*(_QWORD *)(v26 + 32));
      cxl::TextWriter::WriteLine<char,std::wstring,cxl::Exception>(
        v17,
        "The task '{0}' could not be canceled due to {1}.");
      v1 = this;
    }
    std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::wstring>>,std::_Iterator_base0>::operator++(&v25);
    v7 = v25;
  }
  v12 = (__int64 **)v1[8].Ptr;
  std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const,cxl::counted_ptr<ClusWmi::TaskManager::ScheduledTask>>>>::_Erase_tree<std::allocator<std::_Tree_node<std::pair<std::wstring const,cxl::counted_ptr<ClusWmi::TaskManager::ScheduledTask>>,void *>>>(
    (__int64)&v1[8],
    (__int64)&v1[8],
    v12[1]);
  v12[1] = (__int64 *)v12;
  *v12 = (__int64 *)v12;
  v12[2] = (__int64 *)v12;
  v1[9].Ptr = 0;
  v13 = v1[26].Ptr;
  if ( v13 )
    (*(void (__fastcall **)(PVOID))(*(_QWORD *)v13 + 24LL))(v13);
  CloseThreadpoolCleanupGroupMembers(*((PTP_CLEANUP_GROUP *)v1[27].Ptr + 3), 1, v1[27].Ptr);
  if ( v1[14].Ptr )
    ClusApi::EventThread::Stop((ClusApi::EventThread *)v1[14].Ptr);
  cxl::ScopedResOwner<cxl::NonReentrantRWLock,cxl::AcquireExclusiveTraits<cxl::NonReentrantRWLock>>::Release(v20);
  cxl::ScopedResOwner<cxl::NonReentrantRWLock,cxl::AcquireExclusiveTraits<cxl::NonReentrantRWLock>>::Release(v21);
  cxl::ScopedResOwner<cxl::NonReentrantRWLock,cxl::AcquireExclusiveTraits<cxl::NonReentrantRWLock>>::Release(v22);
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
  v16 = v1[5].Ptr;
  if ( v16 )
  {
    std::_Destroy_range<std::allocator<std::shared_ptr<Wsp::Facade::IStorageHealth>>>(v16, v1[6].Ptr, v14, v15);
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
0x18001c840  mov     [rsp+arg_0], rcx
0x18001c845  push    rbx
0x18001c846  push    rdi
0x18001c847  push    r12
0x18001c849  push    r14
0x18001c84b  push    r15
0x18001c84d  sub     rsp, 70h
0x18001c851  mov     rdi, rcx
0x18001c854  lea     rdx, [rcx+78h]; struct cxl::NonReentrantRWLock *
0x18001c858  lea     rcx, [rsp+98h+var_40]; this
0x18001c85d  call    ??0AcquireWriteLock@cxl@@QEAA@AEAVNonReentrantRWLock@1@@Z; cxl::AcquireWriteLock::AcquireWriteLock(cxl::NonReentrantRWLock &)
0x18001c862  nop
0x18001c863  mov     byte ptr [rdi+0C0h], 0
0x18001c86a  cmp     qword ptr [rdi+20h], 0
0x18001c86f  jz      short loc_18001C87B
0x18001c871  mov     rcx, rdi
0x18001c874  call    ?pop_front@?$deque@U?$counted_ptr@VScheduledTask@TaskManager@ClusWmi@@@cxl@@V?$allocator@U?$counted_ptr@VScheduledTask@TaskManager@ClusWmi@@@cxl@@@std@@@std@@QEAAXXZ; std::deque<cxl::counted_ptr<ClusWmi::TaskManager::ScheduledTask>>::pop_front(void)
0x18001c879  jmp     short loc_18001C86A
0x18001c87b  mov     rcx, [rdi+0C8h]
0x18001c882  test    rcx, rcx
0x18001c885  jz      short loc_18001C893
0x18001c887  mov     rax, [rcx]
0x18001c88a  mov     rax, [rax+18h]
0x18001c88e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c893  lea     rdx, [rdi+98h]; struct cxl::NonReentrantRWLock *
0x18001c89a  lea     rcx, [rsp+98h+var_50]; this
0x18001c89f  call    ??0AcquireWriteLock@cxl@@QEAA@AEAVNonReentrantRWLock@1@@Z; cxl::AcquireWriteLock::AcquireWriteLock(cxl::NonReentrantRWLock &)
0x18001c8a4  nop
0x18001c8a5  mov     rdx, [rdi+30h]
0x18001c8a9  mov     rcx, [rdi+28h]
0x18001c8ad  cmp     rcx, rdx
0x18001c8b0  jz      short loc_18001C8BF
0x18001c8b2  call    ??$_Destroy_range@V?$allocator@V?$shared_ptr@UIStorageHealth@Facade@Wsp@@@std@@@std@@@std@@YAXPEAV?$shared_ptr@UIStorageHealth@Facade@Wsp@@@0@QEAV10@AEAV?$allocator@V?$shared_ptr@UIStorageHealth@Facade@Wsp@@@std@@@0@@Z; std::_Destroy_range<std::allocator<std::shared_ptr<Wsp::Facade::IStorageHealth>>>(std::shared_ptr<Wsp::Facade::IStorageHealth> *,std::shared_ptr<Wsp::Facade::IStorageHealth> * const,std::allocator<std::shared_ptr<Wsp::Facade::IStorageHealth>> &)
0x18001c8b7  mov     rax, [rdi+28h]
0x18001c8bb  mov     [rdi+30h], rax
0x18001c8bf  lea     rdx, [rdi+88h]; struct cxl::NonReentrantRWLock *
0x18001c8c6  lea     rcx, [rsp+98h+var_60]; this
0x18001c8cb  call    ??0AcquireWriteLock@cxl@@QEAA@AEAVNonReentrantRWLock@1@@Z; cxl::AcquireWriteLock::AcquireWriteLock(cxl::NonReentrantRWLock &)
0x18001c8d0  nop
0x18001c8d1  mov     rax, [rdi+40h]
0x18001c8d5  mov     rax, [rax]
0x18001c8d8  mov     [rsp+98h+arg_8], rax
0x18001c8e0  cmp     byte ptr [rax+19h], 0
0x18001c8e4  jnz     short loc_18001C94A
0x18001c8e6  add     rax, 20h ; ' '
0x18001c8ea  mov     [rsp+98h+arg_10], rax
0x18001c8f2  mov     r14, [rax+20h]
0x18001c8f6  mov     rbx, [r14+20h]
0x18001c8fa  lea     rdx, [rbx+158h]; struct cxl::NonReentrantRWLock *
0x18001c901  lea     rcx, [rsp+98h+var_70]; this
0x18001c906  call    ??0AcquireReadLock@cxl@@QEAA@AEAVNonReentrantRWLock@1@@Z; cxl::AcquireReadLock::AcquireReadLock(cxl::NonReentrantRWLock &)
0x18001c90b  mov     bl, [rbx+128h]
0x18001c911  lea     rcx, [rsp+98h+var_70]
0x18001c916  call    ?Release@?$ScopedResOwner@VNonReentrantRWLock@cxl@@V?$AcquireSharedTraits@VNonReentrantRWLock@cxl@@@2@@cxl@@QEBAXXZ; cxl::ScopedResOwner<cxl::NonReentrantRWLock,cxl::AcquireSharedTraits<cxl::NonReentrantRWLock>>::Release(void)
0x18001c91b  test    bl, bl
0x18001c91d  jz      short loc_18001C929
0x18001c91f  mov     rcx, [r14+20h]; this
0x18001c923  call    ?Stop@Task@ClusWmi@@QEAAXXZ; ClusWmi::Task::Stop(void)
0x18001c928  nop
0x18001c929  jmp     short loc_18001C933
0x18001c92b  mov     rdi, [rsp+98h+arg_0]
0x18001c933  lea     rcx, [rsp+98h+arg_8]
0x18001c93b  call    ??E?$_Tree_unchecked_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@std@@@std@@U_Iterator_base0@2@@std@@QEAAAEAV01@XZ; std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::wstring>>,std::_Iterator_base0>::operator++(void)
0x18001c940  mov     rax, [rsp+98h+arg_8]
0x18001c948  jmp     short loc_18001C8E0
0x18001c94a  lea     r14, [rdi+40h]
0x18001c94e  mov     rbx, [r14]
0x18001c951  mov     r8, [rbx+8]
0x18001c955  mov     rdx, r14
0x18001c958  mov     rcx, r14
0x18001c95b  call    ??$_Erase_tree@V?$allocator@U?$_Tree_node@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@U?$counted_ptr@VScheduledTask@TaskManager@ClusWmi@@@cxl@@@std@@PEAX@std@@@std@@@?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@U?$counted_ptr@VScheduledTask@TaskManager@ClusWmi@@@cxl@@@std@@@std@@@std@@QEAAXAEAV?$allocator@U?$_Tree_node@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@U?$counted_ptr@VScheduledTask@TaskManager@ClusWmi@@@cxl@@@std@@PEAX@std@@@1@PEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@U?$counted_ptr@VScheduledTask@TaskManager@ClusWmi@@@cxl@@@std@@PEAX@1@@Z; std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const,cxl::counted_ptr<ClusWmi::TaskManager::ScheduledTask>>>>::_Erase_tree<std::allocator<std::_Tree_node<std::pair<std::wstring const,cxl::counted_ptr<ClusWmi::TaskManager::ScheduledTask>>,void *>>>(std::allocator<std::_Tree_node<std::pair<std::wstring const,cxl::counted_ptr<ClusWmi::TaskManager::ScheduledTask>>,void *>> &,std::_Tree_node<std::pair<std::wstring const,cxl::counted_ptr<ClusWmi::TaskManager::ScheduledTask>>,void *> *)
0x18001c960  mov     [rbx+8], rbx
0x18001c964  mov     [rbx], rbx
0x18001c967  mov     [rbx+10h], rbx
0x18001c96b  mov     qword ptr [r14+8], 0
0x18001c973  lea     r12, [rdi+0D0h]
0x18001c97a  mov     rcx, [r12]
0x18001c97e  test    rcx, rcx
0x18001c981  jz      short loc_18001C98F
0x18001c983  mov     rax, [rcx]
0x18001c986  mov     rax, [rax+18h]
0x18001c98a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c98f  lea     rbx, [rdi+0D8h]
0x18001c996  mov     rcx, [rbx]
0x18001c999  mov     r8, rcx; pvCleanupContext
0x18001c99c  mov     edx, 1; fCancelPendingCallbacks
0x18001c9a1  mov     rcx, [rcx+18h]; ptpcg
0x18001c9a5  call    cs:__imp_CloseThreadpoolCleanupGroupMembers
0x18001c9ab  lea     r15, [rdi+70h]
0x18001c9af  cmp     qword ptr [r15], 0
0x18001c9b3  jz      short loc_18001C9BE
0x18001c9b5  mov     rcx, [r15]; this
0x18001c9b8  call    ?Stop@EventThread@ClusApi@@QEAAXXZ; ClusApi::EventThread::Stop(void)
0x18001c9bd  nop
0x18001c9be  lea     rcx, [rsp+98h+var_60]
0x18001c9c3  call    ?Release@?$ScopedResOwner@VNonReentrantRWLock@cxl@@V?$AcquireExclusiveTraits@VNonReentrantRWLock@cxl@@@2@@cxl@@QEBAXXZ; cxl::ScopedResOwner<cxl::NonReentrantRWLock,cxl::AcquireExclusiveTraits<cxl::NonReentrantRWLock>>::Release(void)
0x18001c9c8  nop
0x18001c9c9  lea     rcx, [rsp+98h+var_50]
0x18001c9ce  call    ?Release@?$ScopedResOwner@VNonReentrantRWLock@cxl@@V?$AcquireExclusiveTraits@VNonReentrantRWLock@cxl@@@2@@cxl@@QEBAXXZ; cxl::ScopedResOwner<cxl::NonReentrantRWLock,cxl::AcquireExclusiveTraits<cxl::NonReentrantRWLock>>::Release(void)
0x18001c9d3  nop
0x18001c9d4  lea     rcx, [rsp+98h+var_40]
0x18001c9d9  call    ?Release@?$ScopedResOwner@VNonReentrantRWLock@cxl@@V?$AcquireExclusiveTraits@VNonReentrantRWLock@cxl@@@2@@cxl@@QEBAXXZ; cxl::ScopedResOwner<cxl::NonReentrantRWLock,cxl::AcquireExclusiveTraits<cxl::NonReentrantRWLock>>::Release(void)
0x18001c9de  nop
0x18001c9df  lea     rcx, [rdi+0E0h]; this
0x18001c9e6  call    ?Clear@Token@cxl@@QEAAXXZ; cxl::Token::Clear(void)
0x18001c9eb  nop
0x18001c9ec  mov     rcx, rbx
0x18001c9ef  call    ??1?$counted_ptr@VThreadPool@tp2@cxl@@@cxl@@QEAA@XZ; cxl::counted_ptr<cxl::tp2::ThreadPool>::~counted_ptr<cxl::tp2::ThreadPool>(void)
0x18001c9f4  nop
0x18001c9f5  mov     rcx, r12
0x18001c9f8  call    ??1?$counted_ptr@VThreadPool@tp2@cxl@@@cxl@@QEAA@XZ; cxl::counted_ptr<cxl::tp2::ThreadPool>::~counted_ptr<cxl::tp2::ThreadPool>(void)
0x18001c9fd  nop
0x18001c9fe  lea     rcx, [rdi+0C8h]
0x18001ca05  call    ??1?$counted_ptr@VThreadPool@tp2@cxl@@@cxl@@QEAA@XZ; cxl::counted_ptr<cxl::tp2::ThreadPool>::~counted_ptr<cxl::tp2::ThreadPool>(void)
0x18001ca0a  nop
0x18001ca0b  lea     rcx, [rdi+0A8h]; this
0x18001ca12  call    ??1NonReentrantRWLock@cxl@@QEAA@XZ; cxl::NonReentrantRWLock::~NonReentrantRWLock(void)
0x18001ca17  nop
0x18001ca18  lea     rcx, [rdi+98h]; this
0x18001ca1f  call    ??1NonReentrantRWLock@cxl@@QEAA@XZ; cxl::NonReentrantRWLock::~NonReentrantRWLock(void)
0x18001ca24  nop
0x18001ca25  lea     rcx, [rdi+88h]; this
0x18001ca2c  call    ??1NonReentrantRWLock@cxl@@QEAA@XZ; cxl::NonReentrantRWLock::~NonReentrantRWLock(void)
0x18001ca31  nop
0x18001ca32  lea     rcx, [rdi+78h]; this
0x18001ca36  call    ??1NonReentrantRWLock@cxl@@QEAA@XZ; cxl::NonReentrantRWLock::~NonReentrantRWLock(void)
0x18001ca3b  nop
0x18001ca3c  mov     rcx, r15
0x18001ca3f  call    ??1?$unique_ptr@VEventThread@ClusApi@@U?$default_delete@VEventThread@ClusApi@@@std@@@std@@QEAA@XZ; std::unique_ptr<ClusApi::EventThread>::~unique_ptr<ClusApi::EventThread>(void)
0x18001ca44  nop
0x18001ca45  lea     rcx, [rdi+60h]
0x18001ca49  call    ??1?$_Tree@V?$_Tmap_traits@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$shared_ptr@UINotificationWorkItem@ClusWmi@@@2@UCaseInsensitive_LessThan@cxl@@V?$allocator@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$shared_ptr@UINotificationWorkItem@ClusWmi@@@2@@std@@@2@$0A@@std@@@std@@QEAA@XZ; std::_Tree<std::_Tmap_traits<std::wstring,std::shared_ptr<ClusWmi::INotificationWorkItem>,cxl::CaseInsensitive_LessThan,std::allocator<std::pair<std::wstring const,std::shared_ptr<ClusWmi::INotificationWorkItem>>>,0>>::~_Tree<std::_Tmap_traits<std::wstring,std::shared_ptr<ClusWmi::INotificationWorkItem>,cxl::CaseInsensitive_LessThan,std::allocator<std::pair<std::wstring const,std::shared_ptr<ClusWmi::INotificationWorkItem>>>,0>>(void)
0x18001ca4e  nop
0x18001ca4f  lea     rcx, [rdi+50h]
0x18001ca53  call    ??1?$_Tree@V?$_Tmap_traits@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$shared_ptr@UINotificationWorkItem@ClusWmi@@@2@UCaseInsensitive_LessThan@cxl@@V?$allocator@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$shared_ptr@UINotificationWorkItem@ClusWmi@@@2@@std@@@2@$0A@@std@@@std@@QEAA@XZ; std::_Tree<std::_Tmap_traits<std::wstring,std::shared_ptr<ClusWmi::INotificationWorkItem>,cxl::CaseInsensitive_LessThan,std::allocator<std::pair<std::wstring const,std::shared_ptr<ClusWmi::INotificationWorkItem>>>,0>>::~_Tree<std::_Tmap_traits<std::wstring,std::shared_ptr<ClusWmi::INotificationWorkItem>,cxl::CaseInsensitive_LessThan,std::allocator<std::pair<std::wstring const,std::shared_ptr<ClusWmi::INotificationWorkItem>>>,0>>(void)
0x18001ca58  nop
0x18001ca59  mov     rcx, r14
0x18001ca5c  call    ??1?$_Tree@V?$_Tmap_traits@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@U?$counted_ptr@VCHealthConnection@Health2@Wsp@@@cxl@@U?$less@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@U?$counted_ptr@VCHealthConnection@Health2@Wsp@@@cxl@@@std@@@2@$0A@@std@@@std@@QEAA@XZ; std::_Tree<std::_Tmap_traits<std::wstring,cxl::counted_ptr<Wsp::Health2::CHealthConnection>,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,cxl::counted_ptr<Wsp::Health2::CHealthConnection>>>,0>>::~_Tree<std::_Tmap_traits<std::wstring,cxl::counted_ptr<Wsp::Health2::CHealthConnection>,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,cxl::counted_ptr<Wsp::Health2::CHealthConnection>>>,0>>(void)
0x18001ca61  nop
0x18001ca62  mov     rcx, [rdi+28h]
0x18001ca66  test    rcx, rcx
0x18001ca69  jz      short loc_18001CAA0
0x18001ca6b  mov     rdx, [rdi+30h]
0x18001ca6f  call    ??$_Destroy_range@V?$allocator@V?$shared_ptr@UIStorageHealth@Facade@Wsp@@@std@@@std@@@std@@YAXPEAV?$shared_ptr@UIStorageHealth@Facade@Wsp@@@0@QEAV10@AEAV?$allocator@V?$shared_ptr@UIStorageHealth@Facade@Wsp@@@std@@@0@@Z; std::_Destroy_range<std::allocator<std::shared_ptr<Wsp::Facade::IStorageHealth>>>(std::shared_ptr<Wsp::Facade::IStorageHealth> *,std::shared_ptr<Wsp::Facade::IStorageHealth> * const,std::allocator<std::shared_ptr<Wsp::Facade::IStorageHealth>> &)
0x18001ca74  mov     rcx, [rdi+28h]
0x18001ca78  mov     rdx, [rdi+38h]
0x18001ca7c  sub     rdx, rcx
0x18001ca7f  and     rdx, 0FFFFFFFFFFFFFFF0h
0x18001ca83  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x18001ca88  mov     qword ptr [rdi+28h], 0
0x18001ca90  mov     qword ptr [rdi+30h], 0
0x18001ca98  mov     qword ptr [rdi+38h], 0
0x18001caa0  mov     rcx, rdi
0x18001caa3  add     rsp, 70h
0x18001caa7  pop     r15
0x18001caa9  pop     r14
0x18001caab  pop     r12
0x18001caad  pop     rdi
0x18001caae  pop     rbx
0x18001caaf  jmp     ??1?$deque@U?$counted_ptr@VScheduledTask@TaskManager@ClusWmi@@@cxl@@V?$allocator@U?$counted_ptr@VScheduledTask@TaskManager@ClusWmi@@@cxl@@@std@@@std@@QEAA@XZ; std::deque<cxl::counted_ptr<ClusWmi::TaskManager::ScheduledTask>>::~deque<cxl::counted_ptr<ClusWmi::TaskManager::ScheduledTask>>(void)
```
