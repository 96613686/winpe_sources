# DefDlgProcWorker

- ea: `0x180008ab0`
- end: `0x18000950a`
- name: `DefDlgProcWorker`
- size: `2650`
- prototype: `__int64 __usercall@<rax>(struct tagWND *@<rcx>, int)`
- caller_count: `2`
- callee_count: `32`
- tags: `authz_impersonation`

## callers

- `0x180008a50`
- `0x180052ea0`

## callees

- `0x18000772c`
- `0x180008ab0`
- `0x180009510`
- `0x180009ba8`
- `0x18000a9f0`
- `0x18000cf20`
- `0x18000d210`
- `0x180010950`
- `0x1800130e0`
- `0x180013900`
- `0x180016320`
- `0x180020990`
- `0x180029150`
- `0x180029cf4`
- `0x180029ec8`
- `0x180029f40`
- `0x18002a698`
- `0x18002a720`
- `0x18002a8ec`
- `0x18002aa38`
- `0x18002aa8c`
- `0x18002aac8`
- `0x18002ac78`
- `0x180034c90`
- `0x180038560`
- `0x18003bb00`
- `0x18004b360`
- `0x18004baf0`
- `0x180052f2c`
- `0x18005f1c0`
- `0x180069284`
- `0x18006eda8`

## import_xrefs

- `win32u!NtUserMessageBeep` at `0x180009392`
- `win32u!NtUserMessageBeep` at `0x180009392`
- `win32u!NtUserSetThreadState` at `0x180008dc7`
- `win32u!NtUserSetThreadState` at `0x180009192`
- `win32u!NtUserSetThreadState` at `0x180008dc7`
- `win32u!NtUserSetThreadState` at `0x180009192`
- `win32u!NtUserQueryWindow` at `0x180008eee`
- `win32u!NtUserQueryWindow` at `0x1800090fb`
- `win32u!NtUserQueryWindow` at `0x180008eee`
- `win32u!NtUserQueryWindow` at `0x1800090fb`
- `win32u!NtUserFillWindow` at `0x180008d78`
- `win32u!NtUserFillWindow` at `0x180008d78`
- `win32u!NtUserSetDialogPointer` at `0x180008e3b`
- `win32u!NtUserSetDialogPointer` at `0x180008e3b`
- `win32u!NtUserSetWindowFNID` at `0x180008e92`
- `win32u!NtUserSetWindowFNID` at `0x180008e92`
- `win32u!NtUserShowCursor` at `0x180008f28`
- `win32u!NtUserShowCursor` at `0x180008f6b`
- `win32u!NtUserShowCursor` at `0x180009135`
- `win32u!NtUserShowCursor` at `0x180009178`
- `win32u!NtUserShowCursor` at `0x180008f28`
- `win32u!NtUserShowCursor` at `0x180008f6b`
- `win32u!NtUserShowCursor` at `0x180009135`
- `win32u!NtUserShowCursor` at `0x180009178`
- `win32u!NtUserSetWindowPos` at `0x18000936e`
- `win32u!NtUserSetWindowPos` at `0x18000936e`
- `win32u!NtUserSetCursorPos` at `0x180008f60`
- `win32u!NtUserSetCursorPos` at `0x18000916d`
- `win32u!NtUserSetCursorPos` at `0x180008f60`
- `win32u!NtUserSetCursorPos` at `0x18000916d`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800980ab`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800980ab`
- `GDI32!DeleteObject` at `0x180008de1`
- `GDI32!DeleteObject` at `0x180008e0a`
- `GDI32!DeleteObject` at `0x180008de1`
- `GDI32!DeleteObject` at `0x180008e0a`

## pseudocode

