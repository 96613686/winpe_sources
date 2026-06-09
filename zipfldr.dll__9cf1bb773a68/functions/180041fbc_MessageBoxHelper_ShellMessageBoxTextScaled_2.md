# MessageBoxHelper::ShellMessageBoxTextScaled___2

- ea: `0x180041fbc`
- end: `0x18004206b`
- name: `MessageBoxHelper::ShellMessageBoxTextScaled___2`
- size: `175`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config, loader_planting`

## callers

- `0x180024cb4`
- `0x1800429f0`

## callees

- `0x18003b124`
- `0x180041fbc`
- `0x180071010`

## import_xrefs

- `SHLWAPI!__imp_ShellMessageBoxW` at `0x180042047`
- `SHLWAPI!__imp_ShellMessageBoxW` at `0x180042047`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180041ffe`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180041ffe`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x180041fe4`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x180041fe4`

## string_xrefs

- `0x180041fd7`: `shlwapi.dll`

## pseudocode

```c
__int64 MessageBoxHelper::ShellMessageBoxTextScaled___2(__int64 a1, HWND a2, const WCHAR *a3, ...)
{
  HINSTANCE v3; // rsi
  HMODULE LibraryW; // rax
  FARPROC ProcAddress; // rax
  int v8; // eax
  unsigned int v9; // ebx
  HMODULE v11; // [rsp+68h] [rbp+20h] BYREF
  va_list va; // [rsp+68h] [rbp+20h]
  __int64 fuStyle; // [rsp+70h] [rbp+28h]
  va_list va1; // [rsp+78h] [rbp+30h] BYREF

  va_start(va1, a3);
  va_start(va, a3);
  v11 = va_arg(va1, HMODULE);
  fuStyle = va_arg(va1, _QWORD);
  v3 = g_hmodThisDll;
  LibraryW = LoadLibraryW(L"shlwapi.dll");
  v11 = LibraryW;
  if ( LibraryW && (ProcAddress = GetProcAddress(LibraryW, "ShellMessageBoxInternal")) != 0 )
    v8 = ((__int64 (__fastcall *)(HINSTANCE, HWND, __int64, const WCHAR *, __int64, _DWORD))ProcAddress)(
           v3,
           a2,
           1,
           a3,
           10055,
           fuStyle);
  else
    v8 = ShellMessageBoxW(v3, a2, a3, (LPCWSTR)0x2747, fuStyle);
  v9 = v8;
  wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&int FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&int FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>((HMODULE *)va);
  return v9;
}

```

## disassembly

```asm
0x180041fbc  mov     [rsp+arg_0], rbx
0x180041fc1  mov     [rsp+arg_8], rsi
0x180041fc6  mov     [rsp+arg_18], r9
0x180041fcb  push    rdi
0x180041fcc  sub     rsp, 40h
0x180041fd0  mov     rsi, cs:g_hmodThisDll
0x180041fd7  lea     rcx, aShlwapiDll_0; "shlwapi.dll"
0x180041fde  mov     rbx, r8
0x180041fe1  mov     rdi, rdx
0x180041fe4  call    cs:__imp_LoadLibraryW
0x180041fea  mov     [rsp+48h+arg_18], rax
0x180041fef  test    rax, rax
0x180041ff2  jz      short loc_180042030
0x180041ff4  lea     rdx, aShellmessagebo; "ShellMessageBoxInternal"
0x180041ffb  mov     rcx, rax; hModule
0x180041ffe  call    cs:__imp_GetProcAddress
0x180042004  test    rax, rax
0x180042007  jz      short loc_180042030
0x180042009  mov     edx, dword ptr [rsp+48h+arg_20]
0x18004200d  mov     r9, rbx
0x180042010  mov     [rsp+48h+var_20], edx
0x180042014  mov     r8d, 1
0x18004201a  mov     rdx, rdi
0x18004201d  mov     qword ptr [rsp+48h+fuStyle], 2747h
0x180042026  mov     rcx, rsi
0x180042029  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004202e  jmp     short loc_18004204D
0x180042030  mov     eax, dword ptr [rsp+48h+arg_20]
0x180042034  mov     r9d, 2747h; lpcTitle
0x18004203a  mov     r8, rbx; lpcText
0x18004203d  mov     [rsp+48h+fuStyle], eax; fuStyle
0x180042041  mov     rdx, rdi; hWnd
0x180042044  mov     rcx, rsi; hAppInst
0x180042047  call    cs:__imp_ShellMessageBoxW
0x18004204d  lea     rcx, [rsp+48h+arg_18]
0x180042052  mov     ebx, eax
0x180042054  call    ??1?$unique_storage@U?$resource_policy@PEAUHINSTANCE__@@P6AHPEAU1@@Z$1?FreeLibrary@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>(void)
0x180042059  mov     rsi, [rsp+48h+arg_8]
0x18004205e  mov     eax, ebx
0x180042060  mov     rbx, [rsp+48h+arg_0]
0x180042065  add     rsp, 40h
0x180042069  pop     rdi
0x18004206a  retn
```
