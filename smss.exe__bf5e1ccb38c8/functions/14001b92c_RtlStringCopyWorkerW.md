# RtlStringCopyWorkerW

- ea: `0x14001b92c`
- end: `0x14001b97d`
- name: `RtlStringCopyWorkerW`
- size: `81`
- prototype: `NTSTATUS __stdcall(NTSTRSAFE_PWSTR pszDest, size_t cchDest, size_t *pcchNewDestLength, STRSAFE_PCNZWCH pszSrc, size_t cchToCopy)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x14001b8a4`

## callees

- `0x14001b92c`

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
0x14001b92c  xor     r10d, r10d
0x14001b92f  mov     r8, rdx
0x14001b932  test    rdx, rdx
0x14001b935  jz      short loc_14001B95E
0x14001b937  mov     rax, [rsp+cchToCopy]
0x14001b93c  test    rax, rax
0x14001b93f  jz      short loc_14001B95E
0x14001b941  movzx   edx, word ptr [r9]
0x14001b945  test    dx, dx
0x14001b948  jz      short loc_14001B95E
0x14001b94a  mov     [rcx], dx
0x14001b94d  add     r9, 2
0x14001b951  add     rcx, 2
0x14001b955  dec     rax
0x14001b958  sub     r8, 1
0x14001b95c  jnz     short loc_14001B93C
0x14001b95e  mov     rax, r8
0x14001b961  lea     rdx, [rcx-2]
0x14001b965  neg     rax
0x14001b968  sbb     eax, eax
0x14001b96a  not     eax
0x14001b96c  and     eax, 80000005h
0x14001b971  test    r8, r8
0x14001b974  cmovnz  rdx, rcx
0x14001b978  mov     [rdx], r10w
0x14001b97c  retn
```
