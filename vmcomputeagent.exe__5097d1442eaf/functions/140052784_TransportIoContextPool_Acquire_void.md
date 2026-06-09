# TransportIoContextPool::Acquire(void)

- ea: `0x140052784`
- end: `0x140052987`
- name: `?Acquire@TransportIoContextPool@@QEAA?AVActiveTransportIoContext@@XZ`
- size: `515`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `file_ops, broker_com_uri`

## callers

- `0x140053238`
- `0x140055950`

## callees

- `0x1400056c4`
- `0x140052784`
- `0x140057ef0`
- `0x1400fe010`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!SleepConditionVariableSRW` at `0x1400527da`
- `api-ms-win-core-synch-l1-2-0!SleepConditionVariableSRW` at `0x1400527da`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x14005295f`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x14005295f`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1400527ac`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1400527ac`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1400527b2`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1400527e0`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1400527b2`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1400527e0`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
_QWORD *__fastcall TransportIoContextPool::Acquire(__int64 *a1, _QWORD *a2)
{
  __int64 *v4; // rbp
  __int64 v5; // rdi
  __int64 v6; // rax
  __int64 v7; // r12
  volatile signed __int32 *v8; // rdi
  __int64 *v9; // r15
  volatile signed __int32 *v10; // rbx
  __int64 v11; // rdx
  signed __int32 v12; // eax
  signed __int32 v13; // ett
  RTL_SRWLOCK v14; // rax
  volatile signed __int32 *v15; // rbx

  v4 = a1 + 2;
  AcquireSRWLockExclusive((PSRWLOCK)a1 + 2);
  for ( *((_DWORD *)v4 + 2) = GetCurrentThreadId(); ; *((_DWORD *)v4 + 2) = GetCurrentThreadId() )
  {
    v5 = a1[5];
    if ( v5 )
      break;
    *((_DWORD *)v4 + 2) = 0;
    SleepConditionVariableSRW((PCONDITION_VARIABLE)a1 + 4, (PSRWLOCK)v4, 0xFFFFFFFF, 0);
  }
  v6 = *(_QWORD *)(v5 + 16);
  if ( v6 )
    _InterlockedIncrement((volatile signed __int32 *)(v6 + 8));
  v7 = *(_QWORD *)(v5 + 8);
  v8 = *(volatile signed __int32 **)(v5 + 16);
  v9 = (__int64 *)a1[5];
  a1[5] = *v9;
  v10 = (volatile signed __int32 *)v9[2];
  if ( v10 )
  {
    if ( _InterlockedExchangeAdd(v10 + 2, 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v10)(v10);
      if ( _InterlockedExchangeAdd(v10 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v10 + 8LL))(v10);
    }
  }
  operator delete(v9, 0x18u);
  v11 = a1[1];
  if ( !v11 )
LABEL_28:
    std::_Throw_bad_weak_ptr();
  v12 = *(_DWORD *)(v11 + 8);
  do
  {
    if ( !v12 )
      goto LABEL_28;
    v13 = v12;
    v12 = _InterlockedCompareExchange((volatile signed __int32 *)(v11 + 8), v12 + 1, v12);
  }
  while ( v13 != v12 );
  v14.Ptr = (PVOID)*a1;
  v15 = (volatile signed __int32 *)a1[1];
  *a2 = 0;
  a2[1] = 0;
  if ( v8 )
    _InterlockedIncrement(v8 + 2);
  *a2 = v7;
  a2[1] = v8;
  a2[2] = 0;
  a2[3] = 0;
  if ( v15 )
    _InterlockedIncrement(v15 + 2);
  a2[2] = v14.Ptr;
  a2[3] = v15;
  if ( v15 )
  {
    if ( _InterlockedExchangeAdd(v15 + 2, 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v15)(v15);
      if ( _InterlockedExchangeAdd(v15 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v15 + 8LL))(v15);
    }
  }
  if ( v8 )
  {
    if ( _InterlockedExchangeAdd(v8 + 2, 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v8)(v8);
      if ( _InterlockedExchangeAdd(v8 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v8 + 8LL))(v8);
    }
  }
  *((_DWORD *)v4 + 2) = 0;
  ReleaseSRWLockExclusive((PSRWLOCK)v4);
  return a2;
}

```

## disassembly

