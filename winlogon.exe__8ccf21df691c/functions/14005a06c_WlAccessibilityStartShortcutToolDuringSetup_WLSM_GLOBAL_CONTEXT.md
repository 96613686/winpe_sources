# WlAccessibilityStartShortcutToolDuringSetup(_WLSM_GLOBAL_CONTEXT *)

- ea: `0x14005a06c`
- end: `0x14005a685`
- name: `?WlAccessibilityStartShortcutToolDuringSetup@@YAKPEAU_WLSM_GLOBAL_CONTEXT@@@Z`
- size: `1561`
- prototype: `__int64 __fastcall(CSession **)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x140059380`

## callees

- `0x1400057f4`
- `0x14000d4e0`
- `0x14000fb30`
- `0x140041c34`
- `0x140053720`
- `0x1400544e0`
- `0x14005a06c`
- `0x14007b9dc`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14005a4b3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14005a515`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14005a560`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14005a5af`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14005a4b3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14005a515`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14005a560`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14005a5af`
- `api-ms-win-core-processthreads-l1-1-0!CreateProcessW` at `0x14005a4a9`
- `api-ms-win-core-processthreads-l1-1-0!CreateProcessW` at `0x14005a4a9`
- `api-ms-win-core-processthreads-l1-1-0!ResumeThread` at `0x14005a5a4`
- `api-ms-win-core-processthreads-l1-1-0!ResumeThread` at `0x14005a5a4`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14005a63b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14005a64e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14005a65c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14009ebb5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14009ebc8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14009ebd8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14005a63b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14005a64e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14005a65c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14009ebb5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14009ebc8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14009ebd8`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x14005a1b1`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x14005a1b1`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x14005a1e3`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x14005a1e3`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14005a1ee`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14005a1ee`
- `api-ms-win-core-job-l2-1-0!AssignProcessToJobObject` at `0x14005a556`
- `api-ms-win-core-job-l2-1-0!AssignProcessToJobObject` at `0x14005a556`
- `api-ms-win-core-job-l2-1-0!TerminateJobObject` at `0x14005a5f0`
- `api-ms-win-core-job-l2-1-0!TerminateJobObject` at `0x14005a5f0`
- `ntdll!NtClose` at `0x14005a1f9`
- `ntdll!NtClose` at `0x14005a1f9`
- `ntdll!RtlOpenCurrentUser` at `0x14005a16b`
- `ntdll!RtlOpenCurrentUser` at `0x14005a16b`

## string_xrefs

- `0x14005a2fe`: `atbroker.exe`
- `0x14005a366`: `atbroker.exe`
- `0x14005a3da`: `atbroker.exe`
- `0x14005a1a5`: `Control Panel\Accessibility`

## pseudocode

```c
__int64 __fastcall WlAccessibilityStartShortcutToolDuringSetup(CSession **a1)
{
  DWORD LastError; // ebx
  void *v3; // r15
  unsigned int v4; // r14d
  CUser *v5; // rcx
  __int64 v6; // rdx
  int v7; // edx
  CUser *v8; // rcx
  __int64 v9; // rdx
  void *AccessibilityJobObject; // rax
  BYTE Data[4]; // [rsp+50h] [rbp-178h] BYREF
  DWORD cbData; // [rsp+54h] [rbp-174h] BYREF
  DWORD Type; // [rsp+58h] [rbp-170h] BYREF
  HKEY hKey; // [rsp+60h] [rbp-168h] BYREF
  void *KeyHandle; // [rsp+68h] [rbp-160h] BYREF
  void *v17; // [rsp+70h] [rbp-158h]
  struct _PROCESS_INFORMATION ProcessInformation; // [rsp+78h] [rbp-150h] BYREF
  struct _STARTUPINFOW StartupInfo; // [rsp+90h] [rbp-138h] BYREF
  WCHAR CommandLine[64]; // [rsp+100h] [rbp-C8h] BYREF

  LastError = 0;
  *(_DWORD *)Data = 1;
  memset_0(&StartupInfo, 0, sizeof(StartupInfo));
  memset(&ProcessInformation, 0, sizeof(ProcessInformation));
  v3 = 0;
  v17 = 0;
  v4 = *((_DWORD *)*a1 + 44);
  if ( WPP_GLOBAL_Control != (CUser *)&WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x40000) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 127, WPP_08fbe39dfd5c3ed1d0f5d3aa8d6e811c_Traceguids, v4);
  }
  switch ( v4 )
  {
    case 0xFFFFFFF7:
      if ( (int)StringCchPrintfW(
                  CommandLine,
                  0x40u,
                  L"%s %s %s",
                  L"atbroker.exe",
                  L"/start narrator",
                  L"/hardwarebuttonlaunch") < 0 )
      {
        v5 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (CUser *)&WPP_GLOBAL_Control
          || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x40000) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
          goto LABEL_28;
        }
        v6 = 132;
        goto LABEL_27;
      }
      break;
    case 0xFFFFFFF8:
      if ( (int)StringCchPrintfW(CommandLine, 0x40u, L"%s %s", L"atbroker.exe", L"/start magnifierpane") < 0 )
      {
        v5 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (CUser *)&WPP_GLOBAL_Control
          || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x40000) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
          goto LABEL_28;
        }
        v6 = 131;
        goto LABEL_27;
      }
      break;
    case 0xFFFFFFFA:
      if ( (int)StringCchPrintfW(CommandLine, 0x40u, L"%s %s", L"atbroker.exe", L"/hardwarebuttonlaunch") < 0 )
      {
        v5 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (CUser *)&WPP_GLOBAL_Control
          || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x40000) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
          goto LABEL_28;
        }
        v6 = 130;
        goto LABEL_27;
      }
      break;
    case 0xFFFFFFFE:
      if ( (int)StringCchPrintfW(CommandLine, 0x40u, L"osk.exe -s") < 0 )
      {
        v5 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (CUser *)&WPP_GLOBAL_Control
          || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x40000) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
          goto LABEL_28;
        }
        v6 = 129;
        goto LABEL_27;
      }
      break;
    case 0xFFFFFFFF:
      if ( (int)StringCchPrintfW(CommandLine, 0x40u, L"utilman.exe /debug") < 0 )
      {
        v5 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (CUser *)&WPP_GLOBAL_Control
          || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x40000) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
          goto LABEL_28;
        }
        v6 = 128;
        goto LABEL_27;
      }
      break;
    default:
      if ( v4 >= 0xC8 )
      {
        KeyHandle = 0;
        if ( RtlOpenCurrentUser(0x2000000u, &KeyHandle) >= 0 )
        {
          hKey = 0;
          cbData = 4;
          Type = 0;
          if ( !RegOpenKeyExW((HKEY)KeyHandle, L"Control Panel\\Accessibility", 0, 0x20019u, &hKey) )
          {
            RegQueryValueExW(hKey, L"Warning Sounds", 0, &Type, Data, &cbData);
            RegCloseKey(hKey);
          }
          NtClose(KeyHandle);
        }
        if ( *(_DWORD *)Data )
          ++v4;
      }
      if ( (int)StringCchPrintfW(CommandLine, 0x40u, L"sethc.exe %ld", v4) < 0 )
      {
        v5 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (CUser *)&WPP_GLOBAL_Control
          || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x40000) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
          goto LABEL_28;
        }
        v6 = 133;
