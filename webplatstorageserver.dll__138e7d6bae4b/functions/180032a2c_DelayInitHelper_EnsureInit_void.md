# DelayInitHelper::EnsureInit(void)

- ea: `0x180032a2c`
- end: `0x180032b45`
- name: `?EnsureInit@DelayInitHelper@@QEBAXXZ`
- size: `281`
- prototype: `void __fastcall(DelayInitHelper *__hidden this)`
- caller_count: `11`
- callee_count: `2`
- tags: ``

## callers

- `0x1800328a4`
- `0x1800339c0`
- `0x1800340f8`
- `0x180037100`
- `0x18005b014`
- `0x1800617e0`
- `0x180070098`
- `0x180075c60`
- `0x180092754`
- `0x1800a0418`
- `0x1800a1500`

## callees

- `0x180032a2c`
- `0x1800c6010`

## import_xrefs

- `msvcp_win!_Unlock_shared_ptr_spin_lock` at `0x180032a6c`
- `msvcp_win!_Unlock_shared_ptr_spin_lock` at `0x180032a6c`
- `msvcp_win!_Lock_shared_ptr_spin_lock` at `0x180032a41`
- `msvcp_win!_Lock_shared_ptr_spin_lock` at `0x180032a41`
- `msvcp_win!?__ExceptionPtrRethrow@@YAXPEBX@Z` at `0x180032b3e`
- `msvcp_win!?__ExceptionPtrRethrow@@YAXPEBX@Z` at `0x180032b3e`
- `msvcp_win!?__ExceptionPtrToBool@@YA_NPEBX@Z` at `0x180032ab6`
- `msvcp_win!?__ExceptionPtrToBool@@YA_NPEBX@Z` at `0x180032ab6`
- `msvcp_win!?__ExceptionPtrCreate@@YAXPEAX@Z` at `0x180032a94`
- `msvcp_win!?__ExceptionPtrCreate@@YAXPEAX@Z` at `0x180032a94`
- `msvcp_win!?__ExceptionPtrCopy@@YAXPEAXPEBX@Z` at `0x180032b2c`
- `msvcp_win!?__ExceptionPtrCopy@@YAXPEAXPEBX@Z` at `0x180032b2c`
- `msvcp_win!?__ExceptionPtrDestroy@@YAXPEAX@Z` at `0x180032ac4`
- `msvcp_win!?__ExceptionPtrDestroy@@YAXPEAX@Z` at `0x180032ac4`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x180032aac`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x180032aac`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
void __fastcall DelayInitHelper::EnsureInit(DelayInitHelper *this)
{
  __int64 v2; // rax
  union _RTL_RUN_ONCE *v3; // rdi
  volatile signed __int32 *v4; // rbx
  PINIT_ONCE InitOnce[2]; // [rsp+20h] [rbp-40h] BYREF
  __int128 v6; // [rsp+30h] [rbp-30h] BYREF
  _QWORD Parameter[2]; // [rsp+40h] [rbp-20h] BYREF
  __int128 v8; // [rsp+50h] [rbp-10h] BYREF

  _Lock_shared_ptr_spin_lock();
  *(_OWORD *)InitOnce = 0;
  v2 = *((_QWORD *)this + 3);
  if ( v2 )
    _InterlockedIncrement((volatile signed __int32 *)(v2 + 8));
  InitOnce[0] = *((PINIT_ONCE *)this + 2);
  InitOnce[1] = *((PINIT_ONCE *)this + 3);
  _Unlock_shared_ptr_spin_lock();
  v3 = InitOnce[0];
  if ( InitOnce[0] )
  {
    Parameter[0] = InitOnce;
    Parameter[1] = this;
    v8 = 0;
    __ExceptionPtrCreate(&v8);
    InitOnceExecuteOnce(v3, lambda_60775d1107346de3b9cc64a0a0339a26_::_lambda_invoker_cdecl_, Parameter, 0);
    if ( __ExceptionPtrToBool(&v8) )
    {
      v6 = 0;
      __ExceptionPtrCopy(&v6, &v8);
      __ExceptionPtrRethrow(&v6);
      JUMPOUT(0x180032B44LL);
    }
    __ExceptionPtrDestroy(&v8);
  }
  v4 = (volatile signed __int32 *)InitOnce[1];
  if ( InitOnce[1] && _InterlockedExchangeAdd((volatile signed __int32 *)&InitOnce[1][1], 0xFFFFFFFF) == 1 )
  {
    (**(void (__fastcall ***)(volatile signed __int32 *))v4)(v4);
    if ( !_InterlockedDecrement(v4 + 3) )
      (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v4 + 8LL))(v4);
  }
}

