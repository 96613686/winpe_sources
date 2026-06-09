# InitRegInfo_Sqloledb(void)

- ea: `0x383895c20`
- end: `0x383895c71`
- name: `?InitRegInfo_Sqloledb@@YAXXZ`
- size: `81`
- prototype: `void(void)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0x38389a0c0`

## callees

- `0x383895c20`

## import_xrefs

- `ADVAPI32!RegOpenKeyExW` at `0x383895c5e`
- `ADVAPI32!RegOpenKeyExW` at `0x383895c5e`
- `ADVAPI32!RegQueryValueExW` at `0x3838d4fa0`
- `ADVAPI32!RegQueryValueExW` at `0x3838d4fa0`
- `ADVAPI32!RegCloseKey` at `0x3838d4fba`
- `ADVAPI32!RegCloseKey` at `0x3838d4fba`

## string_xrefs

- `0x383895c29`: `SOFTWARE\Microsoft\MSSQLServer\Client\SQLXMLX`
- `0x3838d4f7c`: `FORXML_GenerateGUIDBraces`

## pseudocode

```c
void InitRegInfo_Sqloledb(void)
{
  DWORD cbData; // [rsp+40h] [rbp+8h] BYREF
  int Data; // [rsp+48h] [rbp+10h] BYREF
  HKEY hKey; // [rsp+50h] [rbp+18h] BYREF

  hKey = HKEY_CURRENT_USER_LOCAL_SETTINGS|0x7FFFFFF8LL;
  Data = 0;
  cbData = 4;
  if ( !RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"SOFTWARE\\Microsoft\\MSSQLServer\\Client\\SQLXMLX", 0, 9u, &hKey)
    && hKey != HKEY_CURRENT_USER_LOCAL_SETTINGS|0x7FFFFFF8LL )
  {
    cbData = 4;
    if ( !RegQueryValueExW(hKey, L"FORXML_GenerateGUIDBraces", 0, 0, (LPBYTE)&Data, &cbData) )
      g_fGenerateGUIDSWithBraces = Data != 0;
    RegCloseKey(hKey);
  }
}

```

## disassembly

```asm
0x383895c20  sub     rsp, 38h
0x383895c24  lea     rax, [rsp+38h+hKey]
0x383895c29  lea     rdx, aSoftwareMicros_10; "SOFTWARE\\Microsoft\\MSSQLServer\\Clien"...
0x383895c30  mov     r9d, 9; samDesired
0x383895c36  xor     r8d, r8d; ulOptions
0x383895c39  mov     rcx, 0FFFFFFFF80000002h; hKey
0x383895c40  mov     [rsp+38h+hKey], 0FFFFFFFFFFFFFFFFh
0x383895c49  mov     [rsp+38h+phkResult], rax; phkResult
0x383895c4e  mov     [rsp+38h+Data], 0
0x383895c56  mov     [rsp+38h+cbData], 4
0x383895c5e  call    cs:__imp_RegOpenKeyExW
0x383895c64  test    eax, eax
0x383895c66  jz      loc_3838D4F68
0x383895c6c  add     rsp, 38h
0x383895c70  retn
0x3838d4f68  mov     rcx, [rsp+38h+hKey]; hKey
0x3838d4f6d  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x3838d4f71  jz      loc_383895C6C
0x3838d4f77  lea     rax, [rsp+38h+cbData]
0x3838d4f7c  lea     rdx, aForxmlGenerate; "FORXML_GenerateGUIDBraces"
0x3838d4f83  xor     r9d, r9d; lpType
0x3838d4f86  mov     [rsp+38h+lpcbData], rax; lpcbData
0x3838d4f8b  lea     rax, [rsp+38h+Data]
0x3838d4f90  xor     r8d, r8d; lpReserved
0x3838d4f93  mov     [rsp+38h+phkResult], rax; lpData
0x3838d4f98  mov     [rsp+38h+cbData], 4
0x3838d4fa0  call    cs:__imp_RegQueryValueExW
0x3838d4fa6  test    eax, eax
0x3838d4fa8  jnz     short loc_3838D4FB5
0x3838d4faa  cmp     [rsp+38h+Data], eax
0x3838d4fae  setnz   cs:?g_fGenerateGUIDSWithBraces@@3_NA; bool g_fGenerateGUIDSWithBraces
0x3838d4fb5  mov     rcx, [rsp+38h+hKey]; hKey
0x3838d4fba  call    cs:__imp_RegCloseKey
0x3838d4fc0  nop
0x3838d4fc1  jmp     loc_383895C6C
```
