# ComputeFlushPeriod

- ea: `0x18000d4a0`
- end: `0x18000d6ec`
- name: `ComputeFlushPeriod`
- size: `588`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x18000d32c`

## pseudocode

```c
__int64 __fastcall ComputeFlushPeriod(unsigned __int64 a1)
{
  __int64 v1; // r10
  unsigned int v2; // eax
  unsigned int v3; // eax
  unsigned int v4; // eax
  unsigned int v5; // eax
  unsigned int v6; // eax
  unsigned int v7; // eax
  unsigned int v8; // eax
  unsigned int v9; // eax
  unsigned int v10; // eax
  unsigned int v11; // eax
  unsigned int v12; // eax
  unsigned int v13; // eax
  unsigned int v14; // eax
  unsigned int v15; // eax
  unsigned int v16; // eax
  unsigned int v17; // eax
  unsigned int v18; // eax
  unsigned int v19; // eax

  v1 = *(_QWORD *)(*(_QWORD *)(a1 + 328) + 8LL);
  v2 = 1025
     * (*(unsigned __int8 *)(v1 - 13)
      + ((1025
        * (*(unsigned __int8 *)(v1 - 14)
         + ((1025
           * (*(unsigned __int8 *)(v1 - 15)
            + ((1025 * *(unsigned __int8 *)(v1 - 16)) ^ ((1025 * (unsigned int)*(unsigned __int8 *)(v1 - 16)) >> 6))))
          ^ ((1025
            * (*(unsigned __int8 *)(v1 - 15)
             + ((1025 * *(unsigned __int8 *)(v1 - 16)) ^ ((1025 * (unsigned int)*(unsigned __int8 *)(v1 - 16)) >> 6)))) >> 6))))
       ^ ((1025
         * (*(unsigned __int8 *)(v1 - 14)
          + ((1025
            * (*(unsigned __int8 *)(v1 - 15)
             + ((1025 * *(unsigned __int8 *)(v1 - 16)) ^ ((1025 * (unsigned int)*(unsigned __int8 *)(v1 - 16)) >> 6))))
           ^ ((1025
             * (*(unsigned __int8 *)(v1 - 15)
              + ((1025 * *(unsigned __int8 *)(v1 - 16)) ^ ((1025 * (unsigned int)*(unsigned __int8 *)(v1 - 16)) >> 6)))) >> 6)))) >> 6)));
  v3 = 1025 * (*(unsigned __int8 *)(v1 - 12) + (v2 ^ (v2 >> 6)));
  v4 = 1025 * (*(unsigned __int8 *)(v1 - 11) + (v3 ^ (v3 >> 6)));
  v5 = 1025 * (*(unsigned __int8 *)(v1 - 10) + (v4 ^ (v4 >> 6)));
  v6 = 1025 * (*(unsigned __int8 *)(v1 - 9) + (v5 ^ (v5 >> 6)));
  v7 = 1025 * (*(unsigned __int8 *)(v1 - 8) + (v6 ^ (v6 >> 6)));
  v8 = 1025 * (*(unsigned __int8 *)(v1 - 7) + (v7 ^ (v7 >> 6)));
  v9 = 1025 * (*(unsigned __int8 *)(v1 - 6) + (v8 ^ (v8 >> 6)));
  v10 = 1025 * (*(unsigned __int8 *)(v1 - 5) + (v9 ^ (v9 >> 6)));
  v11 = 1025 * (*(unsigned __int8 *)(v1 - 4) + (v10 ^ (v10 >> 6)));
  v12 = 1025 * (*(unsigned __int8 *)(v1 - 3) + (v11 ^ (v11 >> 6)));
  v13 = 1025 * (*(unsigned __int8 *)(v1 - 2) + (v12 ^ (v12 >> 6)));
  v14 = 1025 * (*(unsigned __int8 *)(v1 - 1) + (v13 ^ (v13 >> 6)));
  v15 = 1025 * ((unsigned __int8)(a1 >> 4) + (v14 ^ (v14 >> 6)));
  v16 = 1025
      * ((unsigned __int8)(a1 >> 20)
       + ((1025 * ((unsigned __int8)(a1 >> 12) + (v15 ^ (v15 >> 6))))
        ^ ((1025 * ((unsigned __int8)(a1 >> 12) + (v15 ^ (v15 >> 6)))) >> 6)));
  v17 = 1025
      * ((unsigned __int8)(a1 >> 36)
       + ((1025 * ((unsigned __int8)(a1 >> 28) + (v16 ^ (v16 >> 6))))
        ^ ((1025 * ((unsigned __int8)(a1 >> 28) + (v16 ^ (v16 >> 6)))) >> 6)));
  v18 = 1025
      * ((unsigned __int8)(a1 >> 52)
       + ((1025 * ((unsigned __int8)(a1 >> 44) + (v17 ^ (v17 >> 6))))
        ^ ((1025 * ((unsigned __int8)(a1 >> 44) + (v17 ^ (v17 >> 6)))) >> 6)));
  v19 = 9 * ((1025 * ((a1 >> 60) + (v18 ^ (v18 >> 6)))) ^ ((1025 * ((a1 >> 60) + (v18 ^ (v18 >> 6)))) >> 6));
  return 32769 * (v19 ^ (v19 >> 11)) % 0x927C0 + 600000;
}

