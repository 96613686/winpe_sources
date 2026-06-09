# Concurrency::details::_CancellationTokenState::_DeregisterCallback(Concurrency::details::_CancellationTokenRegistration *)

- ea: `0x1800590d0`
- end: `0x180059262`
- name: `?_DeregisterCallback@_CancellationTokenState@details@Concurrency@@QEAAXPEAV_CancellationTokenRegistration@23@@Z`
- size: `402`
- prototype: `void __fastcall(Concurrency::details::_CancellationTokenState *__hidden this, struct Concurrency::details::_CancellationTokenRegistration *)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops, broker_com_uri`

## callers

- `0x1800568a0`

## callees

- `0x180003388`
- `0x180055f28`
- `0x1800590d0`
- `0x180086010`

## import_xrefs

- `msvcp_win!?GetCurrentThreadId@platform@details@Concurrency@@YAJXZ` at `0x1800591e7`
- `msvcp_win!?GetCurrentThreadId@platform@details@Concurrency@@YAJXZ` at `0x1800591e7`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x180059107`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x180059129`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x180059107`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x180059129`
- `msvcp_win!_Mtx_lock` at `0x1800590f2`
- `msvcp_win!_Mtx_lock` at `0x1800590f2`
- `msvcp_win!_Cnd_wait` at `0x180059220`
- `msvcp_win!_Cnd_wait` at `0x180059220`
- `msvcp_win!_Mtx_unlock` at `0x1800591b1`
- `msvcp_win!_Mtx_unlock` at `0x180059241`
- `msvcp_win!_Mtx_unlock` at `0x1800591b1`
- `msvcp_win!_Mtx_unlock` at `0x180059241`

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
  _Mtx_t v11[2]; // [rsp+20h] [rbp-48h] BYREF

  v4 = (char *)this + 24;
  v11[0] = (Concurrency::details::_CancellationTokenState *)((char *)this + 24);
  if ( _Mtx_lock((Concurrency::details::_CancellationTokenState *)((char *)this + 24)) )
  {
    std::_Throw_Cpp_error(5);
    __debugbreak();
  }
  if ( *((_DWORD *)v4 + 19) == 0x7FFFFFFF )
  {
    *((_DWORD *)v4 + 19) = 2147483646;
    std::_Throw_Cpp_error(6);
  }
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
        goto LABEL_17;
    }
    if ( v7 )
      v7[1] = v8;
    else
      *((_QWORD *)this + 13) = v8;
    if ( !v5[1] )
      *((_QWORD *)this + 14) = v7;
    operator delete(v5, 0x10u);
LABEL_17:
    _InterlockedExchange((volatile __int32 *)a2 + 4, 2);
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)a2 + 2, 0xFFFFFFFF) == 1 )
      (*(void (__fastcall **)(struct Concurrency::details::_CancellationTokenRegistration *))(*(_QWORD *)a2 + 8LL))(a2);
  }
  else
  {
    v6 = 1;
  }
  _Mtx_unlock((_Mtx_t)v4);
  if ( v6 )
  {
    v10 = _InterlockedCompareExchange((volatile signed __int32 *)a2 + 4, 1, 0);
    if ( v10 >= 2
      && v10 - 2 >= 2
      && v10 != Concurrency::details::platform::GetCurrentThreadId(v9)
      && _InterlockedExchange((volatile __int32 *)a2 + 4, 2) != 3 )
    {
      *(_OWORD *)v11 = 0;
      std::unique_lock<std::mutex>::unique_lock<std::mutex>(v11, (char *)a2 + 96);
      while ( !*((_BYTE *)a2 + 176) )
        _Cnd_wait((struct Concurrency::details::_CancellationTokenRegistration *)((char *)a2 + 24), v11[0]);
      if ( LOBYTE(v11[1]) )
        _Mtx_unlock(v11[0]);
    }
  }
}

