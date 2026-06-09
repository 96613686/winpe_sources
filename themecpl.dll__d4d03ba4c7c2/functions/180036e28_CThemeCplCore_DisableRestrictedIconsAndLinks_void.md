# CThemeCplCore::_DisableRestrictedIconsAndLinks(void)

- ea: `0x180036e28`
- end: `0x18003705b`
- name: `?_DisableRestrictedIconsAndLinks@CThemeCplCore@@AEAAXXZ`
- size: `563`
- prototype: `void __fastcall(CThemeCplCore *__hidden this)`
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180035ba4`
- `0x1800375ec`

## callees

- `0x180002280`
- `0x180002f34`
- `0x180036e28`
- `0x180037064`

## import_xrefs

- `SHELL32!__imp_SHRestricted` at `0x180036e62`
- `SHELL32!__imp_SHRestricted` at `0x180036e97`
- `SHELL32!__imp_SHRestricted` at `0x180036eb3`
- `SHELL32!__imp_SHRestricted` at `0x180036f1f`
- `SHELL32!__imp_SHRestricted` at `0x180036e62`
- `SHELL32!__imp_SHRestricted` at `0x180036e97`
- `SHELL32!__imp_SHRestricted` at `0x180036eb3`
- `SHELL32!__imp_SHRestricted` at `0x180036f1f`
- `SHLWAPI!__imp_SHWindowsPolicy` at `0x180036eea`
- `SHLWAPI!__imp_SHWindowsPolicy` at `0x180036eea`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x180036fd9`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x180036fd9`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180036f72`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180036f72`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x180037006`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x180037006`
- `DUI70!StrToID` at `0x180036ff4`
- `DUI70!StrToID` at `0x180036ff4`
- `DUI70!?SetContentString@Element@DirectUI@@QEAAJPEBG@Z` at `0x18003701d`
- `DUI70!?SetContentString@Element@DirectUI@@QEAAJPEBG@Z` at `0x18003701d`
- `DUI70!?SetLayoutPos@Element@DirectUI@@QEAAJH@Z` at `0x180037035`
- `DUI70!?SetLayoutPos@Element@DirectUI@@QEAAJH@Z` at `0x180037035`

## string_xrefs

- `0x180036e79`: `DesktopBackgroundLink`
- `0x180036f01`: `SoundsLink`
- `0x180036eca`: `ScreenSaverLink`

## pseudocode

```c
void __fastcall CThemeCplCore::_DisableRestrictedIconsAndLinks(CThemeCplCore *this)
{
  bool v1; // zf
  const CHAR *v3; // rdx
  LSTATUS ValueW; // eax
  bool v5; // sf
  DirectUI::Element *v6; // rbx
  unsigned __int16 v7; // ax
  DirectUI::Element *Descendent; // rbx
  DWORD pcbData[4]; // [rsp+40h] [rbp-448h] BYREF
  WCHAR Buffer[264]; // [rsp+50h] [rbp-438h] BYREF
  _WORD pvData[264]; // [rsp+260h] [rbp-228h] BYREF

  v1 = *((_BYTE *)this + 280) == 0;
  *((_BYTE *)this + 298) = 0;
  if ( !v1 )
    *((_BYTE *)this + 298) = 1;
  if ( SHRestricted(REST_NOCHANGINGWALLPAPER) )
  {
    CThemeCplCore::_EnableIconAndLink(this, *((struct DirectUI::Element **)this + 22), L"DesktopBackgroundLink", 0);
    *((_BYTE *)this + 298) = 1;
  }
  if ( SHRestricted(REST_NODISPLAYAPPEARANCEPAGE) )
    *((_BYTE *)this + 298) = 1;
  if ( SHRestricted(REST_NODISPSCREENSAVEPG) )
  {
    CThemeCplCore::_EnableIconAndLink(this, *((struct DirectUI::Element **)this + 28), L"ScreenSaverLink", 0);
    *((_BYTE *)this + 298) = 1;
  }
  if ( SHWindowsPolicy(&POLID_NoChangingSoundScheme, v3) )
  {
    CThemeCplCore::_EnableIconAndLink(this, *((struct DirectUI::Element **)this + 26), L"SoundsLink", 0);
    *((_BYTE *)this + 298) = 1;
  }
  if ( SHRestricted(REST_NOVISUALSTYLECHOICE) )
    goto LABEL_16;
  pcbData[0] = 520;
  ValueW = RegGetValueW(
             HKEY_CURRENT_USER,
             L"Software\\Microsoft\\Windows\\CurrentVersion\\Policies\\System",
             L"SetVisualStyle",
             2u,
             0,
             pvData,
             pcbData);
  v5 = ValueW < 0;
  if ( ValueW )
  {
    pvData[0] = 0;
    v5 = ValueW < 0;
    if ( ValueW > 0 )
      v5 = 1;
  }
  if ( !v5 )
LABEL_16:
    *((_BYTE *)this + 298) = 1;
  if ( *((_BYTE *)this + 298) )
  {
    memset_0(Buffer, 0, 0x208u);
    if ( LoadStringW(g_hinst, 0x17u, Buffer, 260) )
    {
      v6 = (DirectUI::Element *)*((_QWORD *)this + 3);
      v7 = StrToID(L"GroupPolicyText");
      Descendent = DirectUI::Element::FindDescendent(v6, v7);
      if ( (int)DirectUI::Element::SetContentString(Descendent, Buffer) >= 0 )
        DirectUI::Element::SetLayoutPos(Descendent, 3);
    }
  }
}

