# DUI_SetElementBitmap(DirectUI::Element *,HBITMAP__ *,uchar,uint,ImageRtlMode,bool)

- ea: `0x18004f148`
- end: `0x18004f202`
- name: `?DUI_SetElementBitmap@@YAJPEAVElement@DirectUI@@PEAUHBITMAP__@@EIW4ImageRtlMode@@_N@Z`
- size: `186`
- prototype: `int __high(struct DirectUI::Element *, HBITMAP, unsigned __int8, unsigned int, enum ImageRtlMode, bool)`
- caller_count: `5`
- callee_count: `1`
- tags: ``

## callers

- `0x180022030`
- `0x180037b8c`
- `0x180037d68`
- `0x180038020`
- `0x180038924`

## callees

- `0x18004f148`

## import_xrefs

- `GDI32!DeleteObject` at `0x18004f1c7`
- `GDI32!DeleteObject` at `0x18004f1c7`
- `DUI70!?Release@Value@DirectUI@@QEAAXXZ` at `0x18004f1b6`
- `DUI70!?Release@Value@DirectUI@@QEAAXXZ` at `0x18004f1b6`
- `DUI70!?SetValue@Element@DirectUI@@QEAAJP6APEBUPropertyInfo@2@XZHPEAVValue@2@@Z` at `0x18004f1a5`
- `DUI70!?SetValue@Element@DirectUI@@QEAAJP6APEBUPropertyInfo@2@XZHPEAVValue@2@@Z` at `0x18004f1a5`
- `DUI70!?ContentProp@Element@DirectUI@@SAPEBUPropertyInfo@2@XZ` at `0x18004f192`
- `DUI70!?ContentProp@Element@DirectUI@@SAPEBUPropertyInfo@2@XZ` at `0x18004f1da`
- `DUI70!?CreateGraphic@Value@DirectUI@@SAPEAV12@PEAUHBITMAP__@@EI_N11@Z` at `0x18004f17e`
- `DUI70!?CreateGraphic@Value@DirectUI@@SAPEAV12@PEAUHBITMAP__@@EI_N11@Z` at `0x18004f17e`
- `DUI70!?RemoveLocalValue@Element@DirectUI@@QEAAJP6APEBUPropertyInfo@2@XZ@Z` at `0x18004f1e1`
- `DUI70!?RemoveLocalValue@Element@DirectUI@@QEAAJP6APEBUPropertyInfo@2@XZ@Z` at `0x18004f1e1`

## pseudocode

```c
__int64 __fastcall DUI_SetElementBitmap(DirectUI::Element *a1, HBITMAP a2, unsigned __int8 a3, unsigned int a4)
{
  struct DirectUI::Value *Graphic; // rax
  DirectUI::Value *v7; // rsi
  unsigned int v8; // ebx

  if ( a2 )
  {
    Graphic = DirectUI::Value::CreateGraphic(a2, a3, a4, 0, 0, 0);
    v7 = Graphic;
    if ( Graphic )
    {
      v8 = DirectUI::Element::SetValue(
             a1,
             (const struct DirectUI::PropertyInfo *(*)(void))DirectUI::Element::ContentProp,
             1,
             Graphic);
      DirectUI::Value::Release(v7);
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
  return v8;
}

```

## disassembly

```asm
0x18004f148  mov     [rsp+arg_0], rbx
0x18004f14d  mov     [rsp+arg_8], rsi
0x18004f152  push    rdi
0x18004f153  sub     rsp, 30h
0x18004f157  mov     eax, r9d
0x18004f15a  mov     r10b, r8b
0x18004f15d  mov     rbx, rdx
0x18004f160  mov     rdi, rcx
0x18004f163  test    rdx, rdx
0x18004f166  jz      short loc_18004F1DA
0x18004f168  mov     [rsp+38h+var_10], 0
0x18004f16d  xor     r9d, r9d
0x18004f170  mov     r8d, eax
0x18004f173  mov     [rsp+38h+var_18], 0
0x18004f178  mov     dl, r10b
0x18004f17b  mov     rcx, rbx
0x18004f17e  call    cs:__imp_?CreateGraphic@Value@DirectUI@@SAPEAV12@PEAUHBITMAP__@@EI_N11@Z; DirectUI::Value::CreateGraphic(HBITMAP__ *,uchar,uint,bool,bool,bool)
0x18004f185  nop     dword ptr [rax+rax+00h]
0x18004f18a  mov     rsi, rax
0x18004f18d  test    rax, rax
0x18004f190  jz      short loc_18004F1C4
0x18004f192  mov     rdx, cs:__imp_?ContentProp@Element@DirectUI@@SAPEBUPropertyInfo@2@XZ; DirectUI::Element::ContentProp(void)
0x18004f199  mov     r9, rax
0x18004f19c  mov     r8d, 1
0x18004f1a2  mov     rcx, rdi
0x18004f1a5  call    cs:__imp_?SetValue@Element@DirectUI@@QEAAJP6APEBUPropertyInfo@2@XZHPEAVValue@2@@Z; DirectUI::Element::SetValue(DirectUI::PropertyInfo const * (*)(void),int,DirectUI::Value *)
0x18004f1ac  nop     dword ptr [rax+rax+00h]
0x18004f1b1  mov     rcx, rsi
0x18004f1b4  mov     ebx, eax
0x18004f1b6  call    cs:__imp_?Release@Value@DirectUI@@QEAAXXZ; DirectUI::Value::Release(void)
0x18004f1bd  nop     dword ptr [rax+rax+00h]
0x18004f1c2  jmp     short loc_18004F1EF
0x18004f1c4  mov     rcx, rbx; ho
0x18004f1c7  call    cs:__imp_DeleteObject
0x18004f1ce  nop     dword ptr [rax+rax+00h]
0x18004f1d3  mov     ebx, 8007000Eh
0x18004f1d8  jmp     short loc_18004F1EF
0x18004f1da  mov     rdx, cs:__imp_?ContentProp@Element@DirectUI@@SAPEBUPropertyInfo@2@XZ; DirectUI::Element::ContentProp(void)
0x18004f1e1  call    cs:__imp_?RemoveLocalValue@Element@DirectUI@@QEAAJP6APEBUPropertyInfo@2@XZ@Z; DirectUI::Element::RemoveLocalValue(DirectUI::PropertyInfo const * (*)(void))
0x18004f1e8  nop     dword ptr [rax+rax+00h]
0x18004f1ed  mov     ebx, eax
0x18004f1ef  mov     rsi, [rsp+38h+arg_8]
0x18004f1f4  mov     eax, ebx
0x18004f1f6  mov     rbx, [rsp+38h+arg_0]
0x18004f1fb  add     rsp, 30h
0x18004f1ff  pop     rdi
0x18004f200  retn
```
