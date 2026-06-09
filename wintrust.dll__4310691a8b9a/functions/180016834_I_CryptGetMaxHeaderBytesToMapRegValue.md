# I_CryptGetMaxHeaderBytesToMapRegValue

- ea: `0x180016834`
- end: `0x1800168c1`
- name: `I_CryptGetMaxHeaderBytesToMapRegValue`
- size: `141`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180016640`

## callees

- `0x180016834`
- `0x180047ed8`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001687b`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001687b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800168b9`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800168b9`

## string_xrefs

- `0x180016868`: `Software\Microsoft\Cryptography\Wintrust\Config`

## pseudocode

```c
__int64 I_CryptGetMaxHeaderBytesToMapRegValue()
{
  unsigned int v0; // ebx
  unsigned int v2; // [rsp+40h] [rbp+8h] BYREF
  HKEY hKey; // [rsp+48h] [rbp+10h] BYREF

  v0 = dword_180069F44;
  if ( !dword_180069F44 )
  {
    hKey = 0;
    v0 = 10485760;
    if ( !RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"Software\\Microsoft\\Cryptography\\Wintrust\\Config", 0, 0x20019u, &hKey) )
    {
      v2 = 0;
      ReadDWORDValueFromRegistry(hKey, L"MaxHeaderBytesToMap", &v2);
      if ( v2 )
        v0 = v2;
      RegCloseKey(hKey);
    }
    dword_180069F44 = v0;
  }
  return v0;
}

```

## disassembly

```asm
0x180016834  push    rbx
0x180016836  sub     rsp, 30h
0x18001683a  mov     ebx, cs:dword_180069F44
0x180016840  test    ebx, ebx
0x180016842  jz      short loc_18001684C
0x180016844  mov     eax, ebx
0x180016846  add     rsp, 30h
0x18001684a  pop     rbx
0x18001684b  retn
0x18001684c  lea     rax, [rsp+38h+hKey]
0x180016851  mov     [rsp+38h+hKey], 0
0x18001685a  mov     r9d, 20019h; samDesired
0x180016860  mov     [rsp+38h+phkResult], rax; phkResult
0x180016865  xor     r8d, r8d; ulOptions
0x180016868  lea     rdx, aSoftwareMicros_11; "Software\\Microsoft\\Cryptography\\Wint"...
0x18001686f  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180016876  mov     ebx, 0A00000h
0x18001687b  call    cs:__imp_RegOpenKeyExW
0x180016881  test    eax, eax
0x180016883  jz      short loc_18001688D
0x180016885  mov     cs:dword_180069F44, ebx
0x18001688b  jmp     short loc_180016844
0x18001688d  mov     rcx, [rsp+38h+hKey]
0x180016892  lea     r8, [rsp+38h+arg_0]
0x180016897  lea     rdx, aMaxheaderbytes; "MaxHeaderBytesToMap"
0x18001689e  mov     [rsp+38h+arg_0], 0
0x1800168a6  call    _ReadDWORDValueFromRegistry
0x1800168ab  mov     ecx, [rsp+38h+arg_0]
0x1800168af  test    ecx, ecx
0x1800168b1  cmovnz  ebx, ecx
0x1800168b4  mov     rcx, [rsp+38h+hKey]; hKey
0x1800168b9  call    cs:__imp_RegCloseKey
0x1800168bf  jmp     short loc_180016885
```
