# CWallpaperCore::_SetChangeInterval(uint)

- ea: `0x180042fd8`
- end: `0x18004308e`
- name: `?_SetChangeInterval@CWallpaperCore@@AEAAXI@Z`
- size: `182`
- prototype: `void __fastcall(CWallpaperCore *__hidden this, unsigned int)`
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18003bacc`
- `0x18003ca90`

## callees

- `0x180042fd8`
- `0x180057010`

## import_xrefs

- `USER32!SendMessageW` at `0x180043035`
- `USER32!SendMessageW` at `0x180043058`
- `USER32!SendMessageW` at `0x180043035`
- `USER32!SendMessageW` at `0x180043058`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x180043003`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x180043003`
- `DUI70!StrToID` at `0x180042ff1`
- `DUI70!StrToID` at `0x180042ff1`
- `DUI70!?SetSelection@Combobox@DirectUI@@QEAAJH@Z` at `0x180043076`
- `DUI70!?SetSelection@Combobox@DirectUI@@QEAAJH@Z` at `0x180043076`

## string_xrefs

- `0x180042fea`: `ComboBox_Interval`

## pseudocode

```c
void __fastcall CWallpaperCore::_SetChangeInterval(CWallpaperCore *this, int a2)
{
  DirectUI::Element *v2; // rbx
  unsigned __int16 v4; // ax
  DirectUI::Combobox *Descendent; // rdi
  HWND v6; // rbp
  unsigned int v7; // ebx
  int v8; // esi

  v2 = (DirectUI::Element *)*((_QWORD *)this + 4);
  v4 = StrToID(L"ComboBox_Interval");
  Descendent = DirectUI::Element::FindDescendent(v2, v4);
  v6 = (HWND)(*(__int64 (__fastcall **)(DirectUI::Combobox *))(*(_QWORD *)Descendent + 360LL))(Descendent);
  v7 = 0;
  v8 = SendMessageW(v6, 0x146u, 0, 0);
  if ( v8 > 0 )
  {
    while ( (unsigned int)SendMessageW(v6, 0x150u, v7, 0) != a2 )
    {
      if ( (int)++v7 >= v8 )
        return;
    }
    DirectUI::Combobox::SetSelection(Descendent, v7);
  }
}

```

## disassembly

```asm
0x180042fd8  push    rbx
0x180042fda  push    rbp
0x180042fdb  push    rsi
0x180042fdc  push    rdi
0x180042fdd  push    r14
0x180042fdf  sub     rsp, 20h
0x180042fe3  mov     rbx, [rcx+20h]
0x180042fe7  mov     r14d, edx
0x180042fea  lea     rcx, aComboboxInterv; "ComboBox_Interval"
0x180042ff1  call    cs:__imp_StrToID
0x180042ff8  nop     dword ptr [rax+rax+00h]
0x180042ffd  movzx   edx, ax
0x180043000  mov     rcx, rbx
0x180043003  call    cs:__imp_?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z; DirectUI::Element::FindDescendent(ushort)
0x18004300a  nop     dword ptr [rax+rax+00h]
0x18004300f  mov     rdi, rax
0x180043012  mov     rcx, [rax]
0x180043015  mov     rax, [rcx+168h]
0x18004301c  mov     rcx, rdi
0x18004301f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180043024  xor     r9d, r9d; lParam
0x180043027  xor     r8d, r8d; wParam
0x18004302a  mov     edx, 146h; Msg
0x18004302f  mov     rcx, rax; hWnd
0x180043032  mov     rbp, rax
0x180043035  call    cs:__imp_SendMessageW
0x18004303c  nop     dword ptr [rax+rax+00h]
0x180043041  xor     ebx, ebx
0x180043043  mov     rsi, rax
0x180043046  test    eax, eax
0x180043048  jle     short loc_180043082
0x18004304a  mov     r8d, ebx; wParam
0x18004304d  xor     r9d, r9d; lParam
0x180043050  mov     edx, 150h; Msg
0x180043055  mov     rcx, rbp; hWnd
0x180043058  call    cs:__imp_SendMessageW
0x18004305f  nop     dword ptr [rax+rax+00h]
0x180043064  cmp     eax, r14d
0x180043067  jz      short loc_180043071
0x180043069  inc     ebx
0x18004306b  cmp     ebx, esi
0x18004306d  jl      short loc_18004304A
0x18004306f  jmp     short loc_180043082
0x180043071  mov     edx, ebx
0x180043073  mov     rcx, rdi
0x180043076  call    cs:__imp_?SetSelection@Combobox@DirectUI@@QEAAJH@Z; DirectUI::Combobox::SetSelection(int)
0x18004307d  nop     dword ptr [rax+rax+00h]
0x180043082  add     rsp, 20h
0x180043086  pop     r14
0x180043088  pop     rdi
0x180043089  pop     rsi
0x18004308a  pop     rbp
0x18004308b  pop     rbx
0x18004308c  retn
```
