# PnpInstallStartup

- ea: `0x180012dac`
- end: `0x180012fe1`
- name: `PnpInstallStartup`
- size: `565`
- prototype: `_BOOL8()`
- caller_count: `2`
- callee_count: `5`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x18000cf30`
- `0x180013fb0`

## callees

- `0x18000a210`
- `0x18000a9e0`
- `0x1800117d4`
- `0x180011ab8`
- `0x180012dac`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180012ef5`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180012f7f`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180012fd6`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800191fa`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180019218`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180019236`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180012ef5`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180012f7f`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180012fd6`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800191fa`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180019218`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180019236`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180012e49`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180012e78`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180012e94`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180012e49`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180012e78`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180012e94`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180012f3c`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180012f3c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180012e5b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180012f08`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180012fc7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180012e5b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180012f08`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180012fc7`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x180012fb5`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x180012fb5`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemInfo` at `0x180012ebd`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemInfo` at `0x180012ebd`

## pseudocode

```c
_BOOL8 PnpInstallStartup()
{
  DWORD LastError; // ebx
  DWORD dwNumberOfProcessors; // eax
  _SYSTEM_INFO SystemInfo; // [rsp+38h] [rbp-40h] BYREF
  DWORD ThreadId; // [rsp+80h] [rbp+8h] BYREF

  LastError = 0;
  ThreadId = 0;
  memset(&SystemInfo, 0, sizeof(SystemInfo));
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x10000000) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 31, WPP_f291e930712a394bf89cc8c0b8336be0_Traceguids);
  pSetupBeginSynchronizedAccess(&Handles);
  ServerInstallQueuingEnabled = 0;
  ServerInstallProcessingEnabled = 0;
  ServerInstallBatchComplete = 0;
  ServerInstallBatchTotal = 0;
  ServerInstallBatchTimeoutDetected = 0;
  ServerInstallUpdateStatus();
  SchedulerWaitEvents = CreateEventW(0, 0, 0, 0);
  if ( SchedulerWaitEvents
    && (hObject = CreateEventW(0, 1, 0, 0)) != 0
    && (hSourceHandle = CreateEventW(0, 0, 0, 0)) != 0 )
  {
    memset(&SystemInfo, 0, sizeof(SystemInfo));
    GetSystemInfo(&SystemInfo);
    if ( SystemInfo.dwNumberOfProcessors < 4 || (dwNumberOfProcessors = 16, SystemInfo.dwNumberOfProcessors < 0x10) )
    {
      dwNumberOfProcessors = SystemInfo.dwNumberOfProcessors;
      if ( SystemInfo.dwNumberOfProcessors < 4 )
        dwNumberOfProcessors = 4;
    }
    ServerInstallMaxThreads = dwNumberOfProcessors;
    PnpServiceOutstandingInstalls = 0;
  }
  else
  {
    LastError = GetLastError();
  }
  ReleaseMutex(hMutex);
  if ( !LastError )
  {
    if ( CreateNoPendingInstallEvent() )
    {
      pSetupBeginSynchronizedAccess(&Handles);
      ServerInstallListSize = 0;
      ServerInstallQueuingEnabled = 1;
      ReleaseMutex(hMutex);
      pSetupBeginSynchronizedAccess(&PnpInstallThreadLock);
      PnpInstallThread = CreateThread(0, 0, (LPTHREAD_START_ROUTINE)DeviceInstallThreadProc, 0, 0, &ThreadId);
      if ( !PnpInstallThread )
        LastError = GetLastError();
      ReleaseMutex(qword_1800239E8);
    }
    else
    {
      LastError = GetLastError();
    }
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x10000000) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 32, WPP_f291e930712a394bf89cc8c0b8336be0_Traceguids);
  SetLastError(LastError);
  return LastError == 0;
}

