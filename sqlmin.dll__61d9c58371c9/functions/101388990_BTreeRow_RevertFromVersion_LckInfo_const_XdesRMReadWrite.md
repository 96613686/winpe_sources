# BTreeRow::RevertFromVersion(LckInfo const *,XdesRMReadWrite *)

- ea: `0x101388990`
- end: `0x10138ffc9`
- name: `?RevertFromVersion@BTreeRow@@QEAA?AW4LogicalRevertReturnCode@@PEBVLckInfo@@PEAVXdesRMReadWrite@@@Z`
- size: `30265`
- prototype: ``
- caller_count: `5`
- callee_count: `45`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x10043fcb0`
- `0x100444150`
- `0x10045c720`
- `0x10056e860`
- `0x101427de0`

## callees

- `0x100401490`
- `0x100402000`
- `0x10040f500`
- `0x1004152e0`
- `0x100415e90`
- `0x10043e110`
- `0x100441e00`
- `0x100441e40`
- `0x100443460`
- `0x10046bf90`
- `0x100470cc0`
- `0x1004729d0`
- `0x100480030`
- `0x10048c200`
- `0x10048c710`
- `0x10049a0c0`
- `0x10049ff80`
- `0x1004a08c0`
- `0x1004a2010`
- `0x1004b8e80`
- `0x1005b10b0`
- `0x1005def40`
- `0x100664740`
- `0x101200050`
- `0x1013844d0`
- `0x101388990`
- `0x1013b28f0`
- `0x1013e52f0`
- `0x101408d90`
- `0x10140ebf0`
- `0x1017371e0`
- `0x101d11730`
- `0x101d19a30`
- `0x101d1e980`
- `0x101d94000`
- `0x1021d45f0`
- `0x1021d5c70`
- `0x1021d8a90`
- `0x1021e8a60`
- `0x1021e8ae0`
- `0x1021eab40`
- `0x1021ed230`
- `0x102394d80`
- `0x1023aea00`
- `0x1023aee60`

## import_xrefs

- `KERNEL32!HeapAlloc` at `0x10138acf4`
- `KERNEL32!HeapAlloc` at `0x10138acf4`
- `KERNEL32!GetProcessHeap` at `0x10138ace3`
- `KERNEL32!GetProcessHeap` at `0x10138ace3`
- `sqldk!??0CDStream@@QEAA@XZ` at `0x10138acdc`
- `sqldk!??0CDStream@@QEAA@XZ` at `0x10138acdc`
- `sqldk!??1CDStream@@QEAA@XZ` at `0x10138ad5f`
- `sqldk!??1CDStream@@QEAA@XZ` at `0x10138ad5f`
- `sqldk!?AddDevice@CDStream@@QEAAHPEAVCDumpStream@@@Z` at `0x10138ad2d`
- `sqldk!?AddDevice@CDStream@@QEAAHPEAVCDumpStream@@@Z` at `0x10138ad2d`
- `sqldk!?g_pAutoXactFactory@@3PEAVIAutoXactFactory@@EA` at `0x101388c97`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x101388f18`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x101388ff5`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1013890d0`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1013893b7`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x101389486`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x101389800`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1013898cc`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x101389995`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x101389bf5`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x101389cb4`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x101389f13`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x10138a050`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x10138a11f`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x10138a1ec`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x10138a456`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x10138a516`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x10138add6`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x10138b01d`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x10138b1b8`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x10138b295`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x10138b370`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x10138b648`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x10138b70d`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x10138b8a7`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x10138b979`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x10138ba4a`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x10138bce3`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x10138bda2`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x10138be52`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x10138c00d`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x10138c0e7`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x10138c1bf`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x10138c4a5`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x10138c56a`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x10138c6ff`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x10138c7d1`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x10138c8a2`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x10138cb35`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x10138cbf4`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x10138cdec`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x10138cec6`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x10138cf9e`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x10138d27a`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x10138d33f`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x10138d4ce`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x10138d5a0`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x10138d671`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x10138d908`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x10138d9c7`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x10138db37`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x10138dc59`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x10138dd34`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x10138de0e`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x10138e0ef`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x10138e1c2`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x10138e366`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x10138e440`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x10138e518`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x10138e7f3`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x10138e8b8`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x10138ea47`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x10138eb19`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x10138ebea`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x10138ee78`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x10138ef37`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x10138f23c`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x10138f30e`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x10138f3df`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x10138f65c`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x10138f729`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x10138f85f`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x10138f93c`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x10138fa17`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x10138fcea`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x10138fdae`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x101388f18`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x101388ff5`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1013890d0`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1013893b7`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x101389486`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x101389800`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1013898cc`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x101389995`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x101389bf5`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x101389cb4`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x101389f13`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x10138a050`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x10138a11f`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x10138a1ec`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x10138a456`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x10138a516`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x10138add6`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x10138b01d`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x10138b1b8`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x10138b295`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x10138b370`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x10138b648`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x10138b70d`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x10138b8a7`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x10138b979`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x10138ba4a`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x10138bce3`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x10138bda2`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x10138be52`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x10138c00d`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x10138c0e7`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x10138c1bf`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x10138c4a5`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x10138c56a`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x10138c6ff`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x10138c7d1`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x10138c8a2`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x10138cb35`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x10138cbf4`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x10138cdec`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x10138cec6`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x10138cf9e`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x10138d27a`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x10138d33f`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x10138d4ce`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x10138d5a0`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x10138d671`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x10138d908`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x10138d9c7`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x10138db37`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x10138dc59`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x10138dd34`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x10138de0e`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x10138e0ef`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x10138e1c2`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x10138e366`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x10138e440`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x10138e518`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x10138e7f3`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x10138e8b8`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x10138ea47`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x10138eb19`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x10138ebea`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x10138ee78`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x10138ef37`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x10138f23c`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x10138f30e`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x10138f3df`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x10138f65c`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x10138f729`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x10138f85f`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x10138f93c`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x10138fa17`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x10138fcea`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x10138fdae`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x101388ef2`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x101388fcf`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x1013890a7`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x101389391`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10138945d`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x1013897da`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x1013898a6`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10138996f`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x101389bcf`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x101389c8e`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10138a02a`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10138a0f9`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10138a1c6`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10138a430`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10138a4f0`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10138a7aa`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10138b192`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10138b26f`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10138b34a`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10138b622`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10138b6e7`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10138b881`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10138b953`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10138ba24`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10138bcbd`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10138bd7c`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10138bfe7`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10138c0c1`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10138c199`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10138c47f`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10138c544`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10138c6d9`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10138c7ab`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10138c87c`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10138cb0f`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10138cbce`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10138cdc6`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10138cea0`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10138cf78`

## string_xrefs

