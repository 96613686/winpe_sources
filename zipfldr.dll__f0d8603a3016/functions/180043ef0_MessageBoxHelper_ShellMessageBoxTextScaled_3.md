# MessageBoxHelper::ShellMessageBoxTextScaled___3

- ea: `0x180043ef0`
- end: `0x180043f96`
- name: `MessageBoxHelper::ShellMessageBoxTextScaled___3`
- size: `166`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, loader_planting`

## callers

- `0x18002cc30`

## callees

- `0x18003b124`
- `0x180043ef0`
- `0x180071010`

## import_xrefs

- `SHLWAPI!__imp_ShellMessageBoxW` at `0x180043f77`
- `SHLWAPI!__imp_ShellMessageBoxW` at `0x180043f77`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180043f2a`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180043f2a`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x180043f10`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x180043f10`

## string_xrefs

- `0x180043f06`: `shlwapi.dll`

## pseudocode

```c
__int64 MessageBoxHelper::ShellMessageBoxTextScaled___3(__int64 a1, HWND a2, __int64 a3, ...)
{
  HINSTANCE v3; // rdi
  HMODULE LibraryW; // rax
  FARPROC ProcAddress; // rax
  int v7; // eax
  unsigned int v8; // ebx
  HMODULE v10; // [rsp+68h] [rbp+20h] BYREF
  va_list va; // [rsp+68h] [rbp+20h]
  va_list va1; // [rsp+70h] [rbp+28h] BYREF

  va_start(va1, a3);
  va_start(va, a3);
  v10 = va_arg(va1, HMODULE);
  v3 = g_hmodThisDll;
  LibraryW = LoadLibraryW(L"shlwapi.dll");
  v10 = LibraryW;
  if ( LibraryW && (ProcAddress = GetProcAddress(LibraryW, "ShellMessageBoxInternal")) != 0 )
    v7 = ((__int64 (__fastcall *)(HINSTANCE, HWND, __int64, __int64, __int64, int))ProcAddress)(
           v3,
           a2,
           1,
           10192,
           10133,
           64);
  else
    v7 = ShellMessageBoxW(v3, a2, (LPCWSTR)0x27D0, (LPCWSTR)0x2795, 0x40u);
  v8 = v7;
  wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&int FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&int FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>((HMODULE *)va);
  return v8;
}

```

## disassembly

```asm
0x180043ef0  mov     [rsp+arg_0], rbx
0x180043ef5  mov     [rsp+arg_18], r9
0x180043efa  push    rdi
0x180043efb  sub     rsp, 40h
0x180043eff  mov     rdi, cs:g_hmodThisDll
0x180043f06  lea     rcx, aShlwapiDll_0; "shlwapi.dll"
0x180043f0d  mov     rbx, rdx
0x180043f10  call    cs:__imp_LoadLibraryW
0x180043f16  mov     [rsp+48h+arg_18], rax
0x180043f1b  test    rax, rax
0x180043f1e  jz      short loc_180043F5F
0x180043f20  lea     rdx, aShellmessagebo; "ShellMessageBoxInternal"
0x180043f27  mov     rcx, rax; hModule
0x180043f2a  call    cs:__imp_GetProcAddress
0x180043f30  test    rax, rax
0x180043f33  jz      short loc_180043F5F
0x180043f35  mov     [rsp+48h+var_20], 40h ; '@'
0x180043f3d  mov     r9d, 27D0h
0x180043f43  mov     r8d, 1
0x180043f49  mov     qword ptr [rsp+48h+fuStyle], 2795h
0x180043f52  mov     rdx, rbx
0x180043f55  mov     rcx, rdi
0x180043f58  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180043f5d  jmp     short loc_180043F7D
0x180043f5f  mov     r9d, 2795h; lpcTitle
0x180043f65  mov     [rsp+48h+fuStyle], 40h ; '@'; fuStyle
0x180043f6d  mov     rdx, rbx; hWnd
0x180043f70  mov     rcx, rdi; hAppInst
0x180043f73  lea     r8d, [r9+3Bh]; lpcText
0x180043f77  call    cs:__imp_ShellMessageBoxW
0x180043f7d  lea     rcx, [rsp+48h+arg_18]
0x180043f82  mov     ebx, eax
0x180043f84  call    ??1?$unique_storage@U?$resource_policy@PEAUHINSTANCE__@@P6AHPEAU1@@Z$1?FreeLibrary@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>(void)
0x180043f89  mov     eax, ebx
0x180043f8b  mov     rbx, [rsp+48h+arg_0]
0x180043f90  add     rsp, 40h
0x180043f94  pop     rdi
0x180043f95  retn
```
