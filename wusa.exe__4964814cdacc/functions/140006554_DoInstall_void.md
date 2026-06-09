# DoInstall(void)

- ea: `0x140006554`
- end: `0x1400067e9`
- name: `?DoInstall@@YAJXZ`
- size: `661`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `3`
- tags: `installer_update`

## callers

- `0x14000c488`

## callees

- `0x140006554`
- `0x140013490`
- `0x140013844`

## import_xrefs

- `KERNEL32!CloseHandle` at `0x140006778`
- `KERNEL32!CloseHandle` at `0x140006778`
- `KERNEL32!CreateThread` at `0x140006617`
- `KERNEL32!CreateThread` at `0x140006657`
- `KERNEL32!CreateThread` at `0x140006617`
- `KERNEL32!CreateThread` at `0x140006657`
- `KERNEL32!GetExitCodeThread` at `0x140006725`
- `KERNEL32!GetExitCodeThread` at `0x140006725`
- `KERNEL32!GetLastError` at `0x14000659c`
- `KERNEL32!GetLastError` at `0x14000662a`
- `KERNEL32!GetLastError` at `0x14000666a`
- `KERNEL32!GetLastError` at `0x140006747`
- `KERNEL32!GetLastError` at `0x140006798`
- `KERNEL32!GetLastError` at `0x1400067c3`
- `KERNEL32!GetLastError` at `0x14000659c`
- `KERNEL32!GetLastError` at `0x14000662a`
- `KERNEL32!GetLastError` at `0x14000666a`
- `KERNEL32!GetLastError` at `0x140006747`
- `KERNEL32!GetLastError` at `0x140006798`
- `KERNEL32!GetLastError` at `0x1400067c3`
- `USER32!PeekMessageW` at `0x1400066e7`
- `USER32!PeekMessageW` at `0x1400066e7`
- `USER32!MsgWaitForMultipleObjects` at `0x140006707`
- `USER32!MsgWaitForMultipleObjects` at `0x140006707`
- `USER32!DestroyAcceleratorTable` at `0x14000678e`
- `USER32!DestroyAcceleratorTable` at `0x14000678e`
- `USER32!CreateAcceleratorTableW` at `0x140006587`
- `USER32!CreateAcceleratorTableW` at `0x140006587`
- `USER32!TranslateAcceleratorW` at `0x1400066b8`
- `USER32!TranslateAcceleratorW` at `0x1400066b8`
- `USER32!DestroyWindow` at `0x14000673d`
- `USER32!DestroyWindow` at `0x14000673d`
- `USER32!DispatchMessageW` at `0x1400066d0`
- `USER32!DispatchMessageW` at `0x1400066d0`
- `USER32!TranslateMessage` at `0x1400066c6`
- `USER32!TranslateMessage` at `0x1400066c6`

## string_xrefs

- `0x14000663f`: `Failed to create work thread`
- `0x14000667f`: `Failed to create work thread`
- `0x1400065b1`: `Failure to create accelerator key table()`
- `0x14000658d`: `DoInstall`
- `0x1400065e6`: `Failure is returned by CreateProgressWindow()`

## pseudocode

