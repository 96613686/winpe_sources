# CacheStorageActiveReference::EnsureCacheStorageInfo(std::shared_ptr<EseHelper::IDatabaseTable> const &)

- ea: `0x18003c760`
- end: `0x18003c7f2`
- name: `?EnsureCacheStorageInfo@CacheStorageActiveReference@@QEAAXAEBV?$shared_ptr@UIDatabaseTable@EseHelper@@@std@@@Z`
- size: `146`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x18003bcf8`
- `0x18006d1b4`

## callees

- `0x18003c760`

## import_xrefs

- `msvcp_win!?__ExceptionPtrRethrow@@YAXPEBX@Z` at `0x18003c7eb`
- `msvcp_win!?__ExceptionPtrRethrow@@YAXPEBX@Z` at `0x18003c7eb`
- `msvcp_win!?__ExceptionPtrToBool@@YA_NPEBX@Z` at `0x18003c7aa`
- `msvcp_win!?__ExceptionPtrToBool@@YA_NPEBX@Z` at `0x18003c7aa`
- `msvcp_win!?__ExceptionPtrCreate@@YAXPEAX@Z` at `0x18003c784`
- `msvcp_win!?__ExceptionPtrCreate@@YAXPEAX@Z` at `0x18003c784`
- `msvcp_win!?__ExceptionPtrCopy@@YAXPEAXPEBX@Z` at `0x18003c7d9`
- `msvcp_win!?__ExceptionPtrCopy@@YAXPEAXPEBX@Z` at `0x18003c7d9`
- `msvcp_win!?__ExceptionPtrDestroy@@YAXPEAX@Z` at `0x18003c7b8`
- `msvcp_win!?__ExceptionPtrDestroy@@YAXPEAX@Z` at `0x18003c7b8`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x18003c7a0`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x18003c7a0`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall CacheStorageActiveReference::EnsureCacheStorageInfo(union _RTL_RUN_ONCE *a1, __int64 a2)
{
  __int128 v3; // [rsp+20h] [rbp-30h] BYREF
  _QWORD Parameter[2]; // [rsp+30h] [rbp-20h] BYREF
  __int128 v5; // [rsp+40h] [rbp-10h] BYREF

  Parameter[0] = a1;
  Parameter[1] = a2;
  v5 = 0;
  __ExceptionPtrCreate(&v5);
  InitOnceExecuteOnce(a1 + 16, lambda_6bd70fdb7c04097612af34e3faf7263b_::_lambda_invoker_cdecl_, Parameter, 0);
  if ( __ExceptionPtrToBool(&v5) )
  {
    v3 = 0;
    __ExceptionPtrCopy(&v3, &v5);
    __ExceptionPtrRethrow(&v3);
    JUMPOUT(0x18003C7F1LL);
  }
  __ExceptionPtrDestroy(&v5);
}

```

## disassembly

```asm
0x18003c760  mov     [rsp-8+arg_8], rbx
0x18003c765  push    rbp
0x18003c766  mov     rbp, rsp
0x18003c769  sub     rsp, 50h
0x18003c76d  mov     rbx, rcx
0x18003c770  mov     [rbp+Parameter], rcx
0x18003c774  mov     [rbp+var_18], rdx
0x18003c778  xorps   xmm0, xmm0
0x18003c77b  movdqu  [rbp+var_10], xmm0
0x18003c780  lea     rcx, [rbp+var_10]
0x18003c784  call    cs:__imp_?__ExceptionPtrCreate@@YAXPEAX@Z; __ExceptionPtrCreate(void *)
0x18003c78a  nop
0x18003c78b  lea     rcx, [rbx+80h]; InitOnce
0x18003c792  xor     r9d, r9d; Context
0x18003c795  lea     r8, [rbp+Parameter]; Parameter
0x18003c799  lea     rdx, _lambda_6bd70fdb7c04097612af34e3faf7263b____lambda_invoker_cdecl_; InitFn
0x18003c7a0  call    cs:__imp_InitOnceExecuteOnce
0x18003c7a6  lea     rcx, [rbp+var_10]
0x18003c7aa  call    cs:__imp_?__ExceptionPtrToBool@@YA_NPEBX@Z; __ExceptionPtrToBool(void const *)
0x18003c7b0  test    al, al
0x18003c7b2  jnz     short loc_18003C7C9
0x18003c7b4  lea     rcx, [rbp+var_10]
0x18003c7b8  call    cs:__imp_?__ExceptionPtrDestroy@@YAXPEAX@Z; __ExceptionPtrDestroy(void *)
0x18003c7be  mov     rbx, [rsp+50h+arg_8]
0x18003c7c3  add     rsp, 50h
0x18003c7c7  pop     rbp
0x18003c7c8  retn
0x18003c7c9  xorps   xmm0, xmm0
0x18003c7cc  movdqu  [rbp+var_30], xmm0
0x18003c7d1  lea     rdx, [rbp+var_10]
0x18003c7d5  lea     rcx, [rbp+var_30]
0x18003c7d9  call    cs:__imp_?__ExceptionPtrCopy@@YAXPEAXPEBX@Z; __ExceptionPtrCopy(void *,void const *)
0x18003c7df  lea     rax, [rbp+var_30]
0x18003c7e3  mov     [rbp+arg_0], rax
0x18003c7e7  lea     rcx, [rbp+var_30]
0x18003c7eb  call    cs:__imp_?__ExceptionPtrRethrow@@YAXPEBX@Z; __ExceptionPtrRethrow(void const *)
```
