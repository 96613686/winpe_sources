# CACSecurityPage::OnPaint(uint,unsigned __int64,__int64,int &)

- ea: `0x18000ad4c`
- end: `0x18000b072`
- name: `?OnPaint@CACSecurityPage@@QEAA_JI_K_JAEAH@Z`
- size: `806`
- prototype: `__int64 __fastcall(CACSecurityPage *__hidden this, unsigned int, unsigned __int64, __int64, int *)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18000c290`

## callees

- `0x18000ad4c`
- `0x18001bf0a`
- `0x18001bf40`

## import_xrefs

- `GDI32!CreateSolidBrush` at `0x18000aed6`
- `GDI32!CreateSolidBrush` at `0x18000aed6`
- `GDI32!GetStockObject` at `0x18000aef3`
- `GDI32!GetStockObject` at `0x18000aef3`
- `GDI32!Rectangle` at `0x18000af1e`
- `GDI32!Rectangle` at `0x18000af1e`
- `GDI32!SetBkMode` at `0x18000af2c`
- `GDI32!SetBkMode` at `0x18000af2c`
- `GDI32!SetTextColor` at `0x18000af42`
- `GDI32!SetTextColor` at `0x18000af42`
- `GDI32!DeleteObject` at `0x18000afb5`
- `GDI32!DeleteObject` at `0x18000afb5`
- `GDI32!SelectObject` at `0x18000aee5`
- `GDI32!SelectObject` at `0x18000aeff`
- `GDI32!SelectObject` at `0x18000af70`
- `GDI32!SelectObject` at `0x18000afac`
- `GDI32!SelectObject` at `0x18000aee5`
- `GDI32!SelectObject` at `0x18000aeff`
- `GDI32!SelectObject` at `0x18000af70`
- `GDI32!SelectObject` at `0x18000afac`
- `USER32!EndPaint` at `0x18000b041`
- `USER32!EndPaint` at `0x18000b041`
- `USER32!DrawIcon` at `0x18000b033`
- `USER32!DrawIcon` at `0x18000b033`
- `USER32!DrawTextW` at `0x18000afa0`
- `USER32!DrawTextW` at `0x18000afa0`
- `USER32!GetSysColor` at `0x18000aece`
- `USER32!GetSysColor` at `0x18000af37`
- `USER32!GetSysColor` at `0x18000aece`
- `USER32!GetSysColor` at `0x18000af37`
- `USER32!BeginPaint` at `0x18000aea7`
- `USER32!BeginPaint` at `0x18000aea7`
- `USER32!LoadIconW` at `0x18000ae94`
- `USER32!LoadIconW` at `0x18000ae94`
- `USER32!LoadStringW` at `0x18000ae82`
- `USER32!LoadStringW` at `0x18000ae82`
- `USER32!GetDlgItem` at `0x18000af51`
- `USER32!GetDlgItem` at `0x18000af51`
- `USER32!SendMessageW` at `0x18000af64`
- `USER32!SendMessageW` at `0x18000af64`
- `UxTheme!DrawThemeBackground` at `0x18000afe0`
- `UxTheme!DrawThemeBackground` at `0x18000afe0`
- `UxTheme!DrawThemeText` at `0x18000b01f`
- `UxTheme!DrawThemeText` at `0x18000b01f`

## pseudocode

