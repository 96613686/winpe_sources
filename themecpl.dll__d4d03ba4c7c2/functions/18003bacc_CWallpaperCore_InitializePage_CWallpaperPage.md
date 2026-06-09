# CWallpaperCore::InitializePage(CWallpaperPage *)

- ea: `0x18003bacc`
- end: `0x18003bff1`
- name: `?InitializePage@CWallpaperCore@@QEAAJPEAVCWallpaperPage@@@Z`
- size: `1317`
- prototype: `__int64 __fastcall(CWallpaperCore *__hidden this, struct CWallpaperPage *)`
- caller_count: `1`
- callee_count: `20`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x180044280`

## callees

- `0x180002280`
- `0x180008c98`
- `0x18000af30`
- `0x180024828`
- `0x18003bacc`
- `0x180040d48`
- `0x180040f88`
- `0x1800414b8`
- `0x1800415d0`
- `0x180042fd8`
- `0x1800430ec`
- `0x1800431a0`
- `0x180043280`
- `0x180043564`
- `0x180043ad0`
- `0x180044cc0`
- `0x180052f3c`
- `0x180053f64`
- `0x1800553a4`
- `0x180057010`

## import_xrefs

- `SHELL32!__imp_SHRestricted` at `0x18003bcc0`
- `SHELL32!__imp_SHRestricted` at `0x18003bcc0`
- `SHLWAPI!__imp_IUnknown_GetSite` at `0x18003bb7d`
- `SHLWAPI!__imp_IUnknown_GetSite` at `0x18003bb7d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003bb33`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003bca3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003bb33`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003bca3`
- `USER32!GetParent` at `0x18003be1a`
- `USER32!GetParent` at `0x18003be1a`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x18003bcf1`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x18003bd1d`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x18003bdd0`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x18003bf53`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x18003bcf1`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x18003bd1d`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x18003bdd0`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x18003bf53`
- `DUI70!StrToID` at `0x18003bcdf`
- `DUI70!StrToID` at `0x18003bd0b`
- `DUI70!StrToID` at `0x18003bdbe`
- `DUI70!StrToID` at `0x18003bf41`
- `DUI70!StrToID` at `0x18003bcdf`
- `DUI70!StrToID` at `0x18003bd0b`
- `DUI70!StrToID` at `0x18003bdbe`
- `DUI70!StrToID` at `0x18003bf41`
- `DUI70!?SetLayoutPos@Element@DirectUI@@QEAAJH@Z` at `0x18003bd3e`
- `DUI70!?SetLayoutPos@Element@DirectUI@@QEAAJH@Z` at `0x18003bd52`
- `DUI70!?SetLayoutPos@Element@DirectUI@@QEAAJH@Z` at `0x18003bd3e`
- `DUI70!?SetLayoutPos@Element@DirectUI@@QEAAJH@Z` at `0x18003bd52`
- `DUI70!?GetClassInfoPtr@Combobox@DirectUI@@SAPEAUIClassInfo@2@XZ` at `0x18003bddf`
- `DUI70!?GetClassInfoPtr@Combobox@DirectUI@@SAPEAUIClassInfo@2@XZ` at `0x18003bddf`

## string_xrefs

- `0x18003bdb7`: `ComboBox_PictureFolder`

## pseudocode

```c
__int64 __fastcall CWallpaperCore::InitializePage(CWallpaperCore *this, struct CWallpaperPage *a2, __int64 a3)
{
  void *v5; // rcx
  HRESULT Site; // ebx
  IUnknown *v7; // rcx
  __int64 v8; // rcx
  __int64 v9; // r8
  unsigned int i; // ebx
  __int64 v11; // rax
  __int64 v12; // rcx
  __int64 v13; // rdx
  DWORD v14; // eax
  DirectUI::Element *v15; // rbx
  unsigned __int16 v16; // ax
  struct DirectUI::Element *Descendent; // rax
  DirectUI::Element *v18; // rbx
  DirectUI::Element *v19; // r14
  unsigned __int16 v20; // ax
  struct DirectUI::Element *v21; // rax
  DirectUI::Element *v22; // rbx
  __int64 v23; // rcx
  DirectUI::Element *v24; // rbx
  unsigned __int16 v25; // ax
  struct DirectUI::Element *v26; // r14
  __int64 ClassInfoPtr; // rbx
  HWND v28; // rax
  HWND Parent; // rax
  UINT_PTR v30; // r8
  __int64 v31; // rcx
  CWallpaperCore *v32; // rcx
  const unsigned __int16 *v33; // r8
  const unsigned __int16 *v34; // r9
  __int64 v35; // rcx
  unsigned __int16 v36; // ax
  struct DirectUI::Element *v37; // rax
  struct IObjectWithSite *v38; // rcx
  char v39; // al
  unsigned int v41; // [rsp+30h] [rbp-38h] BYREF
  int v42; // [rsp+34h] [rbp-34h] BYREF
  __int128 v43; // [rsp+38h] [rbp-30h] BYREF

  if ( (Microsoft_Windows_ThemeCPLEnableBits & 4) != 0 )
    McGenEventWrite_EventWriteTransfer(this, ThemeCPL_WallpaperPageInit_Start, a3, 1, &v43);
  v5 = (void *)*((_QWORD *)this + 25);
  *(_WORD *)((char *)this + 183) = 0;
  *((_WORD *)this + 89) = 1;
  CoTaskMemFree(v5);
  *((_QWORD *)this + 25) = 0;
  *((_QWORD *)this + 5) = a2;
  *((_QWORD *)this + 4) = a2;
  SafeRelease<IUnknown>((char *)this + 64);
  if ( *((_QWORD *)this + 8) )
  {
    Site = 0;
LABEL_8:
    DUI_WalkIUnknownElements(a2, (void (*)(struct IUnknown *, __int64))DUI_SetSiteOnUnknown, *((_QWORD *)this + 8));
    goto LABEL_9;
  }
  v7 = (IUnknown *)((char *)a2 + 208);
  if ( !a2 )
    v7 = 0;
  Site = IUnknown_GetSite(v7, &GUID_00000000_0000_0000_c000_000000000046, (void **)this + 8);
  if ( Site >= 0 )
    goto LABEL_8;
LABEL_9:
  *((_BYTE *)this + 185) = 0;
  if ( Site < 0 )
    goto LABEL_44;
  v8 = *((_QWORD *)this + 52);
  if ( !v8 )
  {
    Site = -2147467259;
    goto LABEL_44;
  }
  *((_DWORD *)this + 55) = 0;
  v41 = 0;
  Site = (*(__int64 (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v8 + 48LL))(v8, &v41);
  if ( Site < 0 )
    goto LABEL_44;
  for ( i = 0; i < v41; ++i )
  {
    v11 = *((unsigned int *)this + 55);
    if ( (unsigned int)v11 >= 0x10 )
      break;
    if ( (*(int (__fastcall **)(_QWORD, _QWORD, char *))(**((_QWORD **)this + 52) + 40LL))(
           *((_QWORD *)this + 52),
           i,
           (char *)this + 8 * v11 + 224) >= 0 )
    {
      v12 = *((_QWORD *)this + 52);
      v13 = *((unsigned int *)this + 55);
      v43 = 0;
      if ( (*(unsigned int (__fastcall **)(__int64, _QWORD, __int128 *))(*(_QWORD *)v12 + 56LL))(
             v12,
             *((_QWORD *)this + v13 + 28),
             &v43) )
      {
        CoTaskMemFree(*((LPVOID *)this + *((unsigned int *)this + 55) + 28));
      }
      else
      {
        (*(void (__fastcall **)(_QWORD, _QWORD, char *))(**((_QWORD **)this + 52) + 176LL))(
          *((_QWORD *)this + 52),
          *((_QWORD *)this + *((unsigned int *)this + 55) + 28),
          (char *)this + 4 * *((unsigned int *)this + 55) + 352);
        ++*((_DWORD *)this + 55);
      }
    }
  }
  v14 = SHRestricted(REST_NOCHANGINGWALLPAPER);
  v15 = (DirectUI::Element *)*((_QWORD *)this + 4);
  if ( v14 )
  {
    Site = DisplayPageBarricade(*((struct DirectUI::Element **)this + 4), L"PageContent", L"PolicyRestrictionBarricade");
    if ( Site < 0 )
      goto LABEL_44;
    goto LABEL_40;
  }
  v16 = StrToID(L"Browser_PictureArea");
  Descendent = DirectUI::Element::FindDescendent(v15, v16);
  v18 = (DirectUI::Element *)*((_QWORD *)this + 4);
  v19 = Descendent;
  v20 = StrToID(L"LoadingText");
  v21 = DirectUI::Element::FindDescendent(v18, v20);
  v22 = v21;
  if ( v19 && v21 )
  {
    DirectUI::Element::SetLayoutPos(v19, -3);
    DirectUI::Element::SetLayoutPos(v22, 4);
  }
  if ( !(unsigned int)CSlideshowSettings::s_PolicyAllowsSlideshow() )
    *((_BYTE *)this + 176) = 1;
  v23 = *((_QWORD *)this + 52);
  v41 = 0;
  Site = (*(__int64 (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v23 + 72LL))(v23, &v41);
  CWallpaperCore::_SetColorTile(this, v41);
  if ( Site >= 0 )
  {
    Site = CWallpaperCore::_InitializePictureArea(this);
    if ( Site >= 0 )
    {
      v24 = (DirectUI::Element *)*((_QWORD *)this + 4);
      v25 = StrToID(L"ComboBox_PictureFolder");
      v26 = DirectUI::Element::FindDescendent(v24, v25);
      ClassInfoPtr = DirectUI::Combobox::GetClassInfoPtr();
      if ( (*(__int64 (__fastcall **)(struct DirectUI::Element *))(*(_QWORD *)v26 + 280LL))(v26) == ClassInfoPtr )
      {
        v28 = (HWND)(*(__int64 (__fastcall **)(struct DirectUI::Element *))(*(_QWORD *)v26 + 360LL))(v26);
        Parent = GetParent(v28);
        if ( Parent )
          SetWindowSubclass(Parent, CWallpaperCore::s_SubclassWndProc, v30, (DWORD_PTR)this);
      }
      Site = CWallpaperCore::_InitializePathComboBox(this);
      if ( Site >= 0 )
      {
        Site = CWallpaperCore::_InitializePictureLayoutCombobox(this);
        if ( Site >= 0 )
        {
          v31 = *((_QWORD *)this + 52);
          v41 = 0;
          Site = (*(__int64 (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v31 + 88LL))(v31, &v41);
          if ( Site >= 0 )
          {
            CWallpaperCore::_SetPictureLayoutSelection(this, v41);
            if ( !*((_BYTE *)this + 176)
              || (Site = CWallpaperCore::_SwitchVisibleElement(v32, *((struct DirectUI::Element **)this + 4), v33, v34),
                  Site >= 0) )
            {
              Site = CWallpaperCore::_UpdateSlideshowEnabled(this);
              if ( Site >= 0 )
              {
                Site = CWallpaperCore::_InitializeIntervalCombobox(this);
                if ( Site >= 0 )
                {
                  v35 = *((_QWORD *)this + 52);
                  v42 = 0;
                  v41 = 0;
                  Site = (*(__int64 (__fastcall **)(__int64, int *, unsigned int *))(*(_QWORD *)v35 + 120LL))(
                           v35,
                           &v42,
                           &v41);
                  if ( Site >= 0 )
                  {
                    CWallpaperCore::_SetChangeInterval(this, v41);
                    CWallpaperCore::_SetShuffle(this, v42 & 1);
LABEL_40:
                    v36 = StrToID(L"Button_OK");
                    v37 = DirectUI::Element::FindDescendent(a2, v36);
                    v38 = (struct IObjectWithSite *)((char *)a2 + 208);
                    if ( !a2 )
                      v38 = 0;
                    Site = DUIFramework_SetRegisteredDefaultButton(v38, v37);
                  }
                }
              }
            }
          }
        }
      }
    }
  }
LABEL_44:
  v39 = Microsoft_Windows_ThemeCPLEnableBits;
  if ( (Microsoft_Windows_ThemeCPLEnableBits & 1) != 0 )
  {
    McGenEventWrite_EventWriteTransfer(v8, ThemeCPL_WallpaperPage_Ready, v9, 1, &v43);
    v39 = Microsoft_Windows_ThemeCPLEnableBits;
  }
  if ( (v39 & 4) != 0 )
    McGenEventWrite_EventWriteTransfer(v8, ThemeCPL_WallpaperPageInit_Stop, v9, 1, &v43);
  return (unsigned int)Site;
}

```

## disassembly

```asm
0x18003bacc  mov     r11, rsp
0x18003bacf  mov     [r11+18h], rbx
0x18003bad3  mov     [r11+20h], rsi
0x18003bad7  push    rdi
0x18003bad8  push    r14
0x18003bada  push    r15
0x18003badc  sub     rsp, 50h
0x18003bae0  mov     rax, cs:__security_cookie
0x18003bae7  xor     rax, rsp
0x18003baea  mov     [rsp+68h+var_20], rax
0x18003baef  test    byte ptr cs:Microsoft_Windows_ThemeCPLEnableBits, 4
0x18003baf6  mov     rsi, rdx
0x18003baf9  mov     rdi, rcx
0x18003bafc  jz      short loc_18003BB18
0x18003bafe  lea     rax, [r11-30h]
0x18003bb02  mov     r9d, 1
0x18003bb08  lea     rdx, ThemeCPL_WallpaperPageInit_Start
0x18003bb0f  mov     [r11-48h], rax
0x18003bb13  call    McGenEventWrite_EventWriteTransfer
0x18003bb18  mov     rcx, [rdi+0C8h]; pv
0x18003bb1f  xor     r15d, r15d
0x18003bb22  mov     [rdi+0B7h], r15w
0x18003bb2a  mov     word ptr [rdi+0B2h], 1
0x18003bb33  call    cs:__imp_CoTaskMemFree
0x18003bb3a  nop     dword ptr [rax+rax+00h]
0x18003bb3f  lea     r14, [rdi+40h]
0x18003bb43  mov     [rdi+0C8h], r15
0x18003bb4a  mov     rcx, r14
0x18003bb4d  mov     [rdi+28h], rsi
0x18003bb51  mov     [rdi+20h], rsi
0x18003bb55  call    ??$SafeRelease@UIUnknown@@@@YAXPEAPEAUIUnknown@@@Z; SafeRelease<IUnknown>(IUnknown * *)
0x18003bb5a  cmp     [r14], r15
0x18003bb5d  jz      short loc_18003BB64
0x18003bb5f  mov     ebx, r15d
0x18003bb62  jmp     short loc_18003BB8F
0x18003bb64  lea     rcx, [rsi+0D0h]
0x18003bb6b  test    rsi, rsi
0x18003bb6e  jnz     short loc_18003BB73
0x18003bb70  mov     rcx, r15; punk
0x18003bb73  mov     r8, r14; ppv
0x18003bb76  lea     rdx, _GUID_00000000_0000_0000_c000_000000000046; riid
0x18003bb7d  call    cs:__imp_IUnknown_GetSite
0x18003bb84  nop     dword ptr [rax+rax+00h]
0x18003bb89  mov     ebx, eax
0x18003bb8b  test    eax, eax
0x18003bb8d  js      short loc_18003BBA1
0x18003bb8f  mov     r8, [r14]; __int64
0x18003bb92  lea     rdx, ?DUI_SetSiteOnUnknown@@YAXPEAUIUnknown@@_J@Z; void (*)(struct IUnknown *, __int64)
0x18003bb99  mov     rcx, rsi; struct DirectUI::Element *
0x18003bb9c  call    ?DUI_WalkIUnknownElements@@YAXPEAVElement@DirectUI@@P6AXPEAUIUnknown@@_J@Z2@Z; DUI_WalkIUnknownElements(DirectUI::Element *,void (*)(IUnknown *,__int64),__int64)
0x18003bba1  mov     [rdi+0B9h], r15b
0x18003bba8  test    ebx, ebx
0x18003bbaa  js      loc_18003BF7F
0x18003bbb0  mov     rcx, [rdi+1A0h]
0x18003bbb7  test    rcx, rcx
0x18003bbba  jz      loc_18003BF7A
0x18003bbc0  mov     [rdi+0DCh], r15d
0x18003bbc7  lea     rdx, [rsp+68h+var_38]
0x18003bbcc  mov     [rsp+68h+var_38], r15d
0x18003bbd1  mov     rax, [rcx]
0x18003bbd4  mov     rax, [rax+30h]
0x18003bbd8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003bbdd  mov     ebx, eax
0x18003bbdf  test    eax, eax
0x18003bbe1  js      loc_18003BF7F
0x18003bbe7  mov     ebx, r15d
0x18003bbea  cmp     [rsp+68h+var_38], r15d
0x18003bbef  jbe     loc_18003BCBB
0x18003bbf5  mov     eax, [rdi+0DCh]
0x18003bbfb  cmp     eax, 10h
0x18003bbfe  jnb     loc_18003BCBB
0x18003bc04  mov     r9, [rdi+1A0h]
0x18003bc0b  add     rax, 1Ch
0x18003bc0f  mov     edx, ebx
0x18003bc11  mov     rcx, [r9]
0x18003bc14  lea     r8, [rdi+rax*8]
0x18003bc18  mov     rax, [rcx+28h]
0x18003bc1c  mov     rcx, r9
0x18003bc1f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003bc24  test    eax, eax
0x18003bc26  js      loc_18003BCAF
0x18003bc2c  mov     rcx, [rdi+1A0h]
0x18003bc33  lea     r8, [rsp+68h+var_30]
0x18003bc38  mov     edx, [rdi+0DCh]
0x18003bc3e  xorps   xmm0, xmm0
0x18003bc41  movups  [rsp+68h+var_30], xmm0
0x18003bc46  mov     rax, [rcx]
0x18003bc49  mov     rdx, [rdi+rdx*8+0E0h]
0x18003bc51  mov     rax, [rax+38h]
0x18003bc55  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003bc5a  test    eax, eax
0x18003bc5c  jnz     short loc_18003BC95
0x18003bc5e  mov     edx, [rdi+0DCh]
0x18003bc64  lea     r8, [rdi+160h]
0x18003bc6b  mov     rcx, [rdi+1A0h]
0x18003bc72  lea     r8, [r8+rdx*4]
0x18003bc76  mov     rdx, [rdi+rdx*8+0E0h]
0x18003bc7e  mov     rax, [rcx]
0x18003bc81  mov     rax, [rax+0B0h]
0x18003bc88  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003bc8d  inc     dword ptr [rdi+0DCh]
0x18003bc93  jmp     short loc_18003BCAF
0x18003bc95  mov     ecx, [rdi+0DCh]
0x18003bc9b  mov     rcx, [rdi+rcx*8+0E0h]; pv
0x18003bca3  call    cs:__imp_CoTaskMemFree
0x18003bcaa  nop     dword ptr [rax+rax+00h]
0x18003bcaf  inc     ebx
0x18003bcb1  cmp     ebx, [rsp+68h+var_38]
0x18003bcb5  jb      loc_18003BBF5
0x18003bcbb  mov     ecx, 40000011h; rest
0x18003bcc0  call    cs:__imp_SHRestricted
0x18003bcc7  nop     dword ptr [rax+rax+00h]
0x18003bccc  mov     rbx, [rdi+20h]
0x18003bcd0  test    eax, eax
0x18003bcd2  jnz     loc_18003BF1E
0x18003bcd8  lea     rcx, aBrowserPicture; "Browser_PictureArea"
0x18003bcdf  call    cs:__imp_StrToID
0x18003bce6  nop     dword ptr [rax+rax+00h]
0x18003bceb  movzx   edx, ax
0x18003bcee  mov     rcx, rbx
0x18003bcf1  call    cs:__imp_?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z; DirectUI::Element::FindDescendent(ushort)
0x18003bcf8  nop     dword ptr [rax+rax+00h]
0x18003bcfd  mov     rbx, [rdi+20h]
0x18003bd01  lea     rcx, aLoadingtext; "LoadingText"
0x18003bd08  mov     r14, rax
0x18003bd0b  call    cs:__imp_StrToID
0x18003bd12  nop     dword ptr [rax+rax+00h]
0x18003bd17  movzx   edx, ax
0x18003bd1a  mov     rcx, rbx
0x18003bd1d  call    cs:__imp_?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z; DirectUI::Element::FindDescendent(ushort)
0x18003bd24  nop     dword ptr [rax+rax+00h]
0x18003bd29  mov     rbx, rax
0x18003bd2c  test    r14, r14
0x18003bd2f  jz      short loc_18003BD5E
0x18003bd31  test    rax, rax
0x18003bd34  jz      short loc_18003BD5E
0x18003bd36  mov     edx, 0FFFFFFFDh
0x18003bd3b  mov     rcx, r14
0x18003bd3e  call    cs:__imp_?SetLayoutPos@Element@DirectUI@@QEAAJH@Z; DirectUI::Element::SetLayoutPos(int)
0x18003bd45  nop     dword ptr [rax+rax+00h]
0x18003bd4a  mov     edx, 4
0x18003bd4f  mov     rcx, rbx
0x18003bd52  call    cs:__imp_?SetLayoutPos@Element@DirectUI@@QEAAJH@Z; DirectUI::Element::SetLayoutPos(int)
0x18003bd59  nop     dword ptr [rax+rax+00h]
0x18003bd5e  call    ?s_PolicyAllowsSlideshow@CSlideshowSettings@@SAJXZ; CSlideshowSettings::s_PolicyAllowsSlideshow(void)
0x18003bd63  test    eax, eax
0x18003bd65  jnz     short loc_18003BD6E
0x18003bd67  mov     byte ptr [rdi+0B0h], 1
0x18003bd6e  mov     rcx, [rdi+1A0h]
0x18003bd75  lea     rdx, [rsp+68h+var_38]
0x18003bd7a  mov     [rsp+68h+var_38], r15d
0x18003bd7f  mov     rax, [rcx]
0x18003bd82  mov     rax, [rax+48h]
0x18003bd86  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003bd8b  mov     edx, [rsp+68h+var_38]; unsigned int
0x18003bd8f  mov     rcx, rdi; this
0x18003bd92  mov     ebx, eax
0x18003bd94  call    ?_SetColorTile@CWallpaperCore@@AEAAXK@Z; CWallpaperCore::_SetColorTile(ulong)
0x18003bd99  test    ebx, ebx
0x18003bd9b  js      loc_18003BF7F
0x18003bda1  mov     rcx, rdi; this
0x18003bda4  call    ?_InitializePictureArea@CWallpaperCore@@AEAAJXZ; CWallpaperCore::_InitializePictureArea(void)
0x18003bda9  mov     ebx, eax
0x18003bdab  test    eax, eax
0x18003bdad  js      loc_18003BF7F
0x18003bdb3  mov     rbx, [rdi+20h]
0x18003bdb7  lea     rcx, aComboboxPictur; "ComboBox_PictureFolder"
0x18003bdbe  call    cs:__imp_StrToID
0x18003bdc5  nop     dword ptr [rax+rax+00h]
0x18003bdca  movzx   edx, ax
0x18003bdcd  mov     rcx, rbx
0x18003bdd0  call    cs:__imp_?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z; DirectUI::Element::FindDescendent(ushort)
0x18003bdd7  nop     dword ptr [rax+rax+00h]
0x18003bddc  mov     r14, rax
0x18003bddf  call    cs:__imp_?GetClassInfoPtr@Combobox@DirectUI@@SAPEAUIClassInfo@2@XZ; DirectUI::Combobox::GetClassInfoPtr(void)
0x18003bde6  nop     dword ptr [rax+rax+00h]
0x18003bdeb  mov     rcx, [r14]
0x18003bdee  mov     rbx, rax
0x18003bdf1  mov     rax, [rcx+118h]
0x18003bdf8  mov     rcx, r14
0x18003bdfb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003be00  cmp     rax, rbx
0x18003be03  jnz     short loc_18003BE3D
0x18003be05  mov     rcx, [r14]
0x18003be08  mov     rax, [rcx+168h]
0x18003be0f  mov     rcx, r14
0x18003be12  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003be17  mov     rcx, rax; hWnd
0x18003be1a  call    cs:__imp_GetParent
0x18003be21  nop     dword ptr [rax+rax+00h]
0x18003be26  test    rax, rax
0x18003be29  jz      short loc_18003BE3D
0x18003be2b  mov     r9, rdi; dwRefData
0x18003be2e  lea     rdx, ?s_SubclassWndProc@CWallpaperCore@@CA_JPEAUHWND__@@I_K_J11@Z; pfnSubclass
0x18003be35  mov     rcx, rax; hWnd
0x18003be38  call    SetWindowSubclass
0x18003be3d  mov     rcx, rdi; this
0x18003be40  call    ?_InitializePathComboBox@CWallpaperCore@@AEAAJXZ; CWallpaperCore::_InitializePathComboBox(void)
0x18003be45  mov     ebx, eax
0x18003be47  test    eax, eax
0x18003be49  js      loc_18003BF7F
0x18003be4f  mov     rcx, rdi; this
0x18003be52  call    ?_InitializePictureLayoutCombobox@CWallpaperCore@@AEAAJXZ; CWallpaperCore::_InitializePictureLayoutCombobox(void)
0x18003be57  mov     ebx, eax
0x18003be59  test    eax, eax
0x18003be5b  js      loc_18003BF7F
0x18003be61  mov     rcx, [rdi+1A0h]
0x18003be68  lea     rdx, [rsp+68h+var_38]
0x18003be6d  mov     [rsp+68h+var_38], r15d
0x18003be72  mov     rax, [rcx]
0x18003be75  mov     rax, [rax+58h]
0x18003be79  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003be7e  mov     ebx, eax
0x18003be80  test    eax, eax
0x18003be82  js      loc_18003BF7F
0x18003be88  mov     edx, [rsp+68h+var_38]
0x18003be8c  mov     rcx, rdi
0x18003be8f  call    ?_SetPictureLayoutSelection@CWallpaperCore@@AEAAXW4DESKTOP_WALLPAPER_POSITION@@@Z; CWallpaperCore::_SetPictureLayoutSelection(DESKTOP_WALLPAPER_POSITION)
0x18003be94  cmp     [rdi+0B0h], r15b
0x18003be9b  jz      short loc_18003BEB0
0x18003be9d  mov     rdx, [rdi+20h]; struct DirectUI::Element *
0x18003bea1  call    ?_SwitchVisibleElement@CWallpaperCore@@AEAAJPEAVElement@DirectUI@@PEBG1@Z; CWallpaperCore::_SwitchVisibleElement(DirectUI::Element *,ushort const *,ushort const *)
0x18003bea6  mov     ebx, eax
0x18003bea8  test    eax, eax
0x18003beaa  js      loc_18003BF7F
0x18003beb0  mov     rcx, rdi; this
0x18003beb3  call    ?_UpdateSlideshowEnabled@CWallpaperCore@@AEAAJXZ; CWallpaperCore::_UpdateSlideshowEnabled(void)
0x18003beb8  mov     ebx, eax
0x18003beba  test    eax, eax
0x18003bebc  js      loc_18003BF7F
0x18003bec2  mov     rcx, rdi; this
0x18003bec5  call    ?_InitializeIntervalCombobox@CWallpaperCore@@AEAAJXZ; CWallpaperCore::_InitializeIntervalCombobox(void)
0x18003beca  mov     ebx, eax
0x18003becc  test    eax, eax
0x18003bece  js      loc_18003BF7F
0x18003bed4  mov     rcx, [rdi+1A0h]
0x18003bedb  lea     r8, [rsp+68h+var_38]
0x18003bee0  mov     [rsp+68h+var_34], r15d
0x18003bee5  lea     rdx, [rsp+68h+var_34]
0x18003beea  mov     [rsp+68h+var_38], r15d
0x18003beef  mov     rax, [rcx]
0x18003bef2  mov     rax, [rax+78h]
0x18003bef6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003befb  mov     ebx, eax
0x18003befd  test    eax, eax
0x18003beff  js      short loc_18003BF7F
0x18003bf01  mov     edx, [rsp+68h+var_38]; unsigned int
0x18003bf05  mov     rcx, rdi; this
0x18003bf08  call    ?_SetChangeInterval@CWallpaperCore@@AEAAXI@Z; CWallpaperCore::_SetChangeInterval(uint)
0x18003bf0d  mov     edx, [rsp+68h+var_34]
0x18003bf11  mov     rcx, rdi; this
0x18003bf14  and     dl, 1; bool
0x18003bf17  call    ?_SetShuffle@CWallpaperCore@@AEAAX_N@Z; CWallpaperCore::_SetShuffle(bool)
0x18003bf1c  jmp     short loc_18003BF3A
0x18003bf1e  lea     r8, aPolicyrestrict; "PolicyRestrictionBarricade"
0x18003bf25  mov     rcx, rbx; struct DirectUI::Element *
0x18003bf28  lea     rdx, aPagecontent; "PageContent"
0x18003bf2f  call    ?DisplayPageBarricade@@YAJPEAVElement@DirectUI@@PEBG1@Z; DisplayPageBarricade(DirectUI::Element *,ushort const *,ushort const *)
0x18003bf34  mov     ebx, eax
0x18003bf36  test    eax, eax
0x18003bf38  js      short loc_18003BF7F
0x18003bf3a  lea     rcx, aButtonOk; "Button_OK"
0x18003bf41  call    cs:__imp_StrToID
0x18003bf48  nop     dword ptr [rax+rax+00h]
0x18003bf4d  movzx   edx, ax
0x18003bf50  mov     rcx, rsi
0x18003bf53  call    cs:__imp_?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z; DirectUI::Element::FindDescendent(ushort)
0x18003bf5a  nop     dword ptr [rax+rax+00h]
0x18003bf5f  lea     rcx, [rsi+0D0h]
0x18003bf66  test    rsi, rsi
0x18003bf69  jnz     short loc_18003BF6E
0x18003bf6b  mov     rcx, r15; struct IObjectWithSite *
0x18003bf6e  mov     rdx, rax; struct DirectUI::Element *
0x18003bf71  call    ?DUIFramework_SetRegisteredDefaultButton@@YAJPEAUIObjectWithSite@@PEAVElement@DirectUI@@@Z; DUIFramework_SetRegisteredDefaultButton(IObjectWithSite *,DirectUI::Element *)
0x18003bf76  mov     ebx, eax
0x18003bf78  jmp     short loc_18003BF7F
0x18003bf7a  mov     ebx, 80004005h
0x18003bf7f  mov     eax, cs:Microsoft_Windows_ThemeCPLEnableBits
0x18003bf85  test    al, 1
0x18003bf87  jz      short loc_18003BFAB
0x18003bf89  lea     rax, [rsp+68h+var_30]
0x18003bf8e  mov     r9d, 1
0x18003bf94  lea     rdx, ThemeCPL_WallpaperPage_Ready
0x18003bf9b  mov     [rsp+68h+var_48], rax
0x18003bfa0  call    McGenEventWrite_EventWriteTransfer
0x18003bfa5  mov     eax, cs:Microsoft_Windows_ThemeCPLEnableBits
0x18003bfab  test    al, 4
0x18003bfad  jz      short loc_18003BFCB
0x18003bfaf  lea     rax, [rsp+68h+var_30]
0x18003bfb4  mov     r9d, 1
0x18003bfba  lea     rdx, ThemeCPL_WallpaperPageInit_Stop
0x18003bfc1  mov     [rsp+68h+var_48], rax
0x18003bfc6  call    McGenEventWrite_EventWriteTransfer
0x18003bfcb  mov     eax, ebx
0x18003bfcd  mov     rcx, [rsp+68h+var_20]
0x18003bfd2  xor     rcx, rsp; StackCookie
0x18003bfd5  call    __security_check_cookie
0x18003bfda  lea     r11, [rsp+68h+var_18]
0x18003bfdf  mov     rbx, [r11+30h]
0x18003bfe3  mov     rsi, [r11+38h]
  ... truncated ...
```
