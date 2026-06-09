# ComboBoxEx::OnNotify(uint,unsigned __int64,__int64,__int64 *)

- ea: `0x1800109f0`
- end: `0x180010ac6`
- name: `?OnNotify@ComboBoxEx@@UEAA_NI_K_JPEA_J@Z`
- size: `214`
- prototype: `bool __fastcall(ComboBoxEx *__hidden this, unsigned int, unsigned __int64, __int64, __int64 *)`
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x1800109f0`
- `0x180010cc8`
- `0x180057010`

## import_xrefs

- `USER32!SendMessageW` at `0x180010a53`
- `USER32!SendMessageW` at `0x180010a53`
- `DUI70!?FireEvent@Element@DirectUI@@QEAAXPEAUEvent@2@_N1@Z` at `0x180010a9b`
- `DUI70!?FireEvent@Element@DirectUI@@QEAAXPEAUEvent@2@_N1@Z` at `0x180010a9b`
- `DUI70!?OnNotify@Combobox@DirectUI@@UEAA_NI_K_JPEA_J@Z` at `0x180010aba`

## pseudocode

```c
bool __fastcall ComboBoxEx::OnNotify(ComboBoxEx *this, unsigned int a2, unsigned __int64 a3, __int64 a4, __int64 *a5)
{
  HWND v9; // rax
  int v10; // eax
  _BYTE v12[8]; // [rsp+30h] [rbp-58h] BYREF
  __int64 v13; // [rsp+38h] [rbp-50h]
  unsigned int v14; // [rsp+50h] [rbp-38h]
  unsigned int v15; // [rsp+98h] [rbp+10h] BYREF

  if ( a2 == 273 && WORD1(a3) == 9 )
  {
    v9 = (HWND)(*(__int64 (__fastcall **)(ComboBoxEx *))(*(_QWORD *)this + 360LL))(this);
    if ( v9 )
    {
      v15 = 0;
      v10 = SendMessageW(v9, a2 + 54, 0, 0);
      if ( (int)ComboBoxEx::_GetValueAtIndex(this, v10, &v15) >= 0 )
      {
        v13 = ComboBoxEx::SelectedValueChange;
        v14 = v15;
        DirectUI::Element::FireEvent(this, (struct DirectUI::Event *)v12, 1, 0);
      }
    }
  }
  return DirectUI::Combobox::OnNotify(this, a2, a3, a4, a5);
}

```

## disassembly

```asm
0x1800109f0  push    rbx
0x1800109f2  push    rbp
0x1800109f3  push    rsi
0x1800109f4  push    rdi
0x1800109f5  sub     rsp, 68h
0x1800109f9  mov     rbp, r9
0x1800109fc  mov     rdi, r8
0x1800109ff  mov     esi, edx
0x180010a01  mov     rbx, rcx
0x180010a04  cmp     edx, 111h
0x180010a0a  jnz     loc_180010AA7
0x180010a10  mov     rax, r8
0x180010a13  mov     ecx, 9
0x180010a18  shr     rax, 10h
0x180010a1c  cmp     cx, ax
0x180010a1f  jnz     loc_180010AA7
0x180010a25  mov     rax, [rbx]
0x180010a28  mov     rcx, rbx
0x180010a2b  mov     rax, [rax+168h]
0x180010a32  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010a37  test    rax, rax
0x180010a3a  jz      short loc_180010AA7
0x180010a3c  xor     r9d, r9d; lParam
0x180010a3f  mov     [rsp+88h+arg_8], 0
0x180010a4a  xor     r8d, r8d; wParam
0x180010a4d  lea     edx, [rsi+36h]; Msg
0x180010a50  mov     rcx, rax; hWnd
0x180010a53  call    cs:__imp_SendMessageW
0x180010a5a  nop     dword ptr [rax+rax+00h]
0x180010a5f  lea     r8, [rsp+88h+arg_8]; unsigned int *
0x180010a67  mov     rcx, rbx; this
0x180010a6a  mov     rdx, rax; int
0x180010a6d  call    ?_GetValueAtIndex@ComboBoxEx@@AEAAJHPEAK@Z; ComboBoxEx::_GetValueAtIndex(int,ulong *)
0x180010a72  test    eax, eax
0x180010a74  js      short loc_180010AA7
0x180010a76  mov     rax, cs:?SelectedValueChange@ComboBoxEx@@2VUID@@A; UID ComboBoxEx::SelectedValueChange
0x180010a7d  lea     rdx, [rsp+88h+var_58]
0x180010a82  mov     [rsp+88h+var_50], rax
0x180010a87  xor     r9d, r9d
0x180010a8a  mov     eax, [rsp+88h+arg_8]
0x180010a91  mov     r8b, 1
0x180010a94  mov     rcx, rbx
0x180010a97  mov     [rsp+88h+var_38], eax
0x180010a9b  call    cs:__imp_?FireEvent@Element@DirectUI@@QEAAXPEAUEvent@2@_N1@Z; DirectUI::Element::FireEvent(DirectUI::Event *,bool,bool)
0x180010aa2  nop     dword ptr [rax+rax+00h]
0x180010aa7  mov     r9, rbp
0x180010aaa  mov     r8, rdi
0x180010aad  mov     edx, esi
0x180010aaf  mov     rcx, rbx
0x180010ab2  add     rsp, 68h
0x180010ab6  pop     rdi
0x180010ab7  pop     rsi
0x180010ab8  pop     rbp
0x180010ab9  pop     rbx
0x180010aba  jmp     cs:__imp_?OnNotify@Combobox@DirectUI@@UEAA_NI_K_JPEA_J@Z; DirectUI::Combobox::OnNotify(uint,unsigned __int64,__int64,__int64 *)
```
