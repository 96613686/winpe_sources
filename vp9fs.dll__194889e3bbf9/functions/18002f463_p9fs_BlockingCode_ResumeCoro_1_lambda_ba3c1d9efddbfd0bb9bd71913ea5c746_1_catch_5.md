# _p9fs::BlockingCode$_ResumeCoro$1__lambda_ba3c1d9efddbfd0bb9bd71913ea5c746____::_1_::catch$5

- ea: `0x18002f463`
- end: `0x18002f4d2`
- name: `_p9fs::BlockingCode$_ResumeCoro$1__lambda_ba3c1d9efddbfd0bb9bd71913ea5c746____::_1_::catch$5`
- size: `111`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: ``

## import_xrefs

- `msvcp_win!?__ExceptionPtrDestroy@@YAXPEAX@Z` at `0x18002f4b9`
- `msvcp_win!?__ExceptionPtrDestroy@@YAXPEAX@Z` at `0x18002f4b9`
- `msvcp_win!?__ExceptionPtrCurrentException@@YAXPEAX@Z` at `0x18002f4a1`
- `msvcp_win!?__ExceptionPtrCurrentException@@YAXPEAX@Z` at `0x18002f4a1`
- `msvcp_win!?__ExceptionPtrCreate@@YAXPEAX@Z` at `0x18002f497`
- `msvcp_win!?__ExceptionPtrCreate@@YAXPEAX@Z` at `0x18002f497`
- `msvcp_win!?__ExceptionPtrAssign@@YAXPEAXPEBX@Z` at `0x18002f4af`
- `msvcp_win!?__ExceptionPtrAssign@@YAXPEAXPEBX@Z` at `0x18002f4af`

## pseudocode

```c
__int64 __fastcall p9fs::BlockingCode__ResumeCoro_1__lambda_ba3c1d9efddbfd0bb9bd71913ea5c746____::_1_::catch_5(
        __int64 a1,
        __int64 a2)
{
  __int64 v2; // rbx

  v2 = *(_QWORD *)(a2 + 40);
  *(_WORD *)(v2 + 8) = -1;
  *(_OWORD *)(v2 + 40) = 0;
  *(_QWORD *)(v2 + 40) = 0;
  *(_QWORD *)(v2 + 48) = 0;
  __ExceptionPtrCreate((void *)(v2 + 40));
  __ExceptionPtrCurrentException((void *)(v2 + 40));
  __ExceptionPtrAssign((void *)(v2 - 32), (const void *)(v2 + 40));
  __ExceptionPtrDestroy((void *)(v2 + 40));
  return 0;
}

```

## disassembly

```asm
0x18002f463  mov     [rsp+arg_8], rdx
0x18002f468  push    rbx
0x18002f469  push    rbp
0x18002f46a  sub     rsp, 28h
0x18002f46e  mov     rbp, rdx
0x18002f471  or      eax, 0FFFFFFFFh
0x18002f474  mov     rbx, [rbp+28h]
0x18002f478  mov     [rbx+8], ax
0x18002f47c  xorps   xmm0, xmm0
0x18002f47f  movups  xmmword ptr [rbx+28h], xmm0
0x18002f483  mov     qword ptr [rbx+28h], 0
0x18002f48b  mov     qword ptr [rbx+30h], 0
0x18002f493  lea     rcx, [rbx+28h]
0x18002f497  call    cs:__imp_?__ExceptionPtrCreate@@YAXPEAX@Z; __ExceptionPtrCreate(void *)
0x18002f49d  lea     rcx, [rbx+28h]
0x18002f4a1  call    cs:__imp_?__ExceptionPtrCurrentException@@YAXPEAX@Z; __ExceptionPtrCurrentException(void *)
0x18002f4a7  lea     rdx, [rbx+28h]
0x18002f4ab  lea     rcx, [rbx-20h]
0x18002f4af  call    cs:__imp_?__ExceptionPtrAssign@@YAXPEAXPEBX@Z; __ExceptionPtrAssign(void *,void const *)
0x18002f4b5  lea     rcx, [rbx+28h]
0x18002f4b9  call    cs:__imp_?__ExceptionPtrDestroy@@YAXPEAX@Z; __ExceptionPtrDestroy(void *)
0x18002f4bf  nop
0x18002f4c0  mov     rax, 0
0x18002f4ca  add     rsp, 28h
0x18002f4ce  pop     rbp
0x18002f4cf  pop     rbx
0x18002f4d0  retn
```
