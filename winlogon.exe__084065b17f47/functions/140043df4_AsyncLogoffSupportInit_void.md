# AsyncLogoffSupportInit(void)

- ea: `0x140043df4`
- end: `0x14004400b`
- name: `?AsyncLogoffSupportInit@@YAKXZ`
- size: `535`
- prototype: `unsigned int(void)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x1400877f0`

## callees

- `0x1400057f4`
- `0x1400155f0`
- `0x140043df4`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x140043e1f`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x140043e1f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140043e31`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140043e31`
- `ntdll!RtlRegisterWait` at `0x140043f39`
- `ntdll!RtlRegisterWait` at `0x140043f39`
- `ntdll!RtlInitializeCriticalSection` at `0x140043e8f`
- `ntdll!RtlInitializeCriticalSection` at `0x140043e8f`
- `ntdll!RtlDeleteCriticalSection` at `0x140043fa5`
- `ntdll!RtlDeleteCriticalSection` at `0x14009e97a`
- `ntdll!RtlDeleteCriticalSection` at `0x140043fa5`
- `ntdll!RtlDeleteCriticalSection` at `0x14009e97a`
- `ntdll!RtlNtStatusToDosError` at `0x140043e9b`
- `ntdll!RtlNtStatusToDosError` at `0x140043f45`
- `ntdll!RtlNtStatusToDosError` at `0x140043e9b`
- `ntdll!RtlNtStatusToDosError` at `0x140043f45`

## pseudocode

```c
__int64 AsyncLogoffSupportInit(void)
{
  ULONG LastError; // eax
  ULONG v1; // ebx
  CUser *v2; // rcx
  __int64 v3; // rdx
  int v4; // eax
  CMachine *v5; // rcx
  int v6; // eax

  if ( g_fExecuteSetup || (g_hLogoffEvent = CreateEventW(0, 1, 0, L"Global\\WinlogonLogoff")) != 0 )
  {
    v4 = RtlInitializeCriticalSection(&g_LogoffThreadCritSec);
    if ( v4 >= 0 )
    {
      dword_1400D2E48 = 1;
      CMachine::RegQueryDWORD(
        v5,
        L"Software\\Policies\\Microsoft\\Windows\\System",
        L"AllowBlockingAppsAtShutdown",
        0,
        &g_fShutdownResolverDisabled);
      if ( g_fExecuteSetup
        || (v6 = RtlRegisterWait(&phNewWaitObject, g_hLogoffEvent, AsyncLogoffCb, 0, 0xFFFFFFFF, 8u), v6 >= 0) )
      {
        v1 = 0;
        goto LABEL_20;
      }
      LastError = RtlNtStatusToDosError(v6);
      v1 = LastError;
      v2 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (CUser *)&WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x2000) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v3 = 45;
        goto LABEL_7;
      }
    }
    else
    {
      LastError = RtlNtStatusToDosError(v4);
      v1 = LastError;
      v2 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (CUser *)&WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x2000) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v3 = 44;
        goto LABEL_7;
      }
    }
  }
  else
  {
    LastError = GetLastError();
    v1 = LastError;
    v2 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (CUser *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x2000) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v3 = 43;
LABEL_7:
      WPP_SF_d(*((_QWORD *)v2 + 2), v3, WPP_0869ef17fb29338ff610f5528229efc9_Traceguids, LastError);
LABEL_20:
      v2 = WPP_GLOBAL_Control;
    }
  }
  if ( v1 && dword_1400D2E48 )
  {
    RtlDeleteCriticalSection(&g_LogoffThreadCritSec);
    *(_OWORD *)&g_LogoffThreadCritSec.DebugInfo = 0;
    *(_OWORD *)&g_LogoffThreadCritSec.OwningThread = 0;
    g_LogoffThreadCritSec.SpinCount = 0;
    dword_1400D2E48 = 0;
    v2 = WPP_GLOBAL_Control;
  }
  if ( v2 != (CUser *)&WPP_GLOBAL_Control && (*((_DWORD *)v2 + 7) & 0x2000) != 0 && *((_BYTE *)v2 + 25) >= 4u )
    WPP_SF_d(*((_QWORD *)v2 + 2), 46, WPP_0869ef17fb29338ff610f5528229efc9_Traceguids, v1);
  return v1;
}

