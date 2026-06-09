# ASNUnregisterServer(void)

- ea: `0x180035a4c`
- end: `0x180035af4`
- name: `?ASNUnregisterServer@@YAJXZ`
- size: `168`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180035980`

## callees

- `0x180035a4c`
- `0x180035afc`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180035a8a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180035ac9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180035a8a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180035ac9`
- `CRYPT32!CryptUnregisterOIDFunction` at `0x180035a80`
- `CRYPT32!CryptUnregisterOIDFunction` at `0x180035abf`
- `CRYPT32!CryptUnregisterOIDFunction` at `0x180035a80`
- `CRYPT32!CryptUnregisterOIDFunction` at `0x180035abf`

## string_xrefs

- `0x180035a69`: `CryptDllEncodeObject`
- `0x180035aa8`: `CryptDllDecodeObject`

## pseudocode

```c
__int64 ASNUnregisterServer(void)
{
  unsigned int v0; // edi
  unsigned int i; // ebx
  unsigned int j; // ebx

  v0 = 0;
  for ( i = 0; i < 0x22; ++i )
  {
    if ( !CryptUnregisterOIDFunction(1u, "CryptDllEncodeObject", off_180052CC0[2 * (int)i]) && GetLastError() != 2 )
      v0 = HError();
  }
  for ( j = 0; j < 0x22; ++j )
  {
    if ( !CryptUnregisterOIDFunction(1u, "CryptDllDecodeObject", off_180052A90[2 * (int)j]) && GetLastError() != 2 )
      v0 = HError();
  }
  return v0;
}

```

## disassembly

```asm
0x180035a4c  mov     [rsp+arg_0], rbx
0x180035a51  mov     [rsp+arg_8], rbp
0x180035a56  push    rdi
0x180035a57  sub     rsp, 20h
0x180035a5b  xor     edi, edi
0x180035a5d  lea     rbp, __ImageBase
0x180035a64  xor     ebx, ebx
0x180035a66  movsxd  r8, ebx
0x180035a69  lea     rdx, pszFuncName; "CryptDllEncodeObject"
0x180035a70  add     r8, r8
0x180035a73  mov     ecx, 1; dwEncodingType
0x180035a78  mov     r8, ss:rva off_180052CC0[rbp+r8*8]; pszOID
0x180035a80  call    cs:__imp_CryptUnregisterOIDFunction
0x180035a86  test    eax, eax
0x180035a88  jnz     short loc_180035A9C
0x180035a8a  call    cs:__imp_GetLastError
0x180035a90  cmp     eax, 2
0x180035a93  jz      short loc_180035A9C
0x180035a95  call    ?HError@@YAJXZ; HError(void)
0x180035a9a  mov     edi, eax
0x180035a9c  inc     ebx
0x180035a9e  cmp     ebx, 22h ; '"'
0x180035aa1  jb      short loc_180035A66
0x180035aa3  xor     ebx, ebx
0x180035aa5  movsxd  r8, ebx
0x180035aa8  lea     rdx, aCryptdlldecode; "CryptDllDecodeObject"
0x180035aaf  add     r8, r8
0x180035ab2  mov     ecx, 1; dwEncodingType
0x180035ab7  mov     r8, ss:rva off_180052A90[rbp+r8*8]; pszOID
0x180035abf  call    cs:__imp_CryptUnregisterOIDFunction
0x180035ac5  test    eax, eax
0x180035ac7  jnz     short loc_180035ADB
0x180035ac9  call    cs:__imp_GetLastError
0x180035acf  cmp     eax, 2
0x180035ad2  jz      short loc_180035ADB
0x180035ad4  call    ?HError@@YAJXZ; HError(void)
0x180035ad9  mov     edi, eax
0x180035adb  inc     ebx
0x180035add  cmp     ebx, 22h ; '"'
0x180035ae0  jb      short loc_180035AA5
0x180035ae2  mov     rbx, [rsp+28h+arg_0]
0x180035ae7  mov     eax, edi
0x180035ae9  mov     rbp, [rsp+28h+arg_8]
0x180035aee  add     rsp, 20h
0x180035af2  pop     rdi
0x180035af3  retn
```
