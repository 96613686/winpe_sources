# RtmConvertNetAddressToIpv6AddressAndLength

- ea: `0x18000dc60`
- end: `0x18000dcf2`
- name: `RtmConvertNetAddressToIpv6AddressAndLength`
- size: `146`
- prototype: `DWORD __stdcall(PRTM_NET_ADDRESS pNetAddress, PIN6_ADDR pAddress, PDWORD pLength, DWORD dwAddressSize)`
- caller_count: `6`
- callee_count: `1`
- tags: ``

## callers

- `0x1800027d8`
- `0x180002dd0`
- `0x180003a20`
- `0x18000b440`
- `0x18000c560`
- `0x18000cf90`

## callees

- `0x18000dc60`

## pseudocode

```c
DWORD __stdcall RtmConvertNetAddressToIpv6AddressAndLength(
        PRTM_NET_ADDRESS pNetAddress,
        PIN6_ADDR pAddress,
        PDWORD pLength,
        DWORD dwAddressSize)
{
  __int64 v6; // rdx
  unsigned int v7; // eax
  __int64 i; // rcx
  UCHAR v9; // bl

  if ( !pNetAddress || !pAddress || !pLength || dwAddressSize > 0x10 )
    return 87;
  v6 = pNetAddress->NumBits >> 3;
  v7 = pNetAddress->NumBits & 0x80000007;
  for ( i = 0; (unsigned int)i < dwAddressSize; i = (unsigned int)(i + 1) )
  {
    if ( (unsigned int)i >= (unsigned int)v6 )
      v9 = 0;
    else
      v9 = pNetAddress->AddrBits[i];
    pAddress->u.Byte[i] = v9;
  }
  if ( v7 )
    pAddress->u.Byte[v6] = pNetAddress->AddrBits[v6] & (-1 << (8 - v7));
  *pLength = pNetAddress->NumBits;
  return 0;
}

```

## disassembly

```asm
0x18000dc60  mov     [rsp+arg_0], rbx
0x18000dc65  mov     [rsp+arg_8], rdi
0x18000dc6a  mov     r11, rdx
0x18000dc6d  mov     r10, rcx
0x18000dc70  test    rcx, rcx
0x18000dc73  jz      short loc_18000DCE2
0x18000dc75  test    rdx, rdx
0x18000dc78  jz      short loc_18000DCE2
0x18000dc7a  test    r8, r8
0x18000dc7d  jz      short loc_18000DCE2
0x18000dc7f  cmp     r9d, 10h
0x18000dc83  ja      short loc_18000DCE2
0x18000dc85  movzx   eax, word ptr [rcx+2]
0x18000dc89  mov     edx, eax
0x18000dc8b  shr     edx, 3
0x18000dc8e  and     eax, 80000007h
0x18000dc93  jge     short loc_18000DC9C
0x18000dc95  dec     eax
0x18000dc97  or      eax, 0FFFFFFF8h
0x18000dc9a  inc     eax
0x18000dc9c  xor     ecx, ecx
0x18000dc9e  test    r9d, r9d
0x18000dca1  jz      short loc_18000DCBB
0x18000dca3  cmp     ecx, edx
0x18000dca5  jnb     short loc_18000DCAE
0x18000dca7  mov     bl, [rcx+r10+4]
0x18000dcac  jmp     short loc_18000DCB0
0x18000dcae  xor     bl, bl
0x18000dcb0  mov     [rcx+r11], bl
0x18000dcb4  inc     ecx
0x18000dcb6  cmp     ecx, r9d
0x18000dcb9  jb      short loc_18000DCA3
0x18000dcbb  test    eax, eax
0x18000dcbd  jz      short loc_18000DCD6
0x18000dcbf  mov     ecx, 8
0x18000dcc4  sub     ecx, eax
0x18000dcc6  mov     eax, 0FFh
0x18000dccb  shl     al, cl
0x18000dccd  and     al, [rdx+r10+4]
0x18000dcd2  mov     [rdx+r11], al
0x18000dcd6  movzx   eax, word ptr [r10+2]
0x18000dcdb  mov     [r8], eax
0x18000dcde  xor     eax, eax
0x18000dce0  jmp     short loc_18000DCE7
0x18000dce2  mov     eax, 57h ; 'W'
0x18000dce7  mov     rbx, [rsp+arg_0]
0x18000dcec  mov     rdi, [rsp+arg_8]
0x18000dcf1  retn
```
