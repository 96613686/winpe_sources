# CAccountGroupPage::OnListenedEvent(DirectUI::Element *,DirectUI::Event *)

- ea: `0x18000ef40`
- end: `0x18000f0fb`
- name: `?OnListenedEvent@CAccountGroupPage@@UEAAXPEAVElement@DirectUI@@PEAUEvent@3@@Z`
- size: `443`
- prototype: `void __fastcall(CAccountGroupPage *__hidden this, struct DirectUI::Element *, struct DirectUI::Event *)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x18000ef40`
- `0x180063a20`

## import_xrefs

- `DUI70!?SetContentString@Element@DirectUI@@QEAAJPEBG@Z` at `0x18000f08d`
- `DUI70!?SetContentString@Element@DirectUI@@QEAAJPEBG@Z` at `0x18000f08d`
- `DUI70!?SelectionChange@Combobox@DirectUI@@SA?AVUID@@XZ` at `0x18000f023`
- `DUI70!?SelectionChange@Combobox@DirectUI@@SA?AVUID@@XZ` at `0x18000f023`
- `DUI70!?SetSelection@Combobox@DirectUI@@QEAAJH@Z` at `0x18000efd7`
- `DUI70!?SetSelection@Combobox@DirectUI@@QEAAJH@Z` at `0x18000efd7`
- `DUI70!?SetEnabled@Element@DirectUI@@QEAAJ_N@Z` at `0x18000efc1`
- `DUI70!?SetEnabled@Element@DirectUI@@QEAAJ_N@Z` at `0x18000efcc`
- `DUI70!?SetEnabled@Element@DirectUI@@QEAAJ_N@Z` at `0x18000f0da`
- `DUI70!?SetEnabled@Element@DirectUI@@QEAAJ_N@Z` at `0x18000f0e5`
- `DUI70!?SetEnabled@Element@DirectUI@@QEAAJ_N@Z` at `0x18000efc1`
- `DUI70!?SetEnabled@Element@DirectUI@@QEAAJ_N@Z` at `0x18000efcc`
- `DUI70!?SetEnabled@Element@DirectUI@@QEAAJ_N@Z` at `0x18000f0da`
- `DUI70!?SetEnabled@Element@DirectUI@@QEAAJ_N@Z` at `0x18000f0e5`
- `DUI70!StrToID` at `0x18000ef71`
- `DUI70!StrToID` at `0x18000ef87`
- `DUI70!StrToID` at `0x18000efa7`
- `DUI70!StrToID` at `0x18000eff3`
- `DUI70!StrToID` at `0x18000f013`
- `DUI70!StrToID` at `0x18000f047`
- `DUI70!StrToID` at `0x18000f075`
- `DUI70!StrToID` at `0x18000f0a0`
- `DUI70!StrToID` at `0x18000f0c0`
- `DUI70!StrToID` at `0x18000ef71`
- `DUI70!StrToID` at `0x18000ef87`
- `DUI70!StrToID` at `0x18000efa7`
- `DUI70!StrToID` at `0x18000eff3`
- `DUI70!StrToID` at `0x18000f013`
- `DUI70!StrToID` at `0x18000f047`
- `DUI70!StrToID` at `0x18000f075`
- `DUI70!StrToID` at `0x18000f0a0`
- `DUI70!StrToID` at `0x18000f0c0`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x18000ef93`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x18000efb3`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x18000f081`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x18000f0ac`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x18000f0cc`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x18000ef93`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x18000efb3`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x18000f081`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x18000f0ac`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x18000f0cc`

## string_xrefs

- `0x18000ef80`: `OtherComboBox`
- `0x18000f039`: `OtherComboBox`
- `0x18000f099`: `OtherComboBox`
- `0x18000ef9d`: `OtherComboInfo`
- `0x18000f06b`: `OtherComboInfo`
- `0x18000f0b6`: `OtherComboInfo`

## pseudocode

