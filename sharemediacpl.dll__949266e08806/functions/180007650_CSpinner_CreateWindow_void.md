# CSpinner::_CreateWindow(void)

- ea: `0x180007650`
- end: `0x180007770`
- name: `?_CreateWindow@CSpinner@@AEAAJXZ`
- size: `288`
- prototype: `__int64 __fastcall(LONG_PTR dwNewLong)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180007778`

## callees

- `0x18000291e`
- `0x180007650`

## import_xrefs

- `KERNEL32!GetLastError` at `0x1800076d1`
- `KERNEL32!GetLastError` at `0x1800076d1`
- `USER32!GetClassInfoExW` at `0x180007689`
- `USER32!GetClassInfoExW` at `0x180007689`
- `USER32!DefWindowProcW` at `0x1800076a6`
- `USER32!RegisterClassExW` at `0x1800076c6`
- `USER32!RegisterClassExW` at `0x1800076c6`
- `USER32!CreateWindowExW` at `0x180007724`
- `USER32!CreateWindowExW` at `0x180007724`
- `USER32!SetWindowLongPtrW` at `0x18000773c`
- `USER32!SetWindowLongPtrW` at `0x180007751`
- `USER32!SetWindowLongPtrW` at `0x18000773c`
- `USER32!SetWindowLongPtrW` at `0x180007751`

## pseudocode

```c
__int64 __fastcall CSpinner::_CreateWindow(LONG_PTR dwNewLong)
{
  signed int LastError; // eax
  signed int v3; // ebx
  HWND Window; // rax
  HWND v5; // rdi
  tagWNDCLASSEXW wcx; // [rsp+60h] [rbp-78h] BYREF

  memset_0(&wcx, 0, sizeof(wcx));
  if ( GetClassInfoExW(g_hinst, L"Spinner Message Window", &wcx) )
    goto LABEL_6;
  wcx.hInstance = g_hinst;
  wcx.lpfnWndProc = DefWindowProcW;
  wcx.cbSize = 80;
  wcx.cbWndExtra = 8;
  wcx.lpszClassName = L"Spinner Message Window";
  if ( RegisterClassExW(&wcx) )
    goto LABEL_6;
  LastError = GetLastError();
  v3 = LastError;
  if ( LastError > 0 )
    v3 = (unsigned __int16)LastError | 0x80070000;
  if ( v3 >= 0 )
  {
LABEL_6:
    Window = CreateWindowExW(0, L"Spinner Message Window", 0, 0, 0, 0, 0, 0, HWND_MESSAGE, 0, g_hinst, 0);
    v5 = Window;
    if ( Window )
    {
      v3 = 0;
      SetWindowLongPtrW(Window, 0, dwNewLong);
      SetWindowLongPtrW(v5, -4, (LONG_PTR)CSpinner::s_WndProc);
      *(_QWORD *)(dwNewLong + 32) = v5;
    }
    else
    {
      return (unsigned int)-2147467259;
    }
  }
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x180007650  push    rbx
0x180007652  push    rbp
0x180007653  push    rsi
0x180007654  push    rdi
0x180007655  sub     rsp, 0B8h
0x18000765c  mov     rsi, rcx
0x18000765f  mov     ebx, 50h ; 'P'
0x180007664  mov     r8d, ebx; Size
0x180007667  lea     rcx, [rsp+0D8h+wcx]; void *
0x18000766c  xor     edx, edx; Val
0x18000766e  call    memset_0
0x180007673  mov     rcx, cs:g_hinst; hInstance
0x18000767a  lea     rdi, ClassName; "Spinner Message Window"
0x180007681  mov     rdx, rdi; lpszClass
0x180007684  lea     r8, [rsp+0D8h+wcx]; lpwcx
0x180007689  call    cs:__imp_GetClassInfoExW
0x18000768f  xor     ebp, ebp
0x180007691  test    eax, eax
0x180007693  jnz     short loc_1800076EA
0x180007695  mov     rax, cs:g_hinst
0x18000769c  lea     rcx, [rsp+0D8h+wcx]; WNDCLASSEXW *
0x1800076a1  mov     [rsp+0D8h+wcx.hInstance], rax
0x1800076a6  mov     rax, cs:__imp_DefWindowProcW
0x1800076ad  mov     [rsp+0D8h+wcx.lpfnWndProc], rax
0x1800076b2  mov     [rsp+0D8h+wcx.cbSize], ebx
0x1800076b6  mov     [rsp+0D8h+wcx.cbWndExtra], 8
0x1800076be  mov     [rsp+0D8h+wcx.lpszClassName], rdi
0x1800076c6  call    cs:__imp_RegisterClassExW
0x1800076cc  test    ax, ax
0x1800076cf  jnz     short loc_1800076EA
0x1800076d1  call    cs:__imp_GetLastError
0x1800076d7  mov     ebx, eax
0x1800076d9  test    eax, eax
0x1800076db  jle     short loc_1800076E6
0x1800076dd  movzx   ebx, ax
0x1800076e0  or      ebx, 80070000h
0x1800076e6  test    ebx, ebx
0x1800076e8  js      short loc_180007762
0x1800076ea  mov     rax, cs:g_hinst
0x1800076f1  xor     r9d, r9d; dwStyle
0x1800076f4  mov     [rsp+0D8h+lpParam], rbp; lpParam
0x1800076f9  xor     r8d, r8d; lpWindowName
0x1800076fc  mov     [rsp+0D8h+hInstance], rax; hInstance
0x180007701  mov     rdx, rdi; lpClassName
0x180007704  mov     [rsp+0D8h+hMenu], rbp; hMenu
0x180007709  xor     ecx, ecx; dwExStyle
0x18000770b  mov     [rsp+0D8h+hWndParent], 0FFFFFFFFFFFFFFFDh; hWndParent
0x180007714  mov     [rsp+0D8h+nHeight], ebp; nHeight
0x180007718  mov     [rsp+0D8h+nWidth], ebp; nWidth
0x18000771c  mov     [rsp+0D8h+Y], ebp; Y
0x180007720  mov     [rsp+0D8h+X], ebp; X
0x180007724  call    cs:__imp_CreateWindowExW
0x18000772a  mov     rdi, rax
0x18000772d  test    rax, rax
0x180007730  jz      short loc_18000775D
0x180007732  mov     r8, rsi; dwNewLong
0x180007735  xor     edx, edx; nIndex
0x180007737  mov     rcx, rax; hWnd
0x18000773a  mov     ebx, ebp
0x18000773c  call    cs:__imp_SetWindowLongPtrW
0x180007742  lea     r8, ?s_WndProc@CSpinner@@SA_JPEAUHWND__@@I_K_J@Z; dwNewLong
0x180007749  mov     edx, 0FFFFFFFCh; nIndex
0x18000774e  mov     rcx, rdi; hWnd
0x180007751  call    cs:__imp_SetWindowLongPtrW
0x180007757  mov     [rsi+20h], rdi
0x18000775b  jmp     short loc_180007762
0x18000775d  mov     ebx, 80004005h
0x180007762  mov     eax, ebx
0x180007764  add     rsp, 0B8h
0x18000776b  pop     rdi
0x18000776c  pop     rsi
0x18000776d  pop     rbp
0x18000776e  pop     rbx
0x18000776f  retn
```
