# InputBoxPositionDialog

- ea: `0x180076ae4`
- end: `0x180076ee6`
- name: `InputBoxPositionDialog`
- size: `1026`
- prototype: `__int64 __fastcall(HWND hWnd)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x1800766f0`

## callees

- `0x180026570`
- `0x180076ae4`
- `0x180079490`

## import_xrefs

- `USER32!GetWindowRect` at `0x180076b8a`
- `USER32!GetWindowRect` at `0x180076baa`
- `USER32!GetWindowRect` at `0x180076d71`
- `USER32!GetWindowRect` at `0x180076b8a`
- `USER32!GetWindowRect` at `0x180076baa`
- `USER32!GetWindowRect` at `0x180076d71`
- `USER32!GetDC` at `0x180076c09`
- `USER32!GetDC` at `0x180076c09`
- `USER32!SetWindowPos` at `0x180076d3e`
- `USER32!SetWindowPos` at `0x180076dc6`
- `USER32!SetWindowPos` at `0x180076d3e`
- `USER32!SetWindowPos` at `0x180076dc6`
- `USER32!ShowWindow` at `0x180076b55`
- `USER32!ShowWindow` at `0x180076b55`
- `USER32!MapWindowPoints` at `0x180076d90`
- `USER32!MapWindowPoints` at `0x180076d90`
- `USER32!MoveWindow` at `0x180076e92`
- `USER32!MoveWindow` at `0x180076e92`
- `USER32!SendMessageA` at `0x180076c37`
- `USER32!SendMessageA` at `0x180076c37`
- `USER32!GetClientRect` at `0x180076be6`
- `USER32!GetClientRect` at `0x180076be6`
- `USER32!GetDlgItem` at `0x180076b3c`
- `USER32!GetDlgItem` at `0x180076bbe`
- `USER32!GetDlgItem` at `0x180076d5a`
- `USER32!GetDlgItem` at `0x180076b3c`
- `USER32!GetDlgItem` at `0x180076bbe`
- `USER32!GetDlgItem` at `0x180076d5a`
- `USER32!DrawTextW` at `0x180076c99`
- `USER32!DrawTextW` at `0x180076c99`
- `USER32!GetDesktopWindow` at `0x180076b96`
- `USER32!GetDesktopWindow` at `0x180076b96`
- `USER32!SetForegroundWindow` at `0x180076ea1`
- `USER32!SetForegroundWindow` at `0x180076ea1`
- `USER32!ReleaseDC` at `0x180076ccd`
- `USER32!ReleaseDC` at `0x180076ccd`
- `USER32!EnableWindow` at `0x180076b66`
- `USER32!EnableWindow` at `0x180076b66`
- `USER32!GetWindowTextW` at `0x180076c71`
- `USER32!GetWindowTextW` at `0x180076c71`
- `GDI32!SelectObject` at `0x180076c51`
- `GDI32!SelectObject` at `0x180076cbb`
- `GDI32!SelectObject` at `0x180076c51`
- `GDI32!SelectObject` at `0x180076cbb`

## pseudocode

