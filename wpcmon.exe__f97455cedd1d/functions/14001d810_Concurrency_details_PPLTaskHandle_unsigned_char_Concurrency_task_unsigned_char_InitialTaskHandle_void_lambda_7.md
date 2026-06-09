# Concurrency::details::_PPLTaskHandle_unsigned_char_Concurrency::task_unsigned_char_::_InitialTaskHandle_void__lambda_7cf29648c90828924bdf1b4d08968125__Concurrency::details::_TypeSelectorNoAsync__Concurrency::details::_TaskProcHandle_::invoke

- ea: `0x14001d810`
- end: `0x14001d93e`
- name: `Concurrency::details::_PPLTaskHandle_unsigned_char_Concurrency::task_unsigned_char_::_InitialTaskHandle_void__lambda_7cf29648c90828924bdf1b4d08968125__Concurrency::details::_TypeSelectorNoAsync__Concurrency::details::_TaskProcHandle_::invoke`
- size: `302`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callees

- `0x14001b55c`
- `0x14001b6c8`
- `0x14001c284`
- `0x14001d810`
- `0x1400a8010`

## import_xrefs

- `msvcp_win!?_Xbad_function_call@std@@YAXXZ` at `0x14001d8c5`
- `msvcp_win!?_Xbad_function_call@std@@YAXXZ` at `0x14001d8c5`
- `msvcp_win!?_LogTaskExecutionCompleted@_TaskEventLogger@details@Concurrency@@QEAAXXZ` at `0x14001d927`
- `msvcp_win!?_LogTaskExecutionCompleted@_TaskEventLogger@details@Concurrency@@QEAAXXZ` at `0x14001d927`
- `msvcp_win!?_LogWorkItemStarted@_TaskEventLogger@details@Concurrency@@QEAAXXZ` at `0x14001d8b5`
- `msvcp_win!?_LogWorkItemStarted@_TaskEventLogger@details@Concurrency@@QEAAXXZ` at `0x14001d8b5`
- `msvcp_win!?_LogWorkItemCompleted@_TaskEventLogger@details@Concurrency@@QEAAXXZ` at `0x14001d8dd`
- `msvcp_win!?_LogWorkItemCompleted@_TaskEventLogger@details@Concurrency@@QEAAXXZ` at `0x14001d8dd`

## pseudocode

