# Vml::VmExeModule<GuestComputeServiceModule>::Run(int)

- ea: `0x14003cab4`
- end: `0x14003cc0c`
- name: `?Run@?$VmExeModule@VGuestComputeServiceModule@@@Vml@@QEAAHH@Z`
- size: `344`
- prototype: `__int64 __fastcall(char *lpContext)`
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x14003cc60`

## callees

- `0x14000ddac`
- `0x14000efd8`
- `0x14000f264`
- `0x14003c270`
- `0x14003c5c8`
- `0x14003c76c`
- `0x14003cab4`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x14003cafa`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x14003cb51`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x14003cafa`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x14003cb51`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x14003cbbb`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x14003cbbb`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x14003cb30`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x14003cb8b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x14003cb30`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x14003cb8b`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x14003cb27`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x14003cb82`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x14003cb27`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x14003cb82`
- `api-ms-win-service-core-l1-1-0!RegisterServiceCtrlHandlerExW` at `0x14003cadd`
- `api-ms-win-service-core-l1-1-0!RegisterServiceCtrlHandlerExW` at `0x14003cadd`

## string_xrefs

- `0x14003cbf9`: `onecore\vm\common\vml\VmModules.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall Vml::VmExeModule<GuestComputeServiceModule>::Run(char *lpContext)
{
  const WCHAR *ServiceName; // rax
  SERVICE_STATUS_HANDLE v3; // rax
  const char *v4; // r9
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]

  try
  {
    ServiceName = (const WCHAR *)Vml::VmServiceModule<GuestComputeServiceModule>::GetServiceName(lpContext);
    v3 = RegisterServiceCtrlHandlerExW(
           ServiceName,
           Vml::VmServiceModule<GuestComputeServiceModule>::ServiceHandlerEx,
           lpContext);
    *((_QWORD *)lpContext + 17) = v3;
    if ( !v3 )
      wil::details::in1diag3::Throw_GetLastError(
        retaddr,
        (void *)0xC0C,
        (unsigned int)"onecore\\vm\\common\\vml\\VmModules.h",
        v4);
    EnterCriticalSection((LPCRITICAL_SECTION)lpContext + 1);
    if ( *((_DWORD *)lpContext + 27) != 2 )
      *(_QWORD *)(lpContext + 124) = 0;
    *((_DWORD *)lpContext + 27) = 2;
    *((_DWORD *)lpContext + 29) = 0;
    SetServiceStatus(*((SERVICE_STATUS_HANDLE *)lpContext + 17), (LPSERVICE_STATUS)(lpContext + 104));
    LeaveCriticalSection((LPCRITICAL_SECTION)lpContext + 1);
    Vml::VmExeModule<GuestComputeServiceModule>::PrepareToRun(lpContext);
    if ( *((_DWORD *)lpContext + 27) == 2 && *((_QWORD *)lpContext + 17) )
    {
      EnterCriticalSection((LPCRITICAL_SECTION)lpContext + 1);
      if ( *((_DWORD *)lpContext + 27) != 4 )
        *(_QWORD *)(lpContext + 124) = 0;
      *((_DWORD *)lpContext + 27) = 4;
      *((_DWORD *)lpContext + 29) = 0;
      *((_DWORD *)lpContext + 28) |= 1u;
      SetServiceStatus(*((SERVICE_STATUS_HANDLE *)lpContext + 17), (LPSERVICE_STATUS)(lpContext + 104));
      LeaveCriticalSection((LPCRITICAL_SECTION)lpContext + 1);
    }
    if ( (unsigned int)VmlIsDebugTraceEnabled(49154) )
      VmlDebugTrace(49154, L"Waiting for quit event...\n");
    WaitForSingleObject(*((HANDLE *)lpContext + 11), 0xFFFFFFFF);
    if ( (unsigned int)VmlIsDebugTraceEnabled(49154) )
      VmlDebugTrace(49154, L"Quit event signaled - main message loop terminated.\n");
  }
  catch ( ... )
  {
    Vml::VmServiceModule<GuestComputeServiceModule>::CleanUpFromRun(lpContext);
    throw;
  }
  Vml::VmServiceModule<GuestComputeServiceModule>::CleanUpFromRun(lpContext);
  return 0;
}

```

## disassembly

