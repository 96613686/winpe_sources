# wil::StoredFailureInfo::SetFailureInfo(wil::FailureInfo const &)

- ea: `0x180002d40`
- end: `0x18000336a`
- name: `?SetFailureInfo@StoredFailureInfo@wil@@QEAAXAEBUFailureInfo@2@@Z`
- size: `1578`
- prototype: `void __fastcall(wil::StoredFailureInfo *__hidden this, const struct wil::FailureInfo *)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x180002124`

## callees

- `0x18000209e`
- `0x180002d40`
- `0x180003490`
- `0x180003688`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180002f41`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180002f41`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180002f4f`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180002f4f`

## pseudocode

```c
void __fastcall wil::StoredFailureInfo::SetFailureInfo(wil::StoredFailureInfo *this, const struct wil::FailureInfo *a2)
{
  __int64 v2; // r15
  __int64 v5; // rbx
  __int64 v6; // rcx
  __int64 v7; // r13
  __int64 v8; // rax
  __int64 v9; // rcx
  __int64 v10; // r12
  __int64 v11; // rax
  __int64 v12; // rcx
  __int64 v13; // r14
  __int64 v14; // rax
  __int64 v15; // rcx
  __int64 v16; // rdi
  __int64 v17; // rax
  __int64 v18; // rcx
  __int64 v19; // r11
  __int64 v20; // rax
  __int64 v21; // rcx
  __int64 v22; // r10
  __int64 v23; // rax
  __int64 v24; // rcx
  __int64 v25; // r9
  __int64 v26; // rax
  __int64 v27; // rcx
  __int64 v28; // r8
  __int64 v29; // rax
  __int64 v30; // rcx
  __int64 v31; // rdx
  __int64 v32; // rax
  __int64 v33; // rcx
  __int64 v34; // rax
  __int64 v35; // rax
  void **v36; // rdi
  volatile signed __int32 *v37; // rcx
  volatile signed __int32 *v38; // r14
  void *v39; // rbx
  HANDLE ProcessHeap; // rax
  char *v41; // rbx
  rsize_t v42; // rdx
  char **v43; // r14
  char *v44; // rdi
  _WORD *v45; // r8
  __int64 v46; // rax
  unsigned __int64 v47; // r12
  char **v48; // r14
  _BYTE *v49; // r8
  __int64 v50; // rax
  __int64 v51; // r12
  char **v52; // r14
  _BYTE *v53; // r8
  __int64 v54; // rax
  __int64 v55; // r12
  char **v56; // r14
  _BYTE *v57; // r8
  __int64 v58; // rax
  __int64 v59; // r12
  char **v60; // r14
  _BYTE *v61; // r8
  __int64 v62; // rax
  __int64 v63; // r12
  char **v64; // r14
  _BYTE *v65; // r8
  __int64 v66; // rax
  __int64 v67; // r12
  char **v68; // r14
  _BYTE *v69; // r8
  __int64 v70; // rax
  __int64 v71; // r12
  char **v72; // r14
  _WORD *v73; // r8
  __int64 v74; // rax
  unsigned __int64 v75; // r12
  char **v76; // r14
  _BYTE *v77; // r8
  __int64 v78; // rax
  __int64 v79; // r12
  char **v80; // rsi
  _WORD *v81; // r8
  rsize_t v82; // r15

  v2 = -1;
  *(_OWORD *)this = *(_OWORD *)a2;
  v5 = 2;
  *((_OWORD *)this + 1) = *((_OWORD *)a2 + 1);
  *((_OWORD *)this + 2) = *((_OWORD *)a2 + 2);
  *((_OWORD *)this + 3) = *((_OWORD *)a2 + 3);
  *((_OWORD *)this + 4) = *((_OWORD *)a2 + 4);
  *((_OWORD *)this + 5) = *((_OWORD *)a2 + 5);
  *((_OWORD *)this + 6) = *((_OWORD *)a2 + 6);
  *((_OWORD *)this + 7) = *((_OWORD *)a2 + 7);
  *((_OWORD *)this + 8) = *((_OWORD *)a2 + 8);
  *((_QWORD *)this + 18) = *((_QWORD *)a2 + 18);
  v6 = *((_QWORD *)a2 + 3);
  if ( v6 )
  {
    v8 = -1;
    do
      ++v8;
    while ( *(_WORD *)(v6 + 2 * v8) );
    v7 = 2 * v8 + 2;
  }
  else
  {
    v7 = 2;
  }
  v9 = *((_QWORD *)a2 + 5);
  if ( v9 )
  {
    v11 = -1;
    do
      ++v11;
    while ( *(_BYTE *)(v9 + v11) );
    v10 = v11 + 1;
  }
  else
  {
    v10 = 1;
  }
  v12 = *((_QWORD *)a2 + 6);
  if ( v12 )
  {
    v14 = -1;
    do
      ++v14;
    while ( *(_BYTE *)(v12 + v14) );
    v13 = v14 + 1;
  }
  else
  {
    v13 = 1;
  }
  v15 = *((_QWORD *)a2 + 7);
  if ( v15 )
  {
    v17 = -1;
    do
      ++v17;
    while ( *(_BYTE *)(v15 + v17) );
    v16 = v17 + 1;
  }
  else
  {
    v16 = 1;
  }
  v18 = *((_QWORD *)a2 + 9);
  if ( v18 )
  {
    v20 = -1;
    do
      ++v20;
    while ( *(_BYTE *)(v18 + v20) );
    v19 = v20 + 1;
  }
  else
  {
    v19 = 1;
  }
  v21 = *((_QWORD *)a2 + 16);
  if ( v21 )
  {
    v23 = -1;
    do
      ++v23;
    while ( *(_BYTE *)(v21 + v23) );
    v22 = v23 + 1;
  }
  else
  {
    v22 = 1;
  }
  v24 = *((_QWORD *)a2 + 14);
  if ( v24 )
  {
    v26 = -1;
    do
      ++v26;
    while ( *(_BYTE *)(v24 + v26) );
    v25 = v26 + 1;
  }
  else
  {
    v25 = 1;
  }
  v27 = *((_QWORD *)a2 + 15);
  if ( v27 )
  {
    v29 = -1;
    do
      ++v29;
    while ( *(_WORD *)(v27 + 2 * v29) );
    v28 = 2 * v29 + 2;
  }
  else
  {
    v28 = 2;
  }
  v30 = *((_QWORD *)a2 + 11);
  if ( v30 )
  {
    v32 = -1;
    do
      ++v32;
    while ( *(_BYTE *)(v30 + v32) );
    v31 = v32 + 1;
  }
  else
  {
    v31 = 1;
  }
  v33 = *((_QWORD *)a2 + 12);
  if ( v33 )
  {
    v34 = -1;
    do
      ++v34;
    while ( *(_WORD *)(v33 + 2 * v34) );
    v5 = 2 * v34 + 2;
  }
  v35 = v16 + v19 + v22 + v25 + v28 + v5 + v31;
  v36 = (void **)((char *)this + 152);
  v37 = (volatile signed __int32 *)*((_QWORD *)this + 19);
  v38 = (volatile signed __int32 *)(v7 + v10 + v35 + v13);
  if ( !v37 )
    goto LABEL_56;
  if ( *v37 != 1 || *((_QWORD *)this + 20) < (unsigned __int64)v38 )
  {
    if ( _InterlockedExchangeAdd(v37, 0xFFFFFFFF) == 1 )
    {
      v39 = *v36;
      ProcessHeap = GetProcessHeap();
      HeapFree(ProcessHeap, 0, v39);
    }
    *v36 = 0;
    *((_QWORD *)this + 20) = 0;
LABEL_56:
    wil::details::shared_buffer::create((volatile signed __int32 **)this + 19, v38);
  }
  v41 = (char *)(((unsigned __int64)*v36 + 4) & -(__int64)(*v36 != 0));
  if ( !v41 )
    return;
  v42 = *((_QWORD *)this + 20);
  v43 = (char **)((char *)this + 24);
  v44 = &v41[v42];
  if ( v41 != &v41[v42] && (v45 = (_WORD *)*((_QWORD *)a2 + 3)) != 0 && *v45 )
  {
    v46 = -1;
    do
      ++v46;
    while ( v45[v46] );
    v47 = 2 * v46 + 2;
    if ( v42 < v47 )
    {
      if ( this != (wil::StoredFailureInfo *)-24LL )
        *v43 = 0;
      v48 = (char **)((char *)this + 40);
      goto LABEL_73;
    }
    memcpy_s(v41, v42, v45, 2 * v46 + 2);
    if ( this != (wil::StoredFailureInfo *)-24LL )
      *v43 = v41;
    v41 += v47;
  }
  else if ( this != (wil::StoredFailureInfo *)-24LL )
  {
    *v43 = 0;
  }
  v48 = (char **)((char *)this + 40);
  if ( v41 == v44 )
    goto LABEL_84;
LABEL_73:
  v49 = (_BYTE *)*((_QWORD *)a2 + 5);
  if ( !v49 || !*v49 )
  {
LABEL_84:
    if ( v48 )
      *v48 = 0;
    goto LABEL_86;
  }
  v50 = -1;
  do
    ++v50;
  while ( v49[v50] );
  v51 = v50 + 1;
  if ( v44 - v41 < (unsigned __int64)(v50 + 1) )
  {
    if ( v48 )
      *v48 = 0;
    v52 = (char **)((char *)this + 48);
    goto LABEL_87;
  }
  memcpy_s(v41, v44 - v41, v49, v50 + 1);
  if ( v48 )
    *v48 = v41;
  v41 += v51;
LABEL_86:
  v52 = (char **)((char *)this + 48);
  if ( v41 == v44 )
    goto LABEL_98;
LABEL_87:
  v53 = (_BYTE *)*((_QWORD *)a2 + 6);
  if ( !v53 || !*v53 )
  {
LABEL_98:
    if ( v52 )
      *v52 = 0;
    goto LABEL_100;
  }
  v54 = -1;
  do
    ++v54;
  while ( v53[v54] );
  v55 = v54 + 1;
  if ( v44 - v41 < (unsigned __int64)(v54 + 1) )
  {
    if ( v52 )
      *v52 = 0;
    v56 = (char **)((char *)this + 56);
    goto LABEL_101;
  }
  memcpy_s(v41, v44 - v41, v53, v54 + 1);
  if ( v52 )
    *v52 = v41;
  v41 += v55;
LABEL_100:
  v56 = (char **)((char *)this + 56);
  if ( v41 == v44 )
    goto LABEL_112;
LABEL_101:
  v57 = (_BYTE *)*((_QWORD *)a2 + 7);
  if ( !v57 || !*v57 )
  {
LABEL_112:
    if ( v56 )
      *v56 = 0;
    goto LABEL_114;
  }
  v58 = -1;
  do
    ++v58;
  while ( v57[v58] );
  v59 = v58 + 1;
  if ( v44 - v41 < (unsigned __int64)(v58 + 1) )
  {
    if ( v56 )
      *v56 = 0;
    v60 = (char **)((char *)this + 72);
    goto LABEL_115;
  }
  memcpy_s(v41, v44 - v41, v57, v58 + 1);
  if ( v56 )
    *v56 = v41;
  v41 += v59;
LABEL_114:
  v60 = (char **)((char *)this + 72);
  if ( v41 == v44 )
    goto LABEL_126;
LABEL_115:
  v61 = (_BYTE *)*((_QWORD *)a2 + 9);
  if ( !v61 || !*v61 )
  {
LABEL_126:
    if ( v60 )
      *v60 = 0;
    goto LABEL_128;
  }
  v62 = -1;
  do
    ++v62;
  while ( v61[v62] );
  v63 = v62 + 1;
  if ( v44 - v41 < (unsigned __int64)(v62 + 1) )
  {
    if ( v60 )
      *v60 = 0;
    v64 = (char **)((char *)this + 128);
    goto LABEL_129;
  }
  memcpy_s(v41, v44 - v41, v61, v62 + 1);
  if ( v60 )
    *v60 = v41;
  v41 += v63;
LABEL_128:
  v64 = (char **)((char *)this + 128);
  if ( v41 == v44 )
    goto LABEL_140;
LABEL_129:
  v65 = (_BYTE *)*((_QWORD *)a2 + 16);
  if ( !v65 || !*v65 )
  {
LABEL_140:
    if ( v64 )
      *v64 = 0;
    goto LABEL_142;
  }
  v66 = -1;
  do
    ++v66;
  while ( v65[v66] );
  v67 = v66 + 1;
  if ( v44 - v41 < (unsigned __int64)(v66 + 1) )
  {
    if ( v64 )
      *v64 = 0;
    v68 = (char **)((char *)this + 112);
    goto LABEL_143;
  }
  memcpy_s(v41, v44 - v41, v65, v66 + 1);
  if ( v64 )
    *v64 = v41;
  v41 += v67;
LABEL_142:
  v68 = (char **)((char *)this + 112);
  if ( v41 == v44 )
    goto LABEL_154;
LABEL_143:
  v69 = (_BYTE *)*((_QWORD *)a2 + 14);
  if ( !v69 || !*v69 )
  {
LABEL_154:
    if ( v68 )
      *v68 = 0;
    goto LABEL_156;
  }
  v70 = -1;
  do
    ++v70;
  while ( v69[v70] );
  v71 = v70 + 1;
  if ( v44 - v41 < (unsigned __int64)(v70 + 1) )
  {
    if ( v68 )
      *v68 = 0;
    v72 = (char **)((char *)this + 120);
    goto LABEL_157;
  }
  memcpy_s(v41, v44 - v41, v69, v70 + 1);
  if ( v68 )
    *v68 = v41;
  v41 += v71;
LABEL_156:
  v72 = (char **)((char *)this + 120);
  if ( v41 == v44 )
    goto LABEL_168;
LABEL_157:
  v73 = (_WORD *)*((_QWORD *)a2 + 15);
  if ( !v73 || !*v73 )
  {
LABEL_168:
    if ( v72 )
      *v72 = 0;
    goto LABEL_170;
  }
  v74 = -1;
  do
    ++v74;
  while ( v73[v74] );
  v75 = 2 * v74 + 2;
  if ( v44 - v41 < v75 )
  {
    if ( v72 )
      *v72 = 0;
    v76 = (char **)((char *)this + 88);
    goto LABEL_171;
  }
  memcpy_s(v41, v44 - v41, v73, 2 * v74 + 2);
  if ( v72 )
    *v72 = v41;
  v41 += v75;
LABEL_170:
  v76 = (char **)((char *)this + 88);
  if ( v41 == v44 )
    goto LABEL_182;
LABEL_171:
  v77 = (_BYTE *)*((_QWORD *)a2 + 11);
  if ( !v77 || !*v77 )
  {
LABEL_182:
    if ( v76 )
      *v76 = 0;
    goto LABEL_184;
  }
  v78 = -1;
  do
    ++v78;
  while ( v77[v78] );
  v79 = v78 + 1;
  if ( v44 - v41 < (unsigned __int64)(v78 + 1) )
  {
    if ( v76 )
      *v76 = 0;
    v80 = (char **)((char *)this + 96);
    goto LABEL_185;
  }
  memcpy_s(v41, v44 - v41, v77, v78 + 1);
  if ( v76 )
    *v76 = v41;
  v41 += v79;
LABEL_184:
  v80 = (char **)((char *)this + 96);
  if ( v41 == v44 )
    goto LABEL_192;
LABEL_185:
  v81 = (_WORD *)*((_QWORD *)a2 + 12);
  if ( !v81 || !*v81 )
    goto LABEL_192;
  do
    ++v2;
  while ( v81[v2] );
  v82 = 2 * v2 + 2;
  if ( v44 - v41 < v82 )
  {
LABEL_192:
    if ( v80 )
      *v80 = 0;
    goto LABEL_194;
  }
  memcpy_s(v41, v44 - v41, v81, v82);
  if ( v80 )
    *v80 = v41;
  v41 += v82;
LABEL_194:
  memset_0(v41, 0, v44 - v41);
}

```

