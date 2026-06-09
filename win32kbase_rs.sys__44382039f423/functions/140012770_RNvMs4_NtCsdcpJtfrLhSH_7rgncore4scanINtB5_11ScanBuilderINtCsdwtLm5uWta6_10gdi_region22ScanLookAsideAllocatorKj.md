# _RNvMs4_NtCsdcpJtfrLhSH_7rgncore4scanINtB5_11ScanBuilderINtCsdwtLm5uWta6_10gdi_region22ScanLookAsideAllocatorKj70_EE18commit_or_coalesceB7_

- ea: `0x140012770`
- end: `0x140012a28`
- name: `_RNvMs4_NtCsdcpJtfrLhSH_7rgncore4scanINtB5_11ScanBuilderINtCsdwtLm5uWta6_10gdi_region22ScanLookAsideAllocatorKj70_EE18commit_or_coalesceB7_`
- size: `696`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `2`
- callee_count: `10`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x14000cc10`
- `0x14000e9d0`

## callees

- `0x14000fdc0`
- `0x1400120f0`
- `0x140012770`
- `0x140017a10`
- `0x140017dd0`
- `0x140018470`
- `0x1400184d7`
- `0x140018630`
- `0x140018690`
- `0x1400193b0`

## pseudocode

```c
__int64 __fastcall RNvMs4_NtCsdcpJtfrLhSH_7rgncore4scanINtB5_11ScanBuilderINtCsdwtLm5uWta6_10gdi_region22ScanLookAsideAllocatorKj70_EE18commit_or_coalesceB7_(
        __int64 a1)
{
  unsigned __int64 *v2; // rsi
  unsigned __int64 v3; // rdi
  unsigned __int64 v4; // rdx
  __int64 v5; // rax
  uintptr_t v6; // r15
  unsigned __int64 v7; // rbx
  uintptr_t v8; // rcx
  unsigned __int64 v9; // r12
  __int64 v10; // r8
  unsigned __int64 v11; // rdx
  __int64 result; // rax
  _DWORD *v13; // r15
  _DWORD *v14; // r8
  int v15; // ebp
  unsigned __int64 v16; // r12
  unsigned __int64 v17; // rax
  unsigned __int64 v18; // r14
  __int64 v19; // [rsp+0h] [rbp-98h] BYREF
  char v20; // [rsp+3Fh] [rbp-59h] BYREF
  __int64 v21; // [rsp+40h] [rbp-58h] BYREF
  _DWORD *v22; // [rsp+48h] [rbp-50h]
  __int64 v23; // [rsp+58h] [rbp-40h]

  v2 = *(unsigned __int64 **)a1;
  v3 = *(_QWORD *)(a1 + 16);
  if ( v3 )
  {
    v4 = v2[2];
    if ( v3 - 1 >= v4 )
      RNvNtCs9MWeMO1rkJG_4core9panicking18panic_bounds_check(v3 - 1, v4, &off_14001BFC0);
    v5 = *(int *)(v2[1] + 4 * v3 - 4);
    if ( v5 < 0 )
      RNvNtCs9MWeMO1rkJG_4core6result13unwrap_failed(
        (unsigned int)anon_22b06d26984f22b1c5b0f9b994440758_6_llvm_8899961222222301143,
        43,
        (unsigned int)&v20,
        (unsigned int)anon_22b06d26984f22b1c5b0f9b994440758_5_llvm_8899961222222301143,
        (__int64)&off_14001BFD8);
    v6 = v3 - v5 - 4;
    if ( !RNvMNtCsdcpJtfrLhSH_7rgncore4scanINtB2_12ScanInternalQINtNtCsexo9QDNEsji_5alloc3vec3VeclINtCsdwtLm5uWta6_10gdi_region22ScanLookAsideAllocatorKj70_EEB1o_E13is_valid_scanB4__llvm_8899961222222301143(
            (__int64)v2,
            v6) )
      RNvNtCs9MWeMO1rkJG_4core9panicking5panic(
        "assertion failed: ScanInternal::is_valid_scan(&&*self.scan_data, previous_index)TryFromIntErrorseh_unwind\\src\\lib.rs",
        80,
        &off_14001BFF0);
    v7 = v2[2];
    if ( v6 >= v7 )
      RNvNtCs9MWeMO1rkJG_4core9panicking18panic_bounds_check(
        v6,
        v2[2],
        &anon_22b06d26984f22b1c5b0f9b994440758_2_llvm_8899961222222301143);
    v8 = v6 + 3;
    v9 = v2[1];
    v10 = *(int *)(v9 + 4 * v6);
    v11 = v10 + v6 + 3;
    if ( __CFADD__(v10, v6 + 3) || v11 > v7 )
      RNvNtNtCs9MWeMO1rkJG_4core5slice5index16slice_index_fail(
        v8,
        v11,
        v2[2],
        &anon_22b06d26984f22b1c5b0f9b994440758_16_llvm_8899961222222301143);
    if ( v7 < v3 + 3 )
      RNvNtNtCs9MWeMO1rkJG_4core5slice5index16slice_index_fail(
        v3 + 3,
        v2[2],
        v2[2],
        &anon_22b06d26984f22b1c5b0f9b994440758_51_llvm_8899961222222301143);
    if ( v7 - (v3 + 3) == v10 && !memcmp((const void *)(v9 + 4 * v8), (const void *)(v9 + 4 * (v3 + 3)), 4 * v10) )
    {
      if ( v3 + 2 >= v7 )
        RNvNtCs9MWeMO1rkJG_4core9panicking18panic_bounds_check(v3 + 2, v7, &off_14001C008);
      if ( v6 + 2 >= v7 )
        RNvNtCs9MWeMO1rkJG_4core9panicking18panic_bounds_check(v6 + 2, v7, &off_14001C020);
      *(_DWORD *)(v9 + 4 * v6 + 8) = *(_DWORD *)(v9 + 4 * v3 + 8);
      if ( v3 <= v2[2] )
      {
        v2[2] = v3;
        result = 0;
        goto LABEL_20;
      }
LABEL_35:
      RNvNtCs9MWeMO1rkJG_4core9panicking5panic(
        "assertion failed: index <= scan_data.len()assertion failed: ScanInternal::is_valid_scan(&&*self.scan_data, previ"
        "ous_index)TryFromIntErrorseh_unwind\\src\\lib.rs",
        42,
        &anon_22b06d26984f22b1c5b0f9b994440758_44_llvm_8899961222222301143);
    }
  }
  else
  {
    v7 = v2[2];
  }
  if ( v3 >= v7 )
    goto LABEL_36;
  v13 = *(_DWORD **)(a1 + 8);
  v14 = (_DWORD *)v2[1];
  v15 = v14[v3];
  if ( *v2 != v7 )
  {
    v16 = v7 + 1;
LABEL_19:
    v14[v7] = v15;
    v2[2] = v16;
    ++*v13;
    result = 256;
    goto LABEL_20;
  }
  v16 = v7 + 1;
  v17 = 2 * v7;
  if ( v7 + 1 > 2 * v7 )
    v17 = v7 + 1;
  v18 = 4;
  if ( v17 >= 5 )
    v18 = v17;
  RNvMs4_NtCsexo9QDNEsji_5alloc7raw_vecINtB5_11RawVecInnerINtCsdwtLm5uWta6_10gdi_region22ScanLookAsideAllocatorKj70_EE11finish_growCsdcpJtfrLhSH_7rgncore_llvm_18110786352924170244(
    &v21,
    v7,
    v14,
    v18,
    4u,
    4u);
  if ( (_DWORD)v21 != 1 )
  {
    v14 = v22;
    v2[1] = (unsigned __int64)v22;
    *v2 = v18;
    goto LABEL_19;
  }
  if ( v3 > v2[2] )
    goto LABEL_35;
  result = 0xE00000001LL;
  v2[2] = v3;
  if ( !v3 )
  {
    RNvNtCsdwtLm5uWta6_10gdi_region3ffi27RustOnZeroSizedScanCallback();
    result = 0xE00000001LL;
  }
LABEL_20:
  if ( _security_cookie != ((unsigned __int64)&v19 ^ v23) )
LABEL_36:
    RNvNtCs9MWeMO1rkJG_4core9panicking18panic_bounds_check(
      v3,
      v7,
      &anon_22b06d26984f22b1c5b0f9b994440758_42_llvm_8899961222222301143);
  return result;
}

