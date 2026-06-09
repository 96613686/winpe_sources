# MessageBoxHelper::ShellMessageBoxTextScaled_unsigned_int_

- ea: `0x1800409a8`
- end: `0x180040a60`
- name: `MessageBoxHelper::ShellMessageBoxTextScaled_unsigned_int_`
- size: `184`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, loader_planting`

## callers

- `0x18000b430`

## callees

- `0x18003b124`
- `0x1800409a8`
- `0x180071010`

## import_xrefs

- `SHLWAPI!__imp_ShellMessageBoxW` at `0x180040a41`
- `SHLWAPI!__imp_ShellMessageBoxW` at `0x180040a41`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800409e2`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800409e2`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x1800409c8`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x1800409c8`

## string_xrefs

- `0x1800409be`: `shlwapi.dll`

## pseudocode

```c
__int64 MessageBoxHelper::ShellMessageBoxTextScaled_unsigned_int_(__int64 a1, HWND a2, __int64 a3, ...)
{
  HINSTANCE v3; // rdi
  HMODULE LibraryW; // rax
  FARPROC ProcAddress; // rax
  int v7; // eax
  unsigned int v8; // ebx
  HMODULE v10; // [rsp+68h] [rbp+20h] BYREF
  va_list va; // [rsp+68h] [rbp+20h]
  __int64 v12; // [rsp+70h] [rbp+28h]
  __int64 v13; // [rsp+78h] [rbp+30h]
  va_list va1; // [rsp+80h] [rbp+38h] BYREF

  va_start(va1, a3);
  va_start(va, a3);
  v10 = va_arg(va1, HMODULE);
  v12 = va_arg(va1, _QWORD);
  v13 = va_arg(va1, _QWORD);
  v3 = g_hmodThisDll;
  LibraryW = LoadLibraryW(L"shlwapi.dll");
  v10 = LibraryW;
  if ( LibraryW && (ProcAddress = GetProcAddress(LibraryW, "ShellMessageBoxInternal")) != 0 )
    v7 = ((__int64 (__fastcall *)(HINSTANCE, HWND, __int64, __int64, __int64, int, _DWORD))ProcAddress)(
           v3,
           a2,
           1,
           10601,
           10055,
           52,
           v13);
  else
    v7 = ShellMessageBoxW(v3, a2, (LPCWSTR)0x2969, (LPCWSTR)0x2747, 0x34u, v13);
  v8 = v7;
  wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&int FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&int FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>((HMODULE *)va);
  return v8;
}

```

## disassembly

```asm
0x1800409a8  mov     [rsp+arg_0], rbx
0x1800409ad  mov     [rsp+arg_18], r9
0x1800409b2  push    rdi
0x1800409b3  sub     rsp, 40h
0x1800409b7  mov     rdi, cs:g_hmodThisDll
0x1800409be  lea     rcx, aShlwapiDll_0; "shlwapi.dll"
0x1800409c5  mov     rbx, rdx
0x1800409c8  call    cs:__imp_LoadLibraryW
0x1800409ce  mov     [rsp+48h+arg_18], rax
0x1800409d3  test    rax, rax
0x1800409d6  jz      short loc_180040A1F
0x1800409d8  lea     rdx, aShellmessagebo; "ShellMessageBoxInternal"
0x1800409df  mov     rcx, rax; hModule
0x1800409e2  call    cs:__imp_GetProcAddress
0x1800409e8  test    rax, rax
0x1800409eb  jz      short loc_180040A1F
0x1800409ed  mov     edx, dword ptr [rsp+48h+arg_28]
0x1800409f1  mov     r9d, 2969h
0x1800409f7  mov     [rsp+48h+var_18], edx
0x1800409fb  mov     r8d, 1
0x180040a01  mov     [rsp+48h+var_20], 34h ; '4'
0x180040a09  mov     rdx, rbx
0x180040a0c  mov     rcx, rdi
0x180040a0f  mov     qword ptr [rsp+48h+fuStyle], 2747h
0x180040a18  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180040a1d  jmp     short loc_180040A47
0x180040a1f  mov     eax, dword ptr [rsp+48h+arg_28]
0x180040a23  mov     r9d, 2747h; lpcTitle
0x180040a29  mov     [rsp+48h+var_20], eax
0x180040a2d  mov     r8d, 2969h; lpcText
0x180040a33  mov     rdx, rbx; hWnd
0x180040a36  mov     [rsp+48h+fuStyle], 34h ; '4'; fuStyle
0x180040a3e  mov     rcx, rdi; hAppInst
0x180040a41  call    cs:__imp_ShellMessageBoxW
0x180040a47  lea     rcx, [rsp+48h+arg_18]
0x180040a4c  mov     ebx, eax
0x180040a4e  call    ??1?$unique_storage@U?$resource_policy@PEAUHINSTANCE__@@P6AHPEAU1@@Z$1?FreeLibrary@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>(void)
0x180040a53  mov     eax, ebx
0x180040a55  mov     rbx, [rsp+48h+arg_0]
0x180040a5a  add     rsp, 40h
0x180040a5e  pop     rdi
0x180040a5f  retn
```
