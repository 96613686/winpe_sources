# _RNvMs4_NtCsdcpJtfrLhSH_7rgncore4scanINtB5_11ScanBuilderINtCsdwtLm5uWta6_10gdi_region22ScanLookAsideAllocatorKj70_EE18commit_or_coalesceCs7vXzV21FY6F_8gdi_rust

- ea: `0x14000f800`
- end: `0x14000faa0`
- name: `_RNvMs4_NtCsdcpJtfrLhSH_7rgncore4scanINtB5_11ScanBuilderINtCsdwtLm5uWta6_10gdi_region22ScanLookAsideAllocatorKj70_EE18commit_or_coalesceCs7vXzV21FY6F_8gdi_rust`
- size: `672`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `1`
- callee_count: `10`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1400101f0`

## callees

- `0x14000f5b0`
- `0x14000f800`
- `0x14000fdc0`
- `0x140017a10`
- `0x140017dd0`
- `0x140018470`
- `0x1400184d7`
- `0x140018630`
- `0x140018690`
- `0x140018ab0`

## pseudocode

```c
__int64 __fastcall RNvMs4_NtCsdcpJtfrLhSH_7rgncore4scanINtB5_11ScanBuilderINtCsdwtLm5uWta6_10gdi_region22ScanLookAsideAllocatorKj70_EE18commit_or_coalesceCs7vXzV21FY6F_8gdi_rust(
        __int64 a1)
{
  __int64 *v2; // rsi
  unsigned __int64 v3; // rdi
  unsigned __int64 v4; // rdx
  __int64 v5; // rax
  unsigned __int64 v6; // r15
  unsigned __int64 v7; // rbx
  unsigned __int64 v8; // rcx
  __int64 v9; // r12
  __int64 v10; // r8
  unsigned __int64 v11; // rdx
  __int64 result; // rax
  _DWORD *v13; // r15
  __int64 v14; // rax
  int v15; // ebp
  __int64 v16; // r14
  __int64 v17; // [rsp+0h] [rbp-88h] BYREF
  char v18; // [rsp+2Fh] [rbp-59h] BYREF
  int v19; // [rsp+30h] [rbp-58h] BYREF
  __int64 v20; // [rsp+38h] [rbp-50h]
  __int64 v21; // [rsp+48h] [rbp-40h]

  v2 = *(__int64 **)a1;
  v3 = *(_QWORD *)(a1 + 16);
  if ( v3 )
  {
    v4 = v2[2];
    if ( v3 - 1 >= v4 )
      RNvNtCs9MWeMO1rkJG_4core9panicking18panic_bounds_check(v3 - 1, v4, &off_14001B998);
    v5 = *(int *)(v2[1] + 4 * v3 - 4);
    if ( v5 < 0 )
      RNvNtCs9MWeMO1rkJG_4core6result13unwrap_failed(
        (unsigned int)&anon_01189c164b0c425bf67614ee34d1a89c_5_llvm_7541658972310832757,
        43,
        (unsigned int)&v18,
        (unsigned int)anon_01189c164b0c425bf67614ee34d1a89c_4_llvm_7541658972310832757,
        (__int64)&off_14001B9B0);
    v6 = v3 - v5 - 4;
    if ( !(unsigned __int8)RNvMNtCsdcpJtfrLhSH_7rgncore4scanINtB2_12ScanInternalRINtNtCsexo9QDNEsji_5alloc3vec3VeclINtCsdwtLm5uWta6_10gdi_region22ScanLookAsideAllocatorKj70_EEB1o_E13is_valid_scanCs7vXzV21FY6F_8gdi_rust_llvm_7541658972310832757(
                             v2,
                             v6) )
      RNvNtCs9MWeMO1rkJG_4core9panicking5panic(&byte_14001CF5F, 80, &off_14001B9C8);
    v7 = v2[2];
    if ( v6 >= v7 )
      RNvNtCs9MWeMO1rkJG_4core9panicking18panic_bounds_check(
        v6,
        v2[2],
        &anon_01189c164b0c425bf67614ee34d1a89c_1_llvm_7541658972310832757);
    v8 = v6 + 3;
    v9 = v2[1];
    v10 = *(int *)(v9 + 4 * v6);
    v11 = v10 + v6 + 3;
    if ( __CFADD__(v10, v6 + 3) || v11 > v7 )
      RNvNtNtCs9MWeMO1rkJG_4core5slice5index16slice_index_fail(v8, v11, v2[2], &off_14001B908);
    if ( v7 < v3 + 3 )
      RNvNtNtCs9MWeMO1rkJG_4core5slice5index16slice_index_fail(
        v3 + 3,
        v2[2],
        v2[2],
        &anon_01189c164b0c425bf67614ee34d1a89c_27_llvm_7541658972310832757);
    if ( v7 - (v3 + 3) == v10 && !memcmp((const void *)(v9 + 4 * v8), (const void *)(v9 + 4 * (v3 + 3)), 4 * v10) )
    {
      if ( v3 + 2 >= v7 )
        RNvNtCs9MWeMO1rkJG_4core9panicking18panic_bounds_check(v3 + 2, v7, &off_14001B9E0);
      if ( v6 + 2 >= v7 )
        RNvNtCs9MWeMO1rkJG_4core9panicking18panic_bounds_check(v6 + 2, v7, &off_14001B9F8);
      *(_DWORD *)(v9 + 4 * v6 + 8) = *(_DWORD *)(v9 + 4 * v3 + 8);
      if ( v3 <= v2[2] )
      {
        v2[2] = v3;
        result = 0;
        goto LABEL_19;
      }
LABEL_32:
      RNvNtCs9MWeMO1rkJG_4core9panicking5panic(
        anon_01189c164b0c425bf67614ee34d1a89c_19_llvm_7541658972310832757,
        42,
        &anon_01189c164b0c425bf67614ee34d1a89c_20_llvm_7541658972310832757);
    }
  }
  else
  {
    v7 = v2[2];
  }
  if ( v3 >= v7 )
    goto LABEL_33;
  v13 = *(_DWORD **)(a1 + 8);
  v14 = v2[1];
  v15 = *(_DWORD *)(v14 + 4 * v3);
  if ( *v2 != v7 )
    goto LABEL_18;
  v16 = 4;
  if ( 2 * v7 >= 5 )
    v16 = 2 * v7;
  RNvMs4_NtCsexo9QDNEsji_5alloc7raw_vecINtB5_11RawVecInnerINtCsdwtLm5uWta6_10gdi_region22ScanLookAsideAllocatorKj70_EE11finish_growCs7vXzV21FY6F_8gdi_rust_llvm_1180095224807683263(
    (unsigned int)&v19,
    (_DWORD)v2,
    v16,
    4,
    4);
  if ( v19 != 1 )
  {
    v14 = v20;
    v2[1] = v20;
    *v2 = v16;
LABEL_18:
    *(_DWORD *)(v14 + 4 * v7) = v15;
    ++v2[2];
    ++*v13;
    result = 256;
    goto LABEL_19;
  }
  if ( v3 > v2[2] )
    goto LABEL_32;
  result = 0xE00000001LL;
  v2[2] = v3;
  if ( !v3 )
  {
    RNvNtCsdwtLm5uWta6_10gdi_region3ffi27RustOnZeroSizedScanCallback();
    result = 0xE00000001LL;
  }
LABEL_19:
  if ( _security_cookie != ((unsigned __int64)&v17 ^ v21) )
LABEL_33:
    RNvNtCs9MWeMO1rkJG_4core9panicking18panic_bounds_check(v3, v7, &off_14001B968);
  return result;
}

