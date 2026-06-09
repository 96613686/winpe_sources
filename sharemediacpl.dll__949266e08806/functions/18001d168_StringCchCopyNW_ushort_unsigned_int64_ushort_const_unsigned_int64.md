# StringCchCopyNW(ushort *,unsigned __int64,ushort const *,unsigned __int64)

- ea: `0x18001d168`
- end: `0x18001d1e5`
- name: `?StringCchCopyNW@@YAJPEAG_KPEBG1@Z`
- size: `125`
- prototype: `__int64 __fastcall(unsigned __int16 *, unsigned __int64, const unsigned __int16 *, unsigned __int64)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x18001cd1c`
- `0x18001cf74`

## callees

- `0x18001d168`

## pseudocode

```c
__int64 __fastcall StringCchCopyNW(
        unsigned __int16 *a1,
        unsigned __int64 a2,
        unsigned __int16 *a3,
        unsigned __int64 a4)
{
  unsigned __int64 v4; // r10
  unsigned __int16 *v5; // r11
  unsigned int v6; // edx

  v4 = a2;
  v5 = a1;
  if ( a2 )
  {
    if ( a2 > 0x7FFFFFFF || a4 > 0x7FFFFFFE )
    {
      v6 = -2147024809;
    }
    else
    {
      do
      {
        if ( !a4 )
          break;
        if ( !*a3 )
          break;
        *v5++ = *a3++;
        --a4;
        --v4;
      }
      while ( v4 );
      a1 = v5 - 1;
      if ( v4 )
        a1 = v5;
      v6 = v4 == 0 ? 0x8007007A : 0;
    }
    *a1 = 0;
  }
  else
  {
    return (unsigned int)-2147024809;
  }
  return v6;
}

```

## disassembly

```asm
0x18001d168  mov     [rsp+arg_0], rbx
0x18001d16d  xor     ebx, ebx
0x18001d16f  mov     r10, rdx
0x18001d172  mov     r11, rcx
0x18001d175  test    rdx, rdx
0x18001d178  jz      short loc_18001D1D0
0x18001d17a  cmp     rdx, 7FFFFFFFh
0x18001d181  jbe     short loc_18001D18A
0x18001d183  mov     edx, 80070057h
0x18001d188  jmp     short loc_18001D1DA
0x18001d18a  cmp     r9, 7FFFFFFEh
0x18001d191  ja      short loc_18001D183
0x18001d193  test    r9, r9
0x18001d196  jz      short loc_18001D1B6
0x18001d198  movzx   eax, word ptr [r8]
0x18001d19c  test    ax, ax
0x18001d19f  jz      short loc_18001D1B6
0x18001d1a1  mov     [r11], ax
0x18001d1a5  add     r8, 2
0x18001d1a9  add     r11, 2
0x18001d1ad  dec     r9
0x18001d1b0  sub     r10, 1
0x18001d1b4  jnz     short loc_18001D193
0x18001d1b6  test    r10, r10
0x18001d1b9  lea     rcx, [r11-2]
0x18001d1bd  cmovnz  rcx, r11
0x18001d1c1  neg     r10
0x18001d1c4  sbb     edx, edx
0x18001d1c6  not     edx
0x18001d1c8  and     edx, 8007007Ah
0x18001d1ce  jmp     short loc_18001D1DA
0x18001d1d0  mov     edx, 80070057h
0x18001d1d5  test    r10, r10
0x18001d1d8  jz      short loc_18001D1DD
0x18001d1da  mov     [rcx], bx
0x18001d1dd  mov     rbx, [rsp+arg_0]
0x18001d1e2  mov     eax, edx
0x18001d1e4  retn
```
