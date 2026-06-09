# CShareWithListItemBase::OnPropertyChanged(DirectUI::PropertyInfo const *,int,DirectUI::Value *,DirectUI::Value *)

- ea: `0x18000bfa0`
- end: `0x18000c13e`
- name: `?OnPropertyChanged@CShareWithListItemBase@@UEAAXPEBUPropertyInfo@DirectUI@@HPEAVValue@3@1@Z`
- size: `414`
- prototype: `void __fastcall(CShareWithListItemBase *__hidden this, const struct DirectUI::PropertyInfo *, int, struct DirectUI::Value *, struct DirectUI::Value *)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x18000bfa0`
- `0x18001e010`

## import_xrefs

- `DUI70!?OnPropertyChanged@Element@DirectUI@@UEAAXPEBUPropertyInfo@2@HPEAVValue@2@1@Z` at `0x18000c137`
- `DUI70!?SetVisible@Element@DirectUI@@QEAAJ_N@Z` at `0x18000c089`
- `DUI70!?SetVisible@Element@DirectUI@@QEAAJ_N@Z` at `0x18000c0ee`
- `DUI70!?SetVisible@Element@DirectUI@@QEAAJ_N@Z` at `0x18000c11b`
- `DUI70!?SetVisible@Element@DirectUI@@QEAAJ_N@Z` at `0x18000c089`
- `DUI70!?SetVisible@Element@DirectUI@@QEAAJ_N@Z` at `0x18000c0ee`
- `DUI70!?SetVisible@Element@DirectUI@@QEAAJ_N@Z` at `0x18000c11b`
- `DUI70!?SelectedProp@Element@DirectUI@@SAPEBUPropertyInfo@2@XZ` at `0x18000bff7`
- `DUI70!?SelectedProp@Element@DirectUI@@SAPEBUPropertyInfo@2@XZ` at `0x18000bff7`
- `DUI70!?MouseFocusedProp@Element@DirectUI@@SAPEBUPropertyInfo@2@XZ` at `0x18000bfe3`
- `DUI70!?MouseFocusedProp@Element@DirectUI@@SAPEBUPropertyInfo@2@XZ` at `0x18000bfe3`
- `DUI70!?MouseWithinProp@Element@DirectUI@@SAPEBUPropertyInfo@2@XZ` at `0x18000bfcf`
- `DUI70!?MouseWithinProp@Element@DirectUI@@SAPEBUPropertyInfo@2@XZ` at `0x18000bfcf`
- `DUI70!?KeyFocusedProp@Element@DirectUI@@SAPEBUPropertyInfo@2@XZ` at `0x18000bfbb`
- `DUI70!?KeyFocusedProp@Element@DirectUI@@SAPEBUPropertyInfo@2@XZ` at `0x18000bfbb`
- `DUI70!StrToID` at `0x18000c04b`
- `DUI70!StrToID` at `0x18000c072`
- `DUI70!StrToID` at `0x18000c096`
- `DUI70!StrToID` at `0x18000c0b3`
- `DUI70!StrToID` at `0x18000c0d7`
- `DUI70!StrToID` at `0x18000c104`
- `DUI70!StrToID` at `0x18000c04b`
- `DUI70!StrToID` at `0x18000c072`
- `DUI70!StrToID` at `0x18000c096`
- `DUI70!StrToID` at `0x18000c0b3`
- `DUI70!StrToID` at `0x18000c0d7`
- `DUI70!StrToID` at `0x18000c104`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x18000c057`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x18000c07e`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x18000c0a2`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x18000c0bf`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x18000c0e3`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x18000c110`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x18000c057`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x18000c07e`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x18000c0a2`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x18000c0bf`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x18000c0e3`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x18000c110`
- `DUI70!?SetLayoutPos@Element@DirectUI@@QEAAJH@Z` at `0x18000c065`
- `DUI70!?SetLayoutPos@Element@DirectUI@@QEAAJH@Z` at `0x18000c0ca`
- `DUI70!?SetLayoutPos@Element@DirectUI@@QEAAJH@Z` at `0x18000c065`
- `DUI70!?SetLayoutPos@Element@DirectUI@@QEAAJH@Z` at `0x18000c0ca`

## string_xrefs

- `0x18000c06b`: `CustomizeDeviceLink`
- `0x18000c0d0`: `CustomizeDeviceLink`
- `0x18000c044`: `CustomizeRemoveLinkArea`
- `0x18000c0ac`: `CustomizeRemoveLinkArea`
- `0x18000c08f`: `RemovePlayerLink`
- `0x18000c0fd`: `RemovePlayerLink`

## pseudocode

