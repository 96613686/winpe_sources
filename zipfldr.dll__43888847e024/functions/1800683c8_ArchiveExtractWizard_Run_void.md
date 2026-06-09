# ArchiveExtractWizard::Run(void)

- ea: `0x1800683c8`
- end: `0x180068666`
- name: `?Run@ArchiveExtractWizard@@AEAA_JXZ`
- size: `670`
- prototype: `__int64 __fastcall(ArchiveExtractWizard *__hidden this)`
- caller_count: `1`
- callee_count: `14`
- tags: `loader_planting`

## callers

- `0x180068a90`

## callees

- `0x180020cbc`
- `0x180031e94`
- `0x180034760`
- `0x180036f50`
- `0x180037958`
- `0x1800421a4`
- `0x1800423c4`
- `0x180049dc4`
- `0x18005fbec`
- `0x1800651dc`
- `0x1800683c8`
- `0x18006866c`
- `0x18006daa0`
- `0x18006db34`

## import_xrefs

- `SHLWAPI!__imp_ShellMessageBoxW` at `0x18006860f`
- `SHLWAPI!__imp_ShellMessageBoxW` at `0x18006860f`
- `USER32!SetThreadDpiAwarenessContext` at `0x1800683fe`
- `USER32!SetThreadDpiAwarenessContext` at `0x1800685ea`
- `USER32!SetThreadDpiAwarenessContext` at `0x180068633`
- `USER32!SetThreadDpiAwarenessContext` at `0x1800683fe`
- `USER32!SetThreadDpiAwarenessContext` at `0x1800685ea`
- `USER32!SetThreadDpiAwarenessContext` at `0x180068633`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall ArchiveExtractWizard::Run(ArchiveExtractWizard *this)
{
  UINT v2; // edi
  __int64 v3; // rdx
  __int64 v4; // r8
  __int64 v5; // rax
  bool v6; // al
  __int64 v7; // rdx
  __int64 v8; // r8
  unsigned __int64 v9; // rbx
  const WCHAR *pszTemplate; // r15
  unsigned int TextScaleFactor; // eax
  __int64 v12; // rcx
  int v13; // eax
  struct _PSP *v14; // rax
  struct _PROPSHEETHEADERW_V2 *v15; // rdx
  __int64 v16; // rbx
  unsigned __int64 i; // rdi
  UINT fuStyle; // [rsp+20h] [rbp-E0h]
  __int64 v20[3]; // [rsp+30h] [rbp-D0h] BYREF
  char v21; // [rsp+48h] [rbp-B8h]
  _BYTE v22[32]; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v23; // [rsp+70h] [rbp-90h] BYREF
  PROPSHEETPAGEW_V4 constPropSheetPagePointer; // [rsp+80h] [rbp-80h] BYREF
  PROPSHEETHEADERW_V2 v25; // [rsp+F0h] [rbp-10h] BYREF
  HPROPSHEETPAGE v26[2]; // [rsp+150h] [rbp+50h] BYREF
  __int128 v27; // [rsp+160h] [rbp+60h]
  __int64 v28; // [rsp+170h] [rbp+70h]
  wil::details::in1diag3 *retaddr; // [rsp+1A8h] [rbp+A8h]

  v23 = SetThreadDpiAwarenessContext(-2);
  v20[2] = (__int64)&v23;
  v21 = 1;
  v2 = 0;
  v5 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr((char *)this + 8, v3, v4);
  v6 = CheckForKnownArchiveSupportIssues(v5);
  switch ( v6 )
  {
    case 2:
      v2 = 1;
      break;
    case 3:
      v20[0] = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr((char *)this + 8, v7, v8);
      v20[1] = *((_QWORD *)this + 3);
      v20[0] = *(_QWORD *)(split_extension((__int64)v22, v20) + 16);
      ArchiveFolderTelemetry::ExtractArchiveEncrypted<unsigned short const *>(v20);
      v2 = 3;
      *((_DWORD *)this + 19) = 10577;
      break;
    case 4:
      ArchiveFolderTelemetry::ExtractArchiveSolidRAR();
      v2 = 3;
      *((_DWORD *)this + 19) = 10578;
      break;
  }
  *(_OWORD *)v26 = 0;
  v27 = 0;
  v28 = 0;
  v9 = 0;
  while ( 1 )
  {
    constPropSheetPagePointer.dwSize = 104;
    memset_0(&constPropSheetPagePointer.dwFlags, 0, 0x64u);
    constPropSheetPagePointer.hInstance = &_ImageBase;
    constPropSheetPagePointer.lParam = (LPARAM)this;
    constPropSheetPagePointer.dwFlags = 4096;
    constPropSheetPagePointer.pszTemplate = (LPCWSTR)`ArchiveExtractWizard::Run'::`2'::pages[4 * v9];
    if ( (unsigned int)anonymous_namespace_::GetTextScaleFactor() <= 0x7D )
    {
      pszTemplate = constPropSheetPagePointer.pszTemplate;
    }
    else
    {
      pszTemplate = (const WCHAR *)qword_180075708[4 * v9];
      constPropSheetPagePointer.pszTemplate = pszTemplate;
    }
    constPropSheetPagePointer.pszHeaderTitle = (LPCWSTR)qword_1800756F8[4 * v9];
    constPropSheetPagePointer.pfnDlgProc = (DLGPROC)*(&off_180075700 + 4 * v9);
    v20[0] = 0;
    TextScaleFactor = anonymous_namespace_::GetTextScaleFactor();
    v13 = anonymous_namespace_::ScaleDialogTemplate_0(v12, pszTemplate, TextScaleFactor, v20);
    if ( v13 >= 0 )
    {
      constPropSheetPagePointer.pszTemplate = (LPCWSTR)v20[0];
      constPropSheetPagePointer.dwFlags |= 1u;
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xA2,
        (unsigned int)"onecore\\internal\\shell\\inc\\private\\ShCore-Win32DialogResourceHelpers.h",
        (const char *)(unsigned int)v13,
        fuStyle);
    }
    v14 = CreatePropertySheetPageW(&constPropSheetPagePointer);
    v26[v9] = v14;
    if ( !v14 )
      break;
    if ( ++v9 >= 5 )
    {
      v25.dwSize = 96;
      memset_0(&v25.dwFlags, 0, 0x5Cu);
      v25.hInstance = &_ImageBase;
      v25.dwFlags = 16388;
      v25.ppsp = (LPCPROPSHEETPAGEW)v26;
      v25.nPages = 5;
      v25.nStartPage = v2;
      v25.pszCaption = (LPCWSTR)10563;
      v25.hIcon = (HICON)123;
      v16 = (int)AccessibilityHelpers::DoPropertySheetWithScaling(&v25, v15);
      SetThreadDpiAwarenessContext(v23);
      return v16;
    }
  }
  ShellMessageBoxW(&_ImageBase, 0, (LPCWSTR)0x27A5, (LPCWSTR)0x2941, 0x10u);
  for ( i = 0; i < v9; ++i )
    DestroyPropertySheetPage(v26[i]);
  SetThreadDpiAwarenessContext(v23);
  return -1;
}

