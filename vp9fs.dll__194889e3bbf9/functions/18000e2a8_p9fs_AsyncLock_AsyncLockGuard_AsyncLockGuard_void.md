# p9fs::AsyncLock::AsyncLockGuard::~AsyncLockGuard(void)

- ea: `0x18000e2a8`
- end: `0x18000e32c`
- name: `??1AsyncLockGuard@AsyncLock@p9fs@@QEAA@XZ`
- size: `132`
- prototype: `void __fastcall(p9fs::AsyncLock::AsyncLockGuard *__hidden this)`
- caller_count: `2`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180017570`
- `0x180031585`

## callees

- `0x1800074e0`
- `0x18000c4bc`
- `0x18000e2a8`

## string_xrefs

- `0x18000e31a`: `onecore\vm\dv\storage\plan9\dll\p9await.h`

## pseudocode

```c
void __fastcall p9fs::AsyncLock::AsyncLockGuard::~AsyncLockGuard(p9fs::AsyncLock::AsyncLockGuard *this)
{
  __int64 v1; // rdx
  unsigned __int64 v2; // rcx
  unsigned __int64 v3; // r8
  unsigned __int64 v4; // rax
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  v1 = *(_QWORD *)this;
  if ( *(_QWORD *)this
    && (*(_QWORD *)(v1 + 8) || _InterlockedCompareExchange64((volatile signed __int64 *)v1, 0, 1) != 1) )
  {
    v2 = *(_QWORD *)(v1 + 8);
    if ( !v2 )
    {
      v3 = _InterlockedExchange64((volatile __int64 *)v1, 1);
      if ( v3 <= 1 )
        wil::details::in1diag3::_FailFast_Unexpected(
          retaddr,
          (void *)0x30B,
          (unsigned int)"onecore\\vm\\dv\\storage\\plan9\\dll\\p9await.h",
          (const char *)1);
      do
      {
        v4 = *(_QWORD *)(v3 + 8);
        *(_QWORD *)(v3 + 8) = v2;
        v2 = v3;
        v3 = v4;
      }
      while ( v4 );
      *(_QWORD *)(v1 + 8) = v2;
    }
    *(_QWORD *)(v1 + 8) = *(_QWORD *)(v2 + 8);
    p9fs::Scheduler::Schedule(&p9fs::g_Scheduler);
  }
}

```

## disassembly

```asm
0x18000e2a8  sub     rsp, 28h
0x18000e2ac  mov     rdx, [rcx]
0x18000e2af  test    rdx, rdx
0x18000e2b2  jz      short loc_18000E310
0x18000e2b4  cmp     qword ptr [rdx+8], 0
0x18000e2b9  mov     r9d, 1; char *
0x18000e2bf  jnz     short loc_18000E2CD
0x18000e2c1  xor     ecx, ecx
0x18000e2c3  mov     eax, r9d
0x18000e2c6  lock cmpxchg [rdx], rcx
0x18000e2cb  jz      short loc_18000E310
0x18000e2cd  mov     rcx, [rdx+8]
0x18000e2d1  test    rcx, rcx
0x18000e2d4  jnz     short loc_18000E2F8
0x18000e2d6  mov     r8, r9
0x18000e2d9  xchg    r8, [rdx]
0x18000e2dc  cmp     r8, r9
0x18000e2df  jbe     short loc_18000E315
0x18000e2e1  mov     rax, [r8+8]
0x18000e2e5  mov     [r8+8], rcx
0x18000e2e9  mov     rcx, r8
0x18000e2ec  mov     r8, rax
0x18000e2ef  test    rax, rax
0x18000e2f2  jnz     short loc_18000E2E1
0x18000e2f4  mov     [rdx+8], rcx
0x18000e2f8  mov     rax, [rcx+8]
0x18000e2fc  mov     [rdx+8], rax
0x18000e300  mov     rdx, [rcx+10h]
0x18000e304  lea     rcx, ?g_Scheduler@p9fs@@3VScheduler@1@A; _Smtx_t *
0x18000e30b  call    ?Schedule@Scheduler@p9fs@@QEAAXU?$coroutine_handle@X@experimental@std@@@Z; p9fs::Scheduler::Schedule(std::experimental::coroutine_handle<void>)
0x18000e310  add     rsp, 28h
0x18000e314  retn
0x18000e315  mov     rcx, [rsp+28h]; this
0x18000e31a  lea     r8, aOnecoreVmDvSto_1; "onecore\\vm\\dv\\storage\\plan9\\dll\\p"...
0x18000e321  mov     edx, 30Bh; void *
0x18000e326  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
```
