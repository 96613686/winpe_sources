# __lambda_3123e5f836e94e335610d7bf7d199c56_$_ResumeCoro$1::operator()_::_1_::catch$17

- ea: `0x18002fbb1`
- end: `0x18002fc40`
- name: `__lambda_3123e5f836e94e335610d7bf7d199c56_$_ResumeCoro$1::operator()_::_1_::catch$17`
- size: `143`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task`

## callees

- `0x180018f14`

## import_xrefs

- `msvcp_win!?__ExceptionPtrDestroy@@YAXPEAX@Z` at `0x18002fc1d`
- `msvcp_win!?__ExceptionPtrDestroy@@YAXPEAX@Z` at `0x18002fc1d`
- `msvcp_win!?__ExceptionPtrCurrentException@@YAXPEAX@Z` at `0x18002fbff`
- `msvcp_win!?__ExceptionPtrCurrentException@@YAXPEAX@Z` at `0x18002fbff`
- `msvcp_win!?__ExceptionPtrCreate@@YAXPEAX@Z` at `0x18002fbf2`
- `msvcp_win!?__ExceptionPtrCreate@@YAXPEAX@Z` at `0x18002fbf2`
- `msvcp_win!?__ExceptionPtrAssign@@YAXPEAXPEBX@Z` at `0x18002fc10`
- `msvcp_win!?__ExceptionPtrAssign@@YAXPEAXPEBX@Z` at `0x18002fc10`

## pseudocode

```c
__int64 __fastcall _lambda_3123e5f836e94e335610d7bf7d199c56___ResumeCoro_1::operator()_::_1_::catch_17(
        __int64 a1,
        __int64 a2)
{
  __int64 v2; // rbx

  v2 = *(_QWORD *)(a2 + 56);
  *(_WORD *)(v2 + 8) = -1;
  *(_OWORD *)(v2 + 320) = 0;
  *(_QWORD *)(v2 + 320) = 0;
  *(_QWORD *)(v2 + 328) = 0;
  __ExceptionPtrCreate((void *)(v2 + 320));
  __ExceptionPtrCurrentException((void *)(v2 + 320));
  __ExceptionPtrAssign(*(void **)(v2 - 16), (const void *)(v2 + 320));
  __ExceptionPtrDestroy((void *)(v2 + 320));
  p9fs::AsyncTask::promise_type::Signal((p9fs::AsyncTask::promise_type *)(v2 - 16));
  return 0;
}

```

## disassembly

```asm
0x18002fbb1  mov     [rsp+arg_8], rdx
0x18002fbb6  push    rbx
0x18002fbb7  push    rbp
0x18002fbb8  push    rdi
0x18002fbb9  sub     rsp, 20h
0x18002fbbd  mov     rbp, rdx
0x18002fbc0  or      eax, 0FFFFFFFFh
0x18002fbc3  mov     rbx, [rbp+38h]
0x18002fbc7  mov     [rbx+8], ax
0x18002fbcb  xorps   xmm0, xmm0
0x18002fbce  movups  xmmword ptr [rbx+140h], xmm0
0x18002fbd5  mov     qword ptr [rbx+140h], 0
0x18002fbe0  mov     qword ptr [rbx+148h], 0
0x18002fbeb  lea     rcx, [rbx+140h]
0x18002fbf2  call    cs:__imp_?__ExceptionPtrCreate@@YAXPEAX@Z; __ExceptionPtrCreate(void *)
0x18002fbf8  lea     rcx, [rbx+140h]
0x18002fbff  call    cs:__imp_?__ExceptionPtrCurrentException@@YAXPEAX@Z; __ExceptionPtrCurrentException(void *)
0x18002fc05  lea     rdx, [rbx+140h]
0x18002fc0c  mov     rcx, [rbx-10h]
0x18002fc10  call    cs:__imp_?__ExceptionPtrAssign@@YAXPEAXPEBX@Z; __ExceptionPtrAssign(void *,void const *)
0x18002fc16  lea     rcx, [rbx+140h]
0x18002fc1d  call    cs:__imp_?__ExceptionPtrDestroy@@YAXPEAX@Z; __ExceptionPtrDestroy(void *)
0x18002fc23  lea     rcx, [rbx-10h]; this
0x18002fc27  call    ?Signal@promise_type@AsyncTask@p9fs@@AEAAXXZ; p9fs::AsyncTask::promise_type::Signal(void)
0x18002fc2c  nop
0x18002fc2d  mov     rax, 0
0x18002fc37  add     rsp, 20h
0x18002fc3b  pop     rdi
0x18002fc3c  pop     rbp
0x18002fc3d  pop     rbx
0x18002fc3e  retn
```
