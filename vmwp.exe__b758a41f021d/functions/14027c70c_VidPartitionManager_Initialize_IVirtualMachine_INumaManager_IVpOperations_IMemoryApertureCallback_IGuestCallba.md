# VidPartitionManager::Initialize(IVirtualMachine *,INumaManager *,IVpOperations *,IMemoryApertureCallback *,IGuestCallback *,void *,void *,Config::VmWorkerProcess::ProcessorSettings const &,Config::VmWorkerProcess::MemorySettings const &,_HV_PARTITION_CREATION_PROPERTIES_V2 const &,_HV_PARTITION_SYNTHETIC_PROCESSOR_FEATURES const &,_VMM_PARTITION_PROPERTIES const &)

- ea: `0x14027c70c`
- end: `0x14027f2eb`
- name: `?Initialize@VidPartitionManager@@AEAAJPEAUIVirtualMachine@@PEAUINumaManager@@PEAUIVpOperations@@PEAVIMemoryApertureCallback@@PEAUIGuestCallback@@PEAX5AEBUProcessorSettings@VmWorkerProcess@Config@@AEBUMemorySettings@89@AEBU_HV_PARTITION_CREATION_PROPERTIES_V2@@AEBT_HV_PARTITION_SYNTHETIC_PROCESSOR_FEATURES@@AEBU_VMM_PARTITION_PROPERTIES@@@Z`
- size: `11231`
- prototype: `__int64 __fastcall(VidPartitionManager *__hidden this, struct IVirtualMachine *, struct INumaManager *, struct IVpOperations *, struct IMemoryApertureCallback *, struct IGuestCallback *, void *, void *, const struct Config::VmWorkerProcess::ProcessorSettings *, const struct Config::VmWorkerProcess::MemorySettings *, const struct _HV_PARTITION_CREATION_PROPERTIES_V2 *, const union _HV_PARTITION_SYNTHETIC_PROCESSOR_FEATURES *, const struct _VMM_PARTITION_PROPERTIES *)`
- caller_count: `1`
- callee_count: `69`
- tags: `file_ops, registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x14027bd90`

## callees

- `0x14000db24`
- `0x14000dbbc`
- `0x14000dc64`
- `0x14000dcfc`
- `0x14001ec28`
- `0x140022290`
- `0x140022548`
- `0x1400364a0`
- `0x1400378c8`
- `0x14003d828`
- `0x14004ad1c`
- `0x14004fcf8`
- `0x140052d9c`
- `0x140053de8`
- `0x140053f10`
- `0x1400545bc`
- `0x140055e18`
- `0x140055f4c`
- `0x14005c4b8`
- `0x14005e524`
- `0x140065598`
- `0x140066eec`
- `0x1400690dc`
- `0x1400691b4`
- `0x140069690`
- `0x14006da84`
- `0x14006fe88`
- `0x140073f70`
- `0x140075648`
- `0x140078628`
- `0x14007a6cc`
- `0x140083990`
- `0x1400927e8`
- `0x14009394c`
- `0x14009ae9c`
- `0x1400a6fa4`
- `0x1400ba144`
- `0x1400c1de4`
- `0x1400cf7e0`
- `0x1400d924c`
- `0x1400d937c`
- `0x1400da040`
- `0x14011c570`
- `0x14011ea40`
- `0x14011edec`
- `0x14011f6fc`
- `0x140121a35`
- `0x140131414`
- `0x140138908`
- `0x1401ce318`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14027ef1e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14027f1fb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14027ef1e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14027f1fb`
- `vid!VidOpenStatisticsHandle` at `0x14027c7d3`
- `vid!VidOpenStatisticsHandle` at `0x14027c7d3`
- `vid!VidGetSystemInformation` at `0x14027d76c`
- `vid!VidGetSystemInformation` at `0x14027d76c`
- `vid!VidGetSystemTopology` at `0x14027d6e6`
- `vid!VidGetSystemTopology` at `0x14027d6e6`
- `vid!VidQueryPartitionInformation` at `0x14027e7f5`
- `vid!VidQueryPartitionInformation` at `0x14027e7f5`
- `vid!VidSetPartitionProperty` at `0x14027e56d`
- `vid!VidSetPartitionProperty` at `0x14027e56d`
- `vid!VidGetPartitionPropertyEx` at `0x14027d5a1`
- `vid!VidGetPartitionPropertyEx` at `0x14027e4b0`
- `vid!VidGetPartitionPropertyEx` at `0x14027d5a1`
- `vid!VidGetPartitionPropertyEx` at `0x14027e4b0`
- `vid!VidCreatePartition` at `0x14027e407`
- `vid!VidCreatePartition` at `0x14027e407`
- `vid!VidSetPartitionFriendlyName` at `0x14027e539`
- `vid!VidSetPartitionFriendlyName` at `0x14027e539`
- `vid!VidAttachPartition` at `0x14027e427`
- `vid!VidAttachPartition` at `0x14027e427`

## string_xrefs

- `0x14027c8e5`: `/configuration/global_settings/debug/channel_id`
- `0x14027ebcf`: `Physically backed VMs don't support deferred commit.`
- `0x14027eed6`: `Failed to copy specified hosting process name suffix into the IOCTL buffer`
- `0x14027ef89`: `Failed to create partition. GetLastError=%d .\n`
- `0x14027eb9d`: `Physically backed VMs don't support private compression stores.`

## pseudocode

