# __lambda_14a7a5d5c2db807f1a68f78f3c68b6c0_$_ResumeCoro$1::operator()_::_1_::catch$17

- ea: `0x18002f646`
- end: `0x18002f6ca`
- name: `__lambda_14a7a5d5c2db807f1a68f78f3c68b6c0_$_ResumeCoro$1::operator()_::_1_::catch$17`
- size: `132`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: ``

## import_xrefs

- `msvcp_win!?__ExceptionPtrDestroy@@YAXPEAX@Z` at `0x18002f6b1`
- `msvcp_win!?__ExceptionPtrDestroy@@YAXPEAX@Z` at `0x18002f6b1`
- `msvcp_win!?__ExceptionPtrCurrentException@@YAXPEAX@Z` at `0x18002f693`
- `msvcp_win!?__ExceptionPtrCurrentException@@YAXPEAX@Z` at `0x18002f693`
- `msvcp_win!?__ExceptionPtrCreate@@YAXPEAX@Z` at `0x18002f686`
- `msvcp_win!?__ExceptionPtrCreate@@YAXPEAX@Z` at `0x18002f686`
- `msvcp_win!?__ExceptionPtrAssign@@YAXPEAXPEBX@Z` at `0x18002f6a4`
- `msvcp_win!?__ExceptionPtrAssign@@YAXPEAXPEBX@Z` at `0x18002f6a4`

## pseudocode

```c
__int64 __fastcall _lambda_14a7a5d5c2db807f1a68f78f3c68b6c0___ResumeCoro_1::operator()_::_1_::catch_17(
        __int64 a1,
        __int64 a2)
{
  __int64 v2; // rbx

  v2 = *(_QWORD *)(a2 + 48);
  *(_WORD *)(v2 + 8) = -1;
  *(_OWORD *)(v2 + 2560) = 0;
  *(_QWORD *)(v2 + 2560) = 0;
  *(_QWORD *)(v2 + 2568) = 0;
  __ExceptionPtrCreate((void *)(v2 + 2560));
  __ExceptionPtrCurrentException((void *)(v2 + 2560));
  __ExceptionPtrAssign((void *)(v2 - 16), (const void *)(v2 + 2560));
  __ExceptionPtrDestroy((void *)(v2 + 2560));
  return 0;
}

```

## disassembly

```asm
0x18002f646  mov     [rsp+arg_8], rdx
0x18002f64b  push    rbx
0x18002f64c  push    rbp
0x18002f64d  sub     rsp, 28h
0x18002f651  mov     rbp, rdx
0x18002f654  or      eax, 0FFFFFFFFh
0x18002f657  mov     rbx, [rbp+30h]
0x18002f65b  mov     [rbx+8], ax
0x18002f65f  xorps   xmm0, xmm0
0x18002f662  movups  xmmword ptr [rbx+0A00h], xmm0
0x18002f669  mov     qword ptr [rbx+0A00h], 0
0x18002f674  mov     qword ptr [rbx+0A08h], 0
0x18002f67f  lea     rcx, [rbx+0A00h]
0x18002f686  call    cs:__imp_?__ExceptionPtrCreate@@YAXPEAX@Z; __ExceptionPtrCreate(void *)
0x18002f68c  lea     rcx, [rbx+0A00h]
0x18002f693  call    cs:__imp_?__ExceptionPtrCurrentException@@YAXPEAX@Z; __ExceptionPtrCurrentException(void *)
0x18002f699  lea     rdx, [rbx+0A00h]
0x18002f6a0  lea     rcx, [rbx-10h]
0x18002f6a4  call    cs:__imp_?__ExceptionPtrAssign@@YAXPEAXPEBX@Z; __ExceptionPtrAssign(void *,void const *)
0x18002f6aa  lea     rcx, [rbx+0A00h]
0x18002f6b1  call    cs:__imp_?__ExceptionPtrDestroy@@YAXPEAX@Z; __ExceptionPtrDestroy(void *)
0x18002f6b7  nop
0x18002f6b8  mov     rax, 0
0x18002f6c2  add     rsp, 28h
0x18002f6c6  pop     rbp
0x18002f6c7  pop     rbx
0x18002f6c8  retn
```
