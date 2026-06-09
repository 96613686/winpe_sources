# Windows::Internal::_anonymous_namespace_::CDimmingWindow::_InitializeOnDesktop

- ea: `0x1800b0b54`
- end: `0x1800b0d1b`
- name: `Windows::Internal::_anonymous_namespace_::CDimmingWindow::_InitializeOnDesktop`
- size: `455`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x1800b01bc`

## callees

- `0x180054130`
- `0x1800b0758`
- `0x1800b0b54`
- `0x1800b1094`

## import_xrefs

- `USER32!CreateWindowInBandEx` at `0x1800b0c48`
- `USER32!CreateWindowInBandEx` at `0x1800b0c48`
- `USER32!GetMonitorInfoW` at `0x1800b0bd8`
- `USER32!GetMonitorInfoW` at `0x1800b0bd8`
- `USER32!SetPropW` at `0x1800b0c6f`
- `USER32!SetPropW` at `0x1800b0c6f`
- `USER32!CreateWindowExW` at `0x1800b0cb4`
- `USER32!CreateWindowExW` at `0x1800b0cb4`
- `USER32!DestroyWindow` at `0x1800b0ce3`
- `USER32!DestroyWindow` at `0x1800b0ce3`

## pseudocode

```c
__int64 __fastcall Windows::Internal::_anonymous_namespace_::CDimmingWindow::_InitializeOnDesktop(
        __int64 a1,
        DWORD a2,
        const WCHAR *a3,
        const WCHAR *a4,
        DWORD dwStyle,
        __int64 a6,
        int a7,
        HMONITOR hMonitor)
{
  HWND WindowInBand; // rax
  HWND Window; // rax
  struct tagMONITORINFO mi; // [rsp+70h] [rbp-78h] BYREF

  Windows::Internal::_anonymous_namespace_::CDimmingWindow::_RegisterDimmingWindowClass();
  *(_BYTE *)(a1 + 16) = 1;
  memset(&mi, 0, sizeof(mi));
  mi.cbSize = 40;
  GetMonitorInfoW(hMonitor, &mi);
  WindowInBand = (HWND)CreateWindowInBandEx(
                         0x80000,
                         L"Shell_Dim",
                         0,
                         0x80000000LL,
                         mi.rcMonitor.left,
                         mi.rcMonitor.top,
                         mi.rcMonitor.right - mi.rcMonitor.left,
                         mi.rcMonitor.bottom - mi.rcMonitor.top,
                         a6,
                         0,
                         &_ImageBase,
                         a1,
                         0,
                         a7);
  *(_QWORD *)(a1 + 8) = WindowInBand;
  if ( WindowInBand )
  {
    SetPropW(WindowInBand, L"Shell_Dimming_Window_Prop", HANDLE_FLAG_INHERIT);
    Window = CreateWindowExW(
               a2,
               a3,
               a4,
               dwStyle,
               0x80000000,
               0x80000000,
               0x80000000,
               0x80000000,
               *(HWND *)(a1 + 8),
               0,
               &_ImageBase,
               0);
    *(_QWORD *)a1 = Window;
    if ( Window )
    {
      if ( a6 )
        Windows::Internal::_anonymous_namespace_::CWindowWaiter::Wait(a1 + 40, a6, *(_QWORD *)(a1 + 8));
    }
    else
    {
      DestroyWindow(*(HWND *)(a1 + 8));
      *(_QWORD *)(a1 + 8) = 0;
    }
  }
  return *(_QWORD *)a1;
}

