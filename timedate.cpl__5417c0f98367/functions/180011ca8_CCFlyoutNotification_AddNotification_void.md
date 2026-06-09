# CCFlyoutNotification::_AddNotification(void)

- ea: `0x180011ca8`
- end: `0x180011d30`
- name: `?_AddNotification@CCFlyoutNotification@@AEAAHXZ`
- size: `136`
- prototype: `__int64 __fastcall(CCFlyoutNotification *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x180010720`

## callees

- `0x180011ca8`

## import_xrefs

- `DUI70!?Destroy@Element@DirectUI@@QEAAJ_N@Z` at `0x180011d1a`
- `DUI70!?Destroy@Element@DirectUI@@QEAAJ_N@Z` at `0x180011d1a`
- `DUI70!?CreateElement@DUIXmlParser@DirectUI@@QEAAJPEBGPEAVElement@2@1PEAKPEAPEAV32@@Z` at `0x180011cf0`
- `DUI70!?CreateElement@DUIXmlParser@DirectUI@@QEAAJPEBGPEAVElement@2@1PEAKPEAPEAV32@@Z` at `0x180011cf0`
- `DUI70!?Add@Element@DirectUI@@QEAAJPEAV12@@Z` at `0x180011d04`
- `DUI70!?Add@Element@DirectUI@@QEAAJPEAV12@@Z` at `0x180011d04`

## pseudocode

```c
__int64 __fastcall CCFlyoutNotification::_AddNotification(struct DirectUI::Element **this)
{
  unsigned int v1; // ebx
  DirectUI::Element **v2; // rdi

  v1 = 0;
  if ( CCFlyoutNotification::s_pParser )
  {
    if ( CCFlyoutNotification::s_pParent )
    {
      if ( CCFlyoutNotification::s_pRoot )
      {
        v2 = this + 1;
        if ( (int)DirectUI::DUIXmlParser::CreateElement(
                    CCFlyoutNotification::s_pParser,
                    L"Notification",
                    0,
                    CCFlyoutNotification::s_pParent,
                    0,
                    this + 1) >= 0 )
        {
          if ( (int)DirectUI::Element::Add(CCFlyoutNotification::s_pParent, *v2) < 0 )
          {
            DirectUI::Element::Destroy(*v2, 1);
            *v2 = 0;
          }
          else
          {
            return 1;
          }
        }
      }
    }
  }
  return v1;
}

```

## disassembly

```asm
0x180011ca8  mov     [rsp+arg_0], rbx
0x180011cad  push    rdi
0x180011cae  sub     rsp, 30h
0x180011cb2  mov     rdi, rcx
0x180011cb5  xor     ebx, ebx
0x180011cb7  mov     rcx, cs:?s_pParser@CCFlyoutNotification@@0PEAVDUIXmlParser@DirectUI@@EA; DirectUI::DUIXmlParser * CCFlyoutNotification::s_pParser
0x180011cbe  test    rcx, rcx
0x180011cc1  jz      short loc_180011D23
0x180011cc3  mov     r9, cs:?s_pParent@CCFlyoutNotification@@0PEAVElement@DirectUI@@EA; DirectUI::Element * CCFlyoutNotification::s_pParent
0x180011cca  test    r9, r9
0x180011ccd  jz      short loc_180011D23
0x180011ccf  cmp     cs:?s_pRoot@CCFlyoutNotification@@1PEAVElement@DirectUI@@EA, rbx; DirectUI::Element * CCFlyoutNotification::s_pRoot
0x180011cd6  jz      short loc_180011D23
0x180011cd8  add     rdi, 8
0x180011cdc  lea     rdx, aNotification; "Notification"
0x180011ce3  mov     [rsp+38h+var_10], rdi
0x180011ce8  xor     r8d, r8d
0x180011ceb  mov     [rsp+38h+var_18], rbx
0x180011cf0  call    cs:__imp_?CreateElement@DUIXmlParser@DirectUI@@QEAAJPEBGPEAVElement@2@1PEAKPEAPEAV32@@Z; DirectUI::DUIXmlParser::CreateElement(ushort const *,DirectUI::Element *,DirectUI::Element *,ulong *,DirectUI::Element * *)
0x180011cf6  test    eax, eax
0x180011cf8  js      short loc_180011D23
0x180011cfa  mov     rdx, [rdi]
0x180011cfd  mov     rcx, cs:?s_pParent@CCFlyoutNotification@@0PEAVElement@DirectUI@@EA; DirectUI::Element * CCFlyoutNotification::s_pParent
0x180011d04  call    cs:__imp_?Add@Element@DirectUI@@QEAAJPEAV12@@Z; DirectUI::Element::Add(DirectUI::Element *)
0x180011d0a  test    eax, eax
0x180011d0c  js      short loc_180011D15
0x180011d0e  mov     ebx, 1
0x180011d13  jmp     short loc_180011D23
0x180011d15  mov     rcx, [rdi]
0x180011d18  mov     dl, 1
0x180011d1a  call    cs:__imp_?Destroy@Element@DirectUI@@QEAAJ_N@Z; DirectUI::Element::Destroy(bool)
0x180011d20  mov     [rdi], rbx
0x180011d23  mov     eax, ebx
0x180011d25  mov     rbx, [rsp+38h+arg_0]
0x180011d2a  add     rsp, 30h
0x180011d2e  pop     rdi
0x180011d2f  retn
```
