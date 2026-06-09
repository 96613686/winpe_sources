# wil::details_abi::SubscriptionList::OnSignaled(wil::srwlock &)

- ea: `0x140008a80`
- end: `0x140008b3d`
- name: `?OnSignaled@SubscriptionList@details_abi@wil@@QEAAXAEAVsrwlock@3@@Z`
- size: `189`
- prototype: `void __fastcall(LPCRITICAL_SECTION lpCriticalSection, PSRWLOCK SRWLock)`
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x1400049d0`
- `0x140004a00`
- `0x140004b00`
- `0x14000bce0`

## callees

- `0x140008a80`
- `0x140015010`

## import_xrefs

- `KERNEL32!AcquireSRWLockExclusive` at `0x140008acf`
- `KERNEL32!AcquireSRWLockExclusive` at `0x140008acf`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x140008b07`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x140008b07`
- `KERNEL32!AcquireSRWLockShared` at `0x140008a96`
- `KERNEL32!AcquireSRWLockShared` at `0x140008a96`
- `KERNEL32!ReleaseSRWLockShared` at `0x140008ab0`
- `KERNEL32!ReleaseSRWLockShared` at `0x140008ab0`
- `KERNEL32!LeaveCriticalSection` at `0x140008b25`
- `KERNEL32!LeaveCriticalSection` at `0x140008b25`
- `KERNEL32!EnterCriticalSection` at `0x140008ac6`
- `KERNEL32!EnterCriticalSection` at `0x140008ac6`

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
0x140008a80  push    rbx
0x140008a82  push    rbp
0x140008a83  push    rsi
0x140008a84  push    rdi
0x140008a85  push    r14
0x140008a87  push    r15
0x140008a89  sub     rsp, 28h
0x140008a8d  mov     rsi, rcx
0x140008a90  mov     rbp, rdx
0x140008a93  mov     rcx, rdx; SRWLock
0x140008a96  call    cs:__imp_AcquireSRWLockShared
0x140008a9c  mov     rdi, [rsi+30h]
0x140008aa0  sub     rdi, [rsi+28h]
0x140008aa4  shr     rdi, 4
0x140008aa8  test    rbp, rbp
0x140008aab  jz      short loc_140008AB6
0x140008aad  mov     rcx, rbp; SRWLock
0x140008ab0  call    cs:__imp_ReleaseSRWLockShared
0x140008ab6  xor     ebx, ebx
0x140008ab8  test    rdi, rdi
0x140008abb  jz      short loc_140008B30
0x140008abd  mov     rcx, rsi; lpCriticalSection
0x140008ac0  xor     r14d, r14d
0x140008ac3  xor     r15d, r15d
0x140008ac6  call    cs:__imp_EnterCriticalSection
0x140008acc  mov     rcx, rbp; SRWLock
0x140008acf  call    cs:__imp_AcquireSRWLockExclusive
0x140008ad5  cmp     rbx, rdi
0x140008ad8  jnb     short loc_140008AFF
0x140008ada  mov     rdx, [rsi+28h]
0x140008ade  lea     rax, [rbx+1]
0x140008ae2  add     rbx, rbx
0x140008ae5  lea     rcx, [rdx+rbx*8]
0x140008ae9  mov     rbx, rax
0x140008aec  cmp     [rcx], r14
0x140008aef  jnz     short loc_140008AF8
0x140008af1  cmp     rax, rdi
0x140008af4  jb      short loc_140008ADE
0x140008af6  jmp     short loc_140008AFF
0x140008af8  mov     r14, [rcx]
0x140008afb  mov     r15, [rcx+8]
0x140008aff  test    rbp, rbp
0x140008b02  jz      short loc_140008B0D
0x140008b04  mov     rcx, rbp; SRWLock
0x140008b07  call    cs:__imp_ReleaseSRWLockExclusive
0x140008b0d  test    r14, r14
0x140008b10  jz      short loc_140008B1D
0x140008b12  mov     rcx, r15
0x140008b15  mov     rax, r14
0x140008b18  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140008b1d  test    rsi, rsi
0x140008b20  jz      short loc_140008B2B
0x140008b22  mov     rcx, rsi; lpCriticalSection
0x140008b25  call    cs:__imp_LeaveCriticalSection
0x140008b2b  cmp     rbx, rdi
0x140008b2e  jb      short loc_140008ABD
0x140008b30  add     rsp, 28h
0x140008b34  pop     r15
0x140008b36  pop     r14
0x140008b38  pop     rdi
0x140008b39  pop     rsi
0x140008b3a  pop     rbp
0x140008b3b  pop     rbx
0x140008b3c  retn
```