```c
__int64 __fastcall CACSecurityPage::OnPaint(CACSecurityPage *this, __int64 a2, __int64 a3, __int64 a4, int *a5)
{
  __int64 result; // rax
  double v7; // xmm2_8
  HDC v8; // rdi
  void *v9; // rcx
  DWORD SysColor; // eax
  HBRUSH SolidBrush; // r14
  HGDIOBJ v12; // r12
  HGDIOBJ StockObject; // rax
  DWORD v14; // eax
  HWND DlgItem; // rax
  void *v16; // rax
  __int64 v17; // rax
  HICON hIcon; // [rsp+50h] [rbp-B0h]
  RECT left; // [rsp+58h] [rbp-A8h] BYREF
  struct tagRECT rc; // [rsp+68h] [rbp-98h] BYREF
  tagPAINTSTRUCT Paint; // [rsp+80h] [rbp-80h] BYREF
  WCHAR Buffer; // [rsp+D0h] [rbp-30h] BYREF
  _BYTE v23[1998]; // [rsp+D2h] [rbp-2Eh] BYREF

  memset_0(&Paint, 0, sizeof(Paint));
  *a5 = 0;
  Buffer = 0;
  memset_0(v23, 0, sizeof(v23));
  if ( !*((_DWORD *)this + 23) )
    return 1;
  v7 = *((double *)this + 163);
  left.left = (int)(v7 * 5.0);
  left.top = (int)(v7 * 10.0);
  left.right = (int)(v7 * 335.0);
  left.bottom = (int)(v7 * 62.0);
  rc.left = (int)(v7 * 60.0);
  rc.top = (int)(v7 * 20.0);
  rc.right = (int)(v7 * 325.0);
  rc.bottom = (int)(v7 * 55.0);
  LoadStringW(hModule, 0x439Eu, &Buffer, 1000);
  hIcon = LoadIconW(hModule, (LPCWSTR)0x4650);
  v8 = BeginPaint(*((HWND *)this + 1), &Paint);
  if ( v8 )
  {
    v9 = (void *)*((_QWORD *)this + 158);
    if ( v9 )
    {
      DrawThemeBackground(v9, v8, 6, 11, &left, 0);
      DrawThemeText(*((HTHEME *)this + 158), v8, 6, 11, &Buffer, -1, 0x10u, 0, &rc);
    }
    else
    {
      SysColor = GetSysColor(5);
      SolidBrush = CreateSolidBrush(SysColor);
      v12 = SelectObject(v8, SolidBrush);
      StockObject = GetStockObject(8);
      SelectObject(v8, StockObject);
      Rectangle(v8, left.left, left.top, left.right, left.bottom);
      SetBkMode(v8, 1);
      v14 = GetSysColor(8);
      SetTextColor(v8, v14);
      DlgItem = GetDlgItem(*((HWND *)this + 1), 1008);
      v16 = (void *)SendMessageW(DlgItem, 0x31u, 0, 0);
      SelectObject(v8, v16);
      v17 = -1;
      do
        ++v17;
      while ( *(_WORD *)&v23[2 * v17 - 2] );
      DrawTextW(v8, &Buffer, v17, &rc, 0x10u);
      SelectObject(v8, v12);
      DeleteObject(SolidBrush);
    }
  }
  DrawIcon(v8, (int)(v7 * 15.0), (int)(v7 * 20.0), hIcon);
  EndPaint(*((HWND *)this + 1), &Paint);
  result = 0;
  *a5 = 1;
  return result;
}

```

## disassembly

