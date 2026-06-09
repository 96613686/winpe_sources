# TouchKeyboardExperienceManager::UpdateShellPreferencesBasedOnThemesBool(ushort const *,bool *,bool *,bool *)

- ea: `0x180066a14`
- end: `0x18006707c`
- name: `?UpdateShellPreferencesBasedOnThemesBool@TouchKeyboardExperienceManager@@AEAAXPEBGPEA_N11@Z`
- size: `1640`
- prototype: `void __fastcall(TouchKeyboardExperienceManager *__hidden this, const unsigned __int16 *, bool *, bool *, bool *)`
- caller_count: `1`
- callee_count: `12`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x180227814`

## callees

- `0x180031c70`
- `0x18005d940`
- `0x18005db20`
- `0x18005f410`
- `0x18005f540`
- `0x18006634c`
- `0x180066a14`
- `0x18007b3e0`
- `0x1800e0728`
- `0x1800ecfc0`
- `0x180356360`
- `0x1804b6024`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180066e4c`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180066e62`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180066e78`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180066e8a`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180067032`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180067045`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180067058`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18006706b`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180066e4c`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180066e62`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180066e78`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180066e8a`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180067032`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180067045`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180067058`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18006706b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180066cc5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180066d25`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180066da8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180066dfb`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180066cc5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180066d25`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180066da8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180066dfb`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180066b58`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180066c1e`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180066b58`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180066c1e`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
void __fastcall TouchKeyboardExperienceManager::UpdateShellPreferencesBasedOnThemesBool(
        TouchKeyboardExperienceManager *this,
        const unsigned __int16 *a2,
        bool *a3,
        bool *a4,
        bool *a5)
{
  TouchKeyboardExperienceManager *v7; // rsi
  WCHAR *v8; // r12
  bool v9; // r14
  __int64 v10; // rax
  __int64 v11; // rax
  __int64 v12; // rax
  __int64 v13; // rax
  LSTATUS ValueW; // eax
  signed int v15; // ecx
  signed int v16; // ebx
  unsigned int v17; // edx
  bool v18; // si
  LSTATUS v19; // eax
  const WCHAR *v20; // r15
  unsigned __int64 v21; // rbx
  unsigned __int64 v22; // rdi
  unsigned int v23; // eax
  UINT32 v24; // edx
  HRESULT StringReference; // eax
  unsigned __int64 v26; // rdi
  unsigned int v27; // eax
  UINT32 v28; // edx
  HRESULT v29; // eax
  int v30; // eax
  wil::details::in1diag3 *v31; // rcx
  unsigned __int64 v32; // rdi
  unsigned int v33; // eax
  UINT32 v34; // edx
  HRESULT v35; // eax
  const WCHAR *v36; // rdi
  HSTRING v37; // r15
  unsigned int v38; // eax
  UINT32 v39; // edx
  HRESULT v40; // eax
  int v41; // eax
  KeyboardHosting::TabTipAdapter *v42; // rdi
  HSTRING v43; // rbx
  PCWSTR *v44; // rax
  __int64 v45; // rax
  int v46; // eax
  KeyboardHosting::TabTipAdapter *v47; // rdi
  HSTRING v48; // rbx
  PCWSTR *v49; // rax
  __int64 v50; // rax
  int v51; // eax
  int pdwType; // [rsp+20h] [rbp-C1h]
  unsigned int pvData; // [rsp+40h] [rbp-A1h] BYREF
  DWORD pcbData[2]; // [rsp+48h] [rbp-99h] BYREF
  DWORD v55[2]; // [rsp+50h] [rbp-91h] BYREF
  bool *v56; // [rsp+58h] [rbp-89h] BYREF
  TouchKeyboardExperienceManager *v57; // [rsp+60h] [rbp-81h]
  bool *v58; // [rsp+68h] [rbp-79h]
  __int128 hstringHeader; // [rsp+70h] [rbp-71h] BYREF
  __int128 hstringHeader_16; // [rsp+80h] [rbp-61h] BYREF
  __int128 Src; // [rsp+90h] [rbp-51h] BYREF
  __int128 Src_16; // [rsp+A0h] [rbp-41h] BYREF
  PCWSTR v63[3]; // [rsp+B0h] [rbp-31h] BYREF
  unsigned __int64 v64; // [rsp+C8h] [rbp-19h]
  PCWSTR sourceString[3]; // [rsp+D0h] [rbp-11h] BYREF
  unsigned __int64 v66; // [rsp+E8h] [rbp+7h]
  wil::details::in1diag3 *retaddr; // [rsp+138h] [rbp+57h]

  v58 = a4;
  v7 = this;
  v57 = this;
  v56 = a5;
  v8 = 0;
  v9 = 0;
  Src = 0;
  Src_16 = 0;
  v10 = std::_WChar_traits<unsigned short>::length(L"HasBorder");
  std::wstring::_Construct<1,unsigned short const *>(&Src, L"HasBorder", v10);
  std::_WChar_traits<unsigned short>::length(L"KeyboardTheme_Dark_");
  v11 = std::wstring::_Insert<unsigned short>(&Src);
  std::wstring::wstring(sourceString, v11);
  std::wstring::_Tidy_deallocate(&Src);
  hstringHeader = 0;
  hstringHeader_16 = 0;
  v12 = std::_WChar_traits<unsigned short>::length(L"HasBorder");
  std::wstring::_Construct<1,unsigned short const *>(&hstringHeader, L"HasBorder", v12);
  std::_WChar_traits<unsigned short>::length(L"KeyboardTheme_Light_");
  v13 = std::wstring::_Insert<unsigned short>(&hstringHeader);
  std::wstring::wstring(v63, v13);
  std::wstring::_Tidy_deallocate(&hstringHeader);
  v55[0] = 0;
  pcbData[0] = 4;
  ValueW = RegGetValueW(
             HKEY_CURRENT_USER,
             L"SOFTWARE\\Microsoft\\TabletTip\\1.7\\SelectedThemeDark",
             L"HasBorder",
             0x10000012u,
             v55,
             &pvData,
             pcbData);
  v15 = ValueW;
  LOWORD(v16) = 13;
  v17 = 1;
  if ( ValueW )
  {
    if ( ValueW == 234 )
    {
      LOWORD(v15) = 13;
    }
    else if ( ValueW <= 0 )
    {
      goto LABEL_5;
    }
    goto LABEL_4;
  }
  LOWORD(v15) = 13;
  if ( v55[0] == 4 )
  {
    if ( pvData <= 1 )
    {
      v15 = 0;
      v9 = pvData == 1;
      goto LABEL_5;
    }
LABEL_4:
    v15 = (unsigned __int16)v15 | 0x80070000;
    goto LABEL_5;
  }
  if ( pcbData[0] != 4 || (unsigned __int16)(pvData - 48) > 1u )
    goto LABEL_4;
  v9 = (_WORD)pvData == 49;
  v15 = 0;
LABEL_5:
  if ( v15 < 0 )
    goto LABEL_6;
  v18 = 0;
  pcbData[0] = 0;
  v55[0] = 4;
  v19 = RegGetValueW(
          HKEY_CURRENT_USER,
          L"SOFTWARE\\Microsoft\\TabletTip\\1.7\\SelectedThemeLight",
          L"HasBorder",
          0x10000012u,
          pcbData,
          &pvData,
          v55);
  if ( v19 )
  {
    if ( v19 == 234 || (v16 = v19, v19 > 0) )
    {
      v17 = 1;
LABEL_12:
      v16 = (unsigned __int16)v16 | 0x80070000;
      goto LABEL_13;
    }
    v17 = 1;
  }
  else
  {
    v17 = 1;
    if ( pcbData[0] == 4 )
    {
      if ( pvData > 1 )
        goto LABEL_12;
      v16 = 0;
      v18 = pvData == 1;
    }
    else
    {
      if ( v55[0] != 4 || (unsigned __int16)(pvData - 48) > 1u )
        goto LABEL_12;
      v18 = (_WORD)pvData == 49;
      v16 = 0;
    }
  }
LABEL_13:
  if ( v16 < 0 )
  {
LABEL_80:
    v7 = v57;
LABEL_6:
    if ( *a3 != (_BYTE)v8 )
    {
      v42 = (KeyboardHosting::TabTipAdapter *)*((_QWORD *)v7 + 73);
      *((_QWORD *)&hstringHeader_16 + 1) = v8;
      Microsoft::WRL::Wrappers::HStringReference::CreateReference((HSTRING_HEADER *)&hstringHeader, &::pvData, v17, 0);
      v43 = (HSTRING)*((_QWORD *)&hstringHeader_16 + 1);
      v44 = sourceString;
      if ( v66 > 7 )
        v44 = (PCWSTR *)sourceString[0];
      v56 = (bool *)v44;
      v45 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(&Src, &v56);
      v46 = KeyboardHosting::TabTipAdapter::SetShellPreference(v42, *(HSTRING *)(v45 + 24), v43);
      if ( v46 < 0 )
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x1212,
          (unsigned int)"pcshell\\twinui\\touchkeyboardexperiencemanager\\lib\\touchkeyboardexperiencemanager.cpp",
          (const char *)(unsigned int)v46,
          pdwType);
      v47 = (KeyboardHosting::TabTipAdapter *)*((_QWORD *)v7 + 73);
      *((_QWORD *)&hstringHeader_16 + 1) = v8;
      Microsoft::WRL::Wrappers::HStringReference::CreateReference((HSTRING_HEADER *)&hstringHeader, &::pvData, 1u, 0);
      v48 = (HSTRING)*((_QWORD *)&hstringHeader_16 + 1);
      v49 = v63;
      if ( v64 > 7 )
        v49 = (PCWSTR *)v63[0];
      v56 = (bool *)v49;
      v50 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(&Src, &v56);
      v51 = KeyboardHosting::TabTipAdapter::SetShellPreference(v47, *(HSTRING *)(v50 + 24), v48);
      if ( v51 < 0 )
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x1213,
          (unsigned int)"pcshell\\twinui\\touchkeyboardexperiencemanager\\lib\\touchkeyboardexperiencemanager.cpp",
          (const char *)(unsigned int)v51,
          pdwType);
      *a3 = (char)v8;
    }
    goto LABEL_7;
  }
  if ( *a3 && v9 == *a4 && v18 == *a5 )
    goto LABEL_7;
  v20 = L"1";
  v8 = (WCHAR *)L"1";
  if ( !v9 )
    v8 = (WCHAR *)L"0";
  *((_QWORD *)&hstringHeader_16 + 1) = 0;
  v21 = -1;
  v22 = -1;
  do
    ++v22;
  while ( v8[v22] );
  if ( v22 > 0xFFFFFFFF )
    goto LABEL_54;
  *(_QWORD *)v55 = *((_QWORD *)v57 + 73);
  v23 = Microsoft::WRL::Wrappers::HStringReference::AddOne(v22);
  v24 = v23 - 1;
  if ( (unsigned int)v22 < v23 )
    v24 = v22;
  StringReference = WindowsCreateStringReference(
                      v8,
                      v24,
                      (HSTRING_HEADER *)&hstringHeader,
                      (HSTRING *)&hstringHeader_16 + 1);
  if ( StringReference < 0 )
  {
    RaiseException(StringReference, 1u, 0, 0);
    goto LABEL_77;
  }
  v8 = (WCHAR *)sourceString;
  if ( v66 > 7 )
    v8 = (WCHAR *)sourceString[0];
  *((_QWORD *)&Src_16 + 1) = 0;
  v26 = -1;
  do
    ++v26;
  while ( v8[v26] );
  if ( v26 > 0xFFFFFFFF )
    goto LABEL_53;
  *(_QWORD *)pcbData = *((_QWORD *)&hstringHeader_16 + 1);
  v27 = Microsoft::WRL::Wrappers::HStringReference::AddOne(v26);
  v28 = v27 - 1;
  if ( (unsigned int)v26 < v27 )
    v28 = v26;
  v29 = WindowsCreateStringReference(v8, v28, (HSTRING_HEADER *)&Src, (HSTRING *)&Src_16 + 1);
  v8 = 0;
  if ( v29 < 0 )
  {
LABEL_77:
    RaiseException(v29, 1u, 0, 0);
LABEL_78:
    RaiseException(v35, 1u, 0, 0);
    goto LABEL_79;
  }
  v30 = KeyboardHosting::TabTipAdapter::SetShellPreference(
          *(KeyboardHosting::TabTipAdapter **)v55,
          *((HSTRING *)&Src_16 + 1),
          *(HSTRING *)pcbData);
  v31 = retaddr;
  if ( v30 < 0 )
    goto LABEL_55;
  while ( 1 )
  {
    if ( !v18 )
      v20 = L"0";
    *((_QWORD *)&hstringHeader_16 + 1) = v8;
    v32 = v21;
    do
      ++v32;
    while ( v20[v32] != (_WORD)v8 );
    if ( v32 > 0xFFFFFFFF )
      goto LABEL_52;
    v8 = (WCHAR *)*((_QWORD *)v57 + 73);
    v33 = Microsoft::WRL::Wrappers::HStringReference::AddOne(v32);
    v34 = v33 - 1;
    if ( (unsigned int)v32 < v33 )
      v34 = v32;
    v35 = WindowsCreateStringReference(v20, v34, (HSTRING_HEADER *)&hstringHeader, (HSTRING *)&hstringHeader_16 + 1);
    if ( v35 < 0 )
      goto LABEL_78;
    v36 = (const WCHAR *)v63;
    if ( v64 > 7 )
      v36 = v63[0];
    *((_QWORD *)&Src_16 + 1) = 0;
    do
      ++v21;
    while ( v36[v21] );
    if ( v21 <= 0xFFFFFFFF )
      break;
    RaiseException(0x80070216, 1u, 0, 0);
LABEL_52:
    RaiseException(0x80070216, 1u, 0, 0);
LABEL_53:
    RaiseException(0x80070216, 1u, 0, 0);
LABEL_54:
    RaiseException(0x80070216, v17, 0, 0);
LABEL_55:
    wil::details::in1diag3::_Log_Hr(
      v31,
      (void *)0x1208,
      (unsigned int)"pcshell\\twinui\\touchkeyboardexperiencemanager\\lib\\touchkeyboardexperiencemanager.cpp",
      (const char *)(unsigned int)v30,
      pdwType);
  }
  v37 = (HSTRING)*((_QWORD *)&hstringHeader_16 + 1);
  v38 = Microsoft::WRL::Wrappers::HStringReference::AddOne(v21);
  v39 = v38 - 1;
  if ( (unsigned int)v21 < v38 )
    v39 = v21;
  v40 = WindowsCreateStringReference(v36, v39, (HSTRING_HEADER *)&Src, (HSTRING *)&Src_16 + 1);
  if ( v40 < 0 )
  {
LABEL_79:
    RaiseException(v40, 1u, 0, 0);
    goto LABEL_80;
  }
  v41 = KeyboardHosting::TabTipAdapter::SetShellPreference(
          (KeyboardHosting::TabTipAdapter *)v8,
          *((HSTRING *)&Src_16 + 1),
          v37);
  if ( v41 < 0 )
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x1209,
      (unsigned int)"pcshell\\twinui\\touchkeyboardexperiencemanager\\lib\\touchkeyboardexperiencemanager.cpp",
      (const char *)(unsigned int)v41,
      pdwType);
  *v58 = v9;
  *v56 = v18;
  *a3 = 1;
