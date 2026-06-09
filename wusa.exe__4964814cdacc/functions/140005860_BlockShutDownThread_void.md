# BlockShutDownThread(void *)

- ea: `0x140005860`
- end: `0x140005b19`
- name: `?BlockShutDownThread@@YAKPEAX@Z`
- size: `697`
- prototype: `ULONG __stdcall(PVOID Parameter)`
- caller_count: `0`
- callee_count: `4`
- tags: `installer_update`

## callees

- `0x140001a63`
- `0x140005860`
- `0x14000e280`
- `0x140013490`

## import_xrefs

- `KERNEL32!LocalFree` at `0x140005b04`
- `KERNEL32!LocalFree` at `0x140005b04`
- `KERNEL32!GetLastError` at `0x1400058cf`
- `KERNEL32!GetLastError` at `0x14000595a`
- `KERNEL32!GetLastError` at `0x140005994`
- `KERNEL32!GetLastError` at `0x1400059ca`
- `KERNEL32!GetLastError` at `0x140005a66`
- `KERNEL32!GetLastError` at `0x140005a9d`
- `KERNEL32!GetLastError` at `0x1400058cf`
- `KERNEL32!GetLastError` at `0x14000595a`
- `KERNEL32!GetLastError` at `0x140005994`
- `KERNEL32!GetLastError` at `0x1400059ca`
- `KERNEL32!GetLastError` at `0x140005a66`
- `KERNEL32!GetLastError` at `0x140005a9d`
- `USER32!CreateWindowExW` at `0x140005948`
- `USER32!CreateWindowExW` at `0x140005948`
- `USER32!PeekMessageW` at `0x140005a27`
- `USER32!PeekMessageW` at `0x140005a27`
- `USER32!MsgWaitForMultipleObjects` at `0x140005a45`
- `USER32!MsgWaitForMultipleObjects` at `0x140005a45`
- `USER32!RegisterClassExW` at `0x1400058c2`
- `USER32!RegisterClassExW` at `0x1400058c2`
- `USER32!DestroyWindow` at `0x140005a93`
- `USER32!DestroyWindow` at `0x140005a93`
- `USER32!ShutdownBlockReasonDestroy` at `0x140005a5c`
- `USER32!ShutdownBlockReasonDestroy` at `0x140005a5c`
- `USER32!ShutdownBlockReasonCreate` at `0x14000598a`
- `USER32!ShutdownBlockReasonCreate` at `0x14000598a`
- `USER32!DispatchMessageW` at `0x140005a11`
- `USER32!DispatchMessageW` at `0x140005a11`
- `USER32!TranslateMessage` at `0x140005a07`
- `USER32!TranslateMessage` at `0x140005a07`

## string_xrefs

- `0x1400058f2`: `BlockShutDownThread`
- `0x1400059ed`: `BlockShutDownThread`
- `0x140005a7b`: `BlockShutDownThread`
- `0x140005ab2`: `BlockShutDownThread`
- `0x140005af0`: `BlockShutDownThread`
- `0x14000596f`: `Failed to create window of progress bar`
- `0x1400059a9`: `Failed. ShutdownBlockReasonCreate returned false.`

## pseudocode

