# Shell_NotifyIconW

- ea: `0x180020c70`
- end: `0x18002130c`
- name: `Shell_NotifyIconW`
- size: `1692`
- prototype: `BOOL __stdcall(DWORD dwMessage, PNOTIFYICONDATAW lpData)`
- caller_count: `8`
- callee_count: `8`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x180142fa0`
- `0x1803b208c`
- `0x1803b21b8`
- `0x1803b2208`
- `0x1803b22dc`
- `0x1804274f4`
- `0x18042760c`
- `0x1804277b0`

## callees

- `0x1800208d8`
- `0x180020c70`
- `0x180021314`
- `0x180021490`
- `0x180233280`
- `0x1802342e4`
- `0x1802342fc`
- `0x180562de0`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!GetLongPathNameW` at `0x180020f45`
- `api-ms-win-core-file-l1-1-0!GetLongPathNameW` at `0x180020f45`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180021015`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180021025`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002118c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180021015`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180021025`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002118c`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180020cb7`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180021034`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002104b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800211ac`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002120c`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180021289`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180021301`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180020cb7`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180021034`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002104b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800211ac`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002120c`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180021289`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180021301`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800212d1`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800212d1`
- `USER32!ChangeWindowMessageFilterEx` at `0x180020f7f`
- `USER32!ChangeWindowMessageFilterEx` at `0x180020f98`
- `USER32!ChangeWindowMessageFilterEx` at `0x1800211e9`
- `USER32!ChangeWindowMessageFilterEx` at `0x180020f7f`
- `USER32!ChangeWindowMessageFilterEx` at `0x180020f98`
- `USER32!ChangeWindowMessageFilterEx` at `0x1800211e9`
- `USER32!GetIconInfo` at `0x1800210e7`
- `USER32!GetIconInfo` at `0x180021226`
- `USER32!GetIconInfo` at `0x1800210e7`
- `USER32!GetIconInfo` at `0x180021226`
- `USER32!RegisterWindowMessageW` at `0x1800212c0`
- `USER32!RegisterWindowMessageW` at `0x1800212c0`
- `USER32!SendMessageTimeoutW` at `0x18002100a`
- `USER32!SendMessageTimeoutW` at `0x18002100a`
- `USER32!GetWindowThreadProcessId` at `0x180020efa`
- `USER32!GetWindowThreadProcessId` at `0x1800212a4`
- `USER32!GetWindowThreadProcessId` at `0x180020efa`
- `USER32!GetWindowThreadProcessId` at `0x1800212a4`
- `USER32!AllowSetForegroundWindow` at `0x1800212ae`
- `USER32!AllowSetForegroundWindow` at `0x1800212ae`
- `USER32!FindWindowW` at `0x180020cc8`
- `USER32!FindWindowW` at `0x180020cc8`
- `USER32!GetSystemMetrics` at `0x1800210a4`
- `USER32!GetSystemMetrics` at `0x1800210af`
- `USER32!GetSystemMetrics` at `0x180021117`
- `USER32!GetSystemMetrics` at `0x180021124`
- `USER32!GetSystemMetrics` at `0x1800210a4`
- `USER32!GetSystemMetrics` at `0x1800210af`
- `USER32!GetSystemMetrics` at `0x180021117`
- `USER32!GetSystemMetrics` at `0x180021124`
- `GDI32!DeleteObject` at `0x180021267`
- `GDI32!DeleteObject` at `0x180021272`
- `GDI32!DeleteObject` at `0x180021267`
- `GDI32!DeleteObject` at `0x180021272`
- `GDI32!GetObjectW` at `0x180021104`
- `GDI32!GetObjectW` at `0x18002123f`
- `GDI32!GetObjectW` at `0x180021104`
- `GDI32!GetObjectW` at `0x18002123f`
- `api-ms-win-shcore-path-l1-1-0!__imp_PathIsNetworkPathW` at `0x180020f27`
- `api-ms-win-shcore-path-l1-1-0!__imp_PathIsNetworkPathW` at `0x180020f27`

## string_xrefs

- `0x1800212b9`: `TaskbarCreated`

## pseudocode

```c
BOOL __stdcall Shell_NotifyIconW(DWORD dwMessage, PNOTIFYICONDATAW lpData)
{
  BOOL v4; // edi
  HWND WindowW; // r13
  DWORD cbSize; // r14d
  int v7; // esi
  GUID guidItem; // xmm0
  size_t v9; // r8
  WCHAR *szInfo; // rax
  char *v11; // rcx
  __int64 v12; // rdx
  __int128 v13; // xmm1
  __int128 v14; // xmm0
  __int128 v15; // xmm1
  __int128 v16; // xmm0
  __int128 v17; // xmm1
  __int128 v18; // xmm0
  __int128 v19; // xmm1
  __int128 v20; // xmm0
  __int128 v21; // xmm1
  int v22; // ecx
  __int128 v23; // xmm0
  __int128 v24; // xmm1
  __int128 v25; // xmm0
  __int128 v26; // xmm1
  __int128 v27; // xmm0
  __int128 v28; // xmm1
  HWND hWnd; // rcx
  unsigned int v30; // r8d
  signed int v31; // eax
  bool v32; // sf
  HWND v33; // rcx
  DWORD v34; // r8d
  HWND v35; // r8
  DWORD v36; // ecx
  int SystemMetrics; // esi
  int v39; // eax
  HICON v40; // rcx
  int v41; // r12d
  int v42; // edi
  int v43; // eax
  signed int LastError; // eax
  HWND v45; // rcx
  HICON v46; // rcx
  DWORD v47; // ecx
  DWORD CurrentProcessId; // eax
  unsigned int v49; // r8d
  ICONINFO lParam; // [rsp+40h] [rbp-C0h] BYREF
  DWORD dwProcessId; // [rsp+60h] [rbp-A0h] BYREF
  ULONG_PTR dwResult; // [rsp+68h] [rbp-98h] BYREF
  _OWORD pv[2]; // [rsp+70h] [rbp-90h] BYREF
  _DWORD v54[5]; // [rsp+90h] [rbp-70h] BYREF
  UINT uFlags; // [rsp+A4h] [rbp-5Ch]
  UINT message; // [rsp+A8h] [rbp-58h]
  int hIcon; // [rsp+ACh] [rbp-54h]
  _BYTE v58[254]; // [rsp+B0h] [rbp-50h] BYREF
  __int16 v59; // [rsp+1AEh] [rbp+AEh]
  DWORD dwState; // [rsp+1B0h] [rbp+B0h]
  DWORD dwStateMask; // [rsp+1B4h] [rbp+B4h]
  char v62; // [rsp+1B8h] [rbp+B8h] BYREF
  __int16 v63; // [rsp+3B6h] [rbp+2B6h]
  UINT uTimeout; // [rsp+3B8h] [rbp+2B8h]
  __int128 v65; // [rsp+3BCh] [rbp+2BCh]
  __int128 v66; // [rsp+3CCh] [rbp+2CCh]
  __int128 v67; // [rsp+3DCh] [rbp+2DCh]
  __int128 v68; // [rsp+3ECh] [rbp+2ECh]
  __int128 v69; // [rsp+3FCh] [rbp+2FCh]
  __int128 v70; // [rsp+40Ch] [rbp+30Ch]
  __int128 v71; // [rsp+41Ch] [rbp+31Ch]
  __int128 v72; // [rsp+42Ch] [rbp+32Ch]
  DWORD dwInfoFlags; // [rsp+43Ch] [rbp+33Ch]
  GUID v74; // [rsp+440h] [rbp+340h]
  int hBalloonIcon; // [rsp+450h] [rbp+350h]
  unsigned __int16 v76[262]; // [rsp+454h] [rbp+354h] BYREF
  WCHAR pszPath; // [rsp+660h] [rbp+560h] BYREF
  _BYTE v78[4174]; // [rsp+662h] [rbp+562h] BYREF

  if ( lpData )
  {
    SetLastError(0);
    v4 = 0;
    WindowW = FindWindowW(L"Shell_TrayWnd", 0);
    if ( !WindowW )
      goto LABEL_39;
    cbSize = lpData->cbSize;
    v4 = 1;
    if ( lpData->cbSize != 976 )
    {
      if ( cbSize == 968 )
      {
        v7 = 63;
        goto LABEL_7;
      }
      if ( cbSize == 952 )
      {
        v7 = 31;
        goto LABEL_7;
      }
      v7 = 7;
      cbSize = 168;
LABEL_6:
      if ( !v4 )
        goto LABEL_39;
LABEL_7:
      memset_0(v54, 0, 0x5CCu);
      guidItem = lpData->guidItem;
      v54[3] = lpData->hWnd;
      v54[4] = lpData->uID;
      v9 = 128;
      uFlags = lpData->uFlags;
      message = lpData->uCallbackMessage;
      hIcon = (int)lpData->hIcon;
      dwState = lpData->dwState;
      dwStateMask = lpData->dwStateMask;
      uTimeout = lpData->uTimeout;
      dwInfoFlags = lpData->dwInfoFlags;
      hBalloonIcon = (int)lpData->hBalloonIcon;
      if ( v7 != 7 )
        v9 = 256;
      v74 = guidItem;
      memcpy_0(v58, lpData->szTip, v9);
      szInfo = lpData->szInfo;
      v11 = &v62;
      v12 = 4;
      do
      {
        v13 = *((_OWORD *)szInfo + 1);
        *(_OWORD *)v11 = *(_OWORD *)szInfo;
        v14 = *((_OWORD *)szInfo + 2);
        *((_OWORD *)v11 + 1) = v13;
        v15 = *((_OWORD *)szInfo + 3);
        *((_OWORD *)v11 + 2) = v14;
        v16 = *((_OWORD *)szInfo + 4);
        *((_OWORD *)v11 + 3) = v15;
        v17 = *((_OWORD *)szInfo + 5);
        *((_OWORD *)v11 + 4) = v16;
        v18 = *((_OWORD *)szInfo + 6);
        *((_OWORD *)v11 + 5) = v17;
        v19 = *((_OWORD *)szInfo + 7);
        szInfo += 64;
        *((_OWORD *)v11 + 6) = v18;
        *((_OWORD *)v11 + 7) = v19;
        v11 += 128;
        --v12;
      }
      while ( v12 );
      v20 = *(_OWORD *)lpData->szInfoTitle;
      v21 = *(_OWORD *)&lpData->szInfoTitle[8];
      v22 = v7 & uFlags;
      v54[2] = 956;
      uFlags = v22;
      v65 = v20;
      v23 = *(_OWORD *)&lpData->szInfoTitle[16];
      v66 = v21;
      v24 = *(_OWORD *)&lpData->szInfoTitle[24];
      v67 = v23;
      v25 = *(_OWORD *)&lpData->szInfoTitle[32];
      v68 = v24;
      v26 = *(_OWORD *)&lpData->szInfoTitle[40];
      v69 = v25;
      v27 = *(_OWORD *)&lpData->szInfoTitle[48];
      v70 = v26;
      v28 = *(_OWORD *)&lpData->szInfoTitle[56];
      v71 = v27;
      v72 = v28;
      if ( (v22 & 4) != 0 )
        v59 = 0;
      if ( ((cbSize - 952) & 0xFFFFFFE7) == 0 && (v22 & 0x10) != 0 )
      {
        v63 = 0;
        HIWORD(v72) = 0;
      }
      if ( dwMessage == 3 )
      {
        dwProcessId = 0;
        GetWindowThreadProcessId(WindowW, &dwProcessId);
        AllowSetForegroundWindow(dwProcessId);
      }
      if ( ::message == -1 )
        ::message = RegisterWindowMessageW(L"TaskbarCreated");
      if ( dwMessage )
      {
        if ( dwMessage != 1 )
          goto LABEL_34;
        goto LABEL_29;
      }
      memset_0(v78, 0, 0x1046u);
      hWnd = lpData->hWnd;
      dwProcessId = 0;
      pszPath = 0;
      if ( GetWindowThreadProcessId(hWnd, &dwProcessId) )
      {
        v31 = SHExePathFromPid(dwProcessId, &pszPath, v30);
      }
      else
      {
        LastError = GetLastError();
        v32 = LastError < 0;
        if ( LastError <= 0 )
          goto LABEL_24;
        v31 = (unsigned __int16)LastError | 0x80070000;
      }
      v32 = v31 < 0;
LABEL_24:
      if ( !v32
        || (CurrentProcessId = GetCurrentProcessId(), (int)SHExePathFromPid(CurrentProcessId, &pszPath, v49) >= 0) )
      {
        if ( !PathIsNetworkPathW(&pszPath) && !GetLongPathNameW(&pszPath, &pszPath, 0x824u) )
          ResultFromKnownLastError();
        EncodeCommonRelativePath(v76);
      }
LABEL_29:
      if ( (uFlags & 1) != 0 )
      {
        v33 = lpData->hWnd;
        if ( v33 )
        {
          ChangeWindowMessageFilterEx(v33, message, 1u, 0);
          v34 = 1;
          goto LABEL_32;
        }
      }
LABEL_34:
      if ( dwMessage != 2 || (uFlags & 1) == 0 || (v45 = lpData->hWnd) == 0 )
      {
LABEL_35:
        v35 = lpData->hWnd;
        lParam.hbmMask = (HBITMAP)v54;
        v54[0] = 880096291;
        v54[1] = dwMessage;
        dwResult = 0;
        *(_QWORD *)&lParam.yHotspot = 1484;
        *(_QWORD *)&lParam.fIcon = 1;
        if ( SendMessageTimeoutW(WindowW, 0x4Au, (WPARAM)v35, (LPARAM)&lParam, 0xBu, 0x1B58u, &dwResult) )
        {
          if ( dwResult == 1 )
          {
            v4 = 1;
            v36 = 0;
          }
          else
          {
            v4 = 0;
            v36 = -2147467259;
          }
          SetLastError(v36);
          if ( v4 )
            return v4;
        }
        else
        {
          if ( !GetLastError() )
            SetLastError(0x5B4u);
          v4 = 0;
        }
LABEL_39:
        if ( !GetLastError() )
          SetLastError(0x80004005);
        return v4;
      }
      ChangeWindowMessageFilterEx(v45, message, 2u, 0);
      v34 = 2;
LABEL_32:
      ChangeWindowMessageFilterEx(lpData->hWnd, ::message, v34, 0);
      goto LABEL_35;
    }
    if ( dwMessage > 1 || (lpData->uFlags & 0x10) == 0 || (lpData->dwInfoFlags & 4) == 0 )
      goto LABEL_5;
    SystemMetrics = GetSystemMetrics(11);
    v39 = GetSystemMetrics(11);
    v40 = lpData->hBalloonIcon;
    lParam.fIcon = 1;
    v41 = v39;
    memset(&lParam.xHotspot, 0, 28);
    memset(pv, 0, sizeof(pv));
    if ( !v40 )
    {
      v46 = lpData->hIcon;
      if ( !v46 )
        goto LABEL_5;
      if ( !GetIconInfo(v46, &lParam) )
      {
        v47 = 0;
        goto LABEL_80;
      }
      if ( !GetObjectW(lParam.hbmColor, 32, pv)
        || (lpData->dwInfoFlags & 0x20) == 0
        || SDWORD1(pv[0]) >= 32 && SDWORD2(pv[0]) >= 32 )
      {
        goto LABEL_76;
      }
      goto LABEL_75;
    }
    if ( !GetIconInfo(v40, &lParam) )
    {
      SetLastError(0);
      goto LABEL_77;
    }
    if ( GetObjectW(lParam.hbmColor, 32, pv) )
    {
      v42 = GetSystemMetrics(49);
      v43 = GetSystemMetrics(50);
      if ( (lpData->dwInfoFlags & 0x20) != 0 )
      {
        if ( SDWORD1(pv[0]) < SystemMetrics || SDWORD2(pv[0]) < v41 )
          goto LABEL_75;
      }
      else if ( *(_QWORD *)((char *)pv + 4) != __PAIR64__(v43, v42) )
      {
LABEL_75:
        v4 = 0;
        goto LABEL_76;
      }
      v4 = 1;
    }
LABEL_76:
    DeleteObject(lParam.hbmColor);
    DeleteObject(lParam.hbmMask);
LABEL_77:
    if ( !v4 )
    {
      v47 = 1462;
LABEL_80:
      SetLastError(v47);
    }
LABEL_5:
    v7 = 511;
    goto LABEL_6;
  }
  SetLastError(0x57u);
  return 0;
}

