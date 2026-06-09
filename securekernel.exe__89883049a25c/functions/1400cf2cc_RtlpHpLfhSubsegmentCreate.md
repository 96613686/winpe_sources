# RtlpHpLfhSubsegmentCreate

- ea: `0x1400cf2cc`
- end: `0x1400cf4ab`
- name: `RtlpHpLfhSubsegmentCreate`
- size: `479`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x14000ffec`

## callees

- `0x1400cdcec`
- `0x1400cf084`
- `0x1400cf2cc`
- `0x1400cfc28`
- `0x1400d0578`
- `0x1400d38dc`

## pseudocode

```c
__int64 __fastcall RtlpHpLfhSubsegmentCreate(__int64 a1, volatile signed __int64 *a2, int a3)
{
  unsigned int v6; // ebp
  unsigned int v7; // eax
  int v8; // ecx
  unsigned int v9; // eax
  unsigned int v10; // edx
  unsigned int v11; // r8d
  unsigned int v12; // edi
  unsigned int v13; // eax
  unsigned int v14; // r9d
  unsigned int v15; // eax
  void *v16; // rsi
  unsigned int v17; // ebp
  __int64 v18; // rcx
  int (__fastcall *v19)(__int64, void *, _QWORD, int *); // rax
  __int64 v20; // rdx
  __int64 v21; // rdi
  __int64 v22; // r8
  signed __int32 v24[8]; // [rsp+0h] [rbp-78h] BYREF
  int v25; // [rsp+80h] [rbp+8h] BYREF
  int v26; // [rsp+88h] [rbp+10h] BYREF
  int v27; // [rsp+98h] [rbp+20h] BYREF

  v27 = 0;
  v25 = 0;
  v6 = (unsigned __int16)RtlpBucketBlockSizes[(*(unsigned __int8 *)a2 >> 1) + 1];
  v7 = RtlpHpLfhBucketComputeNewSubsegmentBlockCount(a2, (unsigned int)a3);
  v8 = (8 * (((unsigned __int64)v7 + 31) >> 5) + 79) & 0xFFFFFFF0;
  v9 = RtlpCalculateSubsegmentSizeIndex(v8 + 2 * ((v8 + v7 * v6 + 4095) >> 12) + v7 * v6);
  if ( v9 <= 0xC )
    LOBYTE(v9) = 12;
  v12 = 1 << v9;
  if ( v10 <= v11 >> 6 )
  {
    v13 = RtlpCalculateSubsegmentSizeIndex(v11);
    if ( v13 <= v14 )
      LOBYTE(v13) = v14;
    v15 = 1 << v13;
    if ( v12 > v15 )
      v12 = v15;
  }
  v16 = (void *)((__int64 (__fastcall *)(_QWORD, _QWORD, int *, int *))(a1 ^ RtlpHpHeapGlobals ^ *(_QWORD *)(a1 + 8)))(
                  *(_QWORD *)a1,
                  v12,
                  &v25,
                  &v27);
  if ( !v16 )
    return 0;
  if ( a3 >= 1 || (v25 & 1) != 0 )
    v17 = v12;
  else
    v17 = RtlpHpLfhSubsegmentComputeCommitUnit(v12, v6);
  v18 = *(_QWORD *)a1;
  v19 = (int (__fastcall *)(__int64, void *, _QWORD, int *))(a1 ^ RtlpHpHeapGlobals ^ *(_QWORD *)(a1 + 24));
  v26 = 0;
  if ( v19(v18, v16, v17, &v26) < 0 )
  {
    ((void (__fastcall *)(_QWORD, void *, _QWORD))(a1 ^ RtlpHpHeapGlobals ^ *(_QWORD *)(a1 + 16)))(
      *(_QWORD *)a1,
      v16,
      v12);
    return 0;
  }
  v21 = RtlpHpLfhSubsegmentInitialize(v16, (__int64)a2, a1, v26 == 0);
  _InterlockedOr(v24, 0);
  _InterlockedAdd64(a2 + 8, 1u);
  _InterlockedAdd64(a2 + 7, *(unsigned __int16 *)(v21 + 34));
  if ( (*(_DWORD *)(*(_QWORD *)(*(_QWORD *)a1 + 56LL) + 20LL) & 0x80u) != 0
    && !*((_QWORD *)&KeGetPcr()->NtTib.ExceptionList[182].Handler + (unsigned int)(*(_DWORD *)(a1 + 76) - 1)) )
  {
    RtlpHpLfhThreadDataInitializeSet(a1, v20, v22);
  }
  return v21;
}

