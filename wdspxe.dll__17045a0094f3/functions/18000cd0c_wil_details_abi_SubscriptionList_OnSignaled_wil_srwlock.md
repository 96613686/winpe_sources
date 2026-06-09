# wil::details_abi::SubscriptionList::OnSignaled(wil::srwlock &)

- ea: `0x18000cd0c`
- end: `0x18000ce2a`
- name: `?OnSignaled@SubscriptionList@details_abi@wil@@QEAAXAEAVsrwlock@3@@Z`
- size: `286`
- prototype: `void __fastcall(LPCRITICAL_SECTION lpCriticalSection, PSRWLOCK SRWLock)`
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x180008fd0`
- `0x180009000`
- `0x1800090b0`
- `0x180010600`

## callees

- `0x18000cd0c`
- `0x180013010`

## import_xrefs

- `KERNEL32!EnterCriticalSection` at `0x18000cd6d`
- `KERNEL32!EnterCriticalSection` at `0x18000cd6d`
- `KERNEL32!LeaveCriticalSection` at `0x18000cdfb`
- `KERNEL32!LeaveCriticalSection` at `0x18000cdfb`
- `KERNEL32!AcquireSRWLockExclusive` at `0x18000cd7c`
- `KERNEL32!AcquireSRWLockExclusive` at `0x18000cd7c`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x18000cdd7`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x18000cdd7`
- `KERNEL32!AcquireSRWLockShared` at `0x18000cd2d`
- `KERNEL32!AcquireSRWLockShared` at `0x18000cd2d`
- `KERNEL32!ReleaseSRWLockShared` at `0x18000cd4d`
- `KERNEL32!ReleaseSRWLockShared` at `0x18000cd4d`

## pseudocode

```c
void __fastcall wil::details_abi::SubscriptionList::OnSignaled(LPCRITICAL_SECTION lpCriticalSection, PSRWLOCK SRWLock)
{
  unsigned __int64 v4; // rdi
  unsigned __int64 v5; // rbx
  void (__fastcall *v6)(unsigned __int64); // r14
  unsigned __int64 v7; // r15
  PRTL_CRITICAL_SECTION_DEBUG DebugInfo; // rdx
  WORD *v9; // rax
  unsigned __int64 v10; // rcx
  __m128i v11; // xmm1

  AcquireSRWLockShared(SRWLock);
  v4 = (*(_QWORD *)&lpCriticalSection[1].LockCount - (unsigned __int64)lpCriticalSection[1].DebugInfo) >> 4;
  if ( SRWLock )
    ReleaseSRWLockShared(SRWLock);
  v5 = 0;
  while ( v5 < v4 )
  {
    v6 = 0;
    v7 = 0;
    EnterCriticalSection(lpCriticalSection);
    AcquireSRWLockExclusive(SRWLock);
    if ( v5 < v4 )
    {
      DebugInfo = lpCriticalSection[1].DebugInfo;
      v9 = &DebugInfo->Type + 8 * v5;
      while ( 1 )
      {
        v10 = v5 + 1;
        if ( *(_QWORD *)v9 )
          break;
        v9 += 8;
        ++v5;
        if ( v10 >= v4 )
          goto LABEL_10;
      }
      v11 = *((__m128i *)&DebugInfo->Type + v5++);
      v6 = (void (__fastcall *)(unsigned __int64))v11.m128i_i64[0];
      v7 = _mm_srli_si128(v11, 8).m128i_u64[0];
    }
LABEL_10:
    if ( SRWLock )
      ReleaseSRWLockExclusive(SRWLock);
    if ( v6 )
      v6(v7);
    if ( lpCriticalSection )
      LeaveCriticalSection(lpCriticalSection);
  }
}

