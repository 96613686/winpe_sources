# _RNvMNtCsdcpJtfrLhSH_7rgncore4scanINtB2_12ScanInternalRINtNtCsexo9QDNEsji_5alloc3vec3VeclINtCsdwtLm5uWta6_10gdi_region22ScanLookAsideAllocatorKj70_EEB1o_E6x_wallB4_

- ea: `0x1400121f0`
- end: `0x14001225a`
- name: `_RNvMNtCsdcpJtfrLhSH_7rgncore4scanINtB2_12ScanInternalRINtNtCsexo9QDNEsji_5alloc3vec3VeclINtCsdwtLm5uWta6_10gdi_region22ScanLookAsideAllocatorKj70_EEB1o_E6x_wallB4_`
- size: `106`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation`

## callers

- `0x14000cc10`

## callees

- `0x1400121f0`
- `0x1400184d7`
- `0x140018630`

## pseudocode

```c
__int64 __fastcall RNvMNtCsdcpJtfrLhSH_7rgncore4scanINtB2_12ScanInternalRINtNtCsexo9QDNEsji_5alloc3vec3VeclINtCsdwtLm5uWta6_10gdi_region22ScanLookAsideAllocatorKj70_EEB1o_E6x_wallB4_(
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
      &anon_22b06d26984f22b1c5b0f9b994440758_2_llvm_8899961222222301143);
  v6 = *(_QWORD *)(v3 + 8);
  if ( a2 >= *(int *)(v6 + 4 * v4) )
    RNvNtCs9MWeMO1rkJG_4core9panicking5panic(
      &anon_22b06d26984f22b1c5b0f9b994440758_12_llvm_8899961222222301143,
      43,
      &anon_22b06d26984f22b1c5b0f9b994440758_13_llvm_8899961222222301143);
  v7 = a2 + v4 + 3;
  if ( v7 >= v5 )
    RNvNtCs9MWeMO1rkJG_4core9panicking18panic_bounds_check(
      v7,
      v5,
      &anon_22b06d26984f22b1c5b0f9b994440758_14_llvm_8899961222222301143);
  return *(unsigned int *)(v6 + 4 * v7);
}

```

## disassembly

```asm
0x1400121f0  sub     rsp, 28h
0x1400121f4  mov     rax, rdx
0x1400121f7  mov     r8, [rcx]
0x1400121fa  mov     rcx, [rcx+8]
0x1400121fe  mov     rdx, [r8+10h]
0x140012202  cmp     rcx, rdx
0x140012205  jnb     short loc_140012241
0x140012207  mov     r8, [r8+8]
0x14001220b  movsxd  r9, dword ptr [r8+rcx*4]
0x14001220f  cmp     rax, r9
0x140012212  jnb     short loc_140012229
0x140012214  add     rcx, rax
0x140012217  add     rcx, 3
0x14001221b  cmp     rcx, rdx
0x14001221e  jnb     short loc_14001224D
0x140012220  mov     eax, [r8+rcx*4]
0x140012224  add     rsp, 28h
0x140012228  retn
0x140012229  lea     rcx, anon_22b06d26984f22b1c5b0f9b994440758_12_llvm_8899961222222301143
0x140012230  lea     r8, anon_22b06d26984f22b1c5b0f9b994440758_13_llvm_8899961222222301143
0x140012237  mov     edx, 2Bh ; '+'
0x14001223c  call    _RNvNtCs9MWeMO1rkJG_4core9panicking5panic
0x140012241  lea     r8, anon_22b06d26984f22b1c5b0f9b994440758_2_llvm_8899961222222301143
0x140012248  call    _RNvNtCs9MWeMO1rkJG_4core9panicking18panic_bounds_check
0x14001224d  lea     r8, anon_22b06d26984f22b1c5b0f9b994440758_14_llvm_8899961222222301143
0x140012254  call    _RNvNtCs9MWeMO1rkJG_4core9panicking18panic_bounds_check
```
