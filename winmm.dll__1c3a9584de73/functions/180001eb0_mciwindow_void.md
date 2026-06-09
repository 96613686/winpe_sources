# mciwindow(void *)

- ea: `0x180001eb0`
- end: `0x1800020ca`
- name: `?mciwindow@@YAXPEAX@Z`
- size: `538`
- prototype: `ULONG __stdcall(PVOID Parameter)`
- caller_count: `0`
- callee_count: `4`
- tags: `installer_update, broker_com_uri`

## callees

- `0x180001eb0`
- `0x1800020d0`
- `0x18000b1f8`
- `0x180015e44`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180001f5c`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180001f5c`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadPriority` at `0x180001ef4`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadPriority` at `0x180001ef4`
- `api-ms-win-core-processthreads-l1-1-0!ExitThread` at `0x180001f83`
- `api-ms-win-core-processthreads-l1-1-0!ExitThread` at `0x180001f83`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180001ee6`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180001ee6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002048`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002048`
- `ext-ms-win-ntuser-message-l1-1-0!DispatchMessageA` at `0x180002025`
- `ext-ms-win-ntuser-message-l1-1-0!DispatchMessageA` at `0x180002025`
- `ext-ms-win-ntuser-message-l1-1-0!GetMessageA` at `0x180001fbb`
- `ext-ms-win-ntuser-message-l1-1-0!GetMessageA` at `0x180001ffd`
- `ext-ms-win-ntuser-message-l1-1-0!GetMessageA` at `0x180001fbb`
- `ext-ms-win-ntuser-message-l1-1-0!GetMessageA` at `0x180001ffd`
- `ext-ms-win-ntuser-windowclass-l1-1-0!UnregisterClassA` at `0x180002079`
- `ext-ms-win-ntuser-windowclass-l1-1-0!UnregisterClassA` at `0x180002079`
- `ext-ms-win-ntuser-window-l1-1-0!DestroyWindow` at `0x180002015`
- `ext-ms-win-ntuser-window-l1-1-0!DestroyWindow` at `0x180002015`
- `ext-ms-win-ntuser-window-l1-1-0!CreateWindowExA` at `0x180001f3c`
- `ext-ms-win-ntuser-window-l1-1-0!CreateWindowExA` at `0x180001f3c`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x180001f69`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x180001f69`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x180001f7b`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x180001f7b`

## string_xrefs

- `0x180001f01`: `MCI command handling window`

## pseudocode

```c
_BOOL8 __fastcall mciwindow(PVOID Parameter)
{
  _BOOL8 result; // rax
  int v3; // ebx
  HANDLE CurrentThread; // rax
  __int64 v5; // rdx
  __int64 v6; // r8
  HWND v7; // rcx
  DWORD LastError; // eax
  tagMSG Msg; // [rsp+60h] [rbp-38h] BYREF

  result = LoadWINMM();
  if ( result )
  {
    v3 = 1;
    CurrentThread = GetCurrentThread();
    SetThreadPriority(CurrentThread, 2);
    hwndNotify = CreateWindowExA(0, (LPCSTR)0x2B, mciWndName, 0, 0, 0, 0, 0, HWND_MESSAGE, 0, ghInst, 0);
    if ( !hwndNotify )
    {
      if ( WPP_GLOBAL_Control != (LPCWSTR)&WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400000) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        LastError = GetLastError();
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 27, WPP_c5fb3da3b9933c3192700b6086acf07d_Traceguids, LastError);
      }
      UnregisterClassA((LPCSTR)0x2B, ghInst);
      v3 = 0;
    }
    SetEvent(Parameter);
    CoInitializeEx(0, 2u);
    if ( v3 )
    {
      memset(&Msg, 0, sizeof(Msg));
      while ( GetMessageA(&Msg, 0, 0, 0) )
      {
        if ( WPP_GLOBAL_Control != (LPCWSTR)&WPP_GLOBAL_Control
          && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400000) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
        {
          WPP_SF_DqPP(*((_QWORD *)WPP_GLOBAL_Control + 2), v5, v6, Msg.message, Msg.hwnd, Msg.wParam, Msg.lParam);
        }
        if ( Msg.hwnd )
          DispatchMessageA(&Msg);
      }
      v7 = hwndNotify;
      hwndNotify = 0;
      DestroyWindow(v7);
    }
    CoUninitialize();
    ExitThread(0);
  }
  return result;
}

