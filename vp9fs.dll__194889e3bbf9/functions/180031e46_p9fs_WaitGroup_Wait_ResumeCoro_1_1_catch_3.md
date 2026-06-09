# _p9fs::WaitGroup::Wait$_ResumeCoro$1_::_1_::catch$3

- ea: `0x180031e46`
- end: `0x180031eb5`
- name: `_p9fs::WaitGroup::Wait$_ResumeCoro$1_::_1_::catch$3`
- size: `111`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: ``

## import_xrefs

- `msvcp_win!?__ExceptionPtrDestroy@@YAXPEAX@Z` at `0x180031e9c`
- `msvcp_win!?__ExceptionPtrDestroy@@YAXPEAX@Z` at `0x180031e9c`
- `msvcp_win!?__ExceptionPtrCurrentException@@YAXPEAX@Z` at `0x180031e84`
- `msvcp_win!?__ExceptionPtrCurrentException@@YAXPEAX@Z` at `0x180031e84`
- `msvcp_win!?__ExceptionPtrCreate@@YAXPEAX@Z` at `0x180031e7a`
- `msvcp_win!?__ExceptionPtrCreate@@YAXPEAX@Z` at `0x180031e7a`
- `msvcp_win!?__ExceptionPtrAssign@@YAXPEAXPEBX@Z` at `0x180031e92`
- `msvcp_win!?__ExceptionPtrAssign@@YAXPEAXPEBX@Z` at `0x180031e92`

## pseudocode

```c
__int64 __fastcall p9fs::WaitGroup::Wait__ResumeCoro_1_::_1_::catch_3(__int64 a1, __int64 a2)
{
  __int64 v2; // rbx

  v2 = *(_QWORD *)(a2 + 40);
  *(_WORD *)(v2 + 8) = -1;
  *(_OWORD *)(v2 + 48) = 0;
  *(_QWORD *)(v2 + 48) = 0;
  *(_QWORD *)(v2 + 56) = 0;
  __ExceptionPtrCreate((void *)(v2 + 48));
  __ExceptionPtrCurrentException((void *)(v2 + 48));
  __ExceptionPtrAssign((void *)(v2 - 16), (const void *)(v2 + 48));
  __ExceptionPtrDestroy((void *)(v2 + 48));
  return 0;
}

```

## disassembly

```asm
0x180031e46  mov     [rsp+arg_8], rdx
0x180031e4b  push    rbx
0x180031e4c  push    rbp
0x180031e4d  sub     rsp, 28h
0x180031e51  mov     rbp, rdx
0x180031e54  or      eax, 0FFFFFFFFh
0x180031e57  mov     rbx, [rbp+28h]
0x180031e5b  mov     [rbx+8], ax
0x180031e5f  xorps   xmm0, xmm0
0x180031e62  movups  xmmword ptr [rbx+30h], xmm0
0x180031e66  mov     qword ptr [rbx+30h], 0
0x180031e6e  mov     qword ptr [rbx+38h], 0
0x180031e76  lea     rcx, [rbx+30h]
0x180031e7a  call    cs:__imp_?__ExceptionPtrCreate@@YAXPEAX@Z; __ExceptionPtrCreate(void *)
0x180031e80  lea     rcx, [rbx+30h]
0x180031e84  call    cs:__imp_?__ExceptionPtrCurrentException@@YAXPEAX@Z; __ExceptionPtrCurrentException(void *)
0x180031e8a  lea     rdx, [rbx+30h]
0x180031e8e  lea     rcx, [rbx-10h]
0x180031e92  call    cs:__imp_?__ExceptionPtrAssign@@YAXPEAXPEBX@Z; __ExceptionPtrAssign(void *,void const *)
0x180031e98  lea     rcx, [rbx+30h]
0x180031e9c  call    cs:__imp_?__ExceptionPtrDestroy@@YAXPEAX@Z; __ExceptionPtrDestroy(void *)
0x180031ea2  nop
0x180031ea3  mov     rax, 0
0x180031ead  add     rsp, 28h
0x180031eb1  pop     rbp
0x180031eb2  pop     rbx
0x180031eb3  retn
```
