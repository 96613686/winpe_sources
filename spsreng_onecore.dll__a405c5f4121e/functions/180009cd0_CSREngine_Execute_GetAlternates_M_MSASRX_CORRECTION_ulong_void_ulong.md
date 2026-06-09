# CSREngine::Execute_GetAlternates_M(MSASRX_CORRECTION *,ulong,void * *,ulong *)

- ea: `0x180009cd0`
- end: `0x18000a539`
- name: `?Execute_GetAlternates_M@CSREngine@@QEAAJPEAUMSASRX_CORRECTION@@KPEAPEAXPEAK@Z`
- size: `2153`
- prototype: `__int64 __fastcall(CSREngine *__hidden this, struct MSASRX_CORRECTION *, unsigned int, void **, unsigned int *)`
- caller_count: `2`
- callee_count: `21`
- tags: `file_ops, authz_impersonation, service_task, broker_com_uri`

## callers

- `0x18000ed20`
- `0x18000ef20`

## callees

- `0x180002470`
- `0x180002aac`
- `0x180002db8`
- `0x180002e00`
- `0x1800040b8`
- `0x180004312`
- `0x18000627c`
- `0x1800062a0`
- `0x180009cd0`
- `0x18000dbe0`
- `0x18001cc40`
- `0x18007a314`
- `0x18008221c`
- `0x180082800`
- `0x180082988`
- `0x180082fc4`
- `0x18008352c`
- `0x180083684`
- `0x180083a54`
- `0x1800b1690`
- `0x180102010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180009f59`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180009f82`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180009f9c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180009fd8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180009fe2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180009f59`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180009f82`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180009f9c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180009fd8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180009fe2`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180009db7`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180009db7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180009f03`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000a2a4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180009f03`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000a2a4`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180009f3c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180009f3c`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180009d63`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180009d63`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CSREngine::Execute_GetAlternates_M(
        CSREngine *this,
        struct MSASRX_CORRECTION *a2,
        ULONG a3,
        void **a4,
        unsigned int *a5)
{
  struct LATTICE_NODE **v7; // rdi
  unsigned int v8; // r15d
  struct tagSPPHRASEALT *v9; // r12
  CPhoneDecoder *v10; // r14
  char *pvResultExtra; // r13
  HRESULT AlternatePhraseTemplate; // esi
  LPVOID v13; // rcx
  __int64 v14; // rbx
  __int64 v15; // rcx
  __int64 v16; // rcx
  struct tagSPPHRASEALT *v17; // rax
  __int64 k; // rbx
  LPVOID *v19; // r12
  __int64 m; // rbx
  struct SPPHRASE *v22; // rdx
  struct SPPHRASE *v23; // r8
  char *v24; // rax
  struct CRecentReco *RecentReco; // rax
  struct CRecentReco *v26; // rbx
  char *v27; // rdx
  unsigned int v28; // eax
  __int64 i; // rdi
  ISpPhraseBuilder *pPhrase; // rcx
  _DWORD *v31; // rax
  ULONG *v32; // rcx
  unsigned int v33; // r14d
  const void **v34; // r13
  _DWORD *v35; // rbx
  ULONG *v36; // rbx
  __int64 v37; // rdi
  unsigned int v38; // eax
  unsigned int v39; // r8d
  unsigned int v40; // r13d
  unsigned __int16 v41; // r10
  int v42; // r11d
  int v43; // edi
  int v44; // ebx
  ULONG v45; // ecx
  __int64 j; // rdx
  unsigned int v47; // eax
  int v48; // r8d
  struct LATTICE_NODE *v49; // rcx
  __int64 v50; // r10
  __int64 v51; // rdi
  unsigned int v52; // ecx
  unsigned int v53; // [rsp+30h] [rbp-D8h]
  HRESULT v54; // [rsp+68h] [rbp-A0h]
  int v55; // [rsp+68h] [rbp-A0h]
  struct LATTICE_NODE **v56; // [rsp+70h] [rbp-98h] BYREF
  unsigned int v57; // [rsp+78h] [rbp-90h] BYREF
  unsigned int v58; // [rsp+7Ch] [rbp-8Ch]
  int v59; // [rsp+80h] [rbp-88h]
  unsigned int v60; // [rsp+84h] [rbp-84h]
  unsigned int v61; // [rsp+88h] [rbp-80h]
  unsigned int v62[2]; // [rsp+90h] [rbp-78h]
  void *v63; // [rsp+98h] [rbp-70h]
  LPVOID pv; // [rsp+A0h] [rbp-68h] BYREF
  void *v65; // [rsp+A8h] [rbp-60h] BYREF
  LPVOID ppv; // [rsp+B0h] [rbp-58h] BYREF
  ULONG v67; // [rsp+B8h] [rbp-50h]
  ULONG v68; // [rsp+BCh] [rbp-4Ch]
  struct CRecentReco *v69; // [rsp+C0h] [rbp-48h]
  unsigned int v70[2]; // [rsp+C8h] [rbp-40h]
  struct SPPHRASE *v71; // [rsp+D0h] [rbp-38h] BYREF
  CPhoneDecoder *v72; // [rsp+D8h] [rbp-30h]
  ISpPhrase *v73; // [rsp+E0h] [rbp-28h]
  struct tagSPPHRASEALTREQUEST v74; // [rsp+E8h] [rbp-20h] BYREF
  struct tagSPPHRASEALT *v75; // [rsp+118h] [rbp+10h]
  struct _GUID v76; // [rsp+128h] [rbp+20h] BYREF
  _BYTE v77[256]; // [rsp+138h] [rbp+30h] BYREF
  unsigned int v79; // [rsp+250h] [rbp+148h] BYREF
  ULONG v80; // [rsp+258h] [rbp+150h]
  void **v81; // [rsp+260h] [rbp+158h]

  v81 = a4;
  v80 = a3;
  v7 = 0;
  v8 = 0;
  v79 = 0;
  memset_0(v77, 0, 0xB8u);
  v57 = 0;
  *(_QWORD *)&v74.ulRequestAltCount = 0;
  memset(&v74.cbResultExtra + 1, 0, 20);
  v73 = 0;
  v9 = 0;
  v63 = 0;
  v10 = 0;
  v72 = 0;
  pv = 0;
  v71 = 0;
  v65 = 0;
  v56 = 0;
  EnterCriticalSection((LPCRITICAL_SECTION)(*(_QWORD *)(*((_QWORD *)this + 17) + 64LL) + 600LL));
  v67 = *((_DWORD *)a2 + 1);
  v74.ulStartElement = v67;
  v68 = *((_DWORD *)a2 + 2);
  v74.cElements = v68;
  v60 = *((_DWORD *)a2 + 3);
  v80 = *((_DWORD *)a2 + 4);
  v74.cbResultExtra = v80;
  pvResultExtra = (char *)a2 + 20;
  v74.pvResultExtra = (char *)a2 + 20;
  ppv = 0;
  AlternatePhraseTemplate = CoCreateInstance(
                              &CLSID_SpPhraseBuilder,
                              0,
                              0x17u,
                              &GUID_88a3342a_0bed_4834_922b_88d43173162f,
                              &ppv);
  if ( AlternatePhraseTemplate >= 0 )
  {
    AlternatePhraseTemplate = (*(__int64 (__fastcall **)(LPVOID, char *))(*(_QWORD *)ppv + 64LL))(
                                ppv,
                                (char *)a2 + ((v80 + 7) & 0xFFFFFFF8) + 20);
    if ( AlternatePhraseTemplate >= 0 )
    {
      v13 = ppv;
      v73 = (ISpPhrase *)ppv;
      ppv = 0;
      v74.pPhrase = v73;
      v14 = v60;
      if ( v60 > 0x400 )
        v14 = 1024;
      v60 = v14;
      v74.ulRequestAltCount = v14;
      AlternatePhraseTemplate = (*(__int64 (__fastcall **)(LPVOID, LPVOID *))(*(_QWORD *)v13 + 24LL))(v13, &pv);
      if ( AlternatePhraseTemplate >= 0 )
      {
        if ( *((_DWORD *)pv + 16) && *((_QWORD *)pv + 13) )
        {
          AlternatePhraseTemplate = MakeAlternatePhraseTemplate(&v74, &v71);
          if ( AlternatePhraseTemplate < 0 )
            goto LABEL_22;
          if ( (pvResultExtra[64] & 1) != 0 )
          {
            v15 = *(_QWORD *)(*((_QWORD *)this + 17) + 64LL);
            if ( *(_QWORD *)(pvResultExtra + 76) != *(_QWORD *)(v15 + 560)
              || *(_QWORD *)(pvResultExtra + 84) != *(_QWORD *)(v15 + 568) )
            {
              AlternatePhraseTemplate = -2147418113;
              goto LABEL_22;
            }
          }
          ReconstructInternalPointers((struct LATTICE *)v77, (struct LATTICE_HEADER *)pvResultExtra);
          AlternatePhraseTemplate = BuildElementArrays((int **)&v65, &v56, &v57, (struct LATTICE *)v77);
          if ( AlternatePhraseTemplate < 0 )
            goto LABEL_21;
          LOBYTE(v80) = 0;
          v16 = 0;
          if ( v57 )
          {
            while ( *((_DWORD *)v65 + v16) == (_DWORD)v16 )
            {
              v16 = (unsigned int)(v16 + 1);
              if ( (unsigned int)v16 >= v57 )
                goto LABEL_19;
            }
            LOBYTE(v80) = 1;
          }
LABEL_19:
          v17 = (struct tagSPPHRASEALT *)CoTaskMemAlloc(40 * v14);
          v9 = v17;
          v75 = v17;
          if ( !v17 )
          {
LABEL_20:
            AlternatePhraseTemplate = -2147024882;
LABEL_21:
            v7 = v56;
            goto LABEL_22;
          }
          memset_0(v17, 0, 40 * v14);
          AlternatePhraseTemplate = AddOriginalPhraseAlternate(&v74, v22, v9, &v79);
          v8 = v79;
          if ( AlternatePhraseTemplate < 0 )
            goto LABEL_21;
          if ( v79 == (_DWORD)v14 )
            goto LABEL_98;
          v7 = v56;
          if ( byte_180150A4A )
          {
            AlternatePhraseTemplate = CDecoder::GetAlternatesForAnalyzer(
                                        *(CDecoder **)(*((_QWORD *)this + 17) + 64LL),
                                        &v74,
                                        v23,
                                        v71,
                                        v9,
                                        &v79,
                                        (struct LATTICE_HEADER *)pvResultExtra,
                                        (int *)v65,
                                        v56,
                                        v57);
            v8 = v79;
            if ( AlternatePhraseTemplate < 0 )
              goto LABEL_22;
            if ( v79 == (_DWORD)v14 )
              goto LABEL_98;
          }
          if ( !byte_180150A4B || (pvResultExtra[64] & 1) != 0 )
          {
LABEL_98:
            if ( byte_180150A51 )
            {
              AlternatePhraseTemplate = EnforceAlternateBoundaries(&v74, v9, v8);
              if ( AlternatePhraseTemplate < 0 )
                goto LABEL_21;
            }
            v76 = (struct _GUID)*((_OWORD *)pvResultExtra + 1);
            RecentReco = CHistory::FindRecentReco(*((CHistory **)this + 119), &v76);
            v26 = RecentReco;
            v69 = RecentReco;
            if ( RecentReco )
              RecentReco = (struct CRecentReco *)*((_QWORD *)RecentReco + 5);
            AlternatePhraseTemplate = AttachAltExtraData(&v74, v9, v8, (int *)v65, v57, v53, RecentReco);
            v54 = AlternatePhraseTemplate;
            if ( AlternatePhraseTemplate < 0 )
              goto LABEL_21;
            if ( v8 )
            {
              v27 = (char *)CWinHeap::Alloc(*((void ***)this + 16), 8LL * v8, 1u);
              v63 = v27;
            }
            else
            {
              v27 = (char *)v63;
            }
            v28 = 16 * v8 + 8;
            v61 = v28;
            for ( i = 0; (unsigned int)i < v8; v27 = (char *)v63 )
            {
              *(_QWORD *)v62 = 5 * i;
              pPhrase = v9[i].pPhrase;
              *(_QWORD *)v70 = &v27[8 * i];
              AlternatePhraseTemplate = ((__int64 (__fastcall *)(ISpPhraseBuilder *))pPhrase->lpVtbl->GetSerializedPhrase)(pPhrase);
              v54 = AlternatePhraseTemplate;
              if ( AlternatePhraseTemplate < 0 )
                goto LABEL_21;
              v28 = ((*(&v9->cbAltExtra + 2 * *(_QWORD *)v62) + 7) & 0xFFFFFFF8)
                  + ((***(_DWORD ***)v70 + 7) & 0xFFFFFFF8)
                  + v61;
              v61 = v28;
              i = (unsigned int)(i + 1);
            }
            v31 = CoTaskMemAlloc(v28);
            *(_QWORD *)&v76.Data1 = v31;
            if ( v31 )
            {
              *v31 = v8;
              v32 = v31 + 2;
              v58 = 0;
              if ( v8 )
              {
                v33 = v58;
                v34 = (const void **)v63;
                do
                {
                  *(_QWORD *)v62 = 5LL * v33;
                  *v32 = v9[v33].ulStartElementInParent;
                  v32[1] = v9[v33].cElementsInParent;
                  v32[2] = v9[v33].cElementsInAlternate;
                  v32[3] = v9[v33].cbAltExtra;
                  v35 = v32 + 4;
                  memcpy_0(v32 + 4, v34[v33], *(unsigned int *)v34[v33]);
                  v36 = (_DWORD *)((char *)v35 + ((*(_DWORD *)v34[v33] + 7) & 0xFFFFFFF8));
                  v37 = *(_QWORD *)v62;
                  v38 = *(&v9->cbAltExtra + 2 * *(_QWORD *)v62);
                  v32 = v36;
                  if ( v38 )
                  {
                    memcpy_0(v36, *((const void **)&v9->pvAltExtra + *(_QWORD *)v62), v38);
                    v32 = (ULONG *)((char *)v36 + ((*(&v9->cbAltExtra + 2 * v37) + 7) & 0xFFFFFFF8));
                  }
                  ++v33;
                }
                while ( v33 < v8 );
                AlternatePhraseTemplate = v54;
                v10 = v72;
                pvResultExtra = (char *)v74.pvResultExtra;
                v26 = v69;
              }
              v39 = *((_DWORD *)pvResultExtra + 4);
              LODWORD(v69) = v39;
              v62[0] = *((_DWORD *)pvResultExtra + 9);
              v70[0] = *((_DWORD *)pvResultExtra + 13);
              if ( v26 )
              {
                v40 = 0;
                do
                {
                  v40 += *((_DWORD *)v26 + 18);
                  v26 = (struct CRecentReco *)*((_QWORD *)v26 + 3);
                }
                while ( v26 );
              }
              else
              {
                v40 = -1;
              }
              v58 = v40;
              v41 = 0;
              v59 = 0;
              v42 = 0;
              v43 = 0;
              v55 = 0;
              v44 = 0;
              v45 = 0;
              if ( !(_BYTE)v80 )
              {
                v80 = v57;
                for ( j = 0; ; j = (unsigned int)(j + 1) )
                {
                  v47 = v57;
                  if ( v57 > 0x10 )
                    v47 = 16;
                  if ( (unsigned int)j >= v47 )
                    break;
                  v48 = 1 << (15 - j);
                  if ( (unsigned int)j >= v67 && (unsigned int)j < v68 + v67 )
                    v44 |= v48;
                  v49 = v56[j];
                  if ( (*((_BYTE *)v49 + 8) & 0x10) != 0 )
                  {
                    v43 |= v48;
                    v55 = v43;
                  }
                  if ( (*((_DWORD *)v49 + 2) & 0x200) != 0 )
                    v42 |= v48;
                  if ( *((_DWORD *)pv + 28) )
                  {
                    v50 = 0;
                    v51 = *((_QWORD *)pv + 15);
                    while ( 1 )
                    {
                      v52 = *(_DWORD *)(v51 + 24 * v50 + 16);
                      if ( (unsigned int)j >= v52 && (unsigned int)j < *(_DWORD *)(v51 + 24 * v50 + 20) + v52 )
                        break;
                      v50 = (unsigned int)(v50 + 1);
                      if ( (unsigned int)v50 >= *((_DWORD *)pv + 28) )
                      {
                        v41 = v59;
                        goto LABEL_90;
                      }
                    }
                    v41 = v48 | v59;
                    v59 |= v48;
LABEL_90:
                    v43 = v55;
                  }
                }
                v10 = v72;
                v8 = v79;
                v9 = v75;
                v40 = v58;
                v45 = v80;
                v39 = (unsigned int)v69;
              }
              CSREngine::LogSQMEvent(
                this,
                0x73Du,
                9u,
                v39,
                v62[0],
                v70[0],
                v40,
                (unsigned __int16)v43 | (v44 << 16),
                v41 | (v42 << 16),
                v45 << 16,
                (unsigned __int16)v8 | (v60 << 16),
                3u);
              *a5 = v61;
              *v81 = *(void **)&v76.Data1;
              goto LABEL_21;
            }
            goto LABEL_20;
          }
          v24 = (char *)CAllocOnSpecificHeapBase::operator_new(0x110u, *((struct CHeap **)this + 16), 0);
          v10 = (CPhoneDecoder *)v24;
          if ( v24 )
          {
            *((_QWORD *)v24 + 5) = &g_heap;
            *((_QWORD *)v24 + 7) = 0;
            *((_QWORD *)v24 + 10) = 0;
            *((_QWORD *)v24 + 6) = 0;
            *((_DWORD *)v24 + 16) = 0;
            *(_QWORD *)(v24 + 68) = 1;
            *((_QWORD *)v24 + 4) = &CPhoneMatchHash::`vftable';
            *((_QWORD *)v24 + 11) = 0;
            *((_QWORD *)v24 + 13) = 0;
            *((_QWORD *)v24 + 12) = 0;
            *((_QWORD *)v24 + 14) = 64;
            *((_QWORD *)v24 + 15) = 0;
            *((_DWORD *)v24 + 32) = 1;
            *((_QWORD *)v24 + 25) = 0;
            AlternatePhraseTemplate = -2147467263;
          }
          else
          {
            AlternatePhraseTemplate = -2147024882;
            v10 = 0;
          }
        }
        else
        {
          AlternatePhraseTemplate = -2147024809;
        }
      }
    }
  }
