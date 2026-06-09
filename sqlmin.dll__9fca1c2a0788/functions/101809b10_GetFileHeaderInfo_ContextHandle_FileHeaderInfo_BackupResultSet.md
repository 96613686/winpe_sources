# GetFileHeaderInfo(ContextHandle,FileHeaderInfo *,BackupResultSet *)

- ea: `0x101809b10`
- end: `0x10180d6f7`
- name: `?GetFileHeaderInfo@@YAXVContextHandle@@PEAUFileHeaderInfo@@PEAVBackupResultSet@@@Z`
- size: `15335`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x101f34e00`

## callees

- `0x100401490`
- `0x100402000`
- `0x100441e00`
- `0x100472440`
- `0x1012c79e0`
- `0x1018081f0`
- `0x1018086f0`
- `0x101809a40`
- `0x101809b10`
- `0x101f7b410`
- `0x1021d8a90`
- `0x1021eafd0`

## import_xrefs

- `KERNEL32!SetLastError` at `0x10180d6c7`
- `KERNEL32!SetLastError` at `0x10180d6c7`
- `sqldk!?GetOSErrString@@YAPEA_WKAEAVErrorStringHolder@@PEBXK@Z` at `0x101809bcd`
- `sqldk!?GetOSErrString@@YAPEA_WKAEAVErrorStringHolder@@PEBXK@Z` at `0x101809bcd`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x101809e25`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x101809ef8`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x101809fc9`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x10180a250`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x10180a31a`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x10180a6a1`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x10180a765`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x10180a82b`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x10180aa85`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x10180ab41`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x10180aef6`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x10180afbd`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x10180b083`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x10180b2e7`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x10180b3a4`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x10180b708`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x10180b7db`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x10180b8ac`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x10180bb21`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x10180bbe9`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x10180bf52`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x10180c025`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x10180c0f6`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x10180c36a`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x10180c432`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x10180c7aa`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x10180c87d`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x10180c94e`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x10180cbca`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x10180cc92`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x10180cff7`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x10180d0ca`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x10180d19b`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x10180d411`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x10180d4d9`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x101809e25`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x101809ef8`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x101809fc9`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x10180a250`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x10180a31a`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x10180a6a1`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x10180a765`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x10180a82b`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x10180aa85`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x10180ab41`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x10180aef6`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x10180afbd`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x10180b083`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x10180b2e7`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x10180b3a4`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x10180b708`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x10180b7db`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x10180b8ac`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x10180bb21`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x10180bbe9`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x10180bf52`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x10180c025`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x10180c0f6`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x10180c36a`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x10180c432`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x10180c7aa`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x10180c87d`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x10180c94e`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x10180cbca`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x10180cc92`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x10180cff7`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x10180d0ca`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x10180d19b`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x10180d411`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x10180d4d9`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x101809bf1`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x101809e01`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x101809ed4`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x101809fa5`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10180a22c`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10180a2f6`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10180a67d`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10180a741`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10180a807`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10180aa61`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10180ab1d`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10180ad37`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10180aed2`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10180af99`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10180b05f`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10180b2c3`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10180b380`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10180b6e4`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10180b7b7`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10180b888`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10180bafd`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10180bbc5`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10180bf2e`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10180c001`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10180c0d2`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10180c346`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10180c40e`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10180c786`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10180c859`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10180c92a`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10180cba6`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10180cc6e`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10180cfd3`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10180d0a6`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10180d177`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10180d3ed`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10180d4b5`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x101809bf1`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x101809e01`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x101809ed4`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x101809fa5`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10180a22c`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10180a2f6`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10180a67d`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10180a741`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10180a807`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10180aa61`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10180ab1d`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10180ad37`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10180aed2`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10180af99`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10180b05f`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10180b2c3`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10180b380`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10180b6e4`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10180b7b7`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10180b888`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10180bafd`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10180bbc5`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10180bf2e`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10180c001`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10180c0d2`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10180c346`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10180c40e`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10180c786`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10180c859`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10180c92a`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10180cba6`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10180cc6e`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10180cfd3`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10180d0a6`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10180d177`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10180d3ed`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10180d4b5`
- `sqldk!SystemThread_TlsIndex` at `0x101809dac`
- `sqldk!SystemThread_TlsIndex` at `0x101809e7f`
- `sqldk!SystemThread_TlsIndex` at `0x101809f50`
- `sqldk!SystemThread_TlsIndex` at `0x10180a1d7`
- `sqldk!SystemThread_TlsIndex` at `0x10180a2a1`
- `sqldk!SystemThread_TlsIndex` at `0x10180a628`
- `sqldk!SystemThread_TlsIndex` at `0x10180a6ec`
- `sqldk!SystemThread_TlsIndex` at `0x10180a7b2`
- `sqldk!SystemThread_TlsIndex` at `0x10180aa0c`
- `sqldk!SystemThread_TlsIndex` at `0x10180aac8`
- `sqldk!SystemThread_TlsIndex` at `0x10180ae7d`
- `sqldk!SystemThread_TlsIndex` at `0x10180af44`
- `sqldk!SystemThread_TlsIndex` at `0x10180b00a`
- `sqldk!SystemThread_TlsIndex` at `0x10180b26e`
- `sqldk!SystemThread_TlsIndex` at `0x10180b32b`
- `sqldk!SystemThread_TlsIndex` at `0x10180b68f`
- `sqldk!SystemThread_TlsIndex` at `0x10180b762`
- `sqldk!SystemThread_TlsIndex` at `0x10180b833`
- `sqldk!SystemThread_TlsIndex` at `0x10180baa8`
- `sqldk!SystemThread_TlsIndex` at `0x10180bb70`
- `sqldk!SystemThread_TlsIndex` at `0x10180bed9`
- `sqldk!SystemThread_TlsIndex` at `0x10180bfac`
- `sqldk!SystemThread_TlsIndex` at `0x10180c07d`
- `sqldk!SystemThread_TlsIndex` at `0x10180c2f1`
- `sqldk!SystemThread_TlsIndex` at `0x10180c3b9`
- `sqldk!SystemThread_TlsIndex` at `0x10180c731`
- `sqldk!SystemThread_TlsIndex` at `0x10180c804`
- `sqldk!SystemThread_TlsIndex` at `0x10180c8d5`
- `sqldk!SystemThread_TlsIndex` at `0x10180cb51`
- `sqldk!SystemThread_TlsIndex` at `0x10180cc19`
- `sqldk!SystemThread_TlsIndex` at `0x10180cf7e`
- `sqldk!SystemThread_TlsIndex` at `0x10180d051`
- `sqldk!SystemThread_TlsIndex` at `0x10180d122`
- `sqldk!SystemThread_TlsIndex` at `0x10180d398`
- `sqldk!SystemThread_TlsIndex` at `0x10180d460`
- `sqldk!SystemThread_TlsOffset` at `0x101809db5`
- `sqldk!SystemThread_TlsOffset` at `0x101809e88`
- `sqldk!SystemThread_TlsOffset` at `0x101809f59`
- `sqldk!SystemThread_TlsOffset` at `0x10180a1e0`
- `sqldk!SystemThread_TlsOffset` at `0x10180a2aa`
- `sqldk!SystemThread_TlsOffset` at `0x10180a631`
- `sqldk!SystemThread_TlsOffset` at `0x10180a6f5`
- `sqldk!SystemThread_TlsOffset` at `0x10180a7bb`
- `sqldk!SystemThread_TlsOffset` at `0x10180aa15`
- `sqldk!SystemThread_TlsOffset` at `0x10180aad1`
- `sqldk!SystemThread_TlsOffset` at `0x10180ae86`
- `sqldk!SystemThread_TlsOffset` at `0x10180af4d`
- `sqldk!SystemThread_TlsOffset` at `0x10180b013`
- `sqldk!SystemThread_TlsOffset` at `0x10180b277`
- `sqldk!SystemThread_TlsOffset` at `0x10180b334`
- `sqldk!SystemThread_TlsOffset` at `0x10180b698`
- `sqldk!SystemThread_TlsOffset` at `0x10180b76b`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall GetFileHeaderInfo(__int64 a1, wchar_t **a2, BackupResultSet *a3)
{
  BackupResultSet *v3; // rsi
  __int64 v5; // r14
  wchar_t *v6; // rcx
  __int64 v7; // rax
  wchar_t *v8; // rdi
  __int64 v9; // rbx
  wchar_t *OSErrString; // rax
  __int64 v11; // r15
  int v12; // r8d
  const unsigned __int8 *v13; // rbx
  unsigned int v14; // eax
  unsigned int v15; // r9d
  const unsigned __int8 *v16; // r8
  int v17; // edx
  int v18; // eax
  unsigned int v19; // r9d
  const unsigned __int8 *v20; // rdi
  __int64 v21; // rax
  __int64 v22; // rax
  unsigned int v23; // r10d
  __int64 v24; // rax
  __int64 v25; // rax
  __int64 v26; // rax
  __int64 v27; // rax
  const unsigned __int8 *v28; // rax
  unsigned int v29; // ebx
  __int64 v30; // rcx
  unsigned int v31; // ecx
  unsigned __int16 v32; // cx
  __int16 v33; // r11
  __int16 v34; // cx
  struct RecVersioningInfo *VersioningInfo; // rax
  __int64 v36; // r9
  __int64 v37; // r8
  int v38; // edx
  __int16 v39; // ax
  __int64 v40; // rax
  __int64 v41; // rax
  __int64 v42; // rax
  __int64 v43; // rax
  __int16 v44; // dx
  const unsigned __int8 *v45; // rax
  unsigned int v46; // esi
  unsigned int v47; // edi
  unsigned int v48; // edi
  unsigned int v49; // r8d
  int v50; // edx
  int v51; // eax
  const unsigned __int8 *v52; // rbx
  unsigned int v53; // edx
  const unsigned __int8 *v54; // rdi
  __int64 v55; // rax
  __int64 v56; // rax
  __int64 v57; // rax
  __int64 v58; // rax
  __int64 v59; // rax
  __int64 v60; // rax
  const unsigned __int8 *v61; // rax
  unsigned int v62; // ebx
  __int64 v63; // rcx
  unsigned int v64; // ecx
  unsigned __int16 v65; // dx
  const unsigned __int8 *v66; // rdx
  __int16 v67; // r8
  __int16 v68; // cx
  struct RecVersioningInfo *v69; // rax
  __int64 v70; // r9
  __int64 v71; // r8
  int v72; // edx
  __int16 v73; // ax
  __int64 v74; // rax
  __int64 v75; // rax
  __int64 v76; // rax
  __int64 v77; // rax
  __int16 v78; // r8
  const unsigned __int8 *v79; // rax
  unsigned int v80; // esi
  unsigned int v81; // edi
  BackupResultSet *v82; // rdi
  unsigned int v83; // r8d
  int v84; // edx
  int v85; // eax
  const unsigned __int8 *v86; // rbx
  unsigned int v87; // edx
  const unsigned __int8 *v88; // rdi
  __int64 v89; // rax
  __int64 v90; // rax
  __int64 v91; // rax
  __int64 v92; // rax
  __int64 v93; // rax
  __int64 v94; // rax
  const unsigned __int8 *v95; // rax
  unsigned int v96; // ebx
  __int64 v97; // rcx
  unsigned int v98; // ecx
  unsigned __int16 v99; // r8
  const unsigned __int8 *v100; // r8
  __int16 v101; // ax
  __int16 v102; // cx
  struct RecVersioningInfo *v103; // rax
  __int64 v104; // r9
  __int64 v105; // rdx
  int v106; // r8d
  __int16 v107; // ax
  __int64 v108; // rax
  __int64 v109; // rax
  __int64 v110; // rax
  __int64 v111; // rax
  const unsigned __int8 *v112; // rax
  unsigned int v113; // esi
  unsigned int v114; // edi
  struct BackupResultSet *v115; // r14
  unsigned int v116; // eax
  unsigned int v117; // r9d
  const unsigned __int8 *v118; // r8
  int v119; // edx
  int v120; // eax
  const unsigned __int8 *v121; // rbx
  unsigned int v122; // edx
  const unsigned __int8 *v123; // rdi
  __int64 v124; // rax
  __int64 v125; // rax
  unsigned int v126; // r10d
  __int64 v127; // rax
  __int64 v128; // rax
  __int64 v129; // rax
  __int64 v130; // rax
  const unsigned __int8 *v131; // rax
  unsigned int v132; // ebx
  __int64 v133; // rcx
  unsigned int v134; // ecx
  unsigned __int16 v135; // cx
  __int16 v136; // ax
  __int16 v137; // cx
  struct RecVersioningInfo *v138; // rax
  __int64 v139; // r9
  __int64 v140; // rdx
  int v141; // r8d
  __int16 v142; // ax
  __int64 v143; // rax
  __int64 v144; // rax
  __int64 v145; // rax
  __int64 v146; // rax
  __int16 v147; // r9
  const unsigned __int8 *v148; // rax
  unsigned int v149; // esi
  unsigned int v150; // edi
  unsigned int v151; // eax
  unsigned int v152; // r9d
  const unsigned __int8 *v153; // r8
  int v154; // edx
  int v155; // eax
  const unsigned __int8 *v156; // rbx
  unsigned int v157; // edx
  const unsigned __int8 *v158; // rdi
  __int64 v159; // rax
  __int64 v160; // rax
  unsigned int v161; // r10d
  __int64 v162; // rax
  __int64 v163; // rax
  __int64 v164; // rax
  __int64 v165; // rax
  const unsigned __int8 *v166; // rax
  unsigned int v167; // ebx
  __int64 v168; // rcx
  unsigned int v169; // ecx
  unsigned __int16 v170; // cx
  __int16 v171; // r11
  __int16 v172; // cx
  struct RecVersioningInfo *v173; // rax
  __int64 v174; // r9
  __int64 v175; // rdx
  int v176; // r8d
  __int16 v177; // ax
  __int64 v178; // rax
  __int64 v179; // rax
  __int64 v180; // rax
  __int64 v181; // rax
  __int16 v182; // r9
  const unsigned __int8 *v183; // rax
  unsigned int v184; // esi
  unsigned int v185; // edi
  unsigned int v186; // eax
  unsigned int v187; // r9d
  const unsigned __int8 *v188; // r8
  int v189; // edx
  int v190; // eax
  const unsigned __int8 *v191; // rbx
  unsigned int v192; // edx
  const unsigned __int8 *v193; // rdi
  __int64 v194; // rax
  __int64 v195; // rax
  unsigned int v196; // r10d
  __int64 v197; // rax
  __int64 v198; // rax
  __int64 v199; // rax
  __int64 v200; // rax
  const unsigned __int8 *v201; // rax
  unsigned int v202; // ebx
  __int64 v203; // rcx
  unsigned int v204; // ecx
  unsigned __int16 v205; // cx
  __int16 v206; // r11
  __int16 v207; // cx
  struct RecVersioningInfo *v208; // rax
  __int64 v209; // r9
  __int64 v210; // rdx
  int v211; // r8d
  __int16 v212; // ax
  __int64 v213; // rax
  __int64 v214; // rax
  __int64 v215; // rax
  __int64 v216; // rax
  __int16 v217; // r9
  const unsigned __int8 *v218; // rax
  unsigned int v219; // esi
  unsigned int v220; // edi
  unsigned int v221; // eax
  unsigned int v222; // r9d
  const unsigned __int8 *v223; // r8
  int v224; // edx
  int v225; // eax
  unsigned int v226; // ebx
  unsigned int v227; // edx
  const unsigned __int8 *v228; // rdi
  __int64 v229; // rax
  __int64 v230; // rax
  unsigned int v231; // r9d
  __int64 v232; // rax
  __int64 v233; // rax
  __int64 v234; // rax
  __int64 v235; // rax
  const unsigned __int8 *v236; // rax
  unsigned int v237; // ebx
  __int64 v238; // rcx
  unsigned int v239; // ecx
  unsigned __int16 v240; // cx
  __int16 v241; // ax
  __int16 v242; // cx
  struct RecVersioningInfo *v243; // rax
  __int64 v244; // r9
  __int64 v245; // rdx
  int v246; // r8d
  __int16 v247; // ax
  __int64 v248; // rax
  __int64 v249; // rax
  __int64 v250; // rax
  __int64 v251; // rax
  __int16 v252; // r10
  const unsigned __int8 *v253; // rax
  unsigned int v254; // edi
  unsigned int v255; // ebx
  const unsigned __int8 *v256; // rax
  void *v257; // rbx
  struct IFileSystemHandler *v258; // rax
  unsigned __int8 *Destination; // [rsp+20h] [rbp-E0h]
  rsize_t DestinationSize; // [rsp+28h] [rbp-D8h]
  unsigned int v261; // [rsp+40h] [rbp-C0h] BYREF
  int v262; // [rsp+48h] [rbp-B8h] BYREF
  unsigned __int16 v263; // [rsp+4Ch] [rbp-B4h]
  unsigned __int16 v264; // [rsp+4Eh] [rbp-B2h]
  unsigned int *v265; // [rsp+50h] [rbp-B0h]
  unsigned int v266; // [rsp+58h] [rbp-A8h] BYREF
  unsigned int v267; // [rsp+5Ch] [rbp-A4h] BYREF
  unsigned int v268; // [rsp+60h] [rbp-A0h] BYREF
  unsigned int v269; // [rsp+64h] [rbp-9Ch] BYREF
  unsigned int v270; // [rsp+68h] [rbp-98h] BYREF
  unsigned int v271; // [rsp+6Ch] [rbp-94h] BYREF
  unsigned int v272; // [rsp+70h] [rbp-90h] BYREF
  BackupResultSet *v273; // [rsp+78h] [rbp-88h]
  unsigned int v274; // [rsp+80h] [rbp-80h] BYREF
  void *v275[9]; // [rsp+88h] [rbp-78h] BYREF
  __int16 v276; // [rsp+D0h] [rbp-30h] BYREF
  __int16 v277; // [rsp+D2h] [rbp-2Eh] BYREF
  unsigned int v278; // [rsp+D4h] [rbp-2Ch]
  const unsigned __int8 *v279; // [rsp+D8h] [rbp-28h]
  PageComprMgr *v280; // [rsp+E0h] [rbp-20h]
  unsigned int v281; // [rsp+E8h] [rbp-18h]
  unsigned __int16 v282; // [rsp+ECh] [rbp-14h]
  unsigned __int64 v283; // [rsp+EEh] [rbp-12h]
  _TBYTE v284; // [rsp+F6h] [rbp-Ah]
  int v285; // [rsp+104h] [rbp+4h]
  char v286[8191]; // [rsp+180h] [rbp+80h] BYREF
  char v287; // [rsp+217Fh] [rbp+207Fh] BYREF

  v275[1] = (void *)-2LL;
  v3 = a3;
  v273 = a3;
  v5 = -1;
  v275[0] = (void *)-1LL;
  v6 = *a2;
  v7 = -1;
  do
    ++v7;
  while ( v6[v7] );
  if ( !(unsigned __int8)UtOpenFile(v6, 2 * v7, v275, &v274) )
  {
    BackupResultSet::EndResultSet(v3, 1);
    v8 = *a2;
    v9 = -1;
    do
      ++v9;
    while ( v8[v9] );
    OSErrString = GetOSErrString(v274, (struct ErrorStringHolder *)v286, 0, 0);
    ex_raise(51, 23, 16, 20, OSErrString, 2 * v9, v8);
  }
  v276 = -1;
  v11 = 0;
  v279 = 0;
  v278 = 0;
  v283 = 0;
  *(_QWORD *)((char *)&v284 + 2) = 0;
  v280 = 0;
  v285 = -1;
  v264 &= 0xFFE0u;
  if ( !(unsigned int)GetHdrPageAndRec(v275, (unsigned __int64)&v287 & 0xFFFFFFFFFFFFF000uLL, &v276) )
    RaiseFileHdrErr(v3, 28, *a2, (wchar_t *)L"HEADER");
  v262 = -4;
  v13 = (const unsigned __int8 *)4;
  v263 = 4;
  v14 = v264;
  LOWORD(v14) = v264 & 0xFFE0;
  v15 = v264 & 0xFFE0;
  v264 &= 0xFFE0u;
  v265 = 0;
  if ( !v276 )
  {
    v16 = v279;
    if ( (*v279 & 0x10) != 0 )
    {
      if ( (int)v280 > -4 )
      {
        if ( *(_WORD *)&v279[(unsigned int)v280] >= 4u )
        {
          LOBYTE(v17) = v279[(unsigned int)v280 + 2] >> 3;
          v18 = 1;
        }
        else
        {
          v17 = ~(v15 >> 4);
          v18 = 0;
        }
      }
      else
      {
        v17 = ~(v14 >> 4);
        v18 = 0;
      }
    }
    else
    {
      if ( ((1 << (*v279 & 0xE)) & 0x1105) == 0 )
        goto LABEL_23;
      LOBYTE(v17) = ~(unsigned __int8)(v15 >> 4);
      v18 = 0;
    }
    if ( (v17 & 1) != 0 )
    {
      v13 = 0;
      v261 = 0;
      goto LABEL_140;
    }
    if ( !v18 && (v264 & 0x10) != 0 )
    {
      v261 = *v265;
      goto LABEL_140;
    }
LABEL_23:
    if ( v278 )
    {
      v23 = v281;
    }
    else
    {
      v277 = 0;
      v19 = (unsigned int)v280;
      HIDWORD(v280) = (_DWORD)v280;
      if ( (*v279 & 0x10) != 0 )
      {
        v19 = (((unsigned int)*(unsigned __int16 *)&v279[(unsigned int)v280] + 7) >> 3) + (_DWORD)v280 + 2;
        HIDWORD(v280) = v19;
      }
      if ( (*v279 & 0x20) != 0 )
      {
        v20 = &v279[v19];
        v282 = *(_WORD *)v20;
        if ( !v282 )
        {
          if ( byte_10316E8D7 || (qword_10317B120 & 1) != 0 )
          {
            v21 = *(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                            + SystemThread_TlsOffset
                            + 8LL);
            if ( v21 )
            {
              v22 = *(_QWORD *)(v21 + 96);
              if ( v22 )
              {
                if ( *(_BYTE *)(v22 + 1177) )
                {
                  if ( byte_10316E7C7 || (qword_10317B120 & 2) != 0 )
                    utassert_fail(1u, "false", "Sql\\Ntdbms\\storeng\\drs\\fixedvarrecord.cpp", 2010, 0);
                  else
                    ex_raise(34, 68, 21, 1003);
                }
              }
            }
            v16 = v279;
          }
          RaiseInconsistencyError(v16, 3);
          v16 = v279;
        }
        v23 = HIDWORD(v280) + 2 * (v282 + 1);
        v281 = v23;
        if ( v23 > 0x1F9E )
        {
          if ( byte_10316E8D7 || (qword_10317B120 & 1) != 0 )
          {
            v24 = *(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                            + SystemThread_TlsOffset
                            + 8LL);
            if ( v24 )
            {
              v25 = *(_QWORD *)(v24 + 96);
              if ( v25 )
              {
                if ( *(_BYTE *)(v25 + 1177) )
                {
                  if ( byte_10316E7C7 || (qword_10317B120 & 2) != 0 )
                    utassert_fail(1u, "false", "Sql\\Ntdbms\\storeng\\drs\\fixedvarrecord.cpp", 2017, 0);
                  else
                    ex_raise(34, 68, 21, 1004);
                }
              }
            }
            v16 = v279;
          }
          RaiseInconsistencyError(v16, 4);
          v23 = v281;
          v16 = v279;
        }
        v19 = *(_WORD *)&v20[2 * v282] & 0x7FFF;
        v278 = v19;
        if ( v23 > v19 )
        {
          if ( byte_10316E8D7 || (qword_10317B120 & 1) != 0 )
          {
            v26 = *(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                            + SystemThread_TlsOffset
                            + 8LL);
            if ( v26 )
            {
              v27 = *(_QWORD *)(v26 + 96);
              if ( v27 )
              {
                if ( *(_BYTE *)(v27 + 1177) )
                {
                  if ( byte_10316E7C7 || (qword_10317B120 & 2) != 0 )
                    utassert_fail(1u, "false", "Sql\\Ntdbms\\storeng\\drs\\fixedvarrecord.cpp", 2024, 0);
                  else
                    ex_raise(34, 68, 21, 1004);
                }
              }
            }
            v16 = v279;
          }
          RaiseInconsistencyError(v16, 4);
          v23 = v281;
          v16 = v279;
          v19 = v278;
        }
        while ( *(__int16 *)&v20[2 * v282] < 0 )
        {
          v28 = &v16[HIDWORD(v280)];
          if ( v282 == 1 )
          {
            v29 = v23;
            v30 = 1;
          }
          else
          {
            v30 = v282;
            v29 = *(_WORD *)&v28[2 * v282 - 2] & 0x7FFF;
          }
          v31 = *(_WORD *)&v28[2 * v30] & 0x7FFF;
          if ( v29 < v23 || v31 < v29 )
          {
            RaiseInconsistencyError(v16, 7);
            v23 = v281;
            v16 = v279;
            v19 = v278;
          }
          if ( v29 < v23 || v29 > v19 )
            goto LABEL_115;
          v32 = *(_WORD *)&v16[v29];
          if ( v32 == 5 )
          {
            v277 |= 2u;
            --v282;
            WORD2(v284) = v29;
            v33 = *(_WORD *)&v16[(unsigned __int16)v29 + 2];
            if ( (v33 & 0x4000) != 0 )
              v34 = (v33 ^ WORD3(v284)) & 0x3800 ^ WORD3(v284);
            else
              v34 = WORD3(v284) & 0xC7FF;
            WORD3(v284) = v34;
            WORD3(v284) = v34 ^ (*(_WORD *)&v16[(unsigned __int16)v29 + 2] ^ v34) & 0x7FF;
            break;
          }
          if ( v32 >= 0x400u )
          {
            v277 |= 1u;
            if ( --v282 )
              continue;
          }
          break;
        }
      }
      else
      {
        v278 = v19;
        v282 = 0;
        v23 = v19;
        v281 = v19;
      }
      if ( (*v16 & 0x40) != 0 )
      {
        LODWORD(v284) = v19;
        v278 = v19 + 14;
        VersioningInfo = FixedVarRecord::FindVersioningInfo((FixedVarRecord *)&v277);
        v36 = HIDWORD(*(_QWORD *)VersioningInfo);
        v37 = HIWORD(*(_QWORD *)VersioningInfo);
        v38 = 0;
        if ( (((__int16)v37 ^ ((unsigned int)(__int16)v37 >> 1)) & 0x2000) != 0 )
        {
          v39 = v37 & 0xDFFF;
          if ( (v37 & 0x4000) != 0 )
            v39 = v37 | 0x2000;
          LOWORD(v37) = v39;
        }
        if ( (_WORD)v37 == 0xFFFC )
          v38 = (unsigned __int16)v36 >> 5;
        v19 = v38 + v278;
        v278 += v38;
        v23 = v281;
        v16 = v279;
      }
      else
      {
        LODWORD(v284) = 0;
      }
      if ( v283 && v283 < (unsigned __int64)&v16[v19] )
      {
        if ( byte_10316E8D7 || (qword_10317B120 & 1) != 0 )
        {
          v40 = *(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                          + SystemThread_TlsOffset
                          + 8LL);
          if ( v40 )
          {
            v41 = *(_QWORD *)(v40 + 96);
            if ( v41 )
            {
              if ( *(_BYTE *)(v41 + 1177) )
              {
                if ( byte_10316E7C7 || (qword_10317B120 & 2) != 0 )
                  utassert_fail(1u, "false", "Sql\\Ntdbms\\storeng\\drs\\fixedvarrecord.cpp", 2114, 0);
                else
                  ex_raise(34, 68, 21, 1018);
              }
            }
          }
          v16 = v279;
        }
        RaiseInconsistencyError(v16, 18);
        v23 = v281;
        v16 = v279;
        v19 = v278;
      }
      if ( v19 - 1 > 0x3F3B )
      {
        if ( byte_10316E8D7 || (qword_10317B120 & 1) != 0 )
        {
          v42 = *(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                          + SystemThread_TlsOffset
                          + 8LL);
          if ( v42 )
          {
            v43 = *(_QWORD *)(v42 + 96);
            if ( v43 )
            {
              if ( *(_BYTE *)(v43 + 1177) )
              {
                if ( byte_10316E7C7 || (qword_10317B120 & 2) != 0 )
                  utassert_fail(1u, "false", "Sql\\Ntdbms\\storeng\\drs\\fixedvarrecord.cpp", 2119, 0);
                else
                  ex_raise(34, 68, 21, 1005);
              }
            }
          }
          v16 = v279;
        }
        RaiseInconsistencyError(v16, 5);
        v23 = v281;
        v16 = v279;
      }
    }
LABEL_115:
    v44 = -(__int16)v262;
    if ( (v264 & 0x10) == 0 )
      goto LABEL_118;
    if ( (*v16 & 0x10) != 0 )
    {
      if ( v262 < (int)v280 && *(_WORD *)&v16[(unsigned int)v280] >= v263 )
      {
LABEL_118:
        if ( v44 > (unsigned int)v282 )
        {
          v13 = v16;
          v261 = 0;
        }
        else
        {
          v45 = &v16[HIDWORD(v280)];
          if ( v44 == 1 )
          {
            v46 = v23;
          }
          else
          {
            _mm_lfence();
            v46 = *(_WORD *)&v45[2 * v44 - 2] & 0x7FFF;
            v23 = v281;
            v16 = v279;
          }
          v47 = *(_WORD *)&v45[2 * v44] & 0x7FFF;
          if ( v46 < v23 || v47 < v46 )
          {
            RaiseInconsistencyError(v16, 7);
            v16 = v279;
          }
          v13 = &v16[v46];
          v48 = v47 - v46;
          v3 = v273;
          v261 = v48;
        }
        goto LABEL_140;
      }
    }
    else if ( ((1 << (*v16 & 0xE)) & 0x1105) == 0 )
    {
      goto LABEL_118;
    }
    v13 = (const unsigned __int8 *)(v265 + 1);
    v261 = *v265;
    goto LABEL_140;
  }
  v266 = 0;
  v13 = CDRecord::LocateColumnInternal(
          (CDRecord *)&v277,
          (const struct PhysicalColumnAttribute *)&v262,
          v12,
          &v261,
          &v266);
  if ( v276 && v280 && *(_QWORD *)v280 && (v264 & 8) == 0 && (v266 & 1) == 0 )
  {
    if ( !v13 || v13 == &g_bitValueOne )
    {
      v261 = 0;
      v13 = 0;
    }
    else
    {
      LODWORD(DestinationSize) = 0;
      v13 = PageComprMgr::DecompressColumnPartialInline(
              v280,
              (const struct PhysicalColumnAttribute *)&v262,
              v13,
              v261,
              0,
              DestinationSize,
              &v261,
              v266);
    }
  }
LABEL_140:
  if ( !v13 || v261 != 2 )
    RaiseFileHdrErr(v3, 21, *a2, (wchar_t *)L"FGID");
  *((_WORD *)a2 + 5) = *(_WORD *)v13;
  v262 = -3;
  v263 = 3;
  v49 = v264 & 0xFFE0;
  v264 &= 0xFFE0u;
  v265 = 0;
  if ( !v276 )
  {
    if ( (*v279 & 0x10) != 0 )
    {
      if ( (int)v280 > -3 )
      {
        if ( *(_WORD *)&v279[(unsigned int)v280] >= 3u )
        {
          LOBYTE(v50) = v279[(unsigned int)v280 + 2] >> 2;
          v51 = 1;
        }
        else
        {
          v50 = ~(v49 >> 4);
          v51 = 0;
        }
      }
      else
      {
        v50 = ~(v49 >> 4);
        v51 = 0;
      }
    }
    else
    {
      if ( ((1 << (*v279 & 0xE)) & 0x1105) == 0 )
        goto LABEL_157;
      LOBYTE(v50) = ~(unsigned __int8)(v49 >> 4);
      v51 = 0;
    }
    if ( (v50 & 1) != 0 )
    {
      v52 = 0;
      v261 = 0;
      goto LABEL_268;
    }
    if ( !v51 && (v264 & 0x10) != 0 )
    {
      v52 = (const unsigned __int8 *)4;
      v261 = *v265;
      goto LABEL_268;
    }
LABEL_157:
    if ( !v278 )
    {
      v277 = 0;
      v53 = (unsigned int)v280;
      HIDWORD(v280) = (_DWORD)v280;
      if ( (*v279 & 0x10) != 0 )
      {
        v53 = (((unsigned int)*(unsigned __int16 *)&v279[(unsigned int)v280] + 7) >> 3) + (_DWORD)v280 + 2;
        HIDWORD(v280) = v53;
      }
      if ( (*v279 & 0x20) != 0 )
      {
        v54 = &v279[v53];
        v282 = *(_WORD *)v54;
        if ( !v282 )
        {
          if ( byte_10316E8D7 || (qword_10317B120 & 1) != 0 )
          {
            v55 = *(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                            + SystemThread_TlsOffset
                            + 8LL);
            if ( v55 )
            {
              v56 = *(_QWORD *)(v55 + 96);
              if ( v56 )
              {
                if ( *(_BYTE *)(v56 + 1177) )
                {
                  if ( byte_10316E7C7 || (qword_10317B120 & 2) != 0 )
                    utassert_fail(1u, "false", "Sql\\Ntdbms\\storeng\\drs\\fixedvarrecord.cpp", 2010, 0);
                  else
                    ex_raise(34, 68, 21, 1003);
                }
              }
            }
          }
          RaiseInconsistencyError(v279, 3);
        }
        v281 = HIDWORD(v280) + 2 * (v282 + 1);
        if ( v281 > 0x1F9E )
        {
          if ( byte_10316E8D7 || (qword_10317B120 & 1) != 0 )
          {
            v57 = *(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                            + SystemThread_TlsOffset
                            + 8LL);
            if ( v57 )
            {
              v58 = *(_QWORD *)(v57 + 96);
              if ( v58 )
              {
                if ( *(_BYTE *)(v58 + 1177) )
                {
                  if ( byte_10316E7C7 || (qword_10317B120 & 2) != 0 )
                    utassert_fail(1u, "false", "Sql\\Ntdbms\\storeng\\drs\\fixedvarrecord.cpp", 2017, 0);
                  else
                    ex_raise(34, 68, 21, 1004);
                }
              }
            }
          }
          RaiseInconsistencyError(v279, 4);
        }
        v278 = *(_WORD *)&v54[2 * v282] & 0x7FFF;
        if ( v281 > v278 )
        {
          if ( byte_10316E8D7 || (qword_10317B120 & 1) != 0 )
          {
            v59 = *(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                            + SystemThread_TlsOffset
                            + 8LL);
            if ( v59 )
            {
              v60 = *(_QWORD *)(v59 + 96);
              if ( v60 )
              {
                if ( *(_BYTE *)(v60 + 1177) )
                {
                  if ( byte_10316E7C7 || (qword_10317B120 & 2) != 0 )
                    utassert_fail(1u, "false", "Sql\\Ntdbms\\storeng\\drs\\fixedvarrecord.cpp", 2024, 0);
                  else
                    ex_raise(34, 68, 21, 1004);
                }
              }
            }
          }
          RaiseInconsistencyError(v279, 4);
        }
        while ( *(__int16 *)&v54[2 * v282] < 0 )
        {
          v61 = &v279[HIDWORD(v280)];
          if ( v282 == 1 )
          {
            v62 = v281;
            v63 = 1;
          }
          else
          {
            v63 = v282;
            v62 = *(_WORD *)&v61[2 * v282 - 2] & 0x7FFF;
          }
          v64 = *(_WORD *)&v61[2 * v63] & 0x7FFF;
          if ( v62 < v281 || v64 < v62 )
            RaiseInconsistencyError(v279, 7);
          if ( v62 < v281 || v62 > v278 )
            goto LABEL_244;
          v65 = *(_WORD *)&v279[v62];
          if ( v65 == 5 )
          {
            v277 |= 2u;
            --v282;
            WORD2(v284) = v62;
            v66 = &v279[(unsigned __int16)v62];
            v67 = *((_WORD *)v66 + 1);
            if ( (v67 & 0x4000) != 0 )
              v68 = (v67 ^ WORD3(v284)) & 0x3800 ^ WORD3(v284);
            else
              v68 = WORD3(v284) & 0xC7FF;
            WORD3(v284) = v68;
            WORD3(v284) = v68 ^ (*((_WORD *)v66 + 1) ^ v68) & 0x7FF;
            break;
          }
          if ( v65 >= 0x400u )
          {
            v277 |= 1u;
            if ( --v282 )
              continue;
          }
          break;
        }
      }
      else
      {
        v278 = v53;
        v282 = 0;
        v281 = v53;
      }
      if ( (*v279 & 0x40) != 0 )
      {
        LODWORD(v284) = v278;
        v278 += 14;
        v69 = FixedVarRecord::FindVersioningInfo((FixedVarRecord *)&v277);
        v70 = HIDWORD(*(_QWORD *)v69);
        v71 = HIWORD(*(_QWORD *)v69);
        v72 = 0;
        if ( (((__int16)v71 ^ ((unsigned int)(__int16)v71 >> 1)) & 0x2000) != 0 )
        {
          v73 = v71 & 0xDFFF;
          if ( (v71 & 0x4000) != 0 )
            v73 = v71 | 0x2000;
          LOWORD(v71) = v73;
        }
        if ( (_WORD)v71 == 0xFFFC )
          v72 = (unsigned __int16)v70 >> 5;
        v278 += v72;
      }
      else
      {
        LODWORD(v284) = 0;
      }
      if ( v283 && v283 < (unsigned __int64)&v279[v278] )
      {
        if ( byte_10316E8D7 || (qword_10317B120 & 1) != 0 )
        {
          v74 = *(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                          + SystemThread_TlsOffset
                          + 8LL);
          if ( v74 )
          {
            v75 = *(_QWORD *)(v74 + 96);
            if ( v75 )
            {
              if ( *(_BYTE *)(v75 + 1177) )
              {
                if ( byte_10316E7C7 || (qword_10317B120 & 2) != 0 )
                  utassert_fail(1u, "false", "Sql\\Ntdbms\\storeng\\drs\\fixedvarrecord.cpp", 2114, 0);
                else
                  ex_raise(34, 68, 21, 1018);
              }
            }
          }
        }
        RaiseInconsistencyError(v279, 18);
      }
      if ( v278 - 1 > 0x3F3B )
      {
        if ( byte_10316E8D7 || (qword_10317B120 & 1) != 0 )
        {
          v76 = *(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                          + SystemThread_TlsOffset
                          + 8LL);
          if ( v76 )
          {
            v77 = *(_QWORD *)(v76 + 96);
            if ( v77 )
            {
              if ( *(_BYTE *)(v77 + 1177) )
              {
                if ( byte_10316E7C7 || (qword_10317B120 & 2) != 0 )
                  utassert_fail(1u, "false", "Sql\\Ntdbms\\storeng\\drs\\fixedvarrecord.cpp", 2119, 0);
                else
                  ex_raise(34, 68, 21, 1005);
              }
            }
          }
        }
        RaiseInconsistencyError(v279, 5);
      }
    }
LABEL_244:
    v78 = -(__int16)v262;
    if ( (v264 & 0x10) == 0 )
      goto LABEL_247;
    if ( (*v279 & 0x10) != 0 )
    {
      if ( v262 < (int)v280 && *(_WORD *)&v279[(unsigned int)v280] >= v263 )
      {
LABEL_247:
        if ( v78 > (unsigned int)v282 )
        {
          v52 = v279;
          v261 = 0;
        }
        else
        {
          v79 = &v279[HIDWORD(v280)];
          if ( v78 == 1 )
          {
            v80 = v281;
          }
          else
          {
            _mm_lfence();
            v80 = *(_WORD *)&v79[2 * v78 - 2] & 0x7FFF;
          }
          v81 = *(_WORD *)&v79[2 * v78] & 0x7FFF;
          if ( v80 < v281 || v81 < v80 )
            RaiseInconsistencyError(v279, 7);
          v52 = &v279[v80];
          v261 = v81 - v80;
        }
        goto LABEL_268;
      }
    }
    else if ( ((1 << (*v279 & 0xE)) & 0x1105) == 0 )
    {
      goto LABEL_247;
    }
    v52 = (const unsigned __int8 *)(v265 + 1);
    v261 = *v265;
    goto LABEL_268;
  }
  v267 = 0;
  v52 = CDRecord::LocateColumnInternal(
          (CDRecord *)&v277,
          (const struct PhysicalColumnAttribute *)&v262,
          v49,
          &v261,
          &v267);
  if ( v276 && v280 && *(_QWORD *)v280 && (v264 & 8) == 0 && (v267 & 1) == 0 )
  {
    if ( !v52 || v52 == &g_bitValueOne )
    {
      v261 = 0;
      v52 = 0;
    }
    else
    {
      LODWORD(DestinationSize) = 0;
      v52 = PageComprMgr::DecompressColumnPartialInline(
              v280,
              (const struct PhysicalColumnAttribute *)&v262,
              v52,
              v261,
              0,
              DestinationSize,
              &v261,
              v267);
    }
  }
LABEL_268:
  if ( v52 && v261 == 2 )
  {
    v82 = v273;
  }
  else
  {
    v82 = v273;
    RaiseFileHdrErr(v273, 22, *a2, (wchar_t *)L"FILEID");
  }
  if ( *((_WORD *)a2 + 4) != *(_WORD *)v52 )
  {
    BackupResultSet::EndResultSet(v82, 1);
    do
      ++v5;
    while ( (*a2)[v5] );
    LODWORD(Destination) = 2 * v5;
    ex_raise(51, 71, 16, 22, Destination, *a2);
  }
  v262 = -5;
  v263 = 5;
  v83 = v264 & 0xFFE0;
  v264 &= 0xFFE0u;
  v265 = 0;
  if ( !v276 )
  {
    if ( (*v279 & 0x10) != 0 )
    {
      if ( (int)v280 > -5 )
      {
        if ( *(_WORD *)&v279[(unsigned int)v280] >= 5u )
        {
          LOBYTE(v84) = v279[(unsigned int)v280 + 2] >> 4;
          v85 = 1;
        }
        else
        {
          v84 = ~(v83 >> 4);
          v85 = 0;
        }
      }
      else
      {
        v84 = ~(v83 >> 4);
        v85 = 0;
      }
    }
    else
    {
      if ( ((1 << (*v279 & 0xE)) & 0x1105) == 0 )
        goto LABEL_290;
      LOBYTE(v84) = ~(unsigned __int8)(v83 >> 4);
      v85 = 0;
    }
    if ( (v84 & 1) != 0 )
    {
      v86 = 0;
      v261 = 0;
      goto LABEL_401;
    }
    if ( !v85 && (v264 & 0x10) != 0 )
    {
      v86 = (const unsigned __int8 *)4;
      v261 = *v265;
      goto LABEL_401;
    }
LABEL_290:
    if ( !v278 )
    {
      v277 = 0;
      v87 = (unsigned int)v280;
      HIDWORD(v280) = (_DWORD)v280;
      if ( (*v279 & 0x10) != 0 )
      {
        v87 = (((unsigned int)*(unsigned __int16 *)&v279[(unsigned int)v280] + 7) >> 3) + (_DWORD)v280 + 2;
        HIDWORD(v280) = v87;
      }
      if ( (*v279 & 0x20) != 0 )
      {
        v88 = &v279[v87];
        v282 = *(_WORD *)v88;
        if ( !v282 )
        {
          if ( byte_10316E8D7 || (qword_10317B120 & 1) != 0 )
          {
            v89 = *(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                            + SystemThread_TlsOffset
                            + 8LL);
            if ( v89 )
            {
              v90 = *(_QWORD *)(v89 + 96);
              if ( v90 )
              {
                if ( *(_BYTE *)(v90 + 1177) )
                {
                  if ( byte_10316E7C7 || (qword_10317B120 & 2) != 0 )
                    utassert_fail(1u, "false", "Sql\\Ntdbms\\storeng\\drs\\fixedvarrecord.cpp", 2010, 0);
                  else
                    ex_raise(34, 68, 21, 1003);
                }
              }
            }
          }
          RaiseInconsistencyError(v279, 3);
        }
        v281 = HIDWORD(v280) + 2 * (v282 + 1);
        if ( v281 > 0x1F9E )
        {
          if ( byte_10316E8D7 || (qword_10317B120 & 1) != 0 )
          {
            v91 = *(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                            + SystemThread_TlsOffset
                            + 8LL);
            if ( v91 )
            {
              v92 = *(_QWORD *)(v91 + 96);
              if ( v92 )
              {
                if ( *(_BYTE *)(v92 + 1177) )
                {
                  if ( byte_10316E7C7 || (qword_10317B120 & 2) != 0 )
                    utassert_fail(1u, "false", "Sql\\Ntdbms\\storeng\\drs\\fixedvarrecord.cpp", 2017, 0);
                  else
                    ex_raise(34, 68, 21, 1004);
                }
              }
            }
          }
          RaiseInconsistencyError(v279, 4);
        }
        v87 = *(_WORD *)&v88[2 * v282] & 0x7FFF;
        v278 = v87;
        if ( v281 > v87 )
        {
          if ( byte_10316E8D7 || (qword_10317B120 & 1) != 0 )
          {
            v93 = *(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                            + SystemThread_TlsOffset
                            + 8LL);
            if ( v93 )
            {
              v94 = *(_QWORD *)(v93 + 96);
              if ( v94 )
              {
                if ( *(_BYTE *)(v94 + 1177) )
                {
                  if ( byte_10316E7C7 || (qword_10317B120 & 2) != 0 )
                    utassert_fail(1u, "false", "Sql\\Ntdbms\\storeng\\drs\\fixedvarrecord.cpp", 2024, 0);
                  else
                    ex_raise(34, 68, 21, 1004);
                }
              }
            }
          }
          RaiseInconsistencyError(v279, 4);
          v87 = v278;
        }
        while ( *(__int16 *)&v88[2 * v282] < 0 )
        {
          v95 = &v279[HIDWORD(v280)];
          if ( v282 == 1 )
          {
            v96 = v281;
            v97 = 1;
          }
          else
          {
            v97 = v282;
            v96 = *(_WORD *)&v95[2 * v282 - 2] & 0x7FFF;
          }
          v98 = *(_WORD *)&v95[2 * v97] & 0x7FFF;
          if ( v96 < v281 || v98 < v96 )
          {
            RaiseInconsistencyError(v279, 7);
            v87 = v278;
          }
          if ( v96 < v281 || v96 > v87 )
            goto LABEL_377;
          v99 = *(_WORD *)&v279[v96];
          if ( v99 == 5 )
          {
            v277 |= 2u;
            --v282;
            WORD2(v284) = v96;
            v100 = &v279[(unsigned __int16)v96];
            v101 = *((_WORD *)v100 + 1);
            if ( (v101 & 0x4000) != 0 )
              v102 = (WORD3(v284) ^ v101) & 0x3800 ^ WORD3(v284);
            else
              v102 = WORD3(v284) & 0xC7FF;
            WORD3(v284) = v102;
            WORD3(v284) = v102 ^ (*((_WORD *)v100 + 1) ^ v102) & 0x7FF;
            break;
          }
          if ( v99 >= 0x400u )
          {
            v277 |= 1u;
            if ( --v282 )
              continue;
          }
          break;
        }
      }
      else
      {
        v278 = v87;
        v282 = 0;
        v281 = v87;
      }
      if ( (*v279 & 0x40) != 0 )
      {
        LODWORD(v284) = v87;
        v278 = v87 + 14;
        v103 = FixedVarRecord::FindVersioningInfo((FixedVarRecord *)&v277);
        v104 = HIDWORD(*(_QWORD *)v103);
        v105 = HIWORD(*(_QWORD *)v103);
        v106 = 0;
        if ( (((__int16)v105 ^ ((unsigned int)(__int16)v105 >> 1)) & 0x2000) != 0 )
        {
          v107 = v105 & 0xDFFF;
          if ( (v105 & 0x4000) != 0 )
            v107 = v105 | 0x2000;
          LOWORD(v105) = v107;
        }
        if ( (_WORD)v105 == 0xFFFC )
          v106 = (unsigned __int16)v104 >> 5;
        v87 = v106 + v278;
        v278 += v106;
      }
      else
      {
        LODWORD(v284) = 0;
      }
      if ( v283 && v283 < (unsigned __int64)&v279[v87] )
      {
        if ( byte_10316E8D7 || (qword_10317B120 & 1) != 0 )
        {
          v108 = *(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                           + SystemThread_TlsOffset
                           + 8LL);
          if ( v108 )
          {
            v109 = *(_QWORD *)(v108 + 96);
            if ( v109 )
            {
              if ( *(_BYTE *)(v109 + 1177) )
              {
                if ( byte_10316E7C7 || (qword_10317B120 & 2) != 0 )
                  utassert_fail(1u, "false", "Sql\\Ntdbms\\storeng\\drs\\fixedvarrecord.cpp", 2114, 0);
                else
                  ex_raise(34, 68, 21, 1018);
              }
            }
          }
        }
        RaiseInconsistencyError(v279, 18);
        v87 = v278;
      }
      if ( v87 - 1 > 0x3F3B )
      {
        if ( byte_10316E8D7 || (qword_10317B120 & 1) != 0 )
        {
          v110 = *(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                           + SystemThread_TlsOffset
                           + 8LL);
          if ( v110 )
          {
            v111 = *(_QWORD *)(v110 + 96);
            if ( v111 )
            {
              if ( *(_BYTE *)(v111 + 1177) )
              {
                if ( byte_10316E7C7 || (qword_10317B120 & 2) != 0 )
                  utassert_fail(1u, "false", "Sql\\Ntdbms\\storeng\\drs\\fixedvarrecord.cpp", 2119, 0);
                else
                  ex_raise(34, 68, 21, 1005);
              }
            }
          }
        }
        RaiseInconsistencyError(v279, 5);
      }
    }
LABEL_377:
    v83 = (unsigned __int16)v262;
    LOWORD(v83) = -(__int16)v262;
    if ( (v264 & 0x10) == 0 )
      goto LABEL_380;
    if ( (*v279 & 0x10) != 0 )
    {
      if ( v262 < (int)v280 && *(_WORD *)&v279[(unsigned int)v280] >= v263 )
      {
LABEL_380:
        if ( (__int16)v83 > (unsigned int)v282 )
        {
          v86 = v279;
          v261 = 0;
        }
        else
        {
          v112 = &v279[HIDWORD(v280)];
          if ( (__int16)v83 == 1 )
          {
            v113 = v281;
          }
          else
          {
            _mm_lfence();
            v113 = *(_WORD *)&v112[2 * (__int16)v83 - 2] & 0x7FFF;
          }
          v114 = *(_WORD *)&v112[2 * (__int16)v83] & 0x7FFF;
          if ( v113 < v281 || v114 < v113 )
            RaiseInconsistencyError(v279, 7);
          v86 = &v279[v113];
          v261 = v114 - v113;
        }
        goto LABEL_401;
      }
    }
    else if ( ((1 << (*v279 & 0xE)) & 0x1105) == 0 )
    {
      goto LABEL_380;
    }
    v86 = (const unsigned __int8 *)(v265 + 1);
    v261 = *v265;
    goto LABEL_401;
  }
  v268 = 0;
  v86 = CDRecord::LocateColumnInternal(
          (CDRecord *)&v277,
          (const struct PhysicalColumnAttribute *)&v262,
          v83,
          &v261,
          &v268);
  if ( v276 && v280 && *(_QWORD *)v280 && (v264 & 8) == 0 && (v268 & 1) == 0 )
  {
    if ( !v86 || v86 == &g_bitValueOne )
    {
      v261 = 0;
      v86 = 0;
    }
    else
    {
      LODWORD(DestinationSize) = 0;
      v86 = PageComprMgr::DecompressColumnPartialInline(
              v280,
              (const struct PhysicalColumnAttribute *)&v262,
              v86,
              v261,
              0,
              DestinationSize,
              &v261,
              v268);
    }
  }
LABEL_401:
  if ( v86 && v261 == 4 )
  {
    v115 = v273;
  }
  else
  {
    v115 = v273;
    RaiseFileHdrErr(v273, 23, *a2, (wchar_t *)L"SIZE");
  }
  *((_DWORD *)a2 + 3) = *(_DWORD *)v86;
  v262 = -6;
  v263 = 6;
  v116 = v264;
  LOWORD(v116) = v264 & 0xFFE0;
  v117 = v264 & 0xFFE0;
  v264 &= 0xFFE0u;
  v265 = 0;
  if ( !v276 )
  {
    v118 = v279;
    if ( (*v279 & 0x10) != 0 )
    {
      if ( (int)v280 > -6 )
      {
        if ( *(_WORD *)&v279[(unsigned int)v280] >= 6u )
        {
          LOBYTE(v119) = v279[(unsigned int)v280 + 2] >> 5;
          v120 = 1;
        }
        else
        {
          v119 = ~(v117 >> 4);
          v120 = 0;
        }
      }
      else
      {
        v119 = ~(v116 >> 4);
        v120 = 0;
      }
    }
    else
    {
      if ( ((1 << (*v279 & 0xE)) & 0x1105) == 0 )
        goto LABEL_419;
      LOBYTE(v119) = ~(unsigned __int8)(v117 >> 4);
      v120 = 0;
    }
    if ( (v119 & 1) != 0 )
    {
      v121 = 0;
      v261 = 0;
      goto LABEL_536;
    }
    if ( !v120 && (v264 & 0x10) != 0 )
    {
      v121 = (const unsigned __int8 *)4;
      v261 = *v265;
      goto LABEL_536;
    }
LABEL_419:
    if ( !v278 )
    {
      v277 = 0;
      v122 = (unsigned int)v280;
      HIDWORD(v280) = (_DWORD)v280;
      if ( (*v279 & 0x10) != 0 )
      {
        v122 = (((unsigned int)*(unsigned __int16 *)&v279[(unsigned int)v280] + 7) >> 3) + (_DWORD)v280 + 2;
        HIDWORD(v280) = v122;
      }
      if ( (*v279 & 0x20) != 0 )
      {
        v123 = &v279[v122];
        v282 = *(_WORD *)v123;
        if ( !v282 )
        {
          if ( byte_10316E8D7 || (qword_10317B120 & 1) != 0 )
          {
            v124 = *(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                             + SystemThread_TlsOffset
                             + 8LL);
            if ( v124 )
            {
              v125 = *(_QWORD *)(v124 + 96);
              if ( v125 )
              {
                if ( *(_BYTE *)(v125 + 1177) )
                {
                  if ( byte_10316E7C7 || (qword_10317B120 & 2) != 0 )
                    utassert_fail(1u, "false", "Sql\\Ntdbms\\storeng\\drs\\fixedvarrecord.cpp", 2010, 0);
                  else
                    ex_raise(34, 68, 21, 1003);
                }
              }
            }
            v118 = v279;
          }
          RaiseInconsistencyError(v118, 3);
          v118 = v279;
        }
        v126 = HIDWORD(v280) + 2 * (v282 + 1);
        v281 = v126;
        if ( v126 > 0x1F9E )
        {
          if ( byte_10316E8D7 || (qword_10317B120 & 1) != 0 )
          {
            v127 = *(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                             + SystemThread_TlsOffset
                             + 8LL);
            if ( v127 )
            {
              v128 = *(_QWORD *)(v127 + 96);
              if ( v128 )
              {
                if ( *(_BYTE *)(v128 + 1177) )
                {
                  if ( byte_10316E7C7 || (qword_10317B120 & 2) != 0 )
                    utassert_fail(1u, "false", "Sql\\Ntdbms\\storeng\\drs\\fixedvarrecord.cpp", 2017, 0);
                  else
                    ex_raise(34, 68, 21, 1004);
                }
              }
            }
            v118 = v279;
          }
          RaiseInconsistencyError(v118, 4);
          v126 = v281;
          v118 = v279;
        }
        v122 = *(_WORD *)&v123[2 * v282] & 0x7FFF;
        v278 = v122;
        if ( v126 > v122 )
        {
          if ( byte_10316E8D7 || (qword_10317B120 & 1) != 0 )
          {
            v129 = *(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                             + SystemThread_TlsOffset
                             + 8LL);
            if ( v129 )
            {
              v130 = *(_QWORD *)(v129 + 96);
              if ( v130 )
              {
                if ( *(_BYTE *)(v130 + 1177) )
                {
                  if ( byte_10316E7C7 || (qword_10317B120 & 2) != 0 )
                    utassert_fail(1u, "false", "Sql\\Ntdbms\\storeng\\drs\\fixedvarrecord.cpp", 2024, 0);
                  else
                    ex_raise(34, 68, 21, 1004);
                }
              }
            }
            v118 = v279;
          }
          RaiseInconsistencyError(v118, 4);
          v126 = v281;
          v118 = v279;
          v122 = v278;
        }
        while ( *(__int16 *)&v123[2 * v282] < 0 )
        {
          v131 = &v118[HIDWORD(v280)];
          if ( v282 == 1 )
          {
            v132 = v126;
            v133 = 1;
          }
          else
          {
            v133 = v282;
            v132 = *(_WORD *)&v131[2 * v282 - 2] & 0x7FFF;
          }
          v134 = *(_WORD *)&v131[2 * v133] & 0x7FFF;
          if ( v132 < v126 || v134 < v132 )
          {
            RaiseInconsistencyError(v118, 7);
            v126 = v281;
            v118 = v279;
            v122 = v278;
          }
          if ( v132 < v126 || v132 > v122 )
            goto LABEL_512;
          v135 = *(_WORD *)&v118[v132];
          if ( v135 == 5 )
          {
            v277 |= 2u;
            --v282;
            WORD2(v284) = v132;
            v136 = *(_WORD *)&v118[(unsigned __int16)v132 + 2];
            if ( (v136 & 0x4000) != 0 )
              v137 = (WORD3(v284) ^ v136) & 0x3800 ^ WORD3(v284);
            else
              v137 = WORD3(v284) & 0xC7FF;
            WORD3(v284) = v137;
            WORD3(v284) = v137 ^ (*(_WORD *)&v118[(unsigned __int16)v132 + 2] ^ v137) & 0x7FF;
            break;
          }
          if ( v135 >= 0x400u )
          {
            v277 |= 1u;
            if ( --v282 )
              continue;
          }
          break;
        }
      }
      else
      {
        v278 = v122;
        v282 = 0;
        v126 = v122;
        v281 = v122;
      }
      if ( (*v118 & 0x40) != 0 )
      {
        LODWORD(v284) = v122;
        v278 = v122 + 14;
        v138 = FixedVarRecord::FindVersioningInfo((FixedVarRecord *)&v277);
        v139 = HIDWORD(*(_QWORD *)v138);
        v140 = HIWORD(*(_QWORD *)v138);
        v141 = 0;
        if ( (((__int16)v140 ^ ((unsigned int)(__int16)v140 >> 1)) & 0x2000) != 0 )
        {
          v142 = v140 & 0xDFFF;
          if ( (v140 & 0x4000) != 0 )
            v142 = v140 | 0x2000;
          LOWORD(v140) = v142;
        }
        if ( (_WORD)v140 == 0xFFFC )
          v141 = (unsigned __int16)v139 >> 5;
        v122 = v141 + v278;
        v278 += v141;
        v126 = v281;
        v118 = v279;
      }
      else
      {
        LODWORD(v284) = 0;
      }
      if ( v283 && v283 < (unsigned __int64)&v118[v122] )
      {
        if ( byte_10316E8D7 || (qword_10317B120 & 1) != 0 )
        {
          v143 = *(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                           + SystemThread_TlsOffset
                           + 8LL);
          if ( v143 )
          {
            v144 = *(_QWORD *)(v143 + 96);
            if ( v144 )
            {
              if ( *(_BYTE *)(v144 + 1177) )
              {
                if ( byte_10316E7C7 || (qword_10317B120 & 2) != 0 )
                  utassert_fail(1u, "false", "Sql\\Ntdbms\\storeng\\drs\\fixedvarrecord.cpp", 2114, 0);
                else
                  ex_raise(34, 68, 21, 1018);
              }
            }
          }
          v118 = v279;
        }
        RaiseInconsistencyError(v118, 18);
        v126 = v281;
        v118 = v279;
        v122 = v278;
      }
      if ( v122 - 1 <= 0x3F3B )
      {
LABEL_512:
        v147 = -(__int16)v262;
        if ( (v264 & 0x10) == 0 )
          goto LABEL_515;
        if ( (*v118 & 0x10) != 0 )
        {
          if ( v262 < (int)v280 && *(_WORD *)&v118[(unsigned int)v280] >= v263 )
          {
LABEL_515:
            if ( v147 > (unsigned int)v282 )
            {
              v121 = v118;
              v261 = 0;
            }
            else
            {
              v148 = &v118[HIDWORD(v280)];
              if ( v147 == 1 )
              {
                v149 = v126;
              }
              else
              {
                _mm_lfence();
                v149 = *(_WORD *)&v148[2 * v147 - 2] & 0x7FFF;
                v126 = v281;
                v118 = v279;
              }
              v150 = *(_WORD *)&v148[2 * v147] & 0x7FFF;
              if ( v149 < v126 || v150 < v149 )
              {
                RaiseInconsistencyError(v118, 7);
                v118 = v279;
              }
              v121 = &v118[v149];
              v261 = v150 - v149;
            }
            goto LABEL_536;
          }
        }
        else if ( ((1 << (*v118 & 0xE)) & 0x1105) == 0 )
        {
          goto LABEL_515;
        }
        v121 = (const unsigned __int8 *)(v265 + 1);
        v261 = *v265;
        goto LABEL_536;
      }
      if ( byte_10316E8D7 || (qword_10317B120 & 1) != 0 )
      {
        v145 = *(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                         + SystemThread_TlsOffset
                         + 8LL);
        if ( v145 )
        {
          v146 = *(_QWORD *)(v145 + 96);
          if ( v146 )
          {
            if ( *(_BYTE *)(v146 + 1177) )
            {
              if ( byte_10316E7C7 || (qword_10317B120 & 2) != 0 )
                utassert_fail(1u, "false", "Sql\\Ntdbms\\storeng\\drs\\fixedvarrecord.cpp", 2119, 0);
              else
                ex_raise(34, 68, 21, 1005);
            }
          }
        }
        v118 = v279;
      }
      RaiseInconsistencyError(v118, 5);
      v118 = v279;
    }
    v126 = v281;
    goto LABEL_512;
  }
  v269 = 0;
  v121 = CDRecord::LocateColumnInternal(
           (CDRecord *)&v277,
           (const struct PhysicalColumnAttribute *)&v262,
           v83,
           &v261,
           &v269);
  if ( v276 && v280 && *(_QWORD *)v280 && (v264 & 8) == 0 && (v269 & 1) == 0 )
  {
    if ( !v121 || v121 == &g_bitValueOne )
    {
      v261 = 0;
      v121 = 0;
    }
    else
    {
      LODWORD(DestinationSize) = 0;
      v121 = PageComprMgr::DecompressColumnPartialInline(
               v280,
               (const struct PhysicalColumnAttribute *)&v262,
               v121,
               v261,
               0,
               DestinationSize,
               &v261,
               v269);
    }
  }
LABEL_536:
  if ( !v121 || v261 != 4 )
    RaiseFileHdrErr(v115, 24, *a2, (wchar_t *)L"MAXSIZE");
  *((_DWORD *)a2 + 4) = *(_DWORD *)v121;
  v262 = -7;
  v263 = 7;
  v151 = v264;
  LOWORD(v151) = v264 & 0xFFE0;
  v152 = v264 & 0xFFE0;
  v264 &= 0xFFE0u;
  v265 = 0;
  if ( !v276 )
  {
    v153 = v279;
    if ( (*v279 & 0x10) != 0 )
    {
      if ( (int)v280 > -7 )
      {
        if ( *(_WORD *)&v279[(unsigned int)v280] >= 7u )
        {
          LOBYTE(v154) = v279[(unsigned int)v280 + 2] >> 6;
          v155 = 1;
        }
        else
        {
          v154 = ~(v152 >> 4);
          v155 = 0;
        }
      }
      else
      {
        v154 = ~(v151 >> 4);
        v155 = 0;
      }
    }
    else
    {
      if ( ((1 << (*v279 & 0xE)) & 0x1105) == 0 )
        goto LABEL_553;
      LOBYTE(v154) = ~(unsigned __int8)(v152 >> 4);
      v155 = 0;
    }
    if ( (v154 & 1) != 0 )
    {
      v156 = 0;
      v261 = 0;
      goto LABEL_670;
    }
    if ( !v155 && (v264 & 0x10) != 0 )
    {
      v156 = (const unsigned __int8 *)4;
      v261 = *v265;
      goto LABEL_670;
    }
LABEL_553:
    if ( v278 )
    {
      v161 = v281;
    }
    else
    {
      v277 = 0;
      v157 = (unsigned int)v280;
      HIDWORD(v280) = (_DWORD)v280;
      if ( (*v279 & 0x10) != 0 )
      {
        v157 = (((unsigned int)*(unsigned __int16 *)&v279[(unsigned int)v280] + 7) >> 3) + (_DWORD)v280 + 2;
        HIDWORD(v280) = v157;
      }
      if ( (*v279 & 0x20) != 0 )
      {
        v158 = &v279[v157];
        v282 = *(_WORD *)v158;
        if ( !v282 )
        {
          if ( byte_10316E8D7 || (qword_10317B120 & 1) != 0 )
          {
            v159 = *(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                             + SystemThread_TlsOffset
                             + 8LL);
            if ( v159 )
            {
              v160 = *(_QWORD *)(v159 + 96);
              if ( v160 )
              {
                if ( *(_BYTE *)(v160 + 1177) )
                {
                  if ( byte_10316E7C7 || (qword_10317B120 & 2) != 0 )
                    utassert_fail(1u, "false", "Sql\\Ntdbms\\storeng\\drs\\fixedvarrecord.cpp", 2010, 0);
                  else
                    ex_raise(34, 68, 21, 1003);
                }
              }
            }
            v153 = v279;
          }
          RaiseInconsistencyError(v153, 3);
          v153 = v279;
        }
        v161 = HIDWORD(v280) + 2 * (v282 + 1);
        v281 = v161;
        if ( v161 > 0x1F9E )
        {
          if ( byte_10316E8D7 || (qword_10317B120 & 1) != 0 )
          {
            v162 = *(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                             + SystemThread_TlsOffset
                             + 8LL);
            if ( v162 )
            {
              v163 = *(_QWORD *)(v162 + 96);
              if ( v163 )
              {
                if ( *(_BYTE *)(v163 + 1177) )
                {
                  if ( byte_10316E7C7 || (qword_10317B120 & 2) != 0 )
                    utassert_fail(1u, "false", "Sql\\Ntdbms\\storeng\\drs\\fixedvarrecord.cpp", 2017, 0);
                  else
                    ex_raise(34, 68, 21, 1004);
                }
              }
            }
            v153 = v279;
          }
          RaiseInconsistencyError(v153, 4);
          v161 = v281;
          v153 = v279;
        }
        v157 = *(_WORD *)&v158[2 * v282] & 0x7FFF;
        v278 = v157;
        if ( v161 > v157 )
        {
          if ( byte_10316E8D7 || (qword_10317B120 & 1) != 0 )
          {
            v164 = *(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                             + SystemThread_TlsOffset
                             + 8LL);
            if ( v164 )
            {
              v165 = *(_QWORD *)(v164 + 96);
              if ( v165 )
              {
                if ( *(_BYTE *)(v165 + 1177) )
                {
                  if ( byte_10316E7C7 || (qword_10317B120 & 2) != 0 )
                    utassert_fail(1u, "false", "Sql\\Ntdbms\\storeng\\drs\\fixedvarrecord.cpp", 2024, 0);
                  else
                    ex_raise(34, 68, 21, 1004);
                }
              }
            }
            v153 = v279;
          }
          RaiseInconsistencyError(v153, 4);
          v161 = v281;
          v153 = v279;
          v157 = v278;
        }
        while ( *(__int16 *)&v158[2 * v282] < 0 )
        {
          v166 = &v153[HIDWORD(v280)];
          if ( v282 == 1 )
          {
            v167 = v161;
            v168 = 1;
          }
          else
          {
            v168 = v282;
            v167 = *(_WORD *)&v166[2 * v282 - 2] & 0x7FFF;
          }
          v169 = *(_WORD *)&v166[2 * v168] & 0x7FFF;
          if ( v167 < v161 || v169 < v167 )
          {
            RaiseInconsistencyError(v153, 7);
            v161 = v281;
            v153 = v279;
            v157 = v278;
          }
          if ( v167 < v161 || v167 > v157 )
            goto LABEL_645;
          v170 = *(_WORD *)&v153[v167];
          if ( v170 == 5 )
          {
            v277 |= 2u;
            --v282;
            WORD2(v284) = v167;
            v171 = *(_WORD *)&v153[(unsigned __int16)v167 + 2];
            if ( (v171 & 0x4000) != 0 )
              v172 = (v171 ^ WORD3(v284)) & 0x3800 ^ WORD3(v284);
            else
              v172 = WORD3(v284) & 0xC7FF;
            WORD3(v284) = v172;
            WORD3(v284) = v172 ^ (*(_WORD *)&v153[(unsigned __int16)v167 + 2] ^ v172) & 0x7FF;
            break;
          }
          if ( v170 >= 0x400u )
          {
            v277 |= 1u;
            if ( --v282 )
              continue;
          }
          break;
        }
      }
      else
      {
        v278 = v157;
        v282 = 0;
        v161 = v157;
        v281 = v157;
      }
      if ( (*v153 & 0x40) != 0 )
      {
        LODWORD(v284) = v157;
        v278 = v157 + 14;
        v173 = FixedVarRecord::FindVersioningInfo((FixedVarRecord *)&v277);
        v174 = HIDWORD(*(_QWORD *)v173);
        v175 = HIWORD(*(_QWORD *)v173);
        v176 = 0;
        if ( (((__int16)v175 ^ ((unsigned int)(__int16)v175 >> 1)) & 0x2000) != 0 )
        {
          v177 = v175 & 0xDFFF;
          if ( (v175 & 0x4000) != 0 )
            v177 = v175 | 0x2000;
          LOWORD(v175) = v177;
        }
        if ( (_WORD)v175 == 0xFFFC )
          v176 = (unsigned __int16)v174 >> 5;
        v157 = v176 + v278;
        v278 += v176;
        v161 = v281;
        v153 = v279;
      }
      else
      {
        LODWORD(v284) = 0;
      }
      if ( v283 && v283 < (unsigned __int64)&v153[v157] )
      {
        if ( byte_10316E8D7 || (qword_10317B120 & 1) != 0 )
        {
          v178 = *(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                           + SystemThread_TlsOffset
                           + 8LL);
          if ( v178 )
          {
            v179 = *(_QWORD *)(v178 + 96);
            if ( v179 )
            {
              if ( *(_BYTE *)(v179 + 1177) )
              {
                if ( byte_10316E7C7 || (qword_10317B120 & 2) != 0 )
                  utassert_fail(1u, "false", "Sql\\Ntdbms\\storeng\\drs\\fixedvarrecord.cpp", 2114, 0);
                else
                  ex_raise(34, 68, 21, 1018);
              }
            }
          }
          v153 = v279;
        }
        RaiseInconsistencyError(v153, 18);
        v161 = v281;
        v153 = v279;
        v157 = v278;
      }
      if ( v157 - 1 > 0x3F3B )
      {
        if ( byte_10316E8D7 || (qword_10317B120 & 1) != 0 )
        {
          v180 = *(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                           + SystemThread_TlsOffset
                           + 8LL);
          if ( v180 )
          {
            v181 = *(_QWORD *)(v180 + 96);
            if ( v181 )
            {
              if ( *(_BYTE *)(v181 + 1177) )
              {
                if ( byte_10316E7C7 || (qword_10317B120 & 2) != 0 )
                  utassert_fail(1u, "false", "Sql\\Ntdbms\\storeng\\drs\\fixedvarrecord.cpp", 2119, 0);
                else
                  ex_raise(34, 68, 21, 1005);
              }
            }
          }
          v153 = v279;
        }
        RaiseInconsistencyError(v153, 5);
        v161 = v281;
        v153 = v279;
      }
    }
LABEL_645:
    v182 = -(__int16)v262;
    if ( (v264 & 0x10) == 0 )
      goto LABEL_648;
    if ( (*v153 & 0x10) != 0 )
    {
      if ( v262 < (int)v280 && *(_WORD *)&v153[(unsigned int)v280] >= v263 )
      {
LABEL_648:
        if ( v182 > (unsigned int)v282 )
        {
          v156 = v153;
          v261 = 0;
        }
        else
        {
          v183 = &v153[HIDWORD(v280)];
          if ( v182 == 1 )
          {
            v184 = v161;
          }
          else
          {
            _mm_lfence();
            v184 = *(_WORD *)&v183[2 * v182 - 2] & 0x7FFF;
            v161 = v281;
            v153 = v279;
          }
          v185 = *(_WORD *)&v183[2 * v182] & 0x7FFF;
          if ( v184 < v161 || v185 < v184 )
          {
            RaiseInconsistencyError(v153, 7);
            v153 = v279;
          }
          v156 = &v153[v184];
          v261 = v185 - v184;
        }
        goto LABEL_670;
      }
    }
    else if ( ((1 << (*v153 & 0xE)) & 0x1105) == 0 )
    {
      goto LABEL_648;
    }
    v156 = (const unsigned __int8 *)(v265 + 1);
    v261 = *v265;
    goto LABEL_670;
  }
  v270 = 0;
  v156 = CDRecord::LocateColumnInternal(
           (CDRecord *)&v277,
           (const struct PhysicalColumnAttribute *)&v262,
           (int)v118,
           &v261,
           &v270);
  if ( v276 && v280 && *(_QWORD *)v280 && (v264 & 8) == 0 && (v270 & 1) == 0 )
  {
    if ( !v156 || v156 == &g_bitValueOne )
    {
      v261 = 0;
      v156 = 0;
    }
    else
    {
      LODWORD(DestinationSize) = 0;
      v156 = PageComprMgr::DecompressColumnPartialInline(
               v280,
               (const struct PhysicalColumnAttribute *)&v262,
               v156,
               v261,
               0,
               DestinationSize,
               &v261,
               v270);
    }
  }
LABEL_670:
  if ( !v156 || v261 != 4 )
    RaiseFileHdrErr(v115, 25, *a2, (wchar_t *)L"GROWTH");
  *((_DWORD *)a2 + 5) = *(_DWORD *)v156;
  v262 = -8;
  v263 = 8;
  v186 = v264;
  LOWORD(v186) = v264 & 0xFFE0;
  v187 = v264 & 0xFFE0;
  v264 &= 0xFFE0u;
  v265 = 0;
  if ( !v276 )
  {
    v188 = v279;
    if ( (*v279 & 0x10) != 0 )
    {
      if ( (int)v280 > -8 )
      {
        if ( *(_WORD *)&v279[(unsigned int)v280] >= 8u )
        {
          v189 = v279[(unsigned int)v280 + 2] >> 7;
          v190 = 1;
        }
        else
        {
          v189 = ((v187 >> 4) & 1) == 0;
          v190 = 0;
        }
      }
      else
      {
        v189 = ((v186 >> 4) & 1) == 0;
        v190 = 0;
      }
    }
    else
    {
      if ( ((1 << (*v279 & 0xE)) & 0x1105) == 0 )
        goto LABEL_687;
      v189 = ((v187 >> 4) & 1) == 0;
      v190 = 0;
    }
    if ( v189 )
    {
      v191 = 0;
      v261 = 0;
      goto LABEL_804;
    }
    if ( !v190 && (v264 & 0x10) != 0 )
    {
      v191 = (const unsigned __int8 *)4;
      v261 = *v265;
      goto LABEL_804;
    }
LABEL_687:
    if ( !v278 )
    {
      v277 = 0;
      v192 = (unsigned int)v280;
      HIDWORD(v280) = (_DWORD)v280;
      if ( (*v279 & 0x10) != 0 )
      {
        v192 = (((unsigned int)*(unsigned __int16 *)&v279[(unsigned int)v280] + 7) >> 3) + (_DWORD)v280 + 2;
        HIDWORD(v280) = v192;
      }
      if ( (*v279 & 0x20) != 0 )
      {
        v193 = &v279[v192];
        v282 = *(_WORD *)v193;
        if ( !v282 )
        {
          if ( byte_10316E8D7 || (qword_10317B120 & 1) != 0 )
          {
            v194 = *(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                             + SystemThread_TlsOffset
                             + 8LL);
            if ( v194 )
            {
              v195 = *(_QWORD *)(v194 + 96);
              if ( v195 )
              {
                if ( *(_BYTE *)(v195 + 1177) )
                {
                  if ( byte_10316E7C7 || (qword_10317B120 & 2) != 0 )
                    utassert_fail(1u, "false", "Sql\\Ntdbms\\storeng\\drs\\fixedvarrecord.cpp", 2010, 0);
                  else
                    ex_raise(34, 68, 21, 1003);
                }
              }
            }
            v188 = v279;
          }
          RaiseInconsistencyError(v188, 3);
          v188 = v279;
        }
        v196 = HIDWORD(v280) + 2 * (v282 + 1);
        v281 = v196;
        if ( v196 > 0x1F9E )
        {
          if ( byte_10316E8D7 || (qword_10317B120 & 1) != 0 )
          {
            v197 = *(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                             + SystemThread_TlsOffset
                             + 8LL);
            if ( v197 )
            {
              v198 = *(_QWORD *)(v197 + 96);
              if ( v198 )
              {
                if ( *(_BYTE *)(v198 + 1177) )
                {
                  if ( byte_10316E7C7 || (qword_10317B120 & 2) != 0 )
                    utassert_fail(1u, "false", "Sql\\Ntdbms\\storeng\\drs\\fixedvarrecord.cpp", 2017, 0);
                  else
                    ex_raise(34, 68, 21, 1004);
                }
              }
            }
            v188 = v279;
          }
          RaiseInconsistencyError(v188, 4);
          v196 = v281;
          v188 = v279;
        }
        v192 = *(_WORD *)&v193[2 * v282] & 0x7FFF;
        v278 = v192;
        if ( v196 > v192 )
        {
          if ( byte_10316E8D7 || (qword_10317B120 & 1) != 0 )
          {
            v199 = *(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                             + SystemThread_TlsOffset
                             + 8LL);
            if ( v199 )
            {
              v200 = *(_QWORD *)(v199 + 96);
              if ( v200 )
              {
                if ( *(_BYTE *)(v200 + 1177) )
                {
                  if ( byte_10316E7C7 || (qword_10317B120 & 2) != 0 )
                    utassert_fail(1u, "false", "Sql\\Ntdbms\\storeng\\drs\\fixedvarrecord.cpp", 2024, 0);
                  else
                    ex_raise(34, 68, 21, 1004);
                }
              }
            }
            v188 = v279;
          }
          RaiseInconsistencyError(v188, 4);
          v196 = v281;
          v188 = v279;
          v192 = v278;
        }
        while ( *(__int16 *)&v193[2 * v282] < 0 )
        {
          v201 = &v188[HIDWORD(v280)];
          if ( v282 == 1 )
          {
            v202 = v196;
            v203 = 1;
          }
          else
          {
            v203 = v282;
            v202 = *(_WORD *)&v201[2 * v282 - 2] & 0x7FFF;
          }
          v204 = *(_WORD *)&v201[2 * v203] & 0x7FFF;
          if ( v202 < v196 || v204 < v202 )
          {
            RaiseInconsistencyError(v188, 7);
            v196 = v281;
            v188 = v279;
            v192 = v278;
          }
          if ( v202 < v196 || v202 > v192 )
            goto LABEL_780;
          v205 = *(_WORD *)&v188[v202];
          if ( v205 == 5 )
          {
            v277 |= 2u;
            --v282;
            WORD2(v284) = v202;
            v206 = *(_WORD *)&v188[(unsigned __int16)v202 + 2];
            if ( (v206 & 0x4000) != 0 )
              v207 = (v206 ^ WORD3(v284)) & 0x3800 ^ WORD3(v284);
            else
              v207 = WORD3(v284) & 0xC7FF;
            WORD3(v284) = v207;
            WORD3(v284) = v207 ^ (*(_WORD *)&v188[(unsigned __int16)v202 + 2] ^ v207) & 0x7FF;
            break;
          }
          if ( v205 >= 0x400u )
          {
            v277 |= 1u;
            if ( --v282 )
              continue;
          }
          break;
        }
      }
      else
      {
        v278 = v192;
        v282 = 0;
        v196 = v192;
        v281 = v192;
      }
      if ( (*v188 & 0x40) != 0 )
      {
        LODWORD(v284) = v192;
        v278 = v192 + 14;
        v208 = FixedVarRecord::FindVersioningInfo((FixedVarRecord *)&v277);
        v209 = HIDWORD(*(_QWORD *)v208);
        v210 = HIWORD(*(_QWORD *)v208);
        v211 = 0;
        if ( (((__int16)v210 ^ ((unsigned int)(__int16)v210 >> 1)) & 0x2000) != 0 )
        {
          v212 = v210 & 0xDFFF;
          if ( (v210 & 0x4000) != 0 )
            v212 = v210 | 0x2000;
          LOWORD(v210) = v212;
        }
        if ( (_WORD)v210 == 0xFFFC )
          v211 = (unsigned __int16)v209 >> 5;
        v192 = v211 + v278;
        v278 += v211;
        v196 = v281;
        v188 = v279;
      }
      else
      {
        LODWORD(v284) = 0;
      }
      if ( v283 && v283 < (unsigned __int64)&v188[v192] )
      {
        if ( byte_10316E8D7 || (qword_10317B120 & 1) != 0 )
        {
          v213 = *(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                           + SystemThread_TlsOffset
                           + 8LL);
          if ( v213 )
          {
            v214 = *(_QWORD *)(v213 + 96);
            if ( v214 )
            {
              if ( *(_BYTE *)(v214 + 1177) )
              {
                if ( byte_10316E7C7 || (qword_10317B120 & 2) != 0 )
                  utassert_fail(1u, "false", "Sql\\Ntdbms\\storeng\\drs\\fixedvarrecord.cpp", 2114, 0);
                else
                  ex_raise(34, 68, 21, 1018);
              }
            }
          }
          v188 = v279;
        }
        RaiseInconsistencyError(v188, 18);
        v196 = v281;
        v188 = v279;
        v192 = v278;
      }
      if ( v192 - 1 <= 0x3F3B )
      {
LABEL_780:
        v217 = -(__int16)v262;
        if ( (v264 & 0x10) == 0 )
          goto LABEL_783;
        if ( (*v188 & 0x10) != 0 )
        {
          if ( v262 < (int)v280 && *(_WORD *)&v188[(unsigned int)v280] >= v263 )
          {
LABEL_783:
            if ( v217 > (unsigned int)v282 )
            {
              v191 = v188;
              v261 = 0;
            }
            else
            {
              v218 = &v188[HIDWORD(v280)];
              if ( v217 == 1 )
              {
                v219 = v196;
              }
              else
              {
                _mm_lfence();
                v219 = *(_WORD *)&v218[2 * v217 - 2] & 0x7FFF;
                v196 = v281;
                v188 = v279;
              }
              v220 = *(_WORD *)&v218[2 * v217] & 0x7FFF;
              if ( v219 < v196 || v220 < v219 )
              {
                RaiseInconsistencyError(v188, 7);
                v188 = v279;
              }
              v191 = &v188[v219];
              v261 = v220 - v219;
            }
            goto LABEL_804;
          }
        }
        else if ( ((1 << (*v188 & 0xE)) & 0x1105) == 0 )
        {
          goto LABEL_783;
        }
        v191 = (const unsigned __int8 *)(v265 + 1);
        v261 = *v265;
        goto LABEL_804;
      }
      if ( byte_10316E8D7 || (qword_10317B120 & 1) != 0 )
      {
        v215 = *(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                         + SystemThread_TlsOffset
                         + 8LL);
        if ( v215 )
        {
          v216 = *(_QWORD *)(v215 + 96);
          if ( v216 )
          {
            if ( *(_BYTE *)(v216 + 1177) )
            {
              if ( byte_10316E7C7 || (qword_10317B120 & 2) != 0 )
                utassert_fail(1u, "false", "Sql\\Ntdbms\\storeng\\drs\\fixedvarrecord.cpp", 2119, 0);
              else
                ex_raise(34, 68, 21, 1005);
            }
          }
        }
        v188 = v279;
      }
      RaiseInconsistencyError(v188, 5);
      v188 = v279;
    }
    v196 = v281;
    goto LABEL_780;
  }
  v271 = 0;
  v191 = CDRecord::LocateColumnInternal(
           (CDRecord *)&v277,
           (const struct PhysicalColumnAttribute *)&v262,
           (int)v153,
           &v261,
           &v271);
  if ( v276 && v280 && *(_QWORD *)v280 && (v264 & 8) == 0 && (v271 & 1) == 0 )
  {
    if ( !v191 || v191 == &g_bitValueOne )
    {
      v261 = 0;
      v191 = 0;
    }
    else
    {
      LODWORD(DestinationSize) = 0;
      v191 = PageComprMgr::DecompressColumnPartialInline(
               v280,
               (const struct PhysicalColumnAttribute *)&v262,
               v191,
               v261,
               0,
               DestinationSize,
               &v261,
               v271);
    }
  }
LABEL_804:
  if ( !v191 || v261 != 4 )
    RaiseFileHdrErr(v115, 26, *a2, (wchar_t *)L"PERF");
  *((_DWORD *)a2 + 7) = *(_DWORD *)v191;
  v262 = -14;
  v263 = 14;
  v221 = v264;
  LOWORD(v221) = v264 & 0xFFE0;
  v222 = v264 & 0xFFE0;
  v264 &= 0xFFE0u;
  v265 = 0;
  if ( v276 )
  {
    v272 = 0;
    v256 = CDRecord::LocateColumnInternal(
             (CDRecord *)&v277,
             (const struct PhysicalColumnAttribute *)&v262,
             (int)v188,
             &v261,
             &v272);
    if ( v276 && v280 && *(_QWORD *)v280 && (v264 & 8) == 0 && (v272 & 1) == 0 )
    {
      if ( !v256 || v256 == &g_bitValueOne )
      {
        v226 = 0;
        v261 = 0;
        v256 = 0;
        goto LABEL_938;
      }
      LODWORD(DestinationSize) = 0;
      v256 = PageComprMgr::DecompressColumnPartialInline(
               v280,
               (const struct PhysicalColumnAttribute *)&v262,
               v256,
               v261,
               0,
               DestinationSize,
               &v261,
               v272);
    }
    v226 = v261;
LABEL_938:
    v11 = (__int64)v256;
    goto LABEL_939;
  }
  v223 = v279;
  if ( (*v279 & 0x10) != 0 )
  {
    if ( (int)v280 > -14 )
    {
      if ( *(_WORD *)&v279[(unsigned int)v280] >= 0xEu )
      {
        LOBYTE(v224) = v279[(unsigned int)v280 + 3] >> 5;
        v225 = 1;
      }
      else
      {
        v224 = ~(v222 >> 4);
        v225 = 0;
      }
    }
    else
    {
      v224 = ~(v221 >> 4);
      v225 = 0;
    }
  }
  else
  {
    if ( ((1 << (*v279 & 0xE)) & 0x1105) == 0 )
      goto LABEL_821;
    LOBYTE(v224) = ~(unsigned __int8)(v222 >> 4);
    v225 = 0;
  }
  if ( (v224 & 1) != 0 )
  {
    v226 = 0;
    v261 = 0;
    goto LABEL_939;
  }
  if ( !v225 && (v264 & 0x10) != 0 )
  {
    v11 = 4;
    v226 = *v265;
    v261 = *v265;
    goto LABEL_939;
  }
LABEL_821:
  if ( v278 )
  {
LABEL_913:
    v231 = v281;
    goto LABEL_914;
  }
  v277 = 0;
  v227 = (unsigned int)v280;
  HIDWORD(v280) = (_DWORD)v280;
  if ( (*v279 & 0x10) != 0 )
  {
    v227 = (((unsigned int)*(unsigned __int16 *)&v279[(unsigned int)v280] + 7) >> 3) + (_DWORD)v280 + 2;
    HIDWORD(v280) = v227;
  }
  if ( (*v279 & 0x20) != 0 )
  {
    v228 = &v279[v227];
    v282 = *(_WORD *)v228;
    if ( !v282 )
    {
      if ( byte_10316E8D7 || (qword_10317B120 & 1) != 0 )
      {
        v229 = *(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                         + SystemThread_TlsOffset
                         + 8LL);
        if ( v229 )
        {
          v230 = *(_QWORD *)(v229 + 96);
          if ( v230 )
          {
            if ( *(_BYTE *)(v230 + 1177) )
            {
              if ( byte_10316E7C7 || (qword_10317B120 & 2) != 0 )
                utassert_fail(1u, "false", "Sql\\Ntdbms\\storeng\\drs\\fixedvarrecord.cpp", 2010, 0);
              else
                ex_raise(34, 68, 21, 1003);
            }
          }
        }
        v223 = v279;
      }
      RaiseInconsistencyError(v223, 3);
      v223 = v279;
    }
    v231 = HIDWORD(v280) + 2 * (v282 + 1);
    v281 = v231;
    if ( v231 > 0x1F9E )
    {
      if ( byte_10316E8D7 || (qword_10317B120 & 1) != 0 )
      {
        v232 = *(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                         + SystemThread_TlsOffset
                         + 8LL);
        if ( v232 )
        {
          v233 = *(_QWORD *)(v232 + 96);
          if ( v233 )
          {
            if ( *(_BYTE *)(v233 + 1177) )
            {
              if ( byte_10316E7C7 || (qword_10317B120 & 2) != 0 )
                utassert_fail(1u, "false", "Sql\\Ntdbms\\storeng\\drs\\fixedvarrecord.cpp", 2017, 0);
              else
                ex_raise(34, 68, 21, 1004);
            }
          }
        }
        v223 = v279;
      }
      RaiseInconsistencyError(v223, 4);
      v231 = v281;
      v223 = v279;
    }
    v227 = *(_WORD *)&v228[2 * v282] & 0x7FFF;
    v278 = v227;
    if ( v231 > v227 )
    {
      if ( byte_10316E8D7 || (qword_10317B120 & 1) != 0 )
      {
        v234 = *(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                         + SystemThread_TlsOffset
                         + 8LL);
        if ( v234 )
        {
          v235 = *(_QWORD *)(v234 + 96);
          if ( v235 )
          {
            if ( *(_BYTE *)(v235 + 1177) )
            {
              if ( byte_10316E7C7 || (qword_10317B120 & 2) != 0 )
                utassert_fail(1u, "false", "Sql\\Ntdbms\\storeng\\drs\\fixedvarrecord.cpp", 2024, 0);
              else
                ex_raise(34, 68, 21, 1004);
            }
          }
        }
        v223 = v279;
      }
      RaiseInconsistencyError(v223, 4);
      v231 = v281;
      v223 = v279;
      v227 = v278;
    }
    while ( *(__int16 *)&v228[2 * v282] < 0 )
    {
      v236 = &v223[HIDWORD(v280)];
      if ( v282 == 1 )
      {
        v237 = v231;
        v238 = 1;
      }
      else
      {
        v238 = v282;
        v237 = *(_WORD *)&v236[2 * v282 - 2] & 0x7FFF;
      }
      v239 = *(_WORD *)&v236[2 * v238] & 0x7FFF;
      if ( v237 < v231 || v239 < v237 )
      {
        RaiseInconsistencyError(v223, 7);
        v231 = v281;
        v223 = v279;
        v227 = v278;
      }
      if ( v237 < v231 || v237 > v227 )
        goto LABEL_914;
      v240 = *(_WORD *)&v223[v237];
      if ( v240 == 5 )
      {
        v277 |= 2u;
        --v282;
        WORD2(v284) = v237;
        v241 = *(_WORD *)&v223[(unsigned __int16)v237 + 2];
        if ( (v241 & 0x4000) != 0 )
          v242 = (WORD3(v284) ^ v241) & 0x3800 ^ WORD3(v284);
        else
          v242 = WORD3(v284) & 0xC7FF;
        WORD3(v284) = v242;
        WORD3(v284) = v242 ^ (*(_WORD *)&v223[(unsigned __int16)v237 + 2] ^ v242) & 0x7FF;
        break;
      }
      if ( v240 >= 0x400u )
      {
        v277 |= 1u;
        if ( --v282 )
          continue;
      }
      break;
    }
  }
  else
  {
    v278 = v227;
    v282 = 0;
    v231 = v227;
    v281 = v227;
  }
  if ( (*v223 & 0x40) != 0 )
  {
    LODWORD(v284) = v227;
    v278 = v227 + 14;
    v243 = FixedVarRecord::FindVersioningInfo((FixedVarRecord *)&v277);
    v244 = HIDWORD(*(_QWORD *)v243);
    v245 = HIWORD(*(_QWORD *)v243);
    v246 = 0;
    if ( (((__int16)v245 ^ ((unsigned int)(__int16)v245 >> 1)) & 0x2000) != 0 )
    {
      v247 = v245 & 0xDFFF;
      if ( (v245 & 0x4000) != 0 )
        v247 = v245 | 0x2000;
      LOWORD(v245) = v247;
    }
    if ( (_WORD)v245 == 0xFFFC )
      v246 = (unsigned __int16)v244 >> 5;
    v227 = v246 + v278;
    v278 += v246;
    v231 = v281;
    v223 = v279;
  }
  else
  {
    LODWORD(v284) = 0;
  }
  if ( v283 && v283 < (unsigned __int64)&v223[v227] )
  {
    if ( byte_10316E8D7 || (qword_10317B120 & 1) != 0 )
    {
      v248 = *(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                       + SystemThread_TlsOffset
                       + 8LL);
      if ( v248 )
      {
        v249 = *(_QWORD *)(v248 + 96);
        if ( v249 )
        {
          if ( *(_BYTE *)(v249 + 1177) )
          {
            if ( byte_10316E7C7 || (qword_10317B120 & 2) != 0 )
              utassert_fail(1u, "false", "Sql\\Ntdbms\\storeng\\drs\\fixedvarrecord.cpp", 2114, 0);
            else
              ex_raise(34, 68, 21, 1018);
          }
        }
      }
      v223 = v279;
    }
    RaiseInconsistencyError(v223, 18);
    v231 = v281;
    v223 = v279;
    v227 = v278;
  }
  if ( v227 - 1 > 0x3F3B )
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
              utassert_fail(1u, "false", "Sql\\Ntdbms\\storeng\\drs\\fixedvarrecord.cpp", 2119, 0);
            else
              ex_raise(34, 68, 21, 1005);
          }
        }
      }
      v223 = v279;
    }
    RaiseInconsistencyError(v223, 5);
    v223 = v279;
    goto LABEL_913;
  }
LABEL_914:
  v252 = -(__int16)v262;
  if ( (v264 & 0x10) == 0 )
    goto LABEL_917;
  if ( (*v223 & 0x10) == 0 )
  {
    if ( ((1 << (*v223 & 0xE)) & 0x1105) == 0 )
      goto LABEL_917;
LABEL_922:
    v226 = *v265;
    v11 = (__int64)(v265 + 1);
    v261 = *v265;
    goto LABEL_939;
  }
  if ( v262 >= (int)v280 || *(_WORD *)&v223[(unsigned int)v280] < v263 )
    goto LABEL_922;
LABEL_917:
  if ( v252 > (unsigned int)v282 )
  {
    v226 = 0;
    v11 = (__int64)v223;
    v261 = 0;
  }
  else
  {
    v253 = &v223[HIDWORD(v280)];
    if ( v252 == 1 )
    {
      v254 = v231;
    }
    else
    {
      _mm_lfence();
      v254 = *(_WORD *)&v253[2 * v252 - 2] & 0x7FFF;
      v231 = v281;
      v223 = v279;
    }
    v255 = *(_WORD *)&v253[2 * v252] & 0x7FFF;
    if ( v254 < v231 || v255 < v254 )
    {
      RaiseInconsistencyError(v223, 7);
      v223 = v279;
    }
    v226 = v255 - v254;
    v11 = (__int64)&v223[v254];
    v261 = v226;
  }
LABEL_939:
  if ( v226 )
  {
    if ( !v11 || v226 != 4 )
      RaiseFileHdrErr(v115, 27, *a2, (wchar_t *)L"STATUS");
    *((_DWORD *)a2 + 6) = *(_DWORD *)v11;
  }
  v257 = v275[0];
  if ( v275[0] != (void *)-1LL )
  {
    v258 = DBGetHandlerForHandle(v275[0]);
    if ( v258 )
      (*(void (__fastcall **)(struct IFileSystemHandler *, void *))(*(_QWORD *)v258 + 208LL))(v258, v257);
    else
      SetLastError(0x32u);
  }
}

```

