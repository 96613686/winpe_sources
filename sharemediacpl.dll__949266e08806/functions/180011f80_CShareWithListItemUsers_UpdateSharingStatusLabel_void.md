# CShareWithListItemUsers::_UpdateSharingStatusLabel(void)

- ea: `0x180011f80`
- end: `0x1800120e3`
- name: `?_UpdateSharingStatusLabel@CShareWithListItemUsers@@EEAAJXZ`
- size: `355`
- prototype: `__int64 __fastcall(CShareWithListItemUsers *__hidden this)`
- caller_count: `0`
- callee_count: `7`
- tags: `authz_impersonation, registry_config, installer_update`

## callees

- `0x180001d60`
- `0x18000291e`
- `0x180003860`
- `0x180003888`
- `0x180004358`
- `0x1800071f8`
- `0x180011f80`

## import_xrefs

- `USER32!LoadStringW` at `0x18001206d`
- `USER32!LoadStringW` at `0x18001206d`
- `DUI70!?SetAccName@Element@DirectUI@@QEAAJPEBG@Z` at `0x180012089`
- `DUI70!?SetAccName@Element@DirectUI@@QEAAJPEBG@Z` at `0x180012089`
- `DUI70!?SetContentString@Element@DirectUI@@QEAAJPEBG@Z` at `0x18001207b`
- `DUI70!?SetContentString@Element@DirectUI@@QEAAJPEBG@Z` at `0x18001207b`
- `DUI70!StrToID` at `0x180011fdf`
- `DUI70!StrToID` at `0x180011fdf`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x180011feb`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x180011feb`

## string_xrefs

- `0x180011fd8`: `ShareAccessLabel`

## pseudocode

```c
__int64 __fastcall CShareWithListItemUsers::_UpdateSharingStatusLabel(CDeviceSettings **this)
{
  unsigned __int16 v2; // ax
  DirectUI::Element *Descendent; // rbp
  int AuthorizationStatus; // ebx
  CDeviceSettings *v5; // rcx
  UINT v6; // edi
  _DWORD v8[4]; // [rsp+20h] [rbp-168h] BYREF
  WCHAR Buffer[152]; // [rsp+30h] [rbp-158h] BYREF

  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 233, &WPP_59386dd0a0913b67da6dc13cee28e88f_Traceguids);
  v2 = StrToID(L"ShareAccessLabel");
  Descendent = DirectUI::Element::FindDescendent((DirectUI::Element *)this, v2);
  if ( Descendent )
  {
    v5 = this[27];
    v8[0] = 0;
    AuthorizationStatus = CDeviceSettings::GetAuthorizationStatus(v5, (enum AuthorizationStatus *)v8);
    if ( AuthorizationStatus >= 0 )
    {
      v6 = 16;
      if ( v8[0] == 2 )
      {
        v6 = 15;
        if ( !(unsigned int)CDeviceSettings::UseDefaultSettings(this[27]) )
          v6 = 73;
      }
      memset_0(Buffer, 0, 0x12Cu);
      LoadStringW(g_hinst, v6, Buffer, 150);
      DirectUI::Element::SetContentString(Descendent, Buffer);
      DirectUI::Element::SetAccName(Descendent, Buffer);
    }
  }
  else
  {
    AuthorizationStatus = -2147467259;
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      234,
      &WPP_59386dd0a0913b67da6dc13cee28e88f_Traceguids,
      (unsigned int)AuthorizationStatus);
  return (unsigned int)AuthorizationStatus;
}

```

## disassembly