```

## disassembly

```asm
0x1800590d0  mov     [rsp+arg_10], rbx
0x1800590d5  push    rbp
0x1800590d6  push    rsi
0x1800590d7  push    rdi
0x1800590d8  push    r12
0x1800590da  push    r14
0x1800590dc  sub     rsp, 40h
0x1800590e0  mov     rdi, rdx
0x1800590e3  mov     rsi, rcx
0x1800590e6  lea     rbx, [rcx+18h]
0x1800590ea  mov     [rsp+68h+var_48], rbx
0x1800590ef  mov     rcx, rbx; _Mtx_t
0x1800590f2  call    cs:__imp__Mtx_lock
0x1800590f9  nop     dword ptr [rax+rax+00h]
0x1800590fe  test    eax, eax
0x180059100  jz      short loc_180059114
0x180059102  mov     ecx, 5
0x180059107  call    cs:__imp_?_Throw_Cpp_error@std@@YAXH@Z; std::_Throw_Cpp_error(int)
0x18005910e  nop     dword ptr [rax+rax+00h]
0x180059113  int     3; Trap to Debugger
0x180059114  cmp     dword ptr [rbx+4Ch], 7FFFFFFFh
0x18005911b  jnz     short loc_180059136
0x18005911d  mov     dword ptr [rbx+4Ch], 7FFFFFFEh
0x180059124  mov     ecx, 6
0x180059129  call    cs:__imp_?_Throw_Cpp_error@std@@YAXH@Z; std::_Throw_Cpp_error(int)
0x180059130  nop     dword ptr [rax+rax+00h]
0x180059135  nop
0x180059136  mov     rcx, [rsi+68h]; void *
0x18005913a  mov     ebp, 2
0x18005913f  lea     r12d, [rbp-1]
0x180059143  test    rcx, rcx
0x180059146  jnz     short loc_18005914D
0x180059148  mov     r14b, r12b
0x18005914b  jmp     short loc_1800591AE
0x18005914d  xor     r14b, r14b
0x180059150  xor     eax, eax
0x180059152  mov     rdx, [rcx+8]
0x180059156  cmp     [rcx], rdi
0x180059159  jz      short loc_180059168
0x18005915b  mov     rax, rcx
0x18005915e  mov     rcx, rdx
0x180059161  test    rdx, rdx
0x180059164  jnz     short loc_180059152
0x180059166  jmp     short loc_18005918C
0x180059168  test    rax, rax
0x18005916b  jnz     short loc_180059173
0x18005916d  mov     [rsi+68h], rdx
0x180059171  jmp     short loc_180059177
0x180059173  mov     [rax+8], rdx
0x180059177  cmp     qword ptr [rcx+8], 0
0x18005917c  jnz     short loc_180059182
0x18005917e  mov     [rsi+70h], rax
0x180059182  mov     edx, 10h; unsigned __int64
0x180059187  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18005918c  mov     eax, ebp
0x18005918e  xchg    eax, [rdi+10h]
0x180059191  or      eax, 0FFFFFFFFh
0x180059194  lock xadd [rdi+8], eax
0x180059199  cmp     eax, r12d
0x18005919c  jnz     short loc_1800591AE
0x18005919e  mov     rax, [rdi]
0x1800591a1  mov     rcx, rdi
0x1800591a4  mov     rax, [rax+8]
0x1800591a8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800591ad  nop
0x1800591ae  mov     rcx, rbx; _Mtx_t
0x1800591b1  call    cs:__imp__Mtx_unlock
0x1800591b8  nop     dword ptr [rax+rax+00h]
0x1800591bd  test    r14b, r14b
0x1800591c0  jz      loc_18005924D
0x1800591c6  xor     eax, eax
0x1800591c8  lock cmpxchg [rdi+10h], r12d
0x1800591ce  mov     ebx, eax
0x1800591d0  jz      short loc_18005924D
0x1800591d2  mov     edx, eax
0x1800591d4  test    eax, eax
0x1800591d6  jz      short loc_18005924D
0x1800591d8  sub     edx, 1
0x1800591db  jz      short loc_18005924D
0x1800591dd  sub     edx, 1
0x1800591e0  jz      short loc_18005924D
0x1800591e2  cmp     edx, 1
0x1800591e5  jz      short loc_18005924D
0x1800591e7  call    cs:__imp_?GetCurrentThreadId@platform@details@Concurrency@@YAJXZ; Concurrency::details::platform::GetCurrentThreadId(void)
0x1800591ee  nop     dword ptr [rax+rax+00h]
0x1800591f3  cmp     ebx, eax
0x1800591f5  jz      short loc_18005924D
0x1800591f7  xchg    ebp, [rdi+10h]
0x1800591fa  cmp     ebp, 3
0x1800591fd  jz      short loc_18005924D
0x1800591ff  xorps   xmm0, xmm0
0x180059202  movups  xmmword ptr [rsp+68h+var_48], xmm0
0x180059207  lea     rdx, [rdi+60h]
0x18005920b  lea     rcx, [rsp+68h+var_48]
0x180059210  call    ??0?$unique_lock@Vmutex@std@@@std@@QEAA@AEAVmutex@1@@Z; std::unique_lock<std::mutex>::unique_lock<std::mutex>(std::mutex &)
0x180059215  jmp     short loc_18005922C
0x180059217  mov     rdx, [rsp+68h+var_48]; _Mtx_t
0x18005921c  lea     rcx, [rdi+18h]; _Cnd_t
0x180059220  call    cs:__imp__Cnd_wait
0x180059227  nop     dword ptr [rax+rax+00h]
0x18005922c  cmp     byte ptr [rdi+0B0h], 0
0x180059233  jz      short loc_180059217
0x180059235  cmp     byte ptr [rsp+68h+var_48+8], 0
0x18005923a  jz      short loc_18005924D
0x18005923c  mov     rcx, [rsp+68h+var_48]; _Mtx_t
0x180059241  call    cs:__imp__Mtx_unlock
0x180059248  nop     dword ptr [rax+rax+00h]
0x18005924d  mov     rbx, [rsp+68h+arg_10]
0x180059255  add     rsp, 40h
0x180059259  pop     r14
0x18005925b  pop     r12
0x18005925d  pop     rdi
0x18005925e  pop     rsi
0x18005925f  pop     rbp
0x180059260  retn
```
