# GetInstallLanguage

- ea: `0x18000c480`
- end: `0x18000c58b`
- name: `GetInstallLanguage`
- size: `267`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x18000cba0`

## callees

- `0x18000c480`
- `0x18000d1c0`

## import_xrefs

- `msvcrt!_wcsnicmp` at `0x18000c548`
- `msvcrt!_wcsnicmp` at `0x18000c548`
- `ADVAPI32!RegCloseKey` at `0x18000c51d`
- `ADVAPI32!RegCloseKey` at `0x18000c51d`
- `ADVAPI32!RegOpenKeyExW` at `0x18000c4e0`
- `ADVAPI32!RegOpenKeyExW` at `0x18000c4e0`
- `ADVAPI32!RegQueryValueExW` at `0x18000c510`
- `ADVAPI32!RegQueryValueExW` at `0x18000c510`

## string_xrefs

- `0x18000c4d2`: `Software\Microsoft\Active Setup\Installed Components\{89820200-ECBD-11CF-8B85-00AA005B4383}`

## pseudocode

```c
__int64 GetInstallLanguage()
{
  unsigned __int16 v0; // cx
  unsigned int v1; // ebx
  DWORD cbData; // [rsp+30h] [rbp-28h] BYREF
  HKEY hKey; // [rsp+38h] [rbp-20h] BYREF
  wchar_t Data; // [rsp+40h] [rbp-18h] BYREF

  v0 = word_180014914;
  hKey = 0;
  if ( !word_180014914 )
  {
    cbData = 6;
    if ( !RegOpenKeyExW(
            HKEY_LOCAL_MACHINE,
            L"Software\\Microsoft\\Active Setup\\Installed Components\\{89820200-ECBD-11CF-8B85-00AA005B4383}",
            0,
            1u,
            &hKey) )
    {
      v1 = RegQueryValueExW(hKey, L"Locale", 0, 0, (LPBYTE)&Data, &cbData);
      RegCloseKey(hKey);
      if ( !v1 )
      {
        while ( v1 < 0x1C )
        {
          if ( !_wcsnicmp(&Data, (&off_18000F480)[2 * (int)v1], 3u) )
          {
            v0 = *((_WORD *)&off_18000F480 + 8 * (int)v1 + 4);
            word_180014914 = v0;
            return v0;
          }
          ++v1;
        }
      }
    }
    return (unsigned __int16)word_180014914;
  }
  return v0;
}

```

## disassembly

```asm
0x18000c480  mov     r11, rsp
0x18000c483  mov     [r11+8], rbx
0x18000c487  mov     [r11+10h], rsi
0x18000c48b  push    rdi
0x18000c48c  sub     rsp, 50h
0x18000c490  mov     rax, cs:__security_cookie
0x18000c497  xor     rax, rsp
0x18000c49a  mov     [rsp+58h+var_10], rax
0x18000c49f  movzx   ecx, cs:word_180014914
0x18000c4a6  xor     eax, eax
0x18000c4a8  mov     qword ptr [r11-20h], 0
0x18000c4b0  cmp     ax, cx
0x18000c4b3  jnz     loc_18000C56B
0x18000c4b9  lea     rax, [r11-20h]
0x18000c4bd  mov     [rsp+58h+cbData], 6
0x18000c4c5  mov     r9d, 1; samDesired
0x18000c4cb  mov     [r11-38h], rax
0x18000c4cf  xor     r8d, r8d; ulOptions
0x18000c4d2  lea     rdx, aSoftwareMicros_0; "Software\\Microsoft\\Active Setup\\Inst"...
0x18000c4d9  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18000c4e0  call    cs:__imp_RegOpenKeyExW
0x18000c4e6  test    eax, eax
0x18000c4e8  jnz     short loc_18000C564
0x18000c4ea  mov     rcx, [rsp+58h+hKey]; hKey
0x18000c4ef  lea     rax, [rsp+58h+cbData]
0x18000c4f4  mov     [rsp+58h+lpcbData], rax; lpcbData
0x18000c4f9  lea     rdx, aLocale; "Locale"
0x18000c500  lea     rax, [rsp+58h+Data]
0x18000c505  xor     r9d, r9d; lpType
0x18000c508  xor     r8d, r8d; lpReserved
0x18000c50b  mov     [rsp+58h+lpData], rax; lpData
0x18000c510  call    cs:__imp_RegQueryValueExW
0x18000c516  mov     rcx, [rsp+58h+hKey]; hKey
0x18000c51b  mov     ebx, eax
0x18000c51d  call    cs:__imp_RegCloseKey
0x18000c523  test    ebx, ebx
0x18000c525  jnz     short loc_18000C564
0x18000c527  lea     rsi, off_18000F480; "EN"
0x18000c52e  cmp     ebx, 1Ch
0x18000c531  jnb     short loc_18000C564
0x18000c533  movsxd  rdi, ebx
0x18000c536  lea     rcx, [rsp+58h+Data]; String1
0x18000c53b  add     rdi, rdi
0x18000c53e  mov     r8d, 3; MaxCount
0x18000c544  mov     rdx, [rsi+rdi*8]; String2
0x18000c548  call    cs:__imp__wcsnicmp
0x18000c54e  test    eax, eax
0x18000c550  jz      short loc_18000C556
0x18000c552  inc     ebx
0x18000c554  jmp     short loc_18000C52E
0x18000c556  movzx   ecx, word ptr [rsi+rdi*8+8]
0x18000c55b  mov     cs:word_180014914, cx
0x18000c562  jmp     short loc_18000C56B
0x18000c564  movzx   ecx, cs:word_180014914
0x18000c56b  movzx   eax, cx
0x18000c56e  mov     rcx, [rsp+58h+var_10]
0x18000c573  xor     rcx, rsp; StackCookie
0x18000c576  call    __security_check_cookie
0x18000c57b  mov     rbx, [rsp+58h+arg_0]
0x18000c580  mov     rsi, [rsp+58h+arg_8]
0x18000c585  add     rsp, 50h
0x18000c589  pop     rdi
0x18000c58a  retn
```
