# SleepStudy::StopTrackingInterface(_NET_LUID_LH const &)

- ea: `0x180035bc4`
- end: `0x180035d36`
- name: `?StopTrackingInterface@SleepStudy@@YAXAEBT_NET_LUID_LH@@@Z`
- size: `370`
- prototype: `void __fastcall(SleepStudy *__hidden this, const union _NET_LUID_LH *)`
- caller_count: `3`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callers

- `0x180035df0`
- `0x18004b494`
- `0x1800543d4`

## callees

- `0x180010080`
- `0x180035bc4`
- `0x18007103c`
- `0x1800afe44`
- `0x1800afef8`
- `0x1800f7010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180035c41`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180035c41`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180035c7a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180035d29`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180035c7a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180035d29`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180035c1a`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180035c1a`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180035be5`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180035be5`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x180035c8f`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x180035c8f`

## string_xrefs

- `0x180035ced`: `onecoreuap\net\wcm\service\base\server\sleepstudy.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall SleepStudy::StopTrackingInterface(SleepStudy *this, const union _NET_LUID_LH *a2)
{
  volatile signed __int32 *v3; // rbx
  __int64 v4; // rdi
  const char *v5; // r9
  _QWORD v6[2]; // [rsp+20h] [rbp-28h] BYREF
  __int128 v7; // [rsp+30h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]

  v7 = 0;
  AcquireSRWLockShared(&SleepStudy::Singleton::s_lock);
  v3 = (volatile signed __int32 *)qword_18013EFD8;
  if ( qword_18013EFD8 )
  {
    _InterlockedIncrement((volatile signed __int32 *)qword_18013EFD8 + 2);
    v3 = (volatile signed __int32 *)qword_18013EFD8;
  }
  v4 = *(_QWORD *)&SleepStudy::Singleton::s_instance;
  *(_QWORD *)&v7 = *(_QWORD *)&SleepStudy::Singleton::s_instance;
  *((_QWORD *)&v7 + 1) = v3;
  ReleaseSRWLockShared(&SleepStudy::Singleton::s_lock);
  try
  {
    if ( v4 )
    {
      v6[0] = v4;
      v6[1] = *(_QWORD *)this;
      EnterCriticalSection((LPCRITICAL_SECTION)(v4 + 128));
      if ( *(_BYTE *)(v4 + 392) )
      {
        if ( v4 != -128 )
          LeaveCriticalSection((LPCRITICAL_SECTION)(v4 + 128));
      }
      else
      {
        if ( *(_DWORD *)(v4 + 120) == 1 )
          std::deque_std::function_void___cdecl_void___std::allocator_std::function_void___cdecl_void______::emplace_back__SleepStudy::StopTrackingInterface_::_3_::_lambda_1___(
            v4 + 272,
            v6);
        else
          std::deque_std::variant_std::function_void___cdecl_void___std::shared_ptr_WcmCommon::BaseThreadPoolWaitableResult____std::allocator_std::variant_std::function_void___cdecl_void___std::shared_ptr_WcmCommon::BaseThreadPoolWaitableResult_______::emplace_back__SleepStudy::StopTrackingInterface_::_3_::_lambda_1___(
            v4 + 352,
            v6);
        if ( v4 != -128 )
          LeaveCriticalSection((LPCRITICAL_SECTION)(v4 + 128));
        _InterlockedIncrement64((volatile signed __int64 *)(v4 + 256));
        SubmitThreadpoolWork(*(PTP_WORK *)(v4 + 248));
      }
      if ( v3 )
      {
        if ( _InterlockedExchangeAdd(v3 + 2, 0xFFFFFFFF) == 1 )
        {
          (**(void (__fastcall ***)(volatile signed __int32 *))v3)(v3);
          if ( !_InterlockedDecrement(v3 + 3) )
            (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v3 + 8LL))(v3);
        }
      }
    }
    else
    {
      wil::details::in1diag3::Log_Win32(
        retaddr,
        (void *)0x2C6,
        (unsigned int)"onecoreuap\\net\\wcm\\service\\base\\server\\sleepstudy.cpp",
        (const char *)0x139F,
        v6[0]);
      if ( v3 )
        std::_Ref_count_base::_Decref((std::_Ref_count_base *)v3);
    }
  }
  catch ( ... )
  {
    wil::details::in1diag3::Log_CaughtException(
      retaddr,
      (void *)0x2F0,
      (unsigned int)"onecoreuap\\net\\wcm\\service\\base\\server\\sleepstudy.cpp",
      v5);
  }
}

