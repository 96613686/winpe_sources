# CShareMediaCore::OnEvent(DirectUI::Event *)

- ea: `0x18000b78c`
- end: `0x18000ba74`
- name: `?OnEvent@CShareMediaCore@@QEAAXPEAUEvent@DirectUI@@@Z`
- size: `744`
- prototype: `void __fastcall(CShareMediaCore *__hidden this, struct DirectUI::Event *)`
- caller_count: `1`
- callee_count: `15`
- tags: `authz_impersonation, service_task, installer_update, broker_com_uri`

## callers

- `0x180013700`

## callees

- `0x180003860`
- `0x180003888`
- `0x18000b78c`
- `0x18000d954`
- `0x18000ec90`
- `0x18000f020`
- `0x18000f1cc`
- `0x18000f2f4`
- `0x18000f660`
- `0x18000f95c`
- `0x18000fae8`
- `0x18000fd88`
- `0x180010590`
- `0x1800120ec`
- `0x18001815c`

## import_xrefs

- `DUI70!?SelectionChange@Combobox@DirectUI@@SA?AVUID@@XZ` at `0x18000b9f9`
- `DUI70!?SelectionChange@Combobox@DirectUI@@SA?AVUID@@XZ` at `0x18000b9f9`
- `DUI70!?Click@Button@DirectUI@@SA?AVUID@@XZ` at `0x18000b7b0`
- `DUI70!?Click@Button@DirectUI@@SA?AVUID@@XZ` at `0x18000b7b0`
- `DUI70!?GetSelection@Combobox@DirectUI@@QEAAHXZ` at `0x18000ba2c`
- `DUI70!?GetSelection@Combobox@DirectUI@@QEAAHXZ` at `0x18000ba2c`
- `DUI70!StrToID` at `0x18000b7d4`
- `DUI70!StrToID` at `0x18000b7fa`
- `DUI70!StrToID` at `0x18000b81e`
- `DUI70!StrToID` at `0x18000b8b4`
- `DUI70!StrToID` at `0x18000b8db`
- `DUI70!StrToID` at `0x18000b901`
- `DUI70!StrToID` at `0x18000b927`
- `DUI70!StrToID` at `0x18000b946`
- `DUI70!StrToID` at `0x18000b965`
- `DUI70!StrToID` at `0x18000b98b`
- `DUI70!StrToID` at `0x18000ba19`
- `DUI70!StrToID` at `0x18000b7d4`
- `DUI70!StrToID` at `0x18000b7fa`
- `DUI70!StrToID` at `0x18000b81e`
- `DUI70!StrToID` at `0x18000b8b4`
- `DUI70!StrToID` at `0x18000b8db`
- `DUI70!StrToID` at `0x18000b901`
- `DUI70!StrToID` at `0x18000b927`
- `DUI70!StrToID` at `0x18000b946`
- `DUI70!StrToID` at `0x18000b965`
- `DUI70!StrToID` at `0x18000b98b`
- `DUI70!StrToID` at `0x18000ba19`

## string_xrefs

- `0x18000ba0b`: `NetworkFilterCombo`
- `0x18000b7c6`: `CustomizeDefaultLink`
- `0x18000b7f3`: `MediaSharingPrivacyLink`
- `0x18000b817`: `LearnMoreAboutMediaSharingLink`
- `0x18000b8ad`: `ChoosePowerOptionsLink`
- `0x18000b984`: `LaunchServicesLink`

## pseudocode

