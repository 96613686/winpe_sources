# MessageBoxHelper::ShellMessageBoxTextScaled_unsigned_short___

- ea: `0x180040a68`
- end: `0x180040b1d`
- name: `MessageBoxHelper::ShellMessageBoxTextScaled_unsigned_short___`
- size: `181`
- prototype: `__int64 __fastcall(HINSTANCE hAppInst, HWND hWnd, LPCWSTR lpcText, LPCWSTR lpcTitle, UINT, __int64)`
- caller_count: `3`
- callee_count: `3`
- tags: `registry_config, loader_planting`

## callers

- `0x18000b0bc`
- `0x18000b430`
- `0x18002c184`

## callees

- `0x18003b124`
- `0x180040a68`
- `0x180071010`

## import_xrefs

- `SHLWAPI!__imp_ShellMessageBoxW` at `0x180040b00`
- `SHLWAPI!__imp_ShellMessageBoxW` at `0x180040b00`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180040a9e`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180040a9e`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x180040a84`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x180040a84`

## string_xrefs

- `0x180040a77`: `shlwapi.dll`

## pseudocode

```c
__int64 __fastcall MessageBoxHelper::ShellMessageBoxTextScaled_unsigned_short___(
        HINSTANCE hAppInst,
        HWND hWnd,
        LPCWSTR lpcText,
        LPCWSTR lpcTitle,
        UINT fuStyle,
        __int64 a6)
{
  HMODULE LibraryW; // rax
  FARPROC ProcAddress; // rax
  int v12; // eax
  unsigned int v13; // ebx
  HMODULE v15[7]; // [rsp+40h] [rbp-38h] BYREF

  LibraryW = LoadLibraryW(L"shlwapi.dll");
  v15[0] = LibraryW;
  if ( LibraryW && (ProcAddress = GetProcAddress(LibraryW, "ShellMessageBoxInternal")) != 0 )
    v12 = ((__int64 (__fastcall *)(HINSTANCE, HWND, __int64, LPCWSTR, LPCWSTR, UINT, __int64))ProcAddress)(
            hAppInst,
            hWnd,
            1,
            lpcText,
            lpcTitle,
            fuStyle,
            a6);
  else
    v12 = ShellMessageBoxW(hAppInst, hWnd, lpcText, lpcTitle, fuStyle, a6);
  v13 = v12;
  wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&int FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&int FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>(v15);
  return v13;
}

```

## disassembly

```asm
0x180040a68  push    rbx
0x180040a6a  push    rbp
0x180040a6b  push    rsi
0x180040a6c  push    rdi
0x180040a6d  sub     rsp, 58h
0x180040a71  mov     rbp, rcx
0x180040a74  mov     rbx, r9
0x180040a77  lea     rcx, aShlwapiDll_0; "shlwapi.dll"
0x180040a7e  mov     rdi, r8
0x180040a81  mov     rsi, rdx
0x180040a84  call    cs:__imp_LoadLibraryW
0x180040a8a  mov     [rsp+78h+var_38], rax
0x180040a8f  test    rax, rax
0x180040a92  jz      short loc_180040ADC
0x180040a94  lea     rdx, aShellmessagebo; "ShellMessageBoxInternal"
0x180040a9b  mov     rcx, rax; hModule
0x180040a9e  call    cs:__imp_GetProcAddress
0x180040aa4  test    rax, rax
0x180040aa7  jz      short loc_180040ADC
0x180040aa9  mov     rcx, [rsp+78h+arg_28]
0x180040ab1  mov     r9, rdi
0x180040ab4  mov     [rsp+78h+var_48], rcx
0x180040ab9  mov     r8d, 1
0x180040abf  mov     ecx, [rsp+78h+arg_20]
0x180040ac6  mov     rdx, rsi
0x180040ac9  mov     dword ptr [rsp+78h+var_50], ecx
0x180040acd  mov     rcx, rbp
0x180040ad0  mov     qword ptr [rsp+78h+fuStyle], rbx
0x180040ad5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180040ada  jmp     short loc_180040B06
0x180040adc  mov     rax, [rsp+78h+arg_28]
0x180040ae4  mov     r9, rbx; lpcTitle
0x180040ae7  mov     [rsp+78h+var_50], rax
0x180040aec  mov     r8, rdi; lpcText
0x180040aef  mov     eax, [rsp+78h+arg_20]
0x180040af6  mov     rdx, rsi; hWnd
0x180040af9  mov     rcx, rbp; hAppInst
0x180040afc  mov     [rsp+78h+fuStyle], eax; fuStyle
0x180040b00  call    cs:__imp_ShellMessageBoxW
0x180040b06  lea     rcx, [rsp+78h+var_38]
0x180040b0b  mov     ebx, eax
0x180040b0d  call    ??1?$unique_storage@U?$resource_policy@PEAUHINSTANCE__@@P6AHPEAU1@@Z$1?FreeLibrary@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>(void)
0x180040b12  mov     eax, ebx
0x180040b14  add     rsp, 58h
0x180040b18  pop     rdi
0x180040b19  pop     rsi
0x180040b1a  pop     rbp
0x180040b1b  pop     rbx
0x180040b1c  retn
```