- `0x10138db29`: `!committedRec.IsGhostRecord()`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
__int64 __fastcall BTreeRow::RevertFromVersion(__int64 a1, __int64 a2, XdesRMReadWrite *a3)
{
  BTreeRow *v3; // r12
  struct XDES *v4; // rsi
  __int64 v5; // rbx
  unsigned int v6; // eax
  unsigned __int8 **RecordLong; // rdi
  unsigned int v8; // r13d
  char *v9; // rcx
  int v10; // r14d
  __int16 v11; // r15
  char *v12; // rcx
  int v13; // ecx
  struct RecoveryUnit *v14; // r15
  struct HoBtAccess *v15; // r13
  XdesRMReadWrite *v16; // rbx
  __int64 v17; // rsi
  _QWORD *v18; // rbx
  __int64 v19; // rax
  __int64 *v20; // rax
  __int64 v21; // rax
  unsigned __int8 *v22; // rsi
  void *v23; // rsp
  unsigned int v24; // r14d
  _BYTE *v25; // rcx
  __int16 *v26; // r14
  __int16 *v27; // rbx
  unsigned int v28; // edx
  unsigned __int16 *v29; // rdi
  __int64 v30; // rax
  __int64 v31; // rax
  unsigned int v32; // r8d
  __int64 v33; // rax
  __int64 v34; // rax
  __int64 v35; // rax
  __int64 v36; // rax
  char *v37; // rax
  unsigned int v38; // ebx
  unsigned __int16 v39; // r9
  char *v40; // r9
  __int16 v41; // r10
  __int16 v42; // cx
  struct RecVersioningInfo *VersioningInfo; // rax
  __int64 v44; // r9
  __int64 v45; // rdx
  int v46; // r8d
  __int16 v47; // ax
  __int64 v48; // rax
  __int64 v49; // rax
  __int64 v50; // rax
  __int64 v51; // rax
  char v52; // cl
  unsigned int v53; // ecx
  unsigned __int8 *v54; // rdx
  int v55; // ecx
  unsigned int v56; // ebx
  unsigned int v57; // ecx
  unsigned __int8 *v58; // rdx
  __int16 v59; // r8
  __int16 v60; // cx
  _QWORD *v61; // rax
  unsigned __int64 v62; // r8
  char v63; // dl
  BOOL v64; // eax
  unsigned int v65; // eax
  __int64 v66; // rdx
  int v67; // eax
  int v68; // ecx
  unsigned __int16 *v69; // rsi
  unsigned __int16 v70; // ax
  __int64 v71; // rax
  __int64 v72; // rax
  unsigned int v73; // edx
  __int64 v74; // rax
  __int64 v75; // rax
  __int64 v76; // rcx
  unsigned int v77; // eax
  __int64 v78; // rax
  __int64 v79; // rax
  __int64 v80; // rdx
  __int64 v81; // rax
  unsigned int v82; // edi
  unsigned int v83; // ecx
  unsigned int v84; // eax
  unsigned __int16 v85; // dx
  __int16 v86; // ax
  __int64 v87; // r8
  __int16 v88; // dx
  int v89; // eax
  struct RecVersioningInfo *v90; // rax
  __int64 v91; // r9
  __int64 v92; // rdx
  __int16 v93; // ax
  unsigned __int64 v94; // rdx
  int v95; // ecx
  __int64 v96; // rax
  __int64 v97; // rax
  __int64 v98; // rax
  __int64 v99; // rax
  char v100; // cl
  bool v101; // zf
  _BYTE *v102; // rax
  __int64 v103; // rdx
  unsigned __int8 AntiMatterValue; // al
  BTreeRow *v105; // r15
  __int64 *v106; // rax
  __int64 v107; // rax
  __int64 v108; // r11
  char v109; // al
  __int64 v110; // xmm1_8
  __int64 *v111; // rax
  __int64 v112; // rax
  bool v113; // r13
  __int16 v114; // dx
  __int64 v115; // rdx
  _BYTE *v116; // r9
  char v117; // al
  _BYTE *v118; // r8
  int v119; // ecx
  unsigned __int16 *v120; // rsi
  unsigned __int16 v121; // ax
  __int64 v122; // rax
  __int64 v123; // rax
  unsigned int v124; // edx
  __int64 v125; // rax
  __int64 v126; // rax
  unsigned int v127; // ecx
  __int64 v128; // rax
  __int64 v129; // rax
  __int64 v130; // rdx
  __int64 v131; // r8
  __int64 v132; // rax
  unsigned int v133; // edi
  unsigned int v134; // eax
  unsigned __int16 v135; // cx
  __int64 v136; // r8
  __int16 v137; // dx
  int v138; // eax
  struct RecVersioningInfo *v139; // rax
  __int64 v140; // r9
  __int64 v141; // rdx
  int v142; // r8d
  __int16 v143; // ax
  unsigned __int64 v144; // rdx
  int v145; // ecx
  __int64 v146; // rax
  __int64 v147; // rax
  __int64 v148; // rax
  __int64 v149; // rax
  unsigned int v150; // ecx
  _BYTE *v151; // r8
  char v152; // al
  unsigned int v153; // edx
  unsigned __int8 *v154; // r8
  unsigned __int8 *v155; // rdx
  int v156; // ecx
  unsigned int v157; // ebx
  unsigned int v158; // edx
  unsigned __int8 *v159; // rdx
  __int16 v160; // r8
  __int16 v161; // cx
  _QWORD *v162; // rax
  __int64 v163; // rax
  const struct PageRow *v164; // r14
  __int16 *v165; // rdi
  __int64 v166; // rsi
  struct XDES *v167; // rbx
  __int64 v168; // r15
  char v169; // r12
  __int64 v170; // rcx
  struct XDES *v171; // r13
  __int64 v172; // rbx
  __int64 v173; // rcx
  unsigned int v174; // eax
  __int64 v175; // rax
  struct CSessionTraceFlags *v176; // rcx
  __int64 v177; // rax
  __int64 v178; // rdi
  unsigned int v179; // ebx
  __int64 v180; // rax
  unsigned int v181; // ecx
  unsigned int v182; // ecx
  __int64 v183; // rbx
  __int64 v184; // rcx
  __int64 v185; // rax
  struct CSessionTraceFlags *v186; // rcx
  __int64 v187; // rax
  __int64 v188; // rdi
  __int64 v189; // rcx
  unsigned int v190; // ebx
  __int64 v191; // rax
  __int64 v192; // r8
  struct CSessionTraceFlags *v193; // rcx
  HANDLE ProcessHeap; // rax
  CTracePrintStream *v195; // rax
  CTracePrintStream *v196; // rbx
  char v197; // di
  __int16 v199; // r9
  unsigned __int8 *v200; // rcx
  unsigned int v201; // eax
  unsigned int v202; // eax
  BOOL v203; // edx
  char v204; // r8
  bool v205; // bl
  unsigned __int8 v206; // al
  int v207; // ecx
  char v208; // si
  char v209; // di
  __int64 v210; // rdx
  __int64 v211; // rax
  BTreeRow *v212; // r14
  struct Record *v213; // rcx
  bool v214; // r15
  int RowCountAdjustmentForLogicalRevert; // r12d
  char v216; // r14
  unsigned int v217; // edi
  unsigned __int8 *v218; // rsi
  unsigned __int16 v219; // dx
  __int64 v220; // rax
  __int64 v221; // rax
  unsigned int v222; // r8d
  __int64 v223; // rax
  __int64 v224; // rax
  __int64 v225; // rax
  __int64 v226; // rax
  unsigned __int8 *v227; // rax
  unsigned int v228; // ebx
  unsigned __int16 v229; // r9
  unsigned __int8 *v230; // rdx
  __int16 v231; // r8
  __int16 v232; // cx
  struct RecVersioningInfo *v233; // rax
  __int64 v234; // r9
  __int64 v235; // rdx
  int v236; // r8d
  __int16 v237; // ax
  __int64 v238; // rax
  __int64 v239; // rax
  __int64 v240; // rax
  __int64 v241; // rax
  char v242; // cl
  bool v243; // zf
  int v244; // r13d
  unsigned __int8 *v245; // r14
  struct HoBtAccess *v246; // r8
  int v247; // r15d
  unsigned int v248; // edx
  unsigned __int16 *v249; // rsi
  unsigned __int16 v250; // r8
  __int64 v251; // rax
  __int64 v252; // rax
  unsigned int v253; // r9d
  __int64 v254; // rax
  __int64 v255; // rax
  __int64 v256; // rax
  __int64 v257; // rax
  char *v258; // rax
  unsigned int v259; // ebx
  unsigned __int16 v260; // r10
  char *v261; // r8
  __int16 v262; // r9
  __int16 v263; // cx
  struct RecVersioningInfo *v264; // rax
  __int64 v265; // r9
  __int64 v266; // rdx
  int v267; // r8d
  __int16 v268; // ax
  __int64 v269; // rax
  __int64 v270; // rax
  __int64 v271; // rax
  __int64 v272; // rax
  char v273; // cl
  unsigned int v274; // ecx
  unsigned __int64 v275; // rbx
  void *v276; // rsi
  unsigned __int64 v277; // rdx
  XdesRMReadWrite *v278; // rbx
  unsigned int v279; // ebx
  unsigned int v280; // edi
  unsigned __int8 *v281; // rsi
  unsigned __int16 v282; // dx
  __int64 v283; // rax
  __int64 v284; // rax
  unsigned int v285; // r8d
  __int64 v286; // rax
  __int64 v287; // rax
  __int64 v288; // rax
  __int64 v289; // rax
  unsigned __int8 *v290; // rax
  unsigned int v291; // ebx
  unsigned __int16 v292; // r9
  unsigned __int8 *v293; // rdx
  __int16 v294; // r8
  __int16 v295; // cx
  struct RecVersioningInfo *v296; // rax
  __int64 v297; // r9
  __int64 v298; // rdx
  int v299; // r8d
  __int16 v300; // ax
  __int64 v301; // rax
  __int64 v302; // rax
  __int64 v303; // rax
  __int64 v304; // rax
  char v305; // cl
  bool v306; // zf
  unsigned int v307; // r13d
  unsigned __int8 *v308; // r14
  unsigned int v309; // edx
  unsigned __int16 *v310; // rsi
  unsigned __int16 v311; // r8
  __int64 v312; // rax
  __int64 v313; // rax
  unsigned int v314; // r9d
  __int64 v315; // rax
  __int64 v316; // rax
  __int64 v317; // rax
  __int64 v318; // rax
  char *v319; // rax
  unsigned int v320; // ebx
  unsigned __int16 v321; // r10
  char *v322; // r8
  __int16 v323; // r9
  __int16 v324; // cx
  struct RecVersioningInfo *v325; // rax
  __int64 v326; // r9
  __int64 v327; // rdx
  int v328; // r8d
  __int16 v329; // ax
  __int64 v330; // rax
  __int64 v331; // rax
  __int64 v332; // rax
  __int64 v333; // rax
  char v334; // cl
  unsigned int v335; // ecx
  void *v336; // rbx
  XdesRMReadWrite *v337; // rsi
  __int64 *v338; // r9
  unsigned int v339; // edi
  unsigned __int8 *v340; // rsi
  unsigned __int16 v341; // dx
  __int64 v342; // rax
  __int64 v343; // rax
  unsigned int v344; // r8d
  __int64 v345; // rax
  __int64 v346; // rax
  __int64 v347; // rax
  __int64 v348; // rax
  unsigned __int8 *v349; // rax
  unsigned int v350; // ebx
  unsigned __int16 v351; // r9
  unsigned __int8 *v352; // rdx
  __int16 v353; // r8
  __int16 v354; // cx
  struct RecVersioningInfo *v355; // rax
  __int64 v356; // rdx
  int v357; // r8d
  __int64 v358; // rax
  __int64 v359; // rax
  __int64 v360; // rax
  __int64 v361; // rax
  char v362; // cl
  bool v363; // zf
  unsigned int v364; // r13d
  unsigned __int8 *v365; // r14
  unsigned int v366; // edx
  unsigned __int16 *v367; // rsi
  unsigned __int16 v368; // r8
  __int64 v369; // rax
  __int64 v370; // rax
  unsigned int v371; // r9d
  __int64 v372; // rax
  __int64 v373; // rax
  __int64 v374; // rax
  __int64 v375; // rax
  char *v376; // rax
  unsigned int v377; // ebx
  unsigned __int16 v378; // r10
  char *v379; // r8
  __int16 v380; // r9
  __int16 v381; // cx
  struct RecVersioningInfo *v382; // rax
  __int64 v383; // rdx
  int v384; // r8d
  __int64 v385; // rax
  __int64 v386; // rax
  __int64 v387; // rax
  __int64 v388; // rax
  char v389; // cl
  unsigned int v390; // ecx
  void *v391; // rbx
  XdesRMReadWrite *v392; // rsi
  __int64 *v393; // r9
  __int16 v394; // r8
  char v395; // dl
  BOOL v396; // ecx
  unsigned int v397; // edx
  unsigned __int8 *v398; // rdi
  unsigned __int16 v399; // r8
  __int64 v400; // rax
  __int64 v401; // rax
  unsigned int v402; // r9d
  __int64 v403; // rax
  __int64 v404; // rax
  __int64 v405; // rax
  __int64 v406; // rax
  unsigned __int8 *v407; // rax
  unsigned int v408; // ebx
  unsigned __int16 v409; // r10
  unsigned __int8 *v410; // r8
  __int16 v411; // r9
  __int16 v412; // cx
  struct RecVersioningInfo *v413; // rax
  __int64 v414; // rdx
  int v415; // r8d
  __int64 v416; // rax
  __int64 v417; // rax
  __int64 v418; // rax
  __int64 v419; // rax
  unsigned __int8 *v420; // rbx
  XdesRMReadWrite *v421; // rsi
  unsigned __int8 *v422; // rsi
  unsigned __int16 v423; // dx
  __int64 v424; // rax
  __int64 v425; // rax
  unsigned int v426; // r8d
  __int64 v427; // rax
  __int64 v428; // rax
  __int64 v429; // rax
  __int64 v430; // rax
  unsigned __int8 *v431; // rax
  unsigned int v432; // ebx
  unsigned __int16 v433; // r9
  unsigned __int8 *v434; // rdx
  __int16 v435; // r8
  __int16 v436; // cx
  struct RecVersioningInfo *v437; // rax
  __int64 v438; // rdx
  int v439; // r8d
  __int64 v440; // rax
  __int64 v441; // rax
  __int64 v442; // rax
  __int64 v443; // rax
  char v444; // cl
  bool v445; // zf
  unsigned int v446; // edx
  unsigned __int16 *v447; // rsi
  unsigned __int16 v448; // r8
  __int64 v449; // rax
  __int64 v450; // rax
  unsigned int v451; // r9d
  __int64 v452; // rax
  __int64 v453; // rax
  __int64 v454; // rax
  __int64 v455; // rax
  char *v456; // rax
  unsigned int v457; // ebx
  unsigned __int16 v458; // r10
  char *v459; // r8
  __int16 v460; // r9
  __int16 v461; // cx
  struct RecVersioningInfo *v462; // rax
  __int64 v463; // rdx
  int v464; // r8d
  __int64 v465; // rax
  __int64 v466; // rax
  __int64 v467; // rax
  __int64 v468; // rax
  char v469; // cl
  unsigned int v470; // ecx
  unsigned int v471; // ecx
  unsigned int v472; // ecx
  int v473; // ebx
  __int16 v474; // di
  __int64 v475; // rax
  struct HoBtAccess *v476; // r15
  BOOL v477; // esi
  unsigned int v478; // edx
  unsigned __int16 *v479; // rdi
  unsigned __int16 v480; // r8
  __int64 v481; // rax
  __int64 v482; // rax
  unsigned int v483; // r9d
  __int64 v484; // rax
  __int64 v485; // rax
  __int64 v486; // rax
  __int64 v487; // rax
  char *v488; // rax
  unsigned int v489; // ebx
  unsigned __int16 v490; // r10
  char *v491; // r8
  __int16 v492; // r9
  __int16 v493; // cx
  struct RecVersioningInfo *v494; // rax
  __int64 v495; // rdx
  int v496; // r8d
  __int64 v497; // rax
  __int64 v498; // rax
  __int64 v499; // rax
  __int64 v500; // rax
  unsigned int v501; // edx
  unsigned __int8 *v502; // rdi
  unsigned __int16 v503; // dx
  __int64 v504; // rax
  __int64 v505; // rax
  unsigned int v506; // r8d
  __int64 v507; // rax
  __int64 v508; // rax
  __int64 v509; // rax
  __int64 v510; // rax
  unsigned __int8 *v511; // rax
  unsigned int v512; // ebx
  unsigned __int16 v513; // r9
  unsigned __int8 *v514; // rdx
  __int16 v515; // r8
  __int16 v516; // cx
  struct RecVersioningInfo *v517; // rax
  __int64 v518; // rdx
  int v519; // r8d
  __int64 v520; // rax
  __int64 v521; // rax
  __int64 v522; // rax
  __int64 v523; // rax
  char v524; // cl
  bool v525; // zf
  unsigned int v526; // r13d
  __int64 v527; // rbx
  unsigned int v528; // [rsp+0h] [rbp-1FF0h]
  int v529; // [rsp+0h] [rbp-1FF0h]
  int v530; // [rsp+8h] [rbp-1FE8h]
  int v531; // [rsp+10h] [rbp-1FE0h]
  int v532; // [rsp+18h] [rbp-1FD8h]
  unsigned int v533; // [rsp+20h] [rbp-1FD0h]
  _BYTE Destination[8016]; // [rsp+50h] [rbp-1FA0h] BYREF
  __int64 v535; // [rsp+1FA0h] [rbp-50h]
  char v536; // [rsp+1FF0h] [rbp+0h]
  char v537; // [rsp+1FF1h] [rbp+1h]
  __int16 v538; // [rsp+1FF8h] [rbp+8h] BYREF
  __int16 v539; // [rsp+1FFAh] [rbp+Ah] BYREF
  unsigned int v540; // [rsp+1FFCh] [rbp+Ch]
  void *v541; // [rsp+2000h] [rbp+10h]
  __int64 v542; // [rsp+2008h] [rbp+18h]
  unsigned int v543; // [rsp+2010h] [rbp+20h]
  unsigned __int16 v544; // [rsp+2014h] [rbp+24h]
  unsigned __int64 v545; // [rsp+2016h] [rbp+26h]
  _TBYTE v546; // [rsp+201Eh] [rbp+2Eh]
  int v547; // [rsp+2030h] [rbp+40h] BYREF
  bool v548; // [rsp+2034h] [rbp+44h]
  unsigned __int8 v549; // [rsp+2035h] [rbp+45h]
  char v550; // [rsp+2036h] [rbp+46h]
  char v551; // [rsp+2037h] [rbp+47h]
  unsigned __int8 v552[4]; // [rsp+2038h] [rbp+48h] BYREF
  unsigned int v553; // [rsp+203Ch] [rbp+4Ch]
  BTreeRow *v554; // [rsp+2040h] [rbp+50h]
  struct HoBtAccess *v555; // [rsp+2048h] [rbp+58h] BYREF
  __int16 v556; // [rsp+2050h] [rbp+60h]
  unsigned __int16 v557; // [rsp+2058h] [rbp+68h]
  int v558; // [rsp+205Ch] [rbp+6Ch]
  unsigned int v559; // [rsp+2060h] [rbp+70h]
  int v560; // [rsp+2068h] [rbp+78h] BYREF
  __int16 v561; // [rsp+206Ch] [rbp+7Ch]
  __int16 v562; // [rsp+206Eh] [rbp+7Eh]
  BOOL v563; // [rsp+2070h] [rbp+80h]
  XdesRMReadWrite *v564; // [rsp+2078h] [rbp+88h]
  struct XDES *v565; // [rsp+2080h] [rbp+90h] BYREF
  __int16 v566; // [rsp+208Ah] [rbp+9Ah]
  int v567; // [rsp+208Ch] [rbp+9Ch] BYREF
  __int16 v568; // [rsp+2090h] [rbp+A0h]
  _QWORD *v569; // [rsp+2098h] [rbp+A8h]
  int v570; // [rsp+20A0h] [rbp+B0h] BYREF
  __int16 v571; // [rsp+20A4h] [rbp+B4h]
  int v572; // [rsp+20B0h] [rbp+C0h] BYREF
  __int16 v573; // [rsp+20B4h] [rbp+C4h]
  int v574; // [rsp+20B6h] [rbp+C6h] BYREF
  __int16 v575; // [rsp+20BAh] [rbp+CAh]
  int v576; // [rsp+20BCh] [rbp+CCh] BYREF
  __int16 v577; // [rsp+20C0h] [rbp+D0h]
  int v578; // [rsp+20C2h] [rbp+D2h] BYREF
  __int16 v579; // [rsp+20C6h] [rbp+D6h]
  int v580; // [rsp+20C8h] [rbp+D8h] BYREF
  __int16 v581; // [rsp+20CCh] [rbp+DCh]
  int v582; // [rsp+20CEh] [rbp+DEh] BYREF
  __int16 v583; // [rsp+20D2h] [rbp+E2h]
  int v584; // [rsp+20D4h] [rbp+E4h] BYREF
  __int16 v585; // [rsp+20D8h] [rbp+E8h]
  int v586; // [rsp+20DAh] [rbp+EAh] BYREF
  __int16 v587; // [rsp+20DEh] [rbp+EEh]
  __int16 v588; // [rsp+20E0h] [rbp+F0h]
  __int64 v589; // [rsp+20F0h] [rbp+100h] BYREF
  unsigned int CtrNestIdFromVersionRecPtr; // [rsp+2100h] [rbp+110h]
  int v591; // [rsp+2104h] [rbp+114h] BYREF
  __int16 v592; // [rsp+2108h] [rbp+118h]
  int v593; // [rsp+210Ch] [rbp+11Ch] BYREF
  __int16 v594; // [rsp+2110h] [rbp+120h]
  __int64 v595; // [rsp+2118h] [rbp+128h]
  __int64 v596; // [rsp+2120h] [rbp+130h]
  __int64 v597; // [rsp+2128h] [rbp+138h] BYREF
  unsigned __int16 v598; // [rsp+2130h] [rbp+140h]
  unsigned int v599; // [rsp+2138h] [rbp+148h]
  char v600[8]; // [rsp+213Ch] [rbp+14Ch] BYREF
  __int64 v601; // [rsp+2144h] [rbp+154h] BYREF
  char v602[8]; // [rsp+214Ch] [rbp+15Ch] BYREF
  char v603[8]; // [rsp+2154h] [rbp+164h] BYREF
  _BYTE v604[12]; // [rsp+215Ch] [rbp+16Ch] BYREF
  __int64 v605; // [rsp+2168h] [rbp+178h]
  unsigned int v606[2]; // [rsp+2178h] [rbp+188h] BYREF
  __int64 v607; // [rsp+21E0h] [rbp+1F0h]
  _BYTE v608[96]; // [rsp+2200h] [rbp+210h] BYREF
  char v609[8]; // [rsp+2260h] [rbp+270h] BYREF
  int v610; // [rsp+2268h] [rbp+278h]
  int v611; // [rsp+2270h] [rbp+280h]
  _QWORD *v612; // [rsp+2278h] [rbp+288h]
  char *v613; // [rsp+2280h] [rbp+290h]
  __int64 v614; // [rsp+2288h] [rbp+298h]
  _QWORD v615[2]; // [rsp+2290h] [rbp+2A0h] BYREF
  char v616; // [rsp+22A0h] [rbp+2B0h] BYREF
  __int64 v617; // [rsp+24B0h] [rbp+4C0h]
  __int64 v618; // [rsp+24B8h] [rbp+4C8h]
  __int16 v619; // [rsp+24C0h] [rbp+4D0h] BYREF
  int v620; // [rsp+24C2h] [rbp+4D2h]
  __int16 v621; // [rsp+24C6h] [rbp+4D6h]
  __int16 v622; // [rsp+24D0h] [rbp+4E0h] BYREF
  __int16 v623; // [rsp+24D2h] [rbp+4E2h] BYREF
  unsigned int v624; // [rsp+24D4h] [rbp+4E4h]
  unsigned __int8 *v625; // [rsp+24D8h] [rbp+4E8h]
  __int64 v626; // [rsp+24E0h] [rbp+4F0h]
  unsigned int v627; // [rsp+24E8h] [rbp+4F8h]
  unsigned __int16 v628; // [rsp+24ECh] [rbp+4FCh]
  unsigned __int64 v629; // [rsp+24EEh] [rbp+4FEh]
  _TBYTE v630; // [rsp+24F6h] [rbp+506h]
  unsigned int v631; // [rsp+2500h] [rbp+510h]
  int v632; // [rsp+2504h] [rbp+514h]
  __int64 v633; // [rsp+2580h] [rbp+590h] BYREF
  int v634; // [rsp+2588h] [rbp+598h]
  __int16 v635; // [rsp+258Ch] [rbp+59Ch]
  __int16 v636; // [rsp+2590h] [rbp+5A0h] BYREF
  __int16 v637; // [rsp+2592h] [rbp+5A2h] BYREF
  unsigned int v638; // [rsp+2594h] [rbp+5A4h]
  void *Source; // [rsp+2598h] [rbp+5A8h]
  _QWORD *v640; // [rsp+25A0h] [rbp+5B0h]
  unsigned int v641; // [rsp+25A8h] [rbp+5B8h]
  unsigned __int16 v642; // [rsp+25ACh] [rbp+5BCh]
  unsigned __int64 v643; // [rsp+25AEh] [rbp+5BEh]
  _TBYTE v644; // [rsp+25B6h] [rbp+5C6h]
  int v645; // [rsp+25C4h] [rbp+5D4h]
  __int16 v646; // [rsp+2640h] [rbp+650h] BYREF
  __int16 v647; // [rsp+2642h] [rbp+652h] BYREF
  unsigned int v648; // [rsp+2644h] [rbp+654h]
  unsigned __int8 *v649; // [rsp+2648h] [rbp+658h]
  _QWORD *v650; // [rsp+2650h] [rbp+660h]
  unsigned int v651; // [rsp+2658h] [rbp+668h]
  unsigned __int16 v652; // [rsp+265Ch] [rbp+66Ch]
  __int64 v653; // [rsp+265Eh] [rbp+66Eh]
  _TBYTE v654; // [rsp+2666h] [rbp+676h]
  unsigned __int8 *v655; // [rsp+2678h] [rbp+688h]
  int v656; // [rsp+2680h] [rbp+690h]
  __int64 v657; // [rsp+2688h] [rbp+698h] BYREF
  __int16 v658; // [rsp+2690h] [rbp+6A0h]
  __int64 v659; // [rsp+2698h] [rbp+6A8h] BYREF
  __int16 v660; // [rsp+26A0h] [rbp+6B0h]
  __int16 v661; // [rsp+26A8h] [rbp+6B8h] BYREF
  __int16 v662; // [rsp+26AAh] [rbp+6BAh] BYREF
  unsigned int v663; // [rsp+26ACh] [rbp+6BCh]
  unsigned __int8 *v664; // [rsp+26B0h] [rbp+6C0h]
  __int64 v665; // [rsp+26B8h] [rbp+6C8h]
  unsigned int v666; // [rsp+26C0h] [rbp+6D0h]
  __int16 v667; // [rsp+26C4h] [rbp+6D4h]
  __int64 v668; // [rsp+26C6h] [rbp+6D6h]
  _TBYTE v669; // [rsp+26CEh] [rbp+6DEh]
  int v670; // [rsp+26DCh] [rbp+6ECh]
  unsigned __int8 v671[2656]; // [rsp+2760h] [rbp+770h] BYREF
  unsigned __int8 v672[8096]; // [rsp+31C0h] [rbp+11D0h] BYREF
  unsigned __int8 v673[8096]; // [rsp+5160h] [rbp+3170h] BYREF

  v607 = -2;
  v564 = a3;
  v589 = a2;
  v3 = (BTreeRow *)a1;
  v554 = (BTreeRow *)a1;
  v4 = *(struct XDES **)(*(_QWORD *)(a1 + 40) + 8LL);
  v565 = v4;
  v5 = *((_QWORD *)v4 + 6);
  v596 = v5;
  v6 = *(_DWORD *)(a1 + 16) & 0xFFFFFEFF;
  *(_DWORD *)(a1 + 16) = v6;
  if ( (v6 & 0x80u) == 0 && (*(_BYTE *)(a1 + 52) & 1) != 0 )
    RecordLong = (unsigned __int8 **)(a1 + 72);
  else
    RecordLong = (unsigned __int8 **)BTreeRow::GetRecordLong((BTreeRow *)a1, 1);
  v8 = 0;
  v553 = 0;
  v9 = (char *)RecordLong + 2;
  if ( *(_WORD *)RecordLong )
    CDRecord::GetXdesTs(v9, &v572);
  else
    FixedVarRecord::GetXdesTs(v9, &v572);
  v10 = v572;
  v570 = v572;
  v593 = v572;
  v11 = v573;
  v566 = v573;
  v594 = v573;
  v567 = v572;
  v568 = v573;
  v12 = (char *)RecordLong + 2;
  if ( *(_WORD *)RecordLong )
    CDRecord::GetVersionRecPtr(v12, &v586);
  else
    FixedVarRecord::GetVersionRecPtr(v12, &v586);
  v560 = v586;
  v561 = v587;
  v562 = v588;
  v13 = (*RecordLong[1] >> 1) & 1;
  if ( !*(_WORD *)RecordLong )
    v13 = (*RecordLong[1] >> 6) & 1;
  if ( !v13 || word_10318AB38 == v11 && NullXdesId == v10 )
    goto LABEL_1689;
  v14 = (struct RecoveryUnit *)v5;
  if ( !(unsigned int)XdesMgr::GetRowAbortState(v5 + 6600, &v567, &v560) )
    goto LABEL_1689;
  v622 = -1;
  v625 = 0;
  v624 = 0;
  v629 = 0;
  *(_QWORD *)((char *)&v630 + 2) = 0;
  v626 = 0;
  v632 = -1;
  v636 = -1;
  Source = 0;
  v638 = 0;
  v643 = 0;
  *(_QWORD *)((char *)&v644 + 2) = 0;
  v640 = 0;
  v645 = -1;
  v646 = -1;
  v649 = 0;
  v648 = 0;
  v653 = 0;
  *(_QWORD *)((char *)&v654 + 2) = 0;
  v650 = 0;
  v655 = 0;
  v656 = 0;
  v538 = -1;
  v541 = 0;
  v540 = 0;
  v545 = 0;
  *(_QWORD *)((char *)&v546 + 2) = 0;
  v542 = 0;
  v15 = (struct HoBtAccess *)**((_QWORD **)v3 + 5);
  v555 = v15;
  v547 = 0;
  v548 = 0;
  LOBYTE(v558) = 0;
  v595 = 0;
  v633 = 0;
  v634 = 0;
  v635 = 0;
  v536 = 0;
  v661 = -1;
  v664 = 0;
  v663 = 0;
  v668 = 0;
  *(_QWORD *)((char *)&v669 + 2) = 0;
  v665 = 0;
  v670 = -1;
  v550 = 0;
  if ( *(_BYTE *)(v5 + 8272) )
  {
    scierrlogwithstate(0x298u, 10, 2);
    DBTABLE::RaiseReadonlyDbError(*(DBTABLE **)(v5 + 1712));
  }
  v569 = 0;
  v551 = 1;
  v16 = v564;
  if ( !v564 )
  {
    v551 = 0;
    v17 = *((_QWORD *)v4 + 82);
    v18 = (_QWORD *)(*(__int64 (__fastcall **)(struct IAutoXactFactory *))(*(_QWORD *)g_pAutoXactFactory + 8LL))(g_pAutoXactFactory);
    if ( v569 != v18 && v569 )
      (*(void (__fastcall **)(_QWORD *, __int64))*v569)(v569, 1);
    v569 = v18;
    v19 = *v18;
    LOBYTE(v535) = 0;
    (*(void (__fastcall **)(_QWORD *, const wchar_t *, __int64, __int64, _DWORD))(v19 + 24))(
      v18,
      L"BTreeRow::RevertFromVersion",
      54,
      v17,
      v535);
    v16 = (XdesRMReadWrite *)(*(__int64 (__fastcall **)(_QWORD *, struct RecoveryUnit *))(*v569 + 88LL))(v569, v14);
    v564 = v16;
    (*(void (__fastcall **)(XdesRMReadWrite *, _QWORD))(*(_QWORD *)v16 + 840LL))(v16, 0);
  }
  v537 = (*(__int64 (__fastcall **)(XdesRMReadWrite *))(*(_QWORD *)v16 + 8LL))(v16);
  PageRow::Clone((PageRow *)&v636, (const struct PageRow *)RecordLong);
  if ( (*((_DWORD *)qword_10317B628 + 11) & 0x20) != 0 )
  {
    v20 = *(__int64 **)(*((_QWORD *)v3 + 3) + 48LL);
    if ( v20 )
    {
      v21 = *v20;
      if ( v21 )
      {
        if ( v21 != *((_QWORD *)v3 + 4) )
          *((_QWORD *)v3 + 4) = v21;
      }
    }
  }
  if ( *(char *)(*((_QWORD *)v3 + 4) + 2LL) >= 0
    || *(char *)(((unsigned __int64)Source & 0xFFFFFFFFFFFFE000uLL) + 2) >= 0 )
  {
    v22 = v655;
  }
  else
  {
    v22 = v655;
    if ( !v655 )
    {
      v23 = alloca(8096);
      v22 = Destination;
      v655 = Destination;
      v24 = 8094;
      v656 = 8094;
      goto LABEL_35;
    }
  }
  v24 = v656;
LABEL_35:
  v25 = Source;
  if ( *(char *)(((unsigned __int64)Source & 0xFFFFFFFFFFFFE000uLL) + 2) >= 0 )
  {
    v26 = &v636;
    v27 = &v637;
    goto LABEL_151;
  }
  v646 = v636;
  if ( v636 )
  {
    if ( v640 && *v640 )
    {
      Record::DecompressRec((Record *)&v646, v22, v24, (const struct Record *)&v636);
    }
    else
    {
      CDRecord::CopyNewRec((CDRecord *)&v647, v22, v24, (const struct CDRecord *)&v637);
      v61 = v640;
      if ( !v636 )
        v61 = 0;
      v650 = v61;
    }
    goto LABEL_150;
  }
  v28 = v638;
  if ( !v638 )
  {
    v637 = 0;
    v28 = (unsigned int)v640;
    HIDWORD(v640) = (_DWORD)v640;
    if ( (*(_BYTE *)Source & 0x10) != 0 )
    {
      v28 = (((unsigned int)*(unsigned __int16 *)((char *)Source + (unsigned int)v640) + 7) >> 3) + (_DWORD)v640 + 2;
      HIDWORD(v640) = v28;
    }
    if ( (*(_BYTE *)Source & 0x20) != 0 )
    {
      v29 = (unsigned __int16 *)((char *)Source + v28);
      v642 = *v29;
      if ( !v642 )
      {
        if ( byte_10316E8D7 || (qword_10317B120 & 1) != 0 )
        {
          v30 = *(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                          + SystemThread_TlsOffset
                          + 8LL);
          if ( v30 )
          {
            v31 = *(_QWORD *)(v30 + 96);
            if ( v31 )
            {
              if ( *(_BYTE *)(v31 + 1177) )
              {
                if ( byte_10316E7C7 || (qword_10317B120 & 2) != 0 )
                  utassert_fail(1u, "false", "Sql\\Ntdbms\\storeng\\drs\\fixedvarrecord.cpp", 2010, 0);
                else
                  ex_raise(34, 68, 21, 1003);
              }
            }
          }
        }
        RaiseInconsistencyError(Source, 3);
      }
      v32 = HIDWORD(v640) + 2 * (v642 + 1);
      v641 = v32;
      if ( v32 > 0x1F9E )
      {
        if ( byte_10316E8D7 || (qword_10317B120 & 1) != 0 )
        {
          v33 = *(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                          + SystemThread_TlsOffset
                          + 8LL);
          if ( v33 )
          {
            v34 = *(_QWORD *)(v33 + 96);
            if ( v34 )
            {
              if ( *(_BYTE *)(v34 + 1177) )
              {
                if ( byte_10316E7C7 || (qword_10317B120 & 2) != 0 )
                  utassert_fail(1u, "false", "Sql\\Ntdbms\\storeng\\drs\\fixedvarrecord.cpp", 2017, 0);
                else
                  ex_raise(34, 68, 21, 1004);
              }
            }
          }
        }
        RaiseInconsistencyError(Source, 4);
        v32 = v641;
      }
      v28 = v29[v642] & 0x7FFF;
      v638 = v28;
      if ( v32 > v28 )
      {
        if ( byte_10316E8D7 || (qword_10317B120 & 1) != 0 )
        {
          v35 = *(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                          + SystemThread_TlsOffset
                          + 8LL);
          if ( v35 )
          {
            v36 = *(_QWORD *)(v35 + 96);
            if ( v36 )
            {
              if ( *(_BYTE *)(v36 + 1177) )
              {
                if ( byte_10316E7C7 || (qword_10317B120 & 2) != 0 )
                  utassert_fail(1u, "false", "Sql\\Ntdbms\\storeng\\drs\\fixedvarrecord.cpp", 2024, 0);
                else
                  ex_raise(34, 68, 21, 1004);
              }
            }
          }
        }
        RaiseInconsistencyError(Source, 4);
        v32 = v641;
        v28 = v638;
      }
      while ( (v29[v642] & 0x8000u) != 0 )
      {
        v37 = (char *)Source + HIDWORD(v640);
        if ( v642 == 1 )
          v38 = v32;
        else
          v38 = *(_WORD *)&v37[2 * v642 - 2] & 0x7FFF;
        if ( v38 < v32 || (*(_WORD *)&v37[2 * v642] & 0x7FFFu) < v38 )
        {
          RaiseInconsistencyError(Source, 7);
          v32 = v641;
          v28 = v638;
        }
        if ( v38 < v32 || v38 > v28 )
          goto LABEL_126;
        v39 = *(_WORD *)((char *)Source + v38);
        if ( v39 == 5 )
        {
          v637 |= 2u;
          --v642;
          WORD2(v644) = v38;
          v40 = (char *)Source + (unsigned __int16)v38;
          v41 = *((_WORD *)v40 + 1);
          if ( (v41 & 0x4000) != 0 )
            v42 = (v41 ^ WORD3(v644)) & 0x3800 ^ WORD3(v644);
          else
            v42 = WORD3(v644) & 0xC7FF;
          WORD3(v644) = v42;
          WORD3(v644) = v42 ^ (*((_WORD *)v40 + 1) ^ v42) & 0x7FF;
          break;
        }
        if ( v39 >= 0x400u )
        {
          v637 |= 1u;
          if ( --v642 )
            continue;
        }
        break;
      }
    }
    else
    {
      v638 = v28;
      v642 = 0;
      v32 = v28;
      v641 = v28;
    }
    if ( (*(_BYTE *)Source & 0x40) != 0 )
    {
      LODWORD(v644) = v28;
      v638 = v28 + 14;
      VersioningInfo = FixedVarRecord::FindVersioningInfo((FixedVarRecord *)&v637);
      v44 = HIDWORD(*(_QWORD *)VersioningInfo);
      v45 = HIWORD(*(_QWORD *)VersioningInfo);
      v46 = 0;
      if ( (((__int16)v45 ^ ((unsigned int)(__int16)v45 >> 1)) & 0x2000) != 0 )
      {
        v47 = v45 & 0xDFFF;
        if ( (v45 & 0x4000) != 0 )
          v47 = v45 | 0x2000;
        LOWORD(v45) = v47;
      }
      if ( (_WORD)v45 == 0xFFFC )
        v46 = (unsigned __int16)v44 >> 5;
      v28 = v46 + v638;
      v638 += v46;
      v32 = v641;
    }
    else
    {
      LODWORD(v644) = 0;
    }
    if ( v643 && v643 < (unsigned __int64)Source + v28 )
    {
      if ( byte_10316E8D7 || (qword_10317B120 & 1) != 0 )
      {
        v48 = *(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                        + SystemThread_TlsOffset
                        + 8LL);
        if ( v48 )
        {
          v49 = *(_QWORD *)(v48 + 96);
          if ( v49 )
          {
            if ( *(_BYTE *)(v49 + 1177) )
            {
              if ( byte_10316E7C7 || (qword_10317B120 & 2) != 0 )
                utassert_fail(1u, "false", "Sql\\Ntdbms\\storeng\\drs\\fixedvarrecord.cpp", 2114, 0);
              else
                ex_raise(34, 68, 21, 1018);
            }
          }
        }
      }
      RaiseInconsistencyError(Source, 18);
      v32 = v641;
      v28 = v638;
    }
    if ( v28 - 1 <= 0x3F3B )
      goto LABEL_126;
    if ( byte_10316E8D7 || (qword_10317B120 & 1) != 0 )
    {
      v50 = *(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                      + SystemThread_TlsOffset
                      + 8LL);
      if ( v50 )
      {
        v51 = *(_QWORD *)(v50 + 96);
        if ( v51 )
        {
          if ( *(_BYTE *)(v51 + 1177) )
          {
            if ( byte_10316E7C7 || (qword_10317B120 & 2) != 0 )
              utassert_fail(1u, "false", "Sql\\Ntdbms\\storeng\\drs\\fixedvarrecord.cpp", 2119, 0);
            else
              ex_raise(34, 68, 21, 1005);
          }
        }
      }
    }
    RaiseInconsistencyError(Source, 5);
    v28 = v638;
  }
  v32 = v641;
LABEL_126:
  if ( v28 >= 9 || (v52 = *(_BYTE *)Source & 0xE) != 0 && v52 != 12 )
    v53 = v28;
  else
    v53 = 9;
  v650 = v640;
  v647 = v637;
  v648 = v28;
  v652 = v642;
  v651 = v32;
  LODWORD(v654) = LODWORD(v644);
  memcpy_s(v22, v24, Source, v53);
  v649 = v22;
  if ( (unsigned int)FixedVarRecord::HasSparseVector((FixedVarRecord *)&v647) )
  {
    v54 = &v649[HIDWORD(v650)];
    v55 = *(unsigned __int16 *)v54 - 1;
    if ( (v647 & 1) == 0 )
      v55 = *(unsigned __int16 *)v54;
    if ( v55 == 1 )
      v56 = v651;
    else
      v56 = *(_WORD *)&v54[2 * v55 - 2] & 0x7FFF;
    v57 = *(_WORD *)&v54[2 * v55] & 0x7FFF;
    if ( v56 < v651 || v57 < v56 )
      RaiseInconsistencyError(v649, 7);
    WORD2(v654) = v56;
    v58 = &v649[(unsigned __int16)v56];
    v59 = *((_WORD *)v58 + 1);
    if ( (v59 & 0x4000) != 0 )
      v60 = (v59 ^ WORD3(v654)) & 0x3800 ^ WORD3(v654);
    else
      v60 = WORD3(v654) & 0xC7FF;
    WORD3(v654) = v60;
    WORD3(v654) = v60 ^ (*((_WORD *)v58 + 1) ^ v60) & 0x7FF;
  }
LABEL_150:
  v26 = &v646;
  v27 = &v647;
  v25 = v649;
LABEL_151:
  v62 = (unsigned __int16)*v26;
  if ( (_WORD)v62 )
  {
    v64 = (((*v25 & 0x1C) - 4) & 0xFFFFFFE7) == 0;
  }
  else
  {
    v63 = *v25 & 0xE;
    v563 = 0;
    if ( v63 == 2 )
    {
      v563 = (v25[1] & 1) != 0;
      goto LABEL_158;
    }
    if ( ((v63 - 10) & 0xF9) != 0 )
      goto LABEL_158;
    v64 = 1;
  }
  v563 = v64;
LABEL_158:
  v599 = ((v562 ^ ((unsigned int)v562 >> 1)) >> 13) & 1;
  v65 = *(_DWORD *)(v27 + 1);
  v559 = v65;
  if ( !(_WORD)v62 )
  {
    if ( !v65 )
    {
      *v27 = 0;
      v66 = *(unsigned int *)(v27 + 7);
      *(_DWORD *)(v27 + 9) = v66;
      v62 = *(_QWORD *)(v27 + 3);
      v67 = *(unsigned __int8 *)v62;
      v68 = v66;
      if ( (*(_BYTE *)v62 & 0x10) != 0 )
      {
        LODWORD(v66) = (((unsigned int)*(unsigned __int16 *)(v66 + v62) + 7) >> 3) + 2 + v66;
        *(_DWORD *)(v27 + 9) = v66;
        LOBYTE(v67) = *(_BYTE *)v62;
        v68 = v66;
      }
      if ( (v67 & 0x20) != 0 )
      {
        v69 = (unsigned __int16 *)(v62 + (unsigned int)v66);
        v70 = *v69;
        v27[13] = *v69;
        if ( !v70 )
        {
          if ( byte_10316E8D7 || (qword_10317B120 & 1) != 0 )
          {
            v71 = *(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                            + SystemThread_TlsOffset
                            + 8LL);
            if ( v71 )
            {
              v72 = *(_QWORD *)(v71 + 96);
              if ( v72 )
              {
                if ( *(_BYTE *)(v72 + 1177) )
                {
                  if ( byte_10316E7C7 || (qword_10317B120 & 2) != 0 )
                    utassert_fail(1u, "false", "Sql\\Ntdbms\\storeng\\drs\\fixedvarrecord.cpp", 2010, 0);
                  else
                    ex_raise(34, 68, 21, 1003);
                }
              }
            }
          }
          RaiseInconsistencyError(*(_QWORD *)(v27 + 3), 3);
          v70 = v27[13];
          v68 = *(_DWORD *)(v27 + 9);
        }
        v73 = v68 + 2 * (v70 + 1);
        *(_DWORD *)(v27 + 11) = v73;
        if ( v73 > 0x1F9E )
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
                    utassert_fail(1u, "false", "Sql\\Ntdbms\\storeng\\drs\\fixedvarrecord.cpp", 2017, 0);
                  else
                    ex_raise(34, 68, 21, 1004);
                }
              }
            }
          }
          RaiseInconsistencyError(*(_QWORD *)(v27 + 3), 4);
          v73 = *(_DWORD *)(v27 + 11);
        }
        v76 = (unsigned __int16)v27[13];
        v77 = v69[v76] & 0x7FFF;
        *(_DWORD *)(v27 + 1) = v77;
        if ( v73 > v77 )
        {
          if ( byte_10316E8D7 || (qword_10317B120 & 1) != 0 )
          {
            v78 = *(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                            + SystemThread_TlsOffset
                            + 8LL);
            if ( v78 )
            {
              v79 = *(_QWORD *)(v78 + 96);
              if ( v79 )
              {
                if ( *(_BYTE *)(v79 + 1177) )
                {
                  if ( byte_10316E7C7 || (qword_10317B120 & 2) != 0 )
                    utassert_fail(1u, "false", "Sql\\Ntdbms\\storeng\\drs\\fixedvarrecord.cpp", 2024, 0);
                  else
                    ex_raise(34, 68, 21, 1004);
                }
              }
            }
          }
          RaiseInconsistencyError(*(_QWORD *)(v27 + 3), 4);
          LOWORD(v76) = v27[13];
        }
        while ( 1 )
        {
          v80 = (unsigned __int16)v76;
          if ( (v69[(unsigned __int16)v76] & 0x8000u) == 0 )
          {
LABEL_211:
            v62 = *(_QWORD *)(v27 + 3);
            goto LABEL_213;
          }
          v81 = *(_QWORD *)(v27 + 3) + *(unsigned int *)(v27 + 9);
          if ( (unsigned __int16)v76 == 1 )
          {
            v82 = *(_DWORD *)(v27 + 11);
            v83 = v82;
            v84 = *(_WORD *)(v81 + 2 * v80) & 0x7FFF;
          }
          else
          {
            v82 = *(_WORD *)(v81 + 2LL * (unsigned __int16)v76 - 2) & 0x7FFF;
            v83 = *(_DWORD *)(v27 + 11);
            v84 = *(_WORD *)(v81 + 2 * v80) & 0x7FFF;
            if ( v82 < v83 )
              goto LABEL_201;
          }
          if ( v84 < v82 )
          {
LABEL_201:
            RaiseInconsistencyError(*(_QWORD *)(v27 + 3), 7);
            v83 = *(_DWORD *)(v27 + 11);
          }
          if ( v82 < v83 || v82 > *(_DWORD *)(v27 + 1) )
            goto LABEL_245;
          v85 = *(_WORD *)(v82 + *(_QWORD *)(v27 + 3));
          if ( v85 == 5 )
          {
            *v27 |= 2u;
            --v27[13];
            v27[20] = v82;
            v87 = *(_QWORD *)(v27 + 3) + (unsigned __int16)v82;
            v88 = v27[21] & 0xC7FF;
            if ( _bittest16((const signed __int16 *)(v87 + 2), 0xEu) )
              v88 |= *(_WORD *)(v87 + 2) & 0x3800;
            v27[21] = v88;
            v27[21] = v88 ^ (*(_WORD *)(v87 + 2) ^ v88) & 0x7FF;
            goto LABEL_211;
          }
          if ( v85 < 0x400u )
            goto LABEL_211;
          *v27 |= 1u;
          v86 = v27[13] - 1;
          v27[13] = v86;
          if ( !v86 )
            goto LABEL_211;
          LOWORD(v76) = v86;
        }
      }
      *(_DWORD *)(v27 + 1) = v66;
      v27[13] = 0;
      *(_DWORD *)(v27 + 11) = v68;
