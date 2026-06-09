# StringCchLengthW(ushort const *,unsigned __int64,unsigned __int64 *)

- ea: `0x180005060`
- end: `0x1800050c3`
- name: `?StringCchLengthW@@YAJPEBG_KPEA_K@Z`
- size: `99`
- prototype: `__int64 __fastcall(const unsigned __int16 *, unsigned __int64, unsigned __int64 *)`
- caller_count: `16`
- callee_count: `1`
- tags: ``

## callers

- `0x1800039f0`
- `0x180005df0`
- `0x180009820`
- `0x18000ae90`
- `0x18000cd9c`
- `0x1800176e0`
- `0x1800177dc`
- `0x180017a20`
- `0x18001ad08`
- `0x18001ae50`
- `0x1800245e8`
- `0x180024838`
- `0x180024994`
- `0x180024e3c`
- `0x180024f00`
- `0x1800251b8`

## callees

- `0x180005060`

## pseudocode

```c
__int64 __fastcall StringCchLengthW(const unsigned __int16 *a1, unsigned __int64 a2, unsigned __int64 *a3)
{
  unsigned __int64 i; // r9
  __int64 result; // rax

  if ( !a1 || a2 > 0x7FFFFFFF )
  {
    result = 2147942487LL;
    goto LABEL_13;
  }
  for ( i = a2; i; --i )
  {
    if ( !*a1 )
      break;
    ++a1;
  }
  result = i == 0 ? 0x80070057 : 0;
  if ( !a3 )
  {
    if ( i )
      return result;
LABEL_13:
    if ( !a3 )
      return result;
    goto LABEL_14;
  }
  if ( i )
  {
    *a3 = a2 - i;
    return result;
  }
  *a3 = 0;
LABEL_14:
  *a3 = 0;
  return result;
}

```

## disassembly

```asm
0x180005060  xor     r10d, r10d
0x180005063  test    rcx, rcx
0x180005066  jz      short loc_1800050B5
0x180005068  cmp     rdx, 7FFFFFFFh
0x18000506f  ja      short loc_1800050B5
0x180005071  mov     r9, rdx
0x180005074  test    rdx, rdx
0x180005077  jz      short loc_180005089
0x180005079  cmp     [rcx], r10w
0x18000507d  jz      short loc_180005089
0x18000507f  add     rcx, 2
0x180005083  sub     r9, 1
0x180005087  jnz     short loc_180005079
0x180005089  mov     rax, r9
0x18000508c  neg     rax
0x18000508f  sbb     eax, eax
0x180005091  not     eax
0x180005093  and     eax, 80070057h
0x180005098  test    r8, r8
0x18000509b  jz      short loc_1800050AE
0x18000509d  test    r9, r9
0x1800050a0  jz      short loc_1800050A9
0x1800050a2  sub     rdx, r9
0x1800050a5  mov     [r8], rdx
0x1800050a8  retn
0x1800050a9  mov     [r8], r10
0x1800050ac  jmp     short loc_1800050BF
0x1800050ae  test    r9, r9
0x1800050b1  jnz     short locret_1800050C2
0x1800050b3  jmp     short loc_1800050BA
0x1800050b5  mov     eax, 80070057h
0x1800050ba  test    r8, r8
0x1800050bd  jz      short locret_1800050C2
0x1800050bf  mov     [r8], r10
0x1800050c2  retn
```
