# MessageBoxHelper::ShellMessageBoxTextScaled_unsigned_short____1

- ea: `0x180044fa0`
- end: `0x18004505c`
- name: `MessageBoxHelper::ShellMessageBoxTextScaled_unsigned_short____1`
- size: `188`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, loader_planting`

## callers

- `0x1800450f0`

## callees

- `0x18003b124`
- `0x180044fa0`
- `0x180071010`

## import_xrefs

- `SHLWAPI!__imp_ShellMessageBoxW` at `0x18004503d`
- `SHLWAPI!__imp_ShellMessageBoxW` at `0x18004503d`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180044fda`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180044fda`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x180044fc0`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x180044fc0`

## string_xrefs

- `0x180044fb6`: `shlwapi.dll`

## pseudocode

```c
__int64 MessageBoxHelper::ShellMessageBoxTextScaled_unsigned_short____1(__int64 a1, HWND a2, __int64 a3, ...)
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
           10219,
           10055,
           48,
           v13);
  else
    v7 = ShellMessageBoxW(v3, a2, (LPCWSTR)0x27EB, (LPCWSTR)0x2747, 0x30u, v13);
  v8 = v7;
  wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&int FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&int FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>((HMODULE *)va);
  return v8;
}

```

## disassembly

```asm
0x180044fa0  mov     [rsp+arg_0], rbx
0x180044fa5  mov     [rsp+arg_18], r9
0x180044faa  push    rdi
0x180044fab  sub     rsp, 40h
0x180044faf  mov     rdi, cs:g_hmodThisDll
0x180044fb6  lea     rcx, aShlwapiDll_0; "shlwapi.dll"
0x180044fbd  mov     rbx, rdx
0x180044fc0  call    cs:__imp_LoadLibraryW
0x180044fc6  mov     [rsp+48h+arg_18], rax
0x180044fcb  test    rax, rax
0x180044fce  jz      short loc_180045019
0x180044fd0  lea     rdx, aShellmessagebo; "ShellMessageBoxInternal"
0x180044fd7  mov     rcx, rax; hModule
0x180044fda  call    cs:__imp_GetProcAddress
0x180044fe0  test    rax, rax
0x180044fe3  jz      short loc_180045019
0x180044fe5  mov     rdx, [rsp+48h+arg_28]
0x180044fea  mov     r9d, 27EBh
0x180044ff0  mov     [rsp+48h+var_18], rdx
0x180044ff5  mov     r8d, 1
0x180044ffb  mov     dword ptr [rsp+48h+var_20], 30h ; '0'
0x180045003  mov     rdx, rbx
0x180045006  mov     rcx, rdi
0x180045009  mov     qword ptr [rsp+48h+fuStyle], 2747h
0x180045012  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180045017  jmp     short loc_180045043
0x180045019  mov     rax, [rsp+48h+arg_28]
0x18004501e  mov     r9d, 2747h; lpcTitle
0x180045024  mov     [rsp+48h+var_20], rax
0x180045029  mov     r8d, 27EBh; lpcText
0x18004502f  mov     rdx, rbx; hWnd
0x180045032  mov     [rsp+48h+fuStyle], 30h ; '0'; fuStyle
0x18004503a  mov     rcx, rdi; hAppInst
0x18004503d  call    cs:__imp_ShellMessageBoxW
0x180045043  lea     rcx, [rsp+48h+arg_18]
0x180045048  mov     ebx, eax
0x18004504a  call    ??1?$unique_storage@U?$resource_policy@PEAUHINSTANCE__@@P6AHPEAU1@@Z$1?FreeLibrary@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>(void)
0x18004504f  mov     eax, ebx
0x180045051  mov     rbx, [rsp+48h+arg_0]
0x180045056  add     rsp, 40h
0x18004505a  pop     rdi
0x18004505b  retn
```
