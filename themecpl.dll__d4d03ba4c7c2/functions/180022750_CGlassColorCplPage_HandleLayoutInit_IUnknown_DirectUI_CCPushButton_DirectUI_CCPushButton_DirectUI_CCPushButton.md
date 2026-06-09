# CGlassColorCplPage::HandleLayoutInit(IUnknown *,DirectUI::CCPushButton *,DirectUI::CCPushButton *,DirectUI::CCPushButton *,bool,bool *)

- ea: `0x180022750`
- end: `0x18002293e`
- name: `?HandleLayoutInit@CGlassColorCplPage@@UEAAJPEAUIUnknown@@PEAVCCPushButton@DirectUI@@11_NPEA_N@Z`
- size: `494`
- prototype: `__int64 __fastcall(CGlassColorCplPage *__hidden this, struct IUnknown *, struct DirectUI::CCPushButton *, struct DirectUI::CCPushButton *, struct DirectUI::CCPushButton *, bool, bool *)`
- caller_count: `0`
- callee_count: `8`
- tags: `registry_config, installer_update, broker_com_uri`

## callees

- `0x180008c98`
- `0x180022750`
- `0x180023aa4`
- `0x180024828`
- `0x1800248d4`
- `0x18004ef88`
- `0x1800553a4`
- `0x180057010`

## import_xrefs

- `SHELL32!__imp_SHRestricted` at `0x18002278a`
- `SHELL32!__imp_SHRestricted` at `0x18002278a`
- `SHLWAPI!__imp_IsOS` at `0x1800227d4`
- `SHLWAPI!__imp_IsOS` at `0x1800227d4`
- `dwmapi!__imp_DwmpIsCompositionCapable` at `0x18002284c`
- `dwmapi!__imp_DwmpIsCompositionCapable` at `0x18002284c`
- `USER32!GetSystemMetrics` at `0x180022839`
- `USER32!GetSystemMetrics` at `0x180022839`
- `USER32!GetAncestor` at `0x180022900`
- `USER32!GetAncestor` at `0x180022900`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x180022801`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x180022801`
- `DUI70!StrToID` at `0x1800227ef`
- `DUI70!StrToID` at `0x1800227ef`
- `DUI70!?SetEnabled@Element@DirectUI@@QEAAJ_N@Z` at `0x1800228a9`
- `DUI70!?SetEnabled@Element@DirectUI@@QEAAJ_N@Z` at `0x1800228a9`
- `DUI70!?SetLayoutPos@Element@DirectUI@@QEAAJH@Z` at `0x18002281e`
- `DUI70!?SetLayoutPos@Element@DirectUI@@QEAAJH@Z` at `0x1800228ce`
- `DUI70!?SetLayoutPos@Element@DirectUI@@QEAAJH@Z` at `0x18002281e`
- `DUI70!?SetLayoutPos@Element@DirectUI@@QEAAJH@Z` at `0x1800228ce`
- `DUI70!?SetVisible@Element@DirectUI@@QEAAJ_N@Z` at `0x1800228ba`
- `DUI70!?SetVisible@Element@DirectUI@@QEAAJ_N@Z` at `0x1800228ba`

## string_xrefs

- `0x18002287f`: `DesktopCompositionDisabledBarricade`

## pseudocode

