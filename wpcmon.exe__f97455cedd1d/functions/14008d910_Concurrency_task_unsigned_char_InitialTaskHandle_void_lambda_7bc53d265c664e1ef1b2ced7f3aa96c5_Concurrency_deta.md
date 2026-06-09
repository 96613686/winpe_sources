# Concurrency::task_unsigned_char_::_InitialTaskHandle_void__lambda_7bc53d265c664e1ef1b2ced7f3aa96c5__Concurrency::details::_TypeSelectorNoAsync_::_Perform

- ea: `0x14008d910`
- end: `0x14008da0a`
- name: `Concurrency::task_unsigned_char_::_InitialTaskHandle_void__lambda_7bc53d265c664e1ef1b2ced7f3aa96c5__Concurrency::details::_TypeSelectorNoAsync_::_Perform`
- size: `250`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0x14008da30`

## callees

- `0x14001b55c`
- `0x14001b6c8`
- `0x14008d910`
- `0x1400a8010`

## import_xrefs

- `msvcp_win!?_Xbad_function_call@std@@YAXXZ` at `0x14008d9a4`
- `msvcp_win!?_Xbad_function_call@std@@YAXXZ` at `0x14008d9a4`
- `msvcp_win!?_LogWorkItemStarted@_TaskEventLogger@details@Concurrency@@QEAAXXZ` at `0x14008d994`
- `msvcp_win!?_LogWorkItemStarted@_TaskEventLogger@details@Concurrency@@QEAAXXZ` at `0x14008d994`
- `msvcp_win!?_LogWorkItemCompleted@_TaskEventLogger@details@Concurrency@@QEAAXXZ` at `0x14008d9bd`
- `msvcp_win!?_LogWorkItemCompleted@_TaskEventLogger@details@Concurrency@@QEAAXXZ` at `0x14008d9bd`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall Concurrency::task_unsigned_char_::_InitialTaskHandle_void__lambda_7bc53d265c664e1ef1b2ced7f3aa96c5__Concurrency::details::_TypeSelectorNoAsync_::_Perform(
        _QWORD *a1)
{
  Concurrency::details::_Task_impl_base *v2; // r14
  __int64 v3; // rcx
  __int64 v4; // rdi
  Concurrency::details::_TaskEventLogger *v5; // rbx
  __int64 v6; // rcx
  __int64 *v7; // rcx
  __int64 v8; // rdx
  _QWORD v10[7]; // [rsp+20h] [rbp-39h] BYREF
  _QWORD *v11; // [rsp+58h] [rbp-1h]
  _BYTE v12[64]; // [rsp+60h] [rbp+7h] BYREF

  v2 = (Concurrency::details::_Task_impl_base *)a1[1];
  v11 = 0;
  v10[0] = &std::_Func_impl_no_alloc<_lambda_7bc53d265c664e1ef1b2ced7f3aa96c5_,void,>::`vftable';
  v10[1] = a1[3];
  v3 = a1[4];
  v10[2] = v3;
  if ( v3 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v3 + 8LL))(v3);
  v11 = v10;
  v4 = Concurrency::_Init_func_transformer<void>::_Perform(v12, v10);
  v5 = (Concurrency::details::_TaskEventLogger *)(a1[1] + 352LL);
  Concurrency::details::_TaskEventLogger::_LogWorkItemStarted(v5);
  v6 = *(_QWORD *)(v4 + 56);
  if ( !v6 )
  {
    std::_Xbad_function_call();
    __debugbreak();
  }
  (*(void (__fastcall **)(__int64))(*(_QWORD *)v6 + 16LL))(v6);
  Concurrency::details::_TaskEventLogger::_LogWorkItemCompleted(v5);
  v7 = *(__int64 **)(v4 + 56);
  if ( v7 )
  {
    v8 = *v7;
    LOBYTE(v8) = v7 != (__int64 *)v4;
    (*(void (__fastcall **)(__int64 *, __int64))(*v7 + 32))(v7, v8);
    *(_QWORD *)(v4 + 56) = 0;
  }
  return Concurrency::details::_Task_impl<unsigned char>::_FinalizeAndRunContinuations(v2);
}

