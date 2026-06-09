# Windows::Internal::_anonymous_namespace_::CDimmingWindow::_InitializeSystem

- ea: `0x1800b0d24`
- end: `0x1800b0ecf`
- name: `Windows::Internal::_anonymous_namespace_::CDimmingWindow::_InitializeSystem`
- size: `427`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `service_task`

## callers

- `0x1800331fc`

## callees

- `0x180054130`
- `0x1800b0800`
- `0x1800b0d24`
- `0x1800b111c`

## import_xrefs

- `USER32!CreateWindowInBand` at `0x1800b0df3`
- `USER32!CreateWindowInBand` at `0x1800b0df3`
- `USER32!GetMonitorInfoW` at `0x1800b0d81`
- `USER32!GetMonitorInfoW` at `0x1800b0d81`
- `USER32!SetPropW` at `0x1800b0e16`
- `USER32!SetPropW` at `0x1800b0e16`
- `USER32!CreateWindowExW` at `0x1800b0e78`
- `USER32!CreateWindowExW` at `0x1800b0e78`
- `USER32!DestroyWindow` at `0x1800b0e9d`
- `USER32!DestroyWindow` at `0x1800b0e9d`

## pseudocode

```c
__int64 __fastcall Windows::Internal::_anonymous_namespace_::CDimmingWindow::_InitializeSystem(
        __int64 a1,
        int a2,
        __int64 a3,
        const WCHAR *a4,
        DWORD dwStyle,
        char a6,
        HMONITOR hMonitor,
        char a8)
{
  HWND WindowInBand; // rax
  LONG X; // eax
  LONG Y; // ecx
  struct tagMONITORINFO mi; // [rsp+70h] [rbp-29h] BYREF

  Windows::Internal::_anonymous_namespace_::CDimmingWindow::_RegisterSystemDimmingWindowClass();
  *(_BYTE *)(a1 + 16) = 1;
  memset(&mi, 0, sizeof(mi));
  mi.cbSize = 40;
  GetMonitorInfoW(hMonitor, &mi);
  WindowInBand = (HWND)CreateWindowInBand(
                         0x80000,
                         L"Shell_SystemDim",
                         0,
                         0x80000000LL,
                         mi.rcMonitor.left,
                         mi.rcMonitor.top,
                         mi.rcMonitor.right - mi.rcMonitor.left,
                         mi.rcMonitor.bottom - mi.rcMonitor.top,
                         0,
                         0,
                         &_ImageBase,
                         a1,
                         a6 != 0 ? 1 : 4);
  *(_QWORD *)(a1 + 8) = WindowInBand;
  if ( WindowInBand )
  {
    SetPropW(WindowInBand, L"Shell_Dimming_Window_Prop", HANDLE_FLAG_INHERIT);
    if ( a8 )
    {
      X = mi.rcMonitor.left;
      Y = mi.rcMonitor.top;
    }
    else
    {
      X = 0x80000000;
      Y = 0x80000000;
    }
    *(_QWORD *)a1 = CreateWindowExW(
                      a2 | 0x40000u,
                      L"Shell_SystemDialog",
                      a4,
                      dwStyle,
                      X,
                      Y,
                      0x80000000,
                      0x80000000,
                      *(HWND *)(a1 + 8),
                      0,
                      &_ImageBase,
                      0);
  }
  if ( *(_QWORD *)a1 )
  {
    Windows::Internal::_anonymous_namespace_::CDimmingWindow::_CreateTaskbarProxyWindow(a1, a4);
  }
  else
  {
    DestroyWindow(*(HWND *)(a1 + 8));
    *(_QWORD *)(a1 + 8) = 0;
  }
  return *(_QWORD *)a1;
}

```

## disassembly

