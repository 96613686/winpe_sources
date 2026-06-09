# CWNPNet::Init(bool,IWNPNetEvents *,LogCommandManager *)

- ea: `0x1800390a4`
- end: `0x18003982d`
- name: `?Init@CWNPNet@@QEAAJ_NPEAVIWNPNetEvents@@PEAVLogCommandManager@@@Z`
- size: `1929`
- prototype: `__int64 __fastcall(CWNPNet *this, char, struct IWNPNetEvents *, struct LogCommandManager *)`
- caller_count: `1`
- callee_count: `19`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x180025364`

## callees

- `0x180007924`
- `0x18000795c`
- `0x18000c97c`
- `0x18000fddc`
- `0x18000fe2c`
- `0x18000fe54`
- `0x18001344c`
- `0x18001c06c`
- `0x180021524`
- `0x18002fcdc`
- `0x180033660`
- `0x180038cf8`
- `0x1800390a4`
- `0x180039834`
- `0x180039c24`
- `0x18003ab40`
- `0x180044348`
- `0x180060b10`
- `0x180096010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180039367`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18003952f`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180039367`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18003952f`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180039507`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180039507`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180039353`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800394f9`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18003951e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180039353`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800394f9`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18003951e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003966d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003966d`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExA` at `0x1800394ca`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExA` at `0x1800395e7`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExA` at `0x1800394ca`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExA` at `0x1800395e7`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExA` at `0x180039492`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExA` at `0x180039492`

## string_xrefs

- `0x1800393ed`: `client.wns.windows.com`

## pseudocode

```c
__int64 __fastcall CWNPNet::Init(CWNPNet *this, char a2, struct IWNPNetEvents *a3, struct LogCommandManager *a4)
{
  PVOID v8; // rcx
  unsigned int v9; // ebx
  PVOID *v10; // rcx
  __int64 v11; // rdx
  __int64 v12; // r9
  int v13; // eax
  int v14; // eax
  HANDLE ProcessHeap; // rax
  LPVOID v16; // rax
  char *v17; // rcx
  int v18; // eax
  DWORD v19; // eax
  void *v20; // rbx
  HANDLE v21; // rax
  DWORD v22; // ebx
  HANDLE v23; // rax
  LPVOID v24; // rax
  _BYTE *v25; // rax
  _QWORD *v26; // rcx
  __int64 v27; // rdx
  int inited; // eax
  __int64 v29; // rcx
  TraceLoggingCorrelationVector *v30; // rax
  void *v31; // rcx
  int phkResult; // [rsp+20h] [rbp-20h]
  DWORD lpcbData; // [rsp+30h] [rbp-10h] BYREF
  HKEY hKey; // [rsp+38h] [rbp-8h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+28h]
  DWORD cbData; // [rsp+70h] [rbp+30h] BYREF
  DWORD Type; // [rsp+80h] [rbp+40h] BYREF

  v8 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_dc(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      49,
      &WPP_4e47059d20e03c0ffeb37878b8bdc70f_Traceguids,
      *((unsigned int *)this + 52),
      a2);
    v8 = WPP_GLOBAL_Control;
  }
  if ( !a3 )
  {
    MicrosoftTelemetryAssertTriggeredNoArgs(v8);
    v8 = WPP_GLOBAL_Control;
  }
  if ( !*((_DWORD *)this + 52) || (MicrosoftTelemetryAssertTriggeredNoArgs(v8), !*((_DWORD *)this + 52)) )
  {
    *((_BYTE *)this + 1597) = a2;
    Microsoft::WRL::ComPtr<LogCommandManager>::operator=((char *)this + 1704, a4);
    v13 = CAbstractConnection::Init(this, *((_BYTE *)this + 1597), a4);
    v9 = v13;
    if ( v13 < 0 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          52,
          &WPP_4e47059d20e03c0ffeb37878b8bdc70f_Traceguids,
          (unsigned int)v13);
      }
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x290,
        (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\prov\\trans\\wnpnet.cpp",
        (const char *)v9,
        phkResult);
      v10 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
        return v9;
      if ( *((char *)WPP_GLOBAL_Control + 28) >= 0 )
        goto LABEL_114;
      v11 = 53;
      goto LABEL_24;
    }
    if ( !CMsgrWndBase::IsMsgrWindow(this) )
    {
      v14 = (*(__int64 (__fastcall **)(CWNPNet *, const unsigned __int16 *, __int64))(*(_QWORD *)this + 8LL))(
              this,
              L"WnpNet",
              -3);
      v9 = v14;
      if ( v14 < 0 )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            54,
            &WPP_4e47059d20e03c0ffeb37878b8bdc70f_Traceguids,
            (unsigned int)v14);
        }
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x296,
          (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\prov\\trans\\wnpnet.cpp",
          (const char *)v9,
          phkResult);
        v10 = (PVOID *)WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
          return v9;
        if ( *((char *)WPP_GLOBAL_Control + 28) >= 0 )
          goto LABEL_114;
        v11 = 55;
        goto LABEL_24;
      }
    }
    *((_DWORD *)this + 52) = 1;
    CWNPNet::LogWnpState(this);
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
    {
      WPP_SF_dLc(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        56,
        &WPP_4e47059d20e03c0ffeb37878b8bdc70f_Traceguids,
        0,
        *((_DWORD *)this + 52),
        *((_BYTE *)this + 1597));
    }
    *((_QWORD *)this + 25) = a3;
    if ( CWNPNet::SetWnsEndPointFromGroupPolicy(this) )
      goto LABEL_89;
    ProcessHeap = GetProcessHeap();
    v16 = HeapAlloc(ProcessHeap, 8u, 0x17u);
    *((_QWORD *)this + 39) = v16;
    if ( !v16
      && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 57, &WPP_4e47059d20e03c0ffeb37878b8bdc70f_Traceguids, 2147942414LL);
    }
    v17 = (char *)*((_QWORD *)this + 39);
    if ( !v17 )
    {
      v9 = -2147024882;
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x2A6,
        (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\prov\\trans\\wnpnet.cpp",
        (const char *)0x8007000ELL,
        phkResult);
      v10 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
        return v9;
      if ( *((char *)WPP_GLOBAL_Control + 28) >= 0 )
        goto LABEL_114;
      v11 = 58;
      goto LABEL_111;
    }
    v18 = StringCchCopyA(v17, 0x17u, "client.wns.windows.com");
    v9 = v18;
    if ( v18 < 0 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          59,
          &WPP_4e47059d20e03c0ffeb37878b8bdc70f_Traceguids,
          (unsigned int)v18);
      }
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x2AA,
        (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\prov\\trans\\wnpnet.cpp",
        (const char *)v9,
        phkResult);
      v10 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
        return v9;
      if ( *((char *)WPP_GLOBAL_Control + 28) >= 0 )
        goto LABEL_114;
      v11 = 60;
      goto LABEL_24;
    }
    hKey = 0;
    if ( RegOpenKeyExA(
           HKEY_LOCAL_MACHINE,
           "Software\\Microsoft\\Windows\\CurrentVersion\\PushNotifications",
           0,
           1u,
           &hKey) )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
      {
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 65, &WPP_4e47059d20e03c0ffeb37878b8bdc70f_Traceguids);
      }
      goto LABEL_89;
    }
    cbData = 0;
    Type = 0;
    if ( !RegQueryValueExA(hKey, "Server", 0, &Type, 0, &cbData) && Type == 1 && (v19 = cbData) != 0 )
    {
      v20 = (void *)*((_QWORD *)this + 39);
      if ( v20 )
      {
        v21 = GetProcessHeap();
        HeapFree(v21, 0, v20);
        *((_QWORD *)this + 39) = 0;
        v19 = cbData;
      }
      v22 = v19 + 1;
      v23 = GetProcessHeap();
      v24 = HeapAlloc(v23, 8u, v22);
      *((_QWORD *)this + 39) = v24;
      if ( !v24
        && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          61,
          &WPP_4e47059d20e03c0ffeb37878b8bdc70f_Traceguids,
          2147942414LL);
      }
      v25 = (_BYTE *)*((_QWORD *)this + 39);
      if ( !v25 )
      {
        v9 = -2147024882;
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x2BF,
          (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\prov\\trans\\wnpnet.cpp",
          (const char *)0x8007000ELL,
          phkResult);
        v10 = (PVOID *)WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
          return v9;
        if ( *((char *)WPP_GLOBAL_Control + 28) >= 0 )
          goto LABEL_114;
        v11 = 62;
        goto LABEL_111;
      }
      *v25 = 0;
      lpcbData = cbData + 1;
      if ( !RegQueryValueExA(hKey, "Server", 0, &Type, *((LPBYTE *)this + 39), &lpcbData)
        && Type == 1
        && cbData == lpcbData )
      {
        *(_BYTE *)(cbData + *((_QWORD *)this + 39)) = 0;
        GetPortFromServerString(*((char **)this + 39), (unsigned __int16 *)this + 164);
LABEL_84:
        RegCloseKey(hKey);
LABEL_89:
        inited = CWNPNet::InitServerName(this);
        v9 = inited;
        if ( inited >= 0 )
        {
          if ( !*((_WORD *)this + 164) )
            MicrosoftTelemetryAssertTriggeredNoArgs(v29);
          *((_WORD *)this + 165) = *((_WORD *)this + 164);
          v30 = (TraceLoggingCorrelationVector *)operator new(0x90u, (const struct std::nothrow_t *)&std::nothrow);
          if ( v30 )
            v30 = TraceLoggingCorrelationVector::TraceLoggingCorrelationVector(v30);
          v31 = (void *)*((_QWORD *)this + 34);
          *((_QWORD *)this + 34) = v30;
          if ( v31 )
            operator delete(v31, (const struct std::nothrow_t *)0x90);
          if ( *((_QWORD *)this + 34) )
            goto LABEL_113;
          v9 = -2147024882;
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            WPP_SF_d(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              68,
              &WPP_4e47059d20e03c0ffeb37878b8bdc70f_Traceguids,
              2147942414LL);
          }
          wil::details::in1diag3::_Log_Hr(
            retaddr,
            (void *)0x2ED,
            (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\prov\\trans\\wnpnet.cpp",
            (const char *)0x8007000ELL,
            phkResult);
          v10 = (PVOID *)WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
            return v9;
          if ( *((char *)WPP_GLOBAL_Control + 28) >= 0 )
            goto LABEL_114;
          v11 = 69;
LABEL_111:
          v12 = 2147942414LL;
          goto LABEL_112;
        }
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            66,
            &WPP_4e47059d20e03c0ffeb37878b8bdc70f_Traceguids,
            (unsigned int)inited);
        }
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x2E3,
          (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\prov\\trans\\wnpnet.cpp",
          (const char *)v9,
          phkResult);
        v10 = (PVOID *)WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
          return v9;
        if ( *((char *)WPP_GLOBAL_Control + 28) >= 0 )
          goto LABEL_114;
        v11 = 67;
