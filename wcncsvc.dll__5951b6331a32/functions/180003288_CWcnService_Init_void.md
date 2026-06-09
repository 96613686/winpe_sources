# CWcnService::Init(void)

- ea: `0x180003288`
- end: `0x180003837`
- name: `?Init@CWcnService@@QEAAJXZ`
- size: `1455`
- prototype: `__int64 __fastcall(CWcnService *this, __int64)`
- caller_count: `1`
- callee_count: `11`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x1800054a0`

## callees

- `0x180003288`
- `0x180003ad0`
- `0x180003b98`
- `0x180003dec`
- `0x180004ed8`
- `0x180004f2c`
- `0x180004f78`
- `0x180004fb8`
- `0x180005014`
- `0x180053004`
- `0x18005a010`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000342e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000342e`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000339d`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000339d`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180003406`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180003406`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180003655`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180003655`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003504`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003667`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003671`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000367b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003504`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003667`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003671`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000367b`
- `api-ms-win-service-core-l1-1-0!RegisterServiceCtrlHandlerExW` at `0x1800034f6`
- `api-ms-win-service-core-l1-1-0!RegisterServiceCtrlHandlerExW` at `0x1800034f6`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CWcnService::Init(CWcnService *this, __int64 a2)
{
  CWcnService *v2; // rdi
  unsigned int v3; // esi
  const char *Indent; // rax
  __int64 v5; // r10
  __int64 v6; // rdx
  _BYTE *v7; // r10
  const char *v8; // rax
  __int64 v9; // r10
  const char *v10; // rax
  __int64 v11; // r10
  int v12; // ebx
  _BYTE *v13; // r10
  unsigned int v14; // eax
  __int64 v15; // r10
  char v16; // r11
  const char *v17; // rax
  __int64 v18; // r10
  const char *v19; // rax
  __int64 v20; // r10
  const char *v21; // rax
  __int64 v22; // r10
  SERVICE_STATUS_HANDLE v23; // rax
  signed int LastError; // r11d
  signed int v25; // ebx
  unsigned int v26; // ebx
  _BYTE *v27; // r10
  unsigned int v28; // eax
  __int64 v29; // r10
  char v30; // r11
  const char *v31; // rax
  __int64 v32; // r10
  __int64 v33; // rdx
  int started; // eax
  __int64 v35; // rcx
  __int64 v36; // r9
  const char *v37; // rax
  __int64 v38; // r10
  HANDLE EventW; // rax
  unsigned int v40; // ebx
  unsigned int v41; // eax
  __int64 v42; // r10
  int v43; // eax
  unsigned int v44; // ebx
  unsigned int v45; // eax
  __int64 v46; // r10
  const char *v47; // rax
  __int64 v48; // r10
  unsigned int v49; // eax
  __int64 v50; // r10
  CWcnService *cbData; // [rsp+70h] [rbp+8h] BYREF
  int Data; // [rsp+78h] [rbp+10h] BYREF
  HKEY hKey; // [rsp+80h] [rbp+18h] BYREF

  cbData = this;
  v2 = g_pWcnService;
  v3 = 1;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    Indent = GetIndent(1);
    WPP_SF_s(*(_QWORD *)(v5 + 16), 12, WPP_ac811424b605344d9cc8b73f32b92b60_Traceguids, Indent);
  }
  McGenEventRegister_EtwEventRegister(WCN_ETW_EVENT_GUID, a2, WCN_ETW_EVENT_GUID_Context, WCN_ETW_EVENT_GUID_Context);
  McGenEventRegister_EtwEventRegister(
    WCN_ETW_SECURE_EVENT_GUID,
    v6,
    WCN_ETW_SECURE_EVENT_GUID_Context,
    WCN_ETW_SECURE_EVENT_GUID_Context);
  v7 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
  {
    if ( *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    {
      v8 = GetIndent(0);
      WPP_SF_s(*(_QWORD *)(v9 + 16), 13, WPP_ac811424b605344d9cc8b73f32b92b60_Traceguids, v8);
      v7 = WPP_GLOBAL_Control;
    }
    if ( v7 != (_BYTE *)&WPP_GLOBAL_Control && v7[25] >= 6u )
    {
      v10 = GetIndent(1);
      WPP_SF_s(*(_QWORD *)(v11 + 16), 65, WPP_ac811424b605344d9cc8b73f32b92b60_Traceguids, v10);
    }
  }
  v12 = 0;
  LODWORD(cbData) = 4;
  hKey = 0;
  Data = 0;
  if ( !RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"Software\\Microsoft\\Windows\\CurrentVersion\\WCN", 0, 1u, &hKey) )
  {
    if ( !RegQueryValueExW(hKey, L"WSCVersion", 0, 0, (LPBYTE)&Data, (LPDWORD)&cbData) && (_DWORD)cbData == 4 )
      v12 = Data;
    goto LABEL_17;
  }
  v13 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    v14 = (unsigned int)GetIndent(0);
    WPP_SF_sd(*(_QWORD *)(v15 + 16), 66, (unsigned int)WPP_ac811424b605344d9cc8b73f32b92b60_Traceguids, v14, v16);
LABEL_17:
    v13 = WPP_GLOBAL_Control;
  }
  if ( hKey )
  {
    RegCloseKey(hKey);
    v13 = WPP_GLOBAL_Control;
  }
  if ( v13 != (_BYTE *)&WPP_GLOBAL_Control && v13[25] >= 6u )
  {
    v17 = GetIndent(-1);
    WPP_SF_s(*(_QWORD *)(v18 + 16), 67, WPP_ac811424b605344d9cc8b73f32b92b60_Traceguids, v17);
    v13 = WPP_GLOBAL_Control;
  }
  if ( v12 )
  {
    if ( v12 == 16 )
    {
      CWcnService::m_VersionOverride = 16;
    }
    else if ( v12 == 32 )
    {
      CWcnService::m_VersionOverride = 32;
    }
    else
    {
      if ( v13 == (_BYTE *)&WPP_GLOBAL_Control )
        goto LABEL_34;
      if ( v13[25] >= 3u )
      {
        v19 = GetIndent(0);
        WPP_SF_s(*(_QWORD *)(v20 + 16), 14, WPP_ac811424b605344d9cc8b73f32b92b60_Traceguids, v19);
        v13 = WPP_GLOBAL_Control;
      }
    }
  }
  if ( v13 != (_BYTE *)&WPP_GLOBAL_Control && v13[25] >= 6u )
  {
    v21 = GetIndent(1);
    WPP_SF_s(*(_QWORD *)(v22 + 16), 25, WPP_ac811424b605344d9cc8b73f32b92b60_Traceguids, v21);
  }
LABEL_34:
  v23 = RegisterServiceCtrlHandlerExW(L"wcncsvc", WcnServiceControlMessageHandlerThunk, v2);
  *(_QWORD *)v2 = v23;
  if ( v23 )
  {
    v25 = 0;
    *(_QWORD *)((char *)v2 + 28) = 1;
    *(_QWORD *)((char *)v2 + 20) = 0;
    *((_DWORD *)v2 + 2) = 32;
    *(_QWORD *)((char *)v2 + 12) = 2;
    CWcnService::NotifyStatus(v2, 2u);
    goto LABEL_45;
  }
  LastError = GetLastError();
  if ( LastError )
  {
    if ( LastError > 0 )
      v26 = (unsigned __int16)LastError | 0x80070000;
    else
      v26 = LastError;
    v25 = v26 | 0x80000000;
  }
  else
  {
    v25 = 0;
  }
  v27 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
    goto LABEL_49;
  if ( *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    v28 = (unsigned int)GetIndent(0);
    WPP_SF_sd(*(_QWORD *)(v29 + 16), 26, (unsigned int)WPP_ac811424b605344d9cc8b73f32b92b60_Traceguids, v28, v30);
LABEL_45:
    v27 = WPP_GLOBAL_Control;
  }
  if ( v27 != (_BYTE *)&WPP_GLOBAL_Control && v27[25] >= 6u )
  {
    v31 = GetIndent(-1);
    WPP_SF_s(*(_QWORD *)(v32 + 16), 27, WPP_ac811424b605344d9cc8b73f32b92b60_Traceguids, v31);
    v27 = WPP_GLOBAL_Control;
  }
LABEL_49:
  if ( v25 < 0 )
  {
    if ( v27 == (_BYTE *)&WPP_GLOBAL_Control || v27[25] < 2u )
      goto LABEL_86;
    v33 = 15;
    goto LABEL_84;
  }
  started = CWcnService::StartSubsystems(v2);
  v25 = started;
  if ( started < 0 )
  {
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      goto LABEL_86;
    v35 = *((_QWORD *)WPP_GLOBAL_Control + 2);
    v33 = 16;
    v36 = (unsigned int)started;
    goto LABEL_85;
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    v37 = GetIndent(1);
    WPP_SF_s(*(_QWORD *)(v38 + 16), 28, WPP_ac811424b605344d9cc8b73f32b92b60_Traceguids, v37);
  }
  EventW = CreateEventW(0, 0, 0, 0);
  *((_QWORD *)v2 + 5) = EventW;
  if ( !EventW )
  {
    if ( (int)GetLastError() > 0 )
      v40 = (unsigned __int16)GetLastError() | 0x80070000;
    else
      v40 = GetLastError();
    v25 = v40 | 0x80000000;
    v27 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
      goto LABEL_80;
    if ( *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      goto LABEL_76;
    v41 = (unsigned int)GetIndent(0);
    WPP_SF_sd(*(_QWORD *)(v42 + 16), 29, (unsigned int)WPP_ac811424b605344d9cc8b73f32b92b60_Traceguids, v41, v25);
    goto LABEL_75;
  }
  v43 = (*((__int64 (__fastcall **)(__int64, const WCHAR *, HANDLE, __int64 (__fastcall *)(CWcnService *), CWcnService *, int))g_pSvchostGlobalData
         + 24))(
          (__int64)v2 + 48,
          L"wcncsvc",
          EventW,
          WcnServiceStopEventThunk,
          v2,
          24);
  if ( !v43 )
  {
    v25 = 0;
    goto LABEL_75;
  }
  if ( v43 > 0 )
    v44 = (unsigned __int16)v43 | 0x80070000;
  else
    v44 = v43;
  v25 = v44 | 0x80000000;
  v27 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
    goto LABEL_80;
  if ( *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_Dd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      30,
      WPP_ac811424b605344d9cc8b73f32b92b60_Traceguids,
      (unsigned int)v43,
      v25);
LABEL_75:
    v27 = WPP_GLOBAL_Control;
  }
LABEL_76:
  if ( v27 != (_BYTE *)&WPP_GLOBAL_Control && (v25 < 0 || v27[25] >= 6u) )
  {
    v45 = (unsigned int)GetIndent(-1);
    WPP_SF_sd(*(_QWORD *)(v46 + 16), 31, (unsigned int)WPP_ac811424b605344d9cc8b73f32b92b60_Traceguids, v45, v25);
    v27 = WPP_GLOBAL_Control;
  }
LABEL_80:
  if ( v25 < 0 )
  {
    if ( v27 == (_BYTE *)&WPP_GLOBAL_Control || v27[25] < 2u )
      goto LABEL_86;
    v33 = 17;
LABEL_84:
    v35 = *((_QWORD *)v27 + 2);
    v36 = (unsigned int)v25;
LABEL_85:
    WPP_SF_d(v35, v33, WPP_ac811424b605344d9cc8b73f32b92b60_Traceguids, v36);
LABEL_86:
    *((_DWORD *)v2 + 5) = 1066;
    *((_DWORD *)v2 + 6) = v25;
    CWcnService::Shutdown(v2);
    goto LABEL_91;
  }
  if ( v27 != (_BYTE *)&WPP_GLOBAL_Control && v27[25] >= 4u )
  {
    v47 = GetIndent(0);
    WPP_SF_s(*(_QWORD *)(v48 + 16), 18, WPP_ac811424b605344d9cc8b73f32b92b60_Traceguids, v47);
  }
  v3 = 4;
LABEL_91:
  CWcnService::NotifyStatus(v2, v3);
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (v25 < 0 || *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u) )
  {
    v49 = (unsigned int)GetIndent(-1);
    WPP_SF_sd(*(_QWORD *)(v50 + 16), 20, (unsigned int)WPP_ac811424b605344d9cc8b73f32b92b60_Traceguids, v49, v25);
  }
  return (unsigned int)v25;
}

```

