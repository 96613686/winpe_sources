# wil::details_abi::SubscriptionList::OnSignaled(wil::srwlock &)

- ea: `0x180007c64`
- end: `0x180007d21`
- name: `?OnSignaled@SubscriptionList@details_abi@wil@@QEAAXAEAVsrwlock@3@@Z`
- size: `189`
- prototype: `void __fastcall(LPCRITICAL_SECTION lpCriticalSection, PSRWLOCK SRWLock)`
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x180002bb0`
- `0x180002be0`
- `0x180002ce0`
- `0x18000bf70`

## callees

- `0x180007c64`
- `0x18001b010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180007c94`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180007c94`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180007cb3`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180007cb3`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180007ceb`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180007ceb`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180007d09`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180007d09`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180007c7a`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180007c7a`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180007caa`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180007caa`

## pseudocode

```c
void __fastcall wil::details_abi::SubscriptionList::OnSignaled(LPCRITICAL_SECTION lpCriticalSection, PSRWLOCK SRWLock)
{
  unsigned __int64 v4; // rdi
  unsigned __int64 v5; // rbx
  void (__fastcall *v6)(__int64); // r14
  __int64 v7; // r15
  unsigned __int64 v8; // rax
  WORD *v9; // rcx

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
      while ( 1 )
      {
        v8 = v5 + 1;
        v9 = &lpCriticalSection[1].DebugInfo->Type + 8 * v5++;
        if ( *(_QWORD *)v9 )
          break;
        if ( v8 >= v4 )
          goto LABEL_9;
      }
      v6 = *(void (__fastcall **)(__int64))v9;
      v7 = *((_QWORD *)v9 + 1);
    }
LABEL_9:
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
0x180007c64  push    rbx
0x180007c66  push    rbp
0x180007c67  push    rsi
0x180007c68  push    rdi
0x180007c69  push    r14
0x180007c6b  push    r15
0x180007c6d  sub     rsp, 28h
0x180007c71  mov     rbp, rdx
0x180007c74  mov     rsi, rcx
0x180007c77  mov     rcx, rdx; SRWLock
0x180007c7a  call    cs:__imp_AcquireSRWLockShared
0x180007c80  mov     rdi, [rsi+30h]
0x180007c84  sub     rdi, [rsi+28h]
0x180007c88  shr     rdi, 4
0x180007c8c  test    rbp, rbp
0x180007c8f  jz      short loc_180007C9A
0x180007c91  mov     rcx, rbp; SRWLock
0x180007c94  call    cs:__imp_ReleaseSRWLockShared
0x180007c9a  xor     ebx, ebx
0x180007c9c  test    rdi, rdi
0x180007c9f  jz      short loc_180007D14
0x180007ca1  xor     r14d, r14d
0x180007ca4  xor     r15d, r15d
0x180007ca7  mov     rcx, rsi; lpCriticalSection
0x180007caa  call    cs:__imp_EnterCriticalSection
0x180007cb0  mov     rcx, rbp; SRWLock
0x180007cb3  call    cs:__imp_AcquireSRWLockExclusive
0x180007cb9  cmp     rbx, rdi
0x180007cbc  jnb     short loc_180007CE3
0x180007cbe  mov     rdx, [rsi+28h]
0x180007cc2  lea     rax, [rbx+1]
0x180007cc6  add     rbx, rbx
0x180007cc9  lea     rcx, [rdx+rbx*8]
0x180007ccd  mov     rbx, rax
0x180007cd0  cmp     [rcx], r14
0x180007cd3  jnz     short loc_180007CDC
0x180007cd5  cmp     rax, rdi
0x180007cd8  jb      short loc_180007CC2
0x180007cda  jmp     short loc_180007CE3
0x180007cdc  mov     r14, [rcx]
0x180007cdf  mov     r15, [rcx+8]
0x180007ce3  test    rbp, rbp
0x180007ce6  jz      short loc_180007CF1
0x180007ce8  mov     rcx, rbp; SRWLock
0x180007ceb  call    cs:__imp_ReleaseSRWLockExclusive
0x180007cf1  test    r14, r14
0x180007cf4  jz      short loc_180007D01
0x180007cf6  mov     rcx, r15
0x180007cf9  mov     rax, r14
0x180007cfc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007d01  test    rsi, rsi
0x180007d04  jz      short loc_180007D0F
0x180007d06  mov     rcx, rsi; lpCriticalSection
0x180007d09  call    cs:__imp_LeaveCriticalSection
0x180007d0f  cmp     rbx, rdi
0x180007d12  jb      short loc_180007CA1
0x180007d14  add     rsp, 28h
0x180007d18  pop     r15
0x180007d1a  pop     r14
0x180007d1c  pop     rdi
0x180007d1d  pop     rsi
0x180007d1e  pop     rbp
0x180007d1f  pop     rbx
0x180007d20  retn
```
