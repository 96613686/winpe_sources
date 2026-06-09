# sub_1800EB2CC

- ea: `0x1800eb2cc`
- end: `0x1800eb5c2`
- name: `sub_1800EB2CC`
- size: `758`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800eb078`

## callees

- `0x1800994a0`
- `0x1800eb2cc`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800eb341`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800eb36e`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800eb39d`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800eb3d4`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800eb341`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800eb36e`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800eb39d`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800eb3d4`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800eb4e3`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800eb4f8`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800eb50d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800eb561`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800eb576`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800eb58b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800eb4e3`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800eb4f8`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800eb50d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800eb561`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800eb576`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800eb58b`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800eb42c`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800eb42c`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800eb473`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800eb4aa`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800eb473`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800eb4aa`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800eb54c`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800eb54c`

## pseudocode

```c
__int64 sub_1800EB2CC()
{
  LSTATUS v0; // eax
  HKEY v1; // rcx
  int v2; // ebx
  LSTATUS v3; // eax
  LSTATUS v4; // eax
  __int64 result; // rax
  HKEY v6; // [rsp+50h] [rbp-39h] BYREF
  DWORD cbData; // [rsp+58h] [rbp-31h] BYREF
  DWORD Type; // [rsp+5Ch] [rbp-2Dh] BYREF
  BYTE v9[4]; // [rsp+60h] [rbp-29h] BYREF
  HKEY phkResult; // [rsp+68h] [rbp-21h] BYREF
  HKEY hKey; // [rsp+70h] [rbp-19h] BYREF
  DWORD dwDisposition; // [rsp+78h] [rbp-11h] BYREF
  BYTE Data[80]; // [rsp+80h] [rbp-9h] BYREF

  *(_DWORD *)v9 = 30;
  cbData = 80;
  v6 = 0;
  Type = 4;
  phkResult = 0;
  hKey = 0;
  v0 = RegOpenKeyExW(HKEY_CURRENT_USER, L"SOFTWARE", 0, 0x20019u, &hKey);
  if ( v0 )
    v0 = RegOpenKeyExW(HKEY_CURRENT_USER, L"Software", 0, 0x20019u, &hKey);
  if ( hKey && !v0 )
    v0 = RegOpenKeyExW(hKey, L"Microsoft", 0, 0x20019u, &phkResult);
  if ( !phkResult )
  {
    v1 = v6;
    goto LABEL_16;
  }
  if ( v0 )
  {
LABEL_28:
    v1 = v6;
    goto LABEL_29;
  }
  v0 = RegOpenKeyExW(phkResult, L"Scrunch", 0, 0x20019u, &v6);
  if ( v0 == 2 )
  {
    dwDisposition = 0;
    v0 = RegCreateKeyExW(phkResult, L"Scrunch", 0, (LPWSTR)&Class, 0, 0xF003Fu, 0, &v6, &dwDisposition);
  }
  v1 = v6;
  if ( !v6 )
  {
LABEL_16:
    v2 = 0;
    if ( v0 )
      goto LABEL_29;
    goto LABEL_17;
  }
  if ( v0 )
    goto LABEL_29;
  v2 = 1;
  cbData = 4;
  v3 = RegQueryValueExW(v6, L"CPU Clock Speed", 0, &Type, Data, &cbData);
  v1 = v6;
  if ( !v3 )
  {
LABEL_17:
    if ( Type == 4 )
    {
      dword_18028FD2C = *(_DWORD *)Data;
      if ( v1 )
        RegCloseKey(v1);
      if ( phkResult )
        RegCloseKey(phkResult);
      if ( hKey )
        RegCloseKey(hKey);
      return (unsigned int)dword_18028FD2C;
    }
    if ( !v2 )
      goto LABEL_29;
    goto LABEL_26;
  }
  cbData = 4;
  v4 = RegQueryValueExW(v6, L"Adapt MHz", 0, &Type, Data, &cbData);
  v1 = v6;
  if ( !v4 )
  {
    v2 = 0;
    goto LABEL_17;
  }
LABEL_26:
  if ( (unsigned int)(*(_DWORD *)v9 - 100) <= 0x7C9C )
  {
    RegSetValueExW(v1, L"CPU Clock Speed", 0, 4u, v9, 4u);
    goto LABEL_28;
  }
LABEL_29:
  if ( v1 )
    RegCloseKey(v1);
  if ( phkResult )
    RegCloseKey(phkResult);
  if ( hKey )
    RegCloseKey(hKey);
  result = *(unsigned int *)v9;
  dword_18028FD2C = *(_DWORD *)v9;
  return result;
}

```

