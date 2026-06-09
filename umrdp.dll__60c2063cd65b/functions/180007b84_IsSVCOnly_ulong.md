# IsSVCOnly(ulong)

- ea: `0x180007b84`
- end: `0x180007cbb`
- name: `?IsSVCOnly@@YAHK@Z`
- size: `311`
- prototype: `__int64 __fastcall(unsigned int)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x1800072f0`

## callees

- `0x180007b84`
- `0x180009fa8`
- `0x1800134cc`
- `0x180047ef0`

## import_xrefs

- `msvcrt!wcsrchr` at `0x180007bdf`
- `msvcrt!wcsrchr` at `0x180007bdf`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180007c43`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180007c43`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180007c75`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180007c75`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180007c93`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180007c93`
- `WINSTA!WinStationNameFromLogonIdW` at `0x180007bc9`
- `WINSTA!WinStationNameFromLogonIdW` at `0x180007bc9`

## pseudocode

```c
_BOOL8 __fastcall IsSVCOnly(unsigned int a1)
{
  BOOL v1; // ebx
  wchar_t *v2; // rax
  unsigned int v3; // r11d
  BYTE Data[4]; // [rsp+30h] [rbp-D0h] BYREF
  DWORD cbData; // [rsp+34h] [rbp-CCh] BYREF
  DWORD Type; // [rsp+38h] [rbp-C8h] BYREF
  HKEY hKey; // [rsp+40h] [rbp-C0h] BYREF
  wchar_t Str[40]; // [rsp+50h] [rbp-B0h] BYREF
  WCHAR SubKey[264]; // [rsp+A0h] [rbp-60h] BYREF

  v1 = 0;
  hKey = 0;
  *(_DWORD *)Data = 0;
  Type = 4;
  cbData = 4;
  if ( (unsigned __int8)WinStationNameFromLogonIdW(0, a1, Str) )
  {
    v2 = wcsrchr(Str, 0x23u);
    if ( v2 )
    {
      *v2 = 0;
      if ( !(unsigned int)StringCchCopyW(
                            SubKey,
                            0x104u,
                            L"System\\CurrentControlSet\\Control\\Terminal Server\\WinStations\\")
        && !StringCchCatW(SubKey, v3, Str)
        && !RegOpenKeyExW(HKEY_LOCAL_MACHINE, SubKey, 0, 0x20019u, &hKey)
        && !RegQueryValueExW(hKey, L"ForceAudioSVC", 0, &Type, Data, &cbData) )
      {
        v1 = *(_DWORD *)Data == 1;
      }
    }
  }
  if ( hKey )
    RegCloseKey(hKey);
  return v1;
}

```

## disassembly

```asm
0x180007b84  mov     [rsp-8+arg_8], rbx
0x180007b89  push    rbp
0x180007b8a  lea     rbp, [rsp-1C0h]
0x180007b92  sub     rsp, 2C0h
0x180007b99  mov     rax, cs:__security_cookie
0x180007ba0  xor     rax, rsp
0x180007ba3  mov     [rbp+1C0h+var_10], rax
0x180007baa  xor     ebx, ebx
0x180007bac  lea     r8, [rsp+2C0h+Str]
0x180007bb1  mov     edx, ecx
0x180007bb3  mov     [rsp+2C0h+hKey], rbx
0x180007bb8  xor     ecx, ecx
0x180007bba  mov     dword ptr [rsp+2C0h+Data], ebx
0x180007bbe  lea     eax, [rbx+4]
0x180007bc1  mov     [rsp+2C0h+Type], eax
0x180007bc5  mov     [rsp+2C0h+cbData], eax
0x180007bc9  call    cs:__imp_WinStationNameFromLogonIdW
0x180007bcf  test    al, al
0x180007bd1  jz      loc_180007C89
0x180007bd7  lea     edx, [rbx+23h]; Ch
0x180007bda  lea     rcx, [rsp+2C0h+Str]; Str
0x180007bdf  call    cs:__imp_wcsrchr
0x180007be5  test    rax, rax
0x180007be8  jz      loc_180007C89
0x180007bee  xor     ecx, ecx
0x180007bf0  lea     r8, aSystemCurrentc_4; "System\\CurrentControlSet\\Control\\Ter"...
0x180007bf7  mov     [rax], cx
0x180007bfa  mov     r11d, 104h
0x180007c00  lea     rcx, [rbp+1C0h+SubKey]; unsigned __int16 *
0x180007c04  mov     edx, r11d; unsigned __int64
0x180007c07  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180007c0c  test    eax, eax
0x180007c0e  jnz     short loc_180007C89
0x180007c10  lea     r8, [rsp+2C0h+Str]; unsigned __int16 *
0x180007c15  mov     edx, r11d; unsigned __int64
0x180007c18  lea     rcx, [rbp+1C0h+SubKey]; unsigned __int16 *
0x180007c1c  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180007c21  test    eax, eax
0x180007c23  jnz     short loc_180007C89
0x180007c25  lea     rax, [rsp+2C0h+hKey]
0x180007c2a  mov     r9d, 20019h; samDesired
0x180007c30  xor     r8d, r8d; ulOptions
0x180007c33  mov     [rsp+2C0h+phkResult], rax; phkResult
0x180007c38  lea     rdx, [rbp+1C0h+SubKey]; lpSubKey
0x180007c3c  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180007c43  call    cs:__imp_RegOpenKeyExW
0x180007c49  test    eax, eax
0x180007c4b  jnz     short loc_180007C89
0x180007c4d  mov     rcx, [rsp+2C0h+hKey]; hKey
0x180007c52  lea     rax, [rsp+2C0h+cbData]
0x180007c57  mov     [rsp+2C0h+lpcbData], rax; lpcbData
0x180007c5c  lea     r9, [rsp+2C0h+Type]; lpType
0x180007c61  lea     rax, [rsp+2C0h+Data]
0x180007c66  xor     r8d, r8d; lpReserved
0x180007c69  lea     rdx, ValueName; "ForceAudioSVC"
0x180007c70  mov     [rsp+2C0h+phkResult], rax; lpData
0x180007c75  call    cs:__imp_RegQueryValueExW
0x180007c7b  test    eax, eax
0x180007c7d  jnz     short loc_180007C89
0x180007c7f  lea     eax, [rbx+1]
0x180007c82  cmp     dword ptr [rsp+2C0h+Data], eax
0x180007c86  cmovz   ebx, eax
0x180007c89  mov     rcx, [rsp+2C0h+hKey]; hKey
0x180007c8e  test    rcx, rcx
0x180007c91  jz      short loc_180007C99
0x180007c93  call    cs:__imp_RegCloseKey
0x180007c99  mov     eax, ebx
0x180007c9b  mov     rcx, [rbp+1C0h+var_10]
0x180007ca2  xor     rcx, rsp; StackCookie
0x180007ca5  call    __security_check_cookie
0x180007caa  mov     rbx, [rsp+2C0h+arg_8]
0x180007cb2  add     rsp, 2C0h
0x180007cb9  pop     rbp
0x180007cba  retn
```
