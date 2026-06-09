# CShareWithListItemBase::_SetCheckedStateProp(bool)

- ea: `0x1800108b8`
- end: `0x18001090b`
- name: `?_SetCheckedStateProp@CShareWithListItemBase@@IEAAX_N@Z`
- size: `83`
- prototype: `void __fastcall(CShareWithListItemBase *__hidden this, bool)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x18000ba80`
- `0x18000e4b0`
- `0x1800119e0`

## callees

- `0x1800108b8`

## import_xrefs

- `DUI70!?SetValue@Element@DirectUI@@QEAAJPEBUPropertyInfo@2@HPEAVValue@2@@Z` at `0x1800108f1`
- `DUI70!?SetValue@Element@DirectUI@@QEAAJPEBUPropertyInfo@2@HPEAVValue@2@@Z` at `0x1800108f1`
- `DUI70!?CreateBool@Value@DirectUI@@SAPEAV12@_N@Z` at `0x1800108d0`
- `DUI70!?CreateBool@Value@DirectUI@@SAPEAV12@_N@Z` at `0x1800108d0`
- `DUI70!?Release@Value@DirectUI@@QEAAXXZ` at `0x1800108fa`
- `DUI70!?Release@Value@DirectUI@@QEAAXXZ` at `0x1800108fa`

## pseudocode

```c
void __fastcall CShareWithListItemBase::_SetCheckedStateProp(CShareWithListItemBase *this, bool a2)
{
  DirectUI::Element *v2; // rdi
  struct DirectUI::Value *Bool; // rax
  DirectUI::Value *v4; // rbx

  v2 = (DirectUI::Element *)*((_QWORD *)this + 26);
  if ( v2 )
  {
    Bool = DirectUI::Value::CreateBool(a2);
    v4 = Bool;
    if ( Bool )
    {
      DirectUI::Element::SetValue(v2, (const struct DirectUI::PropertyInfo *)&off_18002A090, 1, Bool);
      DirectUI::Value::Release(v4);
    }
  }
}

```

## disassembly

```asm
0x1800108b8  mov     [rsp+arg_0], rbx
0x1800108bd  push    rdi
0x1800108be  sub     rsp, 20h
0x1800108c2  mov     rdi, [rcx+0D0h]
0x1800108c9  test    rdi, rdi
0x1800108cc  jz      short loc_180010900
0x1800108ce  mov     cl, dl
0x1800108d0  call    cs:__imp_?CreateBool@Value@DirectUI@@SAPEAV12@_N@Z; DirectUI::Value::CreateBool(bool)
0x1800108d6  mov     rbx, rax
0x1800108d9  test    rax, rax
0x1800108dc  jz      short loc_180010900
0x1800108de  mov     r9, rax
0x1800108e1  lea     rdx, off_18002A090; "Checked"
0x1800108e8  mov     r8d, 1
0x1800108ee  mov     rcx, rdi
0x1800108f1  call    cs:__imp_?SetValue@Element@DirectUI@@QEAAJPEBUPropertyInfo@2@HPEAVValue@2@@Z; DirectUI::Element::SetValue(DirectUI::PropertyInfo const *,int,DirectUI::Value *)
0x1800108f7  mov     rcx, rbx
0x1800108fa  call    cs:__imp_?Release@Value@DirectUI@@QEAAXXZ; DirectUI::Value::Release(void)
0x180010900  mov     rbx, [rsp+28h+arg_0]
0x180010905  add     rsp, 20h
0x180010909  pop     rdi
0x18001090a  retn
```
