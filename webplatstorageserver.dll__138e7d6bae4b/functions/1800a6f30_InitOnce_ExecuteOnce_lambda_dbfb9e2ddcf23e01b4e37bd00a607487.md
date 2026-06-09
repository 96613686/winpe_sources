# InitOnce::ExecuteOnce__lambda_dbfb9e2ddcf23e01b4e37bd00a607487___

- ea: `0x1800a6f30`
- end: `0x1800a6fc6`
- name: `InitOnce::ExecuteOnce__lambda_dbfb9e2ddcf23e01b4e37bd00a607487___`
- size: `150`
- prototype: `__int64 __fastcall(PINIT_ONCE InitOnce)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x1800756fc`

## callees

- `0x1800a6f30`

## import_xrefs

- `msvcp_win!?__ExceptionPtrRethrow@@YAXPEBX@Z` at `0x1800a6fa8`
- `msvcp_win!?__ExceptionPtrRethrow@@YAXPEBX@Z` at `0x1800a6fa8`
- `msvcp_win!?__ExceptionPtrToBool@@YA_NPEBX@Z` at `0x1800a6f7c`
- `msvcp_win!?__ExceptionPtrToBool@@YA_NPEBX@Z` at `0x1800a6f7c`
- `msvcp_win!?__ExceptionPtrCreate@@YAXPEAX@Z` at `0x1800a6f58`
- `msvcp_win!?__ExceptionPtrCreate@@YAXPEAX@Z` at `0x1800a6f58`
- `msvcp_win!?__ExceptionPtrCopy@@YAXPEAXPEBX@Z` at `0x1800a6f96`
- `msvcp_win!?__ExceptionPtrCopy@@YAXPEAXPEBX@Z` at `0x1800a6f96`
- `msvcp_win!?__ExceptionPtrDestroy@@YAXPEAX@Z` at `0x1800a6fb3`
- `msvcp_win!?__ExceptionPtrDestroy@@YAXPEAX@Z` at `0x1800a6fb3`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x1800a6f70`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x1800a6f70`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall InitOnce::ExecuteOnce__lambda_dbfb9e2ddcf23e01b4e37bd00a607487___(PINIT_ONCE InitOnce)
{
  unsigned int inited; // ebx
  __int128 v4; // [rsp+20h] [rbp-30h] BYREF
  char Parameter; // [rsp+30h] [rbp-20h] BYREF
  int v6; // [rsp+31h] [rbp-1Fh]
  __int16 v7; // [rsp+35h] [rbp-1Bh]
  char v8; // [rsp+37h] [rbp-19h]
  __int128 v9; // [rsp+38h] [rbp-18h] BYREF

  v6 = 0;
  v7 = 0;
  v8 = 0;
  v9 = 0;
  __ExceptionPtrCreate(&v9);
  inited = InitOnceExecuteOnce(
             InitOnce,
             lambda_8747b78e4abc4e6c8b04417471389f8d_::_lambda_invoker_cdecl_,
             &Parameter,
             0);
  if ( __ExceptionPtrToBool(&v9) )
  {
    v4 = 0;
    __ExceptionPtrCopy(&v4, &v9);
    __ExceptionPtrRethrow(&v4);
  }
  __ExceptionPtrDestroy(&v9);
  return inited;
}

```

## disassembly

```asm
0x1800a6f30  mov     [rsp-8+arg_8], rbx
0x1800a6f35  push    rbp
0x1800a6f36  mov     rbp, rsp
0x1800a6f39  sub     rsp, 50h
0x1800a6f3d  mov     rbx, rcx
0x1800a6f40  xor     eax, eax
0x1800a6f42  mov     [rbp+var_1F], eax
0x1800a6f45  mov     [rbp+var_1B], ax
0x1800a6f49  mov     [rbp+var_19], al
0x1800a6f4c  xorps   xmm0, xmm0
0x1800a6f4f  movdqu  [rbp+var_18], xmm0
0x1800a6f54  lea     rcx, [rbp+var_18]
0x1800a6f58  call    cs:__imp_?__ExceptionPtrCreate@@YAXPEAX@Z; __ExceptionPtrCreate(void *)
0x1800a6f5e  nop
0x1800a6f5f  xor     r9d, r9d; Context
0x1800a6f62  lea     r8, [rbp+Parameter]; Parameter
0x1800a6f66  lea     rdx, _lambda_8747b78e4abc4e6c8b04417471389f8d____lambda_invoker_cdecl_; InitFn
0x1800a6f6d  mov     rcx, rbx; InitOnce
0x1800a6f70  call    cs:__imp_InitOnceExecuteOnce
0x1800a6f76  mov     ebx, eax
0x1800a6f78  lea     rcx, [rbp+var_18]
0x1800a6f7c  call    cs:__imp_?__ExceptionPtrToBool@@YA_NPEBX@Z; __ExceptionPtrToBool(void const *)
0x1800a6f82  test    al, al
0x1800a6f84  jz      short loc_1800A6FAF
0x1800a6f86  xorps   xmm0, xmm0
0x1800a6f89  movdqu  [rbp+var_30], xmm0
0x1800a6f8e  lea     rdx, [rbp+var_18]
0x1800a6f92  lea     rcx, [rbp+var_30]
0x1800a6f96  call    cs:__imp_?__ExceptionPtrCopy@@YAXPEAXPEBX@Z; __ExceptionPtrCopy(void *,void const *)
0x1800a6f9c  lea     rax, [rbp+var_30]
0x1800a6fa0  mov     [rbp+arg_0], rax
0x1800a6fa4  lea     rcx, [rbp+var_30]
0x1800a6fa8  call    cs:__imp_?__ExceptionPtrRethrow@@YAXPEBX@Z; __ExceptionPtrRethrow(void const *)
0x1800a6fae  nop
0x1800a6faf  lea     rcx, [rbp+var_18]
0x1800a6fb3  call    cs:__imp_?__ExceptionPtrDestroy@@YAXPEAX@Z; __ExceptionPtrDestroy(void *)
0x1800a6fb9  mov     eax, ebx
0x1800a6fbb  mov     rbx, [rsp+50h+arg_8]
0x1800a6fc0  add     rsp, 50h
0x1800a6fc4  pop     rbp
0x1800a6fc5  retn
```
