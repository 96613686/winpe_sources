# SXWriter::getUnitokenFromNames(wchar_t const *,int,wchar_t const *,int,wchar_t const *,int,ulong *,Unitoken *)

- ea: `0x100409da0`
- end: `0x10040a3b4`
- name: `?getUnitokenFromNames@SXWriter@@AEAAXPEB_WH0H0HPEAKPEAVUnitoken@@@Z`
- size: `1556`
- prototype: `void __usercall(SXWriter *__hidden this@<rcx>, const wchar_t *@<rdx>, int@<r8d>, const wchar_t *@<r9>, int, const wchar_t *, int, unsigned int *, struct Unitoken *)`
- caller_count: `5`
- callee_count: `11`
- tags: ``

## callers

- `0x100409320`
- `0x1004098d0`
- `0x10040aab0`
- `0x10040ace0`
- `0x10040af70`

## callees

- `0x100401350`
- `0x100406550`
- `0x1004086f0`
- `0x100409840`
- `0x100409da0`
- `0x10040a3c0`
- `0x10040a470`
- `0x100412e30`
- `0x100413250`
- `0x100413590`
- `0x10041b390`

## pseudocode

```c
void __fastcall SXWriter::getUnitokenFromNames(
        SXWriter *this,
        wchar_t *a2,
        int a3,
        wchar_t *a4,
        unsigned int a5,
        wchar_t *a6,
        unsigned int a7,
        unsigned int *a8,
        struct Unitoken *a9)
{
  unsigned int v9; // r14d
  size_t v10; // r13
  wchar_t *v12; // r10
  unsigned int v13; // esi
  const wchar_t *v14; // r11
  int v15; // eax
  size_t v16; // r12
  wchar_t *v17; // rdx
  unsigned int v18; // ebp
  const wchar_t *v19; // r8
  int v20; // eax
  size_t v21; // r15
  wchar_t *v22; // rdx
  const wchar_t *v23; // r8
  int v24; // eax
  __int64 v25; // r10
  __int64 v26; // r9
  __int64 v27; // r8
  __int64 v28; // rbx
  int v29; // eax
  unsigned int v30; // esi
  __int64 v31; // rdx
  struct CStringPtr *v32; // rdx
  wchar_t *v33; // rdx
  __int64 v34; // rdx
  struct CStringPtr *v35; // rdx
  struct Unitoken *v36; // rbx
  __int64 v37; // rdx
  struct CStringPtr *v38; // rdx
  __int64 v39; // rdx
  struct CStringPtr *v40; // rdx
  struct Unitoken *v41; // r14
  unsigned int v42; // ebp
  __int64 v43; // rdx
  unsigned int v44; // r15d
  RStringPtr *v45; // rcx
  __int64 v46; // rdx
  __int64 v47; // r13
  unsigned int *v48; // rbx
  __int64 v49; // rax
  unsigned int v50; // ebx
  unsigned int v51; // r10d
  wchar_t *v52; // r11
  __int64 v53; // rax
  int v54; // r12d
  __int64 v55; // rax
  int v56; // r14d
  __int64 v57; // r8
  __int64 v58; // r9
  __int64 v59; // rdx
  __int64 v60; // rax
  _BYTE *v61; // rax
  int v62; // [rsp+28h] [rbp-60h]
  int v63; // [rsp+28h] [rbp-60h]
  unsigned int v64; // [rsp+30h] [rbp-58h]
  __int64 v65; // [rsp+38h] [rbp-50h]
  __int64 v66; // [rsp+90h] [rbp+8h] BYREF
  wchar_t *String2; // [rsp+98h] [rbp+10h]
  unsigned int v68; // [rsp+A0h] [rbp+18h] BYREF
  wchar_t *Src; // [rsp+A8h] [rbp+20h]

  Src = a4;
  String2 = a2;
  v9 = 0;
  v10 = a3;
  v12 = a2;
  v13 = 0;
  v14 = &a2[a3];
  if ( a2 < v14 )
  {
    do
    {
      v15 = *v12++;
      v13 = v15 + 16 * v13;
      if ( (v13 & 0xF0000000) != 0 )
        v13 ^= v13 & 0xF0000000 ^ ((v13 & 0xF0000000) >> 24);
    }
    while ( v12 < v14 );
  }
  v16 = (int)a5;
  v17 = a4;
  v18 = 0;
  v19 = &a4[a5];
  if ( a4 < v19 )
  {
    do
    {
      v20 = *v17++;
      v18 = v20 + 16 * v18;
      if ( (v18 & 0xF0000000) != 0 )
        v18 ^= v18 & 0xF0000000 ^ ((v18 & 0xF0000000) >> 24);
    }
    while ( v17 < v19 );
  }
  v21 = (int)a7;
  v22 = a6;
  v23 = &a6[a7];
  if ( a6 < v23 )
  {
    do
    {
      v24 = *v22++;
      v9 = v24 + 16 * v9;
      if ( (v9 & 0xF0000000) != 0 )
        v9 ^= v9 & 0xF0000000 ^ ((v9 & 0xF0000000) >> 24);
    }
    while ( v22 < v23 );
  }
  v25 = *((_QWORD *)this + 10);
  v66 = v25;
  v26 = *(unsigned int *)(v25 + 156);
  v27 = *(_QWORD *)(v25 + 144);
  v64 = v13 + v9 + HIWORD(v18) + (v18 << 16);
  v65 = v27 + 56 * v26;
  v28 = v27 + 56LL * (v64 % ((int)v26 - 1));
  v29 = *(_DWORD *)(v28 + 16);
  if ( v29 == -1 )
    goto LABEL_24;
  while ( 1 )
  {
    if ( v29 != (_DWORD)v10 || *(_DWORD *)(v28 + 32) != (_DWORD)v16 || *(_DWORD *)(v28 + 48) != (_DWORD)v21 )
      goto LABEL_21;
    if ( !wcsncmp(*(const wchar_t **)(v28 + 8), String2, v10)
      && !wcsncmp(*(const wchar_t **)(v28 + 24), Src, v16)
      && !wcsncmp(*(const wchar_t **)(v28 + 40), a6, v21) )
    {
      break;
    }
    v25 = v66;
LABEL_21:
    v28 += 56;
    if ( v28 == v65 )
      v28 = *(_QWORD *)(v25 + 144);
    v29 = *(_DWORD *)(v28 + 16);
    if ( v29 == -1 )
      goto LABEL_24;
  }
  if ( !v28 )
  {
LABEL_24:
    if ( *(_DWORD *)(*((_QWORD *)this + 10) + 116LL) < 0x270Fu )
      goto LABEL_26;
    do
    {
      SXWriter::MakeNewTokenTable(this);
LABEL_26:
      ;
    }
    while ( (unsigned int)SXWriter::getOrWriteToken(this, String2, v10, &a7)
         || (unsigned int)SXWriter::getOrWriteToken(this, Src, v16, &v68)
         || (unsigned int)SXWriter::getOrWriteToken(this, a6, v21, (unsigned int *)&v66) );
    v30 = a7;
    v31 = *((_QWORD *)this + 10);
    if ( a7 )
    {
      if ( a7 >= *(_DWORD *)(v31 + 36) )
        goto LABEL_67;
      _mm_lfence();
      v30 = a7;
      v32 = *(struct CStringPtr **)(*(_QWORD *)(v31 + 40) + 8LL * a7);
    }
    else
    {
      v32 = (struct CStringPtr *)rspNull;
    }
    v41 = a9;
    RStringPtr::assign(a9, v32);
    v42 = v68;
    v43 = *((_QWORD *)this + 10);
    if ( v68 )
    {
      if ( v68 >= *(_DWORD *)(v43 + 36) )
        goto LABEL_67;
      _mm_lfence();
      v42 = v68;
      RStringPtr::assign(
        (struct Unitoken *)((char *)v41 + 8),
        *(struct CStringPtr **)(*(_QWORD *)(v43 + 40) + 8LL * v68));
      v30 = a7;
    }
    else
    {
      RStringPtr::assign((struct Unitoken *)((char *)v41 + 8), rspNull);
    }
    v44 = v66;
    v45 = (struct Unitoken *)((char *)v41 + 16);
    v46 = *((_QWORD *)this + 10);
    if ( (_DWORD)v66 )
    {
      if ( (unsigned int)v66 >= *(_DWORD *)(v46 + 36) )
        goto LABEL_67;
      _mm_lfence();
      v44 = v66;
      RStringPtr::assign(v45, *(struct CStringPtr **)(*(_QWORD *)(v46 + 40) + 8LL * (unsigned int)v66));
      v30 = a7;
      v42 = v68;
    }
    else
    {
      RStringPtr::assign(v45, rspNull);
    }
    v47 = *((_QWORD *)this + 10);
    v48 = a8;
    SXTokenTable::putUnitokenData((SXTokenTable *)v47, v41, a8);
    v49 = *((_QWORD *)v41 + 2);
    v50 = *v48;
    v51 = *(_DWORD *)(v49 + 16);
    v52 = (wchar_t *)(v49 + 24);
    v53 = *((_QWORD *)v41 + 1);
    a5 = v51;
    String2 = v52;
    v54 = *(_DWORD *)(v53 + 16);
    a6 = (wchar_t *)(v53 + 24);
    v55 = *(_QWORD *)v41;
    v56 = *(_DWORD *)(*(_QWORD *)v41 + 16LL);
    Src = (wchar_t *)(v55 + 24);
    if ( *(_DWORD *)(v47 + 160) == *(_DWORD *)(v47 + 152) )
    {
      _htableutsx::grow((_htableutsx *)(v47 + 128));
      v51 = a5;
      v52 = String2;
    }
    v57 = *(unsigned int *)(v47 + 156);
    v58 = *(_QWORD *)(v47 + 144);
    v59 = v58 + 56LL * (v64 % ((int)v57 - 1));
    while ( *(_DWORD *)(v59 + 16) != -1 )
    {
      v60 = v59 + 56;
      v59 = *(_QWORD *)(v47 + 144);
      if ( v60 != v58 + 56 * v57 )
        v59 = v60;
    }
    *(_QWORD *)(v59 + 8) = Src;
    *(_QWORD *)(v59 + 24) = a6;
    *(_DWORD *)(v59 + 52) = v64;
    *(_DWORD *)v59 = v50;
    *(_DWORD *)(v59 + 16) = v56;
    *(_DWORD *)(v59 + 32) = v54;
    *(_QWORD *)(v59 + 40) = v52;
    *(_DWORD *)(v59 + 48) = v51;
    ++*(_DWORD *)(v47 + 152);
    v61 = (_BYTE *)*((_QWORD *)this + 38);
    if ( v61 == *((_BYTE **)this + 39) )
    {
      SXWriter::writeBuffer(this);
      v61 = (_BYTE *)*((_QWORD *)this + 38);
    }
    *v61 = -17;
    ++*((_QWORD *)this + 38);
    SXWriter::WriteMb32(this, v30);
    SXWriter::WriteMb32(this, v42);
    SXWriter::WriteMb32(this, v44);
    return;
  }
  v33 = String2;
  *a8 = *(_DWORD *)v28;
  if ( (unsigned int)SXTokenTable::getTokenFromNameAndHash(*((_QWORD *)this + 10), v33, (unsigned int)v10, v13, &a5, 0) != 1 )
    goto LABEL_67;
  v34 = *((_QWORD *)this + 10);
  if ( !a5 )
  {
    v35 = (struct CStringPtr *)rspNull;
    goto LABEL_37;
  }
  if ( a5 >= *(_DWORD *)(v34 + 36) )
    goto LABEL_67;
  _mm_lfence();
  v35 = *(struct CStringPtr **)(*(_QWORD *)(v34 + 40) + 8LL * a5);
LABEL_37:
  v36 = a9;
  RStringPtr::assign(a9, v35);
  LOBYTE(v62) = 0;
  if ( (unsigned int)SXTokenTable::getTokenFromNameAndHash(
                       *((_QWORD *)this + 10),
                       Src,
                       (unsigned int)v16,
                       v18,
                       &a5,
                       v62) != 1 )
    goto LABEL_67;
  v37 = *((_QWORD *)this + 10);
  if ( !a5 )
  {
    v38 = (struct CStringPtr *)rspNull;
    goto LABEL_42;
  }
  if ( a5 >= *(_DWORD *)(v37 + 36) )
    goto LABEL_67;
  _mm_lfence();
  v38 = *(struct CStringPtr **)(*(_QWORD *)(v37 + 40) + 8LL * a5);
LABEL_42:
  RStringPtr::assign((struct Unitoken *)((char *)v36 + 8), v38);
  LOBYTE(v63) = 0;
  if ( (unsigned int)SXTokenTable::getTokenFromNameAndHash(*((_QWORD *)this + 10), a6, (unsigned int)v21, v9, &a5, v63) != 1 )
    goto LABEL_67;
  v39 = *((_QWORD *)this + 10);
  if ( !a5 )
  {
    v40 = (struct CStringPtr *)rspNull;
    goto LABEL_45;
  }
  if ( a5 >= *(_DWORD *)(v39 + 36) )
  {
LABEL_67:
    MXRRaiseException(-2147467259);
    JUMPOUT(0x10040A3B3LL);
  }
  _mm_lfence();
  v40 = *(struct CStringPtr **)(*(_QWORD *)(v39 + 40) + 8LL * a5);
LABEL_45:
  RStringPtr::assign((struct Unitoken *)((char *)v36 + 16), v40);
}

```

