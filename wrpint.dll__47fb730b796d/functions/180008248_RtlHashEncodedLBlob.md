# RtlHashEncodedLBlob

- ea: `0x180008248`
- end: `0x18000894d`
- name: `RtlHashEncodedLBlob`
- size: `1797`
- prototype: `unsigned __int16 *__fastcall(__int64 *, __int64, unsigned int (__fastcall *)(unsigned int), _QWORD *)`
- caller_count: `3`
- callee_count: `5`
- tags: ``

## callers

- `0x180009e30`
- `0x180016178`
- `0x180016478`

## callees

- `0x1800054f0`
- `0x180007568`
- `0x180008248`
- `0x180009460`
- `0x18001c010`

## pseudocode

```c
unsigned __int16 *__fastcall RtlHashEncodedLBlob(
        __int64 *a1,
        __int64 a2,
        unsigned int (__fastcall *a3)(unsigned int),
        _QWORD *a4)
{
  const char *v4; // rax
  unsigned __int16 *result; // rax
  unsigned __int16 *v6; // rdi
  __int64 v7; // rax
  unsigned __int64 v8; // rbx
  unsigned int v9; // esi
  unsigned int v10; // r14d
  unsigned int v11; // r15d
  unsigned int v12; // r12d
  unsigned __int16 *v13; // rdx
  char v14; // r9
  unsigned __int16 v15; // cx
  unsigned __int16 v16; // ax
  unsigned __int16 v17; // cx
  unsigned __int16 v18; // cx
  unsigned __int16 v19; // ax
  unsigned __int16 v20; // cx
  unsigned __int16 v21; // cx
  unsigned __int16 v22; // ax
  unsigned __int16 v23; // cx
  unsigned __int16 v24; // cx
  unsigned __int16 v25; // ax
  unsigned __int16 v26; // cx
  int v27; // eax
  unsigned __int16 *v28; // rdx
  int v29; // eax
  unsigned __int16 *v30; // rdx
  int v31; // eax
  unsigned __int16 *v32; // rdx
  int v33; // eax
  unsigned __int8 *v34; // rdx
  unsigned __int16 v35; // cx
  unsigned __int16 v36; // ax
  unsigned __int16 v37; // cx
  unsigned __int16 v38; // cx
  unsigned __int16 v39; // ax
  unsigned __int16 v40; // cx
  unsigned __int16 v41; // cx
  unsigned __int16 v42; // ax
  unsigned __int16 v43; // cx
  unsigned __int16 v44; // cx
  unsigned __int16 v45; // ax
  unsigned __int16 v46; // cx
  unsigned int *v47; // rax
  unsigned int *v48; // rax
  unsigned int *v49; // rax
  unsigned int *v50; // rax
  int v51; // eax
  unsigned __int8 *v52; // rdx
  int v53; // eax
  unsigned __int8 *v54; // rdx
  int v55; // eax
  unsigned __int8 *v56; // rdx
  int v57; // eax
  __int64 v58; // rax
  int v59; // ecx
  __int64 v60; // rax
  int v61; // ecx
  __int64 v62; // rax
  int v63; // ecx
  __int64 v64; // rax
  unsigned __int16 v65; // [rsp+20h] [rbp-49h]
  unsigned __int16 v66; // [rsp+20h] [rbp-49h]
  unsigned __int16 v67; // [rsp+20h] [rbp-49h]
  unsigned __int16 v68; // [rsp+20h] [rbp-49h]
  unsigned __int16 v69; // [rsp+20h] [rbp-49h]
  unsigned __int16 v70; // [rsp+20h] [rbp-49h]
  unsigned __int16 v71; // [rsp+20h] [rbp-49h]
  unsigned __int16 v72; // [rsp+20h] [rbp-49h]
  const char *v74; // [rsp+30h] [rbp-39h] BYREF
  const char *v75; // [rsp+38h] [rbp-31h]
  __int64 v76; // [rsp+40h] [rbp-29h]
  const char *v77; // [rsp+48h] [rbp-21h]
  _QWORD *v78; // [rsp+50h] [rbp-19h]
  _BYTE v79[16]; // [rsp+58h] [rbp-11h] BYREF
  _BYTE v80[16]; // [rsp+68h] [rbp-1h] BYREF
  _BYTE v81[72]; // [rsp+78h] [rbp+Fh] BYREF

  v78 = a4;
  if ( a4 )
    *a4 = 0;
  if ( !a1 )
  {
    v76 = 2337;
    v74 = "onecore\\base\\lstring\\lblob.cpp";
    v75 = "RtlHashEncodedLBlob";
    v4 = "Not-null check failed: Blob";
LABEL_5:
    v77 = v4;
    RtlReportErrorOrigination(a1, a2, 3221225485LL);
    return (unsigned __int16 *)3221225485LL;
  }
  v6 = (unsigned __int16 *)a1[2];
  if ( !v6 && *a1 || (v7 = *a1, *a1 > (unsigned __int64)a1[1]) )
  {
    v76 = 2338;
    v74 = "onecore\\base\\lstring\\lblob.cpp";
    v75 = "RtlHashEncodedLBlob";
    v4 = "::RtlIsLBlobValid(Blob)";
    goto LABEL_5;
  }
  if ( !a4 )
  {
    v76 = 2340;
    v74 = "onecore\\base\\lstring\\lblob.cpp";
    v75 = "RtlHashEncodedLBlob";
    v4 = "Not-null check failed: PseudoKeyOut";
    goto LABEL_5;
  }
  v8 = (unsigned __int64)v6 + v7;
  v9 = 0;
  v10 = 0;
  v11 = 0;
  v12 = 0;
  if ( (((unsigned __int8)v6 | (unsigned __int8)v7) & 1) == 0 )
  {
    v13 = (unsigned __int16 *)a1[2];
    if ( a3 == FsnpDowncaseChar )
    {
      v14 = 1;
      if ( v6 == (unsigned __int16 *)v8 )
        goto LABEL_45;
      while ( 1 )
      {
        v15 = *v13++;
        v65 = v15;
        if ( v15 > 0x7Fu )
          break;
        v16 = v15;
        v17 = v15 + 32;
        if ( (unsigned __int16)(v16 - 65) > 0x19u )
          v17 = v65;
        v9 = v17 + 65599 * v9;
        if ( v13 != (unsigned __int16 *)v8 )
        {
          v18 = *v13++;
          v66 = v18;
          if ( v18 > 0x7Fu )
            break;
          v19 = v18;
          v20 = v18 + 32;
          if ( (unsigned __int16)(v19 - 65) > 0x19u )
            v20 = v66;
          v10 = v20 + 65599 * v10;
          if ( v13 != (unsigned __int16 *)v8 )
          {
            v21 = *v13++;
            v67 = v21;
            if ( v21 > 0x7Fu )
              break;
            v22 = v21;
            v23 = v21 + 32;
            if ( (unsigned __int16)(v22 - 65) > 0x19u )
              v23 = v67;
            v11 = v23 + 65599 * v11;
            if ( v13 != (unsigned __int16 *)v8 )
            {
              v24 = *v13++;
              v68 = v24;
              if ( v24 > 0x7Fu )
                break;
              v25 = v24;
              v26 = v24 + 32;
              if ( (unsigned __int16)(v25 - 65) > 0x19u )
                v26 = v68;
              v12 = v26 + 65599 * v12;
              if ( v13 != (unsigned __int16 *)v8 )
                continue;
            }
          }
        }
        goto LABEL_45;
      }
    }
    v14 = 0;
    if ( !a3 )
    {
      v14 = 1;
      while ( v13 != (unsigned __int16 *)v8 )
      {
        v27 = *v13;
        if ( (unsigned __int16)v27 > 0x7Fu )
          goto LABEL_44;
        v28 = v13 + 1;
        v9 = v27 + 65599 * v9;
        if ( v28 == (unsigned __int16 *)v8 )
          break;
        v29 = *v28;
        if ( (unsigned __int16)v29 > 0x7Fu )
          goto LABEL_44;
        v30 = v28 + 1;
        v10 = v29 + 65599 * v10;
        if ( v30 == (unsigned __int16 *)v8 )
          break;
        v31 = *v30;
        if ( (unsigned __int16)v31 > 0x7Fu )
          goto LABEL_44;
        v32 = v30 + 1;
        v11 = v31 + 65599 * v11;
        if ( v32 == (unsigned __int16 *)v8 )
          break;
        v33 = *v32;
        if ( (unsigned __int16)v33 > 0x7Fu )
        {
LABEL_44:
          v14 = 0;
          break;
        }
        v13 = v32 + 1;
        v12 = v33 + 65599 * v12;
      }
    }
LABEL_45:
    v9 &= -(v14 != 0);
    v10 &= -(v14 != 0);
    v11 &= -(v14 != 0);
    v12 &= -(v14 != 0);
    if ( v14 )
    {
LABEL_46:
      *v78 = v12 + 0x1FFFFFFF7LL * v11 + 0xFFFFFFDC00000051uLL * v10 + 0x1E5FFFFFD27LL * v9;
      return 0;
    }
    goto LABEL_70;
  }
  if ( (char *)RtlDecodeUtf16LE == (char *)RtlDecodeUtf8 )
  {
    v34 = (unsigned __int8 *)a1[2];
    if ( a3 == FsnpDowncaseChar )
    {
      if ( v6 == (unsigned __int16 *)v8 )
        goto LABEL_46;
      while ( 1 )
      {
        v35 = *v34++;
        v69 = v35;
        if ( v35 > 0x7Fu )
          break;
        v36 = v35;
        v37 = v35 + 32;
        if ( (unsigned __int16)(v36 - 65) > 0x19u )
          v37 = v69;
        v9 = v37 + 65599 * v9;
        if ( v34 != (unsigned __int8 *)v8 )
        {
          v38 = *v34++;
          v70 = v38;
          if ( v38 > 0x7Fu )
            break;
          v39 = v38;
          v40 = v38 + 32;
          if ( (unsigned __int16)(v39 - 65) > 0x19u )
            v40 = v70;
          v10 = v40 + 65599 * v10;
          if ( v34 != (unsigned __int8 *)v8 )
          {
            v41 = *v34++;
            v71 = v41;
            if ( v41 > 0x7Fu )
              break;
            v42 = v41;
            v43 = v41 + 32;
            if ( (unsigned __int16)(v42 - 65) > 0x19u )
              v43 = v71;
            v11 = v43 + 65599 * v11;
            if ( v34 != (unsigned __int8 *)v8 )
            {
              v44 = *v34++;
              v72 = v44;
              if ( v44 > 0x7Fu )
                break;
              v45 = v44;
              v46 = v44 + 32;
              if ( (unsigned __int16)(v45 - 65) > 0x19u )
                v46 = v72;
              v12 = v46 + 65599 * v12;
              if ( v34 != (unsigned __int8 *)v8 )
                continue;
            }
          }
        }
        goto LABEL_46;
      }
    }
    if ( !a3 )
    {
      while ( v34 != (unsigned __int8 *)v8 )
      {
        v51 = *v34;
        if ( (unsigned __int8)v51 > 0x7Fu )
          goto LABEL_69;
        v52 = v34 + 1;
        v9 = v51 + 65599 * v9;
        if ( v52 == (unsigned __int8 *)v8 )
          break;
        v53 = *v52;
        if ( (unsigned __int8)v53 > 0x7Fu )
          goto LABEL_69;
        v54 = v52 + 1;
        v10 = v53 + 65599 * v10;
        if ( v54 == (unsigned __int8 *)v8 )
          break;
        v55 = *v54;
        if ( (unsigned __int8)v55 > 0x7Fu )
          goto LABEL_69;
        v56 = v54 + 1;
        v11 = v55 + 65599 * v11;
        if ( v56 == (unsigned __int8 *)v8 )
          break;
        v57 = *v56;
        if ( (unsigned __int8)v57 > 0x7Fu )
          goto LABEL_69;
        v34 = v56 + 1;
        v12 = v57 + 65599 * v12;
      }
      goto LABEL_46;
    }
LABEL_69:
    v9 = 0;
    v10 = 0;
    v11 = 0;
    v12 = 0;
  }
LABEL_70:
  if ( v6 == (unsigned __int16 *)v8 )
    goto LABEL_46;
  if ( a3 )
  {
    while ( 1 )
    {
      v47 = (unsigned int *)RtlDecodeUtf16LE((__int64)v79, v6, v8);
      v6 = (unsigned __int16 *)*((_QWORD *)v47 + 1);
      if ( *v47 == -1 )
        break;
      v9 = ((__int64 (__fastcall *)(_QWORD))a3)(*v47) + 65599 * v9;
      if ( v6 == (unsigned __int16 *)v8 )
        goto LABEL_46;
      v48 = (unsigned int *)RtlDecodeUtf16LE((__int64)v80, v6, v8);
      v6 = (unsigned __int16 *)*((_QWORD *)v48 + 1);
      if ( *v48 == -1 )
        break;
      v10 = ((__int64 (__fastcall *)(_QWORD))a3)(*v48) + 65599 * v10;
      if ( v6 == (unsigned __int16 *)v8 )
        goto LABEL_46;
      v49 = (unsigned int *)RtlDecodeUtf16LE((__int64)v81, v6, v8);
      v6 = (unsigned __int16 *)*((_QWORD *)v49 + 1);
      if ( *v49 == -1 )
        break;
      v11 = ((__int64 (__fastcall *)(_QWORD))a3)(*v49) + 65599 * v11;
      if ( v6 == (unsigned __int16 *)v8 )
        goto LABEL_46;
      v50 = (unsigned int *)RtlDecodeUtf16LE((__int64)&v74, v6, v8);
      v6 = (unsigned __int16 *)*((_QWORD *)v50 + 1);
      if ( *v50 == -1 )
        break;
      v12 = ((__int64 (__fastcall *)(_QWORD))a3)(*v50) + 65599 * v12;
      if ( v6 == (unsigned __int16 *)v8 )
        goto LABEL_46;
    }
LABEL_91:
    if ( (int)v6 < 0 )
      return (unsigned __int16 *)(unsigned int)v6;
LABEL_103:
    INTERNAL_ERROR_ACTION(-1073741595);
  }
  while ( 1 )
  {
    v58 = RtlDecodeUtf16LE((__int64)&v74, v6, v8);
    v59 = *(_DWORD *)v58;
    result = *(unsigned __int16 **)(v58 + 8);
    if ( v59 == -1 )
      break;
    v9 = v59 + 65599 * v9;
    if ( result == (unsigned __int16 *)v8 )
      goto LABEL_46;
    v60 = RtlDecodeUtf16LE((__int64)v81, result, v8);
    v61 = *(_DWORD *)v60;
    result = *(unsigned __int16 **)(v60 + 8);
    if ( v61 == -1 )
      break;
    v10 = v61 + 65599 * v10;
    if ( result == (unsigned __int16 *)v8 )
      goto LABEL_46;
    v62 = RtlDecodeUtf16LE((__int64)v80, result, v8);
    v63 = *(_DWORD *)v62;
    result = *(unsigned __int16 **)(v62 + 8);
    if ( v63 == -1 )
      break;
    v11 = v63 + 65599 * v11;
    if ( result == (unsigned __int16 *)v8 )
      goto LABEL_46;
    v64 = RtlDecodeUtf16LE((__int64)v79, result, v8);
    v6 = *(unsigned __int16 **)(v64 + 8);
    if ( *(_DWORD *)v64 == -1 )
      goto LABEL_91;
    v12 = *(_DWORD *)v64 + 65599 * v12;
    if ( v6 == (unsigned __int16 *)v8 )
      goto LABEL_46;
  }
  if ( (int)result >= 0 )
    goto LABEL_103;
  return result;
}

```

