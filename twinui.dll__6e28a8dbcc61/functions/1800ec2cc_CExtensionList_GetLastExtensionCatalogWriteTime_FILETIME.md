# CExtensionList::_GetLastExtensionCatalogWriteTime(_FILETIME *)

- ea: `0x1800ec2cc`
- end: `0x1800ec4ea`
- name: `?_GetLastExtensionCatalogWriteTime@CExtensionList@@AEAAJPEAU_FILETIME@@@Z`
- size: `542`
- prototype: `__int64 __fastcall(CExtensionList *__hidden this, struct _FILETIME *)`
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x180058ba8`
- `0x1803678a0`

## callees

- `0x1800ec2cc`
- `0x1800ec758`
- `0x18013d330`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1800ec45d`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1800ec49b`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1800ec45d`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1800ec49b`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x1800ec406`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x1800ec406`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800ec486`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800ec486`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800ec35f`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800ec35f`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x1800ec3b6`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x1800ec3b6`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x1800ec429`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x1800ec46d`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x1800ec429`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x1800ec46d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800ec4ae`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800ec4ae`

## string_xrefs

- `0x1800ec2fe`: `Extensions\ContractId`

## pseudocode

```c
__int64 __fastcall CExtensionList::_GetLastExtensionCatalogWriteTime(CExtensionList *this, struct _FILETIME *a2)
{
  __int64 v3; // r9
  signed int v4; // ebx
  LSTATUS v5; // eax
  LSTATUS v6; // eax
  signed int v7; // edi
  DWORD v8; // ebx
  LSTATUS v9; // eax
  struct _FILETIME ftLastWriteTime; // [rsp+60h] [rbp-A0h] BYREF
  FILETIME FileTime1; // [rsp+68h] [rbp-98h] BYREF
  HKEY hKey; // [rsp+70h] [rbp-90h] BYREF
  DWORD cchName; // [rsp+78h] [rbp-88h] BYREF
  LPCWSTR lpSubKey[4]; // [rsp+80h] [rbp-80h] BYREF
  WCHAR Name[264]; // [rsp+A0h] [rbp-60h] BYREF

  ftLastWriteTime = 0;
  *a2 = 0;
  v3 = *((_QWORD *)this + 9);
  memset(lpSubKey, 0, 24);
  v4 = Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::ConcatFormat(
         lpSubKey,
         L"%s\\%s",
         L"Extensions\\ContractId",
         v3);
  if ( v4 >= 0 )
  {
    hKey = 0;
    v5 = RegOpenKeyExW(HKEY_CLASSES_ROOT, lpSubKey[0], 0, 0x20019u, &hKey);
    v4 = v5;
    if ( v5 > 0 )
      v4 = (unsigned __int16)v5 | 0x80070000;
    if ( v4 < 0 )
    {
      if ( v4 == -2147024894 )
      {
        GetSystemTimeAsFileTime(&ftLastWriteTime);
        v4 = 0;
      }
    }
    else
    {
      v6 = RegQueryInfoKeyW(hKey, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, &ftLastWriteTime);
      v7 = v6;
      if ( v6 > 0 )
        v7 = (unsigned __int16)v6 | 0x80070000;
      v8 = 0;
      while ( v7 >= 0 )
      {
        cchName = 260;
        FileTime1 = 0;
        v9 = RegEnumKeyExW(hKey, v8, Name, &cchName, 0, 0, 0, &FileTime1);
        v7 = v9;
        if ( v9 > 0 )
          v7 = (unsigned __int16)v9 | 0x80070000;
        if ( v7 >= 0 && CompareFileTime(&FileTime1, &ftLastWriteTime) > 0 )
          ftLastWriteTime = FileTime1;
        ++v8;
      }
      v4 = 0;
      if ( v7 != -2147024637 )
        v4 = v7;
      if ( v4 >= 0 )
      {
        FileTime1 = 0;
        GetSystemTimeAsFileTime(&FileTime1);
        if ( CompareFileTime(&FileTime1, &ftLastWriteTime) < 0 )
          ftLastWriteTime = FileTime1;
      }
      RegCloseKey(hKey);
    }
  }
  if ( lpSubKey[0] )
    CoTaskMemFree((LPVOID)lpSubKey[0]);
  if ( v4 >= 0 )
    *a2 = ftLastWriteTime;
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x1800ec2cc  mov     [rsp-8+arg_10], rbx
0x1800ec2d1  mov     [rsp-8+arg_18], rdi
0x1800ec2d6  push    rbp
0x1800ec2d7  push    r14
0x1800ec2d9  push    r15
0x1800ec2db  lea     rbp, [rsp-1C0h]
0x1800ec2e3  sub     rsp, 2C0h
0x1800ec2ea  mov     rax, cs:__security_cookie
0x1800ec2f1  xor     rax, rsp
0x1800ec2f4  mov     [rbp+1D0h+var_20], rax
0x1800ec2fb  xor     r15d, r15d
0x1800ec2fe  lea     r8, aExtensionsCont; "Extensions\\ContractId"
0x1800ec305  xor     eax, eax
0x1800ec307  mov     qword ptr [rsp+2D0h+ftLastWriteTime.dwLowDateTime], r15
0x1800ec30c  mov     [rdx], rax
0x1800ec30f  mov     r14, rdx
0x1800ec312  mov     r9, [rcx+48h]
0x1800ec316  lea     rdx, aSS_2; "%s\\%s"
0x1800ec31d  lea     rcx, [rbp+1D0h+lpSubKey]
0x1800ec321  mov     [rbp+1D0h+lpSubKey], r15
0x1800ec325  mov     [rbp+1D0h+var_248], r15
0x1800ec329  mov     [rbp+1D0h+var_240], r15
0x1800ec32d  call    ?ConcatFormat@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@QEAAJPEBGZZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::ConcatFormat(ushort const *,...)
0x1800ec332  mov     ebx, eax
0x1800ec334  test    eax, eax
0x1800ec336  js      loc_1800EC4A4
0x1800ec33c  mov     rdx, [rbp+1D0h+lpSubKey]; lpSubKey
0x1800ec340  lea     rax, [rsp+2D0h+hKey]
0x1800ec345  mov     r9d, 20019h; samDesired
0x1800ec34b  mov     [rsp+2D0h+phkResult], rax; phkResult
0x1800ec350  xor     r8d, r8d; ulOptions
0x1800ec353  mov     [rsp+2D0h+hKey], r15
0x1800ec358  mov     rcx, 0FFFFFFFF80000000h; hKey
0x1800ec35f  call    cs:__imp_RegOpenKeyExW
0x1800ec365  mov     ebx, eax
0x1800ec367  test    eax, eax
0x1800ec369  jle     short loc_1800EC374
0x1800ec36b  movzx   ebx, ax
0x1800ec36e  or      ebx, 80070000h
0x1800ec374  test    ebx, ebx
0x1800ec376  js      loc_1800EC48E
0x1800ec37c  mov     rcx, [rsp+2D0h+hKey]; hKey
0x1800ec381  lea     rax, [rsp+2D0h+ftLastWriteTime]
0x1800ec386  mov     [rsp+2D0h+lpftLastWriteTime], rax; lpftLastWriteTime
0x1800ec38b  xor     r9d, r9d; lpReserved
0x1800ec38e  mov     [rsp+2D0h+lpcbSecurityDescriptor], r15; lpcbSecurityDescriptor
0x1800ec393  xor     r8d, r8d; lpcchClass
0x1800ec396  mov     [rsp+2D0h+lpcbMaxValueLen], r15; lpcbMaxValueLen
0x1800ec39b  xor     edx, edx; lpClass
0x1800ec39d  mov     [rsp+2D0h+lpcbMaxValueNameLen], r15; lpcbMaxValueNameLen
0x1800ec3a2  mov     [rsp+2D0h+lpcValues], r15; lpcValues
0x1800ec3a7  mov     [rsp+2D0h+lpcbMaxClassLen], r15; lpcbMaxClassLen
0x1800ec3ac  mov     [rsp+2D0h+lpcbMaxSubKeyLen], r15; lpcbMaxSubKeyLen
0x1800ec3b1  mov     [rsp+2D0h+phkResult], r15; lpcSubKeys
0x1800ec3b6  call    cs:__imp_RegQueryInfoKeyW
0x1800ec3bc  mov     edi, eax
0x1800ec3be  test    eax, eax
0x1800ec3c0  jle     short loc_1800EC3CB
0x1800ec3c2  movzx   edi, ax
0x1800ec3c5  or      edi, 80070000h
0x1800ec3cb  mov     ebx, r15d
0x1800ec3ce  jmp     short loc_1800EC43F
0x1800ec3d0  mov     rcx, [rsp+2D0h+hKey]; hKey
0x1800ec3d5  lea     rax, [rsp+2D0h+FileTime1]
0x1800ec3da  mov     [rsp+2D0h+lpcValues], rax; lpftLastWriteTime
0x1800ec3df  lea     r9, [rsp+2D0h+cchName]; lpcchName
0x1800ec3e4  mov     [rsp+2D0h+lpcbMaxClassLen], r15; lpcchClass
0x1800ec3e9  lea     r8, [rbp+1D0h+Name]; lpName
0x1800ec3ed  mov     [rsp+2D0h+lpcbMaxSubKeyLen], r15; lpClass
0x1800ec3f2  mov     edx, ebx; dwIndex
0x1800ec3f4  mov     [rsp+2D0h+phkResult], r15; lpReserved
0x1800ec3f9  mov     [rsp+2D0h+cchName], 104h
0x1800ec401  mov     qword ptr [rsp+2D0h+FileTime1.dwLowDateTime], r15
0x1800ec406  call    cs:__imp_RegEnumKeyExW
0x1800ec40c  mov     edi, eax
0x1800ec40e  test    eax, eax
0x1800ec410  jle     short loc_1800EC41B
0x1800ec412  movzx   edi, ax
0x1800ec415  or      edi, 80070000h
0x1800ec41b  test    edi, edi
0x1800ec41d  js      short loc_1800EC43D
0x1800ec41f  lea     rdx, [rsp+2D0h+ftLastWriteTime]; lpFileTime2
0x1800ec424  lea     rcx, [rsp+2D0h+FileTime1]; lpFileTime1
0x1800ec429  call    cs:__imp_CompareFileTime
0x1800ec42f  test    eax, eax
0x1800ec431  jle     short loc_1800EC43D
0x1800ec433  mov     rax, qword ptr [rsp+2D0h+FileTime1.dwLowDateTime]
0x1800ec438  mov     qword ptr [rsp+2D0h+ftLastWriteTime.dwLowDateTime], rax
0x1800ec43d  inc     ebx
0x1800ec43f  test    edi, edi
0x1800ec441  jns     short loc_1800EC3D0
0x1800ec443  cmp     edi, 80070103h
0x1800ec449  mov     ebx, r15d
0x1800ec44c  cmovnz  ebx, edi
0x1800ec44f  test    ebx, ebx
0x1800ec451  js      short loc_1800EC481
0x1800ec453  lea     rcx, [rsp+2D0h+FileTime1]; lpSystemTimeAsFileTime
0x1800ec458  mov     qword ptr [rsp+2D0h+FileTime1.dwLowDateTime], r15
0x1800ec45d  call    cs:__imp_GetSystemTimeAsFileTime
0x1800ec463  lea     rdx, [rsp+2D0h+ftLastWriteTime]; lpFileTime2
0x1800ec468  lea     rcx, [rsp+2D0h+FileTime1]; lpFileTime1
0x1800ec46d  call    cs:__imp_CompareFileTime
0x1800ec473  test    eax, eax
0x1800ec475  jns     short loc_1800EC481
0x1800ec477  mov     rax, qword ptr [rsp+2D0h+FileTime1.dwLowDateTime]
0x1800ec47c  mov     qword ptr [rsp+2D0h+ftLastWriteTime.dwLowDateTime], rax
0x1800ec481  mov     rcx, [rsp+2D0h+hKey]; hKey
0x1800ec486  call    cs:__imp_RegCloseKey
0x1800ec48c  jmp     short loc_1800EC4A4
0x1800ec48e  cmp     ebx, 80070002h
0x1800ec494  jnz     short loc_1800EC4A4
0x1800ec496  lea     rcx, [rsp+2D0h+ftLastWriteTime]; lpSystemTimeAsFileTime
0x1800ec49b  call    cs:__imp_GetSystemTimeAsFileTime
0x1800ec4a1  mov     ebx, r15d
0x1800ec4a4  cmp     [rbp+1D0h+lpSubKey], r15
0x1800ec4a8  jz      short loc_1800EC4B4
0x1800ec4aa  mov     rcx, [rbp+1D0h+lpSubKey]; pv
0x1800ec4ae  call    cs:__imp_CoTaskMemFree
0x1800ec4b4  test    ebx, ebx
0x1800ec4b6  js      short loc_1800EC4C0
0x1800ec4b8  mov     rax, qword ptr [rsp+2D0h+ftLastWriteTime.dwLowDateTime]
0x1800ec4bd  mov     [r14], rax
0x1800ec4c0  mov     eax, ebx
0x1800ec4c2  mov     rcx, [rbp+1D0h+var_20]
0x1800ec4c9  xor     rcx, rsp; StackCookie
0x1800ec4cc  call    __security_check_cookie
0x1800ec4d1  lea     r11, [rsp+2D0h+var_10]
0x1800ec4d9  mov     rbx, [r11+30h]
0x1800ec4dd  mov     rdi, [r11+38h]
0x1800ec4e1  mov     rsp, r11
0x1800ec4e4  pop     r15
0x1800ec4e6  pop     r14
0x1800ec4e8  pop     rbp
0x1800ec4e9  retn
```