```

## disassembly

```asm
0x1800683c8  mov     [rsp-8+arg_8], rbx
0x1800683cd  mov     [rsp-8+arg_10], rsi
0x1800683d2  push    rbp
0x1800683d3  push    rdi
0x1800683d4  push    r12
0x1800683d6  push    r14
0x1800683d8  push    r15
0x1800683da  lea     rbp, [rsp-80h]
0x1800683df  sub     rsp, 180h
0x1800683e6  mov     rax, cs:__security_cookie
0x1800683ed  xor     rax, rsp
0x1800683f0  mov     [rbp+0A0h+var_28], rax
0x1800683f4  mov     r14, rcx
0x1800683f7  mov     rcx, 0FFFFFFFFFFFFFFFEh
0x1800683fe  call    cs:__imp_SetThreadDpiAwarenessContext
0x180068404  mov     [rsp+1A0h+var_130], rax
0x180068409  lea     rax, [rsp+1A0h+var_130]
0x18006840e  mov     [rsp+1A0h+var_160], rax
0x180068413  mov     [rsp+1A0h+var_158], 1
0x180068418  xor     edi, edi
0x18006841a  lea     rcx, [r14+8]
0x18006841e  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180068423  mov     rcx, rax
0x180068426  call    ?CheckForKnownArchiveSupportIssues@@YA?AW4ArchiveSupportLevel@@PEBG@Z; CheckForKnownArchiveSupportIssues(ushort const *)
0x18006842b  movzx   ecx, al
0x18006842e  sub     ecx, 2
0x180068431  jz      short loc_180068499
0x180068433  sub     ecx, 1
0x180068436  jz      short loc_180068451
0x180068438  cmp     ecx, 1
0x18006843b  jnz     short loc_18006849E
0x18006843d  call    ?ExtractArchiveSolidRAR@ArchiveFolderTelemetry@@SAXXZ; ArchiveFolderTelemetry::ExtractArchiveSolidRAR(void)
0x180068442  mov     edi, 3
0x180068447  mov     dword ptr [r14+4Ch], 2952h
0x18006844f  jmp     short loc_18006849E
0x180068451  lea     rcx, [r14+8]
0x180068455  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18006845a  mov     [rsp+1A0h+var_170], rax
0x18006845f  mov     rax, [r14+18h]
0x180068463  mov     [rsp+1A0h+var_168], rax
0x180068468  lea     rdx, [rsp+1A0h+var_170]
0x18006846d  lea     rcx, [rsp+1A0h+var_150]
0x180068472  call    ?split_extension@@YA?AU?$pair@V?$basic_string_view@GU?$char_traits@G@std@@@std@@V12@@std@@V?$basic_string_view@GU?$char_traits@G@std@@@2@@Z; split_extension(std::basic_string_view<ushort>)
0x180068477  mov     rcx, [rax+10h]
0x18006847b  mov     [rsp+1A0h+var_170], rcx
0x180068480  lea     rcx, [rsp+1A0h+var_170]
0x180068485  call    ??$ExtractArchiveEncrypted@PEBG@ArchiveFolderTelemetry@@SAX$$QEAPEBG@Z; ArchiveFolderTelemetry::ExtractArchiveEncrypted<ushort const *>(ushort const * &&)
0x18006848a  mov     edi, 3
0x18006848f  mov     dword ptr [r14+4Ch], 2951h
0x180068497  jmp     short loc_18006849E
0x180068499  mov     edi, 1
0x18006849e  xorps   xmm0, xmm0
0x1800684a1  xor     eax, eax
0x1800684a3  movups  xmmword ptr [rbp+0A0h+var_50], xmm0
0x1800684a7  movups  [rbp+0A0h+var_40], xmm0
0x1800684ab  mov     [rbp+0A0h+var_30], rax
0x1800684af  xor     ebx, ebx
0x1800684b1  lea     r12, __ImageBase
0x1800684b8  mov     [rbp+0A0h+constPropSheetPagePointer.dwSize], 68h ; 'h'
0x1800684bf  xor     edx, edx; Val
0x1800684c1  lea     r8d, [rdx+64h]; Size
0x1800684c5  lea     rcx, [rbp+0A0h+constPropSheetPagePointer.dwFlags]; void *
0x1800684c9  call    memset_0
0x1800684ce  mov     [rbp+0A0h+constPropSheetPagePointer.hInstance], r12
0x1800684d2  mov     [rbp+0A0h+constPropSheetPagePointer.lParam], r14
0x1800684d6  mov     [rbp+0A0h+constPropSheetPagePointer.dwFlags], 1000h
0x1800684dd  mov     rsi, rbx
0x1800684e0  shl     rsi, 5
0x1800684e4  mov     rax, [rsi+r12+756F0h]
0x1800684ec  mov     qword ptr [rbp+0A0h+constPropSheetPagePointer.10h], rax
0x1800684f0  call    _anonymous_namespace___GetTextScaleFactor
0x1800684f5  lea     rcx, off_180075700
0x1800684fc  cmp     eax, 7Dh ; '}'
0x1800684ff  lea     rax, qword_1800756F8
0x180068506  jbe     short loc_180068516
0x180068508  mov     r15, [rsi+r12+75708h]
0x180068510  mov     qword ptr [rbp+0A0h+constPropSheetPagePointer.10h], r15
0x180068514  jmp     short loc_18006851A
0x180068516  mov     r15, qword ptr [rbp+0A0h+constPropSheetPagePointer.10h]
0x18006851a  mov     rax, [rax+rsi]
0x18006851e  mov     [rbp+0A0h+constPropSheetPagePointer.pszHeaderTitle], rax
0x180068522  mov     rax, [rcx+rsi]
0x180068526  mov     [rbp+0A0h+constPropSheetPagePointer.pfnDlgProc], rax
0x18006852a  mov     [rsp+1A0h+var_170], 0
0x180068533  call    _anonymous_namespace___GetTextScaleFactor
0x180068538  mov     r8d, eax
0x18006853b  lea     r9, [rsp+1A0h+var_170]
0x180068540  mov     rdx, r15
0x180068543  call    _anonymous_namespace___ScaleDialogTemplate_0
0x180068548  test    eax, eax
0x18006854a  jns     short loc_180068569
0x18006854c  mov     rcx, [rbp+0A8h]; this
0x180068553  mov     r9d, eax; char *
0x180068556  lea     r8, aOnecoreInterna_5; "onecore\\internal\\shell\\inc\\private"...
0x18006855d  mov     edx, 0A2h; void *
0x180068562  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180068567  jmp     short loc_180068576
0x180068569  mov     rax, [rsp+1A0h+var_170]
0x18006856e  mov     qword ptr [rbp+0A0h+constPropSheetPagePointer.10h], rax
0x180068572  or      [rbp+0A0h+constPropSheetPagePointer.dwFlags], 1
0x180068576  lea     rcx, [rbp+0A0h+constPropSheetPagePointer]; constPropSheetPagePointer
0x18006857a  call    CreatePropertySheetPageW
0x18006857f  mov     [rbp+rbx*8+0A0h+var_50], rax
0x180068584  test    rax, rax
0x180068587  jz      short loc_1800685F6
0x180068589  inc     rbx
0x18006858c  cmp     rbx, 5
0x180068590  jb      loc_1800684B8
0x180068596  mov     [rbp+0A0h+var_B0.dwSize], 60h ; '`'
0x18006859d  xor     edx, edx; Val
0x18006859f  lea     r8d, [rdx+5Ch]; Size
0x1800685a3  lea     rcx, [rbp+0A0h+var_B0.dwFlags]; void *
0x1800685a7  call    memset_0
0x1800685ac  mov     [rbp+0A0h+var_B0.hInstance], r12
0x1800685b0  mov     [rbp+0A0h+var_B0.dwFlags], 4004h
0x1800685b7  lea     rax, [rbp+0A0h+var_50]
0x1800685bb  mov     qword ptr [rbp+0A0h+var_B0.38h], rax
0x1800685bf  mov     [rbp+0A0h+var_B0.nPages], 5
0x1800685c6  mov     dword ptr [rbp+0A0h+var_B0.30h], edi
0x1800685c9  mov     [rbp+0A0h+var_B0.pszCaption], 2943h
0x1800685d1  mov     qword ptr [rbp+0A0h+var_B0.18h], 7Bh ; '{'
0x1800685d9  lea     rcx, [rbp+0A0h+var_B0]; this
0x1800685dd  call    ?DoPropertySheetWithScaling@AccessibilityHelpers@@YAHPEAU_PROPSHEETHEADERW_V2@@@Z; AccessibilityHelpers::DoPropertySheetWithScaling(_PROPSHEETHEADERW_V2 *)
0x1800685e2  movsxd  rbx, eax
0x1800685e5  mov     rcx, [rsp+1A0h+var_130]
0x1800685ea  call    cs:__imp_SetThreadDpiAwarenessContext
0x1800685f0  nop
0x1800685f1  mov     rax, rbx
0x1800685f4  jmp     short loc_18006863E
0x1800685f6  mov     [rsp+1A0h+fuStyle], 10h; fuStyle
0x1800685fe  xor     edx, edx; hWnd
0x180068600  mov     r9d, 2941h; lpcTitle
0x180068606  mov     r8d, 27A5h; lpcText
0x18006860c  mov     rcx, r12; hAppInst
0x18006860f  call    cs:__imp_ShellMessageBoxW
0x180068615  xor     edi, edi
0x180068617  test    rbx, rbx
0x18006861a  jz      short loc_18006862E
0x18006861c  mov     rcx, [rbp+rdi*8+0A0h+var_50]; HPROPSHEETPAGE
0x180068621  call    DestroyPropertySheetPage
0x180068626  inc     rdi
0x180068629  cmp     rdi, rbx
0x18006862c  jb      short loc_18006861C
0x18006862e  mov     rcx, [rsp+1A0h+var_130]
0x180068633  call    cs:__imp_SetThreadDpiAwarenessContext
0x180068639  nop
0x18006863a  or      rax, 0FFFFFFFFFFFFFFFFh
0x18006863e  mov     rcx, [rbp+0A0h+var_28]
0x180068642  xor     rcx, rsp; StackCookie
0x180068645  call    __security_check_cookie
0x18006864a  lea     r11, [rsp+1A0h+var_20]
0x180068652  mov     rbx, [r11+38h]
0x180068656  mov     rsi, [r11+40h]
0x18006865a  mov     rsp, r11
0x18006865d  pop     r15
0x18006865f  pop     r14
0x180068661  pop     r12
0x180068663  pop     rdi
0x180068664  pop     rbp
0x180068665  retn
```
