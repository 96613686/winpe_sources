# StringCchCopyW(ushort *,unsigned __int64,ushort const *)

- ea: `0x140009c04`
- end: `0x140009c6f`
- name: `?StringCchCopyW@@YAJPEAG_KPEBG@Z`
- size: `107`
- prototype: `__int64 __fastcall(unsigned __int16 *, unsigned __int64, const unsigned __int16 *)`
- caller_count: `19`
- callee_count: `1`
- tags: ``

## callers

- `0x1400032c0`
- `0x140005914`
- `0x140006588`
- `0x1400069c8`
- `0x140006f6c`
- `0x140007d94`
- `0x140008d14`
- `0x140009258`
- `0x14000dab0`
- `0x140013e10`
- `0x1400157ac`
- `0x1400172f4`
- `0x140017398`
- `0x14001b10c`
- `0x14001b4a8`
- `0x14001b5d0`
- `0x14001cd40`
- `0x140021eb4`
- `0x140021ff4`

## callees

- `0x140009c04`

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
0x140009c04  xor     r10d, r10d
0x140009c07  mov     r9, rcx
0x140009c0a  test    rdx, rdx
0x140009c0d  jz      short loc_140009C60
0x140009c0f  cmp     rdx, 7FFFFFFFh
0x140009c16  jbe     short loc_140009C1F
0x140009c18  mov     eax, 80070057h
0x140009c1d  jmp     short loc_140009C6A
0x140009c1f  mov     eax, 7FFFFFFEh
0x140009c24  test    rax, rax
0x140009c27  jz      short loc_140009C47
0x140009c29  movzx   ecx, word ptr [r8]
0x140009c2d  test    cx, cx
0x140009c30  jz      short loc_140009C47
0x140009c32  mov     [r9], cx
0x140009c36  add     r8, 2
0x140009c3a  add     r9, 2
0x140009c3e  dec     rax
0x140009c41  sub     rdx, 1
0x140009c45  jnz     short loc_140009C24
0x140009c47  test    rdx, rdx
0x140009c4a  lea     rcx, [r9-2]
0x140009c4e  cmovnz  rcx, r9
0x140009c52  neg     rdx
0x140009c55  sbb     eax, eax
0x140009c57  not     eax
0x140009c59  and     eax, 8007007Ah
0x140009c5e  jmp     short loc_140009C6A
0x140009c60  mov     eax, 80070057h
0x140009c65  test    rdx, rdx
0x140009c68  jz      short locret_140009C6E
0x140009c6a  mov     [rcx], r10w
0x140009c6e  retn
```
