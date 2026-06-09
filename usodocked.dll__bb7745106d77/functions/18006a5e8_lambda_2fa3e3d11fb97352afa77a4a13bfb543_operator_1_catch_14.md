# __lambda_2fa3e3d11fb97352afa77a4a13bfb543_::operator()_::_1_::catch$14

- ea: `0x18006a5e8`
- end: `0x18006a644`
- name: `__lambda_2fa3e3d11fb97352afa77a4a13bfb543_::operator()_::_1_::catch$14`
- size: `92`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task`

## callees

- `0x180038408`

## import_xrefs

- `msvcp_win!?__ExceptionPtrCreate@@YAXPEAX@Z` at `0x18006a609`
- `msvcp_win!?__ExceptionPtrCreate@@YAXPEAX@Z` at `0x18006a609`
- `msvcp_win!?__ExceptionPtrCurrentException@@YAXPEAX@Z` at `0x18006a613`
- `msvcp_win!?__ExceptionPtrCurrentException@@YAXPEAX@Z` at `0x18006a613`
- `msvcp_win!?__ExceptionPtrDestroy@@YAXPEAX@Z` at `0x18006a62b`
- `msvcp_win!?__ExceptionPtrDestroy@@YAXPEAX@Z` at `0x18006a62b`

## pseudocode

```c
__int64 __fastcall _lambda_2fa3e3d11fb97352afa77a4a13bfb543_::operator()_::_1_::catch_14(__int64 a1, __int64 a2)
{
  Concurrency::details::_Task_impl_base *v3; // rbx

  v3 = *(Concurrency::details::_Task_impl_base **)(a2 + 208);
  *(_OWORD *)(a2 + 32) = 0;
  __ExceptionPtrCreate((void *)(a2 + 32));
  __ExceptionPtrCurrentException((void *)(a2 + 32));
  Concurrency::details::_Task_impl_base::_CancelWithException(v3, (const struct std::exception_ptr *)(a2 + 32));
  __ExceptionPtrDestroy((void *)(a2 + 32));
  return 0;
}

```

## disassembly

```asm
0x18006a5e8  mov     [rsp+arg_8], rdx
0x18006a5ed  push    rbx
0x18006a5ee  push    rbp
0x18006a5ef  sub     rsp, 28h
0x18006a5f3  mov     rbp, rdx
0x18006a5f6  mov     rbx, [rbp+0D0h]
0x18006a5fd  xorps   xmm0, xmm0
0x18006a600  movdqu  xmmword ptr [rbp+20h], xmm0
0x18006a605  lea     rcx, [rbp+20h]
0x18006a609  call    cs:__imp_?__ExceptionPtrCreate@@YAXPEAX@Z; __ExceptionPtrCreate(void *)
0x18006a60f  lea     rcx, [rbp+20h]
0x18006a613  call    cs:__imp_?__ExceptionPtrCurrentException@@YAXPEAX@Z; __ExceptionPtrCurrentException(void *)
0x18006a619  nop
0x18006a61a  lea     rdx, [rbp+20h]; struct std::exception_ptr *
0x18006a61e  mov     rcx, rbx; this
0x18006a621  call    ?_CancelWithException@_Task_impl_base@details@Concurrency@@QEAA_NAEBVexception_ptr@std@@@Z; Concurrency::details::_Task_impl_base::_CancelWithException(std::exception_ptr const &)
0x18006a626  nop
0x18006a627  lea     rcx, [rbp+20h]
0x18006a62b  call    cs:__imp_?__ExceptionPtrDestroy@@YAXPEAX@Z; __ExceptionPtrDestroy(void *)
0x18006a631  nop
0x18006a632  mov     rax, 0
0x18006a63c  add     rsp, 28h
0x18006a640  pop     rbp
0x18006a641  pop     rbx
0x18006a642  retn
```
