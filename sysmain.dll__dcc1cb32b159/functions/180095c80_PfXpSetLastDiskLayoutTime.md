# PfXpSetLastDiskLayoutTime

- ea: `0x180095c80`
- end: `0x180095dbc`
- name: `PfXpSetLastDiskLayoutTime`
- size: `316`
- prototype: `__int64 __fastcall(FILETIME *lpFileTime)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x180018ec0`

## callees

- `0x180039f94`
- `0x180095c80`
- `0x1800b64c0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180095cd7`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180095d95`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180095cd7`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180095d95`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180095cf6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180095cf6`
- `api-ms-win-core-file-l1-1-0!FileTimeToLocalFileTime` at `0x180095cec`
- `api-ms-win-core-file-l1-1-0!FileTimeToLocalFileTime` at `0x180095cec`
- `api-ms-win-core-timezone-l1-1-0!FileTimeToSystemTime` at `0x180095d09`
- `api-ms-win-core-timezone-l1-1-0!FileTimeToSystemTime` at `0x180095d09`

## pseudocode

```c
DWORD __fastcall PfXpSetLastDiskLayoutTime(FILETIME *lpFileTime)
{
  DWORD result; // eax
  __int64 v3; // rax
  BYTE *lpData; // [rsp+20h] [rbp-79h]
  __int64 cbData; // [rsp+28h] [rbp-71h]
  int wHour; // [rsp+30h] [rbp-69h]
  int wMinute; // [rsp+38h] [rbp-61h]
  int wSecond; // [rsp+40h] [rbp-59h]
  struct _FILETIME LocalFileTime; // [rsp+50h] [rbp-49h] BYREF
  struct _SYSTEMTIME SystemTime; // [rsp+58h] [rbp-41h] BYREF
  wchar_t pszDest[56]; // [rsp+70h] [rbp-29h] BYREF

  LocalFileTime = 0;
  SystemTime = 0;
  result = RegSetValueExW(hKey, L"LastDiskLayoutTime", 0, 3u, (const BYTE *)lpFileTime, 8u);
  if ( !result )
  {
    if ( FileTimeToLocalFileTime(lpFileTime, &LocalFileTime) && FileTimeToSystemTime(&LocalFileTime, &SystemTime) )
    {
      wSecond = SystemTime.wSecond;
      wMinute = SystemTime.wMinute;
      wHour = SystemTime.wHour;
      LODWORD(cbData) = SystemTime.wDay;
      LODWORD(lpData) = SystemTime.wMonth;
      StringCbPrintfW(
        pszDest,
        0x64u,
        L"%04d/%02d/%02d-%02d:%02d:%02d",
        SystemTime.wYear,
        lpData,
        cbData,
        wHour,
        wMinute,
        wSecond);
      v3 = -1;
      do
        ++v3;
      while ( pszDest[v3] );
      return RegSetValueExW(hKey, L"LastDiskLayoutTimeString", 0, 1u, (const BYTE *)pszDest, 2 * v3 + 2);
    }
    else
    {
      return GetLastError();
    }
  }
  return result;
}

```

## disassembly

