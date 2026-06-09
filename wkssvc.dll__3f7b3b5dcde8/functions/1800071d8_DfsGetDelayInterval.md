# DfsGetDelayInterval

- ea: `0x1800071d8`
- end: `0x1800072d2`
- name: `DfsGetDelayInterval`
- size: `250`
- prototype: `__int64()`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18002d080`

## callees

- `0x1800071d8`
- `0x1800072d8`
- `0x180007400`
- `0x180007434`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180007227`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180007227`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180007261`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180007261`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180007255`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180007255`

## pseudocode

```c
__int64 DfsGetDelayInterval()
{
  __int64 v0; // rdx
  __int64 v1; // r8
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
0x1800071d8  push    rbp
0x1800071da  push    rbx
0x1800071db  mov     rbp, rsp
0x1800071de  sub     rsp, 48h
0x1800071e2  lea     rax, [rbp+hKey]
0x1800071e6  mov     [rbp+var_18], 0
0x1800071ee  mov     r9d, 20019h; samDesired
0x1800071f4  mov     [rsp+48h+phkResult], rax; phkResult
0x1800071f9  xor     r8d, r8d; ulOptions
0x1800071fc  mov     [rbp+hKey], 0
0x180007204  lea     rdx, aSoftwarePolici; "Software\\Policies\\Microsoft\\System\\"...
0x18000720b  mov     [rbp+Data], 0
0x180007212  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180007219  mov     [rbp+cbData], 4
0x180007220  mov     [rbp+Type], 0
0x180007227  call    cs:__imp_RegOpenKeyExW
0x18000722d  test    eax, eax
0x18000722f  jnz     short loc_180007271
0x180007231  mov     rcx, [rbp+hKey]; hKey
0x180007235  lea     rax, [rbp+cbData]
0x180007239  mov     [rsp+48h+lpcbData], rax; lpcbData
0x18000723e  lea     r9, [rbp+Type]; lpType
0x180007242  lea     rax, [rbp+Data]
0x180007246  xor     r8d, r8d; lpReserved
0x180007249  lea     rdx, aDfsdcnamedelay; "DfsDcNameDelay"
0x180007250  mov     [rsp+48h+phkResult], rax; lpData
0x180007255  call    cs:__imp_RegQueryValueExW
0x18000725b  mov     rcx, [rbp+hKey]; hKey
0x18000725f  mov     ebx, eax
0x180007261  call    cs:__imp_RegCloseKey
0x180007267  test    ebx, ebx
0x180007269  jnz     short loc_180007271
0x18000726b  cmp     [rbp+Type], 4
0x18000726f  jz      short loc_1800072AB
0x180007271  mov     r9d, 1
0x180007277  lea     rcx, [rbp+var_18]
0x18000727b  call    NetpOpenConfigDataEx
0x180007280  test    eax, eax
0x180007282  jnz     short loc_1800072B0
0x180007284  mov     rcx, [rbp+var_18]
0x180007288  lea     r9, [rbp+Data]
0x18000728c  lea     r8d, [rax+0Fh]
0x180007290  lea     rdx, aDfsdcnamedelay; "DfsDcNameDelay"
0x180007297  call    NetpGetConfigDword
0x18000729c  mov     rcx, [rbp+var_18]
0x1800072a0  mov     ebx, eax
0x1800072a2  call    NetpCloseConfigData
0x1800072a7  test    ebx, ebx
0x1800072a9  jnz     short loc_1800072B0
0x1800072ab  mov     eax, [rbp+Data]
0x1800072ae  jmp     short loc_1800072B5
0x1800072b0  mov     eax, 0Fh
0x1800072b5  cmp     eax, 3Ch ; '<'
0x1800072b8  jbe     short loc_1800072C1
0x1800072ba  mov     eax, 3Ch ; '<'
0x1800072bf  jmp     short loc_1800072CB
0x1800072c1  cmp     eax, 0Fh
0x1800072c4  jnb     short loc_1800072CB
0x1800072c6  mov     eax, 0Fh
0x1800072cb  add     rsp, 48h
0x1800072cf  pop     rbx
0x1800072d0  pop     rbp
0x1800072d1  retn
```
