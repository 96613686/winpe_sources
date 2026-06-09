# _RNvMNtCsdcpJtfrLhSH_7rgncore4scanINtB2_12ScanInternalRINtNtCsexo9QDNEsji_5alloc3vec3VeclINtCsdwtLm5uWta6_10gdi_region22ScanLookAsideAllocatorKj70_EEB1o_E13is_valid_scanCs7vXzV21FY6F_8gdi_rust.llvm.7541658972310832757

- ea: `0x14000f5b0`
- end: `0x14000f6a5`
- name: `_RNvMNtCsdcpJtfrLhSH_7rgncore4scanINtB2_12ScanInternalRINtNtCsexo9QDNEsji_5alloc3vec3VeclINtCsdwtLm5uWta6_10gdi_region22ScanLookAsideAllocatorKj70_EEB1o_E13is_valid_scanCs7vXzV21FY6F_8gdi_rust.llvm.7541658972310832757`
- size: `245`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `3`
- callee_count: `5`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x140003860`
- `0x140004af0`
- `0x14000f800`

## callees

- `0x14000f5b0`
- `0x140017a10`
- `0x140018400`
- `0x140018470`
- `0x1400184d7`

## pseudocode

```c
char __fastcall RNvMNtCsdcpJtfrLhSH_7rgncore4scanINtB2_12ScanInternalRINtNtCsexo9QDNEsji_5alloc3vec3VeclINtCsdwtLm5uWta6_10gdi_region22ScanLookAsideAllocatorKj70_EEB1o_E13is_valid_scanCs7vXzV21FY6F_8gdi_rust_llvm_7541658972310832757(
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
        &anon_01189c164b0c425bf67614ee34d1a89c_3_llvm_7541658972310832757);
    v8 = *(int *)(v5 + 4 * v7);
    if ( v8 < 0 )
      RNvNtCs9MWeMO1rkJG_4core6result13unwrap_failed(
        (unsigned int)&anon_01189c164b0c425bf67614ee34d1a89c_5_llvm_7541658972310832757,
        43,
        (unsigned int)&v11,
        (unsigned int)anon_01189c164b0c425bf67614ee34d1a89c_4_llvm_7541658972310832757,
        (__int64)&anon_01189c164b0c425bf67614ee34d1a89c_6_llvm_7541658972310832757);
    v13 = v8;
    LOBYTE(v2) = 1;
    if ( (_DWORD)v8 != (_DWORD)v6 )
    {
      v10[5] = &anon_01189c164b0c425bf67614ee34d1a89c_7_llvm_7541658972310832757;
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
      &anon_01189c164b0c425bf67614ee34d1a89c_2_llvm_7541658972310832757);
  return v2;
}

```

## disassembly

```asm
0x14000f5b0  sub     rsp, 58h
0x14000f5b4  mov     rax, rdx
0x14000f5b7  mov     rdx, cs:__security_cookie
0x14000f5be  xor     rdx, rsp
0x14000f5c1  mov     [rsp+58h+var_8], rdx
0x14000f5c6  lea     r9, [rax+4]
0x14000f5ca  mov     rdx, [rcx+10h]
0x14000f5ce  cmp     r9, rdx
0x14000f5d1  ja      short loc_14000F5F6
0x14000f5d3  cmp     rax, rdx
0x14000f5d6  jnb     loc_14000F689
0x14000f5dc  mov     r10, [rcx+8]
0x14000f5e0  movsxd  r8, dword ptr [r10+rax*4]
0x14000f5e4  test    r8, r8
0x14000f5e7  js      short loc_14000F5F6
0x14000f5e9  mov     [rsp+58h+var_18], r8
0x14000f5ee  add     r9, r8
0x14000f5f1  cmp     r9, rdx
0x14000f5f4  jbe     short loc_14000F611
0x14000f5f6  xor     eax, eax
0x14000f5f8  mov     rcx, [rsp+58h+var_8]
0x14000f5fd  xor     rcx, rsp
0x14000f600  mov     rdx, cs:__security_cookie
0x14000f607  cmp     rdx, rcx
0x14000f60a  jnz     short loc_14000F67C
0x14000f60c  add     rsp, 58h
0x14000f610  retn
0x14000f611  lea     rcx, [rax+r8]
0x14000f615  add     rcx, 3
0x14000f619  cmp     rcx, rdx
0x14000f61c  jnb     short loc_14000F698
0x14000f61e  movsxd  rcx, dword ptr [r10+rcx*4]
0x14000f622  test    rcx, rcx
0x14000f625  js      short loc_14000F653
0x14000f627  mov     [rsp+58h+var_10], rcx
0x14000f62c  mov     al, 1
0x14000f62e  cmp     ecx, r8d
0x14000f631  jz      short loc_14000F5F8
0x14000f633  lea     rax, anon_01189c164b0c425bf67614ee34d1a89c_7_llvm_7541658972310832757
0x14000f63a  mov     [rsp+58h+var_30], rax
0x14000f63f  lea     rdx, [rsp+58h+var_10]
0x14000f644  lea     r8, [rsp+58h+var_18]
0x14000f649  xor     ecx, ecx
0x14000f64b  xor     r9d, r9d
0x14000f64e  call    _RINvNtCs9MWeMO1rkJG_4core9panicking13assert_failedjjEB4_
0x14000f653  lea     rax, anon_01189c164b0c425bf67614ee34d1a89c_6_llvm_7541658972310832757
0x14000f65a  mov     [rsp+58h+var_38], rax
0x14000f65f  lea     rcx, anon_01189c164b0c425bf67614ee34d1a89c_5_llvm_7541658972310832757
0x14000f666  lea     r9, anon_01189c164b0c425bf67614ee34d1a89c_4_llvm_7541658972310832757
0x14000f66d  lea     r8, [rsp+58h+var_19]
0x14000f672  mov     edx, 2Bh ; '+'
0x14000f677  call    _RNvNtCs9MWeMO1rkJG_4core6result13unwrap_failed
0x14000f67c  mov     rcx, [rsp+58h+var_8]
0x14000f681  xor     rcx, rsp; StackCookie
0x14000f684  call    __security_check_cookie
0x14000f689  lea     r8, anon_01189c164b0c425bf67614ee34d1a89c_2_llvm_7541658972310832757
0x14000f690  mov     rcx, rax
0x14000f693  call    _RNvNtCs9MWeMO1rkJG_4core9panicking18panic_bounds_check
0x14000f698  lea     r8, anon_01189c164b0c425bf67614ee34d1a89c_3_llvm_7541658972310832757
0x14000f69f  call    _RNvNtCs9MWeMO1rkJG_4core9panicking18panic_bounds_check
```