```asm
0x1800b0d24  push    rbp
0x1800b0d26  push    rbx
0x1800b0d27  push    rsi
0x1800b0d28  push    rdi
0x1800b0d29  push    r12
0x1800b0d2b  push    r14
0x1800b0d2d  push    r15
0x1800b0d2f  lea     rbp, [rsp-7]
0x1800b0d34  sub     rsp, 0A0h
0x1800b0d3b  mov     rax, cs:__security_cookie
0x1800b0d42  xor     rax, rsp
0x1800b0d45  mov     [rbp+37h+var_38], rax
0x1800b0d49  mov     r15d, [rbp+37h+dwStyle]
0x1800b0d4d  mov     r14, r9
0x1800b0d50  mov     rbx, [rbp+37h+hMonitor]
0x1800b0d54  mov     esi, edx
0x1800b0d56  mov     rdi, rcx
0x1800b0d59  call    Windows__Internal___anonymous_namespace___CDimmingWindow___RegisterSystemDimmingWindowClass
0x1800b0d5e  xorps   xmm0, xmm0
0x1800b0d61  mov     byte ptr [rdi+10h], 1
0x1800b0d65  xor     eax, eax
0x1800b0d67  lea     rdx, [rbp+37h+mi]; lpmi
0x1800b0d6b  movups  xmmword ptr [rbp+37h+mi.cbSize], xmm0
0x1800b0d6f  mov     rcx, rbx; hMonitor
0x1800b0d72  mov     [rbp+37h+mi.cbSize], 28h ; '('
0x1800b0d79  movups  xmmword ptr [rbp+37h+mi.rcMonitor.bottom], xmm0
0x1800b0d7d  mov     qword ptr [rbp+37h+mi.rcWork.bottom], rax
0x1800b0d81  call    cs:__imp_GetMonitorInfoW
0x1800b0d88  nop     dword ptr [rax+rax+00h]
0x1800b0d8d  mov     r9d, [rbp+37h+mi.rcMonitor.top]
0x1800b0d91  lea     r12, __ImageBase
0x1800b0d98  mov     edx, [rbp+37h+mi.rcMonitor.left]
0x1800b0d9b  mov     r8d, [rbp+37h+mi.rcMonitor.bottom]
0x1800b0d9f  mov     ecx, [rbp+37h+mi.rcMonitor.right]
0x1800b0da2  neg     [rbp+37h+arg_28]
0x1800b0da5  sbb     eax, eax
0x1800b0da7  sub     r8d, r9d
0x1800b0daa  sub     ecx, edx
0x1800b0dac  and     eax, 0FFFFFFFDh
0x1800b0daf  add     eax, 4
0x1800b0db2  xor     ebx, ebx
0x1800b0db4  mov     [rsp+0D0h+var_70], eax
0x1800b0db8  mov     [rsp+0D0h+lpParam], rdi
0x1800b0dbd  mov     [rsp+0D0h+hInstance], r12
0x1800b0dc2  mov     [rsp+0D0h+hMenu], rbx
0x1800b0dc7  mov     [rsp+0D0h+hWndParent], rbx
0x1800b0dcc  mov     [rsp+0D0h+nHeight], r8d
0x1800b0dd1  xor     r8d, r8d
0x1800b0dd4  mov     [rsp+0D0h+nWidth], ecx
0x1800b0dd8  mov     ecx, 80000h
0x1800b0ddd  mov     [rsp+0D0h+Y], r9d
0x1800b0de2  mov     r9d, 80000000h
0x1800b0de8  mov     [rsp+0D0h+X], edx
0x1800b0dec  lea     rdx, aShellSystemdim; "Shell_SystemDim"
0x1800b0df3  call    cs:__imp_CreateWindowInBand
0x1800b0dfa  nop     dword ptr [rax+rax+00h]
0x1800b0dff  mov     [rdi+8], rax
0x1800b0e03  test    rax, rax
0x1800b0e06  jz      short loc_1800B0E87
0x1800b0e08  lea     r8d, [rbx+1]; hData
0x1800b0e0c  mov     rcx, rax; hWnd
0x1800b0e0f  lea     rdx, aShellDimmingWi; "Shell_Dimming_Window_Prop"
0x1800b0e16  call    cs:__imp_SetPropW
0x1800b0e1d  nop     dword ptr [rax+rax+00h]
0x1800b0e22  mov     r8d, 80000000h
0x1800b0e28  mov     rdx, [rdi+8]
0x1800b0e2c  cmp     [rbp+37h+arg_38], bl
0x1800b0e2f  jz      short loc_1800B0E39
0x1800b0e31  mov     eax, [rbp+37h+mi.rcMonitor.left]
0x1800b0e34  mov     ecx, [rbp+37h+mi.rcMonitor.top]
0x1800b0e37  jmp     short loc_1800B0E3F
0x1800b0e39  mov     eax, r8d
0x1800b0e3c  mov     ecx, r8d
0x1800b0e3f  mov     [rsp+0D0h+lpParam], rbx; lpParam
0x1800b0e44  bts     esi, 12h
0x1800b0e48  mov     [rsp+0D0h+hInstance], r12; hInstance
0x1800b0e4d  mov     r9d, r15d; dwStyle
0x1800b0e50  mov     [rsp+0D0h+hMenu], rbx; hMenu
0x1800b0e55  mov     [rsp+0D0h+hWndParent], rdx; hWndParent
0x1800b0e5a  lea     rdx, aShellSystemdia_0; "Shell_SystemDialog"
0x1800b0e61  mov     [rsp+0D0h+nHeight], r8d; nHeight
0x1800b0e66  mov     [rsp+0D0h+nWidth], r8d; nWidth
0x1800b0e6b  mov     r8, r14; lpWindowName
0x1800b0e6e  mov     [rsp+0D0h+Y], ecx; Y
0x1800b0e72  mov     ecx, esi; dwExStyle
0x1800b0e74  mov     [rsp+0D0h+X], eax; X
0x1800b0e78  call    cs:__imp_CreateWindowExW
0x1800b0e7f  nop     dword ptr [rax+rax+00h]
0x1800b0e84  mov     [rdi], rax
0x1800b0e87  cmp     [rdi], rbx
0x1800b0e8a  jz      short loc_1800B0E99
0x1800b0e8c  mov     rdx, r14
0x1800b0e8f  mov     rcx, rdi
0x1800b0e92  call    Windows__Internal___anonymous_namespace___CDimmingWindow___CreateTaskbarProxyWindow
0x1800b0e97  jmp     short loc_1800B0EAD
0x1800b0e99  mov     rcx, [rdi+8]; hWnd
0x1800b0e9d  call    cs:__imp_DestroyWindow
0x1800b0ea4  nop     dword ptr [rax+rax+00h]
0x1800b0ea9  mov     [rdi+8], rbx
0x1800b0ead  mov     rax, [rdi]
0x1800b0eb0  mov     rcx, [rbp+37h+var_38]
0x1800b0eb4  xor     rcx, rsp; StackCookie
0x1800b0eb7  call    __security_check_cookie
0x1800b0ebc  add     rsp, 0A0h
0x1800b0ec3  pop     r15
0x1800b0ec5  pop     r14
0x1800b0ec7  pop     r12
0x1800b0ec9  pop     rdi
0x1800b0eca  pop     rsi
0x1800b0ecb  pop     rbx
0x1800b0ecc  pop     rbp
0x1800b0ecd  retn
```
