# CWallpaperCore::LocationDropDownChange(uint)

- ea: `0x18003c52c`
- end: `0x18003c62a`
- name: `?LocationDropDownChange@CWallpaperCore@@AEAAXI@Z`
- size: `254`
- prototype: `void __fastcall(CWallpaperCore *__hidden this, unsigned int)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180043e00`

## callees

- `0x18003c52c`
- `0x180042ab4`
- `0x180057010`

## import_xrefs

- `SHELL32!__imp_ILFree` at `0x18003c60d`
- `SHELL32!__imp_ILFree` at `0x18003c60d`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x18003c5a2`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x18003c5a2`
- `DUI70!StrToID` at `0x18003c590`
- `DUI70!StrToID` at `0x18003c590`
- `DUI70!?GetSelection@Combobox@DirectUI@@QEAAHXZ` at `0x18003c5df`
- `DUI70!?GetSelection@Combobox@DirectUI@@QEAAHXZ` at `0x18003c5df`
- `DUI70!?GetClassInfoPtr@Combobox@DirectUI@@SAPEAUIClassInfo@2@XZ` at `0x18003c5b6`
- `DUI70!?GetClassInfoPtr@Combobox@DirectUI@@SAPEAUIClassInfo@2@XZ` at `0x18003c5b6`

## string_xrefs

- `0x18003c589`: `ComboBox_PictureFolder`

## pseudocode

```c
void __fastcall CWallpaperCore::LocationDropDownChange(CWallpaperCore *this, int a2)
{
  DirectUI::Element *v3; // rbx
  unsigned __int16 v4; // ax
  DirectUI::Combobox *Descendent; // rsi
  __int64 ClassInfoPtr; // rbx
  const ITEMIDLIST *v7; // rdx

  if ( a2 == 8 )
  {
    *((_BYTE *)this + 184) = 0;
LABEL_6:
    if ( !*((_BYTE *)this + 183) && *((_QWORD *)this + 26) )
    {
      v3 = (DirectUI::Element *)*((_QWORD *)this + 4);
      v4 = StrToID(L"ComboBox_PictureFolder");
      Descendent = DirectUI::Element::FindDescendent(v3, v4);
      if ( Descendent )
      {
        ClassInfoPtr = DirectUI::Combobox::GetClassInfoPtr();
        if ( (*(__int64 (__fastcall **)(DirectUI::Combobox *))(*(_QWORD *)Descendent + 280LL))(Descendent) == ClassInfoPtr
          && DirectUI::Combobox::GetSelection(Descendent) == -1 )
        {
          v7 = (const ITEMIDLIST *)*((_QWORD *)this + 26);
          *((_BYTE *)this + 179) = 1;
          CWallpaperCore::_SelectFromPathCombo(this, v7);
        }
      }
      ILFree(*((LPITEMIDLIST *)this + 26));
    }
    return;
  }
  if ( a2 == 7 )
  {
    *((_BYTE *)this + 184) = 1;
    return;
  }
  if ( !*((_BYTE *)this + 184) )
    goto LABEL_6;
}

```

## disassembly

```asm
0x18003c52c  mov     [rsp+arg_0], rbx
0x18003c531  mov     [rsp+arg_8], rsi
0x18003c536  push    rdi
0x18003c537  sub     rsp, 20h
0x18003c53b  mov     rdi, rcx
0x18003c53e  cmp     edx, 8
0x18003c541  jnz     short loc_18003C54C
0x18003c543  mov     byte ptr [rcx+0B8h], 0
0x18003c54a  jmp     short loc_18003C56A
0x18003c54c  cmp     edx, 7
0x18003c54f  jnz     short loc_18003C55D
0x18003c551  mov     byte ptr [rcx+0B8h], 1
0x18003c558  jmp     loc_18003C619
0x18003c55d  cmp     byte ptr [rcx+0B8h], 0
0x18003c564  jnz     loc_18003C619
0x18003c56a  cmp     byte ptr [rcx+0B7h], 0
0x18003c571  jnz     loc_18003C619
0x18003c577  cmp     qword ptr [rcx+0D0h], 0
0x18003c57f  jz      loc_18003C619
0x18003c585  mov     rbx, [rcx+20h]
0x18003c589  lea     rcx, aComboboxPictur; "ComboBox_PictureFolder"
0x18003c590  call    cs:__imp_StrToID
0x18003c597  nop     dword ptr [rax+rax+00h]
0x18003c59c  movzx   edx, ax
0x18003c59f  mov     rcx, rbx
0x18003c5a2  call    cs:__imp_?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z; DirectUI::Element::FindDescendent(ushort)
0x18003c5a9  nop     dword ptr [rax+rax+00h]
0x18003c5ae  mov     rsi, rax
0x18003c5b1  test    rax, rax
0x18003c5b4  jz      short loc_18003C606
0x18003c5b6  call    cs:__imp_?GetClassInfoPtr@Combobox@DirectUI@@SAPEAUIClassInfo@2@XZ; DirectUI::Combobox::GetClassInfoPtr(void)
0x18003c5bd  nop     dword ptr [rax+rax+00h]
0x18003c5c2  mov     rcx, [rsi]
0x18003c5c5  mov     rbx, rax
0x18003c5c8  mov     rax, [rcx+118h]
0x18003c5cf  mov     rcx, rsi
0x18003c5d2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003c5d7  cmp     rax, rbx
0x18003c5da  jnz     short loc_18003C606
0x18003c5dc  mov     rcx, rsi
0x18003c5df  call    cs:__imp_?GetSelection@Combobox@DirectUI@@QEAAHXZ; DirectUI::Combobox::GetSelection(void)
0x18003c5e6  nop     dword ptr [rax+rax+00h]
0x18003c5eb  cmp     eax, 0FFFFFFFFh
0x18003c5ee  jnz     short loc_18003C606
0x18003c5f0  mov     rdx, [rdi+0D0h]; struct _ITEMIDLIST_ABSOLUTE *
0x18003c5f7  mov     rcx, rdi; this
0x18003c5fa  mov     byte ptr [rdi+0B3h], 1
0x18003c601  call    ?_SelectFromPathCombo@CWallpaperCore@@AEAAJPEBU_ITEMIDLIST_ABSOLUTE@@@Z; CWallpaperCore::_SelectFromPathCombo(_ITEMIDLIST_ABSOLUTE const *)
0x18003c606  mov     rcx, [rdi+0D0h]; pidl
0x18003c60d  call    cs:__imp_ILFree
0x18003c614  nop     dword ptr [rax+rax+00h]
0x18003c619  mov     rbx, [rsp+28h+arg_0]
0x18003c61e  mov     rsi, [rsp+28h+arg_8]
0x18003c623  add     rsp, 20h
0x18003c627  pop     rdi
0x18003c628  retn
```
