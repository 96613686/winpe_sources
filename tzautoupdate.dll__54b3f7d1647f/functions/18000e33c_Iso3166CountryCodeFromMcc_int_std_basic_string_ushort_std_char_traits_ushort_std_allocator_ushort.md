# Iso3166CountryCodeFromMcc(int,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> &)

- ea: `0x18000e33c`
- end: `0x18000e473`
- name: `?Iso3166CountryCodeFromMcc@@YAJHAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z`
- size: `311`
- prototype: `__int64 __fastcall(unsigned int, __int64)`
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config, loader_planting, installer_update`

## callers

- `0x18000dc80`

## callees

- `0x18000883c`
- `0x18000885c`
- `0x18000d240`
- `0x18000da78`
- `0x18000db94`
- `0x18000e33c`
- `0x18000e968`
- `0x18000eae0`
- `0x18001b150`
- `0x18001d010`

## import_xrefs

- `msvcrt!swprintf_s` at `0x18000e377`
- `msvcrt!swprintf_s` at `0x18000e377`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000e3b0`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000e3b0`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x18000e392`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x18000e392`

## string_xrefs

- `0x18000e3be`: `onecore\base\win32\winnls\tzautoupdate\countrycodefinder.cpp`
- `0x18000e40b`: `onecore\base\win32\winnls\tzautoupdate\countrycodefinder.cpp`
- `0x18000e38b`: `ProvDataStore.dll`

## pseudocode

```c
__int64 __fastcall Iso3166CountryCodeFromMcc(unsigned int a1, __int64 a2)
{
  HMODULE LibraryW; // rax
  const char *v4; // r9
  __int64 v5; // rdx
  FARPROC ProcAddress; // rax
  unsigned int LastError; // ebx
  _QWORD *v8; // rcx
  int v9; // eax
  __int64 v10; // rax
  __int64 v11; // rdx
  int v13; // [rsp+20h] [rbp-79h]
  HMODULE v14; // [rsp+30h] [rbp-69h] BYREF
  _QWORD v15[4]; // [rsp+38h] [rbp-61h] BYREF
  __int64 v16; // [rsp+58h] [rbp-41h] BYREF
  wchar_t Buffer[64]; // [rsp+60h] [rbp-39h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+F8h] [rbp+5Fh]

  swprintf_s(Buffer, 0x40u, L"%d", a1);
  std::wstring::wstring(v15, Buffer);
  LibraryW = LoadLibraryW(L"ProvDataStore.dll");
  v14 = LibraryW;
  if ( !LibraryW )
  {
    v5 = 89;
LABEL_5:
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)v5,
                  (unsigned int)"onecore\\base\\win32\\winnls\\tzautoupdate\\countrycodefinder.cpp",
                  v4);
    goto LABEL_11;
  }
  ProcAddress = GetProcAddress(LibraryW, "MvDsGetInfoFromMcc");
  if ( !ProcAddress )
  {
    v5 = 92;
    goto LABEL_5;
  }
  v16 = 0;
  v8 = v15;
  if ( v15[3] >= 8u )
    v8 = (_QWORD *)v15[0];
  v9 = ((__int64 (__fastcall *)(_QWORD *, const wchar_t *, __int64 *, __int64))ProcAddress)(v8, L"iso3166", &v16, 4);
  LastError = v9;
  if ( v9 >= 0 )
  {
    v10 = std::char_traits<unsigned short>::length(&v16);
    std::wstring::assign(a2, &v16, v10);
    LastError = 0;
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x5F,
      (unsigned int)"onecore\\base\\win32\\winnls\\tzautoupdate\\countrycodefinder.cpp",
      (const char *)(unsigned int)v9,
      v13);
  }
LABEL_11:
  wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&int FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&int FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>(&v14);
  LOBYTE(v11) = 1;
  std::wstring::_Tidy(v15, v11, 0);
  return LastError;
}

