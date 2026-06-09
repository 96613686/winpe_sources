# MB_DlgProc(HWND__ *,uint,unsigned __int64,__int64)

- ea: `0x18004b590`
- end: `0x18004b925`
- name: `?MB_DlgProc@@YA_JPEAUHWND__@@I_K_J@Z`
- size: `917`
- prototype: `__int64 __fastcall(HWND, unsigned int, unsigned __int64, __int64)`
- caller_count: `0`
- callee_count: `16`
- tags: `service_task, broker_com_uri`

## callees

- `0x18000bd00`
- `0x18000d210`
- `0x18000e280`
- `0x180010950`
- `0x180016310`
- `0x180029b80`
- `0x18004b590`
- `0x18004baa0`
- `0x18004baf0`
- `0x18004e6a0`
- `0x180054490`
- `0x180061988`
- `0x180088568`
- `0x1800889f8`
- `0x180088c14`
- `0x180088c9c`

## import_xrefs

- `win32u!NtUserNotifyWinEvent` at `0x18004b6d6`
- `win32u!NtUserNotifyWinEvent` at `0x18004b6d6`
- `win32u!NtUserGetWindowContextHelpId` at `0x18009e1b1`
- `win32u!NtUserGetWindowContextHelpId` at `0x18009e1b1`
- `win32u!NtUserSetMsgBox` at `0x18004b660`
- `win32u!NtUserSetMsgBox` at `0x18004b660`
- `win32u!NtUserSetWindowContextHelpId` at `0x18004b806`
- `win32u!NtUserSetWindowContextHelpId` at `0x18004b806`
- `win32u!NtUserSetWindowPos` at `0x18004b774`
- `win32u!NtUserSetWindowPos` at `0x18004b774`
- `win32u!NtUserSetFocus` at `0x18004b702`
- `win32u!NtUserSetFocus` at `0x18004b702`
- `win32u!NtUserSetTimer` at `0x18004b73c`
- `win32u!NtUserSetTimer` at `0x18004b73c`
- `win32u!NtUserKillTimer` at `0x18004b8d6`
- `win32u!NtUserKillTimer` at `0x18004b8d6`
- `win32u!NtUserGetSystemMenu` at `0x18004b874`
- `win32u!NtUserGetSystemMenu` at `0x18004b874`
- `win32u!NtUserDeleteMenu` at `0x18004b88e`
- `win32u!NtUserDeleteMenu` at `0x18004b88e`
- `GDI32!SetBkMode` at `0x18004b7a7`
- `GDI32!SetBkMode` at `0x18004b7a7`
- `GDI32!SetTextColor` at `0x18004b799`
- `GDI32!SetTextColor` at `0x18004b799`

## pseudocode

