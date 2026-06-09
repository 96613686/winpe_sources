# CDeviceEventHandler::s_ProcessDeviceEvents(void *)

- ea: `0x1800be890`
- end: `0x1800bee25`
- name: `?s_ProcessDeviceEvents@CDeviceEventHandler@@CAKPEAX@Z`
- size: `1429`
- prototype: `unsigned int __fastcall(void *)`
- caller_count: `0`
- callee_count: `25`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callees

- `0x18000d4b0`
- `0x18000d4c0`
- `0x18001df70`
- `0x180086dac`
- `0x1800bb328`
- `0x1800be890`
- `0x1800bfb48`
- `0x1800c0614`
- `0x1800c0948`
- `0x1800c1520`
- `0x1800c1694`
- `0x1801d4cb8`
- `0x1801f1370`
- `0x18020ba48`
- `0x180225ccc`
- `0x180233280`
- `0x1802342fc`
- `0x180243d40`
- `0x18025c218`
- `0x18025c240`
- `0x18025c514`
- `0x1802dd760`
- `0x1802e2548`
- `0x1803713bc`
- `0x180571010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800be8dd`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800be8dd`
- `api-ms-win-core-processthreads-l1-1-0!GetThreadId` at `0x1800be8e6`
- `api-ms-win-core-processthreads-l1-1-0!GetThreadId` at `0x1800be8e6`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800be925`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800be9f5`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800bed1b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800be925`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800be9f5`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800bed1b`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800bea54`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800bea81`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800bea54`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800bea81`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x1800be9ac`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x1800be9ac`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1800be97f`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1800be998`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1800be97f`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1800be998`
- `USER32!GetAsyncKeyState` at `0x1800bec41`
- `USER32!GetAsyncKeyState` at `0x1800bec41`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800bed54`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800bed5f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800bed54`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800bed5f`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x1800beab5`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x1800beab5`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800bec18`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800bec18`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x1800bed86`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x1800bed86`
- `api-ms-win-shcore-registry-l1-1-0!SHGetValueW` at `0x1800bebca`
- `api-ms-win-shcore-registry-l1-1-0!SHGetValueW` at `0x1800bebca`
- `Windows.Storage!__imp_SHCLSIDFromString` at `0x1800bebf3`
- `Windows.Storage!__imp_SHCLSIDFromString` at `0x1800bebf3`

## string_xrefs

- `0x1800bebbc`: `Software\Microsoft\Windows\CurrentVersion\Explorer\AutoplayExtensions\ShellUI`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CDeviceEventHandler::s_ProcessDeviceEvents(void *a1, __int64 a2, int a3)
{
  HANDLE CurrentThread; // rax
  DWORD ThreadId; // r13d
  unsigned int v5; // ebx
  int v6; // r8d
  int v7; // esi
  DWORD TickCount; // ebx
  char *v9; // rdi
  DWORD v10; // ebx
  int RecommededAndRegisteredApps; // esi
  LSTATUS UI; // esi
  CAutoplayDeviceDataManager *v13; // rcx
  int v14; // eax
  LPVOID *v15; // rax
  SHORT AsyncKeyState; // ax
  __int64 v17; // rbx
  _QWORD *v18; // rcx
  __int64 v19; // rdx
  __int64 v20; // r9
  int v22; // [rsp+50h] [rbp-B0h] BYREF
  int v23; // [rsp+54h] [rbp-ACh]
  CAutoplayDeviceData *v24; // [rsp+58h] [rbp-A8h] BYREF
  int v25; // [rsp+60h] [rbp-A0h]
  unsigned __int16 *v26; // [rsp+68h] [rbp-98h] BYREF
  LPVOID pv; // [rsp+70h] [rbp-90h] BYREF
  DWORD pdwType; // [rsp+78h] [rbp-88h] BYREF
  DWORD pcbData[2]; // [rsp+80h] [rbp-80h] BYREF
  struct IAutoPlayUI *v30; // [rsp+88h] [rbp-78h] BYREF
  CLSID pclsid; // [rsp+90h] [rbp-70h] BYREF
  OLECHAR sz[40]; // [rsp+A0h] [rbp-60h] BYREF
  WCHAR pvData[264]; // [rsp+F0h] [rbp-10h] BYREF

  if ( (Microsoft_Windows_Shell_CoreEnableBits & 1) != 0 )
    McGenEventWrite_EtwEventWriteTransfer(
      (_DWORD)a1,
      (unsigned int)&ShellTask_AutoPlay_ProcessDevicesEventsThread_Start,
      a3,
      1,
      (__int64)&pclsid);
  CurrentThread = GetCurrentThread();
  ThreadId = GetThreadId(CurrentThread);
  CCritSecDelayInitBase::Enter(&CDeviceEventHandler::s_csAutoplayPrompt);
  v5 = CDeviceEventHandler::s_dwThreadIDQueueOwner;
  if ( !CDeviceEventHandler::s_dwThreadIDQueueOwner
    && CDeviceEventHandler::s_dpaDeviceInterfaceEvents
    && *(int *)CDeviceEventHandler::s_dpaDeviceInterfaceEvents > 0 )
  {
    v5 = ThreadId;
    CDeviceEventHandler::s_dwThreadIDQueueOwner = ThreadId;
  }
  LeaveCriticalSection(&CDeviceEventHandler::s_csAutoplayPrompt);
  if ( v5 == ThreadId )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 36, &WPP_6a67a0b5e4173297d889067deb12d96d_Traceguids, ThreadId);
    v25 = SHCoInitialize();
    if ( v25 >= 0 )
    {
      v7 = 1;
      v23 = 1;
      while ( 1 )
      {
        TickCount = GetTickCount();
        while ( (!CDeviceEventHandler::s_dpaDeviceInterfaceEvents
              || !*(_DWORD *)CDeviceEventHandler::s_dpaDeviceInterfaceEvents)
             && GetTickCount() - TickCount < 0xC8 )
          Sleep(0x19u);
        CCritSecDelayInitBase::Enter(&CDeviceEventHandler::s_csAutoplayPrompt);
        v9 = (char *)DPA_DeletePtr(CDeviceEventHandler::s_dpaDeviceInterfaceEvents, 0);
        if ( !v9 )
        {
          v7 = 0;
          v23 = 0;
          CDeviceEventHandler::s_dwThreadIDQueueOwner = 0;
          CDPA_Base<CDeviceEventInfo,CTContainer_PolicyNewMem>::Destroy(&CDeviceEventHandler::s_dpaDeviceInterfaceEvents);
        }
        LeaveCriticalSection(&CDeviceEventHandler::s_csAutoplayPrompt);
        if ( !v9 )
          goto LABEL_55;
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
          WPP_SF_SS(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            37,
            (unsigned int)&WPP_6a67a0b5e4173297d889067deb12d96d_Traceguids,
            *((_QWORD *)v9 + 6),
            *((_QWORD *)v9 + 3));
        v10 = 1;
        if ( CompareStringOrdinal(*((LPCWCH *)v9 + 6), -1, L"DeviceRemoval", -1, 1) == 2 )
        {
          CDeviceEventHandler::s_HandlePossibleDXPDeviceInterfaceRemoval(*((LPCWCH *)v9 + 3));
        }
        else if ( CompareStringOrdinal(*((LPCWCH *)v9 + 6), -1, L"DeviceArrival", -1, 1) == 2 )
        {
          pdwType = 1;
          v22 = 0;
          pcbData[0] = 0;
          pv = 0;
          v26 = 0;
          RecommededAndRegisteredApps = 0;
          if ( StringFromGUID2((const GUID *const)(v9 + 8), sz, 39) )
            RecommededAndRegisteredApps = _GetRecommededAndRegisteredApps(sz, &v26, (int *)pcbData);
          if ( RecommededAndRegisteredApps >= 0 )
          {
            ClearDeviceStage(*((const unsigned __int16 **)v9 + 3));
            goto LABEL_33;
          }
          UI = CDeviceEventHandler::s_ConditionallyLaunchDXP(
                 (const struct _GUID *)(v9 + 8),
                 *((const unsigned __int16 **)v9 + 3),
                 *((_DWORD *)v9 + 10),
                 (int *)&pdwType,
                 &v22,
                 (LPWSTR *)&pv);
          if ( UI < 0 )
            goto LABEL_51;
          v10 = pdwType;
LABEL_33:
          if ( v10 && !*((_DWORD *)v9 + 10) )
          {
            if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
              WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 38, &WPP_6a67a0b5e4173297d889067deb12d96d_Traceguids);
            CCritSecDelayInitBase::Enter(&g_csAutoplayDeviceDataManager);
            v24 = 0;
            v14 = CAutoplayDeviceDataManager::AddDeviceData(
                    v13,
                    *((const unsigned __int16 **)v9 + 3),
                    (const struct _GUID *)(v9 + 8),
                    &v24);
            UI = v14;
            if ( v14 >= 0 )
            {
              memset_0(pvData, 0, 0x208u);
              pdwType = 0;
              pcbData[0] = 520;
              UI = SHGetValueW(
                     HKEY_LOCAL_MACHINE,
                     L"Software\\Microsoft\\Windows\\CurrentVersion\\Explorer\\AutoplayExtensions\\ShellUI",
                     0,
                     &pdwType,
                     pvData,
                     pcbData);
              if ( UI >= 0 )
              {
                ATL::CComPtr<IClassFactory>::CComPtr<IClassFactory>(&v30);
                pclsid = 0;
                SHCLSIDFromString(pvData, &pclsid);
                v15 = (LPVOID *)ATL::CComPtrBase<IAutoPlayUI>::operator&(&v30);
                UI = CoCreateInstance(&pclsid, 0, 1u, &GUID_4d0bbc56_877f_463a_8252_8853f813470f, v15);
                if ( UI >= 0 )
                {
                  UI = CAutoplayDeviceData::SetUI(v24, v30);
                  if ( UI >= 0 )
                  {
                    AsyncKeyState = GetAsyncKeyState(16);
                    UI = (*(__int64 (__fastcall **)(struct IAutoPlayUI *, __int64 *, char *, _QWORD, int, int, _QWORD, unsigned __int16 *, LPVOID))(*(_QWORD *)v30 + 32LL))(
                           v30,
                           &g_AutoplayDeviceDataManager,
                           v9 + 8,
                           *((_QWORD *)v9 + 3),
                           (AsyncKeyState >> 31) & 0x21,
                           v22,
                           *((_QWORD *)v9 + 4),
                           v26,
                           pv);
                    if ( UI < 0 )
                      CAutoplayDeviceDataManager::RemoveUI(
                        (CAutoplayDeviceDataManager *)&g_AutoplayDeviceDataManager,
                        *((LPCWSTR *)v9 + 3));
                  }
                }
                ATL::CComPtr<IUICommandWithBackgroundColor>::~CComPtr<IUICommandWithBackgroundColor>(&v30);
              }
              goto LABEL_48;
            }
            if ( v14 == -2147024713 )
            {
              *(_QWORD *)pcbData = 0;
              UI = CAutoplayDeviceData::GetUI(v24, (struct IAutoPlayUI **)pcbData);
              if ( UI >= 0 )
              {
                v17 = *(_QWORD *)pcbData;
                (*(void (__fastcall **)(_QWORD, _QWORD))(**(_QWORD **)pcbData + 104LL))(
                  *(_QWORD *)pcbData,
                  *((_QWORD *)v9 + 3));
                (*(void (__fastcall **)(__int64))(*(_QWORD *)v17 + 16LL))(v17);
              }
LABEL_48:
              CAutoplayDeviceData::Release(v24);
            }
            LeaveCriticalSection(&g_csAutoplayDeviceDataManager);
            if ( UI < 0 )
            {
LABEL_51:
              if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
              {
                WPP_SF_d(
                  *((_QWORD *)WPP_GLOBAL_Control + 2),
                  39,
                  &WPP_6a67a0b5e4173297d889067deb12d96d_Traceguids,
                  (unsigned int)UI);
              }
            }
          }
          CoTaskMemFree(pv);
          CoTaskMemFree(v26);
        }
        CDeviceEventInfo::`scalar deleting destructor'((CDeviceEventInfo *)v9, 1u);
        v7 = v23;
