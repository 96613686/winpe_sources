# CFlyout::_GetElementPointers(void)

- ea: `0x180011ff0`
- end: `0x180012189`
- name: `?_GetElementPointers@CFlyout@@AEAAJXZ`
- size: `409`
- prototype: `__int64 __fastcall(CFlyout *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation`

## callers

- `0x180011950`

## callees

- `0x180010d50`
- `0x180011ff0`
- `0x18002a010`

## import_xrefs

- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x180012015`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x180012050`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x1800120cf`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x1800120f8`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x18001211d`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x180012142`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x180012167`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x180012015`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x180012050`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x1800120cf`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x1800120f8`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x18001211d`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x180012142`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x180012167`
- `DUI70!StrToID` at `0x180012009`
- `DUI70!StrToID` at `0x180012044`
- `DUI70!StrToID` at `0x18001206d`
- `DUI70!StrToID` at `0x180012098`
- `DUI70!StrToID` at `0x1800120c3`
- `DUI70!StrToID` at `0x1800120ec`
- `DUI70!StrToID` at `0x180012111`
- `DUI70!StrToID` at `0x180012136`
- `DUI70!StrToID` at `0x18001215b`
- `DUI70!StrToID` at `0x180012009`
- `DUI70!StrToID` at `0x180012044`
- `DUI70!StrToID` at `0x18001206d`
- `DUI70!StrToID` at `0x180012098`
- `DUI70!StrToID` at `0x1800120c3`
- `DUI70!StrToID` at `0x1800120ec`
- `DUI70!StrToID` at `0x180012111`
- `DUI70!StrToID` at `0x180012136`
- `DUI70!StrToID` at `0x18001215b`

## string_xrefs

- `0x1800120bc`: `ExtraClocksPanel`
- `0x1800120e5`: `ExtraClock1`
- `0x18001210a`: `ExtraClock2`

## pseudocode

```c
__int64 __fastcall CFlyout::_GetElementPointers(CFlyout *this)
{
  unsigned int v2; // edi
  unsigned __int16 v3; // ax
  struct DirectUI::Element *Descendent; // rax
  unsigned __int16 v5; // ax
  struct DirectUI::Element *v6; // rax
  unsigned __int16 v7; // ax
  struct CCAnalogClock *ClockElement; // rax
  unsigned __int16 v9; // ax
  struct CCAnalogClock *v10; // rax
  unsigned __int16 v11; // ax
  struct DirectUI::Element *v12; // rax
  unsigned __int16 v13; // ax
  struct DirectUI::Element *v14; // rax
  unsigned __int16 v15; // ax
  struct DirectUI::Element *v16; // rax
  unsigned __int16 v17; // ax
  struct DirectUI::Element *v18; // rax
  unsigned __int16 v19; // ax
  struct DirectUI::Element *v20; // rax

  v2 = -2147467259;
  v3 = StrToID(L"MonthCalendar");
  Descendent = DirectUI::Element::FindDescendent(this, v3);
  *((_QWORD *)this + 40) = Descendent;
  if ( Descendent )
  {
    (*(void (__fastcall **)(CFlyout *))(*(_QWORD *)this + 472LL))(this);
    v5 = StrToID(L"MainClockPanel");
    v6 = DirectUI::Element::FindDescendent(this, v5);
    *((_QWORD *)this + 34) = v6;
    if ( v6 )
    {
      v7 = StrToID(L"MainClock");
      ClockElement = CFlyout::GetClockElement(this, v7, 0);
      *((_QWORD *)this + 41) = ClockElement;
      if ( ClockElement )
      {
        v9 = StrToID(L"MainDigitalClock");
        v10 = CFlyout::GetClockElement(this, v9, 0);
        *((_QWORD *)this + 37) = v10;
        if ( v10 )
        {
          v11 = StrToID(L"ExtraClocksPanel");
          v12 = DirectUI::Element::FindDescendent(this, v11);
          *((_QWORD *)this + 35) = v12;
          if ( v12 )
          {
            v13 = StrToID(L"ExtraClock1");
            v14 = DirectUI::Element::FindDescendent(this, v13);
            *((_QWORD *)this + 38) = v14;
            if ( v14 )
            {
              v15 = StrToID(L"ExtraClock2");
              v16 = DirectUI::Element::FindDescendent(this, v15);
              *((_QWORD *)this + 39) = v16;
              if ( v16 )
              {
                v17 = StrToID(L"NotificationPanel");
                v18 = DirectUI::Element::FindDescendent(this, v17);
                *((_QWORD *)this + 44) = v18;
                if ( v18 )
                {
                  v19 = StrToID(L"MainClockDayName");
                  v20 = DirectUI::Element::FindDescendent(this, v19);
                  *((_QWORD *)this + 45) = v20;
                  if ( v20 )
                    return 0;
                }
              }
            }
          }
        }
      }
    }
  }
  return v2;
}

```

## disassembly

