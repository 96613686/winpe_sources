# Concurrency::details::_CancellationTokenState::_DeregisterCallback(Concurrency::details::_CancellationTokenRegistration *)

- ea: `0x140036cb4`
- end: `0x140036dc9`
- name: `?_DeregisterCallback@_CancellationTokenState@details@Concurrency@@QEAAXPEAV_CancellationTokenRegistration@23@@Z`
- size: `277`
- prototype: `void(Concurrency::details::_CancellationTokenState *__hidden this, struct Concurrency::details::_CancellationTokenRegistration *)`
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops, broker_com_uri`

## callers

- `0x14001ba18`

## callees

- `0x1400072e4`
- `0x14001078c`
- `0x1400129bc`
- `0x14001a5d8`
- `0x14001f964`
- `0x140027084`
- `0x140036cb4`
- `0x140037308`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140036d6e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140036d6e`

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
0x140036cb4  mov     [rsp+arg_10], rbx
0x140036cb9  push    rbp
0x140036cba  push    rsi
0x140036cbb  push    rdi
0x140036cbc  push    r12
0x140036cbe  push    r14
0x140036cc0  sub     rsp, 30h
0x140036cc4  mov     rdi, rdx
0x140036cc7  mov     rbp, rcx
0x140036cca  lea     rbx, [rcx+18h]
0x140036cce  mov     [rsp+58h+var_38], rbx
0x140036cd3  mov     rcx, rbx; this
0x140036cd6  call    ?lock@_Mutex_base@std@@QEAAXXZ; std::_Mutex_base::lock(void)
0x140036cdb  nop
0x140036cdc  mov     rcx, [rbp+68h]; void *
0x140036ce0  mov     esi, 2
0x140036ce5  lea     r12d, [rsi-1]
0x140036ce9  test    rcx, rcx
0x140036cec  jnz     short loc_140036CF3
0x140036cee  mov     r14b, r12b
0x140036cf1  jmp     short loc_140036D40
0x140036cf3  xor     r14b, r14b
0x140036cf6  xor     eax, eax
0x140036cf8  test    rcx, rcx
0x140036cfb  jz      short loc_140036D32
0x140036cfd  mov     rdx, [rcx+8]
0x140036d01  cmp     [rcx], rdi
0x140036d04  jz      short loc_140036D0E
0x140036d06  mov     rax, rcx
0x140036d09  mov     rcx, rdx
0x140036d0c  jmp     short loc_140036CF8
0x140036d0e  test    rax, rax
0x140036d11  jnz     short loc_140036D19
0x140036d13  mov     [rbp+68h], rdx
0x140036d17  jmp     short loc_140036D1D
0x140036d19  mov     [rax+8], rdx
0x140036d1d  cmp     qword ptr [rcx+8], 0
0x140036d22  jnz     short loc_140036D28
0x140036d24  mov     [rbp+70h], rax
0x140036d28  mov     edx, 10h; struct std::nothrow_t *
0x140036d2d  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x140036d32  mov     eax, esi
0x140036d34  xchg    eax, [rdi+10h]
0x140036d37  mov     rcx, rdi; this
0x140036d3a  call    ?_Release@_RefCounter@details@Concurrency@@QEAAJXZ; Concurrency::details::_RefCounter::_Release(void)
0x140036d3f  nop
0x140036d40  mov     rcx, rbx; this
0x140036d43  call    ?unlock@_Mutex_base@std@@QEAAXXZ; std::_Mutex_base::unlock(void)
0x140036d48  test    r14b, r14b
0x140036d4b  jz      short loc_140036DB7
0x140036d4d  xor     eax, eax
0x140036d4f  lock cmpxchg [rdi+10h], r12d
0x140036d55  mov     ebx, eax
0x140036d57  jz      short loc_140036DB7
0x140036d59  mov     edx, eax
0x140036d5b  test    eax, eax
0x140036d5d  jz      short loc_140036DB7
0x140036d5f  sub     edx, 1
0x140036d62  jz      short loc_140036DB7
0x140036d64  sub     edx, 1
0x140036d67  jz      short loc_140036DB7
0x140036d69  cmp     edx, 1
0x140036d6c  jz      short loc_140036DB7
0x140036d6e  call    cs:__imp_GetCurrentThreadId
0x140036d75  nop     dword ptr [rax+rax+00h]
0x140036d7a  cmp     ebx, eax
0x140036d7c  jz      short loc_140036DB7
0x140036d7e  xchg    esi, [rdi+10h]
0x140036d81  cmp     esi, 3
0x140036d84  jz      short loc_140036DB7
0x140036d86  lea     rdx, [rdi+60h]
0x140036d8a  lea     rcx, [rsp+58h+var_38]
0x140036d8f  call    ??0?$unique_lock@Vmutex@std@@@std@@QEAA@AEAVmutex@1@@Z; std::unique_lock<std::mutex>::unique_lock<std::mutex>(std::mutex &)
0x140036d94  jmp     short loc_140036DA4
0x140036d96  lea     rdx, [rsp+58h+var_38]
0x140036d9b  lea     rcx, [rdi+18h]
0x140036d9f  call    ?wait@condition_variable@std@@QEAAXAEAV?$unique_lock@Vmutex@std@@@2@@Z; std::condition_variable::wait(std::unique_lock<std::mutex> &)
0x140036da4  cmp     byte ptr [rdi+0B0h], 0
0x140036dab  jz      short loc_140036D96
0x140036dad  lea     rcx, [rsp+58h+var_38]
0x140036db2  call    ??1?$unique_lock@Vmutex@std@@@std@@QEAA@XZ; std::unique_lock<std::mutex>::~unique_lock<std::mutex>(void)
0x140036db7  mov     rbx, [rsp+58h+arg_10]
0x140036dbc  add     rsp, 30h
0x140036dc0  pop     r14
0x140036dc2  pop     r12
0x140036dc4  pop     rdi
0x140036dc5  pop     rsi
0x140036dc6  pop     rbp
0x140036dc7  retn
```
