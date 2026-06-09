# CTooltip::_GetExtraTzTime(uint,DirectUI::Element *)

- ea: `0x18001eea8`
- end: `0x18001f010`
- name: `?_GetExtraTzTime@CTooltip@@AEAAPEAVElement@DirectUI@@IPEAV23@@Z`
- size: `360`
- prototype: `struct DirectUI::Element *__fastcall(CTooltip *__hidden this, unsigned int, struct DirectUI::Element *)`
- caller_count: `2`
- callee_count: `5`
- tags: `authz_impersonation`

## callers

- `0x18001e920`
- `0x18001ead0`

## callees

- `0x18000f1c8`
- `0x18001eea8`
- `0x18001f018`
- `0x180028f2e`
- `0x180028f60`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTime` at `0x18001ef35`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTime` at `0x18001ef35`
- `api-ms-win-core-datetime-l1-1-0!GetTimeFormatW` at `0x18001ef7f`
- `api-ms-win-core-datetime-l1-1-0!GetTimeFormatW` at `0x18001ef7f`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x18001eefc`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x18001efb6`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x18001eefc`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x18001efb6`
- `DUI70!StrToID` at `0x18001eef0`
- `DUI70!StrToID` at `0x18001efaa`
- `DUI70!StrToID` at `0x18001eef0`
- `DUI70!StrToID` at `0x18001efaa`
- `DUI70!?SetContentString@Element@DirectUI@@QEAAJPEBG@Z` at `0x18001ef91`
- `DUI70!?SetContentString@Element@DirectUI@@QEAAJPEBG@Z` at `0x18001efe5`
- `DUI70!?SetContentString@Element@DirectUI@@QEAAJPEBG@Z` at `0x18001ef91`
- `DUI70!?SetContentString@Element@DirectUI@@QEAAJPEBG@Z` at `0x18001efe5`

## string_xrefs

- `0x18001ef97`: `ExtraClockDay1`
- `0x18001efa3`: `ExtraClockDay2`

## pseudocode

```c
struct DirectUI::Element *__fastcall CTooltip::_GetExtraTzTime(CTooltip *this, int a2, struct DirectUI::Element *a3)
{
  DirectUI::Element *Descendent; // rbx
  const unsigned __int16 *v6; // rcx
  unsigned __int16 v7; // ax
  const unsigned __int16 *v8; // rcx
  unsigned __int16 v9; // ax
  CTooltip *v10; // rcx
  DirectUI::Element *v11; // rdi
  unsigned int lpTimeStr; // [rsp+20h] [rbp-E0h]
  SYSTEMTIME Time; // [rsp+30h] [rbp-D0h] BYREF
  struct _SYSTEMTIME SystemTime; // [rsp+40h] [rbp-C0h] BYREF
  WCHAR TimeStr[256]; // [rsp+50h] [rbp-B0h] BYREF

  Descendent = a3;
  if ( !a3 )
  {
    v6 = L"FirstClock";
    if ( a2 != 1 )
      v6 = L"SecondClock";
    v7 = StrToID(v6);
    Descendent = DirectUI::Element::FindDescendent(this, v7);
  }
  if ( Descendent )
  {
    memset_0(TimeStr, 0, sizeof(TimeStr));
    SystemTime = 0;
    Time = 0;
    GetSystemTime(&SystemTime);
    if ( GetExtraTzLocalTime((a2 == 2) + 1, &SystemTime, &Time) )
    {
      if ( GetTimeFormatW(0x400u, 2u, &Time, 0, TimeStr, 256) )
      {
        DirectUI::Element::SetContentString(Descendent, TimeStr);
        v8 = L"ExtraClockDay1";
        if ( a2 != 1 )
          v8 = L"ExtraClockDay2";
        v9 = StrToID(v8);
        v11 = DirectUI::Element::FindDescendent(this, v9);
        if ( v11 && CTooltip::_GetTodaysDayName(v10, &Time, 0xEu, TimeStr, lpTimeStr) )
          DirectUI::Element::SetContentString(v11, TimeStr);
      }
    }
  }
  return Descendent;
}

```

## disassembly

