# SetNewSSDemo(HWND__ *,int)

- ea: `0x18001c608`
- end: `0x18001ca06`
- name: `?SetNewSSDemo@@YAXPEAUHWND__@@H@Z`
- size: `1022`
- prototype: `void __fastcall(HWND hDlg, int)`
- caller_count: `3`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x18001f7c0`
- `0x1800475c0`
- `0x180048378`

## callees

- `0x18001c608`
- `0x180032834`
- `0x1800358c0`
- `0x180042e80`
- `0x180047550`
- `0x180048580`

## import_xrefs

- `api-ms-win-core-kernel32-legacy-l1-1-0!MulDiv` at `0x18001c682`
- `api-ms-win-core-kernel32-legacy-l1-1-0!MulDiv` at `0x18001c697`
- `api-ms-win-core-kernel32-legacy-l1-1-0!MulDiv` at `0x18001c6aa`
- `api-ms-win-core-kernel32-legacy-l1-1-0!MulDiv` at `0x18001c6bc`
- `api-ms-win-core-kernel32-legacy-l1-1-0!MulDiv` at `0x18001c682`
- `api-ms-win-core-kernel32-legacy-l1-1-0!MulDiv` at `0x18001c697`
- `api-ms-win-core-kernel32-legacy-l1-1-0!MulDiv` at `0x18001c6aa`
- `api-ms-win-core-kernel32-legacy-l1-1-0!MulDiv` at `0x18001c6bc`
- `GDI32!GetStockObject` at `0x18001c751`
- `GDI32!GetStockObject` at `0x18001c751`
- `GDI32!GetObjectW` at `0x18001c814`
- `GDI32!GetObjectW` at `0x18001c814`
- `GDI32!GetDeviceCaps` at `0x18001c653`
- `GDI32!GetDeviceCaps` at `0x18001c660`
- `GDI32!GetDeviceCaps` at `0x18001c653`
- `GDI32!GetDeviceCaps` at `0x18001c660`
- `GDI32!SelectObject` at `0x18001c743`
- `GDI32!SelectObject` at `0x18001c76d`
- `GDI32!SelectObject` at `0x18001c93d`
- `GDI32!SelectObject` at `0x18001c9ba`
- `GDI32!SelectObject` at `0x18001c743`
- `GDI32!SelectObject` at `0x18001c76d`
- `GDI32!SelectObject` at `0x18001c93d`
- `GDI32!SelectObject` at `0x18001c9ba`
- `GDI32!CreateCompatibleDC` at `0x18001c720`
- `GDI32!CreateCompatibleDC` at `0x18001c720`
- `GDI32!DeleteDC` at `0x18001c776`
- `GDI32!DeleteDC` at `0x18001c776`
- `USER32!ReleaseDC` at `0x18001c66d`
- `USER32!ReleaseDC` at `0x18001c72e`
- `USER32!ReleaseDC` at `0x18001c66d`
- `USER32!ReleaseDC` at `0x18001c72e`
- `USER32!GetDC` at `0x18001c640`
- `USER32!GetDC` at `0x18001c70f`
- `USER32!GetDC` at `0x18001c640`
- `USER32!GetDC` at `0x18001c70f`
- `USER32!GetClientRect` at `0x18001c82f`
- `USER32!GetClientRect` at `0x18001c82f`
- `USER32!FillRect` at `0x18001c761`
- `USER32!FillRect` at `0x18001c761`
- `USER32!ShowWindow` at `0x18001c7ae`
- `USER32!ShowWindow` at `0x18001c8b4`
- `USER32!ShowWindow` at `0x18001c7ae`
- `USER32!ShowWindow` at `0x18001c8b4`
- `USER32!GetDlgItem` at `0x18001c822`
- `USER32!GetDlgItem` at `0x18001c9c8`
- `USER32!GetDlgItem` at `0x18001c822`
- `USER32!GetDlgItem` at `0x18001c9c8`
- `USER32!EnumChildWindows` at `0x18001c78d`
- `USER32!EnumChildWindows` at `0x18001c78d`
- `USER32!MoveWindow` at `0x18001c877`
- `USER32!MoveWindow` at `0x18001c877`
- `USER32!DrawIconEx` at `0x18001c9a5`
- `USER32!DrawIconEx` at `0x18001c9a5`
- `USER32!InvalidateRect` at `0x18001c9d6`
- `USER32!InvalidateRect` at `0x18001c9d6`
- `UxTheme!__imp_ClassicGetSystemMetrics` at `0x18001c8d8`
- `UxTheme!__imp_ClassicGetSystemMetrics` at `0x18001c8e6`
- `UxTheme!__imp_ClassicGetSystemMetrics` at `0x18001c8d8`
- `UxTheme!__imp_ClassicGetSystemMetrics` at `0x18001c8e6`

## pseudocode

```c
void __fastcall SetNewSSDemo(HWND hDlg, int a2)
{
  __int64 v3; // r14
  HDC DC; // rbx
  int DeviceCaps; // esi
  int v6; // edi
  LONG v7; // ebx
  int nHeight; // r12d
  int v9; // r13d
  HWND SSDemoParent; // rsi
  HDC v11; // rax
  HDC v12; // rbx
  HDC CompatibleDC; // rdi
  HGDIOBJ v14; // rbx
  HBRUSH StockObject; // rax
  int v16; // edx
  __int64 v17; // rdi
  HWND DlgItem; // rax
  const unsigned __int16 *v19; // rcx
  unsigned int v20; // r8d
  int SystemMetrics; // r14d
  int v22; // eax
  HGDIOBJ v23; // rsi
  HICON v24; // rbx
  HWND v25; // rax
  LONG v26; // [rsp+50h] [rbp-B0h]
  LONG v27; // [rsp+54h] [rbp-ACh]
  int v28; // [rsp+58h] [rbp-A8h]
  RECT pv[2]; // [rsp+60h] [rbp-A0h] BYREF
  RECT rc; // [rsp+80h] [rbp-80h] BYREF
  unsigned __int16 v31[264]; // [rsp+90h] [rbp-70h] BYREF

  v3 = a2;
  DC = GetDC(0);
  DeviceCaps = GetDeviceCaps(DC, 88);
  v6 = GetDeviceCaps(DC, 88);
  ReleaseDC(0, DC);
  v26 = MulDiv(17, v6, 96);
  v7 = v26;
  v27 = MulDiv(16, DeviceCaps, 96);
  nHeight = MulDiv(112, v6, 96);
  v9 = MulDiv(152, DeviceCaps, 96);
  rc.top = v26;
  rc.left = v27;
  rc.right = v27 + v9;
  rc.bottom = nHeight + v26;
  SSDemoParent = GetSSDemoParent(hDlg);
  if ( SSDemoParent )
  {
    if ( (int)v3 >= 0 && dword_18008B238 < 0 && g_hbmDemo )
    {
      v11 = GetDC(0);
      v12 = v11;
      if ( v11 )
      {
        CompatibleDC = CreateCompatibleDC(v11);
        ReleaseDC(0, v12);
        if ( CompatibleDC )
        {
          v14 = SelectObject(CompatibleDC, g_hbmDemo);
          StockObject = (HBRUSH)GetStockObject(4);
          FillRect(CompatibleDC, &rc, StockObject);
          SelectObject(CompatibleDC, v14);
          DeleteDC(CompatibleDC);
        }
      }
      v7 = v26;
    }
    EnumChildWindows(SSDemoParent, EnumSSChildWindowsProc, (LPARAM)SSDemoParent);
    if ( (int)v3 < 0 && dword_18008B238 >= 0 )
      ReloadMonitorBitmap(hDlg, v16);
    ShowWindow(SSDemoParent, 0);
    dword_18008B23C = 0;
    if ( (int)v3 >= 0 )
    {
      dword_18008B238 = v3;
      _mm_lfence();
      v17 = v3;
      if ( *(_WORD *)(&g_aszMethods)[v3] == 80 )
      {
        memset(pv, 0, sizeof(pv));
        if ( g_hbmDemo )
        {
          GetObjectW(g_hbmDemo, 32, pv);
          DlgItem = GetDlgItem(hDlg, 1302);
          GetClientRect(DlgItem, &rc);
          rc.left = v27 + (rc.right - pv[0].top) / 2;
          rc.top = v7 + (rc.bottom - pv[0].right) / 2;
          MoveWindow(SSDemoParent, rc.left, rc.top, v9, nHeight, 0);
          _PathBuildArgs(v31, 0x104u, (const unsigned __int16 *)&g_szSaverName, L" /p %u", SSDemoParent);
          if ( WinExecN(v19, v31, v20) > 0x20 )
          {
            ShowWindow(SSDemoParent, 8);
            dword_18008B23C = 1;
            return;
          }
        }
      }
      if ( (unsigned int)v3 < 0x64 )
      {
        SystemMetrics = ClassicGetSystemMetrics(11);
        v22 = ClassicGetSystemMetrics(12);
        v23 = 0;
        v28 = v22;
        v24 = (HICON)(&g_hIcons)[v17];
        if ( !v24 )
        {
          _mm_lfence();
          if ( *(_WORD *)(&g_aszMethods)[v17] != 73 || (v24 = g_hIdleWildIcon) == 0 )
          {
            v24 = g_hDefaultIcon;
            if ( g_hbmDemo )
            {
              v23 = SelectObject(g_hdcMem, g_hbmDemo);
              v22 = v28;
            }
          }
        }
        DrawIconEx(
          g_hdcMem,
          v27 + (v9 - 2 * SystemMetrics) / 2,
          v26 + (nHeight - 2 * v22) / 2,
          v24,
          2 * SystemMetrics,
          2 * v22,
          0,
          0,
          3u);
        if ( v23 )
          SelectObject(g_hdcMem, v23);
      }
    }
  }
  v25 = GetDlgItem(hDlg, 1302);
  InvalidateRect(v25, 0, 0);
}