```asm
0x140052784  mov     [rsp+arg_10], rbx
0x140052789  mov     [rsp+arg_18], rbp
0x14005278e  push    rsi
0x14005278f  push    rdi
0x140052790  push    r12
0x140052792  push    r14
0x140052794  push    r15
0x140052796  sub     rsp, 40h
0x14005279a  mov     rsi, rdx
0x14005279d  mov     r14, rcx
0x1400527a0  mov     [rsp+68h+var_40], rdx
0x1400527a5  lea     rbp, [rcx+10h]
0x1400527a9  mov     rcx, rbp; SRWLock
0x1400527ac  call    cs:__imp_AcquireSRWLockExclusive
0x1400527b2  call    cs:__imp_GetCurrentThreadId
0x1400527b8  mov     [rbp+8], eax
0x1400527bb  mov     [rsp+68h+var_40], rbp
0x1400527c0  mov     rdi, [r14+28h]
0x1400527c4  test    rdi, rdi
0x1400527c7  jnz     short loc_1400527EB
0x1400527c9  mov     [rbp+8], edi
0x1400527cc  lea     rcx, [r14+20h]; ConditionVariable
0x1400527d0  xor     r9d, r9d; Flags
0x1400527d3  or      r8d, 0FFFFFFFFh; dwMilliseconds
0x1400527d7  mov     rdx, rbp; SRWLock
0x1400527da  call    cs:__imp_SleepConditionVariableSRW
0x1400527e0  call    cs:__imp_GetCurrentThreadId
0x1400527e6  mov     [rbp+8], eax
0x1400527e9  jmp     short loc_1400527C0
0x1400527eb  xorps   xmm0, xmm0
0x1400527ee  movups  [rsp+68h+var_38], xmm0
0x1400527f3  mov     rax, [rdi+10h]
0x1400527f7  test    rax, rax
0x1400527fa  jz      short loc_140052800
0x1400527fc  lock inc dword ptr [rax+8]
0x140052800  mov     r12, [rdi+8]
0x140052804  mov     qword ptr [rsp+68h+var_38], r12
0x140052809  mov     rdi, [rdi+10h]
0x14005280d  mov     qword ptr [rsp+68h+var_38+8], rdi
0x140052812  mov     r15, [r14+28h]
0x140052816  mov     rax, [r15]
0x140052819  mov     [r14+28h], rax
0x14005281d  mov     rbx, [r15+10h]
0x140052821  test    rbx, rbx
0x140052824  jz      short loc_14005285D
0x140052826  or      eax, 0FFFFFFFFh
0x140052829  lock xadd [rbx+8], eax
0x14005282e  cmp     eax, 1
0x140052831  jnz     short loc_14005285D
0x140052833  mov     rax, [rbx]
0x140052836  mov     rcx, rbx
0x140052839  mov     rax, [rax]
0x14005283c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140052841  or      eax, 0FFFFFFFFh
0x140052844  lock xadd [rbx+0Ch], eax
0x140052849  cmp     eax, 1
0x14005284c  jnz     short loc_14005285D
0x14005284e  mov     rax, [rbx]
0x140052851  mov     rcx, rbx
0x140052854  mov     rax, [rax+8]
0x140052858  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14005285d  mov     edx, 18h; unsigned __int64
0x140052862  mov     rcx, r15; void *
0x140052865  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x14005286a  mov     rdx, [r14+8]
0x14005286e  test    rdx, rdx
0x140052871  jz      loc_140052981
0x140052877  mov     eax, [rdx+8]
0x14005287a  jmp     short loc_140052886
0x14005287c  lea     ecx, [rax+1]
0x14005287f  lock cmpxchg [rdx+8], ecx
0x140052884  jz      short loc_140052890
0x140052886  test    eax, eax
0x140052888  jz      loc_140052981
0x14005288e  jmp     short loc_14005287C
0x140052890  mov     rax, [r14]
0x140052893  mov     rbx, [r14+8]
0x140052897  mov     qword ptr [rsi], 0
0x14005289e  mov     qword ptr [rsi+8], 0
0x1400528a6  test    rdi, rdi
0x1400528a9  jz      short loc_1400528AF
0x1400528ab  lock inc dword ptr [rdi+8]
0x1400528af  mov     [rsi], r12
0x1400528b2  mov     [rsi+8], rdi
0x1400528b6  mov     qword ptr [rsi+10h], 0
0x1400528be  mov     qword ptr [rsi+18h], 0
0x1400528c6  test    rbx, rbx
0x1400528c9  jz      short loc_1400528CF
0x1400528cb  lock inc dword ptr [rbx+8]
0x1400528cf  mov     [rsi+10h], rax
0x1400528d3  mov     [rsi+18h], rbx
0x1400528d7  or      r14d, 0FFFFFFFFh
0x1400528db  test    rbx, rbx
0x1400528de  jz      short loc_140052918
0x1400528e0  mov     eax, r14d
0x1400528e3  lock xadd [rbx+8], eax
0x1400528e8  add     eax, r14d
0x1400528eb  jnz     short loc_140052918
0x1400528ed  mov     rax, [rbx]
0x1400528f0  mov     rcx, rbx
0x1400528f3  mov     rax, [rax]
0x1400528f6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400528fb  mov     eax, r14d
0x1400528fe  lock xadd [rbx+0Ch], eax
0x140052903  add     eax, r14d
0x140052906  jnz     short loc_140052918
0x140052908  mov     rax, [rbx]
0x14005290b  mov     rcx, rbx
0x14005290e  mov     rax, [rax+8]
0x140052912  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140052917  nop
0x140052918  test    rdi, rdi
0x14005291b  jz      short loc_140052955
0x14005291d  mov     eax, r14d
0x140052920  lock xadd [rdi+8], eax
0x140052925  add     eax, r14d
0x140052928  jnz     short loc_140052955
0x14005292a  mov     rax, [rdi]
0x14005292d  mov     rcx, rdi
0x140052930  mov     rax, [rax]
0x140052933  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140052938  mov     eax, r14d
0x14005293b  lock xadd [rdi+0Ch], eax
0x140052940  add     eax, r14d
0x140052943  jnz     short loc_140052955
0x140052945  mov     rdx, [rdi]
0x140052948  mov     rcx, rdi
0x14005294b  mov     rax, [rdx+8]
0x14005294f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140052954  nop
0x140052955  mov     dword ptr [rbp+8], 0
0x14005295c  mov     rcx, rbp; SRWLock
0x14005295f  call    cs:__imp_ReleaseSRWLockExclusive
0x140052965  mov     rax, rsi
0x140052968  lea     r11, [rsp+68h+var_28]
0x14005296d  mov     rbx, [r11+40h]
0x140052971  mov     rbp, [r11+48h]
0x140052975  mov     rsp, r11
0x140052978  pop     r15
0x14005297a  pop     r14
0x14005297c  pop     r12
0x14005297e  pop     rdi
0x14005297f  pop     rsi
0x140052980  retn
0x140052981  call    ?_Throw_bad_weak_ptr@std@@YAXXZ; std::_Throw_bad_weak_ptr(void)
```
