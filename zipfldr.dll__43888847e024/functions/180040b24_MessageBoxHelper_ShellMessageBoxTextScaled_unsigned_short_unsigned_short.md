# MessageBoxHelper::ShellMessageBoxTextScaled_unsigned_short___unsigned_short___

- ea: `0x180040b24`
- end: `0x180040c00`
- name: `MessageBoxHelper::ShellMessageBoxTextScaled_unsigned_short___unsigned_short___`
- size: `220`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, loader_planting`

## callers

- `0x18002c184`

## callees

- `0x18003b124`
- `0x180040b24`
- `0x180071010`

## import_xrefs

- `SHLWAPI!__imp_ShellMessageBoxW` at `0x180040be1`
- `SHLWAPI!__imp_ShellMessageBoxW` at `0x180040be1`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180040b5e`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180040b5e`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x180040b44`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x180040b44`

## string_xrefs

- `0x180040b3a`: `shlwapi.dll`

## pseudocode

```c
__int64 MessageBoxHelper::ShellMessageBoxTextScaled_unsigned_short___unsigned_short___(
        __int64 a1,
        HWND a2,
        __int64 a3,
        ...)
{
  HINSTANCE v3; // rdi
  HMODULE LibraryW; // rax
  FARPROC ProcAddress; // rax
  int v7; // eax
  unsigned int v8; // ebx
  HMODULE v10; // [rsp+78h] [rbp+20h] BYREF
  va_list va; // [rsp+78h] [rbp+20h]
  __int64 v12; // [rsp+80h] [rbp+28h]
  __int64 v13; // [rsp+88h] [rbp+30h]
  __int64 v14; // [rsp+90h] [rbp+38h]
  va_list va1; // [rsp+98h] [rbp+40h] BYREF

  va_start(va1, a3);
  va_start(va, a3);
  v10 = va_arg(va1, HMODULE);
  v12 = va_arg(va1, _QWORD);
  v13 = va_arg(va1, _QWORD);
  v14 = va_arg(va1, _QWORD);
  v3 = g_hmodThisDll;
  LibraryW = LoadLibraryW(L"shlwapi.dll");
  v10 = LibraryW;
  if ( LibraryW && (ProcAddress = GetProcAddress(LibraryW, "ShellMessageBoxInternal")) != 0 )
    v7 = ((__int64 (__fastcall *)(HINSTANCE, HWND, __int64, __int64, __int64, int, __int64, __int64))ProcAddress)(
           v3,
           a2,
           1,
           10419,
           10055,
           48,
           v13,
           v14);
  else
    v7 = ShellMessageBoxW(v3, a2, (LPCWSTR)0x28B3, (LPCWSTR)0x2747, 0x30u, v13, v14);
  v8 = v7;
  wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&int FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&int FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>((HMODULE *)va);
  return v8;
}

```

## disassembly

```asm
0x180040b24  mov     [rsp+arg_0], rbx
0x180040b29  mov     [rsp+arg_18], r9
0x180040b2e  push    rdi
0x180040b2f  sub     rsp, 50h
0x180040b33  mov     rdi, cs:g_hmodThisDll
0x180040b3a  lea     rcx, aShlwapiDll_0; "shlwapi.dll"
0x180040b41  mov     rbx, rdx
0x180040b44  call    cs:__imp_LoadLibraryW
0x180040b4a  mov     [rsp+58h+arg_18], rax
0x180040b4f  test    rax, rax
0x180040b52  jz      short loc_180040BAD
0x180040b54  lea     rdx, aShellmessagebo; "ShellMessageBoxInternal"
0x180040b5b  mov     rcx, rax; hModule
0x180040b5e  call    cs:__imp_GetProcAddress
0x180040b64  test    rax, rax
0x180040b67  jz      short loc_180040BAD
0x180040b69  mov     rdx, [rsp+58h+arg_30]
0x180040b71  mov     r9d, 28B3h
0x180040b77  mov     [rsp+58h+var_20], rdx
0x180040b7c  mov     r8d, 1
0x180040b82  mov     rdx, [rsp+58h+arg_28]
0x180040b8a  mov     rcx, rdi
0x180040b8d  mov     [rsp+58h+var_28], rdx
0x180040b92  mov     rdx, rbx
0x180040b95  mov     dword ptr [rsp+58h+var_30], 30h ; '0'
0x180040b9d  mov     qword ptr [rsp+58h+fuStyle], 2747h
0x180040ba6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180040bab  jmp     short loc_180040BE7
0x180040bad  mov     rax, [rsp+58h+arg_30]
0x180040bb5  mov     r9d, 2747h; lpcTitle
0x180040bbb  mov     [rsp+58h+var_28], rax
0x180040bc0  mov     r8d, 28B3h; lpcText
0x180040bc6  mov     rax, [rsp+58h+arg_28]
0x180040bce  mov     rdx, rbx; hWnd
0x180040bd1  mov     [rsp+58h+var_30], rax
0x180040bd6  mov     rcx, rdi; hAppInst
0x180040bd9  mov     [rsp+58h+fuStyle], 30h ; '0'; fuStyle
0x180040be1  call    cs:__imp_ShellMessageBoxW
0x180040be7  lea     rcx, [rsp+58h+arg_18]
0x180040bec  mov     ebx, eax
0x180040bee  call    ??1?$unique_storage@U?$resource_policy@PEAUHINSTANCE__@@P6AHPEAU1@@Z$1?FreeLibrary@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>(void)
0x180040bf3  mov     eax, ebx
0x180040bf5  mov     rbx, [rsp+58h+arg_0]
0x180040bfa  add     rsp, 50h
0x180040bfe  pop     rdi
0x180040bff  retn
```
