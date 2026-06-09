# CIndexSettingsPage::_OnCommand(uint,HWND__ *,uint)

- ea: `0x1800198d4`
- end: `0x180019c76`
- name: `?_OnCommand@CIndexSettingsPage@@AEAA_JIPEAUHWND__@@I@Z`
- size: `930`
- prototype: `__int64 __fastcall(CIndexSettingsPage *__hidden this, unsigned int, HWND, unsigned int)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800192dc`

## callees

- `0x18000cfa0`
- `0x180018a6c`
- `0x180018e68`
- `0x18001908c`
- `0x1800193c8`
- `0x180019598`
- `0x1800198d4`
- `0x180019f80`
- `0x18001ec6c`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180019bdf`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180019bdf`
- `ntdll!WinSqmIncrementDWORD` at `0x180019a23`
- `ntdll!WinSqmIncrementDWORD` at `0x180019c5b`
- `ntdll!WinSqmIncrementDWORD` at `0x180019a23`
- `ntdll!WinSqmIncrementDWORD` at `0x180019c5b`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!GetParent` at `0x1800199d7`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!GetParent` at `0x1800199d7`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!PostMessageW` at `0x1800199ec`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!PostMessageW` at `0x1800199ec`
- `USER32!CheckDlgButton` at `0x1800199b7`
- `USER32!CheckDlgButton` at `0x180019ae3`
- `USER32!CheckDlgButton` at `0x180019b87`
- `USER32!CheckDlgButton` at `0x180019c3e`
- `USER32!CheckDlgButton` at `0x1800199b7`
- `USER32!CheckDlgButton` at `0x180019ae3`
- `USER32!CheckDlgButton` at `0x180019b87`
- `USER32!CheckDlgButton` at `0x180019c3e`
- `USER32!IsDlgButtonChecked` at `0x180019955`
- `USER32!IsDlgButtonChecked` at `0x180019acf`
- `USER32!IsDlgButtonChecked` at `0x180019b32`
- `USER32!IsDlgButtonChecked` at `0x180019955`
- `USER32!IsDlgButtonChecked` at `0x180019acf`
- `USER32!IsDlgButtonChecked` at `0x180019b32`

## pseudocode

