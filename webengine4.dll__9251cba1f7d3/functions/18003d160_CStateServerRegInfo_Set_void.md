# CStateServerRegInfo::Set(void)

- ea: `0x18003d160`
- end: `0x18003d286`
- name: `?Set@CStateServerRegInfo@@UEAAXXZ`
- size: `294`
- prototype: `void __fastcall(CStateServerRegInfo *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, service_task`

## callers

- `0x18003ef38`

## callees

- `0x18003d160`

## import_xrefs

- `ADVAPI32!RegCloseKey` at `0x18003d270`
- `ADVAPI32!RegCloseKey` at `0x18003d270`
- `ADVAPI32!RegOpenKeyExW` at `0x18003d1a7`
- `ADVAPI32!RegOpenKeyExW` at `0x18003d1a7`
- `ADVAPI32!RegSetValueExW` at `0x18003d1fe`
- `ADVAPI32!RegSetValueExW` at `0x18003d22f`
- `ADVAPI32!RegSetValueExW` at `0x18003d261`
- `ADVAPI32!RegSetValueExW` at `0x18003d1fe`
- `ADVAPI32!RegSetValueExW` at `0x18003d22f`
- `ADVAPI32!RegSetValueExW` at `0x18003d261`
- `ADVAPI32!RegCreateKeyW` at `0x18003d1c0`
- `ADVAPI32!RegCreateKeyW` at `0x18003d1c0`

## string_xrefs

- `0x18003d19d`: `SYSTEM\CurrentControlSet\Services\aspnet_state\Parameters`
- `0x18003d1b9`: `SYSTEM\CurrentControlSet\Services\aspnet_state\Parameters`

## pseudocode

```c
void __fastcall CStateServerRegInfo::Set(CStateServerRegInfo *this)
{
  LSTATUS v2; // eax
  char v3; // al
  int Data; // [rsp+40h] [rbp+10h] BYREF
  HKEY hKey; // [rsp+48h] [rbp+18h] BYREF

  hKey = 0;
  if ( (*((_BYTE *)this + 20) & 3) != 0 )
  {
    v2 = RegOpenKeyExW(
           HKEY_LOCAL_MACHINE,
           L"SYSTEM\\CurrentControlSet\\Services\\aspnet_state\\Parameters",
           0,
           0x20006u,
           &hKey);
    if ( v2 == 2 )
      v2 = RegCreateKeyW(HKEY_LOCAL_MACHINE, L"SYSTEM\\CurrentControlSet\\Services\\aspnet_state\\Parameters", &hKey);
    if ( !v2 )
    {
      v3 = *((_BYTE *)this + 20);
      if ( (v3 & 2) != 0 )
      {
        Data = *((_DWORD *)this + 3);
        RegSetValueExW(hKey, L"Port", 0, 4u, (const BYTE *)&Data, 4u);
        v3 = *((_BYTE *)this + 20);
      }
      if ( (v3 & 1) != 0 )
      {
        Data = *((_DWORD *)this + 2);
        RegSetValueExW(hKey, L"AllowRemoteConnection", 0, 4u, (const BYTE *)&Data, 4u);
        v3 = *((_BYTE *)this + 20);
      }
      if ( (v3 & 4) != 0 )
      {
        Data = *((_DWORD *)this + 4);
        RegSetValueExW(hKey, L"DontResetOnUpgradeAllowRemoteConnection", 0, 4u, (const BYTE *)&Data, 4u);
      }
    }
    if ( hKey )
      RegCloseKey(hKey);
  }
}

```

## disassembly

