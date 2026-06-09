# CGlassColorCplPage::OnDestroy(void)

- ea: `0x180022bc0`
- end: `0x180022ca1`
- name: `?OnDestroy@CGlassColorCplPage@@UEAAXXZ`
- size: `225`
- prototype: `void __fastcall(CGlassColorCplPage *__hidden this)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x180022bc0`

## import_xrefs

- `DUI70!?OnDestroy@Element@DirectUI@@UEAAXXZ` at `0x180022c95`
- `DUI70!?RemoveListener@Element@DirectUI@@QEAAXPEAUIElementListener@2@@Z` at `0x180022bec`
- `DUI70!?RemoveListener@Element@DirectUI@@QEAAXPEAUIElementListener@2@@Z` at `0x180022c10`
- `DUI70!?RemoveListener@Element@DirectUI@@QEAAXPEAUIElementListener@2@@Z` at `0x180022c34`
- `DUI70!?RemoveListener@Element@DirectUI@@QEAAXPEAUIElementListener@2@@Z` at `0x180022c58`
- `DUI70!?RemoveListener@Element@DirectUI@@QEAAXPEAUIElementListener@2@@Z` at `0x180022c7c`
- `DUI70!?RemoveListener@Element@DirectUI@@QEAAXPEAUIElementListener@2@@Z` at `0x180022bec`
- `DUI70!?RemoveListener@Element@DirectUI@@QEAAXPEAUIElementListener@2@@Z` at `0x180022c10`
- `DUI70!?RemoveListener@Element@DirectUI@@QEAAXPEAUIElementListener@2@@Z` at `0x180022c34`
- `DUI70!?RemoveListener@Element@DirectUI@@QEAAXPEAUIElementListener@2@@Z` at `0x180022c58`
- `DUI70!?RemoveListener@Element@DirectUI@@QEAAXPEAUIElementListener@2@@Z` at `0x180022c7c`

## pseudocode

```c
void __fastcall CGlassColorCplPage::OnDestroy(CGlassColorCplPage *this)
{
  DirectUI::Element *v2; // rcx
  unsigned __int64 v3; // rdi
  DirectUI::Element *v4; // rcx
  DirectUI::Element *v5; // rcx
  DirectUI::Element *v6; // rcx
  DirectUI::Element *v7; // rcx

  v2 = (DirectUI::Element *)*((_QWORD *)this + 27);
  v3 = (unsigned __int64)this + 200;
  if ( v2 )
    DirectUI::Element::RemoveListener(
      v2,
      (struct DirectUI::IElementListener *)(v3 & ((unsigned __int128)-(__int128)(unsigned __int64)this >> 64)));
  v4 = (DirectUI::Element *)*((_QWORD *)this + 32);
  if ( v4 )
    DirectUI::Element::RemoveListener(
      v4,
      (struct DirectUI::IElementListener *)(v3 & ((unsigned __int128)-(__int128)(unsigned __int64)this >> 64)));
  v5 = (DirectUI::Element *)*((_QWORD *)this + 33);
  if ( v5 )
    DirectUI::Element::RemoveListener(
      v5,
      (struct DirectUI::IElementListener *)(v3 & ((unsigned __int128)-(__int128)(unsigned __int64)this >> 64)));
  v6 = (DirectUI::Element *)*((_QWORD *)this + 34);
  if ( v6 )
    DirectUI::Element::RemoveListener(
      v6,
      (struct DirectUI::IElementListener *)(v3 & ((unsigned __int128)-(__int128)(unsigned __int64)this >> 64)));
  v7 = (DirectUI::Element *)*((_QWORD *)this + 29);
  if ( v7 )
    DirectUI::Element::RemoveListener(
      v7,
      (struct DirectUI::IElementListener *)(v3 & ((unsigned __int128)-(__int128)(unsigned __int64)this >> 64)));
  DirectUI::Element::OnDestroy(this);
}

```

## disassembly

```asm
0x180022bc0  mov     [rsp+arg_0], rbx
0x180022bc5  push    rdi
0x180022bc6  sub     rsp, 20h
0x180022bca  mov     rbx, rcx
0x180022bcd  mov     rcx, [rcx+0D8h]
0x180022bd4  lea     rdi, [rbx+0C8h]
0x180022bdb  test    rcx, rcx
0x180022bde  jz      short loc_180022BF8
0x180022be0  mov     rax, rbx
0x180022be3  neg     rax
0x180022be6  sbb     rdx, rdx
0x180022be9  and     rdx, rdi
0x180022bec  call    cs:__imp_?RemoveListener@Element@DirectUI@@QEAAXPEAUIElementListener@2@@Z; DirectUI::Element::RemoveListener(DirectUI::IElementListener *)
0x180022bf3  nop     dword ptr [rax+rax+00h]
0x180022bf8  mov     rcx, [rbx+100h]
0x180022bff  test    rcx, rcx
0x180022c02  jz      short loc_180022C1C
0x180022c04  mov     rax, rbx
0x180022c07  neg     rax
0x180022c0a  sbb     rdx, rdx
0x180022c0d  and     rdx, rdi
0x180022c10  call    cs:__imp_?RemoveListener@Element@DirectUI@@QEAAXPEAUIElementListener@2@@Z; DirectUI::Element::RemoveListener(DirectUI::IElementListener *)
0x180022c17  nop     dword ptr [rax+rax+00h]
0x180022c1c  mov     rcx, [rbx+108h]
0x180022c23  test    rcx, rcx
0x180022c26  jz      short loc_180022C40
0x180022c28  mov     rax, rbx
0x180022c2b  neg     rax
0x180022c2e  sbb     rdx, rdx
0x180022c31  and     rdx, rdi
0x180022c34  call    cs:__imp_?RemoveListener@Element@DirectUI@@QEAAXPEAUIElementListener@2@@Z; DirectUI::Element::RemoveListener(DirectUI::IElementListener *)
0x180022c3b  nop     dword ptr [rax+rax+00h]
0x180022c40  mov     rcx, [rbx+110h]
0x180022c47  test    rcx, rcx
0x180022c4a  jz      short loc_180022C64
0x180022c4c  mov     rax, rbx
0x180022c4f  neg     rax
0x180022c52  sbb     rdx, rdx
0x180022c55  and     rdx, rdi
0x180022c58  call    cs:__imp_?RemoveListener@Element@DirectUI@@QEAAXPEAUIElementListener@2@@Z; DirectUI::Element::RemoveListener(DirectUI::IElementListener *)
0x180022c5f  nop     dword ptr [rax+rax+00h]
0x180022c64  mov     rcx, [rbx+0E8h]
0x180022c6b  test    rcx, rcx
0x180022c6e  jz      short loc_180022C88
0x180022c70  mov     rax, rbx
0x180022c73  neg     rax
0x180022c76  sbb     rdx, rdx
0x180022c79  and     rdx, rdi
0x180022c7c  call    cs:__imp_?RemoveListener@Element@DirectUI@@QEAAXPEAUIElementListener@2@@Z; DirectUI::Element::RemoveListener(DirectUI::IElementListener *)
0x180022c83  nop     dword ptr [rax+rax+00h]
0x180022c88  mov     rcx, rbx
0x180022c8b  mov     rbx, [rsp+28h+arg_0]
0x180022c90  add     rsp, 20h
0x180022c94  pop     rdi
0x180022c95  jmp     cs:__imp_?OnDestroy@Element@DirectUI@@UEAAXXZ; DirectUI::Element::OnDestroy(void)
```
