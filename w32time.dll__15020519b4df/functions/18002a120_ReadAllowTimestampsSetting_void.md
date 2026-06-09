# ReadAllowTimestampsSetting(void)

- ea: `0x18002a120`
- end: `0x18002a337`
- name: `?ReadAllowTimestampsSetting@@YAKXZ`
- size: `535`
- prototype: `unsigned int(void)`
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config, service_task`

## callers

- `0x1800239c4`
- `0x1800301f8`

## callees

- `0x18002a120`
- `0x18003d270`
- `0x18003dd2c`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002a197`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002a294`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002a197`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002a294`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002a2f7`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002a329`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800675a2`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800675b8`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002a2f7`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002a329`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800675a2`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800675b8`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18002a239`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18002a2d2`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18002a239`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18002a2d2`
- `api-ms-win-stateseparation-helpers-l1-1-0!GetPersistedRegistryLocationW` at `0x18002a1c4`
- `api-ms-win-stateseparation-helpers-l1-1-0!GetPersistedRegistryLocationW` at `0x18002a1c4`

## string_xrefs

- `0x18002a1bd`: `W32TimeConfig`
- `0x18002a189`: `System\CurrentControlSet\Services\W32Time\Config`

## pseudocode

```c
__int64 ReadAllowTimestampsSetting(void)
{
  HKEY v0; // rbx
  LSTATUS ValueW; // eax
  bool v2; // sf
  DWORD pcbData; // [rsp+40h] [rbp-258h] BYREF
  unsigned int pvData; // [rsp+44h] [rbp-254h] BYREF
  DWORD pdwType; // [rsp+48h] [rbp-250h] BYREF
  HKEY hKey; // [rsp+50h] [rbp-248h] BYREF
  HKEY hkey; // [rsp+58h] [rbp-240h] BYREF
  DWORD v9; // [rsp+60h] [rbp-238h]
  WCHAR SubKey; // [rsp+70h] [rbp-228h] BYREF
  _BYTE v11[526]; // [rsp+72h] [rbp-226h] BYREF

  hKey = 0;
  hkey = 0;
  pvData = 1;
  v9 = 4;
  pdwType = 0;
  SubKey = 0;
  memset_0(v11, 0, 0x206u);
  if ( !RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"System\\CurrentControlSet\\Services\\W32Time\\Config", 0, 1u, &hkey) )
  {
    if ( !(unsigned int)GetPersistedRegistryLocationW(L"W32TimeConfig", 0, &SubKey, 520, 0) )
      RegOpenKeyExW(HKEY_LOCAL_MACHINE, &SubKey, 0, 1u, &hKey);
    v0 = hkey;
    pcbData = 4;
    ValueW = 2;
    if ( hKey )
      ValueW = RegGetValueW(hKey, 0, L"AllowTimeStamps", 0xFFFFu, &pdwType, &pvData, &pcbData);
    if ( ValueW == 2 )
    {
      pcbData = 4;
      ValueW = RegGetValueW(v0, 0, L"AllowTimeStamps", 0xFFFFu, &pdwType, &pvData, &pcbData);
    }
    v2 = ValueW < 0;
    if ( ValueW )
    {
      if ( ValueW > 0 )
        v2 = 1;
      if ( v2 )
        goto LABEL_15;
    }
    else
    {
      v9 = pcbData;
    }
    if ( pdwType == 4 )
      goto LABEL_16;
LABEL_15:
    pvData = 1;
  }
LABEL_16:
  if ( hKey )
    RegCloseKey(hKey);
  if ( hkey )
    RegCloseKey(hkey);
  return pvData;
}

