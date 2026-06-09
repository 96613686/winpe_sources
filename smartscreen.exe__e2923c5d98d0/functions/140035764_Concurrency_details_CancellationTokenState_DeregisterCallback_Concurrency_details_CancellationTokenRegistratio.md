# Concurrency::details::_CancellationTokenState::_DeregisterCallback(Concurrency::details::_CancellationTokenRegistration *)

- ea: `0x140035764`
- end: `0x140035872`
- name: `?_DeregisterCallback@_CancellationTokenState@details@Concurrency@@QEAAXPEAV_CancellationTokenRegistration@23@@Z`
- size: `270`
- prototype: `void(Concurrency::details::_CancellationTokenState *__hidden this, struct Concurrency::details::_CancellationTokenRegistration *)`
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops, broker_com_uri`

## callers

- `0x14001abf0`

## callees

- `0x140006e8c`
- `0x14000ff0c`
- `0x14001218c`
- `0x1400198d0`
- `0x14001eaa4`
- `0x140025f04`
- `0x140035764`
- `0x140035dfc`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14003581e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14003581e`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall Concurrency::details::_CancellationTokenState::_DeregisterCallback(
        Concurrency::details::_CancellationTokenState *this,
        struct Concurrency::details::_CancellationTokenRegistration *a2)
{
  std::_Mutex_base *v4; // rbx
  struct Concurrency::details::_CancellationTokenRegistration **v5; // rcx
  char v6; // r14
  struct Concurrency::details::_CancellationTokenRegistration **v7; // rax
  struct Concurrency::details::_CancellationTokenRegistration *v8; // rdx
  unsigned __int32 v9; // eax
  _QWORD v10[7]; // [rsp+20h] [rbp-38h] BYREF

  v4 = (Concurrency::details::_CancellationTokenState *)((char *)this + 24);
  v10[0] = (char *)this + 24;
  std::_Mutex_base::lock((Concurrency::details::_CancellationTokenState *)((char *)this + 24));
  v5 = (struct Concurrency::details::_CancellationTokenRegistration **)*((_QWORD *)this + 13);
  if ( v5 )
  {
    v6 = 0;
    v7 = 0;
    while ( v5 )
    {
      v8 = v5[1];
      if ( *v5 == a2 )
      {
        if ( v7 )
          v7[1] = v8;
        else
          *((_QWORD *)this + 13) = v8;
        if ( !v5[1] )
          *((_QWORD *)this + 14) = v7;
        operator delete(v5, (const struct std::nothrow_t *)0x10);
        break;
      }
      v7 = v5;
      v5 = (struct Concurrency::details::_CancellationTokenRegistration **)v5[1];
    }
    _InterlockedExchange((volatile __int32 *)a2 + 4, 2);
    Concurrency::details::_RefCounter::_Release(a2);
  }
  else
  {
    v6 = 1;
  }
  std::_Mutex_base::unlock(v4);
  if ( v6 )
  {
    v9 = _InterlockedCompareExchange((volatile signed __int32 *)a2 + 4, 1, 0);
    if ( v9 >= 2
      && v9 - 2 >= 2
      && v9 != GetCurrentThreadId()
      && _InterlockedExchange((volatile __int32 *)a2 + 4, 2) != 3 )
    {
      std::unique_lock<std::mutex>::unique_lock<std::mutex>(v10, (char *)a2 + 96);
      while ( !*((_BYTE *)a2 + 176) )
        std::condition_variable::wait((char *)a2 + 24, v10);
      std::unique_lock<std::mutex>::~unique_lock<std::mutex>(v10);
    }
  }
}

