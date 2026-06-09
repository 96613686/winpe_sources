# _p9fs::Socket::AcceptAsync$_ResumeCoro$1_::_1_::catch$26

- ea: `0x18003348a`
- end: `0x18003350e`
- name: `_p9fs::Socket::AcceptAsync$_ResumeCoro$1_::_1_::catch$26`
- size: `132`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: ``

## import_xrefs

- `msvcp_win!?__ExceptionPtrDestroy@@YAXPEAX@Z` at `0x1800334f5`
- `msvcp_win!?__ExceptionPtrDestroy@@YAXPEAX@Z` at `0x1800334f5`
- `msvcp_win!?__ExceptionPtrCurrentException@@YAXPEAX@Z` at `0x1800334d7`
- `msvcp_win!?__ExceptionPtrCurrentException@@YAXPEAX@Z` at `0x1800334d7`
- `msvcp_win!?__ExceptionPtrCreate@@YAXPEAX@Z` at `0x1800334ca`
- `msvcp_win!?__ExceptionPtrCreate@@YAXPEAX@Z` at `0x1800334ca`
- `msvcp_win!?__ExceptionPtrAssign@@YAXPEAXPEBX@Z` at `0x1800334e8`
- `msvcp_win!?__ExceptionPtrAssign@@YAXPEAXPEBX@Z` at `0x1800334e8`

## pseudocode

```c
__int64 __fastcall p9fs::Socket::AcceptAsync__ResumeCoro_1_::_1_::catch_26(__int64 a1, __int64 a2)
{
  __int64 v2; // rbx

  v2 = *(_QWORD *)(a2 + 88);
  *(_WORD *)(v2 + 8) = -1;
  *(_OWORD *)(v2 + 216) = 0;
  *(_QWORD *)(v2 + 216) = 0;
  *(_QWORD *)(v2 + 224) = 0;
  __ExceptionPtrCreate((void *)(v2 + 216));
  __ExceptionPtrCurrentException((void *)(v2 + 216));
  __ExceptionPtrAssign((void *)(v2 - 32), (const void *)(v2 + 216));
  __ExceptionPtrDestroy((void *)(v2 + 216));
  return 0;
}

```

## disassembly

```asm
0x18003348a  mov     [rsp+arg_8], rdx
0x18003348f  push    rbx
0x180033490  push    rbp
0x180033491  sub     rsp, 48h
0x180033495  mov     rbp, rdx
0x180033498  or      eax, 0FFFFFFFFh
0x18003349b  mov     rbx, [rbp+58h]
0x18003349f  mov     [rbx+8], ax
0x1800334a3  xorps   xmm0, xmm0
0x1800334a6  movups  xmmword ptr [rbx+0D8h], xmm0
0x1800334ad  mov     qword ptr [rbx+0D8h], 0
0x1800334b8  mov     qword ptr [rbx+0E0h], 0
0x1800334c3  lea     rcx, [rbx+0D8h]
0x1800334ca  call    cs:__imp_?__ExceptionPtrCreate@@YAXPEAX@Z; __ExceptionPtrCreate(void *)
0x1800334d0  lea     rcx, [rbx+0D8h]
0x1800334d7  call    cs:__imp_?__ExceptionPtrCurrentException@@YAXPEAX@Z; __ExceptionPtrCurrentException(void *)
0x1800334dd  lea     rdx, [rbx+0D8h]
0x1800334e4  lea     rcx, [rbx-20h]
0x1800334e8  call    cs:__imp_?__ExceptionPtrAssign@@YAXPEAXPEBX@Z; __ExceptionPtrAssign(void *,void const *)
0x1800334ee  lea     rcx, [rbx+0D8h]
0x1800334f5  call    cs:__imp_?__ExceptionPtrDestroy@@YAXPEAX@Z; __ExceptionPtrDestroy(void *)
0x1800334fb  nop
0x1800334fc  mov     rax, 0
0x180033506  add     rsp, 48h
0x18003350a  pop     rbp
0x18003350b  pop     rbx
0x18003350c  retn
```
