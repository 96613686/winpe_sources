# GetInstallLanguage

- ea: `0x18000f55c`
- end: `0x18000f667`
- name: `GetInstallLanguage`
- size: `267`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x18000fc7c`

## callees

- `0x18000f55c`
- `0x180010250`

## import_xrefs

- `msvcrt!_wcsnicmp` at `0x18000f624`
- `msvcrt!_wcsnicmp` at `0x18000f624`
- `ADVAPI32!RegQueryValueExW` at `0x18000f5ec`
- `ADVAPI32!RegQueryValueExW` at `0x18000f5ec`
- `ADVAPI32!RegCloseKey` at `0x18000f5f9`
- `ADVAPI32!RegCloseKey` at `0x18000f5f9`
- `ADVAPI32!RegOpenKeyExW` at `0x18000f5bc`
- `ADVAPI32!RegOpenKeyExW` at `0x18000f5bc`

## string_xrefs

- `0x18000f5ae`: `Software\Microsoft\Active Setup\Installed Components\{89820200-ECBD-11CF-8B85-00AA005B4383}`

## pseudocode

```c
__int64 GetInstallLanguage()
{
  unsigned __int16 v0; // cx
  unsigned int v1; // ebx
  DWORD cbData; // [rsp+30h] [rbp-28h] BYREF
  HKEY hKey; // [rsp+38h] [rbp-20h] BYREF
  wchar_t Data; // [rsp+40h] [rbp-18h] BYREF

  v0 = word_180018C1C;
  hKey = 0;
  if ( !word_180018C1C )
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
          if ( !_wcsnicmp(&Data, (&off_180012D60)[2 * (int)v1], 3u) )
          {
            v0 = *((_WORD *)&off_180012D60 + 8 * (int)v1 + 4);
            word_180018C1C = v0;
            return v0;
          }
          ++v1;
        }
      }
    }
    return (unsigned __int16)word_180018C1C;
  }
  return v0;
}

```

## disassembly

```asm
0x18000f55c  mov     r11, rsp
0x18000f55f  mov     [r11+8], rbx
0x18000f563  mov     [r11+10h], rsi
0x18000f567  push    rdi
0x18000f568  sub     rsp, 50h
0x18000f56c  mov     rax, cs:__security_cookie
0x18000f573  xor     rax, rsp
0x18000f576  mov     [rsp+58h+var_10], rax
0x18000f57b  movzx   ecx, cs:word_180018C1C
0x18000f582  xor     eax, eax
0x18000f584  mov     qword ptr [r11-20h], 0
0x18000f58c  cmp     ax, cx
0x18000f58f  jnz     loc_18000F647
0x18000f595  lea     rax, [r11-20h]
0x18000f599  mov     [rsp+58h+cbData], 6
0x18000f5a1  mov     r9d, 1; samDesired
0x18000f5a7  mov     [r11-38h], rax
0x18000f5ab  xor     r8d, r8d; ulOptions
0x18000f5ae  lea     rdx, aSoftwareMicros_0; "Software\\Microsoft\\Active Setup\\Inst"...
0x18000f5b5  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18000f5bc  call    cs:__imp_RegOpenKeyExW
0x18000f5c2  test    eax, eax
0x18000f5c4  jnz     short loc_18000F640
0x18000f5c6  mov     rcx, [rsp+58h+hKey]; hKey
0x18000f5cb  lea     rax, [rsp+58h+cbData]
0x18000f5d0  mov     [rsp+58h+lpcbData], rax; lpcbData
0x18000f5d5  lea     rdx, aLocale; "Locale"
0x18000f5dc  lea     rax, [rsp+58h+Data]
0x18000f5e1  xor     r9d, r9d; lpType
0x18000f5e4  xor     r8d, r8d; lpReserved
0x18000f5e7  mov     [rsp+58h+lpData], rax; lpData
0x18000f5ec  call    cs:__imp_RegQueryValueExW
0x18000f5f2  mov     rcx, [rsp+58h+hKey]; hKey
0x18000f5f7  mov     ebx, eax
0x18000f5f9  call    cs:__imp_RegCloseKey
0x18000f5ff  test    ebx, ebx
0x18000f601  jnz     short loc_18000F640
0x18000f603  lea     rsi, off_180012D60; "EN"
0x18000f60a  cmp     ebx, 1Ch
0x18000f60d  jnb     short loc_18000F640
0x18000f60f  movsxd  rdi, ebx
0x18000f612  lea     rcx, [rsp+58h+Data]; String1
0x18000f617  add     rdi, rdi
0x18000f61a  mov     r8d, 3; MaxCount
0x18000f620  mov     rdx, [rsi+rdi*8]; String2
0x18000f624  call    cs:__imp__wcsnicmp
0x18000f62a  test    eax, eax
0x18000f62c  jz      short loc_18000F632
0x18000f62e  inc     ebx
0x18000f630  jmp     short loc_18000F60A
0x18000f632  movzx   ecx, word ptr [rsi+rdi*8+8]
0x18000f637  mov     cs:word_180018C1C, cx
0x18000f63e  jmp     short loc_18000F647
0x18000f640  movzx   ecx, cs:word_180018C1C
0x18000f647  movzx   eax, cx
0x18000f64a  mov     rcx, [rsp+58h+var_10]
0x18000f64f  xor     rcx, rsp; StackCookie
0x18000f652  call    __security_check_cookie
0x18000f657  mov     rbx, [rsp+58h+arg_0]
0x18000f65c  mov     rsi, [rsp+58h+arg_8]
0x18000f661  add     rsp, 50h
0x18000f665  pop     rdi
0x18000f666  retn
```
