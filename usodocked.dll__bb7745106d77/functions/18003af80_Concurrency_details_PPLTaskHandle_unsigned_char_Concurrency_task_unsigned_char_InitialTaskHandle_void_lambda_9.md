# Concurrency::details::_PPLTaskHandle_unsigned_char_Concurrency::task_unsigned_char_::_InitialTaskHandle_void__lambda_94a8c85bcb70cc5e50a26f8b8e2b2321__Concurrency::details::_TypeSelectorNoAsync__Concurrency::details::_TaskProcHandle_::invoke

- ea: `0x18003af80`
- end: `0x18003b0b0`
- name: `Concurrency::details::_PPLTaskHandle_unsigned_char_Concurrency::task_unsigned_char_::_InitialTaskHandle_void__lambda_94a8c85bcb70cc5e50a26f8b8e2b2321__Concurrency::details::_TypeSelectorNoAsync__Concurrency::details::_TaskProcHandle_::invoke`
- size: `304`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callees

- `0x180039300`
- `0x180039764`
- `0x18003a3b8`
- `0x18003af80`
- `0x180071010`

## import_xrefs

- `msvcp_win!?_Xbad_function_call@std@@YAXXZ` at `0x18003b037`
- `msvcp_win!?_Xbad_function_call@std@@YAXXZ` at `0x18003b037`
- `msvcp_win!?_LogWorkItemCompleted@_TaskEventLogger@details@Concurrency@@QEAAXXZ` at `0x18003b04f`
- `msvcp_win!?_LogWorkItemCompleted@_TaskEventLogger@details@Concurrency@@QEAAXXZ` at `0x18003b04f`
- `msvcp_win!?_LogWorkItemStarted@_TaskEventLogger@details@Concurrency@@QEAAXXZ` at `0x18003b027`
- `msvcp_win!?_LogWorkItemStarted@_TaskEventLogger@details@Concurrency@@QEAAXXZ` at `0x18003b027`
- `msvcp_win!?_LogTaskExecutionCompleted@_TaskEventLogger@details@Concurrency@@QEAAXXZ` at `0x18003b099`
- `msvcp_win!?_LogTaskExecutionCompleted@_TaskEventLogger@details@Concurrency@@QEAAXXZ` at `0x18003b099`

## pseudocode

