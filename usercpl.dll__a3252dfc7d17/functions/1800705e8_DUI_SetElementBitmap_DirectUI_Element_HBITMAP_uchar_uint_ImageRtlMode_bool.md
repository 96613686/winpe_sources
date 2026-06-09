# DUI_SetElementBitmap(DirectUI::Element *,HBITMAP__ *,uchar,uint,ImageRtlMode,bool)

- ea: `0x1800705e8`
- end: `0x180070680`
- name: `?DUI_SetElementBitmap@@YAJPEAVElement@DirectUI@@PEAUHBITMAP__@@EIW4ImageRtlMode@@_N@Z`
- size: `152`
- prototype: `int __high(struct DirectUI::Element *, HBITMAP, unsigned __int8, unsigned int, enum ImageRtlMode, bool)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x18003bc3c`
- `0x180061f48`

## callees

- `0x1800705e8`

## import_xrefs

- `DUI70!?ContentProp@Element@DirectUI@@SAPEBUPropertyInfo@2@XZ` at `0x180070629`
- `DUI70!?ContentProp@Element@DirectUI@@SAPEBUPropertyInfo@2@XZ` at `0x18007065f`
- `DUI70!?SetValue@Element@DirectUI@@QEAAJP6APEBUPropertyInfo@2@XZHPEAVValue@2@@Z` at `0x18007063c`
- `DUI70!?SetValue@Element@DirectUI@@QEAAJP6APEBUPropertyInfo@2@XZHPEAVValue@2@@Z` at `0x18007063c`
- `DUI70!?Release@Value@DirectUI@@QEAAXXZ` at `0x180070647`
- `DUI70!?Release@Value@DirectUI@@QEAAXXZ` at `0x180070647`
- `DUI70!?CreateGraphic@Value@DirectUI@@SAPEAV12@PEAUHBITMAP__@@EI_N11@Z` at `0x18007061b`
- `DUI70!?CreateGraphic@Value@DirectUI@@SAPEAV12@PEAUHBITMAP__@@EI_N11@Z` at `0x18007061b`
- `DUI70!?RemoveLocalValue@Element@DirectUI@@QEAAJP6APEBUPropertyInfo@2@XZ@Z` at `0x180070666`
- `DUI70!?RemoveLocalValue@Element@DirectUI@@QEAAJP6APEBUPropertyInfo@2@XZ@Z` at `0x180070666`
- `GDI32!DeleteObject` at `0x180070652`
- `GDI32!DeleteObject` at `0x180070652`

## pseudocode

```c
__int64 __fastcall DUI_SetElementBitmap(DirectUI::Element *a1, HBITMAP a2, unsigned __int8 a3)
{
  struct DirectUI::Value *Graphic; // rax
  DirectUI::Value *v6; // rsi
  unsigned int v7; // ebx

  if ( a2 )
  {
    Graphic = DirectUI::Value::CreateGraphic(a2, a3, 0xFFFFFFFF, 0, 0, 0);
    v6 = Graphic;
    if ( Graphic )
    {
      v7 = DirectUI::Element::SetValue(
             a1,
             (const struct DirectUI::PropertyInfo *(*)(void))DirectUI::Element::ContentProp,
             1,
             Graphic);
      DirectUI::Value::Release(v6);
    }
    else
    {
      DeleteObject(a2);
      return (unsigned int)-2147024882;
    }
  }
  else
  {
    return (unsigned int)DirectUI::Element::RemoveLocalValue(
                           a1,
                           (const struct DirectUI::PropertyInfo *(*)(void))DirectUI::Element::ContentProp);
  }
  return v7;
}

```

## disassembly

```asm
0x1800705e8  mov     [rsp+arg_0], rbx
0x1800705ed  mov     [rsp+arg_8], rsi
0x1800705f2  push    rdi
0x1800705f3  sub     rsp, 30h
0x1800705f7  mov     al, r8b
0x1800705fa  mov     rbx, rdx
0x1800705fd  mov     rdi, rcx
0x180070600  test    rdx, rdx
0x180070603  jz      short loc_18007065F
0x180070605  mov     [rsp+38h+var_10], 0
0x18007060a  xor     r9d, r9d
0x18007060d  or      r8d, 0FFFFFFFFh
0x180070611  mov     [rsp+38h+var_18], 0
0x180070616  mov     dl, al
0x180070618  mov     rcx, rbx
0x18007061b  call    cs:__imp_?CreateGraphic@Value@DirectUI@@SAPEAV12@PEAUHBITMAP__@@EI_N11@Z; DirectUI::Value::CreateGraphic(HBITMAP__ *,uchar,uint,bool,bool,bool)
0x180070621  mov     rsi, rax
0x180070624  test    rax, rax
0x180070627  jz      short loc_18007064F
0x180070629  mov     rdx, cs:__imp_?ContentProp@Element@DirectUI@@SAPEBUPropertyInfo@2@XZ; DirectUI::Element::ContentProp(void)
0x180070630  mov     r9, rax
0x180070633  mov     r8d, 1
0x180070639  mov     rcx, rdi
0x18007063c  call    cs:__imp_?SetValue@Element@DirectUI@@QEAAJP6APEBUPropertyInfo@2@XZHPEAVValue@2@@Z; DirectUI::Element::SetValue(DirectUI::PropertyInfo const * (*)(void),int,DirectUI::Value *)
0x180070642  mov     rcx, rsi
0x180070645  mov     ebx, eax
0x180070647  call    cs:__imp_?Release@Value@DirectUI@@QEAAXXZ; DirectUI::Value::Release(void)
0x18007064d  jmp     short loc_18007066E
0x18007064f  mov     rcx, rbx; ho
0x180070652  call    cs:__imp_DeleteObject
0x180070658  mov     ebx, 8007000Eh
0x18007065d  jmp     short loc_18007066E
0x18007065f  mov     rdx, cs:__imp_?ContentProp@Element@DirectUI@@SAPEBUPropertyInfo@2@XZ; DirectUI::Element::ContentProp(void)
0x180070666  call    cs:__imp_?RemoveLocalValue@Element@DirectUI@@QEAAJP6APEBUPropertyInfo@2@XZ@Z; DirectUI::Element::RemoveLocalValue(DirectUI::PropertyInfo const * (*)(void))
0x18007066c  mov     ebx, eax
0x18007066e  mov     rsi, [rsp+38h+arg_8]
0x180070673  mov     eax, ebx
0x180070675  mov     rbx, [rsp+38h+arg_0]
0x18007067a  add     rsp, 30h
0x18007067e  pop     rdi
0x18007067f  retn
```
