# CACDot11Page::InitReadOnlyProfile(void)

- ea: `0x180011e30`
- end: `0x180011f96`
- name: `?InitReadOnlyProfile@CACDot11Page@@AEAAXXZ`
- size: `358`
- prototype: `void __fastcall(CACDot11Page *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180012124`

## callees

- `0x180012660`

## import_xrefs

- `USER32!EnableWindow` at `0x180011e52`
- `USER32!EnableWindow` at `0x180011e6c`
- `USER32!EnableWindow` at `0x180011e86`
- `USER32!EnableWindow` at `0x180011ea0`
- `USER32!EnableWindow` at `0x180011eba`
- `USER32!EnableWindow` at `0x180011ed4`
- `USER32!EnableWindow` at `0x180011eee`
- `USER32!EnableWindow` at `0x180011f08`
- `USER32!EnableWindow` at `0x180011f22`
- `USER32!EnableWindow` at `0x180011f3c`
- `USER32!EnableWindow` at `0x180011f56`
- `USER32!EnableWindow` at `0x180011f70`
- `USER32!EnableWindow` at `0x180011e52`
- `USER32!EnableWindow` at `0x180011e6c`
- `USER32!EnableWindow` at `0x180011e86`
- `USER32!EnableWindow` at `0x180011ea0`
- `USER32!EnableWindow` at `0x180011eba`
- `USER32!EnableWindow` at `0x180011ed4`
- `USER32!EnableWindow` at `0x180011eee`
- `USER32!EnableWindow` at `0x180011f08`
- `USER32!EnableWindow` at `0x180011f22`
- `USER32!EnableWindow` at `0x180011f3c`
- `USER32!EnableWindow` at `0x180011f56`
- `USER32!EnableWindow` at `0x180011f70`
- `USER32!EnableWindow` at `0x180011f8f`
- `USER32!GetDlgItem` at `0x180011e47`
- `USER32!GetDlgItem` at `0x180011e61`
- `USER32!GetDlgItem` at `0x180011e7b`
- `USER32!GetDlgItem` at `0x180011e95`
- `USER32!GetDlgItem` at `0x180011eaf`
- `USER32!GetDlgItem` at `0x180011ec9`
- `USER32!GetDlgItem` at `0x180011ee3`
- `USER32!GetDlgItem` at `0x180011efd`
- `USER32!GetDlgItem` at `0x180011f17`
- `USER32!GetDlgItem` at `0x180011f31`
- `USER32!GetDlgItem` at `0x180011f4b`
- `USER32!GetDlgItem` at `0x180011f65`
- `USER32!GetDlgItem` at `0x180011f7f`
- `USER32!GetDlgItem` at `0x180011e47`
- `USER32!GetDlgItem` at `0x180011e61`
- `USER32!GetDlgItem` at `0x180011e7b`
- `USER32!GetDlgItem` at `0x180011e95`
- `USER32!GetDlgItem` at `0x180011eaf`
- `USER32!GetDlgItem` at `0x180011ec9`
- `USER32!GetDlgItem` at `0x180011ee3`
- `USER32!GetDlgItem` at `0x180011efd`
- `USER32!GetDlgItem` at `0x180011f17`
- `USER32!GetDlgItem` at `0x180011f31`
- `USER32!GetDlgItem` at `0x180011f4b`
- `USER32!GetDlgItem` at `0x180011f65`
- `USER32!GetDlgItem` at `0x180011f7f`

## pseudocode

```c
void __fastcall CACDot11Page::InitReadOnlyProfile(HWND *this)
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
  HWND v12; // rax
  HWND v13; // rax
  HWND v14; // rax

  CACDot11Page::RefreshControls((CACDot11Page *)this);
  DlgItem = GetDlgItem(this[1], 16013);
  EnableWindow(DlgItem, 0);
  v3 = GetDlgItem(this[1], 16014);
  EnableWindow(v3, 0);
  v4 = GetDlgItem(this[1], 16015);
  EnableWindow(v4, 0);
  v5 = GetDlgItem(this[1], 16016);
  EnableWindow(v5, 0);
  v6 = GetDlgItem(this[1], 16017);
  EnableWindow(v6, 0);
  v7 = GetDlgItem(this[1], 16018);
  EnableWindow(v7, 0);
  v8 = GetDlgItem(this[1], 16019);
  EnableWindow(v8, 0);
  v9 = GetDlgItem(this[1], 16020);
  EnableWindow(v9, 0);
  v10 = GetDlgItem(this[1], 16021);
  EnableWindow(v10, 0);
  v11 = GetDlgItem(this[1], 16025);
  EnableWindow(v11, 0);
  v12 = GetDlgItem(this[1], 16026);
  EnableWindow(v12, 0);
  v13 = GetDlgItem(this[1], 16027);
  EnableWindow(v13, 0);
  v14 = GetDlgItem(this[1], 16022);
  EnableWindow(v14, 0);
}

```

## disassembly