LABEL_213:
      if ( (*(_BYTE *)v62 & 0x40) != 0 )
      {
        v89 = *(_DWORD *)(v27 + 1);
        *((_DWORD *)v27 + 9) = v89;
        *(_DWORD *)(v27 + 1) = v89 + 14;
        v90 = FixedVarRecord::FindVersioningInfo((FixedVarRecord *)v27);
        v91 = HIDWORD(*(_QWORD *)v90);
        v92 = HIWORD(*(_QWORD *)v90);
        v62 = 0;
        if ( (((__int16)v92 ^ ((unsigned int)(__int16)v92 >> 1)) & 0x2000) != 0 )
        {
          v93 = v92 & 0xDFFF;
          if ( (v92 & 0x4000) != 0 )
            v93 = v92 | 0x2000;
          LOWORD(v92) = v93;
        }
        if ( (_WORD)v92 == 0xFFFC )
          v62 = (unsigned __int16)v91 >> 5;
        *(_DWORD *)(v27 + 1) += v62;
      }
      else
      {
        *((_DWORD *)v27 + 9) = 0;
      }
      v94 = *(_QWORD *)(v27 + 14);
      v95 = *(_DWORD *)(v27 + 1);
      if ( v94 && v94 < *(_QWORD *)(v27 + 3) + (unsigned __int64)*(unsigned int *)(v27 + 1) )
      {
        if ( byte_10316E8D7 || (qword_10317B120 & 1) != 0 )
        {
          v96 = *(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                          + SystemThread_TlsOffset
                          + 8LL);
          if ( v96 )
          {
            v97 = *(_QWORD *)(v96 + 96);
            if ( v97 )
            {
              if ( *(_BYTE *)(v97 + 1177) )
              {
                if ( byte_10316E7C7 || (qword_10317B120 & 2) != 0 )
                  utassert_fail(1u, "false", "Sql\\Ntdbms\\storeng\\drs\\fixedvarrecord.cpp", 2114, 0);
                else
                  ex_raise(34, 68, 21, 1018);
              }
            }
          }
        }
        RaiseInconsistencyError(*(_QWORD *)(v27 + 3), 18);
        v95 = *(_DWORD *)(v27 + 1);
      }
      if ( (unsigned int)(v95 - 1) > 0x3F3B )
      {
        if ( byte_10316E8D7 || (qword_10317B120 & 1) != 0 )
        {
          v98 = *(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                          + SystemThread_TlsOffset
                          + 8LL);
          if ( v98 )
          {
            v99 = *(_QWORD *)(v98 + 96);
            if ( v99 )
            {
              if ( *(_BYTE *)(v99 + 1177) )
              {
                if ( byte_10316E7C7 || (qword_10317B120 & 2) != 0 )
                  utassert_fail(1u, "false", "Sql\\Ntdbms\\storeng\\drs\\fixedvarrecord.cpp", 2119, 0);
                else
                  ex_raise(34, 68, 21, 1005);
              }
            }
          }
        }
        RaiseInconsistencyError(*(_QWORD *)(v27 + 3), 5);
      }
    }
LABEL_245:
    v559 = *(_DWORD *)(v27 + 1);
    if ( v559 >= 9 )
      goto LABEL_255;
    v100 = **(_BYTE **)(v27 + 3) & 0xE;
    if ( v100 )
    {
      v101 = v100 == 12;
      goto LABEL_253;
    }
LABEL_254:
    v559 = 9;
    goto LABEL_255;
  }
  if ( !v65 )
  {
    CDRecord::Resize((CDRecord *)v27);
    v65 = *(_DWORD *)(v27 + 1);
    v559 = v65;
  }
  if ( v65 >= 9 )
    goto LABEL_255;
  v102 = *(_BYTE **)(v27 + 3);
  if ( (*v102 & 0x1C) == 0 )
    goto LABEL_254;
  v101 = (*v102 & 0x1C) == 12;
LABEL_253:
  if ( v101 )
    goto LABEL_254;
LABEL_255:
  v659 = 0;
  v660 = 0;
  CtrNestIdFromVersionRecPtr = VersionMgr::GetCtrNestIdFromVersionRecPtr(
                                 (const struct VersionRecPtr *)&v560,
                                 v14,
                                 (const unsigned __int16 *)v62,
                                 (const struct LSN *)&v659,
                                 (struct VersionRecPtr *)v606,
                                 0);
  LongRecord_FormatKeyValuesIntoRecord(v15, (const struct Record *)v26, 0, v671, v528, (struct Record *)&v538);
  if ( v537 || !(v548 = (*(_BYTE *)(*((_QWORD *)v15 + 1) + 264LL) & 0x40) != 0) )
    AntiMatterValue = v552[0];
  else
    AntiMatterValue = IndexDataSetSession::ShortRecord_GetAntiMatterValue(v15, (const struct Record *)v26);
  v549 = AntiMatterValue;
  v105 = v554;
  if ( (*((_DWORD *)qword_10317B628 + 11) & 0x20) != 0 )
  {
    v106 = *(__int64 **)(*((_QWORD *)v554 + 3) + 48LL);
    if ( v106 )
    {
      v107 = *v106;
      if ( v107 )
      {
        if ( v107 != *((_QWORD *)v554 + 4) )
          *((_QWORD *)v554 + 4) = v107;
      }
    }
  }
  v108 = *((_QWORD *)v105 + 4);
  if ( !*(_WORD *)(v108 + 36) )
    goto LABEL_273;
  v109 = *(_BYTE *)(v108 + 1);
  if ( v109 != 11 )
  {
    if ( v109 == 8 )
    {
LABEL_270:
      if ( *(_DWORD *)(v108 + 24) == 99 )
        goto LABEL_271;
LABEL_273:
      v110 = *(_QWORD *)(v108 + 40);
      v597 = v110;
      v557 = *(_WORD *)(v108 + 48);
      v598 = v557;
      goto LABEL_274;
    }
LABEL_269:
    if ( v109 != 9 )
      goto LABEL_273;
    goto LABEL_270;
  }
  if ( *(_DWORD *)(v108 + 24) != 99 )
    goto LABEL_269;
LABEL_271:
  v591 = *(_DWORD *)(v108 + 32);
  v592 = *(_WORD *)(v108 + 36);
  if ( !(unsigned __int8)IsConcurrentUpdateSupportedPageId(&v591, v103) )
    goto LABEL_273;
  PageHeader::GetIcxLsn(v108, &v597);
  v557 = v598;
  v110 = v597;
LABEL_274:
  v605 = v110;
  if ( (*((_DWORD *)qword_10317B628 + 11) & 0x20) != 0 )
  {
    v111 = *(__int64 **)(*((_QWORD *)v105 + 3) + 48LL);
    if ( v111 )
    {
      v112 = *v111;
      if ( v112 )
      {
        if ( v112 != *((_QWORD *)v105 + 4) )
          *((_QWORD *)v105 + 4) = v112;
      }
    }
  }
  v113 = (*(_WORD *)(*((_QWORD *)v105 + 4) + 4LL) & 0x2000) != 0;
  if ( v560 >= 0 )
    goto LABEL_401;
  v114 = v562;
  if ( ((v562 ^ ((unsigned int)v562 >> 1)) & 0x2000) != 0 )
  {
    v114 = v562 & 0xDFFF;
    if ( (v562 & 0x4000) != 0 )
      v114 = v562 | 0x2000;
  }
  if ( v114 == -4 )
    utassert_fail(1u, "!IsInRowDiff()", "setypes.cpp", 1260, 0);
  if ( VersionRecPtr::IsNull((VersionRecPtr *)&v560)
    || VersionRecPtr::IsInvalid((VersionRecPtr *)&v560)
    || (v562 & 0x1000) == 0 )
  {
    v661 = *v26;
    if ( v661 )
    {
      v162 = (_QWORD *)*((_QWORD *)v26 + 2);
      if ( v162 && *v162 )
      {
        Record::DecompressRec((Record *)&v661, v672, 0x1F9Eu, (const struct Record *)v26);
      }
      else
      {
        CDRecord::CopyNewRec((CDRecord *)&v662, v672, 0x1F9Eu, (const struct CDRecord *)(v26 + 1));
        v163 = 0;
        if ( *v26 )
          v163 = *((_QWORD *)v26 + 2);
        v665 = v163;
      }
    }
    else
    {
      if ( !*((_DWORD *)v26 + 1) )
      {
        v26[1] = 0;
        v115 = *((unsigned int *)v26 + 4);
        *((_DWORD *)v26 + 5) = v115;
        v116 = (_BYTE *)*((_QWORD *)v26 + 1);
        v117 = *v116;
        v118 = v116;
        v119 = v115;
        if ( (*v116 & 0x10) != 0 )
        {
          LODWORD(v115) = (((unsigned int)*(unsigned __int16 *)&v116[v115] + 7) >> 3) + 2 + v115;
          *((_DWORD *)v26 + 5) = v115;
          v117 = *v116;
          v119 = v115;
        }
        if ( (v117 & 0x20) != 0 )
        {
          v120 = (unsigned __int16 *)&v116[(unsigned int)v115];
          v121 = *v120;
          v26[14] = *v120;
          if ( !v121 )
          {
            if ( byte_10316E8D7 || (qword_10317B120 & 1) != 0 )
            {
              v122 = *(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                               + SystemThread_TlsOffset
                               + 8LL);
              if ( v122 )
              {
                v123 = *(_QWORD *)(v122 + 96);
                if ( v123 )
                {
                  if ( *(_BYTE *)(v123 + 1177) )
                  {
                    if ( byte_10316E7C7 || (qword_10317B120 & 2) != 0 )
                      utassert_fail(1u, "false", "Sql\\Ntdbms\\storeng\\drs\\fixedvarrecord.cpp", 2010, 0);
                    else
                      ex_raise(34, 68, 21, 1003);
                  }
                }
              }
            }
            RaiseInconsistencyError(*((_QWORD *)v26 + 1), 3);
            v121 = v26[14];
            v119 = *((_DWORD *)v26 + 5);
          }
          v124 = v119 + 2 * (v121 + 1);
          *((_DWORD *)v26 + 6) = v124;
          if ( v124 > 0x1F9E )
          {
            if ( byte_10316E8D7 || (qword_10317B120 & 1) != 0 )
            {
              v125 = *(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                               + SystemThread_TlsOffset
                               + 8LL);
              if ( v125 )
              {
                v126 = *(_QWORD *)(v125 + 96);
                if ( v126 )
                {
                  if ( *(_BYTE *)(v126 + 1177) )
                  {
                    if ( byte_10316E7C7 || (qword_10317B120 & 2) != 0 )
                      utassert_fail(1u, "false", "Sql\\Ntdbms\\storeng\\drs\\fixedvarrecord.cpp", 2017, 0);
                    else
                      ex_raise(34, 68, 21, 1004);
                  }
                }
              }
            }
            RaiseInconsistencyError(*((_QWORD *)v26 + 1), 4);
            v124 = *((_DWORD *)v26 + 6);
          }
          v127 = v120[(unsigned __int16)v26[14]] & 0x7FFF;
          *((_DWORD *)v26 + 1) = v127;
          if ( v124 > v127 )
          {
            if ( byte_10316E8D7 || (qword_10317B120 & 1) != 0 )
            {
              v128 = *(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                               + SystemThread_TlsOffset
                               + 8LL);
              if ( v128 )
              {
                v129 = *(_QWORD *)(v128 + 96);
                if ( v129 )
                {
                  if ( *(_BYTE *)(v129 + 1177) )
                  {
                    if ( byte_10316E7C7 || (qword_10317B120 & 2) != 0 )
                      utassert_fail(1u, "false", "Sql\\Ntdbms\\storeng\\drs\\fixedvarrecord.cpp", 2024, 0);
                    else
                      ex_raise(34, 68, 21, 1004);
                  }
                }
              }
            }
            RaiseInconsistencyError(*((_QWORD *)v26 + 1), 4);
          }
          while ( 1 )
          {
            v130 = (unsigned __int16)v26[14];
            if ( (v120[(unsigned int)(v130 - 1) + 1] & 0x8000u) == 0 )
            {
LABEL_340:
              v118 = (_BYTE *)*((_QWORD *)v26 + 1);
              goto LABEL_342;
            }
            v131 = *((_QWORD *)v26 + 1);
            v132 = v131 + *((unsigned int *)v26 + 5);
            if ( (_DWORD)v130 == 1 )
              break;
            v133 = *(_WORD *)(v132 + 2 * v130 - 2) & 0x7FFF;
            v134 = *(_WORD *)(v132 + 2 * v130) & 0x7FFF;
            if ( v133 >= *((_DWORD *)v26 + 6) )
              goto LABEL_330;
LABEL_331:
            RaiseInconsistencyError(*((_QWORD *)v26 + 1), 7);
            v131 = *((_QWORD *)v26 + 1);
            if ( v133 < *((_DWORD *)v26 + 6) )
              goto LABEL_374;
LABEL_332:
            if ( v133 > *((_DWORD *)v26 + 1) )
              goto LABEL_374;
            v135 = *(_WORD *)(v133 + v131);
            if ( v135 == 5 )
            {
              v26[1] |= 2u;
              --v26[14];
              v26[21] = v133;
              v136 = *((_QWORD *)v26 + 1) + (unsigned __int16)v133;
              v137 = v26[22] & 0xC7FF;
              if ( _bittest16((const signed __int16 *)(v136 + 2), 0xEu) )
                v137 |= *(_WORD *)(v136 + 2) & 0x3800;
              v26[22] = v137;
              v26[22] = v137 ^ (*(_WORD *)(v136 + 2) ^ v137) & 0x7FF;
              goto LABEL_340;
            }
            if ( v135 >= 0x400u )
            {
              v26[1] |= 1u;
              v101 = v26[14]-- == 1;
              if ( !v101 )
                continue;
            }
            goto LABEL_340;
          }
          v133 = *((_DWORD *)v26 + 6);
          v134 = *(_WORD *)(v132 + 2 * v130) & 0x7FFF;
LABEL_330:
          if ( v134 >= v133 )
            goto LABEL_332;
          goto LABEL_331;
        }
        *((_DWORD *)v26 + 1) = v115;
        v26[14] = 0;
        *((_DWORD *)v26 + 6) = v119;
LABEL_342:
        if ( (*v118 & 0x40) != 0 )
        {
          v138 = *((_DWORD *)v26 + 1);
          *(_DWORD *)(v26 + 19) = v138;
          *((_DWORD *)v26 + 1) = v138 + 14;
          v139 = FixedVarRecord::FindVersioningInfo((FixedVarRecord *)(v26 + 1));
          v140 = HIDWORD(*(_QWORD *)v139);
          v141 = HIWORD(*(_QWORD *)v139);
          v142 = 0;
          if ( (((__int16)v141 ^ ((unsigned int)(__int16)v141 >> 1)) & 0x2000) != 0 )
          {
            v143 = v141 & 0xDFFF;
            if ( (v141 & 0x4000) != 0 )
              v143 = v141 | 0x2000;
            LOWORD(v141) = v143;
          }
          if ( (_WORD)v141 == 0xFFFC )
            v142 = (unsigned __int16)v140 >> 5;
          *((_DWORD *)v26 + 1) += v142;
          v118 = (_BYTE *)*((_QWORD *)v26 + 1);
        }
        else
        {
          *(_DWORD *)(v26 + 19) = 0;
        }
        v144 = *(_QWORD *)(v26 + 15);
        v145 = *((_DWORD *)v26 + 1);
        if ( v144 && v144 < (unsigned __int64)&v118[*((unsigned int *)v26 + 1)] )
        {
          if ( byte_10316E8D7 || (qword_10317B120 & 1) != 0 )
          {
            v146 = *(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                             + SystemThread_TlsOffset
                             + 8LL);
            if ( v146 )
            {
              v147 = *(_QWORD *)(v146 + 96);
              if ( v147 )
              {
                if ( *(_BYTE *)(v147 + 1177) )
                {
                  if ( byte_10316E7C7 || (qword_10317B120 & 2) != 0 )
                    utassert_fail(1u, "false", "Sql\\Ntdbms\\storeng\\drs\\fixedvarrecord.cpp", 2114, 0);
                  else
                    ex_raise(34, 68, 21, 1018);
                }
              }
            }
          }
          RaiseInconsistencyError(*((_QWORD *)v26 + 1), 18);
          v145 = *((_DWORD *)v26 + 1);
        }
        if ( (unsigned int)(v145 - 1) > 0x3F3B )
        {
          if ( byte_10316E8D7 || (qword_10317B120 & 1) != 0 )
          {
            v148 = *(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                             + SystemThread_TlsOffset
                             + 8LL);
            if ( v148 )
            {
              v149 = *(_QWORD *)(v148 + 96);
              if ( v149 )
              {
                if ( *(_BYTE *)(v149 + 1177) )
                {
                  if ( byte_10316E7C7 || (qword_10317B120 & 2) != 0 )
                    utassert_fail(1u, "false", "Sql\\Ntdbms\\storeng\\drs\\fixedvarrecord.cpp", 2119, 0);
                  else
                    ex_raise(34, 68, 21, 1005);
                }
              }
            }
          }
          RaiseInconsistencyError(*((_QWORD *)v26 + 1), 5);
        }
      }
LABEL_374:
      v150 = *((_DWORD *)v26 + 1);
      if ( v150 >= 9 || (v151 = (_BYTE *)*((_QWORD *)v26 + 1), (v152 = *v151 & 0xE) != 0) && v152 != 12 )
      {
        v153 = *((_DWORD *)v26 + 1);
        v151 = (_BYTE *)*((_QWORD *)v26 + 1);
      }
      else
      {
        v153 = 9;
      }
      LODWORD(v665) = *((_DWORD *)v26 + 4);
      v662 = v26[1];
      v663 = v150;
      v667 = v26[14];
      HIDWORD(v665) = *((_DWORD *)v26 + 5);
      v666 = *((_DWORD *)v26 + 6);
      LODWORD(v669) = *(_DWORD *)(v26 + 19);
      memcpy_s(v672, 0x1F9Eu, v151, v153);
      v664 = v672;
      if ( (unsigned int)FixedVarRecord::HasSparseVector((FixedVarRecord *)&v662) )
      {
        v154 = v664;
        v155 = &v664[HIDWORD(v665)];
        v156 = *(unsigned __int16 *)v155 - 1;
        if ( (v662 & 1) == 0 )
          v156 = *(unsigned __int16 *)v155;
        if ( v156 == 1 )
          v157 = v666;
        else
          v157 = *(_WORD *)&v155[2 * v156 - 2] & 0x7FFF;
        v158 = *(_WORD *)&v155[2 * v156] & 0x7FFF;
        if ( v157 < v666 || v158 < v157 )
        {
          RaiseInconsistencyError(v664, 7);
          v154 = v664;
        }
        WORD2(v669) = v157;
        v159 = &v154[(unsigned __int16)v157];
        v160 = *((_WORD *)v159 + 1);
        if ( (v160 & 0x4000) != 0 )
          v161 = (v160 ^ WORD3(v669)) & 0x3800 ^ WORD3(v669);
        else
          v161 = WORD3(v669) & 0xC7FF;
        WORD3(v669) = v161;
        WORD3(v669) = v161 ^ (*((_WORD *)v159 + 1) ^ v161) & 0x7FF;
      }
    }
    BTreeRow::SaveCurrentPosition(v105);
    if ( *((char *)v105 + 16) >= 0 )
    {
      PageContext::ReleaseAccess(*((PageContext **)v105 + 3));
      *((_DWORD *)v105 + 4) |= 0x80u;
    }
    v550 = 1;
    v164 = (const struct PageRow *)&v661;
    v165 = &v662;
  }
  else
  {
LABEL_401:
    v164 = (BTreeRow *)((char *)v105 + 72);
    v165 = (__int16 *)((char *)v105 + 74);
  }
  v657 = 0;
  v658 = 0;
  v166 = *(_QWORD *)(*((_QWORD *)v105 + 31) + 24LL);
  v167 = v565;
  v168 = *((_QWORD *)v565 + 6);
  v169 = *(_BYTE *)(v168 + 7390);
  if ( *(_BYTE *)(v168 + 8272) && (*(_BYTE *)(v166 + 16) & 1) != 0 )
  {
    v170 = (*(unsigned int (__fastcall **)(struct XDES *))(*(_QWORD *)v565 + 240LL))(v565)
         ? *(_QWORD *)((*(__int64 (__fastcall **)(struct XDES *))(*(_QWORD *)v167 + 488LL))(v167) + 584)
         : *((_QWORD *)v167 + 73);
    if ( !*(_BYTE *)(v170 + 22) )
      ex_raise(39, 48, 16, 2);
  }
  PageRow::Clone((PageRow *)&v622, v164);
  v547 = 1;
  if ( !v113 )
  {
    if ( (byte_10317AD6E & 8) != 0
      || (v185 = *(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                           + SystemThread_TlsOffset)) != 0
      && (v186 = **(struct CSessionTraceFlags ***)(v185 + 56)) != 0
      && CSessionTraceFlags::CheckSessionTraceInternal(v186, 0xF73u) )
    {
      v171 = v167;
      v187 = *((_QWORD *)v167 + 26);
      if ( v187 )
        v188 = *(_QWORD *)(v187 + 64);
      else
        v188 = 0;
      v189 = *((_QWORD *)v167 + 82);
      v190 = *(unsigned __int16 *)(*((_QWORD *)v167 + 6) + 1720LL);
      v191 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v189 + 312LL))(v189);
      LogSystemMetadata(
        L"Page is current (dbid= %d rowsetid=%I64d) by xact (xactid=%I64d, xts=%I64d)\n",
        v190,
        *(_QWORD *)(v166 + 40),
        v191,
        v188);
    }
    else
    {
      v171 = v167;
    }
    goto LABEL_479;
  }
  v171 = v167;
  v172 = *((_QWORD *)v167 + 6);
  if ( *(_BYTE *)(v172 + 6872) )
    goto LABEL_1692;
  if ( *(_WORD *)v164 )
    CDRecord::GetVersionRecPtr(v165, v603);
  else
    FixedVarRecord::GetVersionRecPtr(v165, v603);
  if ( !VersionRecPtr::IsVersionPersisted((VersionRecPtr *)v603) )
  {
LABEL_1692:
    v173 = *(_QWORD *)(*(_QWORD *)(v172 + 1712) + 704LL);
    if ( (*(_WORD *)(v173 + 10) != 2 || (_DWORD)v605) && (unsigned int)v605 <= *(_DWORD *)v173 )
    {
      if ( (_DWORD)v605 != *(_DWORD *)v173
        || (v174 = *(_DWORD *)(v173 + 4), HIDWORD(v605) <= v174)
        && (HIDWORD(v605) != v174 || v557 <= *(_WORD *)(v173 + 8)) )
      {
        if ( !*(_BYTE *)(v172 + 8272) )
          goto LABEL_1693;
        if ( *(_WORD *)v164 )
          CDRecord::GetVersionRecPtr(v165, v604);
        else
          FixedVarRecord::GetVersionRecPtr(v165, v604);
        if ( !VersionRecPtr::IsVersionPersisted((VersionRecPtr *)v604) )
        {
LABEL_1693:
          if ( (byte_10317AD6E & 8) != 0
            || (v175 = *(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                                 + SystemThread_TlsOffset)) != 0
            && (v176 = **(struct CSessionTraceFlags ***)(v175 + 56)) != 0
            && CSessionTraceFlags::CheckSessionTraceInternal(v176, 0xF73u) )
          {
            v177 = *((_QWORD *)v171 + 26);
            if ( v177 )
              v178 = *(_QWORD *)(v177 + 64);
            else
              v178 = 0;
            v179 = *(unsigned __int16 *)(*((_QWORD *)v171 + 6) + 1720LL);
            v180 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)v171 + 82) + 312LL))(*((_QWORD *)v171 + 82));
            LogSystemMetadata(
              L"Before recovery version (dbid= %d rowsetid=%I64d) by xact (xactid=%I64d, xts=%I64d)\n",
              v179,
              *(_QWORD *)(v166 + 40),
              v180,
              v178);
          }
          goto LABEL_479;
        }
      }
    }
  }
  v181 = *v625;
  if ( v622 )
    v182 = v181 >> 1;
  else
    v182 = v181 >> 6;
  if ( (v182 & 1) == 0 )
    goto LABEL_479;
  if ( v622 )
    CDRecord::GetXdesTs(&v623, &v574);
  else
    FixedVarRecord::GetXdesTs(&v623, &v574);
  if ( !v575 && !v574 )
  {
LABEL_479:
    if ( (byte_10317AD6E & 8) != 0
      || (v192 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset,
          *(_QWORD *)v192)
      && (v193 = **(struct CSessionTraceFlags ***)(*(_QWORD *)v192 + 56LL)) != 0
      && CSessionTraceFlags::CheckSessionTraceInternal(v193, 0xF73u) )
    {
      CDStream::CDStream((CDStream *)v608);
      ProcessHeap = GetProcessHeap();
      v195 = (CTracePrintStream *)HeapAlloc(ProcessHeap, 0, 0x6C0u);
      *(_QWORD *)v606 = v195;
      if ( v195 )
        v196 = CTracePrintStream::CTracePrintStream(v195, 0);
      else
        v196 = 0;
      if ( v196 && !CDStream::AddDevice((CDStream *)v608, v196) )
        (**(void (__fastcall ***)(CTracePrintStream *, __int64))v196)(v196, 1);
      Record::Dump((Record *)&v622, (struct CDStream *)v608);
      CDStream::~CDStream((CDStream *)v608);
    }
    goto LABEL_490;
  }
  if ( !v166 || (*(_BYTE *)(v166 + 16) & 0x20) == 0 )
    goto LABEL_467;
  v183 = (*((_BYTE *)v171 + 536) & 4) != 0
       ? (*(__int64 (__fastcall **)(struct XDES *))(*(_QWORD *)v171 + 488LL))(v171) + 40
       : (__int64)v171 + 40;
  if ( v622 )
    CDRecord::GetXdesTs(&v623, &v576);
  else
    FixedVarRecord::GetXdesTs(&v623, &v576);
  if ( v577 != *(_WORD *)(v183 + 4) || v576 != *(_DWORD *)v183 )
    goto LABEL_467;
  if ( (v184 = *((_QWORD *)v171 + 26), v169)
    && (!v184
     || !*(_BYTE *)(v184 + 52)
     || !*(_QWORD *)(v184 + 64)
     || *(_QWORD *)(*(_QWORD *)v166 + 40LL) == _InterlockedCompareExchange64(
                                                 (volatile signed __int64 *)(v184 + 296),
                                                 0,
                                                 0))
    || (VersionMgr::GetVersionWithUpdateMarker(
          *((struct XVB **)v171 + 26),
          *(const struct UserInfo **)(v166 + 32),
          *(const struct DBTABLE **)(v168 + 1712),
          v673,
          0x1F9Eu,
          *(const struct UpdateSequenceMarker **)v166,
          (struct Record *)&v622,
          0,
          0,
          (struct VersionMgr::GetVersionResult *)&v547,
          0),
        v169) )
  {
    if ( v622 )
      CDRecord::GetVersionRecPtr(&v623, v600);
    else
      FixedVarRecord::GetVersionRecPtr(&v623, v600);
    if ( v622 )
      CDRecord::GetXdesTs(&v623, &v578);
    else
      FixedVarRecord::GetXdesTs(&v623, &v578);
    v567 = v578;
    v568 = v579;
    if ( (unsigned int)XdesMgr::GetRowAbortState(v168 + 6600, &v567, v600) )
    {
LABEL_467:
      if ( *(_WORD *)v164 == 1 )
        VersionMgr::GetVersionFromCompressed(
          v164,
          v673,
          0x1F9Eu,
          v171,
          (const struct VersionScanParams *)v166,
          (struct PageRow *)&v622,
          (struct VersionMgr::GetVersionResult *)&v547,
          1,
          0,
          0,
          (const struct LSN *)&v657,
          0);
      else
        VersionMgr::GetVersionLong(
          v673,
          0x1F9Eu,
          v171,
          (const struct VersionScanParams *)v166,
          (struct Record *)&v622,
          (struct VersionMgr::GetVersionResult *)&v547,
          1,
          0,
          0,
          (const struct LSN *)&v657,
          0,
          0);
    }
  }
