# TetheringService::CleanUp(void)

- ea: `0x180015e30`
- end: `0x1800162d4`
- name: `?CleanUp@TetheringService@@AEAAXXZ`
- size: `1188`
- prototype: `void __fastcall(TetheringService *__hidden this)`
- caller_count: `2`
- callee_count: `11`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x18000bd50`
- `0x18001935c`

## callees

- `0x18000304c`
- `0x18000bf4c`
- `0x18000bf74`
- `0x18000d73c`
- `0x18000f920`
- `0x1800107fc`
- `0x180015e30`
- `0x18001f740`
- `0x180020bd8`
- `0x180025bfc`
- `0x180026558`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18001623e`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18001623e`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180015f07`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180015f07`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180015ee0`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180016250`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180015ee0`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180016250`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180015e9d`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180016213`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180015e9d`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180016213`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolCleanupGroup` at `0x1800160a8`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolCleanupGroup` at `0x1800160a8`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolCleanupGroupMembers` at `0x18001609b`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolCleanupGroupMembers` at `0x18001609b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800161ca`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800161e3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800161fc`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800161ca`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800161e3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800161fc`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x180015f9a`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x180015fb3`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x180015f9a`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x180015fb3`
- `api-ms-win-core-threadpool-legacy-l1-1-0!DeleteTimerQueueTimer` at `0x180016164`
- `api-ms-win-core-threadpool-legacy-l1-1-0!DeleteTimerQueueTimer` at `0x180016180`
- `api-ms-win-core-threadpool-legacy-l1-1-0!DeleteTimerQueueTimer` at `0x18001619c`
- `api-ms-win-core-threadpool-legacy-l1-1-0!DeleteTimerQueueTimer` at `0x180016164`
- `api-ms-win-core-threadpool-legacy-l1-1-0!DeleteTimerQueueTimer` at `0x180016180`
- `api-ms-win-core-threadpool-legacy-l1-1-0!DeleteTimerQueueTimer` at `0x18001619c`
- `api-ms-win-core-threadpool-legacy-l1-1-0!DeleteTimerQueueEx` at `0x1800161b1`
- `api-ms-win-core-threadpool-legacy-l1-1-0!DeleteTimerQueueEx` at `0x1800161b1`
- `ntdll!RtlUnsubscribeWnfNotificationWaitForCompletion` at `0x180015eb7`
- `ntdll!RtlUnsubscribeWnfNotificationWaitForCompletion` at `0x180015ed0`
- `ntdll!RtlUnsubscribeWnfNotificationWaitForCompletion` at `0x180015eb7`
- `ntdll!RtlUnsubscribeWnfNotificationWaitForCompletion` at `0x180015ed0`
- `wlanapi!WlanRegisterNotification` at `0x18001627d`
- `wlanapi!WlanRegisterNotification` at `0x18001627d`
- `wlanapi!WlanCloseHandle` at `0x18001628c`
- `wlanapi!WlanCloseHandle` at `0x18001628c`

## pseudocode