```

## disassembly

```asm
0x180001eb0  push    rdi
0x180001eb2  sub     rsp, 90h
0x180001eb9  mov     rdi, rcx
0x180001ebc  call    LoadWINMM
0x180001ec1  test    eax, eax
0x180001ec3  jz      loc_1800020C1
0x180001ec9  mov     [rsp+98h+arg_0], rbx
0x180001ed1  mov     ebx, 1
0x180001ed6  mov     [rsp+98h+arg_8], rbp
0x180001ede  mov     [rsp+98h+arg_10], rsi
0x180001ee6  call    cs:__imp_GetCurrentThread
0x180001eec  mov     rcx, rax; hThread
0x180001eef  mov     edx, 2; nPriority
0x180001ef4  call    cs:__imp_SetThreadPriority
0x180001efa  mov     rax, cs:ghInst
0x180001f01  lea     r8, ?mciWndName@@3PADA; "MCI command handling window"
0x180001f08  xor     ebp, ebp
0x180001f0a  xor     r9d, r9d; dwStyle
0x180001f0d  mov     [rsp+98h+lpParam], rbp; lpParam
0x180001f12  mov     edx, 2Bh ; '+'; lpClassName
0x180001f17  mov     [rsp+98h+hInstance], rax; hInstance
0x180001f1c  xor     ecx, ecx; dwExStyle
0x180001f1e  mov     [rsp+98h+hMenu], rbp; hMenu
0x180001f23  mov     [rsp+98h+hWndParent], 0FFFFFFFFFFFFFFFDh; hWndParent
0x180001f2c  mov     [rsp+98h+nHeight], ebp; nHeight
0x180001f30  mov     [rsp+98h+nWidth], ebp; nWidth
0x180001f34  mov     [rsp+98h+Y], ebp; Y
0x180001f38  mov     [rsp+98h+X], ebp; X
0x180001f3c  call    cs:__imp_CreateWindowExA
0x180001f42  mov     cs:hwndNotify, rax
0x180001f49  lea     rsi, WPP_GLOBAL_Control
0x180001f50  test    rax, rax
0x180001f53  jz      loc_18000202D
0x180001f59  mov     rcx, rdi; hEvent
0x180001f5c  call    cs:__imp_SetEvent
0x180001f62  mov     edx, 2; dwCoInit
0x180001f67  xor     ecx, ecx; pvReserved
0x180001f69  call    cs:__imp_CoInitializeEx
0x180001f6f  test    ebx, ebx
0x180001f71  mov     rbx, [rsp+98h+arg_0]
0x180001f79  jnz     short loc_180001F99
0x180001f7b  call    cs:__imp_CoUninitialize
0x180001f81  xor     ecx, ecx; dwExitCode
0x180001f83  call    cs:__imp_ExitThread
0x180001f89  mov     rsi, [rsp+98h+arg_10]
0x180001f91  mov     rbp, [rsp+98h+arg_8]
0x180001f99  xorps   xmm0, xmm0
0x180001f9c  lea     rcx, [rsp+98h+Msg]; lpMsg
0x180001fa1  xor     r9d, r9d; wMsgFilterMax
0x180001fa4  xor     r8d, r8d; wMsgFilterMin
0x180001fa7  xor     edx, edx; hWnd
0x180001fa9  movups  xmmword ptr [rsp+98h+Msg.hwnd], xmm0
0x180001fae  movups  xmmword ptr [rsp+98h+Msg.wParam], xmm0
0x180001fb3  movups  xmmword ptr [rsp+98h+Msg.time], xmm0
0x180001fbb  call    cs:__imp_GetMessageA
0x180001fc1  test    eax, eax
0x180001fc3  jz      short loc_180002007
0x180001fc5  nop     word ptr [rax+rax+00000000h]
0x180001fd0  mov     rcx, cs:WPP_GLOBAL_Control
0x180001fd7  cmp     rcx, rsi
0x180001fda  jz      short loc_180001FE9
0x180001fdc  test    dword ptr [rcx+1Ch], 400000h
0x180001fe3  jnz     loc_180002086
0x180001fe9  cmp     [rsp+98h+Msg.hwnd], rbp
0x180001fee  jnz     short loc_180002020
0x180001ff0  xor     r9d, r9d; wMsgFilterMax
0x180001ff3  lea     rcx, [rsp+98h+Msg]; lpMsg
0x180001ff8  xor     r8d, r8d; wMsgFilterMin
0x180001ffb  xor     edx, edx; hWnd
0x180001ffd  call    cs:__imp_GetMessageA
0x180002003  test    eax, eax
0x180002005  jnz     short loc_180001FD0
0x180002007  mov     rcx, cs:hwndNotify; hWnd
0x18000200e  mov     cs:hwndNotify, rbp
0x180002015  call    cs:__imp_DestroyWindow
0x18000201b  jmp     loc_180001F7B
0x180002020  lea     rcx, [rsp+98h+Msg]; lpMsg
0x180002025  call    cs:__imp_DispatchMessageA
0x18000202b  jmp     short loc_180001FF0
0x18000202d  mov     rax, cs:WPP_GLOBAL_Control
0x180002034  cmp     rax, rsi
0x180002037  jz      short loc_18000206D
0x180002039  test    dword ptr [rax+1Ch], 400000h
0x180002040  jz      short loc_18000206D
0x180002042  cmp     byte ptr [rax+19h], 2
0x180002046  jb      short loc_18000206D
0x180002048  call    cs:__imp_GetLastError
0x18000204e  mov     rcx, cs:WPP_GLOBAL_Control
0x180002055  lea     r8, WPP_c5fb3da3b9933c3192700b6086acf07d_Traceguids
0x18000205c  mov     edx, 1Bh
0x180002061  mov     r9d, eax
0x180002064  mov     rcx, [rcx+10h]
0x180002068  call    WPP_SF_d
0x18000206d  mov     rdx, cs:ghInst; hInstance
0x180002074  mov     ecx, 2Bh ; '+'; lpClassName
0x180002079  call    cs:__imp_UnregisterClassA
0x18000207f  mov     ebx, ebp
0x180002081  jmp     loc_180001F59
0x180002086  cmp     byte ptr [rcx+19h], 5
0x18000208a  jb      loc_180001FE9
0x180002090  mov     rax, [rsp+98h+Msg.lParam]
0x180002095  mov     r9d, [rsp+98h+Msg.message]
0x18000209a  mov     rcx, [rcx+10h]
0x18000209e  mov     qword ptr [rsp+98h+nWidth], rax
0x1800020a3  mov     rax, [rsp+98h+Msg.wParam]
0x1800020a8  mov     qword ptr [rsp+98h+Y], rax
0x1800020ad  mov     rax, [rsp+98h+Msg.hwnd]
0x1800020b2  mov     qword ptr [rsp+98h+X], rax
0x1800020b7  call    WPP_SF_DqPP
0x1800020bc  jmp     loc_180001FE9
0x1800020c1  add     rsp, 90h
0x1800020c8  pop     rdi
0x1800020c9  retn
```
