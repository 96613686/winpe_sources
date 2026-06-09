# AutoFillIPD(tagOBJBASE *,IPDTag *)

- ea: `0x383930a30`
- end: `0x38393371f`
- name: `?AutoFillIPD@@YAFPEAUtagOBJBASE@@PEAUIPDTag@@@Z`
- size: `11503`
- prototype: `__int16(struct tagOBJBASE *, struct IPDTag *)`
- caller_count: `5`
- callee_count: `44`
- tags: `file_ops, installer_update`

## callers

- `0x3838b70a0`
- `0x383928810`
- `0x3839295b0`
- `0x38392b4c0`
- `0x38392d590`

## callees

- `0x3838424f0`
- `0x3838434c0`
- `0x3838435e0`
- `0x3838435f0`
- `0x38384dd90`
- `0x383869d00`
- `0x383869d70`
- `0x38386a450`
- `0x38386d140`
- `0x38386d3c0`
- `0x38386ff50`
- `0x383870700`
- `0x3838707f0`
- `0x383871ae0`
- `0x383871d80`
- `0x383872620`
- `0x383873ca0`
- `0x38387da60`
- `0x383893160`
- `0x38389a4e0`
- `0x38389a5a0`
- `0x38389a920`
- `0x3838a3b00`
- `0x3838b3260`
- `0x3838b37e0`
- `0x3838bae20`
- `0x3838bb000`
- `0x38391aed0`
- `0x38391afe0`
- `0x38392afd0`
- `0x38392dc90`
- `0x383930a30`
- `0x383933750`
- `0x3839351f0`
- `0x383935f70`
- `0x3839368e0`
- `0x383936af0`
- `0x383936be0`
- `0x383952630`
- `0x38395ee50`
- `0x383962350`
- `0x383964030`
- `0x3839654d0`
- `0x3839656b0`

## import_xrefs

- `MSVCR100!_wcsnicmp` at `0x38393111b`
- `MSVCR100!_wcsnicmp` at `0x383931135`
- `MSVCR100!_wcsnicmp` at `0x38393114f`
- `MSVCR100!_wcsnicmp` at `0x383931169`
- `MSVCR100!_wcsnicmp` at `0x383931195`
- `MSVCR100!_wcsnicmp` at `0x383931209`
- `MSVCR100!_wcsnicmp` at `0x383931287`
- `MSVCR100!_wcsnicmp` at `0x3839312ba`
- `MSVCR100!_wcsnicmp` at `0x3839317b7`
- `MSVCR100!_wcsnicmp` at `0x38393111b`
- `MSVCR100!_wcsnicmp` at `0x383931135`
- `MSVCR100!_wcsnicmp` at `0x38393114f`
- `MSVCR100!_wcsnicmp` at `0x383931169`
- `MSVCR100!_wcsnicmp` at `0x383931195`
- `MSVCR100!_wcsnicmp` at `0x383931209`
- `MSVCR100!_wcsnicmp` at `0x383931287`
- `MSVCR100!_wcsnicmp` at `0x3839312ba`
- `MSVCR100!_wcsnicmp` at `0x3839317b7`
- `MSVCR100!_wcsicmp` at `0x38393329a`
- `MSVCR100!_wcsicmp` at `0x38393329a`

## string_xrefs

