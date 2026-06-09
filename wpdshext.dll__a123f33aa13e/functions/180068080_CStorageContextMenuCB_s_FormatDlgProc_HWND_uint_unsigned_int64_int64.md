# CStorageContextMenuCB::s_FormatDlgProc(HWND__ *,uint,unsigned __int64,__int64)

- ea: `0x180068080`
- end: `0x1800684d2`
- name: `?s_FormatDlgProc@CStorageContextMenuCB@@CA_JPEAUHWND__@@I_K_J@Z`
- size: `1106`
- prototype: `__int64 __fastcall(HWND hWnd, UINT Msg, WPARAM wParam, LPARAM lParam)`
- caller_count: `0`
- callee_count: `10`
- tags: `broker_com_uri`

## callees

- `0x180024fec`
- `0x1800287d0`
- `0x18002ab58`
- `0x180035590`
- `0x1800361ba`
- `0x180041ab0`
- `0x180068080`
- `0x180068518`
- `0x18006ef2c`
- `0x180078010`

## import_xrefs

- `SHLWAPI!__imp_SHCreateThread` at `0x1800683eb`
- `SHLWAPI!__imp_SHCreateThread` at `0x1800683eb`
- `USER32!LoadStringW` at `0x1800681a8`
- `USER32!LoadStringW` at `0x1800682bb`
- `USER32!LoadStringW` at `0x18006841d`
- `USER32!LoadStringW` at `0x1800681a8`
- `USER32!LoadStringW` at `0x1800682bb`
- `USER32!LoadStringW` at `0x18006841d`
- `USER32!SendMessageW` at `0x180068220`
- `USER32!SendMessageW` at `0x180068220`
- `USER32!SetDlgItemTextW` at `0x1800681bd`
- `USER32!SetDlgItemTextW` at `0x1800682ef`
- `USER32!SetDlgItemTextW` at `0x180068432`
- `USER32!SetDlgItemTextW` at `0x1800681bd`
- `USER32!SetDlgItemTextW` at `0x1800682ef`
- `USER32!SetDlgItemTextW` at `0x180068432`
- `USER32!EndDialog` at `0x180068153`
- `USER32!EndDialog` at `0x180068153`
- `USER32!GetDlgItem` at `0x1800681e2`
- `USER32!GetDlgItem` at `0x1800681fb`
- `USER32!GetDlgItem` at `0x18006822e`
- `USER32!GetDlgItem` at `0x1800682fd`
- `USER32!GetDlgItem` at `0x180068316`
- `USER32!GetDlgItem` at `0x18006832f`
- `USER32!GetDlgItem` at `0x180068440`
- `USER32!GetDlgItem` at `0x180068459`
- `USER32!GetDlgItem` at `0x1800681e2`
- `USER32!GetDlgItem` at `0x1800681fb`
- `USER32!GetDlgItem` at `0x18006822e`
- `USER32!GetDlgItem` at `0x1800682fd`
- `USER32!GetDlgItem` at `0x180068316`
- `USER32!GetDlgItem` at `0x18006832f`
- `USER32!GetDlgItem` at `0x180068440`
- `USER32!GetDlgItem` at `0x180068459`
- `USER32!GetWindowLongPtrW` at `0x1800680b9`
- `USER32!GetWindowLongPtrW` at `0x1800680b9`
- `USER32!SetWindowLongPtrW` at `0x1800680d5`
- `USER32!SetWindowLongPtrW` at `0x180068486`
- `USER32!SetWindowLongPtrW` at `0x1800680d5`
- `USER32!SetWindowLongPtrW` at `0x180068486`
- `USER32!ShowWindow` at `0x1800681ed`
- `USER32!ShowWindow` at `0x180068209`
- `USER32!ShowWindow` at `0x180068308`
- `USER32!ShowWindow` at `0x180068321`
- `USER32!ShowWindow` at `0x18006833d`
- `USER32!ShowWindow` at `0x18006844b`
- `USER32!ShowWindow` at `0x180068464`
- `USER32!ShowWindow` at `0x1800681ed`
- `USER32!ShowWindow` at `0x180068209`
- `USER32!ShowWindow` at `0x180068308`
- `USER32!ShowWindow` at `0x180068321`
- `USER32!ShowWindow` at `0x18006833d`
- `USER32!ShowWindow` at `0x18006844b`
- `USER32!ShowWindow` at `0x180068464`
- `USER32!DefWindowProcW` at `0x1800684ad`
- `USER32!DefWindowProcW` at `0x1800684ad`
- `USER32!SetFocus` at `0x180068237`
- `USER32!SetFocus` at `0x180068237`
- `SHELL32!SHGetFileInfoW` at `0x180068397`
- `SHELL32!SHGetFileInfoW` at `0x180068397`
- `SHELL32!__imp_ILFree` at `0x1800683c1`
- `SHELL32!__imp_ILFree` at `0x1800683c1`