```asm
0x180095c80  mov     [rsp-8+arg_8], rbx
0x180095c85  mov     [rsp-8+arg_10], rdi
0x180095c8a  push    rbp
0x180095c8b  lea     rbp, [rsp-57h]
0x180095c90  sub     rsp, 0F0h
0x180095c97  mov     rax, cs:__security_cookie
0x180095c9e  xor     rax, rsp
0x180095ca1  mov     [rbp+57h+var_10], rax
0x180095ca5  xor     edi, edi
0x180095ca7  mov     dword ptr [rsp+0F0h+cbData], 8; cbData
0x180095caf  mov     rbx, rcx
0x180095cb2  mov     [rsp+0F0h+lpData], rcx; lpData
0x180095cb7  mov     rcx, cs:hKey; hKey
0x180095cbe  lea     rdx, aLastdisklayout; "LastDiskLayoutTime"
0x180095cc5  xorps   xmm0, xmm0
0x180095cc8  mov     qword ptr [rbp+57h+LocalFileTime.dwLowDateTime], rdi
0x180095ccc  lea     r9d, [rdi+3]; dwType
0x180095cd0  xor     r8d, r8d; Reserved
0x180095cd3  movups  xmmword ptr [rbp+57h+SystemTime.wYear], xmm0
0x180095cd7  call    cs:__imp_RegSetValueExW
0x180095cdd  test    eax, eax
0x180095cdf  jnz     loc_180095D9B
0x180095ce5  lea     rdx, [rbp+57h+LocalFileTime]; lpLocalFileTime
0x180095ce9  mov     rcx, rbx; lpFileTime
0x180095cec  call    cs:__imp_FileTimeToLocalFileTime
0x180095cf2  test    eax, eax
0x180095cf4  jnz     short loc_180095D01
0x180095cf6  call    cs:__imp_GetLastError
0x180095cfc  jmp     loc_180095D9B
0x180095d01  lea     rdx, [rbp+57h+SystemTime]; lpSystemTime
0x180095d05  lea     rcx, [rbp+57h+LocalFileTime]; lpFileTime
0x180095d09  call    cs:__imp_FileTimeToSystemTime
0x180095d0f  test    eax, eax
0x180095d11  jz      short loc_180095CF6
0x180095d13  movzx   ecx, [rbp+57h+SystemTime.wMinute]
0x180095d17  movzx   edx, [rbp+57h+SystemTime.wHour]
0x180095d1b  movzx   r8d, [rbp+57h+SystemTime.wDay]
0x180095d20  movzx   eax, [rbp+57h+SystemTime.wSecond]
0x180095d24  movzx   r10d, [rbp+57h+SystemTime.wMonth]
0x180095d29  movzx   r9d, [rbp+57h+SystemTime.wYear]
0x180095d2e  mov     [rsp+0F0h+var_B0], eax
0x180095d32  mov     [rsp+0F0h+var_B8], ecx
0x180095d36  lea     rcx, [rbp+57h+pszDest]; pszDest
0x180095d3a  mov     [rsp+0F0h+var_C0], edx
0x180095d3e  mov     edx, 64h ; 'd'; cbDest
0x180095d43  mov     dword ptr [rsp+0F0h+cbData], r8d
0x180095d48  lea     r8, a04d02d02d02d02; "%04d/%02d/%02d-%02d:%02d:%02d"
0x180095d4f  mov     dword ptr [rsp+0F0h+lpData], r10d
0x180095d54  call    StringCbPrintfW
0x180095d59  lea     rcx, [rbp+57h+pszDest]
0x180095d5d  or      rax, 0FFFFFFFFFFFFFFFFh
0x180095d61  inc     rax
0x180095d64  cmp     [rcx+rax*2], di
0x180095d68  jnz     short loc_180095D61
0x180095d6a  mov     rcx, cs:hKey; hKey
0x180095d71  lea     eax, ds:2[rax*2]
0x180095d78  mov     dword ptr [rsp+0F0h+cbData], eax; cbData
0x180095d7c  lea     rdx, aLastdisklayout_0; "LastDiskLayoutTimeString"
0x180095d83  lea     rax, [rbp+57h+pszDest]
0x180095d87  mov     r9d, 1; dwType
0x180095d8d  xor     r8d, r8d; Reserved
0x180095d90  mov     [rsp+0F0h+lpData], rax; lpData
0x180095d95  call    cs:__imp_RegSetValueExW
0x180095d9b  mov     rcx, [rbp+57h+var_10]
0x180095d9f  xor     rcx, rsp; StackCookie
0x180095da2  call    __security_check_cookie
0x180095da7  lea     r11, [rsp+0F0h+var_s0]
0x180095daf  mov     rbx, [r11+18h]
0x180095db3  mov     rdi, [r11+20h]
0x180095db7  mov     rsp, r11
0x180095dba  pop     rbp
0x180095dbb  retn
```
