# CWcnPageWlanPbcCombo::OnSetActive(void)

- ea: `0x180016b80`
- end: `0x180016e3e`
- name: `?OnSetActive@CWcnPageWlanPbcCombo@@UEAA_JXZ`
- size: `702`
- prototype: `__int64 __fastcall(CWcnPageWlanPbcCombo *__hidden this)`
- caller_count: `0`
- callee_count: `12`
- tags: `installer_update, broker_com_uri`

## callees

- `0x180001820`
- `0x18000a1bc`
- `0x18000ce94`
- `0x18000d630`
- `0x18000fc10`
- `0x180013744`
- `0x180016b80`
- `0x180017108`
- `0x180017220`
- `0x1800174a4`
- `0x18002de1c`
- `0x18002de84`

## import_xrefs

- `USER32!PostMessageW` at `0x180016c9a`
- `USER32!PostMessageW` at `0x180016cbc`
- `USER32!PostMessageW` at `0x180016c9a`
- `USER32!PostMessageW` at `0x180016cbc`
- `USER32!SetTimer` at `0x180016db4`
- `USER32!SetTimer` at `0x180016db4`
- `DUI70!?SetVisible@Element@DirectUI@@QEAAJ_N@Z` at `0x180016c69`
- `DUI70!?SetVisible@Element@DirectUI@@QEAAJ_N@Z` at `0x180016d72`
- `DUI70!?SetVisible@Element@DirectUI@@QEAAJ_N@Z` at `0x180016c69`
- `DUI70!?SetVisible@Element@DirectUI@@QEAAJ_N@Z` at `0x180016d72`
- `DUI70!?SetLayoutPos@Element@DirectUI@@QEAAJH@Z` at `0x180016c5a`
- `DUI70!?SetLayoutPos@Element@DirectUI@@QEAAJH@Z` at `0x180016d53`
- `DUI70!?SetLayoutPos@Element@DirectUI@@QEAAJH@Z` at `0x180016d63`
- `DUI70!?SetLayoutPos@Element@DirectUI@@QEAAJH@Z` at `0x180016c5a`
- `DUI70!?SetLayoutPos@Element@DirectUI@@QEAAJH@Z` at `0x180016d53`
- `DUI70!?SetLayoutPos@Element@DirectUI@@QEAAJH@Z` at `0x180016d63`
- `DUI70!?SetPasswordCharacter@TouchEditBase@DirectUI@@QEAAJH@Z` at `0x180016cce`
- `DUI70!?SetPasswordCharacter@TouchEditBase@DirectUI@@QEAAJH@Z` at `0x180016cce`

## pseudocode

