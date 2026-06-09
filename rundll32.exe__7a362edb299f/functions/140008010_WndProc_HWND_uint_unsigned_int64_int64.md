# WndProc(HWND__ *,uint,unsigned __int64,__int64)

- ea: `0x140008010`
- end: `0x1400081c4`
- name: `?WndProc@@YA_JPEAUHWND__@@I_K_J@Z`
- size: `436`
- prototype: `LRESULT __fastcall(HWND hWnd, UINT Msg, WPARAM wParam, LPARAM lParam)`
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x1400015a0`
- `0x140002254`
- `0x140008010`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x140008101`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x140008101`
- `ext-ms-win-ntuser-windowclass-l1-1-0!GetWindowLongPtrW` at `0x140008087`
- `ext-ms-win-ntuser-windowclass-l1-1-0!GetWindowLongPtrW` at `0x140008136`
- `ext-ms-win-ntuser-windowclass-l1-1-0!GetWindowLongPtrW` at `0x140008087`
- `ext-ms-win-ntuser-windowclass-l1-1-0!GetWindowLongPtrW` at `0x140008136`
- `ext-ms-win-ntuser-windowclass-l1-1-0!SetWindowLongPtrW` at `0x140008078`
- `ext-ms-win-ntuser-windowclass-l1-1-0!SetWindowLongPtrW` at `0x140008179`
- `ext-ms-win-ntuser-windowclass-l1-1-0!SetWindowLongPtrW` at `0x140008078`
- `ext-ms-win-ntuser-windowclass-l1-1-0!SetWindowLongPtrW` at `0x140008179`
- `ext-ms-win-ntuser-windowclass-l1-1-0!GetClassNameW` at `0x1400080d7`
- `ext-ms-win-ntuser-windowclass-l1-1-0!GetClassNameW` at `0x1400080d7`
- `ext-ms-win-ntuser-windowclass-l1-1-2!GetClassLongPtrW` at `0x14000814f`
- `ext-ms-win-ntuser-windowclass-l1-1-2!GetClassLongPtrW` at `0x140008160`
- `ext-ms-win-ntuser-windowclass-l1-1-2!GetClassLongPtrW` at `0x14000814f`
- `ext-ms-win-ntuser-windowclass-l1-1-2!GetClassLongPtrW` at `0x140008160`
- `ext-ms-win-ntuser-windowclass-l1-1-2!SetClassLongPtrW` at `0x140008069`
- `ext-ms-win-ntuser-windowclass-l1-1-2!SetClassLongPtrW` at `0x14000818a`
- `ext-ms-win-ntuser-windowclass-l1-1-2!SetClassLongPtrW` at `0x140008069`
- `ext-ms-win-ntuser-windowclass-l1-1-2!SetClassLongPtrW` at `0x14000818a`
- `ext-ms-win-ntuser-window-l1-1-0!DefWindowProcW` at `0x14000819c`
- `ext-ms-win-ntuser-window-l1-1-0!DefWindowProcW` at `0x14000819c`
- `ext-ms-win-ntuser-window-l1-1-0!GetWindow` at `0x1400080a2`
- `ext-ms-win-ntuser-window-l1-1-0!GetWindow` at `0x140008112`
- `ext-ms-win-ntuser-window-l1-1-0!GetWindow` at `0x140008123`
- `ext-ms-win-ntuser-window-l1-1-0!GetWindow` at `0x1400080a2`
- `ext-ms-win-ntuser-window-l1-1-0!GetWindow` at `0x140008112`
- `ext-ms-win-ntuser-window-l1-1-0!GetWindow` at `0x140008123`

## pseudocode

```c
LRESULT __fastcall WndProc(HWND hWnd, UINT Msg, WPARAM wParam, LPARAM lParam)
{
  LONG_PTR v8; // r8
  HWND Window; // rdi
  LONG_PTR WindowLongPtrW; // r15
  LONG_PTR ClassLongPtrW; // rbx
  WCHAR ClassName; // [rsp+30h] [rbp-E8h] BYREF
  _BYTE v14[158]; // [rsp+32h] [rbp-E6h] BYREF

  if ( Msg == 28 )
  {
    if ( GetWindowLongPtrW(hWnd, 0) )
    {
      Window = GetWindow(hWnd, 3u);
      if ( Window )
      {
        ClassName = 0;
        memset_0(v14, 0, sizeof(v14));
        if ( GetClassNameW(Window, &ClassName, 80) && CompareStringW(0x7Fu, 1u, &ClassName, -1, L"IME", -1) == 2 )
          Window = GetWindow(Window, 3u);
        if ( GetWindow(Window, 4u) == hWnd )
        {
          WindowLongPtrW = GetWindowLongPtrW(Window, -20);
          if ( (WindowLongPtrW & 0x40080) == 0 && !GetClassLongPtrW(Window, -34) )
          {
            ClassLongPtrW = GetClassLongPtrW(hWnd, -14);
            SetWindowLongPtrW(Window, -20, WindowLongPtrW | 0x40000);
            SetClassLongPtrW(Window, -34, ClassLongPtrW);
          }
        }
      }
    }
    return DefWindowProcW(hWnd, Msg, wParam, lParam);
  }
  if ( Msg != 78 || *(_DWORD *)(lParam + 16) != -500 )
    return DefWindowProcW(hWnd, Msg, wParam, lParam);
  v8 = *(_QWORD *)(lParam + 24);
  if ( v8 )
    SetClassLongPtrW(hWnd, -14, v8);
  SetWindowLongPtrW(hWnd, 0, 1);
  return 0;
}

