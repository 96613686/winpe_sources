# WDComponent_Cleanup

- ea: `0x180002688`
- end: `0x180002ad8`
- name: `WDComponent_Cleanup`
- size: `1104`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x180002670`

## callees

- `0x180001b50`
- `0x1800020b4`
- `0x180002688`
- `0x180002dc0`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800026ca`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800026ca`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x1800026e1`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x1800026e1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002702`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002710`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800027b4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800027c2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000286f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002881`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800028ee`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002907`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002a11`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002a1f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002702`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002710`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800027b4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800027c2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000286f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002881`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800028ee`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002907`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002a11`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002a1f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180002aab`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180002aab`
- `api-ms-win-security-base-l1-1-0!AdjustTokenPrivileges` at `0x18000285f`
- `api-ms-win-security-base-l1-1-0!AdjustTokenPrivileges` at `0x1800029fd`
- `api-ms-win-security-base-l1-1-0!AdjustTokenPrivileges` at `0x18000285f`
- `api-ms-win-security-base-l1-1-0!AdjustTokenPrivileges` at `0x1800029fd`
- `api-ms-win-security-lsalookup-l2-1-0!LookupPrivilegeValueW` at `0x1800027a4`
- `api-ms-win-security-lsalookup-l2-1-0!LookupPrivilegeValueW` at `0x1800027a4`
- `WDSCORE!WdsSetupLogMessageW` at `0x180002786`
- `WDSCORE!WdsSetupLogMessageW` at `0x180002a95`
- `WDSCORE!WdsSetupLogMessageW` at `0x180002786`
- `WDSCORE!WdsSetupLogMessageW` at `0x180002a95`
- `WDSCORE!CurrentIP` at `0x18000271e`
- `WDSCORE!CurrentIP` at `0x1800027d0`
- `WDSCORE!CurrentIP` at `0x18000288f`
- `WDSCORE!CurrentIP` at `0x180002915`
- `WDSCORE!CurrentIP` at `0x180002a2d`
- `WDSCORE!CurrentIP` at `0x18000271e`
- `WDSCORE!CurrentIP` at `0x1800027d0`
- `WDSCORE!CurrentIP` at `0x18000288f`
- `WDSCORE!CurrentIP` at `0x180002915`
- `WDSCORE!CurrentIP` at `0x180002a2d`

## string_xrefs

- `0x18000274a`: `WDComponent_Cleanup`
- `0x1800027fc`: `WDComponent_Cleanup`
- `0x1800028bb`: `WDComponent_Cleanup`
- `0x180002941`: `WDComponent_Cleanup`
- `0x180002a59`: `WDComponent_Cleanup`
- `0x18000272d`: `MRTGeneralize:%d - ERROR: OpenProcessToken failed: error code %d`
- `0x18000279d`: `SeRestorePrivilege`
- `0x1800027df`: `MRTGeneralize:%d - ERROR: LookupPrivilegeValue failed: error code %d`
- `0x18000289e`: `MRTGeneralize:%d - ERROR: AdjustTokenPrivileges (enable) failed: error code %d`
- `0x180002924`: `MRTGeneralize:%d - ERROR: AdjustTokenPrivileges failed: error code %d`
- `0x180002974`: `InstallTime`
- `0x180002a3c`: `MRTGeneralize:%d - ERROR: AdjustTokenPrivileges (restore) failed: error code %d`

## pseudocode

