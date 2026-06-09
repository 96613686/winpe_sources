# StringCchCopyW(ushort *,unsigned __int64,ushort const *)

- ea: `0x18001e15c`
- end: `0x18001e1c7`
- name: `?StringCchCopyW@@YAJPEAG_KPEBG@Z`
- size: `107`
- prototype: `__int64 __fastcall(unsigned __int16 *, unsigned __int64, const unsigned __int16 *)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x180005b30`
- `0x18000f5a0`
- `0x1800236b4`

## callees

- `0x18001e15c`

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
0x18001e15c  xor     r10d, r10d
0x18001e15f  mov     r9, rcx
0x18001e162  test    rdx, rdx
0x18001e165  jz      short loc_18001E1B8
0x18001e167  cmp     rdx, 7FFFFFFFh
0x18001e16e  jbe     short loc_18001E177
0x18001e170  mov     eax, 80070057h
0x18001e175  jmp     short loc_18001E1C2
0x18001e177  mov     eax, 7FFFFFFEh
0x18001e17c  test    rax, rax
0x18001e17f  jz      short loc_18001E19F
0x18001e181  movzx   ecx, word ptr [r8]
0x18001e185  test    cx, cx
0x18001e188  jz      short loc_18001E19F
0x18001e18a  mov     [r9], cx
0x18001e18e  add     r8, 2
0x18001e192  add     r9, 2
0x18001e196  dec     rax
0x18001e199  sub     rdx, 1
0x18001e19d  jnz     short loc_18001E17C
0x18001e19f  test    rdx, rdx
0x18001e1a2  lea     rcx, [r9-2]
0x18001e1a6  cmovnz  rcx, r9
0x18001e1aa  neg     rdx
0x18001e1ad  sbb     eax, eax
0x18001e1af  not     eax
0x18001e1b1  and     eax, 8007007Ah
0x18001e1b6  jmp     short loc_18001E1C2
0x18001e1b8  mov     eax, 80070057h
0x18001e1bd  test    rdx, rdx
0x18001e1c0  jz      short locret_18001E1C6
0x18001e1c2  mov     [rcx], r10w
0x18001e1c6  retn
```
