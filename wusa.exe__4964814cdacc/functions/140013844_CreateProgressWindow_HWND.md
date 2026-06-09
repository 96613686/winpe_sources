# CreateProgressWindow(HWND__ * *)

- ea: `0x140013844`
- end: `0x140013a87`
- name: `?CreateProgressWindow@@YAJPEAPEAUHWND__@@@Z`
- size: `579`
- prototype: `__int64 __fastcall(HWND *)`
- caller_count: `1`
- callee_count: `4`
- tags: `installer_update`

## callers

- `0x140006554`

## callees

- `0x140001a63`
- `0x140013490`
- `0x140013844`
- `0x140014910`

## import_xrefs

- `KERNEL32!GetLastError` at `0x1400138ee`
- `KERNEL32!GetLastError` at `0x1400139e0`
- `KERNEL32!GetLastError` at `0x140013a13`
- `KERNEL32!GetLastError` at `0x1400138ee`
- `KERNEL32!GetLastError` at `0x1400139e0`
- `KERNEL32!GetLastError` at `0x140013a13`
- `GDI32!GetStockObject` at `0x1400138ca`
- `GDI32!GetStockObject` at `0x1400138ca`
- `GDI32!GetDeviceCaps` at `0x14001393d`
- `GDI32!GetDeviceCaps` at `0x140013950`
- `GDI32!GetDeviceCaps` at `0x14001393d`
- `GDI32!GetDeviceCaps` at `0x140013950`
- `USER32!CreateWindowExW` at `0x1400139d2`
- `USER32!CreateWindowExW` at `0x1400139d2`
- `USER32!UpdateWindow` at `0x140013a09`
- `USER32!UpdateWindow` at `0x140013a09`
- `USER32!RegisterClassExW` at `0x1400138e3`
- `USER32!RegisterClassExW` at `0x1400138e3`
- `USER32!GetDC` at `0x14001392c`
- `USER32!GetDC` at `0x14001392c`
- `USER32!SendMessageW` at `0x140013a4a`
- `USER32!SendMessageW` at `0x140013a4a`
- `USER32!SystemParametersInfoW` at `0x140013973`
- `USER32!SystemParametersInfoW` at `0x140013973`
- `USER32!LoadCursorW` at `0x1400138bd`
- `USER32!LoadCursorW` at `0x1400138bd`
- `USER32!LoadIconW` at `0x1400138ac`
- `USER32!LoadIconW` at `0x1400138ac`

## string_xrefs

- `0x1400139f5`: `Failed to create window of progress bar`
- `0x140013919`: `CreateProgressWindow`
- `0x140013a28`: `Failed to update progress window after created it.`

## pseudocode

```c
__int64 __fastcall CreateProgressWindow(HWND *a1)
{
  signed int LastError; // eax
  unsigned int v4; // ebx
  const char *v5; // r8
  __int64 v6; // rdx
  HDC DC; // rbx
  int nWidth; // edi
  int DeviceCaps; // eax
  int v10; // kr00_4
  HWND Window; // rax
  HWND v12; // rdi
  signed int v13; // eax
  signed int v14; // eax
  WNDCLASSEXW v15; // [rsp+60h] [rbp-49h] BYREF
  __int128 pvParam; // [rsp+B0h] [rbp+7h] BYREF

  if ( dword_140020188 )
    return 0;
  memset_0(&v15, 0, sizeof(v15));
  v15.lpfnWndProc = (WNDPROC)ProgressWindowProc;
  v15.hInstance = _Module;
  v15.cbSize = 80;
  v15.hIcon = LoadIconW(_Module, (LPCWSTR)0x65);
  v15.hCursor = LoadCursorW(0, (LPCWSTR)0x7F00);
  v15.hbrBackground = (HBRUSH)GetStockObject(5);
  v15.lpszClassName = L"WusaProgress";
  if ( !RegisterClassExW(&v15) )
  {
    LastError = GetLastError();
    v4 = LastError;
    if ( LastError > 0 )
      v4 = (unsigned __int16)LastError | 0x80070000;
    v5 = "Failed to register window class";
    v6 = 369;
LABEL_7:
    if ( (v4 & 0x80000000) == 0 )
      v4 = -2147467259;
    WusaLogDebugEventA(L"CreateProgressWindow", v6, v5);
    return v4;
  }
  DC = GetDC(0);
  nWidth = 4 * GetDeviceCaps(DC, 88);
  DeviceCaps = GetDeviceCaps(DC, 90);
  pvParam = 0;
  v10 = 3 * DeviceCaps;
  LODWORD(DC) = 3 * DeviceCaps / 2;
  SystemParametersInfoW(0x30u, 0, &pvParam, 0);
  Window = CreateWindowExW(
             0,
             L"WusaProgress",
             lpWindowName,
             0x90C00000,
             (DWORD2(pvParam) + (int)pvParam - nWidth) / 2,
             (DWORD1(pvParam) + HIDWORD(pvParam) - (int)DC) / 2,
             nWidth,
             v10 / 2,
             0,
             0,
             _Module,
             0);
  v12 = Window;
  if ( !Window )
  {
    v13 = GetLastError();
    v4 = v13;
    if ( v13 > 0 )
      v4 = (unsigned __int16)v13 | 0x80070000;
    v5 = "Failed to create window of progress bar";
    v6 = 393;
    goto LABEL_7;
  }
  if ( !UpdateWindow(Window) )
  {
    v14 = GetLastError();
    v4 = v14;
    if ( v14 > 0 )
      v4 = (unsigned __int16)v14 | 0x80070000;
    v5 = "Failed to update progress window after created it.";
    v6 = 396;
    goto LABEL_7;
  }
  v4 = 0;
  if ( SendMessageW(v12, 0x402u, 0, 0) )
    WusaLogDebugEventA(L"CreateProgressWindow", 401, "Failed to send message WM_WUA_EXPAND_STARTED to progress window");
  else
    *a1 = v12;
  return v4;
}

```

