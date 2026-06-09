# wil::details_abi::SubscriptionList::OnSignaled(wil::srwlock &)

- ea: `0x140009ff8`
- end: `0x14000a0b5`
- name: `?OnSignaled@SubscriptionList@details_abi@wil@@QEAAXAEAVsrwlock@3@@Z`
- size: `189`
- prototype: `void __fastcall(LPCRITICAL_SECTION lpCriticalSection, PSRWLOCK SRWLock)`
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x140008870`
- `0x1400088a0`
- `0x1400089a0`
- `0x14000be50`

## callees

- `0x140009ff8`
- `0x140016010`

## import_xrefs

- `KERNEL32!EnterCriticalSection` at `0x14000a03e`
- `KERNEL32!EnterCriticalSection` at `0x14000a03e`
- `KERNEL32!LeaveCriticalSection` at `0x14000a09d`
- `KERNEL32!LeaveCriticalSection` at `0x14000a09d`
- `KERNEL32!AcquireSRWLockExclusive` at `0x14000a047`
- `KERNEL32!AcquireSRWLockExclusive` at `0x14000a047`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x14000a07f`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x14000a07f`
- `KERNEL32!AcquireSRWLockShared` at `0x14000a00e`
- `KERNEL32!AcquireSRWLockShared` at `0x14000a00e`
- `KERNEL32!ReleaseSRWLockShared` at `0x14000a028`
- `KERNEL32!ReleaseSRWLockShared` at `0x14000a028`

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
0x140009ff8  push    rbx
0x140009ffa  push    rbp
0x140009ffb  push    rsi
0x140009ffc  push    rdi
0x140009ffd  push    r14
0x140009fff  push    r15
0x14000a001  sub     rsp, 28h
0x14000a005  mov     rsi, rcx
0x14000a008  mov     rbp, rdx
0x14000a00b  mov     rcx, rdx; SRWLock
0x14000a00e  call    cs:__imp_AcquireSRWLockShared
0x14000a014  mov     rdi, [rsi+30h]
0x14000a018  sub     rdi, [rsi+28h]
0x14000a01c  shr     rdi, 4
0x14000a020  test    rbp, rbp
0x14000a023  jz      short loc_14000A02E
0x14000a025  mov     rcx, rbp; SRWLock
0x14000a028  call    cs:__imp_ReleaseSRWLockShared
0x14000a02e  xor     ebx, ebx
0x14000a030  test    rdi, rdi
0x14000a033  jz      short loc_14000A0A8
0x14000a035  mov     rcx, rsi; lpCriticalSection
0x14000a038  xor     r14d, r14d
0x14000a03b  xor     r15d, r15d
0x14000a03e  call    cs:__imp_EnterCriticalSection
0x14000a044  mov     rcx, rbp; SRWLock
0x14000a047  call    cs:__imp_AcquireSRWLockExclusive
0x14000a04d  cmp     rbx, rdi
0x14000a050  jnb     short loc_14000A077
0x14000a052  mov     rdx, [rsi+28h]
0x14000a056  lea     rax, [rbx+1]
0x14000a05a  add     rbx, rbx
0x14000a05d  lea     rcx, [rdx+rbx*8]
0x14000a061  mov     rbx, rax
0x14000a064  cmp     [rcx], r14
0x14000a067  jnz     short loc_14000A070
0x14000a069  cmp     rax, rdi
0x14000a06c  jb      short loc_14000A056
0x14000a06e  jmp     short loc_14000A077
0x14000a070  mov     r14, [rcx]
0x14000a073  mov     r15, [rcx+8]
0x14000a077  test    rbp, rbp
0x14000a07a  jz      short loc_14000A085
0x14000a07c  mov     rcx, rbp; SRWLock
0x14000a07f  call    cs:__imp_ReleaseSRWLockExclusive
0x14000a085  test    r14, r14
0x14000a088  jz      short loc_14000A095
0x14000a08a  mov     rcx, r15
0x14000a08d  mov     rax, r14
0x14000a090  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000a095  test    rsi, rsi
0x14000a098  jz      short loc_14000A0A3
0x14000a09a  mov     rcx, rsi; lpCriticalSection
0x14000a09d  call    cs:__imp_LeaveCriticalSection
0x14000a0a3  cmp     rbx, rdi
0x14000a0a6  jb      short loc_14000A035
0x14000a0a8  add     rsp, 28h
0x14000a0ac  pop     r15
0x14000a0ae  pop     r14
0x14000a0b0  pop     rdi
0x14000a0b1  pop     rsi
0x14000a0b2  pop     rbp
0x14000a0b3  pop     rbx
0x14000a0b4  retn
```
