# WscGetDatastoreRegKey(_SECURITY_PRODUCT_TYPE)

- ea: `0x1800287b0`
- end: `0x1800287cc`
- name: `?WscGetDatastoreRegKey@@YAPEBGW4_SECURITY_PRODUCT_TYPE@@@Z`
- size: `28`
- prototype: `const unsigned __int16 *__fastcall(enum _SECURITY_PRODUCT_TYPE)`
- caller_count: `3`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180016d50`
- `0x180037a0c`
- `0x18003e88c`

## callees

- `0x1800287b0`

## string_xrefs

- `0x1800287c4`: `SOFTWARE\Microsoft\Security Center\Provider\Av`
- `0x1800287bc`: `SOFTWARE\Microsoft\Security Center\Provider\Fw`

## pseudocode

```c
const unsigned __int16 *__fastcall WscGetDatastoreRegKey(enum _SECURITY_PRODUCT_TYPE a1)
{
  if ( a1 == SECURITY_PRODUCT_TYPE_ANTIVIRUS )
    return L"SOFTWARE\\Microsoft\\Security Center\\Provider\\Av";
  if ( a1 == SECURITY_PRODUCT_TYPE_FIREWALL )
    return L"SOFTWARE\\Microsoft\\Security Center\\Provider\\Fw";
  return 0;
}

```

## disassembly

```asm
0x1800287b0  test    ecx, ecx
0x1800287b2  jz      short loc_1800287C4
0x1800287b4  cmp     ecx, 1
0x1800287b7  jz      short loc_1800287BC
0x1800287b9  xor     eax, eax
0x1800287bb  retn
0x1800287bc  lea     rax, aSoftwareMicros_7; "SOFTWARE\\Microsoft\\Security Center\\P"...
0x1800287c3  retn
0x1800287c4  lea     rax, aSoftwareMicros_13; "SOFTWARE\\Microsoft\\Security Center\\P"...
0x1800287cb  retn
```
