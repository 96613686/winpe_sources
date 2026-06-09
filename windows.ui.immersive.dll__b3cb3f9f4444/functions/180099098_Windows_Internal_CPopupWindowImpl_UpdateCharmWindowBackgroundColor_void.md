# Windows::Internal::CPopupWindowImpl::_UpdateCharmWindowBackgroundColor(void)

- ea: `0x180099098`
- end: `0x1800992cb`
- name: `?_UpdateCharmWindowBackgroundColor@CPopupWindowImpl@Internal@Windows@@AEAAXXZ`
- size: `563`
- prototype: `void __fastcall(Windows::Internal::CPopupWindowImpl *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `installer_update, broker_com_uri`

## callers

- `0x18009824c`

## callees

- `0x18001bf90`
- `0x180054130`
- `0x180093870`
- `0x180099098`

## import_xrefs

- `USER32!SetWindowCompositionAttribute` at `0x180099214`
- `USER32!SetWindowCompositionAttribute` at `0x180099214`
- `UxTheme!IsCompositionActive` at `0x1800991b9`
- `UxTheme!IsCompositionActive` at `0x1800991b9`
- `DUI70!?SetBackgroundColor@Element@DirectUI@@QEAAJK@Z` at `0x1800992a8`
- `DUI70!?SetBackgroundColor@Element@DirectUI@@QEAAJK@Z` at `0x1800992a8`
- `DUI70!?GetHWND@NativeHWNDHost@DirectUI@@QEAAPEAUHWND__@@XZ` at `0x180099200`
- `DUI70!?GetHWND@NativeHWNDHost@DirectUI@@QEAAPEAUHWND__@@XZ` at `0x180099200`
- `DUI70!?GetElement@NativeHWNDHost@DirectUI@@QEAAPEAVElement@2@XZ` at `0x1800990b3`
- `DUI70!?GetElement@NativeHWNDHost@DirectUI@@QEAAPEAVElement@2@XZ` at `0x1800990ed`
- `DUI70!?GetElement@NativeHWNDHost@DirectUI@@QEAAPEAVElement@2@XZ` at `0x180099127`
- `DUI70!?GetElement@NativeHWNDHost@DirectUI@@QEAAPEAVElement@2@XZ` at `0x180099297`
- `DUI70!?GetElement@NativeHWNDHost@DirectUI@@QEAAPEAVElement@2@XZ` at `0x1800990b3`
- `DUI70!?GetElement@NativeHWNDHost@DirectUI@@QEAAPEAVElement@2@XZ` at `0x1800990ed`
- `DUI70!?GetElement@NativeHWNDHost@DirectUI@@QEAAPEAVElement@2@XZ` at `0x180099127`
- `DUI70!?GetElement@NativeHWNDHost@DirectUI@@QEAAPEAVElement@2@XZ` at `0x180099297`
- `DUI70!?RemoveLocalValue@Element@DirectUI@@QEAAJPEBUPropertyInfo@2@@Z` at `0x180099237`
- `DUI70!?RemoveLocalValue@Element@DirectUI@@QEAAJPEBUPropertyInfo@2@@Z` at `0x180099255`
- `DUI70!?RemoveLocalValue@Element@DirectUI@@QEAAJPEBUPropertyInfo@2@@Z` at `0x180099273`
- `DUI70!?RemoveLocalValue@Element@DirectUI@@QEAAJPEBUPropertyInfo@2@@Z` at `0x180099237`
- `DUI70!?RemoveLocalValue@Element@DirectUI@@QEAAJPEBUPropertyInfo@2@@Z` at `0x180099255`
- `DUI70!?RemoveLocalValue@Element@DirectUI@@QEAAJPEBUPropertyInfo@2@@Z` at `0x180099273`
- `DUI70!?ClassProp@Element@DirectUI@@SAPEBUPropertyInfo@2@XZ` at `0x180099225`
- `DUI70!?ClassProp@Element@DirectUI@@SAPEBUPropertyInfo@2@XZ` at `0x180099243`
- `DUI70!?ClassProp@Element@DirectUI@@SAPEBUPropertyInfo@2@XZ` at `0x180099261`
- `DUI70!?ClassProp@Element@DirectUI@@SAPEBUPropertyInfo@2@XZ` at `0x180099225`
- `DUI70!?ClassProp@Element@DirectUI@@SAPEBUPropertyInfo@2@XZ` at `0x180099243`
- `DUI70!?ClassProp@Element@DirectUI@@SAPEBUPropertyInfo@2@XZ` at `0x180099261`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x1800990db`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x180099115`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x18009914f`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x1800990db`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x180099115`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x18009914f`
- `DUI70!StrToID` at `0x1800990c9`
- `DUI70!StrToID` at `0x180099103`
- `DUI70!StrToID` at `0x18009913d`
- `DUI70!StrToID` at `0x1800990c9`
- `DUI70!StrToID` at `0x180099103`
- `DUI70!StrToID` at `0x18009913d`
- `DUI70!?SetClass@Element@DirectUI@@QEAAJPEBG@Z` at `0x180099175`
- `DUI70!?SetClass@Element@DirectUI@@QEAAJPEBG@Z` at `0x18009918b`
- `DUI70!?SetClass@Element@DirectUI@@QEAAJPEBG@Z` at `0x1800991a1`
- `DUI70!?SetClass@Element@DirectUI@@QEAAJPEBG@Z` at `0x180099175`
- `DUI70!?SetClass@Element@DirectUI@@QEAAJPEBG@Z` at `0x18009918b`
- `DUI70!?SetClass@Element@DirectUI@@QEAAJPEBG@Z` at `0x1800991a1`

## pseudocode

```c
void __fastcall Windows::Internal::CPopupWindowImpl::_UpdateCharmWindowBackgroundColor(
        Windows::Internal::CPopupWindowImpl *this)
{
  DirectUI::Element *Element; // rbx
  unsigned __int16 v3; // ax
  DirectUI::Element *Descendent; // rsi
  DirectUI::Element *v5; // rbx
  unsigned __int16 v6; // ax
  DirectUI::Element *v7; // rbp
  DirectUI::Element *v8; // rbx
  unsigned __int16 v9; // ax
  DirectUI::Element *v10; // rbx
  unsigned int Color; // ebx
  HWND HWND; // rax
  const struct DirectUI::PropertyInfo *v13; // rax
  const struct DirectUI::PropertyInfo *v14; // rax
  const struct DirectUI::PropertyInfo *v15; // rax
  DirectUI::Element *v16; // rax
  _QWORD v17[3]; // [rsp+20h] [rbp-58h] BYREF
  __int128 v18; // [rsp+38h] [rbp-40h] BYREF

  Element = DirectUI::NativeHWNDHost::GetElement(this);
  v3 = StrToID(L"CharmWindowBorder");
  Descendent = DirectUI::Element::FindDescendent(Element, v3);
  v5 = DirectUI::NativeHWNDHost::GetElement(this);
  v6 = StrToID(L"ContentArea");
  v7 = DirectUI::Element::FindDescendent(v5, v6);
  v8 = DirectUI::NativeHWNDHost::GetElement(this);
  v9 = StrToID(L"TitleBarBackground");
  v10 = DirectUI::Element::FindDescendent(v8, v9);
  if ( (unsigned int)IsHighContrast() )
  {
    DirectUI::Element::SetClass(v7, L"HighContrast");
    DirectUI::Element::SetClass(Descendent, L"HighContrast");
    DirectUI::Element::SetClass(v10, L"HighContrast");
LABEL_3:
    Color = CImmersiveColor::GetColor(41);
    goto LABEL_4;
  }
  v13 = (const struct DirectUI::PropertyInfo *)DirectUI::Element::ClassProp();
  DirectUI::Element::RemoveLocalValue(v7, v13);
  v14 = (const struct DirectUI::PropertyInfo *)DirectUI::Element::ClassProp();
  DirectUI::Element::RemoveLocalValue(Descendent, v14);
  v15 = (const struct DirectUI::PropertyInfo *)DirectUI::Element::ClassProp();
  DirectUI::Element::RemoveLocalValue(v10, v15);
  if ( (*((_BYTE *)this + 344) & 1) == 0 )
    goto LABEL_3;
  Color = *((_DWORD *)this + 85);
LABEL_4:
  if ( IsCompositionActive() )
  {
    v17[0] = 19;
    v18 = 0;
    LODWORD(v18) = 1;
    DWORD2(v18) = Color;
    v17[1] = &v18;
    v17[2] = 16;
    HWND = DirectUI::NativeHWNDHost::GetHWND(this);
    SetWindowCompositionAttribute(HWND, v17);
  }
  else
  {
    v16 = DirectUI::NativeHWNDHost::GetElement(this);
    DirectUI::Element::SetBackgroundColor(v16, Color);
  }
}

