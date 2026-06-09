# Wsp::Health2::ResClient::~ResClient(void)

- ea: `0x18007d2f0`
- end: `0x18007d3b9`
- name: `??1ResClient@Health2@Wsp@@QEAA@XZ`
- size: `201`
- prototype: `void __fastcall(Wsp::Health2::ResClient *__hidden this)`
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x18007d3fc`

## callees

- `0x180017fcc`
- `0x1800189bc`
- `0x18001aef0`
- `0x18001d0e4`
- `0x18007d2f0`
- `0x18007db88`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18007d36e`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18007d36e`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18007d34b`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18007d34b`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18007d326`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18007d326`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18007d33b`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18007d33b`

## pseudocode

```c
void __fastcall Wsp::Health2::ResClient::~ResClient(Wsp::Health2::ResClient *this)
{
  _BYTE v2[24]; // [rsp+20h] [rbp-18h] BYREF

  cxl::AcquireWriteLock::AcquireWriteLock((cxl::AcquireWriteLock *)v2, (Wsp::Health2::ResClient *)((char *)this + 104));
  if ( *((_QWORD *)this + 16) )
  {
    SetThreadpoolTimer(*((PTP_TIMER *)this + 15), 0, 0, 0);
    WaitForThreadpoolTimerCallbacks(*((PTP_TIMER *)this + 15), 1);
    CloseThreadpoolTimer(*((PTP_TIMER *)this + 15));
    if ( *((_QWORD *)this + 9) )
      std::_Tree<std::_Tmap_traits<std::wstring,cxl::counted_ptr<Wsp::Health2::CHealthConnection>,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,cxl::counted_ptr<Wsp::Health2::CHealthConnection>>>,0>>::clear((char *)this + 64);
    FreeLibrary(*((HMODULE *)this + 16));
    *((_QWORD *)this + 16) = 0;
  }
  cxl::ScopedResOwner<cxl::NonReentrantRWLock,cxl::AcquireExclusiveTraits<cxl::NonReentrantRWLock>>::Release(v2);
  cxl::NonReentrantRWLock::~NonReentrantRWLock((Wsp::Health2::ResClient *)((char *)this + 104));
  cxl::NonReentrantRWLock::~NonReentrantRWLock((Wsp::Health2::ResClient *)((char *)this + 88));
  std::_Tree<std::_Tmap_traits<std::wstring,cxl::counted_ptr<Wsp::Health2::CHealthConnection>,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,cxl::counted_ptr<Wsp::Health2::CHealthConnection>>>,0>>::~_Tree<std::_Tmap_traits<std::wstring,cxl::counted_ptr<Wsp::Health2::CHealthConnection>,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,cxl::counted_ptr<Wsp::Health2::CHealthConnection>>>,0>>((char *)this + 64);
}

```

## disassembly

```asm
0x18007d2f0  mov     [rsp+arg_0], rbx
0x18007d2f5  mov     [rsp+arg_8], rsi
0x18007d2fa  push    rdi
0x18007d2fb  sub     rsp, 30h
0x18007d2ff  mov     rbx, rcx
0x18007d302  lea     rdx, [rcx+68h]; struct cxl::NonReentrantRWLock *
0x18007d306  lea     rcx, [rsp+38h+var_18]; this
0x18007d30b  call    ??0AcquireWriteLock@cxl@@QEAA@AEAVNonReentrantRWLock@1@@Z; cxl::AcquireWriteLock::AcquireWriteLock(cxl::NonReentrantRWLock &)
0x18007d310  cmp     qword ptr [rbx+80h], 0
0x18007d318  jz      short loc_18007D385
0x18007d31a  xor     r9d, r9d; msWindowLength
0x18007d31d  xor     r8d, r8d; msPeriod
0x18007d320  xor     edx, edx; pftDueTime
0x18007d322  mov     rcx, [rbx+78h]; pti
0x18007d326  call    cs:__imp_SetThreadpoolTimer
0x18007d32d  nop     dword ptr [rax+rax+00h]
0x18007d332  mov     edx, 1; fCancelPendingCallbacks
0x18007d337  mov     rcx, [rbx+78h]; pti
0x18007d33b  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x18007d342  nop     dword ptr [rax+rax+00h]
0x18007d347  mov     rcx, [rbx+78h]; pti
0x18007d34b  call    cs:__imp_CloseThreadpoolTimer
0x18007d352  nop     dword ptr [rax+rax+00h]
0x18007d357  cmp     qword ptr [rbx+48h], 0
0x18007d35c  jbe     short loc_18007D367
0x18007d35e  lea     rcx, [rbx+40h]
0x18007d362  call    ?clear@?$_Tree@V?$_Tmap_traits@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@U?$counted_ptr@VCHealthConnection@Health2@Wsp@@@cxl@@U?$less@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@U?$counted_ptr@VCHealthConnection@Health2@Wsp@@@cxl@@@std@@@2@$0A@@std@@@std@@QEAAXXZ; std::_Tree<std::_Tmap_traits<std::wstring,cxl::counted_ptr<Wsp::Health2::CHealthConnection>,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,cxl::counted_ptr<Wsp::Health2::CHealthConnection>>>,0>>::clear(void)
0x18007d367  mov     rcx, [rbx+80h]; hLibModule
0x18007d36e  call    cs:__imp_FreeLibrary
0x18007d375  nop     dword ptr [rax+rax+00h]
0x18007d37a  mov     qword ptr [rbx+80h], 0
0x18007d385  lea     rcx, [rsp+38h+var_18]
0x18007d38a  call    ?Release@?$ScopedResOwner@VNonReentrantRWLock@cxl@@V?$AcquireExclusiveTraits@VNonReentrantRWLock@cxl@@@2@@cxl@@QEBAXXZ; cxl::ScopedResOwner<cxl::NonReentrantRWLock,cxl::AcquireExclusiveTraits<cxl::NonReentrantRWLock>>::Release(void)
0x18007d38f  lea     rcx, [rbx+68h]; this
0x18007d393  call    ??1NonReentrantRWLock@cxl@@QEAA@XZ; cxl::NonReentrantRWLock::~NonReentrantRWLock(void)
0x18007d398  lea     rcx, [rbx+58h]; this
0x18007d39c  call    ??1NonReentrantRWLock@cxl@@QEAA@XZ; cxl::NonReentrantRWLock::~NonReentrantRWLock(void)
0x18007d3a1  lea     rcx, [rbx+40h]
0x18007d3a5  mov     rbx, [rsp+38h+arg_0]
0x18007d3aa  mov     rsi, [rsp+38h+arg_8]
0x18007d3af  add     rsp, 30h
0x18007d3b3  pop     rdi
0x18007d3b4  jmp     ??1?$_Tree@V?$_Tmap_traits@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@U?$counted_ptr@VCHealthConnection@Health2@Wsp@@@cxl@@U?$less@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@U?$counted_ptr@VCHealthConnection@Health2@Wsp@@@cxl@@@std@@@2@$0A@@std@@@std@@QEAA@XZ; std::_Tree<std::_Tmap_traits<std::wstring,cxl::counted_ptr<Wsp::Health2::CHealthConnection>,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,cxl::counted_ptr<Wsp::Health2::CHealthConnection>>>,0>>::~_Tree<std::_Tmap_traits<std::wstring,cxl::counted_ptr<Wsp::Health2::CHealthConnection>,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,cxl::counted_ptr<Wsp::Health2::CHealthConnection>>>,0>>(void)
```