## disassembly

```asm
0x180008248  mov     [rsp-8+arg_8], rbx
0x18000824d  push    rbp
0x18000824e  push    rsi
0x18000824f  push    rdi
0x180008250  push    r12
0x180008252  push    r13
0x180008254  push    r14
0x180008256  push    r15
0x180008258  lea     rbp, [rsp-27h]
0x18000825d  sub     rsp, 90h
0x180008264  mov     [rbp+57h+var_70], r9
0x180008268  mov     r10, r8
0x18000826b  mov     [rbp+57h+var_98], r8
0x18000826f  test    r9, r9
0x180008272  jz      short loc_18000827B
0x180008274  mov     qword ptr [r9], 0
0x18000827b  test    rcx, rcx
0x18000827e  jnz     short loc_1800082BE
0x180008280  lea     rax, aOnecoreBaseLst_1; "onecore\\base\\lstring\\lblob.cpp"
0x180008287  mov     [rbp+57h+var_80], 921h
0x18000828f  mov     [rbp+57h+var_90], rax
0x180008293  lea     rax, aRtlhashencoded; "RtlHashEncodedLBlob"
0x18000829a  mov     [rbp+57h+var_88], rax
0x18000829e  lea     rax, aNotNullCheckFa_18; "Not-null check failed: Blob"
0x1800082a5  mov     r8d, 0C000000Dh
0x1800082ab  mov     [rbp+57h+var_78], rax
0x1800082af  call    RtlReportErrorOrigination
0x1800082b4  mov     eax, 0C000000Dh
0x1800082b9  jmp     loc_18000856D
0x1800082be  mov     rdi, [rcx+10h]
0x1800082c2  test    rdi, rdi
0x1800082c5  jnz     short loc_1800082CC
0x1800082c7  cmp     [rcx], rdi
0x1800082ca  jnz     short loc_1800082D5
0x1800082cc  mov     rax, [rcx]
0x1800082cf  cmp     rax, [rcx+8]
0x1800082d3  jbe     short loc_1800082FC
0x1800082d5  lea     rax, aOnecoreBaseLst_1; "onecore\\base\\lstring\\lblob.cpp"
0x1800082dc  mov     [rbp+57h+var_80], 922h
0x1800082e4  mov     [rbp+57h+var_90], rax
0x1800082e8  lea     rax, aRtlhashencoded; "RtlHashEncodedLBlob"
0x1800082ef  mov     [rbp+57h+var_88], rax
0x1800082f3  lea     rax, aRtlislblobvali_0; "::RtlIsLBlobValid(Blob)"
0x1800082fa  jmp     short loc_1800082A5
0x1800082fc  test    r9, r9
0x1800082ff  jnz     short loc_18000832B
0x180008301  lea     rax, aOnecoreBaseLst_1; "onecore\\base\\lstring\\lblob.cpp"
0x180008308  mov     [rbp+57h+var_80], 924h
0x180008310  mov     [rbp+57h+var_90], rax
0x180008314  lea     rax, aRtlhashencoded; "RtlHashEncodedLBlob"
0x18000831b  mov     [rbp+57h+var_88], rax
0x18000831f  lea     rax, aNotNullCheckFa_3; "Not-null check failed: PseudoKeyOut"
0x180008326  jmp     loc_1800082A5
0x18000832b  lea     rbx, [rax+rdi]
0x18000832f  xor     esi, esi
0x180008331  or      rax, rdi
0x180008334  xor     r14d, r14d
0x180008337  xor     r15d, r15d
0x18000833a  xor     r12d, r12d
0x18000833d  test    al, 1
0x18000833f  jnz     loc_180008588
0x180008345  lea     rax, ?FsnpDowncaseChar@@YAKK@Z; FsnpDowncaseChar(ulong)
0x18000834c  mov     rdx, rdi
0x18000834f  mov     r8w, 7Fh
0x180008354  cmp     r10, rax
0x180008357  jz      short loc_180008369
0x180008359  lea     rax, ?FsnpDowncaseChar@@YAKK@Z; FsnpDowncaseChar(ulong)
0x180008360  cmp     r10, rax
0x180008363  jnz     loc_180008476
0x180008369  mov     r9b, 1
0x18000836c  cmp     rdi, rbx
0x18000836f  jz      loc_1800084F6
0x180008375  mov     r11w, 41h ; 'A'
0x18000837a  mov     r13w, 20h ; ' '
0x18000837f  movzx   ecx, word ptr [rdx]
0x180008382  add     rdx, 2
0x180008386  mov     [rbp+57h+var_A0], cx
0x18000838a  cmp     cx, r8w
0x18000838e  ja      loc_180008476
0x180008394  movzx   eax, cx
0x180008397  add     cx, r13w
0x18000839b  sub     ax, r11w
0x18000839f  cmp     ax, 19h
0x1800083a3  cmova   cx, [rbp+57h+var_A0]
0x1800083a8  imul    esi, 1003Fh
0x1800083ae  movzx   ecx, cx
0x1800083b1  add     esi, ecx
0x1800083b3  cmp     rdx, rbx
0x1800083b6  jz      loc_1800084F6
0x1800083bc  movzx   ecx, word ptr [rdx]
0x1800083bf  add     rdx, 2
0x1800083c3  mov     [rbp+57h+var_A0], cx
0x1800083c7  cmp     cx, r8w
0x1800083cb  ja      loc_180008476
0x1800083d1  movzx   eax, cx
0x1800083d4  add     cx, r13w
0x1800083d8  sub     ax, r11w
0x1800083dc  cmp     ax, 19h
0x1800083e0  cmova   cx, [rbp+57h+var_A0]
0x1800083e5  imul    r14d, 1003Fh
0x1800083ec  movzx   ecx, cx
0x1800083ef  add     r14d, ecx
0x1800083f2  cmp     rdx, rbx
0x1800083f5  jz      loc_1800084F6
0x1800083fb  movzx   ecx, word ptr [rdx]
0x1800083fe  add     rdx, 2
0x180008402  mov     [rbp+57h+var_A0], cx
0x180008406  cmp     cx, r8w
0x18000840a  ja      short loc_180008476
0x18000840c  movzx   eax, cx
0x18000840f  add     cx, r13w
0x180008413  sub     ax, r11w
0x180008417  cmp     ax, 19h
0x18000841b  cmova   cx, [rbp+57h+var_A0]
0x180008420  imul    r15d, 1003Fh
0x180008427  movzx   ecx, cx
0x18000842a  add     r15d, ecx
0x18000842d  cmp     rdx, rbx
0x180008430  jz      loc_1800084F6
0x180008436  movzx   ecx, word ptr [rdx]
0x180008439  add     rdx, 2
0x18000843d  mov     [rbp+57h+var_A0], cx
0x180008441  cmp     cx, r8w
0x180008445  ja      short loc_180008476
0x180008447  movzx   eax, cx
0x18000844a  add     cx, r13w
0x18000844e  sub     ax, r11w
0x180008452  cmp     ax, 19h
0x180008456  cmova   cx, [rbp+57h+var_A0]
0x18000845b  imul    r12d, 1003Fh
0x180008462  movzx   ecx, cx
0x180008465  add     r12d, ecx
0x180008468  cmp     rdx, rbx
0x18000846b  jnz     loc_18000837F
0x180008471  jmp     loc_1800084F6
0x180008476  xor     r9b, r9b
0x180008479  test    r10, r10
0x18000847c  jnz     short loc_1800084F6
0x18000847e  mov     r9b, 1
0x180008481  jmp     short loc_1800084EC
0x180008483  movzx   eax, word ptr [rdx]
0x180008486  cmp     ax, r8w
0x18000848a  ja      short loc_1800084F3
0x18000848c  imul    esi, 1003Fh
0x180008492  add     rdx, 2
0x180008496  add     esi, eax
0x180008498  cmp     rdx, rbx
0x18000849b  jz      short loc_1800084F6
0x18000849d  movzx   eax, word ptr [rdx]
0x1800084a0  cmp     ax, r8w
0x1800084a4  ja      short loc_1800084F3
0x1800084a6  imul    r14d, 1003Fh
0x1800084ad  add     rdx, 2
0x1800084b1  add     r14d, eax
0x1800084b4  cmp     rdx, rbx
0x1800084b7  jz      short loc_1800084F6
0x1800084b9  movzx   eax, word ptr [rdx]
0x1800084bc  cmp     ax, r8w
0x1800084c0  ja      short loc_1800084F3
0x1800084c2  imul    r15d, 1003Fh
0x1800084c9  add     rdx, 2
0x1800084cd  add     r15d, eax
0x1800084d0  cmp     rdx, rbx
0x1800084d3  jz      short loc_1800084F6
0x1800084d5  movzx   eax, word ptr [rdx]
0x1800084d8  cmp     ax, r8w
0x1800084dc  ja      short loc_1800084F3
0x1800084de  imul    r12d, 1003Fh
0x1800084e5  add     rdx, 2
0x1800084e9  add     r12d, eax
0x1800084ec  cmp     rdx, rbx
0x1800084ef  jnz     short loc_180008483
0x1800084f1  jmp     short loc_1800084F6
0x1800084f3  xor     r9b, r9b
0x1800084f6  mov     al, r9b
0x1800084f9  neg     al
0x1800084fb  mov     al, r9b
0x1800084fe  sbb     ecx, ecx
0x180008500  and     esi, ecx
0x180008502  neg     al
0x180008504  mov     al, r9b
0x180008507  sbb     ecx, ecx
0x180008509  and     r14d, ecx
0x18000850c  neg     al
0x18000850e  mov     al, r9b
0x180008511  sbb     ecx, ecx
0x180008513  and     r15d, ecx
0x180008516  neg     al
0x180008518  sbb     ecx, ecx
0x18000851a  and     r12d, ecx
0x18000851d  test    r9b, r9b
0x180008520  jz      loc_1800086E2
0x180008526  mov     rax, 1E5FFFFFD27h
0x180008530  mov     ecx, esi
0x180008532  imul    rcx, rax
0x180008536  mov     rdx, 0FFFFFFDC00000051h
0x180008540  mov     eax, r14d
0x180008543  imul    rax, rdx
0x180008547  mov     rdx, 1FFFFFFF7h
0x180008551  add     rcx, rax
0x180008554  mov     eax, r15d
0x180008557  imul    rax, rdx
0x18000855b  add     rcx, rax
0x18000855e  mov     eax, r12d
0x180008561  add     rcx, rax
0x180008564  mov     rax, [rbp+57h+var_70]
0x180008568  mov     [rax], rcx
0x18000856b  xor     eax, eax
0x18000856d  mov     rbx, [rsp+0C0h+arg_8]
0x180008575  add     rsp, 90h
0x18000857c  pop     r15
0x18000857e  pop     r14
0x180008580  pop     r13
0x180008582  pop     r12
0x180008584  pop     rdi
0x180008585  pop     rsi
0x180008586  pop     rbp
0x180008587  retn
0x180008588  lea     rcx, RtlDecodeUtf16LE
0x18000858f  lea     rax, RtlDecodeUtf8
0x180008596  cmp     rcx, rax
0x180008599  jnz     loc_1800086E2
0x18000859f  lea     rax, ?FsnpDowncaseChar@@YAKK@Z; FsnpDowncaseChar(ulong)
0x1800085a6  mov     rdx, rdi
0x1800085a9  mov     r8w, 7Fh
0x1800085ae  cmp     r10, rax
0x1800085b1  jz      short loc_1800085C3
0x1800085b3  lea     rax, ?FsnpDowncaseChar@@YAKK@Z; FsnpDowncaseChar(ulong)
0x1800085ba  cmp     r10, rax
0x1800085bd  jnz     loc_1800086CE
0x1800085c3  cmp     rdi, rbx
0x1800085c6  jz      loc_180008526
0x1800085cc  mov     r11w, 41h ; 'A'
0x1800085d1  mov     r13w, 20h ; ' '
0x1800085d6  mov     r9w, 19h
0x1800085db  movzx   ecx, byte ptr [rdx]
0x1800085de  inc     rdx
0x1800085e1  mov     [rbp+57h+var_A0], cx
0x1800085e5  cmp     cx, r8w
0x1800085e9  ja      loc_1800086CE
0x1800085ef  movzx   eax, cx
0x1800085f2  add     cx, r13w
0x1800085f6  sub     ax, r11w
0x1800085fa  cmp     ax, r9w
0x1800085fe  cmova   cx, [rbp+57h+var_A0]
0x180008603  imul    esi, 1003Fh
0x180008609  movzx   ecx, cx
0x18000860c  add     esi, ecx
0x18000860e  cmp     rdx, rbx
0x180008611  jz      loc_180008526
0x180008617  movzx   ecx, byte ptr [rdx]
0x18000861a  inc     rdx
0x18000861d  mov     [rbp+57h+var_A0], cx
0x180008621  cmp     cx, r8w
0x180008625  ja      loc_1800086CE
0x18000862b  movzx   eax, cx
0x18000862e  add     cx, r13w
0x180008632  sub     ax, r11w
0x180008636  cmp     ax, r9w
0x18000863a  cmova   cx, [rbp+57h+var_A0]
0x18000863f  imul    r14d, 1003Fh
0x180008646  movzx   ecx, cx
0x180008649  add     r14d, ecx
0x18000864c  cmp     rdx, rbx
0x18000864f  jz      loc_180008526
0x180008655  movzx   ecx, byte ptr [rdx]
0x180008658  inc     rdx
0x18000865b  mov     [rbp+57h+var_A0], cx
0x18000865f  cmp     cx, r8w
0x180008663  ja      short loc_1800086CE
0x180008665  movzx   eax, cx
0x180008668  add     cx, r13w
0x18000866c  sub     ax, r11w
0x180008670  cmp     ax, r9w
0x180008674  cmova   cx, [rbp+57h+var_A0]
0x180008679  imul    r15d, 1003Fh
0x180008680  movzx   ecx, cx
0x180008683  add     r15d, ecx
0x180008686  cmp     rdx, rbx
0x180008689  jz      loc_180008526
0x18000868f  movzx   ecx, byte ptr [rdx]
0x180008692  inc     rdx
0x180008695  mov     [rbp+57h+var_A0], cx
0x180008699  cmp     cx, r8w
0x18000869d  ja      short loc_1800086CE
0x18000869f  movzx   eax, cx
0x1800086a2  add     cx, r13w
0x1800086a6  sub     ax, r11w
0x1800086aa  cmp     ax, r9w
0x1800086ae  cmova   cx, [rbp+57h+var_A0]
0x1800086b3  imul    r12d, 1003Fh
0x1800086ba  movzx   ecx, cx
0x1800086bd  add     r12d, ecx
0x1800086c0  cmp     rdx, rbx
0x1800086c3  jnz     loc_1800085DB
0x1800086c9  jmp     loc_180008526
0x1800086ce  test    r10, r10
0x1800086d1  jz      loc_180008860
0x1800086d7  xor     esi, esi
0x1800086d9  xor     r14d, r14d
  ... truncated ...
```
