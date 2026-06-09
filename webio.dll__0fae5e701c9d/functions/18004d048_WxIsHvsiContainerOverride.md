# WxIsHvsiContainerOverride

- ea: `0x18004d048`
- end: `0x18004d199`
- name: `WxIsHvsiContainerOverride`
- size: `337`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, service_task`

## callers

- `0x18004cde0`

## callees

- `0x18004d048`
- `0x1800722f0`
- `0x18009218c`
- `0x180092564`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18004d103`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18004d103`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18004d173`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18004d173`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18004d0ba`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18004d0ba`

## string_xrefs

- `0x18004d0ac`: `SYSTEM\CurrentControlSet\Services\Dnscache\Parameters\dnscache`

## pseudocode

```c
__int64 WxIsHvsiContainerOverride()
{
  unsigned int v0; // ebx
  int v1; // eax
  bool v2; // sf
  bool v3; // sf
  DWORD Type; // [rsp+38h] [rbp-28h] BYREF
  BYTE Data[4]; // [rsp+3Ch] [rbp-24h] BYREF
  DWORD cbData; // [rsp+40h] [rbp-20h] BYREF
  HKEY hKey; // [rsp+48h] [rbp-18h] BYREF

  v0 = 0;
  *(_DWORD *)Data = 0;
  Type = 0;
  hKey = 0;
  cbData = 4;
  if ( (BYTE3(xmmword_1800AD720) & 0x20) != 0 )
    WPP_SF_(1053, 27, WPP_34669277914b3b6bb504f68bf473a142_Traceguids);
  v1 = RegOpenKeyExW(
         HKEY_LOCAL_MACHINE,
         L"SYSTEM\\CurrentControlSet\\Services\\Dnscache\\Parameters\\dnscache",
         0,
         0x20019u,
         &hKey);
  v2 = v1 < 0;
  if ( v1 > 0 )
  {
    v1 = (unsigned __int16)v1 | 0x80070000;
    v2 = v1 < 0;
  }
  if ( !v2 )
  {
    v1 = RegQueryValueExW(hKey, L"IsHvsiContainerOverride", 0, &Type, Data, &cbData);
    v3 = v1 < 0;
    if ( v1 > 0 )
    {
      v1 = (unsigned __int16)v1 | 0x80070000;
      v3 = v1 < 0;
    }
    if ( !v3 )
    {
      if ( Type == 4 )
      {
        v1 = 0;
        LOBYTE(v0) = *(_DWORD *)Data != 0;
      }
      else
      {
        v1 = -2147023886;
      }
    }
  }
  if ( (BYTE3(xmmword_1800AD720) & 0x20) != 0 )
    WPP_SF_dd(1053, 28, WPP_34669277914b3b6bb504f68bf473a142_Traceguids, v0, v1);
  if ( hKey )
    RegCloseKey(hKey);
  return v0;
}

