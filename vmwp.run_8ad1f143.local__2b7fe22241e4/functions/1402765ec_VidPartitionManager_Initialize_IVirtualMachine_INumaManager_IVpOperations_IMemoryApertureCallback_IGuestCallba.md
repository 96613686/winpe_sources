# VidPartitionManager::Initialize(IVirtualMachine *,INumaManager *,IVpOperations *,IMemoryApertureCallback *,IGuestCallback *,void *,void *,Config::VmWorkerProcess::ProcessorSettings const &,Config::VmWorkerProcess::MemorySettings const &,_HV_PARTITION_CREATION_PROPERTIES_V2 const &,_HV_PARTITION_SYNTHETIC_PROCESSOR_FEATURES const &,_VMM_PARTITION_PROPERTIES const &)

- ea: `0x1402765ec`
- end: `0x14027918b`
- name: `?Initialize@VidPartitionManager@@AEAAJPEAUIVirtualMachine@@PEAUINumaManager@@PEAUIVpOperations@@PEAVIMemoryApertureCallback@@PEAUIGuestCallback@@PEAX5AEBUProcessorSettings@VmWorkerProcess@Config@@AEBUMemorySettings@89@AEBU_HV_PARTITION_CREATION_PROPERTIES_V2@@AEBT_HV_PARTITION_SYNTHETIC_PROCESSOR_FEATURES@@AEBU_VMM_PARTITION_PROPERTIES@@@Z`
- size: `11167`
- prototype: `__int64 __fastcall(VidPartitionManager *__hidden this, struct IVirtualMachine *, struct INumaManager *, struct IVpOperations *, struct IMemoryApertureCallback *, struct IGuestCallback *, void *, void *, const struct Config::VmWorkerProcess::ProcessorSettings *, const struct Config::VmWorkerProcess::MemorySettings *, const struct _HV_PARTITION_CREATION_PROPERTIES_V2 *, const union _HV_PARTITION_SYNTHETIC_PROCESSOR_FEATURES *, const struct _VMM_PARTITION_PROPERTIES *)`
- caller_count: `1`
- callee_count: `69`
- tags: `file_ops, registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x140275c70`

## callees

