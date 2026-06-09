# EXFORMOBJ_flComputeWtoDAccelFlags

- ea: `0x140001650`
- end: `0x1400016a7`
- name: `EXFORMOBJ_flComputeWtoDAccelFlags`
- size: `87`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x140001650`

## pseudocode

```c
__int64 __fastcall EXFORMOBJ_flComputeWtoDAccelFlags(unsigned int *a1)
{
  __int64 result; // rax
  __m128 v2; // rt1

  result = ((*((_QWORD *)a1 + 3) == 0) << 6) | 8u;
  if ( *((float *)a1 + 1) == 0.0 && *((float *)a1 + 2) == 0.0 )
  {
    v2.m128_i32[0] = a1[3];
    return (unsigned int)result
         | (2
          * (_mm_cvtsi128_si32((__m128i)_mm_and_ps(
                                          _mm_cmpeq_ss((__m128)LODWORD(FLOAT_16_0), v2),
                                          _mm_cmpeq_ss((__m128)*a1, (__m128)LODWORD(FLOAT_16_0))))
           & 1))
         | 1;
  }
  return result;
}

```

## disassembly

```asm
0x140001650  mov     edx, [rcx+1Ch]
0x140001653  xor     eax, eax
0x140001655  or      edx, [rcx+18h]
0x140001658  setz    al
0x14000165b  shl     eax, 6
0x14000165e  or      eax, 8
0x140001661  movss   xmm1, dword ptr [rcx+4]
0x140001666  xorps   xmm0, xmm0
0x140001669  ucomiss xmm1, xmm0
0x14000166c  jnz     short locret_1400016A6
0x14000166e  jp      short locret_1400016A6
0x140001670  movss   xmm1, dword ptr [rcx+8]
0x140001675  ucomiss xmm1, xmm0
0x140001678  jnz     short locret_1400016A6
0x14000167a  jp      short locret_1400016A6
0x14000167c  movss   xmm0, cs:__real@41800000
0x140001684  movss   xmm1, dword ptr [rcx]
0x140001688  cmpeqss xmm1, xmm0
0x14000168d  cmpeqss xmm0, dword ptr [rcx+0Ch]
0x140001693  andps   xmm0, xmm1
0x140001696  movd    ecx, xmm0
0x14000169a  and     ecx, 1
0x14000169d  add     ecx, ecx
0x14000169f  or      ecx, eax
0x1400016a1  or      ecx, 1
0x1400016a4  mov     eax, ecx
0x1400016a6  retn
```