```c
void __fastcall TetheringService::CleanUp(TetheringService *this)
{
  void *v2; // rcx
  SC_HANDLE *v3; // rdi
  TetheringServiceTelemetry *v4; // rcx
  unsigned int v5; // esi
  int v6; // eax
  TetheringServiceTelemetry *v7; // rcx
  __int64 v8; // rsi
  __int64 v9; // rdi
  void *v10; // rcx
  void *v11; // rdx
  void *v12; // rdx
  void *v13; // rdx
  void *v14; // rcx
  void *v15; // rcx
  HANDLE v16; // rcx
  _QWORD **v17; // rdi
  _QWORD *v18; // rcx
  _QWORD *v19; // rax
  void *v20; // rcx

  if ( WPP_GLOBAL_Control != (TetheringServiceTelemetry *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 39, &WPP_ad96878468d9324e80184c9fc08cbc2e_Traceguids);
  }
  if ( *((_BYTE *)this + 1890) )
    CPowerHandler::PreventSleepInternal((TetheringService *)((char *)this + 1752), 0);
  BtPanHandler::Shutdown((TetheringService *)((char *)this + 1184));
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 1488));
  TetheringService::UninitializeCellularWnfSubscriptions(this);
  if ( *((_QWORD *)this + 213) )
  {
    RtlUnsubscribeWnfNotificationWaitForCompletion();
    *((_QWORD *)this + 213) = 0;
  }
  if ( *((_QWORD *)this + 212) )
  {
    RtlUnsubscribeWnfNotificationWaitForCompletion();
    *((_QWORD *)this + 212) = 0;
  }
  LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 1488));
  TetheringService::StopSharing(this, 1, 12);
  v2 = (void *)*((_QWORD *)this + 74);
  if ( v2 )
    SetEvent(v2);
  EntitlementMgr::Uninitialize((TetheringService *)((char *)this + 568));
  v3 = (SC_HANDLE *)((char *)this + 312);
  v4 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (TetheringServiceTelemetry *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 14, &WPP_61b13f64d1073f22fbe44920aae21d64_Traceguids);
    v4 = WPP_GLOBAL_Control;
  }
  v5 = 0;
  if ( *((_BYTE *)this + 336) )
  {
    v6 = SharedAccessSvcMgr::Stop((TetheringService *)((char *)this + 312));
    v5 = v6;
    if ( v6 >= 0 )
    {
LABEL_20:
      v4 = WPP_GLOBAL_Control;
      goto LABEL_21;
    }
    v4 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (TetheringServiceTelemetry *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        15,
        &WPP_61b13f64d1073f22fbe44920aae21d64_Traceguids,
        (unsigned int)v6);
      goto LABEL_20;
    }
  }
LABEL_21:
  if ( *((_QWORD *)this + 40) )
  {
    CloseServiceHandle(*((SC_HANDLE *)this + 40));
    *((_QWORD *)this + 40) = 0;
    v4 = WPP_GLOBAL_Control;
  }
  if ( *v3 )
  {
    CloseServiceHandle(*v3);
    *v3 = 0;
    v4 = WPP_GLOBAL_Control;
  }
  if ( v4 != (TetheringServiceTelemetry *)&WPP_GLOBAL_Control && (*((_BYTE *)v4 + 28) & 8) != 0 )
  {
    WPP_SF_d(*((_QWORD *)v4 + 2), 16, &WPP_61b13f64d1073f22fbe44920aae21d64_Traceguids, v5);
    v4 = WPP_GLOBAL_Control;
  }
  if ( v4 != (TetheringServiceTelemetry *)&WPP_GLOBAL_Control && (*((_BYTE *)v4 + 28) & 8) != 0 )
    WPP_SF_(*((_QWORD *)v4 + 2), 14, &WPP_c92c1a9e691a3125ab7df275584a9ff2_Traceguids);
  InterfaceMgr::DisableWFDGOMode((TetheringService *)((char *)this + 352), 1, 1, 1, 1, 1, 1, 1);
  *((_OWORD *)this + 27) = 0;
  *((_OWORD *)this + 26) = 0;
  *(GUID *)((char *)this + 524) = GUID_NULL;
  v7 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (TetheringServiceTelemetry *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 15, &WPP_c92c1a9e691a3125ab7df275584a9ff2_Traceguids, 0);
    v7 = WPP_GLOBAL_Control;
  }
  if ( *((_QWORD *)this + 235) )
  {
    CloseThreadpoolCleanupGroupMembers(*((PTP_CLEANUP_GROUP *)this + 235), 1, 0);
    CloseThreadpoolCleanupGroup(*((PTP_CLEANUP_GROUP *)this + 235));
    *((_QWORD *)this + 235) = 0;
    v7 = WPP_GLOBAL_Control;
  }
  if ( v7 != (TetheringServiceTelemetry *)&WPP_GLOBAL_Control && (*((_BYTE *)v7 + 28) & 8) != 0 )
    WPP_SF_(*((_QWORD *)v7 + 2), 17, &WPP_526e2569a9333f836f2472508a4e2fa1_Traceguids);
  v8 = 0;
  v9 = 0;
  do
  {
    if ( *(_DWORD *)((char *)&g_rgTetheringSettingsGlobal + v9 + 12) )
    {
      if ( ((*(_DWORD *)((char *)&g_rgTetheringSettingsGlobal + v9 + 8) - 1) & 0xFFFFFFFD) == 0 )
      {
        v10 = *(struct _TETHERING_SETTING near **)((char *)&g_rgTetheringSettingsGlobal + v9 + 16);
        if ( v10 )
        {
          free(v10);
          *(struct _TETHERING_SETTING near **)((char *)&g_rgTetheringSettingsGlobal + v9 + 16) = 0;
        }
      }
    }
    ++v8;
    v9 += 48;
  }
  while ( v8 != 17 );
  g_fTetheringSettingsLoaded = 0;
  if ( WPP_GLOBAL_Control != (TetheringServiceTelemetry *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 18, &WPP_526e2569a9333f836f2472508a4e2fa1_Traceguids);
  }
  v11 = (void *)*((_QWORD *)this + 197);
  if ( v11 )
    DeleteTimerQueueTimer(*((HANDLE *)this + 198), v11, (HANDLE)0xFFFFFFFFFFFFFFFFLL);
  v12 = (void *)*((_QWORD *)this + 200);
  if ( v12 )
    DeleteTimerQueueTimer(*((HANDLE *)this + 201), v12, (HANDLE)0xFFFFFFFFFFFFFFFFLL);
  v13 = (void *)*((_QWORD *)this + 203);
  if ( v13 )
    DeleteTimerQueueTimer(*((HANDLE *)this + 204), v13, (HANDLE)0xFFFFFFFFFFFFFFFFLL);
  v14 = (void *)*((_QWORD *)this + 195);
  if ( v14 )
    DeleteTimerQueueEx(v14, (HANDLE)0xFFFFFFFFFFFFFFFFLL);
  v15 = (void *)*((_QWORD *)this + 194);
  *((_QWORD *)this + 195) = 0;
  if ( v15 )
    CloseHandle(v15);
  v16 = g_hWlanDisconnected;
  *((_QWORD *)this + 194) = 0;
  if ( v16 )
    CloseHandle(v16);
  g_hWlanDisconnected = 0;
  if ( g_hWlanPowerSet )
    CloseHandle(g_hWlanPowerSet);
  g_hWlanPowerSet = 0;
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 1304));
  v17 = (_QWORD **)((char *)this + 1344);
  while ( 1 )
  {
    v18 = *v17;
    if ( *v17 == v17 )
      break;
    if ( (_QWORD **)v18[1] != v17 || (v19 = (_QWORD *)*v18, *(_QWORD **)(*v18 + 8LL) != v18) )
      __fastfail(3u);
    *v17 = v19;
    v19[1] = v17;
    free(v18);
  }
  LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 1304));
  v20 = (void *)*((_QWORD *)this + 191);
  if ( v20 )
  {
    WlanRegisterNotification(v20, 0, 0, TetheringService::s_WlanNotificationCallback, 0, 0, 0);
    WlanCloseHandle(*((HANDLE *)this + 191), 0);
    *((_QWORD *)this + 191) = 0;
  }
  *((_BYTE *)this + 1888) = 0;
  if ( WPP_GLOBAL_Control != (TetheringServiceTelemetry *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 40, &WPP_ad96878468d9324e80184c9fc08cbc2e_Traceguids);
  }
}

```