```c
__int64 __fastcall InputBoxPositionDialog(HWND hWnd, __int64 a2)
{
  int v4; // eax
  HWND DlgItem; // rax
  HWND v6; // rbx
  HWND DesktopWindow; // rax
  HWND v8; // rax
  HWND v9; // rbx
  int v10; // r13d
  HDC DC; // rsi
  void *v12; // rax
  void *v13; // r12
  int v14; // edi
  int v15; // eax
  LONG bottom; // r8d
  LONG top; // r9d
  LONG v18; // esi
  int v19; // ecx
  HWND v20; // rbx
  int v21; // r11d
  int v22; // r8d
  LONG left; // r10d
  int v24; // edx
  int v26; // [rsp+40h] [rbp-C0h]
  int v27; // [rsp+44h] [rbp-BCh]
  tagRECT Rect; // [rsp+48h] [rbp-B8h] BYREF
  struct tagRECT v29; // [rsp+58h] [rbp-A8h] BYREF
  HGDIOBJ h[2]; // [rsp+68h] [rbp-98h] BYREF
  struct tagRECT rc; // [rsp+78h] [rbp-88h] BYREF
  WCHAR String[1024]; // [rsp+90h] [rbp-70h] BYREF

  v4 = COleScript::InSafeMode(*(COleScript **)(a2 + 48), 0);
  v26 = v4;
  if ( !*(_QWORD *)(a2 + 32) || v4 )
  {
    DlgItem = GetDlgItem(hWnd, 3);
    v6 = DlgItem;
    if ( DlgItem )
    {
      ShowWindow(DlgItem, 0);
      EnableWindow(v6, 0);
    }
  }
  Rect = 0;
  v29 = 0;
  GetWindowRect(hWnd, &Rect);
  DesktopWindow = GetDesktopWindow();
  GetWindowRect(DesktopWindow, &v29);
  v8 = GetDlgItem(hWnd, 1001);
  v9 = v8;
  if ( !v8
    || (rc = 0, GetClientRect(v8, &rc), v10 = rc.bottom - rc.top, v27 = rc.right - rc.left, (DC = GetDC(v9)) == 0) )
  {
    *(_DWORD *)(a2 + 56) = -2147418113;
    return 0;
  }
  h[0] = 0;
  v12 = (void *)SendMessageA(v9, 0x31u, 0, 0);
  v13 = v12;
  if ( v12 )
    h[0] = SelectObject(DC, v12);
  v14 = 0;
  if ( GetWindowTextW(v9, String, 1024) )
  {
    v15 = DrawTextW(DC, String, -1, &rc, 0xC50u);
    if ( v15 )
      v14 = v15 - v10;
  }
  if ( v13 )
    SelectObject(DC, h[0]);
  ReleaseDC(v9, DC);
  bottom = Rect.bottom;
  if ( v14 <= 0 )
  {
    v18 = v29.bottom;
    top = v29.top;
    goto LABEL_21;
  }
  if ( !v26 )
    goto LABEL_19;
  top = v29.top;
  v18 = v29.bottom;
  v19 = v29.bottom + Rect.top - Rect.bottom - v29.top;
  if ( v14 <= v19 )
    goto LABEL_19;
  if ( v19 > 0 )
  {
    v14 = v29.bottom + Rect.top - Rect.bottom - v29.top;
LABEL_19:
    Rect.bottom += v14;
    SetWindowPos(v9, 0, 0, 0, v27, v14 + v10, 0x16u);
    *(_OWORD *)h = 0;
    v20 = GetDlgItem(hWnd, 1000);
    GetWindowRect(v20, (LPRECT)h);
    MapWindowPoints(0, hWnd, (LPPOINT)h, 2u);
    SetWindowPos(v20, 0, (int)h[0], v14 + HIDWORD(h[0]), 0, 0, 0x15u);
    bottom = Rect.bottom;
    top = v29.top;
    v18 = v29.bottom;
  }
LABEL_21:
  v21 = Rect.right - Rect.left;
  v22 = bottom - Rect.top;
  left = *(_DWORD *)(a2 + 24);
  if ( left == 0x80000000 )
    left = (v29.right - v21 - v29.left) / 2;
  v24 = *(_DWORD *)(a2 + 28);
  if ( v24 == 0x80000000 )
  {
    v24 = (v18 - v22 - top) / 3;
    if ( v24 < top )
      v24 = top;
  }
  if ( v26 )
  {
    if ( v21 + left > v29.right )
      left = v29.right - v21;
    if ( left < v29.left )
      left = v29.left;
    if ( v21 + v24 > v18 )
      v24 = v18 - v22;
    if ( v24 < top )
      v24 = top;
  }
  MoveWindow(hWnd, left, v24, v21, v22, 1);
  SetForegroundWindow(hWnd);
  return 1;
}

```

## disassembly

