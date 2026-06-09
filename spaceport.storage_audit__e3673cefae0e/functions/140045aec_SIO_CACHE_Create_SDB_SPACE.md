# SIO_CACHE::Create(SDB_SPACE *)

- ea: `0x140045aec`
- end: `0x140045d79`
- name: `?Create@SIO_CACHE@@IEAAJPEAVSDB_SPACE@@@Z`
- size: `653`
- prototype: `__int64 __fastcall(SIO_CACHE *__hidden this, struct SDB_SPACE *)`
- caller_count: `1`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x140046a94`

## callees

- `0x140026130`
- `0x1400268c0`
- `0x140026db0`
- `0x140045aec`
- `0x140051c38`
- `0x140052790`
- `0x140054490`
- `0x140068000`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x140045d59`
- `ntoskrnl!ExFreePoolWithTag` at `0x140045d59`
- `ntoskrnl!RtlComputeCrc32` at `0x140045cf3`
- `ntoskrnl!RtlComputeCrc32` at `0x140045cf3`

## pseudocode

```c
__int64 __fastcall SIO_CACHE::Create(SIO_CACHE *this, struct SDB_SPACE *a2)
{
  char *v4; // rdi
  __int64 v5; // rax
  __int64 v6; // rdx
  __int64 v7; // rcx
  __int64 v8; // rcx
  SP_RESILIENCY_INFO *v9; // rdx
  unsigned int v10; // eax
  __int64 v11; // r11
  unsigned int v12; // r9d
  __int64 v13; // rdx
  unsigned int v14; // r8d
  unsigned int v15; // r14d
  __int64 v16; // r12
  unsigned __int64 v17; // r15
  unsigned int v18; // ebp
  unsigned __int64 v19; // r10
  int v20; // eax
  unsigned int v21; // r13d
  unsigned __int64 v22; // r8
  unsigned __int64 v23; // rcx
  unsigned __int64 v24; // rcx
  unsigned int v25; // ebx
  __int128 v26; // xmm0
  ULONG v27; // eax
  struct _GUID v29; // [rsp+20h] [rbp-58h] BYREF

  v4 = 0;
  v5 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 1) + 80LL))(*((_QWORD *)this + 1));
  LOBYTE(v6) = 11;
  SIO_SPACE::GetChild(v5, v6);
  v7 = *((_QWORD *)a2 + 32);
  if ( v7 )
  {
    do
    {
      v8 = *(_QWORD *)(v7 + 8LL * (*(_WORD *)(v7 + 30) & 1) + 32);
      v9 = (SP_RESILIENCY_INFO *)(v8 + 104);
      v7 = *(_QWORD *)(v8 + 184);
    }
    while ( v7 );
  }
  else
  {
    v9 = (struct SDB_SPACE *)((char *)a2 + 128);
  }
  v10 = SP_RESILIENCY_INFO::NumberOfDataColumns(v9);
  v12 = *((_DWORD *)this + 26);
  v14 = *(_DWORD *)(v13 + 20) * v10;
  v15 = v12;
  if ( v12 < 0x1000 )
    v15 = 4096;
  *((_DWORD *)this + 118) = v14;
  v16 = 2 * v15;
  v17 = v16 + (v15 << 10);
  if ( v17 >= *(_QWORD *)(v11 + 112) )
    goto LABEL_15;
  *((_DWORD *)this + 120) = v14 / v12;
  v18 = (((v14 / v12 + 7) >> 3) + 23) & 0xFFFFFFF8;
  if ( (unsigned __int64)v18 + 56 > v15 )
    goto LABEL_15;
  v19 = v14;
  v20 = (*(_QWORD *)(v11 + 112) - v17) / v14;
  *((_DWORD *)this + 119) = v20;
  v21 = v15 + v12 + v20 * v18 - 1 - (v15 + v12 + v20 * v18 - 1) % v15;
  v22 = v17 + 2 * v21 + v14 - 1 - (v17 + 2 * v21 + v14 - 1) % v14;
  *((_QWORD *)this + 58) = v22;
  v23 = *(_QWORD *)(v11 + 112);
  if ( v22 >= v23 )
    goto LABEL_15;
  v24 = v23 - v22 - (v23 - v22) % v19;
  if ( v24 && v24 / v19 <= 0xFFFFFFFF )
  {
    *((_DWORD *)this + 119) = v24 / v19;
    v4 = (char *)SC_ENV::Allocate(v12, 0x58587053u, 0, 0);
    if ( v4 )
    {
      *(_QWORD *)v4 = 0x45484341435053LL;
      v26 = (__int128)*SIO_SLOTS::GetHeaderSpaceId((SIO_CACHE *)((char *)this + 16), &v29, 1u);
      *((_QWORD *)v4 + 6) = v16;
      *((_DWORD *)v4 + 6) = 1;
      *((_QWORD *)v4 + 5) = 1;
      *(_OWORD *)(v4 + 8) = v26;
      *((_DWORD *)v4 + 14) = v15;
      *((_QWORD *)v4 + 10) = *((_QWORD *)this + 58);
      *((_DWORD *)v4 + 22) = *((_DWORD *)this + 118);
      *((_DWORD *)v4 + 23) = *((_DWORD *)this + 119);
      *(_QWORD *)(v4 + 28) = 96;
      *((_DWORD *)v4 + 15) = 1024;
      *((_QWORD *)v4 + 8) = v17;
      *((_DWORD *)v4 + 18) = v21;
      *((_DWORD *)v4 + 19) = 2;
      v27 = RtlComputeCrc32(0, (PUCHAR)v4, 0x60u);
      *((_DWORD *)this + 9) = 1;
      *((_DWORD *)v4 + 9) = v27;
      *((_QWORD *)this + 5) = v16;
      *((_DWORD *)this + 12) = v15;
      *((_DWORD *)this + 13) = 1024;
      *((_QWORD *)this + 7) = v17;
      *((_DWORD *)this + 16) = v21;
      *((_DWORD *)this + 17) = 2;
      *((_DWORD *)this + 19) = v18;
      v25 = SIO_SLOTS::WriteHeader((SIO_CACHE *)((char *)this + 16), v4);
    }
    else
    {
      v25 = -1073741670;
    }
  }
  else
  {
LABEL_15:
    v25 = -1073741637;
  }
  SIO_CACHE::LogStatus(this, 2);
  if ( v4 )
    ExFreePoolWithTag(v4, 0);
  return v25;
}

```

