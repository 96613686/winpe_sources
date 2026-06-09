# CACDot11Page::MoveFipsCheckBoxUp(int)

- ea: `0x180012068`
- end: `0x18001211b`
- name: `?MoveFipsCheckBoxUp@CACDot11Page@@QEAAXH@Z`
- size: `179`
- prototype: `void __fastcall(CACDot11Page *__hidden this, int)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180012660`

## callees

- `0x180012068`

## import_xrefs

- `USER32!MoveWindow` at `0x1800120f9`
- `USER32!MoveWindow` at `0x1800120f9`
- `USER32!InvalidateRect` at `0x180012108`
- `USER32!InvalidateRect` at `0x180012108`
- `USER32!GetDlgItem` at `0x1800120d5`
- `USER32!GetDlgItem` at `0x1800120d5`
- `USER32!GetWindowLongW` at `0x180012083`
- `USER32!GetWindowLongW` at `0x180012083`

## pseudocode

```c
void __fastcall CACDot11Page::MoveFipsCheckBoxUp(HWND *this, int a2)
{
  LONG WindowLongW; // eax
  int v5; // eax
  int v6; // esi
  int nHeight; // r14d
  int v8; // r15d
  int v9; // ebp
  int v10; // esi
  int v11; // edi
  HWND DlgItem; // rax

  WindowLongW = GetWindowLongW(this[1], -20);
  if ( *((_DWORD *)this + 14) )
  {
    v5 = WindowLongW & 0x400000;
    v6 = *((_DWORD *)this + 18);
    nHeight = *((_DWORD *)this + 20) - v6;
    v8 = *((_DWORD *)this + 17);
    v9 = *((_DWORD *)this + 19);
    if ( a2 )
      v6 = *((_DWORD *)this + 33);
    v10 = v6 - *((_DWORD *)this + 48);
    if ( v5 )
      v11 = *((_DWORD *)this + 49) - v9;
    else
      v11 = v8 - *((_DWORD *)this + 47);
    DlgItem = GetDlgItem(this[1], 16022);
    MoveWindow(DlgItem, v11, v10, v9 - v8, nHeight, 1);
    InvalidateRect(this[1], 0, 1);
  }
}

```

## disassembly

```asm
0x180012068  push    rbx
0x18001206a  push    rbp
0x18001206b  push    rsi
0x18001206c  push    rdi
0x18001206d  push    r14
0x18001206f  push    r15
0x180012071  sub     rsp, 38h
0x180012075  mov     edi, edx
0x180012077  mov     rbx, rcx
0x18001207a  mov     rcx, [rcx+8]; hWnd
0x18001207e  mov     edx, 0FFFFFFECh; nIndex
0x180012083  call    cs:__imp_GetWindowLongW
0x180012089  cmp     dword ptr [rbx+38h], 0
0x18001208d  jz      short loc_18001210E
0x18001208f  mov     r14d, [rbx+50h]
0x180012093  and     eax, 400000h
0x180012098  mov     esi, [rbx+48h]
0x18001209b  sub     r14d, esi
0x18001209e  mov     r15d, [rbx+44h]
0x1800120a2  mov     ebp, [rbx+4Ch]
0x1800120a5  test    edi, edi
0x1800120a7  jz      short loc_1800120AF
0x1800120a9  mov     esi, [rbx+84h]
0x1800120af  sub     esi, [rbx+0C0h]
0x1800120b5  test    eax, eax
0x1800120b7  jz      short loc_1800120C3
0x1800120b9  mov     edi, [rbx+0C4h]
0x1800120bf  sub     edi, ebp
0x1800120c1  jmp     short loc_1800120CC
0x1800120c3  mov     edi, r15d
0x1800120c6  sub     edi, [rbx+0BCh]
0x1800120cc  mov     rcx, [rbx+8]; hDlg
0x1800120d0  mov     edx, 3E96h; nIDDlgItem
0x1800120d5  call    cs:__imp_GetDlgItem
0x1800120db  sub     ebp, r15d
0x1800120de  mov     r8d, esi; Y
0x1800120e1  mov     r15d, 1
0x1800120e7  mov     r9d, ebp; nWidth
0x1800120ea  mov     [rsp+68h+bRepaint], r15d; bRepaint
0x1800120ef  mov     edx, edi; X
0x1800120f1  mov     rcx, rax; hWnd
0x1800120f4  mov     [rsp+68h+nHeight], r14d; nHeight
0x1800120f9  call    cs:__imp_MoveWindow
0x1800120ff  mov     rcx, [rbx+8]; hWnd
0x180012103  mov     r8d, r15d; bErase
0x180012106  xor     edx, edx; lpRect
0x180012108  call    cs:__imp_InvalidateRect
0x18001210e  add     rsp, 38h
0x180012112  pop     r15
0x180012114  pop     r14
0x180012116  pop     rdi
0x180012117  pop     rsi
0x180012118  pop     rbp
0x180012119  pop     rbx
0x18001211a  retn
```
