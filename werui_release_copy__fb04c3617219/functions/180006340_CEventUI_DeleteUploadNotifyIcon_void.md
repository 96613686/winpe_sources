# CEventUI::DeleteUploadNotifyIcon(void)

- ea: `0x180006340`
- end: `0x18000643a`
- name: `?DeleteUploadNotifyIcon@CEventUI@@AEAAJXZ`
- size: `250`
- prototype: `__int64 __fastcall(CEventUI *__hidden this)`
- caller_count: `3`
- callee_count: `5`
- tags: ``

## callers

- `0x180007d50`
- `0x180007e50`
- `0x18000899c`

## callees

- `0x180003604`
- `0x180003fe4`
- `0x180006340`
- `0x180016c1e`
- `0x180016c50`

## import_xrefs

- `KERNEL32!GetLastError` at `0x1800063aa`
- `KERNEL32!GetLastError` at `0x1800063d2`
- `KERNEL32!GetLastError` at `0x1800063aa`
- `KERNEL32!GetLastError` at `0x1800063d2`
- `SHELL32!Shell_NotifyIconW` at `0x1800063a0`
- `SHELL32!Shell_NotifyIconW` at `0x1800063a0`
- `ext-ms-win-ntuser-window-l1-1-0!IsWindow` at `0x180006407`
- `ext-ms-win-ntuser-window-l1-1-0!IsWindow` at `0x180006407`
- `ext-ms-win-ntuser-window-l1-1-0!ShowWindow` at `0x180006417`
- `ext-ms-win-ntuser-window-l1-1-0!ShowWindow` at `0x180006417`

## pseudocode

```c
__int64 __fastcall CEventUI::DeleteUploadNotifyIcon(CEventUI *this)
{
  DWORD LastError; // eax
  unsigned int v3; // ebx
  DWORD v4; // eax
  struct _NOTIFYICONDATAW Data; // [rsp+20h] [rbp-3E8h] BYREF

  memset_0(&Data, 0, sizeof(Data));
  if ( *((_DWORD *)this + 188) )
  {
    Data.hWnd = (HWND)*((_QWORD *)this + 13);
    Data.cbSize = 976;
    Data.uID = 255;
    if ( !Shell_NotifyIconW(2u, &Data) )
    {
      LastError = GetLastError();
      v3 = ERROR_HR_FROM_WIN32(LastError);
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        v4 = GetLastError();
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 37, &WPP_ddf8af267e4d35c632af17f8a6fba57b_Traceguids, v4);
      }
      return v3;
    }
    *((_DWORD *)this + 188) = 0;
  }
  if ( IsWindow(*((HWND *)this + 14)) )
    ShowWindow(*((HWND *)this + 14), 0);
  return 0;
}

```

## disassembly

```asm
0x180006340  push    rbx
0x180006342  sub     rsp, 400h
0x180006349  mov     rax, cs:__security_cookie
0x180006350  xor     rax, rsp
0x180006353  mov     [rsp+408h+var_18], rax
0x18000635b  mov     rbx, rcx
0x18000635e  xor     edx, edx; Val
0x180006360  lea     rcx, [rsp+408h+Data]; void *
0x180006365  mov     r8d, 3D0h; Size
0x18000636b  call    memset_0
0x180006370  cmp     dword ptr [rbx+2F0h], 0
0x180006377  jz      loc_180006403
0x18000637d  mov     rax, [rbx+68h]
0x180006381  lea     rdx, [rsp+408h+Data]; lpData
0x180006386  mov     ecx, 2; dwMessage
0x18000638b  mov     [rsp+408h+Data.hWnd], rax
0x180006390  mov     [rsp+408h+Data.cbSize], 3D0h
0x180006398  mov     [rsp+408h+Data.uID], 0FFh
0x1800063a0  call    cs:__imp_Shell_NotifyIconW
0x1800063a6  test    eax, eax
0x1800063a8  jnz     short loc_1800063F9
0x1800063aa  call    cs:__imp_GetLastError
0x1800063b0  mov     ecx, eax; unsigned int
0x1800063b2  call    ?ERROR_HR_FROM_WIN32@@YAJK@Z; ERROR_HR_FROM_WIN32(ulong)
0x1800063b7  mov     ebx, eax
0x1800063b9  mov     rax, cs:WPP_GLOBAL_Control
0x1800063c0  lea     rcx, WPP_GLOBAL_Control
0x1800063c7  cmp     rax, rcx
0x1800063ca  jz      short loc_18000641F
0x1800063cc  test    byte ptr [rax+1Ch], 1
0x1800063d0  jz      short loc_18000641F
0x1800063d2  call    cs:__imp_GetLastError
0x1800063d8  mov     rcx, cs:WPP_GLOBAL_Control
0x1800063df  lea     r8, WPP_ddf8af267e4d35c632af17f8a6fba57b_Traceguids
0x1800063e6  mov     edx, 25h ; '%'
0x1800063eb  mov     r9d, eax
0x1800063ee  mov     rcx, [rcx+10h]
0x1800063f2  call    WPP_SF_d
0x1800063f7  jmp     short loc_18000641F
0x1800063f9  mov     dword ptr [rbx+2F0h], 0
0x180006403  mov     rcx, [rbx+70h]; hWnd
0x180006407  call    cs:__imp_IsWindow
0x18000640d  test    eax, eax
0x18000640f  jz      short loc_18000641D
0x180006411  mov     rcx, [rbx+70h]; hWnd
0x180006415  xor     edx, edx; nCmdShow
0x180006417  call    cs:__imp_ShowWindow
0x18000641d  xor     ebx, ebx
0x18000641f  mov     eax, ebx
0x180006421  mov     rcx, [rsp+408h+var_18]
0x180006429  xor     rcx, rsp; StackCookie
0x18000642c  call    __security_check_cookie
0x180006431  add     rsp, 400h
0x180006438  pop     rbx
0x180006439  retn
```
