# wil::details_abi::SubscriptionList::OnSignaled(wil::srwlock &)

- ea: `0x18000c35c`
- end: `0x18000c419`
- name: `?OnSignaled@SubscriptionList@details_abi@wil@@QEAAXAEAVsrwlock@3@@Z`
- size: `189`
- prototype: `void __fastcall(LPCRITICAL_SECTION lpCriticalSection, PSRWLOCK SRWLock)`
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x18000aa30`
- `0x18000aa60`
- `0x18000ab10`
- `0x18000dc00`

## callees

- `0x18000c35c`
- `0x18000f010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000c3ab`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000c3ab`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000c3e3`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000c3e3`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18000c372`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18000c372`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18000c38c`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18000c38c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000c401`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000c401`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000c3a2`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000c3a2`

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
0x18000c35c  push    rbx
0x18000c35e  push    rbp
0x18000c35f  push    rsi
0x18000c360  push    rdi
0x18000c361  push    r14
0x18000c363  push    r15
0x18000c365  sub     rsp, 28h
0x18000c369  mov     rbp, rdx
0x18000c36c  mov     rsi, rcx
0x18000c36f  mov     rcx, rdx; SRWLock
0x18000c372  call    cs:__imp_AcquireSRWLockShared
0x18000c378  mov     rdi, [rsi+30h]
0x18000c37c  sub     rdi, [rsi+28h]
0x18000c380  shr     rdi, 4
0x18000c384  test    rbp, rbp
0x18000c387  jz      short loc_18000C392
0x18000c389  mov     rcx, rbp; SRWLock
0x18000c38c  call    cs:__imp_ReleaseSRWLockShared
0x18000c392  xor     ebx, ebx
0x18000c394  test    rdi, rdi
0x18000c397  jz      short loc_18000C40C
0x18000c399  xor     r14d, r14d
0x18000c39c  xor     r15d, r15d
0x18000c39f  mov     rcx, rsi; lpCriticalSection
0x18000c3a2  call    cs:__imp_EnterCriticalSection
0x18000c3a8  mov     rcx, rbp; SRWLock
0x18000c3ab  call    cs:__imp_AcquireSRWLockExclusive
0x18000c3b1  cmp     rbx, rdi
0x18000c3b4  jnb     short loc_18000C3DB
0x18000c3b6  mov     rdx, [rsi+28h]
0x18000c3ba  lea     rax, [rbx+1]
0x18000c3be  add     rbx, rbx
0x18000c3c1  lea     rcx, [rdx+rbx*8]
0x18000c3c5  mov     rbx, rax
0x18000c3c8  cmp     [rcx], r14
0x18000c3cb  jnz     short loc_18000C3D4
0x18000c3cd  cmp     rax, rdi
0x18000c3d0  jb      short loc_18000C3BA
0x18000c3d2  jmp     short loc_18000C3DB
0x18000c3d4  mov     r14, [rcx]
0x18000c3d7  mov     r15, [rcx+8]
0x18000c3db  test    rbp, rbp
0x18000c3de  jz      short loc_18000C3E9
0x18000c3e0  mov     rcx, rbp; SRWLock
0x18000c3e3  call    cs:__imp_ReleaseSRWLockExclusive
0x18000c3e9  test    r14, r14
0x18000c3ec  jz      short loc_18000C3F9
0x18000c3ee  mov     rcx, r15
0x18000c3f1  mov     rax, r14
0x18000c3f4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c3f9  test    rsi, rsi
0x18000c3fc  jz      short loc_18000C407
0x18000c3fe  mov     rcx, rsi; lpCriticalSection
0x18000c401  call    cs:__imp_LeaveCriticalSection
0x18000c407  cmp     rbx, rdi
0x18000c40a  jb      short loc_18000C399
0x18000c40c  add     rsp, 28h
0x18000c410  pop     r15
0x18000c412  pop     r14
0x18000c414  pop     rdi
0x18000c415  pop     rsi
0x18000c416  pop     rbp
0x18000c417  pop     rbx
0x18000c418  retn
```