LABEL_24:
        v12 = v9;
        goto LABEL_112;
      }
      v26 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 3u )
      {
        goto LABEL_84;
      }
      v27 = 63;
    }
    else
    {
      v26 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 3u )
      {
        goto LABEL_84;
      }
      v27 = 64;
    }
    WPP_SF_(v26[2], v27, &WPP_4e47059d20e03c0ffeb37878b8bdc70f_Traceguids);
    goto LABEL_84;
  }
  v9 = -2147418113;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 50, &WPP_4e47059d20e03c0ffeb37878b8bdc70f_Traceguids, 2147549183LL);
  }
  wil::details::in1diag3::_Log_Hr(
    retaddr,
    (void *)0x288,
    (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\prov\\trans\\wnpnet.cpp",
    (const char *)0x8000FFFFLL,
    phkResult);
  v10 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
  {
    if ( *((char *)WPP_GLOBAL_Control + 28) < 0 )
    {
      v11 = 51;
      v12 = 2147549183LL;
LABEL_112:
      WPP_SF_d(v10[2], v11, &WPP_4e47059d20e03c0ffeb37878b8bdc70f_Traceguids, v12);
LABEL_113:
      v10 = (PVOID *)WPP_GLOBAL_Control;
    }
LABEL_114:
    if ( v10 != &WPP_GLOBAL_Control && (*((_BYTE *)v10 + 28) & 4) != 0 && *((_BYTE *)v10 + 25) >= 6u )
      WPP_SF_d(v10[2], 70, &WPP_4e47059d20e03c0ffeb37878b8bdc70f_Traceguids, v9);
  }
  return v9;
}

