# Concurrency::details::_Task_impl_base::_RegisterCancellation(std::weak_ptr<Concurrency::details::_Task_impl_base>)

- ea: `0x14001b7ec`
- end: `0x14001ba96`
- name: `?_RegisterCancellation@_Task_impl_base@details@Concurrency@@QEAAXV?$weak_ptr@U_Task_impl_base@details@Concurrency@@@std@@@Z`
- size: `682`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x14001a490`
- `0x14004be48`

## callees

- `0x1400057f0`
- `0x14001b7ec`
- `0x1400a8010`

## import_xrefs

- `msvcp_win!?GetCurrentThreadId@platform@details@Concurrency@@YAJXZ` at `0x14001b998`
- `msvcp_win!?GetCurrentThreadId@platform@details@Concurrency@@YAJXZ` at `0x14001b998`
- `msvcp_win!_Cnd_broadcast` at `0x14001ba16`
- `msvcp_win!_Cnd_broadcast` at `0x14001ba16`
- `msvcp_win!_Mtx_unlock` at `0x14001b989`
- `msvcp_win!_Mtx_unlock` at `0x14001ba0c`
- `msvcp_win!_Mtx_unlock` at `0x14001b989`
- `msvcp_win!_Mtx_unlock` at `0x14001ba0c`
- `msvcp_win!_Mtx_lock` at `0x14001b921`
- `msvcp_win!_Mtx_lock` at `0x14001b9cf`
- `msvcp_win!_Mtx_lock` at `0x14001b921`
- `msvcp_win!_Mtx_lock` at `0x14001b9cf`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x14001b9de`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x14001b9fb`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x14001b9de`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x14001b9fb`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
int __fastcall Concurrency::details::_Task_impl_base::_RegisterCancellation(__int64 a1, __int64 *a2)
{
  volatile signed __int32 *v4; // rdi
  char v5; // r12
  __int64 v6; // rsi
  Concurrency::details::platform *v7; // rcx
  char *v8; // rbx
  struct _Mtx_internal_imp_t *v9; // r14
  __int64 v10; // rsi
  char **v11; // rax
  int result; // eax
  signed __int32 CurrentThreadId; // esi
  signed __int32 v14; // eax
  volatile signed __int32 *v15; // rcx

  v4 = (volatile signed __int32 *)a2[1];
  v5 = 0;
  if ( v4 )
  {
    v6 = *a2;
    _InterlockedIncrement(v4 + 3);
  }
  else
  {
    v4 = 0;
    v6 = 0;
  }
  v8 = (char *)operator new(0xD0u);
  *(_QWORD *)v8 = &Concurrency::details::_RefCounter::`vftable';
  *((_DWORD *)v8 + 2) = 1;
  *((_DWORD *)v8 + 4) = 3;
  *((_QWORD *)v8 + 3) = 0;
  *((_QWORD *)v8 + 4) = 0;
  *(_OWORD *)(v8 + 40) = 0;
  *(_OWORD *)(v8 + 56) = 0;
  *(_OWORD *)(v8 + 72) = 0;
  *((_QWORD *)v8 + 11) = 0;
  v9 = (struct _Mtx_internal_imp_t *)(v8 + 96);
  *((_QWORD *)v8 + 12) = 2;
  *(_OWORD *)(v8 + 120) = 0;
  *(_OWORD *)(v8 + 136) = 0;
  *(_OWORD *)(v8 + 152) = 0;
  *((_QWORD *)v8 + 13) = 0;
  *((_QWORD *)v8 + 14) = 0;
  *((_DWORD *)v8 + 42) = -1;
  *((_DWORD *)v8 + 43) = 0;
  v8[176] = 0;
  *((_QWORD *)v8 + 23) = 0;
  *(_QWORD *)v8 = &Concurrency::details::_CancellationTokenCallback<_lambda_be3e5d9dce35d2c8dbfa8485373731d5_>::`vftable';
  *((_QWORD *)v8 + 24) = 0;
  *((_QWORD *)v8 + 25) = 0;
  if ( v4 )
  {
    *((_QWORD *)v8 + 24) = v6;
    *((_QWORD *)v8 + 25) = v4;
    _InterlockedIncrement(v4 + 3);
  }
  *(_QWORD *)(a1 + 128) = v8;
  v10 = *(_QWORD *)(a1 + 120);
  _InterlockedExchange((volatile __int32 *)v8 + 4, 0);
  _InterlockedIncrement((volatile signed __int32 *)v8 + 2);
  *((_QWORD *)v8 + 23) = v10;
  if ( *(_DWORD *)(v10 + 16) )
    goto LABEL_17;
  if ( _Mtx_lock((_Mtx_t)(v10 + 24)) )
    goto LABEL_22;
  if ( *(_DWORD *)(v10 + 100) == 0x7FFFFFFF )
  {
    *(_DWORD *)(v10 + 100) = 2147483646;
    goto LABEL_25;
  }
  if ( *(_DWORD *)(v10 + 16) )
  {
    v5 = 1;
  }
  else
  {
    v11 = (char **)operator new(0x10u);
    *v11 = v8;
    v11[1] = 0;
    if ( *(_QWORD *)(v10 + 104) )
      *(_QWORD *)(*(_QWORD *)(v10 + 112) + 8LL) = v11;
    else
      *(_QWORD *)(v10 + 104) = v11;
    *(_QWORD *)(v10 + 112) = v11;
  }
  result = _Mtx_unlock((_Mtx_t)(v10 + 24));
  if ( v5 )
  {
LABEL_17:
    CurrentThreadId = Concurrency::details::platform::GetCurrentThreadId(v7);
    if ( !_InterlockedCompareExchange((volatile signed __int32 *)v8 + 4, CurrentThreadId, 0) )
    {
      (*(void (__fastcall **)(char *))(*(_QWORD *)v8 + 16LL))(v8);
      v14 = _InterlockedCompareExchange((volatile signed __int32 *)v8 + 4, 3, CurrentThreadId);
      if ( CurrentThreadId != v14 )
        CurrentThreadId = v14;
      if ( CurrentThreadId == 2 )
      {
        if ( _Mtx_lock(v9) )
        {
LABEL_22:
          std::_Throw_Cpp_error(5);
          __debugbreak();
        }
        if ( *((_DWORD *)v8 + 43) == 0x7FFFFFFF )
        {
          *((_DWORD *)v8 + 43) = 2147483646;
LABEL_25:
          std::_Throw_Cpp_error(6);
          __debugbreak();
        }
        v8[176] = 1;
        _Mtx_unlock(v9);
        _Cnd_broadcast((_Cnd_t)(v8 + 24));
      }
    }
    result = _InterlockedDecrement((volatile signed __int32 *)v8 + 2);
    if ( !result )
      result = (*(__int64 (__fastcall **)(char *))(*(_QWORD *)v8 + 8LL))(v8);
  }
  if ( v4 )
  {
    result = _InterlockedDecrement(v4 + 3);
    if ( !result )
      result = (*(__int64 (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v4 + 8LL))(v4);
  }
  v15 = (volatile signed __int32 *)a2[1];
  if ( v15 )
  {
    result = _InterlockedDecrement(v15 + 3);
    if ( !result )
      return (*(__int64 (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v15 + 8LL))(v15);
  }
  return result;
}

```

