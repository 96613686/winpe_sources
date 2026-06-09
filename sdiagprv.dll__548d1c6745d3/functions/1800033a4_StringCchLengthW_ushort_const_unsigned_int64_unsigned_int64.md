# StringCchLengthW(ushort const *,unsigned __int64,unsigned __int64 *)

- ea: `0x1800033a4`
- end: `0x1800033f9`
- name: `?StringCchLengthW@@YAJPEBG_KPEA_K@Z`
- size: `85`
- prototype: `__int64 __fastcall(const unsigned __int16 *, __int64, unsigned __int64 *)`
- caller_count: `5`
- callee_count: `1`
- tags: ``

## callers

- `0x180002ac4`
- `0x180006a78`
- `0x18000c618`
- `0x18000dc8c`
- `0x18000e7f4`

## callees

- `0x1800033a4`

## pseudocode

```c
__int64 __fastcall StringCchLengthW(const unsigned __int16 *a1, __int64 a2, unsigned __int64 *a3)
{
  __int64 v3; // r9
  __int64 result; // rax

  if ( !a1 )
  {
    result = 2147942487LL;
    goto LABEL_12;
  }
  v3 = a2;
  do
  {
    if ( !*a1 )
      break;
    ++a1;
    --v3;
  }
  while ( v3 );
  result = v3 == 0 ? 0x80070057 : 0;
  if ( !a3 )
  {
    if ( v3 )
      return result;
LABEL_12:
    if ( !a3 )
      return result;
    goto LABEL_13;
  }
  if ( v3 )
  {
    *a3 = a2 - v3;
    return result;
  }
  *a3 = 0;
LABEL_13:
  *a3 = 0;
  return result;
}

```

## disassembly

```asm
0x1800033a4  xor     r10d, r10d
0x1800033a7  test    rcx, rcx
0x1800033aa  jz      short loc_1800033EB
0x1800033ac  mov     r9, rdx
0x1800033af  cmp     [rcx], r10w
0x1800033b3  jz      short loc_1800033BF
0x1800033b5  add     rcx, 2
0x1800033b9  sub     r9, 1
0x1800033bd  jnz     short loc_1800033AF
0x1800033bf  mov     rax, r9
0x1800033c2  neg     rax
0x1800033c5  sbb     eax, eax
0x1800033c7  not     eax
0x1800033c9  and     eax, 80070057h
0x1800033ce  test    r8, r8
0x1800033d1  jz      short loc_1800033E4
0x1800033d3  test    r9, r9
0x1800033d6  jz      short loc_1800033DF
0x1800033d8  sub     rdx, r9
0x1800033db  mov     [r8], rdx
0x1800033de  retn
0x1800033df  mov     [r8], r10
0x1800033e2  jmp     short loc_1800033F5
0x1800033e4  test    r9, r9
0x1800033e7  jnz     short locret_1800033F8
0x1800033e9  jmp     short loc_1800033F0
0x1800033eb  mov     eax, 80070057h
0x1800033f0  test    r8, r8
0x1800033f3  jz      short locret_1800033F8
0x1800033f5  mov     [r8], r10
0x1800033f8  retn
```
