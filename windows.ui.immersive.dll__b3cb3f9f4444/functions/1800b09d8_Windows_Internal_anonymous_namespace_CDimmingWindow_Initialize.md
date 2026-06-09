# Windows::Internal::_anonymous_namespace_::CDimmingWindow::_Initialize

- ea: `0x1800b09d8`
- end: `0x1800b0b4c`
- name: `Windows::Internal::_anonymous_namespace_::CDimmingWindow::_Initialize`
- size: `372`
- prototype: `__int64 __usercall@<rax>(LPVOID lpParam@<rcx>, DWORD dwExStyle@<edx>, DWORD dwStyle, HWND, __int64)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x1800b00f0`

## callees

- `0x1800b0758`
- `0x1800b09d8`
- `0x1800b0ed8`
- `0x1800b1094`
- `0x1800ed010`

## import_xrefs

- `USER32!SetPropW` at `0x1800b0a9a`
- `USER32!SetPropW` at `0x1800b0a9a`
- `USER32!CreateWindowExW` at `0x1800b0a71`
- `USER32!CreateWindowExW` at `0x1800b0aff`
- `USER32!CreateWindowExW` at `0x1800b0a71`
- `USER32!CreateWindowExW` at `0x1800b0aff`
- `USER32!DestroyWindow` at `0x1800b0b29`
- `USER32!DestroyWindow` at `0x1800b0b29`

## pseudocode

```c
__int64 __fastcall Windows::Internal::_anonymous_namespace_::CDimmingWindow::_Initialize(
        char *lpParam,
        DWORD dwExStyle,
        __int64 a3,
        const WCHAR *a4,
        DWORD dwStyle,
        HWND hWndParent,
        __int64 a7)
{
  int *v10; // rax
  HWND Window; // rax
  HWND v12; // rax
  _BYTE v14[56]; // [rsp+60h] [rbp-38h] BYREF

  *((_QWORD *)lpParam + 3) = a7;
  Windows::Internal::_anonymous_namespace_::CDimmingWindow::_RegisterDimmingWindowClass();
  v10 = (int *)(*((__int64 (__fastcall **)(_BYTE *, HWND, _QWORD))lpParam + 3))(v14, hWndParent, 0);
  Window = CreateWindowExW(
             0x80000u,
             L"Shell_Dim",
             0,
             0x80000000,
             *v10,
             v10[1],
             v10[2] - *v10,
             v10[3] - v10[1],
             hWndParent,
             0,
             &_ImageBase,
             lpParam);
  *((_QWORD *)lpParam + 1) = Window;
  if ( Window )
  {
    SetPropW(Window, L"Shell_Dimming_Window_Prop", HANDLE_FLAG_INHERIT);
    Windows::Internal::_anonymous_namespace_::CDimmingWindow::_InvokeCallback(lpParam, v14, hWndParent);
    v12 = CreateWindowExW(
            dwExStyle,
            L"Shell_HostingContainer",
            a4,
            dwStyle,
            0x80000000,
            0x80000000,
            0x80000000,
            0x80000000,
            *((HWND *)lpParam + 1),
            0,
            &_ImageBase,
            0);
    *(_QWORD *)lpParam = v12;
    if ( v12 )
    {
      Windows::Internal::_anonymous_namespace_::CWindowWaiter::Wait(lpParam + 40, hWndParent, *((_QWORD *)lpParam + 1));
    }
    else
    {
      DestroyWindow(*((HWND *)lpParam + 1));
      *((_QWORD *)lpParam + 1) = 0;
    }
  }
  return *(_QWORD *)lpParam;
}

```

## disassembly