LABEL_55:
        if ( !v7 )
        {
          if ( !v25 )
            CoUninitialize();
          break;
        }
      }
    }
    v18 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    {
      v19 = 40;
      v20 = ThreadId;
LABEL_65:
      WPP_SF_d(v18[2], v19, &WPP_6a67a0b5e4173297d889067deb12d96d_Traceguids, v20);
    }
  }
  else if ( v5 )
  {
    v18 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    {
      v19 = 41;
      v20 = v5;
      goto LABEL_65;
    }
  }
  if ( (Microsoft_Windows_Shell_CoreEnableBits & 1) != 0 )
    McGenEventWrite_EtwEventWriteTransfer(
      (unsigned int)&pclsid,
      (unsigned int)&ShellTask_AutoPlay_ProcessDevicesEventsThread_Stop,
      v6,
      1,
      (__int64)&pclsid);
  return 1;
}

```

## disassembly

```asm
0x1800be890  push    rbp
0x1800be892  push    rbx
0x1800be893  push    rsi
0x1800be894  push    rdi
0x1800be895  push    r13
0x1800be897  push    r15
0x1800be899  lea     rbp, [rsp-218h]
0x1800be8a1  sub     rsp, 318h
0x1800be8a8  mov     rax, cs:__security_cookie
0x1800be8af  xor     rax, rsp
0x1800be8b2  mov     [rbp+240h+var_40], rax
0x1800be8b9  test    byte ptr cs:Microsoft_Windows_Shell_CoreEnableBits, 1
0x1800be8c0  jz      short loc_1800BE8DD
0x1800be8c2  lea     rax, [rbp+240h+pclsid]
0x1800be8c6  mov     qword ptr [rsp+340h+bIgnoreCase], rax
0x1800be8cb  mov     r9d, 1
0x1800be8d1  lea     rdx, ShellTask_AutoPlay_ProcessDevicesEventsThread_Start
0x1800be8d8  call    McGenEventWrite_EtwEventWriteTransfer
0x1800be8dd  call    cs:__imp_GetCurrentThread
0x1800be8e3  mov     rcx, rax; Thread
0x1800be8e6  call    cs:__imp_GetThreadId
0x1800be8ec  mov     r13d, eax
0x1800be8ef  lea     rcx, ?s_csAutoplayPrompt@CDeviceEventHandler@@0VCCritSecDelayInitBase@@A; Parameter
0x1800be8f6  call    ?Enter@CCritSecDelayInitBase@@QEAAXXZ; CCritSecDelayInitBase::Enter(void)
0x1800be8fb  mov     ebx, cs:?s_dwThreadIDQueueOwner@CDeviceEventHandler@@0KA; ulong CDeviceEventHandler::s_dwThreadIDQueueOwner
0x1800be901  test    ebx, ebx
0x1800be903  jnz     short loc_1800BE91E
0x1800be905  mov     rax, cs:?s_dpaDeviceInterfaceEvents@CDeviceEventHandler@@0V?$CDPANewMem@VCDeviceEventInfo@@@@A; CDPANewMem<CDeviceEventInfo> CDeviceEventHandler::s_dpaDeviceInterfaceEvents
0x1800be90c  test    rax, rax
0x1800be90f  jz      short loc_1800BE91E
0x1800be911  cmp     [rax], ebx
0x1800be913  jle     short loc_1800BE91E
0x1800be915  mov     ebx, r13d
0x1800be918  mov     cs:?s_dwThreadIDQueueOwner@CDeviceEventHandler@@0KA, ebx; ulong CDeviceEventHandler::s_dwThreadIDQueueOwner
0x1800be91e  lea     rcx, ?s_csAutoplayPrompt@CDeviceEventHandler@@0VCCritSecDelayInitBase@@A; lpCriticalSection
0x1800be925  call    cs:__imp_LeaveCriticalSection
0x1800be92b  cmp     ebx, r13d
0x1800be92e  jnz     loc_1800BEDA8
0x1800be934  lea     r15, WPP_GLOBAL_Control
0x1800be93b  mov     rcx, cs:WPP_GLOBAL_Control
0x1800be942  cmp     rcx, r15
0x1800be945  jz      short loc_1800BE965
0x1800be947  test    byte ptr [rcx+1Ch], 8
0x1800be94b  jz      short loc_1800BE965
0x1800be94d  mov     edx, 24h ; '$'
0x1800be952  mov     r9d, r13d
0x1800be955  lea     r8, WPP_6a67a0b5e4173297d889067deb12d96d_Traceguids
0x1800be95c  mov     rcx, [rcx+10h]
0x1800be960  call    WPP_SF_d
0x1800be965  call    ?SHCoInitialize@@YAJXZ; SHCoInitialize(void)
0x1800be96a  mov     [rsp+340h+var_2E0], eax
0x1800be96e  test    eax, eax
0x1800be970  js      loc_1800BED8C
0x1800be976  mov     esi, 1
0x1800be97b  mov     [rsp+340h+var_2EC], esi
0x1800be97f  call    cs:__imp_GetTickCount
0x1800be985  mov     ebx, eax
0x1800be987  mov     rax, cs:?s_dpaDeviceInterfaceEvents@CDeviceEventHandler@@0V?$CDPANewMem@VCDeviceEventInfo@@@@A; CDPANewMem<CDeviceEventInfo> CDeviceEventHandler::s_dpaDeviceInterfaceEvents
0x1800be98e  test    rax, rax
0x1800be991  jz      short loc_1800BE998
0x1800be993  cmp     dword ptr [rax], 0
0x1800be996  jnz     short loc_1800BE9B4
0x1800be998  call    cs:__imp_GetTickCount
0x1800be99e  sub     eax, ebx
0x1800be9a0  cmp     eax, 0C8h
0x1800be9a5  jnb     short loc_1800BE9B4
0x1800be9a7  mov     ecx, 19h; dwMilliseconds
0x1800be9ac  call    cs:__imp_Sleep
0x1800be9b2  jmp     short loc_1800BE987
0x1800be9b4  lea     rcx, ?s_csAutoplayPrompt@CDeviceEventHandler@@0VCCritSecDelayInitBase@@A; Parameter
0x1800be9bb  call    ?Enter@CCritSecDelayInitBase@@QEAAXXZ; CCritSecDelayInitBase::Enter(void)
0x1800be9c0  xor     edx, edx; i
0x1800be9c2  mov     rcx, cs:?s_dpaDeviceInterfaceEvents@CDeviceEventHandler@@0V?$CDPANewMem@VCDeviceEventInfo@@@@A; hdpa
0x1800be9c9  call    DPA_DeletePtr
0x1800be9ce  mov     rdi, rax
0x1800be9d1  test    rax, rax
0x1800be9d4  jnz     short loc_1800BE9EE
0x1800be9d6  xor     esi, esi
0x1800be9d8  mov     [rsp+340h+var_2EC], esi
0x1800be9dc  mov     cs:?s_dwThreadIDQueueOwner@CDeviceEventHandler@@0KA, esi; ulong CDeviceEventHandler::s_dwThreadIDQueueOwner
0x1800be9e2  lea     rcx, ?s_dpaDeviceInterfaceEvents@CDeviceEventHandler@@0V?$CDPANewMem@VCDeviceEventInfo@@@@A; CDPANewMem<CDeviceEventInfo> CDeviceEventHandler::s_dpaDeviceInterfaceEvents
0x1800be9e9  call    ?Destroy@?$CDPA_Base@VCDeviceEventInfo@@VCTContainer_PolicyNewMem@@@@QEAAHXZ; CDPA_Base<CDeviceEventInfo,CTContainer_PolicyNewMem>::Destroy(void)
0x1800be9ee  lea     rcx, ?s_csAutoplayPrompt@CDeviceEventHandler@@0VCCritSecDelayInitBase@@A; lpCriticalSection
0x1800be9f5  call    cs:__imp_LeaveCriticalSection
0x1800be9fb  test    rdi, rdi
0x1800be9fe  jz      loc_1800BED78
0x1800bea04  mov     rcx, cs:WPP_GLOBAL_Control
0x1800bea0b  cmp     rcx, r15
0x1800bea0e  jz      short loc_1800BEA38
0x1800bea10  test    byte ptr [rcx+1Ch], 8
0x1800bea14  jz      short loc_1800BEA38
0x1800bea16  mov     edx, 25h ; '%'
0x1800bea1b  mov     rax, [rdi+18h]
0x1800bea1f  mov     qword ptr [rsp+340h+bIgnoreCase], rax
0x1800bea24  mov     r9, [rdi+30h]
0x1800bea28  lea     r8, WPP_6a67a0b5e4173297d889067deb12d96d_Traceguids
0x1800bea2f  mov     rcx, [rcx+10h]
0x1800bea33  call    WPP_SF_SS
0x1800bea38  mov     ebx, 1
0x1800bea3d  mov     [rsp+340h+bIgnoreCase], ebx; bIgnoreCase
0x1800bea41  or      esi, 0FFFFFFFFh
0x1800bea44  mov     r9d, esi; cchCount2
0x1800bea47  lea     r8, aDeviceremoval; "DeviceRemoval"
0x1800bea4e  mov     edx, esi; cchCount1
0x1800bea50  mov     rcx, [rdi+30h]; lpString1
0x1800bea54  call    cs:__imp_CompareStringOrdinal
0x1800bea5a  cmp     eax, 2
0x1800bea5d  jnz     short loc_1800BEA6D
0x1800bea5f  mov     rcx, [rdi+18h]; lpString2
0x1800bea63  call    ?s_HandlePossibleDXPDeviceInterfaceRemoval@CDeviceEventHandler@@CAJPEBG@Z; CDeviceEventHandler::s_HandlePossibleDXPDeviceInterfaceRemoval(ushort const *)
0x1800bea68  jmp     loc_1800BED6A
0x1800bea6d  mov     [rsp+340h+bIgnoreCase], ebx; bIgnoreCase
0x1800bea71  mov     r9d, esi; cchCount2
0x1800bea74  lea     r8, aDevicearrival; "DeviceArrival"
0x1800bea7b  mov     edx, esi; cchCount1
0x1800bea7d  mov     rcx, [rdi+30h]; lpString1
0x1800bea81  call    cs:__imp_CompareStringOrdinal
0x1800bea87  cmp     eax, 2
0x1800bea8a  jnz     loc_1800BED6A
0x1800bea90  mov     [rsp+340h+pdwType], ebx
0x1800bea94  xor     eax, eax
0x1800bea96  mov     [rsp+340h+var_2F0], eax
0x1800bea9a  mov     [rbp+240h+var_2C0], eax
0x1800bea9d  mov     [rsp+340h+pv], rax
0x1800beaa2  mov     [rsp+340h+var_2D8], rax
0x1800beaa7  mov     esi, eax
0x1800beaa9  lea     rcx, [rdi+8]; rguid
0x1800beaad  lea     r8d, [rax+27h]; cchMax
0x1800beab1  lea     rdx, [rbp+240h+sz]; lpsz
0x1800beab5  call    cs:__imp_StringFromGUID2
0x1800beabb  test    eax, eax
0x1800beabd  jz      short loc_1800BEAD3
0x1800beabf  lea     r8, [rbp+240h+var_2C0]; int *
0x1800beac3  lea     rdx, [rsp+340h+var_2D8]; unsigned __int16 **
0x1800beac8  lea     rcx, [rbp+240h+sz]; unsigned __int16 *
0x1800beacc  call    ?_GetRecommededAndRegisteredApps@@YAJPEBGPEAPEAGPEAH@Z; _GetRecommededAndRegisteredApps(ushort const *,ushort * *,int *)
0x1800bead1  mov     esi, eax
0x1800bead3  test    esi, esi
0x1800bead5  jns     short loc_1800BEB11
0x1800bead7  lea     rax, [rsp+340h+pv]
0x1800beadc  mov     [rsp+340h+pcbData], rax; ppwsz
0x1800beae1  lea     rax, [rsp+340h+var_2F0]
0x1800beae6  mov     qword ptr [rsp+340h+bIgnoreCase], rax; int *
0x1800beaeb  lea     r9, [rsp+340h+pdwType]; int *
0x1800beaf0  mov     r8d, [rdi+28h]; int
0x1800beaf4  mov     rdx, [rdi+18h]; unsigned __int16 *
0x1800beaf8  lea     rcx, [rdi+8]; struct _GUID *
0x1800beafc  call    ?s_ConditionallyLaunchDXP@CDeviceEventHandler@@CAJAEBU_GUID@@PEBGHPEAH2PEAPEAG@Z; CDeviceEventHandler::s_ConditionallyLaunchDXP(_GUID const &,ushort const *,int,int *,int *,ushort * *)
0x1800beb01  mov     esi, eax
0x1800beb03  test    eax, eax
0x1800beb05  js      loc_1800BED25
0x1800beb0b  mov     ebx, [rsp+340h+pdwType]
0x1800beb0f  jmp     short loc_1800BEB1A
0x1800beb11  mov     rcx, [rdi+18h]; unsigned __int16 *
0x1800beb15  call    ?ClearDeviceStage@@YAJPEBG@Z; ClearDeviceStage(ushort const *)
0x1800beb1a  test    ebx, ebx
0x1800beb1c  jz      loc_1800BED4F
0x1800beb22  cmp     dword ptr [rdi+28h], 0
0x1800beb26  jnz     loc_1800BED4F
0x1800beb2c  mov     rcx, cs:WPP_GLOBAL_Control
0x1800beb33  cmp     rcx, r15
0x1800beb36  jz      short loc_1800BEB53
0x1800beb38  test    byte ptr [rcx+1Ch], 8
0x1800beb3c  jz      short loc_1800BEB53
0x1800beb3e  mov     edx, 26h ; '&'
0x1800beb43  lea     r8, WPP_6a67a0b5e4173297d889067deb12d96d_Traceguids
0x1800beb4a  mov     rcx, [rcx+10h]
0x1800beb4e  call    WPP_SF_
0x1800beb53  lea     rcx, ?g_csAutoplayDeviceDataManager@@3VCCritSecDelayInitBase@@A; Parameter
0x1800beb5a  call    ?Enter@CCritSecDelayInitBase@@QEAAXXZ; CCritSecDelayInitBase::Enter(void)
0x1800beb5f  mov     [rsp+340h+var_2E8], 0
0x1800beb68  lea     r9, [rsp+340h+var_2E8]; struct CAutoplayDeviceData **
0x1800beb6d  lea     r8, [rdi+8]; struct _GUID *
0x1800beb71  mov     rdx, [rdi+18h]; unsigned __int16 *
0x1800beb75  call    ?AddDeviceData@CAutoplayDeviceDataManager@@QEAAJPEBGAEBU_GUID@@PEAPEAVCAutoplayDeviceData@@@Z; CAutoplayDeviceDataManager::AddDeviceData(ushort const *,_GUID const &,CAutoplayDeviceData * *)
0x1800beb7a  mov     esi, eax
0x1800beb7c  test    eax, eax
0x1800beb7e  js      loc_1800BECC1
0x1800beb84  mov     esi, 208h
0x1800beb89  mov     r8d, esi; Size
0x1800beb8c  xor     edx, edx; Val
0x1800beb8e  lea     rcx, [rbp+240h+pvData]; void *
0x1800beb92  call    memset_0
0x1800beb97  mov     [rsp+340h+pdwType], 0
0x1800beb9f  mov     [rbp+240h+var_2C0], esi
0x1800beba2  lea     rax, [rbp+240h+var_2C0]
0x1800beba6  mov     [rsp+340h+pcbData], rax; pcbData
0x1800bebab  lea     rax, [rbp+240h+pvData]
0x1800bebaf  mov     qword ptr [rsp+340h+bIgnoreCase], rax; pvData
0x1800bebb4  lea     r9, [rsp+340h+pdwType]; pdwType
0x1800bebb9  xor     r8d, r8d; pszValue
0x1800bebbc  lea     rdx, aSoftwareMicros_40; "Software\\Microsoft\\Windows\\CurrentVe"...
0x1800bebc3  mov     rcx, 0FFFFFFFF80000002h; hkey
0x1800bebca  call    cs:__imp_SHGetValueW
0x1800bebd0  mov     esi, eax
0x1800bebd2  test    eax, eax
0x1800bebd4  js      loc_1800BED0A
0x1800bebda  lea     rcx, [rbp+240h+var_2B8]; void *
0x1800bebde  call    ??0?$CComPtr@UIClassFactory@@@ATL@@QEAA@XZ; ATL::CComPtr<IClassFactory>::CComPtr<IClassFactory>(void)
0x1800bebe3  nop
0x1800bebe4  xorps   xmm0, xmm0
0x1800bebe7  movups  xmmword ptr [rbp+240h+pclsid.Data1], xmm0
0x1800bebeb  lea     rdx, [rbp+240h+pclsid]; pclsid
0x1800bebef  lea     rcx, [rbp+240h+pvData]; psz
0x1800bebf3  call    cs:__imp_SHCLSIDFromString
0x1800bebf9  lea     rcx, [rbp+240h+var_2B8]
0x1800bebfd  call    ??I?$CComPtrBase@UIAutoPlayUI@@@ATL@@QEAAPEAPEAUIAutoPlayUI@@XZ; ATL::CComPtrBase<IAutoPlayUI>::operator&(void)
0x1800bec02  mov     qword ptr [rsp+340h+bIgnoreCase], rax; ppv
0x1800bec07  lea     r9, _GUID_4d0bbc56_877f_463a_8252_8853f813470f; riid
0x1800bec0e  xor     edx, edx; pUnkOuter
0x1800bec10  lea     r8d, [rdx+1]; dwClsContext
0x1800bec14  lea     rcx, [rbp+240h+pclsid]; rclsid
0x1800bec18  call    cs:__imp_CoCreateInstance
0x1800bec1e  mov     esi, eax
0x1800bec20  test    eax, eax
0x1800bec22  js      loc_1800BECB6
0x1800bec28  mov     rdx, [rbp+240h+var_2B8]; struct IAutoPlayUI *
0x1800bec2c  mov     rcx, [rsp+340h+var_2E8]; this
0x1800bec31  call    ?SetUI@CAutoplayDeviceData@@QEAAJPEAUIAutoPlayUI@@@Z; CAutoplayDeviceData::SetUI(IAutoPlayUI *)
0x1800bec36  mov     esi, eax
0x1800bec38  test    eax, eax
0x1800bec3a  js      short loc_1800BECB6
0x1800bec3c  mov     ecx, 10h; vKey
0x1800bec41  call    cs:__imp_GetAsyncKeyState
0x1800bec47  mov     rcx, [rbp+240h+var_2B8]
0x1800bec4b  mov     r8, [rsp+340h+pv]
0x1800bec50  mov     rdx, [rcx]
0x1800bec53  movsx   r9d, ax
0x1800bec57  sar     r9d, 1Fh
0x1800bec5b  and     r9d, 21h
0x1800bec5f  mov     r10, [rdx+20h]
0x1800bec63  mov     [rsp+340h+var_300], r8
0x1800bec68  mov     rax, [rsp+340h+var_2D8]
0x1800bec6d  mov     [rsp+340h+var_308], rax
0x1800bec72  mov     rax, [rdi+20h]
0x1800bec76  mov     [rsp+340h+var_310], rax
0x1800bec7b  mov     eax, [rsp+340h+var_2F0]
0x1800bec7f  mov     dword ptr [rsp+340h+pcbData], eax
0x1800bec83  mov     [rsp+340h+bIgnoreCase], r9d
0x1800bec88  mov     r9, [rdi+18h]
0x1800bec8c  lea     r8, [rdi+8]
0x1800bec90  lea     rdx, ?g_AutoplayDeviceDataManager@@3VCAutoplayDeviceDataManager@@A; CAutoplayDeviceDataManager g_AutoplayDeviceDataManager
0x1800bec97  mov     rax, r10
0x1800bec9a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bec9f  mov     esi, eax
0x1800beca1  test    eax, eax
0x1800beca3  jns     short loc_1800BECB6
0x1800beca5  mov     rdx, [rdi+18h]; lpString2
0x1800beca9  lea     rcx, ?g_AutoplayDeviceDataManager@@3VCAutoplayDeviceDataManager@@A; this
0x1800becb0  call    ?RemoveUI@CAutoplayDeviceDataManager@@UEAAJPEBG@Z; CAutoplayDeviceDataManager::RemoveUI(ushort const *)
0x1800becb5  nop
0x1800becb6  lea     rcx, [rbp+240h+var_2B8]; void *
0x1800becba  call    ??1?$CComPtr@UIUICommandWithBackgroundColor@@@ATL@@QEAA@XZ; ATL::CComPtr<IUICommandWithBackgroundColor>::~CComPtr<IUICommandWithBackgroundColor>(void)
0x1800becbf  jmp     short loc_1800BED0A
0x1800becc1  cmp     eax, 800700B7h
0x1800becc6  jnz     short loc_1800BED14
0x1800becc8  mov     qword ptr [rbp+240h+var_2C0], 0
0x1800becd0  lea     rdx, [rbp+240h+var_2C0]; struct IAutoPlayUI **
0x1800becd4  mov     rcx, [rsp+340h+var_2E8]; this
0x1800becd9  call    ?GetUI@CAutoplayDeviceData@@QEAAJPEAPEAUIAutoPlayUI@@@Z; CAutoplayDeviceData::GetUI(IAutoPlayUI * *)
0x1800becde  mov     esi, eax
0x1800bece0  test    eax, eax
0x1800bece2  js      short loc_1800BED0A
0x1800bece4  mov     rbx, qword ptr [rbp+240h+var_2C0]
0x1800bece8  mov     rax, [rbx]
0x1800beceb  mov     rdx, [rdi+18h]
0x1800becef  mov     rcx, rbx
0x1800becf2  mov     rax, [rax+68h]
0x1800becf6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800becfb  mov     rax, [rbx]
0x1800becfe  mov     rcx, rbx
0x1800bed01  mov     rax, [rax+10h]
0x1800bed05  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bed0a  mov     rcx, [rsp+340h+var_2E8]; this
0x1800bed0f  call    ?Release@CAutoplayDeviceData@@QEAAKXZ; CAutoplayDeviceData::Release(void)
0x1800bed14  lea     rcx, ?g_csAutoplayDeviceDataManager@@3VCCritSecDelayInitBase@@A; lpCriticalSection
0x1800bed1b  call    cs:__imp_LeaveCriticalSection
0x1800bed21  test    esi, esi
0x1800bed23  jns     short loc_1800BED4F
0x1800bed25  mov     rcx, cs:WPP_GLOBAL_Control
0x1800bed2c  cmp     rcx, r15
0x1800bed2f  jz      short loc_1800BED4F
0x1800bed31  test    byte ptr [rcx+1Ch], 8
0x1800bed35  jz      short loc_1800BED4F
0x1800bed37  mov     edx, 27h ; '''
0x1800bed3c  mov     r9d, esi
0x1800bed3f  lea     r8, WPP_6a67a0b5e4173297d889067deb12d96d_Traceguids
0x1800bed46  mov     rcx, [rcx+10h]
0x1800bed4a  call    WPP_SF_d
0x1800bed4f  mov     rcx, [rsp+340h+pv]; pv
0x1800bed54  call    cs:__imp_CoTaskMemFree
0x1800bed5a  mov     rcx, [rsp+340h+var_2D8]; pv
0x1800bed5f  call    cs:__imp_CoTaskMemFree
0x1800bed65  mov     ebx, 1
0x1800bed6a  mov     edx, ebx; unsigned int
0x1800bed6c  mov     rcx, rdi; this
0x1800bed6f  call    ??_GCDeviceEventInfo@@UEAAPEAXI@Z; CDeviceEventInfo::`scalar deleting destructor'(uint)
0x1800bed74  mov     esi, [rsp+340h+var_2EC]
0x1800bed78  test    esi, esi
0x1800bed7a  jnz     loc_1800BE97F
  ... truncated ...
```
