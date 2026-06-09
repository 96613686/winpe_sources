# wil::details_abi::SubscriptionList::OnSignaled(wil::srwlock &)

- ea: `0x18000d9a0`
- end: `0x18000da64`
- name: `?OnSignaled@SubscriptionList@details_abi@wil@@QEAAXAEAVsrwlock@3@@Z`
- size: `196`
- prototype: `void __fastcall(LPCRITICAL_SECTION lpCriticalSection, PSRWLOCK SRWLock)`
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x18000a220`
- `0x18000a250`
- `0x18000a280`
- `0x18000f970`

## callees

- `0x18000d9a0`
- `0x18001c010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18000d9b9`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18000d9b9`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18000d9d3`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18000d9d3`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000da2a`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000da2a`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000d9e9`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000d9e9`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000d9f2`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000d9f2`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000da48`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000da48`

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
0x18000d9a0  mov     [rsp+arg_10], rbx
0x18000d9a5  push    rbp
0x18000d9a6  push    rsi
0x18000d9a7  push    rdi
0x18000d9a8  push    r14
0x18000d9aa  push    r15
0x18000d9ac  sub     rsp, 20h
0x18000d9b0  mov     rsi, rcx
0x18000d9b3  mov     rbp, rdx
0x18000d9b6  mov     rcx, rdx; SRWLock
0x18000d9b9  call    cs:__imp_AcquireSRWLockShared
0x18000d9bf  mov     rdi, [rsi+30h]
0x18000d9c3  sub     rdi, [rsi+28h]
0x18000d9c7  shr     rdi, 4
0x18000d9cb  test    rbp, rbp
0x18000d9ce  jz      short loc_18000D9D9
0x18000d9d0  mov     rcx, rbp; SRWLock
0x18000d9d3  call    cs:__imp_ReleaseSRWLockShared
0x18000d9d9  xor     ebx, ebx
0x18000d9db  test    rdi, rdi
0x18000d9de  jz      short loc_18000DA53
0x18000d9e0  mov     rcx, rsi; lpCriticalSection
0x18000d9e3  xor     r14d, r14d
0x18000d9e6  xor     r15d, r15d
0x18000d9e9  call    cs:__imp_EnterCriticalSection
0x18000d9ef  mov     rcx, rbp; SRWLock
0x18000d9f2  call    cs:__imp_AcquireSRWLockExclusive
0x18000d9f8  cmp     rbx, rdi
0x18000d9fb  jnb     short loc_18000DA22
0x18000d9fd  mov     rdx, [rsi+28h]
0x18000da01  lea     rax, [rbx+1]
0x18000da05  add     rbx, rbx
0x18000da08  lea     rcx, [rdx+rbx*8]
0x18000da0c  mov     rbx, rax
0x18000da0f  cmp     [rcx], r14
0x18000da12  jnz     short loc_18000DA1B
0x18000da14  cmp     rax, rdi
0x18000da17  jb      short loc_18000DA01
0x18000da19  jmp     short loc_18000DA22
0x18000da1b  mov     r14, [rcx]
0x18000da1e  mov     r15, [rcx+8]
0x18000da22  test    rbp, rbp
0x18000da25  jz      short loc_18000DA30
0x18000da27  mov     rcx, rbp; SRWLock
0x18000da2a  call    cs:__imp_ReleaseSRWLockExclusive
0x18000da30  test    r14, r14
0x18000da33  jz      short loc_18000DA40
0x18000da35  mov     rcx, r15
0x18000da38  mov     rax, r14
0x18000da3b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000da40  test    rsi, rsi
0x18000da43  jz      short loc_18000DA4E
0x18000da45  mov     rcx, rsi; lpCriticalSection
0x18000da48  call    cs:__imp_LeaveCriticalSection
0x18000da4e  cmp     rbx, rdi
0x18000da51  jb      short loc_18000D9E0
0x18000da53  mov     rbx, [rsp+48h+arg_10]
0x18000da58  add     rsp, 20h
0x18000da5c  pop     r15
0x18000da5e  pop     r14
0x18000da60  pop     rdi
0x18000da61  pop     rsi
0x18000da62  pop     rbp
0x18000da63  retn
```