LABEL_27:
        WPP_SF_(*((_QWORD *)v5 + 2), v6, WPP_08fbe39dfd5c3ed1d0f5d3aa8d6e811c_Traceguids);
LABEL_28:
        LastError = 87;
        goto LABEL_77;
      }
      break;
  }
  StartupInfo.cb = 104;
  StartupInfo.dwFlags = 1;
  StartupInfo.wShowWindow = 1;
  StartupInfo.lpDesktop = L"Winsta0\\Default";
  if ( CreateProcessW(0, CommandLine, 0, 0, 0, 0x404u, 0, 0, &StartupInfo, &ProcessInformation) )
  {
    AccessibilityJobObject = CSession::GetAccessibilityJobObject(a1[2], v7);
    v3 = AccessibilityJobObject;
    v17 = AccessibilityJobObject;
    if ( AccessibilityJobObject )
    {
      if ( AssignProcessToJobObject(AccessibilityJobObject, ProcessInformation.hProcess) )
      {
        if ( ResumeThread(ProcessInformation.hThread) == -1 )
        {
          LastError = GetLastError();
          v8 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (CUser *)&WPP_GLOBAL_Control
            && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x40000) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            v9 = 137;
            goto LABEL_54;
          }
        }
        else if ( dword_1400D2D00 )
        {
          if ( WPP_GLOBAL_Control != (CUser *)&WPP_GLOBAL_Control
            && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x40000) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
          {
            WPP_SF_S(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              138,
              WPP_08fbe39dfd5c3ed1d0f5d3aa8d6e811c_Traceguids,
              CommandLine);
          }
          LastError = 0;
        }
        else
        {
          TerminateJobObject(v3, 0x42Bu);
        }
      }
      else
      {
        LastError = GetLastError();
        v8 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (CUser *)&WPP_GLOBAL_Control
          && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x40000) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          v9 = 136;
          goto LABEL_54;
        }
      }
    }
    else
    {
      LastError = GetLastError();
      v8 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (CUser *)&WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x40000) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v9 = 135;
        goto LABEL_54;
      }
    }
  }
  else
  {
    LastError = GetLastError();
    v8 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (CUser *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x40000) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v9 = 134;
LABEL_54:
      WPP_SF_d(*((_QWORD *)v8 + 2), v9, WPP_08fbe39dfd5c3ed1d0f5d3aa8d6e811c_Traceguids, LastError);
    }
  }
