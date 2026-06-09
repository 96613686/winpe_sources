# Concurrency::details::_CancellationTokenState::_DeregisterCallback(Concurrency::details::_CancellationTokenRegistration *)

- ea: `0x14001ad68`
- end: `0x14001aec5`
- name: `?_DeregisterCallback@_CancellationTokenState@details@Concurrency@@QEAAXPEAV_CancellationTokenRegistration@23@@Z`
- size: `349`
- prototype: `void __fastcall(Concurrency::details::_CancellationTokenState *__hidden this, struct Concurrency::details::_CancellationTokenRegistration *)`
- caller_count: `2`
- callee_count: `3`
- tags: `file_ops, broker_com_uri`

## callers

- `0x14000cb3c`
- `0x140047dc8`

## callees

- `0x140005554`
- `0x14001ad68`
- `0x1400a8010`

## import_xrefs

- `msvcp_win!?GetCurrentThreadId@platform@details@Concurrency@@YAJXZ` at `0x14001ae4a`
- `msvcp_win!?GetCurrentThreadId@platform@details@Concurrency@@YAJXZ` at `0x14001ae4a`
- `msvcp_win!_Mtx_unlock` at `0x14001ae1e`
- `msvcp_win!_Mtx_unlock` at `0x14001aea2`
- `msvcp_win!_Mtx_unlock` at `0x14001ae1e`
- `msvcp_win!_Mtx_unlock` at `0x14001aea2`
- `msvcp_win!_Cnd_wait` at `0x14001ae90`
- `msvcp_win!_Cnd_wait` at `0x14001ae90`
- `msvcp_win!_Mtx_lock` at `0x14001ad8a`
- `msvcp_win!_Mtx_lock` at `0x14001ae63`
- `msvcp_win!_Mtx_lock` at `0x14001ad8a`
- `msvcp_win!_Mtx_lock` at `0x14001ae63`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x14001ae82`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x14001aebe`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x14001ae82`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x14001aebe`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall Concurrency::details::_CancellationTokenState::_DeregisterCallback(
        Concurrency::details::_CancellationTokenState *this,
        struct Concurrency::details::_CancellationTokenRegistration *a2)
{
  char *v4; // rbx
  _QWORD *v5; // rcx
  char v6; // r14
  _QWORD *v7; // rax
  __int64 v8; // rdx
  Concurrency::details::platform *v9; // rcx
  unsigned __int32 v10; // eax

  v4 = (char *)this + 24;
  if ( _Mtx_lock((Concurrency::details::_CancellationTokenState *)((char *)this + 24)) )
    goto LABEL_29;
  if ( *((_DWORD *)v4 + 19) == 0x7FFFFFFF )
    goto LABEL_24;
  v5 = (_QWORD *)*((_QWORD *)this + 13);
  if ( v5 )
  {
    v6 = 0;
    v7 = 0;
    while ( 1 )
    {
      v8 = v5[1];
      if ( (struct Concurrency::details::_CancellationTokenRegistration *)*v5 == a2 )
        break;
      v7 = v5;
      v5 = (_QWORD *)v5[1];
      if ( !v8 )
        goto LABEL_15;
    }
    if ( v7 )
      v7[1] = v8;
    else
      *((_QWORD *)this + 13) = v8;
    if ( !v5[1] )
      *((_QWORD *)this + 14) = v7;
    operator delete(v5, 0x10u);
LABEL_15:
    _InterlockedExchange((volatile __int32 *)a2 + 4, 2);
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)a2 + 2, 0xFFFFFFFF) == 1 )
      (*(void (__fastcall **)(struct Concurrency::details::_CancellationTokenRegistration *))(*(_QWORD *)a2 + 8LL))(a2);
  }
  else
  {
    v6 = 1;
  }
  _Mtx_unlock((_Mtx_t)v4);
  if ( !v6 )
    return;
  v10 = _InterlockedCompareExchange((volatile signed __int32 *)a2 + 4, 1, 0);
  if ( v10 < 2
    || v10 - 2 < 2
    || v10 == Concurrency::details::platform::GetCurrentThreadId(v9)
    || _InterlockedExchange((volatile __int32 *)a2 + 4, 2) == 3 )
  {
    return;
  }
  v4 = (char *)a2 + 96;
  if ( _Mtx_lock((struct Concurrency::details::_CancellationTokenRegistration *)((char *)a2 + 96)) )
  {
LABEL_29:
    std::_Throw_Cpp_error(5);
    JUMPOUT(0x14001AEC4LL);
  }
  if ( *((_DWORD *)a2 + 43) == 0x7FFFFFFF )
  {
LABEL_24:
    *((_DWORD *)v4 + 19) = 2147483646;
    std::_Throw_Cpp_error(6);
    __debugbreak();
  }
  while ( !*((_BYTE *)a2 + 176) )
    _Cnd_wait(
      (struct Concurrency::details::_CancellationTokenRegistration *)((char *)a2 + 24),
      (struct Concurrency::details::_CancellationTokenRegistration *)((char *)a2 + 96));
  _Mtx_unlock((struct Concurrency::details::_CancellationTokenRegistration *)((char *)a2 + 96));
}

