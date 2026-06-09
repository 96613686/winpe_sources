# DeltaDredge2(ulong,ushort * *)

- ea: `0x18000c744`
- end: `0x18000c7f0`
- name: `?DeltaDredge2@@YAKKPEAPEAG@Z`
- size: `172`
- prototype: `__int64 __fastcall(DWORD, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180004390`

## callees

- `0x18000c744`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000c781`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000c781`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000c7e1`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000c7e1`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000c7c4`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000c7c4`

## pseudocode

```c
__int64 __fastcall DeltaDredge2(DWORD a1, unsigned __int16 **a2)
{
  unsigned int v2; // edi
  HKEY v3; // rbx
  DWORD Type; // [rsp+50h] [rbp+8h] BYREF
  unsigned __int16 **cbData; // [rsp+58h] [rbp+10h] BYREF
  HKEY hKey; // [rsp+60h] [rbp+18h] BYREF
  HKEY v8; // [rsp+68h] [rbp+20h]

  cbData = a2;
  Type = a1;
  v2 = 2;
  hKey = 0;
  if ( !RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"Software\\Microsoft\\WBEM\\CIMOM", 0, 0x20019u, &hKey) )
  {
    v3 = hKey;
    v8 = hKey;
    LODWORD(cbData) = 0;
    Type = 0;
    if ( !RegQueryValueExW(hKey, L"KnownSvcs", 0, &Type, 0, (LPDWORD)&cbData) && Type == 7 && (unsigned int)cbData > 2 )
      v2 = 0;
    RegCloseKey(v3);
  }
  return v2;
}

```

## disassembly

```asm
0x18000c744  mov     rax, rsp
0x18000c747  mov     [rax+10h], rdx
0x18000c74b  mov     [rax+8], ecx
0x18000c74e  push    rbx
0x18000c74f  push    rdi
0x18000c750  sub     rsp, 38h
0x18000c754  mov     edi, 2
0x18000c759  mov     qword ptr [rax+18h], 0
0x18000c761  lea     rax, [rax+18h]
0x18000c765  mov     [rsp+48h+phkResult], rax; phkResult
0x18000c76a  mov     r9d, 20019h; samDesired
0x18000c770  xor     r8d, r8d; ulOptions
0x18000c773  lea     rdx, SubKey; "Software\\Microsoft\\WBEM\\CIMOM"
0x18000c77a  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18000c781  call    cs:__imp_RegOpenKeyExW
0x18000c787  test    eax, eax
0x18000c789  jnz     short loc_18000C7E7
0x18000c78b  mov     rbx, [rsp+48h+hKey]
0x18000c790  mov     [rsp+48h+arg_18], rbx
0x18000c795  mov     dword ptr [rsp+48h+cbData], eax
0x18000c799  mov     [rsp+48h+Type], eax
0x18000c79d  lea     rax, [rsp+48h+cbData]
0x18000c7a2  mov     [rsp+48h+lpcbData], rax; lpcbData
0x18000c7a7  mov     [rsp+48h+phkResult], 0; lpData
0x18000c7b0  lea     r9, [rsp+48h+Type]; lpType
0x18000c7b5  xor     r8d, r8d; lpReserved
0x18000c7b8  lea     rdx, aKnownsvcs; "KnownSvcs"
0x18000c7bf  mov     rcx, [rsp+48h+hKey]; hKey
0x18000c7c4  call    cs:__imp_RegQueryValueExW
0x18000c7ca  test    eax, eax
0x18000c7cc  jnz     short loc_18000C7DE
0x18000c7ce  cmp     [rsp+48h+Type], 7
0x18000c7d3  jnz     short loc_18000C7DE
0x18000c7d5  xor     ecx, ecx
0x18000c7d7  cmp     dword ptr [rsp+48h+cbData], edi
0x18000c7db  cmova   edi, ecx
0x18000c7de  mov     rcx, rbx; hKey
0x18000c7e1  call    cs:__imp_RegCloseKey
0x18000c7e7  mov     eax, edi
0x18000c7e9  add     rsp, 38h
0x18000c7ed  pop     rdi
0x18000c7ee  pop     rbx
0x18000c7ef  retn
```
