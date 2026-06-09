# StringCopyWorkerW

- ea: `0x18000aa18`
- end: `0x18000aa69`
- name: `StringCopyWorkerW`
- size: `81`
- prototype: `static HRESULT __stdcall(STRSAFE_LPWSTR pszDest, size_t cchDest, size_t *pcchNewDestLength, STRSAFE_PCNZWCH pszSrc, size_t cchToCopy)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x18000a948`
- `0x18000a9d4`

## callees

- `0x18000aa18`

## pseudocode

```c
HRESULT __stdcall StringCopyWorkerW(
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
0x18000aa18  xor     r10d, r10d
0x18000aa1b  mov     r8, rdx
0x18000aa1e  mov     eax, 7FFFFFFEh
0x18000aa23  test    rdx, rdx
0x18000aa26  jz      short loc_18000AA4A
0x18000aa28  test    rax, rax
0x18000aa2b  jz      short loc_18000AA4A
0x18000aa2d  movzx   edx, word ptr [r9]
0x18000aa31  test    dx, dx
0x18000aa34  jz      short loc_18000AA4A
0x18000aa36  mov     [rcx], dx
0x18000aa39  add     r9, 2
0x18000aa3d  add     rcx, 2
0x18000aa41  dec     rax
0x18000aa44  sub     r8, 1
0x18000aa48  jnz     short loc_18000AA28
0x18000aa4a  mov     rax, r8
0x18000aa4d  lea     rdx, [rcx-2]
0x18000aa51  neg     rax
0x18000aa54  sbb     eax, eax
0x18000aa56  not     eax
0x18000aa58  and     eax, 8007007Ah
0x18000aa5d  test    r8, r8
0x18000aa60  cmovnz  rdx, rcx
0x18000aa64  mov     [rdx], r10w
0x18000aa68  retn
```