```c
__int64 __fastcall MB_DlgProc(HWND a1, int a2, HDC a3, LONG_PTR a4)
{
  int v7; // edx
  int v8; // edx
  int v9; // edx
  int v10; // edx
  int v11; // edx
  int v12; // edx
  int v13; // edx
  int v14; // edx
  LONG_PTR WindowLongPtrW; // rax
  LONG_PTR v17; // rbp
  struct tagWND *v18; // rax
  unsigned int v19; // esi
  HWND v20; // rax
  int i; // esi
  __int64 v22; // r8
  COLORREF SysColor; // eax
  INT_PTR v24; // rdx
  int v25; // ecx
  int v26; // eax
  __int64 SystemMenu; // rax
  HWND DlgItem; // rax
  void (*v29)(struct tagHELPINFO *); // rbp
  HWND Window; // rdi
  unsigned int WindowContextHelpId; // eax
  int v32; // edx
  int v33; // r8d

  v7 = a2 - 15;
  if ( !v7 )
  {
    DrawCommandRectangle(a1);
    return 1;
  }
  v8 = v7 - 68;
  if ( !v8 )
  {
LABEL_52:
    v29 = *(void (**)(struct tagHELPINFO *))(GetWindowLongPtrW(a1, -21) + 64);
    if ( v29 )
    {
      Window = 0;
    }
    else
    {
      Window = GetWindow(a1, 4u);
      if ( !Window )
        return 1;
    }
    WindowContextHelpId = NtUserGetWindowContextHelpId(a1);
    SendHelpMessage(Window, v32, v33, a1, WindowContextHelpId, v29);
    return 1;
  }
  v9 = v8 - 47;
  if ( v9 )
  {
    v10 = v9 - 142;
    if ( !v10 )
    {
      SetWindowLongPtrW(a1, -21, a4);
      NtUserSetMsgBox(a1);
      if ( *(_QWORD *)(a4 + 56) )
        NtUserSetWindowContextHelpId(a1);
      v19 = 3;
      if ( (*(_DWORD *)(a4 + 40) & 0x40000) != 0 )
        NtUserSetWindowPos(a1, -1, 0, 0, 0, 0, 3);
      if ( (*(_DWORD *)(a4 + 40) & 0x80u) == 0 )
      {
        v26 = *(_DWORD *)(a4 + 40) & 0xF0;
        if ( v26 != 16 )
        {
          if ( v26 == 32 )
            v19 = 4;
          else
            v19 = (v26 == 48) + 1;
        }
      }
      else
      {
        SendDlgItemMessageW(a1, 20, 0x170u, *(_QWORD *)(a4 + 48), 0);
        v19 = 2;
      }
      if ( (*(_DWORD *)(gpsi + 1892) & 0x8000) != 0 )
        NtUserNotifyWinEvent(2, a1, 4294967286LL, v19);
      if ( !*(_QWORD *)(a4 + 8) && (*(_DWORD *)(a4 + 40) & 0x3000) == 0x2000 )
        StartTaskModalDialog(a1);
      v20 = GetWindow(a1, 5u);
      for ( i = *(_DWORD *)(a4 + 116); i; --i )
        v20 = GetWindow(v20, 2u);
      NtUserSetFocus(v20);
      if ( !*(_DWORD *)(a4 + 120) )
      {
        SystemMenu = NtUserGetSystemMenu(a1, 0);
        if ( SystemMenu )
          NtUserDeleteMenu(SystemMenu, 61536, 0);
      }
      if ( (*(_BYTE *)(a4 + 40) & 0xF) == 0 )
      {
        DlgItem = GetDlgItem(a1, 1);
        if ( DlgItem )
          SetWindowLongPtrW(DlgItem, -12, 2);
      }
      v22 = *(unsigned int *)(a4 + 124);
      if ( (_DWORD)v22 != -1 && !NtUserSetTimer(a1, 0, v22) )
        *(_DWORD *)(a4 + 124) = -1;
      return 0;
    }
    v11 = v10 - 1;
    if ( v11 )
    {
      v12 = v11 - 2;
      if ( v12 )
      {
        v13 = v12 - 35;
        if ( !v13 )
          return *(_QWORD *)(gpsi + 4736);
        v14 = v13 - 2;
        if ( !v14 )
        {
          SysColor = GetSysColor(8);
          SetTextColor(a3, SysColor);
          SetBkMode(a3, 1);
          return (__int64)GetSysColorBrush(5);
        }
        if ( v14 != 457 )
          return 0;
        MB_CopyToClipboard(a1);
        return 1;
      }
      EndTaskModalDialog(a1);
      v24 = 32000;
      goto LABEL_58;
    }
    if ( (unsigned __int16)a3 <= 6u )
    {
      if ( (unsigned __int16)a3 == 6 )
        goto LABEL_57;
      if ( (unsigned __int16)a3 == 1 || (unsigned __int16)a3 == 2 )
      {
        if ( !GetDlgItem(a1, (unsigned __int16)a3) )
          return 0;
        goto LABEL_57;
      }
      v25 = (unsigned __int16)a3 - 3;
      if ( (unsigned __int16)a3 == 3 )
      {
LABEL_57:
        EndTaskModalDialog(a1);
        v24 = (unsigned __int16)a3;
LABEL_58:
        EndDialog(a1, v24);
        return 1;
      }
      goto LABEL_56;
    }
    if ( (unsigned __int16)a3 == 7 )
      goto LABEL_57;
    v25 = (unsigned __int16)a3 - 9;
    if ( (unsigned __int16)a3 != 9 )
    {
LABEL_56:
      if ( (unsigned int)(v25 - 1) > 1 )
        return 0;
      goto LABEL_57;
    }
    goto LABEL_52;
  }
  WindowLongPtrW = GetWindowLongPtrW(a1, -21);
  v17 = WindowLongPtrW;
  if ( WindowLongPtrW && *(_DWORD *)(WindowLongPtrW + 124) != -1 )
  {
    NtUserKillTimer(a1, 0);
    *(_DWORD *)(v17 + 124) = -1;
  }
  v18 = ValidateHwnd(a1);
  if ( !v18 )
    return 0;
  return DefWindowProcWorker(v18, 0x82u, (unsigned __int64)a3, a4, 0);
}

```

