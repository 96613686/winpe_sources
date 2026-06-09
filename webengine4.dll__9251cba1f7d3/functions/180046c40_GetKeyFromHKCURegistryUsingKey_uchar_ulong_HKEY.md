# GetKeyFromHKCURegistryUsingKey(uchar *,ulong,HKEY__ *)

- ea: `0x180046c40`
- end: `0x180046ed1`
- name: `?GetKeyFromHKCURegistryUsingKey@@YAJPEAEKPEAUHKEY__@@@Z`
- size: `657`
- prototype: `__int64 __fastcall(unsigned __int8 *, size_t Size, HKEY hKey)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, installer_update`

## callers

- `0x180046a40`

## callees

- `0x1800458ec`
- `0x180046c40`
- `0x18004734c`
- `0x1800479c0`
- `0x18004d030`
- `0x18004d350`
- `0x1800653c0`

## import_xrefs

- `KERNEL32!GetSystemTimeAsFileTime` at `0x180046dd4`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x180046e15`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x180046dd4`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x180046e15`
- `ADVAPI32!RegQueryValueExW` at `0x180046cd1`
- `ADVAPI32!RegQueryValueExW` at `0x180046d08`
- `ADVAPI32!RegQueryValueExW` at `0x180046cd1`
- `ADVAPI32!RegQueryValueExW` at `0x180046d08`
- `ADVAPI32!RegSetValueExW` at `0x180046d98`
- `ADVAPI32!RegSetValueExW` at `0x180046dc5`
- `ADVAPI32!RegSetValueExW` at `0x180046dfd`
- `ADVAPI32!RegSetValueExW` at `0x180046e3a`
- `ADVAPI32!RegSetValueExW` at `0x180046e5e`
- `ADVAPI32!RegSetValueExW` at `0x180046e8d`
- `ADVAPI32!RegSetValueExW` at `0x180046d98`
- `ADVAPI32!RegSetValueExW` at `0x180046dc5`
- `ADVAPI32!RegSetValueExW` at `0x180046dfd`
- `ADVAPI32!RegSetValueExW` at `0x180046e3a`
- `ADVAPI32!RegSetValueExW` at `0x180046e5e`
- `ADVAPI32!RegSetValueExW` at `0x180046e8d`

## pseudocode

```c
__int64 __fastcall GetKeyFromHKCURegistryUsingKey(unsigned __int8 *a1, size_t Size, HKEY hKey)
{
  DWORD v4; // esi
  unsigned int v6; // ebx
  DWORD lpcbData; // [rsp+30h] [rbp-D0h] BYREF
  BYTE Data[4]; // [rsp+34h] [rbp-CCh] BYREF
  DWORD cbData; // [rsp+38h] [rbp-C8h] BYREF
  DWORD Type; // [rsp+3Ch] [rbp-C4h] BYREF
  struct _FILETIME SystemTimeAsFileTime; // [rsp+40h] [rbp-C0h] BYREF
  DWORD v13; // [rsp+48h] [rbp-B8h] BYREF
  BYTE lpData[1024]; // [rsp+50h] [rbp-B0h] BYREF

  v4 = Size;
  if ( !a1 || !(_DWORD)Size )
    return 2147942487LL;
  memset_0(lpData, 0, sizeof(lpData));
  lpcbData = 1024;
  cbData = 4;
  if ( RegQueryValueExW(hKey, L"AutoGenKeyFormat", 0, &Type, Data, &cbData)
    || Type != 4
    || RegQueryValueExW(hKey, L"AutoGenKeyV4", 0, &v13, lpData, &lpcbData)
    || !(unsigned int)MachineKeyWasCreatedAfterInstall(hKey)
    || (v6 = UnCryptKeyFromReg(a1, v4, lpData, lpcbData, *(unsigned int *)Data)) != 0 )
  {
    lpcbData = 1024;
    v6 = CryptKeyToStoreInReg(a1, v4, lpData, &lpcbData, (unsigned int *)Data, 0);
    if ( v6
      || RegSetValueExW(hKey, L"AutoGenKeyFormat", 0, 4u, Data, 4u)
      || RegSetValueExW(hKey, L"AutoGenKeyV4", 0, 3u, lpData, lpcbData) )
    {
      *(_DWORD *)Data = 2;
      GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
      if ( RegSetValueExW(hKey, L"AutoGenKeyFormat", 0, 4u, Data, 4u)
        || RegSetValueExW(hKey, L"AutoGenKeyV4", 0, 3u, a1, v4)
        || RegSetValueExW(hKey, L"AutoGenKeyCreationTime", 0, 0xBu, (const BYTE *)&SystemTimeAsFileTime, 8u) )
      {
        return (unsigned int)GetLastWin32Error();
      }
      else
      {
        return 0;
      }
    }
    else
    {
      GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
      RegSetValueExW(hKey, L"AutoGenKeyCreationTime", 0, 0xBu, (const BYTE *)&SystemTimeAsFileTime, 8u);
    }
  }
  return v6;
}

