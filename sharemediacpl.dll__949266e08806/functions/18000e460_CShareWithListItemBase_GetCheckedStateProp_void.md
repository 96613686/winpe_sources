# CShareWithListItemBase::_GetCheckedStateProp(void)

- ea: `0x18000e460`
- end: `0x18000e49c`
- name: `?_GetCheckedStateProp@CShareWithListItemBase@@IEAA_NXZ`
- size: `60`
- prototype: `bool __fastcall(CShareWithListItemBase *__hidden this)`
- caller_count: `3`
- callee_count: `1`
- tags: `installer_update`

## callers

- `0x18000ba80`
- `0x18000ef20`
- `0x1800119e0`

## callees

- `0x18000e460`

## import_xrefs

- `DUI70!?GetValue@Element@DirectUI@@QEAAPEAVValue@2@PEBUPropertyInfo@2@HPEAUUpdateCache@2@@Z` at `0x18000e482`
- `DUI70!?GetValue@Element@DirectUI@@QEAAPEAVValue@2@PEBUPropertyInfo@2@HPEAUUpdateCache@2@@Z` at `0x18000e482`
- `DUI70!?Release@Value@DirectUI@@QEAAXXZ` at `0x18000e48e`
- `DUI70!?Release@Value@DirectUI@@QEAAXXZ` at `0x18000e48e`

## pseudocode

```c
char __fastcall CShareWithListItemBase::_GetCheckedStateProp(CShareWithListItemBase *this)
{
  DirectUI::Element *v1; // rcx
  char v2; // bl
  struct DirectUI::Value *Value; // rax

  v1 = (DirectUI::Element *)*((_QWORD *)this + 26);
  v2 = 0;
  if ( v1 )
  {
    Value = DirectUI::Element::GetValue(v1, (const struct DirectUI::PropertyInfo *)&off_18002A090, 2, 0);
    v2 = *((_BYTE *)Value + 8);
    DirectUI::Value::Release(Value);
  }
  return v2;
}

```

## disassembly

```asm
0x18000e460  push    rbx
0x18000e462  sub     rsp, 20h
0x18000e466  mov     rcx, [rcx+0D0h]
0x18000e46d  xor     bl, bl
0x18000e46f  test    rcx, rcx
0x18000e472  jz      short loc_18000E494
0x18000e474  xor     r9d, r9d
0x18000e477  lea     rdx, off_18002A090; "Checked"
0x18000e47e  lea     r8d, [r9+2]
0x18000e482  call    cs:__imp_?GetValue@Element@DirectUI@@QEAAPEAVValue@2@PEBUPropertyInfo@2@HPEAUUpdateCache@2@@Z; DirectUI::Element::GetValue(DirectUI::PropertyInfo const *,int,DirectUI::UpdateCache *)
0x18000e488  mov     rcx, rax
0x18000e48b  mov     bl, [rax+8]
0x18000e48e  call    cs:__imp_?Release@Value@DirectUI@@QEAAXXZ; DirectUI::Value::Release(void)
0x18000e494  mov     al, bl
0x18000e496  add     rsp, 20h
0x18000e49a  pop     rbx
0x18000e49b  retn
```
