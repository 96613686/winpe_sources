# ExecuteSetup(void *)

- ea: `0x14007e078`
- end: `0x14007e460`
- name: `?ExecuteSetup@@YAKPEAX@Z`
- size: `1000`
- prototype: `unsigned int __fastcall(void *)`
- caller_count: `1`
- callee_count: `14`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x1400873d4`

## callees

- `0x1400057f4`
- `0x14000d4e0`
- `0x14000fb30`
- `0x140041c34`
- `0x14004ea3c`
- `0x140053720`
- `0x1400544e0`
- `0x14007e078`
- `0x14007e468`
- `0x14007e750`
- `0x14007eb84`
- `0x140099c0c`
- `0x140099e54`
- `0x14009cbd0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x14007e36e`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x14007e36e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14007e26e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14007e2d0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14007e3c4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14007e26e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14007e2d0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14007e3c4`
- `api-ms-win-core-processthreads-l1-1-0!GetExitCodeProcess` at `0x14007e389`
- `api-ms-win-core-processthreads-l1-1-0!GetExitCodeProcess` at `0x14007e389`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14007e2c6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14007e323`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14007e429`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14007e2c6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14007e323`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14007e429`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x14007e175`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x14007e175`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x14007e15f`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x14007e15f`
- `KERNELBASE!CreateProcessInternalW` at `0x14007e2b9`
- `KERNELBASE!CreateProcessInternalW` at `0x14007e2b9`
- `ext-ms-win-ntuser-keyboard-l1-1-0!GetAsyncKeyState` at `0x14007e184`
- `ext-ms-win-ntuser-keyboard-l1-1-0!GetAsyncKeyState` at `0x14007e192`
- `ext-ms-win-ntuser-keyboard-l1-1-0!GetAsyncKeyState` at `0x14007e184`
- `ext-ms-win-ntuser-keyboard-l1-1-0!GetAsyncKeyState` at `0x14007e192`

## pseudocode

