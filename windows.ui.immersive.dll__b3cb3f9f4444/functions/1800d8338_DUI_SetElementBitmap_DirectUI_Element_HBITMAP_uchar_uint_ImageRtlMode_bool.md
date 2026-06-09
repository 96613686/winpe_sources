# DUI_SetElementBitmap(DirectUI::Element *,HBITMAP__ *,uchar,uint,ImageRtlMode,bool)

- ea: `0x1800d8338`
- end: `0x1800d83ef`
- name: `?DUI_SetElementBitmap@@YAJPEAVElement@DirectUI@@PEAUHBITMAP__@@EIW4ImageRtlMode@@_N@Z`
- size: `183`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x180094a20`
- `0x1800df110`

## callees

- `0x1800d8338`

## import_xrefs

- `GDI32!DeleteObject` at `0x1800d83b4`
- `GDI32!DeleteObject` at `0x1800d83b4`
- `DUI70!?RemoveLocalValue@Element@DirectUI@@QEAAJP6APEBUPropertyInfo@2@XZ@Z` at `0x1800d83ce`
- `DUI70!?RemoveLocalValue@Element@DirectUI@@QEAAJP6APEBUPropertyInfo@2@XZ@Z` at `0x1800d83ce`
- `DUI70!?CreateGraphic@Value@DirectUI@@SAPEAV12@PEAUHBITMAP__@@EI_N11@Z` at `0x1800d836b`
- `DUI70!?CreateGraphic@Value@DirectUI@@SAPEAV12@PEAUHBITMAP__@@EI_N11@Z` at `0x1800d836b`
- `DUI70!?ContentProp@Element@DirectUI@@SAPEBUPropertyInfo@2@XZ` at `0x1800d837f`
- `DUI70!?ContentProp@Element@DirectUI@@SAPEBUPropertyInfo@2@XZ` at `0x1800d83c7`
- `DUI70!?Release@Value@DirectUI@@QEAAXXZ` at `0x1800d83a3`
- `DUI70!?Release@Value@DirectUI@@QEAAXXZ` at `0x1800d83a3`
- `DUI70!?SetValue@Element@DirectUI@@QEAAJP6APEBUPropertyInfo@2@XZHPEAVValue@2@@Z` at `0x1800d8392`
- `DUI70!?SetValue@Element@DirectUI@@QEAAJP6APEBUPropertyInfo@2@XZHPEAVValue@2@@Z` at `0x1800d8392`

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
0x1800d8338  mov     [rsp+arg_0], rbx
0x1800d833d  mov     [rsp+arg_8], rsi
0x1800d8342  push    rdi
0x1800d8343  sub     rsp, 30h
0x1800d8347  mov     al, r8b
0x1800d834a  mov     rbx, rdx
0x1800d834d  mov     rdi, rcx
0x1800d8350  test    rdx, rdx
0x1800d8353  jz      short loc_1800D83C7
0x1800d8355  mov     [rsp+38h+var_10], 0
0x1800d835a  xor     r9d, r9d
0x1800d835d  or      r8d, 0FFFFFFFFh
0x1800d8361  mov     [rsp+38h+var_18], 0
0x1800d8366  mov     dl, al
0x1800d8368  mov     rcx, rbx
0x1800d836b  call    cs:__imp_?CreateGraphic@Value@DirectUI@@SAPEAV12@PEAUHBITMAP__@@EI_N11@Z; DirectUI::Value::CreateGraphic(HBITMAP__ *,uchar,uint,bool,bool,bool)
0x1800d8372  nop     dword ptr [rax+rax+00h]
0x1800d8377  mov     rsi, rax
0x1800d837a  test    rax, rax
0x1800d837d  jz      short loc_1800D83B1
0x1800d837f  mov     rdx, cs:__imp_?ContentProp@Element@DirectUI@@SAPEBUPropertyInfo@2@XZ; DirectUI::Element::ContentProp(void)
0x1800d8386  mov     r9, rax
0x1800d8389  mov     r8d, 1
0x1800d838f  mov     rcx, rdi
0x1800d8392  call    cs:__imp_?SetValue@Element@DirectUI@@QEAAJP6APEBUPropertyInfo@2@XZHPEAVValue@2@@Z; DirectUI::Element::SetValue(DirectUI::PropertyInfo const * (*)(void),int,DirectUI::Value *)
0x1800d8399  nop     dword ptr [rax+rax+00h]
0x1800d839e  mov     rcx, rsi
0x1800d83a1  mov     ebx, eax
0x1800d83a3  call    cs:__imp_?Release@Value@DirectUI@@QEAAXXZ; DirectUI::Value::Release(void)
0x1800d83aa  nop     dword ptr [rax+rax+00h]
0x1800d83af  jmp     short loc_1800D83DC
0x1800d83b1  mov     rcx, rbx; ho
0x1800d83b4  call    cs:__imp_DeleteObject
0x1800d83bb  nop     dword ptr [rax+rax+00h]
0x1800d83c0  mov     ebx, 8007000Eh
0x1800d83c5  jmp     short loc_1800D83DC
0x1800d83c7  mov     rdx, cs:__imp_?ContentProp@Element@DirectUI@@SAPEBUPropertyInfo@2@XZ; DirectUI::Element::ContentProp(void)
0x1800d83ce  call    cs:__imp_?RemoveLocalValue@Element@DirectUI@@QEAAJP6APEBUPropertyInfo@2@XZ@Z; DirectUI::Element::RemoveLocalValue(DirectUI::PropertyInfo const * (*)(void))
0x1800d83d5  nop     dword ptr [rax+rax+00h]
0x1800d83da  mov     ebx, eax
0x1800d83dc  mov     rsi, [rsp+38h+arg_8]
0x1800d83e1  mov     eax, ebx
0x1800d83e3  mov     rbx, [rsp+38h+arg_0]
0x1800d83e8  add     rsp, 30h
0x1800d83ec  pop     rdi
0x1800d83ed  retn
```
