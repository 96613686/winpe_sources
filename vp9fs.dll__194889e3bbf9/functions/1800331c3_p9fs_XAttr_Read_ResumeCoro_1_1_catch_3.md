# _p9fs::XAttr::Read$_ResumeCoro$1_::_1_::catch$3

- ea: `0x1800331c3`
- end: `0x180033232`
- name: `_p9fs::XAttr::Read$_ResumeCoro$1_::_1_::catch$3`
- size: `111`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: ``

## import_xrefs

- `msvcp_win!?__ExceptionPtrDestroy@@YAXPEAX@Z` at `0x180033219`
- `msvcp_win!?__ExceptionPtrDestroy@@YAXPEAX@Z` at `0x180033219`
- `msvcp_win!?__ExceptionPtrCurrentException@@YAXPEAX@Z` at `0x180033201`
- `msvcp_win!?__ExceptionPtrCurrentException@@YAXPEAX@Z` at `0x180033201`
- `msvcp_win!?__ExceptionPtrCreate@@YAXPEAX@Z` at `0x1800331f7`
- `msvcp_win!?__ExceptionPtrCreate@@YAXPEAX@Z` at `0x1800331f7`
- `msvcp_win!?__ExceptionPtrAssign@@YAXPEAXPEBX@Z` at `0x18003320f`
- `msvcp_win!?__ExceptionPtrAssign@@YAXPEAXPEBX@Z` at `0x18003320f`

## pseudocode

```c
__int64 __fastcall p9fs::XAttr::Read__ResumeCoro_1_::_1_::catch_3(__int64 a1, __int64 a2)
{
  __int64 v2; // rbx

  v2 = *(_QWORD *)(a2 + 40);
  *(_WORD *)(v2 + 8) = -1;
  *(_OWORD *)(v2 + 64) = 0;
  *(_QWORD *)(v2 + 64) = 0;
  *(_QWORD *)(v2 + 72) = 0;
  __ExceptionPtrCreate((void *)(v2 + 64));
  __ExceptionPtrCurrentException((void *)(v2 + 64));
  __ExceptionPtrAssign((void *)(v2 - 32), (const void *)(v2 + 64));
  __ExceptionPtrDestroy((void *)(v2 + 64));
  return 0;
}

```

## disassembly

```asm
0x1800331c3  mov     [rsp+arg_8], rdx
0x1800331c8  push    rbx
0x1800331c9  push    rbp
0x1800331ca  sub     rsp, 28h
0x1800331ce  mov     rbp, rdx
0x1800331d1  or      eax, 0FFFFFFFFh
0x1800331d4  mov     rbx, [rbp+28h]
0x1800331d8  mov     [rbx+8], ax
0x1800331dc  xorps   xmm0, xmm0
0x1800331df  movups  xmmword ptr [rbx+40h], xmm0
0x1800331e3  mov     qword ptr [rbx+40h], 0
0x1800331eb  mov     qword ptr [rbx+48h], 0
0x1800331f3  lea     rcx, [rbx+40h]
0x1800331f7  call    cs:__imp_?__ExceptionPtrCreate@@YAXPEAX@Z; __ExceptionPtrCreate(void *)
0x1800331fd  lea     rcx, [rbx+40h]
0x180033201  call    cs:__imp_?__ExceptionPtrCurrentException@@YAXPEAX@Z; __ExceptionPtrCurrentException(void *)
0x180033207  lea     rdx, [rbx+40h]
0x18003320b  lea     rcx, [rbx-20h]
0x18003320f  call    cs:__imp_?__ExceptionPtrAssign@@YAXPEAXPEBX@Z; __ExceptionPtrAssign(void *,void const *)
0x180033215  lea     rcx, [rbx+40h]
0x180033219  call    cs:__imp_?__ExceptionPtrDestroy@@YAXPEAX@Z; __ExceptionPtrDestroy(void *)
0x18003321f  nop
0x180033220  mov     rax, 0
0x18003322a  add     rsp, 28h
0x18003322e  pop     rbp
0x18003322f  pop     rbx
0x180033230  retn
```
