# I_HashComputeImageHashesEx<BCRYPT_HASH_CTXT>(BCRYPT_HASH_CTXT *,void const *,ulong,ulong,long (*)(void *,ulong,ulong *,void * *,ulong *),void *,uchar * *,ulong *,ulong,HASHLIB_CERT_INFO *,uchar *)

- ea: `0x180016e50`
- end: `0x180017430`
- name: `??$I_HashComputeImageHashesEx@UBCRYPT_HASH_CTXT@@@@YAJPEAUBCRYPT_HASH_CTXT@@PEBXKKP6AJPEAXKPEAKPEAPEAX3@Z2PEAPEAE3KPEAUHASHLIB_CERT_INFO@@PEAE@Z`
- size: `1504`
- prototype: `__int64 __fastcall(struct BCRYPT_HASH_CTXT *, PUCHAR pbInput, ULONG, unsigned int, int, void *, unsigned __int8 **, unsigned int *, unsigned int, int, _BYTE *)`
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x18001695c`

## callees

- `0x180016e50`
- `0x180017440`
- `0x1800179a0`
- `0x1800483ac`
- `0x18004de6a`
- `0x18004deb0`
- `0x180051010`

## import_xrefs

- `bcrypt!BCryptHashData` at `0x18001717c`
- `bcrypt!BCryptHashData` at `0x1800172de`
- `bcrypt!BCryptHashData` at `0x1800173b3`
- `bcrypt!BCryptHashData` at `0x1800173f1`
- `bcrypt!BCryptHashData` at `0x18001717c`
- `bcrypt!BCryptHashData` at `0x1800172de`
- `bcrypt!BCryptHashData` at `0x1800173b3`
- `bcrypt!BCryptHashData` at `0x1800173f1`
- `bcrypt!BCryptCreateHash` at `0x180016f47`
- `bcrypt!BCryptCreateHash` at `0x180016f47`
- `bcrypt!BCryptFinishHash` at `0x180017093`
- `bcrypt!BCryptFinishHash` at `0x180017093`
- `bcrypt!BCryptGetProperty` at `0x180016f85`
- `bcrypt!BCryptGetProperty` at `0x180016f85`
- `bcrypt!BCryptDestroyHash` at `0x18001709e`
- `bcrypt!BCryptDestroyHash` at `0x1800173c6`
- `bcrypt!BCryptDestroyHash` at `0x18001709e`
- `bcrypt!BCryptDestroyHash` at `0x1800173c6`

## pseudocode

```c
__int64 __fastcall I_HashComputeImageHashesEx<BCRYPT_HASH_CTXT>(
        struct BCRYPT_HASH_CTXT *a1,
        PUCHAR pbInput,
        ULONG a3,
        unsigned int a4,
        int a5,
        void *a6,
        unsigned __int8 **a7,
        unsigned int *a8,
        unsigned int a9,
        int a10,
        _BYTE *a11)
{
  unsigned int *v11; // rax
  struct BCRYPT_HASH_CTXT *v12; // r10
  unsigned __int8 **v14; // rcx
  unsigned __int64 v16; // rcx
  __int64 v17; // rbx
  char *v18; // r15
  void *v19; // rcx
  int v20; // esi
  _DWORD *v21; // rcx
  unsigned int v22; // r15d
  struct BCRYPT_HASH_CTXT *v23; // rsi
  __int64 v24; // r14
  __int64 v25; // rdi
  unsigned int v27; // r14d
  unsigned int v28; // edi
  unsigned int v29; // r9d
  __int64 v30; // rdx
  unsigned int v31; // eax
  unsigned int v32; // r15d
  unsigned int v33; // ecx
  unsigned int v34; // r13d
  ULONG v35; // esi
  unsigned int v36; // r15d
  struct BCRYPT_HASH_CTXT *v37; // r14
  unsigned int v38; // ecx
  unsigned int v39; // ecx
  unsigned int v40; // eax
  unsigned int v41; // edi
  struct BCRYPT_HASH_CTXT *v42; // rbx
  unsigned int v43; // r13d
  ULONG v44; // r14d
  __int64 v45; // r15
  unsigned int v46; // edx
  ULONG v47; // r8d
  unsigned int v48; // esi
  struct BCRYPT_HASH_CTXT *v49; // r14
  ULONG v50; // ebx
  __int64 v51; // r15
  int Hash; // [rsp+58h] [rbp-B0h]
  ULONG v53; // [rsp+58h] [rbp-B0h]
  unsigned int v54; // [rsp+5Ch] [rbp-ACh]
  ULONG v55; // [rsp+60h] [rbp-A8h]
  int v56; // [rsp+64h] [rbp-A4h]
  ULONG pcbResult[2]; // [rsp+68h] [rbp-A0h] BYREF
  BCRYPT_HANDLE *v58; // [rsp+70h] [rbp-98h]
  unsigned int v59[2]; // [rsp+78h] [rbp-90h] BYREF
  struct BCRYPT_HASH_CTXT *v60; // [rsp+80h] [rbp-88h]
  __int64 v61; // [rsp+88h] [rbp-80h]
  __int64 v62; // [rsp+90h] [rbp-78h]
  _BYTE *v63; // [rsp+98h] [rbp-70h]
  int v64[2]; // [rsp+A8h] [rbp-60h] BYREF
  ULONG cbInput; // [rsp+C8h] [rbp-40h]
  unsigned int v66; // [rsp+D4h] [rbp-34h]
  __int64 v67; // [rsp+D8h] [rbp-30h] BYREF
  unsigned int v68; // [rsp+E0h] [rbp-28h] BYREF
  unsigned int v69; // [rsp+E4h] [rbp-24h] BYREF
  __int64 (__fastcall *v70)(__int64, _QWORD, unsigned int *, __int64 *, unsigned int *); // [rsp+E8h] [rbp-20h]
  __int64 v71; // [rsp+F0h] [rbp-18h]
  int v72; // [rsp+F8h] [rbp-10h] BYREF
  UCHAR v73[28]; // [rsp+FCh] [rbp-Ch] BYREF
  UCHAR pbInputa[8]; // [rsp+118h] [rbp+10h] BYREF

  v11 = a8;
  v12 = a1;
  v60 = a1;
  v14 = a7;
  v61 = (__int64)a7;
  *(_DWORD *)pbInputa = a3;
  *(_QWORD *)v59 = a8;
  v63 = a11;
  if ( a4 < 0x40 || *(_WORD *)pbInput != 23117 )
    goto LABEL_73;
  v16 = *((unsigned int *)pbInput + 15);
  if ( (unsigned __int64)a4 - 64 < v16 || a4 - (unsigned int)v16 <= 0x108 || *(_DWORD *)&pbInput[v16] != 17744 )
  {
    v11 = *(unsigned int **)v59;
    v14 = (unsigned __int8 **)v61;
LABEL_73:
    if ( a11 )
      *a11 = 0;
    if ( a3 == a4 )
      return I_HashComputeMemoryHash<BCRYPT_HASH_CTXT>(v12, pbInput, a3, *v14, v11);
    else
      return 3221225485LL;
  }
  LODWORD(v17) = 0;
  while ( 1 )
  {
    LODWORD(v58) = v17;
    if ( (unsigned int)v17 >= a9 )
      break;
    v18 = (char *)v12 + 536 * (unsigned int)v17;
    pcbResult[0] = 0;
    v19 = *(void **)v18;
    v58 = (BCRYPT_HANDLE *)(v18 + 8);
    Hash = BCryptCreateHash(v19, (BCRYPT_HASH_HANDLE *)v18 + 1, (PUCHAR)v18 + 16, 0x200u, 0, 0, 0);
    v20 = Hash;
    if ( Hash < 0 )
      goto LABEL_12;
    Hash = BCryptGetProperty(*v58, L"HashDigestLength", (PUCHAR)v18 + 528, 4u, pcbResult, 0);
    v20 = Hash;
    if ( Hash < 0 )
    {
      BCryptDestroyHash(*v58);
      goto LABEL_15;
    }
    v21 = (_DWORD *)(*(_QWORD *)v59 + 4LL * (unsigned int)v17);
    if ( v21 )
    {
      LODWORD(v17) = v17 + 1;
      v12 = v60;
      *v21 = *((_DWORD *)v18 + 132);
    }
    else
    {
LABEL_12:
      if ( v20 < 0 )
        goto LABEL_15;
      v12 = v60;
      LODWORD(v17) = v17 + 1;
    }
  }
  memset_0(v64, 0, 0x50u);
  v72 = 0;
  v22 = 1;
  v56 = 1;
  memset(v73, 0, sizeof(v73));
  v59[0] = 1;
  Hash = HashpParsePEHeader(
           (char *)pbInput,
           *(unsigned int *)pbInputa,
           a4,
           0,
           BigFileHashMapViewOfFileCallbackPE,
           a6,
           0,
           (struct _HASHLIB_LOADED_IMAGE *)v64,
           (struct _EXCLUDE_RANGE *const)&v72,
           v59);
  v20 = Hash;
  if ( Hash < 0 )
    goto LABEL_15;
  v27 = cbInput;
  v28 = 0;
  v29 = v68;
  v55 = cbInput;
  while ( v22 < v59[0] )
  {
    if ( !v27 )
      goto LABEL_47;
    v30 = 8LL * v22;
    v31 = *(_DWORD *)&v73[v30 - 4];
    v62 = v30;
    if ( v31 >= v28 )
    {
      v32 = v31 - v28;
      if ( v31 - v28 >= v27 )
        v32 = v27;
      pcbResult[0] = v32;
      if ( v32 )
      {
        v33 = v28;
        v54 = v28;
        v34 = v32;
        if ( v28 > v66 )
          goto LABEL_36;
        v35 = v66 - v28;
        if ( v32 < v66 - v28 )
          v35 = v32;
        if ( !v35 )
          goto LABEL_36;
        if ( a9 )
        {
          v36 = 0;
          v37 = v60;
          do
            BCryptHashData(*((BCRYPT_HASH_HANDLE *)v37 + 67 * v36++ + 1), (PUCHAR)(v28 + *(_QWORD *)v64), v35, 0);
          while ( v36 < a9 );
          LODWORD(v17) = (_DWORD)v58;
          v32 = v34;
          v27 = v55;
          v29 = v68;
        }
        v33 = v35 + v28;
        v54 = v35 + v28;
        v34 -= v35;
        if ( v34 )
        {
LABEL_36:
          if ( v70 )
          {
            while ( 1 )
            {
              if ( v29 )
              {
                if ( v33 >= v69 )
                {
                  v46 = v33 - v69;
                  if ( v33 - v69 < v29 )
                  {
                    v47 = v34;
                    if ( v34 >= v29 - v46 )
                      v47 = v29 - v46;
                    v48 = 0;
                    v53 = v47;
                    if ( a9 )
                    {
                      v49 = v60;
                      v50 = v47;
                      v51 = v46;
                      do
                        BCryptHashData(*((BCRYPT_HASH_HANDLE *)v49 + 67 * v48++ + 1), (PUCHAR)(v51 + v67), v50, 0);
                      while ( v48 < a9 );
                      LODWORD(v17) = (_DWORD)v58;
                      v27 = v55;
                      v32 = pcbResult[0];
                      v29 = v68;
                      v33 = v54;
                      v47 = v53;
                    }
                    v34 -= v47;
                    if ( !v34 )
                      goto LABEL_38;
                    v33 += v47;
                    v54 = v33;
                  }
                }
              }
              Hash = v70(v71, v33, &v69, &v67, &v68);
              v20 = Hash;
              if ( Hash < 0 )
                goto LABEL_49;
              v29 = v68;
              v33 = v54;
            }
          }
          v20 = -1073741811;
          goto LABEL_48;
        }
LABEL_38:
        v27 -= v32;
        v28 += v32;
        v55 = v27;
        if ( !v27 )
        {
          v22 = v56;
          goto LABEL_45;
        }
        v30 = v62;
      }
      v22 = v56;
    }
    v38 = *(_DWORD *)&v73[v30] + *(_DWORD *)&v73[v30 - 4];
    if ( v38 >= v28 )
    {
      v39 = v38 - v28;
      v40 = v27;
      if ( v27 >= v39 )
        v40 = v39;
      v27 -= v40;
      v55 = v27;
      v28 += v40;
    }
LABEL_45:
    v56 = ++v22;
  }
  if ( !v27 )
  {
LABEL_47:
    v20 = 0;
LABEL_48:
    Hash = v20;
    goto LABEL_49;
  }
  v20 = HashpHashMappedBytes<BCRYPT_HASH_CTXT>((int)v60, a9, (int)v64, v28, v27);
  Hash = v20;
LABEL_49:
  if ( v20 >= 0 )
  {
    v41 = 0;
    if ( a9 )
    {
      v42 = v60;
      v43 = ((*(_DWORD *)pbInputa + 7) & 0xFFFFFFF8) - *(_DWORD *)pbInputa;
      do
      {
        v44 = v43;
        v45 = 536LL * v41;
        for ( *(_QWORD *)pbInputa = 0; v44 >= 8; v44 -= 8 )
          BCryptHashData(*(BCRYPT_HASH_HANDLE *)((char *)v42 + v45 + 8), pbInputa, 8u, 0);
        if ( v44 )
          BCryptHashData(*(BCRYPT_HASH_HANDLE *)((char *)v42 + v45 + 8), pbInputa, v44, 0);
        ++v41;
      }
      while ( v41 < a9 );
      LODWORD(v17) = (_DWORD)v58;
    }
    if ( v63 )
      *v63 = 1;
  }
LABEL_15:
  if ( (_DWORD)v17 )
  {
    v23 = v60;
    v24 = v61;
    do
    {
      v17 = (unsigned int)(v17 - 1);
      v25 = 536LL * (unsigned int)v17;
      BCryptFinishHash(
        *(BCRYPT_HASH_HANDLE *)((char *)v23 + v25 + 8),
        *(PUCHAR *)(v24 + 8 * v17),
        *(_DWORD *)((char *)v23 + v25 + 528),
        0);
      BCryptDestroyHash(*(BCRYPT_HASH_HANDLE *)((char *)v23 + v25 + 8));
    }
    while ( (_DWORD)v17 );
    return (unsigned int)Hash;
  }
  return (unsigned int)v20;
}

