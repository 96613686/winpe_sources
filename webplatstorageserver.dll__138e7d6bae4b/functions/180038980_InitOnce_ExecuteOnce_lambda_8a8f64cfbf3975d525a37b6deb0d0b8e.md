# InitOnce::ExecuteOnce__lambda_8a8f64cfbf3975d525a37b6deb0d0b8e___

- ea: `0x180038980`
- end: `0x180038a19`
- name: `InitOnce::ExecuteOnce__lambda_8a8f64cfbf3975d525a37b6deb0d0b8e___`
- size: `153`
- prototype: `__int64 __fastcall(PINIT_ONCE InitOnce)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x1800387e4`

## callees

- `0x180038980`

## import_xrefs

- `msvcp_win!?__ExceptionPtrRethrow@@YAXPEBX@Z` at `0x1800389fb`
- `msvcp_win!?__ExceptionPtrRethrow@@YAXPEBX@Z` at `0x1800389fb`
- `msvcp_win!?__ExceptionPtrToBool@@YA_NPEBX@Z` at `0x1800389cf`
- `msvcp_win!?__ExceptionPtrToBool@@YA_NPEBX@Z` at `0x1800389cf`
- `msvcp_win!?__ExceptionPtrCreate@@YAXPEAX@Z` at `0x1800389ab`
- `msvcp_win!?__ExceptionPtrCreate@@YAXPEAX@Z` at `0x1800389ab`
- `msvcp_win!?__ExceptionPtrCopy@@YAXPEAXPEBX@Z` at `0x1800389e9`
- `msvcp_win!?__ExceptionPtrCopy@@YAXPEAXPEBX@Z` at `0x1800389e9`
- `msvcp_win!?__ExceptionPtrDestroy@@YAXPEAX@Z` at `0x180038a06`
- `msvcp_win!?__ExceptionPtrDestroy@@YAXPEAX@Z` at `0x180038a06`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x1800389c3`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x1800389c3`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall InitOnce::ExecuteOnce__lambda_8a8f64cfbf3975d525a37b6deb0d0b8e___(PINIT_ONCE InitOnce, _OWORD *a2)
{
  unsigned int inited; // ebx
  __int128 v5; // [rsp+20h] [rbp-40h] BYREF
  _OWORD Parameter[2]; // [rsp+30h] [rbp-30h] BYREF
  __int128 v7; // [rsp+50h] [rbp-10h] BYREF

  Parameter[0] = *a2;
  Parameter[1] = a2[1];
  v7 = 0;
  __ExceptionPtrCreate(&v7);
  inited = InitOnceExecuteOnce(InitOnce, lambda_33ad47b4fc92c337c55784e1ad6a8020_::_lambda_invoker_cdecl_, Parameter, 0);
  if ( __ExceptionPtrToBool(&v7) )
  {
    v5 = 0;
    __ExceptionPtrCopy(&v5, &v7);
    __ExceptionPtrRethrow(&v5);
  }
  __ExceptionPtrDestroy(&v7);
  return inited;
}

```

## disassembly

```asm
0x180038980  mov     [rsp-8+arg_8], rbx
0x180038985  push    rbp
0x180038986  mov     rbp, rsp
0x180038989  sub     rsp, 60h
0x18003898d  mov     rbx, rcx
0x180038990  movaps  xmm0, xmmword ptr [rdx]
0x180038993  movups  [rbp+Parameter], xmm0
0x180038997  movaps  xmm1, xmmword ptr [rdx+10h]
0x18003899b  movups  [rbp+var_20], xmm1
0x18003899f  xorps   xmm0, xmm0
0x1800389a2  movdqu  [rbp+var_10], xmm0
0x1800389a7  lea     rcx, [rbp+var_10]
0x1800389ab  call    cs:__imp_?__ExceptionPtrCreate@@YAXPEAX@Z; __ExceptionPtrCreate(void *)
0x1800389b1  nop
0x1800389b2  xor     r9d, r9d; Context
0x1800389b5  lea     r8, [rbp+Parameter]; Parameter
0x1800389b9  lea     rdx, _lambda_33ad47b4fc92c337c55784e1ad6a8020____lambda_invoker_cdecl_; InitFn
0x1800389c0  mov     rcx, rbx; InitOnce
0x1800389c3  call    cs:__imp_InitOnceExecuteOnce
0x1800389c9  mov     ebx, eax
0x1800389cb  lea     rcx, [rbp+var_10]
0x1800389cf  call    cs:__imp_?__ExceptionPtrToBool@@YA_NPEBX@Z; __ExceptionPtrToBool(void const *)
0x1800389d5  test    al, al
0x1800389d7  jz      short loc_180038A02
0x1800389d9  xorps   xmm0, xmm0
0x1800389dc  movdqu  [rbp+var_40], xmm0
0x1800389e1  lea     rdx, [rbp+var_10]
0x1800389e5  lea     rcx, [rbp+var_40]
0x1800389e9  call    cs:__imp_?__ExceptionPtrCopy@@YAXPEAXPEBX@Z; __ExceptionPtrCopy(void *,void const *)
0x1800389ef  lea     rax, [rbp+var_40]
0x1800389f3  mov     [rbp+arg_0], rax
0x1800389f7  lea     rcx, [rbp+var_40]
0x1800389fb  call    cs:__imp_?__ExceptionPtrRethrow@@YAXPEBX@Z; __ExceptionPtrRethrow(void const *)
0x180038a01  nop
0x180038a02  lea     rcx, [rbp+var_10]
0x180038a06  call    cs:__imp_?__ExceptionPtrDestroy@@YAXPEAX@Z; __ExceptionPtrDestroy(void *)
0x180038a0c  mov     eax, ebx
0x180038a0e  mov     rbx, [rsp+60h+arg_8]
0x180038a13  add     rsp, 60h
0x180038a17  pop     rbp
0x180038a18  retn
```
