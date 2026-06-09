# MessageBoxHelper::ShellMessageBoxTextScaled_unsigned_short_const___

- ea: `0x180040c08`
- end: `0x180040cc5`
- name: `MessageBoxHelper::ShellMessageBoxTextScaled_unsigned_short_const___`
- size: `189`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config, loader_planting`

## callers

- `0x18000b430`
- `0x180041050`

## callees

- `0x18003b124`
- `0x180040c08`
- `0x180071010`

## import_xrefs

- `SHLWAPI!__imp_ShellMessageBoxW` at `0x180040ca8`
- `SHLWAPI!__imp_ShellMessageBoxW` at `0x180040ca8`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180040c46`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180040c46`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x180040c2c`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x180040c2c`

## string_xrefs

- `0x180040c1c`: `shlwapi.dll`

## pseudocode

```c
__int64 __fastcall MessageBoxHelper::ShellMessageBoxTextScaled_unsigned_short_const___(
        HMODULE a1,
        HWND a2,
        const WCHAR *a3,
        const WCHAR *a4,
        UINT fuStyle,
        __int64 a6)
{
  HINSTANCE v6; // rbp
  HMODULE LibraryW; // rax
  FARPROC ProcAddress; // rax
  int v12; // eax
  unsigned int v13; // ebx
  HMODULE v15; // [rsp+70h] [rbp+8h] BYREF

  v15 = a1;
  v6 = g_hmodThisDll;
  LibraryW = LoadLibraryW(L"shlwapi.dll");
  v15 = LibraryW;
  if ( LibraryW && (ProcAddress = GetProcAddress(LibraryW, "ShellMessageBoxInternal")) != 0 )
    v12 = ((__int64 (__fastcall *)(HINSTANCE, HWND, __int64, const WCHAR *, const WCHAR *, UINT, __int64))ProcAddress)(
            v6,
            a2,
            1,
            a3,
            a4,
            fuStyle,
            a6);
  else
    v12 = ShellMessageBoxW(v6, a2, a3, a4, fuStyle, a6);
  v13 = v12;
  wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&int FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&int FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>(&v15);
  return v13;
}

```

## disassembly

```asm
0x180040c08  mov     [rsp+arg_0], rcx
0x180040c0d  push    rbx
0x180040c0e  push    rbp
0x180040c0f  push    rsi
0x180040c10  push    rdi
0x180040c11  sub     rsp, 48h
0x180040c15  mov     rbp, cs:g_hmodThisDll
0x180040c1c  lea     rcx, aShlwapiDll_0; "shlwapi.dll"
0x180040c23  mov     rbx, r9
0x180040c26  mov     rdi, r8
0x180040c29  mov     rsi, rdx
0x180040c2c  call    cs:__imp_LoadLibraryW
0x180040c32  mov     [rsp+68h+arg_0], rax
0x180040c37  test    rax, rax
0x180040c3a  jz      short loc_180040C84
0x180040c3c  lea     rdx, aShellmessagebo; "ShellMessageBoxInternal"
0x180040c43  mov     rcx, rax; hModule
0x180040c46  call    cs:__imp_GetProcAddress
0x180040c4c  test    rax, rax
0x180040c4f  jz      short loc_180040C84
0x180040c51  mov     rdx, [rsp+68h+arg_28]
0x180040c59  mov     r9, rdi
0x180040c5c  mov     [rsp+68h+var_38], rdx
0x180040c61  mov     r8d, 1
0x180040c67  mov     edx, [rsp+68h+arg_20]
0x180040c6e  mov     rcx, rbp
0x180040c71  mov     dword ptr [rsp+68h+var_40], edx
0x180040c75  mov     rdx, rsi
0x180040c78  mov     qword ptr [rsp+68h+fuStyle], rbx
0x180040c7d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180040c82  jmp     short loc_180040CAE
0x180040c84  mov     rax, [rsp+68h+arg_28]
0x180040c8c  mov     r9, rbx; lpcTitle
0x180040c8f  mov     [rsp+68h+var_40], rax
0x180040c94  mov     r8, rdi; lpcText
0x180040c97  mov     eax, [rsp+68h+arg_20]
0x180040c9e  mov     rdx, rsi; hWnd
0x180040ca1  mov     rcx, rbp; hAppInst
0x180040ca4  mov     [rsp+68h+fuStyle], eax; fuStyle
0x180040ca8  call    cs:__imp_ShellMessageBoxW
0x180040cae  lea     rcx, [rsp+68h+arg_0]
0x180040cb3  mov     ebx, eax
0x180040cb5  call    ??1?$unique_storage@U?$resource_policy@PEAUHINSTANCE__@@P6AHPEAU1@@Z$1?FreeLibrary@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>(void)
0x180040cba  mov     eax, ebx
0x180040cbc  add     rsp, 48h
0x180040cc0  pop     rdi
0x180040cc1  pop     rsi
0x180040cc2  pop     rbp
0x180040cc3  pop     rbx
0x180040cc4  retn
```