## disassembly

```asm
0x14001b7ec  mov     rax, rsp
0x14001b7ef  mov     [rax+18h], rbx
0x14001b7f3  mov     [rax+10h], rdx
0x14001b7f7  push    rbp
0x14001b7f8  push    rsi
0x14001b7f9  push    rdi
0x14001b7fa  push    r12
0x14001b7fc  push    r13
0x14001b7fe  push    r14
0x14001b800  push    r15
0x14001b802  sub     rsp, 30h
0x14001b806  mov     r15, rdx
0x14001b809  mov     rbp, rcx
0x14001b80c  xorps   xmm0, xmm0
0x14001b80f  movdqu  xmmword ptr [rax-48h], xmm0
0x14001b814  mov     rdi, [rdx+8]
0x14001b818  xor     r12d, r12d
0x14001b81b  test    rdi, rdi
0x14001b81e  jz      short loc_14001B831
0x14001b820  mov     rsi, [rdx]
0x14001b823  mov     [rax-48h], rsi
0x14001b827  mov     [rax-40h], rdi
0x14001b82b  lock inc dword ptr [rdi+0Ch]
0x14001b82f  jmp     short loc_14001B83B
0x14001b831  mov     rdi, [rsp+68h+var_40]
0x14001b836  mov     rsi, [rsp+68h+var_48]
0x14001b83b  mov     ecx, 0D0h; Size
0x14001b840  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x14001b845  mov     rbx, rax
0x14001b848  mov     [rsp+68h+arg_0], rax
0x14001b84d  lea     rax, ??_7_RefCounter@details@Concurrency@@6B@; const Concurrency::details::_RefCounter::`vftable'
0x14001b854  mov     [rbx], rax
0x14001b857  mov     dword ptr [rbx+8], 1
0x14001b85e  mov     dword ptr [rbx+10h], 3
0x14001b865  mov     [rbx+18h], r12
0x14001b869  mov     [rbx+20h], r12
0x14001b86d  xorps   xmm0, xmm0
0x14001b870  xor     eax, eax
0x14001b872  movups  xmmword ptr [rbx+28h], xmm0
0x14001b876  movups  xmmword ptr [rbx+38h], xmm0
0x14001b87a  movups  xmmword ptr [rbx+48h], xmm0
0x14001b87e  mov     [rbx+58h], rax
0x14001b882  lea     r14, [rbx+60h]
0x14001b886  mov     qword ptr [r14], 2
0x14001b88d  movups  xmmword ptr [r14+18h], xmm0
0x14001b892  movups  xmmword ptr [r14+28h], xmm0
0x14001b897  movups  xmmword ptr [r14+38h], xmm0
0x14001b89c  mov     [r14+8], r12
0x14001b8a0  mov     [r14+10h], r12
0x14001b8a4  mov     dword ptr [r14+48h], 0FFFFFFFFh
0x14001b8ac  mov     [r14+4Ch], r12d
0x14001b8b0  mov     [rbx+0B0h], r12b
0x14001b8b7  mov     [rbx+0B8h], r12
0x14001b8be  lea     rax, ??_7?$_CancellationTokenCallback@V_lambda_be3e5d9dce35d2c8dbfa8485373731d5_@@@details@Concurrency@@6B@; const Concurrency::details::_CancellationTokenCallback<_lambda_be3e5d9dce35d2c8dbfa8485373731d5_>::`vftable'
0x14001b8c5  mov     [rbx], rax
0x14001b8c8  mov     [rbx+0C0h], r12
0x14001b8cf  mov     [rbx+0C8h], r12
0x14001b8d6  test    rdi, rdi
0x14001b8d9  jz      short loc_14001B8ED
0x14001b8db  mov     [rbx+0C0h], rsi
0x14001b8e2  mov     [rbx+0C8h], rdi
0x14001b8e9  lock inc dword ptr [rdi+0Ch]
0x14001b8ed  mov     [rbp+80h], rbx
0x14001b8f4  mov     rsi, [rbp+78h]
0x14001b8f8  mov     eax, r12d
0x14001b8fb  xchg    eax, [rbx+10h]
0x14001b8fe  lock inc dword ptr [rbx+8]
0x14001b902  mov     [rbx+0B8h], rsi
0x14001b909  mov     eax, [rsi+10h]
0x14001b90c  nop
0x14001b90d  test    eax, eax
0x14001b90f  jnz     loc_14001B998
0x14001b915  lea     rbp, [rsi+18h]
0x14001b919  mov     [rsp+68h+arg_0], rbp
0x14001b91e  mov     rcx, rbp; _Mtx_t
0x14001b921  call    cs:__imp__Mtx_lock
0x14001b927  test    eax, eax
0x14001b929  jnz     loc_14001B9D9
0x14001b92f  mov     eax, [rbp+4Ch]
0x14001b932  cmp     eax, 7FFFFFFFh
0x14001b937  jnz     short loc_14001B943
0x14001b939  dec     eax
0x14001b93b  mov     [rbp+4Ch], eax
0x14001b93e  jmp     loc_14001B9F6
0x14001b943  mov     eax, [rsi+10h]
0x14001b946  nop
0x14001b947  test    eax, eax
0x14001b949  jz      short loc_14001B950
0x14001b94b  mov     r12b, 1
0x14001b94e  jmp     short loc_14001B986
0x14001b950  mov     ecx, 10h; Size
0x14001b955  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x14001b95a  mov     rcx, rax
0x14001b95d  mov     [rsp+68h+arg_0], rax
0x14001b962  mov     [rax], rbx
0x14001b965  mov     qword ptr [rax+8], 0
0x14001b96d  cmp     qword ptr [rsi+68h], 0
0x14001b972  jnz     short loc_14001B97A
0x14001b974  mov     [rsi+68h], rax
0x14001b978  jmp     short loc_14001B982
0x14001b97a  mov     rax, [rsi+70h]
0x14001b97e  mov     [rax+8], rcx
0x14001b982  mov     [rsi+70h], rcx
0x14001b986  mov     rcx, rbp; _Mtx_t
0x14001b989  call    cs:__imp__Mtx_unlock
0x14001b98f  test    r12b, r12b
0x14001b992  jz      loc_14001BA3B
0x14001b998  call    cs:__imp_?GetCurrentThreadId@platform@details@Concurrency@@YAJXZ; Concurrency::details::platform::GetCurrentThreadId(void)
0x14001b99e  mov     esi, eax
0x14001b9a0  xor     eax, eax
0x14001b9a2  lock cmpxchg [rbx+10h], esi
0x14001b9a7  jnz     short loc_14001BA1C
0x14001b9a9  mov     rcx, [rbx]
0x14001b9ac  mov     rax, [rcx+10h]
0x14001b9b0  mov     rcx, rbx
0x14001b9b3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001b9b8  mov     eax, esi
0x14001b9ba  mov     ecx, 3
0x14001b9bf  lock cmpxchg [rbx+10h], ecx
0x14001b9c4  cmovnz  esi, eax
0x14001b9c7  cmp     esi, 2
0x14001b9ca  jnz     short loc_14001BA1C
0x14001b9cc  mov     rcx, r14; _Mtx_t
0x14001b9cf  call    cs:__imp__Mtx_lock
0x14001b9d5  test    eax, eax
0x14001b9d7  jz      short loc_14001B9E5
0x14001b9d9  mov     ecx, 5
0x14001b9de  call    cs:__imp_?_Throw_Cpp_error@std@@YAXH@Z; std::_Throw_Cpp_error(int)
0x14001b9e4  int     3; Trap to Debugger
0x14001b9e5  mov     eax, [r14+4Ch]
0x14001b9e9  cmp     eax, 7FFFFFFFh
0x14001b9ee  jnz     short loc_14001BA02
0x14001b9f0  dec     eax
0x14001b9f2  mov     [r14+4Ch], eax
0x14001b9f6  mov     ecx, 6
0x14001b9fb  call    cs:__imp_?_Throw_Cpp_error@std@@YAXH@Z; std::_Throw_Cpp_error(int)
0x14001ba01  int     3; Trap to Debugger
0x14001ba02  mov     byte ptr [rbx+0B0h], 1
0x14001ba09  mov     rcx, r14; _Mtx_t
0x14001ba0c  call    cs:__imp__Mtx_unlock
0x14001ba12  lea     rcx, [rbx+18h]; _Cnd_t
0x14001ba16  call    cs:__imp__Cnd_broadcast
0x14001ba1c  or      esi, 0FFFFFFFFh
0x14001ba1f  mov     eax, esi
0x14001ba21  lock xadd [rbx+8], eax
0x14001ba26  add     eax, esi
0x14001ba28  jnz     short loc_14001BA3E
0x14001ba2a  mov     rax, [rbx]
0x14001ba2d  mov     rcx, rbx
0x14001ba30  mov     rax, [rax+8]
0x14001ba34  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001ba39  jmp     short loc_14001BA3E
0x14001ba3b  or      esi, 0FFFFFFFFh
0x14001ba3e  test    rdi, rdi
0x14001ba41  jz      short loc_14001BA5E
0x14001ba43  mov     eax, esi
0x14001ba45  lock xadd [rdi+0Ch], eax
0x14001ba4a  add     eax, esi
0x14001ba4c  jnz     short loc_14001BA5E
0x14001ba4e  mov     rax, [rdi]
0x14001ba51  mov     rcx, rdi
0x14001ba54  mov     rax, [rax+8]
0x14001ba58  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001ba5d  nop
0x14001ba5e  mov     rcx, [r15+8]
0x14001ba62  test    rcx, rcx
0x14001ba65  jz      short loc_14001BA7E
0x14001ba67  mov     eax, esi
0x14001ba69  lock xadd [rcx+0Ch], eax
0x14001ba6e  add     eax, esi
0x14001ba70  jnz     short loc_14001BA7E
0x14001ba72  mov     rax, [rcx]
0x14001ba75  mov     rax, [rax+8]
0x14001ba79  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001ba7e  mov     rbx, [rsp+68h+arg_10]
0x14001ba86  add     rsp, 30h
0x14001ba8a  pop     r15
0x14001ba8c  pop     r14
0x14001ba8e  pop     r13
0x14001ba90  pop     r12
0x14001ba92  pop     rdi
0x14001ba93  pop     rsi
0x14001ba94  pop     rbp
0x14001ba95  retn
```
