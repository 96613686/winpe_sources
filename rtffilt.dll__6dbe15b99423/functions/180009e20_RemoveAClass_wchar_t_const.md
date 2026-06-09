# RemoveAClass(wchar_t const *)

- ea: `0x180009e20`
- end: `0x18000a117`
- name: `?RemoveAClass@@YAJPEB_W@Z`
- size: `759`
- prototype: `__int64 __fastcall(LPCWSTR lpSubKey)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18000ba74`

## callees

- `0x180001e40`
- `0x180001e80`
- `0x180009e20`
- `0x18000a120`
- `0x18000b288`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180009fe5`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180009fe5`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180009eb0`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180009fcd`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000a0ad`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180009eb0`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180009fcd`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000a0ad`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180009fc0`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180009fc0`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x180009f1a`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x18000a0a0`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x180009f1a`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x18000a0a0`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180009e8b`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180009ecf`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180009f80`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000a03f`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180009e8b`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180009ecf`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180009f80`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000a03f`
- `api-ms-win-core-registry-l2-1-0!RegDeleteKeyW` at `0x180009ea3`
- `api-ms-win-core-registry-l2-1-0!RegDeleteKeyW` at `0x18000a05b`
- `api-ms-win-core-registry-l2-1-0!RegDeleteKeyW` at `0x18000a065`
- `api-ms-win-core-registry-l2-1-0!RegDeleteKeyW` at `0x180009ea3`
- `api-ms-win-core-registry-l2-1-0!RegDeleteKeyW` at `0x18000a05b`
- `api-ms-win-core-registry-l2-1-0!RegDeleteKeyW` at `0x18000a065`

## string_xrefs

- `0x180009e74`: `CLSID`
- `0x18000a050`: `CLSID`
- `0x180009f48`: `\CLSID`

## pseudocode

```c
__int64 __fastcall RemoveAClass(LPCWSTR lpSubKey)
{
  unsigned int v2; // esi
  unsigned int v3; // ebx
  LSTATUS v4; // edi
  DWORD v5; // r14d
  __int64 v6; // rax
  __int64 v7; // rax
  unsigned __int64 v8; // rcx
  LSTATUS v9; // ebx
  DWORD cchName; // [rsp+40h] [rbp-C0h] BYREF
  HKEY phkResult; // [rsp+48h] [rbp-B8h] BYREF
  HKEY hKey; // [rsp+50h] [rbp-B0h] BYREF
  DWORD Type; // [rsp+58h] [rbp-A8h] BYREF
  struct _FILETIME ftLastWriteTime; // [rsp+60h] [rbp-A0h] BYREF
  wchar_t Name[264]; // [rsp+70h] [rbp-90h] BYREF
  BYTE Data[528]; // [rsp+280h] [rbp+180h] BYREF

  hKey = HKEY_CURRENT_USER_LOCAL_SETTINGS|0x7FFFFFF8LL;
  v2 = 0;
  v3 = 0;
  v4 = RegOpenKeyExW(HKEY_CLASSES_ROOT, L"CLSID", 0, 0x2001Fu, &hKey);
  if ( !v4 )
  {
    v2 = RegDeleteKeyW(hKey, lpSubKey);
    RegCloseKey(hKey);
    v4 = RegOpenKeyExW(HKEY_CLASSES_ROOT, 0, 0, 0x2001Fu, &hKey);
    if ( !v4 )
    {
      v5 = 0;
      while ( 1 )
      {
        cchName = 260;
        ftLastWriteTime = 0;
        v3 = RegEnumKeyExW(hKey, v5, Name, &cchName, 0, 0, 0, &ftLastWriteTime);
        if ( v3 )
          break;
        ++v5;
        v6 = -1;
        do
          ++v6;
        while ( Name[v6] );
        StringCchCatW(Name, 260 - v6, L"\\CLSID");
        phkResult = 0;
        if ( RegOpenKeyExW(HKEY_CLASSES_ROOT, Name, 0, 0x2001Fu, &phkResult) )
        {
          v4 = 0;
        }
        else
        {
          Type = 0;
          cchName = 520;
          v4 = RegQueryValueExW(phkResult, 0, 0, &Type, Data, &cchName);
          RegCloseKey(phkResult);
          if ( !v4 && !(unsigned int)_o__wcsicmp(Data, lpSubKey) )
          {
            v7 = -1;
            do
              ++v7;
            while ( Name[v7] );
            v8 = 2 * v7 - 12;
            if ( v8 >= 0x208 )
              _report_rangecheckfailure();
            *(wchar_t *)((char *)Name + v8) = 0;
            v4 = RegOpenKeyExW(HKEY_CLASSES_ROOT, Name, 0, 0x2001Fu, &phkResult);
            if ( !v4 )
            {
              if ( v2 )
                RegDeleteKeyW(phkResult, L"CLSID");
              else
                v2 = RegDeleteKeyW(phkResult, L"CLSID");
              v5 = 0;
            }
            cchName = 260;
            v9 = RegEnumKeyExW(phkResult, 0, Name, &cchName, 0, 0, 0, &ftLastWriteTime);
            RegCloseKey(phkResult);
            if ( v9 == 259 )
              RemoveAClassName(Name);
          }
        }
      }
    }
  }
  if ( v3 == 259 )
    v3 = v4;
  if ( v3 )
    return v3;
  return v2;
}

```

