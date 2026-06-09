# WxIsHvsiContainer

- ea: `0x18004d1a0`
- end: `0x18004d2f1`
- name: `WxIsHvsiContainer`
- size: `337`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18004cde0`

## callees

- `0x18004d1a0`
- `0x1800722f0`
- `0x18009218c`
- `0x180092564`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18004d25b`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18004d25b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18004d2cb`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18004d2cb`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18004d212`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18004d212`

## pseudocode

```c
__int64 WxIsHvsiContainer()
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
    WPP_SF_(1053, 25, WPP_34669277914b3b6bb504f68bf473a142_Traceguids);
  v1 = RegOpenKeyExW(
         HKEY_LOCAL_MACHINE,
         L"SOFTWARE\\Microsoft\\Windows NT\\CurrentVersion\\Containers",
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
    v1 = RegQueryValueExW(hKey, L"SecureAutoProxy", 0, &Type, Data, &cbData);
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
    WPP_SF_dd(1053, 26, WPP_34669277914b3b6bb504f68bf473a142_Traceguids, v0, v1);
  if ( hKey )
    RegCloseKey(hKey);
  return v0;
}

```

## disassembly

```asm
0x18004d1a0  mov     [rsp-8+arg_0], rbx
0x18004d1a5  push    rbp
0x18004d1a6  mov     rbp, rsp
0x18004d1a9  sub     rsp, 60h
0x18004d1ad  mov     rax, cs:__security_cookie
0x18004d1b4  xor     rax, rsp
0x18004d1b7  mov     [rbp+var_10], rax
0x18004d1bb  xor     ebx, ebx
0x18004d1bd  mov     [rbp+var_2C], 0
0x18004d1c4  mov     dword ptr [rbp+Data], ebx
0x18004d1c7  mov     [rbp+Type], ebx
0x18004d1ca  mov     [rbp+hKey], rbx
0x18004d1ce  mov     [rbp+cbData], 4
0x18004d1d5  test    byte ptr cs:xmmword_1800AD720+3, 20h
0x18004d1dc  jz      short loc_18004D1F2
0x18004d1de  lea     edx, [rbx+19h]
0x18004d1e1  mov     ecx, 41Dh
0x18004d1e6  lea     r8, WPP_34669277914b3b6bb504f68bf473a142_Traceguids
0x18004d1ed  call    WPP_SF_
0x18004d1f2  lea     rax, [rbp+hKey]
0x18004d1f6  mov     r9d, 20019h; samDesired
0x18004d1fc  xor     r8d, r8d; ulOptions
0x18004d1ff  mov     [rsp+60h+phkResult], rax; phkResult
0x18004d204  lea     rdx, aSoftwareMicros_3; "SOFTWARE\\Microsoft\\Windows NT\\Curren"...
0x18004d20b  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18004d212  call    cs:__imp_RegOpenKeyExW
0x18004d219  nop     dword ptr [rax+rax+00h]
0x18004d21e  test    eax, eax
0x18004d220  jle     short loc_18004D22C
0x18004d222  movzx   eax, ax
0x18004d225  or      eax, 80070000h
0x18004d22a  test    eax, eax
0x18004d22c  jns     short loc_18004D237
0x18004d22e  mov     [rbp+var_2C], 133h
0x18004d235  jmp     short loc_18004D29C
0x18004d237  mov     rcx, [rbp+hKey]; hKey
0x18004d23b  lea     rax, [rbp+cbData]
0x18004d23f  mov     [rsp+60h+lpcbData], rax; lpcbData
0x18004d244  lea     r9, [rbp+Type]; lpType
0x18004d248  lea     rax, [rbp+Data]
0x18004d24c  xor     r8d, r8d; lpReserved
0x18004d24f  lea     rdx, aSecureautoprox; "SecureAutoProxy"
0x18004d256  mov     [rsp+60h+phkResult], rax; lpData
0x18004d25b  call    cs:__imp_RegQueryValueExW
0x18004d262  nop     dword ptr [rax+rax+00h]
0x18004d267  test    eax, eax
0x18004d269  jle     short loc_18004D275
0x18004d26b  movzx   eax, ax
0x18004d26e  or      eax, 80070000h
0x18004d273  test    eax, eax
0x18004d275  jns     short loc_18004D280
0x18004d277  mov     [rbp+var_2C], 13Ah
0x18004d27e  jmp     short loc_18004D29C
0x18004d280  cmp     [rbp+Type], 4
0x18004d284  jz      short loc_18004D294
0x18004d286  mov     eax, 800703F2h
0x18004d28b  mov     [rbp+var_2C], 13Dh
0x18004d292  jmp     short loc_18004D29C
0x18004d294  xor     eax, eax
0x18004d296  cmp     dword ptr [rbp+Data], eax
0x18004d299  setnz   bl
0x18004d29c  test    byte ptr cs:xmmword_1800AD720+3, 20h
0x18004d2a3  jz      short loc_18004D2C2
0x18004d2a5  mov     edx, 1Ah
0x18004d2aa  mov     dword ptr [rsp+60h+phkResult], eax
0x18004d2ae  mov     ecx, 41Dh
0x18004d2b3  lea     r8, WPP_34669277914b3b6bb504f68bf473a142_Traceguids
0x18004d2ba  mov     r9d, ebx
0x18004d2bd  call    WPP_SF_dd
0x18004d2c2  mov     rcx, [rbp+hKey]; hKey
0x18004d2c6  test    rcx, rcx
0x18004d2c9  jz      short loc_18004D2D7
0x18004d2cb  call    cs:__imp_RegCloseKey
0x18004d2d2  nop     dword ptr [rax+rax+00h]
0x18004d2d7  mov     eax, ebx
0x18004d2d9  mov     rcx, [rbp+var_10]
0x18004d2dd  xor     rcx, rsp; StackCookie
0x18004d2e0  call    __security_check_cookie
0x18004d2e5  mov     rbx, [rsp+60h+arg_0]
0x18004d2ea  add     rsp, 60h
0x18004d2ee  pop     rbp
0x18004d2ef  retn
```