```

## disassembly

```asm
0x1800390a4  mov     [rsp-28h+arg_8], rbx
0x1800390a9  mov     [rsp-28h+arg_18], rsi
0x1800390ae  push    rbp
0x1800390af  push    rdi
0x1800390b0  push    r12
0x1800390b2  push    r13
0x1800390b4  push    r14
0x1800390b6  mov     rbp, rsp
0x1800390b9  sub     rsp, 40h
0x1800390bd  mov     r14, r9
0x1800390c0  mov     rsi, r8
0x1800390c3  mov     bl, dl
0x1800390c5  mov     rdi, rcx
0x1800390c8  lea     r12, WPP_GLOBAL_Control
0x1800390cf  lea     r13, WPP_4e47059d20e03c0ffeb37878b8bdc70f_Traceguids
0x1800390d6  mov     rcx, cs:WPP_GLOBAL_Control
0x1800390dd  cmp     rcx, r12
0x1800390e0  jz      short loc_180039111
0x1800390e2  test    byte ptr [rcx+1Ch], 4
0x1800390e6  jz      short loc_180039111
0x1800390e8  cmp     byte ptr [rcx+19h], 6
0x1800390ec  jb      short loc_180039111
0x1800390ee  mov     edx, 31h ; '1'
0x1800390f3  mov     byte ptr [rsp+40h+phkResult], bl; int
0x1800390f7  mov     r9d, [rdi+0D0h]
0x1800390fe  mov     r8, r13
0x180039101  mov     rcx, [rcx+10h]
0x180039105  call    WPP_SF_dc
0x18003910a  mov     rcx, cs:WPP_GLOBAL_Control
0x180039111  test    rsi, rsi
0x180039114  jnz     short loc_180039122
0x180039116  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18003911b  mov     rcx, cs:WPP_GLOBAL_Control
0x180039122  cmp     dword ptr [rdi+0D0h], 0
0x180039129  jz      loc_1800391B0
0x18003912f  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180039134  mov     rcx, cs:WPP_GLOBAL_Control
0x18003913b  cmp     dword ptr [rdi+0D0h], 0
0x180039142  jz      short loc_1800391B0
0x180039144  mov     ebx, 8000FFFFh
0x180039149  cmp     rcx, r12
0x18003914c  jz      short loc_18003916E
0x18003914e  test    byte ptr [rcx+1Ch], 4
0x180039152  jz      short loc_18003916E
0x180039154  cmp     byte ptr [rcx+19h], 2
0x180039158  jb      short loc_18003916E
0x18003915a  mov     edx, 32h ; '2'
0x18003915f  mov     r9d, ebx
0x180039162  mov     r8, r13
0x180039165  mov     rcx, [rcx+10h]
0x180039169  call    WPP_SF_d
0x18003916e  mov     rcx, [rbp+28h]; this
0x180039172  mov     r9d, ebx; char *
0x180039175  lea     r8, aOnecoreuapBase_10; "onecoreuap\\base\\diagnosis\\platform\\"...
0x18003917c  mov     edx, 288h; void *
0x180039181  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180039186  mov     rcx, cs:WPP_GLOBAL_Control
0x18003918d  cmp     rcx, r12
0x180039190  jz      loc_180039812
0x180039196  test    byte ptr [rcx+1Ch], 80h
0x18003919a  jz      loc_1800397ED
0x1800391a0  mov     edx, 33h ; '3'
0x1800391a5  mov     r9d, 8000FFFFh
0x1800391ab  jmp     loc_1800397DA
0x1800391b0  mov     [rdi+63Dh], bl
0x1800391b6  lea     rcx, [rdi+6A8h]
0x1800391bd  mov     rdx, r14
0x1800391c0  call    ??4?$ComPtr@VLogCommandManager@@@WRL@Microsoft@@QEAAAEAV012@PEAVLogCommandManager@@@Z; Microsoft::WRL::ComPtr<LogCommandManager>::operator=(LogCommandManager *)
0x1800391c5  mov     r8, r14; struct LogCommandManager *
0x1800391c8  mov     dl, [rdi+63Dh]; bool
0x1800391ce  mov     rcx, rdi; this
0x1800391d1  call    ?Init@CAbstractConnection@@UEAAJ_NPEAVLogCommandManager@@@Z; CAbstractConnection::Init(bool,LogCommandManager *)
0x1800391d6  mov     ebx, eax
0x1800391d8  test    eax, eax
0x1800391da  jns     short loc_180039247
0x1800391dc  mov     rcx, cs:WPP_GLOBAL_Control
0x1800391e3  cmp     rcx, r12
0x1800391e6  jz      short loc_180039208
0x1800391e8  test    byte ptr [rcx+1Ch], 4
0x1800391ec  jz      short loc_180039208
0x1800391ee  cmp     byte ptr [rcx+19h], 2
0x1800391f2  jb      short loc_180039208
0x1800391f4  mov     edx, 34h ; '4'
0x1800391f9  mov     r9d, eax
0x1800391fc  mov     r8, r13
0x1800391ff  mov     rcx, [rcx+10h]
0x180039203  call    WPP_SF_d
0x180039208  mov     rcx, [rbp+28h]; this
0x18003920c  mov     r9d, ebx; char *
0x18003920f  lea     r8, aOnecoreuapBase_10; "onecoreuap\\base\\diagnosis\\platform\\"...
0x180039216  mov     edx, 290h; void *
0x18003921b  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180039220  mov     rcx, cs:WPP_GLOBAL_Control
0x180039227  cmp     rcx, r12
0x18003922a  jz      loc_180039812
0x180039230  test    byte ptr [rcx+1Ch], 80h
0x180039234  jz      loc_1800397ED
0x18003923a  mov     edx, 35h ; '5'
0x18003923f  mov     r9d, ebx
0x180039242  jmp     loc_1800397DA
0x180039247  mov     rcx, rdi; this
0x18003924a  call    ?IsMsgrWindow@CMsgrWndBase@@IEAA_NXZ; CMsgrWndBase::IsMsgrWindow(void)
0x18003924f  test    al, al
0x180039251  jnz     loc_1800392E2
0x180039257  mov     rax, [rdi]
0x18003925a  mov     r8, 0FFFFFFFFFFFFFFFDh
0x180039261  lea     rdx, ?g_WnpNetWindowName@@3QBGB; "WnpNet"
0x180039268  mov     rcx, rdi
0x18003926b  mov     rax, [rax+8]
0x18003926f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180039274  mov     ebx, eax
0x180039276  test    eax, eax
0x180039278  jns     short loc_1800392E2
0x18003927a  mov     rcx, cs:WPP_GLOBAL_Control
0x180039281  cmp     rcx, r12
0x180039284  jz      short loc_1800392A6
0x180039286  test    byte ptr [rcx+1Ch], 4
0x18003928a  jz      short loc_1800392A6
0x18003928c  cmp     byte ptr [rcx+19h], 2
0x180039290  jb      short loc_1800392A6
0x180039292  mov     edx, 36h ; '6'
0x180039297  mov     r9d, eax
0x18003929a  mov     r8, r13
0x18003929d  mov     rcx, [rcx+10h]
0x1800392a1  call    WPP_SF_d
0x1800392a6  mov     rcx, [rbp+28h]; this
0x1800392aa  mov     r9d, ebx; char *
0x1800392ad  lea     r8, aOnecoreuapBase_10; "onecoreuap\\base\\diagnosis\\platform\\"...
0x1800392b4  mov     edx, 296h; void *
0x1800392b9  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800392be  mov     rcx, cs:WPP_GLOBAL_Control
0x1800392c5  cmp     rcx, r12
0x1800392c8  jz      loc_180039812
0x1800392ce  test    byte ptr [rcx+1Ch], 80h
0x1800392d2  jz      loc_1800397ED
0x1800392d8  mov     edx, 37h ; '7'
0x1800392dd  jmp     loc_18003923F
0x1800392e2  mov     dword ptr [rdi+0D0h], 1
0x1800392ec  mov     rcx, rdi; this
0x1800392ef  call    ?LogWnpState@CWNPNet@@AEAAXXZ; CWNPNet::LogWnpState(void)
0x1800392f4  mov     rcx, cs:WPP_GLOBAL_Control
0x1800392fb  mov     r14b, 4
0x1800392fe  cmp     rcx, r12
0x180039301  jz      short loc_180039337
0x180039303  test    [rcx+1Ch], r14b
0x180039307  jz      short loc_180039337
0x180039309  cmp     byte ptr [rcx+19h], 5
0x18003930d  jb      short loc_180039337
0x18003930f  mov     edx, 38h ; '8'
0x180039314  mov     al, [rdi+63Dh]
0x18003931a  mov     byte ptr [rsp+40h+lpcbData], al
0x18003931e  mov     eax, [rdi+0D0h]
0x180039324  mov     dword ptr [rsp+40h+phkResult], eax; int
0x180039328  xor     r9d, r9d
0x18003932b  mov     r8, r13
0x18003932e  mov     rcx, [rcx+10h]
0x180039332  call    WPP_SF_dLc
0x180039337  mov     [rdi+0C8h], rsi
0x18003933e  mov     rcx, rdi; this
0x180039341  call    ?SetWnsEndPointFromGroupPolicy@CWNPNet@@AEAA_NXZ; CWNPNet::SetWnsEndPointFromGroupPolicy(void)
0x180039346  mov     esi, 8007000Eh
0x18003934b  test    al, al
0x18003934d  jnz     loc_18003969E
0x180039353  call    cs:__imp_GetProcessHeap
0x180039359  mov     rcx, rax; hHeap
0x18003935c  mov     ebx, 17h
0x180039361  mov     r8d, ebx; dwBytes
0x180039364  lea     edx, [rbx-0Fh]; dwFlags
0x180039367  call    cs:__imp_HeapAlloc
0x18003936d  mov     [rdi+138h], rax
0x180039374  test    rax, rax
0x180039377  jnz     short loc_1800393A3
0x180039379  mov     rcx, cs:WPP_GLOBAL_Control
0x180039380  cmp     rcx, r12
0x180039383  jz      short loc_1800393A3
0x180039385  test    [rcx+1Ch], r14b
0x180039389  jz      short loc_1800393A3
0x18003938b  cmp     byte ptr [rcx+19h], 2
0x18003938f  jb      short loc_1800393A3
0x180039391  lea     edx, [rbx+22h]
0x180039394  mov     r9d, esi
0x180039397  mov     r8, r13
0x18003939a  mov     rcx, [rcx+10h]
0x18003939e  call    WPP_SF_d
0x1800393a3  mov     rcx, [rdi+138h]; char *
0x1800393aa  test    rcx, rcx
0x1800393ad  jnz     short loc_1800393ED
0x1800393af  mov     ebx, esi
0x1800393b1  mov     rcx, [rbp+28h]; this
0x1800393b5  mov     r9d, esi; char *
0x1800393b8  lea     r8, aOnecoreuapBase_10; "onecoreuap\\base\\diagnosis\\platform\\"...
0x1800393bf  mov     edx, 2A6h; void *
0x1800393c4  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800393c9  mov     rcx, cs:WPP_GLOBAL_Control
0x1800393d0  cmp     rcx, r12
0x1800393d3  jz      loc_180039812
0x1800393d9  test    byte ptr [rcx+1Ch], 80h
0x1800393dd  jz      loc_1800397ED
0x1800393e3  mov     edx, 3Ah ; ':'
0x1800393e8  jmp     loc_1800397D4
0x1800393ed  lea     r8, aClientWnsWindo; "client.wns.windows.com"
0x1800393f4  mov     rdx, rbx; unsigned __int64
0x1800393f7  call    ?StringCchCopyA@@YAJPEAD_KPEBD@Z; StringCchCopyA(char *,unsigned __int64,char const *)
0x1800393fc  mov     ebx, eax
0x1800393fe  test    eax, eax
0x180039400  jns     short loc_18003946A
0x180039402  mov     rcx, cs:WPP_GLOBAL_Control
0x180039409  cmp     rcx, r12
0x18003940c  jz      short loc_18003942E
0x18003940e  test    [rcx+1Ch], r14b
0x180039412  jz      short loc_18003942E
0x180039414  cmp     byte ptr [rcx+19h], 2
0x180039418  jb      short loc_18003942E
0x18003941a  mov     edx, 3Bh ; ';'
0x18003941f  mov     r9d, eax
0x180039422  mov     r8, r13
0x180039425  mov     rcx, [rcx+10h]
0x180039429  call    WPP_SF_d
0x18003942e  mov     rcx, [rbp+28h]; this
0x180039432  mov     r9d, ebx; char *
0x180039435  lea     r8, aOnecoreuapBase_10; "onecoreuap\\base\\diagnosis\\platform\\"...
0x18003943c  mov     edx, 2AAh; void *
0x180039441  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180039446  mov     rcx, cs:WPP_GLOBAL_Control
0x18003944d  cmp     rcx, r12
0x180039450  jz      loc_180039812
0x180039456  test    byte ptr [rcx+1Ch], 80h
0x18003945a  jz      loc_1800397ED
0x180039460  mov     edx, 3Ch ; '<'
0x180039465  jmp     loc_18003923F
0x18003946a  mov     [rbp+hKey], 0
0x180039472  lea     rax, [rbp+hKey]
0x180039476  mov     [rsp+40h+phkResult], rax; int
0x18003947b  mov     r9d, 1; samDesired
0x180039481  xor     r8d, r8d; ulOptions
0x180039484  lea     rdx, aSoftwareMicros_1; "Software\\Microsoft\\Windows\\CurrentVe"...
0x18003948b  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180039492  call    cs:__imp_RegOpenKeyExA
0x180039498  test    eax, eax
0x18003949a  jnz     loc_180039675
0x1800394a0  mov     [rbp+cbData], eax
0x1800394a3  mov     [rbp+Type], eax
0x1800394a6  lea     rax, [rbp+cbData]
0x1800394aa  mov     [rsp+40h+lpcbData], rax; lpcbData
0x1800394af  mov     [rsp+40h+phkResult], 0; int
0x1800394b8  lea     r9, [rbp+Type]; lpType
0x1800394bc  xor     r8d, r8d; lpReserved
0x1800394bf  lea     rdx, ValueName; "Server"
0x1800394c6  mov     rcx, [rbp+hKey]; hKey
0x1800394ca  call    cs:__imp_RegQueryValueExA
0x1800394d0  test    eax, eax
0x1800394d2  jnz     loc_180039640
0x1800394d8  cmp     [rbp+Type], 1
0x1800394dc  jnz     loc_180039640
0x1800394e2  mov     eax, [rbp+cbData]
0x1800394e5  test    eax, eax
0x1800394e7  jz      loc_180039640
0x1800394ed  mov     rbx, [rdi+138h]
0x1800394f4  test    rbx, rbx
0x1800394f7  jz      short loc_18003951B
0x1800394f9  call    cs:__imp_GetProcessHeap
0x1800394ff  mov     r8, rbx; lpMem
0x180039502  xor     edx, edx; dwFlags
0x180039504  mov     rcx, rax; hHeap
0x180039507  call    cs:__imp_HeapFree
0x18003950d  mov     qword ptr [rdi+138h], 0
0x180039518  mov     eax, [rbp+cbData]
0x18003951b  lea     ebx, [rax+1]
0x18003951e  call    cs:__imp_GetProcessHeap
0x180039524  mov     r8d, ebx; dwBytes
0x180039527  mov     edx, 8; dwFlags
0x18003952c  mov     rcx, rax; hHeap
0x18003952f  call    cs:__imp_HeapAlloc
0x180039535  mov     [rdi+138h], rax
0x18003953c  test    rax, rax
0x18003953f  jnz     short loc_18003956B
0x180039541  mov     rcx, cs:WPP_GLOBAL_Control
0x180039548  cmp     rcx, r12
0x18003954b  jz      short loc_18003956B
0x18003954d  test    [rcx+1Ch], r14b
0x180039551  jz      short loc_18003956B
0x180039553  cmp     byte ptr [rcx+19h], 2
0x180039557  jb      short loc_18003956B
0x180039559  lea     edx, [rax+3Dh]
0x18003955c  mov     r9d, esi
0x18003955f  mov     r8, r13
0x180039562  mov     rcx, [rcx+10h]
0x180039566  call    WPP_SF_d
0x18003956b  mov     rax, [rdi+138h]
0x180039572  test    rax, rax
0x180039575  jnz     short loc_1800395B5
0x180039577  mov     ebx, esi
0x180039579  mov     rcx, [rbp+28h]; this
0x18003957d  mov     r9d, esi; char *
0x180039580  lea     r8, aOnecoreuapBase_10; "onecoreuap\\base\\diagnosis\\platform\\"...
0x180039587  mov     edx, 2BFh; void *
0x18003958c  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180039591  mov     rcx, cs:WPP_GLOBAL_Control
0x180039598  cmp     rcx, r12
0x18003959b  jz      loc_180039812
  ... truncated ...
```
