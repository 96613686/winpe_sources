# DwSoapSizeLimit(void)

- ea: `0x180014e60`
- end: `0x180014f12`
- name: `?DwSoapSizeLimit@@YAKXZ`
- size: `178`
- prototype: `unsigned int(void)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180014580`

## callees

- `0x180014e60`
- `0x180055ab8`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180014ec9`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180014ec9`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180014e9c`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180014e9c`

## pseudocode

```c
__int64 DwSoapSizeLimit(void)
{
  __int64 result; // rax
  HKEY hKey; // [rsp+40h] [rbp+8h] BYREF

  result = dword_1800761E8;
  if ( !dword_1800761E8 )
  {
    hKey = 0;
    if ( !RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\UPnP", 0, 1u, &hKey) )
    {
      HrRegQueryDword(hKey, L"SOAP size Limit", &dword_1800761E8);
      RegCloseKey(hKey);
    }
    result = dword_1800761E8;
    if ( !dword_1800761E8 )
    {
      result = 0x400000;
      dword_1800761E8 = 0x400000;
    }
    if ( (unsigned int)result <= 0x2800 )
    {
      result = 10240;
      dword_1800761E8 = 10240;
    }
    if ( (unsigned int)result >= 0x7FFFFFFF )
    {
      result = 0x7FFFFFFF;
      dword_1800761E8 = 0x7FFFFFFF;
    }
  }
  return result;
}

```

## disassembly

```asm
0x180014e60  sub     rsp, 38h
0x180014e64  mov     eax, cs:dword_1800761E8
0x180014e6a  test    eax, eax
0x180014e6c  jnz     loc_180014F0C
0x180014e72  lea     rax, [rsp+38h+hKey]
0x180014e77  mov     [rsp+38h+hKey], 0
0x180014e80  mov     r9d, 1; samDesired
0x180014e86  mov     [rsp+38h+phkResult], rax; phkResult
0x180014e8b  xor     r8d, r8d; ulOptions
0x180014e8e  lea     rdx, aSoftwareMicros_4; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x180014e95  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180014e9c  call    cs:__imp_RegOpenKeyExW
0x180014ea3  nop     dword ptr [rax+rax+00h]
0x180014ea8  test    eax, eax
0x180014eaa  jnz     short loc_180014ED5
0x180014eac  mov     rcx, [rsp+38h+hKey]; HKEY
0x180014eb1  lea     r8, dword_1800761E8; unsigned int *
0x180014eb8  lea     rdx, aSoapSizeLimit; "SOAP size Limit"
0x180014ebf  call    ?HrRegQueryDword@@YAJPEAUHKEY__@@PEBGPEAK@Z; HrRegQueryDword(HKEY__ *,ushort const *,ulong *)
0x180014ec4  mov     rcx, [rsp+38h+hKey]; hKey
0x180014ec9  call    cs:__imp_RegCloseKey
0x180014ed0  nop     dword ptr [rax+rax+00h]
0x180014ed5  mov     eax, cs:dword_1800761E8
0x180014edb  test    eax, eax
0x180014edd  jnz     short loc_180014EEA
0x180014edf  mov     eax, 400000h
0x180014ee4  mov     cs:dword_1800761E8, eax
0x180014eea  mov     ecx, 2800h
0x180014eef  cmp     eax, ecx
0x180014ef1  ja      short loc_180014EFB
0x180014ef3  mov     eax, ecx
0x180014ef5  mov     cs:dword_1800761E8, ecx
0x180014efb  mov     ecx, 7FFFFFFFh
0x180014f00  cmp     eax, ecx
0x180014f02  jb      short loc_180014F0C
0x180014f04  mov     eax, ecx
0x180014f06  mov     cs:dword_1800761E8, ecx
0x180014f0c  add     rsp, 38h
0x180014f10  retn
```
