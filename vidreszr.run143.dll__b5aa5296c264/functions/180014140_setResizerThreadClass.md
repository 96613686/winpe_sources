# setResizerThreadClass

- ea: `0x180014140`
- end: `0x1800141a2`
- name: `setResizerThreadClass`
- size: `98`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x180007e90`
- `0x180008440`

## callees

- `0x180014140`

## pseudocode

```c
__int64 __fastcall setResizerThreadClass(__int64 a1, __int64 a2, _WORD *a3, int a4)
{
  _WORD *v4; // r10
  __int64 v5; // r9
  __int64 v6; // rax
  _WORD *v7; // rdx
  __int64 result; // rax

  if ( !a1 )
    return 1;
  *(_DWORD *)(a1 + 720) = a4;
  v4 = (_WORD *)(a1 + 208);
  v5 = 256;
  v6 = 2147483646;
  do
  {
    if ( !v6 )
      break;
    if ( !*a3 )
      break;
    *v4++ = *a3++;
    --v6;
    --v5;
  }
  while ( v5 );
  v7 = v4 - 1;
  result = 2147942522LL;
  if ( v5 )
  {
    v7 = v4;
    result = 0;
  }
  *v7 = 0;
  return result;
}

```

## disassembly

```asm
0x180014140  test    rcx, rcx
0x180014143  jz      short loc_18001419C
0x180014145  mov     [rcx+2D0h], r9d
0x18001414c  lea     r10, [rcx+0D0h]
0x180014153  mov     r9d, 100h
0x180014159  mov     eax, 7FFFFFFEh
0x18001415e  xchg    ax, ax
0x180014160  test    rax, rax
0x180014163  jz      short loc_180014183
0x180014165  movzx   ecx, word ptr [r8]
0x180014169  test    cx, cx
0x18001416c  jz      short loc_180014183
0x18001416e  mov     [r10], cx
0x180014172  add     r8, 2
0x180014176  add     r10, 2
0x18001417a  dec     rax
0x18001417d  sub     r9, 1
0x180014181  jnz     short loc_180014160
0x180014183  xor     ecx, ecx
0x180014185  lea     rdx, [r10-2]
0x180014189  test    r9, r9
0x18001418c  mov     eax, 8007007Ah
0x180014191  cmovnz  rdx, r10
0x180014195  cmovnz  eax, ecx
0x180014198  mov     [rdx], cx
0x18001419b  retn
0x18001419c  mov     eax, 1
0x1800141a1  retn
```
