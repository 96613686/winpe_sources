# SensUninitialize(void)

- ea: `0x1800093d8`
- end: `0x180009728`
- name: `?SensUninitialize@@YAHXZ`
- size: `848`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x180009310`

## callees

- `0x180001008`
- `0x180008300`
- `0x1800093b0`
- `0x1800093d8`
- `0x180009cc4`
- `0x18000b010`

## import_xrefs

- `RPCRT4!RpcServerUnregisterIf` at `0x1800094cd`
- `RPCRT4!RpcServerUnregisterIf` at `0x18000953e`
- `RPCRT4!RpcServerUnregisterIf` at `0x1800094cd`
- `RPCRT4!RpcServerUnregisterIf` at `0x18000953e`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180009690`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180009690`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180009616`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180009687`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180009616`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180009687`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x180009623`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x180009623`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800095d3`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180009644`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800095d3`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180009644`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180009602`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180009630`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180009602`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180009630`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1800093e3`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1800093e3`
- `api-ms-win-core-memory-l1-1-0!UnmapViewOfFile` at `0x1800095e5`
- `api-ms-win-core-memory-l1-1-0!UnmapViewOfFile` at `0x1800095e5`
- `KERNELBASE!WTSIsServerContainer` at `0x180009468`
- `KERNELBASE!WTSIsServerContainer` at `0x180009468`
- `api-ms-win-core-com-l1-1-0!CoRevokeClassObject` at `0x1800095ab`
- `api-ms-win-core-com-l1-1-0!CoRevokeClassObject` at `0x1800095ab`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x180009656`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x180009673`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x180009656`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x180009673`
- `WS2_32!__imp_WSAGetLastError` at `0x1800096c1`
- `WS2_32!__imp_WSAGetLastError` at `0x1800096c1`
- `WS2_32!__imp_WSACleanup` at `0x18000969f`
- `WS2_32!__imp_WSACleanup` at `0x18000969f`
- `SYSNTFY!SysNotifyStopServer` at `0x180009439`
- `SYSNTFY!SysNotifyStopServer` at `0x180009439`

## pseudocode

```c
__int64 SensUninitialize(void)
{
  _QWORD *v0; // rcx
  __int64 v1; // rdx
  unsigned int v2; // eax
  unsigned int v3; // ebx
  unsigned int v4; // eax
  _QWORD *v5; // rcx
  unsigned int Error; // eax

  GetTickCount();
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 32, WPP_806191927c0c3ac359d6ef1d0e80ee46_Traceguids);
  }
  TraceLoggingUnregister_EventUnregister();
  if ( qword_180011930 )
    SysNotifyStopServer(&qword_180011930);
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 34, WPP_806191927c0c3ac359d6ef1d0e80ee46_Traceguids);
  }
  if ( !(unsigned __int8)WTSIsServerContainer() )
  {
    if ( (unsigned int)MediaSenseUnregister() )
    {
      v0 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
      {
        v1 = 36;
        goto LABEL_21;
      }
    }
    else
    {
      v0 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v1 = 35;
LABEL_21:
        WPP_SF_(v0[2], v1, WPP_806191927c0c3ac359d6ef1d0e80ee46_Traceguids);
      }
    }
  }
  v2 = RpcServerUnregisterIf(qword_18000C350, 0, 0);
  if ( v2 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 37, WPP_806191927c0c3ac359d6ef1d0e80ee46_Traceguids, v2);
    }
    v3 = 0;
  }
  else
  {
    v3 = 1;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 38, WPP_806191927c0c3ac359d6ef1d0e80ee46_Traceguids);
    }
  }
  v4 = RpcServerUnregisterIf(qword_18000C660, 0, 0);
  if ( v4 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 39, WPP_806191927c0c3ac359d6ef1d0e80ee46_Traceguids, v4);
    }
    v3 = 0;
  }
  else if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
         && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
         && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 40, WPP_806191927c0c3ac359d6ef1d0e80ee46_Traceguids);
  }
  if ( gdwRegCO )
    CoRevokeClassObject(gdwRegCO);
  if ( gpChangeCF )
    ((void (__fastcall *)(struct IClassFactory *))gpChangeCF->lpVtbl->Release)(gpChangeCF);
  EnterCriticalSection(&gSensLock);
  if ( gpSensCache )
  {
    UnmapViewOfFile(gpSensCache);
    gpSensCache = 0;
  }
  if ( ghSensFileMap )
  {
    CloseHandle(ghSensFileMap);
    ghSensFileMap = 0;
  }
  LeaveCriticalSection(&gSensLock);
  ResetEvent(ghSensStartedEvent);
  CloseHandle(ghSensStartedEvent);
  ghSensStartedEvent = 0;
  EnterCriticalSection(&gSensLock);
  if ( ghSCM )
  {
    CloseServiceHandle(ghSCM);
    ghSCM = 0;
  }
  if ( ghRasMan )
  {
    CloseServiceHandle(ghRasMan);
    ghRasMan = 0;
  }
  LeaveCriticalSection(&gSensLock);
  DeleteCriticalSection(&gSensLock);
  if ( !gbWSAInit )
  {
    v5 = WPP_GLOBAL_Control;
    goto LABEL_63;
  }
  if ( WSACleanup() )
  {
    v5 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_61;
    }
    Error = WSAGetLastError();
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 41, WPP_806191927c0c3ac359d6ef1d0e80ee46_Traceguids, Error);
  }
  v5 = WPP_GLOBAL_Control;
