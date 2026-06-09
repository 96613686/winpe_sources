# RtlStringCopyWorkerW

- ea: `0x180005940`
- end: `0x18000598d`
- name: `RtlStringCopyWorkerW`
- size: `77`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180005630`

## callees

- `0x180005940`

## pseudocode

```c
__int64 __fastcall RtlStringCopyWorkerW(_WORD *a1, __int64 a2, __int64 a3, _WORD *a4)
{
  __int64 v4; // r10
  __int64 i; // rax
  _WORD *v7; // rdx
  __int64 result; // rax

  v4 = a2;
  for ( i = 2147483646; v4; --v4 )
  {
    if ( !i )
      break;
    if ( !*a4 )
      break;
    *a1++ = *a4++;
    --i;
  }
  v7 = a1 - 1;
  result = 2147483653LL;
  if ( v4 )
  {
    v7 = a1;
    result = 0;
  }
  *v7 = 0;
  return result;
}

```

## disassembly

```asm
0x180005940  mov     r10, rdx
0x180005943  mov     r11, rcx
0x180005946  mov     eax, 7FFFFFFEh
0x18000594b  test    rdx, rdx
0x18000594e  jz      short loc_180005974
0x180005950  test    rax, rax
0x180005953  jz      short loc_180005974
0x180005955  movzx   r8d, word ptr [r9]
0x180005959  test    r8w, r8w
0x18000595d  jz      short loc_180005974
0x18000595f  mov     [r11], r8w
0x180005963  add     r9, 2
0x180005967  add     r11, 2
0x18000596b  dec     rax
0x18000596e  sub     r10, 1
0x180005972  jnz     short loc_180005950
0x180005974  xor     ecx, ecx
0x180005976  lea     rdx, [r11-2]
0x18000597a  test    r10, r10
0x18000597d  mov     eax, 80000005h
0x180005982  cmovnz  rdx, r11
0x180005986  cmovnz  eax, ecx
0x180005989  mov     [rdx], cx
0x18000598c  retn
```
