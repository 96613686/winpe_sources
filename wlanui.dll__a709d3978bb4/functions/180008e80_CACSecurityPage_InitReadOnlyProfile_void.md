# CACSecurityPage::InitReadOnlyProfile(void)

- ea: `0x180008e80`
- end: `0x180009015`
- name: `?InitReadOnlyProfile@CACSecurityPage@@AEAAXXZ`
- size: `405`
- prototype: `void __fastcall(CACSecurityPage *__hidden this)`
- caller_count: `1`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x18000a7f8`

## import_xrefs

- `USER32!EnableWindow` at `0x180008e9d`
- `USER32!EnableWindow` at `0x180008eb7`
- `USER32!EnableWindow` at `0x180008ed1`
- `USER32!EnableWindow` at `0x180008eeb`
- `USER32!EnableWindow` at `0x180008f05`
- `USER32!EnableWindow` at `0x180008f1f`
- `USER32!EnableWindow` at `0x180008f39`
- `USER32!EnableWindow` at `0x180008f53`
- `USER32!EnableWindow` at `0x180008f6d`
- `USER32!EnableWindow` at `0x180008f87`
- `USER32!EnableWindow` at `0x180008fa1`
- `USER32!EnableWindow` at `0x180008fbb`
- `USER32!EnableWindow` at `0x180008fd5`
- `USER32!EnableWindow` at `0x180008fef`
- `USER32!EnableWindow` at `0x180008e9d`
- `USER32!EnableWindow` at `0x180008eb7`
- `USER32!EnableWindow` at `0x180008ed1`
- `USER32!EnableWindow` at `0x180008eeb`
- `USER32!EnableWindow` at `0x180008f05`
- `USER32!EnableWindow` at `0x180008f1f`
- `USER32!EnableWindow` at `0x180008f39`
- `USER32!EnableWindow` at `0x180008f53`
- `USER32!EnableWindow` at `0x180008f6d`
- `USER32!EnableWindow` at `0x180008f87`
- `USER32!EnableWindow` at `0x180008fa1`
- `USER32!EnableWindow` at `0x180008fbb`
- `USER32!EnableWindow` at `0x180008fd5`
- `USER32!EnableWindow` at `0x180008fef`
- `USER32!EnableWindow` at `0x18000900e`
- `USER32!GetDlgItem` at `0x180008e92`
- `USER32!GetDlgItem` at `0x180008eac`
- `USER32!GetDlgItem` at `0x180008ec6`
- `USER32!GetDlgItem` at `0x180008ee0`
- `USER32!GetDlgItem` at `0x180008efa`
- `USER32!GetDlgItem` at `0x180008f14`
- `USER32!GetDlgItem` at `0x180008f2e`
- `USER32!GetDlgItem` at `0x180008f48`
- `USER32!GetDlgItem` at `0x180008f62`
- `USER32!GetDlgItem` at `0x180008f7c`
- `USER32!GetDlgItem` at `0x180008f96`
- `USER32!GetDlgItem` at `0x180008fb0`
- `USER32!GetDlgItem` at `0x180008fca`
- `USER32!GetDlgItem` at `0x180008fe4`
- `USER32!GetDlgItem` at `0x180008ffe`
- `USER32!GetDlgItem` at `0x180008e92`
- `USER32!GetDlgItem` at `0x180008eac`
- `USER32!GetDlgItem` at `0x180008ec6`
- `USER32!GetDlgItem` at `0x180008ee0`
- `USER32!GetDlgItem` at `0x180008efa`
- `USER32!GetDlgItem` at `0x180008f14`
- `USER32!GetDlgItem` at `0x180008f2e`
- `USER32!GetDlgItem` at `0x180008f48`
- `USER32!GetDlgItem` at `0x180008f62`
- `USER32!GetDlgItem` at `0x180008f7c`
- `USER32!GetDlgItem` at `0x180008f96`
- `USER32!GetDlgItem` at `0x180008fb0`
- `USER32!GetDlgItem` at `0x180008fca`
- `USER32!GetDlgItem` at `0x180008fe4`
- `USER32!GetDlgItem` at `0x180008ffe`

## pseudocode

```c
void __fastcall CACSecurityPage::InitReadOnlyProfile(HWND *this)
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
  HWND v15; // rax
  HWND v16; // rax

  DlgItem = GetDlgItem(this[1], 1109);
  EnableWindow(DlgItem, 0);
  v3 = GetDlgItem(this[1], 15076);
  EnableWindow(v3, 0);
  v4 = GetDlgItem(this[1], 1110);
  EnableWindow(v4, 0);
  v5 = GetDlgItem(this[1], 1111);
  EnableWindow(v5, 0);
  v6 = GetDlgItem(this[1], 1113);
  EnableWindow(v6, 0);
  v7 = GetDlgItem(this[1], 1112);
  EnableWindow(v7, 0);
  v8 = GetDlgItem(this[1], 1126);
  EnableWindow(v8, 0);
  v9 = GetDlgItem(this[1], 1125);
  EnableWindow(v9, 0);
  v10 = GetDlgItem(this[1], 1118);
  EnableWindow(v10, 0);
  v11 = GetDlgItem(this[1], 1119);
  EnableWindow(v11, 0);
  v12 = GetDlgItem(this[1], 1120);
  EnableWindow(v12, 0);
  v13 = GetDlgItem(this[1], 1121);
  EnableWindow(v13, 0);
  v14 = GetDlgItem(this[1], 15077);
  EnableWindow(v14, 0);
  v15 = GetDlgItem(this[1], 15078);
  EnableWindow(v15, 0);
  v16 = GetDlgItem(this[1], 15079);
  EnableWindow(v16, 0);
}

