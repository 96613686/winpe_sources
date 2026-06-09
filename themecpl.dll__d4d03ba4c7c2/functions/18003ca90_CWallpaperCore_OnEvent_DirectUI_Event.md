# CWallpaperCore::OnEvent(DirectUI::Event *)

- ea: `0x18003ca90`
- end: `0x18003cc6f`
- name: `?OnEvent@CWallpaperCore@@QEAAXPEAUEvent@DirectUI@@@Z`
- size: `479`
- prototype: `void __fastcall(CWallpaperCore *__hidden this, struct DirectUI::Event *)`
- caller_count: `1`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x1800444d0`

## callees

- `0x18003c7dc`
- `0x18003ca90`
- `0x18003fac8`
- `0x180042204`
- `0x1800426f0`
- `0x180042808`
- `0x18004289c`
- `0x180042fd8`
- `0x180057010`

## import_xrefs

- `USER32!SendMessageW` at `0x18003cb9c`
- `USER32!SendMessageW` at `0x18003cb9c`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x18003cb6c`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x18003cb6c`
- `DUI70!StrToID` at `0x18003cb08`
- `DUI70!StrToID` at `0x18003cb2d`
- `DUI70!StrToID` at `0x18003cb5a`
- `DUI70!StrToID` at `0x18003cc1f`
- `DUI70!StrToID` at `0x18003cb08`
- `DUI70!StrToID` at `0x18003cb2d`
- `DUI70!StrToID` at `0x18003cb5a`
- `DUI70!StrToID` at `0x18003cc1f`
- `DUI70!?Click@Button@DirectUI@@SA?AVUID@@XZ` at `0x18003cabe`
- `DUI70!?Click@Button@DirectUI@@SA?AVUID@@XZ` at `0x18003cabe`
- `DUI70!?SelectionChange@Combobox@DirectUI@@SA?AVUID@@XZ` at `0x18003cae8`
- `DUI70!?SelectionChange@Combobox@DirectUI@@SA?AVUID@@XZ` at `0x18003cae8`

## string_xrefs

- `0x18003cb01`: `ComboBox_PictureFolder`
- `0x18003cb26`: `ComboBox_Interval`
- `0x18003cb53`: `ComboBox_Interval`
- `0x18003cc18`: `ComboBox_Position`

## pseudocode

```c
void __fastcall CWallpaperCore::OnEvent(DirectUI::Element **this, struct DirectUI::Event *a2)
{
  __int16 v4; // bx
  _QWORD *v5; // rax
  __int64 v6; // rcx
  DirectUI::Element *v7; // rbx
  unsigned __int16 v8; // ax
  struct DirectUI::Element *Descendent; // rax
  HWND v10; // rax
  unsigned int v11; // ebx
  DirectUI::Element *v12; // rcx
  CWallpaperCore *v13; // rcx
  unsigned int v14; // [rsp+38h] [rbp+10h] BYREF
  int v15; // [rsp+40h] [rbp+18h] BYREF

  if ( *((_DWORD *)a2 + 5) == 1 )
  {
    v4 = *(_WORD *)(*(_QWORD *)a2 + 144LL);
    if ( *((_QWORD *)a2 + 1) == *(_QWORD *)DirectUI::Button::Click(&v14) )
    {
      CWallpaperCore::OnActionInitiated((CWallpaperCore *)this, a2);
    }
    else
    {
      v5 = (_QWORD *)DirectUI::Combobox::SelectionChange(&v14);
      v6 = *((_QWORD *)a2 + 1);
      if ( v6 == *v5 )
      {
        if ( v4 == (unsigned __int16)StrToID(L"ComboBox_PictureFolder") )
        {
          CWallpaperCore::_OnSelectPictureFolder((CWallpaperCore *)this);
        }
        else if ( v4 == (unsigned __int16)StrToID(L"ComboBox_Interval") && !*((_BYTE *)this + 178) )
        {
          v7 = this[4];
          v8 = StrToID(L"ComboBox_Interval");
          Descendent = DirectUI::Element::FindDescendent(v7, v8);
          v10 = (HWND)(*(__int64 (__fastcall **)(struct DirectUI::Element *))(*(_QWORD *)Descendent + 360LL))(Descendent);
          v11 = SendMessageW(v10, 0x150u, *((int *)a2 + 9), 0);
          CWallpaperCore::_SetChangeInterval((CWallpaperCore *)this, v11);
          CWallpaperCore::_PrepareForChange((CWallpaperCore *)this);
          v12 = this[52];
          v14 = 0;
          v15 = 0;
          if ( (*(int (__fastcall **)(DirectUI::Element *, unsigned int *, int *))(*(_QWORD *)v12 + 120LL))(
                 v12,
                 &v14,
                 &v15) >= 0 )
            (*(void (__fastcall **)(DirectUI::Element *, _QWORD, _QWORD))(*(_QWORD *)this[52] + 112LL))(
              this[52],
              v14,
              v11);
          CWallpaperCore::_PostChange(v13);
        }
      }
      else if ( v6 == ComboBoxEx::SelectedValueChange
             && v4 == (unsigned __int16)StrToID(L"ComboBox_Position")
             && !*((_BYTE *)this + 178) )
      {
        CWallpaperCore::_OnChangePosition((__int64)this, *((unsigned int *)a2 + 8));
      }
    }
  }
  else if ( !*((_DWORD *)a2 + 5) && *((_QWORD *)a2 + 1) == CWallpaperPage::EnableBrowse )
  {
    CWallpaperCore::_EnableBrowse((CWallpaperCore *)this, (bool)a2);
  }
}

