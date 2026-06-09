# CIEProxyFromWinHttp::CreateHttpTunnel(char const *,char const *,ushort)

- ea: `0x1800620e4`
- end: `0x180062937`
- name: `?CreateHttpTunnel@CIEProxyFromWinHttp@@QEAAJPEBD0G@Z`
- size: `2131`
- prototype: `__int64 __fastcall(DWORD_PTR dwContext, LPCCH lpMultiByteStr, LPCCH, __int16)`
- caller_count: `1`
- callee_count: `5`
- tags: `service_task`

## callers

- `0x1800527dc`

## callees

- `0x18000fddc`
- `0x18000fe54`
- `0x18001ce24`
- `0x1800620e4`
- `0x1800636b0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18006256c`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800625d9`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18006256c`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800625d9`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180062886`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180062886`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180062876`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180062876`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180062291`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180062351`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006240b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800624d3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180062593`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180062600`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180062660`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006271e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800627b8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180062809`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180062291`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180062351`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006240b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800624d3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180062593`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180062600`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180062660`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006271e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800627b8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180062809`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800628c8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800628ee`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800628c8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800628ee`
- `WINHTTP!WinHttpSendRequest` at `0x180062710`
- `WINHTTP!WinHttpSendRequest` at `0x180062710`
- `WINHTTP!WinHttpOpenRequest` at `0x1800624c0`
- `WINHTTP!WinHttpOpenRequest` at `0x1800624c0`
- `WINHTTP!WinHttpSetOption` at `0x1800623fd`
- `WINHTTP!WinHttpSetOption` at `0x1800623fd`
- `WINHTTP!WinHttpConnect` at `0x18006233e`
- `WINHTTP!WinHttpConnect` at `0x18006233e`
- `WINHTTP!WinHttpOpen` at `0x18006226e`
- `WINHTTP!WinHttpOpen` at `0x18006226e`
- `WINHTTP!WinHttpSetStatusCallback` at `0x180062650`
- `WINHTTP!WinHttpSetStatusCallback` at `0x1800628aa`
- `WINHTTP!WinHttpSetStatusCallback` at `0x180062650`
- `WINHTTP!WinHttpSetStatusCallback` at `0x1800628aa`

## pseudocode

```c
__int64 __fastcall CIEProxyFromWinHttp::CreateHttpTunnel(
        DWORD_PTR dwContext,
        LPCCH lpMultiByteStr,
        LPCCH a3,
        __int16 a4)
{
  int v8; // eax
  signed int LastError; // ebx
  PVOID *v10; // rcx
  __int64 v11; // rdx
  int v12; // eax
  const WCHAR *v13; // rcx
  HINTERNET v14; // rax
  __int64 v15; // r9
  bool v16; // sf
  HINTERNET v17; // rax
  signed int v18; // eax
  __int64 v19; // r9
  bool v20; // sf
  signed int v21; // eax
  __int64 v22; // r9
  bool v23; // sf
  HINTERNET v24; // rax
  signed int v25; // eax
  __int64 v26; // r9
  bool v27; // sf
  HANDLE EventW; // rax
  signed int v29; // eax
  HANDLE v30; // rax
  signed int v31; // eax
  signed int v32; // eax
  __int64 v33; // r9
  bool v34; // sf
  signed int v35; // eax
  __int64 v36; // r9
  bool v37; // sf
  signed int v38; // eax
  signed int v39; // eax
  HANDLE ProcessHeap; // rax
  int dwFlags; // [rsp+20h] [rbp-68h]
  int dwFlagsa; // [rsp+20h] [rbp-68h]
  int dwFlagsb; // [rsp+20h] [rbp-68h]
  int dwFlagsc; // [rsp+20h] [rbp-68h]
  LPCWSTR pszAgentW; // [rsp+40h] [rbp-48h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+0h]

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_ssd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      (_DWORD)lpMultiByteStr,
      (_DWORD)a3,
      (_DWORD)lpMultiByteStr,
      (__int64)a3,
      a4);
  }
  pszAgentW = 0;
  v8 = WpnUtf8ToUtf16(lpMultiByteStr, (unsigned __int16 **)&pszAgentW);
  LastError = v8;
  if ( v8 >= 0 )
  {
    v12 = WpnUtf8ToUtf16(a3, (unsigned __int16 **)(dwContext + 32));
    LastError = v12;
    if ( v12 >= 0 )
    {
      v13 = pszAgentW;
      *(_WORD *)(dwContext + 40) = a4;
      v14 = WinHttpOpen(v13, 4u, 0, 0, 0x10000000u);
      *(_QWORD *)(dwContext + 48) = v14;
      if ( v14 )
        goto LABEL_35;
      LastError = GetLastError();
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        if ( LastError > 0 )
          v15 = (unsigned __int16)LastError | 0x80070000;
        else
          v15 = (unsigned int)LastError;
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 55, &WPP_410e2d598473313f5e012b5f9c63d8ac_Traceguids, v15);
      }
      v16 = LastError < 0;
      if ( LastError > 0 )
      {
        LastError = (unsigned __int16)LastError | 0x80070000;
        v16 = LastError < 0;
      }
      if ( !v16 )
      {
LABEL_35:
        v17 = WinHttpConnect(
                *(HINTERNET *)(dwContext + 48),
                *(LPCWSTR *)(dwContext + 32),
                *(_WORD *)(dwContext + 40),
                0);
        *(_QWORD *)(dwContext + 56) = v17;
        if ( v17 )
          goto LABEL_59;
        v18 = GetLastError();
        LastError = v18;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          if ( v18 > 0 )
            v19 = (unsigned __int16)v18 | 0x80070000;
          else
            v19 = (unsigned int)v18;
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 57, &WPP_410e2d598473313f5e012b5f9c63d8ac_Traceguids, v19);
        }
        v20 = LastError < 0;
        if ( LastError > 0 )
        {
          LastError = (unsigned __int16)LastError | 0x80070000;
          v20 = LastError < 0;
        }
        if ( !v20 )
        {
LABEL_59:
          if ( WinHttpSetOption(*(HINTERNET *)(dwContext + 56), 0x82u, 0, 0) )
            goto LABEL_63;
          v21 = GetLastError();
          LastError = v21;
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            if ( v21 > 0 )
              v22 = (unsigned __int16)v21 | 0x80070000;
            else
              v22 = (unsigned int)v21;
            WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 59, &WPP_410e2d598473313f5e012b5f9c63d8ac_Traceguids, v22);
          }
          v23 = LastError < 0;
          if ( LastError > 0 )
          {
            LastError = (unsigned __int16)LastError | 0x80070000;
            v23 = LastError < 0;
          }
          if ( !v23 )
          {
LABEL_63:
            v24 = WinHttpOpenRequest(*(HINTERNET *)(dwContext + 56), 0, 0, 0, 0, 0, 0);
            *(_QWORD *)(dwContext + 64) = v24;
            if ( v24 )
              goto LABEL_77;
            v25 = GetLastError();
            LastError = v25;
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
              && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
            {
              if ( v25 > 0 )
                v26 = (unsigned __int16)v25 | 0x80070000;
              else
                v26 = (unsigned int)v25;
              WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 61, &WPP_410e2d598473313f5e012b5f9c63d8ac_Traceguids, v26);
            }
            v27 = LastError < 0;
            if ( LastError > 0 )
            {
              LastError = (unsigned __int16)LastError | 0x80070000;
              v27 = LastError < 0;
            }
            if ( !v27 )
            {
LABEL_77:
              EventW = CreateEventW(0, 0, 0, 0);
              *(_QWORD *)(dwContext + 80) = EventW;
              if ( !EventW
                && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
                && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
              {
                v29 = GetLastError();
                if ( v29 > 0 )
                  v29 = (unsigned __int16)v29 | 0x80070000;
                WPP_SF_d(
                  *((_QWORD *)WPP_GLOBAL_Control + 2),
                  63,
                  &WPP_410e2d598473313f5e012b5f9c63d8ac_Traceguids,
                  (unsigned int)v29);
              }
              if ( (unsigned __int64)(*(_QWORD *)(dwContext + 80) - 1LL) > 0xFFFFFFFFFFFFFFFDuLL )
              {
                v39 = GetLastError();
                LastError = v39;
                if ( v39 > 0 )
                  LastError = (unsigned __int16)v39 | 0x80070000;
                if ( LastError >= 0 )
                  LastError = -2147467259;
                wil::details::in1diag3::_Log_Hr(
                  retaddr,
                  (void *)0x1F7,
                  (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\prov\\trans\\ieproxy.cpp",
                  (const char *)(unsigned int)LastError,
                  dwFlagsb);
                v10 = (PVOID *)WPP_GLOBAL_Control;
                if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *((char *)WPP_GLOBAL_Control + 28) < 0 )
                {
                  v11 = 64;
                  goto LABEL_135;
                }
              }
              else
              {
                v30 = CreateEventW(0, 0, 0, 0);
                *(_QWORD *)(dwContext + 88) = v30;
                if ( !v30
                  && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                  && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
                  && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
                {
                  v31 = GetLastError();
                  if ( v31 > 0 )
                    v31 = (unsigned __int16)v31 | 0x80070000;
                  WPP_SF_d(
                    *((_QWORD *)WPP_GLOBAL_Control + 2),
                    65,
                    &WPP_410e2d598473313f5e012b5f9c63d8ac_Traceguids,
                    (unsigned int)v31);
                }
                if ( (unsigned __int64)(*(_QWORD *)(dwContext + 88) - 1LL) > 0xFFFFFFFFFFFFFFFDuLL )
                {
                  v38 = GetLastError();
                  LastError = v38;
                  if ( v38 > 0 )
                    LastError = (unsigned __int16)v38 | 0x80070000;
                  if ( LastError >= 0 )
                    LastError = -2147467259;
                  wil::details::in1diag3::_Log_Hr(
                    retaddr,
                    (void *)0x1FE,
                    (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\prov\\trans\\ieproxy.cpp",
                    (const char *)(unsigned int)LastError,
                    dwFlagsb);
                  v10 = (PVOID *)WPP_GLOBAL_Control;
                  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *((char *)WPP_GLOBAL_Control + 28) < 0 )
                  {
                    v11 = 66;
                    goto LABEL_135;
                  }
                }
                else
                {
                  if ( WinHttpSetStatusCallback(
                         *(HINTERNET *)(dwContext + 64),
                         CIEProxyFromWinHttp::InternetStatusCallBack,
                         0x97E0000u,
                         0) != (WINHTTP_STATUS_CALLBACK)-1LL )
                    goto LABEL_153;
                  v32 = GetLastError();
                  LastError = v32;
                  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
                    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
                  {
                    if ( v32 > 0 )
                      v33 = (unsigned __int16)v32 | 0x80070000;
                    else
                      v33 = (unsigned int)v32;
                    WPP_SF_d(
                      *((_QWORD *)WPP_GLOBAL_Control + 2),
                      67,
                      &WPP_410e2d598473313f5e012b5f9c63d8ac_Traceguids,
                      v33);
                  }
                  v34 = LastError < 0;
                  if ( LastError > 0 )
                  {
                    LastError = (unsigned __int16)LastError | 0x80070000;
                    v34 = LastError < 0;
                  }
                  if ( v34 )
                  {
                    wil::details::in1diag3::_Log_Hr(
                      retaddr,
                      (void *)0x208,
                      (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\prov\\trans\\ieproxy.cpp",
                      (const char *)(unsigned int)LastError,
                      dwFlagsb);
                    v10 = (PVOID *)WPP_GLOBAL_Control;
                    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *((char *)WPP_GLOBAL_Control + 28) < 0 )
                    {
                      v11 = 68;
                      goto LABEL_135;
                    }
                  }
                  else
                  {
LABEL_153:
                    if ( WinHttpSendRequest(*(HINTERNET *)(dwContext + 64), 0, 0, 0, 0, 0, dwContext) )
                    {
LABEL_136:
                      v10 = (PVOID *)WPP_GLOBAL_Control;
                      goto LABEL_137;
                    }
                    v35 = GetLastError();
                    LastError = v35;
                    v10 = (PVOID *)WPP_GLOBAL_Control;
                    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
                      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
                    {
                      if ( v35 > 0 )
                        v36 = (unsigned __int16)v35 | 0x80070000;
                      else
                        v36 = (unsigned int)v35;
                      WPP_SF_d(
                        *((_QWORD *)WPP_GLOBAL_Control + 2),
                        69,
                        &WPP_410e2d598473313f5e012b5f9c63d8ac_Traceguids,
                        v36);
                      v10 = (PVOID *)WPP_GLOBAL_Control;
                    }
                    v37 = LastError < 0;
                    if ( LastError > 0 )
                    {
                      LastError = (unsigned __int16)LastError | 0x80070000;
                      v37 = LastError < 0;
                    }
                    if ( v37 )
                    {
                      wil::details::in1diag3::_Log_Hr(
                        retaddr,
                        (void *)0x215,
                        (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\prov\\trans\\ieproxy.cpp",
                        (const char *)(unsigned int)LastError,
                        dwFlagsc);
                      v10 = (PVOID *)WPP_GLOBAL_Control;
                      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *((char *)WPP_GLOBAL_Control + 28) < 0 )
                      {
                        v11 = 70;
                        goto LABEL_135;
                      }
                    }
                  }
                }
              }
            }
            else
            {
              wil::details::in1diag3::_Log_Hr(
                retaddr,
                (void *)0x1EE,
                (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\prov\\trans\\ieproxy.cpp",
                (const char *)(unsigned int)LastError,
                dwFlagsb);
              v10 = (PVOID *)WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *((char *)WPP_GLOBAL_Control + 28) < 0 )
              {
                v11 = 62;
                goto LABEL_135;
              }
            }
          }
          else
          {
            wil::details::in1diag3::_Log_Hr(
              retaddr,
              (void *)0x1DD,
              (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\prov\\trans\\ieproxy.cpp",
              (const char *)(unsigned int)LastError,
              dwFlagsa);
            v10 = (PVOID *)WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *((char *)WPP_GLOBAL_Control + 28) < 0 )
            {
              v11 = 60;
              goto LABEL_135;
            }
          }
        }
        else
        {
          wil::details::in1diag3::_Log_Hr(
            retaddr,
            (void *)0x1D6,
            (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\prov\\trans\\ieproxy.cpp",
            (const char *)(unsigned int)LastError,
            dwFlagsa);
          v10 = (PVOID *)WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *((char *)WPP_GLOBAL_Control + 28) < 0 )
          {
            v11 = 58;
            goto LABEL_135;
          }
        }
      }
      else
      {
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x1CE,
          (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\prov\\trans\\ieproxy.cpp",
          (const char *)(unsigned int)LastError,
          dwFlagsa);
        v10 = (PVOID *)WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *((char *)WPP_GLOBAL_Control + 28) < 0 )
        {
          v11 = 56;
          goto LABEL_135;
        }
      }
    }
    else
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          53,
          &WPP_410e2d598473313f5e012b5f9c63d8ac_Traceguids,
          (unsigned int)v12);
      }
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x1C0,
        (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\prov\\trans\\ieproxy.cpp",
        (const char *)(unsigned int)LastError,
        dwFlags);
      v10 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *((char *)WPP_GLOBAL_Control + 28) < 0 )
      {
        v11 = 54;
        goto LABEL_135;
      }
    }
  }
  else
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        51,
        &WPP_410e2d598473313f5e012b5f9c63d8ac_Traceguids,
        (unsigned int)v8);
    }
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x1BC,
      (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\prov\\trans\\ieproxy.cpp",
      (const char *)(unsigned int)LastError,
      dwFlags);
    v10 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *((char *)WPP_GLOBAL_Control + 28) < 0 )
    {
      v11 = 52;
LABEL_135:
      WPP_SF_d(v10[2], v11, &WPP_410e2d598473313f5e012b5f9c63d8ac_Traceguids, (unsigned int)LastError);
      goto LABEL_136;
    }
  }
