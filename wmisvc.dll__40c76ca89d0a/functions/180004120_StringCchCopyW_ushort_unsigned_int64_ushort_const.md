# StringCchCopyW(ushort *,unsigned __int64,ushort const *)

- ea: `0x180004120`
- end: `0x18000418d`
- name: `?StringCchCopyW@@YAJPEAG_KPEBG@Z`
- size: `109`
- prototype: `__int64 __fastcall(unsigned __int16 *, unsigned __int64, unsigned __int16 *)`
- caller_count: `21`
- callee_count: `1`
- tags: ``

## callers

- `0x180001470`
- `0x180002a5c`
- `0x1800031e0`
- `0x180003b94`
- `0x18000408c`
- `0x180004900`
- `0x180005a60`
- `0x180006e18`
- `0x180006ed0`
- `0x18000ac5c`
- `0x18000ba0c`
- `0x180012e9c`
- `0x180013ddc`
- `0x180013edc`
- `0x1800142c0`
- `0x18001855c`
- `0x180018654`
- `0x180018850`
- `0x180019520`
- `0x18001ae4c`
- `0x18001c450`

## callees

- `0x180004120`

## pseudocode

```c
__int64 __fastcall StringCchCopyW(unsigned __int16 *a1, unsigned __int64 a2, unsigned __int16 *a3)
{
  unsigned __int16 *v3; // r9
  __int64 v4; // rax
  unsigned __int16 *v5; // rax
  __int64 result; // rax

  v3 = a1;
  if ( !a2 )
    return 2147942487LL;
  if ( a2 > 0x7FFFFFFF )
  {
    result = 2147942487LL;
    *a1 = 0;
  }
  else
  {
    v4 = 2147483646;
    do
    {
      if ( !v4 )
        break;
      if ( !*a3 )
        break;
      *v3++ = *a3++;
      --v4;
      --a2;
    }
    while ( a2 );
    v5 = v3 - 1;
    if ( a2 )
      v5 = v3;
    *v5 = 0;
    result = 2147942522LL;
    if ( a2 )
      return 0;
  }
  return result;
}

```

## disassembly

```asm
0x180004120  mov     r9, rcx
0x180004123  test    rdx, rdx
0x180004126  jz      short loc_18000417C
0x180004128  cmp     rdx, 7FFFFFFFh
0x18000412f  ja      short loc_180004175
0x180004131  mov     eax, 7FFFFFFEh
0x180004136  test    rax, rax
0x180004139  jz      short loc_180004159
0x18000413b  movzx   ecx, word ptr [r8]
0x18000413f  test    cx, cx
0x180004142  jz      short loc_180004159
0x180004144  mov     [r9], cx
0x180004148  add     r8, 2
0x18000414c  add     r9, 2
0x180004150  dec     rax
0x180004153  sub     rdx, 1
0x180004157  jnz     short loc_180004136
0x180004159  test    rdx, rdx
0x18000415c  lea     rax, [r9-2]
0x180004160  cmovnz  rax, r9
0x180004164  xor     ecx, ecx
0x180004166  test    rdx, rdx
0x180004169  mov     [rax], cx
0x18000416c  mov     eax, 8007007Ah
0x180004171  cmovnz  eax, ecx
0x180004174  retn
0x180004175  mov     eax, 80070057h
0x18000417a  jmp     short loc_180004186
0x18000417c  mov     eax, 80070057h
0x180004181  test    rdx, rdx
0x180004184  jz      short locret_180004174
0x180004186  xor     ecx, ecx
0x180004188  mov     [r9], cx
0x18000418c  retn
```