## pseudocode

```c
LRESULT __fastcall CStorageContextMenuCB::s_FormatDlgProc(HWND hWnd, UINT Msg, WPARAM wParam, _QWORD *lParam)
{
  _QWORD *WindowLongPtrW; // rsi
  __int64 v9; // r8
  unsigned int v10; // r9d
  UINT v11; // edi
  UINT v12; // edi
  UINT v13; // edi
  PVOID v15; // rcx
  UINT v16; // edx
  HWND v17; // rax
  HWND v18; // rax
  HWND v19; // rax
  CStorageFolder *v20; // rcx
  HWND v21; // rax
  HWND v22; // rax
  HWND v23; // rax
  __int64 v24; // rcx
  const ITEMIDLIST *v25; // rdx
  ITEMIDLIST *v26; // rdi
  HWND DlgItem; // rax
  HWND v28; // rax
  LPCWSTR pszPath[2]; // [rsp+30h] [rbp-D0h] BYREF
  SHFILEINFOW psfi; // [rsp+40h] [rbp-C0h] BYREF
  WCHAR Buffer[264]; // [rsp+300h] [rbp+200h] BYREF
  WCHAR String[264]; // [rsp+510h] [rbp+410h] BYREF
  WCHAR v33[264]; // [rsp+720h] [rbp+620h] BYREF

  WindowLongPtrW = (_QWORD *)GetWindowLongPtrW(hWnd, 16);
  if ( Msg == 272 )
  {
    SetWindowLongPtrW(hWnd, 16, (LONG_PTR)lParam);
    WindowLongPtrW = lParam;
  }
  if ( WindowLongPtrW )
  {
    v11 = Msg - 2;
    if ( !v11 )
    {
      ReplaceDlgIcon(hWnd, 302, 0);
      SetWindowLongPtrW(hWnd, 16, 0);
      (*(void (__fastcall **)(_QWORD *))(*WindowLongPtrW + 16LL))(WindowLongPtrW);
      return 1;
    }
    v12 = v11 - 270;
    if ( !v12 )
    {
      LoadStringW(g_hInst, 0x101u, String, 260);
      SetDlgItemTextW(hWnd, 303, String);
      DlgItem = GetDlgItem(hWnd, 301);
      ShowWindow(DlgItem, 0);
      v28 = GetDlgItem(hWnd, 304);
      ShowWindow(v28, 0);
      return 1;
    }
    v13 = v12 - 1;
    if ( v13 )
    {
      if ( v13 != 851 )
        return 0;
      v15 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 197, WPP_9caa288f52d13f713777aed0becde05d_Traceguids);
      if ( (_DWORD)lParam != -2147023673 )
      {
        pszPath[0] = 0;
        if ( (_DWORD)lParam )
        {
          IsolationAwareLoadIconMetric(v15, 32513, v9, pszPath);
          v16 = 260;
        }
        else
        {
          IsolationAwareLoadIconMetric(v15, 32516, v9, pszPath);
          v16 = 259;
        }
        LoadStringW(g_hInst, v16, Buffer, 260);
        SetDlgItemTextW(hWnd, 303, Buffer);
        if ( pszPath[0] )
          ReplaceDlgIcon(hWnd, 302, pszPath[0]);
        v17 = GetDlgItem(hWnd, 301);
        ShowWindow(v17, 0);
        v18 = GetDlgItem(hWnd, 304);
        ShowWindow(v18, 5);
        SendMessageW(hWnd, 0x401u, 0x130u, 0);
        v19 = GetDlgItem(hWnd, 304);
        SetFocus(v19);
        return 1;
      }
    }
    else
    {
      if ( (unsigned __int16)wParam == 1 )
      {
        v20 = (CStorageFolder *)WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 198, WPP_9caa288f52d13f713777aed0becde05d_Traceguids);
        CStorageFolder::_Name(v20, (const struct STORAGEITEM *)WindowLongPtrW[2], Buffer, v10);
        LoadStringW(g_hInst, 0x102u, v33, 260);
        StringCchPrintfW(String, 0x104u, v33, Buffer);
        SetDlgItemTextW(hWnd, 303, String);
        v21 = GetDlgItem(hWnd, 1);
        ShowWindow(v21, 0);
        v22 = GetDlgItem(hWnd, 2);
        ShowWindow(v22, 0);
        v23 = GetDlgItem(hWnd, 301);
        ShowWindow(v23, 5);
        v24 = WindowLongPtrW[1];
        v25 = (const ITEMIDLIST *)WindowLongPtrW[2];
        pszPath[0] = 0;
        if ( (int)SHILCombine(*(const ITEMIDLIST **)(v24 + 64), v25, (LPITEMIDLIST *)pszPath) >= 0 )
        {
          memset_0(&psfi, 0, sizeof(psfi));
          v26 = (ITEMIDLIST *)pszPath[0];
          if ( SHGetFileInfoW(pszPath[0], 0x10u, &psfi, 0x2B8u, 0x118u) && psfi.hIcon )
            ReplaceDlgIcon(hWnd, 302, psfi.hIcon);
          if ( v26 )
            ILFree(v26);
        }
        (*(void (__fastcall **)(_QWORD *))(*WindowLongPtrW + 8LL))(WindowLongPtrW);
        WindowLongPtrW[3] = hWnd;
        if ( !SHCreateThread(CStorageContextMenuCB::s_FormatThreadProc, WindowLongPtrW, 8u, 0) )
          (*(void (__fastcall **)(_QWORD *))(*WindowLongPtrW + 16LL))(WindowLongPtrW);
        return 1;
      }
      if ( (unsigned __int16)wParam != 2 && (unsigned __int16)wParam != 304 )
        return 1;
    }
    EndDialog(hWnd, 2);
    return 1;
  }
  return DefWindowProcW(hWnd, Msg, wParam, (LPARAM)lParam);
}

```

