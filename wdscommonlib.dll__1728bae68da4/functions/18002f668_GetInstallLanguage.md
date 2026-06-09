# GetInstallLanguage

- ea: `0x18002f668`
- end: `0x18002f78c`
- name: `GetInstallLanguage`
- size: `292`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x18002fd90`

## callees

- `0x180002235`
- `0x18002f668`
- `0x180030390`

## import_xrefs

- `ADVAPI32!RegCloseKey` at `0x18002f710`
- `ADVAPI32!RegCloseKey` at `0x18002f710`
- `ADVAPI32!RegOpenKeyExW` at `0x18002f6c3`
- `ADVAPI32!RegOpenKeyExW` at `0x18002f6c3`
- `ADVAPI32!RegQueryValueExW` at `0x18002f6fd`
- `ADVAPI32!RegQueryValueExW` at `0x18002f6fd`

## string_xrefs

- `0x18002f6b5`: `Software\Microsoft\Active Setup\Installed Components\{89820200-ECBD-11CF-8B85-00AA005B4383}`

## pseudocode

```c
__int64 GetInstallLanguage()
{
  LSTATUS v0; // ebx
  int v1; // ebx
  const wchar_t **i; // rdi
  DWORD cbData; // [rsp+30h] [rbp-28h] BYREF
  HKEY hKey; // [rsp+38h] [rbp-20h] BYREF
  wchar_t Data; // [rsp+40h] [rbp-18h] BYREF

  hKey = 0;
  if ( !word_18004BE9C )
  {
    cbData = 6;
    if ( !RegOpenKeyExW(
            HKEY_LOCAL_MACHINE,
            L"Software\\Microsoft\\Active Setup\\Installed Components\\{89820200-ECBD-11CF-8B85-00AA005B4383}",
            0,
            1u,
            &hKey) )
    {
      v0 = RegQueryValueExW(hKey, L"Locale", 0, 0, (LPBYTE)&Data, &cbData);
      RegCloseKey(hKey);
      if ( !v0 )
      {
        v1 = 0;
        for ( i = (const wchar_t **)&off_180032CF0; wcsnicmp_0(&Data, *i, 3u); i += 2 )
        {
          if ( (unsigned int)++v1 >= 0x1C )
            return (unsigned __int16)word_18004BE9C;
        }
        word_18004BE9C = *((_WORD *)&off_180032CF0 + 8 * v1 + 4);
      }
    }
  }
  return (unsigned __int16)word_18004BE9C;
}

```

## disassembly

```asm
0x18002f668  mov     r11, rsp
0x18002f66b  mov     [r11+8], rbx
0x18002f66f  mov     [r11+10h], rbp
0x18002f673  mov     [r11+18h], rsi
0x18002f677  push    rdi
0x18002f678  sub     rsp, 50h
0x18002f67c  mov     rax, cs:__security_cookie
0x18002f683  xor     rax, rsp
0x18002f686  mov     [rsp+58h+var_10], rax
0x18002f68b  xor     esi, esi
0x18002f68d  cmp     si, cs:word_18004BE9C
0x18002f694  mov     [r11-20h], rsi
0x18002f698  jnz     loc_18002F762
0x18002f69e  lea     rax, [r11-20h]
0x18002f6a2  mov     [rsp+58h+cbData], 6
0x18002f6aa  lea     r9d, [rsi+1]; samDesired
0x18002f6ae  mov     [r11-38h], rax
0x18002f6b2  xor     r8d, r8d; ulOptions
0x18002f6b5  lea     rdx, SubKey; "Software\\Microsoft\\Active Setup\\Inst"...
0x18002f6bc  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18002f6c3  call    cs:__imp_RegOpenKeyExW
0x18002f6ca  nop     dword ptr [rax+rax+00h]
0x18002f6cf  test    eax, eax
0x18002f6d1  jnz     loc_18002F762
0x18002f6d7  mov     rcx, [rsp+58h+hKey]; hKey
0x18002f6dc  lea     rax, [rsp+58h+cbData]
0x18002f6e1  mov     [rsp+58h+lpcbData], rax; lpcbData
0x18002f6e6  lea     rdx, ValueName; "Locale"
0x18002f6ed  lea     rax, [rsp+58h+Data]
0x18002f6f2  xor     r9d, r9d; lpType
0x18002f6f5  xor     r8d, r8d; lpReserved
0x18002f6f8  mov     [rsp+58h+lpData], rax; lpData
0x18002f6fd  call    cs:__imp_RegQueryValueExW
0x18002f704  nop     dword ptr [rax+rax+00h]
0x18002f709  mov     rcx, [rsp+58h+hKey]; hKey
0x18002f70e  mov     ebx, eax
0x18002f710  call    cs:__imp_RegCloseKey
0x18002f717  nop     dword ptr [rax+rax+00h]
0x18002f71c  test    ebx, ebx
0x18002f71e  jnz     short loc_18002F762
0x18002f720  lea     rbp, off_180032CF0; "EN"
0x18002f727  mov     ebx, esi
0x18002f729  mov     rdi, rbp
0x18002f72c  mov     rdx, [rdi]; String2
0x18002f72f  lea     rcx, [rsp+58h+Data]; String1
0x18002f734  mov     r8d, 3; MaxCount
0x18002f73a  call    _wcsnicmp_0
0x18002f73f  test    eax, eax
0x18002f741  jz      short loc_18002F750
0x18002f743  inc     ebx
0x18002f745  add     rdi, 10h
0x18002f749  cmp     ebx, 1Ch
0x18002f74c  jb      short loc_18002F72C
0x18002f74e  jmp     short loc_18002F762
0x18002f750  movsxd  rax, ebx
0x18002f753  add     rax, rax
0x18002f756  movzx   eax, word ptr [rbp+rax*8+8]
0x18002f75b  mov     cs:word_18004BE9C, ax
0x18002f762  movzx   eax, cs:word_18004BE9C
0x18002f769  mov     rcx, [rsp+58h+var_10]
0x18002f76e  xor     rcx, rsp; StackCookie
0x18002f771  call    __security_check_cookie
0x18002f776  mov     rbx, [rsp+58h+arg_0]
0x18002f77b  mov     rbp, [rsp+58h+arg_8]
0x18002f780  mov     rsi, [rsp+58h+arg_10]
0x18002f785  add     rsp, 50h
0x18002f789  pop     rdi
0x18002f78a  retn
```
