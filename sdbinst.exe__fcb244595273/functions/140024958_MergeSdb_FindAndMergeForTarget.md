# MergeSdb_FindAndMergeForTarget

- ea: `0x140024958`
- end: `0x1400273fa`
- name: `MergeSdb_FindAndMergeForTarget`
- size: `10914`
- prototype: `__int64 __fastcall(wchar_t *Str, wchar_t *String1, unsigned int, int)`
- caller_count: `1`
- callee_count: `46`
- tags: `file_ops, authz_impersonation, registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x140008500`

## callees

- `0x1400031b8`
- `0x140006f60`
- `0x140007024`
- `0x14001008c`
- `0x14001a678`
- `0x140020cb8`
- `0x140020f9c`
- `0x1400213f0`
- `0x140021670`
- `0x140021934`
- `0x140021ee4`
- `0x140022090`
- `0x140022210`
- `0x1400222f4`
- `0x14002232c`
- `0x140022390`
- `0x1400223f0`
- `0x1400224f0`
- `0x14002257c`
- `0x14002269c`
- `0x140022744`
- `0x1400230fc`
- `0x140023334`
- `0x140023458`
- `0x140023638`
- `0x1400238c0`
- `0x1400242ac`
- `0x1400244cc`
- `0x140024564`
- `0x14002460c`
- `0x14002469c`
- `0x1400247f4`
- `0x1400248cc`
- `0x140024958`
- `0x140027400`
- `0x140029710`
- `0x14002a044`
- `0x14002a33c`
- `0x14002a494`
- `0x14002adfc`
- `0x14002be40`
- `0x14002c0c0`
- `0x14002c36c`
- `0x14002d1dc`
- `0x14002d418`
- `0x14002e420`

## import_xrefs

- `ADVAPI32!RegOpenKeyExW` at `0x140025026`
- `ADVAPI32!RegOpenKeyExW` at `0x140025026`
- `ADVAPI32!RegQueryInfoKeyW` at `0x140025298`
- `ADVAPI32!RegQueryInfoKeyW` at `0x140025298`
- `ADVAPI32!RegCloseKey` at `0x140025065`
- `ADVAPI32!RegCloseKey` at `0x1400250c1`
- `ADVAPI32!RegCloseKey` at `0x1400250f3`
- `ADVAPI32!RegCloseKey` at `0x14002519d`
- `ADVAPI32!RegCloseKey` at `0x1400251cf`
- `ADVAPI32!RegCloseKey` at `0x1400252f0`
- `ADVAPI32!RegCloseKey` at `0x140025322`
- `ADVAPI32!RegCloseKey` at `0x140025491`
- `ADVAPI32!RegCloseKey` at `0x1400254c3`
- `ADVAPI32!RegCloseKey` at `0x14002579b`
- `ADVAPI32!RegCloseKey` at `0x1400257cd`
- `ADVAPI32!RegCloseKey` at `0x14002595c`
- `ADVAPI32!RegCloseKey` at `0x14002598e`
- `ADVAPI32!RegCloseKey` at `0x140025b25`
- `ADVAPI32!RegCloseKey` at `0x140025b57`
- `ADVAPI32!RegCloseKey` at `0x140025c40`
- `ADVAPI32!RegCloseKey` at `0x140025c72`
- `ADVAPI32!RegCloseKey` at `0x140025e13`
- `ADVAPI32!RegCloseKey` at `0x140025e45`
- `ADVAPI32!RegCloseKey` at `0x140026242`
- `ADVAPI32!RegCloseKey` at `0x140026274`
- `ADVAPI32!RegCloseKey` at `0x140026665`
- `ADVAPI32!RegCloseKey` at `0x14002668b`
- `ADVAPI32!RegCloseKey` at `0x1400267e4`
- `ADVAPI32!RegCloseKey` at `0x140026806`
- `ADVAPI32!RegCloseKey` at `0x140026983`
- `ADVAPI32!RegCloseKey` at `0x1400269a5`
- `ADVAPI32!RegCloseKey` at `0x140026a63`
- `ADVAPI32!RegCloseKey` at `0x140026a85`
- `ADVAPI32!RegCloseKey` at `0x140026cb0`
- `ADVAPI32!RegCloseKey` at `0x140026cd2`
- `ADVAPI32!RegCloseKey` at `0x140026e03`
- `ADVAPI32!RegCloseKey` at `0x140026e25`
- `ADVAPI32!RegCloseKey` at `0x140026f36`
- `ADVAPI32!RegCloseKey` at `0x140026f68`
- `ADVAPI32!RegCloseKey` at `0x140027091`
- `ADVAPI32!RegCloseKey` at `0x1400270c3`
- `ADVAPI32!RegCloseKey` at `0x1400271a3`
- `ADVAPI32!RegCloseKey` at `0x1400271d5`
- `ADVAPI32!RegCloseKey` at `0x1400272ee`
- `ADVAPI32!RegCloseKey` at `0x140025065`
- `ADVAPI32!RegCloseKey` at `0x1400250c1`
- `ADVAPI32!RegCloseKey` at `0x1400250f3`
- `ADVAPI32!RegCloseKey` at `0x14002519d`
- `ADVAPI32!RegCloseKey` at `0x1400251cf`
- `ADVAPI32!RegCloseKey` at `0x1400252f0`
- `ADVAPI32!RegCloseKey` at `0x140025322`
- `ADVAPI32!RegCloseKey` at `0x140025491`
- `ADVAPI32!RegCloseKey` at `0x1400254c3`
- `ADVAPI32!RegCloseKey` at `0x14002579b`
- `ADVAPI32!RegCloseKey` at `0x1400257cd`
- `ADVAPI32!RegCloseKey` at `0x14002595c`
- `ADVAPI32!RegCloseKey` at `0x14002598e`
- `ADVAPI32!RegCloseKey` at `0x140025b25`
- `ADVAPI32!RegCloseKey` at `0x140025b57`
- `ADVAPI32!RegCloseKey` at `0x140025c40`
- `ADVAPI32!RegCloseKey` at `0x140025c72`
- `ADVAPI32!RegCloseKey` at `0x140025e13`
- `ADVAPI32!RegCloseKey` at `0x140025e45`
- `ADVAPI32!RegCloseKey` at `0x140026242`
- `ADVAPI32!RegCloseKey` at `0x140026274`
- `ADVAPI32!RegCloseKey` at `0x140026665`
- `ADVAPI32!RegCloseKey` at `0x14002668b`
- `ADVAPI32!RegCloseKey` at `0x1400267e4`
- `ADVAPI32!RegCloseKey` at `0x140026806`
- `ADVAPI32!RegCloseKey` at `0x140026983`
- `ADVAPI32!RegCloseKey` at `0x1400269a5`
- `ADVAPI32!RegCloseKey` at `0x140026a63`
- `ADVAPI32!RegCloseKey` at `0x140026a85`
- `ADVAPI32!RegCloseKey` at `0x140026cb0`
- `ADVAPI32!RegCloseKey` at `0x140026cd2`
- `ADVAPI32!RegCloseKey` at `0x140026e03`
- `ADVAPI32!RegCloseKey` at `0x140026e25`
- `ADVAPI32!RegCloseKey` at `0x140026f36`
- `ADVAPI32!RegCloseKey` at `0x140026f68`
- `ADVAPI32!RegCloseKey` at `0x140027091`
- `ADVAPI32!RegCloseKey` at `0x1400270c3`
- `ADVAPI32!RegCloseKey` at `0x1400271a3`
- `ADVAPI32!RegCloseKey` at `0x1400271d5`
- `ADVAPI32!RegCloseKey` at `0x1400272ee`
- `KERNEL32!GetFileAttributesW` at `0x14002641c`
- `KERNEL32!GetFileAttributesW` at `0x140026499`
- `KERNEL32!GetFileAttributesW` at `0x14002641c`
- `KERNEL32!GetFileAttributesW` at `0x140026499`
- `KERNEL32!GetLastError` at `0x140024b9c`
- `KERNEL32!GetLastError` at `0x140024c63`
- `KERNEL32!GetLastError` at `0x140024cbb`
- `KERNEL32!GetLastError` at `0x140024e20`
- `KERNEL32!GetLastError` at `0x140024b9c`
- `KERNEL32!GetLastError` at `0x140024c63`
- `KERNEL32!GetLastError` at `0x140024cbb`
- `KERNEL32!GetLastError` at `0x140024e20`
- `KERNEL32!GetProcessHeap` at `0x140024ba4`
- `KERNEL32!GetProcessHeap` at `0x140024c05`
- `KERNEL32!GetProcessHeap` at `0x140024c26`
- `KERNEL32!GetProcessHeap` at `0x140024c6b`
- `KERNEL32!GetProcessHeap` at `0x140024cc3`
- `KERNEL32!GetProcessHeap` at `0x140024d70`
- `KERNEL32!GetProcessHeap` at `0x140024d8d`
- `KERNEL32!GetProcessHeap` at `0x140024e28`
- `KERNEL32!GetProcessHeap` at `0x140024ec8`
- `KERNEL32!GetProcessHeap` at `0x140024ee1`
- `KERNEL32!GetProcessHeap` at `0x140024ef5`
- `KERNEL32!GetProcessHeap` at `0x140024f12`
- `KERNEL32!GetProcessHeap` at `0x140024f3b`
- `KERNEL32!GetProcessHeap` at `0x140024f58`
- `KERNEL32!GetProcessHeap` at `0x1400250d5`
- `KERNEL32!GetProcessHeap` at `0x14002510e`
- `KERNEL32!GetProcessHeap` at `0x140025127`
- `KERNEL32!GetProcessHeap` at `0x140025140`
- `KERNEL32!GetProcessHeap` at `0x140025154`
- `KERNEL32!GetProcessHeap` at `0x1400251b1`
- `KERNEL32!GetProcessHeap` at `0x1400251ea`
- `KERNEL32!GetProcessHeap` at `0x140025203`
- `KERNEL32!GetProcessHeap` at `0x14002521c`
- `KERNEL32!GetProcessHeap` at `0x140025239`
- `KERNEL32!GetProcessHeap` at `0x140025304`
- `KERNEL32!GetProcessHeap` at `0x14002533d`
- `KERNEL32!GetProcessHeap` at `0x140025356`
- `KERNEL32!GetProcessHeap` at `0x14002536f`
- `KERNEL32!GetProcessHeap` at `0x14002538c`
- `KERNEL32!GetProcessHeap` at `0x1400253b9`
- `KERNEL32!GetProcessHeap` at `0x140025473`
- `KERNEL32!GetProcessHeap` at `0x1400254a5`
- `KERNEL32!GetProcessHeap` at `0x1400254de`
- `KERNEL32!GetProcessHeap` at `0x1400254f7`
- `KERNEL32!GetProcessHeap` at `0x140025510`
- `KERNEL32!GetProcessHeap` at `0x14002552d`
- `KERNEL32!GetProcessHeap` at `0x140025556`
- `KERNEL32!GetProcessHeap` at `0x140025573`
- `KERNEL32!GetProcessHeap` at `0x14002567b`
- `KERNEL32!GetProcessHeap` at `0x140025698`
- `KERNEL32!GetProcessHeap` at `0x1400256e8`
- `KERNEL32!GetProcessHeap` at `0x140025769`
- `KERNEL32!GetProcessHeap` at `0x14002577d`
- `KERNEL32!GetProcessHeap` at `0x1400257af`
- `KERNEL32!GetProcessHeap` at `0x1400257e8`
- `KERNEL32!GetProcessHeap` at `0x140025801`
- `KERNEL32!GetProcessHeap` at `0x14002581a`
- `KERNEL32!GetProcessHeap` at `0x140025837`
- `KERNEL32!GetProcessHeap` at `0x140025860`
- `KERNEL32!GetProcessHeap` at `0x14002587d`
- `KERNEL32!GetProcessHeap` at `0x14002592a`
- `KERNEL32!GetProcessHeap` at `0x14002593e`
- `KERNEL32!GetProcessHeap` at `0x140025970`
- `KERNEL32!GetProcessHeap` at `0x1400259a9`
- `KERNEL32!GetProcessHeap` at `0x1400259c2`
- `KERNEL32!GetProcessHeap` at `0x1400259db`
- `KERNEL32!GetProcessHeap` at `0x1400259ef`
- `KERNEL32!GetProcessHeap` at `0x140025a18`
- `KERNEL32!GetProcessHeap` at `0x140025a35`
- `KERNEL32!GetProcessHeap` at `0x140025af3`
- `KERNEL32!GetProcessHeap` at `0x140025b07`
- `KERNEL32!GetProcessHeap` at `0x140025b39`
- `KERNEL32!GetProcessHeap` at `0x140025b72`
- `KERNEL32!GetProcessHeap` at `0x140025b86`
- `KERNEL32!GetProcessHeap` at `0x140025b9f`
- `KERNEL32!GetProcessHeap` at `0x140025bbc`
- `KERNEL32!GetProcessHeap` at `0x140025c0e`
- `KERNEL32!GetProcessHeap` at `0x140025c22`
- `KERNEL32!GetProcessHeap` at `0x140025c54`
- `KERNEL32!GetProcessHeap` at `0x140025c8d`
- `KERNEL32!GetProcessHeap` at `0x140025ca1`
- `KERNEL32!GetProcessHeap` at `0x140025cba`
- `KERNEL32!GetProcessHeap` at `0x140025cd7`
- `KERNEL32!GetProcessHeap` at `0x140025de1`
- `KERNEL32!GetProcessHeap` at `0x140025df5`
- `KERNEL32!GetProcessHeap` at `0x140025e27`
- `KERNEL32!GetProcessHeap` at `0x140025e60`
- `KERNEL32!GetProcessHeap` at `0x140025e79`
- `KERNEL32!GetProcessHeap` at `0x140025e96`
- `KERNEL32!GetProcessHeap` at `0x140026179`
- `KERNEL32!GetProcessHeap` at `0x1400261e4`
- `KERNEL32!GetProcessHeap` at `0x140026210`
- `KERNEL32!GetProcessHeap` at `0x140026224`
- `KERNEL32!GetProcessHeap` at `0x140026256`
- `KERNEL32!GetProcessHeap` at `0x14002628f`
- `KERNEL32!GetProcessHeap` at `0x140026536`
- `KERNEL32!GetProcessHeap` at `0x140026ebe`
- `KERNEL32!GetProcessHeap` at `0x140026ed8`
- `KERNEL32!GetProcessHeap` at `0x140026f04`
- `KERNEL32!GetProcessHeap` at `0x140026f18`
- `KERNEL32!GetProcessHeap` at `0x140026f4a`
- `KERNEL32!GetProcessHeap` at `0x140026f83`
- `KERNEL32!GetProcessHeap` at `0x14002705f`
- `KERNEL32!GetProcessHeap` at `0x140027073`
- `KERNEL32!GetProcessHeap` at `0x1400270a5`
- `KERNEL32!GetProcessHeap` at `0x1400270de`
- `KERNEL32!GetProcessHeap` at `0x1400270f2`
- `KERNEL32!GetProcessHeap` at `0x14002710b`
- `KERNEL32!GetProcessHeap` at `0x140027171`
- `KERNEL32!GetProcessHeap` at `0x140027185`
- `KERNEL32!GetProcessHeap` at `0x1400271b7`
- `KERNEL32!GetProcessHeap` at `0x1400271f0`
- `KERNEL32!GetProcessHeap` at `0x140027209`
- `KERNEL32!GetProcessHeap` at `0x140027222`

