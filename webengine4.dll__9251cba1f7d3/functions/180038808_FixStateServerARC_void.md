# FixStateServerARC(void)

- ea: `0x180038808`
- end: `0x180038948`
- name: `?FixStateServerARC@@YAJXZ`
- size: `320`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, service_task, installer_update`

## callers

- `0x18003c1e8`

## callees

- `0x180038808`
- `0x18003abe4`

## import_xrefs

- `ADVAPI32!RegCloseKey` at `0x180038938`
- `ADVAPI32!RegCloseKey` at `0x180038938`
- `ADVAPI32!RegOpenKeyExW` at `0x18003885d`
- `ADVAPI32!RegOpenKeyExW` at `0x18003885d`
- `ADVAPI32!RegQueryValueExW` at `0x18003888e`
- `ADVAPI32!RegQueryValueExW` at `0x18003888e`
- `ADVAPI32!RegSetValueExW` at `0x1800388ca`
- `ADVAPI32!RegSetValueExW` at `0x1800388f9`
- `ADVAPI32!RegSetValueExW` at `0x1800388ca`
- `ADVAPI32!RegSetValueExW` at `0x1800388f9`

## string_xrefs

- `0x18003884f`: `SYSTEM\CurrentControlSet\Services\aspnet_state\Parameters`

## pseudocode

```c
__int64 FixStateServerARC(void)
{
  unsigned int v0; // ebx
  LSTATUS v1; // eax
  int Data; // [rsp+50h] [rbp+20h] BYREF
  DWORD cbData; // [rsp+58h] [rbp+28h] BYREF
  HKEY hKey; // [rsp+60h] [rbp+30h] BYREF

  v0 = 0;
  hKey = 0;
  cbData = 4;
  CSetupLogging::Log(1, "FixStateServerARC", 0, "Fixing State Server AllowRemoteConnection value", 0);
  v1 = RegOpenKeyExW(
         HKEY_LOCAL_MACHINE,
         L"SYSTEM\\CurrentControlSet\\Services\\aspnet_state\\Parameters",
         0,
         0x2001Bu,
         &hKey);
  if ( !v1 )
  {
    v1 = RegQueryValueExW(hKey, L"DontResetOnUpgradeAllowRemoteConnection", 0, 0, (LPBYTE)&Data, &cbData);
    if ( v1 == 1168 || v1 == 2 )
      goto LABEL_6;
    if ( !v1 )
    {
      if ( Data )
        goto LABEL_10;
LABEL_6:
      Data = 0;
      v1 = RegSetValueExW(hKey, L"AllowRemoteConnection", 0, 4u, (const BYTE *)&Data, 4u);
      if ( !v1 )
      {
        Data = 1;
        v1 = RegSetValueExW(hKey, L"DontResetOnUpgradeAllowRemoteConnection", 0, 4u, (const BYTE *)&Data, 4u);
        if ( !v1 )
          goto LABEL_10;
      }
    }
  }
  v0 = (unsigned __int16)v1 | 0x80070000;
  if ( v1 <= 0 )
    v0 = v1;
LABEL_10:
  CSetupLogging::Log(v0, "FixStateServerARC", 0, "Fixing State Server AllowRemoteConnection value", 0);
  if ( hKey )
    RegCloseKey(hKey);
  return v0;
}

