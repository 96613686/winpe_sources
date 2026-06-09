# ThreadShutdownNotify

- ea: `0x180008c10`
- end: `0x180009681`
- name: `ThreadShutdownNotify`
- size: `2673`
- prototype: `__int64 __fastcall(unsigned int, __int64, HWND, DWORD, int *, __int64, __int64)`
- caller_count: `3`
- callee_count: `11`
- tags: `loader_planting, service_task, installer_update`

## callers

- `0x180005474`
- `0x180009688`
- `0x18000a914`

## callees

- `0x180006208`
- `0x180006514`
- `0x180006898`
- `0x180008c10`
- `0x18000b9a8`
- `0x180010f3c`
- `0x180011030`
- `0x1800119e8`
- `0x180011b5c`
- `0x1800138c5`
- `0x1800138f0`

## import_xrefs

- `KERNELBASE!LocalAlloc` at `0x180008f45`
- `KERNELBASE!LocalAlloc` at `0x180008f45`
- `ntdll!NtQueryInformationProcess` at `0x1800093c4`
- `ntdll!NtQueryInformationProcess` at `0x1800093c4`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180008fc2`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1800090bc`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1800090e1`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180009368`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180008fc2`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1800090bc`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1800090e1`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180009368`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180008fa0`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000961b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180008fa0`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000961b`
- `win32u!NtUserQueryInformationThread` at `0x180008db8`
- `win32u!NtUserQueryInformationThread` at `0x180009304`
- `win32u!NtUserQueryInformationThread` at `0x180008db8`
- `win32u!NtUserQueryInformationThread` at `0x180009304`
- `USER32!EnumThreadWindows` at `0x180008d3d`
- `USER32!EnumThreadWindows` at `0x180008d3d`
- `USER32!IsWindowVisible` at `0x180008d7f`
- `USER32!IsWindowVisible` at `0x1800093f0`
- `USER32!IsWindowVisible` at `0x180008d7f`
- `USER32!IsWindowVisible` at `0x1800093f0`
- `USER32!IsHungAppWindow` at `0x180008e26`
- `USER32!IsHungAppWindow` at `0x180008e26`
- `USER32!SetForegroundWindow` at `0x180008e09`
- `USER32!SetForegroundWindow` at `0x180008e09`
- `USER32!PostMessageW` at `0x180008ef1`
- `USER32!PostMessageW` at `0x180008ef1`
- `USER32!SendMessageCallbackW` at `0x180008f8d`
- `USER32!SendMessageCallbackW` at `0x180008f8d`
- `USER32!MsgWaitForMultipleObjects` at `0x180009116`
- `USER32!MsgWaitForMultipleObjects` at `0x180009116`
- `USER32!PeekMessageW` at `0x180009156`
- `USER32!PeekMessageW` at `0x1800091e1`
- `USER32!PeekMessageW` at `0x180009156`
- `USER32!PeekMessageW` at `0x1800091e1`
- `USER32!IsDialogMessageW` at `0x180009180`
- `USER32!IsDialogMessageW` at `0x180009180`
- `USER32!CallMsgFilterW` at `0x18000919b`
- `USER32!CallMsgFilterW` at `0x18000919b`
- `USER32!TranslateMessage` at `0x1800091b5`
- `USER32!TranslateMessage` at `0x1800091b5`
- `USER32!DispatchMessageW` at `0x1800091c5`
- `USER32!DispatchMessageW` at `0x1800091c5`
- `USER32!IsWindow` at `0x1800092dd`
- `USER32!IsWindow` at `0x1800092dd`
- `USER32!CreateDialogParamW` at `0x18000950e`
- `USER32!CreateDialogParamW` at `0x18000950e`
- `USER32!DestroyWindow` at `0x1800095c8`
- `USER32!DestroyWindow` at `0x1800095c8`
- `USER32!GetWindow` at `0x180008d68`
- `USER32!GetWindow` at `0x180008d68`
- `USER32!IsWindowEnabled` at `0x180008dc9`
- `USER32!IsWindowEnabled` at `0x180008dc9`
- `USER32!SendNotifyMessageW` at `0x180008f29`
- `USER32!SendNotifyMessageW` at `0x180008f29`
- `USER32!__imp_IsCoreWindow` at `0x180008e6d`
- `USER32!__imp_IsCoreWindow` at `0x180008e6d`

## pseudocode

```c
__int64 __fastcall ThreadShutdownNotify(
        unsigned int a1,
        __int64 a2,
        HWND a3,
        DWORD a4,
        int *a5,
        __int64 a6,
        __int64 a7)
{
  int v8; // r12d
  __int64 v9; // rbx
  int v10; // r14d
  _DWORD *dwData; // r15
  unsigned int v13; // r14d
  void *v14; // rdi
  DWORD v15; // r12d
  HWND v16; // rbx
  int v17; // edi
  HWND Window; // rax
  __int64 v19; // rcx
  WPARAM v20; // rbx
  int v21; // edi
  DWORD v22; // ebx
  DWORD TickCount; // eax
  DWORD v24; // eax
  unsigned int v25; // ebx
  signed int v26; // esi
  DWORD v27; // r9d
  __int64 v28; // rsi
  signed int v29; // eax
  HWND v30; // r12
  int v31; // r13d
  int v32; // ecx
  int v33; // ecx
  int v34; // ecx
  int v35; // edx
  __int64 v36; // r14
  __int64 v37; // rcx
  int v38; // ecx
  __int128 v39; // xmm0
  LPARAM v40; // rax
  HANDLE v41; // rcx
  __int64 v42; // rsi
  __int64 v43; // r12
  int v44; // r14d
  int *v45; // rcx
  int v46; // [rsp+30h] [rbp-D0h]
  LPARAM lParam; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v48; // [rsp+48h] [rbp-B8h]
  WPARAM wParam; // [rsp+50h] [rbp-B0h] BYREF
  int v50; // [rsp+58h] [rbp-A8h] BYREF
  int v51; // [rsp+5Ch] [rbp-A4h]
  int v52; // [rsp+60h] [rbp-A0h]
  HANDLE v53; // [rsp+68h] [rbp-98h]
  DWORD v54; // [rsp+70h] [rbp-90h]
  DWORD nCount; // [rsp+74h] [rbp-8Ch]
  __int64 v56; // [rsp+78h] [rbp-88h]
  UINT v57; // [rsp+80h] [rbp-80h] BYREF
  HWND hDlg; // [rsp+88h] [rbp-78h]
  HWND hWnd; // [rsp+90h] [rbp-70h]
  int *v60; // [rsp+98h] [rbp-68h]
  tagMSG Msg; // [rsp+A0h] [rbp-60h] BYREF
  _BYTE v62[16]; // [rsp+D0h] [rbp-30h] BYREF
  __int64 v63; // [rsp+E0h] [rbp-20h]
  HANDLE v64; // [rsp+E8h] [rbp-18h]
  LPARAM v65; // [rsp+F0h] [rbp-10h]
  int dwInitParam; // [rsp+160h] [rbp+60h] BYREF
  int dwInitParam_4; // [rsp+164h] [rbp+64h] BYREF
  int v68; // [rsp+168h] [rbp+68h]
  __int64 v69; // [rsp+170h] [rbp+70h]
  HANDLE v70; // [rsp+178h] [rbp+78h]
  LPARAM v71; // [rsp+180h] [rbp+80h]
  _OWORD ProcessInformation[2]; // [rsp+1F0h] [rbp+F0h] BYREF
  HANDLE pHandles[2]; // [rsp+210h] [rbp+110h] BYREF
  __int64 v74; // [rsp+220h] [rbp+120h]

  v8 = a1;
  v9 = a7;
  hWnd = a3;
  wParam = a1;
  v60 = a5;
  v48 = a6;
  lParam = 0;
  v54 = a4;
  memset_0(&dwInitParam, 0, 0x90u);
  v50 = 0;
  v74 = 0;
  memset(&Msg, 0, sizeof(Msg));
  *(_OWORD *)pHandles = 0;
  if ( a5 )
    *a5 = 0;
  v10 = v8 & 0x10;
  v51 = v10;
  if ( (v8 & 0x10) != 0 && (unsigned int)dword_18001D8F0 > 8 )
    return 4;
  v46 = 0;
  dwData = 0;
  v52 = v8 & 0x20;
  if ( (v8 & 0x20) == 0 )
  {
    v15 = *(_DWORD *)(a2 + 48);
    v53 = *(HANDLE *)(a2 + 64);
    lParam = (LPARAM)hWnd;
    v16 = hWnd;
    if ( !hWnd )
    {
      EnumThreadWindows(v15, FindWindowFromThread, (LPARAM)&lParam);
      v16 = (HWND)lParam;
      if ( !lParam )
        return 5;
    }
    v17 = 0;
    v56 = a2;
    while ( 1 )
    {
      Window = GetWindow(v16, 4u);
      v16 = Window;
      if ( !Window || !IsWindowVisible(Window) )
        break;
      lParam = (LPARAM)v16;
    }
    if ( v10 )
    {
      v19 = *(_QWORD *)(a2 + 64);
      HIDWORD(wParam) = gCmsHungAppTimeout;
      NtUserQueryInformationThread(v19, 4, (char *)&wParam + 4, 4);
      if ( !IsWindowEnabled((HWND)lParam) || HIDWORD(wParam) )
        v17 = 1;
    }
    else
    {
      if ( IsHungAppWindow((HWND)lParam) && (unsigned int)ThreadWindowsCanBlock(a2, &v50) && !v50 )
      {
        EtwBlockingAppLog(2, lParam);
        return 3;
      }
      if ( (unsigned int)IsCoreWindow(lParam) )
      {
        v20 = (unsigned int)wParam;
        if ( (wParam & 0x80000800) == 0x80000800 )
          return 3;
        goto LABEL_21;
      }
    }
    if ( v17 )
    {
      v8 = wParam;
      v13 = 0;
      v14 = v53;
LABEL_55:
      v9 = a7;
      goto LABEL_56;
    }
    v20 = (unsigned int)wParam;
LABEL_21:
    if ( (v20 & 0x200) != 0 )
    {
      if ( (v20 & 2) != 0 || !(unsigned int)ThreadWindowsCanBlock(a2, &v50) )
      {
        v13 = (unsigned int)gCmsQuickAppShutdownTimeout >> 1;
      }
      else
      {
        v13 = gCmsQuickAppShutdownTimeout;
        if ( v50 )
          v13 = gCmsQuickAppShutdownCleanupTimeout;
      }
    }
    else
    {
      SetForegroundWindow((HWND)lParam);
      v13 = gCmsHungAppTimeout;
    }
    v21 = v51;
    if ( v51 )
    {
      EtwLogThreadShutdown_SentMessage(16, 0, v15);
      PostMessageW((HWND)lParam, 0x10u, 0, 0);
LABEL_45:
      v22 = v54;
      if ( v54 == -1 )
      {
        v8 = wParam;
      }
      else
      {
        TickCount = GetTickCount();
        v8 = wParam;
        if ( TickCount - v22 >= gCmsQuickResolverTimeout && !v21 && (wParam & 0x80u) == 0LL && !gfAllowBlockingApps )
        {
          memset_0(v62, 0, 0x90u);
          v9 = a7;
          v14 = v53;
          v65 = lParam;
          v64 = v53;
          v63 = a2;
          if ( (unsigned int)PrepareResolverEntry(a7, v62) )
          {
            ShowResolverDialog(v48, a7);
            v46 = 1;
          }
          goto LABEL_56;
        }
      }
      v14 = v53;
      goto LABEL_55;
    }
    if ( (v20 & 0x102) == 0 )
    {
      EtwLogThreadShutdown_SentMessage(59, v20, v15);
      SendNotifyMessageW((HWND)lParam, 0x3Bu, v20, 0);
      return 1;
    }
    dwData = LocalAlloc(0x40u, 8u);
    if ( dwData )
    {
      EtwLogThreadShutdown_SentMessage(59, v20, v15);
      if ( SendMessageCallbackW((HWND)lParam, 0x3Bu, v20, 0, WMCSCallback, (ULONG_PTR)dwData) )
      {
        v21 = v51;
        goto LABEL_45;
      }
      LocalFree(dwData);
    }
    return 3;
  }
  v56 = 0;
  v13 = 0;
  v53 = (HANDLE)a2;
  v14 = (void *)a2;
LABEL_56:
  hDlg = 0;
  _InterlockedIncrement(&dword_18001D8F0);
  memset_0(&dwInitParam_4, 0, 0x8Cu);
  pHandles[1] = v14;
  pHandles[0] = gheventCancel;
  dwInitParam = 1;
  nCount = 2;
  if ( v46 )
  {
    v74 = *(_QWORD *)(v9 + 32);
    nCount = 3;
  }
  v24 = GetTickCount();
  v54 = v24;
  v25 = 0;
  while ( 1 )
  {
    HIDWORD(wParam) = v13;
    v26 = v13;
    if ( v13 - 1 <= 0xFFFFFFFD )
    {
      v26 = v24 + v13 - GetTickCount();
      HIDWORD(wParam) = v26;
      if ( v26 < 0 )
      {
        v26 = 0;
        HIDWORD(wParam) = 0;
      }
    }
    v27 = v26;
    v28 = nCount;
    v29 = MsgWaitForMultipleObjects(nCount, pHandles, 0, v27, 0x1CFFu);
    if ( v29 == 258 )
    {
      if ( (v8 & 0x80u) != 0 )
        goto LABEL_142;
      v35 = v52;
      if ( !v52 )
      {
        v36 = v56;
        if ( (unsigned int)BoostHardError(*(_QWORD *)(v56 + 40), 2) || GetInputWindow(v36, (HWND)lParam) )
        {
          dwInitParam |= 0x10u;
        }
        else
        {
          if ( !IsWindow((HWND)lParam) )
          {
            v37 = *(_QWORD *)(v36 + 64);
            v57 = gCmsHungAppTimeout;
            NtUserQueryInformationThread(v37, 4, &v57, 4);
            if ( !v57 )
            {
LABEL_142:
              v25 = 1;
              goto LABEL_143;
            }
          }
          if ( (v8 & 0x40) != 0 || (v8 & 0x18) == 0 )
            goto LABEL_141;
          v38 = v51;
          if ( v51 )
          {
            dwInitParam |= 4u;
            v35 = v52;
            goto LABEL_115;
          }
          if ( dwData )
          {
            if ( (*(_BYTE *)dwData & 2) != 0 && dwData[1] == 3 )
            {
              memset(ProcessInformation, 0, sizeof(ProcessInformation));
              GetTickCount();
              EtwBlockingAppLog(1, lParam);
              v39 = *(_OWORD *)(v36 + 40);
              qword_180021C00 = lParam;
              xmmword_180021BE8 = v39;
              if ( NtQueryInformationProcess(
                     *(HANDLE *)(*(_QWORD *)(v36 + 56) + 80LL),
                     ProcessTimes,
                     ProcessInformation,
                     0x20u,
                     0) >= 0 )
                qword_180021BF8 = *(_QWORD *)&ProcessInformation[0];
            }
          }
          if ( !gfAllowBlockingApps && !IsWindowVisible((HWND)lParam) && !(unsigned int)ThreadWindowsCanBlock(v36, 0) )
            goto LABEL_141;
          dwInitParam |= 8u;
        }
        v35 = v52;
      }
      v38 = v51;
LABEL_115:
      if ( gfAutoEndTask )
        goto LABEL_141;
      v13 = -1;
      v68 = 0;
      dwInitParam_4 = v8;
      v70 = v53;
      if ( v35 )
      {
        v40 = (LPARAM)hWnd;
        v69 = 0;
      }
      else
      {
        v69 = v56;
        v40 = lParam;
      }
      v71 = v40;
      if ( v38 || gfAllowBlockingApps )
      {
        hDlg = CreateDialogParamW(ghModuleWin, (LPCWSTR)0xA, 0, EndTaskDlgProc, (LPARAM)&dwInitParam);
        if ( !hDlg )
        {
          dwInitParam |= 1u;
LABEL_141:
          v25 = 3;
LABEL_143:
          v42 = a7;
          v43 = v48;
LABEL_144:
          v44 = v46;
          goto LABEL_145;
        }
      }
      else
      {
        if ( v35 )
          goto LABEL_141;
        if ( v46 )
          ResetResolverDialog(v48, a7);
        if ( !(unsigned int)PrepareResolverEntry(a7, &dwInitParam) )
          goto LABEL_141;
        ShowResolverDialog(v48, a7);
        if ( !v46 )
        {
          v46 = 1;
          pHandles[v28] = *(HANDLE *)(a7 + 32);
          nCount = v28 + 1;
        }
      }
      goto LABEL_128;
    }
    if ( v29 >= 0 && v29 < (unsigned int)v28 )
      break;
    if ( v29 != (_DWORD)v28 )
    {
      v25 = 3;
      goto LABEL_128;
    }
    if ( PeekMessageW(&Msg, 0, 0, 0, 1u) )
    {
      v30 = hDlg;
      v31 = v52;
      do
      {
        if ( ((dwInitParam & 1) != 0 || !IsDialogMessageW(v30, &Msg))
          && (v31 && !CallMsgFilterW(&Msg, 0) || (dwInitParam & 1) != 0) )
        {
          TranslateMessage(&Msg);
          DispatchMessageW(&Msg);
        }
      }
      while ( PeekMessageW(&Msg, 0, 0, 0, 1u) );
      v8 = wParam;
    }
    if ( !dwData || (*dwData & 6) != 2 )
      goto LABEL_88;
    *dwData |= 4u;
    v32 = dwData[1];
    if ( v32 )
    {
      v33 = v32 - 1;
      if ( !v33 )
        goto LABEL_86;
      v34 = v33 - 1;
      if ( !v34 )
        goto LABEL_87;
      if ( v34 != 1 )
        goto LABEL_86;
      if ( v13 != -1 )
        v13 = 0;
    }
    else if ( !(unsigned int)ThreadWindowsCanBlock(v56, &v50) || !v50 )
    {
LABEL_86:
      BoostHardError(*(_QWORD *)(v56 + 40), 1);
LABEL_87:
      v25 = 1;
    }
LABEL_88:
    if ( (dwInitParam & 3) == 3 )
    {
      if ( v68 != 259 )
      {
        v44 = v46;
        v42 = a7;
        v43 = v48;
        if ( v68 == 260 )
          v25 = 7;
        else
          v25 = 4;
        goto LABEL_145;
      }
      v25 = 3;
      if ( (dwInitParam & 4) == 0 )
        goto LABEL_143;
      v25 = v68 - 259 + 6;
    }
LABEL_128:
    if ( v25 )
      goto LABEL_143;
    v24 = v54;
  }
  v41 = pHandles[v29];
  if ( v41 == gheventCancel )
  {
    v25 = 4;
    goto LABEL_143;
  }
  v42 = a7;
  v43 = v48;
  if ( v41 == v53 )
  {
    v25 = 1;
    goto LABEL_144;
  }
  v44 = 0;
  v25 = 4;
  if ( (unsigned int)ResetResolverDialog(v48, a7) == 260 )
    v25 = 7;
LABEL_145:
  if ( (dwInitParam & 1) == 0 )
    DestroyWindow(hDlg);
  if ( v44 )
    ResetResolverDialog(v43, v42);
  v45 = v60;
  if ( dwData && v60 )
    *v60 = (*dwData >> 1) & 1;
  if ( v25 == 4 && v45 )
    *v45 = 1;
  if ( dwData )
  {
    if ( (*dwData & 2) != 0 )
      LocalFree(dwData);
    else
      *dwData |= 1u;
  }
  if ( v25 == 3 && !v52 )
    BoostHardError(*(_QWORD *)(v56 + 40), 1);
  _InterlockedDecrement(&dword_18001D8F0);
  return v25;
}