LABEL_490:
  v197 = v537;
  if ( !v537 || v547 != 1 )
  {
    if ( (unsigned int)(v547 - 2) > 2 && v547 )
      utassert_fail(1u, "v.IsCopied() || !v.IsVisible()", "IndexRowScanner.cpp", 3160, 0);
    v199 = v622;
    v200 = v625;
    v201 = *v625;
    if ( v622 )
      v202 = v201 >> 1;
    else
      v202 = v201 >> 6;
    if ( (v202 & 1) != 0 )
    {
      if ( v622 )
        CDRecord::GetXdesTs(&v623, &v565);
      else
        FixedVarRecord::GetXdesTs(&v623, &v565);
      v199 = v622;
      v200 = v625;
    }
    v205 = 1;
    if ( v547 )
    {
      v203 = 0;
      if ( v199 )
      {
        LOBYTE(v203) = (((*v200 & 0x1C) - 4) & 0xFFFFFFE7) == 0;
      }
      else
      {
        v204 = *v200 & 0xE;
        v203 = v204 == 2 ? (v200[1] & 1) != 0 : ((v204 - 10) & 0xF9) == 0;
      }
      if ( !v203 )
        v205 = 0;
    }
    if ( v197 )
    {
      v209 = 0;
      v208 = 0;
      v536 = 0;
      if ( v205 )
        goto LABEL_547;
    }
    else if ( v205 )
    {
      if ( v548 )
      {
        if ( v547 )
        {
          v206 = IndexDataSetSession::ShortRecord_GetAntiMatterValue(v555, (const struct Record *)&v622);
          v199 = v622;
        }
        else
        {
          v206 = 0;
        }
        if ( v549 == 4 )
        {
          v207 = (unsigned __int8)v558;
          if ( !v206 )
            v207 = 1;
          v558 = v207;
        }
      }
      if ( !v547 )
        goto LABEL_545;
      if ( v199 )
        CDRecord::GetXdesTs(&v623, &v580);
      else
        FixedVarRecord::GetXdesTs(&v623, &v580);
      if ( v581 || v580 )
      {
        if ( v622 )
          CDRecord::GetVersionRecPtr(&v623, &v601);
        else
          FixedVarRecord::GetVersionRecPtr(&v623, &v601);
        v633 = v601;
        if ( v622 )
          CDRecord::GetXdesTs(&v623, &v582);
        else
          FixedVarRecord::GetXdesTs(&v623, &v582);
        v634 = v582;
        v635 = v583;
        v208 = 1;
        v536 = 1;
      }
      else
      {
LABEL_545:
        v208 = 0;
      }
      v209 = v558;
      goto LABEL_547;
    }
    v209 = 0;
    v208 = 0;
    v536 = 0;
    if ( v589 )
    {
      v210 = *(unsigned __int8 *)(v589 + 3);
      v536 = 0;
      if ( (_BYTE)v210 )
      {
        v211 = *((_QWORD *)v555 + 1);
        v536 = 0;
        v212 = v554;
        if ( !*(_BYTE *)(v211 + 1873) )
        {
          if ( (unsigned int)BTreeRow::AcquireKeyLockWithNoWait(v554, v210, &v622, v171, v555) )
            utassert_fail(1u, "retCode == LOCK_SUCCESS", "IndexRowScanner.cpp", 3275, 0);
          v536 = 0;
        }
LABEL_548:
        if ( !v550 )
        {
          BTreeRow::SaveCurrentPosition(v212);
          if ( *((char *)v212 + 16) >= 0 )
          {
            PageContext::ReleaseAccess(*((PageContext **)v212 + 3));
            *((_DWORD *)v212 + 4) |= 0x80u;
          }
        }
        v213 = (struct Record *)&v622;
        if ( !v547 )
          v213 = 0;
        v214 = v563;
        RowCountAdjustmentForLogicalRevert = GetRowCountAdjustmentForLogicalRevert(
                                               v213,
                                               v563,
                                               (const struct XdesTs *)&v593,
                                               v599);
        v216 = v537;
        if ( v537 )
        {
          if ( !v547 )
          {
            v217 = 0;
            v244 = 9;
            goto LABEL_657;
          }
          v217 = v624;
          if ( v622 )
          {
            if ( !v624 )
            {
              CDRecord::Resize((CDRecord *)&v623);
              v217 = v624;
            }
            if ( v217 >= 9 )
              goto LABEL_653;
            if ( (*v625 & 0x1C) != 0 )
            {
              v243 = (*v625 & 0x1C) == 12;
LABEL_651:
              if ( v243 )
                goto LABEL_652;
LABEL_653:
              v244 = 9;
LABEL_654:
              if ( v547 )
              {
                v245 = v625;
LABEL_658:
                v246 = v555;
                v247 = *(_DWORD *)(*((_QWORD *)v555 + 1) + 256LL);
                if ( v538 )
                {
                  v274 = v540;
                  if ( !v540 )
                  {
                    CDRecord::Resize((CDRecord *)&v539);
                    v274 = v540;
                    v246 = v555;
                  }
                  if ( v274 >= 9 || (*(_BYTE *)v541 & 0x1C) != 0 && (*(_BYTE *)v541 & 0x1C) != 0xC )
                    v244 = v274;
                }
                else
                {
                  v248 = v540;
                  if ( !v540 )
                  {
                    v539 = 0;
                    v248 = v542;
                    HIDWORD(v542) = v542;
                    if ( (*(_BYTE *)v541 & 0x10) != 0 )
                    {
                      v248 = (((unsigned int)*(unsigned __int16 *)((char *)v541 + (unsigned int)v542) + 7) >> 3)
                           + v542
                           + 2;
                      HIDWORD(v542) = v248;
                    }
                    if ( (*(_BYTE *)v541 & 0x20) != 0 )
                    {
                      v249 = (unsigned __int16 *)((char *)v541 + v248);
                      v250 = *v249;
                      v544 = v250;
                      if ( !v250 )
                      {
                        if ( byte_10316E8D7 || (qword_10317B120 & 1) != 0 )
                        {
                          v251 = *(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer
                                             + SystemThread_TlsIndex)
                                           + SystemThread_TlsOffset
                                           + 8LL);
                          if ( v251 )
                          {
                            v252 = *(_QWORD *)(v251 + 96);
                            if ( v252 )
                            {
                              if ( *(_BYTE *)(v252 + 1177) )
                              {
                                if ( byte_10316E7C7 || (qword_10317B120 & 2) != 0 )
                                  utassert_fail(1u, "false", "Sql\\Ntdbms\\storeng\\drs\\fixedvarrecord.cpp", 2010, 0);
                                else
                                  ex_raise(34, 68, 21, 1003);
                              }
                            }
                          }
                        }
                        RaiseInconsistencyError(v541, 3);
                        v250 = v544;
                      }
                      v253 = HIDWORD(v542) + 2 + 2 * v250;
                      v543 = v253;
                      if ( v253 > 0x1F9E )
                      {
                        if ( byte_10316E8D7 || (qword_10317B120 & 1) != 0 )
                        {
                          v254 = *(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer
                                             + SystemThread_TlsIndex)
                                           + SystemThread_TlsOffset
                                           + 8LL);
                          if ( v254 )
                          {
                            v255 = *(_QWORD *)(v254 + 96);
                            if ( v255 )
                            {
                              if ( *(_BYTE *)(v255 + 1177) )
                              {
                                if ( byte_10316E7C7 || (qword_10317B120 & 2) != 0 )
                                  utassert_fail(1u, "false", "Sql\\Ntdbms\\storeng\\drs\\fixedvarrecord.cpp", 2017, 0);
                                else
                                  ex_raise(34, 68, 21, 1004);
                              }
                            }
                          }
                        }
                        RaiseInconsistencyError(v541, 4);
                        v250 = v544;
                        v253 = v543;
                      }
                      v248 = v249[v250] & 0x7FFF;
                      v540 = v248;
                      if ( v253 > v248 )
                      {
                        if ( byte_10316E8D7 || (qword_10317B120 & 1) != 0 )
                        {
                          v256 = *(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer
                                             + SystemThread_TlsIndex)
                                           + SystemThread_TlsOffset
                                           + 8LL);
                          if ( v256 )
                          {
                            v257 = *(_QWORD *)(v256 + 96);
                            if ( v257 )
                            {
                              if ( *(_BYTE *)(v257 + 1177) )
                              {
                                if ( byte_10316E7C7 || (qword_10317B120 & 2) != 0 )
                                  utassert_fail(1u, "false", "Sql\\Ntdbms\\storeng\\drs\\fixedvarrecord.cpp", 2024, 0);
                                else
                                  ex_raise(34, 68, 21, 1004);
                              }
                            }
                          }
                        }
                        RaiseInconsistencyError(v541, 4);
                        v250 = v544;
                        v253 = v543;
                        v248 = v540;
                      }
                      while ( (v249[v250] & 0x8000u) != 0 )
                      {
                        v258 = (char *)v541 + HIDWORD(v542);
                        if ( v250 == 1 )
                          v259 = v253;
                        else
                          v259 = *(_WORD *)&v258[2 * v250 - 2] & 0x7FFF;
                        if ( v259 < v253 || (*(_WORD *)&v258[2 * v250] & 0x7FFFu) < v259 )
                        {
                          RaiseInconsistencyError(v541, 7);
                          v250 = v544;
                          v253 = v543;
                          v248 = v540;
                        }
                        if ( v259 < v253 || v259 > v248 )
                          goto LABEL_746;
                        v260 = *(_WORD *)((char *)v541 + v259);
                        if ( v260 == 5 )
                        {
                          v539 |= 2u;
                          v544 = v250 - 1;
                          WORD2(v546) = v259;
                          v261 = (char *)v541 + (unsigned __int16)v259;
                          v262 = *((_WORD *)v261 + 1);
                          if ( (v262 & 0x4000) != 0 )
                            v263 = (v262 ^ WORD3(v546)) & 0x3800 ^ WORD3(v546);
                          else
                            v263 = WORD3(v546) & 0xC7FF;
                          WORD3(v546) = v263;
                          WORD3(v546) = v263 ^ (*((_WORD *)v261 + 1) ^ v263) & 0x7FF;
                          break;
                        }
                        if ( v260 >= 0x400u )
                        {
                          v539 |= 1u;
                          v101 = v250-- == 1;
                          v544 = v250;
                          if ( !v101 )
                            continue;
                        }
                        break;
                      }
                    }
                    else
                    {
                      v540 = v248;
                      v544 = 0;
                      v543 = v248;
                    }
                    if ( (*(_BYTE *)v541 & 0x40) != 0 )
                    {
                      LODWORD(v546) = v248;
                      v540 = v248 + 14;
                      v264 = FixedVarRecord::FindVersioningInfo((FixedVarRecord *)&v539);
                      v265 = HIDWORD(*(_QWORD *)v264);
                      v266 = HIWORD(*(_QWORD *)v264);
                      v267 = 0;
                      if ( (((__int16)v266 ^ ((unsigned int)(__int16)v266 >> 1)) & 0x2000) != 0 )
                      {
                        v268 = v266 & 0xDFFF;
                        if ( (v266 & 0x4000) != 0 )
                          v268 = v266 | 0x2000;
                        LOWORD(v266) = v268;
                      }
                      if ( (_WORD)v266 == 0xFFFC )
                        v267 = (unsigned __int16)v265 >> 5;
                      v248 = v267 + v540;
                      v540 += v267;
                    }
                    else
                    {
                      LODWORD(v546) = 0;
                    }
                    if ( v545 && v545 < (unsigned __int64)v541 + v248 )
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
                                utassert_fail(1u, "false", "Sql\\Ntdbms\\storeng\\drs\\fixedvarrecord.cpp", 2114, 0);
                              else
                                ex_raise(34, 68, 21, 1018);
                            }
                          }
                        }
                      }
                      RaiseInconsistencyError(v541, 18);
                      v248 = v540;
                    }
                    if ( v248 - 1 > 0x3F3B )
                    {
                      if ( byte_10316E8D7 || (qword_10317B120 & 1) != 0 )
                      {
                        v271 = *(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                                         + SystemThread_TlsOffset
                                         + 8LL);
                        if ( v271 )
                        {
                          v272 = *(_QWORD *)(v271 + 96);
                          if ( v272 )
                          {
                            if ( *(_BYTE *)(v272 + 1177) )
                            {
                              if ( byte_10316E7C7 || (qword_10317B120 & 2) != 0 )
                                utassert_fail(1u, "false", "Sql\\Ntdbms\\storeng\\drs\\fixedvarrecord.cpp", 2119, 0);
                              else
                                ex_raise(34, 68, 21, 1005);
                            }
                          }
                        }
                      }
                      RaiseInconsistencyError(v541, 5);
                      v248 = v540;
                    }
LABEL_746:
                    v246 = v555;
                  }
                  if ( v248 >= 9 || (v273 = *(_BYTE *)v541 & 0xE) != 0 && v273 != 12 )
                    v244 = v248;
                }
                v275 = (*((unsigned int *)v246 + 5) | ((unsigned __int64)*((unsigned __int16 *)v246 + 12) << 32)) << 16;
                v276 = v541;
                if ( !(*(unsigned __int8 (__fastcall **)(XdesRMReadWrite *))(*(_QWORD *)v564 + 8LL))(v564) )
                  utassert_fail(1u, "IsDoOnlyLogicalRevertTransaction()", "XdesAM.cpp", 3879, 0);
                v277 = v275;
                v278 = v564;
                XdesRMReadWrite::PrepareDataSetSessionForReadWrite(v564, v277, 1, 1);
                v571 = v566;
                LOBYTE(v530) = v247 == 2;
                v279 = IndexDataSetSession::RevertData(
                         *((_QWORD *)v278 + 1101),
                         v245,
                         v217,
                         v276,
                         v244,
                         v530,
                         RowCountAdjustmentForLogicalRevert,
                         &v570,
                         CtrNestIdFromVersionRecPtr);
                v553 = v279;
                goto LABEL_1676;
              }
