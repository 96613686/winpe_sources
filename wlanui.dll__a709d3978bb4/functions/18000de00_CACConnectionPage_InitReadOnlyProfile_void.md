# CACConnectionPage::InitReadOnlyProfile(void)

- ea: `0x18000de00`
- end: `0x18000df13`
- name: `?InitReadOnlyProfile@CACConnectionPage@@AEAAXXZ`
- size: `275`
- prototype: `void __fastcall(CACConnectionPage *__hidden this)`
- caller_count: `1`
- callee_count: `0`
- tags: ``

## callers

- `0x18000e31c`

## import_xrefs

- `USER32!EnableWindow` at `0x18000de1d`
- `USER32!EnableWindow` at `0x18000de37`
- `USER32!EnableWindow` at `0x18000de51`
- `USER32!EnableWindow` at `0x18000de6b`
- `USER32!EnableWindow` at `0x18000de85`
- `USER32!EnableWindow` at `0x18000de9f`
- `USER32!EnableWindow` at `0x18000deb9`
- `USER32!EnableWindow` at `0x18000ded3`
- `USER32!EnableWindow` at `0x18000deed`
- `USER32!EnableWindow` at `0x18000de1d`
- `USER32!EnableWindow` at `0x18000de37`
- `USER32!EnableWindow` at `0x18000de51`
- `USER32!EnableWindow` at `0x18000de6b`
- `USER32!EnableWindow` at `0x18000de85`
- `USER32!EnableWindow` at `0x18000de9f`
- `USER32!EnableWindow` at `0x18000deb9`
- `USER32!EnableWindow` at `0x18000ded3`
- `USER32!EnableWindow` at `0x18000deed`
- `USER32!EnableWindow` at `0x18000df0c`
- `USER32!GetDlgItem` at `0x18000de12`
- `USER32!GetDlgItem` at `0x18000de2c`
- `USER32!GetDlgItem` at `0x18000de46`
- `USER32!GetDlgItem` at `0x18000de60`
- `USER32!GetDlgItem` at `0x18000de7a`
- `USER32!GetDlgItem` at `0x18000de94`
- `USER32!GetDlgItem` at `0x18000deae`
- `USER32!GetDlgItem` at `0x18000dec8`
- `USER32!GetDlgItem` at `0x18000dee2`
- `USER32!GetDlgItem` at `0x18000defc`
- `USER32!GetDlgItem` at `0x18000de12`
- `USER32!GetDlgItem` at `0x18000de2c`
- `USER32!GetDlgItem` at `0x18000de46`
- `USER32!GetDlgItem` at `0x18000de60`
- `USER32!GetDlgItem` at `0x18000de7a`
- `USER32!GetDlgItem` at `0x18000de94`
- `USER32!GetDlgItem` at `0x18000deae`
- `USER32!GetDlgItem` at `0x18000dec8`
- `USER32!GetDlgItem` at `0x18000dee2`
- `USER32!GetDlgItem` at `0x18000defc`

## pseudocode

```c
void __fastcall CACConnectionPage::InitReadOnlyProfile(HWND *this)
{
  HWND DlgItem; // rax
  HWND v3; // rax
  HWND v4; // rax
  HWND v5; // rax
  HWND v6; // rax
  HWND v7; // rax
  HWND v8; // rax
  HWND v9; // rax
  HWND v10; // rax
  HWND v11; // rax

  DlgItem = GetDlgItem(this[1], 1101);
  EnableWindow(DlgItem, 0);
  v3 = GetDlgItem(this[1], 15071);
  EnableWindow(v3, 0);
  v4 = GetDlgItem(this[1], 1100);
  EnableWindow(v4, 0);
  v5 = GetDlgItem(this[1], 15073);
  EnableWindow(v5, 0);
  v6 = GetDlgItem(this[1], 1127);
  EnableWindow(v6, 0);
  v7 = GetDlgItem(this[1], 1128);
  EnableWindow(v7, 0);
  v8 = GetDlgItem(this[1], 1104);
  EnableWindow(v8, 0);
  v9 = GetDlgItem(this[1], 1105);
  EnableWindow(v9, 0);
  v10 = GetDlgItem(this[1], 1106);
  EnableWindow(v10, 0);
  v11 = GetDlgItem(this[1], 15075);
  EnableWindow(v11, 0);
}

```

