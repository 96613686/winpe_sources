# _Concurrency::details::_PPLTaskHandle_unsigned_char_Concurrency::task_unsigned_char_::_InitialTaskHandle_void__lambda_7bc53d265c664e1ef1b2ced7f3aa96c5__Concurrency::details::_TypeSelectorNoAsync__Concurrency::details::_TaskProcHandle_::invoke_::_1_::catch$4

- ea: `0x1400a2809`
- end: `0x1400a2866`
- name: `_Concurrency::details::_PPLTaskHandle_unsigned_char_Concurrency::task_unsigned_char_::_InitialTaskHandle_void__lambda_7bc53d265c664e1ef1b2ced7f3aa96c5__Concurrency::details::_TypeSelectorNoAsync__Concurrency::details::_TaskProcHandle_::invoke_::_1_::catch$4`
- size: `93`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task`

## callees

- `0x140019988`

## import_xrefs

- `msvcp_win!?__ExceptionPtrCurrentException@@YAXPEAX@Z` at `0x1400a2835`
- `msvcp_win!?__ExceptionPtrCurrentException@@YAXPEAX@Z` at `0x1400a2835`
- `msvcp_win!?__ExceptionPtrCreate@@YAXPEAX@Z` at `0x1400a282b`
- `msvcp_win!?__ExceptionPtrCreate@@YAXPEAX@Z` at `0x1400a282b`
- `msvcp_win!?__ExceptionPtrDestroy@@YAXPEAX@Z` at `0x1400a284d`
- `msvcp_win!?__ExceptionPtrDestroy@@YAXPEAX@Z` at `0x1400a284d`

## pseudocode

```c
__int64 __fastcall Concurrency::details::_PPLTaskHandle_unsigned_char_Concurrency::task_unsigned_char_::_InitialTaskHandle_void__lambda_7bc53d265c664e1ef1b2ced7f3aa96c5__Concurrency::details::_TypeSelectorNoAsync__Concurrency::details::_TaskProcHandle_::invoke_::_1_::catch_4(
        __int64 a1,
        __int64 a2)
{
  Concurrency::details::_Task_impl_base *v3; // rbx

  v3 = *(Concurrency::details::_Task_impl_base **)(*(_QWORD *)(a2 + 80) + 8LL);
  *(_OWORD *)(a2 + 48) = 0;
  __ExceptionPtrCreate((void *)(a2 + 48));
  __ExceptionPtrCurrentException((void *)(a2 + 48));
  Concurrency::details::_Task_impl_base::_CancelWithException(v3, (const struct std::exception_ptr *)(a2 + 48));
  __ExceptionPtrDestroy((void *)(a2 + 48));
  return 0;
}

```

## disassembly

```asm
0x1400a2809  mov     [rsp+arg_8], rdx
0x1400a280e  push    rbx
0x1400a280f  push    rbp
0x1400a2810  sub     rsp, 38h
0x1400a2814  mov     rbp, rdx
0x1400a2817  mov     rax, [rbp+50h]
0x1400a281b  mov     rbx, [rax+8]
0x1400a281f  xorps   xmm0, xmm0
0x1400a2822  movdqu  xmmword ptr [rbp+30h], xmm0
0x1400a2827  lea     rcx, [rbp+30h]
0x1400a282b  call    cs:__imp_?__ExceptionPtrCreate@@YAXPEAX@Z; __ExceptionPtrCreate(void *)
0x1400a2831  lea     rcx, [rbp+30h]
0x1400a2835  call    cs:__imp_?__ExceptionPtrCurrentException@@YAXPEAX@Z; __ExceptionPtrCurrentException(void *)
0x1400a283b  nop
0x1400a283c  lea     rdx, [rbp+30h]; struct std::exception_ptr *
0x1400a2840  mov     rcx, rbx; this
0x1400a2843  call    ?_CancelWithException@_Task_impl_base@details@Concurrency@@QEAA_NAEBVexception_ptr@std@@@Z; Concurrency::details::_Task_impl_base::_CancelWithException(std::exception_ptr const &)
0x1400a2848  nop
0x1400a2849  lea     rcx, [rbp+30h]
0x1400a284d  call    cs:__imp_?__ExceptionPtrDestroy@@YAXPEAX@Z; __ExceptionPtrDestroy(void *)
0x1400a2853  nop
0x1400a2854  mov     rax, 0
0x1400a285e  add     rsp, 38h
0x1400a2862  pop     rbp
0x1400a2863  pop     rbx
0x1400a2864  retn
```
