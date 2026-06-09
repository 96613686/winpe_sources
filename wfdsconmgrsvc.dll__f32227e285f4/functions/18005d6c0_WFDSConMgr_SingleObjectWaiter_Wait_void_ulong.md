# WFDSConMgr::SingleObjectWaiter::Wait(void *,ulong)

- ea: `0x18005d6c0`
- end: `0x18005d8ab`
- name: `?Wait@SingleObjectWaiter@WFDSConMgr@@QEAAXPEAXK@Z`
- size: `491`
- prototype: `void __fastcall(WFDSConMgr::SingleObjectWaiter *__hidden this, void *, unsigned int)`
- caller_count: `2`
- callee_count: `8`
- tags: ``

## callers

- `0x180028d00`
- `0x18004ed3c`

## callees

- `0x180005498`
- `0x1800059c0`
- `0x180006740`
- `0x180009b5c`
- `0x18005c800`
- `0x18005d09c`
- `0x18005d6c0`
- `0x18005dbc4`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005d7c4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005d7c4`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x18005d80c`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x18005d80c`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWait` at `0x18005d7b5`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWait` at `0x18005d7b5`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18005d887`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18005d887`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18005d89b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18005d89b`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18005d6dc`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18005d6dc`

## string_xrefs

- `0x18005d7e8`: `onecoreuap\net\wlan\wfdsconmgr\util\src\threadpool.cpp`
- `0x18005d7d6`: `CreateThreadpoolWait failed`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall WFDSConMgr::SingleObjectWaiter::Wait(WFDSConMgr::SingleObjectWaiter *this, void *a2)
{
  char *v4; // rdi
  RTL_SRWLOCK *v5; // rdi
  char v6; // si
  __int64 v7; // r8
  char v8; // cl
  bool v9; // r9
  struct _TP_CALLBACK_ENVIRON_V3 *v10; // rdx
  struct _TP_WAIT *ThreadpoolWait; // rax
  signed int LastError; // eax
  PSRWLOCK SRWLock[7]; // [rsp+40h] [rbp-38h] BYREF
  LPCRITICAL_SECTION lpCriticalSection; // [rsp+80h] [rbp+8h] BYREF

  v4 = (char *)this + 8;
  EventActivityIdControl(1u, (LPGUID)((char *)this + 8));
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    WPP_SF_q_guid_D(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      26,
      (unsigned int)WPP_96a9a6c77a913b5e31449c3b6f365fcd_Traceguids,
      (_DWORD)this,
      (__int64)v4);
  }
  *((_QWORD *)this + 5) = a2;
  WFDSConMgr::CriticalSection::Lock((char *)this + 72, &lpCriticalSection);
  if ( *((_QWORD *)this + 4) )
    WFDSConMgr::SingleObjectWaiter::Cancel(this);
  v5 = 0;
  v6 = 0;
  v7 = *((_QWORD *)this + 3);
  if ( v7 )
  {
    WFDSConMgr::CThreadpoolEnvironmentBase::AcquireLockQueueShared(*((_QWORD *)this + 3), SRWLock);
    v5 = SRWLock[0];
    v6 = 1;
    v7 = *((_QWORD *)this + 3);
    v8 = *(_BYTE *)(v7 + 88);
    v9 = v8 != 0;
    v10 = (struct _TP_CALLBACK_ENVIRON_V3 *)(v7 + 16);
    if ( v8 )
      v10 = 0;
  }
  else
  {
    v10 = 0;
    v9 = 0;
  }
  if ( v9 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      WPP_SF_qq(*((_QWORD *)WPP_GLOBAL_Control + 2), 29, WPP_96a9a6c77a913b5e31449c3b6f365fcd_Traceguids, this, v7);
    }
  }
  else
  {
    ThreadpoolWait = CreateThreadpoolWait(WFDSConMgr::SingleObjectWaiter::WaitCallback, this, v10);
    *((_QWORD *)this + 4) = ThreadpoolWait;
    if ( !ThreadpoolWait )
    {
      LastError = GetLastError();
      if ( LastError > 0 )
        LastError = (unsigned __int16)LastError | 0x80070000;
      WFDSConMgr::CException::Throw(
        LastError,
        "WFDSConMgr::SingleObjectWaiter::Wait",
        "onecoreuap\\net\\wlan\\wfdsconmgr\\util\\src\\threadpool.cpp",
        176,
        L"CreateThreadpoolWait failed");
    }
    *((_BYTE *)this + 48) = 1;
    SetThreadpoolWait(ThreadpoolWait, *((HANDLE *)this + 5), 0);
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 27, WPP_96a9a6c77a913b5e31449c3b6f365fcd_Traceguids, this);
    }
  }
  if ( v6 && v5 )
    ReleaseSRWLockShared(v5);
  if ( lpCriticalSection )
    LeaveCriticalSection(lpCriticalSection);
}