## disassembly

```asm
0x180068080  push    rbp
0x180068082  push    rbx
0x180068083  push    rsi
0x180068084  push    rdi
0x180068085  push    r14
0x180068087  push    r15
0x180068089  lea     rbp, [rsp-848h]
0x180068091  sub     rsp, 948h
0x180068098  mov     rax, cs:__security_cookie
0x18006809f  xor     rax, rsp
0x1800680a2  mov     [rbp+870h+var_40], rax
0x1800680a9  mov     edi, edx
0x1800680ab  mov     r14, r9
0x1800680ae  mov     edx, 10h; nIndex
0x1800680b3  mov     r15, r8
0x1800680b6  mov     rbx, rcx
0x1800680b9  call    cs:__imp_GetWindowLongPtrW
0x1800680bf  mov     rsi, rax
0x1800680c2  cmp     edi, 110h
0x1800680c8  jnz     short loc_1800680DE
0x1800680ca  mov     r8, r14; dwNewLong
0x1800680cd  mov     edx, 10h; nIndex
0x1800680d2  mov     rcx, rbx; hWnd
0x1800680d5  call    cs:__imp_SetWindowLongPtrW
0x1800680db  mov     rsi, r14
0x1800680de  test    rsi, rsi
0x1800680e1  jz      loc_1800684A2
0x1800680e7  sub     edi, 2
0x1800680ea  jz      loc_18006846C
0x1800680f0  sub     edi, 10Eh
0x1800680f6  jz      loc_180068405
0x1800680fc  sub     edi, 1
0x1800680ff  jz      loc_180068242
0x180068105  cmp     edi, 353h
0x18006810b  jz      short loc_180068114
0x18006810d  xor     eax, eax
0x18006810f  jmp     loc_1800684B3
0x180068114  mov     rcx, cs:WPP_GLOBAL_Control
0x18006811b  lea     rax, WPP_GLOBAL_Control
0x180068122  cmp     rcx, rax
0x180068125  jz      short loc_180068142
0x180068127  test    byte ptr [rcx+1Ch], 40h
0x18006812b  jz      short loc_180068142
0x18006812d  mov     rcx, [rcx+10h]
0x180068131  lea     r8, WPP_9caa288f52d13f713777aed0becde05d_Traceguids
0x180068138  mov     edx, 0C5h
0x18006813d  call    WPP_SF_
0x180068142  cmp     r14d, 800704C7h
0x180068149  jnz     short loc_18006815E
0x18006814b  mov     edx, 2; nResult
0x180068150  mov     rcx, rbx; hDlg
0x180068153  call    cs:__imp_EndDialog
0x180068159  jmp     loc_18006849B
0x18006815e  mov     [rsp+970h+pszPath], 0
0x180068167  lea     r9, [rsp+970h+pszPath]
0x18006816c  test    r14d, r14d
0x18006816f  jnz     short loc_180068187
0x180068171  mov     edx, 7F04h
0x180068176  call    IsolationAwareLoadIconMetric
0x18006817b  mov     r9d, 104h
0x180068181  lea     edx, [r9-1]
0x180068185  jmp     short loc_18006819A
0x180068187  mov     edx, 7F01h
0x18006818c  call    IsolationAwareLoadIconMetric
0x180068191  mov     r9d, 104h; cchBufferMax
0x180068197  mov     edx, r9d; uID
0x18006819a  mov     rcx, cs:g_hInst; hInstance
0x1800681a1  lea     r8, [rbp+870h+Buffer]; lpBuffer
0x1800681a8  call    cs:__imp_LoadStringW
0x1800681ae  lea     r8, [rbp+870h+Buffer]; lpString
0x1800681b5  mov     edx, 12Fh; nIDDlgItem
0x1800681ba  mov     rcx, rbx; hDlg
0x1800681bd  call    cs:__imp_SetDlgItemTextW
0x1800681c3  mov     r8, [rsp+970h+pszPath]
0x1800681c8  test    r8, r8
0x1800681cb  jz      short loc_1800681DA
0x1800681cd  mov     edx, 12Eh
0x1800681d2  mov     rcx, rbx
0x1800681d5  call    ReplaceDlgIcon
0x1800681da  mov     edx, 12Dh; nIDDlgItem
0x1800681df  mov     rcx, rbx; hDlg
0x1800681e2  call    cs:__imp_GetDlgItem
0x1800681e8  mov     rcx, rax; hWnd
0x1800681eb  xor     edx, edx; nCmdShow
0x1800681ed  call    cs:__imp_ShowWindow
0x1800681f3  mov     edx, 130h; nIDDlgItem
0x1800681f8  mov     rcx, rbx; hDlg
0x1800681fb  call    cs:__imp_GetDlgItem
0x180068201  mov     rcx, rax; hWnd
0x180068204  mov     edx, 5; nCmdShow
0x180068209  call    cs:__imp_ShowWindow
0x18006820f  xor     r9d, r9d; lParam
0x180068212  mov     edx, 401h; Msg
0x180068217  mov     r8d, 130h; wParam
0x18006821d  mov     rcx, rbx; hWnd
0x180068220  call    cs:__imp_SendMessageW
0x180068226  mov     edx, 130h; nIDDlgItem
0x18006822b  mov     rcx, rbx; hDlg
0x18006822e  call    cs:__imp_GetDlgItem
0x180068234  mov     rcx, rax; hWnd
0x180068237  call    cs:__imp_SetFocus
0x18006823d  jmp     loc_18006849B
0x180068242  movzx   ecx, r15w
0x180068246  sub     ecx, 1
0x180068249  jz      short loc_180068265
0x18006824b  sub     ecx, 1
0x18006824e  jz      loc_18006814B
0x180068254  cmp     ecx, 12Eh
0x18006825a  jnz     loc_18006849B
0x180068260  jmp     loc_18006814B
0x180068265  mov     rcx, cs:WPP_GLOBAL_Control
0x18006826c  lea     rax, WPP_GLOBAL_Control
0x180068273  cmp     rcx, rax
0x180068276  jz      short loc_180068293
0x180068278  test    byte ptr [rcx+1Ch], 40h
0x18006827c  jz      short loc_180068293
0x18006827e  mov     rcx, [rcx+10h]
0x180068282  lea     r8, WPP_9caa288f52d13f713777aed0becde05d_Traceguids
0x180068289  mov     edx, 0C6h
0x18006828e  call    WPP_SF_
0x180068293  mov     rdx, [rsi+10h]; struct STORAGEITEM *
0x180068297  lea     r8, [rbp+870h+Buffer]; unsigned __int16 *
0x18006829e  call    ?_Name@CStorageFolder@@AEAAPEBGPEFBUSTORAGEITEM@@PEAGI@Z; CStorageFolder::_Name(STORAGEITEM const *,ushort *,uint)
0x1800682a3  mov     rcx, cs:g_hInst; hInstance
0x1800682aa  lea     r8, [rbp+870h+var_250]; lpBuffer
0x1800682b1  mov     r9d, 104h; cchBufferMax
0x1800682b7  lea     edx, [r9-2]; uID
0x1800682bb  call    cs:__imp_LoadStringW
0x1800682c1  lea     r9, [rbp+870h+Buffer]
0x1800682c8  mov     edx, 104h; unsigned __int64
0x1800682cd  lea     r8, [rbp+870h+var_250]; unsigned __int16 *
0x1800682d4  lea     rcx, [rbp+870h+String]; unsigned __int16 *
0x1800682db  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800682e0  lea     r8, [rbp+870h+String]; lpString
0x1800682e7  mov     edx, 12Fh; nIDDlgItem
0x1800682ec  mov     rcx, rbx; hDlg
0x1800682ef  call    cs:__imp_SetDlgItemTextW
0x1800682f5  mov     edx, 1; nIDDlgItem
0x1800682fa  mov     rcx, rbx; hDlg
0x1800682fd  call    cs:__imp_GetDlgItem
0x180068303  mov     rcx, rax; hWnd
0x180068306  xor     edx, edx; nCmdShow
0x180068308  call    cs:__imp_ShowWindow
0x18006830e  mov     edx, 2; nIDDlgItem
0x180068313  mov     rcx, rbx; hDlg
0x180068316  call    cs:__imp_GetDlgItem
0x18006831c  mov     rcx, rax; hWnd
0x18006831f  xor     edx, edx; nCmdShow
0x180068321  call    cs:__imp_ShowWindow
0x180068327  mov     edx, 12Dh; nIDDlgItem
0x18006832c  mov     rcx, rbx; hDlg
0x18006832f  call    cs:__imp_GetDlgItem
0x180068335  mov     rcx, rax; hWnd
0x180068338  mov     edx, 5; nCmdShow
0x18006833d  call    cs:__imp_ShowWindow
0x180068343  mov     rcx, [rsi+8]
0x180068347  lea     r8, [rsp+970h+pszPath]
0x18006834c  mov     rdx, [rsi+10h]
0x180068350  mov     [rsp+970h+pszPath], 0
0x180068359  mov     rcx, [rcx+40h]
0x18006835d  call    SHILCombine
0x180068362  test    eax, eax
0x180068364  js      short loc_1800683C7
0x180068366  mov     edi, 2B8h
0x18006836b  lea     rcx, [rsp+970h+psfi]; void *
0x180068370  mov     r8d, edi; Size
0x180068373  xor     edx, edx; Val
0x180068375  call    memset_0
0x18006837a  mov     r9d, edi; cbFileInfo
0x18006837d  mov     [rsp+970h+uFlags], 118h; uFlags
0x180068385  mov     rdi, [rsp+970h+pszPath]
0x18006838a  lea     r8, [rsp+970h+psfi]; psfi
0x18006838f  mov     rcx, rdi; pszPath
0x180068392  mov     edx, 10h; dwFileAttributes
0x180068397  call    cs:__imp_SHGetFileInfoW
0x18006839d  test    rax, rax
0x1800683a0  jz      short loc_1800683B9
0x1800683a2  mov     r8, [rsp+970h+psfi.hIcon]
0x1800683a7  test    r8, r8
0x1800683aa  jz      short loc_1800683B9
0x1800683ac  mov     edx, 12Eh
0x1800683b1  mov     rcx, rbx
0x1800683b4  call    ReplaceDlgIcon
0x1800683b9  test    rdi, rdi
0x1800683bc  jz      short loc_1800683C7
0x1800683be  mov     rcx, rdi; pidl
0x1800683c1  call    cs:__imp_ILFree
0x1800683c7  mov     rax, [rsi]
0x1800683ca  mov     rcx, rsi
0x1800683cd  mov     rax, [rax+8]
0x1800683d1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800683d6  xor     r9d, r9d; pfnCallback
0x1800683d9  mov     [rsi+18h], rbx
0x1800683dd  mov     rdx, rsi; pData
0x1800683e0  lea     rcx, ?s_FormatThreadProc@CStorageContextMenuCB@@CAKPEAX@Z; pfnThreadProc
0x1800683e7  lea     r8d, [r9+8]; flags
0x1800683eb  call    cs:__imp_SHCreateThread
0x1800683f1  test    eax, eax
0x1800683f3  jnz     loc_18006849B
0x1800683f9  mov     rax, [rsi]
0x1800683fc  mov     rax, [rax+10h]
0x180068400  jmp     loc_180068493
0x180068405  mov     rcx, cs:g_hInst; hInstance
0x18006840c  lea     r8, [rbp+870h+String]; lpBuffer
0x180068413  mov     r9d, 104h; cchBufferMax
0x180068419  lea     edx, [r9-3]; uID
0x18006841d  call    cs:__imp_LoadStringW
0x180068423  lea     r8, [rbp+870h+String]; lpString
0x18006842a  mov     edx, 12Fh; nIDDlgItem
0x18006842f  mov     rcx, rbx; hDlg
0x180068432  call    cs:__imp_SetDlgItemTextW
0x180068438  mov     edx, 12Dh; nIDDlgItem
0x18006843d  mov     rcx, rbx; hDlg
0x180068440  call    cs:__imp_GetDlgItem
0x180068446  mov     rcx, rax; hWnd
0x180068449  xor     edx, edx; nCmdShow
0x18006844b  call    cs:__imp_ShowWindow
0x180068451  mov     edx, 130h; nIDDlgItem
0x180068456  mov     rcx, rbx; hDlg
0x180068459  call    cs:__imp_GetDlgItem
0x18006845f  mov     rcx, rax; hWnd
0x180068462  xor     edx, edx; nCmdShow
0x180068464  call    cs:__imp_ShowWindow
0x18006846a  jmp     short loc_18006849B
0x18006846c  xor     r8d, r8d
0x18006846f  mov     edx, 12Eh
0x180068474  mov     rcx, rbx
0x180068477  call    ReplaceDlgIcon
0x18006847c  xor     r8d, r8d; dwNewLong
0x18006847f  mov     rcx, rbx; hWnd
0x180068482  lea     edx, [r8+10h]; nIndex
0x180068486  call    cs:__imp_SetWindowLongPtrW
0x18006848c  mov     rcx, [rsi]
0x18006848f  mov     rax, [rcx+10h]
0x180068493  mov     rcx, rsi
0x180068496  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006849b  mov     eax, 1
0x1800684a0  jmp     short loc_1800684B3
0x1800684a2  mov     r9, r14; lParam
0x1800684a5  mov     r8, r15; wParam
0x1800684a8  mov     edx, edi; Msg
0x1800684aa  mov     rcx, rbx; hWnd
0x1800684ad  call    cs:__imp_DefWindowProcW
0x1800684b3  mov     rcx, [rbp+870h+var_40]
0x1800684ba  xor     rcx, rsp; StackCookie
0x1800684bd  call    __security_check_cookie
0x1800684c2  add     rsp, 948h
0x1800684c9  pop     r15
0x1800684cb  pop     r14
0x1800684cd  pop     rdi
0x1800684ce  pop     rsi
0x1800684cf  pop     rbx
0x1800684d0  pop     rbp
0x1800684d1  retn
```
