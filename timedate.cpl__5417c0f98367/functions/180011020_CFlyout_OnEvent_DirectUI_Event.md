# CFlyout::OnEvent(DirectUI::Event *)

- ea: `0x180011020`
- end: `0x180011194`
- name: `?OnEvent@CFlyout@@MEAAXPEAUEvent@DirectUI@@@Z`
- size: `372`
- prototype: `void __fastcall(CFlyout *__hidden this, struct DirectUI::Event *)`
- caller_count: `0`
- callee_count: `6`
- tags: `registry_config`

## callees

- `0x1800105f0`
- `0x180010cec`
- `0x180011020`
- `0x180011774`
- `0x1800121c8`
- `0x180013274`

## import_xrefs

- `DUI70!?StartDefer@Element@DirectUI@@QEAAXPEAK@Z` at `0x18001111c`
- `DUI70!?StartDefer@Element@DirectUI@@QEAAXPEAK@Z` at `0x18001111c`
- `DUI70!StrToID` at `0x180011072`
- `DUI70!StrToID` at `0x1800110a7`
- `DUI70!StrToID` at `0x180011072`
- `DUI70!StrToID` at `0x1800110a7`
- `DUI70!?KeyboardNavigate@Element@DirectUI@@SA?AVUID@@XZ` at `0x1800110c5`
- `DUI70!?Click@Button@DirectUI@@SA?AVUID@@XZ` at `0x180011040`
- `DUI70!?OnEvent@HWNDElement@DirectUI@@UEAAXPEAUEvent@2@@Z` at `0x18001117e`
- `DUI70!?OnEvent@HWNDElement@DirectUI@@UEAAXPEAUEvent@2@@Z` at `0x18001117e`
- `DUI70!?GetID@Element@DirectUI@@QEAAGXZ` at `0x180011062`
- `DUI70!?GetID@Element@DirectUI@@QEAAGXZ` at `0x180011097`
- `DUI70!?GetID@Element@DirectUI@@QEAAGXZ` at `0x180011062`
- `DUI70!?GetID@Element@DirectUI@@QEAAGXZ` at `0x180011097`

## string_xrefs

- `0x180011068`: `SettingsLink`

## pseudocode

```c
void __fastcall CFlyout::OnEvent(struct CCAnalogClock **this, DirectUI::Element **a2)
{
  _QWORD *v4; // rbx
  unsigned __int16 ID; // bx
  unsigned __int16 v6; // bx
  struct CCAnalogClock *v7; // rdx
  struct CCAnalogClock **v8; // [rsp+20h] [rbp-18h] BYREF
  unsigned int v9[4]; // [rsp+28h] [rbp-10h] BYREF
  __int64 v10; // [rsp+48h] [rbp+10h] BYREF

  if ( *((_DWORD *)a2 + 5) == 2 )
  {
    v4 = a2 + 1;
    v10 = DirectUI::Button::Click;
    if ( (unsigned __int8)operator==(a2 + 1, &v10) )
    {
      ID = DirectUI::Element::GetID(*a2);
      if ( ID == (unsigned __int16)StrToID(L"SettingsLink") )
      {
        OpenCpl(L"timedate.cpl", 0);
LABEL_5:
        *((_BYTE *)a2 + 16) = 1;
        return;
      }
      v6 = DirectUI::Element::GetID(*a2);
      if ( v6 == (unsigned __int16)StrToID(L"TodayStr") )
      {
        CFlyout::ResetCalendar((CFlyout *)this, 1);
        goto LABEL_5;
      }
      goto LABEL_20;
    }
    v10 = DirectUI::Element::KeyboardNavigate;
    if ( (unsigned __int8)operator==(v4, &v10) )
    {
      if ( g_fMonthcalTab )
      {
        g_fMonthcalTab = 0;
        goto LABEL_5;
      }
      goto LABEL_20;
    }
    if ( *v4 == CFlyout::DayTransitionEvent )
    {
      v8 = this;
      v9[0] = 0;
      DirectUI::Element::StartDefer((DirectUI::Element *)this, v9);
      if ( *((_DWORD *)a2 + 10) )
      {
        if ( *((_DWORD *)this + 64) )
          CFlyout::_SetClockDay(this, this[42]);
        if ( !*((_DWORD *)this + 65) )
          goto LABEL_19;
        v7 = this[43];
      }
      else
      {
        v7 = a2[4];
      }
      CFlyout::_SetClockDay(this, v7);
LABEL_19:
      DirectUI::AutoDefer::EndDefer((DirectUI::AutoDefer *)&v8);
      *((_BYTE *)a2 + 16) = 1;
      DirectUI::AutoDefer::EndDefer((DirectUI::AutoDefer *)&v8);
      return;
    }
  }
LABEL_20:
  DirectUI::HWNDElement::OnEvent((DirectUI::HWNDElement *)this, (struct DirectUI::Event *)a2);
}

```

## disassembly

