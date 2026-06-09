# mi::MiAsyncOperation::MiOperationArgs::Join(std::chrono::duration<__int64,std::ratio<1,1000>> const &,bool)

- ea: `0x1800284c0`
- end: `0x180028579`
- name: `?Join@MiOperationArgs@MiAsyncOperation@mi@@QEAA_NAEBV?$duration@_JU?$ratio@$00$0DOI@@std@@@chrono@std@@_N@Z`
- size: `185`
- prototype: `__int64 __fastcall(mi::MiAsyncOperation::MiOperationArgs *this)`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x180028078`
- `0x180028488`

## callees

- `0x1800284c0`
- `0x180028680`
- `0x18002904c`

## import_xrefs

- `msvcp_win!?__ExceptionPtrRethrow@@YAXPEBX@Z` at `0x180028542`
- `msvcp_win!?__ExceptionPtrRethrow@@YAXPEBX@Z` at `0x180028542`
- `msvcp_win!?__ExceptionPtrToBool@@YA_NPEBX@Z` at `0x180028506`
- `msvcp_win!?__ExceptionPtrToBool@@YA_NPEBX@Z` at `0x180028506`
- `msvcp_win!?__ExceptionPtrCopy@@YAXPEAXPEBX@Z` at `0x180028527`
- `msvcp_win!?__ExceptionPtrCopy@@YAXPEAXPEBX@Z` at `0x180028527`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x1800284ef`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x1800284ef`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180028552`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180028552`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
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
0x1800284c0  mov     [rsp+arg_10], rbx
0x1800284c5  mov     [rsp+arg_18], rsi
0x1800284ca  push    rdi
0x1800284cb  sub     rsp, 30h
0x1800284cf  mov     bl, r8b
0x1800284d2  mov     rdi, rcx
0x1800284d5  mov     edx, [rdx]; int
0x1800284d7  call    ?WaitOne@WaitHandle@mi@@QEBA_NH@Z; mi::WaitHandle::WaitOne(int)
0x1800284dc  test    bl, bl
0x1800284de  jz      short loc_18002855E
0x1800284e0  lea     rbx, [rdi+1C8h]
0x1800284e7  mov     [rsp+38h+arg_0], rbx
0x1800284ec  mov     rcx, rbx; SRWLock
0x1800284ef  call    cs:__imp_AcquireSRWLockShared
0x1800284f6  nop     dword ptr [rax+rax+00h]
0x1800284fb  nop
0x1800284fc  lea     rsi, [rdi+1B8h]
0x180028503  mov     rcx, rsi
0x180028506  call    cs:__imp_?__ExceptionPtrToBool@@YA_NPEBX@Z; __ExceptionPtrToBool(void const *)
0x18002850d  nop     dword ptr [rax+rax+00h]
0x180028512  test    al, al
0x180028514  jz      short loc_18002854F
0x180028516  xorps   xmm0, xmm0
0x180028519  movdqu  [rsp+38h+var_18], xmm0
0x18002851f  mov     rdx, rsi
0x180028522  lea     rcx, [rsp+38h+var_18]
0x180028527  call    cs:__imp_?__ExceptionPtrCopy@@YAXPEAXPEBX@Z; __ExceptionPtrCopy(void *,void const *)
0x18002852e  nop     dword ptr [rax+rax+00h]
0x180028533  lea     rax, [rsp+38h+var_18]
0x180028538  mov     [rsp+38h+arg_8], rax
0x18002853d  lea     rcx, [rsp+38h+var_18]
0x180028542  call    cs:__imp_?__ExceptionPtrRethrow@@YAXPEBX@Z; __ExceptionPtrRethrow(void const *)
0x180028549  nop     dword ptr [rax+rax+00h]
0x18002854e  nop
0x18002854f  mov     rcx, rbx; SRWLock
0x180028552  call    cs:__imp_ReleaseSRWLockShared
0x180028559  nop     dword ptr [rax+rax+00h]
0x18002855e  mov     rcx, rdi; this
0x180028561  call    ?has_exception@MiOperationArgs@MiAsyncOperation@mi@@QEAA_NXZ; mi::MiAsyncOperation::MiOperationArgs::has_exception(void)
0x180028566  xor     al, 1
0x180028568  mov     rbx, [rsp+38h+arg_10]
0x18002856d  mov     rsi, [rsp+38h+arg_18]
0x180028572  add     rsp, 30h
0x180028576  pop     rdi
0x180028577  retn
```
