# RtlStringCopyWorkerW

- ea: `0x14000402c`
- end: `0x1400040a3`
- name: `RtlStringCopyWorkerW`
- size: `119`
- prototype: `NTSTATUS __stdcall(NTSTRSAFE_PWSTR pszDest, size_t cchDest, size_t *pcchNewDestLength, STRSAFE_PCNZWCH pszSrc, size_t cchToCopy)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x140003e70`
- `0x140003f64`
- `0x1400112f0`

## callees

- `0x14000402c`

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
0x14000402c  mov     [rsp+arg_0], rbx
0x140004031  mov     r10, rdx
0x140004034  xor     ebx, ebx
0x140004036  mov     r11, r8
0x140004039  mov     eax, 7FFFFFFEh
0x14000403e  mov     edx, ebx
0x140004040  test    r10, r10
0x140004043  jz      short loc_14000406C
0x140004045  test    rax, rax
0x140004048  jz      short loc_14000406C
0x14000404a  movzx   r8d, word ptr [r9]
0x14000404e  test    r8w, r8w
0x140004052  jz      short loc_14000406C
0x140004054  mov     [rcx], r8w
0x140004058  add     r9, 2
0x14000405c  add     rcx, 2
0x140004060  dec     rax
0x140004063  inc     rdx
0x140004066  sub     r10, 1
0x14000406a  jnz     short loc_140004045
0x14000406c  test    r10, r10
0x14000406f  lea     r8, [rdx-1]
0x140004073  mov     rax, r10
0x140004076  cmovnz  r8, rdx
0x14000407a  neg     rax
0x14000407d  lea     rdx, [rcx-2]
0x140004081  sbb     eax, eax
0x140004083  not     eax
0x140004085  and     eax, 80000005h
0x14000408a  test    r10, r10
0x14000408d  cmovnz  rdx, rcx
0x140004091  mov     [rdx], bx
0x140004094  test    r11, r11
0x140004097  jz      short loc_14000409C
0x140004099  mov     [r11], r8
0x14000409c  mov     rbx, [rsp+arg_0]
0x1400040a1  retn
```
