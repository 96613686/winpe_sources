# CRunningShareManager::RuntimeClassInitialize(void)

- ea: `0x18000edb0`
- end: `0x18000f2bc`
- name: `?RuntimeClassInitialize@CRunningShareManager@@QEAAJXZ`
- size: `1292`
- prototype: `__int64 __fastcall(CRunningShareManager *__hidden this)`
- caller_count: `2`
- callee_count: `3`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x18000ec50`
- `0x18000ed00`

## callees

- `0x18000edb0`
- `0x18002bc68`
- `0x180085010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemRealloc` at `0x18000ee9f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemRealloc` at `0x18000f042`
- `api-ms-win-core-com-l1-1-0!CoTaskMemRealloc` at `0x18000f1e5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemRealloc` at `0x18000ee9f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemRealloc` at `0x18000f042`
- `api-ms-win-core-com-l1-1-0!CoTaskMemRealloc` at `0x18000f1e5`
- `api-ms-win-core-com-l1-1-0!CoGetMalloc` at `0x18000eebe`
- `api-ms-win-core-com-l1-1-0!CoGetMalloc` at `0x18000f061`
- `api-ms-win-core-com-l1-1-0!CoGetMalloc` at `0x18000f204`
- `api-ms-win-core-com-l1-1-0!CoGetMalloc` at `0x18000eebe`
- `api-ms-win-core-com-l1-1-0!CoGetMalloc` at `0x18000f061`
- `api-ms-win-core-com-l1-1-0!CoGetMalloc` at `0x18000f204`

## pseudocode

```c
__int64 __fastcall CRunningShareManager::RuntimeClassInitialize(CRunningShareManager *this)
{
  int v2; // r12d
  unsigned __int64 v3; // r8
  int v4; // edx
  __int64 v5; // rdi
  unsigned __int64 v6; // rdi
  __int64 v7; // rax
  unsigned __int64 v8; // rcx
  unsigned __int64 v9; // r8
  unsigned __int64 v10; // r14
  char *v11; // r15
  unsigned __int64 v12; // r13
  _OWORD *v13; // r8
  int i; // r13d
  unsigned __int64 v15; // r8
  __int64 v16; // rdi
  unsigned __int64 v17; // rdi
  __int64 v18; // rax
  unsigned __int64 v19; // rcx
  unsigned __int64 v20; // r8
  unsigned __int64 v21; // r14
  char *v22; // r15
  unsigned __int64 v23; // r12
  _OWORD *v24; // r8
  int j; // r13d
  unsigned __int64 v26; // r8
  __int64 v27; // rdi
  unsigned __int64 v28; // rdi
  __int64 v29; // rax
  unsigned __int64 v30; // rcx
  unsigned __int64 v31; // r8
  unsigned __int64 v32; // r14
  char *v33; // r15
  unsigned __int64 v34; // r12
  _OWORD *v35; // r8
  LPMALLOC ppMalloc; // [rsp+90h] [rbp+48h] BYREF

  v2 = 0;
  do
  {
    if ( v2 )
    {
      for ( i = 0; !i; i = 1 )
      {
        v15 = *((_QWORD *)this + 13);
        v4 = 0;
        v16 = *((_QWORD *)this + 11);
        if ( v16 != v15 )
          goto LABEL_49;
        v17 = v16 + 1;
        v4 = -2147024774;
        if ( v17 > 0xFFFFFFFE || (v4 = 0, v17 <= v15) )
        {
          if ( v4 >= 0 )
            goto LABEL_49;
        }
        else
        {
          ppMalloc = 0;
          v18 = 2 * v15;
          if ( is_mul_ok(v15, 2u) )
          {
            v19 = v15;
            v20 = v15 + 4096;
            if ( v19 <= 0x1000 )
              v20 = v18;
            if ( v17 <= v20 )
            {
              v17 = v20;
              if ( v20 > 0xFFFFFFFE )
                v17 = 4294967294LL;
            }
            ppMalloc = 0;
            v21 = 32 * v17;
            if ( is_mul_ok(v17, 0x20u) )
            {
              v22 = (char *)CoTaskMemRealloc(*((LPVOID *)this + 10), 32 * v17);
              if ( v22 )
              {
                ppMalloc = 0;
                if ( CoGetMalloc(1u, &ppMalloc) >= 0 )
                {
                  v23 = ((__int64 (__fastcall *)(LPMALLOC, char *))ppMalloc->lpVtbl->GetSize)(ppMalloc, v22);
                  ((void (__fastcall *)(LPMALLOC))ppMalloc->lpVtbl->Release)(ppMalloc);
                  if ( v23 > v21 )
                    memset_0(&v22[v21], 0, v23 - v21);
                }
                v4 = 0;
              }
              else
              {
                v4 = -2147024882;
              }
              if ( v4 < 0 )
                goto LABEL_51;
              *((_QWORD *)this + 13) = v17;
              *((_QWORD *)this + 10) = v22;
LABEL_49:
              ++*((_QWORD *)this + 11);
              v24 = (_OWORD *)(32LL * *((_QWORD *)this + 11) + *((_QWORD *)this + 10) - 32LL);
              if ( v24 )
              {
                *v24 = *(_OWORD *)&SID_ShareFlow.Revision;
                v24[1] = 0;
              }
              goto LABEL_51;
            }
          }
          v4 = -2147024362;
        }
LABEL_51:
        if ( v4 < 0 )
          return (unsigned int)v4;
      }
      v4 = 0;
      for ( j = 0; ; j = 1 )
      {
        if ( j )
          return (unsigned int)v4;
        v26 = *((_QWORD *)this + 13);
        v4 = 0;
        v27 = *((_QWORD *)this + 11);
        if ( v27 != v26 )
          goto LABEL_75;
        v28 = v27 + 1;
        v4 = -2147024774;
        if ( v28 > 0xFFFFFFFE || (v4 = 0, v28 <= v26) )
        {
          if ( v4 >= 0 )
            goto LABEL_75;
        }
        else
        {
          ppMalloc = 0;
          v29 = 2 * v26;
          if ( is_mul_ok(v26, 2u) )
          {
            v30 = v26;
            v31 = v26 + 4096;
            if ( v30 <= 0x1000 )
              v31 = v29;
            if ( v28 <= v31 )
            {
              v28 = v31;
              if ( v31 > 0xFFFFFFFE )
                v28 = 4294967294LL;
            }
            ppMalloc = 0;
            v32 = 32 * v28;
            if ( is_mul_ok(v28, 0x20u) )
            {
              v33 = (char *)CoTaskMemRealloc(*((LPVOID *)this + 10), 32 * v28);
              if ( v33 )
              {
                ppMalloc = 0;
                if ( CoGetMalloc(1u, &ppMalloc) >= 0 )
                {
                  v34 = ((__int64 (__fastcall *)(LPMALLOC, char *))ppMalloc->lpVtbl->GetSize)(ppMalloc, v33);
                  ((void (__fastcall *)(LPMALLOC))ppMalloc->lpVtbl->Release)(ppMalloc);
                  if ( v34 > v32 )
                    memset_0(&v33[v32], 0, v34 - v32);
                }
                v4 = 0;
              }
              else
              {
                v4 = -2147024882;
              }
              if ( v4 < 0 )
                goto LABEL_77;
              *((_QWORD *)this + 13) = v28;
              *((_QWORD *)this + 10) = v33;
LABEL_75:
              ++*((_QWORD *)this + 11);
              v35 = (_OWORD *)(32LL * *((_QWORD *)this + 11) + *((_QWORD *)this + 10) - 32LL);
              if ( v35 )
              {
                *v35 = *(_OWORD *)&SID_DevicesFlow.Revision;
                v35[1] = 0;
              }
              goto LABEL_77;
            }
          }
          v4 = -2147024362;
        }
LABEL_77:
        if ( v4 < 0 )
          return (unsigned int)v4;
      }
    }
    v3 = *((_QWORD *)this + 13);
    v4 = 0;
    v5 = *((_QWORD *)this + 11);
    if ( v5 != v3 )
      goto LABEL_23;
    v6 = v5 + 1;
    v4 = -2147024774;
    if ( v6 > 0xFFFFFFFE || (v4 = 0, v6 <= v3) )
    {
      if ( v4 < 0 )
        goto LABEL_25;
      goto LABEL_23;
    }
    ppMalloc = 0;
    v7 = 2 * v3;
    if ( !is_mul_ok(v3, 2u) )
      goto LABEL_21;
    v8 = v3;
    v9 = v3 + 4096;
    if ( v8 <= 0x1000 )
      v9 = v7;
    if ( v6 <= v9 )
    {
      v6 = v9;
      if ( v9 > 0xFFFFFFFE )
        v6 = 4294967294LL;
    }
    ppMalloc = 0;
    v10 = 32 * v6;
    if ( !is_mul_ok(v6, 0x20u) )
    {
LABEL_21:
      v4 = -2147024362;
      goto LABEL_25;
    }
    v11 = (char *)CoTaskMemRealloc(*((LPVOID *)this + 10), 32 * v6);
    if ( v11 )
    {
      ppMalloc = 0;
      if ( CoGetMalloc(1u, &ppMalloc) >= 0 )
      {
        v12 = ((__int64 (__fastcall *)(LPMALLOC, char *))ppMalloc->lpVtbl->GetSize)(ppMalloc, v11);
        ((void (__fastcall *)(LPMALLOC))ppMalloc->lpVtbl->Release)(ppMalloc);
        if ( v12 > v10 )
          memset_0(&v11[v10], 0, v12 - v10);
      }
      v4 = 0;
    }
    else
    {
      v4 = -2147024882;
    }
    if ( v4 >= 0 )
    {
      *((_QWORD *)this + 13) = v6;
      *((_QWORD *)this + 10) = v11;
LABEL_23:
      ++*((_QWORD *)this + 11);
      v13 = (_OWORD *)(32LL * *((_QWORD *)this + 11) + *((_QWORD *)this + 10) - 32LL);
      if ( v13 )
      {
        *v13 = *(_OWORD *)&SID_RunningShareManager.Revision;
        v13[1] = 0;
      }
    }
LABEL_25:
    v2 = 1;
  }
  while ( v4 >= 0 );
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x18000edb0  push    rbp
0x18000edb2  push    rbx
0x18000edb3  push    rsi
0x18000edb4  push    rdi
0x18000edb5  push    r12
0x18000edb7  push    r13
0x18000edb9  push    r14
0x18000edbb  push    r15
0x18000edbd  mov     rbp, rsp
0x18000edc0  sub     rsp, 48h
0x18000edc4  movups  xmm0, xmmword ptr cs:SID_RunningShareManager.Revision
0x18000edcb  xor     edx, edx
0x18000edcd  mov     rbx, rcx
0x18000edd0  xorps   xmm1, xmm1
0x18000edd3  xor     r12d, r12d
0x18000edd6  movdqu  [rbp+var_28], xmm0
0x18000eddb  mov     r9d, 0FFFFFFFEh
0x18000ede1  movdqu  [rbp+var_18], xmm1
0x18000ede6  cmp     r12d, 1
0x18000edea  jnb     loc_18000EF68
0x18000edf0  mov     esi, r12d
0x18000edf3  shl     rsi, 5
0x18000edf7  mov     rcx, qword ptr [rbp+rsi+var_18]
0x18000edfc  test    rcx, rcx
0x18000edff  jz      short loc_18000EE13
0x18000ee01  mov     rax, [rcx]
0x18000ee04  mov     rax, [rax+8]
0x18000ee08  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ee0d  mov     r9d, 0FFFFFFFEh
0x18000ee13  mov     r8, [rbx+68h]
0x18000ee17  xor     edx, edx
0x18000ee19  mov     rdi, [rbx+58h]
0x18000ee1d  cmp     rdi, r8
0x18000ee20  jnz     loc_18000EF26
0x18000ee26  inc     rdi
0x18000ee29  mov     edx, 8007007Ah
0x18000ee2e  cmp     rdi, r9
0x18000ee31  ja      loc_18000EF22
0x18000ee37  xor     edx, edx
0x18000ee39  cmp     rdi, r8
0x18000ee3c  jbe     loc_18000EF22
0x18000ee42  lea     eax, [rdx+2]
0x18000ee45  mov     [rbp+ppMalloc], rdx
0x18000ee49  mul     r8
0x18000ee4c  test    rdx, rdx
0x18000ee4f  jnz     loc_18000EF1B
0x18000ee55  mov     rcx, rax
0x18000ee58  sub     rcx, r8
0x18000ee5b  add     r8, 1000h
0x18000ee62  cmp     rcx, 1000h
0x18000ee69  cmovbe  r8, rax
0x18000ee6d  cmp     rdi, r8
0x18000ee70  ja      short loc_18000EE7C
0x18000ee72  cmp     r8, r9
0x18000ee75  mov     rdi, r8
0x18000ee78  cmova   rdi, r9
0x18000ee7c  mov     eax, 20h ; ' '
0x18000ee81  mov     [rbp+ppMalloc], 0
0x18000ee89  mul     rdi
0x18000ee8c  mov     r14, rax
0x18000ee8f  test    rdx, rdx
0x18000ee92  jnz     loc_18000EF1B
0x18000ee98  mov     rcx, [rbx+50h]; pv
0x18000ee9c  mov     rdx, rax; cb
0x18000ee9f  call    cs:__imp_CoTaskMemRealloc
0x18000eea5  mov     r15, rax
0x18000eea8  test    rax, rax
0x18000eeab  jz      short loc_18000EF08
0x18000eead  lea     rdx, [rbp+ppMalloc]; ppMalloc
0x18000eeb1  mov     [rbp+ppMalloc], 0
0x18000eeb9  mov     ecx, 1; dwMemContext
0x18000eebe  call    cs:__imp_CoGetMalloc
0x18000eec4  test    eax, eax
0x18000eec6  js      short loc_18000EF04
0x18000eec8  mov     rcx, [rbp+ppMalloc]
0x18000eecc  mov     rdx, [rcx]
0x18000eecf  mov     rax, [rdx+30h]
0x18000eed3  mov     rdx, r15
0x18000eed6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000eedb  mov     rcx, [rbp+ppMalloc]
0x18000eedf  mov     r13, rax
0x18000eee2  mov     rdx, [rcx]
0x18000eee5  mov     rax, [rdx+10h]
0x18000eee9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000eeee  cmp     r13, r14
0x18000eef1  jbe     short loc_18000EF04
0x18000eef3  sub     r13, r14
0x18000eef6  lea     rcx, [r14+r15]; void *
0x18000eefa  mov     r8, r13; Size
0x18000eefd  xor     edx, edx; Val
0x18000eeff  call    memset_0
0x18000ef04  xor     edx, edx
0x18000ef06  jmp     short loc_18000EF0D
0x18000ef08  mov     edx, 8007000Eh
0x18000ef0d  test    edx, edx
0x18000ef0f  js      short loc_18000EF52
0x18000ef11  mov     [rbx+68h], rdi
0x18000ef15  mov     [rbx+50h], r15
0x18000ef19  jmp     short loc_18000EF26
0x18000ef1b  mov     edx, 80070216h
0x18000ef20  jmp     short loc_18000EF52
0x18000ef22  test    edx, edx
0x18000ef24  js      short loc_18000EF52
0x18000ef26  inc     qword ptr [rbx+58h]
0x18000ef2a  mov     rcx, [rbx+58h]
0x18000ef2e  mov     r8, [rbx+50h]
0x18000ef32  shl     rcx, 5
0x18000ef36  add     r8, 0FFFFFFFFFFFFFFE0h
0x18000ef3a  add     r8, rcx
0x18000ef3d  jz      short loc_18000EF52
0x18000ef3f  movups  xmm0, [rbp+rsi+var_28]
0x18000ef44  movups  xmm1, [rbp+rsi+var_18]
0x18000ef49  movups  xmmword ptr [r8], xmm0
0x18000ef4d  movups  xmmword ptr [r8+10h], xmm1
0x18000ef52  inc     r12d
0x18000ef55  mov     r9d, 0FFFFFFFEh
0x18000ef5b  test    edx, edx
0x18000ef5d  jns     loc_18000EDE6
0x18000ef63  jmp     loc_18000F2A9
0x18000ef68  test    edx, edx
0x18000ef6a  js      loc_18000F2A9
0x18000ef70  movups  xmm0, xmmword ptr cs:SID_ShareFlow.Revision
0x18000ef77  xor     edx, edx
0x18000ef79  xorps   xmm1, xmm1
0x18000ef7c  xor     r13d, r13d
0x18000ef7f  movdqu  [rbp+var_28], xmm0
0x18000ef84  movdqu  [rbp+var_18], xmm1
0x18000ef89  cmp     r13d, 1
0x18000ef8d  jnb     loc_18000F10B
0x18000ef93  mov     esi, r13d
0x18000ef96  shl     rsi, 5
0x18000ef9a  mov     rcx, qword ptr [rbp+rsi+var_18]
0x18000ef9f  test    rcx, rcx
0x18000efa2  jz      short loc_18000EFB6
0x18000efa4  mov     rax, [rcx]
0x18000efa7  mov     rax, [rax+8]
0x18000efab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000efb0  mov     r9d, 0FFFFFFFEh
0x18000efb6  mov     r8, [rbx+68h]
0x18000efba  xor     edx, edx
0x18000efbc  mov     rdi, [rbx+58h]
0x18000efc0  cmp     rdi, r8
0x18000efc3  jnz     loc_18000F0C9
0x18000efc9  inc     rdi
0x18000efcc  mov     edx, 8007007Ah
0x18000efd1  cmp     rdi, r9
0x18000efd4  ja      loc_18000F0C5
0x18000efda  xor     edx, edx
0x18000efdc  cmp     rdi, r8
0x18000efdf  jbe     loc_18000F0C5
0x18000efe5  lea     eax, [rdx+2]
0x18000efe8  mov     [rbp+ppMalloc], rdx
0x18000efec  mul     r8
0x18000efef  test    rdx, rdx
0x18000eff2  jnz     loc_18000F0BE
0x18000eff8  mov     rcx, rax
0x18000effb  sub     rcx, r8
0x18000effe  add     r8, 1000h
0x18000f005  cmp     rcx, 1000h
0x18000f00c  cmovbe  r8, rax
0x18000f010  cmp     rdi, r8
0x18000f013  ja      short loc_18000F01F
0x18000f015  cmp     r8, r9
0x18000f018  mov     rdi, r8
0x18000f01b  cmova   rdi, r9
0x18000f01f  mov     eax, 20h ; ' '
0x18000f024  mov     [rbp+ppMalloc], 0
0x18000f02c  mul     rdi
0x18000f02f  mov     r14, rax
0x18000f032  test    rdx, rdx
0x18000f035  jnz     loc_18000F0BE
0x18000f03b  mov     rcx, [rbx+50h]; pv
0x18000f03f  mov     rdx, rax; cb
0x18000f042  call    cs:__imp_CoTaskMemRealloc
0x18000f048  mov     r15, rax
0x18000f04b  test    rax, rax
0x18000f04e  jz      short loc_18000F0AB
0x18000f050  lea     rdx, [rbp+ppMalloc]; ppMalloc
0x18000f054  mov     [rbp+ppMalloc], 0
0x18000f05c  mov     ecx, 1; dwMemContext
0x18000f061  call    cs:__imp_CoGetMalloc
0x18000f067  test    eax, eax
0x18000f069  js      short loc_18000F0A7
0x18000f06b  mov     rcx, [rbp+ppMalloc]
0x18000f06f  mov     rdx, [rcx]
0x18000f072  mov     rax, [rdx+30h]
0x18000f076  mov     rdx, r15
0x18000f079  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f07e  mov     rcx, [rbp+ppMalloc]
0x18000f082  mov     r12, rax
0x18000f085  mov     rdx, [rcx]
0x18000f088  mov     rax, [rdx+10h]
0x18000f08c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f091  cmp     r12, r14
0x18000f094  jbe     short loc_18000F0A7
0x18000f096  sub     r12, r14
0x18000f099  lea     rcx, [r14+r15]; void *
0x18000f09d  mov     r8, r12; Size
0x18000f0a0  xor     edx, edx; Val
0x18000f0a2  call    memset_0
0x18000f0a7  xor     edx, edx
0x18000f0a9  jmp     short loc_18000F0B0
0x18000f0ab  mov     edx, 8007000Eh
0x18000f0b0  test    edx, edx
0x18000f0b2  js      short loc_18000F0F5
0x18000f0b4  mov     [rbx+68h], rdi
0x18000f0b8  mov     [rbx+50h], r15
0x18000f0bc  jmp     short loc_18000F0C9
0x18000f0be  mov     edx, 80070216h
0x18000f0c3  jmp     short loc_18000F0F5
0x18000f0c5  test    edx, edx
0x18000f0c7  js      short loc_18000F0F5
0x18000f0c9  inc     qword ptr [rbx+58h]
0x18000f0cd  mov     rcx, [rbx+58h]
0x18000f0d1  mov     r8, [rbx+50h]
0x18000f0d5  shl     rcx, 5
0x18000f0d9  add     r8, 0FFFFFFFFFFFFFFE0h
0x18000f0dd  add     r8, rcx
0x18000f0e0  jz      short loc_18000F0F5
0x18000f0e2  movups  xmm0, [rbp+rsi+var_28]
0x18000f0e7  movups  xmm1, [rbp+rsi+var_18]
0x18000f0ec  movups  xmmword ptr [r8], xmm0
0x18000f0f0  movups  xmmword ptr [r8+10h], xmm1
0x18000f0f5  inc     r13d
0x18000f0f8  mov     r9d, 0FFFFFFFEh
0x18000f0fe  test    edx, edx
0x18000f100  jns     loc_18000EF89
0x18000f106  jmp     loc_18000F2A9
0x18000f10b  test    edx, edx
0x18000f10d  js      loc_18000F2A9
0x18000f113  movups  xmm0, xmmword ptr cs:SID_DevicesFlow.Revision
0x18000f11a  xor     edx, edx
0x18000f11c  xorps   xmm1, xmm1
0x18000f11f  xor     r13d, r13d
0x18000f122  movdqu  [rbp+var_28], xmm0
0x18000f127  movdqu  [rbp+var_18], xmm1
0x18000f12c  cmp     r13d, 1
0x18000f130  jnb     loc_18000F2A9
0x18000f136  mov     esi, r13d
0x18000f139  shl     rsi, 5
0x18000f13d  mov     rcx, qword ptr [rbp+rsi+var_18]
0x18000f142  test    rcx, rcx
0x18000f145  jz      short loc_18000F159
0x18000f147  mov     rax, [rcx]
0x18000f14a  mov     rax, [rax+8]
0x18000f14e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f153  mov     r9d, 0FFFFFFFEh
0x18000f159  mov     r8, [rbx+68h]
0x18000f15d  xor     edx, edx
0x18000f15f  mov     rdi, [rbx+58h]
0x18000f163  cmp     rdi, r8
0x18000f166  jnz     loc_18000F26C
0x18000f16c  inc     rdi
0x18000f16f  mov     edx, 8007007Ah
0x18000f174  cmp     rdi, r9
0x18000f177  ja      loc_18000F268
0x18000f17d  xor     edx, edx
0x18000f17f  cmp     rdi, r8
0x18000f182  jbe     loc_18000F268
0x18000f188  lea     eax, [rdx+2]
0x18000f18b  mov     [rbp+ppMalloc], rdx
0x18000f18f  mul     r8
0x18000f192  test    rdx, rdx
0x18000f195  jnz     loc_18000F261
0x18000f19b  mov     rcx, rax
0x18000f19e  sub     rcx, r8
0x18000f1a1  add     r8, 1000h
0x18000f1a8  cmp     rcx, 1000h
0x18000f1af  cmovbe  r8, rax
0x18000f1b3  cmp     rdi, r8
0x18000f1b6  ja      short loc_18000F1C2
0x18000f1b8  cmp     r8, r9
0x18000f1bb  mov     rdi, r8
0x18000f1be  cmova   rdi, r9
0x18000f1c2  mov     eax, 20h ; ' '
0x18000f1c7  mov     [rbp+ppMalloc], 0
0x18000f1cf  mul     rdi
0x18000f1d2  mov     r14, rax
0x18000f1d5  test    rdx, rdx
0x18000f1d8  jnz     loc_18000F261
0x18000f1de  mov     rcx, [rbx+50h]; pv
0x18000f1e2  mov     rdx, rax; cb
0x18000f1e5  call    cs:__imp_CoTaskMemRealloc
0x18000f1eb  mov     r15, rax
0x18000f1ee  test    rax, rax
0x18000f1f1  jz      short loc_18000F24E
0x18000f1f3  lea     rdx, [rbp+ppMalloc]; ppMalloc
0x18000f1f7  mov     [rbp+ppMalloc], 0
0x18000f1ff  mov     ecx, 1; dwMemContext
0x18000f204  call    cs:__imp_CoGetMalloc
0x18000f20a  test    eax, eax
0x18000f20c  js      short loc_18000F24A
0x18000f20e  mov     rcx, [rbp+ppMalloc]
0x18000f212  mov     rdx, [rcx]
0x18000f215  mov     rax, [rdx+30h]
0x18000f219  mov     rdx, r15
0x18000f21c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f221  mov     rcx, [rbp+ppMalloc]
0x18000f225  mov     r12, rax
0x18000f228  mov     rdx, [rcx]
  ... truncated ...
```
