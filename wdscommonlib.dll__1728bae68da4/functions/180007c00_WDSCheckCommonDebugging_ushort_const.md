# WDSCheckCommonDebugging(ushort const *)

- ea: `0x180007c00`
- end: `0x180007c8b`
- name: `?WDSCheckCommonDebugging@@YAXPEBG@Z`
- size: `139`
- prototype: `void __fastcall(LPCWSTR lpSubKey)`
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callees

- `0x180007c00`
- `0x18000ef70`

## import_xrefs

- `ADVAPI32!RegCloseKey` at `0x180007c79`
- `ADVAPI32!RegCloseKey` at `0x180007c79`
- `ADVAPI32!RegOpenKeyExW` at `0x180007c2c`
- `ADVAPI32!RegOpenKeyExW` at `0x180007c2c`

## pseudocode

```c
void __fastcall WDSCheckCommonDebugging(LPCWSTR lpSubKey)
{
  int v1; // [rsp+48h] [rbp+10h] BYREF
  HKEY hKey; // [rsp+50h] [rbp+18h] BYREF

  hKey = 0;
  v1 = 0;
  if ( !RegOpenKeyExW(HKEY_LOCAL_MACHINE, lpSubKey, 0, 0x20119u, &hKey)
    && !CRegKey::GetValue((CRegKey *)&hKey, L"EnableWdsDebug", 4u, &v1, 4u)
    && v1 )
  {
    dword_18004BC9C = 1;
  }
  if ( hKey )
    RegCloseKey(hKey);
}

```

## disassembly

```asm
0x180007c00  sub     rsp, 38h
0x180007c04  and     [rsp+38h+hKey], 0
0x180007c0a  lea     rax, [rsp+38h+hKey]
0x180007c0f  and     [rsp+38h+arg_8], 0
0x180007c14  mov     rdx, rcx; lpSubKey
0x180007c17  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180007c1e  mov     [rsp+38h+phkResult], rax; phkResult
0x180007c23  mov     r9d, 20119h; samDesired
0x180007c29  xor     r8d, r8d; ulOptions
0x180007c2c  call    cs:__imp_RegOpenKeyExW
0x180007c33  nop     dword ptr [rax+rax+00h]
0x180007c38  test    eax, eax
0x180007c3a  jnz     short loc_180007C6F
0x180007c3c  lea     r8d, [rax+4]; unsigned int
0x180007c40  lea     r9, [rsp+38h+arg_8]; void *
0x180007c45  mov     dword ptr [rsp+38h+phkResult], r8d; unsigned int
0x180007c4a  lea     rdx, aEnablewdsdebug; "EnableWdsDebug"
0x180007c51  lea     rcx, [rsp+38h+hKey]; this
0x180007c56  call    ?GetValue@CRegKey@@QEAAKPEBGKPEAXK@Z; CRegKey::GetValue(ushort const *,ulong,void *,ulong)
0x180007c5b  test    eax, eax
0x180007c5d  jnz     short loc_180007C6F
0x180007c5f  cmp     [rsp+38h+arg_8], eax
0x180007c63  jbe     short loc_180007C6F
0x180007c65  mov     cs:dword_18004BC9C, 1
0x180007c6f  mov     rcx, [rsp+38h+hKey]; hKey
0x180007c74  test    rcx, rcx
0x180007c77  jz      short loc_180007C85
0x180007c79  call    cs:__imp_RegCloseKey
0x180007c80  nop     dword ptr [rax+rax+00h]
0x180007c85  add     rsp, 38h
0x180007c89  retn
```
