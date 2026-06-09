# _p9fs::Handler::ProcessMessage$_ResumeCoro$1_::_1_::catch$15

- ea: `0x180031499`
- end: `0x18003151d`
- name: `_p9fs::Handler::ProcessMessage$_ResumeCoro$1_::_1_::catch$15`
- size: `132`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `loader_planting`

## import_xrefs

- `msvcp_win!?__ExceptionPtrDestroy@@YAXPEAX@Z` at `0x180031504`
- `msvcp_win!?__ExceptionPtrDestroy@@YAXPEAX@Z` at `0x180031504`
- `msvcp_win!?__ExceptionPtrCurrentException@@YAXPEAX@Z` at `0x1800314e6`
- `msvcp_win!?__ExceptionPtrCurrentException@@YAXPEAX@Z` at `0x1800314e6`
- `msvcp_win!?__ExceptionPtrCreate@@YAXPEAX@Z` at `0x1800314d9`
- `msvcp_win!?__ExceptionPtrCreate@@YAXPEAX@Z` at `0x1800314d9`
- `msvcp_win!?__ExceptionPtrAssign@@YAXPEAXPEBX@Z` at `0x1800314f7`
- `msvcp_win!?__ExceptionPtrAssign@@YAXPEAXPEBX@Z` at `0x1800314f7`

## pseudocode

```c
__int64 __fastcall p9fs::Handler::ProcessMessage__ResumeCoro_1_::_1_::catch_15(__int64 a1, __int64 a2)
{
  __int64 v2; // rbx

  v2 = *(_QWORD *)(a2 + 56);
  *(_WORD *)(v2 + 8) = -1;
  *(_OWORD *)(v2 + 1136) = 0;
  *(_QWORD *)(v2 + 1136) = 0;
  *(_QWORD *)(v2 + 1144) = 0;
  __ExceptionPtrCreate((void *)(v2 + 1136));
  __ExceptionPtrCurrentException((void *)(v2 + 1136));
  __ExceptionPtrAssign((void *)(v2 - 16), (const void *)(v2 + 1136));
  __ExceptionPtrDestroy((void *)(v2 + 1136));
  return 0;
}

```

## disassembly

```asm
0x180031499  mov     [rsp+arg_8], rdx
0x18003149e  push    rbx
0x18003149f  push    rbp
0x1800314a0  sub     rsp, 28h
0x1800314a4  mov     rbp, rdx
0x1800314a7  or      eax, 0FFFFFFFFh
0x1800314aa  mov     rbx, [rbp+38h]
0x1800314ae  mov     [rbx+8], ax
0x1800314b2  xorps   xmm0, xmm0
0x1800314b5  movups  xmmword ptr [rbx+470h], xmm0
0x1800314bc  mov     qword ptr [rbx+470h], 0
0x1800314c7  mov     qword ptr [rbx+478h], 0
0x1800314d2  lea     rcx, [rbx+470h]
0x1800314d9  call    cs:__imp_?__ExceptionPtrCreate@@YAXPEAX@Z; __ExceptionPtrCreate(void *)
0x1800314df  lea     rcx, [rbx+470h]
0x1800314e6  call    cs:__imp_?__ExceptionPtrCurrentException@@YAXPEAX@Z; __ExceptionPtrCurrentException(void *)
0x1800314ec  lea     rdx, [rbx+470h]
0x1800314f3  lea     rcx, [rbx-10h]
0x1800314f7  call    cs:__imp_?__ExceptionPtrAssign@@YAXPEAXPEBX@Z; __ExceptionPtrAssign(void *,void const *)
0x1800314fd  lea     rcx, [rbx+470h]
0x180031504  call    cs:__imp_?__ExceptionPtrDestroy@@YAXPEAX@Z; __ExceptionPtrDestroy(void *)
0x18003150a  nop
0x18003150b  mov     rax, 0
0x180031515  add     rsp, 28h
0x180031519  pop     rbp
0x18003151a  pop     rbx
0x18003151b  retn
```