- `0x14000d5a0`
- `0x14000d638`
- `0x14000d6e0`
- `0x14000d778`
- `0x14001e648`
- `0x140021d20`
- `0x140021fd8`
- `0x14002a1d0`
- `0x140031ca8`
- `0x140042260`
- `0x14004c13c`
- `0x140051a78`
- `0x14005342c`
- `0x1400544a8`
- `0x1400545d0`
- `0x140054a90`
- `0x14005600c`
- `0x14005613c`
- `0x1400586e4`
- `0x14005b648`
- `0x14005e804`
- `0x14005ecc0`
- `0x140061ddc`
- `0x140066780`
- `0x140067f6c`
- `0x14006af58`
- `0x14006fee8`
- `0x140070bcc`
- `0x140081798`
- `0x1400828fc`
- `0x1400996d8`
- `0x14009d7cc`
- `0x1400b2bf0`
- `0x1400c5a3c`
- `0x1400c5d44`
- `0x1400d4974`
- `0x1400dd814`
- `0x1400df760`
- `0x1400e7f6c`
- `0x1400e8d14`
- `0x1400e8d40`
- `0x1400fe1dc`
- `0x14012f6ac`
- `0x140132960`
- `0x140132d0c`
- `0x14013361c`
- `0x140135955`
- `0x1401452b4`
- `0x14014c608`
- `0x1401dec68`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140278dae`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14027909b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140278dae`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14027909b`
- `vid!VidOpenStatisticsHandle` at `0x1402766a7`
- `vid!VidOpenStatisticsHandle` at `0x1402766a7`
- `vid!VidGetSystemInformation` at `0x1402775f2`
- `vid!VidGetSystemInformation` at `0x1402775f2`
- `vid!VidGetSystemTopology` at `0x14027756c`
- `vid!VidGetSystemTopology` at `0x14027756c`
- `vid!VidQueryPartitionInformation` at `0x140278682`
- `vid!VidQueryPartitionInformation` at `0x140278682`
- `vid!VidSetPartitionProperty` at `0x1402783f7`
- `vid!VidSetPartitionProperty` at `0x1402783f7`
- `vid!VidGetPartitionPropertyEx` at `0x14027742a`
- `vid!VidGetPartitionPropertyEx` at `0x14027833d`
- `vid!VidGetPartitionPropertyEx` at `0x14027742a`
- `vid!VidGetPartitionPropertyEx` at `0x14027833d`
- `vid!VidCreatePartition` at `0x140278297`
- `vid!VidCreatePartition` at `0x140278297`
- `vid!VidSetPartitionFriendlyName` at `0x1402783c3`
- `vid!VidSetPartitionFriendlyName` at `0x1402783c3`
- `vid!VidAttachPartition` at `0x1402782b7`
- `vid!VidAttachPartition` at `0x1402782b7`

## string_xrefs

- `0x1402767bd`: `/configuration/global_settings/debug/channel_id`
- `0x140278d66`: `Failed to copy specified hosting process name suffix into the IOCTL buffer`
- `0x140278e19`: `Failed to create partition. GetLastError=%d .\n`
- `0x140278a2d`: `Physically backed VMs don't support private compression stores.`
- `0x140278a5f`: `Physically backed VMs don't support deferred commit.`

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
  HKEY v16; // r13
  __int64 v17; // rax
  const char *v18; // r9
  __int64 v19; // rax
  int v20; // eax
  unsigned __int8 v21; // al
  __int64 v22; // r12
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
  __int64 v41; // rbx
  __int64 v42; // rdi
  __int64 v43; // rsi
  __int64 v44; // rbx
  __int64 v45; // rax
  __int64 v46; // rbx
  unsigned int v47; // eax
  __int64 v48; // rdi
  int v49; // eax
  int v50; // eax
  int v51; // eax
  int v52; // eax
  __int64 v53; // r12
  __int64 v54; // rbx
  __int64 v55; // rax
  __int64 v56; // rax
  int v57; // edi
  __int64 v58; // rax
  __int64 v59; // rsi
  unsigned int v60; // edi
  __int64 v61; // rax
  __int64 v62; // rax
  unsigned int v63; // eax
  __int128 v64; // xmm6
  const struct Config::VmWorkerProcess::MemorySettings *v65; // rsi
  __int64 v66; // r12
  unsigned int v67; // edx
  int v68; // edx
  unsigned int v69; // eax
  __int64 *v70; // rbx
  __int64 v71; // rdx
  void (__fastcall *v72)(__int64 *, struct VmRepository **, _QWORD); // rdi
  unsigned int v73; // eax
  void *v74; // rbx
  const unsigned __int16 *v75; // r8
  VmPrefixRepository *v76; // rax
  struct VmRepository *v77; // rbx
  struct VmRepository *v78; // rdi
  __int64 v79; // rax
  __int64 v80; // r12
  __int64 v81; // rcx
  __int64 v82; // rax
  __int64 v83; // rcx
  __int64 v84; // rbx
  __int64 v85; // rax
  __int64 v86; // rcx
  __int64 v87; // rdi
  char v88; // bl
  unsigned __int64 v89; // rdi
  int SystemTopology; // esi
  __int64 v91; // rax
  const char *v92; // r9
  unsigned int v93; // eax
  struct IVpOperations *v94; // r12
  unsigned int v95; // ecx
  unsigned int v96; // esi
  __int64 v97; // rbx
  unsigned int v98; // ecx
  unsigned int v99; // esi
  __int64 v100; // rbx
  unsigned int v101; // ecx
  unsigned int v102; // esi
  __int64 v103; // rbx
  unsigned int v104; // ecx
  unsigned int v105; // esi
  __int64 v106; // rbx
  __int64 v107; // rbx
  __int64 v108; // rdi
  __int64 v109; // rbx
  __int64 v110; // rsi
  __int64 v111; // rdi
  __int64 v112; // rax
  unsigned int v113; // ecx
  unsigned int v114; // ebx
  const struct Config::VmWorkerProcess::MemorySettings *v115; // r12
  int v116; // ecx
  int v117; // ecx
  unsigned int v118; // ebx
  wchar_t *v119; // rax
  __int64 v120; // rcx
  char v121; // al
  __int64 v122; // rcx
  __int64 v123; // rsi
  __int64 v124; // rax
  unsigned __int64 v125; // rdx
  __int64 v126; // rcx
  unsigned int v127; // eax
  __int64 v128; // rcx
  __int64 v129; // rax
  __int64 v130; // r9
  const unsigned __int16 *v131; // r8
  int v132; // eax
  __int64 v133; // rbx
  struct IVirtualMachine *v134; // rbx
  char v135; // di
  char v136; // al
  char v137; // bl
  unsigned int v138; // ecx
  unsigned int v139; // r12d
  __int64 v140; // rbx
  char v141; // cl
  unsigned int v142; // ecx
  unsigned int v143; // edi
  __int64 v144; // rbx
  struct IVpOperations *v145; // rbx
  unsigned int v146; // ecx
  unsigned int v147; // edi
  __int64 v148; // rbx
  struct IVirtualMachine *v149; // rbx
  unsigned __int64 v150; // rdi
  unsigned int v151; // ecx
  unsigned int v152; // ebx
  __int64 v153; // rax
  unsigned int v154; // eax
  __int64 v155; // rbx
  __int64 v156; // rax
  int v157; // eax
  unsigned int v158; // ecx
  unsigned int v159; // edi
  VidPartitionManager *v160; // rdi
  __int64 v161; // rbx
  __int64 v162; // rax
  __int64 Partition; // rax
  void **v164; // rsi
  const char *v165; // r9
  const char *v166; // rdi
  unsigned __int8 *v167; // rcx
  unsigned __int64 v168; // r15
  unsigned __int64 i; // rbx
  const struct _VMM_PARTITION_PROPERTIES *v170; // r12
  __int64 v171; // rdi
  __int64 v172; // rax
  int v173; // eax
  const char *v174; // r9
  wil *v175; // rcx
  char *v176; // rbx
  unsigned int v177; // eax
  wil *v178; // rcx
  __int64 v179; // r15
  int Instance; // eax
  struct INumaManager *v181; // r15
  int v182; // eax
  const char *v183; // r9
  unsigned __int8 v184; // dl
  unsigned __int8 v185; // r8
  __int64 v186; // r9
  __int64 v187; // rcx
  unsigned __int8 j; // dl
  unsigned int v189; // r12d
  int v190; // r12d
  const struct _tlgProvider_t *v191; // rax
  int v192; // ebx
  void *v193; // rbx
  WorkerStatsPanel *v194; // rbx
  unsigned int v195; // edi
  const unsigned __int16 *v196; // r8
  const struct _GUID *v197; // r9
  int v198; // eax
  const char *v199; // r9
  __int64 result; // rax
  unsigned int v201; // eax
  unsigned int v202; // eax
  unsigned int v203; // eax
  unsigned int v204; // eax
  unsigned int v205; // eax
  unsigned int v206; // eax
  unsigned int v207; // eax
  unsigned int v208; // eax
  unsigned int v209; // eax
  unsigned int v210; // eax
  unsigned int v211; // eax
  unsigned int v212; // eax
  int v213; // edx
  unsigned int v214; // eax
  int v215; // edx
  unsigned int v216; // eax
  int v217; // edx
  const wchar_t *v218; // r8
  unsigned int v219; // eax
  unsigned int v220; // eax
  signed int LastError; // eax
  const struct _GUID *v222; // r8
  const unsigned __int16 *v223; // r9
  unsigned int v224; // esi
  unsigned int v225; // edi
  unsigned int v226; // eax
  const struct _tlgProvider_t *v227; // rax
  int v228; // ebx
  __int64 v229; // rax
  int v230; // r8d
  int v231; // r9d
  unsigned int v232; // eax
  const struct _tlgProvider_t *v233; // rax
  int v234; // esi
  __int64 v235; // rax
  int v236; // r8d
  int v237; // r9d
  unsigned int v238; // eax
  signed int v239; // eax
  unsigned int v240; // ebx
  const struct _tlgProvider_t *v241; // rax
  int v242; // edi
  __int64 v243; // rax
  int v244; // r8d
  int v245; // r9d
  unsigned int v246; // eax
  wil *v247; // rcx
  __int64 v248; // rax
  unsigned int v249; // eax
  unsigned int v250; // eax
  unsigned int v251; // ebx
  __int64 v252; // r9
  VidPartitionManager *v253; // rbx
  unsigned int v254; // ebx
  __int64 v255; // r9
  VidPartitionManager *v256; // rbx
  __int64 v257; // rax
  __int64 v258; // rax
  int v259; // [rsp+20h] [rbp-1898h]
  int v260; // [rsp+20h] [rbp-1898h]
  struct IVpOperations *v261; // [rsp+20h] [rbp-1898h]
  struct IVpOperations *v262; // [rsp+20h] [rbp-1898h]
  int v263; // [rsp+20h] [rbp-1898h]
  int v264; // [rsp+20h] [rbp-1898h]
  int v265; // [rsp+20h] [rbp-1898h]
  struct IMemoryApertureCallback *v266; // [rsp+28h] [rbp-1890h]
  struct IMemoryApertureCallback *v267; // [rsp+28h] [rbp-1890h]
  struct IGuestCallback *v268; // [rsp+30h] [rbp-1888h]
  unsigned __int8 v269; // [rsp+40h] [rbp-1878h] BYREF
  unsigned __int8 v270; // [rsp+41h] [rbp-1877h]
  __int64 v271; // [rsp+48h] [rbp-1870h] BYREF
  int v272; // [rsp+50h] [rbp-1868h]
  unsigned int v273; // [rsp+54h] [rbp-1864h] BYREF
  const struct _VMM_PARTITION_PROPERTIES *v274; // [rsp+58h] [rbp-1860h] BYREF
  struct INumaManager *v275; // [rsp+60h] [rbp-1858h]
  struct INumaManager *v276; // [rsp+68h] [rbp-1850h] BYREF
  VidPartitionManager *v277; // [rsp+70h] [rbp-1848h]
  struct IVpOperations *v278; // [rsp+78h] [rbp-1840h]
  unsigned int *v279; // [rsp+80h] [rbp-1838h]
  __int64 v280[2]; // [rsp+88h] [rbp-1830h] BYREF
  __int64 v281; // [rsp+98h] [rbp-1820h] BYREF
  __int64 v282; // [rsp+A0h] [rbp-1818h]
  VidPartitionManager *v283; // [rsp+A8h] [rbp-1810h]
  struct IVirtualMachine *v284; // [rsp+B0h] [rbp-1808h]
  struct IGuestCallback *v285; // [rsp+B8h] [rbp-1800h]
  const std::exception *v286; // [rsp+C0h] [rbp-17F8h] BYREF
  unsigned int HvCompatibilityVersion; // [rsp+C8h] [rbp-17F0h] BYREF
  unsigned int v288; // [rsp+CCh] [rbp-17ECh] BYREF
  unsigned __int8 v289; // [rsp+D0h] [rbp-17E8h] BYREF
  unsigned int v290; // [rsp+D4h] [rbp-17E4h] BYREF
  unsigned int v291; // [rsp+D8h] [rbp-17E0h] BYREF
  unsigned int v292; // [rsp+DCh] [rbp-17DCh] BYREF
  int v293; // [rsp+E0h] [rbp-17D8h] BYREF
  struct VmRepository *v294; // [rsp+E8h] [rbp-17D0h] BYREF
  __m128i v295; // [rsp+F0h] [rbp-17C8h] BYREF
  void *v296[2]; // [rsp+100h] [rbp-17B8h] BYREF
  __int128 v297; // [rsp+110h] [rbp-17A8h]
  __int128 v298; // [rsp+120h] [rbp-1798h]
  __int64 v299; // [rsp+130h] [rbp-1788h] BYREF
  const struct Config::VmWorkerProcess::MemorySettings *v300; // [rsp+138h] [rbp-1780h] BYREF
  HKEY phkResult; // [rsp+140h] [rbp-1778h] BYREF
  unsigned int v302; // [rsp+148h] [rbp-1770h] BYREF
  char *v303; // [rsp+150h] [rbp-1768h] BYREF
  __int128 v304; // [rsp+158h] [rbp-1760h] BYREF
  __int64 v305; // [rsp+168h] [rbp-1750h]
  __int128 v306; // [rsp+170h] [rbp-1748h] BYREF
  __int64 v307; // [rsp+180h] [rbp-1738h]
  __int128 v308; // [rsp+188h] [rbp-1730h] BYREF
  __int64 v309; // [rsp+198h] [rbp-1720h]
  _BYTE v310[24]; // [rsp+1A0h] [rbp-1718h] BYREF
  __int64 v311; // [rsp+1B8h] [rbp-1700h]
  __m128i v312; // [rsp+1C0h] [rbp-16F8h]
  __int128 v313; // [rsp+1D0h] [rbp-16E8h]
  __int64 v314; // [rsp+1E0h] [rbp-16D8h]
  __int64 v315; // [rsp+1E8h] [rbp-16D0h]
  int v316; // [rsp+1F0h] [rbp-16C8h]
  void *v317[2]; // [rsp+200h] [rbp-16B8h] BYREF
  void *v318[2]; // [rsp+210h] [rbp-16A8h] BYREF
  __int128 v319; // [rsp+220h] [rbp-1698h] BYREF
  __int64 v320; // [rsp+230h] [rbp-1688h]
  void *Src[2]; // [rsp+238h] [rbp-1680h] BYREF
  _DWORD v322[2]; // [rsp+250h] [rbp-1668h] BYREF
  _QWORD v323[509]; // [rsp+258h] [rbp-1660h]
  _BYTE v324[1536]; // [rsp+1240h] [rbp-678h] BYREF
  char *v325[2]; // [rsp+1840h] [rbp-78h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+18B8h] [rbp+0h]

  v278 = a4;
  v275 = a3;
  v284 = a2;
  v277 = this;
  v283 = this;
  v276 = a3;
  v271 = (__int64)a4;
  v285 = a6;
  v300 = a10;
  v274 = a13;
  v16 = (HKEY)((char *)this + 104);
  Vml::VmReferencePtr<IVirtualMachine,Vml::VmWeakReferenceTraits>::Reset((char *)this + 104);
  try
  {
    *((_BYTE *)this + 114) = (*(unsigned int (__fastcall **)(struct IVpOperations *))(*(_QWORD *)a4 + 184LL))(a4) != 0;
    v17 = VidOpenStatisticsHandle();
    *((_QWORD *)this + 10) = v17;
    if ( (unsigned __int64)(v17 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
    {
      v19 = (*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)v16 + 48LL))(*(_QWORD *)v16);
      v20 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v19 + 152LL))(v19);
      v279 = (unsigned int *)((char *)this + 88);
      *((_DWORD *)this + 22) = v20;
      v21 = lambda_997682190daf7855ab97ce0562d05e09_::operator()();
      v22 = v21;
      v269 = v21;
      v303 = 0;
      v292 = 0;
      v290 = 0;
      v299 = 0;
      (*(void (__fastcall **)(_QWORD, __int64 *))(**(_QWORD **)v16 + 56LL))(*(_QWORD *)v16, &v299);
      *(_OWORD *)v325 = 0;
      VmRepositoryAutoLock::VmRepositoryAutoLock(v325, v299, 0);
      if ( SLODWORD(v325[1]) < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x161,
          (unsigned int)"onecore\\vm\\worker\\vidpartition\\vidpartitionmanager.cpp",
          (const char *)LODWORD(v325[1]),
          v260);
      v23 = (*(__int64 (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v299 + 288LL))(v299, &v292);
      if ( v23 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x166,
          (unsigned int)"onecore\\vm\\worker\\vidpartition\\vidpartitionmanager.cpp",
          (const char *)(unsigned int)v23,
          v260);
      (*(void (__fastcall **)(__int64, const unsigned __int16 *, char **))(*(_QWORD *)v299 + 112LL))(
        v299,
        L"/configuration/global_settings/debug/channel_id",
        &v303);
      (*(void (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v299 + 320LL))(v299, &v290);
      memset(v310, 0, sizeof(v310));
      v311 = 0;
      v312 = 0u;
      v313 = 0;
      v314 = 0;
      v315 = 0;
      v316 = 0;
      if ( !*(_BYTE *)Marshal::FromRepository<Vml::VmReferencePtr<VmRepository,Vml::VmUserReferenceTraits> const &,Config::VmWorkerProcess::TopologySettings,>(
                        v296,
                        &v299,
                        v310) )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x170,
          (unsigned int)"onecore\\vm\\worker\\vidpartition\\vidpartitionmanager.cpp",
          (const char *)0x80070057LL,
          v260);
      std::vector<std::pair<std::wstring,enum Marshal::UnmarshalError>>::_Tidy(&v296[1]);
      v272 = v314;
      v273 = v314;
      if ( (unsigned int)v314 > 3 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x175,
          (unsigned int)"onecore\\vm\\worker\\vidpartition\\vidpartitionmanager.cpp",
          (const char *)0x80070057LL,
          v260);
      if ( (_DWORD)v314 && (v292 < 0x903 || v290 != 1) )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x17A,
          (unsigned int)"onecore\\vm\\worker\\vidpartition\\vidpartitionmanager.cpp",
          (const char *)0x80070057LL,
          v260);
      if ( !(_BYTE)v22 )
      {
        if ( (_DWORD)v314 != 3 || (v25 = 1, v292 >= 0xB00) )
          v25 = 0;
        if ( v25 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x180,
            (unsigned int)"onecore\\vm\\worker\\vidpartition\\vidpartitionmanager.cpp",
            (const char *)0x80070057LL,
            v260);
      }
      VmRepositoryAutoLock::~VmRepositoryAutoLock((VmRepositoryAutoLock *)v325);
      v282 = (*(__int64 (__fastcall **)(struct INumaManager *))(*(_QWORD *)a3 + 8LL))(a3);
      v281 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v282 + 88LL))(v282);
      v270 = *(_BYTE *)(v281 + 272);
      *((_BYTE *)this + 92) = v270;
      v308 = 0;
      v309 = 0;
      v304 = 0;
      v305 = 0;
      LOBYTE(v26) = 1;
      wil::details::FeatureImpl<__WilFeatureTraits_Feature_L1VH_VMMFeatures>::ReportUsage(
        `wil::Feature<__WilFeatureTraits_Feature_L1VH_VMMFeatures>::GetImpl'::`2'::impl,
        v26);
      if ( *((_BYTE *)this + 114) )
      {
        if ( *((_WORD *)a13 + 8) )
          HvPartitionPropertyPayload<_HV_PARTITION_PROPERTY_ASSIGNABLE_SYNTHETIC_PROCESSOR_FEATURES>::Initialize(&v304);
        if ( *(_WORD *)a13 )
          HvPartitionPropertyPayload<_HV_PARTITION_PROPERTY_ASSIGNABLE_SYNTHETIC_PROCESSOR_FEATURES>::Initialize(&v308);
      }
      v306 = 0;
      v307 = 0;
      v27 = *((_QWORD *)a13 + 4);
      if ( v27 )
      {
        v28 = *((_QWORD *)a13 + 8);
        if ( v28 )
          HvPartitionPropertyPayload<_HV_PARTITION_PROPERTY_PROCESSOR_FEATURES_EX>::InitializeFromBuffer(
            &v306,
            v28,
            8 * v27 + 8);
      }
      v319 = 0;
      v320 = 0;
      std::vector<enum gsl::byte>::vector<enum gsl::byte>(
        &v319,
        *((_QWORD *)&v304 + 1) + *((_QWORD *)&v306 + 1) - v306 - v304 - v308 + *((_QWORD *)&v308 + 1) + 68704LL);
      *(_OWORD *)v296 = 0;
      gsl::span<unsigned char,-1>::span<unsigned char,-1>(v296, &v319);
      v29 = (unsigned int *)v296[1];
      v325[0] = (char *)v296[0];
      v325[1] = (char *)v296[1];
      if ( (unsigned __int64)gsl::span<unsigned char,-1>::size_bytes(v325) >= 0x10B40 )
      {
        gsl::span<unsigned char,-1>::size_bytes(v325);
        memset_0(v29, 0, 0x10B40u);
        v31 = (unsigned int)gsl::narrow<unsigned int,unsigned __int64,0>(68704);
        v325[0] = 0;
        v32 = *(__m128i *)gsl::span<enum gsl::byte const,-1>::subspan(v296, v280, 68416, 288);
        v295 = v32;
        if ( (gsl::span<unsigned char,-1>::size_bytes(&v295) & 0xF) != 0
          || (v295 = v32,
              v34 = (char *)_mm_srli_si128(v32, 8).m128i_u64[0],
              v35 = gsl::span<unsigned char,-1>::size_bytes(&v295),
              gsl::details::extent_type<-1>::extent_type<-1>(v325, v35 >> 4),
              v325[1] = v34,
              v325[0] == (char *)-1LL)
          || !v34 && v325[0] )
        {
          gsl::details::terminate(v33);
          __debugbreak();
        }
        v295.m128i_i64[0] = 0;
        v36 = *(__m128i *)gsl::span<enum gsl::byte const,-1>::subspan(v296, v280, v31, -1);
        *(__m128i *)v296 = v36;
        gsl::span<unsigned char,-1>::size_bytes(v296);
        *(__m128i *)v296 = v36;
        v37 = _mm_srli_si128(v36, 8).m128i_u64[0];
        v38 = gsl::span<unsigned char,-1>::size_bytes(v296);
        gsl::details::extent_type<-1>::extent_type<-1>(&v295, v38);
        v295.m128i_i64[1] = v37;
        if ( v295.m128i_i64[0] == -1 || !v37 && v295.m128i_i64[0] )
        {
          gsl::details::terminate(v40);
          __debugbreak();
        }
        *(_QWORD *)v310 = v29;
        *(_OWORD *)&v310[8] = *(_OWORD *)v325;
        LODWORD(v311) = v31;
        v312 = v295;
        LOBYTE(v39) = 1;
        wil::details::FeatureImpl<__WilFeatureTraits_Feature_L1VH_VMMFeatures>::ReportUsage(
          `wil::Feature<__WilFeatureTraits_Feature_L1VH_VMMFeatures>::GetImpl'::`2'::impl,
          v39);
        if ( *((_BYTE *)this + 114) )
        {
          if ( *((_QWORD *)&v304 + 1) != (_QWORD)v304 )
          {
            gsl::span<unsigned char,-1>::span<unsigned char,-1>(v296, &v304);
            PartitionConfigHelper::AddProperty(v310, 589831, v296);
          }
          if ( *((_QWORD *)&v308 + 1) != (_QWORD)v308 )
          {
            gsl::span<unsigned char,-1>::span<unsigned char,-1>(v296, &v308);
            PartitionConfigHelper::AddProperty(v310, 589833, v296);
          }
        }
        if ( *((_QWORD *)&v306 + 1) != (_QWORD)v306 )
        {
          gsl::span<unsigned char,-1>::span<unsigned char,-1>(v296, &v306);
          PartitionConfigHelper::AddProperty(v310, 589838, v296);
        }
        v41 = (v22 << 32) | 2;
        if ( (*(unsigned int (__fastcall **)(struct INumaManager *))(*(_QWORD *)v275 + 24LL))(v275) )
          v41 = v22 << 32;
        v42 = v41 | 0x40000000;
        if ( !(*(unsigned __int8 (__fastcall **)(_QWORD))(**(_QWORD **)v16 + 216LL))(*(_QWORD *)v16) )
          v42 = v41;
        v43 = v42 | 0x4000000000000LL;
        if ( !(*(unsigned __int8 (__fastcall **)(_QWORD))(**(_QWORD **)v16 + 224LL))(*(_QWORD *)v16) )
          v43 = v42;
        v44 = v43 | 0x2000000000000LL;
        if ( !(*(unsigned __int8 (__fastcall **)(_QWORD))(**(_QWORD **)v16 + 336LL))(*(_QWORD *)v16) )
          v44 = v43;
        if ( (*(unsigned __int8 (__fastcall **)(_QWORD))(**(_QWORD **)v16 + 344LL))(*(_QWORD *)v16) )
        {
          if ( v292 < 0xC04 )
            wil::details::in1diag3::Throw_Hr(
              retaddr,
              (void *)0x22A,
              (unsigned int)"onecore\\vm\\worker\\vidpartition\\vidpartitionmanager.cpp",
              (const char *)0x80070057LL,
              v260);
          v44 |= 0x40000000000000uLL;
        }
        v45 = v44 | 0x400;
        if ( !*((_BYTE *)a9 + 121) )
          v45 = v44;
        v46 = v45 | 0x100000;
        if ( !*((_BYTE *)a9 + 248) )
          v46 = v45;
        if ( *((_BYTE *)a9 + 256) )
          v47 = *((_DWORD *)a9 + 63);
        else
          v47 = 0;
        v29[11] = v47;
        v48 = (*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)v16 + 448LL))(*(_QWORD *)v16);
        v288 = 0;
        v49 = (*(__int64 (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v48 + 88LL))(v48, &v288);
        if ( v49 < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x243,
            (unsigned int)"onecore\\vm\\worker\\vidpartition\\vidpartitionmanager.cpp",
            (const char *)(unsigned int)v49,
            v260);
        v29[16956] &= 0xFFFFFFF0;
        v29[16956] |= v288 & 0xF;
        v291 = 0;
        v50 = (*(__int64 (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v48 + 96LL))(v48, &v291);
        if ( v50 < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x247,
            (unsigned int)"onecore\\vm\\worker\\vidpartition\\vidpartitionmanager.cpp",
            (const char *)(unsigned int)v50,
            v260);
        if ( v291 )
          v46 |= 8uLL;
        v293 = 0;
        v51 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v48 + 112LL))(v48, &v293);
        if ( v51 < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x24E,
            (unsigned int)"onecore\\vm\\worker\\vidpartition\\vidpartitionmanager.cpp",
            (const char *)(unsigned int)v51,
            v260);
        if ( v293 )
          v46 |= 0x10uLL;
        HvCompatibilityVersion = 0;
        v52 = (*(__int64 (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v48 + 136LL))(
                v48,
                &HvCompatibilityVersion);
        if ( v52 < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x255,
            (unsigned int)"onecore\\vm\\worker\\vidpartition\\vidpartitionmanager.cpp",
            (const char *)(unsigned int)v52,
            v260);
        if ( HvCompatibilityVersion )
          v46 |= 0x80uLL;
        v53 = v46 | 0x80000000000000LL;
        if ( !(*(unsigned __int8 (__fastcall **)(_QWORD))(**(_QWORD **)v16 + 352LL))(*(_QWORD *)v16) )
          v53 = v46;
        if ( (v29[16956] & 0xF) - 2 > 2 )
          goto LABEL_82;
        *((_QWORD *)v29 + 8479) = (*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)v16 + 264LL))(*(_QWORD *)v16);
        v54 = (*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)v16 + 272LL))(*(_QWORD *)v16);
        HvCompatibilityVersion = 0;
        v55 = (*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)v16 + 448LL))(*(_QWORD *)v16);
        (*(void (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v55 + 88LL))(v55, &HvCompatibilityVersion);
        if ( HvCompatibilityVersion == 3 )
        {
          v293 = 0;
          *(_OWORD *)v296 = 0;
          v297 = 0;
          v298 = 0;
          VidPartitionManager::CalculateMaxmimumTdxMigrationStreamCount(v277);
          *(_OWORD *)v296 = 0;
          v297 = 0;
          v298 = 0;
          v56 = (*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)v16 + 448LL))(*(_QWORD *)v16);
          (*(void (__fastcall **)(__int64, int *))(*(_QWORD *)v56 + 144LL))(v56, &v293);
          v57 = v293;
          v58 = (*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)v16 + 48LL))(*(_QWORD *)v16);
          if ( (*(unsigned int (__fastcall **)(__int64, void **))(*(_QWORD *)v58 + 432LL))(v58, v296) )
          {
            if ( !v57 )
            {
              v59 = v29[17098];
              v29[17098] = v59 + 1;
              v60 = *((_DWORD *)v277 + 78);
              v61 = (*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)v16 + 48LL))(*(_QWORD *)v16);
              if ( (*(unsigned __int8 (__fastcall **)(__int64))(*(_QWORD *)v61 + 464LL))(v61) )
              {
                v62 = (*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)v16 + 48LL))(*(_QWORD *)v16);
                v63 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v62 + 472LL))(v62);
                if ( v60 < v63 )
                  v60 = v63;
              }
              v54 |= 4uLL;
              *(_DWORD *)gsl::span<_HV_PARTITION_PROPERTY_ASSOC,-1>::operator[](v325, v59) = 327727;
              *(_QWORD *)(gsl::span<_HV_PARTITION_PROPERTY_ASSOC,-1>::operator[](v325, v59) + 8) = v60 + 1;
              goto LABEL_81;
            }
            if ( v57 != 1 )
            {
              v201 = wil::verify_hresult<long>(2147942487LL);
              LODWORD(v266) = v57;
              wil::details::in1diag3::Throw_HrMsg(
                retaddr,
                (void *)0x2B2,
                (unsigned int)"onecore\\vm\\worker\\vidpartition\\vidpartitionmanager.cpp",
                (const char *)v201,
                (int)"Unknown TDX migratable policy %u",
                (const char *)v266);
            }
          }
          v54 &= ~4uLL;
        }