LABEL_657:
              v245 = 0;
              goto LABEL_658;
            }
          }
          else
          {
            if ( !v624 )
            {
              v623 = 0;
              v217 = v626;
              HIDWORD(v626) = v626;
              if ( (*v625 & 0x10) != 0 )
              {
                v217 = (((unsigned int)*(unsigned __int16 *)&v625[(unsigned int)v626] + 7) >> 3) + v626 + 2;
                HIDWORD(v626) = v217;
              }
              if ( (*v625 & 0x20) != 0 )
              {
                v218 = &v625[v217];
                v219 = *(_WORD *)v218;
                v628 = v219;
                if ( !v219 )
                {
                  if ( byte_10316E8D7 || (qword_10317B120 & 1) != 0 )
                  {
                    v220 = *(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                                     + SystemThread_TlsOffset
                                     + 8LL);
                    if ( v220 )
                    {
                      v221 = *(_QWORD *)(v220 + 96);
                      if ( v221 )
                      {
                        if ( *(_BYTE *)(v221 + 1177) )
                        {
                          if ( byte_10316E7C7 || (qword_10317B120 & 2) != 0 )
                            utassert_fail(1u, "false", "Sql\\Ntdbms\\storeng\\drs\\fixedvarrecord.cpp", 2010, 0);
                          else
                            ex_raise(34, 68, 21, 1003);
                        }
                      }
                    }
                  }
                  RaiseInconsistencyError(v625, 3);
                  v219 = v628;
                }
                v222 = HIDWORD(v626) + 2 + 2 * v219;
                v627 = v222;
                if ( v222 > 0x1F9E )
                {
                  if ( byte_10316E8D7 || (qword_10317B120 & 1) != 0 )
                  {
                    v223 = *(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                                     + SystemThread_TlsOffset
                                     + 8LL);
                    if ( v223 )
                    {
                      v224 = *(_QWORD *)(v223 + 96);
                      if ( v224 )
                      {
                        if ( *(_BYTE *)(v224 + 1177) )
                        {
                          if ( byte_10316E7C7 || (qword_10317B120 & 2) != 0 )
                            utassert_fail(1u, "false", "Sql\\Ntdbms\\storeng\\drs\\fixedvarrecord.cpp", 2017, 0);
                          else
                            ex_raise(34, 68, 21, 1004);
                        }
                      }
                    }
                  }
                  RaiseInconsistencyError(v625, 4);
                  v219 = v628;
                  v222 = v627;
                }
                v217 = *(_WORD *)&v218[2 * v219] & 0x7FFF;
                v624 = v217;
                if ( v222 > v217 )
                {
                  if ( byte_10316E8D7 || (qword_10317B120 & 1) != 0 )
                  {
                    v225 = *(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                                     + SystemThread_TlsOffset
                                     + 8LL);
                    if ( v225 )
                    {
                      v226 = *(_QWORD *)(v225 + 96);
                      if ( v226 )
                      {
                        if ( *(_BYTE *)(v226 + 1177) )
                        {
                          if ( byte_10316E7C7 || (qword_10317B120 & 2) != 0 )
                            utassert_fail(1u, "false", "Sql\\Ntdbms\\storeng\\drs\\fixedvarrecord.cpp", 2024, 0);
                          else
                            ex_raise(34, 68, 21, 1004);
                        }
                      }
                    }
                  }
                  RaiseInconsistencyError(v625, 4);
                  v219 = v628;
                  v222 = v627;
                  v217 = v624;
                }
                while ( *(__int16 *)&v218[2 * v219] < 0 )
                {
                  v227 = &v625[HIDWORD(v626)];
                  if ( v219 == 1 )
                    v228 = v222;
                  else
                    v228 = *(_WORD *)&v227[2 * v219 - 2] & 0x7FFF;
                  if ( v228 < v222 || (*(_WORD *)&v227[2 * v219] & 0x7FFFu) < v228 )
                  {
                    RaiseInconsistencyError(v625, 7);
                    v219 = v628;
                    v222 = v627;
                    v217 = v624;
                  }
                  if ( v228 < v222 || v228 > v217 )
                    goto LABEL_643;
                  v229 = *(_WORD *)&v625[v228];
                  if ( v229 == 5 )
                  {
                    v623 |= 2u;
                    v628 = v219 - 1;
                    WORD2(v630) = v228;
                    v230 = &v625[(unsigned __int16)v228];
                    v231 = *((_WORD *)v230 + 1);
                    if ( (v231 & 0x4000) != 0 )
                      v232 = (v231 ^ WORD3(v630)) & 0x3800 ^ WORD3(v630);
                    else
                      v232 = WORD3(v630) & 0xC7FF;
                    WORD3(v630) = v232;
                    WORD3(v630) = v232 ^ (*((_WORD *)v230 + 1) ^ v232) & 0x7FF;
                    break;
                  }
                  if ( v229 >= 0x400u )
                  {
                    v623 |= 1u;
                    v101 = v219-- == 1;
                    v628 = v219;
                    if ( !v101 )
                      continue;
                  }
                  break;
                }
              }
              else
              {
                v624 = v217;
                v628 = 0;
                v627 = v217;
              }
              if ( (*v625 & 0x40) != 0 )
              {
                LODWORD(v630) = v217;
                v624 = v217 + 14;
                v233 = FixedVarRecord::FindVersioningInfo((FixedVarRecord *)&v623);
                v234 = HIDWORD(*(_QWORD *)v233);
                v235 = HIWORD(*(_QWORD *)v233);
                v236 = 0;
                if ( (((__int16)v235 ^ ((unsigned int)(__int16)v235 >> 1)) & 0x2000) != 0 )
                {
                  v237 = v235 & 0xDFFF;
                  if ( (v235 & 0x4000) != 0 )
                    v237 = v235 | 0x2000;
                  LOWORD(v235) = v237;
                }
                if ( (_WORD)v235 == 0xFFFC )
                  v236 = (unsigned __int16)v234 >> 5;
                v217 = v236 + v624;
                v624 += v236;
              }
              else
              {
                LODWORD(v630) = 0;
              }
              if ( v629 && v629 < (unsigned __int64)&v625[v217] )
              {
                if ( byte_10316E8D7 || (qword_10317B120 & 1) != 0 )
                {
                  v238 = *(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                                   + SystemThread_TlsOffset
                                   + 8LL);
                  if ( v238 )
                  {
                    v239 = *(_QWORD *)(v238 + 96);
                    if ( v239 )
                    {
                      if ( *(_BYTE *)(v239 + 1177) )
                      {
                        if ( byte_10316E7C7 || (qword_10317B120 & 2) != 0 )
                          utassert_fail(1u, "false", "Sql\\Ntdbms\\storeng\\drs\\fixedvarrecord.cpp", 2114, 0);
                        else
                          ex_raise(34, 68, 21, 1018);
                      }
                    }
                  }
                }
                RaiseInconsistencyError(v625, 18);
                v217 = v624;
              }
              if ( v217 - 1 > 0x3F3B )
              {
                if ( byte_10316E8D7 || (qword_10317B120 & 1) != 0 )
                {
                  v240 = *(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                                   + SystemThread_TlsOffset
                                   + 8LL);
                  if ( v240 )
                  {
                    v241 = *(_QWORD *)(v240 + 96);
                    if ( v241 )
                    {
                      if ( *(_BYTE *)(v241 + 1177) )
                      {
                        if ( byte_10316E7C7 || (qword_10317B120 & 2) != 0 )
                          utassert_fail(1u, "false", "Sql\\Ntdbms\\storeng\\drs\\fixedvarrecord.cpp", 2119, 0);
                        else
                          ex_raise(34, 68, 21, 1005);
                      }
                    }
                  }
                }
                RaiseInconsistencyError(v625, 5);
                v217 = v624;
              }
            }
LABEL_643:
            if ( v217 >= 9 )
              goto LABEL_653;
            v242 = *v625 & 0xE;
            if ( v242 )
            {
              v243 = v242 == 12;
              goto LABEL_651;
            }
          }
LABEL_652:
          v244 = 9;
          v217 = 9;
          goto LABEL_654;
        }
        if ( v205 )
        {
          if ( !v209 )
          {
            if ( v214 )
            {
              if ( !v208 )
              {
                v280 = 0;
                v308 = 0;
                v307 = 9;
                goto LABEL_864;
              }
              v280 = v624;
              if ( v622 )
              {
                if ( !v624 )
                {
                  CDRecord::Resize((CDRecord *)&v623);
                  v280 = v624;
                }
                if ( v280 >= 9 )
                  goto LABEL_862;
                if ( (*v625 & 0x1C) != 0 )
                {
                  v306 = (*v625 & 0x1C) == 12;
LABEL_860:
                  if ( v306 )
                    goto LABEL_861;
LABEL_862:
                  v307 = 9;
                  v308 = v625;
                  goto LABEL_864;
                }
              }
              else
              {
                if ( !v624 )
                {
                  v623 = 0;
                  v280 = v626;
                  HIDWORD(v626) = v626;
                  if ( (*v625 & 0x10) != 0 )
                  {
                    v280 = (((unsigned int)*(unsigned __int16 *)&v625[(unsigned int)v626] + 7) >> 3) + v626 + 2;
                    HIDWORD(v626) = v280;
                  }
                  if ( (*v625 & 0x20) != 0 )
                  {
                    v281 = &v625[v280];
                    v282 = *(_WORD *)v281;
                    v628 = v282;
                    if ( !v282 )
                    {
                      if ( byte_10316E8D7 || (qword_10317B120 & 1) != 0 )
                      {
                        v283 = *(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                                         + SystemThread_TlsOffset
                                         + 8LL);
                        if ( v283 )
                        {
                          v284 = *(_QWORD *)(v283 + 96);
                          if ( v284 )
                          {
                            if ( *(_BYTE *)(v284 + 1177) )
                            {
                              if ( byte_10316E7C7 || (qword_10317B120 & 2) != 0 )
                                utassert_fail(1u, "false", "Sql\\Ntdbms\\storeng\\drs\\fixedvarrecord.cpp", 2010, 0);
                              else
                                ex_raise(34, 68, 21, 1003);
                            }
                          }
                        }
                      }
                      RaiseInconsistencyError(v625, 3);
                      v282 = v628;
                    }
                    v285 = HIDWORD(v626) + 2 + 2 * v282;
                    v627 = v285;
                    if ( v285 > 0x1F9E )
                    {
                      if ( byte_10316E8D7 || (qword_10317B120 & 1) != 0 )
                      {
                        v286 = *(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                                         + SystemThread_TlsOffset
                                         + 8LL);
                        if ( v286 )
                        {
                          v287 = *(_QWORD *)(v286 + 96);
                          if ( v287 )
                          {
                            if ( *(_BYTE *)(v287 + 1177) )
                            {
                              if ( byte_10316E7C7 || (qword_10317B120 & 2) != 0 )
                                utassert_fail(1u, "false", "Sql\\Ntdbms\\storeng\\drs\\fixedvarrecord.cpp", 2017, 0);
                              else
                                ex_raise(34, 68, 21, 1004);
                            }
                          }
                        }
                      }
                      RaiseInconsistencyError(v625, 4);
                      v282 = v628;
                      v285 = v627;
                    }
                    v280 = *(_WORD *)&v281[2 * v282] & 0x7FFF;
                    v624 = v280;
                    if ( v285 > v280 )
                    {
                      if ( byte_10316E8D7 || (qword_10317B120 & 1) != 0 )
                      {
                        v288 = *(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                                         + SystemThread_TlsOffset
                                         + 8LL);
                        if ( v288 )
                        {
                          v289 = *(_QWORD *)(v288 + 96);
                          if ( v289 )
                          {
                            if ( *(_BYTE *)(v289 + 1177) )
                            {
                              if ( byte_10316E7C7 || (qword_10317B120 & 2) != 0 )
                                utassert_fail(1u, "false", "Sql\\Ntdbms\\storeng\\drs\\fixedvarrecord.cpp", 2024, 0);
                              else
                                ex_raise(34, 68, 21, 1004);
                            }
                          }
                        }
                      }
                      RaiseInconsistencyError(v625, 4);
                      v282 = v628;
                      v285 = v627;
                      v280 = v624;
                    }
                    while ( *(__int16 *)&v281[2 * v282] < 0 )
                    {
                      v290 = &v625[HIDWORD(v626)];
                      if ( v282 == 1 )
                        v291 = v285;
                      else
                        v291 = *(_WORD *)&v290[2 * v282 - 2] & 0x7FFF;
                      if ( v291 < v285 || (*(_WORD *)&v290[2 * v282] & 0x7FFFu) < v291 )
                      {
                        RaiseInconsistencyError(v625, 7);
                        v282 = v628;
                        v285 = v627;
                        v280 = v624;
                      }
                      if ( v291 < v285 || v291 > v280 )
                        goto LABEL_852;
                      v292 = *(_WORD *)&v625[v291];
                      if ( v292 == 5 )
                      {
                        v623 |= 2u;
                        v628 = v282 - 1;
                        WORD2(v630) = v291;
                        v293 = &v625[(unsigned __int16)v291];
                        v294 = *((_WORD *)v293 + 1);
                        if ( (v294 & 0x4000) != 0 )
                          v295 = (v294 ^ WORD3(v630)) & 0x3800 ^ WORD3(v630);
                        else
                          v295 = WORD3(v630) & 0xC7FF;
                        WORD3(v630) = v295;
                        WORD3(v630) = v295 ^ (*((_WORD *)v293 + 1) ^ v295) & 0x7FF;
                        break;
                      }
                      if ( v292 >= 0x400u )
                      {
                        v623 |= 1u;
                        v101 = v282-- == 1;
                        v628 = v282;
                        if ( !v101 )
                          continue;
                      }
                      break;
                    }
                  }
                  else
                  {
                    v624 = v280;
                    v628 = 0;
                    v627 = v280;
                  }
                  if ( (*v625 & 0x40) != 0 )
                  {
                    LODWORD(v630) = v280;
                    v624 = v280 + 14;
                    v296 = FixedVarRecord::FindVersioningInfo((FixedVarRecord *)&v623);
                    v297 = HIDWORD(*(_QWORD *)v296);
                    v298 = HIWORD(*(_QWORD *)v296);
                    v299 = 0;
                    if ( (((__int16)v298 ^ ((unsigned int)(__int16)v298 >> 1)) & 0x2000) != 0 )
                    {
                      v300 = v298 & 0xDFFF;
                      if ( (v298 & 0x4000) != 0 )
                        v300 = v298 | 0x2000;
                      LOWORD(v298) = v300;
                    }
                    if ( (_WORD)v298 == 0xFFFC )
                      v299 = (unsigned __int16)v297 >> 5;
                    v280 = v299 + v624;
                    v624 += v299;
                  }
                  else
                  {
                    LODWORD(v630) = 0;
                  }
                  if ( v629 && v629 < (unsigned __int64)&v625[v280] )
                  {
                    if ( byte_10316E8D7 || (qword_10317B120 & 1) != 0 )
                    {
                      v301 = *(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                                       + SystemThread_TlsOffset
                                       + 8LL);
                      if ( v301 )
                      {
                        v302 = *(_QWORD *)(v301 + 96);
                        if ( v302 )
                        {
                          if ( *(_BYTE *)(v302 + 1177) )
                          {
                            if ( byte_10316E7C7 || (qword_10317B120 & 2) != 0 )
                              utassert_fail(1u, "false", "Sql\\Ntdbms\\storeng\\drs\\fixedvarrecord.cpp", 2114, 0);
                            else
                              ex_raise(34, 68, 21, 1018);
                          }
                        }
                      }
                    }
                    RaiseInconsistencyError(v625, 18);
                    v280 = v624;
                  }
                  if ( v280 - 1 > 0x3F3B )
                  {
                    if ( byte_10316E8D7 || (qword_10317B120 & 1) != 0 )
                    {
                      v303 = *(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                                       + SystemThread_TlsOffset
                                       + 8LL);
                      if ( v303 )
                      {
                        v304 = *(_QWORD *)(v303 + 96);
                        if ( v304 )
                        {
                          if ( *(_BYTE *)(v304 + 1177) )
                          {
                            if ( byte_10316E7C7 || (qword_10317B120 & 2) != 0 )
                              utassert_fail(1u, "false", "Sql\\Ntdbms\\storeng\\drs\\fixedvarrecord.cpp", 2119, 0);
                            else
                              ex_raise(34, 68, 21, 1005);
                          }
                        }
                      }
                    }
                    RaiseInconsistencyError(v625, 5);
                    v280 = v624;
                  }
                }
LABEL_852:
                if ( v280 >= 9 )
                  goto LABEL_862;
                v305 = *v625 & 0xE;
                if ( v305 )
                {
                  v306 = v305 == 12;
                  goto LABEL_860;
                }
              }
LABEL_861:
              v307 = 9;
              v280 = 9;
              v308 = v625;
LABEL_864:
              if ( v538 )
              {
                v335 = v540;
                if ( !v540 )
                {
                  CDRecord::Resize((CDRecord *)&v539);
                  v335 = v540;
                }
                if ( v335 >= 9 || (*(_BYTE *)v541 & 0x1C) != 0 && (*(_BYTE *)v541 & 0x1C) != 0xC )
                  v307 = v335;
              }
              else
              {
                v309 = v540;
                if ( !v540 )
                {
                  v539 = 0;
                  v309 = v542;
                  HIDWORD(v542) = v542;
                  if ( (*(_BYTE *)v541 & 0x10) != 0 )
                  {
                    v309 = (((unsigned int)*(unsigned __int16 *)((char *)v541 + (unsigned int)v542) + 7) >> 3)
                         + v542
                         + 2;
                    HIDWORD(v542) = v309;
                  }
                  if ( (*(_BYTE *)v541 & 0x20) != 0 )
                  {
                    v310 = (unsigned __int16 *)((char *)v541 + v309);
                    v311 = *v310;
                    v544 = v311;
                    if ( !v311 )
                    {
                      if ( byte_10316E8D7 || (qword_10317B120 & 1) != 0 )
                      {
                        v312 = *(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                                         + SystemThread_TlsOffset
                                         + 8LL);
                        if ( v312 )
                        {
                          v313 = *(_QWORD *)(v312 + 96);
                          if ( v313 )
                          {
                            if ( *(_BYTE *)(v313 + 1177) )
                            {
                              if ( byte_10316E7C7 || (qword_10317B120 & 2) != 0 )
                                utassert_fail(1u, "false", "Sql\\Ntdbms\\storeng\\drs\\fixedvarrecord.cpp", 2010, 0);
                              else
                                ex_raise(34, 68, 21, 1003);
                            }
                          }
                        }
                      }
                      RaiseInconsistencyError(v541, 3);
                      v311 = v544;
                    }
                    v314 = HIDWORD(v542) + 2 + 2 * v311;
                    v543 = v314;
                    if ( v314 > 0x1F9E )
                    {
                      if ( byte_10316E8D7 || (qword_10317B120 & 1) != 0 )
                      {
                        v315 = *(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                                         + SystemThread_TlsOffset
                                         + 8LL);
                        if ( v315 )
                        {
                          v316 = *(_QWORD *)(v315 + 96);
                          if ( v316 )
                          {
                            if ( *(_BYTE *)(v316 + 1177) )
                            {
                              if ( byte_10316E7C7 || (qword_10317B120 & 2) != 0 )
                                utassert_fail(1u, "false", "Sql\\Ntdbms\\storeng\\drs\\fixedvarrecord.cpp", 2017, 0);
                              else
                                ex_raise(34, 68, 21, 1004);
                            }
                          }
                        }
                      }
                      RaiseInconsistencyError(v541, 4);
                      v311 = v544;
                      v314 = v543;
                    }
                    v309 = v310[v311] & 0x7FFF;
                    v540 = v309;
                    if ( v314 > v309 )
                    {
                      if ( byte_10316E8D7 || (qword_10317B120 & 1) != 0 )
                      {
                        v317 = *(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                                         + SystemThread_TlsOffset
                                         + 8LL);
                        if ( v317 )
                        {
                          v318 = *(_QWORD *)(v317 + 96);
                          if ( v318 )
                          {
                            if ( *(_BYTE *)(v318 + 1177) )
                            {
                              if ( byte_10316E7C7 || (qword_10317B120 & 2) != 0 )
                                utassert_fail(1u, "false", "Sql\\Ntdbms\\storeng\\drs\\fixedvarrecord.cpp", 2024, 0);
                              else
                                ex_raise(34, 68, 21, 1004);
                            }
                          }
                        }
                      }
                      RaiseInconsistencyError(v541, 4);
                      v311 = v544;
                      v314 = v543;
                      v309 = v540;
                    }
                    while ( (v310[v311] & 0x8000u) != 0 )
                    {
                      v319 = (char *)v541 + HIDWORD(v542);
                      if ( v311 == 1 )
                        v320 = v314;
                      else
                        v320 = *(_WORD *)&v319[2 * v311 - 2] & 0x7FFF;
                      if ( v320 < v314 || (*(_WORD *)&v319[2 * v311] & 0x7FFFu) < v320 )
                      {
                        RaiseInconsistencyError(v541, 7);
                        v311 = v544;
                        v314 = v543;
                        v309 = v540;
                      }
                      if ( v320 < v314 || v320 > v309 )
                        goto LABEL_952;
                      v321 = *(_WORD *)((char *)v541 + v320);
                      if ( v321 == 5 )
                      {
                        v539 |= 2u;
                        v544 = v311 - 1;
                        WORD2(v546) = v320;
                        v322 = (char *)v541 + (unsigned __int16)v320;
                        v323 = *((_WORD *)v322 + 1);
                        if ( (v323 & 0x4000) != 0 )
                          v324 = (v323 ^ WORD3(v546)) & 0x3800 ^ WORD3(v546);
                        else
                          v324 = WORD3(v546) & 0xC7FF;
                        WORD3(v546) = v324;
                        WORD3(v546) = v324 ^ (*((_WORD *)v322 + 1) ^ v324) & 0x7FF;
                        break;
                      }
                      if ( v321 >= 0x400u )
                      {
                        v539 |= 1u;
                        v101 = v311-- == 1;
                        v544 = v311;
                        if ( !v101 )
                          continue;
                      }
                      break;
                    }
                  }
                  else
                  {
                    v540 = v309;
                    v544 = 0;
                    v543 = v309;
                  }
                  if ( (*(_BYTE *)v541 & 0x40) != 0 )
                  {
                    LODWORD(v546) = v309;
                    v540 = v309 + 14;
                    v325 = FixedVarRecord::FindVersioningInfo((FixedVarRecord *)&v539);
                    v326 = HIDWORD(*(_QWORD *)v325);
                    v327 = HIWORD(*(_QWORD *)v325);
                    v328 = 0;
                    if ( (((__int16)v327 ^ ((unsigned int)(__int16)v327 >> 1)) & 0x2000) != 0 )
                    {
                      v329 = v327 & 0xDFFF;
                      if ( (v327 & 0x4000) != 0 )
                        v329 = v327 | 0x2000;
                      LOWORD(v327) = v329;
                    }
                    if ( (_WORD)v327 == 0xFFFC )
                      v328 = (unsigned __int16)v326 >> 5;
                    v309 = v328 + v540;
                    v540 += v328;
                  }
                  else
                  {
                    LODWORD(v546) = 0;
                  }
                  if ( v545 && v545 < (unsigned __int64)v541 + v309 )
                  {
                    if ( byte_10316E8D7 || (qword_10317B120 & 1) != 0 )
                    {
                      v330 = *(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                                       + SystemThread_TlsOffset
                                       + 8LL);
                      if ( v330 )
                      {
                        v331 = *(_QWORD *)(v330 + 96);
                        if ( v331 )
                        {
                          if ( *(_BYTE *)(v331 + 1177) )
                          {
                            if ( byte_10316E7C7 || (qword_10317B120 & 2) != 0 )
                              utassert_fail(1u, "false", "Sql\\Ntdbms\\storeng\\drs\\fixedvarrecord.cpp", 2114, 0);
                            else
                              ex_raise(34, 68, 21, 1018);
                          }
                        }
                      }
                    }
                    RaiseInconsistencyError(v541, 18);
                    v309 = v540;
                  }
                  if ( v309 - 1 > 0x3F3B )
                  {
                    if ( byte_10316E8D7 || (qword_10317B120 & 1) != 0 )
                    {
                      v332 = *(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                                       + SystemThread_TlsOffset
                                       + 8LL);
                      if ( v332 )
                      {
                        v333 = *(_QWORD *)(v332 + 96);
                        if ( v333 )
                        {
                          if ( *(_BYTE *)(v333 + 1177) )
                          {
                            if ( byte_10316E7C7 || (qword_10317B120 & 2) != 0 )
                              utassert_fail(1u, "false", "Sql\\Ntdbms\\storeng\\drs\\fixedvarrecord.cpp", 2119, 0);
                            else
                              ex_raise(34, 68, 21, 1005);
                          }
                        }
                      }
                    }
                    RaiseInconsistencyError(v541, 5);
                    v309 = v540;
                  }
                }
LABEL_952:
                if ( v309 >= 9 || (v334 = *(_BYTE *)v541 & 0xE) != 0 && v334 != 12 )
                  v307 = v309;
              }
              v336 = v541;
              v337 = v564;
              XdesRMReadWrite::PrepareDataSetSessionForReadWrite(
                v564,
                (*((unsigned int *)v555 + 5) | ((unsigned __int64)*((unsigned __int16 *)v555 + 12) << 32)) << 16,
                1,
                1);
              LOBYTE(v533) = 0;
LABEL_963:
              v338 = &v633;
              if ( !v536 )
                v338 = 0;
              LOBYTE(v532) = v214;
              v279 = IndexDataSetSession::DeleteRowByLogicalRevert(
                       *((_QWORD *)v337 + 1101),
                       v336,
                       v307,
                       v338,
                       0,
                       v308,
                       v280,
                       v532,
                       v533);
              v553 = v279;
              goto LABEL_1676;
            }
            if ( !v208 )
            {
              v280 = 0;
              v308 = 0;
              v307 = 9;
              goto LABEL_1370;
            }
            v280 = v624;
            if ( v622 )
            {
              if ( !v624 )
              {
                CDRecord::Resize((CDRecord *)&v623);
                v280 = v624;
              }
              if ( v280 >= 9 )
                goto LABEL_1368;
              if ( (*v625 & 0x1C) != 0 )
              {
                v445 = (*v625 & 0x1C) == 12;
LABEL_1366:
                if ( v445 )
                  goto LABEL_1367;
LABEL_1368:
                v307 = 9;
                v308 = v625;
                goto LABEL_1370;
              }
            }
            else
            {
              if ( !v624 )
              {
                v623 = 0;
                v280 = v626;
                HIDWORD(v626) = v626;
                if ( (*v625 & 0x10) != 0 )
                {
                  v280 = (((unsigned int)*(unsigned __int16 *)&v625[(unsigned int)v626] + 7) >> 3) + v626 + 2;
                  HIDWORD(v626) = v280;
                }
                if ( (*v625 & 0x20) != 0 )
                {
                  v422 = &v625[v280];
                  v423 = *(_WORD *)v422;
                  v628 = v423;
                  if ( !v423 )
                  {
                    if ( byte_10316E8D7 || (qword_10317B120 & 1) != 0 )
                    {
                      v424 = *(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                                       + SystemThread_TlsOffset
                                       + 8LL);
                      if ( v424 )
                      {
                        v425 = *(_QWORD *)(v424 + 96);
                        if ( v425 )
                        {
                          if ( *(_BYTE *)(v425 + 1177) )
                          {
                            if ( byte_10316E7C7 || (qword_10317B120 & 2) != 0 )
                              utassert_fail(1u, "false", "Sql\\Ntdbms\\storeng\\drs\\fixedvarrecord.cpp", 2010, 0);
                            else
                              ex_raise(34, 68, 21, 1003);
                          }
                        }
                      }
                    }
                    RaiseInconsistencyError(v625, 3);
                    v423 = v628;
                  }
                  v426 = HIDWORD(v626) + 2 + 2 * v423;
                  v627 = v426;
                  if ( v426 > 0x1F9E )
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
                              utassert_fail(1u, "false", "Sql\\Ntdbms\\storeng\\drs\\fixedvarrecord.cpp", 2017, 0);
                            else
                              ex_raise(34, 68, 21, 1004);
                          }
                        }
                      }
                    }
                    RaiseInconsistencyError(v625, 4);
                    v423 = v628;
                    v426 = v627;
                  }
                  v280 = *(_WORD *)&v422[2 * v423] & 0x7FFF;
                  v624 = v280;
                  if ( v426 > v280 )
                  {
                    if ( byte_10316E8D7 || (qword_10317B120 & 1) != 0 )
                    {
                      v429 = *(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                                       + SystemThread_TlsOffset
                                       + 8LL);
                      if ( v429 )
                      {
                        v430 = *(_QWORD *)(v429 + 96);
                        if ( v430 )
                        {
                          if ( *(_BYTE *)(v430 + 1177) )
                          {
                            if ( byte_10316E7C7 || (qword_10317B120 & 2) != 0 )
                              utassert_fail(1u, "false", "Sql\\Ntdbms\\storeng\\drs\\fixedvarrecord.cpp", 2024, 0);
                            else
                              ex_raise(34, 68, 21, 1004);
                          }
                        }
                      }
                    }
                    RaiseInconsistencyError(v625, 4);
                    v423 = v628;
                    v426 = v627;
                    v280 = v624;
                  }
                  while ( *(__int16 *)&v422[2 * v423] < 0 )
                  {
                    v431 = &v625[HIDWORD(v626)];
                    if ( v423 == 1 )
                      v432 = v426;
                    else
                      v432 = *(_WORD *)&v431[2 * v423 - 2] & 0x7FFF;
                    if ( v432 < v426 || (*(_WORD *)&v431[2 * v423] & 0x7FFFu) < v432 )
                    {
                      RaiseInconsistencyError(v625, 7);
                      v423 = v628;
                      v426 = v627;
                      v280 = v624;
                    }
                    if ( v432 < v426 || v432 > v280 )
                      goto LABEL_1358;
                    v433 = *(_WORD *)&v625[v432];
                    if ( v433 == 5 )
                    {
                      v623 |= 2u;
                      v628 = v423 - 1;
                      WORD2(v630) = v432;
                      v434 = &v625[(unsigned __int16)v432];
                      v435 = *((_WORD *)v434 + 1);
                      if ( (v435 & 0x4000) != 0 )
                        v436 = (v435 ^ WORD3(v630)) & 0x3800 ^ WORD3(v630);
                      else
                        v436 = WORD3(v630) & 0xC7FF;
                      WORD3(v630) = v436;
                      WORD3(v630) = v436 ^ (*((_WORD *)v434 + 1) ^ v436) & 0x7FF;
                      break;
                    }
                    if ( v433 >= 0x400u )
                    {
                      v623 |= 1u;
                      v101 = v423-- == 1;
                      v628 = v423;
                      if ( !v101 )
                        continue;
                    }
                    break;
                  }
                }
                else
                {
                  v624 = v280;
                  v628 = 0;
                  v627 = v280;
                }
                if ( (*v625 & 0x40) != 0 )
                {
                  LODWORD(v630) = v280;
                  v624 = v280 + 14;
                  v437 = FixedVarRecord::FindVersioningInfo((FixedVarRecord *)&v623);
                  v438 = HIWORD(*(_QWORD *)v437);
                  v439 = 0;
                  if ( (((__int16)v438 ^ ((unsigned int)(__int16)v438 >> 1)) & 0x2000) != 0 )
                  {
                    if ( (v438 & 0x4000) != 0 )
                      LOWORD(v438) = v438 | 0x2000;
                    else
                      LOWORD(v438) = v438 & 0xDFFF;
                  }
                  if ( (_WORD)v438 == 0xFFFC )
                    v439 = (unsigned __int16)WORD2(*(_QWORD *)v437) >> 5;
                  v280 = v439 + v624;
                  v624 += v439;
                }
                else
                {
                  LODWORD(v630) = 0;
                }
                if ( v629 && v629 < (unsigned __int64)&v625[v280] )
                {
                  if ( byte_10316E8D7 || (qword_10317B120 & 1) != 0 )
                  {
                    v440 = *(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                                     + SystemThread_TlsOffset
                                     + 8LL);
                    if ( v440 )
                    {
                      v441 = *(_QWORD *)(v440 + 96);
                      if ( v441 )
                      {
                        if ( *(_BYTE *)(v441 + 1177) )
                        {
                          if ( byte_10316E7C7 || (qword_10317B120 & 2) != 0 )
                            utassert_fail(1u, "false", "Sql\\Ntdbms\\storeng\\drs\\fixedvarrecord.cpp", 2114, 0);
                          else
                            ex_raise(34, 68, 21, 1018);
                        }
                      }
                    }
                  }
                  RaiseInconsistencyError(v625, 18);
                  v280 = v624;
                }
                if ( v280 - 1 > 0x3F3B )
                {
                  if ( byte_10316E8D7 || (qword_10317B120 & 1) != 0 )
                  {
                    v442 = *(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                                     + SystemThread_TlsOffset
                                     + 8LL);
                    if ( v442 )
                    {
                      v443 = *(_QWORD *)(v442 + 96);
                      if ( v443 )
                      {
                        if ( *(_BYTE *)(v443 + 1177) )
                        {
                          if ( byte_10316E7C7 || (qword_10317B120 & 2) != 0 )
                            utassert_fail(1u, "false", "Sql\\Ntdbms\\storeng\\drs\\fixedvarrecord.cpp", 2119, 0);
                          else
                            ex_raise(34, 68, 21, 1005);
                        }
                      }
                    }
                  }
                  RaiseInconsistencyError(v625, 5);
                  v280 = v624;
                }
              }
