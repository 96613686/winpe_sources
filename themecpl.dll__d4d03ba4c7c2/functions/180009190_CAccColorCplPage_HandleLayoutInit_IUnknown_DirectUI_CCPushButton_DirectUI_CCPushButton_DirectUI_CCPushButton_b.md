# CAccColorCplPage::HandleLayoutInit(IUnknown *,DirectUI::CCPushButton *,DirectUI::CCPushButton *,DirectUI::CCPushButton *,bool,bool *)

- ea: `0x180009190`
- end: `0x180009343`
- name: `?HandleLayoutInit@CAccColorCplPage@@UEAAJPEAUIUnknown@@PEAVCCPushButton@DirectUI@@11_NPEA_N@Z`
- size: `435`
- prototype: `__int64 __fastcall(CAccColorCplPage *__hidden this, struct IUnknown *, struct DirectUI::CCPushButton *, struct DirectUI::CCPushButton *, struct DirectUI::CCPushButton *, bool, bool *)`
- caller_count: `0`
- callee_count: `8`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callees

- `0x180002280`
- `0x180002f34`
- `0x180008c98`
- `0x180009190`
- `0x18000ada4`
- `0x18000af30`
- `0x180024828`
- `0x180057010`

## import_xrefs

- `UxTheme!__imp_QueryThemeServices` at `0x180009213`
- `UxTheme!__imp_QueryThemeServices` at `0x180009213`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800092d8`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800092d8`
- `DUI70!?SetEnabled@Element@DirectUI@@QEAAJ_N@Z` at `0x180009279`
- `DUI70!?SetEnabled@Element@DirectUI@@QEAAJ_N@Z` at `0x18000928b`
- `DUI70!?SetEnabled@Element@DirectUI@@QEAAJ_N@Z` at `0x180009279`
- `DUI70!?SetEnabled@Element@DirectUI@@QEAAJ_N@Z` at `0x18000928b`

## pseudocode

```c
__int64 __fastcall CAccColorCplPage::HandleLayoutInit(
        CAccColorCplPage *this,
        struct IUnknown *a2,
        struct DirectUI::CCPushButton *a3,
        struct DirectUI::CCPushButton *a4,
        struct DirectUI::CCPushButton *a5,
        bool a6,
        bool *a7)
{
  char ThemeServices; // al
  CAccColorCplPage *v12; // rcx
  bool v13; // bp
  int v14; // eax
  __int64 v15; // rcx
  __int64 v16; // r8
  unsigned int v17; // ebx
  char *pvData; // rdi
  DWORD pcbData; // [rsp+40h] [rbp-48h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v21; // [rsp+48h] [rbp-40h] BYREF

  if ( (Microsoft_Windows_ThemeCPLEnableBits & 8) != 0 )
    McGenEventWrite_EventWriteTransfer(
      (__int64)this,
      (const EVENT_DESCRIPTOR *)ThemeCPL_AccColorCplPageInit_Start,
      (__int64)a3,
      1u,
      &v21);
  SafeRelease<IUnknown>((char *)this + 104);
  *((_QWORD *)this + 13) = a2;
  ((void (__fastcall *)(struct IUnknown *))a2->lpVtbl->AddRef)(a2);
  ThemeServices = QueryThemeServices();
  v12 = (CAccColorCplPage *)((char *)this - 200);
  if ( (ThemeServices & 1) != 0 )
  {
    v13 = 1;
    v14 = CAccColorCplPage::_Setup(v12, *a7, a6);
    *a7 = 0;
  }
  else
  {
    v13 = 0;
    v14 = DisplayPageBarricade(v12, L"PageContentHC", L"ThemingDisabledBarricade");
  }
  v17 = v14;
  if ( v14 >= 0 )
  {
    *((_QWORD *)this + 3) = a5;
    *((_QWORD *)this + 1) = a3;
    *((_QWORD *)this + 2) = a4;
    DirectUI::Element::SetEnabled(a3, v13);
    DirectUI::Element::SetEnabled(*((DirectUI::Element **)this + 3), 0);
    pvData = (char *)this + 36;
    pcbData = 64;
    if ( RegGetValueW(HKEY_CURRENT_USER, L"Control Panel\\Appearance", L"CustomColors", 8u, 0, pvData, &pcbData) )
      memset_0(pvData, 0, 0x40u);
  }
  if ( (Microsoft_Windows_ThemeCPLEnableBits & 8) != 0 )
    McGenEventWrite_EventWriteTransfer(v15, (const EVENT_DESCRIPTOR *)ThemeCPL_AccColorCplPageInit_Stop, v16, 1u, &v21);
  return v17;
}

```

## disassembly

