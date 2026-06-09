# ScInitStartTimeout(void)

- ea: `0x1400103b4`
- end: `0x140010534`
- name: `?ScInitStartTimeout@@YAXXZ`
- size: `384`
- prototype: `void(void)`
- caller_count: `2`
- callee_count: `1`
- tags: `registry_config, loader_planting, service_task`

## callers

- `0x140007180`
- `0x140010064`

## callees

- `0x1400103b4`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x140010447`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1400104fe`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x140010447`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1400104fe`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x140010416`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1400104cd`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x140010416`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1400104cd`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140010461`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140010518`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140010461`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140010518`
- `ntdll!RtlGetNtProductType` at `0x140010477`
- `ntdll!RtlGetNtProductType` at `0x140010477`

## string_xrefs

- `0x14001043b`: `ServiceStartTimeout`
- `0x1400104f2`: `FuzzServiceStart`

## pseudocode

```c
void ScInitStartTimeout(void)
{
  DWORD v0; // eax
  DWORD Type; // [rsp+50h] [rbp+18h] BYREF
  _NT_PRODUCT_TYPE ProductType; // [rsp+58h] [rbp+20h] BYREF
  DWORD cbData; // [rsp+60h] [rbp+28h] BYREF
  HKEY hKey; // [rsp+68h] [rbp+30h] BYREF

  ProductType = 0;
  if ( !g_ServiceStartTimeout )
  {
    hKey = 0;
    Type = 0;
    cbData = 4;
    g_ServiceStartTimeout = 0;
    if ( !RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"System\\CurrentControlSet\\Control", 0, 0x20019u, &hKey) )
    {
      if ( !RegQueryValueExW(hKey, L"ServiceStartTimeout", 0, &Type, (LPBYTE)&g_ServiceStartTimeout, &cbData)
        && Type != 4 )
      {
        g_ServiceStartTimeout = 0;
      }
      RegCloseKey(hKey);
    }
    if ( !g_ServiceStartTimeout )
    {
      RtlGetNtProductType(&ProductType);
      v0 = 50000;
      if ( ProductType != NtProductWinNt )
        v0 = 80000;
      g_ServiceStartTimeout = v0;
    }
  }
  if ( g_ServiceStartFuzzing == 255 )
  {
    hKey = 0;
    Type = 0;
    cbData = 4;
    *(_DWORD *)&g_ServiceStartFuzzingMaxDelay = 0;
    if ( !RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"System\\CurrentControlSet\\Control", 0, 0x20019u, &hKey) )
    {
      if ( !RegQueryValueExW(hKey, L"FuzzServiceStart", 0, &Type, &g_ServiceStartFuzzingMaxDelay, &cbData) && Type != 4 )
        *(_DWORD *)&g_ServiceStartFuzzingMaxDelay = 0;
      RegCloseKey(hKey);
    }
    g_ServiceStartFuzzing = *(_DWORD *)&g_ServiceStartFuzzingMaxDelay != 0;
  }
}

```

## disassembly