```

## disassembly

```asm
0x1400cf2cc  mov     rax, rsp
0x1400cf2cf  push    rbx
0x1400cf2d0  push    rbp
0x1400cf2d1  push    rsi
0x1400cf2d2  push    rdi
0x1400cf2d3  push    r13
0x1400cf2d5  push    r14
0x1400cf2d7  push    r15
0x1400cf2d9  sub     rsp, 40h
0x1400cf2dd  mov     dword ptr [rax+20h], 0
0x1400cf2e4  mov     rbx, rcx
0x1400cf2e7  mov     dword ptr [rax+8], 0
0x1400cf2ee  lea     rcx, RtlpBucketBlockSizes
0x1400cf2f5  movzx   eax, byte ptr [rdx]
0x1400cf2f8  mov     r14, rdx
0x1400cf2fb  shr     eax, 1
0x1400cf2fd  mov     r13d, 1
0x1400cf303  add     eax, r13d
0x1400cf306  mov     edx, r8d
0x1400cf309  mov     r15d, r8d
0x1400cf30c  movzx   ebp, word ptr [rcx+rax*2]
0x1400cf310  mov     rcx, r14
0x1400cf313  call    RtlpHpLfhBucketComputeNewSubsegmentBlockCount
0x1400cf318  mov     ecx, eax
0x1400cf31a  mov     r8d, ebp
0x1400cf31d  imul    r8d, eax
0x1400cf321  add     rcx, 1Fh
0x1400cf325  shr     rcx, 5
0x1400cf329  lea     ecx, ds:4Fh[rcx*8]
0x1400cf330  and     ecx, 0FFFFFFF0h
0x1400cf333  lea     eax, [r8+0FFFh]
0x1400cf33a  add     eax, ecx
0x1400cf33c  shr     eax, 0Ch
0x1400cf33f  lea     edx, [rcx+rax*2]
0x1400cf342  lea     ecx, [rdx+r8]
0x1400cf346  call    RtlpCalculateSubsegmentSizeIndex
0x1400cf34b  lea     r9d, [r13+0Bh]
0x1400cf34f  mov     edi, r13d
0x1400cf352  cmp     eax, r9d
0x1400cf355  cmovbe  eax, r9d
0x1400cf359  mov     ecx, eax
0x1400cf35b  mov     eax, r8d
0x1400cf35e  shr     eax, 6
0x1400cf361  shl     edi, cl
0x1400cf363  cmp     edx, eax
0x1400cf365  ja      short loc_1400CF382
0x1400cf367  mov     ecx, r8d
0x1400cf36a  call    RtlpCalculateSubsegmentSizeIndex
0x1400cf36f  cmp     eax, r9d
0x1400cf372  cmovbe  eax, r9d
0x1400cf376  mov     ecx, eax
0x1400cf378  mov     eax, r13d
0x1400cf37b  shl     eax, cl
0x1400cf37d  cmp     edi, eax
0x1400cf37f  cmova   edi, eax
0x1400cf382  mov     rax, [rbx+8]
0x1400cf386  lea     r9, [rsp+78h+arg_18]
0x1400cf38e  xor     rax, cs:RtlpHpHeapGlobals
0x1400cf395  lea     r8, [rsp+78h+arg_0]
0x1400cf39d  mov     rcx, [rbx]
0x1400cf3a0  xor     rax, rbx
0x1400cf3a3  mov     edx, edi
0x1400cf3a5  call    rax
0x1400cf3a7  nop     dword ptr [rax]
0x1400cf3aa  mov     rsi, rax
0x1400cf3ad  test    rax, rax
0x1400cf3b0  jz      loc_1400CF496
0x1400cf3b6  cmp     r15d, r13d
0x1400cf3b9  jge     short loc_1400CF3D2
0x1400cf3bb  test    byte ptr [rsp+78h+arg_0], r13b
0x1400cf3c3  jnz     short loc_1400CF3D2
0x1400cf3c5  mov     edx, ebp
0x1400cf3c7  mov     ecx, edi
0x1400cf3c9  call    RtlpHpLfhSubsegmentComputeCommitUnit
0x1400cf3ce  mov     ebp, eax
0x1400cf3d0  jmp     short loc_1400CF3D4
0x1400cf3d2  mov     ebp, edi
0x1400cf3d4  mov     rax, [rbx+18h]
0x1400cf3d8  lea     r9, [rsp+78h+arg_8]
0x1400cf3e0  xor     rax, cs:RtlpHpHeapGlobals
0x1400cf3e7  mov     r8d, ebp
0x1400cf3ea  mov     rcx, [rbx]
0x1400cf3ed  xor     rax, rbx
0x1400cf3f0  mov     rdx, rsi
0x1400cf3f3  mov     [rsp+78h+arg_8], 0
0x1400cf3fe  call    rax
0x1400cf400  nop     dword ptr [rax]
0x1400cf403  test    eax, eax
0x1400cf405  js      short loc_1400CF47A
0x1400cf407  xor     eax, eax
0x1400cf409  mov     r9d, r15d
0x1400cf40c  cmp     [rsp+78h+arg_8], eax
0x1400cf413  mov     r8d, ebp
0x1400cf416  mov     edx, edi
0x1400cf418  mov     rcx, rsi; void *
0x1400cf41b  cmovz   eax, r13d
0x1400cf41f  mov     [rsp+78h+var_48], eax; int
0x1400cf423  mov     [rsp+78h+var_50], rbx; __int64
0x1400cf428  mov     [rsp+78h+var_58], r14; __int64
0x1400cf42d  call    RtlpHpLfhSubsegmentInitialize
0x1400cf432  mov     rdi, rax
0x1400cf435  lock or [rsp+78h+var_78], 0
0x1400cf43a  lock add [r14+40h], r13
0x1400cf43f  movzx   eax, word ptr [rax+22h]
0x1400cf443  lock add [r14+38h], rax
0x1400cf448  mov     rax, [rbx]
0x1400cf44b  mov     rcx, [rax+38h]
0x1400cf44f  mov     eax, [rcx+14h]
0x1400cf452  test    al, al
0x1400cf454  jns     short loc_1400CF498
0x1400cf456  mov     rcx, gs:0
0x1400cf45f  mov     eax, [rbx+4Ch]
0x1400cf462  sub     eax, r13d
0x1400cf465  cmp     qword ptr [rcx+rax*8+0B68h], 0
0x1400cf46e  jnz     short loc_1400CF498
0x1400cf470  mov     rcx, rbx
0x1400cf473  call    RtlpHpLfhThreadDataInitializeSet
0x1400cf478  jmp     short loc_1400CF498
0x1400cf47a  mov     rax, [rbx+10h]
0x1400cf47e  mov     r8d, edi
0x1400cf481  xor     rax, cs:RtlpHpHeapGlobals
0x1400cf488  mov     rdx, rsi
0x1400cf48b  mov     rcx, [rbx]
0x1400cf48e  xor     rax, rbx
0x1400cf491  call    rax
0x1400cf493  nop     dword ptr [rax]
0x1400cf496  xor     edi, edi
0x1400cf498  mov     rax, rdi
0x1400cf49b  add     rsp, 40h
0x1400cf49f  pop     r15
0x1400cf4a1  pop     r14
0x1400cf4a3  pop     r13
0x1400cf4a5  pop     rdi
0x1400cf4a6  pop     rsi
0x1400cf4a7  pop     rbp
0x1400cf4a8  pop     rbx
0x1400cf4a9  retn
```
