# _p9fs::AcceptExAsync$_ResumeCoro$1_::_1_::catch$5

- ea: `0x180032dd8`
- end: `0x180032e5c`
- name: `_p9fs::AcceptExAsync$_ResumeCoro$1_::_1_::catch$5`
- size: `132`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: ``

## import_xrefs

- `msvcp_win!?__ExceptionPtrDestroy@@YAXPEAX@Z` at `0x180032e43`
- `msvcp_win!?__ExceptionPtrDestroy@@YAXPEAX@Z` at `0x180032e43`
- `msvcp_win!?__ExceptionPtrCurrentException@@YAXPEAX@Z` at `0x180032e25`
- `msvcp_win!?__ExceptionPtrCurrentException@@YAXPEAX@Z` at `0x180032e25`
- `msvcp_win!?__ExceptionPtrCreate@@YAXPEAX@Z` at `0x180032e18`
- `msvcp_win!?__ExceptionPtrCreate@@YAXPEAX@Z` at `0x180032e18`
- `msvcp_win!?__ExceptionPtrAssign@@YAXPEAXPEBX@Z` at `0x180032e36`
- `msvcp_win!?__ExceptionPtrAssign@@YAXPEAXPEBX@Z` at `0x180032e36`

## pseudocode

```c
__int64 __fastcall p9fs::AcceptExAsync__ResumeCoro_1_::_1_::catch_5(__int64 a1, __int64 a2)
{
  __int64 v2; // rbx

  v2 = *(_QWORD *)(a2 + 64);
  *(_WORD *)(v2 + 8) = -1;
  *(_OWORD *)(v2 + 168) = 0;
  *(_QWORD *)(v2 + 168) = 0;
  *(_QWORD *)(v2 + 176) = 0;
  __ExceptionPtrCreate((void *)(v2 + 168));
  __ExceptionPtrCurrentException((void *)(v2 + 168));
  __ExceptionPtrAssign((void *)(v2 - 32), (const void *)(v2 + 168));
  __ExceptionPtrDestroy((void *)(v2 + 168));
  return 0;
}

```

## disassembly

```asm
0x180032dd8  mov     [rsp+arg_8], rdx
0x180032ddd  push    rbx
0x180032dde  push    rbp
0x180032ddf  sub     rsp, 38h
0x180032de3  mov     rbp, rdx
0x180032de6  or      eax, 0FFFFFFFFh
0x180032de9  mov     rbx, [rbp+40h]
0x180032ded  mov     [rbx+8], ax
0x180032df1  xorps   xmm0, xmm0
0x180032df4  movups  xmmword ptr [rbx+0A8h], xmm0
0x180032dfb  mov     qword ptr [rbx+0A8h], 0
0x180032e06  mov     qword ptr [rbx+0B0h], 0
0x180032e11  lea     rcx, [rbx+0A8h]
0x180032e18  call    cs:__imp_?__ExceptionPtrCreate@@YAXPEAX@Z; __ExceptionPtrCreate(void *)
0x180032e1e  lea     rcx, [rbx+0A8h]
0x180032e25  call    cs:__imp_?__ExceptionPtrCurrentException@@YAXPEAX@Z; __ExceptionPtrCurrentException(void *)
0x180032e2b  lea     rdx, [rbx+0A8h]
0x180032e32  lea     rcx, [rbx-20h]
0x180032e36  call    cs:__imp_?__ExceptionPtrAssign@@YAXPEAXPEBX@Z; __ExceptionPtrAssign(void *,void const *)
0x180032e3c  lea     rcx, [rbx+0A8h]
0x180032e43  call    cs:__imp_?__ExceptionPtrDestroy@@YAXPEAX@Z; __ExceptionPtrDestroy(void *)
0x180032e49  nop
0x180032e4a  mov     rax, 0
0x180032e54  add     rsp, 38h
0x180032e58  pop     rbp
0x180032e59  pop     rbx
0x180032e5a  retn
```