LABEL_22:
  LeaveCriticalSection((LPCRITICAL_SECTION)(*(_QWORD *)(*((_QWORD *)this + 17) + 64LL) + 600LL));
  if ( v73 )
    ((void (__fastcall *)(ISpPhrase *))v73->lpVtbl->Release)(v73);
  CoTaskMemFree(0);
  if ( v9 )
  {
    for ( k = 0; (unsigned int)k < v8; k = (unsigned int)(k + 1) )
      FreeAlternate(&v9[k]);
    CoTaskMemFree(v9);
  }
  v19 = (LPVOID *)v63;
  if ( v63 )
  {
    for ( m = 0; (unsigned int)m < v8; m = (unsigned int)(m + 1) )
      CoTaskMemFree(v19[m]);
    CWinHeap::Free(*((CWinHeap **)this + 16), v19);
  }
  if ( v10 )
  {
    CPhoneDecoder::~CPhoneDecoder(v10);
    CAllocOnSpecificHeapBase::operator_delete(v10);
  }
  CoTaskMemFree(pv);
  CoTaskMemFree(v71);
  if ( v65 )
    operator delete(v65);
  if ( v7 )
    operator delete(v7);
  ATL::CComPtrBase<ISpObjectToken>::~CComPtrBase<ISpObjectToken>(&ppv);
  return (unsigned int)AlternatePhraseTemplate;
}

