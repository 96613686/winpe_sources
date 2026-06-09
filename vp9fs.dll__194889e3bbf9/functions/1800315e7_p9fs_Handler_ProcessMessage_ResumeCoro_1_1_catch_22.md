# _p9fs::Handler::ProcessMessage$_ResumeCoro$1_::_1_::catch$22

- ea: `0x1800315e7`
- end: `0x18003166b`
- name: `_p9fs::Handler::ProcessMessage$_ResumeCoro$1_::_1_::catch$22`
- size: `132`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `loader_planting`

## import_xrefs

- `msvcp_win!?__ExceptionPtrDestroy@@YAXPEAX@Z` at `0x180031652`
- `msvcp_win!?__ExceptionPtrDestroy@@YAXPEAX@Z` at `0x180031652`
- `msvcp_win!?__ExceptionPtrCurrentException@@YAXPEAX@Z` at `0x180031634`
- `msvcp_win!?__ExceptionPtrCurrentException@@YAXPEAX@Z` at `0x180031634`
- `msvcp_win!?__ExceptionPtrCreate@@YAXPEAX@Z` at `0x180031627`
- `msvcp_win!?__ExceptionPtrCreate@@YAXPEAX@Z` at `0x180031627`
- `msvcp_win!?__ExceptionPtrAssign@@YAXPEAXPEBX@Z` at `0x180031645`
- `msvcp_win!?__ExceptionPtrAssign@@YAXPEAXPEBX@Z` at `0x180031645`

## pseudocode

```c
__int64 __fastcall p9fs::Handler::ProcessMessage__ResumeCoro_1_::_1_::catch_22(__int64 a1, __int64 a2)
{
  __int64 v2; // rbx

  v2 = *(_QWORD *)(a2 + 72);
  *(_WORD *)(v2 + 8) = -1;
  *(_OWORD *)(v2 + 496) = 0;
  *(_QWORD *)(v2 + 496) = 0;
  *(_QWORD *)(v2 + 504) = 0;
  __ExceptionPtrCreate((void *)(v2 + 496));
  __ExceptionPtrCurrentException((void *)(v2 + 496));
  __ExceptionPtrAssign((void *)(v2 - 16), (const void *)(v2 + 496));
  __ExceptionPtrDestroy((void *)(v2 + 496));
  return 0;
}

```

## disassembly

```asm
0x1800315e7  mov     [rsp+arg_8], rdx
0x1800315ec  push    rbx
0x1800315ed  push    rbp
0x1800315ee  sub     rsp, 38h
0x1800315f2  mov     rbp, rdx
0x1800315f5  or      eax, 0FFFFFFFFh
0x1800315f8  mov     rbx, [rbp+48h]
0x1800315fc  mov     [rbx+8], ax
0x180031600  xorps   xmm0, xmm0
0x180031603  movups  xmmword ptr [rbx+1F0h], xmm0
0x18003160a  mov     qword ptr [rbx+1F0h], 0
0x180031615  mov     qword ptr [rbx+1F8h], 0
0x180031620  lea     rcx, [rbx+1F0h]
0x180031627  call    cs:__imp_?__ExceptionPtrCreate@@YAXPEAX@Z; __ExceptionPtrCreate(void *)
0x18003162d  lea     rcx, [rbx+1F0h]
0x180031634  call    cs:__imp_?__ExceptionPtrCurrentException@@YAXPEAX@Z; __ExceptionPtrCurrentException(void *)
0x18003163a  lea     rdx, [rbx+1F0h]
0x180031641  lea     rcx, [rbx-10h]
0x180031645  call    cs:__imp_?__ExceptionPtrAssign@@YAXPEAXPEBX@Z; __ExceptionPtrAssign(void *,void const *)
0x18003164b  lea     rcx, [rbx+1F0h]
0x180031652  call    cs:__imp_?__ExceptionPtrDestroy@@YAXPEAX@Z; __ExceptionPtrDestroy(void *)
0x180031658  nop
0x180031659  mov     rax, 0
0x180031663  add     rsp, 38h
0x180031667  pop     rbp
0x180031668  pop     rbx
0x180031669  retn
```
