# _RNvMNtCsdcpJtfrLhSH_7rgncore4scanINtB2_12ScanInternalRINtNtCsexo9QDNEsji_5alloc3vec3VeclINtCsdwtLm5uWta6_10gdi_region22ScanLookAsideAllocatorKj70_EEB1o_E8first_ofB4_

- ea: `0x140012380`
- end: `0x1400123b7`
- name: `_RNvMNtCsdcpJtfrLhSH_7rgncore4scanINtB2_12ScanInternalRINtNtCsexo9QDNEsji_5alloc3vec3VeclINtCsdwtLm5uWta6_10gdi_region22ScanLookAsideAllocatorKj70_EEB1o_E8first_ofB4_`
- size: `55`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `2`
- callee_count: `3`
- tags: `authz_impersonation`

## callers

- `0x14000cc10`
- `0x14000e720`

## callees

- `0x1400120f0`
- `0x140012380`
- `0x140018630`

## pseudocode

```c
__int64 __fastcall RNvMNtCsdcpJtfrLhSH_7rgncore4scanINtB2_12ScanInternalRINtNtCsexo9QDNEsji_5alloc3vec3VeclINtCsdwtLm5uWta6_10gdi_region22ScanLookAsideAllocatorKj70_EEB1o_E8first_ofB4_(
        __int64 a1)
{
  if ( !RNvMNtCsdcpJtfrLhSH_7rgncore4scanINtB2_12ScanInternalQINtNtCsexo9QDNEsji_5alloc3vec3VeclINtCsdwtLm5uWta6_10gdi_region22ScanLookAsideAllocatorKj70_EEB1o_E13is_valid_scanB4__llvm_8899961222222301143(
          a1,
          0) )
    RNvNtCs9MWeMO1rkJG_4core9panicking5panic(
      &anon_22b06d26984f22b1c5b0f9b994440758_17_llvm_8899961222222301143,
      52,
      &anon_22b06d26984f22b1c5b0f9b994440758_18_llvm_8899961222222301143);
  return a1;
}

```

## disassembly

```asm
0x140012380  push    rsi
0x140012381  sub     rsp, 20h
0x140012385  mov     rsi, rcx
0x140012388  xor     edx, edx
0x14001238a  call    _RNvMNtCsdcpJtfrLhSH_7rgncore4scanINtB2_12ScanInternalQINtNtCsexo9QDNEsji_5alloc3vec3VeclINtCsdwtLm5uWta6_10gdi_region22ScanLookAsideAllocatorKj70_EEB1o_E13is_valid_scanB4__llvm_8899961222222301143
0x14001238f  test    al, al
0x140012391  jz      short loc_14001239E
0x140012393  mov     rax, rsi
0x140012396  xor     edx, edx
0x140012398  add     rsp, 20h
0x14001239c  pop     rsi
0x14001239d  retn
0x14001239e  lea     rcx, anon_22b06d26984f22b1c5b0f9b994440758_17_llvm_8899961222222301143
0x1400123a5  lea     r8, anon_22b06d26984f22b1c5b0f9b994440758_18_llvm_8899961222222301143
0x1400123ac  mov     edx, 34h ; '4'
0x1400123b1  call    _RNvNtCs9MWeMO1rkJG_4core9panicking5panic
```
