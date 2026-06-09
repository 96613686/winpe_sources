# Concurrency::details::_CancellationTokenState::_DeregisterCallback(Concurrency::details::_CancellationTokenRegistration *)

- ea: `0x180038f40`
- end: `0x18003909d`
- name: `?_DeregisterCallback@_CancellationTokenState@details@Concurrency@@QEAAXPEAV_CancellationTokenRegistration@23@@Z`
- size: `349`
- prototype: `void __fastcall(Concurrency::details::_CancellationTokenState *__hidden this, struct Concurrency::details::_CancellationTokenRegistration *)`
- caller_count: `2`
- callee_count: `3`
- tags: `file_ops, broker_com_uri`

## callers

- `0x18002b75c`
- `0x18002b7f8`

## callees

- `0x180007dc0`
- `0x180038f40`
- `0x180071010`

## import_xrefs

- `msvcp_win!_Cnd_wait` at `0x180039068`
- `msvcp_win!_Cnd_wait` at `0x180039068`
- `msvcp_win!_Mtx_unlock` at `0x180038ff6`
- `msvcp_win!_Mtx_unlock` at `0x18003907a`
- `msvcp_win!_Mtx_unlock` at `0x180038ff6`
- `msvcp_win!_Mtx_unlock` at `0x18003907a`
- `msvcp_win!_Mtx_lock` at `0x180038f62`
- `msvcp_win!_Mtx_lock` at `0x18003903b`
- `msvcp_win!_Mtx_lock` at `0x180038f62`
- `msvcp_win!_Mtx_lock` at `0x18003903b`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x18003905a`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x180039096`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x18003905a`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x180039096`
- `msvcp_win!?GetCurrentThreadId@platform@details@Concurrency@@YAJXZ` at `0x180039022`
- `msvcp_win!?GetCurrentThreadId@platform@details@Concurrency@@YAJXZ` at `0x180039022`

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
    operator delete(v5);
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
    JUMPOUT(0x18003909CLL);
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
0x180038f40  mov     [rsp+arg_10], rbx
0x180038f45  push    rbp
0x180038f46  push    rsi
0x180038f47  push    rdi
0x180038f48  push    r13
0x180038f4a  push    r14
0x180038f4c  sub     rsp, 30h
0x180038f50  mov     rdi, rdx
0x180038f53  mov     rsi, rcx
0x180038f56  lea     rbx, [rcx+18h]
0x180038f5a  mov     [rsp+58h+var_30], rbx
0x180038f5f  mov     rcx, rbx; _Mtx_t
0x180038f62  call    cs:__imp__Mtx_lock
0x180038f68  test    eax, eax
0x180038f6a  jnz     loc_180039091
0x180038f70  cmp     dword ptr [rbx+4Ch], 7FFFFFFFh
0x180038f77  jz      loc_18003904E
0x180038f7d  mov     rcx, [rsi+68h]; Block
0x180038f81  lea     ebp, [rax+2]
0x180038f84  lea     r13d, [rax+1]
0x180038f88  test    rcx, rcx
0x180038f8b  jnz     short loc_180038F92
0x180038f8d  mov     r14b, r13b
0x180038f90  jmp     short loc_180038FF3
0x180038f92  xor     r14b, r14b
0x180038f95  xor     eax, eax
0x180038f97  mov     rdx, [rcx+8]
0x180038f9b  cmp     [rcx], rdi
0x180038f9e  jz      short loc_180038FAD
0x180038fa0  mov     rax, rcx
0x180038fa3  mov     rcx, rdx
0x180038fa6  test    rdx, rdx
0x180038fa9  jnz     short loc_180038F97
0x180038fab  jmp     short loc_180038FD1
0x180038fad  test    rax, rax
0x180038fb0  jnz     short loc_180038FB8
0x180038fb2  mov     [rsi+68h], rdx
0x180038fb6  jmp     short loc_180038FBC
0x180038fb8  mov     [rax+8], rdx
0x180038fbc  cmp     qword ptr [rcx+8], 0
0x180038fc1  jnz     short loc_180038FC7
0x180038fc3  mov     [rsi+70h], rax
0x180038fc7  mov     edx, 10h
0x180038fcc  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180038fd1  mov     eax, ebp
0x180038fd3  xchg    eax, [rdi+10h]
0x180038fd6  or      eax, 0FFFFFFFFh
0x180038fd9  lock xadd [rdi+8], eax
0x180038fde  cmp     eax, r13d
0x180038fe1  jnz     short loc_180038FF3
0x180038fe3  mov     rax, [rdi]
0x180038fe6  mov     rcx, rdi
0x180038fe9  mov     rax, [rax+8]
0x180038fed  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180038ff2  nop
0x180038ff3  mov     rcx, rbx; _Mtx_t
0x180038ff6  call    cs:__imp__Mtx_unlock
0x180038ffc  test    r14b, r14b
0x180038fff  jz      short loc_180039080
0x180039001  xor     eax, eax
0x180039003  lock cmpxchg [rdi+10h], r13d
0x180039009  mov     ebx, eax
0x18003900b  jz      short loc_180039080
0x18003900d  mov     edx, eax
0x18003900f  test    eax, eax
0x180039011  jz      short loc_180039080
0x180039013  sub     edx, 1
0x180039016  jz      short loc_180039080
0x180039018  sub     edx, 1
0x18003901b  jz      short loc_180039080
0x18003901d  cmp     edx, 1
0x180039020  jz      short loc_180039080
0x180039022  call    cs:__imp_?GetCurrentThreadId@platform@details@Concurrency@@YAJXZ; Concurrency::details::platform::GetCurrentThreadId(void)
0x180039028  cmp     ebx, eax
0x18003902a  jz      short loc_180039080
0x18003902c  xchg    ebp, [rdi+10h]
0x18003902f  cmp     ebp, 3
0x180039032  jz      short loc_180039080
0x180039034  lea     rbx, [rdi+60h]
0x180039038  mov     rcx, rbx; _Mtx_t
0x18003903b  call    cs:__imp__Mtx_lock
0x180039041  test    eax, eax
0x180039043  jnz     short loc_180039091
0x180039045  cmp     dword ptr [rbx+4Ch], 7FFFFFFFh
0x18003904c  jnz     short loc_18003906E
0x18003904e  mov     dword ptr [rbx+4Ch], 7FFFFFFEh
0x180039055  mov     ecx, 6
0x18003905a  call    cs:__imp_?_Throw_Cpp_error@std@@YAXH@Z; std::_Throw_Cpp_error(int)
0x180039060  int     3; Trap to Debugger
0x180039061  mov     rdx, rbx; _Mtx_t
0x180039064  lea     rcx, [rdi+18h]; _Cnd_t
0x180039068  call    cs:__imp__Cnd_wait
0x18003906e  cmp     byte ptr [rdi+0B0h], 0
0x180039075  jz      short loc_180039061
0x180039077  mov     rcx, rbx; _Mtx_t
0x18003907a  call    cs:__imp__Mtx_unlock
0x180039080  mov     rbx, [rsp+58h+arg_10]
0x180039085  add     rsp, 30h
0x180039089  pop     r14
0x18003908b  pop     r13
0x18003908d  pop     rdi
0x18003908e  pop     rsi
0x18003908f  pop     rbp
0x180039090  retn
0x180039091  mov     ecx, 5
0x180039096  call    cs:__imp_?_Throw_Cpp_error@std@@YAXH@Z; std::_Throw_Cpp_error(int)
```
