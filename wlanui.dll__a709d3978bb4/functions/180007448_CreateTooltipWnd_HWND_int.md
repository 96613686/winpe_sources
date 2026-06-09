# CreateTooltipWnd(HWND__ *,int)

- ea: `0x180007448`
- end: `0x18000756a`
- name: `?CreateTooltipWnd@@YAPEAUHWND__@@PEAU1@H@Z`
- size: `290`
- prototype: `HWND __fastcall(HWND hWndParent, int)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x18000a7f8`

## callees

- `0x180007448`
- `0x180014b00`
- `0x180014dd8`

## import_xrefs

- `KERNEL32!DeactivateActCtx` at `0x1800074eb`
- `KERNEL32!DeactivateActCtx` at `0x1800074eb`
- `USER32!SetWindowPos` at `0x18000751b`
- `USER32!SetWindowPos` at `0x18000751b`
- `USER32!GetDoubleClickTime` at `0x180007542`
- `USER32!GetDoubleClickTime` at `0x180007542`
- `USER32!GetWindowLongPtrW` at `0x180007456`
- `USER32!GetWindowLongPtrW` at `0x180007456`
- `USER32!GetSystemMetrics` at `0x180007523`
- `USER32!GetSystemMetrics` at `0x180007523`
- `USER32!SendMessageW` at `0x18000753c`
- `USER32!SendMessageW` at `0x180007557`
- `USER32!SendMessageW` at `0x18000753c`
- `USER32!SendMessageW` at `0x180007557`
- `USER32!CreateWindowExW` at `0x1800074d3`
- `USER32!CreateWindowExW` at `0x1800074d3`

## pseudocode

```c
HWND __fastcall CreateTooltipWnd(HWND hWndParent)
{
  HWND Window; // rbx
  int SystemMetrics; // eax
  unsigned __int16 DoubleClickTime; // ax
  ULONG_PTR ulCookie; // [rsp+80h] [rbp+18h] BYREF

  GetWindowLongPtrW(hWndParent, -20);
  ulCookie = 0;
  if ( !(unsigned int)SHActivateContext(&ulCookie) )
    return 0;
  if ( g_hActCtx != (HANDLE)-3LL )
    DelayLoadCC();
  Window = CreateWindowExW(
             0,
             L"tooltips_class32",
             0,
             0x80000042,
             0x80000000,
             0x80000000,
             0x80000000,
             0x80000000,
             hWndParent,
             0,
             0,
             0);
  if ( ulCookie )
    DeactivateActCtx(0, ulCookie);
  if ( !Window )
    return 0;
  SetWindowPos(Window, HWND_MESSAGE|0x2LL, 0, 0, 0, 0, 0x13u);
  SystemMetrics = GetSystemMetrics(0);
  SendMessageW(Window, 0x418u, 0, SystemMetrics / 2);
  DoubleClickTime = GetDoubleClickTime();
  SendMessageW(Window, 0x403u, 0, DoubleClickTime);
  return Window;
}

```

## disassembly

```asm
0x180007448  push    rbx
0x18000744a  sub     rsp, 60h
0x18000744e  mov     edx, 0FFFFFFECh; nIndex
0x180007453  mov     rbx, rcx
0x180007456  call    cs:__imp_GetWindowLongPtrW
0x18000745c  lea     rcx, [rsp+68h+ulCookie]
0x180007464  mov     [rsp+68h+ulCookie], 0
0x180007470  call    SHActivateContext
0x180007475  test    eax, eax
0x180007477  jz      loc_180007562
0x18000747d  cmp     cs:g_hActCtx, 0FFFFFFFFFFFFFFFDh
0x180007485  jz      short loc_18000748C
0x180007487  call    DelayLoadCC
0x18000748c  mov     [rsp+68h+lpParam], 0; lpParam
0x180007495  lea     rdx, ClassName; "tooltips_class32"
0x18000749c  mov     [rsp+68h+hInstance], 0; hInstance
0x1800074a5  mov     eax, 80000000h
0x1800074aa  mov     [rsp+68h+hMenu], 0; hMenu
0x1800074b3  mov     r9d, 80000042h; dwStyle
0x1800074b9  mov     [rsp+68h+hWndParent], rbx; hWndParent
0x1800074be  xor     r8d, r8d; lpWindowName
0x1800074c1  mov     [rsp+68h+nHeight], eax; nHeight
0x1800074c5  xor     ecx, ecx; dwExStyle
0x1800074c7  mov     [rsp+68h+nWidth], eax; nWidth
0x1800074cb  mov     [rsp+68h+Y], eax; Y
0x1800074cf  mov     [rsp+68h+X], eax; X
0x1800074d3  call    cs:__imp_CreateWindowExW
0x1800074d9  mov     rdx, [rsp+68h+ulCookie]; ulCookie
0x1800074e1  mov     rbx, rax
0x1800074e4  test    rdx, rdx
0x1800074e7  jz      short loc_1800074F1
0x1800074e9  xor     ecx, ecx; dwFlags
0x1800074eb  call    cs:__imp_DeactivateActCtx
0x1800074f1  test    rbx, rbx
0x1800074f4  jz      short loc_180007562
0x1800074f6  mov     [rsp+68h+nWidth], 13h; uFlags
0x1800074fe  xor     r9d, r9d; Y
0x180007501  mov     [rsp+68h+Y], 0; cy
0x180007509  xor     r8d, r8d; X
0x18000750c  or      rdx, 0FFFFFFFFFFFFFFFFh; hWndInsertAfter
0x180007510  mov     [rsp+68h+X], 0; cx
0x180007518  mov     rcx, rbx; hWnd
0x18000751b  call    cs:__imp_SetWindowPos
0x180007521  xor     ecx, ecx; nIndex
0x180007523  call    cs:__imp_GetSystemMetrics
0x180007529  xor     r8d, r8d; wParam
0x18000752c  mov     rcx, rbx; hWnd
0x18000752f  cdq
0x180007530  sub     eax, edx
0x180007532  mov     edx, 418h; Msg
0x180007537  sar     eax, 1
0x180007539  movsxd  r9, eax; lParam
0x18000753c  call    cs:__imp_SendMessageW
0x180007542  call    cs:__imp_GetDoubleClickTime
0x180007548  movzx   r9d, ax; lParam
0x18000754c  xor     r8d, r8d; wParam
0x18000754f  mov     edx, 403h; Msg
0x180007554  mov     rcx, rbx; hWnd
0x180007557  call    cs:__imp_SendMessageW
0x18000755d  mov     rax, rbx
0x180007560  jmp     short loc_180007564
0x180007562  xor     eax, eax
0x180007564  add     rsp, 60h
0x180007568  pop     rbx
0x180007569  retn
```
