# SrvNetDisableRdmaListenSocketsAndUnlinkSmbDirect

- ea: `0x140014d20`
- end: `0x140014eed`
- name: `SrvNetDisableRdmaListenSocketsAndUnlinkSmbDirect`
- size: `461`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, installer_update, broker_com_uri`

## callers

- `0x1400256e0`

## callees

- `0x14001389c`
- `0x140014a00`
- `0x140014d20`
- `0x1400156b4`
- `0x14001b060`

## import_xrefs

- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x140014d9f`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x140014e65`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x140014d9f`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x140014e65`
- `ntoskrnl!IoGetActivityIdThread` at `0x140014d2d`
- `ntoskrnl!IoGetActivityIdThread` at `0x140014d2d`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x140014d6d`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x140014d6d`
- `ntoskrnl!ZwClose` at `0x140014e39`
- `ntoskrnl!ZwClose` at `0x140014e39`
- `ntoskrnl!KeAcquireGuardedMutex` at `0x140014d49`
- `ntoskrnl!KeAcquireGuardedMutex` at `0x140014d49`
- `ntoskrnl!KeReleaseGuardedMutex` at `0x140014e78`
- `ntoskrnl!KeReleaseGuardedMutex` at `0x140014e78`
- `ntoskrnl!ExWaitForRundownProtectionRelease` at `0x140014e08`
- `ntoskrnl!ExWaitForRundownProtectionRelease` at `0x140014e08`

## pseudocode

```c
__int64 SrvNetDisableRdmaListenSocketsAndUnlinkSmbDirect()
{
  __int64 ActivityIdThread; // rax
  unsigned int v1; // esi
  __int64 v2; // rbp
  unsigned __int8 v3; // bl
  __int64 v4; // rcx
  char updated; // di
  __int64 v6; // rcx
  __int64 v7; // rcx

  ActivityIdThread = IoGetActivityIdThread();
  v1 = SrvNetActiveRdmaResourcesCount;
  v2 = ActivityIdThread;
  KeAcquireGuardedMutex(&SrvNetRdmaRundownMutex);
  v3 = 1;
  LOBYTE(v4) = 1;
  updated = SrvNetUpdateVolatileForceDisableRdmaSupport(v4);
  ExAcquirePushLockExclusiveEx(&SrvNetRdmaRundownSrwLock, 0);
  if ( SrvNetRdmaRundownState == 1 )
  {
    ExReleasePushLockExclusiveEx(&SrvNetRdmaRundownSrwLock, 0);
  }
  else
  {
    SrvNetRdmaRundownState = 1;
    ExReleasePushLockExclusiveEx(&SrvNetRdmaRundownSrwLock, 0);
    v3 = 0;
    if ( (WPP_MAIN_CB.Queue.Wcb.NumberOfChannels & 0x1000) != 0 )
      McTemplateK0t_EtwWriteTransfer(v6, SRVNET_EVENT_RDMA_RUNDOWN_ACTIVE, v2, v1);
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
    {
      WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 41, WPP_4c791a4f213531f920775678ddb20f34_Traceguids, v1);
    }
    SrvNetRefreshRdmaStateOnAllInterfaces();
    updated = 0;
    ExWaitForRundownProtectionRelease(&SrvNetRdmaRundownProtector);
    if ( SrvNetActiveRdmaResourcesCount )
      __int2c();
    if ( !_InterlockedCompareExchange(&SmbdInitingOrDeiniting, 2, 0) )
    {
      if ( SmbdHandle )
      {
        ZwClose(SmbdHandle);
        SmbdHandle = 0;
        SmbdFastDispatch = 0;
      }
      _InterlockedExchange(&SmbdInitingOrDeiniting, 0);
    }
  }
  KeReleaseGuardedMutex(&SrvNetRdmaRundownMutex);
  if ( (WPP_MAIN_CB.Queue.Wcb.NumberOfChannels & 0x1000) != 0 )
    McTemplateK0t_EtwWriteTransfer(v7, SRVNET_EVENT_RDMA_RUNDOWN_COMPLETE, v2, v3);
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
  {
    WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 42, WPP_4c791a4f213531f920775678ddb20f34_Traceguids, v3);
  }
  if ( updated )
    SrvNetRefreshRdmaStateOnAllInterfaces();
  return 0;
}

