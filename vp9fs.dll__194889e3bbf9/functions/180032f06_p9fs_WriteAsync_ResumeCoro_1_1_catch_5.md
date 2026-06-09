# _p9fs::WriteAsync$_ResumeCoro$1_::_1_::catch$5

- ea: `0x180032f06`
- end: `0x180032f8a`
- name: `_p9fs::WriteAsync$_ResumeCoro$1_::_1_::catch$5`
- size: `132`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: ``

## import_xrefs

- `msvcp_win!?__ExceptionPtrDestroy@@YAXPEAX@Z` at `0x180032f71`
- `msvcp_win!?__ExceptionPtrDestroy@@YAXPEAX@Z` at `0x180032f71`
- `msvcp_win!?__ExceptionPtrCurrentException@@YAXPEAX@Z` at `0x180032f53`
- `msvcp_win!?__ExceptionPtrCurrentException@@YAXPEAX@Z` at `0x180032f53`
- `msvcp_win!?__ExceptionPtrCreate@@YAXPEAX@Z` at `0x180032f46`
- `msvcp_win!?__ExceptionPtrCreate@@YAXPEAX@Z` at `0x180032f46`
- `msvcp_win!?__ExceptionPtrAssign@@YAXPEAXPEBX@Z` at `0x180032f64`
- `msvcp_win!?__ExceptionPtrAssign@@YAXPEAXPEBX@Z` at `0x180032f64`

## pseudocode

```c
__int64 __fastcall p9fs::WriteAsync__ResumeCoro_1_::_1_::catch_5(__int64 a1, __int64 a2)
{
  __int64 v2; // rbx

  v2 = *(_QWORD *)(a2 + 56);
  *(_WORD *)(v2 + 8) = -1;
  *(_OWORD *)(v2 + 144) = 0;
  *(_QWORD *)(v2 + 144) = 0;
  *(_QWORD *)(v2 + 152) = 0;
  __ExceptionPtrCreate((void *)(v2 + 144));
  __ExceptionPtrCurrentException((void *)(v2 + 144));
  __ExceptionPtrAssign((void *)(v2 - 32), (const void *)(v2 + 144));
  __ExceptionPtrDestroy((void *)(v2 + 144));
  return 0;
}

```

## disassembly

```asm
0x180032f06  mov     [rsp+arg_8], rdx
0x180032f0b  push    rbx
0x180032f0c  push    rbp
0x180032f0d  sub     rsp, 38h
0x180032f11  mov     rbp, rdx
0x180032f14  or      eax, 0FFFFFFFFh
0x180032f17  mov     rbx, [rbp+38h]
0x180032f1b  mov     [rbx+8], ax
0x180032f1f  xorps   xmm0, xmm0
0x180032f22  movups  xmmword ptr [rbx+90h], xmm0
0x180032f29  mov     qword ptr [rbx+90h], 0
0x180032f34  mov     qword ptr [rbx+98h], 0
0x180032f3f  lea     rcx, [rbx+90h]
0x180032f46  call    cs:__imp_?__ExceptionPtrCreate@@YAXPEAX@Z; __ExceptionPtrCreate(void *)
0x180032f4c  lea     rcx, [rbx+90h]
0x180032f53  call    cs:__imp_?__ExceptionPtrCurrentException@@YAXPEAX@Z; __ExceptionPtrCurrentException(void *)
0x180032f59  lea     rdx, [rbx+90h]
0x180032f60  lea     rcx, [rbx-20h]
0x180032f64  call    cs:__imp_?__ExceptionPtrAssign@@YAXPEAXPEBX@Z; __ExceptionPtrAssign(void *,void const *)
0x180032f6a  lea     rcx, [rbx+90h]
0x180032f71  call    cs:__imp_?__ExceptionPtrDestroy@@YAXPEAX@Z; __ExceptionPtrDestroy(void *)
0x180032f77  nop
0x180032f78  mov     rax, 0
0x180032f82  add     rsp, 38h
0x180032f86  pop     rbp
0x180032f87  pop     rbx
0x180032f88  retn
```
