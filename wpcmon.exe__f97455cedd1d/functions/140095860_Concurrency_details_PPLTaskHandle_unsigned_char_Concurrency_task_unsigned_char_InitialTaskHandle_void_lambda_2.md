# Concurrency::details::_PPLTaskHandle_unsigned_char_Concurrency::task_unsigned_char_::_InitialTaskHandle_void__lambda_22ca94be88cc0567c38a3454635a1c54__Concurrency::details::_TypeSelectorNoAsync__Concurrency::details::_TaskProcHandle_::invoke

- ea: `0x140095860`
- end: `0x14009599b`
- name: `Concurrency::details::_PPLTaskHandle_unsigned_char_Concurrency::task_unsigned_char_::_InitialTaskHandle_void__lambda_22ca94be88cc0567c38a3454635a1c54__Concurrency::details::_TypeSelectorNoAsync__Concurrency::details::_TaskProcHandle_::invoke`
- size: `315`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `service_task, installer_update, broker_com_uri`

## callees

- `0x14001b55c`
- `0x14001b6c8`
- `0x14001c284`
- `0x140095860`
- `0x1400a8010`

## import_xrefs

- `msvcp_win!?_Xbad_function_call@std@@YAXXZ` at `0x140095922`
- `msvcp_win!?_Xbad_function_call@std@@YAXXZ` at `0x140095922`
- `msvcp_win!?_LogTaskExecutionCompleted@_TaskEventLogger@details@Concurrency@@QEAAXXZ` at `0x140095984`
- `msvcp_win!?_LogTaskExecutionCompleted@_TaskEventLogger@details@Concurrency@@QEAAXXZ` at `0x140095984`
- `msvcp_win!?_LogWorkItemStarted@_TaskEventLogger@details@Concurrency@@QEAAXXZ` at `0x140095912`
- `msvcp_win!?_LogWorkItemStarted@_TaskEventLogger@details@Concurrency@@QEAAXXZ` at `0x140095912`
- `msvcp_win!?_LogWorkItemCompleted@_TaskEventLogger@details@Concurrency@@QEAAXXZ` at `0x14009593a`
- `msvcp_win!?_LogWorkItemCompleted@_TaskEventLogger@details@Concurrency@@QEAAXXZ` at `0x14009593a`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
void __fastcall Concurrency::details::_PPLTaskHandle_unsigned_char_Concurrency::task_unsigned_char_::_InitialTaskHandle_void__lambda_22ca94be88cc0567c38a3454635a1c54__Concurrency::details::_TypeSelectorNoAsync__Concurrency::details::_TaskProcHandle_::invoke(
        __int64 a1)
{
  Concurrency::details::_Task_impl_base **v2; // rbx
  __int64 v3; // rdx
  Concurrency::details::_Task_impl_base *v4; // r15
  __int64 v5; // rdi
  Concurrency::details::_TaskEventLogger *v6; // rsi
  __int64 v7; // rcx
  __int64 v8; // rdx
  __int64 v9; // rcx
  __int64 v10; // rcx
  __int64 v11; // rdx
  Concurrency::details::_Task_impl_base *v12; // rbx
  __int64 v13; // rcx
  __int64 v14; // rdx
  __int128 v15; // [rsp+30h] [rbp-B8h] BYREF
  void **v16; // [rsp+40h] [rbp-A8h] BYREF
  __int128 v17; // [rsp+48h] [rbp-A0h]
  __int64 v18; // [rsp+58h] [rbp-90h]
  void ***v19; // [rsp+78h] [rbp-70h]
  char v20[104]; // [rsp+80h] [rbp-68h] BYREF
  Concurrency::details::_Task_impl_base **v22; // [rsp+F8h] [rbp+10h]

  v2 = (Concurrency::details::_Task_impl_base **)(a1 + 8);
  v22 = (Concurrency::details::_Task_impl_base **)(a1 + 8);
  if ( (unsigned __int8)Concurrency::details::_Task_impl<unsigned char>::_TransitionedToStarted(*(_QWORD *)(a1 + 8)) )
  {
    try
    {
      v4 = *v2;
      v16 = &std::_Func_impl_no_alloc<_lambda_22ca94be88cc0567c38a3454635a1c54_,void,>::`vftable';
      v17 = *(_OWORD *)(a1 + 24);
      v18 = *(_QWORD *)(a1 + 40);
      v19 = &v16;
      v5 = Concurrency::_Init_func_transformer<void>::_Perform(v20, &v16);
      v6 = (Concurrency::details::_Task_impl_base *)((char *)*v2 + 352);
      Concurrency::details::_TaskEventLogger::_LogWorkItemStarted(v6);
      v7 = *(_QWORD *)(v5 + 56);
      if ( !v7 )
        std::_Xbad_function_call();
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v7 + 16LL))(v7);
      Concurrency::details::_TaskEventLogger::_LogWorkItemCompleted(v6);
      v9 = *(_QWORD *)(v5 + 56);
      if ( v9 )
      {
        LOBYTE(v8) = v9 != v5;
        (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v9 + 32LL))(v9, v8);
        *(_QWORD *)(v5 + 56) = 0;
      }
      Concurrency::details::_Task_impl<unsigned char>::_FinalizeAndRunContinuations(v4);
    }
    catch ( Concurrency::task_canceled )
    {
      v10 = *(_QWORD *)(a1 + 8);
      v11 = v10 + 16;
      LOBYTE(v11) = 1;
      (*(void (__fastcall **)(__int64, __int64, _QWORD, _QWORD, __int64))(*(_QWORD *)v10 + 8LL))(
        v10,
        v11,
        0,
        0,
        v10 + 16);
      v2 = v22;
    }
    catch ( Concurrency::details::_Interruption_exception )
    {
      v13 = *(_QWORD *)(a1 + 8);
      v14 = v13 + 16;
      LOBYTE(v14) = 1;
      guard_dispatch_icall_thunk_10345483385596137414(v13, v14, 0, 0, v13 + 16);
      v2 = v22;
    }
    catch ( ... )
    {
      v12 = *(Concurrency::details::_Task_impl_base **)(a1 + 8);
      v15 = 0;
      __ExceptionPtrCreate(&v15);
      __ExceptionPtrCurrentException(&v15);
      Concurrency::details::_Task_impl_base::_CancelWithException(v12, (const struct std::exception_ptr *)&v15);
      __ExceptionPtrDestroy(&v15);
      v2 = v22;
    }
    Concurrency::details::_TaskEventLogger::_LogTaskExecutionCompleted((Concurrency::details::_Task_impl_base *)((char *)*v2 + 352));
  }
  else
  {
    v3 = (__int64)*v2 + 16;
    LOBYTE(v3) = 1;
    (*(void (__fastcall **)(Concurrency::details::_Task_impl_base *, __int64, _QWORD, _QWORD, __int64))(*(_QWORD *)*v2 + 8LL))(
      *v2,
      v3,
      0,
      0,
      (__int64)*v2 + 16);
  }
}

```

## disassembly

```asm
0x140095860  mov     [rsp+arg_0], rcx
0x140095865  push    rbx
0x140095866  push    rsi
0x140095867  push    rdi
0x140095868  push    r14
0x14009586a  push    r15
0x14009586c  sub     rsp, 0C0h
0x140095873  mov     rdi, rcx
0x140095876  lea     rbx, [rcx+8]
0x14009587a  mov     [rsp+0E8h+arg_8], rbx
0x140095882  mov     rcx, [rbx]
0x140095885  call    ?_TransitionedToStarted@?$_Task_impl@E@details@Concurrency@@QEAA_NXZ; Concurrency::details::_Task_impl<uchar>::_TransitionedToStarted(void)
0x14009588a  test    al, al
0x14009588c  jnz     short loc_1400958B3
0x14009588e  mov     rcx, [rbx]
0x140095891  mov     rax, [rcx]
0x140095894  lea     rdx, [rcx+10h]
0x140095898  mov     [rsp+0E8h+var_C8], rdx
0x14009589d  xor     r9d, r9d
0x1400958a0  xor     r8d, r8d
0x1400958a3  mov     dl, 1
0x1400958a5  mov     rax, [rax+8]
0x1400958a9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400958ae  jmp     loc_14009598A
0x1400958b3  mov     r15, [rbx]
0x1400958b6  lea     rax, ??_7?$_Func_impl_no_alloc@V_lambda_22ca94be88cc0567c38a3454635a1c54_@@X$$V@std@@6B@; const std::_Func_impl_no_alloc<_lambda_22ca94be88cc0567c38a3454635a1c54_,void,>::`vftable'
0x1400958bd  mov     [rsp+0E8h+var_A8], rax
0x1400958c2  movups  xmm0, xmmword ptr [rdi+18h]
0x1400958c6  movups  [rsp+0E8h+var_A0], xmm0
0x1400958cb  movsd   xmm1, qword ptr [rdi+28h]
0x1400958d0  movsd   [rsp+0E8h+var_90], xmm1
0x1400958d6  lea     rax, [rsp+0E8h+var_A8]
0x1400958db  mov     [rsp+0E8h+var_70], rax
0x1400958e0  lea     rdx, [rsp+0E8h+var_A8]
0x1400958e5  lea     rcx, [rsp+0E8h+var_68]
0x1400958ed  call    ?_Perform@?$_Init_func_transformer@X@Concurrency@@SA?AV?$function@$$A6AEXZ@std@@V?$function@$$A6AXXZ@4@@Z; Concurrency::_Init_func_transformer<void>::_Perform(std::function<void (void)>)
0x1400958f2  mov     rdi, rax
0x1400958f5  mov     [rsp+0E8h+arg_10], rax
0x1400958fd  mov     rsi, [rbx]
0x140095900  add     rsi, 160h
0x140095907  mov     [rsp+0E8h+arg_18], rsi
0x14009590f  mov     rcx, rsi
0x140095912  call    cs:__imp_?_LogWorkItemStarted@_TaskEventLogger@details@Concurrency@@QEAAXXZ; Concurrency::details::_TaskEventLogger::_LogWorkItemStarted(void)
0x140095918  nop
0x140095919  mov     rcx, [rdi+38h]
0x14009591d  test    rcx, rcx
0x140095920  jnz     short loc_140095928
0x140095922  call    cs:__imp_?_Xbad_function_call@std@@YAXXZ; std::_Xbad_function_call(void)
0x140095928  mov     rax, [rcx]
0x14009592b  mov     rax, [rax+10h]
0x14009592f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140095934  mov     r14b, al
0x140095937  mov     rcx, rsi
0x14009593a  call    cs:__imp_?_LogWorkItemCompleted@_TaskEventLogger@details@Concurrency@@QEAAXXZ; Concurrency::details::_TaskEventLogger::_LogWorkItemCompleted(void)
0x140095940  nop
0x140095941  mov     rcx, [rdi+38h]
0x140095945  test    rcx, rcx
0x140095948  jz      short loc_140095964
0x14009594a  mov     rax, [rcx]
0x14009594d  cmp     rcx, rdi
0x140095950  setnz   dl
0x140095953  mov     rax, [rax+20h]
0x140095957  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14009595c  mov     qword ptr [rdi+38h], 0
0x140095964  mov     dl, r14b
0x140095967  mov     rcx, r15; this
0x14009596a  call    ?_FinalizeAndRunContinuations@?$_Task_impl@E@details@Concurrency@@QEAAXE@Z; Concurrency::details::_Task_impl<uchar>::_FinalizeAndRunContinuations(uchar)
0x14009596f  nop
0x140095970  jmp     short loc_14009597A
0x140095972  mov     rbx, [rsp+0E8h+arg_8]
0x14009597a  mov     rcx, [rbx]
0x14009597d  add     rcx, 160h
0x140095984  call    cs:__imp_?_LogTaskExecutionCompleted@_TaskEventLogger@details@Concurrency@@QEAAXXZ; Concurrency::details::_TaskEventLogger::_LogTaskExecutionCompleted(void)
0x14009598a  add     rsp, 0C0h
0x140095991  pop     r15
0x140095993  pop     r14
0x140095995  pop     rdi
0x140095996  pop     rsi
0x140095997  pop     rbx
0x140095998  retn
0x140095999  jmp     short loc_140095972
```
