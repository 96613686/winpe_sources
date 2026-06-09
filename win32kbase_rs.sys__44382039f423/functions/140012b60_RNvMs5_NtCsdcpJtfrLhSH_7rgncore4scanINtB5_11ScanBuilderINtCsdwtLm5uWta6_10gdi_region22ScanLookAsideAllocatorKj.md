# _RNvMs5_NtCsdcpJtfrLhSH_7rgncore4scanINtB5_11ScanBuilderINtCsdwtLm5uWta6_10gdi_region22ScanLookAsideAllocatorKj70_EE11append_scan

- ea: `0x140012b60`
- end: `0x140012efb`
- name: `_RNvMs5_NtCsdcpJtfrLhSH_7rgncore4scanINtB5_11ScanBuilderINtCsdwtLm5uWta6_10gdi_region22ScanLookAsideAllocatorKj70_EE11append_scan`
- size: `923`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `7`
- callee_count: `5`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x140005340`
- `0x14000b240`
- `0x14000b860`
- `0x14000c640`
- `0x14000cc10`
- `0x1400101f0`
- `0x140011120`

## callees

- `0x14000fdc0`
- `0x140012b60`
- `0x140017a10`
- `0x140017b00`
- `0x1400193b0`

## pseudocode

```c
__int64 __fastcall RNvMs5_NtCsdcpJtfrLhSH_7rgncore4scanINtB5_11ScanBuilderINtCsdwtLm5uWta6_10gdi_region22ScanLookAsideAllocatorKj70_EE11append_scan(
        __int64 a1,
        int a2,
        int a3,
        const void *a4,
        unsigned __int64 a5)
{
  __int64 v6; // rax
  __int64 v7; // rbx
  unsigned __int64 v8; // rdi
  _DWORD *v9; // rax
  __int64 v10; // r12
  __int64 v11; // rbx
  __int64 v12; // rdi
  _DWORD *v13; // rax
  __int64 v14; // r14
  _DWORD *v15; // rax
  __int64 v16; // r12
  __int64 result; // rax
  int v18; // ebp
  int v19; // r14d
  const void *v20; // r12
  int v21; // ebp
  int v22; // r14d
  const void *v23; // r13
  unsigned __int64 v24; // rax
  int v25; // ebp
  const void *v26; // r12
  const void *v27; // r12
  unsigned __int64 v28; // rbx
  unsigned __int64 v29; // rbx
  int v30; // r13d
  const void *v31; // rbp
  unsigned __int64 v32; // rcx
  unsigned __int64 v33; // r14
  __int64 v34; // [rsp+0h] [rbp-98h] BYREF
  int v35; // [rsp+34h] [rbp-64h]
  __int64 v36; // [rsp+38h] [rbp-60h] BYREF
  _DWORD *v37; // [rsp+40h] [rbp-58h]
  __int64 v38; // [rsp+50h] [rbp-48h]

  v6 = *(_QWORD *)a1;
  v7 = *(_QWORD *)(a1 + 16);
  if ( a5 + 4 > *(_QWORD *)a1 - v7 )
  {
    v18 = a2;
    v19 = a3;
    v20 = a4;
    v8 = v7 + a5 + 4;
    if ( v8 <= 2 * v6 )
      v8 = 2 * v6;
    RNvMs4_NtCsexo9QDNEsji_5alloc7raw_vecINtB5_11RawVecInnerINtCsdwtLm5uWta6_10gdi_region22ScanLookAsideAllocatorKj70_EE11finish_growCsdcpJtfrLhSH_7rgncore_llvm_18110786352924170244(
      &v36,
      v6,
      *(const void **)(a1 + 8),
      v8,
      4u,
      4u);
    if ( (_DWORD)v36 == 1 )
      goto LABEL_24;
    *(_QWORD *)(a1 + 8) = v37;
    *(_QWORD *)a1 = v8;
    a4 = v20;
    a3 = v19;
    a2 = v18;
    if ( v8 != v7 )
    {
LABEL_3:
      v9 = *(_DWORD **)(a1 + 8);
      v10 = v7 + 1;
      v9[v7] = a5;
      *(_QWORD *)(a1 + 16) = v7 + 1;
      if ( v8 != v7 + 1 )
      {
LABEL_4:
        v11 = v10 + 1;
        goto LABEL_5;
      }
LABEL_39:
      v35 = a2;
      v30 = a3;
      v31 = a4;
      v11 = v8 + 1;
      v32 = 2 * v8;
      if ( v8 + 1 > 2 * v8 )
        v32 = v8 + 1;
      v33 = 4;
      if ( v32 >= 5 )
        v33 = v32;
      RNvMs4_NtCsexo9QDNEsji_5alloc7raw_vecINtB5_11RawVecInnerINtCsdwtLm5uWta6_10gdi_region22ScanLookAsideAllocatorKj70_EE11finish_growCsdcpJtfrLhSH_7rgncore_llvm_18110786352924170244(
        &v36,
        v8,
        v9,
        v33,
        4u,
        4u);
      if ( (_DWORD)v36 == 1 )
        goto LABEL_44;
      v9 = v37;
      *(_QWORD *)(a1 + 8) = v37;
      *(_QWORD *)a1 = v33;
      a4 = v31;
      a3 = v30;
      a2 = v35;
LABEL_5:
      v9[v10] = a2;
      *(_QWORD *)(a1 + 16) = v11;
      v12 = *(_QWORD *)a1;
      if ( *(_QWORD *)a1 == v11 )
      {
        v25 = a3;
        v26 = a4;
        v14 = v11 + 1;
        v12 = 2 * v11;
        if ( v11 + 1 > (unsigned __int64)(2 * v11) )
          v12 = v11 + 1;
        RNvMs4_NtCsexo9QDNEsji_5alloc7raw_vecINtB5_11RawVecInnerINtCsdwtLm5uWta6_10gdi_region22ScanLookAsideAllocatorKj70_EE11finish_growCsdcpJtfrLhSH_7rgncore_llvm_18110786352924170244(
          &v36,
          v11,
          *(const void **)(a1 + 8),
          v12,
          4u,
          4u);
        if ( (_DWORD)v36 == 1 )
          goto LABEL_44;
        v13 = v37;
        *(_QWORD *)(a1 + 8) = v37;
        *(_QWORD *)a1 = v12;
        a4 = v26;
        a3 = v25;
      }
      else
      {
        v13 = *(_DWORD **)(a1 + 8);
        v14 = v11 + 1;
      }
      v13[v11] = a3;
      *(_QWORD *)(a1 + 16) = v14;
      if ( a5 <= v12 - v14 )
      {
        if ( !a5 )
        {
LABEL_10:
          *(_QWORD *)(a1 + 16) = v14;
          if ( v12 != v14 )
          {
            v15 = *(_DWORD **)(a1 + 8);
            v16 = v14 + 1;
LABEL_12:
            v15[v14] = a5;
            *(_QWORD *)(a1 + 16) = v16;
            ++*(_DWORD *)(a1 + 24);
            result = 0;
            goto LABEL_13;
          }
          v16 = v12 + 1;
          v29 = 2 * v12;
          if ( v12 + 1 > (unsigned __int64)(2 * v12) )
            v29 = v12 + 1;
          RNvMs4_NtCsexo9QDNEsji_5alloc7raw_vecINtB5_11RawVecInnerINtCsdwtLm5uWta6_10gdi_region22ScanLookAsideAllocatorKj70_EE11finish_growCsdcpJtfrLhSH_7rgncore_llvm_18110786352924170244(
            &v36,
            v12,
            *(const void **)(a1 + 8),
            v29,
            4u,
            4u);
          if ( (_DWORD)v36 != 1 )
          {
            v15 = v37;
            *(_QWORD *)(a1 + 8) = v37;
            *(_QWORD *)a1 = v29;
            goto LABEL_12;
          }
          goto LABEL_44;
        }
LABEL_9:
        memmove(&v13[v14], a4, 4 * a5);
        v14 += ((4 * a5 - 4) >> 2) + 1;
        v12 = *(_QWORD *)a1;
        goto LABEL_10;
      }
      v27 = a4;
      v28 = 2 * v12;
      if ( v14 + a5 > 2 * v12 )
        v28 = v14 + a5;
      RNvMs4_NtCsexo9QDNEsji_5alloc7raw_vecINtB5_11RawVecInnerINtCsdwtLm5uWta6_10gdi_region22ScanLookAsideAllocatorKj70_EE11finish_growCsdcpJtfrLhSH_7rgncore_llvm_18110786352924170244(
        &v36,
        v12,
        v13,
        v28,
        4u,
        4u);
      if ( (_DWORD)v36 != 1 )
      {
        v13 = v37;
        *(_QWORD *)(a1 + 8) = v37;
        *(_QWORD *)a1 = v28;
        a4 = v27;
        goto LABEL_9;
      }
LABEL_44:
      result = 14;
      goto LABEL_13;
    }
  }
  else
  {
    v8 = *(_QWORD *)a1;
    if ( v6 != v7 )
      goto LABEL_3;
  }
  v21 = a2;
  v22 = a3;
  v23 = a4;
  v10 = v7 + 1;
  v24 = 2 * v7;
  if ( v7 + 1 > (unsigned __int64)(2 * v7) )
    v24 = v7 + 1;
  v8 = 4;
  if ( v24 >= 5 )
    v8 = v24;
  RNvMs4_NtCsexo9QDNEsji_5alloc7raw_vecINtB5_11RawVecInnerINtCsdwtLm5uWta6_10gdi_region22ScanLookAsideAllocatorKj70_EE11finish_growCsdcpJtfrLhSH_7rgncore_llvm_18110786352924170244(
    &v36,
    v7,
    *(const void **)(a1 + 8),
    v8,
    4u,
    4u);
  if ( (_DWORD)v36 != 1 )
  {
    v9 = v37;
    *(_QWORD *)(a1 + 8) = v37;
    *(_QWORD *)a1 = v8;
    a4 = v23;
    a3 = v22;
    a2 = v21;
    v9[v7] = a5;
    *(_QWORD *)(a1 + 16) = v10;
    if ( v8 != v10 )
      goto LABEL_4;
    goto LABEL_39;
  }
LABEL_24:
  result = 14;
  if ( !v7 )
  {
    RNvNtCsdwtLm5uWta6_10gdi_region3ffi27RustOnZeroSizedScanCallback();
    result = 14;
  }
LABEL_13:
  if ( _security_cookie != ((unsigned __int64)&v34 ^ v38) )
    JUMPOUT(0x140012EFALL);
  return result;
}