```c
// Hidden C++ exception states: #wind=13
__int64 __fastcall VidPartitionManager::Initialize(
        VidPartitionManager *this,
        struct IVirtualMachine *a2,
        struct INumaManager *a3,
        struct IVpOperations *a4,
        struct IMemoryApertureCallback *a5,
        struct IGuestCallback *a6,
        void *a7,
        void *a8,
        const struct Config::VmWorkerProcess::ProcessorSettings *a9,
        const struct Config::VmWorkerProcess::MemorySettings *a10,
        const struct _HV_PARTITION_CREATION_PROPERTIES_V2 *a11,
        const union _HV_PARTITION_SYNTHETIC_PROCESSOR_FEATURES *a12,
        const struct _VMM_PARTITION_PROPERTIES *a13)
{
  const struct Config::VmWorkerProcess::MemorySettings *v16; // rsi
  __int64 **v17; // r13
  __int64 v18; // rax
  const char *v19; // r9
  __int64 v20; // rax
  int v21; // eax
  unsigned __int8 v22; // bl
  int v23; // eax
  char v25; // al
  __int64 v26; // rdx
  __int64 v27; // r8
  __int64 v28; // rdx
  unsigned int *v29; // r15
  gsl::details *v30; // rcx
  __int64 v31; // rdi
  __m128i v32; // xmm6
  gsl::details *v33; // rcx
  char *v34; // xmm6_8
  unsigned __int64 v35; // rax
  __m128i v36; // xmm6
  unsigned __int64 v37; // xmm6_8
  __int64 v38; // rax
  __int64 v39; // rdx
  gsl::details *v40; // rcx
  unsigned __int64 v41; // rbx
  __int64 v42; // rdi
  __int64 v43; // rbx
  __int64 v44; // rdi
  unsigned int v45; // ecx
  unsigned int v46; // ebx
  __int64 v47; // rax
  __int64 v48; // rbx
  unsigned int v49; // eax
  __int64 v50; // rdi
  int v51; // eax
  int v52; // eax
  int v53; // eax
  int v54; // eax
  __int64 v55; // r12
  __int64 v56; // rbx
  __int64 v57; // rax
  __int64 v58; // rax
  int v59; // edi
  __int64 v60; // rax
  __int64 v61; // rsi
  unsigned int v62; // edi
  __int64 v63; // rax
  __int64 v64; // rax
  unsigned int v65; // eax
  __int128 v66; // xmm6
  __int64 v67; // r12
  unsigned int v68; // edx
  int v69; // edx
  unsigned int v70; // eax
  __int64 *v71; // rbx
  __int64 v72; // rdx
  void (__fastcall *v73)(__int64 *, struct VmRepository **, _QWORD); // rdi
  unsigned int v74; // eax
  void *v75; // rbx
  const unsigned __int16 *v76; // r8
  VmPrefixRepository *v77; // rax
  struct VmRepository *v78; // rbx
  struct VmRepository *v79; // rdi
  __int64 v80; // rax
  __int64 v81; // r12
  __int64 v82; // rcx
  __int64 v83; // rax
  __int64 v84; // rcx
  __int64 v85; // rbx
  __int64 v86; // rax
  __int64 v87; // rcx
  __int64 v88; // rdi
  char v89; // bl
  unsigned __int64 v90; // rdi
  VidPartitionManager *v91; // rbx
  int SystemTopology; // esi
  __int64 v93; // rax
  const char *v94; // r9
  unsigned int v95; // eax
  struct IVpOperations *v96; // r12
  unsigned int v97; // ecx
  unsigned int v98; // esi
  __int64 v99; // rbx
  unsigned int v100; // ecx
  unsigned int v101; // esi
  __int64 v102; // rbx
  unsigned int v103; // ecx
  unsigned int v104; // esi
  __int64 v105; // rbx
  unsigned int v106; // ecx
  unsigned int v107; // esi
  __int64 v108; // rbx
  __int64 v109; // rbx
  __int64 v110; // rdi
  __int64 v111; // rbx
  __int64 v112; // rsi
  __int64 v113; // rdi
  struct INumaManager *v114; // rsi
  __int64 v115; // rax
  unsigned int v116; // ecx
  unsigned int v117; // ebx
  const struct Config::VmWorkerProcess::MemorySettings *v118; // r12
  int v119; // ecx
  int v120; // ecx
  unsigned int v121; // ebx
  wchar_t *v122; // rax
  __int64 v123; // rcx
  char v124; // al
  __int64 v125; // rcx
  __int64 v126; // rsi
  __int64 v127; // rax
  unsigned __int64 v128; // rdx
  __int64 v129; // rcx
  unsigned int v130; // eax
  __int64 v131; // rcx
  __int64 v132; // rax
  __int64 v133; // r9
  const unsigned __int16 *v134; // r8
  int v135; // eax
  HKEY v136; // rbx
  struct IVirtualMachine *v137; // rbx
  char v138; // di
  char v139; // al
  char v140; // bl
  unsigned int v141; // ecx
  unsigned int v142; // r12d
  __int64 v143; // rbx
  char v144; // cl
  unsigned int v145; // ecx
  unsigned int v146; // edi
  __int64 v147; // rbx
  struct IVpOperations *v148; // rbx
  unsigned int v149; // ecx
  unsigned int v150; // edi
  __int64 v151; // rbx
  struct IVpOperations *v152; // rbx
  struct IVirtualMachine *v153; // rbx
  unsigned __int64 v154; // rdi
  unsigned int v155; // ecx
  unsigned int v156; // ebx
  __int64 v157; // rax
  unsigned int v158; // eax
  __int64 v159; // rbx
  __int64 v160; // rax
  int v161; // eax
  unsigned int v162; // ecx
  unsigned int v163; // edi
  VidPartitionManager *v164; // rdi
  __int64 v165; // rbx
  __int64 v166; // rax
  __int64 Partition; // rax
  void **v168; // rsi
  const char *v169; // r9
  const struct _VMM_PARTITION_PROPERTIES *v170; // rbx
  __int64 v171; // rdi
  unsigned __int8 *v172; // rcx
  unsigned __int64 v173; // r15
  unsigned __int64 i; // rbx
  __int64 v175; // r12
  __int64 v176; // rdi
  __int64 v177; // rax
  int v178; // eax
  const char *v179; // r9
  wil *v180; // rcx
  char *v181; // rbx
  unsigned int v182; // eax
  wil *v183; // rcx
  __int64 v184; // r15
  int Instance; // eax
  struct INumaManager *v186; // r15
  int v187; // eax
  const char *v188; // r9
  unsigned __int8 v189; // dl
  unsigned __int8 v190; // r8
  __int64 v191; // r9
  __int64 v192; // rcx
  unsigned __int8 j; // dl
  unsigned int v194; // r12d
  int v195; // r12d
  const struct _tlgProvider_t *v196; // rax
  int v197; // ebx
  void *v198; // rbx
  WorkerStatsPanel *v199; // rbx
  unsigned int v200; // edi
  const unsigned __int16 *v201; // r8
  const struct _GUID *v202; // r9
  int v203; // eax
  const char *v204; // r9
  __int64 result; // rax
  unsigned int v206; // eax
  unsigned int v207; // eax
  unsigned int v208; // eax
  unsigned int v209; // eax
  unsigned int v210; // eax
  unsigned int v211; // eax
  unsigned int v212; // eax
  unsigned int v213; // eax
  unsigned int v214; // eax
  unsigned int v215; // eax
  unsigned int v216; // eax
  unsigned int v217; // eax
  int v218; // edx
  unsigned int v219; // eax
  int v220; // edx
  unsigned int v221; // eax
  int v222; // edx
  const wchar_t *v223; // r8
  unsigned int v224; // eax
  unsigned int v225; // eax
  signed int LastError; // eax
  const struct _GUID *v227; // r8
  const unsigned __int16 *v228; // r9
  unsigned int v229; // esi
  unsigned int v230; // edi
  unsigned int v231; // eax
  const struct _tlgProvider_t *v232; // rax
  int v233; // ebx
  __int64 v234; // rax
  int v235; // r8d
  int v236; // r9d
  unsigned int v237; // eax
  const struct _tlgProvider_t *v238; // rax
  int v239; // esi
  __int64 v240; // rax
  int v241; // r8d
  int v242; // r9d
  unsigned int v243; // eax
  signed int v244; // eax
  unsigned int v245; // ebx
  const struct _tlgProvider_t *v246; // rax
  int v247; // edi
  __int64 v248; // rax
  int v249; // r8d
  int v250; // r9d
  unsigned int v251; // eax
  wil *v252; // rcx
  __int64 v253; // rax
  unsigned int v254; // eax
  unsigned int v255; // eax
  unsigned int v256; // ebx
  __int64 v257; // r9
  VidPartitionManager *v258; // rbx
  unsigned int v259; // ebx
  __int64 v260; // r9
  VidPartitionManager *v261; // rbx
  __int64 v262; // rax
  __int64 v263; // rax
  int v264; // [rsp+20h] [rbp-18A8h]
  int v265; // [rsp+20h] [rbp-18A8h]
  struct IVpOperations *v266; // [rsp+20h] [rbp-18A8h]
  struct IVpOperations *v267; // [rsp+20h] [rbp-18A8h]
  int v268; // [rsp+20h] [rbp-18A8h]
  int v269; // [rsp+20h] [rbp-18A8h]
  int v270; // [rsp+20h] [rbp-18A8h]
  struct IMemoryApertureCallback *v271; // [rsp+28h] [rbp-18A0h]
  struct IMemoryApertureCallback *v272; // [rsp+28h] [rbp-18A0h]
  struct IGuestCallback *v273; // [rsp+30h] [rbp-1898h]
  unsigned __int8 v274; // [rsp+40h] [rbp-1888h] BYREF
  unsigned __int8 v275; // [rsp+41h] [rbp-1887h]
  __int64 v276; // [rsp+48h] [rbp-1880h] BYREF
  int v277; // [rsp+50h] [rbp-1878h]
  unsigned int v278; // [rsp+54h] [rbp-1874h] BYREF
  __int64 v279; // [rsp+58h] [rbp-1870h] BYREF
  __int64 v280; // [rsp+60h] [rbp-1868h] BYREF
  struct INumaManager *v281; // [rsp+68h] [rbp-1860h]
  unsigned int *v282; // [rsp+70h] [rbp-1858h]
  struct INumaManager *v283; // [rsp+78h] [rbp-1850h] BYREF
  __m128i v284; // [rsp+80h] [rbp-1848h] BYREF
  VidPartitionManager *v285; // [rsp+90h] [rbp-1838h]
  struct IVpOperations *v286; // [rsp+98h] [rbp-1830h]
  struct IGuestCallback *v287; // [rsp+A0h] [rbp-1828h] BYREF
  VidPartitionManager *v288; // [rsp+A8h] [rbp-1820h]
  HKEY v289; // [rsp+B0h] [rbp-1818h]
  struct IVirtualMachine *v290; // [rsp+B8h] [rbp-1810h]
  const struct _VMM_PARTITION_PROPERTIES *v291; // [rsp+C0h] [rbp-1808h]
  const std::exception *v292; // [rsp+C8h] [rbp-1800h] BYREF
  unsigned int HvCompatibilityVersion; // [rsp+D0h] [rbp-17F8h] BYREF
  unsigned int v294; // [rsp+D4h] [rbp-17F4h] BYREF
  unsigned __int8 v295; // [rsp+D8h] [rbp-17F0h] BYREF
  char *v296; // [rsp+DCh] [rbp-17ECh] BYREF
  unsigned int v297; // [rsp+E4h] [rbp-17E4h] BYREF
  char *v298; // [rsp+E8h] [rbp-17E0h] BYREF
  struct VmRepository *v299[2]; // [rsp+F0h] [rbp-17D8h] BYREF
  void *v300[2]; // [rsp+100h] [rbp-17C8h] BYREF
  __int128 v301; // [rsp+110h] [rbp-17B8h]
  __int128 v302; // [rsp+120h] [rbp-17A8h]
  __int64 v303; // [rsp+130h] [rbp-1798h] BYREF
  const struct Config::VmWorkerProcess::MemorySettings *v304; // [rsp+138h] [rbp-1790h] BYREF
  HKEY phkResult; // [rsp+140h] [rbp-1788h] BYREF
  _QWORD v306[2]; // [rsp+148h] [rbp-1780h] BYREF
  unsigned int v307; // [rsp+158h] [rbp-1770h] BYREF
  char *v308; // [rsp+160h] [rbp-1768h] BYREF
  __int128 v309; // [rsp+168h] [rbp-1760h] BYREF
  __int64 v310; // [rsp+178h] [rbp-1750h]
  __int128 v311; // [rsp+180h] [rbp-1748h] BYREF
  __int64 v312; // [rsp+190h] [rbp-1738h]
  __int128 v313; // [rsp+198h] [rbp-1730h] BYREF
  __int64 v314; // [rsp+1A8h] [rbp-1720h]
  _BYTE v315[24]; // [rsp+1B0h] [rbp-1718h] BYREF
  __int64 v316; // [rsp+1C8h] [rbp-1700h]
  __m128i v317; // [rsp+1D0h] [rbp-16F8h]
  __int128 v318; // [rsp+1E0h] [rbp-16E8h]
  __int64 v319; // [rsp+1F0h] [rbp-16D8h]
  __int64 v320; // [rsp+1F8h] [rbp-16D0h]
  int v321; // [rsp+200h] [rbp-16C8h]
  void *v322[2]; // [rsp+210h] [rbp-16B8h] BYREF
  void *v323[2]; // [rsp+220h] [rbp-16A8h] BYREF
  __int128 v324; // [rsp+230h] [rbp-1698h] BYREF
  __int64 v325; // [rsp+240h] [rbp-1688h]
  void *Src[2]; // [rsp+248h] [rbp-1680h] BYREF
  _DWORD v327[2]; // [rsp+260h] [rbp-1668h] BYREF
  _QWORD v328[509]; // [rsp+268h] [rbp-1660h]
  _BYTE v329[1536]; // [rsp+1250h] [rbp-678h] BYREF
  char *v330[2]; // [rsp+1850h] [rbp-78h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+18C8h] [rbp+0h]

  v286 = a4;
  v281 = a3;
  v290 = a2;
  v285 = this;
  v288 = this;
  v283 = a3;
  v276 = (__int64)a4;
  v287 = a6;
  v16 = a10;
  v304 = a10;
  v291 = a13;
  v17 = (__int64 **)((char *)this + 104);
  Vml::VmReferencePtr<IVirtualMachine,Vml::VmWeakReferenceTraits>::Reset((char *)this + 104);
  try
  {
    *((_BYTE *)this + 114) = (*(unsigned int (__fastcall **)(struct IVpOperations *))(*(_QWORD *)a4 + 184LL))(a4) != 0;
    v18 = VidOpenStatisticsHandle();
    *((_QWORD *)this + 10) = v18;
    if ( (unsigned __int64)(v18 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
    {
      v20 = (*(__int64 (__fastcall **)(__int64 *))(**v17 + 48))(*v17);
      v21 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v20 + 152LL))(v20);
      v282 = (unsigned int *)((char *)this + 88);
      *((_DWORD *)this + 22) = v21;
      v22 = lambda_997682190daf7855ab97ce0562d05e09_::operator()();
      v274 = v22;
      v308 = 0;
      v296 = 0;
      v303 = 0;
      (*(void (__fastcall **)(__int64 *, __int64 *))(**v17 + 56))(*v17, &v303);
      *(_OWORD *)v330 = 0;
      VmRepositoryAutoLock::VmRepositoryAutoLock(v330, v303, 0);
      if ( SLODWORD(v330[1]) < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x161,
          (unsigned int)"onecore\\vm\\worker\\vidpartition\\vidpartitionmanager.cpp",
          (const char *)LODWORD(v330[1]),
          v265);
      v23 = (*(__int64 (__fastcall **)(__int64, char *))(*(_QWORD *)v303 + 288LL))(v303, (char *)&v296 + 4);
      if ( v23 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x166,
          (unsigned int)"onecore\\vm\\worker\\vidpartition\\vidpartitionmanager.cpp",
          (const char *)(unsigned int)v23,
          v265);
      (*(void (__fastcall **)(__int64, const unsigned __int16 *, char **))(*(_QWORD *)v303 + 112LL))(
        v303,
        L"/configuration/global_settings/debug/channel_id",
        &v308);
      (*(void (__fastcall **)(__int64, char **))(*(_QWORD *)v303 + 320LL))(v303, &v296);
      memset(v315, 0, sizeof(v315));
      v316 = 0;
      v317 = 0u;
      v318 = 0;
      v319 = 0;
      v320 = 0;
      v321 = 0;
      if ( !*(_BYTE *)Marshal::FromRepository<Vml::VmReferencePtr<VmRepository,Vml::VmUserReferenceTraits> const &,Config::VmWorkerProcess::TopologySettings,>(
                        v300,
                        &v303,
                        v315) )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x170,
          (unsigned int)"onecore\\vm\\worker\\vidpartition\\vidpartitionmanager.cpp",
          (const char *)0x80070057LL,
          v265);
      std::vector<std::pair<std::wstring,enum Marshal::UnmarshalError>>::_Tidy(&v300[1]);
      v277 = v319;
      v278 = v319;
      if ( (unsigned int)v319 > 3 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x175,
          (unsigned int)"onecore\\vm\\worker\\vidpartition\\vidpartitionmanager.cpp",
          (const char *)0x80070057LL,
          v265);
      if ( (_DWORD)v319 && (HIDWORD(v296) < 0x903 || (_DWORD)v296 != 1) )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x17A,
          (unsigned int)"onecore\\vm\\worker\\vidpartition\\vidpartitionmanager.cpp",
          (const char *)0x80070057LL,
          v265);
      if ( !v22 )
      {
        if ( (_DWORD)v319 != 3 || (v25 = 1, HIDWORD(v296) >= 0xB00) )
          v25 = 0;
        if ( v25 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x180,
            (unsigned int)"onecore\\vm\\worker\\vidpartition\\vidpartitionmanager.cpp",
            (const char *)0x80070057LL,
            v265);
      }
      VmRepositoryAutoLock::~VmRepositoryAutoLock((VmRepositoryAutoLock *)v330);
      v289 = (HKEY)(*(__int64 (__fastcall **)(struct INumaManager *))(*(_QWORD *)a3 + 8LL))(a3);
      v280 = (*(__int64 (__fastcall **)(HKEY))(*(_QWORD *)v289 + 88LL))(v289);
      v275 = *(_BYTE *)(v280 + 272);
      *((_BYTE *)this + 92) = v275;
      v313 = 0;
      v314 = 0;
      v309 = 0;
      v310 = 0;
      LOBYTE(v26) = 1;
      wil::details::FeatureImpl<__WilFeatureTraits_Feature_L1VH_VMMFeatures>::ReportUsage(
        `wil::Feature<__WilFeatureTraits_Feature_L1VH_VMMFeatures>::GetImpl'::`2'::impl,
        v26);
      if ( *((_BYTE *)this + 114) )
      {
        if ( *((_WORD *)v291 + 8) )
          HvPartitionPropertyPayload<_HV_PARTITION_PROPERTY_ASSIGNABLE_SYNTHETIC_PROCESSOR_FEATURES>::Initialize(&v309);
        if ( *(_WORD *)v291 )
          HvPartitionPropertyPayload<_HV_PARTITION_PROPERTY_ASSIGNABLE_SYNTHETIC_PROCESSOR_FEATURES>::Initialize(&v313);
      }
      v311 = 0;
      v312 = 0;
      v27 = *((_QWORD *)v291 + 4);
      if ( v27 )
      {
        v28 = *((_QWORD *)v291 + 8);
        if ( v28 )
          HvPartitionPropertyPayload<_HV_PARTITION_PROPERTY_PROCESSOR_FEATURES_EX>::InitializeFromBuffer(
            &v311,
            v28,
            8 * v27 + 8);
      }
      v324 = 0;
      v325 = 0;
      std::vector<enum gsl::byte>::vector<enum gsl::byte>(
        &v324,
        *((_QWORD *)&v309 + 1) + *((_QWORD *)&v311 + 1) - v311 - v309 - v313 + *((_QWORD *)&v313 + 1) + 68720LL);
      *(_OWORD *)v300 = 0;
      gsl::span<unsigned char,-1>::span<unsigned char,-1>(v300, &v324);
      v29 = (unsigned int *)v300[1];
      v330[0] = (char *)v300[0];
      v330[1] = (char *)v300[1];
      if ( (unsigned __int64)gsl::span<unsigned char,-1>::size_bytes(v330) >= 0x10B40 )
      {
        gsl::span<unsigned char,-1>::size_bytes(v330);
        memset_0(v29, 0, 0x10B40u);
        v31 = (unsigned int)gsl::narrow<unsigned int,unsigned __int64,0>(68720);
        v330[0] = 0;
        v32 = *(__m128i *)gsl::span<enum gsl::byte const,-1>::subspan(v300, v306, 68416, 304);
        v284 = v32;
        if ( (gsl::span<unsigned char,-1>::size_bytes(&v284) & 0xF) != 0
          || (v284 = v32,
              v34 = (char *)_mm_srli_si128(v32, 8).m128i_u64[0],
              v35 = gsl::span<unsigned char,-1>::size_bytes(&v284),
              gsl::details::extent_type<-1>::extent_type<-1>(v330, v35 >> 4),
              v330[1] = v34,
              v330[0] == (char *)-1LL)
          || !v34 && v330[0] )
        {
          gsl::details::terminate(v33);
          __debugbreak();
        }
        v284.m128i_i64[0] = 0;
        v36 = *(__m128i *)gsl::span<enum gsl::byte const,-1>::subspan(v300, v306, v31, -1);
        *(__m128i *)v300 = v36;
        gsl::span<unsigned char,-1>::size_bytes(v300);
        *(__m128i *)v300 = v36;
        v37 = _mm_srli_si128(v36, 8).m128i_u64[0];
        v38 = gsl::span<unsigned char,-1>::size_bytes(v300);
        gsl::details::extent_type<-1>::extent_type<-1>(&v284, v38);
        v284.m128i_i64[1] = v37;
        if ( v284.m128i_i64[0] == -1 || !v37 && v284.m128i_i64[0] )
        {
          gsl::details::terminate(v40);
          __debugbreak();
        }
        *(_QWORD *)v315 = v29;
        *(_OWORD *)&v315[8] = *(_OWORD *)v330;
        LODWORD(v316) = v31;
        v317 = v284;
        LOBYTE(v39) = 1;
        wil::details::FeatureImpl<__WilFeatureTraits_Feature_L1VH_VMMFeatures>::ReportUsage(
          `wil::Feature<__WilFeatureTraits_Feature_L1VH_VMMFeatures>::GetImpl'::`2'::impl,
          v39);
        if ( *((_BYTE *)this + 114) )
        {
          if ( *((_QWORD *)&v309 + 1) != (_QWORD)v309 )
          {
            gsl::span<unsigned char,-1>::span<unsigned char,-1>(v300, &v309);
            PartitionConfigHelper::AddProperty(v315, 589831, v300);
          }
          if ( *((_QWORD *)&v313 + 1) != (_QWORD)v313 )
          {
            gsl::span<unsigned char,-1>::span<unsigned char,-1>(v300, &v313);
            PartitionConfigHelper::AddProperty(v315, 589833, v300);
          }
        }
        if ( *((_QWORD *)&v311 + 1) != (_QWORD)v311 )
        {
          gsl::span<unsigned char,-1>::span<unsigned char,-1>(v300, &v311);
          PartitionConfigHelper::AddProperty(v315, 589838, v300);
        }
        v41 = ((unsigned __int64)v274 << 32) | 2;
        if ( (*(unsigned int (__fastcall **)(struct INumaManager *))(*(_QWORD *)v281 + 24LL))(v281) )
          v41 = (unsigned __int64)v274 << 32;
        v42 = v41 | 0x40000000;
        if ( !(*(unsigned __int8 (__fastcall **)(__int64 *))(**v17 + 216))(*v17) )
          v42 = v41;
        v43 = v42 | 0x4000000000000LL;
        if ( !(*(unsigned __int8 (__fastcall **)(__int64 *))(**v17 + 224))(*v17) )
          v43 = v42;
        v44 = v43 | 0x2000000000000LL;
        if ( !(*(unsigned __int8 (__fastcall **)(__int64 *))(**v17 + 352))(*v17) )
          v44 = v43;
        if ( (*(unsigned __int8 (__fastcall **)(__int64 *))(**v17 + 360))(*v17) )
        {
          if ( HIDWORD(v296) < 0xC04 )
            wil::details::in1diag3::Throw_Hr(
              retaddr,
              (void *)0x22B,
              (unsigned int)"onecore\\vm\\worker\\vidpartition\\vidpartitionmanager.cpp",
              (const char *)0x80070057LL,
              v265);
          v44 |= 0x40000000000000uLL;
          v45 = v29[17098];
          v29[17098] = v45 + 1;
          v46 = v45;
          *(_DWORD *)gsl::span<_HV_PARTITION_PROPERTY_ASSOC,-1>::operator[](v330, v45) = 327734;
          *(_QWORD *)(gsl::span<_HV_PARTITION_PROPERTY_ASSOC,-1>::operator[](v330, v46) + 8) = 1;
        }
        v47 = v44 | 0x400;
        if ( !*((_BYTE *)a9 + 121) )
          v47 = v44;
        v48 = v47 | 0x100000;
        if ( !*((_BYTE *)a9 + 248) )
          v48 = v47;
        if ( *((_BYTE *)a9 + 256) )
          v49 = *((_DWORD *)a9 + 63);
        else
          v49 = 0;
        v29[11] = v49;
        v50 = (*(__int64 (__fastcall **)(__int64 *))(**v17 + 464))(*v17);
        v294 = 0;
        v51 = (*(__int64 (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v50 + 88LL))(v50, &v294);
        if ( v51 < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x24F,
            (unsigned int)"onecore\\vm\\worker\\vidpartition\\vidpartitionmanager.cpp",
            (const char *)(unsigned int)v51,
            v265);
        v29[16956] &= 0xFFFFFFF0;
        v29[16956] |= v294 & 0xF;
        v297 = 0;
        v52 = (*(__int64 (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v50 + 96LL))(v50, &v297);
        if ( v52 < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x253,
            (unsigned int)"onecore\\vm\\worker\\vidpartition\\vidpartitionmanager.cpp",
            (const char *)(unsigned int)v52,
            v265);
        if ( v297 )
          v48 |= 8uLL;
        LODWORD(v298) = 0;
        v53 = (*(__int64 (__fastcall **)(__int64, char **))(*(_QWORD *)v50 + 112LL))(v50, &v298);
        if ( v53 < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x25A,
            (unsigned int)"onecore\\vm\\worker\\vidpartition\\vidpartitionmanager.cpp",
            (const char *)(unsigned int)v53,
            v265);
        if ( (_DWORD)v298 )
          v48 |= 0x10uLL;
        HvCompatibilityVersion = 0;
        v54 = (*(__int64 (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v50 + 136LL))(
                v50,
                &HvCompatibilityVersion);
        if ( v54 < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x261,
            (unsigned int)"onecore\\vm\\worker\\vidpartition\\vidpartitionmanager.cpp",
            (const char *)(unsigned int)v54,
            v265);
        if ( HvCompatibilityVersion )
          v48 |= 0x80uLL;
        v55 = v48 | 0x80000000000000LL;
        if ( !(*(unsigned __int8 (__fastcall **)(__int64 *))(**v17 + 368))(*v17) )
          v55 = v48;
        if ( (v29[16956] & 0xF) - 2 > 2 )
          goto LABEL_82;
        *((_QWORD *)v29 + 8479) = (*(__int64 (__fastcall **)(__int64 *))(**v17 + 264))(*v17);
        v56 = (*(__int64 (__fastcall **)(__int64 *))(**v17 + 272))(*v17);
        HvCompatibilityVersion = 0;
        v57 = (*(__int64 (__fastcall **)(__int64 *))(**v17 + 464))(*v17);
        (*(void (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v57 + 88LL))(v57, &HvCompatibilityVersion);
        if ( HvCompatibilityVersion == 3 )
        {
          LODWORD(v298) = 0;
          *(_OWORD *)v300 = 0;
          v301 = 0;
          v302 = 0;
          VidPartitionManager::CalculateMaxmimumTdxMigrationStreamCount(v285);
          *(_OWORD *)v300 = 0;
          v301 = 0;
          v302 = 0;
          v58 = (*(__int64 (__fastcall **)(__int64 *))(**v17 + 464))(*v17);
          (*(void (__fastcall **)(__int64, char **))(*(_QWORD *)v58 + 144LL))(v58, &v298);
          v59 = (int)v298;
          v60 = (*(__int64 (__fastcall **)(__int64 *))(**v17 + 48))(*v17);
          if ( (*(unsigned int (__fastcall **)(__int64, void **))(*(_QWORD *)v60 + 432LL))(v60, v300) )
          {
            if ( !v59 )
            {
              v61 = v29[17098];
              v29[17098] = v61 + 1;
              v62 = *((_DWORD *)v285 + 78);
              v63 = (*(__int64 (__fastcall **)(__int64 *))(**v17 + 48))(*v17);
              if ( (*(unsigned __int8 (__fastcall **)(__int64))(*(_QWORD *)v63 + 488LL))(v63) )
              {
                v64 = (*(__int64 (__fastcall **)(__int64 *))(**v17 + 48))(*v17);
                v65 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v64 + 496LL))(v64);
                if ( v62 < v65 )
                  v62 = v65;
              }
              v56 |= 4uLL;
              *(_DWORD *)gsl::span<_HV_PARTITION_PROPERTY_ASSOC,-1>::operator[](v330, v61) = 327727;
              *(_QWORD *)(gsl::span<_HV_PARTITION_PROPERTY_ASSOC,-1>::operator[](v330, v61) + 8) = v62 + 1;
              v16 = v304;
              goto LABEL_81;
            }
            if ( v59 != 1 )
            {
              v206 = wil::verify_hresult<long>(2147942487LL);
              LODWORD(v271) = v59;
              wil::details::in1diag3::Throw_HrMsg(
                retaddr,
                (void *)0x2BE,
                (unsigned int)"onecore\\vm\\worker\\vidpartition\\vidpartitionmanager.cpp",
                (const char *)v206,
                (int)"Unknown TDX migratable policy %u",
                (const char *)v271);
            }
          }
          v56 &= ~4uLL;
        }
LABEL_81:
        *((_QWORD *)v29 + 8480) = v56;
LABEL_82:
        LODWORD(v298) = v316;
        v66 = 0;
        if ( (unsigned __int64)(*((_QWORD *)v16 + 5) - 2LL) <= 1 )
        {
          if ( *((_BYTE *)v16 + 160) )
          {
            v68 = v29[12] ^ (v29[12] ^ (*((_DWORD *)v16 + 38) << 11)) & 0x7800;
          }
          else
          {
            v69 = 18432;
            if ( *((_QWORD *)v16 + 23) != 512 )
              v69 = 0x2000;
            v68 = v29[12] & 0xFFFF87FF | v69;
          }
          v29[12] = v68;
          if ( *((_BYTE *)v16 + 176) )
            v70 = v68 ^ (v68 ^ (*((_DWORD *)v16 + 42) << 15)) & 0x78000;
          else
            v70 = v68 & 0xFFF87FFF | 0x20000;
          v29[12] = v70;
          v299[0] = 0;
          v71 = *v17;
          v72 = **v17;
          v73 = *(void (__fastcall **)(__int64 *, struct VmRepository **, _QWORD))(v72 + 160);
          v74 = (*(__int64 (__fastcall **)(__int64 *))(v72 + 64))(*v17);
          v73(v71, v299, v74);
          if ( v299[0] )
          {
            v75 = operator new(0x80u);
            v300[0] = v75;
            memset_0(v75, 0, 0x80u);
            v77 = VmPrefixRepository::VmPrefixRepository((VmPrefixRepository *)v75, v299[0], v76);
            v78 = v77;
            v79 = v299[0];
            if ( v77 )
              Vml::VmSharableObject::IncrementUserCount((VmPrefixRepository *)((char *)v77 + 8));
            v299[0] = v78;
            if ( v79 )
            {
              Vml::VmSharableObject::DecrementUserCount((struct VmRepository *)((char *)v79 + 8));
              v78 = v299[0];
            }
            if ( v78 )
            {
              v80 = MemoryManager::RestoreCloneTemplateId(&MemoryManager::m_Instance, v300, v78);
              if ( *(_BYTE *)(v80 + 16) )
                v66 = *(_OWORD *)v80;
            }
          }
          v81 = v55 | 0x8000000000100LL;
          v82 = v81 | 0x1000;
          if ( !*((_BYTE *)v16 + 313) )
            v82 = v81;
          v83 = v82 | 0x2000;
          if ( !*((_BYTE *)v16 + 314) )
            v83 = v82;
          v84 = v83 | 0x4000;
          if ( !*((_BYTE *)v16 + 315) )
            v84 = v83;
          v85 = v84 | 0x20000;
          if ( !*((_BYTE *)v16 + 316) )
            v85 = v84;
          if ( *((_BYTE *)v16 + 317) )
          {
            memset_0(v327, 0, 0xFE8u);
            if ( (unsigned int)VidGetPartitionPropertyEx(-1, 589831, 0, v327) && (v328[0] & 0x100) == 0 )
              wil::details::in1diag3::Throw_Win32(
                retaddr,
                (void *)0x320,
                (unsigned int)"onecore\\vm\\worker\\vidpartition\\vidpartitionmanager.cpp",
                (const char *)0x32,
                0xFE8u);
            v85 |= 0x20000000010000uLL;
          }
          v86 = v85 | 0x8000;
          if ( !*((_BYTE *)v16 + 144) )
            v86 = v85;
          v87 = v86 | 0x40000;
          if ( !*((_BYTE *)v16 + 145) )
            v87 = v86;
          v88 = v87 | 0x400000;
          if ( !*((_BYTE *)v16 + 208) )
            v88 = v87;
          v89 = *((_BYTE *)v16 + 209);
          Vml::VmReferencePtr<VmRepository,Vml::VmUserReferenceTraits>::~VmReferencePtr<VmRepository,Vml::VmUserReferenceTraits>(v299);
          v67 = v88 | 0x200000;
          if ( !v89 )
            v67 = v88;
        }
        else
        {
          if ( *((_BYTE *)v16 + 160) || *((_BYTE *)v16 + 176) )
          {
            v214 = wil::verify_hresult<long>(3224829998LL);
            wil::details::in1diag3::Throw_HrMsg(
              retaddr,
              (void *)0x350,
              (unsigned int)"onecore\\vm\\worker\\vidpartition\\vidpartitionmanager.cpp",
              (const char *)v214,
              (int)"Physically backed VMs don't support fault clustering.",
              (const char *)v271);
          }
          if ( *((_BYTE *)v16 + 313) || *((_BYTE *)v16 + 314) || *((_BYTE *)v16 + 315) )
          {
            v213 = wil::verify_hresult<long>(3224829998LL);
            wil::details::in1diag3::Throw_HrMsg(
              retaddr,
              (void *)0x359,
              (unsigned int)"onecore\\vm\\worker\\vidpartition\\vidpartitionmanager.cpp",
              (const char *)v213,
              (int)"Physically backed VMs don't support memory heat hints.",
              (const char *)v271);
          }
          if ( *((_BYTE *)v16 + 316) )
          {
            v207 = wil::verify_hresult<long>(3224829998LL);
            wil::details::in1diag3::Throw_HrMsg(
              retaddr,
              (void *)0x360,
              (unsigned int)"onecore\\vm\\worker\\vidpartition\\vidpartitionmanager.cpp",
              (const char *)v207,
              (int)"Physically backed VMs don't support EPF.",
              (const char *)v271);
          }
          if ( *((_BYTE *)v16 + 317) )
          {
            v208 = wil::verify_hresult<long>(3224829998LL);
            wil::details::in1diag3::Throw_HrMsg(
              retaddr,
              (void *)0x367,
              (unsigned int)"onecore\\vm\\worker\\vidpartition\\vidpartitionmanager.cpp",
              (const char *)v208,
              (int)"Physically backed VMs don't support GPA pinning.",
              (const char *)v271);
          }
          if ( *((_BYTE *)v16 + 144) )
          {
            v209 = wil::verify_hresult<long>(3224829998LL);
            wil::details::in1diag3::Throw_HrMsg(
              retaddr,
              (void *)0x36E,
              (unsigned int)"onecore\\vm\\worker\\vidpartition\\vidpartitionmanager.cpp",
              (const char *)v209,
              (int)"Physically backed VMs don't support private compression stores.",
              (const char *)v271);
          }
          if ( *((_BYTE *)v16 + 145) )
          {
            v210 = wil::verify_hresult<long>(3224829998LL);
            wil::details::in1diag3::Throw_HrMsg(
              retaddr,
              (void *)0x375,
              (unsigned int)"onecore\\vm\\worker\\vidpartition\\vidpartitionmanager.cpp",
              (const char *)v210,
              (int)"Physically backed VMs don't support deferred commit.",
              (const char *)v271);
          }
          if ( *((_BYTE *)v16 + 208) )
          {
            v211 = wil::verify_hresult<long>(3224829998LL);
            wil::details::in1diag3::Throw_HrMsg(
              retaddr,
              (void *)0x37C,
              (unsigned int)"onecore\\vm\\worker\\vidpartition\\vidpartitionmanager.cpp",
              (const char *)v211,
              (int)"Physically backed VMs don't support pinning.",
              (const char *)v271);
          }
          v67 = v55 | 0x10000;
          if ( *((_BYTE *)v16 + 209) )
          {
            v212 = wil::verify_hresult<long>(3224829998LL);
            wil::details::in1diag3::Throw_HrMsg(
              retaddr,
              (void *)0x383,
              (unsigned int)"onecore\\vm\\worker\\vidpartition\\vidpartitionmanager.cpp",
              (const char *)v212,
              (int)"Physically backed VMs don't support direct mapped images.",
              (const char *)v271);
          }
        }
        v90 = v67 & 0xFFDFFFFFFFFEFFFFuLL;
        if ( (v29[16956] & 0xF) != 1 )
          v90 = v67;
        if ( (*(unsigned int (__fastcall **)(__int64 *))(**v17 + 64))(*v17) )
        {
          v90 |= 0x800u;
          if ( *(_BYTE *)((*(__int64 (__fastcall **)(__int64 *, void **))(**v17 + 424))(*v17, v300) + 9) )
            v90 |= 0x20000000000uLL;
        }
        if ( v308 )
          v90 |= 1u;
        v295 = 64;
        v307 = 0;
        v273 = (struct IGuestCallback *)&v295;
        v272 = (struct IMemoryApertureCallback *)v329;
        LODWORD(v266) = 0;
        v91 = v285;
        SystemTopology = VidGetSystemTopology(*((_QWORD *)v285 + 10), 0, &v307, 0);
        LODWORD(v299[0]) = SystemTopology;
        v93 = (*(__int64 (__fastcall **)(struct INumaManager *))(*(_QWORD *)v281 + 8LL))(v281);
        if ( (*(unsigned int (__fastcall **)(__int64))(*(_QWORD *)v93 + 328LL))(v93) <= 1 )
        {
          if ( !*((_BYTE *)v91 + 114) )
          {
            HvCompatibilityVersion = 0;
            HIDWORD(v273) = 0;
            LODWORD(v272) = 4;
            v266 = (struct IVpOperations *)&HvCompatibilityVersion;
            if ( !(unsigned int)VidGetSystemInformation(*((_QWORD *)v91 + 10), 1, 0) )
              wil::details::in1diag3::Throw_GetLastError(
                retaddr,
                (void *)0x3C8,
                (unsigned int)"onecore\\vm\\worker\\vidpartition\\vidpartitionmanager.cpp",
                v94);
            if ( HvCompatibilityVersion == 3 )
            {
              phkResult = 0;
              v294 = 0;
              v297 = 0;
              Vml::VmRegistryKey::Open(
                &phkResult,
                HKEY_LOCAL_MACHINE,
                L"SOFTWARE\\Microsoft\\Windows NT\\CurrentVersion\\Virtualization",
                0x20019u);
              if ( !Vml::VmRegistryKey::QueryValue((Vml::VmRegistryKey *)&phkResult, L"NoAutomaticSmtEnablement", &v294) )
                v294 = v274 != 0;
              if ( Vml::VmRegistryKey::QueryValue((Vml::VmRegistryKey *)&phkResult, L"ForceSmtEnablement", &v297) )
              {
                v95 = v297;
              }
              else
              {
                v95 = 0;
                v297 = 0;
              }
              if ( v95 || SystemTopology && !v294 && *v282 > v307 )
              {
                v90 |= 0x800000000uLL;
                v279 = (*(__int64 (__fastcall **)(__int64 *))((*v17)[2] + 8))(*v17 + 2);
                v306[0] = (*(__int64 (__fastcall **)(__int64 *))(*v17)[2])(*v17 + 2);
                VmEventWrite<unsigned short const *,unsigned short const *>(
                  &MSVML_WP_WARN_SMT_AUTO_ENABLED,
                  1u,
                  (__int64)&v279);
              }
              Vml::VmRegistryKey::Close((Vml::VmRegistryKey *)&phkResult);
            }
          }
        }
        else
        {
          v90 |= 0x20u;
        }
        v96 = v286;
        if ( (*(unsigned int (__fastcall **)(struct IVpOperations *))(*(_QWORD *)v286 + 160LL))(v286) )
        {
          if ( (unsigned int)v296 >= 2 )
          {
            if ( (unsigned int)VmlIsDebugTraceEnabled(16416) )
              VmlDebugTrace(16416, L"Only generation 1 and generation 2 VMs support nested virtualization");
            v215 = wil::verify_hresult<long>(2147942450LL);
            LODWORD(v272) = (_DWORD)v296;
            wil::details::in1diag3::Throw_HrMsg(
              retaddr,
              (void *)0x404,
              (unsigned int)"onecore\\vm\\worker\\vidpartition\\vidpartitionmanager.cpp",
              (const char *)v215,
              (int)"virtualSystemSubType = %u",
              (const char *)v272);
          }
          v90 |= 0x40u;
        }
        if ( (*(unsigned int (__fastcall **)(struct IVpOperations *))(*(_QWORD *)v96 + 184LL))(v96) )
        {
          if ( (_DWORD)v296 != 1 )
          {
            if ( (unsigned int)VmlIsDebugTraceEnabled(16416) )
              VmlDebugTrace(16416, L"Only generation 2 VMs support hierarchical virtualization");
            v216 = wil::verify_hresult<long>(2147942450LL);
            LODWORD(v272) = (_DWORD)v296;
            wil::details::in1diag3::Throw_HrMsg(
              retaddr,
              (void *)0x417,
              (unsigned int)"onecore\\vm\\worker\\vidpartition\\vidpartitionmanager.cpp",
              (const char *)v216,
              (int)"virtualSystemSubType = %u",
              (const char *)v272);
          }
          v97 = v29[17098];
          v29[17098] = v97 + 1;
          v98 = v97;
          *(_DWORD *)gsl::span<_HV_PARTITION_PROPERTY_ASSOC,-1>::operator[](v330, v97) = 524545;
          v99 = (*(unsigned int (__fastcall **)(__int64 *))(**v17 + 400))(*v17);
          *(_QWORD *)(gsl::span<_HV_PARTITION_PROPERTY_ASSOC,-1>::operator[](v330, v98) + 8) = v99;
          v100 = v29[17098];
          v29[17098] = v100 + 1;
          v101 = v100;
          *(_DWORD *)gsl::span<_HV_PARTITION_PROPERTY_ASSOC,-1>::operator[](v330, v100) = 524546;
          v102 = (*(unsigned int (__fastcall **)(struct IVpOperations *))(*(_QWORD *)v96 + 192LL))(v96);
          *(_QWORD *)(gsl::span<_HV_PARTITION_PROPERTY_ASSOC,-1>::operator[](v330, v101) + 8) = v102;
          if ( (*(unsigned int (__fastcall **)(__int64 *))(**v17 + 408))(*v17) )
          {
            v103 = v29[17098];
            v29[17098] = v103 + 1;
            v104 = v103;
            *(_DWORD *)gsl::span<_HV_PARTITION_PROPERTY_ASSOC,-1>::operator[](v330, v103) = 131077;
            v105 = (*(int (__fastcall **)(__int64 *))(**v17 + 408))(*v17);
            *(_QWORD *)(gsl::span<_HV_PARTITION_PROPERTY_ASSOC,-1>::operator[](v330, v104) + 8) = v105;
          }
          v90 |= 0x10000000000000uLL;
          v106 = v29[17098];
          v29[17098] = v106 + 1;
          v107 = v106;
          *(_DWORD *)gsl::span<_HV_PARTITION_PROPERTY_ASSOC,-1>::operator[](v330, v106) = 327718;
          (*(void (__fastcall **)(__int64 *, _QWORD *))(**v17 + 416))(*v17, v306);
          v108 = v306[0];
          *(_QWORD *)(gsl::span<_HV_PARTITION_PROPERTY_ASSOC,-1>::operator[](v330, v107) + 8) = v108;
        }
        v109 = v90 | 0x1000000000LL;
        if ( !(*(unsigned int (__fastcall **)(struct IVpOperations *))(*(_QWORD *)v96 + 200LL))(v96) )
          v109 = v90;
        v110 = v109 | 0x1000000000000LL;
        if ( !(*(unsigned int (__fastcall **)(struct IVpOperations *))(*(_QWORD *)v96 + 208LL))(v96) )
          v110 = v109;
        v111 = v110 | 0x2000000000LL;
        if ( !(*(unsigned int (__fastcall **)(struct IVpOperations *))(*(_QWORD *)v96 + 216LL))(v96) )
          v111 = v110;
        v112 = v111 | 0x4000000000LL;
        if ( !(*(unsigned int (__fastcall **)(struct IVpOperations *))(*(_QWORD *)v96 + 224LL))(v96) )
          v112 = v111;
        v113 = v112 | 0x8000000000LL;
        if ( !(*(unsigned int (__fastcall **)(struct IVpOperations *))(*(_QWORD *)v96 + 232LL))(v96) )
          v113 = v112;
        v114 = v281;
        if ( (*(unsigned __int8 (__fastcall **)(struct INumaManager *))(*(_QWORD *)v281 + 72LL))(v281) )
        {
          if ( *v282 > 0xF0 )
          {
            v217 = wil::verify_hresult<long>(2147942450LL);
            LODWORD(v272) = v218;
            wil::details::in1diag3::Throw_HrMsg(
              retaddr,
              (void *)0x47F,
              (unsigned int)"onecore\\vm\\worker\\vidpartition\\vidpartitionmanager.cpp",
              (const char *)v217,
              (int)"Maximum processor count limit exceeded for legacy apic mode(%d).",
              (const char *)v272);
          }
          v113 |= 0x40000000000uLL;
        }
        else if ( (*(unsigned __int8 (__fastcall **)(struct INumaManager *))(*(_QWORD *)v114 + 80LL))(v114) )
        {
          v113 |= 0x80000000000uLL;
          v115 = (*(__int64 (__fastcall **)(struct INumaManager *))(*(_QWORD *)v114 + 8LL))(v114);
          if ( (unsigned __int64)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v115 + 368LL))(v115) >= 0xF0 )
            v113 |= 0x400000000000uLL;
        }
        if ( (*(unsigned __int8 (__fastcall **)(struct INumaManager *))(*(_QWORD *)v114 + 88LL))(v114) )
        {
          v116 = v29[17098];
          v29[17098] = v116 + 1;
          v117 = v116;
          *(_DWORD *)gsl::span<_HV_PARTITION_PROPERTY_ASSOC,-1>::operator[](v330, v116) = 327716;
          *(_QWORD *)(gsl::span<_HV_PARTITION_PROPERTY_ASSOC,-1>::operator[](v330, v117) + 8) = 1;
        }
        if ( (*(unsigned int (__fastcall **)(struct IVpOperations *))(*(_QWORD *)v96 + 240LL))(v96) )
          v113 |= 0x100000000000uLL;
        if ( HIDWORD(v296) >= 0x800 && (_DWORD)v296 != 1 )
          v113 |= 0x80uLL;
        if ( (_DWORD)v296 )
          v113 |= 0x100000000000000uLL;
        v118 = v304;
        if ( *((_BYTE *)v304 + 256) )
        {
          if ( HIDWORD(v296) < (v274 ^ 1u) + 2048 || (_DWORD)v296 != 1 )
          {
            if ( (unsigned int)VmlIsDebugTraceEnabled(16416) )
            {
              v223 = L"RS1";
              if ( !v274 )
                v223 = L"RS2";
              VmlDebugTrace(16416, L"Only generation 2 %s VMs support SGX", v223);
            }
            v224 = wil::verify_hresult<long>(2147778582LL);
            LODWORD(v272) = HIDWORD(v296);
            LODWORD(v273) = (_DWORD)v296;
            wil::details::in1diag3::Throw_HrMsg(
              retaddr,
              (void *)0x4CC,
              (unsigned int)"onecore\\vm\\worker\\vidpartition\\vidpartitionmanager.cpp",
              (const char *)v224,
              (int)"VM version %x (subtype %u) does not support SGX.",
              (const char *)v272,
              v273);
          }
          v113 |= 0x200uLL;
          v119 = *((_DWORD *)v304 + 68);
          if ( v119 )
          {
            v120 = v119 - 1;
            if ( v120 )
            {
              if ( v120 != 1 )
              {
                v219 = wil::verify_hresult<long>(2147942487LL);
                LODWORD(v272) = v220;
                wil::details::in1diag3::Throw_HrMsg(
                  retaddr,
                  (void *)0x4E2,
                  (unsigned int)"onecore\\vm\\worker\\vidpartition\\vidpartitionmanager.cpp",
                  (const char *)v219,
                  (int)"LaunchControlMode = %u",
                  (const char *)v272);
              }
              v113 |= 0x18000000uLL;
            }
            else
            {
              v113 |= 0x8000000uLL;
            }
          }
          if ( *((_QWORD *)v304 + 37) )
          {
            if ( *((_QWORD *)v304 + 37) != 64 )
            {
              NumaManager::GetRequestedNumaNodeMask((const struct Config::VmWorkerProcess::MemorySettings *)((char *)v304 + 280));
              v221 = wil::verify_hresult<long>(2147942487LL);
              LODWORD(v272) = v222;
              wil::details::in1diag3::Throw_HrMsg(
                retaddr,
                (void *)0x4F5,
                (unsigned int)"onecore\\vm\\worker\\vidpartition\\vidpartitionmanager.cpp",
                (const char *)v221,
                (int)"defaultString.size() = %u",
                (const char *)v272);
            }
            v121 = 0;
            while ( 1 )
            {
              HvCompatibilityVersion = v121;
              if ( v121 >= 4 )
                break;
              try
              {
                v122 = (wchar_t *)std::wstring::substr((char *)v118 + 280, v300, 16 * v121, 16);
                *(_QWORD *)&v29[2 * v121 + 16948] = _byteswap_uint64(std::stoull(v122));
                std::wstring::_Tidy_deallocate(v300);
                ++v121;
              }
              catch ( const std::exception *v292 )
              {
                if ( (unsigned int)VmlIsDebugTraceEnabled(16416) )
                {
                  v253 = (*(__int64 (__fastcall **)(const std::exception *))(*(_QWORD *)v292 + 8LL))(v292);
                  VmlDebugTrace(
                    16416,
                    L"Invalid SGX launch control default string (MSR %u): %S",
                    HvCompatibilityVersion,
                    v253);
                }
                v254 = wil::ResultFromCaughtException(v252);
                v255 = wil::verify_hresult<long>(v254);
                wil::details::in1diag3::Throw_Hr(
                  retaddr,
                  (void *)0x508,
                  (unsigned int)"onecore\\vm\\worker\\vidpartition\\vidpartitionmanager.cpp",
                  (const char *)v255,
                  v264);
              }
            }
            v113 |= 0x20000000uLL;
          }
        }
        v300[0] = v17;
        v123 = (*(__int64 (__fastcall **)(__int64 *))(**v17 + 440))(*v17);
        v124 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v123 + 800LL))(v123);
        v125 = v113 | 0x800000000000LL;
        if ( !v124 )
          v125 = v113;
        v126 = v125 | 0x80000;
        if ( !*((_BYTE *)v118 + 192) )
          v126 = v125;
        v127 = (*(__int64 (__fastcall **)(__int64 *))(**v17 + 440))(*v17);
        if ( (*(unsigned __int8 (__fastcall **)(__int64))(*(_QWORD *)v127 + 480LL))(v127) )
        {
          v29[12] |= 0x180u;
          v130 = v29[12] | 0x600;
        }
        else
        {
          v29[12] ^= (v29[12]
                    ^ ((unsigned int)lambda_905e8990a4b2d6ed0cb3f92b5ec73c91_::operator()(v129, *((_QWORD *)v118 + 23)) << 7))
                   & 0x180;
          v130 = v29[12]
               ^ (v29[12]
                ^ ((unsigned int)lambda_905e8990a4b2d6ed0cb3f92b5ec73c91_::operator()(v131, *((_QWORD *)v118 + 25)) << 9))
               & 0x600;
        }
        v29[12] = v130;
        if ( (v130 & 0x600) == 0 && *((_QWORD *)v118 + 5) == 1 )
        {
          v132 = (*(__int64 (__fastcall **)(__int64 *))(**v17 + 48))(*v17);
          if ( (*(unsigned int (__fastcall **)(__int64))(*(_QWORD *)v132 + 392LL))(v132) )
            v29[12] |= 0x600u;
        }
        v133 = *((_QWORD *)v118 + 29);
        if ( v133 )
        {
          v134 = (const unsigned __int16 *)((char *)v118 + 216);
          if ( *((_QWORD *)v118 + 30) > 7u )
            v134 = *(const unsigned __int16 **)v134;
          v135 = StringCbCopyNW((unsigned __int16 *)v29 + 33924, v128, v134, 2 * v133);
          if ( v135 < 0 )
          {
            v225 = wil::verify_hresult<long>((unsigned int)v135);
            wil::details::in1diag3::Throw_HrMsg(
              retaddr,
              (void *)0x57A,
              (unsigned int)"onecore\\vm\\worker\\vidpartition\\vidpartitionmanager.cpp",
              (const char *)v225,
              (int)"Failed to copy specified hosting process name suffix into the IOCTL buffer",
              (const char *)v272);
          }
        }
        v136 = v289;
        phkResult = v289;
        HvCompatibilityVersion = VidPartitionManager::GetHvCompatibilityVersion(v129, HIDWORD(v296));
        *(_OWORD *)Src = 0;
        (*(void (__fastcall **)(HKEY, void **))(*(_QWORD *)v136 + 104LL))(v136, Src);
        *(_OWORD *)v322 = 0;
        (*(void (__fastcall **)(HKEY, void **))(*(_QWORD *)v136 + 112LL))(v136, v322);
        *(_OWORD *)v323 = 0;
        (*(void (__fastcall **)(HKEY, void **))(*(_QWORD *)v136 + 120LL))(v136, v323);
        if ( (v29[16956] & 0xF) == 2 )
        {
          v137 = v290;
          v138 = (*(__int64 (__fastcall **)(struct IVirtualMachine *))(*(_QWORD *)v290 + 248LL))(v290);
          v139 = (*(__int64 (__fastcall **)(struct IVirtualMachine *))(*(_QWORD *)v137 + 256LL))(v137);
          v140 = v139;
          if ( v138 || v139 )
          {
            if ( !(*(unsigned __int8 (__fastcall **)(struct INumaManager *))(*(_QWORD *)v281 + 80LL))(v281) )
              wil::details::in1diag3::Throw_Hr(
                retaddr,
                (void *)0x595,
                (unsigned int)"onecore\\vm\\worker\\vidpartition\\vidpartitionmanager.cpp",
                (const char *)0x80070057LL,
                (int)v266);
            v126 |= 0x400000000000uLL;
            if ( v140 )
            {
              v29[16956] |= 0xC0u;
            }
            else if ( v138 )
            {
              v29[16956] &= ~0x80u;
              v29[16956] |= 0x40u;
            }
          }
        }
        v284.m128i_i64[0] = (__int64)v282;
        v141 = *v282;
        v29[10] = *v282;
        v142 = v275;
        v294 = v275;
        v297 = v275;
        v29[12] ^= (v29[12] ^ v275) & 0x7F;
        *((_QWORD *)v29 + 4) = v126;
        *v29 = HvCompatibilityVersion;
        *(_OWORD *)(v29 + 2) = *(_OWORD *)a11;
        *((_QWORD *)v29 + 3) = *((_QWORD *)a11 + 2);
        v143 = v280;
        memcpy_0(v29 + 46, (const void *)(v280 + 344), v141);
        memcpy_0(v29 + 558, Src[1], 8LL * v29[10]);
        if ( v322[0] )
          memcpy_0(v29 + 4654, v322[1], 16LL * v29[10]);
        if ( v323[0] )
        {
          memcpy_0(v29 + 12847, v323[1], 8LL * v29[10]);
          v144 = 1;
        }
        else
        {
          v144 = 0;
        }
        *((_BYTE *)v29 + 51384) = v144;
        memcpy_0(v29 + 13, (const void *)(v143 + 280), v29[12] & 0x7F);
        memcpy_0(v29 + 29, (const void *)(v143 + 2392), v29[12] & 0x7F);
        *((_OWORD *)v29 + 4236) = v66;
        v29[17099] = 68416;
        v145 = v29[17098];
        v29[17098] = v145 + 1;
        v146 = v145;
        *(_DWORD *)gsl::span<_HV_PARTITION_PROPERTY_ASSOC,-1>::operator[](v330, v145) = 65537;
        v147 = *(_QWORD *)a12;
        *(_QWORD *)(gsl::span<_HV_PARTITION_PROPERTY_ASSOC,-1>::operator[](v330, v146) + 8) = v147;
        v148 = v286;
        if ( (*(unsigned int (__fastcall **)(struct IVpOperations *))(*(_QWORD *)v286 + 168LL))(v286) )
        {
          v149 = v29[17098];
          v29[17098] = v149 + 1;
          v150 = v149;
          *(_DWORD *)gsl::span<_HV_PARTITION_PROPERTY_ASSOC,-1>::operator[](v330, v149) = 524289;
          v151 = (*(unsigned int (__fastcall **)(struct IVpOperations *))(*(_QWORD *)v148 + 176LL))(v148);
          *(_QWORD *)(gsl::span<_HV_PARTITION_PROPERTY_ASSOC,-1>::operator[](v330, v150) + 8) = v151;
          v152 = v286;
          if ( (*(unsigned int (__fastcall **)(struct IVpOperations *))(*(_QWORD *)v286 + 184LL))(v286)
            && (*(unsigned int (__fastcall **)(struct IVpOperations *))(*(_QWORD *)v152 + 176LL))(v152) )
          {
            v29[16956] |= 0x20u;
          }
          else
          {
            v29[16956] |= 0x10u;
          }
        }
        v153 = v290;
        if ( (*(unsigned __int8 (__fastcall **)(struct IVirtualMachine *))(*(_QWORD *)v290 + 216LL))(v290)
          && (v29[16956] & 0xF) - 2 > 2 )
        {
          v304 = 0;
          (*(void (__fastcall **)(__int64 *, _QWORD, const struct Config::VmWorkerProcess::MemorySettings **))(**v17 + 280))(
            *v17,
            0,
            &v304);
          v154 = (((unsigned __int64)v304 + 511) >> 9) + 512;
          v155 = v29[17098];
          v29[17098] = v155 + 1;
          v156 = v155;
          *(_DWORD *)gsl::span<_HV_PARTITION_PROPERTY_ASSOC,-1>::operator[](v330, v155) = 327713;
          *(_QWORD *)(gsl::span<_HV_PARTITION_PROPERTY_ASSOC,-1>::operator[](v330, v156) + 8) = v154;
          v153 = v290;
        }
        v157 = (*(__int64 (__fastcall **)(struct IVirtualMachine *))(*(_QWORD *)v153 + 48LL))(v153);
        v158 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v157 + 240LL))(v157);
        v159 = v158;
        if ( v158 )
        {
          HvCompatibilityVersion = 0;
          v160 = (*(__int64 (__fastcall **)(__int64 *))(**v17 + 464))(*v17);
          v161 = (*(__int64 (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v160 + 88LL))(
                   v160,
                   &HvCompatibilityVersion);
          if ( v161 < 0 )
            wil::details::in1diag3::Throw_Hr(
              retaddr,
              (void *)0x624,
              (unsigned int)"onecore\\vm\\worker\\vidpartition\\vidpartitionmanager.cpp",
              (const char *)(unsigned int)v161,
              (int)v266);
          if ( HvCompatibilityVersion != 3 )
          {
            v162 = v29[17098];
            v29[17098] = v162 + 1;
            v163 = v162;
            *(_DWORD *)gsl::span<_HV_PARTITION_PROPERTY_ASSOC,-1>::operator[](v330, v162) = 393222;
            *(_QWORD *)(gsl::span<_HV_PARTITION_PROPERTY_ASSOC,-1>::operator[](v330, v163) + 8) = v159;
          }
        }
        if ( a7 != (void *)-1LL )
          *((_QWORD *)v29 + 8547) = a7;
        *((_QWORD *)v29 + 8548) = a8;
        v164 = v285;
        *((_QWORD *)v285 + 12) = v126;
        v29[17100] = (_DWORD)v298 - 68416;
        v165 = (*(__int64 (__fastcall **)(__int64 *))(*v17)[2])(*v17 + 2);
        v166 = (*(__int64 (__fastcall **)(__int64 *))((*v17)[2] + 8))(*v17 + 2);
        Partition = VidCreatePartition(v166, v165, v29);
        v168 = (void **)((char *)v164 + 56);
        *((_QWORD *)v164 + 7) = Partition;
        if ( Partition == -1 )
        {
          LastError = GetLastError();
          v229 = LastError;
          if ( (LastError & 0x1FFF0000) != 0 )
          {
            v230 = LastError;
            if ( LastError > 0 )
              v230 = LastError & 0xFFFFFFF | 0x80000000;
          }
          else if ( LastError > 0 )
          {
            v230 = (unsigned __int16)LastError | 0x80070000;
          }
          else
          {
            v230 = LastError;
          }
          if ( LastError == -1070264320 )
          {
            VmEventWriteAndReport(&MSVML_WP_INIT_HYPERVISOR_NOT_RUNNING_ERROR, 5u, v227, v228);
          }
          else
          {
            if ( (unsigned int)VmlIsDebugTraceEnabled(16416) )
              VmlDebugTrace(16416, L"Failed to create partition. GetLastError=%d .\n", v229);
            _snwprintf_s<16>(v300, 16, L"%%%%%u", v230 & 0xEFFFFFFF);
            _snwprintf_s<16>(v330, 16, L"0x%08X", v230 & 0xEFFFFFFF);
            VmEventWriteAndReport<unsigned short (&)[16],unsigned short (&)[16]>(
              (struct _EVENT_DESCRIPTOR *)&MSVML_WP_INIT_CREATE_PARTITION_ERROR,
              (__int64)v300,
              (unsigned __int16 *)v330);
          }
          v231 = wil::verify_hresult<long>(v230);
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x65E,
            (unsigned int)"onecore\\vm\\worker\\vidpartition\\vidpartitionmanager.cpp",
            (const char *)v231,
            (int)v266);
        }
        if ( !(unsigned int)VidAttachPartition(Partition) )
          wil::details::in1diag3::Throw_GetLastError(
            retaddr,
            (void *)0x661,
            (unsigned int)"onecore\\vm\\worker\\vidpartition\\vidpartitionmanager.cpp",
            v169);
        v304 = (VidPartitionManager *)((char *)v164 + 56);
        if ( (*(unsigned int (__fastcall **)(__int64 *))(**v17 + 64))(*v17) )
        {
          v170 = v291;
          if ( *((_QWORD *)v291 + 4) > 2u )
          {
            if ( *((_QWORD *)v291 + 8) )
            {
              memset_0(v327, 0, 0xFE8u);
              LODWORD(v266) = 4072;
              if ( (unsigned int)VidGetPartitionPropertyEx(*v168, 589840, 0, v327) )
              {
                v171 = LOBYTE(v327[0]);
                v172 = (unsigned __int8 *)*((_QWORD *)v170 + 8);
                v173 = *v172;
                if ( LOBYTE(v327[0]) != v173 )
                {
                  v232 = VmWorkerTrace::Provider();
                  v233 = (int)v232;
                  if ( *(_DWORD *)v232 > 2u && (unsigned __int8)tlgKeywordOn(v232, 0) )
                  {
                    v306[0] = v173;
                    v279 = v171;
                    v234 = Vml::VmReferencePtr<IVirtualMachine,Vml::VmWeakReferenceTraits>::operator->(v17);
                    v280 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)(v234 + 16) + 16LL))(v234 + 16);
                    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>>(
                      v233,
                      (unsigned int)&unk_14036BFB0,
                      v235,
                      v236,
                      (__int64)&v280,
                      (__int64)&v279,
                      (__int64)v306);
                  }
                  v237 = wil::verify_hresult<long>(2147549183LL);
                  wil::details::in1diag3::Throw_HrMsg(
                    retaddr,
                    (void *)0x688,
                    (unsigned int)"onecore\\vm\\worker\\vidpartition\\vidpartitionmanager.cpp",
                    (const char *)v237,
                    (int)"Processor features bank count mismatch Hypervisor visible bank count=%zu, Worker visible bank count=%zu",
                    (const char *)v171,
                    v173);
                }
                for ( i = 2; i < v173; ++i )
                {
                  v175 = v328[i];
                  v176 = ~*(_QWORD *)&v172[8 * i + 8];
                  if ( (v175 & v176) != v176 )
                  {
                    v238 = VmWorkerTrace::Provider();
                    v239 = (int)v238;
                    if ( *(_DWORD *)v238 > 2u )
                    {
                      if ( (unsigned __int8)tlgKeywordOn(v238, 0) )
                      {
                        v306[0] = v175;
                        v279 = v176;
                        v280 = i;
                        v240 = Vml::VmReferencePtr<IVirtualMachine,Vml::VmWeakReferenceTraits>::operator->(v17);
                        v287 = (struct IGuestCallback *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)(v240 + 16)
                                                                                           + 16LL))(v240 + 16);
                        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>>(
                          v239,
                          (unsigned int)word_14036BDB2,
                          v241,
                          v242,
                          (__int64)&v287,
                          (__int64)&v280,
                          (__int64)&v279,
                          (__int64)v306);
                      }
                    }
                    v243 = wil::verify_hresult<long>(2147549183LL);
                    wil::details::in1diag3::Throw_HrMsg(
                      retaddr,
                      (void *)0x6AB,
                      (unsigned int)"onecore\\vm\\worker\\vidpartition\\vidpartitionmanager.cpp",
                      (const char *)v243,
                      (int)"Processor features bank %zu: expected enabled features are not a subset of actual enabled fea"
                           "tures. expected enabled=0x%llx, actual enabled=0x%llx",
                      (const char *)i,
                      v176,
                      v175);
                  }
                }
                v142 = v294;
                v164 = v285;
              }
            }
          }
        }
        VidPartitionManager::FreezeTime(v164);
        try
        {
          v177 = (*(__int64 (__fastcall **)(__int64 *))(*v17)[2])(*v17 + 2);
          v178 = VidSetPartitionFriendlyName(*v168, v177);
          v180 = retaddr;
          if ( !v178 )
            wil::details::in1diag3::Throw_GetLastError(
              retaddr,
              (void *)0x6BB,
              (unsigned int)"onecore\\vm\\worker\\vidpartition\\vidpartitionmanager.cpp",
              v179);
        }
        catch ( ... )
        {
          v259 = wil::ResultFromCaughtException(v180);
          v260 = v259;
          LODWORD(v260) = v259 & 0xEFFFFFFF;
          _snwprintf_s<16>(v330, 16, L"%%%%%u", v260);
          _snwprintf_s<16>(v315, 16, L"0x%08X", v259 & 0xEFFFFFFF);
          v261 = v288;
          v262 = Vml::VmReferencePtr<IVirtualMachine,Vml::VmWeakReferenceTraits>::operator->((char *)v288 + 104);
          v276 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)(v262 + 16) + 8LL))(v262 + 16);
          v263 = Vml::VmReferencePtr<IVirtualMachine,Vml::VmWeakReferenceTraits>::operator->((char *)v261 + 104);
          v283 = (struct INumaManager *)(**(__int64 (__fastcall ***)(__int64))(v263 + 16))(v263 + 16);
          VmEventWriteAndReport<unsigned short const *,unsigned short const *,unsigned short (&)[16],unsigned short (&)[16]>(
            (struct _EVENT_DESCRIPTOR *)&MSVML_WP_SET_PARTITION_PROP_ERROR,
            5u,
            (__int64)&v283,
            (__int64)&v276,
            (__int64)v330,
            (__int64)v315);
          throw;
        }
        v181 = v308;
        if ( v308 )
        {
          v182 = VidSetPartitionProperty(*v168, 262147, v308);
          try
          {
            wil::details::in1diag3::Throw_IfWin32BoolFalseMsg(
              retaddr,
              (void *)0x6DD,
              (unsigned int)"onecore\\vm\\worker\\vidpartition\\vidpartitionmanager.cpp",
              (const char *)v182,
              (int)"channelId = %I64u",
              v181);
          }
          catch ( ... )
          {
            v256 = wil::ResultFromCaughtException(v183);
            v257 = v256;
            LODWORD(v257) = v256 & 0xEFFFFFFF;
            _snwprintf_s<16>(v315, 16, L"%%%%%u", v257);
            _snwprintf_s<16>(v330, 16, L"0x%08X", v256 & 0xEFFFFFFF);
            v258 = v288;
            v306[0] = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)(*((_QWORD *)v288 + 13) + 16LL) + 8LL))(*((_QWORD *)v288 + 13) + 16LL);
            v279 = (**(__int64 (__fastcall ***)(__int64))(*((_QWORD *)v258 + 13) + 16LL))(*((_QWORD *)v258 + 13) + 16LL);
            VmEventWrite<unsigned short const *,unsigned short const *,unsigned short (&)[16],unsigned short (&)[16]>(
              &MSVML_WP_SET_DEBUG_CHANNEL_ERROR,
              5u,
              (__int64)v306,
              (__int64)v315,
              (__int64)v330);
            v277 = v278;
            v289 = phkResult;
            v282 = (unsigned int *)v284.m128i_i64[0];
            v168 = (void **)v304;
            v17 = (__int64 **)v300[0];
            v164 = v288;
            v281 = v283;
            v184 = v276;
            v142 = v297;
            goto LABEL_260;
          }
        }
        v184 = (__int64)v286;
