# MonitorAwareUIPositioner::GetOwner(void)

- ea: `0x180016c34`
- end: `0x180016d80`
- name: `?GetOwner@MonitorAwareUIPositioner@@QEAAPEAUHWND__@@XZ`
- size: `332`
- prototype: `HWND __fastcall(MonitorAwareUIPositioner *__hidden this)`
- caller_count: `3`
- callee_count: `3`
- tags: ``

## callers

- `0x180014f14`
- `0x180014fc0`
- `0x18001d900`

## callees

- `0x180005540`
- `0x180005560`
- `0x180016c34`

## import_xrefs

- `USER32!DestroyWindow` at `0x180016d3b`
- `USER32!DestroyWindow` at `0x180016d3b`
- `USER32!SetForegroundWindow` at `0x180016d64`
- `USER32!SetForegroundWindow` at `0x180016d64`
- `USER32!GetAncestor` at `0x180016cb1`
- `USER32!GetAncestor` at `0x180016cb1`
- `USER32!ShowWindow` at `0x180016d5a`
- `USER32!ShowWindow` at `0x180016d5a`
- `USER32!GetWindowBand` at `0x180016c7e`
- `USER32!GetWindowBand` at `0x180016c7e`
- `USER32!CreateWindowInBandEx` at `0x180016d19`
- `USER32!CreateWindowInBandEx` at `0x180016d19`
- `USER32!__imp_IsShellManagedWindow` at `0x180016c93`
- `USER32!__imp_IsShellManagedWindow` at `0x180016c93`

## pseudocode

```c
HWND __fastcall MonitorAwareUIPositioner::GetOwner(MonitorAwareUIPositioner *this)
{
  __int64 v3; // rcx
  int v4; // eax
  int v5; // ebx
  BOOL v6; // edi
  HWND Ancestor; // rax
  __int64 WindowInBand; // rax
  HWND v9; // rdi
  HWND v10; // rbx
  int v11; // [rsp+80h] [rbp+8h] BYREF
  char v12; // [rsp+88h] [rbp+10h] BYREF

  if ( *(_DWORD *)this )
    return 0;
  if ( !*((_QWORD *)this + 4) && *((_BYTE *)this + 24) )
  {
    v3 = *((_QWORD *)this + 1);
    v11 = 0;
    if ( !(unsigned int)GetWindowBand(v3, &v11) )
      v11 = 0;
    v4 = IsShellManagedWindow(*((_QWORD *)this + 1));
    v5 = v11;
    v6 = v4 != 0;
    Ancestor = GetAncestor(*((HWND *)this + 1), 2u);
    WindowInBand = CreateWindowInBandEx(
                     8,
                     L"static",
                     L"Window Dialog",
                     0x80000000LL,
                     *((_DWORD *)this + 4),
                     *((_DWORD *)this + 5),
                     0,
                     0,
                     Ancestor,
                     0,
                     &_ImageBase,
                     0,
                     v5,
                     v6);
    v9 = (HWND)*((_QWORD *)this + 4);
    v10 = (HWND)WindowInBand;
    if ( v9 )
    {
      wil::last_error_context::last_error_context((wil::last_error_context *)&v12);
      DestroyWindow(v9);
      wil::last_error_context::~last_error_context((wil::last_error_context *)&v12);
    }
    *((_QWORD *)this + 4) = v10;
    ShowWindow(v10, 4);
    SetForegroundWindow(*((HWND *)this + 4));
  }
  return (HWND)*((_QWORD *)this + 4);
}

```

## disassembly

```asm
0x180016c34  mov     [rsp+arg_10], rbx
0x180016c39  mov     [rsp+arg_18], rsi
0x180016c3e  push    rdi
0x180016c3f  sub     rsp, 70h
0x180016c43  cmp     dword ptr [rcx], 0
0x180016c46  mov     rsi, rcx
0x180016c49  jz      short loc_180016C52
0x180016c4b  xor     eax, eax
0x180016c4d  jmp     loc_180016D6E
0x180016c52  cmp     qword ptr [rcx+20h], 0
0x180016c57  jnz     loc_180016D6A
0x180016c5d  cmp     byte ptr [rcx+18h], 0
0x180016c61  jz      loc_180016D6A
0x180016c67  mov     rcx, [rcx+8]
0x180016c6b  lea     rdx, [rsp+78h+arg_0]
0x180016c73  mov     [rsp+78h+arg_0], 0
0x180016c7e  call    cs:__imp_GetWindowBand
0x180016c84  test    eax, eax
0x180016c86  jnz     short loc_180016C8F
0x180016c88  mov     [rsp+78h+arg_0], eax
0x180016c8f  mov     rcx, [rsi+8]
0x180016c93  call    cs:__imp_IsShellManagedWindow
0x180016c99  mov     rcx, [rsi+8]; hwnd
0x180016c9d  xor     edi, edi
0x180016c9f  mov     ebx, [rsp+78h+arg_0]
0x180016ca6  test    eax, eax
0x180016ca8  mov     edx, 2; gaFlags
0x180016cad  setnz   dil
0x180016cb1  call    cs:__imp_GetAncestor
0x180016cb7  mov     [rsp+78h+var_10], edi
0x180016cbb  lea     rcx, __ImageBase
0x180016cc2  mov     [rsp+78h+var_18], ebx
0x180016cc6  lea     r8, aWindowDialog; "Window Dialog"
0x180016ccd  mov     [rsp+78h+var_20], 0
0x180016cd6  lea     rdx, aStatic; "static"
0x180016cdd  mov     [rsp+78h+var_28], rcx
0x180016ce2  mov     r9d, 80000000h
0x180016ce8  mov     [rsp+78h+var_30], 0
0x180016cf1  mov     ecx, 8
0x180016cf6  mov     [rsp+78h+var_38], rax
0x180016cfb  mov     eax, [rsi+14h]
0x180016cfe  mov     [rsp+78h+var_40], 0
0x180016d06  mov     [rsp+78h+var_48], 0
0x180016d0e  mov     [rsp+78h+var_50], eax
0x180016d12  mov     eax, [rsi+10h]
0x180016d15  mov     [rsp+78h+var_58], eax
0x180016d19  call    cs:__imp_CreateWindowInBandEx
0x180016d1f  mov     rdi, [rsi+20h]
0x180016d23  mov     rbx, rax
0x180016d26  test    rdi, rdi
0x180016d29  jz      short loc_180016D4E
0x180016d2b  lea     rcx, [rsp+78h+arg_8]; this
0x180016d33  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x180016d38  mov     rcx, rdi; hWnd
0x180016d3b  call    cs:__imp_DestroyWindow
0x180016d41  lea     rcx, [rsp+78h+arg_8]; this
0x180016d49  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x180016d4e  mov     edx, 4; nCmdShow
0x180016d53  mov     [rsi+20h], rbx
0x180016d57  mov     rcx, rbx; hWnd
0x180016d5a  call    cs:__imp_ShowWindow
0x180016d60  mov     rcx, [rsi+20h]; hWnd
0x180016d64  call    cs:__imp_SetForegroundWindow
0x180016d6a  mov     rax, [rsi+20h]
0x180016d6e  lea     r11, [rsp+78h+var_8]
0x180016d73  mov     rbx, [r11+20h]
0x180016d77  mov     rsi, [r11+28h]
0x180016d7b  mov     rsp, r11
0x180016d7e  pop     rdi
0x180016d7f  retn
```