```c
__int64 WDComponent_Cleanup()
{
  HANDLE CurrentProcess; // rax
  DWORD v1; // esi
  DWORD v2; // edi
  __int64 v3; // rbx
  struct tagLOG_PARTIAL_MSG *v4; // rax
  DWORD v5; // edi
  __int64 v6; // rbx
  struct tagLOG_PARTIAL_MSG *v7; // rax
  DWORD v8; // edi
  __int64 v9; // rbx
  struct tagLOG_PARTIAL_MSG *v10; // rax
  DWORD LastError; // edi
  __int64 v12; // rbx
  struct tagLOG_PARTIAL_MSG *v13; // rax
  DWORD v14; // edi
  __int64 v15; // rbx
  struct tagLOG_PARTIAL_MSG *v16; // rax
  DWORD ReturnLength; // [rsp+60h] [rbp-19h] BYREF
  HANDLE TokenHandle; // [rsp+68h] [rbp-11h] BYREF
  _LUID Luid[2]; // [rsp+70h] [rbp-9h] BYREF
  struct _TOKEN_PRIVILEGES NewState; // [rsp+80h] [rbp+7h] BYREF

  TokenHandle = (HANDLE)-1LL;
  *(_OWORD *)&Luid[0].LowPart = 0;
  ReturnLength = 0;
  NewState = 0;
  CurrentProcess = GetCurrentProcess();
  if ( OpenProcessToken(CurrentProcess, 0x28u, &TokenHandle) )
  {
    if ( LookupPrivilegeValueW(0, L"SeRestorePrivilege", (PLUID)&Luid[0].HighPart) )
    {
      Luid[0].LowPart = 1;
      Luid[1].HighPart = 2;
      if ( AdjustTokenPrivileges(TokenHandle, 0, (PTOKEN_PRIVILEGES)Luid, 0x10u, &NewState, &ReturnLength) )
      {
        v1 = 1300;
        if ( GetLastError() == 1300 )
        {
          ReturnLength = 0;
          LastError = GetLastError();
          v12 = CurrentIP();
          v13 = ConstructPartialMsgW(
                  0x2000000u,
                  "MRTGeneralize:%d - ERROR: AdjustTokenPrivileges failed: error code %d",
                  360,
                  1300);
          WdsSetupLogMessageW(
            v13,
            983040,
            L"D",
            0,
            360,
            L"onecore\\amcore\\antimalware\\source\\filehascode\\table\\mrtgeneralize.cpp",
            L"WDComponent_Cleanup",
            v12,
            LastError,
            0,
            0);
        }
        else
        {
          v1 = 0;
          DeleteRegValue(L"SOFTWARE\\Microsoft\\Windows Defender", L"InstallTime");
          DeleteRegValue(L"SOFTWARE\\Microsoft\\Windows Defender\\Scan", L"LastScanRun");
          DeleteRegValue(L"SOFTWARE\\Microsoft\\Windows Defender\\Scan", L"LastScanType");
          DeleteRegValue(L"SOFTWARE\\Microsoft\\Windows Defender\\Scan", L"LastQuickScanID");
          DeleteRegValue(L"SOFTWARE\\Microsoft\\Windows Defender\\Scan", L"LastFullScanID");
          DeleteRegValue(L"SOFTWARE\\Microsoft\\Windows Defender\\Scan", L"MeasureBootEnabled");
        }
      }
      else
      {
        v1 = GetLastError();
        ReturnLength = 0;
        v8 = GetLastError();
        v9 = CurrentIP();
        v10 = ConstructPartialMsgW(
                0x2000000u,
                "MRTGeneralize:%d - ERROR: AdjustTokenPrivileges (enable) failed: error code %d",
                350,
                v1);
        WdsSetupLogMessageW(
          v10,
          983040,
          L"D",
          0,
          350,
          L"onecore\\amcore\\antimalware\\source\\filehascode\\table\\mrtgeneralize.cpp",
          L"WDComponent_Cleanup",
          v9,
          v8,
          0,
          0);
      }
    }
    else
    {
      v1 = GetLastError();
      v5 = GetLastError();
      v6 = CurrentIP();
      v7 = ConstructPartialMsgW(
             0x2000000u,
             "MRTGeneralize:%d - ERROR: LookupPrivilegeValue failed: error code %d",
             330,
             v1);
      WdsSetupLogMessageW(
        v7,
        983040,
        L"D",
        0,
        330,
        L"onecore\\amcore\\antimalware\\source\\filehascode\\table\\mrtgeneralize.cpp",
        L"WDComponent_Cleanup",
        v6,
        v5,
        0,
        0);
    }
  }
  else
  {
    v1 = GetLastError();
    v2 = GetLastError();
    v3 = CurrentIP();
    v4 = ConstructPartialMsgW(0x2000000u, "MRTGeneralize:%d - ERROR: OpenProcessToken failed: error code %d", 317, v1);
    WdsSetupLogMessageW(
      v4,
      983040,
      L"D",
      0,
      317,
      L"onecore\\amcore\\antimalware\\source\\filehascode\\table\\mrtgeneralize.cpp",
      L"WDComponent_Cleanup",
      v3,
      v2,
      0,
      0);
  }
  if ( ReturnLength && !AdjustTokenPrivileges(TokenHandle, 0, &NewState, 0, 0, 0) )
  {
    v1 = GetLastError();
    v14 = GetLastError();
    v15 = CurrentIP();
    v16 = ConstructPartialMsgW(
            0x2000000u,
            "MRTGeneralize:%d - ERROR: AdjustTokenPrivileges (restore) failed: error code %d",
            397,
            v1);
    WdsSetupLogMessageW(
      v16,
      983040,
      L"D",
      0,
      397,
      L"onecore\\amcore\\antimalware\\source\\filehascode\\table\\mrtgeneralize.cpp",
      L"WDComponent_Cleanup",
      v15,
      v14,
      0,
      0);
  }
  if ( TokenHandle != (HANDLE)-1LL )
    CloseHandle(TokenHandle);
  return v1;
}

```

