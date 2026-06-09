# _RINvXCs3PyRTeGQ7Na_12fallible_vecINtNtCsexo9QDNEsji_5alloc3vec3VeclINtCsdwtLm5uWta6_10gdi_region22ScanLookAsideAllocatorKj70_EEINtB3_11FallibleVeclB13_E10try_extendINtNtNtNtCs9MWeMO1rkJG_4core4iter8adapters6cloned6ClonedINtNtB2H_5chain5ChainIB3x_INtNtNtB2L_5slice4iter4IterlEB3W_EB3W_EEECsdcpJtfrLhSH_7rgncore

- ea: `0x140014ae0`
- end: `0x140014dbc`
- name: `_RINvXCs3PyRTeGQ7Na_12fallible_vecINtNtCsexo9QDNEsji_5alloc3vec3VeclINtCsdwtLm5uWta6_10gdi_region22ScanLookAsideAllocatorKj70_EEINtB3_11FallibleVeclB13_E10try_extendINtNtNtNtCs9MWeMO1rkJG_4core4iter8adapters6cloned6ClonedINtNtB2H_5chain5ChainIB3x_INtNtNtB2L_5slice4iter4IterlEB3W_EB3W_EEECsdcpJtfrLhSH_7rgncore`
- size: `732`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1400153c0`

## callees

- `0x140014ae0`
- `0x140017a10`
- `0x1400193b0`

## pseudocode

```c
unsigned __int64 __fastcall RINvXCs3PyRTeGQ7Na_12fallible_vecINtNtCsexo9QDNEsji_5alloc3vec3VeclINtCsdwtLm5uWta6_10gdi_region22ScanLookAsideAllocatorKj70_EEINtB3_11FallibleVeclB13_E10try_extendINtNtNtNtCs9MWeMO1rkJG_4core4iter8adapters6cloned6ClonedINtNtB2H_5chain5ChainIB3x_INtNtNtB2L_5slice4iter4IterlEB3W_EB3W_EEECsdcpJtfrLhSH_7rgncore(
        __int64 *a1,
        __int64 *a2)
{
  __int64 *v2; // r10
  __int64 v3; // r15
  _DWORD *v4; // rbp
  __int64 v5; // r9
  __int64 v6; // rax
  unsigned __int64 v7; // r8
  unsigned __int64 v8; // rcx
  unsigned __int64 v9; // rcx
  __int64 *v10; // r12
  __int64 v11; // rax
  __int64 v12; // r8
  bool v13; // cf
  unsigned __int64 v14; // r8
  unsigned __int64 result; // rax
  __int64 *v16; // rsi
  unsigned __int64 v17; // rcx
  unsigned __int64 v18; // r9
  unsigned __int64 v19; // rdi
  __int64 *v20; // rbx
  _DWORD *v21; // r9
  _DWORD *v22; // r11
  _DWORD *v23; // rcx
  __int64 v24; // r8
  _DWORD *v25; // rdx
  const void *v26; // r8
  _DWORD *v27; // rdi
  _DWORD *v28; // rsi
  _DWORD *v29; // r14
  int v30; // ebx
  __int64 v31; // r13
  unsigned __int64 v32; // rbp
  unsigned __int64 *v33; // r10
  __int64 v34; // [rsp+0h] [rbp-B8h] BYREF
  _DWORD *v35; // [rsp+38h] [rbp-80h]
  _DWORD *v36; // [rsp+40h] [rbp-78h]
  __int64 *v37; // [rsp+48h] [rbp-70h]
  _DWORD *v38; // [rsp+50h] [rbp-68h]
  __int64 v39; // [rsp+58h] [rbp-60h] BYREF
  const void *v40; // [rsp+60h] [rbp-58h]
  __int64 v41; // [rsp+70h] [rbp-48h]

  v2 = a1;
  v3 = *a2;
  v4 = (_DWORD *)a2[5];
  if ( *a2 == 1 )
  {
    v5 = a2[1];
    v6 = a2[3];
    if ( v4 )
    {
      if ( v5 )
      {
        v7 = (unsigned __int64)(a2[2] - v5) >> 2;
        if ( v6 )
          v7 += (unsigned __int64)(a2[4] - v6) >> 2;
      }
      else if ( v6 )
      {
        v7 = (unsigned __int64)(a2[4] - v6) >> 2;
      }
      else
      {
        v7 = 0;
      }
      v9 = (unsigned __int64)(a2[6] - (_QWORD)v4) >> 2;
      goto LABEL_19;
    }
    if ( v5 )
    {
      v9 = (unsigned __int64)(a2[2] - v5) >> 2;
      if ( !v6 )
        goto LABEL_20;
      v7 = (unsigned __int64)(a2[4] - v6) >> 2;
LABEL_19:
      v9 += v7;
LABEL_20:
      v10 = v2 + 2;
      v11 = *v2;
      v12 = v2[2];
      if ( v9 > *v2 - v12 )
      {
        v13 = __CFADD__(v9, v12);
        v14 = v9 + v12;
        if ( v13 )
        {
          result = 0;
          goto LABEL_51;
        }
        v16 = a2;
        v17 = 2 * v11;
        if ( v14 > 2 * v11 )
          v17 = v14;
        v18 = 4;
        if ( v17 >= 5 )
          v18 = v17;
        v19 = v18;
        v20 = v2;
        RNvMs4_NtCsexo9QDNEsji_5alloc7raw_vecINtB5_11RawVecInnerINtCsdwtLm5uWta6_10gdi_region22ScanLookAsideAllocatorKj70_EE11finish_growCsdcpJtfrLhSH_7rgncore_llvm_18110786352924170244(
          &v39,
          v11,
          (const void *)v2[1],
          v18,
          4u,
          4u);
        if ( (_DWORD)v39 == 1 )
        {
LABEL_28:
          result = (unsigned __int64)v40;
          goto LABEL_51;
        }
        v20[1] = (__int64)v40;
        v11 = v19;
        *v20 = v19;
        a2 = v16;
        v2 = v20;
      }
      goto LABEL_30;
    }
    if ( v6 )
    {
      v8 = a2[4] - v6;
      goto LABEL_8;
    }
  }
  else if ( v4 )
  {
    v8 = a2[6] - (_QWORD)v4;
LABEL_8:
    v9 = v8 >> 2;
    goto LABEL_20;
  }
  v10 = a1 + 2;
  v11 = *a1;
LABEL_30:
  v21 = (_DWORD *)a2[1];
  v22 = (_DWORD *)a2[2];
  v23 = (_DWORD *)a2[3];
  v24 = a2[4];
  v38 = (_DWORD *)a2[6];
  v25 = (_DWORD *)v24;
  v26 = (const void *)v2[1];
  v37 = v2;
  v36 = v22;
  v35 = v25;
  while ( 1 )
  {
    if ( v3 != 1 )
    {
      v27 = v21;
LABEL_41:
      if ( !v4 )
        break;
      goto LABEL_42;
    }
    if ( v21 && v21 != v22 )
    {
      v27 = v21 + 1;
      v3 = 1;
      v28 = v23;
      v29 = v4;
      goto LABEL_32;
    }
    if ( v23 )
    {
      v27 = 0;
      if ( v23 != v25 )
      {
        v28 = v23 + 1;
        v3 = 1;
        v27 = 0;
        v29 = v4;
        v21 = v23;
        goto LABEL_32;
      }
      goto LABEL_41;
    }
    v27 = 0;
    if ( !v4 )
      break;
LABEL_42:
    if ( v4 == v38 )
      break;
    v29 = v4 + 1;
    v3 = 0;
    v28 = v23;
    v21 = v4;
LABEL_32:
    v30 = *v21;
    v31 = *v10;
    if ( v11 == *v10 )
    {
      v32 = 2 * v11;
      if ( (unsigned __int64)(2 * v11) < 5 )
        v32 = 4;
      RNvMs4_NtCsexo9QDNEsji_5alloc7raw_vecINtB5_11RawVecInnerINtCsdwtLm5uWta6_10gdi_region22ScanLookAsideAllocatorKj70_EE11finish_growCsdcpJtfrLhSH_7rgncore_llvm_18110786352924170244(
        &v39,
        v11,
        v26,
        v32,
        4u,
        4u);
      if ( (_DWORD)v39 == 1 )
        goto LABEL_28;
      v26 = v40;
      v33 = (unsigned __int64 *)v37;
      v37[1] = (__int64)v40;
      *v33 = v32;
      v11 = v32;
      v22 = v36;
      v25 = v35;
    }
    *((_DWORD *)v26 + v31) = v30;
    *v10 = v31 + 1;
    v21 = v27;
    v23 = v28;
    v4 = v29;
  }
  result = 0x8000000000000001uLL;
LABEL_51:
  if ( _security_cookie != ((unsigned __int64)&v34 ^ v41) )
    JUMPOUT(0x140014DBBLL);
  return result;
}

