# RegAddECDSAAssociation

- ea: `0x18000aa4c`
- end: `0x18000abf6`
- name: `RegAddECDSAAssociation`
- size: `426`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x1800183ec`

## callees

- `0x18000a848`
- `0x18000aa4c`
- `0x18000b114`
- `0x18003c240`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x18000ab71`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x18000ab71`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x18000aae5`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x18000ab20`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x18000ab5d`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x18000aae5`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x18000ab20`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x18000ab5d`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18000abb8`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18000abb8`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000abc8`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000abc8`

## pseudocode

```c
__int64 __fastcall RegAddECDSAAssociation(__int64 a1, const WCHAR *a2, const wchar_t *a3)
{
  __int64 v4; // rdx
  __int64 v6; // rcx
  HRESULT v7; // eax
  HKEY v8; // rdi
  HRESULT v9; // ebx
  DWORD v10; // ebx
  DWORD cchValueName; // [rsp+40h] [rbp-C0h] BYREF
  HKEY hKey; // [rsp+48h] [rbp-B8h] BYREF
  size_t pcchLength[2]; // [rsp+50h] [rbp-B0h] BYREF
  WCHAR ValueName[264]; // [rsp+60h] [rbp-A0h] BYREF

  cchValueName = 260;
  v4 = *(unsigned int *)(a1 + 560);
  v6 = *(_QWORD *)(a1 + 552);
  hKey = 0;
  pcchLength[0] = 0;
  v7 = I_RegOpenCardKey(v6, v4, &hKey, 131079);
  v8 = hKey;
  v9 = v7;
  if ( !v7 )
  {
    v10 = 0;
    if ( RegEnumValueW(hKey, 0, ValueName, &cchValueName, 0, 0, 0, 0) )
      goto LABEL_7;
    do
    {
      ++v10;
      cchValueName = 260;
    }
    while ( !RegEnumValueW(v8, v10, ValueName, &cchValueName, 0, 0, 0, 0) );
    if ( v10 + 1 < 0x64
      || (cchValueName = 260, (v9 = RegEnumValueW(v8, 0, ValueName, &cchValueName, 0, 0, 0, 0)) == 0)
      && (v9 = RegDeleteValueW(v8, ValueName)) == 0 )
    {
LABEL_7:
      v9 = StringCchLengthW(a3, 0x28u, pcchLength);
      if ( v9 >= 0 )
        v9 = RegSetValueExW(v8, a2, 0, 1u, (const BYTE *)a3, 2 * LODWORD(pcchLength[0]) + 2);
    }
  }
  if ( v8 )
    RegCloseKey(v8);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x18000aa4c  mov     [rsp-8+arg_18], rbx
0x18000aa51  push    rbp
0x18000aa52  push    rsi
0x18000aa53  push    rdi
0x18000aa54  push    r14
0x18000aa56  push    r15
0x18000aa58  lea     rbp, [rsp-180h]
0x18000aa60  sub     rsp, 280h
0x18000aa67  mov     rax, cs:__security_cookie
0x18000aa6e  xor     rax, rsp
0x18000aa71  mov     [rbp+1A0h+var_30], rax
0x18000aa78  mov     r14, rdx
0x18000aa7b  mov     [rsp+2A0h+cchValueName], 104h
0x18000aa83  mov     edx, [rcx+230h]
0x18000aa89  mov     rsi, r8
0x18000aa8c  mov     rcx, [rcx+228h]
0x18000aa93  lea     r8, [rsp+2A0h+hKey]
0x18000aa98  xor     r15d, r15d
0x18000aa9b  mov     r9d, 20007h
0x18000aaa1  mov     [rsp+2A0h+hKey], r15
0x18000aaa6  mov     [rsp+2A0h+pcchLength], r15
0x18000aaab  call    I_RegOpenCardKey
0x18000aab0  mov     rdi, [rsp+2A0h+hKey]
0x18000aab5  mov     ebx, eax
0x18000aab7  test    eax, eax
0x18000aab9  jnz     loc_18000ABC0
0x18000aabf  mov     [rsp+2A0h+lpcbData], r15; lpcbData
0x18000aac4  lea     r9, [rsp+2A0h+cchValueName]; lpcchValueName
0x18000aac9  mov     [rsp+2A0h+lpData], r15; lpData
0x18000aace  lea     r8, [rsp+2A0h+ValueName]; lpValueName
0x18000aad3  mov     [rsp+2A0h+lpType], r15; lpType
0x18000aad8  xor     edx, edx; dwIndex
0x18000aada  mov     rcx, rdi; hKey
0x18000aadd  mov     [rsp+2A0h+lpReserved], r15; lpReserved
0x18000aae2  mov     ebx, r15d
0x18000aae5  call    cs:__imp_RegEnumValueW
0x18000aaeb  test    eax, eax
0x18000aaed  jnz     loc_18000AB7D
0x18000aaf3  mov     [rsp+2A0h+lpcbData], r15; lpcbData
0x18000aaf8  lea     r9, [rsp+2A0h+cchValueName]; lpcchValueName
0x18000aafd  mov     [rsp+2A0h+lpData], r15; lpData
0x18000ab02  lea     r8, [rsp+2A0h+ValueName]; lpValueName
0x18000ab07  inc     ebx
0x18000ab09  mov     [rsp+2A0h+lpType], r15; lpType
0x18000ab0e  mov     edx, ebx; dwIndex
0x18000ab10  mov     [rsp+2A0h+lpReserved], r15; lpReserved
0x18000ab15  mov     rcx, rdi; hKey
0x18000ab18  mov     [rsp+2A0h+cchValueName], 104h
0x18000ab20  call    cs:__imp_RegEnumValueW
0x18000ab26  test    eax, eax
0x18000ab28  jz      short loc_18000AAF3
0x18000ab2a  lea     eax, [rbx+1]
0x18000ab2d  cmp     eax, 64h ; 'd'
0x18000ab30  jb      short loc_18000AB7D
0x18000ab32  mov     [rsp+2A0h+lpcbData], r15; lpcbData
0x18000ab37  lea     r9, [rsp+2A0h+cchValueName]; lpcchValueName
0x18000ab3c  mov     [rsp+2A0h+lpData], r15; lpData
0x18000ab41  lea     r8, [rsp+2A0h+ValueName]; lpValueName
0x18000ab46  mov     [rsp+2A0h+lpType], r15; lpType
0x18000ab4b  xor     edx, edx; dwIndex
0x18000ab4d  mov     rcx, rdi; hKey
0x18000ab50  mov     [rsp+2A0h+lpReserved], r15; lpReserved
0x18000ab55  mov     [rsp+2A0h+cchValueName], 104h
0x18000ab5d  call    cs:__imp_RegEnumValueW
0x18000ab63  mov     ebx, eax
0x18000ab65  test    eax, eax
0x18000ab67  jnz     short loc_18000ABC0
0x18000ab69  lea     rdx, [rsp+2A0h+ValueName]; lpValueName
0x18000ab6e  mov     rcx, rdi; hKey
0x18000ab71  call    cs:__imp_RegDeleteValueW
0x18000ab77  mov     ebx, eax
0x18000ab79  test    eax, eax
0x18000ab7b  jnz     short loc_18000ABC0
0x18000ab7d  lea     r8, [rsp+2A0h+pcchLength]; pcchLength
0x18000ab82  mov     edx, 28h ; '('; cchMax
0x18000ab87  mov     rcx, rsi; psz
0x18000ab8a  call    StringCchLengthW
0x18000ab8f  mov     ebx, eax
0x18000ab91  test    eax, eax
0x18000ab93  js      short loc_18000ABC0
0x18000ab95  mov     eax, dword ptr [rsp+2A0h+pcchLength]
0x18000ab99  mov     r9d, 1; dwType
0x18000ab9f  xor     r8d, r8d; Reserved
0x18000aba2  mov     rdx, r14; lpValueName
0x18000aba5  mov     rcx, rdi; hKey
0x18000aba8  lea     eax, ds:2[rax*2]
0x18000abaf  mov     dword ptr [rsp+2A0h+lpType], eax; cbData
0x18000abb3  mov     [rsp+2A0h+lpReserved], rsi; lpData
0x18000abb8  call    cs:__imp_RegSetValueExW
0x18000abbe  mov     ebx, eax
0x18000abc0  test    rdi, rdi
0x18000abc3  jz      short loc_18000ABCE
0x18000abc5  mov     rcx, rdi; hKey
0x18000abc8  call    cs:__imp_RegCloseKey
0x18000abce  mov     eax, ebx
0x18000abd0  mov     rcx, [rbp+1A0h+var_30]
0x18000abd7  xor     rcx, rsp; StackCookie
0x18000abda  call    __security_check_cookie
0x18000abdf  mov     rbx, [rsp+2A0h+arg_18]
0x18000abe7  add     rsp, 280h
0x18000abee  pop     r15
0x18000abf0  pop     r14
0x18000abf2  pop     rdi
0x18000abf3  pop     rsi
0x18000abf4  pop     rbp
0x18000abf5  retn
```
