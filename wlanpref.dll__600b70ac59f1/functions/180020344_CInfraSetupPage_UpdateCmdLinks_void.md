# CInfraSetupPage::UpdateCmdLinks(void)

- ea: `0x180020344`
- end: `0x18002049a`
- name: `?UpdateCmdLinks@CInfraSetupPage@@AEAAXXZ`
- size: `342`
- prototype: `void __fastcall(CInfraSetupPage *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: `installer_update`

## callers

- `0x180009d80`

## callees

- `0x1800079b0`
- `0x180015ac4`
- `0x1800202f8`
- `0x180020344`
- `0x18002d840`

## import_xrefs

- `USER32!ShowWindow` at `0x1800203ff`
- `USER32!ShowWindow` at `0x180020461`
- `USER32!ShowWindow` at `0x18002046c`
- `USER32!ShowWindow` at `0x1800203ff`
- `USER32!ShowWindow` at `0x180020461`
- `USER32!ShowWindow` at `0x18002046c`
- `USER32!GetParent` at `0x180020411`
- `USER32!GetParent` at `0x180020411`
- `USER32!GetWindowRect` at `0x1800203d5`
- `USER32!GetWindowRect` at `0x1800203e2`
- `USER32!GetWindowRect` at `0x1800203ef`
- `USER32!GetWindowRect` at `0x1800203d5`
- `USER32!GetWindowRect` at `0x1800203e2`
- `USER32!GetWindowRect` at `0x1800203ef`
- `USER32!MoveWindow` at `0x180020454`
- `USER32!MoveWindow` at `0x180020454`

## pseudocode

```c
void __fastcall CInfraSetupPage::UpdateCmdLinks(CInfraSetupPage *this)
{
  HWND *v1; // rdi
  HWND v3; // r14
  HWND v4; // rbx
  HWND v5; // r12
  char v6; // r15
  HWND Parent; // rax
  _BYTE v8[8]; // [rsp+30h] [rbp-50h] BYREF
  _BYTE v9[8]; // [rsp+38h] [rbp-48h] BYREF
  _BYTE v10[8]; // [rsp+40h] [rbp-40h] BYREF
  struct tagRECT v11; // [rsp+48h] [rbp-38h] BYREF
  struct tagRECT v12; // [rsp+58h] [rbp-28h] BYREF
  struct tagRECT Rect; // [rsp+68h] [rbp-18h] BYREF

  v1 = (HWND *)((char *)this + 104);
  v3 = *(HWND *)ATL::CWindow::GetDlgItem((char *)this + 104, v8, 10310);
  v4 = *(HWND *)ATL::CWindow::GetDlgItem(v1, v9, 10320);
  v5 = *(HWND *)ATL::CWindow::GetDlgItem(v1, v10, 10312);
  v12 = 0;
  v11 = 0;
  Rect = 0;
  v6 = IsAdhocNetworkAllowed();
  GetWindowRect(*v1, &Rect);
  GetWindowRect(v4, &v11);
  GetWindowRect(v3, &v12);
  if ( !v6 )
    ShowWindow(v3, 0);
  if ( *((_BYTE *)this + 273) )
  {
    ShowWindow(v4, 0);
    ShowWindow(v5, 0);
  }
  else
  {
    Parent = GetParent(*v1);
    SetNextButtonText(Parent, 0x2AA4u);
    if ( !v6 )
      MoveWindow(v4, v12.left - Rect.left, v12.top - Rect.top, v11.right - v11.left, v11.bottom - v11.top, 1);
  }
}

