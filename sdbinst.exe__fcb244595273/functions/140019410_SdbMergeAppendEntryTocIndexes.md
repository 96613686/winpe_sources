# SdbMergeAppendEntryTocIndexes

- ea: `0x140019410`
- end: `0x14001a244`
- name: `SdbMergeAppendEntryTocIndexes`
- size: `3636`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `1`
- callee_count: `17`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x14001d808`

## callees

- `0x14001008c`
- `0x140013898`
- `0x140013938`
- `0x140013d54`
- `0x140014380`
- `0x140014500`
- `0x140014b64`
- `0x140014d4c`
- `0x1400150b8`
- `0x140015838`
- `0x140015e14`
- `0x140016070`
- `0x140016148`
- `0x140018b4c`
- `0x140019410`
- `0x14002e3d6`
- `0x14002e3e2`

## import_xrefs

- `msvcrt!qsort` at `0x140019d1c`
- `msvcrt!qsort` at `0x140019d1c`
- `ntdll!RtlAllocateHeap` at `0x140019609`
- `ntdll!RtlAllocateHeap` at `0x1400198f0`
- `ntdll!RtlAllocateHeap` at `0x140019be9`
- `ntdll!RtlAllocateHeap` at `0x140019de8`
- `ntdll!RtlAllocateHeap` at `0x14001a010`
- `ntdll!RtlAllocateHeap` at `0x140019609`
- `ntdll!RtlAllocateHeap` at `0x1400198f0`
- `ntdll!RtlAllocateHeap` at `0x140019be9`
- `ntdll!RtlAllocateHeap` at `0x140019de8`
- `ntdll!RtlAllocateHeap` at `0x14001a010`
- `ntdll!RtlFreeHeap` at `0x14001a20c`
- `ntdll!RtlFreeHeap` at `0x14001a220`
- `ntdll!RtlFreeHeap` at `0x14001a20c`
- `ntdll!RtlFreeHeap` at `0x14001a220`
- `ntdll!RtlReAllocateHeap` at `0x140019913`
- `ntdll!RtlReAllocateHeap` at `0x140019c0c`
- `ntdll!RtlReAllocateHeap` at `0x14001a03b`
- `ntdll!RtlReAllocateHeap` at `0x140019913`
- `ntdll!RtlReAllocateHeap` at `0x140019c0c`
- `ntdll!RtlReAllocateHeap` at `0x14001a03b`

## string_xrefs

- `0x140019479`: `PDB is not writeable`
- `0x140019d70`: `SdbBeginWriteListTag failed to write TAG_UPDATED_ENTRY_INDEXES`
- `0x140019d37`: `SdbBeginWriteListTag failed to write TAG_SDB_MERGE_METADATA`
- `0x14001a0d3`: `SdbWriteBinaryTag failed to write index bits`
- `0x14001a10d`: `SdbWriteBinaryTag failed to write index bits`
- `0x14001a19b`: `SdbBeginWriteListTag failed to write TAG_INDEX`
- `0x14001a0c1`: `SdbEndWriteListTag failed to write end of TAG_INDEX`
- `0x14001a12f`: `SdbEndWriteListTag failed to write end of TAG_INDEX`
- `0x14001a17d`: `SdbWriteWORDTag failed to write TAG_INDEX_KEY`
- `0x14001a18c`: `SdbWriteWORDTag failed to write TAG_INDEX_TAG`
- `0x14001a1bb`: `SdbEndWriteListTag failed to write end of TAG_UPDATED_ENTRY_INDEXES`
- `0x14001a16e`: `SdbWriteDWORDTag failed to write TAG_INDEX_FLAGS`
- `0x14001a1da`: `SdbEndWriteListTag failed to write end of TAG_SDB_MERGE_METADATA`

## pseudocode

```c
__int64 __fastcall SdbMergeAppendEntryTocIndexes(__int64 a1)
{
  __m128i *v1; // r12
  unsigned int v3; // ebx
  HANDLE v4; // rax
  char *v5; // rdi
  unsigned int FirstTag; // eax
  unsigned int v7; // edi
  size_t v8; // r13
  unsigned int FirstChild; // ebx
  __int16 TagFromTagID; // cx
  unsigned int i; // eax
  PVOID ProcessHeap; // r9
  unsigned __int64 v13; // r15
  __m128i *v14; // rax
  __m128i *v15; // rbx
  unsigned int NextChild; // r13d
  __int16 v17; // r15
  unsigned int v18; // ebx
  unsigned int v19; // r13d
  __int16 v20; // ax
  __int16 v21; // cx
  __int64 v22; // rax
  __int16 v23; // di
  unsigned int v24; // r15d
  int v25; // edi
  unsigned __int64 IndexKeyFromString; // rdi
  __m128i v27; // xmm6
  const WCHAR *StringTagPtr; // rax
  int v29; // eax
  size_t v30; // r13
  size_t v31; // rdi
  unsigned __int128 v32; // rax
  size_t v33; // r15
  __m128i *v34; // rax
  __m128i *v35; // rbx
  __m128i *v36; // rax
  int v37; // eax
  unsigned int k; // eax
  unsigned int v39; // r13d
  __int16 v40; // cx
  __int64 v41; // rax
  __int16 v42; // di
  unsigned int v43; // r15d
  int v44; // edi
  unsigned __int64 v45; // rdi
  __m128i v46; // xmm6
  const WCHAR *v47; // rax
  int v48; // eax
  size_t v49; // r13
  size_t v50; // rdi
  unsigned __int128 v51; // rax
  size_t v52; // r15
  __m128i *v53; // rax
  __m128i *v54; // rbx
  __m128i *v55; // rax
  __int64 v56; // r8
  unsigned __int64 v57; // r15
  size_t v58; // r13
  PVOID v59; // r9
  char *v60; // rax
  char *v61; // rbx
  size_t v62; // rdx
  unsigned int v63; // ecx
  size_t v64; // rax
  __int64 v65; // r8
  __int8 *v66; // rbx
  unsigned __int64 v67; // rax
  unsigned __int64 v68; // kr00_8
  __int64 v69; // r8
  unsigned int v70; // ecx
  unsigned __int64 v71; // rbx
  unsigned __int128 v72; // rax
  char *v73; // rax
  char *v74; // rax
  int v75; // eax
  __int16 j; // [rsp+30h] [rbp-D0h]
  unsigned int v78; // [rsp+30h] [rbp-D0h]
  PVOID HeapHandle; // [rsp+38h] [rbp-C8h]
  unsigned int v80; // [rsp+40h] [rbp-C0h]
  unsigned int v81; // [rsp+40h] [rbp-C0h]
  __m128i v82; // [rsp+48h] [rbp-B8h]
  __m128i v83; // [rsp+48h] [rbp-B8h]
  char *v84; // [rsp+48h] [rbp-B8h]
  char v85; // [rsp+58h] [rbp-A8h]
  size_t v86; // [rsp+60h] [rbp-A0h]
  __int128 Buf1; // [rsp+70h] [rbp-90h] BYREF
  unsigned int v88; // [rsp+80h] [rbp-80h]
  unsigned int v89; // [rsp+84h] [rbp-7Ch]
  size_t NumOfElements; // [rsp+88h] [rbp-78h]
  size_t Size; // [rsp+90h] [rbp-70h]
  unsigned __int64 v92; // [rsp+98h] [rbp-68h]
  __int64 v93; // [rsp+A0h] [rbp-60h]
  PVOID Heap[2]; // [rsp+A8h] [rbp-58h]
  __int128 v95; // [rsp+B8h] [rbp-48h]
  PVOID v96[2]; // [rsp+C8h] [rbp-38h]
  HANDLE v97[2]; // [rsp+D8h] [rbp-28h]
  __int128 v98; // [rsp+E8h] [rbp-18h]
  PVOID P[2]; // [rsp+F8h] [rbp-8h]
  __int64 v100; // [rsp+108h] [rbp+8h]
  size_t v101[2]; // [rsp+110h] [rbp+10h] BYREF
  char v102[16]; // [rsp+120h] [rbp+20h] BYREF

  v1 = 0;
  *(_OWORD *)v97 = 0;
  v98 = 0;
  *(_OWORD *)P = 0;
  *(_OWORD *)Heap = 0;
  v95 = 0;
  *(_OWORD *)v96 = 0;
  if ( !a1 )
    goto LABEL_2;
  if ( !*(_DWORD *)(a1 + 16) )
  {
    AslLogCallPrintf(1, "SdbMergeAppendEntryTocIndexes", 3494, "PDB is not writeable");
LABEL_2:
    v3 = -1073741585;
LABEL_3:
    v1 = (__m128i *)P[1];
    v4 = v97[0];
    v5 = (char *)v96[1];
    goto LABEL_187;
  }
  FirstTag = SdbFindFirstTag(a1, 0, 28673);
  v89 = FirstTag;
  v7 = FirstTag;
  if ( !FirstTag )
  {
    AslLogCallPrintf(1, "SdbMergeAppendEntryTocIndexes", 3501, "Failed to find TAG_DATABASE");
    v3 = -1073741596;
    goto LABEL_3;
  }
  if ( (unsigned int)SdbGetTagDataSize(a1, FirstTag) == 0x20000000 )
  {
    AslLogCallPrintf(1, "SdbMergeAppendEntryTocIndexes", 3510, "TAG_DATABASE is not finished");
    v3 = -1073741480;
    goto LABEL_3;
  }
  Size = 0;
  v8 = 0;
  FirstChild = SdbGetFirstChild(a1, v7);
  if ( FirstChild )
  {
    do
    {
      TagFromTagID = SdbGetTagFromTagID(a1, FirstChild);
      if ( (TagFromTagID & 0xF000) == 0x7000 )
      {
        if ( TagFromTagID == 28674 )
        {
          for ( i = SdbGetFirstChild(a1, FirstChild); i; i = SdbGetNextChild(a1, FirstChild, i) )
            ++v8;
        }
        else
        {
          ++v8;
        }
      }
      FirstChild = SdbGetNextChild(a1, v7, FirstChild);
    }
    while ( FirstChild );
    Size = v8;
  }
  NumOfElements = 0;
  v86 = 0;
  ProcessHeap = NtCurrentPeb()->ProcessHeap;
  HeapHandle = ProcessHeap;
  v100 = 32;
  v93 = 32;
  v92 = 16;
  if ( v8 )
  {
    if ( v8 + 31 >= v8
      && (*(_QWORD *)&Buf1 = 0, is_mul_ok(0, 0x10u))
      && (v13 = (v8 + 31) & 0xFFFFFFFFFFFFFFE0uLL, *(_QWORD *)&Buf1 = 0, v86 = v13, is_mul_ok(v13, 0x10u)) )
    {
      v14 = (__m128i *)RtlAllocateHeap(ProcessHeap, (v13 * (unsigned __int128)0x10u) >> 64, 16 * v13);
      v15 = v14;
      if ( v14 )
      {
        memset_0(v14, 0, 16 * v13);
        v1 = v15;
        goto LABEL_29;
      }
      v3 = -1073741801;
    }
    else
    {
      v3 = -1073741675;
    }
    *(_OWORD *)v97 = 0;
    v98 = 0;
    *(_OWORD *)P = 0;
    AslLogCallPrintf(1, "SdbMergeAppendEntryTocIndexes", 3542, "RtlArrayInitialize failed to initialize array [%x]", v3);
    goto LABEL_3;
  }
LABEL_29:
  NextChild = SdbGetFirstChild(a1, v89);
  v80 = NextChild;
  if ( NextChild )
  {
    v17 = 0;
    v18 = 0;
    for ( j = 0; ; v17 = j )
    {
      v18 = NextChild & 0x3FFFFFFF | v18 & 0xC0000000;
      v82.m128i_i32[3] = v18;
      v19 = v18 & 0x3FFFFFFF;
      if ( (v18 & 0x3FFFFFFF) == 0 )
        goto LABEL_105;
      v20 = SdbGetTagFromTagID(a1, v19);
      v82.m128i_i16[4] = v20;
      v21 = v20;
      if ( v17 == 28674 || (v20 & 0xF000) != 0x7000 )
        goto LABEL_67;
      v22 = 0;
      while ( *((_WORD *)qword_140039F70 + 5 * v22) != v21 )
      {
        if ( (unsigned __int64)++v22 >= 0x24 )
        {
          v17 = 0;
          j = 0;
          goto LABEL_67;
        }
      }
      v23 = *((_WORD *)qword_140039F70 + 5 * v22 + 1);
      v82.m128i_i16[5] = v23;
      v17 = v23;
      j = v23;
      if ( !v23 )
        goto LABEL_67;
      v24 = SdbFindFirstTag(a1, v19, v23);
      if ( !v24 )
        break;
      v25 = v23 & 0xF000;
      v82.m128i_i64[0] = 0;
      if ( ((v25 - 24576) & 0xFFFFDFFF) != 0 )
      {
        if ( v25 != 36864 )
          break;
        IndexKeyFromString = 0;
        if ( (unsigned int)SdbGetTagDataSize(a1, v24) == 16 )
        {
          Buf1 = SDB_GUID_EMPTY;
          v27 = *(__m128i *)SdbReadGUIDTag(v101, a1, v24, &Buf1);
          Buf1 = (__int128)v27;
          if ( memcmp_0(&Buf1, &SDB_GUID_EMPTY, 0x10u) )
          {
            IndexKeyFromString = v27.m128i_i64[0] ^ _mm_srli_si128(v27, 8).m128i_u64[0];
            v82.m128i_i64[0] = IndexKeyFromString;
          }
        }
      }
      else
      {
        StringTagPtr = (const WCHAR *)SdbGetStringTagPtr(a1, v24);
        if ( !StringTagPtr )
          break;
        IndexKeyFromString = SdbMakeIndexKeyFromStringEx(StringTagPtr, 0);
        v82.m128i_i64[0] = IndexKeyFromString;
      }
      if ( !IndexKeyFromString )
        break;
      v29 = SdbFindFirstTag(a1, v19, 4120);
      v30 = NumOfElements;
      v82.m128i_i8[15] = HIBYTE(v18) & 0x7F | (v29 != 0 ? 0x80 : 0);
      if ( NumOfElements >= v86 )
      {
        if ( NumOfElements + 1 <= v86 )
        {
          v3 = -1073741811;
          goto LABEL_65;
        }
        if ( v93 + NumOfElements < NumOfElements + 1
          || (*(_QWORD *)&Buf1 = 0, !is_mul_ok(v86, v92))
          || (*(_QWORD *)&Buf1 = 0,
              v31 = (v93 + NumOfElements) & ~(v93 - 1),
              v32 = v31 * (unsigned __int128)v92,
              v33 = v31 * v92,
              !is_mul_ok(v31, v92)) )
        {
          v3 = -1073741675;
LABEL_65:
          v37 = v3;
LABEL_110:
          v56 = 3554;
LABEL_111:
          AslLogCallPrintf(
            1,
            "SdbMergeAppendEntryTocIndexes",
            v56,
            "Failed to append table of contents entry [%x]",
            v37);
LABEL_112:
          v5 = (char *)v96[1];
          goto LABEL_186;
        }
        if ( v1 )
        {
          v35 = (__m128i *)RtlReAllocateHeap(HeapHandle, DWORD2(v32), v1, v31 * v92);
        }
        else
        {
          v34 = (__m128i *)RtlAllocateHeap(HeapHandle, DWORD2(v32), v31 * v92);
          v35 = v34;
          if ( v34 )
            memset_0(v34, 0, v33);
        }
        if ( !v35 )
        {
          v3 = -1073741801;
          goto LABEL_65;
        }
        v1 = v35;
        v86 = v31;
      }
      *(_QWORD *)&Buf1 = 0;
      if ( !is_mul_ok(v92, v30) || (v36 = (__m128i *)((char *)v1 + v92 * v30), v36 < v1) )
      {
        v37 = -1073741675;
        v3 = -1073741675;
        goto LABEL_110;
      }
      NumOfElements = v30 + 1;
      *v36 = v82;
      v18 = _mm_cvtsi128_si32(_mm_srli_si128(v82, 12));
LABEL_105:
      NextChild = SdbGetNextChild(a1, v89, v80);
      v80 = NextChild;
      if ( !NextChild )
        goto LABEL_115;
    }
    v21 = v82.m128i_i16[4];
    v17 = j;
LABEL_67:
    if ( v21 != 28674 )
      goto LABEL_105;
    for ( k = SdbGetFirstChild(a1, v80); ; k = SdbGetNextChild(a1, v80, v88) )
    {
      v88 = k;
      if ( !k )
        goto LABEL_105;
      v83.m128i_i32[3] = k & 0x3FFFFFFF | v18 & 0xC0000000;
      v85 = v83.m128i_i8[15] | 0x40;
      v83.m128i_i8[15] |= 0x40u;
      v18 = v83.m128i_u32[3];
      v39 = v83.m128i_i32[3] & 0x3FFFFFFF;
      if ( (v83.m128i_i32[3] & 0x3FFFFFFF) != 0 )
      {
        v40 = SdbGetTagFromTagID(a1, v39);
        v83.m128i_i16[4] = v40;
        if ( v17 != 28674 && (v40 & 0xF000) == 0x7000 )
        {
          v41 = 0;
          while ( *((_WORD *)qword_140039F70 + 5 * v41) != v40 )
          {
            if ( (unsigned __int64)++v41 >= 0x24 )
            {
              v17 = 0;
              j = 0;
              goto LABEL_103;
            }
          }
          v42 = *((_WORD *)qword_140039F70 + 5 * v41 + 1);
          v83.m128i_i16[5] = v42;
          v17 = v42;
          j = v42;
          if ( v42 )
            break;
        }
      }
LABEL_103:
      ;
    }
    v43 = SdbFindFirstTag(a1, v39, v42);
    if ( v43 )
    {
      v44 = v42 & 0xF000;
      v83.m128i_i64[0] = 0;
      if ( ((v44 - 24576) & 0xFFFFDFFF) != 0 )
      {
        if ( v44 == 36864 )
        {
          v45 = 0;
          if ( (unsigned int)SdbGetTagDataSize(a1, v43) == 16 )
          {
            Buf1 = SDB_GUID_EMPTY;
            v46 = *(__m128i *)SdbReadGUIDTag(v102, a1, v43, &Buf1);
            Buf1 = (__int128)v46;
            if ( memcmp_0(&Buf1, &SDB_GUID_EMPTY, 0x10u) )
            {
              v45 = v46.m128i_i64[0] ^ _mm_srli_si128(v46, 8).m128i_u64[0];
              v83.m128i_i64[0] = v45;
            }
          }
LABEL_85:
          if ( v45 )
          {
            v48 = SdbFindFirstTag(a1, v39, 4120);
            v49 = NumOfElements;
            v83.m128i_i8[15] = v85 & 0x7F | (v48 != 0 ? 0x80 : 0);
            if ( NumOfElements >= v86 )
            {
              if ( NumOfElements + 1 <= v86 )
              {
                v3 = -1073741811;
                goto LABEL_108;
              }
              if ( NumOfElements + v93 < NumOfElements + 1
                || (*(_QWORD *)&Buf1 = 0, !is_mul_ok(v86, v92))
                || (*(_QWORD *)&Buf1 = 0,
                    v50 = (NumOfElements + v93) & ~(v93 - 1),
                    v51 = v50 * (unsigned __int128)v92,
                    v52 = v50 * v92,
                    !is_mul_ok(v50, v92)) )
              {
                v3 = -1073741675;
LABEL_108:
                v37 = v3;
LABEL_114:
                v56 = 3570;
                goto LABEL_111;
              }
              if ( v1 )
              {
                v54 = (__m128i *)RtlReAllocateHeap(HeapHandle, DWORD2(v51), v1, v50 * v92);
              }
              else
              {
                v53 = (__m128i *)RtlAllocateHeap(HeapHandle, DWORD2(v51), v50 * v92);
                v54 = v53;
                if ( v53 )
                  memset_0(v53, 0, v52);
              }
              if ( !v54 )
              {
                v3 = -1073741801;
                goto LABEL_108;
              }
              v1 = v54;
              v86 = v50;
            }
            *(_QWORD *)&Buf1 = 0;
            if ( !is_mul_ok(v92, v49) || (v55 = (__m128i *)((char *)v1 + v92 * v49), v55 < v1) )
            {
              v37 = -1073741675;
              v3 = -1073741675;
              goto LABEL_114;
            }
            NumOfElements = v49 + 1;
            *v55 = v83;
            v18 = _mm_cvtsi128_si32(_mm_srli_si128(v83, 12));
          }
        }
      }
      else
      {
        v47 = (const WCHAR *)SdbGetStringTagPtr(a1, v43);
        if ( v47 )
        {
          v45 = SdbMakeIndexKeyFromStringEx(v47, 0);
          v83.m128i_i64[0] = v45;
          goto LABEL_85;
        }
      }
    }
    v17 = j;
    goto LABEL_103;
  }
LABEL_115:
  qsort(v1, NumOfElements, 0x10u, SdbpMergeCompareTocEntries);
  v78 = SdbBeginWriteListTag(a1, 28751);
  if ( !v78 )
  {
    AslLogCallPrintf(
      1,
      "SdbMergeAppendEntryTocIndexes",
      3585,
      "SdbBeginWriteListTag failed to write TAG_SDB_MERGE_METADATA");
LABEL_117:
    v3 = -1073741823;
    goto LABEL_112;
  }
  v88 = SdbBeginWriteListTag(a1, 30724);
  if ( !v88 )
  {
    AslLogCallPrintf(
      1,
      "SdbMergeAppendEntryTocIndexes",
      3592,
      "SdbBeginWriteListTag failed to write TAG_UPDATED_ENTRY_INDEXES");
    goto LABEL_117;
  }
  v57 = 0;
  v58 = 0;
  v5 = 0;
  v59 = NtCurrentPeb()->ProcessHeap;
  Heap[0] = v59;
  if ( Size )
  {
    if ( Size + 31 >= Size
      && (*(_QWORD *)&Buf1 = 0, is_mul_ok(0, 0xCu))
      && (v58 = (Size + 31) & 0xFFFFFFFFFFFFFFE0uLL, *(_QWORD *)&Buf1 = 0, Size = 12 * v58, is_mul_ok(v58, 0xCu)) )
    {
      v60 = (char *)RtlAllocateHeap(v59, (v58 * (unsigned __int128)0xCu) >> 64, 12 * v58);
      v61 = v60;
      if ( v60 )
      {
        memset_0(v60, 0, Size);
        v5 = v61;
        goto LABEL_129;
      }
      v3 = -1073741801;
    }
    else
    {
      v3 = -1073741675;
    }
    *(_OWORD *)Heap = 0;
    v95 = 0;
    *(_OWORD *)v96 = 0;
    AslLogCallPrintf(
      1,
      "SdbMergeAppendEntryTocIndexes",
      3609,
      "RtlArrayInitializeBase failed to initialize array [%x]",
      v3);
    goto LABEL_112;
  }
LABEL_129:
  v62 = NumOfElements;
  v63 = 0;
  v93 = 0;
  v64 = 0;
  v81 = 0;
  v65 = 0;
  Size = 0;
  if ( NumOfElements )
  {
    while ( 1 )
    {
      v66 = 0;
      if ( v64 < v62 )
      {
        v68 = v64;
        v67 = v92 * v64;
        *(_QWORD *)&Buf1 = 0;
        if ( !is_mul_ok(v92, v68) || (v66 = &v1->m128i_i8[v67], &v1->m128i_i8[v67] < (__int8 *)v1) )
          v66 = 0;
      }
      if ( !v65 || *(_WORD *)(v65 + 8) != *((_WORD *)v66 + 4) || *(_WORD *)(v65 + 10) != *((_WORD *)v66 + 5) )
      {
        if ( v63 )
        {
          if ( !(unsigned int)SdbpWriteTagData(a1, 38913, v5, (unsigned int)(12 * v57)) )
          {
            AslLogCallPrintf(1, "SdbMergeAppendEntryTocIndexes", 3631, "SdbWriteBinaryTag failed to write index bits");
            goto LABEL_185;
          }
          if ( !(unsigned int)SdbEndWriteListTag(a1, v81) )
          {
            AslLogCallPrintf(
              1,
              "SdbMergeAppendEntryTocIndexes",
              3637,
              "SdbEndWriteListTag failed to write end of TAG_INDEX");
            goto LABEL_185;
          }
          if ( v57 )
          {
            *(_QWORD *)&Buf1 = 0;
            if ( is_mul_ok(v57, 0xCu) )
            {
              memset_0(v5, (v57 * (unsigned __int128)0xCuLL) >> 64, 12 * v57);
              v57 = 0;
            }
          }
        }
        v81 = SdbBeginWriteListTag(a1, 30723);
        if ( !v81 )
        {
          AslLogCallPrintf(1, "SdbMergeAppendEntryTocIndexes", 3648, "SdbBeginWriteListTag failed to write TAG_INDEX");
          goto LABEL_185;
        }
        if ( !(unsigned int)SdbWriteWORDTag(a1, 14338, *((unsigned __int16 *)v66 + 4)) )
        {
          AslLogCallPrintf(1, "SdbMergeAppendEntryTocIndexes", 3654, "SdbWriteWORDTag failed to write TAG_INDEX_TAG");
          goto LABEL_185;
        }
        if ( !(unsigned int)SdbWriteWORDTag(a1, 14339, *((unsigned __int16 *)v66 + 5)) )
        {
          AslLogCallPrintf(1, "SdbMergeAppendEntryTocIndexes", 3660, "SdbWriteWORDTag failed to write TAG_INDEX_KEY");
          goto LABEL_185;
        }
        if ( !(unsigned int)SdbWriteDWORDTag(a1, 16406, 0) )
        {
          AslLogCallPrintf(1, "SdbMergeAppendEntryTocIndexes", 3666, "SdbWriteDWORDTag failed to write TAG_INDEX_FLAGS");
          goto LABEL_185;
        }
        v93 = (__int64)v66;
      }
      v69 = *(_QWORD *)v66;
      v70 = *((_DWORD *)v66 + 3);
      *(_QWORD *)&Buf1 = *(_QWORD *)v66;
      v89 = v70;
      if ( v57 >= v58 )
      {
        if ( v57 + 1 <= v58 )
        {
          v3 = -1073741811;
          goto LABEL_166;
        }
        if ( v100 + v57 < v57 + 1
          || !is_mul_ok(v58, 0xCu)
          || (v71 = (v100 + v57) & ~(v100 - 1),
              v72 = v71 * (unsigned __int128)0xCuLL,
              v101[0] = 12 * v71,
              !is_mul_ok(v71, 0xCu)) )
        {
          v3 = -1073741675;
LABEL_166:
          v75 = v3;
LABEL_175:
          AslLogCallPrintf(1, "SdbMergeAppendEntryTocIndexes", 3677, "RtlArrayAppend failed [%x]", v75);
          goto LABEL_186;
        }
        if ( v5 )
        {
          v73 = (char *)RtlReAllocateHeap(Heap[0], DWORD2(v72), v5, 12 * v71);
        }
        else
        {
          v73 = (char *)RtlAllocateHeap(Heap[0], DWORD2(v72), 12 * v71);
          v84 = v73;
          if ( v73 )
          {
            memset_0(v73, 0, v101[0]);
            v73 = v84;
          }
        }
        if ( !v73 )
        {
          v3 = -1073741801;
          goto LABEL_166;
        }
        v70 = v89;
        v5 = v73;
        v69 = Buf1;
        v58 = v71;
      }
      *(_QWORD *)&Buf1 = 0;
      if ( !is_mul_ok(0xCu, v57) || (v74 = &v5[12 * v57], v74 < v5) )
      {
        v75 = -1073741675;
        v3 = -1073741675;
        goto LABEL_175;
      }
      *(_QWORD *)v74 = v69;
      *((_DWORD *)v74 + 2) = v70 & 0x3FFFFFFF;
      ++v57;
      v62 = NumOfElements;
      v64 = Size + 1;
      Size = v64;
      if ( v64 >= NumOfElements )
        break;
      v63 = v81;
      v65 = v93;
    }
    if ( !v81 )
      goto LABEL_180;
    if ( !(unsigned int)SdbpWriteTagData(a1, 38913, v5, (unsigned int)(12 * v57)) )
    {
      AslLogCallPrintf(1, "SdbMergeAppendEntryTocIndexes", 3687, "SdbWriteBinaryTag failed to write index bits");
      goto LABEL_185;
    }
    v3 = 0;
    if ( !(unsigned int)SdbEndWriteListTag(a1, v81) )
    {
      AslLogCallPrintf(1, "SdbMergeAppendEntryTocIndexes", 3693, "SdbEndWriteListTag failed to write end of TAG_INDEX");
      goto LABEL_185;
    }
  }
  else
  {
LABEL_180:
    v3 = 0;
  }
  if ( (unsigned int)SdbEndWriteListTag(a1, v88) )
  {
    if ( (unsigned int)SdbEndWriteListTag(a1, v78) )
      goto LABEL_186;
    AslLogCallPrintf(
      1,
      "SdbMergeAppendEntryTocIndexes",
      3708,
      "SdbEndWriteListTag failed to write end of TAG_SDB_MERGE_METADATA");
  }
  else
  {
    AslLogCallPrintf(
      1,
      "SdbMergeAppendEntryTocIndexes",
      3702,
      "SdbEndWriteListTag failed to write end of TAG_UPDATED_ENTRY_INDEXES");
  }
LABEL_185:
  v3 = -1073741823;
LABEL_186:
  v4 = HeapHandle;
LABEL_187:
  if ( v1 )
    RtlFreeHeap(v4, 0, v1);
  if ( v5 )
    RtlFreeHeap(Heap[0], 0, v5);
  return v3;
}

