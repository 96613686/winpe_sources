# CGramBackEnd::Commit(ulong)

- ea: `0x180120ea0`
- end: `0x180121746`
- name: `?Commit@CGramBackEnd@@UEAAJK@Z`
- size: `2214`
- prototype: `__int64 __fastcall(CGramBackEnd *__hidden this, unsigned int)`
- caller_count: `0`
- callee_count: `24`
- tags: `file_ops, loader_planting, service_task, installer_update, broker_com_uri`

## callees

- `0x1800123c0`
- `0x18003a808`
- `0x180079e30`
- `0x18007a2dc`
- `0x18007a350`
- `0x18007aae4`
- `0x1800fb528`
- `0x180120610`
- `0x180120694`
- `0x180120ea0`
- `0x18012468c`
- `0x180124894`
- `0x180124ad0`
- `0x18012526c`
- `0x180125414`
- `0x180125468`
- `0x180125a68`
- `0x180125b58`
- `0x180125ca8`
- `0x1801263b8`
- `0x1801264c8`
- `0x180126704`
- `0x18017b66c`
- `0x18028b010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_qsort` at `0x180120fb8`
- `api-ms-win-crt-private-l1-1-0!_o_qsort` at `0x1801210ba`
- `api-ms-win-crt-private-l1-1-0!_o_qsort` at `0x180120fb8`
- `api-ms-win-crt-private-l1-1-0!_o_qsort` at `0x1801210ba`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180120ef6`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180120ef6`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180120f78`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180121640`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180120f78`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180121640`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x1801211e4`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x1801211e4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180121634`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180121634`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180121321`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180121321`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CGramBackEnd::Commit(CGramBackEnd *this, int a2)
{
  CGramBackEnd *v3; // rsi
  int v4; // ebx
  __int64 i; // rdx
  int updated; // edi
  unsigned __int64 v8; // r13
  size_t v9; // r15
  unsigned __int64 v10; // rax
  void *v11; // r12
  __int64 v12; // rbx
  __int64 v13; // rdx
  float *v14; // r12
  int v15; // r13d
  unsigned int v16; // r14d
  size_t v17; // rdx
  _QWORD *v18; // r15
  __int64 k; // rbx
  __int64 v20; // rdx
  int v21; // r9d
  unsigned int v22; // r8d
  unsigned int v23; // eax
  unsigned int v24; // ecx
  int v25; // r15d
  unsigned int v26; // ebx
  __int128 v27; // xmm0
  __int64 v28; // rcx
  __int64 v29; // rdx
  _QWORD *v30; // r8
  int v31; // r9d
  int v32; // eax
  unsigned int v33; // r10d
  __int64 v34; // r8
  __int64 v35; // rcx
  _QWORD *v36; // rdx
  int v37; // r9d
  int v38; // eax
  unsigned int v39; // edx
  int v40; // ecx
  int v41; // ecx
  int v42; // edx
  unsigned int v43; // r14d
  float *v44; // rax
  __int64 v45; // rax
  __int64 v46; // rdi
  __int64 (__fastcall *v47)(__int64, __int64, _QWORD, _QWORD); // r15
  int v48; // ebx
  __int64 v49; // rax
  __int64 v50; // rdi
  __int64 (__fastcall *v51)(__int64, __int64, _QWORD, _QWORD); // r15
  unsigned int v52; // eax
  int v53; // ebx
  __int64 v54; // rax
  CRule *v55; // rbx
  bool v56; // r14
  CRule *v57; // rbx
  char v58; // bl
  unsigned int v59; // ebx
  CGramNode **v60; // r14
  unsigned int v61; // eax
  unsigned int v62; // ebx
  CCfgLexicon *v63; // rcx
  __int64 m; // rax
  bool v65; // [rsp+30h] [rbp-D0h]
  unsigned int v66; // [rsp+34h] [rbp-CCh] BYREF
  unsigned int v67[2]; // [rsp+38h] [rbp-C8h] BYREF
  __int64 j; // [rsp+40h] [rbp-C0h] BYREF
  bool v69[4]; // [rsp+48h] [rbp-B8h] BYREF
  int v70; // [rsp+4Ch] [rbp-B4h]
  void *Base; // [rsp+50h] [rbp-B0h]
  CGramBackEnd *v72; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v73; // [rsp+60h] [rbp-A0h]
  __int64 v74; // [rsp+68h] [rbp-98h] BYREF
  LPCRITICAL_SECTION lpCriticalSection; // [rsp+70h] [rbp-90h]
  unsigned __int64 v76; // [rsp+78h] [rbp-88h]
  unsigned int v77; // [rsp+80h] [rbp-80h] BYREF
  __int128 v78; // [rsp+84h] [rbp-7Ch]
  __int128 v79; // [rsp+94h] [rbp-6Ch]
  __int16 v80; // [rsp+A4h] [rbp-5Ch]
  __int16 v81; // [rsp+A6h] [rbp-5Ah]
  unsigned int v82; // [rsp+A8h] [rbp-58h]
  int v83; // [rsp+ACh] [rbp-54h]
  int v84; // [rsp+B0h] [rbp-50h]
  int v85; // [rsp+B4h] [rbp-4Ch]
  int v86; // [rsp+B8h] [rbp-48h]
  unsigned int v87; // [rsp+BCh] [rbp-44h]
  int v88; // [rsp+C0h] [rbp-40h]
  unsigned int v89; // [rsp+C4h] [rbp-3Ch]
  int v90; // [rsp+C8h] [rbp-38h]
  int v91; // [rsp+CCh] [rbp-34h]
  int v92; // [rsp+D0h] [rbp-30h]
  int v93; // [rsp+D4h] [rbp-2Ch]
  unsigned int v94; // [rsp+D8h] [rbp-28h]
  int v95; // [rsp+DCh] [rbp-24h]
  int v96; // [rsp+E0h] [rbp-20h]
  int v97; // [rsp+FCh] [rbp-4h]
  int v98; // [rsp+100h] [rbp+0h]
  int v99; // [rsp+104h] [rbp+4h]
  int v100; // [rsp+108h] [rbp+8h]
  unsigned int v101; // [rsp+110h] [rbp+10h]

  v70 = a2;
  v3 = this;
  v72 = this;
  v76 = ((unsigned __int64)this + 40) & -(__int64)(this != 0);
  lpCriticalSection = (LPCRITICAL_SECTION)(v76 + 8);
  EnterCriticalSection((LPCRITICAL_SECTION)(v76 + 8));
  if ( (a2 & 0x7FFFFFFE) != 0 )
  {
    v4 = -2147024809;
LABEL_10:
    LeaveCriticalSection((LPCRITICAL_SECTION)(v76 + 8));
    return (unsigned int)v4;
  }
  if ( !*((_QWORD *)v3 + 49) )
  {
    v4 = -2147201023;
    goto LABEL_10;
  }
  if ( (*((_BYTE *)v3 + 416) & 0xB) == 0 && !*((_DWORD *)v3 + 78) )
  {
    v4 = -2147200982;
    LogError(0, -2147200982, *((struct ISpErrorLog **)v3 + 48), 0x99u, L"Need at least one rule!");
    goto LABEL_10;
  }
  if ( (a2 & 1) != 0 )
  {
    v4 = (*(__int64 (__fastcall **)(__int64))(*((_QWORD *)v3 + 4) + 112LL))((__int64)v3 + 32);
    if ( v4 < 0 )
      goto LABEL_10;
  }
  *(_QWORD *)v67 = 0;
  j = 0;
  for ( i = 0; (unsigned int)CSpHandleTable<CRecoInstCategory,void *,1>::Next((char *)v3 + 248, i, &j, v67); i = j )
  {
    if ( *(int *)(*(_QWORD *)v67 + 24LL) > 1 )
      qsort(
        *(void **)(*(_QWORD *)v67 + 16LL),
        *(int *)(*(_QWORD *)v67 + 24LL),
        *(_QWORD *)(*(_QWORD *)v67 + 40LL),
        CArc::CompareSerializationOrder);
  }
  if ( !*((_DWORD *)v3 + 59) || (updated = CGramBackEnd::PrepareNGramsForSerialization(v3), updated >= 0) )
  {
    updated = CGramBackEnd::ValidateAndTagRules(v3);
    if ( updated >= 0 )
    {
      v8 = *((unsigned int *)v3 + 62);
      v66 = v8;
      v9 = (unsigned int)v8;
      v10 = 8 * v8;
      if ( !is_mul_ok(v8, 8u) )
        v10 = -1;
      v11 = operator new[](v10, (const struct std::nothrow_t *)&std::nothrow);
      Base = v11;
      if ( !v11 )
      {
        updated = -2147024882;
        goto LABEL_110;
      }
      v12 = 0;
      v13 = 0;
      for ( j = 0; (unsigned int)CSpHandleTable<CRecoInstCategory,void *,1>::Next((char *)v3 + 248, v13, &j, v67); v13 = j )
      {
        if ( (unsigned int)v12 >= (unsigned int)v8 )
        {
          operator delete(v11);
          updated = -2147418113;
          goto LABEL_110;
        }
        *((_QWORD *)v11 + v12) = *(_QWORD *)v67;
        v12 = (unsigned int)(v12 + 1);
      }
      v14 = 0;
      LODWORD(j) = 1;
      v15 = 0;
      v16 = 0;
      v17 = v9;
      v18 = Base;
      qsort(Base, v17, 8u, CGramNode::ComparePointer);
      for ( k = 0; (unsigned int)k < v66; k = (unsigned int)(k + 1) )
      {
        v20 = v18[k];
        v21 = j;
        *(_DWORD *)(v20 + 80) = j;
        v22 = *(_DWORD *)(v20 + 24) + *(_DWORD *)(v20 + 88);
        if ( !v22 && *(_DWORD *)(*(_QWORD *)(v20 + 8) + 272LL) > 1u )
        {
          CGramBackEnd::LogError(v3, -2147200994, 0x6Eu, 0);
          updated = -2147200926;
          break;
        }
        LODWORD(j) = v22 + v21;
        if ( v16 < v22 )
          v16 = v22;
        v15 += CGramNode::NumSemanticTags((CGramNode *)v20);
      }
      v23 = CSpDynamicString::Length((CGramBackEnd *)((char *)v3 + 432));
      v24 = v23 + 1;
      if ( !v23 )
        v24 = 0;
      LODWORD(v73) = v24;
      if ( updated >= 0 && *((_QWORD *)v3 + 66) )
        updated = UpdateLexicon((char *)v3 + 96);
      if ( (unsigned int)j > 0x3FFFFF || (v65 = 1, *((_DWORD *)v3 + 59)) )
        v65 = 0;
      v25 = *((_DWORD *)v3 + 59);
      v69[0] = v25 != 0;
      v26 = 148;
      memset_0(&v77, 0, 0x94u);
      v67[0] = 148;
      if ( updated >= 0 )
      {
        v81 = *((_WORD *)v3 + 120);
        if ( v65 )
          v27 = xmmword_1802CB000;
        else
          v27 = v25 ? xmmword_1802CAFF0 : xmmword_1802CAFE0;
        v78 = v27;
        CoCreateGuid((GUID *)((char *)v3 + 200));
        v79 = *(_OWORD *)((char *)v3 + 200);
        v80 = *((_WORD *)v3 + 108);
        v82 = v16;
        v28 = *((unsigned int *)v3 + 30);
        v29 = 4 * v28;
        v30 = (_QWORD *)((char *)v3 + 112);
        v31 = (_DWORD)v28 ? *(_DWORD *)(v29 + *v30) : 0;
        v83 = v31;
        v84 = v28;
        v85 = 148;
        if ( (_DWORD)v28 )
        {
          v84 = v28 + 1;
          v32 = *(_DWORD *)(v29 + *v30);
        }
        else
        {
          v32 = 0;
        }
        v33 = ((2 * v32 + 3) & 0xFFFFFFFC) + 148;
        v34 = *((unsigned int *)v3 + 42);
        v35 = 4 * v34;
        v36 = (_QWORD *)((char *)v3 + 160);
        v37 = (_DWORD)v34 ? *(_DWORD *)(v35 + *v36) : 0;
        v86 = v37;
        v87 = ((2 * v32 + 3) & 0xFFFFFFFC) + 148;
        v38 = (_DWORD)v34 ? *(_DWORD *)(v35 + *v36) : 0;
        v39 = v33 + ((2 * v38 + 3) & 0xFFFFFFFC);
        v40 = *((_DWORD *)v3 + 78);
        v88 = v40;
        v89 = v39;
        v41 = v25 ? v39 + 16 * v40 : v39 + 12 * v40;
        v95 = *((_DWORD *)v3 + 49);
        v96 = v41;
        v42 = v41 + 12 * v95;
        v99 = (_DWORD)v73 != 0 ? v42 : 0;
        v90 = j;
        v91 = v42 + ((2 * v73 + 3) & 0xFFFFFFFC);
        v26 = v91 + 8 * j;
        v67[0] = v26;
        if ( *((_DWORD *)v3 + 58) )
        {
          v92 = v91 + 8 * j;
          v43 = v26 + 4 * j;
          v26 = v43;
          v67[0] = v43;
          v44 = (float *)CoTaskMemAlloc(4LL * (unsigned int)j);
          v14 = v44;
          if ( v44 )
            *v44 = 0.0;
          else
            updated = -2147024882;
        }
        else
        {
          v92 = 0;
          v43 = v91 + 8 * j;
        }
        v45 = *((_QWORD *)v3 + 51);
        v97 = v45 ? *(_DWORD *)(v45 + 268) : -1;
        v98 = *((_DWORD *)v3 + 104);
        v100 = *((_DWORD *)v3 + 128);
        if ( updated >= 0 )
        {
          v93 = v15;
          v94 = v26;
          v26 = v43 + 32 * v15;
          v67[0] = v26;
          if ( *((_DWORD *)v3 + 59) )
          {
            updated = CGramBackEnd::CalculateNGramOffsets(v3, v67);
            v26 = v67[0];
          }
        }
      }
      v74 = 0;
      if ( updated >= 0 )
      {
        v101 = v26;
        updated = CGramBackEnd::BuildHeaderExtension(v3, v26, (struct SPCFGSERIALIZEDHEADEREXT *)&v74, v67);
        if ( updated >= 0 )
        {
          v77 = v67[0];
          updated = CGramBackEnd::WriteStream(v3, &v77, 0x94u);
          if ( updated >= 0 )
          {
            if ( CStringBlobT<unsigned short>::SerializeData((char *)v3 + 96) )
            {
              v46 = *((_QWORD *)v3 + 49);
              v47 = *(__int64 (__fastcall **)(__int64, __int64, _QWORD, _QWORD))(*(_QWORD *)v46 + 32LL);
              v48 = *((_DWORD *)v3 + 30) ? *(_DWORD *)(*((_QWORD *)v3 + 14) + 4LL * *((unsigned int *)v3 + 30)) : 0;
              v49 = CStringBlobT<unsigned short>::SerializeData((char *)v3 + 96);
              updated = v47(v46, v49, (2 * v48 + 3) & 0xFFFFFFFC, 0);
              if ( updated < 0 )
                goto LABEL_89;
            }
            if ( CStringBlobT<unsigned short>::SerializeData((char *)v3 + 144) )
            {
              v50 = *((_QWORD *)v3 + 49);
              v51 = *(__int64 (__fastcall **)(__int64, __int64, _QWORD, _QWORD))(*(_QWORD *)v50 + 32LL);
              v52 = *((_DWORD *)v3 + 42);
              v53 = v52 ? *(_DWORD *)(*((_QWORD *)v3 + 20) + 4LL * v52) : 0;
              v54 = CStringBlobT<unsigned short>::SerializeData((char *)v3 + 144);
              updated = v51(v50, v54, (2 * v53 + 3) & 0xFFFFFFFC, 0);
              if ( updated < 0 )
LABEL_89:
                CGramBackEnd::LogError(v3, updated, 0xA1u, 0);
            }
          }
        }
      }
      v55 = (CRule *)*((_QWORD *)v3 + 37);
      if ( updated >= 0 )
      {
        v56 = v69[0];
        do
        {
          if ( !v55 )
            break;
          updated = CRule::Serialize(v55, v65, v56);
          v55 = (CRule *)*((_QWORD *)v55 + 32);
        }
        while ( updated >= 0 );
        v3 = v72;
      }
      v57 = (CRule *)*((_QWORD *)v3 + 37);
      if ( updated >= 0 )
      {
        while ( v57 )
        {
          updated = CRule::SerializeResources(v57);
          v57 = (CRule *)*((_QWORD *)v57 + 32);
          if ( updated < 0 )
            goto LABEL_105;
        }
        v58 = v73;
        if ( (_DWORD)v73
          && ((updated = (*(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD, _QWORD))(**((_QWORD **)v3 + 49) + 32LL))(
                           *((_QWORD *)v3 + 49),
                           *((_QWORD *)v3 + 54),
                           (unsigned int)(2 * v73),
                           0),
               updated < 0)
           || ((-2 * v58) & 3) != 0
           && (*(_WORD *)v69 = 0, updated = CGramBackEnd::WriteStream(v3, v69, 2u), updated < 0)) )
        {
          CGramBackEnd::LogError(v3, updated, 0xA1u, 0);
        }
        else
        {
          v72 = 0;
          updated = CGramBackEnd::WriteStream(v3, &v72, 8u);
        }
      }
LABEL_105:
      v67[0] = 1;
      *(_DWORD *)v69 = 1;
      v59 = 0;
      v60 = (CGramNode **)Base;
      if ( updated >= 0 )
      {
        while ( 1 )
        {
          v61 = v66;
          if ( v59 >= v66 )
            break;
          updated = CGramNode::SerializeNodeEntries(v60[v59++], v14, (unsigned int *)v69, v67);
          if ( updated < 0 )
            goto LABEL_108;
        }
        if ( !*((_DWORD *)v3 + 58) )
          goto LABEL_114;
        updated = CGramBackEnd::WriteStream(v3, v14, 4 * (int)j);
      }
      v61 = v66;
LABEL_114:
      v62 = 0;
      if ( updated >= 0 )
      {
        while ( v62 < v61 )
        {
          updated = CGramNode::SerializeSemanticTags(v60[v62++], v65);
          v61 = v66;
          if ( updated < 0 )
            goto LABEL_108;
        }
        if ( !*((_DWORD *)v3 + 59) || (updated = CGramBackEnd::SerializeNgramBlobs(v3), updated >= 0) )
          updated = CGramBackEnd::WriteStream(v3, &v74, 8u);
      }
      v66 = 0;
      if ( updated < 0
        || (v63 = (CCfgLexicon *)*((_QWORD *)v3 + 66)) != 0
        && (updated = CCfgLexicon::Serialize(v63, *((struct IStream **)v3 + 49), &v66), updated < 0) )
      {
LABEL_108:
        CGramBackEnd::LogError(v3, updated, 0x9Du, 0);
      }
      else if ( v70 < 0 )
      {
        for ( m = *((_QWORD *)v3 + 37); m; m = *(_QWORD *)(m + 256) )
          *(_BYTE *)(m + 12) = 0;
      }
      operator delete(v60);
      CoTaskMemFree(v14);
    }
  }
LABEL_110:
  LeaveCriticalSection(lpCriticalSection);
  return (unsigned int)updated;
}

```