```

## disassembly

```asm
0x18000e33c  mov     [rsp-8+arg_10], rbx
0x18000e341  mov     [rsp-8+arg_18], rdi
0x18000e346  push    rbp
0x18000e347  lea     rbp, [rsp-57h]
0x18000e34c  sub     rsp, 0F0h
0x18000e353  mov     rax, cs:__security_cookie
0x18000e35a  xor     rax, rsp
0x18000e35d  mov     [rbp+57h+var_10], rax
0x18000e361  mov     rdi, rdx
0x18000e364  mov     r9d, ecx
0x18000e367  lea     r8, aD; "%d"
0x18000e36e  mov     edx, 40h ; '@'; BufferCount
0x18000e373  lea     rcx, [rbp+57h+Buffer]; Buffer
0x18000e377  call    cs:__imp_swprintf_s
0x18000e37d  lea     rdx, [rbp+57h+Buffer]
0x18000e381  lea     rcx, [rbp+57h+var_B8]
0x18000e385  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@PEBG@Z; std::wstring::wstring(ushort const *)
0x18000e38a  nop
0x18000e38b  lea     rcx, LibFileName; "ProvDataStore.dll"
0x18000e392  call    cs:__imp_LoadLibraryW
0x18000e398  mov     [rbp+57h+var_C0], rax
0x18000e39c  test    rax, rax
0x18000e39f  jnz     short loc_18000E3A6
0x18000e3a1  lea     edx, [rax+59h]
0x18000e3a4  jmp     short loc_18000E3BE
0x18000e3a6  lea     rdx, aMvdsgetinfofro; "MvDsGetInfoFromMcc"
0x18000e3ad  mov     rcx, rax; hModule
0x18000e3b0  call    cs:__imp_GetProcAddress
0x18000e3b6  test    rax, rax
0x18000e3b9  jnz     short loc_18000E3D2
0x18000e3bb  lea     edx, [rax+5Ch]; void *
0x18000e3be  lea     r8, aOnecoreBaseWin_4; "onecore\\base\\win32\\winnls\\tzautoupd"...
0x18000e3c5  mov     rcx, [rbp+5Fh]; this
0x18000e3c9  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18000e3ce  mov     ebx, eax
0x18000e3d0  jmp     short loc_18000E438
0x18000e3d2  mov     [rbp+57h+var_98], 0
0x18000e3da  lea     rcx, [rbp+57h+var_B8]
0x18000e3de  cmp     [rbp+57h+var_A0], 8
0x18000e3e3  cmovnb  rcx, [rbp+57h+var_B8]
0x18000e3e8  mov     r9d, 4
0x18000e3ee  lea     r8, [rbp+57h+var_98]
0x18000e3f2  lea     rdx, aIso3166; "iso3166"
0x18000e3f9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e3fe  mov     ebx, eax
0x18000e400  test    eax, eax
0x18000e402  jns     short loc_18000E41E
0x18000e404  mov     rcx, [rbp+5Fh]; this
0x18000e408  mov     r9d, eax; char *
0x18000e40b  lea     r8, aOnecoreBaseWin_4; "onecore\\base\\win32\\winnls\\tzautoupd"...
0x18000e412  mov     edx, 5Fh ; '_'; void *
0x18000e417  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000e41c  jmp     short loc_18000E438
0x18000e41e  lea     rcx, [rbp+57h+var_98]
0x18000e422  call    ?length@?$char_traits@G@std@@SA_KPEBG@Z; std::char_traits<ushort>::length(ushort const *)
0x18000e427  mov     r8, rax
0x18000e42a  lea     rdx, [rbp+57h+var_98]
0x18000e42e  mov     rcx, rdi
0x18000e431  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG_K@Z; std::wstring::assign(ushort const *,unsigned __int64)
0x18000e436  xor     ebx, ebx
0x18000e438  lea     rcx, [rbp+57h+var_C0]
0x18000e43c  call    ??1?$unique_storage@U?$resource_policy@PEAUHINSTANCE__@@P6AHPEAU1@@Z$1?FreeLibrary@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>(void)
0x18000e441  nop
0x18000e442  xor     r8d, r8d
0x18000e445  mov     dl, 1
0x18000e447  lea     rcx, [rbp+57h+var_B8]
0x18000e44b  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x18000e450  mov     eax, ebx
0x18000e452  mov     rcx, [rbp+57h+var_10]
0x18000e456  xor     rcx, rsp; StackCookie
0x18000e459  call    __security_check_cookie
0x18000e45e  lea     r11, [rsp+0F0h+var_s0]
0x18000e466  mov     rbx, [r11+20h]
0x18000e46a  mov     rdi, [r11+28h]
0x18000e46e  mov     rsp, r11
0x18000e471  pop     rbp
0x18000e472  retn
```
