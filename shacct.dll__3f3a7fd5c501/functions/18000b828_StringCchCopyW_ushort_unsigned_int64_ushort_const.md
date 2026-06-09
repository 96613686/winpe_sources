# StringCchCopyW(ushort *,unsigned __int64,ushort const *)

- ea: `0x18000b828`
- end: `0x18000b893`
- name: `?StringCchCopyW@@YAJPEAG_KPEBG@Z`
- size: `107`
- prototype: `__int64 __fastcall(unsigned __int16 *, unsigned __int64, const unsigned __int16 *)`
- caller_count: `6`
- callee_count: `1`
- tags: ``

## callers

- `0x18000e6ec`
- `0x18000ed10`
- `0x180013f44`
- `0x1800164c8`
- `0x1800169c4`
- `0x180016aa8`

## callees

- `0x18000b828`

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
0x18000b828  xor     r10d, r10d
0x18000b82b  mov     r9, rcx
0x18000b82e  test    rdx, rdx
0x18000b831  jz      short loc_18000B884
0x18000b833  cmp     rdx, 7FFFFFFFh
0x18000b83a  jbe     short loc_18000B843
0x18000b83c  mov     eax, 80070057h
0x18000b841  jmp     short loc_18000B88E
0x18000b843  mov     eax, 7FFFFFFEh
0x18000b848  test    rax, rax
0x18000b84b  jz      short loc_18000B86B
0x18000b84d  movzx   ecx, word ptr [r8]
0x18000b851  test    cx, cx
0x18000b854  jz      short loc_18000B86B
0x18000b856  mov     [r9], cx
0x18000b85a  add     r8, 2
0x18000b85e  add     r9, 2
0x18000b862  dec     rax
0x18000b865  sub     rdx, 1
0x18000b869  jnz     short loc_18000B848
0x18000b86b  test    rdx, rdx
0x18000b86e  lea     rcx, [r9-2]
0x18000b872  cmovnz  rcx, r9
0x18000b876  neg     rdx
0x18000b879  sbb     eax, eax
0x18000b87b  not     eax
0x18000b87d  and     eax, 8007007Ah
0x18000b882  jmp     short loc_18000B88E
0x18000b884  mov     eax, 80070057h
0x18000b889  test    rdx, rdx
0x18000b88c  jz      short locret_18000B892
0x18000b88e  mov     [rcx], r10w
0x18000b892  retn
```