```c
__int64 __fastcall BlockShutDownThread(PVOID Parameter)
{
  signed int LastError; // eax
  signed int v2; // ebx
  const char *v3; // r8
  __int64 v4; // rdx
  HWND Window; // rax
  signed int v6; // eax
  signed int v7; // eax
  signed int v8; // eax
  DWORD v9; // eax
  DWORD v10; // eax
  DWORD v11; // eax
  HLOCAL v12; // rdi
  MSG Msg; // [rsp+60h] [rbp-49h] BYREF
  WNDCLASSEXW v15; // [rsp+90h] [rbp-19h] BYREF
  HLOCAL hMem; // [rsp+118h] [rbp+6Fh] BYREF

  memset(&Msg, 0, sizeof(Msg));
  memset_0(&v15, 0, sizeof(v15));
  v15.cbSize = 80;
  v15.lpfnWndProc = (WNDPROC)BlockShutDownWindowProc;
  v15.hInstance = _Module;
  v15.style = 3;
  v15.lpszClassName = L"WusaHidden";
  if ( !RegisterClassExW(&v15) )
  {
    LastError = GetLastError();
    v2 = LastError;
    if ( LastError > 0 )
      v2 = (unsigned __int16)LastError | 0x80070000;
    v3 = "Failed to register window class";
    v4 = 196;
LABEL_5:
    if ( v2 >= 0 )
      v2 = -2147467259;
    WusaLogDebugEventA(L"BlockShutDownThread", v4, v3);
    goto LABEL_29;
  }
  Window = CreateWindowExW(0, L"WusaHidden", lpWindowName, 0x80000000, 0, 0, 0, 0, 0, 0, _Module, 0);
  hWnd = Window;
  if ( !Window )
  {
    v6 = GetLastError();
    v2 = v6;
    if ( v6 > 0 )
      v2 = (unsigned __int16)v6 | 0x80070000;
    v3 = "Failed to create window of progress bar";
    v4 = 208;
    goto LABEL_5;
  }
  if ( !ShutdownBlockReasonCreate(Window, &pwszReason) )
  {
    v7 = GetLastError();
    v2 = v7;
    if ( v7 > 0 )
      v2 = (unsigned __int16)v7 | 0x80070000;
    v3 = "Failed. ShutdownBlockReasonCreate returned false.";
    v4 = 212;
    goto LABEL_5;
  }
  while ( 1 )
  {
    v9 = MsgWaitForMultipleObjects(1u, &pHandles, 0, 0xFFFFFFFF, 0x1CFFu);
    if ( !v9 )
    {
      v2 = 0;
      goto LABEL_27;
    }
    if ( v9 != 1 )
      break;
    while ( PeekMessageW(&Msg, 0, 0, 0, 1u) )
    {
      TranslateMessage(&Msg);
      DispatchMessageW(&Msg);
    }
  }
  v8 = GetLastError();
  v2 = v8;
  if ( v8 > 0 )
    v2 = (unsigned __int16)v8 | 0x80070000;
  if ( v2 >= 0 )
    v2 = -2147467259;
  WusaLogDebugEventA(L"BlockShutDownThread", 242, "Failed. Unexpected return from MsgWaitForMultipleObjects()");
LABEL_27:
  if ( !ShutdownBlockReasonDestroy(hWnd) )
  {
    v10 = GetLastError();
    WusaLogDebugEventA(
      L"BlockShutDownThread",
      255,
      "Failed. ShutdownBlockReasonDestroy returns false with error code %u",
      v10);
  }
LABEL_29:
  if ( hWnd )
  {
    if ( !DestroyWindow(hWnd) )
    {
      v11 = GetLastError();
      WusaLogDebugEventA(
        L"BlockShutDownThread",
        264,
        "Warning. Failure returned by DestroyWindow() with error code %d",
        v11);
    }
    hWnd = 0;
  }
  if ( v2 < 0 )
  {
    hMem = 0;
    WusaGetErrorMessage(v2, (unsigned __int16 **)&hMem);
    v12 = hMem;
    WusaLogDebugEventA(L"BlockShutDownThread", 270, "Exit with error code 0X%x (%ls)", v2, (const wchar_t *)hMem);
    if ( v12 )
      LocalFree(v12);
  }
  return (unsigned __int16)v2;
}

```

## disassembly

