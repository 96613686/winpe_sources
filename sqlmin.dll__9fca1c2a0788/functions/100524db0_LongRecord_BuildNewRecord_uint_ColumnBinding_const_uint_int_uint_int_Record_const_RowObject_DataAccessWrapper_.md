# LongRecord::BuildNewRecord(uint,ColumnBinding const *,uint,int,uint,int,Record const *,RowObject *,DataAccessWrapper *,CopiedVarCols const *,SEBitMap const *,CopiedVarCols const &,SEBitMap *,int &,Record &,uchar * const,uint,uint,uint &,uint &,int,SEBitMap *,int &,SetDataPropertyBag *,int,int &,ulong *,int *,int)

- ea: `0x100524db0`
- end: `0x1005255b7`
- name: `?BuildNewRecord@LongRecord@@IEAAHIPEBVColumnBinding@@IHIHPEBVRecord@@PEAVRowObject@@PEAVDataAccessWrapper@@PEBVCopiedVarCols@@PEBVSEBitMap@@AEBV6@PEAV7@AEAHAEAV3@QEAEIIAEAIAEAIH78PEAUSetDataPropertyBag@@H8PEAKPEAHH@Z`
- size: `2055`
- prototype: `__int64 __fastcall(LongRecord *__hidden this, unsigned int, const struct ColumnBinding *, unsigned int, __int64, unsigned int, int, const struct Record *, struct RowObject *, struct DataAccessWrapper *, const struct CopiedVarCols *, const struct SEBitMap *, const struct CopiedVarCols *, struct SEBitMap *, int *, struct Record *, unsigned __int8 *const, unsigned int, unsigned int, unsigned int *, unsigned int *, int, struct SEBitMap *, int *, struct SetDataPropertyBag *, int, int *, unsigned int *, int *, int)`
- caller_count: `1`
- callee_count: `28`
- tags: `broker_com_uri`

## callers

- `0x1005248d0`

## callees

- `0x100401490`
- `0x100401fcf`
- `0x100402000`
- `0x1004025c0`
- `0x100415e90`
- `0x100416140`
- `0x10043db30`
- `0x100441e00`
- `0x10046bf90`
- `0x100492f80`
- `0x100523f90`
- `0x100523fc0`
- `0x100524db0`
- `0x100565a20`
- `0x1005a74b0`
- `0x1014330c0`
- `0x1014331c0`
- `0x1014aceb0`
- `0x10213b950`
- `0x1021d5c70`
- `0x1021d8a90`
- `0x1021e86b0`
- `0x1021e92a0`
- `0x1021eab40`
- `0x1021ed0b0`
- `0x1021ed230`
- `0x1021ed310`
- `0x1021edb20`

## import_xrefs

