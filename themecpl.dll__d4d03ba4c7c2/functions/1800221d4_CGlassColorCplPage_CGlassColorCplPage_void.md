# CGlassColorCplPage::CGlassColorCplPage(void)

- ea: `0x1800221d4`
- end: `0x1800222b9`
- name: `??0CGlassColorCplPage@@QEAA@XZ`
- size: `229`
- prototype: `CGlassColorCplPage *__fastcall(CGlassColorCplPage *__hidden this)`
- caller_count: `1`
- callee_count: `0`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x1800224c0`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800222a3`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800222a3`
- `DUI70!??0Element@DirectUI@@QEAA@XZ` at `0x1800221dd`
- `DUI70!??0Element@DirectUI@@QEAA@XZ` at `0x1800221dd`

## pseudocode

```c
CGlassColorCplPage *__fastcall CGlassColorCplPage::CGlassColorCplPage(CGlassColorCplPage *this)
{
  DirectUI::Element::Element(this);
  *((_BYTE *)this + 296) = 1;
  *(_QWORD *)this = &CGlassColorCplPage::`vftable'{for `DirectUI::Element'};
  *((_QWORD *)this + 25) = &CGlassColorCplPage::`vftable'{for `DirectUI::IElementListener'};
  *((_QWORD *)this + 26) = &CGlassColorCplPage::`vftable'{for `CColorCplPageHandler'};
  *((_QWORD *)this + 27) = 0;
  *((_QWORD *)this + 29) = 0;
  *((_QWORD *)this + 30) = 0;
  *((_QWORD *)this + 31) = 0;
  *((_QWORD *)this + 32) = 0;
  *((_QWORD *)this + 33) = 0;
  *((_QWORD *)this + 34) = 0;
  *((_QWORD *)this + 35) = 0;
  *(_WORD *)((char *)this + 289) = 0;
  *((_DWORD *)this + 73) = 0;
  *((_DWORD *)this + 75) = 0;
  *((_BYTE *)this + 304) = 0;
  *((_DWORD *)this + 77) = 0;
  *((_BYTE *)this + 312) = 0;
  *((_QWORD *)this + 40) = 0;
  *((_QWORD *)this + 41) = 0;
  CoCreateInstance(&CLSID_DesktopWallpaper, 0, 4u, &GUID_c182461f_dfac_4375_ab6e_4cc45aa7f9cc, (LPVOID *)this + 42);
  return this;
}

```

## disassembly

```asm
0x1800221d4  push    rbx
0x1800221d6  sub     rsp, 30h
0x1800221da  mov     rbx, rcx
0x1800221dd  call    cs:__imp_??0Element@DirectUI@@QEAA@XZ; DirectUI::Element::Element(void)
0x1800221e4  nop     dword ptr [rax+rax+00h]
0x1800221e9  mov     byte ptr [rbx+128h], 1
0x1800221f0  lea     rax, ??_7CGlassColorCplPage@@6BElement@DirectUI@@@; const CGlassColorCplPage::`vftable'{for `DirectUI::Element'}
0x1800221f7  mov     [rbx], rax
0x1800221fa  lea     r9, _GUID_c182461f_dfac_4375_ab6e_4cc45aa7f9cc; riid
0x180022201  lea     rax, ??_7CGlassColorCplPage@@6BIElementListener@DirectUI@@@; const CGlassColorCplPage::`vftable'{for `DirectUI::IElementListener'}
0x180022208  xor     edx, edx; pUnkOuter
0x18002220a  mov     [rbx+0C8h], rax
0x180022211  lea     rcx, CLSID_DesktopWallpaper; rclsid
0x180022218  lea     rax, ??_7CGlassColorCplPage@@6BCColorCplPageHandler@@@; const CGlassColorCplPage::`vftable'{for `CColorCplPageHandler'}
0x18002221f  mov     [rbx+0D0h], rax
0x180022226  xor     eax, eax
0x180022228  mov     [rbx+0D8h], rax
0x18002222f  lea     r8d, [rdx+4]; dwClsContext
0x180022233  mov     [rbx+0E8h], rax
0x18002223a  mov     [rbx+0F0h], rax
0x180022241  mov     [rbx+0F8h], rax
0x180022248  mov     [rbx+100h], rax
0x18002224f  mov     [rbx+108h], rax
0x180022256  mov     [rbx+110h], rax
0x18002225d  mov     [rbx+118h], rax
0x180022264  mov     [rbx+121h], ax
0x18002226b  mov     [rbx+124h], eax
0x180022271  mov     [rbx+12Ch], eax
0x180022277  mov     [rbx+130h], al
0x18002227d  mov     [rbx+134h], eax
0x180022283  mov     [rbx+138h], al
0x180022289  mov     [rbx+140h], rax
0x180022290  mov     [rbx+148h], rax
0x180022297  lea     rax, [rbx+150h]
0x18002229e  mov     [rsp+38h+ppv], rax; ppv
0x1800222a3  call    cs:__imp_CoCreateInstance
0x1800222aa  nop     dword ptr [rax+rax+00h]
0x1800222af  mov     rax, rbx
0x1800222b2  add     rsp, 30h
0x1800222b6  pop     rbx
0x1800222b7  retn
```
