# _RNvMNtCsdcpJtfrLhSH_7rgncore4scanINtB2_12ScanInternalQINtNtCsexo9QDNEsji_5alloc3vec3VeclINtCsdwtLm5uWta6_10gdi_region22ScanLookAsideAllocatorKj70_EEB1o_E13is_valid_scanB4_.llvm.8899961222222301143

- ea: `0x1400120f0`
- end: `0x1400121e5`
- name: `_RNvMNtCsdcpJtfrLhSH_7rgncore4scanINtB2_12ScanInternalQINtNtCsexo9QDNEsji_5alloc3vec3VeclINtCsdwtLm5uWta6_10gdi_region22ScanLookAsideAllocatorKj70_EEB1o_E13is_valid_scanB4_.llvm.8899961222222301143`
- size: `245`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `15`
- callee_count: `5`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x14000a950`
- `0x14000a990`
- `0x14000ab50`
- `0x14000abf0`
- `0x14000b0e0`
- `0x14000b240`
- `0x14000b860`
- `0x14000be40`
- `0x14000c440`
- `0x14000e720`
- `0x14000e9d0`
- `0x140012260`
- `0x140012380`
- `0x1400123c0`
- `0x140012770`

## callees

- `0x1400120f0`
- `0x140017a10`
- `0x140018400`
- `0x140018470`
- `0x1400184d7`

## pseudocode

```c
char __fastcall RNvMNtCsdcpJtfrLhSH_7rgncore4scanINtB2_12ScanInternalQINtNtCsexo9QDNEsji_5alloc3vec3VeclINtCsdwtLm5uWta6_10gdi_region22ScanLookAsideAllocatorKj70_EEB1o_E13is_valid_scanB4__llvm_8899961222222301143(
        __int64 a1,
        uintptr_t a2)
{
  uintptr_t v2; // rax
  uintptr_t v3; // r9
  uintptr_t v4; // rdx
  __int64 v5; // r10
  __int64 v6; // r8
  unsigned __int64 v7; // rcx
  __int64 v8; // rcx
  _QWORD v10[7]; // [rsp+0h] [rbp-58h] BYREF
  char v11; // [rsp+3Fh] [rbp-19h] BYREF
  __int64 v12; // [rsp+40h] [rbp-18h]
  __int64 v13; // [rsp+48h] [rbp-10h]
  __int64 v14; // [rsp+50h] [rbp-8h]

  v2 = a2;
  v3 = a2 + 4;
  v4 = *(_QWORD *)(a1 + 16);
  if ( v3 > v4 )
    goto LABEL_5;
  if ( v2 >= v4 )
    goto LABEL_13;
  v5 = *(_QWORD *)(a1 + 8);
  v6 = *(int *)(v5 + 4 * v2);
  if ( v6 >= 0 && (v12 = *(int *)(v5 + 4 * v2), v6 + v3 <= v4) )
  {
    v7 = v2 + v6 + 3;
    if ( v7 >= v4 )
      RNvNtCs9MWeMO1rkJG_4core9panicking18panic_bounds_check(
        v7,
        v4,
        &anon_22b06d26984f22b1c5b0f9b994440758_4_llvm_8899961222222301143);
    v8 = *(int *)(v5 + 4 * v7);
    if ( v8 < 0 )
      RNvNtCs9MWeMO1rkJG_4core6result13unwrap_failed(
        (unsigned int)anon_22b06d26984f22b1c5b0f9b994440758_6_llvm_8899961222222301143,
        43,
        (unsigned int)&v11,
        (unsigned int)anon_22b06d26984f22b1c5b0f9b994440758_5_llvm_8899961222222301143,
        (__int64)&anon_22b06d26984f22b1c5b0f9b994440758_7_llvm_8899961222222301143);
    v13 = v8;
    LOBYTE(v2) = 1;
    if ( (_DWORD)v8 != (_DWORD)v6 )
    {
      v10[5] = &anon_22b06d26984f22b1c5b0f9b994440758_8_llvm_8899961222222301143;
      RINvNtCs9MWeMO1rkJG_4core9panicking13assert_failedjjEB4_(0);
    }
  }
  else
  {
LABEL_5:
    v2 = 0;
  }
  v4 = _security_cookie;
  if ( _security_cookie != ((unsigned __int64)v10 ^ v14) )
LABEL_13:
    RNvNtCs9MWeMO1rkJG_4core9panicking18panic_bounds_check(
      v2,
      v4,
      &anon_22b06d26984f22b1c5b0f9b994440758_3_llvm_8899961222222301143);
  return v2;
}

