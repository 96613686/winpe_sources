# GetInstallLanguage

- ea: `0x14003f42c`
- end: `0x14003f52e`
- name: `GetInstallLanguage`
- size: `258`
- prototype: `__int64()`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x14003faf0`

## callees

- `0x140002778`
- `0x14003f42c`
- `0x140040130`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x14003f489`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x14003f489`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x14003f4b9`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x14003f4b9`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14003f4c6`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14003f4c6`

## string_xrefs

- `0x14003f47b`: `Software\Microsoft\Active Setup\Installed Components\{89820200-ECBD-11CF-8B85-00AA005B4383}`

## pseudocode

```c
__int64 GetInstallLanguage()
{
  LSTATUS v0; // ebx
  DWORD cbData; // [rsp+30h] [rbp-28h] BYREF
  HKEY hKey; // [rsp+38h] [rbp-20h] BYREF
  wchar_t Data; // [rsp+40h] [rbp-18h] BYREF

  hKey = 0;
  if ( !word_140084B3C )
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
        while ( wcsnicmp_0(&Data, (&off_140042260)[2 * v0], 3u) )
        {
          if ( (unsigned int)++v0 >= 0x1C )
            return (unsigned __int16)word_140084B3C;
        }
        word_140084B3C = *((_WORD *)&off_140042260 + 8 * v0 + 4);
      }
    }
  }
  return (unsigned __int16)word_140084B3C;
}

```

## disassembly

```asm
0x14003f42c  mov     r11, rsp
0x14003f42f  mov     [r11+8], rbx
0x14003f433  mov     [r11+10h], rsi
0x14003f437  push    rdi
0x14003f438  sub     rsp, 50h
0x14003f43c  mov     rax, cs:__security_cookie
0x14003f443  xor     rax, rsp
0x14003f446  mov     [rsp+58h+var_10], rax
0x14003f44b  xor     eax, eax
0x14003f44d  mov     qword ptr [r11-20h], 0
0x14003f455  cmp     ax, cs:word_140084B3C
0x14003f45c  jnz     loc_14003F50A
0x14003f462  lea     rax, [r11-20h]
0x14003f466  mov     [rsp+58h+cbData], 6
0x14003f46e  mov     r9d, 1; samDesired
0x14003f474  mov     [r11-38h], rax
0x14003f478  xor     r8d, r8d; ulOptions
0x14003f47b  lea     rdx, SubKey; "Software\\Microsoft\\Active Setup\\Inst"...
0x14003f482  mov     rcx, 0FFFFFFFF80000002h; hKey
0x14003f489  call    cs:__imp_RegOpenKeyExW
0x14003f48f  test    eax, eax
0x14003f491  jnz     short loc_14003F50A
0x14003f493  mov     rcx, [rsp+58h+hKey]; hKey
0x14003f498  lea     rax, [rsp+58h+cbData]
0x14003f49d  mov     [rsp+58h+lpcbData], rax; lpcbData
0x14003f4a2  lea     rdx, ValueName; "Locale"
0x14003f4a9  lea     rax, [rsp+58h+Data]
0x14003f4ae  xor     r9d, r9d; lpType
0x14003f4b1  xor     r8d, r8d; lpReserved
0x14003f4b4  mov     [rsp+58h+lpData], rax; lpData
0x14003f4b9  call    cs:__imp_RegQueryValueExW
0x14003f4bf  mov     rcx, [rsp+58h+hKey]; hKey
0x14003f4c4  mov     ebx, eax
0x14003f4c6  call    cs:__imp_RegCloseKey
0x14003f4cc  test    ebx, ebx
0x14003f4ce  jnz     short loc_14003F50A
0x14003f4d0  lea     rsi, off_140042260; "EN"
0x14003f4d7  movsxd  rdi, ebx
0x14003f4da  lea     rcx, [rsp+58h+Data]; String1
0x14003f4df  add     rdi, rdi
0x14003f4e2  mov     r8d, 3; MaxCount
0x14003f4e8  mov     rdx, [rsi+rdi*8]; String2
0x14003f4ec  call    _wcsnicmp_0
0x14003f4f1  test    eax, eax
0x14003f4f3  jz      short loc_14003F4FE
0x14003f4f5  inc     ebx
0x14003f4f7  cmp     ebx, 1Ch
0x14003f4fa  jb      short loc_14003F4D7
0x14003f4fc  jmp     short loc_14003F50A
0x14003f4fe  movzx   eax, word ptr [rsi+rdi*8+8]
0x14003f503  mov     cs:word_140084B3C, ax
0x14003f50a  movzx   eax, cs:word_140084B3C
0x14003f511  mov     rcx, [rsp+58h+var_10]
0x14003f516  xor     rcx, rsp; StackCookie
0x14003f519  call    __security_check_cookie
0x14003f51e  mov     rbx, [rsp+58h+arg_0]
0x14003f523  mov     rsi, [rsp+58h+arg_8]
0x14003f528  add     rsp, 50h
0x14003f52c  pop     rdi
0x14003f52d  retn
```
