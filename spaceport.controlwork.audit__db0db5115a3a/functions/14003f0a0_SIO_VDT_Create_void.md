# SIO_VDT::Create(void)

- ea: `0x14003f0a0`
- end: `0x14003f2d0`
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
- `0x14003f0a0`
- `0x140051c38`
- `0x140052790`
- `0x140068000`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x14003f2a9`
- `ntoskrnl!ExFreePoolWithTag` at `0x14003f2a9`
- `ntoskrnl!RtlComputeCrc32` at `0x14003f23e`
- `ntoskrnl!RtlComputeCrc32` at `0x14003f23e`

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
0x14003f0a0  mov     [rsp+arg_10], rbx
0x14003f0a5  push    rbp
0x14003f0a6  push    rsi
0x14003f0a7  push    rdi
0x14003f0a8  push    r12
0x14003f0aa  push    r13
0x14003f0ac  push    r14
0x14003f0ae  push    r15
0x14003f0b0  sub     rsp, 30h
0x14003f0b4  mov     rsi, rcx
0x14003f0b7  xor     edi, edi
0x14003f0b9  mov     rcx, [rcx+8]
0x14003f0bd  mov     rax, [rcx]
0x14003f0c0  mov     rax, [rax+50h]
0x14003f0c4  call    _guard_dispatch_icall
0x14003f0c9  mov     dl, 0Ah
0x14003f0cb  mov     rcx, rax
0x14003f0ce  mov     r10, rax
0x14003f0d1  call    ?GetChild@SIO_SPACE@@QEAAPEAV1@W4_SC_SPACE_USAGE@@@Z; SIO_SPACE::GetChild(_SC_SPACE_USAGE)
0x14003f0d6  mov     r8d, [rsi+68h]
0x14003f0da  mov     rbp, rax
0x14003f0dd  mov     r12, [r10+78h]
0x14003f0e1  mov     eax, 1000h
0x14003f0e6  cmp     r8d, eax
0x14003f0e9  mov     [rsi+140h], r12
0x14003f0f0  mov     r14d, r8d
0x14003f0f3  cmovb   r14d, eax
0x14003f0f7  mov     eax, r14d
0x14003f0fa  shl     eax, 0Ah
0x14003f0fd  lea     ecx, [r14+r14]
0x14003f101  lea     r15, [rcx+1FFFFFh]
0x14003f108  mov     [rsp+68h+arg_0], rcx
0x14003f10d  add     r15, rax
0x14003f110  and     r15, 0FFFFFFFFFFE00000h
0x14003f117  cmp     r15, [rbp+70h]
0x14003f11b  jnb     loc_14003F28A
0x14003f121  mov     ecx, [rsi+138h]
0x14003f127  xor     edx, edx
0x14003f129  mov     rax, r12
0x14003f12c  mov     r9d, 0FFFFFFFFh
0x14003f132  div     rcx
0x14003f135  mov     rcx, rax
0x14003f138  cmp     rax, r9
0x14003f13b  ja      loc_14003F28A
0x14003f141  mov     rax, [r10+70h]
0x14003f145  xor     edx, edx
0x14003f147  div     r12
0x14003f14a  cmp     rax, r9
0x14003f14d  ja      loc_14003F28A
0x14003f153  lea     eax, [rcx+7]
0x14003f156  mov     [rsi+148h], ecx
0x14003f15c  shr     eax, 3
0x14003f15f  add     eax, 13h
0x14003f162  and     eax, 0FFFFFFF8h
0x14003f165  mov     r13d, eax
0x14003f168  lea     rcx, [rax+38h]
0x14003f16c  mov     eax, r14d
0x14003f16f  cmp     rcx, rax
0x14003f172  ja      loc_14003F28A
0x14003f178  mov     rbp, [rbp+70h]
0x14003f17c  sub     rbp, r15
0x14003f17f  shr     rbp, 1
0x14003f182  cmp     rbp, r9
0x14003f185  ja      loc_14003F28A
0x14003f18b  mov     rax, [r10+70h]
0x14003f18f  mov     ecx, r8d; unsigned __int64
0x14003f192  xor     r8d, r8d; unsigned __int8
0x14003f195  mov     [rsp+68h+arg_8], rax
0x14003f19a  xor     r9d, r9d; unsigned int
0x14003f19d  mov     edx, 58587053h; unsigned int
0x14003f1a2  call    ?Allocate@SC_ENV@@SAPEAX_KKEK@Z; SC_ENV::Allocate(unsigned __int64,ulong,uchar,ulong)
0x14003f1a7  mov     rdi, rax
0x14003f1aa  test    rax, rax
0x14003f1ad  jnz     short loc_14003F1B9
0x14003f1af  mov     ebx, 0C000009Ah
0x14003f1b4  jmp     loc_14003F28F
0x14003f1b9  mov     rax, 5444565053h
0x14003f1c3  lea     rdx, [rsp+68h+var_48]; retstr
0x14003f1c8  mov     r8d, 1; unsigned int
0x14003f1ce  mov     [rdi], rax
0x14003f1d1  lea     rcx, [rsi+10h]; this
0x14003f1d5  call    ?GetHeaderSpaceId@SIO_SLOTS@@QEAA?AU_GUID@@K@Z; SIO_SLOTS::GetHeaderSpaceId(ulong)
0x14003f1da  mov     rcx, [rsi+140h]
0x14003f1e1  xor     edx, edx
0x14003f1e3  movups  xmm0, xmmword ptr [rax]
0x14003f1e6  mov     eax, 1
0x14003f1eb  mov     [rdi+50h], rcx
0x14003f1ef  mov     ecx, [rsi+138h]
0x14003f1f5  mov     [rdi+18h], eax
0x14003f1f8  mov     [rdi+28h], rax
0x14003f1fc  lea     r8d, [rax+5Fh]; Length
0x14003f200  mov     [rdi+58h], ecx
0x14003f203  mov     rax, [rsp+68h+arg_0]
0x14003f208  xor     ecx, ecx; InitialCrc
0x14003f20a  mov     [rdi+30h], rax
0x14003f20e  mov     rax, [rsp+68h+arg_8]
0x14003f213  div     r12
0x14003f216  mov     rdx, rdi; Buffer
0x14003f219  mov     [rdi+1Ch], r8
0x14003f21d  mov     [rdi+5Ch], eax
0x14003f220  movdqu  xmmword ptr [rdi+8], xmm0
0x14003f225  mov     [rdi+38h], r14d
0x14003f229  mov     dword ptr [rdi+3Ch], 400h
0x14003f230  mov     [rdi+40h], r15
0x14003f234  mov     [rdi+48h], ebp
0x14003f237  mov     dword ptr [rdi+4Ch], 2
0x14003f23e  call    cs:__imp_RtlComputeCrc32
0x14003f245  nop     dword ptr [rax+rax+00h]
0x14003f24a  mov     rdx, rdi; void *
0x14003f24d  mov     dword ptr [rsi+24h], 1
0x14003f254  mov     [rdi+24h], eax
0x14003f257  lea     rcx, [rsi+10h]; this
0x14003f25b  mov     rax, [rsp+68h+arg_0]
0x14003f260  mov     [rsi+28h], rax
0x14003f264  mov     [rsi+30h], r14d
0x14003f268  mov     dword ptr [rsi+34h], 400h
0x14003f26f  mov     [rsi+38h], r15
0x14003f273  mov     [rsi+40h], ebp
0x14003f276  mov     dword ptr [rsi+44h], 2
0x14003f27d  mov     [rsi+4Ch], r13d
0x14003f281  call    ?WriteHeader@SIO_SLOTS@@QEAAJPEAX@Z; SIO_SLOTS::WriteHeader(void *)
0x14003f286  mov     ebx, eax
0x14003f288  jmp     short loc_14003F28F
0x14003f28a  mov     ebx, 0C00000BBh
0x14003f28f  mov     r8d, ebx
0x14003f292  mov     edx, 2
0x14003f297  mov     rcx, rsi
0x14003f29a  call    ?LogStatus@SIO_VDT@@IEAAXW4SIO_VDT_OPERATION@@J@Z; SIO_VDT::LogStatus(SIO_VDT_OPERATION,long)
0x14003f29f  test    rdi, rdi
0x14003f2a2  jz      short loc_14003F2B5
0x14003f2a4  xor     edx, edx; Tag
0x14003f2a6  mov     rcx, rdi; P
0x14003f2a9  call    cs:__imp_ExFreePoolWithTag
0x14003f2b0  nop     dword ptr [rax+rax+00h]
0x14003f2b5  mov     eax, ebx
0x14003f2b7  mov     rbx, [rsp+68h+arg_10]
0x14003f2bf  add     rsp, 30h
0x14003f2c3  pop     r15
0x14003f2c5  pop     r14
0x14003f2c7  pop     r13
0x14003f2c9  pop     r12
0x14003f2cb  pop     rdi
0x14003f2cc  pop     rsi
0x14003f2cd  pop     rbp
0x14003f2ce  retn
```