LABEL_81:
        *((_QWORD *)v29 + 8480) = v54;
LABEL_82:
        v293 = v311;
        v64 = 0;
        v65 = v300;
        if ( (unsigned __int64)(*((_QWORD *)v300 + 5) - 2LL) <= 1 )
        {
          if ( *((_BYTE *)v300 + 160) )
          {
            v67 = v29[12] ^ (v29[12] ^ (*((_DWORD *)v300 + 38) << 11)) & 0x7800;
          }
          else
          {
            v68 = 18432;
            if ( *((_QWORD *)v300 + 23) != 512 )
              v68 = 0x2000;
            v67 = v29[12] & 0xFFFF87FF | v68;
          }
          v29[12] = v67;
          if ( *((_BYTE *)v65 + 176) )
            v69 = v67 ^ (v67 ^ (*((_DWORD *)v65 + 42) << 15)) & 0x78000;
          else
            v69 = v67 & 0xFFF87FFF | 0x20000;
          v29[12] = v69;
          v294 = 0;
          v70 = *(__int64 **)v16;
          v71 = **(_QWORD **)v16;
          v72 = *(void (__fastcall **)(__int64 *, struct VmRepository **, _QWORD))(v71 + 160);
          v73 = (*(__int64 (__fastcall **)(_QWORD))(v71 + 64))(*(_QWORD *)v16);
          v72(v70, &v294, v73);
          if ( v294 )
          {
            v74 = operator new(0x80u);
            v296[0] = v74;
            memset_0(v74, 0, 0x80u);
            v76 = VmPrefixRepository::VmPrefixRepository((VmPrefixRepository *)v74, v294, v75);
            v77 = v76;
            v78 = v294;
            if ( v76 )
              Vml::VmSharableObject::IncrementUserCount((VmPrefixRepository *)((char *)v76 + 8));
            v294 = v77;
            if ( v78 )
            {
              Vml::VmSharableObject::DecrementUserCount((struct VmRepository *)((char *)v78 + 8));
              v77 = v294;
            }
            if ( v77 )
            {
              v79 = MemoryManager::RestoreCloneTemplateId(&MemoryManager::m_Instance, v296, v77);
              if ( *(_BYTE *)(v79 + 16) )
                v64 = *(_OWORD *)v79;
            }
          }
          v80 = v53 | 0x8000000000100LL;
          v81 = v80 | 0x1000;
          if ( !*((_BYTE *)v65 + 313) )
            v81 = v80;
          v82 = v81 | 0x2000;
          if ( !*((_BYTE *)v65 + 314) )
            v82 = v81;
          v83 = v82 | 0x4000;
          if ( !*((_BYTE *)v65 + 315) )
            v83 = v82;
          v84 = v83 | 0x20000;
          if ( !*((_BYTE *)v65 + 316) )
            v84 = v83;
          if ( *((_BYTE *)v65 + 317) )
          {
            memset_0(v322, 0, 0xFE8u);
            if ( (unsigned int)VidGetPartitionPropertyEx(-1, 589831, 0, v322) && (v323[0] & 0x100) == 0 )
              wil::details::in1diag3::Throw_Win32(
                retaddr,
                (void *)0x314,
                (unsigned int)"onecore\\vm\\worker\\vidpartition\\vidpartitionmanager.cpp",
                (const char *)0x32,
                0xFE8u);
            v84 |= 0x20000000010000uLL;
          }
          v85 = v84 | 0x8000;
          if ( !*((_BYTE *)v65 + 144) )
            v85 = v84;
          v86 = v85 | 0x40000;
          if ( !*((_BYTE *)v65 + 145) )
            v86 = v85;
          v87 = v86 | 0x400000;
          if ( !*((_BYTE *)v65 + 208) )
            v87 = v86;
          v88 = *((_BYTE *)v65 + 209);
          Vml::VmReferencePtr<VmRepository,Vml::VmUserReferenceTraits>::~VmReferencePtr<VmRepository,Vml::VmUserReferenceTraits>(&v294);
          v66 = v87 | 0x200000;
          if ( !v88 )
            v66 = v87;
        }
        else
        {
          if ( *((_BYTE *)v300 + 160) || *((_BYTE *)v300 + 176) )
          {
            v209 = wil::verify_hresult<long>(3224829998LL);
            wil::details::in1diag3::Throw_HrMsg(
              retaddr,
              (void *)0x344,
              (unsigned int)"onecore\\vm\\worker\\vidpartition\\vidpartitionmanager.cpp",
              (const char *)v209,
              (int)"Physically backed VMs don't support fault clustering.",
              (const char *)v266);
          }
          if ( *((_BYTE *)v300 + 313) || *((_BYTE *)v300 + 314) || *((_BYTE *)v300 + 315) )
          {
            v208 = wil::verify_hresult<long>(3224829998LL);
            wil::details::in1diag3::Throw_HrMsg(
              retaddr,
              (void *)0x34D,
              (unsigned int)"onecore\\vm\\worker\\vidpartition\\vidpartitionmanager.cpp",
              (const char *)v208,
              (int)"Physically backed VMs don't support memory heat hints.",
              (const char *)v266);
          }
          if ( *((_BYTE *)v300 + 316) )
          {
            v202 = wil::verify_hresult<long>(3224829998LL);
            wil::details::in1diag3::Throw_HrMsg(
              retaddr,
              (void *)0x354,
              (unsigned int)"onecore\\vm\\worker\\vidpartition\\vidpartitionmanager.cpp",
              (const char *)v202,
              (int)"Physically backed VMs don't support EPF.",
              (const char *)v266);
          }
          if ( *((_BYTE *)v300 + 317) )
          {
            v203 = wil::verify_hresult<long>(3224829998LL);
            wil::details::in1diag3::Throw_HrMsg(
              retaddr,
              (void *)0x35B,
              (unsigned int)"onecore\\vm\\worker\\vidpartition\\vidpartitionmanager.cpp",
              (const char *)v203,
              (int)"Physically backed VMs don't support GPA pinning.",
              (const char *)v266);
          }
          if ( *((_BYTE *)v300 + 144) )
          {
            v204 = wil::verify_hresult<long>(3224829998LL);
            wil::details::in1diag3::Throw_HrMsg(
              retaddr,
              (void *)0x362,
              (unsigned int)"onecore\\vm\\worker\\vidpartition\\vidpartitionmanager.cpp",
              (const char *)v204,
              (int)"Physically backed VMs don't support private compression stores.",
              (const char *)v266);
          }
          if ( *((_BYTE *)v300 + 145) )
          {
            v205 = wil::verify_hresult<long>(3224829998LL);
            wil::details::in1diag3::Throw_HrMsg(
              retaddr,
              (void *)0x369,
              (unsigned int)"onecore\\vm\\worker\\vidpartition\\vidpartitionmanager.cpp",
              (const char *)v205,
              (int)"Physically backed VMs don't support deferred commit.",
              (const char *)v266);
          }
          if ( *((_BYTE *)v300 + 208) )
          {
            v206 = wil::verify_hresult<long>(3224829998LL);
            wil::details::in1diag3::Throw_HrMsg(
              retaddr,
              (void *)0x370,
              (unsigned int)"onecore\\vm\\worker\\vidpartition\\vidpartitionmanager.cpp",
              (const char *)v206,
              (int)"Physically backed VMs don't support pinning.",
              (const char *)v266);
          }
          v66 = v53 | 0x10000;
          if ( *((_BYTE *)v300 + 209) )
          {
            v207 = wil::verify_hresult<long>(3224829998LL);
            wil::details::in1diag3::Throw_HrMsg(
              retaddr,
              (void *)0x377,
              (unsigned int)"onecore\\vm\\worker\\vidpartition\\vidpartitionmanager.cpp",
              (const char *)v207,
              (int)"Physically backed VMs don't support direct mapped images.",
              (const char *)v266);
          }
        }
        v89 = v66 & 0xFFDFFFFFFFFEFFFFuLL;
        if ( (v29[16956] & 0xF) != 1 )
          v89 = v66;
        if ( (*(unsigned int (__fastcall **)(_QWORD))(**(_QWORD **)v16 + 64LL))(*(_QWORD *)v16) )
        {
          v89 |= 0x800u;
          if ( *(_BYTE *)((*(__int64 (__fastcall **)(_QWORD, void **))(**(_QWORD **)v16 + 408LL))(*(_QWORD *)v16, v296)
                        + 9) )
            v89 |= 0x20000000000uLL;
        }
        if ( v303 )
          v89 |= 1u;
        v289 = 64;
        v302 = 0;
        v268 = (struct IGuestCallback *)&v289;
        v267 = (struct IMemoryApertureCallback *)v324;
        LODWORD(v261) = 0;
        SystemTopology = VidGetSystemTopology(*((_QWORD *)v277 + 10), 0, &v302, 0);
        LODWORD(v294) = SystemTopology;
        v91 = (*(__int64 (__fastcall **)(struct INumaManager *))(*(_QWORD *)v275 + 8LL))(v275);
        if ( (*(unsigned int (__fastcall **)(__int64))(*(_QWORD *)v91 + 312LL))(v91) <= 1 )
        {
          if ( !*((_BYTE *)v277 + 114) )
          {
            HvCompatibilityVersion = 0;
            HIDWORD(v268) = 0;
            LODWORD(v267) = 4;
            v261 = (struct IVpOperations *)&HvCompatibilityVersion;
            if ( !(unsigned int)VidGetSystemInformation(*((_QWORD *)v277 + 10), 1, 0) )
              wil::details::in1diag3::Throw_GetLastError(
                retaddr,
                (void *)0x3BC,
                (unsigned int)"onecore\\vm\\worker\\vidpartition\\vidpartitionmanager.cpp",
                v92);
            if ( HvCompatibilityVersion == 3 )
            {
              phkResult = 0;
              v288 = 0;
              v291 = 0;
              Vml::VmRegistryKey::Open(
                &phkResult,
                HKEY_LOCAL_MACHINE,
                L"SOFTWARE\\Microsoft\\Windows NT\\CurrentVersion\\Virtualization",
                0x20019u);
              if ( !Vml::VmRegistryKey::QueryValue((Vml::VmRegistryKey *)&phkResult, L"NoAutomaticSmtEnablement", &v288) )
                v288 = v269 != 0;
              if ( Vml::VmRegistryKey::QueryValue((Vml::VmRegistryKey *)&phkResult, L"ForceSmtEnablement", &v291) )
              {
                v93 = v291;
              }
              else
              {
                v93 = 0;
                v291 = 0;
              }
              if ( v93 || SystemTopology && !v288 && *v279 > v302 )
              {
                v89 |= 0x800000000uLL;
                v280[0] = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)(*(_QWORD *)v16 + 16LL) + 8LL))(*(_QWORD *)v16 + 16LL);
                v295.m128i_i64[0] = (**(__int64 (__fastcall ***)(__int64))(*(_QWORD *)v16 + 16LL))(*(_QWORD *)v16 + 16LL);
                VmEventWrite<unsigned short const *,unsigned short const *>(
                  &MSVML_WP_WARN_SMT_AUTO_ENABLED,
                  1u,
                  (__int64)v280);
              }
              Vml::VmRegistryKey::Close((Vml::VmRegistryKey *)&phkResult);
            }
          }
        }
        else
        {
          v89 |= 0x20u;
        }
        v94 = v278;
        if ( (*(unsigned int (__fastcall **)(struct IVpOperations *))(*(_QWORD *)v278 + 160LL))(v278) )
        {
          if ( v290 >= 2 )
          {
            if ( (unsigned int)VmlIsDebugTraceEnabled(16416) )
              VmlDebugTrace(16416, L"Only generation 1 and generation 2 VMs support nested virtualization");
            v210 = wil::verify_hresult<long>(2147942450LL);
            LODWORD(v267) = v290;
            wil::details::in1diag3::Throw_HrMsg(
              retaddr,
              (void *)0x3F8,
              (unsigned int)"onecore\\vm\\worker\\vidpartition\\vidpartitionmanager.cpp",
              (const char *)v210,
              (int)"virtualSystemSubType = %u",
              (const char *)v267);
          }
          v89 |= 0x40u;
        }
        if ( (*(unsigned int (__fastcall **)(struct IVpOperations *))(*(_QWORD *)v278 + 184LL))(v278) )
        {
          if ( v290 != 1 )
          {
            if ( (unsigned int)VmlIsDebugTraceEnabled(16416) )
              VmlDebugTrace(16416, L"Only generation 2 VMs support hierarchical virtualization");
            v211 = wil::verify_hresult<long>(2147942450LL);
            LODWORD(v267) = v290;
            wil::details::in1diag3::Throw_HrMsg(
              retaddr,
              (void *)0x40B,
              (unsigned int)"onecore\\vm\\worker\\vidpartition\\vidpartitionmanager.cpp",
              (const char *)v211,
              (int)"virtualSystemSubType = %u",
              (const char *)v267);
          }
          v95 = v29[17098];
          v29[17098] = v95 + 1;
          v96 = v95;
          *(_DWORD *)gsl::span<_HV_PARTITION_PROPERTY_ASSOC,-1>::operator[](v325, v95) = 524545;
          v97 = (*(unsigned int (__fastcall **)(_QWORD))(**(_QWORD **)v16 + 384LL))(*(_QWORD *)v16);
          *(_QWORD *)(gsl::span<_HV_PARTITION_PROPERTY_ASSOC,-1>::operator[](v325, v96) + 8) = v97;
          v98 = v29[17098];
          v29[17098] = v98 + 1;
          v99 = v98;
          *(_DWORD *)gsl::span<_HV_PARTITION_PROPERTY_ASSOC,-1>::operator[](v325, v98) = 524546;
          v100 = (*(unsigned int (__fastcall **)(struct IVpOperations *))(*(_QWORD *)v94 + 192LL))(v94);
          *(_QWORD *)(gsl::span<_HV_PARTITION_PROPERTY_ASSOC,-1>::operator[](v325, v99) + 8) = v100;
          if ( (*(unsigned int (__fastcall **)(_QWORD))(**(_QWORD **)v16 + 392LL))(*(_QWORD *)v16) )
          {
            v101 = v29[17098];
            v29[17098] = v101 + 1;
            v102 = v101;
            *(_DWORD *)gsl::span<_HV_PARTITION_PROPERTY_ASSOC,-1>::operator[](v325, v101) = 131077;
            v103 = (*(int (__fastcall **)(_QWORD))(**(_QWORD **)v16 + 392LL))(*(_QWORD *)v16);
            *(_QWORD *)(gsl::span<_HV_PARTITION_PROPERTY_ASSOC,-1>::operator[](v325, v102) + 8) = v103;
          }
          v89 |= 0x10000000000000uLL;
          v104 = v29[17098];
          v29[17098] = v104 + 1;
          v105 = v104;
          *(_DWORD *)gsl::span<_HV_PARTITION_PROPERTY_ASSOC,-1>::operator[](v325, v104) = 327718;
          (*(void (__fastcall **)(_QWORD, __m128i *))(**(_QWORD **)v16 + 400LL))(*(_QWORD *)v16, &v295);
          v106 = v295.m128i_i64[0];
          *(_QWORD *)(gsl::span<_HV_PARTITION_PROPERTY_ASSOC,-1>::operator[](v325, v105) + 8) = v106;
        }
        v107 = v89 | 0x1000000000LL;
        if ( !(*(unsigned int (__fastcall **)(struct IVpOperations *))(*(_QWORD *)v94 + 200LL))(v94) )
          v107 = v89;
        v108 = v107 | 0x1000000000000LL;
        if ( !(*(unsigned int (__fastcall **)(struct IVpOperations *))(*(_QWORD *)v94 + 208LL))(v94) )
          v108 = v107;
        v109 = v108 | 0x2000000000LL;
        if ( !(*(unsigned int (__fastcall **)(struct IVpOperations *))(*(_QWORD *)v94 + 216LL))(v94) )
          v109 = v108;
        v110 = v109 | 0x4000000000LL;
        if ( !(*(unsigned int (__fastcall **)(struct IVpOperations *))(*(_QWORD *)v94 + 224LL))(v94) )
          v110 = v109;
        v111 = v110 | 0x8000000000LL;
        if ( !(*(unsigned int (__fastcall **)(struct IVpOperations *))(*(_QWORD *)v94 + 232LL))(v94) )
          v111 = v110;
        if ( (*(unsigned __int8 (__fastcall **)(struct INumaManager *))(*(_QWORD *)v275 + 72LL))(v275) )
        {
          if ( *v279 > 0xF0 )
          {
            v212 = wil::verify_hresult<long>(2147942450LL);
            LODWORD(v267) = v213;
            wil::details::in1diag3::Throw_HrMsg(
              retaddr,
              (void *)0x473,
              (unsigned int)"onecore\\vm\\worker\\vidpartition\\vidpartitionmanager.cpp",
              (const char *)v212,
              (int)"Maximum processor count limit exceeded for legacy apic mode(%d).",
              (const char *)v267);
          }
          v111 |= 0x40000000000uLL;
        }
        else if ( (*(unsigned __int8 (__fastcall **)(struct INumaManager *))(*(_QWORD *)v275 + 80LL))(v275) )
        {
          v111 |= 0x80000000000uLL;
          v112 = (*(__int64 (__fastcall **)(struct INumaManager *))(*(_QWORD *)v275 + 8LL))(v275);
          if ( (unsigned __int64)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v112 + 352LL))(v112) >= 0xF0 )
            v111 |= 0x400000000000uLL;
        }
        if ( (*(unsigned __int8 (__fastcall **)(struct INumaManager *))(*(_QWORD *)v275 + 88LL))(v275) )
        {
          v113 = v29[17098];
          v29[17098] = v113 + 1;
          v114 = v113;
          *(_DWORD *)gsl::span<_HV_PARTITION_PROPERTY_ASSOC,-1>::operator[](v325, v113) = 327716;
          *(_QWORD *)(gsl::span<_HV_PARTITION_PROPERTY_ASSOC,-1>::operator[](v325, v114) + 8) = 1;
        }
        if ( (*(unsigned int (__fastcall **)(struct IVpOperations *))(*(_QWORD *)v94 + 240LL))(v94) )
          v111 |= 0x100000000000uLL;
        if ( v292 >= 0x800 && v290 != 1 )
          v111 |= 0x80uLL;
        if ( v290 )
          v111 |= 0x100000000000000uLL;
        v115 = v300;
        if ( *((_BYTE *)v300 + 256) )
        {
          if ( v292 < (v269 ^ 1u) + 2048 || v290 != 1 )
          {
            if ( (unsigned int)VmlIsDebugTraceEnabled(16416) )
            {
              v218 = L"RS1";
              if ( !v269 )
                v218 = L"RS2";
              VmlDebugTrace(16416, L"Only generation 2 %s VMs support SGX", v218);
            }
            v219 = wil::verify_hresult<long>(2147778582LL);
            LODWORD(v268) = v290;
            LODWORD(v267) = v292;
            wil::details::in1diag3::Throw_HrMsg(
              retaddr,
              (void *)0x4C0,
              (unsigned int)"onecore\\vm\\worker\\vidpartition\\vidpartitionmanager.cpp",
              (const char *)v219,
              (int)"VM version %x (subtype %u) does not support SGX.",
              (const char *)v267,
              v268);
          }
          v111 |= 0x200uLL;
          v116 = *((_DWORD *)v300 + 68);
          if ( v116 )
          {
            v117 = v116 - 1;
            if ( v117 )
            {
              if ( v117 != 1 )
              {
                v214 = wil::verify_hresult<long>(2147942487LL);
                LODWORD(v267) = v215;
                wil::details::in1diag3::Throw_HrMsg(
                  retaddr,
                  (void *)0x4D6,
                  (unsigned int)"onecore\\vm\\worker\\vidpartition\\vidpartitionmanager.cpp",
                  (const char *)v214,
                  (int)"LaunchControlMode = %u",
                  (const char *)v267);
              }
              v111 |= 0x18000000uLL;
            }
            else
            {
              v111 |= 0x8000000uLL;
            }
          }
          if ( *((_QWORD *)v300 + 37) )
          {
            if ( *((_QWORD *)v300 + 37) != 64 )
            {
              NumaManager::GetRequestedNumaNodeMask((const struct Config::VmWorkerProcess::MemorySettings *)((char *)v300 + 280));
              v216 = wil::verify_hresult<long>(2147942487LL);
              LODWORD(v267) = v217;
              wil::details::in1diag3::Throw_HrMsg(
                retaddr,
                (void *)0x4E9,
                (unsigned int)"onecore\\vm\\worker\\vidpartition\\vidpartitionmanager.cpp",
                (const char *)v216,
                (int)"defaultString.size() = %u",
                (const char *)v267);
            }
            v118 = 0;
            while ( 1 )
            {
              HvCompatibilityVersion = v118;
              if ( v118 >= 4 )
                break;
              try
              {
                v119 = (wchar_t *)std::wstring::substr((char *)v115 + 280, v296, 16 * v118, 16);
                *(_QWORD *)&v29[2 * v118 + 16948] = _byteswap_uint64(std::stoull(v119));
                std::wstring::_Tidy_deallocate(v296);
                ++v118;
              }
              catch ( const std::exception *v286 )
              {
                if ( (unsigned int)VmlIsDebugTraceEnabled(16416) )
                {
                  v248 = (*(__int64 (__fastcall **)(const std::exception *))(*(_QWORD *)v286 + 8LL))(v286);
                  VmlDebugTrace(
                    16416,
                    L"Invalid SGX launch control default string (MSR %u): %S",
                    HvCompatibilityVersion,
                    v248);
                }
                v249 = wil::ResultFromCaughtException(v247);
                v250 = wil::verify_hresult<long>(v249);
                wil::details::in1diag3::Throw_Hr(
                  retaddr,
                  (void *)0x4FC,
                  (unsigned int)"onecore\\vm\\worker\\vidpartition\\vidpartitionmanager.cpp",
                  (const char *)v250,
                  v259);
              }
            }
            v111 |= 0x20000000uLL;
          }
        }
        phkResult = v16;
        v120 = (*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)v16 + 424LL))(*(_QWORD *)v16);
        v121 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v120 + 800LL))(v120);
        v122 = v111 | 0x800000000000LL;
        if ( !v121 )
          v122 = v111;
        v123 = v122 | 0x80000;
        if ( !*((_BYTE *)v115 + 192) )
          v123 = v122;
        v124 = (*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)v16 + 424LL))(*(_QWORD *)v16);
        if ( (*(unsigned __int8 (__fastcall **)(__int64))(*(_QWORD *)v124 + 480LL))(v124) )
        {
          v29[12] |= 0x180u;
          v127 = v29[12] | 0x600;
        }
        else
        {
          v29[12] ^= (v29[12]
                    ^ ((unsigned int)lambda_0242864c6572879e96253374616fb0b4_::operator()(v126, *((_QWORD *)v115 + 23)) << 7))
                   & 0x180;
          v127 = v29[12]
               ^ (v29[12]
                ^ ((unsigned int)lambda_0242864c6572879e96253374616fb0b4_::operator()(v128, *((_QWORD *)v115 + 25)) << 9))
               & 0x600;
        }
        v29[12] = v127;
        if ( (v127 & 0x600) == 0 && *((_QWORD *)v115 + 5) == 1 )
        {
          v129 = (*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)v16 + 48LL))(*(_QWORD *)v16);
          if ( (*(unsigned int (__fastcall **)(__int64))(*(_QWORD *)v129 + 392LL))(v129) )
            v29[12] |= 0x600u;
        }
        v130 = *((_QWORD *)v115 + 29);
        if ( v130 )
        {
          v131 = (const unsigned __int16 *)((char *)v115 + 216);
          if ( *((_QWORD *)v115 + 30) > 7u )
            v131 = *(const unsigned __int16 **)v131;
          v132 = StringCbCopyNW((unsigned __int16 *)v29 + 33924, v125, v131, 2 * v130);
          if ( v132 < 0 )
          {
            v220 = wil::verify_hresult<long>((unsigned int)v132);
            wil::details::in1diag3::Throw_HrMsg(
              retaddr,
              (void *)0x56E,
              (unsigned int)"onecore\\vm\\worker\\vidpartition\\vidpartitionmanager.cpp",
              (const char *)v220,
              (int)"Failed to copy specified hosting process name suffix into the IOCTL buffer",
              (const char *)v267);
          }
        }
        v133 = v282;
        v280[0] = v282;
        HvCompatibilityVersion = VidPartitionManager::GetHvCompatibilityVersion(v126, v292);
        *(_OWORD *)Src = 0;
        (*(void (__fastcall **)(__int64, void **))(*(_QWORD *)v133 + 104LL))(v133, Src);
        *(_OWORD *)v317 = 0;
        (*(void (__fastcall **)(__int64, void **))(*(_QWORD *)v133 + 112LL))(v133, v317);
        *(_OWORD *)v318 = 0;
        (*(void (__fastcall **)(__int64, void **))(*(_QWORD *)v133 + 120LL))(v133, v318);
        if ( (v29[16956] & 0xF) == 2 )
        {
          v134 = v284;
          v135 = (*(__int64 (__fastcall **)(struct IVirtualMachine *))(*(_QWORD *)v284 + 248LL))(v284);
          v136 = (*(__int64 (__fastcall **)(struct IVirtualMachine *))(*(_QWORD *)v134 + 256LL))(v134);
          v137 = v136;
          if ( v135 || v136 )
          {
            if ( !(*(unsigned __int8 (__fastcall **)(struct INumaManager *))(*(_QWORD *)v275 + 80LL))(v275) )
              wil::details::in1diag3::Throw_Hr(
                retaddr,
                (void *)0x589,
                (unsigned int)"onecore\\vm\\worker\\vidpartition\\vidpartitionmanager.cpp",
                (const char *)0x80070057LL,
                (int)v261);
            v123 |= 0x400000000000uLL;
            if ( v137 )
            {
              v29[16956] |= 0xC0u;
            }
            else if ( v135 )
            {
              v29[16956] &= ~0x80u;
              v29[16956] |= 0x40u;
            }
          }
        }
        v296[0] = v279;
        v138 = *v279;
        v29[10] = *v279;
        v139 = v270;
        v288 = v270;
        v291 = v270;
        v29[12] ^= (v29[12] ^ v270) & 0x7F;
        *((_QWORD *)v29 + 4) = v123;
        *v29 = HvCompatibilityVersion;
        *(_OWORD *)(v29 + 2) = *(_OWORD *)a11;
        *((_QWORD *)v29 + 3) = *((_QWORD *)a11 + 2);
        v140 = v281;
        memcpy_0(v29 + 46, (const void *)(v281 + 344), v138);
        memcpy_0(v29 + 558, Src[1], 8LL * v29[10]);
        if ( v317[0] )
          memcpy_0(v29 + 4654, v317[1], 16LL * v29[10]);
        if ( v318[0] )
        {
          memcpy_0(v29 + 12847, v318[1], 8LL * v29[10]);
          v141 = 1;
        }
        else
        {
          v141 = 0;
        }
        *((_BYTE *)v29 + 51384) = v141;
        memcpy_0(v29 + 13, (const void *)(v140 + 280), v29[12] & 0x7F);
        memcpy_0(v29 + 29, (const void *)(v140 + 2392), v29[12] & 0x7F);
        *((_OWORD *)v29 + 4236) = v64;
        v29[17099] = 68416;
        v142 = v29[17098];
        v29[17098] = v142 + 1;
        v143 = v142;
        *(_DWORD *)gsl::span<_HV_PARTITION_PROPERTY_ASSOC,-1>::operator[](v325, v142) = 65537;
        v144 = *(_QWORD *)a12;
        *(_QWORD *)(gsl::span<_HV_PARTITION_PROPERTY_ASSOC,-1>::operator[](v325, v143) + 8) = v144;
        v145 = v278;
        if ( (*(unsigned int (__fastcall **)(struct IVpOperations *))(*(_QWORD *)v278 + 168LL))(v278) )
        {
          v146 = v29[17098];
          v29[17098] = v146 + 1;
          v147 = v146;
          *(_DWORD *)gsl::span<_HV_PARTITION_PROPERTY_ASSOC,-1>::operator[](v325, v146) = 524289;
          v148 = (*(unsigned int (__fastcall **)(struct IVpOperations *))(*(_QWORD *)v145 + 176LL))(v145);
          *(_QWORD *)(gsl::span<_HV_PARTITION_PROPERTY_ASSOC,-1>::operator[](v325, v147) + 8) = v148;
          if ( (*(unsigned int (__fastcall **)(struct IVpOperations *))(*(_QWORD *)v278 + 184LL))(v278)
            && (*(unsigned int (__fastcall **)(struct IVpOperations *))(*(_QWORD *)v278 + 176LL))(v278) )
          {
            v29[16956] |= 0x20u;
          }
          else
          {
            v29[16956] |= 0x10u;
          }
        }
        v149 = v284;
        if ( (*(unsigned __int8 (__fastcall **)(struct IVirtualMachine *))(*(_QWORD *)v284 + 216LL))(v284)
          && (v29[16956] & 0xF) - 2 > 2 )
        {
          v300 = 0;
          (*(void (__fastcall **)(_QWORD, _QWORD, const struct Config::VmWorkerProcess::MemorySettings **))(**(_QWORD **)v16 + 288LL))(
            *(_QWORD *)v16,
            0,
            &v300);
          v150 = (((unsigned __int64)v300 + 511) >> 9) + 512;
          v151 = v29[17098];
          v29[17098] = v151 + 1;
          v152 = v151;
          *(_DWORD *)gsl::span<_HV_PARTITION_PROPERTY_ASSOC,-1>::operator[](v325, v151) = 327713;
          *(_QWORD *)(gsl::span<_HV_PARTITION_PROPERTY_ASSOC,-1>::operator[](v325, v152) + 8) = v150;
          v149 = v284;
        }
        v153 = (*(__int64 (__fastcall **)(struct IVirtualMachine *))(*(_QWORD *)v149 + 48LL))(v149);
        v154 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v153 + 240LL))(v153);
        v155 = v154;
        if ( v154 )
        {
          HvCompatibilityVersion = 0;
          v156 = (*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)v16 + 448LL))(*(_QWORD *)v16);
          v157 = (*(__int64 (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v156 + 88LL))(
                   v156,
                   &HvCompatibilityVersion);
          if ( v157 < 0 )
            wil::details::in1diag3::Throw_Hr(
              retaddr,
              (void *)0x618,
              (unsigned int)"onecore\\vm\\worker\\vidpartition\\vidpartitionmanager.cpp",
              (const char *)(unsigned int)v157,
              (int)v261);
          if ( HvCompatibilityVersion != 3 )
          {
            v158 = v29[17098];
            v29[17098] = v158 + 1;
            v159 = v158;
            *(_DWORD *)gsl::span<_HV_PARTITION_PROPERTY_ASSOC,-1>::operator[](v325, v158) = 393222;
            *(_QWORD *)(gsl::span<_HV_PARTITION_PROPERTY_ASSOC,-1>::operator[](v325, v159) + 8) = v155;
          }
        }
        if ( a7 != (void *)-1LL )
          *((_QWORD *)v29 + 8547) = a7;
        *((_QWORD *)v29 + 8548) = a8;
        v160 = v277;
        *((_QWORD *)v277 + 12) = v123;
        v29[17100] = v293 - 68416;
        v161 = (**(__int64 (__fastcall ***)(__int64))(*(_QWORD *)v16 + 16LL))(*(_QWORD *)v16 + 16LL);
        v162 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)(*(_QWORD *)v16 + 16LL) + 8LL))(*(_QWORD *)v16 + 16LL);
        Partition = VidCreatePartition(v162, v161, v29);
        v164 = (void **)((char *)v160 + 56);
        *((_QWORD *)v160 + 7) = Partition;
        if ( Partition == -1 )
        {
          LastError = GetLastError();
          v224 = LastError;
          if ( (LastError & 0x1FFF0000) != 0 )
          {
            v225 = LastError;
            if ( LastError > 0 )
              v225 = LastError & 0xFFFFFFF | 0x80000000;
          }
          else if ( LastError > 0 )
          {
            v225 = (unsigned __int16)LastError | 0x80070000;
          }
          else
          {
            v225 = LastError;
          }
          if ( LastError == -1070264320 )
          {
            VmEventWriteAndReport(&MSVML_WP_INIT_HYPERVISOR_NOT_RUNNING_ERROR, 5u, v222, v223);
          }
          else
          {
            if ( (unsigned int)VmlIsDebugTraceEnabled(16416) )
              VmlDebugTrace(16416, L"Failed to create partition. GetLastError=%d .\n", v224);
            _snwprintf_s<16>(v296, 16, L"%%%%%u", v225 & 0xEFFFFFFF);
            _snwprintf_s<16>(v325, 16, L"0x%08X", v225 & 0xEFFFFFFF);
            VmEventWriteAndReport<unsigned short (&)[16],unsigned short (&)[16]>(
              (struct _EVENT_DESCRIPTOR *)&MSVML_WP_INIT_CREATE_PARTITION_ERROR,
              (__int64)v296,
              (unsigned __int16 *)v325);
          }
          v226 = wil::verify_hresult<long>(v225);
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x652,
            (unsigned int)"onecore\\vm\\worker\\vidpartition\\vidpartitionmanager.cpp",
            (const char *)v226,
            (int)v261);
        }
        if ( !(unsigned int)VidAttachPartition(Partition) )
          wil::details::in1diag3::Throw_GetLastError(
            retaddr,
            (void *)0x655,
            (unsigned int)"onecore\\vm\\worker\\vidpartition\\vidpartitionmanager.cpp",
            v165);
        v300 = (VidPartitionManager *)((char *)v160 + 56);
        if ( (*(unsigned int (__fastcall **)(_QWORD))(**(_QWORD **)v16 + 64LL))(*(_QWORD *)v16) )
        {
          if ( *((_QWORD *)v274 + 4) > 2u )
          {
            if ( *((_QWORD *)v274 + 8) )
            {
              memset_0(v322, 0, 0xFE8u);
              LODWORD(v261) = 4072;
              if ( (unsigned int)VidGetPartitionPropertyEx(*v164, 589840, 0, v322) )
              {
                v166 = (const char *)LOBYTE(v322[0]);
                v167 = (unsigned __int8 *)*((_QWORD *)v274 + 8);
                v168 = *v167;
                if ( LOBYTE(v322[0]) != v168 )
                {
                  v227 = VmWorkerTrace::Provider();
                  v228 = (int)v227;
                  if ( *(_DWORD *)v227 > 2u && (unsigned __int8)tlgKeywordOn(v227, 0) )
                  {
                    v274 = (const struct _VMM_PARTITION_PROPERTIES *)v168;
                    v295.m128i_i64[0] = (__int64)v166;
                    v229 = Vml::VmReferencePtr<IVirtualMachine,Vml::VmWeakReferenceTraits>::operator->(v16);
                    v280[0] = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)(v229 + 16) + 16LL))(v229 + 16);
                    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>>(
                      v228,
                      (unsigned int)&word_140360F26,
                      v230,
                      v231,
                      (__int64)v280,
                      (__int64)&v295,
                      (__int64)&v274);
                  }
                  v232 = wil::verify_hresult<long>(2147549183LL);
                  wil::details::in1diag3::Throw_HrMsg(
                    retaddr,
                    (void *)0x67C,
                    (unsigned int)"onecore\\vm\\worker\\vidpartition\\vidpartitionmanager.cpp",
                    (const char *)v232,
                    (int)"Processor features bank count mismatch Hypervisor visible bank count=%zu, Worker visible bank count=%zu",
                    v166,
                    v168);
                }
                for ( i = 2; i < v168; ++i )
                {
                  v170 = (const struct _VMM_PARTITION_PROPERTIES *)v323[i];
                  v171 = ~*(_QWORD *)&v167[8 * i + 8];
                  if ( ((unsigned __int64)v170 & v171) != v171 )
                  {
                    v233 = VmWorkerTrace::Provider();
                    v234 = (int)v233;
                    if ( *(_DWORD *)v233 > 2u )
                    {
                      if ( (unsigned __int8)tlgKeywordOn(v233, 0) )
                      {
                        v274 = v170;
                        v295.m128i_i64[0] = v171;
                        v280[0] = i;
                        v235 = Vml::VmReferencePtr<IVirtualMachine,Vml::VmWeakReferenceTraits>::operator->(v16);
                        v281 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)(v235 + 16) + 16LL))(v235 + 16);
                        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>>(
                          v234,
                          (unsigned int)&unk_140360D28,
                          v236,
                          v237,
                          (__int64)&v281,
                          (__int64)v280,
                          (__int64)&v295,
                          (__int64)&v274);
                      }
                    }
                    v238 = wil::verify_hresult<long>(2147549183LL);
                    wil::details::in1diag3::Throw_HrMsg(
                      retaddr,
                      (void *)0x69F,
                      (unsigned int)"onecore\\vm\\worker\\vidpartition\\vidpartitionmanager.cpp",
                      (const char *)v238,
                      (int)"Processor features bank %zu: expected enabled features are not a subset of actual enabled fea"
                           "tures. expected enabled=0x%llx, actual enabled=0x%llx",
                      (const char *)i,
                      v171,
                      v170);
                  }
                }
                v139 = v288;
                v160 = v277;
              }
            }
          }
        }
        VidPartitionManager::FreezeTime(v160);
        try
        {
          v172 = (**(__int64 (__fastcall ***)(__int64))(*(_QWORD *)v16 + 16LL))(*(_QWORD *)v16 + 16LL);
          v173 = VidSetPartitionFriendlyName(*v164, v172);
          v175 = retaddr;
          if ( !v173 )
            wil::details::in1diag3::Throw_GetLastError(
              retaddr,
              (void *)0x6AF,
              (unsigned int)"onecore\\vm\\worker\\vidpartition\\vidpartitionmanager.cpp",
              v174);
        }
        catch ( ... )
        {
          v254 = wil::ResultFromCaughtException(v175);
          v255 = v254;
          LODWORD(v255) = v254 & 0xEFFFFFFF;
          _snwprintf_s<16>(v325, 16, L"%%%%%u", v255);
          _snwprintf_s<16>(v310, 16, L"0x%08X", v254 & 0xEFFFFFFF);
          v256 = v283;
          v257 = Vml::VmReferencePtr<IVirtualMachine,Vml::VmWeakReferenceTraits>::operator->((char *)v283 + 104);
          v271 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)(v257 + 16) + 8LL))(v257 + 16);
          v258 = Vml::VmReferencePtr<IVirtualMachine,Vml::VmWeakReferenceTraits>::operator->((char *)v256 + 104);
          v276 = (struct INumaManager *)(**(__int64 (__fastcall ***)(__int64))(v258 + 16))(v258 + 16);
          VmEventWriteAndReport<unsigned short const *,unsigned short const *,unsigned short (&)[16],unsigned short (&)[16]>(
            (struct _EVENT_DESCRIPTOR *)&MSVML_WP_SET_PARTITION_PROP_ERROR,
            5u,
            (__int64)&v276,
            (__int64)&v271,
            (__int64)v325,
            (__int64)v310);
          throw;
        }
        v176 = v303;
        if ( v303 )
        {
          v177 = VidSetPartitionProperty(*v164, 262147, v303);
          try
          {
            wil::details::in1diag3::Throw_IfWin32BoolFalseMsg(
              retaddr,
              (void *)0x6D1,
              (unsigned int)"onecore\\vm\\worker\\vidpartition\\vidpartitionmanager.cpp",
              (const char *)v177,
              (int)"channelId = %I64u",
              v176);
          }
          catch ( ... )
          {
            v251 = wil::ResultFromCaughtException(v178);
            v252 = v251;
            LODWORD(v252) = v251 & 0xEFFFFFFF;
            _snwprintf_s<16>(v310, 16, L"%%%%%u", v252);
            _snwprintf_s<16>(v325, 16, L"0x%08X", v251 & 0xEFFFFFFF);
            v253 = v283;
            v274 = (const struct _VMM_PARTITION_PROPERTIES *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)(*((_QWORD *)v283 + 13) + 16LL)
                                                                                                + 8LL))(*((_QWORD *)v283 + 13) + 16LL);
            v295.m128i_i64[0] = (**(__int64 (__fastcall ***)(__int64))(*((_QWORD *)v253 + 13) + 16LL))(*((_QWORD *)v253 + 13) + 16LL);
            VmEventWrite<unsigned short const *,unsigned short const *,unsigned short (&)[16],unsigned short (&)[16]>(
              &MSVML_WP_SET_DEBUG_CHANNEL_ERROR,
              5u,
              (__int64)&v274,
              (__int64)v310,
              (__int64)v325);
            v272 = v273;
            v282 = v280[0];
            v16 = phkResult;
            v164 = (void **)v300;
            v279 = (unsigned int *)v296[0];
            v160 = v283;
            v275 = v276;
            v179 = v271;
            v139 = v291;
            goto LABEL_260;
          }
        }
        v179 = (__int64)v278;