```c
void __fastcall CShareMediaCore::OnEvent(CShareWithList **this, struct DirectUI::Event *a2)
{
  _QWORD *v4; // rax
  __int64 v5; // rcx
  __int16 v6; // bx
  CShareMediaCore *v7; // rcx
  unsigned int v8; // eax
  __int16 v9; // bx
  unsigned int Selection; // eax
  CShareWithList *v11; // rcx
  char v12; // [rsp+38h] [rbp+10h] BYREF

  if ( *((_DWORD *)a2 + 5) == 1 )
  {
    v4 = (_QWORD *)DirectUI::Button::Click(&v12);
    v5 = *((_QWORD *)a2 + 1);
    if ( *v4 == v5 )
    {
      v6 = *(_WORD *)(*(_QWORD *)a2 + 144LL);
      if ( (unsigned __int16)StrToID(L"CustomizeDefaultLink") == v6 )
      {
        g_bfSqm_USAGE |= 8u;
        CShareMediaCore::_OnCustomizeLink((CShareMediaCore *)this);
      }
      else if ( (unsigned __int16)StrToID(L"MediaSharingPrivacyLink") == v6 )
      {
        g_bfSqm_USAGE |= 0x8000u;
        CShareMediaCore::_OnMediaSharingPrivacyLink(v7);
      }
      else if ( (unsigned __int16)StrToID(L"LearnMoreAboutMediaSharingLink") == v6 )
      {
        g_bfSqm_USAGE |= 0x2000u;
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 64, &WPP_59386dd0a0913b67da6dc13cee28e88f_Traceguids);
        v8 = DUIFramework_DisplayHelpDialog(
               L"7391bdc3-3767-4f98-9cf6-80d8bd2a0594",
               L"WMP_NETWORK_SHARING_CENTER_MEDIA_SHARING");
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 65, &WPP_59386dd0a0913b67da6dc13cee28e88f_Traceguids, v8);
      }
      else if ( (unsigned __int16)StrToID(L"ChoosePowerOptionsLink") == v6 )
      {
        g_bfSqm_USAGE |= 0x800u;
        CShareMediaCore::_OnChoosePowerOptionsLink((CShareMediaCore *)this);
      }
      else if ( (unsigned __int16)StrToID(L"AllowAllButton") == v6 )
      {
        g_bfSqm_USAGE |= 2u;
        CShareMediaCore::_OnAllowAll((CShareMediaCore *)this);
      }
      else if ( (unsigned __int16)StrToID(L"BlockAllButton") == v6 )
      {
        g_bfSqm_USAGE |= 4u;
        CShareMediaCore::_OnBlockAll((CShareMediaCore *)this);
      }
      else if ( (unsigned __int16)StrToID(L"CancelButton") == v6 )
      {
        CShareMediaCore::_OnCancel((CShareMediaCore *)this);
      }
      else if ( (unsigned __int16)StrToID(L"OKButton") == v6 )
      {
        CShareMediaCore::_OnOK((CShareMediaCore *)this);
      }
      else if ( (unsigned __int16)StrToID(L"TurnOnMediaSharing") == v6 )
      {
        g_bfSqm_USAGE |= 1u;
        CShareMediaCore::_OnTurnOnMediaSharing((CShareMediaCore *)this);
      }
      else
      {
        if ( (unsigned __int16)StrToID(L"LaunchServicesLink") != v6 )
          return;
        g_bfSqm_USAGE |= 0x10000u;
        CShareMediaCore::_OnLaunchServicesMSC((CShareMediaCore *)this);
      }
      goto LABEL_43;
    }
    if ( CShareMediaPage::AuthorizationChange != v5 )
      return;
    if ( !*((_DWORD *)this + 60) )
    {
      switch ( *((_DWORD *)a2 + 8) )
      {
        case 1:
          g_bfSqm_USAGE |= 0x100u;
          break;
        case 2:
          g_bfSqm_USAGE |= 0x200u;
          break;
        case 3:
          g_bfSqm_USAGE |= 0x400u;
          break;
      }
    }
    goto LABEL_42;
  }
  if ( *((_QWORD *)a2 + 1) == *(_QWORD *)DirectUI::Combobox::SelectionChange(&v12) )
  {
    v9 = *(_WORD *)(*(_QWORD *)a2 + 144LL);
    if ( (unsigned __int16)StrToID(L"NetworkFilterCombo") == v9 )
    {
      if ( *(_QWORD *)a2 )
      {
        Selection = DirectUI::Combobox::GetSelection(*(DirectUI::Combobox **)a2);
        if ( Selection == *((_DWORD *)this + 48) )
          goto LABEL_43;
        g_bfSqm_USAGE |= 0x20000u;
        v11 = this[7];
        *((_DWORD *)this + 48) = Selection;
        if ( !v11 )
          goto LABEL_43;
        CShareWithList::SetCurrentNetworkFilter(v11, Selection);
LABEL_42:
        CShareMediaCore::_UpdateStatusText((CShareMediaCore *)this);
LABEL_43:
        *((_BYTE *)a2 + 16) = 1;
      }
    }
  }
}

```