```c
__int64 __fastcall DefDlgProcWorker(
        struct tagWND *a1,
        unsigned int a2,
        unsigned __int64 a3,
        struct tagRECT *a4,
        unsigned int a5)
{
  HWND v5; // rsi
  __int64 v10; // rdx
  struct tagWND *v12; // rsi
  HWND Focus; // rax
  struct tagWND *v14; // rax
  struct tagWND *v15; // rdi
  struct tagWND *NextDlgTabItem; // rax
  struct tagWND *v17; // rbx
  HWND v18; // rcx
  HWND v19; // r8
  HWND v20; // rdx
  void *v21; // rcx
  void *v22; // rcx
  struct tagWND *ParentDialog; // rdi
  unsigned __int8 v24; // r8
  HWND v25; // rsi
  struct tagWND *v26; // rcx
  struct tagWND *DlgItem; // rax
  WPARAM v28; // r8
  LPARAM v29; // r9
  struct tagWND *v30; // rax
  struct tagWND *v31; // rsi
  struct tagWND *v32; // rax
  struct tagWND *v33; // rdi
  struct tagWND *v34; // rax
  struct tagWND *v35; // rcx
  struct tagWND *v36; // rax
  HWND v37; // rcx
  unsigned int WindowDPI; // eax
  struct tagWND *ChildControl; // rax
  struct tagWND *v40; // rdi
  struct tagWND *Control; // rax
  struct tagWND *v42; // rax
  __int64 v43; // rax
  char *v44; // rax
  struct tagMONITOR *v45; // rax
  struct tagWND *v46; // rax
  struct tagWND *v47; // rdi
  __int64 v48; // rdx
  struct tagWND *v49; // r8
  __int64 v50; // rax
  HWND v51; // rax
  struct tagWND *v52; // rcx
  __int64 v53; // rax
  struct tagWND *v54; // rax
  HWND v55; // rcx
  HWND v56; // rdx
  HWND v57; // rdx
  struct tagRECT Rect; // [rsp+40h] [rbp-18h] BYREF

  v5 = *(HWND *)a1;
  if ( *((_WORD *)a1 + 21) )
  {
    if ( *((_WORD *)a1 + 21) != 676 )
      return 0;
  }
  else
  {
    if ( *((_DWORD *)a1 + 50) < (int)*(unsigned __int16 *)(gpsi + 348) )
      return 0;
    NtUserSetWindowFNID(v5, 676);
  }
  if ( !(unsigned int)ValidateDialogPwnd(a1) )
    return 0;
  if ( **((_QWORD **)a1 + 37) )
    _SetWindowLongPtr(v5, 0, 0, 0);
  if ( a2 == 112 )
    goto LABEL_55;
  if ( ((a2 - 736) & 0xFFFFFFFD) == 0 )
  {
    WindowDPI = GetWindowDPI(v5);
    OnDpiChanged(a1, WindowDPI, a4);
  }
  v10 = **(_QWORD **)(*((_QWORD *)a1 + 37) + 8LL);
  if ( v10
    && ((unsigned int)UserCallDlgProcCheckWow(*((_QWORD *)a1 + 28), v10, v5, a2, a3, a4)
     || !HMValidateHandleNoSecure(v5)
     || (*((_WORD *)a1 + 21) & 0xC000) != 0) )
  {
    return 0;
  }
  if ( a2 < 0x132 && a2 != 25 && (a2 == 46 || a2 == 47 || a2 == 55 || a2 == 57 || a2 == 272) )
    return 0;
  if ( a2 <= 0xA1 )
  {
    if ( a2 == 161 )
      goto LABEL_146;
    if ( a2 <= 0x2E )
    {
      if ( a2 == 6 )
      {
        ParentDialog = GetParentDialog(a1);
        if ( ParentDialog != a1 )
          NtUserSetThreadState(a3 != 0 ? 0x4000 : 0, 0x4000);
        if ( a3 )
          xxxRestoreDlgFocus(ParentDialog);
        else
          xxxSaveDlgFocus(ParentDialog);
        goto LABEL_26;
      }
      if ( a2 != 7 )
      {
        switch ( a2 )
        {
          case 0x10u:
            DlgItem = _GetDlgItem(a1, 2);
            if ( DlgItem )
            {
              if ( (*((_BYTE *)DlgItem + 31) & 8) != 0 )
              {
                NtUserMessageBeep(0);
                goto LABEL_26;
              }
              v29 = *(_QWORD *)DlgItem;
            }
            else
            {
              v29 = 0;
            }
            PostMessageW(v5, 0x111u, v28, v29);
            goto LABEL_26;
          case 0x14u:
            NtUserFillWindow(v5, v5, a3, 4);
            return 1;
          case 0x18u:
            if ( GetParentDialog(a1) != a1 )
              return DefWindowProcWorker(a1, a2, a3, (__int64)a4, a5);
            if ( a3 )
            {
              if ( !(_WORD)a4 || (*(_BYTE *)(*(_QWORD *)(*((_QWORD *)a1 + 37) + 8LL) + 24LL) & 1) == 0 )
              {
                if ( (v24 & *(_BYTE *)(gpsi + 7004)) != 0 )
                {
                  if ( NtUserQueryWindow(v5, 7) )
                  {
                    v25 = GetDlgItem(v5, *(_DWORD *)(*(_QWORD *)(*((_QWORD *)a1 + 37) + 8LL) + 32LL));
                    if ( v25 )
                    {
                      Rect = 0;
                      NtUserShowCursor(0);
                      GetWindowRect(v25, &Rect);
                      NtUserSetCursorPos(
                        (unsigned int)(Rect.left + (Rect.right - Rect.left) / 2),
                        (unsigned int)(Rect.top + (Rect.bottom - Rect.top) / 2));
                      NtUserShowCursor(1);
                    }
                  }
                }
                return DefWindowProcWorker(a1, a2, a3, (__int64)a4, a5);
              }
              goto LABEL_26;
            }
LABEL_136:
            xxxSaveDlgFocus(a1);
            return DefWindowProcWorker(a1, a2, a3, (__int64)a4, a5);
        }
        if ( a2 != 40 )
          return DefWindowProcWorker(a1, a2, a3, (__int64)a4, a5);
        v12 = GetParentDialog(a1);
        Focus = GetFocus();
        v14 = ValidateHwndNoRip(Focus);
        v15 = v14;
        if ( (_WORD)a4 )
        {
          if ( !v14 )
            v15 = v12;
          NextDlgTabItem = ValidateHwnd((HWND)a3);
LABEL_40:
          v17 = NextDlgTabItem;
          if ( NextDlgTabItem )
            goto LABEL_41;
          return 1;
        }
        if ( v14 )
        {
          if ( !(unsigned int)IsChild(v12, v14) )
            return 1;
          NextDlgTabItem = _GetNextDlgTabItem(v26, v15, a3 != 0);
          goto LABEL_40;
        }
        if ( v12 )
        {
          ChildControl = _GetChildControl(v12, 0);
          v40 = ChildControl;
          if ( ChildControl && !(unsigned int)IsDescendant(v12, ChildControl) )
          {
            v17 = 0;
            goto LABEL_105;
          }
        }
        else
        {
          v40 = 0;
        }
        Control = _NextControl(v12, v40, 3u);
        v17 = Control;
        if ( Control )
        {
          while ( Control != v40 && v17 != v12 )
          {
            v42 = v17;
            if ( v40 )
              v42 = v40;
            v40 = v42;
            if ( (*((_DWORD *)v17 + 7) & 0x18010000) == 0x10010000 )
              break;
            Control = _NextControl(v12, v17, 3u);
            v17 = Control;
          }
        }
LABEL_105:
        v15 = v12;
        if ( !v17 )
        {
          v18 = 0;
          goto LABEL_42;
        }
LABEL_41:
        v18 = *(HWND *)v17;
LABEL_42:
        DlgSetFocus(v18);
        v19 = 0;
        if ( v17 )
          v19 = *(HWND *)v17;
        v20 = 0;
        if ( v15 )
          v20 = *(HWND *)v15;
        xxxCheckDefPushButton(v12, v20, v19);
        return 1;
      }
      v30 = GetParentDialog(a1);
      v31 = v30;
      if ( (*(_BYTE *)(*(_QWORD *)(*((_QWORD *)v30 + 37) + 8LL) + 24LL) & 1) != 0
        || (unsigned int)xxxRestoreDlgFocus(v30) )
      {
        goto LABEL_26;
      }
      v32 = _GetChildControl(v31, 0);
      v33 = v32;
      if ( v32 && !(unsigned int)IsDescendant(v31, v32) )
        goto LABEL_113;
      v34 = _NextControl(v31, v33, 3u);
      v35 = v34;
      if ( v34 )
      {
        if ( v34 == v33 )
          goto LABEL_91;
        do
        {
          if ( v35 == v31 )
            break;
          v36 = v35;
          if ( v33 )
            v36 = v33;
          v33 = v36;
          if ( (*((_DWORD *)v35 + 7) & 0x18010000) == 0x10010000 )
            break;
          v35 = _NextControl(v31, v35, 3u);
        }
        while ( v35 != v33 );
      }
      if ( !v35 )
      {
LABEL_113:
        v37 = 0;
        goto LABEL_92;
      }
LABEL_91:
      v37 = *(HWND *)v35;
LABEL_92:
      DlgSetFocus(v37);
      goto LABEL_26;
    }
    switch ( a2 )
    {
      case '1':
        return *(_QWORD *)(*(_QWORD *)(*((_QWORD *)a1 + 37) + 8LL) + 48LL);
      case 'P':
        if ( (*(_BYTE *)gpsi & 4) == 0
          && **(__int64 (__fastcall ***)(HWND, unsigned int, unsigned __int64, __int64))(*((_QWORD *)a1 + 37) + 8LL) != MB_DlgProc )
        {
          return DefWindowProcWorker(a1, a2, a3, (__int64)a4, a5);
        }
LABEL_26:
        if ( (*((_BYTE *)a1 + 18) & 1) != 0 )
          return **((_QWORD **)a1 + 37);
        return 0;
      case 'U':
        if ( a4 != (struct tagRECT *)3 )
          return 0;
        return 2LL - ((*(_DWORD *)(*(_QWORD *)(*((_QWORD *)a1 + 37) + 8LL) + 24LL) & 4) != 0);
    }
    if ( a2 != 130 )
      return DefWindowProcWorker(a1, a2, a3, (__int64)a4, a5);
LABEL_55:
    NtUserSetThreadState(0, 0x4000);
    v21 = *(void **)(*(_QWORD *)(*((_QWORD *)a1 + 37) + 8LL) + 48LL);
    if ( v21 )
      DeleteObject(v21);
    *(_QWORD *)(*(_QWORD *)(*((_QWORD *)a1 + 37) + 8LL) + 48LL) = 0;
    v22 = *(void **)(*(_QWORD *)(*((_QWORD *)a1 + 37) + 8LL) + 64LL);
    if ( v22 )
      DeleteObject(v22);
    *(_QWORD *)(*(_QWORD *)(*((_QWORD *)a1 + 37) + 8LL) + 64LL) = 0;
    FreeLookasideEntry((struct _LOOKASIDE *)&DialogLookaside, *(void **)(*((_QWORD *)a1 + 37) + 8LL));
    NtUserSetDialogPointer(v5, 0);
    goto LABEL_26;
  }
  if ( a2 <= 0x137 )
  {
    if ( a2 != 274 || GetParentDialog(a1) != a1 || (a3 & 0xFFF0) != 0xF020 )
      return DefWindowProcWorker(a1, a2, a3, (__int64)a4, a5);
    goto LABEL_136;
  }
  if ( a2 == 312 )
    return DefWindowProcWorker(a1, a2, a3, (__int64)a4, a5);
  if ( a2 == 513 || a2 == 529 )
  {
LABEL_146:
    v51 = GetFocus();
    if ( v51 )
    {
      v52 = ValidateHwndNoRip(v51);
      if ( (*((_WORD *)v52 + 21) & 0x2FFF) == 0x2A2
        || ((v53 = *((_QWORD *)v52 + 6)) != 0
          ? (v52 = (struct tagWND *)((char *)v52 + v53 - *((_QWORD *)v52 + 1)))
          : (v52 = 0),
            (*((_WORD *)v52 + 21) & 0x2FFF) == 0x2A2) )
      {
        SendMessageW(*(HWND *)v52, 0x14Fu, 0, 0);
      }
    }
    return DefWindowProcWorker(a1, a2, a3, (__int64)a4, a5);
  }
  if ( a2 != 740 )
  {
    if ( a2 != 1024 )
    {
      if ( a2 != 1025 )
      {
        if ( a2 != 1026 || (*((_BYTE *)a1 + 26) & 1) == 0 )
          return DefWindowProcWorker(a1, a2, a3, (__int64)a4, a5);
        if ( (*((_WORD *)a1 + 21) & 0x2FFF) != 0x29D )
        {
          v43 = *((_QWORD *)a1 + 6);
          v44 = v43 ? (char *)a1 + v43 - *((_QWORD *)a1 + 1) : 0LL;
          if ( (*((_WORD *)v44 + 21) & 0x2FFF) != 0x29D )
            return DefWindowProcWorker(a1, a2, a3, (__int64)a4, a5);
        }
        Rect = *(struct tagRECT *)((char *)a1 + 88);
        v45 = (struct tagMONITOR *)MonitorFromRect(&Rect, 1, 0);
        RepositionRect(v45, &Rect, *((_DWORD *)a1 + 7), *((_DWORD *)a1 + 6));
        NtUserSetWindowPos(
          v5,
          0,
          (unsigned int)Rect.left,
          (unsigned int)Rect.top,
          Rect.right - Rect.left,
          Rect.bottom - Rect.top,
          21);
        goto LABEL_26;
      }
      v46 = GetParentDialog(a1);
      v47 = v46;
      v48 = *(_QWORD *)(*((_QWORD *)v46 + 37) + 8LL);
      if ( (*(_BYTE *)(v48 + 24) & 1) == 0 )
      {
        v49 = 0;
        if ( *(_QWORD *)(v48 + 32) )
          v49 = _FindDlgItem(v46, *(_DWORD *)(v48 + 32));
        if ( a3 && (v54 = _GetDlgItem(a1, a3)) != 0 )
          v55 = *(HWND *)v54;
        else
          v55 = 0;
        v56 = 0;
        if ( v49 )
          v56 = *(HWND *)v49;
        xxxCheckDefPushButton(v47, v56, v55);
        *(_QWORD *)(*(_QWORD *)(*((_QWORD *)v47 + 37) + 8LL) + 32LL) = (unsigned int)a3;
        v57 = 0;
        if ( v47 )
          v57 = *(HWND *)v47;
        NotifyWinEvent(0x8011u, v57, -4, 0);
      }
      return 1;
    }
    v50 = *(_QWORD *)(*((_QWORD *)GetParentDialog(a1) + 37) + 8LL);
    if ( (*(_BYTE *)(v50 + 24) & 1) == 0 && *(_QWORD *)(v50 + 32) )
      return *(unsigned __int16 *)(v50 + 32) | 0x534B0000LL;
    return 0;
  }
  if ( (unsigned int)(a3 - 96) > 0x180 )
  {
    SetLastError(0x57u);
    return 0;
  }
  if ( (*(_BYTE *)(*(_QWORD *)(*((_QWORD *)a1 + 37) + 8LL) + 56LL) & 2) != 0 )
    return 0;
  return GetDialogDpiScaledSize(a1, a3, (struct tagSIZE *)a4);
}

```