- `0x383931114`: `update`
- `0x383931162`: `delete`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall AutoFillIPD(struct tagOBJBASE *a1, struct IPDTag *a2)
{
  struct tagOBJBASE *v3; // r13
  __int64 v4; // rcx
  struct BATCHCTX **v5; // r15
  __int64 v6; // rax
  int v7; // esi
  int v8; // edi
  int NewBatchCtx; // eax
  struct BATCHCTX *v10; // rcx
  SQLRETURN ExtBuffer; // r12
  struct tagSTMT *v12; // rdi
  int v13; // eax
  struct BATCHCTX *v14; // r8
  __int64 v15; // rax
  __int64 v16; // rbx
  const void *v17; // rdi
  char *v18; // rcx
  __int64 v19; // r9
  wchar_t *v20; // r8
  __int64 v21; // rdx
  unsigned __int64 v22; // r8
  __int64 v23; // r9
  struct tagDBC *v24; // rbx
  __int16 v25; // bx
  __int64 v26; // rdx
  struct tagSTMT *v27; // rdi
  int v28; // ebx
  int v29; // eax
  int v30; // r11d
  int ServerMetadata; // eax
  char *v32; // rbx
  __int64 v33; // rdi
  unsigned __int16 LexToken; // r11
  unsigned int v35; // esi
  wchar_t *i; // rbx
  struct tagDBC *v37; // rbx
  int v38; // r14d
  __int16 v39; // r13
  struct tagDBC *v40; // rbx
  unsigned int v41; // edi
  unsigned __int16 v42; // ax
  int v43; // r14d
  unsigned int v44; // esi
  unsigned __int16 v45; // r11
  unsigned int v46; // r14d
  unsigned int v47; // r15d
  unsigned __int16 v48; // ax
  struct tagDBC *v49; // rsi
  unsigned int v50; // edx
  int v51; // r8d
  unsigned int v52; // r12d
  __int16 v53; // ax
  __int16 v54; // ax
  int v55; // r12d
  __int64 v56; // rax
  struct tagDBC *v57; // rbx
  unsigned int v58; // edi
  __int64 v59; // rax
  struct tagDBC *v60; // rsi
  unsigned int v61; // edi
  unsigned __int16 v62; // r14
  unsigned int v63; // edx
  unsigned int v64; // r15d
  __int16 v65; // cx
  __int64 v66; // rax
  int v67; // ebx
  unsigned int v68; // r12d
  __int64 v69; // r13
  __int16 v70; // bx
  struct tagOBJBASE *v71; // r14
  char *v72; // rax
  unsigned int v73; // ebx
  __int64 v74; // r14
  const unsigned __int16 *v75; // rdx
  wchar_t *v76; // rbx
  __int64 v77; // r9
  struct ext_buffer *v78; // rdx
  struct tagSTMT *v79; // r13
  unsigned __int16 v80; // ax
  struct tagOBJBASE *v81; // r14
  unsigned int v82; // ecx
  __int64 v83; // rax
  struct tagDBC *v84; // rbx
  unsigned int v85; // edi
  unsigned __int64 v86; // r13
  unsigned __int64 v87; // r14
  __int64 v88; // r15
  SQLHSTMT v89; // r8
  int v90; // ebx
  __int16 v91; // cx
  int v92; // eax
  __int16 v93; // ax
  struct pl *v94; // rax
  int v95; // r12d
  int v96; // r13d
  unsigned __int64 v97; // rsi
  struct tagDBC *v98; // r15
  unsigned __int16 v99; // bx
  unsigned int v100; // ecx
  const unsigned __int16 *v101; // r13
  int v102; // ebx
  unsigned int v103; // edi
  unsigned __int64 v104; // r15
  unsigned __int64 v105; // r14
  unsigned __int16 *v106; // r12
  int v107; // eax
  __int64 v108; // rdx
  __int64 v109; // r8
  unsigned __int16 *v110; // r10
  unsigned __int64 v111; // rcx
  __int64 v112; // rbx
  unsigned __int16 *v113; // rdx
  __int64 v114; // rax
  __int64 v115; // r8
  unsigned __int16 *v116; // rdx
  __int64 v117; // r9
  signed __int64 v118; // r11
  unsigned __int16 v119; // ax
  unsigned __int16 *v120; // rdx
  __int64 v121; // r8
  unsigned __int64 v122; // r12
  unsigned __int16 v123; // ax
  __int64 v124; // r8
  int v125; // edi
  unsigned __int16 **v126; // r14
  _DWORD *v127; // rbx
  __int64 v128; // rax
  unsigned __int64 v129; // rcx
  unsigned __int16 *v130; // rax
  unsigned __int16 *v131; // rdx
  unsigned __int64 v132; // r9
  unsigned __int16 v133; // ax
  __int64 v134; // rax
  int v135; // eax
  unsigned __int64 v136; // r9
  struct tagSTMT *v137; // r14
  __int64 v138; // r9
  struct tagSTMT *v139; // r15
  __int64 v140; // rcx
  char v141; // al
  __int64 v142; // rbx
  __int64 v143; // rdi
  int v144; // eax
  unsigned __int16 v145; // dx
  unsigned int v146; // eax
  signed int v147; // r13d
  __int64 v148; // r14
  unsigned int v149; // esi
  int v150; // edi
  int v151; // ebx
  struct tagDBC *v152; // r13
  __int16 v153; // cx
  SQLHSTMT v154; // rdi
  unsigned __int64 v155; // rax
  __int64 v156; // r11
  unsigned __int16 *v157; // rcx
  unsigned __int16 v158; // ax
  struct tagOBJBASE *v159; // r13
  __int16 v160; // ax
  __int64 v161; // rax
  __int64 v162; // rax
  SQLUSMALLINT v163; // dx
  SQLUSMALLINT v164; // bx
  unsigned __int16 *v165; // rbx
  SQLLEN v166; // rdi
  struct tagOBJBASE *v167; // rdi
  __int64 v168; // rdx
  unsigned int v169; // r9d
  unsigned __int64 v170; // rbx
  __int64 v171; // rcx
  __int64 v172; // rdi
  __int64 v173; // rsi
  int v174; // eax
  struct BATCHCTX *v175; // rax
  struct BATCHCTX **v176; // rbx
  __int64 v178; // rdx
  unsigned int *BufferLength; // [rsp+20h] [rbp-F0h]
  unsigned int *BufferLengtha; // [rsp+20h] [rbp-F0h]
  unsigned int *BufferLengthb; // [rsp+20h] [rbp-F0h]
  unsigned int *BufferLengthi; // [rsp+20h] [rbp-F0h]
  unsigned int *BufferLengthc; // [rsp+20h] [rbp-F0h]
  unsigned int *BufferLengthd; // [rsp+20h] [rbp-F0h]
  int BufferLengthe; // [rsp+20h] [rbp-F0h]
  int BufferLengthf; // [rsp+20h] [rbp-F0h]
  unsigned int *BufferLengthg; // [rsp+20h] [rbp-F0h]
  unsigned int *BufferLengthh; // [rsp+20h] [rbp-F0h]
  SQLLEN BufferLengthj; // [rsp+20h] [rbp-F0h]
  unsigned __int16 *StrLen_or_IndPtr; // [rsp+28h] [rbp-E8h]
  unsigned int v192; // [rsp+30h] [rbp-E0h]
  size_t v193; // [rsp+58h] [rbp-B8h]
  unsigned __int16 v194; // [rsp+60h] [rbp-B0h]
  int v195; // [rsp+90h] [rbp-80h]
  __int16 Exp; // [rsp+94h] [rbp-7Ch]
  size_t MaxCount; // [rsp+98h] [rbp-78h] BYREF
  struct tagOBJBASE *v198; // [rsp+A0h] [rbp-70h]
  unsigned __int16 v199[4]; // [rsp+A8h] [rbp-68h] BYREF
  SQLLEN v200; // [rsp+B0h] [rbp-60h] BYREF
  SQLSMALLINT ColumnCount[2]; // [rsp+B8h] [rbp-58h] BYREF
  int v202; // [rsp+BCh] [rbp-54h]
  bool v203; // [rsp+C0h] [rbp-50h] BYREF
  signed int v204; // [rsp+C4h] [rbp-4Ch]
  unsigned int v205; // [rsp+C8h] [rbp-48h] BYREF
  char v206[4]; // [rsp+CCh] [rbp-44h] BYREF
  int v207; // [rsp+D0h] [rbp-40h]
  SQLHSTMT StatementHandle; // [rsp+D8h] [rbp-38h]
  unsigned int v209; // [rsp+E0h] [rbp-30h] BYREF
  unsigned int v210[3]; // [rsp+E4h] [rbp-2Ch] BYREF
  struct tagSTMT *v211; // [rsp+F0h] [rbp-20h]
  unsigned __int64 v212; // [rsp+F8h] [rbp-18h] BYREF
  unsigned __int16 *v213; // [rsp+100h] [rbp-10h] BYREF
  unsigned __int64 v214; // [rsp+108h] [rbp-8h]
  struct tagDBC *v215; // [rsp+110h] [rbp+0h]
  struct ext_buffer *v216; // [rsp+118h] [rbp+8h] BYREF
  struct ext_buffer *v217; // [rsp+120h] [rbp+10h] BYREF
  struct tagOBJBASE *v218; // [rsp+128h] [rbp+18h]
  struct tagOBJBASE *v219; // [rsp+130h] [rbp+20h]
  unsigned int v220; // [rsp+138h] [rbp+28h] BYREF
  wchar_t *String2; // [rsp+140h] [rbp+30h] BYREF
  char *v222; // [rsp+148h] [rbp+38h]
  unsigned __int16 *v223; // [rsp+150h] [rbp+40h] BYREF
  unsigned __int64 v224; // [rsp+158h] [rbp+48h] BYREF
  unsigned int v225; // [rsp+160h] [rbp+50h] BYREF
  unsigned int v226; // [rsp+164h] [rbp+54h] BYREF
  int v227; // [rsp+168h] [rbp+58h] BYREF
  struct BATCHCTX *v228; // [rsp+170h] [rbp+60h]
  struct BATCHCTX **v229; // [rsp+178h] [rbp+68h]
  struct BATCHCTX *v230; // [rsp+180h] [rbp+70h]
  struct BATCHCTX *v231; // [rsp+188h] [rbp+78h]
  unsigned __int16 *v232; // [rsp+190h] [rbp+80h]
  unsigned int v233[2]; // [rsp+198h] [rbp+88h]
  unsigned __int16 *v234; // [rsp+1A0h] [rbp+90h]
  unsigned __int16 *v235[5]; // [rsp+1A8h] [rbp+98h] BYREF
  _QWORD v236[4]; // [rsp+1D0h] [rbp+C0h] BYREF
  struct tagOBJBASE *v237; // [rsp+1F0h] [rbp+E0h]
  __int16 v238; // [rsp+1F8h] [rbp+E8h]
  int v239; // [rsp+200h] [rbp+F0h]
  struct ext_buffer *v240; // [rsp+208h] [rbp+F8h]
  struct ext_buffer *v241[2]; // [rsp+210h] [rbp+100h] BYREF
  unsigned __int64 v242; // [rsp+220h] [rbp+110h] BYREF
  __int64 v243; // [rsp+228h] [rbp+118h] BYREF
  __int64 v244; // [rsp+230h] [rbp+120h]
  __int64 v245; // [rsp+238h] [rbp+128h]
  __int64 v246; // [rsp+240h] [rbp+130h]
  __int64 v247; // [rsp+248h] [rbp+138h]
  __int64 v248; // [rsp+250h] [rbp+140h]
  __int64 v249; // [rsp+258h] [rbp+148h]
  __int64 v250; // [rsp+260h] [rbp+150h]
  _OWORD v251[7]; // [rsp+270h] [rbp+160h] BYREF
  _DWORD v252[4]; // [rsp+2E0h] [rbp+1D0h] BYREF
  unsigned __int16 v253[136]; // [rsp+2F0h] [rbp+1E0h] BYREF
  unsigned __int16 TargetValue[136]; // [rsp+400h] [rbp+2F0h] BYREF
  unsigned __int16 v255[136]; // [rsp+510h] [rbp+400h] BYREF
  unsigned __int16 v256[544]; // [rsp+620h] [rbp+510h] BYREF

  v250 = -2;
  v218 = a2;
  v3 = a1;
  v198 = a1;
  v195 = 0;
  v211 = (struct tagSTMT *)*((_QWORD *)a2 + 8);
  v4 = *((_QWORD *)v211 + 14);
  v219 = (struct tagOBJBASE *)v4;
  v5 = *(struct BATCHCTX ***)(v4 + 8024);
  StatementHandle = v5;
  v217 = 0;
  *(_QWORD *)&v210[1] = 0;
  v232 = 0;
  v223 = 0;
  v222 = 0;
  if ( !*(_QWORD *)(v4 + 64)
    || (v6 = *(_QWORD *)(v4 + 64), *(_BYTE *)(v6 + 1246) < 0xBu)
    || (v7 = 1, (*(_BYTE *)(v6 + 400) & 2) != 0) )
  {
    v7 = 0;
  }
  v216 = 0;
  v228 = 0;
  if ( v5 != (struct BATCHCTX **)-304LL )
  {
    v228 = v5[38];
    (*(void (__fastcall **)(__int64, __int64))(*((_QWORD *)v228 + 4) + 8LL))((__int64)v228 + 32, 1);
  }
  v229 = 0;
  v230 = 0;
  v8 = 0;
  if ( v5[139]
    || (NewBatchCtx = CConnection::GetNewBatchCtx(
                        *((union _SLIST_HEADER **)v5[14] + 8),
                        (struct CConnection *)v5,
                        v5 + 139),
        v8 = NewBatchCtx,
        NewBatchCtx >= 0) )
  {
    v10 = v5[139];
    v231 = v10;
    if ( (*(_BYTE *)(*((_QWORD *)v10 + 8) + 400LL) & 1) != 0 )
    {
      v229 = v5;
      v230 = v10;
      ++*((_DWORD *)v5 + 280);
    }
  }
  else
  {
    v231 = 0;
    if ( (bidGblFlags & 2) != 0 )
      bidTraceHR(off_383B43228[0], 3964937, (unsigned int)NewBatchCtx);
  }
  if ( v8 < 0 )
  {
    ExtBuffer = -1;
    if ( (bidGblFlags & 2) != 0 && off_383B49120[0] )
      bidTraceW(off_383B431C0[0], 9373705, off_383B49120[0], 9154);
    goto LABEL_579;
  }
  v12 = v211;
  ExtBuffer = HandleDeferredPrepare(v211);
  Exp = ExtBuffer;
  if ( ExtBuffer == -1 )
  {
    if ( (bidGblFlags & 2) != 0 && off_383B49120[0] )
      bidTraceW(off_383B431C0[0], 9377801, off_383B49120[0], 9158);
    goto LABEL_579;
  }
  v13 = *((_DWORD *)v211 + 371);
  if ( (v13 & 0x200) != 0 && (v13 & 0x900) == 0 && !*((_DWORD *)v211 + 502) )
  {
    v14 = v5[139];
    v199[2] = 0;
    if ( v14 && (unsigned int)CheckBusy((struct tagSTMT *)v5, &v199[2]) || CheckOptions((struct tagSTMT *)v5) == -1 )
      goto LABEL_572;
    v15 = *((_QWORD *)v12 + 58);
    if ( !v15 )
      v15 = *((_QWORD *)v12 + 57);
    v16 = *(_QWORD *)(v15 + 8) >> 1;
    v17 = (const void *)(v15 + 24);
    *(_QWORD *)v233 = v16;
    v234 = (unsigned __int16 *)(v15 + 24);
    if ( !*((_QWORD *)a2 + 15) )
    {
      ExtBuffer = AllocPlex(a2, *((struct tagOBJBASE **)a2 + 8), *(_DWORD *)(*((_QWORD *)a2 + 8) + 780LL));
      if ( (ExtBuffer & 0xFFFE) != 0 )
      {
        if ( (bidGblFlags & 2) != 0 )
        {
          v18 = off_383B431C0[0];
          if ( off_383B49120[0] )
          {
            v19 = 9195;
            v20 = off_383B49120[0];
            v21 = 9415689;
LABEL_571:
            bidTraceW(v18, v21, v20, v19);
            goto LABEL_572;
          }
        }
        goto LABEL_572;
      }
      ExtBuffer = UnbindParam(a2, *(unsigned int *)(*((_QWORD *)a2 + 8) + 780LL));
      Exp = ExtBuffer;
      if ( (ExtBuffer & 0xFFFE) != 0 )
      {
        if ( (bidGblFlags & 2) != 0 )
        {
          v18 = off_383B431C0[0];
          if ( off_383B49120[0] )
          {
            v19 = 9198;
            v20 = off_383B49120[0];
            v21 = 9418761;
            goto LABEL_571;
          }
        }
LABEL_572:
        if ( !v199[2] )
          goto LABEL_579;
        goto LABEL_575;
      }
    }
    if ( (unsigned int)v16 > 0x190 )
      v22 = 2LL * (unsigned int)v16 + 512;
    else
      v22 = 1000;
    if ( CreateExtBufferEx(v219, &v217, v22, 0x80u, 1) == -1 )
      goto LABEL_559;
    v23 = 2LL * (unsigned int)v16;
    v24 = v219;
    if ( WriteToExtBufferEx(v219, &v217, v17, v23, 1) == -1 )
      goto LABEL_559;
    v25 = SubstituteECodes(0, v24, &v217);
    if ( v25 == -1 )
    {
      if ( (bidGblFlags & 2) == 0 )
        goto LABEL_53;
      if ( off_383B49120[0] )
        bidTraceW(off_383B431E8[0], 3800073, off_383B49120[0], 3711);
    }
    if ( (bidGblFlags & 2) != 0 )
    {
      if ( !v25 && (bidGblFlags & 0x40) == 0 )
        goto LABEL_54;
      v26 = 3804161;
      if ( v25 )
        v26 = 3804193;
      bidTraceW(off_383B431E8[0], v26, off_383B494E8[0], (unsigned int)v25);
    }
LABEL_53:
    if ( v25 == -1 )
      goto LABEL_559;
LABEL_54:
    if ( v7 )
    {
      memset(&v236[1], 0, 24);
      v237 = 0;
      v238 = 0;
      v236[0] = &CImpODBCIObtainParameterMetadata::`vftable';
      v241[0] = 0;
      v27 = v211;
      v239 = *((_DWORD *)v211 + 195);
      v240 = v217;
      v241[1] = a2;
      v28 = CImpODBCObtainMetadata::Initialize((CImpODBCObtainMetadata *)v236, v211);
      v195 = v28;
      if ( v28 >= 0 )
      {
        v29 = InitializeNamePool(v237, v241);
        v28 = v29;
        v195 = v29;
        if ( v29 < 0 && (bidGblFlags & 2) != 0 )
          bidTraceHR(off_383B431C0[0], 8876041, (unsigned int)v29);
      }
      else if ( (bidGblFlags & 2) != 0 && off_383B49128[0] )
      {
        bidTraceW(off_383B431C0[0], 8873001, off_383B49128[0], (unsigned int)v28);
      }
      if ( v28 < 0 )
      {
        if ( (bidGblFlags & 2) != 0 )
          bidTraceHR(off_383B431C0[0], 9436169, (unsigned int)v28);
        v236[0] = &CImpODBCIObtainParameterMetadata::`vftable';
        if ( v241[0] )
        {
          ((void (__fastcall *)(struct IMalloc *))g_pMO->lpVtbl->Free)(g_pMO);
          v241[0] = 0;
        }
LABEL_67:
        CImpODBCObtainMetadata::~CImpODBCObtainMetadata((CImpODBCObtainMetadata *)v236);
        v30 = v195;
        goto LABEL_555;
      }
      *((_WORD *)v27 + 398) |= 0x403u;
      ServerMetadata = IObtainMetadata::GetServerMetadata((IObtainMetadata *)v236, 0);
      v195 = ServerMetadata;
      if ( ServerMetadata < 0 )
      {
        if ( (bidGblFlags & 2) != 0 )
          bidTraceHR(off_383B431C0[0], 9443337, (unsigned int)ServerMetadata);
        v236[0] = &CImpODBCIObtainParameterMetadata::`vftable';
        if ( v241[0] )
        {
          ((void (__fastcall *)(struct IMalloc *))g_pMO->lpVtbl->Free)(g_pMO);
          v241[0] = 0;
        }
        goto LABEL_67;
      }
      v236[0] = &CImpODBCIObtainParameterMetadata::`vftable';
      if ( v241[0] )
      {
        ((void (__fastcall *)(struct IMalloc *))g_pMO->lpVtbl->Free)(g_pMO);
        v241[0] = 0;
      }
      CImpODBCObtainMetadata::~CImpODBCObtainMetadata((CImpODBCObtainMetadata *)v236);
LABEL_262:
      SQLFreeStmt(v5, 0);
      ExtBuffer = 0;
      v30 = v195;
      goto LABEL_555;
    }
    v207 = 0;
    v202 = 0;
    v209 = 0;
    LODWORD(v213) = 0;
    v32 = (char *)v217 + 24;
    v33 = *((_QWORD *)v217 + 1) >> 1;
    LexToken = GetLexToken(
                 (struct ext_buffer *)((char *)v217 + 24),
                 (const unsigned __int16 *)(unsigned int)v33,
                 (unsigned __int64)v199,
                 (unsigned int *)&MaxCount,
                 BufferLength);
    v35 = *(_DWORD *)v199;
    for ( i = (wchar_t *)&v32[2 * *(unsigned int *)v199];
          LexToken == 3;
          i = (wchar_t *)((char *)v37 + 2 * *(unsigned int *)v199) )
    {
      if ( *i != 40 )
        break;
      v37 = (struct tagDBC *)&i[(unsigned int)MaxCount];
      LODWORD(v33) = v33 - (v35 + MaxCount);
      LexToken = GetLexToken(
                   v37,
                   (const unsigned __int16 *)(unsigned int)v33,
                   (unsigned __int64)v199,
                   (unsigned int *)&MaxCount,
                   BufferLengtha);
      v35 = *(_DWORD *)v199;
    }
    if ( LexToken != 1 )
      goto LABEL_557;
    v38 = MaxCount;
    if ( (_DWORD)MaxCount == 6 )
    {
      if ( _wcsnicmp(L"update", i, 6u)
        && _wcsnicmp(L"select", i, 6u)
        && _wcsnicmp(L"insert", i, 6u)
        && _wcsnicmp(L"delete", i, 6u) )
      {
LABEL_557:
        v80 = -25368;
        goto LABEL_558;
      }
    }
    else if ( (_DWORD)MaxCount != 4 && (_DWORD)MaxCount != 7 || _wcsnicmp(L"execute", i, (unsigned int)MaxCount) )
    {
      goto LABEL_557;
    }
LABEL_90:
    v39 = *i | 0x20;
    LOWORD(v214) = v39;
    v40 = (struct tagDBC *)&i[v38];
    v41 = v33 - (v35 + v38);
    if ( v39 == 115 )
    {
      while ( v41 )
      {
        v42 = GetLexToken(
                v40,
                (const unsigned __int16 *)v41,
                (unsigned __int64)v199,
                (unsigned int *)&MaxCount,
                BufferLengtha);
        v43 = MaxCount;
        v44 = *(_DWORD *)v199;
        if ( v42 == 1 )
        {
          if ( (_DWORD)MaxCount == 4 && !_wcsnicmp(L"from", (const wchar_t *)v40 + *(unsigned int *)v199, 4u) )
            break;
        }
        else if ( v42 == 3 && *((_WORD *)v40 + *(unsigned int *)v199) == 63 )
        {
          goto LABEL_283;
        }
        v40 = (struct tagDBC *)((char *)v40 + 2 * v44 + 2 * v43);
        v41 -= v44 + v43;
        if ( !v41 )
          goto LABEL_283;
      }
    }
    v45 = GetLexToken(
            v40,
            (const unsigned __int16 *)v41,
            (unsigned __int64)v199,
            (unsigned int *)&MaxCount,
            BufferLengtha);
    v204 = 0;
    if ( v45 != 1 )
    {
      if ( v45 == 3 )
      {
        if ( v39 != 101 )
        {
          v46 = MaxCount;
          v47 = *(_DWORD *)v199;
          goto LABEL_130;
        }
        v47 = *(_DWORD *)v199;
        if ( *((_WORD *)v40 + *(unsigned int *)v199) != 63 )
        {
          v46 = MaxCount;
          goto LABEL_130;
        }
        v204 = 1;
        v56 = (unsigned int)(*(_DWORD *)v199 + MaxCount);
        v57 = (struct tagDBC *)((char *)v40 + 2 * v56);
        v58 = v41 - v56;
        GetLexToken(
          v57,
          (const unsigned __int16 *)v58,
          (unsigned __int64)v199,
          (unsigned int *)&MaxCount,
          BufferLengthb);
        v59 = (unsigned int)(*(_DWORD *)v199 + MaxCount);
        v40 = (struct tagDBC *)((char *)v57 + 2 * v59);
        v41 = v58 - v59;
        v45 = GetLexToken(
                v40,
                (const unsigned __int16 *)v41,
                (unsigned __int64)v199,
                (unsigned int *)&MaxCount,
                BufferLengthi);
      }
      goto LABEL_128;
    }
    v46 = MaxCount;
    if ( (_DWORD)MaxCount == 4 )
    {
      if ( v39 == 105 )
      {
        v47 = *(_DWORD *)v199;
        if ( _wcsnicmp(L"into", (const wchar_t *)v40 + *(unsigned int *)v199, 4u) )
          goto LABEL_132;
        goto LABEL_108;
      }
      if ( v39 == 115 || v39 == 100 )
      {
        v47 = *(_DWORD *)v199;
        if ( _wcsnicmp(L"from", (const wchar_t *)v40 + *(unsigned int *)v199, 4u) )
          goto LABEL_132;
LABEL_108:
        v40 = (struct tagDBC *)((char *)v40 + 2 * v47 + 8);
        v41 += -4 - v47;
        v48 = GetLexToken(
                v40,
                (const unsigned __int16 *)v41,
                (unsigned __int64)v199,
                (unsigned int *)&MaxCount,
                BufferLengthb);
        v45 = v48;
        if ( v39 == 115 && v48 == 3 )
        {
          v49 = v40;
          v47 = *(_DWORD *)v199;
          v50 = *(_DWORD *)v199;
          LODWORD(v212) = *(_DWORD *)v199;
          v46 = MaxCount;
          v51 = MaxCount;
          v220 = MaxCount;
          v52 = v41;
          v205 = v41;
          if ( *((_WORD *)v40 + *(unsigned int *)v199) == 123 )
          {
            if ( v41 - *(_DWORD *)v199 - (unsigned int)MaxCount < 3 )
              goto LABEL_283;
            v53 = *((_WORD *)v40 + *(unsigned int *)v199 + 1);
            if ( v53 != 111 && v53 != 79 )
              goto LABEL_283;
            v54 = *((_WORD *)v40 + *(unsigned int *)v199 + 2);
            if ( v54 != 106 && v54 != 74 )
              goto LABEL_283;
            if ( *((_WORD *)v40 + *(unsigned int *)v199 + 3) != 32 )
              goto LABEL_283;
            v46 = 0;
            LODWORD(MaxCount) = 0;
            v55 = 1;
            v202 = 1;
            goto LABEL_133;
          }
          while ( *((_WORD *)v49 + v50) == 40 )
          {
            ++v209;
            v49 = (struct tagDBC *)((char *)v49 + 2 * v51 + 2 * v50);
            v52 -= v51 + v50;
            v205 = v52;
            v45 = GetLexToken(v49, (const unsigned __int16 *)v52, (unsigned __int64)&v212, &v220, BufferLengthb);
            if ( v45 != 3 )
              break;
            v50 = v212;
            v51 = v220;
          }
LABEL_129:
          if ( v45 != 1 )
          {
LABEL_130:
            v55 = v202;
            if ( !v202 )
              goto LABEL_283;
            goto LABEL_133;
          }
LABEL_132:
          v55 = v202;
LABEL_133:
          v215 = (struct tagDBC *)((char *)v40 + 2 * v47);
          if ( v39 != 101 )
          {
            v60 = (struct tagDBC *)((char *)v40 + 2 * v47 + 2 * v46);
            v61 = v41 - (v47 + v46);
            v62 = GetLexToken(
                    v60,
                    (const unsigned __int16 *)v61,
                    (unsigned __int64)v199,
                    (unsigned int *)&MaxCount,
                    BufferLengthb);
            LOWORD(v212) = v62;
            v63 = v209;
            v204 = v209;
            if ( v39 == 115 )
            {
              while ( v61 )
              {
                v64 = *(_DWORD *)v199;
                if ( v55 )
                {
                  if ( *((_WORD *)v60 + *(unsigned int *)v199) == 125 )
                  {
                    v67 = MaxCount;
                    v60 = (struct tagDBC *)((char *)v60 + 2 * (unsigned int)(*(_DWORD *)v199 + MaxCount));
                    v61 -= *(_DWORD *)v199 + MaxCount;
                    goto LABEL_151;
                  }
                }
                else if ( v62 == 1 )
                {
                  if ( !v63
                    && (unsigned int)IsEndFromClause((wchar_t *)v60 + *(unsigned int *)v199, v61 - *(_DWORD *)v199) )
                  {
                    goto LABEL_150;
                  }
                }
                else if ( v62 == 3 )
                {
                  v65 = *((_WORD *)v60 + *(unsigned int *)v199);
                  if ( v65 == 40 )
                  {
                    v204 = v63 + 1;
                  }
                  else if ( v65 == 41 )
                  {
                    v204 = v63 - 1;
                  }
                }
                v66 = v64 + (unsigned int)MaxCount;
                v60 = (struct tagDBC *)((char *)v60 + 2 * v66);
                v61 -= v66;
                v62 = GetLexToken(
                        v60,
                        (const unsigned __int16 *)v61,
                        (unsigned __int64)v199,
                        (unsigned int *)&MaxCount,
                        BufferLengthc);
                LOWORD(v212) = v62;
                v63 = v204;
              }
            }
            v64 = *(_DWORD *)v199;
LABEL_150:
            v67 = MaxCount;
LABEL_151:
            v224 = (v60 - v215) >> 1;
            v205 = v61 + 1;
            v3 = v198;
            if ( *(_QWORD *)&v210[1] )
            {
              *(_QWORD *)(*(_QWORD *)&v210[1] + 8LL) = 0;
              *((_QWORD *)v216 + 1) = 0;
            }
            else
            {
              ExtBuffer = CreateExtBufferEx(v198, (struct ext_buffer **)&v210[1], 0x3E8u, 0x200u, 1);
              if ( ExtBuffer )
              {
                if ( (bidGblFlags & 2) != 0 && off_383B49120[0] )
                  bidTraceW(off_383B431C0[0], 10363913, off_383B49120[0], 10121);
                goto LABEL_559;
              }
              ExtBuffer = CreateExtBufferEx(v3, &v216, 0x3E8u, 0x200u, 1);
              if ( ExtBuffer )
              {
                if ( (bidGblFlags & 2) != 0 && off_383B49120[0] )
                  bidTraceW(off_383B431C0[0], 10366985, off_383B49120[0], 10124);
                goto LABEL_559;
              }
            }
            ExtBuffer = WriteToExtBufferEx(v3, &v216, L"group by ", 18, 1);
            if ( ExtBuffer )
            {
              if ( (bidGblFlags & 2) != 0 && off_383B49120[0] )
                bidTraceW(off_383B431C0[0], 10377225, off_383B49120[0], 10134);
              goto LABEL_559;
            }
            ExtBuffer = WriteToExtBufferEx(v3, (struct ext_buffer **)&v210[1], L"select ", 14, 1);
            if ( ExtBuffer )
            {
              if ( (bidGblFlags & 2) != 0 && off_383B49120[0] )
                bidTraceW(off_383B431C0[0], 10380297, off_383B49120[0], 10137);
              goto LABEL_559;
            }
            v68 = 1;
            v69 = 1;
            while ( v68 <= *((_DWORD *)v211 + 195) )
            {
              v203 = 0;
              v194 = v62;
              LODWORD(v193) = v67;
              v70 = v214;
              LODWORD(StrLen_or_IndPtr) = v61;
              v71 = v198;
              Exp = FindExp(
                      v198,
                      v218,
                      (const unsigned __int16 *)v60,
                      v205,
                      v60,
                      StrLen_or_IndPtr,
                      v234,
                      v233[0],
                      v214,
                      v68,
                      v64,
                      v193,
                      v194,
                      &String2,
                      v210,
                      &v227,
                      &v203);
              if ( Exp )
              {
                if ( (bidGblFlags & 2) != 0 && off_383B49120[0] )
                {
                  bidTraceW(off_383B431C0[0], 10407945, off_383B49120[0], 10164);
                  ExtBuffer = Exp;
                  v3 = v71;
                  goto LABEL_559;
                }
LABEL_193:
                ExtBuffer = Exp;
                v3 = v71;
                goto LABEL_559;
              }
              if ( v203 )
              {
                i = String2;
                LODWORD(v33) = v210[0];
                v35 = 0;
                *(_DWORD *)v199 = 0;
                v38 = 0;
                LODWORD(MaxCount) = 0;
                goto LABEL_90;
              }
              if ( v227 && v70 != 105 )
              {
                v72 = v222;
                if ( !v222 )
                {
                  v72 = (char *)SQLAllocateMemory(v71, *((unsigned int *)v211 + 195));
                  v222 = v72;
                  if ( !v72 )
                  {
                    if ( (bidGblFlags & 2) != 0 && off_383B49128[0] )
                      bidTraceW(off_383B431C0[0], 10424361, off_383B49128[0], 2147942414LL);
                    goto LABEL_556;
                  }
                }
                v72[v69 - 1] = 1;
              }
              v73 = v210[0];
              v74 = 2LL * v210[0];
              Exp = WriteToExtBufferEx(v198, (struct ext_buffer **)&v210[1], String2, v74, 1);
              if ( Exp )
              {
                if ( (bidGblFlags & 2) != 0 && off_383B49120[0] )
                {
                  bidTraceW(off_383B431C0[0], 10430473, off_383B49120[0], 10186);
                  ExtBuffer = Exp;
                  v3 = v198;
                  goto LABEL_559;
                }
LABEL_284:
                ExtBuffer = Exp;
LABEL_285:
                v3 = v198;
                goto LABEL_559;
              }
              v75 = (const unsigned __int16 *)v73;
              v76 = String2;
              GetLexToken((struct tagDBC *)String2, v75, (unsigned __int64)&v242, &v226, BufferLengthd);
              if ( _wcsnicmp(L"case", v76, 4u) || v226 != 4 )
              {
                v77 = v74;
                v71 = v198;
                Exp = WriteToExtBufferEx(v198, &v216, v76, v77, 1);
                if ( Exp )
                {
                  if ( (bidGblFlags & 2) != 0 && off_383B49120[0] )
                  {
                    bidTraceW(off_383B431C0[0], 10443785, off_383B49120[0], 10199);
                    ExtBuffer = Exp;
                    v3 = v71;
                    goto LABEL_559;
                  }
                  goto LABEL_193;
                }
                Exp = WriteCharToExtBufferEx(v71, &v216, 0x2Cu, 1u, BufferLengthf);
                if ( Exp )
                {
                  if ( (bidGblFlags & 2) != 0 && off_383B49120[0] )
                    bidTraceW(off_383B431C0[0], 10447881, off_383B49120[0], 10203);
                  goto LABEL_193;
                }
              }
              else
              {
                LODWORD(v213) = 1;
                v71 = v198;
              }
              Exp = WriteCharToExtBufferEx(v71, (struct ext_buffer **)&v210[1], 0x2Cu, 1u, BufferLengthe);
              if ( Exp )
              {
                if ( (bidGblFlags & 2) != 0 && off_383B49120[0] )
                {
                  bidTraceW(off_383B431C0[0], 10451977, off_383B49120[0], 10207);
                  ExtBuffer = Exp;
                  v3 = v198;
                  goto LABEL_559;
                }
                goto LABEL_284;
              }
              if ( v210[0] == 1 && *v76 == 42 )
                goto LABEL_204;
              ++v68;
              ++v69;
              v62 = v212;
              v67 = MaxCount;
            }
            v76 = String2;
            v71 = v198;
LABEL_204:
            *(_QWORD *)(*(_QWORD *)&v210[1] + 8LL) -= 2LL;
            ExtBuffer = WriteToExtBufferEx(v71, (struct ext_buffer **)&v210[1], L" from ", 12, 1);
            if ( ExtBuffer )
            {
              if ( (bidGblFlags & 2) == 0 || !off_383B49120[0] )
                goto LABEL_285;
              bidTraceW(off_383B431C0[0], 10461193, off_383B49120[0], 10216);
              v3 = v198;
              goto LABEL_559;
            }
            ExtBuffer = WriteToExtBufferEx(v71, (struct ext_buffer **)&v210[1], v215, 2LL * (unsigned int)v224, 1);
            if ( ExtBuffer )
            {
              if ( (bidGblFlags & 2) == 0 || !off_383B49120[0] )
                goto LABEL_285;
              bidTraceW(off_383B431C0[0], 10464265, off_383B49120[0], 10219);
              v3 = v198;
              goto LABEL_559;
            }
            if ( (_DWORD)v213 )
            {
              v78 = v216;
              *((_QWORD *)v216 + 1) -= 2LL;
              ExtBuffer = WriteToExtBufferEx(
                            v71,
                            (struct ext_buffer **)&v210[1],
                            (char *)v78 + 24,
                            *((_QWORD *)v78 + 1),
                            1);
              if ( ExtBuffer )
              {
                if ( (bidGblFlags & 2) == 0 || !off_383B49120[0] )
                  goto LABEL_285;
                bidTraceW(off_383B431C0[0], 10473481, off_383B49120[0], 10228);
                v3 = v198;
                goto LABEL_559;
              }
            }
            v79 = v211;
            ExtBuffer = GetMetadataQuery(
                          v71,
                          v211,
                          (unsigned __int16 *)(*(_QWORD *)&v210[1] + 24LL),
                          *(_DWORD *)(*(_QWORD *)&v210[1] + 8LL) >> 1,
                          &v223,
                          &v225);
            if ( ExtBuffer )
            {
              if ( (bidGblFlags & 2) == 0 || !off_383B49120[0] )
                goto LABEL_285;
              bidTraceW(off_383B431C0[0], 10477577, off_383B49120[0], 10232);
              v3 = v198;
LABEL_559:
              if ( v217 )
                ((void (__fastcall *)(struct IMalloc *))g_pMO->lpVtbl->Free)(g_pMO);
              if ( *(_QWORD *)&v210[1] )
                ((void (__fastcall *)(struct IMalloc *))g_pMO->lpVtbl->Free)(g_pMO);
              if ( v216 )
                ((void (__fastcall *)(struct IMalloc *))g_pMO->lpVtbl->Free)(g_pMO);
              if ( v232 )
                ((void (__fastcall *)(struct IMalloc *))g_pMO->lpVtbl->Free)(g_pMO);
              if ( v223 )
                ((void (__fastcall *)(struct IMalloc *))g_pMO->lpVtbl->Free)(g_pMO);
              if ( v222 )
                ((void (__fastcall *)(struct IMalloc *))g_pMO->lpVtbl->Free)(g_pMO);
              goto LABEL_572;
            }
            if ( v223 )
            {
              v81 = (struct tagOBJBASE *)StatementHandle;
              ExtBuffer = ExecImmediate((struct tagSTMT *)StatementHandle, v223, v225, *((_DWORD *)v79 + 369), 1);
              if ( ExtBuffer == -1 )
              {
                v3 = v198;
                XferErrors(v198, v81);
                Cancel(v81, 0);
                DisableFmtOnlyMode(v219, 0);
                goto LABEL_559;
              }
              v82 = v210[0];
              if ( v210[0] == 1 && *v76 == 42 )
              {
                v83 = v64 + (unsigned int)MaxCount;
                v84 = (struct tagDBC *)((char *)v60 + 2 * v83);
                v85 = v61 - v83;
                GetLexToken(
                  v84,
                  (const unsigned __int16 *)v85,
                  (unsigned __int64)v199,
                  (unsigned int *)&MaxCount,
                  BufferLengthg);
                v60 = (struct tagDBC *)((char *)v84 + 2 * (unsigned int)(*(_DWORD *)v199 + MaxCount));
                v61 = v85 - (*(_DWORD *)v199 + MaxCount);
                v82 = v210[0];
              }
              v86 = 1;
              v87 = 1;
              v88 = v204;
              v89 = StatementHandle;
              if ( *(_QWORD *)(*((_QWORD *)StatementHandle + 37) + 8LL) )
              {
                while ( 1 )
                {
                  v90 = 0;
                  if ( v82 == 1 && *String2 == 42 )
                  {
                    while ( 1 )
                    {
                      if ( GetLexToken(
                             v60,
                             (const unsigned __int16 *)v61,
                             (unsigned __int64)v199,
                             (unsigned int *)&MaxCount,
                             BufferLengthg) == 3 )
                      {
                        v91 = *((_WORD *)v60 + *(unsigned int *)v199);
                        if ( v91 != 40 )
                        {
                          if ( v91 == 41 )
                          {
                            if ( !v88 )
                              goto LABEL_241;
                          }
                          else
                          {
                            if ( v91 == 44 && !v88 )
                            {
LABEL_241:
                              v60 = (struct tagDBC *)((char *)v60 + 2 * (unsigned int)(MaxCount + *(_DWORD *)v199));
                              v61 -= MaxCount + *(_DWORD *)v199;
                              v89 = StatementHandle;
                              goto LABEL_243;
                            }
                            if ( v91 == 63 )
                              ++v90;
                          }
                        }
                      }
                      v60 = (struct tagDBC *)((char *)v60 + 2 * (unsigned int)(MaxCount + *(_DWORD *)v199));
                      v61 -= MaxCount + *(_DWORD *)v199;
                      if ( !v61 )
                        goto LABEL_241;
                    }
                  }
                  v90 = 1;
LABEL_243:
                  v92 = ParamInfoFromColInfo(
                          (struct paraminfoTag *)v251,
                          (struct tagCOLUMN_INFO *)((v86 - 1) * *(_QWORD *)(*((_QWORD *)v89 + 37) + 24LL)
                                                  + 32
                                                  + *((_QWORD *)v89 + 37)),
                          v211,
                          v218,
                          *((struct ext_buffer **)v89 + 177));
                  v30 = v92;
                  v195 = v92;
                  if ( v92 < 0 )
                    break;
                  if ( v222 && v222[v87 - 1] && (LOWORD(v251[1]) == 0xFFFF || LOWORD(v251[1]) == 0xFFF6) )
                  {
                    v93 = -9;
                    if ( LOWORD(v251[1]) == 0xFFFF )
                      v93 = 12;
                    LOWORD(v251[1]) = v93;
                    *(_QWORD *)&v251[0] = 8000;
                  }
                  if ( v90 )
                  {
                    while ( 1 )
                    {
                      v94 = PlAddNewIEx(v218, *((struct pl **)v218 + 15), v87++, v251, (int)BufferLengthg);
                      *((_QWORD *)v218 + 15) = v94;
                      if ( !v94 )
                        break;
                      if ( !--v90 )
                        goto LABEL_254;
                    }
                    ExtBuffer = -1;
                    if ( (bidGblFlags & 2) != 0 && off_383B49120[0] )
                      bidTraceW(off_383B431C0[0], 10568713, off_383B49120[0], 10321);
                    goto LABEL_553;
                  }
LABEL_254:
                  ++v86;
                  v89 = StatementHandle;
                  if ( v86 > *(_QWORD *)(*((_QWORD *)StatementHandle + 37) + 8LL) )
                    goto LABEL_261;
                  v82 = v210[0];
                }
                if ( (bidGblFlags & 2) == 0 )
                  goto LABEL_554;
                bidTraceHR(off_383B431C0[0], 10554377, (unsigned int)v92);
                goto LABEL_553;
              }
LABEL_261:
              v3 = v198;
              v5 = (struct BATCHCTX **)v89;
              goto LABEL_262;
            }
            v80 = -25400;
            v3 = v198;
LABEL_558:
            v199[2] = v80;
            goto LABEL_559;
          }
          memset(v235, 0, 32);
          v252[0] = -1;
          *(_QWORD *)&v252[1] = 0;
          v252[3] = 0;
          LODWORD(v214) = 1;
          v95 = 0;
          v243 = 0;
          v244 = 0;
          v245 = 0;
          v246 = 0;
          v247 = 0;
          v248 = 0;
          v249 = 0;
          v96 = v41 - v47;
          v202 = v41 - v47;
          v97 = 0;
          v98 = v215;
          do
          {
            v99 = *(_WORD *)v98;
            if ( *(_WORD *)v98 == 46 )
            {
              v252[v97] = -1;
              v205 = 0;
            }
            else
            {
              if ( !(unsigned int)GetIdentifier((const unsigned __int16 *)v98, v46, &v205) )
                goto LABEL_283;
              if ( v99 == 34 || v99 == 91 )
              {
                v95 = 1;
                v235[v97] = (unsigned __int16 *)((char *)v98 + 2);
                v100 = v205;
                v252[v97] = v205 - 2;
              }
              else
              {
                v235[v97] = (unsigned __int16 *)v98;
                v100 = v205;
                v252[v97] = v205;
              }
              v98 = (struct tagDBC *)((char *)v98 + 2 * v100);
              v215 = v98;
              v46 -= v100;
              LODWORD(MaxCount) = v46;
              v96 -= v100;
              v202 = v96;
            }
            if ( !v46 )
              break;
            if ( *(_WORD *)v98 == 46 )
            {
              v98 = (struct tagDBC *)((char *)v98 + 2);
              v215 = v98;
              LODWORD(MaxCount) = --v46;
              v202 = --v96;
            }
            v95 = 0;
            ++v97;
          }
          while ( v97 <= 3 );
          if ( v97 == 4 )
          {
LABEL_283:
            v199[2] = -25400;
            goto LABEL_284;
          }
          v101 = (const unsigned __int16 *)((char *)v98 - 2);
          if ( *((_WORD *)v98 - 1) == 59
            && GetLexToken(
                 v98,
                 (const unsigned __int16 *)v41,
                 (unsigned __int64)v199,
                 (unsigned int *)&MaxCount,
                 BufferLengthb) == 2 )
          {
            v102 = MaxCount;
            v103 = *(_DWORD *)v199;
            if ( v95 )
            {
              v104 = (unsigned int)v252[v97];
              v105 = (unsigned int)(v104 + *(_DWORD *)v199 + MaxCount + 2);
              v224 = v105;
              v106 = (unsigned __int16 *)SQLAllocateMemory(v198, 2 * v105);
              v232 = v106;
              if ( !v106 )
              {
                if ( (bidGblFlags & 2) != 0 && off_383B49128[0] )
                  bidTraceW(off_383B431C0[0], 9727017, off_383B49128[0], 2147942414LL);
                goto LABEL_556;
              }
              v107 = StringCchCopyNExW(v106, v105, v235[v97], v104, 0, &v224, v192);
              v30 = v107;
              v195 = v107;
              if ( v107 < 0 )
              {
                if ( (bidGblFlags & 2) != 0 )
                {
                  v108 = 9730057;
                  goto LABEL_297;
                }
                goto LABEL_341;
              }
              v107 = StringCchCopyNW(&v106[v104], v224, v101, v103 + v102 + 1);
              v30 = v107;
              v195 = v107;
              if ( v107 < 0 )
              {
                if ( (bidGblFlags & 2) != 0 )
                {
                  v108 = 9733129;
                  goto LABEL_297;
                }
                goto LABEL_341;
              }
              v235[v97] = v106;
            }
            v252[v97] += v103 + v102 + 1;
          }
          v110 = v256;
          v213 = v256;
          if ( v97 == 2 )
          {
            if ( v252[0] == -1 )
              goto LABEL_372;
            v111 = 0;
            v112 = v252[0];
            v113 = v256;
            v114 = 540;
            v30 = 0;
            if ( v252[0] >= 0x7FFFFFFFuLL )
              v30 = -2147024809;
            v195 = v30;
            if ( v30 < 0 )
            {
              v256[0] = 0;
            }
            else
            {
              v115 = 540;
              v116 = v256;
              v195 = 0;
              v117 = 0;
              v118 = (char *)v235[0] - (char *)v256;
              while ( v115 + v112 - 540 )
              {
                v119 = *(unsigned __int16 *)((char *)v116 + v118);
                if ( !v119 )
                  break;
                *v116++ = v119;
                ++v117;
                if ( !--v115 )
                {
                  --v116;
                  --v117;
                  v30 = -2147024774;
                  v195 = -2147024774;
                  goto LABEL_316;
                }
              }
              v30 = 0;
LABEL_316:
              *v116 = 0;
              v113 = &v256[v117];
              v114 = 540 - v117;
              if ( v30 >= 0 )
                goto LABEL_320;
            }
            if ( v30 != -2147024774 )
            {
LABEL_321:
              if ( v30 < 0 )
              {
                if ( (bidGblFlags & 2) != 0 )
                {
                  v109 = (unsigned int)v30;
                  v108 = 9759753;
                  goto LABEL_298;
                }
LABEL_341:
                ExtBuffer = Exp;
                goto LABEL_342;
              }
              if ( v111 <= 1 )
              {
                ExtBuffer = -1;
                if ( (bidGblFlags & 2) != 0 )
                {
                  if ( off_383B49120[0] )
                  {
                    bidTraceW(off_383B431C0[0], 9769993, off_383B49120[0], 9541);
                    goto LABEL_339;
                  }
LABEL_340:
                  v3 = v198;
                  goto LABEL_555;
                }
LABEL_342:
                v3 = v198;
                goto LABEL_555;
              }
              v30 = 0;
              v195 = 0;
              if ( v111 > 0x7FFFFFFF )
              {
                v30 = -2147024809;
                v195 = -2147024809;
              }
              if ( v30 < 0 )
                goto LABEL_334;
              v120 = v110;
              v30 = 0;
              v195 = 0;
              v121 = 0;
              v122 = 2147483646 - v111;
              do
              {
                if ( !(v122 + v111) )
                  goto LABEL_333;
                v123 = *(unsigned __int16 *)((char *)v120 + (char *)L"." - (char *)v110);
                if ( !v123 )
                  goto LABEL_333;
                *v120++ = v123;
                ++v121;
                --v111;
              }
              while ( v111 );
              --v120;
              --v121;
              v30 = -2147024774;
              v195 = -2147024774;
LABEL_333:
              *v120 = 0;
              v213 = &v110[v121];
              if ( v30 < 0 )
              {
LABEL_334:
                if ( (bidGblFlags & 2) != 0 )
                {
                  v109 = (unsigned int)v30;
                  v108 = 9765897;
                  goto LABEL_298;
                }
                goto LABEL_341;
              }
LABEL_372:
              if ( !*((_QWORD *)v219 + 8)
                || (v134 = *((_QWORD *)v219 + 8), *(_BYTE *)(v134 + 1246) < 0xAu)
                || (*(_BYTE *)(v134 + 400) & 2) != 0 )
              {
                if ( *((_QWORD *)v219 + 8) && *(_BYTE *)(*((_QWORD *)v219 + 8) + 1246LL) >= 9u )
                  v135 = StringCchCopyW(v213, 540 - (v213 - v256), off_383B26020);
                else
                  v135 = StringCchPrintfW(v213, 540 - (v213 - v256), L".%s", off_383B25F60);
              }
              else
              {
                v135 = StringCchCopyW(v213, 540 - (v213 - v256), off_383B26128);
              }
              v30 = v135;
              v195 = v135;
              if ( v135 < 0 )
              {
                if ( (bidGblFlags & 2) == 0 )
                  goto LABEL_371;
                v109 = (unsigned int)v135;
                v108 = 9829385;
LABEL_298:
                bidTraceHR(off_383B431C0[0], v108, v109);
LABEL_299:
                ExtBuffer = Exp;
                goto LABEL_553;
              }
              v136 = -1;
              do
                ++v136;
              while ( v256[v136] );
              v137 = (struct tagSTMT *)StatementHandle;
              if ( (int)AddRpcCmdFromStmt(v231, (struct tagSTMT *)StatementHandle, v256, v136, 0, (int)StrLen_or_IndPtr) < 0 )
                goto LABEL_299;
              v139 = v211;
              v140 = *((_QWORD *)v211 + 14);
              if ( *(_QWORD *)(v140 + 8360) )
              {
                LODWORD(v244) = *(_DWORD *)(v140 + 9012);
                v141 = *(_BYTE *)(v140 + 9016);
              }
              else
              {
                v141 = 0;
                LODWORD(v244) = 0;
              }
              BYTE4(v244) = v141;
              v142 = (int)v97;
              if ( (v97 & 0x80000000) == 0LL )
              {
                v143 = 3;
                while ( v143 )
                {
                  v144 = v252[v142];
                  v145 = 0;
                  if ( v144 == -1 )
                  {
                    v146 = 0;
                    v145 = 256;
                  }
                  else
                  {
                    v146 = 2 * v144;
                  }
                  LOBYTE(v138) = -25;
                  if ( (*(int (__fastcall **)(_QWORD *, _QWORD, _QWORD, __int64, _QWORD, __int64, unsigned __int16 *, __int64 *))(**((_QWORD **)v137 + 138) + 48LL))(
                         *((_QWORD **)v137 + 138),
                         0,
                         v145,
                         v138,
                         v146,
                         510,
                         v235[v142],
                         &v243) < 0 )
                    goto LABEL_299;
                  --v143;
                  if ( --v142 < 0 )
                    break;
                }
              }
              if ( (*(_BYTE *)(*((_QWORD *)v139 + 14) + 10112LL) & 4) == 0 )
              {
                v206[0] = 3;
                LOBYTE(v138) = 48;
                if ( (*(int (__fastcall **)(_QWORD *, const wchar_t *, _QWORD, __int64, __int64, __int64, char *, _QWORD))(**((_QWORD **)v137 + 138) + 48LL))(
                       *((_QWORD **)v137 + 138),
                       L"@ODBCVer",
                       0,
                       v138,
                       1,
                       1,
                       v206,
                       0) < 0 )
                  goto LABEL_299;
              }
              ExtBuffer = ExecRPCImmediate(v137, 0, *((_DWORD *)v139 + 369), 0, 0);
              if ( ExtBuffer )
              {
                v174 = v207;
                goto LABEL_543;
              }
              v147 = v204;
              if ( !v204 )
              {
                ExtBuffer = SQLFetch(v137);
                if ( ExtBuffer )
                  goto LABEL_542;
                v207 = 1;
              }
              ExtBuffer = SQLFetch(v137);
              v148 = 1;
              if ( !ExtBuffer )
              {
                while ( 1 )
                {
                  v149 = v202;
                  if ( !v202 )
                  {
                    v137 = (struct tagSTMT *)StatementHandle;
                    v174 = v207;
                    goto LABEL_543;
                  }
                  v150 = 0;
                  v151 = 0;
                  if ( v147 )
                  {
                    v204 = 0;
                    goto LABEL_424;
                  }
                  v152 = v215;
                  while ( GetLexToken(
                            v152,
                            (const unsigned __int16 *)v149,
                            (unsigned __int64)v199,
                            (unsigned int *)&MaxCount,
                            BufferLengthh) != 3 )
                  {
LABEL_417:
                    v152 = (struct tagDBC *)((char *)v152 + 2 * (unsigned int)(*(_DWORD *)v199 + MaxCount));
                    v215 = v152;
                    v149 -= *(_DWORD *)v199 + MaxCount;
                    v202 = v149;
                    if ( !v149 )
                      goto LABEL_421;
                  }
                  v153 = *((_WORD *)v152 + *(unsigned int *)v199);
                  if ( v153 == 40 )
                    break;
                  if ( v153 == 41 )
                  {
                    if ( !v151 )
                      goto LABEL_419;
                    --v151;
                    goto LABEL_417;
                  }
                  if ( v153 != 44 || v151 )
                  {
                    if ( v153 == 63 )
                      v150 = 1;
                    goto LABEL_417;
                  }
LABEL_419:
                  if ( v149 )
                  {
                    v215 = (struct tagDBC *)((char *)v152 + 2 * (unsigned int)(*(_DWORD *)v199 + MaxCount));
                    v202 = v149 - (*(_DWORD *)v199 + MaxCount);
                  }
LABEL_421:
                  if ( !v150 )
                    goto LABEL_526;
LABEL_424:
                  v207 = 1;
                  memset(v251, 0, sizeof(v251));
                  LOWORD(v251[4]) = 1;
                  WORD1(v251[5]) = 1;
                  TargetValue[0] = 0;
                  v154 = StatementHandle;
                  if ( (SQLGetData(StatementHandle, 4u, -8, TargetValue, 260, &v200) & 0xFFFE) != 0 )
                    goto LABEL_553;
                  v155 = v200;
                  if ( v200 == -1 )
                  {
                    WORD3(v251[5]) = 0;
                    DWORD2(v251[5]) = 0;
                    v159 = v218;
                    goto LABEL_436;
                  }
                  if ( TargetValue[0] != 64 )
                  {
                    memset(v255, 0, 258);
                    v156 = 129;
                    v157 = v255;
                    do
                    {
                      if ( v156 == -2147483517 )
                        goto LABEL_432;
                      v158 = *(v157 - 136);
                      if ( !v158 )
                        goto LABEL_432;
                      *v157++ = v158;
                      --v156;
                    }
                    while ( v156 );
                    --v157;
LABEL_432:
                    *v157 = 0;
                    StringCchPrintfW(TargetValue, 0x82u, L"@%s", v255);
                    v155 = v200 + 2;
                    v200 += 2LL;
                  }
                  WORD3(v251[5]) = v155 >> 1;
                  v159 = v218;
                  if ( (int)AddToNamePool(
                              v211,
                              (struct ext_buffer **)v218 + 13,
                              TargetValue,
                              WORD3(v251[5]),
                              (unsigned int *)&v251[5] + 2) < 0 )
                  {
                    WORD3(v251[5]) = 0;
                    DWORD2(v251[5]) = 0;
                    ExtBuffer = -1;
                    if ( (bidGblFlags & 2) != 0 )
                    {
                      if ( !off_383B49120[0] )
                        goto LABEL_539;
                      bidTraceW(off_383B431C0[0], 9992201, off_383B49120[0], 9758);
                      v30 = v195;
                      v3 = v198;
                      goto LABEL_555;
                    }
LABEL_339:
                    v30 = v195;
                    goto LABEL_340;
                  }
LABEL_436:
                  if ( (SQLGetData(v154, 5u, -15, &v251[4], 2, &v200) & 0xFFFE) != 0 )
                    goto LABEL_539;
                  v160 = v251[4];
                  if ( !LOWORD(v251[4]) )
                  {
                    v160 = 1;
                    LOWORD(v251[4]) = 1;
                    goto LABEL_448;
                  }
                  if ( LOWORD(v251[4]) == 1
                    || LOWORD(v251[4]) == 2
                    || LOWORD(v251[4]) == 8
                    || LOWORD(v251[4]) == 4
                    || LOWORD(v251[4]) == 16
                    || LOWORD(v251[4]) == 5 )
                  {
                    if ( LOWORD(v251[4]) == 5 )
                    {
                      v160 = 4;
                      LOWORD(v251[4]) = 4;
                    }
LABEL_448:
                    if ( (v251[4] & 0xA) != 0 )
                    {
                      v160 = 2;
                    }
                    else if ( (v251[4] & 0x14) != 0 )
                    {
                      v160 = 4;
                    }
                    WORD3(v251[1]) |= v160;
                    if ( (SQLGetData(v154, 6u, -15, &v251[1], 0, &v200) & 0xFFFE) != 0 )
                      goto LABEL_539;
                    if ( LOWORD(v251[1]) != 0xFF69 && LOWORD(v251[1]) != 0xFF67 )
                      goto LABEL_461;
                    v209 = 0;
                    if ( (SQLGetData(v154, 7u, -8, v253, 258, &v200) & 0xFFFE) != 0
                      || v200 == -1
                      || (int)AddToNamePool(
                                (struct tagOBJBASE *)v154,
                                (struct ext_buffer **)v159 + 13,
                                v253,
                                (unsigned __int64)v200 >> 1,
                                &v209) < 0 )
                    {
                      goto LABEL_539;
                    }
                    if ( LOWORD(v251[1]) == 0xFF69 )
                    {
                      DWORD2(v251[2]) = v209;
                      BYTE11(v251[1]) = (unsigned __int64)v200 >> 1;
                    }
                    else
                    {
                      DWORD2(v251[3]) = v209;
                      BYTE4(v251[3]) = (unsigned __int64)v200 >> 1;
                    }
LABEL_461:
                    if ( (SQLGetData(v154, 8u, -18, v251, 0, &v200) & 0xFFFE) != 0 )
                      goto LABEL_539;
                    if ( (SLOWORD(v251[1]) <= -8 && SLOWORD(v251[1]) >= -10 || LOWORD(v251[1]) == 15)
                      && *(_QWORD *)&v251[0] )
                    {
                      *(_QWORD *)&v251[0] *= 2LL;
                    }
                    if ( (SQLGetData(v154, 0xAu, -15, (char *)&v251[1] + 2, 0, &v200) & 0xFFFE) != 0
                      || (SQLGetData(v154, 0xCu, -15, (char *)&v251[5] + 2, 0, 0) & 0xFFFE) != 0
                      || (SQLGetData(v154, 0x11u, -18, (char *)v251 + 8, 0, &v200) & 0xFFFE) != 0 )
                    {
                      goto LABEL_539;
                    }
                    v161 = *((_QWORD *)&v251[0] + 1);
                    if ( !v200 )
                      v161 = 0;
                    *((_QWORD *)&v251[0] + 1) = v161;
                    if ( (unsigned __int16)(LOWORD(v251[1]) - 91) <= 2u )
                    {
                      LOWORD(v251[1]) -= 82;
                      goto LABEL_512;
                    }
                    switch ( LOWORD(v251[1]) )
                    {
                      case 8:
                        LOWORD(v251[1]) = 6;
                        break;
                      case 0xFF6A:
                        LOWORD(v251[1]) = 13;
                        HIDWORD(v251[3]) = 1;
                        *((_QWORD *)&v251[0] + 1) = 8000;
                        *(_QWORD *)&v251[0] = 8000;
                        break;
                      case 0xFF69:
                      case 0xFF68:
                      case 0xFF67:
                        ColumnCount[0] = 0;
                        if ( (SQLNumResultCols(v154, ColumnCount) & 0xFFFE) != 0 )
                          goto LABEL_539;
                        if ( !*((_QWORD *)v219 + 8)
                          || (v162 = *((_QWORD *)v219 + 8), *(_BYTE *)(v162 + 1246) < 0xAu)
                          || (*(_BYTE *)(v162 + 400) & 2) != 0 )
                        {
                          v163 = ColumnCount[0] - 6;
                          v164 = ColumnCount[0] - 5;
                        }
                        else
                        {
                          v163 = ColumnCount[0] - 8;
                          v164 = ColumnCount[0] - 7;
                        }
                        v253[0] = 0;
                        if ( (SQLGetData(v154, v163, -8, v253, 258, &v200) & 0xFFFE) != 0 )
                          goto LABEL_539;
                        if ( v200 == -1 )
                          goto LABEL_539;
                        if ( (int)AddToNamePool(
                                    (struct tagOBJBASE *)v154,
                                    (struct ext_buffer **)v159 + 13,
                                    v253,
                                    (unsigned __int64)v200 >> 1,
                                    (unsigned int *)&v251[2]) < 0 )
                          goto LABEL_539;
                        BYTE9(v251[1]) = (unsigned __int64)v200 >> 1;
                        v253[0] = 0;
                        if ( (SQLGetData(v154, v164, -8, v253, 258, &v200) & 0xFFFE) != 0
                          || v200 == -1
                          || (int)AddToNamePool(
                                    (struct tagOBJBASE *)v154,
                                    (struct ext_buffer **)v159 + 13,
                                    v253,
                                    (unsigned __int64)v200 >> 1,
                                    (unsigned int *)&v251[2] + 1) < 0 )
                        {
                          goto LABEL_539;
                        }
                        BYTE10(v251[1]) = (unsigned __int64)v200 >> 1;
                        if ( LOWORD(v251[1]) != 0xFF69 )
                        {
                          if ( LOWORD(v251[1]) != 0xFF68 )
                          {
                            LOWORD(v251[1]) = 16;
                            v251[0] = 0u;
                            break;
                          }
                          v253[0] = 0;
                          if ( (SQLGetData(v154, ColumnCount[0] - 1, -8, v253, 258, &v200) & 0xFFFE) == 0
                            && v200 != -1
                            && (int)AddToNamePool(
                                      (struct tagOBJBASE *)v154,
                                      (struct ext_buffer **)v159 + 13,
                                      v253,
                                      (unsigned __int64)v200 >> 1,
                                      (unsigned int *)&v251[3]) >= 0 )
                          {
                            HIWORD(v251[1]) = (unsigned __int8)((unsigned __int64)v200 >> 1);
                            LOWORD(v251[1]) = 15;
                            v251[0] = 0u;
                            break;
                          }
                          goto LABEL_539;
                        }
                        if ( (SQLGetData(v154, ColumnCount[0] - 4, -8, 0, 0, &v200) & 0xFFFE) != 0
                          || v200 == -1
                          || v200 > 4130 )
                        {
                          goto LABEL_539;
                        }
                        if ( (v200 & 0xFFFFFFFFFFFFFFFEuLL) < 0x102 )
                        {
                          v165 = v253;
                          v166 = 258;
                          v253[0] = 0;
                          goto LABEL_500;
                        }
                        v166 = v200 + 2;
                        v165 = (unsigned __int16 *)SQLAllocateMemory((struct tagOBJBASE *)StatementHandle, v200 + 2);
                        if ( v165 )
                        {
LABEL_500:
                          BufferLengthj = v166;
                          v167 = (struct tagOBJBASE *)StatementHandle;
                          if ( (SQLGetData(StatementHandle, ColumnCount[0] - 4, -8, v165, BufferLengthj, &v200) & 0xFFFE) == 0 )
                          {
                            if ( (int)AddToNamePool(
                                        v167,
                                        (struct ext_buffer **)v159 + 13,
                                        v165,
                                        (unsigned __int64)v200 >> 1,
                                        (unsigned int *)&v251[2] + 3) >= 0 )
                            {
                              WORD6(v251[1]) = (unsigned __int64)v200 >> 1;
                              if ( v165 != v253 && v165 )
                                ((void (__fastcall *)(struct IMalloc *, unsigned __int16 *))g_pMO->lpVtbl->Free)(
                                  g_pMO,
                                  v165);
                              LOWORD(v251[1]) = 14;
                              break;
                            }
                            if ( v165 != v253 && v165 )
                            {
                              ((void (__fastcall *)(struct IMalloc *, unsigned __int16 *))g_pMO->lpVtbl->Free)(
                                g_pMO,
                                v165);
                              goto LABEL_553;
                            }
                          }
LABEL_539:
                          v30 = v195;
                          v3 = v198;
LABEL_555:
                          if ( v30 < 0 )
                            goto LABEL_556;
                          goto LABEL_559;
                        }
                        if ( (bidGblFlags & 2) != 0 && off_383B49128[0] )
                          bidTraceW(off_383B431C0[0], 10183721, off_383B49128[0], 2147942414LL);
LABEL_556:
                        ExtBuffer = -1;
                        v3 = v198;
                        goto LABEL_559;
                    }
LABEL_512:
                    v168 = *((_QWORD *)v159 + 15);
                    if ( v168 )
                    {
                      v169 = v214;
                      v170 = (unsigned int)v214;
                      if ( (unsigned __int64)(unsigned int)v214 <= *(_QWORD *)(v168 + 8) )
                      {
                        v171 = *(_QWORD *)(v168 + 24) * (v148 - 1) + v168 + 32;
                        if ( v171 )
                        {
                          if ( *(_WORD *)(v171 + 86) )
                          {
                            if ( (unsigned __int64)(unsigned int)v214 <= *(_QWORD *)(*((_QWORD *)v211 + 55) + 8LL) )
                            {
                              v172 = (unsigned int)v214 - 1LL;
                              while ( 1 )
                              {
                                v173 = *((_QWORD *)v159 + 15) + v172 * *(_QWORD *)(*((_QWORD *)v159 + 15) + 24LL);
                                if ( !_wcsicmp(
                                        (const wchar_t *)(*(unsigned int *)(v173 + 120) + 24LL + *((_QWORD *)v159 + 13)),
                                        (const wchar_t *)(*((_QWORD *)v159 + 13) + DWORD2(v251[5]) + 24LL)) )
                                  break;
                                ++v170;
                                ++v172;
                                if ( v170 > *(_QWORD *)(*((_QWORD *)v211 + 55) + 8LL) )
                                  goto LABEL_522;
                              }
                              *(_OWORD *)(v173 + 32) = v251[0];
                              *(_OWORD *)(v173 + 48) = v251[1];
                              *(_OWORD *)(v173 + 64) = v251[2];
                              *(_OWORD *)(v173 + 80) = v251[3];
                              *(_OWORD *)(v173 + 96) = v251[4];
                              *(_OWORD *)(v173 + 112) = v251[5];
                              *(_OWORD *)(v173 + 128) = v251[6];
                            }
LABEL_522:
                            if ( v170 <= *(_QWORD *)(*((_QWORD *)v211 + 55) + 8LL) )
                              goto LABEL_526;
                            v174 = 0;
                            v137 = (struct tagSTMT *)StatementHandle;
LABEL_543:
                            if ( ExtBuffer == -1 )
                            {
                              v3 = v198;
                              XferErrors(v198, v137);
                              SQLFreeStmt(v137, 0);
                              ExtBuffer = -1;
                              if ( (bidGblFlags & 2) != 0 && off_383B49120[0] )
                                bidTraceW(off_383B431C0[0], 10296329, off_383B49120[0], 10055);
                              v30 = v195;
                              goto LABEL_555;
                            }
                            if ( v174 )
                            {
                              SQLFreeStmt(v137, 0);
                              ExtBuffer = 0;
                            }
                            else
                            {
                              v199[2] = -25368;
                              SQLFreeStmt(v137, 0);
                              ExtBuffer = -1;
                              if ( (bidGblFlags & 2) != 0 && off_383B49120[0] )
                                bidTraceW(off_383B431C0[0], 10303497, off_383B49120[0], 10062);
                            }
LABEL_553:
                            v30 = v195;
LABEL_554:
                            v3 = v198;
                            goto LABEL_555;
                          }
                        }
                      }
                    }
                    else
                    {
                      v169 = v214;
                    }
                    LODWORD(v214) = v169 + 1;
                    ++v148;
                    *((_QWORD *)v159 + 15) = PlAddNewIEx(v159, (struct pl *)v168, v169, v251, (int)BufferLengthh);
                  }
LABEL_526:
                  ExtBuffer = SQLFetch(StatementHandle);
                  if ( ExtBuffer )
                    goto LABEL_538;
                  v147 = v204;
                }
                ++v151;
                goto LABEL_417;
              }
LABEL_538:
              v137 = (struct tagSTMT *)StatementHandle;
LABEL_542:
              v174 = v207;
              goto LABEL_543;
            }
LABEL_320:
            v110 = v113;
            v213 = v113;
            v111 = v114;
            goto LABEL_321;
          }
          if ( v97 != 3 )
            goto LABEL_372;
          v124 = 0;
          v125 = 0;
          v126 = v235;
          v127 = v252;
          while ( 1 )
          {
            if ( *v127 != -1 )
            {
              v107 = StringCchCopyNExW(v110, 540 - (v110 - v256), *v126, (unsigned int)*v127, &v213, 0, v192);
              v30 = v107;
              v195 = v107;
              if ( v107 < 0 )
              {
                if ( (bidGblFlags & 2) == 0 )
                  goto LABEL_371;
                v108 = 9792521;
LABEL_297:
                v109 = (unsigned int)v107;
                goto LABEL_298;
              }
              v110 = v213;
              v124 = 0;
            }
            v128 = v110 - v256;
            v129 = 540 - v128;
            v30 = 0;
            v195 = 0;
            if ( v128 == 540 || v129 > 0x7FFFFFFF )
            {
              v30 = -2147024809;
              v195 = -2147024809;
            }
            if ( v30 < 0 )
            {
LABEL_369:
              if ( (bidGblFlags & 2) != 0 )
              {
                v109 = (unsigned int)v30;
                v108 = 9801737;
                goto LABEL_298;
              }
LABEL_371:
              ExtBuffer = Exp;
              goto LABEL_554;
            }
            v130 = v110;
            if ( v129 )
            {
              v131 = v110;
              v195 = 0;
              v132 = 2147483646 - v129;
              while ( v129 + v132 )
              {
                v133 = *(unsigned __int16 *)((char *)v131 + (char *)L"." - (char *)v110);
                if ( !v133 )
                  break;
                *v131++ = v133;
                ++v124;
                if ( !--v129 )
                {
                  --v131;
                  --v124;
                  v30 = -2147024774;
                  v195 = -2147024774;
                  goto LABEL_362;
                }
              }
              v30 = 0;
LABEL_362:
              *v131 = 0;
              v130 = &v110[v124];
            }
            else
            {
              if ( !v110 )
              {
                v30 = -2147024809;
                v195 = -2147024809;
                goto LABEL_364;
              }
              v30 = -2147024774;
              v195 = -2147024774;
            }
            v110 = v130;
            v213 = v130;
LABEL_364:
            if ( v30 < 0 )
              goto LABEL_369;
            ++v125;
            ++v127;
            ++v126;
            if ( v125 >= 2 )
              goto LABEL_372;
            v124 = 0;
          }
        }
LABEL_128:
        v47 = *(_DWORD *)v199;
        v46 = MaxCount;
        goto LABEL_129;
      }
    }
    v47 = *(_DWORD *)v199;
    goto LABEL_132;
  }
  v199[2] = -25374;
LABEL_575:
  if ( (bidGblFlags & 2) != 0 && off_383B49120[0] )
    bidTraceW(off_383B431C0[0], 10602505, off_383B49120[0], 10354);
  PostSQLErrorEx(v3, v199[2], 0, 0xFFFFFFFFFFFFFFFFuLL, 0xFFFFFFFF);
LABEL_579:
  v175 = v230;
  if ( v230 )
  {
    v176 = v229;
    if ( (*((_DWORD *)v229 + 280))-- == 1 && !*((_QWORD *)v175 + 12) )
    {
      (*(void (__fastcall **)(__int64))(*((_QWORD *)v176[39] + 4) + 8LL))((__int64)v176[39] + 32);
      BATCHCTX::Release(v176[139]);
      v176[139] = 0;
      (*(void (__fastcall **)(__int64))(*((_QWORD *)v176[39] + 4) + 24LL))((__int64)v176[39] + 32);
    }
  }
  if ( (bidGblFlags & 2) != 0 && (ExtBuffer || (bidGblFlags & 0x40) != 0) )
  {
    v178 = 10605569;
    if ( ExtBuffer )
      v178 = 10605601;
    bidTraceW(off_383B431C0[0], v178, off_383B494E8[0], (unsigned int)ExtBuffer);
  }
  if ( v228 )
    (*(void (__fastcall **)(__int64))(*((_QWORD *)v228 + 4) + 24LL))((__int64)v228 + 32);
  return (unsigned __int16)ExtBuffer;
}