```c
void __fastcall CAccountGroupPage::OnListenedEvent(
        CAccountGroupPage *this,
        struct DirectUI::Element *a2,
        struct DirectUI::Event *a3)
{
  __int16 v5; // bx
  DirectUI::Element *v6; // rbx
  unsigned __int16 v7; // ax
  struct DirectUI::Element *Descendent; // rax
  DirectUI::Element *v9; // rbx
  DirectUI::Element *v10; // rdi
  unsigned __int16 v11; // ax
  DirectUI::Element *v12; // rbx
  __int16 v13; // bx
  __int16 v14; // bx
  __int16 v15; // bx
  const unsigned __int16 *Ptr; // rax
  DirectUI::Element *v17; // rbx
  const unsigned __int16 *v18; // rdi
  unsigned __int16 v19; // ax
  DirectUI::Element *v20; // rax
  DirectUI::Element *v21; // rbx
  unsigned __int16 v22; // ax
  struct DirectUI::Element *v23; // rax
  DirectUI::Element *v24; // rbx
  DirectUI::Element *v25; // rdi
  unsigned __int16 v26; // ax
  DirectUI::Element *v27; // rbx
  char v28; // [rsp+40h] [rbp+18h] BYREF

  if ( *((_DWORD *)a3 + 5) == 1 )
  {
    v5 = *(_WORD *)(*(_QWORD *)a3 + 144LL);
    if ( v5 == (unsigned __int16)StrToID(L"navotherR") )
    {
      v6 = (DirectUI::Element *)*((_QWORD *)this + 8);
      v7 = StrToID(L"OtherComboBox");
      Descendent = DirectUI::Element::FindDescendent(v6, v7);
      v9 = (DirectUI::Element *)*((_QWORD *)this + 8);
      v10 = Descendent;
      v11 = StrToID(L"OtherComboInfo");
      v12 = DirectUI::Element::FindDescendent(v9, v11);
      DirectUI::Element::SetEnabled(v10, 1);
      DirectUI::Element::SetEnabled(v12, 1);
      DirectUI::Combobox::SetSelection(v10, 0);
    }
    else
    {
      v13 = *(_WORD *)(*(_QWORD *)a3 + 144LL);
      if ( v13 == (unsigned __int16)StrToID(L"navstandarduserR")
        || (v14 = *(_WORD *)(*(_QWORD *)a3 + 144LL), v14 == (unsigned __int16)StrToID(L"navadminuserR")) )
      {
        v21 = (DirectUI::Element *)*((_QWORD *)this + 8);
        v22 = StrToID(L"OtherComboBox");
        v23 = DirectUI::Element::FindDescendent(v21, v22);
        v24 = (DirectUI::Element *)*((_QWORD *)this + 8);
        v25 = v23;
        v26 = StrToID(L"OtherComboInfo");
        v27 = DirectUI::Element::FindDescendent(v24, v26);
        DirectUI::Element::SetEnabled(v25, 0);
        DirectUI::Element::SetEnabled(v27, 0);
      }
      else if ( *((_QWORD *)a3 + 1) == *(_QWORD *)DirectUI::Combobox::SelectionChange(&v28) )
      {
        v15 = *(_WORD *)(*(_QWORD *)a3 + 144LL);
        if ( v15 == (unsigned __int16)StrToID(L"OtherComboBox") )
        {
          Ptr = (const unsigned __int16 *)g_pfn_DPA_GetPtr(*((HDPA *)this + 210), *((int *)a3 + 9));
          v17 = (DirectUI::Element *)*((_QWORD *)this + 8);
          v18 = Ptr;
          v19 = StrToID(L"OtherComboInfo");
          v20 = DirectUI::Element::FindDescendent(v17, v19);
          DirectUI::Element::SetContentString(v20, v18);
        }
      }
    }
  }
}

```

## disassembly