## string_xrefs

- `0x1400249cc`: `Failed to remove merged sdb files no longer in use (%d)`
- `0x140024abb`: `Failed to remove merge input sdb files no longer registered for use (%d)`
- `0x140024d3e`: `Failed to read information from orignal sdb '%S' (%d)`
- `0x140024be4`: `Failed to expand / concat full sdb file path (%d)`
- `0x1400272ae`: `Failed to get the merge target key path (%d)`
- `0x140024e96`: `Failed to read information from orignal manifested stub sdb '%S' (%d)`
- `0x14002509a`: `Unable to open SdbUpdates key (%d)`
- `0x1400256c3`: `Unable to open SdbUpdates key (%d)`
- `0x140025ad3`: `Unable to open SdbUpdates key (%d)`
- `0x140025fd6`: `Unable to open SdbUpdates key (%d)`
- `0x1400263ad`: `Unable to open SdbUpdates key (%d)`
- `0x140026b7a`: `Unable to open SdbUpdates key (%d)`
- `0x140026fbb`: `Unable to open SdbUpdates key (%d)`
- `0x14002703a`: `Unable to open SdbUpdates key (%d)`
- `0x14002503e`: `Failed to open the target key (%d)`
- `0x140025441`: `RegDeleteValueW failed (%d)`
- `0x140025181`: `Failed to delete redirect value from SdbUpdates (%d)`
- `0x1400258ef`: `Failed to delete redirect value from SdbUpdates (%d)`
- `0x140026409`: `Failed to delete redirect value from SdbUpdates (%d)`
- `0x140027000`: `Failed to delete redirect value from SdbUpdates (%d)`
- `0x140025bee`: `Failed to delete stub redirect value from SdbUpdates (%d)`
- `0x14002602e`: `Failed to delete stub redirect value from SdbUpdates (%d)`
- `0x140026c2c`: `Failed to delete stub redirect value from SdbUpdates (%d)`
- `0x14002714d`: `Failed to delete stub redirect value from SdbUpdates (%d)`
- `0x140025732`: `Failed to read merge disabled registry value (%d)`
- `0x140025f8c`: `Redirected merge sdb is already %S up-to-date with %d merges: '%S' -> '%S'`
- `0x14002635f`: `Redirected merge sdb stub is already %S up-to-date with %d merges: '%S' -> '%S'`
- `0x140026092`: `Failed to load sdb file information from redirected manifested stub sdb file (%d)`
- `0x140026434`: `Failed to clean up temp directory (%d)`
- `0x1400264c0`: `Failed to clean up temp directory (%d)`
- `0x1400261b9`: `Failed to get temp dir (%d)`
- `0x14002650c`: `Failed to create apppatch temp path (%d)`
- `0x140026e99`: `Failed to expand apppatch temp path (%d)`
- `0x1400265fc`: `Failed to copy sdb to temp dir (%d)`
- `0x140026d9a`: `Failed to get unique temp file name (%d)`
- `0x140026d58`: `Failed to copy sdb path to redirect path (%d)`
- `0x140026d3a`: `Failed to concat the registered filename to the redirect full path (%d)`
- `0x1400269ec`: `Failed to find the last backslash in the original sdb full path.`
- `0x140026b26`: `Failed to delete apppatch temp path, swallowing (%d)`
- `0x140026ae5`: `Failed to move merged sdb to appPatch dir (%d)`
- `0x140026bb1`: `Failed to read the merge version from SdbUpdates key (%d)`
- `0x140026b55`: `Unable to copy ACLs from parent (%d)`
- `0x140026bf4`: `Failed to write final data transaction to SdbUpdates key (%d)`
- `0x14002646b`: `%SYSTEMROOT%\AppPatch\Temp`

## pseudocode