```c
__int64 __fastcall CWcnPageWlanPbcCombo::OnSetActive(CWcnPageWlanPbcCombo *this)
{
  _BYTE *v2; // r10
  const char *Indent; // rax
  __int64 v4; // r10
  unsigned __int8 v5; // si
  HWND *Parent; // rax
  HWND *v7; // rax
  bool v8; // zf
  DirectUI::Element *v9; // rcx
  bool v10; // dl
  __int64 v11; // rcx
  __int64 v12; // r8
  __int64 v13; // r9
  const char *v14; // rax
  __int64 v15; // r10
  const char *v16; // rax
  __int64 v17; // r10
  unsigned int *v19; // [rsp+20h] [rbp-68h]
  void *v20; // [rsp+30h] [rbp-58h] BYREF
  _BYTE v21[16]; // [rsp+38h] [rbp-50h] BYREF

  v2 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    Indent = GetIndent(1);
    WPP_SF_s(*(_QWORD *)(v4 + 16), 12, WPP_5d28c7bb4c503e99a1827b75a81abd2f_Traceguids, Indent);
    v2 = WPP_GLOBAL_Control;
  }
  if ( *((_QWORD *)this + 71)
    && *((_QWORD *)this + 72)
    && *((_QWORD *)this + 73)
    && *((_QWORD *)this + 70)
    && *((_QWORD *)this + 74)
    && *((_QWORD *)this + 75)
    && *((_QWORD *)this + 76) )
  {
    *((_BYTE *)this + 506) = 0;
    CWcnPageWlanPbcCombo::_CleanupBackgroundStuff(this);
    DirectUI::Element::SetLayoutPos(*((DirectUI::Element **)this + 72), -3);
    DirectUI::Element::SetVisible(*((DirectUI::Element **)this + 72), 0);
    v5 = 1;
    MicrosoftTelemetryAssertTriggeredNoArgs();
    Parent = (HWND *)ATL::CWindow::GetParent((char *)this + 152, v21);
    PostMessageW(*Parent, 0x48Au, 0, 5);
    v7 = (HWND *)ATL::CWindow::GetParent((char *)this + 152, v21);
    PostMessageW(*v7, 0x48Bu, 0, 7);
    DirectUI::TouchEditBase::SetPasswordCharacter(*((DirectUI::TouchEditBase **)this + 71), 9679);
    CWcnPageWlanPbcCombo::_UpdateWcnWidgets((DirectUI::Element **)this, 0x326u, (unsigned int *)0x2A31, 0);
    v20 = 0;
    if ( (int)CXWizardClassRoot::GetProperty(
                (CWcnPageWlanPbcCombo *)((char *)this + 64),
                (const struct _GUID *)((char *)this + 104),
                L"ProfileMismatch",
                &v20,
                v19) >= 0 )
    {
      v8 = v20 == 0;
      v20 = 0;
      *((_BYTE *)this + 616) = !v8;
      CXWizardClassRoot::SetProperty(
        (CWcnPageWlanPbcCombo *)((char *)this + 64),
        (const struct _GUID *)((char *)this + 104),
        L"ProfileMismatch",
        0,
        2u);
    }
    v9 = (DirectUI::Element *)*((_QWORD *)this + 76);
    if ( *((_BYTE *)this + 616) )
    {
      DirectUI::Element::SetLayoutPos(v9, 1);
      v10 = 1;
    }
    else
    {
      DirectUI::Element::SetLayoutPos(v9, -3);
      v10 = 0;
    }
    DirectUI::Element::SetVisible(*((DirectUI::Element **)this + 76), v10);
    CWcnPageWlanPbcCombo::_BeginBackgroundScan(this);
    if ( (Microsoft_Windows_WCNWizEnableBits & 1) != 0 )
      McGenEventWrite_EtwEventWriteTransfer(v11, (__int64)DisplayComboKeyPage, v12, v13, (__int64)v21);
    SetTimer(*((HWND *)this + 19), 0x264369Au, 0x1D4C0u, 0);
    goto LABEL_22;
  }
  v5 = 0;
  if ( v2 == (_BYTE *)&WPP_GLOBAL_Control )
    return v5 - 1LL;
  if ( v2[25] >= 2u )
  {
    v14 = GetIndent(0);
    WPP_SF_s(*(_QWORD *)(v15 + 16), 13, WPP_5d28c7bb4c503e99a1827b75a81abd2f_Traceguids, v14);
LABEL_22:
    v2 = WPP_GLOBAL_Control;
  }
  if ( v2 != (_BYTE *)&WPP_GLOBAL_Control && v2[25] >= 6u )
  {
    v16 = GetIndent(-1);
    WPP_SF_s(*(_QWORD *)(v17 + 16), 14, WPP_5d28c7bb4c503e99a1827b75a81abd2f_Traceguids, v16);
  }
  return v5 - 1LL;
}

```

## disassembly

