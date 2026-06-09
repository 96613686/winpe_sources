# CDeviceEventHandler::s_ProcessDeviceEvents(void *)

- ea: `0x1800ef9b0`
- end: `0x1800effb6`
- name: `?s_ProcessDeviceEvents@CDeviceEventHandler@@CAKPEAX@Z`
- size: `1542`
- prototype: `unsigned int __fastcall(void *)`
- caller_count: `0`
- callee_count: `25`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callees

- `0x18000d220`
- `0x18000d240`
- `0x180016364`
- `0x18001a2bc`
- `0x1800234e0`
- `0x180055afc`
- `0x1800ef9b0`
- `0x1800effbc`
- `0x1800f0320`
- `0x180196df0`
- `0x18019964c`
- `0x1801ebefc`
- `0x180208c48`
- `0x180222d2c`
- `0x18023c57c`
- `0x180249490`
- `0x18024a53c`
- `0x18025a1a0`
- `0x180273e00`
- `0x180273e30`
- `0x18027412c`
- `0x1802fbd20`
- `0x180300e38`
- `0x1803961b0`
- `0x1805b2010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800ef9fd`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800ef9fd`
- `api-ms-win-core-processthreads-l1-1-0!GetThreadId` at `0x1800efa0c`
- `api-ms-win-core-processthreads-l1-1-0!GetThreadId` at `0x1800efa0c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800efa51`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800efb39`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800efe93`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800efa51`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800efb39`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800efe93`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800efb9e`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800efbd1`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800efb9e`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800efbd1`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x1800efaea`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x1800efaea`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1800efab1`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1800efad0`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1800efab1`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1800efad0`
- `USER32!GetAsyncKeyState` at `0x1800efdb3`
- `USER32!GetAsyncKeyState` at `0x1800efdb3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800efed2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800efee3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800efed2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800efee3`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800efd80`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800efd80`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x1800eff10`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x1800eff10`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x1800efc0b`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x1800efc0b`
- `api-ms-win-shcore-registry-l1-1-0!SHGetValueW` at `0x1800efd26`
- `api-ms-win-shcore-registry-l1-1-0!SHGetValueW` at `0x1800efd26`
- `Windows.Storage!__imp_SHCLSIDFromString` at `0x1800efd55`
- `Windows.Storage!__imp_SHCLSIDFromString` at `0x1800efd55`

## string_xrefs

