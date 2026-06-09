# ServiceControlHandler(ulong,ulong,void *,void *)

- ea: `0x1800034f0`
- end: `0x1800037a6`
- name: `?ServiceControlHandler@@YAKKKPEAX0@Z`
- size: `694`
- prototype: `DWORD __stdcall(DWORD dwControl, DWORD dwEventType, LPVOID lpEventData, LPVOID lpContext)`
- caller_count: `0`
- callee_count: `6`
- tags: `loader_planting, service_task`

## callees

- `0x180002e30`
- `0x1800034f0`
- `0x1800037ac`
- `0x180008e48`
- `0x1800202e8`
- `0x18002fbb4`

## import_xrefs

- `ntdll!EtwEventWrite` at `0x1800036cf`
- `ntdll!EtwEventWrite` at `0x1800036cf`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1800035fa`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180003737`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1800035fa`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180003737`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x180003597`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x1800036f2`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x180003597`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x1800036f2`

## pseudocode

```c
__int64 __fastcall ServiceControlHandler(DWORD dwControl, DWORD dwEventType, LPVOID lpEventData, LPVOID lpContext)
{
  CThirdPartyManager *v6; // rcx
  unsigned int v7; // edi
  DWORD v9; // ebx
  DWORD v10; // ebx
  __int64 v11; // rdx
  struct _RTL_CRITICAL_SECTION *v12; // rax

  v6 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (CThirdPartyManager *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
  {
    WPP_SF_dd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      10,
      WPP_b798000f0de738f41d9362b18d9c2686_Traceguids,
      dwControl,
      dwEventType);
    v6 = WPP_GLOBAL_Control;
  }
  if ( dwControl == 14 )
  {
    if ( dwEventType == 5 )
    {
      if ( v6 != (CThirdPartyManager *)&WPP_GLOBAL_Control && (*((_BYTE *)v6 + 28) & 4) != 0 )
        WPP_SF_(*((_QWORD *)v6 + 2), 111, WPP_feddbfd1be3833cbefac86bf41ce1941_Traceguids);
      SetEvent(g_hEventSessionLogonEvent);
    }
    else
    {
      if ( dwEventType != 8 )
      {
LABEL_11:
        v7 = 0;
        goto LABEL_12;
      }
      if ( v6 != (CThirdPartyManager *)&WPP_GLOBAL_Control && (*((_BYTE *)v6 + 28) & 4) != 0 )
        WPP_SF_(*((_QWORD *)v6 + 2), 112, WPP_feddbfd1be3833cbefac86bf41ce1941_Traceguids);
      if ( (unsigned int)PollForChanges() )
        CAlertStatus::FireNotificationEvents(g_pAlertStatus, 0);
    }
    v6 = WPP_GLOBAL_Control;
    goto LABEL_11;
  }
  v7 = 0;
  v9 = dwControl - 1;
  if ( !v9 )
  {
LABEL_30:
    v12 = g_pAlertStatus;
    if ( g_pAlertStatus )
    {
      if ( v6 != (CThirdPartyManager *)&WPP_GLOBAL_Control && (*((_BYTE *)v6 + 28) & 4) != 0 )
      {
        WPP_SF_(*((_QWORD *)v6 + 2), 11, WPP_b798000f0de738f41d9362b18d9c2686_Traceguids);
        v12 = g_pAlertStatus;
      }
      CAlertStatus::FireNotificationEvents(v12, 1u);
    }
    else if ( v6 != (CThirdPartyManager *)&WPP_GLOBAL_Control && (*((_BYTE *)v6 + 28) & 2) != 0 )
    {
      WPP_SF_(*((_QWORD *)v6 + 2), 12, WPP_b798000f0de738f41d9362b18d9c2686_Traceguids);
    }
    EtwEventWrite(g_Provider, WSC_SVC_Stop_Begin, 0, 0);
    g_serviceStatus.dwCurrentState = 3;
    if ( g_serviceStatusHandle )
    {
      SetServiceStatus(g_serviceStatusHandle, &g_serviceStatus);
    }
    else
    {
      v6 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (CThirdPartyManager *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
      {
        goto LABEL_44;
      }
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 13, WPP_b798000f0de738f41d9362b18d9c2686_Traceguids);
    }
    v6 = WPP_GLOBAL_Control;
LABEL_44:
    if ( g_stopServiceEvent )
    {
      SetEvent(g_stopServiceEvent);
      goto LABEL_18;
    }
    if ( v6 == (CThirdPartyManager *)&WPP_GLOBAL_Control )
      return v7;
    if ( (*((_BYTE *)v6 + 28) & 2) == 0 )
      goto LABEL_12;
    v11 = 14;
LABEL_49:
    WPP_SF_(*((_QWORD *)v6 + 2), v11, WPP_b798000f0de738f41d9362b18d9c2686_Traceguids);
    goto LABEL_18;
  }
  v10 = v9 - 3;
  if ( v10 )
  {
    if ( v10 != 1 )
    {
      v7 = 120;
      goto LABEL_12;
    }
    goto LABEL_30;
  }
  if ( g_serviceStatusHandle )
  {
    SetServiceStatus(g_serviceStatusHandle, &g_serviceStatus);
LABEL_18:
    v6 = WPP_GLOBAL_Control;
    goto LABEL_12;
  }
  if ( v6 == (CThirdPartyManager *)&WPP_GLOBAL_Control )
    return v7;
  if ( (*((_BYTE *)v6 + 28) & 2) != 0 )
  {
    v11 = 15;
    goto LABEL_49;
  }
LABEL_12:
  if ( v6 != (CThirdPartyManager *)&WPP_GLOBAL_Control && (*((_BYTE *)v6 + 28) & 8) != 0 )
    WPP_SF_d(*((_QWORD *)v6 + 2), 16, WPP_b798000f0de738f41d9362b18d9c2686_Traceguids, v7);
  return v7;
}

```

