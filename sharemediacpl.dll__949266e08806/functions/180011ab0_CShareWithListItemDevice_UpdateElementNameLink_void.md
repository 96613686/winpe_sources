# CShareWithListItemDevice::_UpdateElementNameLink(void)

- ea: `0x180011ab0`
- end: `0x180011b9c`
- name: `?_UpdateElementNameLink@CShareWithListItemDevice@@EEAAJXZ`
- size: `236`
- prototype: `__int64 __fastcall(CShareWithListItemDevice *__hidden this)`
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config, service_task, installer_update`

## callees

- `0x180003860`
- `0x180003888`
- `0x1800049c0`
- `0x180011ab0`

## import_xrefs

- `ole32!CoTaskMemFree` at `0x180011b61`
- `ole32!CoTaskMemFree` at `0x180011b61`
- `DUI70!?SetAccName@Element@DirectUI@@QEAAJPEBG@Z` at `0x180011b48`
- `DUI70!?SetAccName@Element@DirectUI@@QEAAJPEBG@Z` at `0x180011b56`
- `DUI70!?SetAccName@Element@DirectUI@@QEAAJPEBG@Z` at `0x180011b48`
- `DUI70!?SetAccName@Element@DirectUI@@QEAAJPEBG@Z` at `0x180011b56`
- `DUI70!?SetContentString@Element@DirectUI@@QEAAJPEBG@Z` at `0x180011b3a`
- `DUI70!?SetContentString@Element@DirectUI@@QEAAJPEBG@Z` at `0x180011b3a`
- `DUI70!StrToID` at `0x180011af1`
- `DUI70!StrToID` at `0x180011af1`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x180011afd`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x180011afd`

## string_xrefs

- `0x180011aea`: `ShareItemLink`

## pseudocode

```c
__int64 __fastcall CShareWithListItemDevice::_UpdateElementNameLink(CDeviceSettings **this)
{
  unsigned __int16 v2; // ax
  DirectUI::Element *Descendent; // rsi
  int DeviceName; // ebx
  CDeviceSettings *v5; // rcx
  LPVOID pv; // [rsp+58h] [rbp+10h] BYREF

  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 251, &WPP_59386dd0a0913b67da6dc13cee28e88f_Traceguids);
  v2 = StrToID(L"ShareItemLink");
  Descendent = DirectUI::Element::FindDescendent((DirectUI::Element *)this, v2);
  if ( Descendent )
  {
    v5 = this[27];
    pv = 0;
    DeviceName = CDeviceSettings::GetDeviceName(v5, (unsigned __int16 **)&pv);
    if ( DeviceName >= 0 )
    {
      DirectUI::Element::SetContentString(Descendent, (const unsigned __int16 *)pv);
      DirectUI::Element::SetAccName(Descendent, (const unsigned __int16 *)pv);
      DirectUI::Element::SetAccName((DirectUI::Element *)this, (const unsigned __int16 *)pv);
      CoTaskMemFree(pv);
    }
  }
  else
  {
    DeviceName = -2147467259;
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      252,
      &WPP_59386dd0a0913b67da6dc13cee28e88f_Traceguids,
      (unsigned int)DeviceName);
  return (unsigned int)DeviceName;
}

```

## disassembly

```asm
0x180011ab0  push    rbx
0x180011ab2  push    rbp
0x180011ab3  push    rsi
0x180011ab4  push    rdi
0x180011ab5  sub     rsp, 28h
0x180011ab9  mov     rdi, rcx
0x180011abc  mov     rcx, cs:WPP_GLOBAL_Control
0x180011ac3  lea     rbp, WPP_GLOBAL_Control
0x180011aca  cmp     rcx, rbp
0x180011acd  jz      short loc_180011AEA
0x180011acf  test    byte ptr [rcx+1Ch], 20h
0x180011ad3  jz      short loc_180011AEA
0x180011ad5  mov     rcx, [rcx+10h]
0x180011ad9  lea     r8, WPP_59386dd0a0913b67da6dc13cee28e88f_Traceguids
0x180011ae0  mov     edx, 0FBh
0x180011ae5  call    WPP_SF_
0x180011aea  lea     rcx, aShareitemlink; "ShareItemLink"
0x180011af1  call    cs:__imp_StrToID
0x180011af7  movzx   edx, ax
0x180011afa  mov     rcx, rdi
0x180011afd  call    cs:__imp_?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z; DirectUI::Element::FindDescendent(ushort)
0x180011b03  mov     rsi, rax
0x180011b06  test    rax, rax
0x180011b09  jnz     short loc_180011B12
0x180011b0b  mov     ebx, 80004005h
0x180011b10  jmp     short loc_180011B67
0x180011b12  mov     rcx, [rdi+0D8h]; this
0x180011b19  lea     rdx, [rsp+48h+pv]; unsigned __int16 **
0x180011b1e  mov     [rsp+48h+pv], 0
0x180011b27  call    ?GetDeviceName@CDeviceSettings@@QEAAJPEAPEAG@Z; CDeviceSettings::GetDeviceName(ushort * *)
0x180011b2c  mov     ebx, eax
0x180011b2e  test    eax, eax
0x180011b30  js      short loc_180011B67
0x180011b32  mov     rdx, [rsp+48h+pv]
0x180011b37  mov     rcx, rsi
0x180011b3a  call    cs:__imp_?SetContentString@Element@DirectUI@@QEAAJPEBG@Z; DirectUI::Element::SetContentString(ushort const *)
0x180011b40  mov     rdx, [rsp+48h+pv]
0x180011b45  mov     rcx, rsi
0x180011b48  call    cs:__imp_?SetAccName@Element@DirectUI@@QEAAJPEBG@Z; DirectUI::Element::SetAccName(ushort const *)
0x180011b4e  mov     rdx, [rsp+48h+pv]
0x180011b53  mov     rcx, rdi
0x180011b56  call    cs:__imp_?SetAccName@Element@DirectUI@@QEAAJPEBG@Z; DirectUI::Element::SetAccName(ushort const *)
0x180011b5c  mov     rcx, [rsp+48h+pv]; pv
0x180011b61  call    cs:__imp_CoTaskMemFree
0x180011b67  mov     rcx, cs:WPP_GLOBAL_Control
0x180011b6e  cmp     rcx, rbp
0x180011b71  jz      short loc_180011B91
0x180011b73  test    byte ptr [rcx+1Ch], 20h
0x180011b77  jz      short loc_180011B91
0x180011b79  mov     rcx, [rcx+10h]
0x180011b7d  lea     r8, WPP_59386dd0a0913b67da6dc13cee28e88f_Traceguids
0x180011b84  mov     edx, 0FCh
0x180011b89  mov     r9d, ebx
0x180011b8c  call    WPP_SF_d
0x180011b91  mov     eax, ebx
0x180011b93  add     rsp, 28h
0x180011b97  pop     rdi
0x180011b98  pop     rsi
0x180011b99  pop     rbp
0x180011b9a  pop     rbx
0x180011b9b  retn
```