## disassembly

```asm
0x180015e30  push    rbx
0x180015e32  push    rbp
0x180015e33  push    rsi
0x180015e34  push    rdi
0x180015e35  push    r12
0x180015e37  push    r15
0x180015e39  sub     rsp, 48h
0x180015e3d  mov     rbx, rcx
0x180015e40  mov     rcx, cs:WPP_GLOBAL_Control
0x180015e47  lea     r15, WPP_GLOBAL_Control
0x180015e4e  cmp     rcx, r15
0x180015e51  jz      short loc_180015E6E
0x180015e53  test    byte ptr [rcx+1Ch], 8
0x180015e57  jz      short loc_180015E6E
0x180015e59  mov     rcx, [rcx+10h]
0x180015e5d  lea     r8, WPP_ad96878468d9324e80184c9fc08cbc2e_Traceguids
0x180015e64  mov     edx, 27h ; '''
0x180015e69  call    WPP_SF_
0x180015e6e  xor     ebp, ebp
0x180015e70  cmp     [rbx+762h], bpl
0x180015e77  jz      short loc_180015E87
0x180015e79  lea     rcx, [rbx+6D8h]; this
0x180015e80  xor     edx, edx; bool
0x180015e82  call    ?PreventSleepInternal@CPowerHandler@@AEAAJ_N@Z; CPowerHandler::PreventSleepInternal(bool)
0x180015e87  lea     rcx, [rbx+4A0h]; this
0x180015e8e  call    ?Shutdown@BtPanHandler@@QEAAJXZ; BtPanHandler::Shutdown(void)
0x180015e93  lea     rdi, [rbx+5D0h]
0x180015e9a  mov     rcx, rdi; lpCriticalSection
0x180015e9d  call    cs:__imp_EnterCriticalSection
0x180015ea3  mov     rcx, rbx; this
0x180015ea6  call    ?UninitializeCellularWnfSubscriptions@TetheringService@@AEAAXXZ; TetheringService::UninitializeCellularWnfSubscriptions(void)
0x180015eab  mov     rcx, [rbx+6A8h]
0x180015eb2  test    rcx, rcx
0x180015eb5  jz      short loc_180015EC4
0x180015eb7  call    cs:__imp_RtlUnsubscribeWnfNotificationWaitForCompletion
0x180015ebd  mov     [rbx+6A8h], rbp
0x180015ec4  mov     rcx, [rbx+6A0h]
0x180015ecb  test    rcx, rcx
0x180015ece  jz      short loc_180015EDD
0x180015ed0  call    cs:__imp_RtlUnsubscribeWnfNotificationWaitForCompletion
0x180015ed6  mov     [rbx+6A0h], rbp
0x180015edd  mov     rcx, rdi; lpCriticalSection
0x180015ee0  call    cs:__imp_LeaveCriticalSection
0x180015ee6  mov     edx, 1
0x180015eeb  mov     rcx, rbx
0x180015eee  lea     r8d, [rdx+0Bh]
0x180015ef2  call    ?StopSharing@TetheringService@@AEAAJKW4StopReason@1@@Z; TetheringService::StopSharing(ulong,TetheringService::StopReason)
0x180015ef7  lea     rdi, [rbx+238h]
0x180015efe  mov     rcx, [rdi+18h]; hEvent
0x180015f02  test    rcx, rcx
0x180015f05  jz      short loc_180015F0D
0x180015f07  call    cs:__imp_SetEvent
0x180015f0d  mov     rcx, rdi; this
0x180015f10  call    ?Uninitialize@EntitlementMgr@@QEAAXXZ; EntitlementMgr::Uninitialize(void)
0x180015f15  lea     rdi, [rbx+138h]
0x180015f1c  mov     rcx, cs:WPP_GLOBAL_Control
0x180015f23  lea     r12, WPP_61b13f64d1073f22fbe44920aae21d64_Traceguids
0x180015f2a  cmp     rcx, r15
0x180015f2d  jz      short loc_180015F4D
0x180015f2f  test    byte ptr [rcx+1Ch], 8
0x180015f33  jz      short loc_180015F4D
0x180015f35  mov     rcx, [rcx+10h]
0x180015f39  mov     edx, 0Eh
0x180015f3e  mov     r8, r12
0x180015f41  call    WPP_SF_
0x180015f46  mov     rcx, cs:WPP_GLOBAL_Control
0x180015f4d  mov     esi, ebp
0x180015f4f  cmp     [rdi+18h], bpl
0x180015f53  jz      short loc_180015F90
0x180015f55  mov     rcx, rdi; this
0x180015f58  call    ?Stop@SharedAccessSvcMgr@@QEAAJXZ; SharedAccessSvcMgr::Stop(void)
0x180015f5d  mov     esi, eax
0x180015f5f  test    eax, eax
0x180015f61  jns     short loc_180015F89
0x180015f63  mov     rcx, cs:WPP_GLOBAL_Control
0x180015f6a  cmp     rcx, r15
0x180015f6d  jz      short loc_180015F90
0x180015f6f  test    byte ptr [rcx+1Ch], 1
0x180015f73  jz      short loc_180015F90
0x180015f75  mov     rcx, [rcx+10h]
0x180015f79  mov     edx, 0Fh
0x180015f7e  mov     r9d, eax
0x180015f81  mov     r8, r12
0x180015f84  call    WPP_SF_d
0x180015f89  mov     rcx, cs:WPP_GLOBAL_Control
0x180015f90  cmp     [rdi+8], rbp
0x180015f94  jz      short loc_180015FAB
0x180015f96  mov     rcx, [rdi+8]; hSCObject
0x180015f9a  call    cs:__imp_CloseServiceHandle
0x180015fa0  mov     [rdi+8], rbp
0x180015fa4  mov     rcx, cs:WPP_GLOBAL_Control
0x180015fab  cmp     [rdi], rbp
0x180015fae  jz      short loc_180015FC3
0x180015fb0  mov     rcx, [rdi]; hSCObject
0x180015fb3  call    cs:__imp_CloseServiceHandle
0x180015fb9  mov     [rdi], rbp
0x180015fbc  mov     rcx, cs:WPP_GLOBAL_Control
0x180015fc3  cmp     rcx, r15
0x180015fc6  jz      short loc_180015FE9
0x180015fc8  test    byte ptr [rcx+1Ch], 8
0x180015fcc  jz      short loc_180015FE9
0x180015fce  mov     rcx, [rcx+10h]
0x180015fd2  mov     edx, 10h
0x180015fd7  mov     r9d, esi
0x180015fda  mov     r8, r12
0x180015fdd  call    WPP_SF_d
0x180015fe2  mov     rcx, cs:WPP_GLOBAL_Control
0x180015fe9  lea     rdi, [rbx+160h]
0x180015ff0  cmp     rcx, r15
0x180015ff3  jz      short loc_180016010
0x180015ff5  test    byte ptr [rcx+1Ch], 8
0x180015ff9  jz      short loc_180016010
0x180015ffb  mov     rcx, [rcx+10h]
0x180015fff  lea     r8, WPP_c92c1a9e691a3125ab7df275584a9ff2_Traceguids
0x180016006  mov     edx, 0Eh
0x18001600b  call    WPP_SF_
0x180016010  mov     [rsp+78h+var_40], 1; bool
0x180016015  mov     r9b, 1; bool
0x180016018  mov     byte ptr [rsp+78h+pdwPrevNotifSource], 1; bool
0x18001601d  mov     r8b, r9b; bool
0x180016020  mov     byte ptr [rsp+78h+pReserved], 1; bool
0x180016025  mov     dl, r9b; bool
0x180016028  mov     rcx, rdi; this
0x18001602b  mov     byte ptr [rsp+78h+pCallbackContext], 1; bool
0x180016030  call    ?DisableWFDGOMode@InterfaceMgr@@AEAAJ_N000000@Z; InterfaceMgr::DisableWFDGOMode(bool,bool,bool,bool,bool,bool,bool)
0x180016035  xorps   xmm0, xmm0
0x180016038  xorps   xmm1, xmm1
0x18001603b  movdqu  xmmword ptr [rdi+50h], xmm0
0x180016040  movdqu  xmmword ptr [rdi+40h], xmm1
0x180016045  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x18001604c  movdqu  xmmword ptr [rdi+0ACh], xmm0
0x180016054  mov     rcx, cs:WPP_GLOBAL_Control
0x18001605b  cmp     rcx, r15
0x18001605e  jz      short loc_180016085
0x180016060  test    byte ptr [rcx+1Ch], 8
0x180016064  jz      short loc_180016085
0x180016066  mov     rcx, [rcx+10h]
0x18001606a  lea     r8, WPP_c92c1a9e691a3125ab7df275584a9ff2_Traceguids
0x180016071  mov     edx, 0Fh
0x180016076  xor     r9d, r9d
0x180016079  call    WPP_SF_d
0x18001607e  mov     rcx, cs:WPP_GLOBAL_Control
0x180016085  mov     rax, [rbx+758h]
0x18001608c  test    rax, rax
0x18001608f  jz      short loc_1800160BC
0x180016091  xor     r8d, r8d; pvCleanupContext
0x180016094  mov     rcx, rax; ptpcg
0x180016097  lea     edx, [r8+1]; fCancelPendingCallbacks
0x18001609b  call    cs:__imp_CloseThreadpoolCleanupGroupMembers
0x1800160a1  mov     rcx, [rbx+758h]; ptpcg
0x1800160a8  call    cs:__imp_CloseThreadpoolCleanupGroup
0x1800160ae  mov     [rbx+758h], rbp
0x1800160b5  mov     rcx, cs:WPP_GLOBAL_Control
0x1800160bc  cmp     rcx, r15
0x1800160bf  jz      short loc_1800160DC
0x1800160c1  test    byte ptr [rcx+1Ch], 8
0x1800160c5  jz      short loc_1800160DC
0x1800160c7  mov     rcx, [rcx+10h]
0x1800160cb  lea     r8, WPP_526e2569a9333f836f2472508a4e2fa1_Traceguids
0x1800160d2  mov     edx, 11h
0x1800160d7  call    WPP_SF_
0x1800160dc  mov     rsi, rbp
0x1800160df  lea     r12, ?g_rgTetheringSettingsGlobal@@3PAU_TETHERING_SETTING@@A; _TETHERING_SETTING near * g_rgTetheringSettingsGlobal
0x1800160e6  mov     rdi, rbp
0x1800160e9  cmp     [rdi+r12+0Ch], ebp
0x1800160ee  jz      short loc_180016112
0x1800160f0  mov     eax, [rdi+r12+8]
0x1800160f5  dec     eax
0x1800160f7  test    eax, 0FFFFFFFDh
0x1800160fc  jnz     short loc_180016112
0x1800160fe  mov     rcx, [rdi+r12+10h]; Block
0x180016103  test    rcx, rcx
0x180016106  jz      short loc_180016112
0x180016108  call    free
0x18001610d  mov     [rdi+r12+10h], rbp
0x180016112  inc     rsi
0x180016115  add     rdi, 30h ; '0'
0x180016119  cmp     rsi, 11h
0x18001611d  jnz     short loc_1800160E9
0x18001611f  mov     cs:?g_fTetheringSettingsLoaded@@3HA, ebp; int g_fTetheringSettingsLoaded
0x180016125  mov     rcx, cs:WPP_GLOBAL_Control
0x18001612c  cmp     rcx, r15
0x18001612f  jz      short loc_18001614A
0x180016131  test    byte ptr [rcx+1Ch], 8
0x180016135  jz      short loc_18001614A
0x180016137  mov     rcx, [rcx+10h]
0x18001613b  lea     edx, [rsi+1]
0x18001613e  lea     r8, WPP_526e2569a9333f836f2472508a4e2fa1_Traceguids
0x180016145  call    WPP_SF_
0x18001614a  mov     rdx, [rbx+628h]; Timer
0x180016151  or      rdi, 0FFFFFFFFFFFFFFFFh
0x180016155  test    rdx, rdx
0x180016158  jz      short loc_18001616A
0x18001615a  mov     rcx, [rbx+630h]; TimerQueue
0x180016161  mov     r8, rdi; CompletionEvent
0x180016164  call    cs:__imp_DeleteTimerQueueTimer
0x18001616a  mov     rdx, [rbx+640h]; Timer
0x180016171  test    rdx, rdx
0x180016174  jz      short loc_180016186
0x180016176  mov     rcx, [rbx+648h]; TimerQueue
0x18001617d  mov     r8, rdi; CompletionEvent
0x180016180  call    cs:__imp_DeleteTimerQueueTimer
0x180016186  mov     rdx, [rbx+658h]; Timer
0x18001618d  test    rdx, rdx
0x180016190  jz      short loc_1800161A2
0x180016192  mov     rcx, [rbx+660h]; TimerQueue
0x180016199  mov     r8, rdi; CompletionEvent
0x18001619c  call    cs:__imp_DeleteTimerQueueTimer
0x1800161a2  mov     rcx, [rbx+618h]; TimerQueue
0x1800161a9  test    rcx, rcx
0x1800161ac  jz      short loc_1800161B7
0x1800161ae  mov     rdx, rdi; CompletionEvent
0x1800161b1  call    cs:__imp_DeleteTimerQueueEx
0x1800161b7  mov     rcx, [rbx+610h]; hObject
0x1800161be  mov     [rbx+618h], rbp
0x1800161c5  test    rcx, rcx
0x1800161c8  jz      short loc_1800161D0
0x1800161ca  call    cs:__imp_CloseHandle
0x1800161d0  mov     rcx, cs:?g_hWlanDisconnected@@3PEAXEA; hObject
0x1800161d7  mov     [rbx+610h], rbp
0x1800161de  test    rcx, rcx
0x1800161e1  jz      short loc_1800161E9
0x1800161e3  call    cs:__imp_CloseHandle
0x1800161e9  mov     rcx, cs:?g_hWlanPowerSet@@3PEAXEA; hObject
0x1800161f0  mov     cs:?g_hWlanDisconnected@@3PEAXEA, rbp; void * g_hWlanDisconnected
0x1800161f7  test    rcx, rcx
0x1800161fa  jz      short loc_180016202
0x1800161fc  call    cs:__imp_CloseHandle
0x180016202  lea     rsi, [rbx+518h]
0x180016209  mov     cs:?g_hWlanPowerSet@@3PEAXEA, rbp; void * g_hWlanPowerSet
0x180016210  mov     rcx, rsi; lpCriticalSection
0x180016213  call    cs:__imp_EnterCriticalSection
0x180016219  lea     rdi, [rbx+540h]
0x180016220  mov     rcx, [rdi]; Block
0x180016223  cmp     rcx, rdi
0x180016226  jz      short loc_18001624D
0x180016228  cmp     [rcx+8], rdi
0x18001622c  jnz     short loc_180016246
0x18001622e  mov     rax, [rcx]
0x180016231  cmp     [rax+8], rcx
0x180016235  jnz     short loc_180016246
0x180016237  mov     [rdi], rax
0x18001623a  mov     [rax+8], rdi
0x18001623e  call    cs:__imp_free
0x180016244  jmp     short loc_180016220
0x180016246  mov     ecx, 3
0x18001624b  int     29h; Win8: RtlFailFast(ecx)
0x18001624d  mov     rcx, rsi; lpCriticalSection
0x180016250  call    cs:__imp_LeaveCriticalSection
0x180016256  mov     rcx, [rbx+5F8h]; hClientHandle
0x18001625d  test    rcx, rcx
0x180016260  jz      short loc_180016299
0x180016262  mov     [rsp+78h+pdwPrevNotifSource], rbp; pdwPrevNotifSource
0x180016267  lea     r9, ?s_WlanNotificationCallback@TetheringService@@CAXPEAU_L2_NOTIFICATION_DATA@@PEAX@Z; funcCallback
0x18001626e  mov     [rsp+78h+pReserved], rbp; pReserved
0x180016273  xor     r8d, r8d; bIgnoreDuplicate
0x180016276  xor     edx, edx; dwNotifSource
0x180016278  mov     [rsp+78h+pCallbackContext], rbp; pCallbackContext
0x18001627d  call    cs:__imp_WlanRegisterNotification
0x180016283  mov     rcx, [rbx+5F8h]; hClientHandle
0x18001628a  xor     edx, edx; pReserved
0x18001628c  call    cs:__imp_WlanCloseHandle
0x180016292  mov     [rbx+5F8h], rbp
0x180016299  mov     [rbx+760h], bpl
0x1800162a0  mov     rcx, cs:WPP_GLOBAL_Control
0x1800162a7  cmp     rcx, r15
0x1800162aa  jz      short loc_1800162C7
0x1800162ac  test    byte ptr [rcx+1Ch], 8
0x1800162b0  jz      short loc_1800162C7
0x1800162b2  mov     rcx, [rcx+10h]
0x1800162b6  lea     r8, WPP_ad96878468d9324e80184c9fc08cbc2e_Traceguids
0x1800162bd  mov     edx, 28h ; '('
0x1800162c2  call    WPP_SF_
0x1800162c7  add     rsp, 48h
0x1800162cb  pop     r15
0x1800162cd  pop     r12
0x1800162cf  pop     rdi
0x1800162d0  pop     rsi
0x1800162d1  pop     rbp
0x1800162d2  pop     rbx
0x1800162d3  retn
```