```c
__int64 DoInstall(void)
{
  HACCEL v0; // rdi
  signed int v1; // eax
  signed int ProgressWindow; // ebx
  const char *v3; // r8
  __int64 v4; // rdx
  signed int LastError; // eax
  signed int v6; // eax
  DWORD v7; // eax
  DWORD v8; // eax
  DWORD v9; // eax
  signed int v11; // eax
  struct tagMSG Msg; // [rsp+30h] [rbp-30h] BYREF
  DWORD ExitCode; // [rsp+90h] [rbp+30h] BYREF
  tagACCEL paccel; // [rsp+98h] [rbp+38h] BYREF
  HANDLE pHandles; // [rsp+A0h] [rbp+40h] BYREF

  pHandles = 0;
  *(_DWORD *)&paccel.fVirt = 1769473;
  paccel.cmd = 2;
  v0 = CreateAcceleratorTableW(&paccel, 1);
  if ( v0 )
  {
    ProgressWindow = CreateProgressWindow(&hWndParent);
    if ( ProgressWindow < 0 )
    {
      WusaLogDebugEventA(L"DoInstall", 1547, "Failure is returned by CreateProgressWindow()");
      goto LABEL_29;
    }
    if ( dword_14002017C )
    {
      pHandles = CreateThread(0, 0, (LPTHREAD_START_ROUTINE)UninstallWorker, 0, 0, 0);
      if ( pHandles )
        goto LABEL_25;
      LastError = GetLastError();
      ProgressWindow = LastError;
      if ( LastError > 0 )
        ProgressWindow = (unsigned __int16)LastError | 0x80070000;
      v3 = "Failed to create work thread";
      v4 = 1553;
    }
    else
    {
      pHandles = CreateThread(0, 0, (LPTHREAD_START_ROUTINE)InstallWorker, 0, 0, 0);
      if ( pHandles )
      {
        while ( 1 )
        {
LABEL_25:
          v7 = MsgWaitForMultipleObjects(1u, &pHandles, 0, 0xFFFFFFFF, 0x1CFFu);
          if ( !v7 )
          {
            if ( pHandles )
            {
              ExitCode = 0;
              if ( GetExitCodeThread(pHandles, &ExitCode) )
                ProgressWindow = ExitCode;
            }
            goto LABEL_29;
          }
          if ( v7 != 1 )
            break;
          memset(&Msg, 0, sizeof(Msg));
          while ( PeekMessageW(&Msg, 0, 0, 0, 1u) )
          {
            if ( !TranslateAcceleratorW(hWndParent, v0, &Msg) )
            {
              TranslateMessage(&Msg);
              DispatchMessageW(&Msg);
            }
          }
        }
        v11 = GetLastError();
        ProgressWindow = v11;
        if ( v11 > 0 )
          ProgressWindow = (unsigned __int16)v11 | 0x80070000;
        v3 = "Failed. Unexpected return from MsgWaitForMultipleObjects()";
        v4 = 1591;
      }
      else
      {
        v6 = GetLastError();
        ProgressWindow = v6;
        if ( v6 > 0 )
          ProgressWindow = (unsigned __int16)v6 | 0x80070000;
        v3 = "Failed to create work thread";
        v4 = 1558;
      }
    }
  }
  else
  {
    v1 = GetLastError();
    ProgressWindow = v1;
    if ( v1 > 0 )
      ProgressWindow = (unsigned __int16)v1 | 0x80070000;
    v3 = "Failure to create accelerator key table()";
    v4 = 1543;
  }
  if ( ProgressWindow >= 0 )
    ProgressWindow = -2147467259;
  WusaLogDebugEventA(L"DoInstall", v4, v3);
LABEL_29:
  if ( hWndParent )
  {
    if ( !DestroyWindow(hWndParent) )
    {
      v8 = GetLastError();
      WusaLogDebugEventA(L"DoInstall", 1613, "Warning. Failure returned by DestroyWindow() with error code %d", v8);
    }
    hWndParent = 0;
  }
  if ( pHandles )
  {
    CloseHandle(pHandles);
    pHandles = 0;
  }
  if ( v0 && !DestroyAcceleratorTable(v0) )
  {
    v9 = GetLastError();
    WusaLogDebugEventA(
      L"DoInstall",
      1626,
      "Warning. Failure returned by DestroyAcceleratorTable() with error code %d",
      v9);
  }
  return (unsigned int)ProgressWindow;
}

```

## disassembly