```

## disassembly

```asm
0x140012b60  push    r15
0x140012b62  push    r14
0x140012b64  push    r13
0x140012b66  push    r12
0x140012b68  push    rsi
0x140012b69  push    rdi
0x140012b6a  push    rbp
0x140012b6b  push    rbx
0x140012b6c  sub     rsp, 58h
0x140012b70  mov     rsi, rcx
0x140012b73  mov     r15, [rsp+98h+arg_20]
0x140012b7b  mov     rax, cs:__security_cookie
0x140012b82  xor     rax, rsp
0x140012b85  mov     [rsp+98h+var_48], rax
0x140012b8a  mov     rax, [rcx]
0x140012b8d  mov     rbx, [rcx+10h]
0x140012b91  lea     rdi, [r15+4]
0x140012b95  mov     rcx, rax
0x140012b98  sub     rcx, rbx
0x140012b9b  cmp     rdi, rcx
0x140012b9e  ja      loc_140012C7A
0x140012ba4  mov     rdi, rax
0x140012ba7  cmp     rdi, rbx
0x140012baa  jz      loc_140012CDA
0x140012bb0  mov     rax, [rsi+8]
0x140012bb4  lea     r12, [rbx+1]
0x140012bb8  mov     [rax+rbx*4], r15d
0x140012bbc  mov     [rsi+10h], r12
0x140012bc0  cmp     rdi, r12
0x140012bc3  jz      loc_140012E75
0x140012bc9  lea     rbx, [r12+1]
0x140012bce  mov     [rax+r12*4], edx
0x140012bd2  mov     [rsi+10h], rbx
0x140012bd6  mov     rdi, [rsi]
0x140012bd9  cmp     rdi, rbx
0x140012bdc  jz      loc_140012D4C
0x140012be2  mov     rax, [rsi+8]
0x140012be6  lea     r14, [rbx+1]
0x140012bea  mov     [rax+rbx*4], r8d
0x140012bee  mov     [rsi+10h], r14
0x140012bf2  mov     rcx, rdi
0x140012bf5  sub     rcx, r14
0x140012bf8  cmp     r15, rcx
0x140012bfb  ja      loc_140012DA9
0x140012c01  test    r15, r15
0x140012c04  jz      short loc_140012C2F
0x140012c06  lea     r8, ds:0[r15*4]; Size
0x140012c0e  lea     rcx, [rax+r14*4]; void *
0x140012c12  mov     rdx, r9; Src
0x140012c15  call    memmove
0x140012c1a  lea     rax, ds:0FFFFFFFFFFFFFFFCh[r15*4]
0x140012c22  shr     rax, 2
0x140012c26  add     r14, rax
0x140012c29  inc     r14
0x140012c2c  mov     rdi, [rsi]
0x140012c2f  mov     [rsi+10h], r14
0x140012c33  cmp     rdi, r14
0x140012c36  jz      loc_140012DFF
0x140012c3c  mov     rax, [rsi+8]
0x140012c40  lea     r12, [r14+1]
0x140012c44  mov     [rax+r14*4], r15d
0x140012c48  mov     [rsi+10h], r12
0x140012c4c  inc     dword ptr [rsi+18h]
0x140012c4f  xor     eax, eax
0x140012c51  mov     rcx, [rsp+98h+var_48]
0x140012c56  xor     rcx, rsp
0x140012c59  mov     rdx, cs:__security_cookie
0x140012c60  cmp     rdx, rcx
0x140012c63  jnz     loc_140012EED
0x140012c69  add     rsp, 58h
0x140012c6d  pop     rbx
0x140012c6e  pop     rbp
0x140012c6f  pop     rdi
0x140012c70  pop     rsi
0x140012c71  pop     r12
0x140012c73  pop     r13
0x140012c75  pop     r14
0x140012c77  pop     r15
0x140012c79  retn
0x140012c7a  mov     ebp, edx
0x140012c7c  mov     r14d, r8d
0x140012c7f  mov     r12, r9
0x140012c82  add     rdi, rbx
0x140012c85  lea     rcx, [rax+rax]
0x140012c89  cmp     rdi, rcx
0x140012c8c  cmovbe  rdi, rcx
0x140012c90  mov     r8, [rsi+8]
0x140012c94  mov     [rsp+98h+var_70], 4
0x140012c9d  mov     [rsp+98h+var_78], 4
0x140012ca6  lea     rcx, [rsp+98h+var_60]
0x140012cab  mov     rdx, rax
0x140012cae  mov     r9, rdi
0x140012cb1  call    _RNvMs4_NtCsexo9QDNEsji_5alloc7raw_vecINtB5_11RawVecInnerINtCsdwtLm5uWta6_10gdi_region22ScanLookAsideAllocatorKj70_EE11finish_growCsdcpJtfrLhSH_7rgncore_llvm_18110786352924170244
0x140012cb6  cmp     dword ptr [rsp+98h+var_60], 1
0x140012cbb  jz      short loc_140012D2F
0x140012cbd  mov     rax, [rsp+98h+var_58]
0x140012cc2  mov     [rsi+8], rax
0x140012cc6  mov     [rsi], rdi
0x140012cc9  mov     r9, r12
0x140012ccc  mov     r8d, r14d
0x140012ccf  mov     edx, ebp
0x140012cd1  cmp     rdi, rbx
0x140012cd4  jnz     loc_140012BB0
0x140012cda  mov     ebp, edx
0x140012cdc  mov     r14d, r8d
0x140012cdf  mov     r13, r9
0x140012ce2  lea     r12, [rbx+1]
0x140012ce6  lea     rax, [rbx+rbx]
0x140012cea  cmp     r12, rax
0x140012ced  cmova   rax, r12
0x140012cf1  cmp     rax, 5
0x140012cf5  mov     edi, 4
0x140012cfa  cmovnb  rdi, rax
0x140012cfe  mov     r8, [rsi+8]
0x140012d02  mov     [rsp+98h+var_70], 4
0x140012d0b  mov     [rsp+98h+var_78], 4
0x140012d14  lea     rcx, [rsp+98h+var_60]
0x140012d19  mov     rdx, rbx
0x140012d1c  mov     r9, rdi
0x140012d1f  call    _RNvMs4_NtCsexo9QDNEsji_5alloc7raw_vecINtB5_11RawVecInnerINtCsdwtLm5uWta6_10gdi_region22ScanLookAsideAllocatorKj70_EE11finish_growCsdcpJtfrLhSH_7rgncore_llvm_18110786352924170244
0x140012d24  cmp     dword ptr [rsp+98h+var_60], 1
0x140012d29  jnz     loc_140012E50
0x140012d2f  mov     eax, 0Eh
0x140012d34  test    rbx, rbx
0x140012d37  jnz     loc_140012C51
0x140012d3d  call    _RNvNtCsdwtLm5uWta6_10gdi_region3ffi27RustOnZeroSizedScanCallback
0x140012d42  mov     eax, 0Eh
0x140012d47  jmp     loc_140012C51
0x140012d4c  mov     ebp, r8d
0x140012d4f  mov     r12, r9
0x140012d52  lea     r14, [rbx+1]
0x140012d56  lea     rdi, [rbx+rbx]
0x140012d5a  cmp     r14, rdi
0x140012d5d  cmova   rdi, r14
0x140012d61  mov     r8, [rsi+8]
0x140012d65  mov     [rsp+98h+var_70], 4
0x140012d6e  mov     [rsp+98h+var_78], 4
0x140012d77  lea     rcx, [rsp+98h+var_60]
0x140012d7c  mov     rdx, rbx
0x140012d7f  mov     r9, rdi
0x140012d82  call    _RNvMs4_NtCsexo9QDNEsji_5alloc7raw_vecINtB5_11RawVecInnerINtCsdwtLm5uWta6_10gdi_region22ScanLookAsideAllocatorKj70_EE11finish_growCsdcpJtfrLhSH_7rgncore_llvm_18110786352924170244
0x140012d87  cmp     dword ptr [rsp+98h+var_60], 1
0x140012d8c  jz      loc_140012EC8
0x140012d92  mov     rax, [rsp+98h+var_58]
0x140012d97  mov     [rsi+8], rax
0x140012d9b  mov     [rsi], rdi
0x140012d9e  mov     r9, r12
0x140012da1  mov     r8d, ebp
0x140012da4  jmp     loc_140012BEA
0x140012da9  mov     r12, r9
0x140012dac  lea     rcx, [r14+r15]
0x140012db0  lea     rbx, [rdi+rdi]
0x140012db4  cmp     rcx, rbx
0x140012db7  cmova   rbx, rcx
0x140012dbb  mov     [rsp+98h+var_70], 4
0x140012dc4  mov     [rsp+98h+var_78], 4
0x140012dcd  lea     rcx, [rsp+98h+var_60]
0x140012dd2  mov     rdx, rdi
0x140012dd5  mov     r8, rax
0x140012dd8  mov     r9, rbx
0x140012ddb  call    _RNvMs4_NtCsexo9QDNEsji_5alloc7raw_vecINtB5_11RawVecInnerINtCsdwtLm5uWta6_10gdi_region22ScanLookAsideAllocatorKj70_EE11finish_growCsdcpJtfrLhSH_7rgncore_llvm_18110786352924170244
0x140012de0  cmp     dword ptr [rsp+98h+var_60], 1
0x140012de5  jz      loc_140012EC8
0x140012deb  mov     rax, [rsp+98h+var_58]
0x140012df0  mov     [rsi+8], rax
0x140012df4  mov     [rsi], rbx
0x140012df7  mov     r9, r12
0x140012dfa  jmp     loc_140012C06
0x140012dff  lea     r12, [rdi+1]
0x140012e03  lea     rbx, [rdi+rdi]
0x140012e07  cmp     r12, rbx
0x140012e0a  cmova   rbx, r12
0x140012e0e  mov     r8, [rsi+8]
0x140012e12  mov     [rsp+98h+var_70], 4
0x140012e1b  mov     [rsp+98h+var_78], 4
0x140012e24  lea     rcx, [rsp+98h+var_60]
0x140012e29  mov     rdx, rdi
0x140012e2c  mov     r9, rbx
0x140012e2f  call    _RNvMs4_NtCsexo9QDNEsji_5alloc7raw_vecINtB5_11RawVecInnerINtCsdwtLm5uWta6_10gdi_region22ScanLookAsideAllocatorKj70_EE11finish_growCsdcpJtfrLhSH_7rgncore_llvm_18110786352924170244
0x140012e34  cmp     dword ptr [rsp+98h+var_60], 1
0x140012e39  jz      loc_140012EC8
0x140012e3f  mov     rax, [rsp+98h+var_58]
0x140012e44  mov     [rsi+8], rax
0x140012e48  mov     [rsi], rbx
0x140012e4b  jmp     loc_140012C44
0x140012e50  mov     rax, [rsp+98h+var_58]
0x140012e55  mov     [rsi+8], rax
0x140012e59  mov     [rsi], rdi
0x140012e5c  mov     r9, r13
0x140012e5f  mov     r8d, r14d
0x140012e62  mov     edx, ebp
0x140012e64  mov     [rax+rbx*4], r15d
0x140012e68  mov     [rsi+10h], r12
0x140012e6c  cmp     rdi, r12
0x140012e6f  jnz     loc_140012BC9
0x140012e75  mov     [rsp+98h+var_64], edx
0x140012e79  mov     r13d, r8d
0x140012e7c  mov     rbp, r9
0x140012e7f  lea     rbx, [rdi+1]
0x140012e83  lea     rcx, [rdi+rdi]
0x140012e87  cmp     rbx, rcx
0x140012e8a  cmova   rcx, rbx
0x140012e8e  cmp     rcx, 5
0x140012e92  mov     r14d, 4
0x140012e98  cmovnb  r14, rcx
0x140012e9c  mov     [rsp+98h+var_70], 4
0x140012ea5  mov     [rsp+98h+var_78], 4
0x140012eae  lea     rcx, [rsp+98h+var_60]
0x140012eb3  mov     rdx, rdi
0x140012eb6  mov     r8, rax
0x140012eb9  mov     r9, r14
0x140012ebc  call    _RNvMs4_NtCsexo9QDNEsji_5alloc7raw_vecINtB5_11RawVecInnerINtCsdwtLm5uWta6_10gdi_region22ScanLookAsideAllocatorKj70_EE11finish_growCsdcpJtfrLhSH_7rgncore_llvm_18110786352924170244
0x140012ec1  cmp     dword ptr [rsp+98h+var_60], 1
0x140012ec6  jnz     short loc_140012ED2
0x140012ec8  mov     eax, 0Eh
0x140012ecd  jmp     loc_140012C51
0x140012ed2  mov     rax, [rsp+98h+var_58]
0x140012ed7  mov     [rsi+8], rax
0x140012edb  mov     [rsi], r14
0x140012ede  mov     r9, rbp
0x140012ee1  mov     r8d, r13d
0x140012ee4  mov     edx, [rsp+98h+var_64]
0x140012ee8  jmp     loc_140012BCE
0x140012eed  mov     rcx, [rsp+98h+var_48]
0x140012ef2  xor     rcx, rsp; StackCookie
0x140012ef5  call    __security_check_cookie
```
