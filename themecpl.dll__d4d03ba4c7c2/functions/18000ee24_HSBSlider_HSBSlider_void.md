# HSBSlider::~HSBSlider(void)

- ea: `0x18000ee24`
- end: `0x18000ee91`
- name: `??1HSBSlider@@UEAA@XZ`
- size: `109`
- prototype: `void __fastcall(HSBSlider *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x18000eea0`

## callees

- `0x18000ee24`

## import_xrefs

- `GDI32!SelectObject` at `0x18000ee4f`
- `GDI32!SelectObject` at `0x18000ee4f`
- `GDI32!DeleteDC` at `0x18000ee71`
- `GDI32!DeleteDC` at `0x18000ee71`
- `GDI32!DeleteObject` at `0x18000ee5e`
- `GDI32!DeleteObject` at `0x18000ee5e`
- `DUI70!??1CCTrackBar@DirectUI@@UEAA@XZ` at `0x18000ee85`

## pseudocode

```c
void __fastcall HSBSlider::~HSBSlider(HSBSlider *this)
{
  HDC v2; // rcx
  void *v3; // rdx
  HGDIOBJ v4; // rax

  *(_QWORD *)this = &HSBSlider::`vftable';
  v2 = (HDC)*((_QWORD *)this + 51);
  if ( v2 )
  {
    v3 = (void *)*((_QWORD *)this + 52);
    if ( v3 )
    {
      v4 = SelectObject(v2, v3);
      DeleteObject(v4);
    }
    DeleteDC(*((HDC *)this + 51));
  }
  DirectUI::CCTrackBar::~CCTrackBar(this);
}

```

## disassembly

```asm
0x18000ee24  push    rbx
0x18000ee26  sub     rsp, 20h
0x18000ee2a  lea     rax, ??_7HSBSlider@@6B@; const HSBSlider::`vftable'
0x18000ee31  mov     rbx, rcx
0x18000ee34  mov     [rcx], rax
0x18000ee37  mov     rcx, [rcx+198h]; hdc
0x18000ee3e  test    rcx, rcx
0x18000ee41  jz      short loc_18000EE7D
0x18000ee43  mov     rdx, [rbx+1A0h]; h
0x18000ee4a  test    rdx, rdx
0x18000ee4d  jz      short loc_18000EE6A
0x18000ee4f  call    cs:__imp_SelectObject
0x18000ee56  nop     dword ptr [rax+rax+00h]
0x18000ee5b  mov     rcx, rax; ho
0x18000ee5e  call    cs:__imp_DeleteObject
0x18000ee65  nop     dword ptr [rax+rax+00h]
0x18000ee6a  mov     rcx, [rbx+198h]; hdc
0x18000ee71  call    cs:__imp_DeleteDC
0x18000ee78  nop     dword ptr [rax+rax+00h]
0x18000ee7d  mov     rcx, rbx
0x18000ee80  add     rsp, 20h
0x18000ee84  pop     rbx
0x18000ee85  jmp     cs:__imp_??1CCTrackBar@DirectUI@@UEAA@XZ; DirectUI::CCTrackBar::~CCTrackBar(void)
```
