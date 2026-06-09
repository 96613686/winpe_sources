# CheckRegistryForMinMaxLifetime(void)

- ea: `0x1800337b8`
- end: `0x1800338f0`
- name: `?CheckRegistryForMinMaxLifetime@@YAXXZ`
- size: `312`
- prototype: `void(void)`
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config, service_task`

## callers

- `0x180005c90`
- `0x180016410`

## callees

- `0x180028000`
- `0x1800337b8`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800338e4`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800338e4`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExA` at `0x180033833`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExA` at `0x1800338b2`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExA` at `0x180033833`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExA` at `0x1800338b2`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExA` at `0x180033802`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExA` at `0x180033802`

## string_xrefs

- `0x1800337c7`: `SYSTEM\CurrentControlSet\Services\SSDPSRV\Parameters`

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
0x1800337b8  push    rbp
0x1800337ba  mov     rbp, rsp
0x1800337bd  sub     rsp, 30h
0x1800337c1  mov     eax, cs:?g_nMaxLifetime@@3IA; uint g_nMaxLifetime
0x1800337c7  lea     rdx, SubKey; "SYSTEM\\CurrentControlSet\\Services\\SS"...
0x1800337ce  mov     [rbp+Data], eax
0x1800337d1  mov     r9d, 20019h; samDesired
0x1800337d7  mov     eax, cs:?g_nMinLifetime@@3IA; uint g_nMinLifetime
0x1800337dd  xor     r8d, r8d; ulOptions
0x1800337e0  mov     [rbp+arg_10], eax
0x1800337e3  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800337ea  lea     rax, [rbp+hKey]
0x1800337ee  mov     [rbp+hKey], 0
0x1800337f6  mov     [rsp+30h+phkResult], rax; phkResult
0x1800337fb  mov     [rbp+cbData], 4
0x180033802  call    cs:__imp_RegOpenKeyExA
0x180033808  test    eax, eax
0x18003380a  jnz     loc_1800338EA
0x180033810  mov     rcx, [rbp+hKey]; hKey
0x180033814  lea     rax, [rbp+cbData]
0x180033818  mov     [rsp+30h+lpcbData], rax; lpcbData
0x18003381d  lea     rdx, aMaxdevicelifet; "MaxDeviceLifetime"
0x180033824  lea     rax, [rbp+Data]
0x180033828  xor     r9d, r9d; lpType
0x18003382b  xor     r8d, r8d; lpReserved
0x18003382e  mov     [rsp+30h+phkResult], rax; lpData
0x180033833  call    cs:__imp_RegQueryValueExA
0x180033839  test    eax, eax
0x18003383b  jz      short loc_180033848
0x18003383d  mov     eax, cs:?g_nMaxLifetime@@3IA; uint g_nMaxLifetime
0x180033843  mov     [rbp+Data], eax
0x180033846  jmp     short loc_180033888
0x180033848  cmp     [rbp+Data], 20C49Bh
0x18003384f  jb      short loc_180033888
0x180033851  mov     eax, cs:?g_nMaxLifetime@@3IA; uint g_nMaxLifetime
0x180033857  mov     [rbp+Data], eax
0x18003385a  mov     rcx, cs:WPP_GLOBAL_Control
0x180033861  lea     rax, WPP_GLOBAL_Control
0x180033868  cmp     rcx, rax
0x18003386b  jz      short loc_180033888
0x18003386d  test    byte ptr [rcx+1Ch], 1
0x180033871  jz      short loc_180033888
0x180033873  mov     rcx, [rcx+10h]
0x180033877  lea     r8, WPP_6f3552b14628310eb215fa0007e7d416_Traceguids
0x18003387e  mov     edx, 40h ; '@'
0x180033883  call    WPP_SF_
0x180033888  mov     rcx, [rbp+hKey]; hKey
0x18003388c  lea     rax, [rbp+cbData]
0x180033890  mov     [rsp+30h+lpcbData], rax; lpcbData
0x180033895  lea     rdx, aMindevicelifet; "MinDeviceLifetime"
0x18003389c  lea     rax, [rbp+arg_10]
0x1800338a0  mov     [rbp+cbData], 4
0x1800338a7  xor     r9d, r9d; lpType
0x1800338aa  mov     [rsp+30h+phkResult], rax; lpData
0x1800338af  xor     r8d, r8d; lpReserved
0x1800338b2  call    cs:__imp_RegQueryValueExA
0x1800338b8  test    eax, eax
0x1800338ba  jnz     short loc_1800338C4
0x1800338bc  mov     eax, [rbp+arg_10]
0x1800338bf  cmp     eax, 18h
0x1800338c2  ja      short loc_1800338CD
0x1800338c4  mov     eax, cs:?g_nMinLifetime@@3IA; uint g_nMinLifetime
0x1800338ca  mov     [rbp+arg_10], eax
0x1800338cd  mov     ecx, [rbp+Data]
0x1800338d0  cmp     ecx, eax
0x1800338d2  jb      short loc_1800338E0
0x1800338d4  mov     cs:?g_nMaxLifetime@@3IA, ecx; uint g_nMaxLifetime
0x1800338da  mov     cs:?g_nMinLifetime@@3IA, eax; uint g_nMinLifetime
0x1800338e0  mov     rcx, [rbp+hKey]; hKey
0x1800338e4  call    cs:__imp_RegCloseKey
0x1800338ea  add     rsp, 30h
0x1800338ee  pop     rbp
0x1800338ef  retn
```