```

## disassembly

```asm
0x18003ca90  mov     [rsp+arg_0], rbx
0x18003ca95  mov     [rsp+arg_18], rsi
0x18003ca9a  push    rdi
0x18003ca9b  sub     rsp, 20h
0x18003ca9f  cmp     dword ptr [rdx+14h], 1
0x18003caa3  mov     rsi, rdx
0x18003caa6  mov     rdi, rcx
0x18003caa9  jnz     loc_18003CC46
0x18003caaf  mov     rax, [rdx]
0x18003cab2  lea     rcx, [rsp+28h+arg_8]
0x18003cab7  movzx   ebx, word ptr [rax+90h]
0x18003cabe  call    cs:__imp_?Click@Button@DirectUI@@SA?AVUID@@XZ; DirectUI::Button::Click(void)
0x18003cac5  nop     dword ptr [rax+rax+00h]
0x18003caca  mov     rax, [rax]
0x18003cacd  cmp     [rsi+8], rax
0x18003cad1  jnz     short loc_18003CAE3
0x18003cad3  mov     rdx, rsi; struct DirectUI::Event *
0x18003cad6  mov     rcx, rdi; this
0x18003cad9  call    ?OnActionInitiated@CWallpaperCore@@AEAAXPEAUEvent@DirectUI@@@Z; CWallpaperCore::OnActionInitiated(DirectUI::Event *)
0x18003cade  jmp     loc_18003CC5E
0x18003cae3  lea     rcx, [rsp+28h+arg_8]
0x18003cae8  call    cs:__imp_?SelectionChange@Combobox@DirectUI@@SA?AVUID@@XZ; DirectUI::Combobox::SelectionChange(void)
0x18003caef  nop     dword ptr [rax+rax+00h]
0x18003caf4  mov     rcx, [rsi+8]
0x18003caf8  cmp     rcx, [rax]
0x18003cafb  jnz     loc_18003CC0F
0x18003cb01  lea     rcx, aComboboxPictur; "ComboBox_PictureFolder"
0x18003cb08  call    cs:__imp_StrToID
0x18003cb0f  nop     dword ptr [rax+rax+00h]
0x18003cb14  cmp     bx, ax
0x18003cb17  jnz     short loc_18003CB26
0x18003cb19  mov     rcx, rdi; this
0x18003cb1c  call    ?_OnSelectPictureFolder@CWallpaperCore@@AEAAXXZ; CWallpaperCore::_OnSelectPictureFolder(void)
0x18003cb21  jmp     loc_18003CC5E
0x18003cb26  lea     rcx, aComboboxInterv; "ComboBox_Interval"
0x18003cb2d  call    cs:__imp_StrToID
0x18003cb34  nop     dword ptr [rax+rax+00h]
0x18003cb39  cmp     bx, ax
0x18003cb3c  jnz     loc_18003CC5E
0x18003cb42  cmp     byte ptr [rdi+0B2h], 0
0x18003cb49  jnz     loc_18003CC5E
0x18003cb4f  mov     rbx, [rdi+20h]
0x18003cb53  lea     rcx, aComboboxInterv; "ComboBox_Interval"
0x18003cb5a  call    cs:__imp_StrToID
0x18003cb61  nop     dword ptr [rax+rax+00h]
0x18003cb66  movzx   edx, ax
0x18003cb69  mov     rcx, rbx
0x18003cb6c  call    cs:__imp_?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z; DirectUI::Element::FindDescendent(ushort)
0x18003cb73  nop     dword ptr [rax+rax+00h]
0x18003cb78  mov     rdx, rax
0x18003cb7b  mov     rcx, [rax]
0x18003cb7e  mov     rax, [rcx+168h]
0x18003cb85  mov     rcx, rdx
0x18003cb88  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003cb8d  movsxd  r8, dword ptr [rsi+24h]; wParam
0x18003cb91  xor     r9d, r9d; lParam
0x18003cb94  mov     edx, 150h; Msg
0x18003cb99  mov     rcx, rax; hWnd
0x18003cb9c  call    cs:__imp_SendMessageW
0x18003cba3  nop     dword ptr [rax+rax+00h]
0x18003cba8  mov     edx, eax; unsigned int
0x18003cbaa  mov     rcx, rdi; this
0x18003cbad  mov     rbx, rax
0x18003cbb0  call    ?_SetChangeInterval@CWallpaperCore@@AEAAXI@Z; CWallpaperCore::_SetChangeInterval(uint)
0x18003cbb5  mov     rcx, rdi; this
0x18003cbb8  call    ?_PrepareForChange@CWallpaperCore@@AEAAXXZ; CWallpaperCore::_PrepareForChange(void)
0x18003cbbd  mov     rcx, [rdi+1A0h]
0x18003cbc4  lea     r8, [rsp+28h+arg_10]
0x18003cbc9  mov     [rsp+28h+arg_8], 0
0x18003cbd1  mov     [rsp+28h+arg_10], 0
0x18003cbd9  mov     rdx, [rcx]
0x18003cbdc  mov     rax, [rdx+78h]
0x18003cbe0  lea     rdx, [rsp+28h+arg_8]
0x18003cbe5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003cbea  test    eax, eax
0x18003cbec  js      short loc_18003CC08
0x18003cbee  mov     rcx, [rdi+1A0h]
0x18003cbf5  mov     r8d, ebx
0x18003cbf8  mov     edx, [rsp+28h+arg_8]
0x18003cbfc  mov     rax, [rcx]
0x18003cbff  mov     rax, [rax+70h]
0x18003cc03  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003cc08  call    ?_PostChange@CWallpaperCore@@AEAAXXZ; CWallpaperCore::_PostChange(void)
0x18003cc0d  jmp     short loc_18003CC5E
0x18003cc0f  cmp     rcx, cs:?SelectedValueChange@ComboBoxEx@@2VUID@@A; UID ComboBoxEx::SelectedValueChange
0x18003cc16  jnz     short loc_18003CC5E
0x18003cc18  lea     rcx, aComboboxPositi; "ComboBox_Position"
0x18003cc1f  call    cs:__imp_StrToID
0x18003cc26  nop     dword ptr [rax+rax+00h]
0x18003cc2b  cmp     bx, ax
0x18003cc2e  jnz     short loc_18003CC5E
0x18003cc30  cmp     byte ptr [rdi+0B2h], 0
0x18003cc37  jnz     short loc_18003CC5E
0x18003cc39  mov     edx, [rsi+20h]
0x18003cc3c  mov     rcx, rdi
0x18003cc3f  call    ?_OnChangePosition@CWallpaperCore@@AEAAXW4DESKTOP_WALLPAPER_POSITION@@@Z; CWallpaperCore::_OnChangePosition(DESKTOP_WALLPAPER_POSITION)
0x18003cc44  jmp     short loc_18003CC5E
0x18003cc46  cmp     dword ptr [rdx+14h], 0
0x18003cc4a  jnz     short loc_18003CC5E
0x18003cc4c  mov     rax, cs:?EnableBrowse@CWallpaperPage@@2VUID@@A; UID CWallpaperPage::EnableBrowse
0x18003cc53  cmp     [rdx+8], rax
0x18003cc57  jnz     short loc_18003CC5E
0x18003cc59  call    ?_EnableBrowse@CWallpaperCore@@AEAAX_N@Z; CWallpaperCore::_EnableBrowse(bool)
0x18003cc5e  mov     rbx, [rsp+28h+arg_0]
0x18003cc63  mov     rsi, [rsp+28h+arg_18]
0x18003cc68  add     rsp, 20h
0x18003cc6c  pop     rdi
0x18003cc6d  retn
```
