# _p9fs::Handler::HandleMessage$_ResumeCoro$1_::_1_::catch$42

- ea: `0x180030f57`
- end: `0x180030fdb`
- name: `_p9fs::Handler::HandleMessage$_ResumeCoro$1_::_1_::catch$42`
- size: `132`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `loader_planting`

## import_xrefs

- `msvcp_win!?__ExceptionPtrDestroy@@YAXPEAX@Z` at `0x180030fc2`
- `msvcp_win!?__ExceptionPtrDestroy@@YAXPEAX@Z` at `0x180030fc2`
- `msvcp_win!?__ExceptionPtrCurrentException@@YAXPEAX@Z` at `0x180030fa4`
- `msvcp_win!?__ExceptionPtrCurrentException@@YAXPEAX@Z` at `0x180030fa4`
- `msvcp_win!?__ExceptionPtrCreate@@YAXPEAX@Z` at `0x180030f97`
- `msvcp_win!?__ExceptionPtrCreate@@YAXPEAX@Z` at `0x180030f97`
- `msvcp_win!?__ExceptionPtrAssign@@YAXPEAXPEBX@Z` at `0x180030fb5`
- `msvcp_win!?__ExceptionPtrAssign@@YAXPEAXPEBX@Z` at `0x180030fb5`

## pseudocode

```c
__int64 __fastcall p9fs::Handler::HandleMessage__ResumeCoro_1_::_1_::catch_42(__int64 a1, __int64 a2)
{
  __int64 v2; // rbx

  v2 = *(_QWORD *)(a2 + 56);
  *(_WORD *)(v2 + 8) = -1;
  *(_OWORD *)(v2 + 848) = 0;
  *(_QWORD *)(v2 + 848) = 0;
  *(_QWORD *)(v2 + 856) = 0;
  __ExceptionPtrCreate((void *)(v2 + 848));
  __ExceptionPtrCurrentException((void *)(v2 + 848));
  __ExceptionPtrAssign((void *)(v2 - 32), (const void *)(v2 + 848));
  __ExceptionPtrDestroy((void *)(v2 + 848));
  return 0;
}

```

## disassembly

```asm
0x180030f57  mov     [rsp+arg_8], rdx
0x180030f5c  push    rbx
0x180030f5d  push    rbp
0x180030f5e  sub     rsp, 28h
0x180030f62  mov     rbp, rdx
0x180030f65  or      eax, 0FFFFFFFFh
0x180030f68  mov     rbx, [rbp+38h]
0x180030f6c  mov     [rbx+8], ax
0x180030f70  xorps   xmm0, xmm0
0x180030f73  movups  xmmword ptr [rbx+350h], xmm0
0x180030f7a  mov     qword ptr [rbx+350h], 0
0x180030f85  mov     qword ptr [rbx+358h], 0
0x180030f90  lea     rcx, [rbx+350h]
0x180030f97  call    cs:__imp_?__ExceptionPtrCreate@@YAXPEAX@Z; __ExceptionPtrCreate(void *)
0x180030f9d  lea     rcx, [rbx+350h]
0x180030fa4  call    cs:__imp_?__ExceptionPtrCurrentException@@YAXPEAX@Z; __ExceptionPtrCurrentException(void *)
0x180030faa  lea     rdx, [rbx+350h]
0x180030fb1  lea     rcx, [rbx-20h]
0x180030fb5  call    cs:__imp_?__ExceptionPtrAssign@@YAXPEAXPEBX@Z; __ExceptionPtrAssign(void *,void const *)
0x180030fbb  lea     rcx, [rbx+350h]
0x180030fc2  call    cs:__imp_?__ExceptionPtrDestroy@@YAXPEAX@Z; __ExceptionPtrDestroy(void *)
0x180030fc8  nop
0x180030fc9  mov     rax, 0
0x180030fd3  add     rsp, 28h
0x180030fd7  pop     rbp
0x180030fd8  pop     rbx
0x180030fd9  retn
```