```

## disassembly

```asm
0x18000d4a0  push    rbx
0x18000d4a2  push    rbp
0x18000d4a3  push    rsi
0x18000d4a4  push    rdi
0x18000d4a5  push    r14
0x18000d4a7  mov     rax, [rcx+148h]
0x18000d4ae  mov     r14, rcx
0x18000d4b1  shr     r14, 4
0x18000d4b5  movzx   r8d, r14b
0x18000d4b9  mov     r10, [rax+8]
0x18000d4bd  mov     rax, r14
0x18000d4c0  shr     rax, 30h
0x18000d4c4  movzx   ebp, al
0x18000d4c7  mov     rax, r14
0x18000d4ca  shr     rax, 28h
0x18000d4ce  movzx   esi, al
0x18000d4d1  mov     rax, r14
0x18000d4d4  shr     rax, 20h
0x18000d4d8  movzx   edi, al
0x18000d4db  mov     rax, r14
0x18000d4de  shr     rax, 18h
0x18000d4e2  movzx   ebx, al
0x18000d4e5  mov     rax, r14
0x18000d4e8  shr     rax, 10h
0x18000d4ec  movzx   r11d, al
0x18000d4f0  mov     rax, r14
0x18000d4f3  shr     rax, 8
0x18000d4f7  movzx   r9d, al
0x18000d4fb  movzx   eax, byte ptr [r10-10h]
0x18000d500  imul    ecx, eax, 401h
0x18000d506  movzx   eax, byte ptr [r10-0Fh]
0x18000d50b  mov     edx, ecx
0x18000d50d  shr     edx, 6
0x18000d510  xor     edx, ecx
0x18000d512  add     edx, eax
0x18000d514  imul    eax, edx, 401h
0x18000d51a  mov     ecx, eax
0x18000d51c  shr     ecx, 6
0x18000d51f  xor     ecx, eax
0x18000d521  movzx   eax, byte ptr [r10-0Eh]
0x18000d526  add     ecx, eax
0x18000d528  imul    eax, ecx, 401h
0x18000d52e  mov     ecx, eax
0x18000d530  shr     ecx, 6
0x18000d533  xor     ecx, eax
0x18000d535  movzx   eax, byte ptr [r10-0Dh]
0x18000d53a  add     ecx, eax
0x18000d53c  imul    eax, ecx, 401h
0x18000d542  mov     ecx, eax
0x18000d544  shr     ecx, 6
0x18000d547  xor     ecx, eax
0x18000d549  movzx   eax, byte ptr [r10-0Ch]
0x18000d54e  add     ecx, eax
0x18000d550  imul    eax, ecx, 401h
0x18000d556  mov     ecx, eax
0x18000d558  shr     ecx, 6
0x18000d55b  xor     ecx, eax
0x18000d55d  movzx   eax, byte ptr [r10-0Bh]
0x18000d562  add     ecx, eax
0x18000d564  imul    eax, ecx, 401h
0x18000d56a  mov     ecx, eax
0x18000d56c  shr     ecx, 6
0x18000d56f  xor     ecx, eax
0x18000d571  movzx   eax, byte ptr [r10-0Ah]
0x18000d576  add     ecx, eax
0x18000d578  imul    eax, ecx, 401h
0x18000d57e  mov     ecx, eax
0x18000d580  shr     ecx, 6
0x18000d583  xor     ecx, eax
0x18000d585  movzx   eax, byte ptr [r10-9]
0x18000d58a  add     ecx, eax
0x18000d58c  imul    eax, ecx, 401h
0x18000d592  mov     ecx, eax
0x18000d594  shr     ecx, 6
0x18000d597  xor     ecx, eax
0x18000d599  movzx   eax, byte ptr [r10-8]
0x18000d59e  add     ecx, eax
0x18000d5a0  imul    eax, ecx, 401h
0x18000d5a6  mov     ecx, eax
0x18000d5a8  shr     ecx, 6
0x18000d5ab  xor     ecx, eax
0x18000d5ad  movzx   eax, byte ptr [r10-7]
0x18000d5b2  add     ecx, eax
0x18000d5b4  imul    eax, ecx, 401h
0x18000d5ba  mov     ecx, eax
0x18000d5bc  shr     ecx, 6
0x18000d5bf  xor     ecx, eax
0x18000d5c1  shr     r14, 38h
0x18000d5c5  movzx   eax, byte ptr [r10-6]
0x18000d5ca  add     ecx, eax
0x18000d5cc  imul    eax, ecx, 401h
0x18000d5d2  mov     ecx, eax
0x18000d5d4  shr     ecx, 6
0x18000d5d7  xor     ecx, eax
0x18000d5d9  movzx   eax, byte ptr [r10-5]
0x18000d5de  add     ecx, eax
0x18000d5e0  imul    eax, ecx, 401h
0x18000d5e6  mov     ecx, eax
0x18000d5e8  shr     ecx, 6
0x18000d5eb  xor     ecx, eax
0x18000d5ed  movzx   eax, byte ptr [r10-4]
0x18000d5f2  add     ecx, eax
0x18000d5f4  imul    eax, ecx, 401h
0x18000d5fa  mov     ecx, eax
0x18000d5fc  shr     ecx, 6
0x18000d5ff  xor     ecx, eax
0x18000d601  movzx   eax, byte ptr [r10-3]
0x18000d606  add     ecx, eax
0x18000d608  imul    eax, ecx, 401h
0x18000d60e  mov     ecx, eax
0x18000d610  shr     ecx, 6
0x18000d613  xor     ecx, eax
0x18000d615  movzx   eax, byte ptr [r10-2]
0x18000d61a  add     ecx, eax
0x18000d61c  imul    eax, ecx, 401h
0x18000d622  mov     ecx, eax
0x18000d624  shr     ecx, 6
0x18000d627  xor     ecx, eax
0x18000d629  movzx   eax, byte ptr [r10-1]
0x18000d62e  add     ecx, eax
0x18000d630  imul    eax, ecx, 401h
0x18000d636  mov     ecx, eax
0x18000d638  shr     ecx, 6
0x18000d63b  xor     ecx, eax
0x18000d63d  add     ecx, r8d
0x18000d640  imul    eax, ecx, 401h
0x18000d646  mov     ecx, eax
0x18000d648  shr     ecx, 6
0x18000d64b  xor     ecx, eax
0x18000d64d  add     ecx, r9d
0x18000d650  imul    eax, ecx, 401h
0x18000d656  mov     ecx, eax
0x18000d658  shr     ecx, 6
0x18000d65b  xor     ecx, eax
0x18000d65d  add     ecx, r11d
0x18000d660  imul    eax, ecx, 401h
0x18000d666  mov     ecx, eax
0x18000d668  shr     ecx, 6
0x18000d66b  xor     ecx, eax
0x18000d66d  add     ecx, ebx
0x18000d66f  imul    eax, ecx, 401h
0x18000d675  mov     ecx, eax
0x18000d677  shr     ecx, 6
0x18000d67a  xor     ecx, eax
0x18000d67c  add     ecx, edi
0x18000d67e  imul    eax, ecx, 401h
0x18000d684  mov     ecx, eax
0x18000d686  shr     ecx, 6
0x18000d689  xor     ecx, eax
0x18000d68b  add     ecx, esi
0x18000d68d  imul    eax, ecx, 401h
0x18000d693  mov     ecx, eax
0x18000d695  shr     ecx, 6
0x18000d698  xor     ecx, eax
0x18000d69a  add     ecx, ebp
0x18000d69c  imul    eax, ecx, 401h
0x18000d6a2  mov     ecx, eax
0x18000d6a4  shr     ecx, 6
0x18000d6a7  xor     ecx, eax
0x18000d6a9  add     ecx, r14d
0x18000d6ac  imul    eax, ecx, 401h
0x18000d6b2  mov     ecx, eax
0x18000d6b4  shr     ecx, 6
0x18000d6b7  xor     ecx, eax
0x18000d6b9  lea     eax, [rcx+rcx*8]
0x18000d6bc  mov     ecx, eax
0x18000d6be  shr     ecx, 0Bh
0x18000d6c1  xor     ecx, eax
0x18000d6c3  mov     eax, 6FD91D85h
0x18000d6c8  imul    r8d, ecx, 8001h
0x18000d6cf  mul     r8d
0x18000d6d2  shr     edx, 12h
0x18000d6d5  imul    ecx, edx, 927C0h
0x18000d6db  sub     r8d, ecx
0x18000d6de  lea     eax, [r8+927C0h]
0x18000d6e5  pop     r14
0x18000d6e7  pop     rdi
0x18000d6e8  pop     rsi
0x18000d6e9  pop     rbp
0x18000d6ea  pop     rbx
0x18000d6eb  retn
```
