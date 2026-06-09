# CFlyout::OnInput(DirectUI::InputEvent *)

- ea: `0x1800112a0`
- end: `0x180011381`
- name: `?OnInput@CFlyout@@MEAAXPEAUInputEvent@DirectUI@@@Z`
- size: `225`
- prototype: `void __fastcall(CFlyout *__hidden this, struct DirectUI::InputEvent *)`
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config`

## callees

- `0x1800112a0`
- `0x180011774`
- `0x180013274`
- `0x18002a010`

## import_xrefs

- `USER32!GetAncestor` at `0x180011366`
- `USER32!GetAncestor` at `0x180011366`
- `USER32!PostMessageW` at `0x180011379`
- `USER32!PostMessageW` at `0x180011379`
- `DUI70!StrToID` at `0x1800112ef`
- `DUI70!StrToID` at `0x18001131b`
- `DUI70!StrToID` at `0x1800112ef`
- `DUI70!StrToID` at `0x18001131b`
- `DUI70!?OnInput@HWNDElement@DirectUI@@UEAAXPEAUInputEvent@2@@Z` at `0x180011348`
- `DUI70!?GetID@Element@DirectUI@@QEAAGXZ` at `0x1800112df`
- `DUI70!?GetID@Element@DirectUI@@QEAAGXZ` at `0x18001130b`
- `DUI70!?GetID@Element@DirectUI@@QEAAGXZ` at `0x1800112df`
- `DUI70!?GetID@Element@DirectUI@@QEAAGXZ` at `0x18001130b`

## string_xrefs

- `0x1800112e5`: `SettingsLink`

## pseudocode

```c
void __fastcall CFlyout::OnInput(CFlyout *this, struct DirectUI::InputEvent *a2)
{
  unsigned __int16 ID; // bx
  unsigned __int16 v5; // bx
  HWND v6; // rax
  HWND Ancestor; // rax

  if ( *(_QWORD *)((char *)a2 + 12) == 0x100000002LL && *((_DWORD *)a2 + 5) <= 1u )
  {
    switch ( *((_WORD *)a2 + 16) )
    {
      case 0xD:
        goto LABEL_6;
      case 0x1B:
        v6 = (HWND)(*(__int64 (__fastcall **)(CFlyout *))(*(_QWORD *)this + 360LL))(this);
        Ancestor = GetAncestor(v6, 1u);
        PostMessageW(Ancestor, 6u, 0, 0);
        break;
      case 0x20:
LABEL_6:
        ID = DirectUI::Element::GetID(*(DirectUI::Element **)a2);
        if ( ID == (unsigned __int16)StrToID(L"SettingsLink") )
          OpenCpl(L"timedate.cpl", 0);
        v5 = DirectUI::Element::GetID(*(DirectUI::Element **)a2);
        if ( v5 == (unsigned __int16)StrToID(L"TodayStr") )
          CFlyout::ResetCalendar(this, 1);
        break;
    }
  }
  DirectUI::HWNDElement::OnInput(this, a2);
}

```

## disassembly

```asm
0x1800112a0  mov     [rsp+arg_0], rbx
0x1800112a5  mov     [rsp+arg_8], rsi
0x1800112aa  push    rdi
0x1800112ab  sub     rsp, 20h
0x1800112af  cmp     dword ptr [rdx+0Ch], 2
0x1800112b3  mov     rdi, rdx
0x1800112b6  mov     rsi, rcx
0x1800112b9  jnz     short loc_180011333
0x1800112bb  cmp     dword ptr [rdx+10h], 1
0x1800112bf  jnz     short loc_180011333
0x1800112c1  cmp     dword ptr [rdx+14h], 1
0x1800112c5  ja      short loc_180011333
0x1800112c7  cmp     word ptr [rdx+20h], 0Dh
0x1800112cc  jz      short loc_1800112DC
0x1800112ce  cmp     word ptr [rdx+20h], 1Bh
0x1800112d3  jz      short loc_18001134F
0x1800112d5  cmp     word ptr [rdx+20h], 20h ; ' '
0x1800112da  jnz     short loc_180011333
0x1800112dc  mov     rcx, [rdx]
0x1800112df  call    cs:__imp_?GetID@Element@DirectUI@@QEAAGXZ; DirectUI::Element::GetID(void)
0x1800112e5  lea     rcx, aSettingslink; "SettingsLink"
0x1800112ec  movzx   ebx, ax
0x1800112ef  call    cs:__imp_StrToID
0x1800112f5  cmp     bx, ax
0x1800112f8  jnz     short loc_180011308
0x1800112fa  xor     edx, edx; unsigned __int16 *
0x1800112fc  lea     rcx, aTimedateCpl; "timedate.cpl"
0x180011303  call    ?OpenCpl@@YAHPEBG0@Z; OpenCpl(ushort const *,ushort const *)
0x180011308  mov     rcx, [rdi]
0x18001130b  call    cs:__imp_?GetID@Element@DirectUI@@QEAAGXZ; DirectUI::Element::GetID(void)
0x180011311  lea     rcx, aTodaystr; "TodayStr"
0x180011318  movzx   ebx, ax
0x18001131b  call    cs:__imp_StrToID
0x180011321  cmp     bx, ax
0x180011324  jnz     short loc_180011333
0x180011326  mov     edx, 1; int
0x18001132b  mov     rcx, rsi; this
0x18001132e  call    ?ResetCalendar@CFlyout@@QEAAXH@Z; CFlyout::ResetCalendar(int)
0x180011333  mov     rdx, rdi
0x180011336  mov     rcx, rsi
0x180011339  mov     rbx, [rsp+28h+arg_0]
0x18001133e  mov     rsi, [rsp+28h+arg_8]
0x180011343  add     rsp, 20h
0x180011347  pop     rdi
0x180011348  jmp     cs:__imp_?OnInput@HWNDElement@DirectUI@@UEAAXPEAUInputEvent@2@@Z; DirectUI::HWNDElement::OnInput(DirectUI::InputEvent *)
0x18001134f  mov     rax, [rcx]
0x180011352  mov     rax, [rax+168h]
0x180011359  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001135e  mov     rcx, rax; hwnd
0x180011361  mov     edx, 1; gaFlags
0x180011366  call    cs:__imp_GetAncestor
0x18001136c  xor     r9d, r9d; lParam
0x18001136f  xor     r8d, r8d; wParam
0x180011372  mov     rcx, rax; hWnd
0x180011375  lea     edx, [r9+6]; Msg
0x180011379  call    cs:__imp_PostMessageW
0x18001137f  jmp     short loc_180011333
```
