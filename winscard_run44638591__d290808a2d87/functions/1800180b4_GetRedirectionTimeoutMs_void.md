# _GetRedirectionTimeoutMs(void)

- ea: `0x1800180b4`
- end: `0x180018169`
- name: `?_GetRedirectionTimeoutMs@@YAKXZ`
- size: `181`
- prototype: `unsigned int(void)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800190cc`

## callees

- `0x1800180b4`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180018143`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180018143`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180018128`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180018128`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800180fa`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800180fa`

## pseudocode

```c
__int64 _GetRedirectionTimeoutMs(void)
{
  __int64 result; // rax
  unsigned int Data; // [rsp+40h] [rbp+10h] BYREF
  DWORD Type; // [rsp+48h] [rbp+18h] BYREF
  DWORD cbData; // [rsp+50h] [rbp+20h] BYREF
  HKEY hKey; // [rsp+58h] [rbp+28h] BYREF

  hKey = 0;
  Data = 5000;
  Type = 4;
  cbData = 4;
  if ( !RegOpenKeyExW(
          HKEY_LOCAL_MACHINE,
          L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\SmartCardRedirection",
          0,
          0x20019u,
          &hKey) )
  {
    if ( RegQueryValueExW(hKey, L"TimeoutMs", 0, &Type, (LPBYTE)&Data, &cbData) || Type != 4 )
      Data = 5000;
    RegCloseKey(hKey);
  }
  result = Data;
  if ( Data < 0x64 )
    return 100;
  if ( Data > 0xEA60 )
    return 60000;
  return result;
}

```

## disassembly

```asm
0x1800180b4  push    rbp
0x1800180b6  mov     rbp, rsp
0x1800180b9  sub     rsp, 30h
0x1800180bd  lea     rax, [rbp+hKey]
0x1800180c1  mov     [rbp+hKey], 0
0x1800180c9  mov     r9d, 20019h; samDesired
0x1800180cf  mov     [rsp+30h+phkResult], rax; phkResult
0x1800180d4  xor     r8d, r8d; ulOptions
0x1800180d7  mov     [rbp+Data], 1388h
0x1800180de  lea     rdx, SubKey; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x1800180e5  mov     [rbp+Type], 4
0x1800180ec  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800180f3  mov     [rbp+cbData], 4
0x1800180fa  call    cs:__imp_RegOpenKeyExW
0x180018100  test    eax, eax
0x180018102  jnz     short loc_180018149
0x180018104  mov     rcx, [rbp+hKey]; hKey
0x180018108  lea     rax, [rbp+cbData]
0x18001810c  mov     [rsp+30h+lpcbData], rax; lpcbData
0x180018111  lea     r9, [rbp+Type]; lpType
0x180018115  lea     rax, [rbp+Data]
0x180018119  xor     r8d, r8d; lpReserved
0x18001811c  lea     rdx, aTimeoutms; "TimeoutMs"
0x180018123  mov     [rsp+30h+phkResult], rax; lpData
0x180018128  call    cs:__imp_RegQueryValueExW
0x18001812e  test    eax, eax
0x180018130  jnz     short loc_180018138
0x180018132  cmp     [rbp+Type], 4
0x180018136  jz      short loc_18001813F
0x180018138  mov     [rbp+Data], 1388h
0x18001813f  mov     rcx, [rbp+hKey]; hKey
0x180018143  call    cs:__imp_RegCloseKey
0x180018149  mov     eax, [rbp+Data]
0x18001814c  cmp     eax, 64h ; 'd'
0x18001814f  jnb     short loc_180018158
0x180018151  mov     eax, 64h ; 'd'
0x180018156  jmp     short loc_180018163
0x180018158  mov     ecx, 0EA60h
0x18001815d  cmp     eax, ecx
0x18001815f  jbe     short loc_180018163
0x180018161  mov     eax, ecx
0x180018163  add     rsp, 30h
0x180018167  pop     rbp
0x180018168  retn
```
