# CreateArchiveWizard::DoCreateArchive(HWND__ *)

- ea: `0x180051400`
- end: `0x180051850`
- name: `?DoCreateArchive@CreateArchiveWizard@@AEAA_JPEAUHWND__@@@Z`
- size: `1104`
- prototype: `__int64 __fastcall(int **this, HWND hDlg)`
- caller_count: `1`
- callee_count: `11`
- tags: `file_ops, registry_config, installer_update, broker_com_uri`

## callers

- `0x180050fe4`

## callees

- `0x180020cbc`
- `0x18003534c`
- `0x180036f50`
- `0x180050680`
- `0x1800506fc`
- `0x180050870`
- `0x180051400`
- `0x18005225c`
- `0x180052574`
- `0x180052838`
- `0x18005ca84`

## import_xrefs

- `SHLWAPI!PathFileExistsW` at `0x18005158a`
- `SHLWAPI!PathFileExistsW` at `0x18005158a`
- `SHLWAPI!PathIsRelativeW` at `0x18005153e`
- `SHLWAPI!PathIsRelativeW` at `0x18005153e`
- `SHLWAPI!PathIsDirectoryW` at `0x18005159f`
- `SHLWAPI!PathIsDirectoryW` at `0x18005159f`
- `SHLWAPI!__imp_ShellMessageBoxW` at `0x180051565`
- `SHLWAPI!__imp_ShellMessageBoxW` at `0x1800515c6`
- `SHLWAPI!__imp_ShellMessageBoxW` at `0x1800516f6`
- `SHLWAPI!__imp_ShellMessageBoxW` at `0x180051816`
- `SHLWAPI!__imp_ShellMessageBoxW` at `0x180051565`
- `SHLWAPI!__imp_ShellMessageBoxW` at `0x1800515c6`
- `SHLWAPI!__imp_ShellMessageBoxW` at `0x1800516f6`
- `SHLWAPI!__imp_ShellMessageBoxW` at `0x180051816`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800516c1`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800516c1`
- `USER32!SendMessageW` at `0x180051622`
- `USER32!SendMessageW` at `0x18005167c`
- `USER32!SendMessageW` at `0x1800517d9`
- `USER32!SendMessageW` at `0x180051622`
- `USER32!SendMessageW` at `0x18005167c`
- `USER32!SendMessageW` at `0x1800517d9`
- `USER32!EnableWindow` at `0x180051466`
- `USER32!EnableWindow` at `0x180051480`
- `USER32!EnableWindow` at `0x18005149a`
- `USER32!EnableWindow` at `0x1800514a6`
- `USER32!EnableWindow` at `0x1800514b2`
- `USER32!EnableWindow` at `0x1800514cc`
- `USER32!EnableWindow` at `0x1800514e6`
- `USER32!EnableWindow` at `0x180051466`
- `USER32!EnableWindow` at `0x180051480`
- `USER32!EnableWindow` at `0x18005149a`
- `USER32!EnableWindow` at `0x1800514a6`
- `USER32!EnableWindow` at `0x1800514b2`
- `USER32!EnableWindow` at `0x1800514cc`
- `USER32!EnableWindow` at `0x1800514e6`
- `USER32!GetDlgItem` at `0x180051435`
- `USER32!GetDlgItem` at `0x180051448`
- `USER32!GetDlgItem` at `0x18005145b`
- `USER32!GetDlgItem` at `0x180051475`
- `USER32!GetDlgItem` at `0x18005148f`
- `USER32!GetDlgItem` at `0x1800514c1`
- `USER32!GetDlgItem` at `0x1800514db`
- `USER32!GetDlgItem` at `0x180051435`
- `USER32!GetDlgItem` at `0x180051448`
- `USER32!GetDlgItem` at `0x18005145b`
- `USER32!GetDlgItem` at `0x180051475`
- `USER32!GetDlgItem` at `0x18005148f`
- `USER32!GetDlgItem` at `0x1800514c1`
- `USER32!GetDlgItem` at `0x1800514db`
- `USER32!IsDlgButtonChecked` at `0x180051749`
- `USER32!IsDlgButtonChecked` at `0x18005176f`
- `USER32!IsDlgButtonChecked` at `0x180051749`
- `USER32!IsDlgButtonChecked` at `0x18005176f`