## disassembly

```asm
0x180002688  push    rbp
0x18000268a  push    rbx
0x18000268b  push    rsi
0x18000268c  push    rdi
0x18000268d  push    r12
0x18000268f  push    r13
0x180002691  push    r15
0x180002693  lea     rbp, [rsp-27h]
0x180002698  sub     rsp, 0A0h
0x18000269f  mov     rax, cs:__security_cookie
0x1800026a6  xor     rax, rsp
0x1800026a9  mov     [rbp+57h+var_40], rax
0x1800026ad  xorps   xmm0, xmm0
0x1800026b0  mov     [rbp+57h+TokenHandle], 0FFFFFFFFFFFFFFFFh
0x1800026b8  xorps   xmm1, xmm1
0x1800026bb  xor     r15d, r15d
0x1800026be  movups  xmmword ptr [rbp+57h+Luid.LowPart], xmm0
0x1800026c2  mov     [rbp+57h+var_70], r15d
0x1800026c6  movups  xmmword ptr [rbp+57h+NewState.PrivilegeCount], xmm1
0x1800026ca  call    cs:__imp_GetCurrentProcess
0x1800026d1  nop     dword ptr [rax+rax+00h]
0x1800026d6  mov     rcx, rax; ProcessHandle
0x1800026d9  lea     r8, [rbp+57h+TokenHandle]; TokenHandle
0x1800026dd  lea     edx, [r15+28h]; DesiredAccess
0x1800026e1  call    cs:__imp_OpenProcessToken
0x1800026e8  nop     dword ptr [rax+rax+00h]
0x1800026ed  mov     r12d, 2000000h
0x1800026f3  lea     r13, aD; "D"
0x1800026fa  test    eax, eax
0x1800026fc  jnz     loc_180002797
0x180002702  call    cs:__imp_GetLastError
0x180002709  nop     dword ptr [rax+rax+00h]
0x18000270e  mov     esi, eax
0x180002710  call    cs:__imp_GetLastError
0x180002717  nop     dword ptr [rax+rax+00h]
0x18000271c  mov     edi, eax
0x18000271e  call    cs:__imp_CurrentIP
0x180002725  nop     dword ptr [rax+rax+00h]
0x18000272a  mov     r9d, esi
0x18000272d  lea     rdx, aMrtgeneralizeD_9; "MRTGeneralize:%d - ERROR: OpenProcessTo"...
0x180002734  mov     r8d, 13Dh
0x18000273a  mov     ecx, r12d; unsigned int
0x18000273d  mov     rbx, rax
0x180002740  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x180002745  mov     [rsp+0D0h+var_80], r15d
0x18000274a  lea     rcx, aWdcomponentCle; "WDComponent_Cleanup"
0x180002751  mov     [rsp+0D0h+var_88], r15
0x180002756  mov     [rsp+0D0h+var_90], edi
0x18000275a  mov     [rsp+0D0h+var_98], rbx
0x18000275f  mov     [rsp+0D0h+var_A0], rcx
0x180002764  lea     rcx, aOnecoreAmcoreA; "onecore\\amcore\\antimalware\\source\\f"...
0x18000276b  mov     [rsp+0D0h+ReturnLength], rcx
0x180002770  mov     dword ptr [rsp+0D0h+PreviousState], 13Dh
0x180002778  xor     r9d, r9d
0x18000277b  mov     r8, r13
0x18000277e  mov     edx, 0F0000h
0x180002783  mov     rcx, rax
0x180002786  call    cs:__imp_WdsSetupLogMessageW
0x18000278d  nop     dword ptr [rax+rax+00h]
0x180002792  jmp     loc_1800029DC
0x180002797  lea     r8, [rbp+57h+Luid.HighPart]; lpLuid
0x18000279b  xor     ecx, ecx; lpSystemName
0x18000279d  lea     rdx, Name; "SeRestorePrivilege"
0x1800027a4  call    cs:__imp_LookupPrivilegeValueW
0x1800027ab  nop     dword ptr [rax+rax+00h]
0x1800027b0  test    eax, eax
0x1800027b2  jnz     short loc_18000282F
0x1800027b4  call    cs:__imp_GetLastError
0x1800027bb  nop     dword ptr [rax+rax+00h]
0x1800027c0  mov     esi, eax
0x1800027c2  call    cs:__imp_GetLastError
0x1800027c9  nop     dword ptr [rax+rax+00h]
0x1800027ce  mov     edi, eax
0x1800027d0  call    cs:__imp_CurrentIP
0x1800027d7  nop     dword ptr [rax+rax+00h]
0x1800027dc  mov     r9d, esi
0x1800027df  lea     rdx, aMrtgeneralizeD_3; "MRTGeneralize:%d - ERROR: LookupPrivile"...
0x1800027e6  mov     r8d, 14Ah
0x1800027ec  mov     ecx, r12d; unsigned int
0x1800027ef  mov     rbx, rax
0x1800027f2  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x1800027f7  mov     [rsp+0D0h+var_80], r15d
0x1800027fc  lea     rcx, aWdcomponentCle; "WDComponent_Cleanup"
0x180002803  mov     [rsp+0D0h+var_88], r15
0x180002808  mov     [rsp+0D0h+var_90], edi
0x18000280c  mov     [rsp+0D0h+var_98], rbx
0x180002811  mov     [rsp+0D0h+var_A0], rcx
0x180002816  lea     rcx, aOnecoreAmcoreA; "onecore\\amcore\\antimalware\\source\\f"...
0x18000281d  mov     [rsp+0D0h+ReturnLength], rcx
0x180002822  mov     dword ptr [rsp+0D0h+PreviousState], 14Ah
0x18000282a  jmp     loc_180002778
0x18000282f  mov     rcx, [rbp+57h+TokenHandle]; TokenHandle
0x180002833  lea     rax, [rbp+57h+var_70]
0x180002837  mov     [rsp+0D0h+ReturnLength], rax; ReturnLength
0x18000283c  lea     r8, [rbp+57h+Luid]; NewState
0x180002840  lea     rax, [rbp+57h+NewState]
0x180002844  mov     [rbp+57h+Luid.LowPart], 1
0x18000284b  mov     r9d, 10h; BufferLength
0x180002851  mov     [rsp+0D0h+PreviousState], rax; PreviousState
0x180002856  xor     edx, edx; DisableAllPrivileges
0x180002858  mov     [rbp+57h+Luid.HighPart+8], 2
0x18000285f  call    cs:__imp_AdjustTokenPrivileges
0x180002866  nop     dword ptr [rax+rax+00h]
0x18000286b  test    eax, eax
0x18000286d  jnz     short loc_1800028EE
0x18000286f  call    cs:__imp_GetLastError
0x180002876  nop     dword ptr [rax+rax+00h]
0x18000287b  mov     esi, eax
0x18000287d  mov     [rbp+57h+var_70], r15d
0x180002881  call    cs:__imp_GetLastError
0x180002888  nop     dword ptr [rax+rax+00h]
0x18000288d  mov     edi, eax
0x18000288f  call    cs:__imp_CurrentIP
0x180002896  nop     dword ptr [rax+rax+00h]
0x18000289b  mov     r9d, esi
0x18000289e  lea     rdx, aMrtgeneralizeD_14; "MRTGeneralize:%d - ERROR: AdjustTokenPr"...
0x1800028a5  mov     r8d, 15Eh
0x1800028ab  mov     ecx, r12d; unsigned int
0x1800028ae  mov     rbx, rax
0x1800028b1  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x1800028b6  mov     [rsp+0D0h+var_80], r15d
0x1800028bb  lea     rcx, aWdcomponentCle; "WDComponent_Cleanup"
0x1800028c2  mov     [rsp+0D0h+var_88], r15
0x1800028c7  mov     [rsp+0D0h+var_90], edi
0x1800028cb  mov     [rsp+0D0h+var_98], rbx
0x1800028d0  mov     [rsp+0D0h+var_A0], rcx
0x1800028d5  lea     rcx, aOnecoreAmcoreA; "onecore\\amcore\\antimalware\\source\\f"...
0x1800028dc  mov     [rsp+0D0h+ReturnLength], rcx
0x1800028e1  mov     dword ptr [rsp+0D0h+PreviousState], 15Eh
0x1800028e9  jmp     loc_180002778
0x1800028ee  call    cs:__imp_GetLastError
0x1800028f5  nop     dword ptr [rax+rax+00h]
0x1800028fa  mov     esi, 514h
0x1800028ff  cmp     eax, esi
0x180002901  jnz     short loc_180002974
0x180002903  mov     [rbp+57h+var_70], r15d
0x180002907  call    cs:__imp_GetLastError
0x18000290e  nop     dword ptr [rax+rax+00h]
0x180002913  mov     edi, eax
0x180002915  call    cs:__imp_CurrentIP
0x18000291c  nop     dword ptr [rax+rax+00h]
0x180002921  mov     r9d, esi
0x180002924  lea     rdx, aMrtgeneralizeD_1; "MRTGeneralize:%d - ERROR: AdjustTokenPr"...
0x18000292b  mov     r8d, 168h
0x180002931  mov     ecx, r12d; unsigned int
0x180002934  mov     rbx, rax
0x180002937  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x18000293c  mov     [rsp+0D0h+var_80], r15d
0x180002941  lea     rcx, aWdcomponentCle; "WDComponent_Cleanup"
0x180002948  mov     [rsp+0D0h+var_88], r15
0x18000294d  mov     [rsp+0D0h+var_90], edi
0x180002951  mov     [rsp+0D0h+var_98], rbx
0x180002956  mov     [rsp+0D0h+var_A0], rcx
0x18000295b  lea     rcx, aOnecoreAmcoreA; "onecore\\amcore\\antimalware\\source\\f"...
0x180002962  mov     [rsp+0D0h+ReturnLength], rcx
0x180002967  mov     dword ptr [rsp+0D0h+PreviousState], 168h
0x18000296f  jmp     loc_180002778
0x180002974  lea     rdx, ValueName; "InstallTime"
0x18000297b  mov     esi, r15d
0x18000297e  lea     rcx, aSoftwareMicros_0; "SOFTWARE\\Microsoft\\Windows Defender"
0x180002985  call    DeleteRegValue
0x18000298a  lea     rbx, aSoftwareMicros_1; "SOFTWARE\\Microsoft\\Windows Defender\\"...
0x180002991  mov     rcx, rbx; lpSubKey
0x180002994  lea     rdx, aLastscanrun; "LastScanRun"
0x18000299b  call    DeleteRegValue
0x1800029a0  lea     rdx, aLastscantype; "LastScanType"
0x1800029a7  mov     rcx, rbx; lpSubKey
0x1800029aa  call    DeleteRegValue
0x1800029af  lea     rdx, aLastquickscani; "LastQuickScanID"
0x1800029b6  mov     rcx, rbx; lpSubKey
0x1800029b9  call    DeleteRegValue
0x1800029be  lea     rdx, aLastfullscanid; "LastFullScanID"
0x1800029c5  mov     rcx, rbx; lpSubKey
0x1800029c8  call    DeleteRegValue
0x1800029cd  lea     rdx, aMeasurebootena; "MeasureBootEnabled"
0x1800029d4  mov     rcx, rbx; lpSubKey
0x1800029d7  call    DeleteRegValue
0x1800029dc  cmp     [rbp+57h+var_70], r15d
0x1800029e0  jz      loc_180002AA1
0x1800029e6  mov     rcx, [rbp+57h+TokenHandle]; TokenHandle
0x1800029ea  lea     r8, [rbp+57h+NewState]; NewState
0x1800029ee  mov     [rsp+0D0h+ReturnLength], r15; ReturnLength
0x1800029f3  xor     r9d, r9d; BufferLength
0x1800029f6  xor     edx, edx; DisableAllPrivileges
0x1800029f8  mov     [rsp+0D0h+PreviousState], r15; PreviousState
0x1800029fd  call    cs:__imp_AdjustTokenPrivileges
0x180002a04  nop     dword ptr [rax+rax+00h]
0x180002a09  test    eax, eax
0x180002a0b  jnz     loc_180002AA1
0x180002a11  call    cs:__imp_GetLastError
0x180002a18  nop     dword ptr [rax+rax+00h]
0x180002a1d  mov     esi, eax
0x180002a1f  call    cs:__imp_GetLastError
0x180002a26  nop     dword ptr [rax+rax+00h]
0x180002a2b  mov     edi, eax
0x180002a2d  call    cs:__imp_CurrentIP
0x180002a34  nop     dword ptr [rax+rax+00h]
0x180002a39  mov     r9d, esi
0x180002a3c  lea     rdx, aMrtgeneralizeD_11; "MRTGeneralize:%d - ERROR: AdjustTokenPr"...
0x180002a43  mov     r8d, 18Dh
0x180002a49  mov     ecx, r12d; unsigned int
0x180002a4c  mov     rbx, rax
0x180002a4f  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x180002a54  mov     [rsp+0D0h+var_80], r15d
0x180002a59  lea     rcx, aWdcomponentCle; "WDComponent_Cleanup"
0x180002a60  mov     [rsp+0D0h+var_88], r15
0x180002a65  xor     r9d, r9d
0x180002a68  mov     [rsp+0D0h+var_90], edi
0x180002a6c  mov     r8, r13
0x180002a6f  mov     [rsp+0D0h+var_98], rbx
0x180002a74  mov     edx, 0F0000h
0x180002a79  mov     [rsp+0D0h+var_A0], rcx
0x180002a7e  lea     rcx, aOnecoreAmcoreA; "onecore\\amcore\\antimalware\\source\\f"...
0x180002a85  mov     [rsp+0D0h+ReturnLength], rcx
0x180002a8a  mov     rcx, rax
0x180002a8d  mov     dword ptr [rsp+0D0h+PreviousState], 18Dh
0x180002a95  call    cs:__imp_WdsSetupLogMessageW
0x180002a9c  nop     dword ptr [rax+rax+00h]
0x180002aa1  mov     rcx, [rbp+57h+TokenHandle]; hObject
0x180002aa5  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x180002aa9  jz      short loc_180002AB7
0x180002aab  call    cs:__imp_CloseHandle
0x180002ab2  nop     dword ptr [rax+rax+00h]
0x180002ab7  mov     eax, esi
0x180002ab9  mov     rcx, [rbp+57h+var_40]
0x180002abd  xor     rcx, rsp; StackCookie
0x180002ac0  call    __security_check_cookie
0x180002ac5  add     rsp, 0A0h
0x180002acc  pop     r15
0x180002ace  pop     r13
0x180002ad0  pop     r12
0x180002ad2  pop     rdi
0x180002ad3  pop     rsi
0x180002ad4  pop     rbx
0x180002ad5  pop     rbp
0x180002ad6  retn
```