LABEL_137:
  if ( pszAgentW )
  {
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, (LPVOID)pszAgentW);
    v10 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( LastError < 0 )
  {
    if ( *(_QWORD *)(dwContext + 64) )
    {
      WinHttpSetStatusCallback(*(HINTERNET *)(dwContext + 64), 0, 0, 0);
      v10 = (PVOID *)WPP_GLOBAL_Control;
    }
    if ( (unsigned __int64)(*(_QWORD *)(dwContext + 80) - 1LL) <= 0xFFFFFFFFFFFFFFFDuLL )
    {
      CloseHandle(*(HANDLE *)(dwContext + 80));
      *(_QWORD *)(dwContext + 80) = 0;
      v10 = (PVOID *)WPP_GLOBAL_Control;
    }
    if ( (unsigned __int64)(*(_QWORD *)(dwContext + 88) - 1LL) <= 0xFFFFFFFFFFFFFFFDuLL )
    {
      CloseHandle(*(HANDLE *)(dwContext + 88));
      *(_QWORD *)(dwContext + 88) = 0;
      v10 = (PVOID *)WPP_GLOBAL_Control;
    }
  }
  if ( v10 != &WPP_GLOBAL_Control && (*((_BYTE *)v10 + 28) & 4) != 0 && *((_BYTE *)v10 + 25) >= 6u )
    WPP_SF_d(v10[2], 71, &WPP_410e2d598473313f5e012b5f9c63d8ac_Traceguids, (unsigned int)LastError);
  return (unsigned int)LastError;
}

