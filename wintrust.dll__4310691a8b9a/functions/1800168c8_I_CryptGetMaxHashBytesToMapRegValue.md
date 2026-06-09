# I_CryptGetMaxHashBytesToMapRegValue

- ea: `0x1800168c8`
- end: `0x180016955`
- name: `I_CryptGetMaxHashBytesToMapRegValue`
- size: `141`
- prototype: `__int64(void)`
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18001647c`
- `0x180016640`

## callees

- `0x1800168c8`
- `0x180047ed8`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001690f`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001690f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001694d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001694d`

## string_xrefs

- `0x1800168fc`: `Software\Microsoft\Cryptography\Wintrust\Config`

## pseudocode

```c
__int64 I_CryptGetMaxHashBytesToMapRegValue()
{
  unsigned int v0; // ebx
  unsigned int v2; // [rsp+40h] [rbp+8h] BYREF
  HKEY hKey; // [rsp+48h] [rbp+10h] BYREF

  v0 = dword_180069F40;
  if ( !dword_180069F40 )
  {
    hKey = 0;
    v0 = 0x100000;
    if ( !RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"Software\\Microsoft\\Cryptography\\Wintrust\\Config", 0, 0x20019u, &hKey) )
    {
      v2 = 0;
      ReadDWORDValueFromRegistry(hKey, L"MaxHashBytesToMap", &v2);
      if ( v2 )
        v0 = v2;
      RegCloseKey(hKey);
    }
    dword_180069F40 = v0;
  }
  return v0;
}

```

## disassembly

```asm
0x1800168c8  push    rbx
0x1800168ca  sub     rsp, 30h
0x1800168ce  mov     ebx, cs:dword_180069F40
0x1800168d4  test    ebx, ebx
0x1800168d6  jz      short loc_1800168E0
0x1800168d8  mov     eax, ebx
0x1800168da  add     rsp, 30h
0x1800168de  pop     rbx
0x1800168df  retn
0x1800168e0  lea     rax, [rsp+38h+hKey]
0x1800168e5  mov     [rsp+38h+hKey], 0
0x1800168ee  mov     r9d, 20019h; samDesired
0x1800168f4  mov     [rsp+38h+phkResult], rax; phkResult
0x1800168f9  xor     r8d, r8d; ulOptions
0x1800168fc  lea     rdx, aSoftwareMicros_11; "Software\\Microsoft\\Cryptography\\Wint"...
0x180016903  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18001690a  mov     ebx, 100000h
0x18001690f  call    cs:__imp_RegOpenKeyExW
0x180016915  test    eax, eax
0x180016917  jz      short loc_180016921
0x180016919  mov     cs:dword_180069F40, ebx
0x18001691f  jmp     short loc_1800168D8
0x180016921  mov     rcx, [rsp+38h+hKey]
0x180016926  lea     r8, [rsp+38h+arg_0]
0x18001692b  lea     rdx, aMaxhashbytesto; "MaxHashBytesToMap"
0x180016932  mov     [rsp+38h+arg_0], 0
0x18001693a  call    _ReadDWORDValueFromRegistry
0x18001693f  mov     ecx, [rsp+38h+arg_0]
0x180016943  test    ecx, ecx
0x180016945  cmovnz  ebx, ecx
0x180016948  mov     rcx, [rsp+38h+hKey]; hKey
0x18001694d  call    cs:__imp_RegCloseKey
0x180016953  jmp     short loc_180016919
```
