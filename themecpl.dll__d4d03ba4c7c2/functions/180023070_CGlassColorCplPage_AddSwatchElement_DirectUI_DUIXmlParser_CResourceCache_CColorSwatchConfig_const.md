# CGlassColorCplPage::_AddSwatchElement(DirectUI::DUIXmlParser *,CResourceCache *,CColorSwatchConfig const *)

- ea: `0x180023070`
- end: `0x18002328b`
- name: `?_AddSwatchElement@CGlassColorCplPage@@AEAAJPEAVDUIXmlParser@DirectUI@@PEAVCResourceCache@@PEBVCColorSwatchConfig@@@Z`
- size: `539`
- prototype: `int(CGlassColorCplPage *__hidden this, struct DirectUI::DUIXmlParser *, struct CResourceCache *, const struct CColorSwatchConfig *)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x180023294`

## callees

- `0x180023070`
- `0x180024474`
- `0x18004ff74`

## import_xrefs

- `GDI32!DeleteObject` at `0x180023257`
- `GDI32!DeleteObject` at `0x180023257`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x1800230a0`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x180023187`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x1800230a0`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x180023187`
- `DUI70!StrToID` at `0x18002308e`
- `DUI70!StrToID` at `0x180023175`
- `DUI70!StrToID` at `0x18002308e`
- `DUI70!StrToID` at `0x180023175`
- `DUI70!?CreateElement@DUIXmlParser@DirectUI@@QEAAJPEBGPEAVElement@2@1PEAKPEAPEAV32@@Z` at `0x1800230e4`
- `DUI70!?CreateElement@DUIXmlParser@DirectUI@@QEAAJPEBGPEAVElement@2@1PEAKPEAPEAV32@@Z` at `0x1800230e4`
- `DUI70!?Add@Element@DirectUI@@QEAAJPEAV12@@Z` at `0x180023102`
- `DUI70!?Add@Element@DirectUI@@QEAAJPEAV12@@Z` at `0x180023102`
- `DUI70!?Destroy@Element@DirectUI@@QEAAJ_N@Z` at `0x18002327d`
- `DUI70!?Destroy@Element@DirectUI@@QEAAJ_N@Z` at `0x18002327d`
- `DUI70!?SetAccDesc@Element@DirectUI@@QEAAJPEBG@Z` at `0x180023151`
- `DUI70!?SetAccDesc@Element@DirectUI@@QEAAJPEBG@Z` at `0x180023151`
- `DUI70!?SetAccName@Element@DirectUI@@QEAAJPEBG@Z` at `0x18002313f`
- `DUI70!?SetAccName@Element@DirectUI@@QEAAJPEBG@Z` at `0x18002313f`
- `DUI70!?SetID@Element@DirectUI@@QEAAJPEBG@Z` at `0x180023123`
- `DUI70!?SetID@Element@DirectUI@@QEAAJPEBG@Z` at `0x180023123`
- `DUI70!?SetTooltip@Element@DirectUI@@QEAAJ_N@Z` at `0x180023162`
- `DUI70!?SetTooltip@Element@DirectUI@@QEAAJ_N@Z` at `0x180023162`
- `DUI70!?Release@Value@DirectUI@@QEAAXXZ` at `0x180023244`
- `DUI70!?Release@Value@DirectUI@@QEAAXXZ` at `0x180023244`
- `DUI70!?SetValue@Element@DirectUI@@QEAAJP6APEBUPropertyInfo@2@XZHPEAVValue@2@@Z` at `0x180023233`
- `DUI70!?SetValue@Element@DirectUI@@QEAAJP6APEBUPropertyInfo@2@XZHPEAVValue@2@@Z` at `0x180023233`
- `DUI70!?ContentProp@Element@DirectUI@@SAPEBUPropertyInfo@2@XZ` at `0x180023220`
- `DUI70!?CreateGraphic@Value@DirectUI@@SAPEAV12@PEAUHBITMAP__@@EI_N11@Z` at `0x18002320c`
- `DUI70!?CreateGraphic@Value@DirectUI@@SAPEAV12@PEAUHBITMAP__@@EI_N11@Z` at `0x18002320c`