## disassembly

```asm
0x140013844  push    rbp
0x140013846  push    rbx
0x140013847  push    rsi
0x140013848  push    rdi
0x140013849  push    r14
0x14001384b  push    r15
0x14001384d  lea     rbp, [rsp-2Fh]
0x140013852  sub     rsp, 0D8h
0x140013859  mov     rax, cs:__security_cookie
0x140013860  xor     rax, rsp
0x140013863  mov     [rbp+57h+var_40], rax
0x140013867  xor     r14d, r14d
0x14001386a  mov     rsi, rcx
0x14001386d  cmp     cs:dword_140020188, r14d
0x140013874  jz      short loc_14001387D
0x140013876  xor     eax, eax
0x140013878  jmp     loc_140013A6B
0x14001387d  mov     ebx, 50h ; 'P'
0x140013882  lea     rcx, [rbp+57h+var_A0]; void *
0x140013886  mov     r8d, ebx; Size
0x140013889  xor     edx, edx; Val
0x14001388b  call    memset_0
0x140013890  mov     rcx, cs:?_Module@@3VAppModule@@A; hInstance
0x140013897  lea     rax, ?ProgressWindowProc@@YA_JPEAUHWND__@@I_K_J@Z; ProgressWindowProc(HWND__ *,uint,unsigned __int64,__int64)
0x14001389e  lea     edx, [rbx+15h]; lpIconName
0x1400138a1  mov     [rbp+57h+var_A0.lpfnWndProc], rax
0x1400138a5  mov     [rbp+57h+var_A0.hInstance], rcx
0x1400138a9  mov     [rbp+57h+var_A0.cbSize], ebx
0x1400138ac  call    cs:__imp_LoadIconW
0x1400138b2  mov     edx, 7F00h; lpCursorName
0x1400138b7  xor     ecx, ecx; hInstance
0x1400138b9  mov     [rbp+57h+var_A0.hIcon], rax
0x1400138bd  call    cs:__imp_LoadCursorW
0x1400138c3  lea     ecx, [rbx-4Bh]; i
0x1400138c6  mov     [rbp+57h+var_A0.hCursor], rax
0x1400138ca  call    cs:__imp_GetStockObject
0x1400138d0  lea     r15, aWusaprogress; "WusaProgress"
0x1400138d7  mov     [rbp+57h+var_A0.hbrBackground], rax
0x1400138db  lea     rcx, [rbp+57h+var_A0]; WNDCLASSEXW *
0x1400138df  mov     [rbp+57h+var_A0.lpszClassName], r15
0x1400138e3  call    cs:__imp_RegisterClassExW
0x1400138e9  test    ax, ax
0x1400138ec  jnz     short loc_14001392A
0x1400138ee  call    cs:__imp_GetLastError
0x1400138f4  mov     ebx, eax
0x1400138f6  test    eax, eax
0x1400138f8  jle     short loc_140013903
0x1400138fa  movzx   ebx, ax
0x1400138fd  or      ebx, 80070000h
0x140013903  lea     r8, aFailedToRegist; "Failed to register window class"
0x14001390a  mov     edx, 171h
0x14001390f  test    ebx, ebx
0x140013911  mov     eax, 80004005h
0x140013916  cmovns  ebx, eax
0x140013919  lea     rcx, aCreateprogress; "CreateProgressWindow"
0x140013920  call    WusaLogDebugEventA
0x140013925  jmp     loc_140013A69
0x14001392a  xor     ecx, ecx; hWnd
0x14001392c  call    cs:__imp_GetDC
0x140013932  mov     rcx, rax; hdc
0x140013935  mov     edx, 58h ; 'X'; index
0x14001393a  mov     rbx, rax
0x14001393d  call    cs:__imp_GetDeviceCaps
0x140013943  mov     edx, 5Ah ; 'Z'; index
0x140013948  mov     rcx, rbx; hdc
0x14001394b  mov     edi, eax
0x14001394d  shl     edi, 2
0x140013950  call    cs:__imp_GetDeviceCaps
0x140013956  xorps   xmm0, xmm0
0x140013959  lea     r8, [rbp+57h+pvParam]; pvParam
0x14001395d  xor     r9d, r9d; fWinIni
0x140013960  movups  [rbp+57h+pvParam], xmm0
0x140013964  lea     eax, [rax+rax*2]
0x140013967  cdq
0x140013968  sub     eax, edx
0x14001396a  xor     edx, edx; uiParam
0x14001396c  sar     eax, 1
0x14001396e  mov     ebx, eax
0x140013970  lea     ecx, [rdx+30h]; uiAction
0x140013973  call    cs:__imp_SystemParametersInfoW
0x140013979  mov     r8, cs:?_Module@@3VAppModule@@A; AppModule _Module
0x140013980  mov     r9d, 90C00000h; dwStyle
0x140013986  mov     eax, dword ptr [rbp+57h+pvParam+0Ch]
0x140013989  sub     eax, ebx
0x14001398b  mov     [rsp+100h+lpParam], r14; lpParam
0x140013990  add     eax, dword ptr [rbp+57h+pvParam+4]
0x140013993  cdq
0x140013994  mov     [rsp+100h+hInstance], r8; hInstance
0x140013999  mov     r8, cs:lpWindowName; lpWindowName
0x1400139a0  sub     eax, edx
0x1400139a2  sar     eax, 1
0x1400139a4  mov     ecx, eax
0x1400139a6  mov     [rsp+100h+hMenu], r14; hMenu
0x1400139ab  mov     eax, dword ptr [rbp+57h+pvParam]
0x1400139ae  sub     eax, edi
0x1400139b0  mov     [rsp+100h+hWndParent], r14; hWndParent
0x1400139b5  add     eax, dword ptr [rbp+57h+pvParam+8]
0x1400139b8  cdq
0x1400139b9  mov     [rsp+100h+nHeight], ebx; nHeight
0x1400139bd  sub     eax, edx
0x1400139bf  mov     [rsp+100h+nWidth], edi; nWidth
0x1400139c3  mov     [rsp+100h+Y], ecx; Y
0x1400139c7  mov     rdx, r15; lpClassName
0x1400139ca  sar     eax, 1
0x1400139cc  xor     ecx, ecx; dwExStyle
0x1400139ce  mov     [rsp+100h+X], eax; X
0x1400139d2  call    cs:__imp_CreateWindowExW
0x1400139d8  mov     rdi, rax
0x1400139db  test    rax, rax
0x1400139de  jnz     short loc_140013A06
0x1400139e0  call    cs:__imp_GetLastError
0x1400139e6  mov     ebx, eax
0x1400139e8  test    eax, eax
0x1400139ea  jle     short loc_1400139F5
0x1400139ec  movzx   ebx, ax
0x1400139ef  or      ebx, 80070000h
0x1400139f5  lea     r8, aFailedToCreate_1; "Failed to create window of progress bar"
0x1400139fc  mov     edx, 189h
0x140013a01  jmp     loc_14001390F
0x140013a06  mov     rcx, rdi; hWnd
0x140013a09  call    cs:__imp_UpdateWindow
0x140013a0f  test    eax, eax
0x140013a11  jnz     short loc_140013A39
0x140013a13  call    cs:__imp_GetLastError
0x140013a19  mov     ebx, eax
0x140013a1b  test    eax, eax
0x140013a1d  jle     short loc_140013A28
0x140013a1f  movzx   ebx, ax
0x140013a22  or      ebx, 80070000h
0x140013a28  lea     r8, aFailedToUpdate; "Failed to update progress window after "...
0x140013a2f  mov     edx, 18Ch
0x140013a34  jmp     loc_14001390F
0x140013a39  xor     r9d, r9d; lParam
0x140013a3c  xor     r8d, r8d; wParam
0x140013a3f  mov     edx, 402h; Msg
0x140013a44  mov     rcx, rdi; hWnd
0x140013a47  mov     ebx, r14d
0x140013a4a  call    cs:__imp_SendMessageW
0x140013a50  test    rax, rax
0x140013a53  jz      short loc_140013A66
0x140013a55  lea     r8, aFailedToSendMe; "Failed to send message WM_WUA_EXPAND_ST"...
0x140013a5c  mov     edx, 191h
0x140013a61  jmp     loc_140013919
0x140013a66  mov     [rsi], rdi
0x140013a69  mov     eax, ebx
0x140013a6b  mov     rcx, [rbp+57h+var_40]
0x140013a6f  xor     rcx, rsp; StackCookie
0x140013a72  call    __security_check_cookie
0x140013a77  add     rsp, 0D8h
0x140013a7e  pop     r15
0x140013a80  pop     r14
0x140013a82  pop     rdi
0x140013a83  pop     rsi
0x140013a84  pop     rbx
0x140013a85  pop     rbp
0x140013a86  retn
```
