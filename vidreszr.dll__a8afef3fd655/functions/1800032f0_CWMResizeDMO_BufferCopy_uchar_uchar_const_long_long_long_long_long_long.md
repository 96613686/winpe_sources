# CWMResizeDMO::BufferCopy(uchar *,uchar const *,long,long,long,long,long,long)

- ea: `0x1800032f0`
- end: `0x180003565`
- name: `?BufferCopy@CWMResizeDMO@@AEAAJPEAEPEBEJJJJJJ@Z`
- size: `629`
- prototype: `int(CWMResizeDMO *__hidden this, unsigned __int8 *, const unsigned __int8 *, int, int, int, int, int, int)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180007e90`

## callees

- `0x1800032f0`
- `0x180015905`

## pseudocode

```c
__int64 __fastcall CWMResizeDMO::BufferCopy(
        CWMResizeDMO *this,
        unsigned __int8 *a2,
        const unsigned __int8 *a3,
        int a4,
        int a5,
        int a6,
        int a7,
        int a8,
        int a9)
{
  const unsigned __int8 *v9; // rbx
  unsigned __int8 *v10; // rdi
  int v11; // r15d
  int v12; // ecx
  int v13; // r14d
  int v14; // eax
  int v15; // ecx
  unsigned __int8 *v16; // rbp
  int v17; // esi
  __int64 v18; // r12
  int v20; // esi
  int v21; // ebp
  __int64 v22; // rsi
  int v23; // ebp
  int v24; // [rsp+20h] [rbp-48h]
  int v25; // [rsp+70h] [rbp+8h]
  int v26; // [rsp+80h] [rbp+18h]

  v9 = a3;
  v10 = a2;
  if ( !a3 || !a2 )
    return 2147500037LL;
  if ( a4 == 1448433993 || a4 == 808596553 || a4 == 842094169 )
  {
    v11 = a5;
    v12 = a8;
    v25 = a6 / 2;
    v13 = a5 / 2;
    v26 = a7 / 2;
    v14 = a8 / 2;
    goto LABEL_22;
  }
  if ( a4 == 961893977 )
  {
    v11 = a5;
    v12 = a8;
    v25 = a6 / 4;
    v13 = a5 / 4;
    v26 = a7 / 4;
    v14 = a8 / 4;
LABEL_22:
    v20 = 0;
    v24 = v14;
    v21 = 0;
    if ( v11 > 0 )
    {
      v22 = v12;
      do
      {
        memcpy_0(v10, v9, a6);
        v9 += a7;
        v10 += v22;
        ++v21;
      }
      while ( v21 < v11 );
      v20 = 0;
    }
    v23 = 0;
    if ( v13 > 0 )
    {
      do
      {
        memcpy_0(v10, v9, v25);
        v9 += v26;
        v10 += v24;
        ++v23;
      }
      while ( v23 < v13 );
      do
      {
        memcpy_0(v10, v9, v25);
        v9 += v26;
        v10 += v24;
        ++v20;
      }
      while ( v20 < v13 );
    }
    return 0;
  }
  if ( a4 > 3 )
  {
    if ( a4 == 1498831189 || a4 == 844715353 || a4 == 909193814 || a4 == 1448433985 )
      goto LABEL_13;
    return 2147500037LL;
  }
  if ( a4 < 3 && a9 )
  {
    v16 = &a2[a8 * (a5 - 1)];
    v15 = -a8;
    goto LABEL_14;
  }
LABEL_13:
  v15 = a8;
  v16 = a2;
LABEL_14:
  v17 = 0;
  if ( a5 <= 0 )
    return 0;
  v18 = v15;
  do
  {
    memcpy_0(v16, v9, a6);
    v9 += a7;
    v16 += v18;
    ++v17;
  }
  while ( v17 < a5 );
  return 0;
}

```

## disassembly

