# FindCreateOrDeleteConnectionKey

- ea: `0x18003097c`
- end: `0x180030d66`
- name: `FindCreateOrDeleteConnectionKey`
- size: `1002`
- prototype: `__int64 __fastcall(HKEY hKey, PCWSTR SourceString)`
- caller_count: `3`
- callee_count: `3`
- tags: `registry_config, loader_planting`

## callers

- `0x1800312d8`
- `0x1800314a8`
- `0x180031538`

## callees

- `0x18000bff8`
- `0x18001fbd0`
- `0x18003097c`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__itow_s` at `0x180030cd3`
- `api-ms-win-crt-private-l1-1-0!_o__itow_s` at `0x180030cd3`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x180030b94`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x180030b94`
- `api-ms-win-crt-private-l1-1-0!_o_towupper` at `0x1800309ee`
- `api-ms-win-crt-private-l1-1-0!_o_towupper` at `0x1800309ee`
- `ntdll!RtlInitUnicodeString` at `0x180030c93`
- `ntdll!RtlInitUnicodeString` at `0x180030c93`
- `ntdll!RtlHashUnicodeString` at `0x180030cae`
- `ntdll!RtlHashUnicodeString` at `0x180030cae`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180030a3f`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180030d1a`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180030a3f`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180030d1a`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180030a7d`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180030b2f`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180030a7d`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180030b2f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180030ba9`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180030bc8`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180030ba9`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180030bc8`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180030b6f`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180030b6f`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x180030afc`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x180030afc`
- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x180030a61`
- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x180030bef`
- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x180030a61`
- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x180030bef`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180030aae`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180030aae`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180030d2d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180030d2d`

## string_xrefs

- `0x180030b4d`: `RemotePath`

## pseudocode

```c
__int64 __fastcall FindCreateOrDeleteConnectionKey(HKEY hKey, wint_t *SourceString, int a3, HKEY *a4)
{
  __int64 v4; // rsi
  __int64 v6; // rdi
  DWORD v7; // r13d
  unsigned int Key; // ebx
  wint_t v12; // ax
  HKEY v14; // rax
  HKEY *v15; // rdi
  unsigned int i; // eax
  WCHAR SubKey[2]; // [rsp+50h] [rbp-B0h] BYREF
  _BYTE dwDisposition[12]; // [rsp+54h] [rbp-ACh] BYREF
  DWORD cbData; // [rsp+60h] [rbp-A0h] BYREF
  DWORD Type; // [rsp+64h] [rbp-9Ch] BYREF
  PHKEY lpdwDisposition; // [rsp+68h] [rbp-98h] BYREF
  LPBYTE lpData; // [rsp+70h] [rbp-90h]
  struct _UNICODE_STRING DestinationString; // [rsp+78h] [rbp-88h] BYREF
  wchar_t pszDest[264]; // [rsp+90h] [rbp-70h] BYREF
  WCHAR Name[264]; // [rsp+2A0h] [rbp+1A0h] BYREF

  v4 = -1;
  lpdwDisposition = a4;
  v6 = -1;
  v7 = 0;
  do
    ++v6;
  while ( SourceString[v6] );
  if ( (unsigned int)v6 < 2 )
    return 87;
  if ( SourceString[1] == 58 )
  {
    v12 = towupper(*SourceString);
    SubKey[1] = 0;
    SubKey[0] = v12;
    if ( a3 == 1 )
    {
      *(_DWORD *)dwDisposition = 0;
      return (unsigned int)RegCreateKeyExW(hKey, SubKey, 0, 0, 0, 0x2001Fu, 0, a4, (LPDWORD)dwDisposition);
    }
    else if ( a3 == 2 )
    {
      return (unsigned int)RegDeleteKeyExW(hKey, SubKey, 0x100u, 0);
    }
    else
    {
      return (unsigned int)RegOpenKeyExW(hKey, SubKey, 0, 0x2001Fu, a4);
    }
  }
  *(_DWORD *)&dwDisposition[8] = 0;
  *(_DWORD *)SubKey = 0;
  cbData = 0;
  Type = 0;
  *(_QWORD *)dwDisposition = (unsigned int)(2 * v6 + 2);
  lpData = (LPBYTE)LocalAlloc(0, *(SIZE_T *)dwDisposition);
  if ( !lpData )
    return 8;
  while ( 1 )
  {
    wcscpy(SubKey, L"ą");
    Key = RegEnumKeyExW(hKey, v7, Name, (LPDWORD)SubKey, 0, 0, 0, 0);
    if ( Key )
    {
      v15 = lpdwDisposition;
      goto LABEL_25;
    }
    if ( !RegOpenKeyExW(hKey, Name, 0, 0x2001Fu, (PHKEY)&dwDisposition[4]) )
      break;
LABEL_20:
    ++v7;
  }
  cbData = *(_DWORD *)dwDisposition;
  Key = RegQueryValueExW(*(HKEY *)&dwDisposition[4], L"RemotePath", 0, &Type, lpData, &cbData);
  if ( Key || Type != 1 || (unsigned int)_o__wcsnicmp(lpData, SourceString, (unsigned int)(v6 + 1)) )
  {
    RegCloseKey(*(HKEY *)&dwDisposition[4]);
    goto LABEL_20;
  }
  if ( a3 == 2 )
  {
    RegCloseKey(*(HKEY *)&dwDisposition[4]);
    *(_QWORD *)&dwDisposition[4] = 0;
    Key = RegDeleteKeyExW(hKey, Name, 0x100u, 0);
  }
  v14 = *(HKEY *)&dwDisposition[4];
  v15 = lpdwDisposition;
  *(_QWORD *)&dwDisposition[4] = 0;
  *lpdwDisposition = v14;
LABEL_25:
  if ( a3 == 1 && Key == 259 )
  {
    *(_DWORD *)dwDisposition = 0;
    DestinationString = 0;
    StringCchCopyW(pszDest, 0xFAu, SourceString);
    do
      ++v4;
    while ( pszDest[v4] );
    for ( i = 0; i < (unsigned int)v4; ++i )
    {
      if ( pszDest[i] == 92 )
        pszDest[i] = 47;
    }
    pszDest[(unsigned int)v4] = 95;
    RtlInitUnicodeString(&DestinationString, SourceString);
    RtlHashUnicodeString(&DestinationString, 1u, 0, (PULONG)dwDisposition);
    _o__itow_s(*(unsigned int *)dwDisposition, &pszDest[(unsigned int)(v4 + 1)], 9);
    pszDest[260] = 0;
    LODWORD(lpdwDisposition) = 0;
    Key = RegCreateKeyExW(hKey, pszDest, 0, 0, 0, 0x2001Fu, 0, v15, (LPDWORD)&lpdwDisposition);
  }
  LocalFree(lpData);
  return Key;
}

