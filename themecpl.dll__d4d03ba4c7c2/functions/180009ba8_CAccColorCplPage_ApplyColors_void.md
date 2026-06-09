# CAccColorCplPage::_ApplyColors(void)

- ea: `0x180009ba8`
- end: `0x18000a118`
- name: `?_ApplyColors@CAccColorCplPage@@AEAAXXZ`
- size: `1392`
- prototype: `void __fastcall(CAccColorCplPage *__hidden this)`
- caller_count: `2`
- callee_count: `8`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180009110`
- `0x1800093a0`

## callees

- `0x180002280`
- `0x180009884`
- `0x180009a98`
- `0x180009ba8`
- `0x18000a17c`
- `0x18000ad28`
- `0x18000af30`
- `0x180057010`

## import_xrefs

- `SHLWAPI!PathFileExistsW` at `0x180009e9f`
- `SHLWAPI!PathFileExistsW` at `0x180009e9f`
- `SHLWAPI!__imp_SHExpandEnvironmentStringsW` at `0x180009e7f`
- `SHLWAPI!__imp_SHExpandEnvironmentStringsW` at `0x180009e7f`
- `UxTheme!__imp_SetSystemVisualStyle` at `0x180009ec4`
- `UxTheme!__imp_SetSystemVisualStyle` at `0x180009ec4`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180009f4e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180009f4e`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180009d18`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180009d18`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180009d4d`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180009d76`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180009d4d`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180009d76`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180009f2a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180009f3d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180009f2a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180009f3d`
- `dwmapi!__imp_DwmpGetColorizationParameters` at `0x180009edf`
- `dwmapi!__imp_DwmpGetColorizationParameters` at `0x180009edf`
- `dwmapi!__imp_DwmpSetColorizationParameters` at `0x180009f1b`
- `dwmapi!__imp_DwmpSetColorizationParameters` at `0x180009f1b`
- `USER32!GetSysColor` at `0x18000a01d`
- `USER32!GetSysColor` at `0x18000a01d`
- `USER32!SetCursor` at `0x180009cd5`
- `USER32!SetCursor` at `0x18000a039`
- `USER32!SetCursor` at `0x180009cd5`
- `USER32!SetCursor` at `0x18000a039`
- `USER32!LoadCursorW` at `0x180009cc6`
- `USER32!LoadCursorW` at `0x180009cc6`
- `USER32!SetSysColors` at `0x180009e62`
- `USER32!SetSysColors` at `0x180009e62`
- `USER32!SendNotifyMessageW` at `0x18000a0ae`
- `USER32!SendNotifyMessageW` at `0x18000a0ae`
- `DUI70!?SetEnabled@Element@DirectUI@@QEAAJ_N@Z` at `0x180009c78`
- `DUI70!?SetEnabled@Element@DirectUI@@QEAAJ_N@Z` at `0x180009c8d`
- `DUI70!?SetEnabled@Element@DirectUI@@QEAAJ_N@Z` at `0x180009ca2`
- `DUI70!?SetEnabled@Element@DirectUI@@QEAAJ_N@Z` at `0x180009cb3`
- `DUI70!?SetEnabled@Element@DirectUI@@QEAAJ_N@Z` at `0x18000a04a`
- `DUI70!?SetEnabled@Element@DirectUI@@QEAAJ_N@Z` at `0x18000a05f`
- `DUI70!?SetEnabled@Element@DirectUI@@QEAAJ_N@Z` at `0x18000a08a`
- `DUI70!?SetEnabled@Element@DirectUI@@QEAAJ_N@Z` at `0x180009c78`
- `DUI70!?SetEnabled@Element@DirectUI@@QEAAJ_N@Z` at `0x180009c8d`
- `DUI70!?SetEnabled@Element@DirectUI@@QEAAJ_N@Z` at `0x180009ca2`
- `DUI70!?SetEnabled@Element@DirectUI@@QEAAJ_N@Z` at `0x180009cb3`
- `DUI70!?SetEnabled@Element@DirectUI@@QEAAJ_N@Z` at `0x18000a04a`
- `DUI70!?SetEnabled@Element@DirectUI@@QEAAJ_N@Z` at `0x18000a05f`
- `DUI70!?SetEnabled@Element@DirectUI@@QEAAJ_N@Z` at `0x18000a08a`

## pseudocode

```c
void __fastcall CAccColorCplPage::_ApplyColors(CAccColorCplPage *this)
{
  unsigned int v1; // r14d
  int v2; // r15d
  __int64 v3; // r8
  __int64 v4; // rdx
  DirectUI::Element **v5; // r13
  HCURSOR CursorW; // rax
  bool v7; // bl
  unsigned int v8; // r12d
  int *v9; // rdi
  unsigned int *v10; // rsi
  signed int v11; // edx
  CAccColorCplPage *v12; // rcx
  unsigned int v13; // eax
  unsigned int v14; // eax
  unsigned int v15; // eax
  int v16; // eax
  CAccColorCplPage *v17; // rcx
  unsigned int i; // r13d
  struct DirectUI::Element *v19; // rdi
  CAccColorCplPage *v20; // rcx
  struct DirectUI::Element *v21; // r14
  HWND v22; // rax
  CAccColorCplPage *v23; // rcx
  HWND v24; // rax
  CAccColorCplPage *v25; // rcx
  struct DirectUI::Element *v26; // rbx
  DWORD SysColor; // eax
  CAccColorCplPage *v28; // rcx
  __int64 v29; // rcx
  __int64 v30; // r8
  unsigned int v31; // [rsp+48h] [rbp-B8h]
  unsigned int v32; // [rsp+48h] [rbp-B8h]
  bool v33; // [rsp+50h] [rbp-B0h] BYREF
  bool v34[7]; // [rsp+51h] [rbp-AFh] BYREF
  int v35; // [rsp+58h] [rbp-A8h] BYREF
  HKEY hKey; // [rsp+60h] [rbp-A0h] BYREF
  CAccColorCplPage *v37; // [rsp+68h] [rbp-98h]
  HCURSOR hCursor; // [rsp+70h] [rbp-90h]
  __int128 v39; // [rsp+80h] [rbp-80h] BYREF
  __int128 v40; // [rsp+90h] [rbp-70h]
  WCHAR pszPath[264]; // [rsp+A0h] [rbp-60h] BYREF

  v1 = 0;
  v37 = this;
  v2 = 0;
  v3 = 0;
  v4 = 0;
  v5 = (DirectUI::Element **)this;
  do
  {
    if ( *(struct CPL_SYSTEM_COLOR_ROW near **)((char *)&CAccColorCplPage::s_rgSystemColorRows + v4 + 24)
      && *((_BYTE *)&CAccColorCplPage::s_rgSystemColorRows + v4 + 40) )
    {
      this = (CAccColorCplPage *)*(unsigned int *)((char *)&CAccColorCplPage::s_rgSystemColorRows + v4 + 32);
      v2 |= 1 << (char)this;
    }
    if ( *(struct CPL_SYSTEM_COLOR_ROW near **)((char *)&CAccColorCplPage::s_rgSystemColorRows + v4 + 48)
      && *((_BYTE *)&CAccColorCplPage::s_rgSystemColorRows + v4 + 64) )
    {
      this = (CAccColorCplPage *)*(unsigned int *)((char *)&CAccColorCplPage::s_rgSystemColorRows + v4 + 56);
      v2 |= 1 << (char)this;
    }
    ++v3;
    v4 += 72;
  }
  while ( v3 != 8 );
  if ( (Microsoft_Windows_ThemeCPLEnableBits & 8) != 0 )
  {
    v35 = v2;
    *(_QWORD *)&v40 = &v35;
    *((_QWORD *)&v40 + 1) = 4;
    McGenEventWrite_EventWriteTransfer(this, ThemeCPL_AccColorCplPageApply_Start, 8, 2, &v39);
  }
  DirectUI::Element::SetEnabled(v5[26], 0);
  DirectUI::Element::SetEnabled(v5[27], 0);
  DirectUI::Element::SetEnabled(v5[28], 0);
  DirectUI::Element::SetEnabled((DirectUI::Element *)v5, 0);
  CursorW = LoadCursorW(0, (LPCWSTR)0x7F02);
  v7 = 0;
  v34[0] = 0;
  hCursor = SetCursor(CursorW);
  v33 = 0;
  hKey = 0;
  if ( !RegOpenKeyExW(HKEY_CURRENT_USER, L"Control Panel\\Colors", 0, 0x20006u, &hKey) )
  {
    v8 = -1;
    v35 = -1;
    if ( is_mul_ok(0x10u, 4u) )
    {
      v9 = (int *)LocalAlloc(0x40u, 0x40u);
      if ( v9 )
      {
        if ( is_mul_ok(0x10u, 4u) )
        {
          v10 = (unsigned int *)LocalAlloc(0x40u, 0x40u);
          v11 = v10 == 0 ? 0x8007000E : 0;
        }
        else
        {
          v10 = 0;
          v11 = -2147024362;
        }
        if ( v11 >= 0 )
        {
          v12 = 0;
          do
          {
            v13 = v1;
            if ( !*((_BYTE *)&CAccColorCplPage::s_rgSystemColorRows + 72 * v1 + 4) )
              v13 = v8;
            v8 = v13;
            v14 = CAccColorCplPage::_ApplyColor(
                    v12,
                    hKey,
                    (struct SYSTEM_COLOR_STATE *)&(&off_18006F228)[9 * v1],
                    (unsigned int)v12,
                    (bool *)&qword_18006F230[9 * v1 + 1],
                    &v33,
                    v34,
                    v9,
                    v10,
                    v31);
            v15 = CAccColorCplPage::_ApplyColor(
                    (CAccColorCplPage *)&qword_18006F230[9 * v1 + 4],
                    hKey,
                    (struct SYSTEM_COLOR_STATE *)&qword_18006F230[9 * v1 + 2],
                    v14,
                    (bool *)&qword_18006F230[9 * v1 + 4],
                    &v33,
                    v34,
                    v9,
                    v10,
                    v32);
            ++v1;
            v12 = (CAccColorCplPage *)v15;
          }
          while ( v1 < 8 );
          v35 = v8;
          SetSysColors(v15, v9, v10);
          v16 = SHExpandEnvironmentStringsW(L"%SystemRoot%\\Resources\\Themes\\Aero\\AeroLite.msstyles", pszPath, 260);
          v5 = (DirectUI::Element **)v37;
          if ( v16 && PathFileExistsW(pszPath) )
          {
            SetSystemVisualStyle(pszPath, L"NormalColor", L"NormalSize", 0);
            v39 = 0;
            v40 = 0;
            DwmpGetColorizationParameters(&v39);
            LODWORD(v39) = 2130706432;
            *(_QWORD *)((char *)&v39 + 4) = 0x357F000000LL;
            LODWORD(v40) = 37;
            *((_QWORD *)&v40 + 1) = 0x200000002LL;
            HIDWORD(v39) = 10;
            DwmpSetColorizationParameters(&v39, 0);
          }
          LocalFree(v10);
          v7 = v33;
        }
        LocalFree(v9);
      }
    }
    RegCloseKey(hKey);
    if ( v7 )
    {
      for ( i = 0; i < 8; ++i )
      {
        v19 = CAccColorCplPage::_ElementAtRow(v17, L"LeftButton", i);
        v21 = CAccColorCplPage::_ElementAtRow(v20, L"RightButton", i);
        v22 = (HWND)(*(__int64 (__fastcall **)(struct DirectUI::Element *))(*(_QWORD *)v19 + 360LL))(v19);
        CAccColorCplPage::_AddColorSwatchToButton(v23, v22, (struct SYSTEM_COLOR_STATE *)&(&off_18006F228)[9 * i]);
        v24 = (HWND)(*(__int64 (__fastcall **)(struct DirectUI::Element *))(*(_QWORD *)v21 + 360LL))(v21);
        CAccColorCplPage::_AddColorSwatchToButton(v25, v24, (struct SYSTEM_COLOR_STATE *)&qword_18006F230[9 * i + 2]);
      }
      v5 = (DirectUI::Element **)v37;
      v8 = v35;
    }
    if ( v34[0] && v8 != -1 )
    {
      v26 = CAccColorCplPage::_ElementAtRow(v17, L"PreviewBoxText", v8);
      SysColor = GetSysColor(8);
      CAccColorCplPage::_SetForegroundColorHelper(v28, v26, SysColor);
    }
  }
  SetCursor(hCursor);
  DirectUI::Element::SetEnabled((DirectUI::Element *)v5, 1);
  DirectUI::Element::SetEnabled(v5[26], 1);
  (*(void (__fastcall **)(DirectUI::Element *))(*(_QWORD *)v5[26] + 168LL))(v5[26]);
  DirectUI::Element::SetEnabled(v5[27], 1);
  if ( v2 )
    SendNotifyMessageW(HWND_BROADCAST, 0x1Au, 0, (LPARAM)L"WindowsThemeElement");
  if ( (Microsoft_Windows_ThemeCPLEnableBits & 8) != 0 )
  {
    v35 = v2;
    *(_QWORD *)&v40 = &v35;
    *((_QWORD *)&v40 + 1) = 4;
    McGenEventWrite_EventWriteTransfer(v29, ThemeCPL_AccColorCplPageApply_Stop, v30, 2, &v39);
  }
}

