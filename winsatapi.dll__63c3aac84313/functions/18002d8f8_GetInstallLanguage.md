# GetInstallLanguage

- ea: `0x18002d8f8`
- end: `0x18002da03`
- name: `GetInstallLanguage`
- size: `267`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x180010818`

## callees

- `0x18002d8f8`
- `0x18002dec0`

## import_xrefs

- `msvcrt!_wcsnicmp` at `0x18002d9c0`
- `msvcrt!_wcsnicmp` at `0x18002d9c0`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002d958`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002d958`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002d995`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002d995`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18002d988`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18002d988`

## string_xrefs

- `0x18002d94a`: `Software\Microsoft\Active Setup\Installed Components\{89820200-ECBD-11CF-8B85-00AA005B4383}`

## pseudocode

```c
__int64 GetInstallLanguage()
{
  unsigned __int16 v0; // cx
  unsigned int v1; // ebx
  DWORD cbData; // [rsp+30h] [rbp-28h] BYREF
  HKEY hKey; // [rsp+38h] [rbp-20h] BYREF
  wchar_t Data; // [rsp+40h] [rbp-18h] BYREF

  v0 = word_18004E534;
  hKey = 0;
  if ( !word_18004E534 )
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
          if ( !_wcsnicmp(&Data, (&off_1800340E0)[2 * (int)v1], 3u) )
          {
            v0 = *((_WORD *)&off_1800340E0 + 8 * (int)v1 + 4);
            word_18004E534 = v0;
            return v0;
          }
          ++v1;
        }
      }
    }
    return (unsigned __int16)word_18004E534;
  }
  return v0;
}

```

## disassembly

```asm
0x18002d8f8  mov     r11, rsp
0x18002d8fb  mov     [r11+8], rbx
0x18002d8ff  mov     [r11+10h], rsi
0x18002d903  push    rdi
0x18002d904  sub     rsp, 50h
0x18002d908  mov     rax, cs:__security_cookie
0x18002d90f  xor     rax, rsp
0x18002d912  mov     [rsp+58h+var_10], rax
0x18002d917  movzx   ecx, cs:word_18004E534
0x18002d91e  xor     eax, eax
0x18002d920  mov     qword ptr [r11-20h], 0
0x18002d928  cmp     ax, cx
0x18002d92b  jnz     loc_18002D9E3
0x18002d931  lea     rax, [r11-20h]
0x18002d935  mov     [rsp+58h+cbData], 6
0x18002d93d  mov     r9d, 1; samDesired
0x18002d943  mov     [r11-38h], rax
0x18002d947  xor     r8d, r8d; ulOptions
0x18002d94a  lea     rdx, SubKey; "Software\\Microsoft\\Active Setup\\Inst"...
0x18002d951  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18002d958  call    cs:__imp_RegOpenKeyExW
0x18002d95e  test    eax, eax
0x18002d960  jnz     short loc_18002D9DC
0x18002d962  mov     rcx, [rsp+58h+hKey]; hKey
0x18002d967  lea     rax, [rsp+58h+cbData]
0x18002d96c  mov     [rsp+58h+lpcbData], rax; lpcbData
0x18002d971  lea     rdx, aLocale; "Locale"
0x18002d978  lea     rax, [rsp+58h+Data]
0x18002d97d  xor     r9d, r9d; lpType
0x18002d980  xor     r8d, r8d; lpReserved
0x18002d983  mov     [rsp+58h+lpData], rax; lpData
0x18002d988  call    cs:__imp_RegQueryValueExW
0x18002d98e  mov     rcx, [rsp+58h+hKey]; hKey
0x18002d993  mov     ebx, eax
0x18002d995  call    cs:__imp_RegCloseKey
0x18002d99b  test    ebx, ebx
0x18002d99d  jnz     short loc_18002D9DC
0x18002d99f  lea     rsi, off_1800340E0; "EN"
0x18002d9a6  cmp     ebx, 1Ch
0x18002d9a9  jnb     short loc_18002D9DC
0x18002d9ab  movsxd  rdi, ebx
0x18002d9ae  lea     rcx, [rsp+58h+Data]; String1
0x18002d9b3  add     rdi, rdi
0x18002d9b6  mov     r8d, 3; MaxCount
0x18002d9bc  mov     rdx, [rsi+rdi*8]; String2
0x18002d9c0  call    cs:__imp__wcsnicmp
0x18002d9c6  test    eax, eax
0x18002d9c8  jz      short loc_18002D9CE
0x18002d9ca  inc     ebx
0x18002d9cc  jmp     short loc_18002D9A6
0x18002d9ce  movzx   ecx, word ptr [rsi+rdi*8+8]
0x18002d9d3  mov     cs:word_18004E534, cx
0x18002d9da  jmp     short loc_18002D9E3
0x18002d9dc  movzx   ecx, cs:word_18004E534
0x18002d9e3  movzx   eax, cx
0x18002d9e6  mov     rcx, [rsp+58h+var_10]
0x18002d9eb  xor     rcx, rsp; StackCookie
0x18002d9ee  call    __security_check_cookie
0x18002d9f3  mov     rbx, [rsp+58h+arg_0]
0x18002d9f8  mov     rsi, [rsp+58h+arg_8]
0x18002d9fd  add     rsp, 50h
0x18002da01  pop     rdi
0x18002da02  retn
```
