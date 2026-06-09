# _RNvMs_CsdcpJtfrLhSH_7rgncoreNtB4_10RegionCore20tighten_bounding_box

- ea: `0x14000be40`
- end: `0x14000c060`
- name: `_RNvMs_CsdcpJtfrLhSH_7rgncoreNtB4_10RegionCore20tighten_bounding_box`
- size: `544`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `3`
- callee_count: `8`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x140005140`
- `0x140005340`
- `0x1400101f0`

## callees

- `0x14000be40`
- `0x1400120f0`
- `0x140017a10`
- `0x140018450`
- `0x140018470`
- `0x1400184d7`
- `0x140018630`
- `0x140018690`

## pseudocode

```c
unsigned __int64 __fastcall RNvMs_CsdcpJtfrLhSH_7rgncoreNtB4_10RegionCore20tighten_bounding_box(__int64 a1)
{
  unsigned __int64 v1; // rdi
  __int64 v3; // r14
  __int64 v4; // rax
  int v5; // ebp
  uintptr_t v6; // rbx
  int v7; // r15d
  int v8; // r13d
  signed int v9; // r12d
  uintptr_t v10; // rbx
  __int64 v11; // rax
  unsigned __int64 v12; // rcx
  unsigned __int64 v13; // rdx
  int *v14; // rdx
  int v15; // eax
  unsigned __int64 result; // rax
  _BYTE v17[32]; // [rsp+0h] [rbp-78h] BYREF
  char v18; // [rsp+2Fh] [rbp-49h] BYREF
  __int64 v19; // [rsp+30h] [rbp-48h]

  if ( *(_DWORD *)(a1 + 24) == 1 )
  {
    *(_OWORD *)(a1 + 28) = 0;
  }
  else
  {
    if ( !RNvMNtCsdcpJtfrLhSH_7rgncore4scanINtB2_12ScanInternalQINtNtCsexo9QDNEsji_5alloc3vec3VeclINtCsdwtLm5uWta6_10gdi_region22ScanLookAsideAllocatorKj70_EEB1o_E13is_valid_scanB4__llvm_8899961222222301143(
            a1,
            0) )
      goto LABEL_29;
    v1 = *(_QWORD *)(a1 + 16);
    if ( v1 <= 2 )
      goto LABEL_33;
    v3 = *(_QWORD *)(a1 + 8);
    v4 = *(int *)(v3 + 4 * v1 - 4);
    if ( v4 < 0 )
      RNvNtCs9MWeMO1rkJG_4core6result13unwrap_failed(
        (__int64)anon_22b06d26984f22b1c5b0f9b994440758_6_llvm_8899961222222301143,
        43,
        (__int64)&v18,
        (__int64)anon_22b06d26984f22b1c5b0f9b994440758_5_llvm_8899961222222301143,
        (__int64)&anon_22b06d26984f22b1c5b0f9b994440758_10_llvm_8899961222222301143);
    if ( v1 < v4 + 4
      || (v5 = *(_DWORD *)(v3 + 8),
          v6 = v1 - v4 - 4,
          !RNvMNtCsdcpJtfrLhSH_7rgncore4scanINtB2_12ScanInternalQINtNtCsexo9QDNEsji_5alloc3vec3VeclINtCsdwtLm5uWta6_10gdi_region22ScanLookAsideAllocatorKj70_EEB1o_E13is_valid_scanB4__llvm_8899961222222301143(
             a1,
             v6)) )
    {
      RNvNtCs9MWeMO1rkJG_4core6option13unwrap_failed((__int64)&anon_22b06d26984f22b1c5b0f9b994440758_15_llvm_8899961222222301143);
    }
    if ( v6 + 1 >= v1 )
      RNvNtCs9MWeMO1rkJG_4core9panicking18panic_bounds_check(
        v6 + 1,
        v1,
        (__int64)&anon_22b06d26984f22b1c5b0f9b994440758_11_llvm_8899961222222301143);
    v7 = *(_DWORD *)(v3 + 4 * v6 + 4);
    if ( !RNvMNtCsdcpJtfrLhSH_7rgncore4scanINtB2_12ScanInternalQINtNtCsexo9QDNEsji_5alloc3vec3VeclINtCsdwtLm5uWta6_10gdi_region22ScanLookAsideAllocatorKj70_EEB1o_E13is_valid_scanB4__llvm_8899961222222301143(
            a1,
            0) )
LABEL_29:
      RNvNtCs9MWeMO1rkJG_4core9panicking5panic(
        (__int64)&anon_22b06d26984f22b1c5b0f9b994440758_17_llvm_8899961222222301143,
        52,
        (__int64)&anon_22b06d26984f22b1c5b0f9b994440758_18_llvm_8899961222222301143);
    v8 = 0x7FFFFFFF;
    v9 = 0x80000000;
    v10 = 0;
    do
    {
      if ( v10 >= v1 )
        RNvNtCs9MWeMO1rkJG_4core9panicking18panic_bounds_check(
          v10,
          v1,
          (__int64)&anon_22b06d26984f22b1c5b0f9b994440758_2_llvm_8899961222222301143);
      v11 = *(int *)(v3 + 4 * v10);
      if ( *(_DWORD *)(v3 + 4 * v10) )
      {
        v12 = v10 + 3;
        if ( v10 + 3 >= v1 )
          RNvNtCs9MWeMO1rkJG_4core9panicking18panic_bounds_check(
            v12,
            v1,
            (__int64)&anon_22b06d26984f22b1c5b0f9b994440758_14_llvm_8899961222222301143);
        v13 = v11 + v12;
        if ( __CFADD__(v11, v12) || v13 > v1 )
          RNvNtNtCs9MWeMO1rkJG_4core5slice5index16slice_index_fail(
            v12,
            v13,
            v1,
            (__int64)&anon_22b06d26984f22b1c5b0f9b994440758_16_llvm_8899961222222301143);
        v14 = (int *)(v3 + 4 * v12);
        if ( v8 >= *v14 )
          v8 = *v14;
        if ( v9 <= v14[v11 - 1] )
          v9 = v14[v11 - 1];
      }
      v10 += v11 + 4;
    }
    while ( RNvMNtCsdcpJtfrLhSH_7rgncore4scanINtB2_12ScanInternalQINtNtCsexo9QDNEsji_5alloc3vec3VeclINtCsdwtLm5uWta6_10gdi_region22ScanLookAsideAllocatorKj70_EEB1o_E13is_valid_scanB4__llvm_8899961222222301143(
              a1,
              v10) );
    v15 = 0;
    if ( v8 < v9 )
      v15 = v8;
    else
      v9 = 0;
    *(_DWORD *)(a1 + 28) = v15;
    *(_DWORD *)(a1 + 32) = v5;
    *(_DWORD *)(a1 + 36) = v9;
    *(_DWORD *)(a1 + 40) = v7;
  }
  result = (unsigned __int64)v17 ^ v19;
  if ( _security_cookie != ((unsigned __int64)v17 ^ v19) )
LABEL_33:
    RNvNtCs9MWeMO1rkJG_4core9panicking18panic_bounds_check(
      2,
      v1,
      (__int64)&anon_22b06d26984f22b1c5b0f9b994440758_19_llvm_8899961222222301143);
  return result;
}