```asm
0x180009190  mov     r11, rsp
0x180009193  mov     [r11+10h], rbx
0x180009197  mov     [r11+18h], rbp
0x18000919b  push    rsi
0x18000919c  push    rdi
0x18000919d  push    r12
0x18000919f  push    r14
0x1800091a1  push    r15
0x1800091a3  sub     rsp, 60h
0x1800091a7  mov     rax, cs:__security_cookie
0x1800091ae  xor     rax, rsp
0x1800091b1  mov     [rsp+88h+var_30], rax
0x1800091b6  test    byte ptr cs:Microsoft_Windows_ThemeCPLEnableBits, 8
0x1800091bd  mov     r12, r9
0x1800091c0  mov     r14, [rsp+88h+arg_30]
0x1800091c8  mov     r15, r8
0x1800091cb  mov     rbx, rdx
0x1800091ce  mov     rsi, rcx
0x1800091d1  jz      short loc_1800091ED
0x1800091d3  lea     rax, [r11-40h]
0x1800091d7  mov     r9d, 1
0x1800091dd  lea     rdx, ThemeCPL_AccColorCplPageInit_Start
0x1800091e4  mov     [r11-68h], rax
0x1800091e8  call    McGenEventWrite_EventWriteTransfer
0x1800091ed  lea     rcx, [rsi+68h]
0x1800091f1  call    ??$SafeRelease@UIUnknown@@@@YAXPEAPEAUIUnknown@@@Z; SafeRelease<IUnknown>(IUnknown * *)
0x1800091f6  lea     rdi, [rsi-0C8h]
0x1800091fd  mov     rcx, rbx
0x180009200  mov     [rdi+130h], rbx
0x180009207  mov     rax, [rbx]
0x18000920a  mov     rax, [rax+8]
0x18000920e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009213  call    cs:__imp_QueryThemeServices
0x18000921a  nop     dword ptr [rax+rax+00h]
0x18000921f  mov     rcx, rdi; struct DirectUI::Element *
0x180009222  test    al, 1
0x180009224  jz      short loc_18000923F
0x180009226  mov     r8b, [rsp+88h+arg_28]; bool
0x18000922e  mov     bpl, 1
0x180009231  mov     dl, [r14]; bool
0x180009234  call    ?_Setup@CAccColorCplPage@@AEAAJ_N0@Z; CAccColorCplPage::_Setup(bool,bool)
0x180009239  mov     byte ptr [r14], 0
0x18000923d  jmp     short loc_180009255
0x18000923f  xor     bpl, bpl
0x180009242  lea     r8, aThemingdisable; "ThemingDisabledBarricade"
0x180009249  lea     rdx, aPagecontenthc; "PageContentHC"
0x180009250  call    ?DisplayPageBarricade@@YAJPEAVElement@DirectUI@@PEBG1@Z; DisplayPageBarricade(DirectUI::Element *,ushort const *,ushort const *)
0x180009255  mov     ebx, eax
0x180009257  test    eax, eax
0x180009259  js      loc_1800092F5
0x18000925f  mov     rax, [rsp+88h+arg_20]
0x180009267  mov     dl, bpl
0x18000926a  mov     rcx, r15
0x18000926d  mov     [rsi+18h], rax
0x180009271  mov     [rsi+8], r15
0x180009275  mov     [rsi+10h], r12
0x180009279  call    cs:__imp_?SetEnabled@Element@DirectUI@@QEAAJ_N@Z; DirectUI::Element::SetEnabled(bool)
0x180009280  nop     dword ptr [rax+rax+00h]
0x180009285  mov     rcx, [rsi+18h]
0x180009289  xor     edx, edx
0x18000928b  call    cs:__imp_?SetEnabled@Element@DirectUI@@QEAAJ_N@Z; DirectUI::Element::SetEnabled(bool)
0x180009292  nop     dword ptr [rax+rax+00h]
0x180009297  mov     esi, 40h ; '@'
0x18000929c  lea     rax, [rsp+88h+var_48]
0x1800092a1  mov     [rsp+88h+pcbData], rax; pcbData
0x1800092a6  lea     r8, ValueName; "CustomColors"
0x1800092ad  add     rdi, 0ECh
0x1800092b4  mov     [rsp+88h+var_48], esi
0x1800092b8  mov     [rsp+88h+pvData], rdi; pvData
0x1800092bd  lea     rdx, SubKey; "Control Panel\\Appearance"
0x1800092c4  lea     r9d, [rsi-38h]; dwFlags
0x1800092c8  mov     [rsp+88h+pdwType], 0; pdwType
0x1800092d1  mov     rcx, 0FFFFFFFF80000001h; hkey
0x1800092d8  call    cs:__imp_RegGetValueW
0x1800092df  nop     dword ptr [rax+rax+00h]
0x1800092e4  test    eax, eax
0x1800092e6  jz      short loc_1800092F5
0x1800092e8  mov     r8d, esi; Size
0x1800092eb  xor     edx, edx; Val
0x1800092ed  mov     rcx, rdi; void *
0x1800092f0  call    memset_0
0x1800092f5  test    byte ptr cs:Microsoft_Windows_ThemeCPLEnableBits, 8
0x1800092fc  jz      short loc_18000931A
0x1800092fe  lea     rax, [rsp+88h+var_40]
0x180009303  mov     r9d, 1
0x180009309  lea     rdx, ThemeCPL_AccColorCplPageInit_Stop
0x180009310  mov     [rsp+88h+pdwType], rax
0x180009315  call    McGenEventWrite_EventWriteTransfer
0x18000931a  mov     eax, ebx
0x18000931c  mov     rcx, [rsp+88h+var_30]
0x180009321  xor     rcx, rsp; StackCookie
0x180009324  call    __security_check_cookie
0x180009329  lea     r11, [rsp+88h+var_28]
0x18000932e  mov     rbx, [r11+38h]
0x180009332  mov     rbp, [r11+40h]
0x180009336  mov     rsp, r11
0x180009339  pop     r15
0x18000933b  pop     r14
0x18000933d  pop     r12
0x18000933f  pop     rdi
0x180009340  pop     rsi
0x180009341  retn
```
