# Concurrency::details::_Task_impl_base::_Wait(void)

- ea: `0x140006ec8`
- end: `0x140006fd1`
- name: `?_Wait@_Task_impl_base@details@Concurrency@@QEAA?AW4task_group_status@3@XZ`
- size: `265`
- prototype: ``
- caller_count: `3`
- callee_count: `9`
- tags: `service_task`

## callers

- `0x140006e1c`
- `0x14001a190`
- `0x14001a260`

## callees

- `0x140006ec8`
- `0x1400070b8`
- `0x1400072e4`
- `0x14001078c`
- `0x1400129bc`
- `0x14001a5d8`
- `0x14001c148`
- `0x14001f964`
- `0x140037338`

## import_xrefs

- `api-ms-win-crt-runtime-l1-1-0!abort` at `0x140006f43`
- `api-ms-win-crt-runtime-l1-1-0!abort` at `0x140006f43`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140006f18`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140006f18`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Concurrency::details::_Task_impl_base::_Wait(__int64 a1)
{
  __int64 v1; // rdi
  int v2; // ebx
  __int64 v3; // rsi
  struct _Mtx_internal_imp_t *v4; // r14
  unsigned int v5; // r8d
  Concurrency::details::_ExceptionHolder *v6; // rcx
  const struct std::exception_ptr *v8; // rax
  _BYTE v9[8]; // [rsp+20h] [rbp-28h] BYREF
  std::_Ref_count_base *v10; // [rsp+28h] [rbp-20h]
  __int64 v12; // [rsp+58h] [rbp+10h]

  v1 = a1;
  v2 = 0;
  if ( *(_BYTE *)(a1 + 12) )
  {
    v3 = a1 + 136;
    v4 = (struct _Mtx_internal_imp_t *)(a1 + 208);
    std::_Mutex_base::lock((std::_Mutex_base *)(a1 + 208));
    while ( *(int *)(v3 + 176) < 2 )
    {
      *(_DWORD *)(v3 + 144) = -1;
      --*(_DWORD *)(v3 + 148);
      if ( !_Primitive_wait_for((struct _Cnd_internal_imp_t *const)v3, v4, v5) )
        abort();
      *(_DWORD *)(v3 + 144) = GetCurrentThreadId();
      ++*(_DWORD *)(v3 + 148);
    }
    std::_Mutex_base::unlock(v4);
  }
  else
  {
    try
    {
      v12 = a1 + 136;
      Concurrency::details::_TaskCollectionBaseImpl::WaitUntilStateChangedTo();
    }
    catch ( Concurrency::details::_Interruption_exception )
    {
      v1 = a1;
      v2 = 0;
    }
    catch ( Concurrency::task_canceled )
    {
      v1 = a1;
      v2 = 0;
    }
    catch ( ... )
    {
      if ( !*(_QWORD *)(a1 + 16) )
      {
        v8 = (const struct std::exception_ptr *)std::current_exception(v9);
        Concurrency::details::_Task_impl_base::_CancelWithException((Concurrency::details::_Task_impl_base *)a1, v8);
        if ( v10 )
          std::_Ref_count_base::_Decref(v10);
      }
      Concurrency::details::_ExceptionHolder::_RethrowUserException(*(Concurrency::details::_ExceptionHolder **)(a1 + 16));
    }
    if ( *(_BYTE *)(v1 + 13) )
    {
      std::unique_lock<std::mutex>::unique_lock<std::mutex>(v9, v12 + 72);
      while ( *(int *)(v12 + 176) < 2 )
        std::condition_variable::wait(v12, v9);
      std::unique_lock<std::mutex>::~unique_lock<std::mutex>(v9);
    }
  }
  v6 = *(Concurrency::details::_ExceptionHolder **)(v1 + 16);
  if ( v6 )
    Concurrency::details::_ExceptionHolder::_RethrowUserException(v6);
  LOBYTE(v2) = *(_DWORD *)(v1 + 8) == 4;
  return (unsigned int)(v2 + 1);
}

