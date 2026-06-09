# GetInstallLanguage

- ea: `0x1800755e4`
- end: `0x1800756ee`
- name: `GetInstallLanguage`
- size: `266`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x180075c48`

## callees

- `0x180045aa0`
- `0x1800755e4`
- `0x1800767a0`

## import_xrefs

- `ADVAPI32!RegOpenKeyExW` at `0x180075644`
- `ADVAPI32!RegOpenKeyExW` at `0x180075644`
- `ADVAPI32!RegCloseKey` at `0x180075681`
- `ADVAPI32!RegCloseKey` at `0x180075681`
- `ADVAPI32!RegQueryValueExW` at `0x180075674`
- `ADVAPI32!RegQueryValueExW` at `0x180075674`

## string_xrefs

- `0x180075636`: `Software\Microsoft\Active Setup\Installed Components\{89820200-ECBD-11CF-8B85-00AA005B4383}`

## pseudocode

```c
__int64 GetInstallLanguage()
{
  unsigned __int16 v0; // cx
  unsigned int v1; // ebx
  DWORD cbData; // [rsp+30h] [rbp-28h] BYREF
  HKEY hKey; // [rsp+38h] [rbp-20h] BYREF
  wchar_t Data; // [rsp+40h] [rbp-18h] BYREF

  v0 = word_18009084C;
  hKey = 0;
  if ( !word_18009084C )
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
          if ( !wcsnicmp_0(&Data, (&off_18007A740)[2 * (int)v1], 3u) )
          {
            v0 = *((_WORD *)&off_18007A740 + 8 * (int)v1 + 4);
            word_18009084C = v0;
            return v0;
          }
          ++v1;
        }
      }
    }
    return (unsigned __int16)word_18009084C;
  }
  return v0;
}

```

## disassembly

```asm
0x1800755e4  mov     r11, rsp
0x1800755e7  mov     [r11+8], rbx
0x1800755eb  mov     [r11+10h], rsi
0x1800755ef  push    rdi
0x1800755f0  sub     rsp, 50h
0x1800755f4  mov     rax, cs:__security_cookie
0x1800755fb  xor     rax, rsp
0x1800755fe  mov     [rsp+58h+var_10], rax
0x180075603  movzx   ecx, cs:word_18009084C
0x18007560a  xor     eax, eax
0x18007560c  mov     qword ptr [r11-20h], 0
0x180075614  cmp     ax, cx
0x180075617  jnz     loc_1800756CE
0x18007561d  lea     rax, [r11-20h]
0x180075621  mov     [rsp+58h+cbData], 6
0x180075629  mov     r9d, 1; samDesired
0x18007562f  mov     [r11-38h], rax
0x180075633  xor     r8d, r8d; ulOptions
0x180075636  lea     rdx, aSoftwareMicros_5; "Software\\Microsoft\\Active Setup\\Inst"...
0x18007563d  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180075644  call    cs:__imp_RegOpenKeyExW
0x18007564a  test    eax, eax
0x18007564c  jnz     short loc_1800756C7
0x18007564e  mov     rcx, [rsp+58h+hKey]; hKey
0x180075653  lea     rax, [rsp+58h+cbData]
0x180075658  mov     [rsp+58h+lpcbData], rax; lpcbData
0x18007565d  lea     rdx, aLocale_0; "Locale"
0x180075664  lea     rax, [rsp+58h+Data]
0x180075669  xor     r9d, r9d; lpType
0x18007566c  xor     r8d, r8d; lpReserved
0x18007566f  mov     [rsp+58h+lpData], rax; lpData
0x180075674  call    cs:__imp_RegQueryValueExW
0x18007567a  mov     rcx, [rsp+58h+hKey]; hKey
0x18007567f  mov     ebx, eax
0x180075681  call    cs:__imp_RegCloseKey
0x180075687  test    ebx, ebx
0x180075689  jnz     short loc_1800756C7
0x18007568b  lea     rsi, off_18007A740; "EN"
0x180075692  cmp     ebx, 1Ch
0x180075695  jnb     short loc_1800756C7
0x180075697  movsxd  rdi, ebx
0x18007569a  lea     rcx, [rsp+58h+Data]; String1
0x18007569f  add     rdi, rdi
0x1800756a2  mov     r8d, 3; MaxCount
0x1800756a8  mov     rdx, [rsi+rdi*8]; String2
0x1800756ac  call    _wcsnicmp_0
0x1800756b1  test    eax, eax
0x1800756b3  jz      short loc_1800756B9
0x1800756b5  inc     ebx
0x1800756b7  jmp     short loc_180075692
0x1800756b9  movzx   ecx, word ptr [rsi+rdi*8+8]
0x1800756be  mov     cs:word_18009084C, cx
0x1800756c5  jmp     short loc_1800756CE
0x1800756c7  movzx   ecx, cs:word_18009084C
0x1800756ce  movzx   eax, cx
0x1800756d1  mov     rcx, [rsp+58h+var_10]
0x1800756d6  xor     rcx, rsp; StackCookie
0x1800756d9  call    __security_check_cookie
0x1800756de  mov     rbx, [rsp+58h+arg_0]
0x1800756e3  mov     rsi, [rsp+58h+arg_8]
0x1800756e8  add     rsp, 50h
0x1800756ec  pop     rdi
0x1800756ed  retn
```
