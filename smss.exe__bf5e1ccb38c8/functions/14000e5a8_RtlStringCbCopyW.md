# RtlStringCbCopyW

- ea: `0x14000e5a8`
- end: `0x14000e614`
- name: `RtlStringCbCopyW`
- size: `108`
- prototype: `NTSTATUS __stdcall(NTSTRSAFE_PWSTR pszDest, size_t cbDest, NTSTRSAFE_PCWSTR pszSrc)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x1400101ec`
- `0x1400127a8`

## callees

- `0x14000e5a8`

## pseudocode

```c
NTSTATUS __stdcall RtlStringCbCopyW(NTSTRSAFE_PWSTR pszDest, size_t cbDest, NTSTRSAFE_PCWSTR pszSrc)
{
  size_t v3; // rdx
  NTSTATUS result; // eax
  __int64 v5; // rax
  NTSTRSAFE_PWSTR v6; // rax

  v3 = cbDest >> 1;
  if ( !v3 )
    return -1073741811;
  if ( v3 <= 0x7FFFFFFF )
  {
    v5 = 2147483646;
    do
    {
      if ( !v5 )
        break;
      if ( !*pszSrc )
        break;
      *pszDest++ = *pszSrc++;
      --v5;
      --v3;
    }
    while ( v3 );
    v6 = pszDest - 1;
    if ( v3 )
      v6 = pszDest;
    *v6 = 0;
    return v3 == 0 ? 0x80000005 : 0;
  }
  else
  {
    result = -1073741811;
    *pszDest = 0;
  }
  return result;
}

```

## disassembly

```asm
0x14000e5a8  xor     r9d, r9d
0x14000e5ab  shr     rdx, 1
0x14000e5ae  jz      short loc_14000E605
0x14000e5b0  cmp     rdx, 7FFFFFFFh
0x14000e5b7  jbe     short loc_14000E5C0
0x14000e5b9  mov     eax, 0C000000Dh
0x14000e5be  jmp     short loc_14000E60F
0x14000e5c0  mov     eax, 7FFFFFFEh
0x14000e5c5  test    rax, rax
0x14000e5c8  jz      short loc_14000E5E9
0x14000e5ca  movzx   r10d, word ptr [r8]
0x14000e5ce  test    r10w, r10w
0x14000e5d2  jz      short loc_14000E5E9
0x14000e5d4  mov     [rcx], r10w
0x14000e5d8  add     r8, 2
0x14000e5dc  add     rcx, 2
0x14000e5e0  dec     rax
0x14000e5e3  sub     rdx, 1
0x14000e5e7  jnz     short loc_14000E5C5
0x14000e5e9  test    rdx, rdx
0x14000e5ec  lea     rax, [rcx-2]
0x14000e5f0  cmovnz  rax, rcx
0x14000e5f4  neg     rdx
0x14000e5f7  mov     [rax], r9w
0x14000e5fb  sbb     eax, eax
0x14000e5fd  not     eax
0x14000e5ff  and     eax, 80000005h
0x14000e604  retn
0x14000e605  mov     eax, 0C000000Dh
0x14000e60a  test    rdx, rdx
0x14000e60d  jz      short locret_14000E613
0x14000e60f  mov     [rcx], r9w
0x14000e613  retn
```
