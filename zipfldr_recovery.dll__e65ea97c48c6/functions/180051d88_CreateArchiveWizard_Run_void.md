# CreateArchiveWizard::Run(void)

- ea: `0x180051d88`
- end: `0x180051f16`
- name: `?Run@CreateArchiveWizard@@AEAA_JXZ`
- size: `398`
- prototype: `__int64 __fastcall(CreateArchiveWizard *__hidden this)`
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x180052280`

## callees

- `0x180034c28`
- `0x180036f50`
- `0x180037958`
- `0x180051d88`
- `0x18006daa0`
- `0x18006db34`

## import_xrefs

- `SHLWAPI!__imp_ShellMessageBoxW` at `0x180051ecf`
- `SHLWAPI!__imp_ShellMessageBoxW` at `0x180051ecf`
- `USER32!SetThreadDpiAwarenessContext` at `0x180051db1`
- `USER32!SetThreadDpiAwarenessContext` at `0x180051eaa`
- `USER32!SetThreadDpiAwarenessContext` at `0x180051ef3`
- `USER32!SetThreadDpiAwarenessContext` at `0x180051db1`
- `USER32!SetThreadDpiAwarenessContext` at `0x180051eaa`
- `USER32!SetThreadDpiAwarenessContext` at `0x180051ef3`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
INT_PTR __fastcall CreateArchiveWizard::Run(CreateArchiveWizard *this)
{
  unsigned __int64 v2; // rbx
  struct _PSP *v3; // rax
  INT_PTR v4; // rbx
  unsigned __int64 i; // rdi
  __int64 v7; // [rsp+40h] [rbp-C0h]
  PROPSHEETHEADERW_V2 v8; // [rsp+50h] [rbp-B0h] BYREF
  PROPSHEETPAGEW_V4 constPropSheetPagePointer; // [rsp+B0h] [rbp-50h] BYREF
  HPROPSHEETPAGE v10[2]; // [rsp+120h] [rbp+20h] BYREF
  __int64 v11; // [rsp+130h] [rbp+30h]

  v7 = SetThreadDpiAwarenessContext(-2);
  *(_OWORD *)v10 = 0;
  v11 = 0;
  v2 = 0;
  while ( 1 )
  {
    constPropSheetPagePointer.dwSize = 104;
    memset_0(&constPropSheetPagePointer.dwFlags, 0, 0x64u);
    constPropSheetPagePointer.hInstance = &_ImageBase;
    constPropSheetPagePointer.lParam = (LPARAM)this;
    constPropSheetPagePointer.dwFlags = 4096;
    constPropSheetPagePointer.pszTemplate = (LPCWSTR)`CreateArchiveWizard::Run'::`2'::pages[3 * v2];
    constPropSheetPagePointer.pszHeaderTitle = (LPCWSTR)qword_1800752C8[3 * v2];
    constPropSheetPagePointer.pfnDlgProc = (DLGPROC)off_1800752D0[3 * v2];
    v3 = CreatePropertySheetPageW(&constPropSheetPagePointer);
    v10[v2] = v3;
    if ( !v3 )
      break;
    if ( ++v2 >= 3 )
    {
      v8.dwSize = 96;
      memset_0(&v8.dwFlags, 0, 0x5Cu);
      v8.hInstance = &_ImageBase;
      v8.dwFlags = 16388;
      v8.ppsp = (LPCPROPSHEETPAGEW)v10;
      v8.nPages = 3;
      v8.nStartPage = 0;
      v8.pszCaption = (LPCWSTR)10610;
      v8.hIcon = (HICON)124;
      v4 = PropertySheetW(&v8);
      SetThreadDpiAwarenessContext(v7);
      return v4;
    }
  }
  ShellMessageBoxW(&_ImageBase, 0, (LPCWSTR)0x27A5, (LPCWSTR)0x2941, 0x10u);
  for ( i = 0; i < v2; ++i )
    DestroyPropertySheetPage(v10[i]);
  SetThreadDpiAwarenessContext(v7);
  return -1;
}