## disassembly

```asm
0x140045aec  push    rbx
0x140045aee  push    rbp
0x140045aef  push    rsi
0x140045af0  push    rdi
0x140045af1  push    r12
0x140045af3  push    r13
0x140045af5  push    r14
0x140045af7  push    r15
0x140045af9  sub     rsp, 38h
0x140045afd  mov     rsi, rcx
0x140045b00  mov     rbx, rdx
0x140045b03  mov     rcx, [rcx+8]
0x140045b07  xor     edi, edi
0x140045b09  mov     rax, [rcx]
0x140045b0c  mov     rax, [rax+50h]
0x140045b10  call    _guard_dispatch_icall
0x140045b15  mov     dl, 0Bh
0x140045b17  mov     rcx, rax
0x140045b1a  call    ?GetChild@SIO_SPACE@@QEAAPEAV1@W4_SC_SPACE_USAGE@@@Z; SIO_SPACE::GetChild(_SC_SPACE_USAGE)
0x140045b1f  mov     rcx, [rbx+100h]
0x140045b26  mov     r11, rax
0x140045b29  test    rcx, rcx
0x140045b2c  jz      short loc_140045B4C
0x140045b2e  movzx   eax, word ptr [rcx+1Eh]
0x140045b32  and     eax, 1
0x140045b35  mov     rcx, [rcx+rax*8+20h]
0x140045b3a  lea     rdx, [rcx+68h]
0x140045b3e  mov     rcx, [rcx+0B8h]
0x140045b45  test    rcx, rcx
0x140045b48  jnz     short loc_140045B2E
0x140045b4a  jmp     short loc_140045B53
0x140045b4c  lea     rdx, [rbx+80h]
0x140045b53  mov     rcx, rdx; this
0x140045b56  call    ?NumberOfDataColumns@SP_RESILIENCY_INFO@@QEAAKXZ; SP_RESILIENCY_INFO::NumberOfDataColumns(void)
0x140045b5b  mov     r9d, [rsi+68h]
0x140045b5f  mov     r8d, eax
0x140045b62  imul    r8d, [rdx+14h]
0x140045b67  mov     eax, 1000h
0x140045b6c  cmp     r9d, eax
0x140045b6f  mov     r14d, r9d
0x140045b72  cmovb   r14d, eax
0x140045b76  mov     r15d, r14d
0x140045b79  shl     r15d, 0Ah
0x140045b7d  mov     [rsi+1D8h], r8d
0x140045b84  lea     r12d, [r14+r14]
0x140045b88  add     r15, r12
0x140045b8b  cmp     r15, [r11+70h]
0x140045b8f  jnb     loc_140045D3A
0x140045b95  mov     eax, r8d
0x140045b98  xor     edx, edx
0x140045b9a  div     r9d
0x140045b9d  mov     [rsi+1E0h], eax
0x140045ba3  add     eax, 7
0x140045ba6  shr     eax, 3
0x140045ba9  add     eax, 17h
0x140045bac  and     eax, 0FFFFFFF8h
0x140045baf  mov     ebp, eax
0x140045bb1  lea     rcx, [rax+38h]
0x140045bb5  mov     eax, r14d
0x140045bb8  cmp     rcx, rax
0x140045bbb  ja      loc_140045D3A
0x140045bc1  mov     rax, [r11+70h]
0x140045bc5  xor     edx, edx
0x140045bc7  sub     rax, r15
0x140045bca  mov     r10d, r8d
0x140045bcd  div     r10
0x140045bd0  xor     edx, edx
0x140045bd2  mov     r13d, ebp
0x140045bd5  imul    r13d, eax
0x140045bd9  dec     r8d
0x140045bdc  mov     [rsi+1DCh], eax
0x140045be2  dec     r13d
0x140045be5  add     r13d, r9d
0x140045be8  add     r13d, r14d
0x140045beb  mov     eax, r13d
0x140045bee  div     r14d
0x140045bf1  sub     r13d, edx
0x140045bf4  xor     edx, edx
0x140045bf6  lea     eax, ds:0[r13*2]
0x140045bfe  add     rax, r15
0x140045c01  add     r8, rax
0x140045c04  mov     rax, r8
0x140045c07  div     r10
0x140045c0a  sub     r8, rdx
0x140045c0d  mov     [rsi+1D0h], r8
0x140045c14  mov     rcx, [r11+70h]
0x140045c18  cmp     r8, rcx
0x140045c1b  jnb     loc_140045D3A
0x140045c21  sub     rcx, r8
0x140045c24  xor     edx, edx
0x140045c26  mov     rax, rcx
0x140045c29  div     r10
0x140045c2c  sub     rcx, rdx
0x140045c2f  jz      loc_140045D3A
0x140045c35  xor     edx, edx
0x140045c37  mov     rax, rcx
0x140045c3a  div     r10
0x140045c3d  mov     ecx, 0FFFFFFFFh
0x140045c42  cmp     rax, rcx
0x140045c45  ja      loc_140045D3A
0x140045c4b  mov     ecx, r9d; unsigned __int64
0x140045c4e  mov     [rsi+1DCh], eax
0x140045c54  xor     r9d, r9d; unsigned int
0x140045c57  xor     r8d, r8d; unsigned __int8
0x140045c5a  mov     edx, 58587053h; unsigned int
0x140045c5f  call    ?Allocate@SC_ENV@@SAPEAX_KKEK@Z; SC_ENV::Allocate(unsigned __int64,ulong,uchar,ulong)
0x140045c64  mov     rdi, rax
0x140045c67  test    rax, rax
0x140045c6a  jnz     short loc_140045C76
0x140045c6c  mov     ebx, 0C000009Ah
0x140045c71  jmp     loc_140045D3F
0x140045c76  mov     rax, 45484341435053h
0x140045c80  lea     rdx, [rsp+78h+var_58]; retstr
0x140045c85  mov     r8d, 1; unsigned int
0x140045c8b  mov     [rdi], rax
0x140045c8e  lea     rcx, [rsi+10h]; this
0x140045c92  call    ?GetHeaderSpaceId@SIO_SLOTS@@QEAA?AU_GUID@@K@Z; SIO_SLOTS::GetHeaderSpaceId(ulong)
0x140045c97  mov     rdx, rdi; Buffer
0x140045c9a  xor     ecx, ecx; InitialCrc
0x140045c9c  movups  xmm0, xmmword ptr [rax]
0x140045c9f  mov     eax, 1
0x140045ca4  mov     [rdi+30h], r12
0x140045ca8  mov     [rdi+18h], eax
0x140045cab  mov     [rdi+28h], rax
0x140045caf  movdqu  xmmword ptr [rdi+8], xmm0
0x140045cb4  lea     r8d, [rax+5Fh]; Length
0x140045cb8  mov     [rdi+38h], r14d
0x140045cbc  mov     rax, [rsi+1D0h]
0x140045cc3  mov     [rdi+50h], rax
0x140045cc7  mov     eax, [rsi+1D8h]
0x140045ccd  mov     [rdi+58h], eax
0x140045cd0  mov     eax, [rsi+1DCh]
0x140045cd6  mov     [rdi+5Ch], eax
0x140045cd9  mov     [rdi+1Ch], r8
0x140045cdd  mov     dword ptr [rdi+3Ch], 400h
0x140045ce4  mov     [rdi+40h], r15
0x140045ce8  mov     [rdi+48h], r13d
0x140045cec  mov     dword ptr [rdi+4Ch], 2
0x140045cf3  call    cs:__imp_RtlComputeCrc32
0x140045cfa  nop     dword ptr [rax+rax+00h]
0x140045cff  mov     rdx, rdi; void *
0x140045d02  mov     dword ptr [rsi+24h], 1
0x140045d09  lea     rcx, [rsi+10h]; this
0x140045d0d  mov     [rdi+24h], eax
0x140045d10  mov     [rsi+28h], r12
0x140045d14  mov     [rsi+30h], r14d
0x140045d18  mov     dword ptr [rsi+34h], 400h
0x140045d1f  mov     [rsi+38h], r15
0x140045d23  mov     [rsi+40h], r13d
0x140045d27  mov     dword ptr [rsi+44h], 2
0x140045d2e  mov     [rsi+4Ch], ebp
0x140045d31  call    ?WriteHeader@SIO_SLOTS@@QEAAJPEAX@Z; SIO_SLOTS::WriteHeader(void *)
0x140045d36  mov     ebx, eax
0x140045d38  jmp     short loc_140045D3F
0x140045d3a  mov     ebx, 0C00000BBh
0x140045d3f  mov     r8d, ebx
0x140045d42  mov     edx, 2
0x140045d47  mov     rcx, rsi
0x140045d4a  call    ?LogStatus@SIO_CACHE@@IEAAXW4SIO_CACHE_OPERATION@@J@Z; SIO_CACHE::LogStatus(SIO_CACHE_OPERATION,long)
0x140045d4f  test    rdi, rdi
0x140045d52  jz      short loc_140045D65
0x140045d54  xor     edx, edx; Tag
0x140045d56  mov     rcx, rdi; P
0x140045d59  call    cs:__imp_ExFreePoolWithTag
0x140045d60  nop     dword ptr [rax+rax+00h]
0x140045d65  mov     eax, ebx
0x140045d67  add     rsp, 38h
0x140045d6b  pop     r15
0x140045d6d  pop     r14
0x140045d6f  pop     r13
0x140045d71  pop     r12
0x140045d73  pop     rdi
0x140045d74  pop     rsi
0x140045d75  pop     rbp
0x140045d76  pop     rbx
0x140045d77  retn
```