- `sqlTsEs!?ConvertVarNumericToNumeric@CSsNumeric@@SA_NPEBEKEEPEAEPEAK@Z` at `0x10212229d`
- `sqlTsEs!?ConvertVarNumericToNumeric@CSsNumeric@@SA_NPEBEKEEPEAEPEAK@Z` at `0x10212229d`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x10211fb28`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x10211fb53`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x10211fb7e`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x10211fc51`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x10211fc7c`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x10212032a`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x102120355`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x102120380`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x10212045f`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x10212048a`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x102120a0a`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x102120a35`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x102120a60`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x102120b3b`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x102120b66`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x102121329`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x10212135e`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x102121389`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x10212145f`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x10212148a`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x10212178e`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1021217d3`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x102122367`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x102122392`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1021223bd`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x10212249b`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1021224c6`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x102122a77`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x102122aa2`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x102122acd`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x102122ba6`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x102122bd1`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x10211fb28`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x10211fb53`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x10211fb7e`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x10211fc51`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x10211fc7c`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x10212032a`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x102120355`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x102120380`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x10212045f`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x10212048a`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x102120a0a`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x102120a35`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x102120a60`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x102120b3b`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x102120b66`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x102121329`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x10212135e`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x102121389`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x10212145f`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x10212148a`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x10212178e`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1021217d3`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x102122367`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x102122392`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1021223bd`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x10212249b`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1021224c6`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x102122a77`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x102122aa2`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x102122acd`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x102122ba6`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x102122bd1`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10211f6ea`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10211f79f`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10211f84f`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10211fa43`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10211fae3`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10211fee3`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10211ff97`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10212004d`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10212024d`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x1021202ee`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x1021205b8`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x102120669`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10212071c`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10212091f`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x1021209d2`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x102120cad`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x102120d68`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x102120e1d`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10212101a`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x1021210bb`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x1021218b0`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x102121c23`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x102121cd7`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x102121d8d`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x102121f97`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10212203b`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x1021222b7`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10212263c`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x1021226f0`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x1021227a5`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10212299a`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x102122a3b`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10211f6ea`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10211f79f`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10211f84f`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10211fa43`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10211fae3`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10211fee3`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10211ff97`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10212004d`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10212024d`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x1021202ee`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x1021205b8`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x102120669`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10212071c`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10212091f`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x1021209d2`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x102120cad`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x102120d68`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x102120e1d`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10212101a`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x1021210bb`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x1021218b0`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x102121c23`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x102121cd7`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x102121d8d`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x102121f97`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10212203b`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x1021222b7`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10212263c`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x1021226f0`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x1021227a5`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10212299a`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x102122a3b`
- `sqldk!SystemThread_TlsIndex` at `0x10211f68f`
- `sqldk!SystemThread_TlsIndex` at `0x10211f744`
- `sqldk!SystemThread_TlsIndex` at `0x10211f7f4`
- `sqldk!SystemThread_TlsIndex` at `0x10211f9e6`
- `sqldk!SystemThread_TlsIndex` at `0x10211fa86`
- `sqldk!SystemThread_TlsIndex` at `0x10211fe86`
- `sqldk!SystemThread_TlsIndex` at `0x10211ff3a`
- `sqldk!SystemThread_TlsIndex` at `0x10211fff0`
- `sqldk!SystemThread_TlsIndex` at `0x1021201f0`
- `sqldk!SystemThread_TlsIndex` at `0x102120291`
- `sqldk!SystemThread_TlsIndex` at `0x10212055d`
- `sqldk!SystemThread_TlsIndex` at `0x10212060e`
- `sqldk!SystemThread_TlsIndex` at `0x1021206c1`
- `sqldk!SystemThread_TlsIndex` at `0x1021208c2`
- `sqldk!SystemThread_TlsIndex` at `0x102120969`
- `sqldk!SystemThread_TlsIndex` at `0x102120c50`
- `sqldk!SystemThread_TlsIndex` at `0x102120d0b`
- `sqldk!SystemThread_TlsIndex` at `0x102120dc0`
- `sqldk!SystemThread_TlsIndex` at `0x102120fbd`
- `sqldk!SystemThread_TlsIndex` at `0x10212105e`
- `sqldk!SystemThread_TlsIndex` at `0x102121bc6`
- `sqldk!SystemThread_TlsIndex` at `0x102121c7a`
- `sqldk!SystemThread_TlsIndex` at `0x102121d30`
- `sqldk!SystemThread_TlsIndex` at `0x102121f3a`
- `sqldk!SystemThread_TlsIndex` at `0x102121fde`
- `sqldk!SystemThread_TlsIndex` at `0x1021225df`
- `sqldk!SystemThread_TlsIndex` at `0x102122693`
- `sqldk!SystemThread_TlsIndex` at `0x102122748`
- `sqldk!SystemThread_TlsIndex` at `0x10212293d`
- `sqldk!SystemThread_TlsIndex` at `0x1021229de`
- `sqldk!SystemThread_TlsOffset` at `0x10211f698`
- `sqldk!SystemThread_TlsOffset` at `0x10211f74d`
- `sqldk!SystemThread_TlsOffset` at `0x10211f7fd`
- `sqldk!SystemThread_TlsOffset` at `0x10211f9ef`
- `sqldk!SystemThread_TlsOffset` at `0x10211fa8f`
- `sqldk!SystemThread_TlsOffset` at `0x10211fe8f`
- `sqldk!SystemThread_TlsOffset` at `0x10211ff43`
- `sqldk!SystemThread_TlsOffset` at `0x10211fff9`
- `sqldk!SystemThread_TlsOffset` at `0x1021201f9`
- `sqldk!SystemThread_TlsOffset` at `0x10212029a`
- `sqldk!SystemThread_TlsOffset` at `0x102120566`
- `sqldk!SystemThread_TlsOffset` at `0x102120617`
- `sqldk!SystemThread_TlsOffset` at `0x1021206ca`
- `sqldk!SystemThread_TlsOffset` at `0x1021208cb`
- `sqldk!SystemThread_TlsOffset` at `0x102120972`
- `sqldk!SystemThread_TlsOffset` at `0x102120c59`
- `sqldk!SystemThread_TlsOffset` at `0x102120d14`
- `sqldk!SystemThread_TlsOffset` at `0x102120dc9`
- `sqldk!SystemThread_TlsOffset` at `0x102120fc6`
- `sqldk!SystemThread_TlsOffset` at `0x102121067`
- `sqldk!SystemThread_TlsOffset` at `0x102121bcf`
- `sqldk!SystemThread_TlsOffset` at `0x102121c83`
- `sqldk!SystemThread_TlsOffset` at `0x102121d39`
- `sqldk!SystemThread_TlsOffset` at `0x102121f43`
- `sqldk!SystemThread_TlsOffset` at `0x102121fe7`
- `sqldk!SystemThread_TlsOffset` at `0x1021225e8`
- `sqldk!SystemThread_TlsOffset` at `0x10212269c`
- `sqldk!SystemThread_TlsOffset` at `0x102122751`
- `sqldk!SystemThread_TlsOffset` at `0x102122946`
- `sqldk!SystemThread_TlsOffset` at `0x1021229e7`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall LongRecord::BuildNewRecord(
        LongRecord *this,
        int a2,
        const struct ColumnBinding *a3,
        int a4,
        __int64 a5,
        unsigned int a6,
        int a7,
        const struct Record *a8,
        struct RowObject *a9,
        struct DataAccessWrapper *a10,
        const struct CopiedVarCols *a11,
        const struct SEBitMap *a12,
        const struct CopiedVarCols *a13,
        struct SEBitMap *a14,
        int *a15,
        struct Record *a16,
        unsigned __int8 *const a17,
        unsigned int a18,
        unsigned int a19,
        unsigned int *a20,
        unsigned int *a21,
        int a22,
        struct SEBitMap *a23,
        int *a24,
        struct SetDataPropertyBag *a25,
        int a26,
        int *a27,
        unsigned int *a28,
        int *a29)
{
  const struct CopiedVarCols *v29; // r14
  Record *v30; // r12
  _WORD *v31; // rdi
  int v32; // ecx
  _WORD *v33; // rdi
  _WORD *v34; // rbx
  __int64 v35; // rsi
  void *v36; // rcx
  unsigned int v37; // eax
  unsigned int v38; // eax
  unsigned int inited; // ebx
  FixedVarRecord *v40; // r13
  unsigned int v41; // r14d
  Record *v42; // rsi
  const struct HoBtAccess *v43; // rcx
  __int64 v44; // rax
  const struct Record *v46; // r15
  unsigned __int16 *v47; // rsi
  unsigned int v48; // r14d
  unsigned int v49; // ebx
  char v50; // cl
  int v51; // eax
  int **v52; // rdi
  unsigned int v53; // eax
  unsigned int SparseColumnCount; // r8d
  unsigned int v55; // ecx
  char v56; // dl
  __int16 v57; // ax
  __int16 *v58; // r13
  Record *v59; // rbx
  FixedVarRecord *v60; // r15
  unsigned int v61; // edx
  unsigned int v62; // ecx
  unsigned int v63; // r12d
  __int64 v64; // rcx
  _BYTE *v65; // r9
  unsigned int v66; // ebx
  __int16 v67; // r14
  unsigned __int16 v68; // bx
  int i; // r8d
  __int64 v70; // rdx
  int v71; // eax
  int v72; // eax
  unsigned int v73; // ecx
  __int64 v74; // rdx
  unsigned int v75; // r12d
  unsigned __int64 v76; // rax
  __int64 v77; // rcx
  unsigned __int64 v78; // rcx
  void *v79; // rsp
  void *v80; // rsp
  unsigned int v81; // ebx
  unsigned int v82; // r11d
  unsigned int v83; // r14d
  unsigned int v84; // r13d
  struct VariableColumnSlot *v85; // r12
  int *v86; // r11
  unsigned int v87; // ebx
  int **v88; // rdi
  Record *v89; // r14
  unsigned int v90; // esi
  unsigned __int64 v91; // r8
  unsigned int *v92; // r12
  __int64 v93; // r9
  __int64 v94; // r13
  int v95; // eax
  __int64 v96; // rcx
  char v97; // r9
  __int64 v98; // rax
  __int64 v99; // rcx
  unsigned int v100; // r15d
  __int64 v101; // rcx
  _QWORD *v102; // rsi
  unsigned int v103; // r8d
  __int16 v104; // ax
  unsigned int v105; // eax
  unsigned int v106; // ebx
  int v107; // r14d
  __int64 v108; // rdi
  unsigned int *v109; // rbx
  int v110; // edi
  __int16 v111; // ax
  int v112; // r8d
  char *v113; // r8
  const struct PhysicalColumnAttribute *v114; // rdx
  char *v115; // r8
  __int64 v116; // r10
  unsigned int v117; // r9d
  unsigned __int16 *v118; // r10
  char *v119; // r8
  __int128 v120; // xmm0
  __int16 v121; // cx
  int v122; // edx
  unsigned int v123; // eax
  int v124; // ecx
  __int64 v125; // rdx
  char *v126; // r8
  char v127; // al
  unsigned __int16 *v128; // rdi
  unsigned __int16 v129; // cx
  __int64 v130; // rax
  __int64 v131; // rax
  unsigned int v132; // r8d
  __int64 v133; // rax
  __int64 v134; // rax
  __int64 v135; // rax
  __int64 v136; // rax
  __int64 v137; // r8
  __int64 v138; // rax
  unsigned int v139; // ebx
  unsigned int v140; // edx
  unsigned int v141; // eax
  unsigned __int16 v142; // cx
  unsigned __int16 v143; // ax
  struct RecVersioningInfo *VersioningInfo; // rax
  __int64 v145; // r9
  __int64 v146; // rdx
  int v147; // r8d
  __int16 v148; // ax
  unsigned __int64 v149; // r8
  int v150; // ecx
  __int64 v151; // rax
  __int64 v152; // rax
  __int64 v153; // rax
  __int64 v154; // rax
  __int64 v155; // r8
  __int16 v156; // dx
  bool v157; // zf
  _BYTE *v158; // rax
  _QWORD *v159; // rcx
  _QWORD *v160; // rax
  __int64 v161; // rax
  __int64 v162; // rdx
  __int64 v163; // r9
  unsigned int v164; // ecx
  int v165; // eax
  __int64 v166; // rdx
  char *v167; // r8
  char v168; // al
  unsigned __int16 *v169; // r14
  unsigned __int16 v170; // cx
  __int64 v171; // rax
  __int64 v172; // rax
  unsigned int v173; // r8d
  __int64 v174; // rax
  __int64 v175; // rax
  __int64 v176; // rax
  __int64 v177; // rax
  char *v178; // rax
  unsigned int v179; // ebx
  unsigned int v180; // edx
  unsigned int v181; // eax
  unsigned __int16 v182; // cx
  unsigned __int16 v183; // ax
  struct RecVersioningInfo *v184; // rax
  __int64 v185; // r9
  __int64 v186; // rdx
  int v187; // r8d
  __int16 v188; // ax
  unsigned __int64 v189; // r8
  int v190; // ecx
  __int64 v191; // rax
  __int64 v192; // rax
  __int64 v193; // rax
  __int64 v194; // rax
  __int64 v195; // r8
  __int16 v196; // dx
  char v197; // dl
  bool v198; // zf
  _BYTE *v199; // rax
  __int64 v200; // r8
  char *v201; // rdx
  char v202; // al
  unsigned __int16 *v203; // r14
  unsigned __int16 v204; // dx
  __int64 v205; // rax
  __int64 v206; // rax
  unsigned int v207; // r9d
  __int64 v208; // rax
  __int64 v209; // rax
  unsigned int v210; // ecx
  __int64 v211; // rax
  __int64 v212; // rax
  __int64 v213; // r9
  __int64 v214; // rax
  unsigned int v215; // ebx
  unsigned int v216; // r8d
  unsigned int v217; // eax
  unsigned __int16 v218; // cx
  int v219; // eax
  struct RecVersioningInfo *v220; // rax
  __int64 v221; // r9
  __int64 v222; // rdx
  int v223; // r8d
  __int16 v224; // ax
  unsigned __int64 v225; // rcx
  __int64 v226; // rax
  __int64 v227; // rax
  __int64 v228; // rax
  __int64 v229; // rax
  __int64 v230; // r8
  __int16 v231; // dx
  unsigned __int64 v232; // rax
  __int64 v233; // rcx
  unsigned __int64 v234; // rcx
  void *v235; // rsp
  void *v236; // rsp
  struct VariableColumnSlot *v237; // r13
  __int64 v238; // rdx
  char *v239; // r8
  char v240; // al
  unsigned __int16 *v241; // rdi
  unsigned __int16 v242; // r8
  __int64 v243; // rax
  __int64 v244; // rax
  const struct Record *v245; // r14
  unsigned int v246; // r9d
  __int64 v247; // rax
  __int64 v248; // rax
  unsigned int v249; // ecx
  __int64 v250; // rax
  __int64 v251; // rax
  char *v252; // r9
  char *v253; // rax
  unsigned int v254; // ebx
  unsigned int v255; // edx
  unsigned int v256; // eax
  unsigned __int16 v257; // cx
  unsigned __int16 v258; // ax
  int v259; // eax
  struct RecVersioningInfo *v260; // rax
  __int64 v261; // r9
  __int64 v262; // rdx
  int v263; // r8d
  __int16 v264; // ax
  unsigned __int64 v265; // r8
  int v266; // ecx
  __int64 v267; // rax
  __int64 v268; // rax
  __int64 v269; // rax
  __int64 v270; // rax
  int v271; // r11d
  __int64 v272; // rbx
  __int64 v273; // r9
  unsigned __int16 v274; // cx
  int v275; // r8d
  __int64 v276; // rdx
  unsigned __int64 v277; // rdi
  unsigned int v278; // ecx
  __int64 v279; // r15
  unsigned __int16 *v280; // r12
  unsigned int v281; // r13d
  __int64 v282; // r14
  __int64 v283; // r8
  unsigned __int16 v284; // r9
  unsigned __int16 v285; // r9
  __int64 v286; // r10
  __int16 *v287; // rbx
  char *v288; // r11
  unsigned __int64 v289; // rdi
  __int16 v290; // si
  __int16 v291; // cx
  int v292; // edx
  __int64 v293; // r8
  unsigned __int16 v294; // dx
  LongRecord *v295; // rbx
  __int64 v296; // r14
  unsigned int *v297; // rbx
  __int64 v298; // rsi
  int *v299; // r15
  unsigned int *v300; // r12
  int v301; // edi
  const struct HoBtColumnAttribute *HoBtColumnAttributeByHoBtColumnId; // rax
  unsigned int v303; // eax
  const struct Record *v304; // rbx
  unsigned int v305; // esi
  struct SetDataPropertyBag *v306; // r10
  __int64 v307; // r9
  int *v308; // rcx
  int v309; // eax
  int v310; // eax
  int v311; // eax
  const struct PhysicalColumnAttribute *v312; // rdx
  _BYTE *v313; // r10
  char v314; // cl
  __int16 v315; // r8
  signed int v316; // r9d
  __int64 v317; // r10
  signed int v318; // esi
  struct VariableColumnSlot *v319; // r13
  unsigned __int64 v320; // r11
  char *v321; // rcx
  _BYTE *v322; // rcx
  _BYTE *v323; // r10
  char v324; // cl
  __int16 v325; // r8
  _BYTE *v326; // rcx
  unsigned int *v327; // r10
  int v328; // r11d
  unsigned int v329; // r8d
  int v330; // r9d
  struct VariableColumnSlot *v331; // rbx
  unsigned int v332; // ecx
  int v333; // eax
  signed int v334; // eax
  unsigned int v335; // eax
  char *v336; // r8
  _BYTE *v337; // rcx
  struct VariableColumnSlot *v338; // r15
  _DWORD *v339; // rcx
  __int64 v340; // r10
  char *v341; // rbx
  unsigned int v342; // ecx
  __int64 v343; // r8
  _BYTE *v344; // r9
  char v345; // al
  _BYTE *v346; // rdx
  unsigned __int16 *v347; // rsi
  unsigned __int16 v348; // dx
  __int64 v349; // rax
  __int64 v350; // rax
  unsigned int v351; // r9d
  __int64 v352; // rax
  __int64 v353; // rax
  __int64 v354; // rax
  __int64 v355; // rax
  __int64 v356; // r9
  __int64 v357; // rax
  unsigned int v358; // edi
  unsigned int v359; // r8d
  unsigned int v360; // eax
  unsigned __int16 v361; // dx
  unsigned __int16 v362; // ax
  int v363; // eax
  struct RecVersioningInfo *v364; // rax
  __int64 v365; // r9
  __int64 v366; // rdx
  int v367; // r8d
  __int16 v368; // ax
  unsigned __int64 v369; // r9
  __int64 v370; // rax
  __int64 v371; // rax
  __int64 v372; // rax
  __int64 v373; // rax
  _BYTE *v374; // r8
  unsigned int v375; // edi
  __int64 v376; // rax
  __int64 v377; // r8
  _WORD *v378; // rsi
  unsigned int v379; // edx
  __int16 v380; // cx
  int v381; // ecx
  unsigned int v382; // edx
  __int16 v383; // cx
  unsigned int v384; // edx
  unsigned int v385; // r8d
  unsigned int *v386; // r12
  struct VariableColumnSlot *v387; // rsi
  unsigned int v388; // eax
  int v389; // r12d
  int v390; // r14d
  unsigned int v391; // edi
  char *v392; // rbx
  __int64 v393; // r15
  LongRecord *v394; // r13
  __int64 v395; // rsi
  const struct HoBtColumnAttribute *v396; // rax
  unsigned int v397; // r9d
  __int16 v398; // dx
  unsigned int v399; // ecx
  _BYTE *v400; // rax
  __int64 v401; // rdx
  char v402; // al
  unsigned __int16 *v403; // rdi
  unsigned __int16 v404; // cx
  __int64 v405; // rax
  __int64 v406; // rax
  unsigned int v407; // r8d
  __int64 v408; // rax
  __int64 v409; // rax
  __int64 v410; // rax
  __int64 v411; // rax
  __int64 v412; // rdx
  unsigned __int64 v413; // rax
  unsigned int v414; // ebx
  unsigned int v415; // ecx
  unsigned int v416; // eax
  unsigned __int16 v417; // cx
  unsigned __int16 v418; // ax
  struct RecVersioningInfo *v419; // rax
  __int64 v420; // r9
  __int64 v421; // rdx
  int v422; // r8d
  __int16 v423; // ax
  int v424; // ecx
  __int64 v425; // rax
  __int64 v426; // rax
  __int64 v427; // rax
  __int64 v428; // rax
  __int64 v429; // r8
  __int16 v430; // dx
  char v431; // cl
  unsigned int v432; // ecx
  _BYTE *v433; // rax
  struct VariableColumnSlot *v434; // [rsp+20h] [rbp-10h]
  unsigned int *v435; // [rsp+28h] [rbp-8h]
  unsigned int v436; // [rsp+30h] [rbp+0h] BYREF
  int v437; // [rsp+34h] [rbp+4h]
  unsigned int v438; // [rsp+38h] [rbp+8h]
  unsigned int SEDefaultMax; // [rsp+3Ch] [rbp+Ch]
  __int64 v440; // [rsp+40h] [rbp+10h]
  Record *v441; // [rsp+48h] [rbp+18h]
  struct VariableColumnSlot *v442; // [rsp+50h] [rbp+20h]
  FixedVarRecord *v443; // [rsp+58h] [rbp+28h]
  unsigned int v444; // [rsp+60h] [rbp+30h]
  unsigned int v445; // [rsp+64h] [rbp+34h]
  unsigned int v446; // [rsp+68h] [rbp+38h]
  BOOL v447; // [rsp+6Ch] [rbp+3Ch]
  struct VariableColumnSlot *v448; // [rsp+70h] [rbp+40h]
  int *v449; // [rsp+78h] [rbp+48h]
  unsigned int v450; // [rsp+80h] [rbp+50h]
  struct DataAccessWrapper *v451; // [rsp+88h] [rbp+58h]
  int v452; // [rsp+90h] [rbp+60h]
  unsigned int v453; // [rsp+94h] [rbp+64h] BYREF
  const struct Record *v454; // [rsp+98h] [rbp+68h]
  unsigned int *v455; // [rsp+A0h] [rbp+70h]
  struct SEBitMap *v456; // [rsp+A8h] [rbp+78h]
  int v457; // [rsp+B0h] [rbp+80h]
  __int64 v458; // [rsp+B8h] [rbp+88h]
  LongRecord *v459; // [rsp+C0h] [rbp+90h]
  unsigned __int64 v460; // [rsp+C8h] [rbp+98h]
  __int64 v461; // [rsp+D0h] [rbp+A0h]
  int **v462; // [rsp+D8h] [rbp+A8h]
  const struct CopiedVarCols *v463; // [rsp+E0h] [rbp+B0h]
  unsigned int *v464; // [rsp+E8h] [rbp+B8h]
  struct RowObject *v465; // [rsp+F0h] [rbp+C0h]
  unsigned __int16 *v466; // [rsp+F8h] [rbp+C8h]
  __int128 v467; // [rsp+100h] [rbp+D0h]
  struct RowObject *v468; // [rsp+110h] [rbp+E0h]
  __int64 v469; // [rsp+118h] [rbp+E8h]
  unsigned __int16 *v470; // [rsp+120h] [rbp+F0h]
  int *v471; // [rsp+128h] [rbp+F8h]
  struct SEBitMap *v472; // [rsp+130h] [rbp+100h]
  int *v473; // [rsp+138h] [rbp+108h]
  unsigned int *v474; // [rsp+140h] [rbp+110h]
  struct SetDataPropertyBag *v475; // [rsp+148h] [rbp+118h]
  const struct ColumnBinding *v476; // [rsp+150h] [rbp+120h]
  const struct CopiedVarCols *v477; // [rsp+158h] [rbp+128h]
  int *v478; // [rsp+160h] [rbp+130h]
  struct RowObject *v479; // [rsp+168h] [rbp+138h]
  __int16 v480; // [rsp+170h] [rbp+140h] BYREF
  char v481[2]; // [rsp+172h] [rbp+142h] BYREF
  int v482; // [rsp+174h] [rbp+144h]
  __int64 v483; // [rsp+178h] [rbp+148h]
  __int64 v484; // [rsp+180h] [rbp+150h]
  __int64 v485; // [rsp+18Eh] [rbp+15Eh]
  __int64 v486; // [rsp+198h] [rbp+168h]
  __int64 v487; // [rsp+1A8h] [rbp+178h]
  unsigned __int8 v488[32]; // [rsp+1B0h] [rbp+180h] BYREF
  unsigned __int8 v489[8096]; // [rsp+1D0h] [rbp+1A0h] BYREF

  v487 = -2;
  v452 = a4;
  v476 = a3;
  LODWORD(v440) = a2;
  v459 = this;
  v444 = a6;
  v46 = a8;
  v454 = a8;
  v479 = a9;
  v451 = a10;
  v477 = a11;
  v463 = a13;
  v456 = a14;
  v449 = a15;
  v441 = a16;
  v455 = a20;
  v464 = a21;
  v472 = a23;
  v471 = a24;
  v475 = a25;
  v478 = a27;
  v474 = a28;
  v473 = a29;
  v442 = 0;
  v448 = 0;
  v480 = -1;
  v483 = 0;
  v482 = 0;
  v485 = 0;
  v486 = 0;
  v484 = 0;
  v447 = 0;
  v437 = 1;
  v462 = 0;
  v450 = 0;
  *a24 = 0;
  if ( a9 && *((_DWORD *)a9 + 2) == 1 )
  {
    *((_DWORD *)a9 + 156) = 0;
    *((_QWORD *)a9 + 80) = 0;
    *((_QWORD *)a9 + 82) = 0;
    *((_DWORD *)a9 + 168) = -1;
    *((_WORD *)a9 + 338) = -1;
    *(_QWORD *)((char *)a9 + 678) = 0;
    *((_DWORD *)a9 + 316) = 0;
    *((_QWORD *)a9 + 160) = 0;
    *((_QWORD *)a9 + 162) = 0;
    *((_DWORD *)a9 + 328) = -1;
    *((_WORD *)a9 + 658) = -1;
    *(_QWORD *)((char *)a9 + 1318) = 0;
    v468 = a9;
    *(_BYTE *)(*((_QWORD *)a9 + 5) + 181LL) = *(_BYTE *)(*((_QWORD *)a9 + 5) + 180LL) != 0;
    v465 = a9;
  }
  else
  {
    v468 = 0;
    v465 = 0;
  }
  if ( a9 )
  {
    v46 = (const struct Record *)(**(__int64 (__fastcall ***)(struct RowObject *))a9)(a9);
    v454 = v46;
  }
  v47 = (unsigned __int16 *)((char *)v46 + 2);
  v470 = (unsigned __int16 *)((char *)v46 + 2);
  if ( *(_WORD *)v46 )
  {
    v48 = *v47;
    v49 = v48;
    if ( v48 <= -(int)a5 )
      v49 = -(int)a5;
    v50 = **((_BYTE **)v46 + 1);
  }
  else
  {
    v48 = FixedVarRecord::NumVarCol((const struct Record *)((char *)v46 + 2));
    v49 = v48;
    if ( v48 <= -(int)a5 )
      v49 = -(int)a5;
    v50 = **((_BYTE **)v46 + 1);
    if ( !*(_WORD *)v46 )
    {
      v51 = (1 << (v50 & 0xE)) & 0x1105;
      goto LABEL_10;
    }
  }
  v123 = v50 & 0x1C;
  v51 = 0;
  if ( v123 <= 0x10 )
  {
    v124 = 69633;
    if ( _bittest(&v124, v123) )
      v51 = 1;
  }
LABEL_10:
  SEDefaultMax = v49;
  if ( v51 )
  {
    v52 = (int **)*((_QWORD *)v451 + 5);
    v462 = v52;
    v53 = *((_DWORD *)v451 + 12);
    v450 = v53;
    SEDefaultMax = v49;
    if ( v53 )
    {
      SEDefaultMax = v49;
      if ( v49 <= (unsigned int)ShortRecord::GetSEDefaultMaxOffset<Record>(v52, v53, v46) )
      {
        _mm_lfence();
        SEDefaultMax = ShortRecord::GetSEDefaultMaxOffset<Record>(v52, v450, v46);
      }
    }
  }
  SparseColumnCount = Record::GetSparseColumnCount(v46);
  v438 = SparseColumnCount;
  v445 = SparseColumnCount;
  v436 = SparseColumnCount + v452;
  v446 = 9;
  if ( a25 )
  {
    if ( *(_WORD *)v46 )
    {
      v55 = *((_DWORD *)v46 + 1);
      if ( !v55 )
      {
        CDRecord::Resize((const struct Record *)((char *)v46 + 2));
        v55 = *((_DWORD *)v46 + 1);
        SparseColumnCount = v438;
      }
      if ( v55 >= 9 )
        goto LABEL_18;
      v158 = (_BYTE *)*((_QWORD *)v46 + 1);
      if ( (*v158 & 0x1C) == 0 )
        goto LABEL_17;
      v157 = (*v158 & 0x1C) == 12;
      goto LABEL_247;
    }
    if ( *((_DWORD *)v46 + 1) )
    {
LABEL_15:
      v55 = *((_DWORD *)v46 + 1);
      if ( v55 >= 9 )
      {
LABEL_18:
        *(_DWORD *)a25 = v55;
        *((_DWORD *)a25 + 1) = v48;
        *((_DWORD *)a25 + 2) = SparseColumnCount;
        *(_QWORD *)((char *)a25 + 12) = 0;
        goto LABEL_19;
      }
      v56 = **((_BYTE **)v46 + 1) & 0xE;
      if ( !v56 )
      {
LABEL_17:
        v55 = 9;
        goto LABEL_18;
      }
      v157 = v56 == 12;
LABEL_247:
      if ( !v157 )
        goto LABEL_18;
      goto LABEL_17;
    }
    *v47 = 0;
    v125 = *((unsigned int *)v46 + 4);
    *((_DWORD *)v46 + 5) = v125;
    v126 = (char *)*((_QWORD *)v46 + 1);
    v127 = *v126;
    if ( (*v126 & 0x10) != 0 )
    {
      LODWORD(v125) = (((unsigned int)*(unsigned __int16 *)&v126[v125] + 7) >> 3) + v125 + 2;
      *((_DWORD *)v46 + 5) = v125;
      v127 = *v126;
    }
    if ( (v127 & 0x20) != 0 )
    {
      v128 = (unsigned __int16 *)&v126[(unsigned int)v125];
      v129 = *v128;
      *((_WORD *)v46 + 14) = *v128;
      if ( !v129 )
      {
        if ( byte_10316E8D7 || (qword_10317B120 & 1) != 0 )
        {
          v130 = *(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                           + SystemThread_TlsOffset
                           + 8LL);
          if ( v130 )
          {
            v131 = *(_QWORD *)(v130 + 96);
            if ( v131 )
            {
              if ( *(_BYTE *)(v131 + 1177) )
              {
                if ( byte_10316E7C7 || (qword_10317B120 & 2) != 0 )
                  utassert_fail(1u, "false", "Sql\\Ntdbms\\storeng\\drs\\fixedvarrecord.cpp", 2010, 0);
                else
                  ex_raise(34, 68, 21, 1003);
              }
            }
          }
        }
        RaiseInconsistencyError(*((_QWORD *)v46 + 1), 3);
        v129 = *((_WORD *)v46 + 14);
        LODWORD(v125) = *((_DWORD *)v46 + 5);
      }
      v132 = v125 + 2 * (v129 + 1);
      *((_DWORD *)v46 + 6) = v132;
      if ( v132 > 0x1F9E )
      {
        if ( byte_10316E8D7 || (qword_10317B120 & 1) != 0 )
        {
          v133 = *(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                           + SystemThread_TlsOffset
                           + 8LL);
          if ( v133 )
          {
            v134 = *(_QWORD *)(v133 + 96);
            if ( v134 )
            {
              if ( *(_BYTE *)(v134 + 1177) )
              {
                if ( byte_10316E7C7 || (qword_10317B120 & 2) != 0 )
                  utassert_fail(1u, "false", "Sql\\Ntdbms\\storeng\\drs\\fixedvarrecord.cpp", 2017, 0);
                else
                  ex_raise(34, 68, 21, 1004);
              }
            }
          }
        }
        RaiseInconsistencyError(*((_QWORD *)v46 + 1), 4);
        v129 = *((_WORD *)v46 + 14);
        v132 = *((_DWORD *)v46 + 6);
      }
      LODWORD(v125) = v128[v129] & 0x7FFF;
      *((_DWORD *)v46 + 1) = v125;
      if ( v132 > (unsigned int)v125 )
      {
        if ( byte_10316E8D7 || (qword_10317B120 & 1) != 0 )
        {
          v135 = *(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                           + SystemThread_TlsOffset
                           + 8LL);
          if ( v135 )
          {
            v136 = *(_QWORD *)(v135 + 96);
            if ( v136 )
            {
              if ( *(_BYTE *)(v136 + 1177) )
              {
                if ( byte_10316E7C7 || (qword_10317B120 & 2) != 0 )
                  utassert_fail(1u, "false", "Sql\\Ntdbms\\storeng\\drs\\fixedvarrecord.cpp", 2024, 0);
                else
                  ex_raise(34, 68, 21, 1004);
              }
            }
          }
        }
        RaiseInconsistencyError(*((_QWORD *)v46 + 1), 4);
        v129 = *((_WORD *)v46 + 14);
        LODWORD(v125) = *((_DWORD *)v46 + 1);
      }
      if ( (v128[v129] & 0x8000u) != 0 )
      {
        v137 = *((_QWORD *)v46 + 1);
        while ( 1 )
        {
          v138 = v137 + *((unsigned int *)v46 + 5);
          if ( v129 == 1 )
          {
            v139 = *((_DWORD *)v46 + 6);
            v140 = v139;
            v141 = *(_WORD *)(v138 + 2LL * v129) & 0x7FFF;
          }
          else
          {
            v139 = *(_WORD *)(v138 + 2LL * v129 - 2) & 0x7FFF;
            v140 = *((_DWORD *)v46 + 6);
            v141 = *(_WORD *)(v138 + 2LL * v129) & 0x7FFF;
            if ( v139 < v140 )
            {
LABEL_196:
              RaiseInconsistencyError(v137, 7);
              v140 = *((_DWORD *)v46 + 6);
              goto LABEL_197;
            }
          }
          if ( v141 < v139 )
            goto LABEL_196;
LABEL_197:
          if ( v139 < v140 )
            goto LABEL_233;
          LODWORD(v125) = *((_DWORD *)v46 + 1);
          if ( v139 > (unsigned int)v125 )
            goto LABEL_233;
          v137 = *((_QWORD *)v46 + 1);
          v142 = *(_WORD *)(v139 + v137);
          if ( v142 == 5 )
          {
            *v47 |= 2u;
            --*((_WORD *)v46 + 14);
            *((_WORD *)v46 + 21) = v139;
            v155 = *((_QWORD *)v46 + 1) + (unsigned __int16)v139;
            v156 = *((_WORD *)v46 + 22) & 0xC7FF;
            if ( (*(_WORD *)(v155 + 2) & 0x4000) != 0 )
              v156 |= *(_WORD *)(v155 + 2) & 0x3800;
            *((_WORD *)v46 + 22) = v156;
            *((_WORD *)v46 + 22) = v156 ^ (*(_WORD *)(v155 + 2) ^ v156) & 0x7FF;
            LODWORD(v125) = *((_DWORD *)v46 + 1);
            v126 = (char *)*((_QWORD *)v46 + 1);
            goto LABEL_204;
          }
          if ( v142 >= 0x400u )
          {
            *v47 |= 1u;
            v143 = *((_WORD *)v46 + 14) - 1;
            *((_WORD *)v46 + 14) = v143;
            if ( v143 )
            {
              v129 = v143;
              if ( (v128[v143] & 0x8000u) != 0 )
                continue;
            }
          }
          break;
        }
      }
      v126 = (char *)*((_QWORD *)v46 + 1);
    }
    else
    {
      *((_DWORD *)v46 + 1) = v125;
      *((_WORD *)v46 + 14) = 0;
      *((_DWORD *)v46 + 6) = v125;
    }
LABEL_204:
    if ( (*v126 & 0x40) != 0 )
    {
      *(_DWORD *)((char *)v46 + 38) = v125;
      *((_DWORD *)v46 + 1) = v125 + 14;
      VersioningInfo = FixedVarRecord::FindVersioningInfo((const struct Record *)((char *)v46 + 2));
      v145 = HIDWORD(*(_QWORD *)VersioningInfo);
      v146 = HIWORD(*(_QWORD *)VersioningInfo);
      v147 = 0;
      if ( (((__int16)v146 ^ ((unsigned int)(__int16)v146 >> 1)) & 0x2000) != 0 )
      {
        v148 = v146 & 0xDFFF;
        if ( (v146 & 0x4000) != 0 )
          v148 = v146 | 0x2000;
        LOWORD(v146) = v148;
      }
      if ( (_WORD)v146 == 0xFFFC )
        v147 = (unsigned __int16)v145 >> 5;
      *((_DWORD *)v46 + 1) += v147;
      LODWORD(v125) = *((_DWORD *)v46 + 1);
    }
    else
    {
      *(_DWORD *)((char *)v46 + 38) = 0;
    }
    v149 = *(_QWORD *)((char *)v46 + 30);
    v150 = v125;
    if ( v149 && v149 < *((_QWORD *)v46 + 1) + (unsigned __int64)(unsigned int)v125 )
    {
      if ( byte_10316E8D7 || (qword_10317B120 & 1) != 0 )
      {
        v151 = *(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                         + SystemThread_TlsOffset
                         + 8LL);
        if ( v151 )
        {
          v152 = *(_QWORD *)(v151 + 96);
          if ( v152 )
          {
            if ( *(_BYTE *)(v152 + 1177) )
            {
              if ( byte_10316E7C7 || (qword_10317B120 & 2) != 0 )
                utassert_fail(1u, "false", "Sql\\Ntdbms\\storeng\\drs\\fixedvarrecord.cpp", 2114, 0);
              else
                ex_raise(34, 68, 21, 1018);
            }
          }
        }
      }
      RaiseInconsistencyError(*((_QWORD *)v46 + 1), 18);
      v150 = *((_DWORD *)v46 + 1);
    }
    if ( (unsigned int)(v150 - 1) > 0x3F3B )
    {
      if ( byte_10316E8D7 || (qword_10317B120 & 1) != 0 )
      {
        v153 = *(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                         + SystemThread_TlsOffset
                         + 8LL);
        if ( v153 )
        {
          v154 = *(_QWORD *)(v153 + 96);
          if ( v154 )
          {
            if ( *(_BYTE *)(v154 + 1177) )
            {
              if ( byte_10316E7C7 || (qword_10317B120 & 2) != 0 )
                utassert_fail(1u, "false", "Sql\\Ntdbms\\storeng\\drs\\fixedvarrecord.cpp", 2119, 0);
              else
                ex_raise(34, 68, 21, 1005);
            }
          }
        }
      }
      RaiseInconsistencyError(*((_QWORD *)v46 + 1), 5);
    }
LABEL_233:
    SparseColumnCount = v438;
    goto LABEL_15;
  }
LABEL_19:
  v57 = *(_WORD *)v46;
  if ( *(_WORD *)v46 && (v159 = (_QWORD *)*((_QWORD *)v46 + 2)) != 0 && *v159 )
  {
    v480 = *(_WORD *)v46;
    if ( *(_WORD *)v46 && (v160 = (_QWORD *)*((_QWORD *)v46 + 2)) != 0 && *v160 )
    {
      Record::DecompressRec((Record *)&v480, v489, 0x1F9Eu, v46);
      v58 = &v480;
      v57 = v480;
    }
    else
    {
      CDRecord::CopyNewRec((CDRecord *)v481, v489, 0x1F9Eu, (const struct Record *)((char *)v46 + 2));
      v161 = 0;
      if ( *(_WORD *)v46 )
        v161 = *((_QWORD *)v46 + 2);
      v484 = v161;
      v58 = &v480;
      v57 = v480;
    }
  }
  else
  {
    v58 = (__int16 *)v46;
  }
  v59 = v441;
  *(_WORD *)v441 = v57;
  v60 = (Record *)((char *)v59 + 2);
  v443 = (Record *)((char *)v59 + 2);
  if ( v57 )
  {
    CDRecord::InitFixedFromOld(
      (Record *)((char *)v59 + 2),
      a17,
      SparseColumnCount,
      (const struct CDRecord *)(v58 + 1),
      v444);
  }
  else
  {
    *((_QWORD *)v59 + 1) = a17;
    *((_DWORD *)v59 + 4) = a7;
    *((_WORD *)v59 + 14) = 0;
    *(_WORD *)v60 = 0;
    *(_DWORD *)((char *)v59 + 38) = 0;
    if ( (**((_BYTE **)v58 + 1) & 0xE) == 6 )
    {
      *a17 = 6;
      v61 = 1;
    }
    else
    {
      *a17 = 0;
      *(_BYTE *)(*((_QWORD *)v59 + 1) + 1LL) = 0;
      *(_WORD *)(*((_QWORD *)v59 + 1) + 2LL) = *((_DWORD *)v59 + 4);
      v61 = 4;
    }
    v62 = *((_DWORD *)v58 + 4);
    if ( v62 >= *((_DWORD *)v59 + 4) )
      v62 = *((_DWORD *)v59 + 4);
    memmove((void *)(v61 + *((_QWORD *)v59 + 1)), (const void *)(v61 + *((_QWORD *)v58 + 1)), v62 - v61);
    v63 = v444;
    if ( v444 )
    {
      **((_BYTE **)v59 + 1) |= 0x10u;
      v64 = *((unsigned int *)v59 + 4);
      *((_DWORD *)v59 + 5) = ((v63 + 7) >> 3) + v64 + 2;
      v65 = (_BYTE *)*((_QWORD *)v58 + 1);
      if ( (*v65 & 0x10) != 0 )
      {
        v66 = *(unsigned __int16 *)&v65[*((unsigned int *)v58 + 4)];
        if ( v66 == v63 )
        {
          memmove(
            (void *)((unsigned int)v64 + *(_QWORD *)((char *)v60 + 6)),
            &v65[*((unsigned int *)v58 + 4)],
            ((v63 + 7) >> 3) + 2);
          v72 = *(_DWORD *)((char *)v60 + 18);
          v59 = v441;
          *(_DWORD *)((char *)v60 + 22) = v72;
          *(_DWORD *)((char *)v60 + 2) = v72;
          goto LABEL_36;
        }
        v67 = v63;
        *(_WORD *)(*(_QWORD *)((char *)v60 + 6) + v64) = v63;
        if ( v66 )
        {
          v162 = *((unsigned int *)v58 + 4);
          v163 = *(unsigned int *)((char *)v60 + 14);
          v164 = *(_DWORD *)((char *)v60 + 18) - v163;
          if ( v164 >= *((_DWORD *)v58 + 5) - (int)v162 )
            v164 = *((_DWORD *)v58 + 5) - v162;
          memmove(
            (void *)(v163 + 2 + *(_QWORD *)((char *)v60 + 6)),
            (const void *)(*((_QWORD *)v58 + 1) + 2LL + v162),
            v164 - 2);
        }
      }
      else
      {
        v66 = 0;
        v67 = v63;
        *(_WORD *)(*(_QWORD *)((char *)v60 + 6) + v64) = v63;
      }
      if ( v63 < v66 )
        LOWORD(v66) = v67;
      v68 = v66 + 1;
      for ( i = v68; v68 <= v63; i = v68 )
      {
        v70 = *(_QWORD *)((char *)v60 + 6) + *(int *)((char *)v60 + 14);
        *(_BYTE *)(((unsigned __int64)(unsigned int)(i - 1) >> 3) + v70 + 2) |= 1 << ((i - 1) & 7);
        ++v68;
      }
      v71 = *(_DWORD *)((char *)v60 + 18);
      v59 = v441;
      *(_DWORD *)((char *)v60 + 22) = v71;
      *(_DWORD *)((char *)v60 + 2) = v71;
    }
    else
    {
      v165 = *((_DWORD *)v59 + 4);
      *((_DWORD *)v59 + 5) = v165;
      *((_DWORD *)v59 + 6) = v165;
      *((_DWORD *)v59 + 1) = v165;
    }
  }
LABEL_36:
  if ( !*(_WORD *)v59 )
  {
    if ( *(_DWORD *)((char *)v60 + 2) )
      goto LABEL_38;
    *(_WORD *)v60 = 0;
    v166 = *(unsigned int *)((char *)v60 + 14);
    *(_DWORD *)((char *)v60 + 18) = v166;
    v167 = *(char **)((char *)v60 + 6);
    v168 = *v167;
    if ( (*v167 & 0x10) != 0 )
    {
      LODWORD(v166) = (((unsigned int)*(unsigned __int16 *)&v167[v166] + 7) >> 3) + v166 + 2;
      *(_DWORD *)((char *)v60 + 18) = v166;
      v168 = *v167;
    }
    if ( (v168 & 0x20) != 0 )
    {
      v169 = (unsigned __int16 *)&v167[(unsigned int)v166];
      v170 = *v169;
      *((_WORD *)v60 + 13) = *v169;
      if ( !v170 )
      {
        if ( byte_10316E8D7 || (qword_10317B120 & 1) != 0 )
        {
          v171 = *(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                           + SystemThread_TlsOffset
                           + 8LL);
          if ( v171 )
          {
            v172 = *(_QWORD *)(v171 + 96);
            if ( v172 )
            {
              if ( *(_BYTE *)(v172 + 1177) )
              {
                if ( byte_10316E7C7 || (qword_10317B120 & 2) != 0 )
                  utassert_fail(1u, "false", "Sql\\Ntdbms\\storeng\\drs\\fixedvarrecord.cpp", 2010, 0);
                else
                  ex_raise(34, 68, 21, 1003);
              }
            }
          }
        }
        RaiseInconsistencyError(*(_QWORD *)((char *)v60 + 6), 3);
        v170 = *((_WORD *)v60 + 13);
        LODWORD(v166) = *(_DWORD *)((char *)v60 + 18);
      }
      v173 = v166 + 2 * (v170 + 1);
      *(_DWORD *)((char *)v60 + 22) = v173;
      if ( v173 > 0x1F9E )
      {
        if ( byte_10316E8D7 || (qword_10317B120 & 1) != 0 )
        {
          v174 = *(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                           + SystemThread_TlsOffset
                           + 8LL);
          if ( v174 )
          {
            v175 = *(_QWORD *)(v174 + 96);
            if ( v175 )
            {
              if ( *(_BYTE *)(v175 + 1177) )
              {
                if ( byte_10316E7C7 || (qword_10317B120 & 2) != 0 )
                  utassert_fail(1u, "false", "Sql\\Ntdbms\\storeng\\drs\\fixedvarrecord.cpp", 2017, 0);
                else
                  ex_raise(34, 68, 21, 1004);
              }
            }
          }
        }
        RaiseInconsistencyError(*(_QWORD *)((char *)v60 + 6), 4);
        v170 = *((_WORD *)v60 + 13);
        v173 = *(_DWORD *)((char *)v60 + 22);
      }
      LODWORD(v166) = v169[v170] & 0x7FFF;
      *(_DWORD *)((char *)v60 + 2) = v166;
      if ( v173 > (unsigned int)v166 )
      {
        if ( byte_10316E8D7 || (qword_10317B120 & 1) != 0 )
        {
          v176 = *(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                           + SystemThread_TlsOffset
                           + 8LL);
          if ( v176 )
          {
            v177 = *(_QWORD *)(v176 + 96);
            if ( v177 )
            {
              if ( *(_BYTE *)(v177 + 1177) )
              {
                if ( byte_10316E7C7 || (qword_10317B120 & 2) != 0 )
                  utassert_fail(1u, "false", "Sql\\Ntdbms\\storeng\\drs\\fixedvarrecord.cpp", 2024, 0);
                else
                  ex_raise(34, 68, 21, 1004);
              }
            }
          }
        }
        RaiseInconsistencyError(*(_QWORD *)((char *)v60 + 6), 4);
        v170 = *((_WORD *)v60 + 13);
        LODWORD(v166) = *(_DWORD *)((char *)v60 + 2);
      }
      if ( (v169[v170] & 0x8000u) != 0 )
      {
        v167 = *(char **)((char *)v60 + 6);
        while ( 1 )
        {
          v178 = &v167[*(unsigned int *)((char *)v60 + 18)];
          if ( v170 == 1 )
          {
            v179 = *(_DWORD *)((char *)v60 + 22);
            v180 = v179;
            v181 = *(_WORD *)&v178[2 * v170] & 0x7FFF;
          }
          else
          {
            v179 = *(_WORD *)&v178[2 * v170 - 2] & 0x7FFF;
            v180 = *(_DWORD *)((char *)v60 + 22);
            v181 = *(_WORD *)&v178[2 * v170] & 0x7FFF;
            if ( v179 < v180 )
            {
LABEL_309:
              RaiseInconsistencyError(v167, 7);
              v180 = *(_DWORD *)((char *)v60 + 22);
              goto LABEL_310;
            }
          }
          if ( v181 < v179 )
            goto LABEL_309;
LABEL_310:
          if ( v179 < v180 )
            goto LABEL_38;
          LODWORD(v166) = *(_DWORD *)((char *)v60 + 2);
          if ( v179 > (unsigned int)v166 )
            goto LABEL_38;
          v167 = *(char **)((char *)v60 + 6);
          v182 = *(_WORD *)&v167[v179];
          if ( v182 == 5 )
          {
            *(_WORD *)v60 |= 2u;
            --*((_WORD *)v60 + 13);
            *((_WORD *)v60 + 20) = v179;
            v195 = *(_QWORD *)((char *)v60 + 6) + (unsigned __int16)v179;
            v196 = *((_WORD *)v60 + 21) & 0xC7FF;
            if ( _bittest16((const signed __int16 *)(v195 + 2), 0xEu) )
              v196 |= *(_WORD *)(v195 + 2) & 0x3800;
            *((_WORD *)v60 + 21) = v196;
            *((_WORD *)v60 + 21) = v196 ^ (*(_WORD *)(v195 + 2) ^ v196) & 0x7FF;
            LODWORD(v166) = *((_DWORD *)v441 + 1);
            break;
          }
          if ( v182 < 0x400u )
            break;
          *(_WORD *)v60 |= 1u;
          v183 = *((_WORD *)v60 + 13) - 1;
          *((_WORD *)v60 + 13) = v183;
          if ( !v183 )
            break;
          v170 = v183;
          if ( (v169[v183] & 0x8000u) == 0 )
            goto LABEL_316;
        }
      }
      v167 = *(char **)((char *)v60 + 6);
    }
    else
    {
      *(_DWORD *)((char *)v60 + 2) = v166;
      *((_WORD *)v60 + 13) = 0;
      *(_DWORD *)((char *)v60 + 22) = v166;
    }
LABEL_316:
    if ( (*v167 & 0x40) != 0 )
    {
      *((_DWORD *)v60 + 9) = v166;
      *(_DWORD *)((char *)v60 + 2) = v166 + 14;
      v184 = FixedVarRecord::FindVersioningInfo(v60);
      v185 = HIDWORD(*(_QWORD *)v184);
      v186 = HIWORD(*(_QWORD *)v184);
      v187 = 0;
      if ( (((__int16)v186 ^ ((unsigned int)(__int16)v186 >> 1)) & 0x2000) != 0 )
      {
        v188 = v186 & 0xDFFF;
        if ( (v186 & 0x4000) != 0 )
          v188 = v186 | 0x2000;
        LOWORD(v186) = v188;
      }
      if ( (_WORD)v186 == 0xFFFC )
        v187 = (unsigned __int16)v185 >> 5;
      *(_DWORD *)((char *)v60 + 2) += v187;
      LODWORD(v166) = *(_DWORD *)((char *)v60 + 2);
    }
    else
    {
      *((_DWORD *)v60 + 9) = 0;
    }
    v189 = *(_QWORD *)((char *)v60 + 28);
    v190 = v166;
    if ( v189 && v189 < *(_QWORD *)((char *)v60 + 6) + (unsigned __int64)(unsigned int)v166 )
    {
      if ( byte_10316E8D7 || (qword_10317B120 & 1) != 0 )
      {
        v191 = *(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                         + SystemThread_TlsOffset
                         + 8LL);
        if ( v191 )
        {
          v192 = *(_QWORD *)(v191 + 96);
          if ( v192 )
          {
            if ( *(_BYTE *)(v192 + 1177) )
            {
              if ( byte_10316E7C7 || (qword_10317B120 & 2) != 0 )
                utassert_fail(1u, "false", "Sql\\Ntdbms\\storeng\\drs\\fixedvarrecord.cpp", 2114, 0);
              else
                ex_raise(34, 68, 21, 1018);
            }
          }
        }
      }
      RaiseInconsistencyError(*(_QWORD *)((char *)v60 + 6), 18);
      v190 = *(_DWORD *)((char *)v60 + 2);
    }
    if ( (unsigned int)(v190 - 1) > 0x3F3B )
    {
      if ( byte_10316E8D7 || (qword_10317B120 & 1) != 0 )
      {
        v193 = *(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                         + SystemThread_TlsOffset
                         + 8LL);
        if ( v193 )
        {
          v194 = *(_QWORD *)(v193 + 96);
          if ( v194 )
          {
            if ( *(_BYTE *)(v194 + 1177) )
            {
              if ( byte_10316E7C7 || (qword_10317B120 & 2) != 0 )
                utassert_fail(1u, "false", "Sql\\Ntdbms\\storeng\\drs\\fixedvarrecord.cpp", 2119, 0);
              else
                ex_raise(34, 68, 21, 1005);
            }
          }
        }
      }
      RaiseInconsistencyError(*(_QWORD *)((char *)v60 + 6), 5);
    }
LABEL_38:
    v73 = *(_DWORD *)((char *)v60 + 2);
    if ( v73 >= 9 )
      goto LABEL_39;
    v197 = **(_BYTE **)((char *)v60 + 6) & 0xE;
    if ( v197 )
    {
      v198 = v197 == 12;
      goto LABEL_360;
    }
    goto LABEL_361;
  }
  v73 = *(_DWORD *)((char *)v60 + 2);
  if ( !v73 )
  {
    CDRecord::Resize(v60);
    v73 = *(_DWORD *)((char *)v60 + 2);
  }
  if ( v73 < 9 )
  {
    v199 = *(_BYTE **)((char *)v60 + 6);
    if ( (*v199 & 0x1C) != 0 )
    {
      v198 = (*v199 & 0x1C) == 12;
LABEL_360:
      if ( !v198 )
        goto LABEL_39;
    }
LABEL_361:
    v73 = 9;
  }
LABEL_39:
  *v455 = v73;
  *v464 = 0;
  v74 = 0xFFFFFFFFFFFFFF0LL;
  v75 = SEDefaultMax;
  if ( !SEDefaultMax )
    goto LABEL_49;
  _mm_lfence();
  v76 = 32LL * SEDefaultMax;
  v77 = v76 + 15;
  if ( v76 + 15 < v76 )
    v77 = 0xFFFFFFFFFFFFFF0LL;
  v78 = v77 & 0xFFFFFFFFFFFFFFF0uLL;
  v79 = alloca(v78);
  v80 = alloca(v78);
  v442 = (struct VariableColumnSlot *)&v436;
  memset_0(&v436, 0, 32 * SEDefaultMax);
  if ( !*v58 )
  {
    v81 = 0;
    if ( *((_DWORD *)v58 + 1) )
    {
LABEL_44:
      v82 = (unsigned __int16)v58[14];
      if ( v82 >= v75 )
        v82 = v75;
      if ( v82 )
      {
        _mm_lfence();
        v116 = *((unsigned int *)v58 + 5) + 2LL;
        v117 = *((_DWORD *)v58 + 6);
        LODWORD(v460) = 0;
        HIDWORD(v460) = __PAIR32__(HIWORD(v460), 0) & 0xFFE00000;
        v461 = 0;
        v118 = (unsigned __int16 *)(*((_QWORD *)v58 + 1) + v116);
        v119 = (char *)v442 + 12;
        v120 = v460;
        do
        {
          v121 = *v118;
          v122 = *v118 >> 15;
          *(_QWORD *)(v119 - 12) = *((_QWORD *)v58 + 1) + v117;
          *((_DWORD *)v119 - 1) = (v121 & 0x7FFF) - v117;
          *(_OWORD *)(v119 + 4) = v120;
          *(_DWORD *)v119 = *(_DWORD *)v119 & 0xFFFFFFF0 | v122 & 1;
          v117 = *v118 & 0x7FFF;
          ++v81;
          v119 += 32;
          ++v118;
        }
        while ( v81 < v82 );
      }
      memset_0((char *)v442 + 32 * v82, 0, 32 * (v75 - v82));
      goto LABEL_48;
    }
    v58[1] = 0;
    v200 = *((unsigned int *)v58 + 4);
    *((_DWORD *)v58 + 5) = v200;
    v201 = (char *)*((_QWORD *)v58 + 1);
    v202 = *v201;
    if ( (*v201 & 0x10) != 0 )
    {
      LODWORD(v200) = (((unsigned int)*(unsigned __int16 *)&v201[v200] + 7) >> 3) + v200 + 2;
      *((_DWORD *)v58 + 5) = v200;
      v202 = *v201;
    }
    if ( (v202 & 0x20) == 0 )
    {
      *((_DWORD *)v58 + 1) = v200;
      v58[14] = 0;
      *((_DWORD *)v58 + 6) = v200;
      goto LABEL_413;
    }
    v203 = (unsigned __int16 *)&v201[(unsigned int)v200];
    v204 = *v203;
    v58[14] = *v203;
    if ( !v204 )
    {
      if ( byte_10316E8D7 || (qword_10317B120 & 1) != 0 )
      {
        v205 = *(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                         + SystemThread_TlsOffset
                         + 8LL);
        if ( v205 )
        {
          v206 = *(_QWORD *)(v205 + 96);
          if ( v206 )
          {
            if ( *(_BYTE *)(v206 + 1177) )
            {
              if ( byte_10316E7C7 || (qword_10317B120 & 2) != 0 )
                utassert_fail(1u, "false", "Sql\\Ntdbms\\storeng\\drs\\fixedvarrecord.cpp", 2010, 0);
              else
                ex_raise(34, 68, 21, 1003);
            }
          }
        }
      }
      RaiseInconsistencyError(*((_QWORD *)v58 + 1), 3);
      v204 = v58[14];
      LODWORD(v200) = *((_DWORD *)v58 + 5);
    }
    v207 = v200 + 2 * (v204 + 1);
    *((_DWORD *)v58 + 6) = v207;
    if ( v207 > 0x1F9E )
    {
      if ( byte_10316E8D7 || (qword_10317B120 & 1) != 0 )
      {
        v208 = *(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                         + SystemThread_TlsOffset
                         + 8LL);
        if ( v208 )
        {
          v209 = *(_QWORD *)(v208 + 96);
          if ( v209 )
          {
            if ( *(_BYTE *)(v209 + 1177) )
            {
              if ( byte_10316E7C7 || (qword_10317B120 & 2) != 0 )
                utassert_fail(1u, "false", "Sql\\Ntdbms\\storeng\\drs\\fixedvarrecord.cpp", 2017, 0);
              else
                ex_raise(34, 68, 21, 1004);
            }
          }
        }
      }
      RaiseInconsistencyError(*((_QWORD *)v58 + 1), 4);
      v204 = v58[14];
      v207 = *((_DWORD *)v58 + 6);
    }
    v210 = v203[v204] & 0x7FFF;
    *((_DWORD *)v58 + 1) = v210;
    if ( v207 > v210 )
    {
      if ( byte_10316E8D7 || (qword_10317B120 & 1) != 0 )
      {
        v211 = *(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                         + SystemThread_TlsOffset
                         + 8LL);
        if ( v211 )
        {
          v212 = *(_QWORD *)(v211 + 96);
          if ( v212 )
          {
            if ( *(_BYTE *)(v212 + 1177) )
            {
              if ( byte_10316E7C7 || (qword_10317B120 & 2) != 0 )
                utassert_fail(1u, "false", "Sql\\Ntdbms\\storeng\\drs\\fixedvarrecord.cpp", 2024, 0);
              else
                ex_raise(34, 68, 21, 1004);
            }
          }
        }
      }
      RaiseInconsistencyError(*((_QWORD *)v58 + 1), 4);
      v204 = v58[14];
    }
    if ( (v203[v204] & 0x8000u) == 0 )
    {
LABEL_413:
      _mm_lfence();
      if ( (**((_BYTE **)v58 + 1) & 0x40) != 0 )
      {
        _mm_lfence();
        v219 = *((_DWORD *)v58 + 1);
        *(_DWORD *)(v58 + 19) = v219;
        *((_DWORD *)v58 + 1) = v219 + 14;
        v220 = FixedVarRecord::FindVersioningInfo((FixedVarRecord *)(v58 + 1));
        v221 = HIDWORD(*(_QWORD *)v220);
        v222 = HIWORD(*(_QWORD *)v220);
        v223 = 0;
        if ( (((__int16)v222 ^ ((unsigned int)(__int16)v222 >> 1)) & 0x2000) != 0 )
        {
          v224 = v222 & 0xDFFF;
          if ( (v222 & 0x4000) != 0 )
            v224 = v222 | 0x2000;
          LOWORD(v222) = v224;
        }
        if ( (_WORD)v222 == 0xFFFC )
          v223 = (unsigned __int16)v221 >> 5;
        *((_DWORD *)v58 + 1) += v223;
      }
      else
      {
        *(_DWORD *)(v58 + 19) = 0;
      }
      v225 = *(_QWORD *)(v58 + 15);
      if ( v225 && v225 < *((_QWORD *)v58 + 1) + (unsigned __int64)*((unsigned int *)v58 + 1) )
      {
        _mm_lfence();
        if ( byte_10316E8D7 || (qword_10317B120 & 1) != 0 )
        {
          v226 = *(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                           + SystemThread_TlsOffset
                           + 8LL);
          if ( v226 )
          {
            v227 = *(_QWORD *)(v226 + 96);
            if ( v227 )
            {
              if ( *(_BYTE *)(v227 + 1177) )
              {
                if ( byte_10316E7C7 || (qword_10317B120 & 2) != 0 )
                  utassert_fail(1u, "false", "Sql\\Ntdbms\\storeng\\drs\\fixedvarrecord.cpp", 2114, 0);
                else
                  ex_raise(34, 68, 21, 1018);
              }
            }
          }
        }
        RaiseInconsistencyError(*((_QWORD *)v58 + 1), 18);
      }
      if ( (unsigned int)(*((_DWORD *)v58 + 1) - 1) <= 0x3F3B )
        goto LABEL_44;
      _mm_lfence();
      if ( byte_10316E8D7 || (qword_10317B120 & 1) != 0 )
      {
        v228 = *(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                         + SystemThread_TlsOffset
                         + 8LL);
        if ( v228 )
        {
          v229 = *(_QWORD *)(v228 + 96);
          if ( v229 )
          {
            if ( *(_BYTE *)(v229 + 1177) )
            {
              if ( !byte_10316E7C7 && (qword_10317B120 & 2) == 0 )
              {
                ex_raise(34, 68, 21, 1005);
                RaiseInconsistencyError(*((_QWORD *)v58 + 1), 5);
                goto LABEL_44;
              }
              utassert_fail(1u, "false", "Sql\\Ntdbms\\storeng\\drs\\fixedvarrecord.cpp", 2119, 0);
            }
          }
        }
      }
      RaiseInconsistencyError(*((_QWORD *)v58 + 1), 5);
      goto LABEL_44;
    }
    v213 = *((_QWORD *)v58 + 1);
    while ( 1 )
    {
      v214 = v213 + *((unsigned int *)v58 + 5);
      if ( v204 == 1 )
      {
        v215 = *((_DWORD *)v58 + 6);
        v216 = v215;
        v217 = *(_WORD *)(v214 + 2LL * v204) & 0x7FFF;
      }
      else
      {
        v215 = *(_WORD *)(v214 + 2LL * v204 - 2) & 0x7FFF;
        v216 = *((_DWORD *)v58 + 6);
        v217 = *(_WORD *)(v214 + 2LL * v204) & 0x7FFF;
        if ( v215 < v216 )
        {
LABEL_405:
          RaiseInconsistencyError(v213, 7);
          v216 = *((_DWORD *)v58 + 6);
          v204 = v58[14];
          goto LABEL_406;
        }
      }
      if ( v217 < v215 )
        goto LABEL_405;
LABEL_406:
      if ( v215 < v216 || v215 > *((_DWORD *)v58 + 1) )
      {
        v81 = 0;
        goto LABEL_44;
      }
      v213 = *((_QWORD *)v58 + 1);
      v218 = *(_WORD *)(v213 + v215);
      if ( v218 == 5 )
      {
        _mm_lfence();
        v58[1] |= 2u;
        --v58[14];
        v58[21] = v215;
        v230 = *((_QWORD *)v58 + 1) + (unsigned __int16)v215;
        v231 = v58[22] & 0xC7FF;
        if ( (*(_WORD *)(v230 + 2) & 0x4000) != 0 )
          v231 |= *(_WORD *)(v230 + 2) & 0x3800;
        v58[22] = v231;
        v58[22] = v231 ^ (*(_WORD *)(v230 + 2) ^ v231) & 0x7FF;
        v81 = 0;
        goto LABEL_413;
      }
      if ( v218 >= 0x400u )
      {
        v58[1] |= 1u;
        v58[14] = --v204;
        if ( v204 )
        {
          if ( (v203[v204] & 0x8000u) != 0 )
            continue;
        }
      }
      v81 = 0;
      goto LABEL_413;
    }
  }
  _mm_lfence();
  CDRecord::GetShortAndLongDataForVCS((CDRecord *)(v58 + 1), (struct VariableColumnSlot *const)&v436, v75);
LABEL_48:
  v74 = 0xFFFFFFFFFFFFFF0LL;
LABEL_49:
  v83 = v436;
  if ( !v436 )
    goto LABEL_50;
  _mm_lfence();
  v232 = 32LL * v436;
  v233 = v232 + 15;
  if ( v232 + 15 < v232 )
    v233 = 0xFFFFFFFFFFFFFF0LL;
  v234 = v233 & 0xFFFFFFFFFFFFFFF0uLL;
  v235 = alloca(v234);
  v236 = alloca(v234);
  v237 = (struct VariableColumnSlot *)&v436;
  v448 = (struct VariableColumnSlot *)&v436;
  memset_0(&v436, 0, 32 * v436);
  if ( !*(_DWORD *)(v47 + 1) )
  {
    *v47 = 0;
    v238 = *(unsigned int *)(v47 + 7);
    *(_DWORD *)(v47 + 9) = v238;
    v239 = *(char **)(v47 + 3);
    v240 = *v239;
    if ( (*v239 & 0x10) != 0 )
    {
      LODWORD(v238) = (((unsigned int)*(unsigned __int16 *)&v239[v238] + 7) >> 3) + v238 + 2;
      *(_DWORD *)(v47 + 9) = v238;
      v240 = *v239;
    }
    if ( (v240 & 0x20) != 0 )
    {
      v241 = (unsigned __int16 *)&v239[(unsigned int)v238];
      v242 = *v241;
      v47[13] = *v241;
      if ( v242 )
      {
        v245 = v454;
      }
      else
      {
        if ( byte_10316E8D7 || (qword_10317B120 & 1) != 0 )
        {
          v243 = *(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                           + SystemThread_TlsOffset
                           + 8LL);
          if ( v243 )
          {
            v244 = *(_QWORD *)(v243 + 96);
            if ( v244 )
            {
              if ( *(_BYTE *)(v244 + 1177) )
              {
                if ( byte_10316E7C7 || (qword_10317B120 & 2) != 0 )
                  utassert_fail(1u, "false", "Sql\\Ntdbms\\storeng\\drs\\fixedvarrecord.cpp", 2010, 0);
                else
                  ex_raise(34, 68, 21, 1003);
              }
            }
          }
        }
        RaiseInconsistencyError(*(_QWORD *)(v47 + 3), 3);
        v242 = v47[13];
        v245 = v454;
        LODWORD(v238) = *((_DWORD *)v454 + 5);
      }
      v246 = v238 + 2 * (v242 + 1);
      *(_DWORD *)(v47 + 11) = v246;
      if ( v246 > 0x1F9E )
      {
        if ( byte_10316E8D7 || (qword_10317B120 & 1) != 0 )
        {
          v247 = *(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                           + SystemThread_TlsOffset
                           + 8LL);
          if ( v247 )
          {
            v248 = *(_QWORD *)(v247 + 96);
            if ( v248 )
            {
              if ( *(_BYTE *)(v248 + 1177) )
              {
                if ( byte_10316E7C7 || (qword_10317B120 & 2) != 0 )
                  utassert_fail(1u, "false", "Sql\\Ntdbms\\storeng\\drs\\fixedvarrecord.cpp", 2017, 0);
                else
                  ex_raise(34, 68, 21, 1004);
              }
            }
          }
        }
        RaiseInconsistencyError(*(_QWORD *)(v47 + 3), 4);
        v242 = *((_WORD *)v245 + 14);
        v246 = *((_DWORD *)v245 + 6);
      }
      v249 = v241[v242] & 0x7FFF;
      *(_DWORD *)(v47 + 1) = v249;
      if ( v246 > v249 )
      {
        if ( byte_10316E8D7 || (qword_10317B120 & 1) != 0 )
        {
          v250 = *(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                           + SystemThread_TlsOffset
                           + 8LL);
          if ( v250 )
          {
            v251 = *(_QWORD *)(v250 + 96);
            if ( v251 )
            {
              if ( *(_BYTE *)(v251 + 1177) )
              {
                if ( byte_10316E7C7 || (qword_10317B120 & 2) != 0 )
                  utassert_fail(1u, "false", "Sql\\Ntdbms\\storeng\\drs\\fixedvarrecord.cpp", 2024, 0);
                else
                  ex_raise(34, 68, 21, 1004);
              }
            }
          }
        }
        RaiseInconsistencyError(*(_QWORD *)(v47 + 3), 4);
        v242 = *((_WORD *)v245 + 14);
      }
      if ( (v241[v242] & 0x8000u) != 0 )
      {
        v252 = *(char **)(v47 + 3);
        while ( 1 )
        {
          v253 = &v252[*(unsigned int *)(v47 + 9)];
          if ( v242 == 1 )
          {
            v254 = *(_DWORD *)(v47 + 11);
            v255 = v254;
            v256 = *(_WORD *)&v253[2 * v242] & 0x7FFF;
          }
          else
          {
            v254 = *(_WORD *)&v253[2 * v242 - 2] & 0x7FFF;
            v255 = *((_DWORD *)v245 + 6);
            v256 = *(_WORD *)&v253[2 * v242] & 0x7FFF;
            if ( v254 < v255 )
            {
LABEL_497:
              RaiseInconsistencyError(v252, 7);
              v255 = *((_DWORD *)v245 + 6);
              goto LABEL_498;
            }
          }
          if ( v256 < v254 )
            goto LABEL_497;
LABEL_498:
          if ( v254 < v255 || v254 > *(_DWORD *)(v47 + 1) )
            goto LABEL_534;
          v252 = *(char **)(v47 + 3);
          v257 = *(_WORD *)&v252[v254];
          if ( v257 == 5 )
          {
            *v47 |= 2u;
            --v47[13];
            v47[20] = v254;
            v293 = *(_QWORD *)(v47 + 3) + (unsigned __int16)v254;
            v294 = v47[21] & 0xC7FF;
            if ( _bittest16((const signed __int16 *)(v293 + 2), 0xEu) )
              v294 |= *(_WORD *)(v293 + 2) & 0x3800;
            v47[21] = v294;
            v47[21] = v294 ^ (*(_WORD *)(v293 + 2) ^ v294) & 0x7FF;
            break;
          }
          if ( v257 < 0x400u )
            break;
          *v47 |= 1u;
          v258 = v47[13] - 1;
          v47[13] = v258;
          if ( !v258 )
            break;
          v242 = v258;
          if ( (v241[v258] & 0x8000u) == 0 )
          {
            LODWORD(v238) = *((_DWORD *)v245 + 1);
            v239 = v252;
            goto LABEL_505;
          }
        }
      }
      LODWORD(v238) = *((_DWORD *)v245 + 1);
      v239 = *(char **)(v47 + 3);
    }
    else
    {
      *(_DWORD *)(v47 + 1) = v238;
      v47[13] = 0;
      *(_DWORD *)(v47 + 11) = v238;
      v245 = v454;
    }
LABEL_505:
    if ( (*v239 & 0x40) != 0 )
    {
      v259 = *(_DWORD *)(v47 + 1);
      *((_DWORD *)v47 + 9) = v259;
      *(_DWORD *)(v47 + 1) = v259 + 14;
      v260 = FixedVarRecord::FindVersioningInfo((FixedVarRecord *)v47);
      v261 = HIDWORD(*(_QWORD *)v260);
      v262 = HIWORD(*(_QWORD *)v260);
      v263 = 0;
      if ( (((__int16)v262 ^ ((unsigned int)(__int16)v262 >> 1)) & 0x2000) != 0 )
      {
        v264 = v262 & 0xDFFF;
        if ( (v262 & 0x4000) != 0 )
          v264 = v262 | 0x2000;
        LOWORD(v262) = v264;
      }
      if ( (_WORD)v262 == 0xFFFC )
        v263 = (unsigned __int16)v261 >> 5;
      *(_DWORD *)(v47 + 1) += v263;
      LODWORD(v238) = *(_DWORD *)(v47 + 1);
    }
    else
    {
      *((_DWORD *)v47 + 9) = 0;
    }
    v265 = *(_QWORD *)(v47 + 14);
    v266 = v238;
    if ( v265 && v265 < *(_QWORD *)(v47 + 3) + (unsigned __int64)(unsigned int)v238 )
    {
      if ( byte_10316E8D7 || (qword_10317B120 & 1) != 0 )
      {
        v267 = *(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                         + SystemThread_TlsOffset
                         + 8LL);
        if ( v267 )
        {
          v268 = *(_QWORD *)(v267 + 96);
          if ( v268 )
          {
            if ( *(_BYTE *)(v268 + 1177) )
            {
              if ( byte_10316E7C7 || (qword_10317B120 & 2) != 0 )
                utassert_fail(1u, "false", "Sql\\Ntdbms\\storeng\\drs\\fixedvarrecord.cpp", 2114, 0);
              else
                ex_raise(34, 68, 21, 1018);
            }
          }
        }
      }
      RaiseInconsistencyError(*(_QWORD *)(v47 + 3), 18);
      v266 = *((_DWORD *)v245 + 1);
    }
    if ( (unsigned int)(v266 - 1) > 0x3F3B )
    {
      if ( byte_10316E8D7 || (qword_10317B120 & 1) != 0 )
      {
        v269 = *(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                         + SystemThread_TlsOffset
                         + 8LL);
        if ( v269 )
        {
          v270 = *(_QWORD *)(v269 + 96);
          if ( v270 )
          {
            if ( *(_BYTE *)(v270 + 1177) )
            {
              if ( byte_10316E7C7 || (qword_10317B120 & 2) != 0 )
                utassert_fail(1u, "false", "Sql\\Ntdbms\\storeng\\drs\\fixedvarrecord.cpp", 2119, 0);
              else
                ex_raise(34, 68, 21, 1005);
            }
          }
        }
      }
      RaiseInconsistencyError(*(_QWORD *)(v47 + 3), 5);
    }
LABEL_534:
    v83 = v436;
  }
  if ( (unsigned int)FixedVarRecord::HasSparseVector((FixedVarRecord *)v47) )
  {
    v271 = v83;
    if ( (v47[21] & 0x7FFu) < v83 )
      v271 = v47[21] & 0x7FF;
    v457 = v271;
    if ( v271 > 0 )
    {
      _mm_lfence();
      v272 = v47[20];
      v273 = *(_QWORD *)(v47 + 3);
      v469 = v272 + v273;
      v274 = v47[21];
      v275 = (v274 >> 11) & 7;
      v276 = (unsigned int)(2 * v275);
      v277 = v276 + v272 + v273 + 4;
      v460 = v277;
      v278 = 2 * (v274 & 0x7FF);
      v279 = v273 + v272 + v278 + v276 + 4;
      v280 = (unsigned __int16 *)(v272 + v273 + 4);
      v466 = v280;
      v458 = 2 * (v278 + v275) + 4;
      v281 = 0;
      v282 = v271;
      v283 = 0;
      do
      {
        v74 = v47[21];
        if ( (v74 & 0x3800) != 0 )
        {
          v74 = *v280;
          v284 = *v280;
        }
        else
        {
          v284 = *(_WORD *)(v47[20] + *(_QWORD *)(v47 + 3) + 2LL);
        }
        v285 = (v284 >> 11) & 7;
        v286 = (v74 & 0x7FF) - 1;
        if ( v283 <= v286 )
        {
          v287 = (__int16 *)(v279 + 2 * v283);
          v288 = (char *)v448 + 32 * v283 + 12;
          v289 = v277 - v279;
          v290 = WORD3(v467);
          do
          {
            if ( v283 >= v282 )
              break;
            LODWORD(v467) = (*(unsigned __int16 *)((char *)v287 + v289) + (v285 << 16)) | 0x80000000;
            WORD2(v467) = 0;
            v290 &= 0xFFF0u;
            WORD3(v467) = v290;
            v291 = *v287;
            v292 = *(unsigned __int16 *)(v279 + 2LL * v281) >> 15;
            *(_QWORD *)(v288 - 12) = v469 + (unsigned int)v458;
            *((_DWORD *)v288 - 1) = (v291 & 0x7FFF) - v458;
            *(_OWORD *)(v288 + 4) = v467;
            v74 = *(_DWORD *)v288 & 0xFFFFFFF0 | v292 & 1;
            *(_DWORD *)v288 = v74;
            LODWORD(v458) = *v287 & 0x7FFF;
            ++v281;
            ++v283;
            v288 += 32;
            ++v287;
          }
          while ( v283 <= v286 );
          v47 = v470;
          v280 = v466;
          v277 = v460;
        }
        v466 = ++v280;
      }
      while ( v283 < v282 );
      v271 = v457;
      v60 = v443;
      v83 = v436;
      v237 = v448;
    }
    if ( v271 < (int)v83 )
      memset_0((char *)v237 + 32 * v271, 0, 32LL * (v83 - v271));
  }
LABEL_50:
  v84 = SEDefaultMax;
  if ( (SEDefaultMax || v452) && v456 )
    memset_0(*(void **)v456, 0, *((unsigned int *)v456 + 2));
  v85 = v442;
  if ( a22 )
  {
    v435 = (unsigned int *)v471;
    v434 = v472;
    v295 = v459;
    RemoveDroppedValues(*((const struct HoBtAccess **)v459 + 3), v442, v84, v441, v472, v471);
    v296 = *((_QWORD *)v295 + 3);
    if ( v438 )
    {
      _mm_lfence();
      v297 = (unsigned int *)((char *)v448 + 12);
      v298 = v438;
      v299 = v473;
      v300 = v474;
      do
      {
        v301 = v297[1];
        HoBtColumnAttributeByHoBtColumnId = 0;
        if ( v301 < 0 )
        {
          _mm_lfence();
          if ( (v301 & 0xC0000000) == 0x80000000 )
            HoBtColumnAttributeByHoBtColumnId = HoBtColumnAttributeCacheShareable::GetHoBtColumnAttributeByHoBtColumnId(
                                                  **(HoBtColumnAttributeCacheShareable ***)(*(_QWORD *)(v296 + 8) + 352LL),
                                                  v301 & 0x1FFFFFFF);
          else
            HoBtColumnAttributeByHoBtColumnId = HoBtColumnAttributeCache::GetHoBtColumnAttributeByOffset(
                                                  *(HoBtColumnAttributeCache **)(*(_QWORD *)(v296 + 8) + 352LL),
                                                  v301);
        }
        if ( (*((_BYTE *)HoBtColumnAttributeByHoBtColumnId + 32) & 0x10) != 0 )
        {
          v303 = *v297;
          if ( (*v297 & 1) != 0 && *(v297 - 1) )
          {
            v300[(*v299)++] = v301 & 0x1FFFFFFF;
            v303 = *v297;
          }
          *(v297 - 1) = 0;
          *v297 = v303 & 0xFFFFFFFC | 2;
        }
        v297 += 8;
        --v298;
      }
      while ( v298 );
      v60 = v443;
      v85 = v442;
    }
  }
  v86 = v449;
  v87 = 0;
  *v449 = 0;
  v88 = v462;
  v89 = v441;
  if ( v462 )
  {
    v304 = v454;
    v305 = v450;
    ShortRecord::SetSEDefaultValues<Record>(v462, v450, v454, v441, v85, (_DWORD)v435);
    if ( v84 )
    {
      v306 = v475;
      if ( v475 )
      {
        if ( v305 )
        {
          v307 = v305;
          do
          {
            v308 = *v88;
            v309 = **v88;
            if ( v309 < 0 )
            {
              v310 = ~v309;
              if ( v310 < (int)v84 && (*((_BYTE *)v85 + 32 * v310 + 12) & 8) != 0 )
              {
                ++*((_DWORD *)v306 + 3);
                if ( *(_WORD *)v304 )
                  v74 = *((unsigned __int16 *)v308 + 2);
                else
                  v74 = (unsigned int)-*v308;
                v311 = *((_DWORD *)v306 + 4);
                if ( v311 <= (int)v74 )
                {
                  if ( *(_WORD *)v304 )
                    v311 = *((unsigned __int16 *)v308 + 2);
                  else
                    v311 = -*v308;
                }
                *((_DWORD *)v306 + 4) = v311;
              }
            }
            ++v88;
            --v307;
          }
          while ( v307 );
        }
      }
    }
    v87 = 0;
    v86 = v449;
  }
  v90 = 0;
  v436 = 0;
  v91 = 0x8000;
  if ( (_DWORD)v440 )
  {
    v92 = (unsigned int *)((char *)v476 + 56);
    v93 = (unsigned int)v440;
    v440 = (unsigned int)v440;
    LODWORD(v94) = v440;
    while ( 1 )
    {
      if ( !*((_BYTE *)v92 + 8) )
        goto LABEL_90;
      v95 = *(v92 - 14);
      if ( v95 > 0 )
        break;
      if ( v95 >= 0 || (*(_WORD *)(*((_QWORD *)v92 + 2) + 12LL) & 0x400) != 0 )
      {
        v327 = (unsigned int *)(*((_QWORD *)v463 + 1) + ((unsigned __int64)v90 << 6));
        v328 = 0;
        if ( v438 )
        {
          v74 = v438 - 1;
          v329 = v327[12] & 0x1FFFFFFF;
          v330 = 0;
          LODWORD(v94) = (int)(v438 - 1) >> 1;
          v331 = v448;
          v332 = *((_DWORD *)v448 + 8 * (int)v94 + 4) & 0x1FFFFFFF;
          if ( v329 == v332 )
          {
LABEL_652:
            v328 = 1;
          }
          else
          {
            while ( 1 )
            {
              if ( v329 <= v332 )
                v74 = (unsigned int)(v94 - 1);
              v333 = v94 + 1;
              if ( v329 <= v332 )
                v333 = v330;
              if ( v333 > (int)v74 )
                break;
              v330 = v333;
              LODWORD(v94) = ((int)v74 + v333) >> 1;
              v332 = *((_DWORD *)v448 + 8 * (int)v94 + 4) & 0x1FFFFFFF;
              if ( v329 == v332 )
                goto LABEL_652;
            }
          }
          v93 = v440;
        }
        else
        {
          v331 = v448;
        }
        v334 = v445;
        if ( v328 )
          v334 = v94;
        v94 = v334;
        v335 = v445 + 1;
        if ( v328 )
          v335 = v445;
        v445 = v335;
        v336 = (char *)v331 + 32 * v94;
        if ( (v336[12] & 1) != 0 && *((_DWORD *)v336 + 2) )
        {
          v337 = (_BYTE *)(*(_QWORD *)v456 + ((unsigned __int64)*v327 >> 3));
          v74 = *v327 & 7;
          *v337 |= 1 << (*(_BYTE *)v327 & 7);
          *v449 = 1;
        }
        *(_OWORD *)v336 = *((_OWORD *)v327 + 2);
        *((_OWORD *)v336 + 1) = *((_OWORD *)v327 + 3);
        *((_DWORD *)v336 + 3) ^= (*((_DWORD *)v336 + 3) ^ (2 * *((unsigned __int8 *)v327 + 24))) & 2;
        v436 = ++v90;
        v87 = 0;
        goto LABEL_89;
      }
      v109 = (unsigned int *)(*((_QWORD *)v463 + 1) + ((unsigned __int64)v90 << 6));
      v110 = ~v109[2];
      if ( *((_WORD *)v109 + 6) && *((unsigned __int16 *)v109 + 6) <= v444 )
      {
        v111 = *(_WORD *)v89;
        if ( (v109[6] & 1) != 0 )
        {
          v114 = (const struct PhysicalColumnAttribute *)(v109 + 2);
          if ( v111 )
            CDRecord::SetNull(v60, v114);
          else
            FixedVarRecord::SetNull(v60, v114, 0, 0);
          v115 = (char *)v442 + 32 * v110;
          if ( (v115[12] & 1) != 0 && *((_DWORD *)v115 + 2) )
          {
            v322 = (_BYTE *)(*(_QWORD *)v456 + ((unsigned __int64)*v109 >> 3));
            v74 = *v109 & 7;
            *v322 |= 1 << (*(_BYTE *)v109 & 7);
            *v449 = 1;
          }
          *(_OWORD *)v115 = *((_OWORD *)v109 + 2);
          *((_OWORD *)v115 + 1) = *((_OWORD *)v109 + 3);
          *((_DWORD *)v115 + 3) |= 2u;
          v436 = ++v90;
          v87 = 0;
          goto LABEL_88;
        }
        v112 = *((unsigned __int16 *)v109 + 6);
        if ( v111 )
        {
          if ( (unsigned __int16)v112 <= *(_WORD *)v60 )
          {
            v323 = (_BYTE *)(*(_QWORD *)((char *)v60 + 6) + *((unsigned __int16 *)v60 + 11) + (__int64)((v112 - 1) / 2));
            v74 = (unsigned __int8)*v323;
            v324 = (unsigned __int8)v74 >> 4;
            v325 = v109[3] & 1;
            if ( v325 )
              v324 = *v323 & 0xF;
            if ( !v324 )
            {
              if ( v325 )
              {
                LOBYTE(v74) = v74 & 0xF0 | 1;
                *v323 = v74;
              }
              else
              {
                *v323 = *v323 & 0xF | 0x10;
              }
            }
          }
        }
        else
        {
          v74 = *((_QWORD *)v89 + 1) + *((int *)v89 + 4);
          *(_BYTE *)(v74 + ((unsigned __int64)(unsigned int)(v112 - 1) >> 3) + 2) &= ~(1 << ((v112 - 1) & 7));
        }
      }
      v113 = (char *)v442 + 32 * v110;
      if ( (v113[12] & 1) != 0 && *((_DWORD *)v113 + 2) )
      {
        v326 = (_BYTE *)(*(_QWORD *)v456 + ((unsigned __int64)*v109 >> 3));
        v74 = *v109 & 7;
        *v326 |= 1 << (*(_BYTE *)v109 & 7);
        *v86 = 1;
      }
      v447 = v447 || *((_DWORD *)v113 + 2) < v109[10];
      *(_OWORD *)v113 = *((_OWORD *)v109 + 2);
      *((_OWORD *)v113 + 1) = *((_OWORD *)v109 + 3);
      v436 = ++v90;
      v87 = 0;
LABEL_88:
      v93 = v440;
LABEL_89:
      v91 = 0x8000;
LABEL_90:
      v92 += 20;
      v440 = --v93;
      v89 = v441;
      v86 = v449;
      if ( !v93 )
      {
        v84 = SEDefaultMax;
        goto LABEL_105;
      }
      v60 = v443;
    }
    v74 = v92[2];
    if ( (v74 & 0x400) != 0 )
    {
      if ( (*(_BYTE *)(*((_QWORD *)v92 + 2) + 42LL) & 0x10) != 0 )
        v96 = *((_QWORD *)v451 + 4);
      else
        v96 = *((_QWORD *)v451 + 3);
      v97 = *(_BYTE *)(v96 + *((_QWORD *)v92 - 1));
      if ( v97 == 3 )
      {
        v100 = 0;
        v102 = 0;
LABEL_73:
        v103 = *((unsigned __int16 *)v92 - 26);
        if ( *((_WORD *)v92 - 26) && v103 <= v444 )
        {
          v104 = *(_WORD *)v89;
          if ( v97 == 3 )
          {
            v312 = (const struct PhysicalColumnAttribute *)(v92 - 14);
            if ( v104 )
              CDRecord::SetNull(v443, v312);
            else
              FixedVarRecord::SetNull(v443, v312, 0, 0);
          }
          else if ( v104 )
          {
            if ( (unsigned __int16)v103 <= *(_WORD *)v443 )
            {
              v313 = (_BYTE *)(*(_QWORD *)((char *)v443 + 6)
                             + *((unsigned __int16 *)v443 + 11)
                             + (__int64)((int)(v103 - 1) / 2));
              v74 = (unsigned __int8)*v313;
              v314 = (unsigned __int8)v74 >> 4;
              v315 = *(_WORD *)(v92 - 13) & 1;
              if ( v315 )
                v314 = *v313 & 0xF;
              if ( !v314 )
              {
                if ( v315 )
                {
                  LOBYTE(v74) = v74 & 0xF0 | 1;
                  *v313 = v74;
                }
                else
                {
                  *v313 = *v313 & 0xF | 0x10;
                }
              }
            }
          }
          else
          {
            v74 = *((_QWORD *)v89 + 1) + *((int *)v89 + 4);
            *(_BYTE *)(((unsigned __int64)(v103 - 1) >> 3) + v74 + 2) &= ~(1 << ((v103 - 1) & 7));
          }
        }
        if ( v102 )
        {
          if ( *((_BYTE *)v92 + 8) == 1 || *((_BYTE *)v92 + 8) == 2 )
          {
            v105 = *((unsigned __int16 *)v92 + 2);
            if ( v105 < v100 )
            {
              utassert_fail(
                1u,
                "pbind->MaxInRowLength () >= newColLen",
                "Sql\\Ntdbms\\storeng\\include\\longrec.inl",
                609,
                0);
              LOWORD(v105) = *((_WORD *)v92 + 2);
            }
            v106 = (unsigned __int16)v105 - v100;
            v107 = *(unsigned __int8 *)(*((_QWORD *)v92 + 2) + 36LL);
            v108 = *((_QWORD *)v441 + 1) + (int)*(v92 - 14);
            if ( v100 )
              memmove((void *)(*((_QWORD *)v441 + 1) + (int)*(v92 - 14)), v102, v100);
            if ( v106 )
              memset_0((void *)(v108 + v100), v107, v106);
            v87 = 0;
          }
          else if ( *((_BYTE *)v92 + 8) == 8 )
          {
            Record::SetColumn(
              v89,
              (const struct PhysicalColumnAttribute *)(v92 - 14),
              (const unsigned __int8 *)v102,
              1u);
          }
          else
          {
            utassert_fail(1u, "FALSE", "Sql\\Ntdbms\\storeng\\include\\longrec.inl", 632, "Invalid switch value");
          }
        }
        else if ( (v92[2] & 0x4000) == 0 )
        {
          ex_raise(6, 81, 16, 5);
        }
        v90 = v436;
        goto LABEL_88;
      }
    }
    else
    {
      v97 = 0;
    }
    if ( (v74 & 0x8000) != 0 && (*((_BYTE *)v451 + 20) & 8) != 0 )
    {
      v100 = *(_DWORD *)(*((_QWORD *)v451 + 7) + 8LL * *v92);
    }
    else
    {
      v98 = *((_QWORD *)v92 + 2);
      if ( (v74 & 0x100) != 0 )
      {
        if ( (*(_BYTE *)(v98 + 42) & 0x10) != 0 )
          v99 = *((_QWORD *)v451 + 4);
        else
          v99 = *((_QWORD *)v451 + 3);
        v100 = *(_DWORD *)(v99 + *(_QWORD *)(v98 + 24));
      }
      else
      {
        v100 = *(unsigned __int16 *)(v98 + 2);
      }
    }
    if ( (v74 & 0x48000) == 0x48000 && (*((_BYTE *)v451 + 20) & 8) != 0 )
    {
      v102 = *(_QWORD **)(*((_QWORD *)v451 + 8) + 8LL * *v92);
    }
    else
    {
      if ( (*(_BYTE *)(*((_QWORD *)v92 + 2) + 42LL) & 0x10) != 0 )
        v101 = *((_QWORD *)v451 + 4);
      else
        v101 = *((_QWORD *)v451 + 3);
      v102 = (_QWORD *)(v101 + *((_QWORD *)v92 - 2));
      if ( (v74 & 0x800) != 0 )
        v102 = (_QWORD *)*v102;
    }
    goto LABEL_73;
  }
LABEL_105:
  v29 = v477;
  if ( v477 && *((_DWORD *)v477 + 1) )
  {
    v316 = 0;
    v317 = 0;
    v318 = v438;
    v319 = v442;
    do
    {
      v74 = (unsigned __int64)v87 >> 3;
      v91 = *(unsigned __int8 *)(v74 + *(_QWORD *)a12);
      LOBYTE(v91) = (unsigned __int8)v91 >> (v87 & 7);
      if ( (v91 & 1) != 0 )
      {
        v320 = *((_QWORD *)v29 + 1) + ((unsigned __int64)v87 << 6);
        if ( (*(_DWORD *)(v320 + 8) & 0xC0000000) == 0x80000000 )
        {
          v91 = *(_DWORD *)(v320 + 48) & 0x1FFFFFFF;
          v338 = v448;
          v339 = (_DWORD *)((char *)v448 + 32 * v317 + 16);
          while ( 1 )
          {
            ++v316;
            v74 = v317 + 1;
            if ( (_DWORD)v91 == (*v339 & 0x1FFFFFFF) )
              break;
            ++v317;
            v339 += 8;
            if ( v316 >= v318 )
              goto LABEL_628;
          }
          v340 = 32 * v317;
          *(_OWORD *)((char *)v448 + v340) = *(_OWORD *)(v320 + 32);
          *(_OWORD *)((char *)v338 + v340 + 16) = *(_OWORD *)(v320 + 48);
          v317 = v74;
        }
        else
        {
          v321 = (char *)v319 - 32 * *(int *)(v320 + 8);
          *((_OWORD *)v321 - 2) = *(_OWORD *)(v320 + 32);
          *((_OWORD *)v321 - 1) = *(_OWORD *)(v320 + 48);
        }
      }
LABEL_628:
      ++v87;
    }
    while ( v87 < *((_DWORD *)v29 + 1) );
    v84 = SEDefaultMax;
  }
  v30 = v441;
  if ( !v84 )
    goto LABEL_119;
  _mm_lfence();
  if ( !*(_WORD *)v441 )
  {
    v31 = 0;
    v91 = (unsigned __int64)v442;
    while ( 1 )
    {
      v74 = v84--;
      if ( *((_DWORD *)v442 + 8 * v84 + 2) )
        break;
      if ( !v84 )
      {
        v437 = 1;
        goto LABEL_119;
      }
    }
    *((_WORD *)v441 + 14) = v74;
    v32 = *((_DWORD *)v30 + 5) + 2 + 2 * v74;
    *((_DWORD *)v30 + 6) = v32;
    *((_DWORD *)v30 + 1) = v32;
    **((_BYTE **)v30 + 1) |= 0x20u;
    if ( *((_DWORD *)v30 + 1) <= a19 )
    {
      v31 = (_WORD *)(*((_QWORD *)v30 + 1) + *((unsigned int *)v30 + 5));
      *v31 = v74;
    }
    v33 = v31 + 1;
    v34 = (_WORD *)(v91 + 12);
    v35 = v74;
    do
    {
      v36 = (void *)(*((_QWORD *)v30 + 1) + *((unsigned int *)v30 + 1));
      v91 = *((unsigned int *)v34 - 1);
      v74 = (unsigned int)(*((_DWORD *)v30 + 1) + v91);
      *((_DWORD *)v30 + 1) = v74;
      v37 = v74;
      if ( (unsigned int)v74 <= a19 && (unsigned int)v74 <= a18 )
      {
        *v33 = v74 & 0x7FFF | ((*v34 & 1) << 15);
        memcpy_s(v36, (unsigned int)v91, *(const void *const *)(v34 - 6), (unsigned int)v91);
        v37 = *((_DWORD *)v30 + 1);
      }
      ++v33;
      v34 += 16;
      --v35;
    }
    while ( v35 );
    *v455 = v37;
    v38 = *((_DWORD *)v30 + 1);
    if ( v38 > a19 || (v437 = 1, v38 > a18) )
      v437 = 0;
LABEL_119:
    inited = v437;
    v40 = v443;
    goto LABEL_120;
  }
  _mm_lfence();
  v397 = v84;
  v40 = v443;
  inited = CDRecord::InitVariable(v443, a18, a19, v397, v442, v455);
  v437 = inited;
LABEL_120:
  v41 = v445;
  if ( !v445 )
    goto LABEL_121;
  if ( !a26 )
  {
    _mm_lfence();
    v341 = (char *)v30 + 2;
    v342 = *((_DWORD *)v30 + 1);
    if ( v342 )
      goto LABEL_745;
    *(_WORD *)v341 = 0;
    v343 = *((unsigned int *)v30 + 4);
    *((_DWORD *)v30 + 5) = v343;
    v344 = (_BYTE *)*((_QWORD *)v30 + 1);
    v345 = *v344;
    v346 = v344;
    if ( (*v344 & 0x10) != 0 )
    {
      LODWORD(v343) = (((unsigned int)*(unsigned __int16 *)&v344[v343] + 7) >> 3) + v343 + 2;
      *((_DWORD *)v30 + 5) = v343;
      v345 = *v344;
    }
    if ( (v345 & 0x20) == 0 )
    {
      *((_DWORD *)v30 + 1) = v343;
      *((_WORD *)v30 + 14) = 0;
      *((_DWORD *)v30 + 6) = v343;
      goto LABEL_715;
    }
    v347 = (unsigned __int16 *)&v344[(unsigned int)v343];
    v348 = *v347;
    *((_WORD *)v30 + 14) = *v347;
    if ( !v348 )
    {
      if ( byte_10316E8D7 || (qword_10317B120 & 1) != 0 )
      {
        v349 = *(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                         + SystemThread_TlsOffset
                         + 8LL);
        if ( v349 )
        {
          v350 = *(_QWORD *)(v349 + 96);
          if ( v350 )
          {
            if ( *(_BYTE *)(v350 + 1177) )
            {
              if ( byte_10316E7C7 || (qword_10317B120 & 2) != 0 )
                utassert_fail(1u, "false", "Sql\\Ntdbms\\storeng\\drs\\fixedvarrecord.cpp", 2010, 0);
              else
                ex_raise(34, 68, 21, 1003);
            }
          }
        }
      }
      RaiseInconsistencyError(*((_QWORD *)v30 + 1), 3);
      v348 = *((_WORD *)v30 + 14);
      LODWORD(v343) = *((_DWORD *)v30 + 5);
    }
    v351 = v343 + 2 * (v348 + 1);
    *((_DWORD *)v30 + 6) = v351;
    if ( v351 > 0x1F9E )
    {
      if ( byte_10316E8D7 || (qword_10317B120 & 1) != 0 )
      {
        v352 = *(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                         + SystemThread_TlsOffset
                         + 8LL);
        if ( v352 )
        {
          v353 = *(_QWORD *)(v352 + 96);
          if ( v353 )
          {
            if ( *(_BYTE *)(v353 + 1177) )
            {
              if ( byte_10316E7C7 || (qword_10317B120 & 2) != 0 )
                utassert_fail(1u, "false", "Sql\\Ntdbms\\storeng\\drs\\fixedvarrecord.cpp", 2017, 0);
              else
                ex_raise(34, 68, 21, 1004);
            }
          }
        }
      }
      RaiseInconsistencyError(*((_QWORD *)v30 + 1), 4);
      v348 = *((_WORD *)v30 + 14);
      v351 = *((_DWORD *)v30 + 6);
    }
    v342 = v347[v348] & 0x7FFF;
    *((_DWORD *)v30 + 1) = v342;
    if ( v351 > v342 )
    {
      if ( byte_10316E8D7 || (qword_10317B120 & 1) != 0 )
      {
        v354 = *(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                         + SystemThread_TlsOffset
                         + 8LL);
        if ( v354 )
        {
          v355 = *(_QWORD *)(v354 + 96);
          if ( v355 )
          {
            if ( *(_BYTE *)(v355 + 1177) )
            {
              if ( byte_10316E7C7 || (qword_10317B120 & 2) != 0 )
                utassert_fail(1u, "false", "Sql\\Ntdbms\\storeng\\drs\\fixedvarrecord.cpp", 2024, 0);
              else
                ex_raise(34, 68, 21, 1004);
            }
          }
        }
      }
      RaiseInconsistencyError(*((_QWORD *)v30 + 1), 4);
      v348 = *((_WORD *)v30 + 14);
      v342 = *((_DWORD *)v30 + 1);
    }
    if ( (v347[v348] & 0x8000u) == 0 )
    {
LABEL_714:
      LODWORD(v343) = *((_DWORD *)v30 + 1);
      v346 = (_BYTE *)*((_QWORD *)v30 + 1);
      goto LABEL_715;
    }
    while ( 1 )
    {
      v356 = *((_QWORD *)v30 + 1);
      v357 = v356 + *((unsigned int *)v30 + 5);
      if ( v348 == 1 )
      {
        v358 = *((_DWORD *)v30 + 6);
        v359 = v358;
        v360 = *(_WORD *)(v357 + 2LL * v348) & 0x7FFF;
      }
      else
      {
        v358 = *(_WORD *)(v357 + 2LL * v348 - 2) & 0x7FFF;
        v359 = *((_DWORD *)v30 + 6);
        v360 = *(_WORD *)(v357 + 2LL * v348) & 0x7FFF;
        if ( v358 < v359 )
        {
LABEL_707:
          RaiseInconsistencyError(*((_QWORD *)v30 + 1), 7);
          v359 = *((_DWORD *)v30 + 6);
          v356 = *((_QWORD *)v30 + 1);
          v342 = *((_DWORD *)v30 + 1);
          goto LABEL_708;
        }
      }
      if ( v360 < v358 )
        goto LABEL_707;
LABEL_708:
      if ( v358 < v359 )
        goto LABEL_745;
      v342 = *((_DWORD *)v30 + 1);
      if ( v358 > v342 )
        goto LABEL_745;
      v361 = *(_WORD *)(v356 + v358);
      if ( v361 == 5 )
      {
        *(_WORD *)v341 |= 2u;
        --*((_WORD *)v30 + 14);
        *((_WORD *)v30 + 21) = v358;
        v343 = *((_QWORD *)v30 + 1) + (unsigned __int16)v358;
        v398 = *((_WORD *)v30 + 22) & 0xC7FF;
        if ( _bittest16((const signed __int16 *)(v343 + 2), 0xEu) )
          v398 |= *(_WORD *)(v343 + 2) & 0x3800;
        *((_WORD *)v30 + 22) = v398;
        *((_WORD *)v30 + 22) = v398 ^ (*(_WORD *)(v343 + 2) ^ v398) & 0x7FF;
        LODWORD(v343) = *((_DWORD *)v30 + 1);
        v346 = (_BYTE *)*((_QWORD *)v30 + 1);
LABEL_715:
        if ( (*v346 & 0x40) != 0 )
        {
          v363 = *((_DWORD *)v30 + 1);
          *(_DWORD *)((char *)v30 + 38) = v363;
          *((_DWORD *)v30 + 1) = v363 + 14;
          v364 = FixedVarRecord::FindVersioningInfo((Record *)((char *)v30 + 2));
          v365 = HIDWORD(*(_QWORD *)v364);
          v366 = HIWORD(*(_QWORD *)v364);
          v367 = 0;
          if ( (((__int16)v366 ^ ((unsigned int)(__int16)v366 >> 1)) & 0x2000) != 0 )
          {
            v368 = v366 & 0xDFFF;
            if ( (v366 & 0x4000) != 0 )
              v368 = v366 | 0x2000;
            LOWORD(v366) = v368;
          }
          if ( (_WORD)v366 == 0xFFFC )
            v367 = (unsigned __int16)v365 >> 5;
          *((_DWORD *)v30 + 1) += v367;
          LODWORD(v343) = *((_DWORD *)v30 + 1);
          v346 = (_BYTE *)*((_QWORD *)v30 + 1);
        }
        else
        {
          *(_DWORD *)((char *)v30 + 38) = 0;
        }
        v369 = *(_QWORD *)((char *)v30 + 30);
        v342 = v343;
        if ( v369 && v369 < (unsigned __int64)&v346[(unsigned int)v343] )
        {
          if ( byte_10316E8D7 || (qword_10317B120 & 1) != 0 )
          {
            v370 = *(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                             + SystemThread_TlsOffset
                             + 8LL);
            if ( v370 )
            {
              v371 = *(_QWORD *)(v370 + 96);
              if ( v371 )
              {
                if ( *(_BYTE *)(v371 + 1177) )
                {
                  if ( byte_10316E7C7 || (qword_10317B120 & 2) != 0 )
                    utassert_fail(1u, "false", "Sql\\Ntdbms\\storeng\\drs\\fixedvarrecord.cpp", 2114, 0);
                  else
                    ex_raise(34, 68, 21, 1018);
                }
              }
            }
          }
          RaiseInconsistencyError(*((_QWORD *)v30 + 1), 18);
          v342 = *((_DWORD *)v30 + 1);
        }
        if ( !v342 || v342 > 0x3F3C )
        {
          if ( byte_10316E8D7 || (qword_10317B120 & 1) != 0 )
          {
            v372 = *(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                             + SystemThread_TlsOffset
                             + 8LL);
            if ( v372 )
            {
              v373 = *(_QWORD *)(v372 + 96);
              if ( v373 )
              {
                if ( *(_BYTE *)(v373 + 1177) )
                {
                  if ( byte_10316E7C7 || (qword_10317B120 & 2) != 0 )
                    utassert_fail(1u, "false", "Sql\\Ntdbms\\storeng\\drs\\fixedvarrecord.cpp", 2119, 0);
                  else
                    ex_raise(34, 68, 21, 1005);
                }
              }
            }
          }
          RaiseInconsistencyError(*((_QWORD *)v30 + 1), 5);
          v342 = *((_DWORD *)v30 + 1);
        }
LABEL_745:
        v374 = (_BYTE *)*((_QWORD *)v30 + 1);
        if ( (*v374 & 0x20) == 0 )
        {
          v342 = *((_DWORD *)v30 + 1) + 2;
          if ( v342 > a19 )
          {
            *((_DWORD *)v30 + 1) = v342;
          }
          else
          {
            *v374 |= 0x20u;
            *(_WORD *)(*((_QWORD *)v30 + 1) + *((unsigned int *)v30 + 5)) = 0;
            *((_DWORD *)v30 + 6) = *((_DWORD *)v30 + 5) + 2;
            *((_DWORD *)v30 + 1) += 2;
            v342 = *((_DWORD *)v30 + 1);
          }
        }
        if ( v342 + 2 > a19 )
        {
          *((_DWORD *)v30 + 1) = v342 + 2;
        }
        else
        {
          v375 = *((unsigned __int16 *)v30 + 14);
          v376 = *((unsigned int *)v30 + 5);
          v377 = *((_QWORD *)v30 + 1);
          v378 = (_WORD *)(v377 + v376);
          v379 = 0;
          if ( *(_WORD *)(v377 + v376) )
          {
            do
            {
              v380 = v378[v379 + 1];
              v378[(unsigned __int16)v379 + 1] &= 0x8000u;
              v378[(unsigned __int16)v379++ + 1] |= ((v380 & 0x7FFF) + 2) & 0x7FFF;
            }
            while ( v379 < (unsigned __int16)*v378 );
            v342 = *((_DWORD *)v30 + 1);
            v377 = *((_QWORD *)v30 + 1);
          }
          memmove(
            (void *)(v377 + (_DWORD)v376 + 2 + 2 * v375 + 2),
            (const void *)(v377 + (_DWORD)v376 + 2 + 2 * v375),
            v342 - ((_DWORD)v376 + 2 + 2 * v375));
          *((_DWORD *)v30 + 1) += 2;
          v381 = *((_DWORD *)v30 + 6) + 2;
          *((_DWORD *)v30 + 6) = v381;
          if ( v375 )
            LOWORD(v381) = v378[v375] & 0x7FFF;
          v382 = v375 + 1;
          if ( v375 < v375 + 1 )
          {
            v383 = v381 & 0x7FFF;
            do
              v378[(unsigned __int16)v375++ + 1] = v383;
            while ( v375 < v382 );
          }
          ++*v378;
          FixedVarRecord::HasSparseVector((Record *)((char *)v30 + 2));
        }
        v384 = *((_DWORD *)v30 + 1);
        v385 = a19 - v384;
        if ( v384 >= a19 )
          v385 = 0;
        v386 = v455;
        v387 = v448;
        FixedVarSparseVector::CreateAndInit((FixedVarSparseVector *)(v341 + 40), v384, v385, v41, v448, v455);
        v388 = *(_DWORD *)(v341 + 2);
        if ( *v386 )
        {
          v74 = *v386 + v388;
          *(_DWORD *)(v341 + 2) = v74;
          if ( (unsigned int)v74 <= a19 )
          {
            v91 = 0x8000;
            LOWORD(v74) = v74 | 0x8000;
            *(_WORD *)(*(_QWORD *)(v341 + 6) + *(unsigned int *)(v341 + 18) + 2LL * *((unsigned __int16 *)v341 + 13) + 2) = v74;
            *(_WORD *)v341 |= 2u;
          }
        }
        else if ( v388 > a19 )
        {
          *(_DWORD *)(v341 + 2) = v388 - 2;
        }
        else
        {
          FixedVarRecord::ShrinkOffTbl((FixedVarRecord *)v341, *((unsigned __int16 *)v341 + 13) + 1, 0);
          if ( (**(_BYTE **)(v341 + 6) & 0x20) != 0 )
            ++*((_WORD *)v341 + 13);
          *((_DWORD *)v341 + 10) = 0;
          *(_WORD *)v341 &= ~2u;
        }
        *v386 = *(_DWORD *)(v341 + 2);
        v389 = (unsigned __int8)v437 & (*(_DWORD *)(v341 + 2) <= a19);
        v390 = 0;
        v391 = 0;
        if ( (int)v445 > 0 )
        {
          _mm_lfence();
          v392 = (char *)v387 + 8;
          v393 = v445;
          v394 = v459;
          do
          {
            if ( (v392[4] & 2) == 0 )
            {
              v395 = *(_QWORD *)(*((_QWORD *)v394 + 3) + 8LL);
              v396 = HoBtColumnAttributeCacheShareable::GetHoBtColumnAttributeByHoBtColumnId(
                       **(HoBtColumnAttributeCacheShareable ***)(v395 + 352),
                       *((_DWORD *)v392 + 2) & 0x1FFFFFFF);
              if ( ((*((_BYTE *)v396 + 52) - 106) & 0xFD) != 0
                || (*(_BYTE *)(v395 + 263) & 8) == 0
                || (*((_BYTE *)v396 + 32) & 0x10) != 0 )
              {
                v391 += *(_DWORD *)v392;
              }
              else
              {
                v453 = 17;
                if ( !CSsNumeric::ConvertVarNumericToNumeric(
                        *((const unsigned __int8 **)v392 - 1),
                        *(_DWORD *)v392,
                        *((_BYTE *)v396 + 53),
                        *((_BYTE *)v396 + 54),
                        v488,
                        &v453) )
                  ex_raise(6, 83, 22, 2);
                v391 += v453;
              }
              ++v390;
            }
            v392 += 32;
            --v393;
          }
          while ( v393 );
          v40 = v443;
          if ( v390 )
            v391 += 6 * v390 + 23;
        }
        *v464 = v391;
        inited = 0;
        if ( v391 <= 0x1F57 )
          inited = v389;
        v437 = inited;
        goto LABEL_121;
      }
      if ( v361 >= 0x400u )
      {
        *(_WORD *)v341 |= 1u;
        v362 = *((_WORD *)v30 + 14) - 1;
        *((_WORD *)v30 + 14) = v362;
        if ( v362 )
        {
          v348 = v362;
          if ( (v347[v362] & 0x8000u) != 0 )
            continue;
        }
      }
      goto LABEL_714;
    }
  }
  v74 = (__int64)v478;
  if ( *v478 )
    goto LABEL_121;
  v399 = 0;
  v400 = (char *)v448 + 12;
  do
  {
    if ( (*v400 & 1) != 0 )
    {
      *v478 = 1;
      break;
    }
    ++v399;
    v400 += 32;
  }
  while ( v399 < v445 );
LABEL_121:
  v42 = v441;
  if ( inited )
  {
    if ( *(_WORD *)v441 )
    {
      v432 = *(_DWORD *)((char *)v40 + 2);
      if ( !v432 )
      {
        CDRecord::Resize(v40);
        v432 = *(_DWORD *)((char *)v40 + 2);
      }
      if ( v432 >= 9
        || (v433 = *(_BYTE **)((char *)v40 + 6), v74 = *v433 & 0x1C, (*v433 & 0x1C) != 0) && (_DWORD)v74 != 12 )
      {
        v446 = v432;
      }
      else
      {
        v446 = 9;
      }
      goto LABEL_127;
    }
    if ( *(_DWORD *)((char *)v40 + 2) )
    {
LABEL_124:
      v74 = *(unsigned int *)((char *)v40 + 2);
      if ( (unsigned int)v74 >= 9 || (v431 = **(_BYTE **)((char *)v40 + 6) & 0xE) != 0 && v431 != 12 )
        v446 = *(_DWORD *)((char *)v40 + 2);
      inited = v437;
LABEL_127:
      *v455 = v446;
      goto LABEL_128;
    }
    *(_WORD *)v40 = 0;
    v401 = *(unsigned int *)((char *)v40 + 14);
    *(_DWORD *)((char *)v40 + 18) = v401;
    v91 = *(_QWORD *)((char *)v40 + 6);
    v402 = *(_BYTE *)v91;
    if ( (*(_BYTE *)v91 & 0x10) != 0 )
    {
      LODWORD(v401) = (((unsigned int)*(unsigned __int16 *)(v401 + v91) + 7) >> 3) + v401 + 2;
      *(_DWORD *)((char *)v40 + 18) = v401;
      v402 = *(_BYTE *)v91;
    }
    if ( (v402 & 0x20) != 0 )
    {
      v403 = (unsigned __int16 *)(v91 + (unsigned int)v401);
      v404 = *v403;
      *((_WORD *)v40 + 13) = *v403;
      if ( !v404 )
      {
        if ( byte_10316E8D7 || (qword_10317B120 & 1) != 0 )
        {
          v405 = *(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                           + SystemThread_TlsOffset
                           + 8LL);
          if ( v405 )
          {
            v406 = *(_QWORD *)(v405 + 96);
            if ( v406 )
            {
              if ( *(_BYTE *)(v406 + 1177) )
              {
                if ( byte_10316E7C7 || (qword_10317B120 & 2) != 0 )
                  utassert_fail(1u, "false", "Sql\\Ntdbms\\storeng\\drs\\fixedvarrecord.cpp", 2010, 0);
                else
                  ex_raise(34, 68, 21, 1003);
              }
            }
          }
        }
        RaiseInconsistencyError(*(_QWORD *)((char *)v40 + 6), 3);
        v404 = *((_WORD *)v40 + 13);
        LODWORD(v401) = *(_DWORD *)((char *)v40 + 18);
      }
      v407 = v401 + 2 * (v404 + 1);
      *(_DWORD *)((char *)v40 + 22) = v407;
      if ( v407 > 0x1F9E )
      {
        if ( byte_10316E8D7 || (qword_10317B120 & 1) != 0 )
        {
          v408 = *(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                           + SystemThread_TlsOffset
                           + 8LL);
          if ( v408 )
          {
            v409 = *(_QWORD *)(v408 + 96);
            if ( v409 )
            {
              if ( *(_BYTE *)(v409 + 1177) )
              {
                if ( byte_10316E7C7 || (qword_10317B120 & 2) != 0 )
                  utassert_fail(1u, "false", "Sql\\Ntdbms\\storeng\\drs\\fixedvarrecord.cpp", 2017, 0);
                else
                  ex_raise(34, 68, 21, 1004);
              }
            }
          }
        }
        RaiseInconsistencyError(*(_QWORD *)((char *)v40 + 6), 4);
        v404 = *((_WORD *)v40 + 13);
        v407 = *(_DWORD *)((char *)v40 + 22);
      }
      LODWORD(v401) = v403[v404] & 0x7FFF;
      *(_DWORD *)((char *)v40 + 2) = v401;
      if ( v407 > (unsigned int)v401 )
      {
        if ( byte_10316E8D7 || (qword_10317B120 & 1) != 0 )
        {
          v410 = *(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                           + SystemThread_TlsOffset
                           + 8LL);
          if ( v410 )
          {
            v411 = *(_QWORD *)(v410 + 96);
            if ( v411 )
            {
              if ( *(_BYTE *)(v411 + 1177) )
              {
                if ( byte_10316E7C7 || (qword_10317B120 & 2) != 0 )
                  utassert_fail(1u, "false", "Sql\\Ntdbms\\storeng\\drs\\fixedvarrecord.cpp", 2024, 0);
                else
                  ex_raise(34, 68, 21, 1004);
              }
            }
          }
        }
        RaiseInconsistencyError(*(_QWORD *)((char *)v40 + 6), 4);
        v404 = *((_WORD *)v40 + 13);
        LODWORD(v401) = *(_DWORD *)((char *)v40 + 2);
      }
      if ( (v403[v404] & 0x8000u) != 0 )
      {
        v91 = *(_QWORD *)((char *)v40 + 6);
        while ( 1 )
        {
          v412 = v404;
          v413 = v91 + *(unsigned int *)((char *)v40 + 18);
          if ( v404 == 1 )
          {
            v414 = *(_DWORD *)((char *)v40 + 22);
            v415 = v414;
            v416 = *(_WORD *)(v413 + 2 * v412) & 0x7FFF;
          }
          else
          {
            v414 = *(_WORD *)(v413 + 2LL * v404 - 2) & 0x7FFF;
            v415 = *(_DWORD *)((char *)v40 + 22);
            v416 = *(_WORD *)(v413 + 2 * v412) & 0x7FFF;
            if ( v414 < v415 )
            {
LABEL_847:
              RaiseInconsistencyError(v91, 7);
              v415 = *(_DWORD *)((char *)v40 + 22);
              goto LABEL_848;
            }
          }
          if ( v416 < v414 )
            goto LABEL_847;
LABEL_848:
          if ( v414 < v415 )
            goto LABEL_124;
          LODWORD(v401) = *(_DWORD *)((char *)v40 + 2);
          if ( v414 > (unsigned int)v401 )
            goto LABEL_124;
          v91 = *(_QWORD *)((char *)v40 + 6);
          v417 = *(_WORD *)(v414 + v91);
          if ( v417 == 5 )
          {
            *(_WORD *)v40 |= 2u;
            --*((_WORD *)v40 + 13);
            *((_WORD *)v40 + 20) = v414;
            v429 = *(_QWORD *)((char *)v40 + 6) + (unsigned __int16)v414;
            v430 = *((_WORD *)v40 + 21) & 0xC7FF;
            if ( _bittest16((const signed __int16 *)(v429 + 2), 0xEu) )
              v430 |= *(_WORD *)(v429 + 2) & 0x3800;
            *((_WORD *)v40 + 21) = v430;
            *((_WORD *)v40 + 21) = v430 ^ (*(_WORD *)(v429 + 2) ^ v430) & 0x7FF;
            LODWORD(v401) = *((_DWORD *)v42 + 1);
            break;
          }
          if ( v417 < 0x400u )
            break;
          *(_WORD *)v40 |= 1u;
          v418 = *((_WORD *)v40 + 13) - 1;
          *((_WORD *)v40 + 13) = v418;
          if ( !v418 )
            break;
          v404 = v418;
          if ( (v403[v418] & 0x8000u) == 0 )
            goto LABEL_854;
        }
      }
      v91 = *(_QWORD *)((char *)v40 + 6);
    }
    else
    {
      *(_DWORD *)((char *)v40 + 2) = v401;
      *((_WORD *)v40 + 13) = 0;
      *(_DWORD *)((char *)v40 + 22) = v401;
    }
LABEL_854:
    if ( (*(_BYTE *)v91 & 0x40) != 0 )
    {
      *((_DWORD *)v40 + 9) = v401;
      *(_DWORD *)((char *)v40 + 2) = v401 + 14;
      v419 = FixedVarRecord::FindVersioningInfo(v40);
      v420 = HIDWORD(*(_QWORD *)v419);
      v421 = HIWORD(*(_QWORD *)v419);
      v422 = 0;
      if ( (((__int16)v421 ^ ((unsigned int)(__int16)v421 >> 1)) & 0x2000) != 0 )
      {
        v423 = v421 & 0xDFFF;
        if ( (v421 & 0x4000) != 0 )
          v423 = v421 | 0x2000;
        LOWORD(v421) = v423;
      }
      if ( (_WORD)v421 == 0xFFFC )
        v422 = (unsigned __int16)v420 >> 5;
      *(_DWORD *)((char *)v40 + 2) += v422;
      LODWORD(v401) = *(_DWORD *)((char *)v40 + 2);
    }
    else
    {
      *((_DWORD *)v40 + 9) = 0;
    }
    v91 = *(_QWORD *)((char *)v40 + 28);
    v424 = v401;
    if ( v91 && v91 < *(_QWORD *)((char *)v40 + 6) + (unsigned __int64)(unsigned int)v401 )
    {
      if ( byte_10316E8D7 || (qword_10317B120 & 1) != 0 )
      {
        v425 = *(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                         + SystemThread_TlsOffset
                         + 8LL);
        if ( v425 )
        {
          v426 = *(_QWORD *)(v425 + 96);
          if ( v426 )
          {
            if ( *(_BYTE *)(v426 + 1177) )
            {
              if ( byte_10316E7C7 || (qword_10317B120 & 2) != 0 )
                utassert_fail(1u, "false", "Sql\\Ntdbms\\storeng\\drs\\fixedvarrecord.cpp", 2114, 0);
              else
                ex_raise(34, 68, 21, 1018);
            }
          }
        }
      }
      RaiseInconsistencyError(*(_QWORD *)((char *)v40 + 6), 18);
      v424 = *(_DWORD *)((char *)v40 + 2);
    }
    if ( (unsigned int)(v424 - 1) > 0x3F3B )
    {
      if ( byte_10316E8D7 || (qword_10317B120 & 1) != 0 )
      {
        v427 = *(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                         + SystemThread_TlsOffset
                         + 8LL);
        if ( v427 )
        {
          v428 = *(_QWORD *)(v427 + 96);
          if ( v428 )
          {
            if ( *(_BYTE *)(v428 + 1177) )
            {
              if ( byte_10316E7C7 || (qword_10317B120 & 2) != 0 )
                utassert_fail(1u, "false", "Sql\\Ntdbms\\storeng\\drs\\fixedvarrecord.cpp", 2119, 0);
              else
                ex_raise(34, 68, 21, 1005);
            }
          }
        }
      }
      RaiseInconsistencyError(*(_QWORD *)((char *)v40 + 6), 5);
    }
    goto LABEL_124;
  }
LABEL_128:
  if ( v479 )
    (*(void (__fastcall **)(struct RowObject *, __int64, unsigned __int64))(*(_QWORD *)v479 + 8LL))(v479, v74, v91);
  if ( (*(_BYTE *)(*(_QWORD *)v451 + 92LL) & 0x20) != 0 )
  {
    if ( v447 )
    {
      v43 = (const struct HoBtAccess *)*((_QWORD *)v459 + 3);
      v44 = *((_QWORD *)v43 + 1);
      if ( *(_DWORD *)(v44 + 188) != 0x7FFFFFFF || *(_DWORD *)(v44 + 196) != 0x7FFFFFFF )
        VerifyVariableSize(v43, v42);
    }
  }
  if ( v465 )
    *(_BYTE *)(*((_QWORD *)v465 + 5) + 181LL) = 0;
  return inited;
}

