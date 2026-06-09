# mi::MiAsyncOperation::MiOperationArgs::Join(std::chrono::duration<__int64,std::ratio<1,1000>> const &,bool)

- ea: `0x1800280f8`
- end: `0x180028192`
- name: `?Join@MiOperationArgs@MiAsyncOperation@mi@@QEAA_NAEBV?$duration@_JU?$ratio@$00$0DOI@@std@@@chrono@std@@_N@Z`
- size: `154`
- prototype: `bool __fastcall(RTL_SRWLOCK *this, int *, char)`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x180027cdc`
- `0x1800280c0`

## callees

- `0x1800280f8`
- `0x180028280`
- `0x180028be0`

## import_xrefs

- `msvcp_win!?__ExceptionPtrRethrow@@YAXPEBX@Z` at `0x180028168`
- `msvcp_win!?__ExceptionPtrRethrow@@YAXPEBX@Z` at `0x180028168`
- `msvcp_win!?__ExceptionPtrToBool@@YA_NPEBX@Z` at `0x180028138`
- `msvcp_win!?__ExceptionPtrToBool@@YA_NPEBX@Z` at `0x180028138`
- `msvcp_win!?__ExceptionPtrCopy@@YAXPEAXPEBX@Z` at `0x180028153`
- `msvcp_win!?__ExceptionPtrCopy@@YAXPEAXPEBX@Z` at `0x180028153`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180028127`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180028127`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180028172`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180028172`

## pseudocode

```c
bool __fastcall mi::MiAsyncOperation::MiOperationArgs::Join(RTL_SRWLOCK *this, int *a2, char a3)
{
  __int128 v6; // [rsp+20h] [rbp-18h] BYREF

  mi::WaitHandle::WaitOne((mi::WaitHandle *)this, *a2);
  if ( a3 )
  {
    AcquireSRWLockShared(this + 57);
    if ( __ExceptionPtrToBool(&this[55]) )
    {
      v6 = 0;
      __ExceptionPtrCopy(&v6, &this[55]);
      __ExceptionPtrRethrow(&v6);
    }
    ReleaseSRWLockShared(this + 57);
  }
  return !mi::MiAsyncOperation::MiOperationArgs::has_exception((mi::MiAsyncOperation::MiOperationArgs *)this);
}

```

## disassembly

```asm
0x1800280f8  mov     [rsp+arg_10], rbx
0x1800280fd  mov     [rsp+arg_18], rsi
0x180028102  push    rdi
0x180028103  sub     rsp, 30h
0x180028107  mov     bl, r8b
0x18002810a  mov     rdi, rcx
0x18002810d  mov     edx, [rdx]; int
0x18002810f  call    ?WaitOne@WaitHandle@mi@@QEBA_NH@Z; mi::WaitHandle::WaitOne(int)
0x180028114  test    bl, bl
0x180028116  jz      short loc_180028178
0x180028118  lea     rbx, [rdi+1C8h]
0x18002811f  mov     [rsp+38h+arg_0], rbx
0x180028124  mov     rcx, rbx; SRWLock
0x180028127  call    cs:__imp_AcquireSRWLockShared
0x18002812d  nop
0x18002812e  lea     rsi, [rdi+1B8h]
0x180028135  mov     rcx, rsi
0x180028138  call    cs:__imp_?__ExceptionPtrToBool@@YA_NPEBX@Z; __ExceptionPtrToBool(void const *)
0x18002813e  test    al, al
0x180028140  jz      short loc_18002816F
0x180028142  xorps   xmm0, xmm0
0x180028145  movdqu  [rsp+38h+var_18], xmm0
0x18002814b  mov     rdx, rsi
0x18002814e  lea     rcx, [rsp+38h+var_18]
0x180028153  call    cs:__imp_?__ExceptionPtrCopy@@YAXPEAXPEBX@Z; __ExceptionPtrCopy(void *,void const *)
0x180028159  lea     rax, [rsp+38h+var_18]
0x18002815e  mov     [rsp+38h+arg_8], rax
0x180028163  lea     rcx, [rsp+38h+var_18]
0x180028168  call    cs:__imp_?__ExceptionPtrRethrow@@YAXPEBX@Z; __ExceptionPtrRethrow(void const *)
0x18002816e  nop
0x18002816f  mov     rcx, rbx; SRWLock
0x180028172  call    cs:__imp_ReleaseSRWLockShared
0x180028178  mov     rcx, rdi; this
0x18002817b  call    ?has_exception@MiOperationArgs@MiAsyncOperation@mi@@QEAA_NXZ; mi::MiAsyncOperation::MiOperationArgs::has_exception(void)
0x180028180  xor     al, 1
0x180028182  mov     rbx, [rsp+38h+arg_10]
0x180028187  mov     rsi, [rsp+38h+arg_18]
0x18002818c  add     rsp, 30h
0x180028190  pop     rdi
0x180028191  retn
```
