# SOS_OS::KillProcess(ulong)

- ea: `0x1004b6f60`
- end: `0x1004b70fe`
- name: `?KillProcess@SOS_OS@@SAXK@Z`
- size: `414`
- prototype: `void __fastcall(UINT uExitCode)`
- caller_count: `4`
- callee_count: `8`
- tags: `service_task`

## callers

- `0x100455160`
- `0x1004b9cb0`
- `0x100552350`
- `0x1005b5de0`

## callees

- `0x1004360f0`
- `0x10045aa50`
- `0x1004b6f60`
- `0x1004b7110`
- `0x1004b9600`
- `0x1005a64a0`
- `0x1005a7110`
- `0x1005a7210`

## import_xrefs

- `KERNEL32!WaitForSingleObject` at `0x1004b7060`
- `KERNEL32!WaitForSingleObject` at `0x1004b7060`
- `KERNEL32!SetThreadPriority` at `0x1004b70cd`
- `KERNEL32!SetThreadPriority` at `0x1004b70cd`
- `KERNEL32!GetCurrentThread` at `0x1004b70af`
- `KERNEL32!GetCurrentThread` at `0x1004b70c2`
- `KERNEL32!GetCurrentThread` at `0x1004b70af`
- `KERNEL32!GetCurrentThread` at `0x1004b70c2`
- `KERNEL32!ExitProcess` at `0x1004b7080`
- `KERNEL32!ExitProcess` at `0x1004b7080`
- `KERNEL32!GetThreadPriority` at `0x1004b70b8`
- `KERNEL32!GetThreadPriority` at `0x1004b70b8`
- `KERNEL32!TerminateProcess` at `0x1004b70de`
- `KERNEL32!TerminateProcess` at `0x1004b70de`
- `KERNEL32!GetCurrentProcess` at `0x1004b70d3`
- `KERNEL32!GetCurrentProcess` at `0x1004b70d3`

## pseudocode

```c
void __fastcall SOS_OS::KillProcess(UINT uExitCode)
{
  __int64 v2; // rbx
  __int64 v3; // rdx
  __int64 v4; // rcx
  __int64 v5; // r14
  __int64 v6; // rax
  HANDLE CurrentThread; // rax
  HANDLE v8; // rax
  HANDLE CurrentProcess; // rax
  _BYTE v10[8]; // [rsp+20h] [rbp-278h] BYREF
  int v11; // [rsp+28h] [rbp-270h]
  int v12; // [rsp+30h] [rbp-268h]
  _QWORD *v13; // [rsp+38h] [rbp-260h]
  char *v14; // [rsp+40h] [rbp-258h]
  __int64 v15; // [rsp+48h] [rbp-250h]
  _QWORD v16[2]; // [rsp+50h] [rbp-248h] BYREF
  char v17; // [rsp+60h] [rbp-238h] BYREF
  __int64 v18; // [rsp+270h] [rbp-28h]
  __int64 v19; // [rsp+278h] [rbp-20h]
  UINT v20; // [rsp+280h] [rbp-18h] BYREF

  v2 = 0;
  if ( (g_XeSosPkg_enabledBitmap & 4) != 0 )
  {
    v11 = 0x10000;
    v12 = 0;
    v13 = v16;
    v14 = &v17;
    v18 = 0;
    v15 = 0;
    v19 = 0;
    v16[0] = &v20;
    v16[1] = 4;
    v20 = uExitCode;
    XeSosPkg::process_killed::Publish((XeSosPkg::process_killed *)v10);
  }
  v3 = 8LL * (unsigned int)tls_index;
  v4 = (unsigned int)SystemThread_TlsOffset + *(_QWORD *)((char *)NtCurrentTeb()->ThreadLocalStoragePointer + v3);
  if ( v4 && *(_QWORD *)(v4 + 272) == v4 )
    v2 = *(_QWORD *)(v4 + 256);
  if ( v2 )
  {
    v5 = (unsigned int)SystemThread_TlsOffset + *(_QWORD *)((char *)NtCurrentTeb()->ThreadLocalStoragePointer + v3);
    v6 = *(_QWORD *)(v5 + 256);
    if ( !v6 )
    {
      SystemThread::MakeMiniSOSThread(0);
      v6 = *(_QWORD *)(v5 + 256);
    }
    if ( (*(_BYTE *)(v6 + 800) & 4) == 0 )
      SOS_Task::SetQuantumTracking(0);
  }
  if ( SOS_OS::sm_KillProcessMutex )
    WaitForSingleObject(SOS_OS::sm_KillProcessMutex, 0xFFFFFFFF);
  SOS_DebugBreakHookMgr::HookAll(2);
  if ( (SOS_PublicGlobals::sm_osOptions & 2) != 0 )
  {
    TimePriv::NotifyShutdownNoLock();
    ExitProcess(uExitCode);
  }
  if ( v2 && (SOS_OS_sm_osProcessStatus & 1) != 0 )
    SOS_OS::SuspendSystemThreads();
  TimePriv::TimeEndPeriod(0);
  CurrentThread = GetCurrentThread();
  if ( GetThreadPriority(CurrentThread) <= 0 )
  {
    v8 = GetCurrentThread();
    SetThreadPriority(v8, 1);
  }
  CurrentProcess = GetCurrentProcess();
  TerminateProcess(CurrentProcess, uExitCode);
}

```

