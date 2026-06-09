# _Concurrency::details::_PPLTaskHandle_unsigned_char_Concurrency::task_unsigned_char_::_InitialTaskHandle_void__lambda_22ca94be88cc0567c38a3454635a1c54__Concurrency::details::_TypeSelectorNoAsync__Concurrency::details::_TaskProcHandle_::invoke_::_1_::catch$10

- ea: `0x14009e78e`
- end: `0x14009e7ee`
- name: `_Concurrency::details::_PPLTaskHandle_unsigned_char_Concurrency::task_unsigned_char_::_InitialTaskHandle_void__lambda_22ca94be88cc0567c38a3454635a1c54__Concurrency::details::_TypeSelectorNoAsync__Concurrency::details::_TaskProcHandle_::invoke_::_1_::catch$10`
- size: `96`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task`

## callees

- `0x140019988`

## import_xrefs

- `msvcp_win!?__ExceptionPtrCurrentException@@YAXPEAX@Z` at `0x14009e7bd`
- `msvcp_win!?__ExceptionPtrCurrentException@@YAXPEAX@Z` at `0x14009e7bd`
- `msvcp_win!?__ExceptionPtrCreate@@YAXPEAX@Z` at `0x14009e7b3`
- `msvcp_win!?__ExceptionPtrCreate@@YAXPEAX@Z` at `0x14009e7b3`
- `msvcp_win!?__ExceptionPtrDestroy@@YAXPEAX@Z` at `0x14009e7d5`
- `msvcp_win!?__ExceptionPtrDestroy@@YAXPEAX@Z` at `0x14009e7d5`

## pseudocode

```c
__int64 __fastcall Concurrency::details::_PPLTaskHandle_unsigned_char_Concurrency::task_unsigned_char_::_InitialTaskHandle_void__lambda_22ca94be88cc0567c38a3454635a1c54__Concurrency::details::_TypeSelectorNoAsync__Concurrency::details::_TaskProcHandle_::invoke_::_1_::catch_10(
        __int64 a1,
        __int64 a2)
{
  Concurrency::details::_Task_impl_base *v3; // rbx

  v3 = *(Concurrency::details::_Task_impl_base **)(*(_QWORD *)(a2 + 240) + 8LL);
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
0x14009e78e  mov     [rsp+arg_8], rdx
0x14009e793  push    rbx
0x14009e794  push    rbp
0x14009e795  sub     rsp, 38h
0x14009e799  mov     rbp, rdx
0x14009e79c  mov     rax, [rbp+0F0h]
0x14009e7a3  mov     rbx, [rax+8]
0x14009e7a7  xorps   xmm0, xmm0
0x14009e7aa  movdqu  xmmword ptr [rbp+30h], xmm0
0x14009e7af  lea     rcx, [rbp+30h]
0x14009e7b3  call    cs:__imp_?__ExceptionPtrCreate@@YAXPEAX@Z; __ExceptionPtrCreate(void *)
0x14009e7b9  lea     rcx, [rbp+30h]
0x14009e7bd  call    cs:__imp_?__ExceptionPtrCurrentException@@YAXPEAX@Z; __ExceptionPtrCurrentException(void *)
0x14009e7c3  nop
0x14009e7c4  lea     rdx, [rbp+30h]; struct std::exception_ptr *
0x14009e7c8  mov     rcx, rbx; this
0x14009e7cb  call    ?_CancelWithException@_Task_impl_base@details@Concurrency@@QEAA_NAEBVexception_ptr@std@@@Z; Concurrency::details::_Task_impl_base::_CancelWithException(std::exception_ptr const &)
0x14009e7d0  nop
0x14009e7d1  lea     rcx, [rbp+30h]
0x14009e7d5  call    cs:__imp_?__ExceptionPtrDestroy@@YAXPEAX@Z; __ExceptionPtrDestroy(void *)
0x14009e7db  nop
0x14009e7dc  mov     rax, 0
0x14009e7e6  add     rsp, 38h
0x14009e7ea  pop     rbp
0x14009e7eb  pop     rbx
0x14009e7ec  retn
```
