# _lambda_c4a24963f2185a7f189027a86da88574_::_lambda_invoker_cdecl_(_RTL_RUN_ONCE *,void *,void * *)

- ea: `0x180028730`
- end: `0x1800287a1`
- name: `?_lambda_invoker_cdecl_@_lambda_c4a24963f2185a7f189027a86da88574_@@CAHPEAT_RTL_RUN_ONCE@@PEAXPEAPEAX@Z`
- size: `113`
- prototype: `BOOL __stdcall(PINIT_ONCE InitOnce, PVOID Parameter, PVOID *Context)`
- caller_count: `0`
- callee_count: `3`
- tags: `registry_config, loader_planting`

## callees

- `0x180028730`
- `0x180029c8c`
- `0x180032010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180028748`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180028748`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180028766`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180028766`

## string_xrefs

- `0x180028741`: `winbioext.dll`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall _lambda_c4a24963f2185a7f189027a86da88574_::_lambda_invoker_cdecl_(
        PINIT_ONCE InitOnce,
        _BYTE *Parameter,
        PVOID *Context)
{
  HMODULE Library; // rax
  unsigned int v5; // ebx
  FARPROC ProcAddress; // rax
  HMODULE v8[3]; // [rsp+20h] [rbp-18h] BYREF
  char v9; // [rsp+58h] [rbp+20h] BYREF

  Library = LoadLibraryExW(L"winbioext.dll", 0, 0x800u);
  v8[0] = Library;
  if ( Library
    && (ProcAddress = GetProcAddress(Library, "WinBioIsESSCapable")) != 0
    && (v9 = 0, ((int (__fastcall *)(char *))ProcAddress)(&v9) >= 0) )
  {
    *Parameter = v9;
    v5 = 1;
  }
  else
  {
    v5 = 0;
  }
  wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&int FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&int FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>(v8);
  return v5;
}

```

## disassembly

```asm
0x180028730  push    rbx
0x180028732  sub     rsp, 30h
0x180028736  mov     rbx, rdx
0x180028739  xor     edx, edx; hFile
0x18002873b  mov     r8d, 800h; dwFlags
0x180028741  lea     rcx, aWinbioextDll; "winbioext.dll"
0x180028748  call    cs:__imp_LoadLibraryExW
0x18002874e  mov     [rsp+38h+var_18], rax
0x180028753  test    rax, rax
0x180028756  jnz     short loc_18002875C
0x180028758  xor     ebx, ebx
0x18002875a  jmp     short loc_18002878F
0x18002875c  lea     rdx, aWinbioisesscap; "WinBioIsESSCapable"
0x180028763  mov     rcx, rax; hModule
0x180028766  call    cs:__imp_GetProcAddress
0x18002876c  test    rax, rax
0x18002876f  jz      short loc_180028758
0x180028771  mov     [rsp+38h+arg_18], 0
0x180028776  lea     rcx, [rsp+38h+arg_18]
0x18002877b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028780  test    eax, eax
0x180028782  js      short loc_180028758
0x180028784  mov     al, [rsp+38h+arg_18]
0x180028788  mov     [rbx], al
0x18002878a  mov     ebx, 1
0x18002878f  lea     rcx, [rsp+38h+var_18]
0x180028794  call    ??1?$unique_storage@U?$resource_policy@PEAUHINSTANCE__@@P6AHPEAU1@@Z$1?FreeLibrary@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>(void)
0x180028799  mov     eax, ebx
0x18002879b  add     rsp, 30h
0x18002879f  pop     rbx
0x1800287a0  retn
```