```

## disassembly

```asm
0x180032a2c  mov     [rsp-8+arg_8], rbx
0x180032a31  mov     [rsp-8+arg_10], rdi
0x180032a36  push    rbp
0x180032a37  mov     rbp, rsp
0x180032a3a  sub     rsp, 60h
0x180032a3e  mov     rbx, rcx
0x180032a41  call    cs:__imp__Lock_shared_ptr_spin_lock
0x180032a47  xorps   xmm0, xmm0
0x180032a4a  movdqu  xmmword ptr [rbp+InitOnce], xmm0
0x180032a4f  mov     rax, [rbx+18h]
0x180032a53  test    rax, rax
0x180032a56  jz      short loc_180032A5C
0x180032a58  lock inc dword ptr [rax+8]
0x180032a5c  mov     rax, [rbx+10h]
0x180032a60  mov     [rbp+InitOnce], rax
0x180032a64  mov     rax, [rbx+18h]
0x180032a68  mov     [rbp+InitOnce+8], rax
0x180032a6c  call    cs:__imp__Unlock_shared_ptr_spin_lock
0x180032a72  nop
0x180032a73  mov     rdi, [rbp+InitOnce]
0x180032a77  test    rdi, rdi
0x180032a7a  jz      short loc_180032ACB
0x180032a7c  lea     rax, [rbp+InitOnce]
0x180032a80  mov     [rbp+Parameter], rax
0x180032a84  mov     [rbp+var_18], rbx
0x180032a88  xorps   xmm0, xmm0
0x180032a8b  movdqu  [rbp+var_10], xmm0
0x180032a90  lea     rcx, [rbp+var_10]
0x180032a94  call    cs:__imp_?__ExceptionPtrCreate@@YAXPEAX@Z; __ExceptionPtrCreate(void *)
0x180032a9a  nop
0x180032a9b  xor     r9d, r9d; Context
0x180032a9e  lea     r8, [rbp+Parameter]; Parameter
0x180032aa2  lea     rdx, _lambda_60775d1107346de3b9cc64a0a0339a26____lambda_invoker_cdecl_; InitFn
0x180032aa9  mov     rcx, rdi; InitOnce
0x180032aac  call    cs:__imp_InitOnceExecuteOnce
0x180032ab2  lea     rcx, [rbp+var_10]
0x180032ab6  call    cs:__imp_?__ExceptionPtrToBool@@YA_NPEBX@Z; __ExceptionPtrToBool(void const *)
0x180032abc  test    al, al
0x180032abe  jnz     short loc_180032B1C
0x180032ac0  lea     rcx, [rbp+var_10]
0x180032ac4  call    cs:__imp_?__ExceptionPtrDestroy@@YAXPEAX@Z; __ExceptionPtrDestroy(void *)
0x180032aca  nop
0x180032acb  mov     rbx, [rbp+InitOnce+8]
0x180032acf  test    rbx, rbx
0x180032ad2  jz      short loc_180032B0A
0x180032ad4  or      edi, 0FFFFFFFFh
0x180032ad7  mov     eax, edi
0x180032ad9  lock xadd [rbx+8], eax
0x180032ade  add     eax, edi
0x180032ae0  jnz     short loc_180032B0A
0x180032ae2  mov     rax, [rbx]
0x180032ae5  mov     rcx, rbx
0x180032ae8  mov     rax, [rax]
0x180032aeb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180032af0  mov     eax, edi
0x180032af2  lock xadd [rbx+0Ch], eax
0x180032af7  add     eax, edi
0x180032af9  jnz     short loc_180032B0A
0x180032afb  mov     rax, [rbx]
0x180032afe  mov     rcx, rbx
0x180032b01  mov     rax, [rax+8]
0x180032b05  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180032b0a  lea     r11, [rsp+60h+var_s0]
0x180032b0f  mov     rbx, [r11+18h]
0x180032b13  mov     rdi, [r11+20h]
0x180032b17  mov     rsp, r11
0x180032b1a  pop     rbp
0x180032b1b  retn
0x180032b1c  xorps   xmm0, xmm0
0x180032b1f  movdqu  [rbp+var_30], xmm0
0x180032b24  lea     rdx, [rbp+var_10]
0x180032b28  lea     rcx, [rbp+var_30]
0x180032b2c  call    cs:__imp_?__ExceptionPtrCopy@@YAXPEAXPEBX@Z; __ExceptionPtrCopy(void *,void const *)
0x180032b32  lea     rax, [rbp+var_30]
0x180032b36  mov     [rbp+arg_0], rax
0x180032b3a  lea     rcx, [rbp+var_30]
0x180032b3e  call    cs:__imp_?__ExceptionPtrRethrow@@YAXPEBX@Z; __ExceptionPtrRethrow(void const *)
```
