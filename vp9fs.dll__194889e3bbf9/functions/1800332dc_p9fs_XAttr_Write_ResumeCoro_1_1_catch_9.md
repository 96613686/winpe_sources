# _p9fs::XAttr::Write$_ResumeCoro$1_::_1_::catch$9

- ea: `0x1800332dc`
- end: `0x18003334b`
- name: `_p9fs::XAttr::Write$_ResumeCoro$1_::_1_::catch$9`
- size: `111`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: ``

## import_xrefs

- `msvcp_win!?__ExceptionPtrDestroy@@YAXPEAX@Z` at `0x180033332`
- `msvcp_win!?__ExceptionPtrDestroy@@YAXPEAX@Z` at `0x180033332`
- `msvcp_win!?__ExceptionPtrCurrentException@@YAXPEAX@Z` at `0x18003331a`
- `msvcp_win!?__ExceptionPtrCurrentException@@YAXPEAX@Z` at `0x18003331a`
- `msvcp_win!?__ExceptionPtrCreate@@YAXPEAX@Z` at `0x180033310`
- `msvcp_win!?__ExceptionPtrCreate@@YAXPEAX@Z` at `0x180033310`
- `msvcp_win!?__ExceptionPtrAssign@@YAXPEAXPEBX@Z` at `0x180033328`
- `msvcp_win!?__ExceptionPtrAssign@@YAXPEAXPEBX@Z` at `0x180033328`

## pseudocode

```c
__int64 __fastcall p9fs::XAttr::Write__ResumeCoro_1_::_1_::catch_9(__int64 a1, __int64 a2)
{
  __int64 v2; // rbx

  v2 = *(_QWORD *)(a2 + 40);
  *(_WORD *)(v2 + 8) = -1;
  *(_OWORD *)(v2 + 48) = 0;
  *(_QWORD *)(v2 + 48) = 0;
  *(_QWORD *)(v2 + 56) = 0;
  __ExceptionPtrCreate((void *)(v2 + 48));
  __ExceptionPtrCurrentException((void *)(v2 + 48));
  __ExceptionPtrAssign((void *)(v2 - 32), (const void *)(v2 + 48));
  __ExceptionPtrDestroy((void *)(v2 + 48));
  return 0;
}

```

## disassembly

```asm
0x1800332dc  mov     [rsp+arg_8], rdx
0x1800332e1  push    rbx
0x1800332e2  push    rbp
0x1800332e3  sub     rsp, 28h
0x1800332e7  mov     rbp, rdx
0x1800332ea  or      eax, 0FFFFFFFFh
0x1800332ed  mov     rbx, [rbp+28h]
0x1800332f1  mov     [rbx+8], ax
0x1800332f5  xorps   xmm0, xmm0
0x1800332f8  movups  xmmword ptr [rbx+30h], xmm0
0x1800332fc  mov     qword ptr [rbx+30h], 0
0x180033304  mov     qword ptr [rbx+38h], 0
0x18003330c  lea     rcx, [rbx+30h]
0x180033310  call    cs:__imp_?__ExceptionPtrCreate@@YAXPEAX@Z; __ExceptionPtrCreate(void *)
0x180033316  lea     rcx, [rbx+30h]
0x18003331a  call    cs:__imp_?__ExceptionPtrCurrentException@@YAXPEAX@Z; __ExceptionPtrCurrentException(void *)
0x180033320  lea     rdx, [rbx+30h]
0x180033324  lea     rcx, [rbx-20h]
0x180033328  call    cs:__imp_?__ExceptionPtrAssign@@YAXPEAXPEBX@Z; __ExceptionPtrAssign(void *,void const *)
0x18003332e  lea     rcx, [rbx+30h]
0x180033332  call    cs:__imp_?__ExceptionPtrDestroy@@YAXPEAX@Z; __ExceptionPtrDestroy(void *)
0x180033338  nop
0x180033339  mov     rax, 0
0x180033343  add     rsp, 28h
0x180033347  pop     rbp
0x180033348  pop     rbx
0x180033349  retn
```