```c
__int64 __fastcall ExecuteSetup(void *a1)
{
  __int64 v2; // rbx
  unsigned int v3; // edx
  void *v4; // rdi
  SHORT AsyncKeyState; // bx
  SHORT v6; // ax
  __int16 v7; // cx
  const wchar_t *v8; // r9
  int v9; // ebx
  DWORD v10; // eax
  __int64 v11; // r9
  DWORD v12; // ebx
  DWORD v13; // eax
  __int64 v14; // r9
  CUser *v15; // rcx
  __int64 v16; // rdx
  DWORD LastError; // eax
  HANDLE hObject; // [rsp+60h] [rbp-A0h] BYREF
  DWORD ExitCode; // [rsp+68h] [rbp-98h] BYREF
  HKEY hKey; // [rsp+70h] [rbp-90h] BYREF
  HANDLE hHandle[2]; // [rsp+78h] [rbp-88h] BYREF
  __int64 v23; // [rsp+88h] [rbp-78h]
  __int64 v24; // [rsp+90h] [rbp-70h] BYREF
  int v25; // [rsp+A0h] [rbp-60h] BYREF
  void *v26; // [rsp+A8h] [rbp-58h]
  const wchar_t *v27; // [rsp+B0h] [rbp-50h]
  void *v28; // [rsp+B8h] [rbp-48h]
  int v29; // [rsp+DCh] [rbp-24h]
  __int16 v30; // [rsp+E0h] [rbp-20h]
  BYTE Data[2048]; // [rsp+110h] [rbp+10h] BYREF
  unsigned __int16 v32[1024]; // [rsp+910h] [rbp+810h] BYREF

  memset_0(Data, 0, sizeof(Data));
  hKey = 0;
  memset_0(&v25, 0, 0x68u);
  v23 = 0;
  v2 = 0;
  hObject = (HANDLE)-1LL;
  v24 = -1;
  *(_OWORD *)hHandle = 0;
  do
    UpdateRegistryItem((struct _REG_CHANGE *)(&WinlogonSetupChanges + 3 * v2++));
  while ( v2 != 6 );
  PrepareSetupExecution(Data, v3, &ExitCode);
  if ( dword_1400D33C4 != 1 )
    MicrosoftTelemetryAssertTriggeredNoArgs();
  if ( dword_1400D33C0 == 1 )
  {
    hKey = 0;
    if ( !RegOpenKeyExW(
            HKEY_LOCAL_MACHINE,
            L"Software\\Microsoft\\Windows NT\\CurrentVersion\\Winlogon",
            0,
            0x2001Bu,
            &hKey) )
      RegDeleteValueW(hKey, L"AutoAdminLogon");
  }
  v4 = Data;
  AsyncKeyState = GetAsyncKeyState(160);
  v6 = GetAsyncKeyState(161);
  if ( WinlogonDebugSetup )
    v7 = 0x8000;
  else
    v7 = v6;
  if ( ((AsyncKeyState | v7) & 0x8000u) != 0 )
  {
    v8 = L"-d";
    if ( v7 >= 0 )
      v8 = (const wchar_t *)&pPassword;
    StringCchPrintfW(v32, 0x400u, L"ntsd %s %s", v8, Data);
    v4 = v32;
  }
  memset_0(&v25, 0, 0x68u);
  v25 = 104;
  v30 = 5;
  v26 = v4;
  v27 = L"winsta0\\Default";
  v28 = v4;
  v29 = 1;
  if ( !(unsigned int)GetTiToken(&hObject) )
  {
    if ( WPP_GLOBAL_Control != (CUser *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, WPP_f970564fce7b32792e727784e751b97c_Traceguids, v4);
    }
    GetLastError();
  }
  v9 = CreateProcessInternalW(hObject, 0, v4, 0, 0, 0, 1024, a1, 0, &v25, hHandle, &v24);
  CloseHandle(hObject);
  if ( v9 )
  {
    ExitCode = 0;
    CloseHandle(hHandle[1]);
    v12 = g_fWinPEMode != 0 ? 864000000 : -1;
    if ( WPP_GLOBAL_Control != (CUser *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 12, WPP_f970564fce7b32792e727784e751b97c_Traceguids, v11);
    }
    v13 = WaitForSingleObject(hHandle[0], v12);
    if ( v13 == 258 )
    {
      LODWORD(hObject) = 1460;
      if ( WPP_GLOBAL_Control != (CUser *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 13, WPP_f970564fce7b32792e727784e751b97c_Traceguids, v12);
      }
      goto LABEL_45;
    }
    if ( v13 == -1 )
    {
      LastError = GetLastError();
      LODWORD(hObject) = LastError;
      v15 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (CUser *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_45;
      }
      v16 = 14;
      v14 = LastError;
    }
    else
    {
      GetExitCodeProcess(hHandle[0], &ExitCode);
      v14 = ExitCode;
      LODWORD(hObject) = ExitCode;
      v15 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (CUser *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 5u )
      {
        goto LABEL_45;
      }
      v16 = 15;
    }
    WPP_SF_d(*((_QWORD *)v15 + 2), v16, WPP_f970564fce7b32792e727784e751b97c_Traceguids, v14);
LABEL_45:
    CloseHandle(hHandle[0]);
    goto LABEL_46;
  }
  v10 = GetLastError();
  LODWORD(hObject) = v10;
  if ( WPP_GLOBAL_Control != (CUser *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_DS(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      11,
      (unsigned int)WPP_f970564fce7b32792e727784e751b97c_Traceguids,
      v10,
      (__int64)v4);
  }
LABEL_46:
  SetSetupExitCode((unsigned int *)&hObject);
  return (unsigned int)hObject;
}

```

## disassembly

