# FindFirstPrinterChangeNotificationWorker(void *,ulong,ulong,ulong,_PRINTER_NOTIFY_OPTIONS *,void * *,int,void *)

- ea: `0x14006669c`
- end: `0x140066ca2`
- name: `?FindFirstPrinterChangeNotificationWorker@@YAHPEAXKKKPEAU_PRINTER_NOTIFY_OPTIONS@@PEAPEAXH0@Z`
- size: `1542`
- prototype: `__int64 __fastcall(struct _PRINTHANDLE *, unsigned int, unsigned int, DWORD dwProcessId, struct _PRINTER_NOTIFY_OPTIONS *, LPHANDLE lpTargetHandle, int, void *)`
- caller_count: `3`
- callee_count: `12`
- tags: `authz_impersonation, registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x140050070`
- `0x1400677b0`
- `0x140067800`

## callees

- `0x1400140cc`
- `0x140017ae0`
- `0x14002abc0`
- `0x14003cd0c`
- `0x140047ad8`
- `0x1400590f0`
- `0x140059114`
- `0x140066508`
- `0x14006669c`
- `0x140067258`
- `0x1400673fc`
- `0x14007a010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x140066787`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x140066c54`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x140066787`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x140066c54`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1400667af`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1400667af`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x140066706`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x140066706`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14006684c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14006687e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140066c05`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14006684c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14006687e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140066c05`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1400669ef`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140066a6c`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140066b37`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140066b61`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140066c63`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1400669ef`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140066a6c`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140066b37`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140066b61`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140066c63`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x140066818`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x140066b86`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x140066818`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x140066b86`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x14006683f`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x140066bac`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x14006683f`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x140066bac`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14006686b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140066bb8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140066c2a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140066c3d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14006686b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140066bb8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140066c2a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140066c3d`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x140066802`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x140066a0c`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x140066802`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x140066a0c`
- `api-ms-win-core-winrt-l1-1-0!RoActivateInstance` at `0x140066920`
- `api-ms-win-core-winrt-l1-1-0!RoActivateInstance` at `0x140066aa9`
- `api-ms-win-core-winrt-l1-1-0!RoActivateInstance` at `0x140066920`
- `api-ms-win-core-winrt-l1-1-0!RoActivateInstance` at `0x140066aa9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x14006690a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x140066a93`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x14006690a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x140066a93`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x1400669e6`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x140066b6d`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x1400669e6`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x140066b6d`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x1400668ad`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x140066a37`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x1400668ad`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x140066a37`

## string_xrefs

- `0x140066903`: `Windows.Graphics.Internal.Printing.PrintScanBroker.PrintScanBrokerHandler`
- `0x140066a8c`: `Windows.Graphics.Internal.Printing.PrintScanBroker.PrintScanBrokerHandler`
- `0x1400667ca`: `Failed to create event.  Error %d.`
- `0x14006699d`: `QueryTo IPrintScanBrokerHandler failed. Error hr: 0x%x`
- `0x140066b1e`: `QueryTo IPrintScanBrokerHandler failed. Error hr: 0x%x`
- `0x140066887`: `Failed to open process handle.  Error %d.`
- `0x140066a1a`: `Failed to open process handle.  Error %d.`
- `0x1400669c1`: `RoActivateInstance for PrintScanBrokerHandler failed. Error hr: 0x%x`
- `0x140066b4b`: `RoActivateInstance for PrintScanBrokerHandler failed. Error hr: 0x%x`

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
          JUMPOUT(0x140066CA1LL);
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
0x14006669c  mov     [rsp-8+arg_8], rbx
0x1400666a1  push    rbp
0x1400666a2  push    rsi
0x1400666a3  push    rdi
0x1400666a4  push    r12
0x1400666a6  push    r13
0x1400666a8  push    r14
0x1400666aa  push    r15
0x1400666ac  lea     rbp, [rsp-7]
0x1400666b1  sub     rsp, 0B0h
0x1400666b8  mov     rax, cs:__security_cookie
0x1400666bf  xor     rax, rsp
0x1400666c2  mov     [rbp+37h+var_40], rax
0x1400666c6  mov     r12, [rbp+37h+arg_20]
0x1400666ca  xor     eax, eax
0x1400666cc  mov     r15, [rbp+37h+lpTargetHandle]
0x1400666d0  mov     r13d, r9d
0x1400666d3  mov     r14, [rbp+37h+arg_38]
0x1400666d7  mov     ebx, r8d
0x1400666da  mov     [rbp+37h+var_68], r12
0x1400666de  mov     esi, edx
0x1400666e0  mov     [rbp+37h+var_80], eax
0x1400666e3  mov     rdi, rcx
0x1400666e6  mov     [rbp+37h+var_70], rax
0x1400666ea  test    rcx, rcx
0x1400666ed  jz      loc_140066C5E
0x1400666f3  cmp     dword ptr [rcx], 6060h
0x1400666f9  jnz     loc_140066C5E
0x1400666ff  lea     rcx, ?RouterNotifySection@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x140066706  call    cs:__imp_EnterCriticalSection
0x14006670c  mov     ecx, cs:?dwRouterUniqueSessionID@@3KA; ulong dwRouterUniqueSessionID
0x140066712  xor     r9d, r9d
0x140066715  mov     [r15], r9
0x140066718  mov     edx, [rdi+50h]; unsigned int
0x14006671b  lea     eax, [rdx+1]
0x14006671e  test    eax, 0FFFFFFFEh
0x140066723  jnz     short loc_14006672E
0x140066725  mov     eax, ecx
0x140066727  inc     ecx
0x140066729  mov     [rdi+50h], eax
0x14006672c  jmp     short loc_140066718
0x14006672e  cmp     word ptr cs:?szMachineFullDNSName@@3PAGA, r9w; ushort near * szMachineFullDNSName
0x140066736  lea     rax, ?szMachineName@@3PAGA; ushort near * szMachineName
0x14006673d  mov     [rsp+0E0h+var_98], r9; struct IRemoteNotifyChannel *
0x140066742  lea     r8, ?szMachineFullDNSName@@3PAGA; ushort near * szMachineFullDNSName
0x140066749  mov     [rsp+0E0h+var_A0], r14; void *
0x14006674e  lea     r9, [rbp+37h+var_80]; unsigned int *
0x140066752  cmovz   r8, rax; unsigned __int16 *
0x140066756  mov     cs:?dwRouterUniqueSessionID@@3KA, ecx; ulong dwRouterUniqueSessionID
0x14006675c  lea     rax, [rbp+37h+var_70]
0x140066760  mov     rcx, rdi; struct _PRINTHANDLE *
0x140066763  mov     [rsp+0E0h+var_A8], rax; struct _PRINTER_NOTIFY_INIT **
0x140066768  mov     qword ptr [rsp+0E0h+dwOptions], r12; struct _PRINTER_NOTIFY_OPTIONS *
0x14006676d  mov     [rsp+0E0h+bInheritHandle], esi; unsigned int
0x140066771  mov     [rsp+0E0h+dwDesiredAccess], ebx; unsigned int
0x140066775  call    ?SetupChange@@YAHPEAU_PRINTHANDLE@@KPEAGPEAKKKPEAU_PRINTER_NOTIFY_OPTIONS@@PEAPEAU_PRINTER_NOTIFY_INIT@@PEAXPEAUIRemoteNotifyChannel@@@Z; SetupChange(_PRINTHANDLE *,ulong,ushort *,ulong *,ulong,ulong,_PRINTER_NOTIFY_OPTIONS *,_PRINTER_NOTIFY_INIT * *,void *,IRemoteNotifyChannel *)
0x14006677a  xor     esi, esi
0x14006677c  test    eax, eax
0x14006677e  jnz     short loc_140066792
0x140066780  lea     rcx, ?RouterNotifySection@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x140066787  call    cs:__imp_LeaveCriticalSection
0x14006678d  jmp     loc_140066C69
0x140066792  mov     rax, [rdi+18h]
0x140066796  test    byte ptr [rax+80h], 1
0x14006679d  jz      loc_140066BCB
0x1400667a3  xor     r9d, r9d; lpName
0x1400667a6  xor     r8d, r8d; bInitialState
0x1400667a9  xor     ecx, ecx; lpEventAttributes
0x1400667ab  lea     edx, [r9+1]; bManualReset
0x1400667af  call    cs:__imp_CreateEventW
0x1400667b5  mov     rcx, [rdi+18h]
0x1400667b9  mov     [rcx+60h], rax
0x1400667bd  mov     rax, [rdi+18h]
0x1400667c1  mov     rcx, [rax+60h]
0x1400667c5  test    rcx, rcx
0x1400667c8  jnz     short loc_1400667D6
0x1400667ca  lea     rbx, aFailedToCreate_7; "Failed to create event.  Error %d."
0x1400667d1  jmp     loc_140066C05
0x1400667d6  cmp     [rbp+37h+arg_30], esi
0x1400667d9  jz      short loc_1400667E3
0x1400667db  mov     [r15], rcx
0x1400667de  jmp     loc_140066BCB
0x1400667e3  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Print_PlatformStabilizationFixes_2026_Wave1@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Print_PlatformStabilizationFixes_2026_Wave1@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Print_PlatformStabilizationFixes_2026_Wave1> `wil::Feature<__WilFeatureTraits_Feature_Print_PlatformStabilizationFixes_2026_Wave1>::GetImpl(void)'::`2'::impl
0x1400667ea  mov     r14d, esi
0x1400667ed  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Print_PlatformStabilizationFixes_2026_Wave1@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Print_PlatformStabilizationFixes_2026_Wave1>::__private_IsEnabled(void)
0x1400667f2  xor     edx, edx; bInheritHandle
0x1400667f4  mov     r8d, r13d; dwProcessId
0x1400667f7  lea     ecx, [rdx+40h]; dwDesiredAccess
0x1400667fa  test    al, al
0x1400667fc  jz      loc_140066A0C
0x140066802  call    cs:__imp_OpenProcess
0x140066808  mov     rsi, rax
0x14006680b  test    rax, rax
0x14006680e  jz      short loc_14006687E
0x140066810  mov     rcx, [rdi+18h]
0x140066814  mov     rbx, [rcx+60h]
0x140066818  call    cs:__imp_GetCurrentProcess
0x14006681e  mov     [rsp+0E0h+dwOptions], 2; dwOptions
0x140066826  mov     r9, r15; lpTargetHandle
0x140066829  mov     rcx, rax; hSourceProcessHandle
0x14006682c  mov     [rsp+0E0h+bInheritHandle], 1; bInheritHandle
0x140066834  mov     r8, rsi; hTargetProcessHandle
0x140066837  mov     [rsp+0E0h+dwDesiredAccess], r14d; dwDesiredAccess
0x14006683c  mov     rdx, rbx; hSourceHandle
0x14006683f  call    cs:__imp_DuplicateHandle
0x140066845  mov     r14d, eax
0x140066848  test    eax, eax
0x14006684a  jnz     short loc_140066868
0x14006684c  call    cs:__imp_GetLastError
0x140066852  mov     r8d, eax
0x140066855  lea     rdx, aFailedToDuplic_0; "Failed to duplicate handle directly.  E"...
0x14006685c  lea     rcx, aFindfirstprint; "FindFirstPrinterChangeNotificationWorke"...
0x140066863  call    ?WriteDbgTraceError@PrvSpoolssTelemetry@@SAXPEADPEAGZZ; PrvSpoolssTelemetry::WriteDbgTraceError(char *,ushort *,...)
0x140066868  mov     rcx, rsi; hObject
0x14006686b  call    cs:__imp_CloseHandle
0x140066871  xor     esi, esi
0x140066873  test    r14d, r14d
0x140066876  jnz     loc_140066BCB
0x14006687c  jmp     short loc_14006689C
0x14006687e  call    cs:__imp_GetLastError
0x140066884  mov     r8d, eax
0x140066887  lea     rdx, aFailedToOpenPr; "Failed to open process handle.  Error %"...
0x14006688e  lea     rcx, aFindfirstprint; "FindFirstPrinterChangeNotificationWorke"...
0x140066895  call    ?WriteDbgTraceError@PrvSpoolssTelemetry@@SAXPEADPEAGZZ; PrvSpoolssTelemetry::WriteDbgTraceError(char *,ushort *,...)
0x14006689a  xor     esi, esi
0x14006689c  call    ?IsWindowsProtectedPrintEnabled@@YAHXZ; IsWindowsProtectedPrintEnabled(void)
0x1400668a1  test    eax, eax
0x1400668a3  jz      loc_140066A00
0x1400668a9  xor     edx, edx; dwCoInit
0x1400668ab  xor     ecx, ecx; pvReserved
0x1400668ad  call    cs:__imp_CoInitializeEx
0x1400668b3  mov     esi, eax
0x1400668b5  mov     eax, 80000000h
0x1400668ba  lea     ecx, [rsi+rax]
0x1400668bd  test    eax, ecx
0x1400668bf  jnz     short loc_1400668E6
0x1400668c1  cmp     esi, 80010106h
0x1400668c7  jz      short loc_1400668E6
0x1400668c9  mov     r8d, esi
0x1400668cc  lea     rdx, aCoinitializeex_1; "CoInitializeEx failed. Error hr: 0x%x"
0x1400668d3  lea     rcx, aFindfirstprint; "FindFirstPrinterChangeNotificationWorke"...
0x1400668da  mov     ebx, esi
0x1400668dc  call    ?WriteDbgTraceError@PrvSpoolssTelemetry@@SAXPEADPEAGZZ; PrvSpoolssTelemetry::WriteDbgTraceError(char *,ushort *,...)
0x1400668e1  jmp     loc_1400669EC
0x1400668e6  lea     r9, [rbp+37h+string]; string
0x1400668ea  mov     [rbp+37h+var_88], 0
0x1400668f2  lea     r8, [rbp+37h+hstringHeader]; hstringHeader
0x1400668f6  mov     [rbp+37h+string], 0
0x1400668fe  mov     edx, 49h ; 'I'; length
0x140066903  lea     rcx, ?RuntimeClass_Windows_Graphics_Internal_Printing_PrintScanBroker_PrintScanBrokerHandler@@3QBGB; "Windows.Graphics.Internal.Printing.Prin"...
0x14006690a  call    cs:__imp_WindowsCreateStringReference
0x140066910  test    eax, eax
0x140066912  js      loc_140066C9A
0x140066918  mov     rcx, [rbp+37h+string]
0x14006691c  lea     rdx, [rbp+37h+var_88]
0x140066920  call    cs:__imp_RoActivateInstance
0x140066926  mov     ebx, eax
0x140066928  test    eax, eax
0x14006692a  js      loc_1400669BE
0x140066930  mov     rcx, [rbp+37h+var_88]
0x140066934  lea     r8, [rbp+37h+var_90]
0x140066938  mov     [rbp+37h+var_90], 0
0x140066940  lea     rdx, _GUID_42964634_70ff_4d1c_8ea0_520607b4c1c3
0x140066947  mov     rax, [rcx]
0x14006694a  mov     rax, [rax]
0x14006694d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140066952  mov     ebx, eax
0x140066954  test    eax, eax
0x140066956  js      short loc_14006699D
0x140066958  mov     rcx, [rbp+37h+var_90]
0x14006695c  lea     r9, [rbp+37h+var_78]
0x140066960  mov     r8, [rdi+18h]
0x140066964  mov     edx, r13d
0x140066967  mov     [rbp+37h+var_78], 0
0x14006696f  mov     rax, [rcx]
0x140066972  mov     r8, [r8+60h]
0x140066976  mov     rax, [rax+58h]
0x14006697a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14006697f  mov     ebx, eax
0x140066981  test    eax, eax
0x140066983  js      short loc_140066994
0x140066985  mov     rax, [rbp+37h+var_78]
0x140066989  mov     r14d, 1
0x14006698f  mov     [r15], rax
0x140066992  jmp     short loc_1400669B3
0x140066994  lea     rdx, aDuplicatehandl; "DuplicateHandleToCaller failed. Error h"...
0x14006699b  jmp     short loc_1400669A4
0x14006699d  lea     rdx, aQuerytoIprints; "QueryTo IPrintScanBrokerHandler failed."...
0x1400669a4  mov     r8d, eax
0x1400669a7  lea     rcx, aFindfirstprint; "FindFirstPrinterChangeNotificationWorke"...
0x1400669ae  call    ?WriteDbgTraceError@PrvSpoolssTelemetry@@SAXPEADPEAGZZ; PrvSpoolssTelemetry::WriteDbgTraceError(char *,ushort *,...)
0x1400669b3  lea     rcx, [rbp+37h+var_90]; this
0x1400669b7  call    ??1DriverConfigModuleAdapter@sandbox@@QEAA@XZ; sandbox::DriverConfigModuleAdapter::~DriverConfigModuleAdapter(void)
0x1400669bc  jmp     short loc_1400669D4
0x1400669be  mov     r8d, eax
0x1400669c1  lea     rdx, aRoactivateinst_0; "RoActivateInstance for PrintScanBrokerH"...
0x1400669c8  lea     rcx, aFindfirstprint; "FindFirstPrinterChangeNotificationWorke"...
0x1400669cf  call    ?WriteDbgTraceError@PrvSpoolssTelemetry@@SAXPEADPEAGZZ; PrvSpoolssTelemetry::WriteDbgTraceError(char *,ushort *,...)
0x1400669d4  lea     rcx, [rbp+37h+var_88]; this
0x1400669d8  call    ??1DriverConfigModuleAdapter@sandbox@@QEAA@XZ; sandbox::DriverConfigModuleAdapter::~DriverConfigModuleAdapter(void)
0x1400669dd  shr     esi, 1Fh
0x1400669e0  xor     sil, 1
0x1400669e4  jz      short loc_1400669EC
0x1400669e6  call    cs:__imp_CoUninitialize
0x1400669ec  movzx   ecx, bx; dwErrCode
0x1400669ef  call    cs:__imp_SetLastError
0x1400669f5  xor     esi, esi
0x1400669f7  test    r14d, r14d
0x1400669fa  jnz     loc_140066BCB
0x140066a00  lea     rbx, aFailedToDuplic; "Failed to duplicate handle.  Error %d."
0x140066a07  jmp     loc_140066C05
0x140066a0c  call    cs:__imp_OpenProcess
0x140066a12  mov     r12, rax
0x140066a15  test    rax, rax
0x140066a18  jnz     short loc_140066A26
0x140066a1a  lea     rbx, aFailedToOpenPr; "Failed to open process handle.  Error %"...
0x140066a21  jmp     loc_140066C05
0x140066a26  call    ?IsWindowsProtectedPrintSpoolerWorkerEnabled@@YAHXZ; IsWindowsProtectedPrintSpoolerWorkerEnabled(void)
0x140066a2b  test    eax, eax
0x140066a2d  jz      loc_140066B7E
0x140066a33  xor     edx, edx; dwCoInit
0x140066a35  xor     ecx, ecx; pvReserved
0x140066a37  call    cs:__imp_CoInitializeEx
0x140066a3d  mov     ebx, eax
0x140066a3f  mov     eax, 80000000h
0x140066a44  lea     ecx, [rbx+rax]
0x140066a47  test    eax, ecx
0x140066a49  jnz     short loc_140066A77
0x140066a4b  cmp     ebx, 80010106h
0x140066a51  jz      short loc_140066A77
0x140066a53  mov     r8d, ebx
0x140066a56  lea     rdx, aCoinitializeex_1; "CoInitializeEx failed. Error hr: 0x%x"
0x140066a5d  lea     rcx, aFindfirstprint; "FindFirstPrinterChangeNotificationWorke"...
0x140066a64  call    ?WriteDbgTraceError@PrvSpoolssTelemetry@@SAXPEADPEAGZZ; PrvSpoolssTelemetry::WriteDbgTraceError(char *,ushort *,...)
0x140066a69  movzx   ecx, bx; dwErrCode
0x140066a6c  call    cs:__imp_SetLastError
0x140066a72  jmp     loc_140066BB5
0x140066a77  lea     r9, [rbp+37h+string]; string
0x140066a7b  mov     [rbp+37h+var_90], rsi
0x140066a7f  lea     r8, [rbp+37h+hstringHeader]; hstringHeader
0x140066a83  mov     [rbp+37h+string], rsi
0x140066a87  mov     edx, 49h ; 'I'; length
0x140066a8c  lea     rcx, ?RuntimeClass_Windows_Graphics_Internal_Printing_PrintScanBroker_PrintScanBrokerHandler@@3QBGB; "Windows.Graphics.Internal.Printing.Prin"...
0x140066a93  call    cs:__imp_WindowsCreateStringReference
0x140066a99  test    eax, eax
0x140066a9b  js      loc_140066C92
0x140066aa1  mov     rcx, [rbp+37h+string]
0x140066aa5  lea     rdx, [rbp+37h+var_90]
0x140066aa9  call    cs:__imp_RoActivateInstance
0x140066aaf  mov     esi, eax
0x140066ab1  test    eax, eax
0x140066ab3  js      loc_140066B48
0x140066ab9  mov     rcx, [rbp+37h+var_90]
0x140066abd  lea     r8, [rbp+37h+var_88]
0x140066ac1  mov     [rbp+37h+var_88], r14
0x140066ac5  lea     rdx, _GUID_42964634_70ff_4d1c_8ea0_520607b4c1c3
0x140066acc  mov     rax, [rcx]
0x140066acf  mov     rax, [rax]
0x140066ad2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140066ad7  mov     esi, eax
0x140066ad9  test    eax, eax
0x140066adb  js      short loc_140066B1E
0x140066add  mov     rcx, [rbp+37h+var_88]
0x140066ae1  lea     r9, [rbp+37h+var_78]
0x140066ae5  mov     r8, [rdi+18h]
0x140066ae9  mov     edx, r13d
0x140066aec  mov     [rbp+37h+var_78], r14
0x140066af0  mov     rax, [rcx]
0x140066af3  mov     r8, [r8+60h]
0x140066af7  mov     rax, [rax+58h]
0x140066afb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140066b00  mov     esi, eax
0x140066b02  test    eax, eax
0x140066b04  js      short loc_140066B15
0x140066b06  mov     rax, [rbp+37h+var_78]
0x140066b0a  mov     r14d, 1
0x140066b10  mov     [r15], rax
0x140066b13  jmp     short loc_140066B3D
0x140066b15  lea     rdx, aDuplicatehandl; "DuplicateHandleToCaller failed. Error h"...
0x140066b1c  jmp     short loc_140066B25
0x140066b1e  lea     rdx, aQuerytoIprints; "QueryTo IPrintScanBrokerHandler failed."...
0x140066b25  mov     r8d, esi
0x140066b28  lea     rcx, aFindfirstprint; "FindFirstPrinterChangeNotificationWorke"...
0x140066b2f  call    ?WriteDbgTraceError@PrvSpoolssTelemetry@@SAXPEADPEAGZZ; PrvSpoolssTelemetry::WriteDbgTraceError(char *,ushort *,...)
0x140066b34  movzx   ecx, si; dwErrCode
0x140066b37  call    cs:__imp_SetLastError
0x140066b3d  lea     rcx, [rbp+37h+var_88]; this
0x140066b41  call    ??1DriverConfigModuleAdapter@sandbox@@QEAA@XZ; sandbox::DriverConfigModuleAdapter::~DriverConfigModuleAdapter(void)
0x140066b46  jmp     short loc_140066B67
0x140066b48  mov     r8d, esi
0x140066b4b  lea     rdx, aRoactivateinst_0; "RoActivateInstance for PrintScanBrokerH"...
0x140066b52  lea     rcx, aFindfirstprint; "FindFirstPrinterChangeNotificationWorke"...
0x140066b59  call    ?WriteDbgTraceError@PrvSpoolssTelemetry@@SAXPEADPEAGZZ; PrvSpoolssTelemetry::WriteDbgTraceError(char *,ushort *,...)
0x140066b5e  movzx   ecx, si; dwErrCode
0x140066b61  call    cs:__imp_SetLastError
0x140066b67  xor     esi, esi
0x140066b69  test    ebx, ebx
0x140066b6b  js      short loc_140066B73
0x140066b6d  call    cs:__imp_CoUninitialize
0x140066b73  lea     rcx, [rbp+37h+var_90]; this
  ... truncated ...
```
