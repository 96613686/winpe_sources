# ORCreateKey

- ea: `0x1402469f0`
- end: `0x140246fe2`
- name: `ORCreateKey`
- size: `1522`
- prototype: `__int64 __fastcall(int, int, int, int, PSECURITY_DESCRIPTOR pSecurityDescriptor, __int64, __int64)`
- caller_count: `1`
- callee_count: `16`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x140081fa4`

## callees

- `0x140133eba`
- `0x140134048`
- `0x1401365b9`
- `0x1402468c0`
- `0x1402469f0`
- `0x140247070`
- `0x1402472a0`
- `0x14024763c`
- `0x140247998`
- `0x140249aa0`
- `0x140249edc`
- `0x140249ef8`
- `0x140249f48`
- `0x14024a000`
- `0x14024a920`
- `0x14024ac0c`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!DestroyPrivateObjectSecurity` at `0x140246b40`
- `api-ms-win-security-base-l1-1-0!DestroyPrivateObjectSecurity` at `0x140246b40`
- `api-ms-win-security-base-l1-1-0!IsValidSecurityDescriptor` at `0x140246dbf`
- `api-ms-win-security-base-l1-1-0!IsValidSecurityDescriptor` at `0x140246dbf`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x140246b58`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x140246b58`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x140246ab4`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x140246ab4`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x140246ce6`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x140246ce6`

## pseudocode