```asm
0x180011e30  push    rbx
0x180011e32  sub     rsp, 20h
0x180011e36  mov     rbx, rcx
0x180011e39  call    ?RefreshControls@CACDot11Page@@QEAA_JXZ; CACDot11Page::RefreshControls(void)
0x180011e3e  mov     rcx, [rbx+8]; hDlg
0x180011e42  mov     edx, 3E8Dh; nIDDlgItem
0x180011e47  call    cs:__imp_GetDlgItem
0x180011e4d  mov     rcx, rax; hWnd
0x180011e50  xor     edx, edx; bEnable
0x180011e52  call    cs:__imp_EnableWindow
0x180011e58  mov     rcx, [rbx+8]; hDlg
0x180011e5c  mov     edx, 3E8Eh; nIDDlgItem
0x180011e61  call    cs:__imp_GetDlgItem
0x180011e67  mov     rcx, rax; hWnd
0x180011e6a  xor     edx, edx; bEnable
0x180011e6c  call    cs:__imp_EnableWindow
0x180011e72  mov     rcx, [rbx+8]; hDlg
0x180011e76  mov     edx, 3E8Fh; nIDDlgItem
0x180011e7b  call    cs:__imp_GetDlgItem
0x180011e81  mov     rcx, rax; hWnd
0x180011e84  xor     edx, edx; bEnable
0x180011e86  call    cs:__imp_EnableWindow
0x180011e8c  mov     rcx, [rbx+8]; hDlg
0x180011e90  mov     edx, 3E90h; nIDDlgItem
0x180011e95  call    cs:__imp_GetDlgItem
0x180011e9b  mov     rcx, rax; hWnd
0x180011e9e  xor     edx, edx; bEnable
0x180011ea0  call    cs:__imp_EnableWindow
0x180011ea6  mov     rcx, [rbx+8]; hDlg
0x180011eaa  mov     edx, 3E91h; nIDDlgItem
0x180011eaf  call    cs:__imp_GetDlgItem
0x180011eb5  mov     rcx, rax; hWnd
0x180011eb8  xor     edx, edx; bEnable
0x180011eba  call    cs:__imp_EnableWindow
0x180011ec0  mov     rcx, [rbx+8]; hDlg
0x180011ec4  mov     edx, 3E92h; nIDDlgItem
0x180011ec9  call    cs:__imp_GetDlgItem
0x180011ecf  mov     rcx, rax; hWnd
0x180011ed2  xor     edx, edx; bEnable
0x180011ed4  call    cs:__imp_EnableWindow
0x180011eda  mov     rcx, [rbx+8]; hDlg
0x180011ede  mov     edx, 3E93h; nIDDlgItem
0x180011ee3  call    cs:__imp_GetDlgItem
0x180011ee9  mov     rcx, rax; hWnd
0x180011eec  xor     edx, edx; bEnable
0x180011eee  call    cs:__imp_EnableWindow
0x180011ef4  mov     rcx, [rbx+8]; hDlg
0x180011ef8  mov     edx, 3E94h; nIDDlgItem
0x180011efd  call    cs:__imp_GetDlgItem
0x180011f03  mov     rcx, rax; hWnd
0x180011f06  xor     edx, edx; bEnable
0x180011f08  call    cs:__imp_EnableWindow
0x180011f0e  mov     rcx, [rbx+8]; hDlg
0x180011f12  mov     edx, 3E95h; nIDDlgItem
0x180011f17  call    cs:__imp_GetDlgItem
0x180011f1d  mov     rcx, rax; hWnd
0x180011f20  xor     edx, edx; bEnable
0x180011f22  call    cs:__imp_EnableWindow
0x180011f28  mov     rcx, [rbx+8]; hDlg
0x180011f2c  mov     edx, 3E99h; nIDDlgItem
0x180011f31  call    cs:__imp_GetDlgItem
0x180011f37  mov     rcx, rax; hWnd
0x180011f3a  xor     edx, edx; bEnable
0x180011f3c  call    cs:__imp_EnableWindow
0x180011f42  mov     rcx, [rbx+8]; hDlg
0x180011f46  mov     edx, 3E9Ah; nIDDlgItem
0x180011f4b  call    cs:__imp_GetDlgItem
0x180011f51  mov     rcx, rax; hWnd
0x180011f54  xor     edx, edx; bEnable
0x180011f56  call    cs:__imp_EnableWindow
0x180011f5c  mov     rcx, [rbx+8]; hDlg
0x180011f60  mov     edx, 3E9Bh; nIDDlgItem
0x180011f65  call    cs:__imp_GetDlgItem
0x180011f6b  mov     rcx, rax; hWnd
0x180011f6e  xor     edx, edx; bEnable
0x180011f70  call    cs:__imp_EnableWindow
0x180011f76  mov     rcx, [rbx+8]; hDlg
0x180011f7a  mov     edx, 3E96h; nIDDlgItem
0x180011f7f  call    cs:__imp_GetDlgItem
0x180011f85  mov     rcx, rax
0x180011f88  xor     edx, edx
0x180011f8a  add     rsp, 20h
0x180011f8e  pop     rbx
0x180011f8f  jmp     cs:__imp_EnableWindow
```
