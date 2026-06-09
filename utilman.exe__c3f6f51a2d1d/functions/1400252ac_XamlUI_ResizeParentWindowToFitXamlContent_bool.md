# XamlUI::ResizeParentWindowToFitXamlContent(bool)

- ea: `0x1400252ac`
- end: `0x140025566`
- name: `?ResizeParentWindowToFitXamlContent@XamlUI@@AEAAX_N@Z`
- size: `698`
- prototype: `void __fastcall(XamlUI *__hidden this, bool)`
- caller_count: `2`
- callee_count: `10`
- tags: `installer_update, broker_com_uri`

## callers

- `0x140025030`
- `0x140025820`

## callees

- `0x140002480`
- `0x14000367c`
- `0x140022dcc`
- `0x1400240d4`
- `0x14002471c`
- `0x140024de4`
- `0x1400252ac`
- `0x140025604`
- `0x1400256e8`
- `0x14002576c`

## import_xrefs

- `USER32!GetDpiForWindow` at `0x14002536e`
- `USER32!GetDpiForWindow` at `0x14002536e`
- `USER32!SetWindowPos` at `0x1400254c7`
- `USER32!SetWindowPos` at `0x140025508`
- `USER32!SetWindowPos` at `0x1400254c7`
- `USER32!SetWindowPos` at `0x140025508`
- `USER32!GetWindowLongW` at `0x1400253af`
- `USER32!GetWindowLongW` at `0x1400253c6`
- `USER32!GetWindowLongW` at `0x1400253af`
- `USER32!GetWindowLongW` at `0x1400253c6`
- `USER32!GetWindowRect` at `0x14002546d`
- `USER32!GetWindowRect` at `0x14002546d`
- `USER32!AdjustWindowRectExForDpi` at `0x1400253e6`
- `USER32!AdjustWindowRectExForDpi` at `0x1400253e6`

## string_xrefs

- `0x140025302`: `enduser\ezap\xamlcommon\xamlui.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall XamlUI::ResizeParentWindowToFitXamlContent(XamlUI *this, char a2)
{
  __int64 v4; // rax
  int DpiForWindow; // edi
  float v6; // xmm6_4
  float v7; // xmm7_4
  float v8; // xmm6_4
  unsigned int WindowLongW; // ebx
  unsigned int v10; // eax
  const char *v11; // r9
  int cy; // edi
  int v13; // r14d
  UINT uFlags; // ebx
  const char *v15; // r9
  const char *v16; // r9
  const char *v17; // r9
  float v18[2]; // [rsp+48h] [rbp-F0h] BYREF
  _QWORD v19[3]; // [rsp+50h] [rbp-E8h] BYREF
  __int16 v20; // [rsp+68h] [rbp-D0h]
  _BYTE v21[8]; // [rsp+70h] [rbp-C8h] BYREF
  _BYTE v22[56]; // [rsp+78h] [rbp-C0h] BYREF
  __int128 v23; // [rsp+B0h] [rbp-88h] BYREF
  struct tagRECT Rect; // [rsp+C0h] [rbp-78h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+138h] [rbp+0h]

  _revoke___event_revoker_UIFrameworkElement_Xaml_UI_Windows_winrt___MP8type___abi_UIFrameworkElement_Xaml_UI_Windows_winrt__X_impl_5_EAAHUevent_token_5___E1___96785__BBJA_AA_impl_winrt__QEAAXXZ((char *)this + 64);
  v4 = wistd::unique_ptr<void,wil::process_heap_deleter>::unique_ptr<void,wil::process_heap_deleter>(v21, this);
  v19[0] = retaddr;
  v19[1] = "enduser\\ezap\\xamlcommon\\xamlui.cpp";
  v19[2] = 0;
  v20 = 243;
  wil::scope_exit_log__lambda_f2f6ad95b941ed2acd9e9da7e90c9c52___(v22, v19, v4);
  try
  {
    winrt::impl::consume_Windows_UI_Xaml_IUIElement<winrt::Windows::UI::Xaml::FrameworkElement>::Measure();
    winrt::impl::consume_Windows_UI_Xaml_IUIElement<winrt::Windows::UI::Xaml::FrameworkElement>::DesiredSize(
      (char *)this + 40,
      v18);
    winrt::impl::consume_Windows_UI_Xaml_IUIElement<winrt::Windows::UI::Xaml::FrameworkElement>::UpdateLayout((char *)this + 40);
    DpiForWindow = GetDpiForWindow(*((_QWORD *)this + 2));
    v6 = (float)DpiForWindow / 96.0;
    v7 = v6 * v18[0];
    v8 = v6 * v18[1];
    v23 = 0;
    WindowLongW = GetWindowLongW(*((HWND *)this + 1), -20);
    v10 = GetWindowLongW(*((HWND *)this + 1), -16);
    if ( !(unsigned int)AdjustWindowRectExForDpi(&v23, v10, 0, WindowLongW, DpiForWindow) )
      wil::details::in1diag3::_Throw_GetLastError(
        retaddr,
        (void *)0x10F,
        (unsigned int)"enduser\\ezap\\xamlcommon\\xamlui.cpp",
        v11);
    cy = HIDWORD(v23) + (int)(float)(v8 + 0.5) - DWORD1(v23);
    v13 = DWORD2(v23) + (int)(float)(v7 + 0.5) - v23;
    uFlags = 86;
    if ( a2 && *((_DWORD *)this + 6) == 1 )
      uFlags = 70;
    Rect = 0;
    if ( GetWindowRect(*((HWND *)this + 1), &Rect) )
    {
      if ( (Rect.bottom - Rect.top != cy || Rect.right - Rect.left != v13)
        && !SetWindowPos(*((HWND *)this + 1), 0, 0, 0, v13, cy, uFlags) )
      {
        wil::details::in1diag3::_Throw_GetLastError(
          retaddr,
          (void *)0x121,
          (unsigned int)"enduser\\ezap\\xamlcommon\\xamlui.cpp",
          v15);
      }
    }
    else if ( !SetWindowPos(*((HWND *)this + 1), 0, 0, 0, v13, cy, uFlags) )
    {
      wil::details::in1diag3::_Throw_GetLastError(
        retaddr,
        (void *)0x127,
        (unsigned int)"enduser\\ezap\\xamlcommon\\xamlui.cpp",
        v16);
    }
    wil::details::lambda_call_log__lambda_f2f6ad95b941ed2acd9e9da7e90c9c52___::reset(v22);
  }
  catch ( ... )
  {
    wil::details::in1diag3::Log_CaughtException(
      retaddr,
      (void *)0x12A,
      (unsigned int)"enduser\\ezap\\xamlcommon\\xamlui.cpp",
      v17);
  }
}

```

