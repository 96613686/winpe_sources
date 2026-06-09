# CACConnectionPage::OnPaint(uint,unsigned __int64,__int64,int &)

- ea: `0x18000e918`
- end: `0x18000ec4b`
- name: `?OnPaint@CACConnectionPage@@QEAA_JI_K_JAEAH@Z`
- size: `819`
- prototype: `__int64 __fastcall(CACConnectionPage *__hidden this, unsigned int, unsigned __int64, __int64, int *)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x18000ed80`

## callees

- `0x18000e918`
- `0x18001bf0a`
- `0x18001bf40`

## import_xrefs

- `GDI32!CreateSolidBrush` at `0x18000ea9b`
- `GDI32!CreateSolidBrush` at `0x18000ea9b`
- `GDI32!GetStockObject` at `0x18000eab8`
- `GDI32!GetStockObject` at `0x18000eab8`
- `GDI32!Rectangle` at `0x18000eae3`
- `GDI32!Rectangle` at `0x18000eae3`
- `GDI32!SetBkMode` at `0x18000eaf1`
- `GDI32!SetBkMode` at `0x18000eaf1`
- `GDI32!SetTextColor` at `0x18000eb07`
- `GDI32!SetTextColor` at `0x18000eb07`
- `GDI32!DeleteObject` at `0x18000eb7a`
- `GDI32!DeleteObject` at `0x18000eb7a`
- `GDI32!SelectObject` at `0x18000eaaa`
- `GDI32!SelectObject` at `0x18000eac4`
- `GDI32!SelectObject` at `0x18000eb35`
- `GDI32!SelectObject` at `0x18000eb71`
- `GDI32!SelectObject` at `0x18000eaaa`
- `GDI32!SelectObject` at `0x18000eac4`
- `GDI32!SelectObject` at `0x18000eb35`
- `GDI32!SelectObject` at `0x18000eb71`
- `USER32!EndPaint` at `0x18000ec12`
- `USER32!EndPaint` at `0x18000ec12`
- `USER32!DrawIcon` at `0x18000ec03`
- `USER32!DrawIcon` at `0x18000ec03`
- `USER32!DrawTextW` at `0x18000eb65`
- `USER32!DrawTextW` at `0x18000eb65`
- `USER32!GetSysColor` at `0x18000ea93`
- `USER32!GetSysColor` at `0x18000eafc`
- `USER32!GetSysColor` at `0x18000ea93`
- `USER32!GetSysColor` at `0x18000eafc`
- `USER32!BeginPaint` at `0x18000ea6c`
- `USER32!BeginPaint` at `0x18000ea6c`
- `USER32!LoadIconW` at `0x18000ea5a`
- `USER32!LoadIconW` at `0x18000ea5a`
- `USER32!LoadStringW` at `0x18000ea48`
- `USER32!LoadStringW` at `0x18000ea48`
- `USER32!GetDlgItem` at `0x18000eb16`
- `USER32!GetDlgItem` at `0x18000eb16`
- `USER32!SendMessageW` at `0x18000eb29`
- `USER32!SendMessageW` at `0x18000eb29`
- `UxTheme!DrawThemeBackground` at `0x18000eba4`
- `UxTheme!DrawThemeBackground` at `0x18000eba4`
- `UxTheme!DrawThemeText` at `0x18000ebe3`
- `UxTheme!DrawThemeText` at `0x18000ebe3`

## pseudocode

