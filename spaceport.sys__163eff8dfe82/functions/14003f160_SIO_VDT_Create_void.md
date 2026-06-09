# SIO_VDT::Create(void)

- ea: `0x14003f160`
- end: `0x14003f390`
- name: `?Create@SIO_VDT@@IEAAJXZ`
- size: `560`
- prototype: `__int64 __fastcall(SIO_VDT *__hidden this)`
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x14002a860`

## callees

- `0x1400268c0`
- `0x140026db0`
- `0x14002aa3c`
- `0x14003f160`
- `0x140051cf8`
- `0x140052850`
- `0x140068150`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x14003f369`
- `ntoskrnl!ExFreePoolWithTag` at `0x14003f369`
- `ntoskrnl!RtlComputeCrc32` at `0x14003f2fe`
- `ntoskrnl!RtlComputeCrc32` at `0x14003f2fe`

## pseudocode

```c
__int64 __fastcall SIO_VDT::Create(SIO_VDT *this)
{
  char *v2; // rdi
  __int64 v3; // rax
  __int64 v4; // rdx
  __int64 Child; // rax
  __int64 v6; // r10
  unsigned int v7; // r8d
  unsigned __int64 v8; // r12
  unsigned int v9; // r14d
  unsigned __int64 v10; // r15
  int v11; // ecx
  unsigned int v12; // r13d
  unsigned __int64 v13; // rbp
  unsigned int v14; // ebx
  __int128 v15; // xmm0
  int v16; // ecx
  ULONG v17; // eax
  struct _GUID v19; // [rsp+20h] [rbp-48h] BYREF
  __int64 v20; // [rsp+70h] [rbp+8h]
  unsigned __int64 v21; // [rsp+78h] [rbp+10h]

  v2 = 0;
  v3 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 1) + 80LL))(*((_QWORD *)this + 1));
  LOBYTE(v4) = 10;
  Child = SIO_SPACE::GetChild(v3, v4);
  v7 = *((_DWORD *)this + 26);
  v8 = *(_QWORD *)(v6 + 120);
  *((_QWORD *)this + 40) = v8;
  v9 = v7;
  if ( v7 < 0x1000 )
    v9 = 4096;
  v20 = 2 * v9;
  v10 = ((v9 << 10) + v20 + 0x1FFFFF) & 0xFFFFFFFFFFE00000uLL;
  if ( v10 >= *(_QWORD *)(Child + 112)
    || (v11 = v8 / *((unsigned int *)this + 78), v8 / *((unsigned int *)this + 78) > 0xFFFFFFFF)
    || *(_QWORD *)(v6 + 112) / v8 > 0xFFFFFFFF
    || (*((_DWORD *)this + 82) = v11,
        v12 = (((unsigned int)(v11 + 7) >> 3) + 19) & 0xFFFFFFF8,
        (unsigned __int64)v12 + 56 > v9)
    || (v13 = (*(_QWORD *)(Child + 112) - v10) >> 1, v13 > 0xFFFFFFFF) )
  {
    v14 = -1073741637;
  }
  else
  {
    v21 = *(_QWORD *)(v6 + 112);
    v2 = (char *)SC_ENV::Allocate(v7, 0x58587053u, 0, 0);
    if ( v2 )
    {
      *(_QWORD *)v2 = 0x5444565053LL;
      v15 = (__int128)*SIO_SLOTS::GetHeaderSpaceId((SIO_VDT *)((char *)this + 16), &v19, 1u);
      *((_QWORD *)v2 + 10) = *((_QWORD *)this + 40);
      v16 = *((_DWORD *)this + 78);
      *((_DWORD *)v2 + 6) = 1;
      *((_QWORD *)v2 + 5) = 1;
      *((_DWORD *)v2 + 22) = v16;
      *((_QWORD *)v2 + 6) = v20;
      *(_QWORD *)(v2 + 28) = 96;
      *((_DWORD *)v2 + 23) = v21 / v8;
      *(_OWORD *)(v2 + 8) = v15;
      *((_DWORD *)v2 + 14) = v9;
      *((_DWORD *)v2 + 15) = 1024;
      *((_QWORD *)v2 + 8) = v10;
      *((_DWORD *)v2 + 18) = v13;
      *((_DWORD *)v2 + 19) = 2;
      v17 = RtlComputeCrc32(0, (PUCHAR)v2, 0x60u);
      *((_DWORD *)this + 9) = 1;
      *((_DWORD *)v2 + 9) = v17;
      *((_QWORD *)this + 5) = v20;
      *((_DWORD *)this + 12) = v9;
      *((_DWORD *)this + 13) = 1024;
      *((_QWORD *)this + 7) = v10;
      *((_DWORD *)this + 16) = v13;
      *((_DWORD *)this + 17) = 2;
      *((_DWORD *)this + 19) = v12;
      v14 = SIO_SLOTS::WriteHeader((SIO_VDT *)((char *)this + 16), v2);
    }
    else
    {
      v14 = -1073741670;
    }
  }
  SIO_VDT::LogStatus(this, 2, v14);
  if ( v2 )
    ExFreePoolWithTag(v2, 0);
  return v14;
}

```

