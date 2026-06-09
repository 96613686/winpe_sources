# Concurrency::details::_CancellationTokenState::_RegisterCallback(Concurrency::details::_CancellationTokenRegistration *)

- ea: `0x140035c78`
- end: `0x140035d73`
- name: `?_RegisterCallback@_CancellationTokenState@details@Concurrency@@QEAAXPEAV_CancellationTokenRegistration@23@@Z`
- size: `251`
- prototype: `void(Concurrency::details::_CancellationTokenState *__hidden this, struct Concurrency::details::_CancellationTokenRegistration *)`
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x140035d7c`

## callees

- `0x140006e8c`
- `0x1400198d0`
- `0x140025f70`
- `0x140035c78`
- `0x140035dfc`
- `0x140068010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140035d07`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140035d07`
- `api-ms-win-core-synch-l1-2-0!WakeAllConditionVariable` at `0x140035d58`
- `api-ms-win-core-synch-l1-2-0!WakeAllConditionVariable` at `0x140035d58`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall Concurrency::details::_CancellationTokenState::_RegisterCallback(
        Concurrency::details::_CancellationTokenState *this,
        struct Concurrency::details::_CancellationTokenRegistration *a2)
{
  std::_Mutex_base *v4; // rsi
  char v5; // bp
  _QWORD *v6; // rax
  DWORD CurrentThreadId; // ebx
  signed __int32 v8; // eax

  _InterlockedExchange((volatile __int32 *)a2 + 4, 0);
  _InterlockedIncrement((volatile signed __int32 *)a2 + 2);
  *((_QWORD *)a2 + 23) = this;
  if ( *((_DWORD *)this + 4) )
    goto LABEL_9;
  v4 = (Concurrency::details::_CancellationTokenState *)((char *)this + 24);
  std::_Mutex_base::lock((Concurrency::details::_CancellationTokenState *)((char *)this + 24));
  if ( *((_DWORD *)this + 4) )
  {
    v5 = 1;
  }
  else
  {
    v5 = 0;
    v6 = operator new(0x10u);
    *v6 = a2;
    v6[1] = 0;
    if ( *((_QWORD *)this + 13) )
      *(_QWORD *)(*((_QWORD *)this + 14) + 8LL) = v6;
    else
      *((_QWORD *)this + 13) = v6;
    *((_QWORD *)this + 14) = v6;
  }
  std::_Mutex_base::unlock(v4);
  if ( v5 )
  {
LABEL_9:
    CurrentThreadId = GetCurrentThreadId();
    if ( !_InterlockedCompareExchange((volatile signed __int32 *)a2 + 4, CurrentThreadId, 0) )
    {
      (*(void (__fastcall **)(struct Concurrency::details::_CancellationTokenRegistration *))(*(_QWORD *)a2 + 16LL))(a2);
      v8 = _InterlockedCompareExchange((volatile signed __int32 *)a2 + 4, 3, CurrentThreadId);
      if ( CurrentThreadId != v8 )
        CurrentThreadId = v8;
      if ( CurrentThreadId == 2 )
      {
        std::_Mutex_base::lock((struct Concurrency::details::_CancellationTokenRegistration *)((char *)a2 + 96));
        *((_BYTE *)a2 + 176) = 1;
        std::_Mutex_base::unlock((struct Concurrency::details::_CancellationTokenRegistration *)((char *)a2 + 96));
        WakeAllConditionVariable((PCONDITION_VARIABLE)a2 + 4);
      }
    }
    Concurrency::details::_RefCounter::_Release(a2);
  }
}

