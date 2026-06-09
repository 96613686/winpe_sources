# TSParseBuffers(_SecBuffer *,_SecBufferDesc *,uchar * *,ulong *,uchar * *,ulong *,ulong *,long *,uchar * *,ulong *)

- ea: `0x180004460`
- end: `0x180004aa9`
- name: `?TSParseBuffers@@YAJPEAU_SecBuffer@@PEAU_SecBufferDesc@@PEAPEAEPEAK233PEAJ23@Z`
- size: `1609`
- prototype: `__int64 __fastcall(struct _SecBuffer *, struct _SecBufferDesc *, unsigned __int8 **, unsigned int *, unsigned __int8 **, unsigned int *, unsigned int *, int *, unsigned __int8 **, unsigned int *)`
- caller_count: `2`
- callee_count: `7`
- tags: `loader_planting`

## callers

- `0x180001160`
- `0x180006650`

## callees

- `0x1800032c0`
- `0x180004460`
- `0x180005ed0`
- `0x1800062e0`
- `0x18000c1a4`
- `0x18001c63c`
- `0x18001d010`

## import_xrefs

- `MSASN1!ASN1_Decode` at `0x180004568`
- `MSASN1!ASN1_Decode` at `0x180004568`
- `MSASN1!ASN1_CreateDecoder` at `0x18000453c`
- `MSASN1!ASN1_CreateDecoder` at `0x180004796`
- `MSASN1!ASN1_CreateDecoder` at `0x18000453c`
- `MSASN1!ASN1_CreateDecoder` at `0x180004796`
- `MSASN1!ASN1_CreateModule` at `0x1800048fa`
- `MSASN1!ASN1_CreateModule` at `0x180004a97`
- `MSASN1!ASN1_CreateModule` at `0x1800048fa`
- `MSASN1!ASN1_CreateModule` at `0x180004a97`
- `MSASN1!ASN1_FreeDecoded` at `0x1800047ae`
- `MSASN1!ASN1_FreeDecoded` at `0x1800047ae`
- `MSASN1!ASN1_CloseDecoder` at `0x180004580`
- `MSASN1!ASN1_CloseDecoder` at `0x1800047be`
- `MSASN1!ASN1_CloseDecoder` at `0x180004580`
- `MSASN1!ASN1_CloseDecoder` at `0x1800047be`

## pseudocode

