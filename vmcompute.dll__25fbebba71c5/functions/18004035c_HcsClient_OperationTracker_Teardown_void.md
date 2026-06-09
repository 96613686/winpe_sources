# HcsClient::OperationTracker::Teardown(void)

- ea: `0x18004035c`
- end: `0x18004047a`
- name: `?Teardown@OperationTracker@HcsClient@@QEAAXXZ`
- size: `286`
- prototype: `void __fastcall(HcsClient::OperationTracker *__hidden this)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x1800412a4`
- `0x180046f64`

## callees

- `0x18004035c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18004036c`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800403ba`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18004042f`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18004036c`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800403ba`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18004042f`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800403a7`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18004041b`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180040464`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800403a7`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18004041b`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180040464`
- `api-ms-win-core-synch-l1-2-0!SleepConditionVariableSRW` at `0x1800403f8`
- `api-ms-win-core-synch-l1-2-0!SleepConditionVariableSRW` at `0x18004044f`
- `api-ms-win-core-synch-l1-2-0!SleepConditionVariableSRW` at `0x1800403f8`
- `api-ms-win-core-synch-l1-2-0!SleepConditionVariableSRW` at `0x18004044f`
- `api-ms-win-core-synch-l1-2-0!WakeAllConditionVariable` at `0x180040394`
- `api-ms-win-core-synch-l1-2-0!WakeAllConditionVariable` at `0x180040394`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18004037c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800403c6`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18004037c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800403c6`

## pseudocode

```c
void __fastcall HcsClient::OperationTracker::Teardown(HcsClient::OperationTracker *this)
{
  __int64 v1; // rdi
  char v2; // si
  DWORD CurrentThreadId; // eax

  v1 = *((_QWORD *)this + 13);
  AcquireSRWLockExclusive((PSRWLOCK)v1);
  *(_BYTE *)(v1 + 24) = 1;
  if ( *(_DWORD *)(v1 + 16) == GetCurrentThreadId() )
  {
    v2 = 1;
    WakeAllConditionVariable((PCONDITION_VARIABLE)(v1 + 8));
  }
  else
  {
    v2 = 0;
  }
  ReleaseSRWLockExclusive((PSRWLOCK)v1);
  AcquireSRWLockExclusive((PSRWLOCK)(v1 + 40));
  CurrentThreadId = GetCurrentThreadId();
  if ( !*(_DWORD *)(v1 + 56) || *(_DWORD *)(v1 + 56) == 3 || *(_DWORD *)(v1 + 60) == CurrentThreadId )
  {
    *(_DWORD *)(v1 + 56) = 3;
  }
  else
  {
    *(_DWORD *)(v1 + 56) = 2;
    do
      SleepConditionVariableSRW((PCONDITION_VARIABLE)(v1 + 48), (PSRWLOCK)(v1 + 40), 0xFFFFFFFF, 0);
    while ( *(_DWORD *)(v1 + 56) != 3 );
  }
  if ( v1 != -40 )
    ReleaseSRWLockExclusive((PSRWLOCK)(v1 + 40));
  if ( !v2 )
  {
    AcquireSRWLockExclusive((PSRWLOCK)v1);
    *(_BYTE *)(v1 + 24) = 1;
    while ( *(_DWORD *)(v1 + 16) )
      SleepConditionVariableSRW((PCONDITION_VARIABLE)(v1 + 8), (PSRWLOCK)v1, 0xFFFFFFFF, 0);
    ReleaseSRWLockExclusive((PSRWLOCK)v1);
  }
}

