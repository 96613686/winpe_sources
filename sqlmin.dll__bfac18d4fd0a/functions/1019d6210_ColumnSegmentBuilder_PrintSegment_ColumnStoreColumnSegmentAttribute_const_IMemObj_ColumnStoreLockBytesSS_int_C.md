# ColumnSegmentBuilder::PrintSegment(ColumnStoreColumnSegmentAttribute const *,IMemObj *,ColumnStoreLockBytesSS *,int,ColumnStoreObjectKey const &,ColumnStoreBlobManager *,uint,uint)

- ea: `0x1019d6210`
- end: `0x1019d6a14`
- name: `?PrintSegment@ColumnSegmentBuilder@@SAXPEBVColumnStoreColumnSegmentAttribute@@PEAVIMemObj@@PEAVColumnStoreLockBytesSS@@HAEBVColumnStoreObjectKey@@PEAVColumnStoreBlobManager@@II@Z`
- size: `2052`
- prototype: `void __fastcall(const struct ColumnStoreColumnSegmentAttribute *, struct IMemObj *, struct ColumnStoreLockBytesSS *, int, const struct ColumnStoreObjectKey *, struct ColumnStoreBlobManager *, unsigned int, unsigned int)`
- caller_count: `1`
- callee_count: `9`
- tags: `file_ops`

## callers

- `0x1019de000`

## callees

- `0x100401490`
- `0x100402000`
- `0x100415470`
- `0x1004fab50`
- `0x1019d5a00`
- `0x1019d6210`
- `0x1019d6a20`
- `0x1019db440`
- `0x102394d80`

## import_xrefs

