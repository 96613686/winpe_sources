# SrvNetEnableRdmaListenSockets

- ea: `0x140014f70`
- end: `0x1400150e3`
- name: `SrvNetEnableRdmaListenSockets`
- size: `371`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `installer_update, broker_com_uri`

## callers

- `0x1400256e0`

## callees

- `0x14001389c`
- `0x140014948`
- `0x140014a00`
- `0x140014f70`
- `0x1400156b4`
- `0x140015790`
- `0x14001b060`

## import_xrefs

- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x140015053`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x140015053`
- `ntoskrnl!IoGetActivityIdThread` at `0x140014f7b`
- `ntoskrnl!IoGetActivityIdThread` at `0x140014f7b`
- `ntoskrnl!RtlRunOnceInitialize` at `0x140015019`
- `ntoskrnl!RtlRunOnceInitialize` at `0x140015019`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x140014ffd`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x140014ffd`
- `ntoskrnl!ExReInitializeRundownProtection` at `0x14001502c`
- `ntoskrnl!ExReInitializeRundownProtection` at `0x14001502c`
- `ntoskrnl!KeAcquireGuardedMutex` at `0x140014fde`
- `ntoskrnl!KeAcquireGuardedMutex` at `0x140014fde`
- `ntoskrnl!KeReleaseGuardedMutex` at `0x140015066`
- `ntoskrnl!KeReleaseGuardedMutex` at `0x140015066`

## pseudocode

```c
__int64 SrvNetEnableRdmaListenSockets()
{
  __int64 ActivityIdThread; // rax
  __int64 v1; // rcx
  __int64 v2; // rsi
  unsigned __int8 updated; // bp
  char v4; // di
  __int64 v5; // rcx
  unsigned __int8 v6; // bl

  ActivityIdThread = IoGetActivityIdThread();
  v2 = ActivityIdThread;
  if ( (WPP_MAIN_CB.Queue.Wcb.NumberOfChannels & 0x1000) != 0 )
    McTemplateK0_EtwWriteTransfer(v1, SRVNET_EVENT_RDMA_REACTIVATION, ActivityIdThread);
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
  {
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 39, WPP_4c791a4f213531f920775678ddb20f34_Traceguids);
  }
  KeAcquireGuardedMutex(&SrvNetRdmaRundownMutex);
  updated = SrvNetUpdateVolatileForceDisableRdmaSupport(0);
  ExAcquirePushLockExclusiveEx(&SrvNetRdmaRundownSrwLock, 0);
  if ( SrvNetRdmaRundownState == 1 )
  {
    RtlRunOnceInitialize(&SrvNetSmbdInitOnce);
    ExReInitializeRundownProtection(&SrvNetRdmaRundownProtector);
    SrvNetRdmaRundownState = 0;
    v4 = 1;
  }
  else
  {
    v4 = 0;
  }
  ExReleasePushLockExclusiveEx(&SrvNetRdmaRundownSrwLock, 0);
  KeReleaseGuardedMutex(&SrvNetRdmaRundownMutex);
  v6 = v4 ^ 1;
  if ( (WPP_MAIN_CB.Queue.Wcb.NumberOfChannels & 0x1000) != 0 )
    McTemplateK0t_EtwWriteTransfer(v5, SRVNET_EVENT_RDMA_REACTIVATION_COMPLETE, v2, v6);
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
  {
    WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 40, WPP_4c791a4f213531f920775678ddb20f34_Traceguids, v6);
  }
  if ( updated || v4 )
    SrvNetRefreshRdmaStateOnAllInterfaces();
  return 0;
}

```

## disassembly

