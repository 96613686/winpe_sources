# GetMMAuthMachineCertificateHash

- ea: `0x180069148`
- end: `0x180069217`
- name: `GetMMAuthMachineCertificateHash`
- size: `207`
- prototype: `__int64 __fastcall(LPBYTE lpData)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, service_task`

## callers

- `0x18003bdb4`

## callees

- `0x180069148`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryValueExA` at `0x1800691c6`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExA` at `0x1800691c6`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180069207`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180069207`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExA` at `0x180069197`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExA` at `0x180069197`

## string_xrefs

- `0x180069181`: `SYSTEM\CurrentControlSet\Services\RemoteAccess\Parameters`

## pseudocode

```c
__int64 __fastcall GetMMAuthMachineCertificateHash(LPBYTE lpData, _DWORD *a2)
{
  unsigned int v4; // ebx
  LSTATUS v5; // eax
  DWORD Type; // [rsp+50h] [rbp+8h] BYREF
  DWORD cbData; // [rsp+58h] [rbp+10h] BYREF
  HKEY hKey; // [rsp+60h] [rbp+18h] BYREF

  *a2 = 0;
  hKey = 0;
  Type = 3;
  cbData = 20;
  *lpData = 0;
  v4 = RegOpenKeyExA(HKEY_LOCAL_MACHINE, "SYSTEM\\CurrentControlSet\\Services\\RemoteAccess\\Parameters", 0, 1u, &hKey);
  if ( !v4 )
  {
    v5 = RegQueryValueExA(hKey, "ServerAuthCert", 0, &Type, lpData, &cbData);
    v4 = v5;
    if ( v5 == 2 )
    {
      v4 = 0;
    }
    else if ( !v5 )
    {
      if ( Type == 3 )
      {
        if ( cbData == 20 )
          *a2 = 1;
        else
          v4 = 13;
      }
      else
      {
        v4 = 1804;
      }
    }
  }
  if ( hKey )
    RegCloseKey(hKey);
  return v4;
}

```

## disassembly

```asm
0x180069148  mov     rax, rsp
0x18006914b  push    rbx
0x18006914c  push    rsi
0x18006914d  push    rdi
0x18006914e  sub     rsp, 30h
0x180069152  mov     dword ptr [rdx], 0
0x180069158  mov     rdi, rdx
0x18006915b  mov     qword ptr [rax+18h], 0
0x180069163  mov     rsi, rcx
0x180069166  mov     dword ptr [rax+8], 3
0x18006916d  mov     r9d, 1; samDesired
0x180069173  mov     dword ptr [rax+10h], 14h
0x18006917a  lea     rax, [rax+18h]
0x18006917e  mov     byte ptr [rcx], 0
0x180069181  lea     rdx, aSystemCurrentc_1; "SYSTEM\\CurrentControlSet\\Services\\Re"...
0x180069188  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18006918f  mov     [rsp+48h+phkResult], rax; phkResult
0x180069194  xor     r8d, r8d; ulOptions
0x180069197  call    cs:__imp_RegOpenKeyExA
0x18006919d  mov     ebx, eax
0x18006919f  test    eax, eax
0x1800691a1  jnz     short loc_1800691FD
0x1800691a3  mov     rcx, [rsp+48h+hKey]; hKey
0x1800691a8  lea     rax, [rsp+48h+cbData]
0x1800691ad  mov     [rsp+48h+lpcbData], rax; lpcbData
0x1800691b2  lea     r9, [rsp+48h+Type]; lpType
0x1800691b7  xor     r8d, r8d; lpReserved
0x1800691ba  mov     [rsp+48h+phkResult], rsi; lpData
0x1800691bf  lea     rdx, aServerauthcert; "ServerAuthCert"
0x1800691c6  call    cs:__imp_RegQueryValueExA
0x1800691cc  mov     ebx, eax
0x1800691ce  cmp     eax, 2
0x1800691d1  jnz     short loc_1800691D7
0x1800691d3  xor     ebx, ebx
0x1800691d5  jmp     short loc_1800691FD
0x1800691d7  test    eax, eax
0x1800691d9  jnz     short loc_1800691FD
0x1800691db  cmp     [rsp+48h+Type], 3
0x1800691e0  jz      short loc_1800691E9
0x1800691e2  mov     ebx, 70Ch
0x1800691e7  jmp     short loc_1800691FD
0x1800691e9  cmp     [rsp+48h+cbData], 14h
0x1800691ee  jz      short loc_1800691F7
0x1800691f0  mov     ebx, 0Dh
0x1800691f5  jmp     short loc_1800691FD
0x1800691f7  mov     dword ptr [rdi], 1
0x1800691fd  mov     rcx, [rsp+48h+hKey]; hKey
0x180069202  test    rcx, rcx
0x180069205  jz      short loc_18006920D
0x180069207  call    cs:__imp_RegCloseKey
0x18006920d  mov     eax, ebx
0x18006920f  add     rsp, 30h
0x180069213  pop     rdi
0x180069214  pop     rsi
0x180069215  pop     rbx
0x180069216  retn
```
