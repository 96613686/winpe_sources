# RtlStringCchCopyW

- ea: `0x14000b5d8`
- end: `0x14000b644`
- name: `RtlStringCchCopyW`
- size: `108`
- prototype: `NTSTATUS __stdcall(NTSTRSAFE_PWSTR pszDest, size_t cchDest, NTSTRSAFE_PCWSTR pszSrc)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x140025f38`

## callees

- `0x14000b5d8`

## pseudocode

```c
NTSTATUS __stdcall RtlStringCchCopyW(NTSTRSAFE_PWSTR pszDest, size_t cchDest, NTSTRSAFE_PCWSTR pszSrc)
{
  NTSTRSAFE_PWSTR v3; // r9
  __int64 v4; // rax
  NTSTATUS result; // eax

  v3 = pszDest;
  if ( !cchDest )
    return -1073741811;
  if ( cchDest > 0x7FFFFFFF )
  {
    result = -1073741811;
  }
  else
  {
    v4 = 2147483646;
    do
    {
      if ( !v4 )
        break;
      if ( !*pszSrc )
        break;
      *v3++ = *pszSrc++;
      --v4;
      --cchDest;
    }
    while ( cchDest );
    pszDest = v3 - 1;
    if ( cchDest )
      pszDest = v3;
    result = cchDest == 0 ? 0x80000005 : 0;
  }
  *pszDest = 0;
  return result;
}

```

## disassembly

```asm
0x14000b5d8  xor     r10d, r10d
0x14000b5db  mov     r9, rcx
0x14000b5de  test    rdx, rdx
0x14000b5e1  jz      short loc_14000B638
0x14000b5e3  cmp     rdx, 7FFFFFFFh
0x14000b5ea  ja      short loc_14000B631
0x14000b5ec  mov     eax, 7FFFFFFEh
0x14000b5f1  test    rax, rax
0x14000b5f4  jz      short loc_14000B614
0x14000b5f6  movzx   ecx, word ptr [r8]
0x14000b5fa  test    cx, cx
0x14000b5fd  jz      short loc_14000B614
0x14000b5ff  mov     [r9], cx
0x14000b603  add     r8, 2
0x14000b607  add     r9, 2
0x14000b60b  dec     rax
0x14000b60e  sub     rdx, 1
0x14000b612  jnz     short loc_14000B5F1
0x14000b614  test    rdx, rdx
0x14000b617  lea     rcx, [r9-2]
0x14000b61b  cmovnz  rcx, r9
0x14000b61f  neg     rdx
0x14000b622  sbb     eax, eax
0x14000b624  not     eax
0x14000b626  and     eax, 80000005h
0x14000b62b  mov     [rcx], r10w
0x14000b62f  retn
0x14000b631  mov     eax, 0C000000Dh
0x14000b636  jmp     short loc_14000B62B
0x14000b638  mov     eax, 0C000000Dh
0x14000b63d  test    rdx, rdx
0x14000b640  jz      short locret_14000B62F
0x14000b642  jmp     short loc_14000B62B
```
