# wil::details_abi::SubscriptionList::OnSignaled(wil::srwlock &)

- ea: `0x140009200`
- end: `0x1400092bd`
- name: `?OnSignaled@SubscriptionList@details_abi@wil@@QEAAXAEAVsrwlock@3@@Z`
- size: `189`
- prototype: `void __fastcall(LPCRITICAL_SECTION lpCriticalSection, PSRWLOCK SRWLock)`
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x140008250`
- `0x140008280`
- `0x140008330`
- `0x14000a710`

## callees

- `0x140009200`
- `0x14000c010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x140009246`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x140009246`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1400092a5`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1400092a5`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x140009287`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x140009287`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x140009216`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x140009216`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x14000924f`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x14000924f`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x140009230`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x140009230`

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
0x140009200  push    rbx
0x140009202  push    rbp
0x140009203  push    rsi
0x140009204  push    rdi
0x140009205  push    r14
0x140009207  push    r15
0x140009209  sub     rsp, 28h
0x14000920d  mov     rsi, rcx
0x140009210  mov     rbp, rdx
0x140009213  mov     rcx, rdx; SRWLock
0x140009216  call    cs:__imp_AcquireSRWLockShared
0x14000921c  mov     rdi, [rsi+30h]
0x140009220  sub     rdi, [rsi+28h]
0x140009224  shr     rdi, 4
0x140009228  test    rbp, rbp
0x14000922b  jz      short loc_140009236
0x14000922d  mov     rcx, rbp; SRWLock
0x140009230  call    cs:__imp_ReleaseSRWLockShared
0x140009236  xor     ebx, ebx
0x140009238  test    rdi, rdi
0x14000923b  jz      short loc_1400092B0
0x14000923d  mov     rcx, rsi; lpCriticalSection
0x140009240  xor     r14d, r14d
0x140009243  xor     r15d, r15d
0x140009246  call    cs:__imp_EnterCriticalSection
0x14000924c  mov     rcx, rbp; SRWLock
0x14000924f  call    cs:__imp_AcquireSRWLockExclusive
0x140009255  cmp     rbx, rdi
0x140009258  jnb     short loc_14000927F
0x14000925a  mov     rdx, [rsi+28h]
0x14000925e  lea     rax, [rbx+1]
0x140009262  add     rbx, rbx
0x140009265  lea     rcx, [rdx+rbx*8]
0x140009269  mov     rbx, rax
0x14000926c  cmp     [rcx], r14
0x14000926f  jnz     short loc_140009278
0x140009271  cmp     rax, rdi
0x140009274  jb      short loc_14000925E
0x140009276  jmp     short loc_14000927F
0x140009278  mov     r14, [rcx]
0x14000927b  mov     r15, [rcx+8]
0x14000927f  test    rbp, rbp
0x140009282  jz      short loc_14000928D
0x140009284  mov     rcx, rbp; SRWLock
0x140009287  call    cs:__imp_ReleaseSRWLockExclusive
0x14000928d  test    r14, r14
0x140009290  jz      short loc_14000929D
0x140009292  mov     rcx, r15
0x140009295  mov     rax, r14
0x140009298  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000929d  test    rsi, rsi
0x1400092a0  jz      short loc_1400092AB
0x1400092a2  mov     rcx, rsi; lpCriticalSection
0x1400092a5  call    cs:__imp_LeaveCriticalSection
0x1400092ab  cmp     rbx, rdi
0x1400092ae  jb      short loc_14000923D
0x1400092b0  add     rsp, 28h
0x1400092b4  pop     r15
0x1400092b6  pop     r14
0x1400092b8  pop     rdi
0x1400092b9  pop     rsi
0x1400092ba  pop     rbp
0x1400092bb  pop     rbx
0x1400092bc  retn
```
