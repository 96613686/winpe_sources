# SpGetDescription(ISpObjectToken *,ushort * *,ushort)

- ea: `0x180013ba0`
- end: `0x180013e51`
- name: `?SpGetDescription@@YAJPEAUISpObjectToken@@PEAPEAGG@Z`
- size: `689`
- prototype: `__int64 __fastcall(struct ISpObjectToken *, unsigned __int16 **, unsigned __int16)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x18000e6b0`

## callees

- `0x1800034b0`
- `0x1800040b8`
- `0x1800042fa`
- `0x180013ba0`
- `0x180013e58`
- `0x180102010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x180013cb4`
- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x180013cb4`
- `api-ms-win-core-sysinfo-l1-1-0!GetVersionExW` at `0x180013c1f`
- `api-ms-win-core-sysinfo-l1-1-0!GetVersionExW` at `0x180013c1f`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180013dc7`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180013dc7`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180013c67`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180013c67`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180013db9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180013dd9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180013db9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180013dd9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180013d3e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180013d3e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180013da9`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180013da9`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180013d2b`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180013d2b`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x180013c4b`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x180013c4b`

## string_xrefs

- `0x180013c44`: `advapi32.dll`

## pseudocode

```c
__int64 __fastcall SpGetDescription(struct ISpObjectToken *a1, LPVOID *a2, unsigned __int16 a3)
{
  unsigned int v3; // r12d
  HMODULE LibraryW; // rax
  HMODULE v7; // r14
  FARPROC ProcAddress; // r15
  signed int v9; // ebx
  wchar_t *v10; // rax
  const WCHAR *v11; // rbx
  __int64 v12; // rcx
  bool v13; // cc
  unsigned __int16 *v14; // rax
  HKEY v15; // rcx
  wchar_t *Str; // [rsp+40h] [rbp-C0h] BYREF
  HKEY hKey; // [rsp+48h] [rbp-B8h] BYREF
  struct _OSVERSIONINFOW VersionInformation; // [rsp+50h] [rbp-B0h] BYREF
  unsigned __int16 v20[12]; // [rsp+170h] [rbp+70h] BYREF

  v3 = a3;
  Str = 0;
  hKey = 0;
  if ( a2 && a1 )
  {
    memset_0(&VersionInformation.dwMajorVersion, 0, 0x110u);
    VersionInformation.dwOSVersionInfoSize = 276;
    *a2 = 0;
    if ( !GetVersionExW(&VersionInformation)
      || VersionInformation.dwPlatformId != 2
      || VersionInformation.dwMajorVersion < 6 )
    {
LABEL_30:
      if ( *a2 )
      {
        CoTaskMemFree(*a2);
        *a2 = 0;
      }
      SpHexFromUlong(v20, v3);
      v9 = ((__int64 (__fastcall *)(struct ISpObjectToken *, unsigned __int16 *, LPVOID *))a1->lpVtbl->GetStringValue)(
             a1,
             v20,
             a2);
      if ( v9 == -2147200966 )
        return ((unsigned int (__fastcall *)(struct ISpObjectToken *, _QWORD, LPVOID *))a1->lpVtbl->GetStringValue)(
                 a1,
                 0,
                 a2);
      return (unsigned int)v9;
    }
    LibraryW = LoadLibraryW(L"advapi32.dll");
    v7 = LibraryW;
    if ( LibraryW )
    {
      ProcAddress = GetProcAddress(LibraryW, "RegLoadMUIStringW");
      v9 = ProcAddress == 0 ? 0x8002802F : 0;
      if ( ProcAddress )
      {
        v9 = ((__int64 (__fastcall *)(struct ISpObjectToken *, wchar_t **))a1->lpVtbl->GetId)(a1, &Str);
        if ( v9 >= 0 )
        {
          v10 = wcschr(Str, 0x5Cu);
          if ( !v10 )
          {
            LOWORD(v9) = 160;
LABEL_21:
            v9 = (unsigned __int16)v9 | 0x80070000;
            goto LABEL_23;
          }
          *v10 = 0;
          v11 = v10 + 1;
          *a2 = 0;
          if ( !wcsncmp_0(Str, L"HKEY_LOCAL_MACHINE", 0x104u) )
          {
            v12 = -2147483646;
          }
          else
          {
            if ( wcsncmp_0(Str, L"HKEY_CURRENT_USER", 0x104u) )
            {
              v9 = 160;
              goto LABEL_17;
            }
            v12 = -2147483647;
          }
          v9 = RegOpenKeyExW((HKEY)v12, v11, 0, 1u, &hKey);
          v13 = v9 <= 0;
          if ( v9 )
            goto LABEL_18;
          v14 = (unsigned __int16 *)CoTaskMemAlloc(0x208u);
          v15 = hKey;
          *a2 = v14;
          v9 = ((__int64 (__fastcall *)(HKEY, const wchar_t *, unsigned __int16 *, __int64, _QWORD, int, _QWORD))ProcAddress)(
                 v15,
                 L"Description",
                 v14,
                 520,
                 0,
                 1,
                 0);
LABEL_17:
          v13 = v9 <= 0;
LABEL_18:
          if ( v13 )
            goto LABEL_23;
          goto LABEL_21;
        }
      }
    }
    else
    {
      v9 = -2147023739;
    }
LABEL_23:
    if ( hKey )
      RegCloseKey(hKey);
    if ( Str )
      CoTaskMemFree(Str);
    if ( v7 )
      FreeLibrary(v7);
    if ( v9 >= 0 )
      return (unsigned int)v9;
    goto LABEL_30;
  }
  return 2147500035LL;
}