```c
__int64 __fastcall CGlassColorCplPage::HandleLayoutInit(
        CGlassColorCplPage *this,
        struct IUnknown *a2,
        struct DirectUI::CCPushButton *a3,
        struct DirectUI::CCPushButton *a4,
        struct DirectUI::CCPushButton *a5,
        bool a6,
        bool *a7)
{
  const unsigned __int16 *v9; // r8
  int ElementRootHWND; // edi
  unsigned __int16 v11; // ax
  DirectUI::Element *Descendent; // rax
  unsigned int SystemMetrics; // eax
  bool *v14; // rbx
  int v15; // eax
  DirectUI::Element *v16; // rbx
  HWND Ancestor; // rax
  UINT_PTR v18; // r8
  HWND v19; // rbx
  HWND hwnd; // [rsp+50h] [rbp+8h] BYREF

  SafeRelease<IUnknown>((char *)this + 120);
  *((_QWORD *)this + 15) = a2;
  ((void (__fastcall *)(struct IUnknown *))a2->lpVtbl->AddRef)(a2);
  if ( SHRestricted(REST_NODISPLAYAPPEARANCEPAGE) )
  {
    v9 = L"PolicyRestrictionBarricade";
    goto LABEL_12;
  }
  if ( IsPersonalizationFeatureAvailable() )
  {
    LODWORD(hwnd) = 0;
    SystemMetrics = GetSystemMetrics(4096);
    if ( (int)DwmpIsCompositionCapable(SystemMetrics, &hwnd) >= 0 && (_DWORD)hwnd )
    {
      v14 = a7;
      v15 = CGlassColorCplPage::_Setup((CGlassColorCplPage *)((char *)this - 208), *a7, a6);
      *v14 = 0;
      goto LABEL_13;
    }
    v9 = L"DesktopCompositionDisabledBarricade";
LABEL_12:
    v15 = DisplayPageBarricade((CGlassColorCplPage *)((char *)this - 208), L"PageContent", v9);
LABEL_13:
    ElementRootHWND = v15;
    if ( v15 < 0 )
      return (unsigned int)ElementRootHWND;
    goto LABEL_14;
  }
  ElementRootHWND = DisplayPageBarricade(
                      (CGlassColorCplPage *)((char *)this - 208),
                      L"PageContent",
                      L"FeatureNotPresentBarricade");
  if ( ElementRootHWND < 0 )
    return (unsigned int)ElementRootHWND;
  if ( IsOS(0x1Du) )
  {
    v11 = StrToID(L"ButtonWindowsAnytimeUpgrade");
    Descendent = DirectUI::Element::FindDescendent((CGlassColorCplPage *)((char *)this - 208), v11);
    if ( Descendent )
      DirectUI::Element::SetLayoutPos(Descendent, -3);
  }
LABEL_14:
  v16 = a5;
  DirectUI::Element::SetEnabled(a5, 0);
  DirectUI::Element::SetVisible(v16, 0);
  DirectUI::Element::SetLayoutPos(v16, -3);
  hwnd = 0;
  ElementRootHWND = DUI_GetElementRootHWND((CGlassColorCplPage *)((char *)this - 208), &hwnd);
  if ( ElementRootHWND >= 0 )
  {
    Ancestor = GetAncestor(hwnd, 2u);
    v19 = Ancestor;
    if ( Ancestor )
    {
      if ( SetWindowSubclass(Ancestor, CGlassColorCplPage::s_SubclassWndProc, v18, (DWORD_PTR)this - 208) )
      {
        *((_QWORD *)this + 9) = v19;
        *((_BYTE *)this + 80) = 0;
      }
    }
  }
  return (unsigned int)ElementRootHWND;
}

```

## disassembly

