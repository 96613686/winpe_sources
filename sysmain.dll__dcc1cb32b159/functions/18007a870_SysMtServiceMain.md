# SysMtServiceMain

- ea: `0x18007a870`
- end: `0x18007a9d0`
- name: `SysMtServiceMain`
- size: `352`
- prototype: `DWORD()`
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting, service_task`

## callees

- `0x180066924`
- `0x18007a870`
- `0x180087ed0`
- `0x180087fdc`

## import_xrefs

- `ntdll!RtlAcquireSRWLockExclusive` at `0x18007a896`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x18007a975`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x18007a896`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x18007a975`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18007a8ae`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18007a9bf`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18007a8ae`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18007a9bf`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x18007a8c2`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x18007a8c2`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18007a9a8`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18007a9a8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007a91e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007a91e`
- `api-ms-win-service-core-l1-1-0!RegisterServiceCtrlHandlerExW` at `0x18007a90c`
- `api-ms-win-service-core-l1-1-0!RegisterServiceCtrlHandlerExW` at `0x18007a90c`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x18007a932`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x18007a99b`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x18007a932`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x18007a99b`

## pseudocode

```c
DWORD SysMtServiceMain()
{
  SERVICE_STATUS_HANDLE v0; // rax
  DWORD result; // eax
  DWORD v2; // edi
  int v3; // ebx
  unsigned int v4; // ebx
  _QWORD v5[3]; // [rsp+20h] [rbp-18h] BYREF

  v5[1] = hEvent;
  v5[0] = 0;
  RtlAcquireSRWLockExclusive(&PfSvcGlobalsLock);
  SysMtGlobals = 0;
  RtlReleaseSRWLockExclusive(&PfSvcGlobalsLock);
  _InterlockedIncrement(&dword_1800D3FB0);
  ResetEvent(hEvent);
  ServiceStatus.dwServiceType = 32;
  *(_OWORD *)&ServiceStatus.dwWin32ExitCode = 0;
  ServiceStatus.dwControlsAccepted = 197;
  ServiceStatus.dwCurrentState = 4;
  v0 = RegisterServiceCtrlHandlerExW(L"sysmain", SysMtServiceControlHandler, (LPVOID)dword_1800D3FB0);
  SysMtGlobals = v0;
  if ( v0 && SetServiceStatus(v0, &ServiceStatus) )
  {
    v3 = TlgRegisterAggregateProviderEx();
    v5[0] = SysMtGlobals;
    result = PfSvcMainThread(v5);
    v2 = result;
    if ( v3 >= 0 )
      result = TlgUnregisterAggregateProvider();
  }
  else
  {
    result = GetLastError();
    v2 = result;
  }
  if ( SysMtGlobals )
  {
    RtlAcquireSRWLockExclusive(&PfSvcGlobalsLock);
    v4 = 0;
    ServiceStatus.dwCurrentState = 1;
    ServiceStatus.dwWin32ExitCode = v2;
    do
    {
      if ( SetServiceStatus(SysMtGlobals, &ServiceStatus) )
        break;
      Sleep(0x64u);
      ++v4;
    }
    while ( v4 < 0x258 );
    return RtlReleaseSRWLockExclusive(&PfSvcGlobalsLock);
  }
  return result;
}

```

## disassembly

```asm
0x18007a870  mov     [rsp+arg_0], rbx
0x18007a875  push    rdi
0x18007a876  sub     rsp, 30h
0x18007a87a  mov     rax, cs:hEvent
0x18007a881  lea     rcx, PfSvcGlobalsLock
0x18007a888  mov     [rsp+38h+var_10], rax
0x18007a88d  mov     [rsp+38h+var_18], 0
0x18007a896  call    cs:__imp_RtlAcquireSRWLockExclusive
0x18007a89c  lea     rcx, PfSvcGlobalsLock
0x18007a8a3  mov     cs:SysMtGlobals, 0
0x18007a8ae  call    cs:__imp_RtlReleaseSRWLockExclusive
0x18007a8b4  lock inc cs:dword_1800D3FB0
0x18007a8bb  mov     rcx, cs:hEvent; hEvent
0x18007a8c2  call    cs:__imp_ResetEvent
0x18007a8c8  movsxd  r8, cs:dword_1800D3FB0; lpContext
0x18007a8cf  lea     rdx, SysMtServiceControlHandler; lpHandlerProc
0x18007a8d6  xorps   xmm0, xmm0
0x18007a8d9  lea     rcx, aSysmain_0; "sysmain"
0x18007a8e0  movups  xmmword ptr cs:ServiceStatus.dwServiceType, xmm0
0x18007a8e7  mov     cs:ServiceStatus.dwServiceType, 20h ; ' '
0x18007a8f1  movups  xmmword ptr cs:ServiceStatus.dwWin32ExitCode, xmm0
0x18007a8f8  mov     cs:ServiceStatus.dwControlsAccepted, 0C5h
0x18007a902  mov     cs:ServiceStatus.dwCurrentState, 4
0x18007a90c  call    cs:__imp_RegisterServiceCtrlHandlerExW
0x18007a912  mov     cs:SysMtGlobals, rax
0x18007a919  test    rax, rax
0x18007a91c  jnz     short loc_18007A928
0x18007a91e  call    cs:__imp_GetLastError
0x18007a924  mov     edi, eax
0x18007a926  jmp     short loc_18007A964
0x18007a928  lea     rdx, ServiceStatus; lpServiceStatus
0x18007a92f  mov     rcx, rax; hServiceStatus
0x18007a932  call    cs:__imp_SetServiceStatus
0x18007a938  test    eax, eax
0x18007a93a  jz      short loc_18007A91E
0x18007a93c  call    TlgRegisterAggregateProviderEx
0x18007a941  mov     rcx, cs:SysMtGlobals
0x18007a948  mov     ebx, eax
0x18007a94a  mov     [rsp+38h+var_18], rcx
0x18007a94f  lea     rcx, [rsp+38h+var_18]
0x18007a954  call    PfSvcMainThread
0x18007a959  mov     edi, eax
0x18007a95b  test    ebx, ebx
0x18007a95d  js      short loc_18007A964
0x18007a95f  call    TlgUnregisterAggregateProvider
0x18007a964  cmp     cs:SysMtGlobals, 0
0x18007a96c  jz      short loc_18007A9C5
0x18007a96e  lea     rcx, PfSvcGlobalsLock
0x18007a975  call    cs:__imp_RtlAcquireSRWLockExclusive
0x18007a97b  xor     ebx, ebx
0x18007a97d  mov     cs:ServiceStatus.dwCurrentState, 1
0x18007a987  mov     cs:ServiceStatus.dwWin32ExitCode, edi
0x18007a98d  mov     rcx, cs:SysMtGlobals; hServiceStatus
0x18007a994  lea     rdx, ServiceStatus; lpServiceStatus
0x18007a99b  call    cs:__imp_SetServiceStatus
0x18007a9a1  test    eax, eax
0x18007a9a3  jnz     short loc_18007A9B8
0x18007a9a5  lea     ecx, [rax+64h]; dwMilliseconds
0x18007a9a8  call    cs:__imp_Sleep
0x18007a9ae  inc     ebx
0x18007a9b0  cmp     ebx, 258h
0x18007a9b6  jb      short loc_18007A98D
0x18007a9b8  lea     rcx, PfSvcGlobalsLock
0x18007a9bf  call    cs:__imp_RtlReleaseSRWLockExclusive
0x18007a9c5  mov     rbx, [rsp+38h+arg_0]
0x18007a9ca  add     rsp, 30h
0x18007a9ce  pop     rdi
0x18007a9cf  retn
```
