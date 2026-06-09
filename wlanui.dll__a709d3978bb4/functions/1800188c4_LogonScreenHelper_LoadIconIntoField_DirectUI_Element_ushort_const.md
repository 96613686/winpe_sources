# LogonScreenHelper::LoadIconIntoField(DirectUI::Element *,ushort const *)

- ea: `0x1800188c4`
- end: `0x180018937`
- name: `?LoadIconIntoField@LogonScreenHelper@@QEAAXPEAVElement@DirectUI@@PEBG@Z`
- size: `115`
- prototype: `void(LogonScreenHelper *__hidden this, struct DirectUI::Element *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x1800182a8`

## callees

- `0x1800188c4`

## import_xrefs

- `USER32!LoadIconW` at `0x1800188db`
- `USER32!LoadIconW` at `0x1800188db`
- `DUI70!?CreateGraphic@Value@DirectUI@@SAPEAV12@PEAUHICON__@@_N11@Z` at `0x1800188f1`
- `DUI70!?CreateGraphic@Value@DirectUI@@SAPEAV12@PEAUHICON__@@_N11@Z` at `0x1800188f1`
- `DUI70!?SetValue@Element@DirectUI@@QEAAJP6APEBUPropertyInfo@2@XZHPEAVValue@2@@Z` at `0x180018912`
- `DUI70!?SetValue@Element@DirectUI@@QEAAJP6APEBUPropertyInfo@2@XZHPEAVValue@2@@Z` at `0x180018912`
- `DUI70!?SetVisible@Element@DirectUI@@QEAAJ_N@Z` at `0x18001891d`
- `DUI70!?SetVisible@Element@DirectUI@@QEAAJ_N@Z` at `0x18001891d`
- `DUI70!?Release@Value@DirectUI@@QEAAXXZ` at `0x180018926`
- `DUI70!?Release@Value@DirectUI@@QEAAXXZ` at `0x180018926`
- `DUI70!?ContentProp@Element@DirectUI@@SAPEBUPropertyInfo@2@XZ` at `0x1800188ff`

## pseudocode

```c
void __fastcall LogonScreenHelper::LoadIconIntoField(
        LogonScreenHelper *this,
        struct DirectUI::Element *a2,
        const unsigned __int16 *a3)
{
  HICON IconW; // rax
  struct DirectUI::Value *Graphic; // rax
  DirectUI::Value *v6; // rdi

  if ( a2 )
  {
    IconW = LoadIconW(0, a3);
    if ( IconW )
    {
      Graphic = DirectUI::Value::CreateGraphic(IconW, 0, 0, 0);
      v6 = Graphic;
      if ( Graphic )
      {
        DirectUI::Element::SetValue(
          a2,
          (const struct DirectUI::PropertyInfo *(*)(void))DirectUI::Element::ContentProp,
          1,
          Graphic);
        DirectUI::Element::SetVisible(a2, 0);
        DirectUI::Value::Release(v6);
      }
    }
  }
}

```

## disassembly

```asm
0x1800188c4  test    rdx, rdx
0x1800188c7  jz      short locret_180018936
0x1800188c9  mov     [rsp+arg_0], rbx
0x1800188ce  push    rdi
0x1800188cf  sub     rsp, 20h
0x1800188d3  mov     rbx, rdx
0x1800188d6  xor     ecx, ecx; hInstance
0x1800188d8  mov     rdx, r8; lpIconName
0x1800188db  call    cs:__imp_LoadIconW
0x1800188e1  test    rax, rax
0x1800188e4  jz      short loc_18001892C
0x1800188e6  xor     r9d, r9d
0x1800188e9  xor     r8d, r8d
0x1800188ec  xor     edx, edx
0x1800188ee  mov     rcx, rax
0x1800188f1  call    cs:__imp_?CreateGraphic@Value@DirectUI@@SAPEAV12@PEAUHICON__@@_N11@Z; DirectUI::Value::CreateGraphic(HICON__ *,bool,bool,bool)
0x1800188f7  mov     rdi, rax
0x1800188fa  test    rax, rax
0x1800188fd  jz      short loc_18001892C
0x1800188ff  mov     rdx, cs:__imp_?ContentProp@Element@DirectUI@@SAPEBUPropertyInfo@2@XZ; DirectUI::Element::ContentProp(void)
0x180018906  mov     r9, rax
0x180018909  mov     r8d, 1
0x18001890f  mov     rcx, rbx
0x180018912  call    cs:__imp_?SetValue@Element@DirectUI@@QEAAJP6APEBUPropertyInfo@2@XZHPEAVValue@2@@Z; DirectUI::Element::SetValue(DirectUI::PropertyInfo const * (*)(void),int,DirectUI::Value *)
0x180018918  xor     edx, edx
0x18001891a  mov     rcx, rbx
0x18001891d  call    cs:__imp_?SetVisible@Element@DirectUI@@QEAAJ_N@Z; DirectUI::Element::SetVisible(bool)
0x180018923  mov     rcx, rdi
0x180018926  call    cs:__imp_?Release@Value@DirectUI@@QEAAXXZ; DirectUI::Value::Release(void)
0x18001892c  mov     rbx, [rsp+28h+arg_0]
0x180018931  add     rsp, 20h
0x180018935  pop     rdi
0x180018936  retn
```