```

## disassembly

```asm
0x180035bc4  mov     [rsp+arg_0], rbx
0x180035bc9  mov     [rsp+arg_10], rsi
0x180035bce  push    rdi
0x180035bcf  sub     rsp, 40h
0x180035bd3  mov     rsi, rcx
0x180035bd6  xorps   xmm0, xmm0
0x180035bd9  movups  [rsp+48h+var_18], xmm0
0x180035bde  lea     rcx, ?s_lock@Singleton@SleepStudy@@0Vsrwlock@wil@@A; SRWLock
0x180035be5  call    cs:__imp_AcquireSRWLockShared
0x180035beb  mov     rbx, cs:qword_18013EFD8
0x180035bf2  test    rbx, rbx
0x180035bf5  jz      short loc_180035C02
0x180035bf7  lock inc dword ptr [rbx+8]
0x180035bfb  mov     rbx, cs:qword_18013EFD8
0x180035c02  mov     rdi, cs:?s_instance@Singleton@SleepStudy@@0V?$shared_ptr@VSingleton@SleepStudy@@@std@@A; std::shared_ptr<SleepStudy::Singleton> SleepStudy::Singleton::s_instance
0x180035c09  mov     qword ptr [rsp+48h+var_18], rdi
0x180035c0e  mov     qword ptr [rsp+48h+var_18+8], rbx
0x180035c13  lea     rcx, ?s_lock@Singleton@SleepStudy@@0Vsrwlock@wil@@A; SRWLock
0x180035c1a  call    cs:__imp_ReleaseSRWLockShared
0x180035c20  nop
0x180035c21  test    rdi, rdi
0x180035c24  jz      loc_180035CE2
0x180035c2a  mov     [rsp+48h+var_28], rdi
0x180035c2f  mov     rax, [rsi]
0x180035c32  mov     [rsp+48h+var_20], rax
0x180035c37  lea     rsi, [rdi+80h]
0x180035c3e  mov     rcx, rsi; lpCriticalSection
0x180035c41  call    cs:__imp_EnterCriticalSection
0x180035c47  mov     [rsp+48h+arg_8], rsi
0x180035c4c  lea     rcx, [rdi+110h]
0x180035c53  cmp     byte ptr [rcx+78h], 0
0x180035c57  jnz     loc_180035D1D
0x180035c5d  lea     rdx, [rsp+48h+var_28]
0x180035c62  cmp     dword ptr [rdi+78h], 1
0x180035c66  jnz     loc_180035D0F
0x180035c6c  call    std__deque_std__function_void___cdecl_void___std__allocator_std__function_void___cdecl_void________emplace_back__SleepStudy__StopTrackingInterface____3____lambda_1___
0x180035c71  nop
0x180035c72  test    rsi, rsi
0x180035c75  jz      short loc_180035C80
0x180035c77  mov     rcx, rsi; lpCriticalSection
0x180035c7a  call    cs:__imp_LeaveCriticalSection
0x180035c80  lock inc qword ptr [rdi+100h]
0x180035c88  mov     rcx, [rdi+0F8h]; pwk
0x180035c8f  call    cs:__imp_SubmitThreadpoolWork
0x180035c95  nop
0x180035c96  test    rbx, rbx
0x180035c99  jz      short loc_180035CD2
0x180035c9b  or      edi, 0FFFFFFFFh
0x180035c9e  mov     eax, edi
0x180035ca0  lock xadd [rbx+8], eax
0x180035ca5  add     eax, edi
0x180035ca7  jnz     short loc_180035CD2
0x180035ca9  mov     rax, [rbx]
0x180035cac  mov     rcx, rbx
0x180035caf  mov     rax, [rax]
0x180035cb2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180035cb7  mov     eax, edi
0x180035cb9  lock xadd [rbx+0Ch], eax
0x180035cbe  add     eax, edi
0x180035cc0  jnz     short loc_180035CD2
0x180035cc2  mov     rax, [rbx]
0x180035cc5  mov     rcx, rbx
0x180035cc8  mov     rax, [rax+8]
0x180035ccc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180035cd1  nop
0x180035cd2  mov     rbx, [rsp+48h+arg_0]
0x180035cd7  mov     rsi, [rsp+48h+arg_10]
0x180035cdc  add     rsp, 40h
0x180035ce0  pop     rdi
0x180035ce1  retn
0x180035ce2  mov     rcx, [rsp+48h]; this
0x180035ce7  mov     r9d, 139Fh; char *
0x180035ced  lea     r8, aOnecoreuapNetW_22; "onecoreuap\\net\\wcm\\service\\base\\se"...
0x180035cf4  mov     edx, 2C6h; void *
0x180035cf9  call    ?Log_Win32@in1diag3@details@wil@@YAKPEAXIPEBDK@Z; wil::details::in1diag3::Log_Win32(void *,uint,char const *,ulong)
0x180035cfe  nop
0x180035cff  test    rbx, rbx
0x180035d02  jz      short loc_180035D0D
0x180035d04  mov     rcx, rbx; this
0x180035d07  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180035d0c  nop
0x180035d0d  jmp     short loc_180035CD2
0x180035d0f  add     rcx, 50h ; 'P'
0x180035d13  call    std__deque_std__variant_std__function_void___cdecl_void___std__shared_ptr_WcmCommon__BaseThreadPoolWaitableResult____std__allocator_std__variant_std__function_void___cdecl_void___std__shared_ptr_WcmCommon__BaseThreadPoolWaitableResult_________emplace_back__SleepStudy__StopTrackingInterface____3____lambda_1___
0x180035d18  jmp     loc_180035C72
0x180035d1d  test    rsi, rsi
0x180035d20  jz      loc_180035C96
0x180035d26  mov     rcx, rsi; lpCriticalSection
0x180035d29  call    cs:__imp_LeaveCriticalSection
0x180035d2f  jmp     loc_180035C96
0x180035d34  jmp     short loc_180035CD2
```
