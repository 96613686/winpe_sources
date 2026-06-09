# MessageBoxHelper::ShellMessageBoxTextScaled_unsigned_short_const___unsigned_short___

- ea: `0x180047a90`
- end: `0x180047b73`
- name: `MessageBoxHelper::ShellMessageBoxTextScaled_unsigned_short_const___unsigned_short___`
- size: `227`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, loader_planting`

## callers

- `0x180047cc8`

## callees

- `0x18003b124`
- `0x180047a90`
- `0x180071010`

## import_xrefs

- `SHLWAPI!__imp_ShellMessageBoxW` at `0x180047b4f`
- `SHLWAPI!__imp_ShellMessageBoxW` at `0x180047b4f`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180047ad2`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180047ad2`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x180047ab8`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x180047ab8`

## string_xrefs

- `0x180047aab`: `shlwapi.dll`

## pseudocode

```c
__int64 MessageBoxHelper::ShellMessageBoxTextScaled_unsigned_short_const___unsigned_short___(
        __int64 a1,
        HWND a2,
        const WCHAR *a3,
        ...)
{
  HINSTANCE v3; // rsi
  HMODULE LibraryW; // rax
  FARPROC ProcAddress; // rax
  int v8; // eax
  unsigned int v9; // ebx
  HMODULE v11; // [rsp+78h] [rbp+20h] BYREF
  va_list va; // [rsp+78h] [rbp+20h]
  __int64 v13; // [rsp+80h] [rbp+28h]
  __int64 v14; // [rsp+88h] [rbp+30h]
  __int64 v15; // [rsp+90h] [rbp+38h]
  va_list va1; // [rsp+98h] [rbp+40h] BYREF

  va_start(va1, a3);
  va_start(va, a3);
  v11 = va_arg(va1, HMODULE);
  v13 = va_arg(va1, _QWORD);
  v14 = va_arg(va1, _QWORD);
  v15 = va_arg(va1, _QWORD);
  v3 = g_hmodThisDll;
  LibraryW = LoadLibraryW(L"shlwapi.dll");
  v11 = LibraryW;
  if ( LibraryW && (ProcAddress = GetProcAddress(LibraryW, "ShellMessageBoxInternal")) != 0 )
    v8 = ((__int64 (__fastcall *)(HINSTANCE, HWND, __int64, const WCHAR *, __int64, int, __int64, __int64))ProcAddress)(
           v3,
           a2,
           1,
           a3,
           10055,
           48,
           v14,
           v15);
  else
    v8 = ShellMessageBoxW(v3, a2, a3, (LPCWSTR)0x2747, 0x30u, v14, v15);
  v9 = v8;
  wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&int FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&int FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>((HMODULE *)va);
  return v9;
}

```

## disassembly

```asm
0x180047a90  mov     [rsp+arg_0], rbx
0x180047a95  mov     [rsp+arg_8], rsi
0x180047a9a  mov     [rsp+arg_18], r9
0x180047a9f  push    rdi
0x180047aa0  sub     rsp, 50h
0x180047aa4  mov     rsi, cs:g_hmodThisDll
0x180047aab  lea     rcx, aShlwapiDll_0; "shlwapi.dll"
0x180047ab2  mov     rbx, r8
0x180047ab5  mov     rdi, rdx
0x180047ab8  call    cs:__imp_LoadLibraryW
0x180047abe  mov     [rsp+58h+arg_18], rax
0x180047ac3  test    rax, rax
0x180047ac6  jz      short loc_180047B1E
0x180047ac8  lea     rdx, aShellmessagebo; "ShellMessageBoxInternal"
0x180047acf  mov     rcx, rax; hModule
0x180047ad2  call    cs:__imp_GetProcAddress
0x180047ad8  test    rax, rax
0x180047adb  jz      short loc_180047B1E
0x180047add  mov     rdx, [rsp+58h+arg_30]
0x180047ae5  mov     r9, rbx
0x180047ae8  mov     [rsp+58h+var_20], rdx
0x180047aed  mov     r8d, 1
0x180047af3  mov     rdx, [rsp+58h+arg_28]
0x180047afb  mov     rcx, rsi
0x180047afe  mov     [rsp+58h+var_28], rdx
0x180047b03  mov     rdx, rdi
0x180047b06  mov     dword ptr [rsp+58h+var_30], 30h ; '0'
0x180047b0e  mov     qword ptr [rsp+58h+fuStyle], 2747h
0x180047b17  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180047b1c  jmp     short loc_180047B55
0x180047b1e  mov     rax, [rsp+58h+arg_30]
0x180047b26  mov     r9d, 2747h; lpcTitle
0x180047b2c  mov     [rsp+58h+var_28], rax
0x180047b31  mov     r8, rbx; lpcText
0x180047b34  mov     rax, [rsp+58h+arg_28]
0x180047b3c  mov     rdx, rdi; hWnd
0x180047b3f  mov     [rsp+58h+var_30], rax
0x180047b44  mov     rcx, rsi; hAppInst
0x180047b47  mov     [rsp+58h+fuStyle], 30h ; '0'; fuStyle
0x180047b4f  call    cs:__imp_ShellMessageBoxW
0x180047b55  lea     rcx, [rsp+58h+arg_18]
0x180047b5a  mov     ebx, eax
0x180047b5c  call    ??1?$unique_storage@U?$resource_policy@PEAUHINSTANCE__@@P6AHPEAU1@@Z$1?FreeLibrary@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>(void)
0x180047b61  mov     rsi, [rsp+58h+arg_8]
0x180047b66  mov     eax, ebx
0x180047b68  mov     rbx, [rsp+58h+arg_0]
0x180047b6d  add     rsp, 50h
0x180047b71  pop     rdi
0x180047b72  retn
```