```asm
0x140006554  push    rbp
0x140006556  push    rbx
0x140006557  push    rdi
0x140006558  push    r14
0x14000655a  push    r15
0x14000655c  mov     rbp, rsp
0x14000655f  sub     rsp, 60h
0x140006563  mov     r14d, 1
0x140006569  mov     [rbp+pHandles], 0
0x140006571  mov     edx, r14d; cAccel
0x140006574  mov     dword ptr [rbp+paccel.fVirt], 1B0001h
0x14000657b  lea     rcx, [rbp+paccel]; paccel
0x14000657f  lea     eax, [r14+1]
0x140006583  mov     [rbp+paccel.cmd], ax
0x140006587  call    cs:__imp_CreateAcceleratorTableW
0x14000658d  lea     r15, aDoinstall; "DoInstall"
0x140006594  mov     rdi, rax
0x140006597  test    rax, rax
0x14000659a  jnz     short loc_1400065D4
0x14000659c  call    cs:__imp_GetLastError
0x1400065a2  mov     ebx, eax
0x1400065a4  test    eax, eax
0x1400065a6  jle     short loc_1400065B1
0x1400065a8  movzx   ebx, ax
0x1400065ab  or      ebx, 80070000h
0x1400065b1  lea     r8, aFailureToCreat; "Failure to create accelerator key table"...
0x1400065b8  mov     edx, 607h
0x1400065bd  test    ebx, ebx
0x1400065bf  mov     eax, 80004005h
0x1400065c4  cmovns  ebx, eax
0x1400065c7  mov     rcx, r15
0x1400065ca  call    WusaLogDebugEventA
0x1400065cf  jmp     loc_140006731
0x1400065d4  lea     rcx, hWndParent; HWND *
0x1400065db  call    ?CreateProgressWindow@@YAJPEAPEAUHWND__@@@Z; CreateProgressWindow(HWND__ * *)
0x1400065e0  mov     ebx, eax
0x1400065e2  test    eax, eax
0x1400065e4  jns     short loc_1400065F4
0x1400065e6  lea     r8, aFailureIsRetur; "Failure is returned by CreateProgressWi"...
0x1400065ed  mov     edx, 60Bh
0x1400065f2  jmp     short loc_1400065C7
0x1400065f4  xor     ecx, ecx; lpThreadAttributes
0x1400065f6  mov     [rsp+60h+lpThreadId], 0; lpThreadId
0x1400065ff  xor     r9d, r9d; lpParameter
0x140006602  mov     [rsp+60h+dwCreationFlags], ecx; dwCreationFlags
0x140006606  xor     edx, edx; dwStackSize
0x140006608  cmp     cs:dword_14002017C, ecx
0x14000660e  jz      short loc_140006650
0x140006610  lea     r8, ?UninstallWorker@@YAKPEAX@Z; lpStartAddress
0x140006617  call    cs:__imp_CreateThread
0x14000661d  mov     [rbp+pHandles], rax
0x140006621  test    rax, rax
0x140006624  jnz     loc_1400066F1
0x14000662a  call    cs:__imp_GetLastError
0x140006630  mov     ebx, eax
0x140006632  test    eax, eax
0x140006634  jle     short loc_14000663F
0x140006636  movzx   ebx, ax
0x140006639  or      ebx, 80070000h
0x14000663f  lea     r8, aFailedToCreate_12; "Failed to create work thread"
0x140006646  mov     edx, 611h
0x14000664b  jmp     loc_1400065BD
0x140006650  lea     r8, ?InstallWorker@@YAKPEAX@Z; lpStartAddress
0x140006657  call    cs:__imp_CreateThread
0x14000665d  mov     [rbp+pHandles], rax
0x140006661  test    rax, rax
0x140006664  jnz     loc_1400066F1
0x14000666a  call    cs:__imp_GetLastError
0x140006670  mov     ebx, eax
0x140006672  test    eax, eax
0x140006674  jle     short loc_14000667F
0x140006676  movzx   ebx, ax
0x140006679  or      ebx, 80070000h
0x14000667f  lea     r8, aFailedToCreate_12; "Failed to create work thread"
0x140006686  mov     edx, 616h
0x14000668b  jmp     loc_1400065BD
0x140006690  cmp     eax, r14d
0x140006693  jnz     loc_1400067C3
0x140006699  xorps   xmm0, xmm0
0x14000669c  movups  xmmword ptr [rbp+Msg.hwnd], xmm0
0x1400066a0  movups  xmmword ptr [rbp+Msg.wParam], xmm0
0x1400066a4  movups  xmmword ptr [rbp+Msg.time], xmm0
0x1400066a8  jmp     short loc_1400066D6
0x1400066aa  mov     rcx, cs:hWndParent; hWnd
0x1400066b1  lea     r8, [rbp+Msg]; lpMsg
0x1400066b5  mov     rdx, rdi; hAccTable
0x1400066b8  call    cs:__imp_TranslateAcceleratorW
0x1400066be  test    eax, eax
0x1400066c0  jnz     short loc_1400066D6
0x1400066c2  lea     rcx, [rbp+Msg]; lpMsg
0x1400066c6  call    cs:__imp_TranslateMessage
0x1400066cc  lea     rcx, [rbp+Msg]; lpMsg
0x1400066d0  call    cs:__imp_DispatchMessageW
0x1400066d6  xor     r9d, r9d; wMsgFilterMax
0x1400066d9  mov     [rsp+60h+dwCreationFlags], r14d; wRemoveMsg
0x1400066de  xor     r8d, r8d; wMsgFilterMin
0x1400066e1  lea     rcx, [rbp+Msg]; lpMsg
0x1400066e5  xor     edx, edx; hWnd
0x1400066e7  call    cs:__imp_PeekMessageW
0x1400066ed  test    eax, eax
0x1400066ef  jnz     short loc_1400066AA
0x1400066f1  or      r9d, 0FFFFFFFFh; dwMilliseconds
0x1400066f5  mov     [rsp+60h+dwCreationFlags], 1CFFh; dwWakeMask
0x1400066fd  xor     r8d, r8d; fWaitAll
0x140006700  lea     rdx, [rbp+pHandles]; pHandles
0x140006704  mov     ecx, r14d; nCount
0x140006707  call    cs:__imp_MsgWaitForMultipleObjects
0x14000670d  test    eax, eax
0x14000670f  jnz     loc_140006690
0x140006715  mov     rcx, [rbp+pHandles]; hThread
0x140006719  test    rcx, rcx
0x14000671c  jz      short loc_140006731
0x14000671e  lea     rdx, [rbp+ExitCode]; lpExitCode
0x140006722  mov     [rbp+ExitCode], eax
0x140006725  call    cs:__imp_GetExitCodeThread
0x14000672b  test    eax, eax
0x14000672d  cmovnz  ebx, [rbp+ExitCode]
0x140006731  mov     rcx, cs:hWndParent; hWnd
0x140006738  test    rcx, rcx
0x14000673b  jz      short loc_14000676F
0x14000673d  call    cs:__imp_DestroyWindow
0x140006743  test    eax, eax
0x140006745  jnz     short loc_140006764
0x140006747  call    cs:__imp_GetLastError
0x14000674d  lea     r8, aWarningFailure_0; "Warning. Failure returned by DestroyWin"...
0x140006754  mov     edx, 64Dh
0x140006759  mov     r9d, eax
0x14000675c  mov     rcx, r15
0x14000675f  call    WusaLogDebugEventA
0x140006764  mov     cs:hWndParent, 0
0x14000676f  mov     rcx, [rbp+pHandles]; hObject
0x140006773  test    rcx, rcx
0x140006776  jz      short loc_140006786
0x140006778  call    cs:__imp_CloseHandle
0x14000677e  mov     [rbp+pHandles], 0
0x140006786  test    rdi, rdi
0x140006789  jz      short loc_1400067B5
0x14000678b  mov     rcx, rdi; hAccel
0x14000678e  call    cs:__imp_DestroyAcceleratorTable
0x140006794  test    eax, eax
0x140006796  jnz     short loc_1400067B5
0x140006798  call    cs:__imp_GetLastError
0x14000679e  lea     r8, aWarningFailure; "Warning. Failure returned by DestroyAcc"...
0x1400067a5  mov     edx, 65Ah
0x1400067aa  mov     r9d, eax
0x1400067ad  mov     rcx, r15
0x1400067b0  call    WusaLogDebugEventA
0x1400067b5  mov     eax, ebx
0x1400067b7  add     rsp, 60h
0x1400067bb  pop     r15
0x1400067bd  pop     r14
0x1400067bf  pop     rdi
0x1400067c0  pop     rbx
0x1400067c1  pop     rbp
0x1400067c2  retn
0x1400067c3  call    cs:__imp_GetLastError
0x1400067c9  mov     ebx, eax
0x1400067cb  test    eax, eax
0x1400067cd  jle     short loc_1400067D8
0x1400067cf  movzx   ebx, ax
0x1400067d2  or      ebx, 80070000h
0x1400067d8  lea     r8, aFailedUnexpect; "Failed. Unexpected return from MsgWaitF"...
0x1400067df  mov     edx, 637h
0x1400067e4  jmp     loc_1400065BD
```
