# Concurrency::details::_TaskCollectionBaseImpl::WaitUntilStateChangedTo(Concurrency::details::_TaskCollectionBaseImpl::_TaskCollectionState)

- ea: `0x1400070b8`
- end: `0x140007132`
- name: `?WaitUntilStateChangedTo@_TaskCollectionBaseImpl@details@Concurrency@@IEAAXW4_TaskCollectionState@123@@Z`
- size: `122`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `service_task`

## callers

- `0x140006ec8`

## callees

- `0x1400070b8`
- `0x1400072e4`
- `0x14001a5d8`
- `0x14001c148`

## import_xrefs

- `api-ms-win-crt-runtime-l1-1-0!abort` at `0x140007125`
- `api-ms-win-crt-runtime-l1-1-0!abort` at `0x140007125`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1400070f2`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1400070f2`

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
0x1400070b8  mov     [rsp+arg_0], rbx
0x1400070bd  push    rdi
0x1400070be  sub     rsp, 20h
0x1400070c2  lea     rdi, [rcx+48h]
0x1400070c6  mov     rbx, rcx
0x1400070c9  mov     rcx, rdi; this
0x1400070cc  call    ?lock@_Mutex_base@std@@QEAAXXZ; std::_Mutex_base::lock(void)
0x1400070d1  jmp     short loc_14000710A
0x1400070d3  dec     dword ptr [rbx+94h]
0x1400070d9  mov     rdx, rdi; struct _Mtx_internal_imp_t *
0x1400070dc  mov     rcx, rbx; struct _Cnd_internal_imp_t *
0x1400070df  mov     dword ptr [rbx+90h], 0FFFFFFFFh
0x1400070e9  call    ?_Primitive_wait_for@@YA_NQEAU_Cnd_internal_imp_t@@QEAU_Mtx_internal_imp_t@@I@Z; _Primitive_wait_for(_Cnd_internal_imp_t * const,_Mtx_internal_imp_t * const,uint)
0x1400070ee  test    al, al
0x1400070f0  jz      short loc_140007125
0x1400070f2  call    cs:__imp_GetCurrentThreadId
0x1400070f9  nop     dword ptr [rax+rax+00h]
0x1400070fe  inc     dword ptr [rbx+94h]
0x140007104  mov     [rbx+90h], eax
0x14000710a  cmp     dword ptr [rbx+0B0h], 2
0x140007111  jl      short loc_1400070D3
0x140007113  mov     rcx, rdi; this
0x140007116  mov     rbx, [rsp+28h+arg_0]
0x14000711b  add     rsp, 20h
0x14000711f  pop     rdi
0x140007120  jmp     ?unlock@_Mutex_base@std@@QEAAXXZ; std::_Mutex_base::unlock(void)
0x140007125  call    cs:__imp_abort
```
