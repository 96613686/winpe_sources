# SHCreateWorkerWindowW

- ea: `0x180044820`
- end: `0x1800449cb`
- name: `SHCreateWorkerWindowW`
- size: `427`
- prototype: `__int64 __fastcall(LONG_PTR dwNewLong, HWND hWndParent, DWORD dwExStyle, DWORD dwStyle, HMENU, LONG_PTR)`
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x180044820`
- `0x1800449e0`
- `0x1800672e8`

## import_xrefs

- `api-ms-win-core-localization-l1-2-0!GetLocaleInfoW` at `0x1800449a8`
- `api-ms-win-core-localization-l1-2-0!GetLocaleInfoW` at `0x1800449a8`
- `api-ms-win-core-localization-obsolete-l1-2-0!GetUserDefaultUILanguage` at `0x180044978`
- `api-ms-win-core-localization-obsolete-l1-2-0!GetUserDefaultUILanguage` at `0x180044978`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!DefWindowProcW` at `0x180044855`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!CreateWindowExW` at `0x1800448fd`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!CreateWindowExW` at `0x1800448fd`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!SetWindowLongPtrW` at `0x180044937`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!SetWindowLongPtrW` at `0x18004494d`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!SetWindowLongPtrW` at `0x180044937`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!SetWindowLongPtrW` at `0x18004494d`
- `ext-ms-win-rtcore-ntuser-cursor-l1-1-0!LoadCursorW` at `0x18004487c`
- `ext-ms-win-rtcore-ntuser-cursor-l1-1-0!LoadCursorW` at `0x18004487c`

## pseudocode

```c
HWND __fastcall SHCreateWorkerWindowW(
        LONG_PTR dwNewLong,
        HWND hWndParent,
        DWORD dwExStyle,
        DWORD dwStyle,
        HMENU hMenu,
        LONG_PTR dwNewLonga)
{
  HCURSOR CursorW; // rax
  HWND Window; // rax
  HWND v12; // rbx
  int v14; // ecx
  int v15; // eax
  __int32 v16; // ebx
  LANGID UserDefaultUILanguage; // ax
  WNDCLASSW WndClass; // [rsp+60h] [rbp-78h] BYREF
  int LCData; // [rsp+E8h] [rbp+10h] BYREF

  memset_0(&WndClass, 0, sizeof(WndClass));
  WndClass.lpfnWndProc = DefWindowProcW;
  WndClass.hInstance = g_hinst;
  WndClass.cbWndExtra = 8;
  CursorW = LoadCursorW(0, (LPCWSTR)0x7F00);
  WndClass.hbrBackground = (HBRUSH)16;
  WndClass.hCursor = CursorW;
  WndClass.lpszClassName = L"WorkerW";
  if ( !hWndParent )
  {
    v14 = `IsBiDiLocalizedSystemEx'::`2'::s_tbBiDi;
    if ( `IsBiDiLocalizedSystemEx'::`2'::s_tbBiDi == -1 )
    {
      v16 = 0;
      UserDefaultUILanguage = GetUserDefaultUILanguage();
      `IsBiDiLocalizedSystemEx'::`2'::s_langID = UserDefaultUILanguage;
      if ( UserDefaultUILanguage )
      {
        LCData = 0;
        if ( GetLocaleInfoW(UserDefaultUILanguage, 0x20000070u, (LPWSTR)&LCData, 2) > 0 )
          LOBYTE(v16) = LCData == 1;
      }
      _InterlockedExchange(&`IsBiDiLocalizedSystemEx'::`2'::s_tbBiDi, v16);
      v14 = `IsBiDiLocalizedSystemEx'::`2'::s_tbBiDi;
    }
    v15 = 0;
    if ( v14 == 1 )
      v15 = 0x400000;
    dwExStyle |= v15;
  }
  SHRegisterClassW(&WndClass);
  Window = CreateWindowExW(dwExStyle, L"WorkerW", 0, dwStyle, 0, 0, 0, 0, hWndParent, hMenu, g_hinst, 0);
  v12 = Window;
  if ( Window )
  {
    SetWindowLongPtrW(Window, 0, dwNewLonga);
    if ( dwNewLong )
      SetWindowLongPtrW(v12, -4, dwNewLong);
  }
  return v12;
}