## disassembly

```asm
0x1004b6f60  mov     r11, rsp
0x1004b6f63  mov     [r11+10h], rbx
0x1004b6f67  mov     [r11+18h], rsi
0x1004b6f6b  mov     [r11+20h], rdi
0x1004b6f6f  mov     [rsp+arg_0], ecx
0x1004b6f73  push    r14
0x1004b6f75  sub     rsp, 290h
0x1004b6f7c  mov     edi, ecx
0x1004b6f7e  xor     ebx, ebx
0x1004b6f80  lea     esi, [rbx+1]
0x1004b6f83  test    byte ptr cs:?g_XeSosPkg_enabledBitmap@@3U?$XBitmap@U?$StaticStorage@$0FD@@@@@A, 4; XBitmap<StaticStorage<83>> g_XeSosPkg_enabledBitmap
0x1004b6f8a  jz      short loc_1004B6FD9
0x1004b6f8c  mov     [rsp+298h+var_270], 10000h
0x1004b6f94  mov     [rsp+298h+var_268], ebx
0x1004b6f98  lea     rax, [rsp+298h+var_248]
0x1004b6f9d  mov     [rsp+298h+var_260], rax
0x1004b6fa2  lea     rax, [rsp+298h+var_238]
0x1004b6fa7  mov     [rsp+298h+var_258], rax
0x1004b6fac  mov     [r11-28h], rbx
0x1004b6fb0  mov     [rsp+298h+var_250], rbx
0x1004b6fb5  mov     [r11-20h], rbx
0x1004b6fb9  lea     rax, [r11-18h]
0x1004b6fbd  mov     [rsp+298h+var_248], rax
0x1004b6fc2  mov     [rsp+298h+var_240], 4
0x1004b6fcb  mov     [r11-18h], ecx
0x1004b6fcf  lea     rcx, [rsp+298h+var_278]; this
0x1004b6fd4  call    ?Publish@process_killed@XeSosPkg@@QEAAXXZ; XeSosPkg::process_killed::Publish(void)
0x1004b6fd9  mov     rcx, gs:58h
0x1004b6fe2  mov     eax, cs:_tls_index
0x1004b6fe8  lea     rdx, ds:0[rax*8]
0x1004b6ff0  mov     r8d, cs:SystemThread_TlsOffset
0x1004b6ff7  mov     rcx, [rdx+rcx]
0x1004b6ffb  add     rcx, r8
0x1004b6ffe  jz      short loc_1004B7010
0x1004b7000  cmp     [rcx+110h], rcx
0x1004b7007  jnz     short loc_1004B7010
0x1004b7009  mov     rbx, [rcx+100h]
0x1004b7010  test    rbx, rbx
0x1004b7013  jz      short loc_1004B704F
0x1004b7015  mov     rax, gs:58h
0x1004b701e  mov     r14, [rdx+rax]
0x1004b7022  add     r14, r8
0x1004b7025  mov     rax, [r14+100h]
0x1004b702c  test    rax, rax
0x1004b702f  jnz     short loc_1004B703F
0x1004b7031  xor     ecx, ecx; void *
0x1004b7033  call    ?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z; SystemThread::MakeMiniSOSThread(void *)
0x1004b7038  mov     rax, [r14+100h]
0x1004b703f  test    byte ptr [rax+320h], 4
0x1004b7046  jnz     short loc_1004B704F
0x1004b7048  xor     ecx, ecx; int
0x1004b704a  call    ?SetQuantumTracking@SOS_Task@@SAXH@Z; SOS_Task::SetQuantumTracking(int)
0x1004b704f  mov     rcx, cs:?sm_KillProcessMutex@SOS_OS@@0PEAXEA; hHandle
0x1004b7056  test    rcx, rcx
0x1004b7059  jz      short loc_1004B7066
0x1004b705b  mov     edx, 0FFFFFFFFh; dwMilliseconds
0x1004b7060  call    cs:__imp_WaitForSingleObject
0x1004b7066  mov     ecx, 2
0x1004b706b  call    ?HookAll@SOS_DebugBreakHookMgr@@SA?AW4SOS_RESULT@@W4Action@1@@Z; SOS_DebugBreakHookMgr::HookAll(SOS_DebugBreakHookMgr::Action)
0x1004b7070  test    byte ptr cs:?sm_osOptions@SOS_PublicGlobals@@2KA, 2; ulong SOS_PublicGlobals::sm_osOptions
0x1004b7077  jz      short loc_1004B7087
0x1004b7079  call    ?NotifyShutdownNoLock@TimePriv@@SAXXZ; TimePriv::NotifyShutdownNoLock(void)
0x1004b707e  mov     ecx, edi; uExitCode
0x1004b7080  call    cs:__imp_ExitProcess
0x1004b7087  test    rbx, rbx
0x1004b708a  jz      short loc_1004B709A
0x1004b708c  test    byte ptr cs:?SOS_OS_sm_osProcessStatus@@3KA, 1; ulong SOS_OS_sm_osProcessStatus
0x1004b7093  jz      short loc_1004B709A
0x1004b7095  call    ?SuspendSystemThreads@SOS_OS@@CAXXZ; SOS_OS::SuspendSystemThreads(void)
0x1004b709a  jmp     short loc_1004B70A8
0x1004b709c  mov     esi, 1
0x1004b70a1  mov     edi, [rsp+298h+arg_0]
0x1004b70a8  xor     ecx, ecx; int
0x1004b70aa  call    ?TimeEndPeriod@TimePriv@@CAXH@Z; TimePriv::TimeEndPeriod(int)
0x1004b70af  call    cs:__imp_GetCurrentThread
0x1004b70b5  mov     rcx, rax; hThread
0x1004b70b8  call    cs:__imp_GetThreadPriority
0x1004b70be  test    eax, eax
0x1004b70c0  jg      short loc_1004B70D3
0x1004b70c2  call    cs:__imp_GetCurrentThread
0x1004b70c8  mov     rcx, rax; hThread
0x1004b70cb  mov     edx, esi; nPriority
0x1004b70cd  call    cs:__imp_SetThreadPriority
0x1004b70d3  call    cs:__imp_GetCurrentProcess
0x1004b70d9  mov     rcx, rax; hProcess
0x1004b70dc  mov     edx, edi; uExitCode
0x1004b70de  call    cs:__imp_TerminateProcess
0x1004b70e4  lea     r11, [rsp+298h+var_8]
0x1004b70ec  mov     rbx, [r11+18h]
0x1004b70f0  mov     rsi, [r11+20h]
0x1004b70f4  mov     rdi, [r11+28h]
0x1004b70f8  mov     rsp, r11
0x1004b70fb  pop     r14
0x1004b70fd  retn
```
