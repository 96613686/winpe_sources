# FindFirstPrinterChangeNotificationWorker(void *,ulong,ulong,ulong,_PRINTER_NOTIFY_OPTIONS *,void * *,int,void *)

- ea: `0x14006cc88`
- end: `0x14006d347`
- name: `?FindFirstPrinterChangeNotificationWorker@@YAHPEAXKKKPEAU_PRINTER_NOTIFY_OPTIONS@@PEAPEAXH0@Z`
- size: `1727`
- prototype: `__int64 __fastcall(struct _PRINTHANDLE *, unsigned int, unsigned int, DWORD dwProcessId, struct _PRINTER_NOTIFY_OPTIONS *, LPHANDLE lpTargetHandle, int, void *)`
- caller_count: `3`
- callee_count: `12`
- tags: `authz_impersonation, registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x140054d30`
- `0x14006dec0`
- `0x14006df10`

## callees

- `0x140015378`
- `0x140018f84`
- `0x14002d0a0`
- `0x140040654`
- `0x14004be9c`
- `0x14005e898`
- `0x14005e8c0`
- `0x14006cabc`
- `0x14006cc88`
- `0x14006d8e8`
- `0x14006daa8`
- `0x140081010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x14006cd79`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x14006d2ec`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x14006cd79`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x14006d2ec`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x14006cda7`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x14006cda7`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x14006ccf2`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x14006ccf2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14006ce60`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14006ce9e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14006d28b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14006ce60`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14006ce9e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14006d28b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14006d02d`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14006d0bc`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14006d199`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14006d1c9`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14006d301`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14006d02d`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14006d0bc`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14006d199`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14006d1c9`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14006d301`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x14006ce20`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x14006d1fa`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x14006ce20`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x14006d1fa`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x14006ce4d`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x14006d226`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x14006ce4d`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x14006d226`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14006ce85`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14006d238`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14006d2b6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14006d2cf`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14006ce85`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14006d238`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14006d2b6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14006d2cf`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x14006ce00`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x14006d050`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x14006ce00`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x14006d050`
- `api-ms-win-core-winrt-l1-1-0!RoActivateInstance` at `0x14006cf52`
- `api-ms-win-core-winrt-l1-1-0!RoActivateInstance` at `0x14006d105`
- `api-ms-win-core-winrt-l1-1-0!RoActivateInstance` at `0x14006cf52`
- `api-ms-win-core-winrt-l1-1-0!RoActivateInstance` at `0x14006d105`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x14006cf36`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x14006d0e9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x14006cf36`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x14006d0e9`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x14006d01e`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x14006d1db`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x14006d01e`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x14006d1db`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x14006ced3`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x14006d081`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x14006ced3`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x14006d081`

## string_xrefs

- `0x14006cf2f`: `Windows.Graphics.Internal.Printing.PrintScanBroker.PrintScanBrokerHandler`
- `0x14006d0e2`: `Windows.Graphics.Internal.Printing.PrintScanBroker.PrintScanBrokerHandler`
- `0x14006cdc8`: `Failed to create event.  Error %d.`
- `0x14006cfd5`: `QueryTo IPrintScanBrokerHandler failed. Error hr: 0x%x`
- `0x14006d180`: `QueryTo IPrintScanBrokerHandler failed. Error hr: 0x%x`
- `0x14006cff9`: `RoActivateInstance for PrintScanBrokerHandler failed. Error hr: 0x%x`
- `0x14006d1b3`: `RoActivateInstance for PrintScanBrokerHandler failed. Error hr: 0x%x`
- `0x14006cead`: `Failed to open process handle.  Error %d.`
- `0x14006d064`: `Failed to open process handle.  Error %d.`

## pseudocode

```c
__int64 __fastcall FindFirstPrinterChangeNotificationWorker(
        struct _PRINTHANDLE *a1,
        unsigned int a2,
        unsigned int a3,
        DWORD dwProcessId,
        struct _PRINTER_NOTIFY_OPTIONS *a5,
        LPHANDLE lpTargetHandle,
        int a7,
        void *a8)
{
  struct _PRINTER_NOTIFY_OPTIONS *v8; // r12
  unsigned int v13; // ecx
  unsigned int v14; // edx
  unsigned int v15; // eax
  unsigned __int16 *v16; // r8
  unsigned int v17; // r8d
  void *v18; // rcx
  unsigned __int16 *v19; // rbx
  BOOL v20; // r14d
  HANDLE v21; // rsi
  void *v22; // rbx
  HANDLE CurrentProcess; // rax
  DWORD LastError; // eax
  DWORD v25; // eax
  HRESULT v26; // esi
  unsigned __int16 v27; // bx
  HRESULT v28; // eax
  int v29; // edx
  unsigned int v30; // r8d
  int v31; // eax
  int v32; // eax
  __int64 v33; // r8
  int v34; // eax
  HANDLE v35; // r12
  HRESULT v36; // ebx
  HRESULT v37; // eax
  int v38; // edx
  unsigned int v39; // r8d
  int v40; // eax
  unsigned __int16 v41; // si
  int v42; // esi
  __int64 v43; // r8
  void *v44; // rbx
  HANDLE v45; // rax
  unsigned int v46; // ebx
  DWORD v47; // eax
  void *v48; // rcx
  __int64 v50; // [rsp+50h] [rbp-59h] BYREF
  __int64 v51; // [rsp+58h] [rbp-51h] BYREF
  unsigned int v52; // [rsp+60h] [rbp-49h] BYREF
  void *v53; // [rsp+68h] [rbp-41h] BYREF
  struct _PRINTER_NOTIFY_INIT *v54; // [rsp+70h] [rbp-39h] BYREF
  struct _PRINTER_NOTIFY_OPTIONS *v55; // [rsp+78h] [rbp-31h]
  HSTRING_HEADER hstringHeader; // [rsp+80h] [rbp-29h] BYREF
  HSTRING string; // [rsp+98h] [rbp-11h] BYREF

  v8 = a5;
  v55 = a5;
  v52 = 0;
  v54 = 0;
  if ( !a1 || *(_DWORD *)a1 != 24672 )
  {
    SetLastError(6u);
    return 0;
  }
  EnterCriticalSection(&RouterNotifySection);
  v13 = dwRouterUniqueSessionID;
  *lpTargetHandle = 0;
  while ( 1 )
  {
    v14 = *((_DWORD *)a1 + 20);
    if ( ((v14 + 1) & 0xFFFFFFFE) != 0 )
      break;
    v15 = v13++;
    *((_DWORD *)a1 + 20) = v15;
  }
  v16 = (unsigned __int16 *)&szMachineFullDNSName;
  if ( !(_WORD)szMachineFullDNSName )
    v16 = &szMachineName;
  dwRouterUniqueSessionID = v13;
  if ( (unsigned int)SetupChange(a1, v14, v16, &v52, a3, a2, a5, &v54, a8, 0) )
  {
    if ( (*(_BYTE *)(*((_QWORD *)a1 + 3) + 128LL) & 1) == 0 )
      goto LABEL_61;
    *(_QWORD *)(*((_QWORD *)a1 + 3) + 96LL) = CreateEventW(0, 1, 0, 0);
    v18 = *(void **)(*((_QWORD *)a1 + 3) + 96LL);
    if ( !v18 )
    {
      v19 = L"Failed to create event.  Error %d.";
      goto LABEL_64;
    }
    if ( a7 )
    {
      *lpTargetHandle = v18;
      goto LABEL_61;
    }
    v20 = 0;
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Print_PlatformStabilizationFixes_2026_Wave1>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Print_PlatformStabilizationFixes_2026_Wave1>::GetImpl'::`2'::impl) )
    {
      v21 = OpenProcess(0x40u, 0, dwProcessId);
      if ( v21 )
      {
        v22 = *(void **)(*((_QWORD *)a1 + 3) + 96LL);
        CurrentProcess = GetCurrentProcess();
        v20 = DuplicateHandle(CurrentProcess, v22, v21, lpTargetHandle, 0, 1, 2u);
        if ( !v20 )
        {
          LastError = GetLastError();
          PrvSpoolssTelemetry::WriteDbgTraceError(
            "FindFirstPrinterChangeNotificationWorker",
            L"Failed to duplicate handle directly.  Error %d.",
            LastError);
        }
        CloseHandle(v21);
        if ( v20 )
          goto LABEL_61;
      }
      else
      {
        v25 = GetLastError();
        PrvSpoolssTelemetry::WriteDbgTraceError(
          "FindFirstPrinterChangeNotificationWorker",
          L"Failed to open process handle.  Error %d.",
          v25);
      }
      if ( !(unsigned int)IsWindowsProtectedPrintEnabled() )
        goto LABEL_38;
      v26 = CoInitializeEx(0, 0);
      if ( (int)(v26 + 0x80000000) < 0 || v26 == -2147417850 )
      {
        v51 = 0;
        string = 0;
        v28 = WindowsCreateStringReference(
                L"Windows.Graphics.Internal.Printing.PrintScanBroker.PrintScanBrokerHandler",
                0x49u,
                &hstringHeader,
                &string);
        if ( v28 < 0 )
        {
          Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v28, v29, v30);
          JUMPOUT(0x14006D346LL);
        }
        v31 = RoActivateInstance(string, &v51);
        v27 = v31;
        if ( v31 < 0 )
        {
          PrvSpoolssTelemetry::WriteDbgTraceError(
            "FindFirstPrinterChangeNotificationWorker",
            L"RoActivateInstance for PrintScanBrokerHandler failed. Error hr: 0x%x",
            (unsigned int)v31);
        }
        else
        {
          v50 = 0;
          v32 = (**(__int64 (__fastcall ***)(__int64, GUID *, __int64 *))v51)(
                  v51,
                  &GUID_42964634_70ff_4d1c_8ea0_520607b4c1c3,
                  &v50);
          v27 = v32;
          if ( v32 < 0 )
          {
            PrvSpoolssTelemetry::WriteDbgTraceError(
              "FindFirstPrinterChangeNotificationWorker",
              L"QueryTo IPrintScanBrokerHandler failed. Error hr: 0x%x",
              (unsigned int)v32);
          }
          else
          {
            v33 = *((_QWORD *)a1 + 3);
            v53 = 0;
            v34 = (*(__int64 (__fastcall **)(__int64, _QWORD, _QWORD, void **))(*(_QWORD *)v50 + 88LL))(
                    v50,
                    dwProcessId,
                    *(_QWORD *)(v33 + 96),
                    &v53);
            v27 = v34;
            if ( v34 < 0 )
            {
              PrvSpoolssTelemetry::WriteDbgTraceError(
                "FindFirstPrinterChangeNotificationWorker",
                L"DuplicateHandleToCaller failed. Error hr: 0x%x",
                (unsigned int)v34);
            }
            else
            {
              v20 = 1;
              *lpTargetHandle = v53;
            }
          }
          sandbox::DriverConfigModuleAdapter::~DriverConfigModuleAdapter((sandbox::DriverConfigModuleAdapter *)&v50);
        }
        sandbox::DriverConfigModuleAdapter::~DriverConfigModuleAdapter((sandbox::DriverConfigModuleAdapter *)&v51);
        if ( v26 >= 0 )
          CoUninitialize();
      }
      else
      {
        v27 = v26;
        PrvSpoolssTelemetry::WriteDbgTraceError(
          "FindFirstPrinterChangeNotificationWorker",
          L"CoInitializeEx failed. Error hr: 0x%x",
          (unsigned int)v26);
      }
      SetLastError(v27);
      if ( !v20 )
        goto LABEL_38;
