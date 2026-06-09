# Concurrency::details::_Task_impl_base::_Wait(void)

- ea: `0x140006b30`
- end: `0x140006c2c`
- name: `?_Wait@_Task_impl_base@details@Concurrency@@QEAA?AW4task_group_status@3@XZ`
- size: `252`
- prototype: ``
- caller_count: `3`
- callee_count: `9`
- tags: `service_task`

## callers

- `0x140006a84`
- `0x1400194a0`
- `0x140019570`

## callees

- `0x140006b30`
- `0x140006d14`
- `0x140006e8c`
- `0x14000ff0c`
- `0x14001218c`
- `0x1400198d0`
- `0x14001b294`
- `0x14001eaa4`
- `0x140035e2c`

## import_xrefs

- `api-ms-win-crt-runtime-l1-1-0!abort` at `0x140006ba5`
- `api-ms-win-crt-runtime-l1-1-0!abort` at `0x140006ba5`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140006b80`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140006b80`

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
0x140006b30  mov     [rsp+arg_10], rbx
0x140006b35  mov     [rsp+arg_0], rcx
0x140006b3a  push    rsi
0x140006b3b  push    rdi
0x140006b3c  push    r14
0x140006b3e  sub     rsp, 30h
0x140006b42  mov     rdi, rcx
0x140006b45  xor     ebx, ebx
0x140006b47  cmp     [rcx+0Ch], bl
0x140006b4a  jz      short loc_140006BAC
0x140006b4c  lea     rsi, [rcx+88h]
0x140006b53  lea     r14, [rsi+48h]
0x140006b57  mov     rcx, r14; this
0x140006b5a  call    ?lock@_Mutex_base@std@@QEAAXXZ; std::_Mutex_base::lock(void)
0x140006b5f  jmp     short loc_140006B92
0x140006b61  mov     dword ptr [rsi+90h], 0FFFFFFFFh
0x140006b6b  dec     dword ptr [rsi+94h]
0x140006b71  mov     rdx, r14; struct _Mtx_internal_imp_t *
0x140006b74  mov     rcx, rsi; struct _Cnd_internal_imp_t *
0x140006b77  call    ?_Primitive_wait_for@@YA_NQEAU_Cnd_internal_imp_t@@QEAU_Mtx_internal_imp_t@@I@Z; _Primitive_wait_for(_Cnd_internal_imp_t * const,_Mtx_internal_imp_t * const,uint)
0x140006b7c  test    al, al
0x140006b7e  jz      short loc_140006BA5
0x140006b80  call    cs:__imp_GetCurrentThreadId
0x140006b86  mov     [rsi+90h], eax
0x140006b8c  inc     dword ptr [rsi+94h]
0x140006b92  cmp     dword ptr [rsi+0B0h], 2
0x140006b99  jl      short loc_140006B61
0x140006b9b  mov     rcx, r14; this
0x140006b9e  call    ?unlock@_Mutex_base@std@@QEAAXXZ; std::_Mutex_base::unlock(void)
0x140006ba3  jmp     short loc_140006C03
0x140006ba5  call    cs:__imp_abort
0x140006bac  add     rcx, 88h
0x140006bb3  mov     [rsp+48h+arg_8], rcx
0x140006bb8  call    ?WaitUntilStateChangedTo@_TaskCollectionBaseImpl@details@Concurrency@@IEAAXW4_TaskCollectionState@123@@Z; Concurrency::details::_TaskCollectionBaseImpl::WaitUntilStateChangedTo(Concurrency::details::_TaskCollectionBaseImpl::_TaskCollectionState)
0x140006bbd  nop
0x140006bbe  jmp     short loc_140006BC9
0x140006bc0  jmp     short $+2
0x140006bc2  mov     rdi, [rsp+48h+arg_0]
0x140006bc7  xor     ebx, ebx
0x140006bc9  cmp     [rdi+0Dh], bl
0x140006bcc  jz      short loc_140006C03
0x140006bce  mov     rsi, [rsp+48h+arg_8]
0x140006bd3  lea     rdx, [rsi+48h]
0x140006bd7  lea     rcx, [rsp+48h+var_28]
0x140006bdc  call    ??0?$unique_lock@Vmutex@std@@@std@@QEAA@AEAVmutex@1@@Z; std::unique_lock<std::mutex>::unique_lock<std::mutex>(std::mutex &)
0x140006be1  jmp     short loc_140006BF0
0x140006be3  lea     rdx, [rsp+48h+var_28]
0x140006be8  mov     rcx, rsi
0x140006beb  call    ?wait@condition_variable@std@@QEAAXAEAV?$unique_lock@Vmutex@std@@@2@@Z; std::condition_variable::wait(std::unique_lock<std::mutex> &)
0x140006bf0  cmp     dword ptr [rsi+0B0h], 2
0x140006bf7  jl      short loc_140006BE3
0x140006bf9  lea     rcx, [rsp+48h+var_28]
0x140006bfe  call    ??1?$unique_lock@Vmutex@std@@@std@@QEAA@XZ; std::unique_lock<std::mutex>::~unique_lock<std::mutex>(void)
0x140006c03  mov     rcx, [rdi+10h]; this
0x140006c07  test    rcx, rcx
0x140006c0a  jz      short loc_140006C12
0x140006c0c  call    ?_RethrowUserException@_ExceptionHolder@details@Concurrency@@QEAAXXZ; Concurrency::details::_ExceptionHolder::_RethrowUserException(void)
0x140006c12  mov     ecx, [rdi+8]
0x140006c15  cmp     ecx, 4
0x140006c18  setz    bl
0x140006c1b  lea     eax, [rbx+1]
0x140006c1e  mov     rbx, [rsp+48h+arg_10]
0x140006c23  add     rsp, 30h
0x140006c27  pop     r14
0x140006c29  pop     rdi
0x140006c2a  pop     rsi
0x140006c2b  retn
```
