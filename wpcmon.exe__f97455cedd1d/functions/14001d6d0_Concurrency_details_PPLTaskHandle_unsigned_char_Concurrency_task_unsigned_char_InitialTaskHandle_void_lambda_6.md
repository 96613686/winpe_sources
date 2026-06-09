# Concurrency::details::_PPLTaskHandle_unsigned_char_Concurrency::task_unsigned_char_::_InitialTaskHandle_void__lambda_6f762fb20c396d21772d1c31e31e567d__Concurrency::details::_TypeSelectorNoAsync__Concurrency::details::_TaskProcHandle_::invoke

- ea: `0x14001d6d0`
- end: `0x14001d7fe`
- name: `Concurrency::details::_PPLTaskHandle_unsigned_char_Concurrency::task_unsigned_char_::_InitialTaskHandle_void__lambda_6f762fb20c396d21772d1c31e31e567d__Concurrency::details::_TypeSelectorNoAsync__Concurrency::details::_TaskProcHandle_::invoke`
- size: `302`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `service_task, installer_update, broker_com_uri`

## callees

- `0x14001b55c`
- `0x14001b6c8`
- `0x14001c284`
- `0x14001d6d0`
- `0x1400a8010`

## import_xrefs

- `msvcp_win!?_Xbad_function_call@std@@YAXXZ` at `0x14001d785`
- `msvcp_win!?_Xbad_function_call@std@@YAXXZ` at `0x14001d785`
- `msvcp_win!?_LogTaskExecutionCompleted@_TaskEventLogger@details@Concurrency@@QEAAXXZ` at `0x14001d7e7`
- `msvcp_win!?_LogTaskExecutionCompleted@_TaskEventLogger@details@Concurrency@@QEAAXXZ` at `0x14001d7e7`
- `msvcp_win!?_LogWorkItemStarted@_TaskEventLogger@details@Concurrency@@QEAAXXZ` at `0x14001d775`
- `msvcp_win!?_LogWorkItemStarted@_TaskEventLogger@details@Concurrency@@QEAAXXZ` at `0x14001d775`
- `msvcp_win!?_LogWorkItemCompleted@_TaskEventLogger@details@Concurrency@@QEAAXXZ` at `0x14001d79d`
- `msvcp_win!?_LogWorkItemCompleted@_TaskEventLogger@details@Concurrency@@QEAAXXZ` at `0x14001d79d`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
void __fastcall Concurrency::details::_PPLTaskHandle_unsigned_char_Concurrency::task_unsigned_char_::_InitialTaskHandle_void__lambda_6f762fb20c396d21772d1c31e31e567d__Concurrency::details::_TypeSelectorNoAsync__Concurrency::details::_TaskProcHandle_::invoke(
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
  char v17; // [rsp+48h] [rbp-A0h]
  void ***v18; // [rsp+78h] [rbp-70h]
  char v19[104]; // [rsp+80h] [rbp-68h] BYREF
  Concurrency::details::_Task_impl_base **v21; // [rsp+F8h] [rbp+10h]

  v2 = (Concurrency::details::_Task_impl_base **)(a1 + 8);
  v21 = (Concurrency::details::_Task_impl_base **)(a1 + 8);
  if ( (unsigned __int8)Concurrency::details::_Task_impl<unsigned char>::_TransitionedToStarted(*(_QWORD *)(a1 + 8)) )
  {
    try
    {
      v4 = *v2;
      v16 = &std::_Func_impl_no_alloc<_lambda_6f762fb20c396d21772d1c31e31e567d_,void,>::`vftable';
      v17 = *(_BYTE *)(a1 + 24);
      v18 = &v16;
      v5 = Concurrency::_Init_func_transformer<void>::_Perform(v19, &v16);
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
      v2 = v21;
    }
    catch ( Concurrency::details::_Interruption_exception )
    {
      v13 = *(_QWORD *)(a1 + 8);
      v14 = v13 + 16;
      LOBYTE(v14) = 1;
      guard_dispatch_icall_thunk_10345483385596137414(v13, v14, 0, 0, v13 + 16);
      v2 = v21;
    }
    catch ( ... )
    {
      v12 = *(Concurrency::details::_Task_impl_base **)(a1 + 8);
      v15 = 0;
      __ExceptionPtrCreate(&v15);
      __ExceptionPtrCurrentException(&v15);
      Concurrency::details::_Task_impl_base::_CancelWithException(v12, (const struct std::exception_ptr *)&v15);
      __ExceptionPtrDestroy(&v15);
      v2 = v21;
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
0x14001d6d0  mov     [rsp+arg_0], rcx
0x14001d6d5  push    rbx
0x14001d6d6  push    rsi
0x14001d6d7  push    rdi
0x14001d6d8  push    r14
0x14001d6da  push    r15
0x14001d6dc  sub     rsp, 0C0h
0x14001d6e3  mov     rdi, rcx
0x14001d6e6  lea     rbx, [rcx+8]
0x14001d6ea  mov     [rsp+0E8h+arg_8], rbx
0x14001d6f2  mov     rcx, [rbx]
0x14001d6f5  call    ?_TransitionedToStarted@?$_Task_impl@E@details@Concurrency@@QEAA_NXZ; Concurrency::details::_Task_impl<uchar>::_TransitionedToStarted(void)
0x14001d6fa  test    al, al
0x14001d6fc  jnz     short loc_14001D723
0x14001d6fe  mov     rcx, [rbx]
0x14001d701  mov     rax, [rcx]
0x14001d704  lea     rdx, [rcx+10h]
0x14001d708  mov     [rsp+0E8h+var_C8], rdx
0x14001d70d  xor     r9d, r9d
0x14001d710  xor     r8d, r8d
0x14001d713  mov     dl, 1
0x14001d715  mov     rax, [rax+8]
0x14001d719  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001d71e  jmp     loc_14001D7ED
0x14001d723  mov     r15, [rbx]
0x14001d726  lea     rax, ??_7?$_Func_impl_no_alloc@V_lambda_6f762fb20c396d21772d1c31e31e567d_@@X$$V@std@@6B@; const std::_Func_impl_no_alloc<_lambda_6f762fb20c396d21772d1c31e31e567d_,void,>::`vftable'
0x14001d72d  mov     [rsp+0E8h+var_A8], rax
0x14001d732  mov     al, [rdi+18h]
0x14001d735  mov     [rsp+0E8h+var_A0], al
0x14001d739  lea     rax, [rsp+0E8h+var_A8]
0x14001d73e  mov     [rsp+0E8h+var_70], rax
0x14001d743  lea     rdx, [rsp+0E8h+var_A8]
0x14001d748  lea     rcx, [rsp+0E8h+var_68]
0x14001d750  call    ?_Perform@?$_Init_func_transformer@X@Concurrency@@SA?AV?$function@$$A6AEXZ@std@@V?$function@$$A6AXXZ@4@@Z; Concurrency::_Init_func_transformer<void>::_Perform(std::function<void (void)>)
0x14001d755  mov     rdi, rax
0x14001d758  mov     [rsp+0E8h+arg_10], rax
0x14001d760  mov     rsi, [rbx]
0x14001d763  add     rsi, 160h
0x14001d76a  mov     [rsp+0E8h+arg_18], rsi
0x14001d772  mov     rcx, rsi
0x14001d775  call    cs:__imp_?_LogWorkItemStarted@_TaskEventLogger@details@Concurrency@@QEAAXXZ; Concurrency::details::_TaskEventLogger::_LogWorkItemStarted(void)
0x14001d77b  nop
0x14001d77c  mov     rcx, [rdi+38h]
0x14001d780  test    rcx, rcx
0x14001d783  jnz     short loc_14001D78B
0x14001d785  call    cs:__imp_?_Xbad_function_call@std@@YAXXZ; std::_Xbad_function_call(void)
0x14001d78b  mov     rax, [rcx]
0x14001d78e  mov     rax, [rax+10h]
0x14001d792  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001d797  mov     r14b, al
0x14001d79a  mov     rcx, rsi
0x14001d79d  call    cs:__imp_?_LogWorkItemCompleted@_TaskEventLogger@details@Concurrency@@QEAAXXZ; Concurrency::details::_TaskEventLogger::_LogWorkItemCompleted(void)
0x14001d7a3  nop
0x14001d7a4  mov     rcx, [rdi+38h]
0x14001d7a8  test    rcx, rcx
0x14001d7ab  jz      short loc_14001D7C7
0x14001d7ad  mov     rax, [rcx]
0x14001d7b0  cmp     rcx, rdi
0x14001d7b3  setnz   dl
0x14001d7b6  mov     rax, [rax+20h]
0x14001d7ba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001d7bf  mov     qword ptr [rdi+38h], 0
0x14001d7c7  mov     dl, r14b
0x14001d7ca  mov     rcx, r15; this
0x14001d7cd  call    ?_FinalizeAndRunContinuations@?$_Task_impl@E@details@Concurrency@@QEAAXE@Z; Concurrency::details::_Task_impl<uchar>::_FinalizeAndRunContinuations(uchar)
0x14001d7d2  nop
0x14001d7d3  jmp     short loc_14001D7DD
0x14001d7d5  mov     rbx, [rsp+0E8h+arg_8]
0x14001d7dd  mov     rcx, [rbx]
0x14001d7e0  add     rcx, 160h
0x14001d7e7  call    cs:__imp_?_LogTaskExecutionCompleted@_TaskEventLogger@details@Concurrency@@QEAAXXZ; Concurrency::details::_TaskEventLogger::_LogTaskExecutionCompleted(void)
0x14001d7ed  add     rsp, 0C0h
0x14001d7f4  pop     r15
0x14001d7f6  pop     r14
0x14001d7f8  pop     rdi
0x14001d7f9  pop     rsi
0x14001d7fa  pop     rbx
0x14001d7fb  retn
0x14001d7fc  jmp     short loc_14001D7D5
```