## disassembly

```asm
0x1800034f0  mov     [rsp+arg_0], rbx
0x1800034f5  mov     [rsp+arg_8], rsi
0x1800034fa  push    rdi
0x1800034fb  sub     rsp, 30h
0x1800034ff  mov     edi, edx
0x180003501  mov     ebx, ecx
0x180003503  mov     rcx, cs:WPP_GLOBAL_Control
0x18000350a  lea     rsi, WPP_GLOBAL_Control
0x180003511  cmp     rcx, rsi
0x180003514  jz      short loc_180003520
0x180003516  test    byte ptr [rcx+1Ch], 8
0x18000351a  jnz     loc_180003605
0x180003520  cmp     ebx, 0Eh
0x180003523  jnz     short loc_180003569
0x180003525  cmp     edi, 5
0x180003528  jz      loc_1800035EA
0x18000352e  cmp     edi, 8
0x180003531  jnz     short loc_180003550
0x180003533  cmp     rcx, rsi
0x180003536  jnz     loc_1800035C6
0x18000353c  call    ?PollForChanges@@YAHXZ; PollForChanges(void)
0x180003541  test    eax, eax
0x180003543  jnz     loc_18000376F
0x180003549  mov     rcx, cs:WPP_GLOBAL_Control
0x180003550  xor     edi, edi
0x180003552  cmp     rcx, rsi
0x180003555  jnz     short loc_1800035A6
0x180003557  mov     rbx, [rsp+38h+arg_0]
0x18000355c  mov     eax, edi
0x18000355e  mov     rsi, [rsp+38h+arg_8]
0x180003563  add     rsp, 30h
0x180003567  pop     rdi
0x180003568  retn
0x180003569  xor     edi, edi
0x18000356b  sub     ebx, 1
0x18000356e  jz      loc_180003659
0x180003574  sub     ebx, 3
0x180003577  jnz     loc_18000362D
0x18000357d  mov     rax, cs:?g_serviceStatusHandle@@3PEAUSERVICE_STATUS_HANDLE__@@EA; SERVICE_STATUS_HANDLE__ * g_serviceStatusHandle
0x180003584  test    rax, rax
0x180003587  jz      loc_18000363C
0x18000358d  lea     rdx, ?g_serviceStatus@@3U_SERVICE_STATUS@@A; lpServiceStatus
0x180003594  mov     rcx, rax; hServiceStatus
0x180003597  call    cs:__imp_SetServiceStatus
0x18000359d  mov     rcx, cs:WPP_GLOBAL_Control
0x1800035a4  jmp     short loc_180003552
0x1800035a6  test    byte ptr [rcx+1Ch], 8
0x1800035aa  jz      short loc_180003557
0x1800035ac  mov     rcx, [rcx+10h]
0x1800035b0  lea     r8, WPP_b798000f0de738f41d9362b18d9c2686_Traceguids
0x1800035b7  mov     edx, 10h
0x1800035bc  mov     r9d, edi
0x1800035bf  call    WPP_SF_d
0x1800035c4  jmp     short loc_180003557
0x1800035c6  test    byte ptr [rcx+1Ch], 4
0x1800035ca  jz      loc_18000353C
0x1800035d0  mov     rcx, [rcx+10h]
0x1800035d4  lea     r8, WPP_feddbfd1be3833cbefac86bf41ce1941_Traceguids
0x1800035db  mov     edx, 70h ; 'p'
0x1800035e0  call    WPP_SF_
0x1800035e5  jmp     loc_18000353C
0x1800035ea  cmp     rcx, rsi
0x1800035ed  jnz     loc_180003782
0x1800035f3  mov     rcx, cs:?g_hEventSessionLogonEvent@@3PEAXEA; hEvent
0x1800035fa  call    cs:__imp_SetEvent
0x180003600  jmp     loc_180003549
0x180003605  mov     rcx, [rcx+10h]
0x180003609  lea     r8, WPP_b798000f0de738f41d9362b18d9c2686_Traceguids
0x180003610  mov     edx, 0Ah
0x180003615  mov     [rsp+38h+var_18], edi
0x180003619  mov     r9d, ebx
0x18000361c  call    WPP_SF_dd
0x180003621  mov     rcx, cs:WPP_GLOBAL_Control
0x180003628  jmp     loc_180003520
0x18000362d  cmp     ebx, 1
0x180003630  jz      short loc_180003659
0x180003632  mov     edi, 78h ; 'x'
0x180003637  jmp     loc_180003552
0x18000363c  cmp     rcx, rsi
0x18000363f  jz      loc_180003557
0x180003645  test    byte ptr [rcx+1Ch], 2
0x180003649  jz      loc_180003552
0x18000364f  mov     edx, 0Fh
0x180003654  jmp     loc_18000375A
0x180003659  mov     rax, cs:?g_pAlertStatus@@3PEAVCAlertStatus@@EA; CAlertStatus * g_pAlertStatus
0x180003660  test    rax, rax
0x180003663  jz      short loc_18000369B
0x180003665  cmp     rcx, rsi
0x180003668  jz      short loc_18000368C
0x18000366a  test    byte ptr [rcx+1Ch], 4
0x18000366e  jz      short loc_18000368C
0x180003670  mov     rcx, [rcx+10h]
0x180003674  lea     r8, WPP_b798000f0de738f41d9362b18d9c2686_Traceguids
0x18000367b  mov     edx, 0Bh
0x180003680  call    WPP_SF_
0x180003685  mov     rax, cs:?g_pAlertStatus@@3PEAVCAlertStatus@@EA; CAlertStatus * g_pAlertStatus
0x18000368c  mov     edx, 1; int
0x180003691  mov     rcx, rax; lpCriticalSection
0x180003694  call    ?FireNotificationEvents@CAlertStatus@@QEAAXH@Z; CAlertStatus::FireNotificationEvents(int)
0x180003699  jmp     short loc_1800036BB
0x18000369b  cmp     rcx, rsi
0x18000369e  jz      short loc_1800036BB
0x1800036a0  test    byte ptr [rcx+1Ch], 2
0x1800036a4  jz      short loc_1800036BB
0x1800036a6  mov     rcx, [rcx+10h]
0x1800036aa  lea     r8, WPP_b798000f0de738f41d9362b18d9c2686_Traceguids
0x1800036b1  mov     edx, 0Ch
0x1800036b6  call    WPP_SF_
0x1800036bb  mov     rcx, cs:?g_Provider@@3_KA; unsigned __int64 g_Provider
0x1800036c2  lea     rdx, WSC_SVC_Stop_Begin
0x1800036c9  xor     r9d, r9d
0x1800036cc  xor     r8d, r8d
0x1800036cf  call    cs:__imp_EtwEventWrite
0x1800036d5  mov     rcx, cs:?g_serviceStatusHandle@@3PEAUSERVICE_STATUS_HANDLE__@@EA; hServiceStatus
0x1800036dc  mov     cs:?g_serviceStatus@@3U_SERVICE_STATUS@@A.dwCurrentState, 3; _SERVICE_STATUS g_serviceStatus ...
0x1800036e6  test    rcx, rcx
0x1800036e9  jz      short loc_1800036FA
0x1800036eb  lea     rdx, ?g_serviceStatus@@3U_SERVICE_STATUS@@A; lpServiceStatus
0x1800036f2  call    cs:__imp_SetServiceStatus
0x1800036f8  jmp     short loc_180003721
0x1800036fa  mov     rcx, cs:WPP_GLOBAL_Control
0x180003701  cmp     rcx, rsi
0x180003704  jz      short loc_180003728
0x180003706  test    byte ptr [rcx+1Ch], 2
0x18000370a  jz      short loc_180003728
0x18000370c  mov     rcx, [rcx+10h]
0x180003710  lea     r8, WPP_b798000f0de738f41d9362b18d9c2686_Traceguids
0x180003717  mov     edx, 0Dh
0x18000371c  call    WPP_SF_
0x180003721  mov     rcx, cs:WPP_GLOBAL_Control
0x180003728  mov     rax, cs:?g_stopServiceEvent@@3PEAXEA; void * g_stopServiceEvent
0x18000372f  test    rax, rax
0x180003732  jz      short loc_180003742
0x180003734  mov     rcx, rax; hEvent
0x180003737  call    cs:__imp_SetEvent
0x18000373d  jmp     loc_18000359D
0x180003742  cmp     rcx, rsi
0x180003745  jz      loc_180003557
0x18000374b  test    byte ptr [rcx+1Ch], 2
0x18000374f  jz      loc_180003552
0x180003755  mov     edx, 0Eh
0x18000375a  mov     rcx, [rcx+10h]
0x18000375e  lea     r8, WPP_b798000f0de738f41d9362b18d9c2686_Traceguids
0x180003765  call    WPP_SF_
0x18000376a  jmp     loc_18000359D
0x18000376f  mov     rcx, cs:?g_pAlertStatus@@3PEAVCAlertStatus@@EA; lpCriticalSection
0x180003776  xor     edx, edx; int
0x180003778  call    ?FireNotificationEvents@CAlertStatus@@QEAAXH@Z; CAlertStatus::FireNotificationEvents(int)
0x18000377d  jmp     loc_180003549
0x180003782  test    byte ptr [rcx+1Ch], 4
0x180003786  jz      loc_1800035F3
0x18000378c  mov     rcx, [rcx+10h]
0x180003790  lea     r8, WPP_feddbfd1be3833cbefac86bf41ce1941_Traceguids
0x180003797  mov     edx, 6Fh ; 'o'
0x18000379c  call    WPP_SF_
0x1800037a1  jmp     loc_1800035F3
```