```

## disassembly

```asm
0x100524db0  push    rbp
0x100524db2  push    rsi
0x100524db3  push    rdi
0x100524db4  push    r12
0x100524db6  push    r13
0x100524db8  push    r14
0x100524dba  push    r15
0x100524dbc  mov     eax, 2180h
0x100524dc1  call    _alloca_probe
0x100524dc6  sub     rsp, rax
0x100524dc9  lea     rbp, [rsp+30h]
0x100524dce  mov     [rbp+2180h+var_2008], 0FFFFFFFFFFFFFFFEh
0x100524dd9  mov     [rbp+2180h+arg_8], rbx
0x100524de0  mov     rax, cs:__security_cookie
0x100524de7  xor     rax, rbp
0x100524dea  mov     [rbp+2180h+var_40], rax
0x100524df1  mov     [rbp+2180h+var_2120], r9d
0x100524df5  mov     [rbp+2180h+var_2060], r8
0x100524dfc  mov     dword ptr [rbp+2180h+var_2170], edx
0x100524dff  mov     [rbp+2180h+var_20F0], rcx
0x100524e06  mov     eax, [rbp+2180h+arg_28]
0x100524e0c  mov     [rbp+2180h+var_2150], eax
0x100524e0f  mov     edi, dword ptr [rbp+2180h+arg_20]
0x100524e15  mov     r15, [rbp+2180h+arg_38]
0x100524e1c  mov     [rbp+2180h+var_2118], r15
0x100524e20  mov     r8, [rbp+2180h+arg_40]
0x100524e27  mov     [rbp+2180h+var_2048], r8
0x100524e2e  mov     rax, [rbp+2180h+arg_48]
0x100524e35  mov     [rbp+2180h+var_2128], rax
0x100524e39  mov     rax, [rbp+2180h+arg_50]
0x100524e40  mov     [rbp+2180h+var_2058], rax
0x100524e47  mov     rax, [rbp+2180h+arg_60]
0x100524e4e  mov     [rbp+2180h+var_20D0], rax
0x100524e55  mov     rax, [rbp+2180h+arg_68]
0x100524e5c  mov     [rbp+2180h+var_2108], rax
0x100524e60  mov     rcx, [rbp+2180h+arg_70]
0x100524e67  mov     [rbp+2180h+var_2138], rcx
0x100524e6b  mov     rax, [rbp+2180h+arg_78]
0x100524e72  mov     [rbp+2180h+var_2168], rax
0x100524e76  mov     r12, [rbp+2180h+arg_80]
0x100524e7d  mov     rax, [rbp+2180h+arg_98]
0x100524e84  mov     [rbp+2180h+var_2110], rax
0x100524e88  mov     rax, [rbp+2180h+arg_A0]
0x100524e8f  mov     [rbp+2180h+var_20C8], rax
0x100524e96  mov     rax, [rbp+2180h+arg_B0]
0x100524e9d  mov     [rbp+2180h+var_2080], rax
0x100524ea4  mov     rax, [rbp+2180h+arg_B8]
0x100524eab  mov     [rbp+2180h+var_2088], rax
0x100524eb2  mov     r13, [rbp+2180h+arg_C0]
0x100524eb9  mov     [rbp+2180h+var_2068], r13
0x100524ec0  mov     rcx, [rbp+2180h+arg_D0]
0x100524ec7  mov     [rbp+2180h+var_2050], rcx
0x100524ece  mov     rcx, [rbp+2180h+arg_D8]
0x100524ed5  mov     [rbp+2180h+var_2070], rcx
0x100524edc  mov     rcx, [rbp+2180h+arg_E0]
0x100524ee3  mov     [rbp+2180h+var_2078], rcx
0x100524eea  xor     r9d, r9d
0x100524eed  mov     [rbp+2180h+var_2160], r9
0x100524ef1  mov     [rbp+2180h+var_2140], r9
0x100524ef5  mov     ecx, 0FFFFFFFFh
0x100524efa  mov     [rbp+2180h+var_2040], cx
0x100524f01  mov     [rbp+2180h+var_2038], r9
0x100524f08  mov     [rbp+2180h+var_203C], r9d
0x100524f0f  mov     [rbp+2180h+var_2022], r9
0x100524f16  mov     [rbp+2180h+var_2018], r9
0x100524f1d  mov     [rbp+2180h+var_2030], r9
0x100524f24  mov     [rbp+2180h+var_2144], r9d
0x100524f28  mov     [rbp+2180h+var_217C], 1
0x100524f2f  mov     [rbp+2180h+var_20D8], r9
0x100524f36  mov     [rbp+2180h+var_2130], r9d
0x100524f3a  mov     [rax], r9d
0x100524f3d  mov     eax, 0FFFFh
0x100524f42  test    r8, r8
0x100524f45  jnz     loc_1005FDCC3
0x100524f4b  mov     [rbp+2180h+var_20A0], r9
0x100524f52  mov     [rbp+2180h+var_20C0], r9
0x100524f59  test    r8, r8
0x100524f5c  jnz     loc_1005FDD54
0x100524f62  lea     rsi, [r15+2]
0x100524f66  mov     [rbp+2180h+var_2090], rsi
0x100524f6d  cmp     word ptr [r15], 0
0x100524f72  jnz     loc_10211F5BB
0x100524f78  mov     rcx, rsi; this
0x100524f7b  call    ?NumVarCol@FixedVarRecord@@AEBAHXZ; FixedVarRecord::NumVarCol(void)
0x100524f80  mov     r14d, eax
0x100524f83  neg     edi
0x100524f85  mov     ebx, eax
0x100524f87  cmp     eax, edi
0x100524f89  cmovbe  ebx, edi
0x100524f8c  mov     rcx, [r15+8]
0x100524f90  movzx   ecx, byte ptr [rcx]
0x100524f93  cmp     word ptr [r15], 0
0x100524f98  jnz     loc_10211F5D1
0x100524f9e  and     cl, 0Eh
0x100524fa1  mov     eax, 1
0x100524fa6  shl     eax, cl
0x100524fa8  and     eax, 1105h
0x100524fad  jmp     short loc_100524FB0
0x100524fb0  mov     [rbp+2180h+var_2174], ebx
0x100524fb3  test    eax, eax
0x100524fb5  jz      short loc_100524FD7
0x100524fb7  mov     rax, [rbp+2180h+var_2128]
0x100524fbb  mov     rdi, [rax+28h]
0x100524fbf  mov     [rbp+2180h+var_20D8], rdi
0x100524fc6  mov     eax, [rax+30h]
0x100524fc9  mov     [rbp+2180h+var_2130], eax
0x100524fcc  mov     [rbp+2180h+var_2174], ebx
0x100524fcf  test    eax, eax
0x100524fd1  jnz     loc_10211F5F8
0x100524fd7  mov     rcx, r15; this
0x100524fda  call    ?GetSparseColumnCount@Record@@QEBAHXZ; Record::GetSparseColumnCount(void)
0x100524fdf  mov     r8d, eax; unsigned int
0x100524fe2  mov     [rbp+2180h+var_2178], eax
0x100524fe5  mov     [rbp+2180h+var_214C], eax
0x100524fe8  mov     ecx, [rbp+2180h+var_2120]
0x100524feb  add     ecx, eax
0x100524fed  mov     [rbp+2180h+var_2180], ecx
0x100524ff0  mov     edi, 4000h
0x100524ff5  mov     r10d, 7FFFh
0x100524ffb  mov     r9d, 9
0x100525001  mov     [rbp+2180h+var_2148], r9d
0x100525005  test    r13, r13
0x100525008  jz      loc_10211FCD6
0x10052500e  cmp     word ptr [r15], 0
0x100525013  jnz     loc_10211FC9B
0x100525019  cmp     dword ptr [rsi+2], 0
0x10052501d  jz      loc_10211F62A
0x100525023  mov     ecx, [rsi+2]
0x100525026  cmp     ecx, 9
0x100525029  jnb     short loc_10052503E
0x10052502b  mov     rax, [rsi+6]
0x10052502f  movzx   edx, byte ptr [rax]
0x100525032  and     dl, 0Eh
0x100525035  jnz     loc_10211FC89
0x10052503b  mov     ecx, r9d
0x10052503e  mov     [r13+0], ecx
0x100525042  mov     [r13+4], r14d
0x100525046  mov     [r13+8], r8d
0x10052504a  xor     r14d, r14d
0x10052504d  mov     [r13+0Ch], r14
0x100525051  jmp     short loc_100525054
0x100525054  movzx   eax, word ptr [r15]
0x100525058  test    ax, ax
0x10052505b  jnz     loc_10211FCDF
0x100525061  mov     r13, r15
0x100525064  mov     rbx, [rbp+2180h+var_2168]
0x100525068  mov     [rbx], ax
0x10052506b  lea     r15, [rbx+2]
0x10052506f  mov     [rbp+2180h+var_2158], r15
0x100525073  test    ax, ax
0x100525076  jnz     loc_10211FDFF
0x10052507c  mov     [r15+6], r12
0x100525080  mov     eax, [rbp+2180h+arg_30]
0x100525086  mov     [r15+0Eh], eax
0x10052508a  mov     [r15+1Ah], r14w
0x10052508f  mov     [r15], r14w
0x100525093  mov     [r15+24h], r14d
0x100525097  mov     rax, [r13+8]
0x10052509b  movzx   ecx, byte ptr [rax]
0x10052509e  and     cl, 0Eh
0x1005250a1  cmp     cl, 6
0x1005250a4  jz      loc_10211FD87
0x1005250aa  mov     byte ptr [r12], 0
0x1005250af  mov     rax, [r15+6]
0x1005250b3  mov     byte ptr [rax+1], 0
0x1005250b7  mov     ecx, [r15+0Eh]
0x1005250bb  mov     rax, [r15+6]
0x1005250bf  mov     [rax+2], cx
0x1005250c3  mov     edx, 4
0x1005250c8  mov     ecx, [r13+10h]
0x1005250cc  mov     r9d, edx
0x1005250cf  cmp     ecx, [r15+0Eh]
0x1005250d3  cmovnb  ecx, [r15+0Eh]
0x1005250d8  sub     ecx, edx
0x1005250da  mov     r8d, ecx; Size
0x1005250dd  mov     rdx, [r13+8]
0x1005250e1  add     rdx, r9; Src
0x1005250e4  mov     rcx, [r15+6]
0x1005250e8  add     rcx, r9; void *
0x1005250eb  call    memmove
0x1005250f0  mov     r12d, [rbp+2180h+var_2150]
0x1005250f4  test    r12d, r12d
0x1005250f7  jz      loc_10211FDEA
0x1005250fd  mov     rax, [r15+6]
0x100525101  or      byte ptr [rax], 10h
0x100525104  mov     ecx, [r15+0Eh]
0x100525108  lea     eax, [r12+7]
0x10052510d  shr     eax, 3
0x100525110  lea     edx, [rcx+2]
0x100525113  add     edx, eax
0x100525115  mov     [r15+12h], edx
0x100525119  mov     r9, [r13+8]
0x10052511d  test    byte ptr [r9], 10h
0x100525121  jnz     short loc_10052518D
0x100525123  mov     ebx, r14d
0x100525126  movzx   r14d, r12w
0x10052512a  mov     rax, [r15+6]
0x10052512e  mov     [rax+rcx], r12w
0x100525133  cmp     r12d, ebx
0x100525136  cmovb   bx, r14w
0x10052513b  inc     bx
0x10052513e  movzx   r8d, bx
0x100525142  cmp     r8d, r12d
0x100525145  ja      short loc_100525177
0x100525147  movsxd  rdx, dword ptr [r15+0Eh]
0x10052514b  add     rdx, [r15+6]
0x10052514f  lea     ecx, [r8-1]
0x100525153  mov     r8d, ecx
0x100525156  shr     r8, 3
0x10052515a  movzx   eax, byte ptr [r8+rdx+2]
0x100525160  and     ecx, 7
0x100525163  bts     eax, ecx
0x100525166  mov     [r8+rdx+2], al
0x10052516b  inc     bx
0x10052516e  movzx   r8d, bx
0x100525172  cmp     r8d, r12d
0x100525175  jbe     short loc_100525147
0x100525177  xor     r14d, r14d
0x10052517a  mov     eax, [r15+12h]
0x10052517e  mov     rbx, [rbp+2180h+var_2168]
0x100525182  mov     [r15+16h], eax
0x100525186  mov     [r15+2], eax
0x10052518a  jmp     short loc_1005251CD
0x10052518d  mov     eax, [r13+10h]
0x100525191  movzx   ebx, word ptr [rax+r9]
0x100525196  mov     r10d, ecx
0x100525199  cmp     ebx, r12d
0x10052519c  jnz     loc_10211FD96
0x1005251a2  sub     edx, ecx
0x1005251a4  mov     r8d, edx; Size
0x1005251a7  mov     edx, [r13+10h]
0x1005251ab  add     rdx, r9; Src
0x1005251ae  mov     rcx, [r15+6]
0x1005251b2  add     rcx, r10; void *
0x1005251b5  call    memmove
0x1005251ba  mov     eax, [r15+12h]
0x1005251be  mov     rbx, [rbp+2180h+var_2168]
0x1005251c2  mov     [r15+16h], eax
0x1005251c6  mov     [r15+2], eax
0x1005251ca  jmp     short loc_1005251CD
0x1005251cd  cmp     word ptr [rbx], 0
0x1005251d1  jnz     loc_1021204BA
0x1005251d7  cmp     dword ptr [r15+2], 0
0x1005251dc  jz      loc_10211FE1C
0x1005251e2  mov     ecx, [r15+2]
0x1005251e6  cmp     ecx, 9
0x1005251e9  jb      loc_102120497
0x1005251ef  mov     rax, [rbp+2180h+var_2110]
0x1005251f3  mov     [rax], ecx
0x1005251f5  mov     rax, [rbp+2180h+var_20C8]
0x1005251fc  xor     ebx, ebx
0x1005251fe  mov     [rax], ebx
0x100525200  mov     rdx, 0FFFFFFFFFFFFFF0h
0x10052520a  mov     r12d, [rbp+2180h+var_2174]
0x10052520e  test    r12d, r12d
0x100525211  jz      loc_1005252AF
0x100525217  lfence
0x10052521a  mov     eax, r12d
0x10052521d  shl     rax, 5
0x100525221  lea     rcx, [rax+0Fh]
0x100525225  cmp     rcx, rax
0x100525228  jbe     loc_1021204E9
0x10052522e  and     rcx, 0FFFFFFFFFFFFFFF0h
0x100525232  mov     rax, rcx
0x100525235  call    _alloca_probe
0x10052523a  sub     rsp, rcx
0x10052523d  lea     rbx, [rsp+21B0h+var_2180]
0x100525242  mov     [rbp+2180h+var_2160], rbx
0x100525246  mov     r8d, r12d
0x100525249  shl     r8d, 5; Size
0x10052524d  xor     edx, edx; Val
0x10052524f  mov     rcx, rbx; void *
0x100525252  call    memset_0
0x100525257  cmp     word ptr [r13+0], 0
0x10052525d  jnz     loc_102120B87
0x100525263  xor     ebx, ebx
0x100525265  cmp     [r13+4], ebx
0x100525269  jz      loc_1021204F2
0x10052526f  movzx   r11d, word ptr [r13+1Ch]
0x100525274  cmp     r11d, r12d
0x100525277  cmovnb  r11d, r12d
0x10052527b  test    r11d, r11d
0x10052527e  jnz     loc_1005FDD69
0x100525284  mov     r8d, r12d
0x100525287  sub     r8d, r11d
0x10052528a  shl     r8d, 5; Size
0x10052528e  mov     ecx, r11d
0x100525291  shl     rcx, 5
0x100525295  add     rcx, [rbp+2180h+var_2160]; void *
0x100525299  xor     edx, edx; Val
0x10052529b  call    memset_0
0x1005252a0  jmp     short loc_1005252A3
0x1005252a3  xor     ebx, ebx
0x1005252a5  mov     rdx, 0FFFFFFFFFFFFFF0h
0x1005252af  mov     r14d, [rbp+2180h+var_2180]
0x1005252b3  test    r14d, r14d
0x1005252b6  jnz     loc_102120BA0
0x1005252bc  mov     r13d, [rbp+2180h+var_2174]
0x1005252c0  test    r13d, r13d
0x1005252c3  jz      loc_1021214A6
  ... truncated ...
```
