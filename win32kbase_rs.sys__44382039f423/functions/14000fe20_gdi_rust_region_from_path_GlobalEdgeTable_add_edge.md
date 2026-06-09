# gdi_rust::region::from_path::GlobalEdgeTable::add_edge

- ea: `0x14000fe20`
- end: `0x1400101e8`
- name: `gdi_rust::region::from_path::GlobalEdgeTable::add_edge`
- size: `968`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x1400101f0`

## callees

- `0x14000fe20`
- `0x140017a10`
- `0x140017b00`
- `0x140018450`
- `0x140018780`
- `0x1400189a0`

## pseudocode

```c
__int64 __fastcall gdi_rust::region::from_path::GlobalEdgeTable::add_edge(_QWORD *a1, int *a2, int *a3, __int64 a4)
{
  int v4; // r10d
  int v5; // esi
  unsigned int v6; // edi
  char v7; // r15
  int v8; // r11d
  int *v9; // rax
  int v10; // r10d
  int v11; // edx
  int v12; // ebx
  int v13; // r8d
  __int64 result; // rax
  int v15; // r14d
  bool v16; // cc
  bool v17; // bp
  unsigned __int64 v18; // r8
  unsigned __int64 v19; // r14
  __int64 v20; // r14
  __int64 v21; // r12
  unsigned int v22; // r8d
  __int64 v23; // r13
  int v24; // esi
  unsigned int v25; // eax
  __int64 v26; // rdi
  int v27; // r8d
  int v28; // r9d
  int v29; // r10d
  __int64 v30; // r11
  __int64 v31; // r13
  int v32; // r8d
  int v33; // eax
  int v34; // r10d
  bool v35; // sf
  __int64 v36; // r13
  int v37; // r8d
  __int64 v38; // r9
  __int64 v39; // r13
  int v40; // r10d
  bool v41; // sf
  __int64 v42; // r13
  int v43; // r8d
  __int64 v44; // r9
  unsigned __int64 v45; // rbx
  unsigned __int64 v46; // r15
  __int64 v47; // r14
  _DWORD *v48; // rax
  __int64 v49; // rbp
  bool v50; // zf
  __int64 v51; // rdx
  unsigned __int64 v52; // r13
  __int64 v53; // r15
  _QWORD *v54; // rax
  __int64 v55; // rcx
  __int64 v56; // r8
  __int64 *v57; // rax
  __int64 v58; // [rsp+0h] [rbp-B8h] BYREF
  char v59; // [rsp+36h] [rbp-82h]
  char v60; // [rsp+37h] [rbp-81h]
  _QWORD *v61; // [rsp+38h] [rbp-80h]
  unsigned __int64 v62; // [rsp+40h] [rbp-78h]
  __int64 v63; // [rsp+48h] [rbp-70h]
  __int64 v64; // [rsp+50h] [rbp-68h]
  int v65; // [rsp+58h] [rbp-60h] BYREF
  __int64 v66; // [rsp+60h] [rbp-58h]
  __int64 v67; // [rsp+70h] [rbp-48h]

  v4 = a3[1];
  v5 = a2[1];
  v6 = v4 - v5;
  if ( v4 >= v5 )
  {
    v7 = 1;
    v8 = a2[1];
    v9 = a3;
    a3 = a2;
    v5 = v4;
  }
  else
  {
    v6 = v5 - v4;
    v7 = -1;
    v8 = a3[1];
    v9 = a2;
  }
  v10 = *a3;
  v11 = *v9;
  v12 = 0;
  if ( a4 )
  {
    v13 = *(_DWORD *)(a4 + 4);
    result = 0;
    if ( v5 < v13 )
      goto LABEL_61;
    v15 = *(_DWORD *)(a4 + 12);
    if ( v8 > v15 )
      goto LABEL_61;
    v12 = 0;
    v16 = v8 < v13;
    v17 = v8 < v13;
    if ( v8 > v13 )
      v13 = v8;
    if ( v16 )
      v12 = v8;
    if ( v5 >= v15 )
      v5 = *(_DWORD *)(a4 + 12);
    v8 = v13;
  }
  else
  {
    v17 = 0;
  }
  v18 = (unsigned __int64)(v8 + 15LL) >> 4;
  v19 = (unsigned __int64)(v5 + 15LL) >> 4;
  result = 0;
  v16 = (int)v19 <= (int)v18;
  v20 = (unsigned int)(v19 - v18);
  if ( v16 )
    goto LABEL_61;
  v62 = (unsigned __int64)(v8 + 15LL) >> 4;
  v21 = v6;
  v22 = v11 - v10;
  if ( v11 < v10 )
  {
    v23 = -(__int64)v6;
    v22 = v10 - v11;
    if ( v10 - v11 < v6 )
    {
      v24 = 0;
      v59 = -1;
      if ( v17 )
        goto LABEL_28;
LABEL_22:
      v25 = (v8 + 15) & 0xFFFFFFF0;
      goto LABEL_30;
    }
    if ( !v6 )
      goto LABEL_70;
    v24 = -(int)(v22 / v6);
    v59 = -1;
    goto LABEL_27;
  }
  if ( v22 >= v6 )
  {
    if ( !v6 )
      goto LABEL_70;
    v24 = v22 / v6;
    v23 = -1;
    v59 = 1;
LABEL_27:
    v22 %= v6;
    if ( !v17 )
      goto LABEL_22;
    goto LABEL_28;
  }
  v23 = -1;
  v24 = 0;
  v59 = 1;
  if ( !v17 )
    goto LABEL_22;
LABEL_28:
  if ( !a4 )
    RNvNtCs9MWeMO1rkJG_4core6option13unwrap_failed(&off_14001BB20);
  v25 = *(_DWORD *)(a4 + 4);
  v8 = v12;
LABEL_30:
  v26 = v22;
  v27 = v25 - v8;
  v60 = v7;
  v64 = v20;
  if ( v25 != v8 )
  {
    v28 = v8 + 1;
    if ( (v27 & 1) != 0 )
    {
      v29 = v24 + v10;
      v30 = 0;
      v35 = v26 + v23 < 0;
      v31 = v26 + v23;
      v32 = 0;
      if ( !v35 )
      {
        v32 = v59;
        v30 = v21;
      }
      v27 = v29 + v32;
      v23 = v31 - v30;
      v10 = v27;
      v8 = v28;
      if ( v25 == v28 )
        goto LABEL_48;
    }
    else if ( v25 == v28 )
    {
      goto LABEL_48;
    }
    v33 = v25 - v8;
    do
    {
      v34 = v24 + v10;
      v35 = v26 + v23 < 0;
      v36 = v26 + v23;
      v37 = 0;
      if ( !v35 )
        v37 = v59;
      v38 = 0;
      if ( !v35 )
        v38 = v21;
      v39 = v36 - v38;
      v40 = v37 + v24 + v34;
      v41 = v26 + v39 < 0;
      v42 = v26 + v39;
      v43 = 0;
      if ( !v41 )
        v43 = v59;
      v44 = 0;
      if ( !v41 )
        v44 = v21;
      v27 = v40 + v43;
      v23 = v42 - v44;
      v10 = v27;
      v33 -= 2;
    }
    while ( v33 );
    goto LABEL_48;
  }
  v27 = v10;
LABEL_48:
  v45 = (unsigned __int64)(v27 + 15LL) >> 4;
  v46 = ((_BYTE)v27 + 15) & 0xF;
  if ( v59 == 1 )
    v46 = ((v27 + 15LL) & 0xFFFFFFFFFFFFFFF0uLL) - v27;
  v47 = a1[2];
  if ( v47 )
  {
    v48 = (_DWORD *)(a1[1] + 32LL);
    v49 = 0;
    while ( *v48 < (int)v62 || *v48 == (_DWORD)v62 && *(v48 - 1) < (int)v45 )
    {
      ++v49;
      v48 += 12;
      if ( v47 == v49 )
      {
        v49 = a1[2];
        v50 = *a1 == v47;
        v61 = a1;
        if ( !v50 )
          goto LABEL_59;
        goto LABEL_64;
      }
    }
  }
  else
  {
    v49 = 0;
  }
  v50 = *a1 == v47;
  v61 = a1;
  if ( !v50 )
  {
LABEL_59:
    v51 = a1[1];
LABEL_60:
    v52 = v23 - v21 * v46;
    v53 = 48 * v49;
    memmove((void *)(v51 + v53 + 48), (const void *)(v53 + v51), 48 * (v47 - v49));
    v54 = v61;
    v55 = v61[1];
    *(_QWORD *)(v55 + v53) = v52;
    *(_QWORD *)(v55 + v53 + 8) = 16 * v26;
    *(_QWORD *)(v55 + v53 + 16) = 16 * v21;
    *(_DWORD *)(v55 + v53 + 24) = v64;
    *(_DWORD *)(v55 + v53 + 28) = v45;
    *(_DWORD *)(v55 + v53 + 32) = v62;
    *(_DWORD *)(v55 + v53 + 36) = v24;
    *(_BYTE *)(v55 + v53 + 40) = v59;
    *(_BYTE *)(v55 + v53 + 41) = v60;
    ++v54[2];
    result = 0;
    goto LABEL_61;
  }
LABEL_64:
  v56 = 4;
  if ( (unsigned __int64)(2 * v47) >= 5 )
    v56 = 2 * v47;
  v63 = v56;
  RNvMs4_NtCsexo9QDNEsji_5alloc7raw_vecINtB5_11RawVecInnerINtCs1EG24RjTlfM_9gdi_alloc15TaggedAllocatorKm67646547_EE11finish_growCs7vXzV21FY6F_8gdi_rust_llvm_1180095224807683263(
    (unsigned int)&v65,
    (_DWORD)a1,
    v56,
    8,
    48);
  if ( v65 != 1 )
  {
    v51 = v66;
    v57 = v61;
    v61[1] = v66;
    *v57 = v63;
    goto LABEL_60;
  }
  result = 14;
LABEL_61:
  if ( _security_cookie != ((unsigned __int64)&v58 ^ v67) )
LABEL_70:
    RNvNtNtCs9MWeMO1rkJG_4core9panicking11panic_const23panic_const_div_by_zero((__int64)&off_14001BB08);
  return result;
}

