# CThemeCplCore::_CreateThemeChangeListener(void)

- ea: `0x180036ba0`
- end: `0x180036cd4`
- name: `?_CreateThemeChangeListener@CThemeCplCore@@AEAAJXZ`
- size: `308`
- prototype: `__int64 __fastcall(LONG_PTR dwNewLong)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180035ba4`

## callees

- `0x180002f34`
- `0x180036ba0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180036ca0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180036ca0`
- `USER32!CreateWindowExW` at `0x180036c6f`
- `USER32!CreateWindowExW` at `0x180036c6f`
- `USER32!GetClassInfoExW` at `0x180036be6`
- `USER32!GetClassInfoExW` at `0x180036be6`
- `USER32!RegisterClassExW` at `0x180036c23`
- `USER32!RegisterClassExW` at `0x180036c23`
- `USER32!SetWindowLongPtrW` at `0x180036c92`
- `USER32!SetWindowLongPtrW` at `0x180036c92`

## pseudocode

```c
__int64 __fastcall CThemeCplCore::_CreateThemeChangeListener(LONG_PTR dwNewLong)
{
  signed int v2; // ebx
  HWND Window; // rax
  signed int LastError; // eax
  tagWNDCLASSEXW wcx; // [rsp+60h] [rbp-78h] BYREF

  v2 = 0;
  if ( !*(_QWORD *)(dwNewLong + 272) )
  {
    memset_0(&wcx, 0, sizeof(wcx));
    if ( (GetClassInfoExW(g_hinst, L"PersonalizationThemeChangeListener", &wcx)
       || (wcx.cbSize = 80,
           wcx.lpfnWndProc = (WNDPROC)CThemeCplCore::s_WndProcThemeChangeListener,
           wcx.hInstance = g_hinst,
           wcx.lpszClassName = L"PersonalizationThemeChangeListener",
           RegisterClassExW(&wcx)))
      && (Window = CreateWindowExW(
                     0,
                     L"PersonalizationThemeChangeListener",
                     0,
                     0,
                     0x80000000,
                     0x80000000,
                     0x80000000,
                     0x80000000,
                     0,
                     0,
                     g_hinst,
                     0),
          (*(_QWORD *)(dwNewLong + 272) = Window) != 0) )
    {
      SetWindowLongPtrW(Window, -21, dwNewLong);
    }
    else
    {
      LastError = GetLastError();
      v2 = LastError;
      if ( LastError > 0 )
        v2 = (unsigned __int16)LastError | 0x80070000;
      if ( v2 >= 0 )
        return (unsigned int)-2147467259;
    }
  }
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x180036ba0  push    rbx
0x180036ba2  push    rbp
0x180036ba3  push    rsi
0x180036ba4  push    rdi
0x180036ba5  sub     rsp, 0B8h
0x180036bac  xor     esi, esi
0x180036bae  mov     rdi, rcx
0x180036bb1  mov     ebx, esi
0x180036bb3  cmp     [rcx+110h], rsi
0x180036bba  jnz     loc_180036CC5
0x180036bc0  xor     edx, edx; Val
0x180036bc2  lea     r8d, [rsi+50h]; Size
0x180036bc6  lea     rcx, [rsp+0D8h+wcx]; void *
0x180036bcb  call    memset_0
0x180036bd0  mov     rcx, cs:g_hinst; hInstance
0x180036bd7  lea     rbp, szClass; "PersonalizationThemeChangeListener"
0x180036bde  mov     rdx, rbp; lpszClass
0x180036be1  lea     r8, [rsp+0D8h+wcx]; lpwcx
0x180036be6  call    cs:__imp_GetClassInfoExW
0x180036bed  nop     dword ptr [rax+rax+00h]
0x180036bf2  test    eax, eax
0x180036bf4  jnz     short loc_180036C34
0x180036bf6  lea     rax, ?s_WndProcThemeChangeListener@CThemeCplCore@@CA_JPEAUHWND__@@I_K_J@Z; CThemeCplCore::s_WndProcThemeChangeListener(HWND__ *,uint,unsigned __int64,__int64)
0x180036bfd  mov     [rsp+0D8h+wcx.cbSize], 50h ; 'P'
0x180036c05  mov     [rsp+0D8h+wcx.lpfnWndProc], rax
0x180036c0a  lea     rcx, [rsp+0D8h+wcx]; WNDCLASSEXW *
0x180036c0f  mov     rax, cs:g_hinst
0x180036c16  mov     [rsp+0D8h+wcx.hInstance], rax
0x180036c1b  mov     [rsp+0D8h+wcx.lpszClassName], rbp
0x180036c23  call    cs:__imp_RegisterClassExW
0x180036c2a  nop     dword ptr [rax+rax+00h]
0x180036c2f  test    ax, ax
0x180036c32  jz      short loc_180036CA0
0x180036c34  mov     rax, cs:g_hinst
0x180036c3b  xor     r9d, r9d; dwStyle
0x180036c3e  mov     [rsp+0D8h+lpParam], rsi; lpParam
0x180036c43  xor     r8d, r8d; lpWindowName
0x180036c46  mov     [rsp+0D8h+hInstance], rax; hInstance
0x180036c4b  mov     rdx, rbp; lpClassName
0x180036c4e  mov     [rsp+0D8h+hMenu], rsi; hMenu
0x180036c53  mov     eax, 80000000h
0x180036c58  mov     [rsp+0D8h+hWndParent], rsi; hWndParent
0x180036c5d  xor     ecx, ecx; dwExStyle
0x180036c5f  mov     [rsp+0D8h+nHeight], eax; nHeight
0x180036c63  mov     [rsp+0D8h+nWidth], eax; nWidth
0x180036c67  mov     [rsp+0D8h+Y], eax; Y
0x180036c6b  mov     [rsp+0D8h+X], eax; X
0x180036c6f  call    cs:__imp_CreateWindowExW
0x180036c76  nop     dword ptr [rax+rax+00h]
0x180036c7b  mov     [rdi+110h], rax
0x180036c82  test    rax, rax
0x180036c85  jz      short loc_180036CA0
0x180036c87  mov     r8, rdi; dwNewLong
0x180036c8a  mov     edx, 0FFFFFFEBh; nIndex
0x180036c8f  mov     rcx, rax; hWnd
0x180036c92  call    cs:__imp_SetWindowLongPtrW
0x180036c99  nop     dword ptr [rax+rax+00h]
0x180036c9e  jmp     short loc_180036CC5
0x180036ca0  call    cs:__imp_GetLastError
0x180036ca7  nop     dword ptr [rax+rax+00h]
0x180036cac  mov     ebx, eax
0x180036cae  test    eax, eax
0x180036cb0  jle     short loc_180036CBB
0x180036cb2  movzx   ebx, ax
0x180036cb5  or      ebx, 80070000h
0x180036cbb  test    ebx, ebx
0x180036cbd  mov     eax, 80004005h
0x180036cc2  cmovns  ebx, eax
0x180036cc5  mov     eax, ebx
0x180036cc7  add     rsp, 0B8h
0x180036cce  pop     rdi
0x180036ccf  pop     rsi
0x180036cd0  pop     rbp
0x180036cd1  pop     rbx
0x180036cd2  retn
```