- `KERNEL32!HeapAlloc` at `0x1019d632a`
- `KERNEL32!HeapAlloc` at `0x1019d632a`
- `KERNEL32!GetProcessHeap` at `0x1019d6319`
- `KERNEL32!GetProcessHeap` at `0x1019d6319`
- `sqldk!??0CDStream@@QEAA@XZ` at `0x1019d6293`
- `sqldk!??0CDStream@@QEAA@XZ` at `0x1019d6293`
- `sqldk!??1CDStream@@QEAA@XZ` at `0x1019d69e4`
- `sqldk!??1CDStream@@QEAA@XZ` at `0x1019d69e4`
- `sqldk!?AddDevice@CDStream@@QEAAHPEAVCDumpStream@@@Z` at `0x1019d6357`
- `sqldk!?AddDevice@CDStream@@QEAAHPEAVCDumpStream@@@Z` at `0x1019d6357`
- `sqldk!?Init@CAutoStreamHeader@@QEAAHPEAVCDStream@@PEBDZZ` at `0x1019d638b`
- `sqldk!?Init@CAutoStreamHeader@@QEAAHPEAVCDStream@@PEBDZZ` at `0x1019d63c5`
- `sqldk!?Init@CAutoStreamHeader@@QEAAHPEAVCDStream@@PEBDZZ` at `0x1019d6448`
- `sqldk!?Init@CAutoStreamHeader@@QEAAHPEAVCDStream@@PEBDZZ` at `0x1019d660b`
- `sqldk!?Init@CAutoStreamHeader@@QEAAHPEAVCDStream@@PEBDZZ` at `0x1019d6693`
- `sqldk!?Init@CAutoStreamHeader@@QEAAHPEAVCDStream@@PEBDZZ` at `0x1019d6742`
- `sqldk!?Init@CAutoStreamHeader@@QEAAHPEAVCDStream@@PEBDZZ` at `0x1019d67ea`
- `sqldk!?Init@CAutoStreamHeader@@QEAAHPEAVCDStream@@PEBDZZ` at `0x1019d638b`
- `sqldk!?Init@CAutoStreamHeader@@QEAAHPEAVCDStream@@PEBDZZ` at `0x1019d63c5`
- `sqldk!?Init@CAutoStreamHeader@@QEAAHPEAVCDStream@@PEBDZZ` at `0x1019d6448`
- `sqldk!?Init@CAutoStreamHeader@@QEAAHPEAVCDStream@@PEBDZZ` at `0x1019d660b`
- `sqldk!?Init@CAutoStreamHeader@@QEAAHPEAVCDStream@@PEBDZZ` at `0x1019d6693`
- `sqldk!?Init@CAutoStreamHeader@@QEAAHPEAVCDStream@@PEBDZZ` at `0x1019d6742`
- `sqldk!?Init@CAutoStreamHeader@@QEAAHPEAVCDStream@@PEBDZZ` at `0x1019d67ea`
- `sqldk!??1CAutoStreamHeader@@QEAA@XZ` at `0x1019d6428`
- `sqldk!??1CAutoStreamHeader@@QEAA@XZ` at `0x1019d65d1`
- `sqldk!??1CAutoStreamHeader@@QEAA@XZ` at `0x1019d65e5`
- `sqldk!??1CAutoStreamHeader@@QEAA@XZ` at `0x1019d666d`
- `sqldk!??1CAutoStreamHeader@@QEAA@XZ` at `0x1019d6712`
- `sqldk!??1CAutoStreamHeader@@QEAA@XZ` at `0x1019d67c4`
- `sqldk!??1CAutoStreamHeader@@QEAA@XZ` at `0x1019d6933`
- `sqldk!??1CAutoStreamHeader@@QEAA@XZ` at `0x1019d694c`
- `sqldk!??1CAutoStreamHeader@@QEAA@XZ` at `0x1019d69d9`
- `sqldk!??1CAutoStreamHeader@@QEAA@XZ` at `0x1019d6428`
- `sqldk!??1CAutoStreamHeader@@QEAA@XZ` at `0x1019d65d1`
- `sqldk!??1CAutoStreamHeader@@QEAA@XZ` at `0x1019d65e5`
- `sqldk!??1CAutoStreamHeader@@QEAA@XZ` at `0x1019d666d`
- `sqldk!??1CAutoStreamHeader@@QEAA@XZ` at `0x1019d6712`
- `sqldk!??1CAutoStreamHeader@@QEAA@XZ` at `0x1019d67c4`
- `sqldk!??1CAutoStreamHeader@@QEAA@XZ` at `0x1019d6933`
- `sqldk!??1CAutoStreamHeader@@QEAA@XZ` at `0x1019d694c`
- `sqldk!??1CAutoStreamHeader@@QEAA@XZ` at `0x1019d69d9`
- `sqldk!??0CAutoStreamHeader@@QEAA@XZ` at `0x1019d62a1`
- `sqldk!??0CAutoStreamHeader@@QEAA@XZ` at `0x1019d63ac`
- `sqldk!??0CAutoStreamHeader@@QEAA@XZ` at `0x1019d6432`
- `sqldk!??0CAutoStreamHeader@@QEAA@XZ` at `0x1019d65f2`
- `sqldk!??0CAutoStreamHeader@@QEAA@XZ` at `0x1019d667a`
- `sqldk!??0CAutoStreamHeader@@QEAA@XZ` at `0x1019d6729`
- `sqldk!??0CAutoStreamHeader@@QEAA@XZ` at `0x1019d67d1`
- `sqldk!??0CAutoStreamHeader@@QEAA@XZ` at `0x1019d62a1`
- `sqldk!??0CAutoStreamHeader@@QEAA@XZ` at `0x1019d63ac`
- `sqldk!??0CAutoStreamHeader@@QEAA@XZ` at `0x1019d6432`
- `sqldk!??0CAutoStreamHeader@@QEAA@XZ` at `0x1019d65f2`
- `sqldk!??0CAutoStreamHeader@@QEAA@XZ` at `0x1019d667a`
- `sqldk!??0CAutoStreamHeader@@QEAA@XZ` at `0x1019d6729`
- `sqldk!??0CAutoStreamHeader@@QEAA@XZ` at `0x1019d67d1`
- `sqldk!?GetDefaultLocale@@YAPEAU__crt_locale_pointers@@XZ` at `0x1019d6895`
- `sqldk!?GetDefaultLocale@@YAPEAU__crt_locale_pointers@@XZ` at `0x1019d6895`
- `sqldk!?Write@CDStream@@QEAAHPEBD0ZZ` at `0x1019d63e1`
- `sqldk!?Write@CDStream@@QEAAHPEBD0ZZ` at `0x1019d63fd`
- `sqldk!?Write@CDStream@@QEAAHPEBD0ZZ` at `0x1019d641a`
- `sqldk!?Write@CDStream@@QEAAHPEBD0ZZ` at `0x1019d6488`
- `sqldk!?Write@CDStream@@QEAAHPEBD0ZZ` at `0x1019d64ce`
- `sqldk!?Write@CDStream@@QEAAHPEBD0ZZ` at `0x1019d64e9`
- `sqldk!?Write@CDStream@@QEAAHPEBD0ZZ` at `0x1019d6548`
- `sqldk!?Write@CDStream@@QEAAHPEBD0ZZ` at `0x1019d6583`
- `sqldk!?Write@CDStream@@QEAAHPEBD0ZZ` at `0x1019d65a7`
- `sqldk!?Write@CDStream@@QEAAHPEBD0ZZ` at `0x1019d6627`
- `sqldk!?Write@CDStream@@QEAAHPEBD0ZZ` at `0x1019d6643`
- `sqldk!?Write@CDStream@@QEAAHPEBD0ZZ` at `0x1019d665f`
- `sqldk!?Write@CDStream@@QEAAHPEBD0ZZ` at `0x1019d66c8`
- `sqldk!?Write@CDStream@@QEAAHPEBD0ZZ` at `0x1019d66e7`
- `sqldk!?Write@CDStream@@QEAAHPEBD0ZZ` at `0x1019d6760`
- `sqldk!?Write@CDStream@@QEAAHPEBD0ZZ` at `0x1019d677d`
- `sqldk!?Write@CDStream@@QEAAHPEBD0ZZ` at `0x1019d679a`
- `sqldk!?Write@CDStream@@QEAAHPEBD0ZZ` at `0x1019d67b6`
- `sqldk!?Write@CDStream@@QEAAHPEBD0ZZ` at `0x1019d68d4`
- `sqldk!?Write@CDStream@@QEAAHPEBD0ZZ` at `0x1019d63e1`
- `sqldk!?Write@CDStream@@QEAAHPEBD0ZZ` at `0x1019d63fd`
- `sqldk!?Write@CDStream@@QEAAHPEBD0ZZ` at `0x1019d641a`
- `sqldk!?Write@CDStream@@QEAAHPEBD0ZZ` at `0x1019d6488`
- `sqldk!?Write@CDStream@@QEAAHPEBD0ZZ` at `0x1019d64ce`
- `sqldk!?Write@CDStream@@QEAAHPEBD0ZZ` at `0x1019d64e9`
- `sqldk!?Write@CDStream@@QEAAHPEBD0ZZ` at `0x1019d6548`
- `sqldk!?Write@CDStream@@QEAAHPEBD0ZZ` at `0x1019d6583`
- `sqldk!?Write@CDStream@@QEAAHPEBD0ZZ` at `0x1019d65a7`
- `sqldk!?Write@CDStream@@QEAAHPEBD0ZZ` at `0x1019d6627`
- `sqldk!?Write@CDStream@@QEAAHPEBD0ZZ` at `0x1019d6643`
- `sqldk!?Write@CDStream@@QEAAHPEBD0ZZ` at `0x1019d665f`
- `sqldk!?Write@CDStream@@QEAAHPEBD0ZZ` at `0x1019d66c8`
- `sqldk!?Write@CDStream@@QEAAHPEBD0ZZ` at `0x1019d66e7`
- `sqldk!?Write@CDStream@@QEAAHPEBD0ZZ` at `0x1019d6760`
- `sqldk!?Write@CDStream@@QEAAHPEBD0ZZ` at `0x1019d677d`
- `sqldk!?Write@CDStream@@QEAAHPEBD0ZZ` at `0x1019d679a`
- `sqldk!?Write@CDStream@@QEAAHPEBD0ZZ` at `0x1019d67b6`
- `sqldk!?Write@CDStream@@QEAAHPEBD0ZZ` at `0x1019d68d4`
- `sqldk!?Flush@CDStream@@QEAAHXZ` at `0x1019d64f3`
- `sqldk!?Flush@CDStream@@QEAAHXZ` at `0x1019d65b1`
- `sqldk!?Flush@CDStream@@QEAAHXZ` at `0x1019d66f1`
- `sqldk!?Flush@CDStream@@QEAAHXZ` at `0x1019d68e4`
- `sqldk!?Flush@CDStream@@QEAAHXZ` at `0x1019d64f3`
- `sqldk!?Flush@CDStream@@QEAAHXZ` at `0x1019d65b1`
- `sqldk!?Flush@CDStream@@QEAAHXZ` at `0x1019d66f1`
- `sqldk!?Flush@CDStream@@QEAAHXZ` at `0x1019d68e4`
- `sqldk!??3@YAXPEAX_K@Z` at `0x1019d69b3`
- `sqldk!??3@YAXPEAX_K@Z` at `0x1019d69bf`
- `sqldk!??3@YAXPEAX_K@Z` at `0x1019d69cb`
- `sqldk!??3@YAXPEAX_K@Z` at `0x1019d69b3`
- `sqldk!??3@YAXPEAX_K@Z` at `0x1019d69bf`
- `sqldk!??3@YAXPEAX_K@Z` at `0x1019d69cb`
- `sqldk!??_V@YAXPEAX@Z` at `0x1019d699b`
- `sqldk!??_V@YAXPEAX@Z` at `0x1019d699b`