```asm
0x140014f70  push    rbx
0x140014f72  push    rbp
0x140014f73  push    rsi
0x140014f74  push    rdi
0x140014f75  push    r15
0x140014f77  sub     rsp, 20h
0x140014f7b  call    cs:__imp_IoGetActivityIdThread
0x140014f82  nop     dword ptr [rax+rax+00h]
0x140014f87  test    byte ptr cs:WPP_MAIN_CB.Queue+11h, 10h
0x140014f8e  mov     rsi, rax
0x140014f91  jz      short loc_140014FA2
0x140014f93  mov     r8, rax
0x140014f96  lea     rdx, SRVNET_EVENT_RDMA_REACTIVATION
0x140014f9d  call    McTemplateK0_EtwWriteTransfer
0x140014fa2  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x140014fa9  lea     r15, WPP_GLOBAL_Control
0x140014fb0  cmp     rcx, r15
0x140014fb3  jz      short loc_140014FD7
0x140014fb5  mov     eax, [rcx+2Ch]
0x140014fb8  test    al, 10h
0x140014fba  jz      short loc_140014FD7
0x140014fbc  cmp     byte ptr [rcx+29h], 2
0x140014fc0  jb      short loc_140014FD7
0x140014fc2  mov     rcx, [rcx+18h]
0x140014fc6  lea     r8, WPP_4c791a4f213531f920775678ddb20f34_Traceguids
0x140014fcd  mov     edx, 27h ; '''
0x140014fd2  call    WPP_SF_
0x140014fd7  lea     rcx, SrvNetRdmaRundownMutex; Mutex
0x140014fde  call    cs:__imp_KeAcquireGuardedMutex
0x140014fe5  nop     dword ptr [rax+rax+00h]
0x140014fea  xor     ecx, ecx
0x140014fec  call    SrvNetUpdateVolatileForceDisableRdmaSupport
0x140014ff1  xor     edx, edx
0x140014ff3  lea     rcx, SrvNetRdmaRundownSrwLock
0x140014ffa  mov     bpl, al
0x140014ffd  call    cs:__imp_ExAcquirePushLockExclusiveEx
0x140015004  nop     dword ptr [rax+rax+00h]
0x140015009  cmp     cs:SrvNetRdmaRundownState, 1
0x140015010  jnz     short loc_140015047
0x140015012  lea     rcx, SrvNetSmbdInitOnce; RunOnce
0x140015019  call    cs:__imp_RtlRunOnceInitialize
0x140015020  nop     dword ptr [rax+rax+00h]
0x140015025  lea     rcx, SrvNetRdmaRundownProtector; RunRef
0x14001502c  call    cs:__imp_ExReInitializeRundownProtection
0x140015033  nop     dword ptr [rax+rax+00h]
0x140015038  mov     cs:SrvNetRdmaRundownState, 0
0x140015042  mov     dil, 1
0x140015045  jmp     short loc_14001504A
0x140015047  xor     dil, dil
0x14001504a  xor     edx, edx
0x14001504c  lea     rcx, SrvNetRdmaRundownSrwLock
0x140015053  call    cs:__imp_ExReleasePushLockExclusiveEx
0x14001505a  nop     dword ptr [rax+rax+00h]
0x14001505f  lea     rcx, SrvNetRdmaRundownMutex; Mutex
0x140015066  call    cs:__imp_KeReleaseGuardedMutex
0x14001506d  nop     dword ptr [rax+rax+00h]
0x140015072  mov     bl, dil
0x140015075  xor     bl, 1
0x140015078  test    byte ptr cs:WPP_MAIN_CB.Queue+11h, 10h
0x14001507f  jz      short loc_140015094
0x140015081  movzx   r9d, bl
0x140015085  lea     rdx, SRVNET_EVENT_RDMA_REACTIVATION_COMPLETE
0x14001508c  mov     r8, rsi
0x14001508f  call    McTemplateK0t_EtwWriteTransfer
0x140015094  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14001509b  cmp     rcx, r15
0x14001509e  jz      short loc_1400150C6
0x1400150a0  mov     eax, [rcx+2Ch]
0x1400150a3  test    al, 10h
0x1400150a5  jz      short loc_1400150C6
0x1400150a7  cmp     byte ptr [rcx+29h], 2
0x1400150ab  jb      short loc_1400150C6
0x1400150ad  mov     rcx, [rcx+18h]
0x1400150b1  lea     r8, WPP_4c791a4f213531f920775678ddb20f34_Traceguids
0x1400150b8  movzx   r9d, bl
0x1400150bc  mov     edx, 28h ; '('
0x1400150c1  call    WPP_SF_d
0x1400150c6  test    bpl, bpl
0x1400150c9  jnz     short loc_1400150D0
0x1400150cb  test    dil, dil
0x1400150ce  jz      short loc_1400150D5
0x1400150d0  call    SrvNetRefreshRdmaStateOnAllInterfaces
0x1400150d5  xor     eax, eax
0x1400150d7  add     rsp, 20h
0x1400150db  pop     r15
0x1400150dd  pop     rdi
0x1400150de  pop     rsi
0x1400150df  pop     rbp
0x1400150e0  pop     rbx
0x1400150e1  retn
```