## disassembly

```asm
0x180008ab0  push    rbp
0x180008ab2  push    rbx
0x180008ab3  push    rsi
0x180008ab4  push    rdi
0x180008ab5  push    r12
0x180008ab7  push    r13
0x180008ab9  push    r14
0x180008abb  push    r15
0x180008abd  mov     rbp, rsp
0x180008ac0  sub     rsp, 58h
0x180008ac4  mov     rsi, [rcx]
0x180008ac7  xor     r13d, r13d
0x180008aca  mov     r15, r9
0x180008acd  mov     r14, r8
0x180008ad0  mov     edi, edx
0x180008ad2  mov     rbx, rcx
0x180008ad5  cmp     [rcx+2Ah], r13w
0x180008ada  jz      loc_180008E70
0x180008ae0  mov     edx, 2A4h
0x180008ae5  cmp     [rcx+2Ah], dx
0x180008ae9  jnz     loc_180008D54
0x180008aef  mov     rcx, rbx; struct tagWND *
0x180008af2  call    ?ValidateDialogPwnd@@YAHPEAUtagWND@@@Z; ValidateDialogPwnd(tagWND *)
0x180008af7  test    eax, eax
0x180008af9  jz      loc_180008D54
0x180008aff  mov     rax, [rbx+128h]
0x180008b06  cmp     [rax], r13
0x180008b09  jz      short loc_180008B1B
0x180008b0b  xor     r9d, r9d; int
0x180008b0e  xor     r8d, r8d; __int64
0x180008b11  xor     edx, edx; int
0x180008b13  mov     rcx, rsi; HWND
0x180008b16  call    ?_SetWindowLongPtr@@YA_JPEAUHWND__@@H_JH@Z; _SetWindowLongPtr(HWND__ *,int,__int64,int)
0x180008b1b  mov     [rbp+arg_0], r13
0x180008b1f  mov     r12, r13
0x180008b22  cmp     edi, 70h ; 'p'
0x180008b25  jz      loc_180008DC0
0x180008b2b  lea     eax, [rdi-2E0h]
0x180008b31  test    eax, 0FFFFFFFDh
0x180008b36  jz      loc_180009090
0x180008b3c  mov     rax, [rbx+128h]
0x180008b43  mov     rcx, [rax+8]
0x180008b47  mov     rdx, [rcx]
0x180008b4a  test    rdx, rdx
0x180008b4d  jz      short loc_180008BA0
0x180008b4f  mov     rcx, [rbx+0E0h]
0x180008b56  lea     rax, [rbp+arg_0]
0x180008b5a  mov     [rsp+58h+var_20], rax
0x180008b5f  mov     r9d, edi
0x180008b62  mov     [rsp+58h+var_30], r15
0x180008b67  mov     r8, rsi
0x180008b6a  mov     qword ptr [rsp+58h+var_38], r14
0x180008b6f  call    ?UserCallDlgProcCheckWow@@YAHPEAU_ACTIVATION_CONTEXT@@P6A_JPEAUHWND__@@I_K_J@Z1W4_WM_VALUE@@23PEAXPEA_J@Z; UserCallDlgProcCheckWow(_ACTIVATION_CONTEXT *,__int64 (*)(HWND__ *,uint,unsigned __int64,__int64),HWND__ *,_WM_VALUE,unsigned __int64,__int64,void *,__int64 *)
0x180008b74  test    eax, eax
0x180008b76  jnz     loc_180008C45
0x180008b7c  mov     rcx, rsi
0x180008b7f  call    HMValidateHandleNoSecure
0x180008b84  test    rax, rax
0x180008b87  jz      loc_180008C45
0x180008b8d  mov     eax, 0C000h
0x180008b92  test    [rbx+2Ah], ax
0x180008b96  jnz     loc_180008C45
0x180008b9c  mov     r12, [rbp+arg_0]
0x180008ba0  mov     eax, 132h
0x180008ba5  mov     r8d, 2
0x180008bab  cmp     edi, eax
0x180008bad  jbe     loc_180008C4E
0x180008bb3  mov     eax, edi
0x180008bb5  sub     eax, 133h
0x180008bba  jz      loc_180008D5B
0x180008bc0  sub     eax, 1
0x180008bc3  jz      loc_180008D5B
0x180008bc9  sub     eax, 1
0x180008bcc  jz      loc_180008D5B
0x180008bd2  sub     eax, 1
0x180008bd5  jz      loc_180008D5B
0x180008bdb  sub     eax, 1
0x180008bde  jz      loc_180008D5B
0x180008be4  cmp     eax, 1
0x180008be7  jz      loc_180008D5B
0x180008bed  test    r12, r12
0x180008bf0  jnz     loc_180008C83
0x180008bf6  mov     eax, 0A1h
0x180008bfb  cmp     edi, eax
0x180008bfd  jbe     loc_180008C9E
0x180008c03  mov     eax, 137h
0x180008c08  cmp     edi, eax
0x180008c0a  jbe     loc_1800093C7
0x180008c10  mov     eax, edi
0x180008c12  sub     eax, 138h
0x180008c17  jnz     loc_1800092A5
0x180008c1d  mov     eax, [rbp+arg_20]
0x180008c20  mov     r9, r15; __int64
0x180008c23  mov     r8, r14; unsigned __int64
0x180008c26  mov     [rsp+58h+var_38], eax; unsigned int
0x180008c2a  mov     edx, edi; unsigned int
0x180008c2c  mov     rcx, rbx; struct tagWND *
0x180008c2f  call    ?DefWindowProcWorker@@YA_JPEAUtagWND@@I_K_JK@Z; DefWindowProcWorker(tagWND *,uint,unsigned __int64,__int64,ulong)
0x180008c34  add     rsp, 58h
0x180008c38  pop     r15
0x180008c3a  pop     r14
0x180008c3c  pop     r13
0x180008c3e  pop     r12
0x180008c40  pop     rdi
0x180008c41  pop     rsi
0x180008c42  pop     rbx
0x180008c43  pop     rbp
0x180008c44  retn
0x180008c45  mov     r12, [rbp+arg_0]
0x180008c49  mov     rax, r12
0x180008c4c  jmp     short loc_180008C34
0x180008c4e  jz      loc_180008D5B
0x180008c54  mov     eax, edi
0x180008c56  sub     eax, 19h
0x180008c59  jz      loc_180008D5B
0x180008c5f  sub     eax, 15h
0x180008c62  jz      short loc_180008C7E
0x180008c64  sub     eax, 1
0x180008c67  jz      short loc_180008C7E
0x180008c69  sub     eax, 8
0x180008c6c  jz      short loc_180008C7E
0x180008c6e  sub     eax, r8d
0x180008c71  jz      short loc_180008C7E
0x180008c73  cmp     eax, 0D7h
0x180008c78  jnz     loc_180008BED
0x180008c7e  mov     eax, r12d
0x180008c81  jmp     short loc_180008C34
0x180008c83  cmp     edi, 18h
0x180008c86  jz      loc_1800090AA
0x180008c8c  test    byte ptr [rbx+12h], 1
0x180008c90  jz      short loc_180008C49
0x180008c92  mov     rax, [rbx+128h]
0x180008c99  mov     rax, [rax]
0x180008c9c  jmp     short loc_180008C34
0x180008c9e  jz      loc_1800094C2
0x180008ca4  cmp     edi, 2Eh ; '.'
0x180008ca7  ja      loc_180008D88
0x180008cad  jz      short loc_180008C49
0x180008caf  mov     eax, edi
0x180008cb1  sub     eax, 6
0x180008cb4  jz      loc_180008E46
0x180008cba  sub     eax, 1
0x180008cbd  jz      loc_180008FD2
0x180008cc3  sub     eax, 9
0x180008cc6  jz      loc_180008FA9
0x180008ccc  sub     eax, 4
0x180008ccf  jz      loc_180008D69
0x180008cd5  sub     eax, 4
0x180008cd8  jz      loc_180008E9D
0x180008cde  sub     eax, 1
0x180008ce1  jz      loc_180008C1D
0x180008ce7  cmp     eax, 0Fh
0x180008cea  jnz     loc_180008C1D
0x180008cf0  mov     rcx, rbx; struct tagWND *
0x180008cf3  call    ?GetParentDialog@@YAPEAUtagWND@@PEAU1@@Z; GetParentDialog(tagWND *)
0x180008cf8  mov     rsi, rax
0x180008cfb  call    GetFocus
0x180008d00  mov     rcx, rax; HWND
0x180008d03  call    ?ValidateHwndNoRip@@YAPEAUtagWND@@PEAUHWND__@@@Z; ValidateHwndNoRip(HWND__ *)
0x180008d08  mov     rdi, rax
0x180008d0b  test    r15w, r15w
0x180008d0f  jz      loc_180008F76
0x180008d15  test    rax, rax
0x180008d18  mov     rcx, r14; HWND
0x180008d1b  cmovz   rdi, rsi
0x180008d1f  call    ?ValidateHwnd@@YAPEAUtagWND@@PEAUHWND__@@@Z; ValidateHwnd(HWND__ *)
0x180008d24  mov     rbx, rax
0x180008d27  test    rax, rax
0x180008d2a  jz      short loc_180008D7E
0x180008d2c  mov     rcx, [rbx]; hWnd
0x180008d2f  call    ?DlgSetFocus@@YAXPEAUHWND__@@@Z; DlgSetFocus(HWND__ *)
0x180008d34  mov     r8, r13
0x180008d37  test    rbx, rbx
0x180008d3a  jz      short loc_180008D3F
0x180008d3c  mov     r8, [rbx]; HWND
0x180008d3f  mov     rdx, r13
0x180008d42  test    rdi, rdi
0x180008d45  jz      short loc_180008D4A
0x180008d47  mov     rdx, [rdi]; HWND
0x180008d4a  mov     rcx, rsi; struct tagWND *
0x180008d4d  call    ?xxxCheckDefPushButton@@YAXPEAUtagWND@@PEAUHWND__@@1@Z; xxxCheckDefPushButton(tagWND *,HWND__ *,HWND__ *)
0x180008d52  jmp     short loc_180008D7E
0x180008d54  xor     eax, eax
0x180008d56  jmp     loc_180008C34
0x180008d5b  test    r12, r12
0x180008d5e  jz      loc_180008BF6
0x180008d64  jmp     loc_180008C49
0x180008d69  mov     r9d, 4
0x180008d6f  mov     r8, r14
0x180008d72  mov     rdx, rsi
0x180008d75  mov     rcx, rsi
0x180008d78  call    cs:__imp_NtUserFillWindow
0x180008d7e  mov     eax, 1
0x180008d83  jmp     loc_180008C34
0x180008d88  mov     eax, edi
0x180008d8a  sub     eax, 2Fh ; '/'
0x180008d8d  jz      loc_180008C49
0x180008d93  sub     eax, r8d
0x180008d96  jz      loc_1800093B3
0x180008d9c  sub     eax, 8
0x180008d9f  jz      loc_180008C49
0x180008da5  sub     eax, 17h
0x180008da8  jz      loc_18000925A
0x180008dae  sub     eax, 5
0x180008db1  jz      loc_180009233
0x180008db7  sub     eax, 1Bh
0x180008dba  jnz     loc_1800093A5
0x180008dc0  mov     edx, 4000h
0x180008dc5  xor     ecx, ecx
0x180008dc7  call    cs:__imp_NtUserSetThreadState
0x180008dcd  mov     rax, [rbx+128h]
0x180008dd4  mov     rcx, [rax+8]
0x180008dd8  mov     rcx, [rcx+30h]; ho
0x180008ddc  test    rcx, rcx
0x180008ddf  jz      short loc_180008DE7
0x180008de1  call    cs:__imp_DeleteObject
0x180008de7  mov     rax, [rbx+128h]
0x180008dee  mov     rcx, [rax+8]
0x180008df2  mov     [rcx+30h], r13
0x180008df6  mov     rax, [rbx+128h]
0x180008dfd  mov     rcx, [rax+8]
0x180008e01  mov     rcx, [rcx+40h]; ho
0x180008e05  test    rcx, rcx
0x180008e08  jz      short loc_180008E10
0x180008e0a  call    cs:__imp_DeleteObject
0x180008e10  mov     rax, [rbx+128h]
0x180008e17  mov     rcx, [rax+8]
0x180008e1b  mov     [rcx+40h], r13
0x180008e1f  lea     rcx, ?DialogLookaside@@3U_LOOKASIDE@@A; struct _LOOKASIDE *
0x180008e26  mov     rdx, [rbx+128h]
0x180008e2d  mov     rdx, [rdx+8]; void *
0x180008e31  call    ?FreeLookasideEntry@@YAXPEAU_LOOKASIDE@@PEAX@Z; FreeLookasideEntry(_LOOKASIDE *,void *)
0x180008e36  xor     edx, edx
0x180008e38  mov     rcx, rsi
0x180008e3b  call    cs:__imp_NtUserSetDialogPointer
0x180008e41  jmp     loc_180008C8C
0x180008e46  mov     rcx, rbx; struct tagWND *
0x180008e49  call    ?GetParentDialog@@YAPEAUtagWND@@PEAU1@@Z; GetParentDialog(tagWND *)
0x180008e4e  mov     rdi, rax
0x180008e51  cmp     rax, rbx
0x180008e54  jnz     loc_180009183
0x180008e5a  mov     rcx, rdi; struct tagWND *
0x180008e5d  test    r14, r14
0x180008e60  jnz     loc_180009086
0x180008e66  call    ?xxxSaveDlgFocus@@YAHPEAUtagWND@@@Z; xxxSaveDlgFocus(tagWND *)
0x180008e6b  jmp     loc_180008C8C
0x180008e70  mov     rax, cs:gpsi
0x180008e77  movzx   ecx, word ptr [rax+15Ch]
0x180008e7e  cmp     [rbx+0C8h], ecx
0x180008e84  jl      loc_180008D54
0x180008e8a  mov     edx, 2A4h
0x180008e8f  mov     rcx, rsi
0x180008e92  call    cs:__imp_NtUserSetWindowFNID
0x180008e98  jmp     loc_180008AEF
0x180008e9d  mov     rcx, rbx; struct tagWND *
0x180008ea0  call    ?GetParentDialog@@YAPEAUtagWND@@PEAU1@@Z; GetParentDialog(tagWND *)
0x180008ea5  cmp     rax, rbx
0x180008ea8  jnz     loc_180008C1D
0x180008eae  test    r14, r14
0x180008eb1  jz      loc_180009406
0x180008eb7  test    r15w, r15w
0x180008ebb  jz      short loc_180008ED2
0x180008ebd  mov     rax, [rbx+128h]
0x180008ec4  mov     rcx, [rax+8]
0x180008ec8  test    byte ptr [rcx+18h], 1
0x180008ecc  jnz     loc_180008C8C
0x180008ed2  mov     rax, cs:gpsi
0x180008ed9  test    [rax+1B5Ch], r8b
0x180008ee0  jz      loc_180008C1D
0x180008ee6  mov     edx, 7
0x180008eeb  mov     rcx, rsi
0x180008eee  call    cs:__imp_NtUserQueryWindow
0x180008ef4  test    rax, rax
0x180008ef7  jz      loc_180008C1D
0x180008efd  mov     rax, [rbx+128h]
0x180008f04  mov     rcx, rsi; hDlg
0x180008f07  mov     rdx, [rax+8]
0x180008f0b  mov     edx, [rdx+20h]; nIDDlgItem
0x180008f0e  call    GetDlgItem
0x180008f13  mov     rsi, rax
0x180008f16  test    rax, rax
0x180008f19  jz      loc_180008C1D
0x180008f1f  xorps   xmm0, xmm0
0x180008f22  xor     ecx, ecx
0x180008f24  movups  xmmword ptr [rbp+Rect.left], xmm0
0x180008f28  call    cs:__imp_NtUserShowCursor
0x180008f2e  lea     rdx, [rbp+Rect]; lpRect
0x180008f32  mov     rcx, rsi; hWnd
0x180008f35  call    GetWindowRect
0x180008f3a  mov     eax, [rbp+Rect.bottom]
0x180008f3d  mov     r8d, 2
0x180008f43  sub     eax, [rbp+Rect.top]
0x180008f46  cdq
0x180008f47  idiv    r8d
0x180008f4a  mov     ecx, eax
0x180008f4c  mov     eax, [rbp+Rect.right]
0x180008f4f  sub     eax, [rbp+Rect.left]
0x180008f52  add     ecx, [rbp+Rect.top]
0x180008f55  cdq
0x180008f56  idiv    r8d
  ... truncated ...
```
