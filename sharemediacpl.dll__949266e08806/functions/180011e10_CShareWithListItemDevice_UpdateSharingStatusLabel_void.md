# CShareWithListItemDevice::_UpdateSharingStatusLabel(void)

- ea: `0x180011e10`
- end: `0x180011f73`
- name: `?_UpdateSharingStatusLabel@CShareWithListItemDevice@@EEAAJXZ`
- size: `355`
- prototype: `__int64 __fastcall(CShareWithListItemDevice *__hidden this)`
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
- `0x180011e10`

## import_xrefs

- `USER32!LoadStringW` at `0x180011efd`
- `USER32!LoadStringW` at `0x180011efd`
- `DUI70!?SetAccName@Element@DirectUI@@QEAAJPEBG@Z` at `0x180011f19`
- `DUI70!?SetAccName@Element@DirectUI@@QEAAJPEBG@Z` at `0x180011f19`
- `DUI70!?SetContentString@Element@DirectUI@@QEAAJPEBG@Z` at `0x180011f0b`
- `DUI70!?SetContentString@Element@DirectUI@@QEAAJPEBG@Z` at `0x180011f0b`
- `DUI70!StrToID` at `0x180011e6f`
- `DUI70!StrToID` at `0x180011e6f`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x180011e7b`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x180011e7b`

## string_xrefs

- `0x180011e68`: `ShareAccessLabel`

## pseudocode

```c
__int64 __fastcall CShareWithListItemDevice::_UpdateSharingStatusLabel(CDeviceSettings **this)
{
  unsigned __int16 v2; // ax
  DirectUI::Element *Descendent; // rbp
  int AuthorizationStatus; // ebx
  CDeviceSettings *v5; // rcx
  UINT v6; // edi
  _DWORD v8[4]; // [rsp+20h] [rbp-168h] BYREF
  WCHAR Buffer[152]; // [rsp+30h] [rbp-158h] BYREF

  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 255, &WPP_59386dd0a0913b67da6dc13cee28e88f_Traceguids);
  v2 = StrToID(L"ShareAccessLabel");
  Descendent = DirectUI::Element::FindDescendent((DirectUI::Element *)this, v2);
  if ( Descendent )
  {
    v5 = this[27];
    v8[0] = 0;
    AuthorizationStatus = CDeviceSettings::GetAuthorizationStatus(v5, (enum AuthorizationStatus *)v8);
    if ( AuthorizationStatus >= 0 )
    {
      v6 = 13;
      if ( v8[0] == 2 )
      {
        v6 = 14;
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
      256,
      &WPP_59386dd0a0913b67da6dc13cee28e88f_Traceguids,
      (unsigned int)AuthorizationStatus);
  return (unsigned int)AuthorizationStatus;
}

```

## disassembly