```

## disassembly

```asm
0x18000cd0c  mov     [rsp+arg_0], rbx
0x18000cd11  mov     [rsp+arg_8], rbp
0x18000cd16  mov     [rsp+arg_10], rsi
0x18000cd1b  push    rdi
0x18000cd1c  push    r14
0x18000cd1e  push    r15
0x18000cd20  sub     rsp, 20h
0x18000cd24  mov     rbp, rcx
0x18000cd27  mov     rsi, rdx
0x18000cd2a  mov     rcx, rdx; SRWLock
0x18000cd2d  call    cs:__imp_AcquireSRWLockShared
0x18000cd34  nop     dword ptr [rax+rax+00h]
0x18000cd39  mov     rdi, [rbp+30h]
0x18000cd3d  sub     rdi, [rbp+28h]
0x18000cd41  shr     rdi, 4
0x18000cd45  test    rsi, rsi
0x18000cd48  jz      short loc_18000CD59
0x18000cd4a  mov     rcx, rsi; SRWLock
0x18000cd4d  call    cs:__imp_ReleaseSRWLockShared
0x18000cd54  nop     dword ptr [rax+rax+00h]
0x18000cd59  xor     ebx, ebx
0x18000cd5b  test    rdi, rdi
0x18000cd5e  jz      loc_18000CE10
0x18000cd64  mov     rcx, rbp; lpCriticalSection
0x18000cd67  xor     r14d, r14d
0x18000cd6a  xor     r15d, r15d
0x18000cd6d  call    cs:__imp_EnterCriticalSection
0x18000cd74  nop     dword ptr [rax+rax+00h]
0x18000cd79  mov     rcx, rsi; SRWLock
0x18000cd7c  call    cs:__imp_AcquireSRWLockExclusive
0x18000cd83  nop     dword ptr [rax+rax+00h]
0x18000cd88  cmp     rbx, rdi
0x18000cd8b  jnb     short loc_18000CDCF
0x18000cd8d  mov     rdx, [rbp+28h]
0x18000cd91  mov     rax, rbx
0x18000cd94  shl     rax, 4
0x18000cd98  add     rax, rdx
0x18000cd9b  lea     rcx, [rbx+1]
0x18000cd9f  cmp     [rax], r14
0x18000cda2  jnz     short loc_18000CDB2
0x18000cda4  add     rax, 10h
0x18000cda8  mov     rbx, rcx
0x18000cdab  cmp     rcx, rdi
0x18000cdae  jb      short loc_18000CD9B
0x18000cdb0  jmp     short loc_18000CDCF
0x18000cdb2  add     rbx, rbx
0x18000cdb5  movups  xmm1, xmmword ptr [rdx+rbx*8]
0x18000cdb9  mov     rbx, rcx
0x18000cdbc  movdqa  xmm0, xmm1
0x18000cdc0  movq    r14, xmm1
0x18000cdc5  psrldq  xmm0, 8
0x18000cdca  movq    r15, xmm0
0x18000cdcf  test    rsi, rsi
0x18000cdd2  jz      short loc_18000CDE3
0x18000cdd4  mov     rcx, rsi; SRWLock
0x18000cdd7  call    cs:__imp_ReleaseSRWLockExclusive
0x18000cdde  nop     dword ptr [rax+rax+00h]
0x18000cde3  test    r14, r14
0x18000cde6  jz      short loc_18000CDF3
0x18000cde8  mov     rcx, r15
0x18000cdeb  mov     rax, r14
0x18000cdee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cdf3  test    rbp, rbp
0x18000cdf6  jz      short loc_18000CE07
0x18000cdf8  mov     rcx, rbp; lpCriticalSection
0x18000cdfb  call    cs:__imp_LeaveCriticalSection
0x18000ce02  nop     dword ptr [rax+rax+00h]
0x18000ce07  cmp     rbx, rdi
0x18000ce0a  jb      loc_18000CD64
0x18000ce10  mov     rbx, [rsp+38h+arg_0]
0x18000ce15  mov     rbp, [rsp+38h+arg_8]
0x18000ce1a  mov     rsi, [rsp+38h+arg_10]
0x18000ce1f  add     rsp, 20h
0x18000ce23  pop     r15
0x18000ce25  pop     r14
0x18000ce27  pop     rdi
0x18000ce28  retn
```
