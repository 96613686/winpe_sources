# CLogConfigurableFilter::CompareDword(ulong,tagLOG_FILTER_COMPAREOP,ulong)

- ea: `0x180025894`
- end: `0x1800258f2`
- name: `?CompareDword@CLogConfigurableFilter@@IEAAHKW4tagLOG_FILTER_COMPAREOP@@K@Z`
- size: `94`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180025b34`

## callees

- `0x180025894`

## pseudocode

```c
bool __fastcall CLogConfigurableFilter::CompareDword(__int64 a1, unsigned int a2, int a3, unsigned int a4)
{
  int v4; // r8d
  int v5; // r8d
  int v6; // r8d
  int v7; // r8d
  bool result; // al

  if ( !a3 )
    return a2 == a4;
  v4 = a3 - 1;
  if ( !v4 )
    return a2 != a4;
  v5 = v4 - 1;
  if ( !v5 )
    return a2 < a4;
  v6 = v5 - 1;
  if ( !v6 )
    return a2 <= a4;
  v7 = v6 - 1;
  if ( !v7 )
    return a2 > a4;
  result = 0;
  if ( v7 == 1 )
    return a2 >= a4;
  return result;
}

```

## disassembly

```asm
0x180025894  test    r8d, r8d
0x180025897  jz      short loc_1800258E9
0x180025899  sub     r8d, 1
0x18002589d  jz      short loc_1800258DF
0x18002589f  sub     r8d, 1
0x1800258a3  jz      short loc_1800258D5
0x1800258a5  sub     r8d, 1
0x1800258a9  jz      short loc_1800258CB
0x1800258ab  sub     r8d, 1
0x1800258af  jz      short loc_1800258C1
0x1800258b1  xor     eax, eax
0x1800258b3  cmp     r8d, 1
0x1800258b7  jnz     short locret_1800258F1
0x1800258b9  cmp     edx, r9d
0x1800258bc  setnb   al
0x1800258bf  retn
0x1800258c1  xor     eax, eax
0x1800258c3  cmp     edx, r9d
0x1800258c6  setnbe  al
0x1800258c9  retn
0x1800258cb  xor     eax, eax
0x1800258cd  cmp     edx, r9d
0x1800258d0  setbe   al
0x1800258d3  retn
0x1800258d5  xor     eax, eax
0x1800258d7  cmp     edx, r9d
0x1800258da  setb    al
0x1800258dd  retn
0x1800258df  xor     eax, eax
0x1800258e1  cmp     edx, r9d
0x1800258e4  setnz   al
0x1800258e7  retn
0x1800258e9  xor     eax, eax
0x1800258eb  cmp     edx, r9d
0x1800258ee  setz    al
0x1800258f1  retn
```
