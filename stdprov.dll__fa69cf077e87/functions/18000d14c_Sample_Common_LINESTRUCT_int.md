# Sample_Common(_LINESTRUCT *,int)

- ea: `0x18000d14c`
- end: `0x18000d18b`
- name: `?Sample_Common@@YAMPEAU_LINESTRUCT@@H@Z`
- size: `63`
- prototype: `float __fastcall(struct _LINESTRUCT *, int)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x18000cb10`

## callees

- `0x18000d14c`

## pseudocode

```c
float __fastcall Sample_Common(struct _LINESTRUCT *a1, int a2)
{
  float v2; // xmm1_4

  if ( *((_DWORD *)a1 + 8) - *((_DWORD *)a1 + 12) <= 0 || *((_DWORD *)a1 + 10) - *((_DWORD *)a1 + 14) <= 0 )
    return 0.0;
  v2 = (float)(*((_DWORD *)a1 + 8) - *((_DWORD *)a1 + 12)) / (float)(*((_DWORD *)a1 + 10) - *((_DWORD *)a1 + 14));
  if ( a2 == 1 )
    return v2 * 100.0;
  return v2;
}

```

## disassembly

```asm
0x18000d14c  mov     r8d, [rcx+20h]
0x18000d150  sub     r8d, [rcx+30h]
0x18000d154  test    r8d, r8d
0x18000d157  jle     short loc_18000D187
0x18000d159  mov     eax, [rcx+28h]
0x18000d15c  sub     eax, [rcx+38h]
0x18000d15f  test    eax, eax
0x18000d161  jle     short loc_18000D187
0x18000d163  movd    xmm1, r8d
0x18000d168  movd    xmm0, eax
0x18000d16c  cvtdq2ps xmm1, xmm1
0x18000d16f  cvtdq2ps xmm0, xmm0
0x18000d172  divss   xmm1, xmm0
0x18000d176  cmp     edx, 1
0x18000d179  jnz     short loc_18000D183
0x18000d17b  mulss   xmm1, cs:__real@42c80000
0x18000d183  movaps  xmm0, xmm1
0x18000d186  retn
0x18000d187  xorps   xmm0, xmm0
0x18000d18a  retn
```
