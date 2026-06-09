# ReadTTFSpline

- ea: `0x18000a650`
- end: `0x18000aefc`
- name: `ReadTTFSpline`
- size: `2220`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x180004320`

## callees

- `0x180006400`
- `0x180006504`
- `0x180009c80`
- `0x18000a650`
- `0x18000af10`
- `0x18000b160`
- `0x18000bc10`

## import_xrefs

- `msvcrt!longjmp` at `0x18000aa4e`
- `msvcrt!longjmp` at `0x18000aa5e`
- `msvcrt!longjmp` at `0x18000ab36`
- `msvcrt!longjmp` at `0x18000ab46`
- `msvcrt!longjmp` at `0x18000ab74`
- `msvcrt!longjmp` at `0x18000ab8b`
- `msvcrt!longjmp` at `0x18000ab9b`
- `msvcrt!longjmp` at `0x18000abab`
- `msvcrt!longjmp` at `0x18000aa4e`
- `msvcrt!longjmp` at `0x18000aa5e`
- `msvcrt!longjmp` at `0x18000ab36`
- `msvcrt!longjmp` at `0x18000ab46`
- `msvcrt!longjmp` at `0x18000ab74`
- `msvcrt!longjmp` at `0x18000ab8b`
- `msvcrt!longjmp` at `0x18000ab9b`
- `msvcrt!longjmp` at `0x18000abab`

## pseudocode

```c
__int64 __fastcall ReadTTFSpline(__int64 a1, char *a2)
{
  char *v5; // rsi
  __int64 v6; // rdx
  __int64 v7; // rdx
  __int64 v8; // rcx
  __int64 v9; // rdx
  __int64 v10; // rcx
  __int64 v11; // rdx
  __int64 v12; // rcx
  __int64 v13; // rdx
  __int64 v14; // rcx
  __int64 v15; // rdx
  __int64 v16; // rcx
  unsigned int v17; // eax
  __int64 v18; // rax
  __int64 v19; // r8
  __int64 v20; // rax
  __int64 v21; // r8
  __int16 v22; // cx
  __int16 v23; // dx
  __int16 i; // bp
  __int16 v25; // r8
  __int64 v26; // rcx
  char *v27; // rax
  __int64 v28; // r8
  __int64 v29; // rax
  __int16 v30; // cx
  __int16 v31; // di
  _JBTYPE *v32; // rcx
  unsigned __int8 *v33; // rdx
  char v34; // bp
  __int64 v35; // rcx
  __int64 v36; // rax
  __int64 v37; // r8
  __int16 v38; // bp
  __int16 v39; // di
  __int64 v40; // r14
  char v41; // cl
  char v42; // al
  __int16 v43; // cx
  __int16 v44; // r10
  __int16 v45; // r8
  __int64 v46; // r9
  char v47; // dl
  char v48; // al
  unsigned __int64 v49; // rcx
  bool v50; // zf
  unsigned __int8 *v51; // rax
  bool v52; // cc
  _JBTYPE *v53; // rcx
  char *v55; // rax
  char j; // dl
  __int64 v57; // rcx
  char *v58; // rax
  _JBTYPE *v59; // rcx
  __int64 v60; // rax
  unsigned __int16 v61; // r8
  char v62; // al
  __int64 v63; // rdx
  __int64 v64; // rcx
  unsigned __int16 v65; // di
  __int64 v66; // rdx
  __int16 v67; // ax
  char *v68; // rsi
  char *v69; // r14
  __int64 v70; // rdx
  __int64 v71; // rdx
  __int16 v72; // ax
  char *v73; // rax
  __int64 v74; // rdx
  __int16 v75; // ax
  char *v76; // rax
  __int64 v77; // r8
  __int64 v78; // rax
  __int64 v79; // r8
  unsigned __int16 k; // r8
  char v81; // al
  __int64 v82; // rdx
  char *v83; // rax
  __int64 v84; // rdi
  char *v85; // rax
  __int64 v86; // rdx
  __int64 v87; // rdx
  __int64 v88; // rdx

  CheckReadBoundsGlyph(a1, a2, 10);
  v5 = a2 + 10;
  v6 = *(_QWORD *)(a1 + 72);
  *(_WORD *)(a1 + 12) = (unsigned __int8)a2[1] | (unsigned __int16)(*a2 << 8);
  *(_WORD *)(a1 + 2) = (unsigned __int8)a2[3] | (unsigned __int16)(a2[2] << 8);
  *(_WORD *)(a1 + 6) = (unsigned __int8)a2[5] | (unsigned __int16)(a2[4] << 8);
  *(_WORD *)a1 = (unsigned __int8)a2[7] | (unsigned __int16)(a2[6] << 8);
  *(_WORD *)(a1 + 4) = (unsigned __int8)a2[9] | (unsigned __int16)(a2[8] << 8);
  DiscardPointer(*(_QWORD *)(a1 + 136), v6, 1);
  v7 = *(_QWORD *)(a1 + 16);
  v8 = *(_QWORD *)(a1 + 136);
  *(_QWORD *)(a1 + 72) = 0;
  DiscardPointer(v8, v7, 1);
  v9 = *(_QWORD *)(a1 + 24);
  v10 = *(_QWORD *)(a1 + 136);
  *(_QWORD *)(a1 + 16) = 0;
  DiscardPointer(v10, v9, 1);
  v11 = *(_QWORD *)(a1 + 48);
  v12 = *(_QWORD *)(a1 + 136);
  *(_QWORD *)(a1 + 24) = 0;
  DiscardPointer(v12, v11, 1);
  v13 = *(_QWORD *)(a1 + 32);
  v14 = *(_QWORD *)(a1 + 136);
  *(_QWORD *)(a1 + 48) = 0;
  DiscardPointer(v14, v13, 1);
  v15 = *(_QWORD *)(a1 + 40);
  v16 = *(_QWORD *)(a1 + 136);
  *(_QWORD *)(a1 + 32) = 0;
  DiscardPointer(v16, v15, 1);
  v17 = *(__int16 *)(a1 + 12);
  *(_QWORD *)(a1 + 40) = 0;
  *(_WORD *)(a1 + 14) = 0;
  if ( (v17 & 0x8000u) == 0 )
  {
    if ( (__int16)v17 > 0 )
    {
      VerifyGlyphBuffersize(a1, 2, v17);
      v18 = MTX_mem_malloc(*(_QWORD *)(a1 + 136), (unsigned int)(2 * *(__int16 *)(a1 + 12)));
      v19 = (unsigned int)*(__int16 *)(a1 + 12);
      *(_QWORD *)(a1 + 16) = v18;
      VerifyGlyphBuffersize(a1, 2, v19);
      v20 = MTX_mem_malloc(*(_QWORD *)(a1 + 136), (unsigned int)(2 * *(__int16 *)(a1 + 12)));
      v21 = (unsigned int)(2 * *(__int16 *)(a1 + 12));
      *(_QWORD *)(a1 + 24) = v20;
      CheckReadBoundsGlyph(a1, v5, v21);
      v22 = *(_WORD *)(a1 + 12);
      v23 = 0;
      for ( i = 0; i < v22; v23 = *(_WORD *)(v84 + *(_QWORD *)(a1 + 24)) + 1 )
      {
        v84 = 2LL * i;
        *(_WORD *)(v84 + *(_QWORD *)(a1 + 16)) = v23;
        v85 = v5;
        v5 += 2;
        *(_WORD *)(v84 + *(_QWORD *)(a1 + 24)) = (*v85 << 8) | (unsigned __int8)v85[1];
        VerifyConditionInternal(*(_QWORD *)(a1 + 136), 1);
        ++i;
        v22 = *(_WORD *)(a1 + 12);
      }
      v25 = *(_WORD *)(*(_QWORD *)(a1 + 24) + 2LL * v22 - 2);
      v26 = *(_QWORD *)(a1 + 136);
      *(_WORD *)(a1 + 14) = ++v25;
      VerifyConditionInternal(v26, v25 > 0);
      CheckReadBoundsGlyph(a1, v5, 2);
      v27 = v5;
      v5 += 2;
      v28 = (unsigned __int16)((unsigned __int8)v27[1] | (unsigned __int16)(*v27 << 8));
      *(_WORD *)(a1 + 70) = v28;
      CheckReadBoundsGlyph(a1, v5, v28);
      if ( *(_WORD *)(a1 + 70) )
      {
        VerifyGlyphBuffersize(a1, 1, *(unsigned __int16 *)(a1 + 70));
        v60 = MTX_mem_malloc(*(_QWORD *)(a1 + 136), *(unsigned __int16 *)(a1 + 70));
        v61 = 0;
        for ( *(_QWORD *)(a1 + 72) = v60; v61 < *(_WORD *)(a1 + 70); *(_BYTE *)(v63 + *(_QWORD *)(a1 + 72)) = v62 )
        {
          v62 = *v5++;
          v63 = v61++;
        }
      }
      VerifyGlyphBuffersize(a1, 1, (unsigned int)*(__int16 *)(a1 + 14));
      v29 = MTX_mem_malloc(*(_QWORD *)(a1 + 136), (unsigned int)*(__int16 *)(a1 + 14));
      v30 = *(_WORD *)(a1 + 14);
      v31 = 0;
      for ( *(_QWORD *)(a1 + 48) = v29; v31 < v30; v30 = *(_WORD *)(a1 + 14) )
      {
        v32 = *(_JBTYPE **)(a1 + 136);
        v33 = (unsigned __int8 *)(v5 + 1);
        if ( (unsigned __int64)(v5 + 1) > *(_QWORD *)(a1 + 128) )
          longjmp(v32 + 3, 3362);
        if ( (unsigned __int64)v5 < *(_QWORD *)(a1 + 120) )
          longjmp(v32 + 3, 3362);
        v34 = *v5++;
        v35 = v31++;
        *(_BYTE *)(v35 + *(_QWORD *)(a1 + 48)) = v34;
        if ( (v34 & 8) != 0 )
        {
          CheckReadBoundsGlyph(a1, v33, 1);
          for ( j = *v5++; v31 < *(__int16 *)(a1 + 14); *(_BYTE *)(v57 + *(_QWORD *)(a1 + 48)) = v34 )
          {
            if ( !j )
              break;
            --j;
            v57 = v31++;
          }
        }
      }
      VerifyGlyphBuffersize(a1, 2, (unsigned int)v30);
      v36 = MTX_mem_malloc(*(_QWORD *)(a1 + 136), (unsigned int)(2 * *(__int16 *)(a1 + 14)));
      v37 = (unsigned int)*(__int16 *)(a1 + 14);
      *(_QWORD *)(a1 + 32) = v36;
      VerifyGlyphBuffersize(a1, 2, v37);
      v38 = 0;
      *(_QWORD *)(a1 + 40) = MTX_mem_malloc(*(_QWORD *)(a1 + 136), (unsigned int)(2 * *(__int16 *)(a1 + 14)));
      v39 = 0;
      if ( *(__int16 *)(a1 + 14) > 0 )
      {
        do
        {
          v40 = v39;
          v41 = *(_BYTE *)(v39 + *(_QWORD *)(a1 + 48));
          v42 = v41 & 0x10;
          if ( (v41 & 2) != 0 )
          {
            if ( v42 )
            {
              CheckReadBoundsGlyph(a1, v5, 1);
              v38 += (unsigned __int8)*v5;
            }
            else
            {
              CheckReadBoundsGlyph(a1, v5, 1);
              v38 -= (unsigned __int8)*v5;
            }
            ++v5;
          }
          else if ( !v42 )
          {
            CheckReadBoundsGlyph(a1, v5, 2);
            v55 = v5;
            v5 += 2;
            v38 += (unsigned __int8)v55[1] | (unsigned __int16)(*v55 << 8);
          }
          ++v39;
          *(_WORD *)(*(_QWORD *)(a1 + 32) + 2 * v40) = v38;
          v43 = *(_WORD *)(a1 + 14);
        }
        while ( v39 < v43 );
        v44 = 0;
        v45 = 0;
        if ( v43 > 0 )
        {
          do
          {
            v46 = v45;
            v47 = *(_BYTE *)(v45 + *(_QWORD *)(a1 + 48));
            v48 = v47 & 0x20;
            if ( (v47 & 4) != 0 )
            {
              v49 = *(_QWORD *)(a1 + 128);
              v50 = v48 == 0;
              v51 = (unsigned __int8 *)(v5 + 1);
              if ( v50 )
              {
                v52 = (unsigned __int64)v51 <= v49;
                v53 = *(_JBTYPE **)(a1 + 136);
                if ( !v52 )
                  longjmp(v53 + 3, 3362);
                if ( (unsigned __int64)v5 < *(_QWORD *)(a1 + 120) )
                  longjmp(v53 + 3, 3362);
                v44 -= (unsigned __int8)*v5;
              }
              else
              {
                v52 = (unsigned __int64)v51 <= v49;
                v59 = *(_JBTYPE **)(a1 + 136);
                if ( !v52 )
                  longjmp(v59 + 3, 3362);
                if ( (unsigned __int64)v5 < *(_QWORD *)(a1 + 120) )
                  longjmp(v59 + 3, 3362);
                v44 += (unsigned __int8)*v5;
              }
              ++v5;
            }
            else if ( !v48 )
            {
              if ( (unsigned __int64)(v5 + 2) > *(_QWORD *)(a1 + 128) )
                longjmp((_JBTYPE *)(*(_QWORD *)(a1 + 136) + 48LL), 3362);
              if ( (unsigned __int64)v5 < *(_QWORD *)(a1 + 120) )
                longjmp((_JBTYPE *)(*(_QWORD *)(a1 + 136) + 48LL), 3362);
              v58 = v5;
              v5 += 2;
              v44 += (*v58 << 8) | (unsigned __int8)v58[1];
            }
            ++v45;
            *(_WORD *)(*(_QWORD *)(a1 + 40) + 2 * v46) = v44;
            *(_BYTE *)(v46 + *(_QWORD *)(a1 + 48)) = v47 & 1;
          }
          while ( v45 < *(__int16 *)(a1 + 14) );
        }
      }
    }
    return (unsigned int)((_DWORD)v5 - (_DWORD)a2);
  }
  v64 = *(_QWORD *)(a1 + 136);
  v50 = *(_QWORD *)(a1 + 56) == 0;
  *(_WORD *)(a1 + 68) = v17;
  VerifyConditionInternal(v64, !v50);
  do
  {
    CheckReadBoundsGlyph(a1, v5, 4);
    v65 = (*v5 << 8) | (unsigned __int8)v5[1];
    WriteComponentData(a1, v65);
    v66 = (unsigned int)v5[2];
    v67 = (unsigned __int8)v5[3];
    LOWORD(v66) = v5[2] << 8;
    v68 = v5 + 4;
    LOWORD(v66) = v67 | v66;
    WriteComponentData(a1, v66);
    v69 = v68 + 2;
    if ( (v65 & 1) != 0 )
    {
      CheckReadBoundsGlyph(a1, v68, 4);
      v70 = (unsigned int)*v68;
      LOWORD(v70) = (unsigned __int8)v68[1] | (unsigned __int16)(*v68 << 8);
      WriteComponentData(a1, v70);
      v5 = v68 + 4;
      v71 = (unsigned __int8)v69[1];
      v72 = *v69 << 8;
    }
    else
    {
      CheckReadBoundsGlyph(a1, v68, 2);
      v83 = v68;
      v5 = v68 + 2;
      v71 = (unsigned int)*v83;
      v72 = (unsigned __int8)v83[1];
      LOWORD(v71) = (_WORD)v71 << 8;
    }
    LOWORD(v71) = v72 | v71;
    WriteComponentData(a1, v71);
    if ( (v65 & 8) != 0 )
    {
      CheckReadBoundsGlyph(a1, v5, 2);
      v73 = v5;
      v5 += 2;
      goto LABEL_55;
    }
    if ( (v65 & 0x40) != 0 )
    {
      CheckReadBoundsGlyph(a1, v5, 4);
      v86 = (unsigned int)*v5;
      LOWORD(v86) = (unsigned __int8)v5[1] | (unsigned __int16)(*v5 << 8);
      WriteComponentData(a1, v86);
      v74 = (unsigned int)v5[2];
      v75 = (unsigned __int8)v5[3];
      v5 += 4;
      LOWORD(v74) = (_WORD)v74 << 8;
      goto LABEL_56;
    }
    if ( (v65 & 0x80u) != 0 )
    {
      CheckReadBoundsGlyph(a1, v5, 8);
      WriteComponentData(a1, (unsigned __int16)((*v5 << 8) | (unsigned __int8)v5[1]));
      v87 = (unsigned int)v5[2];
      LOWORD(v87) = (unsigned __int8)v5[3] | (unsigned __int16)(v5[2] << 8);
      WriteComponentData(a1, v87);
      v88 = (unsigned int)v5[4];
      LOWORD(v88) = (unsigned __int8)v5[5] | (unsigned __int16)(v5[4] << 8);
      WriteComponentData(a1, v88);
      v73 = v5 + 6;
      v5 += 8;
LABEL_55:
      v74 = (unsigned __int8)v73[1];
      v75 = *v73 << 8;
LABEL_56:
      LOWORD(v74) = v75 | v74;
      WriteComponentData(a1, v74);
    }
    VerifyConditionInternal(*(_QWORD *)(a1 + 136), *(_WORD *)(a1 + 66) < *(_WORD *)(a1 + 64));
  }
  while ( (v65 & 0x20) != 0 );
  *(_WORD *)(a1 + 70) = 0;
  if ( (v65 & 0x100) != 0 )
  {
    CheckReadBoundsGlyph(a1, v5, 2);
    v76 = v5;
    v5 += 2;
    v77 = (unsigned __int16)((unsigned __int8)v76[1] | (unsigned __int16)(*v76 << 8));
    *(_WORD *)(a1 + 70) = v77;
    VerifyGlyphBuffersize(a1, 1, v77);
    v78 = MTX_mem_malloc(*(_QWORD *)(a1 + 136), *(unsigned __int16 *)(a1 + 70));
    v79 = *(unsigned __int16 *)(a1 + 70);
    *(_QWORD *)(a1 + 72) = v78;
    CheckReadBoundsGlyph(a1, v5, v79);
    for ( k = 0; k < *(_WORD *)(a1 + 70); *(_BYTE *)(v82 + *(_QWORD *)(a1 + 72)) = v81 )
    {
      v81 = *v5++;
      v82 = k++;
    }
  }
  return (unsigned int)((_DWORD)v5 - (_DWORD)a2);
}

