# _Concurrency::details::_PPLTaskHandle_Optional_bool__Concurrency::task_Optional_bool___::_InitialTaskHandle_Optional_bool___lambda_f3e09f59ff4f256821f7695ec4f9692e__Concurrency::details::_TypeSelectorNoAsync__Concurrency::details::_TaskProcHandle_::invoke_::_1_::catch$17

- ea: `0x1400a28b9`
- end: `0x1400a2919`
- name: `_Concurrency::details::_PPLTaskHandle_Optional_bool__Concurrency::task_Optional_bool___::_InitialTaskHandle_Optional_bool___lambda_f3e09f59ff4f256821f7695ec4f9692e__Concurrency::details::_TypeSelectorNoAsync__Concurrency::details::_TaskProcHandle_::invoke_::_1_::catch$17`
- size: `96`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task`

## callees

- `0x140019988`

## import_xrefs

- `msvcp_win!?__ExceptionPtrCurrentException@@YAXPEAX@Z` at `0x1400a28e8`
- `msvcp_win!?__ExceptionPtrCurrentException@@YAXPEAX@Z` at `0x1400a28e8`
- `msvcp_win!?__ExceptionPtrCreate@@YAXPEAX@Z` at `0x1400a28de`
- `msvcp_win!?__ExceptionPtrCreate@@YAXPEAX@Z` at `0x1400a28de`
- `msvcp_win!?__ExceptionPtrDestroy@@YAXPEAX@Z` at `0x1400a2900`
- `msvcp_win!?__ExceptionPtrDestroy@@YAXPEAX@Z` at `0x1400a2900`

## pseudocode

```c
__int64 __fastcall Concurrency::details::_PPLTaskHandle_Optional_bool__Concurrency::task_Optional_bool___::_InitialTaskHandle_Optional_bool___lambda_f3e09f59ff4f256821f7695ec4f9692e__Concurrency::details::_TypeSelectorNoAsync__Concurrency::details::_TaskProcHandle_::invoke_::_1_::catch_17(
        __int64 a1,
        __int64 a2)
{
  Concurrency::details::_Task_impl_base *v3; // rbx

  v3 = *(Concurrency::details::_Task_impl_base **)(*(_QWORD *)(a2 + 224) + 8LL);
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
0x1400a28b9  mov     [rsp+arg_8], rdx
0x1400a28be  push    rbx
0x1400a28bf  push    rbp
0x1400a28c0  sub     rsp, 38h
0x1400a28c4  mov     rbp, rdx
0x1400a28c7  mov     rax, [rbp+0E0h]
0x1400a28ce  mov     rbx, [rax+8]
0x1400a28d2  xorps   xmm0, xmm0
0x1400a28d5  movdqu  xmmword ptr [rbp+30h], xmm0
0x1400a28da  lea     rcx, [rbp+30h]
0x1400a28de  call    cs:__imp_?__ExceptionPtrCreate@@YAXPEAX@Z; __ExceptionPtrCreate(void *)
0x1400a28e4  lea     rcx, [rbp+30h]
0x1400a28e8  call    cs:__imp_?__ExceptionPtrCurrentException@@YAXPEAX@Z; __ExceptionPtrCurrentException(void *)
0x1400a28ee  nop
0x1400a28ef  lea     rdx, [rbp+30h]; struct std::exception_ptr *
0x1400a28f3  mov     rcx, rbx; this
0x1400a28f6  call    ?_CancelWithException@_Task_impl_base@details@Concurrency@@QEAA_NAEBVexception_ptr@std@@@Z; Concurrency::details::_Task_impl_base::_CancelWithException(std::exception_ptr const &)
0x1400a28fb  nop
0x1400a28fc  lea     rcx, [rbp+30h]
0x1400a2900  call    cs:__imp_?__ExceptionPtrDestroy@@YAXPEAX@Z; __ExceptionPtrDestroy(void *)
0x1400a2906  nop
0x1400a2907  mov     rax, 0
0x1400a2911  add     rsp, 38h
0x1400a2915  pop     rbp
0x1400a2916  pop     rbx
0x1400a2917  retn
```
