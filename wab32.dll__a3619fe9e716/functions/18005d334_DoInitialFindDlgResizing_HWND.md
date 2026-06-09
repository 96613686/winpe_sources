# DoInitialFindDlgResizing(HWND__ *)

- ea: `0x18005d334`
- end: `0x18005d491`
- name: `?DoInitialFindDlgResizing@@YAXPEAUHWND__@@@Z`
- size: `349`
- prototype: `void __fastcall(HWND hWndTo)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180060850`

## callees

- `0x18005d334`
- `0x180091ef0`

## import_xrefs

- `USER32!GetDlgItem` at `0x18005d39c`
- `USER32!GetDlgItem` at `0x18005d3b7`
- `USER32!GetDlgItem` at `0x18005d407`
- `USER32!GetDlgItem` at `0x18005d39c`
- `USER32!GetDlgItem` at `0x18005d3b7`
- `USER32!GetDlgItem` at `0x18005d407`
- `USER32!GetWindowRect` at `0x18005d3a9`
- `USER32!GetWindowRect` at `0x18005d3c4`
- `USER32!GetWindowRect` at `0x18005d417`
- `USER32!GetWindowRect` at `0x18005d3a9`
- `USER32!GetWindowRect` at `0x18005d3c4`
- `USER32!GetWindowRect` at `0x18005d417`
- `USER32!MapWindowPoints` at `0x18005d3d9`
- `USER32!MapWindowPoints` at `0x18005d3ee`
- `USER32!MapWindowPoints` at `0x18005d438`
- `USER32!MapWindowPoints` at `0x18005d3d9`
- `USER32!MapWindowPoints` at `0x18005d3ee`
- `USER32!MapWindowPoints` at `0x18005d438`
- `USER32!MoveWindow` at `0x18005d45a`
- `USER32!MoveWindow` at `0x18005d45a`

## pseudocode

```c
void __fastcall DoInitialFindDlgResizing(HWND hWndTo)
{
  HWND DlgItem; // rax
  HWND v3; // rax
  int v4; // r12d
  __int64 i; // r14
  HWND v6; // rsi
  int v7; // edi
  int nHeight; // ebx
  int nIDDlgItem[4]; // [rsp+30h] [rbp-29h]
  int v10; // [rsp+40h] [rbp-19h]
  int v11; // [rsp+44h] [rbp-15h]
  int v12; // [rsp+48h] [rbp-11h]
  struct tagRECT v13; // [rsp+50h] [rbp-9h] BYREF
  struct tagRECT v14; // [rsp+60h] [rbp+7h] BYREF
  struct tagRECT Rect; // [rsp+70h] [rbp+17h] BYREF

  v10 = 2793;
  v11 = 2794;
  v14 = 0;
  *(__m128i *)nIDDlgItem = _mm_load_si128((const __m128i *)&_xmm);
  v12 = 2795;
  Rect = 0;
  v13 = 0;
  DlgItem = GetDlgItem(hWndTo, 1151);
  GetWindowRect(DlgItem, &Rect);
  v3 = GetDlgItem(hWndTo, 2789);
  GetWindowRect(v3, &v14);
  MapWindowPoints(0, hWndTo, (LPPOINT)&Rect, 2u);
  MapWindowPoints(0, hWndTo, (LPPOINT)&v14, 2u);
  v4 = v14.left - Rect.left;
  for ( i = 0; i != 7; ++i )
  {
    v6 = GetDlgItem(hWndTo, nIDDlgItem[i]);
    GetWindowRect(v6, &v13);
    v7 = v13.right - v13.left;
    nHeight = v13.bottom - v13.top;
    MapWindowPoints(0, hWndTo, (LPPOINT)&v13, 2u);
    MoveWindow(v6, v13.left - v4, v13.top, v7, nHeight, 1);
  }
}

```

## disassembly

