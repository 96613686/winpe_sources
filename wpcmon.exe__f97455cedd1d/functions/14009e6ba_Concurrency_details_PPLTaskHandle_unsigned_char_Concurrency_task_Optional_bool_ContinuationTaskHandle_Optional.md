# _Concurrency::details::_PPLTaskHandle_unsigned_char_Concurrency::task_Optional_bool___::_ContinuationTaskHandle_Optional_bool__void_std::function_void___cdecl(Optional_bool_)__std::integral_constant_bool_0__Concurrency::details::_TypeSelectorNoAsync__Concurrency::details::_ContinuationTaskHandleBase_::invoke_::_1_::catch$4

- ea: `0x14009e6ba`
- end: `0x14009e717`
- name: `_Concurrency::details::_PPLTaskHandle_unsigned_char_Concurrency::task_Optional_bool___::_ContinuationTaskHandle_Optional_bool__void_std::function_void___cdecl(Optional_bool_)__std::integral_constant_bool_0__Concurrency::details::_TypeSelectorNoAsync__Concurrency::details::_ContinuationTaskHandleBase_::invoke_::_1_::catch$4`
- size: `93`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task`

## callees

- `0x140019988`

## import_xrefs

- `msvcp_win!?__ExceptionPtrCurrentException@@YAXPEAX@Z` at `0x14009e6e6`
- `msvcp_win!?__ExceptionPtrCurrentException@@YAXPEAX@Z` at `0x14009e6e6`
- `msvcp_win!?__ExceptionPtrCreate@@YAXPEAX@Z` at `0x14009e6dc`
- `msvcp_win!?__ExceptionPtrCreate@@YAXPEAX@Z` at `0x14009e6dc`
- `msvcp_win!?__ExceptionPtrDestroy@@YAXPEAX@Z` at `0x14009e6fe`
- `msvcp_win!?__ExceptionPtrDestroy@@YAXPEAX@Z` at `0x14009e6fe`

## pseudocode

```c
__int64 __fastcall Concurrency::details::_PPLTaskHandle_unsigned_char_Concurrency::task_Optional_bool___::_ContinuationTaskHandle_Optional_bool__void_std::function_void___cdecl_Optional_bool____std::integral_constant_bool_0__Concurrency::details::_TypeSelectorNoAsync__Concurrency::details::_ContinuationTaskHandleBase_::invoke_::_1_::catch_4(
        __int64 a1,
        __int64 a2)
{
  Concurrency::details::_Task_impl_base *v3; // rbx

  v3 = *(Concurrency::details::_Task_impl_base **)(*(_QWORD *)(a2 + 80) + 40LL);
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
0x14009e6ba  mov     [rsp+arg_8], rdx
0x14009e6bf  push    rbx
0x14009e6c0  push    rbp
0x14009e6c1  sub     rsp, 38h
0x14009e6c5  mov     rbp, rdx
0x14009e6c8  mov     rax, [rbp+50h]
0x14009e6cc  mov     rbx, [rax+28h]
0x14009e6d0  xorps   xmm0, xmm0
0x14009e6d3  movdqu  xmmword ptr [rbp+30h], xmm0
0x14009e6d8  lea     rcx, [rbp+30h]
0x14009e6dc  call    cs:__imp_?__ExceptionPtrCreate@@YAXPEAX@Z; __ExceptionPtrCreate(void *)
0x14009e6e2  lea     rcx, [rbp+30h]
0x14009e6e6  call    cs:__imp_?__ExceptionPtrCurrentException@@YAXPEAX@Z; __ExceptionPtrCurrentException(void *)
0x14009e6ec  nop
0x14009e6ed  lea     rdx, [rbp+30h]; struct std::exception_ptr *
0x14009e6f1  mov     rcx, rbx; this
0x14009e6f4  call    ?_CancelWithException@_Task_impl_base@details@Concurrency@@QEAA_NAEBVexception_ptr@std@@@Z; Concurrency::details::_Task_impl_base::_CancelWithException(std::exception_ptr const &)
0x14009e6f9  nop
0x14009e6fa  lea     rcx, [rbp+30h]
0x14009e6fe  call    cs:__imp_?__ExceptionPtrDestroy@@YAXPEAX@Z; __ExceptionPtrDestroy(void *)
0x14009e704  nop
0x14009e705  mov     rax, 0
0x14009e70f  add     rsp, 38h
0x14009e713  pop     rbp
0x14009e714  pop     rbx
0x14009e715  retn
```