```asm
0x180022750  push    rbx
0x180022752  push    rbp
0x180022753  push    rsi
0x180022754  push    rdi
0x180022755  sub     rsp, 28h
0x180022759  mov     rbp, rcx
0x18002275c  mov     rbx, rdx
0x18002275f  add     rcx, 78h ; 'x'
0x180022763  call    ??$SafeRelease@UIUnknown@@@@YAXPEAPEAUIUnknown@@@Z; SafeRelease<IUnknown>(IUnknown * *)
0x180022768  lea     rsi, [rbp-0D0h]
0x18002276f  mov     rcx, rbx
0x180022772  mov     [rsi+148h], rbx
0x180022779  mov     rax, [rbx]
0x18002277c  mov     rax, [rax+8]
0x180022780  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022785  mov     ecx, 4000005Bh; rest
0x18002278a  call    cs:__imp_SHRestricted
0x180022791  nop     dword ptr [rax+rax+00h]
0x180022796  test    eax, eax
0x180022798  jz      short loc_1800227A6
0x18002279a  lea     r8, aPolicyrestrict; "PolicyRestrictionBarricade"
0x1800227a1  jmp     loc_180022886
0x1800227a6  call    ?IsPersonalizationFeatureAvailable@@YA_NXZ; IsPersonalizationFeatureAvailable(void)
0x1800227ab  test    al, al
0x1800227ad  jnz     short loc_18002282C
0x1800227af  lea     r8, aFeaturenotpres; "FeatureNotPresentBarricade"
0x1800227b6  mov     rcx, rsi; struct DirectUI::Element *
0x1800227b9  lea     rdx, aPagecontent; "PageContent"
0x1800227c0  call    ?DisplayPageBarricade@@YAJPEAVElement@DirectUI@@PEBG1@Z; DisplayPageBarricade(DirectUI::Element *,ushort const *,ushort const *)
0x1800227c5  mov     edi, eax
0x1800227c7  test    eax, eax
0x1800227c9  js      loc_180022932
0x1800227cf  mov     ecx, 1Dh; dwOS
0x1800227d4  call    cs:__imp_IsOS
0x1800227db  nop     dword ptr [rax+rax+00h]
0x1800227e0  test    eax, eax
0x1800227e2  jz      loc_18002289F
0x1800227e8  lea     rcx, aButtonwindowsa; "ButtonWindowsAnytimeUpgrade"
0x1800227ef  call    cs:__imp_StrToID
0x1800227f6  nop     dword ptr [rax+rax+00h]
0x1800227fb  movzx   edx, ax
0x1800227fe  mov     rcx, rsi
0x180022801  call    cs:__imp_?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z; DirectUI::Element::FindDescendent(ushort)
0x180022808  nop     dword ptr [rax+rax+00h]
0x18002280d  test    rax, rax
0x180022810  jz      loc_18002289F
0x180022816  mov     edx, 0FFFFFFFDh
0x18002281b  mov     rcx, rax
0x18002281e  call    cs:__imp_?SetLayoutPos@Element@DirectUI@@QEAAJH@Z; DirectUI::Element::SetLayoutPos(int)
0x180022825  nop     dword ptr [rax+rax+00h]
0x18002282a  jmp     short loc_18002289F
0x18002282c  mov     ecx, 1000h; nIndex
0x180022831  mov     dword ptr [rsp+48h+hwnd], 0
0x180022839  call    cs:__imp_GetSystemMetrics
0x180022840  nop     dword ptr [rax+rax+00h]
0x180022845  mov     ecx, eax
0x180022847  lea     rdx, [rsp+48h+hwnd]
0x18002284c  call    cs:__imp_DwmpIsCompositionCapable
0x180022853  nop     dword ptr [rax+rax+00h]
0x180022858  test    eax, eax
0x18002285a  js      short loc_18002287F
0x18002285c  cmp     dword ptr [rsp+48h+hwnd], 0
0x180022861  jz      short loc_18002287F
0x180022863  mov     rbx, [rsp+48h+arg_30]
0x18002286b  mov     rcx, rsi; this
0x18002286e  mov     r8b, [rsp+48h+arg_28]; bool
0x180022873  mov     dl, [rbx]; bool
0x180022875  call    ?_Setup@CGlassColorCplPage@@AEAAJ_N0@Z; CGlassColorCplPage::_Setup(bool,bool)
0x18002287a  mov     byte ptr [rbx], 0
0x18002287d  jmp     short loc_180022895
0x18002287f  lea     r8, aDesktopcomposi; "DesktopCompositionDisabledBarricade"
0x180022886  lea     rdx, aPagecontent; "PageContent"
0x18002288d  mov     rcx, rsi; struct DirectUI::Element *
0x180022890  call    ?DisplayPageBarricade@@YAJPEAVElement@DirectUI@@PEBG1@Z; DisplayPageBarricade(DirectUI::Element *,ushort const *,ushort const *)
0x180022895  mov     edi, eax
0x180022897  test    eax, eax
0x180022899  js      loc_180022932
0x18002289f  mov     rbx, [rsp+48h+arg_20]
0x1800228a4  xor     edx, edx
0x1800228a6  mov     rcx, rbx
0x1800228a9  call    cs:__imp_?SetEnabled@Element@DirectUI@@QEAAJ_N@Z; DirectUI::Element::SetEnabled(bool)
0x1800228b0  nop     dword ptr [rax+rax+00h]
0x1800228b5  xor     edx, edx
0x1800228b7  mov     rcx, rbx
0x1800228ba  call    cs:__imp_?SetVisible@Element@DirectUI@@QEAAJ_N@Z; DirectUI::Element::SetVisible(bool)
0x1800228c1  nop     dword ptr [rax+rax+00h]
0x1800228c6  mov     edx, 0FFFFFFFDh
0x1800228cb  mov     rcx, rbx
0x1800228ce  call    cs:__imp_?SetLayoutPos@Element@DirectUI@@QEAAJH@Z; DirectUI::Element::SetLayoutPos(int)
0x1800228d5  nop     dword ptr [rax+rax+00h]
0x1800228da  lea     rdx, [rsp+48h+hwnd]; HWND *
0x1800228df  mov     [rsp+48h+hwnd], 0
0x1800228e8  mov     rcx, rsi; struct DirectUI::Element *
0x1800228eb  call    ?DUI_GetElementRootHWND@@YAJPEAVElement@DirectUI@@PEAPEAUHWND__@@@Z; DUI_GetElementRootHWND(DirectUI::Element *,HWND__ * *)
0x1800228f0  mov     edi, eax
0x1800228f2  test    eax, eax
0x1800228f4  js      short loc_180022932
0x1800228f6  mov     rcx, [rsp+48h+hwnd]; hwnd
0x1800228fb  mov     edx, 2; gaFlags
0x180022900  call    cs:__imp_GetAncestor
0x180022907  nop     dword ptr [rax+rax+00h]
0x18002290c  mov     rbx, rax
0x18002290f  test    rax, rax
0x180022912  jz      short loc_180022932
0x180022914  mov     r9, rsi; dwRefData
0x180022917  lea     rdx, ?s_SubclassWndProc@CGlassColorCplPage@@CA_JPEAUHWND__@@I_K_J11@Z; pfnSubclass
0x18002291e  mov     rcx, rax; hWnd
0x180022921  call    SetWindowSubclass
0x180022926  test    eax, eax
0x180022928  jz      short loc_180022932
0x18002292a  mov     [rbp+48h], rbx
0x18002292e  mov     byte ptr [rbp+50h], 0
0x180022932  mov     eax, edi
0x180022934  add     rsp, 28h
0x180022938  pop     rdi
0x180022939  pop     rsi
0x18002293a  pop     rbp
0x18002293b  pop     rbx
0x18002293c  retn
```
