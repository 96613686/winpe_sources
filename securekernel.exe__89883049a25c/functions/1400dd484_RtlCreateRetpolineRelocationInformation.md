# RtlCreateRetpolineRelocationInformation

- ea: `0x1400dd484`
- end: `0x1400dd735`
- name: `RtlCreateRetpolineRelocationInformation`
- size: `689`
- prototype: `__int64 __fastcall(int, int, int, int, __int64, void *, int, void *, int)`
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x14007e240`

## callees

- `0x1400dd484`
- `0x1400ddb30`
- `0x1400de1ac`
- `0x1400de2a4`
- `0x1400f9780`
- `0x1400f9a80`

## pseudocode

```c
__int64 __fastcall RtlCreateRetpolineRelocationInformation(
        unsigned int a1,
        unsigned int a2,
        __int64 a3,
        __int64 a4,
        __int64 a5,
        char *a6,
        unsigned int a7,
        void *a8,
        unsigned int a9)
{
  unsigned __int64 v11; // r10
  size_t v13; // r8
  size_t v14; // rdi
  unsigned int v15; // ecx
  unsigned __int8 v16; // dl
  _DWORD *v17; // rdi
  unsigned __int64 v18; // r8
  _DWORD *v19; // r15
  unsigned __int64 v20; // r9
  _DWORD *v21; // r13
  unsigned __int64 v22; // r10
  __int64 v23; // rax
  int v24; // r12d
  __int64 v25; // rax
  unsigned int v26; // r14d
  __int64 v27; // rax
  unsigned int v28; // ebx
  char *v29; // rsi
  unsigned int v30; // eax
  const void *v31; // r11
  char *v32; // rsi
  char *v33; // rax
  char *v34; // rbx
  unsigned int v36; // [rsp+30h] [rbp-50h] BYREF
  unsigned int v37; // [rsp+34h] [rbp-4Ch] BYREF
  unsigned int v38; // [rsp+38h] [rbp-48h]
  _DWORD *v39; // [rsp+40h] [rbp-40h]
  _DWORD *v40; // [rsp+48h] [rbp-38h]
  _DWORD *v41; // [rsp+50h] [rbp-30h]
  __int64 v42; // [rsp+58h] [rbp-28h] BYREF
  unsigned __int64 v43; // [rsp+60h] [rbp-20h]
  unsigned __int64 v44; // [rsp+68h] [rbp-18h]
  unsigned __int64 v45; // [rsp+70h] [rbp-10h]
  __int64 v47; // [rsp+C8h] [rbp+48h] BYREF

  v11 = (unsigned __int64)a1 >> 12;
  v13 = 4 * (a2 + 3 * v11);
  if ( a7 < v13 )
    return 3221225507LL;
  v14 = 8 * v11;
  if ( a9 < 8 * v11 )
    return 3221225507LL;
  v41 = 0;
  memset_0(a6, 0, v13);
  memset_0(a8, 0, v14);
  v15 = 0;
  v16 = 0;
  v38 = 0;
  v42 = 0;
  LOBYTE(a7) = 0;
  if ( a3 )
  {
    v17 = (_DWORD *)(a3 + 12);
    v18 = a3 + 12 + *(unsigned int *)(a3 + 8);
  }
  else
  {
    v17 = 0;
    v18 = 0;
  }
  v43 = v18;
  if ( a4 )
  {
    v19 = (_DWORD *)(a4 + 12);
    v20 = a4 + 12 + *(unsigned int *)(a4 + 8);
  }
  else
  {
    v19 = 0;
    v20 = 0;
  }
  v44 = v20;
  if ( a5 )
  {
    v21 = (_DWORD *)(a5 + 12);
    v22 = a5 + 12 + *(unsigned int *)(a5 + 8);
  }
  else
  {
    v21 = 0;
    v22 = 0;
  }
  v45 = v22;
  if ( a1 )
  {
    do
    {
      if ( (unsigned __int64)v17 < v18 && *v17 == v15 )
      {
        v23 = (unsigned int)v17[1];
        v39 = v17;
        v17 = (_DWORD *)((char *)v17 + v23);
        v24 = v23 - 8;
      }
      else
      {
        v39 = 0;
        v24 = 0;
      }
      LODWORD(v47) = v24;
      if ( (unsigned __int64)v19 < v20 && *v19 == v15 )
      {
        v25 = (unsigned int)v19[1];
        v40 = v19;
        v19 = (_DWORD *)((char *)v19 + v25);
        v26 = v25 - 8;
      }
      else
      {
        v40 = 0;
        v26 = 0;
      }
      v36 = v26;
      if ( (unsigned __int64)v21 < v22 && *v21 == v15 )
      {
        v27 = (unsigned int)v21[1];
        v41 = v21;
        v21 = (_DWORD *)((char *)v21 + v27);
        v28 = v27 - 8;
      }
      else
      {
        v28 = 0;
      }
      v37 = v28;
      if ( v16 || v24 || v26 || v28 )
      {
        v29 = a6;
        *((_WORD *)a6 + 3) = v16;
        if ( v16 )
        {
          v30 = RtlSizeOfRetpolineRelocationEntry(v16);
          memmove(v29 + 8, v31, v30);
        }
        if ( v24 )
        {
          RtlpCopyRetpolineRelocationBlockEntryArray(v29 + 12, (__int64)&v47);
          LOWORD(v24) = v47;
          v32 = &v29[(unsigned int)v47 + 12];
        }
        else
        {
          v32 = v29 + 12;
        }
        if ( v26 )
        {
          RtlpCopyRetpolineRelocationBlockEntryArray(v32, (__int64)&v36);
          LOWORD(v26) = v36;
          v32 += v36;
        }
        if ( v28 )
        {
          RtlpCopyRetpolineRelocationBlockEntryArray(v32, (__int64)&v37);
          LOWORD(v28) = v37;
          v32 += v37;
        }
        v33 = a6;
        a6 = v32;
        *((_WORD *)v33 + 2) = v28;
        v34 = v33;
        *((_WORD *)v33 + 1) = v26;
        *(_WORD *)v33 = v24;
        RtlpScanRetpolineIndexForEndStraddle(v33, &a7, &v42);
        v15 = v38;
        v18 = v43;
        v20 = v44;
        v22 = v45;
        *((_QWORD *)a8 + ((unsigned __int64)v38 >> 12)) = v34;
        v16 = a7;
      }
      v15 += 4096;
      v38 = v15;
    }
    while ( v15 < a1 );
  }
  return 0;
}