```c
__int64 __fastcall MergeSdb_FindAndMergeForTarget(wchar_t *Str, wchar_t *String1, unsigned int a3, int a4)
{
  const wchar_t *v4; // rbx
  unsigned int v6; // eax
  __int64 v7; // rcx
  unsigned int v8; // ebx
  int v10; // r15d
  __int64 *v11; // rsi
  const wchar_t *v12; // rdx
  size_t v13; // r14
  int v14; // eax
  wchar_t *v15; // rsi
  int v16; // eax
  __int64 v17; // rcx
  __int64 v18; // rax
  void *v19; // r14
  void *v20; // rsi
  DWORD LastError; // ebx
  HANDLE v22; // rax
  void *v23; // rdi
  HANDLE ProcessHeap; // rax
  WCHAR *v25; // rdi
  HANDLE v26; // rax
  WCHAR *v27; // rbx
  int v28; // eax
  unsigned int v29; // esi
  void *v30; // rbx
  HANDLE v31; // rax
  WCHAR *v32; // rbx
  HANDLE v33; // rax
  wchar_t *v34; // rdi
  WCHAR *v35; // rsi
  wchar_t *v36; // rax
  unsigned __int16 *v37; // rsi
  unsigned __int16 *v38; // r14
  DWORD v39; // ebx
  HANDLE v40; // rax
  __int64 v41; // r8
  int v42; // eax
  unsigned int v43; // r12d
  unsigned int v44; // r14d
  unsigned __int16 *v45; // rbx
  HANDLE v46; // rax
  HANDLE v47; // rax
  HANDLE v48; // rax
  WCHAR *v49; // rbx
  HANDLE v50; // rax
  void *v51; // rbx
  HANDLE v52; // rax
  WCHAR *v53; // rbx
  HANDLE v54; // rax
  __int64 v55; // rax
  __int64 v56; // rcx
  __int64 v57; // r14
  void *v58; // rbx
  __int64 v59; // rcx
  int MergeTargetRegistryKeyPathForTarget; // eax
  LSTATUS v61; // eax
  __int64 v62; // rdx
  __int64 v63; // r8
  const char *v64; // r9
  __int64 v65; // r8
  PCWSTR v66; // r14
  const char *v67; // r9
  __int64 v68; // r8
  HANDLE v69; // rax
  unsigned __int16 *v70; // rbx
  HANDLE v71; // rax
  HANDLE v72; // rax
  HANDLE v73; // rax
  HANDLE v74; // rax
  WCHAR *v75; // r8
  HANDLE v76; // rax
  unsigned __int16 *v77; // rbx
  HANDLE v78; // rax
  HANDLE v79; // rax
  HANDLE v80; // rax
  HANDLE v81; // rax
  void *v82; // r8
  DWORD v83; // eax
  WCHAR *v84; // r12
  __int64 v85; // r8
  HANDLE v86; // rax
  unsigned __int16 *v87; // rbx
  HANDLE v88; // rax
  HANDLE v89; // rax
  HANDLE v90; // rax
  WCHAR *v91; // rbx
  HANDLE v92; // rax
  LPVOID v93; // rbx
  HANDLE v94; // rax
  void *v95; // r8
  unsigned int v96; // eax
  unsigned int v97; // eax
  const unsigned __int16 *v98; // rdx
  unsigned int v99; // eax
  unsigned __int16 *v100; // rcx
  HANDLE v101; // rax
  HANDLE v102; // rax
  unsigned __int16 *v103; // rbx
  HANDLE v104; // rax
  HANDLE v105; // rax
  HANDLE v106; // rax
  PCWSTR v107; // rbx
  HANDLE v108; // rax
  void *v109; // r8
  void *v110; // rbx
  HANDLE v111; // rax
  WCHAR *v112; // rbx
  HANDLE v113; // rax
  unsigned __int16 *v114; // rcx
  unsigned int v115; // eax
  int v116; // eax
  void *v117; // r14
  const WCHAR *j; // rdx
  void *v119; // r14
  HANDLE v120; // rax
  HANDLE v121; // rax
  int v122; // eax
  const unsigned __int16 *v123; // rdx
  HANDLE v124; // rax
  unsigned int RegValue; // eax
  __int64 v126; // rdx
  __int64 v127; // r8
  __int64 v128; // r11
  void *v129; // rcx
  HANDLE v130; // rax
  HANDLE v131; // rax
  HANDLE v132; // rax
  unsigned __int16 *v133; // rbx
  HANDLE v134; // rax
  HANDLE v135; // rax
  HANDLE v136; // rax
  PCWSTR v137; // rbx
  HANDLE v138; // rax
  void *v139; // r8
  void *v140; // rbx
  HANDLE v141; // rax
  WCHAR *v142; // rbx
  HANDLE v143; // rax
  int v144; // eax
  WCHAR *v145; // r15
  unsigned int v146; // eax
  void *v147; // rcx
  HANDLE v148; // rax
  HANDLE v149; // rax
  HANDLE v150; // rax
  unsigned __int16 *v151; // rbx
  HANDLE v152; // rax
  HANDLE v153; // rax
  HANDLE v154; // rax
  HANDLE v155; // rax
  void *v156; // rbx
  HANDLE v157; // rax
  WCHAR *v158; // rbx
  HANDLE v159; // rax
  void *v160; // rcx
  void *v161; // rcx
  int v162; // eax
  HANDLE v163; // rax
  HANDLE v164; // rax
  HANDLE v165; // rax
  unsigned __int16 *v166; // rbx
  HANDLE v167; // rax
  HANDLE v168; // rax
  HANDLE v169; // rax
  unsigned int v170; // eax
  HANDLE v171; // rax
  HANDLE v172; // rax
  HANDLE v173; // rax
  unsigned __int16 *v174; // rbx
  HANDLE v175; // rax
  HANDLE v176; // rax
  HANDLE v177; // rax
  __int64 v178; // rcx
  const WCHAR **v179; // rdx
  unsigned int v180; // eax
  const WCHAR **v181; // rax
  unsigned __int64 v182; // rax
  HANDLE v183; // rax
  HANDLE v184; // rax
  HANDLE v185; // rax
  unsigned __int16 *v186; // rbx
  HANDLE v187; // rax
  HANDLE v188; // rax
  HANDLE v189; // rax
  char v190; // r8
  const WCHAR *v191; // rax
  __int64 v192; // r9
  const WCHAR *v193; // rcx
  char matched; // al
  const wchar_t *v195; // rdx
  __int64 v196; // rdx
  __int64 v197; // r8
  unsigned int v198; // eax
  const char *v199; // r9
  __int64 v200; // r8
  unsigned int v201; // eax
  const WCHAR **v202; // rax
  unsigned __int64 v203; // rax
  char v204; // dl
  __int64 v205; // r8
  void *v206; // r13
  HANDLE v207; // rax
  unsigned int v208; // eax
  WCHAR *v209; // r13
  HANDLE v210; // rax
  HANDLE v211; // rax
  HANDLE v212; // rax
  HANDLE v213; // rax
  unsigned __int16 *v214; // rbx
  HANDLE v215; // rax
  const WCHAR *v216; // r8
  __int64 v217; // r9
  const WCHAR *v218; // rax
  const WCHAR *v219; // rcx
  char v220; // al
  const wchar_t *v221; // rdx
  __int64 v222; // rdx
  __int64 v223; // r8
  unsigned int v224; // eax
  const char *v225; // r9
  __int64 v226; // r8
  int v227; // eax
  int v228; // eax
  int v229; // ecx
  WCHAR *v230; // rbx
  int v231; // eax
  BOOL DirectoryW; // eax
  unsigned int v233; // edi
  HANDLE v234; // rax
  unsigned int v235; // ebx
  __int64 v236; // r8
  char v237; // r12
  const WCHAR *v238; // rcx
  BOOL v239; // eax
  __int64 v240; // r8
  int UniqueTempDirectoryFileName; // eax
  NTSTATUS v242; // ebx
  ULONG v243; // eax
  BOOL v244; // eax
  __int64 v245; // r8
  NTSTATUS v246; // ebx
  const char *v247; // r9
  unsigned int v248; // eax
  int v249; // r12d
  PCWSTR v250; // rax
  __int64 v251; // rcx
  unsigned __int64 v252; // rbx
  const unsigned __int16 *v253; // r8
  int v254; // eax
  wchar_t *v255; // rax
  int v256; // eax
  BOOL v257; // eax
  const char *v258; // r9
  __int64 v259; // r8
  unsigned __int16 *v260; // rdx
  BOOL v261; // eax
  unsigned int v262; // eax
  __int64 v263; // rdx
  __int64 v264; // r8
  unsigned int v265; // eax
  unsigned int v266; // eax
  unsigned __int16 *v267; // r8
  unsigned int v268; // eax
  int v269; // eax
  HANDLE v270; // rax
  HANDLE v271; // rax
  HANDLE v272; // rax
  HANDLE v273; // rax
  HANDLE v274; // rax
  unsigned __int16 *v275; // rbx
  HANDLE v276; // rax
  unsigned int v277; // eax
  const char *v278; // r9
  __int64 v279; // r8
  unsigned int v280; // eax
  const char *v281; // r9
  __int64 v282; // r8
  HANDLE v283; // rax
  HANDLE v284; // rax
  HANDLE v285; // rax
  unsigned __int16 *v286; // rbx
  HANDLE v287; // rax
  HANDLE v288; // rax
  HANDLE v289; // rax
  HANDLE v290; // rax
  HANDLE v291; // rax
  HANDLE v292; // rax
  unsigned __int16 *v293; // rbx
  HANDLE v294; // rax
  HANDLE v295; // rax
  HANDLE v296; // rax
  void *v297; // rbx
  HANDLE v298; // rax
  WCHAR *v299; // rbx
  HANDLE v300; // rax
  HANDLE v301; // rax
  unsigned __int16 *v302; // rbx
  HANDLE v303; // rax
  HANDLE v304; // rax
  HANDLE v305; // rax
  PCWSTR v306; // rbx
  void *v307; // rbx
  HANDLE v308; // rax
  WCHAR *v309; // rbx
  HANDLE v310; // rax
  HANDLE v311; // rax
  PHKEY phkResult; // [rsp+20h] [rbp-E0h]
  PHKEY phkResulta; // [rsp+20h] [rbp-E0h]
  PHKEY phkResultb; // [rsp+20h] [rbp-E0h]
  PHKEY phkResultc; // [rsp+20h] [rbp-E0h]
  LPDWORD lpcbMaxSubKeyLen; // [rsp+28h] [rbp-D8h]
  char v317; // [rsp+60h] [rbp-A0h] BYREF
  _BYTE v318[3]; // [rsp+61h] [rbp-9Fh] BYREF
  unsigned int i; // [rsp+64h] [rbp-9Ch] BYREF
  HKEY v320; // [rsp+68h] [rbp-98h] BYREF
  unsigned int TempPath2W; // [rsp+70h] [rbp-90h]
  HKEY hKey; // [rsp+78h] [rbp-88h] BYREF
  PCWSTR FileName; // [rsp+80h] [rbp-80h] BYREF
  LPCWSTR lpFileName; // [rsp+88h] [rbp-78h] BYREF
  LPVOID lpMem; // [rsp+90h] [rbp-70h] BYREF
  unsigned __int16 *v326; // [rsp+98h] [rbp-68h] BYREF
  const WCHAR **v327; // [rsp+A0h] [rbp-60h] BYREF
  unsigned __int64 v328; // [rsp+A8h] [rbp-58h]
  char v329; // [rsp+B0h] [rbp-50h]
  __int64 v330; // [rsp+C0h] [rbp-40h] BYREF
  unsigned __int64 v331; // [rsp+C8h] [rbp-38h]
  LPCWSTR v332; // [rsp+D0h] [rbp-30h] BYREF
  LPCWSTR lpNewFileName; // [rsp+D8h] [rbp-28h] BYREF
  void *v334; // [rsp+E0h] [rbp-20h] BYREF
  void *v335; // [rsp+E8h] [rbp-18h] BYREF
  void *v336; // [rsp+F0h] [rbp-10h] BYREF
  LPVOID v337; // [rsp+F8h] [rbp-8h] BYREF
  PCWSTR v338; // [rsp+100h] [rbp+0h] BYREF
  int v339; // [rsp+108h] [rbp+8h]
  DWORD cbMaxSubKeyLen; // [rsp+10Ch] [rbp+Ch] BYREF
  PCWSTR v341; // [rsp+110h] [rbp+10h] BYREF
  DWORD cbMaxValueNameLen; // [rsp+118h] [rbp+18h] BYREF
  HKEY *v343; // [rsp+120h] [rbp+20h] BYREF
  DWORD cSubKeys; // [rsp+128h] [rbp+28h] BYREF
  _QWORD v345[2]; // [rsp+130h] [rbp+30h] BYREF
  DWORD cValues; // [rsp+140h] [rbp+40h] BYREF
  unsigned int v347[3]; // [rsp+144h] [rbp+44h] BYREF
  LPVOID v348[2]; // [rsp+150h] [rbp+50h] BYREF
  const unsigned __int16 *v349; // [rsp+160h] [rbp+60h] BYREF
  unsigned int v350; // [rsp+168h] [rbp+68h]
  wchar_t *Stra[2]; // [rsp+170h] [rbp+70h] BYREF
  LPVOID v352; // [rsp+180h] [rbp+80h] BYREF
  const WCHAR *v353; // [rsp+188h] [rbp+88h] BYREF
  void *v354; // [rsp+190h] [rbp+90h] BYREF
  unsigned __int16 *v355; // [rsp+198h] [rbp+98h] BYREF
  LPVOID v356; // [rsp+1A0h] [rbp+A0h] BYREF
  void *v357; // [rsp+1A8h] [rbp+A8h] BYREF
  __int64 v358; // [rsp+1B0h] [rbp+B0h] BYREF
  _QWORD v359[8]; // [rsp+1C0h] [rbp+C0h] BYREF
  __int64 v360; // [rsp+200h] [rbp+100h]
  __int64 v361; // [rsp+220h] [rbp+120h]
  _BYTE v362[64]; // [rsp+250h] [rbp+150h] BYREF
  __int64 v363; // [rsp+290h] [rbp+190h]
  _BYTE v364[96]; // [rsp+2E0h] [rbp+1E0h] BYREF
  unsigned __int16 *v365; // [rsp+340h] [rbp+240h]
  unsigned __int16 *v366; // [rsp+348h] [rbp+248h]
  _BYTE v367[128]; // [rsp+370h] [rbp+270h] BYREF
  const WCHAR **v368; // [rsp+3F0h] [rbp+2F0h]
  unsigned __int64 v369; // [rsp+3F8h] [rbp+2F8h]
  _BYTE v370[128]; // [rsp+400h] [rbp+300h] BYREF
  const WCHAR **v371; // [rsp+480h] [rbp+380h]
  unsigned __int64 v372; // [rsp+488h] [rbp+388h]

  v339 = a4;
  TempPath2W = a3;
  v4 = String1;
  if ( !Str || !*Str )
    return 87;
  if ( String1 )
  {
    v10 = 0;
    LODWORD(v334) = 0;
    if ( *String1 )
    {
      do
      {
        v11 = &qword_140031120;
        while ( 1 )
        {
          v12 = (const wchar_t *)v11[1];
          v13 = -1;
          do
            ++v13;
          while ( v12[v13] );
          if ( !_wcsnicmp(v4, v12, v13) )
            break;
          v11 += 3;
          if ( v11 == &qword_140031198 )
          {
            AslLogCallPrintf(1, "MergeSdb_FindAndMergeForTarget", 1810, "Invalid SDB source.");
            return 87;
          }
        }
        v10 |= *((_DWORD *)v11 + 1);
        v4 += v13;
        LODWORD(v334) = v10;
      }
      while ( *v4 );
    }
  }
  else
  {
    LODWORD(v334) = -1;
  }
  v6 = MergeSdb_RemoveUnusedSdbFiles();
  v8 = v6;
  if ( v6 )
  {
    AslLogCallPrintf(
      1,
      "MergeSdb_FindAndMergeForTarget",
      1818,
      "Failed to remove merged sdb files no longer in use (%d)",
      v6);
    return v8;
  }
  v14 = MergeSdbp_RemoveUnusedSdbRegistrationFiles(v7);
  if ( v14 )
    AslLogCallPrintf(
      1,
      "MergeSdb_FindAndMergeForTarget",
      1827,
      "Failed to remove merge input sdb files no longer registered for use (%d)",
      v14);
  FileName = 0;
  lpMem = 0;
  v15 = wcsrchr(Str, 0x5Cu);
  if ( v15 )
  {
    wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
      &v353,
      Str,
      -1);
    FileName = v353;
    v353 = 0;
    wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
      &v354,
      v15 + 1,
      -1);
    v20 = v354;
    v354 = 0;
  }
  else
  {
    v16 = wil::ExpandEnvironmentStringsW<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>,256>(
            L"%SYSTEMROOT%\\AppPatch",
            &FileName);
    v8 = v16;
    if ( v16 < 0 )
      goto LABEL_33;
    v17 = -1;
    do
      ++v17;
    while ( Str[v17] );
    if ( FileName )
    {
      v18 = -1;
      do
        ++v18;
      while ( FileName[v18] );
    }
    else
    {
      v18 = 0;
    }
    v331 = v17;
    Stra[0] = (wchar_t *)FileName;
    v348[0] = (LPVOID)L"\\";
    v330 = (__int64)Str;
    v348[1] = (LPVOID)1;
    Stra[1] = (wchar_t *)v18;
    v16 = wil::details::str_build_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>,wil::details::string_view_t,wil::details::string_view_t,wil::details::string_view_t>(
            &FileName,
            Stra,
            v348,
            &v330);
    v8 = v16;
    if ( v16 < 0 )
    {
LABEL_33:
      if ( (v16 & 0x1FFF0000) == 0x70000 )
        v8 = (unsigned __int16)v8;
      AslLogCallPrintf(
        1,
        "MergeSdb_FindAndMergeForTarget",
        1848,
        "Failed to expand / concat full sdb file path (%d)",
        v8);
      v23 = lpMem;
      if ( lpMem )
      {
        ProcessHeap = GetProcessHeap();
        HeapFree(ProcessHeap, 0, v23);
      }
      v25 = (WCHAR *)FileName;
      if ( FileName )
      {
        v26 = GetProcessHeap();
        HeapFree(v26, 0, v25);
      }
      return v8;
    }
    i = 0;
    wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
      &v352,
      Str,
      -1);
    v19 = lpMem;
    v20 = v352;
    if ( lpMem )
    {
      LastError = GetLastError();
      v22 = GetProcessHeap();
      HeapFree(v22, 0, v19);
      SetLastError(LastError);
    }
    v352 = 0;
  }
  v27 = (WCHAR *)FileName;
  lpMem = v20;
  if ( !FileName )
  {
    if ( v20 )
    {
      v94 = GetProcessHeap();
      v95 = v20;
      goto LABEL_566;
    }
LABEL_568:
    if ( v27 )
    {
      v311 = GetProcessHeap();
      HeapFree(v311, 0, v27);
    }
    return 14;
  }
  if ( !v20 )
    goto LABEL_568;
  if ( !RtlDoesFileExists_U(FileName) )
  {
LABEL_538:
    v297 = lpMem;
    if ( lpMem )
    {
      v298 = GetProcessHeap();
      HeapFree(v298, 0, v297);
    }
    v299 = (WCHAR *)FileName;
    if ( FileName )
    {
      v300 = GetProcessHeap();
      HeapFree(v300, 0, v299);
    }
    return 0;
  }
  Pca::MergeSdb::Utils::SdbFileData::SdbFileData((Pca::MergeSdb::Utils::SdbFileData *)v359);
  v28 = Pca::MergeSdb::Utils::SdbFileData::LoadFromSdbFile(
          (Pca::MergeSdb::Utils::SdbFileData *)v359,
          (WCHAR *)FileName,
          (const unsigned __int16 *)lpMem);
  v29 = v28;
  if ( v28 )
  {
    AslLogCallPrintf(
      1,
      "MergeSdb_FindAndMergeForTarget",
      1874,
      "Failed to read information from orignal sdb '%S' (%d)",
      Str,
      v28);
    Pca::MergeSdb::Utils::SdbFileData::~SdbFileData((Pca::MergeSdb::Utils::SdbFileData *)v359);
    v30 = lpMem;
    if ( lpMem )
    {
      v31 = GetProcessHeap();
      HeapFree(v31, 0, v30);
    }
    v32 = (WCHAR *)FileName;
    if ( FileName )
    {
      v33 = GetProcessHeap();
      HeapFree(v33, 0, v32);
    }
    return v29;
  }
  v338 = 0;
  MergeSdbp_GetRedirectedSdbPath((void **)&v338, (__int64)FileName);
  Stra[0] = 0;
  MergeSdbp_GetManifestedStub((void **)Stra, (char *)lpMem);
  v34 = Stra[0];
  v35 = 0;
  v341 = 0;
  v326 = 0;
  if ( Stra[0] )
  {
    MergeSdbp_GetRedirectedSdbPath((void **)&v341, (__int64)Stra[0]);
    v36 = wcsrchr(v34, 0x5Cu);
    if ( v36 )
    {
      wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
        &v355,
        v36 + 1,
        -1);
      v37 = v326;
      v38 = v355;
      if ( v326 )
      {
        v39 = GetLastError();
        v40 = GetProcessHeap();
        HeapFree(v40, 0, v37);
        SetLastError(v39);
      }
      v326 = v38;
      v355 = 0;
    }
    v35 = (WCHAR *)v341;
  }
  else
  {
    v339 = 0;
  }
  Pca::MergeSdb::Utils::SdbFileData::SdbFileData((Pca::MergeSdb::Utils::SdbFileData *)v362);
  if ( v34 )
  {
    v42 = Pca::MergeSdb::Utils::SdbFileData::LoadFromSdbFile((Pca::MergeSdb::Utils::SdbFileData *)v362, v34, v326);
    v43 = 0;
    v44 = v42;
    if ( v42 )
    {
      AslLogCallPrintf(
        1,
        "MergeSdb_FindAndMergeForTarget",
        1904,
        "Failed to read information from orignal manifested stub sdb '%S' (%d)",
        v34,
        v42);
      Pca::MergeSdb::Utils::SdbFileData::~SdbFileData((Pca::MergeSdb::Utils::SdbFileData *)v362);
      v45 = v326;
      if ( v326 )
      {
        v46 = GetProcessHeap();
        HeapFree(v46, 0, v45);
      }
      if ( v35 )
      {
        v47 = GetProcessHeap();
        HeapFree(v47, 0, v35);
      }
      v48 = GetProcessHeap();
      HeapFree(v48, 0, v34);
      v49 = (WCHAR *)v338;
      if ( v338 )
      {
        v50 = GetProcessHeap();
        HeapFree(v50, 0, v49);
      }
      Pca::MergeSdb::Utils::SdbFileData::~SdbFileData((Pca::MergeSdb::Utils::SdbFileData *)v359);
      v51 = lpMem;
      if ( lpMem )
      {
        v52 = GetProcessHeap();
        HeapFree(v52, 0, v51);
      }
      v53 = (WCHAR *)FileName;
      if ( FileName )
      {
        v54 = GetProcessHeap();
        HeapFree(v54, 0, v53);
      }
      return v44;
    }
    v55 = v363;
    v56 = v363;
  }
  else
  {
    v55 = v363;
    v56 = 0;
    v43 = 0;
  }
  v57 = v360;
  if ( v56 > v360 )
    v57 = v55 & -(__int64)(v34 != 0);
  v320 = 0;
  v58 = 0;
  v343 = &v320;
  v335 = 0;
  if ( v361 )
  {
    MergeTargetRegistryKeyPathForTarget = Pca::MergeSdb::Utils::SdbFileData::GetMergeTargetRegistryKeyPathForTarget(
                                            (__int64)&v335,
                                            v361,
                                            v41);
    v58 = v335;
    v59 = (unsigned int)MergeTargetRegistryKeyPathForTarget;
    if ( MergeTargetRegistryKeyPathForTarget < 0 )
    {
      v43 = (unsigned __int16)MergeTargetRegistryKeyPathForTarget;
      if ( (MergeTargetRegistryKeyPathForTarget & 0x1FFF0000) != 0x70000 )
        v43 = MergeTargetRegistryKeyPathForTarget;
      goto LABEL_545;
    }
  }
  else
  {
    v59 = 5023;
  }
  if ( (int)v59 < 0 )
  {
LABEL_545:
    AslLogCallPrintf(1, "MergeSdb_FindAndMergeForTarget", 1933, "Failed to get the merge target key path (%d)", v43);
LABEL_546:
    if ( v58 )
    {
      v301 = GetProcessHeap();
      HeapFree(v301, 0, v58);
    }
    if ( v320 )
      RegCloseKey(v320);
    Pca::MergeSdb::Utils::SdbFileData::~SdbFileData((Pca::MergeSdb::Utils::SdbFileData *)v362);
    v302 = v326;
    if ( v326 )
    {
      v303 = GetProcessHeap();
      HeapFree(v303, 0, v302);
    }
    if ( v35 )
    {
      v304 = GetProcessHeap();
      HeapFree(v304, 0, v35);
    }
    if ( v34 )
    {
      v305 = GetProcessHeap();
      HeapFree(v305, 0, v34);
    }
    v306 = v338;
    if ( !v338 )
      goto LABEL_559;
    v74 = GetProcessHeap();
    v75 = (WCHAR *)v306;
LABEL_558:
    HeapFree(v74, 0, v75);
LABEL_559:
    Pca::MergeSdb::Utils::SdbFileData::~SdbFileData((Pca::MergeSdb::Utils::SdbFileData *)v359);
    v307 = lpMem;
    if ( lpMem )
    {
      v308 = GetProcessHeap();
      HeapFree(v308, 0, v307);
    }
    v309 = (WCHAR *)FileName;
    if ( FileName )
    {
      v310 = GetProcessHeap();
      HeapFree(v310, 0, v309);
    }
    return v43;
  }
  v331 = 0;
  v330 = std::_List_alloc<0,std::_List_base_types<Pca::MergeSdb::Utils::RegistrationInfo>>::_Buynode0(v59, 0, 0);
  hKey = 0;
  v61 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, (LPCWSTR)v58, 0, 0x2001Fu, &hKey);
  v43 = v61;
  if ( v61 )
  {
    if ( v61 != 2 )
    {
      v64 = "Failed to open the target key (%d)";
      v65 = 1945;
LABEL_80:
      LODWORD(phkResult) = v43;
      AslLogCallPrintf(1, "MergeSdb_FindAndMergeForTarget", v65, v64, phkResult);
      if ( hKey )
        RegCloseKey(hKey);
      std::list<Pca::MergeSdb::Utils::RegistrationInfo>::~list<Pca::MergeSdb::Utils::RegistrationInfo>(&v330);
      goto LABEL_546;
    }
    v66 = v338;
    if ( v338 )
    {
      v43 = lambda_ce78dd138d137ef97cf3e4f50eb625f5_::operator()(&v343, v62, v63);
      if ( v43 )
      {
        v67 = "Unable to open SdbUpdates key (%d)";
        v68 = 1955;
LABEL_86:
        LODWORD(phkResult) = v43;
        AslLogCallPrintf(1, "MergeSdb_FindAndMergeForTarget", v68, v67, phkResult);
        if ( hKey )
          RegCloseKey(hKey);
        std::list<Pca::MergeSdb::Utils::RegistrationInfo>::~list<Pca::MergeSdb::Utils::RegistrationInfo>(&v330);
        if ( v58 )
        {
          v69 = GetProcessHeap();
          HeapFree(v69, 0, v58);
        }
        if ( v320 )
          RegCloseKey(v320);
        Pca::MergeSdb::Utils::SdbFileData::~SdbFileData((Pca::MergeSdb::Utils::SdbFileData *)v362);
        v70 = v326;
        if ( v326 )
        {
          v71 = GetProcessHeap();
          HeapFree(v71, 0, v70);
        }
        if ( v35 )
        {
          v72 = GetProcessHeap();
          HeapFree(v72, 0, v35);
        }
        if ( v34 )
        {
          v73 = GetProcessHeap();
          HeapFree(v73, 0, v34);
        }
        v74 = GetProcessHeap();
        v75 = (WCHAR *)v66;
        goto LABEL_558;
      }
      v43 = MergeSdbp_CommitSdbUpdatesKeyValueAndVersionTransacted(v320, 0, (const unsigned __int16 *)lpMem, 0, 1);
      if ( v43 )
      {
        v67 = "Failed to delete redirect value from SdbUpdates (%d)";
        v68 = 1964;
        goto LABEL_86;
      }
    }
    if ( hKey )
      RegCloseKey(hKey);
    std::list<Pca::MergeSdb::Utils::RegistrationInfo>::~list<Pca::MergeSdb::Utils::RegistrationInfo>(&v330);
    if ( v58 )
    {
      v76 = GetProcessHeap();
      HeapFree(v76, 0, v58);
    }
    if ( v320 )
      RegCloseKey(v320);
    Pca::MergeSdb::Utils::SdbFileData::~SdbFileData((Pca::MergeSdb::Utils::SdbFileData *)v362);
    v77 = v326;
    if ( v326 )
    {
      v78 = GetProcessHeap();
      HeapFree(v78, 0, v77);
    }
    if ( v35 )
    {
      v79 = GetProcessHeap();
      HeapFree(v79, 0, v35);
    }
    if ( v34 )
    {
      v80 = GetProcessHeap();
      HeapFree(v80, 0, v34);
    }
    if ( !v66 )
      goto LABEL_537;
    v81 = GetProcessHeap();
    v82 = (void *)v66;
    goto LABEL_536;
  }
  cSubKeys = 0;
  cbMaxSubKeyLen = 0;
  cValues = 0;
  cbMaxValueNameLen = 0;
  v43 = RegQueryInfoKeyW(hKey, 0, 0, 0, &cSubKeys, &cbMaxSubKeyLen, 0, &cValues, &cbMaxValueNameLen, 0, 0, 0);
  if ( v43 )
  {
    v64 = "RegQueryInfoKeyW failed for merge target key (%d)";
    v65 = 1988;
    goto LABEL_80;
  }
  v83 = cbMaxSubKeyLen;
  if ( cbMaxValueNameLen > cbMaxSubKeyLen )
    v83 = cbMaxValueNameLen;
  cbMaxSubKeyLen = v83 + 1;
  wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
    &v337,
    0,
    v83 + 1);
  v84 = (WCHAR *)v337;
  v85 = 0;
  if ( !v337 )
  {
LABEL_120:
    if ( hKey )
      RegCloseKey(hKey);
    std::list<Pca::MergeSdb::Utils::RegistrationInfo>::~list<Pca::MergeSdb::Utils::RegistrationInfo>(&v330);
    if ( v58 )
    {
      v86 = GetProcessHeap();
      HeapFree(v86, 0, v58);
    }
    if ( v320 )
      RegCloseKey(v320);
    Pca::MergeSdb::Utils::SdbFileData::~SdbFileData((Pca::MergeSdb::Utils::SdbFileData *)v362);
    v87 = v326;
    if ( v326 )
    {
      v88 = GetProcessHeap();
      HeapFree(v88, 0, v87);
    }
    if ( v35 )
    {
      v89 = GetProcessHeap();
      HeapFree(v89, 0, v35);
    }
    if ( v34 )
    {
      v90 = GetProcessHeap();
      HeapFree(v90, 0, v34);
    }
    v91 = (WCHAR *)v338;
    if ( v338 )
    {
      v92 = GetProcessHeap();
      HeapFree(v92, 0, v91);
    }
    Pca::MergeSdb::Utils::SdbFileData::~SdbFileData((Pca::MergeSdb::Utils::SdbFileData *)v359);
    v93 = lpMem;
    if ( !lpMem )
      goto LABEL_567;
    v94 = GetProcessHeap();
    v95 = v93;
LABEL_566:
    HeapFree(v94, 0, v95);
LABEL_567:
    v27 = (WCHAR *)FileName;
    goto LABEL_568;
  }
  if ( cValues && cbMaxValueNameLen > 1 )
  {
    v96 = 0;
    v349 = 0;
    v350 = 0;
LABEL_139:
    for ( i = v96; ; v96 = i )
    {
      v97 = Pca::MergeSdb::Utils::RegUtil::EnumRegValue((struct Pca::MergeSdb::Utils::RegValue *)&v349, hKey, v96);
      v85 = 0;
      if ( v97 )
        break;
      if ( v350 <= 3 || !v349 || (v98 = v349 + 6, v349 == (const unsigned __int16 *)-12LL) || !*v98 )
      {
        v96 = i + 1;
        goto LABEL_139;
      }
      v99 = Pca::MergeSdb::Utils::RegUtil::DeleteRegValue(hKey, v98);
      LODWORD(lpFileName) = v99;
      if ( v99 )
      {
        AslLogCallPrintf(1, "MergeSdb_FindAndMergeForTarget", 2018, "RegDeleteValueW failed (%d)", v99);
        v100 = (unsigned __int16 *)v349;
        v349 = 0;
        if ( v100 )
          operator delete[](v100);
        goto LABEL_150;
      }
    }
    v114 = (unsigned __int16 *)v349;
    v349 = 0;
    if ( v114 )
    {
      operator delete[](v114);
      v85 = 0;
    }
  }
  v115 = 0;
  i = 0;
  if ( cSubKeys )
  {
    while ( 1 )
    {
      v358 = v57;
      v116 = MergeSdbp_ProcessMergeTargetSubKey(hKey, cbMaxSubKeyLen, v84, v115, &v358, &v330);
      v85 = 0;
      LODWORD(lpFileName) = v116;
      if ( v116 )
        break;
      v115 = i + 1;
      i = v115;
      if ( v115 >= cSubKeys )
        goto LABEL_175;
    }
    if ( v116 != 259 )
    {
      AslLogCallPrintf(
        1,
        "MergeSdb_FindAndMergeForTarget",
        2039,
        "MergeSdbp_ProcessMergeTargetSubKey failed (%d)",
        v116);
LABEL_150:
      v101 = GetProcessHeap();
      HeapFree(v101, 0, v84);
      if ( hKey )
        RegCloseKey(hKey);
      std::list<Pca::MergeSdb::Utils::RegistrationInfo>::~list<Pca::MergeSdb::Utils::RegistrationInfo>(&v330);
      if ( v58 )
      {
        v102 = GetProcessHeap();
        HeapFree(v102, 0, v58);
      }
      if ( v320 )
        RegCloseKey(v320);
      Pca::MergeSdb::Utils::SdbFileData::~SdbFileData((Pca::MergeSdb::Utils::SdbFileData *)v362);
      v103 = v326;
      if ( v326 )
      {
        v104 = GetProcessHeap();
        HeapFree(v104, 0, v103);
      }
      if ( v35 )
      {
        v105 = GetProcessHeap();
        HeapFree(v105, 0, v35);
      }
      if ( v34 )
      {
        v106 = GetProcessHeap();
        HeapFree(v106, 0, v34);
      }
      v107 = v338;
      if ( !v338 )
        goto LABEL_165;
      v108 = GetProcessHeap();
      v109 = (void *)v107;
LABEL_164:
      HeapFree(v108, 0, v109);
LABEL_165:
      Pca::MergeSdb::Utils::SdbFileData::~SdbFileData((Pca::MergeSdb::Utils::SdbFileData *)v359);
      v110 = lpMem;
      if ( lpMem )
      {
        v111 = GetProcessHeap();
        HeapFree(v111, 0, v110);
      }
      v112 = (WCHAR *)FileName;
      if ( FileName )
      {
        v113 = GetProcessHeap();
        HeapFree(v113, 0, v112);
      }
      return (unsigned int)lpFileName;
    }
  }
LABEL_175:
  v117 = 0;
  v336 = 0;
  for ( j = *(const WCHAR **)v330; j != (const WCHAR *)v330; j = *(const WCHAR **)j )
  {
    if ( **((_DWORD **)j + 21) == 3 )
    {
      wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
        &v356,
        *((_QWORD *)j + 2),
        -1);
      wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::operator=(
        &v336,
        &v356);
      v119 = v356;
      if ( v356 )
      {
        v120 = GetProcessHeap();
        HeapFree(v120, 0, v119);
      }
      v117 = v336;
      if ( !v336 )
      {
        v121 = GetProcessHeap();
        HeapFree(v121, 0, v84);
        goto LABEL_120;
      }
      break;
    }
  }
  v122 = lambda_ce78dd138d137ef97cf3e4f50eb625f5_::operator()(&v343, j, v85);
  LODWORD(lpFileName) = v122;
  if ( v122 )
  {
    AslLogCallPrintf(1, "MergeSdb_FindAndMergeForTarget", 2060, "Unable to open SdbUpdates key (%d)", v122);
    if ( v117 )
    {
      v124 = GetProcessHeap();
      HeapFree(v124, 0, v117);
    }
    goto LABEL_150;
  }
  v345[1] = 0;
  v345[0] = 0;
  LODWORD(lpFileName) = 0;
  RegValue = Pca::MergeSdb::Utils::RegUtil::ReadRegValue(v320, v123, (struct Pca::MergeSdb::Utils::RegValue *)v345);
  v128 = 0;
  i = RegValue;
  if ( RegValue )
  {
    if ( RegValue != 2 )
    {
      AslLogCallPrintf(
        1,
        "MergeSdb_FindAndMergeForTarget",
        2071,
        "Failed to read merge disabled registry value (%d)",
        RegValue);
      v129 = (void *)v345[0];
      v345[0] = 0;
      if ( v129 )
        operator delete[](v129);
      if ( v117 )
      {
        v130 = GetProcessHeap();
        HeapFree(v130, 0, v117);
      }
      v131 = GetProcessHeap();
      HeapFree(v131, 0, v84);
      if ( hKey )
        RegCloseKey(hKey);
      std::list<Pca::MergeSdb::Utils::RegistrationInfo>::~list<Pca::MergeSdb::Utils::RegistrationInfo>(&v330);
      if ( v58 )
      {
        v132 = GetProcessHeap();
        HeapFree(v132, 0, v58);
      }
      if ( v320 )
        RegCloseKey(v320);
      Pca::MergeSdb::Utils::SdbFileData::~SdbFileData((Pca::MergeSdb::Utils::SdbFileData *)v362);
      v133 = v326;
      if ( v326 )
      {
        v134 = GetProcessHeap();
        HeapFree(v134, 0, v133);
      }
      if ( v35 )
      {
        v135 = GetProcessHeap();
        HeapFree(v135, 0, v35);
      }
      if ( v34 )
      {
        v136 = GetProcessHeap();
        HeapFree(v136, 0, v34);
      }
      v137 = v338;
      if ( !v338 )
        goto LABEL_209;
      v138 = GetProcessHeap();
      v139 = (void *)v137;
LABEL_208:
      HeapFree(v138, 0, v139);
LABEL_209:
      Pca::MergeSdb::Utils::SdbFileData::~SdbFileData((Pca::MergeSdb::Utils::SdbFileData *)v359);
      v140 = lpMem;
      if ( lpMem )
      {
        v141 = GetProcessHeap();
        HeapFree(v141, 0, v140);
      }
      v142 = (WCHAR *)FileName;
      if ( FileName )
      {
        v143 = GetProcessHeap();
        HeapFree(v143, 0, v142);
      }
      return i;
    }
    goto LABEL_215;
  }
  if ( !Pca::MergeSdb::Utils::RegValue::GetValueValue(
          (Pca::MergeSdb::Utils::RegValue *)v345,
          (unsigned int *)&lpFileName) )
  {
LABEL_215:
    v144 = v128;
    goto LABEL_217;
  }
  v144 = (int)lpFileName;
LABEL_217:
  if ( v144 )
  {
    v145 = (WCHAR *)v338;
    if ( v338 )
    {
      v146 = MergeSdbp_CommitSdbUpdatesKeyValueAndVersionTransacted(v320, 0, (const unsigned __int16 *)lpMem, 0, 1);
      v128 = 0;
      TempPath2W = v146;
      if ( v146 )
      {
        AslLogCallPrintf(
          1,
          "MergeSdb_FindAndMergeForTarget",
          2091,
          "Failed to delete redirect value from SdbUpdates (%d)",
          v146);
        v147 = (void *)v345[0];
        v345[0] = 0;
        if ( v147 )
          operator delete[](v147);
        goto LABEL_222;
      }
    }
    v160 = (void *)v345[0];
    v345[0] = v128;
    if ( v160 )
      operator delete[](v160);
    goto LABEL_520;
  }
  v161 = (void *)v345[0];
  v345[0] = v128;
  if ( v161 )
  {
    operator delete[](v161);
    LODWORD(v128) = 0;
  }
  v145 = (WCHAR *)v338;
  if ( !v331 )
  {
    if ( !v338 )
      goto LABEL_498;
    v277 = lambda_ce78dd138d137ef97cf3e4f50eb625f5_::operator()(&v343, v126, v127);
    TempPath2W = v277;
    if ( v277 )
    {
      v278 = "Unable to open SdbUpdates key (%d)";
      v279 = 2117;
    }
    else
    {
      v277 = MergeSdbp_CommitSdbUpdatesKeyValueAndVersionTransacted(v320, 0, (const unsigned __int16 *)lpMem, 0, 1);
      TempPath2W = v277;
      if ( !v277 )
      {
        wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::operator=(&v338);
        v145 = (WCHAR *)v338;
        goto LABEL_498;
      }
      v278 = "Failed to delete redirect value from SdbUpdates (%d)";
      v279 = 2126;
    }
    LODWORD(phkResult) = v277;
    AslLogCallPrintf(1, "MergeSdb_FindAndMergeForTarget", v279, v278, phkResult);
    goto LABEL_222;
  }
  if ( v331 != 1 || !v117 )
    goto LABEL_280;
  if ( v339 != (_DWORD)v128 && !v338 )
  {
LABEL_498:
    if ( v35 )
    {
      v280 = lambda_ce78dd138d137ef97cf3e4f50eb625f5_::operator()(&v343, v126, v127);
      TempPath2W = v280;
      if ( v280 )
      {
        v281 = "Unable to open SdbUpdates key (%d)";
        v282 = 2135;
LABEL_501:
        LODWORD(phkResult) = v280;
        AslLogCallPrintf(1, "MergeSdb_FindAndMergeForTarget", v282, v281, phkResult);
        goto LABEL_502;
      }
      v280 = MergeSdbp_CommitSdbUpdatesKeyValueAndVersionTransacted(v320, 0, v326, 0, 1);
      TempPath2W = v280;
      if ( v280 )
      {
        v281 = "Failed to delete stub redirect value from SdbUpdates (%d)";
        v282 = 2144;
        goto LABEL_501;
      }
      wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::operator=(&v341);
      v35 = (WCHAR *)v341;
    }
LABEL_520:
    if ( v117 )
    {
      v290 = GetProcessHeap();
      HeapFree(v290, 0, v117);
    }
    v291 = GetProcessHeap();
    HeapFree(v291, 0, v84);
    if ( hKey )
      RegCloseKey(hKey);
    std::list<Pca::MergeSdb::Utils::RegistrationInfo>::~list<Pca::MergeSdb::Utils::RegistrationInfo>(&v330);
    if ( v58 )
    {
      v292 = GetProcessHeap();
      HeapFree(v292, 0, v58);
    }
    if ( v320 )
      RegCloseKey(v320);
    Pca::MergeSdb::Utils::SdbFileData::~SdbFileData((Pca::MergeSdb::Utils::SdbFileData *)v362);
    v293 = v326;
    if ( v326 )
    {
      v294 = GetProcessHeap();
      HeapFree(v294, 0, v293);
    }
    if ( v35 )
    {
      v295 = GetProcessHeap();
      HeapFree(v295, 0, v35);
    }
    if ( v34 )
    {
      v296 = GetProcessHeap();
      HeapFree(v296, 0, v34);
    }
    if ( !v145 )
      goto LABEL_537;
    goto LABEL_535;
  }
  if ( v35 )
  {
    v162 = lambda_ce78dd138d137ef97cf3e4f50eb625f5_::operator()(&v343, v126, v127);
    LODWORD(lpFileName) = v162;
    if ( v162 )
    {
      AslLogCallPrintf(1, "MergeSdb_FindAndMergeForTarget", 2164, "Unable to open SdbUpdates key (%d)", v162);
      v163 = GetProcessHeap();
      HeapFree(v163, 0, v117);
      v164 = GetProcessHeap();
      HeapFree(v164, 0, v84);
      if ( hKey )
        RegCloseKey(hKey);
      std::list<Pca::MergeSdb::Utils::RegistrationInfo>::~list<Pca::MergeSdb::Utils::RegistrationInfo>(&v330);
      if ( v58 )
      {
        v165 = GetProcessHeap();
        HeapFree(v165, 0, v58);
      }
      if ( v320 )
        RegCloseKey(v320);
      Pca::MergeSdb::Utils::SdbFileData::~SdbFileData((Pca::MergeSdb::Utils::SdbFileData *)v362);
      v166 = v326;
      if ( v326 )
      {
        v167 = GetProcessHeap();
        HeapFree(v167, 0, v166);
      }
      v168 = GetProcessHeap();
      HeapFree(v168, 0, v35);
      if ( v34 )
      {
        v169 = GetProcessHeap();
        HeapFree(v169, 0, v34);
      }
      if ( !v145 )
        goto LABEL_165;
      v108 = GetProcessHeap();
      v109 = v145;
      goto LABEL_164;
    }
    v170 = MergeSdbp_CommitSdbUpdatesKeyValueAndVersionTransacted(v320, 0, v326, 0, 1);
    i = v170;
    if ( v170 )
    {
      AslLogCallPrintf(
        1,
        "MergeSdb_FindAndMergeForTarget",
        2173,
        "Failed to delete stub redirect value from SdbUpdates (%d)",
        v170);
      v171 = GetProcessHeap();
      HeapFree(v171, 0, v117);
      v172 = GetProcessHeap();
      HeapFree(v172, 0, v84);
      if ( hKey )
        RegCloseKey(hKey);
      std::list<Pca::MergeSdb::Utils::RegistrationInfo>::~list<Pca::MergeSdb::Utils::RegistrationInfo>(&v330);
      if ( v58 )
      {
        v173 = GetProcessHeap();
        HeapFree(v173, 0, v58);
      }
      if ( v320 )
        RegCloseKey(v320);
      Pca::MergeSdb::Utils::SdbFileData::~SdbFileData((Pca::MergeSdb::Utils::SdbFileData *)v362);
      v174 = v326;
      if ( v326 )
      {
        v175 = GetProcessHeap();
        HeapFree(v175, 0, v174);
      }
LABEL_274:
      v176 = GetProcessHeap();
      HeapFree(v176, 0, v35);
LABEL_275:
      if ( v34 )
      {
        v177 = GetProcessHeap();
        HeapFree(v177, 0, v34);
      }
      if ( !v145 )
        goto LABEL_209;
      v138 = GetProcessHeap();
      v139 = v145;
      goto LABEL_208;
    }
    wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::operator=(&v341);
    v35 = (WCHAR *)v341;
    LOBYTE(v128) = 0;
  }
LABEL_280:
  LOBYTE(v126) = v128;
  std::list_Pca::MergeSdb::Utils::RegistrationInfo_std::allocator_Pca::MergeSdb::Utils::RegistrationInfo___::sort__lambda_c5b5923c216b51f2fdbd2d40cd9e82ec___(
    &v330,
    v126);
  v327 = 0;
  v328 = 0;
  v327 = (const WCHAR **)std::_List_alloc<0,std::_List_base_types<Pca::MergeSdb::PreviousMergeDbInfo>>::_Buynode0(
                           v178,
                           0,
                           0);
  v179 = v327;
  if ( v145 )
  {
    Pca::MergeSdb::Utils::SdbFileData::SdbFileData((Pca::MergeSdb::Utils::SdbFileData *)v367);
    v180 = Pca::MergeSdb::Utils::SdbFileData::LoadFromSdbFile((Pca::MergeSdb::Utils::SdbFileData *)v367, v145, 0);
    i = v180;
    if ( v180 )
    {
      AslLogCallPrintf(
        1,
        "MergeSdb_FindAndMergeForTarget",
        2196,
        "Failed to load sdb file information from redirected sdb file (%d)",
        v180);
    }
    else
    {
      v181 = v368;
      v368 = v327;
      v327 = v181;
      v182 = v369;
      v369 = v328;
      v328 = v182;
      std::list_Pca::MergeSdb::PreviousMergeDbInfo_std::allocator_Pca::MergeSdb::PreviousMergeDbInfo___::sort__lambda_ab93fee0497c657d172fe9a324dca64d___(
        &v327,
        0);
    }
    if ( v328 == 2 && v331 == 1 && v117 )
    {
      Pca::MergeSdb::Utils::SdbFileData::~SdbFileData((Pca::MergeSdb::Utils::SdbFileData *)v367);
      std::list<Pca::MergeSdb::PreviousMergeDbInfo>::clear(&v327);
      operator delete(v327);
      v183 = GetProcessHeap();
      HeapFree(v183, 0, v117);
      v184 = GetProcessHeap();
      HeapFree(v184, 0, v84);
      if ( hKey )
        RegCloseKey(hKey);
      std::list<Pca::MergeSdb::Utils::RegistrationInfo>::~list<Pca::MergeSdb::Utils::RegistrationInfo>(&v330);
      if ( v58 )
      {
        v185 = GetProcessHeap();
        HeapFree(v185, 0, v58);
      }
      if ( v320 )
        RegCloseKey(v320);
      Pca::MergeSdb::Utils::SdbFileData::~SdbFileData((Pca::MergeSdb::Utils::SdbFileData *)v362);
      v186 = v326;
      if ( v326 )
      {
        v187 = GetProcessHeap();
        HeapFree(v187, 0, v186);
      }
      if ( v35 )
      {
        v188 = GetProcessHeap();
        HeapFree(v188, 0, v35);
      }
      if ( v34 )
      {
        v189 = GetProcessHeap();
        HeapFree(v189, 0, v34);
      }
LABEL_535:
      v81 = GetProcessHeap();
      v82 = v145;
LABEL_536:
      HeapFree(v81, 0, v82);
LABEL_537:
      Pca::MergeSdb::Utils::SdbFileData::~SdbFileData((Pca::MergeSdb::Utils::SdbFileData *)v359);
      goto LABEL_538;
    }
    Pca::MergeSdb::Utils::SdbFileData::~SdbFileData((Pca::MergeSdb::Utils::SdbFileData *)v367);
    v179 = v327;
  }
  v190 = 1;
  v317 = 1;
  v318[0] = 1;
  if ( v328 <= v331 + 1 )
  {
    v191 = *v179;
    v192 = v330;
    lpFileName = v191;
    v193 = *(const WCHAR **)v330;
    v348[0] = *(LPVOID *)v330;
    if ( v191 != (const WCHAR *)v179 )
    {
      v191 = *(const WCHAR **)v191;
      lpFileName = v191;
    }
    while ( v191 != (const WCHAR *)v179 || v193 != (const WCHAR *)v192 )
    {
      matched = MergeSdbp_MatchMergeInputToAlreadyMerged(
                  (unsigned int)&v317,
                  (unsigned int)v318,
                  (unsigned int)&v327,
                  (unsigned int)&lpFileName,
                  (__int64)&v330,
                  (__int64)v348,
                  (_DWORD)v334,
                  TempPath2W);
      v190 = v318[0];
      if ( !matched )
        break;
      if ( !v318[0] )
        goto LABEL_318;
      v179 = v327;
      v191 = lpFileName;
      v193 = (const WCHAR *)v348[0];
      v192 = v330;
    }
    if ( v190 )
    {
      v195 = L"entirely";
      if ( !v317 )
        v195 = L"sufficiently";
      LODWORD(lpcbMaxSubKeyLen) = v331;
      AslLogCallPrintf(
        3,
        "MergeSdb_FindAndMergeForTarget",
        2268,
        "Redirected merge sdb is already %S up-to-date with %d merges: '%S' -> '%S'",
        v195,
        lpcbMaxSubKeyLen,
        FileName,
        v145);
      if ( v35 )
      {
        v198 = lambda_ce78dd138d137ef97cf3e4f50eb625f5_::operator()(&v343, v196, v197);
        TempPath2W = v198;
        if ( v198 )
        {
          v199 = "Unable to open SdbUpdates key (%d)";
          v200 = 2275;
LABEL_314:
          LODWORD(phkResulta) = v198;
          AslLogCallPrintf(1, "MergeSdb_FindAndMergeForTarget", v200, v199, phkResulta);
          std::list<Pca::MergeSdb::PreviousMergeDbInfo>::clear(&v327);
          operator delete(v327);
LABEL_502:
          if ( v117 )
          {
            v283 = GetProcessHeap();
            HeapFree(v283, 0, v117);
          }
          v284 = GetProcessHeap();
          HeapFree(v284, 0, v84);
          if ( hKey )
            RegCloseKey(hKey);
          std::list<Pca::MergeSdb::Utils::RegistrationInfo>::~list<Pca::MergeSdb::Utils::RegistrationInfo>(&v330);
          if ( v58 )
          {
            v285 = GetProcessHeap();
            HeapFree(v285, 0, v58);
          }
          if ( v320 )
            RegCloseKey(v320);
          Pca::MergeSdb::Utils::SdbFileData::~SdbFileData((Pca::MergeSdb::Utils::SdbFileData *)v362);
          v286 = v326;
          if ( v326 )
          {
            v287 = GetProcessHeap();
            HeapFree(v287, 0, v286);
          }
          goto LABEL_512;
        }
        v198 = MergeSdbp_CommitSdbUpdatesKeyValueAndVersionTransacted(v320, 0, v326, 0, 1);
        TempPath2W = v198;
        if ( v198 )
        {
          v199 = "Failed to delete stub redirect value from SdbUpdates (%d)";
          v200 = 2284;
          goto LABEL_314;
        }
      }
      goto LABEL_317;
    }
  }
LABEL_318:
  std::list<Pca::MergeSdb::PreviousMergeDbInfo>::clear(&v327);
  if ( v35 )
  {
    Pca::MergeSdb::Utils::SdbFileData::SdbFileData((Pca::MergeSdb::Utils::SdbFileData *)v370);
    v201 = Pca::MergeSdb::Utils::SdbFileData::LoadFromSdbFile((Pca::MergeSdb::Utils::SdbFileData *)v370, v35, 0);
    i = v201;
    if ( v201 )
    {
      AslLogCallPrintf(
        1,
        "MergeSdb_FindAndMergeForTarget",
        2316,
        "Failed to load sdb file information from redirected manifested stub sdb file (%d)",
        v201);
    }
    else
    {
      v202 = v371;
      v371 = v327;
      v327 = v202;
      v203 = v372;
      v372 = v328;
      v328 = v203;
      std::list_Pca::MergeSdb::PreviousMergeDbInfo_std::allocator_Pca::MergeSdb::PreviousMergeDbInfo___::sort__lambda_ab93fee0497c657d172fe9a324dca64d___(
        &v327,
        0);
    }
    Pca::MergeSdb::Utils::SdbFileData::~SdbFileData((Pca::MergeSdb::Utils::SdbFileData *)v370);
  }
  v204 = 1;
  v317 = 1;
  v329 = 1;
  v318[0] = 1;
  if ( v328 > v331 )
  {
    v329 = 0;
    goto LABEL_325;
  }
  v216 = (const WCHAR *)v327;
  v217 = v330;
  v218 = *v327;
  v219 = *(const WCHAR **)v330;
  v348[0] = (LPVOID)*v327;
  lpFileName = v219;
  while ( v218 != v216 || v219 != (const WCHAR *)v217 )
  {
    v220 = MergeSdbp_MatchMergeInputToAlreadyMerged(
             (unsigned int)&v317,
             (unsigned int)v318,
             (unsigned int)&v327,
             (unsigned int)v348,
             (__int64)&v330,
             (__int64)&lpFileName,
             (_DWORD)v334,
             TempPath2W);
    v204 = v318[0];
    v329 = v318[0];
    if ( !v220 )
      break;
    if ( !v318[0] )
      goto LABEL_325;
    v216 = (const WCHAR *)v327;
    v218 = (const WCHAR *)v348[0];
    v219 = lpFileName;
    v217 = v330;
  }
  if ( !v204 || !v339 )
  {
LABEL_325:
    std::list<Pca::MergeSdb::PreviousMergeDbInfo>::clear(&v327);
    TempPath2W = GetTempPath2W(0, 0);
    v205 = TempPath2W;
    v334 = 0;
    if ( TempPath2W > 0x105 )
      v205 = 261;
    lpFileName = 0;
    v206 = 0;
    wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
      &v357,
      0,
      v205);
    wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::operator=(
      &lpFileName,
      &v357);
    v348[0] = v357;
    if ( v357 )
    {
      v207 = GetProcessHeap();
      HeapFree(v207, 0, v348[0]);
    }
    v208 = GetTempPath2W(TempPath2W, lpFileName);
    if ( PcaFailedGle(&i, TempPath2W >= v208) )
    {
      AslLogCallPrintf(1, "MergeSdb_FindAndMergeForTarget", 2423, "Failed to get temp dir (%d)", i);
      v209 = (WCHAR *)lpFileName;
      if ( lpFileName )
      {
        v210 = GetProcessHeap();
        HeapFree(v210, 0, v209);
      }
      std::list<Pca::MergeSdb::PreviousMergeDbInfo>::clear(&v327);
      operator delete(v327);
      if ( v117 )
      {
        v211 = GetProcessHeap();
        HeapFree(v211, 0, v117);
      }
      v212 = GetProcessHeap();
      HeapFree(v212, 0, v84);
      if ( hKey )
        RegCloseKey(hKey);
      std::list<Pca::MergeSdb::Utils::RegistrationInfo>::~list<Pca::MergeSdb::Utils::RegistrationInfo>(&v330);
      if ( v58 )
      {
        v213 = GetProcessHeap();
        HeapFree(v213, 0, v58);
      }
      if ( v320 )
        RegCloseKey(v320);
      Pca::MergeSdb::Utils::SdbFileData::~SdbFileData((Pca::MergeSdb::Utils::SdbFileData *)v362);
      v214 = v326;
      if ( v326 )
      {
        v215 = GetProcessHeap();
        HeapFree(v215, 0, v214);
      }
      if ( !v35 )
        goto LABEL_275;
      goto LABEL_274;
    }
    if ( GetFileAttributesW(lpFileName) != -1 )
    {
      v227 = Pca::MergeSdb::Utils::SdbFileData::ClearTempDirectoryOfMatchingTempFiles(lpFileName);
      if ( v227 )
        AslLogCallPrintf(1, "MergeSdb_FindAndMergeForTarget", 2430, "Failed to clean up temp directory (%d)", v227);
      wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::swap(
        &v334,
        &lpFileName);
      v206 = v334;
    }
    v228 = wil::ExpandEnvironmentStringsW<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>,256>(
             L"%SYSTEMROOT%\\AppPatch\\Temp",
             &lpFileName);
    TempPath2W = v228;
    v229 = v228;
    if ( v228 < 0 )
    {
      if ( (v228 & 0x1FFF0000) == 0x70000 )
      {
        v229 = (unsigned __int16)v228;
        TempPath2W = (unsigned __int16)v228;
      }
      AslLogCallPrintf(1, "MergeSdb_FindAndMergeForTarget", 2439, "Failed to expand apppatch temp path (%d)", v229);
      if ( lpFileName )
      {
        v270 = GetProcessHeap();
        HeapFree(v270, 0, (LPVOID)lpFileName);
      }
      if ( v206 )
      {
        v271 = GetProcessHeap();
        HeapFree(v271, 0, v206);
      }
      std::list<Pca::MergeSdb::PreviousMergeDbInfo>::clear(&v327);
      operator delete(v327);
      if ( v117 )
      {
        v272 = GetProcessHeap();
        HeapFree(v272, 0, v117);
      }
      v273 = GetProcessHeap();
      HeapFree(v273, 0, v84);
      if ( hKey )
        RegCloseKey(hKey);
      std::list<Pca::MergeSdb::Utils::RegistrationInfo>::~list<Pca::MergeSdb::Utils::RegistrationInfo>(&v330);
      if ( v58 )
      {
        v274 = GetProcessHeap();
        HeapFree(v274, 0, v58);
      }
      if ( v320 )
        RegCloseKey(v320);
      Pca::MergeSdb::Utils::SdbFileData::~SdbFileData((Pca::MergeSdb::Utils::SdbFileData *)v362);
      v275 = v326;
      if ( v326 )
      {
        v276 = GetProcessHeap();
        HeapFree(v276, 0, v275);
      }
      if ( !v35 )
      {
LABEL_513:
        if ( v34 )
        {
          v289 = GetProcessHeap();
          HeapFree(v289, 0, v34);
        }
        if ( !v145 )
          goto LABEL_237;
        goto LABEL_236;
      }
LABEL_512:
      v288 = GetProcessHeap();
      HeapFree(v288, 0, v35);
      goto LABEL_513;
    }
    v230 = (WCHAR *)lpFileName;
    i = 0;
    v317 = 0;
    if ( GetFileAttributesW(lpFileName) == -1 )
    {
      if ( !v206 )
      {
        DirectoryW = CreateDirectoryW(v230, 0);
        if ( PcaFailedGle(&i, DirectoryW) )
        {
          v233 = i;
          AslLogCallPrintf(1, "MergeSdb_FindAndMergeForTarget", 2450, "Failed to create apppatch temp path (%d)", i);
          if ( v230 )
          {
            v234 = GetProcessHeap();
            HeapFree(v234, 0, v230);
          }
          goto LABEL_382;
        }
        wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::swap(
          &v334,
          &lpFileName);
        v206 = v334;
        v317 = 1;
      }
    }
    else
    {
      v231 = Pca::MergeSdb::Utils::SdbFileData::ClearTempDirectoryOfMatchingTempFiles(v230);
      if ( v231 )
        AslLogCallPrintf(1, "MergeSdb_FindAndMergeForTarget", 2445, "Failed to clean up temp directory (%d)", v231);
    }
    lpNewFileName = 0;
    wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::operator=(&lpNewFileName);
    v332 = 0;
    wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::operator=(&v332);
    i = Pca::MergeSdb::Utils::SdbFileData::GetUniqueTempDirectoryFileName(
          (struct Pca::MergeSdb::Utils::TempFilePathHolder *)&lpNewFileName,
          (const unsigned __int16 *)v206);
    v235 = i;
    if ( i )
    {
      v236 = 2476;
LABEL_465:
      v247 = "Failed to get unique temp file name (%d)";
      goto LABEL_466;
    }
    v237 = v329;
    if ( v329 )
      v238 = v35;
    else
      v238 = *(const WCHAR **)(*(_QWORD *)v330 + 16LL);
    v239 = CopyFileW(v238, lpNewFileName, 0);
    if ( PcaFailedGle(&i, v239) )
    {
      v240 = 2486;
LABEL_380:
      v233 = i;
      AslLogCallPrintf(1, "MergeSdb_FindAndMergeForTarget", v240, "Failed to copy sdb to temp dir (%d)", i);
LABEL_381:
      Pca::MergeSdb::Utils::TempFilePathHolder::~TempFilePathHolder((Pca::MergeSdb::Utils::TempFilePathHolder *)&v332);
      Pca::MergeSdb::Utils::TempFilePathHolder::~TempFilePathHolder((Pca::MergeSdb::Utils::TempFilePathHolder *)&lpNewFileName);
      wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(&lpFileName);
      wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(&v334);
LABEL_382:
      std::list<Pca::MergeSdb::PreviousMergeDbInfo>::clear(&v327);
      operator delete(v327);
      wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(&v336);
      wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(&v337);
      if ( hKey )
        RegCloseKey(hKey);
      std::list<Pca::MergeSdb::Utils::RegistrationInfo>::~list<Pca::MergeSdb::Utils::RegistrationInfo>(&v330);
      wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(&v335);
      if ( v320 )
        RegCloseKey(v320);
      goto LABEL_472;
    }
    UniqueTempDirectoryFileName = Pca::MergeSdb::Utils::SdbFileData::GetUniqueTempDirectoryFileName(
                                    (struct Pca::MergeSdb::Utils::TempFilePathHolder *)&v332,
                                    (const unsigned __int16 *)v206);
    v235 = UniqueTempDirectoryFileName;
    if ( UniqueTempDirectoryFileName < 0 )
    {
      if ( (UniqueTempDirectoryFileName & 0x1FFF0000) == 0x70000 )
        v235 = (unsigned __int16)UniqueTempDirectoryFileName;
      v236 = 2496;
      goto LABEL_465;
    }
    i = 0;
    if ( !v237 && v331 > 1 )
    {
      while ( 1 )
      {
        v242 = SdbMergeDatabases(lpNewFileName, *(_QWORD *)(**(_QWORD **)v330 + 16LL), v332, 1);
        v243 = RtlNtStatusToDosError(v242);
        TempPath2W = v243;
        if ( v242 < 0 )
          break;
        Pca::MergeSdb::Utils::TempFilePathHolder::Delete(&lpNewFileName);
        wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::swap(
          &lpNewFileName,
          &v332);
        i = Pca::MergeSdb::Utils::SdbFileData::GetUniqueTempDirectoryFileName(
              (struct Pca::MergeSdb::Utils::TempFilePathHolder *)&v332,
              (const unsigned __int16 *)v206);
        v235 = i;
        if ( i )
        {
          v236 = 2531;
          goto LABEL_465;
        }
        std::list<Pca::MergeSdb::Utils::RegistrationInfo>::pop_front(&v330);
        if ( v331 <= 1 )
          goto LABEL_392;
      }
      v245 = 2516;
      goto LABEL_397;
    }
LABEL_392:
    if ( v339 )
    {
      v244 = CopyFileW(lpNewFileName, v332, 0);
      if ( PcaFailedGle(&i, v244) )
      {
        v240 = 2555;
        goto LABEL_380;
      }
    }
    else
    {
      v246 = SdbMergeDatabases(v359[0], lpNewFileName, v332, 0);
      v243 = RtlNtStatusToDosError(v246);
      TempPath2W = v243;
      if ( v246 < 0 )
      {
        v245 = 2564;
LABEL_397:
        AslLogCallPrintf(1, "MergeSdb_FindAndMergeForTarget", v245, "SdbMergeDatabases failed (%d)", v243);
        Pca::MergeSdb::Utils::TempFilePathHolder::~TempFilePathHolder((Pca::MergeSdb::Utils::TempFilePathHolder *)&v332);
        Pca::MergeSdb::Utils::TempFilePathHolder::~TempFilePathHolder((Pca::MergeSdb::Utils::TempFilePathHolder *)&lpNewFileName);
        wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(&lpFileName);
        wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(&v334);
        std::list<Pca::MergeSdb::PreviousMergeDbInfo>::clear(&v327);
        operator delete(v327);
        wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(&v336);
        wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(&v337);
        if ( hKey )
          RegCloseKey(hKey);
        std::list<Pca::MergeSdb::Utils::RegistrationInfo>::~list<Pca::MergeSdb::Utils::RegistrationInfo>(&v330);
        wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(&v335);
        if ( v320 )
          RegCloseKey(v320);
        v233 = TempPath2W;
        goto LABEL_472;
      }
      v235 = MergeSdbp_VerifyPredictedMergeChecksumMatches(FileName, lpNewFileName, v332);
      if ( v235 )
      {
        v247 = "Failed to verify matching sdb checksums (%d)";
        v236 = 2569;
LABEL_466:
        LODWORD(phkResult) = v235;
        AslLogCallPrintf(1, "MergeSdb_FindAndMergeForTarget", v236, v247, phkResult);
        goto LABEL_467;
      }
    }
    Pca::MergeSdb::Utils::TempFilePathHolder::Delete(&lpNewFileName);
    wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::swap(
      &lpNewFileName,
      &v332);
    if ( !v237 )
      std::list<Pca::MergeSdb::Utils::RegistrationInfo>::pop_front(&v330);
    Pca::MergeSdb::Utils::SdbFileData::SdbFileData((Pca::MergeSdb::Utils::SdbFileData *)v364);
    v248 = Pca::MergeSdb::Utils::SdbFileData::LoadFromSdbFile(
             (Pca::MergeSdb::Utils::SdbFileData *)v364,
             (WCHAR *)lpNewFileName,
             (const unsigned __int16 *)lpMem);
    v235 = v248;
    if ( v248 )
    {
      AslLogCallPrintf(1, "MergeSdb_FindAndMergeForTarget", 2586, "Failed to load file data from merged sdb (%d)", v248);
      Pca::MergeSdb::Utils::SdbFileData::~SdbFileData((Pca::MergeSdb::Utils::SdbFileData *)v364);
LABEL_467:
      Pca::MergeSdb::Utils::TempFilePathHolder::~TempFilePathHolder((Pca::MergeSdb::Utils::TempFilePathHolder *)&v332);
      Pca::MergeSdb::Utils::TempFilePathHolder::~TempFilePathHolder((Pca::MergeSdb::Utils::TempFilePathHolder *)&lpNewFileName);
      wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(&lpFileName);
      wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(&v334);
      std::list<Pca::MergeSdb::PreviousMergeDbInfo>::clear(&v327);
      operator delete(v327);
      wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(&v336);
      wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(&v337);
      if ( hKey )
        RegCloseKey(hKey);
      std::list<Pca::MergeSdb::Utils::RegistrationInfo>::~list<Pca::MergeSdb::Utils::RegistrationInfo>(&v330);
      wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(&v335);
      if ( v320 )
        RegCloseKey(v320);
      v233 = v235;
LABEL_472:
      Pca::MergeSdb::Utils::SdbFileData::~SdbFileData((Pca::MergeSdb::Utils::SdbFileData *)v362);
      wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(&v326);
      wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(&v341);
      wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(Stra);
      wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(&v338);
      Pca::MergeSdb::Utils::SdbFileData::~SdbFileData((Pca::MergeSdb::Utils::SdbFileData *)v359);
      wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(&lpMem);
      wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(&FileName);
      return v233;
    }
    v249 = v339;
    v250 = FileName;
    if ( v339 )
      v250 = v34;
    v251 = -1;
    do
      ++v251;
    while ( v250[v251] );
    v252 = v251 + 20;
    Pca::MergeSdb::Utils::TempFilePathHolder::Alloc((void **)&v332, v251 + 20);
    if ( !v332 )
    {
      Pca::MergeSdb::Utils::SdbFileData::~SdbFileData((Pca::MergeSdb::Utils::SdbFileData *)v364);
      Pca::MergeSdb::Utils::TempFilePathHolder::~TempFilePathHolder((Pca::MergeSdb::Utils::TempFilePathHolder *)&v332);
      Pca::MergeSdb::Utils::TempFilePathHolder::~TempFilePathHolder((Pca::MergeSdb::Utils::TempFilePathHolder *)&lpNewFileName);
      wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(&lpFileName);
      wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(&v334);
      std::list<Pca::MergeSdb::PreviousMergeDbInfo>::clear(&v327);
      operator delete(v327);
      wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(&v336);
      wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(&v337);
      if ( hKey )
        RegCloseKey(hKey);
      std::list<Pca::MergeSdb::Utils::RegistrationInfo>::~list<Pca::MergeSdb::Utils::RegistrationInfo>(&v330);
      wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(&v335);
      if ( v320 )
        RegCloseKey(v320);
      v233 = 14;
      goto LABEL_472;
    }
    v253 = FileName;
    if ( v249 )
      v253 = v34;
    v254 = StringCchCopyW((unsigned __int16 *)v332, v252, v253);
    v233 = v254;
    if ( v254 < 0 )
    {
      if ( (v254 & 0x1FFF0000) == 0x70000 )
        v233 = (unsigned __int16)v254;
      v258 = "Failed to copy sdb path to redirect path (%d)";
      v259 = 2603;
    }
    else
    {
      v255 = wcsrchr(v332, 0x5Cu);
      if ( !v255 )
      {
        AslLogCallPrintf(
          1,
          "MergeSdb_FindAndMergeForTarget",
          2610,
          "Failed to find the last backslash in the original sdb full path.");
        Pca::MergeSdb::Utils::SdbFileData::~SdbFileData((Pca::MergeSdb::Utils::SdbFileData *)v364);
        Pca::MergeSdb::Utils::TempFilePathHolder::~TempFilePathHolder((Pca::MergeSdb::Utils::TempFilePathHolder *)&v332);
        Pca::MergeSdb::Utils::TempFilePathHolder::~TempFilePathHolder((Pca::MergeSdb::Utils::TempFilePathHolder *)&lpNewFileName);
        wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(&lpFileName);
        wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(&v334);
        std::list<Pca::MergeSdb::PreviousMergeDbInfo>::clear(&v327);
        operator delete(v327);
        wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(&v336);
        wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(&v337);
        if ( hKey )
          RegCloseKey(hKey);
        std::list<Pca::MergeSdb::Utils::RegistrationInfo>::~list<Pca::MergeSdb::Utils::RegistrationInfo>(&v330);
        wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(&v335);
        if ( v320 )
          RegCloseKey(v320);
        v233 = 1359;
        goto LABEL_472;
      }
      v255[1] = 0;
      v256 = StringCchCatW((unsigned __int16 *)v332, v252, v366);
      v233 = v256;
      if ( v256 < 0 )
      {
        if ( (v256 & 0x1FFF0000) == 0x70000 )
          v233 = (unsigned __int16)v256;
        v258 = "Failed to concat the registered filename to the redirect full path (%d)";
        v259 = 2624;
      }
      else
      {
        i = 0;
        v257 = MoveFileExW(lpNewFileName, v332, 0xBu);
        if ( !PcaFailedGle(&i, v257) )
        {
          Pca::MergeSdb::Utils::TempFilePathHolder::Delete(&lpNewFileName);
          if ( v317 )
          {
            v261 = RemoveDirectoryW((LPCWSTR)v206);
            if ( PcaFailedGle(&i, v261) )
              AslLogCallPrintf(
                1,
                "MergeSdb_FindAndMergeForTarget",
                2643,
                "Failed to delete apppatch temp path, swallowing (%d)",
                i);
          }
          v262 = Pca::MergeSdb::Utils::CopyAclsFromParentDir((LPWSTR)v332, v260);
          v233 = v262;
          if ( v262 )
          {
            LODWORD(phkResult) = v262;
            AslLogCallPrintf(
              1,
              "MergeSdb_FindAndMergeForTarget",
              2652,
              "Unable to copy ACLs from parent (%d)",
              phkResult);
          }
          else
          {
            v265 = lambda_ce78dd138d137ef97cf3e4f50eb625f5_::operator()(&v343, v263, v264);
            v233 = v265;
            if ( v265 )
            {
              LODWORD(phkResult) = v265;
              AslLogCallPrintf(
                1,
                "MergeSdb_FindAndMergeForTarget",
                2658,
                "Unable to open SdbUpdates key (%d)",
                phkResult);
            }
            else
            {
              v347[0] = 0;
              v266 = Pca::MergeSdb::Utils::RegUtil::ReadRegValue(v320, L"MergeVer", v347);
              v233 = v266;
              if ( (v266 & 0xFFFFFFFD) != 0 )
              {
                LODWORD(phkResult) = v266;
                AslLogCallPrintf(
                  1,
                  "MergeSdb_FindAndMergeForTarget",
                  2665,
                  "Failed to read the merge version from SdbUpdates key (%d)",
                  phkResult);
              }
              else
              {
                v267 = v365;
                if ( v249 )
                  v267 = v326;
                v268 = MergeSdbp_CommitSdbUpdatesKeyValueAndVersionTransacted(v320, v347[0], v267, v366, 0);
                v233 = v268;
                if ( !v268 )
                {
                  if ( !v249 )
                  {
                    if ( v35 )
                    {
                      v269 = MergeSdbp_CommitSdbUpdatesKeyValueAndVersionTransacted(v320, 0, v326, 0, 1);
                      if ( v269 )
                        AslLogCallPrintf(
                          1,
                          "MergeSdb_FindAndMergeForTarget",
                          2691,
                          "Failed to delete stub redirect value from SdbUpdates (%d)",
                          v269);
                    }
                  }
                  Pca::MergeSdb::Utils::TempFilePathHolder::Clear((Pca::MergeSdb::Utils::TempFilePathHolder *)&v332);
                  Pca::MergeSdb::Utils::SdbFileData::~SdbFileData((Pca::MergeSdb::Utils::SdbFileData *)v364);
                  Pca::MergeSdb::Utils::TempFilePathHolder::~TempFilePathHolder((Pca::MergeSdb::Utils::TempFilePathHolder *)&v332);
                  Pca::MergeSdb::Utils::TempFilePathHolder::~TempFilePathHolder((Pca::MergeSdb::Utils::TempFilePathHolder *)&lpNewFileName);
                  wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(&lpFileName);
                  wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(&v334);
                  std::list<Pca::MergeSdb::PreviousMergeDbInfo>::clear(&v327);
                  operator delete(v327);
                  wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(&v336);
                  wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(&v337);
                  if ( hKey )
                    RegCloseKey(hKey);
                  std::list<Pca::MergeSdb::Utils::RegistrationInfo>::~list<Pca::MergeSdb::Utils::RegistrationInfo>(&v330);
                  wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(&v335);
                  if ( v320 )
                    RegCloseKey(v320);
                  Pca::MergeSdb::Utils::SdbFileData::~SdbFileData((Pca::MergeSdb::Utils::SdbFileData *)v362);
                  wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(&v326);
                  wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(&v341);
                  wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(Stra);
                  wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(&v338);
                  Pca::MergeSdb::Utils::SdbFileData::~SdbFileData((Pca::MergeSdb::Utils::SdbFileData *)v359);
                  wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(&lpMem);
                  wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(&FileName);
                  return 0;
                }
                LODWORD(phkResultc) = v268;
                AslLogCallPrintf(
                  1,
                  "MergeSdb_FindAndMergeForTarget",
                  2678,
                  "Failed to write final data transaction to SdbUpdates key (%d)",
                  phkResultc);
              }
            }
          }
          goto LABEL_461;
        }
        v233 = i;
        v258 = "Failed to move merged sdb to appPatch dir (%d)";
        v259 = 2635;
      }
    }
    LODWORD(phkResult) = v233;
    AslLogCallPrintf(1, "MergeSdb_FindAndMergeForTarget", v259, v258, phkResult);
LABEL_461:
    Pca::MergeSdb::Utils::SdbFileData::~SdbFileData((Pca::MergeSdb::Utils::SdbFileData *)v364);
    goto LABEL_381;
  }
  v221 = L"entirely";
  if ( !v317 )
    v221 = L"sufficiently";
  LODWORD(lpcbMaxSubKeyLen) = v331;
  AslLogCallPrintf(
    3,
    "MergeSdb_FindAndMergeForTarget",
    2374,
    "Redirected merge sdb stub is already %S up-to-date with %d merges: '%S' -> '%S'",
    v221,
    lpcbMaxSubKeyLen,
    FileName,
    v35);
  if ( !v145 )
    goto LABEL_317;
  v224 = lambda_ce78dd138d137ef97cf3e4f50eb625f5_::operator()(&v343, v222, v223);
  TempPath2W = v224;
  if ( !v224 )
  {
    v224 = MergeSdbp_CommitSdbUpdatesKeyValueAndVersionTransacted(v320, 0, (const unsigned __int16 *)lpMem, 0, 1);
    TempPath2W = v224;
    if ( v224 )
    {
      v225 = "Failed to delete redirect value from SdbUpdates (%d)";
      v226 = 2390;
      goto LABEL_357;
    }
LABEL_317:
    std::list<Pca::MergeSdb::PreviousMergeDbInfo>::clear(&v327);
    operator delete(v327);
    goto LABEL_520;
  }
  v225 = "Unable to open SdbUpdates key (%d)";
  v226 = 2381;
LABEL_357:
  LODWORD(phkResultb) = v224;
  AslLogCallPrintf(1, "MergeSdb_FindAndMergeForTarget", v226, v225, phkResultb);
  std::list<Pca::MergeSdb::PreviousMergeDbInfo>::clear(&v327);
  operator delete(v327);
LABEL_222:
  if ( v117 )
  {
    v148 = GetProcessHeap();
    HeapFree(v148, 0, v117);
  }
  v149 = GetProcessHeap();
  HeapFree(v149, 0, v84);
  if ( hKey )
    RegCloseKey(hKey);
  std::list<Pca::MergeSdb::Utils::RegistrationInfo>::~list<Pca::MergeSdb::Utils::RegistrationInfo>(&v330);
  if ( v58 )
  {
    v150 = GetProcessHeap();
    HeapFree(v150, 0, v58);
  }
  if ( v320 )
    RegCloseKey(v320);
  Pca::MergeSdb::Utils::SdbFileData::~SdbFileData((Pca::MergeSdb::Utils::SdbFileData *)v362);
  v151 = v326;
  if ( v326 )
  {
    v152 = GetProcessHeap();
    HeapFree(v152, 0, v151);
  }
  if ( v35 )
  {
    v153 = GetProcessHeap();
    HeapFree(v153, 0, v35);
  }
  if ( v34 )
  {
    v154 = GetProcessHeap();
    HeapFree(v154, 0, v34);
  }
LABEL_236:
  v155 = GetProcessHeap();
  HeapFree(v155, 0, v145);
LABEL_237:
  Pca::MergeSdb::Utils::SdbFileData::~SdbFileData((Pca::MergeSdb::Utils::SdbFileData *)v359);
  v156 = lpMem;
  if ( lpMem )
  {
    v157 = GetProcessHeap();
    HeapFree(v157, 0, v156);
  }
  v158 = (WCHAR *)FileName;
  if ( FileName )
  {
    v159 = GetProcessHeap();
    HeapFree(v159, 0, v158);
  }
  return TempPath2W;
}

```

