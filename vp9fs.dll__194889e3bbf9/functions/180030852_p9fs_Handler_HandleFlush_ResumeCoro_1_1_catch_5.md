# _p9fs::Handler::HandleFlush$_ResumeCoro$1_::_1_::catch$5

- ea: `0x180030852`
- end: `0x1800308c1`
- name: `_p9fs::Handler::HandleFlush$_ResumeCoro$1_::_1_::catch$5`
- size: `111`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `loader_planting`

## import_xrefs

- `msvcp_win!?__ExceptionPtrDestroy@@YAXPEAX@Z` at `0x1800308a8`
- `msvcp_win!?__ExceptionPtrDestroy@@YAXPEAX@Z` at `0x1800308a8`
- `msvcp_win!?__ExceptionPtrCurrentException@@YAXPEAX@Z` at `0x180030890`
- `msvcp_win!?__ExceptionPtrCurrentException@@YAXPEAX@Z` at `0x180030890`
- `msvcp_win!?__ExceptionPtrCreate@@YAXPEAX@Z` at `0x180030886`
- `msvcp_win!?__ExceptionPtrCreate@@YAXPEAX@Z` at `0x180030886`
- `msvcp_win!?__ExceptionPtrAssign@@YAXPEAXPEBX@Z` at `0x18003089e`
- `msvcp_win!?__ExceptionPtrAssign@@YAXPEAXPEBX@Z` at `0x18003089e`

## pseudocode

```c
__int64 __fastcall p9fs::Handler::HandleFlush__ResumeCoro_1_::_1_::catch_5(__int64 a1, __int64 a2)
{
  __int64 v2; // rbx

  v2 = *(_QWORD *)(a2 + 40);
  *(_WORD *)(v2 + 8) = -1;
  *(_OWORD *)(v2 + 56) = 0;
  *(_QWORD *)(v2 + 56) = 0;
  *(_QWORD *)(v2 + 64) = 0;
  __ExceptionPtrCreate((void *)(v2 + 56));
  __ExceptionPtrCurrentException((void *)(v2 + 56));
  __ExceptionPtrAssign((void *)(v2 - 32), (const void *)(v2 + 56));
  __ExceptionPtrDestroy((void *)(v2 + 56));
  return 0;
}

```

## disassembly

```asm
0x180030852  mov     [rsp+arg_8], rdx
0x180030857  push    rbx
0x180030858  push    rbp
0x180030859  sub     rsp, 28h
0x18003085d  mov     rbp, rdx
0x180030860  or      eax, 0FFFFFFFFh
0x180030863  mov     rbx, [rbp+28h]
0x180030867  mov     [rbx+8], ax
0x18003086b  xorps   xmm0, xmm0
0x18003086e  movups  xmmword ptr [rbx+38h], xmm0
0x180030872  mov     qword ptr [rbx+38h], 0
0x18003087a  mov     qword ptr [rbx+40h], 0
0x180030882  lea     rcx, [rbx+38h]
0x180030886  call    cs:__imp_?__ExceptionPtrCreate@@YAXPEAX@Z; __ExceptionPtrCreate(void *)
0x18003088c  lea     rcx, [rbx+38h]
0x180030890  call    cs:__imp_?__ExceptionPtrCurrentException@@YAXPEAX@Z; __ExceptionPtrCurrentException(void *)
0x180030896  lea     rdx, [rbx+38h]
0x18003089a  lea     rcx, [rbx-20h]
0x18003089e  call    cs:__imp_?__ExceptionPtrAssign@@YAXPEAXPEBX@Z; __ExceptionPtrAssign(void *,void const *)
0x1800308a4  lea     rcx, [rbx+38h]
0x1800308a8  call    cs:__imp_?__ExceptionPtrDestroy@@YAXPEAX@Z; __ExceptionPtrDestroy(void *)
0x1800308ae  nop
0x1800308af  mov     rax, 0
0x1800308b9  add     rsp, 28h
0x1800308bd  pop     rbp
0x1800308be  pop     rbx
0x1800308bf  retn
```