```

## disassembly

```asm
0x1400dd484  mov     [rsp-38h+arg_10], rbx
0x1400dd489  mov     [rsp-38h+arg_0], ecx
0x1400dd48d  push    rbp
0x1400dd48e  push    rsi
0x1400dd48f  push    rdi
0x1400dd490  push    r12
0x1400dd492  push    r13
0x1400dd494  push    r14
0x1400dd496  push    r15
0x1400dd498  mov     rbp, rsp
0x1400dd49b  sub     rsp, 80h
0x1400dd4a2  mov     rsi, r8
0x1400dd4a5  mov     eax, edx
0x1400dd4a7  mov     r10d, ecx
0x1400dd4aa  mov     rbx, r9
0x1400dd4ad  shr     r10, 0Ch
0x1400dd4b1  mov     r14d, ecx
0x1400dd4b4  lea     r8, [r10+r10*2]
0x1400dd4b8  add     r8, rax
0x1400dd4bb  mov     eax, [rbp+arg_30]
0x1400dd4be  shl     r8, 2; Size
0x1400dd4c2  cmp     rax, r8
0x1400dd4c5  jb      loc_1400DD714
0x1400dd4cb  mov     eax, [rbp+arg_40]
0x1400dd4d1  lea     rdi, ds:0[r10*8]
0x1400dd4d9  cmp     rax, rdi
0x1400dd4dc  jb      loc_1400DD714
0x1400dd4e2  mov     rcx, [rbp+arg_28]; void *
0x1400dd4e6  xor     edx, edx; Val
0x1400dd4e8  mov     [rbp+var_30], 0
0x1400dd4f0  call    memset_0
0x1400dd4f5  mov     rcx, [rbp+arg_38]; void *
0x1400dd4f9  mov     r8, rdi; Size
0x1400dd4fc  xor     edx, edx; Val
0x1400dd4fe  call    memset_0
0x1400dd503  xor     ecx, ecx
0x1400dd505  xor     r11d, r11d
0x1400dd508  xor     dl, dl
0x1400dd50a  mov     [rbp+var_48], ecx
0x1400dd50d  mov     [rbp+var_28], r11
0x1400dd511  mov     byte ptr [rbp+arg_30], dl
0x1400dd514  test    rsi, rsi
0x1400dd517  jz      short loc_1400DD526
0x1400dd519  mov     r8d, [rsi+8]
0x1400dd51d  lea     rdi, [rsi+0Ch]
0x1400dd521  add     r8, rdi
0x1400dd524  jmp     short loc_1400DD52B
0x1400dd526  xor     edi, edi
0x1400dd528  xor     r8d, r8d
0x1400dd52b  mov     [rbp+var_20], r8
0x1400dd52f  test    rbx, rbx
0x1400dd532  jz      short loc_1400DD541
0x1400dd534  mov     r9d, [rbx+8]
0x1400dd538  lea     r15, [rbx+0Ch]
0x1400dd53c  add     r9, r15
0x1400dd53f  jmp     short loc_1400DD547
0x1400dd541  xor     r15d, r15d
0x1400dd544  xor     r9d, r9d
0x1400dd547  mov     rax, [rbp+arg_20]
0x1400dd54b  mov     [rbp+var_18], r9
0x1400dd54f  test    rax, rax
0x1400dd552  jz      short loc_1400DD561
0x1400dd554  mov     r10d, [rax+8]
0x1400dd558  lea     r13, [rax+0Ch]
0x1400dd55c  add     r10, r13
0x1400dd55f  jmp     short loc_1400DD567
0x1400dd561  xor     r13d, r13d
0x1400dd564  xor     r10d, r10d
0x1400dd567  mov     [rbp+var_10], r10
0x1400dd56b  test    r14d, r14d
0x1400dd56e  jz      loc_1400DD710
0x1400dd574  cmp     rdi, r8
0x1400dd577  jnb     short loc_1400DD58D
0x1400dd579  cmp     [rdi], ecx
0x1400dd57b  jnz     short loc_1400DD58D
0x1400dd57d  mov     eax, [rdi+4]
0x1400dd580  mov     [rbp+var_40], rdi
0x1400dd584  add     rdi, rax
0x1400dd587  lea     r12d, [rax-8]
0x1400dd58b  jmp     short loc_1400DD598
0x1400dd58d  mov     [rbp+var_40], 0
0x1400dd595  xor     r12d, r12d
0x1400dd598  mov     dword ptr [rbp+arg_8], r12d
0x1400dd59c  cmp     r15, r9
0x1400dd59f  jnb     short loc_1400DD5B7
0x1400dd5a1  cmp     [r15], ecx
0x1400dd5a4  jnz     short loc_1400DD5B7
0x1400dd5a6  mov     eax, [r15+4]
0x1400dd5aa  mov     [rbp+var_38], r15
0x1400dd5ae  add     r15, rax
0x1400dd5b1  lea     r14d, [rax-8]
0x1400dd5b5  jmp     short loc_1400DD5C2
0x1400dd5b7  mov     [rbp+var_38], 0
0x1400dd5bf  xor     r14d, r14d
0x1400dd5c2  mov     dword ptr [rbp+var_50], r14d
0x1400dd5c6  cmp     r13, r10
0x1400dd5c9  jnb     short loc_1400DD5E1
0x1400dd5cb  cmp     [r13+0], ecx
0x1400dd5cf  jnz     short loc_1400DD5E1
0x1400dd5d1  mov     eax, [r13+4]
0x1400dd5d5  mov     [rbp+var_30], r13
0x1400dd5d9  add     r13, rax
0x1400dd5dc  lea     ebx, [rax-8]
0x1400dd5df  jmp     short loc_1400DD5E3
0x1400dd5e1  xor     ebx, ebx
0x1400dd5e3  mov     dword ptr [rbp+var_50+4], ebx
0x1400dd5e6  test    dl, dl
0x1400dd5e8  jnz     short loc_1400DD5FC
0x1400dd5ea  test    r12d, r12d
0x1400dd5ed  jnz     short loc_1400DD5FC
0x1400dd5ef  test    r14d, r14d
0x1400dd5f2  jnz     short loc_1400DD5FC
0x1400dd5f4  test    ebx, ebx
0x1400dd5f6  jz      loc_1400DD6FE
0x1400dd5fc  mov     rsi, [rbp+arg_28]
0x1400dd600  movzx   eax, dl
0x1400dd603  mov     [rsi+6], ax
0x1400dd607  test    dl, dl
0x1400dd609  jz      short loc_1400DD622
0x1400dd60b  movzx   ecx, dl
0x1400dd60e  call    RtlSizeOfRetpolineRelocationEntry
0x1400dd613  mov     r8d, eax; Size
0x1400dd616  lea     rcx, [rsi+8]; void *
0x1400dd61a  mov     rdx, r11; Src
0x1400dd61d  call    memmove
0x1400dd622  test    r12d, r12d
0x1400dd625  jz      short loc_1400DD656
0x1400dd627  mov     r8, [rbp+var_40]
0x1400dd62b  lea     rcx, [rbp+arg_8]
0x1400dd62f  mov     [rsp+80h+var_60], rcx; __int64
0x1400dd634  add     r8, 8
0x1400dd638  lea     rcx, [rsi+0Ch]; void *
0x1400dd63c  mov     r9d, r12d
0x1400dd63f  mov     edx, 3
0x1400dd644  call    RtlpCopyRetpolineRelocationBlockEntryArray
0x1400dd649  mov     r12d, dword ptr [rbp+arg_8]
0x1400dd64d  add     rsi, 0Ch
0x1400dd651  add     rsi, r12
0x1400dd654  jmp     short loc_1400DD65A
0x1400dd656  add     rsi, 0Ch
0x1400dd65a  test    r14d, r14d
0x1400dd65d  jz      short loc_1400DD687
0x1400dd65f  mov     r8, [rbp+var_38]
0x1400dd663  lea     rax, [rbp+var_50]
0x1400dd667  add     r8, 8
0x1400dd66b  mov     [rsp+80h+var_60], rax; __int64
0x1400dd670  mov     r9d, r14d
0x1400dd673  mov     edx, 4
0x1400dd678  mov     rcx, rsi; void *
0x1400dd67b  call    RtlpCopyRetpolineRelocationBlockEntryArray
0x1400dd680  mov     r14d, dword ptr [rbp+var_50]
0x1400dd684  add     rsi, r14
0x1400dd687  test    ebx, ebx
0x1400dd689  jz      short loc_1400DD6B2
0x1400dd68b  mov     r8, [rbp+var_30]
0x1400dd68f  lea     rax, [rbp+var_50+4]
0x1400dd693  add     r8, 8
0x1400dd697  mov     [rsp+80h+var_60], rax; __int64
0x1400dd69c  mov     r9d, ebx
0x1400dd69f  mov     edx, 5
0x1400dd6a4  mov     rcx, rsi; void *
0x1400dd6a7  call    RtlpCopyRetpolineRelocationBlockEntryArray
0x1400dd6ac  mov     ebx, dword ptr [rbp+var_50+4]
0x1400dd6af  add     rsi, rbx
0x1400dd6b2  mov     rax, [rbp+arg_28]
0x1400dd6b6  lea     r8, [rbp+var_28]
0x1400dd6ba  lea     rdx, [rbp+arg_30]
0x1400dd6be  mov     [rbp+arg_28], rsi
0x1400dd6c2  mov     rcx, rax
0x1400dd6c5  mov     [rax+4], bx
0x1400dd6c9  mov     rbx, rax
0x1400dd6cc  mov     [rax+2], r14w
0x1400dd6d1  mov     [rax], r12w
0x1400dd6d5  call    RtlpScanRetpolineIndexForEndStraddle
0x1400dd6da  mov     ecx, [rbp+var_48]
0x1400dd6dd  mov     rax, [rbp+arg_38]
0x1400dd6e1  mov     edx, ecx
0x1400dd6e3  mov     r11, [rbp+var_28]
0x1400dd6e7  mov     r8, [rbp+var_20]
0x1400dd6eb  mov     r9, [rbp+var_18]
0x1400dd6ef  mov     r10, [rbp+var_10]
0x1400dd6f3  shr     rdx, 0Ch
0x1400dd6f7  mov     [rax+rdx*8], rbx
0x1400dd6fb  mov     dl, byte ptr [rbp+arg_30]
0x1400dd6fe  add     ecx, 1000h
0x1400dd704  mov     [rbp+var_48], ecx
0x1400dd707  cmp     ecx, [rbp+arg_0]
0x1400dd70a  jb      loc_1400DD574
0x1400dd710  xor     eax, eax
0x1400dd712  jmp     short loc_1400DD719
0x1400dd714  mov     eax, 0C0000023h
0x1400dd719  mov     rbx, [rsp+80h+arg_10]
0x1400dd721  add     rsp, 80h
0x1400dd728  pop     r15
0x1400dd72a  pop     r14
0x1400dd72c  pop     r13
0x1400dd72e  pop     r12
0x1400dd730  pop     rdi
0x1400dd731  pop     rsi
0x1400dd732  pop     rbp
0x1400dd733  retn
```
