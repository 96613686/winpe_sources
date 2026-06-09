# DelayInitObject<CacheStorageTables>::Get(void)

- ea: `0x18003f4b4`
- end: `0x18003f5c5`
- name: `?Get@?$DelayInitObject@UCacheStorageTables@@@@QEBAAEBUCacheStorageTables@@XZ`
- size: `273`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x180038078`
- `0x18003d044`
- `0x18003e350`
- `0x18007e900`

## callees

- `0x18003f4b4`
- `0x1800c6010`

## import_xrefs

- `msvcp_win!_Unlock_shared_ptr_spin_lock` at `0x18003f4f1`
- `msvcp_win!_Unlock_shared_ptr_spin_lock` at `0x18003f4f1`
- `msvcp_win!_Lock_shared_ptr_spin_lock` at `0x18003f4c6`
- `msvcp_win!_Lock_shared_ptr_spin_lock` at `0x18003f4c6`
- `msvcp_win!?__ExceptionPtrRethrow@@YAXPEBX@Z` at `0x18003f5be`
- `msvcp_win!?__ExceptionPtrRethrow@@YAXPEBX@Z` at `0x18003f5be`
- `msvcp_win!?__ExceptionPtrToBool@@YA_NPEBX@Z` at `0x18003f53b`
- `msvcp_win!?__ExceptionPtrToBool@@YA_NPEBX@Z` at `0x18003f53b`
- `msvcp_win!?__ExceptionPtrCreate@@YAXPEAX@Z` at `0x18003f519`
- `msvcp_win!?__ExceptionPtrCreate@@YAXPEAX@Z` at `0x18003f519`
- `msvcp_win!?__ExceptionPtrCopy@@YAXPEAXPEBX@Z` at `0x18003f5ac`
- `msvcp_win!?__ExceptionPtrCopy@@YAXPEAXPEBX@Z` at `0x18003f5ac`
- `msvcp_win!?__ExceptionPtrDestroy@@YAXPEAX@Z` at `0x18003f549`
- `msvcp_win!?__ExceptionPtrDestroy@@YAXPEAX@Z` at `0x18003f549`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x18003f531`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x18003f531`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 *__fastcall DelayInitObject<CacheStorageTables>::Get(__int64 *a1)
{
  __int64 v2; // rbx
  __int64 v3; // rax
  union _RTL_RUN_ONCE *v4; // rsi
  volatile signed __int32 *v5; // rbx
  PINIT_ONCE InitOnce[2]; // [rsp+20h] [rbp-48h] BYREF
  __int128 v8; // [rsp+30h] [rbp-38h] BYREF
  _QWORD Parameter[2]; // [rsp+40h] [rbp-28h] BYREF
  __int128 v10; // [rsp+50h] [rbp-18h] BYREF

  v2 = *a1;
  _Lock_shared_ptr_spin_lock();
  *(_OWORD *)InitOnce = 0;
  v3 = *(_QWORD *)(v2 + 24);
  if ( v3 )
    _InterlockedIncrement((volatile signed __int32 *)(v3 + 8));
  InitOnce[0] = *(PINIT_ONCE *)(v2 + 16);
  InitOnce[1] = *(PINIT_ONCE *)(v2 + 24);
  _Unlock_shared_ptr_spin_lock();
  v4 = InitOnce[0];
  if ( InitOnce[0] )
  {
    Parameter[0] = InitOnce;
    Parameter[1] = v2;
    v10 = 0;
    __ExceptionPtrCreate(&v10);
    InitOnceExecuteOnce(v4, lambda_60775d1107346de3b9cc64a0a0339a26_::_lambda_invoker_cdecl_, Parameter, 0);
    if ( __ExceptionPtrToBool(&v10) )
    {
      v8 = 0;
      __ExceptionPtrCopy(&v8, &v10);
      __ExceptionPtrRethrow(&v8);
      JUMPOUT(0x18003F5C4LL);
    }
    __ExceptionPtrDestroy(&v10);
  }
  v5 = (volatile signed __int32 *)InitOnce[1];
  if ( InitOnce[1] )
  {
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)&InitOnce[1][1], 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v5)(v5);
      if ( _InterlockedExchangeAdd(v5 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v5 + 8LL))(v5);
    }
  }
  return a1 + 2;
}

```

## disassembly