```asm
0x180076ae4  mov     [rsp-8+arg_10], rbx
0x180076ae9  push    rbp
0x180076aea  push    rsi
0x180076aeb  push    rdi
0x180076aec  push    r12
0x180076aee  push    r13
0x180076af0  push    r14
0x180076af2  push    r15
0x180076af4  lea     rbp, [rsp-7A0h]
0x180076afc  sub     rsp, 8A0h
0x180076b03  mov     rax, cs:__security_cookie
0x180076b0a  xor     rax, rsp
0x180076b0d  mov     [rbp+7D0h+var_40], rax
0x180076b14  mov     r14, rdx
0x180076b17  mov     r15, rcx
0x180076b1a  xor     edx, edx; struct _GUID *
0x180076b1c  mov     rcx, [r14+30h]; this
0x180076b20  call    ?InSafeMode@COleScript@@QEAAHPEBU_GUID@@@Z; COleScript::InSafeMode(_GUID const *)
0x180076b25  cmp     qword ptr [r14+20h], 0
0x180076b2a  mov     [rsp+8D0h+var_890], eax
0x180076b2e  jz      short loc_180076B34
0x180076b30  test    eax, eax
0x180076b32  jz      short loc_180076B72
0x180076b34  mov     edx, 3; nIDDlgItem
0x180076b39  mov     rcx, r15; hDlg
0x180076b3c  call    cs:__imp_GetDlgItem
0x180076b43  nop     dword ptr [rax+rax+00h]
0x180076b48  mov     rbx, rax
0x180076b4b  test    rax, rax
0x180076b4e  jz      short loc_180076B72
0x180076b50  xor     edx, edx; nCmdShow
0x180076b52  mov     rcx, rax; hWnd
0x180076b55  call    cs:__imp_ShowWindow
0x180076b5c  nop     dword ptr [rax+rax+00h]
0x180076b61  xor     edx, edx; bEnable
0x180076b63  mov     rcx, rbx; hWnd
0x180076b66  call    cs:__imp_EnableWindow
0x180076b6d  nop     dword ptr [rax+rax+00h]
0x180076b72  xorps   xmm0, xmm0
0x180076b75  lea     rdx, [rsp+8D0h+Rect]; lpRect
0x180076b7a  xorps   xmm1, xmm1
0x180076b7d  mov     rcx, r15; hWnd
0x180076b80  movups  xmmword ptr [rsp+8D0h+Rect.left], xmm0
0x180076b85  movups  xmmword ptr [rsp+8D0h+var_878.left], xmm1
0x180076b8a  call    cs:__imp_GetWindowRect
0x180076b91  nop     dword ptr [rax+rax+00h]
0x180076b96  call    cs:__imp_GetDesktopWindow
0x180076b9d  nop     dword ptr [rax+rax+00h]
0x180076ba2  mov     rcx, rax; hWnd
0x180076ba5  lea     rdx, [rsp+8D0h+var_878]; lpRect
0x180076baa  call    cs:__imp_GetWindowRect
0x180076bb1  nop     dword ptr [rax+rax+00h]
0x180076bb6  mov     edx, 3E9h; nIDDlgItem
0x180076bbb  mov     rcx, r15; hDlg
0x180076bbe  call    cs:__imp_GetDlgItem
0x180076bc5  nop     dword ptr [rax+rax+00h]
0x180076bca  mov     rbx, rax
0x180076bcd  test    rax, rax
0x180076bd0  jz      loc_180076EB1
0x180076bd6  xorps   xmm0, xmm0
0x180076bd9  lea     rdx, [rsp+8D0h+rc]; lpRect
0x180076bde  mov     rcx, rax; hWnd
0x180076be1  movups  xmmword ptr [rsp+8D0h+rc.left], xmm0
0x180076be6  call    cs:__imp_GetClientRect
0x180076bed  nop     dword ptr [rax+rax+00h]
0x180076bf2  mov     eax, [rbp+7D0h+rc.right]
0x180076bf5  mov     rcx, rbx; hWnd
0x180076bf8  sub     eax, [rsp+8D0h+rc.left]
0x180076bfc  mov     r13d, [rbp+7D0h+rc.bottom]
0x180076c00  sub     r13d, [rsp+8D0h+rc.top]
0x180076c05  mov     [rsp+8D0h+var_88C], eax
0x180076c09  call    cs:__imp_GetDC
0x180076c10  nop     dword ptr [rax+rax+00h]
0x180076c15  mov     rsi, rax
0x180076c18  test    rax, rax
0x180076c1b  jz      loc_180076EB1
0x180076c21  xor     r9d, r9d; lParam
0x180076c24  mov     [rsp+8D0h+h], 0
0x180076c2d  xor     r8d, r8d; wParam
0x180076c30  mov     rcx, rbx; hWnd
0x180076c33  lea     edx, [r9+31h]; Msg
0x180076c37  call    cs:__imp_SendMessageA
0x180076c3e  nop     dword ptr [rax+rax+00h]
0x180076c43  mov     r12, rax
0x180076c46  test    rax, rax
0x180076c49  jz      short loc_180076C62
0x180076c4b  mov     rdx, rax; h
0x180076c4e  mov     rcx, rsi; hdc
0x180076c51  call    cs:__imp_SelectObject
0x180076c58  nop     dword ptr [rax+rax+00h]
0x180076c5d  mov     [rsp+8D0h+h], rax
0x180076c62  mov     r8d, 400h; nMaxCount
0x180076c68  lea     rdx, [rbp+7D0h+String]; lpString
0x180076c6c  mov     rcx, rbx; hWnd
0x180076c6f  xor     edi, edi
0x180076c71  call    cs:__imp_GetWindowTextW
0x180076c78  nop     dword ptr [rax+rax+00h]
0x180076c7d  test    eax, eax
0x180076c7f  jz      short loc_180076CAE
0x180076c81  lea     r9, [rsp+8D0h+rc]; lprc
0x180076c86  mov     [rsp+8D0h+format], 0C50h; format
0x180076c8e  or      r8d, 0FFFFFFFFh; cchText
0x180076c92  lea     rdx, [rbp+7D0h+String]; lpchText
0x180076c96  mov     rcx, rsi; hdc
0x180076c99  call    cs:__imp_DrawTextW
0x180076ca0  nop     dword ptr [rax+rax+00h]
0x180076ca5  test    eax, eax
0x180076ca7  jz      short loc_180076CAE
0x180076ca9  mov     edi, eax
0x180076cab  sub     edi, r13d
0x180076cae  test    r12, r12
0x180076cb1  jz      short loc_180076CC7
0x180076cb3  mov     rdx, [rsp+8D0h+h]; h
0x180076cb8  mov     rcx, rsi; hdc
0x180076cbb  call    cs:__imp_SelectObject
0x180076cc2  nop     dword ptr [rax+rax+00h]
0x180076cc7  mov     rdx, rsi; hDC
0x180076cca  mov     rcx, rbx; hWnd
0x180076ccd  call    cs:__imp_ReleaseDC
0x180076cd4  nop     dword ptr [rax+rax+00h]
0x180076cd9  mov     r8d, [rsp+8D0h+Rect.bottom]
0x180076cde  mov     r12d, [rsp+8D0h+var_890]
0x180076ce3  test    edi, edi
0x180076ce5  jle     loc_180076DE2
0x180076ceb  test    r12d, r12d
0x180076cee  jz      short loc_180076D13
0x180076cf0  mov     ecx, [rsp+8D0h+Rect.top]
0x180076cf4  mov     r9d, [rsp+8D0h+var_878.top]
0x180076cf9  sub     ecx, r8d
0x180076cfc  mov     esi, [rsp+8D0h+var_878.bottom]
0x180076d00  sub     ecx, r9d
0x180076d03  add     ecx, esi
0x180076d05  cmp     edi, ecx
0x180076d07  jle     short loc_180076D13
0x180076d09  test    ecx, ecx
0x180076d0b  jle     loc_180076DEB
0x180076d11  mov     edi, ecx
0x180076d13  add     r8d, edi
0x180076d16  mov     [rsp+8D0h+uFlags], 16h; uFlags
0x180076d1e  lea     eax, [rdi+r13]
0x180076d22  mov     [rsp+8D0h+Rect.bottom], r8d
0x180076d27  mov     [rsp+8D0h+cy], eax; cy
0x180076d2b  xor     r8d, r8d; X
0x180076d2e  mov     eax, [rsp+8D0h+var_88C]
0x180076d32  xor     r9d, r9d; Y
0x180076d35  xor     edx, edx; hWndInsertAfter
0x180076d37  mov     [rsp+8D0h+format], eax; cx
0x180076d3b  mov     rcx, rbx; hWnd
0x180076d3e  call    cs:__imp_SetWindowPos
0x180076d45  nop     dword ptr [rax+rax+00h]
0x180076d4a  xorps   xmm0, xmm0
0x180076d4d  mov     edx, 3E8h; nIDDlgItem
0x180076d52  mov     rcx, r15; hDlg
0x180076d55  movups  xmmword ptr [rsp+8D0h+h], xmm0
0x180076d5a  call    cs:__imp_GetDlgItem
0x180076d61  nop     dword ptr [rax+rax+00h]
0x180076d66  mov     rcx, rax; hWnd
0x180076d69  lea     rdx, [rsp+8D0h+h]; lpRect
0x180076d6e  mov     rbx, rax
0x180076d71  call    cs:__imp_GetWindowRect
0x180076d78  nop     dword ptr [rax+rax+00h]
0x180076d7d  mov     r13d, 2
0x180076d83  lea     r8, [rsp+8D0h+h]; lpPoints
0x180076d88  mov     r9d, r13d; cPoints
0x180076d8b  mov     rdx, r15; hWndTo
0x180076d8e  xor     ecx, ecx; hWndFrom
0x180076d90  call    cs:__imp_MapWindowPoints
0x180076d97  nop     dword ptr [rax+rax+00h]
0x180076d9c  mov     r9d, dword ptr [rsp+8D0h+h+4]
0x180076da1  xor     edx, edx; hWndInsertAfter
0x180076da3  mov     r8d, dword ptr [rsp+8D0h+h]; X
0x180076da8  add     r9d, edi; Y
0x180076dab  mov     [rsp+8D0h+uFlags], 15h; uFlags
0x180076db3  mov     rcx, rbx; hWnd
0x180076db6  mov     [rsp+8D0h+cy], 0; cy
0x180076dbe  mov     [rsp+8D0h+format], 0; cx
0x180076dc6  call    cs:__imp_SetWindowPos
0x180076dcd  nop     dword ptr [rax+rax+00h]
0x180076dd2  mov     r8d, [rsp+8D0h+Rect.bottom]
0x180076dd7  mov     r9d, [rsp+8D0h+var_878.top]
0x180076ddc  mov     esi, [rsp+8D0h+var_878.bottom]
0x180076de0  jmp     short loc_180076DF1
0x180076de2  mov     esi, [rsp+8D0h+var_878.bottom]
0x180076de6  mov     r9d, [rsp+8D0h+var_878.top]
0x180076deb  mov     r13d, 2
0x180076df1  mov     r11d, [rsp+8D0h+Rect.right]
0x180076df6  mov     ecx, 80000000h
0x180076dfb  sub     r11d, [rsp+8D0h+Rect.left]
0x180076e00  sub     r8d, [rsp+8D0h+Rect.top]
0x180076e05  mov     r10d, [r14+18h]
0x180076e09  mov     ebx, [rsp+8D0h+var_878.right]
0x180076e0d  mov     edi, [rsp+8D0h+var_878.left]
0x180076e11  cmp     r10d, ecx
0x180076e14  jnz     short loc_180076E24
0x180076e16  mov     eax, ebx
0x180076e18  sub     eax, r11d
0x180076e1b  sub     eax, edi
0x180076e1d  cdq
0x180076e1e  idiv    r13d
0x180076e21  mov     r10d, eax
0x180076e24  mov     edx, [r14+1Ch]
0x180076e28  cmp     edx, ecx
0x180076e2a  jnz     short loc_180076E4A
0x180076e2c  mov     ecx, esi
0x180076e2e  mov     eax, 55555556h
0x180076e33  sub     ecx, r8d
0x180076e36  sub     ecx, r9d
0x180076e39  imul    ecx
0x180076e3b  mov     eax, edx
0x180076e3d  shr     eax, 1Fh
0x180076e40  add     edx, eax
0x180076e42  cmp     edx, r9d
0x180076e45  jge     short loc_180076E4A
0x180076e47  mov     edx, r9d
0x180076e4a  test    r12d, r12d
0x180076e4d  jz      short loc_180076E78
0x180076e4f  lea     eax, [r11+r10]
0x180076e53  cmp     eax, ebx
0x180076e55  jle     short loc_180076E5D
0x180076e57  mov     r10d, ebx
0x180076e5a  sub     r10d, r11d
0x180076e5d  cmp     r10d, edi
0x180076e60  lea     eax, [r11+rdx]
0x180076e64  cmovl   r10d, edi
0x180076e68  cmp     eax, esi
0x180076e6a  jle     short loc_180076E71
0x180076e6c  mov     edx, esi
0x180076e6e  sub     edx, r8d
0x180076e71  cmp     edx, r9d
0x180076e74  cmovl   edx, r9d
0x180076e78  mov     ebx, 1
0x180076e7d  mov     r9d, r11d; nWidth
0x180076e80  mov     [rsp+8D0h+cy], ebx; bRepaint
0x180076e84  mov     rcx, r15; hWnd
0x180076e87  mov     [rsp+8D0h+format], r8d; nHeight
0x180076e8c  mov     r8d, edx; Y
0x180076e8f  mov     edx, r10d; X
0x180076e92  call    cs:__imp_MoveWindow
0x180076e99  nop     dword ptr [rax+rax+00h]
0x180076e9e  mov     rcx, r15; hWnd
0x180076ea1  call    cs:__imp_SetForegroundWindow
0x180076ea8  nop     dword ptr [rax+rax+00h]
0x180076ead  mov     eax, ebx
0x180076eaf  jmp     short loc_180076EBB
0x180076eb1  mov     dword ptr [r14+38h], 8000FFFFh
0x180076eb9  xor     eax, eax
0x180076ebb  mov     rcx, [rbp+7D0h+var_40]
0x180076ec2  xor     rcx, rsp; StackCookie
0x180076ec5  call    __security_check_cookie
0x180076eca  mov     rbx, [rsp+8D0h+arg_10]
0x180076ed2  add     rsp, 8A0h
0x180076ed9  pop     r15
0x180076edb  pop     r14
0x180076edd  pop     r13
0x180076edf  pop     r12
0x180076ee1  pop     rdi
0x180076ee2  pop     rsi
0x180076ee3  pop     rbp
0x180076ee4  retn
```
