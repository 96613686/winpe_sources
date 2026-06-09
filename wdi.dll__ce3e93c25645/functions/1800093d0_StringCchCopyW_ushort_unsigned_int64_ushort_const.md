# StringCchCopyW(ushort *,unsigned __int64,ushort const *)

- ea: `0x1800093d0`
- end: `0x18000943b`
- name: `?StringCchCopyW@@YAJPEAG_KPEBG@Z`
- size: `107`
- prototype: `__int64 __fastcall(unsigned __int16 *, unsigned __int64, unsigned __int16 *)`
- caller_count: `6`
- callee_count: `1`
- tags: ``

## callers

- `0x180005000`
- `0x180005880`
- `0x1800072f0`
- `0x1800098e0`
- `0x18000bff0`
- `0x18000d514`

## callees

- `0x1800093d0`

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
0x1800093d0  xor     r10d, r10d
0x1800093d3  mov     r9, rcx
0x1800093d6  test    rdx, rdx
0x1800093d9  jz      short loc_18000942C
0x1800093db  cmp     rdx, 7FFFFFFFh
0x1800093e2  jbe     short loc_1800093EB
0x1800093e4  mov     eax, 80070057h
0x1800093e9  jmp     short loc_180009436
0x1800093eb  mov     eax, 7FFFFFFEh
0x1800093f0  test    rax, rax
0x1800093f3  jz      short loc_180009413
0x1800093f5  movzx   ecx, word ptr [r8]
0x1800093f9  test    cx, cx
0x1800093fc  jz      short loc_180009413
0x1800093fe  mov     [r9], cx
0x180009402  add     r8, 2
0x180009406  add     r9, 2
0x18000940a  dec     rax
0x18000940d  sub     rdx, 1
0x180009411  jnz     short loc_1800093F0
0x180009413  test    rdx, rdx
0x180009416  lea     rcx, [r9-2]
0x18000941a  cmovnz  rcx, r9
0x18000941e  neg     rdx
0x180009421  sbb     eax, eax
0x180009423  not     eax
0x180009425  and     eax, 8007007Ah
0x18000942a  jmp     short loc_180009436
0x18000942c  mov     eax, 80070057h
0x180009431  test    rdx, rdx
0x180009434  jz      short locret_18000943A
0x180009436  mov     [rcx], r10w
0x18000943a  retn
```
