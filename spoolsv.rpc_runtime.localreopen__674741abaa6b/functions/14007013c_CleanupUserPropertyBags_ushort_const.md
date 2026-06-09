# CleanupUserPropertyBags(ushort const *)

- ea: `0x14007013c`
- end: `0x1400702f0`
- name: `?CleanupUserPropertyBags@@YAXPEBG@Z`
- size: `436`
- prototype: `void __fastcall(const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `8`
- tags: `registry_config, loader_planting`

## callers

- `0x1400711b8`
- `0x140071470`

## callees

- `0x140010c4c`
- `0x140013318`
- `0x1400154b8`
- `0x1400257b8`
- `0x14002d0a0`
- `0x140070048`
- `0x14007013c`
- `0x140081010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x140070212`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x140070212`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1400701b5`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1400701b5`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x140070269`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x140070269`
- `api-ms-win-core-registry-l1-1-0!RegDeleteTreeW` at `0x140070294`
- `api-ms-win-core-registry-l1-1-0!RegDeleteTreeW` at `0x140070294`
- `KERNEL32!LoadLibraryExW` at `0x1400701d8`
- `KERNEL32!LoadLibraryExW` at `0x1400701d8`

## string_xrefs

- `0x1400701cb`: `localspl.dll`

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
0x14007013c  mov     [rsp-8+arg_8], rsi
0x140070141  mov     [rsp-8+arg_10], rdi
0x140070146  push    rbp
0x140070147  lea     rbp, [rsp-180h]
0x14007014f  sub     rsp, 280h
0x140070156  mov     rax, cs:__security_cookie
0x14007015d  xor     rax, rsp
0x140070160  mov     [rbp+180h+var_10], rax
0x140070167  mov     rdx, rcx; unsigned __int16 *
0x14007016a  lea     rcx, [rsp+280h+lpSubKey]; this
0x14007016f  call    ??0TString@NCoreLibrary@@QEAA@PEBG@Z; NCoreLibrary::TString::TString(ushort const *)
0x140070174  lea     rdx, aLocalSettingsP; "\\Local Settings\\Printers\\PropertyBag"...
0x14007017b  lea     rcx, [rsp+280h+lpSubKey]; this
0x140070180  call    ?Cat@TString@NCoreLibrary@@QEAAJPEBG@Z; NCoreLibrary::TString::Cat(ushort const *)
0x140070185  mov     rdx, [rsp+280h+lpSubKey]; lpSubKey
0x14007018a  test    eax, eax
0x14007018c  js      loc_1400702C6
0x140070192  lea     rax, [rsp+280h+hKey]
0x140070197  mov     [rsp+280h+hKey], 0
0x1400701a0  mov     r9d, 1000Bh; samDesired
0x1400701a6  mov     [rsp+280h+phkResult], rax; phkResult
0x1400701ab  xor     r8d, r8d; ulOptions
0x1400701ae  mov     rcx, 0FFFFFFFF80000003h; hKey
0x1400701b5  call    cs:__imp_RegOpenKeyExW
0x1400701bc  nop     dword ptr [rax+rax+00h]
0x1400701c1  test    eax, eax
0x1400701c3  jnz     loc_1400702B7
0x1400701c9  xor     edx, edx; hFile
0x1400701cb  lea     rcx, aLocalsplDll; "localspl.dll"
0x1400701d2  mov     r8d, 800h; dwFlags
0x1400701d8  call    cs:__imp_LoadLibraryExW
0x1400701df  nop     dword ptr [rax+rax+00h]
0x1400701e4  lea     rcx, [rsp+280h+var_230]
0x1400701e9  mov     [rsp+280h+var_230], 0
0x1400701f2  mov     rdi, rax
0x1400701f5  call    ?Reset@?$TGenericSP@PEAUHINSTANCE__@@VTAutoHandleHMODULE@NCoreLibrary@@PEAU1@$0A@PEBQEAU1@@NCoreLibrary@@QEAAXXZ; NCoreLibrary::TGenericSP<HINSTANCE__ *,NCoreLibrary::TAutoHandleHMODULE,HINSTANCE__ *,0,HINSTANCE__ * const *>::Reset(void)
0x1400701fa  test    rdi, rdi
0x1400701fd  jz      loc_1400702A4
0x140070203  lea     rdx, aSplisvaliduser; "SplIsValidUserPropertyBag"
0x14007020a  mov     [rsp+280h+var_230], rdi
0x14007020f  mov     rcx, rdi; hModule
0x140070212  call    cs:__imp_GetProcAddress
0x140070219  nop     dword ptr [rax+rax+00h]
0x14007021e  mov     rsi, rax
0x140070221  test    rax, rax
0x140070224  jz      loc_1400702AD
0x14007022a  xor     edi, edi
0x14007022c  mov     rcx, [rsp+280h+hKey]; hKey
0x140070231  lea     r9, [rsp+280h+cchName]; lpcchName
0x140070236  mov     [rsp+280h+lpftLastWriteTime], 0; lpftLastWriteTime
0x14007023f  lea     r8, [rsp+280h+Name]; lpName
0x140070244  mov     [rsp+280h+lpcchClass], 0; lpcchClass
0x14007024d  mov     edx, edi; dwIndex
0x14007024f  mov     [rsp+280h+lpClass], 0; lpClass
0x140070258  mov     [rsp+280h+phkResult], 0; lpReserved
0x140070261  mov     [rsp+280h+cchName], 104h
0x140070269  call    cs:__imp_RegEnumKeyExW
0x140070270  nop     dword ptr [rax+rax+00h]
0x140070275  test    eax, eax
0x140070277  jnz     short loc_1400702AD
0x140070279  lea     rcx, [rsp+280h+Name]
0x14007027e  mov     rax, rsi
0x140070281  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140070286  test    al, al
0x140070288  jnz     short loc_1400702A0
0x14007028a  mov     rcx, [rsp+280h+hKey]; hKey
0x14007028f  lea     rdx, [rsp+280h+Name]; lpSubKey
0x140070294  call    cs:__imp_RegDeleteTreeW
0x14007029b  nop     dword ptr [rax+rax+00h]
0x1400702a0  inc     edi
0x1400702a2  jmp     short loc_14007022C
0x1400702a4  mov     [rsp+280h+var_230], 0
0x1400702ad  lea     rcx, [rsp+280h+var_230]
0x1400702b2  call    ?Reset@?$TGenericSP@PEAUHINSTANCE__@@VTAutoHandleHMODULE@NCoreLibrary@@PEAU1@$0A@PEBQEAU1@@NCoreLibrary@@QEAAXXZ; NCoreLibrary::TGenericSP<HINSTANCE__ *,NCoreLibrary::TAutoHandleHMODULE,HINSTANCE__ *,0,HINSTANCE__ * const *>::Reset(void)
0x1400702b7  lea     rcx, [rsp+280h+hKey]
0x1400702bc  call    ?Reset@?$TGenericSP@PEAUHKEY__@@VTAutoHandleHKEY@NCoreLibrary@@PEAU1@$0A@PEBQEAU1@@NCoreLibrary@@QEAAXXZ; NCoreLibrary::TGenericSP<HKEY__ *,NCoreLibrary::TAutoHandleHKEY,HKEY__ *,0,HKEY__ * const *>::Reset(void)
0x1400702c1  mov     rdx, [rsp+280h+lpSubKey]; void *
0x1400702c6  call    ?vFree@TString@NCoreLibrary@@AEAAXPEAX@Z; NCoreLibrary::TString::vFree(void *)
0x1400702cb  mov     rcx, [rbp+180h+var_10]
0x1400702d2  xor     rcx, rsp; StackCookie
0x1400702d5  call    __security_check_cookie
0x1400702da  lea     r11, [rsp+280h+var_s0]
0x1400702e2  mov     rsi, [r11+18h]
0x1400702e6  mov     rdi, [r11+20h]
0x1400702ea  mov     rsp, r11
0x1400702ed  pop     rbp
0x1400702ee  retn
```