```

## disassembly

```asm
0x140014ae0  push    r15
0x140014ae2  push    r14
0x140014ae4  push    r13
0x140014ae6  push    r12
0x140014ae8  push    rsi
0x140014ae9  push    rdi
0x140014aea  push    rbp
0x140014aeb  push    rbx
0x140014aec  sub     rsp, 78h
0x140014af0  mov     r10, rcx
0x140014af3  mov     rax, cs:__security_cookie
0x140014afa  xor     rax, rsp
0x140014afd  mov     [rsp+0B8h+var_48], rax
0x140014b02  mov     r15, [rdx]
0x140014b05  mov     rbp, [rdx+28h]
0x140014b09  cmp     r15, 1
0x140014b0d  jnz     short loc_140014B41
0x140014b0f  mov     r9, [rdx+8]
0x140014b13  mov     rax, [rdx+18h]
0x140014b17  test    rbp, rbp
0x140014b1a  jz      short loc_140014B53
0x140014b1c  test    r9, r9
0x140014b1f  jz      short loc_140014B75
0x140014b21  mov     r8, [rdx+10h]
0x140014b25  sub     r8, r9
0x140014b28  shr     r8, 2
0x140014b2c  test    rax, rax
0x140014b2f  jz      short loc_140014BA4
0x140014b31  mov     rcx, [rdx+20h]
0x140014b35  sub     rcx, rax
0x140014b38  shr     rcx, 2
0x140014b3c  add     r8, rcx
0x140014b3f  jmp     short loc_140014BA4
0x140014b41  test    rbp, rbp
0x140014b44  jz      short loc_140014B95
0x140014b46  mov     rcx, [rdx+30h]
0x140014b4a  sub     rcx, rbp
0x140014b4d  shr     rcx, 2
0x140014b51  jmp     short loc_140014BB2
0x140014b53  test    r9, r9
0x140014b56  jz      short loc_140014B87
0x140014b58  mov     rcx, [rdx+10h]
0x140014b5c  sub     rcx, r9
0x140014b5f  shr     rcx, 2
0x140014b63  test    rax, rax
0x140014b66  jz      short loc_140014BB2
0x140014b68  mov     r8, [rdx+20h]
0x140014b6c  sub     r8, rax
0x140014b6f  shr     r8, 2
0x140014b73  jmp     short loc_140014BAF
0x140014b75  test    rax, rax
0x140014b78  jz      short loc_140014BA1
0x140014b7a  mov     r8, [rdx+20h]
0x140014b7e  sub     r8, rax
0x140014b81  shr     r8, 2
0x140014b85  jmp     short loc_140014BA4
0x140014b87  test    rax, rax
0x140014b8a  jz      short loc_140014B95
0x140014b8c  mov     rcx, [rdx+20h]
0x140014b90  sub     rcx, rax
0x140014b93  jmp     short loc_140014B4D
0x140014b95  lea     r12, [r10+10h]
0x140014b99  mov     rax, [r10]
0x140014b9c  jmp     loc_140014C44
0x140014ba1  xor     r8d, r8d
0x140014ba4  mov     rcx, [rdx+30h]
0x140014ba8  sub     rcx, rbp
0x140014bab  shr     rcx, 2
0x140014baf  add     rcx, r8
0x140014bb2  lea     r12, [r10+10h]
0x140014bb6  mov     rax, [r10]
0x140014bb9  mov     r8, [r10+10h]
0x140014bbd  mov     r9, rax
0x140014bc0  sub     r9, r8
0x140014bc3  cmp     rcx, r9
0x140014bc6  jbe     short loc_140014C44
0x140014bc8  add     r8, rcx
0x140014bcb  jnb     short loc_140014BD4
0x140014bcd  xor     eax, eax
0x140014bcf  jmp     loc_140014D89
0x140014bd4  mov     rsi, rdx
0x140014bd7  lea     rcx, [rax+rax]
0x140014bdb  cmp     r8, rcx
0x140014bde  cmova   rcx, r8
0x140014be2  cmp     rcx, 5
0x140014be6  mov     r9d, 4
0x140014bec  cmovnb  r9, rcx
0x140014bf0  mov     r8, [r10+8]
0x140014bf4  mov     [rsp+0B8h+var_90], 4
0x140014bfd  mov     [rsp+0B8h+var_98], 4
0x140014c06  lea     rcx, [rsp+0B8h+var_60]
0x140014c0b  mov     rdx, rax
0x140014c0e  mov     rdi, r9
0x140014c11  mov     rbx, r10
0x140014c14  call    _RNvMs4_NtCsexo9QDNEsji_5alloc7raw_vecINtB5_11RawVecInnerINtCsdwtLm5uWta6_10gdi_region22ScanLookAsideAllocatorKj70_EE11finish_growCsdcpJtfrLhSH_7rgncore_llvm_18110786352924170244
0x140014c19  cmp     dword ptr [rsp+0B8h+var_60], 1
0x140014c1e  jnz     short loc_140014C2F
0x140014c20  mov     rax, [rsp+0B8h+var_58]
0x140014c25  mov     rdx, [rsp+0B8h+var_50]
0x140014c2a  jmp     loc_140014D89
0x140014c2f  mov     rax, [rsp+0B8h+var_58]
0x140014c34  mov     [rbx+8], rax
0x140014c38  mov     rax, rdi
0x140014c3b  mov     [rbx], rdi
0x140014c3e  mov     rdx, rsi
0x140014c41  mov     r10, rbx
0x140014c44  mov     r9, [rdx+8]
0x140014c48  mov     r11, [rdx+10h]
0x140014c4c  mov     rcx, [rdx+18h]
0x140014c50  mov     r8, [rdx+20h]
0x140014c54  mov     rdx, [rdx+30h]
0x140014c58  mov     [rsp+0B8h+var_68], rdx
0x140014c5d  mov     rdx, r8
0x140014c60  mov     r8, [r10+8]
0x140014c64  mov     [rsp+0B8h+var_70], r10
0x140014c69  mov     [rsp+0B8h+var_78], r11
0x140014c6e  mov     [rsp+0B8h+var_80], rdx
0x140014c73  jmp     short loc_140014CB4
0x140014c75  lea     rdi, [r9+4]
0x140014c79  mov     r15d, 1
0x140014c7f  mov     rsi, rcx
0x140014c82  mov     r14, rbp
0x140014c85  nop     word ptr [rax+rax+00000000h]
0x140014c90  mov     ebx, [r9]
0x140014c93  mov     r13, [r12]
0x140014c97  cmp     rax, r13
0x140014c9a  jz      loc_140014D1E
0x140014ca0  mov     [r8+r13*4], ebx
0x140014ca4  inc     r13
0x140014ca7  mov     [r12], r13
0x140014cab  mov     r9, rdi
0x140014cae  mov     rcx, rsi
0x140014cb1  mov     rbp, r14
0x140014cb4  cmp     r15, 1
0x140014cb8  jnz     short loc_140014CF0
0x140014cba  test    r9, r9
0x140014cbd  jz      short loc_140014CC4
0x140014cbf  cmp     r9, r11
0x140014cc2  jnz     short loc_140014C75
0x140014cc4  test    rcx, rcx
0x140014cc7  jz      short loc_140014D15
0x140014cc9  mov     edi, 0
0x140014cce  cmp     rcx, rdx
0x140014cd1  jz      short loc_140014CF3
0x140014cd3  lea     rsi, [rcx+4]
0x140014cd7  mov     r15d, 1
0x140014cdd  xor     edi, edi
0x140014cdf  mov     r14, rbp
0x140014ce2  mov     r9, rcx
0x140014ce5  jmp     short loc_140014C90
0x140014cf0  mov     rdi, r9
0x140014cf3  test    rbp, rbp
0x140014cf6  jz      loc_140014D7F
0x140014cfc  cmp     rbp, [rsp+0B8h+var_68]
0x140014d01  jz      short loc_140014D7F
0x140014d03  lea     r14, [rbp+4]
0x140014d07  xor     r15d, r15d
0x140014d0a  mov     rsi, rcx
0x140014d0d  mov     r9, rbp
0x140014d10  jmp     loc_140014C90
0x140014d15  xor     edi, edi
0x140014d17  test    rbp, rbp
0x140014d1a  jnz     short loc_140014CFC
0x140014d1c  jmp     short loc_140014D7F
0x140014d1e  lea     rbp, [rax+rax]
0x140014d22  cmp     rbp, 5
0x140014d26  mov     ecx, 4
0x140014d2b  cmovb   rbp, rcx
0x140014d2f  mov     [rsp+0B8h+var_90], 4
0x140014d38  mov     [rsp+0B8h+var_98], 4
0x140014d41  lea     rcx, [rsp+0B8h+var_60]
0x140014d46  mov     rdx, rax
0x140014d49  mov     r9, rbp
0x140014d4c  call    _RNvMs4_NtCsexo9QDNEsji_5alloc7raw_vecINtB5_11RawVecInnerINtCsdwtLm5uWta6_10gdi_region22ScanLookAsideAllocatorKj70_EE11finish_growCsdcpJtfrLhSH_7rgncore_llvm_18110786352924170244
0x140014d51  cmp     dword ptr [rsp+0B8h+var_60], 1
0x140014d56  jz      loc_140014C20
0x140014d5c  mov     r8, [rsp+0B8h+var_58]
0x140014d61  mov     r10, [rsp+0B8h+var_70]
0x140014d66  mov     [r10+8], r8
0x140014d6a  mov     [r10], rbp
0x140014d6d  mov     rax, rbp
0x140014d70  mov     r11, [rsp+0B8h+var_78]
0x140014d75  mov     rdx, [rsp+0B8h+var_80]
0x140014d7a  jmp     loc_140014CA0
0x140014d7f  mov     rax, 8000000000000001h
0x140014d89  mov     r8, [rsp+0B8h+var_48]
0x140014d8e  xor     r8, rsp
0x140014d91  mov     rcx, cs:__security_cookie
0x140014d98  cmp     rcx, r8
0x140014d9b  jnz     short loc_140014DAE
0x140014d9d  add     rsp, 78h
0x140014da1  pop     rbx
0x140014da2  pop     rbp
0x140014da3  pop     rdi
0x140014da4  pop     rsi
0x140014da5  pop     r12
0x140014da7  pop     r13
0x140014da9  pop     r14
0x140014dab  pop     r15
0x140014dad  retn
0x140014dae  mov     rcx, [rsp+0B8h+var_48]
0x140014db3  xor     rcx, rsp; StackCookie
0x140014db6  call    __security_check_cookie
```