```

## disassembly

```asm
0x180038808  push    rbp
0x18003880a  push    rbx
0x18003880b  push    rsi
0x18003880c  mov     rbp, rsp
0x18003880f  sub     rsp, 30h
0x180038813  xor     ebx, ebx
0x180038815  lea     r9, aFixingStateSer; "Fixing State Server AllowRemoteConnecti"...
0x18003881c  and     [rbp+hKey], rbx
0x180038820  lea     rdx, aFixstateserver; "FixStateServerARC"
0x180038827  and     [rsp+30h+phkResult], rbx
0x18003882c  xor     r8d, r8d; unsigned int
0x18003882f  lea     esi, [rbx+4]
0x180038832  lea     ecx, [rbx+1]; int
0x180038835  mov     [rbp+cbData], esi
0x180038838  call    ?Log@CSetupLogging@@SAXJPEBDI0PEBG@Z; CSetupLogging::Log(long,char const *,uint,char const *,ushort const *)
0x18003883d  lea     rax, [rbp+hKey]
0x180038841  mov     r9d, 2001Bh; samDesired
0x180038847  xor     r8d, r8d; ulOptions
0x18003884a  mov     [rsp+30h+phkResult], rax; phkResult
0x18003884f  lea     rdx, aSystemCurrentc_1; "SYSTEM\\CurrentControlSet\\Services\\as"...
0x180038856  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18003885d  call    cs:__imp_RegOpenKeyExW
0x180038863  test    eax, eax
0x180038865  jnz     loc_180038903
0x18003886b  mov     rcx, [rbp+hKey]; hKey
0x18003886f  lea     rax, [rbp+cbData]
0x180038873  mov     [rsp+30h+lpcbData], rax; lpcbData
0x180038878  lea     rdx, aDontresetonupg; "DontResetOnUpgradeAllowRemoteConnection"
0x18003887f  lea     rax, [rbp+Data]
0x180038883  xor     r9d, r9d; lpType
0x180038886  xor     r8d, r8d; lpReserved
0x180038889  mov     [rsp+30h+phkResult], rax; lpData
0x18003888e  call    cs:__imp_RegQueryValueExW
0x180038894  cmp     eax, 490h
0x180038899  jz      short loc_1800388A9
0x18003889b  cmp     eax, 2
0x18003889e  jz      short loc_1800388A9
0x1800388a0  test    eax, eax
0x1800388a2  jnz     short loc_180038903
0x1800388a4  cmp     [rbp+Data], ebx
0x1800388a7  jnz     short loc_180038911
0x1800388a9  mov     rcx, [rbp+hKey]; hKey
0x1800388ad  lea     rax, [rbp+Data]
0x1800388b1  and     [rbp+Data], ebx
0x1800388b4  lea     rdx, aAllowremotecon; "AllowRemoteConnection"
0x1800388bb  mov     dword ptr [rsp+30h+lpcbData], esi; cbData
0x1800388bf  mov     r9d, esi; dwType
0x1800388c2  xor     r8d, r8d; Reserved
0x1800388c5  mov     [rsp+30h+phkResult], rax; lpData
0x1800388ca  call    cs:__imp_RegSetValueExW
0x1800388d0  test    eax, eax
0x1800388d2  jnz     short loc_180038903
0x1800388d4  mov     rcx, [rbp+hKey]; hKey
0x1800388d8  lea     rax, [rbp+Data]
0x1800388dc  mov     dword ptr [rsp+30h+lpcbData], esi; cbData
0x1800388e0  lea     rdx, aDontresetonupg; "DontResetOnUpgradeAllowRemoteConnection"
0x1800388e7  mov     r9d, esi; dwType
0x1800388ea  mov     [rsp+30h+phkResult], rax; unsigned __int16 *
0x1800388ef  xor     r8d, r8d; Reserved
0x1800388f2  mov     [rbp+Data], 1
0x1800388f9  call    cs:__imp_RegSetValueExW
0x1800388ff  test    eax, eax
0x180038901  jz      short loc_180038911
0x180038903  movzx   ebx, ax
0x180038906  or      ebx, 80070000h
0x18003890c  test    eax, eax
0x18003890e  cmovle  ebx, eax
0x180038911  and     [rsp+30h+phkResult], 0
0x180038917  lea     r9, aFixingStateSer; "Fixing State Server AllowRemoteConnecti"...
0x18003891e  xor     r8d, r8d; unsigned int
0x180038921  lea     rdx, aFixstateserver; "FixStateServerARC"
0x180038928  mov     ecx, ebx; int
0x18003892a  call    ?Log@CSetupLogging@@SAXJPEBDI0PEBG@Z; CSetupLogging::Log(long,char const *,uint,char const *,ushort const *)
0x18003892f  mov     rcx, [rbp+hKey]; hKey
0x180038933  test    rcx, rcx
0x180038936  jz      short loc_18003893E
0x180038938  call    cs:__imp_RegCloseKey
0x18003893e  mov     eax, ebx
0x180038940  add     rsp, 30h
0x180038944  pop     rsi
0x180038945  pop     rbx
0x180038946  pop     rbp
0x180038947  retn
```
