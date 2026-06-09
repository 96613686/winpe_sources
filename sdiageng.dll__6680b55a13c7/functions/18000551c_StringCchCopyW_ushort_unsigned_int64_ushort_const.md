# StringCchCopyW(ushort *,unsigned __int64,ushort const *)

- ea: `0x18000551c`
- end: `0x180005587`
- name: `?StringCchCopyW@@YAJPEAG_KPEBG@Z`
- size: `107`
- prototype: `__int64 __fastcall(unsigned __int16 *, unsigned __int64, unsigned __int16 *)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x18001ee38`
- `0x180027aa0`

## callees

- `0x18000551c`

## pseudocode

```c
__int64 __fastcall StringCchCopyW(unsigned __int16 *a1, unsigned __int64 a2, unsigned __int16 *a3)
{
  unsigned __int16 *v3; // r9
  __int64 result; // rax
  __int64 v5; // rax

  v3 = a1;
  if ( !a2 )
    return 2147942487LL;
  if ( a2 <= 0x7FFFFFFF )
  {
    v5 = 2147483646;
    do
    {
      if ( !v5 )
        break;
      if ( !*a3 )
        break;
      *v3++ = *a3++;
      --v5;
      --a2;
    }
    while ( a2 );
    a1 = v3 - 1;
    if ( a2 )
      a1 = v3;
    result = a2 == 0 ? 0x8007007A : 0;
  }
  else
  {
    result = 2147942487LL;
  }
  *a1 = 0;
  return result;
}

```

## disassembly

```asm
0x18000551c  xor     r10d, r10d
0x18000551f  mov     r9, rcx
0x180005522  test    rdx, rdx
0x180005525  jz      short loc_180005578
0x180005527  cmp     rdx, 7FFFFFFFh
0x18000552e  jbe     short loc_180005537
0x180005530  mov     eax, 80070057h
0x180005535  jmp     short loc_180005582
0x180005537  mov     eax, 7FFFFFFEh
0x18000553c  test    rax, rax
0x18000553f  jz      short loc_18000555F
0x180005541  movzx   ecx, word ptr [r8]
0x180005545  test    cx, cx
0x180005548  jz      short loc_18000555F
0x18000554a  mov     [r9], cx
0x18000554e  add     r8, 2
0x180005552  add     r9, 2
0x180005556  dec     rax
0x180005559  sub     rdx, 1
0x18000555d  jnz     short loc_18000553C
0x18000555f  test    rdx, rdx
0x180005562  lea     rcx, [r9-2]
0x180005566  cmovnz  rcx, r9
0x18000556a  neg     rdx
0x18000556d  sbb     eax, eax
0x18000556f  not     eax
0x180005571  and     eax, 8007007Ah
0x180005576  jmp     short loc_180005582
0x180005578  mov     eax, 80070057h
0x18000557d  test    rdx, rdx
0x180005580  jz      short locret_180005586
0x180005582  mov     [rcx], r10w
0x180005586  retn
```
