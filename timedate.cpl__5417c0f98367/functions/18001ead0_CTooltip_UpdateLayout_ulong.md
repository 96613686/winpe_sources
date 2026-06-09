# CTooltip::UpdateLayout(ulong *)

- ea: `0x18001ead0`
- end: `0x18001ec93`
- name: `?UpdateLayout@CTooltip@@UEAAJPEAK@Z`
- size: `451`
- prototype: `__int64 __fastcall(CTooltip *__hidden this, unsigned int *)`
- caller_count: `0`
- callee_count: `7`
- tags: `authz_impersonation, installer_update`

## callees

- `0x180004368`
- `0x180004450`
- `0x180012350`
- `0x18001ead0`
- `0x18001ed20`
- `0x18001eea8`
- `0x18002a010`

## import_xrefs

- `USER32!GetAncestor` at `0x18001ec60`
- `USER32!GetAncestor` at `0x18001ec60`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x18001eb17`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x18001eb45`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x18001eb78`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x18001eb9d`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x18001eb17`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x18001eb45`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x18001eb78`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x18001eb9d`
- `DUI70!StrToID` at `0x18001eb0b`
- `DUI70!StrToID` at `0x18001eb39`
- `DUI70!StrToID` at `0x18001eb6c`
- `DUI70!StrToID` at `0x18001eb91`
- `DUI70!StrToID` at `0x18001eb0b`
- `DUI70!StrToID` at `0x18001eb39`
- `DUI70!StrToID` at `0x18001eb6c`
- `DUI70!StrToID` at `0x18001eb91`
- `DUI70!?SetLayoutPos@Element@DirectUI@@QEAAJH@Z` at `0x18001eb2c`
- `DUI70!?SetLayoutPos@Element@DirectUI@@QEAAJH@Z` at `0x18001ebc2`
- `DUI70!?SetLayoutPos@Element@DirectUI@@QEAAJH@Z` at `0x18001ebdb`
- `DUI70!?SetLayoutPos@Element@DirectUI@@QEAAJH@Z` at `0x18001eb2c`
- `DUI70!?SetLayoutPos@Element@DirectUI@@QEAAJH@Z` at `0x18001ebc2`
- `DUI70!?SetLayoutPos@Element@DirectUI@@QEAAJH@Z` at `0x18001ebdb`

## string_xrefs

- `0x18001eb65`: `ExtraClock1`
- `0x18001eb8a`: `ExtraClock2`

## pseudocode

```c
__int64 __fastcall CTooltip::UpdateLayout(CTooltip *this, unsigned int *a2)
{
  unsigned __int16 v3; // ax
  DirectUI::Element *Descendent; // rax
  unsigned __int16 v5; // ax
  struct DirectUI::Element *v6; // rax
  unsigned __int16 v7; // ax
  DirectUI::Element *v8; // rdi
  unsigned __int16 v9; // ax
  DirectUI::Element *v10; // rsi
  HWND v12; // rax
  HWND Ancestor; // rax
  void *v14; // [rsp+20h] [rbp-38h]

  (*(void (__fastcall **)(CTooltip *, unsigned int *))(*(_QWORD *)this + 472LL))(this, a2);
  if ( *((_QWORD *)this + 32) )
  {
    v3 = StrToID(L"MainClock");
    Descendent = DirectUI::Element::FindDescendent(this, v3);
    if ( !Descendent )
      return 2147500037LL;
    DirectUI::Element::SetLayoutPos(Descendent, 1);
    v5 = StrToID(L"MainDigitalClock");
    v6 = DirectUI::Element::FindDescendent(this, v5);
    *((_QWORD *)this + 33) = v6;
    if ( !v6 )
      return 2147500037LL;
    CTooltip::_DisplayLocalTime(this, 0);
  }
  v7 = StrToID(L"ExtraClock1");
  v8 = DirectUI::Element::FindDescendent(this, v7);
  if ( v8 )
  {
    v9 = StrToID(L"ExtraClock2");
    v10 = DirectUI::Element::FindDescendent(this, v9);
    if ( v10 )
    {
      DirectUI::Element::SetLayoutPos(v8, *((_DWORD *)this + 64) != 0 ? 1 : -3);
      DirectUI::Element::SetLayoutPos(v10, *((_DWORD *)this + 65) != 0 ? 1 : -3);
      if ( *((_DWORD *)this + 64) )
      {
        CTimeDate::_SetClockName(this, 1u);
        *((_QWORD *)this + 34) = CTooltip::_GetExtraTzTime(this, 1u, 0);
      }
      if ( *((_DWORD *)this + 65) )
      {
        CTimeDate::_SetClockName(this, 2u);
        *((_QWORD *)this + 35) = CTooltip::_GetExtraTzTime(this, 2u, 0);
      }
      if ( !(unsigned int)InitialiseClockSync(1u) )
        return 2147942414LL;
      v12 = (HWND)(*(__int64 (__fastcall **)(CTooltip *))(*(_QWORD *)this + 360LL))(this);
      Ancestor = GetAncestor(v12, 2u);
      if ( (unsigned int)RegisterClockSyncProc(
                           (void (*const)(const struct _SYSTEMTIME *, HWND, void *))NotifyTimeChange,
                           1,
                           0,
                           Ancestor,
                           v14) != -1 )
        return 0;
    }
  }
  return 2147500037LL;
}

```

