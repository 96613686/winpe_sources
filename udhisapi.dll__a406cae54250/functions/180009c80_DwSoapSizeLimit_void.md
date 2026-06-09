# DwSoapSizeLimit(void)

- ea: `0x180009c80`
- end: `0x180009d25`
- name: `?DwSoapSizeLimit@@YAKXZ`
- size: `165`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180005e60`

## callees

- `0x180009c80`
- `0x18000b4c8`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180009cbc`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180009cbc`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180009ce3`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180009ce3`

## pseudocode

```c
__int64 DwSoapSizeLimit(void)
{
  __int64 result; // rax
  HKEY hKey; // [rsp+40h] [rbp+8h] BYREF

  result = dword_18001218C;
  if ( !dword_18001218C )
  {
    hKey = 0;
    if ( !RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\UPnP", 0, 1u, &hKey) )
    {
      HrRegQueryDword(hKey, L"SOAP size Limit", &dword_18001218C);
      RegCloseKey(hKey);
    }
    result = dword_18001218C;
    if ( !dword_18001218C )
    {
      result = 0x400000;
      dword_18001218C = 0x400000;
    }
    if ( (unsigned int)result <= 0x2800 )
    {
      result = 10240;
      dword_18001218C = 10240;
    }
    if ( (unsigned int)result >= 0x7FFFFFFF )
    {
      result = 0x7FFFFFFF;
      dword_18001218C = 0x7FFFFFFF;
    }
  }
  return result;
}

```

## disassembly

```asm
0x180009c80  sub     rsp, 38h
0x180009c84  mov     eax, cs:dword_18001218C
0x180009c8a  test    eax, eax
0x180009c8c  jnz     loc_180009D20
0x180009c92  lea     rax, [rsp+38h+hKey]
0x180009c97  mov     [rsp+38h+hKey], 0
0x180009ca0  mov     r9d, 1; samDesired
0x180009ca6  mov     [rsp+38h+phkResult], rax; phkResult
0x180009cab  xor     r8d, r8d; ulOptions
0x180009cae  lea     rdx, aSoftwareMicros_0; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x180009cb5  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180009cbc  call    cs:__imp_RegOpenKeyExW
0x180009cc2  test    eax, eax
0x180009cc4  jnz     short loc_180009CE9
0x180009cc6  mov     rcx, [rsp+38h+hKey]; HKEY
0x180009ccb  lea     r8, dword_18001218C; unsigned int *
0x180009cd2  lea     rdx, aSoapSizeLimit; "SOAP size Limit"
0x180009cd9  call    ?HrRegQueryDword@@YAJPEAUHKEY__@@PEBGPEAK@Z; HrRegQueryDword(HKEY__ *,ushort const *,ulong *)
0x180009cde  mov     rcx, [rsp+38h+hKey]; hKey
0x180009ce3  call    cs:__imp_RegCloseKey
0x180009ce9  mov     eax, cs:dword_18001218C
0x180009cef  test    eax, eax
0x180009cf1  jnz     short loc_180009CFE
0x180009cf3  mov     eax, 400000h
0x180009cf8  mov     cs:dword_18001218C, eax
0x180009cfe  mov     ecx, 2800h
0x180009d03  cmp     eax, ecx
0x180009d05  ja      short loc_180009D0F
0x180009d07  mov     eax, ecx
0x180009d09  mov     cs:dword_18001218C, ecx
0x180009d0f  mov     ecx, 7FFFFFFFh
0x180009d14  cmp     eax, ecx
0x180009d16  jb      short loc_180009D20
0x180009d18  mov     eax, ecx
0x180009d1a  mov     cs:dword_18001218C, ecx
0x180009d20  add     rsp, 38h
0x180009d24  retn
```