```

## disassembly

```asm
0x18002a120  mov     [rsp+arg_0], rbx
0x18002a125  push    rdi
0x18002a126  sub     rsp, 290h
0x18002a12d  mov     rax, cs:__security_cookie
0x18002a134  xor     rax, rsp
0x18002a137  mov     [rsp+298h+var_18], rax
0x18002a13f  xor     edi, edi
0x18002a141  mov     [rsp+298h+hKey], rdi
0x18002a146  mov     [rsp+298h+hkey], rdi
0x18002a14b  mov     [rsp+298h+var_254], 1
0x18002a153  mov     [rsp+298h+var_238], 4
0x18002a15b  mov     [rsp+298h+pdwType], edi
0x18002a15f  mov     [rsp+298h+SubKey], di
0x18002a164  xor     edx, edx; Val
0x18002a166  mov     r8d, 206h; Size
0x18002a16c  lea     rcx, [rsp+298h+var_226]; void *
0x18002a171  call    memset_0
0x18002a176  lea     rax, [rsp+298h+hkey]
0x18002a17b  mov     [rsp+298h+phkResult], rax; phkResult
0x18002a180  mov     r9d, 1; samDesired
0x18002a186  xor     r8d, r8d; ulOptions
0x18002a189  lea     rdx, aSystemCurrentc; "System\\CurrentControlSet\\Services\\W3"...
0x18002a190  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18002a197  call    cs:__imp_RegOpenKeyExW
0x18002a19e  nop     dword ptr [rax+rax+00h]
0x18002a1a3  test    eax, eax
0x18002a1a5  jnz     loc_18002A2E3
0x18002a1ab  mov     [rsp+298h+phkResult], rdi
0x18002a1b0  mov     r9d, 208h
0x18002a1b6  lea     r8, [rsp+298h+SubKey]
0x18002a1bb  xor     edx, edx
0x18002a1bd  lea     rcx, aW32timeconfig; "W32TimeConfig"
0x18002a1c4  call    cs:__imp_GetPersistedRegistryLocationW
0x18002a1cb  nop     dword ptr [rax+rax+00h]
0x18002a1d0  test    eax, eax
0x18002a1d2  jz      loc_18002A275
0x18002a1d8  mov     rbx, [rsp+298h+hkey]
0x18002a1dd  mov     rcx, [rsp+298h+hKey]; hkey
0x18002a1e2  mov     [rsp+298h+var_258], edi
0x18002a1e6  mov     [rsp+298h+var_258], 4
0x18002a1ee  mov     eax, 2
0x18002a1f3  test    rcx, rcx
0x18002a1f6  jnz     loc_18002A2A5
0x18002a1fc  cmp     eax, 2
0x18002a1ff  jnz     short loc_18002A245
0x18002a201  mov     [rsp+298h+var_258], 4
0x18002a209  lea     rax, [rsp+298h+var_258]
0x18002a20e  mov     [rsp+298h+pcbData], rax; pcbData
0x18002a213  lea     rax, [rsp+298h+var_254]
0x18002a218  mov     [rsp+298h+pvData], rax; pvData
0x18002a21d  lea     rax, [rsp+298h+pdwType]
0x18002a222  mov     [rsp+298h+phkResult], rax; pdwType
0x18002a227  mov     r9d, 0FFFFh; dwFlags
0x18002a22d  lea     r8, aAllowtimestamp; "AllowTimeStamps"
0x18002a234  xor     edx, edx; lpSubKey
0x18002a236  mov     rcx, rbx; hkey
0x18002a239  call    cs:__imp_RegGetValueW
0x18002a240  nop     dword ptr [rax+rax+00h]
0x18002a245  test    eax, eax
0x18002a247  jnz     short loc_18002A25D
0x18002a249  mov     eax, [rsp+298h+var_258]
0x18002a24d  mov     [rsp+298h+var_238], eax
0x18002a251  cmp     [rsp+298h+pdwType], 4
0x18002a256  jnz     short loc_18002A26B
0x18002a258  jmp     loc_18002A2E3
0x18002a25d  jle     short loc_18002A269
0x18002a25f  movzx   eax, ax
0x18002a262  or      eax, 80070000h
0x18002a267  test    eax, eax
0x18002a269  jns     short loc_18002A251
0x18002a26b  mov     [rsp+298h+var_254], 1
0x18002a273  jmp     short loc_18002A2E3
0x18002a275  lea     rax, [rsp+298h+hKey]
0x18002a27a  mov     [rsp+298h+phkResult], rax; phkResult
0x18002a27f  mov     r9d, 1; samDesired
0x18002a285  xor     r8d, r8d; ulOptions
0x18002a288  lea     rdx, [rsp+298h+SubKey]; lpSubKey
0x18002a28d  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18002a294  call    cs:__imp_RegOpenKeyExW
0x18002a29b  nop     dword ptr [rax+rax+00h]
0x18002a2a0  jmp     loc_18002A1D8
0x18002a2a5  lea     rax, [rsp+298h+var_258]
0x18002a2aa  mov     [rsp+298h+pcbData], rax; pcbData
0x18002a2af  lea     rax, [rsp+298h+var_254]
0x18002a2b4  mov     [rsp+298h+pvData], rax; pvData
0x18002a2b9  lea     rax, [rsp+298h+pdwType]
0x18002a2be  mov     [rsp+298h+phkResult], rax; pdwType
0x18002a2c3  mov     r9d, 0FFFFh; dwFlags
0x18002a2c9  lea     r8, aAllowtimestamp; "AllowTimeStamps"
0x18002a2d0  xor     edx, edx; lpSubKey
0x18002a2d2  call    cs:__imp_RegGetValueW
0x18002a2d9  nop     dword ptr [rax+rax+00h]
0x18002a2de  jmp     loc_18002A1FC
0x18002a2e3  mov     rcx, [rsp+298h+hKey]; hKey
0x18002a2e8  test    rcx, rcx
0x18002a2eb  jnz     short loc_18002A329
0x18002a2ed  mov     rcx, [rsp+298h+hkey]; hKey
0x18002a2f2  test    rcx, rcx
0x18002a2f5  jz      short loc_18002A303
0x18002a2f7  call    cs:__imp_RegCloseKey
0x18002a2fe  nop     dword ptr [rax+rax+00h]
0x18002a303  mov     eax, [rsp+298h+var_254]
0x18002a307  mov     rcx, [rsp+298h+var_18]
0x18002a30f  xor     rcx, rsp; StackCookie
0x18002a312  call    __security_check_cookie
0x18002a317  mov     rbx, [rsp+298h+arg_0]
0x18002a31f  add     rsp, 290h
0x18002a326  pop     rdi
0x18002a327  retn
0x18002a329  call    cs:__imp_RegCloseKey
0x18002a330  nop     dword ptr [rax+rax+00h]
0x18002a335  jmp     short loc_18002A2ED
0x180067590  push    rbp
0x180067592  sub     rsp, 40h
0x180067596  mov     rbp, rdx
0x180067599  mov     rcx, [rbp+50h]; hKey
0x18006759d  test    rcx, rcx
0x1800675a0  jz      short loc_1800675AF
0x1800675a2  call    cs:__imp_RegCloseKey
0x1800675a9  nop     dword ptr [rax+rax+00h]
0x1800675ae  nop
0x1800675af  mov     rcx, [rbp+58h]; hKey
0x1800675b3  test    rcx, rcx
0x1800675b6  jz      short loc_1800675C5
0x1800675b8  call    cs:__imp_RegCloseKey
0x1800675bf  nop     dword ptr [rax+rax+00h]
0x1800675c4  nop
0x1800675c5  add     rsp, 40h
0x1800675c9  pop     rbp
0x1800675ca  retn
```