LABEL_7:
  std::wstring::_Tidy_deallocate(v63);
  std::wstring::_Tidy_deallocate(sourceString);
}

```

## disassembly

```asm
0x180066a14  mov     [rsp-8+arg_8], rbx
0x180066a19  push    rbp
0x180066a1a  push    rsi
0x180066a1b  push    rdi
0x180066a1c  push    r12
0x180066a1e  push    r13
0x180066a20  push    r14
0x180066a22  push    r15
0x180066a24  lea     rbp, [rsp-1Fh]
0x180066a29  sub     rsp, 100h
0x180066a30  mov     rax, cs:__security_cookie
0x180066a37  xor     rax, rsp
0x180066a3a  mov     [rbp+4Fh+var_40], rax
0x180066a3e  mov     rdi, r9
0x180066a41  mov     [rbp+4Fh+var_C8], r9
0x180066a45  mov     r13, r8
0x180066a48  mov     rsi, rcx
0x180066a4b  mov     [rsp+130h+var_D0], rcx
0x180066a50  mov     r15, [rbp+4Fh+arg_20]
0x180066a54  mov     [rsp+130h+var_D8], r15
0x180066a59  xor     r12d, r12d
0x180066a5c  mov     r14d, r12d
0x180066a5f  xorps   xmm0, xmm0
0x180066a62  movups  xmmword ptr [rbp+4Fh+Src.Reserved], xmm0
0x180066a66  xorps   xmm1, xmm1
0x180066a69  movdqu  xmmword ptr [rbp+4Fh+Src.Reserved+10h], xmm1
0x180066a6e  lea     rbx, aHasborder; "HasBorder"
0x180066a75  mov     rcx, rbx
0x180066a78  call    ?length@?$_WChar_traits@G@std@@SA_KPEBG@Z; std::_WChar_traits<ushort>::length(ushort const *)
0x180066a7d  mov     r8, rax
0x180066a80  mov     rdx, rbx
0x180066a83  lea     rcx, [rbp+4Fh+Src]
0x180066a87  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x180066a8c  nop
0x180066a8d  lea     rcx, aKeyboardthemeD; "KeyboardTheme_Dark_"
0x180066a94  call    ?length@?$_WChar_traits@G@std@@SA_KPEBG@Z; std::_WChar_traits<ushort>::length(ushort const *)
0x180066a99  mov     r9, rax
0x180066a9c  mov     r8, rcx
0x180066a9f  lea     rcx, [rbp+4Fh+Src]; Src
0x180066aa3  call    ??$_Insert@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_KQEBG0@Z; std::wstring::_Insert<ushort>(unsigned __int64,ushort const * const,unsigned __int64)
0x180066aa8  mov     rdx, rax
0x180066aab  lea     rcx, [rbp+4Fh+sourceString]
0x180066aaf  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@$$QEAV01@@Z; std::wstring::wstring(std::wstring &&)
0x180066ab4  nop
0x180066ab5  lea     rcx, [rbp+4Fh+Src]
0x180066ab9  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180066abe  xorps   xmm0, xmm0
0x180066ac1  movups  xmmword ptr [rbp+4Fh+hstringHeader.Reserved], xmm0
0x180066ac5  xorps   xmm1, xmm1
0x180066ac8  movdqu  xmmword ptr [rbp+4Fh+hstringHeader.Reserved+10h], xmm1
0x180066acd  mov     rcx, rbx
0x180066ad0  call    ?length@?$_WChar_traits@G@std@@SA_KPEBG@Z; std::_WChar_traits<ushort>::length(ushort const *)
0x180066ad5  mov     r8, rax
0x180066ad8  mov     rdx, rbx
0x180066adb  lea     rcx, [rbp+4Fh+hstringHeader]
0x180066adf  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x180066ae4  nop
0x180066ae5  lea     rcx, aKeyboardthemeL; "KeyboardTheme_Light_"
0x180066aec  call    ?length@?$_WChar_traits@G@std@@SA_KPEBG@Z; std::_WChar_traits<ushort>::length(ushort const *)
0x180066af1  mov     r9, rax
0x180066af4  mov     r8, rcx
0x180066af7  lea     rcx, [rbp+4Fh+hstringHeader]; Src
0x180066afb  call    ??$_Insert@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_KQEBG0@Z; std::wstring::_Insert<ushort>(unsigned __int64,ushort const * const,unsigned __int64)
0x180066b00  mov     rdx, rax
0x180066b03  lea     rcx, [rbp+4Fh+var_80]
0x180066b07  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@$$QEAV01@@Z; std::wstring::wstring(std::wstring &&)
0x180066b0c  nop
0x180066b0d  lea     rcx, [rbp+4Fh+hstringHeader]
0x180066b11  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180066b16  mov     [rsp+130h+var_E0], r12d
0x180066b1b  mov     [rsp+130h+var_E8], 4
0x180066b23  lea     rax, [rsp+130h+var_E8]
0x180066b28  mov     [rsp+130h+pcbData], rax; pcbData
0x180066b2d  lea     rax, [rsp+130h+var_F0]
0x180066b32  mov     [rsp+130h+pvData], rax; pvData
0x180066b37  lea     rax, [rsp+130h+var_E0]
0x180066b3c  mov     [rsp+130h+pdwType], rax; int
0x180066b41  mov     r9d, 10000012h; dwFlags
0x180066b47  mov     r8, rbx; lpValue
0x180066b4a  lea     rdx, aSoftwareMicros_71; "SOFTWARE\\Microsoft\\TabletTip\\1.7\\Se"...
0x180066b51  mov     rcx, 0FFFFFFFF80000001h; hkey
0x180066b58  call    cs:__imp_RegGetValueW
0x180066b5e  mov     ecx, eax
0x180066b60  lea     ebx, [r12+0Dh]
0x180066b65  lea     edx, [rbx-0Ch]
0x180066b68  lea     r8d, [r12+31h]
0x180066b6d  test    eax, eax
0x180066b6f  jz      loc_180066FBF
0x180066b75  cmp     eax, 0EAh
0x180066b7a  jz      loc_180066FE2
0x180066b80  test    eax, eax
0x180066b82  jle     short loc_180066B8D
0x180066b84  movzx   ecx, cx
0x180066b87  or      ecx, 80070000h
0x180066b8d  test    ecx, ecx
0x180066b8f  jns     short loc_180066BD5
0x180066b91  cmp     [r13+0], r12b
0x180066b95  jnz     loc_180066ECD
0x180066b9b  lea     rcx, [rbp+4Fh+var_80]
0x180066b9f  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180066ba4  nop
0x180066ba5  lea     rcx, [rbp+4Fh+sourceString]
0x180066ba9  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180066bae  mov     rcx, [rbp+4Fh+var_40]
0x180066bb2  xor     rcx, rsp; StackCookie
0x180066bb5  call    __security_check_cookie
0x180066bba  mov     rbx, [rsp+130h+arg_8]
0x180066bc2  add     rsp, 100h
0x180066bc9  pop     r15
0x180066bcb  pop     r14
0x180066bcd  pop     r13
0x180066bcf  pop     r12
0x180066bd1  pop     rdi
0x180066bd2  pop     rsi
0x180066bd3  pop     rbp
0x180066bd4  retn
0x180066bd5  mov     esi, r12d
0x180066bd8  mov     [rsp+130h+var_E8], r12d
0x180066bdd  mov     [rsp+130h+var_E0], 4
0x180066be5  lea     rax, [rsp+130h+var_E0]
0x180066bea  mov     [rsp+130h+pcbData], rax; pcbData
0x180066bef  lea     rax, [rsp+130h+var_F0]
0x180066bf4  mov     [rsp+130h+pvData], rax; pvData
0x180066bf9  lea     rax, [rsp+130h+var_E8]
0x180066bfe  mov     [rsp+130h+pdwType], rax; int
0x180066c03  mov     r9d, 10000012h; dwFlags
0x180066c09  lea     r8, aHasborder; "HasBorder"
0x180066c10  lea     rdx, aSoftwareMicros_75; "SOFTWARE\\Microsoft\\TabletTip\\1.7\\Se"...
0x180066c17  mov     rcx, 0FFFFFFFF80000001h; hkey
0x180066c1e  call    cs:__imp_RegGetValueW
0x180066c24  test    eax, eax
0x180066c26  jz      loc_180066FE9
0x180066c2c  cmp     eax, 0EAh
0x180066c31  jz      short loc_180066C3D
0x180066c33  mov     ebx, eax
0x180066c35  test    eax, eax
0x180066c37  jle     loc_180066EC3
0x180066c3d  mov     edx, 1
0x180066c42  movzx   ebx, bx
0x180066c45  or      ebx, 80070000h
0x180066c4b  test    ebx, ebx
0x180066c4d  js      loc_180067072
0x180066c53  cmp     [r13+0], r12b
0x180066c57  jnz     loc_18006700F
0x180066c5d  lea     rcx, a0_0; "0"
0x180066c64  lea     r15, a1; "1"
0x180066c6b  mov     r12, r15
0x180066c6e  xor     eax, eax
0x180066c70  test    r14b, r14b
0x180066c73  cmovz   r12, rcx
0x180066c77  mov     [rbp+4Fh+string], rax
0x180066c7b  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180066c7f  mov     rdi, rbx
0x180066c82  inc     rdi
0x180066c85  cmp     [r12+rdi*2], ax
0x180066c8a  jnz     short loc_180066C82
0x180066c8c  mov     eax, 0FFFFFFFFh
0x180066c91  cmp     rdi, rax
0x180066c94  ja      loc_180066E7F
0x180066c9a  mov     rax, [rsp+130h+var_D0]
0x180066c9f  mov     rax, [rax+248h]
0x180066ca6  mov     qword ptr [rsp+130h+var_E0], rax
0x180066cab  mov     ecx, edi; unsigned int
0x180066cad  call    ?AddOne@HStringReference@Wrappers@WRL@Microsoft@@CAII@Z; Microsoft::WRL::Wrappers::HStringReference::AddOne(uint)
0x180066cb2  lea     edx, [rax-1]
0x180066cb5  cmp     edi, eax
0x180066cb7  cmovb   edx, edi; length
0x180066cba  lea     r9, [rbp+4Fh+string]; string
0x180066cbe  lea     r8, [rbp+4Fh+hstringHeader]; hstringHeader
0x180066cc2  mov     rcx, r12; sourceString
0x180066cc5  call    cs:__imp_WindowsCreateStringReference
0x180066ccb  xor     ecx, ecx
0x180066ccd  test    eax, eax
0x180066ccf  js      loc_180067026
0x180066cd5  lea     r12, [rbp+4Fh+sourceString]
0x180066cd9  cmp     [rbp+4Fh+var_48], 7
0x180066cde  cmova   r12, [rbp+4Fh+sourceString]
0x180066ce3  mov     [rbp+4Fh+var_88], rcx
0x180066ce7  mov     rdi, rbx
0x180066cea  inc     rdi
0x180066ced  cmp     [r12+rdi*2], cx
0x180066cf2  jnz     short loc_180066CEA
0x180066cf4  mov     eax, 0FFFFFFFFh
0x180066cf9  cmp     rdi, rax
0x180066cfc  ja      loc_180066E69
0x180066d02  mov     rax, [rbp+4Fh+string]
0x180066d06  mov     qword ptr [rsp+130h+var_E8], rax
0x180066d0b  mov     ecx, edi; unsigned int
0x180066d0d  call    ?AddOne@HStringReference@Wrappers@WRL@Microsoft@@CAII@Z; Microsoft::WRL::Wrappers::HStringReference::AddOne(uint)
0x180066d12  lea     edx, [rax-1]
0x180066d15  cmp     edi, eax
0x180066d17  cmovb   edx, edi; length
0x180066d1a  lea     r9, [rbp+4Fh+var_88]; string
0x180066d1e  lea     r8, [rbp+4Fh+Src]; hstringHeader
0x180066d22  mov     rcx, r12; sourceString
0x180066d25  call    cs:__imp_WindowsCreateStringReference
0x180066d2b  xor     r12d, r12d
0x180066d2e  test    eax, eax
0x180066d30  js      loc_180067039
0x180066d36  mov     r8, qword ptr [rsp+130h+var_E8]; HSTRING
0x180066d3b  mov     rdx, [rbp+4Fh+var_88]; HSTRING
0x180066d3f  mov     rcx, qword ptr [rsp+130h+var_E0]; this
0x180066d44  call    ?SetShellPreference@TabTipAdapter@KeyboardHosting@@QEAAJPEAUHSTRING__@@0@Z; KeyboardHosting::TabTipAdapter::SetShellPreference(HSTRING__ *,HSTRING__ *)
0x180066d49  mov     rcx, [rbp+57h]
0x180066d4d  test    eax, eax
0x180066d4f  js      loc_180066E91
0x180066d55  test    sil, sil
0x180066d58  lea     rax, a0_0; "0"
0x180066d5f  cmovz   r15, rax
0x180066d63  mov     [rbp+4Fh+string], r12
0x180066d67  mov     rdi, rbx
0x180066d6a  inc     rdi
0x180066d6d  cmp     [r15+rdi*2], r12w
0x180066d72  jnz     short loc_180066D6A
0x180066d74  mov     eax, 0FFFFFFFFh
0x180066d79  cmp     rdi, rax
0x180066d7c  ja      loc_180066E53
0x180066d82  mov     rax, [rsp+130h+var_D0]
0x180066d87  mov     r12, [rax+248h]
0x180066d8e  mov     ecx, edi; unsigned int
0x180066d90  call    ?AddOne@HStringReference@Wrappers@WRL@Microsoft@@CAII@Z; Microsoft::WRL::Wrappers::HStringReference::AddOne(uint)
0x180066d95  lea     edx, [rax-1]
0x180066d98  cmp     edi, eax
0x180066d9a  cmovb   edx, edi; length
0x180066d9d  lea     r9, [rbp+4Fh+string]; string
0x180066da1  lea     r8, [rbp+4Fh+hstringHeader]; hstringHeader
0x180066da5  mov     rcx, r15; sourceString
0x180066da8  call    cs:__imp_WindowsCreateStringReference
0x180066dae  xor     ecx, ecx
0x180066db0  test    eax, eax
0x180066db2  js      loc_18006704C
0x180066db8  lea     rdi, [rbp+4Fh+var_80]
0x180066dbc  cmp     [rbp+4Fh+var_68], 7
0x180066dc1  cmova   rdi, [rbp+4Fh+var_80]
0x180066dc6  mov     [rbp+4Fh+var_88], rcx
0x180066dca  inc     rbx
0x180066dcd  cmp     [rdi+rbx*2], cx
0x180066dd1  jnz     short loc_180066DCA
0x180066dd3  mov     eax, 0FFFFFFFFh
0x180066dd8  cmp     rbx, rax
0x180066ddb  ja      short loc_180066E3D
0x180066ddd  mov     r15, [rbp+4Fh+string]
0x180066de1  mov     ecx, ebx; unsigned int
0x180066de3  call    ?AddOne@HStringReference@Wrappers@WRL@Microsoft@@CAII@Z; Microsoft::WRL::Wrappers::HStringReference::AddOne(uint)
0x180066de8  lea     edx, [rax-1]
0x180066deb  cmp     ebx, eax
0x180066ded  cmovb   edx, ebx; length
0x180066df0  lea     r9, [rbp+4Fh+var_88]; string
0x180066df4  lea     r8, [rbp+4Fh+Src]; hstringHeader
0x180066df8  mov     rcx, rdi; sourceString
0x180066dfb  call    cs:__imp_WindowsCreateStringReference
0x180066e01  test    eax, eax
0x180066e03  js      loc_18006705F
0x180066e09  mov     r8, r15; HSTRING
0x180066e0c  mov     rdx, [rbp+4Fh+var_88]; HSTRING
0x180066e10  mov     rcx, r12; this
0x180066e13  call    ?SetShellPreference@TabTipAdapter@KeyboardHosting@@QEAAJPEAUHSTRING__@@0@Z; KeyboardHosting::TabTipAdapter::SetShellPreference(HSTRING__ *,HSTRING__ *)
0x180066e18  mov     rcx, [rbp+57h]; this
0x180066e1c  test    eax, eax
0x180066e1e  js      loc_180066EAA
0x180066e24  mov     rax, [rbp+4Fh+var_C8]
0x180066e28  mov     [rax], r14b
0x180066e2b  mov     rax, [rsp+130h+var_D8]
0x180066e30  mov     [rax], sil
0x180066e33  mov     byte ptr [r13+0], 1
0x180066e38  jmp     loc_180066B9B
0x180066e3d  xor     r9d, r9d; lpArguments
0x180066e40  xor     r8d, r8d; nNumberOfArguments
0x180066e43  lea     edx, [r9+1]; dwExceptionFlags
0x180066e47  mov     ecx, 80070216h; dwExceptionCode
0x180066e4c  call    cs:__imp_RaiseException
0x180066e52  nop
0x180066e53  xor     r9d, r9d; lpArguments
0x180066e56  xor     r8d, r8d; nNumberOfArguments
0x180066e59  lea     edx, [r9+1]; dwExceptionFlags
0x180066e5d  mov     ecx, 80070216h; dwExceptionCode
0x180066e62  call    cs:__imp_RaiseException
0x180066e68  nop
0x180066e69  xor     r9d, r9d; lpArguments
0x180066e6c  xor     r8d, r8d; nNumberOfArguments
0x180066e6f  lea     edx, [r9+1]; dwExceptionFlags
0x180066e73  mov     ecx, 80070216h; dwExceptionCode
0x180066e78  call    cs:__imp_RaiseException
0x180066e7e  nop
0x180066e7f  xor     r9d, r9d; lpArguments
0x180066e82  xor     r8d, r8d; nNumberOfArguments
0x180066e85  mov     ecx, 80070216h; dwExceptionCode
0x180066e8a  call    cs:__imp_RaiseException
0x180066e90  nop
0x180066e91  mov     r9d, eax; char *
0x180066e94  lea     r8, aPcshellTwinuiT_50; "pcshell\\twinui\\touchkeyboardexperienc"...
0x180066e9b  mov     edx, 1208h; void *
0x180066ea0  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180066ea5  jmp     loc_180066D55
0x180066eaa  mov     r9d, eax; char *
0x180066ead  lea     r8, aPcshellTwinuiT_50; "pcshell\\twinui\\touchkeyboardexperienc"...
0x180066eb4  mov     edx, 1209h; void *
0x180066eb9  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180066ebe  jmp     loc_180066E24
0x180066ec3  mov     edx, 1
  ... truncated ...
```
