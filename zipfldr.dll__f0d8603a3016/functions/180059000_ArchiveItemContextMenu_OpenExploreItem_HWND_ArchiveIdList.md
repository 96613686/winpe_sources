# ArchiveItemContextMenu::OpenExploreItem(HWND__ *,ArchiveIdList *)

- ea: `0x180059000`
- end: `0x1800599e7`
- name: `?OpenExploreItem@ArchiveItemContextMenu@@AEAAJPEAUHWND__@@PEAUArchiveIdList@@@Z`
- size: `2535`
- prototype: `__int64 __fastcall(ArchiveItemContextMenu *this, HWND, struct ArchiveIdList *)`
- caller_count: `1`
- callee_count: `25`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180058a20`

## callees

- `0x18001f080`
- `0x1800200e4`
- `0x180020cbc`
- `0x180027a40`
- `0x18002abd0`
- `0x18002ed2c`
- `0x180030a3c`
- `0x180031e94`
- `0x180033aa8`
- `0x180034760`
- `0x180034e5c`
- `0x180034fbc`
- `0x180036f50`
- `0x18003edd4`
- `0x180057d74`
- `0x180057fbc`
- `0x18005832c`
- `0x1800583ec`
- `0x180058688`
- `0x180058890`
- `0x180059000`
- `0x180065238`
- `0x1800652fc`
- `0x180065780`
- `0x180071010`

## import_xrefs

- `SHLWAPI!__imp_SHInvokeCommandOnContextMenu` at `0x18005989e`
- `SHLWAPI!__imp_SHInvokeCommandOnContextMenu` at `0x18005989e`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x18005911d`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x180059166`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x18005911d`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x180059166`
- `USER32!DialogBoxParamW` at `0x18005936b`
- `USER32!DialogBoxParamW` at `0x18005936b`
- `USER32!SetCursor` at `0x18005903e`
- `USER32!SetCursor` at `0x1800590ad`
- `USER32!SetCursor` at `0x180059145`
- `USER32!SetCursor` at `0x180059190`
- `USER32!SetCursor` at `0x1800592d7`
- `USER32!SetCursor` at `0x1800593be`
- `USER32!SetCursor` at `0x1800593d1`
- `USER32!SetCursor` at `0x180059518`
- `USER32!SetCursor` at `0x180059588`
- `USER32!SetCursor` at `0x1800595d4`
- `USER32!SetCursor` at `0x18005965a`
- `USER32!SetCursor` at `0x180059790`
- `USER32!SetCursor` at `0x180059879`
- `USER32!SetCursor` at `0x18005993a`
- `USER32!SetCursor` at `0x1800599b4`
- `USER32!SetCursor` at `0x18005903e`
- `USER32!SetCursor` at `0x1800590ad`
- `USER32!SetCursor` at `0x180059145`
- `USER32!SetCursor` at `0x180059190`
- `USER32!SetCursor` at `0x1800592d7`
- `USER32!SetCursor` at `0x1800593be`
- `USER32!SetCursor` at `0x1800593d1`
- `USER32!SetCursor` at `0x180059518`
- `USER32!SetCursor` at `0x180059588`
- `USER32!SetCursor` at `0x1800595d4`
- `USER32!SetCursor` at `0x18005965a`
- `USER32!SetCursor` at `0x180059790`
- `USER32!SetCursor` at `0x180059879`
- `USER32!SetCursor` at `0x18005993a`
- `USER32!SetCursor` at `0x1800599b4`
- `USER32!LoadCursorW` at `0x180059035`
- `USER32!LoadCursorW` at `0x180059035`
- `USER32!ShowCursor` at `0x180059050`
- `USER32!ShowCursor` at `0x180059050`

## string_xrefs

- `0x1800596ad`: `ReadWriteTempFile`

## pseudocode

```c
__int64 __fastcall ArchiveItemContextMenu::OpenExploreItem(
        ArchiveItemContextMenu *this,
        HWND a2,
        struct ArchiveIdList *a3)
{
  HCURSOR CursorW; // rax
  bool v7; // si
  const unsigned __int16 *v8; // rax
  CTempFileNameArray *v9; // rcx
  unsigned int v10; // r9d
  int TempLocation; // eax
  __int64 v12; // r8
  __int64 v13; // r9
  unsigned int v14; // ebx
  const char *v15; // r9
  __int64 result; // rax
  const char *v17; // r9
  unsigned int LastError; // ebx
  const char *v19; // r9
  unsigned int v20; // ebx
  __int64 v21; // rax
  __int64 v22; // rcx
  int EntireArchive; // ebx
  INT_PTR v24; // rax
  const unsigned __int16 *v25; // rax
  int ArchiveWithWizard; // eax
  unsigned int v27; // ebx
  __int64 v28; // rax
  __int64 v29; // rax
  int ExtendedLengthPath; // eax
  unsigned int v31; // ebx
  __int64 v32; // rax
  int v33; // eax
  unsigned int v34; // ebx
  const WCHAR *v35; // rax
  const struct _GUID *v36; // rdx
  int v37; // eax
  unsigned int v38; // ebx
  __int64 v39; // rcx
  const unsigned __int16 *v40; // rax
  CTempFileNameArray *v41; // rcx
  int v42; // eax
  void *v43; // rbx
  __int64 (__fastcall *v44)(void *, __int64, const GUID *, GUID *); // rdi
  int v45; // eax
  int v46; // eax
  int dwInitParam; // [rsp+20h] [rbp-788h]
  PCWSTR v48[4]; // [rsp+30h] [rbp-778h] BYREF
  HCURSOR *p_hCursor; // [rsp+50h] [rbp-758h]
  char v50; // [rsp+58h] [rbp-750h]
  HCURSOR hCursor; // [rsp+60h] [rbp-748h] BYREF
  void *v52; // [rsp+68h] [rbp-740h] BYREF
  int v53[2]; // [rsp+70h] [rbp-738h] BYREF
  __int64 v54; // [rsp+78h] [rbp-730h] BYREF
  int v55[2]; // [rsp+80h] [rbp-728h] BYREF
  _BYTE v56[16]; // [rsp+88h] [rbp-720h] BYREF
  const WCHAR *v57; // [rsp+98h] [rbp-710h]
  _OWORD v58[2]; // [rsp+A8h] [rbp-700h] BYREF
  _OWORD v59[2]; // [rsp+C8h] [rbp-6E0h] BYREF
  _QWORD v60[4]; // [rsp+E8h] [rbp-6C0h] BYREF
  _BYTE v61[8]; // [rsp+108h] [rbp-6A0h] BYREF
  _QWORD v62[8]; // [rsp+110h] [rbp-698h] BYREF
  unsigned __int16 v63[264]; // [rsp+150h] [rbp-658h] BYREF
  WCHAR Buffer[256]; // [rsp+360h] [rbp-448h] BYREF
  WCHAR v65[256]; // [rsp+560h] [rbp-248h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+7A8h] [rbp+0h]

