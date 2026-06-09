# wil::details_abi::SubscriptionList::OnSignaled(wil::srwlock &)

- ea: `0x18000c290`
- end: `0x18000c34d`
- name: `?OnSignaled@SubscriptionList@details_abi@wil@@QEAAXAEAVsrwlock@3@@Z`
- size: `189`
- prototype: `void __fastcall(LPCRITICAL_SECTION lpCriticalSection, PSRWLOCK SRWLock)`
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x1800080a0`
- `0x1800080d0`
- `0x180008180`
- `0x18000eb10`

## callees

- `0x18000c290`
- `0x180013010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000c317`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000c317`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000c2d6`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000c2d6`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000c2df`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000c2df`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000c335`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000c335`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18000c2c0`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18000c2c0`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18000c2a6`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18000c2a6`

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
0x18000c290  push    rbx
0x18000c292  push    rbp
0x18000c293  push    rsi
0x18000c294  push    rdi
0x18000c295  push    r14
0x18000c297  push    r15
0x18000c299  sub     rsp, 28h
0x18000c29d  mov     rsi, rcx
0x18000c2a0  mov     rbp, rdx
0x18000c2a3  mov     rcx, rdx; SRWLock
0x18000c2a6  call    cs:__imp_AcquireSRWLockShared
0x18000c2ac  mov     rdi, [rsi+30h]
0x18000c2b0  sub     rdi, [rsi+28h]
0x18000c2b4  shr     rdi, 4
0x18000c2b8  test    rbp, rbp
0x18000c2bb  jz      short loc_18000C2C6
0x18000c2bd  mov     rcx, rbp; SRWLock
0x18000c2c0  call    cs:__imp_ReleaseSRWLockShared
0x18000c2c6  xor     ebx, ebx
0x18000c2c8  test    rdi, rdi
0x18000c2cb  jz      short loc_18000C340
0x18000c2cd  mov     rcx, rsi; lpCriticalSection
0x18000c2d0  xor     r14d, r14d
0x18000c2d3  xor     r15d, r15d
0x18000c2d6  call    cs:__imp_EnterCriticalSection
0x18000c2dc  mov     rcx, rbp; SRWLock
0x18000c2df  call    cs:__imp_AcquireSRWLockExclusive
0x18000c2e5  cmp     rbx, rdi
0x18000c2e8  jnb     short loc_18000C30F
0x18000c2ea  mov     rdx, [rsi+28h]
0x18000c2ee  lea     rax, [rbx+1]
0x18000c2f2  add     rbx, rbx
0x18000c2f5  lea     rcx, [rdx+rbx*8]
0x18000c2f9  mov     rbx, rax
0x18000c2fc  cmp     [rcx], r14
0x18000c2ff  jnz     short loc_18000C308
0x18000c301  cmp     rax, rdi
0x18000c304  jb      short loc_18000C2EE
0x18000c306  jmp     short loc_18000C30F
0x18000c308  mov     r14, [rcx]
0x18000c30b  mov     r15, [rcx+8]
0x18000c30f  test    rbp, rbp
0x18000c312  jz      short loc_18000C31D
0x18000c314  mov     rcx, rbp; SRWLock
0x18000c317  call    cs:__imp_ReleaseSRWLockExclusive
0x18000c31d  test    r14, r14
0x18000c320  jz      short loc_18000C32D
0x18000c322  mov     rcx, r15
0x18000c325  mov     rax, r14
0x18000c328  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c32d  test    rsi, rsi
0x18000c330  jz      short loc_18000C33B
0x18000c332  mov     rcx, rsi; lpCriticalSection
0x18000c335  call    cs:__imp_LeaveCriticalSection
0x18000c33b  cmp     rbx, rdi
0x18000c33e  jb      short loc_18000C2CD
0x18000c340  add     rsp, 28h
0x18000c344  pop     r15
0x18000c346  pop     r14
0x18000c348  pop     rdi
0x18000c349  pop     rsi
0x18000c34a  pop     rbp
0x18000c34b  pop     rbx
0x18000c34c  retn
```
