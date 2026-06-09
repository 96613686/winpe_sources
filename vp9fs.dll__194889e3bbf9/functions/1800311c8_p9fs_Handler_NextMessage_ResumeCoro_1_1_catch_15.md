# _p9fs::Handler::NextMessage$_ResumeCoro$1_::_1_::catch$15

- ea: `0x1800311c8`
- end: `0x180031237`
- name: `_p9fs::Handler::NextMessage$_ResumeCoro$1_::_1_::catch$15`
- size: `111`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `loader_planting`

## import_xrefs

- `msvcp_win!?__ExceptionPtrDestroy@@YAXPEAX@Z` at `0x18003121e`
- `msvcp_win!?__ExceptionPtrDestroy@@YAXPEAX@Z` at `0x18003121e`
- `msvcp_win!?__ExceptionPtrCurrentException@@YAXPEAX@Z` at `0x180031206`
- `msvcp_win!?__ExceptionPtrCurrentException@@YAXPEAX@Z` at `0x180031206`
- `msvcp_win!?__ExceptionPtrCreate@@YAXPEAX@Z` at `0x1800311fc`
- `msvcp_win!?__ExceptionPtrCreate@@YAXPEAX@Z` at `0x1800311fc`
- `msvcp_win!?__ExceptionPtrAssign@@YAXPEAXPEBX@Z` at `0x180031214`
- `msvcp_win!?__ExceptionPtrAssign@@YAXPEAXPEBX@Z` at `0x180031214`

## pseudocode

```c
__int64 __fastcall p9fs::Handler::NextMessage__ResumeCoro_1_::_1_::catch_15(__int64 a1, __int64 a2)
{
  __int64 v2; // rbx

  v2 = *(_QWORD *)(a2 + 56);
  *(_WORD *)(v2 + 8) = -1;
  *(_OWORD *)(v2 + 96) = 0;
  *(_QWORD *)(v2 + 96) = 0;
  *(_QWORD *)(v2 + 104) = 0;
  __ExceptionPtrCreate((void *)(v2 + 96));
  __ExceptionPtrCurrentException((void *)(v2 + 96));
  __ExceptionPtrAssign((void *)(v2 - 32), (const void *)(v2 + 96));
  __ExceptionPtrDestroy((void *)(v2 + 96));
  return 0;
}

```

## disassembly

```asm
0x1800311c8  mov     [rsp+arg_8], rdx
0x1800311cd  push    rbx
0x1800311ce  push    rbp
0x1800311cf  sub     rsp, 28h
0x1800311d3  mov     rbp, rdx
0x1800311d6  or      eax, 0FFFFFFFFh
0x1800311d9  mov     rbx, [rbp+38h]
0x1800311dd  mov     [rbx+8], ax
0x1800311e1  xorps   xmm0, xmm0
0x1800311e4  movups  xmmword ptr [rbx+60h], xmm0
0x1800311e8  mov     qword ptr [rbx+60h], 0
0x1800311f0  mov     qword ptr [rbx+68h], 0
0x1800311f8  lea     rcx, [rbx+60h]
0x1800311fc  call    cs:__imp_?__ExceptionPtrCreate@@YAXPEAX@Z; __ExceptionPtrCreate(void *)
0x180031202  lea     rcx, [rbx+60h]
0x180031206  call    cs:__imp_?__ExceptionPtrCurrentException@@YAXPEAX@Z; __ExceptionPtrCurrentException(void *)
0x18003120c  lea     rdx, [rbx+60h]
0x180031210  lea     rcx, [rbx-20h]
0x180031214  call    cs:__imp_?__ExceptionPtrAssign@@YAXPEAXPEBX@Z; __ExceptionPtrAssign(void *,void const *)
0x18003121a  lea     rcx, [rbx+60h]
0x18003121e  call    cs:__imp_?__ExceptionPtrDestroy@@YAXPEAX@Z; __ExceptionPtrDestroy(void *)
0x180031224  nop
0x180031225  mov     rax, 0
0x18003122f  add     rsp, 28h
0x180031233  pop     rbp
0x180031234  pop     rbx
0x180031235  retn
```