```

## disassembly

```asm
0x140014d20  push    rbx
0x140014d22  push    rbp
0x140014d23  push    rsi
0x140014d24  push    rdi
0x140014d25  push    r12
0x140014d27  push    r13
0x140014d29  sub     rsp, 28h
0x140014d2d  call    cs:__imp_IoGetActivityIdThread
0x140014d34  nop     dword ptr [rax+rax+00h]
0x140014d39  mov     esi, cs:SrvNetActiveRdmaResourcesCount
0x140014d3f  lea     rcx, SrvNetRdmaRundownMutex; Mutex
0x140014d46  mov     rbp, rax
0x140014d49  call    cs:__imp_KeAcquireGuardedMutex
0x140014d50  nop     dword ptr [rax+rax+00h]
0x140014d55  mov     ebx, 1
0x140014d5a  mov     cl, bl
0x140014d5c  call    SrvNetUpdateVolatileForceDisableRdmaSupport
0x140014d61  xor     edx, edx
0x140014d63  lea     rcx, SrvNetRdmaRundownSrwLock
0x140014d6a  mov     dil, al
0x140014d6d  call    cs:__imp_ExAcquirePushLockExclusiveEx
0x140014d74  nop     dword ptr [rax+rax+00h]
0x140014d79  lea     r13, WPP_GLOBAL_Control
0x140014d80  lea     r12d, [rbx+1]
0x140014d84  xor     edx, edx
0x140014d86  lea     rcx, SrvNetRdmaRundownSrwLock
0x140014d8d  cmp     cs:SrvNetRdmaRundownState, ebx
0x140014d93  jz      loc_140014E65
0x140014d99  mov     cs:SrvNetRdmaRundownState, ebx
0x140014d9f  call    cs:__imp_ExReleasePushLockExclusiveEx
0x140014da6  nop     dword ptr [rax+rax+00h]
0x140014dab  xor     bl, bl
0x140014dad  test    byte ptr cs:WPP_MAIN_CB.Queue+11h, 10h
0x140014db4  jz      short loc_140014DC8
0x140014db6  mov     r9d, esi
0x140014db9  lea     rdx, SRVNET_EVENT_RDMA_RUNDOWN_ACTIVE
0x140014dc0  mov     r8, rbp
0x140014dc3  call    McTemplateK0t_EtwWriteTransfer
0x140014dc8  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x140014dcf  cmp     rcx, r13
0x140014dd2  jz      short loc_140014DF9
0x140014dd4  mov     eax, [rcx+2Ch]
0x140014dd7  test    al, 10h
0x140014dd9  jz      short loc_140014DF9
0x140014ddb  cmp     [rcx+29h], r12b
0x140014ddf  jb      short loc_140014DF9
0x140014de1  mov     rcx, [rcx+18h]
0x140014de5  lea     r8, WPP_4c791a4f213531f920775678ddb20f34_Traceguids
0x140014dec  mov     edx, 29h ; ')'
0x140014df1  mov     r9d, esi
0x140014df4  call    WPP_SF_d
0x140014df9  call    SrvNetRefreshRdmaStateOnAllInterfaces
0x140014dfe  lea     rcx, SrvNetRdmaRundownProtector; RunRef
0x140014e05  xor     dil, dil
0x140014e08  call    cs:__imp_ExWaitForRundownProtectionRelease
0x140014e0f  nop     dword ptr [rax+rax+00h]
0x140014e14  mov     eax, cs:SrvNetActiveRdmaResourcesCount
0x140014e1a  test    eax, eax
0x140014e1c  jz      short loc_140014E20
0x140014e1e  int     2Ch; Windows NT - assertion failure
0x140014e20  xor     eax, eax
0x140014e22  lock cmpxchg cs:SmbdInitingOrDeiniting, r12d
0x140014e2b  jnz     short loc_140014E71
0x140014e2d  mov     rcx, cs:SmbdHandle; Handle
0x140014e34  test    rcx, rcx
0x140014e37  jz      short loc_140014E5B
0x140014e39  call    cs:__imp_ZwClose
0x140014e40  nop     dword ptr [rax+rax+00h]
0x140014e45  mov     cs:SmbdHandle, 0
0x140014e50  mov     cs:SmbdFastDispatch, 0
0x140014e5b  xor     eax, eax
0x140014e5d  xchg    eax, cs:SmbdInitingOrDeiniting
0x140014e63  jmp     short loc_140014E71
0x140014e65  call    cs:__imp_ExReleasePushLockExclusiveEx
0x140014e6c  nop     dword ptr [rax+rax+00h]
0x140014e71  lea     rcx, SrvNetRdmaRundownMutex; Mutex
0x140014e78  call    cs:__imp_KeReleaseGuardedMutex
0x140014e7f  nop     dword ptr [rax+rax+00h]
0x140014e84  test    byte ptr cs:WPP_MAIN_CB.Queue+11h, 10h
0x140014e8b  movzx   ebx, bl
0x140014e8e  jz      short loc_140014EA2
0x140014e90  mov     r9d, ebx
0x140014e93  lea     rdx, SRVNET_EVENT_RDMA_RUNDOWN_COMPLETE
0x140014e9a  mov     r8, rbp
0x140014e9d  call    McTemplateK0t_EtwWriteTransfer
0x140014ea2  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x140014ea9  cmp     rcx, r13
0x140014eac  jz      short loc_140014ED3
0x140014eae  mov     eax, [rcx+2Ch]
0x140014eb1  test    al, 10h
0x140014eb3  jz      short loc_140014ED3
0x140014eb5  cmp     [rcx+29h], r12b
0x140014eb9  jb      short loc_140014ED3
0x140014ebb  mov     rcx, [rcx+18h]
0x140014ebf  lea     r8, WPP_4c791a4f213531f920775678ddb20f34_Traceguids
0x140014ec6  mov     edx, 2Ah ; '*'
0x140014ecb  mov     r9d, ebx
0x140014ece  call    WPP_SF_d
0x140014ed3  test    dil, dil
0x140014ed6  jz      short loc_140014EDD
0x140014ed8  call    SrvNetRefreshRdmaStateOnAllInterfaces
0x140014edd  xor     eax, eax
0x140014edf  add     rsp, 28h
0x140014ee3  pop     r13
0x140014ee5  pop     r12
0x140014ee7  pop     rdi
0x140014ee8  pop     rsi
0x140014ee9  pop     rbp
0x140014eea  pop     rbx
0x140014eeb  retn
```