```

## disassembly

```asm
0x18003097c  mov     [rsp-8+arg_10], rbx
0x180030981  push    rbp
0x180030982  push    rsi
0x180030983  push    rdi
0x180030984  push    r12
0x180030986  push    r13
0x180030988  push    r14
0x18003098a  push    r15
0x18003098c  lea     rbp, [rsp-3C0h]
0x180030994  sub     rsp, 4C0h
0x18003099b  mov     rax, cs:__security_cookie
0x1800309a2  xor     rax, rsp
0x1800309a5  mov     [rbp+3F0h+var_40], rax
0x1800309ac  or      rsi, 0FFFFFFFFFFFFFFFFh
0x1800309b0  mov     rbx, r9
0x1800309b3  mov     [rsp+4F0h+var_488], rbx
0x1800309b8  mov     rdi, rsi
0x1800309bb  xor     r13d, r13d
0x1800309be  mov     r15d, r8d
0x1800309c1  mov     r12, rdx
0x1800309c4  mov     r14, rcx
0x1800309c7  inc     rdi
0x1800309ca  cmp     [rdx+rdi*2], r13w
0x1800309cf  jnz     short loc_1800309C7
0x1800309d1  cmp     edi, 2
0x1800309d4  jnb     short loc_1800309E0
0x1800309d6  mov     ebx, 57h ; 'W'
0x1800309db  jmp     loc_180030D39
0x1800309e0  cmp     word ptr [rdx+2], 3Ah ; ':'
0x1800309e5  jnz     loc_180030A8B
0x1800309eb  movzx   ecx, word ptr [rdx]; C
0x1800309ee  call    cs:__imp_towupper
0x1800309f5  nop     dword ptr [rax+rax+00h]
0x1800309fa  mov     [rsp+4F0h+SubKey+2], r13w
0x180030a00  lea     rdx, [rsp+4F0h+SubKey]; lpSubKey
0x180030a05  mov     [rsp+4F0h+SubKey], ax
0x180030a0a  mov     rcx, r14; hKey
0x180030a0d  cmp     r15d, 1
0x180030a11  jnz     short loc_180030A52
0x180030a13  lea     rax, [rsp+4F0h+dwDisposition]
0x180030a18  mov     [rsp+4F0h+dwDisposition], r13d
0x180030a1d  mov     [rsp+4F0h+lpdwDisposition], rax; lpdwDisposition
0x180030a22  xor     r9d, r9d; lpClass
0x180030a25  mov     [rsp+4F0h+phkResult], rbx; phkResult
0x180030a2a  xor     r8d, r8d; Reserved
0x180030a2d  mov     [rsp+4F0h+lpSecurityAttributes], r13; lpSecurityAttributes
0x180030a32  mov     [rsp+4F0h+samDesired], 2001Fh; samDesired
0x180030a3a  mov     [rsp+4F0h+dwOptions], r13d; dwOptions
0x180030a3f  call    cs:__imp_RegCreateKeyExW
0x180030a46  nop     dword ptr [rax+rax+00h]
0x180030a4b  mov     ebx, eax
0x180030a4d  jmp     loc_180030D39
0x180030a52  cmp     r15d, 2
0x180030a56  jnz     short loc_180030A6F
0x180030a58  xor     r9d, r9d; Reserved
0x180030a5b  mov     r8d, 100h; samDesired
0x180030a61  call    cs:__imp_RegDeleteKeyExW
0x180030a68  nop     dword ptr [rax+rax+00h]
0x180030a6d  jmp     short loc_180030A4B
0x180030a6f  mov     r9d, 2001Fh; samDesired
0x180030a75  mov     qword ptr [rsp+4F0h+dwOptions], rbx; phkResult
0x180030a7a  xor     r8d, r8d; ulOptions
0x180030a7d  call    cs:__imp_RegOpenKeyExW
0x180030a84  nop     dword ptr [rax+rax+00h]
0x180030a89  jmp     short loc_180030A4B
0x180030a8b  lea     eax, ds:2[rdi*2]
0x180030a92  mov     [rsp+4F0h+hKey], r13
0x180030a97  mov     edx, eax; uBytes
0x180030a99  xor     ecx, ecx; uFlags
0x180030a9b  mov     dword ptr [rsp+4F0h+SubKey], r13d
0x180030aa0  mov     [rsp+4F0h+cbData], r13d
0x180030aa5  mov     [rsp+4F0h+Type], r13d
0x180030aaa  mov     [rsp+4F0h+dwDisposition], eax
0x180030aae  call    cs:__imp_LocalAlloc
0x180030ab5  nop     dword ptr [rax+rax+00h]
0x180030aba  mov     [rsp+4F0h+lpData], rax
0x180030abf  test    rax, rax
0x180030ac2  jnz     short loc_180030ACC
0x180030ac4  lea     ebx, [rax+8]
0x180030ac7  jmp     loc_180030D39
0x180030acc  xor     eax, eax
0x180030ace  mov     dword ptr [rsp+4F0h+SubKey], 105h
0x180030ad6  mov     [rsp+4F0h+phkResult], rax; lpftLastWriteTime
0x180030adb  lea     r9, [rsp+4F0h+SubKey]; lpcchName
0x180030ae0  mov     [rsp+4F0h+lpSecurityAttributes], rax; lpcchClass
0x180030ae5  lea     r8, [rbp+3F0h+Name]; lpName
0x180030aec  mov     qword ptr [rsp+4F0h+samDesired], rax; lpClass
0x180030af1  mov     edx, r13d; dwIndex
0x180030af4  mov     rcx, r14; hKey
0x180030af7  mov     qword ptr [rsp+4F0h+dwOptions], rax; lpReserved
0x180030afc  call    cs:__imp_RegEnumKeyExW
0x180030b03  nop     dword ptr [rax+rax+00h]
0x180030b08  mov     ebx, eax
0x180030b0a  test    eax, eax
0x180030b0c  jnz     loc_180030C16
0x180030b12  lea     rax, [rsp+4F0h+hKey]
0x180030b17  mov     r9d, 2001Fh; samDesired
0x180030b1d  xor     r8d, r8d; ulOptions
0x180030b20  mov     qword ptr [rsp+4F0h+dwOptions], rax; phkResult
0x180030b25  lea     rdx, [rbp+3F0h+Name]; lpSubKey
0x180030b2c  mov     rcx, r14; hKey
0x180030b2f  call    cs:__imp_RegOpenKeyExW
0x180030b36  nop     dword ptr [rax+rax+00h]
0x180030b3b  test    eax, eax
0x180030b3d  jnz     short loc_180030BB5
0x180030b3f  mov     eax, [rsp+4F0h+dwDisposition]
0x180030b43  lea     r9, [rsp+4F0h+Type]; lpType
0x180030b48  mov     rcx, [rsp+4F0h+hKey]; hKey
0x180030b4d  lea     rdx, aRemotepath; "RemotePath"
0x180030b54  mov     [rsp+4F0h+cbData], eax
0x180030b58  xor     r8d, r8d; lpReserved
0x180030b5b  lea     rax, [rsp+4F0h+cbData]
0x180030b60  mov     qword ptr [rsp+4F0h+samDesired], rax; lpcbData
0x180030b65  mov     rax, [rsp+4F0h+lpData]
0x180030b6a  mov     qword ptr [rsp+4F0h+dwOptions], rax; lpData
0x180030b6f  call    cs:__imp_RegQueryValueExW
0x180030b76  nop     dword ptr [rax+rax+00h]
0x180030b7b  mov     ebx, eax
0x180030b7d  test    eax, eax
0x180030b7f  jnz     short loc_180030BA4
0x180030b81  cmp     [rsp+4F0h+Type], 1
0x180030b86  jnz     short loc_180030BA4
0x180030b88  mov     rcx, [rsp+4F0h+lpData]
0x180030b8d  lea     r8d, [rdi+1]
0x180030b91  mov     rdx, r12
0x180030b94  call    cs:__imp__o__wcsnicmp
0x180030b9b  nop     dword ptr [rax+rax+00h]
0x180030ba0  test    eax, eax
0x180030ba2  jz      short loc_180030BBD
0x180030ba4  mov     rcx, [rsp+4F0h+hKey]; hKey
0x180030ba9  call    cs:__imp_RegCloseKey
0x180030bb0  nop     dword ptr [rax+rax+00h]
0x180030bb5  inc     r13d
0x180030bb8  jmp     loc_180030ACC
0x180030bbd  cmp     r15d, 2
0x180030bc1  jnz     short loc_180030BFF
0x180030bc3  mov     rcx, [rsp+4F0h+hKey]; hKey
0x180030bc8  call    cs:__imp_RegCloseKey
0x180030bcf  nop     dword ptr [rax+rax+00h]
0x180030bd4  xor     r13d, r13d
0x180030bd7  lea     rdx, [rbp+3F0h+Name]; lpSubKey
0x180030bde  xor     r9d, r9d; Reserved
0x180030be1  mov     [rsp+4F0h+hKey], r13
0x180030be6  mov     r8d, 100h; samDesired
0x180030bec  mov     rcx, r14; hKey
0x180030bef  call    cs:__imp_RegDeleteKeyExW
0x180030bf6  nop     dword ptr [rax+rax+00h]
0x180030bfb  mov     ebx, eax
0x180030bfd  jmp     short loc_180030C02
0x180030bff  xor     r13d, r13d
0x180030c02  mov     rax, [rsp+4F0h+hKey]
0x180030c07  mov     rdi, [rsp+4F0h+var_488]
0x180030c0c  mov     [rsp+4F0h+hKey], r13
0x180030c11  mov     [rdi], rax
0x180030c14  jmp     short loc_180030C1E
0x180030c16  mov     rdi, [rsp+4F0h+var_488]
0x180030c1b  xor     r13d, r13d
0x180030c1e  cmp     r15d, 1
0x180030c22  jnz     loc_180030D28
0x180030c28  cmp     ebx, 103h
0x180030c2e  jnz     loc_180030D28
0x180030c34  xorps   xmm0, xmm0
0x180030c37  mov     [rsp+4F0h+dwDisposition], r13d
0x180030c3c  mov     r8, r12; pszSrc
0x180030c3f  lea     edx, [rbx-9]; cchDest
0x180030c42  lea     rcx, [rbp+3F0h+pszDest]; pszDest
0x180030c46  movups  xmmword ptr [rsp+4F0h+DestinationString.Length], xmm0
0x180030c4b  call    StringCchCopyW
0x180030c50  lea     r11, [rbp+3F0h+pszDest]
0x180030c54  inc     rsi
0x180030c57  cmp     [r11+rsi*2], r13w
0x180030c5c  jnz     short loc_180030C54
0x180030c5e  mov     eax, r13d
0x180030c61  test    esi, esi
0x180030c63  jz      short loc_180030C7F
0x180030c65  mov     ecx, eax
0x180030c67  cmp     [rbp+rcx*2+3F0h+pszDest], 5Ch ; '\'
0x180030c6d  jnz     short loc_180030C79
0x180030c6f  mov     edx, 2Fh ; '/'
0x180030c74  mov     [rbp+rcx*2+3F0h+pszDest], dx
0x180030c79  inc     eax
0x180030c7b  cmp     eax, esi
0x180030c7d  jb      short loc_180030C65
0x180030c7f  mov     eax, esi
0x180030c81  mov     ecx, 5Fh ; '_'
0x180030c86  mov     rdx, r12; SourceString
0x180030c89  mov     [rbp+rax*2+3F0h+pszDest], cx
0x180030c8e  lea     rcx, [rsp+4F0h+DestinationString]; DestinationString
0x180030c93  call    cs:__imp_RtlInitUnicodeString
0x180030c9a  nop     dword ptr [rax+rax+00h]
0x180030c9f  lea     r9, [rsp+4F0h+dwDisposition]; HashValue
0x180030ca4  xor     r8d, r8d; HashAlgorithm
0x180030ca7  mov     dl, 1; CaseInSensitive
0x180030ca9  lea     rcx, [rsp+4F0h+DestinationString]; String
0x180030cae  call    cs:__imp_RtlHashUnicodeString
0x180030cb5  nop     dword ptr [rax+rax+00h]
0x180030cba  mov     ecx, [rsp+4F0h+dwDisposition]
0x180030cbe  lea     eax, [rsi+1]
0x180030cc1  mov     r9d, 10h
0x180030cc7  lea     rdx, [rbp+3F0h+pszDest]
0x180030ccb  lea     rdx, [rdx+rax*2]
0x180030ccf  lea     r8d, [r9-7]
0x180030cd3  call    cs:__imp__o__itow_s
0x180030cda  nop     dword ptr [rax+rax+00h]
0x180030cdf  lea     rax, [rsp+4F0h+var_488]
0x180030ce4  mov     [rbp+3F0h+var_258], r13w
0x180030cec  mov     [rsp+4F0h+lpdwDisposition], rax; lpdwDisposition
0x180030cf1  lea     rdx, [rbp+3F0h+pszDest]; lpSubKey
0x180030cf5  mov     [rsp+4F0h+phkResult], rdi; phkResult
0x180030cfa  xor     r9d, r9d; lpClass
0x180030cfd  mov     [rsp+4F0h+lpSecurityAttributes], r13; lpSecurityAttributes
0x180030d02  xor     r8d, r8d; Reserved
0x180030d05  mov     [rsp+4F0h+samDesired], 2001Fh; samDesired
0x180030d0d  mov     rcx, r14; hKey
0x180030d10  mov     [rsp+4F0h+dwOptions], r13d; dwOptions
0x180030d15  mov     dword ptr [rsp+4F0h+var_488], r13d
0x180030d1a  call    cs:__imp_RegCreateKeyExW
0x180030d21  nop     dword ptr [rax+rax+00h]
0x180030d26  mov     ebx, eax
0x180030d28  mov     rcx, [rsp+4F0h+lpData]; hMem
0x180030d2d  call    cs:__imp_LocalFree
0x180030d34  nop     dword ptr [rax+rax+00h]
0x180030d39  mov     eax, ebx
0x180030d3b  mov     rcx, [rbp+3F0h+var_40]
0x180030d42  xor     rcx, rsp; StackCookie
0x180030d45  call    __security_check_cookie
0x180030d4a  mov     rbx, [rsp+4F0h+arg_10]
0x180030d52  add     rsp, 4C0h
0x180030d59  pop     r15
0x180030d5b  pop     r14
0x180030d5d  pop     r13
0x180030d5f  pop     r12
0x180030d61  pop     rdi
0x180030d62  pop     rsi
0x180030d63  pop     rbp
0x180030d64  retn
```