LABEL_1358:
              if ( v280 >= 9 )
                goto LABEL_1368;
              v444 = *v625 & 0xE;
              if ( v444 )
              {
                v445 = v444 == 12;
                goto LABEL_1366;
              }
            }
LABEL_1367:
            v307 = 9;
            v280 = 9;
            v308 = v625;
LABEL_1370:
            if ( v538 )
            {
              v470 = v540;
              if ( !v540 )
              {
                CDRecord::Resize((CDRecord *)&v539);
                v470 = v540;
              }
              if ( v470 >= 9 || (*(_BYTE *)v541 & 0x1C) != 0 && (*(_BYTE *)v541 & 0x1C) != 0xC )
                v307 = v470;
            }
            else
            {
              v446 = v540;
              if ( !v540 )
              {
                v539 = 0;
                v446 = v542;
                HIDWORD(v542) = v542;
                if ( (*(_BYTE *)v541 & 0x10) != 0 )
                {
                  v446 = (((unsigned int)*(unsigned __int16 *)((char *)v541 + (unsigned int)v542) + 7) >> 3) + v542 + 2;
                  HIDWORD(v542) = v446;
                }
                if ( (*(_BYTE *)v541 & 0x20) != 0 )
                {
                  v447 = (unsigned __int16 *)((char *)v541 + v446);
                  v448 = *v447;
                  v544 = v448;
                  if ( !v448 )
                  {
                    if ( byte_10316E8D7 || (qword_10317B120 & 1) != 0 )
                    {
                      v449 = *(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                                       + SystemThread_TlsOffset
                                       + 8LL);
                      if ( v449 )
                      {
                        v450 = *(_QWORD *)(v449 + 96);
                        if ( v450 )
                        {
                          if ( *(_BYTE *)(v450 + 1177) )
                          {
                            if ( byte_10316E7C7 || (qword_10317B120 & 2) != 0 )
                              utassert_fail(1u, "false", "Sql\\Ntdbms\\storeng\\drs\\fixedvarrecord.cpp", 2010, 0);
                            else
                              ex_raise(34, 68, 21, 1003);
                          }
                        }
                      }
                    }
                    RaiseInconsistencyError(v541, 3);
                    v448 = v544;
                  }
                  v451 = HIDWORD(v542) + 2 + 2 * v448;
                  v543 = v451;
                  if ( v451 > 0x1F9E )
                  {
                    if ( byte_10316E8D7 || (qword_10317B120 & 1) != 0 )
                    {
                      v452 = *(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                                       + SystemThread_TlsOffset
                                       + 8LL);
                      if ( v452 )
                      {
                        v453 = *(_QWORD *)(v452 + 96);
                        if ( v453 )
                        {
                          if ( *(_BYTE *)(v453 + 1177) )
                          {
                            if ( byte_10316E7C7 || (qword_10317B120 & 2) != 0 )
                              utassert_fail(1u, "false", "Sql\\Ntdbms\\storeng\\drs\\fixedvarrecord.cpp", 2017, 0);
                            else
                              ex_raise(34, 68, 21, 1004);
                          }
                        }
                      }
                    }
                    RaiseInconsistencyError(v541, 4);
                    v448 = v544;
                    v451 = v543;
                  }
                  v446 = v447[v448] & 0x7FFF;
                  v540 = v446;
                  if ( v451 > v446 )
                  {
                    if ( byte_10316E8D7 || (qword_10317B120 & 1) != 0 )
                    {
                      v454 = *(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                                       + SystemThread_TlsOffset
                                       + 8LL);
                      if ( v454 )
                      {
                        v455 = *(_QWORD *)(v454 + 96);
                        if ( v455 )
                        {
                          if ( *(_BYTE *)(v455 + 1177) )
                          {
                            if ( byte_10316E7C7 || (qword_10317B120 & 2) != 0 )
                              utassert_fail(1u, "false", "Sql\\Ntdbms\\storeng\\drs\\fixedvarrecord.cpp", 2024, 0);
                            else
                              ex_raise(34, 68, 21, 1004);
                          }
                        }
                      }
                    }
                    RaiseInconsistencyError(v541, 4);
                    v448 = v544;
                    v451 = v543;
                    v446 = v540;
                  }
                  while ( (v447[v448] & 0x8000u) != 0 )
                  {
                    v456 = (char *)v541 + HIDWORD(v542);
                    if ( v448 == 1 )
                      v457 = v451;
                    else
                      v457 = *(_WORD *)&v456[2 * v448 - 2] & 0x7FFF;
                    if ( v457 < v451 || (*(_WORD *)&v456[2 * v448] & 0x7FFFu) < v457 )
                    {
                      RaiseInconsistencyError(v541, 7);
                      v448 = v544;
                      v451 = v543;
                      v446 = v540;
                    }
                    if ( v457 < v451 || v457 > v446 )
                      goto LABEL_1458;
                    v458 = *(_WORD *)((char *)v541 + v457);
                    if ( v458 == 5 )
                    {
                      v539 |= 2u;
                      v544 = v448 - 1;
                      WORD2(v546) = v457;
                      v459 = (char *)v541 + (unsigned __int16)v457;
                      v460 = *((_WORD *)v459 + 1);
                      if ( (v460 & 0x4000) != 0 )
                        v461 = (v460 ^ WORD3(v546)) & 0x3800 ^ WORD3(v546);
                      else
                        v461 = WORD3(v546) & 0xC7FF;
                      WORD3(v546) = v461;
                      WORD3(v546) = v461 ^ (*((_WORD *)v459 + 1) ^ v461) & 0x7FF;
                      break;
                    }
                    if ( v458 >= 0x400u )
                    {
                      v539 |= 1u;
                      v101 = v448-- == 1;
                      v544 = v448;
                      if ( !v101 )
                        continue;
                    }
                    break;
                  }
                }
                else
                {
                  v540 = v446;
                  v544 = 0;
                  v543 = v446;
                }
                if ( (*(_BYTE *)v541 & 0x40) != 0 )
                {
                  LODWORD(v546) = v446;
                  v540 = v446 + 14;
                  v462 = FixedVarRecord::FindVersioningInfo((FixedVarRecord *)&v539);
                  v463 = HIWORD(*(_QWORD *)v462);
                  v464 = 0;
                  if ( (((__int16)v463 ^ ((unsigned int)(__int16)v463 >> 1)) & 0x2000) != 0 )
                  {
                    if ( (v463 & 0x4000) != 0 )
                      LOWORD(v463) = v463 | 0x2000;
                    else
                      LOWORD(v463) = v463 & 0xDFFF;
                  }
                  if ( (_WORD)v463 == 0xFFFC )
                    v464 = (unsigned __int16)WORD2(*(_QWORD *)v462) >> 5;
                  v446 = v464 + v540;
                  v540 += v464;
                }
                else
                {
                  LODWORD(v546) = 0;
                }
                if ( v545 && v545 < (unsigned __int64)v541 + v446 )
                {
                  if ( byte_10316E8D7 || (qword_10317B120 & 1) != 0 )
                  {
                    v465 = *(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                                     + SystemThread_TlsOffset
                                     + 8LL);
                    if ( v465 )
                    {
                      v466 = *(_QWORD *)(v465 + 96);
                      if ( v466 )
                      {
                        if ( *(_BYTE *)(v466 + 1177) )
                        {
                          if ( byte_10316E7C7 || (qword_10317B120 & 2) != 0 )
                            utassert_fail(1u, "false", "Sql\\Ntdbms\\storeng\\drs\\fixedvarrecord.cpp", 2114, 0);
                          else
                            ex_raise(34, 68, 21, 1018);
                        }
                      }
                    }
                  }
                  RaiseInconsistencyError(v541, 18);
                  v446 = v540;
                }
                if ( v446 - 1 > 0x3F3B )
                {
                  if ( byte_10316E8D7 || (qword_10317B120 & 1) != 0 )
                  {
                    v467 = *(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                                     + SystemThread_TlsOffset
                                     + 8LL);
                    if ( v467 )
                    {
                      v468 = *(_QWORD *)(v467 + 96);
                      if ( v468 )
                      {
                        if ( *(_BYTE *)(v468 + 1177) )
                        {
                          if ( byte_10316E7C7 || (qword_10317B120 & 2) != 0 )
                            utassert_fail(1u, "false", "Sql\\Ntdbms\\storeng\\drs\\fixedvarrecord.cpp", 2119, 0);
                          else
                            ex_raise(34, 68, 21, 1005);
                        }
                      }
                    }
                  }
                  RaiseInconsistencyError(v541, 5);
                  v446 = v540;
                }
              }
LABEL_1458:
              if ( v446 >= 9 || (v469 = *(_BYTE *)v541 & 0xE) != 0 && v469 != 12 )
                v307 = v446;
            }
            v336 = v541;
            v337 = v564;
            XdesRMReadWrite::PrepareDataSetSessionForReadWrite(
              v564,
              (*((unsigned int *)v555 + 5) | ((unsigned __int64)*((unsigned __int16 *)v555 + 12) << 32)) << 16,
              1,
              1);
            LOBYTE(v533) = RowCountAdjustmentForLogicalRevert == 0;
            goto LABEL_963;
          }
LABEL_967:
          v552[0] = 0;
          if ( !v208 )
          {
            v339 = 0;
            v365 = 0;
            v364 = 9;
            goto LABEL_1068;
          }
          v339 = v624;
          if ( v622 )
          {
            if ( !v624 )
            {
              CDRecord::Resize((CDRecord *)&v623);
              v339 = v624;
            }
            if ( v339 >= 9 )
              goto LABEL_1066;
            if ( (*v625 & 0x1C) != 0 )
            {
              v363 = (*v625 & 0x1C) == 12;
LABEL_1064:
              if ( v363 )
                goto LABEL_1065;
LABEL_1066:
              v364 = 9;
              v365 = v625;
              goto LABEL_1068;
            }
          }
          else
          {
            if ( !v624 )
            {
              v623 = 0;
              v339 = v626;
              HIDWORD(v626) = v626;
              if ( (*v625 & 0x10) != 0 )
              {
                v339 = (((unsigned int)*(unsigned __int16 *)&v625[(unsigned int)v626] + 7) >> 3) + v626 + 2;
                HIDWORD(v626) = v339;
              }
              if ( (*v625 & 0x20) != 0 )
              {
                v340 = &v625[v339];
                v341 = *(_WORD *)v340;
                v628 = v341;
                if ( !v341 )
                {
                  if ( byte_10316E8D7 || (qword_10317B120 & 1) != 0 )
                  {
                    v342 = *(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                                     + SystemThread_TlsOffset
                                     + 8LL);
                    if ( v342 )
                    {
                      v343 = *(_QWORD *)(v342 + 96);
                      if ( v343 )
                      {
                        if ( *(_BYTE *)(v343 + 1177) )
                        {
                          if ( byte_10316E7C7 || (qword_10317B120 & 2) != 0 )
                            utassert_fail(1u, "false", "Sql\\Ntdbms\\storeng\\drs\\fixedvarrecord.cpp", 2010, 0);
                          else
                            ex_raise(34, 68, 21, 1003);
                        }
                      }
                    }
                  }
                  RaiseInconsistencyError(v625, 3);
                  v341 = v628;
                }
                v344 = HIDWORD(v626) + 2 + 2 * v341;
                v627 = v344;
                if ( v344 > 0x1F9E )
                {
                  if ( byte_10316E8D7 || (qword_10317B120 & 1) != 0 )
                  {
                    v345 = *(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                                     + SystemThread_TlsOffset
                                     + 8LL);
                    if ( v345 )
                    {
                      v346 = *(_QWORD *)(v345 + 96);
                      if ( v346 )
                      {
                        if ( *(_BYTE *)(v346 + 1177) )
                        {
                          if ( byte_10316E7C7 || (qword_10317B120 & 2) != 0 )
                            utassert_fail(1u, "false", "Sql\\Ntdbms\\storeng\\drs\\fixedvarrecord.cpp", 2017, 0);
                          else
                            ex_raise(34, 68, 21, 1004);
                        }
                      }
                    }
                  }
                  RaiseInconsistencyError(v625, 4);
                  v341 = v628;
                  v344 = v627;
                }
                v339 = *(_WORD *)&v340[2 * v341] & 0x7FFF;
                v624 = v339;
                if ( v344 > v339 )
                {
                  if ( byte_10316E8D7 || (qword_10317B120 & 1) != 0 )
                  {
                    v347 = *(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                                     + SystemThread_TlsOffset
                                     + 8LL);
                    if ( v347 )
                    {
                      v348 = *(_QWORD *)(v347 + 96);
                      if ( v348 )
                      {
                        if ( *(_BYTE *)(v348 + 1177) )
                        {
                          if ( byte_10316E7C7 || (qword_10317B120 & 2) != 0 )
                            utassert_fail(1u, "false", "Sql\\Ntdbms\\storeng\\drs\\fixedvarrecord.cpp", 2024, 0);
                          else
                            ex_raise(34, 68, 21, 1004);
                        }
                      }
                    }
                  }
                  RaiseInconsistencyError(v625, 4);
                  v341 = v628;
                  v344 = v627;
                  v339 = v624;
                }
                while ( *(__int16 *)&v340[2 * v341] < 0 )
                {
                  v349 = &v625[HIDWORD(v626)];
                  if ( v341 == 1 )
                    v350 = v344;
                  else
                    v350 = *(_WORD *)&v349[2 * v341 - 2] & 0x7FFF;
                  if ( v350 < v344 || (*(_WORD *)&v349[2 * v341] & 0x7FFFu) < v350 )
                  {
                    RaiseInconsistencyError(v625, 7);
                    v341 = v628;
                    v344 = v627;
                    v339 = v624;
                  }
                  if ( v350 < v344 || v350 > v339 )
                    goto LABEL_1056;
                  v351 = *(_WORD *)&v625[v350];
                  if ( v351 == 5 )
                  {
                    v623 |= 2u;
                    v628 = v341 - 1;
                    WORD2(v630) = v350;
                    v352 = &v625[(unsigned __int16)v350];
                    v353 = *((_WORD *)v352 + 1);
                    if ( (v353 & 0x4000) != 0 )
                      v354 = (v353 ^ WORD3(v630)) & 0x3800 ^ WORD3(v630);
                    else
                      v354 = WORD3(v630) & 0xC7FF;
                    WORD3(v630) = v354;
                    WORD3(v630) = v354 ^ (*((_WORD *)v352 + 1) ^ v354) & 0x7FF;
                    break;
                  }
                  if ( v351 >= 0x400u )
                  {
                    v623 |= 1u;
                    v101 = v341-- == 1;
                    v628 = v341;
                    if ( !v101 )
                      continue;
                  }
                  break;
                }
              }
              else
              {
                v624 = v339;
                v628 = 0;
                v627 = v339;
              }
              if ( (*v625 & 0x40) != 0 )
              {
                LODWORD(v630) = v339;
                v624 = v339 + 14;
                v355 = FixedVarRecord::FindVersioningInfo((FixedVarRecord *)&v623);
                v356 = HIWORD(*(_QWORD *)v355);
                v357 = 0;
                if ( (((__int16)v356 ^ ((unsigned int)(__int16)v356 >> 1)) & 0x2000) != 0 )
                {
                  if ( (v356 & 0x4000) != 0 )
                    LOWORD(v356) = v356 | 0x2000;
                  else
                    LOWORD(v356) = v356 & 0xDFFF;
                }
                if ( (_WORD)v356 == 0xFFFC )
                  v357 = (unsigned __int16)WORD2(*(_QWORD *)v355) >> 5;
                v339 = v357 + v624;
                v624 += v357;
              }
              else
              {
                LODWORD(v630) = 0;
              }
              if ( v629 && v629 < (unsigned __int64)&v625[v339] )
              {
                if ( byte_10316E8D7 || (qword_10317B120 & 1) != 0 )
                {
                  v358 = *(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                                   + SystemThread_TlsOffset
                                   + 8LL);
                  if ( v358 )
                  {
                    v359 = *(_QWORD *)(v358 + 96);
                    if ( v359 )
                    {
                      if ( *(_BYTE *)(v359 + 1177) )
                      {
                        if ( byte_10316E7C7 || (qword_10317B120 & 2) != 0 )
                          utassert_fail(1u, "false", "Sql\\Ntdbms\\storeng\\drs\\fixedvarrecord.cpp", 2114, 0);
                        else
                          ex_raise(34, 68, 21, 1018);
                      }
                    }
                  }
                }
                RaiseInconsistencyError(v625, 18);
                v339 = v624;
              }
              if ( v339 - 1 > 0x3F3B )
              {
                if ( byte_10316E8D7 || (qword_10317B120 & 1) != 0 )
                {
                  v360 = *(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                                   + SystemThread_TlsOffset
                                   + 8LL);
                  if ( v360 )
                  {
                    v361 = *(_QWORD *)(v360 + 96);
                    if ( v361 )
                    {
                      if ( *(_BYTE *)(v361 + 1177) )
                      {
                        if ( byte_10316E7C7 || (qword_10317B120 & 2) != 0 )
                          utassert_fail(1u, "false", "Sql\\Ntdbms\\storeng\\drs\\fixedvarrecord.cpp", 2119, 0);
                        else
                          ex_raise(34, 68, 21, 1005);
                      }
                    }
                  }
                }
                RaiseInconsistencyError(v625, 5);
                v339 = v624;
              }
            }
LABEL_1056:
            if ( v339 >= 9 )
              goto LABEL_1066;
            v362 = *v625 & 0xE;
            if ( v362 )
            {
              v363 = v362 == 12;
              goto LABEL_1064;
            }
          }
LABEL_1065:
          v364 = 9;
          v339 = 9;
          v365 = v625;
