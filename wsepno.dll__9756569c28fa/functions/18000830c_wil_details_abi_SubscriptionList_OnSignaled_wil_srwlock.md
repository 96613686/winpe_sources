# wil::details_abi::SubscriptionList::OnSignaled(wil::srwlock &)

- ea: `0x18000830c`
- end: `0x1800083c9`
- name: `?OnSignaled@SubscriptionList@details_abi@wil@@QEAAXAEAVsrwlock@3@@Z`
- size: `189`
- prototype: `void __fastcall(LPCRITICAL_SECTION lpCriticalSection, PSRWLOCK SRWLock)`
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x180003d50`
- `0x180003d80`
- `0x180003e80`
- `0x18000aeb0`

## callees

- `0x18000830c`
- `0x18000f010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800083b1`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800083b1`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180008352`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180008352`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000835b`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000835b`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180008393`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180008393`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18000833c`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18000833c`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180008322`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180008322`

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
0x18000830c  push    rbx
0x18000830e  push    rbp
0x18000830f  push    rsi
0x180008310  push    rdi
0x180008311  push    r14
0x180008313  push    r15
0x180008315  sub     rsp, 28h
0x180008319  mov     rbp, rdx
0x18000831c  mov     rsi, rcx
0x18000831f  mov     rcx, rdx; SRWLock
0x180008322  call    cs:__imp_AcquireSRWLockShared
0x180008328  mov     rdi, [rsi+30h]
0x18000832c  sub     rdi, [rsi+28h]
0x180008330  shr     rdi, 4
0x180008334  test    rbp, rbp
0x180008337  jz      short loc_180008342
0x180008339  mov     rcx, rbp; SRWLock
0x18000833c  call    cs:__imp_ReleaseSRWLockShared
0x180008342  xor     ebx, ebx
0x180008344  test    rdi, rdi
0x180008347  jz      short loc_1800083BC
0x180008349  xor     r14d, r14d
0x18000834c  xor     r15d, r15d
0x18000834f  mov     rcx, rsi; lpCriticalSection
0x180008352  call    cs:__imp_EnterCriticalSection
0x180008358  mov     rcx, rbp; SRWLock
0x18000835b  call    cs:__imp_AcquireSRWLockExclusive
0x180008361  cmp     rbx, rdi
0x180008364  jnb     short loc_18000838B
0x180008366  mov     rdx, [rsi+28h]
0x18000836a  lea     rax, [rbx+1]
0x18000836e  add     rbx, rbx
0x180008371  lea     rcx, [rdx+rbx*8]
0x180008375  mov     rbx, rax
0x180008378  cmp     [rcx], r14
0x18000837b  jnz     short loc_180008384
0x18000837d  cmp     rax, rdi
0x180008380  jb      short loc_18000836A
0x180008382  jmp     short loc_18000838B
0x180008384  mov     r14, [rcx]
0x180008387  mov     r15, [rcx+8]
0x18000838b  test    rbp, rbp
0x18000838e  jz      short loc_180008399
0x180008390  mov     rcx, rbp; SRWLock
0x180008393  call    cs:__imp_ReleaseSRWLockExclusive
0x180008399  test    r14, r14
0x18000839c  jz      short loc_1800083A9
0x18000839e  mov     rcx, r15
0x1800083a1  mov     rax, r14
0x1800083a4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800083a9  test    rsi, rsi
0x1800083ac  jz      short loc_1800083B7
0x1800083ae  mov     rcx, rsi; lpCriticalSection
0x1800083b1  call    cs:__imp_LeaveCriticalSection
0x1800083b7  cmp     rbx, rdi
0x1800083ba  jb      short loc_180008349
0x1800083bc  add     rsp, 28h
0x1800083c0  pop     r15
0x1800083c2  pop     r14
0x1800083c4  pop     rdi
0x1800083c5  pop     rsi
0x1800083c6  pop     rbp
0x1800083c7  pop     rbx
0x1800083c8  retn
```