```

## disassembly

```asm
0x180009cd0  mov     rax, rsp
0x180009cd3  mov     [rax+20h], r9
0x180009cd7  mov     [rax+18h], r8d
0x180009cdb  mov     [rax+8], rcx
0x180009cdf  push    rbp
0x180009ce0  push    rbx
0x180009ce1  push    rsi
0x180009ce2  push    rdi
0x180009ce3  push    r12
0x180009ce5  push    r13
0x180009ce7  push    r14
0x180009ce9  push    r15
0x180009ceb  lea     rbp, [rax-138h]
0x180009cf2  sub     rsp, 1F8h
0x180009cf9  mov     rbx, rdx
0x180009cfc  mov     rsi, rcx
0x180009cff  xor     edi, edi
0x180009d01  mov     r15d, edi
0x180009d04  mov     [rbp+130h+arg_8], edi
0x180009d0a  xor     edx, edx; Val
0x180009d0c  mov     r8d, 0B8h; Size
0x180009d12  lea     rcx, [rbp+130h+var_100]; void *
0x180009d16  call    memset_0
0x180009d1b  mov     [rsp+230h+var_1C0], edi
0x180009d1f  mov     qword ptr [rbp+130h+var_150.ulRequestAltCount], rdi
0x180009d23  xorps   xmm0, xmm0
0x180009d26  movdqu  xmmword ptr [rbp+130h+var_150+1Ch], xmm0
0x180009d2b  mov     dword ptr [rbp+130h+var_150.pRecoContext+4], edi
0x180009d2e  mov     [rbp+130h+var_158], rdi
0x180009d32  mov     r12d, edi
0x180009d35  mov     [rbp+130h+var_1A0], rdi
0x180009d39  mov     r14d, edi
0x180009d3c  mov     [rbp+130h+var_160], rdi
0x180009d40  mov     [rbp+130h+pv], rdi
0x180009d44  mov     [rbp+130h+var_168], rdi
0x180009d48  mov     [rbp+130h+var_190], rdi
0x180009d4c  mov     [rsp+230h+var_1C8], rdi
0x180009d51  mov     rax, [rsi+88h]
0x180009d58  mov     rcx, [rax+40h]
0x180009d5c  add     rcx, 258h; lpCriticalSection
0x180009d63  call    cs:__imp_EnterCriticalSection
0x180009d69  mov     eax, [rbx+4]
0x180009d6c  mov     [rbp+130h+var_180], eax
0x180009d6f  mov     [rbp+130h+var_150.ulStartElement], eax
0x180009d72  mov     eax, [rbx+8]
0x180009d75  mov     [rbp+130h+var_17C], eax
0x180009d78  mov     [rbp+130h+var_150.cElements], eax
0x180009d7b  mov     eax, [rbx+0Ch]
0x180009d7e  mov     [rsp+230h+var_1B4], eax
0x180009d82  mov     eax, [rbx+10h]
0x180009d85  mov     [rbp+130h+arg_10], eax
0x180009d8b  mov     [rbp+130h+var_150.cbResultExtra], eax
0x180009d8e  lea     r13, [rbx+14h]
0x180009d92  mov     [rbp+130h+var_150.pvResultExtra], r13
0x180009d96  mov     [rbp+130h+var_188], rdi
0x180009d9a  lea     rax, [rbp+130h+var_188]
0x180009d9e  mov     [rsp+230h+ppv], rax; ppv
0x180009da3  lea     r9, _GUID_88a3342a_0bed_4834_922b_88d43173162f; riid
0x180009daa  xor     edx, edx; pUnkOuter
0x180009dac  lea     r8d, [rdi+17h]; dwClsContext
0x180009db0  lea     rcx, CLSID_SpPhraseBuilder; rclsid
0x180009db7  call    cs:__imp_CoCreateInstance
0x180009dbd  mov     esi, eax
0x180009dbf  test    eax, eax
0x180009dc1  js      loc_180009F23
0x180009dc7  mov     rcx, [rbp+130h+var_188]
0x180009dcb  mov     r8, [rcx]
0x180009dce  mov     eax, [rbp+130h+arg_10]
0x180009dd4  add     eax, 7
0x180009dd7  mov     edx, 0FFFFFFF8h
0x180009ddc  and     rdx, rax
0x180009ddf  add     rdx, 14h
0x180009de3  add     rdx, rbx
0x180009de6  mov     rax, [r8+40h]
0x180009dea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009def  mov     esi, eax
0x180009df1  test    eax, eax
0x180009df3  js      loc_180009F23
0x180009df9  mov     rcx, [rbp+130h+var_188]
0x180009dfd  mov     [rbp+130h+var_158], rcx
0x180009e01  mov     [rbp+130h+var_188], rdi
0x180009e05  mov     [rbp+130h+var_150.pPhrase], rcx
0x180009e09  mov     eax, 400h
0x180009e0e  mov     ebx, [rsp+230h+var_1B4]
0x180009e12  cmp     ebx, eax
0x180009e14  cmova   ebx, eax
0x180009e17  mov     [rsp+230h+var_1B4], ebx
0x180009e1b  mov     [rbp+130h+var_150.ulRequestAltCount], ebx
0x180009e1e  mov     rax, [rcx]
0x180009e21  lea     rdx, [rbp+130h+pv]
0x180009e25  mov     rax, [rax+18h]
0x180009e29  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009e2e  mov     esi, eax
0x180009e30  test    eax, eax
0x180009e32  js      loc_180009F23
0x180009e38  mov     rax, [rbp+130h+pv]
0x180009e3c  cmp     [rax+40h], edi
0x180009e3f  jz      loc_18000A52E
0x180009e45  cmp     [rax+68h], rdi
0x180009e49  jz      loc_18000A52E
0x180009e4f  lea     rdx, [rbp+130h+var_168]; struct SPPHRASE **
0x180009e53  lea     rcx, [rbp+130h+var_150]; struct tagSPPHRASEALTREQUEST *
0x180009e57  call    ?MakeAlternatePhraseTemplate@@YAJPEAUtagSPPHRASEALTREQUEST@@PEAPEAUSPPHRASE@@@Z; MakeAlternatePhraseTemplate(tagSPPHRASEALTREQUEST *,SPPHRASE * *)
0x180009e5c  mov     esi, eax
0x180009e5e  test    eax, eax
0x180009e60  js      loc_180009F23
0x180009e66  test    byte ptr [r13+40h], 1
0x180009e6b  jz      short loc_180009EA3
0x180009e6d  mov     rax, [rbp+130h+arg_0]
0x180009e74  mov     rax, [rax+88h]
0x180009e7b  mov     rcx, [rax+40h]
0x180009e7f  mov     rax, [r13+4Ch]
0x180009e83  cmp     rax, [rcx+230h]
0x180009e8a  jnz     short loc_180009E99
0x180009e8c  mov     rax, [r13+54h]
0x180009e90  cmp     rax, [rcx+238h]
0x180009e97  jz      short loc_180009EA3
0x180009e99  mov     esi, 8000FFFFh
0x180009e9e  jmp     loc_180009F23
0x180009ea3  mov     rdx, r13; struct LATTICE_HEADER *
0x180009ea6  lea     rcx, [rbp+130h+var_100]; struct LATTICE *
0x180009eaa  call    ?ReconstructInternalPointers@@YAXPEAULATTICE@@PEAULATTICE_HEADER@@@Z; ReconstructInternalPointers(LATTICE *,LATTICE_HEADER *)
0x180009eaf  lea     r9, [rbp+130h+var_100]; struct LATTICE *
0x180009eb3  lea     r8, [rsp+230h+var_1C0]; unsigned int *
0x180009eb8  lea     rdx, [rsp+230h+var_1C8]; struct LATTICE_NODE ***
0x180009ebd  lea     rcx, [rbp+130h+var_190]; int **
0x180009ec1  call    ?BuildElementArrays@@YAJPEAPEAHPEAPEAPEAULATTICE_NODE@@PEAKPEAULATTICE@@@Z; BuildElementArrays(int * *,LATTICE_NODE * * *,ulong *,LATTICE *)
0x180009ec6  mov     esi, eax
0x180009ec8  test    eax, eax
0x180009eca  js      short loc_180009F1E
0x180009ecc  mov     byte ptr [rbp+130h+arg_10], 0
0x180009ed3  xor     ecx, ecx
0x180009ed5  mov     r8d, [rsp+230h+var_1C0]
0x180009eda  test    r8d, r8d
0x180009edd  jz      short loc_180009EF8
0x180009edf  mov     rdx, [rbp+130h+var_190]
0x180009ee3  cmp     [rdx+rcx*4], ecx
0x180009ee6  jnz     short loc_180009EF1
0x180009ee8  inc     ecx
0x180009eea  cmp     ecx, r8d
0x180009eed  jb      short loc_180009EE3
0x180009eef  jmp     short loc_180009EF8
0x180009ef1  mov     byte ptr [rbp+130h+arg_10], 1
0x180009ef8  lea     rdi, [rbx+rbx*4]
0x180009efc  shl     rdi, 3
0x180009f00  mov     rcx, rdi; cb
0x180009f03  call    cs:__imp_CoTaskMemAlloc
0x180009f09  mov     r12, rax
0x180009f0c  mov     [rbp+130h+var_120], rax
0x180009f10  test    rax, rax
0x180009f13  jnz     loc_18000A026
0x180009f19  mov     esi, 8007000Eh
0x180009f1e  mov     rdi, [rsp+230h+var_1C8]
0x180009f23  mov     rax, [rbp+130h+arg_0]
0x180009f2a  mov     rax, [rax+88h]
0x180009f31  mov     rcx, [rax+40h]
0x180009f35  add     rcx, 258h; lpCriticalSection
0x180009f3c  call    cs:__imp_LeaveCriticalSection
0x180009f42  mov     rcx, [rbp+130h+var_158]
0x180009f46  test    rcx, rcx
0x180009f49  jz      short loc_180009F57
0x180009f4b  mov     rax, [rcx]
0x180009f4e  mov     rax, [rax+10h]
0x180009f52  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009f57  xor     ecx, ecx; pv
0x180009f59  call    cs:__imp_CoTaskMemFree
0x180009f5f  test    r12, r12
0x180009f62  jz      short loc_180009F88
0x180009f64  xor     ebx, ebx
0x180009f66  test    r15d, r15d
0x180009f69  jz      short loc_180009F7F
0x180009f6b  lea     rcx, [rbx+rbx*4]
0x180009f6f  lea     rcx, [r12+rcx*8]; struct tagSPPHRASEALT *
0x180009f73  call    ?FreeAlternate@@YAXPEAUtagSPPHRASEALT@@@Z; FreeAlternate(tagSPPHRASEALT *)
0x180009f78  inc     ebx
0x180009f7a  cmp     ebx, r15d
0x180009f7d  jb      short loc_180009F6B
0x180009f7f  mov     rcx, r12; pv
0x180009f82  call    cs:__imp_CoTaskMemFree
0x180009f88  mov     r12, [rbp+130h+var_1A0]
0x180009f8c  test    r12, r12
0x180009f8f  jz      short loc_180009FBF
0x180009f91  xor     ebx, ebx
0x180009f93  test    r15d, r15d
0x180009f96  jz      short loc_180009FA9
0x180009f98  mov     rcx, [r12+rbx*8]; pv
0x180009f9c  call    cs:__imp_CoTaskMemFree
0x180009fa2  inc     ebx
0x180009fa4  cmp     ebx, r15d
0x180009fa7  jb      short loc_180009F98
0x180009fa9  mov     rdx, r12; void *
0x180009fac  mov     rax, [rbp+130h+arg_0]
0x180009fb3  mov     rcx, [rax+80h]; this
0x180009fba  call    ?Free@CWinHeap@@QEAA_NPEAX@Z; CWinHeap::Free(void *)
0x180009fbf  test    r14, r14
0x180009fc2  jz      short loc_180009FD4
0x180009fc4  mov     rcx, r14; this
0x180009fc7  call    ??1CPhoneDecoder@@QEAA@XZ; CPhoneDecoder::~CPhoneDecoder(void)
0x180009fcc  mov     rcx, r14; void *
0x180009fcf  call    ?operator_delete@CAllocOnSpecificHeapBase@@SAXPEAX@Z; CAllocOnSpecificHeapBase::operator_delete(void *)
0x180009fd4  mov     rcx, [rbp+130h+pv]; pv
0x180009fd8  call    cs:__imp_CoTaskMemFree
0x180009fde  mov     rcx, [rbp+130h+var_168]; pv
0x180009fe2  call    cs:__imp_CoTaskMemFree
0x180009fe8  mov     rax, [rbp+130h+var_190]
0x180009fec  test    rax, rax
0x180009fef  jz      short loc_180009FF9
0x180009ff1  mov     rcx, rax; void *
0x180009ff4  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180009ff9  test    rdi, rdi
0x180009ffc  jz      short loc_18000A007
0x180009ffe  mov     rcx, rdi; void *
0x18000a001  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000a006  nop
0x18000a007  lea     rcx, [rbp+130h+var_188]
0x18000a00b  call    ??1?$CComPtrBase@UISpObjectToken@@@ATL@@QEAA@XZ; ATL::CComPtrBase<ISpObjectToken>::~CComPtrBase<ISpObjectToken>(void)
0x18000a010  mov     eax, esi
0x18000a012  add     rsp, 1F8h
0x18000a019  pop     r15
0x18000a01b  pop     r14
0x18000a01d  pop     r13
0x18000a01f  pop     r12
0x18000a021  pop     rdi
0x18000a022  pop     rsi
0x18000a023  pop     rbx
0x18000a024  pop     rbp
0x18000a025  retn
0x18000a026  mov     r8, rdi; Size
0x18000a029  xor     edx, edx; Val
0x18000a02b  mov     rcx, r12; void *
0x18000a02e  call    memset_0
0x18000a033  lea     r9, [rbp+130h+arg_8]; unsigned int *
0x18000a03a  mov     r8, r12; struct tagSPPHRASEALT *
0x18000a03d  lea     rcx, [rbp+130h+var_150]; struct tagSPPHRASEALTREQUEST *
0x18000a041  call    ?AddOriginalPhraseAlternate@@YAJPEAUtagSPPHRASEALTREQUEST@@PEAUSPPHRASE@@PEAUtagSPPHRASEALT@@PEAK@Z; AddOriginalPhraseAlternate(tagSPPHRASEALTREQUEST *,SPPHRASE *,tagSPPHRASEALT *,ulong *)
0x18000a046  mov     esi, eax
0x18000a048  mov     r15d, [rbp+130h+arg_8]
0x18000a04f  test    eax, eax
0x18000a051  js      loc_180009F1E
0x18000a057  cmp     r15d, ebx
0x18000a05a  jz      loc_18000A17F
0x18000a060  mov     rdi, [rsp+230h+var_1C8]
0x18000a065  cmp     cs:byte_180150A4A, 0
0x18000a06c  jz      short loc_18000A0D3
0x18000a06e  mov     rax, [rbp+130h+arg_0]
0x18000a075  mov     rcx, [rax+88h]
0x18000a07c  mov     eax, [rsp+230h+var_1C0]
0x18000a080  mov     [rsp+230h+var_1E8], eax; unsigned int
0x18000a084  mov     [rsp+230h+var_1F0], rdi; struct LATTICE_NODE **
0x18000a089  mov     rax, [rbp+130h+var_190]
0x18000a08d  mov     [rsp+230h+var_1F8], rax; int *
0x18000a092  mov     [rsp+230h+var_200], r13; struct LATTICE_HEADER *
0x18000a097  lea     rax, [rbp+130h+arg_8]
0x18000a09e  mov     [rsp+230h+var_208], rax; unsigned int *
0x18000a0a3  mov     [rsp+230h+ppv], r12; struct tagSPPHRASEALT *
0x18000a0a8  mov     r9, [rbp+130h+var_168]; struct SPPHRASE *
0x18000a0ac  lea     rdx, [rbp+130h+var_150]; struct tagSPPHRASEALTREQUEST *
0x18000a0b0  mov     rcx, [rcx+40h]; this
0x18000a0b4  call    ?GetAlternatesForAnalyzer@CDecoder@@QEAAJPEAUtagSPPHRASEALTREQUEST@@PEAUSPPHRASE@@1PEAUtagSPPHRASEALT@@PEAKPEAULATTICE_HEADER@@PEAHPEAPEAULATTICE_NODE@@K@Z; CDecoder::GetAlternatesForAnalyzer(tagSPPHRASEALTREQUEST *,SPPHRASE *,SPPHRASE *,tagSPPHRASEALT *,ulong *,LATTICE_HEADER *,int *,LATTICE_NODE * *,ulong)
0x18000a0b9  mov     esi, eax
0x18000a0bb  mov     r15d, [rbp+130h+arg_8]
0x18000a0c2  test    eax, eax
0x18000a0c4  js      loc_180009F23
0x18000a0ca  cmp     r15d, ebx
0x18000a0cd  jz      loc_18000A17F
0x18000a0d3  cmp     cs:byte_180150A4B, 0
0x18000a0da  jz      loc_18000A17F
0x18000a0e0  test    byte ptr [r13+40h], 1
0x18000a0e5  jnz     loc_18000A17F
0x18000a0eb  xor     r8d, r8d; bool
0x18000a0ee  mov     rax, [rbp+130h+arg_0]
0x18000a0f5  mov     rdx, [rax+80h]; struct CHeap *
0x18000a0fc  mov     ecx, 110h; unsigned __int64
0x18000a101  call    ?operator_new@CAllocOnSpecificHeapBase@@SAPEAX_KPEAVCHeap@@_N@Z; CAllocOnSpecificHeapBase::operator_new(unsigned __int64,CHeap *,bool)
0x18000a106  mov     r14, rax
0x18000a109  xor     ecx, ecx
0x18000a10b  test    rax, rax
0x18000a10e  jz      short loc_18000A172
0x18000a110  lea     rax, ?g_heap@@3VCHeap@@A; CHeap g_heap
0x18000a117  mov     [r14+28h], rax
0x18000a11b  mov     [r14+38h], rcx
0x18000a11f  mov     [r14+50h], rcx
0x18000a123  mov     [r14+30h], rcx
0x18000a127  mov     [r14+40h], ecx
0x18000a12b  mov     qword ptr [r14+44h], 1
0x18000a133  lea     rax, ??_7CPhoneMatchHash@@6B@; const CPhoneMatchHash::`vftable'
0x18000a13a  mov     [r14+20h], rax
0x18000a13e  mov     [r14+58h], rcx
0x18000a142  mov     [r14+68h], rcx
0x18000a146  mov     [r14+60h], rcx
0x18000a14a  mov     qword ptr [r14+70h], 40h ; '@'
0x18000a152  mov     [r14+78h], rcx
0x18000a156  mov     dword ptr [r14+80h], 1
0x18000a161  mov     [r14+0C8h], rcx
0x18000a168  mov     esi, 80004001h
0x18000a16d  jmp     loc_180009F23
0x18000a172  mov     esi, 8007000Eh
0x18000a177  mov     r14, rcx
0x18000a17a  jmp     loc_180009F23
0x18000a17f  cmp     cs:byte_180150A51, 0
  ... truncated ...
```
