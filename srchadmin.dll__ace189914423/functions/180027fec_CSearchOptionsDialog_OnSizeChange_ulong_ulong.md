# CSearchOptionsDialog::_OnSizeChange(ulong,ulong)

- ea: `0x180027fec`
- end: `0x180028255`
- name: `?_OnSizeChange@CSearchOptionsDialog@@AEAAXKK@Z`
- size: `617`
- prototype: `void __fastcall(CSearchOptionsDialog *__hidden this, unsigned int, unsigned int)`
- caller_count: `1`
- callee_count: `4`
- tags: `installer_update`

## callers

- `0x180028520`

## callees

- `0x180005cc0`
- `0x18000d4dc`
- `0x18001675c`
- `0x180027fec`

## import_xrefs

- `api-ms-win-rtcore-ntuser-window-l1-1-0!GetWindowRect` at `0x1800280ab`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!GetWindowRect` at `0x1800280ab`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!EndDeferWindowPos` at `0x1800281f8`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!EndDeferWindowPos` at `0x1800281f8`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!DeferWindowPos` at `0x1800281a9`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!DeferWindowPos` at `0x1800281a9`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!GetWindow` at `0x18002807e`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!GetWindow` at `0x1800281bc`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!GetWindow` at `0x18002807e`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!GetWindow` at `0x1800281bc`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!BeginDeferWindowPos` at `0x18002805d`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!BeginDeferWindowPos` at `0x18002805d`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!GetClientRect` at `0x180028024`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!GetClientRect` at `0x180028024`
- `USER32!UpdateWindow` at `0x180028221`
- `USER32!UpdateWindow` at `0x180028221`
- `USER32!GetDlgCtrlID` at `0x1800280c6`
- `USER32!GetDlgCtrlID` at `0x1800280c6`
- `USER32!MapWindowPoints` at `0x1800280bd`
- `USER32!MapWindowPoints` at `0x1800280bd`
- `USER32!GetDlgItem` at `0x180028206`
- `USER32!GetDlgItem` at `0x180028206`
- `USER32!InvalidateRect` at `0x180028218`
- `USER32!InvalidateRect` at `0x180028218`

## pseudocode

```c
void __fastcall CSearchOptionsDialog::_OnSizeChange(HWND *this)
{
  HWND v2; // rcx
  int v3; // eax
  int v4; // r12d
  int v5; // r15d
  HDWP v6; // rdi
  int Error; // esi
  HWND Window; // rbx
  int DlgCtrlID; // edx
  int v10; // edx
  int v11; // edx
  int v12; // edx
  int v13; // edx
  HDWP v14; // rax
  int cy; // ecx
  int v16; // edx
  int v17; // edx
  int v18; // edx
  HWND DlgItem; // rbx
  struct tagRECT v20; // [rsp+40h] [rbp-30h] BYREF
  struct tagRECT Rect; // [rsp+50h] [rbp-20h] BYREF

  v2 = *this;
  Rect = 0;
  GetClientRect(v2, &Rect);
  v3 = Rect.bottom - Rect.top;
  v4 = Rect.right - Rect.left - *((_DWORD *)this + 442);
  v5 = Rect.bottom - Rect.top - *((_DWORD *)this + 443);
  *((_DWORD *)this + 442) = Rect.right - Rect.left;
  *((_DWORD *)this + 443) = v3;
  v6 = BeginDeferWindowPos(10);
  if ( v6 )
    Error = 0;
  else
    Error = ResultFromKnownLastError();
  Window = GetWindow(*this, 5u);
  if ( Error >= 0 )
  {
    while ( 1 )
    {
      if ( !Window )
      {
        EndDeferWindowPos(v6);
        break;
      }
      v20 = 0;
      GetWindowRect(Window, &v20);
      MapWindowPoints(0, *this, (LPPOINT)&v20, 2u);
      DlgCtrlID = GetDlgCtrlID(Window);
      if ( DlgCtrlID > 407 )
      {
        v16 = DlgCtrlID - 408;
        if ( !v16 )
          goto LABEL_21;
        v17 = v16 - 1;
        if ( !v17 )
        {
LABEL_25:
          v14 = DeferWindowPos(v6, Window, 0, v4 + v20.left, v5 + v20.top, 0, 0, 0x15u);
          goto LABEL_22;
        }
        v18 = v17 - 2;
        if ( v18 )
        {
          if ( v18 != 1 )
            goto LABEL_23;
LABEL_21:
          v14 = DeferWindowPos(
                  v6,
                  Window,
                  0,
                  v20.left,
                  v5 + v20.top,
                  v4 + v20.right - v20.left,
                  v20.bottom - v20.top,
                  0x14u);
          goto LABEL_22;
        }
      }
      else if ( DlgCtrlID != 407 )
      {
        v10 = DlgCtrlID - 2;
        if ( !v10 )
          goto LABEL_25;
        v11 = v10 - 400;
        if ( !v11 || (v12 = v11 - 1) == 0 )
        {
          cy = v20.bottom - v20.top;
          goto LABEL_15;
        }
        v13 = v12 - 2;
        if ( !v13 )
        {
          cy = v5 + v20.bottom - v20.top;
LABEL_15:
          v14 = DeferWindowPos(v6, Window, 0, 0, 0, v4 + v20.right - v20.left, cy, 0x16u);
          goto LABEL_22;
        }
        if ( v13 != 1 )
          goto LABEL_23;
      }
      v14 = DeferWindowPos(v6, Window, 0, v20.left, v5 + v20.top, 0, 0, 0x15u);
LABEL_22:
      v6 = v14;
LABEL_23:
      if ( !v6 )
        break;
      Window = GetWindow(Window, 2u);
    }
  }
  DlgItem = GetDlgItem(*this, 402);
  InvalidateRect(DlgItem, 0, 1);
  UpdateWindow(DlgItem);
  CIndexedLocationsBasket::ResizeColumns((CIndexedLocationsBasket *)(this + 13));
}

