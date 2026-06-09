# CRegistryKey::SetUlongValue(ushort const *,ulong)

- ea: `0x18000c16c`
- end: `0x18000c1af`
- name: `?SetUlongValue@CRegistryKey@@QEAAXPEBGK@Z`
- size: `67`
- prototype: `void __fastcall(HKEY *this, const unsigned __int16 *)`
- caller_count: `8`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x180003dc4`
- `0x1800045d0`
- `0x1800053e4`
- `0x180005e94`
- `0x1800066a8`
- `0x1800078e0`
- `0x180008b6c`
- `0x180008bf0`

## callees

- `0x180008020`
- `0x18000c16c`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18000c193`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18000c193`

## pseudocode

```c
void __fastcall CRegistryKey::SetUlongValue(HKEY *this, const unsigned __int16 *a2)
{
  HKEY v2; // rcx
  unsigned int v3; // eax
  BYTE Data[24]; // [rsp+30h] [rbp-18h] BYREF

  v2 = *this;
  *(_DWORD *)Data = 0;
  v3 = RegSetValueExW(v2, a2, 0, 4u, Data, 4u);
  if ( v3 )
    CException::ThrowException(v3, 0, 0);
}

```

## disassembly

```asm
0x18000c16c  sub     rsp, 48h
0x18000c170  mov     rcx, [rcx]; hKey
0x18000c173  lea     rax, [rsp+48h+Data]
0x18000c178  mov     r9d, 4; dwType
0x18000c17e  mov     dword ptr [rsp+48h+Data], 0
0x18000c186  mov     [rsp+48h+cbData], r9d; cbData
0x18000c18b  xor     r8d, r8d; Reserved
0x18000c18e  mov     [rsp+48h+lpData], rax; lpData
0x18000c193  call    cs:__imp_RegSetValueExW
0x18000c199  test    eax, eax
0x18000c19b  jz      short loc_18000C1AA
0x18000c19d  xor     r8d, r8d
0x18000c1a0  xor     edx, edx
0x18000c1a2  mov     ecx, eax
0x18000c1a4  call    ?ThrowException@CException@@SAXKW4ErrorCodeType@@PEBGZZ; CException::ThrowException(ulong,ErrorCodeType,ushort const *,...)
0x18000c1aa  add     rsp, 48h
0x18000c1ae  retn
```