```asm
0x180011020  mov     r11, rsp
0x180011023  mov     [r11+8], rbx
0x180011027  mov     [r11+18h], rsi
0x18001102b  push    rdi
0x18001102c  sub     rsp, 30h
0x180011030  cmp     dword ptr [rdx+14h], 2
0x180011034  mov     rsi, rdx
0x180011037  mov     rdi, rcx
0x18001103a  jnz     loc_180011178
0x180011040  mov     rax, cs:__imp_?Click@Button@DirectUI@@SA?AVUID@@XZ; DirectUI::Button::Click(void)
0x180011047  lea     rbx, [rdx+8]
0x18001104b  mov     rcx, rbx
0x18001104e  mov     [r11+10h], rax
0x180011052  lea     rdx, [r11+10h]
0x180011056  call    ??8@YA_NAEBVUID@@AEBQ6A?AV0@XZ@Z; operator==(UID const &,UID (*const &)(void))
0x18001105b  test    al, al
0x18001105d  jz      short loc_1800110C5
0x18001105f  mov     rcx, [rsi]
0x180011062  call    cs:__imp_?GetID@Element@DirectUI@@QEAAGXZ; DirectUI::Element::GetID(void)
0x180011068  lea     rcx, aSettingslink; "SettingsLink"
0x18001106f  movzx   ebx, ax
0x180011072  call    cs:__imp_StrToID
0x180011078  cmp     bx, ax
0x18001107b  jnz     short loc_180011094
0x18001107d  xor     edx, edx; unsigned __int16 *
0x18001107f  lea     rcx, aTimedateCpl; "timedate.cpl"
0x180011086  call    ?OpenCpl@@YAHPEBG0@Z; OpenCpl(ushort const *,ushort const *)
0x18001108b  mov     byte ptr [rsi+10h], 1
0x18001108f  jmp     loc_180011184
0x180011094  mov     rcx, [rsi]
0x180011097  call    cs:__imp_?GetID@Element@DirectUI@@QEAAGXZ; DirectUI::Element::GetID(void)
0x18001109d  lea     rcx, aTodaystr; "TodayStr"
0x1800110a4  movzx   ebx, ax
0x1800110a7  call    cs:__imp_StrToID
0x1800110ad  cmp     bx, ax
0x1800110b0  jnz     loc_180011178
0x1800110b6  mov     edx, 1; int
0x1800110bb  mov     rcx, rdi; this
0x1800110be  call    ?ResetCalendar@CFlyout@@QEAAXH@Z; CFlyout::ResetCalendar(int)
0x1800110c3  jmp     short loc_18001108B
0x1800110c5  mov     rax, cs:__imp_?KeyboardNavigate@Element@DirectUI@@SA?AVUID@@XZ; DirectUI::Element::KeyboardNavigate(void)
0x1800110cc  lea     rdx, [rsp+38h+arg_8]
0x1800110d1  mov     rcx, rbx
0x1800110d4  mov     [rsp+38h+arg_8], rax
0x1800110d9  call    ??8@YA_NAEBVUID@@AEBQ6A?AV0@XZ@Z; operator==(UID const &,UID (*const &)(void))
0x1800110de  test    al, al
0x1800110e0  jz      short loc_1800110FB
0x1800110e2  cmp     cs:?g_fMonthcalTab@@3IA, 0; uint g_fMonthcalTab
0x1800110e9  jz      loc_180011178
0x1800110ef  mov     cs:?g_fMonthcalTab@@3IA, 0; uint g_fMonthcalTab
0x1800110f9  jmp     short loc_18001108B
0x1800110fb  mov     rax, cs:?DayTransitionEvent@CFlyout@@2VUID@@A; UID CFlyout::DayTransitionEvent
0x180011102  cmp     [rbx], rax
0x180011105  jnz     short loc_180011178
0x180011107  lea     rdx, [rsp+38h+var_10]
0x18001110c  mov     [rsp+38h+var_18], rdi
0x180011111  mov     rcx, rdi
0x180011114  mov     [rsp+38h+var_10], 0
0x18001111c  call    cs:__imp_?StartDefer@Element@DirectUI@@QEAAXPEAK@Z; DirectUI::Element::StartDefer(ulong *)
0x180011122  cmp     dword ptr [rsi+28h], 0
0x180011126  jz      short loc_180011152
0x180011128  cmp     dword ptr [rdi+100h], 0
0x18001112f  jz      short loc_180011140
0x180011131  mov     rdx, [rdi+150h]; struct CCAnalogClock *
0x180011138  mov     rcx, rdi; this
0x18001113b  call    ?_SetClockDay@CFlyout@@AEAAHPEAVCCAnalogClock@@@Z; CFlyout::_SetClockDay(CCAnalogClock *)
0x180011140  cmp     dword ptr [rdi+104h], 0
0x180011147  jz      short loc_18001115E
0x180011149  mov     rdx, [rdi+158h]
0x180011150  jmp     short loc_180011156
0x180011152  mov     rdx, [rsi+20h]; struct CCAnalogClock *
0x180011156  mov     rcx, rdi; this
0x180011159  call    ?_SetClockDay@CFlyout@@AEAAHPEAVCCAnalogClock@@@Z; CFlyout::_SetClockDay(CCAnalogClock *)
0x18001115e  lea     rcx, [rsp+38h+var_18]; this
0x180011163  call    ?EndDefer@AutoDefer@DirectUI@@QEAAXXZ; DirectUI::AutoDefer::EndDefer(void)
0x180011168  lea     rcx, [rsp+38h+var_18]; this
0x18001116d  mov     byte ptr [rsi+10h], 1
0x180011171  call    ?EndDefer@AutoDefer@DirectUI@@QEAAXXZ; DirectUI::AutoDefer::EndDefer(void)
0x180011176  jmp     short loc_180011184
0x180011178  mov     rdx, rsi
0x18001117b  mov     rcx, rdi
0x18001117e  call    cs:__imp_?OnEvent@HWNDElement@DirectUI@@UEAAXPEAUEvent@2@@Z; DirectUI::HWNDElement::OnEvent(DirectUI::Event *)
0x180011184  mov     rbx, [rsp+38h+arg_0]
0x180011189  mov     rsi, [rsp+38h+arg_10]
0x18001118e  add     rsp, 30h
0x180011192  pop     rdi
0x180011193  retn
```
