# CLogConfigurableFilter::CompareDate(double,tagLOG_FILTER_COMPAREOP,double)

- ea: `0x180025828`
- end: `0x18002588b`
- name: `?CompareDate@CLogConfigurableFilter@@IEAAHNW4tagLOG_FILTER_COMPAREOP@@N@Z`
- size: `99`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180025b34`

## callees

- `0x180025828`

## pseudocode

```c
bool __fastcall CLogConfigurableFilter::CompareDate(__int64 a1, double a2, int a3, double a4)
{
  int v4; // r8d
  int v5; // r8d
  int v6; // r8d
  int v7; // r8d
  bool result; // al
  bool v9; // cf
  bool v10; // cf
  bool v11; // zf

  if ( !a3 )
    return a2 == a4;
  v4 = a3 - 1;
  if ( !v4 )
    return a2 != a4;
  v5 = v4 - 1;
  if ( !v5 )
  {
    v10 = a4 < a2;
    v11 = a4 == a2;
    return !v10 && !v11;
  }
  v6 = v5 - 1;
  if ( !v6 )
  {
    v9 = a4 < a2;
    return !v9;
  }
  v7 = v6 - 1;
  if ( !v7 )
  {
    v10 = a2 < a4;
    v11 = a2 == a4;
    return !v10 && !v11;
  }
  result = 0;
  if ( v7 == 1 )
  {
    v9 = a2 < a4;
    return !v9;
  }
  return result;
}

```

## disassembly

```asm
0x180025828  test    r8d, r8d
0x18002582b  jz      short loc_18002587D
0x18002582d  sub     r8d, 1
0x180025831  jz      short loc_180025871
0x180025833  sub     r8d, 1
0x180025837  jz      short loc_180025866
0x180025839  sub     r8d, 1
0x18002583d  jz      short loc_18002585B
0x18002583f  sub     r8d, 1
0x180025843  jz      short loc_180025853
0x180025845  xor     eax, eax
0x180025847  cmp     r8d, 1
0x18002584b  jnz     short locret_18002587B
0x18002584d  comisd  xmm1, xmm3
0x180025851  jmp     short loc_180025861
0x180025853  xor     eax, eax
0x180025855  comisd  xmm1, xmm3
0x180025859  jmp     short loc_18002586C
0x18002585b  xor     eax, eax
0x18002585d  comisd  xmm3, xmm1
0x180025861  setnb   al
0x180025864  retn
0x180025866  xor     eax, eax
0x180025868  comisd  xmm3, xmm1
0x18002586c  setnbe  al
0x18002586f  retn
0x180025871  ucomisd xmm1, xmm3
0x180025875  jp      short loc_180025885
0x180025877  jnz     short loc_180025885
0x180025879  xor     eax, eax
0x18002587b  retn
0x18002587d  ucomisd xmm1, xmm3
0x180025881  jp      short loc_180025879
0x180025883  jnz     short loc_180025879
0x180025885  mov     eax, 1
0x18002588a  retn
```
