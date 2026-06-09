# CWcnPageWlanPbcCombo::OnListenedEvent(DirectUI::Element *,DirectUI::Event *)

- ea: `0x180016a60`
- end: `0x180016b05`
- name: `?OnListenedEvent@CWcnPageWlanPbcCombo@@UEAAXPEAVElement@DirectUI@@PEAUEvent@3@@Z`
- size: `165`
- prototype: `void __fastcall(CWcnPageWlanPbcCombo *__hidden this, struct DirectUI::Element *, struct DirectUI::Event *)`
- caller_count: `0`
- callee_count: `4`
- tags: `installer_update, broker_com_uri`

## callees

- `0x180011d94`
- `0x180016a60`
- `0x1800172d8`
- `0x1800173e8`

## import_xrefs

- `DUI70!?GetID@Element@DirectUI@@QEAAGXZ` at `0x180016a9c`
- `DUI70!?GetID@Element@DirectUI@@QEAAGXZ` at `0x180016a9c`
- `DUI70!StrToID` at `0x180016aac`
- `DUI70!StrToID` at `0x180016aac`
- `DUI70!?Click@TouchButton@DirectUI@@SA?AVUID@@XZ` at `0x180016a7d`
- `DUI70!?UserTextChanged@TouchEditBase@DirectUI@@SA?AVUID@@XZ` at `0x180016ace`
- `DUI70!?UserTextChanged@TouchEditBase@DirectUI@@SA?AVUID@@XZ` at `0x180016ace`

## string_xrefs

- `0x180016aa2`: `PageWlanPbcCombo_Link`

## pseudocode

```c
void __fastcall CWcnPageWlanPbcCombo::OnListenedEvent(
        DirectUI::Element **this,
        struct DirectUI::Element *a2,
        DirectUI::Element **a3)
{
  unsigned __int16 ID; // bx
  __int64 v6; // [rsp+40h] [rbp+18h] BYREF

  if ( *((_DWORD *)a3 + 5) == 1 )
  {
    v6 = DirectUI::TouchButton::Click;
    if ( (unsigned __int8)operator==(a3 + 1, &v6) )
    {
      ID = DirectUI::Element::GetID(*a3);
      if ( ID == (unsigned __int16)StrToID(L"PageWlanPbcCombo_Link") )
      {
        CWcnPageWlanPbcCombo::_OnLinkClicked((CWcnPageWlanPbcCombo *)(this - 43));
        *((_BYTE *)a3 + 16) = 1;
      }
    }
    else if ( a3[1] == *(DirectUI::Element **)DirectUI::TouchEditBase::UserTextChanged(&v6) && *a3 == this[28] )
    {
      CWcnPageWlanPbcCombo::_UpdateDisabledWidgets((CWcnPageWlanPbcCombo *)(this - 43));
    }
  }
}

```

## disassembly

```asm
0x180016a60  mov     r11, rsp
0x180016a63  mov     [r11+8], rbx
0x180016a67  mov     [r11+10h], rsi
0x180016a6b  push    rdi
0x180016a6c  sub     rsp, 20h
0x180016a70  cmp     dword ptr [r8+14h], 1
0x180016a75  mov     rdi, r8
0x180016a78  mov     rsi, rcx
0x180016a7b  jnz     short loc_180016AF5
0x180016a7d  mov     rax, cs:__imp_?Click@TouchButton@DirectUI@@SA?AVUID@@XZ; DirectUI::TouchButton::Click(void)
0x180016a84  lea     rdx, [r11+18h]
0x180016a88  lea     rcx, [r8+8]
0x180016a8c  mov     [r11+18h], rax
0x180016a90  call    ??8@YA_NAEBVUID@@AEBQ6A?AV0@XZ@Z; operator==(UID const &,UID (*const &)(void))
0x180016a95  test    al, al
0x180016a97  jz      short loc_180016AC9
0x180016a99  mov     rcx, [rdi]
0x180016a9c  call    cs:__imp_?GetID@Element@DirectUI@@QEAAGXZ; DirectUI::Element::GetID(void)
0x180016aa2  lea     rcx, aPagewlanpbccom; "PageWlanPbcCombo_Link"
0x180016aa9  movzx   ebx, ax
0x180016aac  call    cs:__imp_StrToID
0x180016ab2  cmp     bx, ax
0x180016ab5  jnz     short loc_180016AF5
0x180016ab7  lea     rcx, [rsi-158h]; this
0x180016abe  call    ?_OnLinkClicked@CWcnPageWlanPbcCombo@@AEAAXXZ; CWcnPageWlanPbcCombo::_OnLinkClicked(void)
0x180016ac3  mov     byte ptr [rdi+10h], 1
0x180016ac7  jmp     short loc_180016AF5
0x180016ac9  lea     rcx, [rsp+28h+arg_10]
0x180016ace  call    cs:__imp_?UserTextChanged@TouchEditBase@DirectUI@@SA?AVUID@@XZ; DirectUI::TouchEditBase::UserTextChanged(void)
0x180016ad4  mov     rcx, [rax]
0x180016ad7  cmp     [rdi+8], rcx
0x180016adb  jnz     short loc_180016AF5
0x180016add  lea     rcx, [rsi-158h]; this
0x180016ae4  mov     rax, [rcx+238h]
0x180016aeb  cmp     [rdi], rax
0x180016aee  jnz     short loc_180016AF5
0x180016af0  call    ?_UpdateDisabledWidgets@CWcnPageWlanPbcCombo@@AEAAXXZ; CWcnPageWlanPbcCombo::_UpdateDisabledWidgets(void)
0x180016af5  mov     rbx, [rsp+28h+arg_0]
0x180016afa  mov     rsi, [rsp+28h+arg_8]
0x180016aff  add     rsp, 20h
0x180016b03  pop     rdi
0x180016b04  retn
```