```

## disassembly

```asm
0x180051d88  push    rbp
0x180051d8a  push    rbx
0x180051d8b  push    rsi
0x180051d8c  push    rdi
0x180051d8d  lea     rbp, [rsp-48h]
0x180051d92  sub     rsp, 148h
0x180051d99  mov     rax, cs:__security_cookie
0x180051da0  xor     rax, rsp
0x180051da3  mov     [rbp+60h+var_28], rax
0x180051da7  mov     rdi, rcx
0x180051daa  mov     rcx, 0FFFFFFFFFFFFFFFEh
0x180051db1  call    cs:__imp_SetThreadDpiAwarenessContext
0x180051db7  mov     [rsp+160h+var_120], rax
0x180051dbc  lea     rax, [rsp+160h+var_120]
0x180051dc1  mov     [rsp+160h+var_130], rax
0x180051dc6  mov     [rsp+160h+var_128], 1
0x180051dcb  xorps   xmm0, xmm0
0x180051dce  xor     eax, eax
0x180051dd0  movups  xmmword ptr [rbp+60h+var_40], xmm0
0x180051dd4  mov     [rbp+60h+var_30], rax
0x180051dd8  xor     ebx, ebx
0x180051dda  lea     rsi, __ImageBase
0x180051de1  mov     [rbp+60h+constPropSheetPagePointer.dwSize], 68h ; 'h'
0x180051de8  xor     edx, edx; Val
0x180051dea  lea     r8d, [rdx+64h]; Size
0x180051dee  lea     rcx, [rbp+60h+constPropSheetPagePointer.dwFlags]; void *
0x180051df2  call    memset_0
0x180051df7  mov     [rbp+60h+constPropSheetPagePointer.hInstance], rsi
0x180051dfb  mov     [rbp+60h+constPropSheetPagePointer.lParam], rdi
0x180051dff  mov     [rbp+60h+constPropSheetPagePointer.dwFlags], 1000h
0x180051e06  lea     rcx, [rbx+rbx*2]
0x180051e0a  mov     rax, ds:rva ?pages@?1??Run@CreateArchiveWizard@@AEAA_JXZ@4QBUPropertySheetPageData@@B[rsi+rcx*8]; PropertySheetPageData const near * const `CreateArchiveWizard::Run(void)'::`2'::pages ...
0x180051e12  mov     qword ptr [rbp+60h+constPropSheetPagePointer.10h], rax
0x180051e16  mov     rax, ds:rva qword_1800752C8[rsi+rcx*8]
0x180051e1e  mov     [rbp+60h+constPropSheetPagePointer.pszHeaderTitle], rax
0x180051e22  mov     rax, ds:rva off_1800752D0[rsi+rcx*8]
0x180051e2a  mov     [rbp+60h+constPropSheetPagePointer.pfnDlgProc], rax
0x180051e2e  lea     rcx, [rbp+60h+constPropSheetPagePointer]; constPropSheetPagePointer
0x180051e32  call    CreatePropertySheetPageW
0x180051e37  mov     [rbp+rbx*8+60h+var_40], rax
0x180051e3c  test    rax, rax
0x180051e3f  jz      short loc_180051EB6
0x180051e41  inc     rbx
0x180051e44  cmp     rbx, 3
0x180051e48  jb      short loc_180051DE1
0x180051e4a  mov     [rsp+160h+var_110.dwSize], 60h ; '`'
0x180051e52  xor     edx, edx; Val
0x180051e54  lea     r8d, [rdx+5Ch]; Size
0x180051e58  lea     rcx, [rsp+160h+var_110.dwFlags]; void *
0x180051e5d  call    memset_0
0x180051e62  mov     [rsp+160h+var_110.hInstance], rsi
0x180051e67  mov     [rsp+160h+var_110.dwFlags], 4004h
0x180051e6f  lea     rax, [rbp+60h+var_40]
0x180051e73  mov     qword ptr [rbp+60h+var_110.38h], rax
0x180051e77  mov     [rsp+160h+var_110.nPages], 3
0x180051e7f  mov     dword ptr [rbp+60h+var_110.30h], 0
0x180051e86  mov     [rsp+160h+var_110.pszCaption], 2972h
0x180051e8f  mov     qword ptr [rsp+160h+var_110.18h], 7Ch ; '|'
0x180051e98  lea     rcx, [rsp+160h+var_110]; LPCPROPSHEETHEADERW
0x180051e9d  call    PropertySheetW
0x180051ea2  mov     rbx, rax
0x180051ea5  mov     rcx, [rsp+160h+var_120]
0x180051eaa  call    cs:__imp_SetThreadDpiAwarenessContext
0x180051eb0  nop
0x180051eb1  mov     rax, rbx
0x180051eb4  jmp     short loc_180051EFE
0x180051eb6  mov     [rsp+160h+fuStyle], 10h; fuStyle
0x180051ebe  xor     edx, edx; hWnd
0x180051ec0  mov     r9d, 2941h; lpcTitle
0x180051ec6  mov     r8d, 27A5h; lpcText
0x180051ecc  mov     rcx, rsi; hAppInst
0x180051ecf  call    cs:__imp_ShellMessageBoxW
0x180051ed5  xor     edi, edi
0x180051ed7  test    rbx, rbx
0x180051eda  jz      short loc_180051EEE
0x180051edc  mov     rcx, [rbp+rdi*8+60h+var_40]; HPROPSHEETPAGE
0x180051ee1  call    DestroyPropertySheetPage
0x180051ee6  inc     rdi
0x180051ee9  cmp     rdi, rbx
0x180051eec  jb      short loc_180051EDC
0x180051eee  mov     rcx, [rsp+160h+var_120]
0x180051ef3  call    cs:__imp_SetThreadDpiAwarenessContext
0x180051ef9  nop
0x180051efa  or      rax, 0FFFFFFFFFFFFFFFFh
0x180051efe  mov     rcx, [rbp+60h+var_28]
0x180051f02  xor     rcx, rsp; StackCookie
0x180051f05  call    __security_check_cookie
0x180051f0a  add     rsp, 148h
0x180051f11  pop     rdi
0x180051f12  pop     rsi
0x180051f13  pop     rbx
0x180051f14  pop     rbp
0x180051f15  retn
```