```

## disassembly

```asm
0x180008e80  push    rbx
0x180008e82  sub     rsp, 20h
0x180008e86  mov     rbx, rcx
0x180008e89  mov     edx, 455h; nIDDlgItem
0x180008e8e  mov     rcx, [rcx+8]; hDlg
0x180008e92  call    cs:__imp_GetDlgItem
0x180008e98  mov     rcx, rax; hWnd
0x180008e9b  xor     edx, edx; bEnable
0x180008e9d  call    cs:__imp_EnableWindow
0x180008ea3  mov     rcx, [rbx+8]; hDlg
0x180008ea7  mov     edx, 3AE4h; nIDDlgItem
0x180008eac  call    cs:__imp_GetDlgItem
0x180008eb2  mov     rcx, rax; hWnd
0x180008eb5  xor     edx, edx; bEnable
0x180008eb7  call    cs:__imp_EnableWindow
0x180008ebd  mov     rcx, [rbx+8]; hDlg
0x180008ec1  mov     edx, 456h; nIDDlgItem
0x180008ec6  call    cs:__imp_GetDlgItem
0x180008ecc  mov     rcx, rax; hWnd
0x180008ecf  xor     edx, edx; bEnable
0x180008ed1  call    cs:__imp_EnableWindow
0x180008ed7  mov     rcx, [rbx+8]; hDlg
0x180008edb  mov     edx, 457h; nIDDlgItem
0x180008ee0  call    cs:__imp_GetDlgItem
0x180008ee6  mov     rcx, rax; hWnd
0x180008ee9  xor     edx, edx; bEnable
0x180008eeb  call    cs:__imp_EnableWindow
0x180008ef1  mov     rcx, [rbx+8]; hDlg
0x180008ef5  mov     edx, 459h; nIDDlgItem
0x180008efa  call    cs:__imp_GetDlgItem
0x180008f00  mov     rcx, rax; hWnd
0x180008f03  xor     edx, edx; bEnable
0x180008f05  call    cs:__imp_EnableWindow
0x180008f0b  mov     rcx, [rbx+8]; hDlg
0x180008f0f  mov     edx, 458h; nIDDlgItem
0x180008f14  call    cs:__imp_GetDlgItem
0x180008f1a  mov     rcx, rax; hWnd
0x180008f1d  xor     edx, edx; bEnable
0x180008f1f  call    cs:__imp_EnableWindow
0x180008f25  mov     rcx, [rbx+8]; hDlg
0x180008f29  mov     edx, 466h; nIDDlgItem
0x180008f2e  call    cs:__imp_GetDlgItem
0x180008f34  mov     rcx, rax; hWnd
0x180008f37  xor     edx, edx; bEnable
0x180008f39  call    cs:__imp_EnableWindow
0x180008f3f  mov     rcx, [rbx+8]; hDlg
0x180008f43  mov     edx, 465h; nIDDlgItem
0x180008f48  call    cs:__imp_GetDlgItem
0x180008f4e  mov     rcx, rax; hWnd
0x180008f51  xor     edx, edx; bEnable
0x180008f53  call    cs:__imp_EnableWindow
0x180008f59  mov     rcx, [rbx+8]; hDlg
0x180008f5d  mov     edx, 45Eh; nIDDlgItem
0x180008f62  call    cs:__imp_GetDlgItem
0x180008f68  mov     rcx, rax; hWnd
0x180008f6b  xor     edx, edx; bEnable
0x180008f6d  call    cs:__imp_EnableWindow
0x180008f73  mov     rcx, [rbx+8]; hDlg
0x180008f77  mov     edx, 45Fh; nIDDlgItem
0x180008f7c  call    cs:__imp_GetDlgItem
0x180008f82  mov     rcx, rax; hWnd
0x180008f85  xor     edx, edx; bEnable
0x180008f87  call    cs:__imp_EnableWindow
0x180008f8d  mov     rcx, [rbx+8]; hDlg
0x180008f91  mov     edx, 460h; nIDDlgItem
0x180008f96  call    cs:__imp_GetDlgItem
0x180008f9c  mov     rcx, rax; hWnd
0x180008f9f  xor     edx, edx; bEnable
0x180008fa1  call    cs:__imp_EnableWindow
0x180008fa7  mov     rcx, [rbx+8]; hDlg
0x180008fab  mov     edx, 461h; nIDDlgItem
0x180008fb0  call    cs:__imp_GetDlgItem
0x180008fb6  mov     rcx, rax; hWnd
0x180008fb9  xor     edx, edx; bEnable
0x180008fbb  call    cs:__imp_EnableWindow
0x180008fc1  mov     rcx, [rbx+8]; hDlg
0x180008fc5  mov     edx, 3AE5h; nIDDlgItem
0x180008fca  call    cs:__imp_GetDlgItem
0x180008fd0  mov     rcx, rax; hWnd
0x180008fd3  xor     edx, edx; bEnable
0x180008fd5  call    cs:__imp_EnableWindow
0x180008fdb  mov     rcx, [rbx+8]; hDlg
0x180008fdf  mov     edx, 3AE6h; nIDDlgItem
0x180008fe4  call    cs:__imp_GetDlgItem
0x180008fea  mov     rcx, rax; hWnd
0x180008fed  xor     edx, edx; bEnable
0x180008fef  call    cs:__imp_EnableWindow
0x180008ff5  mov     rcx, [rbx+8]; hDlg
0x180008ff9  mov     edx, 3AE7h; nIDDlgItem
0x180008ffe  call    cs:__imp_GetDlgItem
0x180009004  mov     rcx, rax
0x180009007  xor     edx, edx
0x180009009  add     rsp, 20h
0x18000900d  pop     rbx
0x18000900e  jmp     cs:__imp_EnableWindow
```
