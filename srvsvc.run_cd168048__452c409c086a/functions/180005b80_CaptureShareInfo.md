# CaptureShareInfo

- ea: `0x180005b80`
- end: `0x180006030`
- name: `CaptureShareInfo`
- size: `1200`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180003f60`
- `0x180029884`

## callees

- `0x180005b80`
- `0x18001e80c`
- `0x1800435f8`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180005d33`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180005d33`
- `ntdll!RtlLengthSecurityDescriptor` at `0x180005c7b`
- `ntdll!RtlLengthSecurityDescriptor` at `0x180005cd1`
- `ntdll!RtlLengthSecurityDescriptor` at `0x180005c7b`
- `ntdll!RtlLengthSecurityDescriptor` at `0x180005cd1`

## pseudocode

```c
char *__fastcall CaptureShareInfo(
        __int64 a1,
        _WORD *a2,
        int a3,
        _WORD *a4,
        _WORD *Src,
        PSECURITY_DESCRIPTOR SecurityDescriptor,
        PSECURITY_DESCRIPTOR a7,
        char a8,
        unsigned int *a9)
{
  _WORD *v9; // r11
  ULONG v12; // ecx
  __int64 v13; // r10
  __int64 v14; // rax
  bool v15; // zf
  __int64 v16; // rax
  __int64 v17; // rax
  unsigned int v18; // r13d
  size_t v19; // rbx
  ULONG v20; // eax
  unsigned int v21; // r14d
  char *v23; // rax
  char *v24; // r13
  const void **v25; // rcx
  char *v26; // rax
  char *v27; // rdi
  ULONG v28; // eax
  __int64 v29; // rax
  __int64 v30; // rdx
  __int64 v31; // rcx
  __int64 v32; // rax
  __int64 v33; // rdx
  __int64 v34; // rcx
  __int64 v35; // rax
  __int64 v36; // rdx
  __int64 v37; // rcx
  __int64 v38; // rax
  __int64 v39; // rdx
  __int64 v40; // rax
  void *v41; // rcx
  ULONG v42; // [rsp+20h] [rbp-58h]
  ULONG v43; // [rsp+24h] [rbp-54h]
  unsigned int v44; // [rsp+28h] [rbp-50h]
  char *v46; // [rsp+80h] [rbp+8h]
  unsigned int Size; // [rsp+88h] [rbp+10h]
  unsigned int v49; // [rsp+98h] [rbp+20h]

  v9 = *(_WORD **)a1;
  v42 = 0;
  v12 = 0;
  v43 = 0;
  v13 = -1;
  if ( v9 )
  {
    v14 = -1;
    do
      v15 = v9[++v14] == 0;
    while ( !v15 );
    Size = 2 * v14 + 2;
  }
  else
  {
    Size = 0;
  }
  if ( a2 )
  {
    v16 = -1;
    do
      v15 = a2[++v16] == 0;
    while ( !v15 );
    v49 = 2 * v16 + 2;
  }
  else
  {
    v49 = 0;
  }
  if ( a4 )
  {
    v17 = -1;
    do
      v15 = a4[++v17] == 0;
    while ( !v15 );
    v18 = 2 * v17 + 2;
  }
  else
  {
    v18 = 0;
  }
  v44 = v18;
  if ( Src )
  {
    do
      v15 = Src[++v13] == 0;
    while ( !v15 );
    v19 = (unsigned int)(2 * v13 + 2);
  }
  else
  {
    v19 = 0;
  }
  if ( SecurityDescriptor )
  {
    v20 = RtlLengthSecurityDescriptor(SecurityDescriptor);
    v12 = 0;
    v42 = v20 + 4;
  }
  if ( a7 )
  {
    v12 = RtlLengthSecurityDescriptor(a7) + 4;
    v43 = v12;
  }
  v21 = 120;
  if ( Size )
  {
    v21 = Size + 120;
    if ( Size >= 0xFFFFFF88 )
      return 0;
  }
  if ( v49 )
  {
    if ( v21 + v49 < v21 )
      return 0;
    v21 += v49;
  }
  if ( (_DWORD)v19 )
  {
    if ( (unsigned int)v19 + v21 < v21 )
      return 0;
    v21 += v19;
  }
  if ( v18 )
  {
    if ( v21 + v18 < v21 )
      return 0;
    v21 += v18;
  }
  if ( v42 )
  {
    if ( v21 + v42 < v21 )
      return 0;
    v21 += v42;
  }
  if ( !v12 )
    goto LABEL_34;
  if ( v12 + v21 < v21 )
    return 0;
  v21 += v12;
LABEL_34:
  v23 = (char *)LocalAlloc(0x40u, v21);
  v24 = v23;
  if ( !v23 )
  {
    *a9 = 0;
    return 0;
  }
  memset_0(v23, 0, v21);
  v25 = (const void **)a1;
  *(_OWORD *)v24 = *(_OWORD *)a1;
  *((_OWORD *)v24 + 1) = *(_OWORD *)(a1 + 16);
  *((_OWORD *)v24 + 2) = *(_OWORD *)(a1 + 32);
  *((_OWORD *)v24 + 3) = *(_OWORD *)(a1 + 48);
  *((_OWORD *)v24 + 4) = *(_OWORD *)(a1 + 64);
  *((_OWORD *)v24 + 5) = *(_OWORD *)(a1 + 80);
  *((_OWORD *)v24 + 6) = *(_OWORD *)(a1 + 96);
  *((_QWORD *)v24 + 14) = *(_QWORD *)(a1 + 112);
  if ( a3 )
    *((_DWORD *)v24 + 2) = a3;
  v26 = v24 + 120;
  v46 = v24 + 120;
  if ( Size )
  {
    *(_QWORD *)v24 = v26;
    memcpy_0(v24 + 120, *v25, Size);
    v19 = (unsigned int)v19;
    v26 = &v24[Size + 120];
    v46 = v26;
  }
  else
  {
    *(_QWORD *)v24 = 0;
  }
  if ( v49 )
  {
    *((_QWORD *)v24 + 7) = v26;
    memcpy_0(v26, a2, v49);
    v26 = &v46[v49];
    v19 = (unsigned int)v19;
    v46 = v26;
  }
  else
  {
    *((_QWORD *)v24 + 7) = 0;
  }
  if ( (_DWORD)v19 )
  {
    *((_QWORD *)v24 + 2) = v26;
    memcpy_0(v26, Src, v19);
    v26 = &v46[v19];
    v46 += v19;
  }
  else
  {
    *((_QWORD *)v24 + 2) = 0;
  }
  if ( v44 )
  {
    *((_QWORD *)v24 + 5) = v26;
    memcpy_0(v26, a4, v44);
    v26 = &v46[v44];
  }
  else
  {
    *((_QWORD *)v24 + 5) = 0;
  }
  if ( SecurityDescriptor )
  {
    v27 = (char *)((unsigned __int64)(v26 + 3) & 0xFFFFFFFFFFFFFFFCuLL);
    *((_DWORD *)v24 + 6) = (((_DWORD)v26 + 3) & 0xFFFFFFFC) - (_DWORD)v24;
    memcpy_0(v27, SecurityDescriptor, v42 - 4LL);
    v26 = &v27[v42 - 4];
  }
  else
  {
    *((_DWORD *)v24 + 6) = 0;
  }
  if ( a7 )
  {
    v41 = (void *)((unsigned __int64)(v26 + 3) & 0xFFFFFFFFFFFFFFFCuLL);
    *((_QWORD *)v24 + 9) = v41;
    memcpy_0(v41, a7, v43 - 4LL);
    v28 = v43 - 4;
  }
  else
  {
    *((_QWORD *)v24 + 9) = 0;
    v28 = 0;
  }
  *((_DWORD *)v24 + 16) = v28;
  if ( a8 )
  {
    v29 = 0;
    v30 = *((_QWORD *)v24 + 2);
    if ( *(_QWORD *)v24 )
      v29 = *(_QWORD *)v24 - (_QWORD)v24;
    v31 = v30 - (_QWORD)v24;
    *(_QWORD *)v24 = v29;
    v32 = 0;
    v15 = v30 == 0;
    v33 = *((_QWORD *)v24 + 5);
    if ( !v15 )
      v32 = v31;
    v34 = v33 - (_QWORD)v24;
    *((_QWORD *)v24 + 2) = v32;
    v35 = 0;
    v15 = v33 == 0;
    v36 = *((_QWORD *)v24 + 7);
    if ( !v15 )
      v35 = v34;
    v37 = v36 - (_QWORD)v24;
    *((_QWORD *)v24 + 5) = v35;
    v38 = 0;
    v15 = v36 == 0;
    v39 = *((_QWORD *)v24 + 9);
    if ( !v15 )
      v38 = v37;
    *((_QWORD *)v24 + 7) = v38;
    v40 = 0;
    if ( v39 )
      v40 = v39 - (_QWORD)v24;
    *((_QWORD *)v24 + 9) = v40;
  }
  *a9 = v21;
  return v24;
}