```asm
0x1400103b4  push    rbp
0x1400103b6  push    rbx
0x1400103b7  mov     rbp, rsp
0x1400103ba  sub     rsp, 38h
0x1400103be  xor     ebx, ebx
0x1400103c0  cmp     cs:?g_ServiceStartTimeout@@3KA, ebx; ulong g_ServiceStartTimeout
0x1400103c6  mov     [rbp+ProductType], ebx
0x1400103c9  jz      short loc_1400103E2
0x1400103cb  cmp     cs:?g_ServiceStartFuzzing@@3W4_TRI_BOOL@@A, 0FFh; _TRI_BOOL g_ServiceStartFuzzing
0x1400103d5  jz      loc_140010499
0x1400103db  add     rsp, 38h
0x1400103df  pop     rbx
0x1400103e0  pop     rbp
0x1400103e1  retn
0x1400103e2  lea     rax, [rbp+hKey]
0x1400103e6  mov     [rbp+hKey], rbx
0x1400103ea  mov     r9d, 20019h; samDesired
0x1400103f0  mov     [rsp+38h+phkResult], rax; phkResult
0x1400103f5  xor     r8d, r8d; ulOptions
0x1400103f8  mov     [rbp+Type], ebx
0x1400103fb  lea     rdx, aSystemCurrentc_2; "System\\CurrentControlSet\\Control"
0x140010402  mov     [rbp+cbData], 4
0x140010409  mov     rcx, 0FFFFFFFF80000002h; hKey
0x140010410  mov     cs:?g_ServiceStartTimeout@@3KA, ebx; ulong g_ServiceStartTimeout
0x140010416  call    cs:__imp_RegOpenKeyExW
0x14001041c  test    eax, eax
0x14001041e  jnz     short loc_140010467
0x140010420  mov     rcx, [rbp+hKey]; hKey
0x140010424  lea     rax, [rbp+cbData]
0x140010428  mov     [rsp+38h+lpcbData], rax; lpcbData
0x14001042d  lea     r9, [rbp+Type]; lpType
0x140010431  lea     rax, ?g_ServiceStartTimeout@@3KA; ulong g_ServiceStartTimeout
0x140010438  xor     r8d, r8d; lpReserved
0x14001043b  lea     rdx, aServicestartti; "ServiceStartTimeout"
0x140010442  mov     [rsp+38h+phkResult], rax; lpData
0x140010447  call    cs:__imp_RegQueryValueExW
0x14001044d  test    eax, eax
0x14001044f  jnz     short loc_14001045D
0x140010451  cmp     [rbp+Type], 4
0x140010455  jz      short loc_14001045D
0x140010457  mov     cs:?g_ServiceStartTimeout@@3KA, ebx; ulong g_ServiceStartTimeout
0x14001045d  mov     rcx, [rbp+hKey]; hKey
0x140010461  call    cs:__imp_RegCloseKey
0x140010467  cmp     cs:?g_ServiceStartTimeout@@3KA, ebx; ulong g_ServiceStartTimeout
0x14001046d  jnz     loc_1400103CB
0x140010473  lea     rcx, [rbp+ProductType]; ProductType
0x140010477  call    cs:__imp_RtlGetNtProductType
0x14001047d  cmp     [rbp+ProductType], 1
0x140010481  mov     eax, 0C350h
0x140010486  mov     ecx, 13880h
0x14001048b  cmovnz  eax, ecx
0x14001048e  mov     cs:?g_ServiceStartTimeout@@3KA, eax; ulong g_ServiceStartTimeout
0x140010494  jmp     loc_1400103CB
0x140010499  lea     rax, [rbp+hKey]
0x14001049d  mov     [rbp+hKey], rbx
0x1400104a1  mov     r9d, 20019h; samDesired
0x1400104a7  mov     [rsp+38h+phkResult], rax; phkResult
0x1400104ac  xor     r8d, r8d; ulOptions
0x1400104af  mov     [rbp+Type], ebx
0x1400104b2  lea     rdx, aSystemCurrentc_2; "System\\CurrentControlSet\\Control"
0x1400104b9  mov     [rbp+cbData], 4
0x1400104c0  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1400104c7  mov     cs:?g_ServiceStartFuzzingMaxDelay@@3KA, ebx; ulong g_ServiceStartFuzzingMaxDelay
0x1400104cd  call    cs:__imp_RegOpenKeyExW
0x1400104d3  test    eax, eax
0x1400104d5  jnz     short loc_14001051E
0x1400104d7  mov     rcx, [rbp+hKey]; hKey
0x1400104db  lea     rax, [rbp+cbData]
0x1400104df  mov     [rsp+38h+lpcbData], rax; lpcbData
0x1400104e4  lea     r9, [rbp+Type]; lpType
0x1400104e8  lea     rax, ?g_ServiceStartFuzzingMaxDelay@@3KA; ulong g_ServiceStartFuzzingMaxDelay
0x1400104ef  xor     r8d, r8d; lpReserved
0x1400104f2  lea     rdx, aFuzzservicesta; "FuzzServiceStart"
0x1400104f9  mov     [rsp+38h+phkResult], rax; lpData
0x1400104fe  call    cs:__imp_RegQueryValueExW
0x140010504  test    eax, eax
0x140010506  jnz     short loc_140010514
0x140010508  cmp     [rbp+Type], 4
0x14001050c  jz      short loc_140010514
0x14001050e  mov     cs:?g_ServiceStartFuzzingMaxDelay@@3KA, ebx; ulong g_ServiceStartFuzzingMaxDelay
0x140010514  mov     rcx, [rbp+hKey]; hKey
0x140010518  call    cs:__imp_RegCloseKey
0x14001051e  cmp     cs:?g_ServiceStartFuzzingMaxDelay@@3KA, ebx; ulong g_ServiceStartFuzzingMaxDelay
0x140010524  mov     eax, ebx
0x140010526  setnz   al
0x140010529  mov     cs:?g_ServiceStartFuzzing@@3W4_TRI_BOOL@@A, eax; _TRI_BOOL g_ServiceStartFuzzing
0x14001052f  jmp     loc_1400103DB
```
