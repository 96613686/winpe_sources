# _RNvMs_CsdcpJtfrLhSH_7rgncoreNtB4_10RegionCore16set_to_rectangle

- ea: `0x14000b860`
- end: `0x14000bc14`
- name: `_RNvMs_CsdcpJtfrLhSH_7rgncoreNtB4_10RegionCore16set_to_rectangle`
- size: `948`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `6`
- callee_count: `10`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x140004e40`
- `0x1400050c0`
- `0x14000acb0`
- `0x14000ca10`
- `0x14000cc10`
- `0x14000e640`

## callees

- `0x14000b710`
- `0x14000b860`
- `0x1400120f0`
- `0x140012b60`
- `0x140017a10`
- `0x140018450`
- `0x140018470`
- `0x1400184d7`
- `0x140018630`
- `0x1400193b0`

## pseudocode

```c
unsigned __int64 __fastcall RNvMs_CsdcpJtfrLhSH_7rgncoreNtB4_10RegionCore16set_to_rectangle(
        __int64 a1,
        unsigned int *a2)
{
  unsigned int v2; // r15d
  unsigned int v3; // ebp
  int v4; // ebx
  int v5; // esi
  unsigned __int64 result; // rax
  uintptr_t v7; // rdx
  unsigned __int64 v8; // rax
  _QWORD *v9; // rdi
  int *v10; // r12
  __int64 v11; // r13
  __int64 v12; // rcx
  __int64 v13; // r8
  __int64 v14; // r9
  uintptr_t v15; // rdi
  __int64 v16; // rdx
  int v17; // eax
  int v18; // eax
  int v19; // eax
  unsigned __int64 v20; // r14
  _UNKNOWN **v21; // rax
  _BYTE v22[32]; // [rsp+0h] [rbp-98h] BYREF
  int v23; // [rsp+34h] [rbp-64h] BYREF
  __int64 v24[3]; // [rsp+38h] [rbp-60h] BYREF
  __int64 v25; // [rsp+50h] [rbp-48h]

  v2 = *a2;
  v3 = a2[2];
  if ( *a2 == v3 || (v4 = a2[1], v5 = a2[3], v4 == v5) )
  {
    result = (unsigned __int64)v22 ^ v25;
    v7 = _security_cookie;
    if ( _security_cookie == ((unsigned __int64)v22 ^ v25) )
      return RNvMs_CsdcpJtfrLhSH_7rgncoreNtB4_10RegionCore16set_to_null_scan(a1, _security_cookie);
LABEL_40:
    RNvNtCs9MWeMO1rkJG_4core9panicking18panic_bounds_check(
      result,
      v7,
      (__int64)&anon_22b06d26984f22b1c5b0f9b994440758_33_llvm_8899961222222301143);
  }
  *(_OWORD *)(a1 + 28) = *(_OWORD *)a2;
  v8 = *(_QWORD *)(a1 + 16);
  v9 = (_QWORD *)a1;
  if ( v8 != 14 )
  {
    v16 = *(_QWORD *)a1;
    if ( *(_QWORD *)a1 <= 0xDu && 14 - v8 > v16 - v8 )
    {
      if ( v8 > 0xE )
        goto LABEL_46;
      v20 = 14;
      if ( (unsigned __int64)(2 * v16) >= 0xF )
        v20 = 2 * v16;
      RNvMs4_NtCsexo9QDNEsji_5alloc7raw_vecINtB5_11RawVecInnerINtCsdwtLm5uWta6_10gdi_region22ScanLookAsideAllocatorKj70_EE11finish_growCsdcpJtfrLhSH_7rgncore_llvm_18110786352924170244(
        v24,
        v16,
        *(const void **)(a1 + 8),
        v20,
        4u,
        4u);
      if ( LODWORD(v24[0]) == 1 )
      {
LABEL_46:
        LODWORD(v24[0]) = 14;
        v21 = &off_14001B500;
        goto LABEL_38;
      }
      a1 = (__int64)v9;
      v9[1] = v24[1];
      *v9 = v20;
    }
    *(_QWORD *)(a1 + 16) = 0;
    *(_DWORD *)(a1 + 24) = 0;
    v17 = RNvMs5_NtCsdcpJtfrLhSH_7rgncore4scanINtB5_11ScanBuilderINtCsdwtLm5uWta6_10gdi_region22ScanLookAsideAllocatorKj70_EE11append_scan(
            a1,
            0x80000000,
            v4,
            (const void *)4,
            0);
    if ( v17 )
    {
      LODWORD(v24[0]) = v17;
      v21 = &off_14001B4E8;
    }
    else
    {
      v24[0] = __PAIR64__(v3, v2);
      v18 = RNvMs5_NtCsdcpJtfrLhSH_7rgncore4scanINtB5_11ScanBuilderINtCsdwtLm5uWta6_10gdi_region22ScanLookAsideAllocatorKj70_EE11append_scan(
              (__int64)v9,
              v4,
              v5,
              v24,
              2u);
      if ( v18 )
      {
        v23 = v18;
        RNvNtCs9MWeMO1rkJG_4core6result13unwrap_failed(
          (unsigned int)"called `Result::unwrap()` on an `Err` valuergncore\\src\\scan.rs",
          43,
          (unsigned int)&v23,
          (unsigned int)&qword_14001B498,
          (__int64)&off_14001B4D0);
      }
      v19 = RNvMs5_NtCsdcpJtfrLhSH_7rgncore4scanINtB5_11ScanBuilderINtCsdwtLm5uWta6_10gdi_region22ScanLookAsideAllocatorKj70_EE11append_scan(
              (__int64)v9,
              v5,
              0x7FFFFFFF,
              (const void *)4,
              0);
      if ( !v19 )
      {
        if ( !v9[2] )
          RNvMs_CsdcpJtfrLhSH_7rgncoreNtB4_10RegionCore16set_to_null_scan(v9, v7);
        goto LABEL_25;
      }
      LODWORD(v24[0]) = v19;
      v21 = &off_14001B4B8;
    }
LABEL_38:
    RNvNtCs9MWeMO1rkJG_4core6result13unwrap_failed(
      (unsigned int)"called `Result::unwrap()` on an `Err` valuergncore\\src\\scan.rs",
      43,
      (unsigned int)v24,
      (unsigned int)&qword_14001B498,
      (__int64)v21);
  }
  if ( !RNvMNtCsdcpJtfrLhSH_7rgncore4scanINtB2_12ScanInternalQINtNtCsexo9QDNEsji_5alloc3vec3VeclINtCsdwtLm5uWta6_10gdi_region22ScanLookAsideAllocatorKj70_EEB1o_E13is_valid_scanB4__llvm_8899961222222301143(
          a1,
          0) )
    RNvNtCs9MWeMO1rkJG_4core9panicking5panic(
      (__int64)&anon_22b06d26984f22b1c5b0f9b994440758_17_llvm_8899961222222301143,
      52,
      (__int64)&anon_22b06d26984f22b1c5b0f9b994440758_18_llvm_8899961222222301143);
  v10 = (int *)v9[1];
  v10[2] = v4;
  v11 = *v10;
  if ( !RNvMNtCsdcpJtfrLhSH_7rgncore4scanINtB2_12ScanInternalQINtNtCsexo9QDNEsji_5alloc3vec3VeclINtCsdwtLm5uWta6_10gdi_region22ScanLookAsideAllocatorKj70_EEB1o_E13is_valid_scanB4__llvm_8899961222222301143(
          (__int64)v9,
          v11 + 4) )
    RNvNtCs9MWeMO1rkJG_4core6option13unwrap_failed((__int64)&off_14001B468);
  result = v11 + 5;
  v7 = v9[2];
  if ( v11 + 5 >= v7 )
    goto LABEL_40;
  v12 = (__int64)v9;
  v13 = v9[1];
  *(_DWORD *)(v13 + 4 * v11 + 20) = v4;
  if ( v11 + 6 >= v7 )
    RNvNtCs9MWeMO1rkJG_4core9panicking18panic_bounds_check(
      v11 + 6,
      v7,
      (__int64)&anon_22b06d26984f22b1c5b0f9b994440758_23_llvm_8899961222222301143);
  *(_DWORD *)(v13 + 4 * v11 + 24) = v5;
  if ( v11 + 4 >= v7 )
    RNvNtCs9MWeMO1rkJG_4core9panicking18panic_bounds_check(
      v11 + 4,
      v7,
      (__int64)&anon_22b06d26984f22b1c5b0f9b994440758_2_llvm_8899961222222301143);
  v14 = *(int *)(v13 + 4 * v11 + 16);
  if ( !*(_DWORD *)(v13 + 4 * v11 + 16) )
    goto LABEL_32;
  if ( v11 + 7 >= v7 )
    RNvNtCs9MWeMO1rkJG_4core9panicking18panic_bounds_check(
      v11 + 7,
      v7,
      (__int64)&anon_22b06d26984f22b1c5b0f9b994440758_21_llvm_8899961222222301143);
  *(_DWORD *)(v13 + 4 * v11 + 28) = v2;
  if ( (_DWORD)v14 == 1 )
LABEL_32:
    RNvNtCs9MWeMO1rkJG_4core9panicking5panic(
      (__int64)&anon_22b06d26984f22b1c5b0f9b994440758_12_llvm_8899961222222301143,
      43,
      (__int64)&anon_22b06d26984f22b1c5b0f9b994440758_20_llvm_8899961222222301143);
  if ( v11 + 8 >= v7 )
    RNvNtCs9MWeMO1rkJG_4core9panicking18panic_bounds_check(
      v11 + 8,
      v7,
      (__int64)&anon_22b06d26984f22b1c5b0f9b994440758_21_llvm_8899961222222301143);
  *(_DWORD *)(v13 + 4 * v11 + 32) = v3;
  v15 = v14 + v11 + 8;
  if ( !RNvMNtCsdcpJtfrLhSH_7rgncore4scanINtB2_12ScanInternalQINtNtCsexo9QDNEsji_5alloc3vec3VeclINtCsdwtLm5uWta6_10gdi_region22ScanLookAsideAllocatorKj70_EEB1o_E13is_valid_scanB4__llvm_8899961222222301143(
          v12,
          v15) )
    RNvNtCs9MWeMO1rkJG_4core6option13unwrap_failed((__int64)&off_14001B480);
  if ( v15 + 1 >= 0xE )
    RNvNtCs9MWeMO1rkJG_4core9panicking18panic_bounds_check(
      v15 + 1,
      14,
      (__int64)&anon_22b06d26984f22b1c5b0f9b994440758_33_llvm_8899961222222301143);
  v10[v15 + 1] = v5;
LABEL_25:
  result = (unsigned __int64)v22 ^ v25;
  if ( _security_cookie != ((unsigned __int64)v22 ^ v25) )
    goto LABEL_40;
  return result;
}

