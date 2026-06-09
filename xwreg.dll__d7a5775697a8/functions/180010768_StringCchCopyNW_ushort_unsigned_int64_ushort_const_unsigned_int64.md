# StringCchCopyNW(ushort *,unsigned __int64,ushort const *,unsigned __int64)

- ea: `0x180010768`
- end: `0x1800107b5`
- name: `?StringCchCopyNW@@YAJPEAG_KPEBG1@Z`
- size: `77`
- prototype: `__int64 __fastcall(unsigned __int16 *, unsigned __int64, const unsigned __int16 *, unsigned __int64)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x18000e8bc`

## callees

- `0x180010768`

## pseudocode

```c
__int64 __fastcall StringCchCopyNW(unsigned __int16 *a1, __int64 a2, unsigned __int16 *a3)
{
  __int64 v3; // rax
  __int64 v4; // r9
  unsigned __int16 *v5; // rdx
  __int64 result; // rax

  v3 = 260;
  v4 = 261;
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
0x180010768  mov     eax, 104h
0x18001076d  xor     r10d, r10d
0x180010770  lea     r9d, [rax+1]
0x180010774  test    rax, rax
0x180010777  jz      short loc_180010796
0x180010779  movzx   edx, word ptr [r8]
0x18001077d  test    dx, dx
0x180010780  jz      short loc_180010796
0x180010782  mov     [rcx], dx
0x180010785  add     r8, 2
0x180010789  add     rcx, 2
0x18001078d  dec     rax
0x180010790  sub     r9, 1
0x180010794  jnz     short loc_180010774
0x180010796  mov     rax, r9
0x180010799  lea     rdx, [rcx-2]
0x18001079d  neg     rax
0x1800107a0  sbb     eax, eax
0x1800107a2  not     eax
0x1800107a4  and     eax, 8007007Ah
0x1800107a9  test    r9, r9
0x1800107ac  cmovnz  rdx, rcx
0x1800107b0  mov     [rdx], r10w
0x1800107b4  retn
```