  try
  {
    CursorW = LoadCursorW(0, (LPCWSTR)0x7F8A);
    hCursor = SetCursor(CursorW);
    v7 = 1;
    ShowCursor(1);
    p_hCursor = &hCursor;
    v50 = 1;
    v8 = (const unsigned __int16 *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(*((_QWORD *)this + 8) + 64LL);
    TempLocation = CTempFileNameArray::GetTempLocation(v9, v8, v63, v10);
    v14 = TempLocation;
    if ( TempLocation < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xFA,
        (unsigned int)"shell\\ext\\zip\\archive\\archiveitemcontextmenu.cpp",
        (const char *)(unsigned int)TempLocation,
        dwInitParam);
      SetCursor(hCursor);
      return v14;
    }
    if ( *(_QWORD *)(*(_QWORD *)(*((_QWORD *)this + 8) + 144LL) + 72LL) > 1u )
    {
      v48[0] = (PCWSTR)((char *)a3 + 2 * *((unsigned __int16 *)a3 + 15) + 32);
      v48[1] = (PCWSTR)*((unsigned __int16 *)a3 + 14);
      split_extension(v59, v48);
      if ( !LoadStringW(&_ImageBase, 0x27C9u, Buffer, 256) )
      {
        LastError = wil::details::in1diag3::Return_GetLastError(
                      retaddr,
                      (void *)0x107,
                      (unsigned int)"shell\\ext\\zip\\archive\\archiveitemcontextmenu.cpp",
                      v17);
        SetCursor(hCursor);
        return LastError;
      }
      if ( !LoadStringW(&_ImageBase, 0x27C8u, v65, 256) )
      {
        v20 = wil::details::in1diag3::Return_GetLastError(
                retaddr,
                (void *)0x108,
                (unsigned int)"shell\\ext\\zip\\archive\\archiveitemcontextmenu.cpp",
                v19);
        SetCursor(hCursor);
        return v20;
      }
      v60[0] = Buffer;
      v21 = -1;
      v22 = -1;
      do
        ++v22;
      while ( Buffer[v22] );
      v60[1] = v22;
      v60[2] = v65;
      do
        ++v21;
      while ( v65[v21] );
      v60[3] = v21;
      v62[0] = L".bat";
      v62[1] = 4;
      v62[2] = L".cmd";
      v62[3] = 4;
      v62[4] = L".com";
      v62[5] = 4;
      v62[6] = L".exe";
      v62[7] = 4;
      *(_OWORD *)v48 = v59[0];
      if ( (unsigned __int8)matches_name<std::basic_string_view<unsigned short> const *>(v48, v60, v61) )
      {
        std::filesystem::path::path(v60, v63);
        EntireArchive = ExtractEntireArchive(*((_QWORD *)this + 8) + 64LL, (__int64)v60, (__int64)a2, 9);
        std::wstring::_Tidy_deallocate(v60);
        if ( EntireArchive == -2147023673 )
        {
          SetCursor(hCursor);
          return 2147943623LL;
        }
        if ( EntireArchive < 0 )
          wil::details::in1diag3::_Log_Hr(
            retaddr,
            (void *)0x119,
            (unsigned int)"shell\\ext\\zip\\archive\\archiveitemcontextmenu.cpp",
            (const char *)(unsigned int)EntireArchive,
            dwInitParam);
        CTempFileNameArray::ReferenceDirectory(g_pCTFA, v63);
        v7 = EntireArchive < 0;
        goto LABEL_25;
      }
      *(_OWORD *)v48 = v59[1];
      if ( (unsigned __int8)matches_name<std::basic_string_view<unsigned short> const *>(v48, v62, v63) )
      {
        v24 = DialogBoxParamW(&_ImageBase, (LPCWSTR)0xB2, a2, ExtractPromptDlgProc, 0);
        if ( v24 == 2 )
        {
LABEL_24:
          SetCursor(hCursor);
          return 0;
        }
        if ( v24 == 1131 )
        {
          v25 = (const unsigned __int16 *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(*((_QWORD *)this + 8) + 64LL);
          ArchiveWithWizard = ExtractArchiveWithWizard(v25, 0);
          v27 = ArchiveWithWizard;
          if ( ArchiveWithWizard < 0 )
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x12B,
              (unsigned int)"shell\\ext\\zip\\archive\\archiveitemcontextmenu.cpp",
              (const char *)(unsigned int)ArchiveWithWizard,
              dwInitParam);
            SetCursor(hCursor);
            return v27;
          }
          goto LABEL_24;
        }
      }
    }
LABEL_25:
    v58[0] = 0;
    v58[1] = _mm_load_si128((const __m128i *)&_xmm);
    LOWORD(v58[0]) = 0;
    v48[0] = (PCWSTR)((char *)a3 + 32);
    v48[1] = (PCWSTR)(*((unsigned __int16 *)a3 + 14) + (unsigned __int64)*((unsigned __int16 *)a3 + 15));
    LOBYTE(v12) = 0;
    std::filesystem::_Convert_Source_to_wide<std::basic_string_view<unsigned short>,std::filesystem::_Normal_conversion>(
      v59,
      v48,
      v12,
      v13);
    v28 = std::filesystem::path::path(v62, v63);
    v29 = std::filesystem::operator/(v60, v28, v59);
    std::filesystem::path::lexically_normal(v29, v56);
    std::wstring::_Tidy_deallocate(v60);
    std::wstring::_Tidy_deallocate(v62);
    std::wstring::_Tidy_deallocate(v59);
    v48[0] = (PCWSTR)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v56);
    v48[1] = v57;
    ExtendedLengthPath = MakeExtendedLengthPath(v48, (__int64)v58);
    v31 = ExtendedLengthPath;
    if ( ExtendedLengthPath < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x13F,
        (unsigned int)"shell\\ext\\zip\\archive\\archiveitemcontextmenu.cpp",
        (const char *)(unsigned int)ExtendedLengthPath,
        dwInitParam);
      std::wstring::_Tidy_deallocate(v56);
      std::wstring::_Tidy_deallocate(v58);
      SetCursor(hCursor);
      return v31;
    }
    if ( v7 )
    {
      v32 = std::wstring::wstring(v48, v58);
      LOBYTE(dwInitParam) = 11;
      v33 = ExtractFromArchiveByIndex(*((_QWORD *)this + 8) + 64LL, *((unsigned int *)a3 + 6), v32);
      v34 = v33;
      if ( v33 < 0 )
      {
        if ( v33 == -2147023673 )
        {
          std::wstring::_Tidy_deallocate(v56);
          std::wstring::_Tidy_deallocate(v58);
          SetCursor(hCursor);
          return 2147943623LL;
        }
        else
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x14A,
            (unsigned int)"shell\\ext\\zip\\archive\\archiveitemcontextmenu.cpp",
            (const char *)(unsigned int)v33,
            dwInitParam);
          std::wstring::_Tidy_deallocate(v56);
          std::wstring::_Tidy_deallocate(v58);
          SetCursor(hCursor);
          return v34;
        }
      }
    }
    v52 = 0;
    v35 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v56);
    v37 = ShellItemFromFileSystemPath(v35, v36, &v52, 0);
    v38 = v37;
    if ( v37 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x14F,
        (unsigned int)"shell\\ext\\zip\\archive\\archiveitemcontextmenu.cpp",
        (const char *)(unsigned int)v37,
        dwInitParam);
      if ( v52 )
        winrt::com_ptr<IShellFolder2>::unconditional_release_ref(&v52);
