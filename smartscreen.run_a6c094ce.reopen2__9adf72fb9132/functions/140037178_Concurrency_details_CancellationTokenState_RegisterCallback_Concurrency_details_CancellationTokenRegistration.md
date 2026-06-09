# Concurrency::details::_CancellationTokenState::_RegisterCallback(Concurrency::details::_CancellationTokenRegistration *)

- ea: `0x140037178`
- end: `0x140037280`
- name: `?_RegisterCallback@_CancellationTokenState@details@Concurrency@@QEAAXPEAV_CancellationTokenRegistration@23@@Z`
- size: `264`
- prototype: `void(Concurrency::details::_CancellationTokenState *__hidden this, struct Concurrency::details::_CancellationTokenRegistration *)`
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x140037288`

## callees

- `0x1400072e4`
- `0x14001a5d8`
- `0x1400270f0`
- `0x140037178`
- `0x140037308`
- `0x14006a010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140037207`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140037207`
- `api-ms-win-core-synch-l1-2-0!WakeAllConditionVariable` at `0x14003725e`
- `api-ms-win-core-synch-l1-2-0!WakeAllConditionVariable` at `0x14003725e`

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
0x140037178  mov     [rsp+arg_10], rbx
0x14003717d  push    rbp
0x14003717e  push    rsi
0x14003717f  push    rdi
0x140037180  sub     rsp, 30h
0x140037184  mov     rdi, rdx
0x140037187  mov     rbx, rcx
0x14003718a  xor     eax, eax
0x14003718c  xchg    eax, [rdx+10h]
0x14003718f  lock inc dword ptr [rdx+8]
0x140037193  mov     [rdx+0B8h], rcx
0x14003719a  mov     eax, [rcx+10h]
0x14003719d  nop
0x14003719e  test    eax, eax
0x1400371a0  jnz     short loc_140037207
0x1400371a2  lea     rsi, [rcx+18h]
0x1400371a6  mov     [rsp+48h+var_28], rsi
0x1400371ab  mov     rcx, rsi; this
0x1400371ae  call    ?lock@_Mutex_base@std@@QEAAXXZ; std::_Mutex_base::lock(void)
0x1400371b3  nop
0x1400371b4  mov     eax, [rbx+10h]
0x1400371b7  nop
0x1400371b8  test    eax, eax
0x1400371ba  jz      short loc_1400371C1
0x1400371bc  mov     bpl, 1
0x1400371bf  jmp     short loc_1400371FA
0x1400371c1  xor     bpl, bpl
0x1400371c4  mov     ecx, 10h; Size
0x1400371c9  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1400371ce  mov     rcx, rax
0x1400371d1  mov     [rsp+48h+var_28], rax
0x1400371d6  mov     [rax], rdi
0x1400371d9  mov     qword ptr [rax+8], 0
0x1400371e1  cmp     qword ptr [rbx+68h], 0
0x1400371e6  jnz     short loc_1400371EE
0x1400371e8  mov     [rbx+68h], rax
0x1400371ec  jmp     short loc_1400371F6
0x1400371ee  mov     rax, [rbx+70h]
0x1400371f2  mov     [rax+8], rcx
0x1400371f6  mov     [rbx+70h], rcx
0x1400371fa  mov     rcx, rsi; this
0x1400371fd  call    ?unlock@_Mutex_base@std@@QEAAXXZ; std::_Mutex_base::unlock(void)
0x140037202  test    bpl, bpl
0x140037205  jz      short loc_140037272
0x140037207  call    cs:__imp_GetCurrentThreadId
0x14003720e  nop     dword ptr [rax+rax+00h]
0x140037213  mov     ebx, eax
0x140037215  xor     eax, eax
0x140037217  lock cmpxchg [rdi+10h], ebx
0x14003721c  jnz     short loc_14003726A
0x14003721e  mov     rcx, [rdi]
0x140037221  mov     rax, [rcx+10h]
0x140037225  mov     rcx, rdi
0x140037228  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14003722d  mov     ecx, 3
0x140037232  mov     eax, ebx
0x140037234  lock cmpxchg [rdi+10h], ecx
0x140037239  cmovnz  ebx, eax
0x14003723c  cmp     ebx, 2
0x14003723f  jnz     short loc_14003726A
0x140037241  lea     rcx, [rdi+60h]; this
0x140037245  call    ?lock@_Mutex_base@std@@QEAAXXZ; std::_Mutex_base::lock(void)
0x14003724a  mov     byte ptr [rdi+0B0h], 1
0x140037251  lea     rcx, [rdi+60h]; this
0x140037255  call    ?unlock@_Mutex_base@std@@QEAAXXZ; std::_Mutex_base::unlock(void)
0x14003725a  lea     rcx, [rdi+20h]; ConditionVariable
0x14003725e  call    cs:__imp_WakeAllConditionVariable
0x140037265  nop     dword ptr [rax+rax+00h]
0x14003726a  mov     rcx, rdi; this
0x14003726d  call    ?_Release@_RefCounter@details@Concurrency@@QEAAJXZ; Concurrency::details::_RefCounter::_Release(void)
0x140037272  mov     rbx, [rsp+48h+arg_10]
0x140037277  add     rsp, 30h
0x14003727b  pop     rdi
0x14003727c  pop     rsi
0x14003727d  pop     rbp
0x14003727e  retn
```
