# CAnalogClock::_GetBkGroundColor(void)

- ea: `0x180024390`
- end: `0x1800244c4`
- name: `?_GetBkGroundColor@CAnalogClock@@AEAAXXZ`
- size: `308`
- prototype: `void __fastcall(CAnalogClock *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180023f3c`

## callees

- `0x1800024e0`
- `0x180024390`
- `0x180028f60`

## import_xrefs

- `USER32!GetWindowInfo` at `0x1800243d3`
- `USER32!GetWindowInfo` at `0x1800243d3`
- `USER32!GetSysColor` at `0x18002445b`
- `USER32!GetSysColor` at `0x18002445b`
- `USER32!ReleaseDC` at `0x18002444e`
- `USER32!ReleaseDC` at `0x18002444e`
- `USER32!GetDC` at `0x180024433`
- `USER32!GetDC` at `0x180024433`
- `UxTheme!CloseThemeData` at `0x180024412`
- `UxTheme!CloseThemeData` at `0x180024412`
- `UxTheme!OpenThemeData` at `0x1800243ff`
- `UxTheme!OpenThemeData` at `0x1800243ff`
- `GDI32!GetDCBrushColor` at `0x18002443f`
- `GDI32!GetDCBrushColor` at `0x18002443f`

## pseudocode

```c
void __fastcall CAnalogClock::_GetBkGroundColor(CAnalogClock *this)
{
  HWND v2; // rcx
  int v3; // ebp
  int v4; // edi
  int v5; // ebx
  HTHEME v6; // rax
  int v7; // ecx
  HDC DC; // rbx
  COLORREF DCBrushColor; // edi
  COLORREF *v10; // r8
  tagWINDOWINFO pwi; // [rsp+20h] [rbp-78h] BYREF

  v2 = (HWND)*((_QWORD *)this + 1);
  memset(&pwi, 0, sizeof(pwi));
  pwi.cbSize = 60;
  if ( !GetWindowInfo(v2, &pwi) )
    return;
  v3 = pwi.dwStyle & 0x400;
  v4 = pwi.dwStyle & 0x80;
  v5 = 0;
  v6 = OpenThemeData(*(HWND *)this, L"Flyout");
  if ( v6 )
  {
    v5 = 1;
    CloseThemeData(v6);
  }
  if ( !v3 )
  {
    if ( v4 )
      goto LABEL_6;
    if ( !v5 )
    {
      v7 = 5;
      goto LABEL_11;
    }
LABEL_9:
    DC = GetDC(*((HWND *)this + 1));
    DCBrushColor = GetDCBrushColor(DC);
    ReleaseDC(*((HWND *)this + 1), DC);
    goto LABEL_12;
  }
  if ( v5 )
    goto LABEL_9;
LABEL_6:
  v7 = 15;
LABEL_11:
  DCBrushColor = GetSysColor(v7);
LABEL_12:
  if ( DCBrushColor - 1 <= 0xFFFFFFFD )
  {
    v10 = (COLORREF *)operator new(4u, (const struct std::nothrow_t *)&std::nothrow);
    if ( v10 )
      *v10 = BYTE2(DCBrushColor) | DCBrushColor & 0xFF00 | ((DCBrushColor | 0xFFFFFF00) << 16);
    else
      v10 = 0;
    *((_QWORD *)this + 8) = v10;
  }
}

```

## disassembly

