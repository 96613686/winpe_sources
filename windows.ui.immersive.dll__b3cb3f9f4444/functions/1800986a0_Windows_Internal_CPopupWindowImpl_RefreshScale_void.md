# Windows::Internal::CPopupWindowImpl::_RefreshScale(void)

- ea: `0x1800986a0`
- end: `0x18009879b`
- name: `?_RefreshScale@CPopupWindowImpl@Internal@Windows@@AEAAXXZ`
- size: `251`
- prototype: `void __fastcall(Windows::Internal::CPopupWindowImpl *__hidden this)`
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config, installer_update`

## callers

- `0x180022950`
- `0x180026e10`

## callees

- `0x180040968`
- `0x1800906cc`
- `0x180096b5c`
- `0x1800986a0`
- `0x1800ed010`

## import_xrefs

- `DUI70!?GetElement@NativeHWNDHost@DirectUI@@QEAAPEAVElement@2@XZ` at `0x1800986ae`
- `DUI70!?GetElement@NativeHWNDHost@DirectUI@@QEAAPEAVElement@2@XZ` at `0x18009870b`
- `DUI70!?GetElement@NativeHWNDHost@DirectUI@@QEAAPEAVElement@2@XZ` at `0x180098749`
- `DUI70!?GetElement@NativeHWNDHost@DirectUI@@QEAAPEAVElement@2@XZ` at `0x1800986ae`
- `DUI70!?GetElement@NativeHWNDHost@DirectUI@@QEAAPEAVElement@2@XZ` at `0x18009870b`
- `DUI70!?GetElement@NativeHWNDHost@DirectUI@@QEAAPEAVElement@2@XZ` at `0x180098749`
- `DUI70!?Destroy@DUIXmlParser@DirectUI@@QEAAXXZ` at `0x180098730`
- `DUI70!?Destroy@DUIXmlParser@DirectUI@@QEAAXXZ` at `0x180098730`
- `DUI70!?UpdateSheets@DUIXmlParser@DirectUI@@QEAAJPEAVElement@2@@Z` at `0x18009871f`
- `DUI70!?UpdateSheets@DUIXmlParser@DirectUI@@QEAAJPEAVElement@2@@Z` at `0x18009871f`
- `DUI70!?GetDisplayNode@Element@DirectUI@@QEAAPEAUHGADGET__@@XZ` at `0x18009875b`
- `DUI70!?GetDisplayNode@Element@DirectUI@@QEAAPEAUHGADGET__@@XZ` at `0x180098779`
- `DUI70!?GetDisplayNode@Element@DirectUI@@QEAAPEAUHGADGET__@@XZ` at `0x18009875b`
- `DUI70!?GetDisplayNode@Element@DirectUI@@QEAAPEAUHGADGET__@@XZ` at `0x180098779`
- `DUser!InvalidateGadget` at `0x18009876a`
- `DUser!InvalidateGadget` at `0x18009876a`
- `DUser!InvalidateLayeredDescendants` at `0x180098788`
- `DUser!InvalidateLayeredDescendants` at `0x180098788`

## pseudocode

```c
void __fastcall Windows::Internal::CPopupWindowImpl::_RefreshScale(Windows::Internal::CPopupWindowImpl *this)
{
  struct DirectUI::Element *Element; // rax
  __int64 v3; // rcx
  unsigned int v4; // eax
  struct DirectUI::Element *v5; // rax
  DirectUI::Element *v6; // rbx
  struct HGADGET__ *DisplayNode; // rax
  struct HGADGET__ *v8; // rax
  char v9; // [rsp+40h] [rbp+8h] BYREF
  DirectUI::DUIXmlParser *v10; // [rsp+48h] [rbp+10h]

  v9 = 0;
  Element = DirectUI::NativeHWNDHost::GetElement(this);
  ElementWalkAll__lambda_5887d6412ebffbf74f7db4f9848df3d6_(Element, &v9);
  v3 = *((_QWORD *)this + 12);
  v10 = 0;
  v4 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v3 + 112LL))(v3);
  if ( (int)DUI_CreateParserFromResource(&_ImageBase, v4, 0) >= 0 )
  {
    v5 = DirectUI::NativeHWNDHost::GetElement(this);
    DirectUI::DUIXmlParser::UpdateSheets(v10, v5);
    DirectUI::DUIXmlParser::Destroy(v10);
  }
  Windows::Internal::CPopupWindowImpl::_FireResizeEvent(this, 0);
  v6 = DirectUI::NativeHWNDHost::GetElement(this);
  DisplayNode = DirectUI::Element::GetDisplayNode(v6);
  InvalidateGadget(DisplayNode);
  v8 = DirectUI::Element::GetDisplayNode(v6);
  InvalidateLayeredDescendants(v8);
}

