# _RNvMNtCsdcpJtfrLhSH_7rgncore4scanINtB2_12ScanInternalQINtNtCsexo9QDNEsji_5alloc3vec3VeclINtCsdwtLm5uWta6_10gdi_region22ScanLookAsideAllocatorKj70_EEB1o_E7x_wallsB4_

- ea: `0x140012320`
- end: `0x140012378`
- name: `_RNvMNtCsdcpJtfrLhSH_7rgncore4scanINtB2_12ScanInternalQINtNtCsexo9QDNEsji_5alloc3vec3VeclINtCsdwtLm5uWta6_10gdi_region22ScanLookAsideAllocatorKj70_EEB1o_E7x_wallsB4_`
- size: `88`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation`

## callers

- `0x14000cc10`

## callees

- `0x140012320`
- `0x1400184d7`
- `0x140018690`

## pseudocode

```c
__int64 __fastcall RNvMNtCsdcpJtfrLhSH_7rgncore4scanINtB2_12ScanInternalQINtNtCsexo9QDNEsji_5alloc3vec3VeclINtCsdwtLm5uWta6_10gdi_region22ScanLookAsideAllocatorKj70_EEB1o_E7x_wallsB4_(
        __int64 *a1)
{
  __int64 v1; // rax
  unsigned __int64 v2; // rcx
  unsigned __int64 v3; // r8
  __int64 v4; // r9
  __int64 v5; // rdx
  unsigned __int64 v6; // rcx

  v1 = *a1;
  v2 = a1[1];
  v3 = *(_QWORD *)(v1 + 16);
  if ( v2 >= v3 )
    RNvNtCs9MWeMO1rkJG_4core9panicking18panic_bounds_check(
      v2,
      v3,
      &anon_22b06d26984f22b1c5b0f9b994440758_2_llvm_8899961222222301143);
  v4 = *(_QWORD *)(v1 + 8);
  v5 = *(int *)(v4 + 4 * v2);
  v6 = v2 + 3;
  if ( __CFADD__(v5, v6) || v5 + v6 > v3 )
    RNvNtNtCs9MWeMO1rkJG_4core5slice5index16slice_index_fail(
      v6,
      v5 + v6,
      v3,
      &anon_22b06d26984f22b1c5b0f9b994440758_16_llvm_8899961222222301143);
  return v4 + 4 * v6;
}

```

## disassembly

```asm
0x140012320  sub     rsp, 28h
0x140012324  mov     rax, [rcx]
0x140012327  mov     rcx, [rcx+8]
0x14001232b  mov     r8, [rax+10h]
0x14001232f  cmp     rcx, r8
0x140012332  jnb     short loc_140012365
0x140012334  mov     r9, [rax+8]
0x140012338  movsxd  rdx, dword ptr [r9+rcx*4]
0x14001233c  add     rcx, 3
0x140012340  mov     rax, rcx
0x140012343  add     rax, rdx
0x140012346  jb      short loc_140012356
0x140012348  cmp     rax, r8
0x14001234b  ja      short loc_140012356
0x14001234d  lea     rax, [r9+rcx*4]
0x140012351  add     rsp, 28h
0x140012355  retn
0x140012356  lea     r9, anon_22b06d26984f22b1c5b0f9b994440758_16_llvm_8899961222222301143
0x14001235d  mov     rdx, rax
0x140012360  call    _RNvNtNtCs9MWeMO1rkJG_4core5slice5index16slice_index_fail
0x140012365  lea     rax, anon_22b06d26984f22b1c5b0f9b994440758_2_llvm_8899961222222301143
0x14001236c  mov     rdx, r8
0x14001236f  mov     r8, rax
0x140012372  call    _RNvNtCs9MWeMO1rkJG_4core9panicking18panic_bounds_check
```