```

## disassembly

```asm
0x180016e50  mov     r11, rsp
0x180016e53  push    rbp
0x180016e54  push    rsi
0x180016e55  push    rdi
0x180016e56  push    r13
0x180016e58  push    r14
0x180016e5a  lea     rbp, [r11-68h]
0x180016e5e  sub     rsp, 140h
0x180016e65  mov     rax, cs:__security_cookie
0x180016e6c  xor     rax, rsp
0x180016e6f  mov     [rbp+60h+var_48], rax
0x180016e73  mov     rax, [rbp+60h+arg_38]
0x180016e7a  mov     r10, rcx
0x180016e7d  mov     r13, [rbp+60h+arg_50]
0x180016e84  mov     rdi, rdx
0x180016e87  mov     [rsp+160h+var_E8], rcx
0x180016e8c  mov     rcx, [rbp+60h+arg_30]
0x180016e93  mov     [rbp+60h+var_E0], rcx
0x180016e97  mov     r14d, r9d
0x180016e9a  mov     dword ptr [rbp+60h+pbInput], r8d
0x180016e9e  mov     qword ptr [rsp+160h+var_F0], rax
0x180016ea3  mov     [rbp+60h+var_D0], r13
0x180016ea7  cmp     r9d, 40h ; '@'
0x180016eab  jb      loc_18001735A
0x180016eb1  mov     edx, 5A4Dh
0x180016eb6  cmp     [rdi], dx
0x180016eb9  jnz     loc_18001735A
0x180016ebf  mov     ecx, [rdi+3Ch]
0x180016ec2  lea     rax, [r14-40h]
0x180016ec6  cmp     rax, rcx
0x180016ec9  jb      loc_180017351
0x180016ecf  mov     eax, r14d
0x180016ed2  sub     eax, ecx
0x180016ed4  cmp     eax, 108h
0x180016ed9  jbe     loc_180017351
0x180016edf  cmp     dword ptr [rcx+rdi], 4550h
0x180016ee6  jnz     loc_180017351
0x180016eec  mov     [r11-30h], rbx
0x180016ef0  xor     esi, esi
0x180016ef2  mov     [r11-38h], r12
0x180016ef6  mov     ebx, esi
0x180016ef8  mov     r12d, [rbp+60h+arg_40]
0x180016eff  mov     [r11-40h], r15
0x180016f03  mov     dword ptr [rsp+160h+var_F8], ebx
0x180016f07  cmp     ebx, r12d
0x180016f0a  jnb     loc_180016FD4
0x180016f10  mov     [rsp+160h+dwFlags], esi; dwFlags
0x180016f14  mov     r9d, 200h; cbHashObject
0x180016f1a  mov     r13d, ebx
0x180016f1d  imul    r15, r13, 218h
0x180016f24  mov     [rsp+160h+cbSecret], esi; cbSecret
0x180016f28  add     r15, r10
0x180016f2b  mov     [rsp+160h+pcbResult], esi
0x180016f2f  mov     [rsp+160h+pbSecret], rsi; pbSecret
0x180016f34  mov     rcx, [r15]; hAlgorithm
0x180016f37  lea     rax, [r15+8]
0x180016f3b  mov     rdx, rax; phHash
0x180016f3e  mov     [rsp+160h+var_F8], rax
0x180016f43  lea     r8, [r15+10h]; pbHashObject
0x180016f47  call    cs:__imp_BCryptCreateHash
0x180016f4d  mov     [rsp+160h+var_110], eax
0x180016f51  mov     esi, eax
0x180016f53  test    eax, eax
0x180016f55  js      short loc_180016FBE
0x180016f57  mov     rcx, [rsp+160h+var_F8]
0x180016f5c  lea     rax, [rsp+160h+pcbResult]
0x180016f61  mov     [rsp+160h+cbSecret], 0; dwFlags
0x180016f69  lea     r8, [r15+210h]; pbOutput
0x180016f70  mov     r9d, 4; cbOutput
0x180016f76  mov     [rsp+160h+pbSecret], rax; pcbResult
0x180016f7b  lea     rdx, pszProperty; "HashDigestLength"
0x180016f82  mov     rcx, [rcx]; hObject
0x180016f85  call    cs:__imp_BCryptGetProperty
0x180016f8b  mov     [rsp+160h+var_110], eax
0x180016f8f  mov     esi, eax
0x180016f91  test    eax, eax
0x180016f93  js      loc_1800173BE
0x180016f99  mov     rax, qword ptr [rsp+160h+var_F0]
0x180016f9e  lea     rcx, [rax+r13*4]
0x180016fa2  test    rcx, rcx
0x180016fa5  jz      short loc_180016FBE
0x180016fa7  mov     eax, [r15+210h]
0x180016fae  inc     ebx
0x180016fb0  mov     r10, [rsp+160h+var_E8]
0x180016fb5  xor     esi, esi
0x180016fb7  mov     [rcx], eax
0x180016fb9  jmp     loc_180016F03
0x180016fbe  test    esi, esi
0x180016fc0  js      loc_180017057
0x180016fc6  mov     r10, [rsp+160h+var_E8]
0x180016fcb  inc     ebx
0x180016fcd  xor     esi, esi
0x180016fcf  jmp     loc_180016F03
0x180016fd4  xor     edx, edx; Val
0x180016fd6  lea     rcx, [rbp+60h+var_C0]; void *
0x180016fda  mov     r8d, 50h ; 'P'; Size
0x180016fe0  call    memset_0
0x180016fe5  mov     edx, dword ptr [rbp+60h+pbInput]; unsigned int
0x180016fe8  lea     rax, [rsp+160h+var_F0]
0x180016fed  mov     [rsp+160h+var_118], rax; unsigned int *
0x180016ff2  xorps   xmm0, xmm0
0x180016ff5  lea     rax, [rbp+60h+var_70]
0x180016ff9  mov     [rbp+60h+var_70], esi
0x180016ffc  mov     [rsp+160h+var_120], rax; struct _EXCLUDE_RANGE *
0x180017001  mov     r15d, 1
0x180017007  lea     rax, [rbp+60h+var_C0]
0x18001700b  mov     [rsp+5Ch], r15d
0x180017010  mov     [rsp+160h+var_128], rax; struct _HASHLIB_LOADED_IMAGE *
0x180017015  xor     r9d, r9d; unsigned __int8
0x180017018  mov     rax, [rbp+60h+arg_28]
0x18001701f  mov     r8d, r14d; unsigned int
0x180017022  mov     qword ptr [rsp+160h+dwFlags], rsi; struct HASHLIB_CERT_INFO *
0x180017027  mov     rcx, rdi; void *
0x18001702a  mov     qword ptr [rsp+160h+cbSecret], rax; void *
0x18001702f  lea     rax, ?BigFileHashMapViewOfFileCallbackPE@@YAJPEAXKPEAKPEAPEAX1@Z; BigFileHashMapViewOfFileCallbackPE(void *,ulong,ulong *,void * *,ulong *)
0x180017036  movups  xmmword ptr [rbp+60h+var_6C], xmm0
0x18001703a  mov     [rsp+160h+pbSecret], rax; int (*)(void *, unsigned int, unsigned int *, void **, unsigned int *)
0x18001703f  movups  xmmword ptr [rbp+60h+var_6C+0Ch], xmm0
0x180017043  mov     [rsp+160h+var_F0], r15d
0x180017048  call    ?HashpParsePEHeader@@YAJPEBXKKEP6AJPEAXKPEAKPEAPEAX2@Z1PEAUHASHLIB_CERT_INFO@@PEAU_HASHLIB_LOADED_IMAGE@@QEAU_EXCLUDE_RANGE@@2@Z; HashpParsePEHeader(void const *,ulong,ulong,uchar,long (*)(void *,ulong,ulong *,void * *,ulong *),void *,HASHLIB_CERT_INFO *,_HASHLIB_LOADED_IMAGE *,_EXCLUDE_RANGE * const,ulong *)
0x18001704d  mov     [rsp+160h+var_110], eax
0x180017051  mov     esi, eax
0x180017053  test    eax, eax
0x180017055  jns     short loc_1800170D1
0x180017057  mov     r15, [rsp+160h+var_38]
0x18001705f  mov     r12, [rsp+160h+var_30]
0x180017067  test    ebx, ebx
0x180017069  jz      short loc_1800170AC
0x18001706b  mov     rsi, [rsp+160h+var_E8]
0x180017070  mov     r14, [rbp+60h+var_E0]
0x180017074  dec     ebx
0x180017076  xor     r9d, r9d; dwFlags
0x180017079  mov     edx, ebx
0x18001707b  imul    rdi, rdx, 218h
0x180017082  mov     rdx, [r14+rbx*8]; pbOutput
0x180017086  mov     r8d, [rdi+rsi+210h]; cbOutput
0x18001708e  mov     rcx, [rdi+rsi+8]; hHash
0x180017093  call    cs:__imp_BCryptFinishHash
0x180017099  mov     rcx, [rdi+rsi+8]; hHash
0x18001709e  call    cs:__imp_BCryptDestroyHash
0x1800170a4  test    ebx, ebx
0x1800170a6  jnz     short loc_180017074
0x1800170a8  mov     esi, [rsp+160h+var_110]
0x1800170ac  mov     rbx, [rsp+138h]
0x1800170b4  mov     eax, esi
0x1800170b6  mov     rcx, [rbp+60h+var_48]
0x1800170ba  xor     rcx, rsp; StackCookie
0x1800170bd  call    __security_check_cookie
0x1800170c2  add     rsp, 140h
0x1800170c9  pop     r14
0x1800170cb  pop     r13
0x1800170cd  pop     rdi
0x1800170ce  pop     rsi
0x1800170cf  pop     rbp
0x1800170d0  retn
0x1800170d1  mov     r14d, [rbp+60h+cbInput]
0x1800170d5  xor     edi, edi
0x1800170d7  mov     r9, [rbp+60h+var_88]
0x1800170db  mov     [rsp+160h+var_108], r14d
0x1800170e0  cmp     r15d, [rsp+160h+var_F0]
0x1800170e5  jnb     loc_180017205
0x1800170eb  test    r14d, r14d
0x1800170ee  jz      loc_18001720E
0x1800170f4  mov     eax, r15d
0x1800170f7  lea     rdx, ds:0[rax*8]
0x1800170ff  mov     eax, [rbp+rdx+60h+var_70]
0x180017103  mov     [rbp+60h+var_D8], rdx
0x180017107  cmp     eax, edi
0x180017109  jb      loc_1800171D7
0x18001710f  mov     r15d, eax
0x180017112  sub     r15d, edi
0x180017115  cmp     r15d, r14d
0x180017118  cmovnb  r15d, r14d
0x18001711c  mov     [rsp+160h+pcbResult], r15d
0x180017121  test    r15d, r15d
0x180017124  jz      loc_1800171D2
0x18001712a  mov     esi, [rbp+60h+var_94]
0x18001712d  mov     ecx, edi
0x18001712f  mov     [rsp+160h+var_10C], ecx
0x180017133  mov     r13d, r15d
0x180017136  cmp     edi, esi
0x180017138  ja      short loc_1800171A6
0x18001713a  sub     esi, edi
0x18001713c  cmp     r15d, esi
0x18001713f  cmovb   esi, r15d
0x180017143  test    esi, esi
0x180017145  jz      short loc_1800171A6
0x180017147  mov     [rsp+160h+var_10C], 0
0x18001714f  test    r12d, r12d
0x180017152  jz      short loc_18001719A
0x180017154  mov     r15d, [rsp+160h+var_10C]
0x180017159  mov     r14, [rsp+160h+var_E8]
0x18001715e  mov     ebx, edi
0x180017160  mov     rdx, qword ptr [rbp+60h+var_C0]
0x180017164  xor     r9d, r9d; dwFlags
0x180017167  mov     eax, r15d
0x18001716a  add     rdx, rbx; pbInput
0x18001716d  imul    rcx, rax, 218h
0x180017174  mov     r8d, esi; cbInput
0x180017177  mov     rcx, [rcx+r14+8]; hHash
0x18001717c  call    cs:__imp_BCryptHashData
0x180017182  inc     r15d
0x180017185  cmp     r15d, r12d
0x180017188  jb      short loc_180017160
0x18001718a  mov     ebx, dword ptr [rsp+160h+var_F8]
0x18001718e  mov     r15d, r13d
0x180017191  mov     r14d, [rsp+160h+var_108]
0x180017196  mov     r9, [rbp+60h+var_88]
0x18001719a  lea     ecx, [rsi+rdi]
0x18001719d  mov     [rsp+160h+var_10C], ecx
0x1800171a1  sub     r13d, esi
0x1800171a4  jz      short loc_1800171BA
0x1800171a6  cmp     [rbp+60h+var_80], 0
0x1800171ab  jz      loc_1800173D5
0x1800171b1  test    r13d, r13d
0x1800171b4  jnz     loc_18001727F
0x1800171ba  sub     r14d, r15d
0x1800171bd  add     edi, r15d
0x1800171c0  mov     [rsp+160h+var_108], r14d
0x1800171c5  test    r14d, r14d
0x1800171c8  jz      loc_18001739A
0x1800171ce  mov     rdx, [rbp+60h+var_D8]
0x1800171d2  mov     r15d, [rsp+5Ch]
0x1800171d7  mov     ecx, [rbp+rdx+60h+var_70]
0x1800171db  add     ecx, dword ptr [rbp+rdx+60h+var_6C]
0x1800171df  cmp     ecx, edi
0x1800171e1  jb      short loc_1800171F8
0x1800171e3  sub     ecx, edi
0x1800171e5  mov     eax, r14d
0x1800171e8  cmp     r14d, ecx
0x1800171eb  cmovnb  eax, ecx
0x1800171ee  sub     r14d, eax
0x1800171f1  mov     [rsp+160h+var_108], r14d
0x1800171f6  add     edi, eax
0x1800171f8  inc     r15d
0x1800171fb  mov     [rsp+5Ch], r15d
0x180017200  jmp     loc_1800170E0
0x180017205  test    r14d, r14d
0x180017208  jnz     loc_180017376
0x18001720e  xor     esi, esi
0x180017210  mov     [rsp+160h+var_110], esi
0x180017214  test    esi, esi
0x180017216  js      loc_180017057
0x18001721c  xor     edi, edi
0x18001721e  test    r12d, r12d
0x180017221  jz      short loc_180017268
0x180017223  mov     eax, dword ptr [rbp+60h+pbInput]
0x180017226  mov     rbx, [rsp+160h+var_E8]
0x18001722b  lea     r13d, [rax+7]
0x18001722f  and     r13d, 0FFFFFFF8h
0x180017233  sub     r13d, eax
0x180017236  mov     eax, edi
0x180017238  mov     r14d, r13d
0x18001723b  imul    r15, rax, 218h
0x180017242  mov     qword ptr [rbp+60h+pbInput], 0
0x18001724a  cmp     r13d, 8
0x18001724e  jnb     loc_1800173DF
0x180017254  test    r14d, r14d
0x180017257  jnz     loc_1800173A4
0x18001725d  inc     edi
0x18001725f  cmp     edi, r12d
0x180017262  jb      short loc_180017236
0x180017264  mov     ebx, dword ptr [rsp+160h+var_F8]
0x180017268  mov     r13, [rbp+60h+var_D0]
0x18001726c  test    r13, r13
0x18001726f  jz      loc_180017057
0x180017275  mov     byte ptr [r13+0], 1
0x18001727a  jmp     loc_180017057
0x18001727f  test    r9d, r9d
0x180017282  jz      loc_180017316
0x180017288  mov     rax, [rbp+60h+var_88+4]
0x18001728c  cmp     ecx, eax
0x18001728e  jb      loc_180017316
0x180017294  mov     edx, ecx
0x180017296  sub     edx, eax
0x180017298  cmp     edx, r9d
0x18001729b  jnb     short loc_180017316
0x18001729d  mov     eax, r9d
0x1800172a0  mov     r8d, r13d
0x1800172a3  sub     eax, edx
0x1800172a5  cmp     r13d, eax
0x1800172a8  cmovnb  r8d, eax
0x1800172ac  xor     esi, esi
0x1800172ae  mov     [rsp+160h+var_110], r8d
0x1800172b3  test    r12d, r12d
0x1800172b6  jz      short loc_180017306
0x1800172b8  mov     r14, [rsp+160h+var_E8]
0x1800172bd  mov     ebx, r8d
0x1800172c0  mov     r15d, edx
0x1800172c3  mov     rdx, [rbp+60h+var_90]
0x1800172c7  xor     r9d, r9d; dwFlags
0x1800172ca  mov     eax, esi
0x1800172cc  add     rdx, r15; pbInput
0x1800172cf  imul    rcx, rax, 218h
0x1800172d6  mov     r8d, ebx; cbInput
0x1800172d9  mov     rcx, [rcx+r14+8]; hHash
0x1800172de  call    cs:__imp_BCryptHashData
0x1800172e4  inc     esi
0x1800172e6  cmp     esi, r12d
0x1800172e9  jb      short loc_1800172C3
  ... truncated ...
```
