# WFDSConMgr::Timer::Cancel(bool)

- ea: `0x180005640`
- end: `0x1800056d4`
- name: `?Cancel@Timer@WFDSConMgr@@QEAAX_N@Z`
- size: `148`
- prototype: `void __fastcall(WFDSConMgr::Timer *__hidden this, bool)`
- caller_count: `5`
- callee_count: `2`
- tags: ``

## callers

- `0x1800063a8`
- `0x180014a68`
- `0x180015214`
- `0x18002bee0`
- `0x18002dae0`

## callees

- `0x180005498`
- `0x180005640`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180005681`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800056ab`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180005681`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800056ab`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1800056be`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1800056be`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180005698`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180005698`

## pseudocode

```c
void __fastcall WFDSConMgr::Timer::Cancel(WFDSConMgr::Timer *this, char a2)
{
  __int64 v4; // rcx
  PTP_TIMER *v5; // rbx
  PSRWLOCK SRWLock; // [rsp+20h] [rbp-18h] BYREF
  char v7; // [rsp+28h] [rbp-10h]

  v4 = *((_QWORD *)this + 4);
  v5 = (PTP_TIMER *)((char *)this + 24);
  if ( v4 )
  {
    WFDSConMgr::CThreadpoolEnvironmentBase::AcquireLockQueueShared(v4, &SRWLock);
    if ( !*(_BYTE *)(*((_QWORD *)this + 4) + 88LL) )
      SetThreadpoolTimer(*v5, 0, 0, 0);
    if ( v7 && SRWLock )
      ReleaseSRWLockShared(SRWLock);
  }
  else
  {
    SetThreadpoolTimer(*v5, 0, 0, 0);
  }
  if ( a2 )
    WaitForThreadpoolTimerCallbacks(*v5, 1);
}

```

## disassembly

```asm
0x180005640  mov     [rsp+arg_0], rbx
0x180005645  mov     [rsp+arg_8], rsi
0x18000564a  push    rdi
0x18000564b  sub     rsp, 30h
0x18000564f  mov     rdi, rcx
0x180005652  mov     sil, dl
0x180005655  mov     rcx, [rcx+20h]
0x180005659  lea     rbx, [rdi+18h]
0x18000565d  test    rcx, rcx
0x180005660  jz      short loc_1800056A0
0x180005662  lea     rdx, [rsp+38h+SRWLock]
0x180005667  call    ?AcquireLockQueueShared@CThreadpoolEnvironmentBase@WFDSConMgr@@QEAA?AV?$LockSentry@VReadersWriterLock@WFDSConMgr@@$00@2@XZ; WFDSConMgr::CThreadpoolEnvironmentBase::AcquireLockQueueShared(void)
0x18000566c  mov     rax, [rdi+20h]
0x180005670  cmp     byte ptr [rax+58h], 0
0x180005674  jnz     short loc_180005687
0x180005676  mov     rcx, [rbx]; pti
0x180005679  xor     r9d, r9d; msWindowLength
0x18000567c  xor     r8d, r8d; msPeriod
0x18000567f  xor     edx, edx; pftDueTime
0x180005681  call    cs:__imp_SetThreadpoolTimer
0x180005687  cmp     [rsp+38h+var_10], 0
0x18000568c  jz      short loc_1800056B1
0x18000568e  mov     rcx, [rsp+38h+SRWLock]; SRWLock
0x180005693  test    rcx, rcx
0x180005696  jz      short loc_1800056B1
0x180005698  call    cs:__imp_ReleaseSRWLockShared
0x18000569e  jmp     short loc_1800056B1
0x1800056a0  mov     rcx, [rbx]; pti
0x1800056a3  xor     r9d, r9d; msWindowLength
0x1800056a6  xor     r8d, r8d; msPeriod
0x1800056a9  xor     edx, edx; pftDueTime
0x1800056ab  call    cs:__imp_SetThreadpoolTimer
0x1800056b1  test    sil, sil
0x1800056b4  jz      short loc_1800056C4
0x1800056b6  mov     rcx, [rbx]; pti
0x1800056b9  mov     edx, 1; fCancelPendingCallbacks
0x1800056be  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x1800056c4  mov     rbx, [rsp+38h+arg_0]
0x1800056c9  mov     rsi, [rsp+38h+arg_8]
0x1800056ce  add     rsp, 30h
0x1800056d2  pop     rdi
0x1800056d3  retn
```
