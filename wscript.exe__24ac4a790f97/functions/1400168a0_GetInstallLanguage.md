# GetInstallLanguage

- ea: `0x1400168a0`
- end: `0x1400169a3`
- name: `GetInstallLanguage`
- size: `259`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x140016f68`

## callees

- `0x1400168a0`
- `0x1400175a0`

## import_xrefs

- `msvcrt!_wcsnicmp` at `0x140016960`
- `msvcrt!_wcsnicmp` at `0x140016960`
- `ADVAPI32!RegCloseKey` at `0x14001693a`
- `ADVAPI32!RegCloseKey` at `0x14001693a`
- `ADVAPI32!RegQueryValueExW` at `0x14001692d`
- `ADVAPI32!RegQueryValueExW` at `0x14001692d`
- `ADVAPI32!RegOpenKeyExW` at `0x1400168fd`
- `ADVAPI32!RegOpenKeyExW` at `0x1400168fd`

## string_xrefs

- `0x1400168ef`: `Software\Microsoft\Active Setup\Installed Components\{89820200-ECBD-11CF-8B85-00AA005B4383}`

## pseudocode

```c
__int64 GetInstallLanguage()
{
  LSTATUS v0; // ebx
  DWORD cbData; // [rsp+30h] [rbp-28h] BYREF
  HKEY hKey; // [rsp+38h] [rbp-20h] BYREF
  wchar_t Data; // [rsp+40h] [rbp-18h] BYREF

  hKey = 0;
  if ( !word_140020A44 )
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
        while ( _wcsnicmp(&Data, (&off_140019C70)[2 * v0], 3u) )
        {
          if ( (unsigned int)++v0 >= 0x1C )
            return (unsigned __int16)word_140020A44;
        }
        word_140020A44 = *((_WORD *)&off_140019C70 + 8 * v0 + 4);
      }
    }
  }
  return (unsigned __int16)word_140020A44;
}

```

## disassembly

```asm
0x1400168a0  mov     r11, rsp
0x1400168a3  mov     [r11+8], rbx
0x1400168a7  mov     [r11+10h], rsi
0x1400168ab  push    rdi
0x1400168ac  sub     rsp, 50h
0x1400168b0  mov     rax, cs:__security_cookie
0x1400168b7  xor     rax, rsp
0x1400168ba  mov     [rsp+58h+var_10], rax
0x1400168bf  xor     eax, eax
0x1400168c1  mov     qword ptr [r11-20h], 0
0x1400168c9  cmp     ax, cs:word_140020A44
0x1400168d0  jnz     loc_14001697F
0x1400168d6  lea     rax, [r11-20h]
0x1400168da  mov     [rsp+58h+cbData], 6
0x1400168e2  mov     r9d, 1; samDesired
0x1400168e8  mov     [r11-38h], rax
0x1400168ec  xor     r8d, r8d; ulOptions
0x1400168ef  lea     rdx, aSoftwareMicros_1; "Software\\Microsoft\\Active Setup\\Inst"...
0x1400168f6  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1400168fd  call    cs:__imp_RegOpenKeyExW
0x140016903  test    eax, eax
0x140016905  jnz     short loc_14001697F
0x140016907  mov     rcx, [rsp+58h+hKey]; hKey
0x14001690c  lea     rax, [rsp+58h+cbData]
0x140016911  mov     [rsp+58h+lpcbData], rax; lpcbData
0x140016916  lea     rdx, aLocale; "Locale"
0x14001691d  lea     rax, [rsp+58h+Data]
0x140016922  xor     r9d, r9d; lpType
0x140016925  xor     r8d, r8d; lpReserved
0x140016928  mov     [rsp+58h+lpData], rax; lpData
0x14001692d  call    cs:__imp_RegQueryValueExW
0x140016933  mov     rcx, [rsp+58h+hKey]; hKey
0x140016938  mov     ebx, eax
0x14001693a  call    cs:__imp_RegCloseKey
0x140016940  test    ebx, ebx
0x140016942  jnz     short loc_14001697F
0x140016944  lea     rsi, off_140019C70; "EN"
0x14001694b  movsxd  rdi, ebx
0x14001694e  lea     rcx, [rsp+58h+Data]; String1
0x140016953  add     rdi, rdi
0x140016956  mov     r8d, 3; MaxCount
0x14001695c  mov     rdx, [rsi+rdi*8]; String2
0x140016960  call    cs:__imp__wcsnicmp
0x140016966  test    eax, eax
0x140016968  jz      short loc_140016973
0x14001696a  inc     ebx
0x14001696c  cmp     ebx, 1Ch
0x14001696f  jb      short loc_14001694B
0x140016971  jmp     short loc_14001697F
0x140016973  movzx   eax, word ptr [rsi+rdi*8+8]
0x140016978  mov     cs:word_140020A44, ax
0x14001697f  movzx   eax, cs:word_140020A44
0x140016986  mov     rcx, [rsp+58h+var_10]
0x14001698b  xor     rcx, rsp; StackCookie
0x14001698e  call    __security_check_cookie
0x140016993  mov     rbx, [rsp+58h+arg_0]
0x140016998  mov     rsi, [rsp+58h+arg_8]
0x14001699d  add     rsp, 50h
0x1400169a1  pop     rdi
0x1400169a2  retn
```