```

## disassembly

```asm
0x14001ad68  mov     [rsp+arg_8], rbx
0x14001ad6d  push    rbp
0x14001ad6e  push    rsi
0x14001ad6f  push    rdi
0x14001ad70  push    r13
0x14001ad72  push    r14
0x14001ad74  sub     rsp, 20h
0x14001ad78  mov     rdi, rdx
0x14001ad7b  mov     rsi, rcx
0x14001ad7e  lea     rbx, [rcx+18h]
0x14001ad82  mov     [rsp+48h+arg_10], rbx
0x14001ad87  mov     rcx, rbx; _Mtx_t
0x14001ad8a  call    cs:__imp__Mtx_lock
0x14001ad90  test    eax, eax
0x14001ad92  jnz     loc_14001AEB9
0x14001ad98  cmp     dword ptr [rbx+4Ch], 7FFFFFFFh
0x14001ad9f  jz      loc_14001AE76
0x14001ada5  mov     rcx, [rsi+68h]; void *
0x14001ada9  lea     ebp, [rax+2]
0x14001adac  lea     r13d, [rax+1]
0x14001adb0  test    rcx, rcx
0x14001adb3  jnz     short loc_14001ADBA
0x14001adb5  mov     r14b, r13b
0x14001adb8  jmp     short loc_14001AE1B
0x14001adba  xor     r14b, r14b
0x14001adbd  xor     eax, eax
0x14001adbf  mov     rdx, [rcx+8]
0x14001adc3  cmp     [rcx], rdi
0x14001adc6  jz      short loc_14001ADD5
0x14001adc8  mov     rax, rcx
0x14001adcb  mov     rcx, rdx
0x14001adce  test    rdx, rdx
0x14001add1  jnz     short loc_14001ADBF
0x14001add3  jmp     short loc_14001ADF9
0x14001add5  test    rax, rax
0x14001add8  jnz     short loc_14001ADE0
0x14001adda  mov     [rsi+68h], rdx
0x14001adde  jmp     short loc_14001ADE4
0x14001ade0  mov     [rax+8], rdx
0x14001ade4  cmp     qword ptr [rcx+8], 0
0x14001ade9  jnz     short loc_14001ADEF
0x14001adeb  mov     [rsi+70h], rax
0x14001adef  mov     edx, 10h; unsigned __int64
0x14001adf4  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x14001adf9  mov     eax, ebp
0x14001adfb  xchg    eax, [rdi+10h]
0x14001adfe  or      eax, 0FFFFFFFFh
0x14001ae01  lock xadd [rdi+8], eax
0x14001ae06  cmp     eax, r13d
0x14001ae09  jnz     short loc_14001AE1B
0x14001ae0b  mov     rax, [rdi]
0x14001ae0e  mov     rcx, rdi
0x14001ae11  mov     rax, [rax+8]
0x14001ae15  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001ae1a  nop
0x14001ae1b  mov     rcx, rbx; _Mtx_t
0x14001ae1e  call    cs:__imp__Mtx_unlock
0x14001ae24  test    r14b, r14b
0x14001ae27  jz      short loc_14001AEA8
0x14001ae29  xor     eax, eax
0x14001ae2b  lock cmpxchg [rdi+10h], r13d
0x14001ae31  mov     ebx, eax
0x14001ae33  jz      short loc_14001AEA8
0x14001ae35  mov     edx, eax
0x14001ae37  test    eax, eax
0x14001ae39  jz      short loc_14001AEA8
0x14001ae3b  sub     edx, 1
0x14001ae3e  jz      short loc_14001AEA8
0x14001ae40  sub     edx, 1
0x14001ae43  jz      short loc_14001AEA8
0x14001ae45  cmp     edx, 1
0x14001ae48  jz      short loc_14001AEA8
0x14001ae4a  call    cs:__imp_?GetCurrentThreadId@platform@details@Concurrency@@YAJXZ; Concurrency::details::platform::GetCurrentThreadId(void)
0x14001ae50  cmp     ebx, eax
0x14001ae52  jz      short loc_14001AEA8
0x14001ae54  xchg    ebp, [rdi+10h]
0x14001ae57  cmp     ebp, 3
0x14001ae5a  jz      short loc_14001AEA8
0x14001ae5c  lea     rbx, [rdi+60h]
0x14001ae60  mov     rcx, rbx; _Mtx_t
0x14001ae63  call    cs:__imp__Mtx_lock
0x14001ae69  test    eax, eax
0x14001ae6b  jnz     short loc_14001AEB9
0x14001ae6d  cmp     dword ptr [rbx+4Ch], 7FFFFFFFh
0x14001ae74  jnz     short loc_14001AE96
0x14001ae76  mov     dword ptr [rbx+4Ch], 7FFFFFFEh
0x14001ae7d  mov     ecx, 6
0x14001ae82  call    cs:__imp_?_Throw_Cpp_error@std@@YAXH@Z; std::_Throw_Cpp_error(int)
0x14001ae88  int     3; Trap to Debugger
0x14001ae89  mov     rdx, rbx; _Mtx_t
0x14001ae8c  lea     rcx, [rdi+18h]; _Cnd_t
0x14001ae90  call    cs:__imp__Cnd_wait
0x14001ae96  cmp     byte ptr [rdi+0B0h], 0
0x14001ae9d  jz      short loc_14001AE89
0x14001ae9f  mov     rcx, rbx; _Mtx_t
0x14001aea2  call    cs:__imp__Mtx_unlock
0x14001aea8  mov     rbx, [rsp+48h+arg_8]
0x14001aead  add     rsp, 20h
0x14001aeb1  pop     r14
0x14001aeb3  pop     r13
0x14001aeb5  pop     rdi
0x14001aeb6  pop     rsi
0x14001aeb7  pop     rbp
0x14001aeb8  retn
0x14001aeb9  mov     ecx, 5
0x14001aebe  call    cs:__imp_?_Throw_Cpp_error@std@@YAXH@Z; std::_Throw_Cpp_error(int)
```
