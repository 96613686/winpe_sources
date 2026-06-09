# StringCopyWorkerW_0

- ea: `0x18001839c`
- end: `0x180018412`
- name: `StringCopyWorkerW_0`
- size: `118`
- prototype: `static HRESULT __stdcall(STRSAFE_LPWSTR pszDest, size_t cchDest, size_t *pcchNewDestLength, STRSAFE_PCNZWCH pszSrc, size_t cchToCopy)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x18001826c`
- `0x180018418`

## callees

- `0x18001839c`

## pseudocode

```c
HRESULT __stdcall StringCopyWorkerW_0(
        STRSAFE_LPWSTR pszDest,
        size_t cchDest,
        size_t *pcchNewDestLength,
        STRSAFE_PCNZWCH pszSrc,
        size_t cchToCopy)
{
  __int64 v7; // rax
  size_t i; // rdx
  size_t v9; // r8
  STRSAFE_LPWSTR v10; // rdx
  HRESULT result; // eax

  v7 = 2147483646;
  for ( i = 0; cchDest; --cchDest )
  {
    if ( !v7 )
      break;
    if ( !*pszSrc )
      break;
    *pszDest++ = *pszSrc++;
    --v7;
    ++i;
  }
  v9 = i - 1;
  if ( cchDest )
    v9 = i;
  v10 = pszDest - 1;
  result = cchDest == 0 ? 0x8007007A : 0;
  if ( cchDest )
    v10 = pszDest;
  *v10 = 0;
  if ( pcchNewDestLength )
    *pcchNewDestLength = v9;
  return result;
}

```

## disassembly

```asm
0x18001839c  mov     [rsp+arg_0], rbx
0x1800183a1  mov     r10, rdx
0x1800183a4  xor     ebx, ebx
0x1800183a6  mov     r11, r8
0x1800183a9  mov     eax, 7FFFFFFEh
0x1800183ae  mov     edx, ebx
0x1800183b0  test    r10, r10
0x1800183b3  jz      short loc_1800183DC
0x1800183b5  test    rax, rax
0x1800183b8  jz      short loc_1800183DC
0x1800183ba  movzx   r8d, word ptr [r9]
0x1800183be  test    r8w, r8w
0x1800183c2  jz      short loc_1800183DC
0x1800183c4  mov     [rcx], r8w
0x1800183c8  add     r9, 2
0x1800183cc  add     rcx, 2
0x1800183d0  dec     rax
0x1800183d3  inc     rdx
0x1800183d6  sub     r10, 1
0x1800183da  jnz     short loc_1800183B5
0x1800183dc  test    r10, r10
0x1800183df  lea     r8, [rdx-1]
0x1800183e3  mov     rax, r10
0x1800183e6  cmovnz  r8, rdx
0x1800183ea  neg     rax
0x1800183ed  lea     rdx, [rcx-2]
0x1800183f1  sbb     eax, eax
0x1800183f3  not     eax
0x1800183f5  and     eax, 8007007Ah
0x1800183fa  test    r10, r10
0x1800183fd  cmovnz  rdx, rcx
0x180018401  mov     [rdx], bx
0x180018404  test    r11, r11
0x180018407  jz      short loc_18001840C
0x180018409  mov     [r11], r8
0x18001840c  mov     rbx, [rsp+arg_0]
0x180018411  retn
```