```

## disassembly

```asm
0x14008d910  mov     [rsp-8+arg_10], rbx
0x14008d915  mov     [rsp-8+arg_18], rsi
0x14008d91a  push    rbp
0x14008d91b  push    rdi
0x14008d91c  push    r14
0x14008d91e  lea     rbp, [rsp-47h]
0x14008d923  sub     rsp, 0A0h
0x14008d92a  mov     rbx, rcx
0x14008d92d  mov     r14, [rcx+8]
0x14008d931  mov     [rbp+57h+var_58], 0
0x14008d939  lea     rax, ??_7?$_Func_impl_no_alloc@V_lambda_7bc53d265c664e1ef1b2ced7f3aa96c5_@@X$$V@std@@6B@; const std::_Func_impl_no_alloc<_lambda_7bc53d265c664e1ef1b2ced7f3aa96c5_,void,>::`vftable'
0x14008d940  mov     [rbp+57h+var_90], rax
0x14008d944  mov     rax, [rcx+18h]
0x14008d948  mov     [rbp+57h+var_88], rax
0x14008d94c  mov     rcx, [rcx+20h]
0x14008d950  mov     [rbp+57h+var_80], rcx
0x14008d954  test    rcx, rcx
0x14008d957  jz      short loc_14008D966
0x14008d959  mov     rax, [rcx]
0x14008d95c  mov     rax, [rax+8]
0x14008d960  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14008d965  nop
0x14008d966  lea     rax, [rbp+57h+var_90]
0x14008d96a  mov     [rbp+57h+var_58], rax
0x14008d96e  lea     rdx, [rbp+57h+var_90]
0x14008d972  lea     rcx, [rbp+57h+var_50]
0x14008d976  call    ?_Perform@?$_Init_func_transformer@X@Concurrency@@SA?AV?$function@$$A6AEXZ@std@@V?$function@$$A6AXXZ@4@@Z; Concurrency::_Init_func_transformer<void>::_Perform(std::function<void (void)>)
0x14008d97b  mov     rdi, rax
0x14008d97e  mov     [rbp+57h+arg_0], rax
0x14008d982  mov     rbx, [rbx+8]
0x14008d986  add     rbx, 160h
0x14008d98d  mov     [rbp+57h+arg_8], rbx
0x14008d991  mov     rcx, rbx
0x14008d994  call    cs:__imp_?_LogWorkItemStarted@_TaskEventLogger@details@Concurrency@@QEAAXXZ; Concurrency::details::_TaskEventLogger::_LogWorkItemStarted(void)
0x14008d99a  nop
0x14008d99b  mov     rcx, [rdi+38h]
0x14008d99f  test    rcx, rcx
0x14008d9a2  jnz     short loc_14008D9AB
0x14008d9a4  call    cs:__imp_?_Xbad_function_call@std@@YAXXZ; std::_Xbad_function_call(void)
0x14008d9aa  int     3; Trap to Debugger
0x14008d9ab  mov     rax, [rcx]
0x14008d9ae  mov     rax, [rax+10h]
0x14008d9b2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14008d9b7  mov     sil, al
0x14008d9ba  mov     rcx, rbx
0x14008d9bd  call    cs:__imp_?_LogWorkItemCompleted@_TaskEventLogger@details@Concurrency@@QEAAXXZ; Concurrency::details::_TaskEventLogger::_LogWorkItemCompleted(void)
0x14008d9c3  nop
0x14008d9c4  mov     rcx, [rdi+38h]
0x14008d9c8  test    rcx, rcx
0x14008d9cb  jz      short loc_14008D9E7
0x14008d9cd  mov     rdx, [rcx]
0x14008d9d0  mov     rax, [rdx+20h]
0x14008d9d4  cmp     rcx, rdi
0x14008d9d7  setnz   dl
0x14008d9da  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14008d9df  mov     qword ptr [rdi+38h], 0
0x14008d9e7  mov     dl, sil
0x14008d9ea  mov     rcx, r14; this
0x14008d9ed  call    ?_FinalizeAndRunContinuations@?$_Task_impl@E@details@Concurrency@@QEAAXE@Z; Concurrency::details::_Task_impl<uchar>::_FinalizeAndRunContinuations(uchar)
0x14008d9f2  lea     r11, [rsp+0B0h+var_10]
0x14008d9fa  mov     rbx, [r11+30h]
0x14008d9fe  mov     rsi, [r11+38h]
0x14008da02  mov     rsp, r11
0x14008da05  pop     r14
0x14008da07  pop     rdi
0x14008da08  pop     rbp
0x14008da09  retn
```