## pseudocode

```c
__int64 __fastcall CreateArchiveWizard::DoCreateArchive(int **this, HWND hDlg)
{
  HWND v3; // rax
  HWND v4; // rax
  HWND v5; // rax
  HWND v6; // rax
  HWND v7; // rax
  __int64 v8; // rdx
  __int64 v9; // r8
  const WCHAR *v10; // rax
  __int64 v11; // rdx
  __int64 v12; // r8
  const WCHAR *v13; // rax
  __int64 v14; // rdx
  __int64 v15; // r8
  const WCHAR *v16; // rax
  int v17; // eax
  __int64 v18; // rdx
  __int64 v19; // r8
  const WCHAR *v20; // rax
  HWND *FileW; // rbx
  int *v22; // rcx
  int *v23; // rax
  UINT v24; // eax
  UINT v25; // eax
  int v26; // eax
  WPARAM v27; // r8
  HWND *v29; // [rsp+40h] [rbp-59h] BYREF
  _QWORD v30[4]; // [rsp+48h] [rbp-51h] BYREF
  char v31; // [rsp+68h] [rbp-31h]
  HWND *p_hWnd; // [rsp+70h] [rbp-29h] BYREF
  CreateArchiveWizard *v33; // [rsp+78h] [rbp-21h]
  __int64 *v34; // [rsp+80h] [rbp-19h]
  int v35; // [rsp+88h] [rbp-11h] BYREF
  int v36; // [rsp+8Ch] [rbp-Dh]
  char v37; // [rsp+90h] [rbp-9h]
  char v38; // [rsp+91h] [rbp-8h]
  __int64 v39; // [rsp+98h] [rbp-1h]
  __int64 v40; // [rsp+A0h] [rbp+7h]
  HWND hDlga; // [rsp+A8h] [rbp+Fh] BYREF
  HWND hWnd; // [rsp+B0h] [rbp+17h] BYREF
  HWND DlgItem; // [rsp+B8h] [rbp+1Fh] BYREF
  __int64 v44; // [rsp+C0h] [rbp+27h] BYREF
  __int64 v45; // [rsp+C8h] [rbp+2Fh] BYREF

  hDlga = hDlg;
  hWnd = GetDlgItem(hDlg, 10652);
  DlgItem = GetDlgItem(hDlga, 10653);
  v3 = GetDlgItem(hDlga, 1021);
  EnableWindow(v3, 0);
  v4 = GetDlgItem(hDlga, 10650);
  EnableWindow(v4, 0);
  v5 = GetDlgItem(hDlga, 10651);
  EnableWindow(v5, 0);
  EnableWindow(hWnd, 0);
  EnableWindow(DlgItem, 0);
  v6 = GetDlgItem(hDlga, 10654);
  EnableWindow(v6, 0);
  v7 = GetDlgItem(hDlga, 10655);
  EnableWindow(v7, 0);
  v30[0] = &hDlga;
  v30[1] = &hWnd;
  v30[2] = this;
  v30[3] = &DlgItem;
  if ( CreateArchiveWizard::UpdateDestinationPath((CreateArchiveWizard *)this, hDlga) < 0
    || (int)CreateArchiveWizard::ValidateDestinationPath((CreateArchiveWizard *)this) < 0 )
  {
    ShellMessageBoxW(&_ImageBase, hDlga, (LPCWSTR)0x2983, (LPCWSTR)0x2941, 0x10u);
    v31 = 0;
    _lambda_8261491ff9610255c511311215286b88_::operator()(v30);
  }
  else
  {
    v10 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(this + 5, v8, v9);
    if ( PathIsRelativeW(v10) )
    {
      ShellMessageBoxW(&_ImageBase, hDlga, (LPCWSTR)0x2984, (LPCWSTR)0x2941, 0x10u);
      v31 = 0;
      _lambda_8261491ff9610255c511311215286b88_::operator()(v30);
    }
    else
    {
      v13 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(this + 5, v11, v12);
      if ( PathFileExistsW(v13)
        && (v16 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(this + 5, v14, v15),
            PathIsDirectoryW(v16)) )
      {
        ShellMessageBoxW(&_ImageBase, hDlga, (LPCWSTR)0x2985, (LPCWSTR)0x2941, 0x10u);
        v31 = 0;
        _lambda_8261491ff9610255c511311215286b88_::operator()(v30);
      }
      else
      {
        v44 = 0;
        if ( *((_QWORD *)this[9] + 5) )
        {
          p_hWnd = &hWnd;
          v33 = (CreateArchiveWizard *)this;
          v34 = &v44;
          v17 = _lambda_d68eed1bb0f052057592462c50baa577_::operator()(&p_hWnd);
          if ( v17 < 0 )
            goto LABEL_10;
        }
        v45 = 0;
        if ( CreateArchiveWizard::SupportsCompressionLevels((CreateArchiveWizard *)this)
          && (p_hWnd = &hDlga,
              v33 = (CreateArchiveWizard *)&v45,
              v17 = _lambda_1461ea3f50b557e755def5bcfd91e90b_::operator()(&p_hWnd),
              v17 < 0) )
        {
LABEL_10:
          *((_DWORD *)this + 22) = v17;
          SendMessageW(hDlga, 0x465u, 2u, 0);
          v31 = 0;
          _lambda_8261491ff9610255c511311215286b88_::operator()(v30);
        }
        else
        {
          v20 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(this + 5, v18, v19);
          FileW = (HWND *)CreateFileW(v20, 0xC0010000, 0, 0, 2u, 0x80u, 0);
          v29 = FileW;
          if ( (((unsigned __int64)FileW + 1) & 0xFFFFFFFFFFFFFFFEuLL) != 0 )
          {
            v36 = 0;
            v22 = this[9];
            v35 = *v22;
            v23 = this[10];
            if ( v23 && !*((_QWORD *)v22 + 5) )
              v36 = *v23;
            if ( !*((_BYTE *)v22 + 17) || (v24 = IsDlgButtonChecked(hDlga, 10654), v37 = 1, v24 != 1) )
              v37 = 0;
            if ( !*((_BYTE *)this[9] + 16) || (v25 = IsDlgButtonChecked(hDlga, 10655), v38 = 1, v25 != 1) )
              v38 = 0;
            v39 = v44;
            v40 = v45;
            p_hWnd = FileW;
            v29 = 0;
            v26 = CreateArchive(&v35, &p_hWnd, this + 2);
            *((_DWORD *)this + 22) = v26;
            if ( v26 < 0 )
            {
              v27 = 1;
              if ( v26 != -2147023673 )
                v27 = 2;
              SendMessageW(hDlga, 0x465u, v27, 0);
              wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v29);
              v31 = 0;
              _lambda_8261491ff9610255c511311215286b88_::operator()(v30);
            }
            else
            {
              wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v29);
            }
          }
          else
          {
            ShellMessageBoxW(&_ImageBase, hDlga, (LPCWSTR)0x2986, (LPCWSTR)0x2941, 0x10u);
            wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v29);
            v31 = 0;
            _lambda_8261491ff9610255c511311215286b88_::operator()(v30);
          }
        }
      }
    }
  }
  return 1;
}

```

