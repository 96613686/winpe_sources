# WFDSConMgr::WorkItem::Queue(void)

- ea: `0x18005d560`
- end: `0x18005d614`
- name: `?Queue@WorkItem@WFDSConMgr@@UEAAXXZ`
- size: `180`
- prototype: `void __fastcall(WFDSConMgr::WorkItem *__hidden this)`
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x180005498`
- `0x18005d560`
- `0x18005dbc4`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x18005d5e0`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x18005d603`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x18005d5e0`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x18005d603`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18005d5f7`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18005d5f7`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18005d579`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18005d579`

## pseudocode

```c
void __fastcall WFDSConMgr::WorkItem::Queue(WFDSConMgr::WorkItem *this)
{
  char *v1; // rdi
  __int64 v3; // rcx
  PSRWLOCK SRWLock; // [rsp+30h] [rbp-18h] BYREF
  char v5; // [rsp+38h] [rbp-10h]

  v1 = (char *)this + 8;
  EventActivityIdControl(1u, (LPGUID)((char *)this + 8));
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    WPP_SF_q_guid_D(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      21,
      (unsigned int)WPP_96a9a6c77a913b5e31449c3b6f365fcd_Traceguids,
      (_DWORD)this,
      (__int64)v1);
  }
  v3 = *((_QWORD *)this + 4);
  if ( v3 )
  {
    WFDSConMgr::CThreadpoolEnvironmentBase::AcquireLockQueueShared(v3, &SRWLock);
    if ( !*(_BYTE *)(*((_QWORD *)this + 4) + 88LL) )
      SubmitThreadpoolWork(*((PTP_WORK *)this + 3));
    if ( v5 )
    {
      if ( SRWLock )
        ReleaseSRWLockShared(SRWLock);
    }
  }
  else
  {
    SubmitThreadpoolWork(*((PTP_WORK *)this + 3));
  }
}

```

## disassembly

```asm
0x18005d560  mov     [rsp+arg_0], rbx
0x18005d565  push    rdi
0x18005d566  sub     rsp, 40h
0x18005d56a  lea     rdi, [rcx+8]
0x18005d56e  mov     rbx, rcx
0x18005d571  mov     rdx, rdi; ActivityId
0x18005d574  mov     ecx, 1; ControlCode
0x18005d579  call    cs:__imp_EventActivityIdControl
0x18005d57f  mov     rcx, cs:WPP_GLOBAL_Control
0x18005d586  lea     rdx, WPP_GLOBAL_Control
0x18005d58d  cmp     rcx, rdx
0x18005d590  jz      short loc_18005D5BF
0x18005d592  cmp     byte ptr [rcx+19h], 4
0x18005d596  jb      short loc_18005D5BF
0x18005d598  test    byte ptr [rcx+1Ch], 1
0x18005d59c  jz      short loc_18005D5BF
0x18005d59e  mov     rcx, [rcx+10h]
0x18005d5a2  lea     r8, WPP_96a9a6c77a913b5e31449c3b6f365fcd_Traceguids
0x18005d5a9  mov     [rsp+48h+var_20], eax
0x18005d5ad  mov     edx, 15h
0x18005d5b2  mov     r9, rbx
0x18005d5b5  mov     [rsp+48h+var_28], rdi
0x18005d5ba  call    WPP_SF_q_guid_D
0x18005d5bf  mov     rcx, [rbx+20h]
0x18005d5c3  test    rcx, rcx
0x18005d5c6  jz      short loc_18005D5FF
0x18005d5c8  lea     rdx, [rsp+48h+SRWLock]
0x18005d5cd  call    ?AcquireLockQueueShared@CThreadpoolEnvironmentBase@WFDSConMgr@@QEAA?AV?$LockSentry@VReadersWriterLock@WFDSConMgr@@$00@2@XZ; WFDSConMgr::CThreadpoolEnvironmentBase::AcquireLockQueueShared(void)
0x18005d5d2  mov     rax, [rbx+20h]
0x18005d5d6  cmp     byte ptr [rax+58h], 0
0x18005d5da  jnz     short loc_18005D5E6
0x18005d5dc  mov     rcx, [rbx+18h]; pwk
0x18005d5e0  call    cs:__imp_SubmitThreadpoolWork
0x18005d5e6  cmp     [rsp+48h+var_10], 0
0x18005d5eb  jz      short loc_18005D609
0x18005d5ed  mov     rcx, [rsp+48h+SRWLock]; SRWLock
0x18005d5f2  test    rcx, rcx
0x18005d5f5  jz      short loc_18005D609
0x18005d5f7  call    cs:__imp_ReleaseSRWLockShared
0x18005d5fd  jmp     short loc_18005D609
0x18005d5ff  mov     rcx, [rbx+18h]; pwk
0x18005d603  call    cs:__imp_SubmitThreadpoolWork
0x18005d609  mov     rbx, [rsp+48h+arg_0]
0x18005d60e  add     rsp, 40h
0x18005d612  pop     rdi
0x18005d613  retn
```
