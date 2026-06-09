# _Concurrency::details::_Task_impl_base::_ScheduleTask_::_1_::catch$5

- ea: `0x14009e5b5`
- end: `0x14009e615`
- name: `_Concurrency::details::_Task_impl_base::_ScheduleTask_::_1_::catch$5`
- size: `96`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `service_task`

## callees

- `0x140019988`
- `0x14009e5b5`

## import_xrefs

- `msvcp_win!?__ExceptionPtrCurrentException@@YAXPEAX@Z` at `0x14009e5e4`
- `msvcp_win!?__ExceptionPtrCurrentException@@YAXPEAX@Z` at `0x14009e5e4`
- `msvcp_win!?__ExceptionPtrCreate@@YAXPEAX@Z` at `0x14009e5da`
- `msvcp_win!?__ExceptionPtrCreate@@YAXPEAX@Z` at `0x14009e5da`
- `msvcp_win!?__ExceptionPtrDestroy@@YAXPEAX@Z` at `0x14009e5fc`
- `msvcp_win!?__ExceptionPtrDestroy@@YAXPEAX@Z` at `0x14009e5fc`

## pseudocode

```c
__int64 __fastcall Concurrency::details::_Task_impl_base::_ScheduleTask_::_1_::catch_5(__int64 a1, __int64 a2)
{
  Concurrency::details::_Task_impl_base *v3; // rbx

  v3 = *(Concurrency::details::_Task_impl_base **)(a2 + 64);
  if ( !*((_QWORD *)v3 + 2) )
  {
    *(_OWORD *)(a2 + 32) = 0;
    __ExceptionPtrCreate((void *)(a2 + 32));
    __ExceptionPtrCurrentException((void *)(a2 + 32));
    Concurrency::details::_Task_impl_base::_CancelWithException(v3, (const struct std::exception_ptr *)(a2 + 32));
    __ExceptionPtrDestroy((void *)(a2 + 32));
  }
  return 0;
}

```

## disassembly

```asm
0x14009e5b5  mov     [rsp+arg_8], rdx
0x14009e5ba  push    rbx
0x14009e5bb  push    rbp
0x14009e5bc  sub     rsp, 28h
0x14009e5c0  mov     rbp, rdx
0x14009e5c3  mov     rbx, [rbp+40h]
0x14009e5c7  cmp     qword ptr [rbx+10h], 0
0x14009e5cc  jnz     short loc_14009E603
0x14009e5ce  xorps   xmm0, xmm0
0x14009e5d1  movdqu  xmmword ptr [rbp+20h], xmm0
0x14009e5d6  lea     rcx, [rbp+20h]
0x14009e5da  call    cs:__imp_?__ExceptionPtrCreate@@YAXPEAX@Z; __ExceptionPtrCreate(void *)
0x14009e5e0  lea     rcx, [rbp+20h]
0x14009e5e4  call    cs:__imp_?__ExceptionPtrCurrentException@@YAXPEAX@Z; __ExceptionPtrCurrentException(void *)
0x14009e5ea  nop
0x14009e5eb  lea     rdx, [rbp+20h]; struct std::exception_ptr *
0x14009e5ef  mov     rcx, rbx; this
0x14009e5f2  call    ?_CancelWithException@_Task_impl_base@details@Concurrency@@QEAA_NAEBVexception_ptr@std@@@Z; Concurrency::details::_Task_impl_base::_CancelWithException(std::exception_ptr const &)
0x14009e5f7  nop
0x14009e5f8  lea     rcx, [rbp+20h]
0x14009e5fc  call    cs:__imp_?__ExceptionPtrDestroy@@YAXPEAX@Z; __ExceptionPtrDestroy(void *)
0x14009e602  nop
0x14009e603  mov     rax, 0
0x14009e60d  add     rsp, 28h
0x14009e611  pop     rbp
0x14009e612  pop     rbx
0x14009e613  retn
```