## disassembly

```asm
0x180002d40  push    rbx
0x180002d42  push    rbp
0x180002d43  push    rsi
0x180002d44  push    rdi
0x180002d45  push    r12
0x180002d47  push    r13
0x180002d49  push    r14
0x180002d4b  push    r15
0x180002d4d  sub     rsp, 28h
0x180002d51  movups  xmm0, xmmword ptr [rdx]
0x180002d54  or      r15, 0FFFFFFFFFFFFFFFFh
0x180002d58  mov     rsi, rcx
0x180002d5b  mov     rbp, rdx
0x180002d5e  movups  xmmword ptr [rcx], xmm0
0x180002d61  movups  xmm1, xmmword ptr [rdx+10h]
0x180002d65  lea     ebx, [r15+3]
0x180002d69  movups  xmmword ptr [rcx+10h], xmm1
0x180002d6d  movups  xmm0, xmmword ptr [rdx+20h]
0x180002d71  movups  xmmword ptr [rcx+20h], xmm0
0x180002d75  movups  xmm1, xmmword ptr [rdx+30h]
0x180002d79  movups  xmmword ptr [rcx+30h], xmm1
0x180002d7d  movups  xmm0, xmmword ptr [rdx+40h]
0x180002d81  movups  xmmword ptr [rcx+40h], xmm0
0x180002d85  movups  xmm1, xmmword ptr [rdx+50h]
0x180002d89  movups  xmmword ptr [rcx+50h], xmm1
0x180002d8d  movups  xmm0, xmmword ptr [rdx+60h]
0x180002d91  movups  xmmword ptr [rcx+60h], xmm0
0x180002d95  movups  xmm1, xmmword ptr [rdx+70h]
0x180002d99  movups  xmmword ptr [rcx+70h], xmm1
0x180002d9d  movups  xmm0, xmmword ptr [rdx+80h]
0x180002da4  movups  xmmword ptr [rcx+80h], xmm0
0x180002dab  mov     rax, [rdx+90h]
0x180002db2  mov     [rcx+90h], rax
0x180002db9  mov     rcx, [rdx+18h]
0x180002dbd  xor     edx, edx
0x180002dbf  test    rcx, rcx
0x180002dc2  jnz     short loc_180002DC9
0x180002dc4  mov     r13d, ebx
0x180002dc7  jmp     short loc_180002DDD
0x180002dc9  mov     rax, r15
0x180002dcc  inc     rax
0x180002dcf  cmp     [rcx+rax*2], dx
0x180002dd3  jnz     short loc_180002DCC
0x180002dd5  lea     r13, ds:2[rax*2]
0x180002ddd  mov     rcx, [rbp+28h]
0x180002de1  test    rcx, rcx
0x180002de4  jnz     short loc_180002DEC
0x180002de6  lea     r12d, [rcx+1]
0x180002dea  jmp     short loc_180002DFB
0x180002dec  mov     rax, r15
0x180002def  inc     rax
0x180002df2  cmp     [rcx+rax], dl
0x180002df5  jnz     short loc_180002DEF
0x180002df7  lea     r12, [rax+1]
0x180002dfb  mov     rcx, [rbp+30h]
0x180002dff  test    rcx, rcx
0x180002e02  jnz     short loc_180002E0A
0x180002e04  lea     r14d, [rcx+1]
0x180002e08  jmp     short loc_180002E19
0x180002e0a  mov     rax, r15
0x180002e0d  inc     rax
0x180002e10  cmp     [rcx+rax], dl
0x180002e13  jnz     short loc_180002E0D
0x180002e15  lea     r14, [rax+1]
0x180002e19  mov     rcx, [rbp+38h]
0x180002e1d  test    rcx, rcx
0x180002e20  jnz     short loc_180002E27
0x180002e22  lea     edi, [rcx+1]
0x180002e25  jmp     short loc_180002E36
0x180002e27  mov     rax, r15
0x180002e2a  inc     rax
0x180002e2d  cmp     [rcx+rax], dl
0x180002e30  jnz     short loc_180002E2A
0x180002e32  lea     rdi, [rax+1]
0x180002e36  mov     rcx, [rbp+48h]
0x180002e3a  test    rcx, rcx
0x180002e3d  jnz     short loc_180002E45
0x180002e3f  lea     r11d, [rcx+1]
0x180002e43  jmp     short loc_180002E54
0x180002e45  mov     rax, r15
0x180002e48  inc     rax
0x180002e4b  cmp     [rcx+rax], dl
0x180002e4e  jnz     short loc_180002E48
0x180002e50  lea     r11, [rax+1]
0x180002e54  mov     rcx, [rbp+80h]
0x180002e5b  test    rcx, rcx
0x180002e5e  jnz     short loc_180002E66
0x180002e60  lea     r10d, [rcx+1]
0x180002e64  jmp     short loc_180002E75
0x180002e66  mov     rax, r15
0x180002e69  inc     rax
0x180002e6c  cmp     [rcx+rax], dl
0x180002e6f  jnz     short loc_180002E69
0x180002e71  lea     r10, [rax+1]
0x180002e75  mov     rcx, [rbp+70h]
0x180002e79  test    rcx, rcx
0x180002e7c  jnz     short loc_180002E84
0x180002e7e  lea     r9d, [rcx+1]
0x180002e82  jmp     short loc_180002E93
0x180002e84  mov     rax, r15
0x180002e87  inc     rax
0x180002e8a  cmp     [rcx+rax], dl
0x180002e8d  jnz     short loc_180002E87
0x180002e8f  lea     r9, [rax+1]
0x180002e93  mov     rcx, [rbp+78h]
0x180002e97  test    rcx, rcx
0x180002e9a  jnz     short loc_180002EA1
0x180002e9c  mov     r8, rbx
0x180002e9f  jmp     short loc_180002EB5
0x180002ea1  mov     rax, r15
0x180002ea4  inc     rax
0x180002ea7  cmp     [rcx+rax*2], dx
0x180002eab  jnz     short loc_180002EA4
0x180002ead  lea     r8, ds:2[rax*2]
0x180002eb5  mov     rcx, [rbp+58h]
0x180002eb9  test    rcx, rcx
0x180002ebc  jnz     short loc_180002EC3
0x180002ebe  lea     edx, [rcx+1]
0x180002ec1  jmp     short loc_180002ED2
0x180002ec3  mov     rax, r15
0x180002ec6  inc     rax
0x180002ec9  cmp     [rcx+rax], dl
0x180002ecc  jnz     short loc_180002EC6
0x180002ece  lea     rdx, [rax+1]
0x180002ed2  mov     rcx, [rbp+60h]
0x180002ed6  test    rcx, rcx
0x180002ed9  jz      short loc_180002EF1
0x180002edb  mov     rax, r15
0x180002ede  xor     ebx, ebx
0x180002ee0  inc     rax
0x180002ee3  cmp     [rcx+rax*2], bx
0x180002ee7  jnz     short loc_180002EE0
0x180002ee9  lea     rbx, ds:2[rax*2]
0x180002ef1  lea     rax, [rbx+rdx]
0x180002ef5  add     rax, r8
0x180002ef8  add     rax, r9
0x180002efb  add     rax, r10
0x180002efe  add     rax, r11
0x180002f01  add     rax, rdi
0x180002f04  lea     rdi, [rsi+98h]
0x180002f0b  mov     rcx, [rdi]
0x180002f0e  add     r14, rax
0x180002f11  add     r14, r12
0x180002f14  add     r14, r13
0x180002f17  xor     r13d, r13d
0x180002f1a  test    rcx, rcx
0x180002f1d  jz      short loc_180002F5C
0x180002f1f  cmp     dword ptr [rcx], 1
0x180002f22  jnz     short loc_180002F32
0x180002f24  cmp     [rsi+0A0h], r14
0x180002f2b  jnb     short loc_180002F67
0x180002f2d  test    rcx, rcx
0x180002f30  jz      short loc_180002F5C
0x180002f32  mov     eax, r15d
0x180002f35  lock xadd [rcx], eax
0x180002f39  add     eax, r15d
0x180002f3c  jnz     short loc_180002F55
0x180002f3e  mov     rbx, [rdi]
0x180002f41  call    cs:__imp_GetProcessHeap
0x180002f47  mov     r8, rbx; lpMem
0x180002f4a  xor     edx, edx; dwFlags
0x180002f4c  mov     rcx, rax; hHeap
0x180002f4f  call    cs:__imp_HeapFree
0x180002f55  mov     [rdi], r13
0x180002f58  mov     [rdi+8], r13
0x180002f5c  mov     rdx, r14; unsigned __int64
0x180002f5f  mov     rcx, rdi; this
0x180002f62  call    ?create@shared_buffer@details@wil@@QEAA_N_K@Z; wil::details::shared_buffer::create(unsigned __int64)
0x180002f67  mov     rax, [rdi]
0x180002f6a  lea     rcx, [rax+4]
0x180002f6e  neg     rax
0x180002f71  sbb     rbx, rbx
0x180002f74  and     rbx, rcx
0x180002f77  jz      loc_180003359
0x180002f7d  mov     rdx, [rdi+8]; DestinationSize
0x180002f81  lea     r14, [rsi+18h]
0x180002f85  lea     rdi, [rbx+rdx]
0x180002f89  cmp     rbx, rdi
0x180002f8c  jz      short loc_180002FDD
0x180002f8e  mov     r8, [rbp+18h]; Source
0x180002f92  test    r8, r8
0x180002f95  jz      short loc_180002FDD
0x180002f97  cmp     [r8], r13w
0x180002f9b  jz      short loc_180002FDD
0x180002f9d  mov     rax, r15
0x180002fa0  inc     rax
0x180002fa3  cmp     [r8+rax*2], r13w
0x180002fa8  jnz     short loc_180002FA0
0x180002faa  lea     r12, ds:2[rax*2]
0x180002fb2  cmp     rdx, r12
0x180002fb5  jnb     short loc_180002FC5
0x180002fb7  test    r14, r14
0x180002fba  jz      short loc_180002FBF
0x180002fbc  mov     [r14], r13
0x180002fbf  lea     r14, [rsi+28h]
0x180002fc3  jmp     short loc_180002FEE
0x180002fc5  mov     r9, r12; SourceSize
0x180002fc8  mov     rcx, rbx; Destination
0x180002fcb  call    memcpy_s
0x180002fd0  test    r14, r14
0x180002fd3  jz      short loc_180002FD8
0x180002fd5  mov     [r14], rbx
0x180002fd8  add     rbx, r12
0x180002fdb  jmp     short loc_180002FE5
0x180002fdd  test    r14, r14
0x180002fe0  jz      short loc_180002FE5
0x180002fe2  mov     [r14], r13
0x180002fe5  lea     r14, [rsi+28h]
0x180002fe9  cmp     rbx, rdi
0x180002fec  jz      short loc_18000303D
0x180002fee  mov     r8, [rbp+28h]; Source
0x180002ff2  test    r8, r8
0x180002ff5  jz      short loc_18000303D
0x180002ff7  cmp     [r8], r13b
0x180002ffa  jz      short loc_18000303D
0x180002ffc  mov     rax, r15
0x180002fff  inc     rax
0x180003002  cmp     [r8+rax], r13b
0x180003006  jnz     short loc_180002FFF
0x180003008  mov     rdx, rdi
0x18000300b  lea     r12, [rax+1]
0x18000300f  sub     rdx, rbx; DestinationSize
0x180003012  cmp     rdx, r12
0x180003015  jnb     short loc_180003025
0x180003017  test    r14, r14
0x18000301a  jz      short loc_18000301F
0x18000301c  mov     [r14], r13
0x18000301f  lea     r14, [rsi+30h]
0x180003023  jmp     short loc_18000304E
0x180003025  mov     r9, r12; SourceSize
0x180003028  mov     rcx, rbx; Destination
0x18000302b  call    memcpy_s
0x180003030  test    r14, r14
0x180003033  jz      short loc_180003038
0x180003035  mov     [r14], rbx
0x180003038  add     rbx, r12
0x18000303b  jmp     short loc_180003045
0x18000303d  test    r14, r14
0x180003040  jz      short loc_180003045
0x180003042  mov     [r14], r13
0x180003045  lea     r14, [rsi+30h]
0x180003049  cmp     rbx, rdi
0x18000304c  jz      short loc_18000309D
0x18000304e  mov     r8, [rbp+30h]; Source
0x180003052  test    r8, r8
0x180003055  jz      short loc_18000309D
0x180003057  cmp     [r8], r13b
0x18000305a  jz      short loc_18000309D
0x18000305c  mov     rax, r15
0x18000305f  inc     rax
0x180003062  cmp     [r8+rax], r13b
0x180003066  jnz     short loc_18000305F
0x180003068  mov     rdx, rdi
0x18000306b  lea     r12, [rax+1]
0x18000306f  sub     rdx, rbx; DestinationSize
0x180003072  cmp     rdx, r12
0x180003075  jnb     short loc_180003085
0x180003077  test    r14, r14
0x18000307a  jz      short loc_18000307F
0x18000307c  mov     [r14], r13
0x18000307f  lea     r14, [rsi+38h]
0x180003083  jmp     short loc_1800030AE
0x180003085  mov     r9, r12; SourceSize
0x180003088  mov     rcx, rbx; Destination
0x18000308b  call    memcpy_s
0x180003090  test    r14, r14
0x180003093  jz      short loc_180003098
0x180003095  mov     [r14], rbx
0x180003098  add     rbx, r12
0x18000309b  jmp     short loc_1800030A5
0x18000309d  test    r14, r14
0x1800030a0  jz      short loc_1800030A5
0x1800030a2  mov     [r14], r13
0x1800030a5  lea     r14, [rsi+38h]
0x1800030a9  cmp     rbx, rdi
0x1800030ac  jz      short loc_1800030FD
0x1800030ae  mov     r8, [rbp+38h]; Source
0x1800030b2  test    r8, r8
0x1800030b5  jz      short loc_1800030FD
0x1800030b7  cmp     [r8], r13b
0x1800030ba  jz      short loc_1800030FD
0x1800030bc  mov     rax, r15
0x1800030bf  inc     rax
0x1800030c2  cmp     [r8+rax], r13b
0x1800030c6  jnz     short loc_1800030BF
0x1800030c8  mov     rdx, rdi
0x1800030cb  lea     r12, [rax+1]
0x1800030cf  sub     rdx, rbx; DestinationSize
0x1800030d2  cmp     rdx, r12
0x1800030d5  jnb     short loc_1800030E5
0x1800030d7  test    r14, r14
0x1800030da  jz      short loc_1800030DF
0x1800030dc  mov     [r14], r13
0x1800030df  lea     r14, [rsi+48h]
0x1800030e3  jmp     short loc_18000310E
0x1800030e5  mov     r9, r12; SourceSize
0x1800030e8  mov     rcx, rbx; Destination
0x1800030eb  call    memcpy_s
0x1800030f0  test    r14, r14
0x1800030f3  jz      short loc_1800030F8
  ... truncated ...
```