```

## disassembly

```asm
0x383930a30  push    rbp
0x383930a32  push    rsi
0x383930a33  push    rdi
0x383930a34  push    r12
0x383930a36  push    r13
0x383930a38  push    r14
0x383930a3a  push    r15
0x383930a3c  lea     rbp, [rsp-960h]
0x383930a44  sub     rsp, 0A70h
0x383930a4b  mov     [rbp+990h+var_840], 0FFFFFFFFFFFFFFFEh
0x383930a56  mov     [rsp+0AA0h+arg_10], rbx
0x383930a5e  mov     rax, cs:__security_cookie
0x383930a65  xor     rax, rsp
0x383930a68  mov     [rbp+990h+var_40], rax
0x383930a6f  mov     r14, rdx
0x383930a72  mov     [rbp+990h+var_978], rdx
0x383930a76  mov     r13, rcx
0x383930a79  mov     [rbp+990h+var_A00], rcx
0x383930a7d  xor     r12d, r12d
0x383930a80  mov     [rbp+990h+var_A10], r12d
0x383930a84  mov     rax, [rdx+40h]
0x383930a88  mov     [rbp+990h+var_9B0], rax
0x383930a8c  mov     rcx, [rax+70h]
0x383930a90  mov     [rbp+990h+var_970], rcx
0x383930a94  mov     r15, [rcx+1F58h]
0x383930a9b  mov     [rbp+990h+StatementHandle], r15
0x383930a9f  mov     [rbp+990h+var_980], r12
0x383930aa3  mov     qword ptr [rbp+990h+var_9BC+4], r12
0x383930aa7  mov     [rbp+990h+var_910], r12
0x383930aae  mov     [rbp+990h+var_950], r12
0x383930ab2  mov     [rbp+990h+var_958], r12
0x383930ab6  mov     rax, [rcx+40h]
0x383930aba  lea     edx, [r12+1]
0x383930abf  test    rax, rax
0x383930ac2  jz      short loc_383930ADC
0x383930ac4  mov     rax, [rcx+40h]
0x383930ac8  cmp     byte ptr [rax+4DEh], 0Bh
0x383930acf  jb      short loc_383930ADC
0x383930ad1  test    byte ptr [rax+190h], 2
0x383930ad8  mov     esi, edx
0x383930ada  jz      short loc_383930ADF
0x383930adc  mov     esi, r12d
0x383930adf  mov     [rbp+990h+var_988], r12
0x383930ae3  lea     rax, [r15+130h]
0x383930aea  mov     [rbp+990h+var_930], r12
0x383930aee  test    rax, rax
0x383930af1  jz      short loc_383930B05
0x383930af3  mov     rax, [rax]
0x383930af6  mov     [rbp+990h+var_930], rax
0x383930afa  lea     rcx, [rax+20h]
0x383930afe  mov     rax, [rcx]
0x383930b01  call    qword ptr [rax+8]
0x383930b04  nop
0x383930b05  mov     [rbp+990h+var_928], r12
0x383930b09  mov     [rbp+990h+var_920], r12
0x383930b0d  mov     edi, r12d
0x383930b10  cmp     [r15+458h], rdi
0x383930b17  jnz     short loc_383930B59
0x383930b19  mov     rcx, [r15+70h]
0x383930b1d  lea     r8, [r15+458h]; struct BATCHCTX **
0x383930b24  mov     rdx, r15; struct CConnection *
0x383930b27  mov     rcx, [rcx+40h]; this
0x383930b2b  call    ?GetNewBatchCtx@CConnection@@QEAAJPEAXPEAPEAVBATCHCTX@@@Z; CConnection::GetNewBatchCtx(void *,BATCHCTX * *)
0x383930b30  mov     edi, eax
0x383930b32  test    eax, eax
0x383930b34  jns     short loc_383930B59
0x383930b36  mov     [rbp+990h+var_918], r12
0x383930b3a  test    byte ptr cs:_bidGblFlags, 2
0x383930b41  jz      short loc_383930B80
0x383930b43  mov     r8d, eax
0x383930b46  mov     edx, 3C8009h
0x383930b4b  mov     rcx, cs:off_383B43228; "d:\\b\\s1\\sources\\sql\\ntdbms\\sqlncl"...
0x383930b52  call    _bidTraceHR
0x383930b57  jmp     short loc_383930B80
0x383930b59  mov     rcx, [r15+458h]
0x383930b60  mov     [rbp+990h+var_918], rcx
0x383930b64  mov     rax, [rcx+40h]
0x383930b68  test    byte ptr [rax+190h], 1
0x383930b6f  jz      short loc_383930B80
0x383930b71  mov     [rbp+990h+var_928], r15
0x383930b75  mov     [rbp+990h+var_920], rcx
0x383930b79  inc     dword ptr [r15+460h]
0x383930b80  test    edi, edi
0x383930b82  jns     short loc_383930BC8
0x383930b84  or      r12, 0FFFFFFFFFFFFFFFFh
0x383930b88  test    byte ptr cs:_bidGblFlags, 2
0x383930b8f  jz      loc_38393364A
0x383930b95  mov     rcx, cs:off_383B431C0; "d:\\b\\s1\\sources\\sql\\ntdbms\\sqlncl"...
0x383930b9c  mov     rax, cs:off_383B49120; "<Trace|MARK> line %d\n"
0x383930ba3  test    rax, rax
0x383930ba6  jz      loc_38393364A
0x383930bac  mov     r9d, 23C2h
0x383930bb2  mov     r8, cs:off_383B49120; "<Trace|MARK> line %d\n"
0x383930bb9  mov     edx, 8F0809h
0x383930bbe  call    _bidTraceW
0x383930bc3  jmp     loc_38393364A
0x383930bc8  mov     rdi, [rbp+990h+var_9B0]
0x383930bcc  mov     rcx, rdi; struct tagSTMT *
0x383930bcf  call    ?HandleDeferredPrepare@@YAFPEAUtagSTMT@@@Z; HandleDeferredPrepare(tagSTMT *)
0x383930bd4  movzx   r12d, ax
0x383930bd8  mov     [rbp+990h+var_A0C], r12d
0x383930bdc  cmp     ax, 0FFFFh
0x383930be0  jnz     short loc_383930C22
0x383930be2  test    byte ptr cs:_bidGblFlags, 2
0x383930be9  jz      loc_38393364A
0x383930bef  mov     rcx, cs:off_383B431C0; "d:\\b\\s1\\sources\\sql\\ntdbms\\sqlncl"...
0x383930bf6  mov     rax, cs:off_383B49120; "<Trace|MARK> line %d\n"
0x383930bfd  test    rax, rax
0x383930c00  jz      loc_38393364A
0x383930c06  mov     r9d, 23C6h
0x383930c0c  mov     r8, cs:off_383B49120; "<Trace|MARK> line %d\n"
0x383930c13  mov     edx, 8F1809h
0x383930c18  call    _bidTraceW
0x383930c1d  jmp     loc_38393364A
0x383930c22  mov     eax, [rdi+5CCh]
0x383930c28  bt      eax, 9
0x383930c2c  jnb     loc_3839335EF
0x383930c32  test    eax, 900h
0x383930c37  jnz     loc_3839335EF
0x383930c3d  cmp     dword ptr [rdi+7D8h], 0
0x383930c44  jnz     loc_3839335EF
0x383930c4a  mov     r8, [r15+458h]
0x383930c51  xor     ecx, ecx
0x383930c53  mov     [rbp+990h+var_9F8+4], cx
0x383930c57  test    r8, r8
0x383930c5a  jz      short loc_383930C70
0x383930c5c  lea     rdx, [rbp+990h+var_9F8+4]; unsigned __int16 *
0x383930c60  mov     rcx, r15; struct tagSTMT *
0x383930c63  call    ?CheckBusy@@YAHPEAUtagSTMT@@PEAG@Z; CheckBusy(tagSTMT *,ushort *)
0x383930c68  test    eax, eax
0x383930c6a  jnz     loc_3839335E2
0x383930c70  mov     rcx, r15; struct tagSTMT *
0x383930c73  call    ?CheckOptions@@YAFPEAUtagSTMT@@@Z; CheckOptions(tagSTMT *)
0x383930c78  cmp     ax, 0FFFFh
0x383930c7c  jz      loc_3839335E2
0x383930c82  mov     rax, [rdi+1D0h]
0x383930c89  test    rax, rax
0x383930c8c  jnz     short loc_383930C95
0x383930c8e  mov     rax, [rdi+1C8h]
0x383930c95  mov     rbx, [rax+8]
0x383930c99  shr     rbx, 1
0x383930c9c  lea     rdi, [rax+18h]
0x383930ca0  mov     qword ptr [rbp+990h+var_908], rbx
0x383930ca7  mov     [rbp+990h+var_900], rdi
0x383930cae  cmp     qword ptr [r14+78h], 0
0x383930cb3  jnz     loc_383930D76
0x383930cb9  mov     rdx, [r14+40h]; struct tagOBJBASE *
0x383930cbd  mov     r8d, [rdx+30Ch]; unsigned int
0x383930cc4  mov     rcx, r14; struct IPDTag *
0x383930cc7  call    ?AllocPlex@@YAFPEAUIPDTag@@PEAUtagOBJBASE@@_K@Z; AllocPlex(IPDTag *,tagOBJBASE *,unsigned __int64)
0x383930ccc  movzx   r12d, ax
0x383930cd0  mov     eax, 0FFFEh
0x383930cd5  test    ax, r12w
0x383930cd9  jz      short loc_383930D16
0x383930cdb  test    byte ptr cs:_bidGblFlags, 2
0x383930ce2  jz      loc_3839335E2
0x383930ce8  mov     rcx, cs:off_383B431C0; "d:\\b\\s1\\sources\\sql\\ntdbms\\sqlncl"...
0x383930cef  mov     rax, cs:off_383B49120; "<Trace|MARK> line %d\n"
0x383930cf6  test    rax, rax
0x383930cf9  jz      loc_3839335E2
0x383930cff  mov     r9d, 23EBh
0x383930d05  mov     r8, cs:off_383B49120; "<Trace|MARK> line %d\n"
0x383930d0c  mov     edx, 8FAC09h
0x383930d11  jmp     loc_3839335DD
0x383930d16  mov     rax, [r14+40h]
0x383930d1a  mov     edx, [rax+30Ch]; unsigned __int64
0x383930d20  mov     rcx, r14; struct IPDTag *
0x383930d23  call    ?UnbindParam@@YAFPEAUIPDTag@@_K@Z; UnbindParam(IPDTag *,unsigned __int64)
0x383930d28  movzx   r12d, ax
0x383930d2c  mov     [rbp+990h+var_A0C], r12d
0x383930d30  mov     eax, 0FFFEh
0x383930d35  test    ax, r12w
0x383930d39  jz      short loc_383930D76
0x383930d3b  test    byte ptr cs:_bidGblFlags, 2
0x383930d42  jz      loc_3839335E2
0x383930d48  mov     rcx, cs:off_383B431C0; "d:\\b\\s1\\sources\\sql\\ntdbms\\sqlncl"...
0x383930d4f  mov     rax, cs:off_383B49120; "<Trace|MARK> line %d\n"
0x383930d56  test    rax, rax
0x383930d59  jz      loc_3839335E2
0x383930d5f  mov     r9d, 23EEh
0x383930d65  mov     r8, cs:off_383B49120; "<Trace|MARK> line %d\n"
0x383930d6c  mov     edx, 8FB809h
0x383930d71  jmp     loc_3839335DD
0x383930d76  cmp     ebx, 190h
0x383930d7c  ja      short loc_383930D86
0x383930d7e  mov     r8d, 3E8h
0x383930d84  jmp     short loc_383930D90
0x383930d86  mov     eax, ebx
0x383930d88  lea     r8, ds:200h[rax*2]; unsigned __int64
0x383930d90  mov     dword ptr [rsp+0AA0h+BufferLength], 1; int
0x383930d98  mov     r9d, 80h; unsigned __int64
0x383930d9e  lea     rdx, [rbp+990h+var_980]; struct ext_buffer **
0x383930da2  mov     rcx, [rbp+990h+var_970]; struct tagOBJBASE *
0x383930da6  call    ?CreateExtBufferEx@@YAFPEAUtagOBJBASE@@PEAPEAUext_buffer@@_K2H@Z; CreateExtBufferEx(tagOBJBASE *,ext_buffer * *,unsigned __int64,unsigned __int64,int)
0x383930dab  cmp     ax, 0FFFFh
0x383930daf  jz      loc_383933550
0x383930db5  mov     r9d, ebx
0x383930db8  add     r9, r9; __int64
0x383930dbb  mov     dword ptr [rsp+0AA0h+BufferLength], 1; unsigned int *
0x383930dc3  mov     r8, rdi; void *
0x383930dc6  lea     rdx, [rbp+990h+var_980]; struct ext_buffer **
0x383930dca  mov     rbx, [rbp+990h+var_970]
0x383930dce  mov     rcx, rbx; struct tagOBJBASE *
0x383930dd1  call    ?WriteToExtBufferEx@@YAFPEAUtagOBJBASE@@PEAPEAUext_buffer@@PEBX_JH@Z; WriteToExtBufferEx(tagOBJBASE *,ext_buffer * *,void const *,__int64,int)
0x383930dd6  cmp     ax, 0FFFFh
0x383930dda  jz      loc_383933550
0x383930de0  lea     r8, [rbp+990h+var_980]; struct ext_buffer **
0x383930de4  mov     rdx, rbx; struct tagDBC *
0x383930de7  xor     ecx, ecx; struct tagSTMT *
0x383930de9  call    ?SubstituteECodes@@YAFPEAUtagSTMT@@PEAUtagDBC@@PEAPEAUext_buffer@@@Z; SubstituteECodes(tagSTMT *,tagDBC *,ext_buffer * *)
0x383930dee  movzx   ebx, ax
0x383930df1  cmp     ax, 0FFFFh
0x383930df5  jnz     short loc_383930E2A
0x383930df7  test    byte ptr cs:_bidGblFlags, 2
0x383930dfe  jz      short loc_383930E68
0x383930e00  mov     rcx, cs:off_383B431E8; "d:\\b\\s1\\sources\\sql\\ntdbms\\sqlncl"...
0x383930e07  mov     rax, cs:off_383B49120; "<Trace|MARK> line %d\n"
0x383930e0e  test    rax, rax
0x383930e11  jz      short loc_383930E2A
0x383930e13  mov     r9d, 0E7Fh
0x383930e19  mov     r8, cs:off_383B49120; "<Trace|MARK> line %d\n"
0x383930e20  mov     edx, 39FC09h
0x383930e25  call    _bidTraceW
0x383930e2a  test    byte ptr cs:_bidGblFlags, 2
0x383930e31  jz      short loc_383930E68
0x383930e33  mov     rcx, cs:off_383B431E8; "d:\\b\\s1\\sources\\sql\\ntdbms\\sqlncl"...
0x383930e3a  mov     r8, cs:off_383B494E8; "<ODBC|DRIVER|RET> %d{SQLRETURN}\n"
0x383930e41  test    bx, bx
0x383930e44  jnz     short loc_383930E4F
0x383930e46  test    byte ptr cs:_bidGblFlags, 40h
0x383930e4d  jz      short loc_383930E72
0x383930e4f  mov     edx, 3A0C01h
0x383930e54  mov     eax, 3A0C21h
0x383930e59  test    bx, bx
0x383930e5c  cmovnz  edx, eax
0x383930e5f  movsx   r9d, bx
0x383930e63  call    _bidTraceW
0x383930e68  cmp     bx, 0FFFFh
0x383930e6c  jz      loc_383933550
0x383930e72  test    esi, esi
0x383930e74  jz      loc_383931078
0x383930e7a  xor     eax, eax
0x383930e7c  mov     [rbp+990h+var_8C8], rax
0x383930e83  mov     [rbp+990h+var_8C0], rax
0x383930e8a  mov     [rbp+990h+var_8B8], rax
0x383930e91  mov     [rbp+990h+var_8B0], rax
0x383930e98  mov     [rbp+990h+var_8A8], ax
0x383930e9f  lea     rsi, ??_7CImpODBCIObtainParameterMetadata@@6B@; const CImpODBCIObtainParameterMetadata::`vftable'
0x383930ea6  mov     [rbp+990h+var_8D0], rsi
0x383930ead  mov     [rbp+990h+var_890], rax
0x383930eb4  mov     rdi, [rbp+990h+var_9B0]
0x383930eb8  mov     eax, [rdi+30Ch]
0x383930ebe  mov     [rbp+990h+var_8A0], eax
0x383930ec4  mov     rax, [rbp+990h+var_980]
0x383930ec8  mov     [rbp+990h+var_898], rax
0x383930ecf  mov     [rbp+990h+var_888], r14
0x383930ed6  mov     rdx, rdi; struct tagSTMT *
0x383930ed9  lea     rcx, [rbp+990h+var_8D0]; this
0x383930ee0  call    ?Initialize@CImpODBCObtainMetadata@@QEAAJPEAUtagSTMT@@@Z; CImpODBCObtainMetadata::Initialize(tagSTMT *)
0x383930ee5  mov     ebx, eax
0x383930ee7  mov     [rbp+990h+var_A10], eax
0x383930eea  test    eax, eax
0x383930eec  jns     short loc_383930F28
0x383930eee  test    byte ptr cs:_bidGblFlags, 2
0x383930ef5  jz      short loc_383930F61
0x383930ef7  mov     rcx, cs:off_383B431C0; "d:\\b\\s1\\sources\\sql\\ntdbms\\sqlncl"...
0x383930efe  mov     rax, cs:off_383B49128; "<Trace|HR> 0x%08X{HRESULT} line %d\n"
0x383930f05  test    rax, rax
0x383930f08  jz      short loc_383930F61
0x383930f0a  mov     dword ptr [rsp+0AA0h+BufferLength], 21D9h
0x383930f12  mov     r9d, ebx
0x383930f15  mov     r8, cs:off_383B49128; "<Trace|HR> 0x%08X{HRESULT} line %d\n"
0x383930f1c  mov     edx, 876429h
0x383930f21  call    _bidTraceW
0x383930f26  jmp     short loc_383930F61
0x383930f28  lea     rdx, [rbp+990h+var_890]; struct ext_buffer **
0x383930f2f  mov     rcx, [rbp+990h+var_8B0]; struct tagOBJBASE *
0x383930f36  call    ?InitializeNamePool@@YAJPEAUtagOBJBASE@@PEAPEAUext_buffer@@@Z; InitializeNamePool(tagOBJBASE *,ext_buffer * *)
0x383930f3b  mov     ebx, eax
0x383930f3d  mov     [rbp+990h+var_A10], eax
0x383930f40  test    eax, eax
0x383930f42  jns     short loc_383930F61
0x383930f44  test    byte ptr cs:_bidGblFlags, 2
0x383930f4b  jz      short loc_383930F61
0x383930f4d  mov     r8d, eax
0x383930f50  mov     edx, 877009h
0x383930f55  mov     rcx, cs:off_383B431C0; "d:\\b\\s1\\sources\\sql\\ntdbms\\sqlncl"...
0x383930f5c  call    _bidTraceHR
0x383930f61  test    ebx, ebx
0x383930f63  jns     short loc_383930FC1
0x383930f65  test    byte ptr cs:_bidGblFlags, 2
0x383930f6c  jz      short loc_383930F83
0x383930f6e  mov     r8d, ebx
0x383930f71  mov     edx, 8FFC09h
0x383930f76  mov     rcx, cs:off_383B431C0; "d:\\b\\s1\\sources\\sql\\ntdbms\\sqlncl"...
0x383930f7d  call    _bidTraceHR
0x383930f82  nop
0x383930f83  mov     [rbp+990h+var_8D0], rsi
0x383930f8a  mov     rdx, [rbp+990h+var_890]
0x383930f91  test    rdx, rdx
  ... truncated ...
```