- `0x1800efd18`: `Software\Microsoft\Windows\CurrentVersion\Explorer\AutoplayExtensions\ShellUI`

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
0x1800ef9b0  push    rbp
0x1800ef9b2  push    rbx
0x1800ef9b3  push    rsi
0x1800ef9b4  push    rdi
0x1800ef9b5  push    r13
0x1800ef9b7  push    r15
0x1800ef9b9  lea     rbp, [rsp-218h]
0x1800ef9c1  sub     rsp, 318h
0x1800ef9c8  mov     rax, cs:__security_cookie
0x1800ef9cf  xor     rax, rsp
0x1800ef9d2  mov     [rbp+240h+var_40], rax
0x1800ef9d9  test    byte ptr cs:Microsoft_Windows_Shell_CoreEnableBits, 1
0x1800ef9e0  jz      short loc_1800EF9FD
0x1800ef9e2  lea     rax, [rbp+240h+pclsid]
0x1800ef9e6  mov     qword ptr [rsp+340h+bIgnoreCase], rax
0x1800ef9eb  mov     r9d, 1
0x1800ef9f1  lea     rdx, ShellTask_AutoPlay_ProcessDevicesEventsThread_Start
0x1800ef9f8  call    McGenEventWrite_EtwEventWriteTransfer
0x1800ef9fd  call    cs:__imp_GetCurrentThread
0x1800efa04  nop     dword ptr [rax+rax+00h]
0x1800efa09  mov     rcx, rax; Thread
0x1800efa0c  call    cs:__imp_GetThreadId
0x1800efa13  nop     dword ptr [rax+rax+00h]
0x1800efa18  mov     r13d, eax
0x1800efa1b  lea     rcx, ?s_csAutoplayPrompt@CDeviceEventHandler@@0VCCritSecDelayInitBase@@A; Parameter
0x1800efa22  call    ?Enter@CCritSecDelayInitBase@@QEAAXXZ; CCritSecDelayInitBase::Enter(void)
0x1800efa27  mov     ebx, cs:?s_dwThreadIDQueueOwner@CDeviceEventHandler@@0KA; ulong CDeviceEventHandler::s_dwThreadIDQueueOwner
0x1800efa2d  test    ebx, ebx
0x1800efa2f  jnz     short loc_1800EFA4A
0x1800efa31  mov     rax, cs:?s_dpaDeviceInterfaceEvents@CDeviceEventHandler@@0V?$CDPANewMem@VCDeviceEventInfo@@@@A; CDPANewMem<CDeviceEventInfo> CDeviceEventHandler::s_dpaDeviceInterfaceEvents
0x1800efa38  test    rax, rax
0x1800efa3b  jz      short loc_1800EFA4A
0x1800efa3d  cmp     [rax], ebx
0x1800efa3f  jle     short loc_1800EFA4A
0x1800efa41  mov     ebx, r13d
0x1800efa44  mov     cs:?s_dwThreadIDQueueOwner@CDeviceEventHandler@@0KA, ebx; ulong CDeviceEventHandler::s_dwThreadIDQueueOwner
0x1800efa4a  lea     rcx, ?s_csAutoplayPrompt@CDeviceEventHandler@@0VCCritSecDelayInitBase@@A; lpCriticalSection
0x1800efa51  call    cs:__imp_LeaveCriticalSection
0x1800efa58  nop     dword ptr [rax+rax+00h]
0x1800efa5d  cmp     ebx, r13d
0x1800efa60  jnz     loc_1800EFF38
0x1800efa66  lea     r15, WPP_GLOBAL_Control
0x1800efa6d  mov     rcx, cs:WPP_GLOBAL_Control
0x1800efa74  cmp     rcx, r15
0x1800efa77  jz      short loc_1800EFA97
0x1800efa79  test    byte ptr [rcx+1Ch], 8
0x1800efa7d  jz      short loc_1800EFA97
0x1800efa7f  mov     edx, 24h ; '$'
0x1800efa84  mov     r9d, r13d
0x1800efa87  lea     r8, WPP_6a67a0b5e4173297d889067deb12d96d_Traceguids
0x1800efa8e  mov     rcx, [rcx+10h]
0x1800efa92  call    WPP_SF_d
0x1800efa97  call    ?SHCoInitialize@@YAJXZ; SHCoInitialize(void)
0x1800efa9c  mov     [rsp+340h+var_2E0], eax
0x1800efaa0  test    eax, eax
0x1800efaa2  js      loc_1800EFF1C
0x1800efaa8  mov     esi, 1
0x1800efaad  mov     [rsp+340h+var_2EC], esi
0x1800efab1  call    cs:__imp_GetTickCount
0x1800efab8  nop     dword ptr [rax+rax+00h]
0x1800efabd  mov     ebx, eax
0x1800efabf  mov     rax, cs:?s_dpaDeviceInterfaceEvents@CDeviceEventHandler@@0V?$CDPANewMem@VCDeviceEventInfo@@@@A; CDPANewMem<CDeviceEventInfo> CDeviceEventHandler::s_dpaDeviceInterfaceEvents
0x1800efac6  test    rax, rax
0x1800efac9  jz      short loc_1800EFAD0
0x1800efacb  cmp     dword ptr [rax], 0
0x1800eface  jnz     short loc_1800EFAF8
0x1800efad0  call    cs:__imp_GetTickCount
0x1800efad7  nop     dword ptr [rax+rax+00h]
0x1800efadc  sub     eax, ebx
0x1800efade  cmp     eax, 0C8h
0x1800efae3  jnb     short loc_1800EFAF8
0x1800efae5  mov     ecx, 19h; dwMilliseconds
0x1800efaea  call    cs:__imp_Sleep
0x1800efaf1  nop     dword ptr [rax+rax+00h]
0x1800efaf6  jmp     short loc_1800EFABF
0x1800efaf8  lea     rcx, ?s_csAutoplayPrompt@CDeviceEventHandler@@0VCCritSecDelayInitBase@@A; Parameter
0x1800efaff  call    ?Enter@CCritSecDelayInitBase@@QEAAXXZ; CCritSecDelayInitBase::Enter(void)
0x1800efb04  xor     edx, edx; i
0x1800efb06  mov     rcx, cs:?s_dpaDeviceInterfaceEvents@CDeviceEventHandler@@0V?$CDPANewMem@VCDeviceEventInfo@@@@A; hdpa
0x1800efb0d  call    DPA_DeletePtr
0x1800efb12  mov     rdi, rax
0x1800efb15  test    rax, rax
0x1800efb18  jnz     short loc_1800EFB32
0x1800efb1a  xor     esi, esi
0x1800efb1c  mov     [rsp+340h+var_2EC], esi
0x1800efb20  mov     cs:?s_dwThreadIDQueueOwner@CDeviceEventHandler@@0KA, esi; ulong CDeviceEventHandler::s_dwThreadIDQueueOwner
0x1800efb26  lea     rcx, ?s_dpaDeviceInterfaceEvents@CDeviceEventHandler@@0V?$CDPANewMem@VCDeviceEventInfo@@@@A; CDPANewMem<CDeviceEventInfo> CDeviceEventHandler::s_dpaDeviceInterfaceEvents
0x1800efb2d  call    ?Destroy@?$CDPA_Base@VCDeviceEventInfo@@VCTContainer_PolicyNewMem@@@@QEAAHXZ; CDPA_Base<CDeviceEventInfo,CTContainer_PolicyNewMem>::Destroy(void)
0x1800efb32  lea     rcx, ?s_csAutoplayPrompt@CDeviceEventHandler@@0VCCritSecDelayInitBase@@A; lpCriticalSection
0x1800efb39  call    cs:__imp_LeaveCriticalSection
0x1800efb40  nop     dword ptr [rax+rax+00h]
0x1800efb45  test    rdi, rdi
0x1800efb48  jz      loc_1800EFF02
0x1800efb4e  mov     rcx, cs:WPP_GLOBAL_Control
0x1800efb55  cmp     rcx, r15
0x1800efb58  jz      short loc_1800EFB82
0x1800efb5a  test    byte ptr [rcx+1Ch], 8
0x1800efb5e  jz      short loc_1800EFB82
0x1800efb60  mov     edx, 25h ; '%'
0x1800efb65  mov     rax, [rdi+18h]
0x1800efb69  mov     qword ptr [rsp+340h+bIgnoreCase], rax
0x1800efb6e  mov     r9, [rdi+30h]
0x1800efb72  lea     r8, WPP_6a67a0b5e4173297d889067deb12d96d_Traceguids
0x1800efb79  mov     rcx, [rcx+10h]
0x1800efb7d  call    WPP_SF_SS
0x1800efb82  mov     ebx, 1
0x1800efb87  mov     [rsp+340h+bIgnoreCase], ebx; bIgnoreCase
0x1800efb8b  or      esi, 0FFFFFFFFh
0x1800efb8e  mov     r9d, esi; cchCount2
0x1800efb91  lea     r8, aDeviceremoval; "DeviceRemoval"
0x1800efb98  mov     edx, esi; cchCount1
0x1800efb9a  mov     rcx, [rdi+30h]; lpString1
0x1800efb9e  call    cs:__imp_CompareStringOrdinal
0x1800efba5  nop     dword ptr [rax+rax+00h]
0x1800efbaa  cmp     eax, 2
0x1800efbad  jnz     short loc_1800EFBBD
0x1800efbaf  mov     rcx, [rdi+18h]; lpString2
0x1800efbb3  call    ?s_HandlePossibleDXPDeviceInterfaceRemoval@CDeviceEventHandler@@CAJPEBG@Z; CDeviceEventHandler::s_HandlePossibleDXPDeviceInterfaceRemoval(ushort const *)
0x1800efbb8  jmp     loc_1800EFEF4
0x1800efbbd  mov     [rsp+340h+bIgnoreCase], ebx; bIgnoreCase
0x1800efbc1  mov     r9d, esi; cchCount2
0x1800efbc4  lea     r8, aDevicearrival; "DeviceArrival"
0x1800efbcb  mov     edx, esi; cchCount1
0x1800efbcd  mov     rcx, [rdi+30h]; lpString1
0x1800efbd1  call    cs:__imp_CompareStringOrdinal
0x1800efbd8  nop     dword ptr [rax+rax+00h]
0x1800efbdd  cmp     eax, 2
0x1800efbe0  jnz     loc_1800EFEF4
0x1800efbe6  mov     [rsp+340h+pdwType], ebx
0x1800efbea  xor     eax, eax
0x1800efbec  mov     [rsp+340h+var_2F0], eax
0x1800efbf0  mov     [rbp+240h+var_2C0], eax
0x1800efbf3  mov     [rsp+340h+pv], rax
0x1800efbf8  mov     [rsp+340h+var_2D8], rax
0x1800efbfd  mov     esi, eax
0x1800efbff  lea     rcx, [rdi+8]; rguid
0x1800efc03  lea     r8d, [rax+27h]; cchMax
0x1800efc07  lea     rdx, [rbp+240h+sz]; lpsz
0x1800efc0b  call    cs:__imp_StringFromGUID2
0x1800efc12  nop     dword ptr [rax+rax+00h]
0x1800efc17  test    eax, eax
0x1800efc19  jz      short loc_1800EFC2F
0x1800efc1b  lea     r8, [rbp+240h+var_2C0]; int *
0x1800efc1f  lea     rdx, [rsp+340h+var_2D8]; unsigned __int16 **
0x1800efc24  lea     rcx, [rbp+240h+sz]; unsigned __int16 *
0x1800efc28  call    ?_GetRecommededAndRegisteredApps@@YAJPEBGPEAPEAGPEAH@Z; _GetRecommededAndRegisteredApps(ushort const *,ushort * *,int *)
0x1800efc2d  mov     esi, eax
0x1800efc2f  test    esi, esi
0x1800efc31  jns     short loc_1800EFC6D
0x1800efc33  lea     rax, [rsp+340h+pv]
0x1800efc38  mov     [rsp+340h+pcbData], rax; ppwsz
0x1800efc3d  lea     rax, [rsp+340h+var_2F0]
0x1800efc42  mov     qword ptr [rsp+340h+bIgnoreCase], rax; int *
0x1800efc47  lea     r9, [rsp+340h+pdwType]; int *
0x1800efc4c  mov     r8d, [rdi+28h]; int
0x1800efc50  mov     rdx, [rdi+18h]; unsigned __int16 *
0x1800efc54  lea     rcx, [rdi+8]; struct _GUID *
0x1800efc58  call    ?s_ConditionallyLaunchDXP@CDeviceEventHandler@@CAJAEBU_GUID@@PEBGHPEAH2PEAPEAG@Z; CDeviceEventHandler::s_ConditionallyLaunchDXP(_GUID const &,ushort const *,int,int *,int *,ushort * *)
0x1800efc5d  mov     esi, eax
0x1800efc5f  test    eax, eax
0x1800efc61  js      loc_1800EFEA3
0x1800efc67  mov     ebx, [rsp+340h+pdwType]
0x1800efc6b  jmp     short loc_1800EFC76
0x1800efc6d  mov     rcx, [rdi+18h]; unsigned __int16 *
0x1800efc71  call    ?ClearDeviceStage@@YAJPEBG@Z; ClearDeviceStage(ushort const *)
0x1800efc76  test    ebx, ebx
0x1800efc78  jz      loc_1800EFECD
0x1800efc7e  cmp     dword ptr [rdi+28h], 0
0x1800efc82  jnz     loc_1800EFECD
0x1800efc88  mov     rcx, cs:WPP_GLOBAL_Control
0x1800efc8f  cmp     rcx, r15
0x1800efc92  jz      short loc_1800EFCAF
0x1800efc94  test    byte ptr [rcx+1Ch], 8
0x1800efc98  jz      short loc_1800EFCAF
0x1800efc9a  mov     edx, 26h ; '&'
0x1800efc9f  lea     r8, WPP_6a67a0b5e4173297d889067deb12d96d_Traceguids
0x1800efca6  mov     rcx, [rcx+10h]
0x1800efcaa  call    WPP_SF_
0x1800efcaf  lea     rcx, ?g_csAutoplayDeviceDataManager@@3VCCritSecDelayInitBase@@A; Parameter
0x1800efcb6  call    ?Enter@CCritSecDelayInitBase@@QEAAXXZ; CCritSecDelayInitBase::Enter(void)
0x1800efcbb  mov     [rsp+340h+var_2E8], 0
0x1800efcc4  lea     r9, [rsp+340h+var_2E8]; struct CAutoplayDeviceData **
0x1800efcc9  lea     r8, [rdi+8]; struct _GUID *
0x1800efccd  mov     rdx, [rdi+18h]; unsigned __int16 *
0x1800efcd1  call    ?AddDeviceData@CAutoplayDeviceDataManager@@QEAAJPEBGAEBU_GUID@@PEAPEAVCAutoplayDeviceData@@@Z; CAutoplayDeviceDataManager::AddDeviceData(ushort const *,_GUID const &,CAutoplayDeviceData * *)
0x1800efcd6  mov     esi, eax
0x1800efcd8  test    eax, eax
0x1800efcda  js      loc_1800EFE39
0x1800efce0  mov     esi, 208h
0x1800efce5  mov     r8d, esi; Size
0x1800efce8  xor     edx, edx; Val
0x1800efcea  lea     rcx, [rbp+240h+pvData]; void *
0x1800efcee  call    memset_0
0x1800efcf3  mov     [rsp+340h+pdwType], 0
0x1800efcfb  mov     [rbp+240h+var_2C0], esi
0x1800efcfe  lea     rax, [rbp+240h+var_2C0]
0x1800efd02  mov     [rsp+340h+pcbData], rax; pcbData
0x1800efd07  lea     rax, [rbp+240h+pvData]
0x1800efd0b  mov     qword ptr [rsp+340h+bIgnoreCase], rax; pvData
0x1800efd10  lea     r9, [rsp+340h+pdwType]; pdwType
0x1800efd15  xor     r8d, r8d; pszValue
0x1800efd18  lea     rdx, pszSubKey; "Software\\Microsoft\\Windows\\CurrentVe"...
0x1800efd1f  mov     rcx, 0FFFFFFFF80000002h; hkey
0x1800efd26  call    cs:__imp_SHGetValueW
0x1800efd2d  nop     dword ptr [rax+rax+00h]
0x1800efd32  mov     esi, eax
0x1800efd34  test    eax, eax
0x1800efd36  js      loc_1800EFE82
0x1800efd3c  lea     rcx, [rbp+240h+var_2B8]; void *
0x1800efd40  call    ??0?$CComPtr@UIClassFactory@@@ATL@@QEAA@XZ; ATL::CComPtr<IClassFactory>::CComPtr<IClassFactory>(void)
0x1800efd45  nop
0x1800efd46  xorps   xmm0, xmm0
0x1800efd49  movups  xmmword ptr [rbp+240h+pclsid.Data1], xmm0
0x1800efd4d  lea     rdx, [rbp+240h+pclsid]; pclsid
0x1800efd51  lea     rcx, [rbp+240h+pvData]; psz
0x1800efd55  call    cs:__imp_SHCLSIDFromString
0x1800efd5c  nop     dword ptr [rax+rax+00h]
0x1800efd61  lea     rcx, [rbp+240h+var_2B8]
0x1800efd65  call    ??I?$CComPtrBase@UIAutoPlayUI@@@ATL@@QEAAPEAPEAUIAutoPlayUI@@XZ; ATL::CComPtrBase<IAutoPlayUI>::operator&(void)
0x1800efd6a  mov     qword ptr [rsp+340h+bIgnoreCase], rax; ppv
0x1800efd6f  lea     r9, _GUID_4d0bbc56_877f_463a_8252_8853f813470f; riid
0x1800efd76  xor     edx, edx; pUnkOuter
0x1800efd78  lea     r8d, [rdx+1]; dwClsContext
0x1800efd7c  lea     rcx, [rbp+240h+pclsid]; rclsid
0x1800efd80  call    cs:__imp_CoCreateInstance
0x1800efd87  nop     dword ptr [rax+rax+00h]
0x1800efd8c  mov     esi, eax
0x1800efd8e  test    eax, eax
0x1800efd90  js      loc_1800EFE2E
0x1800efd96  mov     rdx, [rbp+240h+var_2B8]; struct IAutoPlayUI *
0x1800efd9a  mov     rcx, [rsp+340h+var_2E8]; this
0x1800efd9f  call    ?SetUI@CAutoplayDeviceData@@QEAAJPEAUIAutoPlayUI@@@Z; CAutoplayDeviceData::SetUI(IAutoPlayUI *)
0x1800efda4  mov     esi, eax
0x1800efda6  test    eax, eax
0x1800efda8  js      loc_1800EFE2E
0x1800efdae  mov     ecx, 10h; vKey
0x1800efdb3  call    cs:__imp_GetAsyncKeyState
0x1800efdba  nop     dword ptr [rax+rax+00h]
0x1800efdbf  mov     rcx, [rbp+240h+var_2B8]
0x1800efdc3  mov     r8, [rsp+340h+pv]
0x1800efdc8  mov     rdx, [rcx]
0x1800efdcb  movsx   r9d, ax
0x1800efdcf  sar     r9d, 1Fh
0x1800efdd3  and     r9d, 21h
0x1800efdd7  mov     r10, [rdx+20h]
0x1800efddb  mov     [rsp+340h+var_300], r8
0x1800efde0  mov     rax, [rsp+340h+var_2D8]
0x1800efde5  mov     [rsp+340h+var_308], rax
0x1800efdea  mov     rax, [rdi+20h]
0x1800efdee  mov     [rsp+340h+var_310], rax
0x1800efdf3  mov     eax, [rsp+340h+var_2F0]
0x1800efdf7  mov     dword ptr [rsp+340h+pcbData], eax
0x1800efdfb  mov     [rsp+340h+bIgnoreCase], r9d
0x1800efe00  mov     r9, [rdi+18h]
0x1800efe04  lea     r8, [rdi+8]
0x1800efe08  lea     rdx, ?g_AutoplayDeviceDataManager@@3VCAutoplayDeviceDataManager@@A; CAutoplayDeviceDataManager g_AutoplayDeviceDataManager
0x1800efe0f  mov     rax, r10
0x1800efe12  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800efe17  mov     esi, eax
0x1800efe19  test    eax, eax
0x1800efe1b  jns     short loc_1800EFE2E
0x1800efe1d  mov     rdx, [rdi+18h]; lpString2
0x1800efe21  lea     rcx, ?g_AutoplayDeviceDataManager@@3VCAutoplayDeviceDataManager@@A; this
0x1800efe28  call    ?RemoveUI@CAutoplayDeviceDataManager@@UEAAJPEBG@Z; CAutoplayDeviceDataManager::RemoveUI(ushort const *)
0x1800efe2d  nop
0x1800efe2e  lea     rcx, [rbp+240h+var_2B8]; void *
0x1800efe32  call    ??1?$CComPtr@UIUICommandWithBackgroundColor@@@ATL@@QEAA@XZ; ATL::CComPtr<IUICommandWithBackgroundColor>::~CComPtr<IUICommandWithBackgroundColor>(void)
0x1800efe37  jmp     short loc_1800EFE82
0x1800efe39  cmp     eax, 800700B7h
0x1800efe3e  jnz     short loc_1800EFE8C
0x1800efe40  mov     qword ptr [rbp+240h+var_2C0], 0
0x1800efe48  lea     rdx, [rbp+240h+var_2C0]; struct IAutoPlayUI **
0x1800efe4c  mov     rcx, [rsp+340h+var_2E8]; this
0x1800efe51  call    ?GetUI@CAutoplayDeviceData@@QEAAJPEAPEAUIAutoPlayUI@@@Z; CAutoplayDeviceData::GetUI(IAutoPlayUI * *)
0x1800efe56  mov     esi, eax
0x1800efe58  test    eax, eax
0x1800efe5a  js      short loc_1800EFE82
0x1800efe5c  mov     rbx, qword ptr [rbp+240h+var_2C0]
0x1800efe60  mov     rax, [rbx]
0x1800efe63  mov     rdx, [rdi+18h]
0x1800efe67  mov     rcx, rbx
0x1800efe6a  mov     rax, [rax+68h]
0x1800efe6e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800efe73  mov     rax, [rbx]
0x1800efe76  mov     rcx, rbx
0x1800efe79  mov     rax, [rax+10h]
0x1800efe7d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800efe82  mov     rcx, [rsp+340h+var_2E8]; this
0x1800efe87  call    ?Release@CAutoplayDeviceData@@QEAAKXZ; CAutoplayDeviceData::Release(void)
0x1800efe8c  lea     rcx, ?g_csAutoplayDeviceDataManager@@3VCCritSecDelayInitBase@@A; lpCriticalSection
0x1800efe93  call    cs:__imp_LeaveCriticalSection
0x1800efe9a  nop     dword ptr [rax+rax+00h]
0x1800efe9f  test    esi, esi
0x1800efea1  jns     short loc_1800EFECD
0x1800efea3  mov     rcx, cs:WPP_GLOBAL_Control
0x1800efeaa  cmp     rcx, r15
0x1800efead  jz      short loc_1800EFECD
0x1800efeaf  test    byte ptr [rcx+1Ch], 8
0x1800efeb3  jz      short loc_1800EFECD
0x1800efeb5  mov     edx, 27h ; '''
  ... truncated ...
```