## disassembly

```asm
0x1400252ac  mov     rax, rsp
0x1400252af  push    rbx
0x1400252b0  push    rsi
0x1400252b1  push    rdi
0x1400252b2  push    r12
0x1400252b4  push    r14
0x1400252b6  push    r15
0x1400252b8  sub     rsp, 108h
0x1400252bf  movaps  xmmword ptr [rax-48h], xmm6
0x1400252c3  movaps  xmmword ptr [rax-58h], xmm7
0x1400252c7  mov     rax, cs:__security_cookie
0x1400252ce  xor     rax, rsp
0x1400252d1  mov     [rsp+138h+var_68], rax
0x1400252d9  mov     r15b, dl
0x1400252dc  mov     rsi, rcx
0x1400252df  add     rcx, 40h ; '@'
0x1400252e3  call    ?revoke@?$event_revoker@UIFrameworkElement@Xaml@UI@Windows@winrt@@$MP8type@?$abi@UIFrameworkElement@Xaml@UI@Windows@winrt@@X@impl@5@EAAHUevent_token@5@@_E1??_96785@$BBJA@AA@impl@winrt@@QEAAXXZ
0x1400252e8  mov     rdx, rsi
0x1400252eb  lea     rcx, [rsp+138h+var_C8]
0x1400252f0  call    ??$?0$00X@?$unique_ptr@XUprocess_heap_deleter@wil@@@wistd@@QEAA@PEAX@Z; wistd::unique_ptr<void,wil::process_heap_deleter>::unique_ptr<void,wil::process_heap_deleter>(void *)
0x1400252f5  mov     rcx, [rsp+138h]
0x1400252fd  mov     [rsp+138h+var_E8], rcx
0x140025302  lea     r12, aEnduserEzapXam; "enduser\\ezap\\xamlcommon\\xamlui.cpp"
0x140025309  mov     [rsp+138h+var_E0], r12
0x14002530e  mov     [rsp+138h+var_D8], 0
0x140025317  mov     ecx, 0F3h
0x14002531c  mov     [rsp+138h+var_D0], cx
0x140025321  mov     r8, rax
0x140025324  lea     rdx, [rsp+138h+var_E8]
0x140025329  lea     rcx, [rsp+138h+var_C0]
0x14002532e  call    wil__scope_exit_log__lambda_f2f6ad95b941ed2acd9e9da7e90c9c52___
0x140025333  nop
0x140025334  mov     [rsp+138h+var_F8], 459C4000h
0x14002533c  mov     [rsp+138h+var_F4], 459C4000h
0x140025344  lea     rbx, [rsi+28h]
0x140025348  lea     rdx, [rsp+138h+var_F8]
0x14002534d  mov     rcx, rbx
0x140025350  call    ?Measure@?$consume_Windows_UI_Xaml_IUIElement@UFrameworkElement@Xaml@UI@Windows@winrt@@@impl@winrt@@QEBA@AEBUSize@Foundation@Windows@3@@Z; winrt::impl::consume_Windows_UI_Xaml_IUIElement<winrt::Windows::UI::Xaml::FrameworkElement>::Measure(winrt::Windows::Foundation::Size const &)
0x140025355  lea     rdx, [rsp+138h+var_F0]
0x14002535a  mov     rcx, rbx
0x14002535d  call    ?DesiredSize@?$consume_Windows_UI_Xaml_IUIElement@UFrameworkElement@Xaml@UI@Windows@winrt@@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Windows_UI_Xaml_IUIElement<winrt::Windows::UI::Xaml::FrameworkElement>::DesiredSize(void)
0x140025362  mov     rcx, rbx
0x140025365  call    ?UpdateLayout@?$consume_Windows_UI_Xaml_IUIElement@UFrameworkElement@Xaml@UI@Windows@winrt@@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Windows_UI_Xaml_IUIElement<winrt::Windows::UI::Xaml::FrameworkElement>::UpdateLayout(void)
0x14002536a  mov     rcx, [rsi+10h]
0x14002536e  call    cs:__imp_GetDpiForWindow
0x140025375  nop     dword ptr [rax+rax+00h]
0x14002537a  mov     edi, eax
0x14002537c  xorps   xmm6, xmm6
0x14002537f  cvtsi2ss xmm6, rdi
0x140025384  divss   xmm6, cs:__real@42c00000
0x14002538c  movaps  xmm7, xmm6
0x14002538f  mulss   xmm7, [rsp+138h+var_F0]
0x140025395  mulss   xmm6, [rsp+138h+var_EC]
0x14002539b  xorps   xmm0, xmm0
0x14002539e  movups  [rsp+138h+var_88], xmm0
0x1400253a6  mov     edx, 0FFFFFFECh; nIndex
0x1400253ab  mov     rcx, [rsi+8]; hWnd
0x1400253af  call    cs:__imp_GetWindowLongW
0x1400253b6  nop     dword ptr [rax+rax+00h]
0x1400253bb  mov     ebx, eax
0x1400253bd  mov     edx, 0FFFFFFF0h; nIndex
0x1400253c2  mov     rcx, [rsi+8]; hWnd
0x1400253c6  call    cs:__imp_GetWindowLongW
0x1400253cd  nop     dword ptr [rax+rax+00h]
0x1400253d2  mov     [rsp+138h+var_118], edi
0x1400253d6  mov     r9d, ebx
0x1400253d9  xor     r8d, r8d
0x1400253dc  mov     edx, eax
0x1400253de  lea     rcx, [rsp+138h+var_88]
0x1400253e6  call    cs:__imp_AdjustWindowRectExForDpi
0x1400253ed  nop     dword ptr [rax+rax+00h]
0x1400253f2  mov     rcx, [rsp+138h]; this
0x1400253fa  test    eax, eax
0x1400253fc  jnz     short loc_14002540B
0x1400253fe  mov     r8, r12; unsigned int
0x140025401  mov     edx, 10Fh; void *
0x140025406  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
0x14002540b  addss   xmm6, cs:__real@3f000000
0x140025413  cvttss2si edi, xmm6
0x140025417  sub     edi, dword ptr [rsp+138h+var_88+4]
0x14002541e  add     edi, dword ptr [rsp+138h+var_88+0Ch]
0x140025425  addss   xmm7, cs:__real@3f000000
0x14002542d  cvttss2si r14d, xmm7
0x140025432  sub     r14d, dword ptr [rsp+138h+var_88]
0x14002543a  add     r14d, dword ptr [rsp+138h+var_88+8]
0x140025442  mov     ebx, 56h ; 'V'
0x140025447  test    r15b, r15b
0x14002544a  jz      short loc_140025456
0x14002544c  lea     eax, [rbx-10h]
0x14002544f  cmp     dword ptr [rsi+18h], 1
0x140025453  cmovz   ebx, eax
0x140025456  xorps   xmm0, xmm0
0x140025459  movups  xmmword ptr [rsp+138h+Rect.left], xmm0
0x140025461  lea     rdx, [rsp+138h+Rect]; lpRect
0x140025469  mov     rcx, [rsi+8]; hWnd
0x14002546d  call    cs:__imp_GetWindowRect
0x140025474  nop     dword ptr [rax+rax+00h]
0x140025479  test    eax, eax
0x14002547b  jz      short loc_1400254E7
0x14002547d  mov     eax, [rsp+138h+Rect.bottom]
0x140025484  sub     eax, [rsp+138h+Rect.top]
0x14002548b  cmp     eax, edi
0x14002548d  jnz     short loc_1400254A6
0x14002548f  mov     eax, [rsp+138h+Rect.right]
0x140025496  sub     eax, [rsp+138h+Rect.left]
0x14002549d  cmp     eax, r14d
0x1400254a0  jz      loc_140025529
0x1400254a6  mov     r15, [rsp+138h]
0x1400254ae  mov     [rsp+138h+uFlags], ebx; uFlags
0x1400254b2  mov     [rsp+138h+cy], edi; cy
0x1400254b6  mov     [rsp+138h+var_118], r14d; cx
0x1400254bb  xor     r9d, r9d; Y
0x1400254be  xor     r8d, r8d; X
0x1400254c1  xor     edx, edx; hWndInsertAfter
0x1400254c3  mov     rcx, [rsi+8]; hWnd
0x1400254c7  call    cs:__imp_SetWindowPos
0x1400254ce  nop     dword ptr [rax+rax+00h]
0x1400254d3  test    eax, eax
0x1400254d5  jnz     short loc_140025529
0x1400254d7  mov     r8, r12; unsigned int
0x1400254da  mov     edx, 121h; void *
0x1400254df  mov     rcx, r15; this
0x1400254e2  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
0x1400254e7  mov     r15, [rsp+138h]
0x1400254ef  mov     [rsp+138h+uFlags], ebx; uFlags
0x1400254f3  mov     [rsp+138h+cy], edi; cy
0x1400254f7  mov     [rsp+138h+var_118], r14d; cx
0x1400254fc  xor     r9d, r9d; Y
0x1400254ff  xor     r8d, r8d; X
0x140025502  xor     edx, edx; hWndInsertAfter
0x140025504  mov     rcx, [rsi+8]; hWnd
0x140025508  call    cs:__imp_SetWindowPos
0x14002550f  nop     dword ptr [rax+rax+00h]
0x140025514  test    eax, eax
0x140025516  jnz     short loc_140025529
0x140025518  mov     r8, r12; unsigned int
0x14002551b  mov     edx, 127h; void *
0x140025520  mov     rcx, r15; this
0x140025523  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
0x140025529  lea     rcx, [rsp+138h+var_C0]
0x14002552e  call    wil__details__lambda_call_log__lambda_f2f6ad95b941ed2acd9e9da7e90c9c52_____reset
0x140025533  nop
0x140025534  jmp     short $+2
0x140025536  mov     rcx, [rsp+138h+var_68]
0x14002553e  xor     rcx, rsp; StackCookie
0x140025541  call    __security_check_cookie
0x140025546  lea     r11, [rsp+138h+var_30]
0x14002554e  movaps  xmm6, xmmword ptr [r11-18h]
0x140025553  movaps  xmm7, xmmword ptr [r11-28h]
0x140025558  mov     rsp, r11
0x14002555b  pop     r15
0x14002555d  pop     r14
0x14002555f  pop     r12
0x140025561  pop     rdi
0x140025562  pop     rsi
0x140025563  pop     rbx
0x140025564  retn
```
