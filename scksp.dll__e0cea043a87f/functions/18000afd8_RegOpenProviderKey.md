# RegOpenProviderKey

- ea: `0x18000afd8`
- end: `0x18000b0aa`
- name: `RegOpenProviderKey`
- size: `210`
- prototype: `__int64 __fastcall(PHKEY phkResult)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000abfc`

## callees

- `0x18000afd8`
- `0x18000b0b0`
- `0x18000d9d0`
- `0x18002b140`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18000b076`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18000b076`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000b092`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000b092`

## pseudocode

```c
__int64 __fastcall RegOpenProviderKey(PHKEY phkResult)
{
  wchar_t *v2; // rsi
  unsigned int v3; // edi
  DWORD dwDisposition; // [rsp+68h] [rbp+10h] BYREF

  *phkResult = 0;
  dwDisposition = 0;
  v2 = (wchar_t *)MIDL_user_allocate(0xC4u);
  if ( v2 )
  {
    StringCbPrintfW(
      v2,
      0xC4u,
      L"%s%s",
      L"SYSTEM\\CurrentControlSet\\Control\\Cryptography\\Providers\\",
      L"Microsoft Smart Card Key Storage Provider");
    v3 = RegCreateKeyExW(HKEY_LOCAL_MACHINE, v2, 0, (LPWSTR)&Class, 0, 0x20019u, 0, phkResult, &dwDisposition);
    CspFreeH(v2);
    if ( !v3 )
      return v3;
  }
  else
  {
    v3 = 8;
  }
  if ( *phkResult )
    RegCloseKey(*phkResult);
  return v3;
}

```

## disassembly

```asm
0x18000afd8  mov     rax, rsp
0x18000afdb  mov     [rax+8], rbx
0x18000afdf  mov     [rax+18h], rsi
0x18000afe3  mov     [rax+10h], edx
0x18000afe6  push    rdi
0x18000afe7  sub     rsp, 50h
0x18000afeb  mov     rbx, rcx
0x18000afee  mov     qword ptr [rcx], 0
0x18000aff5  mov     edi, 0C4h
0x18000affa  mov     dword ptr [rax+10h], 0
0x18000b001  mov     ecx, edi; size
0x18000b003  call    MIDL_user_allocate
0x18000b008  mov     rsi, rax
0x18000b00b  test    rax, rax
0x18000b00e  jnz     short loc_18000B015
0x18000b010  lea     edi, [rax+8]
0x18000b013  jmp     short loc_18000B08A
0x18000b015  lea     rax, aMicrosoftSmart; "Microsoft Smart Card Key Storage Provid"...
0x18000b01c  mov     rdx, rdi; cbDest
0x18000b01f  lea     r9, aSystemCurrentc; "SYSTEM\\CurrentControlSet\\Control\\Cry"...
0x18000b026  mov     qword ptr [rsp+58h+dwOptions], rax
0x18000b02b  lea     r8, aSS_0; "%s%s"
0x18000b032  mov     rcx, rsi; pszDest
0x18000b035  call    StringCbPrintfW
0x18000b03a  lea     rax, [rsp+58h+dwDisposition]
0x18000b03f  xor     r8d, r8d; Reserved
0x18000b042  mov     [rsp+58h+lpdwDisposition], rax; lpdwDisposition
0x18000b047  lea     r9, Class; lpClass
0x18000b04e  mov     [rsp+58h+phkResult], rbx; phkResult
0x18000b053  mov     rdx, rsi; lpSubKey
0x18000b056  mov     [rsp+58h+lpSecurityAttributes], 0; lpSecurityAttributes
0x18000b05f  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18000b066  mov     [rsp+58h+samDesired], 20019h; samDesired
0x18000b06e  mov     [rsp+58h+dwOptions], 0; dwOptions
0x18000b076  call    cs:__imp_RegCreateKeyExW
0x18000b07c  mov     edi, eax
0x18000b07e  mov     rcx, rsi
0x18000b081  call    CspFreeH
0x18000b086  test    edi, edi
0x18000b088  jz      short loc_18000B098
0x18000b08a  mov     rcx, [rbx]; hKey
0x18000b08d  test    rcx, rcx
0x18000b090  jz      short loc_18000B098
0x18000b092  call    cs:__imp_RegCloseKey
0x18000b098  mov     rbx, [rsp+58h+arg_0]
0x18000b09d  mov     eax, edi
0x18000b09f  mov     rsi, [rsp+58h+arg_10]
0x18000b0a4  add     rsp, 50h
0x18000b0a8  pop     rdi
0x18000b0a9  retn
```