## disassembly

```asm
0x14003f160  mov     [rsp+arg_10], rbx
0x14003f165  push    rbp
0x14003f166  push    rsi
0x14003f167  push    rdi
0x14003f168  push    r12
0x14003f16a  push    r13
0x14003f16c  push    r14
0x14003f16e  push    r15
0x14003f170  sub     rsp, 30h
0x14003f174  mov     rsi, rcx
0x14003f177  xor     edi, edi
0x14003f179  mov     rcx, [rcx+8]
0x14003f17d  mov     rax, [rcx]
0x14003f180  mov     rax, [rax+50h]
0x14003f184  call    _guard_dispatch_icall
0x14003f189  mov     dl, 0Ah
0x14003f18b  mov     rcx, rax
0x14003f18e  mov     r10, rax
0x14003f191  call    ?GetChild@SIO_SPACE@@QEAAPEAV1@W4_SC_SPACE_USAGE@@@Z; SIO_SPACE::GetChild(_SC_SPACE_USAGE)
0x14003f196  mov     r8d, [rsi+68h]
0x14003f19a  mov     rbp, rax
0x14003f19d  mov     r12, [r10+78h]
0x14003f1a1  mov     eax, 1000h
0x14003f1a6  cmp     r8d, eax
0x14003f1a9  mov     [rsi+140h], r12
0x14003f1b0  mov     r14d, r8d
0x14003f1b3  cmovb   r14d, eax
0x14003f1b7  mov     eax, r14d
0x14003f1ba  shl     eax, 0Ah
0x14003f1bd  lea     ecx, [r14+r14]
0x14003f1c1  lea     r15, [rcx+1FFFFFh]
0x14003f1c8  mov     [rsp+68h+arg_0], rcx
0x14003f1cd  add     r15, rax
0x14003f1d0  and     r15, 0FFFFFFFFFFE00000h
0x14003f1d7  cmp     r15, [rbp+70h]
0x14003f1db  jnb     loc_14003F34A
0x14003f1e1  mov     ecx, [rsi+138h]
0x14003f1e7  xor     edx, edx
0x14003f1e9  mov     rax, r12
0x14003f1ec  mov     r9d, 0FFFFFFFFh
0x14003f1f2  div     rcx
0x14003f1f5  mov     rcx, rax
0x14003f1f8  cmp     rax, r9
0x14003f1fb  ja      loc_14003F34A
0x14003f201  mov     rax, [r10+70h]
0x14003f205  xor     edx, edx
0x14003f207  div     r12
0x14003f20a  cmp     rax, r9
0x14003f20d  ja      loc_14003F34A
0x14003f213  lea     eax, [rcx+7]
0x14003f216  mov     [rsi+148h], ecx
0x14003f21c  shr     eax, 3
0x14003f21f  add     eax, 13h
0x14003f222  and     eax, 0FFFFFFF8h
0x14003f225  mov     r13d, eax
0x14003f228  lea     rcx, [rax+38h]
0x14003f22c  mov     eax, r14d
0x14003f22f  cmp     rcx, rax
0x14003f232  ja      loc_14003F34A
0x14003f238  mov     rbp, [rbp+70h]
0x14003f23c  sub     rbp, r15
0x14003f23f  shr     rbp, 1
0x14003f242  cmp     rbp, r9
0x14003f245  ja      loc_14003F34A
0x14003f24b  mov     rax, [r10+70h]
0x14003f24f  mov     ecx, r8d; unsigned __int64
0x14003f252  xor     r8d, r8d; unsigned __int8
0x14003f255  mov     [rsp+68h+arg_8], rax
0x14003f25a  xor     r9d, r9d; unsigned int
0x14003f25d  mov     edx, 58587053h; unsigned int
0x14003f262  call    ?Allocate@SC_ENV@@SAPEAX_KKEK@Z; SC_ENV::Allocate(unsigned __int64,ulong,uchar,ulong)
0x14003f267  mov     rdi, rax
0x14003f26a  test    rax, rax
0x14003f26d  jnz     short loc_14003F279
0x14003f26f  mov     ebx, 0C000009Ah
0x14003f274  jmp     loc_14003F34F
0x14003f279  mov     rax, 5444565053h
0x14003f283  lea     rdx, [rsp+68h+var_48]; retstr
0x14003f288  mov     r8d, 1; unsigned int
0x14003f28e  mov     [rdi], rax
0x14003f291  lea     rcx, [rsi+10h]; this
0x14003f295  call    ?GetHeaderSpaceId@SIO_SLOTS@@QEAA?AU_GUID@@K@Z; SIO_SLOTS::GetHeaderSpaceId(ulong)
0x14003f29a  mov     rcx, [rsi+140h]
0x14003f2a1  xor     edx, edx
0x14003f2a3  movups  xmm0, xmmword ptr [rax]
0x14003f2a6  mov     eax, 1
0x14003f2ab  mov     [rdi+50h], rcx
0x14003f2af  mov     ecx, [rsi+138h]
0x14003f2b5  mov     [rdi+18h], eax
0x14003f2b8  mov     [rdi+28h], rax
0x14003f2bc  lea     r8d, [rax+5Fh]; Length
0x14003f2c0  mov     [rdi+58h], ecx
0x14003f2c3  mov     rax, [rsp+68h+arg_0]
0x14003f2c8  xor     ecx, ecx; InitialCrc
0x14003f2ca  mov     [rdi+30h], rax
0x14003f2ce  mov     rax, [rsp+68h+arg_8]
0x14003f2d3  div     r12
0x14003f2d6  mov     rdx, rdi; Buffer
0x14003f2d9  mov     [rdi+1Ch], r8
0x14003f2dd  mov     [rdi+5Ch], eax
0x14003f2e0  movdqu  xmmword ptr [rdi+8], xmm0
0x14003f2e5  mov     [rdi+38h], r14d
0x14003f2e9  mov     dword ptr [rdi+3Ch], 400h
0x14003f2f0  mov     [rdi+40h], r15
0x14003f2f4  mov     [rdi+48h], ebp
0x14003f2f7  mov     dword ptr [rdi+4Ch], 2
0x14003f2fe  call    cs:__imp_RtlComputeCrc32
0x14003f305  nop     dword ptr [rax+rax+00h]
0x14003f30a  mov     rdx, rdi; void *
0x14003f30d  mov     dword ptr [rsi+24h], 1
0x14003f314  mov     [rdi+24h], eax
0x14003f317  lea     rcx, [rsi+10h]; this
0x14003f31b  mov     rax, [rsp+68h+arg_0]
0x14003f320  mov     [rsi+28h], rax
0x14003f324  mov     [rsi+30h], r14d
0x14003f328  mov     dword ptr [rsi+34h], 400h
0x14003f32f  mov     [rsi+38h], r15
0x14003f333  mov     [rsi+40h], ebp
0x14003f336  mov     dword ptr [rsi+44h], 2
0x14003f33d  mov     [rsi+4Ch], r13d
0x14003f341  call    ?WriteHeader@SIO_SLOTS@@QEAAJPEAX@Z; SIO_SLOTS::WriteHeader(void *)
0x14003f346  mov     ebx, eax
0x14003f348  jmp     short loc_14003F34F
0x14003f34a  mov     ebx, 0C00000BBh
0x14003f34f  mov     r8d, ebx
0x14003f352  mov     edx, 2
0x14003f357  mov     rcx, rsi
0x14003f35a  call    ?LogStatus@SIO_VDT@@IEAAXW4SIO_VDT_OPERATION@@J@Z; SIO_VDT::LogStatus(SIO_VDT_OPERATION,long)
0x14003f35f  test    rdi, rdi
0x14003f362  jz      short loc_14003F375
0x14003f364  xor     edx, edx; Tag
0x14003f366  mov     rcx, rdi; P
0x14003f369  call    cs:__imp_ExFreePoolWithTag
0x14003f370  nop     dword ptr [rax+rax+00h]
0x14003f375  mov     eax, ebx
0x14003f377  mov     rbx, [rsp+68h+arg_10]
0x14003f37f  add     rsp, 30h
0x14003f383  pop     r15
0x14003f385  pop     r14
0x14003f387  pop     r13
0x14003f389  pop     r12
0x14003f38b  pop     rdi
0x14003f38c  pop     rsi
0x14003f38d  pop     rbp
0x14003f38e  retn
```