```

## disassembly

```asm
0x18001c608  mov     [rsp-8+arg_10], rbx
0x18001c60d  push    rbp
0x18001c60e  push    rsi
0x18001c60f  push    rdi
0x18001c610  push    r12
0x18001c612  push    r13
0x18001c614  push    r14
0x18001c616  push    r15
0x18001c618  lea     rbp, [rsp-1B0h]
0x18001c620  sub     rsp, 2B0h
0x18001c627  mov     rax, cs:__security_cookie
0x18001c62e  xor     rax, rsp
0x18001c631  mov     [rbp+1E0h+var_40], rax
0x18001c638  mov     r15, rcx
0x18001c63b  movsxd  r14, edx
0x18001c63e  xor     ecx, ecx; hWnd
0x18001c640  call    cs:__imp_GetDC
0x18001c646  mov     edi, 58h ; 'X'
0x18001c64b  mov     rcx, rax; hdc
0x18001c64e  mov     edx, edi; index
0x18001c650  mov     rbx, rax
0x18001c653  call    cs:__imp_GetDeviceCaps
0x18001c659  mov     edx, edi; index
0x18001c65b  mov     rcx, rbx; hdc
0x18001c65e  mov     esi, eax
0x18001c660  call    cs:__imp_GetDeviceCaps
0x18001c666  mov     rdx, rbx; hDC
0x18001c669  xor     ecx, ecx; hWnd
0x18001c66b  mov     edi, eax
0x18001c66d  call    cs:__imp_ReleaseDC
0x18001c673  mov     r13d, 60h ; '`'
0x18001c679  mov     edx, edi; nNumerator
0x18001c67b  mov     r8d, r13d; nDenominator
0x18001c67e  lea     ecx, [r13-4Fh]; nNumber
0x18001c682  call    cs:__imp_MulDiv
0x18001c688  mov     r8d, r13d; nDenominator
0x18001c68b  lea     ecx, [r13-50h]; nNumber
0x18001c68f  mov     edx, esi; nNumerator
0x18001c691  mov     [rsp+2E0h+var_290], eax
0x18001c695  mov     ebx, eax
0x18001c697  call    cs:__imp_MulDiv
0x18001c69d  mov     r8d, r13d; nDenominator
0x18001c6a0  lea     ecx, [r13+10h]; nNumber
0x18001c6a4  mov     edx, edi; nNumerator
0x18001c6a6  mov     [rsp+2E0h+var_28C], eax
0x18001c6aa  call    cs:__imp_MulDiv
0x18001c6b0  mov     r8d, r13d; nDenominator
0x18001c6b3  lea     ecx, [r13+38h]; nNumber
0x18001c6b7  mov     edx, esi; nNumerator
0x18001c6b9  mov     r12d, eax
0x18001c6bc  call    cs:__imp_MulDiv
0x18001c6c2  mov     r13d, eax
0x18001c6c5  mov     [rbp+1E0h+rc.top], ebx
0x18001c6c8  mov     eax, [rsp+2E0h+var_28C]
0x18001c6cc  mov     [rbp+1E0h+rc.left], eax
0x18001c6cf  lea     ecx, [rax+r13]
0x18001c6d3  mov     [rbp+1E0h+rc.right], ecx
0x18001c6d6  lea     ecx, [r12+rbx]
0x18001c6da  mov     [rbp+1E0h+rc.bottom], ecx
0x18001c6dd  mov     rcx, r15; hDlg
0x18001c6e0  call    ?GetSSDemoParent@@YAPEAUHWND__@@PEAU1@@Z; GetSSDemoParent(HWND__ *)
0x18001c6e5  mov     rsi, rax
0x18001c6e8  test    rax, rax
0x18001c6eb  jz      loc_18001C9C0
0x18001c6f1  test    r14d, r14d
0x18001c6f4  js      loc_18001C780
0x18001c6fa  cmp     cs:dword_18008B238, 0
0x18001c701  jge     short loc_18001C780
0x18001c703  cmp     cs:?g_hbmDemo@@3PEAUHBITMAP__@@EA, 0; HBITMAP__ * g_hbmDemo
0x18001c70b  jz      short loc_18001C780
0x18001c70d  xor     ecx, ecx; hWnd
0x18001c70f  call    cs:__imp_GetDC
0x18001c715  mov     rbx, rax
0x18001c718  test    rax, rax
0x18001c71b  jz      short loc_18001C77C
0x18001c71d  mov     rcx, rax; hdc
0x18001c720  call    cs:__imp_CreateCompatibleDC
0x18001c726  mov     rdx, rbx; hDC
0x18001c729  xor     ecx, ecx; hWnd
0x18001c72b  mov     rdi, rax
0x18001c72e  call    cs:__imp_ReleaseDC
0x18001c734  test    rdi, rdi
0x18001c737  jz      short loc_18001C77C
0x18001c739  mov     rdx, cs:?g_hbmDemo@@3PEAUHBITMAP__@@EA; h
0x18001c740  mov     rcx, rdi; hdc
0x18001c743  call    cs:__imp_SelectObject
0x18001c749  mov     ecx, 4; i
0x18001c74e  mov     rbx, rax
0x18001c751  call    cs:__imp_GetStockObject
0x18001c757  lea     rdx, [rbp+1E0h+rc]; lprc
0x18001c75b  mov     rcx, rdi; hDC
0x18001c75e  mov     r8, rax; hbr
0x18001c761  call    cs:__imp_FillRect
0x18001c767  mov     rdx, rbx; h
0x18001c76a  mov     rcx, rdi; hdc
0x18001c76d  call    cs:__imp_SelectObject
0x18001c773  mov     rcx, rdi; hdc
0x18001c776  call    cs:__imp_DeleteDC
0x18001c77c  mov     ebx, [rsp+2E0h+var_290]
0x18001c780  mov     r8, rsi; lParam
0x18001c783  lea     rdx, ?EnumSSChildWindowsProc@@YAHPEAUHWND__@@_J@Z; lpEnumFunc
0x18001c78a  mov     rcx, rsi; hWndParent
0x18001c78d  call    cs:__imp_EnumChildWindows
0x18001c793  test    r14d, r14d
0x18001c796  jns     short loc_18001C7A9
0x18001c798  cmp     cs:dword_18008B238, 0
0x18001c79f  jl      short loc_18001C7A9
0x18001c7a1  mov     rcx, r15; hDlg
0x18001c7a4  call    ?ReloadMonitorBitmap@@YAXPEAUHWND__@@H@Z; ReloadMonitorBitmap(HWND__ *,int)
0x18001c7a9  xor     edx, edx; nCmdShow
0x18001c7ab  mov     rcx, rsi; hWnd
0x18001c7ae  call    cs:__imp_ShowWindow
0x18001c7b4  mov     cs:dword_18008B23C, 0
0x18001c7be  test    r14d, r14d
0x18001c7c1  js      loc_18001C9C0
0x18001c7c7  mov     cs:dword_18008B238, r14d
0x18001c7ce  lfence
0x18001c7d1  lea     rax, __ImageBase
0x18001c7d8  mov     rdi, r14
0x18001c7db  mov     rax, rva ?g_aszMethods@@3PAPEAGA[rax+r14*8]; ushort * near * g_aszMethods ...
0x18001c7e3  cmp     word ptr [rax], 50h ; 'P'
0x18001c7e7  jnz     loc_18001C8C9
0x18001c7ed  mov     rcx, cs:?g_hbmDemo@@3PEAUHBITMAP__@@EA; h
0x18001c7f4  xorps   xmm0, xmm0
0x18001c7f7  movups  [rsp+2E0h+pv], xmm0
0x18001c7fc  movups  [rsp+2E0h+var_270], xmm0
0x18001c801  test    rcx, rcx
0x18001c804  jz      loc_18001C8C9
0x18001c80a  lea     r8, [rsp+2E0h+pv]; pv
0x18001c80f  mov     edx, 20h ; ' '; c
0x18001c814  call    cs:__imp_GetObjectW
0x18001c81a  mov     edx, 516h; nIDDlgItem
0x18001c81f  mov     rcx, r15; hDlg
0x18001c822  call    cs:__imp_GetDlgItem
0x18001c828  mov     rcx, rax; hWnd
0x18001c82b  lea     rdx, [rbp+1E0h+rc]; lpRect
0x18001c82f  call    cs:__imp_GetClientRect
0x18001c835  mov     eax, [rbp+1E0h+rc.right]
0x18001c838  mov     r8d, 2
0x18001c83e  sub     eax, dword ptr [rsp+2E0h+pv+4]
0x18001c842  mov     r9d, r13d; nWidth
0x18001c845  cdq
0x18001c846  mov     [rsp+2E0h+bRepaint], 0; bRepaint
0x18001c84e  idiv    r8d
0x18001c851  mov     [rsp+2E0h+nHeight], r12d; nHeight
0x18001c856  mov     ecx, eax
0x18001c858  mov     eax, [rbp+1E0h+rc.bottom]
0x18001c85b  sub     eax, dword ptr [rsp+2E0h+pv+8]
0x18001c85f  add     ecx, [rsp+2E0h+var_28C]
0x18001c863  cdq
0x18001c864  idiv    r8d
0x18001c867  mov     [rbp+1E0h+rc.left], ecx
0x18001c86a  mov     edx, ecx; X
0x18001c86c  add     eax, ebx
0x18001c86e  mov     rcx, rsi; hWnd
0x18001c871  mov     r8d, eax; Y
0x18001c874  mov     [rbp+1E0h+rc.top], eax
0x18001c877  call    cs:__imp_MoveWindow
0x18001c87d  lea     r9, aPU; " /p %u"
0x18001c884  mov     qword ptr [rsp+2E0h+nHeight], rsi
0x18001c889  lea     r8, ?g_szSaverName@@3PAGA; unsigned __int16 *
0x18001c890  mov     edx, 104h; unsigned int
0x18001c895  lea     rcx, [rbp+1E0h+var_250]; unsigned __int16 *
0x18001c899  call    ?_PathBuildArgs@@YAXPEAGKPEBG1ZZ; _PathBuildArgs(ushort *,ulong,ushort const *,ushort const *,...)
0x18001c89e  lea     rdx, [rbp+1E0h+var_250]; unsigned __int16 *
0x18001c8a2  call    ?WinExecN@@YAIPEBGPEAGI@Z; WinExecN(ushort const *,ushort *,uint)
0x18001c8a7  cmp     eax, 20h ; ' '
0x18001c8aa  jbe     short loc_18001C8C9
0x18001c8ac  mov     edx, 8; nCmdShow
0x18001c8b1  mov     rcx, rsi; hWnd
0x18001c8b4  call    cs:__imp_ShowWindow
0x18001c8ba  mov     cs:dword_18008B23C, 1
0x18001c8c4  jmp     loc_18001C9DC
0x18001c8c9  cmp     r14d, 64h ; 'd'
0x18001c8cd  jnb     loc_18001C9C0
0x18001c8d3  mov     ecx, 0Bh
0x18001c8d8  call    cs:__imp_ClassicGetSystemMetrics
0x18001c8de  mov     ecx, 0Ch
0x18001c8e3  mov     r14d, eax
0x18001c8e6  call    cs:__imp_ClassicGetSystemMetrics
0x18001c8ec  lea     rcx, __ImageBase
0x18001c8f3  xor     esi, esi
0x18001c8f5  mov     [rsp+2E0h+var_288], eax
0x18001c8f9  mov     rbx, rva ?g_hIcons@@3PAPEAUHICON__@@A[rcx+rdi*8]; HICON__ * near * g_hIcons ...
0x18001c901  test    rbx, rbx
0x18001c904  jnz     short loc_18001C94A
0x18001c906  lfence
0x18001c909  mov     rcx, rva ?g_aszMethods@@3PAPEAGA[rcx+rdi*8]; ushort * near * g_aszMethods ...
0x18001c911  cmp     word ptr [rcx], 49h ; 'I'
0x18001c915  jnz     short loc_18001C923
0x18001c917  mov     rbx, cs:?g_hIdleWildIcon@@3PEAUHICON__@@EA; HICON__ * g_hIdleWildIcon
0x18001c91e  test    rbx, rbx
0x18001c921  jnz     short loc_18001C94A
0x18001c923  mov     rdx, cs:?g_hbmDemo@@3PEAUHBITMAP__@@EA; h
0x18001c92a  mov     rbx, cs:?g_hDefaultIcon@@3PEAUHICON__@@EA; HICON__ * g_hDefaultIcon
0x18001c931  test    rdx, rdx
0x18001c934  jz      short loc_18001C94A
0x18001c936  mov     rcx, cs:?g_hdcMem@@3PEAUHDC__@@EA; hdc
0x18001c93d  call    cs:__imp_SelectObject
0x18001c943  mov     rsi, rax
0x18001c946  mov     eax, [rsp+2E0h+var_288]
0x18001c94a  lea     ecx, [rax+rax]
0x18001c94d  mov     [rsp+2E0h+diFlags], 3; diFlags
0x18001c955  sub     r12d, ecx
0x18001c958  mov     [rsp+2E0h+hbrFlickerFreeDraw], 0; hbrFlickerFreeDraw
0x18001c961  mov     r9d, 2
0x18001c967  mov     [rsp+2E0h+istepIfAniCur], 0; istepIfAniCur
0x18001c96f  mov     eax, r12d
0x18001c972  mov     [rsp+2E0h+bRepaint], ecx; cyWidth
0x18001c976  mov     rcx, cs:?g_hdcMem@@3PEAUHDC__@@EA; hdc
0x18001c97d  lea     r10d, [r14+r14]
0x18001c981  cdq
0x18001c982  mov     [rsp+2E0h+nHeight], r10d; cxWidth
0x18001c987  idiv    r9d
0x18001c98a  sub     r13d, r10d
0x18001c98d  mov     r8d, eax
0x18001c990  mov     eax, r13d
0x18001c993  add     r8d, [rsp+2E0h+var_290]; yTop
0x18001c998  cdq
0x18001c999  idiv    r9d
0x18001c99c  mov     r9, rbx; hIcon
0x18001c99f  add     eax, [rsp+2E0h+var_28C]
0x18001c9a3  mov     edx, eax; xLeft
0x18001c9a5  call    cs:__imp_DrawIconEx
0x18001c9ab  test    rsi, rsi
0x18001c9ae  jz      short loc_18001C9C0
0x18001c9b0  mov     rcx, cs:?g_hdcMem@@3PEAUHDC__@@EA; hdc
0x18001c9b7  mov     rdx, rsi; h
0x18001c9ba  call    cs:__imp_SelectObject
0x18001c9c0  mov     edx, 516h; nIDDlgItem
0x18001c9c5  mov     rcx, r15; hDlg
0x18001c9c8  call    cs:__imp_GetDlgItem
0x18001c9ce  xor     r8d, r8d; bErase
0x18001c9d1  xor     edx, edx; lpRect
0x18001c9d3  mov     rcx, rax; hWnd
0x18001c9d6  call    cs:__imp_InvalidateRect
0x18001c9dc  mov     rcx, [rbp+1E0h+var_40]
0x18001c9e3  xor     rcx, rsp; StackCookie
0x18001c9e6  call    __security_check_cookie
0x18001c9eb  mov     rbx, [rsp+2E0h+arg_10]
0x18001c9f3  add     rsp, 2B0h
0x18001c9fa  pop     r15
0x18001c9fc  pop     r14
0x18001c9fe  pop     r13
0x18001ca00  pop     r12
0x18001ca02  pop     rdi
0x18001ca03  pop     rsi
0x18001ca04  pop     rbp
0x18001ca05  retn
```