```asm
0x1800032f0  mov     [rsp+arg_0], rcx
0x1800032f5  push    rbx
0x1800032f6  push    rbp
0x1800032f7  push    rsi
0x1800032f8  push    rdi
0x1800032f9  push    r12
0x1800032fb  push    r14
0x1800032fd  push    r15
0x1800032ff  sub     rsp, 30h
0x180003303  mov     rbx, r8
0x180003306  mov     rdi, rdx
0x180003309  test    r8, r8
0x18000330c  jz      loc_180003551
0x180003312  test    rdx, rdx
0x180003315  jz      loc_180003551
0x18000331b  movsxd  r8, [rsp+68h+arg_30]
0x180003323  movsxd  r10, [rsp+68h+arg_28]
0x18000332b  cmp     r9d, 56555949h
0x180003332  jz      loc_180003450
0x180003338  cmp     r9d, 30323449h
0x18000333f  jz      loc_180003450
0x180003345  cmp     r9d, 32315659h
0x18000334c  jz      loc_180003450
0x180003352  cmp     r9d, 39555659h
0x180003359  jnz     short loc_1800033AC
0x18000335b  mov     r15d, [rsp+68h+arg_20]
0x180003363  mov     eax, r10d
0x180003366  mov     ecx, [rsp+68h+arg_38]
0x18000336d  cdq
0x18000336e  and     edx, 3
0x180003371  add     eax, edx
0x180003373  sar     eax, 2
0x180003376  mov     dword ptr [rsp+68h+arg_0], eax
0x18000337a  mov     eax, r15d
0x18000337d  cdq
0x18000337e  and     edx, 3
0x180003381  lea     r14d, [rdx+rax]
0x180003385  mov     eax, r8d
0x180003388  cdq
0x180003389  sar     r14d, 2
0x18000338d  and     edx, 3
0x180003390  add     eax, edx
0x180003392  sar     eax, 2
0x180003395  mov     [rsp+68h+arg_10], eax
0x18000339c  mov     eax, ecx
0x18000339e  cdq
0x18000339f  and     edx, 3
0x1800033a2  add     eax, edx
0x1800033a4  sar     eax, 2
0x1800033a7  jmp     loc_18000348C
0x1800033ac  mov     r14d, [rsp+68h+arg_20]
0x1800033b4  cmp     r9d, 3
0x1800033b8  jle     short loc_18000342C
0x1800033ba  cmp     r9d, 59565955h
0x1800033c1  jz      short loc_1800033E2
0x1800033c3  cmp     r9d, 32595559h
0x1800033ca  jz      short loc_1800033E2
0x1800033cc  cmp     r9d, 36313256h
0x1800033d3  jz      short loc_1800033E2
0x1800033d5  cmp     r9d, 56555941h
0x1800033dc  jnz     loc_180003551
0x1800033e2  mov     ecx, [rsp+68h+arg_38]
0x1800033e9  mov     rbp, rdx
0x1800033ec  xor     esi, esi
0x1800033ee  test    r14d, r14d
0x1800033f1  jle     loc_180003540
0x1800033f7  mov     rdi, r10
0x1800033fa  movsxd  r12, ecx
0x1800033fd  mov     r15, r8
0x180003400  mov     r8, rdi; Size
0x180003403  mov     rdx, rbx; Src
0x180003406  mov     rcx, rbp; void *
0x180003409  call    memcpy_0
0x18000340e  add     rbx, r15
0x180003411  add     rbp, r12
0x180003414  inc     esi
0x180003416  cmp     esi, r14d
0x180003419  jl      short loc_180003400
0x18000341b  xor     eax, eax
0x18000341d  add     rsp, 30h
0x180003421  pop     r15
0x180003423  pop     r14
0x180003425  pop     r12
0x180003427  pop     rdi
0x180003428  pop     rsi
0x180003429  pop     rbp
0x18000342a  pop     rbx
0x18000342b  retn
0x18000342c  jge     short loc_1800033E2
0x18000342e  cmp     [rsp+68h+arg_40], 0
0x180003436  jz      short loc_1800033E2
0x180003438  mov     ecx, [rsp+68h+arg_38]
0x18000343f  lea     eax, [r14-1]
0x180003443  imul    eax, ecx
0x180003446  movsxd  rbp, eax
0x180003449  add     rbp, rdx
0x18000344c  neg     ecx
0x18000344e  jmp     short loc_1800033EC
0x180003450  mov     r15d, [rsp+68h+arg_20]
0x180003458  mov     eax, r10d
0x18000345b  mov     ecx, [rsp+68h+arg_38]
0x180003462  cdq
0x180003463  sub     eax, edx
0x180003465  sar     eax, 1
0x180003467  mov     dword ptr [rsp+68h+arg_0], eax
0x18000346b  mov     eax, r15d
0x18000346e  cdq
0x18000346f  sub     eax, edx
0x180003471  sar     eax, 1
0x180003473  mov     r14d, eax
0x180003476  mov     eax, r8d
0x180003479  cdq
0x18000347a  sub     eax, edx
0x18000347c  sar     eax, 1
0x18000347e  mov     [rsp+68h+arg_10], eax
0x180003485  mov     eax, ecx
0x180003487  cdq
0x180003488  sub     eax, edx
0x18000348a  sar     eax, 1
0x18000348c  xor     esi, esi
0x18000348e  mov     [rsp+68h+var_48], eax
0x180003492  mov     [rsp+68h+arg_8], r13
0x180003497  mov     ebp, esi
0x180003499  test    r15d, r15d
0x18000349c  jle     short loc_1800034CD
0x18000349e  mov     r12, r10
0x1800034a1  movsxd  rsi, ecx
0x1800034a4  mov     r13, r8
0x1800034a7  nop     word ptr [rax+rax+00000000h]
0x1800034b0  mov     r8, r12; Size
0x1800034b3  mov     rdx, rbx; Src
0x1800034b6  mov     rcx, rdi; void *
0x1800034b9  call    memcpy_0
0x1800034be  add     rbx, r13
0x1800034c1  add     rdi, rsi
0x1800034c4  inc     ebp
0x1800034c6  cmp     ebp, r15d
0x1800034c9  jl      short loc_1800034B0
0x1800034cb  xor     esi, esi
0x1800034cd  mov     ebp, esi
0x1800034cf  test    r14d, r14d
0x1800034d2  jle     short loc_18000353B
0x1800034d4  movsxd  r15, dword ptr [rsp+68h+arg_0]
0x1800034d9  movsxd  r12, [rsp+68h+arg_10]
0x1800034e1  movsxd  r13, [rsp+68h+var_48]
0x1800034e6  nop     word ptr [rax+rax+00000000h]
0x1800034f0  mov     r8, r15; Size
0x1800034f3  mov     rdx, rbx; Src
0x1800034f6  mov     rcx, rdi; void *
0x1800034f9  call    memcpy_0
0x1800034fe  add     rbx, r12
0x180003501  add     rdi, r13
0x180003504  inc     ebp
0x180003506  cmp     ebp, r14d
0x180003509  jl      short loc_1800034F0
0x18000350b  movsxd  rbp, dword ptr [rsp+68h+arg_0]
0x180003510  movsxd  r15, [rsp+68h+arg_10]
0x180003518  movsxd  r12, [rsp+68h+var_48]
0x18000351d  nop     dword ptr [rax]
0x180003520  mov     r8, rbp; Size
0x180003523  mov     rdx, rbx; Src
0x180003526  mov     rcx, rdi; void *
0x180003529  call    memcpy_0
0x18000352e  add     rbx, r15
0x180003531  add     rdi, r12
0x180003534  inc     esi
0x180003536  cmp     esi, r14d
0x180003539  jl      short loc_180003520
0x18000353b  mov     r13, [rsp+68h+arg_8]
0x180003540  xor     eax, eax
0x180003542  add     rsp, 30h
0x180003546  pop     r15
0x180003548  pop     r14
0x18000354a  pop     r12
0x18000354c  pop     rdi
0x18000354d  pop     rsi
0x18000354e  pop     rbp
0x18000354f  pop     rbx
0x180003550  retn
0x180003551  mov     eax, 80004005h
0x180003556  add     rsp, 30h
0x18000355a  pop     r15
0x18000355c  pop     r14
0x18000355e  pop     r12
0x180003560  pop     rdi
0x180003561  pop     rsi
0x180003562  pop     rbp
0x180003563  pop     rbx
0x180003564  retn
```
