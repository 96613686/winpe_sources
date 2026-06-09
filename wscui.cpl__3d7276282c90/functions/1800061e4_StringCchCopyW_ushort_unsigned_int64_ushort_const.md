# StringCchCopyW(ushort *,unsigned __int64,ushort const *)

- ea: `0x1800061e4`
- end: `0x18000624f`
- name: `?StringCchCopyW@@YAJPEAG_KPEBG@Z`
- size: `107`
- prototype: `__int64 __fastcall(unsigned __int16 *, unsigned __int64, const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x1800052cc`
- `0x180009300`

## callees

- `0x1800061e4`

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
0x1800061e4  xor     r10d, r10d
0x1800061e7  mov     r9, rcx
0x1800061ea  test    rdx, rdx
0x1800061ed  jz      short loc_180006240
0x1800061ef  cmp     rdx, 7FFFFFFFh
0x1800061f6  jbe     short loc_1800061FF
0x1800061f8  mov     eax, 80070057h
0x1800061fd  jmp     short loc_18000624A
0x1800061ff  mov     eax, 7FFFFFFEh
0x180006204  test    rax, rax
0x180006207  jz      short loc_180006227
0x180006209  movzx   ecx, word ptr [r8]
0x18000620d  test    cx, cx
0x180006210  jz      short loc_180006227
0x180006212  mov     [r9], cx
0x180006216  add     r8, 2
0x18000621a  add     r9, 2
0x18000621e  dec     rax
0x180006221  sub     rdx, 1
0x180006225  jnz     short loc_180006204
0x180006227  test    rdx, rdx
0x18000622a  lea     rcx, [r9-2]
0x18000622e  cmovnz  rcx, r9
0x180006232  neg     rdx
0x180006235  sbb     eax, eax
0x180006237  not     eax
0x180006239  and     eax, 8007007Ah
0x18000623e  jmp     short loc_18000624A
0x180006240  mov     eax, 80070057h
0x180006245  test    rdx, rdx
0x180006248  jz      short locret_18000624E
0x18000624a  mov     [rcx], r10w
0x18000624e  retn
```