```c
void __fastcall CShareWithListItemBase::OnPropertyChanged(
        CShareWithListItemBase *this,
        const struct DirectUI::PropertyInfo *a2,
        int a3,
        struct DirectUI::Value *a4,
        struct DirectUI::Value *a5)
{
  _DWORD *v6; // rdi
  unsigned __int16 v10; // ax
  DirectUI::Element *Descendent; // rax
  unsigned __int16 v12; // ax
  DirectUI::Element *v13; // rax
  unsigned __int16 v14; // ax
  DirectUI::Element *v15; // rax
  bool v16; // dl
  unsigned __int16 v17; // ax
  DirectUI::Element *v18; // rax
  unsigned __int16 v19; // ax
  DirectUI::Element *v20; // rax
  unsigned __int16 v21; // ax

  v6 = (_DWORD *)((char *)a2 + 8);
  if ( a2 == (const struct DirectUI::PropertyInfo *)DirectUI::Element::KeyFocusedProp() && (*v6 & 3) == a3
    || a2 == (const struct DirectUI::PropertyInfo *)DirectUI::Element::MouseWithinProp() && (*v6 & 3) == a3
    || a2 == (const struct DirectUI::PropertyInfo *)DirectUI::Element::MouseFocusedProp() && (*v6 & 3) == a3
    || a2 == (const struct DirectUI::PropertyInfo *)DirectUI::Element::SelectedProp() && (*v6 & 3) == a3 )
  {
    (*(void (__fastcall **)(CShareWithListItemBase *))(*(_QWORD *)this + 456LL))(this);
    if ( !(*(unsigned __int8 (__fastcall **)(CShareWithListItemBase *))(*(_QWORD *)this + 272LL))(this)
      && (*((_BYTE *)this + 148) & 0x52) == 0 )
    {
      v10 = StrToID(L"CustomizeRemoveLinkArea");
      Descendent = DirectUI::Element::FindDescendent(this, v10);
      DirectUI::Element::SetLayoutPos(Descendent, -3);
      v12 = StrToID(L"CustomizeDeviceLink");
      v13 = DirectUI::Element::FindDescendent(this, v12);
      DirectUI::Element::SetVisible(v13, 0);
      v14 = StrToID(L"RemovePlayerLink");
      v15 = DirectUI::Element::FindDescendent(this, v14);
      v16 = 0;
LABEL_14:
      DirectUI::Element::SetVisible(v15, v16);
      goto LABEL_15;
    }
    v17 = StrToID(L"CustomizeRemoveLinkArea");
    v18 = DirectUI::Element::FindDescendent(this, v17);
    DirectUI::Element::SetLayoutPos(v18, 0);
    v19 = StrToID(L"CustomizeDeviceLink");
    v20 = DirectUI::Element::FindDescendent(this, v19);
    DirectUI::Element::SetVisible(v20, 1);
    if ( !*((_DWORD *)this + 58) )
    {
      v21 = StrToID(L"RemovePlayerLink");
      v15 = DirectUI::Element::FindDescendent(this, v21);
      v16 = 1;
      goto LABEL_14;
    }
  }
LABEL_15:
  DirectUI::Element::OnPropertyChanged(this, a2, a3, a4, a5);
}

```

## disassembly