LABEL_1068:
          if ( v538 )
          {
            v390 = v540;
            if ( !v540 )
            {
              CDRecord::Resize((CDRecord *)&v539);
              v390 = v540;
            }
            if ( v390 >= 9 || (*(_BYTE *)v541 & 0x1C) != 0 && (*(_BYTE *)v541 & 0x1C) != 0xC )
              v364 = v390;
          }
          else
          {
            v366 = v540;
            if ( !v540 )
            {
              v539 = 0;
              v366 = v542;
              HIDWORD(v542) = v542;
              if ( (*(_BYTE *)v541 & 0x10) != 0 )
              {
                v366 = (((unsigned int)*(unsigned __int16 *)((char *)v541 + (unsigned int)v542) + 7) >> 3) + v542 + 2;
                HIDWORD(v542) = v366;
              }
              if ( (*(_BYTE *)v541 & 0x20) != 0 )
              {
                v367 = (unsigned __int16 *)((char *)v541 + v366);
                v368 = *v367;
                v544 = v368;
                if ( !v368 )
                {
                  if ( byte_10316E8D7 || (qword_10317B120 & 1) != 0 )
                  {
                    v369 = *(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                                     + SystemThread_TlsOffset
                                     + 8LL);
                    if ( v369 )
                    {
                      v370 = *(_QWORD *)(v369 + 96);
                      if ( v370 )
                      {
                        if ( *(_BYTE *)(v370 + 1177) )
                        {
                          if ( byte_10316E7C7 || (qword_10317B120 & 2) != 0 )
                            utassert_fail(1u, "false", "Sql\\Ntdbms\\storeng\\drs\\fixedvarrecord.cpp", 2010, 0);
                          else
                            ex_raise(34, 68, 21, 1003);
                        }
                      }
                    }
                  }
                  RaiseInconsistencyError(v541, 3);
                  v368 = v544;
                }
                v371 = HIDWORD(v542) + 2 + 2 * v368;
                v543 = v371;
                if ( v371 > 0x1F9E )
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
                            utassert_fail(1u, "false", "Sql\\Ntdbms\\storeng\\drs\\fixedvarrecord.cpp", 2017, 0);
                          else
                            ex_raise(34, 68, 21, 1004);
                        }
                      }
                    }
                  }
                  RaiseInconsistencyError(v541, 4);
                  v368 = v544;
                  v371 = v543;
                }
                v366 = v367[v368] & 0x7FFF;
                v540 = v366;
                if ( v371 > v366 )
                {
                  if ( byte_10316E8D7 || (qword_10317B120 & 1) != 0 )
                  {
                    v374 = *(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                                     + SystemThread_TlsOffset
                                     + 8LL);
                    if ( v374 )
                    {
                      v375 = *(_QWORD *)(v374 + 96);
                      if ( v375 )
                      {
                        if ( *(_BYTE *)(v375 + 1177) )
                        {
                          if ( byte_10316E7C7 || (qword_10317B120 & 2) != 0 )
                            utassert_fail(1u, "false", "Sql\\Ntdbms\\storeng\\drs\\fixedvarrecord.cpp", 2024, 0);
                          else
                            ex_raise(34, 68, 21, 1004);
                        }
                      }
                    }
                  }
                  RaiseInconsistencyError(v541, 4);
                  v368 = v544;
                  v371 = v543;
                  v366 = v540;
                }
                while ( (v367[v368] & 0x8000u) != 0 )
                {
                  v376 = (char *)v541 + HIDWORD(v542);
                  if ( v368 == 1 )
                    v377 = v371;
                  else
                    v377 = *(_WORD *)&v376[2 * v368 - 2] & 0x7FFF;
                  if ( v377 < v371 || (*(_WORD *)&v376[2 * v368] & 0x7FFFu) < v377 )
                  {
                    RaiseInconsistencyError(v541, 7);
                    v368 = v544;
                    v371 = v543;
                    v366 = v540;
                  }
                  if ( v377 < v371 || v377 > v366 )
                    goto LABEL_1156;
                  v378 = *(_WORD *)((char *)v541 + v377);
                  if ( v378 == 5 )
                  {
                    v539 |= 2u;
                    v544 = v368 - 1;
                    WORD2(v546) = v377;
                    v379 = (char *)v541 + (unsigned __int16)v377;
                    v380 = *((_WORD *)v379 + 1);
                    if ( (v380 & 0x4000) != 0 )
                      v381 = (v380 ^ WORD3(v546)) & 0x3800 ^ WORD3(v546);
                    else
                      v381 = WORD3(v546) & 0xC7FF;
                    WORD3(v546) = v381;
                    WORD3(v546) = v381 ^ (*((_WORD *)v379 + 1) ^ v381) & 0x7FF;
                    break;
                  }
                  if ( v378 >= 0x400u )
                  {
                    v539 |= 1u;
                    v101 = v368-- == 1;
                    v544 = v368;
                    if ( !v101 )
                      continue;
                  }
                  break;
                }
              }
              else
              {
                v540 = v366;
                v544 = 0;
                v543 = v366;
              }
              if ( (*(_BYTE *)v541 & 0x40) != 0 )
              {
                LODWORD(v546) = v366;
                v540 = v366 + 14;
                v382 = FixedVarRecord::FindVersioningInfo((FixedVarRecord *)&v539);
                v383 = HIWORD(*(_QWORD *)v382);
                v384 = 0;
                if ( (((__int16)v383 ^ ((unsigned int)(__int16)v383 >> 1)) & 0x2000) != 0 )
                {
                  if ( (v383 & 0x4000) != 0 )
                    LOWORD(v383) = v383 | 0x2000;
                  else
                    LOWORD(v383) = v383 & 0xDFFF;
                }
                if ( (_WORD)v383 == 0xFFFC )
                  v384 = (unsigned __int16)WORD2(*(_QWORD *)v382) >> 5;
                v366 = v384 + v540;
                v540 += v384;
              }
              else
              {
                LODWORD(v546) = 0;
              }
              if ( v545 && v545 < (unsigned __int64)v541 + v366 )
              {
                if ( byte_10316E8D7 || (qword_10317B120 & 1) != 0 )
                {
                  v385 = *(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                                   + SystemThread_TlsOffset
                                   + 8LL);
                  if ( v385 )
                  {
                    v386 = *(_QWORD *)(v385 + 96);
                    if ( v386 )
                    {
                      if ( *(_BYTE *)(v386 + 1177) )
                      {
                        if ( byte_10316E7C7 || (qword_10317B120 & 2) != 0 )
                          utassert_fail(1u, "false", "Sql\\Ntdbms\\storeng\\drs\\fixedvarrecord.cpp", 2114, 0);
                        else
                          ex_raise(34, 68, 21, 1018);
                      }
                    }
                  }
                }
                RaiseInconsistencyError(v541, 18);
                v366 = v540;
              }
              if ( v366 - 1 > 0x3F3B )
              {
                if ( byte_10316E8D7 || (qword_10317B120 & 1) != 0 )
                {
                  v387 = *(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                                   + SystemThread_TlsOffset
                                   + 8LL);
                  if ( v387 )
                  {
                    v388 = *(_QWORD *)(v387 + 96);
                    if ( v388 )
                    {
                      if ( *(_BYTE *)(v388 + 1177) )
                      {
                        if ( byte_10316E7C7 || (qword_10317B120 & 2) != 0 )
                          utassert_fail(1u, "false", "Sql\\Ntdbms\\storeng\\drs\\fixedvarrecord.cpp", 2119, 0);
                        else
                          ex_raise(34, 68, 21, 1005);
                      }
                    }
                  }
                }
                RaiseInconsistencyError(v541, 5);
                v366 = v540;
              }
            }
LABEL_1156:
            if ( v366 >= 9 || (v389 = *(_BYTE *)v541 & 0xE) != 0 && v389 != 12 )
              v364 = v366;
          }
          v391 = v541;
          v392 = v564;
          XdesRMReadWrite::PrepareDataSetSessionForReadWrite(
            v564,
            (*((unsigned int *)v555 + 5) | ((unsigned __int64)*((unsigned __int16 *)v555 + 12) << 32)) << 16,
            1,
            1);
          v393 = &v633;
          if ( !v536 )
            v393 = 0;
          LOBYTE(v533) = RowCountAdjustmentForLogicalRevert == 0;
          LOBYTE(v532) = v214;
          v279 = IndexDataSetSession::DeleteRowByLogicalRevert(
                   *((_QWORD *)v392 + 1101),
                   v391,
                   v364,
                   v393,
                   v552,
                   v365,
                   v339,
                   v532,
                   v533);
          v553 = v279;
          goto LABEL_1676;
        }
        if ( v209 )
          goto LABEL_967;
        if ( v214 )
        {
          v394 = v622;
          if ( v622 )
          {
            v396 = (((*v625 & 0x1C) - 4) & 0xFFFFFFE7) == 0;
          }
          else
          {
            v395 = *v625 & 0xE;
            if ( v395 == 2 )
              v396 = (v625[1] & 1) != 0;
            else
              v396 = ((v395 - 10) & 0xF9) == 0;
          }
          if ( v396 )
          {
            utassert_fail(1u, "!committedRec.IsGhostRecord()", "IndexRowScanner.cpp", 3373, 0);
            v394 = v622;
          }
          if ( v394 )
          {
            if ( !v624 )
              CDRecord::Resize((CDRecord *)&v623);
            goto LABEL_1267;
          }
          if ( v624 )
            goto LABEL_1267;
          v623 = 0;
          v397 = v626;
          HIDWORD(v626) = v626;
          if ( (*v625 & 0x10) != 0 )
          {
            v397 = (((unsigned int)*(unsigned __int16 *)&v625[(unsigned int)v626] + 7) >> 3) + v626 + 2;
            HIDWORD(v626) = v397;
          }
          if ( (*v625 & 0x20) != 0 )
          {
            v398 = &v625[v397];
            v399 = *(_WORD *)v398;
            v628 = v399;
            if ( !v399 )
            {
              if ( byte_10316E8D7 || (qword_10317B120 & 1) != 0 )
              {
                v400 = *(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                                 + SystemThread_TlsOffset
                                 + 8LL);
                if ( v400 )
                {
                  v401 = *(_QWORD *)(v400 + 96);
                  if ( v401 )
                  {
                    if ( *(_BYTE *)(v401 + 1177) )
                    {
                      if ( byte_10316E7C7 || (qword_10317B120 & 2) != 0 )
                        utassert_fail(1u, "false", "Sql\\Ntdbms\\storeng\\drs\\fixedvarrecord.cpp", 2010, 0);
                      else
                        ex_raise(34, 68, 21, 1003);
                    }
                  }
                }
              }
              RaiseInconsistencyError(v625, 3);
              v399 = v628;
            }
            v402 = HIDWORD(v626) + 2 + 2 * v399;
            v627 = v402;
            if ( v402 > 0x1F9E )
            {
              if ( byte_10316E8D7 || (qword_10317B120 & 1) != 0 )
              {
                v403 = *(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                                 + SystemThread_TlsOffset
                                 + 8LL);
                if ( v403 )
                {
                  v404 = *(_QWORD *)(v403 + 96);
                  if ( v404 )
                  {
                    if ( *(_BYTE *)(v404 + 1177) )
                    {
                      if ( byte_10316E7C7 || (qword_10317B120 & 2) != 0 )
                        utassert_fail(1u, "false", "Sql\\Ntdbms\\storeng\\drs\\fixedvarrecord.cpp", 2017, 0);
                      else
                        ex_raise(34, 68, 21, 1004);
                    }
                  }
                }
              }
              RaiseInconsistencyError(v625, 4);
              v399 = v628;
              v402 = v627;
            }
            v397 = *(_WORD *)&v398[2 * v399] & 0x7FFF;
            v624 = v397;
            if ( v402 > v397 )
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
                        utassert_fail(1u, "false", "Sql\\Ntdbms\\storeng\\drs\\fixedvarrecord.cpp", 2024, 0);
                      else
                        ex_raise(34, 68, 21, 1004);
                    }
                  }
                }
              }
              RaiseInconsistencyError(v625, 4);
              v399 = v628;
              v402 = v627;
              v397 = v624;
            }
            while ( *(__int16 *)&v398[2 * v399] < 0 )
            {
              v407 = &v625[HIDWORD(v626)];
              if ( v399 == 1 )
                v408 = v402;
              else
                v408 = *(_WORD *)&v407[2 * v399 - 2] & 0x7FFF;
              if ( v408 < v402 || (*(_WORD *)&v407[2 * v399] & 0x7FFFu) < v408 )
              {
                RaiseInconsistencyError(v625, 7);
                v399 = v628;
                v402 = v627;
                v397 = v624;
              }
              if ( v408 < v402 || v408 > v397 )
                goto LABEL_1267;
              v409 = *(_WORD *)&v625[v408];
              if ( v409 == 5 )
              {
                v623 |= 2u;
                v628 = v399 - 1;
                WORD2(v630) = v408;
                v410 = &v625[(unsigned __int16)v408];
                v411 = *((_WORD *)v410 + 1);
                if ( (v411 & 0x4000) != 0 )
                  v412 = (v411 ^ WORD3(v630)) & 0x3800 ^ WORD3(v630);
                else
                  v412 = WORD3(v630) & 0xC7FF;
                WORD3(v630) = v412;
                WORD3(v630) = v412 ^ (*((_WORD *)v410 + 1) ^ v412) & 0x7FF;
                break;
              }
              if ( v409 >= 0x400u )
              {
                v623 |= 1u;
                v101 = v399-- == 1;
                v628 = v399;
                if ( !v101 )
                  continue;
              }
              break;
            }
          }
          else
          {
            v624 = v397;
            v628 = 0;
            v627 = v397;
          }
          if ( (*v625 & 0x40) != 0 )
          {
            LODWORD(v630) = v397;
            v624 = v397 + 14;
            v413 = FixedVarRecord::FindVersioningInfo((FixedVarRecord *)&v623);
            v414 = HIWORD(*(_QWORD *)v413);
            v415 = 0;
            if ( (((__int16)v414 ^ ((unsigned int)(__int16)v414 >> 1)) & 0x2000) != 0 )
            {
              if ( (v414 & 0x4000) != 0 )
                LOWORD(v414) = v414 | 0x2000;
              else
                LOWORD(v414) = v414 & 0xDFFF;
            }
            if ( (_WORD)v414 == 0xFFFC )
              v415 = (unsigned __int16)WORD2(*(_QWORD *)v413) >> 5;
            v397 = v415 + v624;
            v624 += v415;
          }
          else
          {
            LODWORD(v630) = 0;
          }
          if ( v629 && v629 < (unsigned __int64)&v625[v397] )
          {
            if ( byte_10316E8D7 || (qword_10317B120 & 1) != 0 )
            {
              v416 = *(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                               + SystemThread_TlsOffset
                               + 8LL);
              if ( v416 )
              {
                v417 = *(_QWORD *)(v416 + 96);
                if ( v417 )
                {
                  if ( *(_BYTE *)(v417 + 1177) )
                  {
                    if ( byte_10316E7C7 || (qword_10317B120 & 2) != 0 )
                      utassert_fail(1u, "false", "Sql\\Ntdbms\\storeng\\drs\\fixedvarrecord.cpp", 2114, 0);
                    else
                      ex_raise(34, 68, 21, 1018);
                  }
                }
              }
            }
            RaiseInconsistencyError(v625, 18);
            v397 = v624;
          }
          if ( v397 - 1 <= 0x3F3B )
            goto LABEL_1267;
          if ( byte_10316E8D7 || (qword_10317B120 & 1) != 0 )
          {
            v418 = *(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                             + SystemThread_TlsOffset
                             + 8LL);
            if ( v418 )
            {
              v419 = *(_QWORD *)(v418 + 96);
              if ( v419 )
              {
                if ( *(_BYTE *)(v419 + 1177) )
                {
                  if ( !byte_10316E7C7 && (qword_10317B120 & 2) == 0 )
                  {
                    ex_raise(34, 68, 21, 1005);
                    RaiseInconsistencyError(v625, 5);
LABEL_1267:
                    v420 = v625;
                    v421 = v564;
                    XdesRMReadWrite::PrepareDataSetSessionForReadWrite(
                      v564,
                      (*((unsigned int *)v555 + 5) | ((unsigned __int64)*((unsigned __int16 *)v555 + 12) << 32)) << 16,
                      1,
                      1);
                    IndexDataSetSession::UndoInsertRow(
                      *((IndexDataSetSession **)v421 + 1101),
                      v420,
                      RowCountAdjustmentForLogicalRevert == 0);
                    v279 = v553;
LABEL_1677:
                    if ( !v551 )
                      (*(void (__fastcall **)(_QWORD *))(*v569 + 40LL))(v569);
                    if ( ((v279 - 1) & 0xFFFFFFFC) != 0 || v279 == 3 )
                    {
                      v8 = 3;
                      v527 = v596;
                      if ( (qword_10317F6E4 & 0x4000000) != 0 )
                      {
                        v610 = 0x10000;
                        v611 = 0;
                        v612 = v615;
                        v613 = &v616;
                        v617 = 0;
                        v614 = 0;
                        v618 = 0;
                        v615[0] = &v619;
                        v615[1] = 8;
                        v619 = *(_WORD *)(v596 + 1720);
                        v620 = *((_DWORD *)v554 + 64);
                        v621 = *((_WORD *)v554 + 130);
                        XeSqlPkg::revert_from_version_btree::Publish((XeSqlPkg::revert_from_version_btree *)v609);
                      }
                      ++*(_QWORD *)(v527 + 496);
                      if ( v216 )
                        ++*(_QWORD *)(v527 + 984);
                    }
                    else
                    {
                      v8 = v553;
                    }
                    if ( v569 )
                      (*(void (__fastcall **)(_QWORD *, __int64))*v569)(v569, 1);
                    v3 = v554;
LABEL_1689:
                    (*(void (__fastcall **)(BTreeRow *))(*(_QWORD *)v3 + 8LL))(v3);
                    return v8;
                  }
                  utassert_fail(1u, "false", "Sql\\Ntdbms\\storeng\\drs\\fixedvarrecord.cpp", 2119, 0);
                }
              }
            }
          }
          RaiseInconsistencyError(v625, 5);
          goto LABEL_1267;
        }
        v471 = *v625;
        if ( v622 )
          v472 = v471 >> 1;
        else
          v472 = v471 >> 6;
        if ( (v472 & 1) != 0 )
        {
          if ( v622 )
            CDRecord::GetXdesTs(&v623, &v584);
          else
            FixedVarRecord::GetXdesTs(&v623, &v584);
          v473 = v584;
          v474 = v585;
          if ( v622 )
            CDRecord::GetVersionRecPtr(&v623, v602);
          else
            FixedVarRecord::GetVersionRecPtr(&v623, v602);
          v475 = *((_QWORD *)v171 + 6);
          LODWORD(v589) = v473;
          WORD2(v589) = v474;
          LOBYTE(v533) = 0;
          LOBYTE(v532) = 0;
          LOBYTE(v531) = 0;
          LOBYTE(v530) = 0;
          LOBYTE(v529) = 0;
          if ( !(unsigned __int8)VersionMgr::IsTimestampInteresting(
                                   *(_QWORD *)(v475 + 1712),
                                   &v589,
                                   v602,
                                   &v570,
                                   v529,
                                   v530,
                                   v531,
                                   v532) )
          {
            if ( v622 )
            {
              if ( (*v625 & 2) != 0 )
              {
                if ( !v624 )
                  CDRecord::Resize((CDRecord *)&v623);
                *v625 &= ~2u;
                v624 = v631;
                v631 = 0;
              }
            }
            else
            {
              FixedVarRecord::ClearVersioningInfo((FixedVarRecord *)&v623);
            }
          }
        }
        v476 = v555;
        v477 = *(_DWORD *)(*((_QWORD *)v555 + 1) + 256LL) == 2;
        v555 = 0;
        v556 = 0;
        if ( v538 )
        {
          if ( !v540 )
            CDRecord::Resize((CDRecord *)&v539);
        }
        else if ( !v540 )
        {
          v539 = 0;
          v478 = v542;
          HIDWORD(v542) = v542;
          if ( (*(_BYTE *)v541 & 0x10) != 0 )
          {
            v478 = (((unsigned int)*(unsigned __int16 *)((char *)v541 + (unsigned int)v542) + 7) >> 3) + v542 + 2;
            HIDWORD(v542) = v478;
          }
          if ( (*(_BYTE *)v541 & 0x20) != 0 )
          {
            v479 = (unsigned __int16 *)((char *)v541 + v478);
            v480 = *v479;
            v544 = v480;
            if ( !v480 )
            {
              if ( byte_10316E8D7 || (qword_10317B120 & 1) != 0 )
              {
                v481 = *(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                                 + SystemThread_TlsOffset
                                 + 8LL);
                if ( v481 )
                {
                  v482 = *(_QWORD *)(v481 + 96);
                  if ( v482 )
                  {
                    if ( *(_BYTE *)(v482 + 1177) )
                    {
                      if ( byte_10316E7C7 || (qword_10317B120 & 2) != 0 )
                        utassert_fail(1u, "false", "Sql\\Ntdbms\\storeng\\drs\\fixedvarrecord.cpp", 2010, 0);
                      else
                        ex_raise(34, 68, 21, 1003);
                    }
                  }
                }
              }
              RaiseInconsistencyError(v541, 3);
              v480 = v544;
            }
            v483 = HIDWORD(v542) + 2 + 2 * v480;
            v543 = v483;
            if ( v483 > 0x1F9E )
            {
              if ( byte_10316E8D7 || (qword_10317B120 & 1) != 0 )
              {
                v484 = *(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                                 + SystemThread_TlsOffset
                                 + 8LL);
                if ( v484 )
                {
                  v485 = *(_QWORD *)(v484 + 96);
                  if ( v485 )
                  {
                    if ( *(_BYTE *)(v485 + 1177) )
                    {
                      if ( byte_10316E7C7 || (qword_10317B120 & 2) != 0 )
                        utassert_fail(1u, "false", "Sql\\Ntdbms\\storeng\\drs\\fixedvarrecord.cpp", 2017, 0);
                      else
                        ex_raise(34, 68, 21, 1004);
                    }
                  }
                }
              }
              RaiseInconsistencyError(v541, 4);
              v480 = v544;
              v483 = v543;
            }
            v478 = v479[v480] & 0x7FFF;
            v540 = v478;
            if ( v483 > v478 )
            {
              if ( byte_10316E8D7 || (qword_10317B120 & 1) != 0 )
              {
                v486 = *(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                                 + SystemThread_TlsOffset
                                 + 8LL);
                if ( v486 )
                {
                  v487 = *(_QWORD *)(v486 + 96);
                  if ( v487 )
                  {
                    if ( *(_BYTE *)(v487 + 1177) )
                    {
                      if ( byte_10316E7C7 || (qword_10317B120 & 2) != 0 )
                        utassert_fail(1u, "false", "Sql\\Ntdbms\\storeng\\drs\\fixedvarrecord.cpp", 2024, 0);
                      else
                        ex_raise(34, 68, 21, 1004);
                    }
                  }
                }
              }
              RaiseInconsistencyError(v541, 4);
              v480 = v544;
              v483 = v543;
              v478 = v540;
            }
            while ( (v479[v480] & 0x8000u) != 0 )
            {
              v488 = (char *)v541 + HIDWORD(v542);
              if ( v480 == 1 )
                v489 = v483;
              else
                v489 = *(_WORD *)&v488[2 * v480 - 2] & 0x7FFF;
              if ( v489 < v483 || (*(_WORD *)&v488[2 * v480] & 0x7FFFu) < v489 )
              {
                RaiseInconsistencyError(v541, 7);
                v480 = v544;
                v483 = v543;
                v478 = v540;
              }
              if ( v489 < v483 || v489 > v478 )
                goto LABEL_1576;
              v490 = *(_WORD *)((char *)v541 + v489);
              if ( v490 == 5 )
              {
                v539 |= 2u;
                v544 = v480 - 1;
                WORD2(v546) = v489;
                v491 = (char *)v541 + (unsigned __int16)v489;
                v492 = *((_WORD *)v491 + 1);
                if ( (v492 & 0x4000) != 0 )
                  v493 = (v492 ^ WORD3(v546)) & 0x3800 ^ WORD3(v546);
                else
                  v493 = WORD3(v546) & 0xC7FF;
                WORD3(v546) = v493;
                WORD3(v546) = v493 ^ (*((_WORD *)v491 + 1) ^ v493) & 0x7FF;
                break;
              }
              if ( v490 >= 0x400u )
              {
                v539 |= 1u;
                v101 = v480-- == 1;
                v544 = v480;
                if ( !v101 )
                  continue;
              }
              break;
            }
          }
          else
          {
            v540 = v478;
            v544 = 0;
            v543 = v478;
          }
          if ( (*(_BYTE *)v541 & 0x40) != 0 )
          {
            LODWORD(v546) = v478;
            v540 = v478 + 14;
            v494 = FixedVarRecord::FindVersioningInfo((FixedVarRecord *)&v539);
            v495 = HIWORD(*(_QWORD *)v494);
            v496 = 0;
            if ( (((__int16)v495 ^ ((unsigned int)(__int16)v495 >> 1)) & 0x2000) != 0 )
            {
              if ( (v495 & 0x4000) != 0 )
                LOWORD(v495) = v495 | 0x2000;
              else
                LOWORD(v495) = v495 & 0xDFFF;
            }
            if ( (_WORD)v495 == 0xFFFC )
              v496 = (unsigned __int16)WORD2(*(_QWORD *)v494) >> 5;
            v478 = v496 + v540;
            v540 += v496;
          }
          else
          {
            LODWORD(v546) = 0;
          }
          if ( v545 && v545 < (unsigned __int64)v541 + v478 )
          {
            if ( byte_10316E8D7 || (qword_10317B120 & 1) != 0 )
            {
              v497 = *(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                               + SystemThread_TlsOffset
                               + 8LL);
              if ( v497 )
              {
                v498 = *(_QWORD *)(v497 + 96);
                if ( v498 )
                {
                  if ( *(_BYTE *)(v498 + 1177) )
                  {
                    if ( byte_10316E7C7 || (qword_10317B120 & 2) != 0 )
                      utassert_fail(1u, "false", "Sql\\Ntdbms\\storeng\\drs\\fixedvarrecord.cpp", 2114, 0);
                    else
                      ex_raise(34, 68, 21, 1018);
                  }
                }
              }
            }
            RaiseInconsistencyError(v541, 18);
            v478 = v540;
          }
          if ( v478 - 1 > 0x3F3B )
          {
            if ( byte_10316E8D7 || (qword_10317B120 & 1) != 0 )
            {
              v499 = *(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                               + SystemThread_TlsOffset
                               + 8LL);
              if ( v499 )
              {
                v500 = *(_QWORD *)(v499 + 96);
                if ( v500 )
                {
                  if ( *(_BYTE *)(v500 + 1177) )
                  {
                    if ( !byte_10316E7C7 && (qword_10317B120 & 2) == 0 )
                    {
                      ex_raise(34, 68, 21, 1005);
                      RaiseInconsistencyError(v541, 5);
                      goto LABEL_1576;
                    }
                    utassert_fail(1u, "false", "Sql\\Ntdbms\\storeng\\drs\\fixedvarrecord.cpp", 2119, 0);
                  }
                }
              }
            }
            RaiseInconsistencyError(v541, 5);
          }
        }
