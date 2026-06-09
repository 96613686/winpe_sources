# _GetRegKeyLastWriteTime(HKEY__ *,ushort const *,ushort const *,REG_LAST_WRITE_OPTION,_FILETIME *)

- ea: `0x1800adfac`
- end: `0x1800ae1d8`
- name: `?_GetRegKeyLastWriteTime@@YAJPEAUHKEY__@@PEBG1W4REG_LAST_WRITE_OPTION@@PEAU_FILETIME@@@Z`
- size: `556`
- prototype: ``
- caller_count: `3`
- callee_count: `3`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180058ba8`
- `0x1803678a0`
- `0x1803683e4`

## callees

- `0x1800adfac`
- `0x1800ec758`
- `0x18013d330`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1800ae159`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1800ae195`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1800ae159`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1800ae195`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x1800ae109`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x1800ae109`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800ae054`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800ae054`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800ae17e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800ae17e`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800ae067`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800ae067`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x1800ae0bc`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x1800ae0bc`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x1800ae127`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x1800ae167`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x1800ae127`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x1800ae167`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800ae1aa`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800ae1aa`

## pseudocode

```c
__int64 __fastcall _GetRegKeyLastWriteTime(HKEY a1, __int64 a2, __int64 a3, int a4, PFILETIME lpFileTime2)
{
  signed int v7; // ebx
  LSTATUS v8; // eax
  LSTATUS InfoKeyW; // eax
  signed int v10; // edi
  DWORD v11; // ebx
  LSTATUS v12; // eax
  struct _FILETIME ftLastWriteTime; // [rsp+60h] [rbp-A0h] BYREF
  HKEY hKey; // [rsp+68h] [rbp-98h] BYREF
  DWORD cchName; // [rsp+70h] [rbp-90h] BYREF
  LPCWSTR lpSubKey[3]; // [rsp+78h] [rbp-88h] BYREF
  WCHAR Name[264]; // [rsp+90h] [rbp-70h] BYREF

  memset(lpSubKey, 0, sizeof(lpSubKey));
  *lpFileTime2 = 0;
  v7 = Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::ConcatFormat(
         lpSubKey,
         L"%s\\%s",
         a2,
         a3);
  if ( v7 >= 0 )
  {
    hKey = 0;
    if ( a4 == 1 )
      v8 = RegCreateKeyExW(a1, lpSubKey[0], 0, 0, 0, 0xF003Fu, 0, &hKey, 0);
    else
      v8 = RegOpenKeyExW(a1, lpSubKey[0], 0, 0x20019u, &hKey);
    v7 = v8;
    if ( v8 > 0 )
      v7 = (unsigned __int16)v8 | 0x80070000;
    if ( v7 < 0 )
    {
      if ( v7 == -2147024894 && !a4 )
      {
        GetSystemTimeAsFileTime(lpFileTime2);
        v7 = 0;
      }
    }
    else
    {
      InfoKeyW = RegQueryInfoKeyW(hKey, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, lpFileTime2);
      v10 = InfoKeyW;
      if ( InfoKeyW > 0 )
        v10 = (unsigned __int16)InfoKeyW | 0x80070000;
      v11 = 0;
      while ( v10 >= 0 )
      {
        cchName = 260;
        ftLastWriteTime = 0;
        v12 = RegEnumKeyExW(hKey, v11, Name, &cchName, 0, 0, 0, &ftLastWriteTime);
        v10 = v12;
        if ( v12 > 0 )
          v10 = (unsigned __int16)v12 | 0x80070000;
        if ( v10 >= 0 && CompareFileTime(&ftLastWriteTime, lpFileTime2) > 0 )
          *lpFileTime2 = ftLastWriteTime;
        ++v11;
      }
      v7 = 0;
      if ( v10 != -2147024637 )
        v7 = v10;
      if ( v7 >= 0 )
      {
        ftLastWriteTime = 0;
        GetSystemTimeAsFileTime(&ftLastWriteTime);
        if ( CompareFileTime(&ftLastWriteTime, lpFileTime2) < 0 )
          *lpFileTime2 = ftLastWriteTime;
      }
      RegCloseKey(hKey);
    }
  }
  if ( lpSubKey[0] )
    CoTaskMemFree((LPVOID)lpSubKey[0]);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x1800adfac  mov     [rsp-8+arg_18], rbx
0x1800adfb1  push    rbp
0x1800adfb2  push    rsi
0x1800adfb3  push    rdi
0x1800adfb4  push    r12
0x1800adfb6  push    r14
0x1800adfb8  lea     rbp, [rsp-1B0h]
0x1800adfc0  sub     rsp, 2B0h
0x1800adfc7  mov     rax, cs:__security_cookie
0x1800adfce  xor     rax, rsp
0x1800adfd1  mov     [rbp+1D0h+var_30], rax
0x1800adfd8  mov     rsi, [rbp+1D0h+lpFileTime2]
0x1800adfdf  xor     r12d, r12d
0x1800adfe2  mov     edi, r9d
0x1800adfe5  mov     [rsp+2D0h+lpSubKey], r12
0x1800adfea  mov     r9, r8
0x1800adfed  mov     [rbp+1D0h+var_250], r12
0x1800adff1  mov     r14, rcx
0x1800adff4  mov     [rbp+1D0h+var_248], r12
0x1800adff8  xor     eax, eax
0x1800adffa  lea     rcx, [rsp+2D0h+lpSubKey]
0x1800adfff  mov     r8, rdx
0x1800ae002  mov     [rsi], rax
0x1800ae005  lea     rdx, aSS_2; "%s\\%s"
0x1800ae00c  call    ?ConcatFormat@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@QEAAJPEBGZZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::ConcatFormat(ushort const *,...)
0x1800ae011  mov     ebx, eax
0x1800ae013  test    eax, eax
0x1800ae015  js      loc_1800AE19E
0x1800ae01b  mov     rdx, [rsp+2D0h+lpSubKey]; lpSubKey
0x1800ae020  lea     rax, [rsp+2D0h+hKey]
0x1800ae025  xor     r8d, r8d; ulOptions
0x1800ae028  mov     [rsp+2D0h+hKey], r12
0x1800ae02d  mov     rcx, r14; hKey
0x1800ae030  cmp     edi, 1
0x1800ae033  jnz     short loc_1800AE05C
0x1800ae035  mov     [rsp+2D0h+lpdwDisposition], r12; lpdwDisposition
0x1800ae03a  xor     r9d, r9d; lpClass
0x1800ae03d  mov     [rsp+2D0h+phkResult], rax; phkResult
0x1800ae042  mov     [rsp+2D0h+lpSecurityAttributes], r12; lpSecurityAttributes
0x1800ae047  mov     [rsp+2D0h+samDesired], 0F003Fh; samDesired
0x1800ae04f  mov     [rsp+2D0h+dwOptions], r12d; dwOptions
0x1800ae054  call    cs:__imp_RegCreateKeyExW
0x1800ae05a  jmp     short loc_1800AE06D
0x1800ae05c  mov     r9d, 20019h; samDesired
0x1800ae062  mov     qword ptr [rsp+2D0h+dwOptions], rax; phkResult
0x1800ae067  call    cs:__imp_RegOpenKeyExW
0x1800ae06d  mov     r14d, 80070000h
0x1800ae073  mov     ebx, eax
0x1800ae075  test    eax, eax
0x1800ae077  jle     short loc_1800AE07F
0x1800ae079  movzx   ebx, ax
0x1800ae07c  or      ebx, r14d
0x1800ae07f  test    ebx, ebx
0x1800ae081  js      loc_1800AE186
0x1800ae087  mov     rcx, [rsp+2D0h+hKey]; hKey
0x1800ae08c  xor     r9d, r9d; lpReserved
0x1800ae08f  mov     [rsp+2D0h+lpftLastWriteTime], rsi; lpftLastWriteTime
0x1800ae094  xor     r8d, r8d; lpcchClass
0x1800ae097  mov     [rsp+2D0h+lpcbSecurityDescriptor], r12; lpcbSecurityDescriptor
0x1800ae09c  xor     edx, edx; lpClass
0x1800ae09e  mov     [rsp+2D0h+lpcbMaxValueLen], r12; lpcbMaxValueLen
0x1800ae0a3  mov     [rsp+2D0h+lpdwDisposition], r12; lpcbMaxValueNameLen
0x1800ae0a8  mov     [rsp+2D0h+phkResult], r12; lpcValues
0x1800ae0ad  mov     [rsp+2D0h+lpSecurityAttributes], r12; lpcbMaxClassLen
0x1800ae0b2  mov     qword ptr [rsp+2D0h+samDesired], r12; lpcbMaxSubKeyLen
0x1800ae0b7  mov     qword ptr [rsp+2D0h+dwOptions], r12; lpcSubKeys
0x1800ae0bc  call    cs:__imp_RegQueryInfoKeyW
0x1800ae0c2  mov     edi, eax
0x1800ae0c4  test    eax, eax
0x1800ae0c6  jle     short loc_1800AE0CE
0x1800ae0c8  movzx   edi, ax
0x1800ae0cb  or      edi, r14d
0x1800ae0ce  mov     ebx, r12d
0x1800ae0d1  jmp     short loc_1800AE13B
0x1800ae0d3  mov     rcx, [rsp+2D0h+hKey]; hKey
0x1800ae0d8  lea     rax, [rsp+2D0h+ftLastWriteTime]
0x1800ae0dd  mov     [rsp+2D0h+phkResult], rax; lpftLastWriteTime
0x1800ae0e2  lea     r9, [rsp+2D0h+cchName]; lpcchName
0x1800ae0e7  mov     [rsp+2D0h+lpSecurityAttributes], r12; lpcchClass
0x1800ae0ec  lea     r8, [rbp+1D0h+Name]; lpName
0x1800ae0f0  mov     qword ptr [rsp+2D0h+samDesired], r12; lpClass
0x1800ae0f5  mov     edx, ebx; dwIndex
0x1800ae0f7  mov     qword ptr [rsp+2D0h+dwOptions], r12; lpReserved
0x1800ae0fc  mov     [rsp+2D0h+cchName], 104h
0x1800ae104  mov     qword ptr [rsp+2D0h+ftLastWriteTime.dwLowDateTime], r12
0x1800ae109  call    cs:__imp_RegEnumKeyExW
0x1800ae10f  mov     edi, eax
0x1800ae111  test    eax, eax
0x1800ae113  jle     short loc_1800AE11B
0x1800ae115  movzx   edi, ax
0x1800ae118  or      edi, r14d
0x1800ae11b  test    edi, edi
0x1800ae11d  js      short loc_1800AE139
0x1800ae11f  mov     rdx, rsi; lpFileTime2
0x1800ae122  lea     rcx, [rsp+2D0h+ftLastWriteTime]; lpFileTime1
0x1800ae127  call    cs:__imp_CompareFileTime
0x1800ae12d  test    eax, eax
0x1800ae12f  jle     short loc_1800AE139
0x1800ae131  mov     rax, qword ptr [rsp+2D0h+ftLastWriteTime.dwLowDateTime]
0x1800ae136  mov     [rsi], rax
0x1800ae139  inc     ebx
0x1800ae13b  test    edi, edi
0x1800ae13d  jns     short loc_1800AE0D3
0x1800ae13f  cmp     edi, 80070103h
0x1800ae145  mov     ebx, r12d
0x1800ae148  cmovnz  ebx, edi
0x1800ae14b  test    ebx, ebx
0x1800ae14d  js      short loc_1800AE179
0x1800ae14f  lea     rcx, [rsp+2D0h+ftLastWriteTime]; lpSystemTimeAsFileTime
0x1800ae154  mov     qword ptr [rsp+2D0h+ftLastWriteTime.dwLowDateTime], r12
0x1800ae159  call    cs:__imp_GetSystemTimeAsFileTime
0x1800ae15f  mov     rdx, rsi; lpFileTime2
0x1800ae162  lea     rcx, [rsp+2D0h+ftLastWriteTime]; lpFileTime1
0x1800ae167  call    cs:__imp_CompareFileTime
0x1800ae16d  test    eax, eax
0x1800ae16f  jns     short loc_1800AE179
0x1800ae171  mov     rax, qword ptr [rsp+2D0h+ftLastWriteTime.dwLowDateTime]
0x1800ae176  mov     [rsi], rax
0x1800ae179  mov     rcx, [rsp+2D0h+hKey]; hKey
0x1800ae17e  call    cs:__imp_RegCloseKey
0x1800ae184  jmp     short loc_1800AE19E
0x1800ae186  cmp     ebx, 80070002h
0x1800ae18c  jnz     short loc_1800AE19E
0x1800ae18e  test    edi, edi
0x1800ae190  jnz     short loc_1800AE19E
0x1800ae192  mov     rcx, rsi; lpSystemTimeAsFileTime
0x1800ae195  call    cs:__imp_GetSystemTimeAsFileTime
0x1800ae19b  mov     ebx, r12d
0x1800ae19e  cmp     [rsp+2D0h+lpSubKey], r12
0x1800ae1a3  jz      short loc_1800AE1B0
0x1800ae1a5  mov     rcx, [rsp+2D0h+lpSubKey]; pv
0x1800ae1aa  call    cs:__imp_CoTaskMemFree
0x1800ae1b0  mov     eax, ebx
0x1800ae1b2  mov     rcx, [rbp+1D0h+var_30]
0x1800ae1b9  xor     rcx, rsp; StackCookie
0x1800ae1bc  call    __security_check_cookie
0x1800ae1c1  mov     rbx, [rsp+2D0h+arg_18]
0x1800ae1c9  add     rsp, 2B0h
0x1800ae1d0  pop     r14
0x1800ae1d2  pop     r12
0x1800ae1d4  pop     rdi
0x1800ae1d5  pop     rsi
0x1800ae1d6  pop     rbp
0x1800ae1d7  retn
```