```

## disassembly

```asm
0x1800986a0  push    rbx
0x1800986a2  sub     rsp, 30h
0x1800986a6  mov     rbx, rcx
0x1800986a9  mov     [rsp+38h+arg_0], 0
0x1800986ae  call    cs:__imp_?GetElement@NativeHWNDHost@DirectUI@@QEAAPEAVElement@2@XZ; DirectUI::NativeHWNDHost::GetElement(void)
0x1800986b5  nop     dword ptr [rax+rax+00h]
0x1800986ba  mov     rcx, rax
0x1800986bd  lea     rdx, [rsp+38h+arg_0]
0x1800986c2  call    ElementWalkAll__lambda_5887d6412ebffbf74f7db4f9848df3d6___; ElementWalkAll__lambda_5887d6412ebffbf74f7db4f9848df3d6_
0x1800986c7  mov     rcx, [rbx+60h]
0x1800986cb  mov     [rsp+38h+arg_8], 0
0x1800986d4  mov     rax, [rcx]
0x1800986d7  mov     rax, [rax+70h]
0x1800986db  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800986e0  lea     rcx, [rsp+38h+arg_8]
0x1800986e5  xor     r8d, r8d
0x1800986e8  mov     [rsp+38h+var_10], rcx
0x1800986ed  mov     edx, eax
0x1800986ef  lea     rcx, __ImageBase
0x1800986f6  mov     [rsp+38h+var_18], 0
0x1800986ff  call    ?DUI_CreateParserFromResource@@YAJPEAUHINSTANCE__@@IW4DUI_PARSER_LOAD_FLAGS@@W4DEVICE_SCALE_FACTOR@@PEAUHWND__@@PEAPEAVDUIXmlParser@DirectUI@@@Z; DUI_CreateParserFromResource(HINSTANCE__ *,uint,DUI_PARSER_LOAD_FLAGS,DEVICE_SCALE_FACTOR,HWND__ *,DirectUI::DUIXmlParser * *)
0x180098704  test    eax, eax
0x180098706  js      short loc_18009873C
0x180098708  mov     rcx, rbx
0x18009870b  call    cs:__imp_?GetElement@NativeHWNDHost@DirectUI@@QEAAPEAVElement@2@XZ; DirectUI::NativeHWNDHost::GetElement(void)
0x180098712  nop     dword ptr [rax+rax+00h]
0x180098717  mov     rcx, [rsp+38h+arg_8]
0x18009871c  mov     rdx, rax
0x18009871f  call    cs:__imp_?UpdateSheets@DUIXmlParser@DirectUI@@QEAAJPEAVElement@2@@Z; DirectUI::DUIXmlParser::UpdateSheets(DirectUI::Element *)
0x180098726  nop     dword ptr [rax+rax+00h]
0x18009872b  mov     rcx, [rsp+38h+arg_8]
0x180098730  call    cs:__imp_?Destroy@DUIXmlParser@DirectUI@@QEAAXXZ; DirectUI::DUIXmlParser::Destroy(void)
0x180098737  nop     dword ptr [rax+rax+00h]
0x18009873c  xor     edx, edx; bool
0x18009873e  mov     rcx, rbx; this
0x180098741  call    ?_FireResizeEvent@CPopupWindowImpl@Internal@Windows@@AEAAX_N@Z; Windows::Internal::CPopupWindowImpl::_FireResizeEvent(bool)
0x180098746  mov     rcx, rbx
0x180098749  call    cs:__imp_?GetElement@NativeHWNDHost@DirectUI@@QEAAPEAVElement@2@XZ; DirectUI::NativeHWNDHost::GetElement(void)
0x180098750  nop     dword ptr [rax+rax+00h]
0x180098755  mov     rcx, rax
0x180098758  mov     rbx, rax
0x18009875b  call    cs:__imp_?GetDisplayNode@Element@DirectUI@@QEAAPEAUHGADGET__@@XZ; DirectUI::Element::GetDisplayNode(void)
0x180098762  nop     dword ptr [rax+rax+00h]
0x180098767  mov     rcx, rax
0x18009876a  call    cs:__imp_InvalidateGadget
0x180098771  nop     dword ptr [rax+rax+00h]
0x180098776  mov     rcx, rbx
0x180098779  call    cs:__imp_?GetDisplayNode@Element@DirectUI@@QEAAPEAUHGADGET__@@XZ; DirectUI::Element::GetDisplayNode(void)
0x180098780  nop     dword ptr [rax+rax+00h]
0x180098785  mov     rcx, rax
0x180098788  call    cs:__imp_InvalidateLayeredDescendants
0x18009878f  nop     dword ptr [rax+rax+00h]
0x180098794  add     rsp, 30h
0x180098798  pop     rbx
0x180098799  retn
```