```asm
0x180011ff0  mov     [rsp+arg_0], rbx
0x180011ff5  push    rdi
0x180011ff6  sub     rsp, 20h
0x180011ffa  mov     rbx, rcx
0x180011ffd  mov     edi, 80004005h
0x180012002  lea     rcx, aMonthcalendar; "MonthCalendar"
0x180012009  call    cs:__imp_StrToID
0x18001200f  movzx   edx, ax
0x180012012  mov     rcx, rbx
0x180012015  call    cs:__imp_?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z; DirectUI::Element::FindDescendent(ushort)
0x18001201b  mov     [rbx+140h], rax
0x180012022  test    rax, rax
0x180012025  jz      loc_18001217C
0x18001202b  mov     rax, [rbx]
0x18001202e  mov     rcx, rbx
0x180012031  mov     rax, [rax+1D8h]
0x180012038  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001203d  lea     rcx, aMainclockpanel; "MainClockPanel"
0x180012044  call    cs:__imp_StrToID
0x18001204a  movzx   edx, ax
0x18001204d  mov     rcx, rbx
0x180012050  call    cs:__imp_?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z; DirectUI::Element::FindDescendent(ushort)
0x180012056  mov     [rbx+110h], rax
0x18001205d  test    rax, rax
0x180012060  jz      loc_18001217C
0x180012066  lea     rcx, aMainclock; "MainClock"
0x18001206d  call    cs:__imp_StrToID
0x180012073  xor     r8d, r8d; unsigned int
0x180012076  mov     rcx, rbx; this
0x180012079  movzx   edx, ax; unsigned __int16
0x18001207c  call    ?GetClockElement@CFlyout@@AEAAPEAVCCAnalogClock@@GI@Z; CFlyout::GetClockElement(ushort,uint)
0x180012081  mov     [rbx+148h], rax
0x180012088  test    rax, rax
0x18001208b  jz      loc_18001217C
0x180012091  lea     rcx, aMaindigitalclo; "MainDigitalClock"
0x180012098  call    cs:__imp_StrToID
0x18001209e  xor     r8d, r8d; unsigned int
0x1800120a1  mov     rcx, rbx; this
0x1800120a4  movzx   edx, ax; unsigned __int16
0x1800120a7  call    ?GetClockElement@CFlyout@@AEAAPEAVCCAnalogClock@@GI@Z; CFlyout::GetClockElement(ushort,uint)
0x1800120ac  mov     [rbx+128h], rax
0x1800120b3  test    rax, rax
0x1800120b6  jz      loc_18001217C
0x1800120bc  lea     rcx, aExtraclockspan; "ExtraClocksPanel"
0x1800120c3  call    cs:__imp_StrToID
0x1800120c9  movzx   edx, ax
0x1800120cc  mov     rcx, rbx
0x1800120cf  call    cs:__imp_?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z; DirectUI::Element::FindDescendent(ushort)
0x1800120d5  mov     [rbx+118h], rax
0x1800120dc  test    rax, rax
0x1800120df  jz      loc_18001217C
0x1800120e5  lea     rcx, aExtraclock1; "ExtraClock1"
0x1800120ec  call    cs:__imp_StrToID
0x1800120f2  movzx   edx, ax
0x1800120f5  mov     rcx, rbx
0x1800120f8  call    cs:__imp_?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z; DirectUI::Element::FindDescendent(ushort)
0x1800120fe  mov     [rbx+130h], rax
0x180012105  test    rax, rax
0x180012108  jz      short loc_18001217C
0x18001210a  lea     rcx, aExtraclock2; "ExtraClock2"
0x180012111  call    cs:__imp_StrToID
0x180012117  movzx   edx, ax
0x18001211a  mov     rcx, rbx
0x18001211d  call    cs:__imp_?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z; DirectUI::Element::FindDescendent(ushort)
0x180012123  mov     [rbx+138h], rax
0x18001212a  test    rax, rax
0x18001212d  jz      short loc_18001217C
0x18001212f  lea     rcx, aNotificationpa; "NotificationPanel"
0x180012136  call    cs:__imp_StrToID
0x18001213c  movzx   edx, ax
0x18001213f  mov     rcx, rbx
0x180012142  call    cs:__imp_?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z; DirectUI::Element::FindDescendent(ushort)
0x180012148  mov     [rbx+160h], rax
0x18001214f  test    rax, rax
0x180012152  jz      short loc_18001217C
0x180012154  lea     rcx, aMainclockdayna; "MainClockDayName"
0x18001215b  call    cs:__imp_StrToID
0x180012161  movzx   edx, ax
0x180012164  mov     rcx, rbx
0x180012167  call    cs:__imp_?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z; DirectUI::Element::FindDescendent(ushort)
0x18001216d  xor     ecx, ecx
0x18001216f  mov     [rbx+168h], rax
0x180012176  test    rax, rax
0x180012179  cmovnz  edi, ecx
0x18001217c  mov     rbx, [rsp+28h+arg_0]
0x180012181  mov     eax, edi
0x180012183  add     rsp, 20h
0x180012187  pop     rdi
0x180012188  retn
```