```

## disassembly

```asm
0x14000be40  push    r15
0x14000be42  push    r14
0x14000be44  push    r13
0x14000be46  push    r12
0x14000be48  push    rsi
0x14000be49  push    rdi
0x14000be4a  push    rbp
0x14000be4b  push    rbx
0x14000be4c  sub     rsp, 38h
0x14000be50  mov     rsi, rcx
0x14000be53  mov     rax, cs:__security_cookie
0x14000be5a  xor     rax, rsp
0x14000be5d  mov     [rsp+78h+var_48], rax
0x14000be62  cmp     dword ptr [rcx+18h], 1
0x14000be66  jnz     short loc_14000BE74
0x14000be68  xorps   xmm0, xmm0
0x14000be6b  movups  xmmword ptr [rsi+1Ch], xmm0
0x14000be6f  jmp     loc_14000BF89
0x14000be74  mov     rcx, rsi
0x14000be77  xor     edx, edx
0x14000be79  call    _RNvMNtCsdcpJtfrLhSH_7rgncore4scanINtB2_12ScanInternalQINtNtCsexo9QDNEsji_5alloc3vec3VeclINtCsdwtLm5uWta6_10gdi_region22ScanLookAsideAllocatorKj70_EEB1o_E13is_valid_scanB4__llvm_8899961222222301143
0x14000be7e  test    al, al
0x14000be80  jz      loc_14000BFC1
0x14000be86  mov     rdi, [rsi+10h]
0x14000be8a  cmp     rdi, 2
0x14000be8e  jbe     loc_14000C030
0x14000be94  mov     r14, [rsi+8]
0x14000be98  movsxd  rax, dword ptr [r14+rdi*4-4]
0x14000be9d  test    rax, rax
0x14000bea0  js      loc_14000BFD9
0x14000bea6  lea     rcx, [rax+4]
0x14000beaa  cmp     rdi, rcx
0x14000bead  jb      loc_14000C044
0x14000beb3  mov     ebp, [r14+8]
0x14000beb7  mov     rbx, rdi
0x14000beba  sub     rbx, rax
0x14000bebd  add     rbx, 0FFFFFFFFFFFFFFFCh
0x14000bec1  mov     rcx, rsi
0x14000bec4  mov     rdx, rbx
0x14000bec7  call    _RNvMNtCsdcpJtfrLhSH_7rgncore4scanINtB2_12ScanInternalQINtNtCsexo9QDNEsji_5alloc3vec3VeclINtCsdwtLm5uWta6_10gdi_region22ScanLookAsideAllocatorKj70_EEB1o_E13is_valid_scanB4__llvm_8899961222222301143
0x14000becc  test    al, al
0x14000bece  jz      loc_14000C044
0x14000bed4  lea     rcx, [rbx+1]
0x14000bed8  cmp     rcx, rdi
0x14000bedb  jnb     loc_14000C050
0x14000bee1  mov     r15d, [r14+rbx*4+4]
0x14000bee6  mov     rcx, rsi
0x14000bee9  xor     edx, edx
0x14000beeb  call    _RNvMNtCsdcpJtfrLhSH_7rgncore4scanINtB2_12ScanInternalQINtNtCsexo9QDNEsji_5alloc3vec3VeclINtCsdwtLm5uWta6_10gdi_region22ScanLookAsideAllocatorKj70_EEB1o_E13is_valid_scanB4__llvm_8899961222222301143
0x14000bef0  test    al, al
0x14000bef2  jz      loc_14000BFC1
0x14000bef8  mov     r13d, 7FFFFFFFh
0x14000befe  mov     r12d, 80000000h
0x14000bf04  xor     ebx, ebx
0x14000bf06  jmp     short loc_14000BF26
0x14000bf10  add     rbx, rax
0x14000bf13  add     rbx, 4
0x14000bf17  mov     rcx, rsi
0x14000bf1a  mov     rdx, rbx
0x14000bf1d  call    _RNvMNtCsdcpJtfrLhSH_7rgncore4scanINtB2_12ScanInternalQINtNtCsexo9QDNEsji_5alloc3vec3VeclINtCsdwtLm5uWta6_10gdi_region22ScanLookAsideAllocatorKj70_EEB1o_E13is_valid_scanB4__llvm_8899961222222301143
0x14000bf22  test    al, al
0x14000bf24  jz      short loc_14000BF6E
0x14000bf26  cmp     rbx, rdi
0x14000bf29  jnb     loc_14000C002
0x14000bf2f  movsxd  rax, dword ptr [r14+rbx*4]
0x14000bf33  test    rax, rax
0x14000bf36  jz      short loc_14000BF10
0x14000bf38  lea     rcx, [rbx+3]
0x14000bf3c  cmp     rcx, rdi
0x14000bf3f  jnb     loc_14000C014
0x14000bf45  mov     rdx, rcx
0x14000bf48  add     rdx, rax
0x14000bf4b  jb      short loc_14000BFB2
0x14000bf4d  cmp     rdx, rdi
0x14000bf50  ja      short loc_14000BFB2
0x14000bf52  lea     rdx, [r14+rcx*4]
0x14000bf56  mov     ecx, [r14+rcx*4]
0x14000bf5a  cmp     r13d, ecx
0x14000bf5d  cmovge  r13d, ecx
0x14000bf61  mov     ecx, [rdx+rax*4-4]
0x14000bf65  cmp     r12d, ecx
0x14000bf68  cmovle  r12d, ecx
0x14000bf6c  jmp     short loc_14000BF10
0x14000bf6e  xor     eax, eax
0x14000bf70  cmp     r13d, r12d
0x14000bf73  cmovge  r12d, eax
0x14000bf77  cmovl   eax, r13d
0x14000bf7b  mov     [rsi+1Ch], eax
0x14000bf7e  mov     [rsi+20h], ebp
0x14000bf81  mov     [rsi+24h], r12d
0x14000bf85  mov     [rsi+28h], r15d
0x14000bf89  mov     rax, [rsp+78h+var_48]
0x14000bf8e  xor     rax, rsp
0x14000bf91  mov     rcx, cs:__security_cookie
0x14000bf98  cmp     rcx, rax
0x14000bf9b  jnz     loc_14000C023
0x14000bfa1  add     rsp, 38h
0x14000bfa5  pop     rbx
0x14000bfa6  pop     rbp
0x14000bfa7  pop     rdi
0x14000bfa8  pop     rsi
0x14000bfa9  pop     r12
0x14000bfab  pop     r13
0x14000bfad  pop     r14
0x14000bfaf  pop     r15
0x14000bfb1  retn
0x14000bfb2  lea     r9, anon_22b06d26984f22b1c5b0f9b994440758_16_llvm_8899961222222301143
0x14000bfb9  mov     r8, rdi
0x14000bfbc  call    _RNvNtNtCs9MWeMO1rkJG_4core5slice5index16slice_index_fail
0x14000bfc1  lea     rcx, anon_22b06d26984f22b1c5b0f9b994440758_17_llvm_8899961222222301143
0x14000bfc8  lea     r8, anon_22b06d26984f22b1c5b0f9b994440758_18_llvm_8899961222222301143
0x14000bfcf  mov     edx, 34h ; '4'
0x14000bfd4  call    _RNvNtCs9MWeMO1rkJG_4core9panicking5panic
0x14000bfd9  lea     rax, anon_22b06d26984f22b1c5b0f9b994440758_10_llvm_8899961222222301143
0x14000bfe0  mov     [rsp+78h+var_58], rax
0x14000bfe5  lea     rcx, anon_22b06d26984f22b1c5b0f9b994440758_6_llvm_8899961222222301143
0x14000bfec  lea     r9, anon_22b06d26984f22b1c5b0f9b994440758_5_llvm_8899961222222301143
0x14000bff3  lea     r8, [rsp+78h+var_49]
0x14000bff8  mov     edx, 2Bh ; '+'
0x14000bffd  call    _RNvNtCs9MWeMO1rkJG_4core6result13unwrap_failed
0x14000c002  lea     r8, anon_22b06d26984f22b1c5b0f9b994440758_2_llvm_8899961222222301143
0x14000c009  mov     rcx, rbx
0x14000c00c  mov     rdx, rdi
0x14000c00f  call    _RNvNtCs9MWeMO1rkJG_4core9panicking18panic_bounds_check
0x14000c014  lea     r8, anon_22b06d26984f22b1c5b0f9b994440758_14_llvm_8899961222222301143
0x14000c01b  mov     rdx, rdi
0x14000c01e  call    _RNvNtCs9MWeMO1rkJG_4core9panicking18panic_bounds_check
0x14000c023  mov     rcx, [rsp+78h+var_48]
0x14000c028  xor     rcx, rsp; StackCookie
0x14000c02b  call    __security_check_cookie
0x14000c030  lea     r8, anon_22b06d26984f22b1c5b0f9b994440758_19_llvm_8899961222222301143
0x14000c037  mov     ecx, 2
0x14000c03c  mov     rdx, rdi
0x14000c03f  call    _RNvNtCs9MWeMO1rkJG_4core9panicking18panic_bounds_check
0x14000c044  lea     rcx, anon_22b06d26984f22b1c5b0f9b994440758_15_llvm_8899961222222301143
0x14000c04b  call    _RNvNtCs9MWeMO1rkJG_4core6option13unwrap_failed
0x14000c050  lea     r8, anon_22b06d26984f22b1c5b0f9b994440758_11_llvm_8899961222222301143
0x14000c057  mov     rdx, rdi
0x14000c05a  call    _RNvNtCs9MWeMO1rkJG_4core9panicking18panic_bounds_check
```