LABEL_260:
        Instance = VidNotificationDispatcher::CreateInstance((struct VidNotificationDispatcher **)v160 + 8);
        if ( Instance < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x6E4,
            (unsigned int)"onecore\\vm\\worker\\vidpartition\\vidpartitionmanager.cpp",
            (const char *)(unsigned int)Instance,
            (int)v261);
        v262 = (struct IVpOperations *)v179;
        v181 = v275;
        v182 = VidNotificationDispatcher::Initialize(
                 *((VidNotificationDispatcher **)v160 + 8),
                 v160,
                 v275,
                 *(struct IVirtualMachine **)v16,
                 v262,
                 a5,
                 v285);
        if ( v182 < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x6EB,
            (unsigned int)"onecore\\vm\\worker\\vidpartition\\vidpartitionmanager.cpp",
            (const char *)(unsigned int)v182,
            v263);
        if ( !(unsigned int)Vml::VmCompletionHandlerIo::AssociateHandle(
                              (VidPartitionManager *)((char *)v160 + 120),
                              *v164) )
          wil::details::in1diag3::Throw_GetLastError(
            retaddr,
            (void *)0x6ED,
            (unsigned int)"onecore\\vm\\worker\\vidpartition\\vidpartitionmanager.cpp",
            v183);
        memset_0(v322, 0, 0x100u);
        if ( (_DWORD)v294 )
        {
          v184 = 0;
          v185 = v270;
          if ( v270 )
          {
            v186 = v281;
            do
            {
              v187 = *(unsigned __int8 *)(v186 + v184 + 280);
              v322[v187] += *(_DWORD *)(v186 + 4LL * v184++ + 16);
            }
            while ( v184 < v185 );
          }
          for ( j = 0; j < v289; ++j )
          {
            if ( *(_DWORD *)&v324[24 * j + 4] < v322[j] )
            {
              v271 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)(*(_QWORD *)v16 + 16LL) + 8LL))(*(_QWORD *)v16 + 16LL);
              v276 = (struct INumaManager *)(**(__int64 (__fastcall ***)(__int64))(*(_QWORD *)v16 + 16LL))(*(_QWORD *)v16 + 16LL);
              VmEventWrite<unsigned short const *,unsigned short const *>(
                &MSVML_MM_NUMA_RESOURCES_NOT_ALIGNED_WARNING,
                1u,
                (__int64)&v271);
              break;
            }
          }
        }
        if ( v272 && v270 > 1u )
        {
          *(_OWORD *)v296 = 0;
          *(_QWORD *)&v297 = 0;
          v189 = v139 * v139;
          if ( v189 )
            std::vector<unsigned char const *>::_Resize_reallocate<std::_Value_init_tag>(v296, v189);
          v288 = 0;
          v190 = v272;
          if ( v272 == 2 )
            goto LABEL_279;
          while ( 1 )
          {
            LODWORD(v294) = gsl::narrow<unsigned int,unsigned __int64,0>(((char *)v296[1] - (char *)v296[0]) & 0xFFFFFFFFFFFFFFF8uLL);
            v264 = (int)v296[0];
            if ( (unsigned int)VidQueryPartitionInformation(*v164, 0, &v288, 4) )
              break;
            if ( v190 != 3 )
            {
              v239 = GetLastError();
              v240 = v239;
              if ( v239 > 0 )
                v240 = (unsigned __int16)v239 | 0x80070000;
              v241 = VmWorkerTrace::Provider();
              v242 = (int)v241;
              if ( *(_DWORD *)v241 > 2u && (unsigned __int8)tlgKeywordOn(v241, 0) )
              {
                v273 = v240;
                v269 = v190;
                v243 = Vml::VmReferencePtr<IVirtualMachine,Vml::VmWeakReferenceTraits>::operator->(v16);
                v271 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)(v243 + 16) + 16LL))(v243 + 16);
                _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByVal<1>,_tlgWrapperByVal<4>>(
                  v242,
                  (unsigned int)&byte_140360F87,
                  v244,
                  v245,
                  (__int64)&v271,
                  (__int64)&v269,
                  (__int64)&v273);
              }
              v246 = wil::verify_hresult<long>(v240);
              wil::details::in1diag3::Throw_Hr(
                retaddr,
                (void *)0x740,
                (unsigned int)"onecore\\vm\\worker\\vidpartition\\vidpartitionmanager.cpp",
                (const char *)v246,
                v264);
            }
            v190 = 2;
            v288 = 0;