LABEL_61:
  gbWSAInit = 0;
LABEL_63:
  if ( v5 != &WPP_GLOBAL_Control && (*((_BYTE *)v5 + 28) & 1) != 0 && *((_BYTE *)v5 + 25) >= 4u )
    WPP_SF_(v5[2], 42, WPP_806191927c0c3ac359d6ef1d0e80ee46_Traceguids);
  return v3;
}

```

## disassembly

```asm
0x1800093d8  push    rbx
0x1800093da  push    rbp
0x1800093db  push    r14
0x1800093dd  push    r15
0x1800093df  sub     rsp, 28h
0x1800093e3  call    cs:__imp_GetTickCount
0x1800093e9  mov     rcx, cs:WPP_GLOBAL_Control
0x1800093f0  lea     rbp, WPP_GLOBAL_Control
0x1800093f7  lea     r15, WPP_806191927c0c3ac359d6ef1d0e80ee46_Traceguids
0x1800093fe  mov     r14b, 5
0x180009401  cmp     rcx, rbp
0x180009404  jz      short loc_180009423
0x180009406  test    byte ptr [rcx+1Ch], 1
0x18000940a  jz      short loc_180009423
0x18000940c  cmp     [rcx+19h], r14b
0x180009410  jb      short loc_180009423
0x180009412  mov     rcx, [rcx+10h]
0x180009416  mov     edx, 20h ; ' '
0x18000941b  mov     r8, r15
0x18000941e  call    WPP_SF_
0x180009423  call    TraceLoggingUnregister_EventUnregister
0x180009428  cmp     cs:qword_180011930, 0
0x180009430  jz      short loc_18000943F
0x180009432  lea     rcx, qword_180011930
0x180009439  call    cs:__imp_SysNotifyStopServer
0x18000943f  mov     rcx, cs:WPP_GLOBAL_Control
0x180009446  cmp     rcx, rbp
0x180009449  jz      short loc_180009468
0x18000944b  test    byte ptr [rcx+1Ch], 1
0x18000944f  jz      short loc_180009468
0x180009451  cmp     [rcx+19h], r14b
0x180009455  jb      short loc_180009468
0x180009457  mov     rcx, [rcx+10h]
0x18000945b  mov     edx, 22h ; '"'
0x180009460  mov     r8, r15
0x180009463  call    WPP_SF_
0x180009468  call    cs:__imp_WTSIsServerContainer
0x18000946e  test    al, al
0x180009470  jnz     short loc_1800094C1
0x180009472  call    ?MediaSenseUnregister@@YAHXZ; MediaSenseUnregister(void)
0x180009477  test    eax, eax
0x180009479  jnz     short loc_180009498
0x18000947b  mov     rcx, cs:WPP_GLOBAL_Control
0x180009482  cmp     rcx, rbp
0x180009485  jz      short loc_1800094C1
0x180009487  test    byte ptr [rcx+1Ch], 1
0x18000948b  jz      short loc_1800094C1
0x18000948d  cmp     byte ptr [rcx+19h], 2
0x180009491  jb      short loc_1800094C1
0x180009493  lea     edx, [rax+23h]
0x180009496  jmp     short loc_1800094B5
0x180009498  mov     rcx, cs:WPP_GLOBAL_Control
0x18000949f  cmp     rcx, rbp
0x1800094a2  jz      short loc_1800094C1
0x1800094a4  test    byte ptr [rcx+1Ch], 1
0x1800094a8  jz      short loc_1800094C1
0x1800094aa  cmp     [rcx+19h], r14b
0x1800094ae  jb      short loc_1800094C1
0x1800094b0  mov     edx, 24h ; '$'
0x1800094b5  mov     rcx, [rcx+10h]
0x1800094b9  mov     r8, r15
0x1800094bc  call    WPP_SF_
0x1800094c1  xor     r8d, r8d; WaitForCallsToComplete
0x1800094c4  lea     rcx, qword_18000C350; IfSpec
0x1800094cb  xor     edx, edx; MgrTypeUuid
0x1800094cd  call    cs:__imp_RpcServerUnregisterIf
0x1800094d3  test    eax, eax
0x1800094d5  jz      short loc_180009507
0x1800094d7  mov     rcx, cs:WPP_GLOBAL_Control
0x1800094de  cmp     rcx, rbp
0x1800094e1  jz      short loc_180009503
0x1800094e3  test    byte ptr [rcx+1Ch], 1
0x1800094e7  jz      short loc_180009503
0x1800094e9  cmp     byte ptr [rcx+19h], 2
0x1800094ed  jb      short loc_180009503
0x1800094ef  mov     rcx, [rcx+10h]
0x1800094f3  mov     edx, 25h ; '%'
0x1800094f8  mov     r9d, eax
0x1800094fb  mov     r8, r15
0x1800094fe  call    WPP_SF_d
0x180009503  xor     ebx, ebx
0x180009505  jmp     short loc_180009532
0x180009507  mov     rcx, cs:WPP_GLOBAL_Control
0x18000950e  mov     ebx, 1
0x180009513  cmp     rcx, rbp
0x180009516  jz      short loc_180009532
0x180009518  test    [rcx+1Ch], bl
0x18000951b  jz      short loc_180009532
0x18000951d  cmp     [rcx+19h], r14b
0x180009521  jb      short loc_180009532
0x180009523  mov     rcx, [rcx+10h]
0x180009527  lea     edx, [rbx+25h]
0x18000952a  mov     r8, r15
0x18000952d  call    WPP_SF_
0x180009532  xor     r8d, r8d; WaitForCallsToComplete
0x180009535  lea     rcx, qword_18000C660; IfSpec
0x18000953c  xor     edx, edx; MgrTypeUuid
0x18000953e  call    cs:__imp_RpcServerUnregisterIf
0x180009544  test    eax, eax
0x180009546  jz      short loc_180009578
0x180009548  mov     rcx, cs:WPP_GLOBAL_Control
0x18000954f  cmp     rcx, rbp
0x180009552  jz      short loc_180009574
0x180009554  test    byte ptr [rcx+1Ch], 1
0x180009558  jz      short loc_180009574
0x18000955a  cmp     [rcx+19h], r14b
0x18000955e  jb      short loc_180009574
0x180009560  mov     rcx, [rcx+10h]
0x180009564  mov     edx, 27h ; '''
0x180009569  mov     r9d, eax
0x18000956c  mov     r8, r15
0x18000956f  call    WPP_SF_d
0x180009574  xor     ebx, ebx
0x180009576  jmp     short loc_1800095A1
0x180009578  mov     rcx, cs:WPP_GLOBAL_Control
0x18000957f  cmp     rcx, rbp
0x180009582  jz      short loc_1800095A1
0x180009584  test    byte ptr [rcx+1Ch], 1
0x180009588  jz      short loc_1800095A1
0x18000958a  cmp     [rcx+19h], r14b
0x18000958e  jb      short loc_1800095A1
0x180009590  mov     rcx, [rcx+10h]
0x180009594  mov     edx, 28h ; '('
0x180009599  mov     r8, r15
0x18000959c  call    WPP_SF_
0x1800095a1  mov     ecx, cs:?gdwRegCO@@3KA; dwRegister
0x1800095a7  test    ecx, ecx
0x1800095a9  jz      short loc_1800095B1
0x1800095ab  call    cs:__imp_CoRevokeClassObject
0x1800095b1  mov     rcx, cs:?gpChangeCF@@3PEAUIClassFactory@@EA; IClassFactory * gpChangeCF
0x1800095b8  test    rcx, rcx
0x1800095bb  jz      short loc_1800095C9
0x1800095bd  mov     rax, [rcx]
0x1800095c0  mov     rax, [rax+10h]
0x1800095c4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800095c9  lea     r14, ?gSensLock@@3U_RTL_CRITICAL_SECTION@@A; _RTL_CRITICAL_SECTION gSensLock
0x1800095d0  mov     rcx, r14; lpCriticalSection
0x1800095d3  call    cs:__imp_EnterCriticalSection
0x1800095d9  mov     rcx, cs:?gpSensCache@@3PEAU_SENS_CACHE@@EA; lpBaseAddress
0x1800095e0  test    rcx, rcx
0x1800095e3  jz      short loc_1800095F6
0x1800095e5  call    cs:__imp_UnmapViewOfFile
0x1800095eb  mov     cs:?gpSensCache@@3PEAU_SENS_CACHE@@EA, 0; _SENS_CACHE * gpSensCache
0x1800095f6  mov     rcx, cs:?ghSensFileMap@@3PEAXEA; hObject
0x1800095fd  test    rcx, rcx
0x180009600  jz      short loc_180009613
0x180009602  call    cs:__imp_CloseHandle
0x180009608  mov     cs:?ghSensFileMap@@3PEAXEA, 0; void * ghSensFileMap
0x180009613  mov     rcx, r14; lpCriticalSection
0x180009616  call    cs:__imp_LeaveCriticalSection
0x18000961c  mov     rcx, cs:?ghSensStartedEvent@@3PEAXEA; hEvent
0x180009623  call    cs:__imp_ResetEvent
0x180009629  mov     rcx, cs:?ghSensStartedEvent@@3PEAXEA; hObject
0x180009630  call    cs:__imp_CloseHandle
0x180009636  mov     rcx, r14; lpCriticalSection
0x180009639  mov     cs:?ghSensStartedEvent@@3PEAXEA, 0; void * ghSensStartedEvent
0x180009644  call    cs:__imp_EnterCriticalSection
0x18000964a  mov     rcx, cs:?ghSCM@@3PEAUSC_HANDLE__@@EA; hSCObject
0x180009651  test    rcx, rcx
0x180009654  jz      short loc_180009667
0x180009656  call    cs:__imp_CloseServiceHandle
0x18000965c  mov     cs:?ghSCM@@3PEAUSC_HANDLE__@@EA, 0; SC_HANDLE__ * ghSCM
0x180009667  mov     rcx, cs:?ghRasMan@@3PEAUSC_HANDLE__@@EA; hSCObject
0x18000966e  test    rcx, rcx
0x180009671  jz      short loc_180009684
0x180009673  call    cs:__imp_CloseServiceHandle
0x180009679  mov     cs:?ghRasMan@@3PEAUSC_HANDLE__@@EA, 0; SC_HANDLE__ * ghRasMan
0x180009684  mov     rcx, r14; lpCriticalSection
0x180009687  call    cs:__imp_LeaveCriticalSection
0x18000968d  mov     rcx, r14; lpCriticalSection
0x180009690  call    cs:__imp_DeleteCriticalSection
0x180009696  cmp     cs:?gbWSAInit@@3_NA, 0; bool gbWSAInit
0x18000969d  jz      short loc_1800096F2
0x18000969f  call    cs:__imp_WSACleanup
0x1800096a5  test    eax, eax
0x1800096a7  jz      short loc_1800096E2
0x1800096a9  mov     rcx, cs:WPP_GLOBAL_Control
0x1800096b0  cmp     rcx, rbp
0x1800096b3  jz      short loc_1800096E9
0x1800096b5  test    byte ptr [rcx+1Ch], 1
0x1800096b9  jz      short loc_1800096E9
0x1800096bb  cmp     byte ptr [rcx+19h], 2
0x1800096bf  jb      short loc_1800096E9
0x1800096c1  call    cs:__imp_WSAGetLastError
0x1800096c7  mov     rcx, cs:WPP_GLOBAL_Control
0x1800096ce  mov     edx, 29h ; ')'
0x1800096d3  mov     r9d, eax
0x1800096d6  mov     r8, r15
0x1800096d9  mov     rcx, [rcx+10h]
0x1800096dd  call    WPP_SF_d
0x1800096e2  mov     rcx, cs:WPP_GLOBAL_Control
0x1800096e9  mov     cs:?gbWSAInit@@3_NA, 0; bool gbWSAInit
0x1800096f0  jmp     short loc_1800096F9
0x1800096f2  mov     rcx, cs:WPP_GLOBAL_Control
0x1800096f9  cmp     rcx, rbp
0x1800096fc  jz      short loc_18000971B
0x1800096fe  test    byte ptr [rcx+1Ch], 1
0x180009702  jz      short loc_18000971B
0x180009704  cmp     byte ptr [rcx+19h], 4
0x180009708  jb      short loc_18000971B
0x18000970a  mov     rcx, [rcx+10h]
0x18000970e  mov     edx, 2Ah ; '*'
0x180009713  mov     r8, r15
0x180009716  call    WPP_SF_
0x18000971b  mov     eax, ebx
0x18000971d  add     rsp, 28h
0x180009721  pop     r15
0x180009723  pop     r14
0x180009725  pop     rbp
0x180009726  pop     rbx
0x180009727  retn
```
