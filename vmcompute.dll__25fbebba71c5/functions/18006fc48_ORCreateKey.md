# ORCreateKey

- ea: `0x18006fc48`
- end: `0x18007029c`
- name: `ORCreateKey`
- size: `1620`
- prototype: `__int64 __fastcall(int, int, int, int, PSECURITY_DESCRIPTOR pSecurityDescriptor, __int64, __int64)`
- caller_count: `2`
- callee_count: `13`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800699f4`
- `0x18007b9e0`

## callees

- `0x180003b26`
- `0x180003b32`
- `0x180003c78`
- `0x180004829`
- `0x18006fb20`
- `0x18006fc48`
- `0x180070798`
- `0x1800730b4`
- `0x180073788`
- `0x180073bbc`
- `0x180073c10`
- `0x180073cb8`
- `0x18007469c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180070272`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180070272`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18006fcfc`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18006fcfc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180070042`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180070042`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18006feca`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18006feca`
- `api-ms-win-security-base-l1-1-0!DestroyPrivateObjectSecurity` at `0x18007025a`
- `api-ms-win-security-base-l1-1-0!DestroyPrivateObjectSecurity` at `0x18007025a`
- `api-ms-win-security-base-l1-1-0!CreatePrivateObjectSecurityWithMultipleInheritance` at `0x180070032`
- `api-ms-win-security-base-l1-1-0!CreatePrivateObjectSecurityWithMultipleInheritance` at `0x180070032`
- `api-ms-win-security-base-l1-1-0!IsValidSecurityDescriptor` at `0x18006ff89`
- `api-ms-win-security-base-l1-1-0!IsValidSecurityDescriptor` at `0x18006ff89`

## pseudocode

```c
__int64 __fastcall ORCreateKey(
        __int64 a1,
        _WORD *a2,
        _WORD *a3,
        int a4,
        PSECURITY_DESCRIPTOR pSecurityDescriptor,
        __int64 *a6,
        _DWORD *a7)
{
  __int64 *v7; // r12
  __int64 v10; // r15
  __int64 v11; // r13
  int v12; // r14d
  DWORD LastError; // ebx
  __int64 v14; // rsi
  unsigned __int16 v15; // cx
  __int64 v16; // rcx
  int v17; // edx
  __int64 v18; // r13
  __int64 v19; // rax
  unsigned __int64 v20; // rdx
  _WORD *v21; // rax
  __int16 v22; // cx
  _WORD *v23; // rsi
  unsigned __int64 v24; // rbx
  __int16 v25; // r14
  __int64 v26; // rcx
  unsigned __int16 v27; // ax
  __int64 v28; // r10
  __int64 v29; // rsi
  __int16 v30; // r14
  __int64 v31; // rdi
  void *v32; // r15
  __int64 v33; // r10
  ULONG AutoInheritFlags; // eax
  __int64 v35; // rax
  __int64 v36; // rax
  unsigned __int64 v37; // rax
  unsigned int v38; // ebx
  void *v39; // rax
  _OWORD *v40; // rax
  __int128 v41; // xmm1
  __int64 v42; // r8
  __int128 v43; // xmm0
  __int128 v44; // xmm1
  __int128 v45; // xmm0
  __int64 v46; // rdx
  void *v47; // rcx
  __int64 v49; // [rsp+50h] [rbp-A1h]
  int v50; // [rsp+58h] [rbp-99h] BYREF
  struct _FILETIME SystemTimeAsFileTime; // [rsp+60h] [rbp-91h] BYREF
  BOOL IsContainerObject[2]; // [rsp+68h] [rbp-89h]
  __int64 v53; // [rsp+70h] [rbp-81h] BYREF
  PSECURITY_DESCRIPTOR NewDescriptor; // [rsp+78h] [rbp-79h] BYREF
  PSECURITY_DESCRIPTOR CreatorDescriptor; // [rsp+80h] [rbp-71h]
  __int64 v56; // [rsp+88h] [rbp-69h] BYREF
  __int128 v57; // [rsp+90h] [rbp-61h] BYREF
  __int128 v58; // [rsp+A0h] [rbp-51h] BYREF
  __int128 v59; // [rsp+B0h] [rbp-41h] BYREF
  __int128 v60; // [rsp+C0h] [rbp-31h]
  __int128 v61; // [rsp+D0h] [rbp-21h]
  _BYTE v62[28]; // [rsp+E0h] [rbp-11h]
  unsigned __int16 v63; // [rsp+140h] [rbp+4Fh]

  v7 = a6;
  v53 = 0;
  v56 = 0;
  v50 = 0;
  *a6 = 0;
  v49 = 0;
  LODWORD(v10) = 0;
  SystemTimeAsFileTime = 0;
  v58 = 0;
  CreatorDescriptor = 0;
  v57 = 0;
  NewDescriptor = 0;
  if ( *(_WORD *)(a1 + 28) != 29806 || (v11 = *(_QWORD *)(a1 + 16), v49 = v11, *(_DWORD *)v11 != -1092567328) )
  {
    LastError = 6;
    goto LABEL_97;
  }
  if ( !a2 )
    goto LABEL_6;
  if ( !*a2 )
    goto LABEL_6;
  v12 = a4 & 2;
  if ( a4 != v12 )
    goto LABEL_6;
  EnterCriticalSection((LPCRITICAL_SECTION)(v11 + 136));
  LODWORD(v10) = 1;
  *(_QWORD *)IsContainerObject = 1;
  LastError = ORInitUnicodeStringEx(&v57, a2);
  if ( LastError )
    goto LABEL_97;
  v15 = v57;
  if ( (_WORD)v57 )
  {
    do
    {
      if ( *(_WORD *)(*((_QWORD *)&v57 + 1) + 2 * ((unsigned __int64)v15 >> 1) - 2) != 92 )
        break;
      v15 -= 2;
    }
    while ( v15 );
    LOWORD(v57) = v15;
  }
  if ( *(_WORD *)(a1 + 30) )
  {
    LastError = 1018;
    goto LABEL_7;
  }
  if ( !v15 )
    goto LABEL_6;
  LastError = ORParseSubKey(&v57, a1, &v50, &v53);
  if ( LastError )
  {
LABEL_97:
    v14 = v49;
    goto LABEL_98;
  }
  if ( v50 == 2 )
  {
    v16 = v53;
    if ( !v12 )
      goto LABEL_21;
    if ( (*(_BYTE *)(*(_QWORD *)(v53 + 40) + 2LL) & 0x10) != 0 )
    {
      v7 = a6;
LABEL_21:
      if ( v53 != *(_QWORD *)(v11 + 56) )
      {
        v17 = *(_DWORD *)(v53 + 24);
        if ( v17 == -1 )
        {
          LastError = 1450;
        }
        else
        {
          *(_DWORD *)(v53 + 24) = v17 + 1;
          if ( a7 )
            *a7 = 2;
          *v7 = v16;
          LastError = 0;
        }
        goto LABEL_7;
      }
    }
LABEL_6:
    LastError = 87;
LABEL_7:
    v14 = v11;
    goto LABEL_98;
  }
  v18 = v53;
  v19 = *(_QWORD *)(v53 + 40);
  if ( (*(_BYTE *)(v19 + 2) & 0x10) != 0 || (*(_BYTE *)(v19 + 13) & 3) == 1 )
  {
    LastError = 5;
    goto LABEL_97;
  }
  if ( *(_WORD *)(v53 + 32) == 510 )
    goto LABEL_31;
  v20 = 0;
  v21 = a2;
  do
    v22 = *++v21;
  while ( *v21 );
  while ( v21 > a2 )
  {
    v22 = *--v21;
    if ( *v21 != 92 )
      goto LABEL_38;
  }
  if ( v22 == 92 )
    goto LABEL_40;
  do
  {
LABEL_38:
    if ( v21 == a2 )
      break;
    --v21;
    v20 += 2LL;
  }
  while ( *v21 != 92 );
LABEL_40:
  v23 = v21 + 1;
  v24 = v20 + 2;
  if ( *v21 != 92 )
    v23 = v21;
  if ( v23 != a2 )
    v24 = v20;
  if ( v24 > 0x200 )
  {
LABEL_31:
    LastError = 87;
    goto LABEL_97;
  }
  memset_0(&v59, 0, 0x50u);
  LOWORD(v59) = 27502;
  if ( v12 )
    v25 = 16;
  else
    v25 = 0;
  GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
  *(struct _FILETIME *)((char *)&v59 + 4) = SystemTimeAsFileTime;
  LODWORD(v60) = -1;
  HIDWORD(v60) = -1;
  *(_QWORD *)&v61 = 0xFFFFFFFFLL;
  *((_QWORD *)&v61 + 1) = -1;
  *(_DWORD *)v62 = -1;
  v63 = 0;
  *(_WORD *)&v62[26] = 0;
  v26 = *(_QWORD *)(v49 + 16);
  BYTE12(v59) = 0;
  *(_QWORD *)((char *)&v60 + 4) = 0;
  *(_OWORD *)&v62[4] = 0u;
  *((_QWORD *)&v58 + 1) = v23;
  LOWORD(v58) = v24;
  v53 = v26;
  WORD1(v58) = v24;
  v27 = ORGetCompressedLength(v26, &v58);
  v29 = v27;
  *(_WORD *)&v62[24] = v27;
  if ( v27 >= v24 )
    v30 = v25 & 0xFFDF;
  else
    v30 = v25 | 0x20;
  WORD1(v59) = v30;
  v31 = ORAllocNode(v28, v18);
  if ( !v31 )
  {
    LastError = 8;
    goto LABEL_97;
  }
  v32 = 0;
  if ( pSecurityDescriptor )
  {
    if ( !IsValidSecurityDescriptor(pSecurityDescriptor) )
    {
      LastError = 1338;
LABEL_91:
      v47 = *(void **)(v31 + 120);
      if ( v47 )
        aligned_free(v47);
      aligned_free((void *)v31);
      if ( v32 )
        aligned_free(v32);
      LODWORD(v10) = IsContainerObject[0];
      goto LABEL_97;
    }
    LastError = ORMakeSDRelative(pSecurityDescriptor);
    if ( LastError )
      goto LABEL_91;
  }
  v33 = *(_QWORD *)(*(_QWORD *)(v18 + 96) + 16LL);
  if ( CreatorDescriptor && (*((_BYTE *)CreatorDescriptor + 2) & 4) != 0 )
  {
    AutoInheritFlags = 4216;
  }
  else
  {
    AutoInheritFlags = (*(_WORD *)(v33 + 22) & 0x400 | 0x41E000u) >> 10;
    if ( !CreatorDescriptor )
      goto LABEL_62;
  }
  if ( (*((_BYTE *)CreatorDescriptor + 2) & 0x10) == 0 )
  {
LABEL_62:
    if ( (*(_WORD *)(v33 + 22) & 0x800) != 0 )
      AutoInheritFlags |= 2u;
  }
  if ( !CreatePrivateObjectSecurityWithMultipleInheritance(
          (PSECURITY_DESCRIPTOR)(v33 + 20),
          CreatorDescriptor,
          &NewDescriptor,
          0,
          0,
          IsContainerObject[0],
          AutoInheritFlags,
          0,
          &CmKeyMapping) )
  {
    LastError = GetLastError();
    if ( LastError )
      goto LABEL_91;
  }
  LastError = ORProcessSecurityDescriptor(v49, NewDescriptor, &v56);
  if ( LastError )
    goto LABEL_91;
  v35 = v56;
  *(_QWORD *)(v31 + 96) = v56;
  *(_DWORD *)(*(_QWORD *)(v35 + 16) + 12LL) += IsContainerObject[0];
  if ( a3 )
  {
    v36 = -1;
    do
      ++v36;
    while ( a3[v36] );
    v37 = 2 * v36;
    if ( v37 > 0xFFFF )
    {
      LastError = 534;
      goto LABEL_91;
    }
    *(_WORD *)&v62[26] = v37;
    v63 = v37;
    if ( (_WORD)v37 )
    {
      v38 = (unsigned __int16)v37;
      v39 = o__aligned_malloc_0((unsigned __int16)v37, 0x10u);
      *(_QWORD *)(v31 + 120) = v39;
      if ( !v39 )
      {
LABEL_75:
        LastError = 8;
        goto LABEL_91;
      }
      memcpy_0(v39, a3, v38);
    }
  }
  v40 = o__aligned_malloc_0(v29 + 76, 0x10u);
  v32 = v40;
  if ( !v40 )
    goto LABEL_75;
  v41 = v60;
  v42 = v53;
  *v40 = v59;
  v43 = v61;
  v40[1] = v41;
  v44 = *(_OWORD *)v62;
  v40[2] = v43;
  v45 = *(_OWORD *)&v62[12];
  v40[3] = v44;
  *(_OWORD *)((char *)v40 + 60) = v45;
  ORCompressCopyName((char *)v40 + 76, v29 + 76, v42, &v58);
  *(_QWORD *)(v31 + 40) = v32;
  if ( !v18 || *(_WORD *)(v18 + 28) != 29806 || *(_WORD *)(v31 + 28) != 29806 )
  {
    LastError = 87;
    goto LABEL_91;
  }
  ORInsertTreeNodeIntoSubkeyList(v18, v31);
  v46 = *(_QWORD *)(v18 + 40);
  v10 = *(_QWORD *)IsContainerObject;
  *(_DWORD *)(v46 + 20) += IsContainerObject[0];
  *(struct _FILETIME *)(v46 + 4) = SystemTimeAsFileTime;
  if ( (unsigned int)v63 > *(_DWORD *)(v46 + 56) )
    *(_DWORD *)(v46 + 56) = v63;
  if ( (v30 & 0x20) != 0 )
  {
    if ( 2 * v29 > (unsigned __int64)*(unsigned __int16 *)(v46 + 52) )
    {
      LOWORD(v29) = 2 * v29;
LABEL_85:
      *(_WORD *)(v46 + 52) = v29;
    }
  }
  else if ( (unsigned __int16)v29 > *(_WORD *)(v46 + 52) )
  {
    goto LABEL_85;
  }
  *(_QWORD *)(v18 + 168) += v10;
  if ( a7 )
    *a7 = v10;
  v14 = v49;
  LastError = 0;
  *(_DWORD *)(v49 + 180) = v10;
  *(_DWORD *)(v31 + 24) = v10;
  *a6 = v31;
LABEL_98:
  if ( CreatorDescriptor != pSecurityDescriptor && CreatorDescriptor )
    aligned_free(CreatorDescriptor);
  if ( NewDescriptor )
    DestroyPrivateObjectSecurity(&NewDescriptor);
  if ( (_DWORD)v10 )
    LeaveCriticalSection((LPCRITICAL_SECTION)(v14 + 136));
  return LastError;
}

