# _RNvMs1_NtCsdcpJtfrLhSH_7rgncore4scanINtB5_12ScanInternalQINtNtCsexo9QDNEsji_5alloc3vec3VeclINtCsdwtLm5uWta6_10gdi_region22ScanLookAsideAllocatorKj70_EEB1r_E16merge_in_x_wallsB7_

- ea: `0x140012420`
- end: `0x140012689`
- name: `_RNvMs1_NtCsdcpJtfrLhSH_7rgncore4scanINtB5_12ScanInternalQINtNtCsexo9QDNEsji_5alloc3vec3VeclINtCsdwtLm5uWta6_10gdi_region22ScanLookAsideAllocatorKj70_EEB1r_E16merge_in_x_wallsB7_`
- size: `617`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation`

## callers

- `0x14000b240`

## callees

- `0x140012420`
- `0x140014dd0`
- `0x140017b00`
- `0x1400184d7`
- `0x140018650`
- `0x140018690`

## pseudocode

```c
__int64 __fastcall RNvMs1_NtCsdcpJtfrLhSH_7rgncore4scanINtB5_12ScanInternalQINtNtCsexo9QDNEsji_5alloc3vec3VeclINtCsdwtLm5uWta6_10gdi_region22ScanLookAsideAllocatorKj70_EEB1r_E16merge_in_x_wallsB7_(
        __int64 **a1,
        _DWORD *a2,
        unsigned __int64 a3,
        char *a4,
        unsigned __int64 a5)
{
  __int64 *v5; // rdi
  unsigned __int64 v6; // rsi
  unsigned __int64 v7; // r10
  __int64 v8; // r11
  unsigned __int64 v9; // r13
  unsigned __int64 v10; // rbp
  __int64 result; // rax
  unsigned __int64 v12; // rcx
  _DWORD *v13; // rax
  char *v14; // rcx
  int v15; // r11d
  int v16; // ebx
  _QWORD *v17; // r15
  unsigned __int64 v18; // r10
  unsigned __int64 v19; // r10
  char *v20; // r14
  bool v21; // cf
  unsigned __int64 v22; // rbp
  const void *v23; // r15
  unsigned __int64 v25; // r12
  unsigned __int64 v26; // rdx
  unsigned __int64 v27; // rcx
  unsigned __int64 v28; // rdx
  unsigned __int64 v29; // r14
  unsigned __int64 v30; // rdx
  unsigned __int64 v31; // [rsp+30h] [rbp-48h]

  v5 = *a1;
  v6 = (unsigned __int64)a1[1];
  v7 = (*a1)[2];
  if ( v6 >= v7 )
    RNvNtCs9MWeMO1rkJG_4core9panicking18panic_bounds_check(
      a1[1],
      v7,
      &anon_22b06d26984f22b1c5b0f9b994440758_2_llvm_8899961222222301143);
  v8 = v5[1];
  v9 = *(int *)(v8 + 4 * v6);
  v10 = a3 + v9;
  result = 8;
  if ( a5 >= a3 + v9 )
  {
    v12 = v6 + 3;
    if ( __CFADD__(v9, v6 + 3) || v9 + v6 + 3 > v7 )
      RNvNtNtCs9MWeMO1rkJG_4core5slice5index16slice_index_fail(
        v12,
        v9 + v6 + 3,
        v7,
        &anon_22b06d26984f22b1c5b0f9b994440758_16_llvm_8899961222222301143);
    v13 = (_DWORD *)(v8 + 4 * v12);
    v31 = a3 + v9;
    if ( a3 && (_DWORD)v9 )
    {
      v14 = a4;
      do
      {
        v15 = *v13;
        v16 = *a2;
        v17 = v13;
        v18 = v9;
        if ( *v13 >= *a2 )
        {
          v17 = a2;
          v18 = a3;
        }
        if ( v18 <= 1 )
          RNvNtCs9MWeMO1rkJG_4core9panicking9panic_fmt(&dword_14001D074, 19, &off_14001BEA0);
        if ( v10 <= 1 )
          RNvNtCs9MWeMO1rkJG_4core9panicking9panic_fmt(&dword_14001D074, 19, &off_14001BEB8);
        v19 = v18 - 2;
        v20 = v14 + 8;
        v10 -= 2LL;
        if ( v15 >= v16 )
        {
          a2 = v17 + 1;
          a3 = v19;
        }
        else
        {
          v13 = v17 + 1;
        }
        *(_QWORD *)v14 = *v17;
        if ( v15 < v16 )
          v9 = v19;
        if ( !v9 )
          break;
        v14 += 8;
      }
      while ( a3 );
    }
    else
    {
      v20 = a4;
    }
    v21 = v10 < v9;
    v22 = v10 - v9;
    if ( v21 )
      RNvNtCs9MWeMO1rkJG_4core9panicking9panic_fmt(&dword_14001D074, 19, &off_14001BE70);
    v23 = a2;
    v25 = a3;
    memmove(v20, v13, 4 * v9);
    if ( v25 > v22 )
      RNvNtCs9MWeMO1rkJG_4core9panicking9panic_fmt(&dword_14001D074, 19, &off_14001BE88);
    memmove(&v20[4 * v9], v23, 4 * v25);
    v26 = v5[2];
    if ( v6 >= v26 )
      RNvNtCs9MWeMO1rkJG_4core9panicking18panic_bounds_check(
        v6,
        v26,
        &anon_22b06d26984f22b1c5b0f9b994440758_2_llvm_8899961222222301143);
    v27 = RINvXCs3PyRTeGQ7Na_12fallible_vecINtNtCsexo9QDNEsji_5alloc3vec3VeclINtCsdwtLm5uWta6_10gdi_region22ScanLookAsideAllocatorKj70_EEINtB3_11FallibleVeclB13_E13try_splice_inINtNtNtNtCs9MWeMO1rkJG_4core4iter8adapters3map3MapINtNtNtB2O_5slice4iter7IterMutlENCNvMs1_NtCsdcpJtfrLhSH_7rgncore4scanINtB47_12ScanInternalQBv_B13_E16merge_in_x_walls0EINtNtNtB2O_3ops5range5RangejEEB49_(
            v5,
            v6 + 3,
            v6 + 3 + *(int *)(v5[1] + 4 * v6),
            a4,
            &a4[4 * v31]);
    result = 14;
    if ( v27 == 0x8000000000000001uLL )
    {
      v28 = v5[2];
      if ( v6 >= v28 )
        RNvNtCs9MWeMO1rkJG_4core9panicking18panic_bounds_check(v6, v28, &off_14001BE40);
      *(_DWORD *)(v5[1] + 4 * v6) = v31;
      v29 = v31 + v6 + 3;
      v30 = v5[2];
      if ( v29 >= v30 )
        RNvNtCs9MWeMO1rkJG_4core9panicking18panic_bounds_check(v29, v30, &off_14001BE58);
      *(_DWORD *)(v5[1] + 4 * v29) = v31;
      return 0;
    }
  }
  return result;
}