```

## disassembly

```asm
0x1800620e4  push    rbx
0x1800620e6  push    rbp
0x1800620e7  push    rsi
0x1800620e8  push    rdi
0x1800620e9  push    r13
0x1800620eb  push    r14
0x1800620ed  sub     rsp, 58h
0x1800620f1  movzx   esi, r9w
0x1800620f5  mov     rdi, r8
0x1800620f8  mov     rbx, rdx
0x1800620fb  mov     rbp, rcx
0x1800620fe  mov     rcx, cs:WPP_GLOBAL_Control
0x180062105  lea     r14, WPP_GLOBAL_Control
0x18006210c  cmp     rcx, r14
0x18006210f  jz      short loc_180062132
0x180062111  test    byte ptr [rcx+1Ch], 4
0x180062115  jz      short loc_180062132
0x180062117  cmp     byte ptr [rcx+19h], 6
0x18006211b  jb      short loc_180062132
0x18006211d  mov     rcx, [rcx+10h]
0x180062121  mov     r9, rdx
0x180062124  mov     dword ptr [rsp+88h+ppwszAcceptTypes], esi
0x180062128  mov     qword ptr [rsp+88h+dwFlags], r8; int
0x18006212d  call    WPP_SF_ssd
0x180062132  lea     rdx, [rsp+88h+pszAgentW]; unsigned __int16 **
0x180062137  mov     [rsp+88h+pszAgentW], 0
0x180062140  mov     rcx, rbx; lpMultiByteStr
0x180062143  call    ?WpnUtf8ToUtf16@@YAJPEBDPEAPEAG@Z; WpnUtf8ToUtf16(char const *,ushort * *)
0x180062148  mov     ebx, eax
0x18006214a  test    eax, eax
0x18006214c  jns     short loc_1800621C4
0x18006214e  mov     rcx, cs:WPP_GLOBAL_Control
0x180062155  lea     rsi, WPP_410e2d598473313f5e012b5f9c63d8ac_Traceguids
0x18006215c  cmp     rcx, r14
0x18006215f  jz      short loc_180062184
0x180062161  test    byte ptr [rcx+1Ch], 4
0x180062165  jz      short loc_180062184
0x180062167  mov     dil, 2
0x18006216a  cmp     [rcx+19h], dil
0x18006216e  jb      short loc_180062184
0x180062170  mov     rcx, [rcx+10h]
0x180062174  mov     edx, 33h ; '3'
0x180062179  mov     r9d, eax
0x18006217c  mov     r8, rsi
0x18006217f  call    WPP_SF_d
0x180062184  mov     rcx, [rsp+88h]; this
0x18006218c  lea     r8, aOnecoreuapBase_26; "onecoreuap\\base\\diagnosis\\platform\\"...
0x180062193  mov     r9d, ebx; char *
0x180062196  mov     edx, 1BCh; void *
0x18006219b  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800621a0  mov     rcx, cs:WPP_GLOBAL_Control
0x1800621a7  cmp     rcx, r14
0x1800621aa  jz      loc_18006286E
0x1800621b0  test    byte ptr [rcx+1Ch], 80h
0x1800621b4  jz      loc_18006286E
0x1800621ba  mov     edx, 34h ; '4'
0x1800621bf  jmp     loc_180062858
0x1800621c4  lea     rdx, [rbp+20h]; unsigned __int16 **
0x1800621c8  mov     rcx, rdi; lpMultiByteStr
0x1800621cb  call    ?WpnUtf8ToUtf16@@YAJPEBDPEAPEAG@Z; WpnUtf8ToUtf16(char const *,ushort * *)
0x1800621d0  mov     ebx, eax
0x1800621d2  test    eax, eax
0x1800621d4  jns     short loc_180062253
0x1800621d6  mov     rcx, cs:WPP_GLOBAL_Control
0x1800621dd  lea     r14, WPP_GLOBAL_Control
0x1800621e4  lea     rsi, WPP_410e2d598473313f5e012b5f9c63d8ac_Traceguids
0x1800621eb  cmp     rcx, r14
0x1800621ee  jz      short loc_180062213
0x1800621f0  test    byte ptr [rcx+1Ch], 4
0x1800621f4  jz      short loc_180062213
0x1800621f6  mov     dil, 2
0x1800621f9  cmp     [rcx+19h], dil
0x1800621fd  jb      short loc_180062213
0x1800621ff  mov     rcx, [rcx+10h]
0x180062203  mov     edx, 35h ; '5'
0x180062208  mov     r9d, eax
0x18006220b  mov     r8, rsi
0x18006220e  call    WPP_SF_d
0x180062213  mov     rcx, [rsp+88h]; this
0x18006221b  lea     r8, aOnecoreuapBase_26; "onecoreuap\\base\\diagnosis\\platform\\"...
0x180062222  mov     r9d, ebx; char *
0x180062225  mov     edx, 1C0h; void *
0x18006222a  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18006222f  mov     rcx, cs:WPP_GLOBAL_Control
0x180062236  cmp     rcx, r14
0x180062239  jz      loc_18006286E
0x18006223f  test    byte ptr [rcx+1Ch], 80h
0x180062243  jz      loc_18006286E
0x180062249  mov     edx, 36h ; '6'
0x18006224e  jmp     loc_180062858
0x180062253  mov     rcx, [rsp+88h+pszAgentW]; pszAgentW
0x180062258  xor     r9d, r9d; pszProxyBypassW
0x18006225b  xor     r8d, r8d; pszProxyW
0x18006225e  mov     [rbp+28h], si
0x180062262  mov     [rsp+88h+dwFlags], 10000000h; int
0x18006226a  lea     edx, [r9+4]; dwAccessType
0x18006226e  call    cs:__imp_WinHttpOpen
0x180062274  mov     [rbp+30h], rax
0x180062278  mov     dil, 2
0x18006227b  lea     rsi, WPP_410e2d598473313f5e012b5f9c63d8ac_Traceguids
0x180062282  mov     r13d, 80070000h
0x180062288  test    rax, rax
0x18006228b  jnz     loc_18006232E
0x180062291  call    cs:__imp_GetLastError
0x180062297  mov     ebx, eax
0x180062299  mov     rcx, cs:WPP_GLOBAL_Control
0x1800622a0  lea     rax, WPP_GLOBAL_Control
0x1800622a7  cmp     rcx, rax
0x1800622aa  jz      short loc_1800622D9
0x1800622ac  test    byte ptr [rcx+1Ch], 4
0x1800622b0  jz      short loc_1800622D9
0x1800622b2  cmp     [rcx+19h], dil
0x1800622b6  jb      short loc_1800622D9
0x1800622b8  test    ebx, ebx
0x1800622ba  jg      short loc_1800622C1
0x1800622bc  mov     r9d, ebx
0x1800622bf  jmp     short loc_1800622C8
0x1800622c1  movzx   r9d, bx
0x1800622c5  or      r9d, r13d
0x1800622c8  mov     rcx, [rcx+10h]
0x1800622cc  mov     edx, 37h ; '7'
0x1800622d1  mov     r8, rsi
0x1800622d4  call    WPP_SF_d
0x1800622d9  test    ebx, ebx
0x1800622db  jle     short loc_1800622E5
0x1800622dd  movzx   ebx, bx
0x1800622e0  or      ebx, r13d
0x1800622e3  test    ebx, ebx
0x1800622e5  jns     short loc_18006232E
0x1800622e7  mov     rcx, [rsp+88h]; this
0x1800622ef  lea     r8, aOnecoreuapBase_26; "onecoreuap\\base\\diagnosis\\platform\\"...
0x1800622f6  mov     r9d, ebx; char *
0x1800622f9  mov     edx, 1CEh; void *
0x1800622fe  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180062303  mov     rcx, cs:WPP_GLOBAL_Control
0x18006230a  lea     r14, WPP_GLOBAL_Control
0x180062311  cmp     rcx, r14
0x180062314  jz      loc_18006286E
0x18006231a  test    byte ptr [rcx+1Ch], 80h
0x18006231e  jz      loc_18006286E
0x180062324  mov     edx, 38h ; '8'
0x180062329  jmp     loc_180062858
0x18006232e  movzx   r8d, word ptr [rbp+28h]; nServerPort
0x180062333  xor     r9d, r9d; dwReserved
0x180062336  mov     rdx, [rbp+20h]; pswzServerName
0x18006233a  mov     rcx, [rbp+30h]; hSession
0x18006233e  call    cs:__imp_WinHttpConnect
0x180062344  mov     [rbp+38h], rax
0x180062348  test    rax, rax
0x18006234b  jnz     loc_1800623E7
0x180062351  call    cs:__imp_GetLastError
0x180062357  mov     ebx, eax
0x180062359  mov     rcx, cs:WPP_GLOBAL_Control
0x180062360  lea     r14, WPP_GLOBAL_Control
0x180062367  cmp     rcx, r14
0x18006236a  jz      short loc_180062399
0x18006236c  test    byte ptr [rcx+1Ch], 4
0x180062370  jz      short loc_180062399
0x180062372  cmp     [rcx+19h], dil
0x180062376  jb      short loc_180062399
0x180062378  test    eax, eax
0x18006237a  jg      short loc_180062381
0x18006237c  mov     r9d, eax
0x18006237f  jmp     short loc_180062388
0x180062381  movzx   r9d, bx
0x180062385  or      r9d, r13d
0x180062388  mov     rcx, [rcx+10h]
0x18006238c  mov     edx, 39h ; '9'
0x180062391  mov     r8, rsi
0x180062394  call    WPP_SF_d
0x180062399  test    ebx, ebx
0x18006239b  jle     short loc_1800623A5
0x18006239d  movzx   ebx, bx
0x1800623a0  or      ebx, r13d
0x1800623a3  test    ebx, ebx
0x1800623a5  jns     short loc_1800623EE
0x1800623a7  mov     rcx, [rsp+88h]; this
0x1800623af  lea     r8, aOnecoreuapBase_26; "onecoreuap\\base\\diagnosis\\platform\\"...
0x1800623b6  mov     r9d, ebx; char *
0x1800623b9  mov     edx, 1D6h; void *
0x1800623be  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800623c3  mov     rcx, cs:WPP_GLOBAL_Control
0x1800623ca  cmp     rcx, r14
0x1800623cd  jz      loc_18006286E
0x1800623d3  test    byte ptr [rcx+1Ch], 80h
0x1800623d7  jz      loc_18006286E
0x1800623dd  mov     edx, 3Ah ; ':'
0x1800623e2  jmp     loc_180062858
0x1800623e7  lea     r14, WPP_GLOBAL_Control
0x1800623ee  mov     rcx, [rbp+38h]; hInternet
0x1800623f2  xor     r9d, r9d; dwBufferLength
0x1800623f5  xor     r8d, r8d; lpBuffer
0x1800623f8  mov     edx, 82h; dwOption
0x1800623fd  call    cs:__imp_WinHttpSetOption
0x180062403  test    eax, eax
0x180062405  jnz     loc_18006249A
0x18006240b  call    cs:__imp_GetLastError
0x180062411  mov     ebx, eax
0x180062413  mov     rcx, cs:WPP_GLOBAL_Control
0x18006241a  cmp     rcx, r14
0x18006241d  jz      short loc_18006244C
0x18006241f  test    byte ptr [rcx+1Ch], 4
0x180062423  jz      short loc_18006244C
0x180062425  cmp     [rcx+19h], dil
0x180062429  jb      short loc_18006244C
0x18006242b  test    eax, eax
0x18006242d  jg      short loc_180062434
0x18006242f  mov     r9d, eax
0x180062432  jmp     short loc_18006243B
0x180062434  movzx   r9d, bx
0x180062438  or      r9d, r13d
0x18006243b  mov     rcx, [rcx+10h]
0x18006243f  mov     edx, 3Bh ; ';'
0x180062444  mov     r8, rsi
0x180062447  call    WPP_SF_d
0x18006244c  test    ebx, ebx
0x18006244e  jle     short loc_180062458
0x180062450  movzx   ebx, bx
0x180062453  or      ebx, r13d
0x180062456  test    ebx, ebx
0x180062458  jns     short loc_18006249A
0x18006245a  mov     rcx, [rsp+88h]; this
0x180062462  lea     r8, aOnecoreuapBase_26; "onecoreuap\\base\\diagnosis\\platform\\"...
0x180062469  mov     r9d, ebx; char *
0x18006246c  mov     edx, 1DDh; void *
0x180062471  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180062476  mov     rcx, cs:WPP_GLOBAL_Control
0x18006247d  cmp     rcx, r14
0x180062480  jz      loc_18006286E
0x180062486  test    byte ptr [rcx+1Ch], 80h
0x18006248a  jz      loc_18006286E
0x180062490  mov     edx, 3Ch ; '<'
0x180062495  jmp     loc_180062858
0x18006249a  mov     rcx, [rbp+38h]; hConnect
0x18006249e  xor     r9d, r9d; pwszVersion
0x1800624a1  mov     [rsp+88h+var_58], 0; dwFlags
0x1800624a9  xor     r8d, r8d; pwszObjectName
0x1800624ac  mov     [rsp+88h+ppwszAcceptTypes], 0; ppwszAcceptTypes
0x1800624b5  xor     edx, edx; pwszVerb
0x1800624b7  mov     qword ptr [rsp+88h+dwFlags], 0; int
0x1800624c0  call    cs:__imp_WinHttpOpenRequest
0x1800624c6  mov     [rbp+40h], rax
0x1800624ca  test    rax, rax
0x1800624cd  jnz     loc_180062562
0x1800624d3  call    cs:__imp_GetLastError
0x1800624d9  mov     ebx, eax
0x1800624db  mov     rcx, cs:WPP_GLOBAL_Control
0x1800624e2  cmp     rcx, r14
0x1800624e5  jz      short loc_180062514
0x1800624e7  test    byte ptr [rcx+1Ch], 4
0x1800624eb  jz      short loc_180062514
0x1800624ed  cmp     [rcx+19h], dil
0x1800624f1  jb      short loc_180062514
0x1800624f3  test    eax, eax
0x1800624f5  jg      short loc_1800624FC
0x1800624f7  mov     r9d, eax
0x1800624fa  jmp     short loc_180062503
0x1800624fc  movzx   r9d, bx
0x180062500  or      r9d, r13d
0x180062503  mov     rcx, [rcx+10h]
0x180062507  mov     edx, 3Dh ; '='
0x18006250c  mov     r8, rsi
0x18006250f  call    WPP_SF_d
0x180062514  test    ebx, ebx
0x180062516  jle     short loc_180062520
0x180062518  movzx   ebx, bx
0x18006251b  or      ebx, r13d
0x18006251e  test    ebx, ebx
0x180062520  jns     short loc_180062562
0x180062522  mov     rcx, [rsp+88h]; this
0x18006252a  lea     r8, aOnecoreuapBase_26; "onecoreuap\\base\\diagnosis\\platform\\"...
0x180062531  mov     r9d, ebx; char *
0x180062534  mov     edx, 1EEh; void *
0x180062539  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18006253e  mov     rcx, cs:WPP_GLOBAL_Control
0x180062545  cmp     rcx, r14
0x180062548  jz      loc_18006286E
0x18006254e  test    byte ptr [rcx+1Ch], 80h
0x180062552  jz      loc_18006286E
0x180062558  mov     edx, 3Eh ; '>'
0x18006255d  jmp     loc_180062858
0x180062562  xor     r9d, r9d; lpName
0x180062565  xor     r8d, r8d; bInitialState
0x180062568  xor     edx, edx; bManualReset
0x18006256a  xor     ecx, ecx; lpEventAttributes
0x18006256c  call    cs:__imp_CreateEventW
0x180062572  mov     [rbp+50h], rax
0x180062576  test    rax, rax
0x180062579  jnz     short loc_1800625BE
0x18006257b  mov     rax, cs:WPP_GLOBAL_Control
0x180062582  cmp     rax, r14
0x180062585  jz      short loc_1800625BE
0x180062587  test    byte ptr [rax+1Ch], 4
0x18006258b  jz      short loc_1800625BE
0x18006258d  cmp     [rax+19h], dil
0x180062591  jb      short loc_1800625BE
0x180062593  call    cs:__imp_GetLastError
0x180062599  test    eax, eax
0x18006259b  jle     short loc_1800625A3
0x18006259d  movzx   eax, ax
  ... truncated ...
```
