# CheckRegistryForMinMaxLifetime(void)

- ea: `0x18003623c`
- end: `0x18003638d`
- name: `?CheckRegistryForMinMaxLifetime@@YAXXZ`
- size: `337`
- prototype: `void(void)`
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config, service_task`

## callers

- `0x180006fd0`
- `0x180018804`

## callees

- `0x180029df0`
- `0x18003623c`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003637a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003637a`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExA` at `0x1800362bd`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExA` at `0x180036342`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExA` at `0x1800362bd`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExA` at `0x180036342`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExA` at `0x180036286`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExA` at `0x180036286`

## string_xrefs

- `0x18003624b`: `SYSTEM\CurrentControlSet\Services\SSDPSRV\Parameters`

## pseudocode

```c
void CheckRegistryForMinMaxLifetime(void)
{
  unsigned int v0; // eax
  unsigned int Data; // [rsp+40h] [rbp+10h] BYREF
  DWORD cbData; // [rsp+48h] [rbp+18h] BYREF
  unsigned int v3; // [rsp+50h] [rbp+20h] BYREF
  HKEY hKey; // [rsp+58h] [rbp+28h] BYREF

  Data = g_nMaxLifetime;
  v3 = g_nMinLifetime;
  hKey = 0;
  cbData = 4;
  if ( !RegOpenKeyExA(
          HKEY_LOCAL_MACHINE,
          "SYSTEM\\CurrentControlSet\\Services\\SSDPSRV\\Parameters",
          0,
          0x20019u,
          &hKey) )
  {
    if ( RegQueryValueExA(hKey, "MaxDeviceLifetime", 0, 0, (LPBYTE)&Data, &cbData) )
    {
      Data = g_nMaxLifetime;
    }
    else if ( Data >= 0x20C49B )
    {
      Data = g_nMaxLifetime;
      if ( WPP_GLOBAL_Control != (LPCSTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[28] & 1) != 0 )
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 64, WPP_6f3552b14628310eb215fa0007e7d416_Traceguids);
    }
    cbData = 4;
    if ( RegQueryValueExA(hKey, "MinDeviceLifetime", 0, 0, (LPBYTE)&v3, &cbData) || (v0 = v3, v3 <= 0x18) )
    {
      v0 = g_nMinLifetime;
      v3 = g_nMinLifetime;
    }
    if ( Data >= v0 )
    {
      g_nMaxLifetime = Data;
      g_nMinLifetime = v0;
    }
    RegCloseKey(hKey);
  }
}

```

## disassembly

```asm
0x18003623c  push    rbp
0x18003623e  mov     rbp, rsp
0x180036241  sub     rsp, 30h
0x180036245  mov     eax, cs:?g_nMaxLifetime@@3IA; uint g_nMaxLifetime
0x18003624b  lea     rdx, SubKey; "SYSTEM\\CurrentControlSet\\Services\\SS"...
0x180036252  mov     [rbp+Data], eax
0x180036255  mov     r9d, 20019h; samDesired
0x18003625b  mov     eax, cs:?g_nMinLifetime@@3IA; uint g_nMinLifetime
0x180036261  xor     r8d, r8d; ulOptions
0x180036264  mov     [rbp+arg_10], eax
0x180036267  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18003626e  lea     rax, [rbp+hKey]
0x180036272  mov     [rbp+hKey], 0
0x18003627a  mov     [rsp+30h+phkResult], rax; phkResult
0x18003627f  mov     [rbp+cbData], 4
0x180036286  call    cs:__imp_RegOpenKeyExA
0x18003628d  nop     dword ptr [rax+rax+00h]
0x180036292  test    eax, eax
0x180036294  jnz     loc_180036386
0x18003629a  mov     rcx, [rbp+hKey]; hKey
0x18003629e  lea     rax, [rbp+cbData]
0x1800362a2  mov     [rsp+30h+lpcbData], rax; lpcbData
0x1800362a7  lea     rdx, aMaxdevicelifet; "MaxDeviceLifetime"
0x1800362ae  lea     rax, [rbp+Data]
0x1800362b2  xor     r9d, r9d; lpType
0x1800362b5  xor     r8d, r8d; lpReserved
0x1800362b8  mov     [rsp+30h+phkResult], rax; lpData
0x1800362bd  call    cs:__imp_RegQueryValueExA
0x1800362c4  nop     dword ptr [rax+rax+00h]
0x1800362c9  test    eax, eax
0x1800362cb  jz      short loc_1800362D8
0x1800362cd  mov     eax, cs:?g_nMaxLifetime@@3IA; uint g_nMaxLifetime
0x1800362d3  mov     [rbp+Data], eax
0x1800362d6  jmp     short loc_180036318
0x1800362d8  cmp     [rbp+Data], 20C49Bh
0x1800362df  jb      short loc_180036318
0x1800362e1  mov     eax, cs:?g_nMaxLifetime@@3IA; uint g_nMaxLifetime
0x1800362e7  mov     [rbp+Data], eax
0x1800362ea  mov     rcx, cs:WPP_GLOBAL_Control
0x1800362f1  lea     rax, WPP_GLOBAL_Control
0x1800362f8  cmp     rcx, rax
0x1800362fb  jz      short loc_180036318
0x1800362fd  test    byte ptr [rcx+1Ch], 1
0x180036301  jz      short loc_180036318
0x180036303  mov     rcx, [rcx+10h]
0x180036307  lea     r8, WPP_6f3552b14628310eb215fa0007e7d416_Traceguids
0x18003630e  mov     edx, 40h ; '@'
0x180036313  call    WPP_SF_
0x180036318  mov     rcx, [rbp+hKey]; hKey
0x18003631c  lea     rax, [rbp+cbData]
0x180036320  mov     [rsp+30h+lpcbData], rax; lpcbData
0x180036325  lea     rdx, aMindevicelifet; "MinDeviceLifetime"
0x18003632c  lea     rax, [rbp+arg_10]
0x180036330  mov     [rbp+cbData], 4
0x180036337  xor     r9d, r9d; lpType
0x18003633a  mov     [rsp+30h+phkResult], rax; lpData
0x18003633f  xor     r8d, r8d; lpReserved
0x180036342  call    cs:__imp_RegQueryValueExA
0x180036349  nop     dword ptr [rax+rax+00h]
0x18003634e  test    eax, eax
0x180036350  jnz     short loc_18003635A
0x180036352  mov     eax, [rbp+arg_10]
0x180036355  cmp     eax, 18h
0x180036358  ja      short loc_180036363
0x18003635a  mov     eax, cs:?g_nMinLifetime@@3IA; uint g_nMinLifetime
0x180036360  mov     [rbp+arg_10], eax
0x180036363  mov     ecx, [rbp+Data]
0x180036366  cmp     ecx, eax
0x180036368  jb      short loc_180036376
0x18003636a  mov     cs:?g_nMaxLifetime@@3IA, ecx; uint g_nMaxLifetime
0x180036370  mov     cs:?g_nMinLifetime@@3IA, eax; uint g_nMinLifetime
0x180036376  mov     rcx, [rbp+hKey]; hKey
0x18003637a  call    cs:__imp_RegCloseKey
0x180036381  nop     dword ptr [rax+rax+00h]
0x180036386  add     rsp, 30h
0x18003638a  pop     rbp
0x18003638b  retn
```
