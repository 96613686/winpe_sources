# StringCopyWorkerW_0

- ea: `0x18000c29c`
- end: `0x18000c2ed`
- name: `StringCopyWorkerW_0`
- size: `81`
- prototype: `static HRESULT __stdcall(STRSAFE_LPWSTR pszDest, size_t cchDest, size_t *pcchNewDestLength, STRSAFE_PCNZWCH pszSrc, size_t cchToCopy)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x180002c90`
- `0x18000d12c`

## callees

- `0x18000c29c`

## pseudocode

```c
HRESULT __stdcall StringCopyWorkerW_0(
        STRSAFE_LPWSTR pszDest,
        size_t cchDest,
        size_t *pcchNewDestLength,
        STRSAFE_PCNZWCH pszSrc,
        size_t cchToCopy)
{
  size_t v5; // r8
  __int64 i; // rax
  STRSAFE_LPWSTR v7; // rdx
  HRESULT result; // eax

  v5 = cchDest;
  for ( i = 2147483646; v5; --v5 )
  {
    if ( !i )
      break;
    if ( !*pszSrc )
      break;
    *pszDest++ = *pszSrc++;
    --i;
  }
  v7 = pszDest - 1;
  result = v5 == 0 ? 0x8007007A : 0;
  if ( v5 )
    v7 = pszDest;
  *v7 = 0;
  return result;
}

```

## disassembly

```asm
0x18000c29c  xor     r10d, r10d
0x18000c29f  mov     r8, rdx
0x18000c2a2  mov     eax, 7FFFFFFEh
0x18000c2a7  test    rdx, rdx
0x18000c2aa  jz      short loc_18000C2CE
0x18000c2ac  test    rax, rax
0x18000c2af  jz      short loc_18000C2CE
0x18000c2b1  movzx   edx, word ptr [r9]
0x18000c2b5  test    dx, dx
0x18000c2b8  jz      short loc_18000C2CE
0x18000c2ba  mov     [rcx], dx
0x18000c2bd  add     r9, 2
0x18000c2c1  add     rcx, 2
0x18000c2c5  dec     rax
0x18000c2c8  sub     r8, 1
0x18000c2cc  jnz     short loc_18000C2AC
0x18000c2ce  mov     rax, r8
0x18000c2d1  lea     rdx, [rcx-2]
0x18000c2d5  neg     rax
0x18000c2d8  sbb     eax, eax
0x18000c2da  not     eax
0x18000c2dc  and     eax, 8007007Ah
0x18000c2e1  test    r8, r8
0x18000c2e4  cmovnz  rdx, rcx
0x18000c2e8  mov     [rdx], r10w
0x18000c2ec  retn
```
