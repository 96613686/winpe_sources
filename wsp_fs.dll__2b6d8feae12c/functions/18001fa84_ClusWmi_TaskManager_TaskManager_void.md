# ClusWmi::TaskManager::~TaskManager(void)

- ea: `0x18001fa84`
- end: `0x18001fcf8`
- name: `??1TaskManager@ClusWmi@@QEAA@XZ`
- size: `628`
- prototype: `void __fastcall(ClusWmi::TaskManager *__hidden this)`
- caller_count: `1`
- callee_count: `20`
- tags: `service_task`

## callers

- `0x18001ae8c`

## callees

- `0x180005d94`
- `0x1800154e0`
- `0x18001a728`
- `0x18001a770`
- `0x18001adf0`
- `0x18001b118`
- `0x18001b28c`
- `0x18001d550`
- `0x18001d5a8`
- `0x18001ef74`
- `0x18001f17c`
- `0x18001f7ec`
- `0x18001f81c`
- `0x18001f84c`
- `0x18001f8c8`
- `0x18001fa84`
- `0x180021024`
- `0x1800211ec`
- `0x180022214`
- `0x1800a9010`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolCleanupGroupMembers` at `0x18001fbe9`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolCleanupGroupMembers` at `0x18001fbe9`

## pseudocode

```c
// Hidden C++ exception states: #wind=17
void __fastcall ClusWmi::TaskManager::~TaskManager(RTL_SRWLOCK *this)
{
  RTL_SRWLOCK *v1; // rdi
  PVOID Ptr; // rcx
  PVOID v3; // rdx
  PVOID v4; // rcx
  __int64 v5; // rax
  __int64 v6; // r14
  __int64 v7; // rbx
  char v8; // bl
  __int64 **v9; // rbx
  PVOID v10; // rcx
  PVOID v11; // rcx
  struct cxl::TextWriter *v12; // rbx
  const cxl::Exception *v13; // [rsp+20h] [rbp-78h] BYREF
  _BYTE v14[16]; // [rsp+28h] [rbp-70h] BYREF
  _BYTE v15[16]; // [rsp+38h] [rbp-60h] BYREF
  _BYTE v16[16]; // [rsp+48h] [rbp-50h] BYREF
  _BYTE v17[64]; // [rsp+58h] [rbp-40h] BYREF
  __int64 v20; // [rsp+A8h] [rbp+10h] BYREF
  __int64 v21; // [rsp+B0h] [rbp+18h]

  v1 = this;
  cxl::AcquireWriteLock::AcquireWriteLock((cxl::AcquireWriteLock *)v17, this + 15);
  LOBYTE(v1[24].Ptr) = 0;
  while ( v1[4].Ptr )
    std::deque<cxl::counted_ptr<ClusWmi::TaskManager::ScheduledTask>>::pop_front(v1);
  Ptr = v1[25].Ptr;
  if ( Ptr )
    (*(void (__fastcall **)(PVOID))(*(_QWORD *)Ptr + 24LL))(Ptr);
  cxl::AcquireWriteLock::AcquireWriteLock((cxl::AcquireWriteLock *)v16, v1 + 19);
  v3 = v1[6].Ptr;
  v4 = v1[5].Ptr;
  if ( v4 != v3 )
  {
    std::_Destroy_range<std::allocator<std::shared_ptr<Wsp::Facade::FileServerFacade>>>(v4, v3);
    v1[6].Ptr = v1[5].Ptr;
  }
  cxl::AcquireWriteLock::AcquireWriteLock((cxl::AcquireWriteLock *)v15, v1 + 17);
  v5 = *(_QWORD *)v1[8].Ptr;
  v20 = v5;
  while ( !*(_BYTE *)(v5 + 25) )
  {
    v21 = v5 + 32;
    v6 = *(_QWORD *)(v5 + 64);
    v7 = *(_QWORD *)(v6 + 32);
    cxl::AcquireReadLock::AcquireReadLock((cxl::AcquireReadLock *)v14, (struct cxl::NonReentrantRWLock *)(v7 + 344));
    v8 = *(_BYTE *)(v7 + 296);
    cxl::ScopedResOwner<cxl::NonReentrantRWLock,cxl::AcquireSharedTraits<cxl::NonReentrantRWLock>>::Release(v14);
    try
    {
      if ( v8 )
        ClusWmi::Task::Stop(*(ClusWmi::Task **)(v6 + 32));
    }
    catch ( const cxl::Exception *v13 )
    {
      v12 = (struct cxl::TraceManager *)((char *)cxl::TraceManager::Instance() + 40);
      ClusWmi::TaskManager::ScheduledTask::get_id(*(_QWORD *)(v21 + 32));
      cxl::TextWriter::WriteLine<char,std::wstring,cxl::Exception>(
        v12,
        "The task '{0}' could not be canceled due to {1}.");
      v1 = this;
    }
    std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::wstring>>,std::_Iterator_base0>::operator++(&v20);
    v5 = v20;
  }
  v9 = (__int64 **)v1[8].Ptr;
  std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const,cxl::counted_ptr<ClusWmi::TaskManager::ScheduledTask>>>>::_Erase_tree<std::allocator<std::_Tree_node<std::pair<std::wstring const,cxl::counted_ptr<ClusWmi::TaskManager::ScheduledTask>>,void *>>>(
    (__int64)&v1[8],
    (__int64)&v1[8],
    v9[1]);
  v9[1] = (__int64 *)v9;
  *v9 = (__int64 *)v9;
  v9[2] = (__int64 *)v9;
  v1[9].Ptr = 0;
  v10 = v1[26].Ptr;
  if ( v10 )
    (*(void (__fastcall **)(PVOID))(*(_QWORD *)v10 + 24LL))(v10);
  CloseThreadpoolCleanupGroupMembers(*((PTP_CLEANUP_GROUP *)v1[27].Ptr + 3), 1, v1[27].Ptr);
  if ( v1[14].Ptr )
    ClusApi::EventThread::Stop((ClusApi::EventThread *)v1[14].Ptr);
  cxl::ScopedResOwner<cxl::NonReentrantRWLock,cxl::AcquireExclusiveTraits<cxl::NonReentrantRWLock>>::Release(v15);
  cxl::ScopedResOwner<cxl::NonReentrantRWLock,cxl::AcquireExclusiveTraits<cxl::NonReentrantRWLock>>::Release(v16);
  cxl::ScopedResOwner<cxl::NonReentrantRWLock,cxl::AcquireExclusiveTraits<cxl::NonReentrantRWLock>>::Release(v17);
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
  v11 = v1[5].Ptr;
  if ( v11 )
  {
    std::_Destroy_range<std::allocator<std::shared_ptr<Wsp::Facade::FileServerFacade>>>(v11, v1[6].Ptr);
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
0x18001fa84  mov     [rsp+arg_0], rcx
0x18001fa89  push    rbx
0x18001fa8a  push    rdi
0x18001fa8b  push    r12
0x18001fa8d  push    r14
0x18001fa8f  push    r15
0x18001fa91  sub     rsp, 70h
0x18001fa95  mov     rdi, rcx
0x18001fa98  lea     rdx, [rcx+78h]; struct cxl::NonReentrantRWLock *
0x18001fa9c  lea     rcx, [rsp+98h+var_40]; this
0x18001faa1  call    ??0AcquireWriteLock@cxl@@QEAA@AEAVNonReentrantRWLock@1@@Z; cxl::AcquireWriteLock::AcquireWriteLock(cxl::NonReentrantRWLock &)
0x18001faa6  nop
0x18001faa7  mov     byte ptr [rdi+0C0h], 0
0x18001faae  cmp     qword ptr [rdi+20h], 0
0x18001fab3  jz      short loc_18001FABF
0x18001fab5  mov     rcx, rdi
0x18001fab8  call    ?pop_front@?$deque@U?$counted_ptr@VScheduledTask@TaskManager@ClusWmi@@@cxl@@V?$allocator@U?$counted_ptr@VScheduledTask@TaskManager@ClusWmi@@@cxl@@@std@@@std@@QEAAXXZ; std::deque<cxl::counted_ptr<ClusWmi::TaskManager::ScheduledTask>>::pop_front(void)
0x18001fabd  jmp     short loc_18001FAAE
0x18001fabf  mov     rcx, [rdi+0C8h]
0x18001fac6  test    rcx, rcx
0x18001fac9  jz      short loc_18001FAD7
0x18001facb  mov     rax, [rcx]
0x18001face  mov     rax, [rax+18h]
0x18001fad2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001fad7  lea     rdx, [rdi+98h]; struct cxl::NonReentrantRWLock *
0x18001fade  lea     rcx, [rsp+98h+var_50]; this
0x18001fae3  call    ??0AcquireWriteLock@cxl@@QEAA@AEAVNonReentrantRWLock@1@@Z; cxl::AcquireWriteLock::AcquireWriteLock(cxl::NonReentrantRWLock &)
0x18001fae8  nop
0x18001fae9  mov     rdx, [rdi+30h]
0x18001faed  mov     rcx, [rdi+28h]
0x18001faf1  cmp     rcx, rdx
0x18001faf4  jz      short loc_18001FB03
0x18001faf6  call    ??$_Destroy_range@V?$allocator@V?$shared_ptr@VFileServerFacade@Facade@Wsp@@@std@@@std@@@std@@YAXPEAV?$shared_ptr@VFileServerFacade@Facade@Wsp@@@0@QEAV10@AEAV?$allocator@V?$shared_ptr@VFileServerFacade@Facade@Wsp@@@std@@@0@@Z; std::_Destroy_range<std::allocator<std::shared_ptr<Wsp::Facade::FileServerFacade>>>(std::shared_ptr<Wsp::Facade::FileServerFacade> *,std::shared_ptr<Wsp::Facade::FileServerFacade> * const,std::allocator<std::shared_ptr<Wsp::Facade::FileServerFacade>> &)
0x18001fafb  mov     rax, [rdi+28h]
0x18001faff  mov     [rdi+30h], rax
0x18001fb03  lea     rdx, [rdi+88h]; struct cxl::NonReentrantRWLock *
0x18001fb0a  lea     rcx, [rsp+98h+var_60]; this
0x18001fb0f  call    ??0AcquireWriteLock@cxl@@QEAA@AEAVNonReentrantRWLock@1@@Z; cxl::AcquireWriteLock::AcquireWriteLock(cxl::NonReentrantRWLock &)
0x18001fb14  nop
0x18001fb15  mov     rax, [rdi+40h]
0x18001fb19  mov     rax, [rax]
0x18001fb1c  mov     [rsp+98h+arg_8], rax
0x18001fb24  cmp     byte ptr [rax+19h], 0
0x18001fb28  jnz     short loc_18001FB8E
0x18001fb2a  add     rax, 20h ; ' '
0x18001fb2e  mov     [rsp+98h+arg_10], rax
0x18001fb36  mov     r14, [rax+20h]
0x18001fb3a  mov     rbx, [r14+20h]
0x18001fb3e  lea     rdx, [rbx+158h]; struct cxl::NonReentrantRWLock *
0x18001fb45  lea     rcx, [rsp+98h+var_70]; this
0x18001fb4a  call    ??0AcquireReadLock@cxl@@QEAA@AEAVNonReentrantRWLock@1@@Z; cxl::AcquireReadLock::AcquireReadLock(cxl::NonReentrantRWLock &)
0x18001fb4f  mov     bl, [rbx+128h]
0x18001fb55  lea     rcx, [rsp+98h+var_70]
0x18001fb5a  call    ?Release@?$ScopedResOwner@VNonReentrantRWLock@cxl@@V?$AcquireSharedTraits@VNonReentrantRWLock@cxl@@@2@@cxl@@QEBAXXZ; cxl::ScopedResOwner<cxl::NonReentrantRWLock,cxl::AcquireSharedTraits<cxl::NonReentrantRWLock>>::Release(void)
0x18001fb5f  test    bl, bl
0x18001fb61  jz      short loc_18001FB6D
0x18001fb63  mov     rcx, [r14+20h]; this
0x18001fb67  call    ?Stop@Task@ClusWmi@@QEAAXXZ; ClusWmi::Task::Stop(void)
0x18001fb6c  nop
0x18001fb6d  jmp     short loc_18001FB77
0x18001fb6f  mov     rdi, [rsp+98h+arg_0]
0x18001fb77  lea     rcx, [rsp+98h+arg_8]
0x18001fb7f  call    ??E?$_Tree_unchecked_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@std@@@std@@U_Iterator_base0@2@@std@@QEAAAEAV01@XZ; std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::wstring>>,std::_Iterator_base0>::operator++(void)
0x18001fb84  mov     rax, [rsp+98h+arg_8]
0x18001fb8c  jmp     short loc_18001FB24
0x18001fb8e  lea     r14, [rdi+40h]
0x18001fb92  mov     rbx, [r14]
0x18001fb95  mov     r8, [rbx+8]
0x18001fb99  mov     rdx, r14
0x18001fb9c  mov     rcx, r14
0x18001fb9f  call    ??$_Erase_tree@V?$allocator@U?$_Tree_node@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@U?$counted_ptr@VScheduledTask@TaskManager@ClusWmi@@@cxl@@@std@@PEAX@std@@@std@@@?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@U?$counted_ptr@VScheduledTask@TaskManager@ClusWmi@@@cxl@@@std@@@std@@@std@@QEAAXAEAV?$allocator@U?$_Tree_node@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@U?$counted_ptr@VScheduledTask@TaskManager@ClusWmi@@@cxl@@@std@@PEAX@std@@@1@PEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@U?$counted_ptr@VScheduledTask@TaskManager@ClusWmi@@@cxl@@@std@@PEAX@1@@Z; std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const,cxl::counted_ptr<ClusWmi::TaskManager::ScheduledTask>>>>::_Erase_tree<std::allocator<std::_Tree_node<std::pair<std::wstring const,cxl::counted_ptr<ClusWmi::TaskManager::ScheduledTask>>,void *>>>(std::allocator<std::_Tree_node<std::pair<std::wstring const,cxl::counted_ptr<ClusWmi::TaskManager::ScheduledTask>>,void *>> &,std::_Tree_node<std::pair<std::wstring const,cxl::counted_ptr<ClusWmi::TaskManager::ScheduledTask>>,void *> *)
0x18001fba4  mov     [rbx+8], rbx
0x18001fba8  mov     [rbx], rbx
0x18001fbab  mov     [rbx+10h], rbx
0x18001fbaf  mov     qword ptr [r14+8], 0
0x18001fbb7  lea     r12, [rdi+0D0h]
0x18001fbbe  mov     rcx, [r12]
0x18001fbc2  test    rcx, rcx
0x18001fbc5  jz      short loc_18001FBD3
0x18001fbc7  mov     rax, [rcx]
0x18001fbca  mov     rax, [rax+18h]
0x18001fbce  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001fbd3  lea     rbx, [rdi+0D8h]
0x18001fbda  mov     rcx, [rbx]
0x18001fbdd  mov     r8, rcx; pvCleanupContext
0x18001fbe0  mov     edx, 1; fCancelPendingCallbacks
0x18001fbe5  mov     rcx, [rcx+18h]; ptpcg
0x18001fbe9  call    cs:__imp_CloseThreadpoolCleanupGroupMembers
0x18001fbef  lea     r15, [rdi+70h]
0x18001fbf3  cmp     qword ptr [r15], 0
0x18001fbf7  jz      short loc_18001FC02
0x18001fbf9  mov     rcx, [r15]; this
0x18001fbfc  call    ?Stop@EventThread@ClusApi@@QEAAXXZ; ClusApi::EventThread::Stop(void)
0x18001fc01  nop
0x18001fc02  lea     rcx, [rsp+98h+var_60]
0x18001fc07  call    ?Release@?$ScopedResOwner@VNonReentrantRWLock@cxl@@V?$AcquireExclusiveTraits@VNonReentrantRWLock@cxl@@@2@@cxl@@QEBAXXZ; cxl::ScopedResOwner<cxl::NonReentrantRWLock,cxl::AcquireExclusiveTraits<cxl::NonReentrantRWLock>>::Release(void)
0x18001fc0c  nop
0x18001fc0d  lea     rcx, [rsp+98h+var_50]
0x18001fc12  call    ?Release@?$ScopedResOwner@VNonReentrantRWLock@cxl@@V?$AcquireExclusiveTraits@VNonReentrantRWLock@cxl@@@2@@cxl@@QEBAXXZ; cxl::ScopedResOwner<cxl::NonReentrantRWLock,cxl::AcquireExclusiveTraits<cxl::NonReentrantRWLock>>::Release(void)
0x18001fc17  nop
0x18001fc18  lea     rcx, [rsp+98h+var_40]
0x18001fc1d  call    ?Release@?$ScopedResOwner@VNonReentrantRWLock@cxl@@V?$AcquireExclusiveTraits@VNonReentrantRWLock@cxl@@@2@@cxl@@QEBAXXZ; cxl::ScopedResOwner<cxl::NonReentrantRWLock,cxl::AcquireExclusiveTraits<cxl::NonReentrantRWLock>>::Release(void)
0x18001fc22  nop
0x18001fc23  lea     rcx, [rdi+0E0h]; this
0x18001fc2a  call    ?Clear@Token@cxl@@QEAAXXZ; cxl::Token::Clear(void)
0x18001fc2f  nop
0x18001fc30  mov     rcx, rbx
0x18001fc33  call    ??1?$counted_ptr@VThreadPool@tp2@cxl@@@cxl@@QEAA@XZ; cxl::counted_ptr<cxl::tp2::ThreadPool>::~counted_ptr<cxl::tp2::ThreadPool>(void)
0x18001fc38  nop
0x18001fc39  mov     rcx, r12
0x18001fc3c  call    ??1?$counted_ptr@VThreadPool@tp2@cxl@@@cxl@@QEAA@XZ; cxl::counted_ptr<cxl::tp2::ThreadPool>::~counted_ptr<cxl::tp2::ThreadPool>(void)
0x18001fc41  nop
0x18001fc42  lea     rcx, [rdi+0C8h]
0x18001fc49  call    ??1?$counted_ptr@VThreadPool@tp2@cxl@@@cxl@@QEAA@XZ; cxl::counted_ptr<cxl::tp2::ThreadPool>::~counted_ptr<cxl::tp2::ThreadPool>(void)
0x18001fc4e  nop
0x18001fc4f  lea     rcx, [rdi+0A8h]; this
0x18001fc56  call    ??1NonReentrantRWLock@cxl@@QEAA@XZ; cxl::NonReentrantRWLock::~NonReentrantRWLock(void)
0x18001fc5b  nop
0x18001fc5c  lea     rcx, [rdi+98h]; this
0x18001fc63  call    ??1NonReentrantRWLock@cxl@@QEAA@XZ; cxl::NonReentrantRWLock::~NonReentrantRWLock(void)
0x18001fc68  nop
0x18001fc69  lea     rcx, [rdi+88h]; this
0x18001fc70  call    ??1NonReentrantRWLock@cxl@@QEAA@XZ; cxl::NonReentrantRWLock::~NonReentrantRWLock(void)
0x18001fc75  nop
0x18001fc76  lea     rcx, [rdi+78h]; this
0x18001fc7a  call    ??1NonReentrantRWLock@cxl@@QEAA@XZ; cxl::NonReentrantRWLock::~NonReentrantRWLock(void)
0x18001fc7f  nop
0x18001fc80  mov     rcx, r15
0x18001fc83  call    ??1?$unique_ptr@VEventThread@ClusApi@@U?$default_delete@VEventThread@ClusApi@@@std@@@std@@QEAA@XZ; std::unique_ptr<ClusApi::EventThread>::~unique_ptr<ClusApi::EventThread>(void)
0x18001fc88  nop
0x18001fc89  lea     rcx, [rdi+60h]
0x18001fc8d  call    ??1?$_Tree@V?$_Tmap_traits@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$shared_ptr@UIResource@ClusApi@@@2@U?$less@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$shared_ptr@UIResource@ClusApi@@@2@@std@@@2@$0A@@std@@@std@@QEAA@XZ; std::_Tree<std::_Tmap_traits<std::wstring,std::shared_ptr<ClusApi::IResource>,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::shared_ptr<ClusApi::IResource>>>,0>>::~_Tree<std::_Tmap_traits<std::wstring,std::shared_ptr<ClusApi::IResource>,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::shared_ptr<ClusApi::IResource>>>,0>>(void)
0x18001fc92  nop
0x18001fc93  lea     rcx, [rdi+50h]
0x18001fc97  call    ??1?$_Tree@V?$_Tmap_traits@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$shared_ptr@UIResource@ClusApi@@@2@U?$less@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$shared_ptr@UIResource@ClusApi@@@2@@std@@@2@$0A@@std@@@std@@QEAA@XZ; std::_Tree<std::_Tmap_traits<std::wstring,std::shared_ptr<ClusApi::IResource>,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::shared_ptr<ClusApi::IResource>>>,0>>::~_Tree<std::_Tmap_traits<std::wstring,std::shared_ptr<ClusApi::IResource>,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::shared_ptr<ClusApi::IResource>>>,0>>(void)
0x18001fc9c  nop
0x18001fc9d  mov     rcx, r14
0x18001fca0  call    ??1?$_Tree@V?$_Tmap_traits@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@U?$counted_ptr@VScheduledTask@TaskManager@ClusWmi@@@cxl@@UCaseInsensitive_LessThan@4@V?$allocator@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@U?$counted_ptr@VScheduledTask@TaskManager@ClusWmi@@@cxl@@@std@@@2@$0A@@std@@@std@@QEAA@XZ; std::_Tree<std::_Tmap_traits<std::wstring,cxl::counted_ptr<ClusWmi::TaskManager::ScheduledTask>,cxl::CaseInsensitive_LessThan,std::allocator<std::pair<std::wstring const,cxl::counted_ptr<ClusWmi::TaskManager::ScheduledTask>>>,0>>::~_Tree<std::_Tmap_traits<std::wstring,cxl::counted_ptr<ClusWmi::TaskManager::ScheduledTask>,cxl::CaseInsensitive_LessThan,std::allocator<std::pair<std::wstring const,cxl::counted_ptr<ClusWmi::TaskManager::ScheduledTask>>>,0>>(void)
0x18001fca5  nop
0x18001fca6  mov     rcx, [rdi+28h]
0x18001fcaa  test    rcx, rcx
0x18001fcad  jz      short loc_18001FCE4
0x18001fcaf  mov     rdx, [rdi+30h]
0x18001fcb3  call    ??$_Destroy_range@V?$allocator@V?$shared_ptr@VFileServerFacade@Facade@Wsp@@@std@@@std@@@std@@YAXPEAV?$shared_ptr@VFileServerFacade@Facade@Wsp@@@0@QEAV10@AEAV?$allocator@V?$shared_ptr@VFileServerFacade@Facade@Wsp@@@std@@@0@@Z; std::_Destroy_range<std::allocator<std::shared_ptr<Wsp::Facade::FileServerFacade>>>(std::shared_ptr<Wsp::Facade::FileServerFacade> *,std::shared_ptr<Wsp::Facade::FileServerFacade> * const,std::allocator<std::shared_ptr<Wsp::Facade::FileServerFacade>> &)
0x18001fcb8  mov     rcx, [rdi+28h]
0x18001fcbc  mov     rdx, [rdi+38h]
0x18001fcc0  sub     rdx, rcx
0x18001fcc3  and     rdx, 0FFFFFFFFFFFFFFF0h
0x18001fcc7  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x18001fccc  mov     qword ptr [rdi+28h], 0
0x18001fcd4  mov     qword ptr [rdi+30h], 0
0x18001fcdc  mov     qword ptr [rdi+38h], 0
0x18001fce4  mov     rcx, rdi
0x18001fce7  add     rsp, 70h
0x18001fceb  pop     r15
0x18001fced  pop     r14
0x18001fcef  pop     r12
0x18001fcf1  pop     rdi
0x18001fcf2  pop     rbx
0x18001fcf3  jmp     ??1?$deque@U?$counted_ptr@VScheduledTask@TaskManager@ClusWmi@@@cxl@@V?$allocator@U?$counted_ptr@VScheduledTask@TaskManager@ClusWmi@@@cxl@@@std@@@std@@QEAA@XZ; std::deque<cxl::counted_ptr<ClusWmi::TaskManager::ScheduledTask>>::~deque<cxl::counted_ptr<ClusWmi::TaskManager::ScheduledTask>>(void)
```
