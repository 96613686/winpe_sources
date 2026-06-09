# _RNvMNtCsdcpJtfrLhSH_7rgncore4scanINtB2_12ScanInternalRINtNtCsexo9QDNEsji_5alloc3vec3VeclINtCsdwtLm5uWta6_10gdi_region22ScanLookAsideAllocatorKj70_EEB1o_E6x_wallCs7vXzV21FY6F_8gdi_rust

- ea: `0x14000f6b0`
- end: `0x14000f71a`
- name: `_RNvMNtCsdcpJtfrLhSH_7rgncore4scanINtB2_12ScanInternalRINtNtCsexo9QDNEsji_5alloc3vec3VeclINtCsdwtLm5uWta6_10gdi_region22ScanLookAsideAllocatorKj70_EEB1o_E6x_wallCs7vXzV21FY6F_8gdi_rust`
- size: `106`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation`

## callers

- `0x140011120`

## callees

- `0x14000f6b0`
- `0x1400184d7`
- `0x140018630`

## pseudocode

```c
__int64 __fastcall RNvMNtCsdcpJtfrLhSH_7rgncore4scanINtB2_12ScanInternalRINtNtCsexo9QDNEsji_5alloc3vec3VeclINtCsdwtLm5uWta6_10gdi_region22ScanLookAsideAllocatorKj70_EEB1o_E6x_wallCs7vXzV21FY6F_8gdi_rust(
        __int64 *a1,
        unsigned __int64 a2)
{
  __int64 v3; // r8
  unsigned __int64 v4; // rcx
  unsigned __int64 v5; // rdx
  __int64 v6; // r8
  unsigned __int64 v7; // rcx

  v3 = *a1;
  v4 = a1[1];
  v5 = *(_QWORD *)(v3 + 16);
  if ( v4 >= v5 )
    RNvNtCs9MWeMO1rkJG_4core9panicking18panic_bounds_check(
      v4,
      v5,
      &anon_01189c164b0c425bf67614ee34d1a89c_1_llvm_7541658972310832757);
  v6 = *(_QWORD *)(v3 + 8);
  if ( a2 >= *(int *)(v6 + 4 * v4) )
    RNvNtCs9MWeMO1rkJG_4core9panicking5panic(
      anon_01189c164b0c425bf67614ee34d1a89c_11_llvm_7541658972310832757,
      43,
      &anon_01189c164b0c425bf67614ee34d1a89c_12_llvm_7541658972310832757);
  v7 = a2 + v4 + 3;
  if ( v7 >= v5 )
    RNvNtCs9MWeMO1rkJG_4core9panicking18panic_bounds_check(
      v7,
      v5,
      &anon_01189c164b0c425bf67614ee34d1a89c_13_llvm_7541658972310832757);
  return *(unsigned int *)(v6 + 4 * v7);
}

```

## disassembly

```asm
0x14000f6b0  sub     rsp, 28h
0x14000f6b4  mov     rax, rdx
0x14000f6b7  mov     r8, [rcx]
0x14000f6ba  mov     rcx, [rcx+8]
0x14000f6be  mov     rdx, [r8+10h]
0x14000f6c2  cmp     rcx, rdx
0x14000f6c5  jnb     short loc_14000F701
0x14000f6c7  mov     r8, [r8+8]
0x14000f6cb  movsxd  r9, dword ptr [r8+rcx*4]
0x14000f6cf  cmp     rax, r9
0x14000f6d2  jnb     short loc_14000F6E9
0x14000f6d4  add     rcx, rax
0x14000f6d7  add     rcx, 3
0x14000f6db  cmp     rcx, rdx
0x14000f6de  jnb     short loc_14000F70D
0x14000f6e0  mov     eax, [r8+rcx*4]
0x14000f6e4  add     rsp, 28h
0x14000f6e8  retn
0x14000f6e9  lea     rcx, anon_01189c164b0c425bf67614ee34d1a89c_11_llvm_7541658972310832757
0x14000f6f0  lea     r8, anon_01189c164b0c425bf67614ee34d1a89c_12_llvm_7541658972310832757
0x14000f6f7  mov     edx, 2Bh ; '+'
0x14000f6fc  call    _RNvNtCs9MWeMO1rkJG_4core9panicking5panic
0x14000f701  lea     r8, anon_01189c164b0c425bf67614ee34d1a89c_1_llvm_7541658972310832757
0x14000f708  call    _RNvNtCs9MWeMO1rkJG_4core9panicking18panic_bounds_check
0x14000f70d  lea     r8, anon_01189c164b0c425bf67614ee34d1a89c_13_llvm_7541658972310832757
0x14000f714  call    _RNvNtCs9MWeMO1rkJG_4core9panicking18panic_bounds_check
```
