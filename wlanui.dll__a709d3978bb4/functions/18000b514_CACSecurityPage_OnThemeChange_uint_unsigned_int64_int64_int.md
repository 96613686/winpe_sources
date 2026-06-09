# CACSecurityPage::OnThemeChange(uint,unsigned __int64,__int64,int &)

- ea: `0x18000b514`
- end: `0x18000b634`
- name: `?OnThemeChange@CACSecurityPage@@QEAA_JI_K_JAEAH@Z`
- size: `288`
- prototype: `__int64 __fastcall(CACSecurityPage *__hidden this, unsigned int, unsigned __int64, __int64, int *)`
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18000a7f8`
- `0x18000c290`

## callees

- `0x18000b514`
- `0x18001bf40`

## import_xrefs

- `USER32!PostMessageW` at `0x18000b60e`
- `USER32!PostMessageW` at `0x18000b60e`
- `USER32!InvalidateRect` at `0x18000b5fa`
- `USER32!InvalidateRect` at `0x18000b5fa`
- `UxTheme!IsThemePartDefined` at `0x18000b578`
- `UxTheme!IsThemePartDefined` at `0x18000b578`
- `UxTheme!OpenThemeData` at `0x18000b55a`
- `UxTheme!OpenThemeData` at `0x18000b55a`
- `UxTheme!CloseThemeData` at `0x18000b549`
- `UxTheme!CloseThemeData` at `0x18000b589`
- `UxTheme!CloseThemeData` at `0x18000b549`
- `UxTheme!CloseThemeData` at `0x18000b589`

## pseudocode

```c
__int64 __fastcall CACSecurityPage::OnThemeChange(CACSecurityPage *this, __int64 a2, __int64 a3, __int64 a4, int *a5)
{
  void *v6; // rcx
  HTHEME v7; // rax
  HWND v8; // rcx
  double v9; // xmm1_8
  double v10; // xmm0_8
  __int64 result; // rax
  RECT Rect; // [rsp+20h] [rbp-28h] BYREF

  v6 = (void *)*((_QWORD *)this + 158);
  Rect = 0;
  if ( v6 )
    CloseThemeData(v6);
  v7 = OpenThemeData(*((HWND *)this + 1), L"LISTVIEW");
  *((_QWORD *)this + 158) = v7;
  if ( v7 && !IsThemePartDefined(v7, 6, 11) )
  {
    CloseThemeData(*((HTHEME *)this + 158));
    *((_QWORD *)this + 158) = 0;
  }
  v8 = (HWND)*((_QWORD *)this + 1);
  v9 = *((double *)this + 163) * 10.0;
  v10 = *((double *)this + 163);
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
0x18000b514  mov     [rsp+arg_8], rbx
0x18000b519  push    rdi
0x18000b51a  sub     rsp, 40h
0x18000b51e  mov     rax, cs:__security_cookie
0x18000b525  xor     rax, rsp
0x18000b528  mov     [rsp+48h+var_18], rax
0x18000b52d  mov     rdi, [rsp+48h+arg_20]
0x18000b532  mov     rbx, rcx
0x18000b535  mov     rcx, [rcx+4F0h]; hTheme
0x18000b53c  xorps   xmm0, xmm0
0x18000b53f  movups  xmmword ptr [rsp+48h+Rect.left], xmm0
0x18000b544  test    rcx, rcx
0x18000b547  jz      short loc_18000B54F
0x18000b549  call    cs:__imp_CloseThemeData
0x18000b54f  mov     rcx, [rbx+8]; hwnd
0x18000b553  lea     rdx, pszClassList; "LISTVIEW"
0x18000b55a  call    cs:__imp_OpenThemeData
0x18000b560  mov     [rbx+4F0h], rax
0x18000b567  test    rax, rax
0x18000b56a  jz      short loc_18000B59A
0x18000b56c  mov     edx, 6; iPartId
0x18000b571  mov     rcx, rax; hTheme
0x18000b574  lea     r8d, [rdx+5]; iStateId
0x18000b578  call    cs:__imp_IsThemePartDefined
0x18000b57e  test    eax, eax
0x18000b580  jnz     short loc_18000B59A
0x18000b582  mov     rcx, [rbx+4F0h]; hTheme
0x18000b589  call    cs:__imp_CloseThemeData
0x18000b58f  mov     qword ptr [rbx+4F0h], 0
0x18000b59a  movsd   xmm2, qword ptr [rbx+518h]
0x18000b5a2  lea     rdx, [rsp+48h+Rect]; lpRect
0x18000b5a7  mov     rcx, [rbx+8]; hWnd
0x18000b5ab  movaps  xmm0, xmm2
0x18000b5ae  mulsd   xmm0, cs:__real@4014000000000000
0x18000b5b6  movaps  xmm1, xmm2
0x18000b5b9  mov     r8d, 1; bErase
0x18000b5bf  mulsd   xmm1, cs:__real@4024000000000000
0x18000b5c7  cvttsd2si eax, xmm0
0x18000b5cb  movaps  xmm0, xmm2
0x18000b5ce  mulsd   xmm2, cs:__real@404f000000000000
0x18000b5d6  mov     [rsp+48h+Rect.left], eax
0x18000b5da  mulsd   xmm0, cs:__real@4074f00000000000
0x18000b5e2  cvttsd2si eax, xmm1
0x18000b5e6  mov     [rsp+48h+Rect.top], eax
0x18000b5ea  cvttsd2si eax, xmm0
0x18000b5ee  mov     [rsp+48h+Rect.right], eax
0x18000b5f2  cvttsd2si eax, xmm2
0x18000b5f6  mov     [rsp+48h+Rect.bottom], eax
0x18000b5fa  call    cs:__imp_InvalidateRect
0x18000b600  mov     rcx, [rbx+8]; hWnd
0x18000b604  xor     r9d, r9d; lParam
0x18000b607  xor     r8d, r8d; wParam
0x18000b60a  lea     edx, [r9+0Fh]; Msg
0x18000b60e  call    cs:__imp_PostMessageW
0x18000b614  xor     eax, eax
0x18000b616  mov     dword ptr [rdi], 1
0x18000b61c  mov     rcx, [rsp+48h+var_18]
0x18000b621  xor     rcx, rsp; StackCookie
0x18000b624  call    __security_check_cookie
0x18000b629  mov     rbx, [rsp+48h+arg_8]
0x18000b62e  add     rsp, 40h
0x18000b632  pop     rdi
0x18000b633  retn
```
