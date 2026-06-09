# MessageBoxHelper::ShellMessageBoxTextScaled_unsigned_short_const____0

- ea: `0x1800479c4`
- end: `0x180047a87`
- name: `MessageBoxHelper::ShellMessageBoxTextScaled_unsigned_short_const____0`
- size: `195`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, loader_planting`

## callers

- `0x180047cc8`

## callees

- `0x18003b124`
- `0x1800479c4`
- `0x180071010`

## import_xrefs

- `SHLWAPI!__imp_ShellMessageBoxW` at `0x180047a63`
- `SHLWAPI!__imp_ShellMessageBoxW` at `0x180047a63`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180047a06`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180047a06`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x1800479ec`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x1800479ec`

## string_xrefs

- `0x1800479df`: `shlwapi.dll`

## pseudocode

```c
__int64 MessageBoxHelper::ShellMessageBoxTextScaled_unsigned_short_const____0(
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
  HMODULE v11; // [rsp+68h] [rbp+20h] BYREF
  va_list va; // [rsp+68h] [rbp+20h]
  __int64 v13; // [rsp+70h] [rbp+28h]
  __int64 v14; // [rsp+78h] [rbp+30h]
  va_list va1; // [rsp+80h] [rbp+38h] BYREF

  va_start(va1, a3);
  va_start(va, a3);
  v11 = va_arg(va1, HMODULE);
  v13 = va_arg(va1, _QWORD);
  v14 = va_arg(va1, _QWORD);
  v3 = g_hmodThisDll;
  LibraryW = LoadLibraryW(L"shlwapi.dll");
  v11 = LibraryW;
  if ( LibraryW && (ProcAddress = GetProcAddress(LibraryW, "ShellMessageBoxInternal")) != 0 )
    v8 = ((__int64 (__fastcall *)(HINSTANCE, HWND, __int64, const WCHAR *, __int64, int, __int64))ProcAddress)(
           v3,
           a2,
           1,
           a3,
           10055,
           48,
           v14);
  else
    v8 = ShellMessageBoxW(v3, a2, a3, (LPCWSTR)0x2747, 0x30u, v14);
  v9 = v8;
  wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&int FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&int FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>((HMODULE *)va);
  return v9;
}

```

## disassembly

```asm
0x1800479c4  mov     [rsp+arg_0], rbx
0x1800479c9  mov     [rsp+arg_8], rsi
0x1800479ce  mov     [rsp+arg_18], r9
0x1800479d3  push    rdi
0x1800479d4  sub     rsp, 40h
0x1800479d8  mov     rsi, cs:g_hmodThisDll
0x1800479df  lea     rcx, aShlwapiDll_0; "shlwapi.dll"
0x1800479e6  mov     rbx, r8
0x1800479e9  mov     rdi, rdx
0x1800479ec  call    cs:__imp_LoadLibraryW
0x1800479f2  mov     [rsp+48h+arg_18], rax
0x1800479f7  test    rax, rax
0x1800479fa  jz      short loc_180047A42
0x1800479fc  lea     rdx, aShellmessagebo; "ShellMessageBoxInternal"
0x180047a03  mov     rcx, rax; hModule
0x180047a06  call    cs:__imp_GetProcAddress
0x180047a0c  test    rax, rax
0x180047a0f  jz      short loc_180047A42
0x180047a11  mov     rdx, [rsp+48h+arg_28]
0x180047a16  mov     r9, rbx
0x180047a19  mov     [rsp+48h+var_18], rdx
0x180047a1e  mov     r8d, 1
0x180047a24  mov     dword ptr [rsp+48h+var_20], 30h ; '0'
0x180047a2c  mov     rdx, rdi
0x180047a2f  mov     rcx, rsi
0x180047a32  mov     qword ptr [rsp+48h+fuStyle], 2747h
0x180047a3b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180047a40  jmp     short loc_180047A69
0x180047a42  mov     rax, [rsp+48h+arg_28]
0x180047a47  mov     r9d, 2747h; lpcTitle
0x180047a4d  mov     [rsp+48h+var_20], rax
0x180047a52  mov     r8, rbx; lpcText
0x180047a55  mov     rdx, rdi; hWnd
0x180047a58  mov     [rsp+48h+fuStyle], 30h ; '0'; fuStyle
0x180047a60  mov     rcx, rsi; hAppInst
0x180047a63  call    cs:__imp_ShellMessageBoxW
0x180047a69  lea     rcx, [rsp+48h+arg_18]
0x180047a6e  mov     ebx, eax
0x180047a70  call    ??1?$unique_storage@U?$resource_policy@PEAUHINSTANCE__@@P6AHPEAU1@@Z$1?FreeLibrary@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>(void)
0x180047a75  mov     rsi, [rsp+48h+arg_8]
0x180047a7a  mov     eax, ebx
0x180047a7c  mov     rbx, [rsp+48h+arg_0]
0x180047a81  add     rsp, 40h
0x180047a85  pop     rdi
0x180047a86  retn
```
