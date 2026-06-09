# Shell_NotifyIconW

- ea: `0x18001ae90`
- end: `0x18001b5ed`
- name: `Shell_NotifyIconW`
- size: `1885`
- prototype: `BOOL __stdcall(DWORD dwMessage, PNOTIFYICONDATAW lpData)`
- caller_count: `8`
- callee_count: `8`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x1801545c0`
- `0x1803da474`
- `0x1803da5b0`
- `0x1803da604`
- `0x1803da6dc`
- `0x1804575b8`
- `0x1804576e0`
- `0x1804578ac`

## callees

- `0x180018e4c`
- `0x18001ae90`
- `0x18001b5f4`
- `0x18001b784`
- `0x180249490`
- `0x18024a524`
- `0x18024a53c`
- `0x1805a3840`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!GetLongPathNameW` at `0x18001b17d`
- `api-ms-win-core-file-l1-1-0!GetLongPathNameW` at `0x18001b17d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001b265`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001b27b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001b419`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001b265`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001b27b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001b419`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001aed7`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001b290`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001b2ad`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001b43f`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001b4ab`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001b546`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001b5dc`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001aed7`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001b290`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001b2ad`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001b43f`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001b4ab`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001b546`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001b5dc`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18001b5a6`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18001b5a6`
- `USER32!ChangeWindowMessageFilterEx` at `0x18001b1bd`
- `USER32!ChangeWindowMessageFilterEx` at `0x18001b1dc`
- `USER32!ChangeWindowMessageFilterEx` at `0x18001b482`
- `USER32!ChangeWindowMessageFilterEx` at `0x18001b1bd`
- `USER32!ChangeWindowMessageFilterEx` at `0x18001b1dc`
- `USER32!ChangeWindowMessageFilterEx` at `0x18001b482`
- `USER32!GetIconInfo` at `0x18001b35c`
- `USER32!GetIconInfo` at `0x18001b4cb`
- `USER32!GetIconInfo` at `0x18001b35c`
- `USER32!GetIconInfo` at `0x18001b4cb`
- `USER32!RegisterWindowMessageW` at `0x18001b58f`
- `USER32!RegisterWindowMessageW` at `0x18001b58f`
- `USER32!SendMessageTimeoutW` at `0x18001b254`
- `USER32!SendMessageTimeoutW` at `0x18001b254`
- `USER32!GetWindowThreadProcessId` at `0x18001b126`
- `USER32!GetWindowThreadProcessId` at `0x18001b567`
- `USER32!GetWindowThreadProcessId` at `0x18001b126`
- `USER32!GetWindowThreadProcessId` at `0x18001b567`
- `USER32!AllowSetForegroundWindow` at `0x18001b577`
- `USER32!AllowSetForegroundWindow` at `0x18001b577`
- `USER32!FindWindowW` at `0x18001aeee`
- `USER32!FindWindowW` at `0x18001aeee`
- `USER32!GetSystemMetrics` at `0x18001b30d`
- `USER32!GetSystemMetrics` at `0x18001b31e`
- `USER32!GetSystemMetrics` at `0x18001b398`
- `USER32!GetSystemMetrics` at `0x18001b3ab`
- `USER32!GetSystemMetrics` at `0x18001b30d`
- `USER32!GetSystemMetrics` at `0x18001b31e`
- `USER32!GetSystemMetrics` at `0x18001b398`
- `USER32!GetSystemMetrics` at `0x18001b3ab`
- `GDI32!DeleteObject` at `0x18001b518`
- `GDI32!DeleteObject` at `0x18001b529`
- `GDI32!DeleteObject` at `0x18001b518`
- `GDI32!DeleteObject` at `0x18001b529`
- `GDI32!GetObjectW` at `0x18001b37f`
- `GDI32!GetObjectW` at `0x18001b4ea`
- `GDI32!GetObjectW` at `0x18001b37f`
- `GDI32!GetObjectW` at `0x18001b4ea`
- `api-ms-win-shcore-path-l1-1-0!__imp_PathIsNetworkPathW` at `0x18001b159`
- `api-ms-win-shcore-path-l1-1-0!__imp_PathIsNetworkPathW` at `0x18001b159`

## string_xrefs

- `0x18001b588`: `TaskbarCreated`

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
0x18001ae90  mov     [rsp-8+arg_10], rbx
0x18001ae95  push    rbp
0x18001ae96  push    rsi
0x18001ae97  push    rdi
0x18001ae98  push    r12
0x18001ae9a  push    r13
0x18001ae9c  push    r14
0x18001ae9e  push    r15
0x18001aea0  lea     rbp, [rsp-15C0h]
0x18001aea8  mov     eax, 16C0h
0x18001aead  call    _alloca_probe
0x18001aeb2  sub     rsp, rax
0x18001aeb5  mov     rax, cs:__security_cookie
0x18001aebc  xor     rax, rsp
0x18001aebf  mov     [rbp+15F0h+var_40], rax
0x18001aec6  mov     rbx, rdx
0x18001aec9  mov     r15d, ecx
0x18001aecc  test    rdx, rdx
0x18001aecf  jz      loc_18001B43A
0x18001aed5  xor     ecx, ecx; dwErrCode
0x18001aed7  call    cs:__imp_SetLastError
0x18001aede  nop     dword ptr [rax+rax+00h]
0x18001aee3  xor     edx, edx; lpWindowName
0x18001aee5  lea     rcx, ClassName; "Shell_TrayWnd"
0x18001aeec  xor     edi, edi
0x18001aeee  call    cs:__imp_FindWindowW
0x18001aef5  nop     dword ptr [rax+rax+00h]
0x18001aefa  mov     r13, rax
0x18001aefd  test    rax, rax
0x18001af00  jz      loc_18001B27B
0x18001af06  mov     r14d, [rbx]
0x18001af09  mov     edi, 1
0x18001af0e  lea     r12d, [rdi+0Ah]
0x18001af12  cmp     r14d, 3D0h
0x18001af19  jnz     loc_18001B3F3
0x18001af1f  cmp     r15d, edi
0x18001af22  jbe     loc_18001B2F3
0x18001af28  mov     esi, 1FFh
0x18001af2d  test    edi, edi
0x18001af2f  jz      loc_18001B27B
0x18001af35  mov     r12d, 5CCh
0x18001af3b  lea     rcx, [rbp+15F0h+var_1660]; void *
0x18001af3f  mov     r8d, r12d; Size
0x18001af42  xor     edx, edx; Val
0x18001af44  call    memset_0
0x18001af49  mov     eax, [rbx+8]
0x18001af4c  lea     rdx, [rbx+28h]; Src
0x18001af50  movups  xmm0, xmmword ptr [rbx+3B8h]
0x18001af57  mov     [rbp+15F0h+var_1654], eax
0x18001af5a  lea     rcx, [rbp+15F0h+var_1640]; void *
0x18001af5e  mov     eax, [rbx+10h]
0x18001af61  cmp     esi, 7
0x18001af64  mov     [rbp+15F0h+var_1650], eax
0x18001af67  mov     edi, 80h
0x18001af6c  mov     eax, [rbx+14h]
0x18001af6f  mov     r8d, edi
0x18001af72  mov     [rbp+15F0h+var_164C], eax
0x18001af75  mov     eax, [rbx+18h]
0x18001af78  mov     [rbp+15F0h+message], eax
0x18001af7b  mov     eax, [rbx+20h]
0x18001af7e  mov     [rbp+15F0h+var_1644], eax
0x18001af81  mov     eax, [rbx+128h]
0x18001af87  mov     [rbp+15F0h+var_1540], eax
0x18001af8d  mov     eax, [rbx+12Ch]
0x18001af93  mov     [rbp+15F0h+var_153C], eax
0x18001af99  mov     eax, [rbx+330h]
0x18001af9f  mov     [rbp+15F0h+var_1338], eax
0x18001afa5  mov     eax, [rbx+3B4h]
0x18001afab  mov     [rbp+15F0h+var_12B4], eax
0x18001afb1  mov     eax, [rbx+3C8h]
0x18001afb7  mov     [rbp+15F0h+var_12A0], eax
0x18001afbd  mov     eax, 100h
0x18001afc2  cmovnz  r8d, eax; Size
0x18001afc6  movdqu  [rbp+15F0h+var_12B0], xmm0
0x18001afce  call    memcpy_0
0x18001afd3  lea     rax, [rbx+130h]
0x18001afda  lea     rcx, [rbp+15F0h+var_1538]
0x18001afe1  lea     edx, [rdi-7Ch]
0x18001afe4  movups  xmm0, xmmword ptr [rax]
0x18001afe7  movups  xmm1, xmmword ptr [rax+10h]
0x18001afeb  movups  xmmword ptr [rcx], xmm0
0x18001afee  movups  xmm0, xmmword ptr [rax+20h]
0x18001aff2  movups  xmmword ptr [rcx+10h], xmm1
0x18001aff6  movups  xmm1, xmmword ptr [rax+30h]
0x18001affa  movups  xmmword ptr [rcx+20h], xmm0
0x18001affe  movups  xmm0, xmmword ptr [rax+40h]
0x18001b002  movups  xmmword ptr [rcx+30h], xmm1
0x18001b006  movups  xmm1, xmmword ptr [rax+50h]
0x18001b00a  movups  xmmword ptr [rcx+40h], xmm0
0x18001b00e  movups  xmm0, xmmword ptr [rax+60h]
0x18001b012  movups  xmmword ptr [rcx+50h], xmm1
0x18001b016  movups  xmm1, xmmword ptr [rax+70h]
0x18001b01a  add     rax, rdi
0x18001b01d  movups  xmmword ptr [rcx+60h], xmm0
0x18001b021  movups  xmmword ptr [rcx+70h], xmm1
0x18001b025  add     rcx, rdi
0x18001b028  sub     rdx, 1
0x18001b02c  jnz     short loc_18001AFE4
0x18001b02e  movups  xmm0, xmmword ptr [rbx+334h]
0x18001b035  mov     ecx, [rbp+15F0h+var_164C]
0x18001b038  movups  xmm1, xmmword ptr [rbx+344h]
0x18001b03f  and     ecx, esi
0x18001b041  mov     [rbp+15F0h+var_1658], 3BCh
0x18001b048  mov     [rbp+15F0h+var_164C], ecx
0x18001b04b  movups  [rbp+15F0h+var_1334], xmm0
0x18001b052  movups  xmm0, xmmword ptr [rbx+354h]
0x18001b059  movups  [rbp+15F0h+var_1324], xmm1
0x18001b060  movups  xmm1, xmmword ptr [rbx+364h]
0x18001b067  movups  [rbp+15F0h+var_1314], xmm0
0x18001b06e  movups  xmm0, xmmword ptr [rbx+374h]
0x18001b075  movups  [rbp+15F0h+var_1304], xmm1
0x18001b07c  movups  xmm1, xmmword ptr [rbx+384h]
0x18001b083  movups  [rbp+15F0h+var_12F4], xmm0
0x18001b08a  movups  xmm0, xmmword ptr [rbx+394h]
0x18001b091  movups  [rbp+15F0h+var_12E4], xmm1
0x18001b098  movups  xmm1, xmmword ptr [rbx+3A4h]
0x18001b09f  movups  [rbp+15F0h+var_12D4], xmm0
0x18001b0a6  movups  [rbp+15F0h+var_12C4], xmm1
0x18001b0ad  test    cl, 4
0x18001b0b0  jz      short loc_18001B0BB
0x18001b0b2  xor     eax, eax
0x18001b0b4  mov     [rbp+15F0h+var_1542], ax
0x18001b0bb  lea     eax, [r14-3B8h]
0x18001b0c2  test    eax, 0FFFFFFE7h
0x18001b0c7  jnz     short loc_18001B0DB
0x18001b0c9  cmp     r14d, 3C0h
0x18001b0d0  jz      short loc_18001B0DB
0x18001b0d2  test    cl, 10h
0x18001b0d5  jnz     loc_18001B3DE
0x18001b0db  cmp     r15d, 3
0x18001b0df  jz      loc_18001B557
0x18001b0e5  cmp     cs:message, 0FFFFFFFFh
0x18001b0ec  jz      loc_18001B588
0x18001b0f2  test    r15d, r15d
0x18001b0f5  jnz     loc_18001B1EA
0x18001b0fb  xor     edx, edx; Val
0x18001b0fd  lea     rcx, [rbp+15F0h+var_108E]; void *
0x18001b104  mov     r8d, 1046h; Size
0x18001b10a  call    memset_0
0x18001b10f  mov     rcx, [rbx+8]; hWnd
0x18001b113  lea     rdx, [rsp+16F0h+dwProcessId]; lpdwProcessId
0x18001b118  xor     eax, eax
0x18001b11a  mov     [rsp+16F0h+dwProcessId], r15d
0x18001b11f  mov     [rbp+15F0h+pszPath], ax
0x18001b126  call    cs:__imp_GetWindowThreadProcessId
0x18001b12d  nop     dword ptr [rax+rax+00h]
0x18001b132  test    eax, eax
0x18001b134  jz      loc_18001B419
0x18001b13a  mov     ecx, [rsp+16F0h+dwProcessId]; dwProcessId
0x18001b13e  lea     rdx, [rbp+15F0h+pszPath]; unsigned __int16 *
0x18001b145  call    ?SHExePathFromPid@@YAJKPEAGI@Z; SHExePathFromPid(ulong,ushort *,uint)
0x18001b14a  test    eax, eax
0x18001b14c  js      loc_18001B5A6
0x18001b152  lea     rcx, [rbp+15F0h+pszPath]; pszPath
0x18001b159  call    cs:__imp_PathIsNetworkPathW
0x18001b160  nop     dword ptr [rax+rax+00h]
0x18001b165  test    eax, eax
0x18001b167  jnz     short loc_18001B191
0x18001b169  mov     r8d, 824h; cchBuffer
0x18001b16f  lea     rdx, [rbp+15F0h+pszPath]; lpszLongPath
0x18001b176  lea     rcx, [rbp+15F0h+pszPath]; lpszShortPath
0x18001b17d  call    cs:__imp_GetLongPathNameW
0x18001b184  nop     dword ptr [rax+rax+00h]
0x18001b189  test    eax, eax
0x18001b18b  jz      loc_18001B5CD
0x18001b191  lea     r8, [rbp+15F0h+pszPath]
0x18001b198  lea     rcx, [rbp+15F0h+var_129C]; unsigned __int16 *
0x18001b19f  call    EncodeCommonRelativePath
0x18001b1a4  test    byte ptr [rbp+15F0h+var_164C], 1
0x18001b1a8  jz      short loc_18001B1F0
0x18001b1aa  mov     rcx, [rbx+8]; hwnd
0x18001b1ae  test    rcx, rcx
0x18001b1b1  jz      short loc_18001B1F0
0x18001b1b3  mov     edx, [rbp+15F0h+message]; message
0x18001b1b6  xor     r9d, r9d; pChangeFilterStruct
0x18001b1b9  lea     r8d, [r9+1]; action
0x18001b1bd  call    cs:__imp_ChangeWindowMessageFilterEx
0x18001b1c4  nop     dword ptr [rax+rax+00h]
0x18001b1c9  mov     r8d, 1; action
0x18001b1cf  mov     edx, cs:message; message
0x18001b1d5  xor     r9d, r9d; pChangeFilterStruct
0x18001b1d8  mov     rcx, [rbx+8]; hwnd
0x18001b1dc  call    cs:__imp_ChangeWindowMessageFilterEx
0x18001b1e3  nop     dword ptr [rax+rax+00h]
0x18001b1e8  jmp     short loc_18001B1FE
0x18001b1ea  cmp     r15d, 1
0x18001b1ee  jz      short loc_18001B1A4
0x18001b1f0  mov     edi, 2
0x18001b1f5  cmp     r15d, edi
0x18001b1f8  jz      loc_18001B462
0x18001b1fe  mov     r8, [rbx+8]; wParam
0x18001b202  lea     rax, [rbp+15F0h+var_1660]
0x18001b206  mov     [rsp+16F0h+h], rax
0x18001b20b  lea     r9, [rsp+16F0h+lParam]; lParam
0x18001b210  lea     rax, [rsp+16F0h+dwResult]
0x18001b215  mov     [rbp+15F0h+var_1660], 34753423h
0x18001b21c  mov     [rsp+16F0h+lpdwResult], rax; lpdwResult
0x18001b221  mov     edx, 4Ah ; 'J'; Msg
0x18001b226  mov     [rsp+16F0h+uTimeout], 1B58h; uTimeout
0x18001b22e  mov     rcx, r13; hWnd
0x18001b231  mov     [rsp+16F0h+fuFlags], 0Bh; fuFlags
0x18001b239  mov     [rbp+15F0h+var_165C], r15d
0x18001b23d  mov     [rsp+16F0h+dwResult], 0
0x18001b246  mov     [rsp+16F0h+lParam+8], r12
0x18001b24b  mov     [rsp+16F0h+lParam], 1
0x18001b254  call    cs:__imp_SendMessageTimeoutW
0x18001b25b  nop     dword ptr [rax+rax+00h]
0x18001b260  test    rax, rax
0x18001b263  jnz     short loc_18001B29E
0x18001b265  call    cs:__imp_GetLastError
0x18001b26c  nop     dword ptr [rax+rax+00h]
0x18001b271  test    eax, eax
0x18001b273  jz      loc_18001B5D7
0x18001b279  xor     edi, edi
0x18001b27b  call    cs:__imp_GetLastError
0x18001b282  nop     dword ptr [rax+rax+00h]
0x18001b287  test    eax, eax
0x18001b289  jnz     short loc_18001B2BD
0x18001b28b  mov     ecx, 80004005h; dwErrCode
0x18001b290  call    cs:__imp_SetLastError
0x18001b297  nop     dword ptr [rax+rax+00h]
0x18001b29c  jmp     short loc_18001B2BD
0x18001b29e  cmp     [rsp+16F0h+dwResult], 1
0x18001b2a4  jnz     short loc_18001B2EA
0x18001b2a6  mov     edi, 1
0x18001b2ab  xor     ecx, ecx; dwErrCode
0x18001b2ad  call    cs:__imp_SetLastError
0x18001b2b4  nop     dword ptr [rax+rax+00h]
0x18001b2b9  test    edi, edi
0x18001b2bb  jz      short loc_18001B27B
0x18001b2bd  mov     eax, edi
0x18001b2bf  mov     rcx, [rbp+15F0h+var_40]
0x18001b2c6  xor     rcx, rsp; StackCookie
0x18001b2c9  call    __security_check_cookie
0x18001b2ce  mov     rbx, [rsp+16F0h+arg_10]
0x18001b2d6  add     rsp, 16C0h
0x18001b2dd  pop     r15
0x18001b2df  pop     r14
0x18001b2e1  pop     r13
0x18001b2e3  pop     r12
0x18001b2e5  pop     rdi
0x18001b2e6  pop     rsi
0x18001b2e7  pop     rbp
0x18001b2e8  retn
0x18001b2ea  xor     edi, edi
0x18001b2ec  mov     ecx, 80004005h
0x18001b2f1  jmp     short loc_18001B2AD
0x18001b2f3  test    byte ptr [rbx+14h], 10h
0x18001b2f7  jz      loc_18001AF28
0x18001b2fd  test    byte ptr [rbx+3B4h], 4
0x18001b304  jz      loc_18001AF28
0x18001b30a  mov     ecx, r12d; nIndex
0x18001b30d  call    cs:__imp_GetSystemMetrics
0x18001b314  nop     dword ptr [rax+rax+00h]
0x18001b319  mov     ecx, r12d; nIndex
0x18001b31c  mov     esi, eax
0x18001b31e  call    cs:__imp_GetSystemMetrics
0x18001b325  nop     dword ptr [rax+rax+00h]
0x18001b32a  mov     rcx, [rbx+3C8h]; hIcon
0x18001b331  xorps   xmm0, xmm0
0x18001b334  mov     dword ptr [rsp+16F0h+lParam], edi
0x18001b338  mov     r12d, eax
0x18001b33b  movups  xmmword ptr [rsp+16F0h+lParam+4], xmm0
0x18001b340  movups  xmmword ptr [rsp+16F0h+h], xmm0
0x18001b345  movups  [rsp+16F0h+pv], xmm0
0x18001b34a  movups  [rbp+15F0h+var_1670], xmm0
0x18001b34e  test    rcx, rcx
0x18001b351  jz      loc_18001B4B9
0x18001b357  lea     rdx, [rsp+16F0h+lParam]; piconinfo
0x18001b35c  call    cs:__imp_GetIconInfo
0x18001b363  nop     dword ptr [rax+rax+00h]
0x18001b368  test    eax, eax
0x18001b36a  jz      loc_18001B4A9
0x18001b370  mov     rcx, [rsp+16F0h+h+8]; h
0x18001b375  lea     r8, [rsp+16F0h+pv]; pv
0x18001b37a  mov     edx, 20h ; ' '; c
0x18001b37f  call    cs:__imp_GetObjectW
0x18001b386  nop     dword ptr [rax+rax+00h]
0x18001b38b  test    eax, eax
0x18001b38d  jz      loc_18001B513
0x18001b393  mov     ecx, 31h ; '1'; nIndex
0x18001b398  call    cs:__imp_GetSystemMetrics
0x18001b39f  nop     dword ptr [rax+rax+00h]
0x18001b3a4  mov     ecx, 32h ; '2'; nIndex
0x18001b3a9  mov     edi, eax
0x18001b3ab  call    cs:__imp_GetSystemMetrics
0x18001b3b2  nop     dword ptr [rax+rax+00h]
0x18001b3b7  test    byte ptr [rbx+3B4h], 20h
0x18001b3be  jz      loc_18001B496
0x18001b3c4  cmp     dword ptr [rsp+16F0h+pv+4], esi
0x18001b3c8  jl      loc_18001B511
0x18001b3ce  cmp     dword ptr [rsp+16F0h+pv+8], r12d
0x18001b3d3  jge     loc_18001B4A2
0x18001b3d9  jmp     loc_18001B511
0x18001b3de  xor     eax, eax
0x18001b3e0  mov     [rbp+15F0h+var_133A], ax
0x18001b3e7  mov     word ptr [rbp+15F0h+var_12C4+0Eh], ax
0x18001b3ee  jmp     loc_18001B0DB
0x18001b3f3  cmp     r14d, 3C8h
0x18001b3fa  jz      short loc_18001B40F
  ... truncated ...
```
