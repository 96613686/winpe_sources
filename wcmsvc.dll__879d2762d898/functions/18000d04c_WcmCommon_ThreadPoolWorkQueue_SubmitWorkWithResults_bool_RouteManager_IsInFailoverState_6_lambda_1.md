# WcmCommon::ThreadPoolWorkQueue::SubmitWorkWithResults_bool__RouteManager::IsInFailoverState_::_6_::_lambda_1___

- ea: `0x18000d04c`
- end: `0x18000d208`
- name: `WcmCommon::ThreadPoolWorkQueue::SubmitWorkWithResults_bool__RouteManager::IsInFailoverState_::_6_::_lambda_1___`
- size: `444`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x18000d594`

## callees

- `0x18000d04c`
- `0x18000d210`
- `0x180010560`
- `0x180066548`
- `0x18006de30`
- `0x18008534c`
- `0x180098260`
- `0x1800a1320`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000d086`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000d086`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000d162`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000d1db`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000d162`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000d1db`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x18000d177`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x18000d177`

## pseudocode

```c
_QWORD *__fastcall WcmCommon::ThreadPoolWorkQueue::SubmitWorkWithResults_bool__RouteManager::IsInFailoverState_::_6_::_lambda_1___(
        __int64 a1,
        _QWORD *a2,
        _QWORD *a3)
{
  struct _RTL_CRITICAL_SECTION *v6; // r15
  char *v7; // rsi
  char *v8; // r12
  __int64 v9; // rdx
  _QWORD *v10; // rcx
  __int64 v12; // [rsp+20h] [rbp-59h]
  _BYTE v13[120]; // [rsp+58h] [rbp-21h] BYREF

  v6 = (struct _RTL_CRITICAL_SECTION *)(a1 + 8);
  EnterCriticalSection((LPCRITICAL_SECTION)(a1 + 8));
  if ( *(_BYTE *)(a1 + 272) )
  {
    *a2 = 0;
    a2[1] = 0;
    if ( v6 )
      LeaveCriticalSection(v6);
  }
  else
  {
    v7 = (char *)operator new(0x78u);
    *(_OWORD *)v7 = 0;
    *((_DWORD *)v7 + 2) = 1;
    *((_DWORD *)v7 + 3) = 1;
    *(_QWORD *)v7 = &std::_Ref_count_obj2<WcmCommon::ThreadPoolWaitableResult<bool>>::`vftable';
    v8 = v7 + 16;
    WcmCommon::ThreadPoolWaitableResult_bool_::ThreadPoolWaitableResult_bool___RouteManager::IsInFailoverState_::_6_::_lambda_1___(
      (_QWORD *)v7 + 2,
      a3);
    if ( *(_DWORD *)a1 == 1 )
    {
      _InterlockedIncrement((volatile signed __int32 *)v7 + 2);
      if ( *(_QWORD *)(a1 + 208) <= (unsigned __int64)(*(_QWORD *)(a1 + 224) + 1LL) )
        std::deque<std::shared_ptr<WcmCommon::BaseThreadPoolWaitableResult>>::_Growmap(a1 + 192);
      v9 = *(_QWORD *)(a1 + 208) - 1LL;
      *(_QWORD *)(a1 + 216) &= v9;
      v12 = *(_QWORD *)(a1 + 216) + *(_QWORD *)(a1 + 224);
      if ( !*(_QWORD *)(*(_QWORD *)(a1 + 200) + 8 * (v9 & v12)) )
        *(_QWORD *)(*(_QWORD *)(a1 + 200) + 8 * (v9 & v12)) = std::_Allocate<16,std::_Default_allocate_traits>(0x10u);
      v10 = *(_QWORD **)(*(_QWORD *)(a1 + 200) + 8 * (v12 & (*(_QWORD *)(a1 + 208) - 1LL)));
      *v10 = v8;
      v10[1] = v7;
      ++*(_QWORD *)(a1 + 224);
    }
    else
    {
      std::variant<std::function<void (void)>,std::shared_ptr<WcmCommon::BaseThreadPoolWaitableResult>>::variant<std::function<void (void)>,std::shared_ptr<WcmCommon::BaseThreadPoolWaitableResult>>();
      std::deque<std::variant<std::function<void (void)>,std::shared_ptr<WcmCommon::BaseThreadPoolWaitableResult>>>::_Emplace_back_internal<std::variant<std::function<void (void)>,std::shared_ptr<WcmCommon::BaseThreadPoolWaitableResult>>>(
        (_QWORD *)(a1 + 232),
        (__int64)v13);
      std::variant<std::function<void (void)>,std::shared_ptr<WcmCommon::BaseThreadPoolWaitableResult>>::~variant<std::function<void (void)>,std::shared_ptr<WcmCommon::BaseThreadPoolWaitableResult>>(v13);
    }
    if ( v6 )
      LeaveCriticalSection(v6);
    _InterlockedIncrement64((volatile signed __int64 *)(a1 + 136));
    SubmitThreadpoolWork(*(PTP_WORK *)(a1 + 128));
    *a2 = v8;
    a2[1] = v7;
  }
  return a2;
}

```

## disassembly

```asm
0x18000d04c  mov     [rsp-8+arg_10], rbx
0x18000d051  push    rbp
0x18000d052  push    rsi
0x18000d053  push    rdi
0x18000d054  push    r12
0x18000d056  push    r13
0x18000d058  push    r14
0x18000d05a  push    r15
0x18000d05c  lea     rbp, [rsp-27h]
0x18000d061  sub     rsp, 0A0h
0x18000d068  mov     rdi, r8
0x18000d06b  mov     rbx, rdx
0x18000d06e  mov     r14, rcx
0x18000d071  mov     [rbp+57h+var_B0], rdx
0x18000d075  xor     esi, esi
0x18000d077  xorps   xmm1, xmm1
0x18000d07a  movdqu  [rbp+57h+var_A8], xmm1
0x18000d07f  lea     r15, [rcx+8]
0x18000d083  mov     rcx, r15; lpCriticalSection
0x18000d086  call    cs:__imp_EnterCriticalSection
0x18000d08c  mov     [rbp+57h+var_90], r15
0x18000d090  cmp     [r14+110h], sil
0x18000d097  jnz     loc_18000D1CC
0x18000d09d  lea     ecx, [rsi+78h]; Size
0x18000d0a0  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000d0a5  mov     rsi, rax
0x18000d0a8  mov     [rbp+57h+var_B0], rax
0x18000d0ac  xorps   xmm0, xmm0
0x18000d0af  movups  xmmword ptr [rax], xmm0
0x18000d0b2  mov     dword ptr [rax+8], 1
0x18000d0b9  mov     dword ptr [rax+0Ch], 1
0x18000d0c0  lea     rax, ??_7?$_Ref_count_obj2@V?$ThreadPoolWaitableResult@_N@WcmCommon@@@std@@6B@; const std::_Ref_count_obj2<WcmCommon::ThreadPoolWaitableResult<bool>>::`vftable'
0x18000d0c7  mov     [rsi], rax
0x18000d0ca  lea     r12, [rsi+10h]
0x18000d0ce  mov     rdx, rdi
0x18000d0d1  mov     rcx, r12
0x18000d0d4  call    WcmCommon__ThreadPoolWaitableResult_bool___ThreadPoolWaitableResult_bool___RouteManager__IsInFailoverState____6____lambda_1___
0x18000d0d9  nop
0x18000d0da  mov     qword ptr [rbp+57h+var_A8], r12
0x18000d0de  mov     qword ptr [rbp+57h+var_A8+8], rsi
0x18000d0e2  cmp     dword ptr [r14], 1
0x18000d0e6  jnz     loc_18000D1A2
0x18000d0ec  lea     rdi, [r14+0C0h]
0x18000d0f3  lock inc dword ptr [rsi+8]
0x18000d0f7  mov     [rbp+57h+var_88], r12
0x18000d0fb  mov     [rbp+57h+var_80], rsi
0x18000d0ff  mov     rax, [rdi+20h]
0x18000d103  inc     rax
0x18000d106  cmp     [rdi+10h], rax
0x18000d10a  jbe     loc_18000D1E3
0x18000d110  mov     rdx, [rdi+10h]
0x18000d114  dec     rdx
0x18000d117  and     [rdi+18h], rdx
0x18000d11b  mov     rax, [rdi+20h]
0x18000d11f  add     rax, [rdi+18h]
0x18000d123  mov     [rbp+57h+var_B0], rax
0x18000d127  mov     r13, rax
0x18000d12a  and     r13, rdx
0x18000d12d  mov     rax, [rdi+8]
0x18000d131  cmp     qword ptr [rax+r13*8], 0
0x18000d136  jz      loc_18000D1F0
0x18000d13c  mov     rcx, [rdi+10h]
0x18000d140  dec     rcx
0x18000d143  and     rcx, [rbp+57h+var_B0]
0x18000d147  mov     rax, [rdi+8]
0x18000d14b  mov     rcx, [rax+rcx*8]
0x18000d14f  mov     [rcx], r12
0x18000d152  mov     [rcx+8], rsi
0x18000d156  inc     qword ptr [rdi+20h]
0x18000d15a  test    r15, r15
0x18000d15d  jz      short loc_18000D168
0x18000d15f  mov     rcx, r15; lpCriticalSection
0x18000d162  call    cs:__imp_LeaveCriticalSection
0x18000d168  lock inc qword ptr [r14+88h]
0x18000d170  mov     rcx, [r14+80h]; pwk
0x18000d177  call    cs:__imp_SubmitThreadpoolWork
0x18000d17d  mov     [rbx], r12
0x18000d180  mov     [rbx+8], rsi
0x18000d184  mov     rax, rbx
0x18000d187  mov     rbx, [rsp+0D0h+arg_10]
0x18000d18f  add     rsp, 0A0h
0x18000d196  pop     r15
0x18000d198  pop     r14
0x18000d19a  pop     r13
0x18000d19c  pop     r12
0x18000d19e  pop     rdi
0x18000d19f  pop     rsi
0x18000d1a0  pop     rbp
0x18000d1a1  retn
0x18000d1a2  lea     rdx, [rbp+57h+var_A8]
0x18000d1a6  lea     rcx, [rbp+57h+var_78]
0x18000d1aa  call    ??$?0AEAV?$shared_ptr@V?$ThreadPoolWaitableResult@_N@WcmCommon@@@std@@$0A@$0A@@?$variant@V?$function@$$A6AXXZ@std@@V?$shared_ptr@VBaseThreadPoolWaitableResult@WcmCommon@@@2@@std@@QEAA@AEAV?$shared_ptr@V?$ThreadPoolWaitableResult@_N@WcmCommon@@@1@@Z; std::variant<std::function<void (void)>,std::shared_ptr<WcmCommon::BaseThreadPoolWaitableResult>>::variant<std::function<void (void)>,std::shared_ptr<WcmCommon::BaseThreadPoolWaitableResult>>(std::shared_ptr<WcmCommon::ThreadPoolWaitableResult<bool>> &)
0x18000d1af  nop
0x18000d1b0  lea     rdx, [rbp+57h+var_78]
0x18000d1b4  lea     rcx, [r14+0E8h]
0x18000d1bb  call    ??$_Emplace_back_internal@V?$variant@V?$function@$$A6AXXZ@std@@V?$shared_ptr@VBaseThreadPoolWaitableResult@WcmCommon@@@2@@std@@@?$deque@V?$variant@V?$function@$$A6AXXZ@std@@V?$shared_ptr@VBaseThreadPoolWaitableResult@WcmCommon@@@2@@std@@V?$allocator@V?$variant@V?$function@$$A6AXXZ@std@@V?$shared_ptr@VBaseThreadPoolWaitableResult@WcmCommon@@@2@@std@@@2@@std@@AEAAX$$QEAV?$variant@V?$function@$$A6AXXZ@std@@V?$shared_ptr@VBaseThreadPoolWaitableResult@WcmCommon@@@2@@1@@Z; std::deque<std::variant<std::function<void (void)>,std::shared_ptr<WcmCommon::BaseThreadPoolWaitableResult>>>::_Emplace_back_internal<std::variant<std::function<void (void)>,std::shared_ptr<WcmCommon::BaseThreadPoolWaitableResult>>>(std::variant<std::function<void (void)>,std::shared_ptr<WcmCommon::BaseThreadPoolWaitableResult>> &&)
0x18000d1c0  nop
0x18000d1c1  lea     rcx, [rbp+57h+var_78]
0x18000d1c5  call    ??1?$variant@V?$function@$$A6AXXZ@std@@V?$shared_ptr@VBaseThreadPoolWaitableResult@WcmCommon@@@2@@std@@QEAA@XZ; std::variant<std::function<void (void)>,std::shared_ptr<WcmCommon::BaseThreadPoolWaitableResult>>::~variant<std::function<void (void)>,std::shared_ptr<WcmCommon::BaseThreadPoolWaitableResult>>(void)
0x18000d1ca  jmp     short loc_18000D15A
0x18000d1cc  mov     [rbx], rsi
0x18000d1cf  mov     [rbx+8], rsi
0x18000d1d3  test    r15, r15
0x18000d1d6  jz      short loc_18000D184
0x18000d1d8  mov     rcx, r15; lpCriticalSection
0x18000d1db  call    cs:__imp_LeaveCriticalSection
0x18000d1e1  jmp     short loc_18000D184
0x18000d1e3  mov     rcx, rdi
0x18000d1e6  call    ?_Growmap@?$deque@V?$shared_ptr@VBaseThreadPoolWaitableResult@WcmCommon@@@std@@V?$allocator@V?$shared_ptr@VBaseThreadPoolWaitableResult@WcmCommon@@@std@@@2@@std@@AEAAX_K@Z; std::deque<std::shared_ptr<WcmCommon::BaseThreadPoolWaitableResult>>::_Growmap(unsigned __int64)
0x18000d1eb  jmp     loc_18000D110
0x18000d1f0  mov     ecx, 10h
0x18000d1f5  call    ??$_Allocate@$0BA@U_Default_allocate_traits@std@@@std@@YAPEAX_K@Z; std::_Allocate<16,std::_Default_allocate_traits>(unsigned __int64)
0x18000d1fa  mov     rcx, [rdi+8]
0x18000d1fe  mov     [rcx+r13*8], rax
0x18000d202  jmp     loc_18000D13C
```