```

## disassembly

```asm
0x140008010  push    rbx
0x140008012  push    rbp
0x140008013  push    rsi
0x140008014  push    rdi
0x140008015  push    r12
0x140008017  push    r14
0x140008019  push    r15
0x14000801b  sub     rsp, 0E0h
0x140008022  mov     rax, cs:__security_cookie
0x140008029  xor     rax, rsp
0x14000802c  mov     [rsp+118h+var_48], rax
0x140008034  mov     rbp, r9
0x140008037  mov     r12, r8
0x14000803a  mov     r14d, edx
0x14000803d  mov     rsi, rcx
0x140008040  cmp     edx, 1Ch
0x140008043  jz      short loc_140008085
0x140008045  cmp     edx, 4Eh ; 'N'
0x140008048  jnz     loc_140008190
0x14000804e  cmp     dword ptr [r9+10h], 0FFFFFE0Ch
0x140008056  jnz     loc_140008190
0x14000805c  mov     r8, [r9+18h]; dwNewLong
0x140008060  test    r8, r8
0x140008063  jz      short loc_14000806F
0x140008065  lea     edx, [r14-5Ch]; nIndex
0x140008069  call    cs:__imp_SetClassLongPtrW
0x14000806f  xor     edx, edx; nIndex
0x140008071  mov     rcx, rsi; hWnd
0x140008074  lea     r8d, [rdx+1]; dwNewLong
0x140008078  call    cs:__imp_SetWindowLongPtrW
0x14000807e  xor     eax, eax
0x140008080  jmp     loc_1400081A2
0x140008085  xor     edx, edx; nIndex
0x140008087  call    cs:__imp_GetWindowLongPtrW
0x14000808d  xor     ebx, ebx
0x14000808f  test    rax, rax
0x140008092  jz      loc_140008190
0x140008098  lea     r15d, [rbx+3]
0x14000809c  mov     rcx, rsi; hWnd
0x14000809f  mov     edx, r15d; uCmd
0x1400080a2  call    cs:__imp_GetWindow
0x1400080a8  mov     rdi, rax
0x1400080ab  test    rax, rax
0x1400080ae  jz      loc_140008190
0x1400080b4  xor     edx, edx; Val
0x1400080b6  mov     [rsp+118h+ClassName], bx
0x1400080bb  mov     r8d, 9Eh; Size
0x1400080c1  lea     rcx, [rsp+118h+var_E6]; void *
0x1400080c6  call    memset_0
0x1400080cb  lea     r8d, [rbx+50h]; nMaxCount
0x1400080cf  mov     rcx, rdi; hWnd
0x1400080d2  lea     rdx, [rsp+118h+ClassName]; lpClassName
0x1400080d7  call    cs:__imp_GetClassNameW
0x1400080dd  test    eax, eax
0x1400080df  jz      short loc_14000811B
0x1400080e1  or      r9d, 0FFFFFFFFh; cchCount1
0x1400080e5  lea     rax, String2; "IME"
0x1400080ec  mov     [rsp+118h+cchCount2], r9d; cchCount2
0x1400080f1  lea     r8, [rsp+118h+ClassName]; lpString1
0x1400080f6  lea     edx, [rbx+1]; dwCmpFlags
0x1400080f9  mov     [rsp+118h+lpString2], rax; lpString2
0x1400080fe  lea     ecx, [rbx+7Fh]; Locale
0x140008101  call    cs:__imp_CompareStringW
0x140008107  cmp     eax, 2
0x14000810a  jnz     short loc_14000811B
0x14000810c  mov     edx, r15d; uCmd
0x14000810f  mov     rcx, rdi; hWnd
0x140008112  call    cs:__imp_GetWindow
0x140008118  mov     rdi, rax
0x14000811b  mov     edx, 4; uCmd
0x140008120  mov     rcx, rdi; hWnd
0x140008123  call    cs:__imp_GetWindow
0x140008129  cmp     rax, rsi
0x14000812c  jnz     short loc_140008190
0x14000812e  mov     edx, 0FFFFFFECh; nIndex
0x140008133  mov     rcx, rdi; hWnd
0x140008136  call    cs:__imp_GetWindowLongPtrW
0x14000813c  mov     r15, rax
0x14000813f  test    rax, 40080h
0x140008145  jnz     short loc_140008190
0x140008147  mov     edx, 0FFFFFFDEh; nIndex
0x14000814c  mov     rcx, rdi; hWnd
0x14000814f  call    cs:__imp_GetClassLongPtrW
0x140008155  test    rax, rax
0x140008158  jnz     short loc_140008190
0x14000815a  lea     edx, [rax-0Eh]; nIndex
0x14000815d  mov     rcx, rsi; hWnd
0x140008160  call    cs:__imp_GetClassLongPtrW
0x140008166  bts     r15, 12h
0x14000816b  mov     edx, 0FFFFFFECh; nIndex
0x140008170  mov     r8, r15; dwNewLong
0x140008173  mov     rcx, rdi; hWnd
0x140008176  mov     rbx, rax
0x140008179  call    cs:__imp_SetWindowLongPtrW
0x14000817f  mov     r8, rbx; dwNewLong
0x140008182  mov     edx, 0FFFFFFDEh; nIndex
0x140008187  mov     rcx, rdi; hWnd
0x14000818a  call    cs:__imp_SetClassLongPtrW
0x140008190  mov     r9, rbp; lParam
0x140008193  mov     r8, r12; wParam
0x140008196  mov     edx, r14d; Msg
0x140008199  mov     rcx, rsi; hWnd
0x14000819c  call    cs:__imp_DefWindowProcW
0x1400081a2  mov     rcx, [rsp+118h+var_48]
0x1400081aa  xor     rcx, rsp; StackCookie
0x1400081ad  call    __security_check_cookie
0x1400081b2  add     rsp, 0E0h
0x1400081b9  pop     r15
0x1400081bb  pop     r14
0x1400081bd  pop     r12
0x1400081bf  pop     rdi
0x1400081c0  pop     rsi
0x1400081c1  pop     rbp
0x1400081c2  pop     rbx
0x1400081c3  retn
```