```asm
0x18003f4b4  push    rbp
0x18003f4b6  push    rbx
0x18003f4b7  push    rsi
0x18003f4b8  push    rdi
0x18003f4b9  mov     rbp, rsp
0x18003f4bc  sub     rsp, 68h
0x18003f4c0  mov     rdi, rcx
0x18003f4c3  mov     rbx, [rcx]
0x18003f4c6  call    cs:__imp__Lock_shared_ptr_spin_lock
0x18003f4cc  xorps   xmm0, xmm0
0x18003f4cf  movdqu  xmmword ptr [rbp+InitOnce], xmm0
0x18003f4d4  mov     rax, [rbx+18h]
0x18003f4d8  test    rax, rax
0x18003f4db  jz      short loc_18003F4E1
0x18003f4dd  lock inc dword ptr [rax+8]
0x18003f4e1  mov     rax, [rbx+10h]
0x18003f4e5  mov     [rbp+InitOnce], rax
0x18003f4e9  mov     rax, [rbx+18h]
0x18003f4ed  mov     [rbp+InitOnce+8], rax
0x18003f4f1  call    cs:__imp__Unlock_shared_ptr_spin_lock
0x18003f4f7  nop
0x18003f4f8  mov     rsi, [rbp+InitOnce]
0x18003f4fc  test    rsi, rsi
0x18003f4ff  jz      short loc_18003F550
0x18003f501  lea     rax, [rbp+InitOnce]
0x18003f505  mov     [rbp+Parameter], rax
0x18003f509  mov     [rbp+var_20], rbx
0x18003f50d  xorps   xmm0, xmm0
0x18003f510  movdqu  [rbp+var_18], xmm0
0x18003f515  lea     rcx, [rbp+var_18]
0x18003f519  call    cs:__imp_?__ExceptionPtrCreate@@YAXPEAX@Z; __ExceptionPtrCreate(void *)
0x18003f51f  nop
0x18003f520  xor     r9d, r9d; Context
0x18003f523  lea     r8, [rbp+Parameter]; Parameter
0x18003f527  lea     rdx, _lambda_60775d1107346de3b9cc64a0a0339a26____lambda_invoker_cdecl_; InitFn
0x18003f52e  mov     rcx, rsi; InitOnce
0x18003f531  call    cs:__imp_InitOnceExecuteOnce
0x18003f537  lea     rcx, [rbp+var_18]
0x18003f53b  call    cs:__imp_?__ExceptionPtrToBool@@YA_NPEBX@Z; __ExceptionPtrToBool(void const *)
0x18003f541  test    al, al
0x18003f543  jnz     short loc_18003F59C
0x18003f545  lea     rcx, [rbp+var_18]
0x18003f549  call    cs:__imp_?__ExceptionPtrDestroy@@YAXPEAX@Z; __ExceptionPtrDestroy(void *)
0x18003f54f  nop
0x18003f550  mov     rbx, [rbp+InitOnce+8]
0x18003f554  test    rbx, rbx
0x18003f557  jz      short loc_18003F58F
0x18003f559  or      esi, 0FFFFFFFFh
0x18003f55c  mov     eax, esi
0x18003f55e  lock xadd [rbx+8], eax
0x18003f563  add     eax, esi
0x18003f565  jnz     short loc_18003F58F
0x18003f567  mov     rax, [rbx]
0x18003f56a  mov     rcx, rbx
0x18003f56d  mov     rax, [rax]
0x18003f570  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003f575  mov     eax, esi
0x18003f577  lock xadd [rbx+0Ch], eax
0x18003f57c  add     eax, esi
0x18003f57e  jnz     short loc_18003F58F
0x18003f580  mov     rax, [rbx]
0x18003f583  mov     rcx, rbx
0x18003f586  mov     rax, [rax+8]
0x18003f58a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003f58f  lea     rax, [rdi+10h]
0x18003f593  add     rsp, 68h
0x18003f597  pop     rdi
0x18003f598  pop     rsi
0x18003f599  pop     rbx
0x18003f59a  pop     rbp
0x18003f59b  retn
0x18003f59c  xorps   xmm0, xmm0
0x18003f59f  movdqu  [rbp+var_38], xmm0
0x18003f5a4  lea     rdx, [rbp+var_18]
0x18003f5a8  lea     rcx, [rbp+var_38]
0x18003f5ac  call    cs:__imp_?__ExceptionPtrCopy@@YAXPEAXPEBX@Z; __ExceptionPtrCopy(void *,void const *)
0x18003f5b2  lea     rax, [rbp+var_38]
0x18003f5b6  mov     [rbp+arg_0], rax
0x18003f5ba  lea     rcx, [rbp+var_38]
0x18003f5be  call    cs:__imp_?__ExceptionPtrRethrow@@YAXPEBX@Z; __ExceptionPtrRethrow(void const *)
```