```asm
0x1800b09d8  push    rbx
0x1800b09da  push    rbp
0x1800b09db  push    rsi
0x1800b09dc  push    rdi
0x1800b09dd  push    r15
0x1800b09df  sub     rsp, 70h
0x1800b09e3  mov     rax, [rsp+98h+arg_30]
0x1800b09eb  mov     rsi, r9
0x1800b09ee  mov     [rcx+18h], rax
0x1800b09f2  mov     ebp, edx
0x1800b09f4  mov     rbx, rcx
0x1800b09f7  call    Windows__Internal___anonymous_namespace___CDimmingWindow___RegisterDimmingWindowClass
0x1800b09fc  mov     rdi, [rsp+98h+arg_28]
0x1800b0a04  lea     rcx, [rsp+98h+var_38]
0x1800b0a09  mov     rax, [rbx+18h]
0x1800b0a0d  mov     rdx, rdi
0x1800b0a10  xor     r8d, r8d
0x1800b0a13  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b0a18  mov     [rsp+98h+lpParam], rbx; lpParam
0x1800b0a1d  lea     r15, __ImageBase
0x1800b0a24  mov     [rsp+98h+hInstance], r15; hInstance
0x1800b0a29  mov     [rsp+98h+hMenu], 0; hMenu
0x1800b0a32  mov     r8d, [rax+4]
0x1800b0a36  mov     r9d, [rax]
0x1800b0a39  mov     edx, [rax+0Ch]
0x1800b0a3c  mov     ecx, [rax+8]
0x1800b0a3f  sub     edx, r8d
0x1800b0a42  sub     ecx, r9d
0x1800b0a45  mov     [rsp+98h+hWndParent], rdi; hWndParent
0x1800b0a4a  mov     [rsp+98h+nHeight], edx; nHeight
0x1800b0a4e  lea     rdx, aShellDim; "Shell_Dim"
0x1800b0a55  mov     [rsp+98h+nWidth], ecx; nWidth
0x1800b0a59  mov     ecx, 80000h; dwExStyle
0x1800b0a5e  mov     [rsp+98h+Y], r8d; Y
0x1800b0a63  xor     r8d, r8d; lpWindowName
0x1800b0a66  mov     [rsp+98h+X], r9d; X
0x1800b0a6b  mov     r9d, 80000000h; dwStyle
0x1800b0a71  call    cs:__imp_CreateWindowExW
0x1800b0a78  nop     dword ptr [rax+rax+00h]
0x1800b0a7d  mov     [rbx+8], rax
0x1800b0a81  test    rax, rax
0x1800b0a84  jz      loc_1800B0B3D
0x1800b0a8a  mov     r8d, 1; hData
0x1800b0a90  lea     rdx, aShellDimmingWi; "Shell_Dimming_Window_Prop"
0x1800b0a97  mov     rcx, rax; hWnd
0x1800b0a9a  call    cs:__imp_SetPropW
0x1800b0aa1  nop     dword ptr [rax+rax+00h]
0x1800b0aa6  mov     r8, rdi
0x1800b0aa9  lea     rdx, [rsp+98h+var_38]
0x1800b0aae  mov     rcx, rbx
0x1800b0ab1  call    Windows__Internal___anonymous_namespace___CDimmingWindow___InvokeCallback
0x1800b0ab6  mov     rax, [rbx+8]
0x1800b0aba  lea     rdx, aShellHostingco; "Shell_HostingContainer"
0x1800b0ac1  mov     r9d, [rsp+98h+dwStyle]; dwStyle
0x1800b0ac9  mov     r8, rsi; lpWindowName
0x1800b0acc  mov     [rsp+98h+lpParam], 0; lpParam
0x1800b0ad5  mov     ecx, ebp; dwExStyle
0x1800b0ad7  mov     [rsp+98h+hInstance], r15; hInstance
0x1800b0adc  mov     [rsp+98h+hMenu], 0; hMenu
0x1800b0ae5  mov     [rsp+98h+hWndParent], rax; hWndParent
0x1800b0aea  mov     eax, 80000000h
0x1800b0aef  mov     [rsp+98h+nHeight], eax; nHeight
0x1800b0af3  mov     [rsp+98h+nWidth], eax; nWidth
0x1800b0af7  mov     [rsp+98h+Y], eax; Y
0x1800b0afb  mov     [rsp+98h+X], eax; X
0x1800b0aff  call    cs:__imp_CreateWindowExW
0x1800b0b06  nop     dword ptr [rax+rax+00h]
0x1800b0b0b  mov     [rbx], rax
0x1800b0b0e  test    rax, rax
0x1800b0b11  jz      short loc_1800B0B25
0x1800b0b13  mov     r8, [rbx+8]
0x1800b0b17  lea     rcx, [rbx+28h]
0x1800b0b1b  mov     rdx, rdi
0x1800b0b1e  call    Windows__Internal___anonymous_namespace___CWindowWaiter__Wait
0x1800b0b23  jmp     short loc_1800B0B3D
0x1800b0b25  mov     rcx, [rbx+8]; hWnd
0x1800b0b29  call    cs:__imp_DestroyWindow
0x1800b0b30  nop     dword ptr [rax+rax+00h]
0x1800b0b35  mov     qword ptr [rbx+8], 0
0x1800b0b3d  mov     rax, [rbx]
0x1800b0b40  add     rsp, 70h
0x1800b0b44  pop     r15
0x1800b0b46  pop     rdi
0x1800b0b47  pop     rsi
0x1800b0b48  pop     rbp
0x1800b0b49  pop     rbx
0x1800b0b4a  retn
```