```

## disassembly

```asm
0x180044820  mov     [rsp+arg_0], rbx
0x180044825  mov     [rsp+arg_10], rbp
0x18004482a  push    rsi
0x18004482b  push    rdi
0x18004482c  push    r12
0x18004482e  push    r14
0x180044830  push    r15
0x180044832  sub     rsp, 0B0h
0x180044839  mov     rbp, rdx
0x18004483c  mov     esi, r8d
0x18004483f  xor     edx, edx; Val
0x180044841  mov     rdi, rcx
0x180044844  lea     rcx, [rsp+0D8h+WndClass]; void *
0x180044849  mov     r14d, r9d
0x18004484c  lea     r8d, [rdx+48h]; Size
0x180044850  call    memset_0
0x180044855  mov     rax, cs:__imp_DefWindowProcW
0x18004485c  mov     edx, 7F00h; lpCursorName
0x180044861  mov     [rsp+0D8h+WndClass.lpfnWndProc], rax
0x180044866  xor     ecx, ecx; hInstance
0x180044868  mov     rax, cs:g_hinst
0x18004486f  mov     [rsp+0D8h+WndClass.hInstance], rax
0x180044874  mov     [rsp+0D8h+WndClass.cbWndExtra], 8
0x18004487c  call    cs:__imp_LoadCursorW
0x180044882  xor     r15d, r15d
0x180044885  mov     [rsp+0D8h+WndClass.hbrBackground], 10h
0x180044891  mov     [rsp+0D8h+WndClass.hCursor], rax
0x180044899  lea     r12, ClassName; "WorkerW"
0x1800448a0  mov     [rsp+0D8h+WndClass.lpszClassName], r12
0x1800448a8  test    rbp, rbp
0x1800448ab  jz      loc_180044955
0x1800448b1  lea     rcx, [rsp+0D8h+WndClass]; lpWndClass
0x1800448b6  call    SHRegisterClassW
0x1800448bb  mov     rax, cs:g_hinst
0x1800448c2  mov     r9d, r14d; dwStyle
0x1800448c5  mov     [rsp+0D8h+lpParam], r15; lpParam
0x1800448ca  xor     r8d, r8d; lpWindowName
0x1800448cd  mov     [rsp+0D8h+hInstance], rax; hInstance
0x1800448d2  mov     rdx, r12; lpClassName
0x1800448d5  mov     rax, [rsp+0D8h+arg_20]
0x1800448dd  mov     ecx, esi; dwExStyle
0x1800448df  mov     [rsp+0D8h+hMenu], rax; hMenu
0x1800448e4  mov     [rsp+0D8h+hWndParent], rbp; hWndParent
0x1800448e9  mov     [rsp+0D8h+nHeight], r15d; nHeight
0x1800448ee  mov     [rsp+0D8h+nWidth], r15d; nWidth
0x1800448f3  mov     [rsp+0D8h+Y], r15d; Y
0x1800448f8  mov     [rsp+0D8h+X], r15d; X
0x1800448fd  call    cs:__imp_CreateWindowExW
0x180044903  mov     rbx, rax
0x180044906  test    rax, rax
0x180044909  jnz     short loc_18004492A
0x18004490b  lea     r11, [rsp+0D8h+var_28]
0x180044913  mov     rax, rbx
0x180044916  mov     rbx, [r11+30h]
0x18004491a  mov     rbp, [r11+40h]
0x18004491e  mov     rsp, r11
0x180044921  pop     r15
0x180044923  pop     r14
0x180044925  pop     r12
0x180044927  pop     rdi
0x180044928  pop     rsi
0x180044929  retn
0x18004492a  mov     r8, [rsp+0D8h+dwNewLong]; dwNewLong
0x180044932  xor     edx, edx; nIndex
0x180044934  mov     rcx, rbx; hWnd
0x180044937  call    cs:__imp_SetWindowLongPtrW
0x18004493d  test    rdi, rdi
0x180044940  jz      short loc_18004490B
0x180044942  mov     r8, rdi; dwNewLong
0x180044945  mov     edx, 0FFFFFFFCh; nIndex
0x18004494a  mov     rcx, rbx; hWnd
0x18004494d  call    cs:__imp_SetWindowLongPtrW
0x180044953  jmp     short loc_18004490B
0x180044955  mov     ecx, cs:?s_tbBiDi@?1??IsBiDiLocalizedSystemEx@@YAHPEAG@Z@4JA; long `IsBiDiLocalizedSystemEx(ushort *)'::`2'::s_tbBiDi
0x18004495b  cmp     ecx, 0FFFFFFFFh
0x18004495e  jz      short loc_180044975
0x180044960  cmp     ecx, 1
0x180044963  mov     eax, r15d
0x180044966  mov     edx, 400000h
0x18004496b  cmovz   eax, edx
0x18004496e  or      esi, eax
0x180044970  jmp     loc_1800448B1
0x180044975  mov     ebx, r15d
0x180044978  call    cs:__imp_GetUserDefaultUILanguage
0x18004497e  mov     cs:?s_langID@?1??IsBiDiLocalizedSystemEx@@YAHPEAG@Z@4GA, ax; ushort `IsBiDiLocalizedSystemEx(ushort *)'::`2'::s_langID
0x180044985  test    ax, ax
0x180044988  jz      short loc_1800449BD
0x18004498a  movzx   ecx, ax; Locale
0x18004498d  lea     r8, [rsp+0D8h+LCData]; lpLCData
0x180044995  mov     r9d, 2; cchData
0x18004499b  mov     [rsp+0D8h+LCData], r15d
0x1800449a3  mov     edx, 20000070h; LCType
0x1800449a8  call    cs:__imp_GetLocaleInfoW
0x1800449ae  test    eax, eax
0x1800449b0  jle     short loc_1800449BD
0x1800449b2  cmp     [rsp+0D8h+LCData], 1
0x1800449ba  setz    bl
0x1800449bd  xchg    ebx, cs:?s_tbBiDi@?1??IsBiDiLocalizedSystemEx@@YAHPEAG@Z@4JA; long `IsBiDiLocalizedSystemEx(ushort *)'::`2'::s_tbBiDi
0x1800449c3  mov     ecx, cs:?s_tbBiDi@?1??IsBiDiLocalizedSystemEx@@YAHPEAG@Z@4JA; long `IsBiDiLocalizedSystemEx(ushort *)'::`2'::s_tbBiDi
0x1800449c9  jmp     short loc_180044960
```