```

## disassembly

```asm
0x180008c10  mov     [rsp-8+arg_18], rbx
0x180008c15  push    rbp
0x180008c16  push    rsi
0x180008c17  push    rdi
0x180008c18  push    r12
0x180008c1a  push    r13
0x180008c1c  push    r14
0x180008c1e  push    r15
0x180008c20  lea     rbp, [rsp-130h]
0x180008c28  sub     rsp, 230h
0x180008c2f  mov     rax, cs:__security_cookie
0x180008c36  xor     rax, rsp
0x180008c39  mov     [rbp+160h+var_38], rax
0x180008c40  mov     rax, [rbp+160h+arg_28]
0x180008c47  mov     rsi, rdx
0x180008c4a  mov     rdi, [rbp+160h+arg_20]
0x180008c51  mov     r12d, ecx
0x180008c54  mov     rbx, [rbp+160h+arg_30]
0x180008c5b  xor     r13d, r13d
0x180008c5e  mov     [rbp+160h+hWnd], r8
0x180008c62  xor     edx, edx; Val
0x180008c64  mov     dword ptr [rsp+260h+wParam], ecx
0x180008c68  mov     r8d, 90h; Size
0x180008c6e  lea     rcx, [rbp+160h+dwInitParam]; void *
0x180008c72  mov     [rbp+160h+var_1C8], rdi
0x180008c76  mov     [rsp+260h+var_218], rax
0x180008c7b  mov     [rsp+260h+var_228], rbx
0x180008c80  mov     [rsp+260h+lParam], r13
0x180008c85  mov     [rsp+260h+var_1F0], r9d
0x180008c8a  call    memset_0
0x180008c8f  xorps   xmm0, xmm0
0x180008c92  mov     dword ptr [rsp+260h+wParam+4], r13d
0x180008c97  xor     eax, eax
0x180008c99  mov     [rsp+260h+var_208], r13d
0x180008c9e  mov     [rbp+160h+var_40], rax
0x180008ca5  movups  xmmword ptr [rbp+160h+Msg.hwnd], xmm0
0x180008ca9  movups  xmmword ptr [rbp+160h+Msg.wParam], xmm0
0x180008cad  movups  xmmword ptr [rbp+160h+Msg.time], xmm0
0x180008cb1  movups  xmmword ptr [rbp+160h+pHandles], xmm0
0x180008cb8  test    rdi, rdi
0x180008cbb  jz      short loc_180008CC0
0x180008cbd  mov     [rdi], r13d
0x180008cc0  mov     r14d, r12d
0x180008cc3  and     r14d, 10h
0x180008cc7  mov     [rsp+260h+var_204], r14d
0x180008ccc  jz      short loc_180008CE1
0x180008cce  cmp     cs:dword_18001D8F0, 8
0x180008cd5  jbe     short loc_180008CE1
0x180008cd7  mov     eax, 4
0x180008cdc  jmp     loc_180009656
0x180008ce1  mov     eax, r12d
0x180008ce4  mov     [rsp+260h+var_230], r13d
0x180008ce9  and     eax, 20h
0x180008cec  mov     r15, r13
0x180008cef  mov     [rsp+260h+var_200], eax
0x180008cf3  mov     r13d, 4
0x180008cf9  jz      short loc_180008D10
0x180008cfb  mov     [rsp+260h+var_1E8], r15
0x180008d00  xor     r14d, r14d
0x180008d03  mov     [rsp+260h+var_1F8], rsi
0x180008d08  mov     rdi, rsi
0x180008d0b  jmp     loc_18000905D
0x180008d10  mov     rax, [rsi+40h]
0x180008d14  mov     r12d, [rsi+30h]
0x180008d18  mov     [rsp+260h+var_1F8], rax
0x180008d1d  mov     rax, [rbp+160h+hWnd]
0x180008d21  mov     [rsp+260h+lParam], rax
0x180008d26  mov     rbx, rax
0x180008d29  test    rax, rax
0x180008d2c  jnz     short loc_180008D5B
0x180008d2e  lea     r8, [rsp+260h+lParam]; lParam
0x180008d33  mov     ecx, r12d; dwThreadId
0x180008d36  lea     rdx, FindWindowFromThread; lpfn
0x180008d3d  call    cs:__imp_EnumThreadWindows
0x180008d44  nop     dword ptr [rax+rax+00h]
0x180008d49  mov     rbx, [rsp+260h+lParam]
0x180008d4e  test    rbx, rbx
0x180008d51  jnz     short loc_180008D5B
0x180008d53  lea     eax, [rbx+5]
0x180008d56  jmp     loc_180009656
0x180008d5b  xor     edi, edi
0x180008d5d  mov     [rsp+260h+var_1E8], rsi
0x180008d62  mov     edx, r13d; uCmd
0x180008d65  mov     rcx, rbx; hWnd
0x180008d68  call    cs:__imp_GetWindow
0x180008d6f  nop     dword ptr [rax+rax+00h]
0x180008d74  mov     rbx, rax
0x180008d77  test    rax, rax
0x180008d7a  jz      short loc_180008D96
0x180008d7c  mov     rcx, rax; hWnd
0x180008d7f  call    cs:__imp_IsWindowVisible
0x180008d86  nop     dword ptr [rax+rax+00h]
0x180008d8b  test    eax, eax
0x180008d8d  jz      short loc_180008D96
0x180008d8f  mov     [rsp+260h+lParam], rbx
0x180008d94  jmp     short loc_180008D62
0x180008d96  test    r14d, r14d
0x180008d99  jz      loc_180008E21
0x180008d9f  mov     eax, cs:gCmsHungAppTimeout
0x180008da5  lea     r8, [rsp+260h+wParam+4]
0x180008daa  mov     rcx, [rsi+40h]
0x180008dae  mov     r9d, r13d
0x180008db1  mov     edx, r13d
0x180008db4  mov     dword ptr [rsp+260h+wParam+4], eax
0x180008db8  call    cs:__imp_NtUserQueryInformationThread
0x180008dbf  nop     dword ptr [rax+rax+00h]
0x180008dc4  mov     rcx, [rsp+260h+lParam]; hWnd
0x180008dc9  call    cs:__imp_IsWindowEnabled
0x180008dd0  nop     dword ptr [rax+rax+00h]
0x180008dd5  test    eax, eax
0x180008dd7  jz      short loc_180008DDF
0x180008dd9  cmp     dword ptr [rsp+260h+wParam+4], edi
0x180008ddd  jz      short loc_180008DE4
0x180008ddf  mov     edi, 1
0x180008de4  mov     rax, [rsp+260h+var_1F8]
0x180008de9  mov     [rsp+260h+var_1F8], rax
0x180008dee  test    edi, edi
0x180008df0  jnz     loc_180009041
0x180008df6  mov     ebx, dword ptr [rsp+260h+wParam]
0x180008dfa  bt      ebx, 9
0x180008dfe  jb      loc_180008E97
0x180008e04  mov     rcx, [rsp+260h+lParam]; hWnd
0x180008e09  call    cs:__imp_SetForegroundWindow
0x180008e10  nop     dword ptr [rax+rax+00h]
0x180008e15  mov     r14d, cs:gCmsHungAppTimeout
0x180008e1c  jmp     loc_180008ECD
0x180008e21  mov     rcx, [rsp+260h+lParam]; hwnd
0x180008e26  call    cs:__imp_IsHungAppWindow
0x180008e2d  nop     dword ptr [rax+rax+00h]
0x180008e32  test    eax, eax
0x180008e34  jz      short loc_180008E68
0x180008e36  lea     rdx, [rsp+260h+var_208]
0x180008e3b  mov     rcx, rsi
0x180008e3e  call    ThreadWindowsCanBlock
0x180008e43  test    eax, eax
0x180008e45  jz      short loc_180008E68
0x180008e47  cmp     [rsp+260h+var_208], edi
0x180008e4b  jnz     short loc_180008E68
0x180008e4d  mov     rdx, [rsp+260h+lParam]
0x180008e52  xor     r8d, r8d
0x180008e55  lea     ecx, [r8+2]
0x180008e59  call    EtwBlockingAppLog
0x180008e5e  mov     eax, 3
0x180008e63  jmp     loc_180009656
0x180008e68  mov     rcx, [rsp+260h+lParam]
0x180008e6d  call    cs:__imp_IsCoreWindow
0x180008e74  nop     dword ptr [rax+rax+00h]
0x180008e79  test    eax, eax
0x180008e7b  jz      loc_180008DE4
0x180008e81  mov     ebx, dword ptr [rsp+260h+wParam]
0x180008e85  mov     ecx, 80000800h
0x180008e8a  mov     eax, ebx
0x180008e8c  and     eax, ecx
0x180008e8e  cmp     eax, ecx
0x180008e90  jz      short loc_180008E5E
0x180008e92  jmp     loc_180008DFA
0x180008e97  test    bl, 2
0x180008e9a  jnz     short loc_180008EC3
0x180008e9c  lea     rdx, [rsp+260h+var_208]
0x180008ea1  mov     rcx, rsi
0x180008ea4  call    ThreadWindowsCanBlock
0x180008ea9  test    eax, eax
0x180008eab  jz      short loc_180008EC3
0x180008ead  cmp     [rsp+260h+var_208], r15d
0x180008eb2  mov     r14d, cs:gCmsQuickAppShutdownTimeout
0x180008eb9  cmovnz  r14d, cs:gCmsQuickAppShutdownCleanupTimeout
0x180008ec1  jmp     short loc_180008ECD
0x180008ec3  mov     r14d, cs:gCmsQuickAppShutdownTimeout
0x180008eca  shr     r14d, 1
0x180008ecd  mov     edi, [rsp+260h+var_204]
0x180008ed1  test    edi, edi
0x180008ed3  jz      short loc_180008F02
0x180008ed5  xor     edx, edx
0x180008ed7  mov     r8d, r12d
0x180008eda  lea     ebx, [rdx+10h]
0x180008edd  mov     ecx, ebx
0x180008edf  call    EtwLogThreadShutdown_SentMessage
0x180008ee4  mov     rcx, [rsp+260h+lParam]; hWnd
0x180008ee9  xor     r9d, r9d; lParam
0x180008eec  xor     r8d, r8d; wParam
0x180008eef  mov     edx, ebx; Msg
0x180008ef1  call    cs:__imp_PostMessageW
0x180008ef8  nop     dword ptr [rax+rax+00h]
0x180008efd  jmp     loc_180008FB5
0x180008f02  test    ebx, 102h
0x180008f08  jnz     short loc_180008F3D
0x180008f0a  mov     edi, 3Bh ; ';'
0x180008f0f  mov     r8d, r12d
0x180008f12  mov     ecx, edi
0x180008f14  mov     rdx, rbx
0x180008f17  call    EtwLogThreadShutdown_SentMessage
0x180008f1c  mov     rcx, [rsp+260h+lParam]; hWnd
0x180008f21  xor     r9d, r9d; lParam
0x180008f24  mov     r8, rbx; wParam
0x180008f27  mov     edx, edi; Msg
0x180008f29  call    cs:__imp_SendNotifyMessageW
0x180008f30  nop     dword ptr [rax+rax+00h]
0x180008f35  lea     eax, [rdi-3Ah]
0x180008f38  jmp     loc_180009656
0x180008f3d  mov     edx, 8; uBytes
0x180008f42  lea     ecx, [rdx+38h]; uFlags
0x180008f45  call    cs:__imp_LocalAlloc
0x180008f4c  nop     dword ptr [rax+rax+00h]
0x180008f51  mov     r15, rax
0x180008f54  test    rax, rax
0x180008f57  jz      loc_180008E5E
0x180008f5d  mov     edi, 3Bh ; ';'
0x180008f62  mov     r8d, r12d
0x180008f65  mov     ecx, edi
0x180008f67  mov     rdx, rbx
0x180008f6a  call    EtwLogThreadShutdown_SentMessage
0x180008f6f  mov     rcx, [rsp+260h+lParam]; hWnd
0x180008f74  lea     rax, WMCSCallback
0x180008f7b  mov     [rsp+260h+dwData], r15; dwData
0x180008f80  xor     r9d, r9d; lParam
0x180008f83  mov     r8, rbx; wParam
0x180008f86  mov     [rsp+260h+lpResultCallBack], rax; lpResultCallBack
0x180008f8b  mov     edx, edi; Msg
0x180008f8d  call    cs:__imp_SendMessageCallbackW
0x180008f94  nop     dword ptr [rax+rax+00h]
0x180008f99  test    eax, eax
0x180008f9b  jnz     short loc_180008FB1
0x180008f9d  mov     rcx, r15; hMem
0x180008fa0  call    cs:__imp_LocalFree
0x180008fa7  nop     dword ptr [rax+rax+00h]
0x180008fac  jmp     loc_180008E5E
0x180008fb1  mov     edi, [rsp+260h+var_204]
0x180008fb5  mov     ebx, [rsp+260h+var_1F0]
0x180008fb9  cmp     ebx, 0FFFFFFFFh
0x180008fbc  jz      loc_18000904E
0x180008fc2  call    cs:__imp_GetTickCount
0x180008fc9  nop     dword ptr [rax+rax+00h]
0x180008fce  mov     r12d, dword ptr [rsp+260h+wParam]
0x180008fd3  sub     eax, ebx
0x180008fd5  cmp     eax, cs:gCmsQuickResolverTimeout
0x180008fdb  jb      short loc_180009053
0x180008fdd  test    edi, edi
0x180008fdf  jnz     short loc_180009053
0x180008fe1  test    r12b, r12b
0x180008fe4  js      short loc_180009053
0x180008fe6  cmp     cs:gfAllowBlockingApps, edi
0x180008fec  jnz     short loc_180009053
0x180008fee  xor     edx, edx; Val
0x180008ff0  lea     rcx, [rbp+160h+var_190]; void *
0x180008ff4  mov     r8d, 90h; Size
0x180008ffa  call    memset_0
0x180008fff  mov     rax, [rsp+260h+lParam]
0x180009004  lea     rdx, [rbp+160h+var_190]
0x180009008  mov     rbx, [rsp+260h+var_228]
0x18000900d  mov     rdi, [rsp+260h+var_1F8]
0x180009012  mov     rcx, rbx
0x180009015  mov     [rbp+160h+var_170], rax
0x180009019  mov     [rbp+160h+var_178], rdi
0x18000901d  mov     [rbp+160h+var_180], rsi
0x180009021  call    PrepareResolverEntry
0x180009026  test    eax, eax
0x180009028  jz      short loc_18000905D
0x18000902a  mov     rcx, [rsp+260h+var_218]
0x18000902f  mov     rdx, rbx
0x180009032  call    ShowResolverDialog
0x180009037  mov     [rsp+260h+var_230], 1
0x18000903f  jmp     short loc_18000905D
0x180009041  mov     r12d, dword ptr [rsp+260h+wParam]
0x180009046  xor     r14d, r14d
0x180009049  mov     rdi, rax
0x18000904c  jmp     short loc_180009058
0x18000904e  mov     r12d, dword ptr [rsp+260h+wParam]
0x180009053  mov     rdi, [rsp+260h+var_1F8]
0x180009058  mov     rbx, [rsp+260h+var_228]
0x18000905d  mov     [rbp+160h+hDlg], 0
0x180009065  lock inc cs:dword_18001D8F0
0x18000906c  xor     edx, edx; Val
0x18000906e  lea     rcx, [rbp+160h+dwInitParam+4]; void *
0x180009072  mov     r8d, 8Ch; Size
0x180009078  call    memset_0
0x18000907d  cmp     [rsp+260h+var_230], 0
0x180009082  mov     rax, cs:gheventCancel
0x180009089  mov     [rbp+160h+pHandles+8], rdi
0x180009090  mov     edi, 3
0x180009095  mov     [rbp+160h+pHandles], rax
0x18000909c  mov     dword ptr [rbp+160h+dwInitParam], 1
0x1800090a3  mov     [rsp+260h+nCount], 2
0x1800090ab  jz      short loc_1800090BC
0x1800090ad  mov     rax, [rbx+20h]
0x1800090b1  mov     [rbp+160h+var_40], rax
0x1800090b8  mov     [rsp+260h+nCount], edi
0x1800090bc  call    cs:__imp_GetTickCount
0x1800090c3  nop     dword ptr [rax+rax+00h]
0x1800090c8  mov     [rsp+260h+var_1F0], eax
0x1800090cc  xor     ebx, ebx
0x1800090ce  lea     ecx, [r14-1]
0x1800090d2  mov     dword ptr [rsp+260h+wParam+4], r14d
0x1800090d7  mov     esi, r14d
0x1800090da  cmp     ecx, 0FFFFFFFDh
0x1800090dd  ja      short loc_1800090FB
0x1800090df  add     esi, eax
0x1800090e1  call    cs:__imp_GetTickCount
0x1800090e8  nop     dword ptr [rax+rax+00h]
0x1800090ed  sub     esi, eax
0x1800090ef  mov     dword ptr [rsp+260h+wParam+4], esi
  ... truncated ...
```