```

## disassembly

```asm
0x18004035c  push    rbx
0x18004035e  push    rbp
0x18004035f  push    rsi
0x180040360  push    rdi
0x180040361  sub     rsp, 28h
0x180040365  mov     rdi, [rcx+68h]
0x180040369  mov     rcx, rdi; SRWLock
0x18004036c  call    cs:__imp_AcquireSRWLockExclusive
0x180040373  nop     dword ptr [rax+rax+00h]
0x180040378  mov     byte ptr [rdi+18h], 1
0x18004037c  call    cs:__imp_GetCurrentThreadId
0x180040383  nop     dword ptr [rax+rax+00h]
0x180040388  cmp     [rdi+10h], eax
0x18004038b  jnz     short loc_1800403A2
0x18004038d  lea     rcx, [rdi+8]; ConditionVariable
0x180040391  mov     sil, 1
0x180040394  call    cs:__imp_WakeAllConditionVariable
0x18004039b  nop     dword ptr [rax+rax+00h]
0x1800403a0  jmp     short loc_1800403A4
0x1800403a2  xor     esi, esi
0x1800403a4  mov     rcx, rdi; SRWLock
0x1800403a7  call    cs:__imp_ReleaseSRWLockExclusive
0x1800403ae  nop     dword ptr [rax+rax+00h]
0x1800403b3  lea     rbx, [rdi+28h]
0x1800403b7  mov     rcx, rbx; SRWLock
0x1800403ba  call    cs:__imp_AcquireSRWLockExclusive
0x1800403c1  nop     dword ptr [rax+rax+00h]
0x1800403c6  call    cs:__imp_GetCurrentThreadId
0x1800403cd  nop     dword ptr [rax+rax+00h]
0x1800403d2  cmp     dword ptr [rdi+38h], 0
0x1800403d6  jz      short loc_18004040C
0x1800403d8  cmp     dword ptr [rdi+38h], 3
0x1800403dc  jz      short loc_18004040C
0x1800403de  cmp     [rdi+3Ch], eax
0x1800403e1  jz      short loc_18004040C
0x1800403e3  mov     dword ptr [rdi+38h], 2
0x1800403ea  xor     r9d, r9d; Flags
0x1800403ed  lea     rcx, [rdi+30h]; ConditionVariable
0x1800403f1  or      r8d, 0FFFFFFFFh; dwMilliseconds
0x1800403f5  mov     rdx, rbx; SRWLock
0x1800403f8  call    cs:__imp_SleepConditionVariableSRW
0x1800403ff  nop     dword ptr [rax+rax+00h]
0x180040404  cmp     dword ptr [rdi+38h], 3
0x180040408  jnz     short loc_1800403EA
0x18004040a  jmp     short loc_180040413
0x18004040c  mov     dword ptr [rdi+38h], 3
0x180040413  test    rbx, rbx
0x180040416  jz      short loc_180040427
0x180040418  mov     rcx, rbx; SRWLock
0x18004041b  call    cs:__imp_ReleaseSRWLockExclusive
0x180040422  nop     dword ptr [rax+rax+00h]
0x180040427  test    sil, sil
0x18004042a  jnz     short loc_180040470
0x18004042c  mov     rcx, rdi; SRWLock
0x18004042f  call    cs:__imp_AcquireSRWLockExclusive
0x180040436  nop     dword ptr [rax+rax+00h]
0x18004043b  mov     byte ptr [rdi+18h], 1
0x18004043f  jmp     short loc_18004045B
0x180040441  xor     r9d, r9d; Flags
0x180040444  lea     rcx, [rdi+8]; ConditionVariable
0x180040448  or      r8d, 0FFFFFFFFh; dwMilliseconds
0x18004044c  mov     rdx, rdi; SRWLock
0x18004044f  call    cs:__imp_SleepConditionVariableSRW
0x180040456  nop     dword ptr [rax+rax+00h]
0x18004045b  cmp     dword ptr [rdi+10h], 0
0x18004045f  jnz     short loc_180040441
0x180040461  mov     rcx, rdi; SRWLock
0x180040464  call    cs:__imp_ReleaseSRWLockExclusive
0x18004046b  nop     dword ptr [rax+rax+00h]
0x180040470  add     rsp, 28h
0x180040474  pop     rdi
0x180040475  pop     rsi
0x180040476  pop     rbp
0x180040477  pop     rbx
0x180040478  retn
```