```asm
0x180011f80  mov     [rsp+arg_8], rbx
0x180011f85  mov     [rsp+arg_10], rbp
0x180011f8a  push    rsi
0x180011f8b  push    rdi
0x180011f8c  push    r14
0x180011f8e  sub     rsp, 170h
0x180011f95  mov     rax, cs:__security_cookie
0x180011f9c  xor     rax, rsp
0x180011f9f  mov     [rsp+188h+var_28], rax
0x180011fa7  mov     rsi, rcx
0x180011faa  mov     rcx, cs:WPP_GLOBAL_Control
0x180011fb1  lea     r14, WPP_GLOBAL_Control
0x180011fb8  cmp     rcx, r14
0x180011fbb  jz      short loc_180011FD8
0x180011fbd  test    byte ptr [rcx+1Ch], 20h
0x180011fc1  jz      short loc_180011FD8
0x180011fc3  mov     rcx, [rcx+10h]
0x180011fc7  lea     r8, WPP_59386dd0a0913b67da6dc13cee28e88f_Traceguids
0x180011fce  mov     edx, 0E9h
0x180011fd3  call    WPP_SF_
0x180011fd8  lea     rcx, aShareaccesslab; "ShareAccessLabel"
0x180011fdf  call    cs:__imp_StrToID
0x180011fe5  movzx   edx, ax
0x180011fe8  mov     rcx, rsi
0x180011feb  call    cs:__imp_?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z; DirectUI::Element::FindDescendent(ushort)
0x180011ff1  mov     rbp, rax
0x180011ff4  test    rax, rax
0x180011ff7  jnz     short loc_180012003
0x180011ff9  mov     ebx, 80004005h
0x180011ffe  jmp     loc_18001208F
0x180012003  mov     rcx, [rsi+0D8h]; this
0x18001200a  lea     rdx, [rsp+188h+var_168]; enum AuthorizationStatus *
0x18001200f  mov     [rsp+188h+var_168], 0
0x180012017  call    ?GetAuthorizationStatus@CDeviceSettings@@QEAAJPEAW4AuthorizationStatus@@@Z; CDeviceSettings::GetAuthorizationStatus(AuthorizationStatus *)
0x18001201c  mov     ebx, eax
0x18001201e  test    eax, eax
0x180012020  js      short loc_18001208F
0x180012022  cmp     [rsp+188h+var_168], 2
0x180012027  mov     edi, 10h
0x18001202c  jnz     short loc_180012047
0x18001202e  mov     rcx, [rsi+0D8h]; this
0x180012035  mov     edi, 0Fh
0x18001203a  call    ?UseDefaultSettings@CDeviceSettings@@QEAAHXZ; CDeviceSettings::UseDefaultSettings(void)
0x18001203f  test    eax, eax
0x180012041  lea     ecx, [rdi+3Ah]
0x180012044  cmovz   edi, ecx
0x180012047  xor     edx, edx; Val
0x180012049  lea     rcx, [rsp+188h+Buffer]; void *
0x18001204e  mov     r8d, 12Ch; Size
0x180012054  call    memset_0
0x180012059  mov     rcx, cs:g_hinst; hInstance
0x180012060  lea     r8, [rsp+188h+Buffer]; lpBuffer
0x180012065  mov     r9d, 96h; cchBufferMax
0x18001206b  mov     edx, edi; uID
0x18001206d  call    cs:__imp_LoadStringW
0x180012073  lea     rdx, [rsp+188h+Buffer]
0x180012078  mov     rcx, rbp
0x18001207b  call    cs:__imp_?SetContentString@Element@DirectUI@@QEAAJPEBG@Z; DirectUI::Element::SetContentString(ushort const *)
0x180012081  lea     rdx, [rsp+188h+Buffer]
0x180012086  mov     rcx, rbp
0x180012089  call    cs:__imp_?SetAccName@Element@DirectUI@@QEAAJPEBG@Z; DirectUI::Element::SetAccName(ushort const *)
0x18001208f  mov     rcx, cs:WPP_GLOBAL_Control
0x180012096  cmp     rcx, r14
0x180012099  jz      short loc_1800120B9
0x18001209b  test    byte ptr [rcx+1Ch], 20h
0x18001209f  jz      short loc_1800120B9
0x1800120a1  mov     rcx, [rcx+10h]
0x1800120a5  lea     r8, WPP_59386dd0a0913b67da6dc13cee28e88f_Traceguids
0x1800120ac  mov     edx, 0EAh
0x1800120b1  mov     r9d, ebx
0x1800120b4  call    WPP_SF_d
0x1800120b9  mov     eax, ebx
0x1800120bb  mov     rcx, [rsp+188h+var_28]
0x1800120c3  xor     rcx, rsp; StackCookie
0x1800120c6  call    __security_check_cookie
0x1800120cb  lea     r11, [rsp+188h+var_18]
0x1800120d3  mov     rbx, [r11+28h]
0x1800120d7  mov     rbp, [r11+30h]
0x1800120db  mov     rsp, r11
0x1800120de  pop     r14
0x1800120e0  pop     rdi
0x1800120e1  pop     rsi
0x1800120e2  retn
```