```asm
0x18001eea8  mov     [rsp-8+arg_8], rbx
0x18001eead  push    rbp
0x18001eeae  push    rsi
0x18001eeaf  push    rdi
0x18001eeb0  lea     rbp, [rsp-160h]
0x18001eeb8  sub     rsp, 260h
0x18001eebf  mov     rax, cs:__security_cookie
0x18001eec6  xor     rax, rsp
0x18001eec9  mov     [rbp+170h+var_20], rax
0x18001eed0  mov     rbx, r8
0x18001eed3  mov     edi, edx
0x18001eed5  mov     rsi, rcx
0x18001eed8  test    r8, r8
0x18001eedb  jnz     short loc_18001EF05
0x18001eedd  lea     rcx, aFirstclock; "FirstClock"
0x18001eee4  cmp     edx, 1
0x18001eee7  jz      short loc_18001EEF0
0x18001eee9  lea     rcx, aSecondclock; "SecondClock"
0x18001eef0  call    cs:__imp_StrToID
0x18001eef6  movzx   edx, ax
0x18001eef9  mov     rcx, rsi
0x18001eefc  call    cs:__imp_?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z; DirectUI::Element::FindDescendent(ushort)
0x18001ef02  mov     rbx, rax
0x18001ef05  test    rbx, rbx
0x18001ef08  jz      loc_18001EFEB
0x18001ef0e  xor     edx, edx; Val
0x18001ef10  lea     rcx, [rsp+270h+TimeStr]; void *
0x18001ef15  mov     r8d, 200h; Size
0x18001ef1b  call    memset_0
0x18001ef20  xorps   xmm0, xmm0
0x18001ef23  lea     rcx, [rsp+270h+SystemTime]; lpSystemTime
0x18001ef28  xorps   xmm1, xmm1
0x18001ef2b  movups  xmmword ptr [rsp+270h+SystemTime.wYear], xmm0
0x18001ef30  movups  xmmword ptr [rsp+270h+Time.wYear], xmm1
0x18001ef35  call    cs:__imp_GetSystemTime
0x18001ef3b  xor     ecx, ecx
0x18001ef3d  lea     r8, [rsp+270h+Time]; struct _SYSTEMTIME *
0x18001ef42  cmp     edi, 2
0x18001ef45  lea     rdx, [rsp+270h+SystemTime]; struct _SYSTEMTIME *
0x18001ef4a  setz    cl
0x18001ef4d  inc     ecx; unsigned int
0x18001ef4f  call    ?GetExtraTzLocalTime@@YAHIPEBU_SYSTEMTIME@@PEAU1@@Z; GetExtraTzLocalTime(uint,_SYSTEMTIME const *,_SYSTEMTIME *)
0x18001ef54  test    eax, eax
0x18001ef56  jz      loc_18001EFEB
0x18001ef5c  xor     r9d, r9d; lpFormat
0x18001ef5f  mov     [rsp+270h+cchTime], 100h; cchTime
0x18001ef67  lea     rax, [rsp+270h+TimeStr]
0x18001ef6c  mov     ecx, 400h; Locale
0x18001ef71  lea     r8, [rsp+270h+Time]; lpTime
0x18001ef76  mov     [rsp+270h+lpTimeStr], rax; unsigned int
0x18001ef7b  lea     edx, [r9+2]; dwFlags
0x18001ef7f  call    cs:__imp_GetTimeFormatW
0x18001ef85  test    eax, eax
0x18001ef87  jz      short loc_18001EFEB
0x18001ef89  lea     rdx, [rsp+270h+TimeStr]
0x18001ef8e  mov     rcx, rbx
0x18001ef91  call    cs:__imp_?SetContentString@Element@DirectUI@@QEAAJPEBG@Z; DirectUI::Element::SetContentString(ushort const *)
0x18001ef97  lea     rcx, aExtraclockday1; "ExtraClockDay1"
0x18001ef9e  cmp     edi, 1
0x18001efa1  jz      short loc_18001EFAA
0x18001efa3  lea     rcx, aExtraclockday2; "ExtraClockDay2"
0x18001efaa  call    cs:__imp_StrToID
0x18001efb0  movzx   edx, ax
0x18001efb3  mov     rcx, rsi
0x18001efb6  call    cs:__imp_?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z; DirectUI::Element::FindDescendent(ushort)
0x18001efbc  mov     rdi, rax
0x18001efbf  test    rax, rax
0x18001efc2  jz      short loc_18001EFEB
0x18001efc4  lea     r9, [rsp+270h+TimeStr]; unsigned __int16 *
0x18001efc9  mov     r8d, 0Eh; unsigned int
0x18001efcf  lea     rdx, [rsp+270h+Time]; struct _SYSTEMTIME *
0x18001efd4  call    ?_GetTodaysDayName@CTooltip@@AEAAHQEAU_SYSTEMTIME@@KPEAGK@Z; CTooltip::_GetTodaysDayName(_SYSTEMTIME * const,ulong,ushort *,ulong)
0x18001efd9  test    eax, eax
0x18001efdb  jz      short loc_18001EFEB
0x18001efdd  lea     rdx, [rsp+270h+TimeStr]
0x18001efe2  mov     rcx, rdi
0x18001efe5  call    cs:__imp_?SetContentString@Element@DirectUI@@QEAAJPEBG@Z; DirectUI::Element::SetContentString(ushort const *)
0x18001efeb  mov     rax, rbx
0x18001efee  mov     rcx, [rbp+170h+var_20]
0x18001eff5  xor     rcx, rsp; StackCookie
0x18001eff8  call    __security_check_cookie
0x18001effd  mov     rbx, [rsp+270h+arg_8]
0x18001f005  add     rsp, 260h
0x18001f00c  pop     rdi
0x18001f00d  pop     rsi
0x18001f00e  pop     rbp
0x18001f00f  retn
```