## pseudocode

```c
__int64 __fastcall CGlassColorCplPage::_AddSwatchElement(
        CGlassColorCplPage *this,
        struct DirectUI::DUIXmlParser *a2,
        struct CResourceCache *a3,
        const unsigned __int16 **a4)
{
  unsigned __int16 v8; // ax
  struct DirectUI::Element *Descendent; // rsi
  int Element; // ebx
  DirectUI::Element *v11; // rsi
  unsigned __int16 v12; // ax
  DirectUI::Element *v13; // rsi
  const unsigned __int16 *v14; // rdx
  unsigned __int16 *v15; // rdx
  struct DirectUI::Value *Graphic; // rax
  DirectUI::Value *v17; // rdi
  HGDIOBJ ho[7]; // [rsp+30h] [rbp-38h] BYREF

  v8 = StrToID(L"SwatchSelector");
  Descendent = DirectUI::Element::FindDescendent(this, v8);
  if ( !Descendent )
    return (unsigned int)-2147467259;
  ho[0] = 0;
  Element = DirectUI::DUIXmlParser::CreateElement(a2, L"ColorSwatch", 0, Descendent, 0, (struct DirectUI::Element **)ho);
  if ( Element >= 0 )
  {
    Element = DirectUI::Element::Add(Descendent, (struct DirectUI::Element *)ho[0]);
    if ( Element < 0 )
    {
      DirectUI::Element::Destroy((DirectUI::Element *)ho[0], 1);
      return (unsigned int)Element;
    }
    v11 = (DirectUI::Element *)ho[0];
    Element = DirectUI::Element::SetID((DirectUI::Element *)ho[0], *a4);
    if ( Element >= 0 )
    {
      DirectUI::Element::SetAccName(v11, *a4);
      DirectUI::Element::SetAccDesc(v11, *a4);
      DirectUI::Element::SetTooltip(v11, 1);
      v12 = StrToID(L"ColorSwatchPreview");
      v13 = DirectUI::Element::FindDescendent(v11, v12);
      if ( !v13 )
        return (unsigned int)-2147467259;
      v14 = a4[2];
      ho[0] = 0;
      Element = CResourceCache::GetCachedHandle(a3, v14, (HINSTANCE *)ho);
      if ( Element >= 0 )
      {
        v15 = (unsigned __int16 *)*((unsigned __int16 *)a4 + 12);
        ho[0] = 0;
        Element = LoadImageScaled(g_hinst, v15, (HBITMAP *)ho);
        if ( Element >= 0 )
        {
          Graphic = DirectUI::Value::CreateGraphic((HBITMAP)ho[0], 2u, 0xFFu, 0, 0, 0);
          v17 = Graphic;
          if ( Graphic )
          {
            Element = DirectUI::Element::SetValue(
                        v13,
                        (const struct DirectUI::PropertyInfo *(*)(void))DirectUI::Element::ContentProp,
                        1,
                        Graphic);
            DirectUI::Value::Release(v17);
            return (unsigned int)Element;
          }
          DeleteObject(ho[0]);
          return (unsigned int)-2147467259;
        }
      }
    }
  }
  return (unsigned int)Element;
}

```

## disassembly