```asm
0x14003cab4  mov     [rsp+arg_8], rbx
0x14003cab9  push    rdi
0x14003caba  sub     rsp, 30h
0x14003cabe  mov     rbx, rcx
0x14003cac1  mov     [rsp+38h+var_10], rcx
0x14003cac6  mov     [rsp+38h+var_18], 0
0x14003cacb  call    ?GetServiceName@?$VmServiceModule@VGuestComputeServiceModule@@@Vml@@QEBAPEBGXZ; Vml::VmServiceModule<GuestComputeServiceModule>::GetServiceName(void)
0x14003cad0  mov     r8, rbx; lpContext
0x14003cad3  lea     rdx, ?ServiceHandlerEx@?$VmServiceModule@VGuestComputeServiceModule@@@Vml@@CAKKKPEAX0@Z; lpHandlerProc
0x14003cada  mov     rcx, rax; lpServiceName
0x14003cadd  call    cs:__imp_RegisterServiceCtrlHandlerExW
0x14003cae3  mov     [rbx+88h], rax
0x14003caea  test    rax, rax
0x14003caed  jz      loc_14003CBF4
0x14003caf3  lea     rdi, [rbx+28h]
0x14003caf7  mov     rcx, rdi; lpCriticalSection
0x14003cafa  call    cs:__imp_EnterCriticalSection
0x14003cb00  lea     rdx, [rbx+68h]; lpServiceStatus
0x14003cb04  cmp     dword ptr [rdx+4], 2
0x14003cb08  jz      short loc_14003CB12
0x14003cb0a  mov     qword ptr [rbx+7Ch], 0
0x14003cb12  mov     dword ptr [rbx+6Ch], 2
0x14003cb19  mov     dword ptr [rbx+74h], 0
0x14003cb20  mov     rcx, [rbx+88h]; hServiceStatus
0x14003cb27  call    cs:__imp_SetServiceStatus
0x14003cb2d  mov     rcx, rdi; lpCriticalSection
0x14003cb30  call    cs:__imp_LeaveCriticalSection
0x14003cb36  mov     rcx, rbx
0x14003cb39  call    ?PrepareToRun@?$VmExeModule@VGuestComputeServiceModule@@@Vml@@QEAAXXZ; Vml::VmExeModule<GuestComputeServiceModule>::PrepareToRun(void)
0x14003cb3e  cmp     dword ptr [rbx+6Ch], 2
0x14003cb42  jnz     short loc_14003CB91
0x14003cb44  cmp     qword ptr [rbx+88h], 0
0x14003cb4c  jz      short loc_14003CB91
0x14003cb4e  mov     rcx, rdi; lpCriticalSection
0x14003cb51  call    cs:__imp_EnterCriticalSection
0x14003cb57  cmp     dword ptr [rbx+6Ch], 4
0x14003cb5b  jz      short loc_14003CB65
0x14003cb5d  mov     qword ptr [rbx+7Ch], 0
0x14003cb65  mov     dword ptr [rbx+6Ch], 4
0x14003cb6c  mov     dword ptr [rbx+74h], 0
0x14003cb73  or      dword ptr [rbx+70h], 1
0x14003cb77  lea     rdx, [rbx+68h]; lpServiceStatus
0x14003cb7b  mov     rcx, [rbx+88h]; hServiceStatus
0x14003cb82  call    cs:__imp_SetServiceStatus
0x14003cb88  mov     rcx, rdi; lpCriticalSection
0x14003cb8b  call    cs:__imp_LeaveCriticalSection
0x14003cb91  mov     [rsp+38h+var_18], 1
0x14003cb96  mov     edi, 0C002h
0x14003cb9b  mov     ecx, edi
0x14003cb9d  call    VmlIsDebugTraceEnabled
0x14003cba2  test    eax, eax
0x14003cba4  jz      short loc_14003CBB4
0x14003cba6  lea     rdx, aWaitingForQuit; "Waiting for quit event...\n"
0x14003cbad  mov     ecx, edi
0x14003cbaf  call    VmlDebugTrace
0x14003cbb4  or      edx, 0FFFFFFFFh; dwMilliseconds
0x14003cbb7  mov     rcx, [rbx+58h]; hHandle
0x14003cbbb  call    cs:__imp_WaitForSingleObject
0x14003cbc1  mov     ecx, edi
0x14003cbc3  call    VmlIsDebugTraceEnabled
0x14003cbc8  test    eax, eax
0x14003cbca  jz      short loc_14003CBDB
0x14003cbcc  lea     rdx, aQuitEventSigna; "Quit event signaled - main message loop"...
0x14003cbd3  mov     ecx, edi
0x14003cbd5  call    VmlDebugTrace
0x14003cbda  nop
0x14003cbdb  mov     al, [rsp+38h+var_18]
0x14003cbdf  mov     rcx, rbx
0x14003cbe2  call    ?CleanUpFromRun@?$VmServiceModule@VGuestComputeServiceModule@@@Vml@@QEAAXXZ; Vml::VmServiceModule<GuestComputeServiceModule>::CleanUpFromRun(void)
0x14003cbe7  xor     eax, eax
0x14003cbe9  mov     rbx, [rsp+38h+arg_8]
0x14003cbee  add     rsp, 30h
0x14003cbf2  pop     rdi
0x14003cbf3  retn
0x14003cbf4  mov     rcx, [rsp+38h]; this
0x14003cbf9  lea     r8, aOnecoreVmCommo_0; "onecore\\vm\\common\\vml\\VmModules.h"
0x14003cc00  mov     edx, 0C0Ch; void *
0x14003cc05  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
```
