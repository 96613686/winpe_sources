# __std_type_info_compare

- ea: `0x180003248`
- end: `0x18000326f`
- name: `__std_type_info_compare`
- size: `39`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180006388`

## callees

- `0x180003248`

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
0x180003248  cmp     rcx, rdx
0x18000324b  jz      short loc_180003266
0x18000324d  add     rdx, 9
0x180003251  lea     rax, [rcx+9]
0x180003255  sub     rdx, rax
0x180003258  mov     cl, [rax]
0x18000325a  cmp     cl, [rax+rdx]
0x18000325d  jnz     short loc_180003269
0x18000325f  inc     rax
0x180003262  test    cl, cl
0x180003264  jnz     short loc_180003258
0x180003266  xor     eax, eax
0x180003268  retn
0x180003269  sbb     eax, eax
0x18000326b  or      eax, 1
0x18000326e  retn
```