```asm
0x180024390  push    rbx
0x180024392  push    rbp
0x180024393  push    rsi
0x180024394  push    rdi
0x180024395  sub     rsp, 78h
0x180024399  mov     rax, cs:__security_cookie
0x1800243a0  xor     rax, rsp
0x1800243a3  mov     [rsp+98h+var_38], rax
0x1800243a8  xorps   xmm0, xmm0
0x1800243ab  lea     rdx, [rsp+98h+pwi]; pwi
0x1800243b0  mov     rsi, rcx
0x1800243b3  mov     rcx, [rcx+8]; hwnd
0x1800243b7  movups  xmmword ptr [rsp+98h+pwi.cbSize], xmm0
0x1800243bc  mov     [rsp+98h+pwi.cbSize], 3Ch ; '<'
0x1800243c4  movups  xmmword ptr [rsp+98h+pwi.rcClient.bottom], xmm0
0x1800243c9  movups  xmmword ptr [rsp+98h+pwi.dwWindowStatus], xmm0
0x1800243ce  movups  xmmword ptr [rsp+98h+pwi.rcWindow.bottom], xmm0
0x1800243d3  call    cs:__imp_GetWindowInfo
0x1800243d9  test    eax, eax
0x1800243db  jz      loc_1800244AE
0x1800243e1  mov     edi, [rsp+98h+pwi.dwStyle]
0x1800243e5  lea     rdx, aFlyout; "Flyout"
0x1800243ec  mov     rcx, [rsi]; hwnd
0x1800243ef  mov     ebp, edi
0x1800243f1  and     ebp, 400h
0x1800243f7  and     edi, 80h
0x1800243fd  xor     ebx, ebx
0x1800243ff  call    cs:__imp_OpenThemeData
0x180024405  test    rax, rax
0x180024408  jz      short loc_180024418
0x18002440a  mov     rcx, rax; hTheme
0x18002440d  mov     ebx, 1
0x180024412  call    cs:__imp_CloseThemeData
0x180024418  test    ebp, ebp
0x18002441a  jz      short loc_180024427
0x18002441c  test    ebx, ebx
0x18002441e  jnz     short loc_18002442F
0x180024420  mov     ecx, 0Fh
0x180024425  jmp     short loc_18002445B
0x180024427  test    edi, edi
0x180024429  jnz     short loc_180024420
0x18002442b  test    ebx, ebx
0x18002442d  jz      short loc_180024456
0x18002442f  mov     rcx, [rsi+8]; hWnd
0x180024433  call    cs:__imp_GetDC
0x180024439  mov     rcx, rax; hdc
0x18002443c  mov     rbx, rax
0x18002443f  call    cs:__imp_GetDCBrushColor
0x180024445  mov     rcx, [rsi+8]; hWnd
0x180024449  mov     rdx, rbx; hDC
0x18002444c  mov     edi, eax
0x18002444e  call    cs:__imp_ReleaseDC
0x180024454  jmp     short loc_180024463
0x180024456  mov     ecx, 5; nIndex
0x18002445b  call    cs:__imp_GetSysColor
0x180024461  mov     edi, eax
0x180024463  lea     eax, [rdi-1]
0x180024466  cmp     eax, 0FFFFFFFDh
0x180024469  ja      short loc_1800244AE
0x18002446b  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180024472  mov     ecx, 4; unsigned __int64
0x180024477  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18002447c  mov     r8, rax
0x18002447f  test    rax, rax
0x180024482  jz      short loc_1800244A7
0x180024484  mov     eax, 0FFFFFF00h
0x180024489  movzx   edx, dil
0x18002448d  or      edx, eax
0x18002448f  movzx   ecx, di
0x180024492  and     ecx, eax
0x180024494  shl     edx, 10h
0x180024497  shr     edi, 10h
0x18002449a  or      edx, ecx
0x18002449c  movzx   eax, dil
0x1800244a0  or      edx, eax
0x1800244a2  mov     [r8], edx
0x1800244a5  jmp     short loc_1800244AA
0x1800244a7  xor     r8d, r8d
0x1800244aa  mov     [rsi+40h], r8
0x1800244ae  mov     rcx, [rsp+98h+var_38]
0x1800244b3  xor     rcx, rsp; StackCookie
0x1800244b6  call    __security_check_cookie
0x1800244bb  add     rsp, 78h
0x1800244bf  pop     rdi
0x1800244c0  pop     rsi
0x1800244c1  pop     rbp
0x1800244c2  pop     rbx
0x1800244c3  retn
```
