# LdapConvertSecurityError

- ea: `0x180018cc0`
- end: `0x180018d47`
- name: `LdapConvertSecurityError`
- size: `135`
- prototype: ``
- caller_count: `9`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18000ce40`
- `0x180017854`
- `0x1800191d0`
- `0x18001c2d0`
- `0x18001ef6c`
- `0x18002b1a4`
- `0x18002c04c`
- `0x18004b28c`
- `0x18004b920`

## callees

- `0x180006510`
- `0x180018cc0`

## pseudocode

```c
__int64 __fastcall LdapConvertSecurityError(__int64 a1, signed int a2, __int64 a3)
{
  if ( a2 <= -2146893043 )
  {
    if ( a2 != -2146893043 )
    {
      if ( a2 == -2146893056 )
        return 90;
      if ( a2 == -2146893052 )
        goto LABEL_17;
      if ( a2 != -2146893051 )
      {
        if ( a2 == -2146893050 || a2 == -2146893044 )
          return 49;
LABEL_17:
        SetConnectionError(a1, a2, a3);
        return 82;
      }
    }
    return 86;
  }
  if ( a2 == -2146893042 )
    return 49;
  if ( !a2 )
    return 0;
  if ( a2 != 58 )
  {
    if ( a2 == 1460 )
      return 85;
    goto LABEL_17;
  }
  return 81;
}

```

## disassembly

```asm
0x180018cc0  sub     rsp, 28h
0x180018cc4  mov     eax, 8009030Dh
0x180018cc9  cmp     edx, eax
0x180018ccb  jle     short loc_180018CE1
0x180018ccd  cmp     edx, 8009030Eh
0x180018cd3  jz      short loc_180018D0B
0x180018cd5  test    edx, edx
0x180018cd7  jnz     short loc_180018D20
0x180018cd9  xor     eax, eax
0x180018cdb  add     rsp, 28h
0x180018cdf  retn
0x180018ce1  jz      short loc_180018D19
0x180018ce3  cmp     edx, 80090300h
0x180018ce9  jz      short loc_180018D12
0x180018ceb  cmp     edx, 80090304h
0x180018cf1  jz      short loc_180018D34
0x180018cf3  cmp     edx, 80090305h
0x180018cf9  jz      short loc_180018D19
0x180018cfb  cmp     edx, 80090306h
0x180018d01  jz      short loc_180018D0B
0x180018d03  cmp     edx, 8009030Ch
0x180018d09  jnz     short loc_180018D34
0x180018d0b  mov     eax, 31h ; '1'
0x180018d10  jmp     short loc_180018CDB
0x180018d12  mov     eax, 5Ah ; 'Z'
0x180018d17  jmp     short loc_180018CDB
0x180018d19  mov     eax, 56h ; 'V'
0x180018d1e  jmp     short loc_180018CDB
0x180018d20  cmp     edx, 3Ah ; ':'
0x180018d23  jz      short loc_180018D40
0x180018d25  cmp     edx, 5B4h
0x180018d2b  jnz     short loc_180018D34
0x180018d2d  mov     eax, 55h ; 'U'
0x180018d32  jmp     short loc_180018CDB
0x180018d34  call    SetConnectionError
0x180018d39  mov     eax, 52h ; 'R'
0x180018d3e  jmp     short loc_180018CDB
0x180018d40  mov     eax, 51h ; 'Q'
0x180018d45  jmp     short loc_180018CDB
```
