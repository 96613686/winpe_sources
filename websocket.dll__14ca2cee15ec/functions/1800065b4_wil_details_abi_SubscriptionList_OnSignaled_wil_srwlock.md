# wil::details_abi::SubscriptionList::OnSignaled(wil::srwlock &)

- ea: `0x1800065b4`
- end: `0x180006671`
- name: `?OnSignaled@SubscriptionList@details_abi@wil@@QEAAXAEAVsrwlock@3@@Z`
- size: `189`
- prototype: `void __fastcall(LPCRITICAL_SECTION lpCriticalSection, PSRWLOCK SRWLock)`
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x180002a60`
- `0x180002a90`
- `0x180002b40`
- `0x1800087d0`

## callees

- `0x1800065b4`
- `0x18000e010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180006603`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180006603`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000663b`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000663b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180006659`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180006659`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800065fa`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800065fa`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x1800065ca`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x1800065ca`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x1800065e4`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x1800065e4`

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
0x1800065b4  push    rbx
0x1800065b6  push    rbp
0x1800065b7  push    rsi
0x1800065b8  push    rdi
0x1800065b9  push    r14
0x1800065bb  push    r15
0x1800065bd  sub     rsp, 28h
0x1800065c1  mov     rsi, rcx
0x1800065c4  mov     rbp, rdx
0x1800065c7  mov     rcx, rdx; SRWLock
0x1800065ca  call    cs:__imp_AcquireSRWLockShared
0x1800065d0  mov     rdi, [rsi+30h]
0x1800065d4  sub     rdi, [rsi+28h]
0x1800065d8  shr     rdi, 4
0x1800065dc  test    rbp, rbp
0x1800065df  jz      short loc_1800065EA
0x1800065e1  mov     rcx, rbp; SRWLock
0x1800065e4  call    cs:__imp_ReleaseSRWLockShared
0x1800065ea  xor     ebx, ebx
0x1800065ec  test    rdi, rdi
0x1800065ef  jz      short loc_180006664
0x1800065f1  mov     rcx, rsi; lpCriticalSection
0x1800065f4  xor     r14d, r14d
0x1800065f7  xor     r15d, r15d
0x1800065fa  call    cs:__imp_EnterCriticalSection
0x180006600  mov     rcx, rbp; SRWLock
0x180006603  call    cs:__imp_AcquireSRWLockExclusive
0x180006609  cmp     rbx, rdi
0x18000660c  jnb     short loc_180006633
0x18000660e  mov     rdx, [rsi+28h]
0x180006612  lea     rax, [rbx+1]
0x180006616  add     rbx, rbx
0x180006619  lea     rcx, [rdx+rbx*8]
0x18000661d  mov     rbx, rax
0x180006620  cmp     [rcx], r14
0x180006623  jnz     short loc_18000662C
0x180006625  cmp     rax, rdi
0x180006628  jb      short loc_180006612
0x18000662a  jmp     short loc_180006633
0x18000662c  mov     r14, [rcx]
0x18000662f  mov     r15, [rcx+8]
0x180006633  test    rbp, rbp
0x180006636  jz      short loc_180006641
0x180006638  mov     rcx, rbp; SRWLock
0x18000663b  call    cs:__imp_ReleaseSRWLockExclusive
0x180006641  test    r14, r14
0x180006644  jz      short loc_180006651
0x180006646  mov     rcx, r15
0x180006649  mov     rax, r14
0x18000664c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006651  test    rsi, rsi
0x180006654  jz      short loc_18000665F
0x180006656  mov     rcx, rsi; lpCriticalSection
0x180006659  call    cs:__imp_LeaveCriticalSection
0x18000665f  cmp     rbx, rdi
0x180006662  jb      short loc_1800065F1
0x180006664  add     rsp, 28h
0x180006668  pop     r15
0x18000666a  pop     r14
0x18000666c  pop     rdi
0x18000666d  pop     rsi
0x18000666e  pop     rbp
0x18000666f  pop     rbx
0x180006670  retn
```
