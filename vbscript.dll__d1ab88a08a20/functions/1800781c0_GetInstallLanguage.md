# GetInstallLanguage

- ea: `0x1800781c0`
- end: `0x1800782e1`
- name: `GetInstallLanguage`
- size: `289`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x1800788a0`

## callees

- `0x180046e90`
- `0x1800781c0`
- `0x180079490`

## import_xrefs

- `ADVAPI32!RegOpenKeyExW` at `0x180078220`
- `ADVAPI32!RegOpenKeyExW` at `0x180078220`
- `ADVAPI32!RegCloseKey` at `0x18007826d`
- `ADVAPI32!RegCloseKey` at `0x18007826d`
- `ADVAPI32!RegQueryValueExW` at `0x18007825a`
- `ADVAPI32!RegQueryValueExW` at `0x18007825a`

## string_xrefs

- `0x180078212`: `Software\Microsoft\Active Setup\Installed Components\{89820200-ECBD-11CF-8B85-00AA005B4383}`

## pseudocode

```c
__int64 GetInstallLanguage()
{
  unsigned __int16 v0; // cx
  unsigned int v1; // ebx
  DWORD cbData; // [rsp+30h] [rbp-28h] BYREF
  HKEY hKey; // [rsp+38h] [rbp-20h] BYREF
  wchar_t Data; // [rsp+40h] [rbp-18h] BYREF

  v0 = word_18009384C;
  hKey = 0;
  if ( !word_18009384C )
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
          if ( !wcsnicmp_0(&Data, (&off_18007D740)[2 * (int)v1], 3u) )
          {
            v0 = *((_WORD *)&off_18007D740 + 8 * (int)v1 + 4);
            word_18009384C = v0;
            return v0;
          }
          ++v1;
        }
      }
    }
    return (unsigned __int16)word_18009384C;
  }
  return v0;
}

```

## disassembly

```asm
0x1800781c0  mov     r11, rsp
0x1800781c3  mov     [r11+8], rbx
0x1800781c7  mov     [r11+10h], rsi
0x1800781cb  push    rdi
0x1800781cc  sub     rsp, 50h
0x1800781d0  mov     rax, cs:__security_cookie
0x1800781d7  xor     rax, rsp
0x1800781da  mov     [rsp+58h+var_10], rax
0x1800781df  movzx   ecx, cs:word_18009384C
0x1800781e6  xor     eax, eax
0x1800781e8  mov     qword ptr [r11-20h], 0
0x1800781f0  cmp     ax, cx
0x1800781f3  jnz     loc_1800782C0
0x1800781f9  lea     rax, [r11-20h]
0x1800781fd  mov     [rsp+58h+cbData], 6
0x180078205  mov     r9d, 1; samDesired
0x18007820b  mov     [r11-38h], rax
0x18007820f  xor     r8d, r8d; ulOptions
0x180078212  lea     rdx, aSoftwareMicros_5; "Software\\Microsoft\\Active Setup\\Inst"...
0x180078219  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180078220  call    cs:__imp_RegOpenKeyExW
0x180078227  nop     dword ptr [rax+rax+00h]
0x18007822c  test    eax, eax
0x18007822e  jnz     loc_1800782B9
0x180078234  mov     rcx, [rsp+58h+hKey]; hKey
0x180078239  lea     rax, [rsp+58h+cbData]
0x18007823e  mov     [rsp+58h+lpcbData], rax; lpcbData
0x180078243  lea     rdx, aLocale_0; "Locale"
0x18007824a  lea     rax, [rsp+58h+Data]
0x18007824f  xor     r9d, r9d; lpType
0x180078252  xor     r8d, r8d; lpReserved
0x180078255  mov     [rsp+58h+lpData], rax; lpData
0x18007825a  call    cs:__imp_RegQueryValueExW
0x180078261  nop     dword ptr [rax+rax+00h]
0x180078266  mov     rcx, [rsp+58h+hKey]; hKey
0x18007826b  mov     ebx, eax
0x18007826d  call    cs:__imp_RegCloseKey
0x180078274  nop     dword ptr [rax+rax+00h]
0x180078279  test    ebx, ebx
0x18007827b  jnz     short loc_1800782B9
0x18007827d  lea     rsi, off_18007D740; "EN"
0x180078284  cmp     ebx, 1Ch
0x180078287  jnb     short loc_1800782B9
0x180078289  movsxd  rdi, ebx
0x18007828c  lea     rcx, [rsp+58h+Data]; String1
0x180078291  add     rdi, rdi
0x180078294  mov     r8d, 3; MaxCount
0x18007829a  mov     rdx, [rsi+rdi*8]; String2
0x18007829e  call    _wcsnicmp_0
0x1800782a3  test    eax, eax
0x1800782a5  jz      short loc_1800782AB
0x1800782a7  inc     ebx
0x1800782a9  jmp     short loc_180078284
0x1800782ab  movzx   ecx, word ptr [rsi+rdi*8+8]
0x1800782b0  mov     cs:word_18009384C, cx
0x1800782b7  jmp     short loc_1800782C0
0x1800782b9  movzx   ecx, cs:word_18009384C
0x1800782c0  movzx   eax, cx
0x1800782c3  mov     rcx, [rsp+58h+var_10]
0x1800782c8  xor     rcx, rsp; StackCookie
0x1800782cb  call    __security_check_cookie
0x1800782d0  mov     rbx, [rsp+58h+arg_0]
0x1800782d5  mov     rsi, [rsp+58h+arg_8]
0x1800782da  add     rsp, 50h
0x1800782de  pop     rdi
0x1800782df  retn
```