## disassembly

```asm
0x1800eb2cc  mov     [rsp-8+arg_0], rbx
0x1800eb2d1  mov     [rsp-8+arg_8], rsi
0x1800eb2d6  push    rbp
0x1800eb2d7  lea     rbp, [rsp-57h]
0x1800eb2dc  sub     rsp, 0E0h
0x1800eb2e3  mov     rax, cs:__security_cookie
0x1800eb2ea  xor     rax, rsp
0x1800eb2ed  mov     [rbp+57h+var_10], rax
0x1800eb2f1  lea     rax, [rbp+57h+hKey]
0x1800eb2f5  mov     dword ptr [rbp+57h+var_80], 1Eh
0x1800eb2fc  mov     ebx, 20019h
0x1800eb301  mov     [rbp+57h+cbData], 50h ; 'P'
0x1800eb308  mov     esi, 4
0x1800eb30d  mov     [rbp+57h+var_90], 0
0x1800eb315  mov     r9d, ebx; samDesired
0x1800eb318  mov     [rbp+57h+Type], esi
0x1800eb31b  xor     r8d, r8d; ulOptions
0x1800eb31e  mov     [rbp+57h+var_78], 0
0x1800eb326  lea     rdx, aSoftware; "SOFTWARE"
0x1800eb32d  mov     [rbp+57h+hKey], 0
0x1800eb335  mov     rcx, 0FFFFFFFF80000001h; hKey
0x1800eb33c  mov     [rsp+0E0h+phkResult], rax; phkResult
0x1800eb341  call    cs:RegOpenKeyExW
0x1800eb348  nop     dword ptr [rax+rax+00h]
0x1800eb34d  test    eax, eax
0x1800eb34f  jz      short loc_1800EB37A
0x1800eb351  lea     rax, [rbp+57h+hKey]
0x1800eb355  mov     r9d, ebx; samDesired
0x1800eb358  xor     r8d, r8d; ulOptions
0x1800eb35b  mov     [rsp+0E0h+phkResult], rax; phkResult
0x1800eb360  lea     rdx, aSoftware_0; "Software"
0x1800eb367  mov     rcx, 0FFFFFFFF80000001h; hKey
0x1800eb36e  call    cs:RegOpenKeyExW
0x1800eb375  nop     dword ptr [rax+rax+00h]
0x1800eb37a  mov     rcx, [rbp+57h+hKey]; hKey
0x1800eb37e  test    rcx, rcx
0x1800eb381  jz      short loc_1800EB3A9
0x1800eb383  test    eax, eax
0x1800eb385  jnz     short loc_1800EB3A9
0x1800eb387  lea     rax, [rbp+57h+var_78]
0x1800eb38b  mov     r9d, ebx; samDesired
0x1800eb38e  xor     r8d, r8d; ulOptions
0x1800eb391  mov     [rsp+0E0h+phkResult], rax; phkResult
0x1800eb396  lea     rdx, aMicrosoft; "Microsoft"
0x1800eb39d  call    cs:RegOpenKeyExW
0x1800eb3a4  nop     dword ptr [rax+rax+00h]
0x1800eb3a9  mov     rcx, [rbp+57h+var_78]; hKey
0x1800eb3ad  test    rcx, rcx
0x1800eb3b0  jz      loc_1800EB4C2
0x1800eb3b6  test    eax, eax
0x1800eb3b8  jnz     loc_1800EB558
0x1800eb3be  lea     rax, [rbp+57h+var_90]
0x1800eb3c2  mov     r9d, ebx; samDesired
0x1800eb3c5  xor     r8d, r8d; ulOptions
0x1800eb3c8  mov     [rsp+0E0h+phkResult], rax; phkResult
0x1800eb3cd  lea     rdx, aScrunch; "Scrunch"
0x1800eb3d4  call    cs:RegOpenKeyExW
0x1800eb3db  nop     dword ptr [rax+rax+00h]
0x1800eb3e0  cmp     eax, 2
0x1800eb3e3  jnz     short loc_1800EB438
0x1800eb3e5  mov     rcx, [rbp+57h+var_78]; hKey
0x1800eb3e9  lea     rax, [rbp+57h+dwDisposition]
0x1800eb3ed  mov     [rsp+0E0h+lpdwDisposition], rax; lpdwDisposition
0x1800eb3f2  lea     r9, Class; lpClass
0x1800eb3f9  lea     rax, [rbp+57h+var_90]
0x1800eb3fd  mov     [rbp+57h+dwDisposition], 0
0x1800eb404  mov     [rsp+0E0h+var_A8], rax; phkResult
0x1800eb409  lea     rdx, aScrunch; "Scrunch"
0x1800eb410  mov     [rsp+0E0h+lpSecurityAttributes], 0; lpSecurityAttributes
0x1800eb419  xor     r8d, r8d; Reserved
0x1800eb41c  mov     [rsp+0E0h+samDesired], 0F003Fh; samDesired
0x1800eb424  mov     dword ptr [rsp+0E0h+phkResult], 0; dwOptions
0x1800eb42c  call    cs:RegCreateKeyExW
0x1800eb433  nop     dword ptr [rax+rax+00h]
0x1800eb438  mov     rcx, [rbp+57h+var_90]; hKey
0x1800eb43c  test    rcx, rcx
0x1800eb43f  jz      loc_1800EB4C6
0x1800eb445  test    eax, eax
0x1800eb447  jnz     loc_1800EB55C
0x1800eb44d  lea     ebx, [rax+1]
0x1800eb450  mov     [rbp+57h+cbData], esi
0x1800eb453  lea     rax, [rbp+57h+cbData]
0x1800eb457  xor     r8d, r8d; lpReserved
0x1800eb45a  mov     qword ptr [rsp+0E0h+samDesired], rax; lpcbData
0x1800eb45f  lea     r9, [rbp+57h+Type]; lpType
0x1800eb463  lea     rax, [rbp+57h+Data]
0x1800eb467  lea     rdx, aCpuClockSpeed; "CPU Clock Speed"
0x1800eb46e  mov     [rsp+0E0h+phkResult], rax; lpData
0x1800eb473  call    cs:RegQueryValueExW
0x1800eb47a  nop     dword ptr [rax+rax+00h]
0x1800eb47f  mov     rcx, [rbp+57h+var_90]; hKey
0x1800eb483  test    eax, eax
0x1800eb485  jz      short loc_1800EB4D0
0x1800eb487  lea     rax, [rbp+57h+cbData]
0x1800eb48b  mov     [rbp+57h+cbData], esi
0x1800eb48e  mov     qword ptr [rsp+0E0h+samDesired], rax; lpcbData
0x1800eb493  lea     r9, [rbp+57h+Type]; lpType
0x1800eb497  lea     rax, [rbp+57h+Data]
0x1800eb49b  xor     r8d, r8d; lpReserved
0x1800eb49e  lea     rdx, aAdaptMhz; "Adapt MHz"
0x1800eb4a5  mov     [rsp+0E0h+phkResult], rax; lpData
0x1800eb4aa  call    cs:RegQueryValueExW
0x1800eb4b1  nop     dword ptr [rax+rax+00h]
0x1800eb4b6  mov     rcx, [rbp+57h+var_90]
0x1800eb4ba  test    eax, eax
0x1800eb4bc  jnz     short loc_1800EB525
0x1800eb4be  xor     ebx, ebx
0x1800eb4c0  jmp     short loc_1800EB4D0
0x1800eb4c2  mov     rcx, [rbp+57h+var_90]; hKey
0x1800eb4c6  xor     ebx, ebx
0x1800eb4c8  test    eax, eax
0x1800eb4ca  jnz     loc_1800EB55C
0x1800eb4d0  cmp     [rbp+57h+Type], esi
0x1800eb4d3  jnz     short loc_1800EB521
0x1800eb4d5  mov     eax, dword ptr [rbp+57h+Data]
0x1800eb4d8  mov     cs:dword_18028FD2C, eax
0x1800eb4de  test    rcx, rcx
0x1800eb4e1  jz      short loc_1800EB4EF
0x1800eb4e3  call    cs:RegCloseKey
0x1800eb4ea  nop     dword ptr [rax+rax+00h]
0x1800eb4ef  mov     rcx, [rbp+57h+var_78]; hKey
0x1800eb4f3  test    rcx, rcx
0x1800eb4f6  jz      short loc_1800EB504
0x1800eb4f8  call    cs:RegCloseKey
0x1800eb4ff  nop     dword ptr [rax+rax+00h]
0x1800eb504  mov     rcx, [rbp+57h+hKey]; hKey
0x1800eb508  test    rcx, rcx
0x1800eb50b  jz      short loc_1800EB519
0x1800eb50d  call    cs:RegCloseKey
0x1800eb514  nop     dword ptr [rax+rax+00h]
0x1800eb519  mov     eax, cs:dword_18028FD2C
0x1800eb51f  jmp     short loc_1800EB5A0
0x1800eb521  test    ebx, ebx
0x1800eb523  jz      short loc_1800EB55C
0x1800eb525  mov     eax, dword ptr [rbp+57h+var_80]
0x1800eb528  add     eax, 0FFFFFF9Ch
0x1800eb52b  cmp     eax, 7C9Ch
0x1800eb530  ja      short loc_1800EB55C
0x1800eb532  lea     rax, [rbp+57h+var_80]
0x1800eb536  mov     [rsp+0E0h+samDesired], esi; cbData
0x1800eb53a  mov     r9d, esi; dwType
0x1800eb53d  mov     [rsp+0E0h+phkResult], rax; lpData
0x1800eb542  xor     r8d, r8d; Reserved
0x1800eb545  lea     rdx, aCpuClockSpeed; "CPU Clock Speed"
0x1800eb54c  call    cs:RegSetValueExW
0x1800eb553  nop     dword ptr [rax+rax+00h]
0x1800eb558  mov     rcx, [rbp+57h+var_90]; hKey
0x1800eb55c  test    rcx, rcx
0x1800eb55f  jz      short loc_1800EB56D
0x1800eb561  call    cs:RegCloseKey
0x1800eb568  nop     dword ptr [rax+rax+00h]
0x1800eb56d  mov     rcx, [rbp+57h+var_78]; hKey
0x1800eb571  test    rcx, rcx
0x1800eb574  jz      short loc_1800EB582
0x1800eb576  call    cs:RegCloseKey
0x1800eb57d  nop     dword ptr [rax+rax+00h]
0x1800eb582  mov     rcx, [rbp+57h+hKey]; hKey
0x1800eb586  test    rcx, rcx
0x1800eb589  jz      short loc_1800EB597
0x1800eb58b  call    cs:RegCloseKey
0x1800eb592  nop     dword ptr [rax+rax+00h]
0x1800eb597  mov     eax, dword ptr [rbp+57h+var_80]
0x1800eb59a  mov     cs:dword_18028FD2C, eax
0x1800eb5a0  mov     rcx, [rbp+57h+var_10]
0x1800eb5a4  xor     rcx, rsp; StackCookie
0x1800eb5a7  call    __security_check_cookie
0x1800eb5ac  lea     r11, [rsp+0E0h+var_s0]
0x1800eb5b4  mov     rbx, [r11+10h]
0x1800eb5b8  mov     rsi, [r11+18h]
0x1800eb5bc  mov     rsp, r11
0x1800eb5bf  pop     rbp
0x1800eb5c0  retn
```
