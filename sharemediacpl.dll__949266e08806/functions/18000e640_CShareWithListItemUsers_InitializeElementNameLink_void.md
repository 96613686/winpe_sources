# CShareWithListItemUsers::_InitializeElementNameLink(void)

- ea: `0x18000e640`
- end: `0x18000e758`
- name: `?_InitializeElementNameLink@CShareWithListItemUsers@@EEAAJXZ`
- size: `280`
- prototype: `__int64 __fastcall(CShareWithListItemUsers *__hidden this)`
- caller_count: `0`
- callee_count: `5`
- tags: ``

## callees

- `0x180001d60`
- `0x18000291e`
- `0x180003860`
- `0x180003888`
- `0x18000e640`

## import_xrefs

- `USER32!LoadStringW` at `0x18000e6d9`
- `USER32!LoadStringW` at `0x18000e6d9`
- `DUI70!?SetAccName@Element@DirectUI@@QEAAJPEBG@Z` at `0x18000e6f5`
- `DUI70!?SetAccName@Element@DirectUI@@QEAAJPEBG@Z` at `0x18000e703`
- `DUI70!?SetAccName@Element@DirectUI@@QEAAJPEBG@Z` at `0x18000e6f5`
- `DUI70!?SetAccName@Element@DirectUI@@QEAAJPEBG@Z` at `0x18000e703`
- `DUI70!?SetContentString@Element@DirectUI@@QEAAJPEBG@Z` at `0x18000e6e7`
- `DUI70!?SetContentString@Element@DirectUI@@QEAAJPEBG@Z` at `0x18000e6e7`
- `DUI70!StrToID` at `0x18000e696`
- `DUI70!StrToID` at `0x18000e696`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x18000e6a2`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x18000e6a2`

## string_xrefs

- `0x18000e68f`: `ShareItemLink`

## pseudocode

```c
__int64 __fastcall CShareWithListItemUsers::_InitializeElementNameLink(CShareWithListItemUsers *this)
{
  unsigned __int16 v2; // ax
  DirectUI::Element *Descendent; // rdi
  unsigned int v4; // ebx
  WCHAR Buffer[504]; // [rsp+20h] [rbp-428h] BYREF

  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 227, &WPP_59386dd0a0913b67da6dc13cee28e88f_Traceguids);
  v2 = StrToID(L"ShareItemLink");
  Descendent = DirectUI::Element::FindDescendent(this, v2);
  if ( Descendent )
  {
    v4 = 0;
    memset_0(Buffer, 0, 0x3E8u);
    LoadStringW(g_hinst, 0x1Fu, Buffer, 500);
    DirectUI::Element::SetContentString(Descendent, Buffer);
    DirectUI::Element::SetAccName(Descendent, Buffer);
    DirectUI::Element::SetAccName(this, Buffer);
  }
  else
  {
    v4 = -2147467259;
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 228, &WPP_59386dd0a0913b67da6dc13cee28e88f_Traceguids, v4);
  return v4;
}

```

## disassembly

```asm
0x18000e640  push    rbx
0x18000e642  push    rbp
0x18000e643  push    rsi
0x18000e644  push    rdi
0x18000e645  sub     rsp, 428h
0x18000e64c  mov     rax, cs:__security_cookie
0x18000e653  xor     rax, rsp
0x18000e656  mov     [rsp+448h+var_38], rax
0x18000e65e  mov     rsi, rcx
0x18000e661  mov     rcx, cs:WPP_GLOBAL_Control
0x18000e668  lea     rbp, WPP_GLOBAL_Control
0x18000e66f  cmp     rcx, rbp
0x18000e672  jz      short loc_18000E68F
0x18000e674  test    byte ptr [rcx+1Ch], 20h
0x18000e678  jz      short loc_18000E68F
0x18000e67a  mov     rcx, [rcx+10h]
0x18000e67e  lea     r8, WPP_59386dd0a0913b67da6dc13cee28e88f_Traceguids
0x18000e685  mov     edx, 0E3h
0x18000e68a  call    WPP_SF_
0x18000e68f  lea     rcx, aShareitemlink; "ShareItemLink"
0x18000e696  call    cs:__imp_StrToID
0x18000e69c  movzx   edx, ax
0x18000e69f  mov     rcx, rsi
0x18000e6a2  call    cs:__imp_?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z; DirectUI::Element::FindDescendent(ushort)
0x18000e6a8  mov     rdi, rax
0x18000e6ab  test    rax, rax
0x18000e6ae  jz      short loc_18000E70B
0x18000e6b0  xor     edx, edx; Val
0x18000e6b2  lea     rcx, [rsp+448h+Buffer]; void *
0x18000e6b7  mov     r8d, 3E8h; Size
0x18000e6bd  xor     ebx, ebx
0x18000e6bf  call    memset_0
0x18000e6c4  mov     rcx, cs:g_hinst; hInstance
0x18000e6cb  lea     r8, [rsp+448h+Buffer]; lpBuffer
0x18000e6d0  mov     r9d, 1F4h; cchBufferMax
0x18000e6d6  lea     edx, [rbx+1Fh]; uID
0x18000e6d9  call    cs:__imp_LoadStringW
0x18000e6df  lea     rdx, [rsp+448h+Buffer]
0x18000e6e4  mov     rcx, rdi
0x18000e6e7  call    cs:__imp_?SetContentString@Element@DirectUI@@QEAAJPEBG@Z; DirectUI::Element::SetContentString(ushort const *)
0x18000e6ed  lea     rdx, [rsp+448h+Buffer]
0x18000e6f2  mov     rcx, rdi
0x18000e6f5  call    cs:__imp_?SetAccName@Element@DirectUI@@QEAAJPEBG@Z; DirectUI::Element::SetAccName(ushort const *)
0x18000e6fb  lea     rdx, [rsp+448h+Buffer]
0x18000e700  mov     rcx, rsi
0x18000e703  call    cs:__imp_?SetAccName@Element@DirectUI@@QEAAJPEBG@Z; DirectUI::Element::SetAccName(ushort const *)
0x18000e709  jmp     short loc_18000E710
0x18000e70b  mov     ebx, 80004005h
0x18000e710  mov     rcx, cs:WPP_GLOBAL_Control
0x18000e717  cmp     rcx, rbp
0x18000e71a  jz      short loc_18000E73A
0x18000e71c  test    byte ptr [rcx+1Ch], 20h
0x18000e720  jz      short loc_18000E73A
0x18000e722  mov     rcx, [rcx+10h]
0x18000e726  lea     r8, WPP_59386dd0a0913b67da6dc13cee28e88f_Traceguids
0x18000e72d  mov     edx, 0E4h
0x18000e732  mov     r9d, ebx
0x18000e735  call    WPP_SF_d
0x18000e73a  mov     eax, ebx
0x18000e73c  mov     rcx, [rsp+448h+var_38]
0x18000e744  xor     rcx, rsp; StackCookie
0x18000e747  call    __security_check_cookie
0x18000e74c  add     rsp, 428h
0x18000e753  pop     rdi
0x18000e754  pop     rsi
0x18000e755  pop     rbp
0x18000e756  pop     rbx
0x18000e757  retn
```
