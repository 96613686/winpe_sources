# Concurrency::details::_TaskCollectionBaseImpl::WaitUntilStateChangedTo(Concurrency::details::_TaskCollectionBaseImpl::_TaskCollectionState)

- ea: `0x140006d14`
- end: `0x140006d82`
- name: `?WaitUntilStateChangedTo@_TaskCollectionBaseImpl@details@Concurrency@@IEAAXW4_TaskCollectionState@123@@Z`
- size: `110`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `service_task`

## callers

- `0x140006b30`

## callees

- `0x140006d14`
- `0x140006e8c`
- `0x1400198d0`
- `0x14001b294`

## import_xrefs

- `api-ms-win-crt-runtime-l1-1-0!abort` at `0x140006d7b`
- `api-ms-win-crt-runtime-l1-1-0!abort` at `0x140006d7b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140006d4e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140006d4e`

## pseudocode

```c
void __fastcall Concurrency::details::_TaskCollectionBaseImpl::WaitUntilStateChangedTo(__int64 a1)
{
  struct _Mtx_internal_imp_t *v1; // rdi
  unsigned int v3; // r8d
  DWORD CurrentThreadId; // eax

  v1 = (struct _Mtx_internal_imp_t *)(a1 + 72);
  std::_Mutex_base::lock((std::_Mutex_base *)(a1 + 72));
  while ( *(int *)(a1 + 176) < 2 )
  {
    --*(_DWORD *)(a1 + 148);
    *(_DWORD *)(a1 + 144) = -1;
    if ( !_Primitive_wait_for((struct _Cnd_internal_imp_t *const)a1, v1, v3) )
      abort();
    CurrentThreadId = GetCurrentThreadId();
    ++*(_DWORD *)(a1 + 148);
    *(_DWORD *)(a1 + 144) = CurrentThreadId;
  }
  std::_Mutex_base::unlock(v1);
}

```

## disassembly

```asm
0x140006d14  mov     [rsp+arg_0], rbx
0x140006d19  push    rdi
0x140006d1a  sub     rsp, 20h
0x140006d1e  lea     rdi, [rcx+48h]
0x140006d22  mov     rbx, rcx
0x140006d25  mov     rcx, rdi; this
0x140006d28  call    ?lock@_Mutex_base@std@@QEAAXXZ; std::_Mutex_base::lock(void)
0x140006d2d  jmp     short loc_140006D60
0x140006d2f  dec     dword ptr [rbx+94h]
0x140006d35  mov     rdx, rdi; struct _Mtx_internal_imp_t *
0x140006d38  mov     rcx, rbx; struct _Cnd_internal_imp_t *
0x140006d3b  mov     dword ptr [rbx+90h], 0FFFFFFFFh
0x140006d45  call    ?_Primitive_wait_for@@YA_NQEAU_Cnd_internal_imp_t@@QEAU_Mtx_internal_imp_t@@I@Z; _Primitive_wait_for(_Cnd_internal_imp_t * const,_Mtx_internal_imp_t * const,uint)
0x140006d4a  test    al, al
0x140006d4c  jz      short loc_140006D7B
0x140006d4e  call    cs:__imp_GetCurrentThreadId
0x140006d54  inc     dword ptr [rbx+94h]
0x140006d5a  mov     [rbx+90h], eax
0x140006d60  cmp     dword ptr [rbx+0B0h], 2
0x140006d67  jl      short loc_140006D2F
0x140006d69  mov     rcx, rdi; this
0x140006d6c  mov     rbx, [rsp+28h+arg_0]
0x140006d71  add     rsp, 20h
0x140006d75  pop     rdi
0x140006d76  jmp     ?unlock@_Mutex_base@std@@QEAAXXZ; std::_Mutex_base::unlock(void)
0x140006d7b  call    cs:__imp_abort
```
