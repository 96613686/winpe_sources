# VMX_RAW_CONFIG::WriteBlocks(ulong,ulong,VMX_CHANGE_IDENTITY_TRANSACTION *,VMX_CONFIG_COPY *,uchar,uchar)

- ea: `0x14005a574`
- end: `0x14005ab09`
- name: `?WriteBlocks@VMX_RAW_CONFIG@@AEAAJKKPEAVVMX_CHANGE_IDENTITY_TRANSACTION@@PEAVVMX_CONFIG_COPY@@EE@Z`
- size: `1429`
- prototype: `__int64 __fastcall(VMX_RAW_CONFIG *this, unsigned int, int, struct VMX_CHANGE_IDENTITY_TRANSACTION *, struct VMX_CONFIG_COPY *, unsigned __int8, unsigned __int8)`
- caller_count: `2`
- callee_count: `7`
- tags: `registry_config`

## callers

- `0x1400591f0`
- `0x14005a4c8`

## callees

- `0x1400099d8`
- `0x14001a554`
- `0x14001be80`
- `0x140047d60`
- `0x140058fac`
- `0x140059114`
- `0x14005a574`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x14005aa9a`
- `ntoskrnl!ExFreePoolWithTag` at `0x14005aa9a`

## pseudocode

```c
__int64 __fastcall VMX_RAW_CONFIG::WriteBlocks(
        VMX_RAW_CONFIG *this,
        unsigned int a2,
        int a3,
        struct VMX_CHANGE_IDENTITY_TRANSACTION *a4,
        struct VMX_CONFIG_COPY *a5,
        unsigned __int8 a6,
        unsigned __int8 a7)
{
  __int64 v8; // rsi
  unsigned __int8 *v11; // r14
  unsigned int v12; // ecx
  unsigned int v13; // r12d
  unsigned int v14; // ebp
  unsigned __int8 *v15; // rbx
  unsigned int v16; // ecx
  unsigned int v17; // r15d
  __int64 v18; // rax
  __int64 *v19; // r14
  __int64 v20; // r15
  int v21; // eax
  __int16 v22; // r9
  unsigned int v23; // eax
  unsigned int v24; // esi
  unsigned __int8 *v25; // r14
  unsigned __int64 v26; // r15
  __int64 v27; // rax
  __int64 v28; // rbx
  unsigned int v29; // edx
  int v30; // eax
  __int64 v31; // rcx
  int v32; // eax
  int v33; // esi
  _QWORD *v34; // rax
  _QWORD *v35; // rbx
  unsigned __int8 *v36; // r14
  unsigned __int64 v37; // r15
  __int16 v38; // r8
  _QWORD *v39; // rdx
  __int64 v40; // rax
  __int64 v41; // rsi
  unsigned int v42; // edx
  int v43; // eax
  __int64 *v44; // r14
  __int64 v45; // rbx
  void *v46; // rcx
  struct VMX_CONFIG *v48; // [rsp+20h] [rbp-78h]
  unsigned __int8 *v49; // [rsp+30h] [rbp-68h] BYREF
  unsigned __int8 *v50; // [rsp+38h] [rbp-60h]
  unsigned __int64 v51; // [rsp+40h] [rbp-58h]
  __int64 v52; // [rsp+48h] [rbp-50h]
  int v53; // [rsp+A0h] [rbp+8h]
  char v54; // [rsp+A8h] [rbp+10h]
  unsigned int v55; // [rsp+B0h] [rbp+18h]
  unsigned int v56; // [rsp+B8h] [rbp+20h]

  v8 = a2;
  v11 = (unsigned __int8 *)*((_QWORD *)Global + 32);
  v50 = v11;
  memset(v11, 0, 0x8000u);
  v12 = *((_DWORD *)this + 20);
  v13 = v8 + a3;
  v53 = *((_DWORD *)this + 19);
  v14 = a3 * v12;
  v51 = v8 * v12;
  if ( (_DWORD)v8 )
  {
    v15 = v11;
    v54 = 0;
  }
  else
  {
    v49 = v11;
    VMX_RAW_CONFIG::FormatHeader(this, &v49);
    v12 = *((_DWORD *)this + 20);
    v15 = &v11[*((unsigned int *)this + 21)];
    v54 = 1;
    LODWORD(v8) = *((_DWORD *)this + 21) / v12;
  }
  v16 = v12 - 16;
  v56 = v16;
  v17 = v8;
  v55 = v8;
  v18 = *((_QWORD *)this + 17);
  v52 = 3LL * (unsigned int)v8;
  v19 = (__int64 *)(v18 + 24LL * (unsigned int)v8);
  if ( (unsigned int)v8 < v13 )
  {
    while ( (unsigned int)v8 < *((_DWORD *)this + 33) )
    {
      *(_DWORD *)v15 = *(_DWORD *)"VBLK";
      v15[4] = BYTE3(v8);
      v15[5] = BYTE2(v8);
      v15[6] = BYTE1(v8);
      v15[7] = v8;
      v20 = *v19;
      if ( *v19 )
      {
        v21 = *((_DWORD *)v19 + 3);
        if ( v21 )
          v22 = (v21 + 8) / v16;
        else
          v22 = 0;
        v23 = (v16 + *(_DWORD *)(v20 + 28) + 7) / v16;
        v15[8] = *(_BYTE *)(v20 + 19);
        v15[9] = *(_BYTE *)(v20 + 18);
        v15[10] = *(_BYTE *)(v20 + 17);
        v15[11] = *(_BYTE *)(v20 + 16);
        v15[12] = HIBYTE(v22);
        v15[13] = v22;
        v15[14] = BYTE1(v23);
        v49 = v15 + 16;
        v15[15] = v23;
        if ( !v22 )
          v49 = VmxpFormatTable((const struct VMX_FIELD *)qword_140020300, 3u, (char *)v20, v15 + 16);
        VMX_RAW_RECORD::FormatRecordFragment(
          (VMX_RAW_RECORD *)v20,
          &v49,
          *((_DWORD *)v19 + 4),
          *((_DWORD *)v19 + 3),
          v48);
        v16 = v56;
      }
      LODWORD(v8) = v8 + 1;
      v15 += *((unsigned int *)this + 20);
      v19 += 3;
      if ( (unsigned int)v8 >= v13 )
        goto LABEL_16;
    }
    do
    {
      *(_DWORD *)v15 = *(_DWORD *)"VBLK";
      v15[4] = BYTE3(v8);
      v15[5] = BYTE2(v8);
      v15[6] = BYTE1(v8);
      v15[7] = v8;
      LODWORD(v8) = v8 + 1;
      v15 += *((unsigned int *)this + 20);
    }
    while ( (unsigned int)v8 < v13 );
LABEL_16:
    v17 = v55;
  }
  if ( a4 )
  {
    v24 = 0;
    if ( *((_DWORD *)a4 + 40) )
    {
      v25 = v50;
      v26 = v51;
      do
      {
        v27 = *(_QWORD *)(*((_QWORD *)a4 + 21) + 48LL * v24 + 32);
        v28 = *(_QWORD *)(v27 + 104);
        if ( v28 && *(_BYTE *)(v28 + 19) )
        {
          v29 = v13 == v53
              ? *(_DWORD *)(*(_QWORD *)(v27 + 16) + 36LL)
              - (*(_DWORD *)(*(_QWORD *)(v27 + 16) + 36LL) + v14 - 1) % *(_DWORD *)(*(_QWORD *)(v27 + 16) + 36LL)
              + v14
              - 1
              : v14;
          v30 = VMX_CONFIG_COPY::WriteSectors(
                  (VMX_CONFIG_COPY *)v28,
                  v26 / *(unsigned int *)(*(_QWORD *)(*(_QWORD *)v28 + 16LL) + 36LL),
                  v29 / *(_DWORD *)(*(_QWORD *)(*(_QWORD *)v28 + 16LL) + 36LL),
                  v25);
          if ( v54 )
          {
            if ( v30 >= 0 )
            {
              *(_BYTE *)(v28 + 16) = 1;
              *(_WORD *)(v28 + 20) = *((_WORD *)this + 36);
              *(_QWORD *)(v28 + 24) = *((_QWORD *)this + 7);
              *(_QWORD *)(v28 + 32) = *((_QWORD *)this + 8);
              if ( *((_WORD *)this + 36) == 6 )
                *(_BYTE *)(v28 + 18) = 1;
            }
          }
        }
        ++v24;
      }
      while ( v24 < *((_DWORD *)a4 + 40) );
LABEL_63:
      v17 = v55;
    }
    goto LABEL_64;
  }
  if ( !a5 )
  {
    v34 = (_QWORD *)(*(_QWORD *)this + 16LL);
    v35 = (_QWORD *)*v34;
    if ( (_QWORD *)*v34 == v34 )
    {
LABEL_64:
      v33 = 0;
      goto LABEL_65;
    }
    v36 = v50;
    v37 = v51;
    while ( 1 )
    {
      if ( *((_WORD *)v35 + 16) == 4 )
      {
        v38 = *((_WORD *)v35 + 32);
        if ( (v38 & 8) == 0 && (a6 || (v38 & 4) != 0 || (*(_DWORD *)(v35[5] + 96LL) & 0x20) != 0) )
        {
          if ( a7 )
          {
            v39 = v35 + 5;
LABEL_50:
            if ( (v38 & 1) != 0 )
              v39 = v35 + 6;
            v40 = *(_QWORD *)(*v39 + 128LL);
            if ( v40 )
            {
              v41 = *(_QWORD *)(v40 + 104);
              if ( v41 )
              {
                if ( *(_BYTE *)(v41 + 19) )
                {
                  v42 = v13 == v53
                      ? *(_DWORD *)(*(_QWORD *)(v40 + 16) + 36LL)
                      - (*(_DWORD *)(*(_QWORD *)(v40 + 16) + 36LL) + v14 - 1)
                      % *(_DWORD *)(*(_QWORD *)(v40 + 16) + 36LL)
                      + v14
                      - 1
                      : v14;
                  v43 = VMX_CONFIG_COPY::WriteSectors(
                          (VMX_CONFIG_COPY *)v41,
                          v37 / *(unsigned int *)(*(_QWORD *)(*(_QWORD *)v41 + 16LL) + 36LL),
                          v42 / *(_DWORD *)(*(_QWORD *)(*(_QWORD *)v41 + 16LL) + 36LL),
                          v36);
                  if ( v54 )
                  {
                    if ( v43 >= 0 )
                    {
                      *(_BYTE *)(v41 + 16) = 1;
                      *(_WORD *)(v41 + 20) = *((_WORD *)this + 36);
                      *(_QWORD *)(v41 + 24) = *((_QWORD *)this + 7);
                      *(_QWORD *)(v41 + 32) = *((_QWORD *)this + 8);
                      if ( *((_WORD *)this + 36) == 6 )
                        *(_BYTE *)(v41 + 18) = 1;
                    }
                  }
                }
              }
            }
            goto LABEL_62;
          }
          if ( (v38 & 4) == 0 )
          {
            v39 = v35 + 5;
            if ( (*(_DWORD *)(v35[5] + 96LL) & 0x20) == 0 )
              goto LABEL_50;
          }
        }
      }
LABEL_62:
      v35 = (_QWORD *)*v35;
      if ( v35 == (_QWORD *)(*(_QWORD *)this + 16LL) )
        goto LABEL_63;
    }
  }
  v31 = *(_QWORD *)(*(_QWORD *)a5 + 16LL);
  if ( v13 == v53 )
    v14 = *(_DWORD *)(v31 + 36) + v14 - 1 - (*(_DWORD *)(v31 + 36) + v14 - 1) % *(_DWORD *)(v31 + 36);
  v32 = VMX_CONFIG_COPY::WriteSectors(a5, v51 / *(unsigned int *)(v31 + 36), v14 / *(_DWORD *)(v31 + 36), v50);
  v33 = v32;
  if ( v54 )
  {
    if ( v32 >= 0 )
    {
      *((_BYTE *)a5 + 16) = 1;
      *((_WORD *)a5 + 10) = *((_WORD *)this + 36);
      *((_QWORD *)a5 + 3) = *((_QWORD *)this + 7);
      *((_QWORD *)a5 + 4) = *((_QWORD *)this + 8);
      if ( *((_WORD *)this + 36) == 6 )
        *((_BYTE *)a5 + 18) = 1;
    }
  }
LABEL_65:
  v44 = (__int64 *)(*((_QWORD *)this + 17) + 8 * v52);
  while ( v17 < v13 && v17 < *((_DWORD *)this + 33) )
  {
    v45 = *v44;
    if ( *v44 )
    {
      v46 = *(void **)(v45 + 48);
      if ( v46 )
      {
        ExFreePoolWithTag(v46, 0);
        *(_QWORD *)(v45 + 48) = 0;
      }
    }
    ++v17;
    v44 += 3;
  }
  if ( v33 < 0
    && WPP_GLOBAL_Control != (VMX_NOTIFICATION_QUEUE *)&WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x40) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 41) >= 2u )
  {
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 3),
      68,
      WPP_36c7d132267136af2220cbe73d2245a2_Traceguids,
      (unsigned int)v33);
  }
  return (unsigned int)v33;
}

