# MessageBoxHelper::ShellMessageBoxTextScaled__

- ea: `0x18003ae64`
- end: `0x18003af0c`
- name: `MessageBoxHelper::ShellMessageBoxTextScaled__`
- size: `168`
- prototype: `__int64(__int64, HWND, __int64, ...)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, loader_planting`

## callers

- `0x18001f284`

## callees

- `0x18003ae64`
- `0x18003b124`
- `0x180071010`

## import_xrefs

- `SHLWAPI!__imp_ShellMessageBoxW` at `0x18003aeed`
- `SHLWAPI!__imp_ShellMessageBoxW` at `0x18003aeed`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18003ae9e`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18003ae9e`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x18003ae84`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x18003ae84`

## string_xrefs

- `0x18003ae7a`: `shlwapi.dll`

## pseudocode

```c
__int64 MessageBoxHelper::ShellMessageBoxTextScaled__(__int64 a1, HWND a2, __int64 a3, ...)
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
           10189,
           10055,
           48);
  else
    v7 = ShellMessageBoxW(v3, a2, (LPCWSTR)0x27CD, (LPCWSTR)0x2747, 0x30u);
  v8 = v7;
  wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&int FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&int FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>((HMODULE *)va);
  return v8;
}

```

## disassembly

```asm
0x18003ae64  mov     [rsp+arg_0], rbx
0x18003ae69  mov     [rsp+arg_18], r9
0x18003ae6e  push    rdi
0x18003ae6f  sub     rsp, 40h
0x18003ae73  mov     rdi, cs:g_hmodThisDll
0x18003ae7a  lea     rcx, aShlwapiDll_0; "shlwapi.dll"
0x18003ae81  mov     rbx, rdx
0x18003ae84  call    cs:__imp_LoadLibraryW
0x18003ae8a  mov     [rsp+48h+arg_18], rax
0x18003ae8f  test    rax, rax
0x18003ae92  jz      short loc_18003AED3
0x18003ae94  lea     rdx, aShellmessagebo; "ShellMessageBoxInternal"
0x18003ae9b  mov     rcx, rax; hModule
0x18003ae9e  call    cs:__imp_GetProcAddress
0x18003aea4  test    rax, rax
0x18003aea7  jz      short loc_18003AED3
0x18003aea9  mov     [rsp+48h+var_20], 30h ; '0'
0x18003aeb1  mov     r9d, 27CDh
0x18003aeb7  mov     r8d, 1
0x18003aebd  mov     qword ptr [rsp+48h+fuStyle], 2747h
0x18003aec6  mov     rdx, rbx
0x18003aec9  mov     rcx, rdi
0x18003aecc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003aed1  jmp     short loc_18003AEF3
0x18003aed3  mov     r9d, 2747h; lpcTitle
0x18003aed9  mov     [rsp+48h+fuStyle], 30h ; '0'; fuStyle
0x18003aee1  mov     r8d, 27CDh; lpcText
0x18003aee7  mov     rdx, rbx; hWnd
0x18003aeea  mov     rcx, rdi; hAppInst
0x18003aeed  call    cs:__imp_ShellMessageBoxW
0x18003aef3  lea     rcx, [rsp+48h+arg_18]
0x18003aef8  mov     ebx, eax
0x18003aefa  call    ??1?$unique_storage@U?$resource_policy@PEAUHINSTANCE__@@P6AHPEAU1@@Z$1?FreeLibrary@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>(void)
0x18003aeff  mov     eax, ebx
0x18003af01  mov     rbx, [rsp+48h+arg_0]
0x18003af06  add     rsp, 40h
0x18003af0a  pop     rdi
0x18003af0b  retn
```
