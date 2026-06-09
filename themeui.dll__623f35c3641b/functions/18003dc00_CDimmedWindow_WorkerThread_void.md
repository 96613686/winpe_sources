# CDimmedWindow::WorkerThread(void *)

- ea: `0x18003dc00`
- end: `0x18003de5c`
- name: `?WorkerThread@CDimmedWindow@@CAKPEAX@Z`
- size: `604`
- prototype: `ULONG __stdcall(PVOID Parameter)`
- caller_count: `0`
- callee_count: `6`
- tags: `registry_config, installer_update, broker_com_uri`

## callees

- `0x180030e2c`
- `0x1800358c0`
- `0x18003d650`
- `0x18003d774`
- `0x18003dbb8`
- `0x18003dc00`

## import_xrefs

- `SHCORE!__imp_SHRegGetBoolValueFromHKCUHKLM` at `0x18003dc73`
- `SHCORE!__imp_SHRegGetBoolValueFromHKCUHKLM` at `0x18003dc73`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18003dc36`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18003dc36`
- `USER32!TranslateMessage` at `0x18003ddbb`
- `USER32!TranslateMessage` at `0x18003ddbb`
- `USER32!DispatchMessageW` at `0x18003ddc5`
- `USER32!DispatchMessageW` at `0x18003ddc5`
- `USER32!SystemParametersInfoW` at `0x18003dc4a`
- `USER32!SystemParametersInfoW` at `0x18003dc4a`
- `USER32!GetSystemMetrics` at `0x18003dc95`
- `USER32!GetSystemMetrics` at `0x18003dca2`
- `USER32!GetSystemMetrics` at `0x18003dcb0`
- `USER32!GetSystemMetrics` at `0x18003dcbe`
- `USER32!GetSystemMetrics` at `0x18003dc95`
- `USER32!GetSystemMetrics` at `0x18003dca2`
- `USER32!GetSystemMetrics` at `0x18003dcb0`
- `USER32!GetSystemMetrics` at `0x18003dcbe`
- `USER32!CreateWindowInBand` at `0x18003dd15`
- `USER32!CreateWindowInBand` at `0x18003dd15`
- `USER32!CreateWindowExW` at `0x18003dd61`
- `USER32!CreateWindowExW` at `0x18003dd61`
- `USER32!GetMessageW` at `0x18003ddd7`
- `USER32!GetMessageW` at `0x18003ddd7`

## pseudocode

```c
__int64 __fastcall CDimmedWindow::WorkerThread(HINSTANCE *Parameter)
{
  BOOL v2; // esi
  bool v3; // di
  BOOL BoolValueFromHKCUHKLM; // eax
  int X; // esi
  int Y; // r14d
  int nWidth; // r15d
  int nHeight; // r12d
  HWND WindowInBand; // rdi
  int v10; // ecx
  int v11; // r8d
  int MessageW; // eax
  int v13; // ecx
  int v14; // r8d
  unsigned int v15; // edx
  int pvParam; // [rsp+70h] [rbp-19h] BYREF
  MSG Msg; // [rsp+78h] [rbp-11h] BYREF
  _BYTE v19[16]; // [rsp+A8h] [rbp+1Fh] BYREF

  pvParam = 0;
  v2 = IsDebuggerPresent();
  v3 = !SystemParametersInfoW(0x46u, 0, &pvParam, 0) || !pvParam;
  BoolValueFromHKCUHKLM = SHRegGetBoolValueFromHKCUHKLM(
                            L"Software\\Microsoft\\Windows\\CurrentVersion\\Themes",
                            L"NoCoverWindow",
                            0);
  if ( v2 || !v3 || BoolValueFromHKCUHKLM )
  {
    WindowInBand = 0;
    CDimmedWindow::Release((CDimmedWindow *)Parameter);
  }
  else
  {
    X = GetSystemMetrics(76);
    Y = GetSystemMetrics(77);
    nWidth = GetSystemMetrics(78);
    nHeight = GetSystemMetrics(79);
    WindowInBand = (HWND)CreateWindowInBand(
                           8,
                           L"CoverWindowClass",
                           0,
                           2281701376LL,
                           X,
                           Y,
                           nWidth,
                           nHeight,
                           0,
                           0,
                           Parameter[1],
                           Parameter,
                           7);
    if ( !WindowInBand )
      WindowInBand = CreateWindowExW(
                       8u,
                       L"CoverWindowClass",
                       0,
                       0x88000000,
                       X,
                       Y,
                       nWidth,
                       nHeight,
                       0,
                       0,
                       Parameter[1],
                       Parameter);
    CDimmedWindow::Release((CDimmedWindow *)Parameter);
    if ( WindowInBand )
    {
      if ( (Microsoft_Windows_ThemeUIEnableBits & 1) != 0 )
        McGenEventWrite_EtwEventWriteTransfer(v10, (unsigned int)DimmedWindow_Start, v11, 1, (__int64)v19);
      memset(&Msg, 0, sizeof(Msg));
      while ( 1 )
      {
        MessageW = GetMessageW(&Msg, 0, 0, 0);
        if ( !MessageW || MessageW == -1 )
          break;
        TranslateMessage(&Msg);
        DispatchMessageW(&Msg);
      }
      if ( (Microsoft_Windows_ThemeUIEnableBits & 1) != 0 )
        McGenEventWrite_EtwEventWriteTransfer(v13, (unsigned int)DimmedWindow_Stop, v14, 1, (__int64)v19);
    }
  }
  CDimmedWindow::Destroy((CDimmedWindow *)Parameter);
  if ( !*(_DWORD *)Parameter && Parameter )
    CDimmedWindow::`scalar deleting destructor'((CDimmedWindow *)Parameter, v15);
  return WindowInBand == 0 ? 0x80004005 : 0;
}