```

## disassembly

```asm
0x180046c40  mov     [rsp-8+arg_18], rbx
0x180046c45  push    rbp
0x180046c46  push    rsi
0x180046c47  push    rdi
0x180046c48  push    r14
0x180046c4a  push    r15
0x180046c4c  lea     rbp, [rsp-360h]
0x180046c54  sub     rsp, 460h
0x180046c5b  mov     rax, cs:__security_cookie
0x180046c62  xor     rax, rsp
0x180046c65  mov     [rbp+380h+var_30], rax
0x180046c6c  mov     rdi, r8
0x180046c6f  mov     esi, edx
0x180046c71  mov     r14, rcx
0x180046c74  test    rcx, rcx
0x180046c77  jz      loc_180046EA6
0x180046c7d  cmp     edx, 1
0x180046c80  jb      loc_180046EA6
0x180046c86  xor     edx, edx; Val
0x180046c88  lea     rcx, [rsp+480h+var_430]; void *
0x180046c8d  mov     r8d, 400h; Size
0x180046c93  call    memset_0
0x180046c98  lea     rax, [rsp+480h+cbData]
0x180046c9d  mov     [rsp+480h+var_450], 400h
0x180046ca5  mov     [rsp+480h+lpcbData], rax; lpcbData
0x180046caa  lea     r9, [rsp+480h+Type]; lpType
0x180046caf  lea     rax, [rsp+480h+Data]
0x180046cb4  mov     r15d, 4
0x180046cba  xor     r8d, r8d; lpReserved
0x180046cbd  mov     [rsp+480h+lpData], rax; lpData
0x180046cc2  lea     rdx, aAutogenkeyform; "AutoGenKeyFormat"
0x180046cc9  mov     [rsp+480h+cbData], r15d
0x180046cce  mov     rcx, rdi; hKey
0x180046cd1  call    cs:__imp_RegQueryValueExW
0x180046cd7  test    eax, eax
0x180046cd9  jnz     short loc_180046D44
0x180046cdb  cmp     [rsp+480h+Type], r15d
0x180046ce0  jnz     short loc_180046D44
0x180046ce2  lea     rax, [rsp+480h+var_450]
0x180046ce7  xor     r8d, r8d; lpReserved
0x180046cea  mov     [rsp+480h+lpcbData], rax; int
0x180046cef  lea     r9, [rsp+480h+var_438]; lpType
0x180046cf4  lea     rax, [rsp+480h+var_430]
0x180046cf9  mov     rcx, rdi; hKey
0x180046cfc  lea     rdx, aAutogenkeyv4; "AutoGenKeyV4"
0x180046d03  mov     [rsp+480h+lpData], rax; lpData
0x180046d08  call    cs:__imp_RegQueryValueExW
0x180046d0e  test    eax, eax
0x180046d10  jnz     short loc_180046D44
0x180046d12  mov     rcx, rdi; hKey
0x180046d15  call    ?MachineKeyWasCreatedAfterInstall@@YAHPEAUHKEY__@@@Z; MachineKeyWasCreatedAfterInstall(HKEY__ *)
0x180046d1a  test    eax, eax
0x180046d1c  jz      short loc_180046D44
0x180046d1e  mov     eax, dword ptr [rsp+480h+Data]
0x180046d22  lea     r8, [rsp+480h+var_430]; unsigned __int8 *
0x180046d27  mov     r9d, [rsp+480h+var_450]; unsigned int
0x180046d2c  mov     edx, esi; Size
0x180046d2e  mov     rcx, r14; unsigned __int8 *
0x180046d31  mov     dword ptr [rsp+480h+lpData], eax; unsigned int
0x180046d35  call    ?UnCryptKeyFromReg@@YAJPEAEK0KK@Z; UnCryptKeyFromReg(uchar *,ulong,uchar *,ulong,ulong)
0x180046d3a  mov     ebx, eax
0x180046d3c  test    eax, eax
0x180046d3e  jz      loc_180046EA2
0x180046d44  and     dword ptr [rsp+480h+lpcbData], 0
0x180046d49  lea     rax, [rsp+480h+Data]
0x180046d4e  lea     r9, [rsp+480h+var_450]; unsigned int *
0x180046d53  mov     [rsp+480h+lpData], rax; unsigned int *
0x180046d58  lea     r8, [rsp+480h+var_430]; unsigned __int8 *
0x180046d5d  mov     [rsp+480h+var_450], 400h
0x180046d65  mov     edx, esi; Size
0x180046d67  mov     rcx, r14; Src
0x180046d6a  call    ?CryptKeyToStoreInReg@@YAJPEAEK0PEAK1H@Z; CryptKeyToStoreInReg(uchar *,ulong,uchar *,ulong *,ulong *,int)
0x180046d6f  mov     ebx, eax
0x180046d71  test    eax, eax
0x180046d73  jnz     loc_180046E08
0x180046d79  lea     rax, [rsp+480h+Data]
0x180046d7e  mov     dword ptr [rsp+480h+lpcbData], r15d; cbData
0x180046d83  mov     r9d, r15d; dwType
0x180046d86  mov     [rsp+480h+lpData], rax; lpData
0x180046d8b  xor     r8d, r8d; Reserved
0x180046d8e  lea     rdx, aAutogenkeyform; "AutoGenKeyFormat"
0x180046d95  mov     rcx, rdi; hKey
0x180046d98  call    cs:__imp_RegSetValueExW
0x180046d9e  test    eax, eax
0x180046da0  jnz     short loc_180046E08
0x180046da2  mov     eax, [rsp+480h+var_450]
0x180046da6  lea     r9d, [rbx+3]; dwType
0x180046daa  mov     dword ptr [rsp+480h+lpcbData], eax; cbData
0x180046dae  lea     rdx, aAutogenkeyv4; "AutoGenKeyV4"
0x180046db5  lea     rax, [rsp+480h+var_430]
0x180046dba  xor     r8d, r8d; Reserved
0x180046dbd  mov     rcx, rdi; hKey
0x180046dc0  mov     [rsp+480h+lpData], rax; lpData
0x180046dc5  call    cs:__imp_RegSetValueExW
0x180046dcb  test    eax, eax
0x180046dcd  jnz     short loc_180046E08
0x180046dcf  lea     rcx, [rsp+480h+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x180046dd4  call    cs:__imp_GetSystemTimeAsFileTime
0x180046dda  lea     rax, [rsp+480h+SystemTimeAsFileTime]
0x180046ddf  mov     dword ptr [rsp+480h+lpcbData], 8; cbData
0x180046de7  lea     r9d, [rbx+0Bh]; dwType
0x180046deb  mov     [rsp+480h+lpData], rax; lpData
0x180046df0  xor     r8d, r8d; Reserved
0x180046df3  lea     rdx, aAutogenkeycrea; "AutoGenKeyCreationTime"
0x180046dfa  mov     rcx, rdi; hKey
0x180046dfd  call    cs:__imp_RegSetValueExW
0x180046e03  jmp     loc_180046EA2
0x180046e08  lea     rcx, [rsp+480h+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x180046e0d  mov     dword ptr [rsp+480h+Data], 2
0x180046e15  call    cs:__imp_GetSystemTimeAsFileTime
0x180046e1b  lea     rax, [rsp+480h+Data]
0x180046e20  mov     dword ptr [rsp+480h+lpcbData], r15d; cbData
0x180046e25  mov     r9d, r15d; dwType
0x180046e28  mov     [rsp+480h+lpData], rax; lpData
0x180046e2d  xor     r8d, r8d; Reserved
0x180046e30  lea     rdx, aAutogenkeyform; "AutoGenKeyFormat"
0x180046e37  mov     rcx, rdi; hKey
0x180046e3a  call    cs:__imp_RegSetValueExW
0x180046e40  test    eax, eax
0x180046e42  jnz     short loc_180046E9B
0x180046e44  mov     dword ptr [rsp+480h+lpcbData], esi; cbData
0x180046e48  lea     r9d, [rax+3]; dwType
0x180046e4c  xor     r8d, r8d; Reserved
0x180046e4f  mov     [rsp+480h+lpData], r14; lpData
0x180046e54  lea     rdx, aAutogenkeyv4; "AutoGenKeyV4"
0x180046e5b  mov     rcx, rdi; hKey
0x180046e5e  call    cs:__imp_RegSetValueExW
0x180046e64  test    eax, eax
0x180046e66  jnz     short loc_180046E9B
0x180046e68  lea     rax, [rsp+480h+SystemTimeAsFileTime]
0x180046e6d  mov     dword ptr [rsp+480h+lpcbData], 8; cbData
0x180046e75  mov     r9d, 0Bh; dwType
0x180046e7b  mov     [rsp+480h+lpData], rax; lpData
0x180046e80  xor     r8d, r8d; Reserved
0x180046e83  lea     rdx, aAutogenkeycrea; "AutoGenKeyCreationTime"
0x180046e8a  mov     rcx, rdi; hKey
0x180046e8d  call    cs:__imp_RegSetValueExW
0x180046e93  test    eax, eax
0x180046e95  jnz     short loc_180046E9B
0x180046e97  xor     ebx, ebx
0x180046e99  jmp     short loc_180046EA2
0x180046e9b  call    ?GetLastWin32Error@@YAJXZ; GetLastWin32Error(void)
0x180046ea0  mov     ebx, eax
0x180046ea2  mov     eax, ebx
0x180046ea4  jmp     short loc_180046EAB
0x180046ea6  mov     eax, 80070057h
0x180046eab  mov     rcx, [rbp+380h+var_30]
0x180046eb2  xor     rcx, rsp; StackCookie
0x180046eb5  call    __security_check_cookie
0x180046eba  mov     rbx, [rsp+480h+arg_18]
0x180046ec2  add     rsp, 460h
0x180046ec9  pop     r15
0x180046ecb  pop     r14
0x180046ecd  pop     rdi
0x180046ece  pop     rsi
0x180046ecf  pop     rbp
0x180046ed0  retn
```
