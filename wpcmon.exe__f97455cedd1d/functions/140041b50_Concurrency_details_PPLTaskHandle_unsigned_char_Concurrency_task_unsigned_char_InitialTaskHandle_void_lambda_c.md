# Concurrency::details::_PPLTaskHandle_unsigned_char_Concurrency::task_unsigned_char_::_InitialTaskHandle_void__lambda_cfc090e0bf722fc6cef50fb0dd737372__Concurrency::details::_TypeSelectorNoAsync__Concurrency::details::_TaskProcHandle_::invoke

- ea: `0x140041b50`
- end: `0x140041c74`
- name: `Concurrency::details::_PPLTaskHandle_unsigned_char_Concurrency::task_unsigned_char_::_InitialTaskHandle_void__lambda_cfc090e0bf722fc6cef50fb0dd737372__Concurrency::details::_TypeSelectorNoAsync__Concurrency::details::_TaskProcHandle_::invoke`
- size: `292`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `service_task, installer_update, broker_com_uri`

## callees

- `0x14001b55c`
- `0x14001b6c8`
- `0x14001c284`
- `0x140041b50`
- `0x1400a8010`

## import_xrefs

- `msvcp_win!?_Xbad_function_call@std@@YAXXZ` at `0x140041bfb`
- `msvcp_win!?_Xbad_function_call@std@@YAXXZ` at `0x140041bfb`
- `msvcp_win!?_LogTaskExecutionCompleted@_TaskEventLogger@details@Concurrency@@QEAAXXZ` at `0x140041c5d`
- `msvcp_win!?_LogTaskExecutionCompleted@_TaskEventLogger@details@Concurrency@@QEAAXXZ` at `0x140041c5d`
- `msvcp_win!?_LogWorkItemStarted@_TaskEventLogger@details@Concurrency@@QEAAXXZ` at `0x140041beb`
- `msvcp_win!?_LogWorkItemStarted@_TaskEventLogger@details@Concurrency@@QEAAXXZ` at `0x140041beb`
- `msvcp_win!?_LogWorkItemCompleted@_TaskEventLogger@details@Concurrency@@QEAAXXZ` at `0x140041c13`
- `msvcp_win!?_LogWorkItemCompleted@_TaskEventLogger@details@Concurrency@@QEAAXXZ` at `0x140041c13`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
void __fastcall Concurrency::details::_PPLTaskHandle_unsigned_char_Concurrency::task_unsigned_char_::_InitialTaskHandle_void__lambda_cfc090e0bf722fc6cef50fb0dd737372__Concurrency::details::_TypeSelectorNoAsync__Concurrency::details::_TaskProcHandle_::invoke(
        __int64 a1)
{
  Concurrency::details::_Task_impl_base **v1; // rbx
  __int64 v2; // rdx
  Concurrency::details::_Task_impl_base *v3; // r15
  __int64 v4; // rdi
  Concurrency::details::_TaskEventLogger *v5; // rsi
  __int64 v6; // rcx
  __int64 v7; // rdx
  __int64 v8; // rcx
  __int64 v9; // rcx
  __int64 v10; // rdx
  Concurrency::details::_Task_impl_base *v11; // rbx
  __int64 v12; // rcx
  __int64 v13; // rdx
  __int128 v14; // [rsp+30h] [rbp-B8h] BYREF
  _QWORD v15[8]; // [rsp+40h] [rbp-A8h] BYREF
  char v16[104]; // [rsp+80h] [rbp-68h] BYREF
  Concurrency::details::_Task_impl_base **v18; // [rsp+F8h] [rbp+10h]

  v1 = (Concurrency::details::_Task_impl_base **)(a1 + 8);
  v18 = (Concurrency::details::_Task_impl_base **)(a1 + 8);
  if ( (unsigned __int8)Concurrency::details::_Task_impl<unsigned char>::_TransitionedToStarted(*(_QWORD *)(a1 + 8)) )
  {
    try
    {
      v3 = *v1;
      v15[0] = &std::_Func_impl_no_alloc<_lambda_cfc090e0bf722fc6cef50fb0dd737372_,void,>::`vftable';
      v15[7] = v15;
      v4 = Concurrency::_Init_func_transformer<void>::_Perform(v16, v15);
      v5 = (Concurrency::details::_Task_impl_base *)((char *)*v1 + 352);
      Concurrency::details::_TaskEventLogger::_LogWorkItemStarted(v5);
      v6 = *(_QWORD *)(v4 + 56);
      if ( !v6 )
        std::_Xbad_function_call();
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v6 + 16LL))(v6);
      Concurrency::details::_TaskEventLogger::_LogWorkItemCompleted(v5);
      v8 = *(_QWORD *)(v4 + 56);
      if ( v8 )
      {
        LOBYTE(v7) = v8 != v4;
        (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v8 + 32LL))(v8, v7);
        *(_QWORD *)(v4 + 56) = 0;
      }
      Concurrency::details::_Task_impl<unsigned char>::_FinalizeAndRunContinuations(v3);
    }
    catch ( Concurrency::task_canceled )
    {
      v9 = *(_QWORD *)(a1 + 8);
      v10 = v9 + 16;
      LOBYTE(v10) = 1;
      (*(void (__fastcall **)(__int64, __int64, _QWORD, _QWORD, __int64))(*(_QWORD *)v9 + 8LL))(v9, v10, 0, 0, v9 + 16);
      v1 = v18;
    }
    catch ( Concurrency::details::_Interruption_exception )
    {
      v12 = *(_QWORD *)(a1 + 8);
      v13 = v12 + 16;
      LOBYTE(v13) = 1;
      guard_dispatch_icall_thunk_10345483385596137414(v12, v13, 0, 0, v12 + 16);
      v1 = v18;
    }
    catch ( ... )
    {
      v11 = *(Concurrency::details::_Task_impl_base **)(a1 + 8);
      v14 = 0;
      __ExceptionPtrCreate(&v14);
      __ExceptionPtrCurrentException(&v14);
      Concurrency::details::_Task_impl_base::_CancelWithException(v11, (const struct std::exception_ptr *)&v14);
      __ExceptionPtrDestroy(&v14);
      v1 = v18;
    }
    Concurrency::details::_TaskEventLogger::_LogTaskExecutionCompleted((Concurrency::details::_Task_impl_base *)((char *)*v1 + 352));
  }
  else
  {
    v2 = (__int64)*v1 + 16;
    LOBYTE(v2) = 1;
    (*(void (__fastcall **)(Concurrency::details::_Task_impl_base *, __int64, _QWORD, _QWORD, __int64))(*(_QWORD *)*v1 + 8LL))(
      *v1,
      v2,
      0,
      0,
      (__int64)*v1 + 16);
  }
}

```

## disassembly

```asm
0x140041b50  mov     [rsp+arg_0], rcx
0x140041b55  push    rbx
0x140041b56  push    rsi
0x140041b57  push    rdi
0x140041b58  push    r14
0x140041b5a  push    r15
0x140041b5c  sub     rsp, 0C0h
0x140041b63  lea     rbx, [rcx+8]
0x140041b67  mov     [rsp+0E8h+arg_8], rbx
0x140041b6f  mov     rcx, [rbx]
0x140041b72  call    ?_TransitionedToStarted@?$_Task_impl@E@details@Concurrency@@QEAA_NXZ; Concurrency::details::_Task_impl<uchar>::_TransitionedToStarted(void)
0x140041b77  test    al, al
0x140041b79  jnz     short loc_140041BA0
0x140041b7b  mov     rcx, [rbx]
0x140041b7e  mov     rax, [rcx]
0x140041b81  lea     rdx, [rcx+10h]
0x140041b85  mov     [rsp+0E8h+var_C8], rdx
0x140041b8a  xor     r9d, r9d
0x140041b8d  xor     r8d, r8d
0x140041b90  mov     dl, 1
0x140041b92  mov     rax, [rax+8]
0x140041b96  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140041b9b  jmp     loc_140041C63
0x140041ba0  mov     r15, [rbx]
0x140041ba3  lea     rax, ??_7?$_Func_impl_no_alloc@V_lambda_cfc090e0bf722fc6cef50fb0dd737372_@@X$$V@std@@6B@; const std::_Func_impl_no_alloc<_lambda_cfc090e0bf722fc6cef50fb0dd737372_,void,>::`vftable'
0x140041baa  mov     [rsp+0E8h+var_A8], rax
0x140041baf  lea     rax, [rsp+0E8h+var_A8]
0x140041bb4  mov     [rsp+0E8h+var_70], rax
0x140041bb9  lea     rdx, [rsp+0E8h+var_A8]
0x140041bbe  lea     rcx, [rsp+0E8h+var_68]
0x140041bc6  call    ?_Perform@?$_Init_func_transformer@X@Concurrency@@SA?AV?$function@$$A6AEXZ@std@@V?$function@$$A6AXXZ@4@@Z; Concurrency::_Init_func_transformer<void>::_Perform(std::function<void (void)>)
0x140041bcb  mov     rdi, rax
0x140041bce  mov     [rsp+0E8h+arg_10], rax
0x140041bd6  mov     rsi, [rbx]
0x140041bd9  add     rsi, 160h
0x140041be0  mov     [rsp+0E8h+arg_18], rsi
0x140041be8  mov     rcx, rsi
0x140041beb  call    cs:__imp_?_LogWorkItemStarted@_TaskEventLogger@details@Concurrency@@QEAAXXZ; Concurrency::details::_TaskEventLogger::_LogWorkItemStarted(void)
0x140041bf1  nop
0x140041bf2  mov     rcx, [rdi+38h]
0x140041bf6  test    rcx, rcx
0x140041bf9  jnz     short loc_140041C01
0x140041bfb  call    cs:__imp_?_Xbad_function_call@std@@YAXXZ; std::_Xbad_function_call(void)
0x140041c01  mov     rax, [rcx]
0x140041c04  mov     rax, [rax+10h]
0x140041c08  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140041c0d  mov     r14b, al
0x140041c10  mov     rcx, rsi
0x140041c13  call    cs:__imp_?_LogWorkItemCompleted@_TaskEventLogger@details@Concurrency@@QEAAXXZ; Concurrency::details::_TaskEventLogger::_LogWorkItemCompleted(void)
0x140041c19  nop
0x140041c1a  mov     rcx, [rdi+38h]
0x140041c1e  test    rcx, rcx
0x140041c21  jz      short loc_140041C3D
0x140041c23  mov     rax, [rcx]
0x140041c26  cmp     rcx, rdi
0x140041c29  setnz   dl
0x140041c2c  mov     rax, [rax+20h]
0x140041c30  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140041c35  mov     qword ptr [rdi+38h], 0
0x140041c3d  mov     dl, r14b
0x140041c40  mov     rcx, r15; this
0x140041c43  call    ?_FinalizeAndRunContinuations@?$_Task_impl@E@details@Concurrency@@QEAAXE@Z; Concurrency::details::_Task_impl<uchar>::_FinalizeAndRunContinuations(uchar)
0x140041c48  nop
0x140041c49  jmp     short loc_140041C53
0x140041c4b  mov     rbx, [rsp+0E8h+arg_8]
0x140041c53  mov     rcx, [rbx]
0x140041c56  add     rcx, 160h
0x140041c5d  call    cs:__imp_?_LogTaskExecutionCompleted@_TaskEventLogger@details@Concurrency@@QEAAXXZ; Concurrency::details::_TaskEventLogger::_LogTaskExecutionCompleted(void)
0x140041c63  add     rsp, 0C0h
0x140041c6a  pop     r15
0x140041c6c  pop     r14
0x140041c6e  pop     rdi
0x140041c6f  pop     rsi
0x140041c70  pop     rbx
0x140041c71  retn
0x140041c72  jmp     short loc_140041C4B
```
