# wil::details_abi::SubscriptionList::OnSignaled(wil::srwlock &)

- ea: `0x1800127b4`
- end: `0x180012871`
- name: `?OnSignaled@SubscriptionList@details_abi@wil@@QEAAXAEAVsrwlock@3@@Z`
- size: `189`
- prototype: `void __fastcall(LPCRITICAL_SECTION lpCriticalSection, PSRWLOCK SRWLock)`
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x18000f630`
- `0x18000f660`
- `0x18000f710`
- `0x1800144b0`

## callees

- `0x1800127b4`
- `0x180016010`

## import_xrefs

- `KERNEL32!LeaveCriticalSection` at `0x180012859`
- `KERNEL32!LeaveCriticalSection` at `0x180012859`
- `KERNEL32!EnterCriticalSection` at `0x1800127fa`
- `KERNEL32!EnterCriticalSection` at `0x1800127fa`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x18001283b`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x18001283b`
- `KERNEL32!AcquireSRWLockExclusive` at `0x180012803`
- `KERNEL32!AcquireSRWLockExclusive` at `0x180012803`
- `KERNEL32!ReleaseSRWLockShared` at `0x1800127e4`
- `KERNEL32!ReleaseSRWLockShared` at `0x1800127e4`
- `KERNEL32!AcquireSRWLockShared` at `0x1800127ca`
- `KERNEL32!AcquireSRWLockShared` at `0x1800127ca`

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
0x1800127b4  push    rbx
0x1800127b6  push    rbp
0x1800127b7  push    rsi
0x1800127b8  push    rdi
0x1800127b9  push    r14
0x1800127bb  push    r15
0x1800127bd  sub     rsp, 28h
0x1800127c1  mov     rsi, rcx
0x1800127c4  mov     rbp, rdx
0x1800127c7  mov     rcx, rdx; SRWLock
0x1800127ca  call    cs:__imp_AcquireSRWLockShared
0x1800127d0  mov     rdi, [rsi+30h]
0x1800127d4  sub     rdi, [rsi+28h]
0x1800127d8  shr     rdi, 4
0x1800127dc  test    rbp, rbp
0x1800127df  jz      short loc_1800127EA
0x1800127e1  mov     rcx, rbp; SRWLock
0x1800127e4  call    cs:__imp_ReleaseSRWLockShared
0x1800127ea  xor     ebx, ebx
0x1800127ec  test    rdi, rdi
0x1800127ef  jz      short loc_180012864
0x1800127f1  mov     rcx, rsi; lpCriticalSection
0x1800127f4  xor     r14d, r14d
0x1800127f7  xor     r15d, r15d
0x1800127fa  call    cs:__imp_EnterCriticalSection
0x180012800  mov     rcx, rbp; SRWLock
0x180012803  call    cs:__imp_AcquireSRWLockExclusive
0x180012809  cmp     rbx, rdi
0x18001280c  jnb     short loc_180012833
0x18001280e  mov     rdx, [rsi+28h]
0x180012812  lea     rax, [rbx+1]
0x180012816  add     rbx, rbx
0x180012819  lea     rcx, [rdx+rbx*8]
0x18001281d  mov     rbx, rax
0x180012820  cmp     [rcx], r14
0x180012823  jnz     short loc_18001282C
0x180012825  cmp     rax, rdi
0x180012828  jb      short loc_180012812
0x18001282a  jmp     short loc_180012833
0x18001282c  mov     r14, [rcx]
0x18001282f  mov     r15, [rcx+8]
0x180012833  test    rbp, rbp
0x180012836  jz      short loc_180012841
0x180012838  mov     rcx, rbp; SRWLock
0x18001283b  call    cs:__imp_ReleaseSRWLockExclusive
0x180012841  test    r14, r14
0x180012844  jz      short loc_180012851
0x180012846  mov     rcx, r15
0x180012849  mov     rax, r14
0x18001284c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012851  test    rsi, rsi
0x180012854  jz      short loc_18001285F
0x180012856  mov     rcx, rsi; lpCriticalSection
0x180012859  call    cs:__imp_LeaveCriticalSection
0x18001285f  cmp     rbx, rdi
0x180012862  jb      short loc_1800127F1
0x180012864  add     rsp, 28h
0x180012868  pop     r15
0x18001286a  pop     r14
0x18001286c  pop     rdi
0x18001286d  pop     rsi
0x18001286e  pop     rbp
0x18001286f  pop     rbx
0x180012870  retn
```