## disassembly

```asm
0x18000de00  push    rbx
0x18000de02  sub     rsp, 20h
0x18000de06  mov     rbx, rcx
0x18000de09  mov     edx, 44Dh; nIDDlgItem
0x18000de0e  mov     rcx, [rcx+8]; hDlg
0x18000de12  call    cs:__imp_GetDlgItem
0x18000de18  mov     rcx, rax; hWnd
0x18000de1b  xor     edx, edx; bEnable
0x18000de1d  call    cs:__imp_EnableWindow
0x18000de23  mov     rcx, [rbx+8]; hDlg
0x18000de27  mov     edx, 3ADFh; nIDDlgItem
0x18000de2c  call    cs:__imp_GetDlgItem
0x18000de32  mov     rcx, rax; hWnd
0x18000de35  xor     edx, edx; bEnable
0x18000de37  call    cs:__imp_EnableWindow
0x18000de3d  mov     rcx, [rbx+8]; hDlg
0x18000de41  mov     edx, 44Ch; nIDDlgItem
0x18000de46  call    cs:__imp_GetDlgItem
0x18000de4c  mov     rcx, rax; hWnd
0x18000de4f  xor     edx, edx; bEnable
0x18000de51  call    cs:__imp_EnableWindow
0x18000de57  mov     rcx, [rbx+8]; hDlg
0x18000de5b  mov     edx, 3AE1h; nIDDlgItem
0x18000de60  call    cs:__imp_GetDlgItem
0x18000de66  mov     rcx, rax; hWnd
0x18000de69  xor     edx, edx; bEnable
0x18000de6b  call    cs:__imp_EnableWindow
0x18000de71  mov     rcx, [rbx+8]; hDlg
0x18000de75  mov     edx, 467h; nIDDlgItem
0x18000de7a  call    cs:__imp_GetDlgItem
0x18000de80  mov     rcx, rax; hWnd
0x18000de83  xor     edx, edx; bEnable
0x18000de85  call    cs:__imp_EnableWindow
0x18000de8b  mov     rcx, [rbx+8]; hDlg
0x18000de8f  mov     edx, 468h; nIDDlgItem
0x18000de94  call    cs:__imp_GetDlgItem
0x18000de9a  mov     rcx, rax; hWnd
0x18000de9d  xor     edx, edx; bEnable
0x18000de9f  call    cs:__imp_EnableWindow
0x18000dea5  mov     rcx, [rbx+8]; hDlg
0x18000dea9  mov     edx, 450h; nIDDlgItem
0x18000deae  call    cs:__imp_GetDlgItem
0x18000deb4  mov     rcx, rax; hWnd
0x18000deb7  xor     edx, edx; bEnable
0x18000deb9  call    cs:__imp_EnableWindow
0x18000debf  mov     rcx, [rbx+8]; hDlg
0x18000dec3  mov     edx, 451h; nIDDlgItem
0x18000dec8  call    cs:__imp_GetDlgItem
0x18000dece  mov     rcx, rax; hWnd
0x18000ded1  xor     edx, edx; bEnable
0x18000ded3  call    cs:__imp_EnableWindow
0x18000ded9  mov     rcx, [rbx+8]; hDlg
0x18000dedd  mov     edx, 452h; nIDDlgItem
0x18000dee2  call    cs:__imp_GetDlgItem
0x18000dee8  mov     rcx, rax; hWnd
0x18000deeb  xor     edx, edx; bEnable
0x18000deed  call    cs:__imp_EnableWindow
0x18000def3  mov     rcx, [rbx+8]; hDlg
0x18000def7  mov     edx, 3AE3h; nIDDlgItem
0x18000defc  call    cs:__imp_GetDlgItem
0x18000df02  mov     rcx, rax
0x18000df05  xor     edx, edx
0x18000df07  add     rsp, 20h
0x18000df0b  pop     rbx
0x18000df0c  jmp     cs:__imp_EnableWindow
```
