# StringCchCopyW(ushort *,unsigned __int64,ushort const *)

- ea: `0x1800176e8`
- end: `0x180017737`
- name: `?StringCchCopyW@@YAJPEAG_KPEBG@Z`
- size: `79`
- prototype: `__int64 __fastcall(unsigned __int16 *, unsigned __int64, const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x180018eec`
- `0x18001c0e8`

## callees

- `0x1800176e8`

## pseudocode

```c
__int64 __fastcall StringCchCopyW(unsigned __int16 *a1, __int64 a2, unsigned __int16 *a3)
{
  __int64 v3; // rax
  __int64 v4; // r9
  unsigned __int16 *v5; // rdx
  __int64 result; // rax

  v3 = 2147483646;
  v4 = 260;
  do
  {
    if ( !v3 )
      break;
    if ( !*a3 )
      break;
    *a1++ = *a3++;
    --v3;
    --v4;
  }
  while ( v4 );
  v5 = a1 - 1;
  result = v4 == 0 ? 0x8007007A : 0;
  if ( v4 )
    v5 = a1;
  *v5 = 0;
  return result;
}

```

## disassembly

```asm
0x1800176e8  mov     eax, 7FFFFFFEh
0x1800176ed  mov     r9d, 104h
0x1800176f3  xor     r10d, r10d
0x1800176f6  test    rax, rax
0x1800176f9  jz      short loc_180017718
0x1800176fb  movzx   edx, word ptr [r8]
0x1800176ff  test    dx, dx
0x180017702  jz      short loc_180017718
0x180017704  mov     [rcx], dx
0x180017707  add     r8, 2
0x18001770b  add     rcx, 2
0x18001770f  dec     rax
0x180017712  sub     r9, 1
0x180017716  jnz     short loc_1800176F6
0x180017718  mov     rax, r9
0x18001771b  lea     rdx, [rcx-2]
0x18001771f  neg     rax
0x180017722  sbb     eax, eax
0x180017724  not     eax
0x180017726  and     eax, 8007007Ah
0x18001772b  test    r9, r9
0x18001772e  cmovnz  rdx, rcx
0x180017732  mov     [rdx], r10w
0x180017736  retn
```