```c
__int64 __fastcall CACConnectionPage::OnPaint(CACConnectionPage *this, __int64 a2, __int64 a3, __int64 a4, int *a5)
{
  __int64 result; // rax
  double v7; // xmm6_8
  HICON IconW; // r14
  HDC v9; // rdi
  void *v10; // rcx
  DWORD SysColor; // eax
  HBRUSH SolidBrush; // r12
  HGDIOBJ v13; // r13
  HGDIOBJ StockObject; // rax
  DWORD v15; // eax
  HWND DlgItem; // rax
  void *v17; // rax
  __int64 v18; // rax
  RECT left; // [rsp+58h] [rbp-B0h] BYREF
  struct tagRECT rc; // [rsp+68h] [rbp-A0h] BYREF
  struct tagPAINTSTRUCT Paint; // [rsp+78h] [rbp-90h] BYREF
  WCHAR Buffer; // [rsp+C8h] [rbp-40h] BYREF
  _BYTE v23[1998]; // [rsp+CAh] [rbp-3Eh] BYREF

  memset_0(&Paint, 0, sizeof(Paint));
  *a5 = 0;
  Buffer = 0;
  memset_0(v23, 0, sizeof(v23));
  if ( !*((_DWORD *)this + 30) )
    return 1;
  v7 = *((double *)this + 103);
  left.left = (int)(v7 * 5.0);
  left.top = (int)(v7 * 10.0);
  left.right = (int)(v7 * 335.0);
  left.bottom = (int)(v7 * 62.0);
  rc.left = (int)(v7 * 60.0);
  rc.top = (int)(v7 * 20.0);
  rc.right = (int)(v7 * 325.0);
  rc.bottom = (int)(v7 * 55.0);
  LoadStringW(hModule, 0x439Eu, &Buffer, 1000);
  IconW = LoadIconW(hModule, (LPCWSTR)0x4650);
  v9 = BeginPaint(*((HWND *)this + 1), &Paint);
  if ( v9 )
  {
    v10 = (void *)*((_QWORD *)this + 98);
    if ( v10 )
    {
      DrawThemeBackground(v10, v9, 6, 11, &left, 0);
      DrawThemeText(*((HTHEME *)this + 98), v9, 6, 11, &Buffer, -1, 0x10u, 0, &rc);
    }
    else
    {
      SysColor = GetSysColor(5);
      SolidBrush = CreateSolidBrush(SysColor);
      v13 = SelectObject(v9, SolidBrush);
      StockObject = GetStockObject(8);
      SelectObject(v9, StockObject);
      Rectangle(v9, left.left, left.top, left.right, left.bottom);
      SetBkMode(v9, 1);
      v15 = GetSysColor(8);
      SetTextColor(v9, v15);
      DlgItem = GetDlgItem(*((HWND *)this + 1), 1008);
      v17 = (void *)SendMessageW(DlgItem, 0x31u, 0, 0);
      SelectObject(v9, v17);
      v18 = -1;
      do
        ++v18;
      while ( *(_WORD *)&v23[2 * v18 - 2] );
      DrawTextW(v9, &Buffer, v18, &rc, 0x10u);
      SelectObject(v9, v13);
      DeleteObject(SolidBrush);
    }
    if ( IconW )
      DrawIcon(v9, (int)(v7 * 15.0), (int)(v7 * 20.0), IconW);
  }
  EndPaint(*((HWND *)this + 1), &Paint);
  result = 0;
  *a5 = 1;
  return result;
}

```

## disassembly