```

## disassembly

```asm
0x140019410  mov     rax, rsp
0x140019413  push    rbp
0x140019414  push    rbx
0x140019415  push    rsi
0x140019416  push    rdi
0x140019417  push    r12
0x140019419  push    r13
0x14001941b  push    r14
0x14001941d  push    r15
0x14001941f  lea     rbp, [rsp-48h]
0x140019424  sub     rsp, 148h
0x14001942b  xorps   xmm0, xmm0
0x14001942e  movaps  xmmword ptr [rax-58h], xmm6
0x140019432  xorps   xmm1, xmm1
0x140019435  xor     r12d, r12d
0x140019438  mov     r14, rcx
0x14001943b  movups  xmmword ptr [rbp+80h+var_A8], xmm0
0x14001943f  movups  [rbp+80h+var_98], xmm0
0x140019443  movups  xmmword ptr [rbp+80h+P], xmm0
0x140019447  movups  xmmword ptr [rbp+80h+Heap], xmm1
0x14001944b  movups  [rbp+80h+var_C8], xmm1
0x14001944f  movups  xmmword ptr [rbp+80h+var_B8], xmm1
0x140019453  movups  [rsp+180h+var_138], xmm0
0x140019458  test    rcx, rcx
0x14001945b  jnz     short loc_140019473
0x14001945d  mov     ebx, 0C00000EFh
0x140019462  mov     r12, [rbp+80h+P+8]
0x140019466  mov     rax, [rbp+80h+var_A8]
0x14001946a  mov     rdi, [rbp+80h+var_B8+8]
0x14001946e  jmp     loc_14001A1FF
0x140019473  cmp     [rcx+10h], r12d
0x140019477  jnz     short loc_140019499
0x140019479  lea     r9, aPdbIsNotWritea; "PDB is not writeable"
0x140019480  mov     r8d, 0DA6h
0x140019486  lea     rdx, aSdbmergeappend; "SdbMergeAppendEntryTocIndexes"
0x14001948d  mov     ecx, 1
0x140019492  call    AslLogCallPrintf
0x140019497  jmp     short loc_14001945D
0x140019499  xor     edx, edx
0x14001949b  mov     r8d, 7001h
0x1400194a1  call    SdbFindFirstTag
0x1400194a6  mov     [rbp+80h+var_FC], eax
0x1400194a9  mov     edi, eax
0x1400194ab  test    eax, eax
0x1400194ad  jnz     short loc_1400194D2
0x1400194af  lea     r9, aFailedToFindTa_2; "Failed to find TAG_DATABASE"
0x1400194b6  mov     r8d, 0DADh
0x1400194bc  lea     rdx, aSdbmergeappend; "SdbMergeAppendEntryTocIndexes"
0x1400194c3  lea     ecx, [rax+1]
0x1400194c6  call    AslLogCallPrintf
0x1400194cb  mov     ebx, 0C00000E4h
0x1400194d0  jmp     short loc_140019462
0x1400194d2  mov     edx, edi
0x1400194d4  mov     rcx, r14
0x1400194d7  call    SdbGetTagDataSize
0x1400194dc  cmp     eax, 20000000h
0x1400194e1  jnz     short loc_14001950B
0x1400194e3  lea     r9, aTagDatabaseIsN; "TAG_DATABASE is not finished"
0x1400194ea  mov     r8d, 0DB6h
0x1400194f0  lea     rdx, aSdbmergeappend; "SdbMergeAppendEntryTocIndexes"
0x1400194f7  mov     ecx, 1
0x1400194fc  call    AslLogCallPrintf
0x140019501  mov     ebx, 0C0000158h
0x140019506  jmp     loc_140019462
0x14001950b  mov     edx, edi
0x14001950d  mov     [rbp+80h+Size], r12
0x140019511  mov     rcx, r14
0x140019514  mov     r13, r12
0x140019517  call    SdbGetFirstChild
0x14001951c  mov     ebx, eax
0x14001951e  mov     esi, 1
0x140019523  mov     r15d, 0F000h
0x140019529  test    eax, eax
0x14001952b  jz      short loc_14001958C
0x14001952d  mov     edx, ebx
0x14001952f  mov     rcx, r14
0x140019532  call    SdbGetTagFromTagID
0x140019537  movzx   ecx, ax
0x14001953a  mov     edx, 7000h
0x14001953f  and     ax, r15w
0x140019543  cmp     ax, dx
0x140019546  jnz     short loc_140019575
0x140019548  lea     eax, [rdx+2]
0x14001954b  cmp     cx, ax
0x14001954e  jnz     short loc_140019572
0x140019550  mov     edx, ebx
0x140019552  mov     rcx, r14
0x140019555  call    SdbGetFirstChild
0x14001955a  jmp     short loc_14001956C
0x14001955c  add     r13, rsi
0x14001955f  mov     r8d, eax
0x140019562  mov     edx, ebx
0x140019564  mov     rcx, r14
0x140019567  call    SdbGetNextChild
0x14001956c  test    eax, eax
0x14001956e  jnz     short loc_14001955C
0x140019570  jmp     short loc_140019575
0x140019572  add     r13, rsi
0x140019575  mov     r8d, ebx
0x140019578  mov     edx, edi
0x14001957a  mov     rcx, r14
0x14001957d  call    SdbGetNextChild
0x140019582  mov     ebx, eax
0x140019584  test    eax, eax
0x140019586  jnz     short loc_14001952D
0x140019588  mov     [rbp+80h+Size], r13
0x14001958c  mov     rax, gs:60h
0x140019595  xor     r8d, r8d
0x140019598  mov     [rbp+80h+NumOfElements], r12
0x14001959c  mov     r10d, 0C0000095h
0x1400195a2  mov     [rsp+180h+var_120], r12
0x1400195a7  mov     r9, [rax+30h]
0x1400195ab  mov     eax, 20h ; ' '
0x1400195b0  mov     [rsp+180h+HeapHandle], r9
0x1400195b5  mov     [rbp+80h+var_78], rax
0x1400195b9  mov     [rbp+80h+var_E0], rax
0x1400195bd  lea     r11d, [rax-10h]
0x1400195c1  mov     [rbp+80h+var_E8], r11
0x1400195c5  test    r13, r13
0x1400195c8  jz      loc_140019698
0x1400195ce  lea     r15, [r13+1Fh]
0x1400195d2  cmp     r15, r13
0x1400195d5  jb      short loc_140019630
0x1400195d7  mov     eax, r11d
0x1400195da  mov     qword ptr [rsp+180h+Buf1], r8
0x1400195df  mul     r8
0x1400195e2  test    rdx, rdx
0x1400195e5  jnz     short loc_140019630
0x1400195e7  and     r15, 0FFFFFFFFFFFFFFE0h
0x1400195eb  mov     qword ptr [rsp+180h+Buf1], r8
0x1400195f0  mov     eax, r11d
0x1400195f3  mov     [rsp+180h+var_120], r15
0x1400195f8  mul     r15
0x1400195fb  mov     rdi, rax
0x1400195fe  test    rdx, rdx
0x140019601  jnz     short loc_140019630
0x140019603  mov     r8, rax; Size
0x140019606  mov     rcx, r9; HeapHandle
0x140019609  call    cs:__imp_RtlAllocateHeap
0x14001960f  mov     rbx, rax
0x140019612  test    rax, rax
0x140019615  jz      short loc_140019629
0x140019617  mov     r8, rdi; Size
0x14001961a  xor     edx, edx; Val
0x14001961c  mov     rcx, rax; void *
0x14001961f  call    memset_0
0x140019624  mov     r12, rbx
0x140019627  jmp     short loc_140019698
0x140019629  mov     ebx, 0C0000017h
0x14001962e  jmp     short loc_140019633
0x140019630  mov     ebx, r10d
0x140019633  xorps   xmm0, xmm0
0x140019636  movups  xmmword ptr [rbp+80h+var_A8], xmm0
0x14001963a  movups  [rbp+80h+var_98], xmm0
0x14001963e  movups  xmmword ptr [rbp+80h+P], xmm0
0x140019642  test    ebx, ebx
0x140019644  jns     short loc_14001966A
0x140019646  lea     r9, aRtlarrayinitia; "RtlArrayInitialize failed to initialize"...
0x14001964d  mov     [rsp+180h+var_160], ebx
0x140019651  mov     r8d, 0DD6h
0x140019657  lea     rdx, aSdbmergeappend; "SdbMergeAppendEntryTocIndexes"
0x14001965e  mov     ecx, esi
0x140019660  call    AslLogCallPrintf
0x140019665  jmp     loc_140019462
0x14001966a  mov     rax, [rbp+80h+P]
0x14001966e  mov     rdi, qword ptr [rbp+80h+var_98+8]
0x140019672  mov     r12, [rbp+80h+P+8]
0x140019676  mov     [rbp+80h+var_E0], rax
0x14001967a  mov     rax, qword ptr [rbp+80h+var_98]
0x14001967e  mov     [rbp+80h+NumOfElements], rax
0x140019682  mov     rax, [rbp+80h+var_A8+8]
0x140019686  mov     [rbp+80h+var_E8], rax
0x14001968a  mov     rax, [rbp+80h+var_A8]
0x14001968e  mov     [rsp+180h+HeapHandle], rax
0x140019693  mov     [rsp+180h+var_120], rdi
0x140019698  mov     edx, [rbp+80h+var_FC]
0x14001969b  mov     rcx, r14
0x14001969e  call    SdbGetFirstChild
0x1400196a3  mov     r13d, eax
0x1400196a6  mov     [rsp+180h+var_140], eax
0x1400196aa  xor     eax, eax
0x1400196ac  test    r13d, r13d
0x1400196af  jz      loc_140019D08
0x1400196b5  movzx   r15d, word ptr [rsp+180h+var_138+0Ah]
0x1400196bb  mov     ebx, dword ptr [rsp+180h+var_138+0Ch]
0x1400196bf  mov     [rsp+180h+var_150], r15d
0x1400196c4  mov     word ptr [rsp+180h+var_138+8], ax
0x1400196c9  and     ebx, 0C0000000h
0x1400196cf  mov     eax, r13d
0x1400196d2  and     eax, 3FFFFFFFh
0x1400196d7  or      ebx, eax
0x1400196d9  mov     r13d, ebx
0x1400196dc  mov     dword ptr [rsp+180h+var_138+0Ch], ebx
0x1400196e0  and     r13d, 3FFFFFFFh
0x1400196e7  jz      loc_140019C8D
0x1400196ed  mov     edx, r13d
0x1400196f0  mov     rcx, r14
0x1400196f3  call    SdbGetTagFromTagID
0x1400196f8  mov     edi, 7002h
0x1400196fd  mov     word ptr [rsp+180h+var_138+8], ax
0x140019702  cmp     r15w, di
0x140019706  movzx   ecx, ax
0x140019709  mov     edi, 0F000h
0x14001970e  jz      loc_140019998
0x140019714  and     ax, di
0x140019717  mov     edx, 7000h
0x14001971c  cmp     ax, dx
0x14001971f  jnz     loc_140019998
0x140019725  xor     edx, edx
0x140019727  lea     r8, qword_140039F70
0x14001972e  mov     eax, edx
0x140019730  lea     rdi, [rax+rax*4]
0x140019734  cmp     [r8+rdi*2], cx
0x140019739  jz      short loc_140019750
0x14001973b  add     rax, rsi
0x14001973e  cmp     rax, 24h ; '$'
0x140019742  jb      short loc_140019730
0x140019744  mov     r15d, edx
0x140019747  mov     [rsp+180h+var_150], edx
0x14001974b  jmp     loc_140019993
0x140019750  movzx   edi, word ptr [r8+rdi*2+2]
0x140019756  mov     word ptr [rsp+180h+var_138+0Ah], di
0x14001975b  movzx   r15d, di
0x14001975f  mov     [rsp+180h+var_150], r15d
0x140019764  test    di, di
0x140019767  jz      loc_140019993
0x14001976d  movzx   r8d, di
0x140019771  mov     edx, r13d
0x140019774  mov     rcx, r14
0x140019777  call    SdbFindFirstTag
0x14001977c  xor     edx, edx
0x14001977e  mov     r15d, eax
0x140019781  test    eax, eax
0x140019783  jz      loc_140019989
0x140019789  and     edi, 0F000h
0x14001978f  mov     qword ptr [rsp+180h+var_138], rdx
0x140019794  lea     eax, [rdi-6000h]
0x14001979a  test    eax, 0FFFFDFFFh
0x14001979f  jz      short loc_140019820
0x1400197a1  cmp     edi, 9000h
0x1400197a7  jnz     loc_140019989
0x1400197ad  mov     edi, edx
0x1400197af  mov     rcx, r14
0x1400197b2  mov     edx, r15d
0x1400197b5  call    SdbGetTagDataSize
0x1400197ba  cmp     eax, 10h
0x1400197bd  jnz     loc_140019846
0x1400197c3  movups  xmm0, cs:SDB_GUID_EMPTY
0x1400197ca  lea     r9, [rsp+180h+Buf1]
0x1400197cf  mov     r8d, r15d
0x1400197d2  mov     rdx, r14
0x1400197d5  lea     rcx, [rbp+80h+var_70]
0x1400197d9  movdqu  [rsp+180h+Buf1], xmm0
0x1400197df  call    SdbReadGUIDTag
0x1400197e4  lea     r8d, [rdi+10h]; Size
0x1400197e8  lea     rdx, SDB_GUID_EMPTY; Buf2
0x1400197ef  lea     rcx, [rsp+180h+Buf1]; Buf1
0x1400197f4  movups  xmm6, xmmword ptr [rax]
0x1400197f7  movups  [rsp+180h+Buf1], xmm6
0x1400197fc  call    memcmp_0
0x140019801  xor     ecx, ecx
0x140019803  test    eax, eax
0x140019805  jz      short loc_140019846
0x140019807  movq    rax, xmm6
0x14001980c  psrldq  xmm6, 8
0x140019811  movq    rdi, xmm6
0x140019816  xor     rdi, rax
0x140019819  mov     qword ptr [rsp+180h+var_138], rdi
0x14001981e  jmp     short loc_140019846
0x140019820  mov     edx, r15d
0x140019823  mov     rcx, r14
0x140019826  call    SdbGetStringTagPtr
0x14001982b  test    rax, rax
0x14001982e  jz      loc_140019989
0x140019834  xor     edx, edx
0x140019836  mov     rcx, rax; SourceString
0x140019839  call    SdbMakeIndexKeyFromStringEx
0x14001983e  mov     rdi, rax
0x140019841  mov     qword ptr [rsp+180h+var_138], rax
0x140019846  test    rdi, rdi
0x140019849  jz      loc_140019989
0x14001984f  mov     r8d, 1018h
0x140019855  mov     edx, r13d
0x140019858  mov     rcx, r14
0x14001985b  call    SdbFindFirstTag
0x140019860  mov     r8, [rsp+180h+var_120]
0x140019865  neg     eax
0x140019867  mov     al, byte ptr [rsp+180h+var_138+0Fh]
0x14001986b  mov     r13, [rbp+80h+NumOfElements]
0x14001986f  sbb     cl, cl
0x140019871  and     cl, 80h
0x140019874  and     al, 7Fh
0x140019876  or      cl, al
0x140019878  mov     byte ptr [rsp+180h+var_138+0Fh], cl
0x14001987c  cmp     r13, r8
0x14001987f  jb      loc_140019930
0x140019885  lea     rax, [r13+1]
0x140019889  cmp     rax, r8
0x14001988c  ja      short loc_140019898
0x14001988e  mov     ebx, 0C000000Dh
  ... truncated ...
```