```asm
0x18000ad4c  push    rbp
0x18000ad4e  push    rbx
0x18000ad4f  push    rsi
0x18000ad50  push    rdi
0x18000ad51  push    r12
0x18000ad53  push    r13
0x18000ad55  push    r14
0x18000ad57  push    r15
0x18000ad59  lea     rbp, [rsp-7B8h]
0x18000ad61  sub     rsp, 8B8h
0x18000ad68  mov     rax, cs:__security_cookie
0x18000ad6f  xor     rax, rsp
0x18000ad72  mov     [rbp+7F0h+var_50], rax
0x18000ad79  mov     rsi, [rbp+7F0h+arg_20]
0x18000ad80  xor     edx, edx; Val
0x18000ad82  mov     rbx, rcx
0x18000ad85  lea     rcx, [rbp+7F0h+Paint]; void *
0x18000ad89  lea     r8d, [rdx+48h]; Size
0x18000ad8d  call    memset_0
0x18000ad92  xor     r14d, r14d
0x18000ad95  lea     rcx, [rbp+7F0h+var_81E]; void *
0x18000ad99  xor     edx, edx; Val
0x18000ad9b  mov     [rsi], r14d
0x18000ad9e  mov     r8d, 7CEh; Size
0x18000ada4  mov     [rbp+7F0h+Buffer], r14w
0x18000ada9  call    memset_0
0x18000adae  cmp     [rbx+5Ch], r14d
0x18000adb2  jnz     short loc_18000ADBD
0x18000adb4  lea     eax, [r14+1]
0x18000adb8  jmp     loc_18000B04F
0x18000adbd  movsd   xmm2, qword ptr [rbx+518h]
0x18000adc5  lea     r8, [rbp+7F0h+Buffer]; lpBuffer
0x18000adc9  mov     rcx, cs:hModule; hInstance
0x18000add0  movaps  xmm0, xmm2
0x18000add3  mulsd   xmm0, cs:__real@4014000000000000
0x18000addb  movaps  xmm1, xmm2
0x18000adde  mov     r9d, 3E8h; cchBufferMax
0x18000ade4  mov     edx, 439Eh; uID
0x18000ade9  mulsd   xmm1, cs:__real@4024000000000000
0x18000adf1  cvttsd2si eax, xmm0
0x18000adf5  movaps  xmm0, xmm2
0x18000adf8  mulsd   xmm0, cs:__real@4074f00000000000
0x18000ae00  mov     [rsp+8F0h+left], eax
0x18000ae04  cvttsd2si eax, xmm1
0x18000ae08  movaps  xmm1, xmm2
0x18000ae0b  mulsd   xmm1, cs:__real@404f000000000000
0x18000ae13  mov     [rsp+8F0h+top], eax
0x18000ae17  cvttsd2si eax, xmm0
0x18000ae1b  movaps  xmm0, xmm2
0x18000ae1e  mulsd   xmm0, cs:__real@404e000000000000
0x18000ae26  mov     [rsp+8F0h+right], eax
0x18000ae2a  cvttsd2si eax, xmm1
0x18000ae2e  movaps  xmm1, xmm2
0x18000ae31  mulsd   xmm1, cs:__real@4034000000000000
0x18000ae39  mov     [rsp+8F0h+var_88C], eax
0x18000ae3d  cvttsd2si eax, xmm0
0x18000ae41  cvttsd2si r15d, xmm1
0x18000ae46  mov     [rsp+8F0h+rc.left], eax
0x18000ae4a  movaps  xmm0, xmm2
0x18000ae4d  movaps  xmm1, xmm2
0x18000ae50  mulsd   xmm0, cs:__real@4074500000000000
0x18000ae58  mov     [rsp+8F0h+rc.top], r15d
0x18000ae5d  mulsd   xmm1, cs:__real@404b800000000000
0x18000ae65  mulsd   xmm2, cs:__real@402e000000000000
0x18000ae6d  cvttsd2si eax, xmm0
0x18000ae71  cvttsd2si r13d, xmm2
0x18000ae76  mov     [rsp+8F0h+rc.right], eax
0x18000ae7a  cvttsd2si eax, xmm1
0x18000ae7e  mov     [rsp+8F0h+rc.bottom], eax
0x18000ae82  call    cs:__imp_LoadStringW
0x18000ae88  mov     rcx, cs:hModule; hInstance
0x18000ae8f  mov     edx, 4650h; lpIconName
0x18000ae94  call    cs:__imp_LoadIconW
0x18000ae9a  mov     rcx, [rbx+8]; hWnd
0x18000ae9e  lea     rdx, [rbp+7F0h+Paint]; lpPaint
0x18000aea2  mov     [rsp+8F0h+hIcon], rax
0x18000aea7  call    cs:__imp_BeginPaint
0x18000aead  mov     rdi, rax
0x18000aeb0  test    rax, rax
0x18000aeb3  jz      loc_18000B025
0x18000aeb9  mov     rcx, [rbx+4F0h]; hTheme
0x18000aec0  test    rcx, rcx
0x18000aec3  jnz     loc_18000AFBD
0x18000aec9  mov     ecx, 5; nIndex
0x18000aece  call    cs:__imp_GetSysColor
0x18000aed4  mov     ecx, eax; color
0x18000aed6  call    cs:__imp_CreateSolidBrush
0x18000aedc  mov     rdx, rax; h
0x18000aedf  mov     rcx, rdi; hdc
0x18000aee2  mov     r14, rax
0x18000aee5  call    cs:__imp_SelectObject
0x18000aeeb  mov     ecx, 8; i
0x18000aef0  mov     r12, rax
0x18000aef3  call    cs:__imp_GetStockObject
0x18000aef9  mov     rdx, rax; h
0x18000aefc  mov     rcx, rdi; hdc
0x18000aeff  call    cs:__imp_SelectObject
0x18000af05  mov     edx, [rsp+8F0h+var_88C]
0x18000af09  mov     rcx, rdi; hdc
0x18000af0c  mov     r9d, [rsp+8F0h+right]; right
0x18000af11  mov     r8d, [rsp+8F0h+top]; top
0x18000af16  mov     [rsp+8F0h+bottom], edx; bottom
0x18000af1a  mov     edx, [rsp+8F0h+left]; left
0x18000af1e  call    cs:__imp_Rectangle
0x18000af24  mov     edx, 1; mode
0x18000af29  mov     rcx, rdi; hdc
0x18000af2c  call    cs:__imp_SetBkMode
0x18000af32  mov     ecx, 8; nIndex
0x18000af37  call    cs:__imp_GetSysColor
0x18000af3d  mov     edx, eax; color
0x18000af3f  mov     rcx, rdi; hdc
0x18000af42  call    cs:__imp_SetTextColor
0x18000af48  mov     rcx, [rbx+8]; hDlg
0x18000af4c  mov     edx, 3F0h; nIDDlgItem
0x18000af51  call    cs:__imp_GetDlgItem
0x18000af57  xor     r9d, r9d; lParam
0x18000af5a  xor     r8d, r8d; wParam
0x18000af5d  mov     rcx, rax; hWnd
0x18000af60  lea     edx, [r9+31h]; Msg
0x18000af64  call    cs:__imp_SendMessageW
0x18000af6a  mov     rdx, rax; h
0x18000af6d  mov     rcx, rdi; hdc
0x18000af70  call    cs:__imp_SelectObject
0x18000af76  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000af7a  lea     rdx, [rbp+7F0h+Buffer]
0x18000af7e  xor     ecx, ecx
0x18000af80  inc     rax
0x18000af83  cmp     [rdx+rax*2], cx
0x18000af87  jnz     short loc_18000AF80
0x18000af89  mov     r8d, eax; cchText
0x18000af8c  mov     [rsp+8F0h+bottom], 10h; format
0x18000af94  lea     r9, [rsp+8F0h+rc]; lprc
0x18000af99  mov     rcx, rdi; hdc
0x18000af9c  lea     rdx, [rbp+7F0h+Buffer]; lpchText
0x18000afa0  call    cs:__imp_DrawTextW
0x18000afa6  mov     rdx, r12; h
0x18000afa9  mov     rcx, rdi; hdc
0x18000afac  call    cs:__imp_SelectObject
0x18000afb2  mov     rcx, r14; ho
0x18000afb5  call    cs:__imp_DeleteObject
0x18000afbb  jmp     short loc_18000B025
0x18000afbd  mov     r12d, 0Bh
0x18000afc3  mov     [rsp+8F0h+pClipRect], r14; pClipRect
0x18000afc8  lea     rax, [rsp+8F0h+left]
0x18000afcd  mov     r9d, r12d; iStateId
0x18000afd0  mov     rdx, rdi; hdc
0x18000afd3  mov     qword ptr [rsp+8F0h+bottom], rax; pRect
0x18000afd8  lea     r14d, [r12-5]
0x18000afdd  mov     r8d, r14d; iPartId
0x18000afe0  call    cs:__imp_DrawThemeBackground
0x18000afe6  xor     ecx, ecx
0x18000afe8  lea     rax, [rsp+8F0h+rc]
0x18000afed  mov     [rsp+8F0h+pRect], rax; pRect
0x18000aff2  mov     r9d, r12d; iStateId
0x18000aff5  mov     [rsp+8F0h+dwTextFlags2], ecx; dwTextFlags2
0x18000aff9  lea     rax, [rbp+7F0h+Buffer]
0x18000affd  mov     rcx, [rbx+4F0h]; hTheme
0x18000b004  mov     r8d, r14d; iPartId
0x18000b007  mov     [rsp+8F0h+dwTextFlags], 10h; dwTextFlags
0x18000b00f  mov     rdx, rdi; hdc
0x18000b012  mov     dword ptr [rsp+8F0h+pClipRect], 0FFFFFFFFh; cchText
0x18000b01a  mov     qword ptr [rsp+8F0h+bottom], rax; pszText
0x18000b01f  call    cs:__imp_DrawThemeText
0x18000b025  mov     r9, [rsp+8F0h+hIcon]; hIcon
0x18000b02a  mov     r8d, r15d; Y
0x18000b02d  mov     edx, r13d; X
0x18000b030  mov     rcx, rdi; hDC
0x18000b033  call    cs:__imp_DrawIcon
0x18000b039  mov     rcx, [rbx+8]; hWnd
0x18000b03d  lea     rdx, [rbp+7F0h+Paint]; lpPaint
0x18000b041  call    cs:__imp_EndPaint
0x18000b047  xor     eax, eax
0x18000b049  mov     dword ptr [rsi], 1
0x18000b04f  mov     rcx, [rbp+7F0h+var_50]
0x18000b056  xor     rcx, rsp; StackCookie
0x18000b059  call    __security_check_cookie
0x18000b05e  add     rsp, 8B8h
0x18000b065  pop     r15
0x18000b067  pop     r14
0x18000b069  pop     r13
0x18000b06b  pop     r12
0x18000b06d  pop     rdi
0x18000b06e  pop     rsi
0x18000b06f  pop     rbx
0x18000b070  pop     rbp
0x18000b071  retn
```