```

## disassembly

```asm
0x14000b860  push    r15
0x14000b862  push    r14
0x14000b864  push    r13
0x14000b866  push    r12
0x14000b868  push    rsi
0x14000b869  push    rdi
0x14000b86a  push    rbp
0x14000b86b  push    rbx
0x14000b86c  sub     rsp, 58h
0x14000b870  mov     rax, cs:__security_cookie
0x14000b877  xor     rax, rsp
0x14000b87a  mov     [rsp+98h+var_48], rax
0x14000b87f  mov     r15d, [rdx]
0x14000b882  mov     ebp, [rdx+8]
0x14000b885  cmp     r15d, ebp
0x14000b888  jz      short loc_14000B894
0x14000b88a  mov     ebx, [rdx+4]
0x14000b88d  mov     esi, [rdx+0Ch]
0x14000b890  cmp     ebx, esi
0x14000b892  jnz     short loc_14000B8C1
0x14000b894  mov     rax, [rsp+98h+var_48]
0x14000b899  xor     rax, rsp
0x14000b89c  mov     rdx, cs:__security_cookie
0x14000b8a3  cmp     rdx, rax
0x14000b8a6  jnz     loc_14000BB97
0x14000b8ac  add     rsp, 58h
0x14000b8b0  pop     rbx
0x14000b8b1  pop     rbp
0x14000b8b2  pop     rdi
0x14000b8b3  pop     rsi
0x14000b8b4  pop     r12
0x14000b8b6  pop     r13
0x14000b8b8  pop     r14
0x14000b8ba  pop     r15
0x14000b8bc  jmp     _RNvMs_CsdcpJtfrLhSH_7rgncoreNtB4_10RegionCore16set_to_null_scan
0x14000b8c1  movups  xmm0, xmmword ptr [rdx]
0x14000b8c4  movups  xmmword ptr [rcx+1Ch], xmm0
0x14000b8c8  mov     rax, [rcx+10h]
0x14000b8cc  cmp     rax, 0Eh
0x14000b8d0  mov     rdi, rcx
0x14000b8d3  jnz     loc_14000B9AB
0x14000b8d9  xor     edx, edx
0x14000b8db  call    _RNvMNtCsdcpJtfrLhSH_7rgncore4scanINtB2_12ScanInternalQINtNtCsexo9QDNEsji_5alloc3vec3VeclINtCsdwtLm5uWta6_10gdi_region22ScanLookAsideAllocatorKj70_EEB1o_E13is_valid_scanB4__llvm_8899961222222301143
0x14000b8e0  test    al, al
0x14000b8e2  jz      loc_14000BB00
0x14000b8e8  mov     rcx, rdi
0x14000b8eb  mov     r12, [rdi+8]
0x14000b8ef  mov     [r12+8], ebx
0x14000b8f4  movsxd  r13, dword ptr [r12]
0x14000b8f8  lea     r14, [r13+4]
0x14000b8fc  mov     rdx, r14
0x14000b8ff  call    _RNvMNtCsdcpJtfrLhSH_7rgncore4scanINtB2_12ScanInternalQINtNtCsexo9QDNEsji_5alloc3vec3VeclINtCsdwtLm5uWta6_10gdi_region22ScanLookAsideAllocatorKj70_EEB1o_E13is_valid_scanB4__llvm_8899961222222301143
0x14000b904  test    al, al
0x14000b906  jz      loc_14000BB25
0x14000b90c  lea     rax, [r13+5]
0x14000b910  mov     rdx, [rdi+10h]
0x14000b914  cmp     rax, rdx
0x14000b917  jnb     loc_14000BBA4
0x14000b91d  mov     rcx, rdi
0x14000b920  mov     r8, [rdi+8]
0x14000b924  mov     [r8+r13*4+14h], ebx
0x14000b929  lea     rax, [r13+6]
0x14000b92d  cmp     rax, rdx
0x14000b930  jnb     loc_14000BBB3
0x14000b936  mov     [r8+r13*4+18h], esi
0x14000b93b  cmp     r14, rdx
0x14000b93e  jnb     loc_14000BBC2
0x14000b944  movsxd  r9, dword ptr [r8+r13*4+10h]
0x14000b949  test    r9, r9
0x14000b94c  jz      loc_14000BAE8
0x14000b952  lea     rax, [r13+7]
0x14000b956  cmp     rax, rdx
0x14000b959  jnb     loc_14000BBD1
0x14000b95f  mov     [r8+r13*4+1Ch], r15d
0x14000b964  cmp     r9d, 1
0x14000b968  jz      loc_14000BAE8
0x14000b96e  lea     rdi, [r13+8]
0x14000b972  cmp     rdi, rdx
0x14000b975  jnb     loc_14000BBE0
0x14000b97b  mov     [r8+r13*4+20h], ebp
0x14000b980  add     rdi, r9
0x14000b983  mov     rdx, rdi
0x14000b986  call    _RNvMNtCsdcpJtfrLhSH_7rgncore4scanINtB2_12ScanInternalQINtNtCsexo9QDNEsji_5alloc3vec3VeclINtCsdwtLm5uWta6_10gdi_region22ScanLookAsideAllocatorKj70_EEB1o_E13is_valid_scanB4__llvm_8899961222222301143
0x14000b98b  test    al, al
0x14000b98d  jz      loc_14000BB8B
0x14000b993  lea     rcx, [rdi+1]
0x14000b997  cmp     rcx, 0Eh
0x14000b99b  jnb     loc_14000BBEF
0x14000b9a1  mov     [r12+rdi*4+4], esi
0x14000b9a6  jmp     loc_14000BA61
0x14000b9ab  mov     rdx, [rcx]
0x14000b9ae  cmp     rdx, 0Dh
0x14000b9b2  ja      short loc_14000B9CC
0x14000b9b4  mov     r8d, 0Eh
0x14000b9ba  sub     r8, rax
0x14000b9bd  mov     r9, rdx
0x14000b9c0  sub     r9, rax
0x14000b9c3  cmp     r8, r9
0x14000b9c6  ja      loc_14000BA8A
0x14000b9cc  mov     qword ptr [rcx+10h], 0
0x14000b9d4  mov     dword ptr [rcx+18h], 0
0x14000b9db  mov     [rsp+98h+var_78], 0
0x14000b9e4  mov     r9d, 4
0x14000b9ea  mov     edx, 80000000h
0x14000b9ef  mov     r8d, ebx
0x14000b9f2  call    _RNvMs5_NtCsdcpJtfrLhSH_7rgncore4scanINtB5_11ScanBuilderINtCsdwtLm5uWta6_10gdi_region22ScanLookAsideAllocatorKj70_EE11append_scan
0x14000b9f7  test    eax, eax
0x14000b9f9  jnz     loc_14000BB18
0x14000b9ff  mov     [rsp+98h+var_60], r15d
0x14000ba04  mov     [rsp+98h+var_5C], ebp
0x14000ba08  mov     [rsp+98h+var_78], 2
0x14000ba11  lea     r9, [rsp+98h+var_60]
0x14000ba16  mov     rcx, rdi
0x14000ba19  mov     edx, ebx
0x14000ba1b  mov     r8d, esi
0x14000ba1e  call    _RNvMs5_NtCsdcpJtfrLhSH_7rgncore4scanINtB5_11ScanBuilderINtCsdwtLm5uWta6_10gdi_region22ScanLookAsideAllocatorKj70_EE11append_scan
0x14000ba23  test    eax, eax
0x14000ba25  jnz     loc_14000BB31
0x14000ba2b  mov     [rsp+98h+var_78], 0
0x14000ba34  mov     r9d, 4
0x14000ba3a  mov     rcx, rdi
0x14000ba3d  mov     edx, esi
0x14000ba3f  mov     r8d, 7FFFFFFFh
0x14000ba45  call    _RNvMs5_NtCsdcpJtfrLhSH_7rgncore4scanINtB5_11ScanBuilderINtCsdwtLm5uWta6_10gdi_region22ScanLookAsideAllocatorKj70_EE11append_scan
0x14000ba4a  test    eax, eax
0x14000ba4c  jnz     loc_14000BB5E
0x14000ba52  cmp     qword ptr [rdi+10h], 0
0x14000ba57  jnz     short loc_14000BA61
0x14000ba59  mov     rcx, rdi
0x14000ba5c  call    _RNvMs_CsdcpJtfrLhSH_7rgncoreNtB4_10RegionCore16set_to_null_scan
0x14000ba61  mov     rax, [rsp+98h+var_48]
0x14000ba66  xor     rax, rsp
0x14000ba69  mov     rcx, cs:__security_cookie
0x14000ba70  cmp     rcx, rax
0x14000ba73  jnz     loc_14000BB97
0x14000ba79  add     rsp, 58h
0x14000ba7d  pop     rbx
0x14000ba7e  pop     rbp
0x14000ba7f  pop     rdi
0x14000ba80  pop     rsi
0x14000ba81  pop     r12
0x14000ba83  pop     r13
0x14000ba85  pop     r14
0x14000ba87  pop     r15
0x14000ba89  retn
0x14000ba8a  cmp     rax, 0Eh
0x14000ba8e  ja      loc_14000BC00
0x14000ba94  lea     rax, [rdx+rdx]
0x14000ba98  cmp     rax, 0Fh
0x14000ba9c  mov     r14d, 0Eh
0x14000baa2  cmovnb  r14, rax
0x14000baa6  mov     r8, [rcx+8]
0x14000baaa  mov     [rsp+98h+var_70], 4
0x14000bab3  mov     [rsp+98h+var_78], 4
0x14000babc  lea     rcx, [rsp+98h+var_60]
0x14000bac1  mov     r9, r14
0x14000bac4  call    _RNvMs4_NtCsexo9QDNEsji_5alloc7raw_vecINtB5_11RawVecInnerINtCsdwtLm5uWta6_10gdi_region22ScanLookAsideAllocatorKj70_EE11finish_growCsdcpJtfrLhSH_7rgncore_llvm_18110786352924170244
0x14000bac9  cmp     [rsp+98h+var_60], 1
0x14000bace  jz      loc_14000BC00
0x14000bad4  mov     rax, [rsp+98h+var_58]
0x14000bad9  mov     rcx, rdi
0x14000badc  mov     [rdi+8], rax
0x14000bae0  mov     [rdi], r14
0x14000bae3  jmp     loc_14000B9CC
0x14000bae8  lea     rcx, anon_22b06d26984f22b1c5b0f9b994440758_12_llvm_8899961222222301143
0x14000baef  lea     r8, anon_22b06d26984f22b1c5b0f9b994440758_20_llvm_8899961222222301143
0x14000baf6  mov     edx, 2Bh ; '+'
0x14000bafb  call    _RNvNtCs9MWeMO1rkJG_4core9panicking5panic
0x14000bb00  lea     rcx, anon_22b06d26984f22b1c5b0f9b994440758_17_llvm_8899961222222301143
0x14000bb07  lea     r8, anon_22b06d26984f22b1c5b0f9b994440758_18_llvm_8899961222222301143
0x14000bb0e  mov     edx, 34h ; '4'
0x14000bb13  call    _RNvNtCs9MWeMO1rkJG_4core9panicking5panic
0x14000bb18  mov     [rsp+98h+var_60], eax
0x14000bb1c  lea     rax, off_14001B4E8; "rgncore\\src\\lib.rs"
0x14000bb23  jmp     short loc_14000BB69
0x14000bb25  lea     rcx, off_14001B468; "rgncore\\src\\lib.rs"
0x14000bb2c  call    _RNvNtCs9MWeMO1rkJG_4core6option13unwrap_failed
0x14000bb31  mov     [rsp+98h+var_64], eax
0x14000bb35  lea     rax, off_14001B4D0; "rgncore\\src\\lib.rs"
0x14000bb3c  mov     [rsp+98h+var_78], rax
0x14000bb41  lea     rcx, aCalledResultUn; "called `Result::unwrap()` on an `Err` v"...
0x14000bb48  lea     r9, qword_14001B498
0x14000bb4f  lea     r8, [rsp+98h+var_64]
0x14000bb54  mov     edx, 2Bh ; '+'
0x14000bb59  call    _RNvNtCs9MWeMO1rkJG_4core6result13unwrap_failed
0x14000bb5e  mov     [rsp+98h+var_60], eax
0x14000bb62  lea     rax, off_14001B4B8; "rgncore\\src\\lib.rs"
0x14000bb69  mov     [rsp+98h+var_78], rax
0x14000bb6e  lea     rcx, aCalledResultUn; "called `Result::unwrap()` on an `Err` v"...
0x14000bb75  lea     r9, qword_14001B498
0x14000bb7c  lea     r8, [rsp+98h+var_60]
0x14000bb81  mov     edx, 2Bh ; '+'
0x14000bb86  call    _RNvNtCs9MWeMO1rkJG_4core6result13unwrap_failed
0x14000bb8b  lea     rcx, off_14001B480; "rgncore\\src\\lib.rs"
0x14000bb92  call    _RNvNtCs9MWeMO1rkJG_4core6option13unwrap_failed
0x14000bb97  mov     rcx, [rsp+98h+var_48]
0x14000bb9c  xor     rcx, rsp; StackCookie
0x14000bb9f  call    __security_check_cookie
0x14000bba4  lea     r8, anon_22b06d26984f22b1c5b0f9b994440758_33_llvm_8899961222222301143
0x14000bbab  mov     rcx, rax
0x14000bbae  call    _RNvNtCs9MWeMO1rkJG_4core9panicking18panic_bounds_check
0x14000bbb3  lea     r8, anon_22b06d26984f22b1c5b0f9b994440758_23_llvm_8899961222222301143
0x14000bbba  mov     rcx, rax
0x14000bbbd  call    _RNvNtCs9MWeMO1rkJG_4core9panicking18panic_bounds_check
0x14000bbc2  lea     r8, anon_22b06d26984f22b1c5b0f9b994440758_2_llvm_8899961222222301143
0x14000bbc9  mov     rcx, r14
0x14000bbcc  call    _RNvNtCs9MWeMO1rkJG_4core9panicking18panic_bounds_check
0x14000bbd1  lea     r8, anon_22b06d26984f22b1c5b0f9b994440758_21_llvm_8899961222222301143
0x14000bbd8  mov     rcx, rax
0x14000bbdb  call    _RNvNtCs9MWeMO1rkJG_4core9panicking18panic_bounds_check
0x14000bbe0  lea     r8, anon_22b06d26984f22b1c5b0f9b994440758_21_llvm_8899961222222301143
0x14000bbe7  mov     rcx, rdi
0x14000bbea  call    _RNvNtCs9MWeMO1rkJG_4core9panicking18panic_bounds_check
0x14000bbef  lea     r8, anon_22b06d26984f22b1c5b0f9b994440758_33_llvm_8899961222222301143
0x14000bbf6  mov     edx, 0Eh
0x14000bbfb  call    _RNvNtCs9MWeMO1rkJG_4core9panicking18panic_bounds_check
0x14000bc00  mov     [rsp+98h+var_60], 0Eh
0x14000bc08  lea     rax, off_14001B500; "rgncore\\src\\lib.rs"
0x14000bc0f  jmp     loc_14000BB69
```
