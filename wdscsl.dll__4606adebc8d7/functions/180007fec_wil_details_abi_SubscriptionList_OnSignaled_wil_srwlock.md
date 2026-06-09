# wil::details_abi::SubscriptionList::OnSignaled(wil::srwlock &)

- ea: `0x180007fec`
- end: `0x18000810a`
- name: `?OnSignaled@SubscriptionList@details_abi@wil@@QEAAXAEAVsrwlock@3@@Z`
- size: `286`
- prototype: `void __fastcall(LPCRITICAL_SECTION lpCriticalSection, PSRWLOCK SRWLock)`
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x180002710`
- `0x180002740`
- `0x1800027f0`
- `0x18000b3e0`

## callees

- `0x180007fec`
- `0x18000e010`

## import_xrefs

- `KERNEL32!EnterCriticalSection` at `0x18000804d`
- `KERNEL32!EnterCriticalSection` at `0x18000804d`
- `KERNEL32!LeaveCriticalSection` at `0x1800080db`
- `KERNEL32!LeaveCriticalSection` at `0x1800080db`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x1800080b7`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x1800080b7`
- `KERNEL32!AcquireSRWLockExclusive` at `0x18000805c`
- `KERNEL32!AcquireSRWLockExclusive` at `0x18000805c`
- `KERNEL32!ReleaseSRWLockShared` at `0x18000802d`
- `KERNEL32!ReleaseSRWLockShared` at `0x18000802d`
- `KERNEL32!AcquireSRWLockShared` at `0x18000800d`
- `KERNEL32!AcquireSRWLockShared` at `0x18000800d`

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
0x180007fec  mov     [rsp+arg_0], rbx
0x180007ff1  mov     [rsp+arg_8], rbp
0x180007ff6  mov     [rsp+arg_10], rsi
0x180007ffb  push    rdi
0x180007ffc  push    r14
0x180007ffe  push    r15
0x180008000  sub     rsp, 20h
0x180008004  mov     rbp, rcx
0x180008007  mov     rsi, rdx
0x18000800a  mov     rcx, rdx; SRWLock
0x18000800d  call    cs:__imp_AcquireSRWLockShared
0x180008014  nop     dword ptr [rax+rax+00h]
0x180008019  mov     rdi, [rbp+30h]
0x18000801d  sub     rdi, [rbp+28h]
0x180008021  shr     rdi, 4
0x180008025  test    rsi, rsi
0x180008028  jz      short loc_180008039
0x18000802a  mov     rcx, rsi; SRWLock
0x18000802d  call    cs:__imp_ReleaseSRWLockShared
0x180008034  nop     dword ptr [rax+rax+00h]
0x180008039  xor     ebx, ebx
0x18000803b  test    rdi, rdi
0x18000803e  jz      loc_1800080F0
0x180008044  mov     rcx, rbp; lpCriticalSection
0x180008047  xor     r14d, r14d
0x18000804a  xor     r15d, r15d
0x18000804d  call    cs:__imp_EnterCriticalSection
0x180008054  nop     dword ptr [rax+rax+00h]
0x180008059  mov     rcx, rsi; SRWLock
0x18000805c  call    cs:__imp_AcquireSRWLockExclusive
0x180008063  nop     dword ptr [rax+rax+00h]
0x180008068  cmp     rbx, rdi
0x18000806b  jnb     short loc_1800080AF
0x18000806d  mov     rdx, [rbp+28h]
0x180008071  mov     rax, rbx
0x180008074  shl     rax, 4
0x180008078  add     rax, rdx
0x18000807b  lea     rcx, [rbx+1]
0x18000807f  cmp     [rax], r14
0x180008082  jnz     short loc_180008092
0x180008084  add     rax, 10h
0x180008088  mov     rbx, rcx
0x18000808b  cmp     rcx, rdi
0x18000808e  jb      short loc_18000807B
0x180008090  jmp     short loc_1800080AF
0x180008092  add     rbx, rbx
0x180008095  movups  xmm1, xmmword ptr [rdx+rbx*8]
0x180008099  mov     rbx, rcx
0x18000809c  movdqa  xmm0, xmm1
0x1800080a0  movq    r14, xmm1
0x1800080a5  psrldq  xmm0, 8
0x1800080aa  movq    r15, xmm0
0x1800080af  test    rsi, rsi
0x1800080b2  jz      short loc_1800080C3
0x1800080b4  mov     rcx, rsi; SRWLock
0x1800080b7  call    cs:__imp_ReleaseSRWLockExclusive
0x1800080be  nop     dword ptr [rax+rax+00h]
0x1800080c3  test    r14, r14
0x1800080c6  jz      short loc_1800080D3
0x1800080c8  mov     rcx, r15
0x1800080cb  mov     rax, r14
0x1800080ce  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800080d3  test    rbp, rbp
0x1800080d6  jz      short loc_1800080E7
0x1800080d8  mov     rcx, rbp; lpCriticalSection
0x1800080db  call    cs:__imp_LeaveCriticalSection
0x1800080e2  nop     dword ptr [rax+rax+00h]
0x1800080e7  cmp     rbx, rdi
0x1800080ea  jb      loc_180008044
0x1800080f0  mov     rbx, [rsp+38h+arg_0]
0x1800080f5  mov     rbp, [rsp+38h+arg_8]
0x1800080fa  mov     rsi, [rsp+38h+arg_10]
0x1800080ff  add     rsp, 20h
0x180008103  pop     r15
0x180008105  pop     r14
0x180008107  pop     rdi
0x180008108  retn
```
