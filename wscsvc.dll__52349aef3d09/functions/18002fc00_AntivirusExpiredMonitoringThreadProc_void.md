# AntivirusExpiredMonitoringThreadProc(void *)

- ea: `0x18002fc00`
- end: `0x180030471`
- name: `?AntivirusExpiredMonitoringThreadProc@@YAKPEAX@Z`
- size: `2161`
- prototype: `__int64 __fastcall(PVOID Parameter)`
- caller_count: `0`
- callee_count: `22`
- tags: `registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callees

- `0x180001300`
- `0x180002db0`
- `0x180002e30`
- `0x18000760c`
- `0x1800088b0`
- `0x180015bf0`
- `0x180018b60`
- `0x1800196e0`
- `0x18001b7f0`
- `0x18001c4c0`
- `0x18001c690`
- `0x18001fa14`
- `0x18001fb88`
- `0x1800202e8`
- `0x180023dec`
- `0x18002fc00`
- `0x18003052c`
- `0x1800305ec`
- `0x180036908`
- `0x18003fbf2`
- `0x18003fc30`
- `0x180042010`

## import_xrefs

- `ntdll!RtlNtStatusToDosErrorNoTeb` at `0x18003043d`
- `ntdll!RtlNtStatusToDosErrorNoTeb` at `0x18003043d`
- `ntdll!RtlPublishWnfStateData` at `0x18003002b`
- `ntdll!RtlPublishWnfStateData` at `0x1800301d3`
- `ntdll!RtlPublishWnfStateData` at `0x18003002b`
- `ntdll!RtlPublishWnfStateData` at `0x1800301d3`
- `api-ms-win-core-synch-l1-1-0!SetWaitableTimer` at `0x18002fd68`
- `api-ms-win-core-synch-l1-1-0!SetWaitableTimer` at `0x18002fd68`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002ff60`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800303ea`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002ff60`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800303ea`
- `api-ms-win-core-synch-l1-1-0!CancelWaitableTimer` at `0x1800303f7`
- `api-ms-win-core-synch-l1-1-0!CancelWaitableTimer` at `0x1800303f7`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002fdeb`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002fdeb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002fc9e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002fd72`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180030452`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002fc9e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002fd72`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180030452`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180030400`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180030400`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18002fcea`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18002fd27`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18002fcea`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18002fd27`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18002ff8b`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18003016c`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18002ff8b`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18003016c`
- `api-ms-win-core-synch-l1-2-1!CreateWaitableTimerW` at `0x18002fc8c`
- `api-ms-win-core-synch-l1-2-1!CreateWaitableTimerW` at `0x18002fc8c`
- `api-ms-win-core-synch-l1-2-1!WaitForMultipleObjects` at `0x18002fdc9`
- `api-ms-win-core-synch-l1-2-1!WaitForMultipleObjects` at `0x18002fdc9`

## pseudocode

