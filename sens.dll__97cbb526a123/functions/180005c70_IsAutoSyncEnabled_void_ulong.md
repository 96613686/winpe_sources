# IsAutoSyncEnabled(void *,ulong)

- ea: `0x180005c70`
- end: `0x180005d15`
- name: `?IsAutoSyncEnabled@@YAHPEAXK@Z`
- size: `165`
- prototype: `_BOOL8 __fastcall(void *)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180004fac`

## callees

- `0x180005c70`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180005ceb`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180005ceb`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180005d05`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180005d05`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180005cb6`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180005cb6`

## pseudocode

```c
_BOOL8 __fastcall IsAutoSyncEnabled(void *a1)
{
  BOOL v1; // ebx
  int Data; // [rsp+50h] [rbp+20h] BYREF
  int v4; // [rsp+54h] [rbp+24h]
  DWORD cbData; // [rsp+58h] [rbp+28h] BYREF
  DWORD Type; // [rsp+60h] [rbp+30h] BYREF
  HKEY hKey; // [rsp+68h] [rbp+38h] BYREF

  v4 = HIDWORD(a1);
  v1 = 0;
  hKey = 0;
  Type = 0;
  Data = 0;
  cbData = 0;
  if ( !RegOpenKeyExW(
          HKEY_LOCAL_MACHINE,
          L"Software\\Microsoft\\Windows\\CurrentVersion\\Syncmgr\\AutoSync",
          0,
          1u,
          &hKey) )
  {
    cbData = 4;
    if ( !RegQueryValueExW(hKey, L"Flags", 0, &Type, (LPBYTE)&Data, &cbData) )
      v1 = (Data & 0xA) != 0;
  }
  if ( hKey )
    RegCloseKey(hKey);
  return v1;
}

```

## disassembly

```asm
0x180005c70  mov     [rsp-18h+cbData], edx
0x180005c74  mov     qword ptr [rsp-18h+Data], rcx
0x180005c79  push    rbp
0x180005c7a  push    rbx
0x180005c7b  push    rsi
0x180005c7c  mov     rbp, rsp
0x180005c7f  sub     rsp, 30h
0x180005c83  xor     ebx, ebx
0x180005c85  mov     [rbp+hKey], 0
0x180005c8d  lea     rax, [rbp+hKey]
0x180005c91  mov     [rbp+Type], ebx
0x180005c94  xor     r8d, r8d; ulOptions
0x180005c97  mov     [rbp+Data], ebx
0x180005c9a  lea     rdx, SubKey; "Software\\Microsoft\\Windows\\CurrentVe"...
0x180005ca1  mov     [rbp+cbData], ebx
0x180005ca4  lea     esi, [rbx+1]
0x180005ca7  mov     [rsp+30h+phkResult], rax; phkResult
0x180005cac  mov     r9d, esi; samDesired
0x180005caf  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180005cb6  call    cs:__imp_RegOpenKeyExW
0x180005cbc  test    eax, eax
0x180005cbe  jnz     short loc_180005CFC
0x180005cc0  mov     rcx, [rbp+hKey]; hKey
0x180005cc4  lea     rax, [rbp+cbData]
0x180005cc8  mov     [rsp+30h+lpcbData], rax; lpcbData
0x180005ccd  lea     r9, [rbp+Type]; lpType
0x180005cd1  lea     rax, [rbp+Data]
0x180005cd5  mov     [rbp+cbData], 4
0x180005cdc  xor     r8d, r8d; lpReserved
0x180005cdf  mov     [rsp+30h+phkResult], rax; lpData
0x180005ce4  lea     rdx, ValueName; "Flags"
0x180005ceb  call    cs:__imp_RegQueryValueExW
0x180005cf1  test    eax, eax
0x180005cf3  jnz     short loc_180005CFC
0x180005cf5  test    byte ptr [rbp+Data], 0Ah
0x180005cf9  cmovnz  ebx, esi
0x180005cfc  mov     rcx, [rbp+hKey]; hKey
0x180005d00  test    rcx, rcx
0x180005d03  jz      short loc_180005D0B
0x180005d05  call    cs:__imp_RegCloseKey
0x180005d0b  mov     eax, ebx
0x180005d0d  add     rsp, 30h
0x180005d11  pop     rsi
0x180005d12  pop     rbx
0x180005d13  pop     rbp
0x180005d14  retn
```
