# _RNvMNtCsdcpJtfrLhSH_7rgncore4scanINtB2_12ScanInternalRINtNtCsexo9QDNEsji_5alloc3vec3VeclINtCsdwtLm5uWta6_10gdi_region22ScanLookAsideAllocatorKj70_EEB1o_E4nextB4_

- ea: `0x1400123c0`
- end: `0x140012412`
- name: `_RNvMNtCsdcpJtfrLhSH_7rgncore4scanINtB2_12ScanInternalRINtNtCsexo9QDNEsji_5alloc3vec3VeclINtCsdwtLm5uWta6_10gdi_region22ScanLookAsideAllocatorKj70_EEB1o_E4nextB4_`
- size: `82`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation`

## callers

- `0x14000cc10`

## callees

- `0x1400120f0`
- `0x1400123c0`
- `0x1400184d7`

## pseudocode

```c
__int64 __fastcall RNvMNtCsdcpJtfrLhSH_7rgncore4scanINtB2_12ScanInternalRINtNtCsexo9QDNEsji_5alloc3vec3VeclINtCsdwtLm5uWta6_10gdi_region22ScanLookAsideAllocatorKj70_EEB1o_E4nextB4_(
        __int64 a1,
        unsigned __int64 a2)
{
  unsigned __int64 v2; // rax
  char valid; // al
  __int64 v5; // rcx

  v2 = *(_QWORD *)(a1 + 16);
  if ( a2 >= v2 )
    RNvNtCs9MWeMO1rkJG_4core9panicking18panic_bounds_check(
      a2,
      v2,
      &anon_22b06d26984f22b1c5b0f9b994440758_2_llvm_8899961222222301143);
  valid = RNvMNtCsdcpJtfrLhSH_7rgncore4scanINtB2_12ScanInternalQINtNtCsexo9QDNEsji_5alloc3vec3VeclINtCsdwtLm5uWta6_10gdi_region22ScanLookAsideAllocatorKj70_EEB1o_E13is_valid_scanB4__llvm_8899961222222301143(
            a1,
            a2 + *(int *)(*(_QWORD *)(a1 + 8) + 4 * a2) + 4);
  v5 = 0;
  if ( valid )
    return a1;
  return v5;
}

```

## disassembly

```asm
0x1400123c0  push    rsi
0x1400123c1  push    rdi
0x1400123c2  sub     rsp, 28h
0x1400123c6  mov     rax, [rcx+10h]
0x1400123ca  cmp     rdx, rax
0x1400123cd  jnb     short loc_1400123FF
0x1400123cf  mov     rsi, rcx
0x1400123d2  mov     rax, [rcx+8]
0x1400123d6  movsxd  rax, dword ptr [rax+rdx*4]
0x1400123da  lea     rdi, [rdx+rax]
0x1400123de  add     rdi, 4
0x1400123e2  mov     rdx, rdi
0x1400123e5  call    _RNvMNtCsdcpJtfrLhSH_7rgncore4scanINtB2_12ScanInternalQINtNtCsexo9QDNEsji_5alloc3vec3VeclINtCsdwtLm5uWta6_10gdi_region22ScanLookAsideAllocatorKj70_EEB1o_E13is_valid_scanB4__llvm_8899961222222301143
0x1400123ea  xor     ecx, ecx
0x1400123ec  test    al, al
0x1400123ee  cmovnz  rcx, rsi
0x1400123f2  mov     rax, rcx
0x1400123f5  mov     rdx, rdi
0x1400123f8  add     rsp, 28h
0x1400123fc  pop     rdi
0x1400123fd  pop     rsi
0x1400123fe  retn
0x1400123ff  lea     r8, anon_22b06d26984f22b1c5b0f9b994440758_2_llvm_8899961222222301143
0x140012406  mov     rcx, rdx
0x140012409  mov     rdx, rax
0x14001240c  call    _RNvNtCs9MWeMO1rkJG_4core9panicking18panic_bounds_check
```
