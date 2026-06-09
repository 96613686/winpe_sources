# MessageBoxHelper::ShellMessageBoxTextScaled_unsigned_short____0

- ea: `0x180042074`
- end: `0x180042130`
- name: `MessageBoxHelper::ShellMessageBoxTextScaled_unsigned_short____0`
- size: `188`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, loader_planting`

## callers

- `0x1800429f0`

## callees

- `0x18003b124`
- `0x180042074`
- `0x180071010`

## import_xrefs

- `SHLWAPI!__imp_ShellMessageBoxW` at `0x180042111`
- `SHLWAPI!__imp_ShellMessageBoxW` at `0x180042111`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800420ae`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800420ae`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x180042094`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x180042094`

## string_xrefs

- `0x18004208a`: `shlwapi.dll`

## pseudocode

```c
__int64 MessageBoxHelper::ShellMessageBoxTextScaled_unsigned_short____0(__int64 a1, HWND a2, __int64 a3, ...)
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
    v7 = ((__int64 (__fastcall *)(HINSTANCE, HWND, __int64, __int64, __int64, int, __int64))ProcAddress)(
           v3,
           a2,
           1,
           10427,
           10055,
           48,
           v13);
  else
    v7 = ShellMessageBoxW(v3, a2, (LPCWSTR)0x28BB, (LPCWSTR)0x2747, 0x30u, v13);
  v8 = v7;
  wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&int FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&int FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>((HMODULE *)va);
  return v8;
}

```

## disassembly

```asm
0x180042074  mov     [rsp+arg_0], rbx
0x180042079  mov     [rsp+arg_18], r9
0x18004207e  push    rdi
0x18004207f  sub     rsp, 40h
0x180042083  mov     rdi, cs:g_hmodThisDll
0x18004208a  lea     rcx, aShlwapiDll_0; "shlwapi.dll"
0x180042091  mov     rbx, rdx
0x180042094  call    cs:__imp_LoadLibraryW
0x18004209a  mov     [rsp+48h+arg_18], rax
0x18004209f  test    rax, rax
0x1800420a2  jz      short loc_1800420ED
0x1800420a4  lea     rdx, aShellmessagebo; "ShellMessageBoxInternal"
0x1800420ab  mov     rcx, rax; hModule
0x1800420ae  call    cs:__imp_GetProcAddress
0x1800420b4  test    rax, rax
0x1800420b7  jz      short loc_1800420ED
0x1800420b9  mov     rdx, [rsp+48h+arg_28]
0x1800420be  mov     r9d, 28BBh
0x1800420c4  mov     [rsp+48h+var_18], rdx
0x1800420c9  mov     r8d, 1
0x1800420cf  mov     dword ptr [rsp+48h+var_20], 30h ; '0'
0x1800420d7  mov     rdx, rbx
0x1800420da  mov     rcx, rdi
0x1800420dd  mov     qword ptr [rsp+48h+fuStyle], 2747h
0x1800420e6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800420eb  jmp     short loc_180042117
0x1800420ed  mov     rax, [rsp+48h+arg_28]
0x1800420f2  mov     r9d, 2747h; lpcTitle
0x1800420f8  mov     [rsp+48h+var_20], rax
0x1800420fd  mov     r8d, 28BBh; lpcText
0x180042103  mov     rdx, rbx; hWnd
0x180042106  mov     [rsp+48h+fuStyle], 30h ; '0'; fuStyle
0x18004210e  mov     rcx, rdi; hAppInst
0x180042111  call    cs:__imp_ShellMessageBoxW
0x180042117  lea     rcx, [rsp+48h+arg_18]
0x18004211c  mov     ebx, eax
0x18004211e  call    ??1?$unique_storage@U?$resource_policy@PEAUHINSTANCE__@@P6AHPEAU1@@Z$1?FreeLibrary@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>(void)
0x180042123  mov     eax, ebx
0x180042125  mov     rbx, [rsp+48h+arg_0]
0x18004212a  add     rsp, 40h
0x18004212e  pop     rdi
0x18004212f  retn
```