## pseudocode

```c
// Hidden C++ exception states: #wind=31
void __fastcall ColumnSegmentBuilder::PrintSegment(
        const struct ColumnStoreColumnSegmentAttribute *a1,
        struct IMemObj *a2,
        struct ColumnStoreLockBytesSS *a3,
        int a4,
        const struct ColumnStoreObjectKey *a5,
        struct ColumnStoreBlobManager *a6,
        unsigned int a7,
        unsigned int a8)
{
  unsigned int v12; // r14d
  unsigned int v13; // esi
  int v14; // ecx
  HANDLE ProcessHeap; // rax
  CTracePrintStream *v16; // rax
  CTracePrintStream *v17; // rbx
  char v18; // al
  unsigned int v19; // edi
  char *v20; // rbx
  unsigned int *v21; // rsi
  __int64 *v22; // r9
  unsigned __int64 v23; // r9
  const char *v24; // rdx
  __int64 v25; // r9
  const char *v26; // rdx
  _DWORD *v27; // rdi
  VLDStoreBuilder *v28; // rcx
  unsigned int v29; // esi
  char v30; // r13
  unsigned __int16 v31; // r12
  struct ColumnStoreBlobManager *v32; // rax
  struct ColumnStoreBlobManager *v33; // r15
  unsigned __int16 v34; // bx
  char *v35; // rcx
  unsigned __int64 v36; // rsi
  struct __crt_locale_pointers *DefaultLocale; // rax
  __int64 v38; // rdx
  __int64 v39; // rcx
  struct ColumnStoreObjectKey *v40; // [rsp+20h] [rbp-E0h]
  struct ColumnStoreBlobManager *v41; // [rsp+28h] [rbp-D8h]
  char *v42; // [rsp+60h] [rbp-A0h] BYREF
  _DWORD *v43; // [rsp+68h] [rbp-98h] BYREF
  _BYTE v44[12]; // [rsp+70h] [rbp-90h] BYREF
  __int16 v45; // [rsp+7Ch] [rbp-84h]
  int v46; // [rsp+80h] [rbp-80h] BYREF
  int v47; // [rsp+84h] [rbp-7Ch] BYREF
  char *v48; // [rsp+88h] [rbp-78h] BYREF
  struct ColumnStoreBlobManager *i; // [rsp+90h] [rbp-70h]
  _BYTE v50[96]; // [rsp+A0h] [rbp-60h] BYREF
  char *v51; // [rsp+100h] [rbp+0h] BYREF
  void **v52; // [rsp+108h] [rbp+8h]
  __int64 v53; // [rsp+110h] [rbp+10h]
  struct ColumnStoreObjectKey *v54; // [rsp+118h] [rbp+18h]
  __int64 v55; // [rsp+120h] [rbp+20h]
  __int64 v56; // [rsp+128h] [rbp+28h] BYREF
  int v57; // [rsp+130h] [rbp+30h]
  __int128 v58; // [rsp+138h] [rbp+38h]
  unsigned __int16 v59; // [rsp+148h] [rbp+48h]
  _BYTE v60[528]; // [rsp+150h] [rbp+50h] BYREF
  _BYTE v61[528]; // [rsp+360h] [rbp+260h] BYREF
  _BYTE v62[528]; // [rsp+570h] [rbp+470h] BYREF
  _BYTE v63[528]; // [rsp+780h] [rbp+680h] BYREF
  _BYTE v64[528]; // [rsp+990h] [rbp+890h] BYREF
  _BYTE v65[528]; // [rsp+BA0h] [rbp+AA0h] BYREF
  char v66[528]; // [rsp+DB0h] [rbp+CB0h] BYREF
  char v67[128]; // [rsp+FC0h] [rbp+EC0h] BYREF
  unsigned int v68; // [rsp+10C8h] [rbp+FC8h]

  v55 = -2;
  v12 = a7;
  v54 = a5;
  i = a6;
  v56 = 0;
  v57 = 0;
  v58 = 0;
  v59 = 0;
  CDStream::CDStream((CDStream *)v50);
  CAutoStreamHeader::CAutoStreamHeader((CAutoStreamHeader *)v66);
  memset(v44, 0, sizeof(v44));
  v45 = 0;
  v13 = 0;
  v43 = 0;
  v42 = 0;
  v48 = 0;
  ColumnSegmentBuilder::ReadFromDisk(
    v14,
    (_DWORD)a2,
    (_DWORD)a3,
    (unsigned int)&v56,
    (__int64)v44,
    (__int64)&v43,
    (__int64)&v46,
    (__int64)&v42,
    (__int64)&v51,
    (__int64)&v48,
    (__int64)&v47);
  ProcessHeap = GetProcessHeap();
  v16 = (CTracePrintStream *)HeapAlloc(ProcessHeap, 0, 0x6C0u);
  v52 = (void **)v16;
  if ( v16 )
    v17 = CTracePrintStream::CTracePrintStream(v16, 0);
  else
    v17 = 0;
  if ( v17 && !CDStream::AddDevice((CDStream *)v50, v17) )
    (**(void (__fastcall ***)(CTracePrintStream *, __int64))v17)(v17, 1);
  CAutoStreamHeader::Init(
    (CAutoStreamHeader *)v66,
    (struct CDStream *)v50,
    "Segment: (%d:%d)",
    *((_DWORD *)a1 + 20),
    *((_DWORD *)a1 + 21));
  if ( !(unsigned int)ColumnSegmentBuilder::PrintColSegmentAttributes((struct CDStream *)v50, a1) )
  {
    v20 = v42;
    goto LABEL_52;
  }
  CAutoStreamHeader::CAutoStreamHeader((CAutoStreamHeader *)v62);
  CAutoStreamHeader::Init((CAutoStreamHeader *)v62, (struct CDStream *)v50, "RLE Header:");
  CDStream::Write((CDStream *)v50, "Lob type", "%d", (_DWORD)v58);
  CDStream::Write((CDStream *)v50, "RLE Array Count (In terms of Native Units)", "%d", HIDWORD(v58));
  CDStream::Write((CDStream *)v50, "RLE Array Entry Size", "%d", v59);
  CAutoStreamHeader::~CAutoStreamHeader((CAutoStreamHeader *)v62);
  CAutoStreamHeader::CAutoStreamHeader((CAutoStreamHeader *)v60);
  CAutoStreamHeader::Init((CAutoStreamHeader *)v60, (struct CDStream *)v50, "RLE Data:");
  v18 = *((_BYTE *)a1 + 119) & 0x7F;
  v19 = 0;
  if ( v18 == 4 )
  {
    if ( HIDWORD(v58) )
    {
      v20 = v42;
      while ( 1 )
      {
        CDStream::Write((CDStream *)v50, "Index", "%d", v19 >> 1);
        v21 = (unsigned int *)&v20[8 * v19 + 8];
        v22 = (__int64 *)&v20[8 * v19];
        if ( v21[1] == 1 )
        {
          v23 = abs64(*v22) - 1;
          v24 = "Bitpack Array Index";
        }
        else
        {
          v23 = *v22;
          v24 = "Value";
        }
        CDStream::Write((CDStream *)v50, v24, "%I64x", v23);
        CDStream::Write((CDStream *)v50, "Count", "%I64x", *v21);
        if ( !CDStream::Flush((CDStream *)v50) )
          break;
        v19 += 2;
        if ( v19 >= HIDWORD(v58) )
        {
          v13 = 0;
          goto LABEL_27;
        }
      }
LABEL_25:
      CAutoStreamHeader::~CAutoStreamHeader((CAutoStreamHeader *)v60);
LABEL_52:
      v27 = v43;
      goto LABEL_53;
    }
  }
  else if ( 2 * HIDWORD(v58) )
  {
    v20 = v42;
    while ( 1 )
    {
      CDStream::Write((CDStream *)v50, "Index", "%d", v19 >> 1);
      v25 = *(unsigned int *)&v20[4 * v19];
      _mm_lfence();
      if ( (int)v25 >= 0 )
      {
        v26 = "Value";
      }
      else
      {
        v25 = abs32(v25) - 1;
        v26 = "Bitpack Array Index";
      }
      CDStream::Write((CDStream *)v50, v26, "%d", v25);
      v20 = v42;
      CDStream::Write((CDStream *)v50, "Count", "%d", *(_DWORD *)&v42[4 * v19 + 4]);
      if ( !CDStream::Flush((CDStream *)v50) )
        goto LABEL_25;
      v19 += 2;
      if ( v19 >= 2 * HIDWORD(v58) )
        goto LABEL_27;
    }
  }
  v20 = v42;
LABEL_27:
  CAutoStreamHeader::~CAutoStreamHeader((CAutoStreamHeader *)v60);
  CAutoStreamHeader::CAutoStreamHeader((CAutoStreamHeader *)v63);
  CAutoStreamHeader::Init((CAutoStreamHeader *)v63, (struct CDStream *)v50, "Bookmark Header:");
  CDStream::Write((CDStream *)v50, "Bookmark Count", "%d", DWORD1(v58));
  CDStream::Write((CDStream *)v50, "Bookmark Distance", "%d", DWORD2(v58));
  CDStream::Write((CDStream *)v50, "Bookmark Size", "%d", v46);
  CAutoStreamHeader::~CAutoStreamHeader((CAutoStreamHeader *)v63);
  CAutoStreamHeader::CAutoStreamHeader((CAutoStreamHeader *)v61);
  CAutoStreamHeader::Init((CAutoStreamHeader *)v61, (struct CDStream *)v50, "Bookmark Data:");
  v27 = v43;
  if ( 2 * DWORD1(v58) )
  {
    while ( 1 )
    {
      CDStream::Write((CDStream *)v50, "Position", "%d", v27[v13]);
      CDStream::Write((CDStream *)v50, "Index", "%d", v27[v13 + 1]);
      if ( !CDStream::Flush((CDStream *)v50) )
        break;
      v13 += 2;
      if ( v13 >= 2 * DWORD1(v58) )
        goto LABEL_30;
    }
    CAutoStreamHeader::~CAutoStreamHeader((CAutoStreamHeader *)v61);
  }
  else
  {
LABEL_30:
    CAutoStreamHeader::~CAutoStreamHeader((CAutoStreamHeader *)v61);
    if ( (_DWORD)v58 == 3 )
    {
      CAutoStreamHeader::CAutoStreamHeader((CAutoStreamHeader *)v64);
      CAutoStreamHeader::Init((CAutoStreamHeader *)v64, (struct CDStream *)v50, "Bitpack Data Header:");
      CDStream::Write((CDStream *)v50, "Bitpack Entry Size", "%d", *(unsigned __int16 *)v44);
      CDStream::Write((CDStream *)v50, "Bitpack Unit Count", "%d", *(_DWORD *)&v44[2]);
      CDStream::Write((CDStream *)v50, "Bitpack MinId", "%d", *(_DWORD *)&v44[6]);
      CDStream::Write((CDStream *)v50, "Bitpack DataSize", "%d", v47);
      CAutoStreamHeader::~CAutoStreamHeader((CAutoStreamHeader *)v64);
      CAutoStreamHeader::CAutoStreamHeader((CAutoStreamHeader *)v65);
      CAutoStreamHeader::Init((CAutoStreamHeader *)v65, (struct CDStream *)v50, "Bitpack Data:");
      if ( a4 == 2 && *(_DWORD *)&v44[2] && a7 <= *(_DWORD *)&v44[2] )
      {
        v29 = a8;
        if ( a8 > *(_DWORD *)&v44[2] )
          v29 = *(_DWORD *)&v44[2];
        v68 = v29;
        v30 = v44[0];
        v31 = 0x40u / *(_WORD *)v44;
        if ( a7 < v29 )
        {
          v32 = (struct ColumnStoreBlobManager *)(0xFFFFFFFFFFFFFFFFuLL >> (64 - v44[0]));
          for ( i = v32; ; v32 = i )
          {
            v33 = v32;
            v34 = 0;
            if ( v31 )
              break;
LABEL_43:
            v38 = v12 / 0x64;
            v39 = (unsigned int)(100 * v38);
            if ( v12 == (_DWORD)v39 )
            {
              LOBYTE(v39) = 48;
              YieldAndCheckForAbort(v39, v38);
            }
            if ( ++v12 >= v29 )
              goto LABEL_48;
          }
          _mm_lfence();
          v35 = &v48[8 * v12];
          v51 = v35;
          while ( 1 )
          {
            v36 = ((unsigned __int64)v33 & *(_QWORD *)v35) >> ((unsigned __int8)v34 * v30);
            DefaultLocale = GetDefaultLocale();
            LODWORD(v41) = v34;
            LODWORD(v40) = v12;
            StringCchPrintf_lA(v67, 0x80u, "Unit %d SubUnit %d", DefaultLocale, v40, v41);
            CDStream::Write((CDStream *)v50, v67, "%I64d", v36);
            v33 = (struct ColumnStoreBlobManager *)((_QWORD)v33 << v30);
            if ( !CDStream::Flush((CDStream *)v50) )
              break;
            ++v34;
            v35 = v51;
            if ( v34 >= v31 )
            {
              v29 = v68;
              goto LABEL_43;
            }
          }
LABEL_48:
          v20 = v42;
          v27 = v43;
        }
      }
      CAutoStreamHeader::~CAutoStreamHeader((CAutoStreamHeader *)v65);
    }
    else
    {
      v52 = &VLDStoreBuilder::`vftable';
      v53 = 0;
      VLDStoreBuilder::PrintVLDStore(v28, a2, a3, a4, v54, i);
      v52 = &VLDStoreBuilder::`vftable';
      operator delete[](0);
    }
  }
LABEL_53:
  operator delete(v48, 0);
  operator delete(v20, 0);
  operator delete(v27, 0);
  CAutoStreamHeader::~CAutoStreamHeader((CAutoStreamHeader *)v66);
  CDStream::~CDStream((CDStream *)v50);
}

```

