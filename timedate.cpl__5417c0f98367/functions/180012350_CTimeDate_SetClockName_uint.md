# CTimeDate::_SetClockName(uint)

- ea: `0x180012350`
- end: `0x18001241f`
- name: `?_SetClockName@CTimeDate@@IEAAXI@Z`
- size: `207`
- prototype: `void __fastcall(CTimeDate *__hidden this, unsigned int)`
- caller_count: `2`
- callee_count: `4`
- tags: `authz_impersonation`

## callers

- `0x1800124c8`
- `0x18001ead0`

## callees

- `0x1800089c8`
- `0x18000f138`
- `0x180012350`
- `0x180028f60`

## import_xrefs

- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x180012392`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x180012392`
- `DUI70!StrToID` at `0x180012386`
- `DUI70!StrToID` at `0x180012386`
- `DUI70!?SetContentString@Element@DirectUI@@QEAAJPEBG@Z` at `0x1800123fc`
- `DUI70!?SetContentString@Element@DirectUI@@QEAAJPEBG@Z` at `0x1800123fc`

## string_xrefs

- `0x180012371`: `ExtraClockName1`
- `0x18001237f`: `ExtraClockName2`

## pseudocode

```c
void __fastcall CTimeDate::_SetClockName(CTimeDate *this, int a2)
{
  const unsigned __int16 *v3; // rcx
  unsigned __int16 v5; // ax
  DirectUI::Element *Descendent; // rdi
  unsigned int v7; // r8d
  int v8; // r11d
  unsigned __int16 v9[8]; // [rsp+20h] [rbp-38h] BYREF
  __int128 v10; // [rsp+30h] [rbp-28h]

  v3 = L"ExtraClockName1";
  if ( a2 != 1 )
    v3 = L"ExtraClockName2";
  v5 = StrToID(v3);
  Descendent = DirectUI::Element::FindDescendent(this, v5);
  if ( Descendent )
  {
    *(_OWORD *)v9 = 0;
    v10 = 0;
    if ( (unsigned int)(a2 - 1) <= 1 )
    {
      if ( GetExtraTzDisplayName((a2 == 2) + 1, v9, v7) && v9[0] || (StringCchCopyW(v9, 0x10u, L" "), v8) )
        DirectUI::Element::SetContentString(Descendent, v9);
    }
  }
}

```

## disassembly

```asm
0x180012350  mov     [rsp+arg_8], rbx
0x180012355  mov     [rsp+arg_10], rsi
0x18001235a  push    rdi
0x18001235b  sub     rsp, 50h
0x18001235f  mov     rax, cs:__security_cookie
0x180012366  xor     rax, rsp
0x180012369  mov     [rsp+58h+var_18], rax
0x18001236e  mov     rdi, rcx
0x180012371  lea     rcx, aExtraclockname; "ExtraClockName1"
0x180012378  mov     ebx, edx
0x18001237a  cmp     edx, 1
0x18001237d  jz      short loc_180012386
0x18001237f  lea     rcx, aExtraclockname_0; "ExtraClockName2"
0x180012386  call    cs:__imp_StrToID
0x18001238c  movzx   edx, ax
0x18001238f  mov     rcx, rdi
0x180012392  call    cs:__imp_?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z; DirectUI::Element::FindDescendent(ushort)
0x180012398  xor     esi, esi
0x18001239a  mov     rdi, rax
0x18001239d  test    rax, rax
0x1800123a0  jz      short loc_180012402
0x1800123a2  xorps   xmm0, xmm0
0x1800123a5  lea     ecx, [rbx-1]
0x1800123a8  movups  xmmword ptr [rsp+58h+var_38], xmm0
0x1800123ad  movups  [rsp+58h+var_28], xmm0
0x1800123b2  cmp     ecx, 1
0x1800123b5  ja      short loc_180012402
0x1800123b7  mov     ecx, esi
0x1800123b9  lea     rdx, [rsp+58h+var_38]; unsigned __int16 *
0x1800123be  cmp     ebx, 2
0x1800123c1  setz    cl
0x1800123c4  inc     ecx; unsigned int
0x1800123c6  call    ?GetExtraTzDisplayName@@YAHIPEAGI@Z; GetExtraTzDisplayName(uint,ushort *,uint)
0x1800123cb  mov     r11d, eax
0x1800123ce  test    eax, eax
0x1800123d0  jz      short loc_1800123D9
0x1800123d2  cmp     [rsp+58h+var_38], si
0x1800123d7  jnz     short loc_1800123F4
0x1800123d9  lea     r8, asc_18002F1D4; " "
0x1800123e0  mov     edx, 10h; unsigned __int64
0x1800123e5  lea     rcx, [rsp+58h+var_38]; unsigned __int16 *
0x1800123ea  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800123ef  test    r11d, r11d
0x1800123f2  jz      short loc_180012402
0x1800123f4  lea     rdx, [rsp+58h+var_38]
0x1800123f9  mov     rcx, rdi
0x1800123fc  call    cs:__imp_?SetContentString@Element@DirectUI@@QEAAJPEBG@Z; DirectUI::Element::SetContentString(ushort const *)
0x180012402  mov     rcx, [rsp+58h+var_18]
0x180012407  xor     rcx, rsp; StackCookie
0x18001240a  call    __security_check_cookie
0x18001240f  mov     rbx, [rsp+58h+arg_8]
0x180012414  mov     rsi, [rsp+58h+arg_10]
0x180012419  add     rsp, 50h
0x18001241d  pop     rdi
0x18001241e  retn
```