LABEL_279:
            v288 = 1;
          }
          v191 = VmWorkerTrace::Provider();
          v192 = (int)v191;
          if ( *(_DWORD *)v191 > 4u && (unsigned __int8)tlgKeywordOn(v191, 4096) )
          {
            v269 = v190;
            v325[0] = (char *)v296[0];
            LOWORD(v325[1]) = ((char *)v296[1] - (char *)v296[0]) >> 3;
            v271 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)(*(_QWORD *)v16 + 16LL) + 16LL))(*(_QWORD *)v16 + 16LL);
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperArray<8>,_tlgWrapperByVal<1>>(
              v192,
              (__int64)&v271,
              (__int64)v325,
              (__int64)&v269);
          }
          (*(void (__fastcall **)(__int64, void **))(*(_QWORD *)v282 + 440LL))(v282, v296);
          std::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<unsigned int const,std::shared_ptr<MigrationTransferEndpointTarget>>>>>>>::~_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<unsigned int const,std::shared_ptr<MigrationTransferEndpointTarget>>>>>>>(v296);
        }
        v193 = operator new(0x90u);
        v271 = (__int64)v193;
        memset_0(v193, 0, 0x90u);
        v194 = WorkerStatsPanel::WorkerStatsPanel((WorkerStatsPanel *)v193);
        *((_QWORD *)v160 + 9) = v194;
        v195 = *v279;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)(*(_QWORD *)v16 + 16LL) + 16LL))(*(_QWORD *)v16 + 16LL);
        (**(void (__fastcall ***)(__int64))(*(_QWORD *)v16 + 16LL))(*(_QWORD *)v16 + 16LL);
        v198 = WorkerStatsPanel::Initialize(v194, *v164, v196, v197, v195);
        if ( v198 < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x75D,
            (unsigned int)"onecore\\vm\\worker\\vidpartition\\vidpartitionmanager.cpp",
            (const char *)(unsigned int)v198,
            v265);
        (*(void (__fastcall **)(struct INumaManager *))(*(_QWORD *)v181 + 120LL))(v181);
        std::vector<_VID_VSM_MBP_PERMISSIONS>::_Tidy(&v319);
        std::vector<_VID_VSM_MBP_PERMISSIONS>::_Tidy(&v306);
        std::vector<_VID_VSM_MBP_PERMISSIONS>::_Tidy(&v304);
        std::vector<_VID_VSM_MBP_PERMISSIONS>::_Tidy(&v308);
        Vml::VmReferencePtr<VmRepository,Vml::VmUserReferenceTraits>::~VmReferencePtr<VmRepository,Vml::VmUserReferenceTraits>(&v299);
        return 0;
      }
      gsl::details::terminate(v30);
    }
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0x146,
      (unsigned int)"onecore\\vm\\worker\\vidpartition\\vidpartitionmanager.cpp",
      v18);
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0x763,
                           (unsigned int)"onecore\\vm\\worker\\vidpartition\\vidpartitionmanager.cpp",
                           v199);
  }
  return result;
}

