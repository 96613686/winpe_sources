# DwSoapSizeLimit(void)

- ea: `0x18001fc9c`
- end: `0x18001fd41`
- name: `?DwSoapSizeLimit@@YAKXZ`
- size: `165`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18001f41c`

## callees

- `0x18001fc9c`
- `0x180052258`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001fcff`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001fcff`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001fcd8`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001fcd8`

## pseudocode

```c
__int64 DwSoapSizeLimit(void)
{
  __int64 result; // rax
  HKEY hKey; // [rsp+40h] [rbp+8h] BYREF

  result = dword_1800720E0;
  if ( !dword_1800720E0 )
  {
    hKey = 0;
    if ( !RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\UPnP", 0, 1u, &hKey) )
    {
      HrRegQueryDword(hKey, L"SOAP size Limit", &dword_1800720E0);
      RegCloseKey(hKey);
    }
    result = dword_1800720E0;
    if ( !dword_1800720E0 )
    {
      result = 0x400000;
      dword_1800720E0 = 0x400000;
    }
    if ( (unsigned int)result <= 0x2800 )
    {
      result = 10240;
      dword_1800720E0 = 10240;
    }
    if ( (unsigned int)result >= 0x7FFFFFFF )
    {
      result = 0x7FFFFFFF;
      dword_1800720E0 = 0x7FFFFFFF;
    }
  }
  return result;
}

```

## disassembly

```asm
0x18001fc9c  sub     rsp, 38h
0x18001fca0  mov     eax, cs:dword_1800720E0
0x18001fca6  test    eax, eax
0x18001fca8  jnz     loc_18001FD3C
0x18001fcae  lea     rax, [rsp+38h+hKey]
0x18001fcb3  mov     [rsp+38h+hKey], 0
0x18001fcbc  mov     r9d, 1; samDesired
0x18001fcc2  mov     [rsp+38h+phkResult], rax; phkResult
0x18001fcc7  xor     r8d, r8d; ulOptions
0x18001fcca  lea     rdx, aSoftwareMicros_4; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x18001fcd1  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18001fcd8  call    cs:__imp_RegOpenKeyExW
0x18001fcde  test    eax, eax
0x18001fce0  jnz     short loc_18001FD05
0x18001fce2  mov     rcx, [rsp+38h+hKey]; HKEY
0x18001fce7  lea     r8, dword_1800720E0; unsigned int *
0x18001fcee  lea     rdx, aSoapSizeLimit; "SOAP size Limit"
0x18001fcf5  call    ?HrRegQueryDword@@YAJPEAUHKEY__@@PEBGPEAK@Z; HrRegQueryDword(HKEY__ *,ushort const *,ulong *)
0x18001fcfa  mov     rcx, [rsp+38h+hKey]; hKey
0x18001fcff  call    cs:__imp_RegCloseKey
0x18001fd05  mov     eax, cs:dword_1800720E0
0x18001fd0b  test    eax, eax
0x18001fd0d  jnz     short loc_18001FD1A
0x18001fd0f  mov     eax, 400000h
0x18001fd14  mov     cs:dword_1800720E0, eax
0x18001fd1a  mov     ecx, 2800h
0x18001fd1f  cmp     eax, ecx
0x18001fd21  ja      short loc_18001FD2B
0x18001fd23  mov     eax, ecx
0x18001fd25  mov     cs:dword_1800720E0, ecx
0x18001fd2b  mov     ecx, 7FFFFFFFh
0x18001fd30  cmp     eax, ecx
0x18001fd32  jb      short loc_18001FD3C
0x18001fd34  mov     eax, ecx
0x18001fd36  mov     cs:dword_1800720E0, ecx
0x18001fd3c  add     rsp, 38h
0x18001fd40  retn
```