## disassembly

```asm
0x140024958  mov     [rsp-8+arg_10], rbx
0x14002495d  push    rbp
0x14002495e  push    rsi
0x14002495f  push    rdi
0x140024960  push    r12
0x140024962  push    r13
0x140024964  push    r14
0x140024966  push    r15
0x140024968  lea     rbp, [rsp-3A0h]
0x140024970  sub     rsp, 4A0h
0x140024977  mov     rax, cs:__security_cookie
0x14002497e  xor     rax, rsp
0x140024981  mov     [rbp+3D0h+var_40], rax
0x140024988  xor     r14d, r14d
0x14002498b  mov     [rbp+3D0h+var_3C8], r9d
0x14002498f  mov     [rsp+4D0h+var_460], r8d
0x140024994  mov     rbx, rdx
0x140024997  mov     rdi, rcx
0x14002499a  test    rcx, rcx
0x14002499d  jz      loc_140024A58
0x1400249a3  cmp     [rcx], r14w
0x1400249a7  jz      loc_140024A58
0x1400249ad  or      r12, 0FFFFFFFFFFFFFFFFh
0x1400249b1  test    rdx, rdx
0x1400249b4  jnz     short loc_1400249F2
0x1400249b6  mov     dword ptr [rbp+3D0h+var_3F0], 0FFFFFFFFh
0x1400249bd  call    MergeSdb_RemoveUnusedSdbFiles
0x1400249c2  mov     ebx, eax
0x1400249c4  test    eax, eax
0x1400249c6  jz      loc_140024AA5
0x1400249cc  lea     r9, aFailedToRemove; "Failed to remove merged sdb files no lo"...
0x1400249d3  mov     dword ptr [rsp+4D0h+phkResult], eax
0x1400249d7  mov     r8d, 71Ah
0x1400249dd  lea     rdx, aMergesdbFindan_0; "MergeSdb_FindAndMergeForTarget"
0x1400249e4  mov     ecx, 1
0x1400249e9  call    AslLogCallPrintf
0x1400249ee  mov     eax, ebx
0x1400249f0  jmp     short loc_140024A5D
0x1400249f2  mov     r15d, r14d
0x1400249f5  mov     dword ptr [rbp+3D0h+var_3F0], r14d
0x1400249f9  cmp     r14w, [rdx]
0x1400249fd  jz      short loc_1400249BD
0x1400249ff  lea     rsi, qword_140031120
0x140024a06  xor     r13d, r13d
0x140024a09  mov     rdx, [rsi+8]; String2
0x140024a0d  mov     r14, r12
0x140024a10  inc     r14
0x140024a13  cmp     [rdx+r14*2], r13w
0x140024a18  jnz     short loc_140024A10
0x140024a1a  mov     r8, r14; MaxCount
0x140024a1d  mov     rcx, rbx; String1
0x140024a20  call    cs:__imp__wcsnicmp
0x140024a26  test    eax, eax
0x140024a28  jz      short loc_140024A87
0x140024a2a  add     rsi, 18h
0x140024a2e  lea     rax, qword_140031198
0x140024a35  cmp     rsi, rax
0x140024a38  jnz     short loc_140024A09
0x140024a3a  lea     r9, aInvalidSdbSour; "Invalid SDB source."
0x140024a41  mov     r8d, 712h
0x140024a47  lea     rdx, aMergesdbFindan_0; "MergeSdb_FindAndMergeForTarget"
0x140024a4e  mov     ecx, 1
0x140024a53  call    AslLogCallPrintf
0x140024a58  mov     eax, 57h ; 'W'
0x140024a5d  mov     rcx, [rbp+3D0h+var_40]
0x140024a64  xor     rcx, rsp; StackCookie
0x140024a67  call    __security_check_cookie
0x140024a6c  mov     rbx, [rsp+4D0h+arg_10]
0x140024a74  add     rsp, 4A0h
0x140024a7b  pop     r15
0x140024a7d  pop     r14
0x140024a7f  pop     r13
0x140024a81  pop     r12
0x140024a83  pop     rdi
0x140024a84  pop     rsi
0x140024a85  pop     rbp
0x140024a86  retn
0x140024a87  or      r15d, [rsi+4]
0x140024a8b  lea     rbx, [rbx+r14*2]
0x140024a8f  xor     r14d, r14d
0x140024a92  mov     dword ptr [rbp+3D0h+var_3F0], r15d
0x140024a96  cmp     r14w, [rbx]
0x140024a9a  jnz     loc_1400249FF
0x140024aa0  jmp     loc_1400249BD
0x140024aa5  call    ?MergeSdbp_RemoveUnusedSdbRegistrationFiles@@YAKXZ; MergeSdbp_RemoveUnusedSdbRegistrationFiles(void)
0x140024aaa  lea     r15, aMergesdbFindan_0; "MergeSdb_FindAndMergeForTarget"
0x140024ab1  mov     r13d, 1
0x140024ab7  test    eax, eax
0x140024ab9  jz      short loc_140024AD7
0x140024abb  lea     r9, aFailedToRemove_0; "Failed to remove merge input sdb files "...
0x140024ac2  mov     dword ptr [rsp+4D0h+phkResult], eax
0x140024ac6  mov     r8d, 723h
0x140024acc  mov     rdx, r15
0x140024acf  mov     ecx, r13d
0x140024ad2  call    AslLogCallPrintf
0x140024ad7  mov     edx, 5Ch ; '\'; Ch
0x140024adc  mov     [rbp+3D0h+FileName], r14
0x140024ae0  mov     rcx, rdi; Str
0x140024ae3  mov     [rbp+3D0h+lpMem], r14
0x140024ae7  call    cs:__imp_wcsrchr
0x140024aed  mov     rsi, rax
0x140024af0  test    rax, rax
0x140024af3  jnz     loc_140024C3F
0x140024af9  lea     rdx, [rbp+3D0h+FileName]
0x140024afd  lea     rcx, aSystemrootAppp_0; "%SYSTEMROOT%\\AppPatch"
0x140024b04  call    ??$ExpandEnvironmentStringsW@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@$0BAA@@wil@@YAJPEBGAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@@Z; wil::ExpandEnvironmentStringsW<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>,256>(ushort const *,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &)
0x140024b09  mov     ebx, eax
0x140024b0b  test    eax, eax
0x140024b0d  js      loc_140024BCF
0x140024b13  mov     rcx, r12
0x140024b16  inc     rcx
0x140024b19  cmp     [rdi+rcx*2], r14w
0x140024b1e  jnz     short loc_140024B16
0x140024b20  mov     rdx, [rbp+3D0h+FileName]
0x140024b24  test    rdx, rdx
0x140024b27  jz      short loc_140024B38
0x140024b29  mov     rax, r12
0x140024b2c  inc     rax
0x140024b2f  cmp     [rdx+rax*2], r14w
0x140024b34  jnz     short loc_140024B2C
0x140024b36  jmp     short loc_140024B3B
0x140024b38  mov     rax, r14
0x140024b3b  mov     [rbp+3D0h+var_408], rcx
0x140024b3f  lea     r9, [rbp+3D0h+var_410]
0x140024b43  lea     rcx, asc_1400326D0; "\\"
0x140024b4a  mov     [rbp+3D0h+Str], rdx
0x140024b4e  mov     [rbp+3D0h+var_380], rcx
0x140024b52  lea     r8, [rbp+3D0h+var_380]
0x140024b56  lea     rcx, [rbp+3D0h+FileName]
0x140024b5a  mov     [rbp+3D0h+var_410], rdi
0x140024b5e  lea     rdx, [rbp+3D0h+Str]
0x140024b62  mov     [rbp+3D0h+var_378], r13
0x140024b66  mov     [rbp+3D0h+var_358], rax
0x140024b6a  call    ??$str_build_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@Ustring_view_t@details@2@U342@U342@@details@wil@@YAJAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@1@Ustring_view_t@01@11@Z; wil::details::str_build_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>,wil::details::string_view_t,wil::details::string_view_t,wil::details::string_view_t>(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &,wil::details::string_view_t,wil::details::string_view_t,wil::details::string_view_t)
0x140024b6f  mov     ebx, eax
0x140024b71  test    eax, eax
0x140024b73  js      short loc_140024BCF
0x140024b75  mov     r8, r12
0x140024b78  mov     [rsp+4D0h+var_46C], r14d
0x140024b7d  mov     rdx, rdi
0x140024b80  lea     rcx, [rbp+3D0h+var_350]
0x140024b87  call    ??$make_unique_string_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBG_K@Z; wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(ushort const *,unsigned __int64)
0x140024b8c  mov     r14, [rbp+3D0h+lpMem]
0x140024b90  mov     rsi, [rbp+3D0h+var_350]
0x140024b97  test    r14, r14
0x140024b9a  jz      short loc_140024BC0
0x140024b9c  call    cs:__imp_GetLastError
0x140024ba2  mov     ebx, eax
0x140024ba4  call    cs:__imp_GetProcessHeap
0x140024baa  mov     r8, r14; lpMem
0x140024bad  xor     edx, edx; dwFlags
0x140024baf  mov     rcx, rax; hHeap
0x140024bb2  call    cs:__imp_HeapFree
0x140024bb8  mov     ecx, ebx; dwErrCode
0x140024bba  call    cs:__imp_SetLastError
0x140024bc0  xor     r14d, r14d
0x140024bc3  mov     [rbp+3D0h+var_350], r14
0x140024bca  jmp     loc_140024CE9
0x140024bcf  and     eax, 1FFF0000h
0x140024bd4  cmp     eax, 70000h
0x140024bd9  jnz     short loc_140024BDE
0x140024bdb  movzx   ebx, bx
0x140024bde  mov     eax, ebx
0x140024be0  mov     dword ptr [rsp+4D0h+phkResult], ebx
0x140024be4  lea     r9, aFailedToExpand; "Failed to expand / concat full sdb file"...
0x140024beb  mov     r8d, 738h
0x140024bf1  mov     rdx, r15
0x140024bf4  mov     ecx, r13d
0x140024bf7  call    AslLogCallPrintf
0x140024bfc  mov     rdi, [rbp+3D0h+lpMem]
0x140024c00  test    rdi, rdi
0x140024c03  jz      short loc_140024C19
0x140024c05  call    cs:__imp_GetProcessHeap
0x140024c0b  mov     r8, rdi; lpMem
0x140024c0e  xor     edx, edx; dwFlags
0x140024c10  mov     rcx, rax; hHeap
0x140024c13  call    cs:__imp_HeapFree
0x140024c19  mov     rdi, [rbp+3D0h+FileName]
0x140024c1d  test    rdi, rdi
0x140024c20  jz      loc_1400249EE
0x140024c26  call    cs:__imp_GetProcessHeap
0x140024c2c  mov     r8, rdi; lpMem
0x140024c2f  xor     edx, edx; dwFlags
0x140024c31  mov     rcx, rax; hHeap
0x140024c34  call    cs:__imp_HeapFree
0x140024c3a  jmp     loc_1400249EE
0x140024c3f  mov     r8, r12
0x140024c42  lea     rcx, [rbp+3D0h+var_348]
0x140024c49  mov     rdx, rdi
0x140024c4c  call    ??$make_unique_string_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBG_K@Z; wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(ushort const *,unsigned __int64)
0x140024c51  mov     r14, [rbp+3D0h+FileName]
0x140024c55  xor     ebx, ebx
0x140024c57  mov     r12, [rbp+3D0h+var_348]
0x140024c5e  test    r14, r14
0x140024c61  jz      short loc_140024C89
0x140024c63  call    cs:__imp_GetLastError
0x140024c69  mov     ebx, eax
0x140024c6b  call    cs:__imp_GetProcessHeap
0x140024c71  mov     r8, r14; lpMem
0x140024c74  xor     edx, edx; dwFlags
0x140024c76  mov     rcx, rax; hHeap
0x140024c79  call    cs:__imp_HeapFree
0x140024c7f  mov     ecx, ebx; dwErrCode
0x140024c81  call    cs:__imp_SetLastError
0x140024c87  xor     ebx, ebx
0x140024c89  mov     [rbp+3D0h+FileName], r12
0x140024c8d  lea     rdx, [rsi+2]
0x140024c91  or      r12, 0FFFFFFFFFFFFFFFFh
0x140024c95  mov     [rbp+3D0h+var_348], rbx
0x140024c9c  mov     r8, r12
0x140024c9f  lea     rcx, [rbp+3D0h+var_340]
0x140024ca6  call    ??$make_unique_string_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBG_K@Z; wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(ushort const *,unsigned __int64)
0x140024cab  mov     r14, [rbp+3D0h+lpMem]
0x140024caf  mov     rsi, [rbp+3D0h+var_340]
0x140024cb6  test    r14, r14
0x140024cb9  jz      short loc_140024CDF
0x140024cbb  call    cs:__imp_GetLastError
0x140024cc1  mov     ebx, eax
0x140024cc3  call    cs:__imp_GetProcessHeap
0x140024cc9  mov     r8, r14; lpMem
0x140024ccc  xor     edx, edx; dwFlags
0x140024cce  mov     rcx, rax; hHeap
0x140024cd1  call    cs:__imp_HeapFree
0x140024cd7  mov     ecx, ebx; dwErrCode
0x140024cd9  call    cs:__imp_SetLastError
0x140024cdf  xor     r14d, r14d
0x140024ce2  mov     [rbp+3D0h+var_340], r14
0x140024ce9  mov     rbx, [rbp+3D0h+FileName]
0x140024ced  mov     [rbp+3D0h+lpMem], rsi
0x140024cf1  test    rbx, rbx
0x140024cf4  jz      loc_1400273BA
0x140024cfa  test    rsi, rsi
0x140024cfd  jz      loc_1400273D7
0x140024d03  mov     rcx, rbx; FileName
0x140024d06  call    cs:__imp_RtlDoesFileExists_U
0x140024d0c  test    al, al
0x140024d0e  jz      loc_14002725B
0x140024d14  lea     rcx, [rbp+3D0h+var_310]; this
0x140024d1b  call    ??0SdbFileData@Utils@MergeSdb@Pca@@QEAA@XZ; Pca::MergeSdb::Utils::SdbFileData::SdbFileData(void)
0x140024d20  mov     r8, [rbp+3D0h+lpMem]; unsigned __int16 *
0x140024d24  lea     rcx, [rbp+3D0h+var_310]; this
0x140024d2b  mov     rdx, [rbp+3D0h+FileName]; FileName
0x140024d2f  call    ?LoadFromSdbFile@SdbFileData@Utils@MergeSdb@Pca@@QEAAKPEBG0@Z; Pca::MergeSdb::Utils::SdbFileData::LoadFromSdbFile(ushort const *,ushort const *)
0x140024d34  mov     esi, eax
0x140024d36  test    eax, eax
0x140024d38  jz      short loc_140024DA8
0x140024d3a  mov     dword ptr [rsp+4D0h+lpcbMaxSubKeyLen], eax
0x140024d3e  lea     r9, aFailedToReadIn_0; "Failed to read information from orignal"...
0x140024d45  mov     r8d, 752h
0x140024d4b  mov     [rsp+4D0h+phkResult], rdi
0x140024d50  mov     rdx, r15
0x140024d53  mov     ecx, r13d
0x140024d56  call    AslLogCallPrintf
0x140024d5b  lea     rcx, [rbp+3D0h+var_310]; this
0x140024d62  call    ??1SdbFileData@Utils@MergeSdb@Pca@@QEAA@XZ; Pca::MergeSdb::Utils::SdbFileData::~SdbFileData(void)
0x140024d67  mov     rbx, [rbp+3D0h+lpMem]
0x140024d6b  test    rbx, rbx
0x140024d6e  jz      short loc_140024D84
0x140024d70  call    cs:__imp_GetProcessHeap
0x140024d76  mov     r8, rbx; lpMem
0x140024d79  xor     edx, edx; dwFlags
0x140024d7b  mov     rcx, rax; hHeap
0x140024d7e  call    cs:__imp_HeapFree
0x140024d84  mov     rbx, [rbp+3D0h+FileName]
0x140024d88  test    rbx, rbx
0x140024d8b  jz      short loc_140024DA1
0x140024d8d  call    cs:__imp_GetProcessHeap
0x140024d93  mov     r8, rbx; lpMem
0x140024d96  xor     edx, edx; dwFlags
0x140024d98  mov     rcx, rax; hHeap
0x140024d9b  call    cs:__imp_HeapFree
0x140024da1  mov     eax, esi
0x140024da3  jmp     loc_140024A5D
0x140024da8  mov     rdx, [rbp+3D0h+FileName]
0x140024dac  lea     rcx, [rbp+3D0h+var_3D0]
0x140024db0  mov     [rbp+3D0h+var_3D0], r14
0x140024db4  call    ?MergeSdbp_GetRedirectedSdbPath@@YA_NAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@PEBG@Z; MergeSdbp_GetRedirectedSdbPath(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &,ushort const *)
0x140024db9  mov     rdx, [rbp+3D0h+lpMem]
0x140024dbd  lea     rcx, [rbp+3D0h+Str]
0x140024dc1  mov     [rbp+3D0h+Str], r14
0x140024dc5  call    ?MergeSdbp_GetManifestedStub@@YA_NAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@PEBG@Z; MergeSdbp_GetManifestedStub(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &,ushort const *)
0x140024dca  mov     rdi, [rbp+3D0h+Str]
0x140024dce  mov     rsi, r14
0x140024dd1  mov     [rbp+3D0h+var_3C0], r14
0x140024dd5  mov     [rbp+3D0h+var_438], r14
0x140024dd9  test    rdi, rdi
0x140024ddc  jz      short loc_140024E58
0x140024dde  mov     rdx, rdi
0x140024de1  lea     rcx, [rbp+3D0h+var_3C0]
0x140024de5  call    ?MergeSdbp_GetRedirectedSdbPath@@YA_NAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@PEBG@Z; MergeSdbp_GetRedirectedSdbPath(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &,ushort const *)
0x140024dea  mov     edx, 5Ch ; '\'; Ch
0x140024def  mov     rcx, rdi; Str
0x140024df2  call    cs:__imp_wcsrchr
0x140024df8  test    rax, rax
0x140024dfb  jz      short loc_140024E52
0x140024dfd  lea     rdx, [rax+2]
0x140024e01  mov     r8, r12
0x140024e04  lea     rcx, [rbp+3D0h+var_338]
0x140024e0b  call    ??$make_unique_string_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBG_K@Z; wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(ushort const *,unsigned __int64)
0x140024e10  mov     rsi, [rbp+3D0h+var_438]
  ... truncated ...
```
