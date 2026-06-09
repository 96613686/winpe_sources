# WDSCheckCommonDebugging(ushort const *)

- ea: `0x1800070d0`
- end: `0x18000715b`
- name: `?WDSCheckCommonDebugging@@YAXPEBG@Z`
- size: `139`
- prototype: `void __fastcall(LPCWSTR lpSubKey)`
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callees

- `0x1800070d0`
- `0x18000e400`

## import_xrefs

- `ADVAPI32!RegCloseKey` at `0x180007149`
- `ADVAPI32!RegCloseKey` at `0x180007149`
- `ADVAPI32!RegOpenKeyExW` at `0x1800070fc`
- `ADVAPI32!RegOpenKeyExW` at `0x1800070fc`

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
    dword_180049BAC = 1;
  }
  if ( hKey )
    RegCloseKey(hKey);
}

```

## disassembly

```asm
0x1800070d0  sub     rsp, 38h
0x1800070d4  and     [rsp+38h+hKey], 0
0x1800070da  lea     rax, [rsp+38h+hKey]
0x1800070df  and     [rsp+38h+arg_8], 0
0x1800070e4  mov     rdx, rcx; lpSubKey
0x1800070e7  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800070ee  mov     [rsp+38h+phkResult], rax; phkResult
0x1800070f3  mov     r9d, 20119h; samDesired
0x1800070f9  xor     r8d, r8d; ulOptions
0x1800070fc  call    cs:__imp_RegOpenKeyExW
0x180007103  nop     dword ptr [rax+rax+00h]
0x180007108  test    eax, eax
0x18000710a  jnz     short loc_18000713F
0x18000710c  lea     r8d, [rax+4]; unsigned int
0x180007110  lea     r9, [rsp+38h+arg_8]; void *
0x180007115  mov     dword ptr [rsp+38h+phkResult], r8d; unsigned int
0x18000711a  lea     rdx, aEnablewdsdebug; "EnableWdsDebug"
0x180007121  lea     rcx, [rsp+38h+hKey]; this
0x180007126  call    ?GetValue@CRegKey@@QEAAKPEBGKPEAXK@Z; CRegKey::GetValue(ushort const *,ulong,void *,ulong)
0x18000712b  test    eax, eax
0x18000712d  jnz     short loc_18000713F
0x18000712f  cmp     [rsp+38h+arg_8], eax
0x180007133  jbe     short loc_18000713F
0x180007135  mov     cs:dword_180049BAC, 1
0x18000713f  mov     rcx, [rsp+38h+hKey]; hKey
0x180007144  test    rcx, rcx
0x180007147  jz      short loc_180007155
0x180007149  call    cs:__imp_RegCloseKey
0x180007150  nop     dword ptr [rax+rax+00h]
0x180007155  add     rsp, 38h
0x180007159  retn
```
