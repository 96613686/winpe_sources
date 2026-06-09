# WFDSConMgr::Timer::Set(ulong,ulong,ulong)

- ea: `0x18005e320`
- end: `0x18005e3f9`
- name: `?Set@Timer@WFDSConMgr@@QEAAXKKK@Z`
- size: `217`
- prototype: `void __fastcall(WFDSConMgr::Timer *__hidden this, unsigned int, unsigned int, unsigned int)`
- caller_count: `4`
- callee_count: `3`
- tags: ``

## callers

- `0x180006348`
- `0x180014ce8`
- `0x180015000`
- `0x18002f254`

## callees

- `0x180005498`
- `0x18005dbc4`
- `0x18005e320`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18005e3ba`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18005e3e8`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18005e3ba`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18005e3e8`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18005e3d1`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18005e3d1`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18005e348`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18005e348`

## pseudocode

```c
void __fastcall WFDSConMgr::Timer::Set(WFDSConMgr::Timer *this, int a2)
{
  char *v2; // rdi
  __int64 v4; // rcx
  PSRWLOCK SRWLock; // [rsp+30h] [rbp-18h] BYREF
  char v6; // [rsp+38h] [rbp-10h]
  struct _FILETIME pftDueTime; // [rsp+50h] [rbp+8h] BYREF

  v2 = (char *)this + 8;
  pftDueTime = (struct _FILETIME)(-10000LL * a2);
  EventActivityIdControl(1u, (LPGUID)((char *)this + 8));
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    WPP_SF_q_guid_D(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      11,
      (unsigned int)WPP_621daf02e21a36dfd02ebab89b470631_Traceguids,
      (_DWORD)this,
      (__int64)v2);
  }
  v4 = *((_QWORD *)this + 4);
  if ( v4 )
  {
    WFDSConMgr::CThreadpoolEnvironmentBase::AcquireLockQueueShared(v4, &SRWLock);
    if ( !*(_BYTE *)(*((_QWORD *)this + 4) + 88LL) )
      SetThreadpoolTimer(*((PTP_TIMER *)this + 3), &pftDueTime, 0, 0);
    if ( v6 )
    {
      if ( SRWLock )
        ReleaseSRWLockShared(SRWLock);
    }
  }
  else
  {
    SetThreadpoolTimer(*((PTP_TIMER *)this + 3), &pftDueTime, 0, 0);
  }
}

```

## disassembly

```asm
0x18005e320  mov     [rsp+arg_8], rbx
0x18005e325  push    rdi
0x18005e326  sub     rsp, 40h
0x18005e32a  movsxd  rax, edx
0x18005e32d  lea     rdi, [rcx+8]
0x18005e331  imul    rdx, rax, 0FFFFFFFFFFFFD8F0h
0x18005e338  mov     rbx, rcx
0x18005e33b  mov     ecx, 1; ControlCode
0x18005e340  mov     qword ptr [rsp+48h+pftDueTime.dwLowDateTime], rdx
0x18005e345  mov     rdx, rdi; ActivityId
0x18005e348  call    cs:__imp_EventActivityIdControl
0x18005e34e  mov     rcx, cs:WPP_GLOBAL_Control
0x18005e355  lea     rdx, WPP_GLOBAL_Control
0x18005e35c  cmp     rcx, rdx
0x18005e35f  jz      short loc_18005E38E
0x18005e361  cmp     byte ptr [rcx+19h], 4
0x18005e365  jb      short loc_18005E38E
0x18005e367  test    byte ptr [rcx+1Ch], 1
0x18005e36b  jz      short loc_18005E38E
0x18005e36d  mov     rcx, [rcx+10h]
0x18005e371  lea     r8, WPP_621daf02e21a36dfd02ebab89b470631_Traceguids
0x18005e378  mov     [rsp+48h+var_20], eax
0x18005e37c  mov     edx, 0Bh
0x18005e381  mov     r9, rbx
0x18005e384  mov     [rsp+48h+var_28], rdi
0x18005e389  call    WPP_SF_q_guid_D
0x18005e38e  mov     rcx, [rbx+20h]
0x18005e392  test    rcx, rcx
0x18005e395  jz      short loc_18005E3D9
0x18005e397  lea     rdx, [rsp+48h+SRWLock]
0x18005e39c  call    ?AcquireLockQueueShared@CThreadpoolEnvironmentBase@WFDSConMgr@@QEAA?AV?$LockSentry@VReadersWriterLock@WFDSConMgr@@$00@2@XZ; WFDSConMgr::CThreadpoolEnvironmentBase::AcquireLockQueueShared(void)
0x18005e3a1  mov     rax, [rbx+20h]
0x18005e3a5  cmp     byte ptr [rax+58h], 0
0x18005e3a9  jnz     short loc_18005E3C0
0x18005e3ab  mov     rcx, [rbx+18h]; pti
0x18005e3af  lea     rdx, [rsp+48h+pftDueTime]; pftDueTime
0x18005e3b4  xor     r9d, r9d; msWindowLength
0x18005e3b7  xor     r8d, r8d; msPeriod
0x18005e3ba  call    cs:__imp_SetThreadpoolTimer
0x18005e3c0  cmp     [rsp+48h+var_10], 0
0x18005e3c5  jz      short loc_18005E3EE
0x18005e3c7  mov     rcx, [rsp+48h+SRWLock]; SRWLock
0x18005e3cc  test    rcx, rcx
0x18005e3cf  jz      short loc_18005E3EE
0x18005e3d1  call    cs:__imp_ReleaseSRWLockShared
0x18005e3d7  jmp     short loc_18005E3EE
0x18005e3d9  mov     rcx, [rbx+18h]; pti
0x18005e3dd  lea     rdx, [rsp+48h+pftDueTime]; pftDueTime
0x18005e3e2  xor     r9d, r9d; msWindowLength
0x18005e3e5  xor     r8d, r8d; msPeriod
0x18005e3e8  call    cs:__imp_SetThreadpoolTimer
0x18005e3ee  mov     rbx, [rsp+48h+arg_8]
0x18005e3f3  add     rsp, 40h
0x18005e3f7  pop     rdi
0x18005e3f8  retn
```
