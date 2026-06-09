# CShareWithListItemBase::OnDestroy(void)

- ea: `0x18000b5e0`
- end: `0x18000b67b`
- name: `?OnDestroy@CShareWithListItemBase@@UEAAXXZ`
- size: `155`
- prototype: `void __fastcall(CShareWithListItemBase *__hidden this)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x18000b690`
- `0x18000b710`

## callees

- `0x180003860`
- `0x18000b5e0`

## import_xrefs

- `DUI70!?OnDestroy@Element@DirectUI@@UEAAXXZ` at `0x18000b643`
- `DUI70!?OnDestroy@Element@DirectUI@@UEAAXXZ` at `0x18000b643`
- `DUI70!?RemoveListener@Element@DirectUI@@QEAAXPEAUIElementListener@2@@Z` at `0x18000b63a`
- `DUI70!?RemoveListener@Element@DirectUI@@QEAAXPEAUIElementListener@2@@Z` at `0x18000b63a`

## pseudocode

```c
void __fastcall CShareWithListItemBase::OnDestroy(CShareWithListItemBase *this)
{
  DirectUI::Element *v2; // rcx

  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 167, &WPP_59386dd0a0913b67da6dc13cee28e88f_Traceguids);
  v2 = (DirectUI::Element *)*((_QWORD *)this + 26);
  if ( v2 )
    DirectUI::Element::RemoveListener(
      v2,
      (struct DirectUI::IElementListener *)(((unsigned __int64)this + 200)
                                          & ((unsigned __int128)-(__int128)(unsigned __int64)this >> 64)));
  DirectUI::Element::OnDestroy(this);
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 168, &WPP_59386dd0a0913b67da6dc13cee28e88f_Traceguids);
}

```

## disassembly

```asm
0x18000b5e0  mov     [rsp+arg_0], rbx
0x18000b5e5  push    rdi
0x18000b5e6  sub     rsp, 20h
0x18000b5ea  mov     rbx, rcx
0x18000b5ed  mov     rcx, cs:WPP_GLOBAL_Control
0x18000b5f4  lea     rdi, WPP_GLOBAL_Control
0x18000b5fb  cmp     rcx, rdi
0x18000b5fe  jz      short loc_18000B61B
0x18000b600  test    byte ptr [rcx+1Ch], 20h
0x18000b604  jz      short loc_18000B61B
0x18000b606  mov     rcx, [rcx+10h]
0x18000b60a  lea     r8, WPP_59386dd0a0913b67da6dc13cee28e88f_Traceguids
0x18000b611  mov     edx, 0A7h
0x18000b616  call    WPP_SF_
0x18000b61b  mov     rcx, [rbx+0D0h]
0x18000b622  test    rcx, rcx
0x18000b625  jz      short loc_18000B640
0x18000b627  lea     r8, [rbx+0C8h]
0x18000b62e  mov     rax, rbx
0x18000b631  neg     rax
0x18000b634  sbb     rdx, rdx
0x18000b637  and     rdx, r8
0x18000b63a  call    cs:__imp_?RemoveListener@Element@DirectUI@@QEAAXPEAUIElementListener@2@@Z; DirectUI::Element::RemoveListener(DirectUI::IElementListener *)
0x18000b640  mov     rcx, rbx
0x18000b643  call    cs:__imp_?OnDestroy@Element@DirectUI@@UEAAXXZ; DirectUI::Element::OnDestroy(void)
0x18000b649  mov     rcx, cs:WPP_GLOBAL_Control
0x18000b650  cmp     rcx, rdi
0x18000b653  jz      short loc_18000B670
0x18000b655  test    byte ptr [rcx+1Ch], 20h
0x18000b659  jz      short loc_18000B670
0x18000b65b  mov     rcx, [rcx+10h]
0x18000b65f  lea     r8, WPP_59386dd0a0913b67da6dc13cee28e88f_Traceguids
0x18000b666  mov     edx, 0A8h
0x18000b66b  call    WPP_SF_
0x18000b670  mov     rbx, [rsp+28h+arg_0]
0x18000b675  add     rsp, 20h
0x18000b679  pop     rdi
0x18000b67a  retn
```