```c
__int64 __fastcall ORCreateKey(
        __int64 a1,
        _WORD *a2,
        void *a3,
        int a4,
        PSECURITY_DESCRIPTOR pSecurityDescriptor,
        _QWORD *a6,
        _DWORD *a7)
{
  _QWORD *v7; // r12
  int v10; // r15d
  __int64 v11; // r13
  int v12; // r14d
  unsigned int v13; // ebx
  unsigned __int64 v14; // rcx
  unsigned __int16 v15; // cx
  __int64 v16; // rdi
  unsigned __int64 v18; // rdx
  __int64 v19; // rcx
  _QWORD *v20; // r13
  __int64 v21; // rax
  _WORD *v22; // rax
  _WORD *v23; // rsi
  unsigned __int64 v24; // rbx
  __int16 v25; // r14
  unsigned __int16 v26; // ax
  __int64 v27; // r10
  __int64 v28; // rdi
  __int16 v29; // r14
  __int64 v30; // rsi
  PSECURITY_DESCRIPTOR v31; // rbx
  __int64 v32; // rax
  __int64 v33; // rcx
  _WORD *v34; // rax
  __int64 v35; // rcx
  unsigned int v36; // ebx
  void *v37; // rax
  _OWORD *v38; // rax
  _OWORD *v39; // r12
  __int128 v40; // xmm1
  __int64 v41; // r8
  __int128 v42; // xmm0
  __int128 v43; // xmm1
  __int128 v44; // xmm0
  __int64 v45; // rdx
  __int64 *v46; // rax
  __int64 v47; // [rsp+20h] [rbp-B1h]
  _OWORD *v48; // [rsp+28h] [rbp-A9h]
  int v49; // [rsp+30h] [rbp-A1h] BYREF
  struct _FILETIME SystemTimeAsFileTime; // [rsp+38h] [rbp-99h] BYREF
  __int64 v51; // [rsp+40h] [rbp-91h] BYREF
  PSECURITY_DESCRIPTOR ObjectDescriptor[2]; // [rsp+48h] [rbp-89h] BYREF
  PSECURITY_DESCRIPTOR v53; // [rsp+58h] [rbp-79h]
  __int128 v54; // [rsp+60h] [rbp-71h] BYREF
  __int64 v55; // [rsp+70h] [rbp-61h] BYREF
  __int128 v56; // [rsp+78h] [rbp-59h] BYREF
  __int128 v57; // [rsp+90h] [rbp-41h] BYREF
  __int128 v58; // [rsp+A0h] [rbp-31h]
  __int128 v59; // [rsp+B0h] [rbp-21h]
  _BYTE v60[28]; // [rsp+C0h] [rbp-11h]
  unsigned __int16 v61; // [rsp+120h] [rbp+4Fh] BYREF
  void *Src; // [rsp+130h] [rbp+5Fh]

  Src = a3;
  v7 = a6;
  v51 = 0;
  v55 = 0;
  v49 = 0;
  *a6 = 0;
  v47 = 0;
  v10 = 0;
  v48 = 0;
  v54 = 0;
  SystemTimeAsFileTime = 0;
  v56 = 0;
  v53 = 0;
  ObjectDescriptor[0] = 0;
  v61 = 0;
  if ( *(_WORD *)(a1 + 28) != 29806 || (v11 = *(_QWORD *)(a1 + 16), v47 = v11, *(_DWORD *)v11 != -1092567328) )
  {
    v16 = v47;
    v13 = 6;
    v14 = 0;
    goto LABEL_16;
  }
  if ( !a2 || !*a2 )
  {
    v13 = 87;
    v14 = 0;
    goto LABEL_15;
  }
  v12 = a4 & 2;
  if ( a4 != v12 )
  {
    v13 = 87;
    v14 = 0;
LABEL_15:
    v16 = v11;
    goto LABEL_16;
  }
  EnterCriticalSection((LPCRITICAL_SECTION)(v11 + 136));
  v10 = 1;
  v13 = ORInitUnicodeStringEx(&v56, a2);
  if ( v13 )
  {
LABEL_14:
    v14 = 0;
    goto LABEL_15;
  }
  v15 = v56;
  if ( (_WORD)v56 )
  {
    do
    {
      if ( *(_WORD *)(*((_QWORD *)&v56 + 1) + 2 * ((unsigned __int64)v15 >> 1) - 2) != 92 )
        break;
      v15 -= 2;
    }
    while ( v15 );
    LOWORD(v56) = v15;
  }
  if ( *(_WORD *)(a1 + 30) )
  {
    v13 = 1018;
    goto LABEL_14;
  }
  if ( !v15 )
  {
    v13 = 87;
    goto LABEL_14;
  }
  v13 = ORParseSubKey(&v56, a1, &v49, &v51);
  if ( v13 )
  {
LABEL_30:
    v14 = 0;
    goto LABEL_15;
  }
  if ( v49 == 2 )
  {
    if ( v12 )
    {
      if ( ((unsigned __int8)(v13 + 16) & *(_BYTE *)(*(_QWORD *)(v51 + 40) + 2LL)) == 0 )
      {
LABEL_29:
        v13 = 87;
        goto LABEL_30;
      }
      v7 = a6;
    }
    if ( v51 != *(_QWORD *)(v11 + 56) )
    {
      v13 = ORReferenceTreeNode(v51, 0);
      if ( !v13 )
      {
        if ( a7 )
          *a7 = 2;
        *v7 = v19;
        v13 = 0;
      }
      v14 = v18;
      goto LABEL_15;
    }
    goto LABEL_29;
  }
  v20 = (_QWORD *)v51;
  v21 = *(_QWORD *)(v51 + 40);
  if ( (*(_BYTE *)(v21 + 2) & 0x10) != 0 || (*(_BYTE *)(v21 + 13) & 3) == 1 )
  {
    v13 = 5;
    v14 = 0;
LABEL_40:
    v16 = v47;
    goto LABEL_16;
  }
  v14 = 0;
  if ( *(_WORD *)(v51 + 32) == 510 )
  {
    v13 = 87;
    goto LABEL_40;
  }
  v22 = a2;
  do
    ++v22;
  while ( *v22 );
  do
  {
    if ( v22 <= a2 )
      break;
    --v22;
  }
  while ( *v22 == 92 );
  while ( *v22 != 92 && v22 != a2 )
  {
    v14 += 2LL;
    --v22;
  }
  v23 = v22 + 1;
  v24 = v14 + 2;
  if ( *v22 != 92 )
    v23 = v22;
  if ( v23 != a2 )
    v24 = v14;
  if ( v24 > 0x200 )
  {
    v13 = 87;
LABEL_58:
    v14 = (unsigned __int64)v48;
    goto LABEL_40;
  }
  memset_0(&v57, 0, 0x50u);
  LOWORD(v57) = 27502;
  if ( v12 )
    v25 = 16;
  else
    v25 = 0;
  GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
  *(struct _FILETIME *)((char *)&v57 + 4) = SystemTimeAsFileTime;
  LODWORD(v58) = -1;
  HIDWORD(v58) = -1;
  *(_QWORD *)&v59 = 0xFFFFFFFFLL;
  *((_QWORD *)&v59 + 1) = -1;
  *(_DWORD *)v60 = -1;
  v49 = 0;
  *(_WORD *)&v60[26] = 0;
  BYTE12(v57) = 0;
  *(_QWORD *)((char *)&v58 + 4) = 0;
  *(_WORD *)&v60[24] = 0;
  *(_OWORD *)&v60[4] = 0u;
  *((_QWORD *)&v54 + 1) = v23;
  if ( (int)RtlULongPtrToUShort(v24, &v54) < 0 )
  {
    v13 = 534;
    goto LABEL_58;
  }
  WORD1(v54) = v54;
  v51 = *(_QWORD *)(v47 + 16);
  v26 = ORGetCompressedLength(v51, &v54);
  v28 = v26;
  *(_WORD *)&v60[24] = v26;
  if ( v26 >= v24 )
    v29 = v25 & 0xFFDF;
  else
    v29 = v25 | 0x20;
  WORD1(v57) = v29;
  v30 = ORAllocNode(v27, v20);
  if ( !v30 )
  {
    v13 = 8;
    v14 = 0;
    goto LABEL_40;
  }
  v31 = pSecurityDescriptor;
  if ( pSecurityDescriptor )
  {
    if ( !IsValidSecurityDescriptor(pSecurityDescriptor) )
    {
      v13 = 1338;
LABEL_96:
      ORFree(*(_QWORD *)(v30 + 120));
      ORFree(v30);
      goto LABEL_58;
    }
    v13 = ORMakeSDRelative(v31);
    if ( v13 )
      goto LABEL_96;
  }
  v13 = OrAssignSecurity(*(_QWORD *)(v20[12] + 16LL) + 20LL, v53, ObjectDescriptor);
  if ( v13 )
    goto LABEL_96;
  v13 = ORProcessSecurityDescriptor(v47, ObjectDescriptor[0], &v55);
  if ( v13 )
    goto LABEL_96;
  v32 = v55;
  *(_QWORD *)(v30 + 96) = v55;
  v33 = *(_QWORD *)(v32 + 16);
  v34 = Src;
  ++*(_DWORD *)(v33 + 12);
  if ( v34 )
  {
    v35 = -1;
    do
      ++v35;
    while ( v34[v35] );
    if ( (int)RtlULongPtrToUShort(2 * v35, &v61) < 0 )
    {
      v13 = 534;
      goto LABEL_96;
    }
    *(_WORD *)&v60[26] = v61;
    v49 = v61;
    if ( v61 )
    {
      v36 = v61;
      v37 = o__aligned_malloc_0(v61, 0x10u);
      *(_QWORD *)(v30 + 120) = v37;
      if ( !v37 )
      {
LABEL_83:
        v13 = 8;
        goto LABEL_96;
      }
      memcpy_0(v37, Src, v36);
    }
  }
  v38 = o__aligned_malloc_0(v28 + 76, 0x10u);
  v48 = v38;
  v39 = v38;
  if ( !v38 )
    goto LABEL_83;
  v40 = v58;
  v41 = v51;
  *v38 = v57;
  v42 = v59;
  v38[1] = v40;
  v43 = *(_OWORD *)v60;
  v38[2] = v42;
  v44 = *(_OWORD *)&v60[12];
  v38[3] = v43;
  *(_OWORD *)((char *)v38 + 60) = v44;
  ORCompressCopyName((char *)v38 + 76, v28 + 76, v41, &v54);
  *(_QWORD *)(v30 + 40) = v39;
  v13 = ORInsertSubKey(v20, v30);
  if ( v13 )
    goto LABEL_96;
  v45 = v20[5];
  ++*(_DWORD *)(v45 + 20);
  *(struct _FILETIME *)(v45 + 4) = SystemTimeAsFileTime;
  if ( (unsigned int)(unsigned __int16)v49 > *(_DWORD *)(v45 + 56) )
    *(_DWORD *)(v45 + 56) = (unsigned __int16)v49;
  if ( (v29 & 0x20) != 0 )
  {
    if ( 2 * v28 > (unsigned __int64)*(unsigned __int16 *)(v45 + 52) )
    {
      LOWORD(v28) = 2 * v28;
LABEL_91:
      *(_WORD *)(v45 + 52) = v28;
    }
  }
  else if ( (unsigned __int16)v28 > *(_WORD *)(v45 + 52) )
  {
    goto LABEL_91;
  }
  ++v20[21];
  if ( a7 )
    *a7 = 1;
  v16 = v47;
  v14 = 0;
  v46 = a6;
  v13 = 0;
  *(_DWORD *)(v47 + 180) = 1;
  *(_DWORD *)(v30 + 24) = 1;
  *v46 = v30;
LABEL_16:
  ORFree(v14);
  if ( v53 != pSecurityDescriptor )
    ORFree(v53);
  if ( ObjectDescriptor[0] )
    DestroyPrivateObjectSecurity(ObjectDescriptor);
  if ( v10 )
    LeaveCriticalSection((LPCRITICAL_SECTION)(v16 + 136));
  return v13;
}

```