```asm
0x18003d160  mov     [rsp-8+arg_10], rbx
0x18003d165  mov     [rsp-8+arg_18], rdi
0x18003d16a  push    rbp
0x18003d16b  mov     rbp, rsp
0x18003d16e  sub     rsp, 30h
0x18003d172  and     [rbp+hKey], 0
0x18003d177  mov     rbx, rcx
0x18003d17a  test    byte ptr [rcx+14h], 3
0x18003d17e  jz      loc_18003D276
0x18003d184  lea     rax, [rbp+hKey]
0x18003d188  mov     rdi, 0FFFFFFFF80000002h
0x18003d18f  mov     rcx, rdi; hKey
0x18003d192  mov     [rsp+30h+phkResult], rax; phkResult
0x18003d197  mov     r9d, 20006h; samDesired
0x18003d19d  lea     rdx, aSystemCurrentc_1; "SYSTEM\\CurrentControlSet\\Services\\as"...
0x18003d1a4  xor     r8d, r8d; ulOptions
0x18003d1a7  call    cs:__imp_RegOpenKeyExW
0x18003d1ad  cmp     eax, 2
0x18003d1b0  jnz     short loc_18003D1C6
0x18003d1b2  lea     r8, [rbp+hKey]; phkResult
0x18003d1b6  mov     rcx, rdi; hKey
0x18003d1b9  lea     rdx, aSystemCurrentc_1; "SYSTEM\\CurrentControlSet\\Services\\as"...
0x18003d1c0  call    cs:__imp_RegCreateKeyW
0x18003d1c6  test    eax, eax
0x18003d1c8  jnz     loc_18003D267
0x18003d1ce  mov     al, [rbx+14h]
0x18003d1d1  mov     edi, 4
0x18003d1d6  test    al, 2
0x18003d1d8  jz      short loc_18003D207
0x18003d1da  mov     eax, [rbx+0Ch]
0x18003d1dd  lea     rdx, aPort; "Port"
0x18003d1e4  mov     rcx, [rbp+hKey]; hKey
0x18003d1e8  mov     r9d, edi; dwType
0x18003d1eb  mov     [rbp+Data], eax
0x18003d1ee  xor     r8d, r8d; Reserved
0x18003d1f1  lea     rax, [rbp+Data]
0x18003d1f5  mov     [rsp+30h+cbData], edi; cbData
0x18003d1f9  mov     [rsp+30h+phkResult], rax; lpData
0x18003d1fe  call    cs:__imp_RegSetValueExW
0x18003d204  mov     al, [rbx+14h]
0x18003d207  test    al, 1
0x18003d209  jz      short loc_18003D238
0x18003d20b  mov     eax, [rbx+8]
0x18003d20e  lea     rdx, aAllowremotecon; "AllowRemoteConnection"
0x18003d215  mov     rcx, [rbp+hKey]; hKey
0x18003d219  mov     r9d, edi; dwType
0x18003d21c  mov     [rbp+Data], eax
0x18003d21f  xor     r8d, r8d; Reserved
0x18003d222  lea     rax, [rbp+Data]
0x18003d226  mov     [rsp+30h+cbData], edi; cbData
0x18003d22a  mov     [rsp+30h+phkResult], rax; lpData
0x18003d22f  call    cs:__imp_RegSetValueExW
0x18003d235  mov     al, [rbx+14h]
0x18003d238  test    dil, al
0x18003d23b  jz      short loc_18003D267
0x18003d23d  mov     eax, [rbx+10h]
0x18003d240  lea     rdx, aDontresetonupg; "DontResetOnUpgradeAllowRemoteConnection"
0x18003d247  mov     rcx, [rbp+hKey]; hKey
0x18003d24b  mov     r9d, edi; dwType
0x18003d24e  mov     [rbp+Data], eax
0x18003d251  xor     r8d, r8d; Reserved
0x18003d254  lea     rax, [rbp+Data]
0x18003d258  mov     [rsp+30h+cbData], edi; cbData
0x18003d25c  mov     [rsp+30h+phkResult], rax; lpData
0x18003d261  call    cs:__imp_RegSetValueExW
0x18003d267  mov     rcx, [rbp+hKey]; hKey
0x18003d26b  test    rcx, rcx
0x18003d26e  jz      short loc_18003D276
0x18003d270  call    cs:__imp_RegCloseKey
0x18003d276  mov     rbx, [rsp+30h+arg_10]
0x18003d27b  mov     rdi, [rsp+30h+arg_18]
0x18003d280  add     rsp, 30h
0x18003d284  pop     rbp
0x18003d285  retn
```