```c
__int64 __fastcall CIndexSettingsPage::_OnCommand(CIndexSettingsPage *this, int a2, HWND a3, int a4)
{
  int v5; // edx
  int v6; // edx
  int v7; // edx
  int v8; // edx
  unsigned int v9; // r9d
  HWND v10; // rcx
  UINT v11; // r8d
  __int64 v12; // rax
  HWND Parent; // rax
  UINT v14; // eax
  __int64 v15; // rdx
  HWND v16; // rcx
  unsigned int v17; // r9d
  HWND v18; // rcx
  unsigned __int16 v19; // cx
  unsigned int v20; // r9d
  HWND v21; // rcx
  bool v22; // zf
  HWND v24; // [rsp+60h] [rbp+30h] BYREF
  unsigned int v25; // [rsp+68h] [rbp+38h] BYREF

  v24 = a3;
  if ( a4 )
    return 0;
  v5 = a2 - 902;
  if ( !v5 )
  {
    if ( !*((_DWORD *)this + 19) )
    {
LABEL_50:
      v15 = 4129;
LABEL_51:
      WinSqmIncrementDWORD(0, v15, 1);
      return 0;
    }
    v16 = *(HWND *)this;
    if ( !*((_DWORD *)this + 12) )
    {
      ShowAMessageBox(v16, 0x261u, 0x391u, 0, 0x40u, 0);
      goto LABEL_50;
    }
    if ( IsDlgButtonChecked(v16, 902) == 1 )
    {
      v25 = 1;
      if ( *((_DWORD *)this + 14) )
      {
        v18 = *(HWND *)this;
        *((_DWORD *)this + 14) = 0;
        if ( (int)ShowAMessageBox(v18, 0x6A5u, 0x6A7u, v17, 0x131u, &v25) < 0 || v25 != 1 )
          goto LABEL_50;
      }
      CheckDlgButton(*(HWND *)this, 902, 0);
      LOBYTE(v25) = 0;
      goto LABEL_49;
    }
    v19 = *((_WORD *)this + 40);
    LOBYTE(v25) = 0;
    LOBYTE(v24) = 0;
    if ( (int)IsPathBitlocked(v19, (bool *)&v25, (bool *)&v24) >= 0
      && (_BYTE)v25
      && (!*((_WORD *)this + 300) || CompareStringW(0x7Fu, 1u, (PCNZWCH)this + 40, -1, (PCNZWCH)this + 300, -1) == 2) )
    {
      v25 = 1;
      if ( !*((_DWORD *)this + 14) )
      {
LABEL_48:
        CheckDlgButton(*(HWND *)this, 902, 1u);
        LOBYTE(v25) = 1;
LABEL_49:
        SearchOptionsTelemetry::IndexEncryptedClicked<bool>(&v25);
        goto LABEL_50;
      }
      v21 = *(HWND *)this;
      *((_DWORD *)this + 14) = 0;
      if ( (int)ShowAMessageBox(v21, 0x6A5u, 0x6A6u, v20, 0x131u, &v25) < 0 )
        goto LABEL_50;
      v22 = v25 == 1;
    }
    else
    {
      v22 = (unsigned int)CIndexSettingsPage::_DisplayBitlockerWarning(this, 1, 1) == 0;
    }
    if ( !v22 )
      goto LABEL_50;
    goto LABEL_48;
  }
  v6 = v5 - 1;
  if ( !v6 )
  {
    if ( *((_DWORD *)this + 19) )
    {
      if ( *((_DWORD *)this + 11) )
      {
        v25 = 1;
        if ( !*((_DWORD *)this + 13)
          || (*((_DWORD *)this + 13) = 0, (int)ShowAMessageBox(*(HWND *)this, 0x26Du, 0x26Eu, 0, 0x131u, &v25) >= 0)
          && v25 == 1 )
        {
          v14 = IsDlgButtonChecked(*(HWND *)this, 903);
          CheckDlgButton(*(HWND *)this, 903, v14 != 1);
        }
      }
      else
      {
        ShowAMessageBox(*(HWND *)this, 0x261u, 0x392u, 0, 0x40u, 0);
      }
    }
    v15 = 4130;
    goto LABEL_51;
  }
  v7 = v6 - 3;
  if ( v7 )
  {
    v8 = v7 - 5;
    if ( !v8 )
    {
      v12 = *((_QWORD *)this + 1);
      *(_QWORD *)v12 = 2;
      *(_DWORD *)(v12 + 8) = 1;
      Parent = GetParent(*(HWND *)this);
      PostMessageW(Parent, 0x471u, 3u, 0);
      return 0;
    }
    if ( v8 == 6
      && (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_46595479>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_46595479>::GetImpl'::`2'::impl)
      && *((_DWORD *)this + 19) )
    {
      if ( IsDlgButtonChecked(*(HWND *)this, 917) == 1 )
      {
        v11 = 0;
        goto LABEL_15;
      }
      v25 = 1;
      if ( !*((_DWORD *)this + 18)
        || (v10 = *(HWND *)this,
            *((_DWORD *)this + 18) = 0,
            (int)ShowAMessageBox(v10, 0x290u, 0x291u, v9, 0x141u, &v25) >= 0)
        && v25 == 1 )
      {
        v11 = 1;
LABEL_15:
        *(_DWORD *)(*((_QWORD *)this + 1) + 12LL) = 1;
        CheckDlgButton(*(HWND *)this, 917, v11);
      }
    }
  }
  else if ( *((_DWORD *)this + 19) )
  {
    if ( *((_DWORD *)this + 10) )
    {
      if ( !(unsigned int)CIndexSettingsPage::_BrowseToNewDataLocation((HWND *)this) )
      {
        CIndexSettingsPage::_DisplayNewDataDirectory(this);
        WinSqmIncrementDWORD(0, 4132, 1);
      }
      SearchOptionsTelemetry::NewIndexLocation();
    }
    else
    {
      ShowAMessageBox(*(HWND *)this, 0x261u, 0x263u, 0, 0x40u, 0);
    }
  }
  return 0;
}