```

## disassembly

```asm
0x180013ba0  push    rbp
0x180013ba2  push    rbx
0x180013ba3  push    rsi
0x180013ba4  push    rdi
0x180013ba5  push    r12
0x180013ba7  push    r14
0x180013ba9  push    r15
0x180013bab  lea     rbp, [rsp-90h]
0x180013bb3  sub     rsp, 190h
0x180013bba  mov     rax, cs:__security_cookie
0x180013bc1  xor     rax, rsp
0x180013bc4  mov     [rbp+0C0h+var_38], rax
0x180013bcb  movzx   r12d, r8w
0x180013bcf  mov     rdi, rdx
0x180013bd2  mov     [rsp+1C0h+Str], 0
0x180013bdb  mov     rsi, rcx
0x180013bde  mov     [rsp+1C0h+hKey], 0
0x180013be7  test    rdx, rdx
0x180013bea  jz      loc_180013E2B
0x180013bf0  test    rcx, rcx
0x180013bf3  jz      loc_180013E2B
0x180013bf9  xor     edx, edx; Val
0x180013bfb  lea     rcx, [rsp+1C0h+VersionInformation.dwMajorVersion]; void *
0x180013c00  mov     r8d, 110h; Size
0x180013c06  call    memset_0
0x180013c0b  lea     rcx, [rsp+1C0h+VersionInformation]; lpVersionInformation
0x180013c10  mov     [rsp+1C0h+VersionInformation.dwOSVersionInfoSize], 114h
0x180013c18  mov     qword ptr [rdi], 0
0x180013c1f  call    cs:__imp_GetVersionExW
0x180013c25  cmp     eax, 1
0x180013c28  jnz     loc_180013DD1
0x180013c2e  cmp     [rsp+1C0h+VersionInformation.dwPlatformId], 2
0x180013c33  jnz     loc_180013DD1
0x180013c39  cmp     [rsp+1C0h+VersionInformation.dwMajorVersion], 6
0x180013c3e  jb      loc_180013DD1
0x180013c44  lea     rcx, LibFileName; "advapi32.dll"
0x180013c4b  call    cs:__imp_LoadLibraryW
0x180013c51  mov     r14, rax
0x180013c54  test    rax, rax
0x180013c57  jz      loc_180013D9A
0x180013c5d  lea     rdx, aRegloadmuistri; "RegLoadMUIStringW"
0x180013c64  mov     rcx, rax; hModule
0x180013c67  call    cs:__imp_GetProcAddress
0x180013c6d  mov     rcx, rax
0x180013c70  mov     r15, rax
0x180013c73  neg     rcx
0x180013c76  sbb     ebx, ebx
0x180013c78  not     ebx
0x180013c7a  and     ebx, 8002802Fh
0x180013c80  test    rax, rax
0x180013c83  jz      loc_180013D9F
0x180013c89  mov     rax, [rsi]
0x180013c8c  lea     rdx, [rsp+1C0h+Str]
0x180013c91  mov     rcx, rsi
0x180013c94  mov     rax, [rax+80h]
0x180013c9b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013ca0  mov     ebx, eax
0x180013ca2  test    eax, eax
0x180013ca4  js      loc_180013D9F
0x180013caa  mov     rcx, [rsp+1C0h+Str]; Str
0x180013caf  mov     edx, 5Ch ; '\'; Ch
0x180013cb4  call    cs:__imp_wcschr
0x180013cba  test    rax, rax
0x180013cbd  jz      loc_180013D8A
0x180013cc3  xor     ecx, ecx
0x180013cc5  lea     rdx, aHkeyLocalMachi_0; "HKEY_LOCAL_MACHINE"
0x180013ccc  mov     [rax], cx
0x180013ccf  lea     rbx, [rax+2]
0x180013cd3  mov     [rdi], rcx
0x180013cd6  mov     r8d, 104h; MaxCount
0x180013cdc  mov     rcx, [rsp+1C0h+Str]; String1
0x180013ce1  call    wcsncmp_0
0x180013ce6  test    eax, eax
0x180013ce8  jnz     short loc_180013CF3
0x180013cea  mov     rcx, 0FFFFFFFF80000002h
0x180013cf1  jmp     short loc_180013D15
0x180013cf3  mov     rcx, [rsp+1C0h+Str]; String1
0x180013cf8  lea     rdx, aHkeyCurrentUse_0; "HKEY_CURRENT_USER"
0x180013cff  mov     r8d, 104h; MaxCount
0x180013d05  call    wcsncmp_0
0x180013d0a  test    eax, eax
0x180013d0c  jnz     short loc_180013D7F
0x180013d0e  mov     rcx, 0FFFFFFFF80000001h; hKey
0x180013d15  lea     rax, [rsp+1C0h+hKey]
0x180013d1a  mov     r9d, 1; samDesired
0x180013d20  xor     r8d, r8d; ulOptions
0x180013d23  mov     [rsp+1C0h+phkResult], rax; phkResult
0x180013d28  mov     rdx, rbx; lpSubKey
0x180013d2b  call    cs:__imp_RegOpenKeyExW
0x180013d31  mov     ebx, eax
0x180013d33  test    eax, eax
0x180013d35  jnz     short loc_180013D86
0x180013d37  mov     ebx, 208h
0x180013d3c  mov     ecx, ebx; cb
0x180013d3e  call    cs:__imp_CoTaskMemAlloc
0x180013d44  mov     rcx, [rsp+1C0h+hKey]
0x180013d49  lea     rdx, aDescription; "Description"
0x180013d50  mov     [rdi], rax
0x180013d53  mov     r8, rax
0x180013d56  mov     [rsp+1C0h+var_190], 0
0x180013d5f  mov     rax, r15
0x180013d62  mov     [rsp+1C0h+var_198], 1
0x180013d6a  mov     r9d, ebx
0x180013d6d  mov     [rsp+1C0h+phkResult], 0
0x180013d76  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013d7b  mov     ebx, eax
0x180013d7d  jmp     short loc_180013D84
0x180013d7f  mov     ebx, 0A0h
0x180013d84  test    ebx, ebx
0x180013d86  jle     short loc_180013D9F
0x180013d88  jmp     short loc_180013D8F
0x180013d8a  mov     ebx, 0A0h
0x180013d8f  movzx   ebx, bx
0x180013d92  or      ebx, 80070000h
0x180013d98  jmp     short loc_180013D9F
0x180013d9a  mov     ebx, 80070485h
0x180013d9f  mov     rcx, [rsp+1C0h+hKey]; hKey
0x180013da4  test    rcx, rcx
0x180013da7  jz      short loc_180013DAF
0x180013da9  call    cs:__imp_RegCloseKey
0x180013daf  mov     rcx, [rsp+1C0h+Str]; pv
0x180013db4  test    rcx, rcx
0x180013db7  jz      short loc_180013DBF
0x180013db9  call    cs:__imp_CoTaskMemFree
0x180013dbf  test    r14, r14
0x180013dc2  jz      short loc_180013DCD
0x180013dc4  mov     rcx, r14; hLibModule
0x180013dc7  call    cs:__imp_FreeLibrary
0x180013dcd  test    ebx, ebx
0x180013dcf  jns     short loc_180013E27
0x180013dd1  mov     rcx, [rdi]; pv
0x180013dd4  test    rcx, rcx
0x180013dd7  jz      short loc_180013DE6
0x180013dd9  call    cs:__imp_CoTaskMemFree
0x180013ddf  mov     qword ptr [rdi], 0
0x180013de6  mov     edx, r12d; unsigned int
0x180013de9  lea     rcx, [rbp+0C0h+var_50]; unsigned __int16 *
0x180013ded  call    ?SpHexFromUlong@@YAXPEAGK@Z; SpHexFromUlong(ushort *,ulong)
0x180013df2  mov     rax, [rsi]
0x180013df5  lea     rdx, [rbp+0C0h+var_50]
0x180013df9  mov     r8, rdi
0x180013dfc  mov     rcx, rsi
0x180013dff  mov     rax, [rax+30h]
0x180013e03  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013e08  mov     ebx, eax
0x180013e0a  cmp     eax, 8004503Ah
0x180013e0f  jnz     short loc_180013E27
0x180013e11  mov     rax, [rsi]
0x180013e14  mov     r8, rdi
0x180013e17  xor     edx, edx
0x180013e19  mov     rcx, rsi
0x180013e1c  mov     rax, [rax+30h]
0x180013e20  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013e25  mov     ebx, eax
0x180013e27  mov     eax, ebx
0x180013e29  jmp     short loc_180013E30
0x180013e2b  mov     eax, 80004003h
0x180013e30  mov     rcx, [rbp+0C0h+var_38]
0x180013e37  xor     rcx, rsp; StackCookie
0x180013e3a  call    __security_check_cookie
0x180013e3f  add     rsp, 190h
0x180013e46  pop     r15
0x180013e48  pop     r14
0x180013e4a  pop     r12
0x180013e4c  pop     rdi
0x180013e4d  pop     rsi
0x180013e4e  pop     rbx
0x180013e4f  pop     rbp
0x180013e50  retn
```
