# CleanupUserPropertyBags(ushort const *)

- ea: `0x140069778`
- end: `0x140069909`
- name: `?CleanupUserPropertyBags@@YAXPEBG@Z`
- size: `401`
- prototype: `void __fastcall(const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `8`
- tags: `registry_config, loader_planting`

## callers

- `0x14006a688`
- `0x14006a910`

## callees

- `0x14000fa4c`
- `0x14001246c`
- `0x140014208`
- `0x140023834`
- `0x14002abc0`
- `0x140069688`
- `0x140069778`
- `0x14007a010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x140069842`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x140069842`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1400697f1`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1400697f1`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x14006988f`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x14006988f`
- `api-ms-win-core-registry-l1-1-0!RegDeleteTreeW` at `0x1400698b4`
- `api-ms-win-core-registry-l1-1-0!RegDeleteTreeW` at `0x1400698b4`
- `KERNEL32!LoadLibraryExW` at `0x14006980e`
- `KERNEL32!LoadLibraryExW` at `0x14006980e`

## string_xrefs

- `0x140069801`: `localspl.dll`

## pseudocode

```c
void __fastcall CleanupUserPropertyBags(const unsigned __int16 *a1)
{
  int v1; // eax
  NCoreLibrary::TString *v2; // rcx
  WCHAR *v3; // rdx
  HMODULE Library; // rax
  HMODULE v5; // rdi
  FARPROC ProcAddress; // rsi
  DWORD i; // edi
  HKEY hKey; // [rsp+40h] [rbp-C0h] BYREF
  LPCWSTR lpSubKey; // [rsp+48h] [rbp-B8h] BYREF
  HMODULE v10; // [rsp+50h] [rbp-B0h] BYREF
  DWORD cchName; // [rsp+58h] [rbp-A8h] BYREF
  WCHAR Name[264]; // [rsp+60h] [rbp-A0h] BYREF

  NCoreLibrary::TString::TString((NCoreLibrary::TString *)&lpSubKey, a1);
  v1 = NCoreLibrary::TString::Cat((NCoreLibrary::TString *)&lpSubKey, L"\\Local Settings\\Printers\\PropertyBags");
  v3 = (WCHAR *)lpSubKey;
  if ( v1 >= 0 )
  {
    hKey = 0;
    if ( !RegOpenKeyExW(HKEY_USERS, lpSubKey, 0, 0x1000Bu, &hKey) )
    {
      Library = LoadLibraryExW(L"localspl.dll", 0, 0x800u);
      v10 = 0;
      v5 = Library;
      NCoreLibrary::TGenericSP<HINSTANCE__ *,NCoreLibrary::TAutoHandleHMODULE,HINSTANCE__ *,0,HINSTANCE__ * const *>::Reset(&v10);
      if ( v5 )
      {
        v10 = v5;
        ProcAddress = GetProcAddress(v5, "SplIsValidUserPropertyBag");
        if ( ProcAddress )
        {
          for ( i = 0; ; ++i )
          {
            cchName = 260;
            if ( RegEnumKeyExW(hKey, i, Name, &cchName, 0, 0, 0, 0) )
              break;
            if ( !((unsigned __int8 (__fastcall *)(WCHAR *))ProcAddress)(Name) )
              RegDeleteTreeW(hKey, Name);
          }
        }
      }
      else
      {
        v10 = 0;
      }
      NCoreLibrary::TGenericSP<HINSTANCE__ *,NCoreLibrary::TAutoHandleHMODULE,HINSTANCE__ *,0,HINSTANCE__ * const *>::Reset(&v10);
    }
    NCoreLibrary::TGenericSP<HKEY__ *,NCoreLibrary::TAutoHandleHKEY,HKEY__ *,0,HKEY__ * const *>::Reset(&hKey);
    v3 = (WCHAR *)lpSubKey;
  }
  NCoreLibrary::TString::vFree(v2, v3);
}

```

## disassembly