```

## disassembly

```asm
0x140012420  push    r15
0x140012422  push    r14
0x140012424  push    r13
0x140012426  push    r12
0x140012428  push    rsi
0x140012429  push    rdi
0x14001242a  push    rbp
0x14001242b  push    rbx
0x14001242c  sub     rsp, 38h
0x140012430  mov     rdi, [rcx]
0x140012433  mov     rsi, [rcx+8]
0x140012437  mov     r10, [rdi+10h]
0x14001243b  cmp     rsi, r10
0x14001243e  jnb     loc_140012649
0x140012444  mov     r11, [rdi+8]
0x140012448  movsxd  r13, dword ptr [r11+rsi*4]
0x14001244c  lea     rbp, [r8+r13]
0x140012450  mov     eax, 8
0x140012455  cmp     [rsp+78h+arg_20], rbp
0x14001245d  jb      loc_1400125C6
0x140012463  lea     rcx, [rsi+3]
0x140012467  mov     rax, rcx
0x14001246a  add     rax, r13
0x14001246d  jb      loc_140012607
0x140012473  cmp     rax, r10
0x140012476  ja      loc_140012607
0x14001247c  lea     rax, [r11+rcx*4]
0x140012480  test    r8, r8
0x140012483  mov     [rsp+78h+var_48], rbp
0x140012488  jz      short loc_140012502
0x14001248a  test    r13d, r13d
0x14001248d  jz      short loc_140012502
0x14001248f  mov     rcx, r9
0x140012492  nop     word ptr [rax+rax+00000000h]
0x1400124a0  mov     r11d, [rax]
0x1400124a3  mov     ebx, [rdx]
0x1400124a5  mov     r15, rax
0x1400124a8  mov     r10, r13
0x1400124ab  cmp     r11d, ebx
0x1400124ae  jl      short loc_1400124B6
0x1400124b0  mov     r15, rdx
0x1400124b3  mov     r10, r8
0x1400124b6  cmp     r10, 1
0x1400124ba  jbe     loc_1400125D7
0x1400124c0  cmp     rbp, 1
0x1400124c4  jbe     loc_1400125EF
0x1400124ca  add     r10, 0FFFFFFFFFFFFFFFEh
0x1400124ce  lea     r12, [r15+8]
0x1400124d2  lea     r14, [rcx+8]
0x1400124d6  add     rbp, 0FFFFFFFFFFFFFFFEh
0x1400124da  cmp     r11d, ebx
0x1400124dd  mov     r11, [r15]
0x1400124e0  cmovl   rax, r12
0x1400124e4  cmovge  rdx, r12
0x1400124e8  cmovge  r8, r10
0x1400124ec  mov     [rcx], r11
0x1400124ef  cmovl   r13, r10
0x1400124f3  test    r13, r13
0x1400124f6  jz      short loc_140012505
0x1400124f8  mov     rcx, r14
0x1400124fb  test    r8, r8
0x1400124fe  jnz     short loc_1400124A0
0x140012500  jmp     short loc_140012505
0x140012502  mov     r14, r9
0x140012505  sub     rbp, r13
0x140012508  jb      loc_140012619
0x14001250e  mov     r15, rdx
0x140012511  mov     rbx, r9
0x140012514  lea     r9, ds:0[r13*4]
0x14001251c  mov     rcx, r14; void *
0x14001251f  mov     rdx, rax; Src
0x140012522  mov     r12, r8
0x140012525  mov     r8, r9; Size
0x140012528  call    memmove
0x14001252d  cmp     r12, rbp
0x140012530  ja      loc_140012631
0x140012536  lea     rcx, [r14+r13*4]; void *
0x14001253a  shl     r12, 2
0x14001253e  mov     rdx, r15; Src
0x140012541  mov     r8, r12; Size
0x140012544  call    memmove
0x140012549  mov     rdx, [rdi+10h]
0x14001254d  cmp     rsi, rdx
0x140012550  jnb     loc_14001265B
0x140012556  mov     rax, [rdi+8]
0x14001255a  movsxd  r8, dword ptr [rax+rsi*4]
0x14001255e  lea     r14, [rsi+3]
0x140012562  add     r8, r14
0x140012565  mov     r9, rbx
0x140012568  mov     rbx, [rsp+78h+var_48]
0x14001256d  lea     rax, [r9+rbx*4]
0x140012571  mov     [rsp+78h+var_58], rax
0x140012576  mov     rcx, rdi
0x140012579  mov     rdx, r14
0x14001257c  call    _RINvXCs3PyRTeGQ7Na_12fallible_vecINtNtCsexo9QDNEsji_5alloc3vec3VeclINtCsdwtLm5uWta6_10gdi_region22ScanLookAsideAllocatorKj70_EEINtB3_11FallibleVeclB13_E13try_splice_inINtNtNtNtCs9MWeMO1rkJG_4core4iter8adapters3map3MapINtNtNtB2O_5slice4iter7IterMutlENCNvMs1_NtCsdcpJtfrLhSH_7rgncore4scanINtB47_12ScanInternalQBv_B13_E16merge_in_x_walls0EINtNtNtB2O_3ops5range5RangejEEB49_
0x140012581  mov     rcx, rax
0x140012584  mov     eax, 0Eh
0x140012589  mov     rdx, 8000000000000001h
0x140012593  cmp     rcx, rdx
0x140012596  jnz     short loc_1400125C6
0x140012598  mov     rdx, [rdi+10h]
0x14001259c  cmp     rsi, rdx
0x14001259f  jnb     loc_14001266A
0x1400125a5  mov     rax, [rdi+8]
0x1400125a9  mov     [rax+rsi*4], ebx
0x1400125ac  add     r14, rbx
0x1400125af  mov     rdx, [rdi+10h]
0x1400125b3  cmp     r14, rdx
0x1400125b6  jnb     loc_140012679
0x1400125bc  mov     rax, [rdi+8]
0x1400125c0  mov     [rax+r14*4], ebx
0x1400125c4  xor     eax, eax
0x1400125c6  add     rsp, 38h
0x1400125ca  pop     rbx
0x1400125cb  pop     rbp
0x1400125cc  pop     rdi
0x1400125cd  pop     rsi
0x1400125ce  pop     r12
0x1400125d0  pop     r13
0x1400125d2  pop     r14
0x1400125d4  pop     r15
0x1400125d6  retn
0x1400125d7  lea     rcx, dword_14001D074
0x1400125de  lea     r8, off_14001BEA0; "rgncore\\src\\scan.rs"
0x1400125e5  mov     edx, 13h
0x1400125ea  call    _RNvNtCs9MWeMO1rkJG_4core9panicking9panic_fmt
0x1400125ef  lea     rcx, dword_14001D074
0x1400125f6  lea     r8, off_14001BEB8; "rgncore\\src\\scan.rs"
0x1400125fd  mov     edx, 13h
0x140012602  call    _RNvNtCs9MWeMO1rkJG_4core9panicking9panic_fmt
0x140012607  lea     r9, anon_22b06d26984f22b1c5b0f9b994440758_16_llvm_8899961222222301143
0x14001260e  mov     rdx, rax
0x140012611  mov     r8, r10
0x140012614  call    _RNvNtNtCs9MWeMO1rkJG_4core5slice5index16slice_index_fail
0x140012619  lea     rcx, dword_14001D074
0x140012620  lea     r8, off_14001BE70; "rgncore\\src\\scan.rs"
0x140012627  mov     edx, 13h
0x14001262c  call    _RNvNtCs9MWeMO1rkJG_4core9panicking9panic_fmt
0x140012631  lea     rcx, dword_14001D074
0x140012638  lea     r8, off_14001BE88; "rgncore\\src\\scan.rs"
0x14001263f  mov     edx, 13h
0x140012644  call    _RNvNtCs9MWeMO1rkJG_4core9panicking9panic_fmt
0x140012649  lea     r8, anon_22b06d26984f22b1c5b0f9b994440758_2_llvm_8899961222222301143
0x140012650  mov     rcx, rsi
0x140012653  mov     rdx, r10
0x140012656  call    _RNvNtCs9MWeMO1rkJG_4core9panicking18panic_bounds_check
0x14001265b  lea     r8, anon_22b06d26984f22b1c5b0f9b994440758_2_llvm_8899961222222301143
0x140012662  mov     rcx, rsi
0x140012665  call    _RNvNtCs9MWeMO1rkJG_4core9panicking18panic_bounds_check
0x14001266a  lea     r8, off_14001BE40; "rgncore\\src\\scan.rs"
0x140012671  mov     rcx, rsi
0x140012674  call    _RNvNtCs9MWeMO1rkJG_4core9panicking18panic_bounds_check
0x140012679  lea     r8, off_14001BE58; "rgncore\\src\\scan.rs"
0x140012680  mov     rcx, r14
0x140012683  call    _RNvNtCs9MWeMO1rkJG_4core9panicking18panic_bounds_check
```