```

## disassembly

```asm
0x180012dac  mov     rax, rsp
0x180012daf  mov     [rax+10h], rbx
0x180012db3  push    rsi
0x180012db4  sub     rsp, 70h
0x180012db8  xor     ebx, ebx
0x180012dba  mov     [rax+8], ebx
0x180012dbd  xorps   xmm0, xmm0
0x180012dc0  movups  xmmword ptr [rax-40h], xmm0
0x180012dc4  movups  xmmword ptr [rax-30h], xmm0
0x180012dc8  movups  xmmword ptr [rax-20h], xmm0
0x180012dcc  lea     rsi, WPP_GLOBAL_Control
0x180012dd3  mov     rcx, cs:WPP_GLOBAL_Control
0x180012dda  cmp     rcx, rsi
0x180012ddd  jz      short loc_180012DFB
0x180012ddf  test    dword ptr [rcx+1Ch], 10000000h
0x180012de6  jz      short loc_180012DFB
0x180012de8  lea     edx, [rbx+1Fh]
0x180012deb  lea     r8, WPP_f291e930712a394bf89cc8c0b8336be0_Traceguids
0x180012df2  mov     rcx, [rcx+10h]
0x180012df6  call    WPP_SF_
0x180012dfb  lea     rcx, Handles; lpHandles
0x180012e02  call    pSetupBeginSynchronizedAccess
0x180012e07  nop
0x180012e08  mov     cs:ServerInstallQueuingEnabled, 0
0x180012e12  mov     cs:ServerInstallProcessingEnabled, 0
0x180012e1c  mov     cs:ServerInstallBatchComplete, 0
0x180012e26  mov     cs:ServerInstallBatchTotal, 0
0x180012e30  mov     cs:ServerInstallBatchTimeoutDetected, 0
0x180012e3a  call    ServerInstallUpdateStatus
0x180012e3f  xor     r9d, r9d; lpName
0x180012e42  xor     r8d, r8d; bInitialState
0x180012e45  xor     edx, edx; bManualReset
0x180012e47  xor     ecx, ecx; lpEventAttributes
0x180012e49  call    cs:__imp_CreateEventW
0x180012e4f  mov     cs:SchedulerWaitEvents, rax
0x180012e56  test    rax, rax
0x180012e59  jnz     short loc_180012E6C
0x180012e5b  call    cs:__imp_GetLastError
0x180012e61  mov     ebx, eax
0x180012e63  mov     [rsp+78h+var_48], eax
0x180012e67  jmp     loc_180012EEE
0x180012e6c  xor     r9d, r9d; lpName
0x180012e6f  xor     r8d, r8d; bInitialState
0x180012e72  lea     edx, [r9+1]; bManualReset
0x180012e76  xor     ecx, ecx; lpEventAttributes
0x180012e78  call    cs:__imp_CreateEventW
0x180012e7e  mov     cs:hObject, rax
0x180012e85  test    rax, rax
0x180012e88  jz      short loc_180012E5B
0x180012e8a  xor     r9d, r9d; lpName
0x180012e8d  xor     r8d, r8d; bInitialState
0x180012e90  xor     edx, edx; bManualReset
0x180012e92  xor     ecx, ecx; lpEventAttributes
0x180012e94  call    cs:__imp_CreateEventW
0x180012e9a  mov     cs:hSourceHandle, rax
0x180012ea1  test    rax, rax
0x180012ea4  jz      short loc_180012E5B
0x180012ea6  xorps   xmm0, xmm0
0x180012ea9  movups  xmmword ptr [rsp+78h+SystemInfo], xmm0
0x180012eae  movups  xmmword ptr [rsp+78h+SystemInfo.lpMaximumApplicationAddress], xmm0
0x180012eb3  movups  xmmword ptr [rsp+78h+SystemInfo.dwNumberOfProcessors], xmm0
0x180012eb8  lea     rcx, [rsp+78h+SystemInfo]; lpSystemInfo
0x180012ebd  call    cs:__imp_GetSystemInfo
0x180012ec3  mov     ecx, [rsp+78h+SystemInfo.dwNumberOfProcessors]
0x180012ec7  mov     edx, 4
0x180012ecc  cmp     ecx, edx
0x180012ece  jb      short loc_180012ED7
0x180012ed0  lea     eax, [rdx+0Ch]
0x180012ed3  cmp     ecx, eax
0x180012ed5  jnb     short loc_180012EDE
0x180012ed7  mov     eax, ecx
0x180012ed9  cmp     ecx, edx
0x180012edb  cmovb   eax, edx
0x180012ede  mov     cs:ServerInstallMaxThreads, eax
0x180012ee4  mov     cs:PnpServiceOutstandingInstalls, 0
0x180012eee  mov     rcx, cs:hMutex; hMutex
0x180012ef5  call    cs:__imp_ReleaseMutex
0x180012efb  test    ebx, ebx
0x180012efd  jnz     short loc_180012F10
0x180012eff  call    CreateNoPendingInstallEvent
0x180012f04  test    eax, eax
0x180012f06  jnz     short loc_180012F57
0x180012f08  call    cs:__imp_GetLastError
0x180012f0e  mov     ebx, eax
0x180012f10  mov     rcx, cs:WPP_GLOBAL_Control
0x180012f17  cmp     rcx, rsi
0x180012f1a  jz      short loc_180012F3A
0x180012f1c  test    dword ptr [rcx+1Ch], 10000000h
0x180012f23  jz      short loc_180012F3A
0x180012f25  mov     edx, 20h ; ' '
0x180012f2a  lea     r8, WPP_f291e930712a394bf89cc8c0b8336be0_Traceguids
0x180012f31  mov     rcx, [rcx+10h]
0x180012f35  call    WPP_SF_
0x180012f3a  mov     ecx, ebx; dwErrCode
0x180012f3c  call    cs:__imp_SetLastError
0x180012f42  xor     eax, eax
0x180012f44  test    ebx, ebx
0x180012f46  setz    al
0x180012f49  mov     rbx, [rsp+78h+arg_8]
0x180012f51  add     rsp, 70h
0x180012f55  pop     rsi
0x180012f56  retn
0x180012f57  lea     rcx, Handles; lpHandles
0x180012f5e  call    pSetupBeginSynchronizedAccess
0x180012f63  nop
0x180012f64  mov     cs:ServerInstallListSize, 0
0x180012f6e  mov     cs:ServerInstallQueuingEnabled, 1
0x180012f78  mov     rcx, cs:hMutex; hMutex
0x180012f7f  call    cs:__imp_ReleaseMutex
0x180012f85  lea     rcx, PnpInstallThreadLock; lpHandles
0x180012f8c  call    pSetupBeginSynchronizedAccess
0x180012f91  nop
0x180012f92  lea     rax, [rsp+78h+ThreadId]
0x180012f9a  mov     [rsp+78h+lpThreadId], rax; lpThreadId
0x180012f9f  mov     [rsp+78h+dwCreationFlags], 0; dwCreationFlags
0x180012fa7  xor     r9d, r9d; lpParameter
0x180012faa  lea     r8, DeviceInstallThreadProc; lpStartAddress
0x180012fb1  xor     edx, edx; dwStackSize
0x180012fb3  xor     ecx, ecx; lpThreadAttributes
0x180012fb5  call    cs:__imp_CreateThread
0x180012fbb  mov     cs:PnpInstallThread, rax
0x180012fc2  test    rax, rax
0x180012fc5  jnz     short loc_180012FCF
0x180012fc7  call    cs:__imp_GetLastError
0x180012fcd  mov     ebx, eax
0x180012fcf  mov     rcx, cs:qword_1800239E8; hMutex
0x180012fd6  call    cs:__imp_ReleaseMutex
0x180012fdc  jmp     loc_180012F10
0x1800191ea  push    rbp
0x1800191ec  sub     rsp, 30h
0x1800191f0  mov     rbp, rdx
0x1800191f3  mov     rcx, cs:hMutex; hMutex
0x1800191fa  call    cs:__imp_ReleaseMutex
0x180019200  nop
0x180019201  add     rsp, 30h
0x180019205  pop     rbp
0x180019206  retn
0x180019208  push    rbp
0x18001920a  sub     rsp, 30h
0x18001920e  mov     rbp, rdx
0x180019211  mov     rcx, cs:hMutex; hMutex
0x180019218  call    cs:__imp_ReleaseMutex
0x18001921e  nop
0x18001921f  add     rsp, 30h
0x180019223  pop     rbp
0x180019224  retn
0x180019226  push    rbp
0x180019228  sub     rsp, 30h
0x18001922c  mov     rbp, rdx
0x18001922f  mov     rcx, cs:qword_1800239E8; hMutex
0x180019236  call    cs:__imp_ReleaseMutex
0x18001923c  nop
0x18001923d  add     rsp, 30h
0x180019241  pop     rbp
0x180019242  retn
```
