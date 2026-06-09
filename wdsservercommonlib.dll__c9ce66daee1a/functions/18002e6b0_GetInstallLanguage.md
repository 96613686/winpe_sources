# GetInstallLanguage

- ea: `0x18002e6b0`
- end: `0x18002e7d4`
- name: `GetInstallLanguage`
- size: `292`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x18002edd8`

## callees

- `0x180001885`
- `0x18002e6b0`
- `0x18002f3e0`

## import_xrefs

- `ADVAPI32!RegCloseKey` at `0x18002e758`
- `ADVAPI32!RegCloseKey` at `0x18002e758`
- `ADVAPI32!RegOpenKeyExW` at `0x18002e70b`
- `ADVAPI32!RegOpenKeyExW` at `0x18002e70b`
- `ADVAPI32!RegQueryValueExW` at `0x18002e745`
- `ADVAPI32!RegQueryValueExW` at `0x18002e745`

## string_xrefs

- `0x18002e6fd`: `Software\Microsoft\Active Setup\Installed Components\{89820200-ECBD-11CF-8B85-00AA005B4383}`

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
  if ( !word_180049DA0 )
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
        for ( i = (const wchar_t **)&off_180031270; wcsnicmp_0(&Data, *i, 3u); i += 2 )
        {
          if ( (unsigned int)++v1 >= 0x1C )
            return (unsigned __int16)word_180049DA0;
        }
        word_180049DA0 = *((_WORD *)&off_180031270 + 8 * v1 + 4);
      }
    }
  }
  return (unsigned __int16)word_180049DA0;
}

```

## disassembly

```asm
0x18002e6b0  mov     r11, rsp
0x18002e6b3  mov     [r11+8], rbx
0x18002e6b7  mov     [r11+10h], rbp
0x18002e6bb  mov     [r11+18h], rsi
0x18002e6bf  push    rdi
0x18002e6c0  sub     rsp, 50h
0x18002e6c4  mov     rax, cs:__security_cookie
0x18002e6cb  xor     rax, rsp
0x18002e6ce  mov     [rsp+58h+var_10], rax
0x18002e6d3  xor     esi, esi
0x18002e6d5  cmp     si, cs:word_180049DA0
0x18002e6dc  mov     [r11-20h], rsi
0x18002e6e0  jnz     loc_18002E7AA
0x18002e6e6  lea     rax, [r11-20h]
0x18002e6ea  mov     [rsp+58h+cbData], 6
0x18002e6f2  lea     r9d, [rsi+1]; samDesired
0x18002e6f6  mov     [r11-38h], rax
0x18002e6fa  xor     r8d, r8d; ulOptions
0x18002e6fd  lea     rdx, SubKey; "Software\\Microsoft\\Active Setup\\Inst"...
0x18002e704  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18002e70b  call    cs:__imp_RegOpenKeyExW
0x18002e712  nop     dword ptr [rax+rax+00h]
0x18002e717  test    eax, eax
0x18002e719  jnz     loc_18002E7AA
0x18002e71f  mov     rcx, [rsp+58h+hKey]; hKey
0x18002e724  lea     rax, [rsp+58h+cbData]
0x18002e729  mov     [rsp+58h+lpcbData], rax; lpcbData
0x18002e72e  lea     rdx, ValueName; "Locale"
0x18002e735  lea     rax, [rsp+58h+Data]
0x18002e73a  xor     r9d, r9d; lpType
0x18002e73d  xor     r8d, r8d; lpReserved
0x18002e740  mov     [rsp+58h+lpData], rax; lpData
0x18002e745  call    cs:__imp_RegQueryValueExW
0x18002e74c  nop     dword ptr [rax+rax+00h]
0x18002e751  mov     rcx, [rsp+58h+hKey]; hKey
0x18002e756  mov     ebx, eax
0x18002e758  call    cs:__imp_RegCloseKey
0x18002e75f  nop     dword ptr [rax+rax+00h]
0x18002e764  test    ebx, ebx
0x18002e766  jnz     short loc_18002E7AA
0x18002e768  lea     rbp, off_180031270; "EN"
0x18002e76f  mov     ebx, esi
0x18002e771  mov     rdi, rbp
0x18002e774  mov     rdx, [rdi]; String2
0x18002e777  lea     rcx, [rsp+58h+Data]; String1
0x18002e77c  mov     r8d, 3; MaxCount
0x18002e782  call    _wcsnicmp_0
0x18002e787  test    eax, eax
0x18002e789  jz      short loc_18002E798
0x18002e78b  inc     ebx
0x18002e78d  add     rdi, 10h
0x18002e791  cmp     ebx, 1Ch
0x18002e794  jb      short loc_18002E774
0x18002e796  jmp     short loc_18002E7AA
0x18002e798  movsxd  rax, ebx
0x18002e79b  add     rax, rax
0x18002e79e  movzx   eax, word ptr [rbp+rax*8+8]
0x18002e7a3  mov     cs:word_180049DA0, ax
0x18002e7aa  movzx   eax, cs:word_180049DA0
0x18002e7b1  mov     rcx, [rsp+58h+var_10]
0x18002e7b6  xor     rcx, rsp; StackCookie
0x18002e7b9  call    __security_check_cookie
0x18002e7be  mov     rbx, [rsp+58h+arg_0]
0x18002e7c3  mov     rbp, [rsp+58h+arg_8]
0x18002e7c8  mov     rsi, [rsp+58h+arg_10]
0x18002e7cd  add     rsp, 50h
0x18002e7d1  pop     rdi
0x18002e7d2  retn
```
