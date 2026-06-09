# Ipv4AddressType

- ea: `0x140004da0`
- end: `0x140004de7`
- name: `Ipv4AddressType`
- size: `71`
- prototype: `NL_ADDRESS_TYPE __stdcall(const UCHAR *Address)`
- caller_count: `9`
- callee_count: `1`
- tags: ``

## callers

- `0x140008a7c`
- `0x14000d334`
- `0x14000ee40`
- `0x1400105b0`
- `0x140010e64`
- `0x140011978`
- `0x1400161c0`
- `0x14001e01c`
- `0x14001e08c`

## callees

- `0x140004da0`

## pseudocode

```c
NL_ADDRESS_TYPE __stdcall Ipv4AddressType(const UCHAR *Address)
{
  int v1; // eax
  int v2; // ecx
  bool v3; // zf
  NL_ADDRESS_TYPE result; // eax

  v1 = *(_DWORD *)Address;
  v2 = *(_DWORD *)Address & 0xF0;
  if ( v2 == 224 )
    return 3;
  if ( v1 == -1 )
    return 4;
  if ( !v1 )
    return 0;
  v3 = (_BYTE)v1 == 0;
  result = NlatInvalid;
  if ( !v3 && v2 != 240 )
    return 1;
  return result;
}

```

## disassembly

```asm
0x140004da0  mov     eax, [rcx]
0x140004da2  mov     ecx, eax
0x140004da4  and     ecx, 0F0h
0x140004daa  cmp     ecx, 0E0h
0x140004db0  jz      short loc_140004DC6
0x140004db2  cmp     eax, 0FFFFFFFFh
0x140004db5  jz      short loc_140004DE1
0x140004db7  test    eax, eax
0x140004db9  jz      short loc_140004DDD
0x140004dbb  test    al, al
0x140004dbd  mov     eax, 5
0x140004dc2  jnz     short loc_140004DCD
0x140004dc4  retn
0x140004dc6  mov     eax, 3
0x140004dcb  retn
0x140004dcd  cmp     ecx, 0F0h
0x140004dd3  mov     edx, 1
0x140004dd8  cmovnz  eax, edx
0x140004ddb  retn
0x140004ddd  xor     eax, eax
0x140004ddf  retn
0x140004de1  mov     eax, 4
0x140004de6  retn
```