```

## disassembly

```asm
0x180027fec  mov     [rsp-28h+arg_8], rbx
0x180027ff1  mov     [rsp-28h+arg_10], rsi
0x180027ff6  push    rbp
0x180027ff7  push    rdi
0x180027ff8  push    r12
0x180027ffa  push    r14
0x180027ffc  push    r15
0x180027ffe  mov     rbp, rsp
0x180028001  sub     rsp, 70h
0x180028005  mov     rax, cs:__security_cookie
0x18002800c  xor     rax, rsp
0x18002800f  mov     [rbp+var_10], rax
0x180028013  mov     r14, rcx
0x180028016  lea     rdx, [rbp+Rect]; lpRect
0x18002801a  mov     rcx, [rcx]; hWnd
0x18002801d  xorps   xmm0, xmm0
0x180028020  movups  xmmword ptr [rbp+Rect.left], xmm0
0x180028024  call    cs:__imp_GetClientRect
0x18002802a  mov     edx, [rbp+Rect.right]
0x18002802d  mov     ecx, 0Ah; nNumWindows
0x180028032  sub     edx, [rbp+Rect.left]
0x180028035  mov     eax, [rbp+Rect.bottom]
0x180028038  mov     r12d, edx
0x18002803b  sub     eax, [rbp+Rect.top]
0x18002803e  sub     r12d, [r14+6E8h]
0x180028045  mov     r15d, eax
0x180028048  sub     r15d, [r14+6ECh]
0x18002804f  mov     [r14+6E8h], edx
0x180028056  mov     [r14+6ECh], eax
0x18002805d  call    cs:__imp_BeginDeferWindowPos
0x180028063  mov     rdi, rax
0x180028066  test    rax, rax
0x180028069  jz      short loc_18002806F
0x18002806b  xor     esi, esi
0x18002806d  jmp     short loc_180028076
0x18002806f  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x180028074  mov     esi, eax
0x180028076  mov     rcx, [r14]; hWnd
0x180028079  mov     edx, 5; uCmd
0x18002807e  call    cs:__imp_GetWindow
0x180028084  mov     rbx, rax
0x180028087  test    esi, esi
0x180028089  js      loc_1800281FE
0x18002808f  mov     esi, 2
0x180028094  test    rbx, rbx
0x180028097  jz      loc_1800281F5
0x18002809d  xorps   xmm0, xmm0
0x1800280a0  lea     rdx, [rbp+var_30]; lpRect
0x1800280a4  mov     rcx, rbx; hWnd
0x1800280a7  movups  xmmword ptr [rbp+var_30.left], xmm0
0x1800280ab  call    cs:__imp_GetWindowRect
0x1800280b1  mov     rdx, [r14]; hWndTo
0x1800280b4  lea     r8, [rbp+var_30]; lpPoints
0x1800280b8  mov     r9d, esi; cPoints
0x1800280bb  xor     ecx, ecx; hWndFrom
0x1800280bd  call    cs:__imp_MapWindowPoints
0x1800280c3  mov     rcx, rbx; hWnd
0x1800280c6  call    cs:__imp_GetDlgCtrlID
0x1800280cc  mov     edx, eax
0x1800280ce  mov     eax, 197h
0x1800280d3  cmp     edx, eax
0x1800280d5  jg      loc_18002815E
0x1800280db  jz      short loc_1800280FF
0x1800280dd  sub     edx, esi
0x1800280df  jz      loc_1800281CA
0x1800280e5  sub     edx, 190h
0x1800280eb  jz      short loc_180028156
0x1800280ed  sub     edx, 1
0x1800280f0  jz      short loc_180028156
0x1800280f2  sub     edx, esi
0x1800280f4  jz      short loc_180028127
0x1800280f6  cmp     edx, 1
0x1800280f9  jnz     loc_1800281B2
0x1800280ff  mov     ecx, [rbp+var_30.top]
0x180028102  mov     r9d, [rbp+var_30.left]
0x180028106  add     ecx, r15d
0x180028109  mov     [rsp+70h+uFlags], 15h
0x180028111  mov     [rsp+70h+cy], 0
0x180028119  mov     [rsp+70h+var_48], 0
0x180028121  mov     [rsp+70h+y], ecx
0x180028125  jmp     short loc_1800281A0
0x180028127  mov     ecx, [rbp+var_30.bottom]
0x18002812a  sub     ecx, [rbp+var_30.top]
0x18002812d  add     ecx, r15d
0x180028130  mov     eax, [rbp+var_30.right]
0x180028133  sub     eax, [rbp+var_30.left]
0x180028136  mov     [rsp+70h+uFlags], 16h
0x18002813e  add     eax, r12d
0x180028141  mov     [rsp+70h+cy], ecx
0x180028145  xor     r9d, r9d
0x180028148  mov     [rsp+70h+var_48], eax
0x18002814c  mov     [rsp+70h+y], 0
0x180028154  jmp     short loc_1800281A0
0x180028156  mov     ecx, [rbp+var_30.bottom]
0x180028159  sub     ecx, [rbp+var_30.top]
0x18002815c  jmp     short loc_180028130
0x18002815e  sub     edx, 198h
0x180028164  jz      short loc_180028174
0x180028166  sub     edx, 1
0x180028169  jz      short loc_1800281CA
0x18002816b  sub     edx, esi
0x18002816d  jz      short loc_1800280FF
0x18002816f  cmp     edx, 1
0x180028172  jnz     short loc_1800281B2
0x180028174  mov     eax, [rbp+var_30.top]
0x180028177  mov     ecx, [rbp+var_30.right]
0x18002817a  mov     r9d, [rbp+var_30.left]; x
0x18002817e  sub     ecx, r9d
0x180028181  mov     edx, [rbp+var_30.bottom]
0x180028184  add     ecx, r12d
0x180028187  mov     [rsp+70h+uFlags], 14h; uFlags
0x18002818f  sub     edx, eax
0x180028191  mov     [rsp+70h+cy], edx; cy
0x180028195  add     eax, r15d
0x180028198  mov     [rsp+70h+var_48], ecx; cx
0x18002819c  mov     [rsp+70h+y], eax; y
0x1800281a0  xor     r8d, r8d; hWndInsertAfter
0x1800281a3  mov     rdx, rbx; hWnd
0x1800281a6  mov     rcx, rdi; hWinPosInfo
0x1800281a9  call    cs:__imp_DeferWindowPos
0x1800281af  mov     rdi, rax
0x1800281b2  test    rdi, rdi
0x1800281b5  jz      short loc_1800281FE
0x1800281b7  mov     edx, esi; uCmd
0x1800281b9  mov     rcx, rbx; hWnd
0x1800281bc  call    cs:__imp_GetWindow
0x1800281c2  mov     rbx, rax
0x1800281c5  jmp     loc_180028094
0x1800281ca  mov     ecx, [rbp+var_30.top]
0x1800281cd  mov     r9d, [rbp+var_30.left]
0x1800281d1  add     ecx, r15d
0x1800281d4  mov     [rsp+70h+uFlags], 15h
0x1800281dc  add     r9d, r12d
0x1800281df  mov     [rsp+70h+cy], 0
0x1800281e7  mov     [rsp+70h+var_48], 0
0x1800281ef  mov     [rsp+70h+y], ecx
0x1800281f3  jmp     short loc_1800281A0
0x1800281f5  mov     rcx, rdi; hWinPosInfo
0x1800281f8  call    cs:__imp_EndDeferWindowPos
0x1800281fe  mov     rcx, [r14]; hDlg
0x180028201  mov     edx, 192h; nIDDlgItem
0x180028206  call    cs:__imp_GetDlgItem
0x18002820c  xor     edx, edx; lpRect
0x18002820e  mov     rcx, rax; hWnd
0x180028211  mov     rbx, rax
0x180028214  lea     r8d, [rdx+1]; bErase
0x180028218  call    cs:__imp_InvalidateRect
0x18002821e  mov     rcx, rbx; hWnd
0x180028221  call    cs:__imp_UpdateWindow
0x180028227  lea     rcx, [r14+68h]; this
0x18002822b  call    ?ResizeColumns@CIndexedLocationsBasket@@QEAAXXZ; CIndexedLocationsBasket::ResizeColumns(void)
0x180028230  mov     rcx, [rbp+var_10]
0x180028234  xor     rcx, rsp; StackCookie
0x180028237  call    __security_check_cookie
0x18002823c  lea     r11, [rsp+70h+var_s0]
0x180028241  mov     rbx, [r11+38h]
0x180028245  mov     rsi, [r11+40h]
0x180028249  mov     rsp, r11
0x18002824c  pop     r15
0x18002824e  pop     r14
0x180028250  pop     r12
0x180028252  pop     rdi
0x180028253  pop     rbp
0x180028254  retn
```
