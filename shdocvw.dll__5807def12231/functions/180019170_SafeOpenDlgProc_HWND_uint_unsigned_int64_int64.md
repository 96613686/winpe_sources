# SafeOpenDlgProc(HWND__ *,uint,unsigned __int64,__int64)

- ea: `0x180019170`
- end: `0x180019687`
- name: `?SafeOpenDlgProc@@YA_JPEAUHWND__@@I_K_J@Z`
- size: `1303`
- prototype: `INT_PTR __stdcall(HWND, UINT, WPARAM, LPARAM)`
- caller_count: `0`
- callee_count: `14`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180002240`
- `0x180015aa0`
- `0x180015b28`
- `0x180017170`
- `0x180017264`
- `0x18001911c`
- `0x180019170`
- `0x180019950`
- `0x180019a78`
- `0x180019c58`
- `0x180019d7c`
- `0x18001a26c`
- `0x18001d3b0`
- `0x180029010`

## import_xrefs

- `SHELL32!ShellExecuteW` at `0x18001965b`
- `SHELL32!ShellExecuteW` at `0x18001965b`
- `SHLWAPI!AssocGetPerceivedType` at `0x1800192c8`
- `SHLWAPI!AssocGetPerceivedType` at `0x1800192c8`
- `SHLWAPI!PathFindExtensionW` at `0x18001929f`
- `SHLWAPI!PathFindExtensionW` at `0x18001929f`
- `SHLWAPI!__imp_SHSetDefaultDialogFont` at `0x1800191e2`
- `SHLWAPI!__imp_SHSetDefaultDialogFont` at `0x1800191f0`
- `SHLWAPI!__imp_SHSetDefaultDialogFont` at `0x1800191fe`
- `SHLWAPI!__imp_SHSetDefaultDialogFont` at `0x18001920c`
- `SHLWAPI!__imp_SHSetDefaultDialogFont` at `0x1800191e2`
- `SHLWAPI!__imp_SHSetDefaultDialogFont` at `0x1800191f0`
- `SHLWAPI!__imp_SHSetDefaultDialogFont` at `0x1800191fe`
- `SHLWAPI!__imp_SHSetDefaultDialogFont` at `0x18001920c`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180019527`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180019527`
- `USER32!IsDlgButtonChecked` at `0x18001936c`
- `USER32!IsDlgButtonChecked` at `0x1800193b9`
- `USER32!IsDlgButtonChecked` at `0x1800193e9`
- `USER32!IsDlgButtonChecked` at `0x18001936c`
- `USER32!IsDlgButtonChecked` at `0x1800193b9`
- `USER32!IsDlgButtonChecked` at `0x1800193e9`
- `USER32!CheckDlgButton` at `0x18001921d`
- `USER32!CheckDlgButton` at `0x18001921d`
- `USER32!GetDoubleClickTime` at `0x18001922e`
- `USER32!GetDoubleClickTime` at `0x18001923d`
- `USER32!GetDoubleClickTime` at `0x18001922e`
- `USER32!GetDoubleClickTime` at `0x18001923d`
- `USER32!GetDlgItem` at `0x180019382`
- `USER32!GetDlgItem` at `0x180019382`
- `USER32!SendMessageW` at `0x180019396`
- `USER32!SendMessageW` at `0x180019396`
- `USER32!EndDialog` at `0x180019405`
- `USER32!EndDialog` at `0x180019517`
- `USER32!EndDialog` at `0x180019405`
- `USER32!EndDialog` at `0x180019517`
- `USER32!SetWindowLongPtrW` at `0x1800191d4`
- `USER32!SetWindowLongPtrW` at `0x1800191d4`
- `USER32!GetWindowLongPtrW` at `0x18001919a`
- `USER32!GetWindowLongPtrW` at `0x18001919a`
- `OLEAUT32!__imp_SysAllocString` at `0x1800195cb`
- `OLEAUT32!__imp_SysAllocString` at `0x1800195cb`
- `OLEAUT32!__imp_SysFreeString` at `0x1800195ef`
- `OLEAUT32!__imp_SysFreeString` at `0x1800195ef`

## pseudocode

```c
INT_PTR __fastcall SafeOpenDlgProc(HWND a1, int a2, __int64 a3, LONG_PTR a4)
{
  LONG_PTR WindowLongPtrW; // rax
  struct IUnknown *v9; // rdx
  LONG_PTR v10; // rsi
  int v11; // r15d
  PERCEIVEDFLAG DoubleClickTime; // esi
  HKEY v13; // rcx
  char *v14; // r14
  const WCHAR *ExtensionW; // rax
  int v16; // r8d
  PERCEIVED v17; // ecx
  const struct SIGNATURE_INFO **v18; // rsi
  bool v19; // r12
  int v20; // r14d
  int v21; // r14d
  int v22; // r14d
  int v23; // r14d
  LPARAM v24; // rbx
  HWND DlgItem; // rax
  INT_PTR v26; // rdx
  int v27; // r9d
  DWORD TickCount; // eax
  int v29; // eax
  const OLECHAR *v30; // rcx
  OLECHAR *v31; // rbx
  const unsigned __int16 *v32; // rdx
  __int64 v33; // rcx
  int UrlSchemeW; // eax
  PERCEIVEDFLAG pflag; // [rsp+80h] [rbp+7h] BYREF
  PERCEIVED ptype[2]; // [rsp+88h] [rbp+Fh] BYREF

  WindowLongPtrW = GetWindowLongPtrW(a1, 16);
  v10 = WindowLongPtrW;
  if ( !WindowLongPtrW )
  {
    if ( a2 == 272 )
    {
      v11 = 1;
      goto LABEL_4;
    }
    return 0;
  }
  v20 = a2 - 2;
  if ( !v20 )
  {
    CleanupDialogParam(a1, (HWND *)WindowLongPtrW);
    return 0;
  }
  v11 = 1;
  v21 = v20 - 76;
  if ( !v21 )
  {
    v29 = *(_DWORD *)(a4 + 16);
    if ( v29 == -530 )
    {
      *(_QWORD *)(a4 + 24) = *(_QWORD *)(v10 + 104);
      *(_QWORD *)(a4 + 192) = 0;
    }
    else if ( ((v29 + 4) & 0xFFFFFFFD) == 0 )
    {
      switch ( *(_QWORD *)(a4 + 8) )
      {
        case 0x1143LL:
          v33 = *(_QWORD *)(v10 + 88);
          if ( v33 )
          {
            if ( (*(_BYTE *)(v33 + 12) & 4) != 0 )
            {
              UrlSchemeW = GetUrlSchemeW(*(_QWORD *)(v33 + 56));
              if ( UrlSchemeW == 2 || UrlSchemeW == 11 )
                ShellExecuteW(a1, L"Open", *(LPCWSTR *)(*(_QWORD *)(v10 + 88) + 56LL), 0, 0, 1);
            }
          }
          break;
        case 0x1145LL:
          v32 = *(const unsigned __int16 **)(v10 + 48);
          if ( v32 )
            ViewCertProperties(a1, v32);
          break;
        case 0x114FLL:
          *(_QWORD *)ptype = 0;
          if ( (int)IECreateInstance(
                      &GUID_8cec58e7_07a1_11d9_b15e_000d56bfe6ee,
                      v9,
                      0x17u,
                      &GUID_8cec5884_07a1_11d9_b15e_000d56bfe6ee,
                      (void **)ptype) >= 0 )
          {
            v30 = &Class;
            if ( *(_QWORD *)(v10 + 112) )
              v30 = *(const OLECHAR **)(v10 + 112);
            v31 = SysAllocString(v30);
            if ( v31 )
            {
              (*(void (__fastcall **)(_QWORD, OLECHAR *))(**(_QWORD **)ptype + 24LL))(*(_QWORD *)ptype, v31);
              SysFreeString(v31);
            }
            (*(void (__fastcall **)(_QWORD))(**(_QWORD **)ptype + 16LL))(*(_QWORD *)ptype);
          }
          break;
      }
    }
    return 1;
  }
  v22 = v21 - 56;
  if ( !v22 )
  {
    if ( a3 )
      TickCount = GetTickCount();
    else
      TickCount = 0;
    *(_DWORD *)(v10 + 144) = TickCount;
    return 0;
  }
  v23 = v22 - 138;
  if ( !v23 )
  {
LABEL_4:
    if ( !a4 )
    {
LABEL_52:
      EndDialog(a1, 2);
      return 0;
    }
    SetWindowLongPtrW(a1, 16, a4);
    SHSetDefaultDialogFont(a1, 4419);
    SHSetDefaultDialogFont(a1, 4423);
    SHSetDefaultDialogFont(a1, 4425);
    SHSetDefaultDialogFont(a1, 4421);
    CheckDlgButton(a1, 4428, 1u);
    DoubleClickTime = dword_180038498;
    if ( dword_180038498 == -1 )
    {
      DoubleClickTime = 300;
      if ( GetDoubleClickTime() >= 0x12C )
        DoubleClickTime = GetDoubleClickTime();
      pflag = DoubleClickTime;
      if ( !(unsigned int)SHRegGetDWORD(
                            v13,
                            L"Software\\Microsoft\\Internet Explorer\\Download",
                            L"DownloadActivationDelay",
                            &pflag) )
        DoubleClickTime = pflag;
      dword_180038498 = DoubleClickTime;
    }
    v14 = (char *)(a4 + 80);
    *(_DWORD *)(a4 + 148) = DoubleClickTime;
    if ( *(_DWORD *)(a4 + 12) != 1 || *v14 )
      HideResourceAndResize(a1, 0x114Cu, &qword_18002D080, 3u);
    ExtensionW = PathFindExtensionW(*(LPCWSTR *)(a4 + 24));
    v17 = PERCEIVED_TYPE_UNKNOWN;
    ptype[0] = PERCEIVED_TYPE_UNKNOWN;
    if ( ExtensionW && *ExtensionW )
    {
      pflag = 0;
      AssocGetPerceivedType(ExtensionW, ptype, &pflag, 0);
      v17 = ptype[0];
    }
    v18 = (const struct SIGNATURE_INFO **)(a4 + 88);
    if ( !*v14 || *((_DWORD *)*v18 + 1) == 7 && v17 == PERCEIVED_TYPE_APPLICATION )
    {
      v19 = 1;
      if ( *v18 )
      {
        v27 = 1;
        if ( (*((_BYTE *)*v18 + 12) & 4) != 0 )
          goto LABEL_45;
      }
    }
    else
    {
      v19 = 0;
    }
    v27 = 0;
LABEL_45:
    if ( (unsigned int)SetDialogFileName(a1, *(const unsigned __int16 **)(a4 + 24), v16, v27)
      && (unsigned int)SetDialogPublisher(
                         a1,
                         *v18,
                         v19,
                         (unsigned __int16 **)(a4 + 104),
                         (HWND *)(a4 + 96),
                         (HFONT *)(a4 + 128))
      && (unsigned int)SetDialogFileTypeAndSize(a1, *(LPCWSTR *)(a4 + 32), *(unsigned int *)(a4 + 56))
      && (unsigned int)SetDialogFrom(a1, *(const unsigned __int16 **)(a4 + 40), *(_DWORD *)(a4 + 76)) )
    {
      if ( *v18 )
        v11 = *((_DWORD *)*v18 + 1);
      if ( (unsigned int)InitUI(
                           *(const WCHAR **)(a4 + 24),
                           *(const WCHAR **)(a4 + 32),
                           a1,
                           *(_DWORD *)a4,
                           *(_DWORD *)(a4 + 4),
                           *(LPCWSTR *)(a4 + 16),
                           *(_DWORD *)(a4 + 8),
                           *(_DWORD *)(a4 + 72),
                           v11,
                           *(_DWORD *)(a4 + 60),
                           *v14,
                           (_QWORD *)(a4 + 112),
                           (HICON *)(a4 + 136),
                           (__int64 *)(a4 + 120)) )
        return 0;
    }
    goto LABEL_52;
  }
  if ( v23 == 1 )
  {
    if ( (unsigned __int16)a3 != 2 )
    {
      if ( (unsigned __int16)a3 == 4426 )
      {
        if ( (unsigned int)AllowDownloadCommand((const struct SAFEOPENDLGPARAM *)WindowLongPtrW) )
        {
          if ( !IsDlgButtonChecked(a1, 4428) )
            *(_DWORD *)(v10 + 12) = 2;
          v26 = 1;
          goto LABEL_41;
        }
      }
      else
      {
        if ( (unsigned __int16)a3 != 4427 )
        {
          if ( (unsigned __int16)a3 == 4428 && *(_DWORD *)(WindowLongPtrW + 68) )
          {
            v24 = IsDlgButtonChecked(a1, 4428) == 0;
            DlgItem = GetDlgItem(a1, 4426);
            SendMessageW(DlgItem, 0x160Cu, 0, v24);
          }
          return 1;
        }
        if ( (unsigned int)AllowDownloadCommand((const struct SAFEOPENDLGPARAM *)WindowLongPtrW) )
        {
          if ( !IsDlgButtonChecked(a1, 4428) )
            *(_DWORD *)(v10 + 12) = 2;
          v26 = 4358;
          goto LABEL_41;
        }
      }
      return 1;
    }
    v26 = (unsigned __int16)a3;
LABEL_41:
    EndDialog(a1, v26);
    return 1;
  }
  return 0;
}

