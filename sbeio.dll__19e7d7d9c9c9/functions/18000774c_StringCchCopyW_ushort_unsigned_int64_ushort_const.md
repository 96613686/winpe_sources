# StringCchCopyW(ushort *,unsigned __int64,ushort const *)

- ea: `0x18000774c`
- end: `0x1800077b7`
- name: `?StringCchCopyW@@YAJPEAG_KPEBG@Z`
- size: `107`
- prototype: `__int64 __fastcall(unsigned __int16 *, unsigned __int64, const unsigned __int16 *)`
- caller_count: `17`
- callee_count: `1`
- tags: ``

## callers

- `0x1800057f4`
- `0x180005df0`
- `0x180009820`
- `0x18000cd9c`
- `0x1800177dc`
- `0x180017a20`
- `0x180019f40`
- `0x18001a994`
- `0x18001ad08`
- `0x18001c560`
- `0x1800245e8`
- `0x180024838`
- `0x180024994`
- `0x180024e3c`
- `0x180024f00`
- `0x1800251b8`
- `0x180026b08`

## callees

- `0x18000774c`

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
0x18000774c  xor     r10d, r10d
0x18000774f  mov     r9, rcx
0x180007752  test    rdx, rdx
0x180007755  jz      short loc_1800077A8
0x180007757  cmp     rdx, 7FFFFFFFh
0x18000775e  jbe     short loc_180007767
0x180007760  mov     eax, 80070057h
0x180007765  jmp     short loc_1800077B2
0x180007767  mov     eax, 7FFFFFFEh
0x18000776c  test    rax, rax
0x18000776f  jz      short loc_18000778F
0x180007771  movzx   ecx, word ptr [r8]
0x180007775  test    cx, cx
0x180007778  jz      short loc_18000778F
0x18000777a  mov     [r9], cx
0x18000777e  add     r8, 2
0x180007782  add     r9, 2
0x180007786  dec     rax
0x180007789  sub     rdx, 1
0x18000778d  jnz     short loc_18000776C
0x18000778f  test    rdx, rdx
0x180007792  lea     rcx, [r9-2]
0x180007796  cmovnz  rcx, r9
0x18000779a  neg     rdx
0x18000779d  sbb     eax, eax
0x18000779f  not     eax
0x1800077a1  and     eax, 8007007Ah
0x1800077a6  jmp     short loc_1800077B2
0x1800077a8  mov     eax, 80070057h
0x1800077ad  test    rdx, rdx
0x1800077b0  jz      short locret_1800077B6
0x1800077b2  mov     [rcx], r10w
0x1800077b6  retn
```
