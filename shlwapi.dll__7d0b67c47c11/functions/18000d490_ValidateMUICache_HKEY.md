# _ValidateMUICache(HKEY__ *)

- ea: `0x18000d490`
- end: `0x18000d578`
- name: `?_ValidateMUICache@@YAXPEAUHKEY__@@@Z`
- size: `232`
- prototype: `void __fastcall(HKEY)`
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config`

## callees

- `0x18000d490`
- `0x180012550`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000d560`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000d560`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000d4c3`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000d4c3`
- `api-ms-win-core-localization-obsolete-l1-2-0!GetUserDefaultUILanguage` at `0x18000d4e3`
- `api-ms-win-core-localization-obsolete-l1-2-0!GetUserDefaultUILanguage` at `0x18000d4e3`
- `api-ms-win-shcore-registry-l1-1-0!SHDeleteKeyW` at `0x18000d52c`
- `api-ms-win-shcore-registry-l1-1-0!SHDeleteKeyW` at `0x18000d52c`
- `api-ms-win-shcore-registry-l1-1-0!SHGetValueW` at `0x18000d516`
- `api-ms-win-shcore-registry-l1-1-0!SHGetValueW` at `0x18000d516`
- `api-ms-win-shcore-registry-l1-1-0!SHSetValueW` at `0x18000d556`
- `api-ms-win-shcore-registry-l1-1-0!SHSetValueW` at `0x18000d556`

## pseudocode

```c
void __fastcall _ValidateMUICache(HKEY a1)
{
  LSTATUS v1; // eax
  bool v2; // sf
  HKEY hkey; // [rsp+30h] [rbp-20h] BYREF
  _WORD pvData[2]; // [rsp+38h] [rbp-18h] BYREF
  LANGID UserDefaultUILanguage; // [rsp+3Ch] [rbp-14h] BYREF
  DWORD pcbData; // [rsp+40h] [rbp-10h] BYREF

  hkey = 0;
  v1 = RegOpenKeyExW(a1, 0, 0, 0x2001Fu, &hkey);
  v2 = v1 < 0;
  if ( v1 > 0 )
    v2 = 1;
  if ( !v2 )
  {
    pvData[0] = 0;
    UserDefaultUILanguage = GetUserDefaultUILanguage();
    pcbData = 2;
    SHGetValueW(hkey, 0, L"LangID", 0, pvData, &pcbData);
    if ( pvData[0] != UserDefaultUILanguage )
    {
      SHDeleteKeyW(hkey, 0);
      SHSetValueW(hkey, 0, L"LangID", 3u, &UserDefaultUILanguage, 2u);
    }
    RegCloseKey(hkey);
  }
}

```

## disassembly

```asm
0x18000d490  push    rbp
0x18000d492  mov     rbp, rsp
0x18000d495  sub     rsp, 50h
0x18000d499  mov     rax, cs:__security_cookie
0x18000d4a0  xor     rax, rsp
0x18000d4a3  mov     [rbp+var_8], rax
0x18000d4a7  lea     rax, [rbp+hkey]
0x18000d4ab  mov     [rbp+hkey], 0
0x18000d4b3  mov     r9d, 2001Fh; samDesired
0x18000d4b9  mov     [rsp+50h+phkResult], rax; phkResult
0x18000d4be  xor     r8d, r8d; ulOptions
0x18000d4c1  xor     edx, edx; lpSubKey
0x18000d4c3  call    cs:__imp_RegOpenKeyExW
0x18000d4c9  test    eax, eax
0x18000d4cb  jle     short loc_18000D4D7
0x18000d4cd  movzx   eax, ax
0x18000d4d0  or      eax, 80070000h
0x18000d4d5  test    eax, eax
0x18000d4d7  js      loc_18000D566
0x18000d4dd  xor     eax, eax
0x18000d4df  mov     [rbp+pvData], ax
0x18000d4e3  call    cs:__imp_GetUserDefaultUILanguage
0x18000d4e9  mov     rcx, [rbp+hkey]; hkey
0x18000d4ed  lea     r8, aLangid; "LangID"
0x18000d4f4  mov     [rbp+var_14], ax
0x18000d4f8  xor     r9d, r9d; pdwType
0x18000d4fb  lea     rax, [rbp+var_10]
0x18000d4ff  mov     [rbp+var_10], 2
0x18000d506  mov     [rsp+50h+pcbData], rax; pcbData
0x18000d50b  xor     edx, edx; pszSubKey
0x18000d50d  lea     rax, [rbp+pvData]
0x18000d511  mov     [rsp+50h+phkResult], rax; pvData
0x18000d516  call    cs:__imp_SHGetValueW
0x18000d51c  movzx   eax, [rbp+var_14]
0x18000d520  cmp     [rbp+pvData], ax
0x18000d524  jz      short loc_18000D55C
0x18000d526  mov     rcx, [rbp+hkey]; hkey
0x18000d52a  xor     edx, edx; pszSubKey
0x18000d52c  call    cs:__imp_SHDeleteKeyW
0x18000d532  mov     rcx, [rbp+hkey]; hkey
0x18000d536  lea     rax, [rbp+var_14]
0x18000d53a  mov     dword ptr [rsp+50h+pcbData], 2; cbData
0x18000d542  lea     r8, aLangid; "LangID"
0x18000d549  mov     r9d, 3; dwType
0x18000d54f  mov     [rsp+50h+phkResult], rax; pvData
0x18000d554  xor     edx, edx; pszSubKey
0x18000d556  call    cs:__imp_SHSetValueW
0x18000d55c  mov     rcx, [rbp+hkey]; hKey
0x18000d560  call    cs:__imp_RegCloseKey
0x18000d566  mov     rcx, [rbp+var_8]
0x18000d56a  xor     rcx, rsp; StackCookie
0x18000d56d  call    __security_check_cookie
0x18000d572  add     rsp, 50h
0x18000d576  pop     rbp
0x18000d577  retn
```