```

## disassembly

```asm
0x140043df4  mov     [rsp+arg_0], rbx
0x140043df9  push    rdi
0x140043dfa  sub     rsp, 40h
0x140043dfe  mov     [rsp+48h+var_18], 0
0x140043e06  cmp     cs:?g_fExecuteSetup@@3HA, 0; int g_fExecuteSetup
0x140043e0d  jnz     short loc_140043E88
0x140043e0f  lea     r9, aGlobalWinlogon_0; "Global\\WinlogonLogoff"
0x140043e16  xor     r8d, r8d; bInitialState
0x140043e19  lea     edx, [r8+1]; bManualReset
0x140043e1d  xor     ecx, ecx; lpEventAttributes
0x140043e1f  call    cs:__imp_CreateEventW
0x140043e25  mov     cs:?g_hLogoffEvent@@3PEAXEA, rax; void * g_hLogoffEvent
0x140043e2c  test    rax, rax
0x140043e2f  jnz     short loc_140043E88
0x140043e31  call    cs:__imp_GetLastError
0x140043e37  mov     ebx, eax
0x140043e39  mov     [rsp+48h+var_18], eax
0x140043e3d  lea     rdi, WPP_GLOBAL_Control
0x140043e44  mov     rcx, cs:WPP_GLOBAL_Control
0x140043e4b  cmp     rcx, rdi
0x140043e4e  jz      loc_140043F91
0x140043e54  test    dword ptr [rcx+1Ch], 2000h
0x140043e5b  jz      loc_140043F91
0x140043e61  cmp     byte ptr [rcx+19h], 2
0x140043e65  jb      loc_140043F91
0x140043e6b  mov     edx, 2Bh ; '+'
0x140043e70  mov     r9d, eax
0x140043e73  lea     r8, WPP_0869ef17fb29338ff610f5528229efc9_Traceguids
0x140043e7a  mov     rcx, [rcx+10h]
0x140043e7e  call    WPP_SF_d
0x140043e83  jmp     loc_140043F8A
0x140043e88  lea     rcx, ?g_LogoffThreadCritSec@@3U_RTL_CRITICAL_SECTION@@A; CriticalSection
0x140043e8f  call    cs:__imp_RtlInitializeCriticalSection
0x140043e95  test    eax, eax
0x140043e97  jns     short loc_140043EDC
0x140043e99  mov     ecx, eax; Status
0x140043e9b  call    cs:__imp_RtlNtStatusToDosError
0x140043ea1  mov     ebx, eax
0x140043ea3  mov     [rsp+48h+var_18], eax
0x140043ea7  lea     rdi, WPP_GLOBAL_Control
0x140043eae  mov     rcx, cs:WPP_GLOBAL_Control
0x140043eb5  cmp     rcx, rdi
0x140043eb8  jz      loc_140043F91
0x140043ebe  test    dword ptr [rcx+1Ch], 2000h
0x140043ec5  jz      loc_140043F91
0x140043ecb  cmp     byte ptr [rcx+19h], 2
0x140043ecf  jb      loc_140043F91
0x140043ed5  mov     edx, 2Ch ; ','
0x140043eda  jmp     short loc_140043E70
0x140043edc  mov     cs:dword_1400D2E48, 1
0x140043ee6  lea     rax, ?g_fShutdownResolverDisabled@@3HA; int g_fShutdownResolverDisabled
0x140043eed  mov     qword ptr [rsp+48h+ulMilliseconds], rax; unsigned int *
0x140043ef2  xor     r9d, r9d; unsigned int
0x140043ef5  lea     r8, aAllowblockinga; "AllowBlockingAppsAtShutdown"
0x140043efc  lea     rdx, aSoftwarePolici; "Software\\Policies\\Microsoft\\Windows"...
0x140043f03  call    ?RegQueryDWORD@CMachine@@QEAAKPEBG0KPEAK@Z; CMachine::RegQueryDWORD(ushort const *,ushort const *,ulong,ulong *)
0x140043f08  cmp     cs:?g_fExecuteSetup@@3HA, 0; int g_fExecuteSetup
0x140043f0f  jnz     short loc_140043F7D
0x140043f11  mov     [rsp+48h+ulFlags], 8; ulFlags
0x140043f19  mov     [rsp+48h+ulMilliseconds], 0FFFFFFFFh; ulMilliseconds
0x140043f21  xor     r9d, r9d; pvContext
0x140043f24  lea     r8, ?AsyncLogoffCb@@YAXPEAXE@Z; Callback
0x140043f2b  mov     rdx, cs:?g_hLogoffEvent@@3PEAXEA; hObject
0x140043f32  lea     rcx, phNewWaitObject; phNewWaitObject
0x140043f39  call    cs:__imp_RtlRegisterWait
0x140043f3f  test    eax, eax
0x140043f41  jns     short loc_140043F7D
0x140043f43  mov     ecx, eax; Status
0x140043f45  call    cs:__imp_RtlNtStatusToDosError
0x140043f4b  mov     ebx, eax
0x140043f4d  mov     [rsp+48h+var_18], eax
0x140043f51  lea     rdi, WPP_GLOBAL_Control
0x140043f58  mov     rcx, cs:WPP_GLOBAL_Control
0x140043f5f  cmp     rcx, rdi
0x140043f62  jz      short loc_140043F91
0x140043f64  test    dword ptr [rcx+1Ch], 2000h
0x140043f6b  jz      short loc_140043F91
0x140043f6d  cmp     byte ptr [rcx+19h], 2
0x140043f71  jb      short loc_140043F91
0x140043f73  mov     edx, 2Dh ; '-'
0x140043f78  jmp     loc_140043E70
0x140043f7d  xor     ebx, ebx
0x140043f7f  mov     [rsp+48h+var_18], ebx
0x140043f83  lea     rdi, WPP_GLOBAL_Control
0x140043f8a  mov     rcx, cs:WPP_GLOBAL_Control
0x140043f91  test    ebx, ebx
0x140043f93  jz      short loc_140043FD2
0x140043f95  cmp     cs:dword_1400D2E48, 0
0x140043f9c  jz      short loc_140043FD2
0x140043f9e  lea     rcx, ?g_LogoffThreadCritSec@@3U_RTL_CRITICAL_SECTION@@A; CriticalSection
0x140043fa5  call    cs:__imp_RtlDeleteCriticalSection
0x140043fab  xorps   xmm0, xmm0
0x140043fae  xor     eax, eax
0x140043fb0  movups  xmmword ptr cs:?g_LogoffThreadCritSec@@3U_RTL_CRITICAL_SECTION@@A.DebugInfo, xmm0; _RTL_CRITICAL_SECTION g_LogoffThreadCritSec ...
0x140043fb7  movups  xmmword ptr cs:?g_LogoffThreadCritSec@@3U_RTL_CRITICAL_SECTION@@A.OwningThread, xmm0; _RTL_CRITICAL_SECTION g_LogoffThreadCritSec ...
0x140043fbe  mov     cs:?g_LogoffThreadCritSec@@3U_RTL_CRITICAL_SECTION@@A.SpinCount, rax; _RTL_CRITICAL_SECTION g_LogoffThreadCritSec ...
0x140043fc5  mov     cs:dword_1400D2E48, eax
0x140043fcb  mov     rcx, cs:WPP_GLOBAL_Control
0x140043fd2  cmp     rcx, rdi
0x140043fd5  jz      short loc_140043FFE
0x140043fd7  test    dword ptr [rcx+1Ch], 2000h
0x140043fde  jz      short loc_140043FFE
0x140043fe0  cmp     byte ptr [rcx+19h], 4
0x140043fe4  jb      short loc_140043FFE
0x140043fe6  mov     edx, 2Eh ; '.'
0x140043feb  mov     r9d, ebx
0x140043fee  lea     r8, WPP_0869ef17fb29338ff610f5528229efc9_Traceguids
0x140043ff5  mov     rcx, [rcx+10h]
0x140043ff9  call    WPP_SF_d
0x140043ffe  mov     eax, ebx
0x140044000  mov     rbx, [rsp+48h+arg_0]
0x140044005  add     rsp, 40h
0x140044009  pop     rdi
0x14004400a  retn
0x14009e95b  push    rbp
0x14009e95d  sub     rsp, 30h
0x14009e961  mov     rbp, rdx
0x14009e964  cmp     dword ptr [rbp+30h], 0
0x14009e968  jz      short loc_14009E9A0
0x14009e96a  cmp     cs:dword_1400D2E48, 0
0x14009e971  jz      short loc_14009E9A0
0x14009e973  lea     rcx, ?g_LogoffThreadCritSec@@3U_RTL_CRITICAL_SECTION@@A; CriticalSection
0x14009e97a  call    cs:__imp_RtlDeleteCriticalSection
0x14009e980  xorps   xmm0, xmm0
0x14009e983  xor     eax, eax
0x14009e985  movups  xmmword ptr cs:?g_LogoffThreadCritSec@@3U_RTL_CRITICAL_SECTION@@A.DebugInfo, xmm0; _RTL_CRITICAL_SECTION g_LogoffThreadCritSec ...
0x14009e98c  movups  xmmword ptr cs:?g_LogoffThreadCritSec@@3U_RTL_CRITICAL_SECTION@@A.OwningThread, xmm0; _RTL_CRITICAL_SECTION g_LogoffThreadCritSec ...
0x14009e993  mov     cs:?g_LogoffThreadCritSec@@3U_RTL_CRITICAL_SECTION@@A.SpinCount, rax; _RTL_CRITICAL_SECTION g_LogoffThreadCritSec ...
0x14009e99a  mov     cs:dword_1400D2E48, eax
0x14009e9a0  add     rsp, 30h
0x14009e9a4  pop     rbp
0x14009e9a5  retn
```