```c
__int64 __fastcall AntivirusExpiredMonitoringThreadProc(PVOID Parameter)
{
  BOOL v1; // r14d
  struct CExternalBase *v2; // rdi
  void *v3; // rbx
  DWORD LastError; // esi
  DWORD v5; // eax
  int v6; // r15d
  int v7; // r13d
  __int64 v8; // rcx
  int v9; // eax
  int v10; // r15d
  int v11; // r12d
  DWORD v12; // ebx
  unsigned int v13; // r14d
  int v14; // ebx
  int v15; // eax
  _WORD *v16; // rax
  int v17; // r12d
  int v18; // eax
  unsigned int v19; // r10d
  char ProductState; // al
  int v21; // r8d
  NTSTATUS v22; // ebx
  __int64 v23; // rcx
  __int64 v24; // r8
  __int64 v25; // r9
  __int64 *v26; // rax
  bool v27; // zf
  __int64 *v28; // rax
  CThirdPartyManager *v29; // rcx
  unsigned int v30; // r10d
  char v31; // al
  int v32; // r8d
  __int64 v33; // r8
  __int64 v34; // r9
  __int64 *v35; // rax
  __int64 *v36; // rax
  const wchar_t *v37; // rax
  __int64 *v38; // rax
  CThirdPartyManager *v39; // rcx
  int v40; // edx
  struct IWbemServices *v41; // rbx
  const wchar_t *v42; // r9
  const wchar_t *v43; // rax
  DWORD pcbData; // [rsp+50h] [rbp-B0h] BYREF
  unsigned int v46; // [rsp+54h] [rbp-ACh]
  int v47; // [rsp+58h] [rbp-A8h]
  unsigned __int16 *v48; // [rsp+60h] [rbp-A0h] BYREF
  unsigned int v49[2]; // [rsp+68h] [rbp-98h] BYREF
  __int64 *v50; // [rsp+70h] [rbp-90h] BYREF
  LONG lPeriod; // [rsp+78h] [rbp-88h] BYREF
  struct CExternalBase *v52; // [rsp+80h] [rbp-80h] BYREF
  unsigned __int64 pvData; // [rsp+88h] [rbp-78h] BYREF
  __int64 *v54; // [rsp+90h] [rbp-70h] BYREF
  NTSTATUS v55; // [rsp+98h] [rbp-68h]
  NTSTATUS v56; // [rsp+9Ch] [rbp-64h] BYREF
  int v57; // [rsp+A0h] [rbp-60h] BYREF
  struct IWbemServices *v58; // [rsp+A8h] [rbp-58h] BYREF
  LARGE_INTEGER DueTime; // [rsp+B0h] [rbp-50h] BYREF
  HANDLE WaitableTimerW; // [rsp+B8h] [rbp-48h]
  HANDLE Handles[2]; // [rsp+C0h] [rbp-40h] BYREF
  int v62; // [rsp+D0h] [rbp-30h] BYREF
  struct _FILETIME SystemTimeAsFileTime; // [rsp+D4h] [rbp-2Ch] BYREF
  unsigned __int16 v64[256]; // [rsp+DCh] [rbp-24h] BYREF
  unsigned __int16 v65[258]; // [rsp+2DCh] [rbp+1DCh] BYREF
  int v66; // [rsp+4E0h] [rbp+3E0h] BYREF
  struct _FILETIME v67; // [rsp+4E4h] [rbp+3E4h] BYREF
  unsigned __int16 v68[256]; // [rsp+4ECh] [rbp+3ECh] BYREF
  unsigned __int16 v69[258]; // [rsp+6ECh] [rbp+5ECh] BYREF

  v1 = 0;
  v58 = 0;
  *(_OWORD *)Handles = 0;
  v2 = 0;
  v52 = 0;
  DueTime.QuadPart = 0;
  lPeriod = 86400000;
  pvData = 86400000;
  pcbData = 0;
  if ( WPP_GLOBAL_Control != (CThirdPartyManager *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 21, WPP_c81c3ae13a39328400a46a9fe4e4d5f2_Traceguids);
  WaitableTimerW = CreateWaitableTimerW(0, 0, 0);
  v3 = WaitableTimerW;
  if ( WaitableTimerW )
  {
    pcbData = 4;
    RegGetValueW(
      HKEY_LOCAL_MACHINE,
      L"SOFTWARE\\Policies\\Microsoft\\Windows\\WscTimer",
      L"TimerPeriod",
      0x10u,
      0,
      &lPeriod,
      &pcbData);
    pcbData = 8;
    RegGetValueW(
      HKEY_LOCAL_MACHINE,
      L"SOFTWARE\\Policies\\Microsoft\\Windows\\WscTimer",
      L"Delta",
      0x40u,
      0,
      &pvData,
      &pcbData);
    v54 = 0;
    if ( !is_mul_ok(pvData, 0x2710u) )
    {
      pvData = -1;
      LastError = 534;
      goto LABEL_100;
    }
    pvData *= 10000LL;
    DueTime.QuadPart = -600000000;
    if ( !SetWaitableTimer(v3, &DueTime, lPeriod, 0, 0, 0) )
    {
      LastError = GetLastError();
LABEL_100:
      CancelWaitableTimer(v3);
      CloseHandle(v3);
      goto LABEL_101;
    }
    LastError = 0;
    Handles[0] = g_hShutdownThreadNotify;
    v47 = 0;
    Handles[1] = v3;
    while ( 1 )
    {
      pcbData = 0;
      if ( v2 )
      {
        (**(void (__fastcall ***)(struct CExternalBase *, __int64))v2)(v2, 1);
        v2 = 0;
        v52 = 0;
      }
      v5 = WaitForMultipleObjects(2u, Handles, 0, 0xFFFFFFFF);
      if ( !v5 )
        goto LABEL_105;
      if ( v5 != 1 )
      {
        LastError = GetLastError();
LABEL_105:
        v6 = 0;
LABEL_95:
        if ( v2 )
          (**(void (__fastcall ***)(struct CExternalBase *, __int64))v2)(v2, 1);
        if ( v6 )
          LeaveCriticalSection((LPCRITICAL_SECTION)((char *)WscServiceUtils::g_pAntiVirusManager + 16));
        v3 = WaitableTimerW;
        goto LABEL_100;
      }
      EnterCriticalSection((LPCRITICAL_SECTION)((char *)WscServiceUtils::g_pAntiVirusManager + 16));
      v6 = 1;
      LODWORD(v50) = 1;
      if ( (int)CThirdPartyManager::GetNumberOfProducts(WscServiceUtils::g_pAntiVirusManager, &pcbData) < 0 )
        goto LABEL_95;
      v7 = -1;
      v8 = 0;
      v9 = -1;
      v46 = 0;
      v10 = 0;
      LODWORD(v48) = -1;
      v11 = 0;
      v12 = 0;
      if ( pcbData )
      {
        while ( 1 )
        {
          v49[0] = 0;
          if ( (int)CThirdPartyManager::GetProductBitField(WscServiceUtils::g_pAntiVirusManager, v12, v49) < 0 )
            goto LABEL_94;
          v13 = v49[0];
          if ( (unsigned int)ExtractProductOwner(v49[0]) == 256 || (unsigned int)ExtractProductState(v13) != 4096 )
          {
            if ( (unsigned int)ExtractProductState(v13) == 0x4000 )
            {
              v10 = 1;
              v7 = v12;
            }
            else if ( (unsigned int)ExtractProductNotification(v13) == 3145728 )
            {
              v8 = v46;
              v11 = 1;
              v9 = v12;
              LODWORD(v48) = v12;
              goto LABEL_24;
            }
            v8 = v46;
          }
          else
          {
            v8 = 1;
            v46 = 1;
          }
          v9 = (int)v48;
LABEL_24:
          ++v12;
          v1 = 0;
          if ( v12 >= pcbData )
          {
            if ( v10 )
              v1 = v8 == 0;
            break;
          }
        }
      }
      v6 = 0;
      if ( !v11 || (v14 = 1, (_DWORD)v8) )
        v14 = 0;
      if ( !v1 )
      {
        v7 = -1;
        if ( !v14 )
          goto LABEL_41;
        v7 = v9;
      }
      if ( v7 >= 0 )
      {
        v15 = CThirdPartyManager::CopyProductAtOffset((CThirdPartyManager *)v8, v7, &v52);
        v2 = v52;
        if ( v15 < 0 )
        {
          LastError = (unsigned __int16)v15;
LABEL_94:
          v6 = (int)v50;
          goto LABEL_95;
        }
      }
      if ( v14 )
      {
        v16 = (_WORD *)*((_QWORD *)v2 + 3);
        if ( !v16 || !*v16 )
        {
          v17 = 1;
          v14 = 0;
          v47 = 1;
          goto LABEL_42;
        }
      }
LABEL_41:
      v17 = v47;
LABEL_42:
      LeaveCriticalSection((LPCRITICAL_SECTION)((char *)WscServiceUtils::g_pAntiVirusManager + 16));
      if ( v1 )
      {
        memset_0(&SystemTimeAsFileTime, 0, 0x408u);
        v62 = 3;
        GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
        v18 = StringCchCopyW(v64, 0xFFu, *((const unsigned __int16 **)v2 + 2));
        v1 = 0;
        if ( v18 < 0 )
          goto LABEL_103;
        v18 = StringCchCopyW(v65, v19, *((const unsigned __int16 **)v2 + 3));
        if ( v18 < 0 )
          goto LABEL_103;
        if ( WPP_GLOBAL_Control != (CThirdPartyManager *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
        {
          ProductState = CExternalBase::GetProductState(v2);
          WPP_SF_SSD(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            22,
            v21,
            *((_QWORD *)v2 + 2),
            *((_QWORD *)v2 + 3),
            ProductState);
        }
        v22 = RtlPublishWnfStateData(WNF_WSC_SECURITY_CENTER_USER_NOTIFICATION, 0, &v62, 1036, 0);
        if ( (unsigned int)dword_180053218 > 5 && (unsigned __int8)tlgKeywordOn(&dword_180053218, 0x400000000000LL) )
        {
          v55 = v22;
          v26 = &qword_180045B70;
          if ( *((_QWORD *)v2 + 6) )
            v26 = (__int64 *)*((_QWORD *)v2 + 6);
          v27 = *((_QWORD *)v2 + 5) == 0;
          v50 = v26;
          *(_QWORD *)v49 = v65;
          v48 = v64;
          v28 = &qword_180045B70;
          if ( !v27 )
            v28 = (__int64 *)*((_QWORD *)v2 + 5);
          v54 = v28;
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>>(
            v23,
            (__int64)byte_18004BF13,
            v24,
            v25,
            &v54,
            &v48,
            v49,
            &v50);
        }
      }
      else
      {
        v1 = 0;
        if ( !v14 )
          goto LABEL_74;
        v29 = WscServiceUtils::g_pAntiVirusManager;
        *((_DWORD *)v2 + 20) &= 0xFF0FFFFF;
        if ( (int)CThirdPartyManager::UpdateExternalProduct(v29, v2) < 0 )
          goto LABEL_74;
        memset_0(&v67, 0, 0x408u);
        v66 = 2;
        v18 = StringCchCopyW(v68, 0xFFu, *((const unsigned __int16 **)v2 + 2));
        if ( v18 < 0 || (v18 = StringCchCopyW(v69, v30, *((const unsigned __int16 **)v2 + 3)), v18 < 0) )
        {
LABEL_103:
          LastError = (unsigned __int16)v18;
          goto LABEL_95;
        }
        GetSystemTimeAsFileTime(&v67);
        if ( WPP_GLOBAL_Control != (CThirdPartyManager *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
        {
          v31 = CExternalBase::GetProductState(v2);
          WPP_SF_SSD(*((_QWORD *)WPP_GLOBAL_Control + 2), 23, v32, *((_QWORD *)v2 + 2), *((_QWORD *)v2 + 3), v31);
        }
        v22 = RtlPublishWnfStateData(WNF_WSC_SECURITY_CENTER_USER_NOTIFICATION, 0, &v66, 1036, 0);
        if ( (unsigned int)dword_180053218 > 5 && (unsigned __int8)tlgKeywordOn(&dword_180053218, 0x400000000000LL) )
        {
          v56 = v22;
          v57 = 0;
          v35 = (__int64 *)L"NULL";
          if ( *((_QWORD *)v2 + 6) )
            v35 = (__int64 *)*((_QWORD *)v2 + 6);
          v27 = *((_QWORD *)v2 + 3) == 0;
          v54 = v35;
          v36 = (__int64 *)L"NULL";
          if ( !v27 )
            v36 = (__int64 *)*((_QWORD *)v2 + 3);
          v27 = *((_QWORD *)v2 + 2) == 0;
          v50 = v36;
          v37 = L"NULL";
          if ( !v27 )
            v37 = (const wchar_t *)*((_QWORD *)v2 + 2);
          v27 = *((_QWORD *)v2 + 5) == 0;
          *(_QWORD *)v49 = v37;
          v38 = (__int64 *)L"NULL";
          if ( !v27 )
            v38 = (__int64 *)*((_QWORD *)v2 + 5);
          v48 = (unsigned __int16 *)v38;
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
            (__int64)L"NULL",
            (unsigned __int8 *)byte_18004BEA1,
            v33,
            v34,
            (__int64 **)&v48,
            (__int64 **)v49,
            &v50,
            &v54,
            (__int64)&v57,
            (__int64)&v56);
        }
      }
      if ( v22 < 0 )
      {
        LastError = RtlNtStatusToDosErrorNoTeb(v22);
        goto LABEL_95;
      }
LABEL_74:
      if ( v17 )
      {
        if ( WPP_GLOBAL_Control != (CThirdPartyManager *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
        {
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 24, WPP_c81c3ae13a39328400a46a9fe4e4d5f2_Traceguids);
        }
        v39 = WscServiceUtils::g_pAntiVirusManager;
        *((_DWORD *)v2 + 20) &= 0xFF0FFFFF;
        if ( (int)CThirdPartyManager::UpdateExternalProduct(v39, v2) >= 0 )
        {
          if ( g_pWmiEventManagerAvFw && (int)CWmiEventManager::GetWbemServices(g_pWmiEventManagerAvFw, v40, &v58) >= 0 )
          {
            v41 = v58;
            CExternalBase::UpdatePersistentStore(v2, v58, 0, 4);
            ((void (__fastcall *)(struct IWbemServices *))v41->lpVtbl->Release)(v41);
            v58 = 0;
          }
          CAlertStatus::FireNotificationEvents(g_pAlertStatus, 0);
        }
      }
      if ( v46 || v17 || v7 < 0 )
      {
        if ( WPP_GLOBAL_Control != (CThirdPartyManager *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
        {
          v42 = L"true";
          v43 = L"true";
          if ( !v17 )
            v43 = L"false";
          if ( !v46 )
            v42 = L"false";
          WPP_SF_SSd(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            25,
            (unsigned int)WPP_c81c3ae13a39328400a46a9fe4e4d5f2_Traceguids,
            (_DWORD)v42,
            (__int64)v43,
            v7);
        }
        goto LABEL_95;
      }
    }
  }
  LastError = GetLastError();
LABEL_101:
  _InterlockedCompareExchange(&g_lExpiredStateMonitored, 0, 1);
  return LastError;
}

```

