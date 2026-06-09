# _p9fs::SendAsync$_ResumeCoro$1_::_1_::catch$5

- ea: `0x1800330be`
- end: `0x180033142`
- name: `_p9fs::SendAsync$_ResumeCoro$1_::_1_::catch$5`
- size: `132`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: ``

## import_xrefs

- `msvcp_win!?__ExceptionPtrDestroy@@YAXPEAX@Z` at `0x180033129`
- `msvcp_win!?__ExceptionPtrDestroy@@YAXPEAX@Z` at `0x180033129`
- `msvcp_win!?__ExceptionPtrCurrentException@@YAXPEAX@Z` at `0x18003310b`
- `msvcp_win!?__ExceptionPtrCurrentException@@YAXPEAX@Z` at `0x18003310b`
- `msvcp_win!?__ExceptionPtrCreate@@YAXPEAX@Z` at `0x1800330fe`
- `msvcp_win!?__ExceptionPtrCreate@@YAXPEAX@Z` at `0x1800330fe`
- `msvcp_win!?__ExceptionPtrAssign@@YAXPEAXPEBX@Z` at `0x18003311c`
- `msvcp_win!?__ExceptionPtrAssign@@YAXPEAXPEBX@Z` at `0x18003311c`

## pseudocode

```c
__int64 __fastcall p9fs::SendAsync__ResumeCoro_1_::_1_::catch_5(__int64 a1, __int64 a2)
{
  __int64 v2; // rbx

  v2 = *(_QWORD *)(a2 + 56);
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
0x1800330be  mov     [rsp+arg_8], rdx
0x1800330c3  push    rbx
0x1800330c4  push    rbp
0x1800330c5  sub     rsp, 38h
0x1800330c9  mov     rbp, rdx
0x1800330cc  or      eax, 0FFFFFFFFh
0x1800330cf  mov     rbx, [rbp+38h]
0x1800330d3  mov     [rbx+8], ax
0x1800330d7  xorps   xmm0, xmm0
0x1800330da  movups  xmmword ptr [rbx+98h], xmm0
0x1800330e1  mov     qword ptr [rbx+98h], 0
0x1800330ec  mov     qword ptr [rbx+0A0h], 0
0x1800330f7  lea     rcx, [rbx+98h]
0x1800330fe  call    cs:__imp_?__ExceptionPtrCreate@@YAXPEAX@Z; __ExceptionPtrCreate(void *)
0x180033104  lea     rcx, [rbx+98h]
0x18003310b  call    cs:__imp_?__ExceptionPtrCurrentException@@YAXPEAX@Z; __ExceptionPtrCurrentException(void *)
0x180033111  lea     rdx, [rbx+98h]
0x180033118  lea     rcx, [rbx-20h]
0x18003311c  call    cs:__imp_?__ExceptionPtrAssign@@YAXPEAXPEBX@Z; __ExceptionPtrAssign(void *,void const *)
0x180033122  lea     rcx, [rbx+98h]
0x180033129  call    cs:__imp_?__ExceptionPtrDestroy@@YAXPEAX@Z; __ExceptionPtrDestroy(void *)
0x18003312f  nop
0x180033130  mov     rax, 0
0x18003313a  add     rsp, 38h
0x18003313e  pop     rbp
0x18003313f  pop     rbx
0x180033140  retn
```