## disassembly

```asm
0x1402469f0  mov     [rsp-8+arg_8], rbx
0x1402469f5  mov     [rsp-8+Src], r8
0x1402469fa  push    rbp
0x1402469fb  push    rsi
0x1402469fc  push    rdi
0x1402469fd  push    r12
0x1402469ff  push    r13
0x140246a01  push    r14
0x140246a03  push    r15
0x140246a05  lea     rbp, [rsp-0Fh]
0x140246a0a  sub     rsp, 0E0h
0x140246a11  mov     r12, [rbp+3Fh+arg_28]
0x140246a15  xor     r14d, r14d
0x140246a18  mov     eax, 746Eh
0x140246a1d  mov     [rsp+110h+var_D0], r14
0x140246a22  xorps   xmm0, xmm0
0x140246a25  mov     [rbp+3Fh+var_A0], r14
0x140246a29  xorps   xmm1, xmm1
0x140246a2c  mov     [rsp+110h+var_E0], r14d
0x140246a31  mov     [r12], r14
0x140246a35  mov     rdi, rdx
0x140246a38  mov     rsi, rcx
0x140246a3b  mov     [rsp+110h+var_F0], r14
0x140246a40  mov     r15d, r14d
0x140246a43  mov     [rsp+110h+var_E8], r14
0x140246a48  movups  [rbp+3Fh+var_B0], xmm0
0x140246a4c  mov     qword ptr [rsp+110h+SystemTimeAsFileTime.dwLowDateTime], r14
0x140246a51  movups  [rbp+3Fh+var_98], xmm1
0x140246a55  mov     [rbp+3Fh+var_B8], r14
0x140246a59  mov     [rsp+110h+ObjectDescriptor], r14
0x140246a5e  mov     [rbp+3Fh+arg_0], r14w
0x140246a63  cmp     [rcx+1Ch], ax
0x140246a67  jnz     loc_140246FD0
0x140246a6d  mov     r13, [rcx+10h]
0x140246a71  mov     [rsp+110h+var_F0], r13
0x140246a76  cmp     dword ptr [r13+0], 0BEE0BEE0h
0x140246a7e  jnz     loc_140246FD0
0x140246a84  test    rdx, rdx
0x140246a87  jz      loc_140246FC3
0x140246a8d  cmp     [rdx], r14w
0x140246a91  jz      loc_140246FC3
0x140246a97  mov     r14d, r9d
0x140246a9a  and     r14d, 2
0x140246a9e  cmp     r9d, r14d
0x140246aa1  jz      short loc_140246AAD
0x140246aa3  mov     ebx, 57h ; 'W'
0x140246aa8  mov     ecx, r15d
0x140246aab  jmp     short loc_140246B17
0x140246aad  lea     rcx, [r13+88h]; lpCriticalSection
0x140246ab4  call    cs:__imp_EnterCriticalSection
0x140246abb  nop     dword ptr [rax+rax+00h]
0x140246ac0  mov     rdx, rdi
0x140246ac3  lea     rcx, [rbp+3Fh+var_98]
0x140246ac7  mov     r15d, 1
0x140246acd  call    ORInitUnicodeStringEx
0x140246ad2  xor     r8d, r8d
0x140246ad5  mov     ebx, eax
0x140246ad7  test    eax, eax
0x140246ad9  jnz     short loc_140246B14
0x140246adb  movzx   ecx, word ptr [rbp+3Fh+var_98]
0x140246adf  lea     r9d, [r15+5Bh]
0x140246ae3  test    cx, cx
0x140246ae6  jz      short loc_140246B08
0x140246ae8  mov     rdx, qword ptr [rbp+3Fh+var_98+8]
0x140246aec  movzx   eax, cx
0x140246aef  shr     rax, 1
0x140246af2  cmp     [rdx+rax*2-2], r9w
0x140246af8  jnz     short loc_140246B04
0x140246afa  mov     eax, 0FFFEh
0x140246aff  add     cx, ax
0x140246b02  jnz     short loc_140246AEC
0x140246b04  mov     word ptr [rbp+3Fh+var_98], cx
0x140246b08  cmp     [rsi+1Eh], r8w
0x140246b0d  jz      short loc_140246B82
0x140246b0f  mov     ebx, 3FAh
0x140246b14  mov     rcx, r8
0x140246b17  xor     r14d, r14d
0x140246b1a  mov     rdi, r13
0x140246b1d  call    ORFree
0x140246b22  mov     rax, [rbp+3Fh+var_B8]
0x140246b26  cmp     rax, [rbp+3Fh+pSecurityDescriptor]
0x140246b2a  jz      short loc_140246B34
0x140246b2c  mov     rcx, rax
0x140246b2f  call    ORFree
0x140246b34  cmp     [rsp+110h+ObjectDescriptor], r14
0x140246b39  jz      short loc_140246B4C
0x140246b3b  lea     rcx, [rsp+110h+ObjectDescriptor]; ObjectDescriptor
0x140246b40  call    cs:__imp_DestroyPrivateObjectSecurity
0x140246b47  nop     dword ptr [rax+rax+00h]
0x140246b4c  test    r15d, r15d
0x140246b4f  jz      short loc_140246B64
0x140246b51  lea     rcx, [rdi+88h]; lpCriticalSection
0x140246b58  call    cs:__imp_LeaveCriticalSection
0x140246b5f  nop     dword ptr [rax+rax+00h]
0x140246b64  mov     eax, ebx
0x140246b66  mov     rbx, [rsp+110h+arg_8]
0x140246b6e  add     rsp, 0E0h
0x140246b75  pop     r15
0x140246b77  pop     r14
0x140246b79  pop     r13
0x140246b7b  pop     r12
0x140246b7d  pop     rdi
0x140246b7e  pop     rsi
0x140246b7f  pop     rbp
0x140246b80  retn
0x140246b82  test    cx, cx
0x140246b85  jnz     short loc_140246B8E
0x140246b87  mov     ebx, 57h ; 'W'
0x140246b8c  jmp     short loc_140246B14
0x140246b8e  lea     r9, [rsp+110h+var_D0]
0x140246b93  mov     rdx, rsi
0x140246b96  lea     r8, [rsp+110h+var_E0]
0x140246b9b  lea     rcx, [rbp+3Fh+var_98]
0x140246b9f  call    ORParseSubKey
0x140246ba4  xor     edx, edx
0x140246ba6  mov     ebx, eax
0x140246ba8  test    eax, eax
0x140246baa  jnz     short loc_140246BD0
0x140246bac  cmp     [rsp+110h+var_E0], 2
0x140246bb1  jnz     short loc_140246C0E
0x140246bb3  mov     rcx, [rsp+110h+var_D0]
0x140246bb8  test    r14d, r14d
0x140246bbb  jz      short loc_140246BDC
0x140246bbd  mov     rax, [rcx+28h]
0x140246bc1  lea     r12d, [rbx+10h]
0x140246bc5  test    [rax+2], r12b
0x140246bc9  jnz     short loc_140246BD8
0x140246bcb  mov     ebx, 57h ; 'W'
0x140246bd0  mov     rcx, rdx
0x140246bd3  jmp     loc_140246B17
0x140246bd8  mov     r12, [rbp+3Fh+arg_28]
0x140246bdc  cmp     rcx, [r13+38h]
0x140246be0  jz      short loc_140246BCB
0x140246be2  call    ORReferenceTreeNode
0x140246be7  xor     r14d, r14d
0x140246bea  mov     ebx, eax
0x140246bec  test    eax, eax
0x140246bee  jnz     short loc_140246C06
0x140246bf0  mov     rax, [rbp+3Fh+arg_30]
0x140246bf4  test    rax, rax
0x140246bf7  jz      short loc_140246BFF
0x140246bf9  mov     dword ptr [rax], 2
0x140246bff  mov     [r12], rcx
0x140246c03  mov     ebx, r14d
0x140246c06  mov     rcx, rdx
0x140246c09  jmp     loc_140246B1A
0x140246c0e  mov     r13, [rsp+110h+var_D0]
0x140246c13  mov     r12d, 10h
0x140246c19  mov     rax, [r13+28h]
0x140246c1d  test    [rax+2], r12b
0x140246c21  jz      short loc_140246C38
0x140246c23  mov     ebx, 5
0x140246c28  mov     rcx, rdx
0x140246c2b  mov     rdi, [rsp+110h+var_F0]
0x140246c30  xor     r14d, r14d
0x140246c33  jmp     loc_140246B1D
0x140246c38  mov     al, [rax+0Dh]
0x140246c3b  and     al, 3
0x140246c3d  cmp     al, r15b
0x140246c40  jz      short loc_140246C23
0x140246c42  mov     eax, 1FEh
0x140246c47  mov     rcx, rdx
0x140246c4a  cmp     [r13+20h], ax
0x140246c4f  jnz     short loc_140246C58
0x140246c51  mov     ebx, 57h ; 'W'
0x140246c56  jmp     short loc_140246C2B
0x140246c58  mov     rax, rdi
0x140246c5b  add     rax, 2
0x140246c5f  cmp     [rax], dx
0x140246c62  jnz     short loc_140246C5B
0x140246c64  mov     edx, 5Ch ; '\'
0x140246c69  cmp     rax, rdi
0x140246c6c  jbe     short loc_140246C86
0x140246c6e  sub     rax, 2
0x140246c72  cmp     [rax], dx
0x140246c75  jz      short loc_140246C69
0x140246c77  jmp     short loc_140246C86
0x140246c79  cmp     rax, rdi
0x140246c7c  jz      short loc_140246C8B
0x140246c7e  add     rcx, 2
0x140246c82  sub     rax, 2
0x140246c86  cmp     [rax], dx
0x140246c89  jnz     short loc_140246C79
0x140246c8b  cmp     dx, [rax]
0x140246c8e  lea     rsi, [rax+2]
0x140246c92  lea     rbx, [rcx+2]
0x140246c96  cmovnz  rsi, rax
0x140246c9a  cmp     rsi, rdi
0x140246c9d  cmovnz  rbx, rcx
0x140246ca1  cmp     rbx, 200h
0x140246ca8  jbe     short loc_140246CB9
0x140246caa  mov     ebx, 57h ; 'W'
0x140246caf  mov     rcx, [rsp+110h+var_E8]
0x140246cb4  jmp     loc_140246C2B
0x140246cb9  xor     edx, edx; Val
0x140246cbb  lea     rcx, [rbp+3Fh+var_80]; void *
0x140246cbf  lea     r8d, [rdx+50h]; Size
0x140246cc3  call    memset_0
0x140246cc8  xor     edi, edi
0x140246cca  mov     eax, 6B6Eh
0x140246ccf  mov     word ptr [rbp+3Fh+var_80], ax
0x140246cd3  test    r14d, r14d
0x140246cd6  jz      short loc_140246CDE
0x140246cd8  movzx   r14d, r12w
0x140246cdc  jmp     short loc_140246CE1
0x140246cde  mov     r14d, edi
0x140246ce1  lea     rcx, [rsp+110h+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x140246ce6  call    cs:__imp_GetSystemTimeAsFileTime
0x140246ced  nop     dword ptr [rax+rax+00h]
0x140246cf2  mov     eax, [rsp+110h+SystemTimeAsFileTime.dwLowDateTime]
0x140246cf6  lea     rdx, [rbp+3Fh+var_B0]
0x140246cfa  mov     dword ptr [rbp+3Fh+var_80+4], eax
0x140246cfd  mov     rcx, rbx
0x140246d00  mov     eax, [rsp+110h+SystemTimeAsFileTime.dwHighDateTime]
0x140246d04  mov     dword ptr [rbp+3Fh+var_80+8], eax
0x140246d07  or      eax, 0FFFFFFFFh
0x140246d0a  mov     dword ptr [rbp+3Fh+var_70], eax
0x140246d0d  mov     dword ptr [rbp+3Fh+var_70+0Ch], eax
0x140246d10  mov     dword ptr [rbp+3Fh+var_60], eax
0x140246d13  mov     dword ptr [rbp+3Fh+var_60+8], eax
0x140246d16  mov     dword ptr [rbp+3Fh+var_60+0Ch], eax
0x140246d19  mov     dword ptr [rbp+3Fh+var_50], eax
0x140246d1c  mov     eax, edi
0x140246d1e  mov     [rsp+110h+var_E0], eax
0x140246d22  mov     [rbp+3Fh+var_36], ax
0x140246d26  mov     byte ptr [rbp+3Fh+var_80+0Ch], dil
0x140246d2a  mov     qword ptr [rbp+3Fh+var_70+4], rdi
0x140246d2e  mov     dword ptr [rbp+3Fh+var_60+4], edi
0x140246d31  mov     [rbp+3Fh+var_38], di
0x140246d35  mov     qword ptr [rbp+3Fh+var_50+4], rdi
0x140246d39  mov     qword ptr [rbp+3Fh+var_50+0Ch], rdi
0x140246d3d  mov     qword ptr [rbp+3Fh+var_B0+8], rsi
0x140246d41  call    RtlULongPtrToUShort
0x140246d46  test    eax, eax
0x140246d48  jns     short loc_140246D54
0x140246d4a  mov     ebx, 216h
0x140246d4f  jmp     loc_140246CAF
0x140246d54  movzx   eax, word ptr [rbp+3Fh+var_B0]
0x140246d58  lea     rdx, [rbp+3Fh+var_B0]
0x140246d5c  mov     r10, [rsp+110h+var_F0]
0x140246d61  mov     word ptr [rbp+3Fh+var_B0+2], ax
0x140246d65  mov     rcx, [r10+10h]
0x140246d69  mov     [rsp+110h+var_D0], rcx
0x140246d6e  call    ORGetCompressedLength
0x140246d73  movzx   edi, ax
0x140246d76  mov     [rbp+3Fh+var_38], di
0x140246d7a  cmp     rdi, rbx
0x140246d7d  jnb     short loc_140246D86
0x140246d7f  or      r14w, 20h
0x140246d84  jmp     short loc_140246D8F
0x140246d86  mov     eax, 0FFDFh
0x140246d8b  and     r14w, ax
0x140246d8f  mov     rdx, r13
0x140246d92  mov     word ptr [rbp+3Fh+var_80+2], r14w
0x140246d97  mov     rcx, r10
0x140246d9a  call    ORAllocNode
0x140246d9f  mov     rsi, rax
0x140246da2  xor     eax, eax
0x140246da4  test    rsi, rsi
0x140246da7  jnz     short loc_140246DB3
0x140246da9  lea     ebx, [rax+8]
0x140246dac  mov     ecx, eax
0x140246dae  jmp     loc_140246C2B
0x140246db3  mov     rbx, [rbp+3Fh+pSecurityDescriptor]
0x140246db7  test    rbx, rbx
0x140246dba  jz      short loc_140246DEF
0x140246dbc  mov     rcx, rbx; pSecurityDescriptor
0x140246dbf  call    cs:__imp_IsValidSecurityDescriptor
0x140246dc6  nop     dword ptr [rax+rax+00h]
0x140246dcb  test    eax, eax
0x140246dcd  jnz     short loc_140246DD9
0x140246dcf  mov     ebx, 53Ah
0x140246dd4  jmp     loc_140246FAD
0x140246dd9  lea     rdx, [rbp+3Fh+var_B8]
0x140246ddd  mov     rcx, rbx; pAbsoluteSecurityDescriptor
0x140246de0  call    ORMakeSDRelative
0x140246de5  mov     ebx, eax
0x140246de7  test    eax, eax
0x140246de9  jnz     loc_140246FAD
0x140246def  mov     rax, [r13+60h]
0x140246df3  lea     r8, [rsp+110h+ObjectDescriptor]
0x140246df8  mov     rdx, [rbp+3Fh+var_B8]
0x140246dfc  mov     rcx, [rax+10h]
0x140246e00  add     rcx, 14h
0x140246e04  call    OrAssignSecurity
0x140246e09  mov     ebx, eax
0x140246e0b  test    eax, eax
0x140246e0d  jnz     loc_140246FAD
0x140246e13  mov     rdx, [rsp+110h+ObjectDescriptor]
0x140246e18  lea     r8, [rbp+3Fh+var_A0]
0x140246e1c  mov     rcx, [rsp+110h+var_F0]
0x140246e21  call    ORProcessSecurityDescriptor
0x140246e26  xor     r9d, r9d
0x140246e29  mov     ebx, eax
0x140246e2b  test    eax, eax
0x140246e2d  jnz     loc_140246FAD
0x140246e33  mov     rax, [rbp+3Fh+var_A0]
0x140246e37  mov     [rsi+60h], rax
0x140246e3b  mov     rcx, [rax+10h]
0x140246e3f  mov     rax, [rbp+3Fh+Src]
  ... truncated ...
```
