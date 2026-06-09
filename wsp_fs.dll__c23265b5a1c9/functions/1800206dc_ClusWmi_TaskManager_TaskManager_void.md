# ClusWmi::TaskManager::~TaskManager(void)

- ea: `0x1800206dc`
- end: `0x180020956`
- name: `??1TaskManager@ClusWmi@@QEAA@XZ`
- size: `634`
- prototype: `void __fastcall(ClusWmi::TaskManager *__hidden this)`
- caller_count: `1`
- callee_count: `20`
- tags: `service_task`

## callers

- `0x18001b8fc`

## callees

- `0x180005e64`
- `0x180015be4`
- `0x18001b148`
- `0x18001b198`
- `0x18001b85c`
- `0x18001bb88`
- `0x18001bd0c`
- `0x18001e0d0`
- `0x18001e134`
- `0x18001fba4`
- `0x18001fda4`
- `0x180020428`
- `0x180020458`
- `0x180020488`
- `0x180020504`
- `0x1800206dc`
- `0x180021ccc`
- `0x180021ea0`
- `0x180022f54`
- `0x1800ab010`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolCleanupGroupMembers` at `0x180020841`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolCleanupGroupMembers` at `0x180020841`

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
    ((void (*)(void))std::_Destroy_range<std::allocator<std::shared_ptr<Wsp::Facade::FileServerFacade>>>)();
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
  std::_Tree<std::_Tmap_traits<std::wstring,std::shared_ptr<ClusApi::IResource>,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::shared_ptr<ClusApi::IResource>>>,0>>::~_Tree<std::_Tmap_traits<std::wstring,std::shared_ptr<ClusApi::IResource>,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::shared_ptr<ClusApi::IResource>>>,0>>(&v1[12]);
  std::_Tree<std::_Tmap_traits<std::wstring,std::shared_ptr<ClusApi::IResource>,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::shared_ptr<ClusApi::IResource>>>,0>>::~_Tree<std::_Tmap_traits<std::wstring,std::shared_ptr<ClusApi::IResource>,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::shared_ptr<ClusApi::IResource>>>,0>>(&v1[10]);
  std::_Tree<std::_Tmap_traits<std::wstring,cxl::counted_ptr<ClusWmi::TaskManager::ScheduledTask>,cxl::CaseInsensitive_LessThan,std::allocator<std::pair<std::wstring const,cxl::counted_ptr<ClusWmi::TaskManager::ScheduledTask>>>,0>>::~_Tree<std::_Tmap_traits<std::wstring,cxl::counted_ptr<ClusWmi::TaskManager::ScheduledTask>,cxl::CaseInsensitive_LessThan,std::allocator<std::pair<std::wstring const,cxl::counted_ptr<ClusWmi::TaskManager::ScheduledTask>>>,0>>(&v1[8]);
  v9 = v1[5].Ptr;
  if ( v9 )
  {
    std::_Destroy_range<std::allocator<std::shared_ptr<Wsp::Facade::FileServerFacade>>>(v9, v1[6].Ptr);
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
0x1800206dc  mov     [rsp+arg_0], rcx
0x1800206e1  push    rbx
0x1800206e2  push    rdi
0x1800206e3  push    r12
0x1800206e5  push    r14
0x1800206e7  push    r15
0x1800206e9  sub     rsp, 70h
0x1800206ed  mov     rdi, rcx
0x1800206f0  lea     rdx, [rcx+78h]; struct cxl::NonReentrantRWLock *
0x1800206f4  lea     rcx, [rsp+98h+var_40]; this
0x1800206f9  call    ??0AcquireWriteLock@cxl@@QEAA@AEAVNonReentrantRWLock@1@@Z; cxl::AcquireWriteLock::AcquireWriteLock(cxl::NonReentrantRWLock &)
0x1800206fe  nop
0x1800206ff  mov     byte ptr [rdi+0C0h], 0
0x180020706  cmp     qword ptr [rdi+20h], 0
0x18002070b  jz      short loc_180020717
0x18002070d  mov     rcx, rdi
0x180020710  call    ?pop_front@?$deque@U?$counted_ptr@VScheduledTask@TaskManager@ClusWmi@@@cxl@@V?$allocator@U?$counted_ptr@VScheduledTask@TaskManager@ClusWmi@@@cxl@@@std@@@std@@QEAAXXZ; std::deque<cxl::counted_ptr<ClusWmi::TaskManager::ScheduledTask>>::pop_front(void)
0x180020715  jmp     short loc_180020706
0x180020717  mov     rcx, [rdi+0C8h]
0x18002071e  test    rcx, rcx
0x180020721  jz      short loc_18002072F
0x180020723  mov     rax, [rcx]
0x180020726  mov     rax, [rax+18h]
0x18002072a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002072f  lea     rdx, [rdi+98h]; struct cxl::NonReentrantRWLock *
0x180020736  lea     rcx, [rsp+98h+var_50]; this
0x18002073b  call    ??0AcquireWriteLock@cxl@@QEAA@AEAVNonReentrantRWLock@1@@Z; cxl::AcquireWriteLock::AcquireWriteLock(cxl::NonReentrantRWLock &)
0x180020740  nop
0x180020741  mov     rdx, [rdi+30h]
0x180020745  mov     rcx, [rdi+28h]
0x180020749  cmp     rcx, rdx
0x18002074c  jz      short loc_18002075B
0x18002074e  call    ??$_Destroy_range@V?$allocator@V?$shared_ptr@VFileServerFacade@Facade@Wsp@@@std@@@std@@@std@@YAXPEAV?$shared_ptr@VFileServerFacade@Facade@Wsp@@@0@QEAV10@AEAV?$allocator@V?$shared_ptr@VFileServerFacade@Facade@Wsp@@@std@@@0@@Z; std::_Destroy_range<std::allocator<std::shared_ptr<Wsp::Facade::FileServerFacade>>>(std::shared_ptr<Wsp::Facade::FileServerFacade> *,std::shared_ptr<Wsp::Facade::FileServerFacade> * const,std::allocator<std::shared_ptr<Wsp::Facade::FileServerFacade>> &)
0x180020753  mov     rax, [rdi+28h]
0x180020757  mov     [rdi+30h], rax
0x18002075b  lea     rdx, [rdi+88h]; struct cxl::NonReentrantRWLock *
0x180020762  lea     rcx, [rsp+98h+var_60]; this
0x180020767  call    ??0AcquireWriteLock@cxl@@QEAA@AEAVNonReentrantRWLock@1@@Z; cxl::AcquireWriteLock::AcquireWriteLock(cxl::NonReentrantRWLock &)
0x18002076c  nop
0x18002076d  mov     rax, [rdi+40h]
0x180020771  mov     rax, [rax]
0x180020774  mov     [rsp+98h+arg_8], rax
0x18002077c  cmp     byte ptr [rax+19h], 0
0x180020780  jnz     short loc_1800207E6
0x180020782  add     rax, 20h ; ' '
0x180020786  mov     [rsp+98h+arg_10], rax
0x18002078e  mov     r14, [rax+20h]
0x180020792  mov     rbx, [r14+20h]
0x180020796  lea     rdx, [rbx+158h]; struct cxl::NonReentrantRWLock *
0x18002079d  lea     rcx, [rsp+98h+var_70]; this
0x1800207a2  call    ??0AcquireReadLock@cxl@@QEAA@AEAVNonReentrantRWLock@1@@Z; cxl::AcquireReadLock::AcquireReadLock(cxl::NonReentrantRWLock &)
0x1800207a7  mov     bl, [rbx+128h]
0x1800207ad  lea     rcx, [rsp+98h+var_70]
0x1800207b2  call    ?Release@?$ScopedResOwner@VNonReentrantRWLock@cxl@@V?$AcquireSharedTraits@VNonReentrantRWLock@cxl@@@2@@cxl@@QEBAXXZ; cxl::ScopedResOwner<cxl::NonReentrantRWLock,cxl::AcquireSharedTraits<cxl::NonReentrantRWLock>>::Release(void)
0x1800207b7  test    bl, bl
0x1800207b9  jz      short loc_1800207C5
0x1800207bb  mov     rcx, [r14+20h]; this
0x1800207bf  call    ?Stop@Task@ClusWmi@@QEAAXXZ; ClusWmi::Task::Stop(void)
0x1800207c4  nop
0x1800207c5  jmp     short loc_1800207CF
0x1800207c7  mov     rdi, [rsp+98h+arg_0]
0x1800207cf  lea     rcx, [rsp+98h+arg_8]
0x1800207d7  call    ??E?$_Tree_unchecked_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@std@@@std@@U_Iterator_base0@2@@std@@QEAAAEAV01@XZ; std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::wstring>>,std::_Iterator_base0>::operator++(void)
0x1800207dc  mov     rax, [rsp+98h+arg_8]
0x1800207e4  jmp     short loc_18002077C
0x1800207e6  lea     r14, [rdi+40h]
0x1800207ea  mov     rbx, [r14]
0x1800207ed  mov     r8, [rbx+8]
0x1800207f1  mov     rdx, r14
0x1800207f4  mov     rcx, r14
0x1800207f7  call    ??$_Erase_tree@V?$allocator@U?$_Tree_node@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@U?$counted_ptr@VScheduledTask@TaskManager@ClusWmi@@@cxl@@@std@@PEAX@std@@@std@@@?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@U?$counted_ptr@VScheduledTask@TaskManager@ClusWmi@@@cxl@@@std@@@std@@@std@@QEAAXAEAV?$allocator@U?$_Tree_node@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@U?$counted_ptr@VScheduledTask@TaskManager@ClusWmi@@@cxl@@@std@@PEAX@std@@@1@PEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@U?$counted_ptr@VScheduledTask@TaskManager@ClusWmi@@@cxl@@@std@@PEAX@1@@Z; std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const,cxl::counted_ptr<ClusWmi::TaskManager::ScheduledTask>>>>::_Erase_tree<std::allocator<std::_Tree_node<std::pair<std::wstring const,cxl::counted_ptr<ClusWmi::TaskManager::ScheduledTask>>,void *>>>(std::allocator<std::_Tree_node<std::pair<std::wstring const,cxl::counted_ptr<ClusWmi::TaskManager::ScheduledTask>>,void *>> &,std::_Tree_node<std::pair<std::wstring const,cxl::counted_ptr<ClusWmi::TaskManager::ScheduledTask>>,void *> *)
0x1800207fc  mov     [rbx+8], rbx
0x180020800  mov     [rbx], rbx
0x180020803  mov     [rbx+10h], rbx
0x180020807  mov     qword ptr [r14+8], 0
0x18002080f  lea     r12, [rdi+0D0h]
0x180020816  mov     rcx, [r12]
0x18002081a  test    rcx, rcx
0x18002081d  jz      short loc_18002082B
0x18002081f  mov     rax, [rcx]
0x180020822  mov     rax, [rax+18h]
0x180020826  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002082b  lea     rbx, [rdi+0D8h]
0x180020832  mov     rcx, [rbx]
0x180020835  mov     r8, rcx; pvCleanupContext
0x180020838  mov     edx, 1; fCancelPendingCallbacks
0x18002083d  mov     rcx, [rcx+18h]; ptpcg
0x180020841  call    cs:__imp_CloseThreadpoolCleanupGroupMembers
0x180020848  nop     dword ptr [rax+rax+00h]
0x18002084d  lea     r15, [rdi+70h]
0x180020851  cmp     qword ptr [r15], 0
0x180020855  jz      short loc_180020860
0x180020857  mov     rcx, [r15]; this
0x18002085a  call    ?Stop@EventThread@ClusApi@@QEAAXXZ; ClusApi::EventThread::Stop(void)
0x18002085f  nop
0x180020860  lea     rcx, [rsp+98h+var_60]
0x180020865  call    ?Release@?$ScopedResOwner@VNonReentrantRWLock@cxl@@V?$AcquireExclusiveTraits@VNonReentrantRWLock@cxl@@@2@@cxl@@QEBAXXZ; cxl::ScopedResOwner<cxl::NonReentrantRWLock,cxl::AcquireExclusiveTraits<cxl::NonReentrantRWLock>>::Release(void)
0x18002086a  nop
0x18002086b  lea     rcx, [rsp+98h+var_50]
0x180020870  call    ?Release@?$ScopedResOwner@VNonReentrantRWLock@cxl@@V?$AcquireExclusiveTraits@VNonReentrantRWLock@cxl@@@2@@cxl@@QEBAXXZ; cxl::ScopedResOwner<cxl::NonReentrantRWLock,cxl::AcquireExclusiveTraits<cxl::NonReentrantRWLock>>::Release(void)
0x180020875  nop
0x180020876  lea     rcx, [rsp+98h+var_40]
0x18002087b  call    ?Release@?$ScopedResOwner@VNonReentrantRWLock@cxl@@V?$AcquireExclusiveTraits@VNonReentrantRWLock@cxl@@@2@@cxl@@QEBAXXZ; cxl::ScopedResOwner<cxl::NonReentrantRWLock,cxl::AcquireExclusiveTraits<cxl::NonReentrantRWLock>>::Release(void)
0x180020880  nop
0x180020881  lea     rcx, [rdi+0E0h]; this
0x180020888  call    ?Clear@Token@cxl@@QEAAXXZ; cxl::Token::Clear(void)
0x18002088d  nop
0x18002088e  mov     rcx, rbx
0x180020891  call    ??1?$counted_ptr@VThreadPool@tp2@cxl@@@cxl@@QEAA@XZ; cxl::counted_ptr<cxl::tp2::ThreadPool>::~counted_ptr<cxl::tp2::ThreadPool>(void)
0x180020896  nop
0x180020897  mov     rcx, r12
0x18002089a  call    ??1?$counted_ptr@VThreadPool@tp2@cxl@@@cxl@@QEAA@XZ; cxl::counted_ptr<cxl::tp2::ThreadPool>::~counted_ptr<cxl::tp2::ThreadPool>(void)
0x18002089f  nop
0x1800208a0  lea     rcx, [rdi+0C8h]
0x1800208a7  call    ??1?$counted_ptr@VThreadPool@tp2@cxl@@@cxl@@QEAA@XZ; cxl::counted_ptr<cxl::tp2::ThreadPool>::~counted_ptr<cxl::tp2::ThreadPool>(void)
0x1800208ac  nop
0x1800208ad  lea     rcx, [rdi+0A8h]; this
0x1800208b4  call    ??1NonReentrantRWLock@cxl@@QEAA@XZ; cxl::NonReentrantRWLock::~NonReentrantRWLock(void)
0x1800208b9  nop
0x1800208ba  lea     rcx, [rdi+98h]; this
0x1800208c1  call    ??1NonReentrantRWLock@cxl@@QEAA@XZ; cxl::NonReentrantRWLock::~NonReentrantRWLock(void)
0x1800208c6  nop
0x1800208c7  lea     rcx, [rdi+88h]; this
0x1800208ce  call    ??1NonReentrantRWLock@cxl@@QEAA@XZ; cxl::NonReentrantRWLock::~NonReentrantRWLock(void)
0x1800208d3  nop
0x1800208d4  lea     rcx, [rdi+78h]; this
0x1800208d8  call    ??1NonReentrantRWLock@cxl@@QEAA@XZ; cxl::NonReentrantRWLock::~NonReentrantRWLock(void)
0x1800208dd  nop
0x1800208de  mov     rcx, r15
0x1800208e1  call    ??1?$unique_ptr@VEventThread@ClusApi@@U?$default_delete@VEventThread@ClusApi@@@std@@@std@@QEAA@XZ; std::unique_ptr<ClusApi::EventThread>::~unique_ptr<ClusApi::EventThread>(void)
0x1800208e6  nop
0x1800208e7  lea     rcx, [rdi+60h]
0x1800208eb  call    ??1?$_Tree@V?$_Tmap_traits@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$shared_ptr@UIResource@ClusApi@@@2@U?$less@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$shared_ptr@UIResource@ClusApi@@@2@@std@@@2@$0A@@std@@@std@@QEAA@XZ; std::_Tree<std::_Tmap_traits<std::wstring,std::shared_ptr<ClusApi::IResource>,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::shared_ptr<ClusApi::IResource>>>,0>>::~_Tree<std::_Tmap_traits<std::wstring,std::shared_ptr<ClusApi::IResource>,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::shared_ptr<ClusApi::IResource>>>,0>>(void)
0x1800208f0  nop
0x1800208f1  lea     rcx, [rdi+50h]
0x1800208f5  call    ??1?$_Tree@V?$_Tmap_traits@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$shared_ptr@UIResource@ClusApi@@@2@U?$less@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$shared_ptr@UIResource@ClusApi@@@2@@std@@@2@$0A@@std@@@std@@QEAA@XZ; std::_Tree<std::_Tmap_traits<std::wstring,std::shared_ptr<ClusApi::IResource>,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::shared_ptr<ClusApi::IResource>>>,0>>::~_Tree<std::_Tmap_traits<std::wstring,std::shared_ptr<ClusApi::IResource>,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::shared_ptr<ClusApi::IResource>>>,0>>(void)
0x1800208fa  nop
0x1800208fb  mov     rcx, r14
0x1800208fe  call    ??1?$_Tree@V?$_Tmap_traits@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@U?$counted_ptr@VScheduledTask@TaskManager@ClusWmi@@@cxl@@UCaseInsensitive_LessThan@4@V?$allocator@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@U?$counted_ptr@VScheduledTask@TaskManager@ClusWmi@@@cxl@@@std@@@2@$0A@@std@@@std@@QEAA@XZ; std::_Tree<std::_Tmap_traits<std::wstring,cxl::counted_ptr<ClusWmi::TaskManager::ScheduledTask>,cxl::CaseInsensitive_LessThan,std::allocator<std::pair<std::wstring const,cxl::counted_ptr<ClusWmi::TaskManager::ScheduledTask>>>,0>>::~_Tree<std::_Tmap_traits<std::wstring,cxl::counted_ptr<ClusWmi::TaskManager::ScheduledTask>,cxl::CaseInsensitive_LessThan,std::allocator<std::pair<std::wstring const,cxl::counted_ptr<ClusWmi::TaskManager::ScheduledTask>>>,0>>(void)
0x180020903  nop
0x180020904  mov     rcx, [rdi+28h]
0x180020908  test    rcx, rcx
0x18002090b  jz      short loc_180020942
0x18002090d  mov     rdx, [rdi+30h]
0x180020911  call    ??$_Destroy_range@V?$allocator@V?$shared_ptr@VFileServerFacade@Facade@Wsp@@@std@@@std@@@std@@YAXPEAV?$shared_ptr@VFileServerFacade@Facade@Wsp@@@0@QEAV10@AEAV?$allocator@V?$shared_ptr@VFileServerFacade@Facade@Wsp@@@std@@@0@@Z; std::_Destroy_range<std::allocator<std::shared_ptr<Wsp::Facade::FileServerFacade>>>(std::shared_ptr<Wsp::Facade::FileServerFacade> *,std::shared_ptr<Wsp::Facade::FileServerFacade> * const,std::allocator<std::shared_ptr<Wsp::Facade::FileServerFacade>> &)
0x180020916  mov     rcx, [rdi+28h]
0x18002091a  mov     rdx, [rdi+38h]
0x18002091e  sub     rdx, rcx
0x180020921  and     rdx, 0FFFFFFFFFFFFFFF0h
0x180020925  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x18002092a  mov     qword ptr [rdi+28h], 0
0x180020932  mov     qword ptr [rdi+30h], 0
0x18002093a  mov     qword ptr [rdi+38h], 0
0x180020942  mov     rcx, rdi
0x180020945  add     rsp, 70h
0x180020949  pop     r15
0x18002094b  pop     r14
0x18002094d  pop     r12
0x18002094f  pop     rdi
0x180020950  pop     rbx
0x180020951  jmp     ??1?$deque@U?$counted_ptr@VScheduledTask@TaskManager@ClusWmi@@@cxl@@V?$allocator@U?$counted_ptr@VScheduledTask@TaskManager@ClusWmi@@@cxl@@@std@@@std@@QEAA@XZ; std::deque<cxl::counted_ptr<ClusWmi::TaskManager::ScheduledTask>>::~deque<cxl::counted_ptr<ClusWmi::TaskManager::ScheduledTask>>(void)
```