```

## disassembly

```asm
0x1402765ec  push    rbx
0x1402765ee  push    rsi
0x1402765ef  push    rdi
0x1402765f0  push    r12
0x1402765f2  push    r13
0x1402765f4  push    r14
0x1402765f6  push    r15
0x1402765f8  mov     eax, 1880h
0x1402765fd  call    _alloca_probe
0x140276602  sub     rsp, rax
0x140276605  movaps  [rsp+18B8h+var_48], xmm6
0x14027660d  mov     rax, cs:__security_cookie
0x140276614  xor     rax, rsp
0x140276617  mov     [rsp+18B8h+var_58], rax
0x14027661f  mov     r15, r9
0x140276622  mov     [rsp+18B8h+var_1840], r9
0x140276627  mov     rbx, r8
0x14027662a  mov     [rsp+18B8h+var_1858], rbx
0x14027662f  mov     [rsp+18B8h+var_1808], rdx
0x140276637  mov     rsi, rcx
0x14027663a  mov     [rsp+18B8h+var_1848], rcx
0x14027663f  mov     [rsp+18B8h+var_1810], rcx
0x140276647  mov     [rsp+18B8h+var_1850], rbx
0x14027664c  mov     [rsp+18B8h+var_1870], r9
0x140276651  mov     rcx, [rsp+18B8h+arg_28]
0x140276659  mov     [rsp+18B8h+var_1800], rcx
0x140276661  mov     r12, [rsp+18B8h+arg_48]
0x140276669  mov     [rsp+18B8h+var_1780], r12
0x140276671  mov     rdi, [rsp+18B8h+arg_60]
0x140276679  mov     [rsp+18B8h+var_1860], rdi
0x14027667e  lea     r13, [rsi+68h]
0x140276682  mov     rcx, r13
0x140276685  call    ?Reset@?$VmReferencePtr@UIVirtualMachine@@VVmWeakReferenceTraits@Vml@@@Vml@@QEAAXPEAUIVirtualMachine@@@Z; Vml::VmReferencePtr<IVirtualMachine,Vml::VmWeakReferenceTraits>::Reset(IVirtualMachine *)
0x14027668a  mov     rax, [r15]
0x14027668d  mov     rcx, r15
0x140276690  mov     rax, [rax+0B8h]
0x140276697  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14027669c  xor     r14d, r14d
0x14027669f  test    eax, eax
0x1402766a1  setnz   al
0x1402766a4  mov     [rsi+72h], al
0x1402766a7  call    cs:__imp_VidOpenStatisticsHandle
0x1402766ae  nop     dword ptr [rax+rax+00h]
0x1402766b3  mov     [rsi+50h], rax
0x1402766b7  dec     rax
0x1402766ba  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1402766be  ja      loc_140279170
0x1402766c4  mov     rcx, [r13+0]
0x1402766c8  mov     rax, [rcx]
0x1402766cb  mov     rax, [rax+30h]
0x1402766cf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1402766d4  mov     rdx, rax
0x1402766d7  mov     rcx, [rax]
0x1402766da  mov     rax, [rcx+98h]
0x1402766e1  mov     rcx, rdx
0x1402766e4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1402766e9  lea     rcx, [rsi+58h]
0x1402766ed  mov     [rsp+18B8h+var_1838], rcx
0x1402766f5  mov     [rcx], eax
0x1402766f7  call    _lambda_997682190daf7855ab97ce0562d05e09___operator__
0x1402766fc  movzx   r12d, al
0x140276700  mov     byte ptr [rsp+18B8h+var_1878], r12b
0x140276705  mov     [rsp+18B8h+var_1768], r14
0x14027670d  mov     dword ptr [rsp+18B8h+var_17DC], r14d
0x140276715  mov     dword ptr [rsp+18B8h+var_17E4], r14d
0x14027671d  mov     [rsp+18B8h+var_1788], r14
0x140276725  mov     rcx, [r13+0]
0x140276729  mov     rdx, [rcx]
0x14027672c  mov     rax, [rdx+38h]
0x140276730  lea     rdx, [rsp+18B8h+var_1788]
0x140276738  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14027673d  nop
0x14027673e  xorps   xmm0, xmm0
0x140276741  movups  xmmword ptr [rsp+18B8h+var_78], xmm0
0x140276749  xor     r8d, r8d
0x14027674c  mov     rdx, [rsp+18B8h+var_1788]
0x140276754  lea     rcx, [rsp+18B8h+var_78]
0x14027675c  call    ??0VmRepositoryAutoLock@@QEAA@PEAVVmRepository@@W4VmRepositoryLockFlags@@@Z; VmRepositoryAutoLock::VmRepositoryAutoLock(VmRepository *,VmRepositoryLockFlags)
0x140276761  nop
0x140276762  mov     r9d, dword ptr [rsp+18B8h+var_78+8]; char *
0x14027676a  mov     rcx, [rsp+18B8h]; this
0x140276772  test    r9d, r9d
0x140276775  js      loc_140278890
0x14027677b  mov     rcx, [rsp+18B8h+var_1788]
0x140276783  mov     rax, [rcx]
0x140276786  lea     rdx, [rsp+18B8h+var_17DC]
0x14027678e  mov     rax, [rax+120h]
0x140276795  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14027679a  mov     rcx, [rsp+18B8h]; this
0x1402767a2  test    eax, eax
0x1402767a4  js      loc_1402788A1
0x1402767aa  mov     rcx, [rsp+18B8h+var_1788]
0x1402767b2  mov     rax, [rcx]
0x1402767b5  lea     r8, [rsp+18B8h+var_1768]
0x1402767bd  lea     rdx, ?VIRTUAL_MACHINE_DEBUG_CHANNELID@@3QBGB; "/configuration/global_settings/debug/ch"...
0x1402767c4  mov     rax, [rax+70h]
0x1402767c8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1402767cd  mov     rcx, [rsp+18B8h+var_1788]
0x1402767d5  mov     rax, [rcx]
0x1402767d8  lea     rdx, [rsp+18B8h+var_17E4]
0x1402767e0  mov     rax, [rax+140h]
0x1402767e7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1402767ec  xorps   xmm0, xmm0
0x1402767ef  movdqa  [rsp+18B8h+var_1718], xmm0
0x1402767f8  mov     [rsp+18B8h+var_1708], r14
0x140276800  mov     [rsp+18B8h+var_1700], r14
0x140276808  mov     qword ptr [rsp+18B8h+var_16F8], r14
0x140276810  mov     qword ptr [rsp+18B8h+var_16F8+8], r14
0x140276818  movdqa  [rsp+18B8h+var_16E8], xmm0
0x140276821  mov     [rsp+18B8h+var_16D8], r14
0x140276829  mov     [rsp+18B8h+var_16D0], r14
0x140276831  mov     [rsp+18B8h+var_16C8], r14d
0x140276839  lea     r8, [rsp+18B8h+var_1718]
0x140276841  lea     rdx, [rsp+18B8h+var_1788]
0x140276849  lea     rcx, [rsp+18B8h+var_17B8]
0x140276851  call    ??$FromRepository@AEBV?$VmReferencePtr@VVmRepository@@VVmUserReferenceTraits@Vml@@@Vml@@UTopologySettings@VmWorkerProcess@Config@@$$V@Marshal@@YA?AU?$pair@_NV?$vector@U?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@W4UnmarshalError@Marshal@@@std@@V?$allocator@U?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@W4UnmarshalError@Marshal@@@std@@@2@@std@@@std@@AEBV?$VmReferencePtr@VVmRepository@@VVmUserReferenceTraits@Vml@@@Vml@@PEAUTopologySettings@VmWorkerProcess@Config@@W4UnmarshalFlags@0@@Z; Marshal::FromRepository<Vml::VmReferencePtr<VmRepository,Vml::VmUserReferenceTraits> const &,Config::VmWorkerProcess::TopologySettings,>(Vml::VmReferencePtr<VmRepository,Vml::VmUserReferenceTraits> const &,Config::VmWorkerProcess::TopologySettings *,Marshal::UnmarshalFlags)
0x140276856  nop
0x140276857  mov     rcx, [rsp+18B8h]; this
0x14027685f  cmp     [rax], r14b
0x140276862  jz      loc_1402788B6
0x140276868  lea     rcx, [rsp+18B8h+var_17B8+8]
0x140276870  call    ?_Tidy@?$vector@U?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@W4UnmarshalError@Marshal@@@std@@V?$allocator@U?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@W4UnmarshalError@Marshal@@@std@@@2@@std@@AEAAXXZ; std::vector<std::pair<std::wstring,Marshal::UnmarshalError>>::_Tidy(void)
0x140276875  mov     edx, dword ptr [rsp+18B8h+var_16D8]
0x14027687c  mov     [rsp+18B8h+var_1868], edx
0x140276880  mov     [rsp+18B8h+var_1864], edx
0x140276884  mov     rcx, [rsp+18B8h]; this
0x14027688c  cmp     edx, 3
0x14027688f  ja      loc_1402788CE
0x140276895  mov     eax, dword ptr [rsp+18B8h+var_17DC]
0x14027689c  test    edx, edx
0x14027689e  jz      short loc_1402768B5
0x1402768a0  cmp     eax, 903h
0x1402768a5  jb      short loc_1402768B1
0x1402768a7  cmp     dword ptr [rsp+18B8h+var_17E4], 1
0x1402768af  jz      short loc_1402768B5
0x1402768b1  mov     cl, 1
0x1402768b3  jmp     short loc_1402768B8
0x1402768b5  mov     cl, r14b
0x1402768b8  mov     r10, [rsp+18B8h]
0x1402768c0  test    cl, cl
0x1402768c2  jnz     loc_1402788E5
0x1402768c8  test    r12b, r12b
0x1402768cb  jnz     short loc_1402768EE
0x1402768cd  cmp     edx, 3
0x1402768d0  jnz     short loc_1402768DB
0x1402768d2  cmp     eax, 0B00h
0x1402768d7  mov     al, 1
0x1402768d9  jb      short loc_1402768DE
0x1402768db  mov     al, r14b
0x1402768de  mov     rcx, [rsp+18B8h]; this
0x1402768e6  test    al, al
0x1402768e8  jnz     loc_1402788FF
0x1402768ee  lea     rcx, [rsp+18B8h+var_78]; this
0x1402768f6  call    ??1VmRepositoryAutoLock@@QEAA@XZ; VmRepositoryAutoLock::~VmRepositoryAutoLock(void)
0x1402768fb  mov     rax, [rbx]
0x1402768fe  mov     rcx, rbx
0x140276901  mov     rax, [rax+8]
0x140276905  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14027690a  mov     rcx, rax
0x14027690d  mov     [rsp+18B8h+var_1818], rax
0x140276915  mov     rax, [rax]
0x140276918  mov     rax, [rax+58h]
0x14027691c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140276921  mov     [rsp+18B8h+var_1820], rax
0x140276929  mov     al, [rax+110h]
0x14027692f  mov     byte ptr [rsp+18B8h+var_1878+1], al
0x140276933  mov     [rsi+5Ch], al
0x140276936  xorps   xmm1, xmm1
0x140276939  movdqu  [rsp+18B8h+var_1730], xmm1
0x140276942  mov     [rsp+18B8h+var_1720], r14
0x14027694a  movdqu  [rsp+18B8h+var_1760], xmm1
0x140276953  mov     [rsp+18B8h+var_1750], r14
0x14027695b  mov     dl, 1
0x14027695d  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_L1VH_VMMFeatures@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_L1VH_VMMFeatures@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_L1VH_VMMFeatures> `wil::Feature<__WilFeatureTraits_Feature_L1VH_VMMFeatures>::GetImpl(void)'::`2'::impl
0x140276964  call    ?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_L1VH_VMMFeatures@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_L1VH_VMMFeatures>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)
0x140276969  cmp     [rsi+72h], r14b
0x14027696d  jz      short loc_14027699C
0x14027696f  lea     rdx, [rdi+10h]
0x140276973  cmp     [rdx], r14w
0x140276977  jz      short loc_140276986
0x140276979  lea     rcx, [rsp+18B8h+var_1760]
0x140276981  call    ?Initialize@?$HvPartitionPropertyPayload@U_HV_PARTITION_PROPERTY_ASSIGNABLE_SYNTHETIC_PROCESSOR_FEATURES@@@@QEAAXAEBU_HV_PARTITION_PROPERTY_ASSIGNABLE_SYNTHETIC_PROCESSOR_FEATURES@@@Z; HvPartitionPropertyPayload<_HV_PARTITION_PROPERTY_ASSIGNABLE_SYNTHETIC_PROCESSOR_FEATURES>::Initialize(_HV_PARTITION_PROPERTY_ASSIGNABLE_SYNTHETIC_PROCESSOR_FEATURES const &)
0x140276986  cmp     [rdi], r14w
0x14027698a  jz      short loc_14027699C
0x14027698c  mov     rdx, rdi
0x14027698f  lea     rcx, [rsp+18B8h+var_1730]
0x140276997  call    ?Initialize@?$HvPartitionPropertyPayload@U_HV_PARTITION_PROPERTY_ASSIGNABLE_SYNTHETIC_PROCESSOR_FEATURES@@@@QEAAXAEBU_HV_PARTITION_PROPERTY_ASSIGNABLE_SYNTHETIC_PROCESSOR_FEATURES@@@Z; HvPartitionPropertyPayload<_HV_PARTITION_PROPERTY_ASSIGNABLE_SYNTHETIC_PROCESSOR_FEATURES>::Initialize(_HV_PARTITION_PROPERTY_ASSIGNABLE_SYNTHETIC_PROCESSOR_FEATURES const &)
0x14027699c  xorps   xmm1, xmm1
0x14027699f  movdqu  [rsp+18B8h+var_1748], xmm1
0x1402769a8  mov     [rsp+18B8h+var_1738], r14
0x1402769b0  mov     r8, [rdi+20h]
0x1402769b4  test    r8, r8
0x1402769b7  jz      short loc_1402769D7
0x1402769b9  mov     rdx, [rdi+40h]
0x1402769bd  test    rdx, rdx
0x1402769c0  jz      short loc_1402769D7
0x1402769c2  lea     r8, ds:8[r8*8]
0x1402769ca  lea     rcx, [rsp+18B8h+var_1748]
0x1402769d2  call    ?InitializeFromBuffer@?$HvPartitionPropertyPayload@U_HV_PARTITION_PROPERTY_PROCESSOR_FEATURES_EX@@@@QEAAXPEBU_HV_PARTITION_PROPERTY_PROCESSOR_FEATURES_EX@@_K@Z; HvPartitionPropertyPayload<_HV_PARTITION_PROPERTY_PROCESSOR_FEATURES_EX>::InitializeFromBuffer(_HV_PARTITION_PROPERTY_PROCESSOR_FEATURES_EX const *,unsigned __int64)
0x1402769d7  xorps   xmm0, xmm0
0x1402769da  xor     eax, eax
0x1402769dc  movups  [rsp+18B8h+var_1698], xmm0
0x1402769e4  mov     [rsp+18B8h+var_1688], rax
0x1402769ec  mov     rcx, qword ptr [rsp+18B8h+var_1748+8]
0x1402769f4  sub     rcx, qword ptr [rsp+18B8h+var_1748]
0x1402769fc  sub     rcx, qword ptr [rsp+18B8h+var_1760]
0x140276a04  sub     rcx, qword ptr [rsp+18B8h+var_1730]
0x140276a0c  add     rcx, qword ptr [rsp+18B8h+var_1760+8]
0x140276a14  mov     rdx, qword ptr [rsp+18B8h+var_1730+8]
0x140276a1c  add     rdx, 10C60h
0x140276a23  add     rdx, rcx
0x140276a26  lea     rcx, [rsp+18B8h+var_1698]
0x140276a2e  call    ??0?$vector@W4byte@gsl@@V?$allocator@W4byte@gsl@@@std@@@std@@QEAA@_KAEBV?$allocator@W4byte@gsl@@@1@@Z; std::vector<gsl::byte>::vector<gsl::byte>(unsigned __int64,std::allocator<gsl::byte> const &)
0x140276a33  nop
0x140276a34  xorps   xmm0, xmm0
0x140276a37  movups  xmmword ptr [rsp+18B8h+var_17B8], xmm0
0x140276a3f  lea     rdx, [rsp+18B8h+var_1698]
0x140276a47  lea     rcx, [rsp+18B8h+var_17B8]
0x140276a4f  call    ??$?0$0?0V?$vector@EV?$allocator@E@std@@@std@@$0A@@?$span@E$0?0@gsl@@QEAA@AEAV?$vector@EV?$allocator@E@std@@@std@@@Z; gsl::span<uchar,-1>::span<uchar,-1>(std::vector<uchar> &)
0x140276a54  mov     r15, [rsp+18B8h+var_17B8+8]
0x140276a5c  mov     rax, [rsp+18B8h+var_17B8]
0x140276a64  mov     [rsp+18B8h+var_78], rax
0x140276a6c  mov     [rsp+18B8h+var_78+8], r15
0x140276a74  lea     rcx, [rsp+18B8h+var_78]
0x140276a7c  call    ?size_bytes@?$span@E$0?0@gsl@@QEBA_KXZ; gsl::span<uchar,-1>::size_bytes(void)
0x140276a81  mov     ebx, 10B40h
0x140276a86  cmp     rax, rbx
0x140276a89  jb      loc_14027916A
0x140276a8f  lea     rcx, [rsp+18B8h+var_78]
0x140276a97  call    ?size_bytes@?$span@E$0?0@gsl@@QEBA_KXZ; gsl::span<uchar,-1>::size_bytes(void)
0x140276a9c  mov     r8d, ebx; Size
0x140276a9f  xor     edx, edx; Val
0x140276aa1  mov     rcx, r15; void *
0x140276aa4  call    memset_0
0x140276aa9  mov     ecx, 10C60h
0x140276aae  call    ??$narrow@I_K$0A@@gsl@@YAI_K@Z; gsl::narrow<uint,unsigned __int64,0>(unsigned __int64)
0x140276ab3  mov     edi, eax
0x140276ab5  mov     [rsp+18B8h+var_78], r14
0x140276abd  mov     r9d, 120h
0x140276ac3  mov     r8d, ebx
0x140276ac6  lea     rdx, [rsp+18B8h+var_1830]
0x140276ace  lea     rcx, [rsp+18B8h+var_17B8]
0x140276ad6  call    ?subspan@?$span@$$CBW4byte@gsl@@$0?0@gsl@@QEBA?AV12@_K0@Z; gsl::span<gsl::byte const,-1>::subspan(unsigned __int64,unsigned __int64)
0x140276adb  movups  xmm6, xmmword ptr [rax]
0x140276ade  movaps  [rsp+18B8h+var_17C8], xmm6
0x140276ae6  lea     rcx, [rsp+18B8h+var_17C8]
0x140276aee  call    ?size_bytes@?$span@E$0?0@gsl@@QEBA_KXZ; gsl::span<uchar,-1>::size_bytes(void)
0x140276af3  test    al, 0Fh
0x140276af5  jnz     loc_140279164
0x140276afb  movdqa  [rsp+18B8h+var_17C8], xmm6
0x140276b04  psrldq  xmm6, 8
0x140276b09  movq    rbx, xmm6
0x140276b0e  lea     rcx, [rsp+18B8h+var_17C8]
0x140276b16  call    ?size_bytes@?$span@E$0?0@gsl@@QEBA_KXZ; gsl::span<uchar,-1>::size_bytes(void)
0x140276b1b  shr     rax, 4
0x140276b1f  mov     rdx, rax
0x140276b22  lea     rcx, [rsp+18B8h+var_78]
0x140276b2a  call    ??0?$extent_type@$0?0@details@gsl@@QEAA@_K@Z; gsl::details::extent_type<-1>::extent_type<-1>(unsigned __int64)
0x140276b2f  mov     [rsp+18B8h+var_78+8], rbx
0x140276b37  cmp     [rsp+18B8h+var_78], 0FFFFFFFFFFFFFFFFh
0x140276b40  jz      loc_140279164
0x140276b46  test    rbx, rbx
0x140276b49  jnz     short loc_140276B59
0x140276b4b  cmp     [rsp+18B8h+var_78], r14
0x140276b53  jnz     loc_140279164
0x140276b59  mov     qword ptr [rsp+18B8h+var_17C8], r14
0x140276b61  mov     r8, rdi
0x140276b64  or      r9, 0FFFFFFFFFFFFFFFFh
0x140276b68  lea     rdx, [rsp+18B8h+var_1830]
0x140276b70  lea     rcx, [rsp+18B8h+var_17B8]
0x140276b78  call    ?subspan@?$span@$$CBW4byte@gsl@@$0?0@gsl@@QEBA?AV12@_K0@Z; gsl::span<gsl::byte const,-1>::subspan(unsigned __int64,unsigned __int64)
0x140276b7d  movups  xmm6, xmmword ptr [rax]
0x140276b80  movaps  xmmword ptr [rsp+18B8h+var_17B8], xmm6
0x140276b88  lea     rcx, [rsp+18B8h+var_17B8]
0x140276b90  call    ?size_bytes@?$span@E$0?0@gsl@@QEBA_KXZ; gsl::span<uchar,-1>::size_bytes(void)
0x140276b95  movdqa  xmmword ptr [rsp+18B8h+var_17B8], xmm6
0x140276b9e  psrldq  xmm6, 8
0x140276ba3  movq    rbx, xmm6
0x140276ba8  lea     rcx, [rsp+18B8h+var_17B8]
0x140276bb0  call    ?size_bytes@?$span@E$0?0@gsl@@QEBA_KXZ; gsl::span<uchar,-1>::size_bytes(void)
0x140276bb5  mov     rdx, rax
0x140276bb8  lea     rcx, [rsp+18B8h+var_17C8]
0x140276bc0  call    ??0?$extent_type@$0?0@details@gsl@@QEAA@_K@Z; gsl::details::extent_type<-1>::extent_type<-1>(unsigned __int64)
0x140276bc5  mov     qword ptr [rsp+18B8h+var_17C8+8], rbx
0x140276bcd  cmp     qword ptr [rsp+18B8h+var_17C8], 0FFFFFFFFFFFFFFFFh
0x140276bd6  jz      loc_14027915E
0x140276bdc  test    rbx, rbx
0x140276bdf  jnz     short loc_140276BEF
0x140276be1  cmp     qword ptr [rsp+18B8h+var_17C8], r14
0x140276be9  jnz     loc_14027915E
0x140276bef  mov     qword ptr [rsp+18B8h+var_1718], r15
0x140276bf7  movups  xmm0, xmmword ptr [rsp+18B8h+var_78]
0x140276bff  movdqu  [rsp+18B8h+var_1718+8], xmm0
0x140276c08  mov     dword ptr [rsp+18B8h+var_1700], edi
0x140276c0f  movups  xmm1, [rsp+18B8h+var_17C8]
0x140276c17  movdqu  [rsp+18B8h+var_16F8], xmm1
0x140276c20  mov     dl, 1
0x140276c22  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_L1VH_VMMFeatures@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_L1VH_VMMFeatures@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_L1VH_VMMFeatures> `wil::Feature<__WilFeatureTraits_Feature_L1VH_VMMFeatures>::GetImpl(void)'::`2'::impl
0x140276c29  call    ?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_L1VH_VMMFeatures@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_L1VH_VMMFeatures>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)
0x140276c2e  cmp     [rsi+72h], r14b
  ... truncated ...
```
