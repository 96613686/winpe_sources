# wil::details_abi::SubscriptionList::OnSignaled(wil::srwlock &)

- ea: `0x140007684`
- end: `0x140007741`
- name: `?OnSignaled@SubscriptionList@details_abi@wil@@QEAAXAEAVsrwlock@3@@Z`
- size: `189`
- prototype: `void __fastcall(LPCRITICAL_SECTION lpCriticalSection, PSRWLOCK SRWLock)`
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x1400042d0`
- `0x140004300`
- `0x1400043b0`
- `0x140009b30`

## callees

- `0x140007684`
- `0x14000e010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x140007729`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x140007729`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1400076ca`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1400076ca`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x1400076b4`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x1400076b4`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x14000770b`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x14000770b`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x14000769a`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x14000769a`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1400076d3`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1400076d3`

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
0x140007684  push    rbx
0x140007686  push    rbp
0x140007687  push    rsi
0x140007688  push    rdi
0x140007689  push    r14
0x14000768b  push    r15
0x14000768d  sub     rsp, 28h
0x140007691  mov     rsi, rcx
0x140007694  mov     rbp, rdx
0x140007697  mov     rcx, rdx; SRWLock
0x14000769a  call    cs:__imp_AcquireSRWLockShared
0x1400076a0  mov     rdi, [rsi+30h]
0x1400076a4  sub     rdi, [rsi+28h]
0x1400076a8  shr     rdi, 4
0x1400076ac  test    rbp, rbp
0x1400076af  jz      short loc_1400076BA
0x1400076b1  mov     rcx, rbp; SRWLock
0x1400076b4  call    cs:__imp_ReleaseSRWLockShared
0x1400076ba  xor     ebx, ebx
0x1400076bc  test    rdi, rdi
0x1400076bf  jz      short loc_140007734
0x1400076c1  mov     rcx, rsi; lpCriticalSection
0x1400076c4  xor     r14d, r14d
0x1400076c7  xor     r15d, r15d
0x1400076ca  call    cs:__imp_EnterCriticalSection
0x1400076d0  mov     rcx, rbp; SRWLock
0x1400076d3  call    cs:__imp_AcquireSRWLockExclusive
0x1400076d9  cmp     rbx, rdi
0x1400076dc  jnb     short loc_140007703
0x1400076de  mov     rdx, [rsi+28h]
0x1400076e2  lea     rax, [rbx+1]
0x1400076e6  add     rbx, rbx
0x1400076e9  lea     rcx, [rdx+rbx*8]
0x1400076ed  mov     rbx, rax
0x1400076f0  cmp     [rcx], r14
0x1400076f3  jnz     short loc_1400076FC
0x1400076f5  cmp     rax, rdi
0x1400076f8  jb      short loc_1400076E2
0x1400076fa  jmp     short loc_140007703
0x1400076fc  mov     r14, [rcx]
0x1400076ff  mov     r15, [rcx+8]
0x140007703  test    rbp, rbp
0x140007706  jz      short loc_140007711
0x140007708  mov     rcx, rbp; SRWLock
0x14000770b  call    cs:__imp_ReleaseSRWLockExclusive
0x140007711  test    r14, r14
0x140007714  jz      short loc_140007721
0x140007716  mov     rcx, r15
0x140007719  mov     rax, r14
0x14000771c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140007721  test    rsi, rsi
0x140007724  jz      short loc_14000772F
0x140007726  mov     rcx, rsi; lpCriticalSection
0x140007729  call    cs:__imp_LeaveCriticalSection
0x14000772f  cmp     rbx, rdi
0x140007732  jb      short loc_1400076C1
0x140007734  add     rsp, 28h
0x140007738  pop     r15
0x14000773a  pop     r14
0x14000773c  pop     rdi
0x14000773d  pop     rsi
0x14000773e  pop     rbp
0x14000773f  pop     rbx
0x140007740  retn
```
