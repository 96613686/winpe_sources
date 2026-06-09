# CColorCplPage::OnEvent(DirectUI::Event *)

- ea: `0x18000e010`
- end: `0x18000e178`
- name: `?OnEvent@CColorCplPage@@UEAAXPEAUEvent@DirectUI@@@Z`
- size: `360`
- prototype: `void __fastcall(CColorCplPage *__hidden this, struct DirectUI::Event *)`
- caller_count: `0`
- callee_count: `4`
- tags: `installer_update, broker_com_uri`

## callees

- `0x18000e010`
- `0x18000e4b4`
- `0x18000ed80`
- `0x180057010`

## import_xrefs

- `USER32!SendMessageW` at `0x18000e138`
- `USER32!SendMessageW` at `0x18000e138`
- `DUI70!?Click@Button@DirectUI@@SA?AVUID@@XZ` at `0x18000e034`
- `DUI70!?Click@Button@DirectUI@@SA?AVUID@@XZ` at `0x18000e034`
- `DUI70!?OnEvent@Element@DirectUI@@UEAAXPEAUEvent@2@@Z` at `0x18000e15b`
- `DUI70!?OnEvent@Element@DirectUI@@UEAAXPEAUEvent@2@@Z` at `0x18000e15b`
- `DUI70!?SelectionChange@Combobox@DirectUI@@SA?AVUID@@XZ` at `0x18000e0c7`
- `DUI70!?SelectionChange@Combobox@DirectUI@@SA?AVUID@@XZ` at `0x18000e0c7`
- `DUI70!?GetSelection@Combobox@DirectUI@@QEAAHXZ` at `0x18000e105`
- `DUI70!?GetSelection@Combobox@DirectUI@@QEAAHXZ` at `0x18000e105`

## pseudocode

```c
void __fastcall CColorCplPage::OnEvent(CColorCplPage *this, struct DirectUI::Event *a2)
{
  __int64 v4; // rax
  void (***v5)(void); // rcx
  void (*v6)(void); // rax
  WPARAM Selection; // rbx
  HWND v8; // rax
  int v9; // eax
  char v10; // [rsp+38h] [rbp+10h] BYREF

  if ( *((_DWORD *)a2 + 5) != 1 )
    goto LABEL_16;
  if ( *((_QWORD *)a2 + 1) == *(_QWORD *)DirectUI::Button::Click(&v10) )
  {
    v4 = *(_QWORD *)a2;
    *((_BYTE *)a2 + 16) = 1;
    if ( v4 == *((_QWORD *)this + 99) )
    {
      v5 = (void (***)(void))*((_QWORD *)this + 98);
      *((_BYTE *)this + 260) = 0;
      v6 = **v5;
LABEL_9:
      v6();
      CColorCplPage::_UpdateBannerColors(this);
      goto LABEL_16;
    }
    if ( v4 == *((_QWORD *)this + 100) )
    {
      (*(void (__fastcall **)(_QWORD))(**((_QWORD **)this + 98) + 8LL))(*((_QWORD *)this + 98));
      goto LABEL_16;
    }
    if ( v4 == *((_QWORD *)this + 101) )
    {
      v6 = *(void (**)(void))(**((_QWORD **)this + 98) + 16LL);
      goto LABEL_9;
    }
    *((_BYTE *)a2 + 16) = 0;
  }
  else if ( *((_QWORD *)a2 + 1) == *(_QWORD *)DirectUI::Combobox::SelectionChange(&v10)
         && *(_QWORD *)a2 == *((_QWORD *)this + 102) )
  {
    *((_BYTE *)a2 + 16) = 1;
    if ( *((_BYTE *)this + 259) )
    {
      *((_BYTE *)this + 259) = 0;
    }
    else
    {
      Selection = (int)DirectUI::Combobox::GetSelection(*((DirectUI::Combobox **)this + 102));
      v8 = (HWND)(*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 102) + 360LL))(*((_QWORD *)this + 102));
      v9 = SendMessageW(v8, 0x150u, Selection, 0);
      CColorCplPage::_OnChangeTheme(this, v9);
    }
  }
LABEL_16:
  if ( !*((_BYTE *)a2 + 16) )
    DirectUI::Element::OnEvent(this, a2);
}

```

## disassembly