LABEL_1576:
        if ( v622 )
        {
          if ( !v624 )
            CDRecord::Resize((CDRecord *)&v623);
          if ( v624 >= 9 )
            goto LABEL_1674;
          if ( (*v625 & 0x1C) != 0 )
          {
            v525 = (*v625 & 0x1C) == 12;
LABEL_1672:
            if ( v525 )
              goto LABEL_1673;
LABEL_1674:
            v526 = v624;
            goto LABEL_1675;
          }
        }
        else
        {
          if ( !v624 )
          {
            v623 = 0;
            v501 = v626;
            HIDWORD(v626) = v626;
            if ( (*v625 & 0x10) != 0 )
            {
              v501 = (((unsigned int)*(unsigned __int16 *)&v625[(unsigned int)v626] + 7) >> 3) + v626 + 2;
              HIDWORD(v626) = v501;
            }
            if ( (*v625 & 0x20) != 0 )
            {
              v502 = &v625[v501];
              v503 = *(_WORD *)v502;
              v628 = v503;
              if ( !v503 )
              {
                if ( byte_10316E8D7 || (qword_10317B120 & 1) != 0 )
                {
                  v504 = *(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                                   + SystemThread_TlsOffset
                                   + 8LL);
                  if ( v504 )
                  {
                    v505 = *(_QWORD *)(v504 + 96);
                    if ( v505 )
                    {
                      if ( *(_BYTE *)(v505 + 1177) )
                      {
                        if ( byte_10316E7C7 || (qword_10317B120 & 2) != 0 )
                          utassert_fail(1u, "false", "Sql\\Ntdbms\\storeng\\drs\\fixedvarrecord.cpp", 2010, 0);
                        else
                          ex_raise(34, 68, 21, 1003);
                      }
                    }
                  }
                }
                RaiseInconsistencyError(v625, 3);
                v503 = v628;
              }
              v506 = HIDWORD(v626) + 2 + 2 * v503;
              v627 = v506;
              if ( v506 > 0x1F9E )
              {
                if ( byte_10316E8D7 || (qword_10317B120 & 1) != 0 )
                {
                  v507 = *(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                                   + SystemThread_TlsOffset
                                   + 8LL);
                  if ( v507 )
                  {
                    v508 = *(_QWORD *)(v507 + 96);
                    if ( v508 )
                    {
                      if ( *(_BYTE *)(v508 + 1177) )
                      {
                        if ( byte_10316E7C7 || (qword_10317B120 & 2) != 0 )
                          utassert_fail(1u, "false", "Sql\\Ntdbms\\storeng\\drs\\fixedvarrecord.cpp", 2017, 0);
                        else
                          ex_raise(34, 68, 21, 1004);
                      }
                    }
                  }
                }
                RaiseInconsistencyError(v625, 4);
                v503 = v628;
                v506 = v627;
              }
              v624 = *(_WORD *)&v502[2 * v503] & 0x7FFF;
              if ( v506 > v624 )
              {
                if ( byte_10316E8D7 || (qword_10317B120 & 1) != 0 )
                {
                  v509 = *(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                                   + SystemThread_TlsOffset
                                   + 8LL);
                  if ( v509 )
                  {
                    v510 = *(_QWORD *)(v509 + 96);
                    if ( v510 )
                    {
                      if ( *(_BYTE *)(v510 + 1177) )
                      {
                        if ( byte_10316E7C7 || (qword_10317B120 & 2) != 0 )
                          utassert_fail(1u, "false", "Sql\\Ntdbms\\storeng\\drs\\fixedvarrecord.cpp", 2024, 0);
                        else
                          ex_raise(34, 68, 21, 1004);
                      }
                    }
                  }
                }
                RaiseInconsistencyError(v625, 4);
                v503 = v628;
                v506 = v627;
              }
              while ( *(__int16 *)&v502[2 * v503] < 0 )
              {
                v511 = &v625[HIDWORD(v626)];
                if ( v503 == 1 )
                  v512 = v506;
                else
                  v512 = *(_WORD *)&v511[2 * v503 - 2] & 0x7FFF;
                if ( v512 < v506 || (*(_WORD *)&v511[2 * v503] & 0x7FFFu) < v512 )
                {
                  RaiseInconsistencyError(v625, 7);
                  v503 = v628;
                  v506 = v627;
                }
                if ( v512 < v506 || v512 > v624 )
                  goto LABEL_1664;
                v513 = *(_WORD *)&v625[v512];
                if ( v513 == 5 )
                {
                  v623 |= 2u;
                  v628 = v503 - 1;
                  WORD2(v630) = v512;
                  v514 = &v625[(unsigned __int16)v512];
                  v515 = *((_WORD *)v514 + 1);
                  if ( (v515 & 0x4000) != 0 )
                    v516 = (v515 ^ WORD3(v630)) & 0x3800 ^ WORD3(v630);
                  else
                    v516 = WORD3(v630) & 0xC7FF;
                  WORD3(v630) = v516;
                  WORD3(v630) = v516 ^ (*((_WORD *)v514 + 1) ^ v516) & 0x7FF;
                  break;
                }
                if ( v513 >= 0x400u )
                {
                  v623 |= 1u;
                  v101 = v503-- == 1;
                  v628 = v503;
                  if ( !v101 )
                    continue;
                }
                break;
              }
            }
            else
            {
              v624 = v501;
              v628 = 0;
              v627 = v501;
            }
            if ( (*v625 & 0x40) != 0 )
            {
              LODWORD(v630) = v624;
              v624 += 14;
              v517 = FixedVarRecord::FindVersioningInfo((FixedVarRecord *)&v623);
              v518 = HIWORD(*(_QWORD *)v517);
              v519 = 0;
              if ( (((__int16)v518 ^ ((unsigned int)(__int16)v518 >> 1)) & 0x2000) != 0 )
              {
                if ( (v518 & 0x4000) != 0 )
                  LOWORD(v518) = v518 | 0x2000;
                else
                  LOWORD(v518) = v518 & 0xDFFF;
              }
              if ( (_WORD)v518 == 0xFFFC )
                v519 = (unsigned __int16)WORD2(*(_QWORD *)v517) >> 5;
              v624 += v519;
            }
            else
            {
              LODWORD(v630) = 0;
            }
            if ( v629 && v629 < (unsigned __int64)&v625[v624] )
            {
              if ( byte_10316E8D7 || (qword_10317B120 & 1) != 0 )
              {
                v520 = *(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                                 + SystemThread_TlsOffset
                                 + 8LL);
                if ( v520 )
                {
                  v521 = *(_QWORD *)(v520 + 96);
                  if ( v521 )
                  {
                    if ( *(_BYTE *)(v521 + 1177) )
                    {
                      if ( byte_10316E7C7 || (qword_10317B120 & 2) != 0 )
                        utassert_fail(1u, "false", "Sql\\Ntdbms\\storeng\\drs\\fixedvarrecord.cpp", 2114, 0);
                      else
                        ex_raise(34, 68, 21, 1018);
                    }
                  }
                }
              }
              RaiseInconsistencyError(v625, 18);
            }
            if ( v624 - 1 > 0x3F3B )
            {
              if ( byte_10316E8D7 || (qword_10317B120 & 1) != 0 )
              {
                v522 = *(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                                 + SystemThread_TlsOffset
                                 + 8LL);
                if ( v522 )
                {
                  v523 = *(_QWORD *)(v522 + 96);
                  if ( v523 )
                  {
                    if ( *(_BYTE *)(v523 + 1177) )
                    {
                      if ( byte_10316E7C7 || (qword_10317B120 & 2) != 0 )
                        utassert_fail(1u, "false", "Sql\\Ntdbms\\storeng\\drs\\fixedvarrecord.cpp", 2119, 0);
                      else
                        ex_raise(34, 68, 21, 1005);
                    }
                  }
                }
              }
              RaiseInconsistencyError(v625, 5);
            }
          }
LABEL_1664:
          if ( v624 >= 9 )
            goto LABEL_1674;
          v524 = *v625 & 0xE;
          if ( v524 )
          {
            v525 = v524 == 12;
            goto LABEL_1672;
          }
        }
LABEL_1673:
        v526 = 9;
LABEL_1675:
        XdesRMReadWrite::IndexModify(
          v564,
          (*((unsigned int *)v476 + 5) | ((unsigned __int64)*((unsigned __int16 *)v476 + 12) << 32)) << 16,
          0,
          v625,
          v526,
          0,
          v559,
          v541,
          v533,
          (const struct LSN *)&v555,
          v477,
          RowCountAdjustmentForLogicalRevert == -1,
          1);
        v279 = v553;
LABEL_1676:
        v216 = v537;
        goto LABEL_1677;
      }
    }
LABEL_547:
    v212 = v554;
    goto LABEL_548;
  }
  (*(void (__fastcall **)(BTreeRow *))(*(_QWORD *)v554 + 8LL))(v554);
  if ( v569 )
    (*(void (__fastcall **)(_QWORD *, __int64))*v569)(v569, 1);
  return 1;
}

```

## disassembly

```asm
0x101388990  push    rbp
0x101388992  push    rsi
0x101388993  push    rdi
0x101388994  push    r12
0x101388996  push    r13
0x101388998  push    r14
0x10138899a  push    r15
0x10138899c  mov     eax, 5190h
0x1013889a1  call    _alloca_probe
0x1013889a6  sub     rsp, rax
0x1013889a9  lea     rbp, [rsp+70h]
0x1013889ae  mov     [rbp+5150h+var_4F60], 0FFFFFFFFFFFFFFFEh
0x1013889b9  mov     [rbp+5150h+arg_18], rbx
0x1013889c0  mov     rax, cs:__security_cookie
0x1013889c7  xor     rax, rbp
0x1013889ca  mov     [rbp+5150h+var_40], rax
0x1013889d1  mov     [rbp+5150h+var_50C8], r8
0x1013889d8  mov     [rbp+5150h+var_5050], rdx
0x1013889df  mov     r12, rcx
0x1013889e2  mov     [rbp+5150h+var_5100], rcx
0x1013889e6  mov     rax, [rcx+28h]
0x1013889ea  mov     rsi, [rax+8]
0x1013889ee  mov     [rbp+5150h+var_50C0], rsi
0x1013889f5  mov     rbx, [rsi+30h]
0x1013889f9  mov     [rbp+5150h+var_5020], rbx
0x101388a00  mov     eax, [rcx+10h]
0x101388a03  btr     eax, 8
0x101388a07  mov     [rcx+10h], eax
0x101388a0a  test    al, al
0x101388a0c  js      short loc_101388A1A
0x101388a0e  test    byte ptr [rcx+34h], 1
0x101388a12  jz      short loc_101388A1A
0x101388a14  lea     rdi, [rcx+48h]
0x101388a18  jmp     short loc_101388A24
0x101388a1a  mov     dl, 1; bool
0x101388a1c  call    ?GetRecordLong@BTreeRow@@IEAAPEAVRecord@@_N@Z; BTreeRow::GetRecordLong(bool)
0x101388a21  mov     rdi, rax
0x101388a24  xor     r8d, r8d
0x101388a27  mov     r13d, r8d
0x101388a2a  mov     [rbp+5150h+var_5104], r8d
0x101388a2e  lea     rdx, [rbp+5150h+var_5090]
0x101388a35  lea     rcx, [rdi+2]
0x101388a39  cmp     [rdi], r8w
0x101388a3d  jnz     short loc_101388A46
0x101388a3f  call    ?GetXdesTs@FixedVarRecord@@AEBA?AVXdesTs@@XZ; FixedVarRecord::GetXdesTs(void)
0x101388a44  jmp     short loc_101388A4B
0x101388a46  call    ?GetXdesTs@CDRecord@@AEBA?AVXdesTs@@XZ; CDRecord::GetXdesTs(void)
0x101388a4b  mov     r14d, [rbp+5150h+var_5090]
0x101388a52  mov     [rbp+5150h+var_50A0], r14d
0x101388a59  mov     [rbp+5150h+var_5034], r14d
0x101388a60  movzx   r15d, [rbp+5150h+var_508C]
0x101388a68  mov     [rbp+5150h+var_50B6], r15w
0x101388a70  mov     [rbp+5150h+var_5030], r15w
0x101388a78  mov     [rbp+5150h+var_50B4], r14d
0x101388a7f  mov     [rbp+5150h+var_50B0], r15w
0x101388a87  lea     rdx, [rbp+5150h+var_5066]
0x101388a8e  lea     rcx, [rdi+2]
0x101388a92  cmp     [rdi], r13w
0x101388a96  jnz     short loc_101388A9F
0x101388a98  call    ?GetVersionRecPtr@FixedVarRecord@@AEBA?AVVersionRecPtr@@XZ; FixedVarRecord::GetVersionRecPtr(void)
0x101388a9d  jmp     short loc_101388AA4
0x101388a9f  call    ?GetVersionRecPtr@CDRecord@@AEBA?AVVersionRecPtr@@XZ; CDRecord::GetVersionRecPtr(void)
0x101388aa4  mov     eax, [rbp+5150h+var_5066]
0x101388aaa  mov     [rbp+5150h+var_50D8], eax
0x101388aad  movzx   eax, [rbp+5150h+var_5062]
0x101388ab4  mov     [rbp+5150h+var_50D4], ax
0x101388ab8  movzx   eax, [rbp+5150h+var_5060]
0x101388abf  mov     [rbp+5150h+var_50D2], ax
0x101388ac3  mov     rax, [rdi+8]
0x101388ac7  movzx   ecx, byte ptr [rax]
0x101388aca  mov     eax, ecx
0x101388acc  shr     eax, 6
0x101388acf  and     eax, 1
0x101388ad2  shr     ecx, 1
0x101388ad4  and     ecx, 1
0x101388ad7  cmp     [rdi], r13w
0x101388adb  cmovz   ecx, eax
0x101388ade  test    ecx, ecx
0x101388ae0  jz      loc_10138FF93
0x101388ae6  cmp     cs:word_10318AB38, r15w
0x101388aee  jnz     short loc_101388AFD
0x101388af0  cmp     cs:?NullXdesId@@3VXdesId@@B, r14d; XdesId const NullXdesId
0x101388af7  jz      loc_10138FF93
0x101388afd  mov     r15, rbx
0x101388b00  lea     rcx, [rbx+19C8h]
0x101388b07  lea     r8, [rbp+5150h+var_50D8]
0x101388b0b  lea     rdx, [rbp+5150h+var_50B4]
0x101388b12  call    ?GetRowAbortState@XdesMgr@@QEAA?AW4XdesAbortState@@AEBVXdesId@@AEBVVersionRecPtr@@_N@Z; XdesMgr::GetRowAbortState(XdesId const &,VersionRecPtr const &,bool)
0x101388b17  test    eax, eax
0x101388b19  jz      loc_10138FF93
0x101388b1f  mov     edx, 0FFFFFFFFh
0x101388b24  mov     [rbp+5150h+var_4C70], dx
0x101388b2b  xor     ebx, ebx
0x101388b2d  mov     [rbp+5150h+var_4C68], rbx
0x101388b34  mov     [rbp+5150h+var_4C6C], ebx
0x101388b3a  mov     [rbp+5150h+var_4C52], rbx
0x101388b41  mov     [rbp+5150h+var_4C48], rbx
0x101388b48  mov     [rbp+5150h+var_4C60], rbx
0x101388b4f  mov     [rbp+5150h+var_4C3C], edx
0x101388b55  mov     [rbp+5150h+var_4BB0], dx
0x101388b5c  mov     [rbp+5150h+Source], rbx
0x101388b63  mov     [rbp+5150h+var_4BAC], ebx
0x101388b69  mov     [rbp+5150h+var_4B92], rbx
0x101388b70  mov     [rbp+5150h+var_4B88], rbx
0x101388b77  mov     [rbp+5150h+var_4BA0], rbx
0x101388b7e  mov     [rbp+5150h+var_4B7C], edx
0x101388b84  mov     [rbp+5150h+var_4B00], dx
0x101388b8b  mov     [rbp+5150h+var_4AF8], rbx
0x101388b92  mov     [rbp+5150h+var_4AFC], ebx
0x101388b98  mov     [rbp+5150h+var_4AE2], rbx
0x101388b9f  mov     [rbp+5150h+var_4AD8], rbx
0x101388ba6  mov     [rbp+5150h+var_4AF0], rbx
0x101388bad  mov     [rbp+5150h+var_4AC8], rbx
0x101388bb4  mov     [rbp+5150h+var_4AC0], ebx
0x101388bba  mov     [rbp+5150h+var_5148], dx
0x101388bbe  mov     [rbp+5150h+var_5140], rbx
0x101388bc2  mov     [rbp+5150h+var_5144], ebx
0x101388bc5  mov     [rbp+5150h+var_512A], rbx
0x101388bc9  mov     [rbp+5150h+var_5120], rbx
0x101388bcd  mov     [rbp+5150h+var_5138], rbx
0x101388bd1  mov     rax, [r12+28h]
0x101388bd6  mov     r13, [rax]
0x101388bd9  mov     [rbp+5150h+var_50F8], r13
0x101388bdd  mov     [rbp+5150h+var_5110], ebx
0x101388be0  mov     [rbp+5150h+var_510C], bl
0x101388be3  mov     byte ptr [rbp+5150h+var_50E4], bl
0x101388be6  mov     [rbp+5150h+var_5028], rbx
0x101388bed  mov     eax, ebx
0x101388bef  mov     [rbp+5150h+var_4BC0], rbx
0x101388bf6  mov     [rbp+5150h+var_4BB8], ebx
0x101388bfc  mov     [rbp+5150h+var_4BB4], bx
0x101388c03  xor     cl, cl
0x101388c05  mov     [rbp+5150h+var_5150], cl
0x101388c08  mov     [rbp+5150h+var_4A98], dx
0x101388c0f  mov     [rbp+5150h+var_4A90], rbx
0x101388c16  mov     [rbp+5150h+var_4A94], ebx
0x101388c1c  mov     [rbp+5150h+var_4A7A], rbx
0x101388c23  mov     [rbp+5150h+var_4A70], rbx
0x101388c2a  mov     [rbp+5150h+var_4A88], rbx
0x101388c31  mov     [rbp+5150h+var_4A64], edx
0x101388c37  mov     [rbp+5150h+var_510A], cl
0x101388c3a  cmp     [r15+2050h], cl
0x101388c41  jz      short loc_101388C60
0x101388c43  lea     edx, [rbx+0Ah]; int
0x101388c46  mov     ecx, 298h; unsigned int
0x101388c4b  lea     r8d, [rbx+2]; int
0x101388c4f  call    ?scierrlogwithstate@@YAXKHHZZ; scierrlogwithstate(ulong,int,int,...)
0x101388c54  mov     rcx, [r15+6B0h]; this
0x101388c5b  call    ?RaiseReadonlyDbError@DBTABLE@@QEBAXXZ; DBTABLE::RaiseReadonlyDbError(void)
0x101388c60  mov     [rbp+5150h+var_50A8], rbx
0x101388c67  mov     [rbp+5150h+var_5109], 1
0x101388c6b  mov     r14d, 1
0x101388c71  mov     rbx, [rbp+5150h+var_50C8]
0x101388c78  test    rbx, rbx
0x101388c7b  jnz     loc_101388D11
0x101388c81  mov     [rbp+5150h+var_5109], bl
0x101388c84  mov     rsi, [rsi+290h]
0x101388c8b  mov     rbx, [rbp+5150h+var_50A8]
0x101388c92  test    rbx, rbx
0x101388c95  jnz     short loc_101388CCA
0x101388c97  mov     rax, cs:__imp_?g_pAutoXactFactory@@3PEAVIAutoXactFactory@@EA; IAutoXactFactory * g_pAutoXactFactory
0x101388c9e  mov     rcx, [rax]
0x101388ca1  mov     rax, [rcx]
0x101388ca4  call    qword ptr [rax+8]
0x101388ca7  mov     rbx, rax
0x101388caa  mov     rcx, [rbp+5150h+var_50A8]
0x101388cb1  cmp     rcx, rax
0x101388cb4  jz      short loc_101388CC3
0x101388cb6  test    rcx, rcx
0x101388cb9  jz      short loc_101388CC3
0x101388cbb  mov     rax, [rcx]
0x101388cbe  mov     edx, r14d
0x101388cc1  call    qword ptr [rax]
0x101388cc3  mov     [rbp+5150h+var_50A8], rbx
0x101388cca  mov     rax, [rbx]
0x101388ccd  mov     byte ptr [rsp+51C0h+var_51A0], 0
0x101388cd2  mov     r9, rsi
0x101388cd5  mov     r8d, 36h ; '6'
0x101388cdb  lea     rdx, aBtreerowRevert; "BTreeRow::RevertFromVersion"
0x101388ce2  mov     rcx, rbx
0x101388ce5  call    qword ptr [rax+18h]
0x101388ce8  mov     rcx, [rbp+5150h+var_50A8]
0x101388cef  mov     rax, [rcx]
0x101388cf2  mov     rdx, r15
0x101388cf5  call    qword ptr [rax+58h]
0x101388cf8  mov     rbx, rax
0x101388cfb  mov     [rbp+5150h+var_50C8], rax
0x101388d02  mov     r8, [rax]
0x101388d05  xor     edx, edx
0x101388d07  mov     rcx, rax
0x101388d0a  call    qword ptr [r8+348h]
0x101388d11  mov     rdx, [rbx]
0x101388d14  mov     rcx, rbx
0x101388d17  call    qword ptr [rdx+8]
0x101388d1a  mov     [rbp+5150h+var_514F], al
0x101388d1d  mov     rdx, rdi; struct PageRow *
0x101388d20  lea     rcx, [rbp+5150h+var_4BB0]; this
0x101388d27  call    ?Clone@PageRow@@QEAAXAEBV1@@Z; PageRow::Clone(PageRow const &)
0x101388d2c  mov     rcx, cs:qword_10317B628
0x101388d33  mov     edx, [rcx+2Ch]
0x101388d36  shr     edx, 5
0x101388d39  test    r14b, dl
0x101388d3c  jz      short loc_101388D60
0x101388d3e  mov     rcx, [r12+18h]
0x101388d43  mov     rax, [rcx+30h]
0x101388d47  test    rax, rax
0x101388d4a  jz      short loc_101388D60
0x101388d4c  mov     rax, [rax]
0x101388d4f  test    rax, rax
0x101388d52  jz      short loc_101388D60
0x101388d54  cmp     rax, [r12+20h]
0x101388d59  jz      short loc_101388D60
0x101388d5b  mov     [r12+20h], rax
0x101388d60  mov     rax, [r12+20h]
0x101388d65  cmp     byte ptr [rax+2], 0
0x101388d69  jge     short loc_101388DB2
0x101388d6b  mov     rax, [rbp+5150h+Source]
0x101388d72  and     rax, 0FFFFFFFFFFFFE000h
0x101388d78  cmp     byte ptr [rax+2], 0
0x101388d7c  jge     short loc_101388DB2
0x101388d7e  mov     rsi, [rbp+5150h+var_4AC8]
0x101388d85  test    rsi, rsi
0x101388d88  jnz     short loc_101388DB9
0x101388d8a  mov     eax, 1FA0h
0x101388d8f  call    _alloca_probe
0x101388d94  sub     rsp, rax
0x101388d97  lea     rsi, [rsp+7160h+Destination]
0x101388d9c  mov     [rbp+5150h+var_4AC8], rsi
0x101388da3  mov     r14d, 1F9Eh
0x101388da9  mov     [rbp+5150h+var_4AC0], r14d
0x101388db0  jmp     short loc_101388DC0
0x101388db2  mov     rsi, [rbp+5150h+var_4AC8]
0x101388db9  mov     r14d, [rbp+5150h+var_4AC0]
0x101388dc0  mov     rcx, [rbp+5150h+Source]
0x101388dc7  mov     rax, rcx
0x101388dca  and     rax, 0FFFFFFFFFFFFE000h
0x101388dd0  mov     ebx, 4000h
0x101388dd5  mov     edi, 2000h
0x101388dda  mov     r12d, 9
0x101388de0  cmp     byte ptr [rax+2], 0
0x101388de4  jl      short loc_101388DF9
0x101388de6  lea     r14, [rbp+5150h+var_4BB0]
0x101388ded  lea     rbx, [rbp+5150h+var_4BAE]
0x101388df4  jmp     loc_101389687
0x101388df9  movzx   eax, [rbp+5150h+var_4BB0]
0x101388e00  mov     [rbp+5150h+var_4B00], ax
0x101388e07  test    ax, ax
0x101388e0a  jnz     loc_10138960C
0x101388e10  mov     edx, [rbp+5150h+var_4BAC]
0x101388e16  test    edx, edx
0x101388e18  jnz     loc_1013894A3
0x101388e1e  xor     r9d, r9d
0x101388e21  mov     [rbp+5150h+var_4BAE], r9w
0x101388e29  mov     edx, dword ptr [rbp+5150h+var_4BA0]
0x101388e2f  mov     dword ptr [rbp+5150h+var_4BA0+4], edx
0x101388e35  mov     rcx, [rbp+5150h+Source]
0x101388e3c  test    byte ptr [rcx], 10h
0x101388e3f  jz      short loc_101388E56
0x101388e41  movzx   ecx, word ptr [rdx+rcx]
0x101388e45  add     ecx, 7
0x101388e48  shr     ecx, 3
0x101388e4b  add     edx, 2
0x101388e4e  add     edx, ecx
0x101388e50  mov     dword ptr [rbp+5150h+var_4BA0+4], edx
0x101388e56  mov     rcx, [rbp+5150h+Source]
0x101388e5d  test    byte ptr [rcx], 20h
0x101388e60  jz      loc_10138924A
0x101388e66  mov     edi, edx
0x101388e68  add     rdi, rcx
0x101388e6b  movzx   eax, word ptr [rdi]
0x101388e6e  mov     [rbp+5150h+var_4B94], ax
0x101388e75  test    ax, ax
0x101388e78  jnz     loc_101388F32
0x101388e7e  cmp     cs:byte_10316E8D7, r9b
0x101388e85  jnz     short loc_101388E94
0x101388e87  test    byte ptr cs:qword_10317B120, 1
0x101388e8e  jz      loc_101388F1E
0x101388e94  mov     r8, gs:58h
0x101388e9d  mov     rax, cs:__imp_SystemThread_TlsIndex
0x101388ea4  mov     ecx, [rax]
0x101388ea6  mov     rax, cs:__imp_SystemThread_TlsOffset
0x101388ead  mov     edx, [rax]
0x101388eaf  add     rdx, [r8+rcx*8]
0x101388eb3  mov     rax, [rdx+8]
0x101388eb7  test    rax, rax
0x101388eba  jz      short loc_101388F1E
0x101388ebc  mov     rax, [rax+60h]
0x101388ec0  test    rax, rax
0x101388ec3  jz      short loc_101388F1E
0x101388ec5  cmp     [rax+499h], r9b
0x101388ecc  jz      short loc_101388F1E
0x101388ece  cmp     cs:byte_10316E7C7, r9b
0x101388ed5  jnz     short loc_101388EFA
0x101388ed7  test    byte ptr cs:qword_10317B120, 2
0x101388ede  jnz     short loc_101388EFA
0x101388ee0  mov     edx, 44h ; 'D'
0x101388ee5  lea     ecx, [rdx-22h]
0x101388ee8  mov     r9d, 3EBh
0x101388eee  lea     r8d, [rdx-2Fh]
0x101388ef2  call    cs:__imp_?ex_raise@@YAHHHHHZZ; ex_raise(int,int,int,int,...)
  ... truncated ...
```
