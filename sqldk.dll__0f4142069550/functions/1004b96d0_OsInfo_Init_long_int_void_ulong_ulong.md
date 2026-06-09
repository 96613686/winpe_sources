# OsInfo::Init(long (*)(int,void *,ulong,ulong *))

- ea: `0x1004b96d0`
- end: `0x1004b9a10`
- name: `?Init@OsInfo@@QEAAXP6AJHPEAXKPEAK@Z@Z`
- size: `832`
- prototype: `void __fastcall(OsInfo *__hidden this, int (*)(int, void *, unsigned int, unsigned int *))`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1004b1350`

## callees

- `0x100458050`
- `0x1004b96d0`
- `0x1005b1fc0`

## import_xrefs

- `KERNEL32!GetProductInfo` at `0x1004b9877`
- `KERNEL32!GetProductInfo` at `0x1004b9877`
- `KERNEL32!GetSystemDefaultUILanguage` at `0x1004b9913`
- `KERNEL32!GetSystemDefaultUILanguage` at `0x1004b9913`
- `ADVAPI32!RegQueryValueExW` at `0x1004b98e8`
- `ADVAPI32!RegQueryValueExW` at `0x1004b9994`
- `ADVAPI32!RegQueryValueExW` at `0x1004b98e8`
- `ADVAPI32!RegQueryValueExW` at `0x1004b9994`
- `ADVAPI32!RegOpenKeyExW` at `0x1004b98b7`
- `ADVAPI32!RegOpenKeyExW` at `0x1004b995c`
- `ADVAPI32!RegOpenKeyExW` at `0x1004b98b7`
- `ADVAPI32!RegOpenKeyExW` at `0x1004b995c`
- `ADVAPI32!RegCloseKey` at `0x1004b98fa`
- `ADVAPI32!RegCloseKey` at `0x1004b99d1`
- `ADVAPI32!RegCloseKey` at `0x1004b98fa`
- `ADVAPI32!RegCloseKey` at `0x1004b99d1`
- `api-ms-win-crt-string-l1-1-0!_wcsicmp` at `0x1004b99de`
- `api-ms-win-crt-string-l1-1-0!_wcsicmp` at `0x1004b99f7`
- `api-ms-win-crt-string-l1-1-0!_wcsicmp` at `0x1004b99de`
- `api-ms-win-crt-string-l1-1-0!_wcsicmp` at `0x1004b99f7`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall OsInfo::Init(OsInfo *this, unsigned int (__fastcall *a2)(__int64, DWORD *, __int64))
{
  int v4; // ebx
  LSTATUS v5; // ebx
  const wchar_t *v6; // rax
  PDWORD pdwReturnedProductType; // [rsp+20h] [rbp-48h]
  DWORD cbData; // [rsp+70h] [rbp+8h] BYREF
  HKEY phkResult; // [rsp+78h] [rbp+10h] BYREF
  DWORD lpcbData; // [rsp+80h] [rbp+18h] BYREF
  HKEY hKey; // [rsp+88h] [rbp+20h] BYREF

  if ( !a2 )
    utassert_fail(1u, "nullptr != pfnNtQuerySystemInformation", "osinfo.cpp", 88, 0);
  *(_BYTE *)this = 1;
  if ( ((unsigned int (__fastcall *)(__int64, char *, __int64, _QWORD))a2)(5000, (char *)this + 368, 1088, 0) )
  {
    *((_BYTE *)this + 1) = 0;
    *((_QWORD *)this + 1) = L"Windows";
    LODWORD(pdwReturnedProductType) = *(_DWORD *)&dwOSMajorVersion;
    StringCchPrintf_lW(
      (wchar_t *)this + 33,
      0x14u,
      L"%ld.%ld",
      g_crtLocale,
      pdwReturnedProductType,
      *(_DWORD *)&dwOSMinorVersion,
      -2);
    *((_QWORD *)this + 3) = (char *)this + 66;
    *((_QWORD *)this + 7) = &byte_1007AC154;
    if ( !GetProductInfo(*(DWORD *)&dwOSMajorVersion, *(DWORD *)&dwOSMinorVersion, 0, 0, (PDWORD)this + 13) )
      goto LABEL_16;
    *((_BYTE *)this + 48) = 1;
    cbData = 128;
    phkResult = 0;
    v5 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"SOFTWARE\\Microsoft\\Windows NT\\CurrentVersion", 0, 0x20019u, &phkResult);
    if ( !v5 )
      v5 = RegQueryValueExW(phkResult, L"ProductName", 0, 0, (LPBYTE)this + 106, &cbData);
    if ( phkResult )
      RegCloseKey(phkResult);
    v6 = (const wchar_t *)((char *)this + 106);
    if ( v5 )
LABEL_16:
      v6 = L"Microsoft Windows";
    *((_QWORD *)this + 2) = v6;
    *((_WORD *)this + 32) = GetSystemDefaultUILanguage();
    hKey = 0;
    cbData = 0;
    LODWORD(phkResult) = 0;
    lpcbData = 4;
    if ( !RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"SYSTEM\\CurrentControlSet\\Control", 0, 1u, &hKey) )
    {
      if ( !RegQueryValueExW(hKey, L"ContainerType", 0, &cbData, (LPBYTE)&phkResult, &lpcbData) && cbData == 4 )
      {
        if ( (_DWORD)phkResult == 1 )
        {
          *((_DWORD *)this + 91) = 2;
        }
        else if ( (_DWORD)phkResult == 2 )
        {
          *((_DWORD *)this + 91) = 3;
        }
      }
      RegCloseKey(hKey);
    }
  }
  else
  {
    *((_BYTE *)this + 1) = 1;
    *((_QWORD *)this + 1) = (char *)this + 368;
    *((_QWORD *)this + 2) = (char *)this + 432;
    *((_QWORD *)this + 3) = (char *)this + 688;
    *((_QWORD *)this + 4) = (char *)this + 944;
    *((_QWORD *)this + 5) = (char *)this + 1200;
    *((_BYTE *)this + 48) = 0;
    *((_QWORD *)this + 7) = &word_10067A4A0;
    if ( a2(5002, &cbData, 4) )
      utassert_fail(1u, "status == STATUS_SUCCESS", "osinfo.cpp", 164, 0);
    *((_WORD *)this + 32) = cbData;
    if ( !a2(5003, (DWORD *)&phkResult, 8) )
    {
      v4 = (int)phkResult;
      if ( (int)phkResult >= 4 )
        utassert_fail(1u, "containerType < CT_LAST", "osinfo.cpp", 181, 0);
      *((_DWORD *)this + 91) = v4;
    }
  }
  *((_BYTE *)this + 2) = _wcsicmp(*((const wchar_t **)this + 1), L"Windows") == 0;
  *((_BYTE *)this + 3) = _wcsicmp(*((const wchar_t **)this + 1), L"Linux") == 0;
}

```

