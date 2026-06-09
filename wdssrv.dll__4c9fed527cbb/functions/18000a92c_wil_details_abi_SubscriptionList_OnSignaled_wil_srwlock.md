# wil::details_abi::SubscriptionList::OnSignaled(wil::srwlock &)

- ea: `0x18000a92c`
- end: `0x18000aa4a`
- name: `?OnSignaled@SubscriptionList@details_abi@wil@@QEAAXAEAVsrwlock@3@@Z`
- size: `286`
- prototype: `void __fastcall(LPCRITICAL_SECTION lpCriticalSection, PSRWLOCK SRWLock)`
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x180006420`
- `0x180006450`
- `0x180006560`
- `0x18000e4f0`

## callees

- `0x18000a92c`
- `0x18001d010`

## import_xrefs

- `KERNEL32!LeaveCriticalSection` at `0x18000aa1b`
- `KERNEL32!LeaveCriticalSection` at `0x18000aa1b`
- `KERNEL32!EnterCriticalSection` at `0x18000a98d`
- `KERNEL32!EnterCriticalSection` at `0x18000a98d`
- `KERNEL32!AcquireSRWLockExclusive` at `0x18000a99c`
- `KERNEL32!AcquireSRWLockExclusive` at `0x18000a99c`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x18000a9f7`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x18000a9f7`
- `KERNEL32!AcquireSRWLockShared` at `0x18000a94d`
- `KERNEL32!AcquireSRWLockShared` at `0x18000a94d`
- `KERNEL32!ReleaseSRWLockShared` at `0x18000a96d`
- `KERNEL32!ReleaseSRWLockShared` at `0x18000a96d`

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
0x18000a92c  mov     [rsp+arg_0], rbx
0x18000a931  mov     [rsp+arg_8], rbp
0x18000a936  mov     [rsp+arg_10], rsi
0x18000a93b  push    rdi
0x18000a93c  push    r14
0x18000a93e  push    r15
0x18000a940  sub     rsp, 20h
0x18000a944  mov     rbp, rcx
0x18000a947  mov     rsi, rdx
0x18000a94a  mov     rcx, rdx; SRWLock
0x18000a94d  call    cs:__imp_AcquireSRWLockShared
0x18000a954  nop     dword ptr [rax+rax+00h]
0x18000a959  mov     rdi, [rbp+30h]
0x18000a95d  sub     rdi, [rbp+28h]
0x18000a961  shr     rdi, 4
0x18000a965  test    rsi, rsi
0x18000a968  jz      short loc_18000A979
0x18000a96a  mov     rcx, rsi; SRWLock
0x18000a96d  call    cs:__imp_ReleaseSRWLockShared
0x18000a974  nop     dword ptr [rax+rax+00h]
0x18000a979  xor     ebx, ebx
0x18000a97b  test    rdi, rdi
0x18000a97e  jz      loc_18000AA30
0x18000a984  mov     rcx, rbp; lpCriticalSection
0x18000a987  xor     r14d, r14d
0x18000a98a  xor     r15d, r15d
0x18000a98d  call    cs:__imp_EnterCriticalSection
0x18000a994  nop     dword ptr [rax+rax+00h]
0x18000a999  mov     rcx, rsi; SRWLock
0x18000a99c  call    cs:__imp_AcquireSRWLockExclusive
0x18000a9a3  nop     dword ptr [rax+rax+00h]
0x18000a9a8  cmp     rbx, rdi
0x18000a9ab  jnb     short loc_18000A9EF
0x18000a9ad  mov     rdx, [rbp+28h]
0x18000a9b1  mov     rax, rbx
0x18000a9b4  shl     rax, 4
0x18000a9b8  add     rax, rdx
0x18000a9bb  lea     rcx, [rbx+1]
0x18000a9bf  cmp     [rax], r14
0x18000a9c2  jnz     short loc_18000A9D2
0x18000a9c4  add     rax, 10h
0x18000a9c8  mov     rbx, rcx
0x18000a9cb  cmp     rcx, rdi
0x18000a9ce  jb      short loc_18000A9BB
0x18000a9d0  jmp     short loc_18000A9EF
0x18000a9d2  add     rbx, rbx
0x18000a9d5  movups  xmm1, xmmword ptr [rdx+rbx*8]
0x18000a9d9  mov     rbx, rcx
0x18000a9dc  movdqa  xmm0, xmm1
0x18000a9e0  movq    r14, xmm1
0x18000a9e5  psrldq  xmm0, 8
0x18000a9ea  movq    r15, xmm0
0x18000a9ef  test    rsi, rsi
0x18000a9f2  jz      short loc_18000AA03
0x18000a9f4  mov     rcx, rsi; SRWLock
0x18000a9f7  call    cs:__imp_ReleaseSRWLockExclusive
0x18000a9fe  nop     dword ptr [rax+rax+00h]
0x18000aa03  test    r14, r14
0x18000aa06  jz      short loc_18000AA13
0x18000aa08  mov     rcx, r15
0x18000aa0b  mov     rax, r14
0x18000aa0e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000aa13  test    rbp, rbp
0x18000aa16  jz      short loc_18000AA27
0x18000aa18  mov     rcx, rbp; lpCriticalSection
0x18000aa1b  call    cs:__imp_LeaveCriticalSection
0x18000aa22  nop     dword ptr [rax+rax+00h]
0x18000aa27  cmp     rbx, rdi
0x18000aa2a  jb      loc_18000A984
0x18000aa30  mov     rbx, [rsp+38h+arg_0]
0x18000aa35  mov     rbp, [rsp+38h+arg_8]
0x18000aa3a  mov     rsi, [rsp+38h+arg_10]
0x18000aa3f  add     rsp, 20h
0x18000aa43  pop     r15
0x18000aa45  pop     r14
0x18000aa47  pop     rdi
0x18000aa48  retn
```