```

## disassembly

```asm
0x1400120f0  sub     rsp, 58h
0x1400120f4  mov     rax, rdx
0x1400120f7  mov     rdx, cs:__security_cookie
0x1400120fe  xor     rdx, rsp
0x140012101  mov     [rsp+58h+var_8], rdx
0x140012106  lea     r9, [rax+4]
0x14001210a  mov     rdx, [rcx+10h]
0x14001210e  cmp     r9, rdx
0x140012111  ja      short loc_140012136
0x140012113  cmp     rax, rdx
0x140012116  jnb     loc_1400121C9
0x14001211c  mov     r10, [rcx+8]
0x140012120  movsxd  r8, dword ptr [r10+rax*4]
0x140012124  test    r8, r8
0x140012127  js      short loc_140012136
0x140012129  mov     [rsp+58h+var_18], r8
0x14001212e  add     r9, r8
0x140012131  cmp     r9, rdx
0x140012134  jbe     short loc_140012151
0x140012136  xor     eax, eax
0x140012138  mov     rcx, [rsp+58h+var_8]
0x14001213d  xor     rcx, rsp
0x140012140  mov     rdx, cs:__security_cookie
0x140012147  cmp     rdx, rcx
0x14001214a  jnz     short loc_1400121BC
0x14001214c  add     rsp, 58h
0x140012150  retn
0x140012151  lea     rcx, [rax+r8]
0x140012155  add     rcx, 3
0x140012159  cmp     rcx, rdx
0x14001215c  jnb     short loc_1400121D8
0x14001215e  movsxd  rcx, dword ptr [r10+rcx*4]
0x140012162  test    rcx, rcx
0x140012165  js      short loc_140012193
0x140012167  mov     [rsp+58h+var_10], rcx
0x14001216c  mov     al, 1
0x14001216e  cmp     ecx, r8d
0x140012171  jz      short loc_140012138
0x140012173  lea     rax, anon_22b06d26984f22b1c5b0f9b994440758_8_llvm_8899961222222301143
0x14001217a  mov     [rsp+58h+var_30], rax
0x14001217f  lea     rdx, [rsp+58h+var_10]
0x140012184  lea     r8, [rsp+58h+var_18]
0x140012189  xor     ecx, ecx
0x14001218b  xor     r9d, r9d
0x14001218e  call    _RINvNtCs9MWeMO1rkJG_4core9panicking13assert_failedjjEB4_
0x140012193  lea     rax, anon_22b06d26984f22b1c5b0f9b994440758_7_llvm_8899961222222301143
0x14001219a  mov     [rsp+58h+var_38], rax
0x14001219f  lea     rcx, anon_22b06d26984f22b1c5b0f9b994440758_6_llvm_8899961222222301143
0x1400121a6  lea     r9, anon_22b06d26984f22b1c5b0f9b994440758_5_llvm_8899961222222301143
0x1400121ad  lea     r8, [rsp+58h+var_19]
0x1400121b2  mov     edx, 2Bh ; '+'
0x1400121b7  call    _RNvNtCs9MWeMO1rkJG_4core6result13unwrap_failed
0x1400121bc  mov     rcx, [rsp+58h+var_8]
0x1400121c1  xor     rcx, rsp; StackCookie
0x1400121c4  call    __security_check_cookie
0x1400121c9  lea     r8, anon_22b06d26984f22b1c5b0f9b994440758_3_llvm_8899961222222301143
0x1400121d0  mov     rcx, rax
0x1400121d3  call    _RNvNtCs9MWeMO1rkJG_4core9panicking18panic_bounds_check
0x1400121d8  lea     r8, anon_22b06d26984f22b1c5b0f9b994440758_4_llvm_8899961222222301143
0x1400121df  call    _RNvNtCs9MWeMO1rkJG_4core9panicking18panic_bounds_check
```