## disassembly

```asm
0x18001ead0  push    rbx
0x18001ead2  push    rsi
0x18001ead3  push    rdi
0x18001ead4  push    r14
0x18001ead6  sub     rsp, 38h
0x18001eada  mov     rax, [rcx]
0x18001eadd  mov     rbx, rcx
0x18001eae0  mov     rax, [rax+1D8h]
0x18001eae7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001eaec  cmp     dword ptr [rbx+100h], 0
0x18001eaf3  mov     r14d, 1
0x18001eaf9  jnz     short loc_18001EB04
0x18001eafb  cmp     dword ptr [rbx+104h], 0
0x18001eb02  jz      short loc_18001EB65
0x18001eb04  lea     rcx, aMainclock; "MainClock"
0x18001eb0b  call    cs:__imp_StrToID
0x18001eb11  movzx   edx, ax
0x18001eb14  mov     rcx, rbx
0x18001eb17  call    cs:__imp_?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z; DirectUI::Element::FindDescendent(ushort)
0x18001eb1d  test    rax, rax
0x18001eb20  jz      loc_18001EC84
0x18001eb26  mov     edx, r14d
0x18001eb29  mov     rcx, rax
0x18001eb2c  call    cs:__imp_?SetLayoutPos@Element@DirectUI@@QEAAJH@Z; DirectUI::Element::SetLayoutPos(int)
0x18001eb32  lea     rcx, aMaindigitalclo; "MainDigitalClock"
0x18001eb39  call    cs:__imp_StrToID
0x18001eb3f  movzx   edx, ax
0x18001eb42  mov     rcx, rbx
0x18001eb45  call    cs:__imp_?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z; DirectUI::Element::FindDescendent(ushort)
0x18001eb4b  mov     [rbx+108h], rax
0x18001eb52  test    rax, rax
0x18001eb55  jz      loc_18001EC84
0x18001eb5b  xor     edx, edx; struct _SYSTEMTIME *
0x18001eb5d  mov     rcx, rbx; this
0x18001eb60  call    ?_DisplayLocalTime@CTooltip@@AEAAXPEBU_SYSTEMTIME@@@Z; CTooltip::_DisplayLocalTime(_SYSTEMTIME const *)
0x18001eb65  lea     rcx, aExtraclock1; "ExtraClock1"
0x18001eb6c  call    cs:__imp_StrToID
0x18001eb72  movzx   edx, ax
0x18001eb75  mov     rcx, rbx
0x18001eb78  call    cs:__imp_?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z; DirectUI::Element::FindDescendent(ushort)
0x18001eb7e  mov     rdi, rax
0x18001eb81  test    rax, rax
0x18001eb84  jz      loc_18001EC84
0x18001eb8a  lea     rcx, aExtraclock2; "ExtraClock2"
0x18001eb91  call    cs:__imp_StrToID
0x18001eb97  movzx   edx, ax
0x18001eb9a  mov     rcx, rbx
0x18001eb9d  call    cs:__imp_?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z; DirectUI::Element::FindDescendent(ushort)
0x18001eba3  mov     rsi, rax
0x18001eba6  test    rax, rax
0x18001eba9  jz      loc_18001EC84
0x18001ebaf  mov     ecx, [rbx+100h]
0x18001ebb5  neg     ecx
0x18001ebb7  mov     rcx, rdi
0x18001ebba  sbb     edx, edx
0x18001ebbc  and     edx, 4
0x18001ebbf  add     edx, 0FFFFFFFDh
0x18001ebc2  call    cs:__imp_?SetLayoutPos@Element@DirectUI@@QEAAJH@Z; DirectUI::Element::SetLayoutPos(int)
0x18001ebc8  mov     ecx, [rbx+104h]
0x18001ebce  neg     ecx
0x18001ebd0  mov     rcx, rsi
0x18001ebd3  sbb     edx, edx
0x18001ebd5  and     edx, 4
0x18001ebd8  add     edx, 0FFFFFFFDh
0x18001ebdb  call    cs:__imp_?SetLayoutPos@Element@DirectUI@@QEAAJH@Z; DirectUI::Element::SetLayoutPos(int)
0x18001ebe1  cmp     dword ptr [rbx+100h], 0
0x18001ebe8  jz      short loc_18001EC0A
0x18001ebea  mov     edx, r14d; unsigned int
0x18001ebed  mov     rcx, rbx; this
0x18001ebf0  call    ?_SetClockName@CTimeDate@@IEAAXI@Z; CTimeDate::_SetClockName(uint)
0x18001ebf5  xor     r8d, r8d; struct DirectUI::Element *
0x18001ebf8  mov     edx, r14d; unsigned int
0x18001ebfb  mov     rcx, rbx; this
0x18001ebfe  call    ?_GetExtraTzTime@CTooltip@@AEAAPEAVElement@DirectUI@@IPEAV23@@Z; CTooltip::_GetExtraTzTime(uint,DirectUI::Element *)
0x18001ec03  mov     [rbx+110h], rax
0x18001ec0a  cmp     dword ptr [rbx+104h], 0
0x18001ec11  mov     edi, 2
0x18001ec16  jz      short loc_18001EC36
0x18001ec18  mov     edx, edi; unsigned int
0x18001ec1a  mov     rcx, rbx; this
0x18001ec1d  call    ?_SetClockName@CTimeDate@@IEAAXI@Z; CTimeDate::_SetClockName(uint)
0x18001ec22  xor     r8d, r8d; struct DirectUI::Element *
0x18001ec25  mov     edx, edi; unsigned int
0x18001ec27  mov     rcx, rbx; this
0x18001ec2a  call    ?_GetExtraTzTime@CTooltip@@AEAAPEAVElement@DirectUI@@IPEAV23@@Z; CTooltip::_GetExtraTzTime(uint,DirectUI::Element *)
0x18001ec2f  mov     [rbx+118h], rax
0x18001ec36  mov     ecx, r14d; unsigned int
0x18001ec39  call    ?InitialiseClockSync@@YAHI@Z; InitialiseClockSync(uint)
0x18001ec3e  test    eax, eax
0x18001ec40  jnz     short loc_18001EC49
0x18001ec42  mov     eax, 8007000Eh
0x18001ec47  jmp     short loc_18001EC89
0x18001ec49  mov     rax, [rbx]
0x18001ec4c  mov     rcx, rbx
0x18001ec4f  mov     rax, [rax+168h]
0x18001ec56  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ec5b  mov     rcx, rax; hwnd
0x18001ec5e  mov     edx, edi; gaFlags
0x18001ec60  call    cs:__imp_GetAncestor
0x18001ec66  xor     r8d, r8d; unsigned int
0x18001ec69  lea     rcx, ?NotifyTimeChange@@YAXPEBU_SYSTEMTIME@@QEAUHWND__@@PEAX@Z; void (*)(const struct _SYSTEMTIME *, HWND, void *)
0x18001ec70  mov     r9, rax; HWND
0x18001ec73  mov     edx, r14d; int
0x18001ec76  call    ?RegisterClockSyncProc@@YAHQ6AXPEBU_SYSTEMTIME@@QEAUHWND__@@PEAX@ZHI12@Z; RegisterClockSyncProc(void (*const)(_SYSTEMTIME const *,HWND__ * const,void *),int,uint,HWND__ * const,void *)
0x18001ec7b  cmp     eax, 0FFFFFFFFh
0x18001ec7e  jz      short loc_18001EC84
0x18001ec80  xor     eax, eax
0x18001ec82  jmp     short loc_18001EC89
0x18001ec84  mov     eax, 80004005h
0x18001ec89  add     rsp, 38h
0x18001ec8d  pop     r14
0x18001ec8f  pop     rdi
0x18001ec90  pop     rsi
0x18001ec91  pop     rbx
0x18001ec92  retn
```
