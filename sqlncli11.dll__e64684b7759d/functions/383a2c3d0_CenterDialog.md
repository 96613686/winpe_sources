# CenterDialog

- ea: `0x383a2c3d0`
- end: `0x383a2c502`
- name: `CenterDialog`
- size: `306`
- prototype: `__int64 __fastcall(HWND hWnd)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x383a29590`

## callees

- `0x3838434c0`
- `0x383a2c3d0`

## import_xrefs

- `USER32!GetWindowRect` at `0x383a2c417`
- `USER32!GetWindowRect` at `0x383a2c449`
- `USER32!GetWindowRect` at `0x383a2c417`
- `USER32!GetWindowRect` at `0x383a2c449`
- `USER32!MoveWindow` at `0x383a2c4da`
- `USER32!MoveWindow` at `0x383a2c4da`
- `USER32!GetParent` at `0x383a2c3f4`
- `USER32!GetParent` at `0x383a2c3f4`
- `USER32!IsWindowVisible` at `0x383a2c405`
- `USER32!IsWindowVisible` at `0x383a2c405`
- `USER32!GetSystemMetrics` at `0x383a2c428`
- `USER32!GetSystemMetrics` at `0x383a2c437`
- `USER32!GetSystemMetrics` at `0x383a2c48f`
- `USER32!GetSystemMetrics` at `0x383a2c4b0`
- `USER32!GetSystemMetrics` at `0x383a2c428`
- `USER32!GetSystemMetrics` at `0x383a2c437`
- `USER32!GetSystemMetrics` at `0x383a2c48f`
- `USER32!GetSystemMetrics` at `0x383a2c4b0`

## pseudocode

```c
BOOL __fastcall CenterDialog(HWND hWnd)
{
  HWND Parent; // rax
  HWND v3; // rbx
  int v4; // ebp
  int nHeight; // r14d
  int v6; // edi
  int v7; // ebx
  int v8; // ecx
  int v9; // edx
  struct tagRECT Rect; // [rsp+30h] [rbp-48h] BYREF
  struct tagRECT v12; // [rsp+40h] [rbp-38h] BYREF

  Parent = GetParent(hWnd);
  v3 = Parent;
  if ( Parent && IsWindowVisible(Parent) )
  {
    GetWindowRect(v3, &Rect);
  }
  else
  {
    *(_QWORD *)&Rect.left = 0;
    Rect.right = GetSystemMetrics(0);
    Rect.bottom = GetSystemMetrics(1);
  }
  GetWindowRect(hWnd, &v12);
  v4 = v12.right - v12.left;
  nHeight = v12.bottom - v12.top;
  v6 = ((Rect.left + Rect.right) >> 1) - ((v12.right - v12.left) >> 1);
  v7 = ((Rect.top + Rect.bottom) >> 1) - ((v12.bottom - v12.top) >> 1);
  if ( v6 > 0 )
  {
    v8 = v6 + v4 - GetSystemMetrics(0);
    if ( v8 > 0 )
      v6 -= v8;
  }
  else
  {
    v6 = 1;
  }
  if ( v7 > 0 )
  {
    v9 = v7 + nHeight - GetSystemMetrics(1);
    if ( v9 > 0 )
      v7 -= v9;
  }
  else
  {
    v7 = 1;
  }
  return MoveWindow(hWnd, v6, v7, v4, nHeight, 1);
}

```

## disassembly