```

## disassembly

```asm
0x14000f800  push    r15
0x14000f802  push    r14
0x14000f804  push    r12
0x14000f806  push    rsi
0x14000f807  push    rdi
0x14000f808  push    rbp
0x14000f809  push    rbx
0x14000f80a  sub     rsp, 50h
0x14000f80e  mov     r14, rcx
0x14000f811  mov     rax, cs:__security_cookie
0x14000f818  xor     rax, rsp
0x14000f81b  mov     [rsp+88h+var_40], rax
0x14000f820  mov     rsi, [rcx]
0x14000f823  mov     rdi, [rcx+10h]
0x14000f827  test    rdi, rdi
0x14000f82a  jz      loc_14000F8FE
0x14000f830  lea     rcx, [rdi-1]
0x14000f834  mov     rdx, [rsi+10h]
0x14000f838  cmp     rcx, rdx
0x14000f83b  jnb     loc_14000FA63
0x14000f841  mov     rax, [rsi+8]
0x14000f845  movsxd  rax, dword ptr [rax+rdi*4-4]
0x14000f84a  test    rax, rax
0x14000f84d  js      loc_14000F9D6
0x14000f853  mov     r15, rdi
0x14000f856  sub     r15, rax
0x14000f859  add     r15, 0FFFFFFFFFFFFFFFCh
0x14000f85d  mov     rcx, rsi
0x14000f860  mov     rdx, r15
0x14000f863  call    _RNvMNtCsdcpJtfrLhSH_7rgncore4scanINtB2_12ScanInternalRINtNtCsexo9QDNEsji_5alloc3vec3VeclINtCsdwtLm5uWta6_10gdi_region22ScanLookAsideAllocatorKj70_EEB1o_E13is_valid_scanCs7vXzV21FY6F_8gdi_rust_llvm_7541658972310832757
0x14000f868  test    al, al
0x14000f86a  jz      loc_14000F9FF
0x14000f870  mov     rbx, [rsi+10h]
0x14000f874  cmp     r15, rbx
0x14000f877  jnb     loc_14000FA6F
0x14000f87d  lea     rcx, [r15+3]
0x14000f881  mov     r12, [rsi+8]
0x14000f885  movsxd  r8, dword ptr [r12+r15*4]
0x14000f889  mov     rdx, rcx
0x14000f88c  add     rdx, r8
0x14000f88f  jb      loc_14000F9C7
0x14000f895  cmp     rdx, rbx
0x14000f898  ja      loc_14000F9C7
0x14000f89e  lea     rax, [rdi+3]
0x14000f8a2  mov     rdx, rbx
0x14000f8a5  sub     rdx, rax
0x14000f8a8  jb      loc_14000FA17
0x14000f8ae  cmp     rdx, r8
0x14000f8b1  jnz     short loc_14000F902
0x14000f8b3  lea     rcx, [r12+rcx*4]; Buf1
0x14000f8b7  lea     rdx, [r12+rax*4]; Buf2
0x14000f8bb  shl     r8, 2; Size
0x14000f8bf  call    memcmp
0x14000f8c4  test    eax, eax
0x14000f8c6  jnz     short loc_14000F902
0x14000f8c8  lea     rcx, [rdi+2]
0x14000f8cc  cmp     rcx, rbx
0x14000f8cf  jnb     loc_14000FA81
0x14000f8d5  lea     rcx, [r15+2]
0x14000f8d9  cmp     rcx, rbx
0x14000f8dc  jnb     loc_14000FA90
0x14000f8e2  mov     eax, [r12+rdi*4+8]
0x14000f8e7  mov     [r12+r15*4+8], eax
0x14000f8ec  cmp     rdi, [rsi+10h]
0x14000f8f0  ja      loc_14000FA2C
0x14000f8f6  mov     [rsi+10h], rdi
0x14000f8fa  xor     eax, eax
0x14000f8fc  jmp     short loc_14000F92A
0x14000f8fe  mov     rbx, [rsi+10h]
0x14000f902  cmp     rdi, rbx
0x14000f905  jnb     loc_14000FA51
0x14000f90b  mov     r15, [r14+8]
0x14000f90f  mov     rax, [rsi+8]
0x14000f913  mov     ebp, [rax+rdi*4]
0x14000f916  cmp     [rsi], rbx
0x14000f919  jz      short loc_14000F951
0x14000f91b  mov     [rax+rbx*4], ebp
0x14000f91e  inc     qword ptr [rsi+10h]
0x14000f922  inc     dword ptr [r15]
0x14000f925  mov     eax, 100h
0x14000f92a  mov     rcx, [rsp+88h+var_40]
0x14000f92f  xor     rcx, rsp
0x14000f932  mov     rdx, cs:__security_cookie
0x14000f939  cmp     rdx, rcx
0x14000f93c  jnz     loc_14000FA44
0x14000f942  add     rsp, 50h
0x14000f946  pop     rbx
0x14000f947  pop     rbp
0x14000f948  pop     rdi
0x14000f949  pop     rsi
0x14000f94a  pop     r12
0x14000f94c  pop     r14
0x14000f94e  pop     r15
0x14000f950  retn
0x14000f951  lea     rax, [rbx+rbx]
0x14000f955  cmp     rax, 5
0x14000f959  mov     r14d, 4
0x14000f95f  cmovnb  r14, rax
0x14000f963  mov     [rsp+88h+var_68], 4
0x14000f96c  lea     rcx, [rsp+88h+var_58]
0x14000f971  mov     r9d, 4
0x14000f977  mov     rdx, rsi
0x14000f97a  mov     r8, r14
0x14000f97d  call    _RNvMs4_NtCsexo9QDNEsji_5alloc7raw_vecINtB5_11RawVecInnerINtCsdwtLm5uWta6_10gdi_region22ScanLookAsideAllocatorKj70_EE11finish_growCs7vXzV21FY6F_8gdi_rust_llvm_1180095224807683263
0x14000f982  cmp     [rsp+88h+var_58], 1
0x14000f987  jnz     short loc_14000F9B6
0x14000f989  cmp     rdi, [rsi+10h]
0x14000f98d  ja      loc_14000FA2C
0x14000f993  mov     rax, 0E00000001h
0x14000f99d  mov     [rsi+10h], rdi
0x14000f9a1  test    rdi, rdi
0x14000f9a4  jnz     short loc_14000F92A
0x14000f9a6  mov     rsi, rax
0x14000f9a9  call    _RNvNtCsdwtLm5uWta6_10gdi_region3ffi27RustOnZeroSizedScanCallback
0x14000f9ae  mov     rax, rsi
0x14000f9b1  jmp     loc_14000F92A
0x14000f9b6  mov     rax, [rsp+88h+var_50]
0x14000f9bb  mov     [rsi+8], rax
0x14000f9bf  mov     [rsi], r14
0x14000f9c2  jmp     loc_14000F91B
0x14000f9c7  lea     r9, off_14001B908; "rgncore\\src\\scan.rs"
0x14000f9ce  mov     r8, rbx
0x14000f9d1  call    _RNvNtNtCs9MWeMO1rkJG_4core5slice5index16slice_index_fail
0x14000f9d6  lea     rax, off_14001B9B0; "rgncore\\src\\scan.rs"
0x14000f9dd  mov     [rsp+88h+var_68], rax
0x14000f9e2  lea     rcx, anon_01189c164b0c425bf67614ee34d1a89c_5_llvm_7541658972310832757
0x14000f9e9  lea     r9, anon_01189c164b0c425bf67614ee34d1a89c_4_llvm_7541658972310832757
0x14000f9f0  lea     r8, [rsp+88h+var_59]
0x14000f9f5  mov     edx, 2Bh ; '+'
0x14000f9fa  call    _RNvNtCs9MWeMO1rkJG_4core6result13unwrap_failed
0x14000f9ff  lea     rcx, byte_14001CF5F
0x14000fa06  lea     r8, off_14001B9C8; "rgncore\\src\\scan.rs"
0x14000fa0d  mov     edx, 50h ; 'P'
0x14000fa12  call    _RNvNtCs9MWeMO1rkJG_4core9panicking5panic
0x14000fa17  lea     r9, anon_01189c164b0c425bf67614ee34d1a89c_27_llvm_7541658972310832757
0x14000fa1e  mov     rcx, rax
0x14000fa21  mov     rdx, rbx
0x14000fa24  mov     r8, rbx
0x14000fa27  call    _RNvNtNtCs9MWeMO1rkJG_4core5slice5index16slice_index_fail
0x14000fa2c  lea     rcx, anon_01189c164b0c425bf67614ee34d1a89c_19_llvm_7541658972310832757
0x14000fa33  lea     r8, anon_01189c164b0c425bf67614ee34d1a89c_20_llvm_7541658972310832757
0x14000fa3a  mov     edx, 2Ah ; '*'
0x14000fa3f  call    _RNvNtCs9MWeMO1rkJG_4core9panicking5panic
0x14000fa44  mov     rcx, [rsp+88h+var_40]
0x14000fa49  xor     rcx, rsp; StackCookie
0x14000fa4c  call    __security_check_cookie
0x14000fa51  lea     r8, off_14001B968; "rgncore\\src\\scan.rs"
0x14000fa58  mov     rcx, rdi
0x14000fa5b  mov     rdx, rbx
0x14000fa5e  call    _RNvNtCs9MWeMO1rkJG_4core9panicking18panic_bounds_check
0x14000fa63  lea     r8, off_14001B998; "rgncore\\src\\scan.rs"
0x14000fa6a  call    _RNvNtCs9MWeMO1rkJG_4core9panicking18panic_bounds_check
0x14000fa6f  lea     r8, anon_01189c164b0c425bf67614ee34d1a89c_1_llvm_7541658972310832757
0x14000fa76  mov     rcx, r15
0x14000fa79  mov     rdx, rbx
0x14000fa7c  call    _RNvNtCs9MWeMO1rkJG_4core9panicking18panic_bounds_check
0x14000fa81  lea     r8, off_14001B9E0; "rgncore\\src\\scan.rs"
0x14000fa88  mov     rdx, rbx
0x14000fa8b  call    _RNvNtCs9MWeMO1rkJG_4core9panicking18panic_bounds_check
0x14000fa90  lea     r8, off_14001B9F8; "rgncore\\src\\scan.rs"
0x14000fa97  mov     rdx, rbx
0x14000fa9a  call    _RNvNtCs9MWeMO1rkJG_4core9panicking18panic_bounds_check
```
