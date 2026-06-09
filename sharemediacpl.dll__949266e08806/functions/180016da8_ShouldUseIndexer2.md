# ShouldUseIndexer2

- ea: `0x180016da8`
- end: `0x180016e58`
- name: `ShouldUseIndexer2`
- size: `176`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180005e74`

## callees

- `0x180016da8`

## import_xrefs

- `KERNEL32!RegCloseKey` at `0x180016e36`
- `KERNEL32!RegCloseKey` at `0x180016e36`
- `KERNEL32!RegOpenKeyExW` at `0x180016de5`
- `KERNEL32!RegOpenKeyExW` at `0x180016de5`
- `KERNEL32!RegQueryValueExW` at `0x180016e28`
- `KERNEL32!RegQueryValueExW` at `0x180016e28`

## pseudocode

```c
bool ShouldUseIndexer2()
{
  HKEY v0; // rbx
  DWORD cbData; // [rsp+40h] [rbp+8h] BYREF
  DWORD Type; // [rsp+48h] [rbp+10h] BYREF
  HKEY hKey; // [rsp+50h] [rbp+18h] BYREF

  if ( *(_DWORD *)&Data == 2 )
  {
    hKey = 0;
    if ( RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"Software\\Microsoft\\MediaPlayer\\Preferences\\HME\\", 0, 0x20219u, &hKey) )
    {
      *(_DWORD *)&Data = 1;
    }
    else
    {
      v0 = hKey;
      Type = 0;
      cbData = 4;
      RegQueryValueExW(hKey, L"UseIndexer", 0, &Type, &Data, &cbData);
      if ( v0 )
        RegCloseKey(v0);
    }
  }
  return *(_DWORD *)&Data != 0;
}

```

## disassembly

```asm
0x180016da8  push    rbx
0x180016daa  sub     rsp, 30h
0x180016dae  cmp     cs:Data, 2
0x180016db5  jnz     loc_180016E48
0x180016dbb  lea     rax, [rsp+38h+hKey]
0x180016dc0  mov     [rsp+38h+hKey], 0
0x180016dc9  mov     r9d, 20219h; samDesired
0x180016dcf  mov     [rsp+38h+phkResult], rax; phkResult
0x180016dd4  xor     r8d, r8d; ulOptions
0x180016dd7  lea     rdx, SubKey; "Software\\Microsoft\\MediaPlayer\\Prefe"...
0x180016dde  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180016de5  call    cs:__imp_RegOpenKeyExW
0x180016deb  test    eax, eax
0x180016ded  jnz     short loc_180016E3E
0x180016def  mov     rbx, [rsp+38h+hKey]
0x180016df4  lea     r9, [rsp+38h+Type]; lpType
0x180016df9  mov     [rsp+38h+Type], eax
0x180016dfd  lea     rdx, ValueName; "UseIndexer"
0x180016e04  lea     rax, [rsp+38h+cbData]
0x180016e09  mov     [rsp+38h+cbData], 4
0x180016e11  mov     [rsp+38h+lpcbData], rax; lpcbData
0x180016e16  xor     r8d, r8d; lpReserved
0x180016e19  lea     rax, Data
0x180016e20  mov     rcx, rbx; hKey
0x180016e23  mov     [rsp+38h+phkResult], rax; lpData
0x180016e28  call    cs:__imp_RegQueryValueExW
0x180016e2e  test    rbx, rbx
0x180016e31  jz      short loc_180016E48
0x180016e33  mov     rcx, rbx; hKey
0x180016e36  call    cs:__imp_RegCloseKey
0x180016e3c  jmp     short loc_180016E48
0x180016e3e  mov     cs:Data, 1
0x180016e48  cmp     cs:Data, 0
0x180016e4f  setnz   al
0x180016e52  add     rsp, 30h
0x180016e56  pop     rbx
0x180016e57  retn
```
