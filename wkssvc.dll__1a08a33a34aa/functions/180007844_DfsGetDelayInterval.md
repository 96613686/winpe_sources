# DfsGetDelayInterval

- ea: `0x180007844`
- end: `0x180007951`
- name: `DfsGetDelayInterval`
- size: `269`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18002f910`

## callees

- `0x180007844`
- `0x180007958`
- `0x180007a90`
- `0x180007acc`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180007893`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180007893`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800078d9`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800078d9`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800078c7`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800078c7`

## pseudocode

```c
__int64 DfsGetDelayInterval()
{
  __int64 v0; // rdx
  HKEY v1; // r8
  LSTATUS v2; // ebx
  int ConfigDword; // ebx
  __int64 result; // rax
  _QWORD v5[3]; // [rsp+30h] [rbp-18h] BYREF
  unsigned int Data; // [rsp+60h] [rbp+18h] BYREF
  DWORD Type; // [rsp+68h] [rbp+20h] BYREF
  DWORD cbData; // [rsp+70h] [rbp+28h] BYREF
  HKEY hKey; // [rsp+78h] [rbp+30h] BYREF

  v5[0] = 0;
  hKey = 0;
  Data = 0;
  cbData = 4;
  Type = 0;
  if ( (RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"Software\\Policies\\Microsoft\\System\\DFSClient", 0, 0x20019u, &hKey)
     || (v2 = RegQueryValueExW(hKey, L"DfsDcNameDelay", 0, &Type, (LPBYTE)&Data, &cbData), RegCloseKey(hKey), v2)
     || Type != 4)
    && ((unsigned int)NetpOpenConfigDataEx(v5, v0, v1, 1)
     || (ConfigDword = NetpGetConfigDword(v5[0], L"DfsDcNameDelay", 15, &Data), NetpCloseConfigData(v5[0]), ConfigDword)) )
  {
    result = 15;
  }
  else
  {
    result = Data;
  }
  if ( (unsigned int)result > 0x3C )
    return 60;
  if ( (unsigned int)result < 0xF )
    return 15;
  return result;
}

```

## disassembly

```asm
0x180007844  push    rbp
0x180007846  push    rbx
0x180007847  mov     rbp, rsp
0x18000784a  sub     rsp, 48h
0x18000784e  lea     rax, [rbp+hKey]
0x180007852  mov     [rbp+var_18], 0
0x18000785a  mov     r9d, 20019h; samDesired
0x180007860  mov     [rsp+48h+phkResult], rax; phkResult
0x180007865  xor     r8d, r8d; ulOptions
0x180007868  mov     [rbp+hKey], 0
0x180007870  lea     rdx, aSoftwarePolici; "Software\\Policies\\Microsoft\\System\\"...
0x180007877  mov     [rbp+Data], 0
0x18000787e  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180007885  mov     [rbp+cbData], 4
0x18000788c  mov     [rbp+Type], 0
0x180007893  call    cs:__imp_RegOpenKeyExW
0x18000789a  nop     dword ptr [rax+rax+00h]
0x18000789f  test    eax, eax
0x1800078a1  jnz     short loc_1800078EF
0x1800078a3  mov     rcx, [rbp+hKey]; hKey
0x1800078a7  lea     rax, [rbp+cbData]
0x1800078ab  mov     [rsp+48h+lpcbData], rax; lpcbData
0x1800078b0  lea     r9, [rbp+Type]; lpType
0x1800078b4  lea     rax, [rbp+Data]
0x1800078b8  xor     r8d, r8d; lpReserved
0x1800078bb  lea     rdx, aDfsdcnamedelay; "DfsDcNameDelay"
0x1800078c2  mov     [rsp+48h+phkResult], rax; lpData
0x1800078c7  call    cs:__imp_RegQueryValueExW
0x1800078ce  nop     dword ptr [rax+rax+00h]
0x1800078d3  mov     rcx, [rbp+hKey]; hKey
0x1800078d7  mov     ebx, eax
0x1800078d9  call    cs:__imp_RegCloseKey
0x1800078e0  nop     dword ptr [rax+rax+00h]
0x1800078e5  test    ebx, ebx
0x1800078e7  jnz     short loc_1800078EF
0x1800078e9  cmp     [rbp+Type], 4
0x1800078ed  jz      short loc_180007929
0x1800078ef  mov     r9d, 1
0x1800078f5  lea     rcx, [rbp+var_18]
0x1800078f9  call    NetpOpenConfigDataEx
0x1800078fe  test    eax, eax
0x180007900  jnz     short loc_18000792E
0x180007902  mov     rcx, [rbp+var_18]
0x180007906  lea     r9, [rbp+Data]
0x18000790a  lea     r8d, [rax+0Fh]
0x18000790e  lea     rdx, aDfsdcnamedelay; "DfsDcNameDelay"
0x180007915  call    NetpGetConfigDword
0x18000791a  mov     rcx, [rbp+var_18]
0x18000791e  mov     ebx, eax
0x180007920  call    NetpCloseConfigData
0x180007925  test    ebx, ebx
0x180007927  jnz     short loc_18000792E
0x180007929  mov     eax, [rbp+Data]
0x18000792c  jmp     short loc_180007933
0x18000792e  mov     eax, 0Fh
0x180007933  cmp     eax, 3Ch ; '<'
0x180007936  jbe     short loc_18000793F
0x180007938  mov     eax, 3Ch ; '<'
0x18000793d  jmp     short loc_180007949
0x18000793f  cmp     eax, 0Fh
0x180007942  jnb     short loc_180007949
0x180007944  mov     eax, 0Fh
0x180007949  add     rsp, 48h
0x18000794d  pop     rbx
0x18000794e  pop     rbp
0x18000794f  retn
```
