# WintrustGetRegPolicyFlags

- ea: `0x180013f60`
- end: `0x180014065`
- name: `WintrustGetRegPolicyFlags`
- size: `261`
- prototype: `void __stdcall(DWORD *pdwPolicyFlags)`
- caller_count: `3`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000a410`
- `0x1800137b0`
- `0x18002daa0`

## callees

- `0x180013f60`
- `0x180014490`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18001402f`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18001402f`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180013fe7`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180013fe7`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180014001`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001403d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001405d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180014001`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001403d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001405d`

## pseudocode

```c
void __stdcall WintrustGetRegPolicyFlags(DWORD *pdwPolicyFlags)
{
  LSTATUS v2; // ebx
  HKEY phkResult; // [rsp+50h] [rbp-10h] BYREF
  HKEY hKey; // [rsp+58h] [rbp-8h] BYREF
  DWORD Type; // [rsp+80h] [rbp+20h] BYREF
  DWORD Data; // [rsp+88h] [rbp+28h] BYREF
  DWORD dwDisposition; // [rsp+90h] [rbp+30h] BYREF
  DWORD cbData; // [rsp+98h] [rbp+38h] BYREF

  *pdwPolicyFlags = 146432;
  phkResult = 0;
  dwDisposition = 0;
  Type = 0;
  cbData = 4;
  Data = 0;
  hKey = 0;
  v2 = RegOpenHKCUEx(&hKey);
  if ( !v2 )
  {
    v2 = RegCreateKeyExW(
           hKey,
           L"Software\\Microsoft\\Windows\\CurrentVersion\\WinTrust\\Trust Providers\\Software Publishing",
           0,
           0,
           0,
           0x20019u,
           0,
           &phkResult,
           &dwDisposition);
    if ( hKey )
    {
      if ( hKey != HKEY_CURRENT_USER )
        RegCloseKey(hKey);
    }
  }
  if ( !v2 )
  {
    if ( RegQueryValueExW(phkResult, L"State", 0, &Type, (LPBYTE)&Data, &cbData) )
    {
      RegCloseKey(phkResult);
    }
    else
    {
      RegCloseKey(phkResult);
      if ( Type - 3 <= 1 )
        *pdwPolicyFlags = Data;
    }
  }
}

```

## disassembly

```asm
0x180013f60  push    rbp
0x180013f62  push    rbx
0x180013f63  push    rdi
0x180013f64  mov     rbp, rsp
0x180013f67  sub     rsp, 60h
0x180013f6b  mov     rdi, rcx
0x180013f6e  mov     dword ptr [rcx], 23C00h
0x180013f74  lea     rcx, [rbp+hKey]
0x180013f78  mov     [rbp+var_10], 0
0x180013f80  mov     [rbp+dwDisposition], 0
0x180013f87  mov     [rbp+Type], 0
0x180013f8e  mov     [rbp+cbData], 4
0x180013f95  mov     [rbp+Data], 0
0x180013f9c  mov     [rbp+hKey], 0
0x180013fa4  call    RegOpenHKCUEx
0x180013fa9  mov     ebx, eax
0x180013fab  test    eax, eax
0x180013fad  jnz     short loc_180014007
0x180013faf  mov     rcx, [rbp+hKey]; hKey
0x180013fb3  lea     rax, [rbp+dwDisposition]
0x180013fb7  mov     [rsp+60h+lpdwDisposition], rax; lpdwDisposition
0x180013fbc  lea     rdx, aSoftwareMicros_4; "Software\\Microsoft\\Windows\\CurrentVe"...
0x180013fc3  lea     rax, [rbp+var_10]
0x180013fc7  xor     r9d, r9d; lpClass
0x180013fca  mov     [rsp+60h+phkResult], rax; phkResult
0x180013fcf  xor     r8d, r8d; Reserved
0x180013fd2  mov     [rsp+60h+lpSecurityAttributes], 0; lpSecurityAttributes
0x180013fdb  mov     [rsp+60h+samDesired], 20019h; samDesired
0x180013fe3  mov     [rsp+60h+dwOptions], ebx; dwOptions
0x180013fe7  call    cs:__imp_RegCreateKeyExW
0x180013fed  mov     rcx, [rbp+hKey]; hKey
0x180013ff1  mov     ebx, eax
0x180013ff3  test    rcx, rcx
0x180013ff6  jz      short loc_180014007
0x180013ff8  cmp     rcx, 0FFFFFFFF80000001h
0x180013fff  jz      short loc_180014007
0x180014001  call    cs:__imp_RegCloseKey
0x180014007  test    ebx, ebx
0x180014009  jnz     short loc_18001404E
0x18001400b  mov     rcx, [rbp+var_10]; hKey
0x18001400f  lea     rax, [rbp+cbData]
0x180014013  mov     qword ptr [rsp+60h+samDesired], rax; lpcbData
0x180014018  lea     r9, [rbp+Type]; lpType
0x18001401c  lea     rax, [rbp+Data]
0x180014020  xor     r8d, r8d; lpReserved
0x180014023  lea     rdx, aState; "State"
0x18001402a  mov     qword ptr [rsp+60h+dwOptions], rax; lpData
0x18001402f  call    cs:__imp_RegQueryValueExW
0x180014035  mov     rcx, [rbp+var_10]; hKey
0x180014039  test    eax, eax
0x18001403b  jnz     short loc_18001405D
0x18001403d  call    cs:__imp_RegCloseKey
0x180014043  mov     eax, [rbp+Type]
0x180014046  add     eax, 0FFFFFFFDh
0x180014049  cmp     eax, 1
0x18001404c  jbe     short loc_180014056
0x18001404e  add     rsp, 60h
0x180014052  pop     rdi
0x180014053  pop     rbx
0x180014054  pop     rbp
0x180014055  retn
0x180014056  mov     eax, [rbp+Data]
0x180014059  mov     [rdi], eax
0x18001405b  jmp     short loc_18001404E
0x18001405d  call    cs:__imp_RegCloseKey
0x180014063  jmp     short loc_18001404E
```