LABEL_260:
        Instance = VidNotificationDispatcher::CreateInstance((struct VidNotificationDispatcher **)v164 + 8);
        if ( Instance < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x6F0,
            (unsigned int)"onecore\\vm\\worker\\vidpartition\\vidpartitionmanager.cpp",
            (const char *)(unsigned int)Instance,
            (int)v266);
        v267 = (struct IVpOperations *)v184;
        v186 = v281;
        v187 = VidNotificationDispatcher::Initialize(
                 *((VidNotificationDispatcher **)v164 + 8),
                 v164,
                 v281,
                 (struct IVirtualMachine *)*v17,
                 v267,
                 a5,
                 v287);
        if ( v187 < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x6F7,
            (unsigned int)"onecore\\vm\\worker\\vidpartition\\vidpartitionmanager.cpp",
            (const char *)(unsigned int)v187,
            v268);
        if ( !(unsigned int)Vml::VmCompletionHandlerIo::AssociateHandle(
                              (VidPartitionManager *)((char *)v164 + 120),
                              *v168) )
          wil::details::in1diag3::Throw_GetLastError(
            retaddr,
            (void *)0x6F9,
            (unsigned int)"onecore\\vm\\worker\\vidpartition\\vidpartitionmanager.cpp",
            v188);
        memset_0(v327, 0, 0x100u);
        if ( LODWORD(v299[0]) )
        {
          v189 = 0;
          v190 = v275;
          if ( v275 )
          {
            v191 = v280;
            do
            {
              v192 = *(unsigned __int8 *)(v191 + v189 + 280);
              v327[v192] += *(_DWORD *)(v191 + 4LL * v189++ + 16);
            }
            while ( v189 < v190 );
          }
          for ( j = 0; j < v295; ++j )
          {
            if ( *(_DWORD *)&v329[24 * j + 4] < v327[j] )
            {
              v276 = (*(__int64 (__fastcall **)(__int64 *))((*v17)[2] + 8))(*v17 + 2);
              v283 = (struct INumaManager *)(*(__int64 (__fastcall **)(__int64 *))(*v17)[2])(*v17 + 2);
              VmEventWrite<unsigned short const *,unsigned short const *>(
                &MSVML_MM_NUMA_RESOURCES_NOT_ALIGNED_WARNING,
                1u,
                (__int64)&v276);
              break;
            }
          }
        }
        if ( v277 && v275 > 1u )
        {
          *(_OWORD *)v300 = 0;
          *(_QWORD *)&v301 = 0;
          v194 = v142 * v142;
          if ( v194 )
            std::vector<unsigned char const *>::_Resize_reallocate<std::_Value_init_tag>(v300, v194);
          v294 = 0;
          v195 = v277;
          if ( v277 == 2 )
            goto LABEL_279;
          while ( 1 )
          {
            LODWORD(v299[0]) = gsl::narrow<unsigned int,unsigned __int64,0>(((char *)v300[1] - (char *)v300[0]) & 0xFFFFFFFFFFFFFFF8uLL);
            v269 = (int)v300[0];
            if ( (unsigned int)VidQueryPartitionInformation(*v168, 0, &v294, 4) )
              break;
            if ( v195 != 3 )
            {
              v244 = GetLastError();
              v245 = v244;
              if ( v244 > 0 )
                v245 = (unsigned __int16)v244 | 0x80070000;
              v246 = VmWorkerTrace::Provider();
              v247 = (int)v246;
              if ( *(_DWORD *)v246 > 2u && (unsigned __int8)tlgKeywordOn(v246, 0) )
              {
                v278 = v245;
                v274 = v195;
                v248 = Vml::VmReferencePtr<IVirtualMachine,Vml::VmWeakReferenceTraits>::operator->(v17);
                v276 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)(v248 + 16) + 16LL))(v248 + 16);
                _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByVal<1>,_tlgWrapperByVal<4>>(
                  v247,
                  (unsigned int)byte_14036C011,
                  v249,
                  v250,
                  (__int64)&v276,
                  (__int64)&v274,
                  (__int64)&v278);
              }
              v251 = wil::verify_hresult<long>(v245);
              wil::details::in1diag3::Throw_Hr(
                retaddr,
                (void *)0x74C,
                (unsigned int)"onecore\\vm\\worker\\vidpartition\\vidpartitionmanager.cpp",
                (const char *)v251,
                v269);
            }
            v195 = 2;
            v294 = 0;