```asm
0x140069778  mov     [rsp-8+arg_8], rsi
0x14006977d  mov     [rsp-8+arg_10], rdi
0x140069782  push    rbp
0x140069783  lea     rbp, [rsp-180h]
0x14006978b  sub     rsp, 280h
0x140069792  mov     rax, cs:__security_cookie
0x140069799  xor     rax, rsp
0x14006979c  mov     [rbp+180h+var_10], rax
0x1400697a3  mov     rdx, rcx; unsigned __int16 *
0x1400697a6  lea     rcx, [rsp+280h+lpSubKey]; this
0x1400697ab  call    ??0TString@NCoreLibrary@@QEAA@PEBG@Z; NCoreLibrary::TString::TString(ushort const *)
0x1400697b0  lea     rdx, aLocalSettingsP; "\\Local Settings\\Printers\\PropertyBag"...
0x1400697b7  lea     rcx, [rsp+280h+lpSubKey]; this
0x1400697bc  call    ?Cat@TString@NCoreLibrary@@QEAAJPEBG@Z; NCoreLibrary::TString::Cat(ushort const *)
0x1400697c1  mov     rdx, [rsp+280h+lpSubKey]; lpSubKey
0x1400697c6  test    eax, eax
0x1400697c8  js      loc_1400698E0
0x1400697ce  lea     rax, [rsp+280h+hKey]
0x1400697d3  mov     [rsp+280h+hKey], 0
0x1400697dc  mov     r9d, 1000Bh; samDesired
0x1400697e2  mov     [rsp+280h+phkResult], rax; phkResult
0x1400697e7  xor     r8d, r8d; ulOptions
0x1400697ea  mov     rcx, 0FFFFFFFF80000003h; hKey
0x1400697f1  call    cs:__imp_RegOpenKeyExW
0x1400697f7  test    eax, eax
0x1400697f9  jnz     loc_1400698D1
0x1400697ff  xor     edx, edx; hFile
0x140069801  lea     rcx, aLocalsplDll; "localspl.dll"
0x140069808  mov     r8d, 800h; dwFlags
0x14006980e  call    cs:__imp_LoadLibraryExW
0x140069814  lea     rcx, [rsp+280h+var_230]
0x140069819  mov     [rsp+280h+var_230], 0
0x140069822  mov     rdi, rax
0x140069825  call    ?Reset@?$TGenericSP@PEAUHINSTANCE__@@VTAutoHandleHMODULE@NCoreLibrary@@PEAU1@$0A@PEBQEAU1@@NCoreLibrary@@QEAAXXZ; NCoreLibrary::TGenericSP<HINSTANCE__ *,NCoreLibrary::TAutoHandleHMODULE,HINSTANCE__ *,0,HINSTANCE__ * const *>::Reset(void)
0x14006982a  test    rdi, rdi
0x14006982d  jz      loc_1400698BE
0x140069833  lea     rdx, aSplisvaliduser; "SplIsValidUserPropertyBag"
0x14006983a  mov     [rsp+280h+var_230], rdi
0x14006983f  mov     rcx, rdi; hModule
0x140069842  call    cs:__imp_GetProcAddress
0x140069848  mov     rsi, rax
0x14006984b  test    rax, rax
0x14006984e  jz      short loc_1400698C7
0x140069850  xor     edi, edi
0x140069852  mov     rcx, [rsp+280h+hKey]; hKey
0x140069857  lea     r9, [rsp+280h+cchName]; lpcchName
0x14006985c  mov     [rsp+280h+lpftLastWriteTime], 0; lpftLastWriteTime
0x140069865  lea     r8, [rsp+280h+Name]; lpName
0x14006986a  mov     [rsp+280h+lpcchClass], 0; lpcchClass
0x140069873  mov     edx, edi; dwIndex
0x140069875  mov     [rsp+280h+lpClass], 0; lpClass
0x14006987e  mov     [rsp+280h+phkResult], 0; lpReserved
0x140069887  mov     [rsp+280h+cchName], 104h
0x14006988f  call    cs:__imp_RegEnumKeyExW
0x140069895  test    eax, eax
0x140069897  jnz     short loc_1400698C7
0x140069899  lea     rcx, [rsp+280h+Name]
0x14006989e  mov     rax, rsi
0x1400698a1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400698a6  test    al, al
0x1400698a8  jnz     short loc_1400698BA
0x1400698aa  mov     rcx, [rsp+280h+hKey]; hKey
0x1400698af  lea     rdx, [rsp+280h+Name]; lpSubKey
0x1400698b4  call    cs:__imp_RegDeleteTreeW
0x1400698ba  inc     edi
0x1400698bc  jmp     short loc_140069852
0x1400698be  mov     [rsp+280h+var_230], 0
0x1400698c7  lea     rcx, [rsp+280h+var_230]
0x1400698cc  call    ?Reset@?$TGenericSP@PEAUHINSTANCE__@@VTAutoHandleHMODULE@NCoreLibrary@@PEAU1@$0A@PEBQEAU1@@NCoreLibrary@@QEAAXXZ; NCoreLibrary::TGenericSP<HINSTANCE__ *,NCoreLibrary::TAutoHandleHMODULE,HINSTANCE__ *,0,HINSTANCE__ * const *>::Reset(void)
0x1400698d1  lea     rcx, [rsp+280h+hKey]
0x1400698d6  call    ?Reset@?$TGenericSP@PEAUHKEY__@@VTAutoHandleHKEY@NCoreLibrary@@PEAU1@$0A@PEBQEAU1@@NCoreLibrary@@QEAAXXZ; NCoreLibrary::TGenericSP<HKEY__ *,NCoreLibrary::TAutoHandleHKEY,HKEY__ *,0,HKEY__ * const *>::Reset(void)
0x1400698db  mov     rdx, [rsp+280h+lpSubKey]; void *
0x1400698e0  call    ?vFree@TString@NCoreLibrary@@AEAAXPEAX@Z; NCoreLibrary::TString::vFree(void *)
0x1400698e5  mov     rcx, [rbp+180h+var_10]
0x1400698ec  xor     rcx, rsp; StackCookie
0x1400698ef  call    __security_check_cookie
0x1400698f4  lea     r11, [rsp+280h+var_s0]
0x1400698fc  mov     rsi, [r11+18h]
0x140069900  mov     rdi, [r11+20h]
0x140069904  mov     rsp, r11
0x140069907  pop     rbp
0x140069908  retn
```
