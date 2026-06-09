# AccessibilityHelpers::DoPropertySheetWithScaling(_PROPSHEETHEADERW_V2 *)

- ea: `0x1800421a4`
- end: `0x180042233`
- name: `?DoPropertySheetWithScaling@AccessibilityHelpers@@YAHPEAU_PROPSHEETHEADERW_V2@@@Z`
- size: `143`
- prototype: `__int64 __fastcall(LPCPROPSHEETHEADERW this, struct _PROPSHEETHEADERW_V2 *)`
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x18002c6ac`
- `0x1800683c8`

## callees

- `0x180034c28`
- `0x180036f50`
- `0x18003b124`
- `0x1800421a4`
- `0x180071010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800421dd`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800421dd`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x1800421c3`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x1800421c3`

## string_xrefs

- `0x1800421bc`: `comctl32.dll`

## pseudocode

```c
__int64 __fastcall AccessibilityHelpers::DoPropertySheetWithScaling(
        LPCPROPSHEETHEADERW this,
        struct _PROPSHEETHEADERW_V2 *a2)
{
  HMODULE LibraryW; // rax
  FARPROC ProcAddress; // rax
  unsigned int v5; // ebx
  HMODULE v7; // [rsp+20h] [rbp-28h] BYREF
  _DWORD v8[2]; // [rsp+28h] [rbp-20h] BYREF

  LibraryW = LoadLibraryW(L"comctl32.dll");
  v7 = LibraryW;
  if ( LibraryW && (ProcAddress = GetProcAddress(LibraryW, "PropertySheetInternalW")) != 0 )
  {
    v8[0] = 8;
    v8[1] = 1;
    v5 = ((__int64 (__fastcall *)(LPCPROPSHEETHEADERW, _DWORD *))ProcAddress)(this, v8);
  }
  else
  {
    v5 = PropertySheetW(this);
  }
  wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&int FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&int FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>(&v7);
  return v5;
}

```

## disassembly

```asm
0x1800421a4  push    rbx
0x1800421a6  sub     rsp, 40h
0x1800421aa  mov     rax, cs:__security_cookie
0x1800421b1  xor     rax, rsp
0x1800421b4  mov     [rsp+48h+var_18], rax
0x1800421b9  mov     rbx, rcx
0x1800421bc  lea     rcx, LibFileName; "comctl32.dll"
0x1800421c3  call    cs:__imp_LoadLibraryW
0x1800421c9  mov     [rsp+48h+var_28], rax
0x1800421ce  test    rax, rax
0x1800421d1  jz      short loc_18004220A
0x1800421d3  lea     rdx, aPropertysheeti; "PropertySheetInternalW"
0x1800421da  mov     rcx, rax; hModule
0x1800421dd  call    cs:__imp_GetProcAddress
0x1800421e3  test    rax, rax
0x1800421e6  jz      short loc_18004220A
0x1800421e8  lea     rdx, [rsp+48h+var_20]
0x1800421ed  mov     [rsp+48h+var_20], 8
0x1800421f5  mov     rcx, rbx
0x1800421f8  mov     [rsp+48h+var_1C], 1
0x180042200  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180042205  mov     rbx, rax
0x180042208  jmp     short loc_180042214
0x18004220a  mov     rcx, rbx; LPCPROPSHEETHEADERW
0x18004220d  call    PropertySheetW
0x180042212  mov     ebx, eax
0x180042214  lea     rcx, [rsp+48h+var_28]
0x180042219  call    ??1?$unique_storage@U?$resource_policy@PEAUHINSTANCE__@@P6AHPEAU1@@Z$1?FreeLibrary@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>(void)
0x18004221e  mov     eax, ebx
0x180042220  mov     rcx, [rsp+48h+var_18]
0x180042225  xor     rcx, rsp; StackCookie
0x180042228  call    __security_check_cookie
0x18004222d  add     rsp, 40h
0x180042231  pop     rbx
0x180042232  retn
```