```asm
0x18000e010  mov     [rsp+arg_0], rbx
0x18000e015  mov     [rsp+arg_10], rsi
0x18000e01a  push    rdi
0x18000e01b  sub     rsp, 20h
0x18000e01f  cmp     dword ptr [rdx+14h], 1
0x18000e023  mov     rsi, rdx
0x18000e026  mov     rdi, rcx
0x18000e029  jnz     loc_18000E14F
0x18000e02f  lea     rcx, [rsp+28h+arg_8]
0x18000e034  call    cs:__imp_?Click@Button@DirectUI@@SA?AVUID@@XZ; DirectUI::Button::Click(void)
0x18000e03b  nop     dword ptr [rax+rax+00h]
0x18000e040  mov     rax, [rax]
0x18000e043  cmp     [rsi+8], rax
0x18000e047  jnz     short loc_18000E0C2
0x18000e049  mov     rax, [rsi]
0x18000e04c  mov     byte ptr [rsi+10h], 1
0x18000e050  cmp     rax, [rdi+318h]
0x18000e057  jnz     short loc_18000E06F
0x18000e059  mov     rcx, [rdi+310h]
0x18000e060  mov     byte ptr [rdi+104h], 0
0x18000e067  mov     rax, [rcx]
0x18000e06a  mov     rax, [rax]
0x18000e06d  jmp     short loc_18000E0A7
0x18000e06f  cmp     rax, [rdi+320h]
0x18000e076  jnz     short loc_18000E090
0x18000e078  mov     rcx, [rdi+310h]
0x18000e07f  mov     rax, [rcx]
0x18000e082  mov     rax, [rax+8]
0x18000e086  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e08b  jmp     loc_18000E14F
0x18000e090  cmp     rax, [rdi+328h]
0x18000e097  jnz     short loc_18000E0B9
0x18000e099  mov     rcx, [rdi+310h]
0x18000e0a0  mov     rax, [rcx]
0x18000e0a3  mov     rax, [rax+10h]
0x18000e0a7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e0ac  mov     rcx, rdi; this
0x18000e0af  call    ?_UpdateBannerColors@CColorCplPage@@AEAAXXZ; CColorCplPage::_UpdateBannerColors(void)
0x18000e0b4  jmp     loc_18000E14F
0x18000e0b9  mov     byte ptr [rsi+10h], 0
0x18000e0bd  jmp     loc_18000E14F
0x18000e0c2  lea     rcx, [rsp+28h+arg_8]
0x18000e0c7  call    cs:__imp_?SelectionChange@Combobox@DirectUI@@SA?AVUID@@XZ; DirectUI::Combobox::SelectionChange(void)
0x18000e0ce  nop     dword ptr [rax+rax+00h]
0x18000e0d3  mov     rcx, [rax]
0x18000e0d6  cmp     [rsi+8], rcx
0x18000e0da  jnz     short loc_18000E14F
0x18000e0dc  mov     rax, [rdi+330h]
0x18000e0e3  cmp     [rsi], rax
0x18000e0e6  jnz     short loc_18000E14F
0x18000e0e8  mov     byte ptr [rsi+10h], 1
0x18000e0ec  cmp     byte ptr [rdi+103h], 0
0x18000e0f3  jz      short loc_18000E0FE
0x18000e0f5  mov     byte ptr [rdi+103h], 0
0x18000e0fc  jmp     short loc_18000E14F
0x18000e0fe  mov     rcx, [rdi+330h]
0x18000e105  call    cs:__imp_?GetSelection@Combobox@DirectUI@@QEAAHXZ; DirectUI::Combobox::GetSelection(void)
0x18000e10c  nop     dword ptr [rax+rax+00h]
0x18000e111  mov     rcx, [rdi+330h]
0x18000e118  movsxd  rbx, eax
0x18000e11b  mov     rax, [rcx]
0x18000e11e  mov     rax, [rax+168h]
0x18000e125  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e12a  xor     r9d, r9d; lParam
0x18000e12d  mov     r8, rbx; wParam
0x18000e130  mov     edx, 150h; Msg
0x18000e135  mov     rcx, rax; hWnd
0x18000e138  call    cs:__imp_SendMessageW
0x18000e13f  nop     dword ptr [rax+rax+00h]
0x18000e144  mov     rdx, rax; int
0x18000e147  mov     rcx, rdi; this
0x18000e14a  call    ?_OnChangeTheme@CColorCplPage@@AEAAXH@Z; CColorCplPage::_OnChangeTheme(int)
0x18000e14f  cmp     byte ptr [rsi+10h], 0
0x18000e153  jnz     short loc_18000E167
0x18000e155  mov     rdx, rsi
0x18000e158  mov     rcx, rdi
0x18000e15b  call    cs:__imp_?OnEvent@Element@DirectUI@@UEAAXPEAUEvent@2@@Z; DirectUI::Element::OnEvent(DirectUI::Event *)
0x18000e162  nop     dword ptr [rax+rax+00h]
0x18000e167  mov     rbx, [rsp+28h+arg_0]
0x18000e16c  mov     rsi, [rsp+28h+arg_10]
0x18000e171  add     rsp, 20h
0x18000e175  pop     rdi
0x18000e176  retn
```
