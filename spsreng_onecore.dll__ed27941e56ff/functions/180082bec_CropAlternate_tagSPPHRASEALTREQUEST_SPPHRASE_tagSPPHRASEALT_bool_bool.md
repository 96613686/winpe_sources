# CropAlternate(tagSPPHRASEALTREQUEST *,SPPHRASE *,tagSPPHRASEALT *,bool,bool *)

- ea: `0x180082bec`
- end: `0x180082fbc`
- name: `?CropAlternate@@YAJPEAUtagSPPHRASEALTREQUEST@@PEAUSPPHRASE@@PEAUtagSPPHRASEALT@@_NPEA_N@Z`
- size: `976`
- prototype: `__int64 __fastcall(struct tagSPPHRASEALTREQUEST *, struct SPPHRASE *, struct tagSPPHRASEALT *, bool, bool *)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x18007a314`

## callees

- `0x180002aac`
- `0x180002db8`
- `0x180004312`
- `0x18004c544`
- `0x180082bec`
- `0x180102010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180082f7b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180082f7b`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180082f0e`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180082f0e`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CropAlternate(
        struct tagSPPHRASEALTREQUEST *a1,
        struct SPPHRASE *a2,
        struct tagSPPHRASEALT *a3,
        char a4,
        bool *a5)
{
  __int64 ulStartElement; // r14
  ULONG ulCountOfElements; // esi
  char *v8; // r13
  int v9; // ebx
  unsigned int v10; // r12d
  unsigned int v11; // edi
  ULONG v12; // r10d
  ULONG ulAudioSizeBytes; // edi
  unsigned int i; // r11d
  __int64 v15; // r8
  __int64 v16; // r9
  ULONG v17; // edx
  int v18; // ecx
  unsigned int v19; // r8d
  char *v20; // rbx
  char *v21; // rdi
  char *v22; // rdx
  __int64 j; // r8
  const SPPHRASEREPLACEMENT *pReplacements; // rax
  unsigned int v25; // eax
  __int64 v26; // r9
  _QWORD *v27; // r8
  __int64 v28; // r11
  unsigned int v29; // ecx
  void *v30; // rdi
  ISpPhraseBuilder *v31; // rax
  __int64 v32; // rdx
  int v34; // [rsp+30h] [rbp-38h]
  LPVOID pv; // [rsp+40h] [rbp-28h] BYREF
  void *v36; // [rsp+48h] [rbp-20h] BYREF
  LPVOID ppv; // [rsp+50h] [rbp-18h] BYREF
  void *v38; // [rsp+58h] [rbp-10h] BYREF
  ULONG v40; // [rsp+B8h] [rbp+50h]

  ulStartElement = a1->ulStartElement;
  ulCountOfElements = a2->Rule.ulCountOfElements;
  ppv = 0;
  pv = 0;
  v36 = 0;
  v8 = 0;
  v38 = 0;
  v9 = ((__int64 (__fastcall *)(ISpPhraseBuilder *, LPVOID *))a3->pPhrase->lpVtbl->GetPhrase)(a3->pPhrase, &pv);
  if ( v9 < 0 )
    goto LABEL_38;
  v10 = *((_DWORD *)pv + 16);
  v11 = v10 - ulCountOfElements;
  v34 = v10 - ulCountOfElements + ulStartElement;
  if ( a4 )
  {
    if ( (_DWORD)ulStartElement )
      v12 = a2->pElements[(unsigned int)(ulStartElement - 1)].ulAudioStreamOffset
          + a2->pElements[(unsigned int)(ulStartElement - 1)].ulAudioSizeBytes;
    else
      v12 = 0;
    if ( (unsigned int)ulStartElement >= ulCountOfElements - 1 )
      ulAudioSizeBytes = a2->ulAudioSizeBytes;
    else
      ulAudioSizeBytes = a2->pElements[(unsigned int)(ulStartElement + 1)].ulAudioStreamOffset;
    for ( i = 0; i < v10; ++i )
    {
      v15 = 56LL * i;
      v16 = *((_QWORD *)pv + 13);
      *(_DWORD *)(v15 + v16 + 8) += *((_DWORD *)pv + 6) - LODWORD(a2->ullAudioStreamPosition);
      v17 = *(_DWORD *)(v15 + v16 + 8);
      if ( i == (_DWORD)ulStartElement && v17 < v12 )
      {
        v18 = *(_DWORD *)(v15 + v16 + 12);
        if ( v18 + v17 <= v12 )
          goto LABEL_37;
        *(_DWORD *)(v15 + v16 + 12) = v17 + v18 - v12;
        *(_DWORD *)(v15 + v16 + 8) = v12;
        v17 = v12;
      }
      if ( i == v34 && v17 + *(_DWORD *)(v15 + v16 + 12) > ulAudioSizeBytes )
      {
        if ( v17 >= ulAudioSizeBytes )
          goto LABEL_37;
        *(_DWORD *)(v15 + v16 + 12) = ulAudioSizeBytes - v17;
      }
    }
    v11 = v10 - ulCountOfElements;
  }
  if ( (unsigned int)ulStartElement >= v10 || v10 < ulCountOfElements )
  {
LABEL_37:
    *a5 = 0;
LABEL_38:
    v30 = v36;
    goto LABEL_39;
  }
  *a5 = 1;
  v9 = ReallocArrayVoid(&v36, 0x38u, v10, (struct CHeap *)&g_heap, 0);
  if ( v9 < 0 )
    goto LABEL_38;
  v19 = a2->cReplacements + *((_DWORD *)pv + 28);
  if ( v19 )
  {
    v9 = ReallocArrayVoid(&v38, 0x18u, v19, (struct CHeap *)&g_heap, 0);
    v8 = (char *)v38;
    if ( v9 < 0 )
      goto LABEL_38;
  }
  v40 = v11 + 1;
  v20 = (char *)v36;
  memcpy_0(v36, a2->pElements, 56 * ulStartElement);
  v21 = &v20[56 * ulStartElement];
  memcpy_0(v21, (const void *)(56 * ulStartElement + *((_QWORD *)pv + 13)), 56LL * v40);
  memcpy_0(
    &v21[56 * v40],
    &a2->pElements[ulStartElement + 1],
    56LL * (ulCountOfElements - (unsigned int)ulStartElement - 1));
  *((_QWORD *)pv + 3) = a2->ullAudioStreamPosition;
  *((_DWORD *)pv + 8) = a2->ulAudioSizeBytes;
  v22 = v8;
  for ( j = 0; (unsigned int)j < a2->cReplacements; v22 += 24 )
  {
    pReplacements = a2->pReplacements;
    *(_OWORD *)v22 = *(_OWORD *)&pReplacements[j].bDisplayAttributes;
    *((_QWORD *)v22 + 2) = *(_QWORD *)&pReplacements[j].ulFirstElement;
    v25 = *((_DWORD *)v22 + 4);
    if ( v25 > (unsigned int)ulStartElement )
      *((_DWORD *)v22 + 4) = v40 + v25 - 1;
    j = (unsigned int)(j + 1);
  }
  v26 = 0;
  v27 = pv;
  if ( *((_DWORD *)pv + 28) )
  {
    do
    {
      v28 = v27[15];
      v29 = *(_DWORD *)(v28 + 24 * v26 + 16);
      if ( v29 >= (unsigned int)ulStartElement && *(_DWORD *)(v28 + 24 * v26 + 20) + v29 <= v34 + 1 )
      {
        *(_OWORD *)v22 = *(_OWORD *)(v28 + 24 * v26);
        *((_QWORD *)v22 + 2) = *(_QWORD *)(v28 + 24 * v26 + 16);
        v22 += 24;
        v27 = pv;
      }
      v26 = (unsigned int)(v26 + 1);
    }
    while ( (unsigned int)v26 < *((_DWORD *)v27 + 28) );
  }
  v30 = v36;
  v27[13] = v36;
  *((_QWORD *)pv + 15) = v8;
  *((_DWORD *)pv + 16) = v10;
  *((_DWORD *)pv + 28) = -1431655765 * ((v22 - v8) >> 3);
  v9 = CoCreateInstance(&CLSID_SpPhraseBuilder, 0, 0x17u, &GUID_88a3342a_0bed_4834_922b_88d43173162f, &ppv);
  if ( v9 >= 0 )
  {
    v9 = (*(__int64 (__fastcall **)(LPVOID, LPVOID))(*(_QWORD *)ppv + 56LL))(ppv, pv);
    if ( v9 >= 0 )
    {
      ((void (__fastcall *)(ISpPhraseBuilder *))a3->pPhrase->lpVtbl->Release)(a3->pPhrase);
      v31 = (ISpPhraseBuilder *)ppv;
      ppv = 0;
      a3->pPhrase = v31;
      a3->ulStartElementInParent = ulStartElement;
      a3->cElementsInParent = a1->cElements;
      a3->cElementsInAlternate = v40;
    }
  }
LABEL_39:
  CoTaskMemFree(pv);
  CWinHeap::Free((CWinHeap *)&g_heap, v30);
  CWinHeap::Free((CWinHeap *)&g_heap, v8);
  ATL::CComPtrBase<ISpObjectToken>::~CComPtrBase<ISpObjectToken>(&ppv, v32);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x180082bec  mov     [rsp-40h+arg_18], r9b
0x180082bf1  mov     [rsp-40h+arg_10], r8
0x180082bf6  mov     [rsp-40h+arg_0], rcx
0x180082bfb  push    rbp
0x180082bfc  push    rbx
0x180082bfd  push    rsi
0x180082bfe  push    rdi
0x180082bff  push    r12
0x180082c01  push    r13
0x180082c03  push    r14
0x180082c05  push    r15
0x180082c07  mov     rbp, rsp
0x180082c0a  sub     rsp, 68h
0x180082c0e  mov     r15, rdx
0x180082c11  mov     r14d, [rcx]
0x180082c14  mov     esi, [rdx+40h]
0x180082c17  mov     [rbp+var_34], esi
0x180082c1a  xor     eax, eax
0x180082c1c  mov     [rbp+var_18], rax
0x180082c20  mov     [rbp+pv], rax
0x180082c24  mov     [rbp+var_20], rax
0x180082c28  mov     r13d, eax
0x180082c2b  mov     [rbp+var_10], rax
0x180082c2f  mov     rcx, [r8]
0x180082c32  mov     rax, [rcx]
0x180082c35  lea     rdx, [rbp+pv]
0x180082c39  mov     rax, [rax+18h]
0x180082c3d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180082c42  mov     ebx, eax
0x180082c44  test    eax, eax
0x180082c46  js      loc_180082F73
0x180082c4c  mov     rcx, [rbp+pv]
0x180082c50  mov     r12d, [rcx+40h]
0x180082c54  mov     [rbp+var_30], r12d
0x180082c58  mov     edi, r12d
0x180082c5b  sub     edi, esi
0x180082c5d  mov     [rbp+arg_8], edi
0x180082c60  lea     eax, [rdi+r14]
0x180082c64  mov     [rbp+var_38], eax
0x180082c67  cmp     [rbp+arg_18], r13b
0x180082c6b  jz      loc_180082D31
0x180082c71  test    r14d, r14d
0x180082c74  jz      short loc_180082C8E
0x180082c76  lea     ecx, [r14-1]
0x180082c7a  imul    rdx, rcx, 38h ; '8'
0x180082c7e  mov     rax, [r15+68h]
0x180082c82  mov     r10d, [rdx+rax+0Ch]
0x180082c87  add     r10d, [rdx+rax+8]
0x180082c8c  jmp     short loc_180082C91
0x180082c8e  xor     r10d, r10d
0x180082c91  lea     eax, [rsi-1]
0x180082c94  cmp     r14d, eax
0x180082c97  jnb     short loc_180082CAB
0x180082c99  lea     ecx, [r14+1]
0x180082c9d  imul    rdx, rcx, 38h ; '8'
0x180082ca1  mov     rax, [r15+68h]
0x180082ca5  mov     edi, [rdx+rax+8]
0x180082ca9  jmp     short loc_180082CAF
0x180082cab  mov     edi, [r15+20h]
0x180082caf  xor     r11d, r11d
0x180082cb2  test    r12d, r12d
0x180082cb5  jz      short loc_180082D2E
0x180082cb7  mov     eax, r11d
0x180082cba  imul    r8, rax, 38h ; '8'
0x180082cbe  mov     rax, [rbp+pv]
0x180082cc2  mov     r9, [rax+68h]
0x180082cc6  mov     eax, [rax+18h]
0x180082cc9  sub     eax, [r15+18h]
0x180082ccd  add     [r8+r9+8], eax
0x180082cd2  mov     edx, [r8+r9+8]
0x180082cd7  cmp     r11d, r14d
0x180082cda  jnz     short loc_180082D04
0x180082cdc  cmp     edx, r10d
0x180082cdf  jnb     short loc_180082D04
0x180082ce1  mov     ecx, [r8+r9+0Ch]
0x180082ce6  lea     eax, [rcx+rdx]
0x180082ce9  cmp     eax, r10d
0x180082cec  jbe     loc_180082F6C
0x180082cf2  sub     ecx, r10d
0x180082cf5  add     ecx, edx
0x180082cf7  mov     [r8+r9+0Ch], ecx
0x180082cfc  mov     [r8+r9+8], r10d
0x180082d01  mov     edx, r10d
0x180082d04  cmp     r11d, [rbp+var_38]
0x180082d08  jnz     short loc_180082D26
0x180082d0a  mov     ecx, [r8+r9+0Ch]
0x180082d0f  add     ecx, edx
0x180082d11  cmp     ecx, edi
0x180082d13  jbe     short loc_180082D26
0x180082d15  cmp     edx, edi
0x180082d17  jnb     loc_180082F6C
0x180082d1d  mov     eax, edi
0x180082d1f  sub     eax, edx
0x180082d21  mov     [r8+r9+0Ch], eax
0x180082d26  inc     r11d
0x180082d29  cmp     r11d, r12d
0x180082d2c  jb      short loc_180082CB7
0x180082d2e  mov     edi, [rbp+arg_8]
0x180082d31  cmp     r14d, r12d
0x180082d34  jnb     loc_180082F6C
0x180082d3a  cmp     r12d, esi
0x180082d3d  jb      loc_180082F6C
0x180082d43  mov     rax, [rbp+arg_20]
0x180082d47  mov     byte ptr [rax], 1
0x180082d4a  mov     byte ptr [rsp+68h+ppv], r13b; bool
0x180082d4f  lea     r9, ?g_heap@@3VCHeap@@A; struct CHeap *
0x180082d56  mov     r8d, r12d; unsigned int
0x180082d59  mov     edx, 38h ; '8'; unsigned __int64
0x180082d5e  lea     rcx, [rbp+var_20]; void **
0x180082d62  call    ?ReallocArrayVoid@@YAJPEAPEAX_KKPEAVCHeap@@_N@Z; ReallocArrayVoid(void * *,unsigned __int64,ulong,CHeap *,bool)
0x180082d67  mov     ebx, eax
0x180082d69  test    eax, eax
0x180082d6b  js      loc_180082F73
0x180082d71  mov     rax, [rbp+pv]
0x180082d75  mov     r8d, [rax+70h]
0x180082d79  add     r8d, [r15+70h]; unsigned int
0x180082d7d  jz      short loc_180082DA7
0x180082d7f  mov     byte ptr [rsp+68h+ppv], r13b; bool
0x180082d84  lea     r9, ?g_heap@@3VCHeap@@A; struct CHeap *
0x180082d8b  mov     edx, 18h; unsigned __int64
0x180082d90  lea     rcx, [rbp+var_10]; void **
0x180082d94  call    ?ReallocArrayVoid@@YAJPEAPEAX_KKPEAVCHeap@@_N@Z; ReallocArrayVoid(void * *,unsigned __int64,ulong,CHeap *,bool)
0x180082d99  mov     ebx, eax
0x180082d9b  mov     r13, [rbp+var_10]
0x180082d9f  test    eax, eax
0x180082da1  js      loc_180082F73
0x180082da7  lea     eax, [rdi+1]
0x180082daa  mov     [rbp+arg_8], eax
0x180082dad  imul    rsi, r14, 38h ; '8'
0x180082db1  mov     r8, rsi; Size
0x180082db4  mov     rdx, [r15+68h]; Src
0x180082db8  mov     rbx, [rbp+var_20]
0x180082dbc  mov     rcx, rbx; void *
0x180082dbf  call    memcpy_0
0x180082dc4  lea     rdi, [rsi+rbx]
0x180082dc8  mov     eax, [rbp+arg_8]
0x180082dcb  imul    rbx, rax, 38h ; '8'
0x180082dcf  mov     rax, [rbp+pv]
0x180082dd3  mov     rdx, [rax+68h]
0x180082dd7  add     rdx, rsi; Src
0x180082dda  mov     r8, rbx; Size
0x180082ddd  mov     rcx, rdi; void *
0x180082de0  call    memcpy_0
0x180082de5  mov     eax, [rbp+var_34]
0x180082de8  sub     eax, r14d
0x180082deb  dec     eax
0x180082ded  imul    r8, rax, 38h ; '8'; Size
0x180082df1  mov     rdx, [r15+68h]
0x180082df5  add     rdx, 38h ; '8'
0x180082df9  add     rdx, rsi; Src
0x180082dfc  lea     rcx, [rbx+rdi]; void *
0x180082e00  call    memcpy_0
0x180082e05  mov     rcx, [r15+18h]
0x180082e09  mov     rax, [rbp+pv]
0x180082e0d  mov     [rax+18h], rcx
0x180082e11  mov     ecx, [r15+20h]
0x180082e15  mov     rax, [rbp+pv]
0x180082e19  mov     [rax+20h], ecx
0x180082e1c  mov     rdx, r13
0x180082e1f  xor     r8d, r8d
0x180082e22  cmp     [r15+70h], r8d
0x180082e26  jbe     short loc_180082E63
0x180082e28  mov     r9d, [rbp+arg_8]
0x180082e2c  lea     rcx, [r8+r8*2]
0x180082e30  mov     rax, [r15+78h]
0x180082e34  movups  xmm0, xmmword ptr [rax+rcx*8]
0x180082e38  movups  xmmword ptr [rdx], xmm0
0x180082e3b  movsd   xmm1, qword ptr [rax+rcx*8+10h]
0x180082e41  movsd   qword ptr [rdx+10h], xmm1
0x180082e46  mov     eax, [rdx+10h]
0x180082e49  cmp     eax, r14d
0x180082e4c  jbe     short loc_180082E56
0x180082e4e  dec     eax
0x180082e50  add     eax, r9d
0x180082e53  mov     [rdx+10h], eax
0x180082e56  inc     r8d
0x180082e59  add     rdx, 18h
0x180082e5d  cmp     r8d, [r15+70h]
0x180082e61  jb      short loc_180082E2C
0x180082e63  xor     r9d, r9d
0x180082e66  mov     r8, [rbp+pv]
0x180082e6a  cmp     [r8+70h], r9d
0x180082e6e  jbe     short loc_180082EBD
0x180082e70  mov     r12d, [rbp+var_38]
0x180082e74  lea     r10, [r9+r9*2]
0x180082e78  mov     r11, [r8+78h]
0x180082e7c  mov     ecx, [r11+r10*8+10h]
0x180082e81  cmp     ecx, r14d
0x180082e84  jb      short loc_180082EB0
0x180082e86  add     ecx, [r11+r10*8+14h]
0x180082e8b  lea     eax, [r12+1]
0x180082e90  cmp     ecx, eax
0x180082e92  ja      short loc_180082EB0
0x180082e94  movups  xmm0, xmmword ptr [r11+r10*8]
0x180082e99  movups  xmmword ptr [rdx], xmm0
0x180082e9c  movsd   xmm1, qword ptr [r11+r10*8+10h]
0x180082ea3  movsd   qword ptr [rdx+10h], xmm1
0x180082ea8  add     rdx, 18h
0x180082eac  mov     r8, [rbp+pv]
0x180082eb0  inc     r9d
0x180082eb3  cmp     r9d, [r8+70h]
0x180082eb7  jb      short loc_180082E74
0x180082eb9  mov     r12d, [rbp+var_30]
0x180082ebd  mov     rdi, [rbp+var_20]
0x180082ec1  mov     [r8+68h], rdi
0x180082ec5  mov     rax, [rbp+pv]
0x180082ec9  mov     [rax+78h], r13
0x180082ecd  mov     rax, [rbp+pv]
0x180082ed1  mov     [rax+40h], r12d
0x180082ed5  sub     rdx, r13
0x180082ed8  sar     rdx, 3
0x180082edc  mov     rax, 0AAAAAAAAAAAAAAABh
0x180082ee6  imul    rdx, rax
0x180082eea  mov     rax, [rbp+pv]
0x180082eee  mov     [rax+70h], edx
0x180082ef1  lea     rax, [rbp+var_18]
0x180082ef5  mov     [rsp+68h+ppv], rax; ppv
0x180082efa  lea     r9, _GUID_88a3342a_0bed_4834_922b_88d43173162f; riid
0x180082f01  xor     edx, edx; pUnkOuter
0x180082f03  lea     r8d, [rdx+17h]; dwClsContext
0x180082f07  lea     rcx, CLSID_SpPhraseBuilder; rclsid
0x180082f0e  call    cs:__imp_CoCreateInstance
0x180082f14  mov     ebx, eax
0x180082f16  test    eax, eax
0x180082f18  js      short loc_180082F77
0x180082f1a  mov     rcx, [rbp+var_18]
0x180082f1e  mov     rax, [rcx]
0x180082f21  mov     rdx, [rbp+pv]
0x180082f25  mov     rax, [rax+38h]
0x180082f29  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180082f2e  mov     ebx, eax
0x180082f30  test    eax, eax
0x180082f32  js      short loc_180082F77
0x180082f34  mov     rsi, [rbp+arg_10]
0x180082f38  mov     rcx, [rsi]
0x180082f3b  mov     rax, [rcx]
0x180082f3e  mov     rax, [rax+10h]
0x180082f42  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180082f47  mov     rax, [rbp+var_18]
0x180082f4b  mov     [rbp+var_18], 0
0x180082f53  mov     [rsi], rax
0x180082f56  mov     [rsi+8], r14d
0x180082f5a  mov     rax, [rbp+arg_0]
0x180082f5e  mov     eax, [rax+4]
0x180082f61  mov     [rsi+0Ch], eax
0x180082f64  mov     eax, [rbp+arg_8]
0x180082f67  mov     [rsi+10h], eax
0x180082f6a  jmp     short loc_180082F77
0x180082f6c  mov     rax, [rbp+arg_20]
0x180082f70  mov     [rax], r13b
0x180082f73  mov     rdi, [rbp+var_20]
0x180082f77  mov     rcx, [rbp+pv]; pv
0x180082f7b  call    cs:__imp_CoTaskMemFree
0x180082f81  mov     rdx, rdi; void *
0x180082f84  lea     rcx, ?g_heap@@3VCHeap@@A; this
0x180082f8b  call    ?Free@CWinHeap@@QEAA_NPEAX@Z; CWinHeap::Free(void *)
0x180082f90  mov     rdx, r13; void *
0x180082f93  lea     rcx, ?g_heap@@3VCHeap@@A; this
0x180082f9a  call    ?Free@CWinHeap@@QEAA_NPEAX@Z; CWinHeap::Free(void *)
0x180082f9f  nop
0x180082fa0  lea     rcx, [rbp+var_18]
0x180082fa4  call    ??1?$CComPtrBase@UISpObjectToken@@@ATL@@QEAA@XZ; ATL::CComPtrBase<ISpObjectToken>::~CComPtrBase<ISpObjectToken>(void)
0x180082fa9  mov     eax, ebx
0x180082fab  add     rsp, 68h
0x180082faf  pop     r15
0x180082fb1  pop     r14
0x180082fb3  pop     r13
0x180082fb5  pop     r12
0x180082fb7  pop     rdi
0x180082fb8  pop     rsi
0x180082fb9  pop     rbx
0x180082fba  pop     rbp
0x180082fbb  retn
```