## disassembly

```asm
0x18000b78c  mov     [rsp+arg_0], rbx
0x18000b791  mov     [rsp+arg_10], rsi
0x18000b796  push    rdi
0x18000b797  sub     rsp, 20h
0x18000b79b  cmp     dword ptr [rdx+14h], 1
0x18000b79f  mov     rsi, rcx
0x18000b7a2  lea     rcx, [rsp+28h+arg_8]
0x18000b7a7  mov     rdi, rdx
0x18000b7aa  jnz     loc_18000B9F9
0x18000b7b0  call    cs:__imp_?Click@Button@DirectUI@@SA?AVUID@@XZ; DirectUI::Button::Click(void)
0x18000b7b6  mov     rcx, [rdi+8]
0x18000b7ba  cmp     [rax], rcx
0x18000b7bd  jnz     loc_18000B9AF
0x18000b7c3  mov     rax, [rdi]
0x18000b7c6  lea     rcx, aCustomizedefau; "CustomizeDefaultLink"
0x18000b7cd  movzx   ebx, word ptr [rax+90h]
0x18000b7d4  call    cs:__imp_StrToID
0x18000b7da  cmp     ax, bx
0x18000b7dd  jnz     short loc_18000B7F3
0x18000b7df  or      cs:?g_bfSqm_USAGE@@3KA, 8; ulong g_bfSqm_USAGE
0x18000b7e6  mov     rcx, rsi; this
0x18000b7e9  call    ?_OnCustomizeLink@CShareMediaCore@@AEAAJXZ; CShareMediaCore::_OnCustomizeLink(void)
0x18000b7ee  jmp     loc_18000BA60
0x18000b7f3  lea     rcx, aMediasharingpr; "MediaSharingPrivacyLink"
0x18000b7fa  call    cs:__imp_StrToID
0x18000b800  cmp     ax, bx
0x18000b803  jnz     short loc_18000B817
0x18000b805  bts     cs:?g_bfSqm_USAGE@@3KA, 0Fh; ulong g_bfSqm_USAGE
0x18000b80d  call    ?_OnMediaSharingPrivacyLink@CShareMediaCore@@AEAAJXZ; CShareMediaCore::_OnMediaSharingPrivacyLink(void)
0x18000b812  jmp     loc_18000BA60
0x18000b817  lea     rcx, aLearnmoreabout; "LearnMoreAboutMediaSharingLink"
0x18000b81e  call    cs:__imp_StrToID
0x18000b824  cmp     ax, bx
0x18000b827  jnz     loc_18000B8AD
0x18000b82d  bts     cs:?g_bfSqm_USAGE@@3KA, 0Dh; ulong g_bfSqm_USAGE
0x18000b835  mov     rcx, cs:WPP_GLOBAL_Control
0x18000b83c  lea     rbx, WPP_GLOBAL_Control
0x18000b843  cmp     rcx, rbx
0x18000b846  jz      short loc_18000B863
0x18000b848  test    byte ptr [rcx+1Ch], 20h
0x18000b84c  jz      short loc_18000B863
0x18000b84e  mov     rcx, [rcx+10h]
0x18000b852  lea     r8, WPP_59386dd0a0913b67da6dc13cee28e88f_Traceguids
0x18000b859  mov     edx, 40h ; '@'
0x18000b85e  call    WPP_SF_
0x18000b863  lea     rdx, aWmpNetworkShar; "WMP_NETWORK_SHARING_CENTER_MEDIA_SHARIN"...
0x18000b86a  lea     rcx, a7391bdc337674f; "7391bdc3-3767-4f98-9cf6-80d8bd2a0594"
0x18000b871  call    ?DUIFramework_DisplayHelpDialog@@YAJPEBG0@Z; DUIFramework_DisplayHelpDialog(ushort const *,ushort const *)
0x18000b876  mov     rcx, cs:WPP_GLOBAL_Control
0x18000b87d  cmp     rcx, rbx
0x18000b880  jz      loc_18000BA60
0x18000b886  test    byte ptr [rcx+1Ch], 20h
0x18000b88a  jz      loc_18000BA60
0x18000b890  mov     rcx, [rcx+10h]
0x18000b894  lea     r8, WPP_59386dd0a0913b67da6dc13cee28e88f_Traceguids
0x18000b89b  mov     edx, 41h ; 'A'
0x18000b8a0  mov     r9d, eax
0x18000b8a3  call    WPP_SF_d
0x18000b8a8  jmp     loc_18000BA60
0x18000b8ad  lea     rcx, aChoosepoweropt; "ChoosePowerOptionsLink"
0x18000b8b4  call    cs:__imp_StrToID
0x18000b8ba  cmp     ax, bx
0x18000b8bd  jnz     short loc_18000B8D4
0x18000b8bf  bts     cs:?g_bfSqm_USAGE@@3KA, 0Bh; ulong g_bfSqm_USAGE
0x18000b8c7  mov     rcx, rsi; this
0x18000b8ca  call    ?_OnChoosePowerOptionsLink@CShareMediaCore@@AEAAJXZ; CShareMediaCore::_OnChoosePowerOptionsLink(void)
0x18000b8cf  jmp     loc_18000BA60
0x18000b8d4  lea     rcx, aAllowallbutton; "AllowAllButton"
0x18000b8db  call    cs:__imp_StrToID
0x18000b8e1  cmp     ax, bx
0x18000b8e4  jnz     short loc_18000B8FA
0x18000b8e6  or      cs:?g_bfSqm_USAGE@@3KA, 2; ulong g_bfSqm_USAGE
0x18000b8ed  mov     rcx, rsi; this
0x18000b8f0  call    ?_OnAllowAll@CShareMediaCore@@AEAAJXZ; CShareMediaCore::_OnAllowAll(void)
0x18000b8f5  jmp     loc_18000BA60
0x18000b8fa  lea     rcx, aBlockallbutton; "BlockAllButton"
0x18000b901  call    cs:__imp_StrToID
0x18000b907  cmp     ax, bx
0x18000b90a  jnz     short loc_18000B920
0x18000b90c  or      cs:?g_bfSqm_USAGE@@3KA, 4; ulong g_bfSqm_USAGE
0x18000b913  mov     rcx, rsi; this
0x18000b916  call    ?_OnBlockAll@CShareMediaCore@@AEAAJXZ; CShareMediaCore::_OnBlockAll(void)
0x18000b91b  jmp     loc_18000BA60
0x18000b920  lea     rcx, aCancelbutton; "CancelButton"
0x18000b927  call    cs:__imp_StrToID
0x18000b92d  cmp     ax, bx
0x18000b930  jnz     short loc_18000B93F
0x18000b932  mov     rcx, rsi; this
0x18000b935  call    ?_OnCancel@CShareMediaCore@@AEAAJXZ; CShareMediaCore::_OnCancel(void)
0x18000b93a  jmp     loc_18000BA60
0x18000b93f  lea     rcx, aOkbutton; "OKButton"
0x18000b946  call    cs:__imp_StrToID
0x18000b94c  cmp     ax, bx
0x18000b94f  jnz     short loc_18000B95E
0x18000b951  mov     rcx, rsi; this
0x18000b954  call    ?_OnOK@CShareMediaCore@@AEAAJXZ; CShareMediaCore::_OnOK(void)
0x18000b959  jmp     loc_18000BA60
0x18000b95e  lea     rcx, aTurnonmediasha; "TurnOnMediaSharing"
0x18000b965  call    cs:__imp_StrToID
0x18000b96b  cmp     ax, bx
0x18000b96e  jnz     short loc_18000B984
0x18000b970  or      cs:?g_bfSqm_USAGE@@3KA, 1; ulong g_bfSqm_USAGE
0x18000b977  mov     rcx, rsi; this
0x18000b97a  call    ?_OnTurnOnMediaSharing@CShareMediaCore@@AEAAJXZ; CShareMediaCore::_OnTurnOnMediaSharing(void)
0x18000b97f  jmp     loc_18000BA60
0x18000b984  lea     rcx, aLaunchservices_0; "LaunchServicesLink"
0x18000b98b  call    cs:__imp_StrToID
0x18000b991  cmp     ax, bx
0x18000b994  jnz     loc_18000BA64
0x18000b99a  bts     cs:?g_bfSqm_USAGE@@3KA, 10h; ulong g_bfSqm_USAGE
0x18000b9a2  mov     rcx, rsi; this
0x18000b9a5  call    ?_OnLaunchServicesMSC@CShareMediaCore@@AEAAJXZ; CShareMediaCore::_OnLaunchServicesMSC(void)
0x18000b9aa  jmp     loc_18000BA60
0x18000b9af  cmp     cs:?AuthorizationChange@CShareMediaPage@@2VUID@@A, rcx; UID CShareMediaPage::AuthorizationChange
0x18000b9b6  jnz     loc_18000BA64
0x18000b9bc  cmp     dword ptr [rsi+0F0h], 0
0x18000b9c3  jnz     loc_18000BA58
0x18000b9c9  mov     ecx, [rdi+20h]
0x18000b9cc  sub     ecx, 1
0x18000b9cf  jz      short loc_18000B9EF
0x18000b9d1  sub     ecx, 1
0x18000b9d4  jz      short loc_18000B9E5
0x18000b9d6  cmp     ecx, 1
0x18000b9d9  jnz     short loc_18000BA58
0x18000b9db  bts     cs:?g_bfSqm_USAGE@@3KA, 0Ah; ulong g_bfSqm_USAGE
0x18000b9e3  jmp     short loc_18000BA58
0x18000b9e5  bts     cs:?g_bfSqm_USAGE@@3KA, 9; ulong g_bfSqm_USAGE
0x18000b9ed  jmp     short loc_18000BA58
0x18000b9ef  bts     cs:?g_bfSqm_USAGE@@3KA, 8; ulong g_bfSqm_USAGE
0x18000b9f7  jmp     short loc_18000BA58
0x18000b9f9  call    cs:__imp_?SelectionChange@Combobox@DirectUI@@SA?AVUID@@XZ; DirectUI::Combobox::SelectionChange(void)
0x18000b9ff  mov     rcx, [rax]
0x18000ba02  cmp     [rdi+8], rcx
0x18000ba06  jnz     short loc_18000BA64
0x18000ba08  mov     rax, [rdi]
0x18000ba0b  lea     rcx, aNetworkfilterc; "NetworkFilterCombo"
0x18000ba12  movzx   ebx, word ptr [rax+90h]
0x18000ba19  call    cs:__imp_StrToID
0x18000ba1f  cmp     ax, bx
0x18000ba22  jnz     short loc_18000BA64
0x18000ba24  mov     rcx, [rdi]
0x18000ba27  test    rcx, rcx
0x18000ba2a  jz      short loc_18000BA64
0x18000ba2c  call    cs:__imp_?GetSelection@Combobox@DirectUI@@QEAAHXZ; DirectUI::Combobox::GetSelection(void)
0x18000ba32  cmp     eax, [rsi+0C0h]
0x18000ba38  jz      short loc_18000BA60
0x18000ba3a  bts     cs:?g_bfSqm_USAGE@@3KA, 11h; ulong g_bfSqm_USAGE
0x18000ba42  mov     rcx, [rsi+38h]; this
0x18000ba46  mov     [rsi+0C0h], eax
0x18000ba4c  test    rcx, rcx
0x18000ba4f  jz      short loc_18000BA60
0x18000ba51  mov     edx, eax; unsigned int
0x18000ba53  call    ?SetCurrentNetworkFilter@CShareWithList@@QEAAJK@Z; CShareWithList::SetCurrentNetworkFilter(ulong)
0x18000ba58  mov     rcx, rsi; this
0x18000ba5b  call    ?_UpdateStatusText@CShareMediaCore@@AEAAJXZ; CShareMediaCore::_UpdateStatusText(void)
0x18000ba60  mov     byte ptr [rdi+10h], 1
0x18000ba64  mov     rbx, [rsp+28h+arg_0]
0x18000ba69  mov     rsi, [rsp+28h+arg_10]
0x18000ba6e  add     rsp, 20h
0x18000ba72  pop     rdi
0x18000ba73  retn
```