```

## disassembly

```asm
0x14005a574  push    rbx
0x14005a576  push    rbp
0x14005a577  push    rsi
0x14005a578  push    rdi
0x14005a579  push    r12
0x14005a57b  push    r13
0x14005a57d  push    r14
0x14005a57f  push    r15
0x14005a581  sub     rsp, 58h
0x14005a585  mov     rax, cs:?Global@@3PEAVVMX_GLOBAL_DATA@@EA; VMX_GLOBAL_DATA * Global
0x14005a58c  mov     ebx, r8d
0x14005a58f  mov     esi, edx
0x14005a591  mov     rdi, rcx
0x14005a594  xor     edx, edx; Val
0x14005a596  mov     r8d, 8000h; Size
0x14005a59c  mov     r13, r9
0x14005a59f  mov     r14, [rax+100h]
0x14005a5a6  mov     rcx, r14; void *
0x14005a5a9  mov     [rsp+98h+var_60], r14
0x14005a5ae  call    memset
0x14005a5b3  mov     ecx, [rdi+50h]
0x14005a5b6  lea     r12d, [rsi+rbx]
0x14005a5ba  mov     eax, [rdi+4Ch]
0x14005a5bd  mov     edx, ecx
0x14005a5bf  imul    rdx, rsi
0x14005a5c3  mov     ebp, ecx
0x14005a5c5  mov     [rsp+98h+arg_0], eax
0x14005a5cc  imul    ebp, ebx
0x14005a5cf  xor     r10d, r10d
0x14005a5d2  mov     [rsp+98h+var_58], rdx
0x14005a5d7  test    esi, esi
0x14005a5d9  jnz     short loc_14005A60B
0x14005a5db  lea     rdx, [rsp+98h+var_68]; unsigned __int8 **
0x14005a5e0  mov     [rsp+98h+var_68], r14
0x14005a5e5  mov     rcx, rdi; this
0x14005a5e8  call    ?FormatHeader@VMX_RAW_CONFIG@@AEAAXPEAPEAE@Z; VMX_RAW_CONFIG::FormatHeader(uchar * *)
0x14005a5ed  mov     ebx, [rdi+54h]
0x14005a5f0  xor     edx, edx
0x14005a5f2  mov     ecx, [rdi+50h]
0x14005a5f5  mov     eax, ebx
0x14005a5f7  div     ecx
0x14005a5f9  add     rbx, r14
0x14005a5fc  mov     [rsp+98h+arg_8], 1
0x14005a604  mov     esi, eax
0x14005a606  xor     r10d, r10d
0x14005a609  jmp     short loc_14005A616
0x14005a60b  mov     rbx, r14
0x14005a60e  mov     [rsp+98h+arg_8], r10b
0x14005a616  mov     eax, esi
0x14005a618  add     ecx, 0FFFFFFF0h
0x14005a61b  mov     [rsp+98h+arg_18], ecx
0x14005a622  mov     r15d, esi
0x14005a625  mov     [rsp+98h+arg_10], esi
0x14005a62c  lea     rdx, [rax+rax*2]
0x14005a630  mov     rax, [rdi+88h]
0x14005a637  mov     [rsp+98h+var_50], rdx
0x14005a63c  lea     r14, [rax+rdx*8]
0x14005a640  cmp     esi, r12d
0x14005a643  jnb     loc_14005A77D
0x14005a649  cmp     esi, [rdi+84h]
0x14005a64f  jnb     loc_14005A744
0x14005a655  mov     eax, dword ptr cs:aVblk; "VBLK"
0x14005a65b  mov     [rbx], eax
0x14005a65d  mov     eax, esi
0x14005a65f  shr     eax, 18h
0x14005a662  mov     [rbx+4], al
0x14005a665  mov     eax, esi
0x14005a667  shr     eax, 10h
0x14005a66a  mov     [rbx+5], al
0x14005a66d  mov     eax, esi
0x14005a66f  shr     eax, 8
0x14005a672  mov     [rbx+6], al
0x14005a675  mov     [rbx+7], sil
0x14005a679  mov     r15, [r14]
0x14005a67c  test    r15, r15
0x14005a67f  jz      loc_14005A72D
0x14005a685  mov     eax, [r14+0Ch]
0x14005a689  test    eax, eax
0x14005a68b  jnz     short loc_14005A692
0x14005a68d  mov     r9d, r10d
0x14005a690  jmp     short loc_14005A69D
0x14005a692  add     eax, 8
0x14005a695  xor     edx, edx
0x14005a697  div     ecx
0x14005a699  movzx   r9d, ax
0x14005a69d  mov     eax, [r15+1Ch]
0x14005a6a1  xor     edx, edx
0x14005a6a3  add     eax, 7
0x14005a6a6  add     eax, ecx
0x14005a6a8  div     ecx
0x14005a6aa  mov     cl, [r15+13h]
0x14005a6ae  mov     [rbx+8], cl
0x14005a6b1  mov     r8d, eax
0x14005a6b4  mov     cl, [r15+12h]
0x14005a6b8  mov     [rbx+9], cl
0x14005a6bb  mov     cl, [r15+11h]
0x14005a6bf  mov     [rbx+0Ah], cl
0x14005a6c2  mov     cl, [r15+10h]
0x14005a6c6  mov     [rbx+0Bh], cl
0x14005a6c9  movzx   ecx, r9w
0x14005a6cd  shr     ax, 8
0x14005a6d1  shr     cx, 8
0x14005a6d5  mov     [rbx+0Ch], cl
0x14005a6d8  mov     [rbx+0Dh], r9b
0x14005a6dc  mov     [rbx+0Eh], al
0x14005a6df  lea     rax, [rbx+10h]
0x14005a6e3  mov     [rsp+98h+var_68], rax
0x14005a6e8  mov     [rbx+0Fh], r8b
0x14005a6ec  test    r9w, r9w
0x14005a6f0  jnz     short loc_14005A70E
0x14005a6f2  mov     r9, rax; unsigned __int8 *
0x14005a6f5  lea     rcx, qword_140020300; struct VMX_FIELD *
0x14005a6fc  mov     r8, r15; void *
0x14005a6ff  mov     edx, 3; unsigned int
0x14005a704  call    ?VmxpFormatTable@@YAPEAEPEBVVMX_FIELD@@KPEAXPEAE@Z; VmxpFormatTable(VMX_FIELD const *,ulong,void *,uchar *)
0x14005a709  mov     [rsp+98h+var_68], rax
0x14005a70e  mov     r9d, [r14+0Ch]; unsigned int
0x14005a712  lea     rdx, [rsp+98h+var_68]; unsigned __int8 **
0x14005a717  mov     r8d, [r14+10h]; unsigned int
0x14005a71b  mov     rcx, r15; this
0x14005a71e  call    ?FormatRecordFragment@VMX_RAW_RECORD@@QEAAXPEAPEAEKKPEAVVMX_CONFIG@@@Z; VMX_RAW_RECORD::FormatRecordFragment(uchar * *,ulong,ulong,VMX_CONFIG *)
0x14005a723  mov     ecx, [rsp+98h+arg_18]
0x14005a72a  xor     r10d, r10d
0x14005a72d  mov     eax, [rdi+50h]
0x14005a730  inc     esi
0x14005a732  add     rbx, rax
0x14005a735  add     r14, 18h
0x14005a739  cmp     esi, r12d
0x14005a73c  jb      loc_14005A649
0x14005a742  jmp     short loc_14005A775
0x14005a744  mov     eax, dword ptr cs:aVblk; "VBLK"
0x14005a74a  mov     [rbx], eax
0x14005a74c  mov     eax, esi
0x14005a74e  shr     eax, 18h
0x14005a751  mov     [rbx+4], al
0x14005a754  mov     eax, esi
0x14005a756  shr     eax, 10h
0x14005a759  mov     [rbx+5], al
0x14005a75c  mov     eax, esi
0x14005a75e  shr     eax, 8
0x14005a761  mov     [rbx+6], al
0x14005a764  mov     [rbx+7], sil
0x14005a768  inc     esi
0x14005a76a  mov     eax, [rdi+50h]
0x14005a76d  add     rbx, rax
0x14005a770  cmp     esi, r12d
0x14005a773  jb      short loc_14005A744
0x14005a775  mov     r15d, [rsp+98h+arg_10]
0x14005a77d  test    r13, r13
0x14005a780  jz      loc_14005A868
0x14005a786  mov     esi, r10d
0x14005a789  cmp     [r13+0A0h], r10d
0x14005a790  jbe     loc_14005AA69
0x14005a796  mov     r14, [rsp+98h+var_60]
0x14005a79b  mov     r15, [rsp+98h+var_58]
0x14005a7a0  mov     eax, esi
0x14005a7a2  lea     rcx, [rax+rax*2]
0x14005a7a6  mov     rax, [r13+0A8h]
0x14005a7ad  add     rcx, rcx
0x14005a7b0  mov     rax, [rax+rcx*8+20h]
0x14005a7b5  mov     rbx, [rax+68h]
0x14005a7b9  test    rbx, rbx
0x14005a7bc  jz      loc_14005A854
0x14005a7c2  cmp     [rbx+13h], r10b
0x14005a7c6  jz      loc_14005A854
0x14005a7cc  cmp     r12d, [rsp+98h+arg_0]
0x14005a7d4  jz      short loc_14005A7DA
0x14005a7d6  mov     edx, ebp
0x14005a7d8  jmp     short loc_14005A7F1
0x14005a7da  mov     rax, [rax+10h]
0x14005a7de  xor     edx, edx
0x14005a7e0  mov     ecx, [rax+24h]
0x14005a7e3  lea     eax, [rbp-1]
0x14005a7e6  add     eax, ecx
0x14005a7e8  div     ecx
0x14005a7ea  sub     ecx, edx
0x14005a7ec  lea     edx, [rbp-1]
0x14005a7ef  add     edx, ecx
0x14005a7f1  mov     rax, [rbx]
0x14005a7f4  mov     rcx, [rax+10h]
0x14005a7f8  mov     eax, edx
0x14005a7fa  xor     edx, edx
0x14005a7fc  mov     r9d, [rcx+24h]
0x14005a800  mov     rcx, rbx; this
0x14005a803  div     r9
0x14005a806  xor     edx, edx
0x14005a808  mov     r8, rax; unsigned int
0x14005a80b  mov     rax, r15
0x14005a80e  div     r9
0x14005a811  mov     r9, r14; unsigned __int8 *
0x14005a814  mov     rdx, rax; unsigned __int64
0x14005a817  call    ?WriteSectors@VMX_CONFIG_COPY@@QEAAJ_KKPEAE@Z; VMX_CONFIG_COPY::WriteSectors(unsigned __int64,ulong,uchar *)
0x14005a81c  xor     r10d, r10d
0x14005a81f  cmp     [rsp+98h+arg_8], r10b
0x14005a827  jz      short loc_14005A854
0x14005a829  test    eax, eax
0x14005a82b  js      short loc_14005A854
0x14005a82d  mov     byte ptr [rbx+10h], 1
0x14005a831  movzx   eax, word ptr [rdi+48h]
0x14005a835  mov     [rbx+14h], ax
0x14005a839  mov     rax, [rdi+38h]
0x14005a83d  mov     [rbx+18h], rax
0x14005a841  mov     rax, [rdi+40h]
0x14005a845  mov     [rbx+20h], rax
0x14005a849  cmp     word ptr [rdi+48h], 6
0x14005a84e  jnz     short loc_14005A854
0x14005a850  mov     byte ptr [rbx+12h], 1
0x14005a854  inc     esi
0x14005a856  cmp     esi, [r13+0A0h]
0x14005a85d  jb      loc_14005A7A0
0x14005a863  jmp     loc_14005AA61
0x14005a868  mov     rbx, [rsp+98h+arg_20]
0x14005a870  test    rbx, rbx
0x14005a873  jz      loc_14005A90E
0x14005a879  mov     rax, [rbx]
0x14005a87c  mov     rcx, [rax+10h]
0x14005a880  mov     r8d, [rcx+24h]
0x14005a884  cmp     r12d, [rsp+98h+arg_0]
0x14005a88c  jnz     short loc_14005A89C
0x14005a88e  dec     ebp
0x14005a890  xor     edx, edx
0x14005a892  add     ebp, r8d
0x14005a895  mov     eax, ebp
0x14005a897  div     r8d
0x14005a89a  sub     ebp, edx
0x14005a89c  mov     r9, [rsp+98h+var_60]; unsigned __int8 *
0x14005a8a1  xor     edx, edx
0x14005a8a3  mov     eax, ebp
0x14005a8a5  mov     rcx, r8
0x14005a8a8  div     r8
0x14005a8ab  xor     edx, edx
0x14005a8ad  mov     r8, rax; unsigned int
0x14005a8b0  mov     rax, [rsp+98h+var_58]
0x14005a8b5  div     rcx
0x14005a8b8  mov     rcx, rbx; this
0x14005a8bb  mov     rdx, rax; unsigned __int64
0x14005a8be  call    ?WriteSectors@VMX_CONFIG_COPY@@QEAAJ_KKPEAE@Z; VMX_CONFIG_COPY::WriteSectors(unsigned __int64,ulong,uchar *)
0x14005a8c3  xor     r10d, r10d
0x14005a8c6  mov     esi, eax
0x14005a8c8  cmp     [rsp+98h+arg_8], r10b
0x14005a8d0  jz      loc_14005AA6C
0x14005a8d6  test    eax, eax
0x14005a8d8  js      loc_14005AA6C
0x14005a8de  mov     byte ptr [rbx+10h], 1
0x14005a8e2  movzx   ecx, word ptr [rdi+48h]
0x14005a8e6  mov     [rbx+14h], cx
0x14005a8ea  mov     rcx, [rdi+38h]
0x14005a8ee  mov     [rbx+18h], rcx
0x14005a8f2  mov     rcx, [rdi+40h]
0x14005a8f6  mov     [rbx+20h], rcx
0x14005a8fa  cmp     word ptr [rdi+48h], 6
0x14005a8ff  jnz     loc_14005AA6C
0x14005a905  mov     byte ptr [rbx+12h], 1
0x14005a909  jmp     loc_14005AA6C
0x14005a90e  mov     rax, [rdi]
0x14005a911  add     rax, 10h
0x14005a915  mov     rbx, [rax]
0x14005a918  cmp     rbx, rax
0x14005a91b  jz      loc_14005AA69
0x14005a921  mov     r14, [rsp+98h+var_60]
0x14005a926  mov     r15, [rsp+98h+var_58]
0x14005a92b  cmp     word ptr [rbx+20h], 4
0x14005a930  jnz     loc_14005AA4E
0x14005a936  movzx   r8d, word ptr [rbx+40h]
0x14005a93b  test    r8b, 8
0x14005a93f  jnz     loc_14005AA4E
0x14005a945  cmp     [rsp+98h+arg_28], r10b
0x14005a94d  jnz     short loc_14005A965
0x14005a94f  test    r8b, 4
0x14005a953  jnz     short loc_14005A965
0x14005a955  mov     rax, [rbx+28h]
0x14005a959  mov     ecx, [rax+60h]
0x14005a95c  test    cl, 20h
0x14005a95f  jz      loc_14005AA4E
0x14005a965  cmp     [rsp+98h+arg_30], r10b
0x14005a96d  jnz     short loc_14005A98E
0x14005a96f  test    r8b, 4
0x14005a973  jnz     loc_14005AA4E
0x14005a979  lea     rdx, [rbx+28h]
0x14005a97d  mov     rax, [rdx]
0x14005a980  mov     ecx, [rax+60h]
0x14005a983  test    cl, 20h
0x14005a986  jnz     loc_14005AA4E
0x14005a98c  jmp     short loc_14005A992
0x14005a98e  lea     rdx, [rbx+28h]
0x14005a992  test    r8b, 1
0x14005a996  jz      short loc_14005A99C
0x14005a998  lea     rdx, [rbx+30h]
0x14005a99c  mov     rax, [rdx]
0x14005a99f  mov     rax, [rax+80h]
0x14005a9a6  test    rax, rax
0x14005a9a9  jz      loc_14005AA4E
0x14005a9af  mov     rsi, [rax+68h]
0x14005a9b3  test    rsi, rsi
0x14005a9b6  jz      loc_14005AA4E
0x14005a9bc  cmp     [rsi+13h], r10b
0x14005a9c0  jz      loc_14005AA4E
0x14005a9c6  cmp     r12d, [rsp+98h+arg_0]
0x14005a9ce  jz      short loc_14005A9D4
0x14005a9d0  mov     edx, ebp
  ... truncated ...
```