```asm
0x383a2c3d0  mov     [rsp+arg_8], rbx
0x383a2c3d5  mov     [rsp+arg_10], rbp
0x383a2c3da  push    rsi
0x383a2c3db  push    rdi
0x383a2c3dc  push    r14
0x383a2c3de  sub     rsp, 60h
0x383a2c3e2  mov     rax, cs:__security_cookie
0x383a2c3e9  xor     rax, rsp
0x383a2c3ec  mov     [rsp+78h+var_28], rax
0x383a2c3f1  mov     rsi, rcx
0x383a2c3f4  call    cs:__imp_GetParent
0x383a2c3fa  mov     rbx, rax
0x383a2c3fd  test    rax, rax
0x383a2c400  jz      short loc_383A2C41F
0x383a2c402  mov     rcx, rax; hWnd
0x383a2c405  call    cs:__imp_IsWindowVisible
0x383a2c40b  test    eax, eax
0x383a2c40d  jz      short loc_383A2C41F
0x383a2c40f  lea     rdx, [rsp+78h+Rect]; lpRect
0x383a2c414  mov     rcx, rbx; hWnd
0x383a2c417  call    cs:__imp_GetWindowRect
0x383a2c41d  jmp     short loc_383A2C441
0x383a2c41f  xor     eax, eax
0x383a2c421  xor     ecx, ecx; nIndex
0x383a2c423  mov     qword ptr [rsp+78h+Rect.left], rax
0x383a2c428  call    cs:__imp_GetSystemMetrics
0x383a2c42e  mov     ecx, 1; nIndex
0x383a2c433  mov     [rsp+78h+Rect.right], eax
0x383a2c437  call    cs:__imp_GetSystemMetrics
0x383a2c43d  mov     [rsp+78h+Rect.bottom], eax
0x383a2c441  lea     rdx, [rsp+78h+var_38]; lpRect
0x383a2c446  mov     rcx, rsi; hWnd
0x383a2c449  call    cs:__imp_GetWindowRect
0x383a2c44f  mov     ebp, [rsp+78h+var_38.right]
0x383a2c453  mov     edi, [rsp+78h+Rect.right]
0x383a2c457  add     edi, [rsp+78h+Rect.left]
0x383a2c45b  sub     ebp, [rsp+78h+var_38.left]
0x383a2c45f  mov     r14d, [rsp+78h+var_38.bottom]
0x383a2c464  sub     r14d, [rsp+78h+var_38.top]
0x383a2c469  mov     ebx, [rsp+78h+Rect.bottom]
0x383a2c46d  sar     edi, 1
0x383a2c46f  add     ebx, [rsp+78h+Rect.top]
0x383a2c473  mov     eax, ebp
0x383a2c475  sar     eax, 1
0x383a2c477  sar     ebx, 1
0x383a2c479  sub     edi, eax
0x383a2c47b  mov     eax, r14d
0x383a2c47e  sar     eax, 1
0x383a2c480  sub     ebx, eax
0x383a2c482  test    edi, edi
0x383a2c484  jg      short loc_383A2C48D
0x383a2c486  mov     edi, 1
0x383a2c48b  jmp     short loc_383A2C4A0
0x383a2c48d  xor     ecx, ecx; nIndex
0x383a2c48f  call    cs:__imp_GetSystemMetrics
0x383a2c495  lea     ecx, [rdi+rbp]
0x383a2c498  sub     ecx, eax
0x383a2c49a  test    ecx, ecx
0x383a2c49c  jle     short loc_383A2C4A0
0x383a2c49e  sub     edi, ecx
0x383a2c4a0  test    ebx, ebx
0x383a2c4a2  jg      short loc_383A2C4AB
0x383a2c4a4  mov     ebx, 1
0x383a2c4a9  jmp     short loc_383A2C4C2
0x383a2c4ab  mov     ecx, 1; nIndex
0x383a2c4b0  call    cs:__imp_GetSystemMetrics
0x383a2c4b6  lea     edx, [rbx+r14]
0x383a2c4ba  sub     edx, eax
0x383a2c4bc  test    edx, edx
0x383a2c4be  jle     short loc_383A2C4C2
0x383a2c4c0  sub     ebx, edx
0x383a2c4c2  mov     r9d, ebp; nWidth
0x383a2c4c5  mov     r8d, ebx; Y
0x383a2c4c8  mov     edx, edi; X
0x383a2c4ca  mov     rcx, rsi; hWnd
0x383a2c4cd  mov     [rsp+78h+bRepaint], 1; bRepaint
0x383a2c4d5  mov     [rsp+78h+nHeight], r14d; nHeight
0x383a2c4da  call    cs:__imp_MoveWindow
0x383a2c4e0  mov     rcx, [rsp+78h+var_28]
0x383a2c4e5  xor     rcx, rsp; StackCookie
0x383a2c4e8  call    __security_check_cookie
0x383a2c4ed  lea     r11, [rsp+78h+var_18]
0x383a2c4f2  mov     rbx, [r11+28h]
0x383a2c4f6  mov     rbp, [r11+30h]
0x383a2c4fa  mov     rsp, r11
0x383a2c4fd  pop     r14
0x383a2c4ff  pop     rdi
0x383a2c500  pop     rsi
0x383a2c501  retn
```
