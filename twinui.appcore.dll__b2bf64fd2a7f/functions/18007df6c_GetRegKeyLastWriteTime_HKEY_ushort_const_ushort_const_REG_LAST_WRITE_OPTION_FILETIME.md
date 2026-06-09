# _GetRegKeyLastWriteTime(HKEY__ *,ushort const *,ushort const *,REG_LAST_WRITE_OPTION,_FILETIME *)

- ea: `0x18007df6c`
- end: `0x18007e190`
- name: `?_GetRegKeyLastWriteTime@@YAJPEAUHKEY__@@PEBG1W4REG_LAST_WRITE_OPTION@@PEAU_FILETIME@@@Z`
- size: `548`
- prototype: ``
- caller_count: `4`
- callee_count: `4`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18007b720`
- `0x18007dcd0`
- `0x18007e23c`
- `0x18007f500`

## callees

- `0x180018180`
- `0x18002b1b0`
- `0x180078998`
- `0x18007df6c`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18007e119`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18007e155`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18007e119`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18007e155`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18007e13e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18007e13e`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18007e014`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18007e014`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x18007e0c9`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x18007e0c9`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18007e027`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18007e027`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x18007e07c`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x18007e07c`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x18007e0e7`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x18007e127`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x18007e0e7`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x18007e127`

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
  Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(lpSubKey);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x18007df6c  mov     [rsp-8+arg_18], rbx