```c
void __fastcall Concurrency::details::_PPLTaskHandle_unsigned_char_Concurrency::task_unsigned_char_::_InitialTaskHandle_void__lambda_94a8c85bcb70cc5e50a26f8b8e2b2321__Concurrency::details::_TypeSelectorNoAsync__Concurrency::details::_TaskProcHandle_::invoke(
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
  _QWORD v10[8]; // [rsp+40h] [rbp-A8h] BYREF
  char v11[104]; // [rsp+80h] [rbp-68h] BYREF

  v2 = (Concurrency::details::_Task_impl_base **)(a1 + 8);
  if ( (unsigned __int8)Concurrency::details::_Task_impl<unsigned char>::_TransitionedToStarted(*(_QWORD *)(a1 + 8)) )
  {
    v4 = *v2;
    v10[0] = off_180072D08;
    v10[1] = *(_QWORD *)(a1 + 24);
    v10[7] = v10;
    v5 = Concurrency::_Init_func_transformer<void>::_Perform(v11, v10);
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
0x18003af80  mov     [rsp+arg_0], rcx
0x18003af85  push    rbx
0x18003af86  push    rsi
0x18003af87  push    rdi
0x18003af88  push    r14
0x18003af8a  push    r15
0x18003af8c  sub     rsp, 0C0h
0x18003af93  mov     rdi, rcx
0x18003af96  lea     rbx, [rcx+8]
0x18003af9a  mov     [rsp+0E8h+arg_8], rbx
0x18003afa2  mov     rcx, [rbx]
0x18003afa5  call    ?_TransitionedToStarted@?$_Task_impl@E@details@Concurrency@@QEAA_NXZ; Concurrency::details::_Task_impl<uchar>::_TransitionedToStarted(void)
0x18003afaa  test    al, al
0x18003afac  jnz     short loc_18003AFD3
0x18003afae  mov     rcx, [rbx]
0x18003afb1  mov     rax, [rcx]
0x18003afb4  lea     rdx, [rcx+10h]
0x18003afb8  mov     [rsp+0E8h+var_C8], rdx
0x18003afbd  xor     r9d, r9d
0x18003afc0  xor     r8d, r8d
0x18003afc3  mov     dl, 1
0x18003afc5  mov     rax, [rax+8]
0x18003afc9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003afce  jmp     loc_18003B09F
0x18003afd3  mov     r15, [rbx]
0x18003afd6  lea     rax, off_180072D08
0x18003afdd  mov     [rsp+0E8h+var_A8], rax
0x18003afe2  mov     rax, [rdi+18h]
0x18003afe6  mov     [rsp+0E8h+var_A0], rax
0x18003afeb  lea     rax, [rsp+0E8h+var_A8]
0x18003aff0  mov     [rsp+0E8h+var_70], rax
0x18003aff5  lea     rdx, [rsp+0E8h+var_A8]
0x18003affa  lea     rcx, [rsp+0E8h+var_68]
0x18003b002  call    ?_Perform@?$_Init_func_transformer@X@Concurrency@@SA?AV?$function@$$A6AEXZ@std@@V?$function@$$A6AXXZ@4@@Z; Concurrency::_Init_func_transformer<void>::_Perform(std::function<void (void)>)
0x18003b007  mov     rdi, rax
0x18003b00a  mov     [rsp+0E8h+arg_10], rax
0x18003b012  mov     rsi, [rbx]
0x18003b015  add     rsi, 160h
0x18003b01c  mov     [rsp+0E8h+arg_18], rsi
0x18003b024  mov     rcx, rsi
0x18003b027  call    cs:__imp_?_LogWorkItemStarted@_TaskEventLogger@details@Concurrency@@QEAAXXZ; Concurrency::details::_TaskEventLogger::_LogWorkItemStarted(void)
0x18003b02d  nop
0x18003b02e  mov     rcx, [rdi+38h]
0x18003b032  test    rcx, rcx
0x18003b035  jnz     short loc_18003B03D
0x18003b037  call    cs:__imp_?_Xbad_function_call@std@@YAXXZ; std::_Xbad_function_call(void)
0x18003b03d  mov     rax, [rcx]
0x18003b040  mov     rax, [rax+10h]
0x18003b044  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003b049  mov     r14b, al
0x18003b04c  mov     rcx, rsi
0x18003b04f  call    cs:__imp_?_LogWorkItemCompleted@_TaskEventLogger@details@Concurrency@@QEAAXXZ; Concurrency::details::_TaskEventLogger::_LogWorkItemCompleted(void)
0x18003b055  nop
0x18003b056  mov     rcx, [rdi+38h]
0x18003b05a  test    rcx, rcx
0x18003b05d  jz      short loc_18003B079
0x18003b05f  mov     rax, [rcx]
0x18003b062  cmp     rcx, rdi
0x18003b065  setnz   dl
0x18003b068  mov     rax, [rax+20h]
0x18003b06c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003b071  mov     qword ptr [rdi+38h], 0
0x18003b079  mov     dl, r14b
0x18003b07c  mov     rcx, r15; this
0x18003b07f  call    ?_FinalizeAndRunContinuations@?$_Task_impl@E@details@Concurrency@@QEAAXE@Z; Concurrency::details::_Task_impl<uchar>::_FinalizeAndRunContinuations(uchar)
0x18003b084  nop
0x18003b085  jmp     short loc_18003B08F
0x18003b087  mov     rbx, [rsp+0E8h+arg_8]
0x18003b08f  mov     rcx, [rbx]
0x18003b092  add     rcx, 160h
0x18003b099  call    cs:__imp_?_LogTaskExecutionCompleted@_TaskEventLogger@details@Concurrency@@QEAAXXZ; Concurrency::details::_TaskEventLogger::_LogTaskExecutionCompleted(void)
0x18003b09f  add     rsp, 0C0h
0x18003b0a6  pop     r15
0x18003b0a8  pop     r14
0x18003b0aa  pop     rdi
0x18003b0ab  pop     rsi
0x18003b0ac  pop     rbx
0x18003b0ad  retn
0x18003b0ae  jmp     short loc_18003B087
```
