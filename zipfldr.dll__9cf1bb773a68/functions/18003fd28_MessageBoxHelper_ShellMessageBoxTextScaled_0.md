# MessageBoxHelper::ShellMessageBoxTextScaled___0

- ea: `0x18003fd28`
- end: `0x18003fdd0`
- name: `MessageBoxHelper::ShellMessageBoxTextScaled___0`
- size: `168`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, loader_planting`

## callers

- `0x18003fde0`

## callees

- `0x18003b124`
- `0x18003fd28`
- `0x180071010`

## import_xrefs

- `SHLWAPI!__imp_ShellMessageBoxW` at `0x18003fdb1`
- `SHLWAPI!__imp_ShellMessageBoxW` at `0x18003fdb1`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18003fd62`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18003fd62`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x18003fd48`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x18003fd48`

## string_xrefs

- `0x18003fd3e`: `shlwapi.dll`

## pseudocode

```c
__int64 MessageBoxHelper::ShellMessageBoxTextScaled___0(__int64 a1, HWND a2, __int64 a3, ...)
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
           10055,
           64);
  else
    v7 = ShellMessageBoxW(v3, a2, (LPCWSTR)0x27D0, (LPCWSTR)0x2747, 0x40u);
  v8 = v7;
  wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&int FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&int FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>((HMODULE *)va);
  return v8;
}

```

## disassembly

```asm
0x18003fd28  mov     [rsp+arg_0], rbx
0x18003fd2d  mov     [rsp+arg_18], r9
0x18003fd32  push    rdi
0x18003fd33  sub     rsp, 40h
0x18003fd37  mov     rdi, cs:g_hmodThisDll
0x18003fd3e  lea     rcx, aShlwapiDll_0; "shlwapi.dll"
0x18003fd45  mov     rbx, rdx
0x18003fd48  call    cs:__imp_LoadLibraryW
0x18003fd4e  mov     [rsp+48h+arg_18], rax
0x18003fd53  test    rax, rax
0x18003fd56  jz      short loc_18003FD97
0x18003fd58  lea     rdx, aShellmessagebo; "ShellMessageBoxInternal"
0x18003fd5f  mov     rcx, rax; hModule
0x18003fd62  call    cs:__imp_GetProcAddress
0x18003fd68  test    rax, rax
0x18003fd6b  jz      short loc_18003FD97
0x18003fd6d  mov     [rsp+48h+var_20], 40h ; '@'
0x18003fd75  mov     r9d, 27D0h
0x18003fd7b  mov     r8d, 1
0x18003fd81  mov     qword ptr [rsp+48h+fuStyle], 2747h
0x18003fd8a  mov     rdx, rbx
0x18003fd8d  mov     rcx, rdi
0x18003fd90  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003fd95  jmp     short loc_18003FDB7
0x18003fd97  mov     r9d, 2747h; lpcTitle
0x18003fd9d  mov     [rsp+48h+fuStyle], 40h ; '@'; fuStyle
0x18003fda5  mov     r8d, 27D0h; lpcText
0x18003fdab  mov     rdx, rbx; hWnd
0x18003fdae  mov     rcx, rdi; hAppInst
0x18003fdb1  call    cs:__imp_ShellMessageBoxW
0x18003fdb7  lea     rcx, [rsp+48h+arg_18]
0x18003fdbc  mov     ebx, eax
0x18003fdbe  call    ??1?$unique_storage@U?$resource_policy@PEAUHINSTANCE__@@P6AHPEAU1@@Z$1?FreeLibrary@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>(void)
0x18003fdc3  mov     eax, ebx
0x18003fdc5  mov     rbx, [rsp+48h+arg_0]
0x18003fdca  add     rsp, 40h
0x18003fdce  pop     rdi
0x18003fdcf  retn
```
