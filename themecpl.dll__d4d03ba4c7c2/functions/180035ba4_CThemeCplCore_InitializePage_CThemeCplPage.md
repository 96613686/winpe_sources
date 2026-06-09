# CThemeCplCore::InitializePage(CThemeCplPage *)

- ea: `0x180035ba4`
- end: `0x180036053`
- name: `?InitializePage@CThemeCplCore@@QEAAJPEAVCThemeCplPage@@@Z`
- size: `1199`
- prototype: `__int64 __fastcall(CThemeCplCore *__hidden this, struct CThemeCplPage *)`
- caller_count: `1`
- callee_count: `20`
- tags: `authz_impersonation, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x180038de0`

## callees

- `0x180002280`
- `0x180008c98`
- `0x18000af30`
- `0x180024828`
- `0x1800248d4`
- `0x180035ba4`
- `0x180036ac8`
- `0x180036ba0`
- `0x180036e28`
- `0x1800370fc`
- `0x1800372fc`
- `0x180037b8c`
- `0x180037d68`
- `0x180037f18`
- `0x180038020`
- `0x180038924`
- `0x18004fcf0`
- `0x18004ff74`
- `0x180053f64`
- `0x180057010`

## import_xrefs

- `SHELL32!__imp_SHRestricted` at `0x180035e08`
- `SHELL32!__imp_SHRestricted` at `0x180035e08`
- `SHLWAPI!__imp_IUnknown_GetSite` at `0x180035c0a`
- `SHLWAPI!__imp_IUnknown_GetSite` at `0x180035c0a`
- `SHLWAPI!__imp_IsOS` at `0x180035c50`
- `SHLWAPI!__imp_IsOS` at `0x180035c50`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180035ebd`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180035ebd`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180035f04`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180035f04`
- `api-ms-win-core-synch-l1-1-0!CreateMutexW` at `0x180035d52`
- `api-ms-win-core-synch-l1-1-0!CreateMutexW` at `0x180035d52`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180035d99`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180035d99`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180035d6a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180035d6a`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180035f31`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180035f31`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180035d04`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180035d04`
- `GDI32!DeleteObject` at `0x180035f6f`
- `GDI32!DeleteObject` at `0x180035f6f`
- `USER32!SetCursor` at `0x180035e35`
- `USER32!SetCursor` at `0x180035e35`
- `USER32!LoadCursorW` at `0x180035e26`
- `USER32!LoadCursorW` at `0x180035e26`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x180035c7d`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x180035ce1`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x180035d29`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x180035e83`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x180035c7d`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x180035ce1`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x180035d29`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x180035e83`
- `DUI70!StrToID` at `0x180035c6b`
- `DUI70!StrToID` at `0x180035ccf`
- `DUI70!StrToID` at `0x180035d17`
- `DUI70!StrToID` at `0x180035e71`
- `DUI70!StrToID` at `0x180035c6b`
- `DUI70!StrToID` at `0x180035ccf`
- `DUI70!StrToID` at `0x180035d17`
- `DUI70!StrToID` at `0x180035e71`
- `DUI70!?SetContentString@Element@DirectUI@@QEAAJPEBG@Z` at `0x180035cf4`
- `DUI70!?SetContentString@Element@DirectUI@@QEAAJPEBG@Z` at `0x180035cf4`
- `DUI70!?SetBackgroundColor@Element@DirectUI@@QEAAJK@Z` at `0x180035ea0`
- `DUI70!?SetBackgroundColor@Element@DirectUI@@QEAAJK@Z` at `0x180035ea0`
- `DUI70!?SetLayoutPos@Element@DirectUI@@QEAAJH@Z` at `0x180035c99`
- `DUI70!?SetLayoutPos@Element@DirectUI@@QEAAJH@Z` at `0x180035d3b`
- `DUI70!?SetLayoutPos@Element@DirectUI@@QEAAJH@Z` at `0x180035c99`
- `DUI70!?SetLayoutPos@Element@DirectUI@@QEAAJH@Z` at `0x180035d3b`

## string_xrefs

- `0x180035eb6`: `ThemeUI.dll`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall CThemeCplCore::InitializePage(CThemeCplCore *this, struct CThemeCplPage *a2)
{
  LPVOID v4; // rcx
  int Site; // ebx
  __int64 v6; // r8
  int v7; // r8d
  int v8; // r9d
  unsigned __int16 v9; // ax
  DirectUI::Element *Descendent; // rax
  unsigned __int16 v11; // ax
  DirectUI::Element *v12; // rax
  unsigned __int16 v13; // ax
  DirectUI::Element *v14; // rax
  HANDLE MutexW; // rax
  signed int LastError; // eax
  bool v17; // al
  HCURSOR CursorW; // rax
  DirectUI::Element *v19; // rax
  DirectUI::Element *v20; // rbx
  unsigned __int16 v21; // ax
  HMODULE Library; // rbx
  int inited; // eax
  int ppv; // [rsp+20h] [rbp-30h]
  LPVOID pv; // [rsp+30h] [rbp-20h] BYREF
  LPVOID v27[2]; // [rsp+38h] [rbp-18h] BYREF

  SHTraceSQMCount(&Personalization_HubPageInit_Start, 0xF33u);
  *((_QWORD *)this + 3) = a2;
  SafeRelease<IUnknown>((char *)this + 40);
  Site = IUnknown_GetSite(
           (IUnknown *)(-(__int64)(*((_QWORD *)this + 3) != 0) & (*((_QWORD *)this + 3) + 208LL)),
           &GUID_00000000_0000_0000_c000_000000000046,
           (void **)this + 5);
  if ( Site >= 0 )
  {
    if ( !IsPersonalizationFeatureAvailable() )
    {
      Site = DisplayPageBarricade(a2, L"PageContent", L"FeatureNotPresentBarricade");
      if ( Site < 0 )
        goto LABEL_32;
      if ( IsOS(0x1Du) )
      {
        v9 = StrToID(L"ButtonWindowsAnytimeUpgrade");
        Descendent = DirectUI::Element::FindDescendent(a2, v9);
        if ( Descendent )
          DirectUI::Element::SetLayoutPos(Descendent, -3);
      }
      goto LABEL_31;
    }
    pv = 0;
    TResourceStringAllocCopyEx<unsigned short *>((int)g_hinst, 50, v7, v8, ppv, &pv);
    v11 = StrToID(L"HubInstructions");
    v12 = DirectUI::Element::FindDescendent(a2, v11);
    DirectUI::Element::SetContentString(v12, (const unsigned __int16 *)pv);
    CoTaskMemFree(pv);
    v13 = StrToID(L"ScreenSaver");
    v14 = DirectUI::Element::FindDescendent(a2, v13);
    DirectUI::Element::SetLayoutPos(v14, -1);
    MutexW = CreateMutexW(0, 0, L"Local\\{62D41444-0649-48E1-9670-1E54E5B06001}");
    *((_QWORD *)this + 38) = MutexW;
    if ( MutexW )
    {
      v17 = WaitForSingleObject(MutexW, 0) == 0;
      *((_BYTE *)this + 312) = v17;
      *((_BYTE *)this + 157) = v17;
      *((_QWORD *)this + 31) = 0;
      *((_QWORD *)this + 30) = 0;
      *((_QWORD *)this + 21) = 0;
      *((_QWORD *)this + 27) = 0;
      *((_QWORD *)this + 26) = 0;
      *((_QWORD *)this + 25) = 0;
      *((_QWORD *)this + 24) = 0;
      *((_QWORD *)this + 23) = 0;
      *((_QWORD *)this + 22) = 0;
      *((_QWORD *)this + 29) = 0;
      *((_QWORD *)this + 28) = 0;
      *((_BYTE *)this + 280) = SHRestricted(REST_NOTHEMESTAB) != 0;
      CursorW = LoadCursorW(0, (LPCWSTR)0x7F02);
      *((_QWORD *)this + 36) = SetCursor(CursorW);
      Site = CThemeCplCore::_InitNavPane(this);
      if ( Site >= 0 )
      {
        v19 = (DirectUI::Element *)*((_QWORD *)this + 22);
        if ( v19
          || (v20 = (DirectUI::Element *)*((_QWORD *)this + 3),
              v21 = StrToID(L"DesktopBackgroundIcon"),
              v19 = DirectUI::Element::FindDescendent(v20, v21),
              (*((_QWORD *)this + 22) = v19) != 0) )
        {
          DirectUI::Element::SetBackgroundColor(v19, 0);
          pv = 0;
          Library = LoadLibraryExW(L"ThemeUI.dll", 0, 2u);
          if ( Library )
          {
            if ( (int)LoadImageScaled(Library, (unsigned __int16 *)0x261, (HBITMAP *)&pv) >= 0 )
            {
              CThemeCplCore::s_UpdateDesktopBackgroundIcon(*((struct DirectUI::Element **)this + 22), (HBITMAP)pv, 1);
              FreeLibrary(Library);
            }
          }
        }
        v27[0] = 0;
        if ( CoCreateInstance(&CLSID_ThemeThumbnail, 0, 0x17u, &GUID_b08ae63c_5aa0_445b_9452_feab335e45cb, v27) >= 0 )
        {
          pv = 0;
          if ( (*(int (__fastcall **)(LPVOID, _QWORD, LPVOID *))(*(_QWORD *)v27[0] + 24LL))(v27[0], 0, &pv) >= 0 )
          {
            CThemeCplCore::_UpdateWindowColorIcon(this, (HBITMAP)pv);
            DeleteObject(pv);
          }
        }
        CThemeCplCore::_UpdateSoundsIcon(this, 0x56u);
        CThemeCplCore::_UpdateScreenSaverIcon(this, 0x58u);
        Site = CThemeCplCore::_CreateThemeChangeListener((LONG_PTR)this);
        if ( Site >= 0 )
        {
          *((_QWORD *)this + 20) = *((_QWORD *)this + 34);
          inited = CThemeCplCore::_InitThemeGallery(this);
          Site = inited;
          if ( inited >= 0 && inited != 1 )
            Site = CThemeCplCore::_UpdateThemeElements(this, 1);
          *((_BYTE *)this + 297) = 0;
        }
        v4 = v27[0];
        if ( v27[0] )
          (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v27[0] + 16LL))(v27[0]);
        if ( Site >= 0 )
        {
          CThemeCplCore::_DisableRestrictedIconsAndLinks(this);
LABEL_31:
          DUI_WalkIUnknownElements(
            *((struct DirectUI::Element **)this + 3),
            (void (*)(struct IUnknown *, __int64))DUI_SetSiteOnUnknown,
            *((_QWORD *)this + 5));
        }
      }
    }
    else
    {
      LastError = GetLastError();
      Site = LastError;
      if ( LastError > 0 )
        Site = (unsigned __int16)LastError | 0x80070000;
      if ( Site >= 0 )
        Site = -2147467259;
    }
  }
LABEL_32:
  if ( (Microsoft_Windows_ThemeCPLEnableBits & 4) != 0 )
    McGenEventWrite_EventWriteTransfer(v4, Personalization_HubPageInit_Stop, v6, 1, v27);
  return (unsigned int)Site;
}

```