LABEL_279:
            v294 = 1;
          }
          v196 = VmWorkerTrace::Provider();
          v197 = (int)v196;
          if ( *(_DWORD *)v196 > 4u && (unsigned __int8)tlgKeywordOn(v196, 4096) )
          {
            v274 = v195;
            v330[0] = (char *)v300[0];
            LOWORD(v330[1]) = ((char *)v300[1] - (char *)v300[0]) >> 3;
            v276 = (*(__int64 (__fastcall **)(__int64 *))((*v17)[2] + 16))(*v17 + 2);
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperArray<8>,_tlgWrapperByVal<1>>(
              v197,
              (__int64)&v276,
              (__int64)v330,
              (__int64)&v274);
          }
          (*(void (__fastcall **)(HKEY, void **))(*(_QWORD *)v289 + 456LL))(v289, v300);
          std::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<unsigned int const,std::shared_ptr<MigrationTransferEndpointTarget>>>>>>>::~_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<unsigned int const,std::shared_ptr<MigrationTransferEndpointTarget>>>>>>>(v300);
        }
        v198 = operator new(0x90u);
        v276 = (__int64)v198;
        memset_0(v198, 0, 0x90u);
        v199 = WorkerStatsPanel::WorkerStatsPanel((WorkerStatsPanel *)v198);
        *((_QWORD *)v164 + 9) = v199;
        v200 = *v282;
        (*(void (__fastcall **)(__int64 *))((*v17)[2] + 16))(*v17 + 2);
        (*(void (__fastcall **)(__int64 *))(*v17)[2])(*v17 + 2);
        v203 = WorkerStatsPanel::Initialize(v199, *v168, v201, v202, v200);
        if ( v203 < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x769,
            (unsigned int)"onecore\\vm\\worker\\vidpartition\\vidpartitionmanager.cpp",
            (const char *)(unsigned int)v203,
            v270);
        (*(void (__fastcall **)(struct INumaManager *))(*(_QWORD *)v186 + 120LL))(v186);
        std::vector<_VID_VSM_MBP_PERMISSIONS>::_Tidy(&v324);
        std::vector<_VID_VSM_MBP_PERMISSIONS>::_Tidy(&v311);
        std::vector<_VID_VSM_MBP_PERMISSIONS>::_Tidy(&v309);
        std::vector<_VID_VSM_MBP_PERMISSIONS>::_Tidy(&v313);
        Vml::VmReferencePtr<VmRepository,Vml::VmUserReferenceTraits>::~VmReferencePtr<VmRepository,Vml::VmUserReferenceTraits>(&v303);
        return 0;
      }
      gsl::details::terminate(v30);
    }
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0x146,
      (unsigned int)"onecore\\vm\\worker\\vidpartition\\vidpartitionmanager.cpp",
      v19);
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0x76F,
                           (unsigned int)"onecore\\vm\\worker\\vidpartition\\vidpartitionmanager.cpp",
                           v204);
  }
  return result;
}

