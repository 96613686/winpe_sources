# StringCchCopyW(ushort *,unsigned __int64,ushort const *)

- ea: `0x1800098f8`
- end: `0x180009963`
- name: `?StringCchCopyW@@YAJPEAG_KPEBG@Z`
- size: `107`
- prototype: `__int64 __fastcall(unsigned __int16 *, unsigned __int64, const unsigned __int16 *)`
- caller_count: `7`
- callee_count: `1`
- tags: ``

## callers

- `0x180004780`
- `0x1800064e8`
- `0x180006b88`
- `0x180007720`
- `0x18000a72c`
- `0x18000a820`
- `0x18000ad88`

## callees

- `0x1800098f8`

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
0x1800098f8  xor     r10d, r10d
0x1800098fb  mov     r9, rcx
0x1800098fe  test    rdx, rdx
0x180009901  jz      short loc_180009954
0x180009903  cmp     rdx, 7FFFFFFFh
0x18000990a  jbe     short loc_180009913
0x18000990c  mov     eax, 80070057h
0x180009911  jmp     short loc_18000995E
0x180009913  mov     eax, 7FFFFFFEh
0x180009918  test    rax, rax
0x18000991b  jz      short loc_18000993B
0x18000991d  movzx   ecx, word ptr [r8]
0x180009921  test    cx, cx
0x180009924  jz      short loc_18000993B
0x180009926  mov     [r9], cx
0x18000992a  add     r8, 2
0x18000992e  add     r9, 2
0x180009932  dec     rax
0x180009935  sub     rdx, 1
0x180009939  jnz     short loc_180009918
0x18000993b  test    rdx, rdx
0x18000993e  lea     rcx, [r9-2]
0x180009942  cmovnz  rcx, r9
0x180009946  neg     rdx
0x180009949  sbb     eax, eax
0x18000994b  not     eax
0x18000994d  and     eax, 8007007Ah
0x180009952  jmp     short loc_18000995E
0x180009954  mov     eax, 80070057h
0x180009959  test    rdx, rdx
0x18000995c  jz      short locret_180009962
0x18000995e  mov     [rcx], r10w
0x180009962  retn
```
