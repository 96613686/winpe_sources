# CACDot1XPage::InitReadOnlyProfile(void)

- ea: `0x180013004`
- end: `0x180013117`
- name: `?InitReadOnlyProfile@CACDot1XPage@@AEAAXXZ`
- size: `275`
- prototype: `void __fastcall(CACDot1XPage *__hidden this)`
- caller_count: `1`
- callee_count: `0`
- tags: ``

## callers

- `0x180013570`

## import_xrefs

- `USER32!EnableWindow` at `0x180013021`
- `USER32!EnableWindow` at `0x18001303b`
- `USER32!EnableWindow` at `0x180013055`
- `USER32!EnableWindow` at `0x18001306f`
- `USER32!EnableWindow` at `0x180013089`
- `USER32!EnableWindow` at `0x1800130a3`
- `USER32!EnableWindow` at `0x1800130bd`
- `USER32!EnableWindow` at `0x1800130d7`
- `USER32!EnableWindow` at `0x1800130f1`
- `USER32!EnableWindow` at `0x180013021`
- `USER32!EnableWindow` at `0x18001303b`
- `USER32!EnableWindow` at `0x180013055`
- `USER32!EnableWindow` at `0x18001306f`
- `USER32!EnableWindow` at `0x180013089`
- `USER32!EnableWindow` at `0x1800130a3`
- `USER32!EnableWindow` at `0x1800130bd`
- `USER32!EnableWindow` at `0x1800130d7`
- `USER32!EnableWindow` at `0x1800130f1`
- `USER32!EnableWindow` at `0x180013110`
- `USER32!GetDlgItem` at `0x180013016`
- `USER32!GetDlgItem` at `0x180013030`
- `USER32!GetDlgItem` at `0x18001304a`
- `USER32!GetDlgItem` at `0x180013064`
- `USER32!GetDlgItem` at `0x18001307e`
- `USER32!GetDlgItem` at `0x180013098`
- `USER32!GetDlgItem` at `0x1800130b2`
- `USER32!GetDlgItem` at `0x1800130cc`
- `USER32!GetDlgItem` at `0x1800130e6`
- `USER32!GetDlgItem` at `0x180013100`
- `USER32!GetDlgItem` at `0x180013016`
- `USER32!GetDlgItem` at `0x180013030`
- `USER32!GetDlgItem` at `0x18001304a`
- `USER32!GetDlgItem` at `0x180013064`
- `USER32!GetDlgItem` at `0x18001307e`
- `USER32!GetDlgItem` at `0x180013098`
- `USER32!GetDlgItem` at `0x1800130b2`
- `USER32!GetDlgItem` at `0x1800130cc`
- `USER32!GetDlgItem` at `0x1800130e6`
- `USER32!GetDlgItem` at `0x180013100`

## pseudocode

```c
void __fastcall CACDot1XPage::InitReadOnlyProfile(HWND *this)
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

  DlgItem = GetDlgItem(this[1], 16004);
  EnableWindow(DlgItem, 0);
  v3 = GetDlgItem(this[1], 16005);
  EnableWindow(v3, 0);
  v4 = GetDlgItem(this[1], 16006);
  EnableWindow(v4, 0);
  v5 = GetDlgItem(this[1], 16007);
  EnableWindow(v5, 0);
  v6 = GetDlgItem(this[1], 16008);
  EnableWindow(v6, 0);
  v7 = GetDlgItem(this[1], 16010);
  EnableWindow(v7, 0);
  v8 = GetDlgItem(this[1], 16012);
  EnableWindow(v8, 0);
  v9 = GetDlgItem(this[1], 16023);
  EnableWindow(v9, 0);
  v10 = GetDlgItem(this[1], 16001);
  EnableWindow(v10, 0);
  v11 = GetDlgItem(this[1], 16002);
  EnableWindow(v11, 0);
}

```

## disassembly

```asm
0x180013004  push    rbx
0x180013006  sub     rsp, 20h
0x18001300a  mov     rbx, rcx
0x18001300d  mov     edx, 3E84h; nIDDlgItem
0x180013012  mov     rcx, [rcx+8]; hDlg
0x180013016  call    cs:__imp_GetDlgItem
0x18001301c  mov     rcx, rax; hWnd
0x18001301f  xor     edx, edx; bEnable
0x180013021  call    cs:__imp_EnableWindow
0x180013027  mov     rcx, [rbx+8]; hDlg
0x18001302b  mov     edx, 3E85h; nIDDlgItem
0x180013030  call    cs:__imp_GetDlgItem
0x180013036  mov     rcx, rax; hWnd
0x180013039  xor     edx, edx; bEnable
0x18001303b  call    cs:__imp_EnableWindow
0x180013041  mov     rcx, [rbx+8]; hDlg
0x180013045  mov     edx, 3E86h; nIDDlgItem
0x18001304a  call    cs:__imp_GetDlgItem
0x180013050  mov     rcx, rax; hWnd
0x180013053  xor     edx, edx; bEnable
0x180013055  call    cs:__imp_EnableWindow
0x18001305b  mov     rcx, [rbx+8]; hDlg
0x18001305f  mov     edx, 3E87h; nIDDlgItem
0x180013064  call    cs:__imp_GetDlgItem
0x18001306a  mov     rcx, rax; hWnd
0x18001306d  xor     edx, edx; bEnable
0x18001306f  call    cs:__imp_EnableWindow
0x180013075  mov     rcx, [rbx+8]; hDlg
0x180013079  mov     edx, 3E88h; nIDDlgItem
0x18001307e  call    cs:__imp_GetDlgItem
0x180013084  mov     rcx, rax; hWnd
0x180013087  xor     edx, edx; bEnable
0x180013089  call    cs:__imp_EnableWindow
0x18001308f  mov     rcx, [rbx+8]; hDlg
0x180013093  mov     edx, 3E8Ah; nIDDlgItem
0x180013098  call    cs:__imp_GetDlgItem
0x18001309e  mov     rcx, rax; hWnd
0x1800130a1  xor     edx, edx; bEnable
0x1800130a3  call    cs:__imp_EnableWindow
0x1800130a9  mov     rcx, [rbx+8]; hDlg
0x1800130ad  mov     edx, 3E8Ch; nIDDlgItem
0x1800130b2  call    cs:__imp_GetDlgItem
0x1800130b8  mov     rcx, rax; hWnd
0x1800130bb  xor     edx, edx; bEnable
0x1800130bd  call    cs:__imp_EnableWindow
0x1800130c3  mov     rcx, [rbx+8]; hDlg
0x1800130c7  mov     edx, 3E97h; nIDDlgItem
0x1800130cc  call    cs:__imp_GetDlgItem
0x1800130d2  mov     rcx, rax; hWnd
0x1800130d5  xor     edx, edx; bEnable
0x1800130d7  call    cs:__imp_EnableWindow
0x1800130dd  mov     rcx, [rbx+8]; hDlg
0x1800130e1  mov     edx, 3E81h; nIDDlgItem
0x1800130e6  call    cs:__imp_GetDlgItem
0x1800130ec  mov     rcx, rax; hWnd
0x1800130ef  xor     edx, edx; bEnable
0x1800130f1  call    cs:__imp_EnableWindow
0x1800130f7  mov     rcx, [rbx+8]; hDlg
0x1800130fb  mov     edx, 3E82h; nIDDlgItem
0x180013100  call    cs:__imp_GetDlgItem
0x180013106  mov     rcx, rax
0x180013109  xor     edx, edx
0x18001310b  add     rsp, 20h
0x18001310f  pop     rbx
0x180013110  jmp     cs:__imp_EnableWindow
```
