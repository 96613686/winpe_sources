# SleepStudy::IndicateClientRequestBegin(PdcManager::PowerChangeSource,ulong,std::optional<_GUID> const &)

- ea: `0x18002dc9c`
- end: `0x18002de32`
- name: `?IndicateClientRequestBegin@SleepStudy@@YAXW4PowerChangeSource@PdcManager@@KAEBV?$optional@U_GUID@@@std@@@Z`
- size: `406`
- prototype: ``
- caller_count: `3`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800543d4`
- `0x18009b024`
- `0x18009b580`

## callees

- `0x180010080`
- `0x18002dc9c`
- `0x18007103c`
- `0x1800af860`
- `0x1800af89c`
- `0x1800f7010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002dd34`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002dd34`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002dd70`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002de25`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002dd70`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002de25`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18002dcfc`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18002dcfc`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18002dcc7`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18002dcc7`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x18002dd85`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x18002dd85`

## string_xrefs

- `0x18002dde9`: `onecoreuap\net\wcm\service\base\server\sleepstudy.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall SleepStudy::IndicateClientRequestBegin(int a1, int a2, __int128 *a3)
{
  volatile signed __int32 *v6; // rbx
  __int64 v7; // rdi
  const char *v8; // r9
  unsigned int v9; // [rsp+20h] [rbp-58h]
  __int64 v10; // [rsp+30h] [rbp-48h] BYREF
  int v11; // [rsp+38h] [rbp-40h]
  int v12; // [rsp+3Ch] [rbp-3Ch]
  __int128 v13; // [rsp+40h] [rbp-38h]
  int v14; // [rsp+50h] [rbp-28h]
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+0h]

  AcquireSRWLockShared(&SleepStudy::Singleton::s_lock);
  v6 = (volatile signed __int32 *)qword_18013EFD8;
  if ( qword_18013EFD8 )
  {
    _InterlockedIncrement((volatile signed __int32 *)qword_18013EFD8 + 2);
    v6 = (volatile signed __int32 *)qword_18013EFD8;
  }
  v7 = *(_QWORD *)&SleepStudy::Singleton::s_instance;
  v9 = SleepStudy::Singleton::s_instance;
  ReleaseSRWLockShared(&SleepStudy::Singleton::s_lock);
  try
  {
    if ( v7 )
    {
      v10 = v7;
      v11 = a1;
      v12 = a2;
      v13 = *a3;
      v14 = *((_DWORD *)a3 + 4);
      EnterCriticalSection((LPCRITICAL_SECTION)(v7 + 128));
      if ( *(_BYTE *)(v7 + 392) )
      {
        if ( v7 != -128 )
          LeaveCriticalSection((LPCRITICAL_SECTION)(v7 + 128));
      }
      else
      {
        if ( *(_DWORD *)(v7 + 120) == 1 )
          std::deque_std::function_void___cdecl_void___std::allocator_std::function_void___cdecl_void______::emplace_back__SleepStudy::IndicateClientRequestBegin_::_3_::_lambda_1___(
            v7 + 272,
            &v10);
        else
          std::deque_std::variant_std::function_void___cdecl_void___std::shared_ptr_WcmCommon::BaseThreadPoolWaitableResult____std::allocator_std::variant_std::function_void___cdecl_void___std::shared_ptr_WcmCommon::BaseThreadPoolWaitableResult_______::emplace_back__SleepStudy::IndicateClientRequestBegin_::_3_::_lambda_1___(
            v7 + 352,
            &v10);
        if ( v7 != -128 )
          LeaveCriticalSection((LPCRITICAL_SECTION)(v7 + 128));
        _InterlockedIncrement64((volatile signed __int64 *)(v7 + 256));
        SubmitThreadpoolWork(*(PTP_WORK *)(v7 + 248));
      }
      if ( v6 )
      {
        if ( _InterlockedExchangeAdd(v6 + 2, 0xFFFFFFFF) == 1 )
        {
          (**(void (__fastcall ***)(volatile signed __int32 *))v6)(v6);
          if ( !_InterlockedDecrement(v6 + 3) )
            (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v6 + 8LL))(v6);
        }
      }
    }
    else
    {
      wil::details::in1diag3::Log_Win32(
        retaddr,
        (void *)0x389,
        (unsigned int)"onecoreuap\\net\\wcm\\service\\base\\server\\sleepstudy.cpp",
        (const char *)0x139F,
        v9);
      if ( v6 )
        std::_Ref_count_base::_Decref((std::_Ref_count_base *)v6);
    }
  }
  catch ( ... )
  {
    wil::details::in1diag3::Log_CaughtException(
      retaddr,
      (void *)0x3CE,
      (unsigned int)"onecoreuap\\net\\wcm\\service\\base\\server\\sleepstudy.cpp",
      v8);
  }
}

```

## disassembly

