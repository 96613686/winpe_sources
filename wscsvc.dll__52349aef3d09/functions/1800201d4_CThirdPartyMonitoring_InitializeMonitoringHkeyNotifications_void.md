# CThirdPartyMonitoring::InitializeMonitoringHkeyNotifications(void)

- ea: `0x1800201d4`
- end: `0x180020276`
- name: `?InitializeMonitoringHkeyNotifications@CThirdPartyMonitoring@@AEAAJXZ`
- size: `162`
- prototype: `LSTATUS __fastcall(CThirdPartyMonitoring *this)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000a740`

## callees

- `0x1800201d4`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180020228`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180020228`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180020249`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180020249`
- `api-ms-win-core-registry-l1-1-0!RegNotifyChangeKeyValue` at `0x18002026c`
- `api-ms-win-core-registry-l1-1-0!RegNotifyChangeKeyValue` at `0x18002026c`

## string_xrefs

- `0x1800201f6`: `SOFTWARE\Microsoft\Security Center\Monitoring`

## pseudocode

```c
LSTATUS __fastcall CThirdPartyMonitoring::InitializeMonitoringHkeyNotifications(CThirdPartyMonitoring *this)
{
  HKEY *phkResult; // rbx
  HKEY v3; // rcx
  LSTATUS result; // eax
  bool v5; // cc

  phkResult = (HKEY *)((char *)this + 40);
  v3 = (HKEY)*((_QWORD *)this + 5);
  if ( v3 )
  {
    RegCloseKey(v3);
    *phkResult = 0;
  }
  result = RegCreateKeyExW(
             HKEY_LOCAL_MACHINE,
             L"SOFTWARE\\Microsoft\\Security Center\\Monitoring",
             0,
             0,
             0,
             0x10u,
             0,
             phkResult,
             0);
  v5 = result <= 0;
  if ( !result )
  {
    result = RegNotifyChangeKeyValue(*phkResult, 1, 7u, *((HANDLE *)this + 4), 1);
    v5 = result <= 0;
  }
  if ( !v5 )
    return (unsigned __int16)result | 0x80070000;
  return result;
}

```

## disassembly

```asm
0x1800201d4  mov     [rsp+arg_0], rbx
0x1800201d9  push    rdi
0x1800201da  sub     rsp, 50h
0x1800201de  lea     rbx, [rcx+28h]
0x1800201e2  mov     rdi, rcx
0x1800201e5  mov     rcx, [rbx]; hKey
0x1800201e8  test    rcx, rcx
0x1800201eb  jnz     short loc_180020249
0x1800201ed  mov     [rsp+58h+lpdwDisposition], 0; lpdwDisposition
0x1800201f6  lea     rdx, aSoftwareMicros_8; "SOFTWARE\\Microsoft\\Security Center\\M"...
0x1800201fd  mov     [rsp+58h+phkResult], rbx; phkResult
0x180020202  xor     r9d, r9d; lpClass
0x180020205  mov     [rsp+58h+lpSecurityAttributes], 0; lpSecurityAttributes
0x18002020e  xor     r8d, r8d; Reserved
0x180020211  mov     [rsp+58h+samDesired], 10h; samDesired
0x180020219  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180020220  mov     [rsp+58h+dwOptions], 0; dwOptions
0x180020228  call    cs:__imp_RegCreateKeyExW
0x18002022e  test    eax, eax
0x180020230  jz      short loc_180020258
0x180020232  jg      short loc_18002023F
0x180020234  mov     rbx, [rsp+58h+arg_0]
0x180020239  add     rsp, 50h
0x18002023d  pop     rdi
0x18002023e  retn
0x18002023f  movzx   eax, ax
0x180020242  or      eax, 80070000h
0x180020247  jmp     short loc_180020234
0x180020249  call    cs:__imp_RegCloseKey
0x18002024f  mov     qword ptr [rbx], 0
0x180020256  jmp     short loc_1800201ED
0x180020258  mov     r9, [rdi+20h]; hEvent
0x18002025c  mov     edx, 1; bWatchSubtree
0x180020261  mov     rcx, [rbx]; hKey
0x180020264  mov     [rsp+58h+dwOptions], edx; fAsynchronous
0x180020268  lea     r8d, [rdx+6]; dwNotifyFilter
0x18002026c  call    cs:__imp_RegNotifyChangeKeyValue
0x180020272  test    eax, eax
0x180020274  jmp     short loc_180020232
```
