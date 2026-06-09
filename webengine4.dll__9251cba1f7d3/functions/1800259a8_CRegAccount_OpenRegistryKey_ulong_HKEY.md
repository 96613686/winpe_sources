# CRegAccount::OpenRegistryKey(ulong,HKEY__ * *)

- ea: `0x1800259a8`
- end: `0x180025a89`
- name: `?OpenRegistryKey@CRegAccount@@CAJKPEAPEAUHKEY__@@@Z`
- size: `225`
- prototype: `__int64 __fastcall(REGSAM samDesired, DWORD dwOptions)`
- caller_count: `2`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180025ff4`
- `0x1800269c8`

## callees

- `0x1800259a8`

## import_xrefs

- `ADVAPI32!RegCloseKey` at `0x180025a56`
- `ADVAPI32!RegCloseKey` at `0x180025a6d`
- `ADVAPI32!RegCloseKey` at `0x180025a56`
- `ADVAPI32!RegCloseKey` at `0x180025a6d`
- `ADVAPI32!RegCreateKeyExW` at `0x180025a34`
- `ADVAPI32!RegCreateKeyExW` at `0x180025a34`
- `ADVAPI32!RegOpenKeyExW` at `0x1800259e0`
- `ADVAPI32!RegOpenKeyExW` at `0x180025a01`
- `ADVAPI32!RegOpenKeyExW` at `0x1800259e0`
- `ADVAPI32!RegOpenKeyExW` at `0x180025a01`

## pseudocode

```c
__int64 __fastcall CRegAccount::OpenRegistryKey(REGSAM samDesired, HKEY *dwOptions)
{
  unsigned int v4; // ebx
  LSTATUS Key; // eax
  HKEY hKey; // [rsp+70h] [rbp+18h] BYREF

  hKey = 0;
  v4 = 0;
  Key = RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"Software\\Microsoft\\ASP.NET", 0, samDesired, &hKey);
  if ( Key
    || RegOpenKeyExW(hKey, L"MachineAccounts", 0, samDesired, dwOptions)
    && (Key = RegCreateKeyExW(hKey, L"MachineAccounts", 0, 0, 0, samDesired, 0, dwOptions, 0)) != 0 )
  {
    v4 = (unsigned __int16)Key | 0x80070000;
    if ( Key <= 0 )
      v4 = Key;
  }
  if ( hKey )
    RegCloseKey(hKey);
  if ( v4 && dwOptions && *dwOptions )
  {
    RegCloseKey(*dwOptions);
    *dwOptions = 0;
  }
  return v4;
}

```

## disassembly

```asm
0x1800259a8  mov     r11, rsp
0x1800259ab  mov     [r11+8], rbx
0x1800259af  mov     [r11+10h], rsi
0x1800259b3  push    rdi
0x1800259b4  sub     rsp, 50h
0x1800259b8  and     qword ptr [r11+18h], 0
0x1800259bd  lea     rax, [r11+18h]
0x1800259c1  mov     rdi, rdx
0x1800259c4  mov     [r11-38h], rax
0x1800259c8  mov     esi, ecx
0x1800259ca  lea     rdx, aSoftwareMicros_9; "Software\\Microsoft\\ASP.NET"
0x1800259d1  mov     r9d, ecx; samDesired
0x1800259d4  xor     r8d, r8d; ulOptions
0x1800259d7  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800259de  xor     ebx, ebx
0x1800259e0  call    cs:__imp_RegOpenKeyExW
0x1800259e6  test    eax, eax
0x1800259e8  jnz     short loc_180025A3E
0x1800259ea  mov     rcx, [rsp+58h+hKey]; hKey
0x1800259ef  lea     rdx, aMachineaccount; "MachineAccounts"
0x1800259f6  mov     r9d, esi; samDesired
0x1800259f9  mov     [rsp+58h+phkResult], rdi; dwOptions
0x1800259fe  xor     r8d, r8d; ulOptions
0x180025a01  call    cs:__imp_RegOpenKeyExW
0x180025a07  test    eax, eax
0x180025a09  jz      short loc_180025A4C
0x180025a0b  and     [rsp+58h+var_18], rbx
0x180025a10  lea     rdx, aMachineaccount; "MachineAccounts"
0x180025a17  mov     rcx, [rsp+58h+hKey]; hKey
0x180025a1c  xor     r9d, r9d; lpClass
0x180025a1f  mov     [rsp+58h+var_20], rdi; phkResult
0x180025a24  xor     r8d, r8d; Reserved
0x180025a27  and     [rsp+58h+var_28], rbx
0x180025a2c  mov     [rsp+58h+samDesired], esi; samDesired
0x180025a30  and     dword ptr [rsp+58h+phkResult], ebx
0x180025a34  call    cs:__imp_RegCreateKeyExW
0x180025a3a  test    eax, eax
0x180025a3c  jz      short loc_180025A4C
0x180025a3e  movzx   ebx, ax
0x180025a41  or      ebx, 80070000h
0x180025a47  test    eax, eax
0x180025a49  cmovle  ebx, eax
0x180025a4c  mov     rcx, [rsp+58h+hKey]; hKey
0x180025a51  test    rcx, rcx
0x180025a54  jz      short loc_180025A5C
0x180025a56  call    cs:__imp_RegCloseKey
0x180025a5c  test    ebx, ebx
0x180025a5e  jz      short loc_180025A77
0x180025a60  test    rdi, rdi
0x180025a63  jz      short loc_180025A77
0x180025a65  mov     rcx, [rdi]; hKey
0x180025a68  test    rcx, rcx
0x180025a6b  jz      short loc_180025A77
0x180025a6d  call    cs:__imp_RegCloseKey
0x180025a73  and     qword ptr [rdi], 0
0x180025a77  mov     rsi, [rsp+58h+arg_8]
0x180025a7c  mov     eax, ebx
0x180025a7e  mov     rbx, [rsp+58h+arg_0]
0x180025a83  add     rsp, 50h
0x180025a87  pop     rdi
0x180025a88  retn
```