## disassembly

```asm
0x18004b590  push    rbx
0x18004b592  push    rbp
0x18004b593  push    rsi
0x18004b594  push    rdi
0x18004b595  push    r14
0x18004b597  sub     rsp, 40h
0x18004b59b  mov     rdi, r9
0x18004b59e  mov     r14, r8
0x18004b5a1  mov     rbx, rcx
0x18004b5a4  sub     edx, 0Fh
0x18004b5a7  jz      loc_18004B91A
0x18004b5ad  sub     edx, 44h ; 'D'
0x18004b5b0  jz      loc_18004B8E4
0x18004b5b6  sub     edx, 2Fh ; '/'
0x18004b5b9  jz      short loc_18004B600
0x18004b5bb  sub     edx, 8Eh
0x18004b5c1  jz      loc_18004B650
0x18004b5c7  sub     edx, 1
0x18004b5ca  jz      loc_18004B7CB
0x18004b5d0  sub     edx, 2
0x18004b5d3  jz      loc_18004B7BC
0x18004b5d9  sub     edx, 23h ; '#'
0x18004b5dc  jz      short loc_18004B640
0x18004b5de  sub     edx, 2
0x18004b5e1  jz      loc_18004B78A
0x18004b5e7  cmp     edx, 1C9h
0x18004b5ed  jz      loc_18004B77F
0x18004b5f3  xor     eax, eax
0x18004b5f5  add     rsp, 40h
0x18004b5f9  pop     r14
0x18004b5fb  pop     rdi
0x18004b5fc  pop     rsi
0x18004b5fd  pop     rbp
0x18004b5fe  pop     rbx
0x18004b5ff  retn
0x18004b600  mov     edx, 0FFFFFFEBh; nIndex
0x18004b605  call    GetWindowLongPtrW
0x18004b60a  mov     rbp, rax
0x18004b60d  test    rax, rax
0x18004b610  jnz     loc_18004B8C5
0x18004b616  mov     rcx, rbx; HWND
0x18004b619  call    ?ValidateHwnd@@YAPEAUtagWND@@PEAUHWND__@@@Z; ValidateHwnd(HWND__ *)
0x18004b61e  test    rax, rax
0x18004b621  jz      short loc_18004B5F3
0x18004b623  mov     r9, rdi; __int64
0x18004b626  mov     dword ptr [rsp+68h+lParam], 0; unsigned int
0x18004b62e  mov     r8, r14; unsigned __int64
0x18004b631  mov     edx, 82h; unsigned int
0x18004b636  mov     rcx, rax; struct tagWND *
0x18004b639  call    ?DefWindowProcWorker@@YA_JPEAUtagWND@@I_K_JK@Z; DefWindowProcWorker(tagWND *,uint,unsigned __int64,__int64,ulong)
0x18004b63e  jmp     short loc_18004B5F5
0x18004b640  mov     rax, cs:gpsi
0x18004b647  mov     rax, [rax+1280h]
0x18004b64e  jmp     short loc_18004B5F5
0x18004b650  mov     r8, rdi; dwNewLong
0x18004b653  mov     edx, 0FFFFFFEBh; nIndex
0x18004b658  call    SetWindowLongPtrW
0x18004b65d  mov     rcx, rbx
0x18004b660  call    cs:__imp_NtUserSetMsgBox
0x18004b666  cmp     qword ptr [rdi+38h], 0
0x18004b66b  jnz     loc_18004B800
0x18004b671  test    dword ptr [rdi+28h], 40000h
0x18004b678  mov     esi, 3
0x18004b67d  jnz     loc_18004B753
0x18004b683  mov     eax, [rdi+28h]
0x18004b686  test    al, al
0x18004b688  jns     loc_18004B811
0x18004b68e  mov     r9, [rdi+30h]; wParam
0x18004b692  mov     edx, 14h; nIDDlgItem
0x18004b697  mov     r8d, 170h; Msg
0x18004b69d  mov     [rsp+68h+lParam], 0; lParam
0x18004b6a6  mov     rcx, rbx; hDlg
0x18004b6a9  call    SendDlgItemMessageW
0x18004b6ae  mov     esi, 2
0x18004b6b3  mov     rax, cs:gpsi
0x18004b6ba  test    dword ptr [rax+764h], 8000h
0x18004b6c4  jz      short loc_18004B6DC
0x18004b6c6  mov     r8d, 0FFFFFFF6h
0x18004b6cc  mov     r9d, esi
0x18004b6cf  mov     rdx, rbx
0x18004b6d2  lea     ecx, [r8+0Ch]
0x18004b6d6  call    cs:__imp_NtUserNotifyWinEvent
0x18004b6dc  cmp     qword ptr [rdi+8], 0
0x18004b6e1  jz      loc_18004B838
0x18004b6e7  mov     edx, 5; uCmd
0x18004b6ec  mov     rcx, rbx; hWnd
0x18004b6ef  call    GetWindow
0x18004b6f4  mov     esi, [rdi+74h]
0x18004b6f7  test    esi, esi
0x18004b6f9  jnz     loc_18004B858
0x18004b6ff  mov     rcx, rax
0x18004b702  call    cs:__imp_NtUserSetFocus
0x18004b708  cmp     dword ptr [rdi+78h], 0
0x18004b70c  jz      loc_18004B86F
0x18004b712  test    byte ptr [rdi+28h], 0Fh
0x18004b716  jz      loc_18004B899
0x18004b71c  mov     r8d, [rdi+7Ch]
0x18004b720  or      esi, 0FFFFFFFFh
0x18004b723  cmp     r8d, esi
0x18004b726  jz      loc_18004B5F3
0x18004b72c  xor     r9d, r9d
0x18004b72f  mov     dword ptr [rsp+68h+lParam], 0
0x18004b737  xor     edx, edx
0x18004b739  mov     rcx, rbx
0x18004b73c  call    cs:__imp_NtUserSetTimer
0x18004b742  test    rax, rax
0x18004b745  jnz     loc_18004B5F3
0x18004b74b  mov     [rdi+7Ch], esi
0x18004b74e  jmp     loc_18004B5F3
0x18004b753  mov     [rsp+68h+var_38], esi
0x18004b757  xor     r9d, r9d
0x18004b75a  mov     dword ptr [rsp+68h+var_40], 0
0x18004b762  xor     r8d, r8d
0x18004b765  or      rdx, 0FFFFFFFFFFFFFFFFh
0x18004b769  mov     dword ptr [rsp+68h+lParam], 0
0x18004b771  mov     rcx, rbx
0x18004b774  call    cs:__imp_NtUserSetWindowPos
0x18004b77a  jmp     loc_18004B683
0x18004b77f  call    ?MB_CopyToClipboard@@YAXPEAUHWND__@@@Z; MB_CopyToClipboard(HWND__ *)
0x18004b784  nop
0x18004b785  jmp     loc_18009E1CB
0x18004b78a  mov     ecx, 8; nIndex
0x18004b78f  call    GetSysColor
0x18004b794  mov     edx, eax; color
0x18004b796  mov     rcx, r14; hdc
0x18004b799  call    cs:__imp_SetTextColor
0x18004b79f  mov     edx, 1; mode
0x18004b7a4  mov     rcx, r14; hdc
0x18004b7a7  call    cs:__imp_SetBkMode
0x18004b7ad  mov     ecx, 5; nIndex
0x18004b7b2  call    GetSysColorBrush
0x18004b7b7  jmp     loc_18004B5F5
0x18004b7bc  call    ?EndTaskModalDialog@@YAXPEAUHWND__@@@Z; EndTaskModalDialog(HWND__ *)
0x18004b7c1  mov     edx, 7D00h
0x18004b7c6  jmp     loc_18009E171
0x18004b7cb  movzx   edi, r14w
0x18004b7cf  cmp     edi, 6
0x18004b7d2  ja      loc_18009E190
0x18004b7d8  jz      loc_18009E166
0x18004b7de  mov     ecx, edi
0x18004b7e0  sub     ecx, 1
0x18004b7e3  jz      loc_18009E17B
0x18004b7e9  sub     ecx, 1
0x18004b7ec  jz      loc_18009E17B
0x18004b7f2  sub     ecx, 1
0x18004b7f5  jnz     loc_18009E158
0x18004b7fb  jmp     loc_18009E166
0x18004b800  mov     edx, [rdi+38h]
0x18004b803  mov     rcx, rbx
0x18004b806  call    cs:__imp_NtUserSetWindowContextHelpId
0x18004b80c  jmp     loc_18004B671
0x18004b811  and     eax, 0F0h
0x18004b816  cmp     eax, 10h
0x18004b819  jz      loc_18004B6B3
0x18004b81f  cmp     eax, 20h ; ' '
0x18004b822  jz      loc_18009E1A2
0x18004b828  xor     esi, esi
0x18004b82a  cmp     eax, 30h ; '0'
0x18004b82d  setz    sil
0x18004b831  inc     esi
0x18004b833  jmp     loc_18004B6B3
0x18004b838  mov     eax, [rdi+28h]
0x18004b83b  and     eax, 3000h
0x18004b840  cmp     eax, 2000h
0x18004b845  jnz     loc_18004B6E7
0x18004b84b  mov     rcx, rbx; hWnd
0x18004b84e  call    ?StartTaskModalDialog@@YAXPEAUHWND__@@@Z; StartTaskModalDialog(HWND__ *)
0x18004b853  jmp     loc_18004B6E7
0x18004b858  mov     edx, 2; uCmd
0x18004b85d  mov     rcx, rax; hWnd
0x18004b860  call    GetWindow
0x18004b865  sub     esi, 1
0x18004b868  jnz     short loc_18004B858
0x18004b86a  jmp     loc_18004B6FF
0x18004b86f  xor     edx, edx
0x18004b871  mov     rcx, rbx
0x18004b874  call    cs:__imp_NtUserGetSystemMenu
0x18004b87a  test    rax, rax
0x18004b87d  jz      loc_18004B712
0x18004b883  xor     r8d, r8d
0x18004b886  mov     edx, 0F060h
0x18004b88b  mov     rcx, rax
0x18004b88e  call    cs:__imp_NtUserDeleteMenu
0x18004b894  jmp     loc_18004B712
0x18004b899  mov     edx, 1; nIDDlgItem
0x18004b89e  mov     rcx, rbx; hDlg
0x18004b8a1  call    GetDlgItem
0x18004b8a6  test    rax, rax
0x18004b8a9  jz      loc_18004B71C
0x18004b8af  mov     edx, 0FFFFFFF4h; nIndex
0x18004b8b4  mov     rcx, rax; hWnd
0x18004b8b7  lea     r8d, [rdx+0Eh]; dwNewLong
0x18004b8bb  call    SetWindowLongPtrW
0x18004b8c0  jmp     loc_18004B71C
0x18004b8c5  or      esi, 0FFFFFFFFh
0x18004b8c8  cmp     [rax+7Ch], esi
0x18004b8cb  jz      loc_18004B616
0x18004b8d1  xor     edx, edx
0x18004b8d3  mov     rcx, rbx
0x18004b8d6  call    cs:__imp_NtUserKillTimer
0x18004b8dc  mov     [rbp+7Ch], esi
0x18004b8df  jmp     loc_18004B616
0x18004b8e4  mov     edx, 0FFFFFFEBh; nIndex
0x18004b8e9  mov     rcx, rbx; hWnd
0x18004b8ec  call    GetWindowLongPtrW
0x18004b8f1  mov     rbp, [rax+40h]
0x18004b8f5  test    rbp, rbp
0x18004b8f8  jnz     loc_18009E1AC
0x18004b8fe  lea     edx, [rbp+4]; uCmd
0x18004b901  mov     rcx, rbx; hWnd
0x18004b904  call    GetWindow
0x18004b909  mov     rdi, rax
0x18004b90c  test    rax, rax
0x18004b90f  jnz     loc_18009E1AE
0x18004b915  jmp     loc_18009E1CB
0x18004b91a  call    ?DrawCommandRectangle@@YAXPEAUHWND__@@@Z; DrawCommandRectangle(HWND__ *)
0x18004b91f  nop
0x18004b920  jmp     loc_18009E1CB
0x18009e158  sub     ecx, 1
0x18009e15b  jz      short loc_18009E166
0x18009e15d  cmp     ecx, 1
0x18009e160  jnz     loc_18004B5F3
0x18009e166  mov     rcx, rbx; HWND
0x18009e169  call    ?EndTaskModalDialog@@YAXPEAUHWND__@@@Z; EndTaskModalDialog(HWND__ *)
0x18009e16e  mov     rdx, rdi; nResult
0x18009e171  mov     rcx, rbx; hDlg
0x18009e174  call    EndDialog
0x18009e179  jmp     short loc_18009E1CB
0x18009e17b  mov     edx, edi; nIDDlgItem
0x18009e17d  mov     rcx, rbx; hDlg
0x18009e180  call    GetDlgItem
0x18009e185  test    rax, rax
0x18009e188  jz      loc_18004B5F3
0x18009e18e  jmp     short loc_18009E166
0x18009e190  mov     ecx, edi
0x18009e192  sub     ecx, 7
0x18009e195  jz      short loc_18009E166
0x18009e197  sub     ecx, 2
0x18009e19a  jz      loc_18004B8E4
0x18009e1a0  jmp     short loc_18009E158
0x18009e1a2  mov     esi, 4
0x18009e1a7  jmp     loc_18004B6B3
0x18009e1ac  xor     edi, edi
0x18009e1ae  mov     rcx, rbx
0x18009e1b1  call    cs:__imp_NtUserGetWindowContextHelpId
0x18009e1b7  mov     r9, rbx; void *
0x18009e1ba  mov     [rsp+68h+var_40], rbp; void (*)(struct tagHELPINFO *)
0x18009e1bf  mov     rcx, rdi; hWnd
0x18009e1c2  mov     dword ptr [rsp+68h+lParam], eax; unsigned int
0x18009e1c6  call    ?SendHelpMessage@@YAXPEAUHWND__@@HHPEAXKP6AXPEAUtagHELPINFO@@@Z@Z; SendHelpMessage(HWND__ *,int,int,void *,ulong,void (*)(tagHELPINFO *))
0x18009e1cb  mov     eax, 1
0x18009e1d0  jmp     loc_18004B5F5
```