## disassembly

```asm
0x1019d6210  push    rbp
0x1019d6212  push    rsi
0x1019d6213  push    rdi
0x1019d6214  push    r12
0x1019d6216  push    r13
0x1019d6218  push    r14
0x1019d621a  push    r15
0x1019d621c  lea     rbp, [rsp-0F50h]
0x1019d6224  mov     eax, 1050h
0x1019d6229  call    _alloca_probe
0x1019d622e  sub     rsp, rax
0x1019d6231  mov     [rbp+0F80h+var_F60], 0FFFFFFFFFFFFFFFEh
0x1019d6239  mov     [rsp+1080h+arg_18], rbx
0x1019d6241  mov     rax, cs:__security_cookie
0x1019d6248  xor     rax, rsp
0x1019d624b  mov     [rbp+0F80h+var_40], rax
0x1019d6252  mov     r15d, r9d
0x1019d6255  mov     r13, r8
0x1019d6258  mov     r12, rdx
0x1019d625b  mov     rdi, rcx
0x1019d625e  mov     r14d, [rbp+0F80h+arg_30]
0x1019d6265  mov     rax, [rbp+0F80h+arg_20]
0x1019d626c  mov     [rbp+0F80h+var_F68], rax
0x1019d6270  mov     rax, [rbp+0F80h+arg_28]
0x1019d6277  mov     [rbp+0F80h+var_FF0], rax
0x1019d627b  xor     eax, eax
0x1019d627d  mov     [rbp+0F80h+var_F58], rax
0x1019d6281  mov     [rbp+0F80h+var_F50], eax
0x1019d6284  xorps   xmm0, xmm0
0x1019d6287  movups  [rbp+0F80h+var_F48], xmm0
0x1019d628b  mov     [rbp+0F80h+var_F38], ax
0x1019d628f  lea     rcx, [rbp+0F80h+var_FE0]
0x1019d6293  call    cs:__imp_??0CDStream@@QEAA@XZ; CDStream::CDStream(void)
0x1019d6299  nop
0x1019d629a  lea     rcx, [rbp+0F80h+var_2D0]
0x1019d62a1  call    cs:__imp_??0CAutoStreamHeader@@QEAA@XZ; CAutoStreamHeader::CAutoStreamHeader(void)
0x1019d62a7  nop
0x1019d62a8  xor     eax, eax
0x1019d62aa  mov     [rsp+1080h+var_1010], rax
0x1019d62af  mov     [rsp+1080h+var_1008], eax
0x1019d62b3  mov     [rsp+1080h+var_1004], ax
0x1019d62b8  xor     esi, esi
0x1019d62ba  mov     [rsp+1080h+var_1018], rsi
0x1019d62bf  mov     [rsp+1080h+var_1020], rsi
0x1019d62c4  mov     [rbp+0F80h+var_FF8], rsi
0x1019d62c8  lea     rax, [rbp+0F80h+var_FFC]
0x1019d62cc  mov     [rsp+1080h+var_1030], rax
0x1019d62d1  lea     rax, [rbp+0F80h+var_FF8]
0x1019d62d5  mov     [rsp+1080h+var_1038], rax
0x1019d62da  lea     rax, [rbp+0F80h+var_F80]
0x1019d62de  mov     [rsp+1080h+var_1040], rax
0x1019d62e3  lea     rax, [rsp+1080h+var_1020]
0x1019d62e8  mov     [rsp+1080h+var_1048], rax
0x1019d62ed  lea     rax, [rbp+0F80h+var_1000]
0x1019d62f1  mov     [rsp+1080h+var_1050], rax
0x1019d62f6  lea     rax, [rsp+1080h+var_1018]
0x1019d62fb  mov     [rsp+1080h+var_1058], rax
0x1019d6300  lea     rax, [rsp+1080h+var_1010]
0x1019d6305  mov     [rsp+1080h+var_1060], rax
0x1019d630a  lea     r9, [rbp+0F80h+var_F58]
0x1019d630e  mov     r8, r13
0x1019d6311  mov     rdx, r12
0x1019d6314  call    ?ReadFromDisk@ColumnSegmentBuilder@@CAXPEBVColumnStoreColumnSegmentAttribute@@PEAVIMemObj@@PEAVColumnStoreLockBytesSS@@AEAVCSLOB_ColumnSegment@@AEAUCSLOB_BitPackDataHeader@@AEAV?$CAutoP@X@@AEAK5656@Z; ColumnSegmentBuilder::ReadFromDisk(ColumnStoreColumnSegmentAttribute const *,IMemObj *,ColumnStoreLockBytesSS *,CSLOB_ColumnSegment &,CSLOB_BitPackDataHeader &,CAutoP<void> &,ulong &,CAutoP<void> &,ulong &,CAutoP<void> &,ulong &)
0x1019d6319  call    cs:__imp_GetProcessHeap
0x1019d631f  mov     rcx, rax; hHeap
0x1019d6322  xor     edx, edx; dwFlags
0x1019d6324  mov     r8d, 6C0h; dwBytes
0x1019d632a  call    cs:__imp_HeapAlloc
0x1019d6330  mov     [rbp+0F80h+var_F78], rax
0x1019d6334  test    rax, rax
0x1019d6337  jz      short loc_1019D6348
0x1019d6339  xor     edx, edx; bool
0x1019d633b  mov     rcx, rax; this
0x1019d633e  call    ??0CTracePrintStream@@QEAA@_N@Z; CTracePrintStream::CTracePrintStream(bool)
0x1019d6343  mov     rbx, rax
0x1019d6346  jmp     short loc_1019D634B
0x1019d6348  mov     rbx, rsi
0x1019d634b  test    rbx, rbx
0x1019d634e  jz      short loc_1019D636E
0x1019d6350  mov     rdx, rbx
0x1019d6353  lea     rcx, [rbp+0F80h+var_FE0]
0x1019d6357  call    cs:__imp_?AddDevice@CDStream@@QEAAHPEAVCDumpStream@@@Z; CDStream::AddDevice(CDumpStream *)
0x1019d635d  test    eax, eax
0x1019d635f  jnz     short loc_1019D636E
0x1019d6361  mov     rax, [rbx]
0x1019d6364  mov     edx, 1
0x1019d6369  mov     rcx, rbx
0x1019d636c  call    qword ptr [rax]
0x1019d636e  mov     eax, [rdi+54h]
0x1019d6371  mov     dword ptr [rsp+1080h+var_1060], eax
0x1019d6375  mov     r9d, [rdi+50h]
0x1019d6379  lea     r8, aSegmentDD; "Segment: (%d:%d)"
0x1019d6380  lea     rdx, [rbp+0F80h+var_FE0]
0x1019d6384  lea     rcx, [rbp+0F80h+var_2D0]
0x1019d638b  call    cs:__imp_?Init@CAutoStreamHeader@@QEAAHPEAVCDStream@@PEBDZZ; CAutoStreamHeader::Init(CDStream *,char const *,...)
0x1019d6391  mov     rdx, rdi; struct ColumnStoreColumnSegmentAttribute *
0x1019d6394  lea     rcx, [rbp+0F80h+var_FE0]; struct CDStream *
0x1019d6398  call    ?PrintColSegmentAttributes@ColumnSegmentBuilder@@CAHPEAVCDStream@@PEBVColumnStoreColumnSegmentAttribute@@@Z; ColumnSegmentBuilder::PrintColSegmentAttributes(CDStream *,ColumnStoreColumnSegmentAttribute const *)
0x1019d639d  test    eax, eax
0x1019d639f  jz      loc_1019D69A3
0x1019d63a5  lea     rcx, [rbp+0F80h+var_B10]
0x1019d63ac  call    cs:__imp_??0CAutoStreamHeader@@QEAA@XZ; CAutoStreamHeader::CAutoStreamHeader(void)
0x1019d63b2  nop
0x1019d63b3  lea     r8, aRleHeader; "RLE Header:"
0x1019d63ba  lea     rdx, [rbp+0F80h+var_FE0]
0x1019d63be  lea     rcx, [rbp+0F80h+var_B10]
0x1019d63c5  call    cs:__imp_?Init@CAutoStreamHeader@@QEAAHPEAVCDStream@@PEBDZZ; CAutoStreamHeader::Init(CDStream *,char const *,...)
0x1019d63cb  mov     r9d, dword ptr [rbp+0F80h+var_F48]
0x1019d63cf  lea     r8, aD_5; "%d"
0x1019d63d6  lea     rdx, aLobType; "Lob type"
0x1019d63dd  lea     rcx, [rbp+0F80h+var_FE0]
0x1019d63e1  call    cs:__imp_?Write@CDStream@@QEAAHPEBD0ZZ; CDStream::Write(char const *,char const *,...)
0x1019d63e7  mov     r9d, dword ptr [rbp+0F80h+var_F48+0Ch]
0x1019d63eb  lea     r8, aD_5; "%d"
0x1019d63f2  lea     rdx, aRleArrayCountI; "RLE Array Count (In terms of Native Uni"...
0x1019d63f9  lea     rcx, [rbp+0F80h+var_FE0]
0x1019d63fd  call    cs:__imp_?Write@CDStream@@QEAAHPEBD0ZZ; CDStream::Write(char const *,char const *,...)
0x1019d6403  movzx   r9d, [rbp+0F80h+var_F38]
0x1019d6408  lea     r8, aD_5; "%d"
0x1019d640f  lea     rdx, aRleArrayEntryS; "RLE Array Entry Size"
0x1019d6416  lea     rcx, [rbp+0F80h+var_FE0]
0x1019d641a  call    cs:__imp_?Write@CDStream@@QEAAHPEBD0ZZ; CDStream::Write(char const *,char const *,...)
0x1019d6420  nop
0x1019d6421  lea     rcx, [rbp+0F80h+var_B10]
0x1019d6428  call    cs:__imp_??1CAutoStreamHeader@@QEAA@XZ; CAutoStreamHeader::~CAutoStreamHeader(void)
0x1019d642e  lea     rcx, [rbp+0F80h+var_F30]
0x1019d6432  call    cs:__imp_??0CAutoStreamHeader@@QEAA@XZ; CAutoStreamHeader::CAutoStreamHeader(void)
0x1019d6438  nop
0x1019d6439  lea     r8, aRleData; "RLE Data:"
0x1019d6440  lea     rdx, [rbp+0F80h+var_FE0]
0x1019d6444  lea     rcx, [rbp+0F80h+var_F30]
0x1019d6448  call    cs:__imp_?Init@CAutoStreamHeader@@QEAAHPEAVCDStream@@PEBDZZ; CAutoStreamHeader::Init(CDStream *,char const *,...)
0x1019d644e  movzx   eax, byte ptr [rdi+77h]
0x1019d6452  and     al, 7Fh
0x1019d6454  mov     edi, esi
0x1019d6456  cmp     al, 4
0x1019d6458  jnz     loc_1019D6514
0x1019d645e  cmp     dword ptr [rbp+0F80h+var_F48+0Ch], esi
0x1019d6461  jbe     loc_1019D65DC
0x1019d6467  mov     rbx, [rsp+1080h+var_1020]
0x1019d646c  nop     dword ptr [rax+00h]
0x1019d6470  mov     r9d, edi
0x1019d6473  shr     r9d, 1
0x1019d6476  lea     r8, aD_5; "%d"
0x1019d647d  lea     rdx, aIndex_2; "Index"
0x1019d6484  lea     rcx, [rbp+0F80h+var_FE0]
0x1019d6488  call    cs:__imp_?Write@CDStream@@QEAAHPEBD0ZZ; CDStream::Write(char const *,char const *,...)
0x1019d648e  lea     eax, [rdi+1]
0x1019d6491  lea     rsi, [rbx+rax*8]
0x1019d6495  mov     eax, edi
0x1019d6497  lea     r9, [rbx+rax*8]
0x1019d649b  lea     r8, aI64x_0; "%I64x"
0x1019d64a2  lea     rcx, [rbp+0F80h+var_FE0]
0x1019d64a6  cmp     dword ptr [rsi+4], 1
0x1019d64aa  jnz     short loc_1019D64C4
0x1019d64ac  mov     rax, [r9]
0x1019d64af  cqo
0x1019d64b1  xor     rax, rdx
0x1019d64b4  sub     rax, rdx
0x1019d64b7  lea     r9, [rax-1]
0x1019d64bb  lea     rdx, aBitpackArrayIn; "Bitpack Array Index"
0x1019d64c2  jmp     short loc_1019D64CE
0x1019d64c4  mov     r9, [r9]
0x1019d64c7  lea     rdx, aValue_0; "Value"
0x1019d64ce  call    cs:__imp_?Write@CDStream@@QEAAHPEBD0ZZ; CDStream::Write(char const *,char const *,...)
0x1019d64d4  mov     r9d, [rsi]
0x1019d64d7  lea     r8, aI64x_0; "%I64x"
0x1019d64de  lea     rdx, aCount_1; "Count"
0x1019d64e5  lea     rcx, [rbp+0F80h+var_FE0]
0x1019d64e9  call    cs:__imp_?Write@CDStream@@QEAAHPEBD0ZZ; CDStream::Write(char const *,char const *,...)
0x1019d64ef  lea     rcx, [rbp+0F80h+var_FE0]
0x1019d64f3  call    cs:__imp_?Flush@CDStream@@QEAAHXZ; CDStream::Flush(void)
0x1019d64f9  test    eax, eax
0x1019d64fb  jz      loc_1019D65CD
0x1019d6501  add     edi, 2
0x1019d6504  cmp     edi, dword ptr [rbp+0F80h+var_F48+0Ch]
0x1019d6507  jb      loc_1019D6470
0x1019d650d  xor     esi, esi
0x1019d650f  jmp     loc_1019D65E1
0x1019d6514  mov     eax, dword ptr [rbp+0F80h+var_F48+0Ch]
0x1019d6517  add     eax, eax
0x1019d6519  jz      loc_1019D65DC
0x1019d651f  mov     rbx, [rsp+1080h+var_1020]
0x1019d6524  nop     dword ptr [rax+00h]
0x1019d6528  nop     dword ptr [rax+rax+00000000h]
0x1019d6530  mov     r9d, edi
0x1019d6533  shr     r9d, 1
0x1019d6536  lea     r8, aD_5; "%d"
0x1019d653d  lea     rdx, aIndex_2; "Index"
0x1019d6544  lea     rcx, [rbp+0F80h+var_FE0]
0x1019d6548  call    cs:__imp_?Write@CDStream@@QEAAHPEBD0ZZ; CDStream::Write(char const *,char const *,...)
0x1019d654e  mov     eax, edi
0x1019d6550  mov     r9d, [rbx+rax*4]
0x1019d6554  lfence
0x1019d6557  lea     r8, aD_5; "%d"
0x1019d655e  lea     rcx, [rbp+0F80h+var_FE0]
0x1019d6562  test    r9d, r9d
0x1019d6565  jns     short loc_1019D657C
0x1019d6567  mov     eax, r9d
0x1019d656a  cdq
0x1019d656b  xor     eax, edx
0x1019d656d  sub     eax, edx
0x1019d656f  lea     r9d, [rax-1]
0x1019d6573  lea     rdx, aBitpackArrayIn; "Bitpack Array Index"
0x1019d657a  jmp     short loc_1019D6583
0x1019d657c  lea     rdx, aValue_0; "Value"
0x1019d6583  call    cs:__imp_?Write@CDStream@@QEAAHPEBD0ZZ; CDStream::Write(char const *,char const *,...)
0x1019d6589  lea     eax, [rdi+1]
0x1019d658c  mov     rbx, [rsp+1080h+var_1020]
0x1019d6591  mov     r9d, [rbx+rax*4]
0x1019d6595  lea     r8, aD_5; "%d"
0x1019d659c  lea     rdx, aCount_1; "Count"
0x1019d65a3  lea     rcx, [rbp+0F80h+var_FE0]
0x1019d65a7  call    cs:__imp_?Write@CDStream@@QEAAHPEBD0ZZ; CDStream::Write(char const *,char const *,...)
0x1019d65ad  lea     rcx, [rbp+0F80h+var_FE0]
0x1019d65b1  call    cs:__imp_?Flush@CDStream@@QEAAHXZ; CDStream::Flush(void)
0x1019d65b7  test    eax, eax
0x1019d65b9  jz      short loc_1019D65CD
0x1019d65bb  add     edi, 2
0x1019d65be  mov     eax, dword ptr [rbp+0F80h+var_F48+0Ch]
0x1019d65c1  add     eax, eax
0x1019d65c3  cmp     edi, eax
0x1019d65c5  jb      loc_1019D6530
0x1019d65cb  jmp     short loc_1019D65E1
0x1019d65cd  lea     rcx, [rbp+0F80h+var_F30]
0x1019d65d1  call    cs:__imp_??1CAutoStreamHeader@@QEAA@XZ; CAutoStreamHeader::~CAutoStreamHeader(void)
0x1019d65d7  jmp     loc_1019D69A8
0x1019d65dc  mov     rbx, [rsp+1080h+var_1020]
0x1019d65e1  lea     rcx, [rbp+0F80h+var_F30]
0x1019d65e5  call    cs:__imp_??1CAutoStreamHeader@@QEAA@XZ; CAutoStreamHeader::~CAutoStreamHeader(void)
0x1019d65eb  lea     rcx, [rbp+0F80h+var_900]
0x1019d65f2  call    cs:__imp_??0CAutoStreamHeader@@QEAA@XZ; CAutoStreamHeader::CAutoStreamHeader(void)
0x1019d65f8  nop
0x1019d65f9  lea     r8, aBookmarkHeader; "Bookmark Header:"
0x1019d6600  lea     rdx, [rbp+0F80h+var_FE0]
0x1019d6604  lea     rcx, [rbp+0F80h+var_900]
0x1019d660b  call    cs:__imp_?Init@CAutoStreamHeader@@QEAAHPEAVCDStream@@PEBDZZ; CAutoStreamHeader::Init(CDStream *,char const *,...)
0x1019d6611  mov     r9d, dword ptr [rbp+0F80h+var_F48+4]
0x1019d6615  lea     r8, aD_5; "%d"
0x1019d661c  lea     rdx, aBookmarkCount; "Bookmark Count"
0x1019d6623  lea     rcx, [rbp+0F80h+var_FE0]
0x1019d6627  call    cs:__imp_?Write@CDStream@@QEAAHPEBD0ZZ; CDStream::Write(char const *,char const *,...)
0x1019d662d  mov     r9d, dword ptr [rbp+0F80h+var_F48+8]
0x1019d6631  lea     r8, aD_5; "%d"
0x1019d6638  lea     rdx, aBookmarkDistan; "Bookmark Distance"
0x1019d663f  lea     rcx, [rbp+0F80h+var_FE0]
0x1019d6643  call    cs:__imp_?Write@CDStream@@QEAAHPEBD0ZZ; CDStream::Write(char const *,char const *,...)
0x1019d6649  mov     r9d, [rbp+0F80h+var_1000]
0x1019d664d  lea     r8, aD_5; "%d"
0x1019d6654  lea     rdx, aBookmarkSize; "Bookmark Size"
0x1019d665b  lea     rcx, [rbp+0F80h+var_FE0]
0x1019d665f  call    cs:__imp_?Write@CDStream@@QEAAHPEBD0ZZ; CDStream::Write(char const *,char const *,...)
0x1019d6665  nop
0x1019d6666  lea     rcx, [rbp+0F80h+var_900]
0x1019d666d  call    cs:__imp_??1CAutoStreamHeader@@QEAA@XZ; CAutoStreamHeader::~CAutoStreamHeader(void)
0x1019d6673  lea     rcx, [rbp+0F80h+var_D20]
0x1019d667a  call    cs:__imp_??0CAutoStreamHeader@@QEAA@XZ; CAutoStreamHeader::CAutoStreamHeader(void)
0x1019d6680  nop
0x1019d6681  lea     r8, aBookmarkData; "Bookmark Data:"
0x1019d6688  lea     rdx, [rbp+0F80h+var_FE0]
0x1019d668c  lea     rcx, [rbp+0F80h+var_D20]
0x1019d6693  call    cs:__imp_?Init@CAutoStreamHeader@@QEAAHPEAVCDStream@@PEBDZZ; CAutoStreamHeader::Init(CDStream *,char const *,...)
0x1019d6699  mov     eax, dword ptr [rbp+0F80h+var_F48+4]
0x1019d669c  add     eax, eax
0x1019d669e  mov     rdi, [rsp+1080h+var_1018]
0x1019d66a3  jz      short loc_1019D670B
0x1019d66a5  nop     word ptr [rax+rax]
0x1019d66aa  nop     word ptr [rax+rax+00h]
0x1019d66b0  mov     eax, esi
0x1019d66b2  mov     r9d, [rdi+rax*4]
0x1019d66b6  lea     r8, aD_5; "%d"
0x1019d66bd  lea     rdx, aPosition_1; "Position"
0x1019d66c4  lea     rcx, [rbp+0F80h+var_FE0]
0x1019d66c8  call    cs:__imp_?Write@CDStream@@QEAAHPEBD0ZZ; CDStream::Write(char const *,char const *,...)
0x1019d66ce  lea     eax, [rsi+1]
0x1019d66d1  mov     r9d, [rdi+rax*4]
0x1019d66d5  lea     r8, aD_5; "%d"
0x1019d66dc  lea     rdx, aIndex_2; "Index"
0x1019d66e3  lea     rcx, [rbp+0F80h+var_FE0]
0x1019d66e7  call    cs:__imp_?Write@CDStream@@QEAAHPEBD0ZZ; CDStream::Write(char const *,char const *,...)
0x1019d66ed  lea     rcx, [rbp+0F80h+var_FE0]
0x1019d66f1  call    cs:__imp_?Flush@CDStream@@QEAAHXZ; CDStream::Flush(void)
0x1019d66f7  test    eax, eax
0x1019d66f9  jz      loc_1019D692C
0x1019d66ff  add     esi, 2
0x1019d6702  mov     eax, dword ptr [rbp+0F80h+var_F48+4]
0x1019d6705  add     eax, eax
0x1019d6707  cmp     esi, eax
0x1019d6709  jb      short loc_1019D66B0
0x1019d670b  lea     rcx, [rbp+0F80h+var_D20]
0x1019d6712  call    cs:__imp_??1CAutoStreamHeader@@QEAA@XZ; CAutoStreamHeader::~CAutoStreamHeader(void)
0x1019d6718  cmp     dword ptr [rbp+0F80h+var_F48], 3
0x1019d671c  jnz     loc_1019D6954
0x1019d6722  lea     rcx, [rbp+0F80h+var_6F0]
0x1019d6729  call    cs:__imp_??0CAutoStreamHeader@@QEAA@XZ; CAutoStreamHeader::CAutoStreamHeader(void)
0x1019d672f  nop
0x1019d6730  lea     r8, aBitpackDataHea; "Bitpack Data Header:"
0x1019d6737  lea     rdx, [rbp+0F80h+var_FE0]
0x1019d673b  lea     rcx, [rbp+0F80h+var_6F0]
0x1019d6742  call    cs:__imp_?Init@CAutoStreamHeader@@QEAAHPEAVCDStream@@PEBDZZ; CAutoStreamHeader::Init(CDStream *,char const *,...)
  ... truncated ...
```