## disassembly

```asm
0x1004b96d0  push    rbx
0x1004b96d2  push    rbp
0x1004b96d3  push    rsi
0x1004b96d4  push    rdi
0x1004b96d5  push    r14
0x1004b96d7  sub     rsp, 40h
0x1004b96db  mov     [rsp+68h+var_38], 0FFFFFFFFFFFFFFFEh
0x1004b96e4  mov     rbx, rdx
0x1004b96e7  mov     rdi, rcx
0x1004b96ea  xor     ebp, ebp
0x1004b96ec  test    rdx, rdx
0x1004b96ef  jnz     short loc_1004B9710
0x1004b96f1  mov     [rsp+68h+pdwReturnedProductType], rbp; Format
0x1004b96f6  lea     r9d, [rdx+58h]; int
0x1004b96fa  lea     r8, aOsinfoCpp; "osinfo.cpp"
0x1004b9701  lea     rdx, aNullptrPfnntqu; "nullptr != pfnNtQuerySystemInformation"
0x1004b9708  lea     ecx, [rbx+1]; unsigned int
0x1004b970b  call    ?utassert_fail@@YAXIPEBD0H0ZZ; utassert_fail(uint,char const *,char const *,int,char const *,...)
0x1004b9710  mov     byte ptr [rdi], 1
0x1004b9713  lea     rsi, [rdi+170h]
0x1004b971a  xor     r9d, r9d
0x1004b971d  mov     r8d, 440h
0x1004b9723  mov     rdx, rsi
0x1004b9726  mov     ecx, 1388h
0x1004b972b  call    rbx
0x1004b972d  lea     r14, aWindows; "Windows"
0x1004b9734  test    eax, eax
0x1004b9736  jnz     loc_1004B9812
0x1004b973c  mov     byte ptr [rdi+1], 1
0x1004b9740  mov     [rdi+8], rsi
0x1004b9744  lea     rax, [rdi+1B0h]
0x1004b974b  mov     [rdi+10h], rax
0x1004b974f  lea     rax, [rdi+2B0h]
0x1004b9756  mov     [rdi+18h], rax
0x1004b975a  lea     rax, [rdi+3B0h]
0x1004b9761  mov     [rdi+20h], rax
0x1004b9765  lea     rax, [rdi+4B0h]
0x1004b976c  mov     [rdi+28h], rax
0x1004b9770  mov     [rdi+30h], bpl
0x1004b9774  lea     rax, word_10067A4A0
0x1004b977b  mov     [rdi+38h], rax
0x1004b977f  xor     r9d, r9d
0x1004b9782  lea     r8d, [r9+4]
0x1004b9786  lea     rdx, [rsp+68h+cbData]
0x1004b978b  mov     ecx, 138Ah
0x1004b9790  call    rbx
0x1004b9792  test    eax, eax
0x1004b9794  jz      short loc_1004B97B9
0x1004b9796  mov     [rsp+68h+pdwReturnedProductType], rbp; Format
0x1004b979b  mov     r9d, 0A4h; int
0x1004b97a1  lea     r8, aOsinfoCpp; "osinfo.cpp"
0x1004b97a8  lea     rdx, aStatusStatusSu; "status == STATUS_SUCCESS"
0x1004b97af  mov     ecx, 1; unsigned int
0x1004b97b4  call    ?utassert_fail@@YAXIPEBD0H0ZZ; utassert_fail(uint,char const *,char const *,int,char const *,...)
0x1004b97b9  movzx   eax, word ptr [rsp+68h+cbData]
0x1004b97be  mov     [rdi+40h], ax
0x1004b97c2  xor     r9d, r9d
0x1004b97c5  lea     r8d, [r9+8]
0x1004b97c9  lea     rdx, [rsp+68h+phkResult]
0x1004b97ce  mov     ecx, 138Bh
0x1004b97d3  call    rbx
0x1004b97d5  test    eax, eax
0x1004b97d7  jnz     loc_1004B99D7
0x1004b97dd  mov     ebx, dword ptr [rsp+68h+phkResult]
0x1004b97e1  cmp     ebx, 4
0x1004b97e4  jl      short loc_1004B9807
0x1004b97e6  mov     [rsp+68h+pdwReturnedProductType], rbp; Format
0x1004b97eb  mov     r9d, 0B5h; int
0x1004b97f1  lea     r8, aOsinfoCpp; "osinfo.cpp"
0x1004b97f8  lea     rdx, aContainertypeC; "containerType < CT_LAST"
0x1004b97ff  lea     ecx, [rax+1]; unsigned int
0x1004b9802  call    ?utassert_fail@@YAXIPEBD0H0ZZ; utassert_fail(uint,char const *,char const *,int,char const *,...)
0x1004b9807  mov     [rdi+16Ch], ebx
0x1004b980d  jmp     loc_1004B99D7
0x1004b9812  mov     [rdi+1], bpl
0x1004b9816  mov     [rdi+8], r14
0x1004b981a  lea     rbx, [rdi+42h]
0x1004b981e  mov     eax, cs:dwOSMinorVersion
0x1004b9824  mov     dword ptr [rsp+68h+lpcbData], eax
0x1004b9828  mov     eax, cs:dwOSMajorVersion
0x1004b982e  mov     dword ptr [rsp+68h+pdwReturnedProductType], eax
0x1004b9832  mov     r9, cs:?g_crtLocale@@3PEAU__crt_locale_pointers@@EA; struct __crt_locale_pointers *
0x1004b9839  lea     r8, aLdLd; "%ld.%ld"
0x1004b9840  mov     edx, 14h; unsigned __int64
0x1004b9845  mov     rcx, rbx; Buffer
0x1004b9848  call    ?StringCchPrintf_lW@@YAJPEA_W_KPEB_WPEAU__crt_locale_pointers@@ZZ; StringCchPrintf_lW(wchar_t *,unsigned __int64,wchar_t const *,__crt_locale_pointers *,...)
0x1004b984d  mov     [rdi+18h], rbx
0x1004b9851  lea     rax, byte_1007AC154
0x1004b9858  mov     [rdi+38h], rax
0x1004b985c  lea     rax, [rdi+34h]
0x1004b9860  mov     [rsp+68h+pdwReturnedProductType], rax; pdwReturnedProductType
0x1004b9865  xor     r9d, r9d; dwSpMinorVersion
0x1004b9868  xor     r8d, r8d; dwSpMajorVersion
0x1004b986b  mov     edx, cs:dwOSMinorVersion; dwOSMinorVersion
0x1004b9871  mov     ecx, cs:dwOSMajorVersion; dwOSMajorVersion
0x1004b9877  call    cs:__imp_GetProductInfo
0x1004b987d  test    eax, eax
0x1004b987f  jz      loc_1004B9908
0x1004b9885  mov     byte ptr [rdi+30h], 1
0x1004b9889  mov     [rsp+68h+cbData], 80h
0x1004b9891  mov     [rsp+68h+phkResult], rbp
0x1004b9896  lea     rax, [rsp+68h+phkResult]
0x1004b989b  mov     [rsp+68h+pdwReturnedProductType], rax; phkResult
0x1004b98a0  mov     r9d, 20019h; samDesired
0x1004b98a6  xor     r8d, r8d; ulOptions
0x1004b98a9  lea     rdx, SubKey; "SOFTWARE\\Microsoft\\Windows NT\\Curren"...
0x1004b98b0  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1004b98b7  call    cs:__imp_RegOpenKeyExW
0x1004b98bd  mov     ebx, eax
0x1004b98bf  test    eax, eax
0x1004b98c1  jnz     short loc_1004B98F0
0x1004b98c3  lea     rax, [rdi+6Ah]
0x1004b98c7  lea     rcx, [rsp+68h+cbData]
0x1004b98cc  mov     [rsp+68h+lpcbData], rcx; lpcbData
0x1004b98d1  mov     [rsp+68h+pdwReturnedProductType], rax; lpData
0x1004b98d6  xor     r9d, r9d; lpType
0x1004b98d9  xor     r8d, r8d; lpReserved
0x1004b98dc  lea     rdx, aProductname; "ProductName"
0x1004b98e3  mov     rcx, [rsp+68h+phkResult]; hKey
0x1004b98e8  call    cs:__imp_RegQueryValueExW
0x1004b98ee  mov     ebx, eax
0x1004b98f0  mov     rcx, [rsp+68h+phkResult]; hKey
0x1004b98f5  test    rcx, rcx
0x1004b98f8  jz      short loc_1004B9900
0x1004b98fa  call    cs:__imp_RegCloseKey
0x1004b9900  test    ebx, ebx
0x1004b9902  lea     rax, [rdi+6Ah]
0x1004b9906  jz      short loc_1004B990F
0x1004b9908  lea     rax, aMicrosoftWindo; "Microsoft Windows"
0x1004b990f  mov     [rdi+10h], rax
0x1004b9913  call    cs:__imp_GetSystemDefaultUILanguage
0x1004b9919  mov     [rdi+40h], ax
0x1004b991d  mov     [rsp+68h+hKey], rbp
0x1004b9925  mov     [rsp+68h+cbData], ebp
0x1004b9929  mov     dword ptr [rsp+68h+phkResult], ebp
0x1004b992d  mov     [rsp+68h+arg_10], 4
0x1004b9938  lea     rax, [rsp+68h+hKey]
0x1004b9940  mov     [rsp+68h+pdwReturnedProductType], rax; phkResult
0x1004b9945  mov     r9d, 1; samDesired
0x1004b994b  xor     r8d, r8d; ulOptions
0x1004b994e  lea     rdx, aSystemCurrentc; "SYSTEM\\CurrentControlSet\\Control"
0x1004b9955  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1004b995c  call    cs:__imp_RegOpenKeyExW
0x1004b9962  test    eax, eax
0x1004b9964  jnz     short loc_1004B99D7
0x1004b9966  lea     rax, [rsp+68h+arg_10]
0x1004b996e  mov     [rsp+68h+lpcbData], rax; lpcbData
0x1004b9973  lea     rax, [rsp+68h+phkResult]
0x1004b9978  mov     [rsp+68h+pdwReturnedProductType], rax; lpData
0x1004b997d  lea     r9, [rsp+68h+cbData]; lpType
0x1004b9982  xor     r8d, r8d; lpReserved
0x1004b9985  lea     rdx, aContainertype; "ContainerType"
0x1004b998c  mov     rcx, [rsp+68h+hKey]; hKey
0x1004b9994  call    cs:__imp_RegQueryValueExW
0x1004b999a  test    eax, eax
0x1004b999c  jnz     short loc_1004B99C9
0x1004b999e  cmp     [rsp+68h+cbData], 4
0x1004b99a3  jnz     short loc_1004B99C9
0x1004b99a5  mov     eax, dword ptr [rsp+68h+phkResult]
0x1004b99a9  cmp     eax, 1
0x1004b99ac  jnz     short loc_1004B99BA
0x1004b99ae  mov     dword ptr [rdi+16Ch], 2
0x1004b99b8  jmp     short loc_1004B99C9
0x1004b99ba  cmp     eax, 2
0x1004b99bd  jnz     short loc_1004B99C9
0x1004b99bf  mov     dword ptr [rdi+16Ch], 3
0x1004b99c9  mov     rcx, [rsp+68h+hKey]; hKey
0x1004b99d1  call    cs:__imp_RegCloseKey
0x1004b99d7  mov     rdx, r14; String2
0x1004b99da  mov     rcx, [rdi+8]; String1
0x1004b99de  call    cs:__imp__wcsicmp
0x1004b99e4  test    eax, eax
0x1004b99e6  setz    al
0x1004b99e9  mov     [rdi+2], al
0x1004b99ec  lea     rdx, aLinux; "Linux"
0x1004b99f3  mov     rcx, [rdi+8]; String1
0x1004b99f7  call    cs:__imp__wcsicmp
0x1004b99fd  test    eax, eax
0x1004b99ff  setz    al
0x1004b9a02  mov     [rdi+3], al
0x1004b9a05  add     rsp, 40h
0x1004b9a09  pop     r14
0x1004b9a0b  pop     rdi
0x1004b9a0c  pop     rsi
0x1004b9a0d  pop     rbp
0x1004b9a0e  pop     rbx
0x1004b9a0f  retn
```
