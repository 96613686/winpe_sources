# StringCchCopyW(ushort *,unsigned __int64,ushort const *)

- ea: `0x1800058f4`
- end: `0x18000595f`
- name: `?StringCchCopyW@@YAJPEAG_KPEBG@Z`
- size: `107`
- prototype: `__int64 __fastcall(unsigned __int16 *, unsigned __int64, unsigned __int16 *)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x180007ce8`
- `0x1800089a8`

## callees

- `0x1800058f4`

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
0x1800058f4  xor     r10d, r10d
0x1800058f7  mov     r9, rcx
0x1800058fa  test    rdx, rdx
0x1800058fd  jz      short loc_180005950
0x1800058ff  cmp     rdx, 7FFFFFFFh
0x180005906  jbe     short loc_18000590F
0x180005908  mov     eax, 80070057h
0x18000590d  jmp     short loc_18000595A
0x18000590f  mov     eax, 7FFFFFFEh
0x180005914  test    rax, rax
0x180005917  jz      short loc_180005937
0x180005919  movzx   ecx, word ptr [r8]
0x18000591d  test    cx, cx
0x180005920  jz      short loc_180005937
0x180005922  mov     [r9], cx
0x180005926  add     r8, 2
0x18000592a  add     r9, 2
0x18000592e  dec     rax
0x180005931  sub     rdx, 1
0x180005935  jnz     short loc_180005914
0x180005937  test    rdx, rdx
0x18000593a  lea     rcx, [r9-2]
0x18000593e  cmovnz  rcx, r9
0x180005942  neg     rdx
0x180005945  sbb     eax, eax
0x180005947  not     eax
0x180005949  and     eax, 8007007Ah
0x18000594e  jmp     short loc_18000595A
0x180005950  mov     eax, 80070057h
0x180005955  test    rdx, rdx
0x180005958  jz      short locret_18000595E
0x18000595a  mov     [rcx], r10w
0x18000595e  retn
```
