# __lambda_3d5f3bee0032f150f7b5c906833347cc_$_ResumeCoro$1::operator()_::_1_::catch$14

- ea: `0x18002fd3a`
- end: `0x18002fdbe`
- name: `__lambda_3d5f3bee0032f150f7b5c906833347cc_$_ResumeCoro$1::operator()_::_1_::catch$14`
- size: `132`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: ``

## import_xrefs

- `msvcp_win!?__ExceptionPtrDestroy@@YAXPEAX@Z` at `0x18002fda5`
- `msvcp_win!?__ExceptionPtrDestroy@@YAXPEAX@Z` at `0x18002fda5`
- `msvcp_win!?__ExceptionPtrCurrentException@@YAXPEAX@Z` at `0x18002fd87`
- `msvcp_win!?__ExceptionPtrCurrentException@@YAXPEAX@Z` at `0x18002fd87`
- `msvcp_win!?__ExceptionPtrCreate@@YAXPEAX@Z` at `0x18002fd7a`
- `msvcp_win!?__ExceptionPtrCreate@@YAXPEAX@Z` at `0x18002fd7a`
- `msvcp_win!?__ExceptionPtrAssign@@YAXPEAXPEBX@Z` at `0x18002fd98`
- `msvcp_win!?__ExceptionPtrAssign@@YAXPEAXPEBX@Z` at `0x18002fd98`

## pseudocode

```c
__int64 __fastcall _lambda_3d5f3bee0032f150f7b5c906833347cc___ResumeCoro_1::operator()_::_1_::catch_14(
        __int64 a1,
        __int64 a2)
{
  __int64 v2; // rbx

  v2 = *(_QWORD *)(a2 + 32);
  *(_WORD *)(v2 + 8) = -1;
  *(_OWORD *)(v2 + 136) = 0;
  *(_QWORD *)(v2 + 136) = 0;
  *(_QWORD *)(v2 + 144) = 0;
  __ExceptionPtrCreate((void *)(v2 + 136));
  __ExceptionPtrCurrentException((void *)(v2 + 136));
  __ExceptionPtrAssign((void *)(v2 - 16), (const void *)(v2 + 136));
  __ExceptionPtrDestroy((void *)(v2 + 136));
  return 0;
}

```

## disassembly

```asm
0x18002fd3a  mov     [rsp+arg_8], rdx
0x18002fd3f  push    rbx
0x18002fd40  push    rbp
0x18002fd41  sub     rsp, 28h
0x18002fd45  mov     rbp, rdx
0x18002fd48  or      eax, 0FFFFFFFFh
0x18002fd4b  mov     rbx, [rbp+20h]
0x18002fd4f  mov     [rbx+8], ax
0x18002fd53  xorps   xmm0, xmm0
0x18002fd56  movups  xmmword ptr [rbx+88h], xmm0
0x18002fd5d  mov     qword ptr [rbx+88h], 0
0x18002fd68  mov     qword ptr [rbx+90h], 0
0x18002fd73  lea     rcx, [rbx+88h]
0x18002fd7a  call    cs:__imp_?__ExceptionPtrCreate@@YAXPEAX@Z; __ExceptionPtrCreate(void *)
0x18002fd80  lea     rcx, [rbx+88h]
0x18002fd87  call    cs:__imp_?__ExceptionPtrCurrentException@@YAXPEAX@Z; __ExceptionPtrCurrentException(void *)
0x18002fd8d  lea     rdx, [rbx+88h]
0x18002fd94  lea     rcx, [rbx-10h]
0x18002fd98  call    cs:__imp_?__ExceptionPtrAssign@@YAXPEAXPEBX@Z; __ExceptionPtrAssign(void *,void const *)
0x18002fd9e  lea     rcx, [rbx+88h]
0x18002fda5  call    cs:__imp_?__ExceptionPtrDestroy@@YAXPEAX@Z; __ExceptionPtrDestroy(void *)
0x18002fdab  nop
0x18002fdac  mov     rax, 0
0x18002fdb6  add     rsp, 28h
0x18002fdba  pop     rbp
0x18002fdbb  pop     rbx
0x18002fdbc  retn
```
