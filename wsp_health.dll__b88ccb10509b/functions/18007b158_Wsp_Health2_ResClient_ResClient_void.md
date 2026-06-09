# Wsp::Health2::ResClient::~ResClient(void)

- ea: `0x18007b158`
- end: `0x18007b209`
- name: `??1ResClient@Health2@Wsp@@QEAA@XZ`
- size: `177`
- prototype: `void __fastcall(Wsp::Health2::ResClient *__hidden this)`
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x18007b24c`

## callees

- `0x180017688`
- `0x180018030`
- `0x18001a470`
- `0x18001c5a8`
- `0x18007b158`
- `0x18007b958`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18007b1c4`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18007b1c4`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18007b1a7`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18007b1a7`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18007b18e`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18007b18e`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18007b19d`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18007b19d`

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
0x18007b158  mov     [rsp+arg_0], rbx
0x18007b15d  mov     [rsp+arg_8], rsi
0x18007b162  push    rdi
0x18007b163  sub     rsp, 30h
0x18007b167  mov     rbx, rcx
0x18007b16a  lea     rdx, [rcx+68h]; struct cxl::NonReentrantRWLock *
0x18007b16e  lea     rcx, [rsp+38h+var_18]; this
0x18007b173  call    ??0AcquireWriteLock@cxl@@QEAA@AEAVNonReentrantRWLock@1@@Z; cxl::AcquireWriteLock::AcquireWriteLock(cxl::NonReentrantRWLock &)
0x18007b178  cmp     qword ptr [rbx+80h], 0
0x18007b180  jz      short loc_18007B1D5
0x18007b182  xor     r9d, r9d; msWindowLength
0x18007b185  xor     r8d, r8d; msPeriod
0x18007b188  xor     edx, edx; pftDueTime
0x18007b18a  mov     rcx, [rbx+78h]; pti
0x18007b18e  call    cs:__imp_SetThreadpoolTimer
0x18007b194  mov     edx, 1; fCancelPendingCallbacks
0x18007b199  mov     rcx, [rbx+78h]; pti
0x18007b19d  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x18007b1a3  mov     rcx, [rbx+78h]; pti
0x18007b1a7  call    cs:__imp_CloseThreadpoolTimer
0x18007b1ad  cmp     qword ptr [rbx+48h], 0
0x18007b1b2  jbe     short loc_18007B1BD
0x18007b1b4  lea     rcx, [rbx+40h]
0x18007b1b8  call    ?clear@?$_Tree@V?$_Tmap_traits@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@U?$counted_ptr@VCHealthConnection@Health2@Wsp@@@cxl@@U?$less@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@U?$counted_ptr@VCHealthConnection@Health2@Wsp@@@cxl@@@std@@@2@$0A@@std@@@std@@QEAAXXZ; std::_Tree<std::_Tmap_traits<std::wstring,cxl::counted_ptr<Wsp::Health2::CHealthConnection>,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,cxl::counted_ptr<Wsp::Health2::CHealthConnection>>>,0>>::clear(void)
0x18007b1bd  mov     rcx, [rbx+80h]; hLibModule
0x18007b1c4  call    cs:__imp_FreeLibrary
0x18007b1ca  mov     qword ptr [rbx+80h], 0
0x18007b1d5  lea     rcx, [rsp+38h+var_18]
0x18007b1da  call    ?Release@?$ScopedResOwner@VNonReentrantRWLock@cxl@@V?$AcquireExclusiveTraits@VNonReentrantRWLock@cxl@@@2@@cxl@@QEBAXXZ; cxl::ScopedResOwner<cxl::NonReentrantRWLock,cxl::AcquireExclusiveTraits<cxl::NonReentrantRWLock>>::Release(void)
0x18007b1df  lea     rcx, [rbx+68h]; this
0x18007b1e3  call    ??1NonReentrantRWLock@cxl@@QEAA@XZ; cxl::NonReentrantRWLock::~NonReentrantRWLock(void)
0x18007b1e8  lea     rcx, [rbx+58h]; this
0x18007b1ec  call    ??1NonReentrantRWLock@cxl@@QEAA@XZ; cxl::NonReentrantRWLock::~NonReentrantRWLock(void)
0x18007b1f1  lea     rcx, [rbx+40h]
0x18007b1f5  mov     rbx, [rsp+38h+arg_0]
0x18007b1fa  mov     rsi, [rsp+38h+arg_8]
0x18007b1ff  add     rsp, 30h
0x18007b203  pop     rdi
0x18007b204  jmp     ??1?$_Tree@V?$_Tmap_traits@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@U?$counted_ptr@VCHealthConnection@Health2@Wsp@@@cxl@@U?$less@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@U?$counted_ptr@VCHealthConnection@Health2@Wsp@@@cxl@@@std@@@2@$0A@@std@@@std@@QEAA@XZ; std::_Tree<std::_Tmap_traits<std::wstring,cxl::counted_ptr<Wsp::Health2::CHealthConnection>,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,cxl::counted_ptr<Wsp::Health2::CHealthConnection>>>,0>>::~_Tree<std::_Tmap_traits<std::wstring,cxl::counted_ptr<Wsp::Health2::CHealthConnection>,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,cxl::counted_ptr<Wsp::Health2::CHealthConnection>>>,0>>(void)
```
