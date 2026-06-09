# StringCchCopyW(ushort *,unsigned __int64,ushort const *)

- ea: `0x1400062b4`
- end: `0x14000631f`
- name: `?StringCchCopyW@@YAJPEAG_KPEBG@Z`
- size: `107`
- prototype: `__int64 __fastcall(unsigned __int16 *, unsigned __int64, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x140007798`

## callees

- `0x1400062b4`

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
0x1400062b4  xor     r10d, r10d
0x1400062b7  mov     r9, rcx
0x1400062ba  test    rdx, rdx
0x1400062bd  jz      short loc_140006310
0x1400062bf  cmp     rdx, 7FFFFFFFh
0x1400062c6  jbe     short loc_1400062CF
0x1400062c8  mov     eax, 80070057h
0x1400062cd  jmp     short loc_14000631A
0x1400062cf  mov     eax, 7FFFFFFEh
0x1400062d4  test    rax, rax
0x1400062d7  jz      short loc_1400062F7
0x1400062d9  movzx   ecx, word ptr [r8]
0x1400062dd  test    cx, cx
0x1400062e0  jz      short loc_1400062F7
0x1400062e2  mov     [r9], cx
0x1400062e6  add     r8, 2
0x1400062ea  add     r9, 2
0x1400062ee  dec     rax
0x1400062f1  sub     rdx, 1
0x1400062f5  jnz     short loc_1400062D4
0x1400062f7  test    rdx, rdx
0x1400062fa  lea     rcx, [r9-2]
0x1400062fe  cmovnz  rcx, r9
0x140006302  neg     rdx
0x140006305  sbb     eax, eax
0x140006307  not     eax
0x140006309  and     eax, 8007007Ah
0x14000630e  jmp     short loc_14000631A
0x140006310  mov     eax, 80070057h
0x140006315  test    rdx, rdx
0x140006318  jz      short locret_14000631E
0x14000631a  mov     [rcx], r10w
0x14000631e  retn
```