```asm
0x18000bfa0  push    rbx
0x18000bfa2  push    rbp
0x18000bfa3  push    rsi
0x18000bfa4  push    rdi
0x18000bfa5  push    r14
0x18000bfa7  sub     rsp, 30h
0x18000bfab  mov     r14, r9
0x18000bfae  lea     rdi, [rdx+8]
0x18000bfb2  mov     ebp, r8d
0x18000bfb5  mov     rsi, rdx
0x18000bfb8  mov     rbx, rcx
0x18000bfbb  call    cs:__imp_?KeyFocusedProp@Element@DirectUI@@SAPEBUPropertyInfo@2@XZ; DirectUI::Element::KeyFocusedProp(void)
0x18000bfc1  cmp     rsi, rax
0x18000bfc4  jnz     short loc_18000BFCF
0x18000bfc6  mov     eax, [rdi]
0x18000bfc8  and     eax, 3
0x18000bfcb  cmp     eax, ebp
0x18000bfcd  jz      short loc_18000C013
0x18000bfcf  call    cs:__imp_?MouseWithinProp@Element@DirectUI@@SAPEBUPropertyInfo@2@XZ; DirectUI::Element::MouseWithinProp(void)
0x18000bfd5  cmp     rsi, rax
0x18000bfd8  jnz     short loc_18000BFE3
0x18000bfda  mov     eax, [rdi]
0x18000bfdc  and     eax, 3
0x18000bfdf  cmp     eax, ebp
0x18000bfe1  jz      short loc_18000C013
0x18000bfe3  call    cs:__imp_?MouseFocusedProp@Element@DirectUI@@SAPEBUPropertyInfo@2@XZ; DirectUI::Element::MouseFocusedProp(void)
0x18000bfe9  cmp     rsi, rax
0x18000bfec  jnz     short loc_18000BFF7
0x18000bfee  mov     eax, [rdi]
0x18000bff0  and     eax, 3
0x18000bff3  cmp     eax, ebp
0x18000bff5  jz      short loc_18000C013
0x18000bff7  call    cs:__imp_?SelectedProp@Element@DirectUI@@SAPEBUPropertyInfo@2@XZ; DirectUI::Element::SelectedProp(void)
0x18000bffd  cmp     rsi, rax
0x18000c000  jnz     loc_18000C121
0x18000c006  mov     eax, [rdi]
0x18000c008  and     eax, 3
0x18000c00b  cmp     eax, ebp
0x18000c00d  jnz     loc_18000C121
0x18000c013  mov     rax, [rbx]
0x18000c016  mov     rcx, rbx
0x18000c019  mov     rax, [rax+1C8h]
0x18000c020  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c025  mov     rax, [rbx]
0x18000c028  mov     rcx, rbx
0x18000c02b  mov     rax, [rax+110h]
0x18000c032  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c037  test    al, al
0x18000c039  jnz     short loc_18000C0AC
0x18000c03b  test    byte ptr [rbx+94h], 52h
0x18000c042  jnz     short loc_18000C0AC
0x18000c044  lea     rcx, aCustomizeremov; "CustomizeRemoveLinkArea"
0x18000c04b  call    cs:__imp_StrToID
0x18000c051  movzx   edx, ax
0x18000c054  mov     rcx, rbx
0x18000c057  call    cs:__imp_?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z; DirectUI::Element::FindDescendent(ushort)
0x18000c05d  mov     rcx, rax
0x18000c060  mov     edx, 0FFFFFFFDh
0x18000c065  call    cs:__imp_?SetLayoutPos@Element@DirectUI@@QEAAJH@Z; DirectUI::Element::SetLayoutPos(int)
0x18000c06b  lea     rcx, aCustomizedevic; "CustomizeDeviceLink"
0x18000c072  call    cs:__imp_StrToID
0x18000c078  movzx   edx, ax
0x18000c07b  mov     rcx, rbx
0x18000c07e  call    cs:__imp_?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z; DirectUI::Element::FindDescendent(ushort)
0x18000c084  mov     rcx, rax
0x18000c087  xor     edx, edx
0x18000c089  call    cs:__imp_?SetVisible@Element@DirectUI@@QEAAJ_N@Z; DirectUI::Element::SetVisible(bool)
0x18000c08f  lea     rcx, aRemoveplayerli; "RemovePlayerLink"
0x18000c096  call    cs:__imp_StrToID
0x18000c09c  movzx   edx, ax
0x18000c09f  mov     rcx, rbx
0x18000c0a2  call    cs:__imp_?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z; DirectUI::Element::FindDescendent(ushort)
0x18000c0a8  xor     edx, edx
0x18000c0aa  jmp     short loc_18000C118
0x18000c0ac  lea     rcx, aCustomizeremov; "CustomizeRemoveLinkArea"
0x18000c0b3  call    cs:__imp_StrToID
0x18000c0b9  movzx   edx, ax
0x18000c0bc  mov     rcx, rbx
0x18000c0bf  call    cs:__imp_?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z; DirectUI::Element::FindDescendent(ushort)
0x18000c0c5  mov     rcx, rax
0x18000c0c8  xor     edx, edx
0x18000c0ca  call    cs:__imp_?SetLayoutPos@Element@DirectUI@@QEAAJH@Z; DirectUI::Element::SetLayoutPos(int)
0x18000c0d0  lea     rcx, aCustomizedevic; "CustomizeDeviceLink"
0x18000c0d7  call    cs:__imp_StrToID
0x18000c0dd  movzx   edx, ax
0x18000c0e0  mov     rcx, rbx
0x18000c0e3  call    cs:__imp_?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z; DirectUI::Element::FindDescendent(ushort)
0x18000c0e9  mov     rcx, rax
0x18000c0ec  mov     dl, 1
0x18000c0ee  call    cs:__imp_?SetVisible@Element@DirectUI@@QEAAJ_N@Z; DirectUI::Element::SetVisible(bool)
0x18000c0f4  cmp     dword ptr [rbx+0E8h], 0
0x18000c0fb  jnz     short loc_18000C121
0x18000c0fd  lea     rcx, aRemoveplayerli; "RemovePlayerLink"
0x18000c104  call    cs:__imp_StrToID
0x18000c10a  movzx   edx, ax
0x18000c10d  mov     rcx, rbx
0x18000c110  call    cs:__imp_?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z; DirectUI::Element::FindDescendent(ushort)
0x18000c116  mov     dl, 1
0x18000c118  mov     rcx, rax
0x18000c11b  call    cs:__imp_?SetVisible@Element@DirectUI@@QEAAJ_N@Z; DirectUI::Element::SetVisible(bool)
0x18000c121  mov     r9, r14
0x18000c124  mov     r8d, ebp
0x18000c127  mov     rdx, rsi
0x18000c12a  mov     rcx, rbx
0x18000c12d  add     rsp, 30h
0x18000c131  pop     r14
0x18000c133  pop     rdi
0x18000c134  pop     rsi
0x18000c135  pop     rbp
0x18000c136  pop     rbx
0x18000c137  jmp     cs:__imp_?OnPropertyChanged@Element@DirectUI@@UEAAXPEBUPropertyInfo@2@HPEAVValue@2@1@Z; DirectUI::Element::OnPropertyChanged(DirectUI::PropertyInfo const *,int,DirectUI::Value *,DirectUI::Value *)
```