```

## disassembly

```asm
0x180005b80  mov     [rsp+arg_10], r8d
0x180005b85  mov     [rsp+arg_0], rcx
0x180005b8a  push    rbp
0x180005b8b  push    rsi
0x180005b8c  push    rdi
0x180005b8d  push    r12
0x180005b8f  push    r14
0x180005b91  push    r15
0x180005b93  sub     rsp, 48h
0x180005b97  mov     r11, [rcx]
0x180005b9a  mov     rsi, rdx
0x180005b9d  xor     edx, edx
0x180005b9f  mov     rbp, r9
0x180005ba2  mov     [rsp+78h+var_58], edx
0x180005ba6  mov     ecx, edx
0x180005ba8  mov     [rsp+78h+var_54], edx
0x180005bac  mov     r10, 0FFFFFFFFFFFFFFFFh
0x180005bb3  test    r11, r11
0x180005bb6  jz      loc_18000601D
0x180005bbc  mov     rax, r10
0x180005bbf  nop
0x180005bc0  cmp     [r11+rax*2+2], cx
0x180005bc6  lea     rax, [rax+1]
0x180005bca  jnz     short loc_180005BC0
0x180005bcc  lea     eax, ds:2[rax*2]
0x180005bd3  mov     dword ptr [rsp+78h+Size], eax
0x180005bda  test    rsi, rsi
0x180005bdd  jz      loc_180005F41
0x180005be3  mov     rax, r10
0x180005be6  nop     word ptr [rax+rax+00000000h]
0x180005bf0  cmp     [rsi+rax*2+2], cx
0x180005bf5  lea     rax, [rax+1]
0x180005bf9  jnz     short loc_180005BF0
0x180005bfb  lea     eax, ds:2[rax*2]
0x180005c02  mov     dword ptr [rsp+78h+arg_18], eax
0x180005c09  mov     [rsp+78h+var_40], r13
0x180005c0e  test    rbp, rbp
0x180005c11  jz      loc_180005F86
0x180005c17  mov     rax, r10
0x180005c1a  nop     word ptr [rax+rax+00h]
0x180005c20  cmp     [r9+rax*2+2], cx
0x180005c26  lea     rax, [rax+1]
0x180005c2a  jnz     short loc_180005C20
0x180005c2c  lea     r13d, ds:2[rax*2]
0x180005c34  mov     rdi, [rsp+78h+Src]
0x180005c3c  mov     [rsp+78h+var_50], r13d
0x180005c41  mov     [rsp+78h+var_38], rbx
0x180005c46  test    rdi, rdi
0x180005c49  jz      loc_180006029
0x180005c4f  nop
0x180005c50  cmp     [rdi+r10*2+2], cx
0x180005c56  lea     r10, [r10+1]
0x180005c5a  jnz     short loc_180005C50
0x180005c5c  lea     ebx, ds:2[r10*2]
0x180005c64  mov     r15, [rsp+78h+SecurityDescriptor]
0x180005c6c  mov     dword ptr [rsp+78h+Src], ebx
0x180005c73  test    r15, r15
0x180005c76  jz      short loc_180005C8C
0x180005c78  mov     rcx, r15; SecurityDescriptor
0x180005c7b  call    cs:__imp_RtlLengthSecurityDescriptor
0x180005c81  mov     ecx, [rsp+78h+var_54]
0x180005c85  add     eax, 4
0x180005c88  mov     [rsp+78h+var_58], eax
0x180005c8c  mov     r12, [rsp+78h+arg_30]
0x180005c94  test    r12, r12
0x180005c97  jnz     short loc_180005CCE
0x180005c99  mov     eax, dword ptr [rsp+78h+Size]
0x180005ca0  mov     r14d, 78h ; 'x'
0x180005ca6  test    eax, eax
0x180005ca8  jz      short loc_180005CE0
0x180005caa  lea     r14d, [rax+78h]
0x180005cae  cmp     r14d, 78h ; 'x'
0x180005cb2  jnb     short loc_180005CE0
0x180005cb4  xor     eax, eax
0x180005cb6  mov     r13, [rsp+78h+var_40]
0x180005cbb  mov     rbx, [rsp+78h+var_38]
0x180005cc0  add     rsp, 48h
0x180005cc4  pop     r15
0x180005cc6  pop     r14
0x180005cc8  pop     r12
0x180005cca  pop     rdi
0x180005ccb  pop     rsi
0x180005ccc  pop     rbp
0x180005ccd  retn
0x180005cce  mov     rcx, r12; SecurityDescriptor
0x180005cd1  call    cs:__imp_RtlLengthSecurityDescriptor
0x180005cd7  lea     ecx, [rax+4]
0x180005cda  mov     [rsp+78h+var_54], ecx
0x180005cde  jmp     short loc_180005C99
0x180005ce0  mov     eax, dword ptr [rsp+78h+arg_18]
0x180005ce7  test    eax, eax
0x180005ce9  jnz     loc_180006009
0x180005cef  test    ebx, ebx
0x180005cf1  jz      short loc_180005CFF
0x180005cf3  lea     eax, [rbx+r14]
0x180005cf7  cmp     eax, r14d
0x180005cfa  jb      short loc_180005CB4
0x180005cfc  mov     r14d, eax
0x180005cff  test    r13d, r13d
0x180005d02  jz      short loc_180005D10
0x180005d04  lea     eax, [r14+r13]
0x180005d08  cmp     eax, r14d
0x180005d0b  jb      short loc_180005CB4
0x180005d0d  mov     r14d, eax
0x180005d10  mov     eax, [rsp+78h+var_58]
0x180005d14  test    eax, eax
0x180005d16  jz      short loc_180005D23
0x180005d18  add     eax, r14d
0x180005d1b  cmp     eax, r14d
0x180005d1e  jb      short loc_180005CB4
0x180005d20  mov     r14d, eax
0x180005d23  test    ecx, ecx
0x180005d25  jnz     loc_180005F71
0x180005d2b  mov     edx, r14d; uBytes
0x180005d2e  mov     ecx, 40h ; '@'; uFlags
0x180005d33  call    cs:__imp_LocalAlloc
0x180005d39  mov     r13, rax
0x180005d3c  test    rax, rax
0x180005d3f  jz      loc_180005FF6
0x180005d45  mov     r8d, r14d; Size
0x180005d48  xor     edx, edx; Val
0x180005d4a  mov     rcx, rax; void *
0x180005d4d  call    memset_0
0x180005d52  mov     rcx, [rsp+78h+arg_0]
0x180005d5a  mov     eax, [rsp+78h+arg_10]
0x180005d61  movups  xmm0, xmmword ptr [rcx]
0x180005d64  movups  xmmword ptr [r13+0], xmm0
0x180005d69  movups  xmm1, xmmword ptr [rcx+10h]
0x180005d6d  movups  xmmword ptr [r13+10h], xmm1
0x180005d72  movups  xmm0, xmmword ptr [rcx+20h]
0x180005d76  movups  xmmword ptr [r13+20h], xmm0
0x180005d7b  movups  xmm1, xmmword ptr [rcx+30h]
0x180005d7f  movups  xmmword ptr [r13+30h], xmm1
0x180005d84  movups  xmm0, xmmword ptr [rcx+40h]
0x180005d88  movups  xmmword ptr [r13+40h], xmm0
0x180005d8d  movups  xmm1, xmmword ptr [rcx+50h]
0x180005d91  movups  xmmword ptr [r13+50h], xmm1
0x180005d96  movups  xmm0, xmmword ptr [rcx+60h]
0x180005d9a  movups  xmmword ptr [r13+60h], xmm0
0x180005d9f  movsd   xmm1, qword ptr [rcx+70h]
0x180005da4  movsd   qword ptr [r13+70h], xmm1
0x180005daa  test    eax, eax
0x180005dac  jz      short loc_180005DB2
0x180005dae  mov     [r13+8], eax
0x180005db2  mov     edx, dword ptr [rsp+78h+Size]
0x180005db9  lea     rax, [r13+78h]
0x180005dbd  mov     [rsp+78h+arg_0], rax
0x180005dc5  test    edx, edx
0x180005dc7  jz      loc_180005FCF
0x180005dcd  mov     [r13+0], rax
0x180005dd1  mov     ebx, edx
0x180005dd3  mov     r8d, edx; Size
0x180005dd6  mov     rdx, [rcx]; Src
0x180005dd9  mov     rcx, rax; void *
0x180005ddc  call    memcpy_0
0x180005de1  lea     rax, [rbx+78h]
0x180005de5  mov     ebx, dword ptr [rsp+78h+Src]
0x180005dec  add     rax, r13
0x180005def  mov     [rsp+78h+arg_0], rax
0x180005df7  mov     ecx, dword ptr [rsp+78h+arg_18]
0x180005dfe  test    ecx, ecx
0x180005e00  jnz     loc_180005F8E
0x180005e06  mov     qword ptr [r13+38h], 0
0x180005e0e  test    ebx, ebx
0x180005e10  jz      loc_180005FC2
0x180005e16  mov     r8, rbx; Size
0x180005e19  mov     [r13+10h], rax
0x180005e1d  mov     rdx, rdi; Src
0x180005e20  mov     rcx, rax; void *
0x180005e23  call    memcpy_0
0x180005e28  mov     rax, [rsp+78h+arg_0]
0x180005e30  add     rax, rbx
0x180005e33  mov     [rsp+78h+arg_0], rax
0x180005e3b  mov     ecx, [rsp+78h+var_50]
0x180005e3f  test    ecx, ecx
0x180005e41  jz      loc_180005FDC
0x180005e47  mov     ebx, ecx
0x180005e49  mov     [r13+28h], rax
0x180005e4d  mov     r8d, ecx; Size
0x180005e50  mov     rdx, rbp; Src
0x180005e53  mov     rcx, rax; void *
0x180005e56  call    memcpy_0
0x180005e5b  mov     rax, [rsp+78h+arg_0]
0x180005e63  add     rax, rbx
0x180005e66  mov     rcx, r13
0x180005e69  test    r15, r15
0x180005e6c  jz      loc_180005FE9
0x180005e72  mov     ebx, [rsp+78h+var_58]
0x180005e76  lea     rdi, [rax+3]
0x180005e7a  and     rdi, 0FFFFFFFFFFFFFFFCh
0x180005e7e  mov     rdx, r15; Src
0x180005e81  mov     eax, edi
0x180005e83  sub     eax, ecx
0x180005e85  mov     rcx, rdi; void *
0x180005e88  lea     r8, [rbx-4]; Size
0x180005e8c  mov     [r13+18h], eax
0x180005e90  call    memcpy_0
0x180005e95  lea     rax, [rbx-4]
0x180005e99  add     rax, rdi
0x180005e9c  test    r12, r12
0x180005e9f  jnz     loc_180005F4D
0x180005ea5  mov     [r13+48h], r12
0x180005ea9  xor     eax, eax
0x180005eab  cmp     [rsp+78h+arg_38], 0
0x180005eb3  mov     rcx, r13
0x180005eb6  mov     [rcx+40h], eax
0x180005eb9  jz      short loc_180005F2E
0x180005ebb  mov     rdx, [r13+0]
0x180005ebf  xor     eax, eax
0x180005ec1  mov     rcx, rdx
0x180005ec4  sub     rcx, r13
0x180005ec7  test    rdx, rdx
0x180005eca  mov     rdx, [r13+10h]
0x180005ece  cmovnz  rax, rcx
0x180005ed2  mov     rcx, rdx
0x180005ed5  sub     rcx, r13
0x180005ed8  mov     [r13+0], rax
0x180005edc  xor     eax, eax
0x180005ede  test    rdx, rdx
0x180005ee1  mov     rdx, [r13+28h]
0x180005ee5  cmovnz  rax, rcx
0x180005ee9  mov     rcx, rdx
0x180005eec  sub     rcx, r13
0x180005eef  mov     [r13+10h], rax
0x180005ef3  xor     eax, eax
0x180005ef5  test    rdx, rdx
0x180005ef8  mov     rdx, [r13+38h]
0x180005efc  cmovnz  rax, rcx
0x180005f00  mov     rcx, rdx
0x180005f03  sub     rcx, r13
0x180005f06  mov     [r13+28h], rax
0x180005f0a  xor     eax, eax
0x180005f0c  test    rdx, rdx
0x180005f0f  mov     rdx, [r13+48h]
0x180005f13  cmovnz  rax, rcx
0x180005f17  mov     rcx, rdx
0x180005f1a  mov     [r13+38h], rax
0x180005f1e  sub     rcx, r13
0x180005f21  xor     eax, eax
0x180005f23  test    rdx, rdx
0x180005f26  cmovnz  rax, rcx
0x180005f2a  mov     [r13+48h], rax
0x180005f2e  mov     rax, [rsp+78h+arg_40]
0x180005f36  mov     [rax], r14d
0x180005f39  mov     rax, r13
0x180005f3c  jmp     loc_180005CB6
0x180005f41  mov     dword ptr [rsp+78h+arg_18], edx
0x180005f48  jmp     loc_180005C09
0x180005f4d  mov     ebx, [rsp+78h+var_54]
0x180005f51  lea     rcx, [rax+3]
0x180005f55  and     rcx, 0FFFFFFFFFFFFFFFCh; void *
0x180005f59  mov     rdx, r12; Src
0x180005f5c  mov     [r13+48h], rcx
0x180005f60  lea     r8, [rbx-4]; Size
0x180005f64  call    memcpy_0
0x180005f69  lea     eax, [rbx-4]
0x180005f6c  jmp     loc_180005EAB
0x180005f71  lea     eax, [rcx+r14]
0x180005f75  cmp     eax, r14d
0x180005f78  jb      loc_180005CB4
0x180005f7e  mov     r14d, eax
0x180005f81  jmp     loc_180005D2B
0x180005f86  mov     r13d, edx
0x180005f89  jmp     loc_180005C34
0x180005f8e  mov     rbx, rcx
0x180005f91  mov     [r13+38h], rax
0x180005f95  mov     r8, rcx; Size
0x180005f98  mov     rdx, rsi; Src
0x180005f9b  mov     rcx, rax; void *
0x180005f9e  call    memcpy_0
0x180005fa3  mov     rax, [rsp+78h+arg_0]
0x180005fab  add     rax, rbx
0x180005fae  mov     ebx, dword ptr [rsp+78h+Src]
0x180005fb5  mov     [rsp+78h+arg_0], rax
0x180005fbd  jmp     loc_180005E0E
0x180005fc2  mov     qword ptr [r13+10h], 0
0x180005fca  jmp     loc_180005E3B
0x180005fcf  mov     qword ptr [r13+0], 0
0x180005fd7  jmp     loc_180005DF7
0x180005fdc  mov     qword ptr [r13+28h], 0
0x180005fe4  jmp     loc_180005E66
0x180005fe9  mov     dword ptr [r13+18h], 0
0x180005ff1  jmp     loc_180005E9C
0x180005ff6  mov     rax, [rsp+78h+arg_40]
0x180005ffe  mov     dword ptr [rax], 0
0x180006004  jmp     loc_180005CB4
0x180006009  add     eax, r14d
0x18000600c  cmp     eax, r14d
0x18000600f  jb      loc_180005CB4
0x180006015  mov     r14d, eax
0x180006018  jmp     loc_180005CEF
0x18000601d  mov     dword ptr [rsp+78h+Size], edx
0x180006024  jmp     loc_180005BDA
0x180006029  mov     ebx, edx
0x18000602b  jmp     loc_180005C64
```