```

## disassembly

```asm
0x180099098  push    rbx
0x18009909a  push    rbp
0x18009909b  push    rsi
0x18009909c  push    rdi
0x18009909d  sub     rsp, 58h
0x1800990a1  mov     rax, cs:__security_cookie
0x1800990a8  xor     rax, rsp
0x1800990ab  mov     [rsp+78h+var_30], rax
0x1800990b0  mov     rdi, rcx
0x1800990b3  call    cs:__imp_?GetElement@NativeHWNDHost@DirectUI@@QEAAPEAVElement@2@XZ; DirectUI::NativeHWNDHost::GetElement(void)
0x1800990ba  nop     dword ptr [rax+rax+00h]
0x1800990bf  lea     rcx, aCharmwindowbor; "CharmWindowBorder"
0x1800990c6  mov     rbx, rax
0x1800990c9  call    cs:__imp_StrToID
0x1800990d0  nop     dword ptr [rax+rax+00h]
0x1800990d5  movzx   edx, ax
0x1800990d8  mov     rcx, rbx
0x1800990db  call    cs:__imp_?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z; DirectUI::Element::FindDescendent(ushort)
0x1800990e2  nop     dword ptr [rax+rax+00h]
0x1800990e7  mov     rcx, rdi
0x1800990ea  mov     rsi, rax
0x1800990ed  call    cs:__imp_?GetElement@NativeHWNDHost@DirectUI@@QEAAPEAVElement@2@XZ; DirectUI::NativeHWNDHost::GetElement(void)
0x1800990f4  nop     dword ptr [rax+rax+00h]
0x1800990f9  lea     rcx, aContentarea; "ContentArea"
0x180099100  mov     rbx, rax
0x180099103  call    cs:__imp_StrToID
0x18009910a  nop     dword ptr [rax+rax+00h]
0x18009910f  movzx   edx, ax
0x180099112  mov     rcx, rbx
0x180099115  call    cs:__imp_?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z; DirectUI::Element::FindDescendent(ushort)
0x18009911c  nop     dword ptr [rax+rax+00h]
0x180099121  mov     rcx, rdi
0x180099124  mov     rbp, rax
0x180099127  call    cs:__imp_?GetElement@NativeHWNDHost@DirectUI@@QEAAPEAVElement@2@XZ; DirectUI::NativeHWNDHost::GetElement(void)
0x18009912e  nop     dword ptr [rax+rax+00h]
0x180099133  lea     rcx, aTitlebarbackgr; "TitleBarBackground"
0x18009913a  mov     rbx, rax
0x18009913d  call    cs:__imp_StrToID
0x180099144  nop     dword ptr [rax+rax+00h]
0x180099149  movzx   edx, ax
0x18009914c  mov     rcx, rbx
0x18009914f  call    cs:__imp_?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z; DirectUI::Element::FindDescendent(ushort)
0x180099156  nop     dword ptr [rax+rax+00h]
0x18009915b  mov     rbx, rax
0x18009915e  call    ?IsHighContrast@@YAHXZ; IsHighContrast(void)
0x180099163  test    eax, eax
0x180099165  jz      loc_180099225
0x18009916b  lea     rdx, aHighcontrast; "HighContrast"
0x180099172  mov     rcx, rbp
0x180099175  call    cs:__imp_?SetClass@Element@DirectUI@@QEAAJPEBG@Z; DirectUI::Element::SetClass(ushort const *)
0x18009917c  nop     dword ptr [rax+rax+00h]
0x180099181  lea     rdx, aHighcontrast; "HighContrast"
0x180099188  mov     rcx, rsi
0x18009918b  call    cs:__imp_?SetClass@Element@DirectUI@@QEAAJPEBG@Z; DirectUI::Element::SetClass(ushort const *)
0x180099192  nop     dword ptr [rax+rax+00h]
0x180099197  lea     rdx, aHighcontrast; "HighContrast"
0x18009919e  mov     rcx, rbx
0x1800991a1  call    cs:__imp_?SetClass@Element@DirectUI@@QEAAJPEBG@Z; DirectUI::Element::SetClass(ushort const *)
0x1800991a8  nop     dword ptr [rax+rax+00h]
0x1800991ad  mov     ecx, 29h ; ')'
0x1800991b2  call    ?GetColor@CImmersiveColor@@SAKW4IMMERSIVE_COLOR_TYPE@@@Z; CImmersiveColor::GetColor(IMMERSIVE_COLOR_TYPE)
0x1800991b7  mov     ebx, eax
0x1800991b9  call    cs:__imp_IsCompositionActive
0x1800991c0  nop     dword ptr [rax+rax+00h]
0x1800991c5  mov     rcx, rdi
0x1800991c8  test    eax, eax
0x1800991ca  jz      loc_180099297
0x1800991d0  xorps   xmm0, xmm0
0x1800991d3  mov     [rsp+78h+var_58], 13h
0x1800991dc  movups  [rsp+78h+var_40], xmm0
0x1800991e1  lea     rax, [rsp+78h+var_40]
0x1800991e6  mov     dword ptr [rsp+78h+var_40], 1
0x1800991ee  mov     dword ptr [rsp+78h+var_40+8], ebx
0x1800991f2  mov     [rsp+78h+var_50], rax
0x1800991f7  mov     [rsp+78h+var_48], 10h
0x180099200  call    cs:__imp_?GetHWND@NativeHWNDHost@DirectUI@@QEAAPEAUHWND__@@XZ; DirectUI::NativeHWNDHost::GetHWND(void)
0x180099207  nop     dword ptr [rax+rax+00h]
0x18009920c  mov     rcx, rax
0x18009920f  lea     rdx, [rsp+78h+var_58]
0x180099214  call    cs:__imp_SetWindowCompositionAttribute
0x18009921b  nop     dword ptr [rax+rax+00h]
0x180099220  jmp     loc_1800992B4
0x180099225  call    cs:__imp_?ClassProp@Element@DirectUI@@SAPEBUPropertyInfo@2@XZ; DirectUI::Element::ClassProp(void)
0x18009922c  nop     dword ptr [rax+rax+00h]
0x180099231  mov     rdx, rax
0x180099234  mov     rcx, rbp
0x180099237  call    cs:__imp_?RemoveLocalValue@Element@DirectUI@@QEAAJPEBUPropertyInfo@2@@Z; DirectUI::Element::RemoveLocalValue(DirectUI::PropertyInfo const *)
0x18009923e  nop     dword ptr [rax+rax+00h]
0x180099243  call    cs:__imp_?ClassProp@Element@DirectUI@@SAPEBUPropertyInfo@2@XZ; DirectUI::Element::ClassProp(void)
0x18009924a  nop     dword ptr [rax+rax+00h]
0x18009924f  mov     rdx, rax
0x180099252  mov     rcx, rsi
0x180099255  call    cs:__imp_?RemoveLocalValue@Element@DirectUI@@QEAAJPEBUPropertyInfo@2@@Z; DirectUI::Element::RemoveLocalValue(DirectUI::PropertyInfo const *)
0x18009925c  nop     dword ptr [rax+rax+00h]
0x180099261  call    cs:__imp_?ClassProp@Element@DirectUI@@SAPEBUPropertyInfo@2@XZ; DirectUI::Element::ClassProp(void)
0x180099268  nop     dword ptr [rax+rax+00h]
0x18009926d  mov     rdx, rax
0x180099270  mov     rcx, rbx
0x180099273  call    cs:__imp_?RemoveLocalValue@Element@DirectUI@@QEAAJPEBUPropertyInfo@2@@Z; DirectUI::Element::RemoveLocalValue(DirectUI::PropertyInfo const *)
0x18009927a  nop     dword ptr [rax+rax+00h]
0x18009927f  test    byte ptr [rdi+158h], 1
0x180099286  jz      loc_1800991AD
0x18009928c  mov     ebx, [rdi+154h]
0x180099292  jmp     loc_1800991B9
0x180099297  call    cs:__imp_?GetElement@NativeHWNDHost@DirectUI@@QEAAPEAVElement@2@XZ; DirectUI::NativeHWNDHost::GetElement(void)
0x18009929e  nop     dword ptr [rax+rax+00h]
0x1800992a3  mov     rcx, rax
0x1800992a6  mov     edx, ebx
0x1800992a8  call    cs:__imp_?SetBackgroundColor@Element@DirectUI@@QEAAJK@Z; DirectUI::Element::SetBackgroundColor(ulong)
0x1800992af  nop     dword ptr [rax+rax+00h]
0x1800992b4  mov     rcx, [rsp+78h+var_30]
0x1800992b9  xor     rcx, rsp; StackCookie
0x1800992bc  call    __security_check_cookie
0x1800992c1  add     rsp, 58h
0x1800992c5  pop     rdi
0x1800992c6  pop     rsi
0x1800992c7  pop     rbp
0x1800992c8  pop     rbx
0x1800992c9  retn
```