LABEL_70:
      std::wstring::_Tidy_deallocate(v56);
      std::wstring::_Tidy_deallocate(v58);
      SetCursor(hCursor);
      return v38;
    }
    *(_QWORD *)v55 = 0;
    if ( (*(int (__fastcall **)(void *, _QWORD, const GUID *, GUID *))(*(_QWORD *)v52 + 24LL))(
           v52,
           0,
           &BHID_AssociationArray,
           &GUID_d7d31033_ccb5_40e3_8efa_a668f231003f) < 0
      || (*(int (__fastcall **)(_QWORD, __int64, const wchar_t *))(**(_QWORD **)v55 + 48LL))(
           *(_QWORD *)v55,
           17760256,
           L"ReadWriteTempFile") < 0 )
    {
      v40 = (const unsigned __int16 *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v56);
      CTempFileNameArray::ReferenceTempFile(v41, v63, v40);
    }
    v54 = 0;
    *(_QWORD *)v53 = 0;
    v42 = BindCtx_RegisterUIWindow_0(v39, a2, &v54);
    v38 = v42;
    if ( v42 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x15F,
        (unsigned int)"shell\\ext\\zip\\archive\\archiveitemcontextmenu.cpp",
        (const char *)(unsigned int)v42,
        (int)v55);
      if ( *(_QWORD *)v53 )
        winrt::com_ptr<IShellFolder2>::unconditional_release_ref(v53);
      if ( v54 )
        winrt::com_ptr<IShellFolder2>::unconditional_release_ref(&v54);
      if ( *(_QWORD *)v55 )
        winrt::com_ptr<IShellFolder2>::unconditional_release_ref(v55);
      if ( v52 )
        winrt::com_ptr<IShellFolder2>::unconditional_release_ref(&v52);
      goto LABEL_70;
    }
    v43 = v52;
    v44 = *(__int64 (__fastcall **)(void *, __int64, const GUID *, GUID *))(*(_QWORD *)v52 + 24LL);
    if ( *(_QWORD *)v53 )
      winrt::com_ptr<IShellFolder2>::unconditional_release_ref(v53);
    v45 = v44(v43, v54, &BHID_SFUIObject, &GUID_000214e4_0000_0000_c000_000000000046);
    v38 = v45;
    if ( v45 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x160,
        (unsigned int)"shell\\ext\\zip\\archive\\archiveitemcontextmenu.cpp",
        (const char *)(unsigned int)v45,
        (int)v53);
      if ( *(_QWORD *)v53 )
        winrt::com_ptr<IShellFolder2>::unconditional_release_ref(v53);
      if ( v54 )
        winrt::com_ptr<IShellFolder2>::unconditional_release_ref(&v54);
      if ( *(_QWORD *)v55 )
        winrt::com_ptr<IShellFolder2>::unconditional_release_ref(v55);
      if ( v52 )
        winrt::com_ptr<IShellFolder2>::unconditional_release_ref(&v52);
      goto LABEL_70;
    }
    v46 = SHInvokeCommandOnContextMenu(a2, *((_QWORD *)this + 10), *(_QWORD *)v53, 0x4000000);
    v38 = v46;
    if ( v46 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x161,
        (unsigned int)"shell\\ext\\zip\\archive\\archiveitemcontextmenu.cpp",
        (const char *)(unsigned int)v46,
        0);
      if ( *(_QWORD *)v53 )
        winrt::com_ptr<IShellFolder2>::unconditional_release_ref(v53);
      if ( v54 )
        winrt::com_ptr<IShellFolder2>::unconditional_release_ref(&v54);
      if ( *(_QWORD *)v55 )
        winrt::com_ptr<IShellFolder2>::unconditional_release_ref(v55);
      if ( v52 )
        winrt::com_ptr<IShellFolder2>::unconditional_release_ref(&v52);
      goto LABEL_70;
    }
    if ( *(_QWORD *)v53 )
      winrt::com_ptr<IShellFolder2>::unconditional_release_ref(v53);
    if ( v54 )
      winrt::com_ptr<IShellFolder2>::unconditional_release_ref(&v54);
    if ( *(_QWORD *)v55 )
      winrt::com_ptr<IShellFolder2>::unconditional_release_ref(v55);
    if ( v52 )
      winrt::com_ptr<IShellFolder2>::unconditional_release_ref(&v52);
    std::wstring::_Tidy_deallocate(v56);
    std::wstring::_Tidy_deallocate(v58);
    SetCursor(hCursor);
    result = 0;
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0x165,
                           (unsigned int)"shell\\ext\\zip\\archive\\archiveitemcontextmenu.cpp",
                           v15);
  }
  return result;
}

