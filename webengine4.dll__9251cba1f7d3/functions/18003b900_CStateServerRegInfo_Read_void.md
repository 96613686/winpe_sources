# CStateServerRegInfo::Read(void)

- ea: `0x18003b900`
- end: `0x18003ba09`
- name: `?Read@CStateServerRegInfo@@UEAAXXZ`
- size: `265`
- prototype: `void __fastcall(CStateServerRegInfo *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, service_task`

## callers

- `0x18003ef38`

## callees

- `0x18003b900`

## import_xrefs

- `ADVAPI32!RegCloseKey` at `0x18003b9f8`
- `ADVAPI32!RegCloseKey` at `0x18003b9f8`
- `ADVAPI32!RegOpenKeyExW` at `0x18003b93c`
- `ADVAPI32!RegOpenKeyExW` at `0x18003b93c`
- `ADVAPI32!RegQueryValueExW` at `0x18003b96d`
- `ADVAPI32!RegQueryValueExW` at `0x18003b9a4`
- `ADVAPI32!RegQueryValueExW` at `0x18003b9db`
- `ADVAPI32!RegQueryValueExW` at `0x18003b96d`
- `ADVAPI32!RegQueryValueExW` at `0x18003b9a4`
- `ADVAPI32!RegQueryValueExW` at `0x18003b9db`

## string_xrefs

- `0x18003b932`: `SYSTEM\CurrentControlSet\Services\aspnet_state\Parameters`

## pseudocode

```c
void __fastcall CStateServerRegInfo::Read(CStateServerRegInfo *this)
{
  int v2; // eax
  int v3; // eax
  int v4; // eax
  int Data; // [rsp+48h] [rbp+18h] BYREF
  DWORD cbData; // [rsp+50h] [rbp+20h] BYREF
  HKEY hKey; // [rsp+58h] [rbp+28h] BYREF

  hKey = 0;
  cbData = 4;
  if ( !RegOpenKeyExW(
          HKEY_LOCAL_MACHINE,
          L"SYSTEM\\CurrentControlSet\\Services\\aspnet_state\\Parameters",
          0,
          0x20019u,
          &hKey) )
  {
    if ( !RegQueryValueExW(hKey, L"Port", 0, 0, (LPBYTE)&Data, &cbData) )
    {
      v2 = Data;
      *((_BYTE *)this + 20) |= 2u;
      *((_DWORD *)this + 3) = v2;
    }
    if ( !RegQueryValueExW(hKey, L"AllowRemoteConnection", 0, 0, (LPBYTE)&Data, &cbData) )
    {
      v3 = Data;
      *((_BYTE *)this + 20) |= 1u;
      *((_DWORD *)this + 2) = v3;
    }
    if ( !RegQueryValueExW(hKey, L"DontResetOnUpgradeAllowRemoteConnection", 0, 0, (LPBYTE)&Data, &cbData) )
    {
      v4 = Data;
      *((_BYTE *)this + 20) |= 4u;
      *((_DWORD *)this + 4) = v4;
    }
  }
  if ( hKey )
    RegCloseKey(hKey);
}

```

## disassembly

```asm
0x18003b900  mov     [rsp-8+arg_0], rbx
0x18003b905  push    rbp
0x18003b906  mov     rbp, rsp
0x18003b909  sub     rsp, 30h
0x18003b90d  and     [rbp+hKey], 0
0x18003b912  lea     rax, [rbp+hKey]
0x18003b916  mov     rbx, rcx
0x18003b919  mov     [rsp+30h+phkResult], rax; phkResult
0x18003b91e  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18003b925  mov     [rbp+cbData], 4
0x18003b92c  mov     r9d, 20019h; samDesired
0x18003b932  lea     rdx, aSystemCurrentc_1; "SYSTEM\\CurrentControlSet\\Services\\as"...
0x18003b939  xor     r8d, r8d; ulOptions
0x18003b93c  call    cs:__imp_RegOpenKeyExW
0x18003b942  test    eax, eax
0x18003b944  jnz     loc_18003B9EF
0x18003b94a  mov     rcx, [rbp+hKey]; hKey
0x18003b94e  lea     rax, [rbp+cbData]
0x18003b952  mov     [rsp+30h+lpcbData], rax; lpcbData
0x18003b957  lea     rdx, aPort; "Port"
0x18003b95e  lea     rax, [rbp+Data]
0x18003b962  xor     r9d, r9d; lpType
0x18003b965  xor     r8d, r8d; lpReserved
0x18003b968  mov     [rsp+30h+phkResult], rax; lpData
0x18003b96d  call    cs:__imp_RegQueryValueExW
0x18003b973  test    eax, eax
0x18003b975  jnz     short loc_18003B981
0x18003b977  mov     eax, [rbp+Data]
0x18003b97a  or      byte ptr [rbx+14h], 2
0x18003b97e  mov     [rbx+0Ch], eax
0x18003b981  mov     rcx, [rbp+hKey]; hKey
0x18003b985  lea     rax, [rbp+cbData]
0x18003b989  mov     [rsp+30h+lpcbData], rax; lpcbData
0x18003b98e  lea     rdx, aAllowremotecon; "AllowRemoteConnection"
0x18003b995  lea     rax, [rbp+Data]
0x18003b999  xor     r9d, r9d; lpType
0x18003b99c  xor     r8d, r8d; lpReserved
0x18003b99f  mov     [rsp+30h+phkResult], rax; lpData
0x18003b9a4  call    cs:__imp_RegQueryValueExW
0x18003b9aa  test    eax, eax
0x18003b9ac  jnz     short loc_18003B9B8
0x18003b9ae  mov     eax, [rbp+Data]
0x18003b9b1  or      byte ptr [rbx+14h], 1
0x18003b9b5  mov     [rbx+8], eax
0x18003b9b8  mov     rcx, [rbp+hKey]; hKey
0x18003b9bc  lea     rax, [rbp+cbData]
0x18003b9c0  mov     [rsp+30h+lpcbData], rax; lpcbData
0x18003b9c5  lea     rdx, aDontresetonupg; "DontResetOnUpgradeAllowRemoteConnection"
0x18003b9cc  lea     rax, [rbp+Data]
0x18003b9d0  xor     r9d, r9d; lpType
0x18003b9d3  xor     r8d, r8d; lpReserved
0x18003b9d6  mov     [rsp+30h+phkResult], rax; lpData
0x18003b9db  call    cs:__imp_RegQueryValueExW
0x18003b9e1  test    eax, eax
0x18003b9e3  jnz     short loc_18003B9EF
0x18003b9e5  mov     eax, [rbp+Data]
0x18003b9e8  or      byte ptr [rbx+14h], 4
0x18003b9ec  mov     [rbx+10h], eax
0x18003b9ef  mov     rcx, [rbp+hKey]; hKey
0x18003b9f3  test    rcx, rcx
0x18003b9f6  jz      short loc_18003B9FE
0x18003b9f8  call    cs:__imp_RegCloseKey
0x18003b9fe  mov     rbx, [rsp+30h+arg_0]
0x18003ba03  add     rsp, 30h
0x18003ba07  pop     rbp
0x18003ba08  retn
```
