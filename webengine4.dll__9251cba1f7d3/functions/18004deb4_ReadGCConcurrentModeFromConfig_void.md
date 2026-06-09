# ReadGCConcurrentModeFromConfig(void)

- ea: `0x18004deb4`
- end: `0x18004df3d`
- name: `?ReadGCConcurrentModeFromConfig@@YAHXZ`
- size: `137`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18004df40`

## callees

- `0x18004deb4`

## import_xrefs

- `ADVAPI32!RegCloseKey` at `0x18004df28`
- `ADVAPI32!RegCloseKey` at `0x18004df28`
- `ADVAPI32!RegOpenKeyExW` at `0x18004dedb`
- `ADVAPI32!RegOpenKeyExW` at `0x18004dedb`
- `ADVAPI32!RegQueryValueExW` at `0x18004df1d`
- `ADVAPI32!RegQueryValueExW` at `0x18004df1d`

## string_xrefs

- `0x18004defa`: `ReadGCConcurrentModeFromConfig`

## pseudocode

```c
__int64 ReadGCConcurrentModeFromConfig(void)
{
  unsigned int v0; // ebx
  int Data; // [rsp+40h] [rbp+8h] BYREF
  DWORD cbData; // [rsp+48h] [rbp+10h] BYREF
  HKEY hKey; // [rsp+50h] [rbp+18h] BYREF

  v0 = 0;
  if ( RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"Software\\Microsoft\\ASP.NET\\4.0.30319.0", 0, 0x20019u, &hKey) )
    return 0;
  Data = 0;
  cbData = 4;
  RegQueryValueExW(hKey, L"ReadGCConcurrentModeFromConfig", 0, 0, (LPBYTE)&Data, &cbData);
  RegCloseKey(hKey);
  LOBYTE(v0) = Data != 0;
  return v0;
}

```

## disassembly

```asm
0x18004deb4  push    rbx
0x18004deb6  sub     rsp, 30h
0x18004deba  lea     rax, [rsp+38h+hKey]
0x18004debf  mov     r9d, 20019h; samDesired
0x18004dec5  xor     r8d, r8d; ulOptions
0x18004dec8  mov     [rsp+38h+phkResult], rax; phkResult
0x18004decd  lea     rdx, aSoftwareMicros_4; "Software\\Microsoft\\ASP.NET\\4.0.30319"...
0x18004ded4  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18004dedb  call    cs:__imp_RegOpenKeyExW
0x18004dee1  xor     ebx, ebx
0x18004dee3  test    eax, eax
0x18004dee5  jz      short loc_18004DEEB
0x18004dee7  xor     eax, eax
0x18004dee9  jmp     short loc_18004DF37
0x18004deeb  mov     rcx, [rsp+38h+hKey]; hKey
0x18004def0  lea     rax, [rsp+38h+cbData]
0x18004def5  mov     [rsp+38h+lpcbData], rax; lpcbData
0x18004defa  lea     rdx, aReadgcconcurre; "ReadGCConcurrentModeFromConfig"
0x18004df01  lea     rax, [rsp+38h+Data]
0x18004df06  mov     [rsp+38h+Data], ebx
0x18004df0a  xor     r9d, r9d; lpType
0x18004df0d  mov     [rsp+38h+phkResult], rax; lpData
0x18004df12  xor     r8d, r8d; lpReserved
0x18004df15  mov     [rsp+38h+cbData], 4
0x18004df1d  call    cs:__imp_RegQueryValueExW
0x18004df23  mov     rcx, [rsp+38h+hKey]; hKey
0x18004df28  call    cs:__imp_RegCloseKey
0x18004df2e  cmp     [rsp+38h+Data], ebx
0x18004df32  setnz   bl
0x18004df35  mov     eax, ebx
0x18004df37  add     rsp, 30h
0x18004df3b  pop     rbx
0x18004df3c  retn
```