## disassembly

```asm
0x180035ba4  mov     [rsp-28h+arg_10], rbx
0x180035ba9  push    rbp
0x180035baa  push    rsi
0x180035bab  push    rdi
0x180035bac  push    r14
0x180035bae  push    r15
0x180035bb0  mov     rbp, rsp
0x180035bb3  sub     rsp, 50h
0x180035bb7  mov     rax, cs:__security_cookie
0x180035bbe  xor     rax, rsp
0x180035bc1  mov     [rbp+var_8], rax
0x180035bc5  mov     rsi, rdx
0x180035bc8  mov     rdi, rcx
0x180035bcb  mov     edx, 0F33h; unsigned int
0x180035bd0  lea     rcx, Personalization_HubPageInit_Start; EventDescriptor
0x180035bd7  call    ?SHTraceSQMCount@@YAXPEBU_EVENT_DESCRIPTOR@@K@Z; SHTraceSQMCount(_EVENT_DESCRIPTOR const *,ulong)
0x180035bdc  mov     [rdi+18h], rsi
0x180035be0  lea     r14, [rdi+28h]
0x180035be4  mov     rcx, r14
0x180035be7  call    ??$SafeRelease@UIUnknown@@@@YAXPEAPEAUIUnknown@@@Z; SafeRelease<IUnknown>(IUnknown * *)
0x180035bec  mov     rax, [rdi+18h]
0x180035bf0  lea     rcx, [rax+0D0h]
0x180035bf7  neg     rax
0x180035bfa  sbb     r9, r9
0x180035bfd  and     rcx, r9; punk
0x180035c00  mov     r8, r14; ppv
0x180035c03  lea     rdx, _GUID_00000000_0000_0000_c000_000000000046; riid
0x180035c0a  call    cs:__imp_IUnknown_GetSite
0x180035c11  nop     dword ptr [rax+rax+00h]
0x180035c16  mov     ebx, eax
0x180035c18  xor     r15d, r15d
0x180035c1b  test    eax, eax
0x180035c1d  js      loc_18003600C
0x180035c23  call    ?IsPersonalizationFeatureAvailable@@YA_NXZ; IsPersonalizationFeatureAvailable(void)
0x180035c28  test    al, al
0x180035c2a  jnz     short loc_180035CAA
0x180035c2c  lea     r8, aFeaturenotpres; "FeatureNotPresentBarricade"
0x180035c33  lea     rdx, aPagecontent; "PageContent"
0x180035c3a  mov     rcx, rsi; struct DirectUI::Element *
0x180035c3d  call    ?DisplayPageBarricade@@YAJPEAVElement@DirectUI@@PEBG1@Z; DisplayPageBarricade(DirectUI::Element *,ushort const *,ushort const *)
0x180035c42  mov     ebx, eax
0x180035c44  test    eax, eax
0x180035c46  js      loc_18003600C
0x180035c4c  lea     ecx, [r15+1Dh]; dwOS
0x180035c50  call    cs:__imp_IsOS
0x180035c57  nop     dword ptr [rax+rax+00h]
0x180035c5c  test    eax, eax
0x180035c5e  jz      loc_180035FF9
0x180035c64  lea     rcx, aButtonwindowsa; "ButtonWindowsAnytimeUpgrade"
0x180035c6b  call    cs:__imp_StrToID
0x180035c72  nop     dword ptr [rax+rax+00h]
0x180035c77  movzx   edx, ax
0x180035c7a  mov     rcx, rsi
0x180035c7d  call    cs:__imp_?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z; DirectUI::Element::FindDescendent(ushort)
0x180035c84  nop     dword ptr [rax+rax+00h]
0x180035c89  test    rax, rax
0x180035c8c  jz      loc_180035FF9
0x180035c92  lea     edx, [r15-3]
0x180035c96  mov     rcx, rax
0x180035c99  call    cs:__imp_?SetLayoutPos@Element@DirectUI@@QEAAJH@Z; DirectUI::Element::SetLayoutPos(int)
0x180035ca0  nop     dword ptr [rax+rax+00h]
0x180035ca5  jmp     loc_180035FF9
0x180035caa  mov     [rbp+pv], r15
0x180035cae  lea     rax, [rbp+pv]
0x180035cb2  mov     [rsp+50h+Src], rax; Src
0x180035cb7  mov     edx, 32h ; '2'; int
0x180035cbc  mov     rcx, cs:g_hinst; int
0x180035cc3  call    ??$TResourceStringAllocCopyEx@PEAG@@YAJPEAUHINSTANCE__@@IGP6AJPEAX_KPEAPEAG@Z13@Z; TResourceStringAllocCopyEx<ushort *>(HINSTANCE__ *,uint,ushort,long (*)(void *,unsigned __int64,ushort * *),void *,ushort * *)
0x180035cc8  lea     rcx, aHubinstruction; "HubInstructions"
0x180035ccf  call    cs:__imp_StrToID
0x180035cd6  nop     dword ptr [rax+rax+00h]
0x180035cdb  movzx   edx, ax
0x180035cde  mov     rcx, rsi
0x180035ce1  call    cs:__imp_?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z; DirectUI::Element::FindDescendent(ushort)
0x180035ce8  nop     dword ptr [rax+rax+00h]
0x180035ced  mov     rdx, [rbp+pv]
0x180035cf1  mov     rcx, rax
0x180035cf4  call    cs:__imp_?SetContentString@Element@DirectUI@@QEAAJPEBG@Z; DirectUI::Element::SetContentString(ushort const *)
0x180035cfb  nop     dword ptr [rax+rax+00h]
0x180035d00  mov     rcx, [rbp+pv]; pv
0x180035d04  call    cs:__imp_CoTaskMemFree
0x180035d0b  nop     dword ptr [rax+rax+00h]
0x180035d10  lea     rcx, aScreensaver; "ScreenSaver"
0x180035d17  call    cs:__imp_StrToID
0x180035d1e  nop     dword ptr [rax+rax+00h]
0x180035d23  movzx   edx, ax
0x180035d26  mov     rcx, rsi
0x180035d29  call    cs:__imp_?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z; DirectUI::Element::FindDescendent(ushort)
0x180035d30  nop     dword ptr [rax+rax+00h]
0x180035d35  or      edx, 0FFFFFFFFh
0x180035d38  mov     rcx, rax
0x180035d3b  call    cs:__imp_?SetLayoutPos@Element@DirectUI@@QEAAJH@Z; DirectUI::Element::SetLayoutPos(int)
0x180035d42  nop     dword ptr [rax+rax+00h]
0x180035d47  lea     r8, Name; "Local\\{62D41444-0649-48E1-9670-1E54E5B"...
0x180035d4e  xor     edx, edx; bInitialOwner
0x180035d50  xor     ecx, ecx; lpMutexAttributes
0x180035d52  call    cs:__imp_CreateMutexW
0x180035d59  nop     dword ptr [rax+rax+00h]
0x180035d5e  mov     [rdi+130h], rax
0x180035d65  test    rax, rax
0x180035d68  jnz     short loc_180035D94
0x180035d6a  call    cs:__imp_GetLastError
0x180035d71  nop     dword ptr [rax+rax+00h]
0x180035d76  mov     ebx, eax
0x180035d78  test    eax, eax
0x180035d7a  jle     short loc_180035D85
0x180035d7c  movzx   ebx, ax
0x180035d7f  or      ebx, 80070000h
0x180035d85  mov     eax, 80004005h
0x180035d8a  test    ebx, ebx
0x180035d8c  cmovns  ebx, eax
0x180035d8f  jmp     loc_18003600C
0x180035d94  xor     edx, edx; dwMilliseconds
0x180035d96  mov     rcx, rax; hHandle
0x180035d99  call    cs:__imp_WaitForSingleObject
0x180035da0  nop     dword ptr [rax+rax+00h]
0x180035da5  test    eax, eax
0x180035da7  setz    al
0x180035daa  mov     [rdi+138h], al
0x180035db0  mov     [rdi+9Dh], al
0x180035db6  mov     [rdi+0F8h], r15
0x180035dbd  mov     [rdi+0F0h], r15
0x180035dc4  mov     [rdi+0A8h], r15
0x180035dcb  mov     [rdi+0D8h], r15
0x180035dd2  mov     [rdi+0D0h], r15
0x180035dd9  mov     [rdi+0C8h], r15
0x180035de0  mov     [rdi+0C0h], r15
0x180035de7  mov     [rdi+0B8h], r15
0x180035dee  mov     [rdi+0B0h], r15
0x180035df5  mov     [rdi+0E8h], r15
0x180035dfc  mov     [rdi+0E0h], r15
0x180035e03  mov     ecx, 4000005Ch; rest
0x180035e08  call    cs:__imp_SHRestricted
0x180035e0f  nop     dword ptr [rax+rax+00h]
0x180035e14  test    eax, eax
0x180035e16  setnz   al
0x180035e19  mov     [rdi+118h], al
0x180035e1f  mov     edx, 7F02h; lpCursorName
0x180035e24  xor     ecx, ecx; hInstance
0x180035e26  call    cs:__imp_LoadCursorW
0x180035e2d  nop     dword ptr [rax+rax+00h]
0x180035e32  mov     rcx, rax; hCursor
0x180035e35  call    cs:__imp_SetCursor
0x180035e3c  nop     dword ptr [rax+rax+00h]
0x180035e41  mov     [rdi+120h], rax
0x180035e48  mov     rcx, rdi; this
0x180035e4b  call    ?_InitNavPane@CThemeCplCore@@AEAAJXZ; CThemeCplCore::_InitNavPane(void)
0x180035e50  mov     ebx, eax
0x180035e52  test    eax, eax
0x180035e54  js      loc_18003600C
0x180035e5a  mov     rax, [rdi+0B0h]
0x180035e61  test    rax, rax
0x180035e64  jnz     short loc_180035E9B
0x180035e66  mov     rbx, [rdi+18h]
0x180035e6a  lea     rcx, aDesktopbackgro_1; "DesktopBackgroundIcon"
0x180035e71  call    cs:__imp_StrToID
0x180035e78  nop     dword ptr [rax+rax+00h]
0x180035e7d  movzx   edx, ax
0x180035e80  mov     rcx, rbx
0x180035e83  call    cs:__imp_?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z; DirectUI::Element::FindDescendent(ushort)
0x180035e8a  nop     dword ptr [rax+rax+00h]
0x180035e8f  mov     [rdi+0B0h], rax
0x180035e96  test    rax, rax
0x180035e99  jz      short loc_180035F10
0x180035e9b  xor     edx, edx
0x180035e9d  mov     rcx, rax
0x180035ea0  call    cs:__imp_?SetBackgroundColor@Element@DirectUI@@QEAAJK@Z; DirectUI::Element::SetBackgroundColor(ulong)
0x180035ea7  nop     dword ptr [rax+rax+00h]
0x180035eac  mov     [rbp+pv], r15
0x180035eb0  xor     edx, edx; hFile
0x180035eb2  lea     r8d, [rdx+2]; dwFlags
0x180035eb6  lea     rcx, aThemeuiDll; "ThemeUI.dll"
0x180035ebd  call    cs:__imp_LoadLibraryExW
0x180035ec4  nop     dword ptr [rax+rax+00h]
0x180035ec9  mov     rbx, rax
0x180035ecc  test    rax, rax
0x180035ecf  jz      short loc_180035F10
0x180035ed1  lea     rax, [rbp+pv]
0x180035ed5  mov     [rsp+50h+ppv], rax; HBITMAP *
0x180035eda  xor     r9d, r9d
0x180035edd  mov     edx, 261h; unsigned __int16 *
0x180035ee2  mov     rcx, rbx; HINSTANCE
0x180035ee5  call    LoadImageScaled
0x180035eea  test    eax, eax
0x180035eec  js      short loc_180035F10
0x180035eee  mov     r8b, 1; bool
0x180035ef1  mov     rdx, [rbp+pv]; HBITMAP
0x180035ef5  mov     rcx, [rdi+0B0h]; struct DirectUI::Element *
0x180035efc  call    ?s_UpdateDesktopBackgroundIcon@CThemeCplCore@@SAXPEAVElement@DirectUI@@PEAUHBITMAP__@@_N@Z; CThemeCplCore::s_UpdateDesktopBackgroundIcon(DirectUI::Element *,HBITMAP__ *,bool)
0x180035f01  mov     rcx, rbx; hLibModule
0x180035f04  call    cs:__imp_FreeLibrary
0x180035f0b  nop     dword ptr [rax+rax+00h]
0x180035f10  mov     [rbp+var_18], r15
0x180035f14  lea     rax, [rbp+var_18]
0x180035f18  mov     [rsp+50h+ppv], rax; ppv
0x180035f1d  lea     r9, _GUID_b08ae63c_5aa0_445b_9452_feab335e45cb; riid
0x180035f24  xor     edx, edx; pUnkOuter
0x180035f26  lea     r8d, [rdx+17h]; dwClsContext
0x180035f2a  lea     rcx, CLSID_ThemeThumbnail; rclsid
0x180035f31  call    cs:__imp_CoCreateInstance
0x180035f38  nop     dword ptr [rax+rax+00h]
0x180035f3d  test    eax, eax
0x180035f3f  js      short loc_180035F7B
0x180035f41  mov     [rbp+pv], r15
0x180035f45  mov     rcx, [rbp+var_18]
0x180035f49  mov     rax, [rcx]
0x180035f4c  lea     r8, [rbp+pv]
0x180035f50  xor     edx, edx
0x180035f52  mov     rax, [rax+18h]
0x180035f56  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180035f5b  test    eax, eax
0x180035f5d  js      short loc_180035F7B
0x180035f5f  mov     rdx, [rbp+pv]; HBITMAP
0x180035f63  mov     rcx, rdi; this
0x180035f66  call    ?_UpdateWindowColorIcon@CThemeCplCore@@AEAAXPEAUHBITMAP__@@@Z; CThemeCplCore::_UpdateWindowColorIcon(HBITMAP__ *)
0x180035f6b  mov     rcx, [rbp+pv]; ho
0x180035f6f  call    cs:__imp_DeleteObject
0x180035f76  nop     dword ptr [rax+rax+00h]
0x180035f7b  mov     edx, 56h ; 'V'; unsigned int
0x180035f80  mov     rcx, rdi; this
0x180035f83  call    ?_UpdateSoundsIcon@CThemeCplCore@@AEAAXI@Z; CThemeCplCore::_UpdateSoundsIcon(uint)
0x180035f88  mov     edx, 58h ; 'X'; unsigned int
0x180035f8d  mov     rcx, rdi; this
0x180035f90  call    ?_UpdateScreenSaverIcon@CThemeCplCore@@AEAAXI@Z; CThemeCplCore::_UpdateScreenSaverIcon(uint)
0x180035f95  mov     rcx, rdi; dwNewLong
0x180035f98  call    ?_CreateThemeChangeListener@CThemeCplCore@@AEAAJXZ; CThemeCplCore::_CreateThemeChangeListener(void)
0x180035f9d  mov     ebx, eax
0x180035f9f  test    eax, eax
0x180035fa1  js      short loc_180035FD7
0x180035fa3  mov     rax, [rdi+110h]
0x180035faa  mov     [rdi+0A0h], rax
0x180035fb1  mov     rcx, rdi; this
0x180035fb4  call    ?_InitThemeGallery@CThemeCplCore@@AEAAJXZ; CThemeCplCore::_InitThemeGallery(void)
0x180035fb9  mov     ebx, eax
0x180035fbb  test    eax, eax
0x180035fbd  js      short loc_180035FD0
0x180035fbf  cmp     eax, 1
0x180035fc2  jz      short loc_180035FD0
0x180035fc4  mov     dl, 1; bool
0x180035fc6  mov     rcx, rdi; this
0x180035fc9  call    ?_UpdateThemeElements@CThemeCplCore@@AEAAJ_N@Z; CThemeCplCore::_UpdateThemeElements(bool)
0x180035fce  mov     ebx, eax
0x180035fd0  mov     [rdi+129h], r15b
0x180035fd7  mov     rcx, [rbp+var_18]
0x180035fdb  test    rcx, rcx
0x180035fde  jz      short loc_180035FED
0x180035fe0  mov     rax, [rcx]
0x180035fe3  mov     rax, [rax+10h]
0x180035fe7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180035fec  nop
0x180035fed  test    ebx, ebx
0x180035fef  js      short loc_18003600C
0x180035ff1  mov     rcx, rdi; this
0x180035ff4  call    ?_DisableRestrictedIconsAndLinks@CThemeCplCore@@AEAAXXZ; CThemeCplCore::_DisableRestrictedIconsAndLinks(void)
0x180035ff9  mov     r8, [r14]; __int64
0x180035ffc  lea     rdx, ?DUI_SetSiteOnUnknown@@YAXPEAUIUnknown@@_J@Z; void (*)(struct IUnknown *, __int64)
0x180036003  mov     rcx, [rdi+18h]; struct DirectUI::Element *
0x180036007  call    ?DUI_WalkIUnknownElements@@YAXPEAVElement@DirectUI@@P6AXPEAUIUnknown@@_J@Z2@Z; DUI_WalkIUnknownElements(DirectUI::Element *,void (*)(IUnknown *,__int64),__int64)
0x18003600c  test    byte ptr cs:Microsoft_Windows_ThemeCPLEnableBits, 4
0x180036013  jz      short loc_180036030
0x180036015  lea     rax, [rbp+var_18]
0x180036019  mov     [rsp+50h+ppv], rax
0x18003601e  mov     r9d, 1
0x180036024  lea     rdx, Personalization_HubPageInit_Stop
0x18003602b  call    McGenEventWrite_EventWriteTransfer
0x180036030  mov     eax, ebx
0x180036032  mov     rcx, [rbp+var_8]
0x180036036  xor     rcx, rsp; StackCookie
0x180036039  call    __security_check_cookie
0x18003603e  mov     rbx, [rsp+50h+arg_10]
0x180036046  add     rsp, 50h
0x18003604a  pop     r15
0x18003604c  pop     r14
0x18003604e  pop     rdi
0x18003604f  pop     rsi
0x180036050  pop     rbp
0x180036051  retn
```
