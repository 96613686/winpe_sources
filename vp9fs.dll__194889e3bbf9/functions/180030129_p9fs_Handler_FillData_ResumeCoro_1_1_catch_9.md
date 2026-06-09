# _p9fs::Handler::FillData$_ResumeCoro$1_::_1_::catch$9

- ea: `0x180030129`
- end: `0x180030198`
- name: `_p9fs::Handler::FillData$_ResumeCoro$1_::_1_::catch$9`
- size: `111`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `loader_planting`

## import_xrefs

- `msvcp_win!?__ExceptionPtrDestroy@@YAXPEAX@Z` at `0x18003017f`
- `msvcp_win!?__ExceptionPtrDestroy@@YAXPEAX@Z` at `0x18003017f`
- `msvcp_win!?__ExceptionPtrCurrentException@@YAXPEAX@Z` at `0x180030167`
- `msvcp_win!?__ExceptionPtrCurrentException@@YAXPEAX@Z` at `0x180030167`
- `msvcp_win!?__ExceptionPtrCreate@@YAXPEAX@Z` at `0x18003015d`
- `msvcp_win!?__ExceptionPtrCreate@@YAXPEAX@Z` at `0x18003015d`
- `msvcp_win!?__ExceptionPtrAssign@@YAXPEAXPEBX@Z` at `0x180030175`
- `msvcp_win!?__ExceptionPtrAssign@@YAXPEAXPEBX@Z` at `0x180030175`

## pseudocode

```c
__int64 __fastcall p9fs::Handler::FillData__ResumeCoro_1_::_1_::catch_9(__int64 a1, __int64 a2)
{
  __int64 v2; // rbx

  v2 = *(_QWORD *)(a2 + 64);
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
0x180030129  mov     [rsp+arg_8], rdx
0x18003012e  push    rbx
0x18003012f  push    rbp
0x180030130  sub     rsp, 38h
0x180030134  mov     rbp, rdx
0x180030137  or      eax, 0FFFFFFFFh
0x18003013a  mov     rbx, [rbp+40h]
0x18003013e  mov     [rbx+8], ax
0x180030142  xorps   xmm0, xmm0
0x180030145  movups  xmmword ptr [rbx+40h], xmm0
0x180030149  mov     qword ptr [rbx+40h], 0
0x180030151  mov     qword ptr [rbx+48h], 0
0x180030159  lea     rcx, [rbx+40h]
0x18003015d  call    cs:__imp_?__ExceptionPtrCreate@@YAXPEAX@Z; __ExceptionPtrCreate(void *)
0x180030163  lea     rcx, [rbx+40h]
0x180030167  call    cs:__imp_?__ExceptionPtrCurrentException@@YAXPEAX@Z; __ExceptionPtrCurrentException(void *)
0x18003016d  lea     rdx, [rbx+40h]
0x180030171  lea     rcx, [rbx-20h]
0x180030175  call    cs:__imp_?__ExceptionPtrAssign@@YAXPEAXPEBX@Z; __ExceptionPtrAssign(void *,void const *)
0x18003017b  lea     rcx, [rbx+40h]
0x18003017f  call    cs:__imp_?__ExceptionPtrDestroy@@YAXPEAX@Z; __ExceptionPtrDestroy(void *)
0x180030185  nop
0x180030186  mov     rax, 0
0x180030190  add     rsp, 38h
0x180030194  pop     rbp
0x180030195  pop     rbx
0x180030196  retn
```