```c
__int64 __fastcall TSParseBuffers(
        struct _SecBuffer *a1,
        struct _SecBufferDesc *a2,
        unsigned __int8 **a3,
        unsigned int *a4,
        unsigned __int8 **a5,
        unsigned int *a6,
        unsigned int *a7,
        int *a8,
        unsigned __int8 **a9,
        unsigned int *a10)
{
  void **v10; // r13
  int v11; // edi
  void **v12; // r12
  void **v13; // r14
  int *v15; // r15
  unsigned int cbBuffer; // ebx
  void *pvBuffer; // rsi
  __int64 Module; // rax
  __int64 v19; // rdx
  __int64 v20; // rbx
  bool v21; // zf
  _QWORD *v22; // rax
  unsigned int v23; // edi
  unsigned __int64 v24; // rbx
  struct _SecBuffer *v25; // rsi
  __int64 v26; // rax
  unsigned int v27; // r14d
  __int64 *i; // rbx
  size_t v29; // rdi
  void *v30; // rsi
  __int64 v31; // rdi
  void *v32; // rcx
  unsigned int *v33; // r14
  size_t v34; // r15
  void *v35; // rsi
  size_t v36; // r8
  const void *v37; // rdx
  __int64 v38; // rax
  struct _SecBuffer *v40; // rax
  void *v41; // rax
  void *v42; // rax
  int v43; // eax
  unsigned int *v44; // rsi
  void *v45; // rax
  unsigned int *v46; // rsi
  void *v47; // rax
  __int64 v48; // [rsp+50h] [rbp-48h] BYREF
  __int64 v49; // [rsp+58h] [rbp-40h] BYREF
  __int64 v50; // [rsp+A8h] [rbp+10h] BYREF
  unsigned __int8 **v51; // [rsp+B0h] [rbp+18h]
  unsigned int *v52; // [rsp+B8h] [rbp+20h]

  v52 = a4;
  v51 = a3;
  v10 = (void **)a9;
  v11 = 0;
  v12 = (void **)a5;
  v13 = (void **)a3;
  v50 = 0;
  if ( !a2 && !a3 && !a5 && !a9 )
    return 3221225485LL;
  if ( !a1 )
    return 0;
  if ( a2 )
    *a2 = 0;
  if ( a3 )
    *a3 = 0;
  if ( v12 )
    *v12 = 0;
  v15 = a8;
  if ( a8 )
    *a8 = 0;
  if ( v10 )
    *v10 = 0;
  cbBuffer = a1->cbBuffer;
  pvBuffer = a1->pvBuffer;
  v48 = 0;
  if ( fTSSSPModuleStarted )
  {
    Module = TSSSP_Module;
  }
  else
  {
    fTSSSPModuleStarted = 1;
    Module = ASN1_CreateModule(
               0x10000,
               1024,
               4096,
               6,
               off_18001E1E0,
               off_18001E1B0,
               off_18001E180,
               qword_18001F2E8,
               1936946036);
    TSSSP_Module = Module;
  }
  if ( (unsigned int)ASN1_CreateDecoder(Module, &v48, 0, 0, 0) )
    goto LABEL_25;
  if ( (int)ASN1_Decode(v48, &v50, 3, 8, pvBuffer, cbBuffer) < 0 )
    v11 = -1073741823;
  if ( v48 )
    ASN1_CloseDecoder();
  if ( v11 < 0 )
    goto LABEL_25;
  v20 = v50;
  if ( !v50 )
    goto LABEL_25;
  LOBYTE(v19) = 0;
  v21 = *(_BYTE *)v50 >= 0;
  *a7 = *(_DWORD *)(v50 + 4);
  if ( !v21 && a2 )
  {
    v22 = *(_QWORD **)(v20 + 8);
    v23 = 0;
    if ( !v22 )
      goto LABEL_25;
    do
    {
      v22 = (_QWORD *)*v22;
      ++v23;
    }
    while ( v22 );
    if ( !v23 )
      goto LABEL_25;
    v24 = 16LL * v23;
    if ( v24 > 0xFFFFFFFF )
    {
      v11 = -1073741675;
      goto LABEL_85;
    }
    if ( TSGlobalState == 1 )
    {
      v25 = (struct _SecBuffer *)((__int64 (__fastcall *)(_QWORD, __int64))TSGlobalLsaFunctions->AllocatePrivateHeap)(
                                   (unsigned int)v24,
                                   v19);
    }
    else
    {
      v40 = (struct _SecBuffer *)((__int64 (__fastcall *)(_QWORD, __int64))TSGlobalDllFunctions->AllocateHeap)(
                                   (unsigned int)v24,
                                   v19);
      v25 = v40;
      if ( v40 )
      {
        memset_0(v40, 0, (unsigned int)v24);
        a2->pBuffers = v25;
LABEL_32:
        v26 = v50;
        v27 = 0;
        a2->cBuffers = v23;
        for ( i = *(__int64 **)(v26 + 8); i; i = (__int64 *)*i )
        {
          v29 = *((unsigned int *)i + 2);
          if ( TSGlobalState == 1 )
          {
            v30 = (void *)((__int64 (__fastcall *)(_QWORD))TSGlobalLsaFunctions->AllocatePrivateHeap)((unsigned int)v29);
          }
          else
          {
            v41 = (void *)((__int64 (__fastcall *)(_QWORD))TSGlobalDllFunctions->AllocateHeap)((unsigned int)v29);
            v30 = v41;
            if ( v41 )
              memset_0(v41, 0, v29);
          }
          v31 = v27;
          a2->pBuffers[v27].pvBuffer = v30;
          v32 = a2->pBuffers[v27].pvBuffer;
          if ( !v32 )
            goto LABEL_58;
          memcpy_0(v32, (const void *)i[2], *((unsigned int *)i + 2));
          ++v27;
          a2->pBuffers[v31].cbBuffer = *((_DWORD *)i + 2);
          a2->pBuffers[v31].BufferType = 2;
        }
        v20 = v50;
        v11 = 0;
        v13 = (void **)v51;
        LOBYTE(v19) = 1;
        goto LABEL_39;
      }
    }
    a2->pBuffers = v25;
    if ( !v25 )
    {
      v11 = -1073741670;
      goto LABEL_85;
    }
    goto LABEL_32;
  }
LABEL_39:
  if ( (*(_WORD *)v20 & 0x10) != 0 )
  {
    v43 = *(_DWORD *)(v20 + 48);
    if ( v43 < 0 )
    {
      *v15 = v43;
      goto LABEL_50;
    }
    goto LABEL_25;
  }
  if ( (*(_WORD *)v20 & 0x40) != 0 )
  {
    if ( v13 )
    {
      v44 = v52;
      if ( v52 )
      {
        v45 = TSAllocate(*(unsigned int *)(v20 + 16));
        *v13 = v45;
        if ( !v45 )
        {
          v11 = -1073741670;
          TSFreeSecBuffers(a2);
          goto LABEL_86;
        }
        *v44 = *(_DWORD *)(v20 + 16);
        memcpy_0(*v13, *(const void **)(v20 + 24), *(unsigned int *)(v20 + 16));
        v20 = v50;
        LOBYTE(v19) = 1;
      }
    }
  }
  if ( (*(_BYTE *)v20 & 0x20) != 0 )
  {
    if ( v12 )
    {
      v33 = a6;
      if ( a6 )
      {
        v34 = *(unsigned int *)(v20 + 32);
        if ( TSGlobalState == 1 )
        {
          v35 = (void *)((__int64 (__fastcall *)(_QWORD, __int64))TSGlobalLsaFunctions->AllocatePrivateHeap)(
                          (unsigned int)v34,
                          v19);
        }
        else
        {
          v42 = (void *)((__int64 (__fastcall *)(_QWORD, __int64))TSGlobalDllFunctions->AllocateHeap)(
                          (unsigned int)v34,
                          v19);
          v35 = v42;
          if ( v42 )
          {
            memset_0(v42, 0, v34);
            *v12 = v35;
LABEL_47:
            v36 = *(unsigned int *)(v20 + 32);
            v37 = *(const void **)(v20 + 40);
            *v33 = v36;
            memcpy_0(v35, v37, v36);
            v20 = v50;
            LOBYTE(v19) = 1;
            goto LABEL_48;
          }
        }
        *v12 = v35;
        if ( !v35 )
        {
LABEL_58:
          v13 = (void **)v51;
          v11 = -1073741670;
          goto LABEL_85;
        }
        goto LABEL_47;
      }
    }
  }
LABEL_48:
  if ( (*(_BYTE *)v20 & 8) == 0 || !v10 || (v46 = a10) == 0 )
  {
    if ( (_BYTE)v19 )
      goto LABEL_50;
    v13 = (void **)v51;
LABEL_25:
    v11 = -1073741811;
    goto LABEL_85;
  }
  v47 = TSAllocate(*(unsigned int *)(v20 + 56));
  *v10 = v47;
  if ( !v47 )
  {
    v13 = (void **)v51;
    v11 = -1073741670;
LABEL_85:
    TSFreeSecBuffers(a2);
    if ( !v13 )
    {
LABEL_88:
      if ( v12 && *v12 )
        TSFree(*v12);
      v20 = v50;
      goto LABEL_50;
    }
LABEL_86:
    if ( *v13 )
      TSFree(*v13);
    goto LABEL_88;
  }
  *v46 = *(_DWORD *)(v20 + 56);
  memcpy_0(*v10, *(const void **)(v20 + 64), *(unsigned int *)(v20 + 56));
  v20 = v50;
LABEL_50:
  if ( v20 )
  {
    v49 = 0;
    if ( fTSSSPModuleStarted )
    {
      v38 = TSSSP_Module;
    }
    else
    {
      fTSSSPModuleStarted = 1;
      v38 = ASN1_CreateModule(
              0x10000,
              1024,
              4096,
              6,
              off_18001E1E0,
              off_18001E1B0,
              off_18001E180,
              qword_18001F2E8,
              1936946036);
      TSSSP_Module = v38;
    }
    if ( !(unsigned int)ASN1_CreateDecoder(v38, &v49, 0, 0, 0) )
    {
      ASN1_FreeDecoded(v49, v20, 3);
      if ( v49 )
        ASN1_CloseDecoder();
    }
  }
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x180004460  mov     [rsp+arg_18], r9
0x180004465  mov     [rsp+arg_10], r8
0x18000446a  push    rbp
0x18000446b  push    rdi
0x18000446c  push    r12
0x18000446e  push    r13
0x180004470  push    r14
0x180004472  sub     rsp, 70h
0x180004476  mov     r13, [rsp+98h+arg_40]
0x18000447e  xor     edi, edi
0x180004480  mov     r12, [rsp+98h+arg_20]
0x180004488  mov     r14, r8
0x18000448b  mov     [rsp+98h+arg_8], rdi
0x180004493  mov     rbp, rdx
0x180004496  test    rdx, rdx
0x180004499  jz      loc_180004892
0x18000449f  test    rcx, rcx
0x1800044a2  jz      loc_1800048B7
0x1800044a8  mov     [rsp+98h+arg_0], rbx
0x1800044b0  mov     [rsp+98h+var_30], rsi
0x1800044b5  mov     [rsp+98h+var_38], r15
0x1800044ba  test    rbp, rbp
0x1800044bd  jz      short loc_1800044C5
0x1800044bf  xorps   xmm0, xmm0
0x1800044c2  movups  xmmword ptr [rdx], xmm0
0x1800044c5  test    r8, r8
0x1800044c8  jz      short loc_1800044CD
0x1800044ca  mov     [r8], rdi
0x1800044cd  test    r12, r12
0x1800044d0  jz      short loc_1800044D6
0x1800044d2  mov     [r12], rdi
0x1800044d6  mov     r15, [rsp+98h+arg_38]
0x1800044de  test    r15, r15
0x1800044e1  jz      short loc_1800044E6
0x1800044e3  mov     [r15], edi
0x1800044e6  test    r13, r13
0x1800044e9  jz      short loc_1800044EF
0x1800044eb  mov     [r13+0], rdi
0x1800044ef  cmp     cs:?fTSSSPModuleStarted@@3HA, edi; int fTSSSPModuleStarted
0x1800044f5  lea     rax, qword_18001F2E8
0x1800044fc  mov     ebx, [rcx]
0x1800044fe  lea     rdx, off_18001E1B0
0x180004505  mov     rsi, [rcx+8]
0x180004509  lea     r8, off_18001E1E0
0x180004510  lea     rcx, off_18001E180
0x180004517  mov     [rsp+98h+var_48], rdi
0x18000451c  jz      loc_1800048BE
0x180004522  mov     rax, cs:TSSSP_Module
0x180004529  xor     r9d, r9d
0x18000452c  mov     [rsp+98h+var_78], rdi
0x180004531  xor     r8d, r8d
0x180004534  lea     rdx, [rsp+98h+var_48]
0x180004539  mov     rcx, rax
0x18000453c  call    cs:__imp_ASN1_CreateDecoder
0x180004542  test    eax, eax
0x180004544  jnz     short loc_1800045C3
0x180004546  mov     rcx, [rsp+98h+var_48]
0x18000454b  lea     rdx, [rsp+98h+arg_8]
0x180004553  mov     dword ptr [rsp+98h+var_70], ebx
0x180004557  mov     r9d, 8
0x18000455d  mov     r8d, 3
0x180004563  mov     [rsp+98h+var_78], rsi
0x180004568  call    cs:__imp_ASN1_Decode
0x18000456e  test    eax, eax
0x180004570  js      loc_18000490C
0x180004576  mov     rcx, [rsp+98h+var_48]
0x18000457b  test    rcx, rcx
0x18000457e  jz      short loc_180004586
0x180004580  call    cs:__imp_ASN1_CloseDecoder
0x180004586  test    edi, edi
0x180004588  js      short loc_1800045C3
0x18000458a  mov     rbx, [rsp+98h+arg_8]
0x180004592  test    rbx, rbx
0x180004595  jz      short loc_1800045C3
0x180004597  mov     rax, [rsp+98h+arg_30]
0x18000459f  xor     dl, dl
0x1800045a1  test    byte ptr [rbx], 80h
0x1800045a4  mov     ecx, [rbx+4]
0x1800045a7  mov     [rax], ecx
0x1800045a9  jz      loc_1800046C3
0x1800045af  test    rbp, rbp
0x1800045b2  jz      loc_1800046C3
0x1800045b8  mov     rax, [rbx+8]
0x1800045bc  xor     edi, edi
0x1800045be  test    rax, rax
0x1800045c1  jnz     short loc_1800045D0
0x1800045c3  mov     edi, 0C000000Dh
0x1800045c8  jmp     loc_180004A05
0x1800045d0  mov     rax, [rax]
0x1800045d3  inc     edi
0x1800045d5  test    rax, rax
0x1800045d8  jnz     short loc_1800045D0
0x1800045da  test    edi, edi
0x1800045dc  jz      short loc_1800045C3
0x1800045de  mov     ebx, edi
0x1800045e0  mov     eax, 0FFFFFFFFh
0x1800045e5  shl     rbx, 4
0x1800045e9  cmp     rbx, rax
0x1800045ec  ja      loc_1800047E0
0x1800045f2  cmp     cs:?TSGlobalState@@3W4_TS_STATE@@A, 1; _TS_STATE TSGlobalState
0x1800045f9  jnz     loc_1800047FC
0x1800045ff  mov     rax, cs:?TSGlobalLsaFunctions@@3PEAU_LSA_SECPKG_FUNCTION_TABLE@@EA; _LSA_SECPKG_FUNCTION_TABLE * TSGlobalLsaFunctions
0x180004606  mov     ecx, ebx
0x180004608  mov     rax, [rax+180h]
0x18000460f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004614  mov     rsi, rax
0x180004617  mov     [rbp+8], rsi
0x18000461b  test    rsi, rsi
0x18000461e  jz      loc_180004916
0x180004624  mov     rax, [rsp+98h+arg_8]
0x18000462c  xor     r14d, r14d
0x18000462f  mov     [rbp+4], edi
0x180004632  mov     rbx, [rax+8]
0x180004636  test    rbx, rbx
0x180004639  jz      short loc_1800046AF
0x18000463b  cmp     cs:?TSGlobalState@@3W4_TS_STATE@@A, 1; _TS_STATE TSGlobalState
0x180004642  mov     edi, [rbx+8]
0x180004645  jnz     loc_18000482F
0x18000464b  mov     rax, cs:?TSGlobalLsaFunctions@@3PEAU_LSA_SECPKG_FUNCTION_TABLE@@EA; _LSA_SECPKG_FUNCTION_TABLE * TSGlobalLsaFunctions
0x180004652  mov     ecx, edi
0x180004654  mov     rax, [rax+180h]
0x18000465b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004660  mov     rsi, rax
0x180004663  mov     rax, [rbp+8]
0x180004667  mov     edi, r14d
0x18000466a  add     rdi, rdi
0x18000466d  mov     [rax+rdi*8+8], rsi
0x180004672  mov     rax, [rbp+8]
0x180004676  mov     rcx, [rax+rdi*8+8]; void *
0x18000467b  test    rcx, rcx
0x18000467e  jz      loc_1800047EA
0x180004684  mov     r8d, [rbx+8]; Size
0x180004688  mov     rdx, [rbx+10h]; Src
0x18000468c  call    memcpy_0
0x180004691  mov     eax, [rbx+8]
0x180004694  inc     r14d
0x180004697  mov     rcx, [rbp+8]
0x18000469b  mov     [rcx+rdi*8], eax
0x18000469e  mov     rax, [rbp+8]
0x1800046a2  mov     dword ptr [rax+rdi*8+4], 2
0x1800046aa  mov     rbx, [rbx]
0x1800046ad  jmp     short loc_180004636
0x1800046af  mov     rbx, [rsp+98h+arg_8]
0x1800046b7  xor     edi, edi
0x1800046b9  mov     r14, [rsp+98h+arg_10]
0x1800046c1  mov     dl, 1
0x1800046c3  movzx   eax, word ptr [rbx]
0x1800046c6  test    al, 10h
0x1800046c8  jnz     loc_180004920
0x1800046ce  test    al, 40h
0x1800046d0  jnz     loc_180004933
0x1800046d6  test    byte ptr [rbx], 20h
0x1800046d9  jz      short loc_180004741
0x1800046db  test    r12, r12
0x1800046de  jz      short loc_180004741
0x1800046e0  mov     r14, [rsp+98h+arg_28]
0x1800046e8  test    r14, r14
0x1800046eb  jz      short loc_180004741
0x1800046ed  cmp     cs:?TSGlobalState@@3W4_TS_STATE@@A, 1; _TS_STATE TSGlobalState
0x1800046f4  mov     r15d, [rbx+20h]
0x1800046f8  jnz     loc_18000485E
0x1800046fe  mov     rax, cs:?TSGlobalLsaFunctions@@3PEAU_LSA_SECPKG_FUNCTION_TABLE@@EA; _LSA_SECPKG_FUNCTION_TABLE * TSGlobalLsaFunctions
0x180004705  mov     ecx, r15d
0x180004708  mov     rax, [rax+180h]
0x18000470f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004714  mov     rsi, rax
0x180004717  mov     [r12], rsi
0x18000471b  test    rsi, rsi
0x18000471e  jz      loc_1800047EA
0x180004724  mov     r8d, [rbx+20h]; Size
0x180004728  mov     rcx, rsi; void *
0x18000472b  mov     rdx, [rbx+28h]; Src
0x18000472f  mov     [r14], r8d
0x180004732  call    memcpy_0
0x180004737  mov     rbx, [rsp+98h+arg_8]
0x18000473f  mov     dl, 1
0x180004741  test    byte ptr [rbx], 8
0x180004744  jnz     loc_180004993
0x18000474a  test    dl, dl
0x18000474c  jz      loc_1800049F0
0x180004752  test    edi, edi
0x180004754  js      loc_1800049FD
0x18000475a  mov     r15, [rsp+98h+var_38]
0x18000475f  test    rbx, rbx
0x180004762  jz      short loc_1800047C4
0x180004764  xor     esi, esi
0x180004766  mov     [rsp+98h+var_40], rsi
0x18000476b  test    rbx, rbx
0x18000476e  jz      short loc_1800047C4
0x180004770  cmp     cs:?fTSSSPModuleStarted@@3HA, esi; int fTSSSPModuleStarted
0x180004776  jz      loc_180004A3F
0x18000477c  mov     rax, cs:TSSSP_Module
0x180004783  xor     r9d, r9d
0x180004786  mov     [rsp+98h+var_78], rsi
0x18000478b  xor     r8d, r8d
0x18000478e  lea     rdx, [rsp+98h+var_40]
0x180004793  mov     rcx, rax
0x180004796  call    cs:__imp_ASN1_CreateDecoder
0x18000479c  test    eax, eax
0x18000479e  jnz     short loc_1800047C4
0x1800047a0  mov     rcx, [rsp+98h+var_40]
0x1800047a5  mov     r8d, 3
0x1800047ab  mov     rdx, rbx
0x1800047ae  call    cs:__imp_ASN1_FreeDecoded
0x1800047b4  mov     rcx, [rsp+98h+var_40]
0x1800047b9  test    rcx, rcx
0x1800047bc  jz      short loc_1800047C4
0x1800047be  call    cs:__imp_ASN1_CloseDecoder
0x1800047c4  mov     rsi, [rsp+98h+var_30]
0x1800047c9  mov     eax, edi
0x1800047cb  mov     rbx, [rsp+98h+arg_0]
0x1800047d3  add     rsp, 70h
0x1800047d7  pop     r14
0x1800047d9  pop     r13
0x1800047db  pop     r12
0x1800047dd  pop     rdi
0x1800047de  pop     rbp
0x1800047df  retn
0x1800047e0  mov     edi, 0C0000095h
0x1800047e5  jmp     loc_180004A05
0x1800047ea  mov     r14, [rsp+98h+arg_10]
0x1800047f2  mov     edi, 0C000009Ah
0x1800047f7  jmp     loc_180004A05
0x1800047fc  mov     rax, cs:?TSGlobalDllFunctions@@3PEAU_SECPKG_DLL_FUNCTIONS@@EA; _SECPKG_DLL_FUNCTIONS * TSGlobalDllFunctions
0x180004803  mov     ecx, ebx
0x180004805  mov     rax, [rax]
0x180004808  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000480d  mov     rsi, rax
0x180004810  test    rax, rax
0x180004813  jz      loc_180004617
0x180004819  mov     r8d, ebx; Size
0x18000481c  xor     edx, edx; Val
0x18000481e  mov     rcx, rax; void *
0x180004821  call    memset_0
0x180004826  mov     [rbp+8], rsi
0x18000482a  jmp     loc_180004624
0x18000482f  mov     rax, cs:?TSGlobalDllFunctions@@3PEAU_SECPKG_DLL_FUNCTIONS@@EA; _SECPKG_DLL_FUNCTIONS * TSGlobalDllFunctions
0x180004836  mov     ecx, edi
0x180004838  mov     rax, [rax]
0x18000483b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004840  mov     rsi, rax
0x180004843  test    rax, rax
0x180004846  jz      loc_180004663
0x18000484c  mov     r8, rdi; Size
0x18000484f  xor     edx, edx; Val
0x180004851  mov     rcx, rax; void *
0x180004854  call    memset_0
0x180004859  jmp     loc_180004663
0x18000485e  mov     rax, cs:?TSGlobalDllFunctions@@3PEAU_SECPKG_DLL_FUNCTIONS@@EA; _SECPKG_DLL_FUNCTIONS * TSGlobalDllFunctions
0x180004865  mov     ecx, r15d
0x180004868  mov     rax, [rax]
0x18000486b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004870  mov     rsi, rax
0x180004873  test    rax, rax
0x180004876  jz      loc_180004717
0x18000487c  mov     r8, r15; Size
0x18000487f  xor     edx, edx; Val
0x180004881  mov     rcx, rax; void *
0x180004884  call    memset_0
0x180004889  mov     [r12], rsi
0x18000488d  jmp     loc_180004724
0x180004892  test    r8, r8
0x180004895  jnz     loc_18000449F
0x18000489b  test    r12, r12
0x18000489e  jnz     loc_18000449F
0x1800048a4  test    r13, r13
0x1800048a7  jnz     loc_18000449F
0x1800048ad  mov     eax, 0C000000Dh
0x1800048b2  jmp     loc_1800047D3
0x1800048b7  xor     eax, eax
0x1800048b9  jmp     loc_1800047D3
0x1800048be  mov     [rsp+98h+var_58], 73737374h
0x1800048c6  mov     r9d, 6
0x1800048cc  mov     [rsp+98h+var_60], rax
0x1800048d1  mov     [rsp+98h+var_68], rcx
0x1800048d6  mov     ecx, 10000h
0x1800048db  mov     [rsp+98h+var_70], rdx
0x1800048e0  mov     edx, 400h
0x1800048e5  mov     [rsp+98h+var_78], r8
0x1800048ea  mov     r8d, 1000h
0x1800048f0  mov     cs:?fTSSSPModuleStarted@@3HA, 1; int fTSSSPModuleStarted
0x1800048fa  call    cs:__imp_ASN1_CreateModule
0x180004900  mov     cs:TSSSP_Module, rax
0x180004907  jmp     loc_180004529
0x18000490c  mov     edi, 0C0000001h
0x180004911  jmp     loc_180004576
0x180004916  mov     edi, 0C000009Ah
0x18000491b  jmp     loc_180004A05
0x180004920  mov     eax, [rbx+30h]
0x180004923  test    eax, eax
0x180004925  jns     loc_1800045C3
0x18000492b  mov     [r15], eax
0x18000492e  jmp     loc_180004752
0x180004933  test    r14, r14
0x180004936  jz      loc_1800046D6
0x18000493c  mov     rsi, [rsp+98h+arg_18]
0x180004944  test    rsi, rsi
0x180004947  jz      loc_1800046D6
0x18000494d  mov     ecx, [rbx+10h]; Size
0x180004950  call    ?TSAllocate@@YAPEAX_K@Z; TSAllocate(unsigned __int64)
  ... truncated ...
```
