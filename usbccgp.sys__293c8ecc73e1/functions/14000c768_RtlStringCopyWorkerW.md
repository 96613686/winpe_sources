# RtlStringCopyWorkerW

- ea: `0x14000c768`
- end: `0x14000c7e1`
- name: `RtlStringCopyWorkerW`
- size: `121`
- prototype: `NTSTATUS __stdcall(NTSTRSAFE_PWSTR pszDest, size_t cchDest, size_t *pcchNewDestLength, STRSAFE_PCNZWCH pszSrc, size_t cchToCopy)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x1400249d4`

## callees

- `0x14000c768`

## pseudocode

```c
NTSTATUS __stdcall RtlStringCopyWorkerW(
        NTSTRSAFE_PWSTR pszDest,
        size_t cchDest,
        size_t *pcchNewDestLength,
        STRSAFE_PCNZWCH pszSrc,
        size_t cchToCopy)
{
  __int64 v7; // rax
  size_t i; // rdx
  size_t v9; // r8
  NTSTRSAFE_PWSTR v10; // rdx
  NTSTATUS result; // eax

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
  result = cchDest == 0 ? 0x80000005 : 0;
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
0x14000c768  mov     [rsp+arg_0], rbx
0x14000c76d  mov     r10, rdx
0x14000c770  xor     ebx, ebx
0x14000c772  mov     r11, r8
0x14000c775  mov     eax, 7FFFFFFEh
0x14000c77a  mov     edx, ebx
0x14000c77c  test    r10, r10
0x14000c77f  jz      short loc_14000C7A8
0x14000c781  test    rax, rax
0x14000c784  jz      short loc_14000C7A8
0x14000c786  movzx   r8d, word ptr [r9]
0x14000c78a  test    r8w, r8w
0x14000c78e  jz      short loc_14000C7A8
0x14000c790  mov     [rcx], r8w
0x14000c794  add     r9, 2
0x14000c798  add     rcx, 2
0x14000c79c  dec     rax
0x14000c79f  inc     rdx
0x14000c7a2  sub     r10, 1
0x14000c7a6  jnz     short loc_14000C781
0x14000c7a8  test    r10, r10
0x14000c7ab  lea     r8, [rdx-1]
0x14000c7af  mov     rax, r10
0x14000c7b2  cmovnz  r8, rdx
0x14000c7b6  neg     rax
0x14000c7b9  lea     rdx, [rcx-2]
0x14000c7bd  sbb     eax, eax
0x14000c7bf  not     eax
0x14000c7c1  and     eax, 80000005h
0x14000c7c6  test    r10, r10
0x14000c7c9  cmovnz  rdx, rcx
0x14000c7cd  mov     [rdx], bx
0x14000c7d0  test    r11, r11
0x14000c7d3  jnz     short loc_14000C7DC
0x14000c7d5  mov     rbx, [rsp+arg_0]
0x14000c7da  retn
0x14000c7dc  mov     [r11], r8
0x14000c7df  jmp     short loc_14000C7D5
```
