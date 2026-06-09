# Concurrency::task_unsigned_char_::_InitialTaskHandle_void__lambda_1801275c076cdb245f17c08e7969cc2f__Concurrency::details::_TypeSelectorNoAsync_::_Perform

- ea: `0x14004c60c`
- end: `0x14004c708`
- name: `Concurrency::task_unsigned_char_::_InitialTaskHandle_void__lambda_1801275c076cdb245f17c08e7969cc2f__Concurrency::details::_TypeSelectorNoAsync_::_Perform`
- size: `252`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callers

- `0x14004c920`

## callees

- `0x1400057f0`
- `0x14001b55c`
- `0x14001b6c8`
- `0x14003421c`
- `0x14004c60c`
- `0x1400a8010`

## import_xrefs

- `msvcp_win!?_Xbad_function_call@std@@YAXXZ` at `0x14004c6a7`
- `msvcp_win!?_Xbad_function_call@std@@YAXXZ` at `0x14004c6a7`
- `msvcp_win!?_LogWorkItemStarted@_TaskEventLogger@details@Concurrency@@QEAAXXZ` at `0x14004c697`
- `msvcp_win!?_LogWorkItemStarted@_TaskEventLogger@details@Concurrency@@QEAAXXZ` at `0x14004c697`
- `msvcp_win!?_LogWorkItemCompleted@_TaskEventLogger@details@Concurrency@@QEAAXXZ` at `0x14004c6c0`
- `msvcp_win!?_LogWorkItemCompleted@_TaskEventLogger@details@Concurrency@@QEAAXXZ` at `0x14004c6c0`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall Concurrency::task_unsigned_char_::_InitialTaskHandle_void__lambda_1801275c076cdb245f17c08e7969cc2f__Concurrency::details::_TypeSelectorNoAsync_::_Perform(
        __int64 a1)
{
  Concurrency::details::_Task_impl_base *v2; // rbp
  _QWORD *v3; // rbx
  __int64 v4; // rbx
  Concurrency::details::_TaskEventLogger *v5; // rsi
  __int64 v6; // rcx
  __int64 *v7; // rcx
  __int64 v8; // rdx
  _BYTE v10[56]; // [rsp+20h] [rbp-98h] BYREF
  _QWORD *v11; // [rsp+58h] [rbp-60h]
  _BYTE v12[88]; // [rsp+60h] [rbp-58h] BYREF

  v2 = *(Concurrency::details::_Task_impl_base **)(a1 + 8);
  v11 = 0;
  v3 = operator new(0x58u);
  *v3 = &std::_Func_impl_no_alloc<_lambda_1801275c076cdb245f17c08e7969cc2f_,void,>::`vftable';
  appids::AnyRuntimeApp::AnyRuntimeApp(
    (appids::AnyRuntimeApp *)(v3 + 1),
    (const struct appids::AnyRuntimeApp *)(a1 + 24));
  v11 = v3;
  v4 = Concurrency::_Init_func_transformer<void>::_Perform(v12, v10);
  v5 = (Concurrency::details::_TaskEventLogger *)(*(_QWORD *)(a1 + 8) + 352LL);
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
0x14004c60c  mov     r11, rsp
0x14004c60f  mov     [r11+18h], rbx
0x14004c613  push    rbp
0x14004c614  push    rsi
0x14004c615  push    rdi
0x14004c616  sub     rsp, 0A0h
0x14004c61d  mov     rdi, rcx
0x14004c620  mov     rbp, [rcx+8]
0x14004c624  lea     rax, [rsp+0B8h+var_98]
0x14004c629  mov     [r11+8], rax
0x14004c62d  mov     qword ptr [r11-60h], 0
0x14004c635  mov     ecx, 58h ; 'X'; Size
0x14004c63a  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x14004c63f  mov     rbx, rax
0x14004c642  mov     [rsp+0B8h+arg_8], rax
0x14004c64a  lea     rdx, [rdi+18h]; struct appids::AnyRuntimeApp *
0x14004c64e  lea     rax, ??_7?$_Func_impl_no_alloc@V_lambda_1801275c076cdb245f17c08e7969cc2f_@@X$$V@std@@6B@; const std::_Func_impl_no_alloc<_lambda_1801275c076cdb245f17c08e7969cc2f_,void,>::`vftable'
0x14004c655  mov     [rbx], rax
0x14004c658  lea     rcx, [rbx+8]; this
0x14004c65c  call    ??0AnyRuntimeApp@appids@@QEAA@AEBV01@@Z; appids::AnyRuntimeApp::AnyRuntimeApp(appids::AnyRuntimeApp const &)
0x14004c661  nop
0x14004c662  mov     [rsp+0B8h+var_60], rbx
0x14004c667  lea     rdx, [rsp+0B8h+var_98]
0x14004c66c  lea     rcx, [rsp+0B8h+var_58]
0x14004c671  call    ?_Perform@?$_Init_func_transformer@X@Concurrency@@SA?AV?$function@$$A6AEXZ@std@@V?$function@$$A6AXXZ@4@@Z; Concurrency::_Init_func_transformer<void>::_Perform(std::function<void (void)>)
0x14004c676  mov     rbx, rax
0x14004c679  mov     [rsp+0B8h+arg_0], rax
0x14004c681  mov     rsi, [rdi+8]
0x14004c685  add     rsi, 160h
0x14004c68c  mov     [rsp+0B8h+arg_8], rsi
0x14004c694  mov     rcx, rsi
0x14004c697  call    cs:__imp_?_LogWorkItemStarted@_TaskEventLogger@details@Concurrency@@QEAAXXZ; Concurrency::details::_TaskEventLogger::_LogWorkItemStarted(void)
0x14004c69d  nop
0x14004c69e  mov     rcx, [rbx+38h]
0x14004c6a2  test    rcx, rcx
0x14004c6a5  jnz     short loc_14004C6AE
0x14004c6a7  call    cs:__imp_?_Xbad_function_call@std@@YAXXZ; std::_Xbad_function_call(void)
0x14004c6ad  int     3; Trap to Debugger
0x14004c6ae  mov     rax, [rcx]
0x14004c6b1  mov     rax, [rax+10h]
0x14004c6b5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14004c6ba  mov     dil, al
0x14004c6bd  mov     rcx, rsi
0x14004c6c0  call    cs:__imp_?_LogWorkItemCompleted@_TaskEventLogger@details@Concurrency@@QEAAXXZ; Concurrency::details::_TaskEventLogger::_LogWorkItemCompleted(void)
0x14004c6c6  nop
0x14004c6c7  mov     rcx, [rbx+38h]
0x14004c6cb  test    rcx, rcx
0x14004c6ce  jz      short loc_14004C6EA
0x14004c6d0  mov     rdx, [rcx]
0x14004c6d3  mov     rax, [rdx+20h]
0x14004c6d7  cmp     rcx, rbx
0x14004c6da  setnz   dl
0x14004c6dd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14004c6e2  mov     qword ptr [rbx+38h], 0
0x14004c6ea  mov     dl, dil
0x14004c6ed  mov     rcx, rbp; this
0x14004c6f0  call    ?_FinalizeAndRunContinuations@?$_Task_impl@E@details@Concurrency@@QEAAXE@Z; Concurrency::details::_Task_impl<uchar>::_FinalizeAndRunContinuations(uchar)
0x14004c6f5  mov     rbx, [rsp+0B8h+arg_10]
0x14004c6fd  add     rsp, 0A0h
0x14004c704  pop     rdi
0x14004c705  pop     rsi
0x14004c706  pop     rbp
0x14004c707  retn
```