```

## disassembly

```asm
0x180036e28  push    rbx
0x180036e2a  sub     rsp, 480h
0x180036e31  mov     rax, cs:__security_cookie
0x180036e38  xor     rax, rsp
0x180036e3b  mov     [rsp+488h+var_18], rax
0x180036e43  cmp     byte ptr [rcx+118h], 0
0x180036e4a  mov     rbx, rcx
0x180036e4d  mov     byte ptr [rcx+12Ah], 0
0x180036e54  jz      short loc_180036E5D
0x180036e56  mov     byte ptr [rcx+12Ah], 1
0x180036e5d  mov     ecx, 40000011h; rest
0x180036e62  call    cs:__imp_SHRestricted
0x180036e69  nop     dword ptr [rax+rax+00h]
0x180036e6e  test    eax, eax
0x180036e70  jz      short loc_180036E92
0x180036e72  mov     rdx, [rbx+0B0h]; struct DirectUI::Element *
0x180036e79  lea     r8, aDesktopbackgro_2; "DesktopBackgroundLink"
0x180036e80  xor     r9d, r9d; bool
0x180036e83  mov     rcx, rbx; this
0x180036e86  call    ?_EnableIconAndLink@CThemeCplCore@@AEAAXPEAVElement@DirectUI@@PEBG_N@Z; CThemeCplCore::_EnableIconAndLink(DirectUI::Element *,ushort const *,bool)
0x180036e8b  mov     byte ptr [rbx+12Ah], 1
0x180036e92  mov     ecx, 4000005Bh; rest
0x180036e97  call    cs:__imp_SHRestricted
0x180036e9e  nop     dword ptr [rax+rax+00h]
0x180036ea3  test    eax, eax
0x180036ea5  jz      short loc_180036EAE
0x180036ea7  mov     byte ptr [rbx+12Ah], 1
0x180036eae  mov     ecx, 40000078h; rest
0x180036eb3  call    cs:__imp_SHRestricted
0x180036eba  nop     dword ptr [rax+rax+00h]
0x180036ebf  test    eax, eax
0x180036ec1  jz      short loc_180036EE3
0x180036ec3  mov     rdx, [rbx+0E0h]; struct DirectUI::Element *
0x180036eca  lea     r8, aScreensaverlin; "ScreenSaverLink"
0x180036ed1  xor     r9d, r9d; bool
0x180036ed4  mov     rcx, rbx; this
0x180036ed7  call    ?_EnableIconAndLink@CThemeCplCore@@AEAAXPEAVElement@DirectUI@@PEBG_N@Z; CThemeCplCore::_EnableIconAndLink(DirectUI::Element *,ushort const *,bool)
0x180036edc  mov     byte ptr [rbx+12Ah], 1
0x180036ee3  lea     rcx, POLID_NoChangingSoundScheme; pszPath
0x180036eea  call    cs:__imp_SHWindowsPolicy
0x180036ef1  nop     dword ptr [rax+rax+00h]
0x180036ef6  test    eax, eax
0x180036ef8  jz      short loc_180036F1A
0x180036efa  mov     rdx, [rbx+0D0h]; struct DirectUI::Element *
0x180036f01  lea     r8, aSoundslink; "SoundsLink"
0x180036f08  xor     r9d, r9d; bool
0x180036f0b  mov     rcx, rbx; this
0x180036f0e  call    ?_EnableIconAndLink@CThemeCplCore@@AEAAXPEAVElement@DirectUI@@PEBG_N@Z; CThemeCplCore::_EnableIconAndLink(DirectUI::Element *,ushort const *,bool)
0x180036f13  mov     byte ptr [rbx+12Ah], 1
0x180036f1a  mov     ecx, 4000005Dh; rest
0x180036f1f  call    cs:__imp_SHRestricted
0x180036f26  nop     dword ptr [rax+rax+00h]
0x180036f2b  test    eax, eax
0x180036f2d  jnz     short loc_180036F9C
0x180036f2f  lea     rax, [rsp+488h+var_448]
0x180036f34  mov     [rsp+488h+var_448], 208h
0x180036f3c  mov     [rsp+488h+pcbData], rax; pcbData
0x180036f41  lea     r8, Value; "SetVisualStyle"
0x180036f48  lea     rax, [rsp+488h+var_228]
0x180036f50  mov     r9d, 2; dwFlags
0x180036f56  mov     [rsp+488h+pvData], rax; pvData
0x180036f5b  lea     rdx, aSoftwareMicros_0; "Software\\Microsoft\\Windows\\CurrentVe"...
0x180036f62  mov     rcx, 0FFFFFFFF80000001h; hkey
0x180036f69  mov     [rsp+488h+pdwType], 0; pdwType
0x180036f72  call    cs:__imp_RegGetValueW
0x180036f79  nop     dword ptr [rax+rax+00h]
0x180036f7e  test    eax, eax
0x180036f80  jz      short loc_180036F9A
0x180036f82  xor     ecx, ecx
0x180036f84  mov     [rsp+488h+var_228], cx
0x180036f8c  test    eax, eax
0x180036f8e  jle     short loc_180036F9A
0x180036f90  movzx   eax, ax
0x180036f93  or      eax, 80070000h
0x180036f98  test    eax, eax
0x180036f9a  js      short loc_180036FA3
0x180036f9c  mov     byte ptr [rbx+12Ah], 1
0x180036fa3  cmp     byte ptr [rbx+12Ah], 0
0x180036faa  jz      loc_180037041
0x180036fb0  xor     edx, edx; Val
0x180036fb2  lea     rcx, [rsp+488h+Buffer]; void *
0x180036fb7  mov     r8d, 208h; Size
0x180036fbd  call    memset_0
0x180036fc2  mov     rcx, cs:g_hinst; hInstance
0x180036fc9  lea     r8, [rsp+488h+Buffer]; lpBuffer
0x180036fce  mov     r9d, 104h; cchBufferMax
0x180036fd4  mov     edx, 17h; uID
0x180036fd9  call    cs:__imp_LoadStringW
0x180036fe0  nop     dword ptr [rax+rax+00h]
0x180036fe5  test    eax, eax
0x180036fe7  jz      short loc_180037041
0x180036fe9  mov     rbx, [rbx+18h]
0x180036fed  lea     rcx, aGrouppolicytex; "GroupPolicyText"
0x180036ff4  call    cs:__imp_StrToID
0x180036ffb  nop     dword ptr [rax+rax+00h]
0x180037000  movzx   edx, ax
0x180037003  mov     rcx, rbx
0x180037006  call    cs:__imp_?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z; DirectUI::Element::FindDescendent(ushort)
0x18003700d  nop     dword ptr [rax+rax+00h]
0x180037012  mov     rcx, rax
0x180037015  lea     rdx, [rsp+488h+Buffer]
0x18003701a  mov     rbx, rax
0x18003701d  call    cs:__imp_?SetContentString@Element@DirectUI@@QEAAJPEBG@Z; DirectUI::Element::SetContentString(ushort const *)
0x180037024  nop     dword ptr [rax+rax+00h]
0x180037029  test    eax, eax
0x18003702b  js      short loc_180037041
0x18003702d  mov     edx, 3
0x180037032  mov     rcx, rbx
0x180037035  call    cs:__imp_?SetLayoutPos@Element@DirectUI@@QEAAJH@Z; DirectUI::Element::SetLayoutPos(int)
0x18003703c  nop     dword ptr [rax+rax+00h]
0x180037041  mov     rcx, [rsp+488h+var_18]
0x180037049  xor     rcx, rsp; StackCookie
0x18003704c  call    __security_check_cookie
0x180037051  add     rsp, 480h
0x180037058  pop     rbx
0x180037059  retn
```