```

## disassembly

```asm
0x18004d048  mov     [rsp-8+arg_0], rbx
0x18004d04d  push    rbp
0x18004d04e  mov     rbp, rsp
0x18004d051  sub     rsp, 60h
0x18004d055  mov     rax, cs:__security_cookie
0x18004d05c  xor     rax, rsp
0x18004d05f  mov     [rbp+var_10], rax
0x18004d063  xor     ebx, ebx
0x18004d065  mov     [rbp+var_2C], 0
0x18004d06c  mov     dword ptr [rbp+Data], ebx
0x18004d06f  mov     [rbp+Type], ebx
0x18004d072  mov     [rbp+hKey], rbx
0x18004d076  mov     [rbp+cbData], 4
0x18004d07d  test    byte ptr cs:xmmword_1800AD720+3, 20h
0x18004d084  jz      short loc_18004D09A
0x18004d086  lea     edx, [rbx+1Bh]
0x18004d089  mov     ecx, 41Dh
0x18004d08e  lea     r8, WPP_34669277914b3b6bb504f68bf473a142_Traceguids
0x18004d095  call    WPP_SF_
0x18004d09a  lea     rax, [rbp+hKey]
0x18004d09e  mov     r9d, 20019h; samDesired
0x18004d0a4  xor     r8d, r8d; ulOptions
0x18004d0a7  mov     [rsp+60h+phkResult], rax; phkResult
0x18004d0ac  lea     rdx, aSystemCurrentc; "SYSTEM\\CurrentControlSet\\Services\\Dn"...
0x18004d0b3  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18004d0ba  call    cs:__imp_RegOpenKeyExW
0x18004d0c1  nop     dword ptr [rax+rax+00h]
0x18004d0c6  test    eax, eax
0x18004d0c8  jle     short loc_18004D0D4
0x18004d0ca  movzx   eax, ax
0x18004d0cd  or      eax, 80070000h
0x18004d0d2  test    eax, eax
0x18004d0d4  jns     short loc_18004D0DF
0x18004d0d6  mov     [rbp+var_2C], 173h
0x18004d0dd  jmp     short loc_18004D144
0x18004d0df  mov     rcx, [rbp+hKey]; hKey
0x18004d0e3  lea     rax, [rbp+cbData]
0x18004d0e7  mov     [rsp+60h+lpcbData], rax; lpcbData
0x18004d0ec  lea     r9, [rbp+Type]; lpType
0x18004d0f0  lea     rax, [rbp+Data]
0x18004d0f4  xor     r8d, r8d; lpReserved
0x18004d0f7  lea     rdx, aIshvsicontaine; "IsHvsiContainerOverride"
0x18004d0fe  mov     [rsp+60h+phkResult], rax; lpData
0x18004d103  call    cs:__imp_RegQueryValueExW
0x18004d10a  nop     dword ptr [rax+rax+00h]
0x18004d10f  test    eax, eax
0x18004d111  jle     short loc_18004D11D
0x18004d113  movzx   eax, ax
0x18004d116  or      eax, 80070000h
0x18004d11b  test    eax, eax
0x18004d11d  jns     short loc_18004D128
0x18004d11f  mov     [rbp+var_2C], 17Ah
0x18004d126  jmp     short loc_18004D144
0x18004d128  cmp     [rbp+Type], 4
0x18004d12c  jz      short loc_18004D13C
0x18004d12e  mov     eax, 800703F2h
0x18004d133  mov     [rbp+var_2C], 17Dh
0x18004d13a  jmp     short loc_18004D144
0x18004d13c  xor     eax, eax
0x18004d13e  cmp     dword ptr [rbp+Data], eax
0x18004d141  setnz   bl
0x18004d144  test    byte ptr cs:xmmword_1800AD720+3, 20h
0x18004d14b  jz      short loc_18004D16A
0x18004d14d  mov     edx, 1Ch
0x18004d152  mov     dword ptr [rsp+60h+phkResult], eax
0x18004d156  mov     ecx, 41Dh
0x18004d15b  lea     r8, WPP_34669277914b3b6bb504f68bf473a142_Traceguids
0x18004d162  mov     r9d, ebx
0x18004d165  call    WPP_SF_dd
0x18004d16a  mov     rcx, [rbp+hKey]; hKey
0x18004d16e  test    rcx, rcx
0x18004d171  jz      short loc_18004D17F
0x18004d173  call    cs:__imp_RegCloseKey
0x18004d17a  nop     dword ptr [rax+rax+00h]
0x18004d17f  mov     eax, ebx
0x18004d181  mov     rcx, [rbp+var_10]
0x18004d185  xor     rcx, rsp; StackCookie
0x18004d188  call    __security_check_cookie
0x18004d18d  mov     rbx, [rsp+60h+arg_0]
0x18004d192  add     rsp, 60h
0x18004d196  pop     rbp
0x18004d197  retn
```
