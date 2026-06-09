# StringCchCopyW(ushort *,unsigned __int64,ushort const *)

- ea: `0x180005d08`
- end: `0x180005d73`
- name: `?StringCchCopyW@@YAJPEAG_KPEBG@Z`
- size: `107`
- prototype: `__int64 __fastcall(unsigned __int16 *, unsigned __int64, unsigned __int16 *)`
- caller_count: `8`
- callee_count: `1`
- tags: ``

## callers

- `0x180004434`
- `0x180004608`
- `0x18000f1f8`
- `0x18000ff3c`
- `0x18001e2fc`
- `0x18001e5e8`
- `0x18001e8f0`
- `0x18001ecec`

## callees

- `0x180005d08`

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
0x180005d08  xor     r10d, r10d
0x180005d0b  mov     r9, rcx
0x180005d0e  test    rdx, rdx
0x180005d11  jz      short loc_180005D64
0x180005d13  cmp     rdx, 7FFFFFFFh
0x180005d1a  jbe     short loc_180005D23
0x180005d1c  mov     eax, 80070057h
0x180005d21  jmp     short loc_180005D6E
0x180005d23  mov     eax, 7FFFFFFEh
0x180005d28  test    rax, rax
0x180005d2b  jz      short loc_180005D4B
0x180005d2d  movzx   ecx, word ptr [r8]
0x180005d31  test    cx, cx
0x180005d34  jz      short loc_180005D4B
0x180005d36  mov     [r9], cx
0x180005d3a  add     r8, 2
0x180005d3e  add     r9, 2
0x180005d42  dec     rax
0x180005d45  sub     rdx, 1
0x180005d49  jnz     short loc_180005D28
0x180005d4b  test    rdx, rdx
0x180005d4e  lea     rcx, [r9-2]
0x180005d52  cmovnz  rcx, r9
0x180005d56  neg     rdx
0x180005d59  sbb     eax, eax
0x180005d5b  not     eax
0x180005d5d  and     eax, 8007007Ah
0x180005d62  jmp     short loc_180005D6E
0x180005d64  mov     eax, 80070057h
0x180005d69  test    rdx, rdx
0x180005d6c  jz      short locret_180005D72
0x180005d6e  mov     [rcx], r10w
0x180005d72  retn
```
