# _p9fs::Handler::Run$_ResumeCoro$1_::_1_::catch$36

- ea: `0x180031dbc`
- end: `0x180031e40`
- name: `_p9fs::Handler::Run$_ResumeCoro$1_::_1_::catch$36`
- size: `132`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `loader_planting`

## import_xrefs

- `msvcp_win!?__ExceptionPtrDestroy@@YAXPEAX@Z` at `0x180031e27`
- `msvcp_win!?__ExceptionPtrDestroy@@YAXPEAX@Z` at `0x180031e27`
- `msvcp_win!?__ExceptionPtrCurrentException@@YAXPEAX@Z` at `0x180031e09`
- `msvcp_win!?__ExceptionPtrCurrentException@@YAXPEAX@Z` at `0x180031e09`
- `msvcp_win!?__ExceptionPtrCreate@@YAXPEAX@Z` at `0x180031dfc`
- `msvcp_win!?__ExceptionPtrCreate@@YAXPEAX@Z` at `0x180031dfc`
- `msvcp_win!?__ExceptionPtrAssign@@YAXPEAXPEBX@Z` at `0x180031e1a`
- `msvcp_win!?__ExceptionPtrAssign@@YAXPEAXPEBX@Z` at `0x180031e1a`

## pseudocode

```c
__int64 __fastcall p9fs::Handler::Run__ResumeCoro_1_::_1_::catch_36(__int64 a1, __int64 a2)
{
  __int64 v2; // rbx

  v2 = *(_QWORD *)(a2 + 80);
  *(_WORD *)(v2 + 8) = -1;
  *(_OWORD *)(v2 + 2256) = 0;
  *(_QWORD *)(v2 + 2256) = 0;
  *(_QWORD *)(v2 + 2264) = 0;
  __ExceptionPtrCreate((void *)(v2 + 2256));
  __ExceptionPtrCurrentException((void *)(v2 + 2256));
  __ExceptionPtrAssign((void *)(v2 - 16), (const void *)(v2 + 2256));
  __ExceptionPtrDestroy((void *)(v2 + 2256));
  return 0;
}

```

## disassembly

```asm
0x180031dbc  mov     [rsp+arg_8], rdx
0x180031dc1  push    rbx
0x180031dc2  push    rbp
0x180031dc3  sub     rsp, 38h
0x180031dc7  mov     rbp, rdx
0x180031dca  or      eax, 0FFFFFFFFh
0x180031dcd  mov     rbx, [rbp+50h]
0x180031dd1  mov     [rbx+8], ax
0x180031dd5  xorps   xmm0, xmm0
0x180031dd8  movups  xmmword ptr [rbx+8D0h], xmm0
0x180031ddf  mov     qword ptr [rbx+8D0h], 0
0x180031dea  mov     qword ptr [rbx+8D8h], 0
0x180031df5  lea     rcx, [rbx+8D0h]
0x180031dfc  call    cs:__imp_?__ExceptionPtrCreate@@YAXPEAX@Z; __ExceptionPtrCreate(void *)
0x180031e02  lea     rcx, [rbx+8D0h]
0x180031e09  call    cs:__imp_?__ExceptionPtrCurrentException@@YAXPEAX@Z; __ExceptionPtrCurrentException(void *)
0x180031e0f  lea     rdx, [rbx+8D0h]
0x180031e16  lea     rcx, [rbx-10h]
0x180031e1a  call    cs:__imp_?__ExceptionPtrAssign@@YAXPEAXPEBX@Z; __ExceptionPtrAssign(void *,void const *)
0x180031e20  lea     rcx, [rbx+8D0h]
0x180031e27  call    cs:__imp_?__ExceptionPtrDestroy@@YAXPEAX@Z; __ExceptionPtrDestroy(void *)
0x180031e2d  nop
0x180031e2e  mov     rax, 0
0x180031e38  add     rsp, 38h
0x180031e3c  pop     rbp
0x180031e3d  pop     rbx
0x180031e3e  retn
```
