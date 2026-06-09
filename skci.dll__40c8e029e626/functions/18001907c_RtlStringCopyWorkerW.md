# RtlStringCopyWorkerW

- ea: `0x18001907c`
- end: `0x1800190cd`
- name: `RtlStringCopyWorkerW`
- size: `81`
- prototype: `NTSTATUS __stdcall(NTSTRSAFE_PWSTR pszDest, size_t cchDest, size_t *pcchNewDestLength, STRSAFE_PCNZWCH pszSrc, size_t cchToCopy)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x180018fd4`
- `0x180019300`

## callees

- `0x18001907c`

## pseudocode

```c
NTSTATUS __stdcall RtlStringCopyWorkerW(
        NTSTRSAFE_PWSTR pszDest,
        size_t cchDest,
        size_t *pcchNewDestLength,
        STRSAFE_PCNZWCH pszSrc,
        size_t cchToCopy)
{
  size_t i; // r8
  NTSTRSAFE_PWSTR v7; // rdx
  NTSTATUS result; // eax

  for ( i = cchDest; i; --i )
  {
    if ( !cchToCopy )
      break;
    if ( !*pszSrc )
      break;
    *pszDest++ = *pszSrc++;
    --cchToCopy;
  }
  v7 = pszDest - 1;
  result = i == 0 ? 0x80000005 : 0;
  if ( i )
    v7 = pszDest;
  *v7 = 0;
  return result;
}

```

## disassembly

```asm
0x18001907c  xor     r10d, r10d
0x18001907f  mov     r8, rdx
0x180019082  test    rdx, rdx
0x180019085  jz      short loc_1800190AE
0x180019087  mov     rax, [rsp+cchToCopy]
0x18001908c  test    rax, rax
0x18001908f  jz      short loc_1800190AE
0x180019091  movzx   edx, word ptr [r9]
0x180019095  test    dx, dx
0x180019098  jz      short loc_1800190AE
0x18001909a  mov     [rcx], dx
0x18001909d  add     r9, 2
0x1800190a1  add     rcx, 2
0x1800190a5  dec     rax
0x1800190a8  sub     r8, 1
0x1800190ac  jnz     short loc_18001908C
0x1800190ae  mov     rax, r8
0x1800190b1  lea     rdx, [rcx-2]
0x1800190b5  neg     rax
0x1800190b8  sbb     eax, eax
0x1800190ba  not     eax
0x1800190bc  and     eax, 80000005h
0x1800190c1  test    r8, r8
0x1800190c4  cmovnz  rdx, rcx
0x1800190c8  mov     [rdx], r10w
0x1800190cc  retn
```
