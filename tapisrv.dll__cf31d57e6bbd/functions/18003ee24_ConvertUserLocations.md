# ConvertUserLocations

- ea: `0x18003ee24`
- end: `0x18003f106`
- name: `ConvertUserLocations`
- size: `738`
- prototype: `__int64 __fastcall(HKEY)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18001cb10`

## callees

- `0x180001600`
- `0x18001c740`
- `0x18001c8a4`
- `0x18003ee24`
- `0x18003f3c0`
- `0x18003f91c`
- `0x18003f958`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003ef00`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003f00c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003f0db`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003f0eb`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003ef00`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003f00c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003f0db`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003f0eb`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18003f0c9`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18003f0c9`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18003ee83`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18003ef48`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18003ee83`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18003ef48`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18003ef80`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18003eff7`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18003ef80`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18003eff7`
- `KERNEL32!GlobalAlloc` at `0x18003efc0`
- `KERNEL32!GlobalAlloc` at `0x18003efc0`
- `KERNEL32!GlobalFree` at `0x18003f0f9`
- `KERNEL32!GlobalFree` at `0x18003f0f9`
- `KERNEL32!GetWindowsDirectoryW` at `0x18003eea4`
- `KERNEL32!GetWindowsDirectoryW` at `0x18003eea4`

## string_xrefs

- `0x18003ef79`: `KeyRenameHistory`
- `0x18003efe5`: `KeyRenameHistory`

## pseudocode

```c
__int64 __fastcall ConvertUserLocations(HKEY a1)
{
  LSTATUS v1; // eax
  unsigned int v2; // ebx
  BYTE *v3; // rdi
  LSTATUS v5; // eax
  LSTATUS v6; // eax
  DWORD v7; // eax
  BYTE *v8; // rbx
  DWORD v9; // eax
  DWORD v10; // esi
  int v11; // ecx
  int v12; // r14d
  PHKEY phkResult; // [rsp+20h] [rbp-E0h]
  PHKEY phkResulta; // [rsp+20h] [rbp-E0h]
  DWORD cbData; // [rsp+30h] [rbp-D0h] BYREF
  HKEY hKey; // [rsp+38h] [rbp-C8h] BYREF
  HKEY v17; // [rsp+40h] [rbp-C0h] BYREF
  DWORD Type; // [rsp+48h] [rbp-B8h] BYREF
  BYTE Data[4]; // [rsp+4Ch] [rbp-B4h] BYREF
  wchar_t NewKeyName[24]; // [rsp+50h] [rbp-B0h] BYREF
  wchar_t pszDest[24]; // [rsp+80h] [rbp-80h] BYREF
  WCHAR Buffer[264]; // [rsp+B0h] [rbp-50h] BYREF

  v17 = 0;
  hKey = 0;
  cbData = 0;
  Type = 0;
  *(_DWORD *)Data = 0;
  v1 = RegOpenKeyExW(a1, L"Software\\Microsoft\\Windows\\CurrentVersion\\Telephony\\Locations", 0, 0x2001Fu, &hKey);
  v2 = v1;
  if ( v1 == 2 )
    return 0;
  v3 = 0;
  if ( !v1 )
  {
    if ( GetWindowsDirectoryW(Buffer, 0xF8u) )
    {
      if ( Buffer[3] )
        StringCbCatW(Buffer, 0x20Au, L"\\");
      StringCbCatW(Buffer, 0x20Au, L"REGULOCS.OLD");
      SaveKey(hKey, Buffer);
    }
    if ( !(unsigned int)IsLocationListInOldFormat(hKey) )
    {
      RegCloseKey(hKey);
      return 0;
    }
    v5 = RegOpenKeyExW(
           HKEY_LOCAL_MACHINE,
           L"Software\\Microsoft\\Windows\\CurrentVersion\\Telephony\\Locations",
           0,
           1u,
           &v17);
    v2 = v5;
    if ( v5 == 2 )
      return 0;
    if ( !v5 )
    {
      v6 = RegQueryValueExW(v17, L"KeyRenameHistory", 0, &Type, 0, &cbData);
      v2 = v6;
      if ( v6 )
      {
        if ( v6 != 2 )
          goto LABEL_27;
        v7 = 0;
        cbData = 0;
      }
      else
      {
        if ( Type != 3 )
        {
          v2 = 13;
          goto LABEL_27;
        }
        v7 = cbData;
      }
      if ( v7 )
      {
        v3 = (BYTE *)GlobalAlloc(0x40u, v7);
        if ( !v3 )
        {
          v2 = 14;
          goto LABEL_27;
        }
        v2 = RegQueryValueExW(v17, L"KeyRenameHistory", 0, 0, v3, &cbData);
        if ( v2 )
          goto LABEL_27;
        RegCloseKey(v17);
        v8 = v3;
        v9 = cbData >> 3;
        v10 = 0;
        v17 = 0;
        for ( cbData = v9; v10 < v9; ++v10 )
        {
          v11 = *(_DWORD *)v8;
          v12 = *((_DWORD *)v8 + 1);
          v8 += 8;
          if ( v12 != v11 )
          {
            LODWORD(phkResult) = v11;
            StringCbPrintfW(pszDest, 0x2Au, L"%s%d", L"Location", phkResult);
            LODWORD(phkResulta) = v12;
            StringCbPrintfW(NewKeyName, 0x2Au, L"%s%d", L"Location", phkResulta);
            RegRenameKey(hKey, pszDest, NewKeyName);
            v9 = cbData;
          }
        }
      }
      *(_DWORD *)Data = 2;
      v2 = RegSetValueExW(hKey, L"LocationListVersion", 0, 4u, Data, 4u);
    }
  }
LABEL_27:
  if ( v17 )
    RegCloseKey(v17);
  if ( hKey )
    RegCloseKey(hKey);
  if ( v3 )
    GlobalFree(v3);
  return v2;
}

```