```asm
0x180016b80  push    rbx
0x180016b82  push    rbp
0x180016b83  push    rsi
0x180016b84  push    rdi
0x180016b85  push    r14
0x180016b87  push    r15
0x180016b89  sub     rsp, 58h
0x180016b8d  mov     rax, cs:__security_cookie
0x180016b94  xor     rax, rsp
0x180016b97  mov     [rsp+88h+var_40], rax
0x180016b9c  mov     rdi, rcx
0x180016b9f  mov     r10, cs:WPP_GLOBAL_Control
0x180016ba6  lea     r15, WPP_GLOBAL_Control
0x180016bad  cmp     r10, r15
0x180016bb0  jz      short loc_180016BE2
0x180016bb2  cmp     byte ptr [r10+19h], 6
0x180016bb7  jb      short loc_180016BE2
0x180016bb9  mov     ecx, 1; int
0x180016bbe  call    ?GetIndent@@YAPEBDH@Z; GetIndent(int)
0x180016bc3  mov     rcx, [r10+10h]
0x180016bc7  lea     r8, WPP_5d28c7bb4c503e99a1827b75a81abd2f_Traceguids
0x180016bce  mov     edx, 0Ch
0x180016bd3  mov     r9, rax
0x180016bd6  call    WPP_SF_s
0x180016bdb  mov     r10, cs:WPP_GLOBAL_Control
0x180016be2  xor     r14d, r14d
0x180016be5  cmp     [rdi+238h], r14
0x180016bec  jz      loc_180016DBC
0x180016bf2  cmp     [rdi+240h], r14
0x180016bf9  jz      loc_180016DBC
0x180016bff  cmp     [rdi+248h], r14
0x180016c06  jz      loc_180016DBC
0x180016c0c  cmp     [rdi+230h], r14
0x180016c13  jz      loc_180016DBC
0x180016c19  cmp     [rdi+250h], r14
0x180016c20  jz      loc_180016DBC
0x180016c26  cmp     [rdi+258h], r14
0x180016c2d  jz      loc_180016DBC
0x180016c33  cmp     [rdi+260h], r14
0x180016c3a  jz      loc_180016DBC
0x180016c40  mov     rcx, rdi; this
0x180016c43  mov     [rdi+1FAh], r14b
0x180016c4a  call    ?_CleanupBackgroundStuff@CWcnPageWlanPbcCombo@@AEAAXXZ; CWcnPageWlanPbcCombo::_CleanupBackgroundStuff(void)
0x180016c4f  mov     rcx, [rdi+240h]
0x180016c56  lea     edx, [r14-3]
0x180016c5a  call    cs:__imp_?SetLayoutPos@Element@DirectUI@@QEAAJH@Z; DirectUI::Element::SetLayoutPos(int)
0x180016c60  mov     rcx, [rdi+240h]
0x180016c67  xor     edx, edx
0x180016c69  call    cs:__imp_?SetVisible@Element@DirectUI@@QEAAJ_N@Z; DirectUI::Element::SetVisible(bool)
0x180016c6f  mov     sil, 1
0x180016c72  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180016c77  lea     rbx, [rdi+98h]
0x180016c7e  mov     rcx, rbx
0x180016c81  lea     rdx, [rsp+88h+var_50]
0x180016c86  call    ?GetParent@CWindow@ATL@@QEBA?AV12@XZ; ATL::CWindow::GetParent(void)
0x180016c8b  lea     r9d, [r14+5]; lParam
0x180016c8f  xor     r8d, r8d; wParam
0x180016c92  mov     edx, 48Ah; Msg
0x180016c97  mov     rcx, [rax]; hWnd
0x180016c9a  call    cs:__imp_PostMessageW
0x180016ca0  lea     rdx, [rsp+88h+var_50]
0x180016ca5  mov     rcx, rbx
0x180016ca8  call    ?GetParent@CWindow@ATL@@QEBA?AV12@XZ; ATL::CWindow::GetParent(void)
0x180016cad  lea     r9d, [r14+7]; lParam
0x180016cb1  xor     r8d, r8d; wParam
0x180016cb4  mov     edx, 48Bh; Msg
0x180016cb9  mov     rcx, [rax]; hWnd
0x180016cbc  call    cs:__imp_PostMessageW
0x180016cc2  mov     rcx, [rdi+238h]
0x180016cc9  mov     edx, 25CFh
0x180016cce  call    cs:__imp_?SetPasswordCharacter@TouchEditBase@DirectUI@@QEAAJH@Z; DirectUI::TouchEditBase::SetPasswordCharacter(int)
0x180016cd4  xor     r9d, r9d; unsigned int
0x180016cd7  mov     edx, 326h; unsigned int
0x180016cdc  mov     r8d, 2A31h; unsigned int
0x180016ce2  mov     rcx, rdi; this
0x180016ce5  call    ?_UpdateWcnWidgets@CWcnPageWlanPbcCombo@@AEAAXIII@Z; CWcnPageWlanPbcCombo::_UpdateWcnWidgets(uint,uint,uint)
0x180016cea  lea     r9, [rsp+88h+var_58]; void **
0x180016cef  mov     [rsp+88h+var_58], r14
0x180016cf4  lea     r8, aProfilemismatc; "ProfileMismatch"
0x180016cfb  lea     rdx, [rdi+68h]; struct _GUID *
0x180016cff  lea     rcx, [rdi+40h]; this
0x180016d03  call    ?GetProperty@CXWizardClassRoot@@QEAAJPEBU_GUID@@QEAGQEAPEAXQEAK@Z; CXWizardClassRoot::GetProperty(_GUID const *,ushort * const,void * * const,ulong * const)
0x180016d08  test    eax, eax
0x180016d0a  js      short loc_180016D3E
0x180016d0c  cmp     [rsp+88h+var_58], r14
0x180016d11  lea     r8, aProfilemismatc; "ProfileMismatch"
0x180016d18  lea     rdx, [rdi+68h]; struct _GUID *
0x180016d1c  mov     [rsp+88h+var_58], r14
0x180016d21  setnz   al
0x180016d24  mov     [rsp+88h+var_68], 2; unsigned int
0x180016d2c  xor     r9d, r9d; void *
0x180016d2f  mov     [rdi+268h], al
0x180016d35  lea     rcx, [rdi+40h]; this
0x180016d39  call    ?SetProperty@CXWizardClassRoot@@QEAAJPEBU_GUID@@QEAGQEAXK@Z; CXWizardClassRoot::SetProperty(_GUID const *,ushort * const,void * const,ulong)
0x180016d3e  mov     rcx, [rdi+260h]
0x180016d45  cmp     [rdi+268h], r14b
0x180016d4c  jz      short loc_180016D5E
0x180016d4e  mov     edx, 1
0x180016d53  call    cs:__imp_?SetLayoutPos@Element@DirectUI@@QEAAJH@Z; DirectUI::Element::SetLayoutPos(int)
0x180016d59  mov     dl, sil
0x180016d5c  jmp     short loc_180016D6B
0x180016d5e  mov     edx, 0FFFFFFFDh
0x180016d63  call    cs:__imp_?SetLayoutPos@Element@DirectUI@@QEAAJH@Z; DirectUI::Element::SetLayoutPos(int)
0x180016d69  xor     edx, edx
0x180016d6b  mov     rcx, [rdi+260h]
0x180016d72  call    cs:__imp_?SetVisible@Element@DirectUI@@QEAAJ_N@Z; DirectUI::Element::SetVisible(bool)
0x180016d78  mov     rcx, rdi; this
0x180016d7b  call    ?_BeginBackgroundScan@CWcnPageWlanPbcCombo@@AEAAXXZ; CWcnPageWlanPbcCombo::_BeginBackgroundScan(void)
0x180016d80  test    cs:Microsoft_Windows_WCNWizEnableBits, sil
0x180016d87  jz      short loc_180016D9F
0x180016d89  lea     rax, [rsp+88h+var_50]
0x180016d8e  lea     rdx, DisplayComboKeyPage
0x180016d95  mov     qword ptr [rsp+88h+var_68], rax
0x180016d9a  call    McGenEventWrite_EtwEventWriteTransfer
0x180016d9f  mov     rcx, [rdi+98h]; hWnd
0x180016da6  xor     r9d, r9d; lpTimerFunc
0x180016da9  mov     edx, 264369Ah; nIDEvent
0x180016dae  mov     r8d, 1D4C0h; uElapse
0x180016db4  call    cs:__imp_SetTimer
0x180016dba  jmp     short loc_180016DEA
0x180016dbc  mov     sil, r14b
0x180016dbf  cmp     r10, r15
0x180016dc2  jz      short loc_180016E1D
0x180016dc4  cmp     byte ptr [r10+19h], 2
0x180016dc9  jb      short loc_180016DF1
0x180016dcb  xor     ecx, ecx; int
0x180016dcd  call    ?GetIndent@@YAPEBDH@Z; GetIndent(int)
0x180016dd2  mov     rcx, [r10+10h]
0x180016dd6  lea     r8, WPP_5d28c7bb4c503e99a1827b75a81abd2f_Traceguids
0x180016ddd  mov     edx, 0Dh
0x180016de2  mov     r9, rax
0x180016de5  call    WPP_SF_s
0x180016dea  mov     r10, cs:WPP_GLOBAL_Control
0x180016df1  cmp     r10, r15
0x180016df4  jz      short loc_180016E1D
0x180016df6  cmp     byte ptr [r10+19h], 6
0x180016dfb  jb      short loc_180016E1D
0x180016dfd  or      ecx, 0FFFFFFFFh; int
0x180016e00  call    ?GetIndent@@YAPEBDH@Z; GetIndent(int)
0x180016e05  mov     rcx, [r10+10h]
0x180016e09  lea     r8, WPP_5d28c7bb4c503e99a1827b75a81abd2f_Traceguids
0x180016e10  mov     edx, 0Eh
0x180016e15  mov     r9, rax
0x180016e18  call    WPP_SF_s
0x180016e1d  movzx   eax, sil
0x180016e21  dec     rax
0x180016e24  mov     rcx, [rsp+88h+var_40]
0x180016e29  xor     rcx, rsp; StackCookie
0x180016e2c  call    __security_check_cookie
0x180016e31  add     rsp, 58h
0x180016e35  pop     r15
0x180016e37  pop     r14
0x180016e39  pop     rdi
0x180016e3a  pop     rsi
0x180016e3b  pop     rbp
0x180016e3c  pop     rbx
0x180016e3d  retn
```