## disassembly

```asm
0x180009e20  mov     [rsp-8+arg_8], rbx
0x180009e25  mov     [rsp-8+arg_10], rsi
0x180009e2a  push    rbp
0x180009e2b  push    rdi
0x180009e2c  push    r12
0x180009e2e  push    r14
0x180009e30  push    r15
0x180009e32  lea     rbp, [rsp-3A0h]
0x180009e3a  sub     rsp, 4A0h
0x180009e41  mov     rax, cs:__security_cookie
0x180009e48  xor     rax, rsp
0x180009e4b  mov     [rbp+3C0h+var_30], rax
0x180009e52  mov     r15, rcx
0x180009e55  mov     [rsp+4C0h+hKey], 0FFFFFFFFFFFFFFFFh
0x180009e5e  xor     r12d, r12d
0x180009e61  lea     rax, [rsp+4C0h+hKey]
0x180009e66  mov     r14d, 2001Fh
0x180009e6c  mov     [rsp+4C0h+phkResult], rax; phkResult
0x180009e71  mov     r9d, r14d; samDesired
0x180009e74  lea     rdx, aClsid_1; "CLSID"
0x180009e7b  xor     r8d, r8d; ulOptions
0x180009e7e  mov     rcx, 0FFFFFFFF80000000h; hKey
0x180009e85  mov     esi, r12d
0x180009e88  mov     ebx, r12d
0x180009e8b  call    cs:__imp_RegOpenKeyExW
0x180009e91  mov     edi, eax
0x180009e93  test    eax, eax
0x180009e95  jnz     loc_18000A0D6
0x180009e9b  mov     rcx, [rsp+4C0h+hKey]; hKey
0x180009ea0  mov     rdx, r15; lpSubKey
0x180009ea3  call    cs:__imp_RegDeleteKeyW
0x180009ea9  mov     rcx, [rsp+4C0h+hKey]; hKey
0x180009eae  mov     esi, eax
0x180009eb0  call    cs:__imp_RegCloseKey
0x180009eb6  lea     rax, [rsp+4C0h+hKey]
0x180009ebb  mov     r9d, r14d; samDesired
0x180009ebe  xor     r8d, r8d; ulOptions
0x180009ec1  mov     [rsp+4C0h+phkResult], rax; phkResult
0x180009ec6  xor     edx, edx; lpSubKey
0x180009ec8  mov     rcx, 0FFFFFFFF80000000h; hKey
0x180009ecf  call    cs:__imp_RegOpenKeyExW
0x180009ed5  mov     edi, eax
0x180009ed7  test    eax, eax
0x180009ed9  jnz     loc_18000A0D6
0x180009edf  mov     r14d, r12d
0x180009ee2  mov     rcx, [rsp+4C0h+hKey]; hKey
0x180009ee7  lea     rax, [rsp+4C0h+ftLastWriteTime]
0x180009eec  mov     [rsp+4C0h+lpftLastWriteTime], rax; lpftLastWriteTime
0x180009ef1  lea     r9, [rsp+4C0h+cchName]; lpcchName
0x180009ef6  mov     [rsp+4C0h+lpcchClass], r12; lpcchClass
0x180009efb  lea     r8, [rsp+4C0h+Name]; lpName
0x180009f00  mov     [rsp+4C0h+lpClass], r12; lpClass
0x180009f05  mov     edx, r14d; dwIndex
0x180009f08  mov     [rsp+4C0h+phkResult], r12; lpReserved
0x180009f0d  mov     [rsp+4C0h+cchName], 104h
0x180009f15  mov     qword ptr [rsp+4C0h+ftLastWriteTime.dwLowDateTime], r12
0x180009f1a  call    cs:__imp_RegEnumKeyExW
0x180009f20  mov     ebx, eax
0x180009f22  test    eax, eax
0x180009f24  jnz     loc_18000A0D6
0x180009f2a  inc     r14d
0x180009f2d  lea     rcx, [rsp+4C0h+Name]
0x180009f32  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180009f36  mov     rax, rbx
0x180009f39  inc     rax
0x180009f3c  cmp     [rcx+rax*2], r12w
0x180009f41  jnz     short loc_180009F39
0x180009f43  mov     edx, 104h
0x180009f48  lea     r8, aClsid_0; "\\CLSID"
0x180009f4f  sub     rdx, rax; unsigned __int64
0x180009f52  lea     rcx, [rsp+4C0h+Name]; wchar_t *
0x180009f57  call    ?StringCchCatW@@YAJPEA_W_KPEB_W@Z; StringCchCatW(wchar_t *,unsigned __int64,wchar_t const *)
0x180009f5c  lea     rax, [rsp+4C0h+var_478]
0x180009f61  mov     [rsp+4C0h+var_478], r12
0x180009f66  mov     r9d, 2001Fh; samDesired
0x180009f6c  mov     [rsp+4C0h+phkResult], rax; phkResult
0x180009f71  xor     r8d, r8d; ulOptions
0x180009f74  lea     rdx, [rsp+4C0h+Name]; lpSubKey
0x180009f79  mov     rcx, 0FFFFFFFF80000000h; hKey
0x180009f80  call    cs:__imp_RegOpenKeyExW
0x180009f86  test    eax, eax
0x180009f88  jnz     loc_18000A0CE
0x180009f8e  mov     rcx, [rsp+4C0h+var_478]; hKey
0x180009f93  lea     rax, [rsp+4C0h+cchName]
0x180009f98  mov     [rsp+4C0h+lpClass], rax; lpcbData
0x180009f9d  lea     r9, [rsp+4C0h+Type]; lpType
0x180009fa2  lea     rax, [rbp+3C0h+Data]
0x180009fa9  mov     [rsp+4C0h+Type], r12d
0x180009fae  xor     r8d, r8d; lpReserved
0x180009fb1  mov     [rsp+4C0h+phkResult], rax; lpData
0x180009fb6  xor     edx, edx; lpValueName
0x180009fb8  mov     [rsp+4C0h+cchName], 208h
0x180009fc0  call    cs:__imp_RegQueryValueExW
0x180009fc6  mov     rcx, [rsp+4C0h+var_478]; hKey
0x180009fcb  mov     edi, eax
0x180009fcd  call    cs:__imp_RegCloseKey
0x180009fd3  test    edi, edi
0x180009fd5  jnz     loc_180009EE2
0x180009fdb  mov     rdx, r15
0x180009fde  lea     rcx, [rbp+3C0h+Data]
0x180009fe5  call    cs:__imp__o__wcsicmp
0x180009feb  test    eax, eax
0x180009fed  jnz     loc_180009EE2
0x180009ff3  lea     rcx, [rsp+4C0h+Name]
0x180009ff8  mov     rax, rbx
0x180009ffb  inc     rax
0x180009ffe  cmp     [rcx+rax*2], r12w
0x18000a003  jnz     short loc_180009FFB
0x18000a005  lea     rcx, ds:0FFFFFFFFFFFFFFF4h[rax*2]
0x18000a00d  cmp     rcx, 208h
0x18000a014  jnb     loc_18000A111
0x18000a01a  mov     [rsp+rcx+4C0h+Name], r12w
0x18000a020  lea     rax, [rsp+4C0h+var_478]
0x18000a025  mov     rcx, 0FFFFFFFF80000000h; hKey
0x18000a02c  mov     [rsp+4C0h+phkResult], rax; phkResult
0x18000a031  mov     r9d, 2001Fh; samDesired
0x18000a037  lea     rdx, [rsp+4C0h+Name]; lpSubKey
0x18000a03c  xor     r8d, r8d; ulOptions
0x18000a03f  call    cs:__imp_RegOpenKeyExW
0x18000a045  mov     edi, eax
0x18000a047  test    eax, eax
0x18000a049  jnz     short loc_18000A06E
0x18000a04b  mov     rcx, [rsp+4C0h+var_478]; hKey
0x18000a050  lea     rdx, aClsid_1; "CLSID"
0x18000a057  test    esi, esi
0x18000a059  jnz     short loc_18000A065
0x18000a05b  call    cs:__imp_RegDeleteKeyW
0x18000a061  mov     esi, eax
0x18000a063  jmp     short loc_18000A06B
0x18000a065  call    cs:__imp_RegDeleteKeyW
0x18000a06b  mov     r14d, r12d
0x18000a06e  mov     rcx, [rsp+4C0h+var_478]; hKey
0x18000a073  lea     rax, [rsp+4C0h+ftLastWriteTime]
0x18000a078  mov     [rsp+4C0h+lpftLastWriteTime], rax; lpftLastWriteTime
0x18000a07d  lea     r9, [rsp+4C0h+cchName]; lpcchName
0x18000a082  mov     [rsp+4C0h+lpcchClass], r12; lpcchClass
0x18000a087  lea     r8, [rsp+4C0h+Name]; lpName
0x18000a08c  mov     [rsp+4C0h+lpClass], r12; lpClass
0x18000a091  xor     edx, edx; dwIndex
0x18000a093  mov     [rsp+4C0h+phkResult], r12; lpReserved
0x18000a098  mov     [rsp+4C0h+cchName], 104h
0x18000a0a0  call    cs:__imp_RegEnumKeyExW
0x18000a0a6  mov     rcx, [rsp+4C0h+var_478]; hKey
0x18000a0ab  mov     ebx, eax
0x18000a0ad  call    cs:__imp_RegCloseKey
0x18000a0b3  cmp     ebx, 103h
0x18000a0b9  jnz     loc_180009EE2
0x18000a0bf  lea     rcx, [rsp+4C0h+Name]; lpSubKey
0x18000a0c4  call    ?RemoveAClassName@@YAJPEB_W@Z; RemoveAClassName(wchar_t const *)
0x18000a0c9  jmp     loc_180009EE2
0x18000a0ce  mov     edi, r12d
0x18000a0d1  jmp     loc_180009EE2
0x18000a0d6  cmp     ebx, 103h
0x18000a0dc  cmovz   ebx, edi
0x18000a0df  test    ebx, ebx
0x18000a0e1  cmovnz  esi, ebx
0x18000a0e4  mov     eax, esi
0x18000a0e6  mov     rcx, [rbp+3C0h+var_30]
0x18000a0ed  xor     rcx, rsp; StackCookie
0x18000a0f0  call    __security_check_cookie
0x18000a0f5  lea     r11, [rsp+4C0h+var_20]
0x18000a0fd  mov     rbx, [r11+38h]
0x18000a101  mov     rsi, [r11+40h]
0x18000a105  mov     rsp, r11
0x18000a108  pop     r15
0x18000a10a  pop     r14
0x18000a10c  pop     r12
0x18000a10e  pop     rdi
0x18000a10f  pop     rbp
0x18000a110  retn
0x18000a111  call    __report_rangecheckfailure
```
