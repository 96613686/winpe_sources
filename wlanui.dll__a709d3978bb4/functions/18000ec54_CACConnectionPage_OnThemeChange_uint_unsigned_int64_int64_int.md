# CACConnectionPage::OnThemeChange(uint,unsigned __int64,__int64,int &)

- ea: `0x18000ec54`
- end: `0x18000ed74`
- name: `?OnThemeChange@CACConnectionPage@@QEAA_JI_K_JAEAH@Z`
- size: `288`
- prototype: `__int64 __fastcall(CACConnectionPage *__hidden this, unsigned int, unsigned __int64, __int64, int *)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x18000e31c`
- `0x18000ed80`

## callees

- `0x18000ec54`
- `0x18001bf40`

## import_xrefs

- `USER32!PostMessageW` at `0x18000ed4e`
- `USER32!PostMessageW` at `0x18000ed4e`
- `USER32!InvalidateRect` at `0x18000ed3a`
- `USER32!InvalidateRect` at `0x18000ed3a`
- `UxTheme!IsThemePartDefined` at `0x18000ecb8`
- `UxTheme!IsThemePartDefined` at `0x18000ecb8`
- `UxTheme!OpenThemeData` at `0x18000ec9a`
- `UxTheme!OpenThemeData` at `0x18000ec9a`
- `UxTheme!CloseThemeData` at `0x18000ec89`
- `UxTheme!CloseThemeData` at `0x18000ecc9`
- `UxTheme!CloseThemeData` at `0x18000ec89`
- `UxTheme!CloseThemeData` at `0x18000ecc9`

## pseudocode

```c
__int64 __fastcall CACConnectionPage::OnThemeChange(
        CACConnectionPage *this,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        int *a5)
{
  void *v6; // rcx
  HTHEME v7; // rax
  HWND v8; // rcx
  double v9; // xmm1_8
  double v10; // xmm0_8
  __int64 result; // rax
  RECT Rect; // [rsp+20h] [rbp-28h] BYREF

  v6 = (void *)*((_QWORD *)this + 98);
  Rect = 0;
  if ( v6 )
    CloseThemeData(v6);
  v7 = OpenThemeData(*((HWND *)this + 1), L"LISTVIEW");
  *((_QWORD *)this + 98) = v7;
  if ( v7 && !IsThemePartDefined(v7, 6, 11) )
  {
    CloseThemeData(*((HTHEME *)this + 98));
    *((_QWORD *)this + 98) = 0;
  }
  v8 = (HWND)*((_QWORD *)this + 1);
  v9 = *((double *)this + 103) * 10.0;
  v10 = *((double *)this + 103);
  Rect.left = (int)(v10 * 5.0);
  Rect.top = (int)v9;
  Rect.right = (int)(v10 * 335.0);
  Rect.bottom = (int)(v10 * 62.0);
  InvalidateRect(v8, &Rect, 1);
  PostMessageW(*((HWND *)this + 1), 0xFu, 0, 0);
  result = 0;
  *a5 = 1;
  return result;
}

```

## disassembly

```asm
0x18000ec54  mov     [rsp+arg_8], rbx
0x18000ec59  push    rdi
0x18000ec5a  sub     rsp, 40h
0x18000ec5e  mov     rax, cs:__security_cookie
0x18000ec65  xor     rax, rsp
0x18000ec68  mov     [rsp+48h+var_18], rax
0x18000ec6d  mov     rdi, [rsp+48h+arg_20]
0x18000ec72  mov     rbx, rcx
0x18000ec75  mov     rcx, [rcx+310h]; hTheme
0x18000ec7c  xorps   xmm0, xmm0
0x18000ec7f  movups  xmmword ptr [rsp+48h+Rect.left], xmm0
0x18000ec84  test    rcx, rcx
0x18000ec87  jz      short loc_18000EC8F
0x18000ec89  call    cs:__imp_CloseThemeData
0x18000ec8f  mov     rcx, [rbx+8]; hwnd
0x18000ec93  lea     rdx, pszClassList; "LISTVIEW"
0x18000ec9a  call    cs:__imp_OpenThemeData
0x18000eca0  mov     [rbx+310h], rax
0x18000eca7  test    rax, rax
0x18000ecaa  jz      short loc_18000ECDA
0x18000ecac  mov     edx, 6; iPartId
0x18000ecb1  mov     rcx, rax; hTheme
0x18000ecb4  lea     r8d, [rdx+5]; iStateId
0x18000ecb8  call    cs:__imp_IsThemePartDefined
0x18000ecbe  test    eax, eax
0x18000ecc0  jnz     short loc_18000ECDA
0x18000ecc2  mov     rcx, [rbx+310h]; hTheme
0x18000ecc9  call    cs:__imp_CloseThemeData
0x18000eccf  mov     qword ptr [rbx+310h], 0
0x18000ecda  movsd   xmm2, qword ptr [rbx+338h]
0x18000ece2  lea     rdx, [rsp+48h+Rect]; lpRect
0x18000ece7  mov     rcx, [rbx+8]; hWnd
0x18000eceb  movaps  xmm0, xmm2
0x18000ecee  mulsd   xmm0, cs:__real@4014000000000000
0x18000ecf6  movaps  xmm1, xmm2
0x18000ecf9  mov     r8d, 1; bErase
0x18000ecff  mulsd   xmm1, cs:__real@4024000000000000
0x18000ed07  cvttsd2si eax, xmm0
0x18000ed0b  movaps  xmm0, xmm2
0x18000ed0e  mulsd   xmm2, cs:__real@404f000000000000
0x18000ed16  mov     [rsp+48h+Rect.left], eax
0x18000ed1a  mulsd   xmm0, cs:__real@4074f00000000000
0x18000ed22  cvttsd2si eax, xmm1
0x18000ed26  mov     [rsp+48h+Rect.top], eax
0x18000ed2a  cvttsd2si eax, xmm0
0x18000ed2e  mov     [rsp+48h+Rect.right], eax
0x18000ed32  cvttsd2si eax, xmm2
0x18000ed36  mov     [rsp+48h+Rect.bottom], eax
0x18000ed3a  call    cs:__imp_InvalidateRect
0x18000ed40  mov     rcx, [rbx+8]; hWnd
0x18000ed44  xor     r9d, r9d; lParam
0x18000ed47  xor     r8d, r8d; wParam
0x18000ed4a  lea     edx, [r9+0Fh]; Msg
0x18000ed4e  call    cs:__imp_PostMessageW
0x18000ed54  xor     eax, eax
0x18000ed56  mov     dword ptr [rdi], 1
0x18000ed5c  mov     rcx, [rsp+48h+var_18]
0x18000ed61  xor     rcx, rsp; StackCookie
0x18000ed64  call    __security_check_cookie
0x18000ed69  mov     rbx, [rsp+48h+arg_8]
0x18000ed6e  add     rsp, 40h
0x18000ed72  pop     rdi
0x18000ed73  retn
```
