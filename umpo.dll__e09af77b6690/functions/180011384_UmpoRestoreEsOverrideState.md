# UmpoRestoreEsOverrideState

- ea: `0x180011384`
- end: `0x18001143c`
- name: `UmpoRestoreEsOverrideState`
- size: `184`
- prototype: `LSTATUS()`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180010e38`

## callees

- `0x180011384`

## import_xrefs

- `ntdll!RtlPublishWnfStateData` at `0x180011431`
- `ntdll!RtlPublishWnfStateData` at `0x180011431`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180011405`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180011405`
- `api-ms-win-stateseparation-helpers-l1-1-0!GetPersistedRegistryLocationW` at `0x1800113c3`
- `api-ms-win-stateseparation-helpers-l1-1-0!GetPersistedRegistryLocationW` at `0x1800113c3`

## pseudocode

```c
LSTATUS UmpoRestoreEsOverrideState()
{
  LSTATUS result; // eax
  int pvData; // [rsp+50h] [rbp+8h] BYREF
  DWORD pcbData; // [rsp+58h] [rbp+10h] BYREF
  int v3; // [rsp+60h] [rbp+18h] BYREF

  v3 = 1;
  pvData = 2;
  pcbData = 4;
  result = GetPersistedRegistryLocationW(
             L"Power",
             L"System\\CurrentControlSet\\Control\\Power",
             &UmpoEcoModeRedirectedRegistryPath,
             128,
             0);
  if ( !result )
  {
    result = RegGetValueW(
               HKEY_LOCAL_MACHINE,
               &UmpoEcoModeRedirectedRegistryPath,
               L"EnergySaverState",
               0x18u,
               0,
               &pvData,
               &pcbData);
    if ( !result && pvData == 1 )
      return RtlPublishWnfStateData(WNF_PO_ENERGY_SAVER_OVERRIDE, 0, &v3, 4, 0);
  }
  return result;
}

```

## disassembly

```asm
0x180011384  mov     rax, rsp
0x180011387  sub     rsp, 48h
0x18001138b  mov     r9d, 80h
0x180011391  mov     dword ptr [rax+18h], 1
0x180011398  lea     r8, UmpoEcoModeRedirectedRegistryPath
0x18001139f  mov     dword ptr [rax+8], 2
0x1800113a6  lea     rdx, aSystemCurrentc; "System\\CurrentControlSet\\Control\\Pow"...
0x1800113ad  mov     dword ptr [rax+10h], 4
0x1800113b4  lea     rcx, ServiceName; "Power"
0x1800113bb  mov     qword ptr [rax-28h], 0
0x1800113c3  call    cs:__imp_GetPersistedRegistryLocationW
0x1800113c9  test    eax, eax
0x1800113cb  jnz     short loc_180011437
0x1800113cd  lea     rax, [rsp+48h+arg_8]
0x1800113d2  mov     r9d, 18h; dwFlags
0x1800113d8  mov     [rsp+48h+pcbData], rax; pcbData
0x1800113dd  lea     r8, aEnergysaversta; "EnergySaverState"
0x1800113e4  lea     rax, [rsp+48h+arg_0]
0x1800113e9  mov     rcx, 0FFFFFFFF80000002h; hkey
0x1800113f0  mov     [rsp+48h+pvData], rax; pvData
0x1800113f5  lea     rdx, UmpoEcoModeRedirectedRegistryPath; lpSubKey
0x1800113fc  mov     [rsp+48h+pdwType], 0; pdwType
0x180011405  call    cs:__imp_RegGetValueW
0x18001140b  test    eax, eax
0x18001140d  jnz     short loc_180011437
0x18001140f  cmp     [rsp+48h+arg_0], 1
0x180011414  jnz     short loc_180011437
0x180011416  mov     rcx, cs:WNF_PO_ENERGY_SAVER_OVERRIDE
0x18001141d  lea     r9d, [rax+4]
0x180011421  lea     r8, [rsp+48h+arg_10]
0x180011426  mov     [rsp+48h+pdwType], 0
0x18001142f  xor     edx, edx
0x180011431  call    cs:__imp_RtlPublishWnfStateData
0x180011437  add     rsp, 48h
0x18001143b  retn
```