```

## disassembly

```asm
0x18000a650  push    rbx
0x18000a652  push    rbp
0x18000a653  push    rsi
0x18000a654  push    rdi
0x18000a655  push    r12
0x18000a657  push    r14
0x18000a659  push    r15
0x18000a65b  sub     rsp, 20h
0x18000a65f  mov     r8d, 0Ah
0x18000a665  mov     rsi, rdx
0x18000a668  mov     rbx, rcx
0x18000a66b  mov     r15, rdx
0x18000a66e  call    CheckReadBoundsGlyph
0x18000a673  movsx   ecx, byte ptr [r15]
0x18000a677  mov     r8d, 1
0x18000a67d  movzx   eax, byte ptr [r15+1]
0x18000a682  add     rsi, 0Ah
0x18000a686  mov     rdx, [rbx+48h]
0x18000a68a  shl     cx, 8
0x18000a68e  or      cx, ax
0x18000a691  mov     [rbx+0Ch], cx
0x18000a695  movsx   ecx, byte ptr [r15+2]
0x18000a69a  movzx   eax, byte ptr [r15+3]
0x18000a69f  shl     cx, 8
0x18000a6a3  or      cx, ax
0x18000a6a6  mov     [rbx+2], cx
0x18000a6aa  movsx   ecx, byte ptr [r15+4]
0x18000a6af  movzx   eax, byte ptr [r15+5]
0x18000a6b4  shl     cx, 8
0x18000a6b8  or      cx, ax
0x18000a6bb  mov     [rbx+6], cx
0x18000a6bf  movsx   ecx, byte ptr [r15+6]
0x18000a6c4  movzx   eax, byte ptr [r15+7]
0x18000a6c9  shl     cx, 8
0x18000a6cd  or      cx, ax
0x18000a6d0  lea     rax, [r15+8]
0x18000a6d4  mov     [rbx], cx
0x18000a6d7  movsx   ecx, byte ptr [rax]
0x18000a6da  movzx   eax, byte ptr [rax+1]
0x18000a6de  shl     cx, 8
0x18000a6e2  or      cx, ax
0x18000a6e5  mov     [rbx+4], cx
0x18000a6e9  mov     rcx, [rbx+88h]
0x18000a6f0  call    DiscardPointer
0x18000a6f5  mov     rdx, [rbx+10h]
0x18000a6f9  xor     r12d, r12d
0x18000a6fc  mov     rcx, [rbx+88h]
0x18000a703  mov     r8d, 1
0x18000a709  mov     [rbx+48h], r12
0x18000a70d  call    DiscardPointer
0x18000a712  mov     rdx, [rbx+18h]
0x18000a716  mov     r8d, 1
0x18000a71c  mov     rcx, [rbx+88h]
0x18000a723  mov     [rbx+10h], r12
0x18000a727  call    DiscardPointer
0x18000a72c  mov     rdx, [rbx+30h]
0x18000a730  mov     r8d, 1
0x18000a736  mov     rcx, [rbx+88h]
0x18000a73d  mov     [rbx+18h], r12
0x18000a741  call    DiscardPointer
0x18000a746  mov     rdx, [rbx+20h]
0x18000a74a  mov     r8d, 1
0x18000a750  mov     rcx, [rbx+88h]
0x18000a757  mov     [rbx+30h], r12
0x18000a75b  call    DiscardPointer
0x18000a760  mov     rdx, [rbx+28h]
0x18000a764  mov     r8d, 1
0x18000a76a  mov     rcx, [rbx+88h]
0x18000a771  mov     [rbx+20h], r12
0x18000a775  call    DiscardPointer
0x18000a77a  movsx   eax, word ptr [rbx+0Ch]
0x18000a77e  mov     [rbx+28h], r12
0x18000a782  mov     [rbx+0Eh], r12w
0x18000a787  test    ax, ax
0x18000a78a  js      loc_18000AC11
0x18000a790  jle     loc_18000AA31
0x18000a796  mov     r8d, eax
0x18000a799  mov     edx, 2
0x18000a79e  mov     rcx, rbx
0x18000a7a1  call    VerifyGlyphBuffersize
0x18000a7a6  movsx   edx, word ptr [rbx+0Ch]
0x18000a7aa  mov     rcx, [rbx+88h]
0x18000a7b1  add     edx, edx
0x18000a7b3  call    MTX_mem_malloc
0x18000a7b8  movsx   r8d, word ptr [rbx+0Ch]
0x18000a7bd  mov     edx, 2
0x18000a7c2  mov     rcx, rbx
0x18000a7c5  mov     [rbx+10h], rax
0x18000a7c9  call    VerifyGlyphBuffersize
0x18000a7ce  movsx   edx, word ptr [rbx+0Ch]
0x18000a7d2  mov     rcx, [rbx+88h]
0x18000a7d9  add     edx, edx
0x18000a7db  call    MTX_mem_malloc
0x18000a7e0  movsx   r8d, word ptr [rbx+0Ch]
0x18000a7e5  mov     rdx, rsi
0x18000a7e8  add     r8d, r8d
0x18000a7eb  mov     [rbx+18h], rax
0x18000a7ef  mov     rcx, rbx
0x18000a7f2  call    CheckReadBoundsGlyph
0x18000a7f7  movzx   ecx, word ptr [rbx+0Ch]
0x18000a7fb  mov     edx, r12d
0x18000a7fe  mov     ebp, r12d
0x18000a801  cmp     r12w, cx
0x18000a805  jl      loc_18000ADF0
0x18000a80b  mov     rax, [rbx+18h]
0x18000a80f  mov     edx, r12d
0x18000a812  movsx   rcx, cx
0x18000a816  movzx   r8d, word ptr [rax+rcx*2-2]
0x18000a81c  mov     rcx, [rbx+88h]
0x18000a823  inc     r8w
0x18000a827  test    r8w, r8w
0x18000a82b  mov     [rbx+0Eh], r8w
0x18000a830  setnle  dl
0x18000a833  call    VerifyConditionInternal
0x18000a838  mov     r8d, 2
0x18000a83e  mov     rdx, rsi
0x18000a841  mov     rcx, rbx
0x18000a844  call    CheckReadBoundsGlyph
0x18000a849  mov     rax, rsi
0x18000a84c  add     rsi, 2
0x18000a850  mov     rdx, rsi
0x18000a853  movsx   ecx, byte ptr [rax]
0x18000a856  movzx   eax, byte ptr [rax+1]
0x18000a85a  shl     cx, 8
0x18000a85e  or      cx, ax
0x18000a861  movzx   r8d, cx
0x18000a865  mov     rcx, rbx
0x18000a868  mov     [rbx+46h], r8w
0x18000a86d  call    CheckReadBoundsGlyph
0x18000a872  movzx   eax, word ptr [rbx+46h]
0x18000a876  test    ax, ax
0x18000a879  jnz     loc_18000ABB2
0x18000a87f  movsx   r8d, word ptr [rbx+0Eh]
0x18000a884  mov     edx, 1
0x18000a889  mov     rcx, rbx
0x18000a88c  call    VerifyGlyphBuffersize
0x18000a891  movsx   edx, word ptr [rbx+0Eh]
0x18000a895  mov     rcx, [rbx+88h]
0x18000a89c  call    MTX_mem_malloc
0x18000a8a1  movzx   ecx, word ptr [rbx+0Eh]
0x18000a8a5  mov     edi, r12d
0x18000a8a8  mov     [rbx+30h], rax
0x18000a8ac  cmp     r12w, cx
0x18000a8b0  jge     short loc_18000A8FC
0x18000a8b2  mov     rcx, [rbx+88h]
0x18000a8b9  lea     rdx, [rsi+1]
0x18000a8bd  cmp     rdx, [rbx+80h]
0x18000a8c4  ja      loc_18000AA55
0x18000a8ca  cmp     rsi, [rbx+78h]
0x18000a8ce  jb      loc_18000AA45
0x18000a8d4  movzx   ebp, byte ptr [rsi]
0x18000a8d7  mov     rsi, rdx
0x18000a8da  mov     rax, [rbx+30h]
0x18000a8de  movsx   rcx, di
0x18000a8e2  inc     di
0x18000a8e5  mov     [rcx+rax], bpl
0x18000a8e9  test    bpl, 8
0x18000a8ed  jnz     loc_18000AAAB
0x18000a8f3  movzx   ecx, word ptr [rbx+0Eh]
0x18000a8f7  cmp     di, cx
0x18000a8fa  jl      short loc_18000A8B2
0x18000a8fc  movsx   r8d, cx
0x18000a900  mov     edx, 2
0x18000a905  mov     rcx, rbx
0x18000a908  call    VerifyGlyphBuffersize
0x18000a90d  movsx   edx, word ptr [rbx+0Eh]
0x18000a911  mov     rcx, [rbx+88h]
0x18000a918  add     edx, edx
0x18000a91a  call    MTX_mem_malloc
0x18000a91f  movsx   r8d, word ptr [rbx+0Eh]
0x18000a924  mov     edx, 2
0x18000a929  mov     rcx, rbx
0x18000a92c  mov     [rbx+20h], rax
0x18000a930  call    VerifyGlyphBuffersize
0x18000a935  movsx   edx, word ptr [rbx+0Eh]
0x18000a939  mov     rcx, [rbx+88h]
0x18000a940  add     edx, edx
0x18000a942  call    MTX_mem_malloc
0x18000a947  mov     ebp, r12d
0x18000a94a  mov     [rbx+28h], rax
0x18000a94e  mov     edi, r12d
0x18000a951  cmp     r12w, [rbx+0Eh]
0x18000a956  jge     loc_18000AA31
0x18000a95c  nop     dword ptr [rax+00h]
0x18000a960  mov     rax, [rbx+30h]
0x18000a964  movsx   r14, di
0x18000a968  movzx   ecx, byte ptr [r14+rax]
0x18000a96d  movzx   eax, cl
0x18000a970  and     al, 10h
0x18000a972  test    cl, 2
0x18000a975  jz      loc_18000AA75
0x18000a97b  mov     r8d, 1
0x18000a981  mov     rdx, rsi
0x18000a984  mov     rcx, rbx
0x18000a987  test    al, al
0x18000a989  jnz     loc_18000AA65
0x18000a98f  call    CheckReadBoundsGlyph
0x18000a994  movzx   eax, byte ptr [rsi]
0x18000a997  sub     bp, ax
0x18000a99a  inc     rsi
0x18000a99d  mov     rax, [rbx+20h]
0x18000a9a1  inc     di
0x18000a9a4  mov     [rax+r14*2], bp
0x18000a9a9  movzx   ecx, word ptr [rbx+0Eh]
0x18000a9ad  cmp     di, cx
0x18000a9b0  jl      short loc_18000A960
0x18000a9b2  mov     r10d, r12d
0x18000a9b5  mov     r8d, r12d
0x18000a9b8  cmp     r12w, cx
0x18000a9bc  jge     short loc_18000AA31
0x18000a9be  xchg    ax, ax
0x18000a9c0  mov     rax, [rbx+30h]
0x18000a9c4  movsx   r9, r8w
0x18000a9c8  movzx   edx, byte ptr [r9+rax]
0x18000a9cd  movzx   eax, dl
0x18000a9d0  and     al, 20h
0x18000a9d2  test    dl, 4
0x18000a9d5  jz      loc_18000AAEE
0x18000a9db  mov     rcx, [rbx+80h]
0x18000a9e2  test    al, al
0x18000a9e4  lea     rax, [rsi+1]
0x18000a9e8  jnz     loc_18000AB4D
0x18000a9ee  cmp     rax, rcx
0x18000a9f1  mov     rcx, [rbx+88h]
0x18000a9f8  ja      loc_18000AB3D
0x18000a9fe  cmp     rsi, [rbx+78h]
0x18000aa02  jb      loc_18000AB2D
0x18000aa08  movzx   eax, byte ptr [rsi]
0x18000aa0b  sub     r10w, ax
0x18000aa0f  inc     rsi
0x18000aa12  mov     rax, [rbx+28h]
0x18000aa16  and     dl, 1
0x18000aa19  inc     r8w
0x18000aa1d  mov     [rax+r9*2], r10w
0x18000aa22  mov     rax, [rbx+30h]
0x18000aa26  mov     [r9+rax], dl
0x18000aa2a  cmp     r8w, [rbx+0Eh]
0x18000aa2f  jl      short loc_18000A9C0
0x18000aa31  sub     esi, r15d
0x18000aa34  mov     eax, esi
0x18000aa36  add     rsp, 20h
0x18000aa3a  pop     r15
0x18000aa3c  pop     r14
0x18000aa3e  pop     r12
0x18000aa40  pop     rdi
0x18000aa41  pop     rsi
0x18000aa42  pop     rbp
0x18000aa43  pop     rbx
0x18000aa44  retn
0x18000aa45  add     rcx, 30h ; '0'; Buf
0x18000aa49  mov     edx, 0D22h; Value
0x18000aa4e  call    cs:__imp_longjmp
0x18000aa55  add     rcx, 30h ; '0'; Buf
0x18000aa59  mov     edx, 0D22h; Value
0x18000aa5e  call    cs:__imp_longjmp
0x18000aa65  call    CheckReadBoundsGlyph
0x18000aa6a  movzx   eax, byte ptr [rsi]
0x18000aa6d  add     bp, ax
0x18000aa70  jmp     loc_18000A99A
0x18000aa75  test    al, al
0x18000aa77  jnz     loc_18000A99D
0x18000aa7d  mov     r8d, 2
0x18000aa83  mov     rdx, rsi
0x18000aa86  mov     rcx, rbx
0x18000aa89  call    CheckReadBoundsGlyph
0x18000aa8e  mov     rax, rsi
0x18000aa91  add     rsi, 2
0x18000aa95  movsx   ecx, byte ptr [rax]
0x18000aa98  movzx   eax, byte ptr [rax+1]
0x18000aa9c  shl     cx, 8
0x18000aaa0  or      cx, ax
0x18000aaa3  add     bp, cx
0x18000aaa6  jmp     loc_18000A99D
0x18000aaab  mov     r8d, 1
0x18000aab1  mov     rcx, rbx
0x18000aab4  call    CheckReadBoundsGlyph
0x18000aab9  movzx   edx, byte ptr [rsi]
0x18000aabc  inc     rsi
0x18000aabf  cmp     di, [rbx+0Eh]
0x18000aac3  jge     loc_18000A8F3
0x18000aac9  test    dl, dl
0x18000aacb  jz      loc_18000A8F3
0x18000aad1  mov     rax, [rbx+30h]
0x18000aad5  add     dl, 0FFh
0x18000aad8  movsx   rcx, di
0x18000aadc  inc     di
0x18000aadf  mov     [rcx+rax], bpl
0x18000aae3  cmp     di, [rbx+0Eh]
0x18000aae7  jl      short loc_18000AAC9
0x18000aae9  jmp     loc_18000A8F3
0x18000aaee  test    al, al
0x18000aaf0  jnz     loc_18000AA12
0x18000aaf6  lea     rcx, [rsi+2]
0x18000aafa  cmp     rcx, [rbx+80h]
0x18000ab01  ja      short loc_18000AB7B
0x18000ab03  mov     rax, [rbx+88h]
0x18000ab0a  cmp     rsi, [rbx+78h]
0x18000ab0e  jb      short loc_18000AB6B
0x18000ab10  mov     rax, rsi
0x18000ab13  mov     rsi, rcx
  ... truncated ...
```
