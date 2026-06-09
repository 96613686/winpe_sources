# _p9fs::HandleConnections$_ResumeCoro$1_::_1_::catch$32

- ea: `0x180030792`
- end: `0x180030821`
- name: `_p9fs::HandleConnections$_ResumeCoro$1_::_1_::catch$32`
- size: `143`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task`

## callees

- `0x180018f14`

## import_xrefs

- `msvcp_win!?__ExceptionPtrDestroy@@YAXPEAX@Z` at `0x1800307fe`
- `msvcp_win!?__ExceptionPtrDestroy@@YAXPEAX@Z` at `0x1800307fe`
- `msvcp_win!?__ExceptionPtrCurrentException@@YAXPEAX@Z` at `0x1800307e0`
- `msvcp_win!?__ExceptionPtrCurrentException@@YAXPEAX@Z` at `0x1800307e0`
- `msvcp_win!?__ExceptionPtrCreate@@YAXPEAX@Z` at `0x1800307d3`
- `msvcp_win!?__ExceptionPtrCreate@@YAXPEAX@Z` at `0x1800307d3`
- `msvcp_win!?__ExceptionPtrAssign@@YAXPEAXPEBX@Z` at `0x1800307f1`
- `msvcp_win!?__ExceptionPtrAssign@@YAXPEAXPEBX@Z` at `0x1800307f1`

## pseudocode

```c
__int64 __fastcall p9fs::HandleConnections__ResumeCoro_1_::_1_::catch_32(__int64 a1, __int64 a2)
{
  __int64 v2; // rbx

  v2 = *(_QWORD *)(a2 + 72);
  *(_WORD *)(v2 + 8) = -1;
  *(_OWORD *)(v2 + 3280) = 0;
  *(_QWORD *)(v2 + 3280) = 0;
  *(_QWORD *)(v2 + 3288) = 0;
  __ExceptionPtrCreate((void *)(v2 + 3280));
  __ExceptionPtrCurrentException((void *)(v2 + 3280));
  __ExceptionPtrAssign(*(void **)(v2 - 16), (const void *)(v2 + 3280));
  __ExceptionPtrDestroy((void *)(v2 + 3280));
  p9fs::AsyncTask::promise_type::Signal((p9fs::AsyncTask::promise_type *)(v2 - 16));
  return 0;
}

```

## disassembly

```asm
0x180030792  mov     [rsp+arg_8], rdx
0x180030797  push    rbx
0x180030798  push    rbp
0x180030799  push    rdi
0x18003079a  sub     rsp, 30h
0x18003079e  mov     rbp, rdx
0x1800307a1  or      eax, 0FFFFFFFFh
0x1800307a4  mov     rbx, [rbp+48h]
0x1800307a8  mov     [rbx+8], ax
0x1800307ac  xorps   xmm0, xmm0
0x1800307af  movups  xmmword ptr [rbx+0CD0h], xmm0
0x1800307b6  mov     qword ptr [rbx+0CD0h], 0
0x1800307c1  mov     qword ptr [rbx+0CD8h], 0
0x1800307cc  lea     rcx, [rbx+0CD0h]
0x1800307d3  call    cs:__imp_?__ExceptionPtrCreate@@YAXPEAX@Z; __ExceptionPtrCreate(void *)
0x1800307d9  lea     rcx, [rbx+0CD0h]
0x1800307e0  call    cs:__imp_?__ExceptionPtrCurrentException@@YAXPEAX@Z; __ExceptionPtrCurrentException(void *)
0x1800307e6  lea     rdx, [rbx+0CD0h]
0x1800307ed  mov     rcx, [rbx-10h]
0x1800307f1  call    cs:__imp_?__ExceptionPtrAssign@@YAXPEAXPEBX@Z; __ExceptionPtrAssign(void *,void const *)
0x1800307f7  lea     rcx, [rbx+0CD0h]
0x1800307fe  call    cs:__imp_?__ExceptionPtrDestroy@@YAXPEAX@Z; __ExceptionPtrDestroy(void *)
0x180030804  lea     rcx, [rbx-10h]; this
0x180030808  call    ?Signal@promise_type@AsyncTask@p9fs@@AEAAXXZ; p9fs::AsyncTask::promise_type::Signal(void)
0x18003080d  nop
0x18003080e  mov     rax, 0
0x180030818  add     rsp, 30h
0x18003081c  pop     rdi
0x18003081d  pop     rbp
0x18003081e  pop     rbx
0x18003081f  retn
```
