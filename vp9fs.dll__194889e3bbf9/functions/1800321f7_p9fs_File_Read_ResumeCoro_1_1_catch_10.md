# _p9fs::File::Read$_ResumeCoro$1_::_1_::catch$10

- ea: `0x1800321f7`
- end: `0x18003227b`
- name: `_p9fs::File::Read$_ResumeCoro$1_::_1_::catch$10`
- size: `132`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: ``

## import_xrefs

- `msvcp_win!?__ExceptionPtrDestroy@@YAXPEAX@Z` at `0x180032262`
- `msvcp_win!?__ExceptionPtrDestroy@@YAXPEAX@Z` at `0x180032262`
- `msvcp_win!?__ExceptionPtrCurrentException@@YAXPEAX@Z` at `0x180032244`
- `msvcp_win!?__ExceptionPtrCurrentException@@YAXPEAX@Z` at `0x180032244`
- `msvcp_win!?__ExceptionPtrCreate@@YAXPEAX@Z` at `0x180032237`
- `msvcp_win!?__ExceptionPtrCreate@@YAXPEAX@Z` at `0x180032237`
- `msvcp_win!?__ExceptionPtrAssign@@YAXPEAXPEBX@Z` at `0x180032255`
- `msvcp_win!?__ExceptionPtrAssign@@YAXPEAXPEBX@Z` at `0x180032255`

## pseudocode

```c
__int64 __fastcall p9fs::File::Read__ResumeCoro_1_::_1_::catch_10(__int64 a1, __int64 a2)
{
  __int64 v2; // rbx

  v2 = *(_QWORD *)(a2 + 64);
  *(_WORD *)(v2 + 8) = -1;
  *(_OWORD *)(v2 + 224) = 0;
  *(_QWORD *)(v2 + 224) = 0;
  *(_QWORD *)(v2 + 232) = 0;
  __ExceptionPtrCreate((void *)(v2 + 224));
  __ExceptionPtrCurrentException((void *)(v2 + 224));
  __ExceptionPtrAssign((void *)(v2 - 32), (const void *)(v2 + 224));
  __ExceptionPtrDestroy((void *)(v2 + 224));
  return 0;
}

```

## disassembly

```asm
0x1800321f7  mov     [rsp+arg_8], rdx
0x1800321fc  push    rbx
0x1800321fd  push    rbp
0x1800321fe  sub     rsp, 38h
0x180032202  mov     rbp, rdx
0x180032205  or      eax, 0FFFFFFFFh
0x180032208  mov     rbx, [rbp+40h]
0x18003220c  mov     [rbx+8], ax
0x180032210  xorps   xmm0, xmm0
0x180032213  movups  xmmword ptr [rbx+0E0h], xmm0
0x18003221a  mov     qword ptr [rbx+0E0h], 0
0x180032225  mov     qword ptr [rbx+0E8h], 0
0x180032230  lea     rcx, [rbx+0E0h]
0x180032237  call    cs:__imp_?__ExceptionPtrCreate@@YAXPEAX@Z; __ExceptionPtrCreate(void *)
0x18003223d  lea     rcx, [rbx+0E0h]
0x180032244  call    cs:__imp_?__ExceptionPtrCurrentException@@YAXPEAX@Z; __ExceptionPtrCurrentException(void *)
0x18003224a  lea     rdx, [rbx+0E0h]
0x180032251  lea     rcx, [rbx-20h]
0x180032255  call    cs:__imp_?__ExceptionPtrAssign@@YAXPEAXPEBX@Z; __ExceptionPtrAssign(void *,void const *)
0x18003225b  lea     rcx, [rbx+0E0h]
0x180032262  call    cs:__imp_?__ExceptionPtrDestroy@@YAXPEAX@Z; __ExceptionPtrDestroy(void *)
0x180032268  nop
0x180032269  mov     rax, 0
0x180032273  add     rsp, 38h
0x180032277  pop     rbp
0x180032278  pop     rbx
0x180032279  retn
```