```

## disassembly

```asm
0x180020344  mov     [rsp-28h+arg_8], rbx
0x180020349  mov     [rsp-28h+arg_10], rsi
0x18002034e  push    rbp
0x18002034f  push    rdi
0x180020350  push    r12
0x180020352  push    r14
0x180020354  push    r15
0x180020356  mov     rbp, rsp
0x180020359  sub     rsp, 80h
0x180020360  mov     rax, cs:__security_cookie
0x180020367  xor     rax, rsp
0x18002036a  mov     [rbp+var_8], rax
0x18002036e  lea     rdi, [rcx+68h]
0x180020372  mov     rsi, rcx
0x180020375  mov     rcx, rdi
0x180020378  lea     rdx, [rbp+var_50]
0x18002037c  mov     r8d, 2846h
0x180020382  call    ?GetDlgItem@CWindow@ATL@@QEBA?AV12@H@Z; ATL::CWindow::GetDlgItem(int)
0x180020387  mov     r8d, 2850h
0x18002038d  lea     rdx, [rbp+var_48]
0x180020391  mov     rcx, rdi
0x180020394  mov     r14, [rax]
0x180020397  call    ?GetDlgItem@CWindow@ATL@@QEBA?AV12@H@Z; ATL::CWindow::GetDlgItem(int)
0x18002039c  mov     r8d, 2848h
0x1800203a2  lea     rdx, [rbp+var_40]
0x1800203a6  mov     rcx, rdi
0x1800203a9  mov     rbx, [rax]
0x1800203ac  call    ?GetDlgItem@CWindow@ATL@@QEBA?AV12@H@Z; ATL::CWindow::GetDlgItem(int)
0x1800203b1  xorps   xmm0, xmm0
0x1800203b4  xorps   xmm1, xmm1
0x1800203b7  mov     r12, [rax]
0x1800203ba  movups  xmmword ptr [rbp+var_28.left], xmm0
0x1800203be  movups  xmmword ptr [rbp+var_38.left], xmm1
0x1800203c2  movups  xmmword ptr [rbp+Rect.left], xmm0
0x1800203c6  call    ?IsAdhocNetworkAllowed@@YA_NXZ; IsAdhocNetworkAllowed(void)
0x1800203cb  mov     rcx, [rdi]; hWnd
0x1800203ce  lea     rdx, [rbp+Rect]; lpRect
0x1800203d2  mov     r15b, al
0x1800203d5  call    cs:__imp_GetWindowRect
0x1800203db  lea     rdx, [rbp+var_38]; lpRect
0x1800203df  mov     rcx, rbx; hWnd
0x1800203e2  call    cs:__imp_GetWindowRect
0x1800203e8  lea     rdx, [rbp+var_28]; lpRect
0x1800203ec  mov     rcx, r14; hWnd
0x1800203ef  call    cs:__imp_GetWindowRect
0x1800203f5  test    r15b, r15b
0x1800203f8  jnz     short loc_180020405
0x1800203fa  xor     edx, edx; nCmdShow
0x1800203fc  mov     rcx, r14; hWnd
0x1800203ff  call    cs:__imp_ShowWindow
0x180020405  cmp     byte ptr [rsi+111h], 0
0x18002040c  jnz     short loc_18002045C
0x18002040e  mov     rcx, [rdi]; hWnd
0x180020411  call    cs:__imp_GetParent
0x180020417  mov     rcx, rax; hWnd
0x18002041a  mov     edx, 2AA4h; unsigned int
0x18002041f  call    ?SetNextButtonText@@YAXPEAUHWND__@@I@Z; SetNextButtonText(HWND__ *,uint)
0x180020424  test    r15b, r15b
0x180020427  jnz     short loc_180020472
0x180020429  mov     eax, [rbp+var_38.bottom]
0x18002042c  mov     rcx, rbx; hWnd
0x18002042f  mov     r9d, [rbp+var_38.right]
0x180020433  mov     r8d, [rbp+var_28.top]
0x180020437  mov     edx, [rbp+var_28.left]
0x18002043a  sub     eax, [rbp+var_38.top]
0x18002043d  sub     r9d, [rbp+var_38.left]; nWidth
0x180020441  sub     r8d, [rbp+Rect.top]; Y
0x180020445  sub     edx, [rbp+Rect.left]; X
0x180020448  mov     [rsp+80h+bRepaint], 1; bRepaint
0x180020450  mov     [rsp+80h+nHeight], eax; nHeight
0x180020454  call    cs:__imp_MoveWindow
0x18002045a  jmp     short loc_180020472
0x18002045c  xor     edx, edx; nCmdShow
0x18002045e  mov     rcx, rbx; hWnd
0x180020461  call    cs:__imp_ShowWindow
0x180020467  xor     edx, edx; nCmdShow
0x180020469  mov     rcx, r12; hWnd
0x18002046c  call    cs:__imp_ShowWindow
0x180020472  mov     rcx, [rbp+var_8]
0x180020476  xor     rcx, rsp; StackCookie
0x180020479  call    __security_check_cookie
0x18002047e  lea     r11, [rsp+80h+var_s0]
0x180020486  mov     rbx, [r11+38h]
0x18002048a  mov     rsi, [r11+40h]
0x18002048e  mov     rsp, r11
0x180020491  pop     r15
0x180020493  pop     r14
0x180020495  pop     r12
0x180020497  pop     rdi
0x180020498  pop     rbp
0x180020499  retn
```