```c
void __fastcall Concurrency::details::_PPLTaskHandle_unsigned_char_Concurrency::task_unsigned_char_::_InitialTaskHandle_void__lambda_7cf29648c90828924bdf1b4d08968125__Concurrency::details::_TypeSelectorNoAsync__Concurrency::details::_TaskProcHandle_::invoke(
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
  void **v10; // [rsp+40h] [rbp-A8h] BYREF
  char v11; // [rsp+48h] [rbp-A0h]
  void ***v12; // [rsp+78h] [rbp-70h]
  char v13[104]; // [rsp+80h] [rbp-68h] BYREF

  v2 = (Concurrency::details::_Task_impl_base **)(a1 + 8);
  if ( (unsigned __int8)Concurrency::details::_Task_impl<unsigned char>::_TransitionedToStarted(*(_QWORD *)(a1 + 8)) )
  {
    v4 = *v2;
    v10 = &std::_Func_impl_no_alloc<_lambda_7cf29648c90828924bdf1b4d08968125_,void,>::`vftable';
    v11 = *(_BYTE *)(a1 + 24);
    v12 = &v10;
    v5 = Concurrency::_Init_func_transformer<void>::_Perform(v13, &v10);
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
0x14001d810  mov     [rsp+arg_0], rcx
0x14001d815  push    rbx
0x14001d816  push    rsi
0x14001d817  push    rdi
0x14001d818  push    r14
0x14001d81a  push    r15
0x14001d81c  sub     rsp, 0C0h
0x14001d823  mov     rdi, rcx
0x14001d826  lea     rbx, [rcx+8]
0x14001d82a  mov     [rsp+0E8h+arg_8], rbx
0x14001d832  mov     rcx, [rbx]
0x14001d835  call    ?_TransitionedToStarted@?$_Task_impl@E@details@Concurrency@@QEAA_NXZ; Concurrency::details::_Task_impl<uchar>::_TransitionedToStarted(void)
0x14001d83a  test    al, al
0x14001d83c  jnz     short loc_14001D863
0x14001d83e  mov     rcx, [rbx]
0x14001d841  mov     rax, [rcx]
0x14001d844  lea     rdx, [rcx+10h]
0x14001d848  mov     [rsp+0E8h+var_C8], rdx
0x14001d84d  xor     r9d, r9d
0x14001d850  xor     r8d, r8d
0x14001d853  mov     dl, 1
0x14001d855  mov     rax, [rax+8]
0x14001d859  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001d85e  jmp     loc_14001D92D
0x14001d863  mov     r15, [rbx]
0x14001d866  lea     rax, ??_7?$_Func_impl_no_alloc@V_lambda_7cf29648c90828924bdf1b4d08968125_@@X$$V@std@@6B@; const std::_Func_impl_no_alloc<_lambda_7cf29648c90828924bdf1b4d08968125_,void,>::`vftable'
0x14001d86d  mov     [rsp+0E8h+var_A8], rax
0x14001d872  mov     al, [rdi+18h]
0x14001d875  mov     [rsp+0E8h+var_A0], al
0x14001d879  lea     rax, [rsp+0E8h+var_A8]
0x14001d87e  mov     [rsp+0E8h+var_70], rax
0x14001d883  lea     rdx, [rsp+0E8h+var_A8]
0x14001d888  lea     rcx, [rsp+0E8h+var_68]
0x14001d890  call    ?_Perform@?$_Init_func_transformer@X@Concurrency@@SA?AV?$function@$$A6AEXZ@std@@V?$function@$$A6AXXZ@4@@Z; Concurrency::_Init_func_transformer<void>::_Perform(std::function<void (void)>)
0x14001d895  mov     rdi, rax
0x14001d898  mov     [rsp+0E8h+arg_10], rax
0x14001d8a0  mov     rsi, [rbx]
0x14001d8a3  add     rsi, 160h
0x14001d8aa  mov     [rsp+0E8h+arg_18], rsi
0x14001d8b2  mov     rcx, rsi
0x14001d8b5  call    cs:__imp_?_LogWorkItemStarted@_TaskEventLogger@details@Concurrency@@QEAAXXZ; Concurrency::details::_TaskEventLogger::_LogWorkItemStarted(void)
0x14001d8bb  nop
0x14001d8bc  mov     rcx, [rdi+38h]
0x14001d8c0  test    rcx, rcx
0x14001d8c3  jnz     short loc_14001D8CB
0x14001d8c5  call    cs:__imp_?_Xbad_function_call@std@@YAXXZ; std::_Xbad_function_call(void)
0x14001d8cb  mov     rax, [rcx]
0x14001d8ce  mov     rax, [rax+10h]
0x14001d8d2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001d8d7  mov     r14b, al
0x14001d8da  mov     rcx, rsi
0x14001d8dd  call    cs:__imp_?_LogWorkItemCompleted@_TaskEventLogger@details@Concurrency@@QEAAXXZ; Concurrency::details::_TaskEventLogger::_LogWorkItemCompleted(void)
0x14001d8e3  nop
0x14001d8e4  mov     rcx, [rdi+38h]
0x14001d8e8  test    rcx, rcx
0x14001d8eb  jz      short loc_14001D907
0x14001d8ed  mov     rax, [rcx]
0x14001d8f0  cmp     rcx, rdi
0x14001d8f3  setnz   dl
0x14001d8f6  mov     rax, [rax+20h]
0x14001d8fa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001d8ff  mov     qword ptr [rdi+38h], 0
0x14001d907  mov     dl, r14b
0x14001d90a  mov     rcx, r15; this
0x14001d90d  call    ?_FinalizeAndRunContinuations@?$_Task_impl@E@details@Concurrency@@QEAAXE@Z; Concurrency::details::_Task_impl<uchar>::_FinalizeAndRunContinuations(uchar)
0x14001d912  nop
0x14001d913  jmp     short loc_14001D91D
0x14001d915  mov     rbx, [rsp+0E8h+arg_8]
0x14001d91d  mov     rcx, [rbx]
0x14001d920  add     rcx, 160h
0x14001d927  call    cs:__imp_?_LogTaskExecutionCompleted@_TaskEventLogger@details@Concurrency@@QEAAXXZ; Concurrency::details::_TaskEventLogger::_LogTaskExecutionCompleted(void)
0x14001d92d  add     rsp, 0C0h
0x14001d934  pop     r15
0x14001d936  pop     r14
0x14001d938  pop     rdi
0x14001d939  pop     rsi
0x14001d93a  pop     rbx
0x14001d93b  retn
0x14001d93c  jmp     short loc_14001D915
```