```

## disassembly

```asm
0x140012770  push    r15
0x140012772  push    r14
0x140012774  push    r12
0x140012776  push    rsi
0x140012777  push    rdi
0x140012778  push    rbp
0x140012779  push    rbx
0x14001277a  sub     rsp, 60h
0x14001277e  mov     r14, rcx
0x140012781  mov     rax, cs:__security_cookie
0x140012788  xor     rax, rsp
0x14001278b  mov     [rsp+98h+var_40], rax
0x140012790  mov     rsi, [rcx]
0x140012793  mov     rdi, [rcx+10h]
0x140012797  test    rdi, rdi
0x14001279a  jz      loc_14001286E
0x1400127a0  lea     rcx, [rdi-1]
0x1400127a4  mov     rdx, [rsi+10h]
0x1400127a8  cmp     rcx, rdx
0x1400127ab  jnb     loc_1400129EB
0x1400127b1  mov     rax, [rsi+8]
0x1400127b5  movsxd  rax, dword ptr [rax+rdi*4-4]
0x1400127ba  test    rax, rax
0x1400127bd  js      loc_14001295E
0x1400127c3  mov     r15, rdi
0x1400127c6  sub     r15, rax
0x1400127c9  add     r15, 0FFFFFFFFFFFFFFFCh
0x1400127cd  mov     rcx, rsi
0x1400127d0  mov     rdx, r15
0x1400127d3  call    _RNvMNtCsdcpJtfrLhSH_7rgncore4scanINtB2_12ScanInternalQINtNtCsexo9QDNEsji_5alloc3vec3VeclINtCsdwtLm5uWta6_10gdi_region22ScanLookAsideAllocatorKj70_EEB1o_E13is_valid_scanB4__llvm_8899961222222301143
0x1400127d8  test    al, al
0x1400127da  jz      loc_140012987
0x1400127e0  mov     rbx, [rsi+10h]
0x1400127e4  cmp     r15, rbx
0x1400127e7  jnb     loc_1400129F7
0x1400127ed  lea     rcx, [r15+3]
0x1400127f1  mov     r12, [rsi+8]
0x1400127f5  movsxd  r8, dword ptr [r12+r15*4]
0x1400127f9  mov     rdx, rcx
0x1400127fc  add     rdx, r8
0x1400127ff  jb      loc_14001294F
0x140012805  cmp     rdx, rbx
0x140012808  ja      loc_14001294F
0x14001280e  lea     rax, [rdi+3]
0x140012812  mov     rdx, rbx
0x140012815  sub     rdx, rax
0x140012818  jb      loc_14001299F
0x14001281e  cmp     rdx, r8
0x140012821  jnz     short loc_140012872
0x140012823  lea     rcx, [r12+rcx*4]; Buf1
0x140012827  lea     rdx, [r12+rax*4]; Buf2
0x14001282b  shl     r8, 2; Size
0x14001282f  call    memcmp
0x140012834  test    eax, eax
0x140012836  jnz     short loc_140012872
0x140012838  lea     rcx, [rdi+2]
0x14001283c  cmp     rcx, rbx
0x14001283f  jnb     loc_140012A09
0x140012845  lea     rcx, [r15+2]
0x140012849  cmp     rcx, rbx
0x14001284c  jnb     loc_140012A18
0x140012852  mov     eax, [r12+rdi*4+8]
0x140012857  mov     [r12+r15*4+8], eax
0x14001285c  cmp     rdi, [rsi+10h]
0x140012860  ja      loc_1400129B4
0x140012866  mov     [rsi+10h], rdi
0x14001286a  xor     eax, eax
0x14001286c  jmp     short loc_1400128A0
0x14001286e  mov     rbx, [rsi+10h]
0x140012872  cmp     rdi, rbx
0x140012875  jnb     loc_1400129D9
0x14001287b  mov     r15, [r14+8]
0x14001287f  mov     r8, [rsi+8]
0x140012883  mov     ebp, [r8+rdi*4]
0x140012887  cmp     [rsi], rbx
0x14001288a  jz      short loc_1400128C7
0x14001288c  lea     r12, [rbx+1]
0x140012890  mov     [r8+rbx*4], ebp
0x140012894  mov     [rsi+10h], r12
0x140012898  inc     dword ptr [r15]
0x14001289b  mov     eax, 100h
0x1400128a0  mov     rcx, [rsp+98h+var_40]
0x1400128a5  xor     rcx, rsp
0x1400128a8  mov     rdx, cs:__security_cookie
0x1400128af  cmp     rdx, rcx
0x1400128b2  jnz     loc_1400129CC
0x1400128b8  add     rsp, 60h
0x1400128bc  pop     rbx
0x1400128bd  pop     rbp
0x1400128be  pop     rdi
0x1400128bf  pop     rsi
0x1400128c0  pop     r12
0x1400128c2  pop     r14
0x1400128c4  pop     r15
0x1400128c6  retn
0x1400128c7  lea     r12, [rbx+1]
0x1400128cb  lea     rax, [rbx+rbx]
0x1400128cf  cmp     r12, rax
0x1400128d2  cmova   rax, r12
0x1400128d6  cmp     rax, 5
0x1400128da  mov     r14d, 4
0x1400128e0  cmovnb  r14, rax
0x1400128e4  mov     [rsp+98h+var_70], 4
0x1400128ed  mov     [rsp+98h+var_78], 4
0x1400128f6  lea     rcx, [rsp+98h+var_58]
0x1400128fb  mov     rdx, rbx
0x1400128fe  mov     r9, r14
0x140012901  call    _RNvMs4_NtCsexo9QDNEsji_5alloc7raw_vecINtB5_11RawVecInnerINtCsdwtLm5uWta6_10gdi_region22ScanLookAsideAllocatorKj70_EE11finish_growCsdcpJtfrLhSH_7rgncore_llvm_18110786352924170244
0x140012906  cmp     dword ptr [rsp+98h+var_58], 1
0x14001290b  jnz     short loc_14001293E
0x14001290d  cmp     rdi, [rsi+10h]
0x140012911  ja      loc_1400129B4
0x140012917  mov     rax, 0E00000001h
0x140012921  mov     [rsi+10h], rdi
0x140012925  test    rdi, rdi
0x140012928  jnz     loc_1400128A0
0x14001292e  mov     rsi, rax
0x140012931  call    _RNvNtCsdwtLm5uWta6_10gdi_region3ffi27RustOnZeroSizedScanCallback
0x140012936  mov     rax, rsi
0x140012939  jmp     loc_1400128A0
0x14001293e  mov     r8, [rsp+98h+var_50]
0x140012943  mov     [rsi+8], r8
0x140012947  mov     [rsi], r14
0x14001294a  jmp     loc_140012890
0x14001294f  lea     r9, anon_22b06d26984f22b1c5b0f9b994440758_16_llvm_8899961222222301143
0x140012956  mov     r8, rbx
0x140012959  call    _RNvNtNtCs9MWeMO1rkJG_4core5slice5index16slice_index_fail
0x14001295e  lea     rax, off_14001BFD8; "rgncore\\src\\scan.rs"
0x140012965  mov     [rsp+98h+var_78], rax
0x14001296a  lea     rcx, anon_22b06d26984f22b1c5b0f9b994440758_6_llvm_8899961222222301143
0x140012971  lea     r9, anon_22b06d26984f22b1c5b0f9b994440758_5_llvm_8899961222222301143
0x140012978  lea     r8, [rsp+98h+var_59]
0x14001297d  mov     edx, 2Bh ; '+'
0x140012982  call    _RNvNtCs9MWeMO1rkJG_4core6result13unwrap_failed
0x140012987  lea     rcx, anon_22b06d26984f22b1c5b0f9b994440758_43_llvm_8899961222222301143+2Ah; "assertion failed: ScanInternal::is_vali"...
0x14001298e  lea     r8, off_14001BFF0; "rgncore\\src\\scan.rs"
0x140012995  mov     edx, 50h ; 'P'
0x14001299a  call    _RNvNtCs9MWeMO1rkJG_4core9panicking5panic
0x14001299f  lea     r9, anon_22b06d26984f22b1c5b0f9b994440758_51_llvm_8899961222222301143
0x1400129a6  mov     rcx, rax
0x1400129a9  mov     rdx, rbx
0x1400129ac  mov     r8, rbx
0x1400129af  call    _RNvNtNtCs9MWeMO1rkJG_4core5slice5index16slice_index_fail
0x1400129b4  lea     rcx, anon_22b06d26984f22b1c5b0f9b994440758_43_llvm_8899961222222301143; "assertion failed: index <= scan_data.le"...
0x1400129bb  lea     r8, anon_22b06d26984f22b1c5b0f9b994440758_44_llvm_8899961222222301143
0x1400129c2  mov     edx, 2Ah ; '*'
0x1400129c7  call    _RNvNtCs9MWeMO1rkJG_4core9panicking5panic
0x1400129cc  mov     rcx, [rsp+98h+var_40]
0x1400129d1  xor     rcx, rsp; StackCookie
0x1400129d4  call    __security_check_cookie
0x1400129d9  lea     r8, anon_22b06d26984f22b1c5b0f9b994440758_42_llvm_8899961222222301143
0x1400129e0  mov     rcx, rdi
0x1400129e3  mov     rdx, rbx
0x1400129e6  call    _RNvNtCs9MWeMO1rkJG_4core9panicking18panic_bounds_check
0x1400129eb  lea     r8, off_14001BFC0; "rgncore\\src\\scan.rs"
0x1400129f2  call    _RNvNtCs9MWeMO1rkJG_4core9panicking18panic_bounds_check
0x1400129f7  lea     r8, anon_22b06d26984f22b1c5b0f9b994440758_2_llvm_8899961222222301143
0x1400129fe  mov     rcx, r15
0x140012a01  mov     rdx, rbx
0x140012a04  call    _RNvNtCs9MWeMO1rkJG_4core9panicking18panic_bounds_check
0x140012a09  lea     r8, off_14001C008; "rgncore\\src\\scan.rs"
0x140012a10  mov     rdx, rbx
0x140012a13  call    _RNvNtCs9MWeMO1rkJG_4core9panicking18panic_bounds_check
0x140012a18  lea     r8, off_14001C020; "rgncore\\src\\scan.rs"
0x140012a1f  mov     rdx, rbx
0x140012a22  call    _RNvNtCs9MWeMO1rkJG_4core9panicking18panic_bounds_check
```