```asm
0x18002dc9c  mov     [rsp+arg_0], rbx
0x18002dca1  mov     [rsp+arg_8], rsi
0x18002dca6  push    rdi
0x18002dca7  push    r14
0x18002dca9  push    r15
0x18002dcab  sub     rsp, 60h
0x18002dcaf  mov     rsi, r8
0x18002dcb2  mov     r14d, edx
0x18002dcb5  mov     r15d, ecx
0x18002dcb8  xorps   xmm0, xmm0
0x18002dcbb  movups  xmmword ptr [rsp+78h+var_58], xmm0
0x18002dcc0  lea     rcx, ?s_lock@Singleton@SleepStudy@@0Vsrwlock@wil@@A; SRWLock
0x18002dcc7  call    cs:__imp_AcquireSRWLockShared
0x18002dccd  mov     rbx, cs:qword_18013EFD8
0x18002dcd4  test    rbx, rbx
0x18002dcd7  jz      short loc_18002DCE4
0x18002dcd9  lock inc dword ptr [rbx+8]
0x18002dcdd  mov     rbx, cs:qword_18013EFD8
0x18002dce4  mov     rdi, cs:?s_instance@Singleton@SleepStudy@@0V?$shared_ptr@VSingleton@SleepStudy@@@std@@A; std::shared_ptr<SleepStudy::Singleton> SleepStudy::Singleton::s_instance
0x18002dceb  mov     qword ptr [rsp+78h+var_58], rdi; unsigned int
0x18002dcf0  mov     qword ptr [rsp+78h+var_58+8], rbx
0x18002dcf5  lea     rcx, ?s_lock@Singleton@SleepStudy@@0Vsrwlock@wil@@A; SRWLock
0x18002dcfc  call    cs:__imp_ReleaseSRWLockShared
0x18002dd02  nop
0x18002dd03  test    rdi, rdi
0x18002dd06  jz      loc_18002DDDE
0x18002dd0c  mov     [rsp+78h+var_48], rdi
0x18002dd11  mov     [rsp+78h+var_40], r15d
0x18002dd16  mov     [rsp+78h+var_3C], r14d
0x18002dd1b  movups  xmm0, xmmword ptr [rsi]
0x18002dd1e  movups  [rsp+78h+var_38], xmm0
0x18002dd23  mov     eax, [rsi+10h]
0x18002dd26  mov     [rsp+78h+var_28], eax
0x18002dd2a  lea     rsi, [rdi+80h]
0x18002dd31  mov     rcx, rsi; lpCriticalSection
0x18002dd34  call    cs:__imp_EnterCriticalSection
0x18002dd3a  mov     [rsp+78h+arg_18], rsi
0x18002dd42  lea     rcx, [rdi+110h]
0x18002dd49  cmp     byte ptr [rcx+78h], 0
0x18002dd4d  jnz     loc_18002DE19
0x18002dd53  lea     rdx, [rsp+78h+var_48]
0x18002dd58  cmp     dword ptr [rdi+78h], 1
0x18002dd5c  jnz     loc_18002DE0B
0x18002dd62  call    std__deque_std__function_void___cdecl_void___std__allocator_std__function_void___cdecl_void________emplace_back__SleepStudy__IndicateClientRequestBegin____3____lambda_1___
0x18002dd67  nop
0x18002dd68  test    rsi, rsi
0x18002dd6b  jz      short loc_18002DD76
0x18002dd6d  mov     rcx, rsi; lpCriticalSection
0x18002dd70  call    cs:__imp_LeaveCriticalSection
0x18002dd76  lock inc qword ptr [rdi+100h]
0x18002dd7e  mov     rcx, [rdi+0F8h]; pwk
0x18002dd85  call    cs:__imp_SubmitThreadpoolWork
0x18002dd8b  nop
0x18002dd8c  test    rbx, rbx
0x18002dd8f  jz      short loc_18002DDC8
0x18002dd91  or      edi, 0FFFFFFFFh
0x18002dd94  mov     eax, edi
0x18002dd96  lock xadd [rbx+8], eax
0x18002dd9b  add     eax, edi
0x18002dd9d  jnz     short loc_18002DDC8
0x18002dd9f  mov     rax, [rbx]
0x18002dda2  mov     rcx, rbx
0x18002dda5  mov     rax, [rax]
0x18002dda8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ddad  mov     eax, edi
0x18002ddaf  lock xadd [rbx+0Ch], eax
0x18002ddb4  add     eax, edi
0x18002ddb6  jnz     short loc_18002DDC8
0x18002ddb8  mov     rax, [rbx]
0x18002ddbb  mov     rcx, rbx
0x18002ddbe  mov     rax, [rax+8]
0x18002ddc2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ddc7  nop
0x18002ddc8  lea     r11, [rsp+78h+var_18]
0x18002ddcd  mov     rbx, [r11+20h]
0x18002ddd1  mov     rsi, [r11+28h]
0x18002ddd5  mov     rsp, r11
0x18002ddd8  pop     r15
0x18002ddda  pop     r14
0x18002dddc  pop     rdi
0x18002dddd  retn
0x18002ddde  mov     rcx, [rsp+78h]; this
0x18002dde3  mov     r9d, 139Fh; char *
0x18002dde9  lea     r8, aOnecoreuapNetW_22; "onecoreuap\\net\\wcm\\service\\base\\se"...
0x18002ddf0  mov     edx, 389h; void *
0x18002ddf5  call    ?Log_Win32@in1diag3@details@wil@@YAKPEAXIPEBDK@Z; wil::details::in1diag3::Log_Win32(void *,uint,char const *,ulong)
0x18002ddfa  nop
0x18002ddfb  test    rbx, rbx
0x18002ddfe  jz      short loc_18002DE09
0x18002de00  mov     rcx, rbx; this
0x18002de03  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18002de08  nop
0x18002de09  jmp     short loc_18002DDC8
0x18002de0b  add     rcx, 50h ; 'P'
0x18002de0f  call    std__deque_std__variant_std__function_void___cdecl_void___std__shared_ptr_WcmCommon__BaseThreadPoolWaitableResult____std__allocator_std__variant_std__function_void___cdecl_void___std__shared_ptr_WcmCommon__BaseThreadPoolWaitableResult_________emplace_back__SleepStudy__IndicateClientRequestBegin____3____lambda_1___
0x18002de14  jmp     loc_18002DD68
0x18002de19  test    rsi, rsi
0x18002de1c  jz      loc_18002DD8C
0x18002de22  mov     rcx, rsi; lpCriticalSection
0x18002de25  call    cs:__imp_LeaveCriticalSection
0x18002de2b  jmp     loc_18002DD8C
0x18002de30  jmp     short loc_18002DDC8
```