```

## disassembly

```asm
0x14027c70c  push    rbx
0x14027c70e  push    rsi
0x14027c70f  push    rdi
0x14027c710  push    r12
0x14027c712  push    r13
0x14027c714  push    r14
0x14027c716  push    r15
0x14027c718  mov     eax, 1890h
0x14027c71d  call    _alloca_probe
0x14027c722  sub     rsp, rax
0x14027c725  movaps  [rsp+18C8h+var_48], xmm6
0x14027c72d  mov     rax, cs:__security_cookie
0x14027c734  xor     rax, rsp
0x14027c737  mov     [rsp+18C8h+var_58], rax
0x14027c73f  mov     r15, r9
0x14027c742  mov     [rsp+18C8h+var_1830], r9
0x14027c74a  mov     rdi, r8
0x14027c74d  mov     [rsp+18C8h+var_1860], r8
0x14027c752  mov     [rsp+18C8h+var_1810], rdx
0x14027c75a  mov     r12, rcx
0x14027c75d  mov     [rsp+18C8h+var_1838], rcx
0x14027c765  mov     [rsp+18C8h+var_1820], rcx
0x14027c76d  mov     [rsp+18C8h+var_1850], r8
0x14027c772  mov     [rsp+18C8h+var_1880], r9
0x14027c777  mov     rcx, [rsp+18C8h+arg_28]
0x14027c77f  mov     [rsp+18C8h+var_1828], rcx
0x14027c787  mov     rsi, [rsp+18C8h+arg_48]
0x14027c78f  mov     [rsp+18C8h+var_1790], rsi
0x14027c797  mov     rbx, [rsp+18C8h+arg_60]
0x14027c79f  mov     [rsp+18C8h+var_1808], rbx
0x14027c7a7  lea     r13, [r12+68h]
0x14027c7ac  mov     rcx, r13
0x14027c7af  call    ?Reset@?$VmReferencePtr@UIVirtualMachine@@VVmWeakReferenceTraits@Vml@@@Vml@@QEAAXPEAUIVirtualMachine@@@Z; Vml::VmReferencePtr<IVirtualMachine,Vml::VmWeakReferenceTraits>::Reset(IVirtualMachine *)
0x14027c7b4  mov     rax, [r15]
0x14027c7b7  mov     rcx, r15
0x14027c7ba  mov     rax, [rax+0B8h]
0x14027c7c1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14027c7c6  xor     r14d, r14d
0x14027c7c9  test    eax, eax
0x14027c7cb  setnz   al
0x14027c7ce  mov     [r12+72h], al
0x14027c7d3  call    cs:__imp_VidOpenStatisticsHandle
0x14027c7da  nop     dword ptr [rax+rax+00h]
0x14027c7df  mov     [r12+50h], rax
0x14027c7e4  dec     rax
0x14027c7e7  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x14027c7eb  ja      loc_14027F2D0
0x14027c7f1  mov     rcx, [r13+0]
0x14027c7f5  mov     rax, [rcx]
0x14027c7f8  mov     rax, [rax+30h]
0x14027c7fc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14027c801  mov     rdx, rax
0x14027c804  mov     rcx, [rax]
0x14027c807  mov     rax, [rcx+98h]
0x14027c80e  mov     rcx, rdx
0x14027c811  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14027c816  lea     rcx, [r12+58h]
0x14027c81b  mov     [rsp+18C8h+var_1858], rcx
0x14027c820  mov     [rcx], eax
0x14027c822  call    _lambda_997682190daf7855ab97ce0562d05e09___operator__
0x14027c827  mov     bl, al
0x14027c829  mov     byte ptr [rsp+18C8h+var_1888], al
0x14027c82d  mov     [rsp+18C8h+var_1768], r14
0x14027c835  mov     dword ptr [rsp+18C8h+var_17EC+4], r14d
0x14027c83d  mov     dword ptr [rsp+18C8h+var_17EC], r14d
0x14027c845  mov     [rsp+18C8h+var_1798], r14
0x14027c84d  mov     rcx, [r13+0]
0x14027c851  mov     rdx, [rcx]
0x14027c854  mov     rax, [rdx+38h]
0x14027c858  lea     rdx, [rsp+18C8h+var_1798]
0x14027c860  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14027c865  nop
0x14027c866  xorps   xmm0, xmm0
0x14027c869  movups  xmmword ptr [rsp+18C8h+var_78], xmm0
0x14027c871  xor     r8d, r8d
0x14027c874  mov     rdx, [rsp+18C8h+var_1798]
0x14027c87c  lea     rcx, [rsp+18C8h+var_78]
0x14027c884  call    ??0VmRepositoryAutoLock@@QEAA@PEAVVmRepository@@W4VmRepositoryLockFlags@@@Z; VmRepositoryAutoLock::VmRepositoryAutoLock(VmRepository *,VmRepositoryLockFlags)
0x14027c889  nop
0x14027c88a  mov     r9d, dword ptr [rsp+18C8h+var_78+8]; char *
0x14027c892  mov     rcx, [rsp+18C8h]; this
0x14027c89a  test    r9d, r9d
0x14027c89d  js      loc_14027EA00
0x14027c8a3  mov     rcx, [rsp+18C8h+var_1798]
0x14027c8ab  mov     rax, [rcx]
0x14027c8ae  lea     rdx, [rsp+18C8h+var_17EC+4]
0x14027c8b6  mov     rax, [rax+120h]
0x14027c8bd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14027c8c2  mov     rcx, [rsp+18C8h]; this
0x14027c8ca  test    eax, eax
0x14027c8cc  js      loc_14027EA11
0x14027c8d2  mov     rcx, [rsp+18C8h+var_1798]
0x14027c8da  mov     rax, [rcx]
0x14027c8dd  lea     r8, [rsp+18C8h+var_1768]
0x14027c8e5  lea     rdx, ?VIRTUAL_MACHINE_DEBUG_CHANNELID@@3QBGB; "/configuration/global_settings/debug/ch"...
0x14027c8ec  mov     rax, [rax+70h]
0x14027c8f0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14027c8f5  mov     rcx, [rsp+18C8h+var_1798]
0x14027c8fd  mov     rax, [rcx]
0x14027c900  lea     rdx, [rsp+18C8h+var_17EC]
0x14027c908  mov     rax, [rax+140h]
0x14027c90f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14027c914  xorps   xmm0, xmm0
0x14027c917  movdqa  [rsp+18C8h+var_1718], xmm0
0x14027c920  mov     [rsp+18C8h+var_1708], r14
0x14027c928  mov     [rsp+18C8h+var_1700], r14
0x14027c930  mov     qword ptr [rsp+18C8h+var_16F8], r14
0x14027c938  mov     qword ptr [rsp+18C8h+var_16F8+8], r14
0x14027c940  movdqa  [rsp+18C8h+var_16E8], xmm0
0x14027c949  mov     [rsp+18C8h+var_16D8], r14
0x14027c951  mov     [rsp+18C8h+var_16D0], r14
0x14027c959  mov     [rsp+18C8h+var_16C8], r14d
0x14027c961  lea     r8, [rsp+18C8h+var_1718]
0x14027c969  lea     rdx, [rsp+18C8h+var_1798]
0x14027c971  lea     rcx, [rsp+18C8h+var_17C8]
0x14027c979  call    ??$FromRepository@AEBV?$VmReferencePtr@VVmRepository@@VVmUserReferenceTraits@Vml@@@Vml@@UTopologySettings@VmWorkerProcess@Config@@$$V@Marshal@@YA?AU?$pair@_NV?$vector@U?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@W4UnmarshalError@Marshal@@@std@@V?$allocator@U?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@W4UnmarshalError@Marshal@@@std@@@2@@std@@@std@@AEBV?$VmReferencePtr@VVmRepository@@VVmUserReferenceTraits@Vml@@@Vml@@PEAUTopologySettings@VmWorkerProcess@Config@@W4UnmarshalFlags@0@@Z; Marshal::FromRepository<Vml::VmReferencePtr<VmRepository,Vml::VmUserReferenceTraits> const &,Config::VmWorkerProcess::TopologySettings,>(Vml::VmReferencePtr<VmRepository,Vml::VmUserReferenceTraits> const &,Config::VmWorkerProcess::TopologySettings *,Marshal::UnmarshalFlags)
0x14027c97e  nop
0x14027c97f  mov     rcx, [rsp+18C8h]; this
0x14027c987  cmp     [rax], r14b
0x14027c98a  jz      loc_14027EA26
0x14027c990  lea     rcx, [rsp+18C8h+var_17C8+8]
0x14027c998  call    ?_Tidy@?$vector@U?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@W4UnmarshalError@Marshal@@@std@@V?$allocator@U?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@W4UnmarshalError@Marshal@@@std@@@2@@std@@AEAAXXZ; std::vector<std::pair<std::wstring,Marshal::UnmarshalError>>::_Tidy(void)
0x14027c99d  mov     edx, dword ptr [rsp+18C8h+var_16D8]
0x14027c9a4  mov     [rsp+18C8h+var_1878], edx
0x14027c9a8  mov     [rsp+18C8h+var_1874], edx
0x14027c9ac  mov     rcx, [rsp+18C8h]; this
0x14027c9b4  cmp     edx, 3
0x14027c9b7  ja      loc_14027EA3E
0x14027c9bd  mov     eax, dword ptr [rsp+18C8h+var_17EC+4]
0x14027c9c4  test    edx, edx
0x14027c9c6  jz      short loc_14027C9DD
0x14027c9c8  cmp     eax, 903h
0x14027c9cd  jb      short loc_14027C9D9
0x14027c9cf  cmp     dword ptr [rsp+18C8h+var_17EC], 1
0x14027c9d7  jz      short loc_14027C9DD
0x14027c9d9  mov     cl, 1
0x14027c9db  jmp     short loc_14027C9E0
0x14027c9dd  mov     cl, r14b
0x14027c9e0  mov     r10, [rsp+18C8h]
0x14027c9e8  test    cl, cl
0x14027c9ea  jnz     loc_14027EA55
0x14027c9f0  test    bl, bl
0x14027c9f2  jnz     short loc_14027CA15
0x14027c9f4  cmp     edx, 3
0x14027c9f7  jnz     short loc_14027CA02
0x14027c9f9  cmp     eax, 0B00h
0x14027c9fe  mov     al, 1
0x14027ca00  jb      short loc_14027CA05
0x14027ca02  mov     al, r14b
0x14027ca05  mov     rcx, [rsp+18C8h]; this
0x14027ca0d  test    al, al
0x14027ca0f  jnz     loc_14027EA6F
0x14027ca15  lea     rcx, [rsp+18C8h+var_78]; this
0x14027ca1d  call    ??1VmRepositoryAutoLock@@QEAA@XZ; VmRepositoryAutoLock::~VmRepositoryAutoLock(void)
0x14027ca22  mov     rax, [rdi]
0x14027ca25  mov     rcx, rdi
0x14027ca28  mov     rax, [rax+8]
0x14027ca2c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14027ca31  mov     rcx, rax
0x14027ca34  mov     [rsp+18C8h+var_1818], rax
0x14027ca3c  mov     rax, [rax]
0x14027ca3f  mov     rax, [rax+58h]
0x14027ca43  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14027ca48  mov     [rsp+18C8h+var_1868], rax
0x14027ca4d  mov     al, [rax+110h]
0x14027ca53  mov     byte ptr [rsp+18C8h+var_1888+1], al
0x14027ca57  mov     [r12+5Ch], al
0x14027ca5c  xorps   xmm1, xmm1
0x14027ca5f  movdqu  [rsp+18C8h+var_1730], xmm1
0x14027ca68  mov     [rsp+18C8h+var_1720], r14
0x14027ca70  movdqu  [rsp+18C8h+var_1760], xmm1
0x14027ca79  mov     [rsp+18C8h+var_1750], r14
0x14027ca81  mov     dl, 1
0x14027ca83  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_L1VH_VMMFeatures@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_L1VH_VMMFeatures@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_L1VH_VMMFeatures> `wil::Feature<__WilFeatureTraits_Feature_L1VH_VMMFeatures>::GetImpl(void)'::`2'::impl
0x14027ca8a  call    ?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_L1VH_VMMFeatures@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_L1VH_VMMFeatures>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)
0x14027ca8f  mov     rbx, [rsp+18C8h+var_1808]
0x14027ca97  cmp     [r12+72h], r14b
0x14027ca9c  jz      short loc_14027CACB
0x14027ca9e  lea     rdx, [rbx+10h]
0x14027caa2  cmp     [rdx], r14w
0x14027caa6  jz      short loc_14027CAB5
0x14027caa8  lea     rcx, [rsp+18C8h+var_1760]
0x14027cab0  call    ?Initialize@?$HvPartitionPropertyPayload@U_HV_PARTITION_PROPERTY_ASSIGNABLE_SYNTHETIC_PROCESSOR_FEATURES@@@@QEAAXAEBU_HV_PARTITION_PROPERTY_ASSIGNABLE_SYNTHETIC_PROCESSOR_FEATURES@@@Z; HvPartitionPropertyPayload<_HV_PARTITION_PROPERTY_ASSIGNABLE_SYNTHETIC_PROCESSOR_FEATURES>::Initialize(_HV_PARTITION_PROPERTY_ASSIGNABLE_SYNTHETIC_PROCESSOR_FEATURES const &)
0x14027cab5  cmp     [rbx], r14w
0x14027cab9  jz      short loc_14027CACB
0x14027cabb  mov     rdx, rbx
0x14027cabe  lea     rcx, [rsp+18C8h+var_1730]
0x14027cac6  call    ?Initialize@?$HvPartitionPropertyPayload@U_HV_PARTITION_PROPERTY_ASSIGNABLE_SYNTHETIC_PROCESSOR_FEATURES@@@@QEAAXAEBU_HV_PARTITION_PROPERTY_ASSIGNABLE_SYNTHETIC_PROCESSOR_FEATURES@@@Z; HvPartitionPropertyPayload<_HV_PARTITION_PROPERTY_ASSIGNABLE_SYNTHETIC_PROCESSOR_FEATURES>::Initialize(_HV_PARTITION_PROPERTY_ASSIGNABLE_SYNTHETIC_PROCESSOR_FEATURES const &)
0x14027cacb  xorps   xmm1, xmm1
0x14027cace  movdqu  [rsp+18C8h+var_1748], xmm1
0x14027cad7  mov     [rsp+18C8h+var_1738], r14
0x14027cadf  mov     r8, [rbx+20h]
0x14027cae3  test    r8, r8
0x14027cae6  jz      short loc_14027CB06
0x14027cae8  mov     rdx, [rbx+40h]
0x14027caec  test    rdx, rdx
0x14027caef  jz      short loc_14027CB06
0x14027caf1  lea     r8, ds:8[r8*8]
0x14027caf9  lea     rcx, [rsp+18C8h+var_1748]
0x14027cb01  call    ?InitializeFromBuffer@?$HvPartitionPropertyPayload@U_HV_PARTITION_PROPERTY_PROCESSOR_FEATURES_EX@@@@QEAAXPEBU_HV_PARTITION_PROPERTY_PROCESSOR_FEATURES_EX@@_K@Z; HvPartitionPropertyPayload<_HV_PARTITION_PROPERTY_PROCESSOR_FEATURES_EX>::InitializeFromBuffer(_HV_PARTITION_PROPERTY_PROCESSOR_FEATURES_EX const *,unsigned __int64)
0x14027cb06  xorps   xmm0, xmm0
0x14027cb09  xor     eax, eax
0x14027cb0b  movups  [rsp+18C8h+var_1698], xmm0
0x14027cb13  mov     [rsp+18C8h+var_1688], rax
0x14027cb1b  mov     rcx, qword ptr [rsp+18C8h+var_1748+8]
0x14027cb23  sub     rcx, qword ptr [rsp+18C8h+var_1748]
0x14027cb2b  sub     rcx, qword ptr [rsp+18C8h+var_1760]
0x14027cb33  sub     rcx, qword ptr [rsp+18C8h+var_1730]
0x14027cb3b  add     rcx, qword ptr [rsp+18C8h+var_1760+8]
0x14027cb43  mov     rdx, qword ptr [rsp+18C8h+var_1730+8]
0x14027cb4b  add     rdx, 10C70h
0x14027cb52  add     rdx, rcx
0x14027cb55  lea     rcx, [rsp+18C8h+var_1698]
0x14027cb5d  call    ??0?$vector@W4byte@gsl@@V?$allocator@W4byte@gsl@@@std@@@std@@QEAA@_KAEBV?$allocator@W4byte@gsl@@@1@@Z; std::vector<gsl::byte>::vector<gsl::byte>(unsigned __int64,std::allocator<gsl::byte> const &)
0x14027cb62  nop
0x14027cb63  xorps   xmm0, xmm0
0x14027cb66  movups  xmmword ptr [rsp+18C8h+var_17C8], xmm0
0x14027cb6e  lea     rdx, [rsp+18C8h+var_1698]
0x14027cb76  lea     rcx, [rsp+18C8h+var_17C8]
0x14027cb7e  call    ??$?0$0?0V?$vector@EV?$allocator@E@std@@@std@@$0A@@?$span@E$0?0@gsl@@QEAA@AEAV?$vector@EV?$allocator@E@std@@@std@@@Z; gsl::span<uchar,-1>::span<uchar,-1>(std::vector<uchar> &)
0x14027cb83  mov     r15, [rsp+18C8h+var_17C8+8]
0x14027cb8b  mov     rax, [rsp+18C8h+var_17C8]
0x14027cb93  mov     [rsp+18C8h+var_78], rax
0x14027cb9b  mov     [rsp+18C8h+var_78+8], r15
0x14027cba3  lea     rcx, [rsp+18C8h+var_78]
0x14027cbab  call    ?size_bytes@?$span@E$0?0@gsl@@QEBA_KXZ; gsl::span<uchar,-1>::size_bytes(void)
0x14027cbb0  mov     ebx, 10B40h
0x14027cbb5  cmp     rax, rbx
0x14027cbb8  jb      loc_14027F2CA
0x14027cbbe  lea     rcx, [rsp+18C8h+var_78]
0x14027cbc6  call    ?size_bytes@?$span@E$0?0@gsl@@QEBA_KXZ; gsl::span<uchar,-1>::size_bytes(void)
0x14027cbcb  mov     r8d, ebx; Size
0x14027cbce  xor     edx, edx; Val
0x14027cbd0  mov     rcx, r15; void *
0x14027cbd3  call    memset_0
0x14027cbd8  mov     ecx, 10C70h
0x14027cbdd  call    ??$narrow@I_K$0A@@gsl@@YAI_K@Z; gsl::narrow<uint,unsigned __int64,0>(unsigned __int64)
0x14027cbe2  mov     edi, eax
0x14027cbe4  mov     [rsp+18C8h+var_78], r14
0x14027cbec  mov     r9d, 130h
0x14027cbf2  mov     r8d, ebx
0x14027cbf5  lea     rdx, [rsp+18C8h+var_1780]
0x14027cbfd  lea     rcx, [rsp+18C8h+var_17C8]
0x14027cc05  call    ?subspan@?$span@$$CBW4byte@gsl@@$0?0@gsl@@QEBA?AV12@_K0@Z; gsl::span<gsl::byte const,-1>::subspan(unsigned __int64,unsigned __int64)
0x14027cc0a  movups  xmm6, xmmword ptr [rax]
0x14027cc0d  movaps  [rsp+18C8h+var_1848], xmm6
0x14027cc15  lea     rcx, [rsp+18C8h+var_1848]
0x14027cc1d  call    ?size_bytes@?$span@E$0?0@gsl@@QEBA_KXZ; gsl::span<uchar,-1>::size_bytes(void)
0x14027cc22  test    al, 0Fh
0x14027cc24  jnz     loc_14027F2C4
0x14027cc2a  movdqa  [rsp+18C8h+var_1848], xmm6
0x14027cc33  psrldq  xmm6, 8
0x14027cc38  movq    rbx, xmm6
0x14027cc3d  lea     rcx, [rsp+18C8h+var_1848]
0x14027cc45  call    ?size_bytes@?$span@E$0?0@gsl@@QEBA_KXZ; gsl::span<uchar,-1>::size_bytes(void)
0x14027cc4a  shr     rax, 4
0x14027cc4e  mov     rdx, rax
0x14027cc51  lea     rcx, [rsp+18C8h+var_78]
0x14027cc59  call    ??0?$extent_type@$0?0@details@gsl@@QEAA@_K@Z; gsl::details::extent_type<-1>::extent_type<-1>(unsigned __int64)
0x14027cc5e  mov     [rsp+18C8h+var_78+8], rbx
0x14027cc66  cmp     [rsp+18C8h+var_78], 0FFFFFFFFFFFFFFFFh
0x14027cc6f  jz      loc_14027F2C4
0x14027cc75  test    rbx, rbx
0x14027cc78  jnz     short loc_14027CC88
0x14027cc7a  cmp     [rsp+18C8h+var_78], r14
0x14027cc82  jnz     loc_14027F2C4
0x14027cc88  mov     qword ptr [rsp+18C8h+var_1848], r14
0x14027cc90  mov     r8, rdi
0x14027cc93  or      r9, 0FFFFFFFFFFFFFFFFh
0x14027cc97  lea     rdx, [rsp+18C8h+var_1780]
0x14027cc9f  lea     rcx, [rsp+18C8h+var_17C8]
0x14027cca7  call    ?subspan@?$span@$$CBW4byte@gsl@@$0?0@gsl@@QEBA?AV12@_K0@Z; gsl::span<gsl::byte const,-1>::subspan(unsigned __int64,unsigned __int64)
0x14027ccac  movups  xmm6, xmmword ptr [rax]
0x14027ccaf  movaps  xmmword ptr [rsp+18C8h+var_17C8], xmm6
0x14027ccb7  lea     rcx, [rsp+18C8h+var_17C8]
0x14027ccbf  call    ?size_bytes@?$span@E$0?0@gsl@@QEBA_KXZ; gsl::span<uchar,-1>::size_bytes(void)
0x14027ccc4  movdqa  xmmword ptr [rsp+18C8h+var_17C8], xmm6
0x14027cccd  psrldq  xmm6, 8
0x14027ccd2  movq    rbx, xmm6
0x14027ccd7  lea     rcx, [rsp+18C8h+var_17C8]
0x14027ccdf  call    ?size_bytes@?$span@E$0?0@gsl@@QEBA_KXZ; gsl::span<uchar,-1>::size_bytes(void)
0x14027cce4  mov     rdx, rax
0x14027cce7  lea     rcx, [rsp+18C8h+var_1848]
0x14027ccef  call    ??0?$extent_type@$0?0@details@gsl@@QEAA@_K@Z; gsl::details::extent_type<-1>::extent_type<-1>(unsigned __int64)
0x14027ccf4  mov     qword ptr [rsp+18C8h+var_1848+8], rbx
0x14027ccfc  cmp     qword ptr [rsp+18C8h+var_1848], 0FFFFFFFFFFFFFFFFh
0x14027cd05  jz      loc_14027F2BE
0x14027cd0b  test    rbx, rbx
0x14027cd0e  jnz     short loc_14027CD1E
0x14027cd10  cmp     qword ptr [rsp+18C8h+var_1848], r14
0x14027cd18  jnz     loc_14027F2BE
0x14027cd1e  mov     qword ptr [rsp+18C8h+var_1718], r15
0x14027cd26  movups  xmm0, xmmword ptr [rsp+18C8h+var_78]
0x14027cd2e  movdqu  [rsp+18C8h+var_1718+8], xmm0
0x14027cd37  mov     dword ptr [rsp+18C8h+var_1700], edi
0x14027cd3e  movups  xmm1, [rsp+18C8h+var_1848]
0x14027cd46  movdqu  [rsp+18C8h+var_16F8], xmm1
0x14027cd4f  mov     dl, 1
0x14027cd51  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_L1VH_VMMFeatures@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_L1VH_VMMFeatures@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_L1VH_VMMFeatures> `wil::Feature<__WilFeatureTraits_Feature_L1VH_VMMFeatures>::GetImpl(void)'::`2'::impl
0x14027cd58  call    ?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_L1VH_VMMFeatures@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_L1VH_VMMFeatures>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)
  ... truncated ...
```
