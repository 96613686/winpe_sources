# _RNvMNtCsdcpJtfrLhSH_7rgncore4scanINtB2_12ScanInternalQINtNtCsexo9QDNEsji_5alloc3vec3VeclINtCsdwtLm5uWta6_10gdi_region22ScanLookAsideAllocatorKj70_EEB1o_E7last_ofB4_

- ea: `0x140012260`
- end: `0x140012312`
- name: `_RNvMNtCsdcpJtfrLhSH_7rgncore4scanINtB2_12ScanInternalQINtNtCsexo9QDNEsji_5alloc3vec3VeclINtCsdwtLm5uWta6_10gdi_region22ScanLookAsideAllocatorKj70_EEB1o_E7last_ofB4_`
- size: `178`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `2`
- callee_count: `5`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x14000cc10`
- `0x14000e720`

## callees

- `0x1400120f0`
- `0x140012260`
- `0x140017a10`
- `0x140018450`
- `0x140018470`

## pseudocode

```c
__int64 __fastcall RNvMNtCsdcpJtfrLhSH_7rgncore4scanINtB2_12ScanInternalQINtNtCsexo9QDNEsji_5alloc3vec3VeclINtCsdwtLm5uWta6_10gdi_region22ScanLookAsideAllocatorKj70_EEB1o_E7last_ofB4_(
        __int64 a1)
{
  unsigned __int64 v1; // rdi
  __int64 v3; // rax
  __int64 v5; // [rsp+0h] [rbp-48h] BYREF
  char v6; // [rsp+2Fh] [rbp-19h] BYREF
  __int64 v7; // [rsp+30h] [rbp-18h]

  v1 = *(_QWORD *)(a1 + 16);
  if ( !v1 )
    goto LABEL_8;
  v3 = *(int *)(*(_QWORD *)(a1 + 8) + 4 * v1 - 4);
  if ( v3 < 0 )
    RNvNtCs9MWeMO1rkJG_4core6result13unwrap_failed(
      (unsigned int)anon_22b06d26984f22b1c5b0f9b994440758_6_llvm_8899961222222301143,
      43,
      (unsigned int)&v6,
      (unsigned int)anon_22b06d26984f22b1c5b0f9b994440758_5_llvm_8899961222222301143,
      (__int64)&anon_22b06d26984f22b1c5b0f9b994440758_10_llvm_8899961222222301143);
  if ( v1 < v3 + 4
    || !RNvMNtCsdcpJtfrLhSH_7rgncore4scanINtB2_12ScanInternalQINtNtCsexo9QDNEsji_5alloc3vec3VeclINtCsdwtLm5uWta6_10gdi_region22ScanLookAsideAllocatorKj70_EEB1o_E13is_valid_scanB4__llvm_8899961222222301143(
          a1,
          v1 - v3 - 4) )
  {
LABEL_8:
    RNvNtCs9MWeMO1rkJG_4core6option13unwrap_failed(&anon_22b06d26984f22b1c5b0f9b994440758_15_llvm_8899961222222301143);
  }
  if ( _security_cookie != ((unsigned __int64)&v5 ^ v7) )
    JUMPOUT(0x140012311LL);
  return a1;
}

```

## disassembly

```asm
0x140012260  push    rsi
0x140012261  push    rdi
0x140012262  sub     rsp, 38h
0x140012266  mov     rax, cs:__security_cookie
0x14001226d  xor     rax, rsp
0x140012270  mov     [rsp+48h+var_18], rax
0x140012275  mov     rdi, [rcx+10h]
0x140012279  test    rdi, rdi
0x14001227c  jz      short loc_1400122F8
0x14001227e  mov     rsi, rcx
0x140012281  mov     rax, [rcx+8]
0x140012285  movsxd  rax, dword ptr [rax+rdi*4-4]
0x14001228a  test    rax, rax
0x14001228d  js      short loc_1400122CF
0x14001228f  lea     rcx, [rax+4]
0x140012293  cmp     rdi, rcx
0x140012296  jb      short loc_1400122F8
0x140012298  sub     rdi, rax
0x14001229b  add     rdi, 0FFFFFFFFFFFFFFFCh
0x14001229f  mov     rcx, rsi
0x1400122a2  mov     rdx, rdi
0x1400122a5  call    _RNvMNtCsdcpJtfrLhSH_7rgncore4scanINtB2_12ScanInternalQINtNtCsexo9QDNEsji_5alloc3vec3VeclINtCsdwtLm5uWta6_10gdi_region22ScanLookAsideAllocatorKj70_EEB1o_E13is_valid_scanB4__llvm_8899961222222301143
0x1400122aa  test    al, al
0x1400122ac  jz      short loc_1400122F8
0x1400122ae  mov     rax, [rsp+48h+var_18]
0x1400122b3  xor     rax, rsp
0x1400122b6  mov     rcx, cs:__security_cookie
0x1400122bd  cmp     rcx, rax
0x1400122c0  jnz     short loc_140012304
0x1400122c2  mov     rax, rsi
0x1400122c5  mov     rdx, rdi
0x1400122c8  add     rsp, 38h
0x1400122cc  pop     rdi
0x1400122cd  pop     rsi
0x1400122ce  retn
0x1400122cf  lea     rax, anon_22b06d26984f22b1c5b0f9b994440758_10_llvm_8899961222222301143
0x1400122d6  mov     [rsp+48h+var_28], rax
0x1400122db  lea     rcx, anon_22b06d26984f22b1c5b0f9b994440758_6_llvm_8899961222222301143
0x1400122e2  lea     r9, anon_22b06d26984f22b1c5b0f9b994440758_5_llvm_8899961222222301143
0x1400122e9  lea     r8, [rsp+48h+var_19]
0x1400122ee  mov     edx, 2Bh ; '+'
0x1400122f3  call    _RNvNtCs9MWeMO1rkJG_4core6result13unwrap_failed
0x1400122f8  lea     rcx, anon_22b06d26984f22b1c5b0f9b994440758_15_llvm_8899961222222301143
0x1400122ff  call    _RNvNtCs9MWeMO1rkJG_4core6option13unwrap_failed
0x140012304  mov     rcx, [rsp+48h+var_18]
0x140012309  xor     rcx, rsp; StackCookie
0x14001230c  call    __security_check_cookie
```