0x18007df71  push    rbp
0x18007df72  push    rsi
0x18007df73  push    rdi
0x18007df74  push    r14
0x18007df76  push    r15
0x18007df78  lea     rbp, [rsp-1B0h]
0x18007df80  sub     rsp, 2B0h
0x18007df87  mov     rax, cs:__security_cookie
0x18007df8e  xor     rax, rsp
0x18007df91  mov     [rbp+1D0h+var_30], rax
0x18007df98  mov     rsi, [rbp+1D0h+lpFileTime2]
0x18007df9f  xor     r15d, r15d
0x18007dfa2  mov     edi, r9d
0x18007dfa5  mov     [rsp+2D0h+lpSubKey], r15
0x18007dfaa  mov     r9, r8
0x18007dfad  mov     [rbp+1D0h+var_250], r15
0x18007dfb1  mov     r14, rcx
0x18007dfb4  mov     [rbp+1D0h+var_248], r15
0x18007dfb8  xor     eax, eax
0x18007dfba  lea     rcx, [rsp+2D0h+lpSubKey]
0x18007dfbf  mov     r8, rdx
0x18007dfc2  mov     [rsi], rax
0x18007dfc5  lea     rdx, aSS; "%s\\%s"
0x18007dfcc  call    ?ConcatFormat@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@QEAAJPEBGZZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::ConcatFormat(ushort const *,...)
0x18007dfd1  mov     ebx, eax
0x18007dfd3  test    eax, eax
0x18007dfd5  js      loc_18007E15E
0x18007dfdb  mov     rdx, [rsp+2D0h+lpSubKey]; lpSubKey
0x18007dfe0  lea     rax, [rsp+2D0h+hKey]
0x18007dfe5  xor     r8d, r8d; ulOptions
0x18007dfe8  mov     [rsp+2D0h+hKey], r15
0x18007dfed  mov     rcx, r14; hKey
0x18007dff0  cmp     edi, 1
0x18007dff3  jnz     short loc_18007E01C
0x18007dff5  mov     [rsp+2D0h+lpdwDisposition], r15; lpdwDisposition
0x18007dffa  xor     r9d, r9d; lpClass
0x18007dffd  mov     [rsp+2D0h+phkResult], rax; phkResult
0x18007e002  mov     [rsp+2D0h+lpSecurityAttributes], r15; lpSecurityAttributes
0x18007e007  mov     [rsp+2D0h+samDesired], 0F003Fh; samDesired
0x18007e00f  mov     [rsp+2D0h+dwOptions], r15d; dwOptions
0x18007e014  call    cs:__imp_RegCreateKeyExW
0x18007e01a  jmp     short loc_18007E02D
0x18007e01c  mov     r9d, 20019h; samDesired
0x18007e022  mov     qword ptr [rsp+2D0h+dwOptions], rax; phkResult
0x18007e027  call    cs:__imp_RegOpenKeyExW
0x18007e02d  mov     r14d, 80070000h
0x18007e033  mov     ebx, eax
0x18007e035  test    eax, eax
0x18007e037  jle     short loc_18007E03F
0x18007e039  movzx   ebx, ax
0x18007e03c  or      ebx, r14d
0x18007e03f  test    ebx, ebx
0x18007e041  js      loc_18007E146
0x18007e047  mov     rcx, [rsp+2D0h+hKey]; hKey
0x18007e04c  xor     r9d, r9d; lpReserved
0x18007e04f  mov     [rsp+2D0h+lpftLastWriteTime], rsi; lpftLastWriteTime
0x18007e054  xor     r8d, r8d; lpcchClass
0x18007e057  mov     [rsp+2D0h+lpcbSecurityDescriptor], r15; lpcbSecurityDescriptor
0x18007e05c  xor     edx, edx; lpClass
0x18007e05e  mov     [rsp+2D0h+lpcbMaxValueLen], r15; lpcbMaxValueLen
0x18007e063  mov     [rsp+2D0h+lpdwDisposition], r15; lpcbMaxValueNameLen
0x18007e068  mov     [rsp+2D0h+phkResult], r15; lpcValues
0x18007e06d  mov     [rsp+2D0h+lpSecurityAttributes], r15; lpcbMaxClassLen
0x18007e072  mov     qword ptr [rsp+2D0h+samDesired], r15; lpcbMaxSubKeyLen
0x18007e077  mov     qword ptr [rsp+2D0h+dwOptions], r15; lpcSubKeys
0x18007e07c  call    cs:__imp_RegQueryInfoKeyW
0x18007e082  mov     edi, eax
0x18007e084  test    eax, eax
0x18007e086  jle     short loc_18007E08E
0x18007e088  movzx   edi, ax
0x18007e08b  or      edi, r14d
0x18007e08e  mov     ebx, r15d
0x18007e091  jmp     short loc_18007E0FB
0x18007e093  mov     rcx, [rsp+2D0h+hKey]; hKey
0x18007e098  lea     rax, [rsp+2D0h+ftLastWriteTime]
0x18007e09d  mov     [rsp+2D0h+phkResult], rax; lpftLastWriteTime
0x18007e0a2  lea     r9, [rsp+2D0h+cchName]; lpcchName
0x18007e0a7  mov     [rsp+2D0h+lpSecurityAttributes], r15; lpcchClass
0x18007e0ac  lea     r8, [rbp+1D0h+Name]; lpName
0x18007e0b0  mov     qword ptr [rsp+2D0h+samDesired], r15; lpClass
0x18007e0b5  mov     edx, ebx; dwIndex
0x18007e0b7  mov     qword ptr [rsp+2D0h+dwOptions], r15; lpReserved
0x18007e0bc  mov     [rsp+2D0h+cchName], 104h
0x18007e0c4  mov     qword ptr [rsp+2D0h+ftLastWriteTime.dwLowDateTime], r15
0x18007e0c9  call    cs:__imp_RegEnumKeyExW
0x18007e0cf  mov     edi, eax
0x18007e0d1  test    eax, eax
0x18007e0d3  jle     short loc_18007E0DB
0x18007e0d5  movzx   edi, ax
0x18007e0d8  or      edi, r14d
0x18007e0db  test    edi, edi
0x18007e0dd  js      short loc_18007E0F9
0x18007e0df  mov     rdx, rsi; lpFileTime2
0x18007e0e2  lea     rcx, [rsp+2D0h+ftLastWriteTime]; lpFileTime1
0x18007e0e7  call    cs:__imp_CompareFileTime
0x18007e0ed  test    eax, eax
0x18007e0ef  jle     short loc_18007E0F9
0x18007e0f1  mov     rax, qword ptr [rsp+2D0h+ftLastWriteTime.dwLowDateTime]
0x18007e0f6  mov     [rsi], rax
0x18007e0f9  inc     ebx
0x18007e0fb  test    edi, edi
0x18007e0fd  jns     short loc_18007E093
0x18007e0ff  cmp     edi, 80070103h
0x18007e105  mov     ebx, r15d
0x18007e108  cmovnz  ebx, edi
0x18007e10b  test    ebx, ebx
0x18007e10d  js      short loc_18007E139
0x18007e10f  lea     rcx, [rsp+2D0h+ftLastWriteTime]; lpSystemTimeAsFileTime
0x18007e114  mov     qword ptr [rsp+2D0h+ftLastWriteTime.dwLowDateTime], r15
0x18007e119  call    cs:__imp_GetSystemTimeAsFileTime
0x18007e11f  mov     rdx, rsi; lpFileTime2
0x18007e122  lea     rcx, [rsp+2D0h+ftLastWriteTime]; lpFileTime1
0x18007e127  call    cs:__imp_CompareFileTime
0x18007e12d  test    eax, eax
0x18007e12f  jns     short loc_18007E139
0x18007e131  mov     rax, qword ptr [rsp+2D0h+ftLastWriteTime.dwLowDateTime]
0x18007e136  mov     [rsi], rax
0x18007e139  mov     rcx, [rsp+2D0h+hKey]; hKey
0x18007e13e  call    cs:__imp_RegCloseKey
0x18007e144  jmp     short loc_18007E15E
0x18007e146  cmp     ebx, 80070002h
0x18007e14c  jnz     short loc_18007E15E
0x18007e14e  test    edi, edi
0x18007e150  jnz     short loc_18007E15E
0x18007e152  mov     rcx, rsi; lpSystemTimeAsFileTime
0x18007e155  call    cs:__imp_GetSystemTimeAsFileTime
0x18007e15b  mov     ebx, r15d
0x18007e15e  lea     rcx, [rsp+2D0h+lpSubKey]
0x18007e163  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x18007e168  mov     eax, ebx
0x18007e16a  mov     rcx, [rbp+1D0h+var_30]
0x18007e171  xor     rcx, rsp; StackCookie
0x18007e174  call    __security_check_cookie
0x18007e179  mov     rbx, [rsp+2D0h+arg_18]
0x18007e181  add     rsp, 2B0h
0x18007e188  pop     r15
0x18007e18a  pop     r14
0x18007e18c  pop     rdi
0x18007e18d  pop     rsi
0x18007e18e  pop     rbp
0x18007e18f  retn
```
