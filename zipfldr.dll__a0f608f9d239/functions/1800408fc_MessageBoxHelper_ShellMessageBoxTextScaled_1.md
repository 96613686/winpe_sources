# MessageBoxHelper::ShellMessageBoxTextScaled___1

- ea: `0x1800408fc`
- end: `0x18004099f`
- name: `MessageBoxHelper::ShellMessageBoxTextScaled___1`
- size: `163`
- prototype: ``
- caller_count: `10`
- callee_count: `3`
- tags: `registry_config, loader_planting`

## callers

- `0x18000b430`
- `0x180015218`
- `0x18002bf78`
- `0x180041050`
- `0x1800450f0`
- `0x180045c98`
- `0x180047c48`
- `0x180047e30`
- `0x180048158`
- `0x18004839c`

## callees

- `0x18003b124`
- `0x1800408fc`
- `0x180071010`

## import_xrefs

- `SHLWAPI!__imp_ShellMessageBoxW` at `0x180040982`
- `SHLWAPI!__imp_ShellMessageBoxW` at `0x180040982`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18004093a`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18004093a`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x180040920`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x180040920`

## string_xrefs

- `0x180040910`: `shlwapi.dll`

## pseudocode

```c
__int64 __fastcall MessageBoxHelper::ShellMessageBoxTextScaled___1(
        HMODULE a1,
        HWND a2,
        const WCHAR *a3,
        const WCHAR *a4,
        UINT fuStyle)
{
  HINSTANCE v5; // rbp
  HMODULE LibraryW; // rax
  FARPROC ProcAddress; // rax
  int v11; // eax
  unsigned int v12; // ebx
  HMODULE v14; // [rsp+70h] [rbp+8h] BYREF

  v14 = a1;
  v5 = g_hmodThisDll;
  LibraryW = LoadLibraryW(L"shlwapi.dll");
  v14 = LibraryW;
  if ( LibraryW && (ProcAddress = GetProcAddress(LibraryW, "ShellMessageBoxInternal")) != 0 )
    v11 = ((__int64 (__fastcall *)(HINSTANCE, HWND, __int64, const WCHAR *, const WCHAR *, UINT))ProcAddress)(
            v5,
            a2,
            1,
            a3,
            a4,
            fuStyle);
  else
    v11 = ShellMessageBoxW(v5, a2, a3, a4, fuStyle);
  v12 = v11;
  wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&int FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&int FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>(&v14);
  return v12;
}

```

## disassembly

```asm
0x1800408fc  mov     [rsp+arg_0], rcx
0x180040901  push    rbx
0x180040902  push    rbp
0x180040903  push    rsi
0x180040904  push    rdi
0x180040905  sub     rsp, 48h
0x180040909  mov     rbp, cs:g_hmodThisDll
0x180040910  lea     rcx, aShlwapiDll_0; "shlwapi.dll"
0x180040917  mov     rbx, r9
0x18004091a  mov     rdi, r8
0x18004091d  mov     rsi, rdx
0x180040920  call    cs:__imp_LoadLibraryW
0x180040926  mov     [rsp+68h+arg_0], rax
0x18004092b  test    rax, rax
0x18004092e  jz      short loc_18004096B
0x180040930  lea     rdx, aShellmessagebo; "ShellMessageBoxInternal"
0x180040937  mov     rcx, rax; hModule
0x18004093a  call    cs:__imp_GetProcAddress
0x180040940  test    rax, rax
0x180040943  jz      short loc_18004096B
0x180040945  mov     edx, [rsp+68h+arg_20]
0x18004094c  mov     r9, rdi
0x18004094f  mov     [rsp+68h+var_40], edx
0x180040953  mov     r8d, 1
0x180040959  mov     rdx, rsi
0x18004095c  mov     qword ptr [rsp+68h+fuStyle], rbx
0x180040961  mov     rcx, rbp
0x180040964  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180040969  jmp     short loc_180040988
0x18004096b  mov     eax, [rsp+68h+arg_20]
0x180040972  mov     r9, rbx; lpcTitle
0x180040975  mov     r8, rdi; lpcText
0x180040978  mov     [rsp+68h+fuStyle], eax; fuStyle
0x18004097c  mov     rdx, rsi; hWnd
0x18004097f  mov     rcx, rbp; hAppInst
0x180040982  call    cs:__imp_ShellMessageBoxW
0x180040988  lea     rcx, [rsp+68h+arg_0]
0x18004098d  mov     ebx, eax
0x18004098f  call    ??1?$unique_storage@U?$resource_policy@PEAUHINSTANCE__@@P6AHPEAU1@@Z$1?FreeLibrary@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>(void)
0x180040994  mov     eax, ebx
0x180040996  add     rsp, 48h
0x18004099a  pop     rdi
0x18004099b  pop     rsi
0x18004099c  pop     rbp
0x18004099d  pop     rbx
0x18004099e  retn
```
