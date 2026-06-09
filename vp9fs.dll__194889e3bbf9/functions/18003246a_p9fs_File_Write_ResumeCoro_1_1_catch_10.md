# _p9fs::File::Write$_ResumeCoro$1_::_1_::catch$10

- ea: `0x18003246a`
- end: `0x1800324ee`
- name: `_p9fs::File::Write$_ResumeCoro$1_::_1_::catch$10`
- size: `132`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: ``

## import_xrefs

- `msvcp_win!?__ExceptionPtrDestroy@@YAXPEAX@Z` at `0x1800324d5`
- `msvcp_win!?__ExceptionPtrDestroy@@YAXPEAX@Z` at `0x1800324d5`
- `msvcp_win!?__ExceptionPtrCurrentException@@YAXPEAX@Z` at `0x1800324b7`
- `msvcp_win!?__ExceptionPtrCurrentException@@YAXPEAX@Z` at `0x1800324b7`
- `msvcp_win!?__ExceptionPtrCreate@@YAXPEAX@Z` at `0x1800324aa`
- `msvcp_win!?__ExceptionPtrCreate@@YAXPEAX@Z` at `0x1800324aa`
- `msvcp_win!?__ExceptionPtrAssign@@YAXPEAXPEBX@Z` at `0x1800324c8`
- `msvcp_win!?__ExceptionPtrAssign@@YAXPEAXPEBX@Z` at `0x1800324c8`

## pseudocode

```c
__int64 __fastcall p9fs::File::Write__ResumeCoro_1_::_1_::catch_10(__int64 a1, __int64 a2)
{
  __int64 v2; // rbx

  v2 = *(_QWORD *)(a2 + 64);
  *(_WORD *)(v2 + 8) = -1;
  *(_OWORD *)(v2 + 328) = 0;
  *(_QWORD *)(v2 + 328) = 0;
  *(_QWORD *)(v2 + 336) = 0;
  __ExceptionPtrCreate((void *)(v2 + 328));
  __ExceptionPtrCurrentException((void *)(v2 + 328));
  __ExceptionPtrAssign((void *)(v2 - 32), (const void *)(v2 + 328));
  __ExceptionPtrDestroy((void *)(v2 + 328));
  return 0;
}

```

## disassembly

```asm
0x18003246a  mov     [rsp+arg_8], rdx
0x18003246f  push    rbx
0x180032470  push    rbp
0x180032471  sub     rsp, 38h
0x180032475  mov     rbp, rdx
0x180032478  or      eax, 0FFFFFFFFh
0x18003247b  mov     rbx, [rbp+40h]
0x18003247f  mov     [rbx+8], ax
0x180032483  xorps   xmm0, xmm0
0x180032486  movups  xmmword ptr [rbx+148h], xmm0
0x18003248d  mov     qword ptr [rbx+148h], 0
0x180032498  mov     qword ptr [rbx+150h], 0
0x1800324a3  lea     rcx, [rbx+148h]
0x1800324aa  call    cs:__imp_?__ExceptionPtrCreate@@YAXPEAX@Z; __ExceptionPtrCreate(void *)
0x1800324b0  lea     rcx, [rbx+148h]
0x1800324b7  call    cs:__imp_?__ExceptionPtrCurrentException@@YAXPEAX@Z; __ExceptionPtrCurrentException(void *)
0x1800324bd  lea     rdx, [rbx+148h]
0x1800324c4  lea     rcx, [rbx-20h]
0x1800324c8  call    cs:__imp_?__ExceptionPtrAssign@@YAXPEAXPEBX@Z; __ExceptionPtrAssign(void *,void const *)
0x1800324ce  lea     rcx, [rbx+148h]
0x1800324d5  call    cs:__imp_?__ExceptionPtrDestroy@@YAXPEAX@Z; __ExceptionPtrDestroy(void *)
0x1800324db  nop
0x1800324dc  mov     rax, 0
0x1800324e6  add     rsp, 38h
0x1800324ea  pop     rbp
0x1800324eb  pop     rbx
0x1800324ec  retn
```
