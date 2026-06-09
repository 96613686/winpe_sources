# __std_type_info_compare

- ea: `0x100417540`
- end: `0x100417567`
- name: `__std_type_info_compare`
- size: `39`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x100419bb4`

## callees

- `0x100417540`

## pseudocode

```c
__int64 __fastcall _std_type_info_compare(__int64 a1, __int64 a2)
{
  char *v2; // rax
  __int64 v3; // rdx
  char v4; // cl

  if ( a1 == a2 )
    return 0;
  v2 = (char *)(a1 + 9);
  v3 = a2 - a1;
  while ( 1 )
  {
    v4 = *v2;
    if ( *v2 != v2[v3] )
      break;
    ++v2;
    if ( !v4 )
      return 0;
  }
  return (unsigned __int8)*v2 < (unsigned __int8)v2[v3] ? -1 : 1;
}

```

## disassembly

```asm
0x100417540  cmp     rcx, rdx
0x100417543  jz      short loc_10041755E
0x100417545  add     rdx, 9
0x100417549  lea     rax, [rcx+9]
0x10041754d  sub     rdx, rax
0x100417550  mov     cl, [rax]
0x100417552  cmp     cl, [rax+rdx]
0x100417555  jnz     short loc_100417561
0x100417557  inc     rax
0x10041755a  test    cl, cl
0x10041755c  jnz     short loc_100417550
0x10041755e  xor     eax, eax
0x100417560  retn
0x100417561  sbb     eax, eax
0x100417563  or      eax, 1
0x100417566  retn
```
