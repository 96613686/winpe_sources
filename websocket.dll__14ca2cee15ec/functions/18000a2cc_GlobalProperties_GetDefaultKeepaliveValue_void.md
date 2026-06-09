# GlobalProperties::GetDefaultKeepaliveValue(void)

- ea: `0x18000a2cc`
- end: `0x18000a3bd`
- name: `?GetDefaultKeepaliveValue@GlobalProperties@@SAKXZ`
- size: `241`
- prototype: `unsigned int(void)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180002470`

## callees

- `0x180002578`
- `0x18000a2cc`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000a316`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000a316`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000a394`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000a394`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000a346`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000a346`

## pseudocode

```c
__int64 GlobalProperties::GetDefaultKeepaliveValue(void)
{
  unsigned int v0; // eax
  signed __int32 v2[8]; // [rsp+0h] [rbp-38h] BYREF
  unsigned int Data; // [rsp+40h] [rbp+8h] BYREF
  DWORD cbData; // [rsp+48h] [rbp+10h] BYREF
  HKEY hKey; // [rsp+50h] [rbp+18h] BYREF

  if ( !GlobalProperties::s_fKeepaliveValueChecked )
  {
    hKey = 0;
    Data = 0;
    cbData = 4;
    if ( RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"SOFTWARE\\Microsoft\\WebSocket", 0, 0x20119u, &hKey)
      || RegQueryValueExW(hKey, L"KeepaliveInterval", 0, 0, (LPBYTE)&Data, &cbData) )
    {
      Trace::Error(-2147024809, 0xD0000026);
    }
    else
    {
      v0 = Data;
      if ( Data < 0x3A98 )
      {
        Trace::Error(-2147024809, 0xD0000027);
        v0 = 15000;
        Data = 15000;
      }
      GlobalProperties::s_ulKeepaliveValue = v0;
    }
    if ( hKey )
    {
      RegCloseKey(hKey);
      hKey = 0;
    }
    _InterlockedOr(v2, 0);
    GlobalProperties::s_fKeepaliveValueChecked = 1;
  }
  return GlobalProperties::s_ulKeepaliveValue;
}

```

## disassembly

```asm
0x18000a2cc  mov     rax, rsp
0x18000a2cf  sub     rsp, 38h
0x18000a2d3  cmp     cs:?s_fKeepaliveValueChecked@GlobalProperties@@0HA, 0; int GlobalProperties::s_fKeepaliveValueChecked
0x18000a2da  jnz     loc_18000A3B2
0x18000a2e0  mov     qword ptr [rax+18h], 0
0x18000a2e8  mov     r9d, 20119h; samDesired
0x18000a2ee  mov     dword ptr [rax+8], 0
0x18000a2f5  xor     r8d, r8d; ulOptions
0x18000a2f8  mov     dword ptr [rax+10h], 4
0x18000a2ff  lea     rax, [rax+18h]
0x18000a303  lea     rdx, SubKey; "SOFTWARE\\Microsoft\\WebSocket"
0x18000a30a  mov     [rsp+38h+phkResult], rax; phkResult
0x18000a30f  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18000a316  call    cs:__imp_RegOpenKeyExW
0x18000a31c  test    eax, eax
0x18000a31e  jnz     short loc_18000A37B
0x18000a320  mov     rcx, [rsp+38h+hKey]; hKey
0x18000a325  lea     rax, [rsp+38h+cbData]
0x18000a32a  mov     [rsp+38h+lpcbData], rax; lpcbData
0x18000a32f  lea     rdx, ValueName; "KeepaliveInterval"
0x18000a336  lea     rax, [rsp+38h+Data]
0x18000a33b  xor     r9d, r9d; lpType
0x18000a33e  xor     r8d, r8d; lpReserved
0x18000a341  mov     [rsp+38h+phkResult], rax; lpData
0x18000a346  call    cs:__imp_RegQueryValueExW
0x18000a34c  test    eax, eax
0x18000a34e  jnz     short loc_18000A37B
0x18000a350  mov     eax, [rsp+38h+Data]
0x18000a354  cmp     eax, 3A98h
0x18000a359  jnb     short loc_18000A373
0x18000a35b  mov     edx, 0D0000027h; unsigned int
0x18000a360  mov     ecx, 80070057h; int
0x18000a365  call    ?Error@Trace@@SAJJKZZ; Trace::Error(long,ulong,...)
0x18000a36a  mov     eax, 3A98h
0x18000a36f  mov     [rsp+38h+Data], eax
0x18000a373  mov     cs:?s_ulKeepaliveValue@GlobalProperties@@0KA, eax; ulong GlobalProperties::s_ulKeepaliveValue
0x18000a379  jmp     short loc_18000A38A
0x18000a37b  mov     edx, 0D0000026h; unsigned int
0x18000a380  mov     ecx, 80070057h; int
0x18000a385  call    ?Error@Trace@@SAJJKZZ; Trace::Error(long,ulong,...)
0x18000a38a  mov     rcx, [rsp+38h+hKey]; hKey
0x18000a38f  test    rcx, rcx
0x18000a392  jz      short loc_18000A3A3
0x18000a394  call    cs:__imp_RegCloseKey
0x18000a39a  mov     [rsp+38h+hKey], 0
0x18000a3a3  lock or [rsp+38h+var_38], 0
0x18000a3a8  mov     cs:?s_fKeepaliveValueChecked@GlobalProperties@@0HA, 1; int GlobalProperties::s_fKeepaliveValueChecked
0x18000a3b2  mov     eax, cs:?s_ulKeepaliveValue@GlobalProperties@@0KA; ulong GlobalProperties::s_ulKeepaliveValue
0x18000a3b8  add     rsp, 38h
0x18000a3bc  retn
```
