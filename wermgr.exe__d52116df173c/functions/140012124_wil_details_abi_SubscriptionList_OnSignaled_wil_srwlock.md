# wil::details_abi::SubscriptionList::OnSignaled(wil::srwlock &)

- ea: `0x140012124`
- end: `0x1400121e1`
- name: `?OnSignaled@SubscriptionList@details_abi@wil@@QEAAXAEAVsrwlock@3@@Z`
- size: `189`
- prototype: `void __fastcall(LPCRITICAL_SECTION lpCriticalSection, PSRWLOCK SRWLock)`
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x14000f770`
- `0x14000f7a0`
- `0x14000f850`
- `0x1400144d0`

## callees

- `0x140012124`
- `0x14001e010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1400121ab`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1400121ab`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x14001213a`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x14001213a`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x140012154`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x140012154`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1400121c9`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1400121c9`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x14001216a`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x14001216a`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x140012173`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x140012173`

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
0x140012124  push    rbx
0x140012126  push    rbp
0x140012127  push    rsi
0x140012128  push    rdi
0x140012129  push    r14
0x14001212b  push    r15
0x14001212d  sub     rsp, 28h
0x140012131  mov     rbp, rdx
0x140012134  mov     rsi, rcx
0x140012137  mov     rcx, rdx; SRWLock
0x14001213a  call    cs:__imp_AcquireSRWLockShared
0x140012140  mov     rdi, [rsi+30h]
0x140012144  sub     rdi, [rsi+28h]
0x140012148  shr     rdi, 4
0x14001214c  test    rbp, rbp
0x14001214f  jz      short loc_14001215A
0x140012151  mov     rcx, rbp; SRWLock
0x140012154  call    cs:__imp_ReleaseSRWLockShared
0x14001215a  xor     ebx, ebx
0x14001215c  test    rdi, rdi
0x14001215f  jz      short loc_1400121D4
0x140012161  xor     r14d, r14d
0x140012164  xor     r15d, r15d
0x140012167  mov     rcx, rsi; lpCriticalSection
0x14001216a  call    cs:__imp_EnterCriticalSection
0x140012170  mov     rcx, rbp; SRWLock
0x140012173  call    cs:__imp_AcquireSRWLockExclusive
0x140012179  cmp     rbx, rdi
0x14001217c  jnb     short loc_1400121A3
0x14001217e  mov     rdx, [rsi+28h]
0x140012182  lea     rax, [rbx+1]
0x140012186  add     rbx, rbx
0x140012189  lea     rcx, [rdx+rbx*8]
0x14001218d  mov     rbx, rax
0x140012190  cmp     [rcx], r14
0x140012193  jnz     short loc_14001219C
0x140012195  cmp     rax, rdi
0x140012198  jb      short loc_140012182
0x14001219a  jmp     short loc_1400121A3
0x14001219c  mov     r14, [rcx]
0x14001219f  mov     r15, [rcx+8]
0x1400121a3  test    rbp, rbp
0x1400121a6  jz      short loc_1400121B1
0x1400121a8  mov     rcx, rbp; SRWLock
0x1400121ab  call    cs:__imp_ReleaseSRWLockExclusive
0x1400121b1  test    r14, r14
0x1400121b4  jz      short loc_1400121C1
0x1400121b6  mov     rcx, r15
0x1400121b9  mov     rax, r14
0x1400121bc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400121c1  test    rsi, rsi
0x1400121c4  jz      short loc_1400121CF
0x1400121c6  mov     rcx, rsi; lpCriticalSection
0x1400121c9  call    cs:__imp_LeaveCriticalSection
0x1400121cf  cmp     rbx, rdi
0x1400121d2  jb      short loc_140012161
0x1400121d4  add     rsp, 28h
0x1400121d8  pop     r15
0x1400121da  pop     r14
0x1400121dc  pop     rdi
0x1400121dd  pop     rsi
0x1400121de  pop     rbp
0x1400121df  pop     rbx
0x1400121e0  retn
```