```

## disassembly

```asm
0x140035764  mov     [rsp+arg_10], rbx
0x140035769  push    rbp
0x14003576a  push    rsi
0x14003576b  push    rdi
0x14003576c  push    r12
0x14003576e  push    r14
0x140035770  sub     rsp, 30h
0x140035774  mov     rdi, rdx
0x140035777  mov     rbp, rcx
0x14003577a  lea     rbx, [rcx+18h]
0x14003577e  mov     [rsp+58h+var_38], rbx
0x140035783  mov     rcx, rbx; this
0x140035786  call    ?lock@_Mutex_base@std@@QEAAXXZ; std::_Mutex_base::lock(void)
0x14003578b  nop
0x14003578c  mov     rcx, [rbp+68h]; void *
0x140035790  mov     esi, 2
0x140035795  lea     r12d, [rsi-1]
0x140035799  test    rcx, rcx
0x14003579c  jnz     short loc_1400357A3
0x14003579e  mov     r14b, r12b
0x1400357a1  jmp     short loc_1400357F0
0x1400357a3  xor     r14b, r14b
0x1400357a6  xor     eax, eax
0x1400357a8  test    rcx, rcx
0x1400357ab  jz      short loc_1400357E2
0x1400357ad  mov     rdx, [rcx+8]
0x1400357b1  cmp     [rcx], rdi
0x1400357b4  jz      short loc_1400357BE
0x1400357b6  mov     rax, rcx
0x1400357b9  mov     rcx, rdx
0x1400357bc  jmp     short loc_1400357A8
0x1400357be  test    rax, rax
0x1400357c1  jnz     short loc_1400357C9
0x1400357c3  mov     [rbp+68h], rdx
0x1400357c7  jmp     short loc_1400357CD
0x1400357c9  mov     [rax+8], rdx
0x1400357cd  cmp     qword ptr [rcx+8], 0
0x1400357d2  jnz     short loc_1400357D8
0x1400357d4  mov     [rbp+70h], rax
0x1400357d8  mov     edx, 10h; struct std::nothrow_t *
0x1400357dd  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1400357e2  mov     eax, esi
0x1400357e4  xchg    eax, [rdi+10h]
0x1400357e7  mov     rcx, rdi; this
0x1400357ea  call    ?_Release@_RefCounter@details@Concurrency@@QEAAJXZ; Concurrency::details::_RefCounter::_Release(void)
0x1400357ef  nop
0x1400357f0  mov     rcx, rbx; this
0x1400357f3  call    ?unlock@_Mutex_base@std@@QEAAXXZ; std::_Mutex_base::unlock(void)
0x1400357f8  test    r14b, r14b
0x1400357fb  jz      short loc_140035861
0x1400357fd  xor     eax, eax
0x1400357ff  lock cmpxchg [rdi+10h], r12d
0x140035805  mov     ebx, eax
0x140035807  jz      short loc_140035861
0x140035809  mov     edx, eax
0x14003580b  test    eax, eax
0x14003580d  jz      short loc_140035861
0x14003580f  sub     edx, 1
0x140035812  jz      short loc_140035861
0x140035814  sub     edx, 1
0x140035817  jz      short loc_140035861
0x140035819  cmp     edx, 1
0x14003581c  jz      short loc_140035861
0x14003581e  call    cs:__imp_GetCurrentThreadId
0x140035824  cmp     ebx, eax
0x140035826  jz      short loc_140035861
0x140035828  xchg    esi, [rdi+10h]
0x14003582b  cmp     esi, 3
0x14003582e  jz      short loc_140035861
0x140035830  lea     rdx, [rdi+60h]
0x140035834  lea     rcx, [rsp+58h+var_38]
0x140035839  call    ??0?$unique_lock@Vmutex@std@@@std@@QEAA@AEAVmutex@1@@Z; std::unique_lock<std::mutex>::unique_lock<std::mutex>(std::mutex &)
0x14003583e  jmp     short loc_14003584E
0x140035840  lea     rdx, [rsp+58h+var_38]
0x140035845  lea     rcx, [rdi+18h]
0x140035849  call    ?wait@condition_variable@std@@QEAAXAEAV?$unique_lock@Vmutex@std@@@2@@Z; std::condition_variable::wait(std::unique_lock<std::mutex> &)
0x14003584e  cmp     byte ptr [rdi+0B0h], 0
0x140035855  jz      short loc_140035840
0x140035857  lea     rcx, [rsp+58h+var_38]
0x14003585c  call    ??1?$unique_lock@Vmutex@std@@@std@@QEAA@XZ; std::unique_lock<std::mutex>::~unique_lock<std::mutex>(void)
0x140035861  mov     rbx, [rsp+58h+arg_10]
0x140035866  add     rsp, 30h
0x14003586a  pop     r14
0x14003586c  pop     r12
0x14003586e  pop     rdi
0x14003586f  pop     rsi
0x140035870  pop     rbp
0x140035871  retn
```
