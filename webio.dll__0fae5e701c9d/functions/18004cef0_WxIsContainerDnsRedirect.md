# WxIsContainerDnsRedirect

- ea: `0x18004cef0`
- end: `0x18004d041`
- name: `WxIsContainerDnsRedirect`
- size: `337`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18004cde0`

## callees

- `0x18004cef0`
- `0x1800722f0`
- `0x18009218c`
- `0x180092564`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18004cfab`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18004cfab`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18004d01b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18004d01b`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18004cf62`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18004cf62`

## pseudocode

```c
__int64 WxIsContainerDnsRedirect()
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
    WPP_SF_(1053, 29, WPP_34669277914b3b6bb504f68bf473a142_Traceguids);
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
    v1 = RegQueryValueExW(hKey, L"SendDnsToHost", 0, &Type, Data, &cbData);
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
    WPP_SF_dd(1053, 30, WPP_34669277914b3b6bb504f68bf473a142_Traceguids, v0, v1);
  if ( hKey )
    RegCloseKey(hKey);
  return v0;
}

```

## disassembly

```asm
0x18004cef0  mov     [rsp-8+arg_0], rbx
0x18004cef5  push    rbp
0x18004cef6  mov     rbp, rsp
0x18004cef9  sub     rsp, 60h
0x18004cefd  mov     rax, cs:__security_cookie
0x18004cf04  xor     rax, rsp
0x18004cf07  mov     [rbp+var_10], rax
0x18004cf0b  xor     ebx, ebx
0x18004cf0d  mov     [rbp+var_2C], 0
0x18004cf14  mov     dword ptr [rbp+Data], ebx
0x18004cf17  mov     [rbp+Type], ebx
0x18004cf1a  mov     [rbp+hKey], rbx
0x18004cf1e  mov     [rbp+cbData], 4
0x18004cf25  test    byte ptr cs:xmmword_1800AD720+3, 20h
0x18004cf2c  jz      short loc_18004CF42
0x18004cf2e  lea     edx, [rbx+1Dh]
0x18004cf31  mov     ecx, 41Dh
0x18004cf36  lea     r8, WPP_34669277914b3b6bb504f68bf473a142_Traceguids
0x18004cf3d  call    WPP_SF_
0x18004cf42  lea     rax, [rbp+hKey]
0x18004cf46  mov     r9d, 20019h; samDesired
0x18004cf4c  xor     r8d, r8d; ulOptions
0x18004cf4f  mov     [rsp+60h+phkResult], rax; phkResult
0x18004cf54  lea     rdx, aSoftwareMicros_3; "SOFTWARE\\Microsoft\\Windows NT\\Curren"...
0x18004cf5b  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18004cf62  call    cs:__imp_RegOpenKeyExW
0x18004cf69  nop     dword ptr [rax+rax+00h]
0x18004cf6e  test    eax, eax
0x18004cf70  jle     short loc_18004CF7C
0x18004cf72  movzx   eax, ax
0x18004cf75  or      eax, 80070000h
0x18004cf7a  test    eax, eax
0x18004cf7c  jns     short loc_18004CF87
0x18004cf7e  mov     [rbp+var_2C], 19Bh
0x18004cf85  jmp     short loc_18004CFEC
0x18004cf87  mov     rcx, [rbp+hKey]; hKey
0x18004cf8b  lea     rax, [rbp+cbData]
0x18004cf8f  mov     [rsp+60h+lpcbData], rax; lpcbData
0x18004cf94  lea     r9, [rbp+Type]; lpType
0x18004cf98  lea     rax, [rbp+Data]
0x18004cf9c  xor     r8d, r8d; lpReserved
0x18004cf9f  lea     rdx, aSenddnstohost; "SendDnsToHost"
0x18004cfa6  mov     [rsp+60h+phkResult], rax; lpData
0x18004cfab  call    cs:__imp_RegQueryValueExW
0x18004cfb2  nop     dword ptr [rax+rax+00h]
0x18004cfb7  test    eax, eax
0x18004cfb9  jle     short loc_18004CFC5
0x18004cfbb  movzx   eax, ax
0x18004cfbe  or      eax, 80070000h
0x18004cfc3  test    eax, eax
0x18004cfc5  jns     short loc_18004CFD0
0x18004cfc7  mov     [rbp+var_2C], 1A2h
0x18004cfce  jmp     short loc_18004CFEC
0x18004cfd0  cmp     [rbp+Type], 4
0x18004cfd4  jz      short loc_18004CFE4
0x18004cfd6  mov     eax, 800703F2h
0x18004cfdb  mov     [rbp+var_2C], 1A5h
0x18004cfe2  jmp     short loc_18004CFEC
0x18004cfe4  xor     eax, eax
0x18004cfe6  cmp     dword ptr [rbp+Data], eax
0x18004cfe9  setnz   bl
0x18004cfec  test    byte ptr cs:xmmword_1800AD720+3, 20h
0x18004cff3  jz      short loc_18004D012
0x18004cff5  mov     edx, 1Eh
0x18004cffa  mov     dword ptr [rsp+60h+phkResult], eax
0x18004cffe  mov     ecx, 41Dh
0x18004d003  lea     r8, WPP_34669277914b3b6bb504f68bf473a142_Traceguids
0x18004d00a  mov     r9d, ebx
0x18004d00d  call    WPP_SF_dd
0x18004d012  mov     rcx, [rbp+hKey]; hKey
0x18004d016  test    rcx, rcx
0x18004d019  jz      short loc_18004D027
0x18004d01b  call    cs:__imp_RegCloseKey
0x18004d022  nop     dword ptr [rax+rax+00h]
0x18004d027  mov     eax, ebx
0x18004d029  mov     rcx, [rbp+var_10]
0x18004d02d  xor     rcx, rsp; StackCookie
0x18004d030  call    __security_check_cookie
0x18004d035  mov     rbx, [rsp+60h+arg_0]
0x18004d03a  add     rsp, 60h
0x18004d03e  pop     rbp
0x18004d03f  retn
```
