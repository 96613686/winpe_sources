# RegCreateHKCUKeyExU

- ea: `0x180013ec0`
- end: `0x180013f52`
- name: `RegCreateHKCUKeyExU`
- size: `146`
- prototype: `DWORD __fastcall(__int64, __int64, __int64, __int64, int, REGSAM samDesired, int, PHKEY phkResult, LPDWORD lpdwDisposition)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180037030`

## callees

- `0x180013ec0`
- `0x180014490`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180013f29`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180013f29`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180013f44`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180013f44`

## pseudocode

```c
DWORD __fastcall RegCreateHKCUKeyExU(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        int a5,
        REGSAM samDesired,
        int a7,
        PHKEY phkResult,
        LPDWORD lpdwDisposition)
{
  DWORD result; // eax
  LSTATUS Key; // ebx
  HKEY hKey; // [rsp+78h] [rbp+20h] BYREF

  hKey = 0;
  result = RegOpenHKCUEx(&hKey);
  if ( !result )
  {
    Key = RegCreateKeyExW(
            hKey,
            L"Software\\Microsoft\\Windows\\CurrentVersion\\WinTrust\\Trust Providers\\Software Publishing",
            0,
            0,
            0,
            samDesired,
            0,
            phkResult,
            lpdwDisposition);
    if ( hKey )
    {
      if ( hKey != HKEY_CURRENT_USER )
        RegCloseKey(hKey);
    }
    return Key;
  }
  return result;
}

```

## disassembly

```asm
0x180013ec0  mov     [rsp+hKey], r9
0x180013ec5  push    rbx
0x180013ec6  sub     rsp, 50h
0x180013eca  lea     rcx, [rsp+58h+hKey]
0x180013ecf  mov     [rsp+58h+hKey], 0
0x180013ed8  call    RegOpenHKCUEx
0x180013edd  test    eax, eax
0x180013edf  jnz     short loc_180013F4C
0x180013ee1  mov     rax, [rsp+58h+arg_40]
0x180013ee9  lea     rdx, aSoftwareMicros_4; "Software\\Microsoft\\Windows\\CurrentVe"...
0x180013ef0  mov     rcx, [rsp+58h+hKey]; hKey
0x180013ef5  xor     r9d, r9d; lpClass
0x180013ef8  mov     [rsp+58h+lpdwDisposition], rax; lpdwDisposition
0x180013efd  xor     r8d, r8d; Reserved
0x180013f00  mov     rax, [rsp+58h+arg_38]
0x180013f08  mov     [rsp+58h+phkResult], rax; phkResult
0x180013f0d  mov     eax, [rsp+58h+arg_28]
0x180013f14  mov     [rsp+58h+lpSecurityAttributes], 0; lpSecurityAttributes
0x180013f1d  mov     [rsp+58h+samDesired], eax; samDesired
0x180013f21  mov     [rsp+58h+dwOptions], 0; dwOptions
0x180013f29  call    cs:__imp_RegCreateKeyExW
0x180013f2f  mov     rcx, [rsp+58h+hKey]; hKey
0x180013f34  mov     ebx, eax
0x180013f36  test    rcx, rcx
0x180013f39  jz      short loc_180013F4A
0x180013f3b  cmp     rcx, 0FFFFFFFF80000001h
0x180013f42  jz      short loc_180013F4A
0x180013f44  call    cs:__imp_RegCloseKey
0x180013f4a  mov     eax, ebx
0x180013f4c  add     rsp, 50h
0x180013f50  pop     rbx
0x180013f51  retn
```