## disassembly

```asm
0x180003288  mov     [rsp+cbData], rcx
0x18000328d  push    rbx
0x18000328e  push    rsi
0x18000328f  push    rdi
0x180003290  push    r14
0x180003292  push    r15
0x180003294  sub     rsp, 40h
0x180003298  mov     rdi, cs:?g_pWcnService@@3PEAVCWcnService@@EA; CWcnService * g_pWcnService
0x18000329f  mov     r10, cs:WPP_GLOBAL_Control
0x1800032a6  lea     r14, WPP_GLOBAL_Control
0x1800032ad  lea     r15, WPP_ac811424b605344d9cc8b73f32b92b60_Traceguids
0x1800032b4  mov     esi, 1
0x1800032b9  cmp     r10, r14
0x1800032bc  jz      short loc_1800032DE
0x1800032be  cmp     byte ptr [r10+19h], 6
0x1800032c3  jb      short loc_1800032DE
0x1800032c5  mov     ecx, esi; int
0x1800032c7  call    ?GetIndent@@YAPEBDH@Z; GetIndent(int)
0x1800032cc  mov     rcx, [r10+10h]
0x1800032d0  lea     edx, [rsi+0Bh]
0x1800032d3  mov     r9, rax
0x1800032d6  mov     r8, r15
0x1800032d9  call    WPP_SF_s
0x1800032de  lea     r8, WCN_ETW_EVENT_GUID_Context
0x1800032e5  mov     r9, r8
0x1800032e8  lea     rcx, WCN_ETW_EVENT_GUID
0x1800032ef  call    McGenEventRegister_EtwEventRegister
0x1800032f4  lea     r8, WCN_ETW_SECURE_EVENT_GUID_Context
0x1800032fb  mov     r9, r8
0x1800032fe  lea     rcx, WCN_ETW_SECURE_EVENT_GUID
0x180003305  call    McGenEventRegister_EtwEventRegister
0x18000330a  mov     r10, cs:WPP_GLOBAL_Control
0x180003311  cmp     r10, r14
0x180003314  jz      short loc_180003366
0x180003316  cmp     byte ptr [r10+19h], 4
0x18000331b  jb      short loc_18000333F
0x18000331d  xor     ecx, ecx; int
0x18000331f  call    ?GetIndent@@YAPEBDH@Z; GetIndent(int)
0x180003324  mov     rcx, [r10+10h]
0x180003328  mov     edx, 0Dh
0x18000332d  mov     r9, rax
0x180003330  mov     r8, r15
0x180003333  call    WPP_SF_s
0x180003338  mov     r10, cs:WPP_GLOBAL_Control
0x18000333f  cmp     r10, r14
0x180003342  jz      short loc_180003366
0x180003344  cmp     byte ptr [r10+19h], 6
0x180003349  jb      short loc_180003366
0x18000334b  mov     ecx, esi; int
0x18000334d  call    ?GetIndent@@YAPEBDH@Z; GetIndent(int)
0x180003352  mov     rcx, [r10+10h]
0x180003356  mov     edx, 41h ; 'A'
0x18000335b  mov     r9, rax
0x18000335e  mov     r8, r15
0x180003361  call    WPP_SF_s
0x180003366  xor     ebx, ebx
0x180003368  mov     dword ptr [rsp+68h+cbData], 4
0x180003370  lea     rax, [rsp+68h+hKey]
0x180003378  mov     [rsp+68h+hKey], rbx
0x180003380  mov     r9d, esi; samDesired
0x180003383  mov     [rsp+68h+Data], ebx
0x180003387  xor     r8d, r8d; ulOptions
0x18000338a  mov     [rsp+68h+phkResult], rax; phkResult
0x18000338f  lea     rdx, SubKey; "Software\\Microsoft\\Windows\\CurrentVe"...
0x180003396  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18000339d  call    cs:__imp_RegOpenKeyExW
0x1800033a3  mov     r11d, eax
0x1800033a6  test    eax, eax
0x1800033a8  jz      short loc_1800033DD
0x1800033aa  mov     r10, cs:WPP_GLOBAL_Control
0x1800033b1  cmp     r10, r14
0x1800033b4  jz      short loc_180003421
0x1800033b6  cmp     byte ptr [r10+19h], 5
0x1800033bb  jb      short loc_180003421
0x1800033bd  xor     ecx, ecx; int
0x1800033bf  call    ?GetIndent@@YAPEBDH@Z; GetIndent(int)
0x1800033c4  mov     rcx, [r10+10h]
0x1800033c8  lea     edx, [rbx+42h]
0x1800033cb  mov     r9, rax
0x1800033ce  mov     dword ptr [rsp+68h+phkResult], r11d
0x1800033d3  mov     r8, r15
0x1800033d6  call    WPP_SF_sd
0x1800033db  jmp     short loc_18000341A
0x1800033dd  mov     rcx, [rsp+68h+hKey]; hKey
0x1800033e5  lea     rax, [rsp+68h+cbData]
0x1800033ea  mov     [rsp+68h+lpcbData], rax; lpcbData
0x1800033ef  lea     rdx, ValueName; "WSCVersion"
0x1800033f6  lea     rax, [rsp+68h+Data]
0x1800033fb  xor     r9d, r9d; lpType
0x1800033fe  xor     r8d, r8d; lpReserved
0x180003401  mov     [rsp+68h+phkResult], rax; lpData
0x180003406  call    cs:__imp_RegQueryValueExW
0x18000340c  test    eax, eax
0x18000340e  jnz     short loc_18000341A
0x180003410  cmp     dword ptr [rsp+68h+cbData], 4
0x180003415  cmovz   ebx, [rsp+68h+Data]
0x18000341a  mov     r10, cs:WPP_GLOBAL_Control
0x180003421  mov     rcx, [rsp+68h+hKey]; hKey
0x180003429  test    rcx, rcx
0x18000342c  jz      short loc_18000343B
0x18000342e  call    cs:__imp_RegCloseKey
0x180003434  mov     r10, cs:WPP_GLOBAL_Control
0x18000343b  cmp     r10, r14
0x18000343e  jz      short loc_18000346A
0x180003440  cmp     byte ptr [r10+19h], 6
0x180003445  jb      short loc_18000346A
0x180003447  or      ecx, 0FFFFFFFFh; int
0x18000344a  call    ?GetIndent@@YAPEBDH@Z; GetIndent(int)
0x18000344f  mov     rcx, [r10+10h]
0x180003453  mov     edx, 43h ; 'C'
0x180003458  mov     r9, rax
0x18000345b  mov     r8, r15
0x18000345e  call    WPP_SF_s
0x180003463  mov     r10, cs:WPP_GLOBAL_Control
0x18000346a  test    ebx, ebx
0x18000346c  jz      short loc_1800034BE
0x18000346e  cmp     ebx, 10h
0x180003471  jz      short loc_1800034B4
0x180003473  cmp     ebx, 20h ; ' '
0x180003476  jz      short loc_1800034A8
0x180003478  cmp     r10, r14
0x18000347b  jz      short loc_1800034E5
0x18000347d  cmp     byte ptr [r10+19h], 3
0x180003482  jb      short loc_1800034BE
0x180003484  xor     ecx, ecx; int
0x180003486  call    ?GetIndent@@YAPEBDH@Z; GetIndent(int)
0x18000348b  mov     rcx, [r10+10h]
0x18000348f  mov     edx, 0Eh
0x180003494  mov     r9, rax
0x180003497  mov     r8, r15
0x18000349a  call    WPP_SF_s
0x18000349f  mov     r10, cs:WPP_GLOBAL_Control
0x1800034a6  jmp     short loc_1800034BE
0x1800034a8  mov     cs:?m_VersionOverride@CWcnService@@0W4tagWCN_PROTOCOL_VERSION@@A, 20h ; ' '; tagWCN_PROTOCOL_VERSION CWcnService::m_VersionOverride
0x1800034b2  jmp     short loc_1800034BE
0x1800034b4  mov     cs:?m_VersionOverride@CWcnService@@0W4tagWCN_PROTOCOL_VERSION@@A, 10h; tagWCN_PROTOCOL_VERSION CWcnService::m_VersionOverride
0x1800034be  cmp     r10, r14
0x1800034c1  jz      short loc_1800034E5
0x1800034c3  cmp     byte ptr [r10+19h], 6
0x1800034c8  jb      short loc_1800034E5
0x1800034ca  mov     ecx, esi; int
0x1800034cc  call    ?GetIndent@@YAPEBDH@Z; GetIndent(int)
0x1800034d1  mov     rcx, [r10+10h]
0x1800034d5  mov     edx, 19h
0x1800034da  mov     r9, rax
0x1800034dd  mov     r8, r15
0x1800034e0  call    WPP_SF_s
0x1800034e5  mov     r8, rdi; lpContext
0x1800034e8  lea     rdx, WcnServiceControlMessageHandlerThunk; lpHandlerProc
0x1800034ef  lea     rcx, ServiceName; "wcncsvc"
0x1800034f6  call    cs:__imp_RegisterServiceCtrlHandlerExW
0x1800034fc  mov     [rdi], rax
0x1800034ff  test    rax, rax
0x180003502  jnz     short loc_180003568
0x180003504  call    cs:__imp_GetLastError
0x18000350a  mov     r11d, eax
0x18000350d  test    eax, eax
0x18000350f  jnz     short loc_180003515
0x180003511  xor     ebx, ebx
0x180003513  jmp     short loc_18000352F
0x180003515  test    r11d, r11d
0x180003518  jg      short loc_18000351F
0x18000351a  mov     ebx, r11d
0x18000351d  jmp     short loc_180003529
0x18000351f  movzx   ebx, r11w
0x180003523  or      ebx, 80070000h
0x180003529  or      ebx, 80000000h
0x18000352f  mov     r10, cs:WPP_GLOBAL_Control
0x180003536  cmp     r10, r14
0x180003539  jz      loc_1800035C2
0x18000353f  cmp     byte ptr [r10+19h], 2
0x180003544  jb      short loc_180003593
0x180003546  xor     ecx, ecx; int
0x180003548  call    ?GetIndent@@YAPEBDH@Z; GetIndent(int)
0x18000354d  mov     rcx, [r10+10h]
0x180003551  mov     edx, 1Ah
0x180003556  mov     r9, rax
0x180003559  mov     dword ptr [rsp+68h+phkResult], r11d
0x18000355e  mov     r8, r15
0x180003561  call    WPP_SF_sd
0x180003566  jmp     short loc_18000358C
0x180003568  xor     ebx, ebx
0x18000356a  mov     [rdi+1Ch], rsi
0x18000356e  mov     rcx, rdi; this
0x180003571  mov     [rdi+14h], rbx
0x180003575  mov     dword ptr [rdi+8], 20h ; ' '
0x18000357c  mov     qword ptr [rdi+0Ch], 2
0x180003584  lea     edx, [rbx+2]; unsigned int
0x180003587  call    ?NotifyStatus@CWcnService@@AEAAXK@Z; CWcnService::NotifyStatus(ulong)
0x18000358c  mov     r10, cs:WPP_GLOBAL_Control
0x180003593  cmp     r10, r14
0x180003596  jz      short loc_1800035C2
0x180003598  cmp     byte ptr [r10+19h], 6
0x18000359d  jb      short loc_1800035C2
0x18000359f  or      ecx, 0FFFFFFFFh; int
0x1800035a2  call    ?GetIndent@@YAPEBDH@Z; GetIndent(int)
0x1800035a7  mov     rcx, [r10+10h]
0x1800035ab  mov     edx, 1Bh
0x1800035b0  mov     r9, rax
0x1800035b3  mov     r8, r15
0x1800035b6  call    WPP_SF_s
0x1800035bb  mov     r10, cs:WPP_GLOBAL_Control
0x1800035c2  test    ebx, ebx
0x1800035c4  jns     short loc_1800035E4
0x1800035c6  cmp     r10, r14
0x1800035c9  jz      loc_1800037A8
0x1800035cf  cmp     byte ptr [r10+19h], 2
0x1800035d4  jb      loc_1800037A8
0x1800035da  mov     edx, 0Fh
0x1800035df  jmp     loc_180003799
0x1800035e4  mov     rcx, rdi; this
0x1800035e7  call    ?StartSubsystems@CWcnService@@AEAAJXZ; CWcnService::StartSubsystems(void)
0x1800035ec  mov     ebx, eax
0x1800035ee  test    eax, eax
0x1800035f0  jns     short loc_18000361D
0x1800035f2  mov     rcx, cs:WPP_GLOBAL_Control
0x1800035f9  cmp     rcx, r14
0x1800035fc  jz      loc_1800037A8
0x180003602  cmp     byte ptr [rcx+19h], 2
0x180003606  jb      loc_1800037A8
0x18000360c  mov     rcx, [rcx+10h]
0x180003610  mov     edx, 10h
0x180003615  mov     r9d, eax
0x180003618  jmp     loc_1800037A0
0x18000361d  mov     r10, cs:WPP_GLOBAL_Control
0x180003624  cmp     r10, r14
0x180003627  jz      short loc_18000364B
0x180003629  cmp     byte ptr [r10+19h], 6
0x18000362e  jb      short loc_18000364B
0x180003630  mov     ecx, esi; int
0x180003632  call    ?GetIndent@@YAPEBDH@Z; GetIndent(int)
0x180003637  mov     rcx, [r10+10h]
0x18000363b  mov     edx, 1Ch
0x180003640  mov     r9, rax
0x180003643  mov     r8, r15
0x180003646  call    WPP_SF_s
0x18000364b  xor     r9d, r9d; lpName
0x18000364e  xor     r8d, r8d; bInitialState
0x180003651  xor     edx, edx; bManualReset
0x180003653  xor     ecx, ecx; lpEventAttributes
0x180003655  call    cs:__imp_CreateEventW
0x18000365b  mov     [rdi+28h], rax
0x18000365f  mov     r8, rax
0x180003662  test    rax, rax
0x180003665  jnz     short loc_1800036CC
0x180003667  call    cs:__imp_GetLastError
0x18000366d  test    eax, eax
0x18000366f  jg      short loc_18000367B
0x180003671  call    cs:__imp_GetLastError
0x180003677  mov     ebx, eax
0x180003679  jmp     short loc_18000368A
0x18000367b  call    cs:__imp_GetLastError
0x180003681  movzx   ebx, ax
0x180003684  or      ebx, 80070000h
0x18000368a  or      ebx, 80000000h
0x180003690  mov     r10, cs:WPP_GLOBAL_Control
0x180003697  cmp     r10, r14
0x18000369a  jz      loc_180003784
0x1800036a0  cmp     byte ptr [r10+19h], 2
0x1800036a5  jb      loc_18000374D
0x1800036ab  xor     ecx, ecx; int
0x1800036ad  call    ?GetIndent@@YAPEBDH@Z; GetIndent(int)
0x1800036b2  mov     rcx, [r10+10h]
0x1800036b6  mov     edx, 1Dh
0x1800036bb  mov     r9, rax
0x1800036be  mov     dword ptr [rsp+68h+phkResult], ebx
0x1800036c2  mov     r8, r15
0x1800036c5  call    WPP_SF_sd
0x1800036ca  jmp     short loc_180003746
0x1800036cc  mov     rax, cs:?g_pSvchostGlobalData@@3PEAU_SVCHOST_GLOBAL_DATA@@EA; _SVCHOST_GLOBAL_DATA * g_pSvchostGlobalData
0x1800036d3  lea     rcx, [rdi+30h]
0x1800036d7  mov     dword ptr [rsp+68h+lpcbData], 18h
0x1800036df  lea     r9, WcnServiceStopEventThunk
0x1800036e6  lea     rdx, ServiceName; "wcncsvc"
0x1800036ed  mov     [rsp+68h+phkResult], rdi
0x1800036f2  mov     rax, [rax+0C0h]
0x1800036f9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800036fe  test    eax, eax
0x180003700  jz      short loc_180003744
0x180003702  jg      short loc_180003708
0x180003704  mov     ebx, eax
0x180003706  jmp     short loc_180003711
0x180003708  movzx   ebx, ax
0x18000370b  or      ebx, 80070000h
0x180003711  or      ebx, 80000000h
0x180003717  mov     r10, cs:WPP_GLOBAL_Control
0x18000371e  cmp     r10, r14
0x180003721  jz      short loc_180003784
0x180003723  cmp     byte ptr [r10+19h], 2
0x180003728  jb      short loc_18000374D
0x18000372a  mov     rcx, [r10+10h]
0x18000372e  mov     edx, 1Eh
0x180003733  mov     r9d, eax
0x180003736  mov     dword ptr [rsp+68h+phkResult], ebx
0x18000373a  mov     r8, r15
0x18000373d  call    WPP_SF_Dd
0x180003742  jmp     short loc_180003746
0x180003744  xor     ebx, ebx
0x180003746  mov     r10, cs:WPP_GLOBAL_Control
0x18000374d  cmp     r10, r14
  ... truncated ...
```