## disassembly

```asm
0x18002fc00  push    rbp
0x18002fc02  push    rbx
0x18002fc03  push    rsi
0x18002fc04  push    rdi
0x18002fc05  push    r12
0x18002fc07  push    r13
0x18002fc09  push    r14
0x18002fc0b  push    r15
0x18002fc0d  lea     rbp, [rsp-808h]
0x18002fc15  sub     rsp, 908h
0x18002fc1c  mov     rax, cs:__security_cookie
0x18002fc23  xor     rax, rsp
0x18002fc26  mov     [rbp+840h+var_50], rax
0x18002fc2d  xor     r14d, r14d
0x18002fc30  mov     eax, 5265C00h
0x18002fc35  xorps   xmm0, xmm0
0x18002fc38  mov     [rbp+840h+var_898], r14
0x18002fc3c  movups  xmmword ptr [rbp+840h+Handles], xmm0
0x18002fc40  mov     edi, r14d
0x18002fc43  mov     [rbp+840h+var_8C0], r14
0x18002fc47  mov     qword ptr [rbp+840h+DueTime], r14
0x18002fc4b  mov     [rsp+940h+lPeriod], eax
0x18002fc4f  mov     [rbp+840h+var_8B8], rax
0x18002fc53  mov     [rsp+940h+var_8F0], r14d
0x18002fc58  mov     rcx, cs:WPP_GLOBAL_Control
0x18002fc5f  lea     rax, WPP_GLOBAL_Control
0x18002fc66  cmp     rcx, rax
0x18002fc69  jz      short loc_18002FC85
0x18002fc6b  test    byte ptr [rcx+1Ch], 8
0x18002fc6f  jz      short loc_18002FC85
0x18002fc71  mov     rcx, [rcx+10h]
0x18002fc75  lea     edx, [r14+15h]
0x18002fc79  lea     r8, WPP_c81c3ae13a39328400a46a9fe4e4d5f2_Traceguids
0x18002fc80  call    WPP_SF_
0x18002fc85  xor     r8d, r8d; lpTimerName
0x18002fc88  xor     edx, edx; bManualReset
0x18002fc8a  xor     ecx, ecx; lpTimerAttributes
0x18002fc8c  call    cs:__imp_CreateWaitableTimerW
0x18002fc92  mov     [rbp+840h+var_888], rax
0x18002fc96  mov     rbx, rax
0x18002fc99  test    rax, rax
0x18002fc9c  jnz     short loc_18002FCAB
0x18002fc9e  call    cs:__imp_GetLastError
0x18002fca4  mov     esi, eax
0x18002fca6  jmp     loc_180030406
0x18002fcab  lea     rax, [rsp+940h+var_8F0]
0x18002fcb0  mov     [rsp+940h+var_8F0], 4
0x18002fcb8  mov     [rsp+940h+pcbData], rax; pcbData
0x18002fcbd  lea     r8, aTimerperiod; "TimerPeriod"
0x18002fcc4  lea     rax, [rsp+940h+lPeriod]
0x18002fcc9  mov     rsi, 0FFFFFFFF80000002h
0x18002fcd0  mov     [rsp+940h+pvData], rax; pvData
0x18002fcd5  lea     rdx, aSoftwarePolici_1; "SOFTWARE\\Policies\\Microsoft\\Windows"...
0x18002fcdc  mov     r9d, 10h; dwFlags
0x18002fce2  mov     [rsp+940h+pdwType], r14; pdwType
0x18002fce7  mov     rcx, rsi; hkey
0x18002fcea  call    cs:__imp_RegGetValueW
0x18002fcf0  lea     rax, [rsp+940h+var_8F0]
0x18002fcf5  mov     [rsp+940h+var_8F0], 8
0x18002fcfd  mov     [rsp+940h+pcbData], rax; pcbData
0x18002fd02  lea     r8, aDelta; "Delta"
0x18002fd09  lea     rax, [rbp+840h+var_8B8]
0x18002fd0d  mov     r9d, 40h ; '@'; dwFlags
0x18002fd13  mov     [rsp+940h+pvData], rax; pvData
0x18002fd18  lea     rdx, aSoftwarePolici_1; "SOFTWARE\\Policies\\Microsoft\\Windows"...
0x18002fd1f  mov     rcx, rsi; hkey
0x18002fd22  mov     [rsp+940h+pdwType], r14; pdwType
0x18002fd27  call    cs:__imp_RegGetValueW
0x18002fd2d  mov     eax, 2710h
0x18002fd32  mov     [rbp+840h+var_8B0], r14
0x18002fd36  mul     [rbp+840h+var_8B8]
0x18002fd3a  test    rdx, rdx
0x18002fd3d  jnz     loc_180030462
0x18002fd43  mov     r8d, [rsp+940h+lPeriod]; lPeriod
0x18002fd48  lea     rdx, [rbp+840h+DueTime]; lpDueTime
0x18002fd4c  mov     dword ptr [rsp+940h+pvData], r14d; fResume
0x18002fd51  xor     r9d, r9d; pfnCompletionRoutine
0x18002fd54  mov     rcx, rbx; hTimer
0x18002fd57  mov     [rsp+940h+pdwType], r14; lpArgToCompletionRoutine
0x18002fd5c  mov     [rbp+840h+var_8B8], rax
0x18002fd60  mov     qword ptr [rbp+840h+DueTime], 0FFFFFFFFDC3CBA00h
0x18002fd68  call    cs:__imp_SetWaitableTimer
0x18002fd6e  test    eax, eax
0x18002fd70  jnz     short loc_18002FD7F
0x18002fd72  call    cs:__imp_GetLastError
0x18002fd78  mov     esi, eax
0x18002fd7a  jmp     loc_1800303F4
0x18002fd7f  mov     rax, cs:?g_hShutdownThreadNotify@@3PEAXEA; void * g_hShutdownThreadNotify
0x18002fd86  mov     esi, r14d
0x18002fd89  mov     [rbp+840h+Handles], rax
0x18002fd8d  mov     dword ptr [rsp+940h+var_8EC+4], r14d
0x18002fd92  mov     [rbp+840h+Handles+8], rbx
0x18002fd96  mov     [rsp+940h+var_8F0], r14d
0x18002fd9b  test    rdi, rdi
0x18002fd9e  jz      short loc_18002FDBA
0x18002fda0  mov     rax, [rdi]
0x18002fda3  mov     edx, 1
0x18002fda8  mov     rcx, rdi
0x18002fdab  mov     rax, [rax]
0x18002fdae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002fdb3  mov     rdi, r14
0x18002fdb6  mov     [rbp+840h+var_8C0], r14
0x18002fdba  xor     r8d, r8d; bWaitAll
0x18002fdbd  lea     rdx, [rbp+840h+Handles]; lpHandles
0x18002fdc1  or      r9d, 0FFFFFFFFh; dwMilliseconds
0x18002fdc5  lea     ecx, [r8+2]; nCount
0x18002fdc9  call    cs:__imp_WaitForMultipleObjects
0x18002fdcf  test    eax, eax
0x18002fdd1  jz      loc_18003045A
0x18002fdd7  cmp     eax, 1
0x18002fdda  jnz     loc_180030452
0x18002fde0  mov     rcx, cs:?g_pAntiVirusManager@WscServiceUtils@@3PEAVCAntiVirusManager@@EA; CAntiVirusManager * WscServiceUtils::g_pAntiVirusManager
0x18002fde7  add     rcx, 10h; lpCriticalSection
0x18002fdeb  call    cs:__imp_EnterCriticalSection
0x18002fdf1  mov     rcx, cs:?g_pAntiVirusManager@WscServiceUtils@@3PEAVCAntiVirusManager@@EA; this
0x18002fdf8  lea     rdx, [rsp+940h+var_8F0]; unsigned int *
0x18002fdfd  mov     r15d, 1
0x18002fe03  mov     dword ptr [rsp+940h+var_8D0], r15d
0x18002fe08  call    ?GetNumberOfProducts@CThirdPartyManager@@QEAAJAEAK@Z; CThirdPartyManager::GetNumberOfProducts(ulong &)
0x18002fe0d  test    eax, eax
0x18002fe0f  js      loc_1800303C2
0x18002fe15  or      r13d, 0FFFFFFFFh
0x18002fe19  mov     ecx, r14d
0x18002fe1c  or      eax, r13d
0x18002fe1f  mov     dword ptr [rsp+940h+var_8EC], ecx
0x18002fe23  mov     r15d, r14d
0x18002fe26  mov     dword ptr [rsp+940h+var_8E0], eax
0x18002fe2a  mov     r12d, r14d
0x18002fe2d  mov     ebx, r14d
0x18002fe30  cmp     [rsp+940h+var_8F0], r14d
0x18002fe35  jbe     loc_18002FEC5
0x18002fe3b  mov     rcx, cs:?g_pAntiVirusManager@WscServiceUtils@@3PEAVCAntiVirusManager@@EA; this
0x18002fe42  lea     r8, [rsp+940h+var_8D8]; unsigned int *
0x18002fe47  mov     edx, ebx; unsigned int
0x18002fe49  mov     [rsp+940h+var_8D8], r14d
0x18002fe4e  call    ?GetProductBitField@CThirdPartyManager@@QEAAJKAEAK@Z; CThirdPartyManager::GetProductBitField(ulong,ulong &)
0x18002fe53  test    eax, eax
0x18002fe55  js      loc_1800303BD
0x18002fe5b  mov     r14d, [rsp+940h+var_8D8]
0x18002fe60  mov     ecx, r14d
0x18002fe63  call    ?ExtractProductOwner@@YA?AW4ProductOwner@@K@Z; ExtractProductOwner(ulong)
0x18002fe68  cmp     eax, 100h
0x18002fe6d  jz      short loc_18002FE89
0x18002fe6f  mov     ecx, r14d
0x18002fe72  call    ?ExtractProductState@@YA?AW4ProductState@@K@Z; ExtractProductState(ulong)
0x18002fe77  cmp     eax, 1000h
0x18002fe7c  jnz     short loc_18002FE89
0x18002fe7e  mov     ecx, 1
0x18002fe83  mov     dword ptr [rsp+940h+var_8EC], ecx
0x18002fe87  jmp     short loc_18002FEA9
0x18002fe89  mov     ecx, r14d
0x18002fe8c  call    ?ExtractProductState@@YA?AW4ProductState@@K@Z; ExtractProductState(ulong)
0x18002fe91  cmp     eax, 4000h
0x18002fe96  jnz     loc_18002FF28
0x18002fe9c  mov     r15d, 1
0x18002fea2  mov     r13d, ebx
0x18002fea5  mov     ecx, dword ptr [rsp+940h+var_8EC]; this
0x18002fea9  mov     eax, dword ptr [rsp+940h+var_8E0]
0x18002fead  inc     ebx
0x18002feaf  mov     r14, rsi
0x18002feb2  cmp     ebx, [rsp+940h+var_8F0]
0x18002feb6  jb      short loc_18002FE3B
0x18002feb8  test    r15d, r15d
0x18002febb  jz      short loc_18002FEC5
0x18002febd  test    ecx, ecx
0x18002febf  jnz     short loc_18002FEC5
0x18002fec1  lea     r14d, [rcx+1]
0x18002fec5  xor     r15d, r15d
0x18002fec8  test    r12d, r12d
0x18002fecb  jz      short loc_18002FED5
0x18002fecd  lea     ebx, [r15+1]
0x18002fed1  test    ecx, ecx
0x18002fed3  jz      short loc_18002FED8
0x18002fed5  mov     ebx, r15d
0x18002fed8  test    r14d, r14d
0x18002fedb  jnz     short loc_18002FEE8
0x18002fedd  or      r13d, 0FFFFFFFFh
0x18002fee1  test    ebx, ebx
0x18002fee3  jz      short loc_18002FF50
0x18002fee5  mov     r13d, eax
0x18002fee8  test    r13d, r13d
0x18002feeb  js      short loc_18002FF05
0x18002feed  lea     r8, [rbp+840h+var_8C0]; struct CExternalBase **
0x18002fef1  mov     edx, r13d; unsigned int
0x18002fef4  call    ?CopyProductAtOffset@CThirdPartyManager@@QEAAJKPEAPEAVCExternalBase@@@Z; CThirdPartyManager::CopyProductAtOffset(ulong,CExternalBase * *)
0x18002fef9  mov     rdi, [rbp+840h+var_8C0]
0x18002fefd  test    eax, eax
0x18002feff  js      loc_1800303B7
0x18002ff05  test    ebx, ebx
0x18002ff07  jz      short loc_18002FF50
0x18002ff09  mov     rax, [rdi+18h]
0x18002ff0d  test    rax, rax
0x18002ff10  jz      short loc_18002FF18
0x18002ff12  cmp     [rax], r15w
0x18002ff16  jnz     short loc_18002FF50
0x18002ff18  mov     r12d, 1
0x18002ff1e  mov     ebx, r15d
0x18002ff21  mov     dword ptr [rsp+940h+var_8EC+4], r12d
0x18002ff26  jmp     short loc_18002FF55
0x18002ff28  mov     ecx, r14d
0x18002ff2b  call    ?ExtractProductNotification@@YA?AW4ProductNotification@@K@Z; ExtractProductNotification(ulong)
0x18002ff30  cmp     eax, 300000h
0x18002ff35  jnz     loc_18002FEA5
0x18002ff3b  mov     ecx, dword ptr [rsp+940h+var_8EC]
0x18002ff3f  mov     r12d, 1
0x18002ff45  mov     eax, ebx
0x18002ff47  mov     dword ptr [rsp+940h+var_8E0], ebx
0x18002ff4b  jmp     loc_18002FEAD
0x18002ff50  mov     r12d, dword ptr [rsp+940h+var_8EC+4]
0x18002ff55  mov     rcx, cs:?g_pAntiVirusManager@WscServiceUtils@@3PEAVCAntiVirusManager@@EA; CAntiVirusManager * WscServiceUtils::g_pAntiVirusManager
0x18002ff5c  add     rcx, 10h; lpCriticalSection
0x18002ff60  call    cs:__imp_LeaveCriticalSection
0x18002ff66  test    r14d, r14d
0x18002ff69  jz      loc_1800300E2
0x18002ff6f  xor     edx, edx; Val
0x18002ff71  lea     rcx, [rbp+840h+SystemTimeAsFileTime]; void *
0x18002ff75  mov     r8d, 408h; Size
0x18002ff7b  call    memset_0
0x18002ff80  lea     rcx, [rbp+840h+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x18002ff84  mov     [rbp+840h+var_870], 3
0x18002ff8b  call    cs:__imp_GetSystemTimeAsFileTime
0x18002ff91  mov     r8, [rdi+10h]; unsigned __int16 *
0x18002ff95  lea     rcx, [rbp+840h+var_864]; unsigned __int16 *
0x18002ff99  mov     r10d, 0FFh
0x18002ff9f  mov     edx, r10d; unsigned __int64
0x18002ffa2  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18002ffa7  xor     r14d, r14d
0x18002ffaa  test    eax, eax
0x18002ffac  js      loc_18003044A
0x18002ffb2  mov     r8, [rdi+18h]; unsigned __int16 *
0x18002ffb6  lea     rcx, [rbp+840h+var_664]; unsigned __int16 *
0x18002ffbd  mov     edx, r10d; unsigned __int64
0x18002ffc0  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18002ffc5  test    eax, eax
0x18002ffc7  js      loc_18003044A
0x18002ffcd  mov     rax, cs:WPP_GLOBAL_Control
0x18002ffd4  lea     rcx, WPP_GLOBAL_Control
0x18002ffdb  cmp     rax, rcx
0x18002ffde  jz      short loc_180030013
0x18002ffe0  test    byte ptr [rax+1Ch], 4
0x18002ffe4  jz      short loc_180030013
0x18002ffe6  mov     rcx, rdi
0x18002ffe9  call    ?GetProductState@CExternalBase@@QEAA?AW4ProductState@@XZ; CExternalBase::GetProductState(void)
0x18002ffee  mov     rcx, cs:WPP_GLOBAL_Control
0x18002fff5  lea     edx, [r14+16h]
0x18002fff9  mov     r9, [rdi+10h]
0x18002fffd  mov     dword ptr [rsp+940h+pvData], eax
0x180030001  mov     rax, [rdi+18h]
0x180030005  mov     rcx, [rcx+10h]
0x180030009  mov     [rsp+940h+pdwType], rax
0x18003000e  call    WPP_SF_SSD
0x180030013  mov     rcx, cs:WNF_WSC_SECURITY_CENTER_USER_NOTIFICATION
0x18003001a  lea     r8, [rbp+840h+var_870]
0x18003001e  mov     r9d, 40Ch
0x180030024  mov     [rsp+940h+pdwType], r14
0x180030029  xor     edx, edx
0x18003002b  call    cs:__imp_RtlPublishWnfStateData
0x180030031  mov     ecx, cs:dword_180053218
0x180030037  mov     ebx, eax
0x180030039  cmp     ecx, 5
0x18003003c  jbe     loc_18003029E
0x180030042  mov     rdx, 400000000000h
0x18003004c  lea     rcx, dword_180053218
0x180030053  call    _tlgKeywordOn
0x180030058  test    al, al
0x18003005a  jz      loc_18003029E
0x180030060  mov     [rbp+840h+var_8A8], ebx
0x180030063  lea     rax, qword_180045B70
0x18003006a  cmp     [rdi+30h], r14
0x18003006e  lea     rdx, byte_18004BF13
0x180030075  cmovnz  rax, [rdi+30h]
0x18003007a  cmp     [rdi+28h], r14
0x18003007e  mov     [rsp+940h+var_8D0], rax
0x180030083  lea     rax, [rbp+840h+var_664]
0x18003008a  mov     qword ptr [rsp+940h+var_8D8], rax
0x18003008f  lea     rax, [rbp+840h+var_864]
0x180030093  mov     [rsp+940h+var_8E0], rax
0x180030098  lea     rax, qword_180045B70
0x18003009f  cmovnz  rax, [rdi+28h]
0x1800300a4  mov     [rbp+840h+var_8B0], rax
0x1800300a8  lea     rax, [rbp+840h+var_8A8]
0x1800300ac  mov     [rsp+940h+var_900], rax
0x1800300b1  lea     rax, [rsp+940h+var_8D0]
0x1800300b6  mov     [rsp+940h+var_908], rax
0x1800300bb  lea     rax, [rsp+940h+var_8D8]
0x1800300c0  mov     [rsp+940h+pcbData], rax
0x1800300c5  lea     rax, [rsp+940h+var_8E0]
0x1800300ca  mov     [rsp+940h+pvData], rax
0x1800300cf  lea     rax, [rbp+840h+var_8B0]
0x1800300d3  mov     [rsp+940h+pdwType], rax
0x1800300d8  call    ??$Write@U?$_tlgWrapSz@G@@U1@U1@U1@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@333AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &)
0x1800300dd  jmp     loc_18003029E
0x1800300e2  xor     r14d, r14d
0x1800300e5  test    ebx, ebx
0x1800300e7  jz      loc_1800302A6
0x1800300ed  mov     rcx, cs:?g_pAntiVirusManager@WscServiceUtils@@3PEAVCAntiVirusManager@@EA; this
0x1800300f4  mov     rdx, rdi; struct CExternalBase *
0x1800300f7  and     dword ptr [rdi+50h], 0FF0FFFFFh
0x1800300fe  call    ?UpdateExternalProduct@CThirdPartyManager@@QEAAJPEAVCExternalBase@@@Z; CThirdPartyManager::UpdateExternalProduct(CExternalBase *)
0x180030103  test    eax, eax
  ... truncated ...
```