LABEL_61:
      v46 = SetupReplyNotification(*((struct _CHANGE **)a1 + 3), v52, v17, v8, v54);
      if ( v46 )
      {
        *(_DWORD *)(*((_QWORD *)a1 + 3) + 12LL) &= ~1u;
        *(_DWORD *)(*((_QWORD *)a1 + 3) + 12LL) |= 0x202u;
LABEL_70:
        LeaveCriticalSection(&RouterNotifySection);
        return v46;
      }
      v19 = L"Failed to set up reply notification.  Error %d.";
LABEL_64:
      v47 = GetLastError();
      PrvSpoolssTelemetry::WriteDbgTraceError("FindFirstPrinterChangeNotificationWorker", v19, v47);
      v48 = *(void **)(*((_QWORD *)a1 + 3) + 96LL);
      if ( v48 )
        CloseHandle(v48);
      if ( !a7 )
      {
        if ( *lpTargetHandle )
          CloseHandle(*lpTargetHandle);
      }
      FailChange(a1);
      v46 = 0;
      goto LABEL_70;
    }
    v35 = OpenProcess(0x40u, 0, dwProcessId);
    if ( !v35 )
    {
      v19 = L"Failed to open process handle.  Error %d.";
      goto LABEL_64;
    }
    if ( !(unsigned int)IsWindowsProtectedPrintSpoolerWorkerEnabled() )
    {
      v44 = *(void **)(*((_QWORD *)a1 + 3) + 96LL);
      v45 = GetCurrentProcess();
      v20 = DuplicateHandle(v45, v44, v35, lpTargetHandle, 0, 1, 2u);
      goto LABEL_59;
    }
    v36 = CoInitializeEx(0, 0);
    if ( (int)(v36 + 0x80000000) >= 0 && v36 != -2147417850 )
    {
      PrvSpoolssTelemetry::WriteDbgTraceError(
        "FindFirstPrinterChangeNotificationWorker",
        L"CoInitializeEx failed. Error hr: 0x%x",
        (unsigned int)v36);
      SetLastError((unsigned __int16)v36);
      goto LABEL_59;
    }
    v50 = 0;
    string = 0;
    v37 = WindowsCreateStringReference(
            L"Windows.Graphics.Internal.Printing.PrintScanBroker.PrintScanBrokerHandler",
            0x49u,
            &hstringHeader,
            &string);
    if ( v37 < 0 )
    {
      Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v37, v38, v39);
      __debugbreak();
    }
    v40 = RoActivateInstance(string, &v50);
    v41 = v40;
    if ( v40 < 0 )
    {
      PrvSpoolssTelemetry::WriteDbgTraceError(
        "FindFirstPrinterChangeNotificationWorker",
        L"RoActivateInstance for PrintScanBrokerHandler failed. Error hr: 0x%x",
        (unsigned int)v40);
      SetLastError(v41);
      goto LABEL_55;
    }
    v51 = 0;
    v42 = (**(__int64 (__fastcall ***)(__int64, GUID *, __int64 *))v50)(
            v50,
            &GUID_42964634_70ff_4d1c_8ea0_520607b4c1c3,
            &v51);
    if ( v42 < 0 )
    {
      PrvSpoolssTelemetry::WriteDbgTraceError(
        "FindFirstPrinterChangeNotificationWorker",
        L"QueryTo IPrintScanBrokerHandler failed. Error hr: 0x%x",
        (unsigned int)v42);
    }
    else
    {
      v43 = *((_QWORD *)a1 + 3);
      v53 = 0;
      v42 = (*(__int64 (__fastcall **)(__int64, _QWORD, _QWORD, void **))(*(_QWORD *)v51 + 88LL))(
              v51,
              dwProcessId,
              *(_QWORD *)(v43 + 96),
              &v53);
      if ( v42 >= 0 )
      {
        v20 = 1;
        *lpTargetHandle = v53;
LABEL_53:
        sandbox::DriverConfigModuleAdapter::~DriverConfigModuleAdapter((sandbox::DriverConfigModuleAdapter *)&v51);
LABEL_55:
        if ( v36 >= 0 )
          CoUninitialize();
        sandbox::DriverConfigModuleAdapter::~DriverConfigModuleAdapter((sandbox::DriverConfigModuleAdapter *)&v50);
LABEL_59:
        CloseHandle(v35);
        if ( v20 )
        {
          v8 = v55;
          goto LABEL_61;
        }
LABEL_38:
        v19 = L"Failed to duplicate handle.  Error %d.";
        goto LABEL_64;
      }
      PrvSpoolssTelemetry::WriteDbgTraceError(
        "FindFirstPrinterChangeNotificationWorker",
        L"DuplicateHandleToCaller failed. Error hr: 0x%x",
        (unsigned int)v42);
    }
    SetLastError((unsigned __int16)v42);
    goto LABEL_53;
  }
  LeaveCriticalSection(&RouterNotifySection);
  return 0;
}

