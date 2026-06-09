# CenterDialog(HWND__ *)

- ea: `0x383920790`
- end: `0x3839208c2`
- name: `?CenterDialog@@YAXPEAUHWND__@@@Z`
- size: `306`
- prototype: `void __fastcall(HWND hWnd)`
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x38391d3b0`
- `0x38391e4d0`
- `0x383923d40`
- `0x3839244b0`

## callees

- `0x3838434c0`
- `0x383920790`

## import_xrefs

- `USER32!GetWindowRect` at `0x3839207d7`
- `USER32!GetWindowRect` at `0x383920809`
- `USER32!GetWindowRect` at `0x3839207d7`
- `USER32!GetWindowRect` at `0x383920809`
- `USER32!MoveWindow` at `0x38392089a`
- `USER32!MoveWindow` at `0x38392089a`
- `USER32!GetParent` at `0x3839207b4`
- `USER32!GetParent` at `0x3839207b4`
- `USER32!IsWindowVisible` at `0x3839207c5`
- `USER32!IsWindowVisible` at `0x3839207c5`
- `USER32!GetSystemMetrics` at `0x3839207e8`
- `USER32!GetSystemMetrics` at `0x3839207f7`
- `USER32!GetSystemMetrics` at `0x38392084f`
- `USER32!GetSystemMetrics` at `0x383920870`
- `USER32!GetSystemMetrics` at `0x3839207e8`
- `USER32!GetSystemMetrics` at `0x3839207f7`
- `USER32!GetSystemMetrics` at `0x38392084f`
- `USER32!GetSystemMetrics` at `0x383920870`

## pseudocode

```c
void __fastcall CenterDialog(HWND hWnd)
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
  struct tagRECT v11; // [rsp+40h] [rbp-38h] BYREF

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
  GetWindowRect(hWnd, &v11);
  v4 = v11.right - v11.left;
  nHeight = v11.bottom - v11.top;
  v6 = ((Rect.left + Rect.right) >> 1) - ((v11.right - v11.left) >> 1);
  v7 = ((Rect.top + Rect.bottom) >> 1) - ((v11.bottom - v11.top) >> 1);
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
  MoveWindow(hWnd, v6, v7, v4, nHeight, 1);
}

```

## disassembly

```asm
0x383920790  mov     [rsp+arg_8], rbx
0x383920795  mov     [rsp+arg_10], rbp
0x38392079a  push    rsi
0x38392079b  push    rdi
0x38392079c  push    r14
0x38392079e  sub     rsp, 60h
0x3839207a2  mov     rax, cs:__security_cookie
0x3839207a9  xor     rax, rsp
0x3839207ac  mov     [rsp+78h+var_28], rax
0x3839207b1  mov     rsi, rcx
0x3839207b4  call    cs:__imp_GetParent
0x3839207ba  mov     rbx, rax
0x3839207bd  test    rax, rax
0x3839207c0  jz      short loc_3839207DF
0x3839207c2  mov     rcx, rax; hWnd
0x3839207c5  call    cs:__imp_IsWindowVisible
0x3839207cb  test    eax, eax
0x3839207cd  jz      short loc_3839207DF
0x3839207cf  lea     rdx, [rsp+78h+Rect]; lpRect
0x3839207d4  mov     rcx, rbx; hWnd
0x3839207d7  call    cs:__imp_GetWindowRect
0x3839207dd  jmp     short loc_383920801
0x3839207df  xor     eax, eax
0x3839207e1  xor     ecx, ecx; nIndex
0x3839207e3  mov     qword ptr [rsp+78h+Rect.left], rax
0x3839207e8  call    cs:__imp_GetSystemMetrics
0x3839207ee  mov     ecx, 1; nIndex
0x3839207f3  mov     [rsp+78h+Rect.right], eax
0x3839207f7  call    cs:__imp_GetSystemMetrics
0x3839207fd  mov     [rsp+78h+Rect.bottom], eax
0x383920801  lea     rdx, [rsp+78h+var_38]; lpRect
0x383920806  mov     rcx, rsi; hWnd
0x383920809  call    cs:__imp_GetWindowRect
0x38392080f  mov     ebp, [rsp+78h+var_38.right]
0x383920813  mov     edi, [rsp+78h+Rect.right]
0x383920817  add     edi, [rsp+78h+Rect.left]
0x38392081b  sub     ebp, [rsp+78h+var_38.left]
0x38392081f  mov     r14d, [rsp+78h+var_38.bottom]
0x383920824  sub     r14d, [rsp+78h+var_38.top]
0x383920829  mov     ebx, [rsp+78h+Rect.bottom]
0x38392082d  sar     edi, 1
0x38392082f  add     ebx, [rsp+78h+Rect.top]
0x383920833  mov     eax, ebp
0x383920835  sar     eax, 1
0x383920837  sar     ebx, 1
0x383920839  sub     edi, eax
0x38392083b  mov     eax, r14d
0x38392083e  sar     eax, 1
0x383920840  sub     ebx, eax
0x383920842  test    edi, edi
0x383920844  jg      short loc_38392084D
0x383920846  mov     edi, 1
0x38392084b  jmp     short loc_383920860
0x38392084d  xor     ecx, ecx; nIndex
0x38392084f  call    cs:__imp_GetSystemMetrics
0x383920855  lea     ecx, [rdi+rbp]
0x383920858  sub     ecx, eax
0x38392085a  test    ecx, ecx
0x38392085c  jle     short loc_383920860
0x38392085e  sub     edi, ecx
0x383920860  test    ebx, ebx
0x383920862  jg      short loc_38392086B
0x383920864  mov     ebx, 1
0x383920869  jmp     short loc_383920882
0x38392086b  mov     ecx, 1; nIndex
0x383920870  call    cs:__imp_GetSystemMetrics
0x383920876  lea     edx, [rbx+r14]
0x38392087a  sub     edx, eax
0x38392087c  test    edx, edx
0x38392087e  jle     short loc_383920882
0x383920880  sub     ebx, edx
0x383920882  mov     r9d, ebp; nWidth
0x383920885  mov     r8d, ebx; Y
0x383920888  mov     edx, edi; X
0x38392088a  mov     rcx, rsi; hWnd
0x38392088d  mov     [rsp+78h+bRepaint], 1; bRepaint
0x383920895  mov     [rsp+78h+nHeight], r14d; nHeight
0x38392089a  call    cs:__imp_MoveWindow
0x3839208a0  mov     rcx, [rsp+78h+var_28]
0x3839208a5  xor     rcx, rsp; StackCookie
0x3839208a8  call    __security_check_cookie
0x3839208ad  lea     r11, [rsp+78h+var_18]
0x3839208b2  mov     rbx, [r11+28h]
0x3839208b6  mov     rbp, [r11+30h]
0x3839208ba  mov     rsp, r11
0x3839208bd  pop     r14
0x3839208bf  pop     rdi
0x3839208c0  pop     rsi
0x3839208c1  retn
```