```asm
0x18000e918  mov     rax, rsp
0x18000e91b  push    rbp
0x18000e91c  push    rbx
0x18000e91d  push    rsi
0x18000e91e  push    rdi
0x18000e91f  push    r12
0x18000e921  push    r13
0x18000e923  push    r14
0x18000e925  push    r15
0x18000e927  lea     rbp, [rax-7F8h]
0x18000e92e  sub     rsp, 8B8h
0x18000e935  movaps  xmmword ptr [rax-58h], xmm6
0x18000e939  mov     rax, cs:__security_cookie
0x18000e940  xor     rax, rsp
0x18000e943  mov     [rbp+7F0h+var_60], rax
0x18000e94a  mov     rsi, [rbp+7F0h+arg_20]
0x18000e951  xor     edx, edx; Val
0x18000e953  mov     rbx, rcx
0x18000e956  lea     rcx, [rsp+8F0h+Paint]; void *
0x18000e95b  lea     r8d, [rdx+48h]; Size
0x18000e95f  call    memset_0
0x18000e964  xor     r12d, r12d
0x18000e967  lea     rcx, [rbp+7F0h+var_82E]; void *
0x18000e96b  xor     edx, edx; Val
0x18000e96d  mov     [rsi], r12d
0x18000e970  mov     r8d, 7CEh; Size
0x18000e976  mov     [rbp+7F0h+Buffer], r12w
0x18000e97b  call    memset_0
0x18000e980  cmp     [rbx+78h], r12d
0x18000e984  jnz     short loc_18000E990
0x18000e986  lea     eax, [r12+1]
0x18000e98b  jmp     loc_18000EC20
0x18000e990  movsd   xmm6, qword ptr [rbx+338h]
0x18000e998  lea     r8, [rbp+7F0h+Buffer]; lpBuffer
0x18000e99c  mov     rcx, cs:hModule; hInstance
0x18000e9a3  movaps  xmm0, xmm6
0x18000e9a6  mulsd   xmm0, cs:__real@4014000000000000
0x18000e9ae  movaps  xmm1, xmm6
0x18000e9b1  mov     r9d, 3E8h; cchBufferMax
0x18000e9b7  mov     edx, 439Eh; uID
0x18000e9bc  mulsd   xmm1, cs:__real@4024000000000000
0x18000e9c4  cvttsd2si eax, xmm0
0x18000e9c8  movaps  xmm0, xmm6
0x18000e9cb  mulsd   xmm0, cs:__real@4074f00000000000
0x18000e9d3  mov     [rsp+8F0h+left], eax
0x18000e9d7  cvttsd2si eax, xmm1
0x18000e9db  movaps  xmm1, xmm6
0x18000e9de  mulsd   xmm1, cs:__real@404f000000000000
0x18000e9e6  mov     [rsp+8F0h+top], eax
0x18000e9ea  cvttsd2si eax, xmm0
0x18000e9ee  movaps  xmm0, xmm6
0x18000e9f1  mulsd   xmm0, cs:__real@404e000000000000
0x18000e9f9  mov     [rsp+8F0h+right], eax
0x18000e9fd  cvttsd2si eax, xmm1
0x18000ea01  movaps  xmm1, xmm6
0x18000ea04  mulsd   xmm1, cs:__real@4034000000000000
0x18000ea0c  mov     [rsp+8F0h+var_894], eax
0x18000ea10  cvttsd2si eax, xmm0
0x18000ea14  cvttsd2si r15d, xmm1
0x18000ea19  mov     [rsp+8F0h+rc.left], eax
0x18000ea1d  movaps  xmm0, xmm6
0x18000ea20  movaps  xmm1, xmm6
0x18000ea23  mulsd   xmm0, cs:__real@4074500000000000
0x18000ea2b  mov     [rsp+8F0h+rc.top], r15d
0x18000ea30  mulsd   xmm1, cs:__real@404b800000000000
0x18000ea38  cvttsd2si eax, xmm0
0x18000ea3c  mov     [rsp+8F0h+rc.right], eax
0x18000ea40  cvttsd2si eax, xmm1
0x18000ea44  mov     [rsp+8F0h+rc.bottom], eax
0x18000ea48  call    cs:__imp_LoadStringW
0x18000ea4e  mov     rcx, cs:hModule; hInstance
0x18000ea55  mov     edx, 4650h; lpIconName
0x18000ea5a  call    cs:__imp_LoadIconW
0x18000ea60  mov     rcx, [rbx+8]; hWnd
0x18000ea64  lea     rdx, [rsp+8F0h+Paint]; lpPaint
0x18000ea69  mov     r14, rax
0x18000ea6c  call    cs:__imp_BeginPaint
0x18000ea72  mov     rdi, rax
0x18000ea75  test    rax, rax
0x18000ea78  jz      loc_18000EC09
0x18000ea7e  mov     rcx, [rbx+310h]; hTheme
0x18000ea85  test    rcx, rcx
0x18000ea88  jnz     loc_18000EB82
0x18000ea8e  mov     ecx, 5; nIndex
0x18000ea93  call    cs:__imp_GetSysColor
0x18000ea99  mov     ecx, eax; color
0x18000ea9b  call    cs:__imp_CreateSolidBrush
0x18000eaa1  mov     rdx, rax; h
0x18000eaa4  mov     rcx, rdi; hdc
0x18000eaa7  mov     r12, rax
0x18000eaaa  call    cs:__imp_SelectObject
0x18000eab0  mov     ecx, 8; i
0x18000eab5  mov     r13, rax
0x18000eab8  call    cs:__imp_GetStockObject
0x18000eabe  mov     rdx, rax; h
0x18000eac1  mov     rcx, rdi; hdc
0x18000eac4  call    cs:__imp_SelectObject
0x18000eaca  mov     edx, [rsp+8F0h+var_894]
0x18000eace  mov     rcx, rdi; hdc
0x18000ead1  mov     r9d, [rsp+8F0h+right]; right
0x18000ead6  mov     r8d, [rsp+8F0h+top]; top
0x18000eadb  mov     [rsp+8F0h+bottom], edx; bottom
0x18000eadf  mov     edx, [rsp+8F0h+left]; left
0x18000eae3  call    cs:__imp_Rectangle
0x18000eae9  mov     edx, 1; mode
0x18000eaee  mov     rcx, rdi; hdc
0x18000eaf1  call    cs:__imp_SetBkMode
0x18000eaf7  mov     ecx, 8; nIndex
0x18000eafc  call    cs:__imp_GetSysColor
0x18000eb02  mov     edx, eax; color
0x18000eb04  mov     rcx, rdi; hdc
0x18000eb07  call    cs:__imp_SetTextColor
0x18000eb0d  mov     rcx, [rbx+8]; hDlg
0x18000eb11  mov     edx, 3F0h; nIDDlgItem
0x18000eb16  call    cs:__imp_GetDlgItem
0x18000eb1c  xor     r9d, r9d; lParam
0x18000eb1f  xor     r8d, r8d; wParam
0x18000eb22  mov     rcx, rax; hWnd
0x18000eb25  lea     edx, [r9+31h]; Msg
0x18000eb29  call    cs:__imp_SendMessageW
0x18000eb2f  mov     rdx, rax; h
0x18000eb32  mov     rcx, rdi; hdc
0x18000eb35  call    cs:__imp_SelectObject
0x18000eb3b  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000eb3f  lea     rdx, [rbp+7F0h+Buffer]
0x18000eb43  xor     ecx, ecx
0x18000eb45  inc     rax
0x18000eb48  cmp     [rdx+rax*2], cx
0x18000eb4c  jnz     short loc_18000EB45
0x18000eb4e  mov     r8d, eax; cchText
0x18000eb51  mov     [rsp+8F0h+bottom], 10h; format
0x18000eb59  lea     r9, [rsp+8F0h+rc]; lprc
0x18000eb5e  mov     rcx, rdi; hdc
0x18000eb61  lea     rdx, [rbp+7F0h+Buffer]; lpchText
0x18000eb65  call    cs:__imp_DrawTextW
0x18000eb6b  mov     rdx, r13; h
0x18000eb6e  mov     rcx, rdi; hdc
0x18000eb71  call    cs:__imp_SelectObject
0x18000eb77  mov     rcx, r12; ho
0x18000eb7a  call    cs:__imp_DeleteObject
0x18000eb80  jmp     short loc_18000EBE9
0x18000eb82  mov     r13d, 0Bh
0x18000eb88  mov     [rsp+8F0h+pClipRect], r12; pClipRect
0x18000eb8d  lea     rax, [rsp+8F0h+left]
0x18000eb92  mov     r9d, r13d; iStateId
0x18000eb95  mov     rdx, rdi; hdc
0x18000eb98  mov     qword ptr [rsp+8F0h+bottom], rax; pRect
0x18000eb9d  lea     r12d, [r13-5]
0x18000eba1  mov     r8d, r12d; iPartId
0x18000eba4  call    cs:__imp_DrawThemeBackground
0x18000ebaa  xor     ecx, ecx
0x18000ebac  lea     rax, [rsp+8F0h+rc]
0x18000ebb1  mov     [rsp+40h], rax; pRect
0x18000ebb6  mov     r9d, r13d; iStateId
0x18000ebb9  mov     [rsp+8F0h+dwTextFlags2], ecx; dwTextFlags2
0x18000ebbd  lea     rax, [rbp+7F0h+Buffer]
0x18000ebc1  mov     rcx, [rbx+310h]; hTheme
0x18000ebc8  mov     r8d, r12d; iPartId
0x18000ebcb  mov     [rsp+8F0h+dwTextFlags], 10h; dwTextFlags
0x18000ebd3  mov     rdx, rdi; hdc
0x18000ebd6  mov     dword ptr [rsp+8F0h+pClipRect], 0FFFFFFFFh; cchText
0x18000ebde  mov     qword ptr [rsp+8F0h+bottom], rax; pszText
0x18000ebe3  call    cs:__imp_DrawThemeText
0x18000ebe9  test    r14, r14
0x18000ebec  jz      short loc_18000EC09
0x18000ebee  mulsd   xmm6, cs:__real@402e000000000000
0x18000ebf6  mov     r9, r14; hIcon
0x18000ebf9  mov     r8d, r15d; Y
0x18000ebfc  mov     rcx, rdi; hDC
0x18000ebff  cvttsd2si edx, xmm6; X
0x18000ec03  call    cs:__imp_DrawIcon
0x18000ec09  mov     rcx, [rbx+8]; hWnd
0x18000ec0d  lea     rdx, [rsp+8F0h+Paint]; lpPaint
0x18000ec12  call    cs:__imp_EndPaint
0x18000ec18  xor     eax, eax
0x18000ec1a  mov     dword ptr [rsi], 1
0x18000ec20  mov     rcx, [rbp+7F0h+var_60]
0x18000ec27  xor     rcx, rsp; StackCookie
0x18000ec2a  call    __security_check_cookie
0x18000ec2f  movaps  xmm6, [rsp+8F0h+var_58+8]
0x18000ec37  add     rsp, 8B8h
0x18000ec3e  pop     r15
0x18000ec40  pop     r14
0x18000ec42  pop     r13
0x18000ec44  pop     r12
0x18000ec46  pop     rdi
0x18000ec47  pop     rsi
0x18000ec48  pop     rbx
0x18000ec49  pop     rbp
0x18000ec4a  retn
```
