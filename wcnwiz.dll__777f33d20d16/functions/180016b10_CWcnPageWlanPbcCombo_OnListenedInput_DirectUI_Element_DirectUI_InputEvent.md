# CWcnPageWlanPbcCombo::OnListenedInput(DirectUI::Element *,DirectUI::InputEvent *)

- ea: `0x180016b10`
- end: `0x180016b72`
- name: `?OnListenedInput@CWcnPageWlanPbcCombo@@UEAAXPEAVElement@DirectUI@@PEAUInputEvent@3@@Z`
- size: `98`
- prototype: `void __fastcall(CWcnPageWlanPbcCombo *__hidden this, struct DirectUI::Element *, struct DirectUI::InputEvent *)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x180016b10`
- `0x1800172d8`

## import_xrefs

- `DUI70!?GetID@Element@DirectUI@@QEAAGXZ` at `0x180016b37`
- `DUI70!?GetID@Element@DirectUI@@QEAAGXZ` at `0x180016b37`
- `DUI70!StrToID` at `0x180016b47`
- `DUI70!StrToID` at `0x180016b47`

## string_xrefs

- `0x180016b3d`: `PageWlanPbcCombo_Link`

## pseudocode

```c
void __fastcall CWcnPageWlanPbcCombo::OnListenedInput(
        CWcnPageWlanPbcCombo *this,
        struct DirectUI::Element *a2,
        DirectUI::Element **a3)
{
  unsigned __int16 ID; // bx

  if ( *((_DWORD *)a3 + 4) == 1 && *((_WORD *)a3 + 16) == 13 )
  {
    ID = DirectUI::Element::GetID(*a3);
    if ( ID == (unsigned __int16)StrToID(L"PageWlanPbcCombo_Link") )
    {
      CWcnPageWlanPbcCombo::_OnLinkClicked((CWcnPageWlanPbcCombo *)((char *)this - 344));
      *((_BYTE *)a3 + 8) = 1;
    }
  }
}

```

## disassembly

```asm
0x180016b10  mov     [rsp+arg_0], rbx
0x180016b15  mov     [rsp+arg_8], rsi
0x180016b1a  push    rdi
0x180016b1b  sub     rsp, 20h
0x180016b1f  cmp     dword ptr [r8+10h], 1
0x180016b24  mov     rdi, r8
0x180016b27  mov     rsi, rcx
0x180016b2a  jnz     short loc_180016B62
0x180016b2c  cmp     word ptr [r8+20h], 0Dh
0x180016b32  jnz     short loc_180016B62
0x180016b34  mov     rcx, [r8]
0x180016b37  call    cs:__imp_?GetID@Element@DirectUI@@QEAAGXZ; DirectUI::Element::GetID(void)
0x180016b3d  lea     rcx, aPagewlanpbccom; "PageWlanPbcCombo_Link"
0x180016b44  movzx   ebx, ax
0x180016b47  call    cs:__imp_StrToID
0x180016b4d  cmp     bx, ax
0x180016b50  jnz     short loc_180016B62
0x180016b52  lea     rcx, [rsi-158h]; this
0x180016b59  call    ?_OnLinkClicked@CWcnPageWlanPbcCombo@@AEAAXXZ; CWcnPageWlanPbcCombo::_OnLinkClicked(void)
0x180016b5e  mov     byte ptr [rdi+8], 1
0x180016b62  mov     rbx, [rsp+28h+arg_0]
0x180016b67  mov     rsi, [rsp+28h+arg_8]
0x180016b6c  add     rsp, 20h
0x180016b70  pop     rdi
0x180016b71  retn
```