## disassembly

```asm
0x101809b10  push    rbp
0x101809b12  push    rsi
0x101809b13  push    rdi
0x101809b14  push    r12
0x101809b16  push    r13
0x101809b18  push    r14
0x101809b1a  push    r15
0x101809b1c  lea     rbp, [rsp-4090h]
0x101809b24  mov     eax, 4190h
0x101809b29  call    _alloca_probe
0x101809b2e  sub     rsp, rax
0x101809b31  mov     [rbp+40C0h+var_4130], 0FFFFFFFFFFFFFFFEh
0x101809b39  mov     [rsp+41C0h+arg_0], rbx
0x101809b41  mov     rax, cs:__security_cookie
0x101809b48  xor     rax, rsp
0x101809b4b  mov     [rbp+40C0h+var_40], rax
0x101809b52  mov     rsi, r8
0x101809b55  mov     [rsp+41C0h+var_4148], r8
0x101809b5a  mov     r13, rdx
0x101809b5d  mov     r14, 0FFFFFFFFFFFFFFFFh
0x101809b64  mov     [rbp+40C0h+var_4138], r14
0x101809b68  mov     rcx, [rdx]
0x101809b6b  mov     rax, r14
0x101809b6e  xchg    ax, ax
0x101809b70  lea     rax, [rax+1]
0x101809b74  cmp     word ptr [rcx+rax*2], 0
0x101809b79  jnz     short loc_101809B70
0x101809b7b  lea     rdx, [rax+rax]
0x101809b7f  lea     r9, [rbp+40C0h+var_4140]
0x101809b83  lea     r8, [rbp+40C0h+var_4138]
0x101809b87  call    ?UtOpenFile@@YA_NPEB_WHAEAV?$CAutoHandleInternal@$0?0$1?DBCloseHandle@@YAHPEAX@Z@@AEAK@Z; UtOpenFile(wchar_t const *,int,CAutoHandleInternal<-1,&DBCloseHandle(void *)> &,ulong &)
0x101809b8c  mov     r12d, 1
0x101809b92  test    al, al
0x101809b94  jnz     short loc_101809BF7
0x101809b96  mov     edx, r12d; int
0x101809b99  mov     rcx, rsi; this
0x101809b9c  call    ?EndResultSet@BackupResultSet@@QEAAXH@Z; BackupResultSet::EndResultSet(int)
0x101809ba1  mov     rdi, [r13+0]
0x101809ba5  mov     rbx, r14
0x101809ba8  nop     dword ptr [rax+rax+00000000h]
0x101809bb0  inc     rbx
0x101809bb3  cmp     word ptr [rdi+rbx*2], 0
0x101809bb8  jnz     short loc_101809BB0
0x101809bba  add     rbx, rbx
0x101809bbd  xor     r9d, r9d
0x101809bc0  xor     r8d, r8d
0x101809bc3  lea     rdx, [rbp+40C0h+var_4040]
0x101809bca  mov     ecx, [rbp+40C0h+var_4140]
0x101809bcd  call    cs:__imp_?GetOSErrString@@YAPEA_WKAEAVErrorStringHolder@@PEBXK@Z; GetOSErrString(ulong,ErrorStringHolder &,void const *,ulong)
0x101809bd3  mov     [rsp+41C0h+var_4190], rdi
0x101809bd8  mov     dword ptr [rsp+41C0h+DestinationSize], ebx
0x101809bdc  mov     [rsp+41C0h+Destination], rax
0x101809be1  mov     edx, 17h
0x101809be6  lea     ecx, [rdx+1Ch]
0x101809be9  lea     r9d, [rdx-3]
0x101809bed  lea     r8d, [rdx-7]
0x101809bf1  call    cs:__imp_?ex_raise@@YAHHHHHZZ; ex_raise(int,int,int,int,...)
0x101809bf7  lea     rdx, [rbp+40C0h+var_2041]
0x101809bfe  and     rdx, 0FFFFFFFFFFFFF000h
0x101809c05  mov     [rbp+40C0h+var_40F0], r14w
0x101809c0a  xor     r15d, r15d
0x101809c0d  mov     [rbp+40C0h+var_40E8], r15
0x101809c11  mov     [rbp+40C0h+var_40EC], r15d
0x101809c15  mov     [rbp+40C0h+var_40D2], r15
0x101809c19  mov     [rbp+40C0h+var_40C8], r15
0x101809c1d  mov     [rbp+40C0h+var_40E0], r15
0x101809c21  mov     [rbp+40C0h+var_40BC], r14d
0x101809c25  mov     edi, 0FFE0h
0x101809c2a  and     [rsp+41C0h+var_4172], di
0x101809c2f  lea     r8, [rbp+40C0h+var_40F0]
0x101809c33  lea     rcx, [rbp+40C0h+var_4138]
0x101809c37  call    ?GetHdrPageAndRec@@YAHAEAV?$CAutoHandleInternal@$0?0$1?DBCloseHandle@@YAHPEAX@Z@@PEAVPage@@PEAVPageRow@@@Z; GetHdrPageAndRec(CAutoHandleInternal<-1,&DBCloseHandle(void *)> &,Page *,PageRow *)
0x101809c3c  test    eax, eax
0x101809c3e  jnz     short loc_101809C56
0x101809c40  lea     r9, aHeader; "HEADER"
0x101809c47  mov     r8, [r13+0]; wchar_t *
0x101809c4b  lea     edx, [rax+1Ch]; int
0x101809c4e  mov     rcx, rsi; struct BackupResultSet *
0x101809c51  call    ?RaiseFileHdrErr@@YAXPEAVBackupResultSet@@HPEA_W1@Z; RaiseFileHdrErr(BackupResultSet *,int,wchar_t *,wchar_t *)
0x101809c56  mov     eax, 0FFFFFFFCh
0x101809c5b  mov     [rsp+41C0h+var_4178], eax
0x101809c5f  mov     ebx, 4
0x101809c64  mov     [rsp+41C0h+var_4174], bx
0x101809c69  movzx   eax, [rsp+41C0h+var_4172]
0x101809c6e  and     ax, di
0x101809c71  movzx   r9d, ax
0x101809c75  movzx   edx, ax
0x101809c78  mov     [rsp+41C0h+var_4172], ax
0x101809c7d  mov     [rsp+41C0h+var_4170], r15
0x101809c82  lea     rdi, ?g_bitValueOne@@3EB; uchar const g_bitValueOne
0x101809c89  lea     r11d, [rbx+3]
0x101809c8d  cmp     [rbp+40C0h+var_40F0], r15w
0x101809c92  jnz     loc_10180A42C
0x101809c98  mov     r8, [rbp+40C0h+var_40E8]
0x101809c9c  movzx   ecx, byte ptr [r8]
0x101809ca0  test    cl, 10h
0x101809ca3  jnz     short loc_101809CC2
0x101809ca5  and     cl, 0Eh
0x101809ca8  mov     eax, r12d
0x101809cab  shl     eax, cl
0x101809cad  test    eax, 1105h
0x101809cb2  jz      loc_101809D3A
0x101809cb8  shr     edx, 4
0x101809cbb  not     edx
0x101809cbd  mov     eax, r15d
0x101809cc0  jmp     short loc_101809CFA
0x101809cc2  cmp     dword ptr [rbp+40C0h+var_40E0], 0FFFFFFFCh
0x101809cc6  jg      short loc_101809CD4
0x101809cc8  mov     edx, eax
0x101809cca  shr     edx, 4
0x101809ccd  not     edx
0x101809ccf  mov     eax, r15d
0x101809cd2  jmp     short loc_101809CFA
0x101809cd4  mov     ecx, dword ptr [rbp+40C0h+var_40E0]
0x101809cd7  cmp     [rcx+r8], bx
0x101809cdc  jnb     short loc_101809CEB
0x101809cde  mov     edx, r9d
0x101809ce1  shr     edx, 4
0x101809ce4  not     edx
0x101809ce6  mov     eax, r15d
0x101809ce9  jmp     short loc_101809CFA
0x101809ceb  movzx   eax, byte ptr [rcx+r8+2]
0x101809cf1  shr     al, 3
0x101809cf4  movzx   edx, al
0x101809cf7  mov     eax, r12d
0x101809cfa  and     edx, r12d
0x101809cfd  test    edx, edx
0x101809cff  jz      short loc_101809D18
0x101809d01  mov     rbx, r15
0x101809d04  mov     edi, r15d
0x101809d07  mov     [rsp+41C0h+var_4180], r15d
0x101809d0c  lea     rdi, ?g_bitValueOne@@3EB; uchar const g_bitValueOne
0x101809d13  jmp     loc_10180A4B7
0x101809d18  test    eax, eax
0x101809d1a  jnz     short loc_101809D3A
0x101809d1c  test    byte ptr [rsp+41C0h+var_4172], 10h
0x101809d21  jz      short loc_101809D3A
0x101809d23  mov     rax, [rsp+41C0h+var_4170]
0x101809d28  mov     edi, [rax]
0x101809d2a  mov     [rsp+41C0h+var_4180], edi
0x101809d2e  lea     rdi, ?g_bitValueOne@@3EB; uchar const g_bitValueOne
0x101809d35  jmp     loc_10180A4B7
0x101809d3a  cmp     [rbp+40C0h+var_40EC], r15d
0x101809d3e  jnz     loc_10180A389
0x101809d44  mov     [rbp+40C0h+var_40EE], r15w
0x101809d49  mov     r9d, dword ptr [rbp+40C0h+var_40E0]
0x101809d4d  mov     dword ptr [rbp+40C0h+var_40E0+4], r9d
0x101809d51  test    byte ptr [r8], 10h
0x101809d55  jz      short loc_101809D6D
0x101809d57  movzx   ecx, word ptr [r9+r8]
0x101809d5c  add     ecx, r11d
0x101809d5f  shr     ecx, 3
0x101809d62  add     r9d, 2
0x101809d66  add     r9d, ecx
0x101809d69  mov     dword ptr [rbp+40C0h+var_40E0+4], r9d
0x101809d6d  test    byte ptr [r8], 20h
0x101809d71  jz      loc_10180A0F8
0x101809d77  mov     edi, r9d
0x101809d7a  add     rdi, r8
0x101809d7d  movzx   eax, word ptr [rdi]
0x101809d80  mov     [rbp+40C0h+var_40D4], ax
0x101809d84  test    ax, ax
0x101809d87  jnz     loc_101809E40
0x101809d8d  cmp     cs:byte_10316E8D7, r15b
0x101809d94  jnz     short loc_101809DA3
0x101809d96  test    byte ptr cs:qword_10317B120, r12b
0x101809d9d  jz      loc_101809E2F
0x101809da3  mov     r8, gs:58h
0x101809dac  mov     rax, cs:__imp_SystemThread_TlsIndex
0x101809db3  mov     ecx, [rax]
0x101809db5  mov     rax, cs:__imp_SystemThread_TlsOffset
0x101809dbc  mov     edx, [rax]
0x101809dbe  add     rdx, [r8+rcx*8]
0x101809dc2  mov     rax, [rdx+8]
0x101809dc6  test    rax, rax
0x101809dc9  jz      short loc_101809E2B
0x101809dcb  mov     rax, [rax+60h]
0x101809dcf  test    rax, rax
0x101809dd2  jz      short loc_101809E2B
0x101809dd4  cmp     [rax+499h], r15b
0x101809ddb  jz      short loc_101809E2B
0x101809ddd  cmp     cs:byte_10316E7C7, r15b
0x101809de4  jnz     short loc_101809E09
0x101809de6  test    byte ptr cs:qword_10317B120, 2
0x101809ded  jnz     short loc_101809E09
0x101809def  mov     edx, 44h ; 'D'
0x101809df4  lea     ecx, [rdx-22h]
0x101809df7  mov     r9d, 3EBh
0x101809dfd  lea     r8d, [rdx-2Fh]
0x101809e01  call    cs:__imp_?ex_raise@@YAHHHHHZZ; ex_raise(int,int,int,int,...)
0x101809e07  jmp     short loc_101809E2B
0x101809e09  mov     [rsp+41C0h+Destination], r15
0x101809e0e  mov     r9d, 7DAh
0x101809e14  lea     r8, aSqlNtdbmsStore_517; "Sql\\Ntdbms\\storeng\\drs\\fixedvarreco"...
0x101809e1b  lea     rdx, aFalse; "false"
0x101809e22  mov     ecx, r12d
0x101809e25  call    cs:__imp_?utassert_fail@@YAXIPEBD0H0ZZ; utassert_fail(uint,char const *,char const *,int,char const *,...)
0x101809e2b  mov     r8, [rbp+40C0h+var_40E8]
0x101809e2f  mov     edx, 3
0x101809e34  mov     rcx, r8
0x101809e37  call    ?RaiseInconsistencyError@@YAXPEBXW4IRN_REF_NUM@@@Z; RaiseInconsistencyError(void const *,IRN_REF_NUM)
0x101809e3c  mov     r8, [rbp+40C0h+var_40E8]
0x101809e40  movzx   r10d, [rbp+40C0h+var_40D4]
0x101809e45  mov     eax, dword ptr [rbp+40C0h+var_40E0+4]
0x101809e48  inc     r10d
0x101809e4b  lea     r10d, [rax+r10*2]
0x101809e4f  mov     [rbp+40C0h+var_40D8], r10d
0x101809e53  cmp     r10d, 1F9Eh
0x101809e5a  jbe     loc_101809F14
0x101809e60  cmp     cs:byte_10316E8D7, r15b
0x101809e67  jnz     short loc_101809E76
0x101809e69  test    byte ptr cs:qword_10317B120, r12b
0x101809e70  jz      loc_101809F02
0x101809e76  mov     r8, gs:58h
0x101809e7f  mov     rax, cs:__imp_SystemThread_TlsIndex
0x101809e86  mov     ecx, [rax]
0x101809e88  mov     rax, cs:__imp_SystemThread_TlsOffset
0x101809e8f  mov     edx, [rax]
0x101809e91  add     rdx, [r8+rcx*8]
0x101809e95  mov     rax, [rdx+8]
0x101809e99  test    rax, rax
0x101809e9c  jz      short loc_101809EFE
0x101809e9e  mov     rax, [rax+60h]
0x101809ea2  test    rax, rax
0x101809ea5  jz      short loc_101809EFE
0x101809ea7  cmp     [rax+499h], r15b
0x101809eae  jz      short loc_101809EFE
0x101809eb0  cmp     cs:byte_10316E7C7, r15b
0x101809eb7  jnz     short loc_101809EDC
0x101809eb9  test    byte ptr cs:qword_10317B120, 2
0x101809ec0  jnz     short loc_101809EDC
0x101809ec2  mov     edx, 44h ; 'D'
0x101809ec7  lea     ecx, [rdx-22h]
0x101809eca  mov     r9d, 3ECh
0x101809ed0  lea     r8d, [rdx-2Fh]
0x101809ed4  call    cs:__imp_?ex_raise@@YAHHHHHZZ; ex_raise(int,int,int,int,...)
0x101809eda  jmp     short loc_101809EFE
0x101809edc  mov     [rsp+41C0h+Destination], r15
0x101809ee1  mov     r9d, 7E1h
0x101809ee7  lea     r8, aSqlNtdbmsStore_517; "Sql\\Ntdbms\\storeng\\drs\\fixedvarreco"...
0x101809eee  lea     rdx, aFalse; "false"
0x101809ef5  mov     ecx, r12d
0x101809ef8  call    cs:__imp_?utassert_fail@@YAXIPEBD0H0ZZ; utassert_fail(uint,char const *,char const *,int,char const *,...)
0x101809efe  mov     r8, [rbp+40C0h+var_40E8]
0x101809f02  mov     edx, ebx
0x101809f04  mov     rcx, r8
0x101809f07  call    ?RaiseInconsistencyError@@YAXPEBXW4IRN_REF_NUM@@@Z; RaiseInconsistencyError(void const *,IRN_REF_NUM)
0x101809f0c  mov     r10d, [rbp+40C0h+var_40D8]
0x101809f10  mov     r8, [rbp+40C0h+var_40E8]
0x101809f14  movzx   eax, [rbp+40C0h+var_40D4]
0x101809f18  movzx   r9d, word ptr [rdi+rax*2]
0x101809f1d  and     r9d, 7FFFh
0x101809f24  mov     [rbp+40C0h+var_40EC], r9d
0x101809f28  cmp     r10d, r9d
0x101809f2b  jbe     loc_101809FF0
0x101809f31  cmp     cs:byte_10316E8D7, r15b
0x101809f38  jnz     short loc_101809F47
0x101809f3a  test    byte ptr cs:qword_10317B120, r12b
0x101809f41  jz      loc_101809FD3
0x101809f47  mov     r8, gs:58h
0x101809f50  mov     rax, cs:__imp_SystemThread_TlsIndex
0x101809f57  mov     ecx, [rax]
0x101809f59  mov     rax, cs:__imp_SystemThread_TlsOffset
0x101809f60  mov     edx, [rax]
0x101809f62  add     rdx, [r8+rcx*8]
0x101809f66  mov     rax, [rdx+8]
0x101809f6a  test    rax, rax
0x101809f6d  jz      short loc_101809FCF
0x101809f6f  mov     rax, [rax+60h]
0x101809f73  test    rax, rax
0x101809f76  jz      short loc_101809FCF
0x101809f78  cmp     [rax+499h], r15b
0x101809f7f  jz      short loc_101809FCF
0x101809f81  cmp     cs:byte_10316E7C7, r15b
0x101809f88  jnz     short loc_101809FAD
0x101809f8a  test    byte ptr cs:qword_10317B120, 2
0x101809f91  jnz     short loc_101809FAD
0x101809f93  mov     edx, 44h ; 'D'
0x101809f98  lea     ecx, [rdx-22h]
0x101809f9b  mov     r9d, 3ECh
0x101809fa1  lea     r8d, [rdx-2Fh]
0x101809fa5  call    cs:__imp_?ex_raise@@YAHHHHHZZ; ex_raise(int,int,int,int,...)
0x101809fab  jmp     short loc_101809FCF
0x101809fad  mov     [rsp+41C0h+Destination], r15
0x101809fb2  mov     r9d, 7E8h
0x101809fb8  lea     r8, aSqlNtdbmsStore_517; "Sql\\Ntdbms\\storeng\\drs\\fixedvarreco"...
0x101809fbf  lea     rdx, aFalse; "false"
0x101809fc6  mov     ecx, r12d
0x101809fc9  call    cs:__imp_?utassert_fail@@YAXIPEBD0H0ZZ; utassert_fail(uint,char const *,char const *,int,char const *,...)
0x101809fcf  mov     r8, [rbp+40C0h+var_40E8]
0x101809fd3  mov     edx, ebx
0x101809fd5  mov     rcx, r8
0x101809fd8  call    ?RaiseInconsistencyError@@YAXPEBXW4IRN_REF_NUM@@@Z; RaiseInconsistencyError(void const *,IRN_REF_NUM)
0x101809fdd  mov     r10d, [rbp+40C0h+var_40D8]
0x101809fe1  mov     r8, [rbp+40C0h+var_40E8]
0x101809fe5  mov     r9d, [rbp+40C0h+var_40EC]
0x101809fe9  nop     dword ptr [rax+00000000h]
0x101809ff0  movzx   edx, [rbp+40C0h+var_40D4]
0x101809ff4  lea     eax, [rdx-1]
0x101809ff7  cmp     [rdi+rax*2+2], r15w
  ... truncated ...
```
