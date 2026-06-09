# WxIsHvsiContainerOverride

- ea: `0x180070dbc`
- end: `0x180070f14`
- name: `WxIsHvsiContainerOverride`
- size: `344`
- prototype: ``
- caller_count: `3`
- callee_count: `4`
- tags: `registry_config, service_task`

## callers

- `0x180013778`
- `0x180070b2c`
- `0x180070cfc`

## callees

- `0x180070dbc`
- `0x1800a1d10`
- `0x1800cf008`
- `0x1800cf4c4`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180070e94`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180070e94`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180070e1e`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180070e1e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180070e51`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180070e51`

## string_xrefs

- `0x180070e10`: `SYSTEM\CurrentControlSet\Services\Dnscache\Parameters\dnscache`

## pseudocode

```c
__int64 WxIsHvsiContainerOverride()
{
  unsigned int v0; // ebx
  LSTATUS v1; // eax
  bool v2; // sf
  LSTATUS v4; // eax
  bool v5; // sf
  DWORD Type; // [rsp+38h] [rbp-28h] BYREF
  BYTE Data[4]; // [rsp+3Ch] [rbp-24h] BYREF
  DWORD cbData; // [rsp+40h] [rbp-20h] BYREF
  HKEY hKey; // [rsp+48h] [rbp-18h] BYREF

  v0 = 0;
  *(_DWORD *)Data = 0;
  Type = 0;
  hKey = 0;
  cbData = 4;
  if ( (BYTE3(xmmword_180107A60) & 0x20) != 0 )
    WPP_SF_(1053, 27, WPP_34669277914b3b6bb504f68bf473a142_Traceguids);
  v1 = RegOpenKeyExW(
         HKEY_LOCAL_MACHINE,
         L"SYSTEM\\CurrentControlSet\\Services\\Dnscache\\Parameters\\dnscache",
         0,
         0x20019u,
         &hKey);
  v2 = v1 < 0;
  if ( v1 > 0 )
    v2 = 1;
  if ( !v2 )
  {
    v4 = RegQueryValueExW(hKey, L"IsHvsiContainerOverride", 0, &Type, Data, &cbData);
    v5 = v4 < 0;
    if ( v4 > 0 )
      v5 = 1;
    if ( !v5 && Type == 4 )
      LOBYTE(v0) = *(_DWORD *)Data != 0;
  }
  if ( (BYTE3(xmmword_180107A60) & 0x20) != 0 )
    WPP_SF_Dd(1053, 28, WPP_34669277914b3b6bb504f68bf473a142_Traceguids, v0);
  if ( hKey )
    RegCloseKey(hKey);
  return v0;
}

```

## disassembly

```asm
0x180070dbc  mov     [rsp-8+arg_0], rbx
0x180070dc1  push    rbp
0x180070dc2  mov     rbp, rsp
0x180070dc5  sub     rsp, 60h
0x180070dc9  mov     rax, cs:__security_cookie
0x180070dd0  xor     rax, rsp
0x180070dd3  mov     [rbp+var_10], rax
0x180070dd7  xor     ebx, ebx
0x180070dd9  mov     [rbp+var_2C], 0
0x180070de0  mov     dword ptr [rbp+Data], ebx
0x180070de3  mov     [rbp+Type], ebx
0x180070de6  mov     [rbp+hKey], rbx
0x180070dea  mov     [rbp+cbData], 4
0x180070df1  test    byte ptr cs:xmmword_180107A60+3, 20h
0x180070df8  jnz     loc_180070EB3
0x180070dfe  lea     rax, [rbp+hKey]
0x180070e02  mov     r9d, 20019h; samDesired
0x180070e08  xor     r8d, r8d; ulOptions
0x180070e0b  mov     [rsp+60h+phkResult], rax; phkResult
0x180070e10  lea     rdx, aSystemCurrentc_1; "SYSTEM\\CurrentControlSet\\Services\\Dn"...
0x180070e17  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180070e1e  call    cs:__imp_RegOpenKeyExW
0x180070e24  test    eax, eax
0x180070e26  jle     short loc_180070E32
0x180070e28  movzx   eax, ax
0x180070e2b  or      eax, 80070000h
0x180070e30  test    eax, eax
0x180070e32  jns     short loc_180070E70
0x180070e34  mov     [rbp+var_2C], 173h
0x180070e3b  test    byte ptr cs:xmmword_180107A60+3, 20h
0x180070e42  jnz     loc_180070EF2
0x180070e48  mov     rcx, [rbp+hKey]; hKey
0x180070e4c  test    rcx, rcx
0x180070e4f  jz      short loc_180070E57
0x180070e51  call    cs:__imp_RegCloseKey
0x180070e57  mov     eax, ebx
0x180070e59  mov     rcx, [rbp+var_10]
0x180070e5d  xor     rcx, rsp; StackCookie
0x180070e60  call    __security_check_cookie
0x180070e65  mov     rbx, [rsp+60h+arg_0]
0x180070e6a  add     rsp, 60h
0x180070e6e  pop     rbp
0x180070e6f  retn
0x180070e70  mov     rcx, [rbp+hKey]; hKey
0x180070e74  lea     rax, [rbp+cbData]
0x180070e78  mov     [rsp+60h+lpcbData], rax; lpcbData
0x180070e7d  lea     r9, [rbp+Type]; lpType
0x180070e81  lea     rax, [rbp+Data]
0x180070e85  xor     r8d, r8d; lpReserved
0x180070e88  lea     rdx, aIshvsicontaine; "IsHvsiContainerOverride"
0x180070e8f  mov     [rsp+60h+phkResult], rax; lpData
0x180070e94  call    cs:__imp_RegQueryValueExW
0x180070e9a  test    eax, eax
0x180070e9c  jle     short loc_180070EA8
0x180070e9e  movzx   eax, ax
0x180070ea1  or      eax, 80070000h
0x180070ea6  test    eax, eax
0x180070ea8  jns     short loc_180070ECE
0x180070eaa  mov     [rbp+var_2C], 17Ah
0x180070eb1  jmp     short loc_180070E3B
0x180070eb3  mov     edx, 1Bh
0x180070eb8  lea     r8, WPP_34669277914b3b6bb504f68bf473a142_Traceguids
0x180070ebf  mov     ecx, 41Dh
0x180070ec4  call    WPP_SF_
0x180070ec9  jmp     loc_180070DFE
0x180070ece  cmp     [rbp+Type], 4
0x180070ed2  jz      short loc_180070EE5
0x180070ed4  mov     eax, 800703F2h
0x180070ed9  mov     [rbp+var_2C], 17Dh
0x180070ee0  jmp     loc_180070E3B
0x180070ee5  xor     eax, eax
0x180070ee7  cmp     dword ptr [rbp+Data], eax
0x180070eea  setnz   bl
0x180070eed  jmp     loc_180070E3B
0x180070ef2  mov     edx, 1Ch
0x180070ef7  mov     dword ptr [rsp+60h+phkResult], eax
0x180070efb  mov     ecx, 41Dh
0x180070f00  lea     r8, WPP_34669277914b3b6bb504f68bf473a142_Traceguids
0x180070f07  mov     r9d, ebx
0x180070f0a  call    WPP_SF_Dd
0x180070f0f  jmp     loc_180070E48
```
