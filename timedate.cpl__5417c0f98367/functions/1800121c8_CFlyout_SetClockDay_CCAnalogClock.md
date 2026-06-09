# CFlyout::_SetClockDay(CCAnalogClock *)

- ea: `0x1800121c8`
- end: `0x18001228a`
- name: `?_SetClockDay@CFlyout@@AEAAHPEAVCCAnalogClock@@@Z`
- size: `194`
- prototype: `__int64 __fastcall(CFlyout *__hidden this, struct CCAnalogClock *)`
- caller_count: `2`
- callee_count: `4`
- tags: `authz_impersonation`

## callers

- `0x180011020`
- `0x1800124c8`

## callees

- `0x1800121c8`
- `0x180012dc4`
- `0x180028f2e`
- `0x180028f60`

## import_xrefs

- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x180012224`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x180012224`
- `DUI70!StrToID` at `0x180012201`
- `DUI70!StrToID` at `0x180012213`
- `DUI70!StrToID` at `0x180012201`
- `DUI70!StrToID` at `0x180012213`
- `DUI70!?SetContentString@Element@DirectUI@@QEAAJPEBG@Z` at `0x180012258`
- `DUI70!?SetContentString@Element@DirectUI@@QEAAJPEBG@Z` at `0x180012258`

## string_xrefs

- `0x1800121fa`: `ExtraClockDay1`
- `0x18001220c`: `ExtraClockDay2`

## pseudocode

```c
__int64 __fastcall CFlyout::_SetClockDay(struct CCAnalogClock **this, struct CCAnalogClock *a2)
{
  unsigned int v2; // ebx
  unsigned __int16 v4; // ax
  unsigned int v5; // esi
  DirectUI::Element *Descendent; // rdi
  unsigned int v7; // r8d
  unsigned __int16 v9[256]; // [rsp+20h] [rbp-218h] BYREF

  v2 = 0;
  if ( a2 == this[42] )
  {
    v4 = StrToID(L"ExtraClockDay1");
    v5 = 1;
  }
  else
  {
    v4 = StrToID(L"ExtraClockDay2");
    v5 = 2;
  }
  Descendent = DirectUI::Element::FindDescendent((DirectUI::Element *)this, v4);
  if ( Descendent )
  {
    memset_0(v9, 0, sizeof(v9));
    GetClockDay(v5, v9, v7);
    DirectUI::Element::SetContentString(Descendent, v9);
    return 1;
  }
  return v2;
}

```

## disassembly

```asm
0x1800121c8  mov     [rsp+arg_8], rbx
0x1800121cd  mov     [rsp+arg_10], rsi
0x1800121d2  push    rdi
0x1800121d3  sub     rsp, 230h
0x1800121da  mov     rax, cs:__security_cookie
0x1800121e1  xor     rax, rsp
0x1800121e4  mov     [rsp+238h+var_18], rax
0x1800121ec  xor     ebx, ebx
0x1800121ee  mov     rdi, rcx
0x1800121f1  cmp     rdx, [rcx+150h]
0x1800121f8  jnz     short loc_18001220C
0x1800121fa  lea     rcx, aExtraclockday1; "ExtraClockDay1"
0x180012201  call    cs:__imp_StrToID
0x180012207  lea     esi, [rbx+1]
0x18001220a  jmp     short loc_18001221E
0x18001220c  lea     rcx, aExtraclockday2; "ExtraClockDay2"
0x180012213  call    cs:__imp_StrToID
0x180012219  mov     esi, 2
0x18001221e  movzx   edx, ax
0x180012221  mov     rcx, rdi
0x180012224  call    cs:__imp_?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z; DirectUI::Element::FindDescendent(ushort)
0x18001222a  mov     rdi, rax
0x18001222d  test    rax, rax
0x180012230  jz      short loc_180012263
0x180012232  xor     edx, edx; Val
0x180012234  lea     rcx, [rsp+238h+var_218]; void *
0x180012239  mov     r8d, 200h; Size
0x18001223f  call    memset_0
0x180012244  lea     rdx, [rsp+238h+var_218]; unsigned __int16 *
0x180012249  mov     ecx, esi; unsigned int
0x18001224b  call    ?GetClockDay@@YAHIPEAGK@Z; GetClockDay(uint,ushort *,ulong)
0x180012250  lea     rdx, [rsp+238h+var_218]
0x180012255  mov     rcx, rdi
0x180012258  call    cs:__imp_?SetContentString@Element@DirectUI@@QEAAJPEBG@Z; DirectUI::Element::SetContentString(ushort const *)
0x18001225e  mov     ebx, 1
0x180012263  mov     eax, ebx
0x180012265  mov     rcx, [rsp+238h+var_18]
0x18001226d  xor     rcx, rsp; StackCookie
0x180012270  call    __security_check_cookie
0x180012275  lea     r11, [rsp+238h+var_8]
0x18001227d  mov     rbx, [r11+18h]
0x180012281  mov     rsi, [r11+20h]
0x180012285  mov     rsp, r11
0x180012288  pop     rdi
0x180012289  retn
```