```

## disassembly

```asm
0x1800b0b54  push    rbx
0x1800b0b56  push    rbp
0x1800b0b57  push    rsi
0x1800b0b58  push    rdi
0x1800b0b59  push    r12
0x1800b0b5b  push    r13
0x1800b0b5d  push    r14
0x1800b0b5f  push    r15
0x1800b0b61  sub     rsp, 0A8h
0x1800b0b68  mov     rax, cs:__security_cookie
0x1800b0b6f  xor     rax, rsp
0x1800b0b72  mov     [rsp+0E8h+var_50], rax
0x1800b0b7a  mov     r13d, [rsp+0E8h+dwStyle]
0x1800b0b82  mov     r12, r9
0x1800b0b85  mov     rbp, [rsp+0E8h+arg_28]
0x1800b0b8d  mov     r15, r8
0x1800b0b90  mov     edi, [rsp+0E8h+arg_30]
0x1800b0b97  mov     r14d, edx
0x1800b0b9a  mov     rbx, [rsp+0E8h+hMonitor]
0x1800b0ba2  mov     rsi, rcx
0x1800b0ba5  call    Windows__Internal___anonymous_namespace___CDimmingWindow___RegisterDimmingWindowClass
0x1800b0baa  xorps   xmm0, xmm0
0x1800b0bad  mov     byte ptr [rsi+10h], 1
0x1800b0bb1  xor     eax, eax
0x1800b0bb3  lea     rdx, [rsp+0E8h+mi]; lpmi
0x1800b0bb8  movups  xmmword ptr [rsp+0E8h+mi.cbSize], xmm0
0x1800b0bbd  mov     rcx, rbx; hMonitor
0x1800b0bc0  mov     [rsp+0E8h+mi.cbSize], 28h ; '('
0x1800b0bc8  movups  xmmword ptr [rsp+0E8h+mi.rcMonitor.bottom], xmm0
0x1800b0bd0  mov     qword ptr [rsp+0E8h+mi.rcWork.bottom], rax
0x1800b0bd8  call    cs:__imp_GetMonitorInfoW
0x1800b0bdf  nop     dword ptr [rax+rax+00h]
0x1800b0be4  mov     r8d, [rsp+0E8h+mi.rcMonitor.top]
0x1800b0be9  xor     ebx, ebx
0x1800b0beb  mov     ecx, [rsp+0E8h+mi.rcMonitor.left]
0x1800b0bef  mov     r9d, 80000000h
0x1800b0bf5  mov     edx, [rsp+0E8h+mi.rcMonitor.bottom]
0x1800b0bfc  mov     eax, [rsp+0E8h+mi.rcMonitor.right]
0x1800b0c00  sub     edx, r8d
0x1800b0c03  mov     [rsp+0E8h+var_80], edi
0x1800b0c07  sub     eax, ecx
0x1800b0c09  mov     [rsp+0E8h+var_88], ebx
0x1800b0c0d  lea     rdi, __ImageBase
0x1800b0c14  mov     [rsp+0E8h+lpParam], rsi
0x1800b0c19  mov     [rsp+0E8h+hInstance], rdi
0x1800b0c1e  mov     [rsp+0E8h+hMenu], rbx
0x1800b0c23  mov     [rsp+0E8h+hWndParent], rbp
0x1800b0c28  mov     [rsp+0E8h+nHeight], edx
0x1800b0c2c  lea     rdx, aShellDim; "Shell_Dim"
0x1800b0c33  mov     [rsp+0E8h+nWidth], eax
0x1800b0c37  mov     [rsp+0E8h+Y], r8d
0x1800b0c3c  xor     r8d, r8d
0x1800b0c3f  mov     [rsp+0E8h+X], ecx
0x1800b0c43  mov     ecx, 80000h
0x1800b0c48  call    cs:__imp_CreateWindowInBandEx
0x1800b0c4f  nop     dword ptr [rax+rax+00h]
0x1800b0c54  mov     [rsi+8], rax
0x1800b0c58  test    rax, rax
0x1800b0c5b  jz      loc_1800B0CF3
0x1800b0c61  lea     r8d, [rbx+1]; hData
0x1800b0c65  mov     rcx, rax; hWnd
0x1800b0c68  lea     rdx, aShellDimmingWi; "Shell_Dimming_Window_Prop"
0x1800b0c6f  call    cs:__imp_SetPropW
0x1800b0c76  nop     dword ptr [rax+rax+00h]
0x1800b0c7b  mov     rax, [rsi+8]
0x1800b0c7f  mov     r9d, r13d; dwStyle
0x1800b0c82  mov     [rsp+0E8h+lpParam], rbx; lpParam
0x1800b0c87  mov     r8, r12; lpWindowName
0x1800b0c8a  mov     [rsp+0E8h+hInstance], rdi; hInstance
0x1800b0c8f  mov     rdx, r15; lpClassName
0x1800b0c92  mov     [rsp+0E8h+hMenu], rbx; hMenu
0x1800b0c97  mov     ecx, r14d; dwExStyle
0x1800b0c9a  mov     [rsp+0E8h+hWndParent], rax; hWndParent
0x1800b0c9f  mov     eax, 80000000h
0x1800b0ca4  mov     [rsp+0E8h+nHeight], eax; nHeight
0x1800b0ca8  mov     [rsp+0E8h+nWidth], eax; nWidth
0x1800b0cac  mov     [rsp+0E8h+Y], eax; Y
0x1800b0cb0  mov     [rsp+0E8h+X], eax; X
0x1800b0cb4  call    cs:__imp_CreateWindowExW
0x1800b0cbb  nop     dword ptr [rax+rax+00h]
0x1800b0cc0  mov     [rsi], rax
0x1800b0cc3  test    rax, rax
0x1800b0cc6  jz      short loc_1800B0CDF
0x1800b0cc8  test    rbp, rbp
0x1800b0ccb  jz      short loc_1800B0CF3
0x1800b0ccd  mov     r8, [rsi+8]
0x1800b0cd1  lea     rcx, [rsi+28h]
0x1800b0cd5  mov     rdx, rbp
0x1800b0cd8  call    Windows__Internal___anonymous_namespace___CWindowWaiter__Wait
0x1800b0cdd  jmp     short loc_1800B0CF3
0x1800b0cdf  mov     rcx, [rsi+8]; hWnd
0x1800b0ce3  call    cs:__imp_DestroyWindow
0x1800b0cea  nop     dword ptr [rax+rax+00h]
0x1800b0cef  mov     [rsi+8], rbx
0x1800b0cf3  mov     rax, [rsi]
0x1800b0cf6  mov     rcx, [rsp+0E8h+var_50]
0x1800b0cfe  xor     rcx, rsp; StackCookie
0x1800b0d01  call    __security_check_cookie
0x1800b0d06  add     rsp, 0A8h
0x1800b0d0d  pop     r15
0x1800b0d0f  pop     r14
0x1800b0d11  pop     r13
0x1800b0d13  pop     r12
0x1800b0d15  pop     rdi
0x1800b0d16  pop     rsi
0x1800b0d17  pop     rbp
0x1800b0d18  pop     rbx
0x1800b0d19  retn
```