```

## disassembly

```asm
0x1800198d4  mov     [rsp-18h+arg_0], rbx
0x1800198d9  mov     [rsp-18h+arg_8], rsi
0x1800198de  mov     [rsp-18h+arg_10], r8
0x1800198e3  push    rbp
0x1800198e4  push    rdi
0x1800198e5  push    r14
0x1800198e7  mov     rbp, rsp
0x1800198ea  sub     rsp, 30h
0x1800198ee  xor     r14d, r14d
0x1800198f1  mov     rbx, rcx
0x1800198f4  test    r9d, r9d
0x1800198f7  jnz     loc_180019C61
0x1800198fd  sub     edx, 386h
0x180019903  jz      loc_180019AF3
0x180019909  sub     edx, 1
0x18001990c  jz      loc_180019A56
0x180019912  sub     edx, 3
0x180019915  jz      loc_1800199F7
0x18001991b  sub     edx, 5
0x18001991e  jz      loc_1800199C2
0x180019924  cmp     edx, 6
0x180019927  jnz     loc_180019C61
0x18001992d  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_46595479@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_46595479@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_46595479> `wil::Feature<__WilFeatureTraits_Feature_46595479>::GetImpl(void)'::`2'::impl
0x180019934  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_46595479@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_46595479>::__private_IsEnabled(void)
0x180019939  test    al, al
0x18001993b  jz      loc_180019C61
0x180019941  cmp     [rbx+4Ch], r14d
0x180019945  jz      loc_180019C61
0x18001994b  mov     rcx, [rbx]; hDlg
0x18001994e  mov     esi, 395h
0x180019953  mov     edx, esi; nIDButton
0x180019955  call    cs:__imp_IsDlgButtonChecked
0x18001995b  lea     edi, [r14+1]
0x18001995f  cmp     eax, edi
0x180019961  jz      short loc_1800199A8
0x180019963  mov     [rbp+arg_18], edi
0x180019966  cmp     [rbx+48h], r14d
0x18001996a  jz      short loc_1800199A3
0x18001996c  mov     rcx, [rbx]; HWND
0x18001996f  lea     rax, [rbp+arg_18]
0x180019973  mov     edx, 290h; unsigned int
0x180019978  mov     qword ptr [rsp+30h+cchCount2], rax; unsigned int *
0x18001997d  mov     [rbx+48h], r14d
0x180019981  mov     dword ptr [rsp+30h+lpString2], 141h; unsigned int
0x180019989  lea     r8d, [rdx+1]; unsigned int
0x18001998d  call    ?ShowAMessageBox@@YAJPEAUHWND__@@IIIIPEAI@Z; ShowAMessageBox(HWND__ *,uint,uint,uint,uint,uint *)
0x180019992  test    eax, eax
0x180019994  js      loc_180019C61
0x18001999a  cmp     [rbp+arg_18], edi
0x18001999d  jnz     loc_180019C61
0x1800199a3  mov     r8d, edi
0x1800199a6  jmp     short loc_1800199AB
0x1800199a8  xor     r8d, r8d; uCheck
0x1800199ab  mov     rax, [rbx+8]
0x1800199af  mov     edx, esi; nIDButton
0x1800199b1  mov     [rax+0Ch], edi
0x1800199b4  mov     rcx, [rbx]; hDlg
0x1800199b7  call    cs:__imp_CheckDlgButton
0x1800199bd  jmp     loc_180019C61
0x1800199c2  mov     rax, [rcx+8]
0x1800199c6  mov     qword ptr [rax], 2
0x1800199cd  mov     dword ptr [rax+8], 1
0x1800199d4  mov     rcx, [rcx]; hWnd
0x1800199d7  call    cs:__imp_GetParent
0x1800199dd  xor     r9d, r9d; lParam
0x1800199e0  mov     edx, 471h; Msg
0x1800199e5  mov     rcx, rax; hWnd
0x1800199e8  lea     r8d, [r9+3]; wParam
0x1800199ec  call    cs:__imp_PostMessageW
0x1800199f2  jmp     loc_180019C61
0x1800199f7  cmp     [rcx+4Ch], r14d
0x1800199fb  jz      loc_180019C61
0x180019a01  cmp     [rcx+28h], r14d
0x180019a05  jz      short loc_180019A33
0x180019a07  call    ?_BrowseToNewDataLocation@CIndexSettingsPage@@AEAAJXZ; CIndexSettingsPage::_BrowseToNewDataLocation(void)
0x180019a0c  test    eax, eax
0x180019a0e  jnz     short loc_180019A29
0x180019a10  mov     rcx, rbx; this
0x180019a13  call    ?_DisplayNewDataDirectory@CIndexSettingsPage@@AEAAJXZ; CIndexSettingsPage::_DisplayNewDataDirectory(void)
0x180019a18  xor     ecx, ecx
0x180019a1a  mov     edx, 1024h
0x180019a1f  lea     r8d, [rcx+1]
0x180019a23  call    cs:__imp_WinSqmIncrementDWORD
0x180019a29  call    ?NewIndexLocation@SearchOptionsTelemetry@@SAXXZ; SearchOptionsTelemetry::NewIndexLocation(void)
0x180019a2e  jmp     loc_180019C61
0x180019a33  mov     rcx, [rcx]; HWND
0x180019a36  mov     edx, 261h; unsigned int
0x180019a3b  mov     qword ptr [rsp+30h+cchCount2], r14; unsigned int *
0x180019a40  mov     dword ptr [rsp+30h+lpString2], 40h ; '@'; unsigned int
0x180019a48  lea     r8d, [rdx+2]; unsigned int
0x180019a4c  call    ?ShowAMessageBox@@YAJPEAUHWND__@@IIIIPEAI@Z; ShowAMessageBox(HWND__ *,uint,uint,uint,uint,uint *)
0x180019a51  jmp     loc_180019C61
0x180019a56  mov     edi, 1
0x180019a5b  cmp     [rcx+4Ch], r14d
0x180019a5f  jz      loc_180019AE9
0x180019a65  cmp     [rcx+2Ch], r14d
0x180019a69  jnz     short loc_180019A8D
0x180019a6b  mov     rcx, [rcx]; HWND
0x180019a6e  mov     edx, 261h; unsigned int
0x180019a73  mov     qword ptr [rsp+30h+cchCount2], r14; unsigned int *
0x180019a78  mov     r8d, 392h; unsigned int
0x180019a7e  mov     dword ptr [rsp+30h+lpString2], 40h ; '@'; unsigned int
0x180019a86  call    ?ShowAMessageBox@@YAJPEAUHWND__@@IIIIPEAI@Z; ShowAMessageBox(HWND__ *,uint,uint,uint,uint,uint *)
0x180019a8b  jmp     short loc_180019AE9
0x180019a8d  mov     [rbp+arg_18], edi
0x180019a90  cmp     [rcx+34h], r14d
0x180019a94  jz      short loc_180019AC5
0x180019a96  mov     edx, 26Dh; unsigned int
0x180019a9b  mov     [rcx+34h], r14d
0x180019a9f  mov     rcx, [rcx]; HWND
0x180019aa2  lea     rax, [rbp+arg_18]
0x180019aa6  mov     qword ptr [rsp+30h+cchCount2], rax; unsigned int *
0x180019aab  mov     dword ptr [rsp+30h+lpString2], 131h; unsigned int
0x180019ab3  lea     r8d, [rdx+1]; unsigned int
0x180019ab7  call    ?ShowAMessageBox@@YAJPEAUHWND__@@IIIIPEAI@Z; ShowAMessageBox(HWND__ *,uint,uint,uint,uint,uint *)
0x180019abc  test    eax, eax
0x180019abe  js      short loc_180019AE9
0x180019ac0  cmp     [rbp+arg_18], edi
0x180019ac3  jnz     short loc_180019AE9
0x180019ac5  mov     rcx, [rbx]; hDlg
0x180019ac8  mov     esi, 387h
0x180019acd  mov     edx, esi; nIDButton
0x180019acf  call    cs:__imp_IsDlgButtonChecked
0x180019ad5  mov     rcx, [rbx]; hDlg
0x180019ad8  mov     r8d, r14d
0x180019adb  cmp     eax, edi
0x180019add  mov     edx, esi; nIDButton
0x180019adf  setnz   r8b; uCheck
0x180019ae3  call    cs:__imp_CheckDlgButton
0x180019ae9  mov     edx, 1022h
0x180019aee  jmp     loc_180019C56
0x180019af3  mov     edi, 1
0x180019af8  cmp     [rcx+4Ch], r14d
0x180019afc  jz      loc_180019C51
0x180019b02  mov     rcx, [rcx]; HWND
0x180019b05  cmp     [rbx+30h], r14d
0x180019b09  jnz     short loc_180019B2D
0x180019b0b  mov     qword ptr [rsp+30h+cchCount2], r14; unsigned int *
0x180019b10  mov     edx, 261h; unsigned int
0x180019b15  mov     r8d, 391h; unsigned int
0x180019b1b  mov     dword ptr [rsp+30h+lpString2], 40h ; '@'; unsigned int
0x180019b23  call    ?ShowAMessageBox@@YAJPEAUHWND__@@IIIIPEAI@Z; ShowAMessageBox(HWND__ *,uint,uint,uint,uint,uint *)
0x180019b28  jmp     loc_180019C51
0x180019b2d  mov     edx, 386h; nIDButton
0x180019b32  call    cs:__imp_IsDlgButtonChecked
0x180019b38  cmp     eax, edi
0x180019b3a  jnz     short loc_180019B96
0x180019b3c  mov     [rbp+arg_18], edi
0x180019b3f  cmp     [rbx+38h], r14d
0x180019b43  jz      short loc_180019B7C
0x180019b45  mov     rcx, [rbx]; HWND
0x180019b48  lea     rax, [rbp+arg_18]
0x180019b4c  mov     edx, 6A5h; unsigned int
0x180019b51  mov     qword ptr [rsp+30h+cchCount2], rax; unsigned int *
0x180019b56  mov     [rbx+38h], r14d
0x180019b5a  mov     dword ptr [rsp+30h+lpString2], 131h; unsigned int
0x180019b62  lea     r8d, [rdx+2]; unsigned int
0x180019b66  call    ?ShowAMessageBox@@YAJPEAUHWND__@@IIIIPEAI@Z; ShowAMessageBox(HWND__ *,uint,uint,uint,uint,uint *)
0x180019b6b  test    eax, eax
0x180019b6d  js      loc_180019C51
0x180019b73  cmp     [rbp+arg_18], edi
0x180019b76  jnz     loc_180019C51
0x180019b7c  mov     rcx, [rbx]; hDlg
0x180019b7f  xor     r8d, r8d; uCheck
0x180019b82  mov     edx, 386h; nIDButton
0x180019b87  call    cs:__imp_CheckDlgButton
0x180019b8d  mov     byte ptr [rbp+arg_18], r14b
0x180019b91  jmp     loc_180019C48
0x180019b96  movzx   ecx, word ptr [rbx+50h]; unsigned __int16
0x180019b9a  lea     r8, [rbp+arg_10]; bool *
0x180019b9e  lea     rdx, [rbp+arg_18]; bool *
0x180019ba2  mov     byte ptr [rbp+arg_18], r14b
0x180019ba6  mov     byte ptr [rbp+arg_10], r14b
0x180019baa  call    ?IsPathBitlocked@@YAJGPEA_N0@Z; IsPathBitlocked(ushort,bool *,bool *)
0x180019baf  test    eax, eax
0x180019bb1  js      short loc_180019C22
0x180019bb3  cmp     byte ptr [rbp+arg_18], r14b
0x180019bb7  jz      short loc_180019C22
0x180019bb9  lea     rax, [rbx+258h]
0x180019bc0  cmp     [rax], r14w
0x180019bc4  jz      short loc_180019BEA
0x180019bc6  or      r9d, 0FFFFFFFFh; cchCount1
0x180019bca  lea     r8, [rbx+50h]; lpString1
0x180019bce  mov     [rsp+30h+cchCount2], r9d; cchCount2
0x180019bd3  mov     edx, edi; dwCmpFlags
0x180019bd5  mov     ecx, 7Fh; Locale
0x180019bda  mov     [rsp+30h+lpString2], rax; lpString2
0x180019bdf  call    cs:__imp_CompareStringW
0x180019be5  cmp     eax, 2
0x180019be8  jnz     short loc_180019C22
0x180019bea  mov     [rbp+arg_18], edi
0x180019bed  cmp     [rbx+38h], r14d
0x180019bf1  jz      short loc_180019C33
0x180019bf3  mov     rcx, [rbx]; HWND
0x180019bf6  lea     rax, [rbp+arg_18]
0x180019bfa  mov     edx, 6A5h; unsigned int
0x180019bff  mov     qword ptr [rsp+30h+cchCount2], rax; unsigned int *
0x180019c04  mov     [rbx+38h], r14d
0x180019c08  mov     dword ptr [rsp+30h+lpString2], 131h; unsigned int
0x180019c10  lea     r8d, [rdx+1]; unsigned int
0x180019c14  call    ?ShowAMessageBox@@YAJPEAUHWND__@@IIIIPEAI@Z; ShowAMessageBox(HWND__ *,uint,uint,uint,uint,uint *)
0x180019c19  test    eax, eax
0x180019c1b  js      short loc_180019C51
0x180019c1d  cmp     [rbp+arg_18], edi
0x180019c20  jmp     short loc_180019C31
0x180019c22  mov     r8d, edi; int
0x180019c25  mov     edx, edi; int
0x180019c27  mov     rcx, rbx; this
0x180019c2a  call    ?_DisplayBitlockerWarning@CIndexSettingsPage@@AEAAJHH@Z; CIndexSettingsPage::_DisplayBitlockerWarning(int,int)
0x180019c2f  test    eax, eax
0x180019c31  jnz     short loc_180019C51
0x180019c33  mov     rcx, [rbx]; hDlg
0x180019c36  mov     r8d, edi; uCheck
0x180019c39  mov     edx, 386h; nIDButton
0x180019c3e  call    cs:__imp_CheckDlgButton
0x180019c44  mov     byte ptr [rbp+arg_18], dil
0x180019c48  lea     rcx, [rbp+arg_18]
0x180019c4c  call    ??$IndexEncryptedClicked@_N@SearchOptionsTelemetry@@SAX$$QEA_N@Z; SearchOptionsTelemetry::IndexEncryptedClicked<bool>(bool &&)
0x180019c51  mov     edx, 1021h
0x180019c56  mov     r8d, edi
0x180019c59  xor     ecx, ecx
0x180019c5b  call    cs:__imp_WinSqmIncrementDWORD
0x180019c61  mov     rbx, [rsp+30h+arg_0]
0x180019c66  xor     eax, eax
0x180019c68  mov     rsi, [rsp+30h+arg_8]
0x180019c6d  add     rsp, 30h
0x180019c71  pop     r14
0x180019c73  pop     rdi
0x180019c74  pop     rbp
0x180019c75  retn
```
