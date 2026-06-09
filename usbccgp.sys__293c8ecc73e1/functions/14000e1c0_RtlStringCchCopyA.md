# RtlStringCchCopyA

- ea: `0x14000e1c0`
- end: `0x14000e209`
- name: `RtlStringCchCopyA`
- size: `73`
- prototype: `NTSTATUS __stdcall(NTSTRSAFE_PSTR pszDest, size_t cchDest, NTSTRSAFE_PCSTR pszSrc)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x14002d27c`

## callees

- `0x14000e1c0`

## pseudocode

```c
NTSTATUS __stdcall RtlStringCchCopyA(NTSTRSAFE_PSTR pszDest, size_t cchDest, NTSTRSAFE_PCSTR pszSrc)
{
  __int64 v4; // rax
  __int64 v5; // rdx
  NTSTRSAFE_PSTR v6; // rcx
  NTSTATUS result; // eax

  v4 = 2147483646;
  v5 = 16;
  do
  {
    if ( !v4 )
      break;
    if ( !*pszSrc )
      break;
    *pszDest++ = *pszSrc++;
    --v4;
    --v5;
  }
  while ( v5 );
  v6 = pszDest - 1;
  result = v5 == 0 ? 0x80000005 : 0;
  if ( v5 )
    v6 = pszDest;
  *v6 = 0;
  return result;
}

```

## disassembly

```asm
0x14000e1c0  mov     r9, rcx
0x14000e1c3  mov     eax, 7FFFFFFEh
0x14000e1c8  mov     edx, 10h
0x14000e1cd  test    rax, rax
0x14000e1d0  jz      short loc_14000E1EB
0x14000e1d2  mov     cl, [r8]
0x14000e1d5  test    cl, cl
0x14000e1d7  jz      short loc_14000E1EB
0x14000e1d9  mov     [r9], cl
0x14000e1dc  inc     r8
0x14000e1df  inc     r9
0x14000e1e2  dec     rax
0x14000e1e5  sub     rdx, 1
0x14000e1e9  jnz     short loc_14000E1CD
0x14000e1eb  mov     rax, rdx
0x14000e1ee  lea     rcx, [r9-1]
0x14000e1f2  neg     rax
0x14000e1f5  sbb     eax, eax
0x14000e1f7  not     eax
0x14000e1f9  and     eax, 80000005h
0x14000e1fe  test    rdx, rdx
0x14000e201  cmovnz  rcx, r9
0x14000e205  mov     byte ptr [rcx], 0
0x14000e208  retn
```