```

## disassembly

```asm
0x18006fc48  mov     [rsp-8+arg_8], rbx
0x18006fc4d  mov     [rsp-8+Src], r8
0x18006fc52  push    rbp
0x18006fc53  push    rsi
0x18006fc54  push    rdi
0x18006fc55  push    r12
0x18006fc57  push    r13
0x18006fc59  push    r14
0x18006fc5b  push    r15
0x18006fc5d  lea     rbp, [rsp-0Fh]
0x18006fc62  sub     rsp, 100h
0x18006fc69  mov     r12, [rbp+3Fh+arg_28]
0x18006fc6d  xor     r10d, r10d
0x18006fc70  mov     eax, 746Eh
0x18006fc75  mov     [rsp+130h+var_C0], r10
0x18006fc7a  xorps   xmm0, xmm0
0x18006fc7d  mov     [rbp+3Fh+var_A8], r10
0x18006fc81  xorps   xmm1, xmm1
0x18006fc84  mov     [rsp+130h+var_D8], r10d
0x18006fc89  mov     [r12], r10
0x18006fc8d  mov     rdi, rdx
0x18006fc90  mov     rsi, rcx
0x18006fc93  mov     [rsp+130h+var_E0], r10
0x18006fc98  mov     r15d, r10d
0x18006fc9b  mov     qword ptr [rsp+130h+SystemTimeAsFileTime.dwLowDateTime], r10
0x18006fca0  movups  [rbp+3Fh+var_90], xmm0
0x18006fca4  mov     [rbp+3Fh+CreatorDescriptor], r10
0x18006fca8  movups  [rbp+3Fh+var_A0], xmm1
0x18006fcac  mov     [rbp+3Fh+NewDescriptor], r10
0x18006fcb0  cmp     [rcx+1Ch], ax
0x18006fcb4  jnz     loc_18007022D
0x18006fcba  mov     r13, [rcx+10h]
0x18006fcbe  mov     [rsp+130h+var_E0], r13
0x18006fcc3  cmp     dword ptr [r13+0], 0BEE0BEE0h
0x18006fccb  jnz     loc_18007022D
0x18006fcd1  test    rdx, rdx
0x18006fcd4  jz      short loc_18006FCE8
0x18006fcd6  cmp     [rdx], r10w
0x18006fcda  jz      short loc_18006FCE8
0x18006fcdc  mov     r14d, r9d
0x18006fcdf  and     r14d, 2
0x18006fce3  cmp     r9d, r14d
0x18006fce6  jz      short loc_18006FCF5
0x18006fce8  mov     ebx, 57h ; 'W'
0x18006fced  mov     rsi, r13
0x18006fcf0  jmp     loc_180070237
0x18006fcf5  lea     rcx, [r13+88h]; lpCriticalSection
0x18006fcfc  call    cs:__imp_EnterCriticalSection
0x18006fd03  nop     dword ptr [rax+rax+00h]
0x18006fd08  mov     r15d, 1
0x18006fd0e  lea     rcx, [rbp+3Fh+var_A0]
0x18006fd12  mov     rdx, rdi
0x18006fd15  mov     qword ptr [rsp+130h+var_C8], r15
0x18006fd1a  call    ORInitUnicodeStringEx
0x18006fd1f  xor     r10d, r10d
0x18006fd22  mov     ebx, eax
0x18006fd24  test    eax, eax
0x18006fd26  jnz     loc_180070232
0x18006fd2c  movzx   ecx, word ptr [rbp+3Fh+var_A0]
0x18006fd30  lea     r8d, [r15+5Bh]
0x18006fd34  test    cx, cx
0x18006fd37  jz      short loc_18006FD59
0x18006fd39  mov     rdx, qword ptr [rbp+3Fh+var_A0+8]
0x18006fd3d  movzx   eax, cx
0x18006fd40  shr     rax, 1
0x18006fd43  cmp     [rdx+rax*2-2], r8w
0x18006fd49  jnz     short loc_18006FD55
0x18006fd4b  mov     eax, 0FFFEh
0x18006fd50  add     cx, ax
0x18006fd53  jnz     short loc_18006FD3D
0x18006fd55  mov     word ptr [rbp+3Fh+var_A0], cx
0x18006fd59  cmp     [rsi+1Eh], r10w
0x18006fd5e  jz      short loc_18006FD67
0x18006fd60  mov     ebx, 3FAh
0x18006fd65  jmp     short loc_18006FCED
0x18006fd67  test    cx, cx
0x18006fd6a  jz      loc_18006FCE8
0x18006fd70  lea     r9, [rsp+130h+var_C0]
0x18006fd75  mov     rdx, rsi
0x18006fd78  lea     r8, [rsp+130h+var_D8]
0x18006fd7d  lea     rcx, [rbp+3Fh+var_A0]
0x18006fd81  call    ORParseSubKey
0x18006fd86  xor     r10d, r10d
0x18006fd89  mov     ebx, eax
0x18006fd8b  test    eax, eax
0x18006fd8d  jnz     loc_180070232
0x18006fd93  cmp     [rsp+130h+var_D8], 2
0x18006fd98  jnz     short loc_18006FDF9
0x18006fd9a  mov     rcx, [rsp+130h+var_C0]
0x18006fd9f  test    r14d, r14d
0x18006fda2  jz      short loc_18006FDBA
0x18006fda4  mov     rax, [rcx+28h]
0x18006fda8  lea     r12d, [rbx+10h]
0x18006fdac  test    [rax+2], r12b
0x18006fdb0  jz      loc_18006FCE8
0x18006fdb6  mov     r12, [rbp+3Fh+arg_28]
0x18006fdba  cmp     rcx, [r13+38h]
0x18006fdbe  jz      loc_18006FCE8
0x18006fdc4  mov     edx, [rcx+18h]
0x18006fdc7  or      eax, 0FFFFFFFFh
0x18006fdca  cmp     edx, eax
0x18006fdcc  jnz     short loc_18006FDD8
0x18006fdce  mov     ebx, 5AAh
0x18006fdd3  jmp     loc_18006FCED
0x18006fdd8  lea     eax, [rdx+1]
0x18006fddb  mov     [rcx+18h], eax
0x18006fdde  mov     rax, [rbp+3Fh+arg_30]
0x18006fde2  test    rax, rax
0x18006fde5  jz      short loc_18006FDED
0x18006fde7  mov     dword ptr [rax], 2
0x18006fded  mov     [r12], rcx
0x18006fdf1  mov     ebx, r10d
0x18006fdf4  jmp     loc_18006FCED
0x18006fdf9  mov     r13, [rsp+130h+var_C0]
0x18006fdfe  mov     r12d, 10h
0x18006fe04  mov     rax, [r13+28h]
0x18006fe08  test    [rax+2], r12b
0x18006fe0c  jz      short loc_18006FE18
0x18006fe0e  mov     ebx, 5
0x18006fe13  jmp     loc_180070232
0x18006fe18  mov     al, [rax+0Dh]
0x18006fe1b  and     al, 3
0x18006fe1d  cmp     al, r15b
0x18006fe20  jz      short loc_18006FE0E
0x18006fe22  mov     eax, 1FEh
0x18006fe27  cmp     [r13+20h], ax
0x18006fe2c  jnz     short loc_18006FE38
0x18006fe2e  mov     ebx, 57h ; 'W'
0x18006fe33  jmp     loc_180070232
0x18006fe38  mov     rdx, r10
0x18006fe3b  mov     rax, rdi
0x18006fe3e  add     rax, 2
0x18006fe42  movzx   ecx, word ptr [rax]
0x18006fe45  test    cx, cx
0x18006fe48  jnz     short loc_18006FE3E
0x18006fe4a  mov     r8d, 5Ch ; '\'
0x18006fe50  cmp     rax, rdi
0x18006fe53  jbe     short loc_18006FE64
0x18006fe55  sub     rax, 2
0x18006fe59  movzx   ecx, word ptr [rax]
0x18006fe5c  cmp     cx, r8w
0x18006fe60  jnz     short loc_18006FE6A
0x18006fe62  jmp     short loc_18006FE50
0x18006fe64  cmp     cx, r8w
0x18006fe68  jz      short loc_18006FE7D
0x18006fe6a  cmp     rax, rdi
0x18006fe6d  jz      short loc_18006FE7D
0x18006fe6f  sub     rax, 2
0x18006fe73  add     rdx, 2
0x18006fe77  cmp     [rax], r8w
0x18006fe7b  jnz     short loc_18006FE6A
0x18006fe7d  cmp     r8w, [rax]
0x18006fe81  lea     rsi, [rax+2]
0x18006fe85  lea     rbx, [rdx+2]
0x18006fe89  cmovnz  rsi, rax
0x18006fe8d  cmp     rsi, rdi
0x18006fe90  cmovnz  rbx, rdx
0x18006fe94  cmp     rbx, 200h
0x18006fe9b  ja      short loc_18006FE2E
0x18006fe9d  xor     edx, edx; Val
0x18006fe9f  lea     rcx, [rbp+3Fh+var_80]; void *
0x18006fea3  lea     r8d, [rdx+50h]; Size
0x18006fea7  call    memset_0
0x18006feac  xor     edi, edi
0x18006feae  mov     eax, 6B6Eh
0x18006feb3  mov     word ptr [rbp+3Fh+var_80], ax
0x18006feb7  test    r14d, r14d
0x18006feba  jz      short loc_18006FEC2
0x18006febc  movzx   r14d, r12w
0x18006fec0  jmp     short loc_18006FEC5
0x18006fec2  mov     r14d, edi
0x18006fec5  lea     rcx, [rsp+130h+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x18006feca  call    cs:__imp_GetSystemTimeAsFileTime
0x18006fed1  nop     dword ptr [rax+rax+00h]
0x18006fed6  mov     eax, [rsp+130h+SystemTimeAsFileTime.dwLowDateTime]
0x18006feda  lea     rdx, [rbp+3Fh+var_90]
0x18006fede  mov     r10, [rsp+130h+var_E0]
0x18006fee3  mov     dword ptr [rbp+3Fh+var_80+4], eax
0x18006fee6  mov     eax, [rsp+130h+SystemTimeAsFileTime.dwHighDateTime]
0x18006feea  mov     dword ptr [rbp+3Fh+var_80+8], eax
0x18006feed  or      eax, 0FFFFFFFFh
0x18006fef0  mov     dword ptr [rbp+3Fh+var_70], eax
0x18006fef3  mov     dword ptr [rbp+3Fh+var_70+0Ch], eax
0x18006fef6  mov     dword ptr [rbp+3Fh+var_60], eax
0x18006fef9  mov     dword ptr [rbp+3Fh+var_60+8], eax
0x18006fefc  mov     dword ptr [rbp+3Fh+var_60+0Ch], eax
0x18006feff  mov     dword ptr [rbp+3Fh+var_50], eax
0x18006ff02  mov     eax, edi
0x18006ff04  mov     [rbp+3Fh+arg_0], eax
0x18006ff07  mov     [rbp+3Fh+var_36], ax
0x18006ff0b  mov     rax, [r10+10h]
0x18006ff0f  mov     rcx, rax
0x18006ff12  mov     byte ptr [rbp+3Fh+var_80+0Ch], dil
0x18006ff16  mov     qword ptr [rbp+3Fh+var_70+4], rdi
0x18006ff1a  mov     dword ptr [rbp+3Fh+var_60+4], edi
0x18006ff1d  mov     qword ptr [rbp+3Fh+var_50+4], rdi
0x18006ff21  mov     qword ptr [rbp+3Fh+var_50+0Ch], rdi
0x18006ff25  mov     qword ptr [rbp+3Fh+var_90+8], rsi
0x18006ff29  mov     word ptr [rbp+3Fh+var_90], bx
0x18006ff2d  mov     [rsp+130h+var_C0], rax
0x18006ff32  mov     word ptr [rbp+3Fh+var_90+2], bx
0x18006ff36  call    ORGetCompressedLength
0x18006ff3b  movzx   esi, ax
0x18006ff3e  mov     [rbp+3Fh+var_38], si
0x18006ff42  cmp     rsi, rbx
0x18006ff45  jnb     short loc_18006FF4E
0x18006ff47  or      r14w, 20h
0x18006ff4c  jmp     short loc_18006FF57
0x18006ff4e  mov     eax, 0FFDFh
0x18006ff53  and     r14w, ax
0x18006ff57  mov     rdx, r13
0x18006ff5a  mov     word ptr [rbp+3Fh+var_80+2], r14w
0x18006ff5f  mov     rcx, r10
0x18006ff62  call    ORAllocNode
0x18006ff67  xor     r10d, r10d
0x18006ff6a  mov     rdi, rax
0x18006ff6d  test    rax, rax
0x18006ff70  jnz     short loc_18006FF7A
0x18006ff72  lea     ebx, [rax+8]
0x18006ff75  jmp     loc_180070232
0x18006ff7a  mov     rbx, [rbp+3Fh+pSecurityDescriptor]
0x18006ff7e  mov     r15, r10
0x18006ff81  test    rbx, rbx
0x18006ff84  jz      short loc_18006FFB9
0x18006ff86  mov     rcx, rbx; pSecurityDescriptor
0x18006ff89  call    cs:__imp_IsValidSecurityDescriptor
0x18006ff90  nop     dword ptr [rax+rax+00h]
0x18006ff95  test    eax, eax
0x18006ff97  jnz     short loc_18006FFA3
0x18006ff99  mov     ebx, 53Ah
0x18006ff9e  jmp     loc_180070203
0x18006ffa3  lea     rdx, [rbp+3Fh+CreatorDescriptor]
0x18006ffa7  mov     rcx, rbx; pAbsoluteSecurityDescriptor
0x18006ffaa  call    ORMakeSDRelative
0x18006ffaf  mov     ebx, eax
0x18006ffb1  test    eax, eax
0x18006ffb3  jnz     loc_180070203
0x18006ffb9  mov     rax, [r13+60h]
0x18006ffbd  xor     ebx, ebx
0x18006ffbf  mov     rdx, [rbp+3Fh+CreatorDescriptor]; CreatorDescriptor
0x18006ffc3  mov     r10, [rax+10h]
0x18006ffc7  test    rdx, rdx
0x18006ffca  jz      short loc_18006FFD9
0x18006ffcc  test    byte ptr [rdx+2], 4
0x18006ffd0  jz      short loc_18006FFD9
0x18006ffd2  mov     eax, 1078h
0x18006ffd7  jmp     short loc_18006FFF0
0x18006ffd9  movzx   eax, word ptr [r10+16h]
0x18006ffde  and     eax, 400h
0x18006ffe3  or      eax, 41E000h
0x18006ffe8  shr     eax, 0Ah
0x18006ffeb  test    rdx, rdx
0x18006ffee  jz      short loc_18006FFF6
0x18006fff0  test    [rdx+2], r12b
0x18006fff4  jnz     short loc_180070005
0x18006fff6  mov     ecx, 800h
0x18006fffb  test    [r10+16h], cx
0x180070000  jz      short loc_180070005
0x180070002  or      eax, 2
0x180070005  lea     rcx, CmKeyMapping
0x18007000c  xor     r9d, r9d; ObjectTypes
0x18007000f  mov     [rsp+130h+GenericMapping], rcx; GenericMapping
0x180070014  lea     r8, [rbp+3Fh+NewDescriptor]; NewDescriptor
0x180070018  mov     [rsp+130h+Token], rbx; Token
0x18007001d  lea     rcx, [r10+14h]; ParentDescriptor
0x180070021  mov     [rsp+130h+AutoInheritFlags], eax; AutoInheritFlags
0x180070025  mov     rax, qword ptr [rsp+130h+var_C8]
0x18007002a  mov     [rsp+130h+IsContainerObject], eax; IsContainerObject
0x18007002e  mov     [rsp+130h+GuidCount], ebx; GuidCount
0x180070032  call    cs:__imp_CreatePrivateObjectSecurityWithMultipleInheritance
0x180070039  nop     dword ptr [rax+rax+00h]
0x18007003e  test    eax, eax
0x180070040  jnz     short loc_180070058
0x180070042  call    cs:__imp_GetLastError
0x180070049  nop     dword ptr [rax+rax+00h]
0x18007004e  mov     ebx, eax
0x180070050  test    eax, eax
0x180070052  jnz     loc_180070203
0x180070058  mov     rdx, [rbp+3Fh+NewDescriptor]
0x18007005c  lea     r8, [rbp+3Fh+var_A8]
0x180070060  mov     rcx, [rsp+130h+var_E0]
0x180070065  call    ORProcessSecurityDescriptor
0x18007006a  mov     ebx, eax
0x18007006c  test    eax, eax
0x18007006e  jnz     loc_180070203
0x180070074  mov     rax, [rbp+3Fh+var_A8]
0x180070078  xor     ebx, ebx
0x18007007a  mov     [rdi+60h], rax
0x18007007e  mov     rcx, [rax+10h]
0x180070082  mov     rax, qword ptr [rsp+130h+var_C8]
0x180070087  add     [rcx+0Ch], eax
0x18007008a  mov     rcx, [rbp+3Fh+Src]
0x18007008e  test    rcx, rcx
0x180070091  jz      short loc_1800700E3
0x180070093  or      rax, 0FFFFFFFFFFFFFFFFh
0x180070097  inc     rax
0x18007009a  cmp     [rcx+rax*2], bx
0x18007009e  jnz     short loc_180070097
0x1800700a0  add     rax, rax
0x1800700a3  cmp     rax, 0FFFFh
  ... truncated ...
```