```

## disassembly

```asm
0x140035c78  mov     [rsp+arg_10], rbx
0x140035c7d  push    rbp
0x140035c7e  push    rsi
0x140035c7f  push    rdi
0x140035c80  sub     rsp, 30h
0x140035c84  mov     rdi, rdx
0x140035c87  mov     rbx, rcx
0x140035c8a  xor     eax, eax
0x140035c8c  xchg    eax, [rdx+10h]
0x140035c8f  lock inc dword ptr [rdx+8]
0x140035c93  mov     [rdx+0B8h], rcx
0x140035c9a  mov     eax, [rcx+10h]
0x140035c9d  nop
0x140035c9e  test    eax, eax
0x140035ca0  jnz     short loc_140035D07
0x140035ca2  lea     rsi, [rcx+18h]
0x140035ca6  mov     [rsp+48h+var_28], rsi
0x140035cab  mov     rcx, rsi; this
0x140035cae  call    ?lock@_Mutex_base@std@@QEAAXXZ; std::_Mutex_base::lock(void)
0x140035cb3  nop
0x140035cb4  mov     eax, [rbx+10h]
0x140035cb7  nop
0x140035cb8  test    eax, eax
0x140035cba  jz      short loc_140035CC1
0x140035cbc  mov     bpl, 1
0x140035cbf  jmp     short loc_140035CFA
0x140035cc1  xor     bpl, bpl
0x140035cc4  mov     ecx, 10h; Size
0x140035cc9  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x140035cce  mov     rcx, rax
0x140035cd1  mov     [rsp+48h+var_28], rax
0x140035cd6  mov     [rax], rdi
0x140035cd9  mov     qword ptr [rax+8], 0
0x140035ce1  cmp     qword ptr [rbx+68h], 0
0x140035ce6  jnz     short loc_140035CEE
0x140035ce8  mov     [rbx+68h], rax
0x140035cec  jmp     short loc_140035CF6
0x140035cee  mov     rax, [rbx+70h]
0x140035cf2  mov     [rax+8], rcx
0x140035cf6  mov     [rbx+70h], rcx
0x140035cfa  mov     rcx, rsi; this
0x140035cfd  call    ?unlock@_Mutex_base@std@@QEAAXXZ; std::_Mutex_base::unlock(void)
0x140035d02  test    bpl, bpl
0x140035d05  jz      short loc_140035D66
0x140035d07  call    cs:__imp_GetCurrentThreadId
0x140035d0d  mov     ebx, eax
0x140035d0f  xor     eax, eax
0x140035d11  lock cmpxchg [rdi+10h], ebx
0x140035d16  jnz     short loc_140035D5E
0x140035d18  mov     rcx, [rdi]
0x140035d1b  mov     rax, [rcx+10h]
0x140035d1f  mov     rcx, rdi
0x140035d22  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140035d27  mov     ecx, 3
0x140035d2c  mov     eax, ebx
0x140035d2e  lock cmpxchg [rdi+10h], ecx
0x140035d33  cmovnz  ebx, eax
0x140035d36  cmp     ebx, 2
0x140035d39  jnz     short loc_140035D5E
0x140035d3b  lea     rcx, [rdi+60h]; this
0x140035d3f  call    ?lock@_Mutex_base@std@@QEAAXXZ; std::_Mutex_base::lock(void)
0x140035d44  mov     byte ptr [rdi+0B0h], 1
0x140035d4b  lea     rcx, [rdi+60h]; this
0x140035d4f  call    ?unlock@_Mutex_base@std@@QEAAXXZ; std::_Mutex_base::unlock(void)
0x140035d54  lea     rcx, [rdi+20h]; ConditionVariable
0x140035d58  call    cs:__imp_WakeAllConditionVariable
0x140035d5e  mov     rcx, rdi; this
0x140035d61  call    ?_Release@_RefCounter@details@Concurrency@@QEAAJXZ; Concurrency::details::_RefCounter::_Release(void)
0x140035d66  mov     rbx, [rsp+48h+arg_10]
0x140035d6b  add     rsp, 30h
0x140035d6f  pop     rdi
0x140035d70  pop     rsi
0x140035d71  pop     rbp
0x140035d72  retn
```