```

## disassembly

```asm
0x180019170  push    rbp
0x180019172  push    rbx
0x180019173  push    rsi
0x180019174  push    rdi
0x180019175  push    r12
0x180019177  push    r13
0x180019179  push    r14
0x18001917b  push    r15
0x18001917d  lea     rbp, [rsp-1Fh]
0x180019182  sub     rsp, 98h
0x180019189  mov     r14d, edx
0x18001918c  mov     rbx, r9
0x18001918f  mov     edx, 10h; nIndex
0x180019194  mov     r12, r8
0x180019197  mov     rdi, rcx
0x18001919a  call    cs:__imp_GetWindowLongPtrW
0x1800191a0  xor     r13d, r13d
0x1800191a3  mov     rsi, rax
0x1800191a6  test    rax, rax
0x1800191a9  jnz     loc_1800192F8
0x1800191af  cmp     r14d, 110h
0x1800191b6  jnz     loc_180019671
0x1800191bc  lea     r15d, [rax+1]
0x1800191c0  test    rbx, rbx
0x1800191c3  jz      loc_18001950F
0x1800191c9  mov     r8, rbx; dwNewLong
0x1800191cc  mov     edx, 10h; nIndex
0x1800191d1  mov     rcx, rdi; hWnd
0x1800191d4  call    cs:__imp_SetWindowLongPtrW
0x1800191da  mov     edx, 1143h
0x1800191df  mov     rcx, rdi
0x1800191e2  call    cs:__imp_SHSetDefaultDialogFont
0x1800191e8  mov     edx, 1147h
0x1800191ed  mov     rcx, rdi
0x1800191f0  call    cs:__imp_SHSetDefaultDialogFont
0x1800191f6  mov     edx, 1149h
0x1800191fb  mov     rcx, rdi
0x1800191fe  call    cs:__imp_SHSetDefaultDialogFont
0x180019204  mov     edx, 1145h
0x180019209  mov     rcx, rdi
0x18001920c  call    cs:__imp_SHSetDefaultDialogFont
0x180019212  mov     r8d, r15d; uCheck
0x180019215  mov     edx, 114Ch; nIDButton
0x18001921a  mov     rcx, rdi; hDlg
0x18001921d  call    cs:__imp_CheckDlgButton
0x180019223  mov     esi, cs:dword_180038498
0x180019229  cmp     esi, 0FFFFFFFFh
0x18001922c  jnz     short loc_18001926C
0x18001922e  call    cs:__imp_GetDoubleClickTime
0x180019234  mov     esi, 12Ch
0x180019239  cmp     eax, esi
0x18001923b  jb      short loc_180019245
0x18001923d  call    cs:__imp_GetDoubleClickTime
0x180019243  mov     esi, eax
0x180019245  lea     r9, [rbp+57h+pflag]; unsigned int *
0x180019249  mov     [rbp+57h+pflag], esi
0x18001924c  lea     r8, aDownloadactiva; "DownloadActivationDelay"
0x180019253  lea     rdx, aSoftwareMicros; "Software\\Microsoft\\Internet Explorer"...
0x18001925a  call    ?SHRegGetDWORD@@YAJPEAUHKEY__@@PEBG1PEAK@Z; SHRegGetDWORD(HKEY__ *,ushort const *,ushort const *,ulong *)
0x18001925f  test    eax, eax
0x180019261  jnz     short loc_180019266
0x180019263  mov     esi, [rbp+57h+pflag]
0x180019266  mov     cs:dword_180038498, esi
0x18001926c  lea     r14, [rbx+50h]
0x180019270  mov     [rbx+94h], esi
0x180019276  cmp     [rbx+0Ch], r15d
0x18001927a  jnz     short loc_180019281
0x18001927c  cmp     [r14], r13b
0x18001927f  jz      short loc_18001929B
0x180019281  mov     r9d, 3; unsigned int
0x180019287  lea     r8, qword_18002D080; unsigned int *
0x18001928e  mov     edx, 114Ch; unsigned int
0x180019293  mov     rcx, rdi; hWndTo
0x180019296  call    ?HideResourceAndResize@@YAXPEAUHWND__@@IPEBIK@Z; HideResourceAndResize(HWND__ *,uint,uint const *,ulong)
0x18001929b  mov     rcx, [rbx+18h]; pszPath
0x18001929f  call    cs:__imp_PathFindExtensionW
0x1800192a5  mov     ecx, r13d
0x1800192a8  mov     [rbp+57h+ptype], ecx
0x1800192ab  test    rax, rax
0x1800192ae  jz      short loc_1800192D1
0x1800192b0  cmp     [rax], r13w
0x1800192b4  jz      short loc_1800192D1
0x1800192b6  xor     r9d, r9d; ppszType
0x1800192b9  mov     [rbp+57h+pflag], r13d
0x1800192bd  lea     r8, [rbp+57h+pflag]; pflag
0x1800192c1  mov     rcx, rax; pszExt
0x1800192c4  lea     rdx, [rbp+57h+ptype]; ptype
0x1800192c8  call    cs:__imp_AssocGetPerceivedType
0x1800192ce  mov     ecx, [rbp+57h+ptype]
0x1800192d1  lea     rsi, [rbx+58h]
0x1800192d5  cmp     [r14], r13b
0x1800192d8  jz      loc_180019410
0x1800192de  mov     rax, [rsi]
0x1800192e1  cmp     dword ptr [rax+4], 7
0x1800192e5  jnz     short loc_1800192F0
0x1800192e7  cmp     ecx, 8
0x1800192ea  jz      loc_180019410
0x1800192f0  mov     r12b, r13b
0x1800192f3  jmp     loc_180019424
0x1800192f8  sub     r14d, 2
0x1800192fc  jz      loc_180019666
0x180019302  mov     r15d, 1
0x180019308  sub     r14d, 4Ch ; 'L'
0x18001930c  jz      loc_18001953D
0x180019312  sub     r14d, 38h ; '8'
0x180019316  jz      loc_180019522
0x18001931c  sub     r14d, 8Ah
0x180019323  jz      loc_1800191C0
0x180019329  cmp     r14d, r15d
0x18001932c  jnz     loc_180019671
0x180019332  movzx   ecx, r12w
0x180019336  mov     eax, ecx
0x180019338  sub     eax, 2
0x18001933b  jz      loc_1800193FF
0x180019341  sub     eax, 1148h
0x180019346  jz      loc_1800193D1
0x18001934c  sub     eax, r15d
0x18001934f  jz      short loc_1800193A1
0x180019351  cmp     eax, r15d
0x180019354  jnz     loc_180019661
0x18001935a  cmp     [rsi+44h], r13d
0x18001935e  jz      loc_180019661
0x180019364  mov     edx, 114Ch; nIDButton
0x180019369  mov     rcx, rdi; hDlg
0x18001936c  call    cs:__imp_IsDlgButtonChecked
0x180019372  mov     rbx, r13
0x180019375  mov     edx, 114Ah; nIDDlgItem
0x18001937a  test    eax, eax
0x18001937c  mov     rcx, rdi; hDlg
0x18001937f  setz    bl
0x180019382  call    cs:__imp_GetDlgItem
0x180019388  mov     r9, rbx; lParam
0x18001938b  xor     r8d, r8d; wParam
0x18001938e  mov     rcx, rax; hWnd
0x180019391  mov     edx, 160Ch; Msg
0x180019396  call    cs:__imp_SendMessageW
0x18001939c  jmp     loc_180019661
0x1800193a1  mov     rcx, rsi; struct SAFEOPENDLGPARAM *
0x1800193a4  call    ?AllowDownloadCommand@@YAHPEBUSAFEOPENDLGPARAM@@@Z; AllowDownloadCommand(SAFEOPENDLGPARAM const *)
0x1800193a9  test    eax, eax
0x1800193ab  jz      loc_180019661
0x1800193b1  mov     edx, 114Ch; nIDButton
0x1800193b6  mov     rcx, rdi; hDlg
0x1800193b9  call    cs:__imp_IsDlgButtonChecked
0x1800193bf  test    eax, eax
0x1800193c1  jnz     short loc_1800193CA
0x1800193c3  mov     dword ptr [rsi+0Ch], 2
0x1800193ca  mov     edx, 1106h
0x1800193cf  jmp     short loc_180019402
0x1800193d1  mov     rcx, rsi; struct SAFEOPENDLGPARAM *
0x1800193d4  call    ?AllowDownloadCommand@@YAHPEBUSAFEOPENDLGPARAM@@@Z; AllowDownloadCommand(SAFEOPENDLGPARAM const *)
0x1800193d9  test    eax, eax
0x1800193db  jz      loc_180019661
0x1800193e1  mov     edx, 114Ch; nIDButton
0x1800193e6  mov     rcx, rdi; hDlg
0x1800193e9  call    cs:__imp_IsDlgButtonChecked
0x1800193ef  test    eax, eax
0x1800193f1  jnz     short loc_1800193FA
0x1800193f3  mov     dword ptr [rsi+0Ch], 2
0x1800193fa  mov     rdx, r15
0x1800193fd  jmp     short loc_180019402
0x1800193ff  mov     rdx, rcx; nResult
0x180019402  mov     rcx, rdi; hDlg
0x180019405  call    cs:__imp_EndDialog
0x18001940b  jmp     loc_180019661
0x180019410  mov     rax, [rsi]
0x180019413  mov     r12b, r15b
0x180019416  test    rax, rax
0x180019419  jz      short loc_180019424
0x18001941b  test    byte ptr [rax+0Ch], 4
0x18001941f  mov     r9d, r15d
0x180019422  jnz     short loc_180019427
0x180019424  mov     r9d, r13d; int
0x180019427  mov     rdx, [rbx+18h]; unsigned __int16 *
0x18001942b  mov     rcx, rdi; hDlg
0x18001942e  call    ?SetDialogFileName@@YAHPEAUHWND__@@PEBGHH@Z; SetDialogFileName(HWND__ *,ushort const *,int,int)
0x180019433  test    eax, eax
0x180019435  jz      loc_18001950F
0x18001943b  mov     rdx, [rsi]; struct SIGNATURE_INFO *
0x18001943e  lea     rax, [rbx+80h]
0x180019445  lea     rcx, [rbx+60h]
0x180019449  mov     qword ptr [rsp+0D0h+nShowCmd], rax; HFONT *
0x18001944e  mov     [rsp+0D0h+lpDirectory], rcx; HWND *
0x180019453  lea     r9, [rbx+68h]; unsigned __int16 **
0x180019457  mov     rcx, rdi; HWND
0x18001945a  mov     r8b, r12b; bool
0x18001945d  call    ?SetDialogPublisher@@YAHPEAUHWND__@@PEBUSIGNATURE_INFO@@_NPEAPEAGPEAPEAU1@PEAPEAUHFONT__@@@Z; SetDialogPublisher(HWND__ *,SIGNATURE_INFO const *,bool,ushort * *,HWND__ * *,HFONT__ * *)
0x180019462  test    eax, eax
0x180019464  jz      loc_18001950F
0x18001946a  mov     r8d, [rbx+38h]; qdw
0x18001946e  mov     rcx, rdi; hDlg
0x180019471  mov     rdx, [rbx+20h]; pszAssoc
0x180019475  call    ?SetDialogFileTypeAndSize@@YAHPEAUHWND__@@PEBGK@Z; SetDialogFileTypeAndSize(HWND__ *,ushort const *,ulong)
0x18001947a  test    eax, eax
0x18001947c  jz      loc_18001950F
0x180019482  mov     r8d, [rbx+4Ch]; int
0x180019486  mov     rcx, rdi; hWndTo
0x180019489  mov     rdx, [rbx+28h]; unsigned __int16 *
0x18001948d  call    ?SetDialogFrom@@YAHPEAUHWND__@@PEBGH@Z; SetDialogFrom(HWND__ *,ushort const *,int)
0x180019492  test    eax, eax
0x180019494  jz      short loc_18001950F
0x180019496  mov     rax, [rsi]
0x180019499  mov     r8b, [r14]
0x18001949c  mov     r9d, [rbx+3Ch]
0x1800194a0  test    rax, rax
0x1800194a3  jz      short loc_1800194A9
0x1800194a5  mov     r15d, [rax+4]
0x1800194a9  lea     rax, [rbx+78h]
0x1800194ad  mov     [rsp+0D0h+var_68], rax
0x1800194b2  lea     rcx, [rbx+88h]
0x1800194b9  mov     eax, [rbx+48h]
0x1800194bc  lea     rdx, [rbx+70h]
0x1800194c0  mov     [rsp+0D0h+var_70], rcx
0x1800194c5  mov     rcx, [rbx+18h]
0x1800194c9  mov     [rsp+0D0h+var_78], rdx
0x1800194ce  mov     rdx, [rbx+20h]
0x1800194d2  mov     [rsp+0D0h+var_80], r8b
0x1800194d7  mov     r8, rdi
0x1800194da  mov     [rsp+0D0h+var_88], r9d
0x1800194df  mov     r9d, [rbx]
0x1800194e2  mov     [rsp+0D0h+var_90], r15d
0x1800194e7  mov     [rsp+0D0h+var_98], eax
0x1800194eb  mov     eax, [rbx+8]
0x1800194ee  mov     [rsp+0D0h+var_A0], eax
0x1800194f2  mov     rax, [rbx+10h]
0x1800194f6  mov     qword ptr [rsp+0D0h+nShowCmd], rax
0x1800194fb  mov     eax, [rbx+4]
0x1800194fe  mov     dword ptr [rsp+0D0h+lpDirectory], eax
0x180019502  call    ?InitUI@@YAHPEBG0PEAUHWND__@@W4SOCLIENT@@W4ATTACHMENT_PROMPT@@0HHW4SIGNATURE_STATE@@H_NPEAPEBGPEAPEAUHICON__@@PEAPEAUHFONT__@@K@Z; InitUI(ushort const *,ushort const *,HWND__ *,SOCLIENT,ATTACHMENT_PROMPT,ushort const *,int,int,SIGNATURE_STATE,int,bool,ushort const * *,HICON__ * *,HFONT__ * *,ulong)
0x180019507  test    eax, eax
0x180019509  jnz     loc_180019671
0x18001950f  mov     edx, 2; nResult
0x180019514  mov     rcx, rdi; hDlg
0x180019517  call    cs:__imp_EndDialog
0x18001951d  jmp     loc_180019671
0x180019522  test    r12, r12
0x180019525  jz      short loc_18001952F
0x180019527  call    cs:__imp_GetTickCount
0x18001952d  jmp     short loc_180019532
0x18001952f  mov     eax, r13d
0x180019532  mov     [rsi+90h], eax
0x180019538  jmp     loc_180019671
0x18001953d  mov     eax, [rbx+10h]
0x180019540  cmp     eax, 0FFFFFDEEh
0x180019545  jnz     short loc_18001955B
0x180019547  mov     rax, [rsi+68h]
0x18001954b  mov     [rbx+18h], rax
0x18001954f  mov     [rbx+0C0h], r13
0x180019556  jmp     loc_180019661
0x18001955b  add     eax, 4
0x18001955e  test    eax, 0FFFFFFFDh
0x180019563  jnz     loc_180019661
0x180019569  mov     rax, [rbx+8]
0x18001956d  sub     rax, 1143h
0x180019573  jz      loc_18001961A
0x180019579  sub     rax, 2
0x18001957d  jz      loc_180019607
0x180019583  cmp     rax, 0Ah
0x180019587  jnz     loc_180019661
0x18001958d  lea     rax, [rbp+57h+ptype]
0x180019591  mov     qword ptr [rbp+57h+ptype], r13
0x180019595  lea     r9, _GUID_8cec5884_07a1_11d9_b15e_000d56bfe6ee; struct _GUID *
0x18001959c  mov     [rsp+0D0h+lpDirectory], rax; void **
0x1800195a1  mov     r8d, 17h; unsigned int
0x1800195a7  lea     rcx, _GUID_8cec58e7_07a1_11d9_b15e_000d56bfe6ee; struct _GUID *
0x1800195ae  call    ?IECreateInstance@@YAJAEBU_GUID@@PEAUIUnknown@@K0PEAPEAX@Z; IECreateInstance(_GUID const &,IUnknown *,ulong,_GUID const &,void * *)
0x1800195b3  test    eax, eax
0x1800195b5  js      loc_180019661
0x1800195bb  cmp     [rsi+70h], r13
0x1800195bf  lea     rcx, Class
0x1800195c6  cmovnz  rcx, [rsi+70h]; psz
0x1800195cb  call    cs:__imp_SysAllocString
0x1800195d1  mov     rbx, rax
0x1800195d4  test    rax, rax
0x1800195d7  jz      short loc_1800195F5
0x1800195d9  mov     rcx, qword ptr [rbp+57h+ptype]
0x1800195dd  mov     rdx, [rcx]
0x1800195e0  mov     rax, [rdx+18h]
0x1800195e4  mov     rdx, rbx
0x1800195e7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800195ec  mov     rcx, rbx; bstrString
0x1800195ef  call    cs:__imp_SysFreeString
0x1800195f5  mov     rcx, qword ptr [rbp+57h+ptype]
0x1800195f9  mov     rax, [rcx]
0x1800195fc  mov     rax, [rax+10h]
0x180019600  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019605  jmp     short loc_180019661
0x180019607  mov     rdx, [rsi+30h]; unsigned __int16 *
0x18001960b  test    rdx, rdx
0x18001960e  jz      short loc_180019661
0x180019610  mov     rcx, rdi; HWND
0x180019613  call    ?ViewCertProperties@@YAHPEAUHWND__@@PEBG@Z; ViewCertProperties(HWND__ *,ushort const *)
0x180019618  jmp     short loc_180019661
0x18001961a  mov     rcx, [rsi+58h]
0x18001961e  test    rcx, rcx
0x180019621  jz      short loc_180019661
0x180019623  test    byte ptr [rcx+0Ch], 4
0x180019627  jz      short loc_180019661
0x180019629  mov     rcx, [rcx+38h]
0x18001962d  call    GetUrlSchemeW
  ... truncated ...
```
