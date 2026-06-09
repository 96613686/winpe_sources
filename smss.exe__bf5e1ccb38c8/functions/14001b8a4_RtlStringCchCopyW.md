# RtlStringCchCopyW

- ea: `0x14001b8a4`
- end: `0x14001b8ea`
- name: `RtlStringCchCopyW`
- size: `70`
- prototype: `NTSTATUS __stdcall(NTSTRSAFE_PWSTR pszDest, size_t cchDest, NTSTRSAFE_PCWSTR pszSrc)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x14001b33c`

## callees

- `0x14001b8a4`
- `0x14001b92c`

## pseudocode

```c
NTSTATUS __stdcall RtlStringCchCopyW(NTSTRSAFE_PWSTR pszDest, size_t cchDest, NTSTRSAFE_PCWSTR pszSrc)
{
  NTSTATUS v3; // edx

  if ( !cchDest )
    return -1073741811;
  if ( cchDest <= 0x7FFFFFFF )
    return RtlStringCopyWorkerW(pszDest, cchDest, (size_t *)pszSrc, pszSrc, 0x7FFFFFFEu);
  v3 = -1073741811;
  *pszDest = 0;
  return v3;
}

```

## disassembly

```asm
0x14001b8a4  sub     rsp, 38h
0x14001b8a8  mov     rax, rdx
0x14001b8ab  test    rdx, rdx
0x14001b8ae  jz      short loc_14001B8D4
0x14001b8b0  cmp     rax, 7FFFFFFFh
0x14001b8b6  jbe     short loc_14001B8BF
0x14001b8b8  mov     edx, 0C000000Dh; cchDest
0x14001b8bd  jmp     short loc_14001B8DE
0x14001b8bf  mov     r9, r8; pszSrc
0x14001b8c2  mov     [rsp+38h+cchToCopy], 7FFFFFFEh; cchToCopy
0x14001b8cb  call    RtlStringCopyWorkerW
0x14001b8d0  mov     edx, eax
0x14001b8d2  jmp     short loc_14001B8E3
0x14001b8d4  mov     edx, 0C000000Dh
0x14001b8d9  test    rax, rax
0x14001b8dc  jz      short loc_14001B8E3
0x14001b8de  xor     eax, eax
0x14001b8e0  mov     [rcx], ax
0x14001b8e3  mov     eax, edx
0x14001b8e5  add     rsp, 38h
0x14001b8e9  retn
```
