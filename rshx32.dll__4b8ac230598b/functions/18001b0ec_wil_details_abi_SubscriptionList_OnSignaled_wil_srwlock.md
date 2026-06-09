# wil::details_abi::SubscriptionList::OnSignaled(wil::srwlock &)

- ea: `0x18001b0ec`
- end: `0x18001b1a9`
- name: `?OnSignaled@SubscriptionList@details_abi@wil@@QEAAXAEAVsrwlock@3@@Z`
- size: `189`
- prototype: `void __fastcall(LPCRITICAL_SECTION lpCriticalSection, PSRWLOCK SRWLock)`
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x1800198f0`
- `0x180019920`
- `0x1800199d0`
- `0x18001c980`

## callees

- `0x18001b0ec`
- `0x18001e010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001b173`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001b173`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18001b13b`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18001b13b`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001b132`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001b132`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001b191`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001b191`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18001b11c`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18001b11c`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18001b102`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18001b102`

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
0x18001b0ec  push    rbx
0x18001b0ee  push    rbp
0x18001b0ef  push    rsi
0x18001b0f0  push    rdi
0x18001b0f1  push    r14
0x18001b0f3  push    r15
0x18001b0f5  sub     rsp, 28h
0x18001b0f9  mov     rsi, rcx
0x18001b0fc  mov     rbp, rdx
0x18001b0ff  mov     rcx, rdx; SRWLock
0x18001b102  call    cs:__imp_AcquireSRWLockShared
0x18001b108  mov     rdi, [rsi+30h]
0x18001b10c  sub     rdi, [rsi+28h]
0x18001b110  shr     rdi, 4
0x18001b114  test    rbp, rbp
0x18001b117  jz      short loc_18001B122
0x18001b119  mov     rcx, rbp; SRWLock
0x18001b11c  call    cs:__imp_ReleaseSRWLockShared
0x18001b122  xor     ebx, ebx
0x18001b124  test    rdi, rdi
0x18001b127  jz      short loc_18001B19C
0x18001b129  mov     rcx, rsi; lpCriticalSection
0x18001b12c  xor     r14d, r14d
0x18001b12f  xor     r15d, r15d
0x18001b132  call    cs:__imp_EnterCriticalSection
0x18001b138  mov     rcx, rbp; SRWLock
0x18001b13b  call    cs:__imp_AcquireSRWLockExclusive
0x18001b141  cmp     rbx, rdi
0x18001b144  jnb     short loc_18001B16B
0x18001b146  mov     rdx, [rsi+28h]
0x18001b14a  lea     rax, [rbx+1]
0x18001b14e  add     rbx, rbx
0x18001b151  lea     rcx, [rdx+rbx*8]
0x18001b155  mov     rbx, rax
0x18001b158  cmp     [rcx], r14
0x18001b15b  jnz     short loc_18001B164
0x18001b15d  cmp     rax, rdi
0x18001b160  jb      short loc_18001B14A
0x18001b162  jmp     short loc_18001B16B
0x18001b164  mov     r14, [rcx]
0x18001b167  mov     r15, [rcx+8]
0x18001b16b  test    rbp, rbp
0x18001b16e  jz      short loc_18001B179
0x18001b170  mov     rcx, rbp; SRWLock
0x18001b173  call    cs:__imp_ReleaseSRWLockExclusive
0x18001b179  test    r14, r14
0x18001b17c  jz      short loc_18001B189
0x18001b17e  mov     rcx, r15
0x18001b181  mov     rax, r14
0x18001b184  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b189  test    rsi, rsi
0x18001b18c  jz      short loc_18001B197
0x18001b18e  mov     rcx, rsi; lpCriticalSection
0x18001b191  call    cs:__imp_LeaveCriticalSection
0x18001b197  cmp     rbx, rdi
0x18001b19a  jb      short loc_18001B129
0x18001b19c  add     rsp, 28h
0x18001b1a0  pop     r15
0x18001b1a2  pop     r14
0x18001b1a4  pop     rdi
0x18001b1a5  pop     rsi
0x18001b1a6  pop     rbp
0x18001b1a7  pop     rbx
0x18001b1a8  retn
```