```

## disassembly

```asm
0x18003dc00  mov     [rsp-8+arg_8], rbx
0x18003dc05  mov     [rsp-8+arg_10], rsi
0x18003dc0a  push    rbp
0x18003dc0b  push    rdi
0x18003dc0c  push    r12
0x18003dc0e  push    r14
0x18003dc10  push    r15
0x18003dc12  lea     rbp, [rsp-37h]
0x18003dc17  sub     rsp, 0C0h
0x18003dc1e  mov     rax, cs:__security_cookie
0x18003dc25  xor     rax, rsp
0x18003dc28  mov     [rbp+57h+var_28], rax
0x18003dc2c  mov     rbx, rcx
0x18003dc2f  mov     [rbp+57h+pvParam], 0
0x18003dc36  call    cs:__imp_IsDebuggerPresent
0x18003dc3c  xor     edx, edx; uiParam
0x18003dc3e  lea     r8, [rbp+57h+pvParam]; pvParam
0x18003dc42  xor     r9d, r9d; fWinIni
0x18003dc45  mov     esi, eax
0x18003dc47  lea     ecx, [rdx+46h]; uiAction
0x18003dc4a  call    cs:__imp_SystemParametersInfoW
0x18003dc50  test    eax, eax
0x18003dc52  jz      short loc_18003DC5F
0x18003dc54  cmp     [rbp+57h+pvParam], 0
0x18003dc58  jz      short loc_18003DC5F
0x18003dc5a  xor     dil, dil
0x18003dc5d  jmp     short loc_18003DC62
0x18003dc5f  mov     dil, 1
0x18003dc62  xor     r8d, r8d; fDefault
0x18003dc65  lea     rdx, aNocoverwindow; "NoCoverWindow"
0x18003dc6c  lea     rcx, pszKey; "Software\\Microsoft\\Windows\\CurrentVe"...
0x18003dc73  call    cs:__imp_SHRegGetBoolValueFromHKCUHKLM
0x18003dc79  test    esi, esi
0x18003dc7b  jnz     loc_18003DE04
0x18003dc81  test    dil, dil
0x18003dc84  jz      loc_18003DE04
0x18003dc8a  test    eax, eax
0x18003dc8c  jnz     loc_18003DE04
0x18003dc92  lea     ecx, [rsi+4Ch]; nIndex
0x18003dc95  call    cs:__imp_GetSystemMetrics
0x18003dc9b  mov     ecx, 4Dh ; 'M'; nIndex
0x18003dca0  mov     esi, eax
0x18003dca2  call    cs:__imp_GetSystemMetrics
0x18003dca8  mov     ecx, 4Eh ; 'N'; nIndex
0x18003dcad  mov     r14d, eax
0x18003dcb0  call    cs:__imp_GetSystemMetrics
0x18003dcb6  mov     ecx, 4Fh ; 'O'; nIndex
0x18003dcbb  mov     r15d, eax
0x18003dcbe  call    cs:__imp_GetSystemMetrics
0x18003dcc4  mov     rcx, [rbx+8]
0x18003dcc8  lea     rdx, aCoverwindowcla; "CoverWindowClass"
0x18003dccf  mov     [rsp+0E0h+var_80], 7
0x18003dcd7  xor     r8d, r8d
0x18003dcda  mov     [rsp+0E0h+lpParam], rbx
0x18003dcdf  mov     r9d, 88000000h
0x18003dce5  mov     [rsp+0E0h+hInstance], rcx
0x18003dcea  mov     r12d, eax
0x18003dced  mov     [rsp+0E0h+hMenu], 0
0x18003dcf6  mov     [rsp+0E0h+hWndParent], 0
0x18003dcff  lea     ecx, [r8+8]
0x18003dd03  mov     [rsp+0E0h+nHeight], eax
0x18003dd07  mov     [rsp+0E0h+nWidth], r15d
0x18003dd0c  mov     [rsp+0E0h+Y], r14d
0x18003dd11  mov     [rsp+0E0h+X], esi
0x18003dd15  call    cs:__imp_CreateWindowInBand
0x18003dd1b  mov     rdi, rax
0x18003dd1e  test    rax, rax
0x18003dd21  jnz     short loc_18003DD6A
0x18003dd23  mov     rax, [rbx+8]
0x18003dd27  lea     rdx, aCoverwindowcla; "CoverWindowClass"
0x18003dd2e  mov     [rsp+0E0h+lpParam], rbx; lpParam
0x18003dd33  lea     ecx, [rdi+8]; dwExStyle
0x18003dd36  mov     [rsp+0E0h+hInstance], rax; hInstance
0x18003dd3b  mov     r9d, 88000000h; dwStyle
0x18003dd41  mov     [rsp+0E0h+hMenu], rdi; hMenu
0x18003dd46  xor     r8d, r8d; lpWindowName
0x18003dd49  mov     [rsp+0E0h+hWndParent], rdi; hWndParent
0x18003dd4e  mov     [rsp+0E0h+nHeight], r12d; nHeight
0x18003dd53  mov     [rsp+0E0h+nWidth], r15d; nWidth
0x18003dd58  mov     [rsp+0E0h+Y], r14d; Y
0x18003dd5d  mov     [rsp+0E0h+X], esi; X
0x18003dd61  call    cs:__imp_CreateWindowExW
0x18003dd67  mov     rdi, rax
0x18003dd6a  mov     rcx, rbx; this
0x18003dd6d  call    ?Release@CDimmedWindow@@QEAAKXZ; CDimmedWindow::Release(void)
0x18003dd72  test    rdi, rdi
0x18003dd75  jz      loc_18003DE0E
0x18003dd7b  mov     esi, 1
0x18003dd80  test    cs:Microsoft_Windows_ThemeUIEnableBits, sil
0x18003dd87  jz      short loc_18003DDA1
0x18003dd89  lea     rax, [rbp+57h+var_38]
0x18003dd8d  mov     r9d, esi
0x18003dd90  lea     rdx, DimmedWindow_Start
0x18003dd97  mov     qword ptr [rsp+0E0h+X], rax
0x18003dd9c  call    McGenEventWrite_EtwEventWriteTransfer
0x18003dda1  xorps   xmm0, xmm0
0x18003dda4  movups  xmmword ptr [rbp+57h+Msg.hwnd], xmm0
0x18003dda8  movups  xmmword ptr [rbp+57h+Msg.wParam], xmm0
0x18003ddac  movups  xmmword ptr [rbp+57h+Msg.time], xmm0
0x18003ddb0  jmp     short loc_18003DDCB
0x18003ddb2  cmp     eax, 0FFFFFFFFh
0x18003ddb5  jz      short loc_18003DDE1
0x18003ddb7  lea     rcx, [rbp+57h+Msg]; lpMsg
0x18003ddbb  call    cs:__imp_TranslateMessage
0x18003ddc1  lea     rcx, [rbp+57h+Msg]; lpMsg
0x18003ddc5  call    cs:__imp_DispatchMessageW
0x18003ddcb  xor     r9d, r9d; wMsgFilterMax
0x18003ddce  lea     rcx, [rbp+57h+Msg]; lpMsg
0x18003ddd2  xor     r8d, r8d; wMsgFilterMin
0x18003ddd5  xor     edx, edx; hWnd
0x18003ddd7  call    cs:__imp_GetMessageW
0x18003dddd  test    eax, eax
0x18003dddf  jnz     short loc_18003DDB2
0x18003dde1  test    cs:Microsoft_Windows_ThemeUIEnableBits, sil
0x18003dde8  jz      short loc_18003DE0E
0x18003ddea  lea     rax, [rbp+57h+var_38]
0x18003ddee  mov     r9d, esi
0x18003ddf1  lea     rdx, DimmedWindow_Stop
0x18003ddf8  mov     qword ptr [rsp+0E0h+X], rax
0x18003ddfd  call    McGenEventWrite_EtwEventWriteTransfer
0x18003de02  jmp     short loc_18003DE0E
0x18003de04  xor     edi, edi
0x18003de06  mov     rcx, rbx; this
0x18003de09  call    ?Release@CDimmedWindow@@QEAAKXZ; CDimmedWindow::Release(void)
0x18003de0e  mov     rcx, rbx; this
0x18003de11  call    ?Destroy@CDimmedWindow@@AEAAXXZ; CDimmedWindow::Destroy(void)
0x18003de16  cmp     dword ptr [rbx], 0
0x18003de19  jnz     short loc_18003DE28
0x18003de1b  test    rbx, rbx
0x18003de1e  jz      short loc_18003DE28
0x18003de20  mov     rcx, rbx; this
0x18003de23  call    ??_GCDimmedWindow@@QEAAPEAXI@Z; CDimmedWindow::`scalar deleting destructor'(uint)
0x18003de28  neg     rdi
0x18003de2b  sbb     eax, eax
0x18003de2d  not     eax
0x18003de2f  and     eax, 80004005h
0x18003de34  mov     rcx, [rbp+57h+var_28]
0x18003de38  xor     rcx, rsp; StackCookie
0x18003de3b  call    __security_check_cookie
0x18003de40  lea     r11, [rsp+0E0h+var_20]
0x18003de48  mov     rbx, [r11+38h]
0x18003de4c  mov     rsi, [r11+40h]
0x18003de50  mov     rsp, r11
0x18003de53  pop     r15
0x18003de55  pop     r14
0x18003de57  pop     r12
0x18003de59  pop     rdi
0x18003de5a  pop     rbp
0x18003de5b  retn
```