## disassembly

```asm
0x180120ea0  push    rbp
0x180120ea2  push    rbx
0x180120ea3  push    rsi
0x180120ea4  push    rdi
0x180120ea5  push    r12
0x180120ea7  push    r13
0x180120ea9  push    r14
0x180120eab  push    r15
0x180120ead  lea     rbp, [rsp-38h]
0x180120eb2  sub     rsp, 138h
0x180120eb9  mov     rax, cs:__security_cookie
0x180120ec0  xor     rax, rsp
0x180120ec3  mov     [rbp+70h+var_50], rax
0x180120ec7  mov     ebx, edx
0x180120ec9  mov     [rsp+170h+var_124], edx
0x180120ecd  mov     rsi, rcx
0x180120ed0  mov     [rsp+170h+var_118], rcx
0x180120ed5  mov     rax, rcx
0x180120ed8  add     rcx, 28h ; '('
0x180120edc  neg     rax
0x180120edf  sbb     r8, r8
0x180120ee2  and     r8, rcx
0x180120ee5  mov     [rsp+170h+var_F8], r8
0x180120eea  lea     rdi, [r8+8]
0x180120eee  mov     [rsp+170h+lpCriticalSection], rdi
0x180120ef3  mov     rcx, rdi; lpCriticalSection
0x180120ef6  call    cs:__imp_EnterCriticalSection
0x180120efc  nop
0x180120efd  test    ebx, 7FFFFFFEh
0x180120f03  jz      short loc_180120F0C
0x180120f05  mov     ebx, 80070057h
0x180120f0a  jmp     short loc_180120F75
0x180120f0c  xor     r15d, r15d
0x180120f0f  cmp     [rsi+188h], r15
0x180120f16  jnz     short loc_180120F1F
0x180120f18  mov     ebx, 80045001h
0x180120f1d  jmp     short loc_180120F75
0x180120f1f  test    byte ptr [rsi+1A0h], 0Bh
0x180120f26  jnz     short loc_180120F5A
0x180120f28  cmp     [rsi+138h], r15d
0x180120f2f  jnz     short loc_180120F5A
0x180120f31  lea     rax, aNeedAtLeastOne; "Need at least one rule!"
0x180120f38  mov     [rsp+170h+var_150], rax; unsigned __int16 *
0x180120f3d  mov     r9d, 99h; unsigned int
0x180120f43  mov     r8, [rsi+180h]; struct ISpErrorLog *
0x180120f4a  mov     ebx, 8004502Ah
0x180120f4f  mov     edx, ebx; int
0x180120f51  xor     ecx, ecx; unsigned int
0x180120f53  call    ?LogError@@YAXKJPEAUISpErrorLog@@IPEBG@Z; LogError(ulong,long,ISpErrorLog *,uint,ushort const *)
0x180120f58  jmp     short loc_180120F75
0x180120f5a  test    bl, 1
0x180120f5d  jz      short loc_180120F85
0x180120f5f  lea     rcx, [rsi+20h]
0x180120f63  mov     rax, [rcx]
0x180120f66  mov     rax, [rax+70h]
0x180120f6a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180120f6f  mov     ebx, eax
0x180120f71  test    eax, eax
0x180120f73  jns     short loc_180120F85
0x180120f75  mov     rcx, rdi; lpCriticalSection
0x180120f78  call    cs:__imp_LeaveCriticalSection
0x180120f7e  mov     eax, ebx
0x180120f80  jmp     loc_180121648
0x180120f85  mov     qword ptr [rsp+170h+var_138], r15
0x180120f8a  mov     [rsp+170h+var_130], r15
0x180120f8f  lea     r14, [rsi+0F8h]
0x180120f96  xor     edx, edx
0x180120f98  jmp     short loc_180120FC3
0x180120f9a  mov     rcx, qword ptr [rsp+170h+var_138]
0x180120f9f  cmp     dword ptr [rcx+18h], 1
0x180120fa3  jle     short loc_180120FBE
0x180120fa5  movsxd  rdx, dword ptr [rcx+18h]; NumOfElements
0x180120fa9  lea     r9, ?CompareSerializationOrder@CArc@@SAHPEBX0@Z; CompareFunction
0x180120fb0  mov     r8, [rcx+28h]; SizeOfElements
0x180120fb4  mov     rcx, [rcx+10h]; Base
0x180120fb8  call    cs:__imp_qsort
0x180120fbe  mov     rdx, [rsp+170h+var_130]
0x180120fc3  lea     r9, [rsp+170h+var_138]
0x180120fc8  lea     r8, [rsp+170h+var_130]
0x180120fcd  mov     rcx, r14
0x180120fd0  call    ?Next@?$CSpHandleTable@VCRecoInstCategory@@PEAX$00@@QEBAHPEAXPEAPEAXPEAPEAVCRecoInstCategory@@@Z; CSpHandleTable<CRecoInstCategory,void *,1>::Next(void *,void * *,CRecoInstCategory * *)
0x180120fd5  test    eax, eax
0x180120fd7  jnz     short loc_180120F9A
0x180120fd9  cmp     [rsi+0ECh], r15d
0x180120fe0  jbe     short loc_180120FF4
0x180120fe2  mov     rcx, rsi; this
0x180120fe5  call    ?PrepareNGramsForSerialization@CGramBackEnd@@QEAAJXZ; CGramBackEnd::PrepareNGramsForSerialization(void)
0x180120fea  mov     edi, eax
0x180120fec  test    eax, eax
0x180120fee  js      loc_18012163B
0x180120ff4  mov     rcx, rsi; this
0x180120ff7  call    ?ValidateAndTagRules@CGramBackEnd@@QEAAJXZ; CGramBackEnd::ValidateAndTagRules(void)
0x180120ffc  mov     edi, eax
0x180120ffe  test    eax, eax
0x180121000  js      loc_18012163B
0x180121006  mov     r13d, [r14]
0x180121009  mov     [rsp+170h+var_13C], r13d
0x18012100e  mov     r15d, r13d
0x180121011  mov     eax, 8
0x180121016  mul     r13
0x180121019  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x180121020  cmovb   rax, rcx
0x180121024  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18012102b  mov     rcx, rax; unsigned __int64
0x18012102e  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x180121033  mov     r12, rax
0x180121036  mov     [rsp+170h+Base], rax
0x18012103b  test    rax, rax
0x18012103e  jnz     short loc_18012104A
0x180121040  mov     edi, 8007000Eh
0x180121045  jmp     loc_18012163B
0x18012104a  xor     ebx, ebx
0x18012104c  xor     edx, edx
0x18012104e  mov     [rsp+170h+var_130], rdx
0x180121053  lea     r9, [rsp+170h+var_138]
0x180121058  lea     r8, [rsp+170h+var_130]
0x18012105d  mov     rcx, r14
0x180121060  call    ?Next@?$CSpHandleTable@VCRecoInstCategory@@PEAX$00@@QEBAHPEAXPEAPEAXPEAPEAVCRecoInstCategory@@@Z; CSpHandleTable<CRecoInstCategory,void *,1>::Next(void *,void * *,CRecoInstCategory * *)
0x180121065  test    eax, eax
0x180121067  jz      short loc_180121092
0x180121069  cmp     ebx, r13d
0x18012106c  jnb     short loc_180121080
0x18012106e  mov     rax, qword ptr [rsp+170h+var_138]
0x180121073  mov     [r12+rbx*8], rax
0x180121077  inc     ebx
0x180121079  mov     rdx, [rsp+170h+var_130]
0x18012107e  jmp     short loc_180121053
0x180121080  mov     rcx, r12; Block
0x180121083  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180121088  mov     edi, 8000FFFFh
0x18012108d  jmp     loc_18012163B
0x180121092  xor     r12d, r12d
0x180121095  mov     dword ptr [rsp+170h+var_130], 1
0x18012109d  xor     r13d, r13d
0x1801210a0  xor     r14d, r14d
0x1801210a3  lea     r9, ?ComparePointer@CGramNode@@SAHPEBX0@Z; CompareFunction
0x1801210aa  lea     r8d, [r12+8]; SizeOfElements
0x1801210af  mov     rdx, r15; NumOfElements
0x1801210b2  mov     r15, [rsp+170h+Base]
0x1801210b7  mov     rcx, r15; Base
0x1801210ba  call    cs:__imp_qsort
0x1801210c0  xor     ebx, ebx
0x1801210c2  cmp     ebx, [rsp+170h+var_13C]
0x1801210c6  jnb     short loc_180121127
0x1801210c8  mov     rdx, [r15+rbx*8]
0x1801210cc  mov     r9d, dword ptr [rsp+170h+var_130]
0x1801210d1  mov     [rdx+50h], r9d
0x1801210d5  mov     r8d, [rdx+58h]
0x1801210d9  add     r8d, [rdx+18h]
0x1801210dd  jnz     short loc_1801210EC
0x1801210df  mov     rax, [rdx+8]
0x1801210e3  cmp     dword ptr [rax+110h], 1
0x1801210ea  ja      short loc_18012110E
0x1801210ec  test    edi, edi
0x1801210ee  js      short loc_180121127
0x1801210f0  add     r9d, r8d
0x1801210f3  mov     dword ptr [rsp+170h+var_130], r9d
0x1801210f8  cmp     r14d, r8d
0x1801210fb  cmovb   r14d, r8d
0x1801210ff  mov     rcx, rdx; this
0x180121102  call    ?NumSemanticTags@CGramNode@@QEAAKXZ; CGramNode::NumSemanticTags(void)
0x180121107  add     r13d, eax
0x18012110a  inc     ebx
0x18012110c  jmp     short loc_1801210C2
0x18012110e  xor     r9d, r9d; unsigned __int16 *
0x180121111  mov     edx, 8004501Eh; int
0x180121116  lea     r8d, [r9+6Eh]; unsigned int
0x18012111a  mov     rcx, rsi; this
0x18012111d  call    ?LogError@CGramBackEnd@@QEAAJJIPEBG@Z; CGramBackEnd::LogError(long,uint,ushort const *)
0x180121122  mov     edi, 80045062h
0x180121127  lea     rcx, [rsi+1B0h]; this
0x18012112e  call    ?Length@CSpDynamicString@@QEBAIXZ; CSpDynamicString::Length(void)
0x180121133  lea     ecx, [rax+1]
0x180121136  test    eax, eax
0x180121138  cmovz   ecx, eax
0x18012113b  mov     dword ptr [rsp+170h+var_110], ecx
0x18012113f  test    edi, edi
0x180121141  js      short loc_18012115A
0x180121143  mov     rdx, [rsi+210h]
0x18012114a  test    rdx, rdx
0x18012114d  jz      short loc_18012115A
0x18012114f  lea     rcx, [rsi+60h]
0x180121153  call    UpdateLexicon
0x180121158  mov     edi, eax
0x18012115a  cmp     dword ptr [rsp+170h+var_130], 3FFFFFh
0x180121162  ja      short loc_180121172
0x180121164  cmp     [rsi+0ECh], r12d
0x18012116b  mov     [rsp+170h+var_140], 1
0x180121170  jz      short loc_180121177
0x180121172  mov     [rsp+170h+var_140], r12b
0x180121177  mov     r15d, [rsi+0ECh]
0x18012117e  test    r15d, r15d
0x180121181  setnz   [rsp+170h+var_128]
0x180121186  mov     ebx, 94h
0x18012118b  mov     r8d, ebx; Size
0x18012118e  xor     edx, edx; Val
0x180121190  lea     rcx, [rbp+70h+var_F0]; void *
0x180121194  call    memset_0
0x180121199  mov     [rsp+170h+var_138], ebx
0x18012119d  test    edi, edi
0x18012119f  js      loc_1801213AE
0x1801211a5  movzx   eax, word ptr [rsi+0F0h]
0x1801211ac  mov     [rbp+70h+var_CA], ax
0x1801211b0  cmp     [rsp+170h+var_140], r12b
0x1801211b5  jz      short loc_1801211C0
0x1801211b7  movups  xmm0, cs:xmmword_1802CB000
0x1801211be  jmp     short loc_1801211D5
0x1801211c0  test    r15d, r15d
0x1801211c3  jz      short loc_1801211CE
0x1801211c5  movups  xmm0, cs:xmmword_1802CAFF0
0x1801211cc  jmp     short loc_1801211D5
0x1801211ce  movups  xmm0, cs:xmmword_1802CAFE0
0x1801211d5  movdqu  [rbp+70h+var_EC], xmm0
0x1801211da  lea     rbx, [rsi+0C8h]
0x1801211e1  mov     rcx, rbx; pguid
0x1801211e4  call    cs:__imp_CoCreateGuid
0x1801211ea  movups  xmm0, xmmword ptr [rbx]
0x1801211ed  movdqu  [rbp+70h+var_DC], xmm0
0x1801211f2  movzx   eax, word ptr [rsi+0D8h]
0x1801211f9  mov     [rbp+70h+var_CC], ax
0x1801211fd  mov     [rbp+70h+var_C8], r14d
0x180121201  mov     ecx, [rsi+78h]
0x180121204  lea     rdx, ds:0[rcx*4]
0x18012120c  lea     r8, [rsi+70h]
0x180121210  test    ecx, ecx
0x180121212  jz      short loc_18012121D
0x180121214  mov     rax, [r8]
0x180121217  mov     r9d, [rdx+rax]
0x18012121b  jmp     short loc_180121220
0x18012121d  xor     r9d, r9d
0x180121220  mov     [rbp+70h+var_C4], r9d
0x180121224  mov     [rbp+70h+var_C0], ecx
0x180121227  mov     [rbp+70h+var_BC], 94h
0x18012122e  test    ecx, ecx
0x180121230  jz      short loc_180121240
0x180121232  lea     eax, [rcx+1]
0x180121235  mov     [rbp+70h+var_C0], eax
0x180121238  mov     rax, [r8]
0x18012123b  mov     eax, [rdx+rax]
0x18012123e  jmp     short loc_180121242
0x180121240  xor     eax, eax
0x180121242  lea     r10d, ds:3[rax*2]
0x18012124a  mov     r11d, 0FFFFFFFCh
0x180121250  and     r10d, r11d
0x180121253  add     r10d, 94h
0x18012125a  mov     r8d, [rsi+0A8h]
0x180121261  lea     rcx, ds:0[r8*4]
0x180121269  lea     rdx, [rsi+0A0h]
0x180121270  test    r8d, r8d
0x180121273  jz      short loc_18012127E
0x180121275  mov     rax, [rdx]
0x180121278  mov     r9d, [rcx+rax]
0x18012127c  jmp     short loc_180121281
0x18012127e  xor     r9d, r9d
0x180121281  mov     [rbp+70h+var_B8], r9d
0x180121285  mov     [rbp+70h+var_B4], r10d
0x180121289  test    r8d, r8d
0x18012128c  jz      short loc_180121296
0x18012128e  mov     rax, [rdx]
0x180121291  mov     eax, [rcx+rax]
0x180121294  jmp     short loc_180121298
0x180121296  xor     eax, eax
0x180121298  lea     edx, ds:3[rax*2]
0x18012129f  and     edx, r11d
0x1801212a2  add     edx, r10d
0x1801212a5  mov     ecx, [rsi+138h]
0x1801212ab  mov     [rbp+70h+var_B0], ecx
0x1801212ae  mov     [rbp+70h+var_AC], edx
0x1801212b1  test    r15d, r15d
0x1801212b4  jnz     short loc_1801212BE
0x1801212b6  lea     eax, [rcx+rcx*2]
0x1801212b9  lea     ecx, [rdx+rax*4]
0x1801212bc  jmp     short loc_1801212C3
0x1801212be  shl     ecx, 4
0x1801212c1  add     ecx, edx
0x1801212c3  mov     eax, [rsi+0C4h]
0x1801212c9  mov     [rbp+70h+var_94], eax
0x1801212cc  mov     [rbp+70h+var_90], ecx
0x1801212cf  lea     eax, [rax+rax*2]
0x1801212d2  lea     edx, [rcx+rax*4]
0x1801212d5  mov     r8, [rsp+170h+var_110]
0x1801212da  mov     eax, r8d
0x1801212dd  neg     eax
0x1801212df  sbb     ecx, ecx
0x1801212e1  and     ecx, edx
0x1801212e3  mov     [rbp+70h+var_6C], ecx
0x1801212e6  lea     ecx, ds:3[r8*2]
0x1801212ee  and     ecx, r11d
0x1801212f1  add     ecx, edx
0x1801212f3  mov     eax, dword ptr [rsp+170h+var_130]
0x1801212f7  mov     [rbp+70h+var_A8], eax
0x1801212fa  mov     [rbp+70h+var_A4], ecx
0x1801212fd  lea     ebx, [rcx+rax*8]
0x180121300  mov     [rsp+170h+var_138], ebx
0x180121304  cmp     [rsi+0E8h], r12d
0x18012130b  jz      short loc_18012133E
0x18012130d  mov     [rbp+70h+var_A0], ebx
0x180121310  lea     r14d, [rbx+rax*4]
0x180121314  mov     ebx, r14d
0x180121317  mov     [rsp+170h+var_138], ebx
  ... truncated ...
```
