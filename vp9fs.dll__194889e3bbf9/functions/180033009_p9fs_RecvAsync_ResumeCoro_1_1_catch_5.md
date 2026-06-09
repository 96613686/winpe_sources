# _p9fs::RecvAsync$_ResumeCoro$1_::_1_::catch$5

- ea: `0x180033009`
- end: `0x18003308d`
- name: `_p9fs::RecvAsync$_ResumeCoro$1_::_1_::catch$5`
- size: `132`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: ``

## import_xrefs

- `msvcp_win!?__ExceptionPtrDestroy@@YAXPEAX@Z` at `0x180033074`
- `msvcp_win!?__ExceptionPtrDestroy@@YAXPEAX@Z` at `0x180033074`
- `msvcp_win!?__ExceptionPtrCurrentException@@YAXPEAX@Z` at `0x180033056`
- `msvcp_win!?__ExceptionPtrCurrentException@@YAXPEAX@Z` at `0x180033056`
- `msvcp_win!?__ExceptionPtrCreate@@YAXPEAX@Z` at `0x180033049`
- `msvcp_win!?__ExceptionPtrCreate@@YAXPEAX@Z` at `0x180033049`
- `msvcp_win!?__ExceptionPtrAssign@@YAXPEAXPEBX@Z` at `0x180033067`
- `msvcp_win!?__ExceptionPtrAssign@@YAXPEAXPEBX@Z` at `0x180033067`

## pseudocode

```c
__int64 __fastcall p9fs::RecvAsync__ResumeCoro_1_::_1_::catch_5(__int64 a1, __int64 a2)
{
  __int64 v2; // rbx

  v2 = *(_QWORD *)(a2 + 64);
  *(_WORD *)(v2 + 8) = -1;
  *(_OWORD *)(v2 + 152) = 0;
  *(_QWORD *)(v2 + 152) = 0;
  *(_QWORD *)(v2 + 160) = 0;
  __ExceptionPtrCreate((void *)(v2 + 152));
  __ExceptionPtrCurrentException((void *)(v2 + 152));
  __ExceptionPtrAssign((void *)(v2 - 32), (const void *)(v2 + 152));
  __ExceptionPtrDestroy((void *)(v2 + 152));
  return 0;
}

```

## disassembly

```asm
0x180033009  mov     [rsp+arg_8], rdx
0x18003300e  push    rbx
0x18003300f  push    rbp
0x180033010  sub     rsp, 38h
0x180033014  mov     rbp, rdx
0x180033017  or      eax, 0FFFFFFFFh
0x18003301a  mov     rbx, [rbp+40h]
0x18003301e  mov     [rbx+8], ax
0x180033022  xorps   xmm0, xmm0
0x180033025  movups  xmmword ptr [rbx+98h], xmm0
0x18003302c  mov     qword ptr [rbx+98h], 0
0x180033037  mov     qword ptr [rbx+0A0h], 0
0x180033042  lea     rcx, [rbx+98h]
0x180033049  call    cs:__imp_?__ExceptionPtrCreate@@YAXPEAX@Z; __ExceptionPtrCreate(void *)
0x18003304f  lea     rcx, [rbx+98h]
0x180033056  call    cs:__imp_?__ExceptionPtrCurrentException@@YAXPEAX@Z; __ExceptionPtrCurrentException(void *)
0x18003305c  lea     rdx, [rbx+98h]
0x180033063  lea     rcx, [rbx-20h]
0x180033067  call    cs:__imp_?__ExceptionPtrAssign@@YAXPEAXPEBX@Z; __ExceptionPtrAssign(void *,void const *)
0x18003306d  lea     rcx, [rbx+98h]
0x180033074  call    cs:__imp_?__ExceptionPtrDestroy@@YAXPEAX@Z; __ExceptionPtrDestroy(void *)
0x18003307a  nop
0x18003307b  mov     rax, 0
0x180033085  add     rsp, 38h
0x180033089  pop     rbp
0x18003308a  pop     rbx
0x18003308b  retn
```
