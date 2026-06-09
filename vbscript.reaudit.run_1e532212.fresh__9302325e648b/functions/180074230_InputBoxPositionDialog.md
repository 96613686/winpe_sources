# InputBoxPositionDialog

- ea: `0x180074230`
- end: `0x1800745ad`
- name: `InputBoxPositionDialog`
- size: `893`
- prototype: `__int64 __fastcall(HWND hWnd)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180073eb0`

## callees

- `0x180039668`
- `0x180074230`
- `0x1800767a0`

## import_xrefs

- `USER32!GetWindowRect` at `0x1800742c4`
- `USER32!GetWindowRect` at `0x1800742d8`
- `USER32!GetWindowRect` at `0x180074457`
- `USER32!GetWindowRect` at `0x1800742c4`
- `USER32!GetWindowRect` at `0x1800742d8`
- `USER32!GetWindowRect` at `0x180074457`
- `USER32!GetDC` at `0x180074325`
- `USER32!GetDC` at `0x180074325`
- `USER32!SetWindowPos` at `0x180074430`
- `USER32!SetWindowPos` at `0x1800744a0`
- `USER32!SetWindowPos` at `0x180074430`
- `USER32!SetWindowPos` at `0x1800744a0`
- `USER32!ShowWindow` at `0x18007429b`
- `USER32!ShowWindow` at `0x18007429b`
- `USER32!MapWindowPoints` at `0x180074470`
- `USER32!MapWindowPoints` at `0x180074470`
- `USER32!MoveWindow` at `0x180074566`
- `USER32!MoveWindow` at `0x180074566`
- `USER32!SendMessageA` at `0x18007434d`
- `USER32!SendMessageA` at `0x18007434d`
- `USER32!GetClientRect` at `0x180074308`
- `USER32!GetClientRect` at `0x180074308`
- `USER32!GetDlgItem` at `0x180074288`
- `USER32!GetDlgItem` at `0x1800742e6`
- `USER32!GetDlgItem` at `0x180074446`
- `USER32!GetDlgItem` at `0x180074288`
- `USER32!GetDlgItem` at `0x1800742e6`
- `USER32!GetDlgItem` at `0x180074446`
- `USER32!DrawTextW` at `0x18007439d`
- `USER32!DrawTextW` at `0x18007439d`
- `USER32!GetDesktopWindow` at `0x1800742ca`
- `USER32!GetDesktopWindow` at `0x1800742ca`
- `USER32!SetForegroundWindow` at `0x18007456f`
- `USER32!SetForegroundWindow` at `0x18007456f`
- `USER32!ReleaseDC` at `0x1800743c5`
- `USER32!ReleaseDC` at `0x1800743c5`
- `USER32!EnableWindow` at `0x1800742a6`
- `USER32!EnableWindow` at `0x1800742a6`
- `USER32!GetWindowTextW` at `0x18007437b`
- `USER32!GetWindowTextW` at `0x18007437b`
- `GDI32!SelectObject` at `0x180074361`
- `GDI32!SelectObject` at `0x1800743b9`
- `GDI32!SelectObject` at `0x180074361`
- `GDI32!SelectObject` at `0x1800743b9`

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
0x180074230  mov     [rsp-8+arg_10], rbx
0x180074235  push    rbp
0x180074236  push    rsi
0x180074237  push    rdi
0x180074238  push    r12
0x18007423a  push    r13
0x18007423c  push    r14
0x18007423e  push    r15
0x180074240  lea     rbp, [rsp-7A0h]
0x180074248  sub     rsp, 8A0h
0x18007424f  mov     rax, cs:__security_cookie
0x180074256  xor     rax, rsp
0x180074259  mov     [rbp+7D0h+var_40], rax
0x180074260  mov     r14, rdx
0x180074263  mov     r15, rcx
0x180074266  xor     edx, edx; struct _GUID *
0x180074268  mov     rcx, [r14+30h]; this
0x18007426c  call    ?InSafeMode@COleScript@@QEAAHPEBU_GUID@@@Z; COleScript::InSafeMode(_GUID const *)
0x180074271  cmp     qword ptr [r14+20h], 0
0x180074276  mov     [rsp+8D0h+var_890], eax
0x18007427a  jz      short loc_180074280
0x18007427c  test    eax, eax
0x18007427e  jz      short loc_1800742AC
0x180074280  mov     edx, 3; nIDDlgItem
0x180074285  mov     rcx, r15; hDlg
0x180074288  call    cs:__imp_GetDlgItem
0x18007428e  mov     rbx, rax
0x180074291  test    rax, rax
0x180074294  jz      short loc_1800742AC
0x180074296  xor     edx, edx; nCmdShow
0x180074298  mov     rcx, rax; hWnd
0x18007429b  call    cs:__imp_ShowWindow
0x1800742a1  xor     edx, edx; bEnable
0x1800742a3  mov     rcx, rbx; hWnd
0x1800742a6  call    cs:__imp_EnableWindow
0x1800742ac  xorps   xmm0, xmm0
0x1800742af  lea     rdx, [rsp+8D0h+Rect]; lpRect
0x1800742b4  xorps   xmm1, xmm1
0x1800742b7  mov     rcx, r15; hWnd
0x1800742ba  movups  xmmword ptr [rsp+8D0h+Rect.left], xmm0
0x1800742bf  movups  xmmword ptr [rsp+8D0h+var_878.left], xmm1
0x1800742c4  call    cs:__imp_GetWindowRect
0x1800742ca  call    cs:__imp_GetDesktopWindow
0x1800742d0  mov     rcx, rax; hWnd
0x1800742d3  lea     rdx, [rsp+8D0h+var_878]; lpRect
0x1800742d8  call    cs:__imp_GetWindowRect
0x1800742de  mov     edx, 3E9h; nIDDlgItem
0x1800742e3  mov     rcx, r15; hDlg
0x1800742e6  call    cs:__imp_GetDlgItem
0x1800742ec  mov     rbx, rax
0x1800742ef  test    rax, rax
0x1800742f2  jz      loc_180074579
0x1800742f8  xorps   xmm0, xmm0
0x1800742fb  lea     rdx, [rsp+8D0h+rc]; lpRect
0x180074300  mov     rcx, rax; hWnd
0x180074303  movups  xmmword ptr [rsp+8D0h+rc.left], xmm0
0x180074308  call    cs:__imp_GetClientRect
0x18007430e  mov     eax, [rbp+7D0h+rc.right]
0x180074311  mov     rcx, rbx; hWnd
0x180074314  sub     eax, [rsp+8D0h+rc.left]
0x180074318  mov     r13d, [rbp+7D0h+rc.bottom]
0x18007431c  sub     r13d, [rsp+8D0h+rc.top]
0x180074321  mov     [rsp+8D0h+var_88C], eax
0x180074325  call    cs:__imp_GetDC
0x18007432b  mov     rsi, rax
0x18007432e  test    rax, rax
0x180074331  jz      loc_180074579
0x180074337  xor     r9d, r9d; lParam
0x18007433a  mov     [rsp+8D0h+h], 0
0x180074343  xor     r8d, r8d; wParam
0x180074346  mov     rcx, rbx; hWnd
0x180074349  lea     edx, [r9+31h]; Msg
0x18007434d  call    cs:__imp_SendMessageA
0x180074353  mov     r12, rax
0x180074356  test    rax, rax
0x180074359  jz      short loc_18007436C
0x18007435b  mov     rdx, rax; h
0x18007435e  mov     rcx, rsi; hdc
0x180074361  call    cs:__imp_SelectObject
0x180074367  mov     [rsp+8D0h+h], rax
0x18007436c  mov     r8d, 400h; nMaxCount
0x180074372  lea     rdx, [rbp+7D0h+String]; lpString
0x180074376  mov     rcx, rbx; hWnd
0x180074379  xor     edi, edi
0x18007437b  call    cs:__imp_GetWindowTextW
0x180074381  test    eax, eax
0x180074383  jz      short loc_1800743AC
0x180074385  lea     r9, [rsp+8D0h+rc]; lprc
0x18007438a  mov     [rsp+8D0h+format], 0C50h; format
0x180074392  or      r8d, 0FFFFFFFFh; cchText
0x180074396  lea     rdx, [rbp+7D0h+String]; lpchText
0x18007439a  mov     rcx, rsi; hdc
0x18007439d  call    cs:__imp_DrawTextW
0x1800743a3  test    eax, eax
0x1800743a5  jz      short loc_1800743AC
0x1800743a7  mov     edi, eax
0x1800743a9  sub     edi, r13d
0x1800743ac  test    r12, r12
0x1800743af  jz      short loc_1800743BF
0x1800743b1  mov     rdx, [rsp+8D0h+h]; h
0x1800743b6  mov     rcx, rsi; hdc
0x1800743b9  call    cs:__imp_SelectObject
0x1800743bf  mov     rdx, rsi; hDC
0x1800743c2  mov     rcx, rbx; hWnd
0x1800743c5  call    cs:__imp_ReleaseDC
0x1800743cb  mov     r8d, [rsp+8D0h+Rect.bottom]
0x1800743d0  mov     r12d, [rsp+8D0h+var_890]
0x1800743d5  test    edi, edi
0x1800743d7  jle     loc_1800744B6
0x1800743dd  test    r12d, r12d
0x1800743e0  jz      short loc_180074405
0x1800743e2  mov     ecx, [rsp+8D0h+Rect.top]
0x1800743e6  mov     r9d, [rsp+8D0h+var_878.top]
0x1800743eb  sub     ecx, r8d
0x1800743ee  mov     esi, [rsp+8D0h+var_878.bottom]
0x1800743f2  sub     ecx, r9d
0x1800743f5  add     ecx, esi
0x1800743f7  cmp     edi, ecx
0x1800743f9  jle     short loc_180074405
0x1800743fb  test    ecx, ecx
0x1800743fd  jle     loc_1800744BF
0x180074403  mov     edi, ecx
0x180074405  add     r8d, edi
0x180074408  mov     [rsp+8D0h+uFlags], 16h; uFlags
0x180074410  lea     eax, [rdi+r13]
0x180074414  mov     [rsp+8D0h+Rect.bottom], r8d
0x180074419  mov     [rsp+8D0h+cy], eax; cy
0x18007441d  xor     r8d, r8d; X
0x180074420  mov     eax, [rsp+8D0h+var_88C]
0x180074424  xor     r9d, r9d; Y
0x180074427  xor     edx, edx; hWndInsertAfter
0x180074429  mov     [rsp+8D0h+format], eax; cx
0x18007442d  mov     rcx, rbx; hWnd
0x180074430  call    cs:__imp_SetWindowPos
0x180074436  xorps   xmm0, xmm0
0x180074439  mov     edx, 3E8h; nIDDlgItem
0x18007443e  mov     rcx, r15; hDlg
0x180074441  movups  xmmword ptr [rsp+8D0h+h], xmm0
0x180074446  call    cs:__imp_GetDlgItem
0x18007444c  mov     rcx, rax; hWnd
0x18007444f  lea     rdx, [rsp+8D0h+h]; lpRect
0x180074454  mov     rbx, rax
0x180074457  call    cs:__imp_GetWindowRect
0x18007445d  mov     r13d, 2
0x180074463  lea     r8, [rsp+8D0h+h]; lpPoints
0x180074468  mov     r9d, r13d; cPoints
0x18007446b  mov     rdx, r15; hWndTo
0x18007446e  xor     ecx, ecx; hWndFrom
0x180074470  call    cs:__imp_MapWindowPoints
0x180074476  mov     r9d, dword ptr [rsp+8D0h+h+4]
0x18007447b  xor     edx, edx; hWndInsertAfter
0x18007447d  mov     r8d, dword ptr [rsp+8D0h+h]; X
0x180074482  add     r9d, edi; Y
0x180074485  mov     [rsp+8D0h+uFlags], 15h; uFlags
0x18007448d  mov     rcx, rbx; hWnd
0x180074490  mov     [rsp+8D0h+cy], 0; cy
0x180074498  mov     [rsp+8D0h+format], 0; cx
0x1800744a0  call    cs:__imp_SetWindowPos
0x1800744a6  mov     r8d, [rsp+8D0h+Rect.bottom]
0x1800744ab  mov     r9d, [rsp+8D0h+var_878.top]
0x1800744b0  mov     esi, [rsp+8D0h+var_878.bottom]
0x1800744b4  jmp     short loc_1800744C5
0x1800744b6  mov     esi, [rsp+8D0h+var_878.bottom]
0x1800744ba  mov     r9d, [rsp+8D0h+var_878.top]
0x1800744bf  mov     r13d, 2
0x1800744c5  mov     r11d, [rsp+8D0h+Rect.right]
0x1800744ca  mov     ecx, 80000000h
0x1800744cf  sub     r11d, [rsp+8D0h+Rect.left]
0x1800744d4  sub     r8d, [rsp+8D0h+Rect.top]
0x1800744d9  mov     r10d, [r14+18h]
0x1800744dd  mov     ebx, [rsp+8D0h+var_878.right]
0x1800744e1  mov     edi, [rsp+8D0h+var_878.left]
0x1800744e5  cmp     r10d, ecx
0x1800744e8  jnz     short loc_1800744F8
0x1800744ea  mov     eax, ebx
0x1800744ec  sub     eax, r11d
0x1800744ef  sub     eax, edi
0x1800744f1  cdq
0x1800744f2  idiv    r13d
0x1800744f5  mov     r10d, eax
0x1800744f8  mov     edx, [r14+1Ch]
0x1800744fc  cmp     edx, ecx
0x1800744fe  jnz     short loc_18007451E
0x180074500  mov     ecx, esi
0x180074502  mov     eax, 55555556h
0x180074507  sub     ecx, r8d
0x18007450a  sub     ecx, r9d
0x18007450d  imul    ecx
0x18007450f  mov     eax, edx
0x180074511  shr     eax, 1Fh
0x180074514  add     edx, eax
0x180074516  cmp     edx, r9d
0x180074519  jge     short loc_18007451E
0x18007451b  mov     edx, r9d
0x18007451e  test    r12d, r12d
0x180074521  jz      short loc_18007454C
0x180074523  lea     eax, [r11+r10]
0x180074527  cmp     eax, ebx
0x180074529  jle     short loc_180074531
0x18007452b  mov     r10d, ebx
0x18007452e  sub     r10d, r11d
0x180074531  cmp     r10d, edi
0x180074534  lea     eax, [r11+rdx]
0x180074538  cmovl   r10d, edi
0x18007453c  cmp     eax, esi
0x18007453e  jle     short loc_180074545
0x180074540  mov     edx, esi
0x180074542  sub     edx, r8d
0x180074545  cmp     edx, r9d
0x180074548  cmovl   edx, r9d
0x18007454c  mov     ebx, 1
0x180074551  mov     r9d, r11d; nWidth
0x180074554  mov     [rsp+8D0h+cy], ebx; bRepaint
0x180074558  mov     rcx, r15; hWnd
0x18007455b  mov     [rsp+8D0h+format], r8d; nHeight
0x180074560  mov     r8d, edx; Y
0x180074563  mov     edx, r10d; X
0x180074566  call    cs:__imp_MoveWindow
0x18007456c  mov     rcx, r15; hWnd
0x18007456f  call    cs:__imp_SetForegroundWindow
0x180074575  mov     eax, ebx
0x180074577  jmp     short loc_180074583
0x180074579  mov     dword ptr [r14+38h], 8000FFFFh
0x180074581  xor     eax, eax
0x180074583  mov     rcx, [rbp+7D0h+var_40]
0x18007458a  xor     rcx, rsp; StackCookie
0x18007458d  call    __security_check_cookie
0x180074592  mov     rbx, [rsp+8D0h+arg_10]
0x18007459a  add     rsp, 8A0h
0x1800745a1  pop     r15
0x1800745a3  pop     r14
0x1800745a5  pop     r13
0x1800745a7  pop     r12
0x1800745a9  pop     rdi
0x1800745aa  pop     rsi
0x1800745ab  pop     rbp
0x1800745ac  retn
```