## disassembly

```asm
0x18003ee24  push    rbp
0x18003ee26  push    rbx
0x18003ee27  push    rsi
0x18003ee28  push    rdi
0x18003ee29  push    r14
0x18003ee2b  push    r15
0x18003ee2d  lea     rbp, [rsp-1D8h]
0x18003ee35  sub     rsp, 2D8h
0x18003ee3c  mov     rax, cs:__security_cookie
0x18003ee43  xor     rax, rsp
0x18003ee46  mov     [rbp+200h+var_40], rax
0x18003ee4d  xor     r15d, r15d
0x18003ee50  lea     rax, [rsp+300h+hKey]
0x18003ee55  mov     r9d, 2001Fh; samDesired
0x18003ee5b  mov     [rsp+300h+var_2C0], r15
0x18003ee60  xor     r8d, r8d; ulOptions
0x18003ee63  mov     [rsp+300h+hKey], r15
0x18003ee68  lea     rdx, aSoftwareMicros_2; "Software\\Microsoft\\Windows\\CurrentVe"...
0x18003ee6f  mov     [rsp+300h+cbData], r15d
0x18003ee74  mov     [rsp+300h+Type], r15d
0x18003ee79  mov     dword ptr [rsp+300h+Data], r15d
0x18003ee7e  mov     [rsp+300h+phkResult], rax; phkResult
0x18003ee83  call    cs:__imp_RegOpenKeyExW
0x18003ee89  mov     ebx, eax
0x18003ee8b  cmp     eax, 2
0x18003ee8e  jz      short loc_18003EF06
0x18003ee90  mov     edi, r15d
0x18003ee93  test    eax, eax
0x18003ee95  jnz     loc_18003F0D1
0x18003ee9b  mov     edx, 0F8h; uSize
0x18003eea0  lea     rcx, [rbp+200h+Buffer]; lpBuffer
0x18003eea4  call    cs:__imp_GetWindowsDirectoryW
0x18003eeaa  test    eax, eax
0x18003eeac  jz      short loc_18003EEED
0x18003eeae  mov     ebx, 20Ah
0x18003eeb3  cmp     [rbp+200h+var_24A], r15w
0x18003eeb8  jz      short loc_18003EECC
0x18003eeba  lea     r8, pszSrc; "\\"
0x18003eec1  mov     edx, ebx; cbDest
0x18003eec3  lea     rcx, [rbp+200h+Buffer]; pszDest
0x18003eec7  call    StringCbCatW
0x18003eecc  lea     r8, aRegulocsOld; "REGULOCS.OLD"
0x18003eed3  mov     rdx, rbx; cbDest
0x18003eed6  lea     rcx, [rbp+200h+Buffer]; pszDest
0x18003eeda  call    StringCbCatW
0x18003eedf  mov     rcx, [rsp+300h+hKey]; hKey
0x18003eee4  lea     rdx, [rbp+200h+Buffer]; lpFile
0x18003eee8  call    SaveKey
0x18003eeed  mov     rcx, [rsp+300h+hKey]
0x18003eef2  call    IsLocationListInOldFormat
0x18003eef7  test    eax, eax
0x18003eef9  jnz     short loc_18003EF27
0x18003eefb  mov     rcx, [rsp+300h+hKey]; hKey
0x18003ef00  call    cs:__imp_RegCloseKey
0x18003ef06  xor     eax, eax
0x18003ef08  mov     rcx, [rbp+200h+var_40]
0x18003ef0f  xor     rcx, rsp; StackCookie
0x18003ef12  call    __security_check_cookie
0x18003ef17  add     rsp, 2D8h
0x18003ef1e  pop     r15
0x18003ef20  pop     r14
0x18003ef22  pop     rdi
0x18003ef23  pop     rsi
0x18003ef24  pop     rbx
0x18003ef25  pop     rbp
0x18003ef26  retn
0x18003ef27  lea     rax, [rsp+300h+var_2C0]
0x18003ef2c  mov     r9d, 1; samDesired
0x18003ef32  xor     r8d, r8d; ulOptions
0x18003ef35  mov     [rsp+300h+phkResult], rax; phkResult
0x18003ef3a  lea     rdx, aSoftwareMicros_2; "Software\\Microsoft\\Windows\\CurrentVe"...
0x18003ef41  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18003ef48  call    cs:__imp_RegOpenKeyExW
0x18003ef4e  mov     ebx, eax
0x18003ef50  cmp     eax, 2
0x18003ef53  jz      short loc_18003EF06
0x18003ef55  test    eax, eax
0x18003ef57  jnz     loc_18003F0D1
0x18003ef5d  mov     rcx, [rsp+300h+var_2C0]; hKey
0x18003ef62  lea     rax, [rsp+300h+cbData]
0x18003ef67  mov     [rsp+300h+lpcbData], rax; lpcbData
0x18003ef6c  lea     r9, [rsp+300h+Type]; lpType
0x18003ef71  xor     r8d, r8d; lpReserved
0x18003ef74  mov     [rsp+300h+phkResult], r15; lpData
0x18003ef79  lea     rdx, aKeyrenamehisto; "KeyRenameHistory"
0x18003ef80  call    cs:__imp_RegQueryValueExW
0x18003ef86  mov     ebx, eax
0x18003ef88  test    eax, eax
0x18003ef8a  jnz     short loc_18003EFA1
0x18003ef8c  cmp     [rsp+300h+Type], 3
0x18003ef91  jz      short loc_18003EF9B
0x18003ef93  lea     ebx, [rax+0Dh]
0x18003ef96  jmp     loc_18003F0D1
0x18003ef9b  mov     eax, [rsp+300h+cbData]
0x18003ef9f  jmp     short loc_18003EFB1
0x18003efa1  cmp     eax, 2
0x18003efa4  jnz     loc_18003F0D1
0x18003efaa  mov     eax, r15d
0x18003efad  mov     [rsp+300h+cbData], eax
0x18003efb1  test    eax, eax
0x18003efb3  jz      loc_18003F09A
0x18003efb9  mov     edx, eax; dwBytes
0x18003efbb  mov     ecx, 40h ; '@'; uFlags
0x18003efc0  call    cs:__imp_GlobalAlloc
0x18003efc6  mov     rdi, rax
0x18003efc9  test    rax, rax
0x18003efcc  jnz     short loc_18003EFD6
0x18003efce  lea     ebx, [rax+0Eh]
0x18003efd1  jmp     loc_18003F0D1
0x18003efd6  mov     rcx, [rsp+300h+var_2C0]; hKey
0x18003efdb  lea     rax, [rsp+300h+cbData]
0x18003efe0  mov     [rsp+300h+lpcbData], rax; lpcbData
0x18003efe5  lea     rdx, aKeyrenamehisto; "KeyRenameHistory"
0x18003efec  xor     r9d, r9d; lpType
0x18003efef  mov     [rsp+300h+phkResult], rdi; lpData
0x18003eff4  xor     r8d, r8d; lpReserved
0x18003eff7  call    cs:__imp_RegQueryValueExW
0x18003effd  mov     ebx, eax
0x18003efff  test    eax, eax
0x18003f001  jnz     loc_18003F0D1
0x18003f007  mov     rcx, [rsp+300h+var_2C0]; hKey
0x18003f00c  call    cs:__imp_RegCloseKey
0x18003f012  mov     eax, [rsp+300h+cbData]
0x18003f016  mov     rbx, rdi
0x18003f019  shr     eax, 3
0x18003f01c  mov     esi, r15d
0x18003f01f  mov     [rsp+300h+var_2C0], r15
0x18003f024  mov     [rsp+300h+cbData], eax
0x18003f028  test    eax, eax
0x18003f02a  jz      short loc_18003F09A
0x18003f02c  mov     ecx, [rbx]
0x18003f02e  mov     r14d, [rbx+4]
0x18003f032  lea     rbx, [rbx+8]
0x18003f036  cmp     r14d, ecx
0x18003f039  jz      short loc_18003F094
0x18003f03b  mov     dword ptr [rsp+300h+phkResult], ecx
0x18003f03f  lea     r9, aLocation; "Location"
0x18003f046  lea     rcx, [rbp+200h+pszDest]; pszDest
0x18003f04a  mov     edx, 2Ah ; '*'; cbDest
0x18003f04f  lea     r8, aSD; "%s%d"
0x18003f056  call    StringCbPrintfW
0x18003f05b  lea     r9, aLocation; "Location"
0x18003f062  mov     dword ptr [rsp+300h+phkResult], r14d
0x18003f067  lea     r8, aSD; "%s%d"
0x18003f06e  mov     edx, 2Ah ; '*'; cbDest
0x18003f073  lea     rcx, [rsp+300h+NewKeyName]; pszDest
0x18003f078  call    StringCbPrintfW
0x18003f07d  mov     rcx, [rsp+300h+hKey]; hKey
0x18003f082  lea     r8, [rsp+300h+NewKeyName]; lpNewKeyName
0x18003f087  lea     rdx, [rbp+200h+pszDest]; lpSubKeyName
0x18003f08b  call    RegRenameKey
0x18003f090  mov     eax, [rsp+300h+cbData]
0x18003f094  inc     esi
0x18003f096  cmp     esi, eax
0x18003f098  jb      short loc_18003F02C
0x18003f09a  mov     rcx, [rsp+300h+hKey]; hKey
0x18003f09f  lea     rax, [rsp+300h+Data]
0x18003f0a4  mov     dword ptr [rsp+300h+lpcbData], 4; cbData
0x18003f0ac  lea     rdx, aLocationlistve; "LocationListVersion"
0x18003f0b3  mov     r9d, 4; dwType
0x18003f0b9  mov     [rsp+300h+phkResult], rax; lpData
0x18003f0be  xor     r8d, r8d; Reserved
0x18003f0c1  mov     dword ptr [rsp+300h+Data], 2
0x18003f0c9  call    cs:__imp_RegSetValueExW
0x18003f0cf  mov     ebx, eax
0x18003f0d1  mov     rcx, [rsp+300h+var_2C0]; hKey
0x18003f0d6  test    rcx, rcx
0x18003f0d9  jz      short loc_18003F0E1
0x18003f0db  call    cs:__imp_RegCloseKey
0x18003f0e1  mov     rcx, [rsp+300h+hKey]; hKey
0x18003f0e6  test    rcx, rcx
0x18003f0e9  jz      short loc_18003F0F1
0x18003f0eb  call    cs:__imp_RegCloseKey
0x18003f0f1  test    rdi, rdi
0x18003f0f4  jz      short loc_18003F0FF
0x18003f0f6  mov     rcx, rdi; hMem
0x18003f0f9  call    cs:__imp_GlobalFree
0x18003f0ff  mov     eax, ebx
0x18003f101  jmp     loc_18003EF08
```