LABEL_77:
  if ( ProcessInformation.hProcess )
    CloseHandle(ProcessInformation.hProcess);
  if ( ProcessInformation.hThread )
    CloseHandle(ProcessInformation.hThread);
  if ( v3 )
    CloseHandle(v3);
  return LastError;
}

```

## disassembly

```asm
0x14005a06c  push    rbx
0x14005a06e  push    rsi
0x14005a06f  push    rdi
0x14005a070  push    r12
0x14005a072  push    r14
0x14005a074  push    r15
0x14005a076  sub     rsp, 198h
0x14005a07d  mov     rax, cs:__security_cookie
0x14005a084  xor     rax, rsp
0x14005a087  mov     [rsp+1C8h+var_48], rax
0x14005a08f  mov     r12, rcx
0x14005a092  xor     ebx, ebx
0x14005a094  mov     dword ptr [rsp+1C8h+Data], 1
0x14005a09c  xor     edx, edx; Val
0x14005a09e  lea     r8d, [rbx+68h]; Size
0x14005a0a2  lea     rcx, [rsp+1C8h+StartupInfo]; void *
0x14005a0aa  call    memset_0
0x14005a0af  xorps   xmm0, xmm0
0x14005a0b2  xor     eax, eax
0x14005a0b4  movups  xmmword ptr [rsp+1C8h+ProcessInformation.hProcess], xmm0
0x14005a0b9  mov     qword ptr [rsp+1C8h+ProcessInformation.dwProcessId], rax
0x14005a0c1  xor     r15d, r15d
0x14005a0c4  mov     [rsp+1C8h+var_158], r15
0x14005a0c9  mov     rax, [r12]
0x14005a0cd  mov     r14d, [rax+0B0h]
0x14005a0d4  lea     rax, WPP_GLOBAL_Control
0x14005a0db  mov     rcx, cs:WPP_GLOBAL_Control
0x14005a0e2  mov     edi, 40000h
0x14005a0e7  cmp     rcx, rax
0x14005a0ea  jz      short loc_14005A112
0x14005a0ec  test    [rcx+1Ch], edi
0x14005a0ef  jz      short loc_14005A112
0x14005a0f1  lea     rsi, WPP_08fbe39dfd5c3ed1d0f5d3aa8d6e811c_Traceguids
0x14005a0f8  cmp     byte ptr [rcx+19h], 4
0x14005a0fc  jb      short loc_14005A119
0x14005a0fe  lea     edx, [rbx+7Fh]
0x14005a101  mov     r9d, r14d
0x14005a104  mov     r8, rsi
0x14005a107  mov     rcx, [rcx+10h]
0x14005a10b  call    WPP_SF_d
0x14005a110  jmp     short loc_14005A119
0x14005a112  lea     rsi, WPP_08fbe39dfd5c3ed1d0f5d3aa8d6e811c_Traceguids
0x14005a119  cmp     r14d, 0FFFFFFF7h
0x14005a11d  jz      loc_14005A3C2
0x14005a123  cmp     r14d, 0FFFFFFF8h
0x14005a127  jz      loc_14005A35A
0x14005a12d  cmp     r14d, 0FFFFFFFAh
0x14005a131  jz      loc_14005A2F2
0x14005a137  cmp     r14d, 0FFFFFFFEh
0x14005a13b  jz      loc_14005A2AC
0x14005a141  cmp     r14d, 0FFFFFFFFh
0x14005a145  jz      loc_14005A252
0x14005a14b  cmp     r14d, 0C8h
0x14005a152  jb      loc_14005A209
0x14005a158  mov     [rsp+1C8h+KeyHandle], 0
0x14005a161  lea     rdx, [rsp+1C8h+KeyHandle]; KeyHandle
0x14005a166  mov     ecx, 2000000h; DesiredAccess
0x14005a16b  call    cs:__imp_RtlOpenCurrentUser
0x14005a171  test    eax, eax
0x14005a173  js      loc_14005A1FF
0x14005a179  mov     [rsp+1C8h+hKey], 0
0x14005a182  mov     [rsp+1C8h+cbData], 4
0x14005a18a  mov     [rsp+1C8h+Type], 0
0x14005a192  lea     rax, [rsp+1C8h+hKey]
0x14005a197  mov     [rsp+1C8h+phkResult], rax; phkResult
0x14005a19c  mov     r9d, 20019h; samDesired
0x14005a1a2  xor     r8d, r8d; ulOptions
0x14005a1a5  lea     rdx, aControlPanelAc; "Control Panel\\Accessibility"
0x14005a1ac  mov     rcx, [rsp+1C8h+KeyHandle]; hKey
0x14005a1b1  call    cs:__imp_RegOpenKeyExW
0x14005a1b7  test    eax, eax
0x14005a1b9  jnz     short loc_14005A1F4
0x14005a1bb  lea     rax, [rsp+1C8h+cbData]
0x14005a1c0  mov     [rsp+1C8h+lpcbData], rax; lpcbData
0x14005a1c5  lea     rax, [rsp+1C8h+Data]
0x14005a1ca  mov     [rsp+1C8h+phkResult], rax; lpData
0x14005a1cf  lea     r9, [rsp+1C8h+Type]; lpType
0x14005a1d4  xor     r8d, r8d; lpReserved
0x14005a1d7  lea     rdx, aWarningSounds; "Warning Sounds"
0x14005a1de  mov     rcx, [rsp+1C8h+hKey]; hKey
0x14005a1e3  call    cs:__imp_RegQueryValueExW
0x14005a1e9  mov     rcx, [rsp+1C8h+hKey]; hKey
0x14005a1ee  call    cs:__imp_RegCloseKey
0x14005a1f4  mov     rcx, [rsp+1C8h+KeyHandle]; Handle
0x14005a1f9  call    cs:__imp_NtClose
0x14005a1ff  cmp     dword ptr [rsp+1C8h+Data], 0
0x14005a204  jz      short loc_14005A209
0x14005a206  inc     r14d
0x14005a209  mov     r9d, r14d
0x14005a20c  lea     r8, aSethcExeLd; "sethc.exe %ld"
0x14005a213  mov     edx, 40h ; '@'; unsigned __int64
0x14005a218  lea     rcx, [rsp+1C8h+CommandLine]; unsigned __int16 *
0x14005a220  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x14005a225  test    eax, eax
0x14005a227  jns     loc_14005A432
0x14005a22d  mov     rcx, cs:WPP_GLOBAL_Control
0x14005a234  lea     rax, WPP_GLOBAL_Control
0x14005a23b  cmp     rcx, rax
0x14005a23e  jz      short loc_14005A2A2
0x14005a240  test    [rcx+1Ch], edi
0x14005a243  jz      short loc_14005A2A2
0x14005a245  cmp     byte ptr [rcx+19h], 2
0x14005a249  jb      short loc_14005A2A2
0x14005a24b  mov     edx, 85h
0x14005a250  jmp     short loc_14005A296
0x14005a252  lea     r8, aUtilmanExeDebu; "utilman.exe /debug"
0x14005a259  mov     edx, 40h ; '@'; unsigned __int64
0x14005a25e  lea     rcx, [rsp+1C8h+CommandLine]; unsigned __int16 *
0x14005a266  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x14005a26b  test    eax, eax
0x14005a26d  jns     loc_14005A432
0x14005a273  mov     rcx, cs:WPP_GLOBAL_Control
0x14005a27a  lea     rax, WPP_GLOBAL_Control
0x14005a281  cmp     rcx, rax
0x14005a284  jz      short loc_14005A2A2
0x14005a286  test    [rcx+1Ch], edi
0x14005a289  jz      short loc_14005A2A2
0x14005a28b  cmp     byte ptr [rcx+19h], 2
0x14005a28f  jb      short loc_14005A2A2
0x14005a291  mov     edx, 80h
0x14005a296  mov     r8, rsi
0x14005a299  mov     rcx, [rcx+10h]
0x14005a29d  call    WPP_SF_
0x14005a2a2  mov     ebx, 57h ; 'W'
0x14005a2a7  jmp     loc_14005A631
0x14005a2ac  lea     r8, aOskExeS; "osk.exe -s"
0x14005a2b3  mov     edx, 40h ; '@'; unsigned __int64
0x14005a2b8  lea     rcx, [rsp+1C8h+CommandLine]; unsigned __int16 *
0x14005a2c0  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x14005a2c5  test    eax, eax
0x14005a2c7  jns     loc_14005A432
0x14005a2cd  mov     rcx, cs:WPP_GLOBAL_Control
0x14005a2d4  lea     rax, WPP_GLOBAL_Control
0x14005a2db  cmp     rcx, rax
0x14005a2de  jz      short loc_14005A2A2
0x14005a2e0  test    [rcx+1Ch], edi
0x14005a2e3  jz      short loc_14005A2A2
0x14005a2e5  cmp     byte ptr [rcx+19h], 2
0x14005a2e9  jb      short loc_14005A2A2
0x14005a2eb  mov     edx, 81h
0x14005a2f0  jmp     short loc_14005A296
0x14005a2f2  lea     rax, aHardwarebutton; "/hardwarebuttonlaunch"
0x14005a2f9  mov     [rsp+1C8h+phkResult], rax
0x14005a2fe  lea     r9, aAtbrokerExe; "atbroker.exe"
0x14005a305  lea     r8, aSS_0; "%s %s"
0x14005a30c  mov     edx, 40h ; '@'; unsigned __int64
0x14005a311  lea     rcx, [rsp+1C8h+CommandLine]; unsigned __int16 *
0x14005a319  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x14005a31e  test    eax, eax
0x14005a320  jns     loc_14005A432
0x14005a326  mov     rcx, cs:WPP_GLOBAL_Control
0x14005a32d  lea     rax, WPP_GLOBAL_Control
0x14005a334  cmp     rcx, rax
0x14005a337  jz      loc_14005A2A2
0x14005a33d  test    [rcx+1Ch], edi
0x14005a340  jz      loc_14005A2A2
0x14005a346  cmp     byte ptr [rcx+19h], 2
0x14005a34a  jb      loc_14005A2A2
0x14005a350  mov     edx, 82h
0x14005a355  jmp     loc_14005A296
0x14005a35a  lea     rax, aStartMagnifier; "/start magnifierpane"
0x14005a361  mov     [rsp+1C8h+phkResult], rax
0x14005a366  lea     r9, aAtbrokerExe; "atbroker.exe"
0x14005a36d  lea     r8, aSS_0; "%s %s"
0x14005a374  mov     edx, 40h ; '@'; unsigned __int64
0x14005a379  lea     rcx, [rsp+1C8h+CommandLine]; unsigned __int16 *
0x14005a381  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x14005a386  test    eax, eax
0x14005a388  jns     loc_14005A432
0x14005a38e  mov     rcx, cs:WPP_GLOBAL_Control
0x14005a395  lea     rax, WPP_GLOBAL_Control
0x14005a39c  cmp     rcx, rax
0x14005a39f  jz      loc_14005A2A2
0x14005a3a5  test    [rcx+1Ch], edi
0x14005a3a8  jz      loc_14005A2A2
0x14005a3ae  cmp     byte ptr [rcx+19h], 2
0x14005a3b2  jb      loc_14005A2A2
0x14005a3b8  mov     edx, 83h
0x14005a3bd  jmp     loc_14005A296
0x14005a3c2  lea     rax, aHardwarebutton; "/hardwarebuttonlaunch"
0x14005a3c9  mov     [rsp+1C8h+lpcbData], rax
0x14005a3ce  lea     rax, aStartNarrator; "/start narrator"
0x14005a3d5  mov     [rsp+1C8h+phkResult], rax
0x14005a3da  lea     r9, aAtbrokerExe; "atbroker.exe"
0x14005a3e1  lea     r8, aSSS; "%s %s %s"
0x14005a3e8  mov     edx, 40h ; '@'; unsigned __int64
0x14005a3ed  lea     rcx, [rsp+1C8h+CommandLine]; unsigned __int16 *
0x14005a3f5  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x14005a3fa  test    eax, eax
0x14005a3fc  jns     short loc_14005A432
0x14005a3fe  mov     rcx, cs:WPP_GLOBAL_Control
0x14005a405  lea     rax, WPP_GLOBAL_Control
0x14005a40c  cmp     rcx, rax
0x14005a40f  jz      loc_14005A2A2
0x14005a415  test    [rcx+1Ch], edi
0x14005a418  jz      loc_14005A2A2
0x14005a41e  cmp     byte ptr [rcx+19h], 2
0x14005a422  jb      loc_14005A2A2
0x14005a428  mov     edx, 84h
0x14005a42d  jmp     loc_14005A296
0x14005a432  mov     [rsp+1C8h+StartupInfo.cb], 68h ; 'h'
0x14005a43d  mov     eax, 1
0x14005a442  mov     [rsp+1C8h+StartupInfo.dwFlags], eax
0x14005a449  mov     [rsp+1C8h+StartupInfo.wShowWindow], ax
0x14005a451  lea     rax, aWinsta0Default; "Winsta0\\Default"
0x14005a458  mov     [rsp+1C8h+StartupInfo.lpDesktop], rax
0x14005a460  lea     rax, [rsp+1C8h+ProcessInformation]
0x14005a465  mov     [rsp+1C8h+lpProcessInformation], rax; lpProcessInformation
0x14005a46a  lea     rax, [rsp+1C8h+StartupInfo]
0x14005a472  mov     [rsp+1C8h+lpStartupInfo], rax; lpStartupInfo
0x14005a477  mov     [rsp+1C8h+lpCurrentDirectory], 0; lpCurrentDirectory
0x14005a480  mov     [rsp+1C8h+lpEnvironment], 0; lpEnvironment
0x14005a489  mov     dword ptr [rsp+1C8h+lpcbData], 404h; dwCreationFlags
0x14005a491  mov     dword ptr [rsp+1C8h+phkResult], 0; bInheritHandles
0x14005a499  xor     r9d, r9d; lpThreadAttributes
0x14005a49c  xor     r8d, r8d; lpProcessAttributes
0x14005a49f  lea     rdx, [rsp+1C8h+CommandLine]; lpCommandLine
0x14005a4a7  xor     ecx, ecx; lpApplicationName
0x14005a4a9  call    cs:__imp_CreateProcessW
0x14005a4af  test    eax, eax
0x14005a4b1  jnz     short loc_14005A4FE
0x14005a4b3  call    cs:__imp_GetLastError
0x14005a4b9  mov     ebx, eax
0x14005a4bb  mov     rcx, cs:WPP_GLOBAL_Control
0x14005a4c2  lea     rax, WPP_GLOBAL_Control
0x14005a4c9  cmp     rcx, rax
0x14005a4cc  jz      loc_14005A631
0x14005a4d2  test    [rcx+1Ch], edi
0x14005a4d5  jz      loc_14005A631
0x14005a4db  cmp     byte ptr [rcx+19h], 2
0x14005a4df  jb      loc_14005A631
0x14005a4e5  mov     edx, 86h
0x14005a4ea  mov     r9d, ebx
0x14005a4ed  mov     r8, rsi
0x14005a4f0  mov     rcx, [rcx+10h]
0x14005a4f4  call    WPP_SF_d
0x14005a4f9  jmp     loc_14005A631
0x14005a4fe  mov     rcx, [r12+10h]; this
0x14005a503  call    ?GetAccessibilityJobObject@CSession@@QEAAPEAXH@Z; CSession::GetAccessibilityJobObject(int)
0x14005a508  mov     r15, rax
0x14005a50b  mov     [rsp+1C8h+var_158], rax
0x14005a510  test    rax, rax
0x14005a513  jnz     short loc_14005A54E
0x14005a515  call    cs:__imp_GetLastError
0x14005a51b  mov     ebx, eax
0x14005a51d  mov     rcx, cs:WPP_GLOBAL_Control
0x14005a524  lea     rax, WPP_GLOBAL_Control
0x14005a52b  cmp     rcx, rax
0x14005a52e  jz      loc_14005A631
0x14005a534  test    [rcx+1Ch], edi
0x14005a537  jz      loc_14005A631
0x14005a53d  cmp     byte ptr [rcx+19h], 2
0x14005a541  jb      loc_14005A631
0x14005a547  mov     edx, 87h
0x14005a54c  jmp     short loc_14005A4EA
0x14005a54e  mov     rdx, [rsp+1C8h+ProcessInformation.hProcess]; hProcess
0x14005a553  mov     rcx, r15; hJob
0x14005a556  call    cs:__imp_AssignProcessToJobObject
0x14005a55c  test    eax, eax
0x14005a55e  jnz     short loc_14005A59C
0x14005a560  call    cs:__imp_GetLastError
0x14005a566  mov     ebx, eax
0x14005a568  mov     rcx, cs:WPP_GLOBAL_Control
0x14005a56f  lea     rax, WPP_GLOBAL_Control
0x14005a576  cmp     rcx, rax
0x14005a579  jz      loc_14005A631
0x14005a57f  test    [rcx+1Ch], edi
0x14005a582  jz      loc_14005A631
0x14005a588  cmp     byte ptr [rcx+19h], 2
0x14005a58c  jb      loc_14005A631
0x14005a592  mov     edx, 88h
0x14005a597  jmp     loc_14005A4EA
0x14005a59c  mov     rcx, [rsp+1C8h+ProcessInformation.hThread]; hThread
0x14005a5a4  call    cs:__imp_ResumeThread
0x14005a5aa  cmp     eax, 0FFFFFFFFh
0x14005a5ad  jnz     short loc_14005A5DF
0x14005a5af  call    cs:__imp_GetLastError
0x14005a5b5  mov     ebx, eax
0x14005a5b7  mov     rcx, cs:WPP_GLOBAL_Control
0x14005a5be  lea     rax, WPP_GLOBAL_Control
0x14005a5c5  cmp     rcx, rax
0x14005a5c8  jz      short loc_14005A631
0x14005a5ca  test    [rcx+1Ch], edi
0x14005a5cd  jz      short loc_14005A631
0x14005a5cf  cmp     byte ptr [rcx+19h], 2
0x14005a5d3  jb      short loc_14005A631
0x14005a5d5  mov     edx, 89h
0x14005a5da  jmp     loc_14005A4EA
0x14005a5df  cmp     cs:dword_1400D2D00, 0
0x14005a5e6  jnz     short loc_14005A5F8
0x14005a5e8  mov     edx, 42Bh; uExitCode
0x14005a5ed  mov     rcx, r15; hJob
0x14005a5f0  call    cs:__imp_TerminateJobObject
0x14005a5f6  jmp     short loc_14005A631
0x14005a5f8  mov     rcx, cs:WPP_GLOBAL_Control
0x14005a5ff  lea     rax, WPP_GLOBAL_Control
0x14005a606  cmp     rcx, rax
0x14005a609  jz      short loc_14005A62F
0x14005a60b  test    [rcx+1Ch], edi
0x14005a60e  jz      short loc_14005A62F
  ... truncated ...
```