```asm
0x180011e10  mov     [rsp+arg_8], rbx
0x180011e15  mov     [rsp+arg_10], rbp
0x180011e1a  push    rsi
0x180011e1b  push    rdi
0x180011e1c  push    r14
0x180011e1e  sub     rsp, 170h
0x180011e25  mov     rax, cs:__security_cookie
0x180011e2c  xor     rax, rsp
0x180011e2f  mov     [rsp+188h+var_28], rax
0x180011e37  mov     rsi, rcx
0x180011e3a  mov     rcx, cs:WPP_GLOBAL_Control
0x180011e41  lea     r14, WPP_GLOBAL_Control
0x180011e48  cmp     rcx, r14
0x180011e4b  jz      short loc_180011E68
0x180011e4d  test    byte ptr [rcx+1Ch], 20h
0x180011e51  jz      short loc_180011E68
0x180011e53  mov     rcx, [rcx+10h]
0x180011e57  lea     r8, WPP_59386dd0a0913b67da6dc13cee28e88f_Traceguids
0x180011e5e  mov     edx, 0FFh
0x180011e63  call    WPP_SF_
0x180011e68  lea     rcx, aShareaccesslab; "ShareAccessLabel"
0x180011e6f  call    cs:__imp_StrToID
0x180011e75  movzx   edx, ax
0x180011e78  mov     rcx, rsi
0x180011e7b  call    cs:__imp_?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z; DirectUI::Element::FindDescendent(ushort)
0x180011e81  mov     rbp, rax
0x180011e84  test    rax, rax
0x180011e87  jnz     short loc_180011E93
0x180011e89  mov     ebx, 80004005h
0x180011e8e  jmp     loc_180011F1F
0x180011e93  mov     rcx, [rsi+0D8h]; this
0x180011e9a  lea     rdx, [rsp+188h+var_168]; enum AuthorizationStatus *
0x180011e9f  mov     [rsp+188h+var_168], 0
0x180011ea7  call    ?GetAuthorizationStatus@CDeviceSettings@@QEAAJPEAW4AuthorizationStatus@@@Z; CDeviceSettings::GetAuthorizationStatus(AuthorizationStatus *)
0x180011eac  mov     ebx, eax
0x180011eae  test    eax, eax
0x180011eb0  js      short loc_180011F1F
0x180011eb2  cmp     [rsp+188h+var_168], 2
0x180011eb7  mov     edi, 0Dh
0x180011ebc  jnz     short loc_180011ED7
0x180011ebe  mov     rcx, [rsi+0D8h]; this
0x180011ec5  mov     edi, 0Eh
0x180011eca  call    ?UseDefaultSettings@CDeviceSettings@@QEAAHXZ; CDeviceSettings::UseDefaultSettings(void)
0x180011ecf  test    eax, eax
0x180011ed1  lea     ecx, [rdi+3Bh]
0x180011ed4  cmovz   edi, ecx
0x180011ed7  xor     edx, edx; Val
0x180011ed9  lea     rcx, [rsp+188h+Buffer]; void *
0x180011ede  mov     r8d, 12Ch; Size
0x180011ee4  call    memset_0
0x180011ee9  mov     rcx, cs:g_hinst; hInstance
0x180011ef0  lea     r8, [rsp+188h+Buffer]; lpBuffer
0x180011ef5  mov     r9d, 96h; cchBufferMax
0x180011efb  mov     edx, edi; uID
0x180011efd  call    cs:__imp_LoadStringW
0x180011f03  lea     rdx, [rsp+188h+Buffer]
0x180011f08  mov     rcx, rbp
0x180011f0b  call    cs:__imp_?SetContentString@Element@DirectUI@@QEAAJPEBG@Z; DirectUI::Element::SetContentString(ushort const *)
0x180011f11  lea     rdx, [rsp+188h+Buffer]
0x180011f16  mov     rcx, rbp
0x180011f19  call    cs:__imp_?SetAccName@Element@DirectUI@@QEAAJPEBG@Z; DirectUI::Element::SetAccName(ushort const *)
0x180011f1f  mov     rcx, cs:WPP_GLOBAL_Control
0x180011f26  cmp     rcx, r14
0x180011f29  jz      short loc_180011F49
0x180011f2b  test    byte ptr [rcx+1Ch], 20h
0x180011f2f  jz      short loc_180011F49
0x180011f31  mov     rcx, [rcx+10h]
0x180011f35  lea     r8, WPP_59386dd0a0913b67da6dc13cee28e88f_Traceguids
0x180011f3c  mov     edx, 100h
0x180011f41  mov     r9d, ebx
0x180011f44  call    WPP_SF_d
0x180011f49  mov     eax, ebx
0x180011f4b  mov     rcx, [rsp+188h+var_28]
0x180011f53  xor     rcx, rsp; StackCookie
0x180011f56  call    __security_check_cookie
0x180011f5b  lea     r11, [rsp+188h+var_18]
0x180011f63  mov     rbx, [r11+28h]
0x180011f67  mov     rbp, [r11+30h]
0x180011f6b  mov     rsp, r11
0x180011f6e  pop     r14
0x180011f70  pop     rdi
0x180011f71  pop     rsi
0x180011f72  retn
```
