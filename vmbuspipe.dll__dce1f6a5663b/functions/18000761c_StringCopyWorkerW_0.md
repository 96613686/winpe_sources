# StringCopyWorkerW_0

- ea: `0x18000761c`
- end: `0x18000768d`
- name: `StringCopyWorkerW_0`
- size: `113`
- prototype: `static HRESULT __stdcall(STRSAFE_LPWSTR pszDest, size_t cchDest, size_t *pcchNewDestLength, STRSAFE_PCNZWCH pszSrc, size_t cchToCopy)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x1800012b0`
- `0x180007578`

## callees

- `0x18000761c`

## pseudocode

```c
HRESULT __stdcall StringCopyWorkerW_0(
        STRSAFE_LPWSTR pszDest,
        size_t cchDest,
        size_t *pcchNewDestLength,
        STRSAFE_PCNZWCH pszSrc,
        size_t cchToCopy)
{
  size_t v8; // rdx
  size_t v9; // r8
  STRSAFE_LPWSTR v10; // rdx
  HRESULT result; // eax

  v8 = 0;
  do
  {
    if ( !cchToCopy )
      break;
    if ( !*pszSrc )
      break;
    *pszDest++ = *pszSrc++;
    --cchToCopy;
    ++v8;
    --cchDest;
  }
  while ( cchDest );
  v9 = v8 - 1;
  if ( cchDest )
    v9 = v8;
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
0x18000761c  mov     [rsp+arg_0], rbx
0x180007621  mov     rax, [rsp+arg_20]
0x180007626  xor     ebx, ebx
0x180007628  mov     r10, rdx
0x18000762b  mov     r11, r8
0x18000762e  mov     edx, ebx
0x180007630  test    rax, rax
0x180007633  jz      short loc_180007657
0x180007635  movzx   r8d, word ptr [r9]
0x180007639  test    r8w, r8w
0x18000763d  jz      short loc_180007657
0x18000763f  mov     [rcx], r8w
0x180007643  add     r9, 2
0x180007647  add     rcx, 2
0x18000764b  dec     rax
0x18000764e  inc     rdx
0x180007651  sub     r10, 1
0x180007655  jnz     short loc_180007630
0x180007657  test    r10, r10
0x18000765a  lea     r8, [rdx-1]
0x18000765e  mov     rax, r10
0x180007661  cmovnz  r8, rdx
0x180007665  neg     rax
0x180007668  lea     rdx, [rcx-2]
0x18000766c  sbb     eax, eax
0x18000766e  not     eax
0x180007670  and     eax, 8007007Ah
0x180007675  test    r10, r10
0x180007678  cmovnz  rdx, rcx
0x18000767c  mov     [rdx], bx
0x18000767f  test    r11, r11
0x180007682  jz      short loc_180007687
0x180007684  mov     [r11], r8
0x180007687  mov     rbx, [rsp+arg_0]
0x18000768c  retn
```