## disassembly

```asm
0x180051400  mov     [rsp-8+arg_10], rbx
0x180051405  push    rbp
0x180051406  push    rsi
0x180051407  push    r14
0x180051409  lea     rbp, [rsp-47h]
0x18005140e  sub     rsp, 0E0h
0x180051415  mov     rax, cs:__security_cookie
0x18005141c  xor     rax, rsp
0x18005141f  mov     [rbp+57h+var_20], rax
0x180051423  mov     rax, rdx
0x180051426  mov     rsi, rcx
0x180051429  mov     [rbp+57h+hDlg], rdx
0x18005142d  mov     edx, 299Ch; nIDDlgItem
0x180051432  mov     rcx, rax; hDlg
0x180051435  call    cs:__imp_GetDlgItem
0x18005143b  mov     [rbp+57h+hWnd], rax
0x18005143f  mov     edx, 299Dh; nIDDlgItem
0x180051444  mov     rcx, [rbp+57h+hDlg]; hDlg
0x180051448  call    cs:__imp_GetDlgItem
0x18005144e  mov     [rbp+57h+var_38], rax
0x180051452  mov     edx, 3FDh; nIDDlgItem
0x180051457  mov     rcx, [rbp+57h+hDlg]; hDlg
0x18005145b  call    cs:__imp_GetDlgItem
0x180051461  mov     rcx, rax; hWnd
0x180051464  xor     edx, edx; bEnable
0x180051466  call    cs:__imp_EnableWindow
0x18005146c  mov     edx, 299Ah; nIDDlgItem
0x180051471  mov     rcx, [rbp+57h+hDlg]; hDlg
0x180051475  call    cs:__imp_GetDlgItem
0x18005147b  mov     rcx, rax; hWnd
0x18005147e  xor     edx, edx; bEnable
0x180051480  call    cs:__imp_EnableWindow
0x180051486  mov     edx, 299Bh; nIDDlgItem
0x18005148b  mov     rcx, [rbp+57h+hDlg]; hDlg
0x18005148f  call    cs:__imp_GetDlgItem
0x180051495  mov     rcx, rax; hWnd
0x180051498  xor     edx, edx; bEnable
0x18005149a  call    cs:__imp_EnableWindow
0x1800514a0  xor     edx, edx; bEnable
0x1800514a2  mov     rcx, [rbp+57h+hWnd]; hWnd
0x1800514a6  call    cs:__imp_EnableWindow
0x1800514ac  xor     edx, edx; bEnable
0x1800514ae  mov     rcx, [rbp+57h+var_38]; hWnd
0x1800514b2  call    cs:__imp_EnableWindow
0x1800514b8  mov     edx, 299Eh; nIDDlgItem
0x1800514bd  mov     rcx, [rbp+57h+hDlg]; hDlg
0x1800514c1  call    cs:__imp_GetDlgItem
0x1800514c7  mov     rcx, rax; hWnd
0x1800514ca  xor     edx, edx; bEnable
0x1800514cc  call    cs:__imp_EnableWindow
0x1800514d2  mov     edx, 299Fh; nIDDlgItem
0x1800514d7  mov     rcx, [rbp+57h+hDlg]; hDlg
0x1800514db  call    cs:__imp_GetDlgItem
0x1800514e1  mov     rcx, rax; hWnd
0x1800514e4  xor     edx, edx; bEnable
0x1800514e6  call    cs:__imp_EnableWindow
0x1800514ec  lea     rax, [rbp+57h+hDlg]
0x1800514f0  mov     [rbp+57h+var_A8], rax
0x1800514f4  lea     rax, [rbp+57h+hWnd]
0x1800514f8  mov     [rbp+57h+var_A0], rax
0x1800514fc  mov     [rbp+57h+var_98], rsi
0x180051500  lea     rax, [rbp+57h+var_38]
0x180051504  mov     [rbp+57h+var_90], rax
0x180051508  mov     rdx, [rbp+57h+hDlg]; HWND
0x18005150c  mov     rcx, rsi; this
0x18005150f  call    ?UpdateDestinationPath@CreateArchiveWizard@@AEAAJPEAUHWND__@@@Z; CreateArchiveWizard::UpdateDestinationPath(HWND__ *)
0x180051514  xor     r14d, r14d
0x180051517  test    eax, eax
0x180051519  js      loc_1800517F9
0x18005151f  mov     rcx, rsi; this
0x180051522  call    ?ValidateDestinationPath@CreateArchiveWizard@@AEAAJXZ; CreateArchiveWizard::ValidateDestinationPath(void)
0x180051527  test    eax, eax
0x180051529  js      loc_1800517F9
0x18005152f  lea     rbx, [rsi+28h]
0x180051533  mov     rcx, rbx
0x180051536  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18005153b  mov     rcx, rax; pszPath
0x18005153e  call    cs:__imp_PathIsRelativeW
0x180051544  test    eax, eax
0x180051546  jz      short loc_18005157F
0x180051548  mov     [rsp+0F0h+fuStyle], 10h; fuStyle
0x180051550  mov     r9d, 2941h; lpcTitle
0x180051556  lea     r8d, [r9+43h]; lpcText
0x18005155a  mov     rdx, [rbp+57h+hDlg]; hWnd
0x18005155e  lea     rcx, __ImageBase; hAppInst
0x180051565  call    cs:__imp_ShellMessageBoxW
0x18005156b  nop
0x18005156c  mov     [rbp+57h+var_88], r14b
0x180051570  lea     rcx, [rbp+57h+var_A8]
0x180051574  call    ??R_lambda_8261491ff9610255c511311215286b88_@@QEBA@XZ; _lambda_8261491ff9610255c511311215286b88_::operator()(void)
0x180051579  nop
0x18005157a  jmp     loc_18005182B
0x18005157f  mov     rcx, rbx
0x180051582  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180051587  mov     rcx, rax; pszPath
0x18005158a  call    cs:__imp_PathFileExistsW
0x180051590  test    eax, eax
0x180051592  jz      short loc_1800515E0
0x180051594  mov     rcx, rbx
0x180051597  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18005159c  mov     rcx, rax; pszPath
0x18005159f  call    cs:__imp_PathIsDirectoryW
0x1800515a5  test    eax, eax
0x1800515a7  jz      short loc_1800515E0
0x1800515a9  mov     [rsp+0F0h+fuStyle], 10h; fuStyle
0x1800515b1  mov     r9d, 2941h; lpcTitle
0x1800515b7  lea     r8d, [r9+44h]; lpcText
0x1800515bb  mov     rdx, [rbp+57h+hDlg]; hWnd
0x1800515bf  lea     rcx, __ImageBase; hAppInst
0x1800515c6  call    cs:__imp_ShellMessageBoxW
0x1800515cc  nop
0x1800515cd  mov     [rbp+57h+var_88], r14b
0x1800515d1  lea     rcx, [rbp+57h+var_A8]
0x1800515d5  call    ??R_lambda_8261491ff9610255c511311215286b88_@@QEBA@XZ; _lambda_8261491ff9610255c511311215286b88_::operator()(void)
0x1800515da  nop
0x1800515db  jmp     loc_18005182B
0x1800515e0  mov     [rbp+57h+var_30], r14
0x1800515e4  mov     rax, [rsi+48h]
0x1800515e8  cmp     [rax+28h], r14
0x1800515ec  jbe     short loc_18005163C
0x1800515ee  lea     rax, [rbp+57h+hWnd]
0x1800515f2  mov     [rbp+57h+var_80], rax
0x1800515f6  mov     [rbp+57h+var_78], rsi
0x1800515fa  lea     rax, [rbp+57h+var_30]
0x1800515fe  mov     [rbp+57h+var_70], rax
0x180051602  lea     rcx, [rbp+57h+var_80]
0x180051606  call    ??R_lambda_d68eed1bb0f052057592462c50baa577_@@QEBA@XZ; _lambda_d68eed1bb0f052057592462c50baa577_::operator()(void)
0x18005160b  test    eax, eax
0x18005160d  jns     short loc_18005163C
0x18005160f  mov     [rsi+58h], eax
0x180051612  xor     r9d, r9d; lParam
0x180051615  mov     edx, 465h; Msg
0x18005161a  lea     r8d, [r9+2]; wParam
0x18005161e  mov     rcx, [rbp+57h+hDlg]; hWnd
0x180051622  call    cs:__imp_SendMessageW
0x180051628  nop
0x180051629  mov     [rbp+57h+var_88], r14b
0x18005162d  lea     rcx, [rbp+57h+var_A8]
0x180051631  call    ??R_lambda_8261491ff9610255c511311215286b88_@@QEBA@XZ; _lambda_8261491ff9610255c511311215286b88_::operator()(void)
0x180051636  nop
0x180051637  jmp     loc_18005182B
0x18005163c  mov     [rbp+57h+var_28], r14
0x180051640  mov     rcx, rsi; this
0x180051643  call    ?SupportsCompressionLevels@CreateArchiveWizard@@AEBA_NXZ; CreateArchiveWizard::SupportsCompressionLevels(void)
0x180051648  test    al, al
0x18005164a  jz      short loc_180051696
0x18005164c  lea     rax, [rbp+57h+hDlg]
0x180051650  mov     [rbp+57h+var_80], rax
0x180051654  lea     rax, [rbp+57h+var_28]
0x180051658  mov     [rbp+57h+var_78], rax
0x18005165c  lea     rcx, [rbp+57h+var_80]
0x180051660  call    ??R_lambda_1461ea3f50b557e755def5bcfd91e90b_@@QEBA@XZ; _lambda_1461ea3f50b557e755def5bcfd91e90b_::operator()(void)
0x180051665  test    eax, eax
0x180051667  jns     short loc_180051696
0x180051669  mov     [rsi+58h], eax
0x18005166c  xor     r9d, r9d; lParam
0x18005166f  mov     edx, 465h; Msg
0x180051674  lea     r8d, [r9+2]; wParam
0x180051678  mov     rcx, [rbp+57h+hDlg]; hWnd
0x18005167c  call    cs:__imp_SendMessageW
0x180051682  nop
0x180051683  mov     [rbp+57h+var_88], r14b
0x180051687  lea     rcx, [rbp+57h+var_A8]
0x18005168b  call    ??R_lambda_8261491ff9610255c511311215286b88_@@QEBA@XZ; _lambda_8261491ff9610255c511311215286b88_::operator()(void)
0x180051690  nop
0x180051691  jmp     loc_18005182B
0x180051696  mov     rcx, rbx
0x180051699  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18005169e  mov     [rsp+0F0h+hTemplateFile], r14; hTemplateFile
0x1800516a3  mov     [rsp+0F0h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x1800516ab  mov     [rsp+0F0h+fuStyle], 2; dwCreationDisposition
0x1800516b3  xor     r9d, r9d; lpSecurityAttributes
0x1800516b6  xor     r8d, r8d; dwShareMode
0x1800516b9  mov     edx, 0C0010000h; dwDesiredAccess
0x1800516be  mov     rcx, rax; lpFileName
0x1800516c1  call    cs:__imp_CreateFileW
0x1800516c7  mov     rbx, rax
0x1800516ca  mov     [rbp+57h+var_B0], rax
0x1800516ce  inc     rax
0x1800516d1  test    rax, 0FFFFFFFFFFFFFFFEh
0x1800516d7  jnz     short loc_180051719
0x1800516d9  mov     [rsp+0F0h+fuStyle], 10h; fuStyle
0x1800516e1  mov     r9d, 2941h; lpcTitle
0x1800516e7  lea     r8d, [r9+45h]; lpcText
0x1800516eb  mov     rdx, [rbp+57h+hDlg]; hWnd
0x1800516ef  lea     rcx, __ImageBase; hAppInst
0x1800516f6  call    cs:__imp_ShellMessageBoxW
0x1800516fc  lea     rcx, [rbp+57h+var_B0]
0x180051700  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x180051705  nop
0x180051706  mov     [rbp+57h+var_88], r14b
0x18005170a  lea     rcx, [rbp+57h+var_A8]
0x18005170e  call    ??R_lambda_8261491ff9610255c511311215286b88_@@QEBA@XZ; _lambda_8261491ff9610255c511311215286b88_::operator()(void)
0x180051713  nop
0x180051714  jmp     loc_18005182B
0x180051719  mov     [rbp+57h+var_64], r14d
0x18005171d  mov     rcx, [rsi+48h]
0x180051721  mov     eax, [rcx]
0x180051723  mov     [rbp+57h+var_68], eax
0x180051726  mov     rax, [rsi+50h]
0x18005172a  test    rax, rax
0x18005172d  jz      short loc_18005173A
0x18005172f  cmp     [rcx+28h], r14
0x180051733  ja      short loc_18005173A
0x180051735  mov     eax, [rax]
0x180051737  mov     [rbp+57h+var_64], eax
0x18005173a  cmp     [rcx+11h], r14b
0x18005173e  jz      short loc_180051758
0x180051740  mov     edx, 299Eh; nIDButton
0x180051745  mov     rcx, [rbp+57h+hDlg]; hDlg
0x180051749  call    cs:__imp_IsDlgButtonChecked
0x18005174f  cmp     eax, 1
0x180051752  mov     [rbp+57h+var_60], 1
0x180051756  jz      short loc_18005175C
0x180051758  mov     [rbp+57h+var_60], r14b
0x18005175c  mov     rax, [rsi+48h]
0x180051760  cmp     [rax+10h], r14b
0x180051764  jz      short loc_18005177E
0x180051766  mov     edx, 299Fh; nIDButton
0x18005176b  mov     rcx, [rbp+57h+hDlg]; hDlg
0x18005176f  call    cs:__imp_IsDlgButtonChecked
0x180051775  cmp     eax, 1
0x180051778  mov     [rbp+57h+var_5F], 1
0x18005177c  jz      short loc_180051782
0x18005177e  mov     [rbp+57h+var_5F], r14b
0x180051782  mov     rax, [rbp+57h+var_30]
0x180051786  mov     [rbp+57h+var_58], rax
0x18005178a  mov     rax, [rbp+57h+var_28]
0x18005178e  mov     [rbp+57h+var_50], rax
0x180051792  mov     [rbp+57h+var_80], rbx
0x180051796  mov     [rbp+57h+var_B0], r14
0x18005179a  lea     r8, [rsi+10h]
0x18005179e  lea     rdx, [rbp+57h+var_80]
0x1800517a2  lea     rcx, [rbp+57h+var_68]
0x1800517a6  call    ?CreateArchive@@YAJAEBUCreateArchiveOptions@@V?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@AEBV?$vector@V?$unique_ptr@$$BY0A@GU?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@V?$allocator@V?$unique_ptr@$$BY0A@GU?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@@std@@@std@@PEAUHWND__@@@Z; CreateArchive(CreateArchiveOptions const &,wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>,std::vector<wistd::unique_ptr<ushort [0],wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>> const &,HWND__ *)
0x1800517ab  mov     [rsi+58h], eax
0x1800517ae  test    eax, eax
0x1800517b0  js      short loc_1800517BE
0x1800517b2  lea     rcx, [rbp+57h+var_B0]
0x1800517b6  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x1800517bb  nop
0x1800517bc  jmp     short loc_18005182B
0x1800517be  xor     r9d, r9d; lParam
0x1800517c1  mov     edx, 465h; Msg
0x1800517c6  mov     rcx, [rbp+57h+hDlg]; hWnd
0x1800517ca  cmp     eax, 800704C7h
0x1800517cf  lea     r8d, [r9+1]
0x1800517d3  jz      short loc_1800517D9
0x1800517d5  lea     r8d, [r9+2]; wParam
0x1800517d9  call    cs:__imp_SendMessageW
0x1800517df  lea     rcx, [rbp+57h+var_B0]
0x1800517e3  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x1800517e8  nop
0x1800517e9  mov     [rbp+57h+var_88], r14b
0x1800517ed  lea     rcx, [rbp+57h+var_A8]
0x1800517f1  call    ??R_lambda_8261491ff9610255c511311215286b88_@@QEBA@XZ; _lambda_8261491ff9610255c511311215286b88_::operator()(void)
0x1800517f6  nop
0x1800517f7  jmp     short loc_18005182B
0x1800517f9  mov     [rsp+0F0h+fuStyle], 10h; fuStyle
0x180051801  mov     r9d, 2941h; lpcTitle
0x180051807  lea     r8d, [r9+42h]; lpcText
0x18005180b  mov     rdx, [rbp+57h+hDlg]; hWnd
0x18005180f  lea     rcx, __ImageBase; hAppInst
0x180051816  call    cs:__imp_ShellMessageBoxW
0x18005181c  nop
0x18005181d  mov     [rbp+57h+var_88], r14b
0x180051821  lea     rcx, [rbp+57h+var_A8]
0x180051825  call    ??R_lambda_8261491ff9610255c511311215286b88_@@QEBA@XZ; _lambda_8261491ff9610255c511311215286b88_::operator()(void)
0x18005182a  nop
0x18005182b  mov     eax, 1
0x180051830  mov     rcx, [rbp+57h+var_20]
0x180051834  xor     rcx, rsp; StackCookie
0x180051837  call    __security_check_cookie
0x18005183c  mov     rbx, [rsp+0F0h+arg_10]
0x180051844  add     rsp, 0E0h
0x18005184b  pop     r14
0x18005184d  pop     rsi
0x18005184e  pop     rbp
0x18005184f  retn
```