```

## disassembly

```asm
0x14000fe20  push    r15
0x14000fe22  push    r14
0x14000fe24  push    r13
0x14000fe26  push    r12
0x14000fe28  push    rsi
0x14000fe29  push    rdi
0x14000fe2a  push    rbp
0x14000fe2b  push    rbx
0x14000fe2c  sub     rsp, 78h
0x14000fe30  mov     rax, cs:__security_cookie
0x14000fe37  xor     rax, rsp
0x14000fe3a  mov     [rsp+0B8h+var_48], rax
0x14000fe3f  mov     r10d, [r8+4]
0x14000fe43  mov     esi, [rdx+4]
0x14000fe46  mov     edi, r10d
0x14000fe49  sub     edi, esi
0x14000fe4b  jge     short loc_14000FE5D
0x14000fe4d  mov     edi, esi
0x14000fe4f  sub     edi, r10d
0x14000fe52  mov     r15b, 0FFh
0x14000fe55  mov     r11d, r10d
0x14000fe58  mov     rax, rdx
0x14000fe5b  jmp     short loc_14000FE6C
0x14000fe5d  mov     r15b, 1
0x14000fe60  mov     r11d, esi
0x14000fe63  mov     rax, r8
0x14000fe66  mov     r8, rdx
0x14000fe69  mov     esi, r10d
0x14000fe6c  mov     r10d, [r8]
0x14000fe6f  mov     edx, [rax]
0x14000fe71  xor     ebx, ebx
0x14000fe73  test    r9, r9
0x14000fe76  jz      short loc_14000FEB1
0x14000fe78  mov     r8d, [r9+4]
0x14000fe7c  xor     eax, eax
0x14000fe7e  cmp     esi, r8d
0x14000fe81  jl      loc_140010129
0x14000fe87  mov     r14d, [r9+0Ch]
0x14000fe8b  cmp     r11d, r14d
0x14000fe8e  jg      loc_140010129
0x14000fe94  xor     ebx, ebx
0x14000fe96  cmp     r11d, r8d
0x14000fe99  setl    bpl
0x14000fe9d  cmovg   r8d, r11d
0x14000fea1  cmovl   ebx, r11d
0x14000fea5  cmp     esi, r14d
0x14000fea8  cmovge  esi, r14d
0x14000feac  mov     r11d, r8d
0x14000feaf  jmp     short loc_14000FEB3
0x14000feb1  xor     ebp, ebp
0x14000feb3  movsxd  r8, r11d
0x14000feb6  add     r8, 0Fh
0x14000feba  shr     r8, 4
0x14000febe  movsxd  r14, esi
0x14000fec1  add     r14, 0Fh
0x14000fec5  shr     r14, 4
0x14000fec9  mov     eax, 0
0x14000fece  sub     r14d, r8d
0x14000fed1  jle     loc_140010129
0x14000fed7  mov     [rsp+0B8h+var_78], r8
0x14000fedc  mov     r8d, edx
0x14000fedf  mov     r12d, edi
0x14000fee2  sub     r8d, r10d
0x14000fee5  jge     short loc_14000FF06
0x14000fee7  mov     r13, r12
0x14000feea  neg     r13
0x14000feed  mov     r8d, r10d
0x14000fef0  sub     r8d, edx
0x14000fef3  cmp     r8d, edi
0x14000fef6  jnb     short loc_14000FF27
0x14000fef8  xor     esi, esi
0x14000fefa  mov     [rsp+0B8h+var_82], 0FFh
0x14000feff  test    bpl, bpl
0x14000ff02  jz      short loc_14000FF1E
0x14000ff04  jmp     short loc_14000FF6D
0x14000ff06  cmp     r8d, edi
0x14000ff09  jnb     short loc_14000FF41
0x14000ff0b  mov     r13, 0FFFFFFFFFFFFFFFFh
0x14000ff12  xor     esi, esi
0x14000ff14  mov     [rsp+0B8h+var_82], 1
0x14000ff19  test    bpl, bpl
0x14000ff1c  jnz     short loc_14000FF6D
0x14000ff1e  lea     eax, [r11+0Fh]
0x14000ff22  and     eax, 0FFFFFFF0h
0x14000ff25  jmp     short loc_14000FF7D
0x14000ff27  test    edi, edi
0x14000ff29  jz      loc_1400101DB
0x14000ff2f  mov     eax, r8d
0x14000ff32  xor     edx, edx
0x14000ff34  div     edi
0x14000ff36  mov     esi, eax
0x14000ff38  neg     esi
0x14000ff3a  mov     [rsp+0B8h+var_82], 0FFh
0x14000ff3f  jmp     short loc_14000FF5E
0x14000ff41  test    edi, edi
0x14000ff43  jz      loc_1400101DB
0x14000ff49  mov     eax, r8d
0x14000ff4c  xor     edx, edx
0x14000ff4e  div     edi
0x14000ff50  mov     esi, eax
0x14000ff52  mov     r13, 0FFFFFFFFFFFFFFFFh
0x14000ff59  mov     [rsp+0B8h+var_82], 1
0x14000ff5e  mov     eax, r8d
0x14000ff61  xor     edx, edx
0x14000ff63  div     edi
0x14000ff65  mov     r8d, edx
0x14000ff68  test    bpl, bpl
0x14000ff6b  jz      short loc_14000FF1E
0x14000ff6d  test    r9, r9
0x14000ff70  jz      loc_1400101C2
0x14000ff76  mov     eax, [r9+4]
0x14000ff7a  mov     r11d, ebx
0x14000ff7d  mov     edi, r8d
0x14000ff80  mov     r8d, eax
0x14000ff83  sub     r8d, r11d
0x14000ff86  mov     [rsp+0B8h+var_81], r15b
0x14000ff8b  mov     [rsp+0B8h+var_68], r14
0x14000ff90  jnz     short loc_14000FF9A
0x14000ff92  mov     r8d, r10d
0x14000ff95  jmp     loc_140010028
0x14000ff9a  movsx   edx, [rsp+0B8h+var_82]
0x14000ff9f  lea     r9d, [r11+1]
0x14000ffa3  test    r8b, 1
0x14000ffa7  jnz     short loc_14000FFB0
0x14000ffa9  cmp     eax, r9d
0x14000ffac  jnz     short loc_14000FFD8
0x14000ffae  jmp     short loc_140010028
0x14000ffb0  add     r10d, esi
0x14000ffb3  xor     r11d, r11d
0x14000ffb6  add     r13, rdi
0x14000ffb9  mov     r8d, 0
0x14000ffbf  cmovns  r8d, edx
0x14000ffc3  cmovns  r11, r12
0x14000ffc7  add     r8d, r10d
0x14000ffca  sub     r13, r11
0x14000ffcd  mov     r10d, r8d
0x14000ffd0  mov     r11d, r9d
0x14000ffd3  cmp     eax, r9d
0x14000ffd6  jz      short loc_140010028
0x14000ffd8  sub     eax, r11d
0x14000ffdb  nop     dword ptr [rax+rax+00h]
0x14000ffe0  add     r10d, esi
0x14000ffe3  add     r13, rdi
0x14000ffe6  mov     r8d, 0
0x14000ffec  cmovns  r8d, edx
0x14000fff0  mov     r9d, 0
0x14000fff6  cmovns  r9, r12
0x14000fffa  sub     r13, r9
0x14000fffd  add     r10d, esi
0x140010000  add     r10d, r8d
0x140010003  add     r13, rdi
0x140010006  mov     r8d, 0
0x14001000c  cmovns  r8d, edx
0x140010010  mov     r9d, 0
0x140010016  cmovns  r9, r12
0x14001001a  add     r8d, r10d
0x14001001d  sub     r13, r9
0x140010020  mov     r10d, r8d
0x140010023  add     eax, 0FFFFFFFEh
0x140010026  jnz     short loc_14000FFE0
0x140010028  movsxd  rax, r8d
0x14001002b  lea     rdx, [rax+0Fh]
0x14001002f  mov     rbx, rdx
0x140010032  shr     rbx, 4
0x140010036  mov     r15d, edx
0x140010039  and     r15d, 0Fh
0x14001003d  and     rdx, 0FFFFFFFFFFFFFFF0h
0x140010041  sub     rdx, rax
0x140010044  cmp     [rsp+0B8h+var_82], 1
0x140010049  cmovz   r15, rdx
0x14001004d  mov     r14, [rcx+10h]
0x140010051  test    r14, r14
0x140010054  jz      short loc_14001008D
0x140010056  mov     rax, [rcx+8]
0x14001005a  add     rax, 20h ; ' '
0x14001005e  xor     ebp, ebp
0x140010060  mov     rdx, [rsp+0B8h+var_78]
0x140010065  jmp     short loc_140010080
0x140010070  inc     rbp
0x140010073  add     rax, 30h ; '0'
0x140010077  cmp     r14, rbp
0x14001007a  jz      loc_140010152
0x140010080  cmp     [rax], edx
0x140010082  jl      short loc_140010070
0x140010084  jnz     short loc_14001008F
0x140010086  cmp     [rax-4], ebx
0x140010089  jl      short loc_140010070
0x14001008b  jmp     short loc_14001008F
0x14001008d  xor     ebp, ebp
0x14001008f  cmp     [rcx], r14
0x140010092  mov     [rsp+0B8h+var_80], rcx
0x140010097  jz      loc_140010163
0x14001009d  mov     rdx, [rcx+8]
0x1400100a1  imul    r15, r12
0x1400100a5  sub     r13, r15
0x1400100a8  shl     rdi, 4
0x1400100ac  shl     r12, 4
0x1400100b0  sub     r14, rbp
0x1400100b3  shl     rbp, 4
0x1400100b7  lea     r15, ds:0[rbp*2]
0x1400100bf  add     r15, rbp
0x1400100c2  lea     rcx, [rdx+r15]
0x1400100c6  add     rcx, 30h ; '0'; void *
0x1400100ca  add     rdx, r15; Src
0x1400100cd  shl     r14, 4
0x1400100d1  lea     r8, [r14+r14*2]; Size
0x1400100d5  call    memmove
0x1400100da  mov     rax, [rsp+0B8h+var_80]
0x1400100df  mov     rcx, [rax+8]
0x1400100e3  mov     [rcx+r15], r13
0x1400100e7  mov     [rcx+r15+8], rdi
0x1400100ec  mov     [rcx+r15+10h], r12
0x1400100f1  mov     rdx, [rsp+0B8h+var_68]
0x1400100f6  mov     [rcx+r15+18h], edx
0x1400100fb  mov     [rcx+r15+1Ch], ebx
0x140010100  mov     rdx, [rsp+0B8h+var_78]
0x140010105  mov     [rcx+r15+20h], edx
0x14001010a  mov     [rcx+r15+24h], esi
0x14001010f  movzx   edx, [rsp+0B8h+var_82]
0x140010114  mov     [rcx+r15+28h], dl
0x140010119  movzx   edx, [rsp+0B8h+var_81]
0x14001011e  mov     [rcx+r15+29h], dl
0x140010123  inc     qword ptr [rax+10h]
0x140010127  xor     eax, eax
0x140010129  mov     rcx, [rsp+0B8h+var_48]
0x14001012e  xor     rcx, rsp
0x140010131  mov     rdx, cs:__security_cookie
0x140010138  cmp     rdx, rcx
0x14001013b  jnz     loc_1400101CE
0x140010141  add     rsp, 78h
0x140010145  pop     rbx
0x140010146  pop     rbp
0x140010147  pop     rdi
0x140010148  pop     rsi
0x140010149  pop     r12
0x14001014b  pop     r13
0x14001014d  pop     r14
0x14001014f  pop     r15
0x140010151  retn
0x140010152  mov     rbp, r14
0x140010155  cmp     [rcx], r14
0x140010158  mov     [rsp+0B8h+var_80], rcx
0x14001015d  jnz     loc_14001009D
0x140010163  lea     rax, [r14+r14]
0x140010167  cmp     rax, 5
0x14001016b  mov     r8d, 4
0x140010171  cmovnb  r8, rax
0x140010175  mov     [rsp+0B8h+var_98], 30h ; '0'
0x14001017e  lea     rax, [rsp+0B8h+var_60]
0x140010183  mov     r9d, 8
0x140010189  mov     rdx, rcx
0x14001018c  mov     rcx, rax
0x14001018f  mov     [rsp+0B8h+var_70], r8
0x140010194  call    _RNvMs4_NtCsexo9QDNEsji_5alloc7raw_vecINtB5_11RawVecInnerINtCs1EG24RjTlfM_9gdi_alloc15TaggedAllocatorKm67646547_EE11finish_growCs7vXzV21FY6F_8gdi_rust_llvm_1180095224807683263
0x140010199  cmp     [rsp+0B8h+var_60], 1
0x14001019e  jnz     short loc_1400101A7
0x1400101a0  mov     eax, 0Eh
0x1400101a5  jmp     short loc_140010129
0x1400101a7  mov     rdx, [rsp+0B8h+var_58]
0x1400101ac  mov     rax, [rsp+0B8h+var_80]
0x1400101b1  mov     [rax+8], rdx
0x1400101b5  mov     rcx, [rsp+0B8h+var_70]
0x1400101ba  mov     [rax], rcx
0x1400101bd  jmp     loc_1400100A1
0x1400101c2  lea     rcx, off_14001BB20; "gdi_rust\\src\\region\\from_path.rs"
0x1400101c9  call    _RNvNtCs9MWeMO1rkJG_4core6option13unwrap_failed
0x1400101ce  mov     rcx, [rsp+0B8h+var_48]
0x1400101d3  xor     rcx, rsp; StackCookie
0x1400101d6  call    __security_check_cookie
0x1400101db  lea     rcx, off_14001BB08; "gdi_rust\\src\\region\\from_path.rs"
0x1400101e2  call    _RNvNtNtCs9MWeMO1rkJG_4core9panicking11panic_const23panic_const_div_by_zero
```