```

## disassembly

```asm
0x14006cc88  mov     [rsp-8+arg_8], rbx
0x14006cc8d  push    rbp
0x14006cc8e  push    rsi
0x14006cc8f  push    rdi
0x14006cc90  push    r12
0x14006cc92  push    r13
0x14006cc94  push    r14
0x14006cc96  push    r15
0x14006cc98  lea     rbp, [rsp-7]
0x14006cc9d  sub     rsp, 0B0h
0x14006cca4  mov     rax, cs:__security_cookie
0x14006ccab  xor     rax, rsp
0x14006ccae  mov     [rbp+37h+var_40], rax
0x14006ccb2  mov     r12, [rbp+37h+arg_20]
0x14006ccb6  xor     eax, eax
0x14006ccb8  mov     r15, [rbp+37h+lpTargetHandle]
0x14006ccbc  mov     r13d, r9d
0x14006ccbf  mov     r14, [rbp+37h+arg_38]
0x14006ccc3  mov     ebx, r8d
0x14006ccc6  mov     [rbp+37h+var_68], r12
0x14006ccca  mov     esi, edx
0x14006cccc  mov     [rbp+37h+var_80], eax
0x14006cccf  mov     rdi, rcx
0x14006ccd2  mov     [rbp+37h+var_70], rax
0x14006ccd6  test    rcx, rcx
0x14006ccd9  jz      loc_14006D2FC
0x14006ccdf  cmp     dword ptr [rcx], 6060h
0x14006cce5  jnz     loc_14006D2FC
0x14006cceb  lea     rcx, ?RouterNotifySection@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x14006ccf2  call    cs:__imp_EnterCriticalSection
0x14006ccf9  nop     dword ptr [rax+rax+00h]
0x14006ccfe  mov     ecx, cs:?dwRouterUniqueSessionID@@3KA; ulong dwRouterUniqueSessionID
0x14006cd04  xor     r9d, r9d
0x14006cd07  mov     [r15], r9
0x14006cd0a  mov     edx, [rdi+50h]; unsigned int
0x14006cd0d  lea     eax, [rdx+1]
0x14006cd10  test    eax, 0FFFFFFFEh
0x14006cd15  jnz     short loc_14006CD20
0x14006cd17  mov     eax, ecx
0x14006cd19  inc     ecx
0x14006cd1b  mov     [rdi+50h], eax
0x14006cd1e  jmp     short loc_14006CD0A
0x14006cd20  cmp     word ptr cs:?szMachineFullDNSName@@3PAGA, r9w; ushort near * szMachineFullDNSName
0x14006cd28  lea     rax, ?szMachineName@@3PAGA; ushort near * szMachineName
0x14006cd2f  mov     [rsp+0E0h+var_98], r9; struct IRemoteNotifyChannel *
0x14006cd34  lea     r8, ?szMachineFullDNSName@@3PAGA; ushort near * szMachineFullDNSName
0x14006cd3b  mov     [rsp+0E0h+var_A0], r14; void *
0x14006cd40  lea     r9, [rbp+37h+var_80]; unsigned int *
0x14006cd44  cmovz   r8, rax; unsigned __int16 *
0x14006cd48  mov     cs:?dwRouterUniqueSessionID@@3KA, ecx; ulong dwRouterUniqueSessionID
0x14006cd4e  lea     rax, [rbp+37h+var_70]
0x14006cd52  mov     rcx, rdi; struct _PRINTHANDLE *
0x14006cd55  mov     [rsp+0E0h+var_A8], rax; struct _PRINTER_NOTIFY_INIT **
0x14006cd5a  mov     qword ptr [rsp+0E0h+dwOptions], r12; struct _PRINTER_NOTIFY_OPTIONS *
0x14006cd5f  mov     [rsp+0E0h+bInheritHandle], esi; unsigned int
0x14006cd63  mov     [rsp+0E0h+dwDesiredAccess], ebx; unsigned int
0x14006cd67  call    ?SetupChange@@YAHPEAU_PRINTHANDLE@@KPEAGPEAKKKPEAU_PRINTER_NOTIFY_OPTIONS@@PEAPEAU_PRINTER_NOTIFY_INIT@@PEAXPEAUIRemoteNotifyChannel@@@Z; SetupChange(_PRINTHANDLE *,ulong,ushort *,ulong *,ulong,ulong,_PRINTER_NOTIFY_OPTIONS *,_PRINTER_NOTIFY_INIT * *,void *,IRemoteNotifyChannel *)
0x14006cd6c  xor     esi, esi
0x14006cd6e  test    eax, eax
0x14006cd70  jnz     short loc_14006CD8A
0x14006cd72  lea     rcx, ?RouterNotifySection@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x14006cd79  call    cs:__imp_LeaveCriticalSection
0x14006cd80  nop     dword ptr [rax+rax+00h]
0x14006cd85  jmp     loc_14006D30D
0x14006cd8a  mov     rax, [rdi+18h]
0x14006cd8e  test    byte ptr [rax+80h], 1
0x14006cd95  jz      loc_14006D251
0x14006cd9b  xor     r9d, r9d; lpName
0x14006cd9e  xor     r8d, r8d; bInitialState
0x14006cda1  xor     ecx, ecx; lpEventAttributes
0x14006cda3  lea     edx, [r9+1]; bManualReset
0x14006cda7  call    cs:__imp_CreateEventW
0x14006cdae  nop     dword ptr [rax+rax+00h]
0x14006cdb3  mov     rcx, [rdi+18h]
0x14006cdb7  mov     [rcx+60h], rax
0x14006cdbb  mov     rax, [rdi+18h]
0x14006cdbf  mov     rcx, [rax+60h]
0x14006cdc3  test    rcx, rcx
0x14006cdc6  jnz     short loc_14006CDD4
0x14006cdc8  lea     rbx, aFailedToCreate_7; "Failed to create event.  Error %d."
0x14006cdcf  jmp     loc_14006D28B
0x14006cdd4  cmp     [rbp+37h+arg_30], esi
0x14006cdd7  jz      short loc_14006CDE1
0x14006cdd9  mov     [r15], rcx
0x14006cddc  jmp     loc_14006D251
0x14006cde1  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Print_PlatformStabilizationFixes_2026_Wave1@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Print_PlatformStabilizationFixes_2026_Wave1@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Print_PlatformStabilizationFixes_2026_Wave1> `wil::Feature<__WilFeatureTraits_Feature_Print_PlatformStabilizationFixes_2026_Wave1>::GetImpl(void)'::`2'::impl
0x14006cde8  mov     r14d, esi
0x14006cdeb  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Print_PlatformStabilizationFixes_2026_Wave1@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Print_PlatformStabilizationFixes_2026_Wave1>::__private_IsEnabled(void)
0x14006cdf0  xor     edx, edx; bInheritHandle
0x14006cdf2  mov     r8d, r13d; dwProcessId
0x14006cdf5  lea     ecx, [rdx+40h]; dwDesiredAccess
0x14006cdf8  test    al, al
0x14006cdfa  jz      loc_14006D050
0x14006ce00  call    cs:__imp_OpenProcess
0x14006ce07  nop     dword ptr [rax+rax+00h]
0x14006ce0c  mov     rsi, rax
0x14006ce0f  test    rax, rax
0x14006ce12  jz      loc_14006CE9E
0x14006ce18  mov     rcx, [rdi+18h]
0x14006ce1c  mov     rbx, [rcx+60h]
0x14006ce20  call    cs:__imp_GetCurrentProcess
0x14006ce27  nop     dword ptr [rax+rax+00h]
0x14006ce2c  mov     [rsp+0E0h+dwOptions], 2; dwOptions
0x14006ce34  mov     r9, r15; lpTargetHandle
0x14006ce37  mov     rcx, rax; hSourceProcessHandle
0x14006ce3a  mov     [rsp+0E0h+bInheritHandle], 1; bInheritHandle
0x14006ce42  mov     r8, rsi; hTargetProcessHandle
0x14006ce45  mov     [rsp+0E0h+dwDesiredAccess], r14d; dwDesiredAccess
0x14006ce4a  mov     rdx, rbx; hSourceHandle
0x14006ce4d  call    cs:__imp_DuplicateHandle
0x14006ce54  nop     dword ptr [rax+rax+00h]
0x14006ce59  mov     r14d, eax
0x14006ce5c  test    eax, eax
0x14006ce5e  jnz     short loc_14006CE82
0x14006ce60  call    cs:__imp_GetLastError
0x14006ce67  nop     dword ptr [rax+rax+00h]
0x14006ce6c  mov     r8d, eax
0x14006ce6f  lea     rdx, aFailedToDuplic_0; "Failed to duplicate handle directly.  E"...
0x14006ce76  lea     rcx, aFindfirstprint; "FindFirstPrinterChangeNotificationWorke"...
0x14006ce7d  call    ?WriteDbgTraceError@PrvSpoolssTelemetry@@SAXPEADPEAGZZ; PrvSpoolssTelemetry::WriteDbgTraceError(char *,ushort *,...)
0x14006ce82  mov     rcx, rsi; hObject
0x14006ce85  call    cs:__imp_CloseHandle
0x14006ce8c  nop     dword ptr [rax+rax+00h]
0x14006ce91  xor     esi, esi
0x14006ce93  test    r14d, r14d
0x14006ce96  jnz     loc_14006D251
0x14006ce9c  jmp     short loc_14006CEC2
0x14006ce9e  call    cs:__imp_GetLastError
0x14006cea5  nop     dword ptr [rax+rax+00h]
0x14006ceaa  mov     r8d, eax
0x14006cead  lea     rdx, aFailedToOpenPr; "Failed to open process handle.  Error %"...
0x14006ceb4  lea     rcx, aFindfirstprint; "FindFirstPrinterChangeNotificationWorke"...
0x14006cebb  call    ?WriteDbgTraceError@PrvSpoolssTelemetry@@SAXPEADPEAGZZ; PrvSpoolssTelemetry::WriteDbgTraceError(char *,ushort *,...)
0x14006cec0  xor     esi, esi
0x14006cec2  call    ?IsWindowsProtectedPrintEnabled@@YAHXZ; IsWindowsProtectedPrintEnabled(void)
0x14006cec7  test    eax, eax
0x14006cec9  jz      loc_14006D044
0x14006cecf  xor     edx, edx; dwCoInit
0x14006ced1  xor     ecx, ecx; pvReserved
0x14006ced3  call    cs:__imp_CoInitializeEx
0x14006ceda  nop     dword ptr [rax+rax+00h]
0x14006cedf  mov     esi, eax
0x14006cee1  mov     eax, 80000000h
0x14006cee6  lea     ecx, [rsi+rax]
0x14006cee9  test    eax, ecx
0x14006ceeb  jnz     short loc_14006CF12
0x14006ceed  cmp     esi, 80010106h
0x14006cef3  jz      short loc_14006CF12
0x14006cef5  mov     r8d, esi
0x14006cef8  lea     rdx, aCoinitializeex_1; "CoInitializeEx failed. Error hr: 0x%x"
0x14006ceff  lea     rcx, aFindfirstprint; "FindFirstPrinterChangeNotificationWorke"...
0x14006cf06  mov     ebx, esi
0x14006cf08  call    ?WriteDbgTraceError@PrvSpoolssTelemetry@@SAXPEADPEAGZZ; PrvSpoolssTelemetry::WriteDbgTraceError(char *,ushort *,...)
0x14006cf0d  jmp     loc_14006D02A
0x14006cf12  lea     r9, [rbp+37h+string]; string
0x14006cf16  mov     [rbp+37h+var_88], 0
0x14006cf1e  lea     r8, [rbp+37h+hstringHeader]; hstringHeader
0x14006cf22  mov     [rbp+37h+string], 0
0x14006cf2a  mov     edx, 49h ; 'I'; length
0x14006cf2f  lea     rcx, ?RuntimeClass_Windows_Graphics_Internal_Printing_PrintScanBroker_PrintScanBrokerHandler@@3QBGB; "Windows.Graphics.Internal.Printing.Prin"...
0x14006cf36  call    cs:__imp_WindowsCreateStringReference
0x14006cf3d  nop     dword ptr [rax+rax+00h]
0x14006cf42  test    eax, eax
0x14006cf44  js      loc_14006D33F
0x14006cf4a  mov     rcx, [rbp+37h+string]
0x14006cf4e  lea     rdx, [rbp+37h+var_88]
0x14006cf52  call    cs:__imp_RoActivateInstance
0x14006cf59  nop     dword ptr [rax+rax+00h]
0x14006cf5e  mov     ebx, eax
0x14006cf60  test    eax, eax
0x14006cf62  js      loc_14006CFF6
0x14006cf68  mov     rcx, [rbp+37h+var_88]
0x14006cf6c  lea     r8, [rbp+37h+var_90]
0x14006cf70  mov     [rbp+37h+var_90], 0
0x14006cf78  lea     rdx, _GUID_42964634_70ff_4d1c_8ea0_520607b4c1c3
0x14006cf7f  mov     rax, [rcx]
0x14006cf82  mov     rax, [rax]
0x14006cf85  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14006cf8a  mov     ebx, eax
0x14006cf8c  test    eax, eax
0x14006cf8e  js      short loc_14006CFD5
0x14006cf90  mov     rcx, [rbp+37h+var_90]
0x14006cf94  lea     r9, [rbp+37h+var_78]
0x14006cf98  mov     r8, [rdi+18h]
0x14006cf9c  mov     edx, r13d
0x14006cf9f  mov     [rbp+37h+var_78], 0
0x14006cfa7  mov     rax, [rcx]
0x14006cfaa  mov     r8, [r8+60h]
0x14006cfae  mov     rax, [rax+58h]
0x14006cfb2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14006cfb7  mov     ebx, eax
0x14006cfb9  test    eax, eax
0x14006cfbb  js      short loc_14006CFCC
0x14006cfbd  mov     rax, [rbp+37h+var_78]
0x14006cfc1  mov     r14d, 1
0x14006cfc7  mov     [r15], rax
0x14006cfca  jmp     short loc_14006CFEB
0x14006cfcc  lea     rdx, aDuplicatehandl; "DuplicateHandleToCaller failed. Error h"...
0x14006cfd3  jmp     short loc_14006CFDC
0x14006cfd5  lea     rdx, aQuerytoIprints; "QueryTo IPrintScanBrokerHandler failed."...
0x14006cfdc  mov     r8d, eax
0x14006cfdf  lea     rcx, aFindfirstprint; "FindFirstPrinterChangeNotificationWorke"...
0x14006cfe6  call    ?WriteDbgTraceError@PrvSpoolssTelemetry@@SAXPEADPEAGZZ; PrvSpoolssTelemetry::WriteDbgTraceError(char *,ushort *,...)
0x14006cfeb  lea     rcx, [rbp+37h+var_90]; this
0x14006cfef  call    ??1DriverConfigModuleAdapter@sandbox@@QEAA@XZ; sandbox::DriverConfigModuleAdapter::~DriverConfigModuleAdapter(void)
0x14006cff4  jmp     short loc_14006D00C
0x14006cff6  mov     r8d, eax
0x14006cff9  lea     rdx, aRoactivateinst_0; "RoActivateInstance for PrintScanBrokerH"...
0x14006d000  lea     rcx, aFindfirstprint; "FindFirstPrinterChangeNotificationWorke"...
0x14006d007  call    ?WriteDbgTraceError@PrvSpoolssTelemetry@@SAXPEADPEAGZZ; PrvSpoolssTelemetry::WriteDbgTraceError(char *,ushort *,...)
0x14006d00c  lea     rcx, [rbp+37h+var_88]; this
0x14006d010  call    ??1DriverConfigModuleAdapter@sandbox@@QEAA@XZ; sandbox::DriverConfigModuleAdapter::~DriverConfigModuleAdapter(void)
0x14006d015  shr     esi, 1Fh
0x14006d018  xor     sil, 1
0x14006d01c  jz      short loc_14006D02A
0x14006d01e  call    cs:__imp_CoUninitialize
0x14006d025  nop     dword ptr [rax+rax+00h]
0x14006d02a  movzx   ecx, bx; dwErrCode
0x14006d02d  call    cs:__imp_SetLastError
0x14006d034  nop     dword ptr [rax+rax+00h]
0x14006d039  xor     esi, esi
0x14006d03b  test    r14d, r14d
0x14006d03e  jnz     loc_14006D251
0x14006d044  lea     rbx, aFailedToDuplic; "Failed to duplicate handle.  Error %d."
0x14006d04b  jmp     loc_14006D28B
0x14006d050  call    cs:__imp_OpenProcess
0x14006d057  nop     dword ptr [rax+rax+00h]
0x14006d05c  mov     r12, rax
0x14006d05f  test    rax, rax
0x14006d062  jnz     short loc_14006D070
0x14006d064  lea     rbx, aFailedToOpenPr; "Failed to open process handle.  Error %"...
0x14006d06b  jmp     loc_14006D28B
0x14006d070  call    ?IsWindowsProtectedPrintSpoolerWorkerEnabled@@YAHXZ; IsWindowsProtectedPrintSpoolerWorkerEnabled(void)
0x14006d075  test    eax, eax
0x14006d077  jz      loc_14006D1F2
0x14006d07d  xor     edx, edx; dwCoInit
0x14006d07f  xor     ecx, ecx; pvReserved
0x14006d081  call    cs:__imp_CoInitializeEx
0x14006d088  nop     dword ptr [rax+rax+00h]
0x14006d08d  mov     ebx, eax
0x14006d08f  mov     eax, 80000000h
0x14006d094  lea     ecx, [rbx+rax]
0x14006d097  test    eax, ecx
0x14006d099  jnz     short loc_14006D0CD
0x14006d09b  cmp     ebx, 80010106h
0x14006d0a1  jz      short loc_14006D0CD
0x14006d0a3  mov     r8d, ebx
0x14006d0a6  lea     rdx, aCoinitializeex_1; "CoInitializeEx failed. Error hr: 0x%x"
0x14006d0ad  lea     rcx, aFindfirstprint; "FindFirstPrinterChangeNotificationWorke"...
0x14006d0b4  call    ?WriteDbgTraceError@PrvSpoolssTelemetry@@SAXPEADPEAGZZ; PrvSpoolssTelemetry::WriteDbgTraceError(char *,ushort *,...)
0x14006d0b9  movzx   ecx, bx; dwErrCode
0x14006d0bc  call    cs:__imp_SetLastError
0x14006d0c3  nop     dword ptr [rax+rax+00h]
0x14006d0c8  jmp     loc_14006D235
0x14006d0cd  lea     r9, [rbp+37h+string]; string
0x14006d0d1  mov     [rbp+37h+var_90], rsi
0x14006d0d5  lea     r8, [rbp+37h+hstringHeader]; hstringHeader
0x14006d0d9  mov     [rbp+37h+string], rsi
0x14006d0dd  mov     edx, 49h ; 'I'; length
0x14006d0e2  lea     rcx, ?RuntimeClass_Windows_Graphics_Internal_Printing_PrintScanBroker_PrintScanBrokerHandler@@3QBGB; "Windows.Graphics.Internal.Printing.Prin"...
0x14006d0e9  call    cs:__imp_WindowsCreateStringReference
0x14006d0f0  nop     dword ptr [rax+rax+00h]
0x14006d0f5  test    eax, eax
0x14006d0f7  js      loc_14006D337
0x14006d0fd  mov     rcx, [rbp+37h+string]
0x14006d101  lea     rdx, [rbp+37h+var_90]
0x14006d105  call    cs:__imp_RoActivateInstance
0x14006d10c  nop     dword ptr [rax+rax+00h]
0x14006d111  mov     esi, eax
0x14006d113  test    eax, eax
0x14006d115  js      loc_14006D1B0
0x14006d11b  mov     rcx, [rbp+37h+var_90]
0x14006d11f  lea     r8, [rbp+37h+var_88]
0x14006d123  mov     [rbp+37h+var_88], r14
0x14006d127  lea     rdx, _GUID_42964634_70ff_4d1c_8ea0_520607b4c1c3
0x14006d12e  mov     rax, [rcx]
0x14006d131  mov     rax, [rax]
0x14006d134  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14006d139  mov     esi, eax
0x14006d13b  test    eax, eax
0x14006d13d  js      short loc_14006D180
0x14006d13f  mov     rcx, [rbp+37h+var_88]
0x14006d143  lea     r9, [rbp+37h+var_78]
0x14006d147  mov     r8, [rdi+18h]
0x14006d14b  mov     edx, r13d
0x14006d14e  mov     [rbp+37h+var_78], r14
0x14006d152  mov     rax, [rcx]
0x14006d155  mov     r8, [r8+60h]
0x14006d159  mov     rax, [rax+58h]
0x14006d15d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14006d162  mov     esi, eax
0x14006d164  test    eax, eax
0x14006d166  js      short loc_14006D177
0x14006d168  mov     rax, [rbp+37h+var_78]
0x14006d16c  mov     r14d, 1
0x14006d172  mov     [r15], rax
0x14006d175  jmp     short loc_14006D1A5
0x14006d177  lea     rdx, aDuplicatehandl; "DuplicateHandleToCaller failed. Error h"...
0x14006d17e  jmp     short loc_14006D187
0x14006d180  lea     rdx, aQuerytoIprints; "QueryTo IPrintScanBrokerHandler failed."...
  ... truncated ...
```