```asm
0x18005d334  mov     [rsp-8+arg_8], rbx
0x18005d339  mov     [rsp-8+arg_10], rsi
0x18005d33e  push    rbp
0x18005d33f  push    rdi
0x18005d340  push    r12
0x18005d342  push    r14
0x18005d344  push    r15
0x18005d346  lea     rbp, [rsp-37h]
0x18005d34b  sub     rsp, 90h
0x18005d352  mov     rax, cs:__security_cookie
0x18005d359  xor     rax, rsp
0x18005d35c  mov     [rbp+57h+var_30], rax
0x18005d360  xorps   xmm1, xmm1
0x18005d363  mov     [rbp+57h+var_70], 0AE9h
0x18005d36a  xorps   xmm0, xmm0
0x18005d36d  mov     [rbp+57h+var_6C], 0AEAh
0x18005d374  movups  xmmword ptr [rbp+57h+var_50.left], xmm1
0x18005d378  mov     edx, 47Fh; nIDDlgItem
0x18005d37d  mov     r15, rcx
0x18005d380  movdqa  xmm1, cs:__xmm@00000ae800000ae700000ae600000ae5
0x18005d388  movdqu  xmmword ptr [rbp+57h+nIDDlgItem], xmm1
0x18005d38d  mov     [rbp+57h+var_68], 0AEBh
0x18005d394  movups  xmmword ptr [rbp+57h+Rect.left], xmm0
0x18005d398  movups  xmmword ptr [rbp+57h+var_60.left], xmm0
0x18005d39c  call    cs:__imp_GetDlgItem
0x18005d3a2  mov     rcx, rax; hWnd
0x18005d3a5  lea     rdx, [rbp+57h+Rect]; lpRect
0x18005d3a9  call    cs:__imp_GetWindowRect
0x18005d3af  mov     edx, 0AE5h; nIDDlgItem
0x18005d3b4  mov     rcx, r15; hDlg
0x18005d3b7  call    cs:__imp_GetDlgItem
0x18005d3bd  mov     rcx, rax; hWnd
0x18005d3c0  lea     rdx, [rbp+57h+var_50]; lpRect
0x18005d3c4  call    cs:__imp_GetWindowRect
0x18005d3ca  mov     r9d, 2; cPoints
0x18005d3d0  lea     r8, [rbp+57h+Rect]; lpPoints
0x18005d3d4  mov     rdx, r15; hWndTo
0x18005d3d7  xor     ecx, ecx; hWndFrom
0x18005d3d9  call    cs:__imp_MapWindowPoints
0x18005d3df  mov     r9d, 2; cPoints
0x18005d3e5  lea     r8, [rbp+57h+var_50]; lpPoints
0x18005d3e9  mov     rdx, r15; hWndTo
0x18005d3ec  xor     ecx, ecx; hWndFrom
0x18005d3ee  call    cs:__imp_MapWindowPoints
0x18005d3f4  mov     r12d, [rbp+57h+var_50.left]
0x18005d3f8  sub     r12d, [rbp+57h+Rect.left]
0x18005d3fc  xor     r14d, r14d
0x18005d3ff  mov     edx, [rbp+r14*4+57h+nIDDlgItem]; nIDDlgItem
0x18005d404  mov     rcx, r15; hDlg
0x18005d407  call    cs:__imp_GetDlgItem
0x18005d40d  mov     rcx, rax; hWnd
0x18005d410  lea     rdx, [rbp+57h+var_60]; lpRect
0x18005d414  mov     rsi, rax
0x18005d417  call    cs:__imp_GetWindowRect
0x18005d41d  mov     edi, [rbp+57h+var_60.right]
0x18005d420  lea     r8, [rbp+57h+var_60]; lpPoints
0x18005d424  mov     ebx, [rbp+57h+var_60.bottom]
0x18005d427  mov     r9d, 2; cPoints
0x18005d42d  sub     edi, [rbp+57h+var_60.left]
0x18005d430  mov     rdx, r15; hWndTo
0x18005d433  sub     ebx, [rbp+57h+var_60.top]
0x18005d436  xor     ecx, ecx; hWndFrom
0x18005d438  call    cs:__imp_MapWindowPoints
0x18005d43e  mov     edx, [rbp+57h+var_60.left]
0x18005d441  mov     r9d, edi; nWidth
0x18005d444  mov     r8d, [rbp+57h+var_60.top]; Y
0x18005d448  sub     edx, r12d; X
0x18005d44b  mov     [rsp+0B0h+bRepaint], 1; bRepaint
0x18005d453  mov     rcx, rsi; hWnd
0x18005d456  mov     [rsp+0B0h+nHeight], ebx; nHeight
0x18005d45a  call    cs:__imp_MoveWindow
0x18005d460  inc     r14
0x18005d463  cmp     r14, 7
0x18005d467  jnz     short loc_18005D3FF
0x18005d469  mov     rcx, [rbp+57h+var_30]
0x18005d46d  xor     rcx, rsp; StackCookie
0x18005d470  call    __security_check_cookie
0x18005d475  lea     r11, [rsp+0B0h+var_20]
0x18005d47d  mov     rbx, [r11+38h]
0x18005d481  mov     rsi, [r11+40h]
0x18005d485  mov     rsp, r11
0x18005d488  pop     r15
0x18005d48a  pop     r14
0x18005d48c  pop     r12
0x18005d48e  pop     rdi
0x18005d48f  pop     rbp
0x18005d490  retn
```
