# Vml::VmSlimEvent::Wait(ulong)

- ea: `0x180060c10`
- end: `0x180060cb8`
- name: `?Wait@VmSlimEvent@Vml@@QEAAHK@Z`
- size: `168`
- prototype: `__int64 __fastcall(PSRWLOCK SRWLock, DWORD dwMilliseconds)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x18005f080`
- `0x18005fe7c`

## callees

- `0x180060c10`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180060c2a`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180060c2a`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180060c96`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180060c96`
- `api-ms-win-core-synch-l1-2-0!SleepConditionVariableSRW` at `0x180060c54`
- `api-ms-win-core-synch-l1-2-0!SleepConditionVariableSRW` at `0x180060c54`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180060c36`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180060c62`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180060c36`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180060c62`

## pseudocode

```c
__int64 __fastcall Vml::VmSlimEvent::Wait(PSRWLOCK SRWLock, DWORD dwMilliseconds)
{
  unsigned int v4; // esi
  BOOL v5; // ebx

  v4 = 0;
  AcquireSRWLockExclusive(SRWLock);
  GetCurrentThreadId();
  do
  {
    if ( HIDWORD(SRWLock[3].Ptr) )
      break;
    LODWORD(SRWLock[1].Ptr) = 0;
    v5 = SleepConditionVariableSRW((PCONDITION_VARIABLE)&SRWLock[2], SRWLock, dwMilliseconds, 0);
    LODWORD(SRWLock[1].Ptr) = GetCurrentThreadId();
  }
  while ( v5 );
  if ( HIDWORD(SRWLock[3].Ptr) )
  {
    if ( LODWORD(SRWLock[3].Ptr) )
      HIDWORD(SRWLock[3].Ptr) = 0;
    v4 = 1;
  }
  LODWORD(SRWLock[1].Ptr) = 0;
  ReleaseSRWLockExclusive(SRWLock);
  return v4;
}

```

## disassembly

```asm
0x180060c10  mov     [rsp+arg_10], rbx
0x180060c15  mov     [rsp+arg_18], rbp
0x180060c1a  push    rsi
0x180060c1b  push    rdi
0x180060c1c  push    r14
0x180060c1e  sub     rsp, 30h
0x180060c22  mov     r14d, edx
0x180060c25  mov     rdi, rcx
0x180060c28  xor     esi, esi
0x180060c2a  call    cs:__imp_AcquireSRWLockExclusive
0x180060c31  nop     dword ptr [rax+rax+00h]
0x180060c36  call    cs:__imp_GetCurrentThreadId
0x180060c3d  nop     dword ptr [rax+rax+00h]
0x180060c42  jmp     short loc_180060C75
0x180060c44  xor     r9d, r9d; Flags
0x180060c47  mov     [rdi+8], esi
0x180060c4a  mov     r8d, r14d; dwMilliseconds
0x180060c4d  lea     rcx, [rdi+10h]; ConditionVariable
0x180060c51  mov     rdx, rdi; SRWLock
0x180060c54  call    cs:__imp_SleepConditionVariableSRW
0x180060c5b  nop     dword ptr [rax+rax+00h]
0x180060c60  mov     ebx, eax
0x180060c62  call    cs:__imp_GetCurrentThreadId
0x180060c69  nop     dword ptr [rax+rax+00h]
0x180060c6e  mov     [rdi+8], eax
0x180060c71  test    ebx, ebx
0x180060c73  jz      short loc_180060C7A
0x180060c75  cmp     [rdi+1Ch], esi
0x180060c78  jz      short loc_180060C44
0x180060c7a  cmp     [rdi+1Ch], esi
0x180060c7d  jz      short loc_180060C8C
0x180060c7f  cmp     [rdi+18h], esi
0x180060c82  jz      short loc_180060C87
0x180060c84  mov     [rdi+1Ch], esi
0x180060c87  mov     esi, 1
0x180060c8c  mov     rcx, rdi; SRWLock
0x180060c8f  mov     dword ptr [rdi+8], 0
0x180060c96  call    cs:__imp_ReleaseSRWLockExclusive
0x180060c9d  nop     dword ptr [rax+rax+00h]
0x180060ca2  mov     rbx, [rsp+48h+arg_10]
0x180060ca7  mov     eax, esi
0x180060ca9  mov     rbp, [rsp+48h+arg_18]
0x180060cae  add     rsp, 30h
0x180060cb2  pop     r14
0x180060cb4  pop     rdi
0x180060cb5  pop     rsi
0x180060cb6  retn
```
