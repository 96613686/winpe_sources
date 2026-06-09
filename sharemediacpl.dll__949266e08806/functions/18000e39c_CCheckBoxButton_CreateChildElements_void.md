# CCheckBoxButton::_CreateChildElements(void)

- ea: `0x18000e39c`
- end: `0x18000e457`
- name: `?_CreateChildElements@CCheckBoxButton@@AEAAJXZ`
- size: `187`
- prototype: `__int64 __fastcall(CCheckBoxButton *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180009600`

## callees

- `0x18000e39c`

## import_xrefs

- `DUI70!?Destroy@Element@DirectUI@@QEAAJ_N@Z` at `0x18000e43f`
- `DUI70!?Destroy@Element@DirectUI@@QEAAJ_N@Z` at `0x18000e43f`
- `DUI70!?Add@Element@DirectUI@@QEAAJPEAV12@@Z` at `0x18000e3e8`
- `DUI70!?Add@Element@DirectUI@@QEAAJPEAV12@@Z` at `0x18000e42e`
- `DUI70!?Add@Element@DirectUI@@QEAAJPEAV12@@Z` at `0x18000e3e8`
- `DUI70!?Add@Element@DirectUI@@QEAAJPEAV12@@Z` at `0x18000e42e`
- `DUI70!?SetID@Element@DirectUI@@QEAAJPEBG@Z` at `0x18000e3d6`
- `DUI70!?SetID@Element@DirectUI@@QEAAJPEBG@Z` at `0x18000e41c`
- `DUI70!?SetID@Element@DirectUI@@QEAAJPEBG@Z` at `0x18000e3d6`
- `DUI70!?SetID@Element@DirectUI@@QEAAJPEBG@Z` at `0x18000e41c`
- `DUI70!?Create@Element@DirectUI@@SAJIPEAV12@PEAKPEAPEAV12@@Z` at `0x18000e3c0`
- `DUI70!?Create@Element@DirectUI@@SAJIPEAV12@PEAKPEAPEAV12@@Z` at `0x18000e406`
- `DUI70!?Create@Element@DirectUI@@SAJIPEAV12@PEAKPEAPEAV12@@Z` at `0x18000e3c0`
- `DUI70!?Create@Element@DirectUI@@SAJIPEAV12@PEAKPEAPEAV12@@Z` at `0x18000e406`

## pseudocode

```c
__int64 __fastcall CCheckBoxButton::_CreateChildElements(struct DirectUI::Element **this)
{
  DirectUI::Element **v1; // rsi
  int v3; // ebx

  v1 = this + 26;
  v3 = DirectUI::Element::Create(0, (struct DirectUI::Element *)this, 0, this + 26);
  if ( v3 >= 0 )
  {
    v3 = DirectUI::Element::SetID(*v1, L"CheckBoxGlyph");
    if ( v3 < 0
      || (v3 = DirectUI::Element::Add((DirectUI::Element *)this, *v1), v3 < 0)
      || (v1 = this + 27, v3 = DirectUI::Element::Create(0, (struct DirectUI::Element *)this, 0, this + 27), v3 >= 0)
      && ((v3 = DirectUI::Element::SetID(*v1, L"CheckBoxLabel"), v3 < 0)
       || (v3 = DirectUI::Element::Add((DirectUI::Element *)this, *v1), v3 < 0)) )
    {
      DirectUI::Element::Destroy(*v1, 0);
    }
  }
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x18000e39c  mov     [rsp+arg_0], rbx
0x18000e3a1  mov     [rsp+arg_8], rsi
0x18000e3a6  push    rdi
0x18000e3a7  sub     rsp, 20h
0x18000e3ab  lea     rsi, [rcx+0D0h]
0x18000e3b2  mov     rdi, rcx
0x18000e3b5  mov     rdx, rcx
0x18000e3b8  mov     r9, rsi
0x18000e3bb  xor     r8d, r8d
0x18000e3be  xor     ecx, ecx
0x18000e3c0  call    cs:__imp_?Create@Element@DirectUI@@SAJIPEAV12@PEAKPEAPEAV12@@Z; DirectUI::Element::Create(uint,DirectUI::Element *,ulong *,DirectUI::Element * *)
0x18000e3c6  mov     ebx, eax
0x18000e3c8  test    eax, eax
0x18000e3ca  js      short loc_18000E445
0x18000e3cc  mov     rcx, [rsi]
0x18000e3cf  lea     rdx, aCheckboxglyph; "CheckBoxGlyph"
0x18000e3d6  call    cs:__imp_?SetID@Element@DirectUI@@QEAAJPEBG@Z; DirectUI::Element::SetID(ushort const *)
0x18000e3dc  mov     ebx, eax
0x18000e3de  test    eax, eax
0x18000e3e0  js      short loc_18000E43A
0x18000e3e2  mov     rdx, [rsi]
0x18000e3e5  mov     rcx, rdi
0x18000e3e8  call    cs:__imp_?Add@Element@DirectUI@@QEAAJPEAV12@@Z; DirectUI::Element::Add(DirectUI::Element *)
0x18000e3ee  mov     ebx, eax
0x18000e3f0  test    eax, eax
0x18000e3f2  js      short loc_18000E43A
0x18000e3f4  lea     rsi, [rdi+0D8h]
0x18000e3fb  xor     r8d, r8d
0x18000e3fe  mov     r9, rsi
0x18000e401  mov     rdx, rdi
0x18000e404  xor     ecx, ecx
0x18000e406  call    cs:__imp_?Create@Element@DirectUI@@SAJIPEAV12@PEAKPEAPEAV12@@Z; DirectUI::Element::Create(uint,DirectUI::Element *,ulong *,DirectUI::Element * *)
0x18000e40c  mov     ebx, eax
0x18000e40e  test    eax, eax
0x18000e410  js      short loc_18000E445
0x18000e412  mov     rcx, [rsi]
0x18000e415  lea     rdx, aCheckboxlabel; "CheckBoxLabel"
0x18000e41c  call    cs:__imp_?SetID@Element@DirectUI@@QEAAJPEBG@Z; DirectUI::Element::SetID(ushort const *)
0x18000e422  mov     ebx, eax
0x18000e424  test    eax, eax
0x18000e426  js      short loc_18000E43A
0x18000e428  mov     rdx, [rsi]
0x18000e42b  mov     rcx, rdi
0x18000e42e  call    cs:__imp_?Add@Element@DirectUI@@QEAAJPEAV12@@Z; DirectUI::Element::Add(DirectUI::Element *)
0x18000e434  mov     ebx, eax
0x18000e436  test    eax, eax
0x18000e438  jns     short loc_18000E445
0x18000e43a  mov     rcx, [rsi]
0x18000e43d  xor     edx, edx
0x18000e43f  call    cs:__imp_?Destroy@Element@DirectUI@@QEAAJ_N@Z; DirectUI::Element::Destroy(bool)
0x18000e445  mov     rsi, [rsp+28h+arg_8]
0x18000e44a  mov     eax, ebx
0x18000e44c  mov     rbx, [rsp+28h+arg_0]
0x18000e451  add     rsp, 20h
0x18000e455  pop     rdi
0x18000e456  retn
```
