# FastRoamingControls::UpdateUIValues(void)

- ea: `0x1800128bc`
- end: `0x18001295e`
- name: `?UpdateUIValues@FastRoamingControls@@QEAAXXZ`
- size: `162`
- prototype: `void __fastcall(FastRoamingControls *__hidden this)`
- caller_count: `2`
- callee_count: `2`
- tags: `installer_update`

## callers

- `0x180012124`
- `0x18001231c`

## callees

- `0x180011a80`
- `0x180012774`

## import_xrefs

- `USER32!CheckDlgButton` at `0x1800128ef`
- `USER32!CheckDlgButton` at `0x180012909`
- `USER32!CheckDlgButton` at `0x1800128ef`
- `USER32!CheckDlgButton` at `0x180012909`
- `USER32!SetDlgItemInt` at `0x18001291f`
- `USER32!SetDlgItemInt` at `0x180012935`
- `USER32!SetDlgItemInt` at `0x18001294b`
- `USER32!SetDlgItemInt` at `0x18001291f`
- `USER32!SetDlgItemInt` at `0x180012935`
- `USER32!SetDlgItemInt` at `0x18001294b`

## pseudocode

```c
void __fastcall FastRoamingControls::UpdateUIValues(FastRoamingControls *this)
{
  *((_QWORD *)this + 1) = *(_QWORD *)(*((_QWORD *)this + 2) + 8LL);
  FastRoamingControls::EnableAllControls(this, 1);
  CheckDlgButton(*((HWND *)this + 1), 16014, *((_DWORD *)this + 6) != 0);
  CheckDlgButton(*((HWND *)this + 1), 16019, *((_DWORD *)this + 9) != 0);
  SetDlgItemInt(*((HWND *)this + 1), 16016, *((_DWORD *)this + 7), 0);
  SetDlgItemInt(*((HWND *)this + 1), 16018, *((_DWORD *)this + 8), 0);
  SetDlgItemInt(*((HWND *)this + 1), 16021, *((_DWORD *)this + 10), 0);
  FastRoamingControls::RefreshControls(this);
}

```

## disassembly

```asm
0x1800128bc  push    rbx
0x1800128be  sub     rsp, 20h
0x1800128c2  mov     rax, [rcx+10h]
0x1800128c6  mov     rbx, rcx
0x1800128c9  mov     rdx, [rax+8]
0x1800128cd  mov     [rcx+8], rdx
0x1800128d1  mov     edx, 1; int
0x1800128d6  call    ?EnableAllControls@FastRoamingControls@@QEAAXH@Z; FastRoamingControls::EnableAllControls(int)
0x1800128db  mov     rcx, [rbx+8]; hDlg
0x1800128df  xor     r8d, r8d
0x1800128e2  cmp     [rbx+18h], r8d
0x1800128e6  mov     edx, 3E8Eh; nIDButton
0x1800128eb  setnz   r8b; uCheck
0x1800128ef  call    cs:__imp_CheckDlgButton
0x1800128f5  mov     rcx, [rbx+8]; hDlg
0x1800128f9  xor     r8d, r8d
0x1800128fc  cmp     [rbx+24h], r8d
0x180012900  mov     edx, 3E93h; nIDButton
0x180012905  setnz   r8b; uCheck
0x180012909  call    cs:__imp_CheckDlgButton
0x18001290f  mov     r8d, [rbx+1Ch]; uValue
0x180012913  xor     r9d, r9d; bSigned
0x180012916  mov     rcx, [rbx+8]; hDlg
0x18001291a  mov     edx, 3E90h; nIDDlgItem
0x18001291f  call    cs:__imp_SetDlgItemInt
0x180012925  mov     r8d, [rbx+20h]; uValue
0x180012929  xor     r9d, r9d; bSigned
0x18001292c  mov     rcx, [rbx+8]; hDlg
0x180012930  mov     edx, 3E92h; nIDDlgItem
0x180012935  call    cs:__imp_SetDlgItemInt
0x18001293b  mov     r8d, [rbx+28h]; uValue
0x18001293f  xor     r9d, r9d; bSigned
0x180012942  mov     rcx, [rbx+8]; hDlg
0x180012946  mov     edx, 3E95h; nIDDlgItem
0x18001294b  call    cs:__imp_SetDlgItemInt
0x180012951  mov     rcx, rbx; this
0x180012954  add     rsp, 20h
0x180012958  pop     rbx
0x180012959  jmp     ?RefreshControls@FastRoamingControls@@QEAAXXZ; FastRoamingControls::RefreshControls(void)
```
