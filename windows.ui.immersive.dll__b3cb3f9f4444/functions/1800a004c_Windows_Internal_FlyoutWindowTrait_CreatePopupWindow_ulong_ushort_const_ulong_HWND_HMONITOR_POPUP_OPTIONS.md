# Windows::Internal::FlyoutWindowTrait::CreatePopupWindow(ulong,ushort const *,ulong,HWND__ *,HMONITOR__ *,POPUP_OPTIONS)

- ea: `0x1800a004c`
- end: `0x1800a0341`
- name: `?CreatePopupWindow@FlyoutWindowTrait@Internal@Windows@@QEAAPEAUHWND__@@KPEBGKPEAU4@PEAUHMONITOR__@@W4POPUP_OPTIONS@@@Z`
- size: `757`
- prototype: `HWND __high(unsigned int, const unsigned __int16 *, unsigned int, HWND, HMONITOR, enum POPUP_OPTIONS)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x18008e800`

## callees

- `0x180030d44`
- `0x180054130`
- `0x180054ad4`
- `0x1800a004c`

## import_xrefs

- `USER32!CreateWindowInBandEx` at `0x1800a021f`
- `USER32!CreateWindowInBandEx` at `0x1800a021f`
- `USER32!GetMonitorInfoW` at `0x1800a01b0`
- `USER32!GetMonitorInfoW` at `0x1800a01b0`
- `USER32!CreateWindowExW` at `0x1800a029f`
- `USER32!CreateWindowExW` at `0x1800a029f`
- `USER32!RegisterClassW` at `0x1800a0103`
- `USER32!RegisterClassW` at `0x1800a0103`
- `USER32!LoadCursorW` at `0x1800a00dc`
- `USER32!LoadCursorW` at `0x1800a00dc`
- `USER32!GetWindowRect` at `0x1800a0241`
- `USER32!GetWindowRect` at `0x1800a0241`
- `USER32!SendMessageW` at `0x1800a0311`
- `USER32!SendMessageW` at `0x1800a0311`
- `dwmapi!DwmSetWindowAttribute` at `0x1800a02db`
- `dwmapi!DwmSetWindowAttribute` at `0x1800a02db`

## pseudocode

```c
HWND __fastcall Windows::Internal::FlyoutWindowTrait::CreatePopupWindow(
        __int64 a1,
        DWORD a2,
        const WCHAR *a3,
        DWORD a4,
        HWND hWnd,
        __int64 a6,
        int a7)
{
  DWORD v7; // eax
  bool v8; // zf
  HCURSOR CursorW; // rax
  LONG X; // ebx
  LONG Y; // r15d
  int nWidth; // edi
  int nHeight; // esi
  int v16; // ecx
  int v17; // eax
  int v18; // r14d
  HMONITOR v19; // rcx
  HWND WindowInBand; // rax
  HWND v21; // rbx
  int pvAttribute; // [rsp+70h] [rbp-90h] BYREF
  int v24; // [rsp+74h] [rbp-8Ch]
  DWORD dwExStyle; // [rsp+78h] [rbp-88h]
  LPCWSTR lpWindowName; // [rsp+80h] [rbp-80h]
  WNDCLASSW WndClass; // [rsp+90h] [rbp-70h] BYREF
  struct tagRECT Rect; // [rsp+E0h] [rbp-20h] BYREF
  struct tagMONITORINFO mi; // [rsp+F0h] [rbp-10h] BYREF

  v7 = a2 | 0x8000000;
  v8 = *(_BYTE *)(a1 + 8) == 0;
  lpWindowName = a3;
  if ( v8 )
    v7 = a2;
  *(_DWORD *)(a1 + 36) = a7;
  dwExStyle = v7;
  *(_QWORD *)(a1 + 40) = a6;
  memset_0(&WndClass, 0, sizeof(WndClass));
  WndClass.style = 520;
  WndClass.lpfnWndProc = (WNDPROC)NoUIAWindowProc;
  WndClass.hInstance = &_ImageBase;
  CursorW = LoadCursorW(0, (LPCWSTR)0x7F00);
  WndClass.hbrBackground = (HBRUSH)6;
  WndClass.hCursor = CursorW;
  WndClass.lpszClassName = L"Shell_Flyout";
  RegisterClassW(&WndClass);
  pvAttribute = a7 & 0x40000000;
  if ( (a7 & 0x40000000) != 0 && (a7 & 0x40000) == 0 )
    a4 |= 0x800000u;
  X = 0x80000000;
  Y = 0x80000000;
  nWidth = 0x80000000;
  nHeight = 0x80000000;
  if ( !hWnd )
  {
    v16 = *(_DWORD *)(a1 + 36);
    v17 = v16 & 0x800000;
    if ( (v16 & 4) != 0 )
    {
      v18 = 1;
    }
    else
    {
      if ( !v17 )
      {
        v18 = (v16 & 0x10000000) != 0 ? 18 : 4;
        goto LABEL_14;
      }
      v18 = 13;
    }
    if ( v17 == 0x800000 )
    {
      v24 = 1;
      goto LABEL_15;
    }
LABEL_14:
    v24 = 0;
LABEL_15:
    v19 = *(HMONITOR *)(a1 + 40);
    if ( v19 )
    {
      if ( *(_BYTE *)(a1 + 49) )
      {
        mi.cbSize = 40;
        memset(&mi.rcMonitor, 0, 36);
        if ( GetMonitorInfoW(v19, &mi) )
        {
          X = mi.rcWork.left;
          nWidth = mi.rcWork.right - mi.rcWork.left;
          Y = mi.rcWork.top;
          nHeight = mi.rcWork.bottom - mi.rcWork.top;
        }
      }
    }
    WindowInBand = (HWND)CreateWindowInBandEx(
                           dwExStyle,
                           L"Shell_Flyout",
                           lpWindowName,
                           a4,
                           X,
                           Y,
                           nWidth,
                           nHeight,
                           0,
                           0,
                           &_ImageBase,
                           0,
                           v18,
                           v24);
    goto LABEL_23;
  }
  if ( *(_BYTE *)(a1 + 48) )
  {
    Rect = 0;
    GetWindowRect(hWnd, &Rect);
    X = Rect.left;
    nWidth = Rect.right - Rect.left;
    Y = Rect.top;
    nHeight = Rect.bottom - Rect.top;
  }
  WindowInBand = CreateWindowExW(
                   dwExStyle,
                   L"Shell_Flyout",
                   lpWindowName,
                   a4,
                   X,
                   Y,
                   nWidth,
                   nHeight,
                   hWnd,
                   0,
                   &_ImageBase,
                   0);
LABEL_23:
  v21 = WindowInBand;
  if ( pvAttribute && (a7 & 0x40000) == 0 )
  {
    pvAttribute = 2;
    DwmSetWindowAttribute(WindowInBand, 0x21u, &pvAttribute, 4u);
  }
  if ( v21 )
  {
    if ( (*(_DWORD *)(a1 + 36) & 0x4000) != 0 )
      SetIhmRequireTouchInEditField(1, v21);
    SendMessageW(v21, 0x127u, 0x30001u, 0);
  }
  return v21;
}

```

