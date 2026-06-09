# GetConfigInfo

- ea: `0x383894370`
- end: `0x3838943d3`
- name: `GetConfigInfo`
- size: `99`
- prototype: `__int64 __fastcall(LPBYTE lpData, LPBYTE)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0x3838924f8`

## callees

- `0x383894370`

## import_xrefs

- `ADVAPI32!RegOpenKeyExW` at `0x3838943ba`
- `ADVAPI32!RegOpenKeyExW` at `0x3838943ba`
- `ADVAPI32!RegQueryValueExW` at `0x3838f2c96`
- `ADVAPI32!RegQueryValueExW` at `0x3838f2cc5`
- `ADVAPI32!RegQueryValueExW` at `0x3838f2c96`
- `ADVAPI32!RegQueryValueExW` at `0x3838f2cc5`
- `ADVAPI32!RegCloseKey` at `0x3838f2cd0`
- `ADVAPI32!RegCloseKey` at `0x3838f2cd0`

## string_xrefs

- `0x38389439e`: `SOFTWARE\Microsoft\DataAccess\SQLNCLI11`

## pseudocode

```c
DWORD __fastcall GetConfigInfo(LPBYTE lpData, LPBYTE a2)
{
  DWORD result; // eax
  bool v4; // zf
  DWORD cbData; // [rsp+40h] [rbp+8h] BYREF
  HKEY hKey; // [rsp+48h] [rbp+10h] BYREF

  *(_DWORD *)lpData = 1;
  result = g_SystemInfo.dwNumberOfProcessors + 1;
  v4 = !g_fIsEmbeddedSNAC;
  *(_DWORD *)a2 = g_SystemInfo.dwNumberOfProcessors + 1;
  if ( v4 )
  {
    result = RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"SOFTWARE\\Microsoft\\DataAccess\\SQLNCLI11", 0, 0x20019u, &hKey);
    if ( !result )
    {
      cbData = 4;
      RegQueryValueExW(hKey, L"UseMPHeap", 0, 0, lpData, &cbData);
      cbData = 4;
      RegQueryValueExW(hKey, L"NumberOfCsPools", 0, 0, a2, &cbData);
      return RegCloseKey(hKey);
    }
  }
  return result;
}

```

## disassembly

```asm
0x383894370  mov     [rsp+arg_10], rbx
0x383894375  push    rdi
0x383894376  sub     rsp, 30h
0x38389437a  mov     dword ptr [rcx], 1
0x383894380  mov     eax, cs:?g_SystemInfo@@3U_SYSTEM_INFO@@A.dwNumberOfProcessors; _SYSTEM_INFO g_SystemInfo ...
0x383894386  mov     rbx, rdx
0x383894389  inc     eax
0x38389438b  cmp     cs:?g_fIsEmbeddedSNAC@@3_NA, 0; bool g_fIsEmbeddedSNAC
0x383894392  mov     rdi, rcx
0x383894395  mov     [rdx], eax
0x383894397  jnz     short loc_3838943C8
0x383894399  lea     rax, [rsp+38h+hKey]
0x38389439e  lea     rdx, aSoftwareMicros_9; "SOFTWARE\\Microsoft\\DataAccess\\SQLNCL"...
0x3838943a5  mov     r9d, 20019h; samDesired
0x3838943ab  xor     r8d, r8d; ulOptions
0x3838943ae  mov     rcx, 0FFFFFFFF80000002h; hKey
0x3838943b5  mov     [rsp+38h+phkResult], rax; phkResult
0x3838943ba  call    cs:__imp_RegOpenKeyExW
0x3838943c0  test    eax, eax
0x3838943c2  jz      loc_3838F2C6D
0x3838943c8  mov     rbx, [rsp+38h+arg_10]
0x3838943cd  add     rsp, 30h
0x3838943d1  pop     rdi
0x3838943d2  retn
0x3838f2c6d  mov     rcx, [rsp+38h+hKey]; hKey
0x3838f2c72  lea     rax, [rsp+38h+cbData]
0x3838f2c77  lea     rdx, aUsempheap; "UseMPHeap"
0x3838f2c7e  mov     [rsp+38h+lpcbData], rax; lpcbData
0x3838f2c83  xor     r9d, r9d; lpType
0x3838f2c86  xor     r8d, r8d; lpReserved
0x3838f2c89  mov     [rsp+38h+phkResult], rdi; lpData
0x3838f2c8e  mov     [rsp+38h+cbData], 4
0x3838f2c96  call    cs:__imp_RegQueryValueExW
0x3838f2c9c  mov     rcx, [rsp+38h+hKey]; hKey
0x3838f2ca1  lea     rax, [rsp+38h+cbData]
0x3838f2ca6  lea     rdx, aNumberofcspool; "NumberOfCsPools"
0x3838f2cad  mov     [rsp+38h+lpcbData], rax; lpcbData
0x3838f2cb2  xor     r9d, r9d; lpType
0x3838f2cb5  xor     r8d, r8d; lpReserved
0x3838f2cb8  mov     [rsp+38h+phkResult], rbx; lpData
0x3838f2cbd  mov     [rsp+38h+cbData], 4
0x3838f2cc5  call    cs:__imp_RegQueryValueExW
0x3838f2ccb  mov     rcx, [rsp+38h+hKey]; hKey
0x3838f2cd0  call    cs:__imp_RegCloseKey
0x3838f2cd6  nop
0x3838f2cd7  jmp     loc_3838943C8
```