```

## disassembly

```asm
0x18005d6c0  push    rbx
0x18005d6c2  push    rsi
0x18005d6c3  push    rdi
0x18005d6c4  push    r15
0x18005d6c6  sub     rsp, 58h
0x18005d6ca  mov     rsi, rdx
0x18005d6cd  mov     rbx, rcx
0x18005d6d0  lea     rdi, [rcx+8]
0x18005d6d4  mov     rdx, rdi; ActivityId
0x18005d6d7  mov     ecx, 1; ControlCode
0x18005d6dc  call    cs:__imp_EventActivityIdControl
0x18005d6e2  lea     r15, WPP_GLOBAL_Control
0x18005d6e9  mov     rcx, cs:WPP_GLOBAL_Control
0x18005d6f0  cmp     rcx, r15
0x18005d6f3  jz      short loc_18005D722
0x18005d6f5  cmp     byte ptr [rcx+19h], 4
0x18005d6f9  jb      short loc_18005D722
0x18005d6fb  test    byte ptr [rcx+1Ch], 1
0x18005d6ff  jz      short loc_18005D722
0x18005d701  mov     edx, 1Ah
0x18005d706  mov     [rsp+78h+var_50], eax
0x18005d70a  mov     [rsp+78h+var_58], rdi
0x18005d70f  mov     r9, rbx
0x18005d712  lea     r8, WPP_96a9a6c77a913b5e31449c3b6f365fcd_Traceguids
0x18005d719  mov     rcx, [rcx+10h]
0x18005d71d  call    WPP_SF_q_guid_D
0x18005d722  mov     [rbx+28h], rsi
0x18005d726  lea     rcx, [rbx+48h]
0x18005d72a  lea     rdx, [rsp+78h+lpCriticalSection]
0x18005d732  call    ?Lock@CriticalSection@WFDSConMgr@@QEAA?AVSyncLock@12@XZ; WFDSConMgr::CriticalSection::Lock(void)
0x18005d737  nop
0x18005d738  cmp     qword ptr [rbx+20h], 0
0x18005d73d  jz      short loc_18005D747
0x18005d73f  mov     rcx, rbx; this
0x18005d742  call    ?Cancel@SingleObjectWaiter@WFDSConMgr@@QEAAX_N@Z; WFDSConMgr::SingleObjectWaiter::Cancel(bool)
0x18005d747  xor     edi, edi
0x18005d749  mov     [rsp+78h+var_48], rdi
0x18005d74e  xor     sil, sil
0x18005d751  mov     [rsp+78h+var_40], sil
0x18005d756  mov     r8, [rbx+18h]
0x18005d75a  test    r8, r8
0x18005d75d  jz      short loc_18005D79A
0x18005d75f  lea     rdx, [rsp+78h+SRWLock]
0x18005d764  mov     rcx, r8
0x18005d767  call    ?AcquireLockQueueShared@CThreadpoolEnvironmentBase@WFDSConMgr@@QEAA?AV?$LockSentry@VReadersWriterLock@WFDSConMgr@@$00@2@XZ; WFDSConMgr::CThreadpoolEnvironmentBase::AcquireLockQueueShared(void)
0x18005d76c  mov     rdi, [rsp+78h+SRWLock]
0x18005d771  mov     [rsp+78h+var_48], rdi
0x18005d776  mov     sil, 1
0x18005d779  mov     [rsp+78h+var_40], sil
0x18005d77e  mov     r8, [rbx+18h]
0x18005d782  mov     cl, [r8+58h]
0x18005d786  test    cl, cl
0x18005d788  setnz   r9b
0x18005d78c  lea     rdx, [r8+10h]
0x18005d790  xor     eax, eax
0x18005d792  test    cl, cl
0x18005d794  cmovnz  rdx, rax
0x18005d798  jmp     short loc_18005D79F
0x18005d79a  xor     edx, edx
0x18005d79c  xor     r9b, r9b
0x18005d79f  test    r9b, r9b
0x18005d7a2  jnz     loc_18005D844
0x18005d7a8  mov     r8, rdx; pcbe
0x18005d7ab  mov     rdx, rbx; pv
0x18005d7ae  lea     rcx, ?WaitCallback@SingleObjectWaiter@WFDSConMgr@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WAIT@@J@Z; pfnwa
0x18005d7b5  call    cs:__imp_CreateThreadpoolWait
0x18005d7bb  mov     [rbx+20h], rax
0x18005d7bf  test    rax, rax
0x18005d7c2  jnz     short loc_18005D7FE
0x18005d7c4  call    cs:__imp_GetLastError
0x18005d7ca  test    eax, eax
0x18005d7cc  jle     short loc_18005D7D6
0x18005d7ce  movzx   eax, ax
0x18005d7d1  or      eax, 80070000h
0x18005d7d6  lea     rcx, aCreatethreadpo; "CreateThreadpoolWait failed"
0x18005d7dd  mov     [rsp+78h+var_58], rcx; unsigned __int16 *
0x18005d7e2  mov     r9d, 1B0h; char
0x18005d7e8  lea     r8, aOnecoreuapNetW_22; "onecoreuap\\net\\wlan\\wfdsconmgr\\util"...
0x18005d7ef  lea     rdx, aWfdsconmgrSing; "WFDSConMgr::SingleObjectWaiter::Wait"
0x18005d7f6  mov     ecx, eax; int
0x18005d7f8  call    ?Throw@CException@WFDSConMgr@@SAXJPEBD0KPEBG@Z; WFDSConMgr::CException::Throw(long,char const *,char const *,ulong,ushort const *)
0x18005d7fe  mov     byte ptr [rbx+30h], 1
0x18005d802  xor     r8d, r8d; pftTimeout
0x18005d805  mov     rdx, [rbx+28h]; h
0x18005d809  mov     rcx, rax; pwa
0x18005d80c  call    cs:__imp_SetThreadpoolWait
0x18005d812  mov     rcx, cs:WPP_GLOBAL_Control
0x18005d819  cmp     rcx, r15
0x18005d81c  jz      short loc_18005D87A
0x18005d81e  cmp     byte ptr [rcx+19h], 4
0x18005d822  jb      short loc_18005D87A
0x18005d824  test    byte ptr [rcx+1Ch], 1
0x18005d828  jz      short loc_18005D87A
0x18005d82a  mov     edx, 1Bh
0x18005d82f  mov     r9, rbx
0x18005d832  lea     r8, WPP_96a9a6c77a913b5e31449c3b6f365fcd_Traceguids
0x18005d839  mov     rcx, [rcx+10h]
0x18005d83d  call    WPP_SF_q
0x18005d842  jmp     short loc_18005D87A
0x18005d844  mov     rcx, cs:WPP_GLOBAL_Control
0x18005d84b  cmp     rcx, r15
0x18005d84e  jz      short loc_18005D87A
0x18005d850  cmp     byte ptr [rcx+19h], 3
0x18005d854  jb      short loc_18005D87A
0x18005d856  test    byte ptr [rcx+1Ch], 1
0x18005d85a  jz      short loc_18005D87A
0x18005d85c  mov     edx, 1Dh
0x18005d861  mov     [rsp+78h+var_58], r8
0x18005d866  mov     r9, rbx
0x18005d869  lea     r8, WPP_96a9a6c77a913b5e31449c3b6f365fcd_Traceguids
0x18005d870  mov     rcx, [rcx+10h]
0x18005d874  call    WPP_SF_qq
0x18005d879  nop
0x18005d87a  test    sil, sil
0x18005d87d  jz      short loc_18005D88E
0x18005d87f  test    rdi, rdi
0x18005d882  jz      short loc_18005D88E
0x18005d884  mov     rcx, rdi; SRWLock
0x18005d887  call    cs:__imp_ReleaseSRWLockShared
0x18005d88d  nop
0x18005d88e  mov     rcx, [rsp+78h+lpCriticalSection]; lpCriticalSection
0x18005d896  test    rcx, rcx
0x18005d899  jz      short loc_18005D8A1
0x18005d89b  call    cs:__imp_LeaveCriticalSection
0x18005d8a1  add     rsp, 58h
0x18005d8a5  pop     r15
0x18005d8a7  pop     rdi
0x18005d8a8  pop     rsi
0x18005d8a9  pop     rbx
0x18005d8aa  retn
```