```

## disassembly

```asm
0x180009ba8  push    rbp
0x180009baa  push    rbx
0x180009bab  push    rsi
0x180009bac  push    rdi
0x180009bad  push    r12
0x180009baf  push    r13
0x180009bb1  push    r14
0x180009bb3  push    r15
0x180009bb5  lea     rbp, [rsp-1C8h]
0x180009bbd  sub     rsp, 2C8h
0x180009bc4  mov     rax, cs:__security_cookie
0x180009bcb  xor     rax, rsp
0x180009bce  mov     [rbp+200h+var_50], rax
0x180009bd5  xor     r14d, r14d
0x180009bd8  mov     [rsp+300h+var_298], rcx
0x180009bdd  mov     r15d, r14d
0x180009be0  lea     r9, ?s_rgSystemColorRows@CAccColorCplPage@@0PAUCPL_SYSTEM_COLOR_ROW@@A; CPL_SYSTEM_COLOR_ROW near * CAccColorCplPage::s_rgSystemColorRows
0x180009be7  mov     r8d, r14d
0x180009bea  mov     edx, r14d
0x180009bed  mov     r13, rcx
0x180009bf0  cmp     [rdx+r9+18h], r14
0x180009bf5  jz      short loc_180009C0D
0x180009bf7  cmp     [rdx+r9+28h], r14b
0x180009bfc  jz      short loc_180009C0D
0x180009bfe  mov     ecx, [rdx+r9+20h]
0x180009c03  mov     eax, 1
0x180009c08  shl     eax, cl
0x180009c0a  or      r15d, eax
0x180009c0d  cmp     [rdx+r9+30h], r14
0x180009c12  jz      short loc_180009C2A
0x180009c14  cmp     [rdx+r9+40h], r14b
0x180009c19  jz      short loc_180009C2A
0x180009c1b  mov     ecx, [rdx+r9+38h]
0x180009c20  mov     eax, 1
0x180009c25  shl     eax, cl
0x180009c27  or      r15d, eax
0x180009c2a  inc     r8
0x180009c2d  add     rdx, 48h ; 'H'
0x180009c31  cmp     r8, 8
0x180009c35  jnz     short loc_180009BF0
0x180009c37  test    byte ptr cs:Microsoft_Windows_ThemeCPLEnableBits, r8b
0x180009c3e  jz      short loc_180009C6F
0x180009c40  lea     rax, [rsp+300h+var_2A8]
0x180009c45  mov     [rsp+300h+var_2A8], r15d
0x180009c4a  mov     qword ptr [rbp+200h+var_270], rax
0x180009c4e  lea     r9d, [r8-6]
0x180009c52  lea     rax, [rbp+200h+var_280]
0x180009c56  mov     qword ptr [rbp+200h+var_270+8], 4
0x180009c5e  lea     rdx, ThemeCPL_AccColorCplPageApply_Start
0x180009c65  mov     [rsp+300h+phkResult], rax
0x180009c6a  call    McGenEventWrite_EventWriteTransfer
0x180009c6f  mov     rcx, [r13+0D0h]
0x180009c76  xor     edx, edx
0x180009c78  call    cs:__imp_?SetEnabled@Element@DirectUI@@QEAAJ_N@Z; DirectUI::Element::SetEnabled(bool)
0x180009c7f  nop     dword ptr [rax+rax+00h]
0x180009c84  mov     rcx, [r13+0D8h]
0x180009c8b  xor     edx, edx
0x180009c8d  call    cs:__imp_?SetEnabled@Element@DirectUI@@QEAAJ_N@Z; DirectUI::Element::SetEnabled(bool)
0x180009c94  nop     dword ptr [rax+rax+00h]
0x180009c99  mov     rcx, [r13+0E0h]
0x180009ca0  xor     edx, edx
0x180009ca2  call    cs:__imp_?SetEnabled@Element@DirectUI@@QEAAJ_N@Z; DirectUI::Element::SetEnabled(bool)
0x180009ca9  nop     dword ptr [rax+rax+00h]
0x180009cae  xor     edx, edx
0x180009cb0  mov     rcx, r13
0x180009cb3  call    cs:__imp_?SetEnabled@Element@DirectUI@@QEAAJ_N@Z; DirectUI::Element::SetEnabled(bool)
0x180009cba  nop     dword ptr [rax+rax+00h]
0x180009cbf  mov     edx, 7F02h; lpCursorName
0x180009cc4  xor     ecx, ecx; hInstance
0x180009cc6  call    cs:__imp_LoadCursorW
0x180009ccd  nop     dword ptr [rax+rax+00h]
0x180009cd2  mov     rcx, rax; hCursor
0x180009cd5  call    cs:__imp_SetCursor
0x180009cdc  nop     dword ptr [rax+rax+00h]
0x180009ce1  mov     bl, r14b
0x180009ce4  mov     [rsp+300h+var_2AF], r14b
0x180009ce9  mov     [rsp+300h+hCursor], rax
0x180009cee  lea     rdx, aControlPanelCo; "Control Panel\\Colors"
0x180009cf5  lea     rax, [rsp+300h+hKey]
0x180009cfa  mov     [rsp+300h+var_2B0], bl
0x180009cfe  mov     r9d, 20006h; samDesired
0x180009d04  mov     [rsp+300h+phkResult], rax; phkResult
0x180009d09  xor     r8d, r8d; ulOptions
0x180009d0c  mov     [rsp+300h+hKey], r14
0x180009d11  mov     rcx, 0FFFFFFFF80000001h; hKey
0x180009d18  call    cs:__imp_RegOpenKeyExW
0x180009d1f  nop     dword ptr [rax+rax+00h]
0x180009d24  test    eax, eax
0x180009d26  jnz     loc_18000A034
0x180009d2c  lea     esi, [rax+10h]
0x180009d2f  or      r12d, 0FFFFFFFFh
0x180009d33  lea     eax, [rsi-0Ch]
0x180009d36  mov     [rsp+300h+var_2A8], r12d
0x180009d3b  mul     rsi
0x180009d3e  test    rdx, rdx
0x180009d41  jnz     loc_180009F49
0x180009d47  mov     rdx, rax; uBytes
0x180009d4a  lea     ecx, [rsi+30h]; uFlags
0x180009d4d  call    cs:__imp_LocalAlloc
0x180009d54  nop     dword ptr [rax+rax+00h]
0x180009d59  mov     rdi, rax
0x180009d5c  test    rax, rax
0x180009d5f  jz      loc_180009F49
0x180009d65  lea     eax, [rsi-0Ch]
0x180009d68  mul     rsi
0x180009d6b  test    rdx, rdx
0x180009d6e  jnz     short loc_180009D97
0x180009d70  mov     rdx, rax; uBytes
0x180009d73  lea     ecx, [rsi+30h]; uFlags
0x180009d76  call    cs:__imp_LocalAlloc
0x180009d7d  nop     dword ptr [rax+rax+00h]
0x180009d82  mov     rcx, rax
0x180009d85  mov     rsi, rax
0x180009d88  neg     rcx
0x180009d8b  sbb     edx, edx
0x180009d8d  not     edx
0x180009d8f  and     edx, 8007000Eh
0x180009d95  jmp     short loc_180009D9F
0x180009d97  mov     rsi, r14
0x180009d9a  mov     edx, 80070216h
0x180009d9f  test    edx, edx
0x180009da1  js      loc_180009F3A
0x180009da7  mov     ecx, r14d; this
0x180009daa  lea     r13, ?s_rgSystemColorRows@CAccColorCplPage@@0PAUCPL_SYSTEM_COLOR_ROW@@A; CPL_SYSTEM_COLOR_ROW near * CAccColorCplPage::s_rgSystemColorRows
0x180009db1  mov     [rsp+300h+var_2C0], rsi; unsigned int *
0x180009db6  lea     rdx, [rsp+300h+var_2AF]
0x180009dbb  mov     eax, r14d
0x180009dbe  lea     r8, [r13+18h]
0x180009dc2  mov     [rsp+300h+var_2C8], rdi; int *
0x180009dc7  mov     r9d, ecx; unsigned int
0x180009dca  mov     [rsp+300h+var_2D0], rdx; bool *
0x180009dcf  lea     rdx, [rsp+300h+var_2B0]
0x180009dd4  mov     [rsp+300h+var_2D8], rdx; bool *
0x180009dd9  mov     rdx, [rsp+300h+hKey]; HKEY
0x180009dde  lea     rbx, [rax+rax*8]
0x180009de2  cmp     byte ptr [r13+rbx*8+4], 0
0x180009de8  lea     r8, [r8+rbx*8]; struct SYSTEM_COLOR_STATE *
0x180009dec  mov     eax, r14d
0x180009def  cmovz   eax, r12d
0x180009df3  mov     r12d, eax
0x180009df6  lea     rax, [r13+28h]
0x180009dfa  lea     rax, [rax+rbx*8]
0x180009dfe  mov     [rsp+300h+phkResult], rax; bool *
0x180009e03  call    ?_ApplyColor@CAccColorCplPage@@AEAAIPEAUHKEY__@@PEAUSYSTEM_COLOR_STATE@@IPEA_N22PEAHPEAKI@Z; CAccColorCplPage::_ApplyColor(HKEY__ *,SYSTEM_COLOR_STATE *,uint,bool *,bool *,bool *,int *,ulong *,uint)
0x180009e08  mov     [rsp+300h+var_2C0], rsi; unsigned int *
0x180009e0d  lea     rdx, [rsp+300h+var_2AF]
0x180009e12  mov     [rsp+300h+var_2C8], rdi; int *
0x180009e17  lea     rcx, [r13+40h]
0x180009e1b  mov     [rsp+300h+var_2D0], rdx; bool *
0x180009e20  lea     rcx, [rcx+rbx*8]; this
0x180009e24  lea     rdx, [rsp+300h+var_2B0]
0x180009e29  mov     r9d, eax; unsigned int
0x180009e2c  mov     [rsp+300h+var_2D8], rdx; bool *
0x180009e31  lea     r8, [r13+30h]
0x180009e35  mov     rdx, [rsp+300h+hKey]; HKEY
0x180009e3a  lea     r8, [r8+rbx*8]; struct SYSTEM_COLOR_STATE *
0x180009e3e  mov     [rsp+300h+phkResult], rcx; bool *
0x180009e43  call    ?_ApplyColor@CAccColorCplPage@@AEAAIPEAUHKEY__@@PEAUSYSTEM_COLOR_STATE@@IPEA_N22PEAHPEAKI@Z; CAccColorCplPage::_ApplyColor(HKEY__ *,SYSTEM_COLOR_STATE *,uint,bool *,bool *,bool *,int *,ulong *,uint)
0x180009e48  inc     r14d
0x180009e4b  mov     ecx, eax; cElements
0x180009e4d  cmp     r14d, 8
0x180009e51  jb      loc_180009DB1
0x180009e57  mov     r8, rsi; lpaRgbValues
0x180009e5a  mov     [rsp+300h+var_2A8], r12d
0x180009e5f  mov     rdx, rdi; lpaElements
0x180009e62  call    cs:__imp_SetSysColors
0x180009e69  nop     dword ptr [rax+rax+00h]
0x180009e6e  mov     r8d, 104h
0x180009e74  lea     rdx, [rbp+200h+pszPath]
0x180009e78  lea     rcx, aSystemrootReso; "%SystemRoot%\\Resources\\Themes\\Aero\\"...
0x180009e7f  call    cs:__imp_SHExpandEnvironmentStringsW
0x180009e86  nop     dword ptr [rax+rax+00h]
0x180009e8b  mov     r13, [rsp+300h+var_298]
0x180009e90  xor     r14d, r14d
0x180009e93  test    eax, eax
0x180009e95  jz      loc_180009F27
0x180009e9b  lea     rcx, [rbp+200h+pszPath]; pszPath
0x180009e9f  call    cs:__imp_PathFileExistsW
0x180009ea6  nop     dword ptr [rax+rax+00h]
0x180009eab  test    eax, eax
0x180009ead  jz      short loc_180009F27
0x180009eaf  xor     r9d, r9d
0x180009eb2  lea     r8, aNormalsize; "NormalSize"
0x180009eb9  lea     rdx, aNormalcolor; "NormalColor"
0x180009ec0  lea     rcx, [rbp+200h+pszPath]
0x180009ec4  call    cs:__imp_SetSystemVisualStyle
0x180009ecb  nop     dword ptr [rax+rax+00h]
0x180009ed0  xorps   xmm0, xmm0
0x180009ed3  lea     rcx, [rbp+200h+var_280]
0x180009ed7  movups  [rbp+200h+var_280], xmm0
0x180009edb  movups  [rbp+200h+var_270], xmm0
0x180009edf  call    cs:__imp_DwmpGetColorizationParameters
0x180009ee6  nop     dword ptr [rax+rax+00h]
0x180009eeb  mov     eax, 7F000000h
0x180009ef0  mov     dword ptr [rbp+200h+var_280+8], 35h ; '5'
0x180009ef7  mov     dword ptr [rbp+200h+var_280], eax
0x180009efa  lea     rcx, [rbp+200h+var_280]
0x180009efe  mov     dword ptr [rbp+200h+var_280+4], eax
0x180009f01  xor     edx, edx
0x180009f03  lea     eax, [r14+2]
0x180009f07  mov     dword ptr [rbp+200h+var_270], 25h ; '%'
0x180009f0e  mov     dword ptr [rbp+200h+var_270+8], eax
0x180009f11  mov     dword ptr [rbp+200h+var_270+0Ch], eax
0x180009f14  mov     dword ptr [rbp+200h+var_280+0Ch], 0Ah
0x180009f1b  call    cs:__imp_DwmpSetColorizationParameters
0x180009f22  nop     dword ptr [rax+rax+00h]
0x180009f27  mov     rcx, rsi; hMem
0x180009f2a  call    cs:__imp_LocalFree
0x180009f31  nop     dword ptr [rax+rax+00h]
0x180009f36  mov     bl, [rsp+300h+var_2B0]
0x180009f3a  mov     rcx, rdi; hMem
0x180009f3d  call    cs:__imp_LocalFree
0x180009f44  nop     dword ptr [rax+rax+00h]
0x180009f49  mov     rcx, [rsp+300h+hKey]; hKey
0x180009f4e  call    cs:__imp_RegCloseKey
0x180009f55  nop     dword ptr [rax+rax+00h]
0x180009f5a  test    bl, bl
0x180009f5c  jz      loc_180009FF9
0x180009f62  mov     r13d, r14d
0x180009f65  lea     r12, ?s_rgSystemColorRows@CAccColorCplPage@@0PAUCPL_SYSTEM_COLOR_ROW@@A; CPL_SYSTEM_COLOR_ROW near * CAccColorCplPage::s_rgSystemColorRows
0x180009f6c  mov     r8d, r13d; unsigned int
0x180009f6f  lea     rdx, aLeftbutton; "LeftButton"
0x180009f76  call    ?_ElementAtRow@CAccColorCplPage@@AEAAPEAVElement@DirectUI@@PEBGI@Z; CAccColorCplPage::_ElementAtRow(ushort const *,uint)
0x180009f7b  mov     r8d, r13d; unsigned int
0x180009f7e  lea     rdx, aRightbutton; "RightButton"
0x180009f85  mov     rdi, rax
0x180009f88  call    ?_ElementAtRow@CAccColorCplPage@@AEAAPEAVElement@DirectUI@@PEBGI@Z; CAccColorCplPage::_ElementAtRow(ushort const *,uint)
0x180009f8d  mov     ecx, r13d
0x180009f90  lea     rbx, [r12+18h]
0x180009f95  mov     r14, rax
0x180009f98  lea     rsi, [rcx+rcx*8]
0x180009f9c  mov     rcx, [rdi]
0x180009f9f  lea     rbx, [rbx+rsi*8]
0x180009fa3  mov     rax, [rcx+168h]
0x180009faa  mov     rcx, rdi
0x180009fad  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009fb2  mov     rdx, rax; HWND
0x180009fb5  mov     r8, rbx; struct SYSTEM_COLOR_STATE *
0x180009fb8  call    ?_AddColorSwatchToButton@CAccColorCplPage@@AEAAXPEAUHWND__@@PEAUSYSTEM_COLOR_STATE@@@Z; CAccColorCplPage::_AddColorSwatchToButton(HWND__ *,SYSTEM_COLOR_STATE *)
0x180009fbd  mov     rax, [r14]
0x180009fc0  lea     rbx, [r12+30h]
0x180009fc5  mov     rcx, r14
0x180009fc8  lea     rbx, [rbx+rsi*8]
0x180009fcc  mov     rax, [rax+168h]
0x180009fd3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009fd8  mov     rdx, rax; HWND
0x180009fdb  mov     r8, rbx; struct SYSTEM_COLOR_STATE *
0x180009fde  call    ?_AddColorSwatchToButton@CAccColorCplPage@@AEAAXPEAUHWND__@@PEAUSYSTEM_COLOR_STATE@@@Z; CAccColorCplPage::_AddColorSwatchToButton(HWND__ *,SYSTEM_COLOR_STATE *)
0x180009fe3  inc     r13d
0x180009fe6  cmp     r13d, 8
0x180009fea  jb      short loc_180009F6C
0x180009fec  mov     r13, [rsp+300h+var_298]
0x180009ff1  xor     r14d, r14d
0x180009ff4  mov     r12d, [rsp+300h+var_2A8]
0x180009ff9  cmp     [rsp+300h+var_2AF], r14b
0x180009ffe  jz      short loc_18000A034
0x18000a000  cmp     r12d, 0FFFFFFFFh
0x18000a004  jz      short loc_18000A034
0x18000a006  mov     r8d, r12d; unsigned int
0x18000a009  lea     rdx, aPreviewboxtext; "PreviewBoxText"
0x18000a010  call    ?_ElementAtRow@CAccColorCplPage@@AEAAPEAVElement@DirectUI@@PEBGI@Z; CAccColorCplPage::_ElementAtRow(ushort const *,uint)
0x18000a015  mov     ecx, 8; nIndex
0x18000a01a  mov     rbx, rax
0x18000a01d  call    cs:__imp_GetSysColor
0x18000a024  nop     dword ptr [rax+rax+00h]
0x18000a029  mov     r8d, eax; unsigned int
0x18000a02c  mov     rdx, rbx; struct DirectUI::Element *
0x18000a02f  call    ?_SetForegroundColorHelper@CAccColorCplPage@@AEAAXPEAVElement@DirectUI@@K@Z; CAccColorCplPage::_SetForegroundColorHelper(DirectUI::Element *,ulong)
0x18000a034  mov     rcx, [rsp+300h+hCursor]; hCursor
0x18000a039  call    cs:__imp_SetCursor
0x18000a040  nop     dword ptr [rax+rax+00h]
0x18000a045  mov     dl, 1
0x18000a047  mov     rcx, r13
0x18000a04a  call    cs:__imp_?SetEnabled@Element@DirectUI@@QEAAJ_N@Z; DirectUI::Element::SetEnabled(bool)
0x18000a051  nop     dword ptr [rax+rax+00h]
0x18000a056  mov     rcx, [r13+0D0h]
0x18000a05d  mov     dl, 1
0x18000a05f  call    cs:__imp_?SetEnabled@Element@DirectUI@@QEAAJ_N@Z; DirectUI::Element::SetEnabled(bool)
0x18000a066  nop     dword ptr [rax+rax+00h]
0x18000a06b  mov     rcx, [r13+0D0h]
0x18000a072  mov     rax, [rcx]
0x18000a075  mov     rax, [rax+0A8h]
0x18000a07c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a081  mov     rcx, [r13+0D8h]
0x18000a088  mov     dl, 1
0x18000a08a  call    cs:__imp_?SetEnabled@Element@DirectUI@@QEAAJ_N@Z; DirectUI::Element::SetEnabled(bool)
0x18000a091  nop     dword ptr [rax+rax+00h]
0x18000a096  test    r15d, r15d
0x18000a099  jz      short loc_18000A0BA
0x18000a09b  xor     r8d, r8d; wParam
0x18000a09e  lea     r9, lParam; "WindowsThemeElement"
0x18000a0a5  mov     ecx, 0FFFFh; hWnd
0x18000a0aa  lea     edx, [r8+1Ah]; Msg
0x18000a0ae  call    cs:__imp_SendNotifyMessageW
0x18000a0b5  nop     dword ptr [rax+rax+00h]
0x18000a0ba  test    byte ptr cs:Microsoft_Windows_ThemeCPLEnableBits, 8
0x18000a0c1  jz      short loc_18000A0F4
0x18000a0c3  lea     rax, [rsp+300h+var_2A8]
0x18000a0c8  mov     [rsp+300h+var_2A8], r15d
0x18000a0cd  mov     qword ptr [rbp+200h+var_270], rax
  ... truncated ...
```
