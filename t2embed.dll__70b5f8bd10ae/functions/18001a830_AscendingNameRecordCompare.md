# AscendingNameRecordCompare

- ea: `0x18001a830`
- end: `0x18001a86d`
- name: `AscendingNameRecordCompare`
- size: `61`
- prototype: `int __cdecl(const void *, const void *)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x18001a830`

## pseudocode

```c
__int64 __fastcall AscendingNameRecordCompare(_WORD *a1, _WORD *a2)
{
  unsigned __int16 v3; // ax
  bool v4; // cf
  unsigned __int16 v5; // ax
  unsigned __int16 v6; // ax

  if ( *a1 != *a2 )
    return *a1 < *a2 ? -1 : 1;
  v3 = a1[1];
  v4 = v3 < a2[1];
  if ( v3 == a2[1] )
  {
    v5 = a1[2];
    v4 = v5 < a2[2];
    if ( v5 == a2[2] )
    {
      v6 = a1[3];
      v4 = v6 < a2[3];
      if ( v6 == a2[3] )
        return 0;
    }
  }
  if ( v4 )
    return 0xFFFFFFFFLL;
  return 1;
}

```

## disassembly

```asm
0x18001a830  movzx   eax, word ptr [rcx]
0x18001a833  cmp     ax, [rdx]
0x18001a836  jz      short loc_18001A840
0x18001a838  sbb     eax, eax
0x18001a83a  and     eax, 0FFFFFFFEh
0x18001a83d  inc     eax
0x18001a83f  retn
0x18001a840  movzx   eax, word ptr [rcx+2]
0x18001a844  cmp     ax, [rdx+2]
0x18001a848  jnz     short loc_18001A85E
0x18001a84a  movzx   eax, word ptr [rcx+4]
0x18001a84e  cmp     ax, [rdx+4]
0x18001a852  jnz     short loc_18001A85E
0x18001a854  movzx   eax, word ptr [rcx+6]
0x18001a858  cmp     ax, [rdx+6]
0x18001a85c  jz      short loc_18001A86A
0x18001a85e  jnb     short loc_18001A864
0x18001a860  or      eax, 0FFFFFFFFh
0x18001a863  retn
0x18001a864  mov     eax, 1
0x18001a869  retn
0x18001a86a  xor     eax, eax
0x18001a86c  retn
```
