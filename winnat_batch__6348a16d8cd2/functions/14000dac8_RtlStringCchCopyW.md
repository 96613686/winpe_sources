# RtlStringCchCopyW

- ea: `0x14000dac8`
- end: `0x14000db17`
- name: `RtlStringCchCopyW`
- size: `79`
- prototype: `NTSTATUS __stdcall(NTSTRSAFE_PWSTR pszDest, size_t cchDest, NTSTRSAFE_PCWSTR pszSrc)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x14000d4e4`
- `0x14002e780`
- `0x1400300c4`

## callees

- `0x14000dac8`

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
0x14000dac8  mov     eax, 7FFFFFFEh
0x14000dacd  mov     r9d, 28h ; '('
0x14000dad3  xor     r10d, r10d
0x14000dad6  test    rax, rax
0x14000dad9  jz      short loc_14000DAF8
0x14000dadb  movzx   edx, word ptr [r8]
0x14000dadf  test    dx, dx
0x14000dae2  jz      short loc_14000DAF8
0x14000dae4  mov     [rcx], dx
0x14000dae7  add     r8, 2
0x14000daeb  add     rcx, 2
0x14000daef  dec     rax
0x14000daf2  sub     r9, 1
0x14000daf6  jnz     short loc_14000DAD6
0x14000daf8  mov     rax, r9
0x14000dafb  lea     rdx, [rcx-2]
0x14000daff  neg     rax
0x14000db02  sbb     eax, eax
0x14000db04  not     eax
0x14000db06  and     eax, 80000005h
0x14000db0b  test    r9, r9
0x14000db0e  cmovnz  rdx, rcx
0x14000db12  mov     [rdx], r10w
0x14000db16  retn
```