```asm
0x140005860  push    rbp
0x140005862  push    rbx
0x140005863  push    rsi
0x140005864  push    rdi
0x140005865  lea     rbp, [rsp-3Fh]
0x14000586a  sub     rsp, 0E8h
0x140005871  xorps   xmm0, xmm0
0x140005874  lea     rcx, [rbp+57h+var_70]; void *
0x140005878  mov     ebx, 50h ; 'P'
0x14000587d  xor     edx, edx; Val
0x14000587f  mov     r8d, ebx; Size
0x140005882  movups  xmmword ptr [rbp+57h+Msg.hwnd], xmm0
0x140005886  movups  xmmword ptr [rbp+57h+Msg.wParam], xmm0
0x14000588a  movups  xmmword ptr [rbp+57h+Msg.time], xmm0
0x14000588e  call    memset_0
0x140005893  lea     rax, ?BlockShutDownWindowProc@@YA_JPEAUHWND__@@I_K_J@Z; BlockShutDownWindowProc(HWND__ *,uint,unsigned __int64,__int64)
0x14000589a  mov     [rbp+57h+var_70.cbSize], ebx
0x14000589d  mov     [rbp+57h+var_70.lpfnWndProc], rax
0x1400058a1  lea     rbx, ClassName; "WusaHidden"
0x1400058a8  mov     rax, cs:?_Module@@3VAppModule@@A; AppModule _Module
0x1400058af  lea     rcx, [rbp+57h+var_70]; WNDCLASSEXW *
0x1400058b3  mov     [rbp+57h+var_70.hInstance], rax
0x1400058b7  mov     [rbp+57h+var_70.style], 3
0x1400058be  mov     [rbp+57h+var_70.lpszClassName], rbx
0x1400058c2  call    cs:__imp_RegisterClassExW
0x1400058c8  xor     esi, esi
0x1400058ca  test    ax, ax
0x1400058cd  jnz     short loc_14000590B
0x1400058cf  call    cs:__imp_GetLastError
0x1400058d5  mov     ebx, eax
0x1400058d7  test    eax, eax
0x1400058d9  jle     short loc_1400058E4
0x1400058db  movzx   ebx, ax
0x1400058de  or      ebx, 80070000h
0x1400058e4  lea     r8, aFailedToRegist; "Failed to register window class"
0x1400058eb  mov     edx, 0C4h
0x1400058f0  test    ebx, ebx
0x1400058f2  lea     rcx, aBlockshutdownt; "BlockShutDownThread"
0x1400058f9  mov     eax, 80004005h
0x1400058fe  cmovns  ebx, eax
0x140005901  call    WusaLogDebugEventA
0x140005906  jmp     loc_140005A87
0x14000590b  mov     rax, cs:?_Module@@3VAppModule@@A; AppModule _Module
0x140005912  mov     r9d, 80000000h; dwStyle
0x140005918  mov     r8, cs:lpWindowName; lpWindowName
0x14000591f  mov     rdx, rbx; lpClassName
0x140005922  mov     [rsp+100h+lpParam], rsi; lpParam
0x140005927  xor     ecx, ecx; dwExStyle
0x140005929  mov     [rsp+100h+hInstance], rax; hInstance
0x14000592e  mov     [rsp+100h+hMenu], rsi; hMenu
0x140005933  mov     [rsp+100h+hWndParent], rsi; hWndParent
0x140005938  mov     [rsp+100h+nHeight], esi; nHeight
0x14000593c  mov     [rsp+100h+nWidth], esi; nWidth
0x140005940  mov     [rsp+100h+Y], esi; Y
0x140005944  mov     [rsp+100h+X], esi; X
0x140005948  call    cs:__imp_CreateWindowExW
0x14000594e  mov     cs:hWnd, rax
0x140005955  test    rax, rax
0x140005958  jnz     short loc_140005980
0x14000595a  call    cs:__imp_GetLastError
0x140005960  mov     ebx, eax
0x140005962  test    eax, eax
0x140005964  jle     short loc_14000596F
0x140005966  movzx   ebx, ax
0x140005969  or      ebx, 80070000h
0x14000596f  lea     r8, aFailedToCreate_1; "Failed to create window of progress bar"
0x140005976  mov     edx, 0D0h
0x14000597b  jmp     loc_1400058F0
0x140005980  lea     rdx, pwszReason; pwszReason
0x140005987  mov     rcx, rax; hWnd
0x14000598a  call    cs:__imp_ShutdownBlockReasonCreate
0x140005990  test    eax, eax
0x140005992  jnz     short loc_1400059BA
0x140005994  call    cs:__imp_GetLastError
0x14000599a  mov     ebx, eax
0x14000599c  test    eax, eax
0x14000599e  jle     short loc_1400059A9
0x1400059a0  movzx   ebx, ax
0x1400059a3  or      ebx, 80070000h
0x1400059a9  lea     r8, aFailedShutdown_0; "Failed. ShutdownBlockReasonCreate retur"...
0x1400059b0  mov     edx, 0D4h
0x1400059b5  jmp     loc_1400058F0
0x1400059ba  mov     edi, 1CFFh
0x1400059bf  mov     ebx, 1
0x1400059c4  jmp     short loc_140005A31
0x1400059c6  cmp     eax, ebx
0x1400059c8  jz      short loc_140005A17
0x1400059ca  call    cs:__imp_GetLastError
0x1400059d0  mov     ebx, eax
0x1400059d2  test    eax, eax
0x1400059d4  jle     short loc_1400059DF
0x1400059d6  movzx   ebx, ax
0x1400059d9  or      ebx, 80070000h
0x1400059df  test    ebx, ebx
0x1400059e1  lea     r8, aFailedUnexpect; "Failed. Unexpected return from MsgWaitF"...
0x1400059e8  mov     eax, 80004005h
0x1400059ed  lea     rcx, aBlockshutdownt; "BlockShutDownThread"
0x1400059f4  mov     edx, 0F2h
0x1400059f9  cmovns  ebx, eax
0x1400059fc  call    WusaLogDebugEventA
0x140005a01  jmp     short loc_140005A55
0x140005a03  lea     rcx, [rbp+57h+Msg]; lpMsg
0x140005a07  call    cs:__imp_TranslateMessage
0x140005a0d  lea     rcx, [rbp+57h+Msg]; lpMsg
0x140005a11  call    cs:__imp_DispatchMessageW
0x140005a17  xor     r9d, r9d; wMsgFilterMax
0x140005a1a  mov     [rsp+100h+X], ebx; wRemoveMsg
0x140005a1e  xor     r8d, r8d; wMsgFilterMin
0x140005a21  lea     rcx, [rbp+57h+Msg]; lpMsg
0x140005a25  xor     edx, edx; hWnd
0x140005a27  call    cs:__imp_PeekMessageW
0x140005a2d  test    eax, eax
0x140005a2f  jnz     short loc_140005A03
0x140005a31  or      r9d, 0FFFFFFFFh; dwMilliseconds
0x140005a35  mov     [rsp+100h+X], edi; dwWakeMask
0x140005a39  xor     r8d, r8d; fWaitAll
0x140005a3c  lea     rdx, pHandles; pHandles
0x140005a43  mov     ecx, ebx; nCount
0x140005a45  call    cs:__imp_MsgWaitForMultipleObjects
0x140005a4b  test    eax, eax
0x140005a4d  jnz     loc_1400059C6
0x140005a53  mov     ebx, esi
0x140005a55  mov     rcx, cs:hWnd; hWnd
0x140005a5c  call    cs:__imp_ShutdownBlockReasonDestroy
0x140005a62  test    eax, eax
0x140005a64  jnz     short loc_140005A87
0x140005a66  call    cs:__imp_GetLastError
0x140005a6c  lea     r8, aFailedShutdown; "Failed. ShutdownBlockReasonDestroy retu"...
0x140005a73  mov     edx, 0FFh
0x140005a78  mov     r9d, eax
0x140005a7b  lea     rcx, aBlockshutdownt; "BlockShutDownThread"
0x140005a82  call    WusaLogDebugEventA
0x140005a87  mov     rcx, cs:hWnd; hWnd
0x140005a8e  test    rcx, rcx
0x140005a91  jz      short loc_140005AC5
0x140005a93  call    cs:__imp_DestroyWindow
0x140005a99  test    eax, eax
0x140005a9b  jnz     short loc_140005ABE
0x140005a9d  call    cs:__imp_GetLastError
0x140005aa3  lea     r8, aWarningFailure_0; "Warning. Failure returned by DestroyWin"...
0x140005aaa  mov     edx, 108h
0x140005aaf  mov     r9d, eax
0x140005ab2  lea     rcx, aBlockshutdownt; "BlockShutDownThread"
0x140005ab9  call    WusaLogDebugEventA
0x140005abe  mov     cs:hWnd, rsi
0x140005ac5  test    ebx, ebx
0x140005ac7  jns     short loc_140005B0A
0x140005ac9  lea     rdx, [rbp+57h+hMem]; unsigned __int16 **
0x140005acd  mov     [rbp+57h+hMem], rsi
0x140005ad1  mov     ecx, ebx; dwMessageId
0x140005ad3  call    ?WusaGetErrorMessage@@YAJKPEAPEAG@Z; WusaGetErrorMessage(ulong,ushort * *)
0x140005ad8  mov     rdi, [rbp+57h+hMem]
0x140005adc  lea     r8, aExitWithErrorC; "Exit with error code 0X%x (%ls)"
0x140005ae3  mov     r9d, ebx
0x140005ae6  mov     qword ptr [rsp+100h+X], rdi
0x140005aeb  mov     edx, 10Eh
0x140005af0  lea     rcx, aBlockshutdownt; "BlockShutDownThread"
0x140005af7  call    WusaLogDebugEventA
0x140005afc  test    rdi, rdi
0x140005aff  jz      short loc_140005B0A
0x140005b01  mov     rcx, rdi; hMem
0x140005b04  call    cs:__imp_LocalFree
0x140005b0a  movzx   eax, bx
0x140005b0d  add     rsp, 0E8h
0x140005b14  pop     rdi
0x140005b15  pop     rsi
0x140005b16  pop     rbx
0x140005b17  pop     rbp
0x140005b18  retn
```