```asm
0x18000ef40  mov     [rsp+arg_0], rbx
0x18000ef45  mov     [rsp+arg_8], rsi
0x18000ef4a  push    rdi
0x18000ef4b  sub     rsp, 20h
0x18000ef4f  cmp     dword ptr [r8+14h], 1
0x18000ef54  mov     rdi, r8
0x18000ef57  mov     rsi, rcx
0x18000ef5a  jnz     loc_18000F0EB
0x18000ef60  mov     rax, [r8]
0x18000ef63  lea     rcx, aNavotherr; "navotherR"
0x18000ef6a  movzx   ebx, word ptr [rax+90h]
0x18000ef71  call    cs:__imp_StrToID
0x18000ef77  cmp     bx, ax
0x18000ef7a  jnz     short loc_18000EFE2
0x18000ef7c  mov     rbx, [rsi+40h]
0x18000ef80  lea     rcx, aOthercombobox; "OtherComboBox"
0x18000ef87  call    cs:__imp_StrToID
0x18000ef8d  movzx   edx, ax
0x18000ef90  mov     rcx, rbx
0x18000ef93  call    cs:__imp_?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z; DirectUI::Element::FindDescendent(ushort)
0x18000ef99  mov     rbx, [rsi+40h]
0x18000ef9d  lea     rcx, aOthercomboinfo; "OtherComboInfo"
0x18000efa4  mov     rdi, rax
0x18000efa7  call    cs:__imp_StrToID
0x18000efad  movzx   edx, ax
0x18000efb0  mov     rcx, rbx
0x18000efb3  call    cs:__imp_?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z; DirectUI::Element::FindDescendent(ushort)
0x18000efb9  mov     dl, 1
0x18000efbb  mov     rcx, rdi
0x18000efbe  mov     rbx, rax
0x18000efc1  call    cs:__imp_?SetEnabled@Element@DirectUI@@QEAAJ_N@Z; DirectUI::Element::SetEnabled(bool)
0x18000efc7  mov     dl, 1
0x18000efc9  mov     rcx, rbx
0x18000efcc  call    cs:__imp_?SetEnabled@Element@DirectUI@@QEAAJ_N@Z; DirectUI::Element::SetEnabled(bool)
0x18000efd2  xor     edx, edx
0x18000efd4  mov     rcx, rdi
0x18000efd7  call    cs:__imp_?SetSelection@Combobox@DirectUI@@QEAAJH@Z; DirectUI::Combobox::SetSelection(int)
0x18000efdd  jmp     loc_18000F0EB
0x18000efe2  mov     rax, [rdi]
0x18000efe5  lea     rcx, aNavstandarduse; "navstandarduserR"
0x18000efec  movzx   ebx, word ptr [rax+90h]
0x18000eff3  call    cs:__imp_StrToID
0x18000eff9  cmp     bx, ax
0x18000effc  jz      loc_18000F095
0x18000f002  mov     rax, [rdi]
0x18000f005  lea     rcx, aNavadminuserr; "navadminuserR"
0x18000f00c  movzx   ebx, word ptr [rax+90h]
0x18000f013  call    cs:__imp_StrToID
0x18000f019  cmp     bx, ax
0x18000f01c  jz      short loc_18000F095
0x18000f01e  lea     rcx, [rsp+28h+arg_10]
0x18000f023  call    cs:__imp_?SelectionChange@Combobox@DirectUI@@SA?AVUID@@XZ; DirectUI::Combobox::SelectionChange(void)
0x18000f029  mov     rcx, [rax]
0x18000f02c  cmp     [rdi+8], rcx
0x18000f030  jnz     loc_18000F0EB
0x18000f036  mov     rax, [rdi]
0x18000f039  lea     rcx, aOthercombobox; "OtherComboBox"
0x18000f040  movzx   ebx, word ptr [rax+90h]
0x18000f047  call    cs:__imp_StrToID
0x18000f04d  cmp     bx, ax
0x18000f050  jnz     loc_18000F0EB
0x18000f056  movsxd  rdx, dword ptr [rdi+24h]; i
0x18000f05a  mov     rcx, [rsi+690h]; hdpa
0x18000f061  call    cs:g_pfn_DPA_GetPtr
0x18000f067  mov     rbx, [rsi+40h]
0x18000f06b  lea     rcx, aOthercomboinfo; "OtherComboInfo"
0x18000f072  mov     rdi, rax
0x18000f075  call    cs:__imp_StrToID
0x18000f07b  movzx   edx, ax
0x18000f07e  mov     rcx, rbx
0x18000f081  call    cs:__imp_?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z; DirectUI::Element::FindDescendent(ushort)
0x18000f087  mov     rcx, rax
0x18000f08a  mov     rdx, rdi
0x18000f08d  call    cs:__imp_?SetContentString@Element@DirectUI@@QEAAJPEBG@Z; DirectUI::Element::SetContentString(ushort const *)
0x18000f093  jmp     short loc_18000F0EB
0x18000f095  mov     rbx, [rsi+40h]
0x18000f099  lea     rcx, aOthercombobox; "OtherComboBox"
0x18000f0a0  call    cs:__imp_StrToID
0x18000f0a6  movzx   edx, ax
0x18000f0a9  mov     rcx, rbx
0x18000f0ac  call    cs:__imp_?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z; DirectUI::Element::FindDescendent(ushort)
0x18000f0b2  mov     rbx, [rsi+40h]
0x18000f0b6  lea     rcx, aOthercomboinfo; "OtherComboInfo"
0x18000f0bd  mov     rdi, rax
0x18000f0c0  call    cs:__imp_StrToID
0x18000f0c6  movzx   edx, ax
0x18000f0c9  mov     rcx, rbx
0x18000f0cc  call    cs:__imp_?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z; DirectUI::Element::FindDescendent(ushort)
0x18000f0d2  xor     edx, edx
0x18000f0d4  mov     rcx, rdi
0x18000f0d7  mov     rbx, rax
0x18000f0da  call    cs:__imp_?SetEnabled@Element@DirectUI@@QEAAJ_N@Z; DirectUI::Element::SetEnabled(bool)
0x18000f0e0  xor     edx, edx
0x18000f0e2  mov     rcx, rbx
0x18000f0e5  call    cs:__imp_?SetEnabled@Element@DirectUI@@QEAAJ_N@Z; DirectUI::Element::SetEnabled(bool)
0x18000f0eb  mov     rbx, [rsp+28h+arg_0]
0x18000f0f0  mov     rsi, [rsp+28h+arg_8]
0x18000f0f5  add     rsp, 20h
0x18000f0f9  pop     rdi
0x18000f0fa  retn
```
