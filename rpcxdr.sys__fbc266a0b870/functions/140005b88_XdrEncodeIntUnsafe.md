# XdrEncodeIntUnsafe

- ea: `0x140005b88`
- end: `0x140005ba3`
- name: `XdrEncodeIntUnsafe`
- size: `27`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `7`
- callee_count: `1`
- tags: ``

## callers

- `0x140002514`
- `0x140004774`
- `0x140004808`
- `0x140004844`
- `0x140004958`
- `0x140004b84`
- `0x140005b40`

## callees

- `0x140005b88`

## pseudocode

```c
__int64 __fastcall XdrEncodeIntUnsafe(__int64 a1, unsigned int a2)
{
  __int64 v2; // rax
  __int64 result; // rax

  v2 = *(_QWORD *)(a1 + 72);
  if ( v2 )
    v2 = *(_QWORD *)(v2 + 64);
  *(_DWORD *)v2 = _byteswap_ulong(a2);
  result = *(_QWORD *)(a1 + 72);
  *(_QWORD *)(result + 64) += 4LL;
  return result;
}

```

## disassembly

```asm
0x140005b88  mov     rax, [rcx+48h]
0x140005b8c  test    rax, rax
0x140005b8f  jz      short loc_140005B95
0x140005b91  mov     rax, [rax+40h]
0x140005b95  bswap   edx
0x140005b97  mov     [rax], edx
0x140005b99  mov     rax, [rcx+48h]
0x140005b9d  add     qword ptr [rax+40h], 4
0x140005ba2  retn
```