```asm
0x180023070  push    rbx
0x180023072  push    rbp
0x180023073  push    rsi
0x180023074  push    rdi
0x180023075  push    r14
0x180023077  sub     rsp, 40h
0x18002307b  mov     rbx, rcx
0x18002307e  mov     rdi, r9
0x180023081  lea     rcx, aSwatchselector; "SwatchSelector"
0x180023088  mov     r14, r8
0x18002308b  mov     rbp, rdx
0x18002308e  call    cs:__imp_StrToID
0x180023095  nop     dword ptr [rax+rax+00h]
0x18002309a  movzx   edx, ax
0x18002309d  mov     rcx, rbx
0x1800230a0  call    cs:__imp_?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z; DirectUI::Element::FindDescendent(ushort)
0x1800230a7  nop     dword ptr [rax+rax+00h]
0x1800230ac  mov     rsi, rax
0x1800230af  test    rax, rax
0x1800230b2  jz      loc_180023263
0x1800230b8  lea     rax, [rsp+68h+ho]
0x1800230bd  mov     [rsp+68h+ho], 0
0x1800230c6  mov     [rsp+68h+var_40], rax
0x1800230cb  lea     rdx, aColorswatch; "ColorSwatch"
0x1800230d2  mov     r9, rsi
0x1800230d5  mov     [rsp+68h+var_48], 0
0x1800230de  xor     r8d, r8d
0x1800230e1  mov     rcx, rbp
0x1800230e4  call    cs:__imp_?CreateElement@DUIXmlParser@DirectUI@@QEAAJPEBGPEAVElement@2@1PEAKPEAPEAV32@@Z; DirectUI::DUIXmlParser::CreateElement(ushort const *,DirectUI::Element *,DirectUI::Element *,ulong *,DirectUI::Element * *)
0x1800230eb  nop     dword ptr [rax+rax+00h]
0x1800230f0  mov     ebx, eax
0x1800230f2  test    eax, eax
0x1800230f4  js      loc_180023268
0x1800230fa  mov     rdx, [rsp+68h+ho]
0x1800230ff  mov     rcx, rsi
0x180023102  call    cs:__imp_?Add@Element@DirectUI@@QEAAJPEAV12@@Z; DirectUI::Element::Add(DirectUI::Element *)
0x180023109  nop     dword ptr [rax+rax+00h]
0x18002310e  mov     ebx, eax
0x180023110  test    eax, eax
0x180023112  js      loc_180023276
0x180023118  mov     rsi, [rsp+68h+ho]
0x18002311d  mov     rdx, [rdi]
0x180023120  mov     rcx, rsi
0x180023123  call    cs:__imp_?SetID@Element@DirectUI@@QEAAJPEBG@Z; DirectUI::Element::SetID(ushort const *)
0x18002312a  nop     dword ptr [rax+rax+00h]
0x18002312f  mov     ebx, eax
0x180023131  test    eax, eax
0x180023133  js      loc_180023268
0x180023139  mov     rdx, [rdi]
0x18002313c  mov     rcx, rsi
0x18002313f  call    cs:__imp_?SetAccName@Element@DirectUI@@QEAAJPEBG@Z; DirectUI::Element::SetAccName(ushort const *)
0x180023146  nop     dword ptr [rax+rax+00h]
0x18002314b  mov     rdx, [rdi]
0x18002314e  mov     rcx, rsi
0x180023151  call    cs:__imp_?SetAccDesc@Element@DirectUI@@QEAAJPEBG@Z; DirectUI::Element::SetAccDesc(ushort const *)
0x180023158  nop     dword ptr [rax+rax+00h]
0x18002315d  mov     dl, 1
0x18002315f  mov     rcx, rsi
0x180023162  call    cs:__imp_?SetTooltip@Element@DirectUI@@QEAAJ_N@Z; DirectUI::Element::SetTooltip(bool)
0x180023169  nop     dword ptr [rax+rax+00h]
0x18002316e  lea     rcx, aColorswatchpre; "ColorSwatchPreview"
0x180023175  call    cs:__imp_StrToID
0x18002317c  nop     dword ptr [rax+rax+00h]
0x180023181  movzx   edx, ax
0x180023184  mov     rcx, rsi
0x180023187  call    cs:__imp_?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z; DirectUI::Element::FindDescendent(ushort)
0x18002318e  nop     dword ptr [rax+rax+00h]
0x180023193  mov     rsi, rax
0x180023196  test    rax, rax
0x180023199  jz      loc_180023263
0x18002319f  mov     rdx, [rdi+10h]; unsigned __int16 *
0x1800231a3  lea     r8, [rsp+68h+ho]; HINSTANCE *
0x1800231a8  mov     rcx, r14; this
0x1800231ab  mov     [rsp+68h+ho], 0
0x1800231b4  call    ?GetCachedHandle@CResourceCache@@QEAAJPEBGPEAPEAUHINSTANCE__@@@Z; CResourceCache::GetCachedHandle(ushort const *,HINSTANCE__ * *)
0x1800231b9  mov     ebx, eax
0x1800231bb  test    eax, eax
0x1800231bd  js      loc_180023268
0x1800231c3  movzx   edx, word ptr [rdi+18h]; unsigned __int16 *
0x1800231c7  lea     rax, [rsp+68h+ho]
0x1800231cc  mov     rcx, cs:g_hinst; HINSTANCE
0x1800231d3  mov     r9d, 1
0x1800231d9  mov     [rsp+68h+var_48], rax; HBITMAP *
0x1800231de  mov     [rsp+68h+ho], 0
0x1800231e7  call    LoadImageScaled
0x1800231ec  mov     ebx, eax
0x1800231ee  test    eax, eax
0x1800231f0  js      short loc_180023268
0x1800231f2  mov     rcx, [rsp+68h+ho]
0x1800231f7  xor     r9d, r9d
0x1800231fa  mov     byte ptr [rsp+68h+var_40], 0
0x1800231ff  mov     r8d, 0FFh
0x180023205  mov     dl, 2
0x180023207  mov     byte ptr [rsp+68h+var_48], 0
0x18002320c  call    cs:__imp_?CreateGraphic@Value@DirectUI@@SAPEAV12@PEAUHBITMAP__@@EI_N11@Z; DirectUI::Value::CreateGraphic(HBITMAP__ *,uchar,uint,bool,bool,bool)
0x180023213  nop     dword ptr [rax+rax+00h]
0x180023218  mov     rdi, rax
0x18002321b  test    rax, rax
0x18002321e  jz      short loc_180023252
0x180023220  mov     rdx, cs:__imp_?ContentProp@Element@DirectUI@@SAPEBUPropertyInfo@2@XZ; DirectUI::Element::ContentProp(void)
0x180023227  mov     r9, rax
0x18002322a  mov     r8d, 1
0x180023230  mov     rcx, rsi
0x180023233  call    cs:__imp_?SetValue@Element@DirectUI@@QEAAJP6APEBUPropertyInfo@2@XZHPEAVValue@2@@Z; DirectUI::Element::SetValue(DirectUI::PropertyInfo const * (*)(void),int,DirectUI::Value *)
0x18002323a  nop     dword ptr [rax+rax+00h]
0x18002323f  mov     rcx, rdi
0x180023242  mov     ebx, eax
0x180023244  call    cs:__imp_?Release@Value@DirectUI@@QEAAXXZ; DirectUI::Value::Release(void)
0x18002324b  nop     dword ptr [rax+rax+00h]
0x180023250  jmp     short loc_180023268
0x180023252  mov     rcx, [rsp+68h+ho]; ho
0x180023257  call    cs:__imp_DeleteObject
0x18002325e  nop     dword ptr [rax+rax+00h]
0x180023263  mov     ebx, 80004005h
0x180023268  mov     eax, ebx
0x18002326a  add     rsp, 40h
0x18002326e  pop     r14
0x180023270  pop     rdi
0x180023271  pop     rsi
0x180023272  pop     rbp
0x180023273  pop     rbx
0x180023274  retn
0x180023276  mov     rcx, [rsp+68h+ho]
0x18002327b  mov     dl, 1
0x18002327d  call    cs:__imp_?Destroy@Element@DirectUI@@QEAAJ_N@Z; DirectUI::Element::Destroy(bool)
0x180023284  nop     dword ptr [rax+rax+00h]
0x180023289  jmp     short loc_180023268
```
