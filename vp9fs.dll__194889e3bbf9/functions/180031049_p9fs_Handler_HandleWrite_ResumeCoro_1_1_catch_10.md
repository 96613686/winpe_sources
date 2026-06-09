# _p9fs::Handler::HandleWrite$_ResumeCoro$1_::_1_::catch$10

- ea: `0x180031049`
- end: `0x1800310b8`
- name: `_p9fs::Handler::HandleWrite$_ResumeCoro$1_::_1_::catch$10`
- size: `111`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `loader_planting`

## import_xrefs

- `msvcp_win!?__ExceptionPtrDestroy@@YAXPEAX@Z` at `0x18003109f`
- `msvcp_win!?__ExceptionPtrDestroy@@YAXPEAX@Z` at `0x18003109f`
- `msvcp_win!?__ExceptionPtrCurrentException@@YAXPEAX@Z` at `0x180031087`
- `msvcp_win!?__ExceptionPtrCurrentException@@YAXPEAX@Z` at `0x180031087`
- `msvcp_win!?__ExceptionPtrCreate@@YAXPEAX@Z` at `0x18003107d`
- `msvcp_win!?__ExceptionPtrCreate@@YAXPEAX@Z` at `0x18003107d`
- `msvcp_win!?__ExceptionPtrAssign@@YAXPEAXPEBX@Z` at `0x180031095`
- `msvcp_win!?__ExceptionPtrAssign@@YAXPEAXPEBX@Z` at `0x180031095`

## pseudocode

```c
__int64 __fastcall p9fs::Handler::HandleWrite__ResumeCoro_1_::_1_::catch_10(__int64 a1, __int64 a2)
{
  __int64 v2; // rbx

  v2 = *(_QWORD *)(a2 + 64);
  *(_WORD *)(v2 + 8) = -1;
  *(_OWORD *)(v2 + 80) = 0;
  *(_QWORD *)(v2 + 80) = 0;
  *(_QWORD *)(v2 + 88) = 0;
  __ExceptionPtrCreate((void *)(v2 + 80));
  __ExceptionPtrCurrentException((void *)(v2 + 80));
  __ExceptionPtrAssign((void *)(v2 - 32), (const void *)(v2 + 80));
  __ExceptionPtrDestroy((void *)(v2 + 80));
  return 0;
}

```

## disassembly

```asm
0x180031049  mov     [rsp+arg_8], rdx
0x18003104e  push    rbx
0x18003104f  push    rbp
0x180031050  sub     rsp, 38h
0x180031054  mov     rbp, rdx
0x180031057  or      eax, 0FFFFFFFFh
0x18003105a  mov     rbx, [rbp+40h]
0x18003105e  mov     [rbx+8], ax
0x180031062  xorps   xmm0, xmm0
0x180031065  movups  xmmword ptr [rbx+50h], xmm0
0x180031069  mov     qword ptr [rbx+50h], 0
0x180031071  mov     qword ptr [rbx+58h], 0
0x180031079  lea     rcx, [rbx+50h]
0x18003107d  call    cs:__imp_?__ExceptionPtrCreate@@YAXPEAX@Z; __ExceptionPtrCreate(void *)
0x180031083  lea     rcx, [rbx+50h]
0x180031087  call    cs:__imp_?__ExceptionPtrCurrentException@@YAXPEAX@Z; __ExceptionPtrCurrentException(void *)
0x18003108d  lea     rdx, [rbx+50h]
0x180031091  lea     rcx, [rbx-20h]
0x180031095  call    cs:__imp_?__ExceptionPtrAssign@@YAXPEAXPEBX@Z; __ExceptionPtrAssign(void *,void const *)
0x18003109b  lea     rcx, [rbx+50h]
0x18003109f  call    cs:__imp_?__ExceptionPtrDestroy@@YAXPEAX@Z; __ExceptionPtrDestroy(void *)
0x1800310a5  nop
0x1800310a6  mov     rax, 0
0x1800310b0  add     rsp, 38h
0x1800310b4  pop     rbp
0x1800310b5  pop     rbx
0x1800310b6  retn
```