## disassembly

```asm
0x1800a004c  push    rbp
0x1800a004e  push    rbx
0x1800a004f  push    rsi
0x1800a0050  push    rdi
0x1800a0051  push    r12
0x1800a0053  push    r13
0x1800a0055  push    r14
0x1800a0057  push    r15
0x1800a0059  lea     rbp, [rsp-28h]
0x1800a005e  sub     rsp, 128h
0x1800a0065  mov     rax, cs:__security_cookie
0x1800a006c  xor     rax, rsp
0x1800a006f  mov     [rbp+60h+var_48], rax
0x1800a0073  mov     ebx, [rbp+60h+arg_30]
0x1800a0079  mov     eax, edx
0x1800a007b  mov     r14, [rbp+60h+hWnd]
0x1800a0082  bts     eax, 1Bh
0x1800a0086  cmp     byte ptr [rcx+8], 0
0x1800a008a  mov     r13, rcx
0x1800a008d  mov     [rbp+60h+lpWindowName], r8
0x1800a0091  mov     r12d, r9d
0x1800a0094  cmovz   eax, edx
0x1800a0097  mov     [rcx+24h], ebx
0x1800a009a  xor     edx, edx; Val
0x1800a009c  mov     [rsp+160h+dwExStyle], eax
0x1800a00a0  mov     rax, [rbp+60h+arg_28]
0x1800a00a7  mov     [rcx+28h], rax
0x1800a00ab  lea     rcx, [rbp+60h+WndClass]; void *
0x1800a00af  lea     r8d, [rdx+48h]; Size
0x1800a00b3  call    memset_0
0x1800a00b8  lea     rax, ?NoUIAWindowProc@@YA_JPEAUHWND__@@I_K_J@Z; NoUIAWindowProc(HWND__ *,uint,unsigned __int64,__int64)
0x1800a00bf  mov     [rbp+60h+WndClass.style], 208h
0x1800a00c6  mov     [rbp+60h+WndClass.lpfnWndProc], rax
0x1800a00ca  mov     edx, 7F00h; lpCursorName
0x1800a00cf  lea     rax, __ImageBase
0x1800a00d6  xor     ecx, ecx; hInstance
0x1800a00d8  mov     [rbp+60h+WndClass.hInstance], rax
0x1800a00dc  call    cs:__imp_LoadCursorW
0x1800a00e3  nop     dword ptr [rax+rax+00h]
0x1800a00e8  lea     rcx, [rbp+60h+WndClass]; lpWndClass
0x1800a00ec  mov     [rbp+60h+WndClass.hbrBackground], 6
0x1800a00f4  mov     [rbp+60h+WndClass.hCursor], rax
0x1800a00f8  lea     rax, ClassName; "Shell_Flyout"
0x1800a00ff  mov     [rbp+60h+WndClass.lpszClassName], rax
0x1800a0103  call    cs:__imp_RegisterClassW
0x1800a010a  nop     dword ptr [rax+rax+00h]
0x1800a010f  mov     eax, ebx
0x1800a0111  mov     r8d, 800000h
0x1800a0117  and     eax, 40000000h
0x1800a011c  mov     [rsp+160h+pvAttribute], eax
0x1800a0120  jz      short loc_1800A012B
0x1800a0122  bt      ebx, 12h
0x1800a0126  jb      short loc_1800A012B
0x1800a0128  or      r12d, r8d
0x1800a012b  mov     ebx, 80000000h
0x1800a0130  xor     edx, edx
0x1800a0132  mov     r15d, ebx
0x1800a0135  mov     edi, ebx
0x1800a0137  mov     esi, ebx
0x1800a0139  lea     r9d, [rdx+1]
0x1800a013d  test    r14, r14
0x1800a0140  jnz     loc_1800A022D
0x1800a0146  mov     ecx, [r13+24h]
0x1800a014a  mov     eax, ecx
0x1800a014c  and     eax, r8d
0x1800a014f  test    cl, 4
0x1800a0152  jz      short loc_1800A0159
0x1800a0154  mov     r14d, r9d
0x1800a0157  jmp     short loc_1800A0163
0x1800a0159  test    eax, eax
0x1800a015b  jz      short loc_1800A016F
0x1800a015d  mov     r14d, 0Dh
0x1800a0163  cmp     eax, r8d
0x1800a0166  jnz     short loc_1800A0182
0x1800a0168  mov     [rsp+160h+var_EC], r9d
0x1800a016d  jmp     short loc_1800A0186
0x1800a016f  and     ecx, 10000000h
0x1800a0175  neg     ecx
0x1800a0177  sbb     r14d, r14d
0x1800a017a  and     r14d, 0Eh
0x1800a017e  add     r14d, 4
0x1800a0182  mov     [rsp+160h+var_EC], edx
0x1800a0186  mov     rcx, [r13+28h]; hMonitor
0x1800a018a  test    rcx, rcx
0x1800a018d  jz      short loc_1800A01D4
0x1800a018f  cmp     [r13+31h], dl
0x1800a0193  jz      short loc_1800A01D4
0x1800a0195  xorps   xmm0, xmm0
0x1800a0198  mov     [rbp+60h+mi.cbSize], 28h ; '('
0x1800a019f  xor     eax, eax
0x1800a01a1  lea     rdx, [rbp+60h+mi]; lpmi
0x1800a01a5  movups  xmmword ptr [rbp+60h+mi.rcMonitor.left], xmm0
0x1800a01a9  mov     [rbp+60h+mi.dwFlags], eax
0x1800a01ac  movups  xmmword ptr [rbp+60h+mi.rcWork.left], xmm0
0x1800a01b0  call    cs:__imp_GetMonitorInfoW
0x1800a01b7  nop     dword ptr [rax+rax+00h]
0x1800a01bc  xor     edx, edx
0x1800a01be  test    eax, eax
0x1800a01c0  jz      short loc_1800A01D4
0x1800a01c2  mov     edi, [rbp+60h+mi.rcWork.right]
0x1800a01c5  mov     ebx, [rbp+60h+mi.rcWork.left]
0x1800a01c8  sub     edi, ebx
0x1800a01ca  mov     esi, [rbp+60h+mi.rcWork.bottom]
0x1800a01cd  mov     r15d, [rbp+60h+mi.rcWork.top]
0x1800a01d1  sub     esi, r15d
0x1800a01d4  mov     eax, [rsp+160h+var_EC]
0x1800a01d8  mov     r9d, r12d
0x1800a01db  mov     r8, [rbp+60h+lpWindowName]
0x1800a01df  mov     ecx, [rsp+160h+dwExStyle]
0x1800a01e3  mov     [rsp+160h+var_F8], eax
0x1800a01e7  lea     rax, __ImageBase
0x1800a01ee  mov     [rsp+160h+var_100], r14d
0x1800a01f3  mov     [rsp+160h+lpParam], rdx
0x1800a01f8  mov     [rsp+160h+hInstance], rax
0x1800a01fd  mov     [rsp+160h+hMenu], rdx
0x1800a0202  mov     [rsp+160h+hWndParent], rdx
0x1800a0207  lea     rdx, ClassName; "Shell_Flyout"
0x1800a020e  mov     [rsp+160h+nHeight], esi
0x1800a0212  mov     [rsp+160h+nWidth], edi
0x1800a0216  mov     [rsp+160h+Y], r15d
0x1800a021b  mov     [rsp+160h+X], ebx
0x1800a021f  call    cs:__imp_CreateWindowInBandEx
0x1800a0226  nop     dword ptr [rax+rax+00h]
0x1800a022b  jmp     short loc_1800A02AB
0x1800a022d  cmp     [r13+30h], dl
0x1800a0231  jz      short loc_1800A0261
0x1800a0233  xorps   xmm0, xmm0
0x1800a0236  lea     rdx, [rbp+60h+Rect]; lpRect
0x1800a023a  mov     rcx, r14; hWnd
0x1800a023d  movups  xmmword ptr [rbp+60h+Rect.left], xmm0
0x1800a0241  call    cs:__imp_GetWindowRect
0x1800a0248  nop     dword ptr [rax+rax+00h]
0x1800a024d  mov     edi, [rbp+60h+Rect.right]
0x1800a0250  mov     esi, [rbp+60h+Rect.bottom]
0x1800a0253  mov     ebx, [rbp+60h+Rect.left]
0x1800a0256  sub     edi, ebx
0x1800a0258  mov     r15d, [rbp+60h+Rect.top]
0x1800a025c  sub     esi, r15d
0x1800a025f  xor     edx, edx
0x1800a0261  mov     r8, [rbp+60h+lpWindowName]; lpWindowName
0x1800a0265  lea     rax, __ImageBase
0x1800a026c  mov     ecx, [rsp+160h+dwExStyle]; dwExStyle
0x1800a0270  mov     r9d, r12d; dwStyle
0x1800a0273  mov     [rsp+160h+lpParam], rdx; lpParam
0x1800a0278  mov     [rsp+160h+hInstance], rax; hInstance
0x1800a027d  mov     [rsp+160h+hMenu], rdx; hMenu
0x1800a0282  lea     rdx, ClassName; "Shell_Flyout"
0x1800a0289  mov     [rsp+160h+hWndParent], r14; hWndParent
0x1800a028e  mov     [rsp+160h+nHeight], esi; nHeight
0x1800a0292  mov     [rsp+160h+nWidth], edi; nWidth
0x1800a0296  mov     [rsp+160h+Y], r15d; Y
0x1800a029b  mov     [rsp+160h+X], ebx; X
0x1800a029f  call    cs:__imp_CreateWindowExW
0x1800a02a6  nop     dword ptr [rax+rax+00h]
0x1800a02ab  cmp     [rsp+160h+pvAttribute], 0
0x1800a02b0  mov     rbx, rax
0x1800a02b3  jz      short loc_1800A02E7
0x1800a02b5  test    [rbp+60h+arg_30], 40000h
0x1800a02bf  jnz     short loc_1800A02E7
0x1800a02c1  mov     r9d, 4; cbAttribute
0x1800a02c7  mov     [rsp+160h+pvAttribute], 2
0x1800a02cf  lea     r8, [rsp+160h+pvAttribute]; pvAttribute
0x1800a02d4  mov     rcx, rax; hwnd
0x1800a02d7  lea     edx, [r9+1Dh]; dwAttribute
0x1800a02db  call    cs:__imp_DwmSetWindowAttribute
0x1800a02e2  nop     dword ptr [rax+rax+00h]
0x1800a02e7  test    rbx, rbx
0x1800a02ea  jz      short loc_1800A031D
0x1800a02ec  test    dword ptr [r13+24h], 4000h
0x1800a02f4  jz      short loc_1800A0300
0x1800a02f6  mov     rdx, rbx; HWND
0x1800a02f9  mov     cl, 1; bool
0x1800a02fb  call    ?SetIhmRequireTouchInEditField@@YA_N_NPEAUHWND__@@@Z; SetIhmRequireTouchInEditField(bool,HWND__ *)
0x1800a0300  xor     r9d, r9d; lParam
0x1800a0303  mov     edx, 127h; Msg
0x1800a0308  mov     r8d, 30001h; wParam
0x1800a030e  mov     rcx, rbx; hWnd
0x1800a0311  call    cs:__imp_SendMessageW
0x1800a0318  nop     dword ptr [rax+rax+00h]
0x1800a031d  mov     rax, rbx
0x1800a0320  mov     rcx, [rbp+60h+var_48]
0x1800a0324  xor     rcx, rsp; StackCookie
0x1800a0327  call    __security_check_cookie
0x1800a032c  add     rsp, 128h
0x1800a0333  pop     r15
0x1800a0335  pop     r14
0x1800a0337  pop     r13
0x1800a0339  pop     r12
0x1800a033b  pop     rdi
0x1800a033c  pop     rsi
0x1800a033d  pop     rbx
0x1800a033e  pop     rbp
0x1800a033f  retn
```