```

## disassembly

```asm
0x180020c70  mov     [rsp-8+arg_10], rbx
0x180020c75  push    rbp
0x180020c76  push    rsi
0x180020c77  push    rdi
0x180020c78  push    r12
0x180020c7a  push    r13
0x180020c7c  push    r14
0x180020c7e  push    r15
0x180020c80  lea     rbp, [rsp-15C0h]
0x180020c88  mov     eax, 16C0h
0x180020c8d  call    _alloca_probe
0x180020c92  sub     rsp, rax
0x180020c95  mov     rax, cs:__security_cookie
0x180020c9c  xor     rax, rsp
0x180020c9f  mov     [rbp+15F0h+var_40], rax
0x180020ca6  mov     rbx, rdx
0x180020ca9  mov     r15d, ecx
0x180020cac  test    rdx, rdx
0x180020caf  jz      loc_1800211A7
0x180020cb5  xor     ecx, ecx; dwErrCode
0x180020cb7  call    cs:__imp_SetLastError
0x180020cbd  xor     edx, edx; lpWindowName
0x180020cbf  lea     rcx, ClassName; "Shell_TrayWnd"
0x180020cc6  xor     edi, edi
0x180020cc8  call    cs:__imp_FindWindowW
0x180020cce  mov     r13, rax
0x180020cd1  test    rax, rax
0x180020cd4  jz      loc_180021025
0x180020cda  mov     r14d, [rbx]
0x180020cdd  mov     edi, 1
0x180020ce2  lea     r12d, [rdi+0Ah]
0x180020ce6  cmp     r14d, 3D0h
0x180020ced  jnz     loc_180021166
0x180020cf3  cmp     r15d, edi
0x180020cf6  jbe     loc_18002108A
0x180020cfc  mov     esi, 1FFh
0x180020d01  test    edi, edi
0x180020d03  jz      loc_180021025
0x180020d09  mov     r12d, 5CCh
0x180020d0f  lea     rcx, [rbp+15F0h+var_1660]; void *
0x180020d13  mov     r8d, r12d; Size
0x180020d16  xor     edx, edx; Val
0x180020d18  call    memset_0
0x180020d1d  mov     eax, [rbx+8]
0x180020d20  lea     rdx, [rbx+28h]; Src
0x180020d24  movups  xmm0, xmmword ptr [rbx+3B8h]
0x180020d2b  mov     [rbp+15F0h+var_1654], eax
0x180020d2e  lea     rcx, [rbp+15F0h+var_1640]; void *
0x180020d32  mov     eax, [rbx+10h]
0x180020d35  cmp     esi, 7
0x180020d38  mov     [rbp+15F0h+var_1650], eax
0x180020d3b  mov     edi, 80h
0x180020d40  mov     eax, [rbx+14h]
0x180020d43  mov     r8d, edi
0x180020d46  mov     [rbp+15F0h+var_164C], eax
0x180020d49  mov     eax, [rbx+18h]
0x180020d4c  mov     [rbp+15F0h+message], eax
0x180020d4f  mov     eax, [rbx+20h]
0x180020d52  mov     [rbp+15F0h+var_1644], eax
0x180020d55  mov     eax, [rbx+128h]
0x180020d5b  mov     [rbp+15F0h+var_1540], eax
0x180020d61  mov     eax, [rbx+12Ch]
0x180020d67  mov     [rbp+15F0h+var_153C], eax
0x180020d6d  mov     eax, [rbx+330h]
0x180020d73  mov     [rbp+15F0h+var_1338], eax
0x180020d79  mov     eax, [rbx+3B4h]
0x180020d7f  mov     [rbp+15F0h+var_12B4], eax
0x180020d85  mov     eax, [rbx+3C8h]
0x180020d8b  mov     [rbp+15F0h+var_12A0], eax
0x180020d91  mov     eax, 100h
0x180020d96  cmovnz  r8d, eax; Size
0x180020d9a  movdqu  [rbp+15F0h+var_12B0], xmm0
0x180020da2  call    memcpy_0
0x180020da7  lea     rax, [rbx+130h]
0x180020dae  lea     rcx, [rbp+15F0h+var_1538]
0x180020db5  lea     edx, [rdi-7Ch]
0x180020db8  movups  xmm0, xmmword ptr [rax]
0x180020dbb  movups  xmm1, xmmword ptr [rax+10h]
0x180020dbf  movups  xmmword ptr [rcx], xmm0
0x180020dc2  movups  xmm0, xmmword ptr [rax+20h]
0x180020dc6  movups  xmmword ptr [rcx+10h], xmm1
0x180020dca  movups  xmm1, xmmword ptr [rax+30h]
0x180020dce  movups  xmmword ptr [rcx+20h], xmm0
0x180020dd2  movups  xmm0, xmmword ptr [rax+40h]
0x180020dd6  movups  xmmword ptr [rcx+30h], xmm1
0x180020dda  movups  xmm1, xmmword ptr [rax+50h]
0x180020dde  movups  xmmword ptr [rcx+40h], xmm0
0x180020de2  movups  xmm0, xmmword ptr [rax+60h]
0x180020de6  movups  xmmword ptr [rcx+50h], xmm1
0x180020dea  movups  xmm1, xmmword ptr [rax+70h]
0x180020dee  add     rax, rdi
0x180020df1  movups  xmmword ptr [rcx+60h], xmm0
0x180020df5  movups  xmmword ptr [rcx+70h], xmm1
0x180020df9  add     rcx, rdi
0x180020dfc  sub     rdx, 1
0x180020e00  jnz     short loc_180020DB8
0x180020e02  movups  xmm0, xmmword ptr [rbx+334h]
0x180020e09  mov     ecx, [rbp+15F0h+var_164C]
0x180020e0c  movups  xmm1, xmmword ptr [rbx+344h]
0x180020e13  and     ecx, esi
0x180020e15  mov     [rbp+15F0h+var_1658], 3BCh
0x180020e1c  mov     [rbp+15F0h+var_164C], ecx
0x180020e1f  movups  [rbp+15F0h+var_1334], xmm0
0x180020e26  movups  xmm0, xmmword ptr [rbx+354h]
0x180020e2d  movups  [rbp+15F0h+var_1324], xmm1
0x180020e34  movups  xmm1, xmmword ptr [rbx+364h]
0x180020e3b  movups  [rbp+15F0h+var_1314], xmm0
0x180020e42  movups  xmm0, xmmword ptr [rbx+374h]
0x180020e49  movups  [rbp+15F0h+var_1304], xmm1
0x180020e50  movups  xmm1, xmmword ptr [rbx+384h]
0x180020e57  movups  [rbp+15F0h+var_12F4], xmm0
0x180020e5e  movups  xmm0, xmmword ptr [rbx+394h]
0x180020e65  movups  [rbp+15F0h+var_12E4], xmm1
0x180020e6c  movups  xmm1, xmmword ptr [rbx+3A4h]
0x180020e73  movups  [rbp+15F0h+var_12D4], xmm0
0x180020e7a  movups  [rbp+15F0h+var_12C4], xmm1
0x180020e81  test    cl, 4
0x180020e84  jz      short loc_180020E8F
0x180020e86  xor     eax, eax
0x180020e88  mov     [rbp+15F0h+var_1542], ax
0x180020e8f  lea     eax, [r14-3B8h]
0x180020e96  test    eax, 0FFFFFFE7h
0x180020e9b  jnz     short loc_180020EAF
0x180020e9d  cmp     r14d, 3C0h
0x180020ea4  jz      short loc_180020EAF
0x180020ea6  test    cl, 10h
0x180020ea9  jnz     loc_180021151
0x180020eaf  cmp     r15d, 3
0x180020eb3  jz      loc_180021294
0x180020eb9  cmp     cs:message, 0FFFFFFFFh
0x180020ec0  jz      loc_1800212B9
0x180020ec6  test    r15d, r15d
0x180020ec9  jnz     loc_180020FA0
0x180020ecf  xor     edx, edx; Val
0x180020ed1  lea     rcx, [rbp+15F0h+var_108E]; void *
0x180020ed8  mov     r8d, 1046h; Size
0x180020ede  call    memset_0
0x180020ee3  mov     rcx, [rbx+8]; hWnd
0x180020ee7  lea     rdx, [rsp+16F0h+dwProcessId]; lpdwProcessId
0x180020eec  xor     eax, eax
0x180020eee  mov     [rsp+16F0h+dwProcessId], r15d
0x180020ef3  mov     [rbp+15F0h+pszPath], ax
0x180020efa  call    cs:__imp_GetWindowThreadProcessId
0x180020f00  test    eax, eax
0x180020f02  jz      loc_18002118C
0x180020f08  mov     ecx, [rsp+16F0h+dwProcessId]; dwProcessId
0x180020f0c  lea     rdx, [rbp+15F0h+pszPath]; unsigned __int16 *
0x180020f13  call    ?SHExePathFromPid@@YAJKPEAGI@Z; SHExePathFromPid(ulong,ushort *,uint)
0x180020f18  test    eax, eax
0x180020f1a  js      loc_1800212D1
0x180020f20  lea     rcx, [rbp+15F0h+pszPath]; pszPath
0x180020f27  call    cs:__imp_PathIsNetworkPathW
0x180020f2d  test    eax, eax
0x180020f2f  jnz     short loc_180020F53
0x180020f31  mov     r8d, 824h; cchBuffer
0x180020f37  lea     rdx, [rbp+15F0h+pszPath]; lpszLongPath
0x180020f3e  lea     rcx, [rbp+15F0h+pszPath]; lpszShortPath
0x180020f45  call    cs:__imp_GetLongPathNameW
0x180020f4b  test    eax, eax
0x180020f4d  jz      loc_1800212F2
0x180020f53  lea     r8, [rbp+15F0h+pszPath]
0x180020f5a  lea     rcx, [rbp+15F0h+var_129C]; unsigned __int16 *
0x180020f61  call    EncodeCommonRelativePath
0x180020f66  test    byte ptr [rbp+15F0h+var_164C], 1
0x180020f6a  jz      short loc_180020FA6
0x180020f6c  mov     rcx, [rbx+8]; hwnd
0x180020f70  test    rcx, rcx
0x180020f73  jz      short loc_180020FA6
0x180020f75  mov     edx, [rbp+15F0h+message]; message
0x180020f78  xor     r9d, r9d; pChangeFilterStruct
0x180020f7b  lea     r8d, [r9+1]; action
0x180020f7f  call    cs:__imp_ChangeWindowMessageFilterEx
0x180020f85  mov     r8d, 1; action
0x180020f8b  mov     edx, cs:message; message
0x180020f91  xor     r9d, r9d; pChangeFilterStruct
0x180020f94  mov     rcx, [rbx+8]; hwnd
0x180020f98  call    cs:__imp_ChangeWindowMessageFilterEx
0x180020f9e  jmp     short loc_180020FB4
0x180020fa0  cmp     r15d, 1
0x180020fa4  jz      short loc_180020F66
0x180020fa6  mov     edi, 2
0x180020fab  cmp     r15d, edi
0x180020fae  jz      loc_1800211C9
0x180020fb4  mov     r8, [rbx+8]; wParam
0x180020fb8  lea     rax, [rbp+15F0h+var_1660]
0x180020fbc  mov     [rsp+16F0h+h], rax
0x180020fc1  lea     r9, [rsp+16F0h+lParam]; lParam
0x180020fc6  lea     rax, [rsp+16F0h+dwResult]
0x180020fcb  mov     [rbp+15F0h+var_1660], 34753423h
0x180020fd2  mov     [rsp+16F0h+lpdwResult], rax; lpdwResult
0x180020fd7  mov     edx, 4Ah ; 'J'; Msg
0x180020fdc  mov     [rsp+16F0h+uTimeout], 1B58h; uTimeout
0x180020fe4  mov     rcx, r13; hWnd
0x180020fe7  mov     [rsp+16F0h+fuFlags], 0Bh; fuFlags
0x180020fef  mov     [rbp+15F0h+var_165C], r15d
0x180020ff3  mov     [rsp+16F0h+dwResult], 0
0x180020ffc  mov     [rsp+16F0h+lParam+8], r12
0x180021001  mov     [rsp+16F0h+lParam], 1
0x18002100a  call    cs:__imp_SendMessageTimeoutW
0x180021010  test    rax, rax
0x180021013  jnz     short loc_18002103C
0x180021015  call    cs:__imp_GetLastError
0x18002101b  test    eax, eax
0x18002101d  jz      loc_1800212FC
0x180021023  xor     edi, edi
0x180021025  call    cs:__imp_GetLastError
0x18002102b  test    eax, eax
0x18002102d  jnz     short loc_180021055
0x18002102f  mov     ecx, 80004005h; dwErrCode
0x180021034  call    cs:__imp_SetLastError
0x18002103a  jmp     short loc_180021055
0x18002103c  cmp     [rsp+16F0h+dwResult], 1
0x180021042  jnz     short loc_180021081
0x180021044  mov     edi, 1
0x180021049  xor     ecx, ecx; dwErrCode
0x18002104b  call    cs:__imp_SetLastError
0x180021051  test    edi, edi
0x180021053  jz      short loc_180021025
0x180021055  mov     eax, edi
0x180021057  mov     rcx, [rbp+15F0h+var_40]
0x18002105e  xor     rcx, rsp; StackCookie
0x180021061  call    __security_check_cookie
0x180021066  mov     rbx, [rsp+16F0h+arg_10]
0x18002106e  add     rsp, 16C0h
0x180021075  pop     r15
0x180021077  pop     r14
0x180021079  pop     r13
0x18002107b  pop     r12
0x18002107d  pop     rdi
0x18002107e  pop     rsi
0x18002107f  pop     rbp
0x180021080  retn
0x180021081  xor     edi, edi
0x180021083  mov     ecx, 80004005h
0x180021088  jmp     short loc_18002104B
0x18002108a  test    byte ptr [rbx+14h], 10h
0x18002108e  jz      loc_180020CFC
0x180021094  test    byte ptr [rbx+3B4h], 4
0x18002109b  jz      loc_180020CFC
0x1800210a1  mov     ecx, r12d; nIndex
0x1800210a4  call    cs:__imp_GetSystemMetrics
0x1800210aa  mov     ecx, r12d; nIndex
0x1800210ad  mov     esi, eax
0x1800210af  call    cs:__imp_GetSystemMetrics
0x1800210b5  mov     rcx, [rbx+3C8h]; hIcon
0x1800210bc  xorps   xmm0, xmm0
0x1800210bf  mov     dword ptr [rsp+16F0h+lParam], edi
0x1800210c3  mov     r12d, eax
0x1800210c6  movups  xmmword ptr [rsp+16F0h+lParam+4], xmm0
0x1800210cb  movups  xmmword ptr [rsp+16F0h+h], xmm0
0x1800210d0  movups  [rsp+16F0h+pv], xmm0
0x1800210d5  movups  [rbp+15F0h+var_1670], xmm0
0x1800210d9  test    rcx, rcx
0x1800210dc  jz      loc_180021214
0x1800210e2  lea     rdx, [rsp+16F0h+lParam]; piconinfo
0x1800210e7  call    cs:__imp_GetIconInfo
0x1800210ed  test    eax, eax
0x1800210ef  jz      loc_18002120A
0x1800210f5  mov     rcx, [rsp+16F0h+h+8]; h
0x1800210fa  lea     r8, [rsp+16F0h+pv]; pv
0x1800210ff  mov     edx, 20h ; ' '; c
0x180021104  call    cs:__imp_GetObjectW
0x18002110a  test    eax, eax
0x18002110c  jz      loc_180021262
0x180021112  mov     ecx, 31h ; '1'; nIndex
0x180021117  call    cs:__imp_GetSystemMetrics
0x18002111d  mov     ecx, 32h ; '2'; nIndex
0x180021122  mov     edi, eax
0x180021124  call    cs:__imp_GetSystemMetrics
0x18002112a  test    byte ptr [rbx+3B4h], 20h
0x180021131  jz      loc_1800211F7
0x180021137  cmp     dword ptr [rsp+16F0h+pv+4], esi
0x18002113b  jl      loc_180021260
0x180021141  cmp     dword ptr [rsp+16F0h+pv+8], r12d
0x180021146  jge     loc_180021203
0x18002114c  jmp     loc_180021260
0x180021151  xor     eax, eax
0x180021153  mov     [rbp+15F0h+var_133A], ax
0x18002115a  mov     word ptr [rbp+15F0h+var_12C4+0Eh], ax
0x180021161  jmp     loc_180020EAF
0x180021166  cmp     r14d, 3C8h
0x18002116d  jz      short loc_180021182
0x18002116f  cmp     r14d, 3B8h
0x180021176  jnz     short loc_1800211B9
0x180021178  mov     esi, 1Fh
0x18002117d  jmp     loc_180020D09
0x180021182  mov     esi, 3Fh ; '?'
0x180021187  jmp     loc_180020D09
0x18002118c  call    cs:__imp_GetLastError
0x180021192  test    eax, eax
0x180021194  jle     loc_180020F1A
0x18002119a  movzx   eax, ax
0x18002119d  or      eax, 80070000h
0x1800211a2  jmp     loc_180020F18
0x1800211a7  mov     ecx, 57h ; 'W'; dwErrCode
0x1800211ac  call    cs:__imp_SetLastError
0x1800211b2  xor     eax, eax
0x1800211b4  jmp     loc_180021057
0x1800211b9  mov     esi, 7
0x1800211be  mov     r14d, 0A8h
  ... truncated ...
```