```

## disassembly

```asm
0x140006ec8  mov     [rsp+arg_10], rbx
0x140006ecd  mov     [rsp+arg_0], rcx
0x140006ed2  push    rsi
0x140006ed3  push    rdi
0x140006ed4  push    r14
0x140006ed6  sub     rsp, 30h
0x140006eda  mov     rdi, rcx
0x140006edd  xor     ebx, ebx
0x140006edf  cmp     [rcx+0Ch], bl
0x140006ee2  jz      short loc_140006F50
0x140006ee4  lea     rsi, [rcx+88h]
0x140006eeb  lea     r14, [rsi+48h]
0x140006eef  mov     rcx, r14; this
0x140006ef2  call    ?lock@_Mutex_base@std@@QEAAXXZ; std::_Mutex_base::lock(void)
0x140006ef7  jmp     short loc_140006F30
0x140006ef9  mov     dword ptr [rsi+90h], 0FFFFFFFFh
0x140006f03  dec     dword ptr [rsi+94h]
0x140006f09  mov     rdx, r14; struct _Mtx_internal_imp_t *
0x140006f0c  mov     rcx, rsi; struct _Cnd_internal_imp_t *
0x140006f0f  call    ?_Primitive_wait_for@@YA_NQEAU_Cnd_internal_imp_t@@QEAU_Mtx_internal_imp_t@@I@Z; _Primitive_wait_for(_Cnd_internal_imp_t * const,_Mtx_internal_imp_t * const,uint)
0x140006f14  test    al, al
0x140006f16  jz      short loc_140006F43
0x140006f18  call    cs:__imp_GetCurrentThreadId
0x140006f1f  nop     dword ptr [rax+rax+00h]
0x140006f24  mov     [rsi+90h], eax
0x140006f2a  inc     dword ptr [rsi+94h]
0x140006f30  cmp     dword ptr [rsi+0B0h], 2
0x140006f37  jl      short loc_140006EF9
0x140006f39  mov     rcx, r14; this
0x140006f3c  call    ?unlock@_Mutex_base@std@@QEAAXXZ; std::_Mutex_base::unlock(void)
0x140006f41  jmp     short loc_140006FA7
0x140006f43  call    cs:__imp_abort
0x140006f50  add     rcx, 88h
0x140006f57  mov     [rsp+48h+arg_8], rcx
0x140006f5c  call    ?WaitUntilStateChangedTo@_TaskCollectionBaseImpl@details@Concurrency@@IEAAXW4_TaskCollectionState@123@@Z; Concurrency::details::_TaskCollectionBaseImpl::WaitUntilStateChangedTo(Concurrency::details::_TaskCollectionBaseImpl::_TaskCollectionState)
0x140006f61  nop
0x140006f62  jmp     short loc_140006F6D
0x140006f64  jmp     short $+2
0x140006f66  mov     rdi, [rsp+48h+arg_0]
0x140006f6b  xor     ebx, ebx
0x140006f6d  cmp     [rdi+0Dh], bl
0x140006f70  jz      short loc_140006FA7
0x140006f72  mov     rsi, [rsp+48h+arg_8]
0x140006f77  lea     rdx, [rsi+48h]
0x140006f7b  lea     rcx, [rsp+48h+var_28]
0x140006f80  call    ??0?$unique_lock@Vmutex@std@@@std@@QEAA@AEAVmutex@1@@Z; std::unique_lock<std::mutex>::unique_lock<std::mutex>(std::mutex &)
0x140006f85  jmp     short loc_140006F94
0x140006f87  lea     rdx, [rsp+48h+var_28]
0x140006f8c  mov     rcx, rsi
0x140006f8f  call    ?wait@condition_variable@std@@QEAAXAEAV?$unique_lock@Vmutex@std@@@2@@Z; std::condition_variable::wait(std::unique_lock<std::mutex> &)
0x140006f94  cmp     dword ptr [rsi+0B0h], 2
0x140006f9b  jl      short loc_140006F87
0x140006f9d  lea     rcx, [rsp+48h+var_28]
0x140006fa2  call    ??1?$unique_lock@Vmutex@std@@@std@@QEAA@XZ; std::unique_lock<std::mutex>::~unique_lock<std::mutex>(void)
0x140006fa7  mov     rcx, [rdi+10h]; this
0x140006fab  test    rcx, rcx
0x140006fae  jz      short loc_140006FB6
0x140006fb0  call    ?_RethrowUserException@_ExceptionHolder@details@Concurrency@@QEAAXXZ; Concurrency::details::_ExceptionHolder::_RethrowUserException(void)
0x140006fb6  mov     ecx, [rdi+8]
0x140006fb9  cmp     ecx, 4
0x140006fbc  setz    bl
0x140006fbf  lea     eax, [rbx+1]
0x140006fc2  mov     rbx, [rsp+48h+arg_10]
0x140006fc7  add     rsp, 30h
0x140006fcb  pop     r14
0x140006fcd  pop     rdi
0x140006fce  pop     rsi
0x140006fcf  retn
```