## disassembly

```asm
0x100409da0  mov     [rsp+Src], r9
0x100409da5  mov     [rsp+String2], rdx
0x100409daa  push    rbx
0x100409dab  push    rbp
0x100409dac  push    rsi
0x100409dad  push    rdi
0x100409dae  push    r12
0x100409db0  push    r13
0x100409db2  push    r14
0x100409db4  push    r15
0x100409db6  sub     rsp, 48h
0x100409dba  xor     r14d, r14d
0x100409dbd  movsxd  r13, r8d
0x100409dc0  mov     eax, r13d
0x100409dc3  mov     rdi, rcx
0x100409dc6  mov     r10, rdx
0x100409dc9  mov     esi, r14d
0x100409dcc  lea     r11, [rdx+rax*2]
0x100409dd0  cmp     rdx, r11
0x100409dd3  jnb     short loc_100409E05
0x100409dd5  nop     word ptr [rax+rax+00000000h]
0x100409de0  movzx   eax, word ptr [r10]
0x100409de4  add     r10, 2
0x100409de8  shl     esi, 4
0x100409deb  add     esi, eax
0x100409ded  mov     ecx, esi
0x100409def  and     ecx, 0F0000000h
0x100409df5  jz      short loc_100409E00
0x100409df7  mov     eax, ecx
0x100409df9  shr     eax, 18h
0x100409dfc  xor     eax, ecx
0x100409dfe  xor     esi, eax
0x100409e00  cmp     r10, r11
0x100409e03  jb      short loc_100409DE0
0x100409e05  movsxd  r12, [rsp+88h+arg_20]
0x100409e0d  mov     rdx, r9
0x100409e10  mov     eax, r12d
0x100409e13  mov     ebp, r14d
0x100409e16  lea     r8, [r9+rax*2]
0x100409e1a  cmp     r9, r8
0x100409e1d  jnb     short loc_100409E44
0x100409e1f  nop
0x100409e20  movzx   eax, word ptr [rdx]
0x100409e23  add     rdx, 2
0x100409e27  shl     ebp, 4
0x100409e2a  add     ebp, eax
0x100409e2c  mov     ecx, ebp
0x100409e2e  and     ecx, 0F0000000h
0x100409e34  jz      short loc_100409E3F
0x100409e36  mov     eax, ecx
0x100409e38  shr     eax, 18h
0x100409e3b  xor     eax, ecx
0x100409e3d  xor     ebp, eax
0x100409e3f  cmp     rdx, r8
0x100409e42  jb      short loc_100409E20
0x100409e44  mov     rcx, [rsp+88h+arg_28]
0x100409e4c  movsxd  r15, [rsp+88h+arg_30]
0x100409e54  mov     rdx, rcx
0x100409e57  mov     eax, r15d
0x100409e5a  lea     r8, [rcx+rax*2]
0x100409e5e  cmp     rcx, r8
0x100409e61  jnb     short loc_100409E98
0x100409e63  nop     dword ptr [rax+00h]
0x100409e67  nop     word ptr [rax+rax+00000000h]
0x100409e70  movzx   eax, word ptr [rdx]
0x100409e73  add     rdx, 2
0x100409e77  shl     r14d, 4
0x100409e7b  add     r14d, eax
0x100409e7e  mov     ecx, r14d
0x100409e81  and     ecx, 0F0000000h
0x100409e87  jz      short loc_100409E93
0x100409e89  mov     eax, ecx
0x100409e8b  shr     eax, 18h
0x100409e8e  xor     eax, ecx
0x100409e90  xor     r14d, eax
0x100409e93  cmp     rdx, r8
0x100409e96  jb      short loc_100409E70
0x100409e98  mov     r10, [rdi+50h]
0x100409e9c  mov     eax, ebp
0x100409e9e  shr     eax, 10h
0x100409ea1  xor     edx, edx
0x100409ea3  add     eax, r14d
0x100409ea6  mov     [rsp+88h+arg_0], r10
0x100409eae  mov     r11d, ebp
0x100409eb1  mov     r9d, [r10+9Ch]
0x100409eb8  mov     r8, [r10+90h]
0x100409ebf  shl     r11d, 10h
0x100409ec3  add     r11d, eax
0x100409ec6  add     r11d, esi
0x100409ec9  lea     ecx, [r9-1]
0x100409ecd  mov     eax, r11d
0x100409ed0  mov     [rsp+88h+var_58], r11d
0x100409ed5  div     ecx
0x100409ed7  imul    rax, r9, 38h ; '8'
0x100409edb  mov     ecx, edx
0x100409edd  add     rax, r8
0x100409ee0  imul    rbx, rcx, 38h ; '8'
0x100409ee4  mov     [rsp+88h+var_50], rax
0x100409ee9  add     rbx, r8
0x100409eec  mov     eax, [rbx+10h]
0x100409eef  cmp     eax, 0FFFFFFFFh
0x100409ef2  jz      short loc_100409F73
0x100409ef4  cmp     eax, r13d
0x100409ef7  jnz     short loc_100409F59
0x100409ef9  cmp     [rbx+20h], r12d
0x100409efd  jnz     short loc_100409F59
0x100409eff  cmp     [rbx+30h], r15d
0x100409f03  jnz     short loc_100409F59
0x100409f05  mov     rdx, [rsp+88h+String2]; String2
0x100409f0d  mov     r8, r13; MaxCount
0x100409f10  mov     rcx, [rbx+8]; String1
0x100409f14  call    wcsncmp
0x100409f19  test    eax, eax
0x100409f1b  jnz     short loc_100409F51
0x100409f1d  mov     rdx, [rsp+88h+Src]; String2
0x100409f25  mov     r8, r12; MaxCount
0x100409f28  mov     rcx, [rbx+18h]; String1
0x100409f2c  call    wcsncmp
0x100409f31  test    eax, eax
0x100409f33  jnz     short loc_100409F51
0x100409f35  mov     rdx, [rsp+88h+arg_28]; String2
0x100409f3d  mov     r8, r15; MaxCount
0x100409f40  mov     rcx, [rbx+28h]; String1
0x100409f44  call    wcsncmp
0x100409f49  test    eax, eax
0x100409f4b  jz      loc_10040A00C
0x100409f51  mov     r10, [rsp+88h+arg_0]
0x100409f59  add     rbx, 38h ; '8'
0x100409f5d  cmp     rbx, [rsp+88h+var_50]
0x100409f62  jnz     short loc_100409F6B
0x100409f64  mov     rbx, [r10+90h]
0x100409f6b  mov     eax, [rbx+10h]
0x100409f6e  cmp     eax, 0FFFFFFFFh
0x100409f71  jnz     short loc_100409EF4
0x100409f73  mov     rax, [rdi+50h]
0x100409f77  cmp     dword ptr [rax+74h], 270Fh
0x100409f7e  jb      short loc_100409F90
0x100409f80  mov     rcx, rdi; this
0x100409f83  call    ?MakeNewTokenTable@SXWriter@@AEAAXXZ; SXWriter::MakeNewTokenTable(void)
0x100409f88  nop     dword ptr [rax+rax+00000000h]
0x100409f90  mov     rdx, [rsp+88h+String2]; Src
0x100409f98  lea     r9, [rsp+88h+arg_30]; unsigned int *
0x100409fa0  mov     r8d, r13d; unsigned int
0x100409fa3  mov     rcx, rdi; this
0x100409fa6  call    ?getOrWriteToken@SXWriter@@AEAAHPEB_WKPEAK@Z; SXWriter::getOrWriteToken(wchar_t const *,ulong,ulong *)
0x100409fab  test    eax, eax
0x100409fad  jnz     short loc_100409F80
0x100409faf  mov     rdx, [rsp+88h+Src]; Src
0x100409fb7  lea     r9, [rsp+88h+arg_10]; unsigned int *
0x100409fbf  mov     r8d, r12d; unsigned int
0x100409fc2  mov     rcx, rdi; this
0x100409fc5  call    ?getOrWriteToken@SXWriter@@AEAAHPEB_WKPEAK@Z; SXWriter::getOrWriteToken(wchar_t const *,ulong,ulong *)
0x100409fca  test    eax, eax
0x100409fcc  jnz     short loc_100409F80
0x100409fce  mov     rdx, [rsp+88h+arg_28]; Src
0x100409fd6  lea     r9, [rsp+88h+arg_0]; unsigned int *
0x100409fde  mov     r8d, r15d; unsigned int
0x100409fe1  mov     rcx, rdi; this
0x100409fe4  call    ?getOrWriteToken@SXWriter@@AEAAHPEB_WKPEAK@Z; SXWriter::getOrWriteToken(wchar_t const *,ulong,ulong *)
0x100409fe9  test    eax, eax
0x100409feb  jnz     short loc_100409F80
0x100409fed  mov     esi, [rsp+88h+arg_30]
0x100409ff4  mov     rdx, [rdi+50h]
0x100409ff8  test    esi, esi
0x100409ffa  jnz     loc_10040A183
0x10040a000  mov     rdx, cs:?rspNull@@3VRStringPtr@@A; RStringPtr rspNull
0x10040a007  jmp     loc_10040A19E
0x10040a00c  test    rbx, rbx
0x10040a00f  jz      loc_100409F73
0x10040a015  mov     ecx, [rbx]
0x10040a017  mov     r9d, esi
0x10040a01a  mov     rax, [rsp+88h+arg_38]
0x10040a022  mov     r8d, r13d
0x10040a025  mov     rdx, [rsp+88h+String2]
0x10040a02d  mov     [rsp+88h+var_60], 0
0x10040a032  mov     [rax], ecx
0x10040a034  lea     rax, [rsp+88h+arg_20]
0x10040a03c  mov     rcx, [rdi+50h]
0x10040a040  mov     [rsp+88h+var_68], rax
0x10040a045  call    ?getTokenFromNameAndHash@SXTokenTable@@QEAA?AW4TokenSearchResult@@PEB_WKKPEAK_N@Z; SXTokenTable::getTokenFromNameAndHash(wchar_t const *,ulong,ulong,ulong *,bool)
0x10040a04a  cmp     eax, 1
0x10040a04d  jnz     loc_10040A3A9
0x10040a053  mov     eax, [rsp+88h+arg_20]
0x10040a05a  mov     rdx, [rdi+50h]
0x10040a05e  test    eax, eax
0x10040a060  jnz     short loc_10040A06B
0x10040a062  mov     rdx, cs:?rspNull@@3VRStringPtr@@A; RStringPtr rspNull
0x10040a069  jmp     short loc_10040A086
0x10040a06b  cmp     eax, [rdx+24h]
0x10040a06e  jnb     loc_10040A3A9
0x10040a074  lfence
0x10040a077  mov     eax, [rsp+88h+arg_20]
0x10040a07e  mov     rdx, [rdx+28h]
0x10040a082  mov     rdx, [rdx+rax*8]; struct CStringPtr *
0x10040a086  mov     rbx, [rsp+88h+arg_40]
0x10040a08e  mov     rcx, rbx; this
0x10040a091  call    ?assign@RStringPtr@@QEAAXPEAVCStringPtr@@@Z; RStringPtr::assign(CStringPtr *)
0x10040a096  mov     rdx, [rsp+88h+Src]
0x10040a09e  lea     rax, [rsp+88h+arg_20]
0x10040a0a6  mov     rcx, [rdi+50h]
0x10040a0aa  mov     r9d, ebp
0x10040a0ad  mov     [rsp+88h+var_60], 0
0x10040a0b2  mov     r8d, r12d
0x10040a0b5  mov     [rsp+88h+var_68], rax
0x10040a0ba  call    ?getTokenFromNameAndHash@SXTokenTable@@QEAA?AW4TokenSearchResult@@PEB_WKKPEAK_N@Z; SXTokenTable::getTokenFromNameAndHash(wchar_t const *,ulong,ulong,ulong *,bool)
0x10040a0bf  cmp     eax, 1
0x10040a0c2  jnz     loc_10040A3A9
0x10040a0c8  mov     eax, [rsp+88h+arg_20]
0x10040a0cf  lea     rcx, [rbx+8]; this
0x10040a0d3  mov     rdx, [rdi+50h]
0x10040a0d7  test    eax, eax
0x10040a0d9  jnz     short loc_10040A0E4
0x10040a0db  mov     rdx, cs:?rspNull@@3VRStringPtr@@A; RStringPtr rspNull
0x10040a0e2  jmp     short loc_10040A0FF
0x10040a0e4  cmp     eax, [rdx+24h]
0x10040a0e7  jnb     loc_10040A3A9
0x10040a0ed  lfence
0x10040a0f0  mov     eax, [rsp+88h+arg_20]
0x10040a0f7  mov     rdx, [rdx+28h]
0x10040a0fb  mov     rdx, [rdx+rax*8]; struct CStringPtr *
0x10040a0ff  call    ?assign@RStringPtr@@QEAAXPEAVCStringPtr@@@Z; RStringPtr::assign(CStringPtr *)
0x10040a104  mov     rdx, [rsp+88h+arg_28]
0x10040a10c  lea     rax, [rsp+88h+arg_20]
0x10040a114  mov     rcx, [rdi+50h]
0x10040a118  mov     r9d, r14d
0x10040a11b  mov     [rsp+88h+var_60], 0
0x10040a120  mov     r8d, r15d
0x10040a123  mov     [rsp+88h+var_68], rax
0x10040a128  call    ?getTokenFromNameAndHash@SXTokenTable@@QEAA?AW4TokenSearchResult@@PEB_WKKPEAK_N@Z; SXTokenTable::getTokenFromNameAndHash(wchar_t const *,ulong,ulong,ulong *,bool)
0x10040a12d  cmp     eax, 1
0x10040a130  jnz     loc_10040A3A9
0x10040a136  mov     eax, [rsp+88h+arg_20]
0x10040a13d  lea     rcx, [rbx+10h]; this
0x10040a141  mov     rdx, [rdi+50h]
0x10040a145  test    eax, eax
0x10040a147  jnz     short loc_10040A166
0x10040a149  mov     rdx, cs:?rspNull@@3VRStringPtr@@A; struct CStringPtr *
0x10040a150  call    ?assign@RStringPtr@@QEAAXPEAVCStringPtr@@@Z; RStringPtr::assign(CStringPtr *)
0x10040a155  add     rsp, 48h
0x10040a159  pop     r15
0x10040a15b  pop     r14
0x10040a15d  pop     r13
0x10040a15f  pop     r12
0x10040a161  pop     rdi
0x10040a162  pop     rsi
0x10040a163  pop     rbp
0x10040a164  pop     rbx
0x10040a165  retn
0x10040a166  cmp     eax, [rdx+24h]
0x10040a169  jnb     loc_10040A3A9
0x10040a16f  lfence
0x10040a172  mov     eax, [rsp+88h+arg_20]
0x10040a179  mov     rdx, [rdx+28h]
0x10040a17d  mov     rdx, [rdx+rax*8]
0x10040a181  jmp     short loc_10040A150
0x10040a183  cmp     esi, [rdx+24h]
0x10040a186  jnb     loc_10040A3A9
0x10040a18c  lfence
0x10040a18f  mov     esi, [rsp+88h+arg_30]
0x10040a196  mov     rdx, [rdx+28h]
0x10040a19a  mov     rdx, [rdx+rsi*8]; struct CStringPtr *
0x10040a19e  mov     r14, [rsp+88h+arg_40]
0x10040a1a6  mov     rcx, r14; this
0x10040a1a9  call    ?assign@RStringPtr@@QEAAXPEAVCStringPtr@@@Z; RStringPtr::assign(CStringPtr *)
0x10040a1ae  mov     ebp, [rsp+88h+arg_10]
0x10040a1b5  mov     rdx, [rdi+50h]
0x10040a1b9  test    ebp, ebp
0x10040a1bb  jnz     short loc_10040A1CF
0x10040a1bd  mov     rdx, cs:?rspNull@@3VRStringPtr@@A; struct CStringPtr *
0x10040a1c4  lea     rcx, [r14+8]; this
0x10040a1c8  call    ?assign@RStringPtr@@QEAAXPEAVCStringPtr@@@Z; RStringPtr::assign(CStringPtr *)
0x10040a1cd  jmp     short loc_10040A1FA
0x10040a1cf  cmp     ebp, [rdx+24h]
0x10040a1d2  jnb     loc_10040A3A9
0x10040a1d8  lfence
0x10040a1db  mov     rdx, [rdx+28h]
0x10040a1df  lea     rcx, [r14+8]; this
0x10040a1e3  mov     ebp, [rsp+88h+arg_10]
0x10040a1ea  mov     rdx, [rdx+rbp*8]; struct CStringPtr *
0x10040a1ee  call    ?assign@RStringPtr@@QEAAXPEAVCStringPtr@@@Z; RStringPtr::assign(CStringPtr *)
0x10040a1f3  mov     esi, [rsp+88h+arg_30]
0x10040a1fa  mov     r15d, dword ptr [rsp+88h+arg_0]
0x10040a202  lea     rcx, [r14+10h]; this
0x10040a206  mov     rdx, [rdi+50h]
0x10040a20a  test    r15d, r15d
0x10040a20d  jnz     short loc_10040A21D
0x10040a20f  mov     rdx, cs:?rspNull@@3VRStringPtr@@A; struct CStringPtr *
0x10040a216  call    ?assign@RStringPtr@@QEAAXPEAVCStringPtr@@@Z; RStringPtr::assign(CStringPtr *)
0x10040a21b  jmp     short loc_10040A24D
0x10040a21d  cmp     r15d, [rdx+24h]
0x10040a221  jnb     loc_10040A3A9
0x10040a227  lfence
0x10040a22a  mov     rdx, [rdx+28h]
0x10040a22e  mov     r15d, dword ptr [rsp+88h+arg_0]
0x10040a236  mov     rdx, [rdx+r15*8]; struct CStringPtr *
0x10040a23a  call    ?assign@RStringPtr@@QEAAXPEAVCStringPtr@@@Z; RStringPtr::assign(CStringPtr *)
0x10040a23f  mov     esi, [rsp+88h+arg_30]
0x10040a246  mov     ebp, [rsp+88h+arg_10]
0x10040a24d  mov     r13, [rdi+50h]
0x10040a251  mov     rdx, r14; struct Unitoken *
  ... truncated ...
```