```asm
0x14007e078  push    rbp
0x14007e07a  push    rbx
0x14007e07b  push    rsi
0x14007e07c  push    rdi
0x14007e07d  push    r12
0x14007e07f  push    r13
0x14007e081  push    r14
0x14007e083  push    r15
0x14007e085  lea     rbp, [rsp-1028h]
0x14007e08d  mov     eax, 1128h
0x14007e092  call    _alloca_probe
0x14007e097  sub     rsp, rax
0x14007e09a  mov     rax, cs:__security_cookie
0x14007e0a1  xor     rax, rsp
0x14007e0a4  mov     [rbp+1060h+var_50], rax
0x14007e0ab  mov     rsi, rcx
0x14007e0ae  xor     edx, edx; Val
0x14007e0b0  lea     rcx, [rbp+1060h+Data]; void *
0x14007e0b4  mov     r8d, 800h; Size
0x14007e0ba  call    memset_0
0x14007e0bf  xor     r15d, r15d
0x14007e0c2  lea     rcx, [rbp+1060h+var_10C0]; void *
0x14007e0c6  xor     edx, edx; Val
0x14007e0c8  mov     [rsp+1160h+hKey], r15
0x14007e0cd  lea     r14d, [r15+68h]
0x14007e0d1  mov     r8d, r14d; Size
0x14007e0d4  call    memset_0
0x14007e0d9  xor     eax, eax
0x14007e0db  xorps   xmm0, xmm0
0x14007e0de  mov     [rbp+1060h+var_10D8], rax
0x14007e0e2  mov     ebx, r15d
0x14007e0e5  or      rax, 0FFFFFFFFFFFFFFFFh
0x14007e0e9  mov     [rsp+1160h+hObject], rax
0x14007e0ee  mov     [rbp+1060h+var_10D0], rax
0x14007e0f2  movups  xmmword ptr [rsp+1160h+hHandle], xmm0
0x14007e0f7  lea     rax, [rbx+rbx*2]
0x14007e0fb  lea     rcx, ?WinlogonSetupChanges@@3PAU_REG_CHANGE@@A; _REG_CHANGE near * WinlogonSetupChanges
0x14007e102  lea     rcx, [rcx+rax*8]; struct _REG_CHANGE *
0x14007e106  call    ?UpdateRegistryItem@@YAXPEAU_REG_CHANGE@@@Z; UpdateRegistryItem(_REG_CHANGE *)
0x14007e10b  inc     rbx
0x14007e10e  cmp     rbx, 6
0x14007e112  jnz     short loc_14007E0F7
0x14007e114  lea     r8, [rsp+1160h+ExitCode]; unsigned int *
0x14007e119  lea     rcx, [rbp+1060h+Data]; lpData
0x14007e11d  call    ?PrepareSetupExecution@@YAXPEAGKPEAK@Z; PrepareSetupExecution(ushort *,ulong,ulong *)
0x14007e122  cmp     cs:dword_1400D33C4, 1
0x14007e129  jz      short loc_14007E130
0x14007e12b  call    MicrosoftTelemetryAssertTriggeredNoArgs; __annotation("Debug", "TelemetryAssert", "TRUE == s_fSetupTypeChecked")
0x14007e130  cmp     cs:dword_1400D33C0, 1
0x14007e137  jnz     short loc_14007E17B
0x14007e139  lea     rax, [rsp+1160h+hKey]
0x14007e13e  mov     [rsp+1160h+hKey], r15
0x14007e143  mov     r9d, 2001Bh; samDesired
0x14007e149  mov     [rsp+1160h+phkResult], rax; phkResult
0x14007e14e  xor     r8d, r8d; ulOptions
0x14007e151  lea     rdx, aSoftwareMicros_48; "Software\\Microsoft\\Windows NT\\Curren"...
0x14007e158  mov     rcx, 0FFFFFFFF80000002h; hKey
0x14007e15f  call    cs:__imp_RegOpenKeyExW
0x14007e165  test    eax, eax
0x14007e167  jnz     short loc_14007E17B
0x14007e169  mov     rcx, [rsp+1160h+hKey]; hKey
0x14007e16e  lea     rdx, aAutoadminlogon; "AutoAdminLogon"
0x14007e175  call    cs:__imp_RegDeleteValueW
0x14007e17b  mov     ecx, 0A0h; vKey
0x14007e180  lea     rdi, [rbp+1060h+Data]
0x14007e184  call    cs:__imp_GetAsyncKeyState
0x14007e18a  mov     ecx, 0A1h; vKey
0x14007e18f  movzx   ebx, ax
0x14007e192  call    cs:__imp_GetAsyncKeyState
0x14007e198  cmp     cs:?WinlogonDebugSetup@@3HA, r15d; int WinlogonDebugSetup
0x14007e19f  jz      short loc_14007E1A8
0x14007e1a1  mov     ecx, 8000h
0x14007e1a6  jmp     short loc_14007E1AB
0x14007e1a8  movzx   ecx, ax
0x14007e1ab  movzx   eax, cx
0x14007e1ae  or      ax, bx
0x14007e1b1  jge     short loc_14007E1F0
0x14007e1b3  test    cx, cx
0x14007e1b6  lea     rax, pPassword
0x14007e1bd  lea     r9, aD_0; "-d"
0x14007e1c4  mov     edx, 400h; unsigned __int64
0x14007e1c9  cmovns  r9, rax
0x14007e1cd  lea     r8, aNtsdSS; "ntsd %s %s"
0x14007e1d4  lea     rax, [rbp+1060h+Data]
0x14007e1d8  lea     rcx, [rbp+1060h+var_850]; unsigned __int16 *
0x14007e1df  mov     [rsp+1160h+phkResult], rax
0x14007e1e4  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x14007e1e9  lea     rdi, [rbp+1060h+var_850]
0x14007e1f0  mov     r8, r14; Size
0x14007e1f3  lea     rcx, [rbp+1060h+var_10C0]; void *
0x14007e1f7  xor     edx, edx; Val
0x14007e1f9  call    memset_0
0x14007e1fe  mov     eax, 5
0x14007e203  mov     [rbp+1060h+var_10C0], r14d
0x14007e207  mov     [rbp+1060h+var_1080], ax
0x14007e20b  lea     rcx, [rsp+1160h+hObject]; void **
0x14007e210  lea     rax, aWinsta0Default_0; "winsta0\\Default"
0x14007e217  mov     [rbp+1060h+var_10B8], rdi
0x14007e21b  mov     [rbp+1060h+var_10B0], rax
0x14007e21f  mov     [rbp+1060h+var_10A8], rdi
0x14007e223  mov     [rbp+1060h+var_1084], 1
0x14007e22a  call    ?GetTiToken@@YAHPEAPEAX@Z; GetTiToken(void * *)
0x14007e22f  lea     r12, WPP_GLOBAL_Control
0x14007e236  mov     r14b, 2
0x14007e239  lea     r13, WPP_f970564fce7b32792e727784e751b97c_Traceguids
0x14007e240  test    eax, eax
0x14007e242  jnz     short loc_14007E274
0x14007e244  mov     rcx, cs:WPP_GLOBAL_Control
0x14007e24b  cmp     rcx, r12
0x14007e24e  jz      short loc_14007E26E
0x14007e250  test    [rcx+1Ch], r14b
0x14007e254  jz      short loc_14007E26E
0x14007e256  cmp     [rcx+19h], r14b
0x14007e25a  jb      short loc_14007E26E
0x14007e25c  mov     rcx, [rcx+10h]
0x14007e260  lea     edx, [rax+0Ah]
0x14007e263  mov     r9, rdi
0x14007e266  mov     r8, r13
0x14007e269  call    WPP_SF_S
0x14007e26e  call    cs:__imp_GetLastError
0x14007e274  mov     rcx, [rsp+1160h+hObject]
0x14007e279  lea     rax, [rbp+1060h+var_10D0]
0x14007e27d  mov     [rsp+1160h+var_1108], rax
0x14007e282  xor     r9d, r9d
0x14007e285  lea     rax, [rsp+1160h+hHandle]
0x14007e28a  mov     r8, rdi
0x14007e28d  mov     [rsp+1160h+var_1110], rax
0x14007e292  xor     edx, edx
0x14007e294  lea     rax, [rbp+1060h+var_10C0]
0x14007e298  mov     [rsp+1160h+var_1118], rax
0x14007e29d  mov     [rsp+1160h+var_1120], r15
0x14007e2a2  mov     [rsp+1160h+var_1128], rsi
0x14007e2a7  mov     [rsp+1160h+var_1130], 400h
0x14007e2af  mov     [rsp+1160h+var_1138], r15d
0x14007e2b4  mov     [rsp+1160h+phkResult], r15
0x14007e2b9  call    cs:__imp_CreateProcessInternalW
0x14007e2bf  mov     rcx, [rsp+1160h+hObject]; hObject
0x14007e2c4  mov     ebx, eax
0x14007e2c6  call    cs:__imp_CloseHandle
0x14007e2cc  test    ebx, ebx
0x14007e2ce  jnz     short loc_14007E31A
0x14007e2d0  call    cs:__imp_GetLastError
0x14007e2d6  mov     dword ptr [rsp+1160h+hObject], eax
0x14007e2da  mov     rcx, cs:WPP_GLOBAL_Control
0x14007e2e1  cmp     rcx, r12
0x14007e2e4  jz      loc_14007E42F
0x14007e2ea  test    [rcx+1Ch], r14b
0x14007e2ee  jz      loc_14007E42F
0x14007e2f4  cmp     [rcx+19h], r14b
0x14007e2f8  jb      loc_14007E42F
0x14007e2fe  mov     rcx, [rcx+10h]
0x14007e302  lea     edx, [rbx+0Bh]
0x14007e305  mov     r9d, eax
0x14007e308  mov     [rsp+1160h+phkResult], rdi
0x14007e30d  mov     r8, r13
0x14007e310  call    WPP_SF_DS
0x14007e315  jmp     loc_14007E42F
0x14007e31a  mov     rcx, [rbp+1060h+hHandle+8]; hObject
0x14007e31e  mov     [rsp+1160h+ExitCode], r15d
0x14007e323  call    cs:__imp_CloseHandle
0x14007e329  mov     eax, cs:?g_fWinPEMode@@3HA; int g_fWinPEMode
0x14007e32f  neg     eax
0x14007e331  sbb     ebx, ebx
0x14007e333  or      edi, 0FFFFFFFFh
0x14007e336  and     ebx, 337F9801h
0x14007e33c  add     ebx, edi
0x14007e33e  mov     rcx, cs:WPP_GLOBAL_Control
0x14007e345  cmp     rcx, r12
0x14007e348  jz      short loc_14007E367
0x14007e34a  test    [rcx+1Ch], r14b
0x14007e34e  jz      short loc_14007E367
0x14007e350  cmp     byte ptr [rcx+19h], 5
0x14007e354  jb      short loc_14007E367
0x14007e356  mov     rcx, [rcx+10h]
0x14007e35a  mov     edx, 0Ch
0x14007e35f  mov     r8, r13
0x14007e362  call    WPP_SF_
0x14007e367  mov     rcx, [rsp+1160h+hHandle]; hHandle
0x14007e36c  mov     edx, ebx; dwMilliseconds
0x14007e36e  call    cs:__imp_WaitForSingleObject
0x14007e374  cmp     eax, 102h
0x14007e379  jz      short loc_14007E3F0
0x14007e37b  cmp     eax, edi
0x14007e37d  jz      short loc_14007E3C4
0x14007e37f  mov     rcx, [rsp+1160h+hHandle]; hProcess
0x14007e384  lea     rdx, [rsp+1160h+ExitCode]; lpExitCode
0x14007e389  call    cs:__imp_GetExitCodeProcess
0x14007e38f  mov     r9d, [rsp+1160h+ExitCode]
0x14007e394  mov     dword ptr [rsp+1160h+hObject], r9d
0x14007e399  mov     rcx, cs:WPP_GLOBAL_Control
0x14007e3a0  cmp     rcx, r12
0x14007e3a3  jz      short loc_14007E424
0x14007e3a5  test    [rcx+1Ch], r14b
0x14007e3a9  jz      short loc_14007E424
0x14007e3ab  cmp     byte ptr [rcx+19h], 5
0x14007e3af  jb      short loc_14007E424
0x14007e3b1  mov     edx, 0Fh
0x14007e3b6  mov     rcx, [rcx+10h]
0x14007e3ba  mov     r8, r13
0x14007e3bd  call    WPP_SF_d
0x14007e3c2  jmp     short loc_14007E424
0x14007e3c4  call    cs:__imp_GetLastError
0x14007e3ca  mov     dword ptr [rsp+1160h+hObject], eax
0x14007e3ce  mov     rcx, cs:WPP_GLOBAL_Control
0x14007e3d5  cmp     rcx, r12
0x14007e3d8  jz      short loc_14007E424
0x14007e3da  test    [rcx+1Ch], r14b
0x14007e3de  jz      short loc_14007E424
0x14007e3e0  cmp     [rcx+19h], r14b
0x14007e3e4  jb      short loc_14007E424
0x14007e3e6  mov     edx, 0Eh
0x14007e3eb  mov     r9d, eax
0x14007e3ee  jmp     short loc_14007E3B6
0x14007e3f0  mov     dword ptr [rsp+1160h+hObject], 5B4h
0x14007e3f8  mov     rcx, cs:WPP_GLOBAL_Control
0x14007e3ff  cmp     rcx, r12
0x14007e402  jz      short loc_14007E424
0x14007e404  test    [rcx+1Ch], r14b
0x14007e408  jz      short loc_14007E424
0x14007e40a  cmp     [rcx+19h], r14b
0x14007e40e  jb      short loc_14007E424
0x14007e410  mov     rcx, [rcx+10h]
0x14007e414  mov     edx, 0Dh
0x14007e419  mov     r9d, ebx
0x14007e41c  mov     r8, r13
0x14007e41f  call    WPP_SF_d
0x14007e424  mov     rcx, [rsp+1160h+hHandle]; hObject
0x14007e429  call    cs:__imp_CloseHandle
0x14007e42f  lea     rcx, [rsp+1160h+hObject]; unsigned int *
0x14007e434  call    ?SetSetupExitCode@@YAXPEAK@Z; SetSetupExitCode(ulong *)
0x14007e439  mov     eax, dword ptr [rsp+1160h+hObject]
0x14007e43d  mov     rcx, [rbp+1060h+var_50]
0x14007e444  xor     rcx, rsp; StackCookie
0x14007e447  call    __security_check_cookie
0x14007e44c  add     rsp, 1128h
0x14007e453  pop     r15
0x14007e455  pop     r14
0x14007e457  pop     r13
0x14007e459  pop     r12
0x14007e45b  pop     rdi
0x14007e45c  pop     rsi
0x14007e45d  pop     rbx
0x14007e45e  pop     rbp
0x14007e45f  retn
```