```

## disassembly

```asm
0x180059000  push    rbx
0x180059002  push    rsi
0x180059003  push    rdi
0x180059004  push    r12
0x180059006  push    r13
0x180059008  push    r14
0x18005900a  push    r15
0x18005900c  sub     rsp, 770h
0x180059013  mov     rax, cs:__security_cookie
0x18005901a  xor     rax, rsp
0x18005901d  mov     [rsp+7A8h+var_48], rax
0x180059025  mov     r14, r8
0x180059028  mov     r12, rdx
0x18005902b  mov     r15, rcx
0x18005902e  mov     edx, 7F8Ah; lpCursorName
0x180059033  xor     ecx, ecx; hInstance
0x180059035  call    cs:__imp_LoadCursorW
0x18005903b  mov     rcx, rax; hCursor
0x18005903e  call    cs:__imp_SetCursor
0x180059044  mov     [rsp+7A8h+hCursor], rax
0x180059049  mov     esi, 1
0x18005904e  mov     ecx, esi; bShow
0x180059050  call    cs:__imp_ShowCursor
0x180059056  lea     rax, [rsp+7A8h+hCursor]
0x18005905b  mov     [rsp+7A8h+var_758], rax
0x180059060  mov     [rsp+7A8h+var_750], sil
0x180059065  mov     rcx, [r15+40h]
0x180059069  add     rcx, 40h ; '@'
0x18005906d  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180059072  lea     r8, [rsp+7A8h+var_658]; unsigned __int16 *
0x18005907a  mov     rdx, rax; unsigned __int16 *
0x18005907d  call    ?GetTempLocation@CTempFileNameArray@@QEAAJPEBGPEAGI@Z; CTempFileNameArray::GetTempLocation(ushort const *,ushort *,uint)
0x180059082  mov     ebx, eax
0x180059084  xor     r13d, r13d
0x180059087  test    eax, eax
0x180059089  jns     short loc_1800590BB
0x18005908b  mov     rcx, [rsp+7A8h]; this
0x180059093  mov     r9d, eax; char *
0x180059096  lea     r8, aShellExtZipArc_12; "shell\\ext\\zip\\archive\\archiveitemco"...
0x18005909d  mov     edx, 0FAh; void *
0x1800590a2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800590a7  nop
0x1800590a8  mov     rcx, [rsp+7A8h+hCursor]; hCursor
0x1800590ad  call    cs:__imp_SetCursor
0x1800590b3  nop
0x1800590b4  mov     eax, ebx
0x1800590b6  jmp     loc_1800599C3
0x1800590bb  mov     rax, [r15+40h]
0x1800590bf  mov     rcx, [rax+90h]
0x1800590c6  cmp     [rcx+48h], rsi
0x1800590ca  jbe     loc_1800593DF
0x1800590d0  movzx   eax, word ptr [r14+1Eh]
0x1800590d5  add     rax, 10h
0x1800590d9  lea     rcx, [r14+rax*2]
0x1800590dd  mov     [rsp+7A8h+var_778], rcx
0x1800590e2  movzx   eax, word ptr [r14+1Ch]
0x1800590e7  mov     [rsp+7A8h+var_778+8], rax
0x1800590ec  lea     rdx, [rsp+7A8h+var_778]
0x1800590f1  lea     rcx, [rsp+7A8h+var_6E0]
0x1800590f9  call    ?split_extension@@YA?AU?$pair@V?$basic_string_view@GU?$char_traits@G@std@@@std@@V12@@std@@V?$basic_string_view@GU?$char_traits@G@std@@@2@@Z; split_extension(std::basic_string_view<ushort>)
0x1800590fe  mov     ebx, 100h
0x180059103  mov     r9d, ebx; cchBufferMax
0x180059106  lea     r8, [rsp+7A8h+Buffer]; lpBuffer
0x18005910e  mov     edx, 27C9h; uID
0x180059113  lea     rdi, __ImageBase
0x18005911a  mov     rcx, rdi; hInstance
0x18005911d  call    cs:__imp_LoadStringW
0x180059123  test    eax, eax
0x180059125  jnz     short loc_180059153
0x180059127  mov     rcx, [rsp+7A8h]; this
0x18005912f  lea     r8, aShellExtZipArc_12; "shell\\ext\\zip\\archive\\archiveitemco"...
0x180059136  lea     edx, [rbx+7]; void *
0x180059139  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18005913e  mov     ebx, eax
0x180059140  mov     rcx, [rsp+7A8h+hCursor]; hCursor
0x180059145  call    cs:__imp_SetCursor
0x18005914b  nop
0x18005914c  mov     eax, ebx
0x18005914e  jmp     loc_1800599C3
0x180059153  mov     r9d, ebx; cchBufferMax
0x180059156  lea     r8, [rsp+7A8h+var_248]; lpBuffer
0x18005915e  mov     edx, 27C8h; uID
0x180059163  mov     rcx, rdi; hInstance
0x180059166  call    cs:__imp_LoadStringW
0x18005916c  test    eax, eax
0x18005916e  jnz     short loc_18005919E
0x180059170  mov     rcx, [rsp+7A8h]; this
0x180059178  lea     r8, aShellExtZipArc_12; "shell\\ext\\zip\\archive\\archiveitemco"...
0x18005917f  mov     edx, 108h; void *
0x180059184  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180059189  mov     ebx, eax
0x18005918b  mov     rcx, [rsp+7A8h+hCursor]; hCursor
0x180059190  call    cs:__imp_SetCursor
0x180059196  nop
0x180059197  mov     eax, ebx
0x180059199  jmp     loc_1800599C3
0x18005919e  lea     rax, [rsp+7A8h+Buffer]
0x1800591a6  mov     [rsp+7A8h+var_6C0], rax
0x1800591ae  lea     rdx, [rsp+7A8h+Buffer]
0x1800591b6  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800591ba  mov     rcx, rax
0x1800591bd  inc     rcx
0x1800591c0  cmp     [rdx+rcx*2], r13w
0x1800591c5  jnz     short loc_1800591BD
0x1800591c7  mov     [rsp+7A8h+var_6B8], rcx
0x1800591cf  lea     rcx, [rsp+7A8h+var_248]
0x1800591d7  mov     [rsp+7A8h+var_6B0], rcx
0x1800591df  lea     rcx, [rsp+7A8h+var_248]
0x1800591e7  inc     rax
0x1800591ea  cmp     [rcx+rax*2], r13w
0x1800591ef  jnz     short loc_1800591E7
0x1800591f1  mov     [rsp+7A8h+var_6A8], rax
0x1800591f9  lea     rax, aBat; ".bat"
0x180059200  mov     [rsp+7A8h+var_698], rax
0x180059208  mov     ecx, 4
0x18005920d  mov     [rsp+7A8h+var_690], rcx
0x180059215  lea     rax, aCmd; ".cmd"
0x18005921c  mov     [rsp+7A8h+var_688], rax
0x180059224  mov     [rsp+7A8h+var_680], rcx
0x18005922c  lea     rax, aCom; ".com"
0x180059233  mov     [rsp+7A8h+var_678], rax
0x18005923b  mov     [rsp+7A8h+var_670], rcx
0x180059243  lea     rax, aExe; ".exe"
0x18005924a  mov     [rsp+7A8h+var_668], rax
0x180059252  mov     [rsp+7A8h+var_660], rcx
0x18005925a  movups  xmm0, [rsp+7A8h+var_6E0]
0x180059262  movdqu  xmmword ptr [rsp+7A8h+var_778], xmm0
0x180059268  lea     r8, [rsp+7A8h+var_6A0]
0x180059270  lea     rdx, [rsp+7A8h+var_6C0]
0x180059278  lea     rcx, [rsp+7A8h+var_778]
0x18005927d  call    ??$matches_name@PEBV?$basic_string_view@GU?$char_traits@G@std@@@std@@@@YA_NV?$basic_string_view@GU?$char_traits@G@std@@@std@@PEBV01@1@Z; matches_name<std::basic_string_view<ushort> const *>(std::basic_string_view<ushort>,std::basic_string_view<ushort> const *,std::basic_string_view<ushort> const *)
0x180059282  test    al, al
0x180059284  jz      loc_180059324
0x18005928a  lea     rdx, [rsp+7A8h+var_658]
0x180059292  lea     rcx, [rsp+7A8h+var_6C0]
0x18005929a  call    ??$?0$$BY0BAE@G$0A@@path@filesystem@std@@QEAA@AEAY0BAE@$$CBGW4format@012@@Z; std::filesystem::path::path(ushort const (&)[260],std::filesystem::path::format)
0x18005929f  mov     rcx, [r15+40h]
0x1800592a3  add     rcx, 40h ; '@'
0x1800592a7  mov     r9b, 9
0x1800592aa  mov     r8, r12
0x1800592ad  lea     rdx, [rsp+7A8h+var_6C0]
0x1800592b5  call    ?ExtractEntireArchive@@YAJAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBVpath@filesystem@2@PEAUHWND__@@W4ExtractFlags@@@Z; ExtractEntireArchive(std::wstring const &,std::filesystem::path const &,HWND__ *,ExtractFlags)
0x1800592ba  mov     ebx, eax
0x1800592bc  lea     rcx, [rsp+7A8h+var_6C0]
0x1800592c4  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800592c9  mov     edi, 800704C7h
0x1800592ce  cmp     ebx, edi
0x1800592d0  jnz     short loc_1800592E5
0x1800592d2  mov     rcx, [rsp+7A8h+hCursor]; hCursor
0x1800592d7  call    cs:__imp_SetCursor
0x1800592dd  nop
0x1800592de  mov     eax, edi
0x1800592e0  jmp     loc_1800599C3
0x1800592e5  mov     rcx, [rsp+7A8h]; this
0x1800592ed  test    ebx, ebx
0x1800592ef  jns     short loc_180059305
0x1800592f1  mov     r9d, ebx; char *
0x1800592f4  lea     r8, aShellExtZipArc_12; "shell\\ext\\zip\\archive\\archiveitemco"...
0x1800592fb  mov     edx, 119h; void *
0x180059300  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180059305  shr     ebx, 1Fh
0x180059308  lea     rdx, [rsp+7A8h+var_658]; unsigned __int16 *
0x180059310  mov     rcx, cs:?g_pCTFA@@3PEAVCTempFileNameArray@@EA; this
0x180059317  call    ?ReferenceDirectory@CTempFileNameArray@@QEAAXPEBG@Z; CTempFileNameArray::ReferenceDirectory(ushort const *)
0x18005931c  mov     sil, bl
0x18005931f  jmp     loc_1800593E4
0x180059324  movups  xmm0, [rsp+7A8h+var_6D0]
0x18005932c  movdqu  xmmword ptr [rsp+7A8h+var_778], xmm0
0x180059332  lea     r8, [rsp+7A8h+var_658]
0x18005933a  lea     rdx, [rsp+7A8h+var_698]
0x180059342  lea     rcx, [rsp+7A8h+var_778]
0x180059347  call    ??$matches_name@PEBV?$basic_string_view@GU?$char_traits@G@std@@@std@@@@YA_NV?$basic_string_view@GU?$char_traits@G@std@@@std@@PEBV01@1@Z; matches_name<std::basic_string_view<ushort> const *>(std::basic_string_view<ushort>,std::basic_string_view<ushort> const *,std::basic_string_view<ushort> const *)
0x18005934c  test    al, al
0x18005934e  jz      loc_1800593DF
0x180059354  mov     qword ptr [rsp+7A8h+dwInitParam], r13; int
0x180059359  lea     r9, ExtractPromptDlgProc; lpDialogFunc
0x180059360  mov     r8, r12; hWndParent
0x180059363  mov     edx, 0B2h; lpTemplateName
0x180059368  mov     rcx, rdi; hInstance
0x18005936b  call    cs:__imp_DialogBoxParamW
0x180059371  cmp     rax, 2
0x180059375  jz      short loc_1800593CC
0x180059377  cmp     rax, 46Bh
0x18005937d  jnz     short loc_1800593DF
0x18005937f  mov     rcx, [r15+40h]
0x180059383  add     rcx, 40h ; '@'
0x180059387  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18005938c  xor     edx, edx; unsigned __int16 *
0x18005938e  mov     rcx, rax; unsigned __int16 *
0x180059391  call    ?ExtractArchiveWithWizard@@YAJPEBG0@Z; ExtractArchiveWithWizard(ushort const *,ushort const *)
0x180059396  mov     ebx, eax
0x180059398  test    eax, eax
0x18005939a  jns     short loc_1800593CC
0x18005939c  mov     rcx, [rsp+7A8h]; this
0x1800593a4  mov     r9d, eax; char *
0x1800593a7  lea     r8, aShellExtZipArc_12; "shell\\ext\\zip\\archive\\archiveitemco"...
0x1800593ae  mov     edx, 12Bh; void *
0x1800593b3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800593b8  nop
0x1800593b9  mov     rcx, [rsp+7A8h+hCursor]; hCursor
0x1800593be  call    cs:__imp_SetCursor
0x1800593c4  nop
0x1800593c5  mov     eax, ebx
0x1800593c7  jmp     loc_1800599C3
0x1800593cc  mov     rcx, [rsp+7A8h+hCursor]; hCursor
0x1800593d1  call    cs:__imp_SetCursor
0x1800593d7  nop
0x1800593d8  xor     eax, eax
0x1800593da  jmp     loc_1800599C3
0x1800593df  mov     edi, 800704C7h
0x1800593e4  xorps   xmm0, xmm0
0x1800593e7  movups  [rsp+7A8h+var_700], xmm0
0x1800593ef  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x1800593f7  movdqu  [rsp+7A8h+var_6F0], xmm1
0x180059400  mov     word ptr [rsp+7A8h+var_700], r13w
0x180059409  lea     rax, [r14+20h]
0x18005940d  mov     [rsp+7A8h+var_778], rax
0x180059412  movzx   ecx, word ptr [r14+1Eh]
0x180059417  movzx   eax, word ptr [r14+1Ch]
0x18005941c  add     rcx, rax
0x18005941f  mov     [rsp+7A8h+var_778+8], rcx
0x180059424  mov     r8b, r13b
0x180059427  lea     rdx, [rsp+7A8h+var_778]
0x18005942c  lea     rcx, [rsp+7A8h+var_6E0]
0x180059434  call    ??$_Convert_Source_to_wide@V?$basic_string_view@GU?$char_traits@G@std@@@std@@U_Normal_conversion@filesystem@2@@filesystem@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@AEBV?$basic_string_view@GU?$char_traits@G@std@@@1@U_Normal_conversion@01@@Z; std::filesystem::_Convert_Source_to_wide<std::basic_string_view<ushort>,std::filesystem::_Normal_conversion>(std::basic_string_view<ushort> const &,std::filesystem::_Normal_conversion)
0x180059439  nop
0x18005943a  lea     rdx, [rsp+7A8h+var_658]
0x180059442  lea     rcx, [rsp+7A8h+var_698]
0x18005944a  call    ??$?0$$BY0BAE@G$0A@@path@filesystem@std@@QEAA@AEAY0BAE@$$CBGW4format@012@@Z; std::filesystem::path::path(ushort const (&)[260],std::filesystem::path::format)
0x18005944f  nop
0x180059450  lea     r8, [rsp+7A8h+var_6E0]
0x180059458  mov     rdx, rax
0x18005945b  lea     rcx, [rsp+7A8h+var_6C0]
0x180059463  call    ??Kfilesystem@std@@YA?AVpath@01@AEBV201@0@Z; std::filesystem::operator/(std::filesystem::path const &,std::filesystem::path const &)
0x180059468  nop
0x180059469  lea     rdx, [rsp+7A8h+var_720]
0x180059471  mov     rcx, rax
0x180059474  call    ?lexically_normal@path@filesystem@std@@QEBA?AV123@XZ; std::filesystem::path::lexically_normal(void)
0x180059479  nop
0x18005947a  lea     rcx, [rsp+7A8h+var_6C0]
0x180059482  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180059487  nop
0x180059488  lea     rcx, [rsp+7A8h+var_698]
0x180059490  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180059495  nop
0x180059496  lea     rcx, [rsp+7A8h+var_6E0]
0x18005949e  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800594a3  lea     rcx, [rsp+7A8h+var_720]
0x1800594ab  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1800594b0  mov     [rsp+7A8h+var_778], rax
0x1800594b5  mov     rax, [rsp+7A8h+var_710]
0x1800594bd  mov     [rsp+7A8h+var_778+8], rax
0x1800594c2  lea     rdx, [rsp+7A8h+var_700]
0x1800594ca  lea     rcx, [rsp+7A8h+var_778]
0x1800594cf  call    ?MakeExtendedLengthPath@@YAJV?$basic_zstring_view@G@wil@@AEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; MakeExtendedLengthPath(wil::basic_zstring_view<ushort>,std::wstring &)
0x1800594d4  mov     ebx, eax
0x1800594d6  test    eax, eax
0x1800594d8  jns     short loc_180059526
0x1800594da  mov     rcx, [rsp+7A8h]; this
0x1800594e2  mov     r9d, eax; char *
0x1800594e5  lea     r8, aShellExtZipArc_12; "shell\\ext\\zip\\archive\\archiveitemco"...
0x1800594ec  mov     edx, 13Fh; void *
0x1800594f1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800594f6  nop
0x1800594f7  lea     rcx, [rsp+7A8h+var_720]
0x1800594ff  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180059504  nop
0x180059505  lea     rcx, [rsp+7A8h+var_700]
0x18005950d  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180059512  nop
0x180059513  mov     rcx, [rsp+7A8h+hCursor]; hCursor
0x180059518  call    cs:__imp_SetCursor
0x18005951e  nop
0x18005951f  mov     eax, ebx
0x180059521  jmp     loc_1800599C3
0x180059526  test    sil, sil
0x180059529  jz      loc_1800595E2
0x18005952f  lea     rdx, [rsp+7A8h+var_700]
0x180059537  lea     rcx, [rsp+7A8h+var_778]
0x18005953c  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x180059541  mov     rcx, [r15+40h]
0x180059545  add     rcx, 40h ; '@'
0x180059549  mov     byte ptr [rsp+7A8h+dwInitParam], 0Bh; int
0x18005954e  mov     r9, r12
0x180059551  mov     r8, rax
0x180059554  mov     edx, [r14+18h]
0x180059558  call    ?ExtractFromArchiveByIndex@@YAJAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@IV12@PEAUHWND__@@W4ExtractFlags@@@Z; ExtractFromArchiveByIndex(std::wstring const &,uint,std::wstring,HWND__ *,ExtractFlags)
0x18005955d  mov     ebx, eax
0x18005955f  test    eax, eax
0x180059561  jns     short loc_1800595E2
0x180059563  cmp     eax, edi
0x180059565  jnz     short loc_180059596
0x180059567  lea     rcx, [rsp+7A8h+var_720]
0x18005956f  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180059574  nop
0x180059575  lea     rcx, [rsp+7A8h+var_700]
0x18005957d  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180059582  nop
0x180059583  mov     rcx, [rsp+7A8h+hCursor]; hCursor
0x180059588  call    cs:__imp_SetCursor
  ... truncated ...
```
