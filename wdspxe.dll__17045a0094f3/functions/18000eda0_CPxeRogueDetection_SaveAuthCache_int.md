# CPxeRogueDetection::SaveAuthCache(int)

- ea: `0x18000eda0`
- end: `0x18000eec4`
- name: `?SaveAuthCache@CPxeRogueDetection@@AEAAKH@Z`
- size: `292`
- prototype: `unsigned int __fastcall(CPxeRogueDetection *__hidden this, int)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18000abe4`

## callees

- `0x180002a30`
- `0x18000eda0`
- `0x180011068`

## import_xrefs

- `ADVAPI32!RegCloseKey` at `0x18000edf5`
- `ADVAPI32!RegCloseKey` at `0x18000eea5`
- `ADVAPI32!RegCloseKey` at `0x18000edf5`
- `ADVAPI32!RegCloseKey` at `0x18000eea5`
- `ADVAPI32!RegOpenKeyExW` at `0x18000eddb`
- `ADVAPI32!RegOpenKeyExW` at `0x18000eddb`
- `ADVAPI32!RegCreateKeyExW` at `0x18000ee3a`
- `ADVAPI32!RegCreateKeyExW` at `0x18000ee3a`
- `WdsCommonLib!?SetValueDword@CRegKey@@QEAAKPEBGK@Z` at `0x18000ee68`
- `WdsCommonLib!?SetValueDword@CRegKey@@QEAAKPEBGK@Z` at `0x18000ee68`

## string_xrefs

- `0x18000edc2`: `System\CurrentControlSet\Services\WDSServer\Providers\WDSPXE\AuthCache`
- `0x18000ee17`: `System\CurrentControlSet\Services\WDSServer\Providers\WDSPXE\AuthCache`
- `0x18000ee8a`: `Failed to cache Authentication Results (rc=%u)`

## pseudocode

```c
__int64 __fastcall CPxeRogueDetection::SaveAuthCache(const unsigned __int16 **this, unsigned int a2)
{
  unsigned int v4; // eax
  __int64 v5; // rdx
  __int64 v6; // r8
  unsigned int v7; // ebx
  unsigned int v8; // eax
  __int64 v9; // rdx
  __int64 v10; // r8
  HKEY hKey; // [rsp+70h] [rbp+18h] BYREF

  hKey = 0;
  if ( RegOpenKeyExW(
         HKEY_LOCAL_MACHINE,
         L"System\\CurrentControlSet\\Services\\WDSServer\\Providers\\WDSPXE\\AuthCache",
         0,
         0x20106u,
         &hKey) )
  {
    if ( hKey )
    {
      RegCloseKey(hKey);
      hKey = 0;
    }
    v4 = RegCreateKeyExW(
           HKEY_LOCAL_MACHINE,
           L"System\\CurrentControlSet\\Services\\WDSServer\\Providers\\WDSPXE\\AuthCache",
           0,
           0,
           0,
           0x20106u,
           0,
           &hKey,
           0);
    v7 = ElValidateWin32_4(v4, v5, v6, 842);
    if ( v7 )
      goto LABEL_6;
  }
  v8 = CRegKey::SetValueDword((CRegKey *)&hKey, this[29], a2);
  v7 = ElValidateWin32_4(v8, v9, v10, 848);
  if ( v7 )
LABEL_6:
    Trace(0x80000u, L"Failed to cache Authentication Results (rc=%u)", v7);
  if ( hKey )
    RegCloseKey(hKey);
  return v7;
}

```

## disassembly

```asm
0x18000eda0  mov     r11, rsp
0x18000eda3  mov     [r11+8], rbx
0x18000eda7  mov     [r11+10h], rsi
0x18000edab  push    rdi
0x18000edac  sub     rsp, 50h
0x18000edb0  and     qword ptr [r11+18h], 0
0x18000edb5  lea     rax, [r11+18h]
0x18000edb9  mov     edi, edx
0x18000edbb  mov     [r11-38h], rax
0x18000edbf  mov     rsi, rcx
0x18000edc2  lea     rdx, aSystemCurrentc_1; "System\\CurrentControlSet\\Services\\WD"...
0x18000edc9  mov     ebx, 20106h
0x18000edce  xor     r8d, r8d; ulOptions
0x18000edd1  mov     r9d, ebx; samDesired
0x18000edd4  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18000eddb  call    cs:__imp_RegOpenKeyExW
0x18000ede2  nop     dword ptr [rax+rax+00h]
0x18000ede7  test    eax, eax
0x18000ede9  jz      short loc_18000EE59
0x18000edeb  mov     rcx, [rsp+58h+hKey]; hKey
0x18000edf0  test    rcx, rcx
0x18000edf3  jz      short loc_18000EE07
0x18000edf5  call    cs:__imp_RegCloseKey
0x18000edfc  nop     dword ptr [rax+rax+00h]
0x18000ee01  and     [rsp+58h+hKey], 0
0x18000ee07  and     [rsp+58h+var_18], 0
0x18000ee0d  lea     rax, [rsp+58h+hKey]
0x18000ee12  mov     [rsp+58h+phkResult], rax; phkResult
0x18000ee17  lea     rdx, aSystemCurrentc_1; "System\\CurrentControlSet\\Services\\WD"...
0x18000ee1e  and     [rsp+58h+var_28], 0
0x18000ee24  xor     r9d, r9d; lpClass
0x18000ee27  mov     [rsp+58h+samDesired], ebx; samDesired
0x18000ee2b  xor     r8d, r8d; Reserved
0x18000ee2e  and     [rsp+58h+var_38], 0
0x18000ee33  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18000ee3a  call    cs:__imp_RegCreateKeyExW
0x18000ee41  nop     dword ptr [rax+rax+00h]
0x18000ee46  mov     ecx, eax
0x18000ee48  mov     r9d, 34Ah
0x18000ee4e  call    ElValidateWin32_4
0x18000ee53  mov     ebx, eax
0x18000ee55  test    eax, eax
0x18000ee57  jnz     short loc_18000EE87
0x18000ee59  mov     rdx, [rsi+0E8h]
0x18000ee60  lea     rcx, [rsp+58h+hKey]
0x18000ee65  mov     r8d, edi
0x18000ee68  call    cs:__imp_?SetValueDword@CRegKey@@QEAAKPEBGK@Z; CRegKey::SetValueDword(ushort const *,ulong)
0x18000ee6f  nop     dword ptr [rax+rax+00h]
0x18000ee74  mov     ecx, eax
0x18000ee76  mov     r9d, 350h
0x18000ee7c  call    ElValidateWin32_4
0x18000ee81  mov     ebx, eax
0x18000ee83  test    eax, eax
0x18000ee85  jz      short loc_18000EE9B
0x18000ee87  mov     r8d, ebx
0x18000ee8a  lea     rdx, aFailedToCacheA; "Failed to cache Authentication Results "...
0x18000ee91  mov     ecx, 80000h; unsigned int
0x18000ee96  call    ?Trace@@YAXKPEBGZZ; Trace(ulong,ushort const *,...)
0x18000ee9b  mov     rcx, [rsp+58h+hKey]; hKey
0x18000eea0  test    rcx, rcx
0x18000eea3  jz      short loc_18000EEB1
0x18000eea5  call    cs:__imp_RegCloseKey
0x18000eeac  nop     dword ptr [rax+rax+00h]
0x18000eeb1  mov     rsi, [rsp+58h+arg_8]
0x18000eeb6  mov     eax, ebx
0x18000eeb8  mov     rbx, [rsp+58h+arg_0]
0x18000eebd  add     rsp, 50h
0x18000eec1  pop     rdi
0x18000eec2  retn
```
