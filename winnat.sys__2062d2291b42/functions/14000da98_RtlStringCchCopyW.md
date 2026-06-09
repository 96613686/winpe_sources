# RtlStringCchCopyW

- ea: `0x14000da98`
- end: `0x14000dae7`
- name: `RtlStringCchCopyW`
- size: `79`
- prototype: `NTSTATUS __stdcall(NTSTRSAFE_PWSTR pszDest, size_t cchDest, NTSTRSAFE_PCWSTR pszSrc)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x14000d4b4`
- `0x14002f780`
- `0x1400311f4`

## callees

- `0x14000da98`

## pseudocode

```c
NTSTATUS __stdcall RtlStringCchCopyW(NTSTRSAFE_PWSTR pszDest, size_t cchDest, NTSTRSAFE_PCWSTR pszSrc)
{
  __int64 v3; // rax
  __int64 v4; // r9
  NTSTRSAFE_PWSTR v5; // rdx
  NTSTATUS result; // eax

  v3 = 2147483646;
  v4 = 40;
  do
  {
    if ( !v3 )
      break;
    if ( !*pszSrc )
      break;
    *pszDest++ = *pszSrc++;
    --v3;
    --v4;
  }
  while ( v4 );
  v5 = pszDest - 1;
  result = v4 == 0 ? 0x80000005 : 0;
  if ( v4 )
    v5 = pszDest;
  *v5 = 0;
  return result;
}

```

## disassembly

```asm
0x14000da98  mov     eax, 7FFFFFFEh
0x14000da9d  mov     r9d, 28h ; '('
0x14000daa3  xor     r10d, r10d
0x14000daa6  test    rax, rax
0x14000daa9  jz      short loc_14000DAC8
0x14000daab  movzx   edx, word ptr [r8]
0x14000daaf  test    dx, dx
0x14000dab2  jz      short loc_14000DAC8
0x14000dab4  mov     [rcx], dx
0x14000dab7  add     r8, 2
0x14000dabb  add     rcx, 2
0x14000dabf  dec     rax
0x14000dac2  sub     r9, 1
0x14000dac6  jnz     short loc_14000DAA6
0x14000dac8  mov     rax, r9
0x14000dacb  lea     rdx, [rcx-2]
0x14000dacf  neg     rax
0x14000dad2  sbb     eax, eax
0x14000dad4  not     eax
0x14000dad6  and     eax, 80000005h
0x14000dadb  test    r9, r9
0x14000dade  cmovnz  rdx, rcx
0x14000dae2  mov     [rdx], r10w
0x14000dae6  retn
```
