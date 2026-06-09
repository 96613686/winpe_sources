# IumInvokeSecureService

- ea: `0x140014dd0`
- end: `0x14001b0ac`
- name: `IumInvokeSecureService`
- size: `25308`
- prototype: `char __fastcall(__int64, __int64)`
- caller_count: `1`
- callee_count: `226`
- tags: `registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x1400ee8b0`

## callees

- `0x140001120`
- `0x140001320`
- `0x140002410`
- `0x1400024b0`
- `0x140002900`
- `0x140002a04`
- `0x140002e40`
- `0x140002ef0`
- `0x140003860`
- `0x140008500`
- `0x140008d00`
- `0x140009520`
- `0x14000a320`
- `0x14000ae60`
- `0x14000b0b0`
- `0x14000b980`
- `0x14000d020`
- `0x14000e130`
- `0x14000e410`
- `0x14000e460`
- `0x14000e4b0`
- `0x14000e810`
- `0x14000e8e0`
- `0x14000ec90`
- `0x14000f0f0`
- `0x14000f8b0`
- `0x140010a9c`
- `0x140010b90`
- `0x140010c00`
- `0x1400111d0`
- `0x1400118d0`
- `0x1400119c4`
- `0x140011f1c`
- `0x140012750`
- `0x140012e40`
- `0x140012ea4`
- `0x1400130c0`
- `0x1400133e8`
- `0x140013a64`
- `0x1400147b4`
- `0x140014d64`
- `0x140014dd0`
- `0x14001b0c0`
- `0x14001d414`
- `0x14001d4c4`
- `0x14001d8cc`
- `0x14001dd58`
- `0x14001e4d8`
- `0x14001f398`
- `0x14001f578`

## import_xrefs

- `skci!SkciTransferVersionResource` at `0x140018d68`
- `skci!SkciTransferVersionResource` at `0x140018d68`
- `skci!SkciSetCodeIntegrityPolicy` at `0x14001906e`
- `skci!SkciSetCodeIntegrityPolicy` at `0x14001906e`
- `skci!SkciCreateCodeCatalog` at `0x140018a57`
- `skci!SkciCreateCodeCatalog` at `0x140018a57`
- `skci!SkciFinalizeSecureImageHash` at `0x140018c76`
- `skci!SkciFinalizeSecureImageHash` at `0x140018c76`
- `cng!BCryptGenRandom` at `0x140015e92`
- `cng!BCryptGenRandom` at `0x140019522`
- `cng!BCryptGenRandom` at `0x140015e92`
- `cng!BCryptGenRandom` at `0x140019522`
- `cng!EntropyPoolTriggerReseedForIum` at `0x140019504`
- `cng!EntropyPoolTriggerReseedForIum` at `0x140019504`
- `cng!BCryptImportKeyPair` at `0x140015f49`
- `cng!BCryptImportKeyPair` at `0x140015f49`
- `cng!BCryptEncrypt` at `0x140015fb0`
- `cng!BCryptEncrypt` at `0x140015fb0`
- `cng!BCryptDestroyKey` at `0x140015fea`
- `cng!BCryptDestroyKey` at `0x140015fea`
- `cng!EntropyProvideData` at `0x1400194ec`
- `cng!EntropyProvideData` at `0x1400194ec`

## pseudocode

```c
char __fastcall IumInvokeSecureService(__int64 a1, __int64 a2)
{
  __int64 v2; // rdi
  unsigned int v3; // r15d
  __int64 v4; // r14
  _QWORD *v5; // r13
  size_t v6; // r12
  __int64 v7; // rdx
  __int64 v8; // rax
  signed __int64 m; // rcx
  __int64 v10; // rax
  signed __int64 i; // rcx
  char result; // al
  char v13; // cl
  __int64 v14; // rcx
  __int64 *v15; // r9
  __int16 v16; // dx
  unsigned __int64 v17; // r8
  __int128 *v18; // rcx
  __int16 v19; // ax
  __int64 v20; // rax
  NTSTATUS inited; // edi
  int v22; // edi
  ULONG_PTR v23; // rbx
  int v24; // ecx
  __int64 v25; // r9
  _QWORD *StackBase; // rax
  _DWORD *v27; // r8
  unsigned __int64 v28; // r8
  size_t *v29; // rsi
  size_t v30; // rdi
  __int64 v31; // r13
  __int64 v32; // rax
  _QWORD *v33; // rbx
  __int64 v34; // rdx
  NTSTATUS v35; // eax
  __int64 v36; // rcx
  PUCHAR v37; // rsi
  _QWORD *v38; // rax
  char v39; // dl
  unsigned int v40; // edi
  __int64 v41; // r10
  unsigned int v42; // ebx
  __int64 v43; // r11
  unsigned int v44; // eax
  __int64 v45; // rcx
  int v46; // eax
  __int16 v47; // bx
  NTSTATUS Thread; // eax
  __int64 v49; // rax
  __int64 v50; // rbx
  _DWORD *v51; // rcx
  signed __int64 v52; // rax
  signed __int64 v53; // rdx
  __int64 v54; // rcx
  PUCHAR v55; // rbx
  signed __int64 v56; // rax
  signed __int64 v57; // rcx
  signed __int64 v58; // r8
  signed __int64 v59; // rdx
  signed __int64 v60; // rdx
  __int64 v61; // rcx
  PUCHAR v62; // rbx
  signed __int64 v63; // rax
  signed __int64 v64; // rcx
  signed __int64 v65; // r8
  signed __int64 v66; // rdx
  _QWORD *v67; // rax
  char v68; // bl
  _QWORD *v69; // rcx
  __int64 v70; // rdi
  int Policy; // eax
  _QWORD *v72; // rax
  signed __int64 v73; // rdx
  __int64 v74; // rcx
  PUCHAR v75; // rbx
  signed __int64 v76; // rax
  signed __int64 v77; // rcx
  signed __int64 v78; // r8
  signed __int64 v79; // rdx
  signed __int64 v80; // rax
  signed __int64 v81; // rdx
  __int64 v82; // rax
  __int64 v83; // r8
  signed __int64 v84; // rdx
  _QWORD *v85; // r13
  _DWORD *v86; // rax
  int v87; // r15d
  int v88; // eax
  PUCHAR v89; // rsi
  int v90; // eax
  ULONG_PTR v91; // rbx
  void *v92; // r12
  __int16 v93; // bx
  __int64 v94; // rcx
  PUCHAR v95; // rbx
  signed __int64 v96; // rax
  signed __int64 v97; // rcx
  signed __int64 v98; // r8
  signed __int64 v99; // rdx
  signed __int64 v100; // rdx
  __int64 v101; // rcx
  PUCHAR v102; // rbx
  signed __int64 v103; // rax
  signed __int64 v104; // rcx
  signed __int64 v105; // r8
  signed __int64 v106; // rdx
  int v107; // ecx
  int v108; // ebx
  BCRYPT_KEY_HANDLE v109; // r15
  ULONG v110; // eax
  __int64 v111; // rbx
  __int128 v112; // xmm0
  signed __int64 v113; // rdx
  void *v114; // r8
  __int64 v115; // rax
  signed __int64 v116; // rdx
  __int64 v117; // rbx
  __int64 v118; // rdx
  signed __int64 v119; // rdx
  __int64 v120; // rbx
  signed __int64 v121; // rdx
  __int64 v122; // rbx
  signed __int64 v123; // rdx
  __int64 v124; // rcx
  ULONG_PTR v125; // r8
  ULONG_PTR v126; // rbx
  signed __int64 v127; // rax
  signed __int64 v128; // rcx
  char v129; // si
  int v130; // eax
  __int64 v131; // rax
  int v132; // edx
  ULONG_PTR v133; // rsi
  int v134; // eax
  int v135; // eax
  signed __int64 v136; // rdx
  __int64 v137; // rcx
  ULONG_PTR v138; // rbx
  signed __int64 v139; // rax
  signed __int64 v140; // rdx
  __int64 v141; // rcx
  ULONG_PTR v142; // rsi
  __int64 v143; // r13
  signed __int64 v144; // rax
  signed __int64 v145; // rcx
  ULONG_PTR v146; // rcx
  _QWORD *v147; // rcx
  __int64 v148; // rcx
  __int64 v149; // rdx
  _QWORD *v150; // rbx
  __int64 v151; // rcx
  unsigned int v152; // ebx
  int v153; // eax
  _QWORD *v154; // rsi
  ULONG_PTR v155; // r15
  __int64 v156; // rdx
  int v157; // ecx
  int v158; // ebx
  __int64 v159; // r12
  signed __int64 v160; // rdx
  unsigned __int64 v161; // r12
  ULONG_PTR v162; // rsi
  unsigned __int64 v163; // rsi
  int v164; // ebx
  unsigned __int64 v165; // rcx
  __int64 v166; // rax
  __int64 v167; // rdx
  __int128 v168; // xmm0
  __int128 *v169; // rcx
  __int64 v170; // rdx
  __int128 *v171; // rax
  __int128 v172; // xmm0
  unsigned __int64 v173; // rcx
  __int64 v174; // rax
  unsigned __int64 v175; // rsi
  unsigned __int64 v176; // rbx
  __int64 v177; // r8
  int v178; // eax
  __int64 v179; // r8
  __int64 v180; // rdx
  __int64 v181; // r8
  __int64 v182; // rax
  __int64 SecurePool; // rax
  __int64 v184; // rdx
  __int64 v185; // rcx
  int v186; // eax
  PUCHAR v187; // rbx
  __int64 v188; // r8
  __int64 v189; // rax
  __int64 v190; // rdx
  __int64 v191; // rcx
  int v192; // eax
  ULONG_PTR v193; // r13
  size_t v194; // rsi
  __int64 v195; // r15
  unsigned __int64 v196; // r12
  int v197; // edx
  void *v198; // rax
  ULONG_PTR v199; // rdi
  _QWORD *v200; // rcx
  unsigned __int64 v201; // rbx
  __int64 v202; // rax
  unsigned __int64 v203; // rax
  __int64 v204; // rcx
  void *v205; // rcx
  __int64 v206; // r8
  unsigned __int8 v207; // si
  __int64 v208; // rbx
  __int64 v209; // rcx
  void *v210; // rbx
  __int64 v211; // rcx
  signed __int64 v212; // rdx
  __int64 v213; // r8
  int Handle; // eax
  __int64 v215; // rbx
  __int64 v216; // rcx
  __int64 v217; // rcx
  ULONG_PTR v218; // rsi
  size_t v219; // rdi
  void *Pool; // rax
  ULONG_PTR v221; // rbx
  __int64 v222; // rax
  unsigned int v223; // ecx
  unsigned __int64 v224; // rbx
  int v225; // eax
  __int64 v226; // rsi
  unsigned int v227; // r12d
  __int64 v228; // r13
  unsigned __int64 v229; // rbx
  __int64 v230; // r9
  unsigned int v231; // ebx
  bool v232; // zf
  struct _EXCEPTION_REGISTRATION_RECORD *ExceptionList; // r13
  unsigned int v234; // eax
  char *v235; // rsi
  __int64 v236; // rcx
  ULONG_PTR v237; // rbx
  unsigned __int8 v238; // al
  __int64 v239; // rbx
  unsigned __int8 v240; // di
  __int64 v241; // rax
  _QWORD *v242; // rcx
  int v243; // ebx
  unsigned __int8 v244; // al
  __int64 v245; // rdx
  unsigned __int8 v246; // si
  __int64 *v247; // rdi
  __int64 **v248; // rcx
  unsigned __int8 v249; // bl
  __int64 v250; // rax
  __int64 v251; // rdx
  __int64 v252; // rax
  __int64 v253; // r8
  unsigned __int8 v254; // di
  _QWORD *v255; // rbx
  __int64 v256; // rax
  int v257; // edi
  unsigned int v258; // ebx
  unsigned int v259; // r15d
  int v260; // eax
  unsigned __int8 v261; // al
  __int64 *v262; // rcx
  unsigned __int8 v263; // si
  __int64 v264; // r8
  unsigned int v265; // ebx
  unsigned int v266; // edx
  __int64 **v267; // rax
  __int64 v268; // rax
  _QWORD **v269; // rcx
  _QWORD **v270; // rax
  _QWORD *v271; // rax
  _QWORD *v272; // rax
  __int64 v273; // rcx
  signed __int64 v274; // rax
  __int64 v275; // rdx
  __int64 v276; // rcx
  __int64 v277; // rcx
  int v278; // eax
  __int64 v279; // rdx
  unsigned __int8 v280; // bl
  _QWORD *v281; // rax
  __int64 v282; // rbx
  __int64 v283; // rcx
  __int64 v284; // rax
  __int16 v285; // cx
  __int16 v286; // cx
  _QWORD *v287; // rcx
  __int64 v288; // rdx
  unsigned int v289; // eax
  unsigned int v290; // edx
  __int64 v291; // rcx
  __int64 v292; // r8
  __int64 v293; // r9
  __int64 v294; // rdx
  __int64 v295; // rcx
  int v296; // r12d
  ULONG_PTR v297; // r15
  size_t v298; // rbx
  _WORD *v299; // rax
  _WORD *v300; // r13
  __int64 v301; // rax
  _DWORD *v302; // rsi
  __int64 v303; // r8
  ULONG_PTR v304; // r12
  __int64 v305; // rbx
  unsigned int v306; // edx
  unsigned int v307; // eax
  __int64 v308; // rdx
  unsigned int v309; // ecx
  __int64 v310; // rax
  unsigned int v311; // eax
  __int64 v312; // r9
  __int64 v313; // r8
  __int64 v314; // rdx
  __int64 v315; // rcx
  _QWORD *v316; // rax
  __int64 v317; // rbx
  __int64 v318; // rcx
  __int64 Nar; // rax
  int v320; // eax
  _QWORD *v321; // rax
  __int64 v322; // rbx
  __int64 v323; // rcx
  __int64 v324; // rax
  __int64 v325; // rax
  __int64 v326; // rcx
  ULONG_PTR v327; // r10
  unsigned int v328; // edi
  __int64 v329; // rcx
  __int64 v330; // rbx
  __int64 v331; // r10
  unsigned int v332; // r13d
  __int64 v333; // r9
  char v334; // cl
  ULONG_PTR v335; // rbx
  __int64 v336; // rax
  _QWORD *v337; // rcx
  __int64 v338; // rdx
  __int64 v339; // rcx
  unsigned __int64 v340; // rsi
  __int64 v341; // rbx
  int v342; // r8d
  ULONG_PTR v343; // r15
  size_t v344; // r12
  const void *v345; // r13
  _QWORD *v346; // rax
  ULONG_PTR v347; // rbx
  __int64 v348; // rcx
  size_t v349; // rax
  size_t v350; // rdi
  _QWORD *v351; // rcx
  __int64 v352; // r8
  __int64 v353; // r15
  __int64 v354; // r13
  _QWORD *v355; // rax
  ULONG_PTR v356; // rbx
  __int64 v357; // rcx
  _QWORD *v358; // rdx
  __int64 v359; // rcx
  __int64 v360; // rdx
  __int64 v361; // rcx
  __int64 v362; // rbx
  __int64 v363; // rsi
  __int64 v364; // r9
  __int64 v365; // rdx
  __int64 v366; // rbx
  int v367; // r8d
  int v368; // eax
  __int64 v369; // rcx
  __int64 v370; // rsi
  __int64 v371; // rbx
  __int64 v372; // r12
  unsigned int v373; // r13d
  int v374; // eax
  ULONG_PTR v375; // r15
  PUCHAR v376; // rbx
  __int64 v377; // rcx
  __int64 v378; // rsi
  __int64 v379; // r15
  __int64 v380; // rax
  int v381; // r9d
  unsigned __int64 v382; // rsi
  void *v383; // rax
  void *v384; // r15
  __int64 v385; // rcx
  unsigned int v386; // r15d
  _QWORD *v387; // rax
  ULONG_PTR v388; // rsi
  __int64 v389; // rcx
  _QWORD *v390; // rcx
  __int64 v391; // rdx
  __int64 *v392; // rsi
  unsigned __int8 v393; // al
  signed __int64 v394; // r8
  __int64 *v395; // rdi
  unsigned __int8 v396; // r13
  __int64 *v397; // rbx
  signed __int64 v398; // rax
  signed __int64 v399; // rcx
  signed __int64 v400; // rdx
  _QWORD *v401; // rcx
  ULONG_PTR v402; // rbx
  _QWORD *v403; // rcx
  __int64 v404; // r8
  _QWORD *v405; // rdx
  __int64 v406; // rax
  __int64 v407; // rcx
  ULONG_PTR v408; // r13
  unsigned int v409; // r15d
  unsigned __int64 v410; // r12
  ULONG_PTR v411; // rax
  unsigned __int64 v412; // rcx
  ULONG_PTR v413; // rcx
  ULONG_PTR *v414; // rdx
  __int64 v415; // rdi
  __int64 v416; // rbx
  unsigned __int8 v417; // al
  __int64 *v418; // rcx
  unsigned __int8 v419; // si
  char v420; // al
  __int64 v421; // r9
  __int64 v422; // rcx
  __int64 v423; // rsi
  __int64 v424; // rcx
  ULONG_PTR v425; // r15
  size_t v426; // rbx
  void *v427; // rax
  const void *v428; // rsi
  _QWORD *v429; // rax
  __int64 v430; // rcx
  __int64 v431; // rbx
  void *v432; // rax
  __int64 v433; // rdi
  _QWORD *v434; // rcx
  __int64 v435; // rdx
  __int64 v436; // rdx
  int v437; // ecx
  __int64 v438; // rdi
  __int64 v439; // r15
  __int64 v440; // r12
  unsigned __int8 v441; // r13
  _QWORD *v442; // rax
  __int64 v443; // rcx
  signed __int64 v444; // rax
  _QWORD *v445; // rbx
  unsigned __int8 v446; // al
  _QWORD *v447; // rcx
  unsigned __int8 v448; // si
  _QWORD *v449; // rcx
  __int64 v450; // rdx
  unsigned __int64 v451; // r15
  unsigned __int64 v452; // rdx
  __int64 v453; // rsi
  char *j; // r12
  unsigned __int64 v455; // rcx
  unsigned int v456; // ecx
  __int64 v457; // rax
  __int64 v458; // rdi
  __int64 v459; // rbx
  int v460; // edx
  __int64 k; // rdx
  __int64 v462; // rcx
  _BYTE *v463; // rax
  __int64 v464; // rax
  unsigned __int64 v465; // r15
  char *v466; // rsi
  __int64 v467; // rbx
  int v468; // eax
  char v469; // cl
  unsigned __int8 v470; // bl
  BOOL v471; // ebx
  unsigned __int8 CurrentIrql; // di
  __int64 v473; // rcx
  __int64 v474; // rcx
  int v475; // eax
  UCHAR *v476; // rbx
  int v477; // eax
  __int64 FunctionInTree; // rsi
  __int64 v479; // rcx
  char v480; // al
  _BYTE *v481; // r12
  _QWORD *v482; // r13
  __int64 v483; // rcx
  __int64 v484; // r15
  unsigned __int8 v485; // bl
  unsigned __int8 v486; // di
  unsigned __int8 v487; // si
  __int64 v488; // rax
  unsigned int v489; // r11d
  __int64 v490; // rdx
  char v491; // al
  bool v492; // cf
  __int64 v493; // rax
  __int64 v494; // rdx
  unsigned int v495; // ecx
  char *v496; // rbx
  __int64 v497; // rsi
  ULONG_PTR v498; // rbx
  unsigned __int8 v499; // bl
  __int64 DeviceByLocation; // rsi
  __int64 v501; // rsi
  unsigned __int8 v502; // r15
  __int64 DeviceByToken; // rax
  ULONG_PTR v504; // rbx
  int v505; // eax
  int v506; // ecx
  int v507; // r8d
  char v508; // dl
  unsigned int v509; // r8d
  __int64 v510; // r9
  __int64 v511; // rcx
  __int64 v512; // rcx
  __int64 v513; // rax
  __int64 v514; // rcx
  __int64 v515; // rcx
  __int64 v516; // rdx
  __int64 v517; // r8
  __int64 v518; // rcx
  unsigned __int8 v519; // dl
  __int64 v520; // r9
  __int64 v521; // rdx
  __int64 v522; // rcx
  int v523; // eax
  ULONG_PTR v524; // rcx
  _OWORD *v525; // rax
  unsigned __int8 v526; // al
  struct _EXCEPTION_REGISTRATION_RECORD *v527; // rcx
  int v528; // r8d
  unsigned __int64 v529; // rdx
  unsigned int v530; // r10d
  int v531; // r10d
  __int64 v532; // rcx
  __int64 v533; // rcx
  __int64 v534; // rbx
  unsigned int v535; // eax
  __int64 v536; // r15
  ULONG_PTR v537; // rsi
  __int64 v538; // rax
  __int64 v539; // rax
  __int64 *v540; // r12
  size_t v541; // rdi
  _DWORD *v542; // rax
  _DWORD *v543; // rbx
  __int64 v544; // rcx
  unsigned int v545; // ebx
  __int64 v546; // rdi
  ULONG_PTR v547; // r13
  ULONG_PTR v548; // rsi
  __int64 v549; // r9
  signed __int32 v550[8]; // [rsp+0h] [rbp-100h] BYREF
  PUCHAR pbInput; // [rsp+20h] [rbp-E0h]
  ULONG cbInput[2]; // [rsp+28h] [rbp-D8h]
  ULONG cbOutput[2]; // [rsp+38h] [rbp-C8h]
  ULONG v554[2]; // [rsp+60h] [rbp-A0h] BYREF
  void *Src; // [rsp+68h] [rbp-98h] BYREF
  __int64 v556; // [rsp+70h] [rbp-90h] BYREF
  PUCHAR v557; // [rsp+78h] [rbp-88h] BYREF
  bool v558; // [rsp+80h] [rbp-80h]
  ULONG_PTR v559; // [rsp+88h] [rbp-78h] BYREF
  unsigned __int16 v560[8]; // [rsp+90h] [rbp-70h] BYREF
  void *v561[2]; // [rsp+A0h] [rbp-60h] BYREF
  _QWORD **v562; // [rsp+B0h] [rbp-50h] BYREF
  __int64 *v563; // [rsp+B8h] [rbp-48h]
  __int64 v564; // [rsp+C0h] [rbp-40h] BYREF
  __int128 v565; // [rsp+C8h] [rbp-38h] BYREF
  ULONG pcbResult; // [rsp+D8h] [rbp-28h] BYREF
  int v567; // [rsp+DCh] [rbp-24h] BYREF
  __int64 v568; // [rsp+E0h] [rbp-20h]
  _QWORD *v569; // [rsp+E8h] [rbp-18h] BYREF
  _QWORD **v570; // [rsp+F0h] [rbp-10h]
  int v571; // [rsp+F8h] [rbp-8h] BYREF
  __int64 v572; // [rsp+100h] [rbp+0h] BYREF
  ULONG_PTR BugCheckParameter3; // [rsp+108h] [rbp+8h] BYREF
  BCRYPT_KEY_HANDLE phKey; // [rsp+110h] [rbp+10h] BYREF
  __int128 v575; // [rsp+118h] [rbp+18h] BYREF
  __int128 v576; // [rsp+128h] [rbp+28h] BYREF
  __int128 v577; // [rsp+138h] [rbp+38h] BYREF
  __int128 v578; // [rsp+148h] [rbp+48h]
  __int128 v579; // [rsp+158h] [rbp+58h] BYREF
  __int64 v580; // [rsp+168h] [rbp+68h]
  ULONG_PTR v581; // [rsp+170h] [rbp+70h] BYREF
  _QWORD v582[2]; // [rsp+178h] [rbp+78h] BYREF
  __int64 v583; // [rsp+188h] [rbp+88h] BYREF
  __int64 v584; // [rsp+190h] [rbp+90h]
  _DWORD *v585; // [rsp+198h] [rbp+98h]
  __int128 v586; // [rsp+1A0h] [rbp+A0h] BYREF
  __int64 v587; // [rsp+1B0h] [rbp+B0h]
  __int128 v588; // [rsp+1B8h] [rbp+B8h] BYREF
  __int64 v589; // [rsp+1C8h] [rbp+C8h]
  ULONG_PTR v590; // [rsp+1D0h] [rbp+D0h] BYREF
  __int128 v591; // [rsp+1D8h] [rbp+D8h] BYREF
  __int128 v592; // [rsp+1E8h] [rbp+E8h]
  _QWORD pPaddingInfo[3]; // [rsp+1F8h] [rbp+F8h] BYREF
  ULONG BackTraceHash[4]; // [rsp+210h] [rbp+110h] BYREF
  __int128 v595; // [rsp+220h] [rbp+120h]
  __int64 v596; // [rsp+230h] [rbp+130h]
  _QWORD v597[3]; // [rsp+238h] [rbp+138h] BYREF
  _QWORD v598[4]; // [rsp+250h] [rbp+150h] BYREF
  __int128 v599; // [rsp+270h] [rbp+170h] BYREF
  __int128 v600; // [rsp+280h] [rbp+180h]
  __int128 v601; // [rsp+290h] [rbp+190h]
  __int128 v602; // [rsp+2A0h] [rbp+1A0h]
  __int64 v603; // [rsp+2B0h] [rbp+1B0h] BYREF
  __int16 v604; // [rsp+2B8h] [rbp+1B8h]
  __int16 v605; // [rsp+2BAh] [rbp+1BAh]
  __int64 v606; // [rsp+2BCh] [rbp+1BCh]
  _DWORD v607[7]; // [rsp+2C4h] [rbp+1C4h] BYREF
  __int128 v608; // [rsp+2E0h] [rbp+1E0h] BYREF
  __int128 v609; // [rsp+2F0h] [rbp+1F0h] BYREF
  __int128 v610; // [rsp+300h] [rbp+200h]
  __int128 v611; // [rsp+310h] [rbp+210h] BYREF
  __int128 v612; // [rsp+320h] [rbp+220h] BYREF
  __int128 v613; // [rsp+330h] [rbp+230h]
  __int128 v614; // [rsp+340h] [rbp+240h]
  __int128 v615; // [rsp+350h] [rbp+250h]
  __int128 v616; // [rsp+360h] [rbp+260h]
  __int128 v617; // [rsp+370h] [rbp+270h]
  __int128 v618; // [rsp+380h] [rbp+280h] BYREF
  __int128 v619; // [rsp+390h] [rbp+290h]
  __int128 v620; // [rsp+3A0h] [rbp+2A0h]
  __int128 v621; // [rsp+3B0h] [rbp+2B0h]
  __int128 v622; // [rsp+3C0h] [rbp+2C0h]
  __int128 v623; // [rsp+3D0h] [rbp+2D0h]
  __int128 v624; // [rsp+3E0h] [rbp+2E0h] BYREF
  __int128 v625; // [rsp+3F0h] [rbp+2F0h]
  __int128 v626; // [rsp+400h] [rbp+300h]
  __int128 v627; // [rsp+410h] [rbp+310h]
  __int128 v628; // [rsp+420h] [rbp+320h]
  __int128 v629; // [rsp+430h] [rbp+330h]
  __int128 v630; // [rsp+440h] [rbp+340h] BYREF
  __int128 v631; // [rsp+450h] [rbp+350h]
  __int128 v632; // [rsp+460h] [rbp+360h]
  __int128 v633; // [rsp+470h] [rbp+370h]
  __int128 v634; // [rsp+480h] [rbp+380h]
  __int128 v635; // [rsp+490h] [rbp+390h]
  __int64 v636; // [rsp+4A0h] [rbp+3A0h]
  _OWORD v637[2]; // [rsp+4B0h] [rbp+3B0h] BYREF
  __int64 v638; // [rsp+4E0h] [rbp+3E0h]

  v3 = 0;
  *(_QWORD *)v554 = a1;
  v4 = a1;
  v559 = 0;
  v5 = 0;
  Src = 0;
  v6 = 0;
  v556 = 0;
  v557 = 0;
  v564 = 0;
  if ( SkiUnrestrictedThreadCount >= 0 )
  {
    if ( IumpLimitedDispatchFromNormalDispatch )
    {
      if ( SkiMirrorOwner )
      {
        if ( *(_WORD *)(a1 + 2) == 279 )
        {
          SkiHibernateAborted = 1;
          _InterlockedExchange64(&SkiBarrierWait, 0);
          _InterlockedExchange64(&SkiMirrorOwner, 0);
        }
        else
        {
          v10 = SkiMirrorOwner;
          for ( i = (__int64)KeGetPcr()->NtTib.ExceptionList | 1; SkiMirrorOwner; v10 = SkiMirrorOwner )
          {
            if ( v10 == 1 && (unsigned __int64)_InterlockedCompareExchange64(&SkiMirrorOwner, i, 1) < 2 )
              break;
            _mm_pause();
          }
        }
      }
      v7 = 1;
      goto LABEL_19;
    }
    v13 = *(_BYTE *)a1;
    v638 = v2;
    if ( SkeNtKernelImportsInitialized != 2 )
    {
      if ( v13 == 2 && *(_WORD *)(v4 + 2) == 271 )
      {
        v606 = 0;
        v608 = 0;
        memset(v607, 0, 12);
        if ( *(_QWORD *)(v4 + 16) == 176 )
        {
          v14 = *(_QWORD *)(v4 + 8);
          v15 = (__int64 *)(v4 + 24);
          v16 = v14;
          v603 = 0;
          v607[5] = 176;
          *(_QWORD *)&v607[3] = v14 & 0xFFFFFFFFFFFFF000uLL;
          v17 = ((unsigned __int64)(v14 & 0xFFF) + 4271) >> 12;
          v18 = &v608;
          v607[6] = v16 & 0xFFF;
          v604 = 8 * (v17 + 6);
          v19 = 0;
          v605 = 0;
          if ( (_DWORD)v17 )
          {
            do
            {
              v20 = *v15++;
              *(_QWORD *)v18 = v20;
              v18 = (__int128 *)((char *)v18 + 8);
              LODWORD(v17) = v17 - 1;
            }
            while ( (_DWORD)v17 );
            v19 = v605;
          }
          v605 = v19 | 2;
          inited = SkmmMapMdl(&v603, 1);
          if ( inited >= 0 )
          {
            v22 = SkeSetNtKernelImports(*(_QWORD *)&v607[1]);
            SkmmUnmapMdl(&v603);
            *(_BYTE *)(v4 + 1) = 1;
            *(_QWORD *)(v4 + 8) = v22;
            return 0;
          }
          goto LABEL_625;
        }
      }
LABEL_31:
      *(_BYTE *)(v4 + 1) = 1;
      result = 0;
      *(_QWORD *)(v4 + 8) = -1073741811;
      return result;
    }
    if ( v13 == 1 )
    {
      SkpsPrepareEnclaveCall(v4, a2);
      return 1;
    }
    if ( v13 != 2 )
      goto LABEL_31;
    v24 = 225;
    v560[0] = *(_WORD *)(v4 + 2);
    v23 = v560[0];
    v25 = 255;
    if ( (unsigned __int16)(v560[0] - 225) <= 2u || (v24 = 229, (unsigned __int16)(v560[0] - 229) <= 1u) )
    {
      if ( g_ExpectedIumInitializationPhase )
      {
        *(_BYTE *)(v4 + 1) = 1;
        result = 0;
        *(_QWORD *)(v4 + 8) = -1073741790;
        return result;
      }
    }
    else
    {
      if ( v560[0] == 231 || v560[0] == 217 )
      {
        if ( g_ExpectedIumInitializationPhase )
        {
          *(_BYTE *)(v4 + 1) = 1;
          result = 0;
          *(_QWORD *)(v4 + 8) = -1073741790;
          return result;
        }
        goto LABEL_50;
      }
      if ( v560[0] < 0xCFu )
      {
        if ( (unsigned __int16)(v560[0] - 1) > 2u && v560[0] != 5 )
        {
          if ( g_ExpectedIumInitializationPhase != 4 )
          {
            *(_BYTE *)(v4 + 1) = 1;
            result = 0;
            *(_QWORD *)(v4 + 8) = -1073741790;
            return result;
          }
          goto LABEL_50;
        }
        if ( g_ExpectedIumInitializationPhase != 2 )
        {
LABEL_51:
          *(_BYTE *)(v4 + 1) = 1;
          result = 0;
          *(_QWORD *)(v4 + 8) = -1073741790;
          return result;
        }
      }
    }
    if ( v560[0] >= 0xFFu )
    {
LABEL_52:
      StackBase = KeGetPcr()->NtTib.StackBase;
      v27 = (_DWORD *)StackBase[33];
      v585 = v27;
      if ( v27 && *v27 != v560[0] )
        StackBase[33] = 0;
      if ( (unsigned __int16)v23 > 0x700u )
LABEL_1257:
        SkeBugCheckEx(0x121u, 0xFFFFFFFFC000001CuLL, v23, 0, 0);
      if ( (_WORD)v23 == 1792 )
        SkeBugCheckEx(*(_DWORD *)(v4 + 8), *(_QWORD *)(v4 + 16), *(_QWORD *)(v4 + 24), *(_QWORD *)(v4 + 32), 0);
      v28 = 0x140000000uLL;
      inited = 0;
      switch ( (int)v23 )
      {
        case 1:
          v163 = __rdtsc();
          if ( _InterlockedCompareExchange(&g_ExpectedIumInitializationPhase, 3, 2) != 2 )
          {
            inited = -1073741790;
            goto LABEL_1254;
          }
          v164 = SkeDisableInterrupts();
          while ( _InterlockedCompareExchange(&SkpUpdateLock, 1, 0) )
          {
            if ( v164 )
              _enable();
            _mm_pause();
            SkeDisableInterrupts();
          }
          v165 = 0xFFFFF78000000000uLL;
          v166 = SkNtosUserSharedData;
          v167 = 7;
          do
          {
            v165 += 128LL;
            v168 = *(_OWORD *)v166;
            v166 += 128;
            *(_OWORD *)(v165 - 128) = v168;
            *(_OWORD *)(v165 - 112) = *(_OWORD *)(v166 - 112);
            *(_OWORD *)(v165 - 96) = *(_OWORD *)(v166 - 96);
            *(_OWORD *)(v165 - 80) = *(_OWORD *)(v166 - 80);
            *(_OWORD *)(v165 - 64) = *(_OWORD *)(v166 - 64);
            *(_OWORD *)(v165 - 48) = *(_OWORD *)(v166 - 48);
            *(_OWORD *)(v165 - 32) = *(_OWORD *)(v166 - 32);
            *(_OWORD *)(v165 - 16) = *(_OWORD *)(v166 - 16);
            --v167;
          }
          while ( v167 );
          *(_OWORD *)v165 = *(_OWORD *)v166;
          *(_OWORD *)(v165 + 16) = *(_OWORD *)(v166 + 16);
          *(_OWORD *)(v165 + 32) = *(_OWORD *)(v166 + 32);
          *(_OWORD *)(v165 + 48) = *(_OWORD *)(v166 + 48);
          *(_OWORD *)(v165 + 64) = *(_OWORD *)(v166 + 64);
          *(_QWORD *)(v165 + 80) = *(_QWORD *)(v166 + 80);
          v169 = (__int128 *)0xFFFFF78000000730LL;
          v170 = 6;
          v171 = (__int128 *)(SkNtosUserSharedData + 1840);
          do
          {
            v169 += 8;
            v172 = *v171;
            v171 += 8;
            *(v169 - 8) = v172;
            *(v169 - 7) = *(v171 - 7);
            *(v169 - 6) = *(v171 - 6);
            *(v169 - 5) = *(v171 - 5);
            *(v169 - 4) = *(v171 - 4);
            *(v169 - 3) = *(v171 - 3);
            *(v169 - 2) = *(v171 - 2);
            *(v169 - 1) = *(v171 - 1);
            --v170;
          }
          while ( v170 );
          *v169 = *v171;
          v169[1] = v171[1];
          v169[2] = v171[2];
          v169[3] = v171[3];
          v169[4] = v171[4];
          v169[5] = v171[5];
          v169[6] = v171[6];
          if ( !MEMORY[0xFFFFF78000000268] )
          {
            MEMORY[0xFFFFF78000000264] = 1;
            MEMORY[0xFFFFF78000000268] = 1;
          }
          MEMORY[0xFFFFF780000003B8] = 0;
          MEMORY[0xFFFFF78000000300] = 10000000;
          MEMORY[0xFFFFF780000003C6] = ShvlpReferenceTscPage != 0 ? 3 : 0;
          MEMORY[0xFFFFF78000000294] = 0;
          MEMORY[0xFFFFF78000000308] = 0;
          MEMORY[0xFFFFF780000002D4] = 0;
          SkpUpdateLock = 0;
          if ( v164 )
            _enable();
          inited = SkInitSystem(4);
          if ( inited < 0 )
            goto LABEL_1254;
          *(_QWORD *)(v4 + 16) = (int)SkCheckHibernationSupport();
          _InterlockedIncrement(&g_ExpectedIumInitializationPhase);
          SkWritePerfTraceEntry(0, 4, __rdtsc() - v163);
          goto LABEL_624;
        case 2:
          v217 = *(_QWORD *)(v4 + 8);
          *(_QWORD *)v554 = 0;
          if ( !v217 )
            goto LABEL_783;
          inited = SkmmMapDataTransfer(v217, *(_QWORD *)(v4 + 16), 1, (unsigned int)v554, 0);
          if ( inited < 0 )
            goto LABEL_1253;
          v218 = *(_QWORD *)v554;
          v219 = *(unsigned int *)(*(_QWORD *)v554 + 40LL);
          Pool = (void *)SkAllocatePool(512, v219, 1920226128);
          v221 = (ULONG_PTR)Pool;
          if ( !Pool )
            goto LABEL_537;
          memmove(Pool, *(const void **)(v218 + 24), v219);
          SkmmUnmapDataTransfer(v218);
          if ( (_DWORD)v219 == 296 )
            inited = SkeStartProcessor(v221);
          else
            inited = -1073741811;
          RtlpHpFreeHeap(qword_14015A9A0, v221);
          goto LABEL_1253;
        case 3:
          v222 = *(_QWORD *)(v4 + 24);
          v223 = *(_DWORD *)(v4 + 8);
          v224 = *(_QWORD *)(v4 + 16);
          v559 = 0;
          LODWORD(v556) = v223;
          v600 = 0;
          if ( v222
            && (v225 = SkmmMapDataTransfer(v222, *(_QWORD *)(v4 + 32), 2, (unsigned int)&v559, 0), v223 = v556,
                                                                                                   v225 >= 0) )
          {
            v226 = *(_QWORD *)(v559 + 24);
            v227 = *(_DWORD *)(v559 + 40);
          }
          else
          {
            v226 = v600;
            v227 = DWORD2(v600);
          }
          if ( _InterlockedExchange(&SkiProcessorStartupLock, 1) )
          {
            inited = -1073741790;
            goto LABEL_548;
          }
          if ( v223 >= (unsigned int)SkeNumberProcessors )
          {
            inited = -1073741811;
            goto LABEL_568;
          }
          v228 = SkeProcessorBlock[v223];
          if ( !v223 )
            goto LABEL_557;
          v229 = v224 >> 12;
          *(_QWORD *)v554 = *(_QWORD *)(v228 + 624);
          inited = SkiProtectProcessorStructure(*(_QWORD *)v554, v229, 1);
          if ( inited < 0 || (inited = SkpgVerifyPage(*(_QWORD *)v554, 0x80000000LL, 0, v230), inited >= 0) )
          {
            if ( inited >= 0 )
            {
LABEL_557:
              if ( v226 && v227 >= 0x4D0 )
              {
                *(_QWORD *)(v228 + 2528) = v226;
                *(_DWORD *)(v228 + 2536) = v227;
              }
              _InterlockedIncrement(&SkiNumberReadyProcessors);
              if ( SkiNumberReadyProcessors == (_DWORD)SkeNumberProcessors && (ShvlpFlags & 4) == 0 )
              {
                v231 = 0;
                do
                {
                  LODWORD(v556) = v231;
                  while ( v231 < 0x800 && _bittest(&SkeActiveProcessorsVp[(unsigned __int64)v231 >> 5], v231 & 0x1F) )
                  {
                    v232 = v231++ == -1;
                    LODWORD(v556) = v231;
                    if ( v232 )
                      goto LABEL_567;
                  }
                  ExceptionList = KeGetPcr()->NtTib.ExceptionList;
                  *(_OWORD *)v561 = 0;
                  LODWORD(Src) = 0;
                  while ( 1 )
                  {
                    v232 = !_BitScanForward(&v234, HIDWORD(ExceptionList[8].Next));
                    LODWORD(Src) = v234;
                    if ( v232 )
                      break;
                    if ( _interlockedbittestandreset((volatile signed __int32 *)&ExceptionList[8].Next + 1, v234) )
                    {
                      *(_QWORD *)v554 = BYTE4(v561[0]);
                      goto LABEL_576;
                    }
                  }
                  *(_QWORD *)v554 = KeGetCurrentIrql();
                  __writecr8(0xFu);
                  ExceptionList = KeGetPcr()->NtTib.ExceptionList;
                  v234 = 4;
                  LODWORD(Src) = 4;
LABEL_576:
                  v235 = (char *)ExceptionList[8].Handler + 4096 * v234;
                  memset_0(v235 + 13, 0, 0xE3u);
                  *(_QWORD *)v235 = -1;
                  v235[12] = 1;
                  *((_DWORD *)v235 + 2) = v231;
                  ShvlpInitializeVpContext(KeGetPcr()->NtTib.ExceptionList, 0, v235 + 16);
                  v236 = *(_QWORD *)((((unsigned __int64)ShvlZeroPage >> 9) & 0x7FFFFFFFF8LL) - 0x98000000000LL)
                       & 0xFFFFFFFFFF000LL;
                  *((_DWORD *)v235 + 54) = v236 + ((unsigned __int16)ShvlZeroPage & 0xFFF);
                  *((_DWORD *)v235 + 55) = HIDWORD(v236);
                  v237 = (int)ShvlpInitiateVariableHypercall(15, (_DWORD)v235, 0, 0, 0, 0);
                  if ( (unsigned int)Src >= 4 )
                    SkeLowerIrql(LOBYTE(v554[0]));
                  else
                    _interlockedbittestandset((volatile signed __int32 *)&ExceptionList[8].Next + 1, (unsigned int)Src);
                  if ( (_DWORD)v237 == -1070268402 )
                    break;
                  if ( (v237 & 0x80000000) != 0LL )
                    SkeBugCheckEx(0x5Cu, 0x56534Du, 2u, v237, 0);
                  v231 = v556 + 1;
                }
                while ( (int)v556 + 1 >= (unsigned int)v556 );
LABEL_567:
                SkeProcessorsInitComplete = 1;
              }
            }
          }
          else
          {
            SkiProtectProcessorStructure(*(_QWORD *)v554, v229, 0);
          }
LABEL_568:
          SkiProcessorStartupLock = 0;
          if ( inited >= 0 )
          {
            *(_DWORD *)(v4 + 16) = BYTE12(v600);
            if ( v559 )
              RtlpHpFreeHeap(qword_14015A9A0, v559);
            goto LABEL_1253;
          }
LABEL_548:
          if ( v559 )
            SkmmUnmapDataTransfer(v559);
          goto LABEL_1253;
        case 4:
          if ( MEMORY[0xFFFFF78000000030] )
            goto LABEL_409;
          wcscpy_s((wchar_t *)0xFFFFF78000000030LL, 0x104u, (const wchar_t *)(SkNtosUserSharedData + 48));
          SkpgRegisterTraceLog(0, 0);
          inited = SkpgConnect(0, 0, 1);
          if ( inited < 0 )
            goto LABEL_1254;
          v215 = *(_QWORD *)(v4 + 16);
          v216 = *(_QWORD *)(v4 + 8);
          if ( _InterlockedCompareExchange(&SkpspSystemDllRegistered, 1, 0) )
            SkeBugCheckEx(0x5Fu, 0x56534Du, 0x446C6Cu, 0, 0);
          if ( SkpKeepsNoSecrets )
          {
            inited = 0;
            goto LABEL_1253;
          }
          inited = SkpspRegisterSystemDll(v216, &SkpspNativeDllInfo, PsIumSystemProcess + 168);
          if ( inited >= 0 )
          {
            if ( !v215 )
              goto LABEL_532;
            inited = SkpspRegisterSystemDll(v215, &SkpspEnclaveRuntimeDllInfo, &SkpspEnclaveInfo);
            if ( inited >= 0 )
              goto LABEL_532;
          }
          goto LABEL_1253;
        case 5:
          if ( _InterlockedCompareExchange(&IumpSystemProcessRegistered, 0, 1) )
            goto LABEL_516;
          v212 = *(_QWORD *)(v4 + 8);
          if ( !v212 )
            goto LABEL_783;
          v213 = *(_QWORD *)(v4 + 16);
          if ( !v213 )
            goto LABEL_783;
          if ( _InterlockedCompareExchange64((volatile signed __int64 *)(PsIumSystemProcess + 56), v212, 0) )
          {
            inited = -1073741811;
          }
          else
          {
            LOBYTE(v212) = 1;
            *(_QWORD *)(PsIumSystemProcess + 48) = v213;
            Handle = SkobCreateHandle(PsIumSystemProcess, v212, 0, v4 + 24);
            if ( Handle < 0 )
              inited = Handle;
          }
          goto LABEL_1253;
        case 6:
          v29 = (size_t *)(v4 + 16);
          if ( SkpKeepsNoSecrets )
          {
            inited = -1073741790;
          }
          else
          {
            v30 = *v29;
            v31 = *(_QWORD *)(v4 + 8);
            v32 = SkAllocatePool(512, 536, 543842895);
            if ( v32 )
            {
              *(_BYTE *)(v32 + 8) = 0;
              *(_QWORD *)v32 = 1397444418;
              v33 = (_QWORD *)(v32 + 32);
              *(_QWORD *)(v32 + 24) = 1;
              *(_QWORD *)(v32 + 16) = &SkpsProcessType;
              memset_0((void *)(v32 + 32), 0, 0x1F8u);
              v33[6] = v31;
              v33[3] = v33 + 2;
              v33[2] = v33 + 2;
              inited = SkmmCreateProcessAddressSpace(v33, 0, v30);
              if ( inited >= 0 )
              {
                v33[30] = 0;
                v33[48] = v33 + 47;
                v33[47] = v33 + 47;
                LOBYTE(v34) = 1;
                v35 = SkobCreateHandle(v33, v34, 0, &v557);
                v6 = (size_t)v557;
                inited = v35;
              }
              SkobDereferenceObject(v33);
            }
            else
            {
              inited = -1073741670;
            }
          }
          if ( (Microsoft_Windows_IsolatedUserModeEnableBits & 1) != 0 )
            McTemplateK0xqqz_EtwWriteTransfer(v24, (unsigned int)IumProcessCreate, v28, 0, 0, inited, 0);
          if ( inited < 0 )
            goto LABEL_1254;
          *v29 = v6;
          goto LABEL_624;
        case 7:
          v36 = *(_QWORD *)(v4 + 48);
          v37 = 0;
          LOBYTE(v556) = 0;
          v557 = 0;
          if ( !v36 )
            goto LABEL_95;
          inited = SkmmMapDataTransfer(v36, *(_QWORD *)(v4 + 56), 1, (unsigned int)&v557, 0);
          if ( inited < 0 )
            goto LABEL_102;
          v37 = v557;
          v6 = *((unsigned int *)v557 + 10);
          if ( (_DWORD)v6 != 8 && (unsigned int)(v6 - 24) > 0x6F )
          {
            inited = -1073741811;
            goto LABEL_99;
          }
          v38 = (_QWORD *)SkAllocatePool(512, *((unsigned int *)v557 + 10), 1349807689);
          v5 = v38;
          if ( !v38 )
          {
            inited = -1073741670;
            goto LABEL_99;
          }
          memset_0(v38, 0, v6);
          memmove(v5, *((const void **)v37 + 3), v6);
          SkmmUnmapDataTransfer(v37);
          v37 = 0;
          if ( v6 == 8 )
            goto LABEL_95;
          if ( (v6 & 7) != 0 || v6 - 24 > 0x70 )
            goto LABEL_94;
          v39 = 0;
          v40 = (unsigned int)(v6 - 8) >> 3;
          v41 = 0;
          v42 = 0;
          if ( !v40 )
            goto LABEL_91;
          do
          {
            v43 = v41;
            v44 = HIDWORD(v5[v41 + 1]);
            if ( (_BYTE)v44 || v44 >= 0x100 || (v5[v43 + 1] & 0xF0000000LL) != 0 )
              goto LABEL_94;
            v45 = 0;
            while ( 1 )
            {
              v4 = *(_QWORD *)v554;
              if ( BYTE2(v5[v43 + 1]) == 20 )
                v39 = 1;
              if ( LODWORD(v5[v43 + 1]) == **((_DWORD **)&`IsTrustletCreateAttributeWellFormed'::`2'::KnownAttributeTypes
                                            + v45) )
                break;
              v45 = (unsigned int)(v45 + 1);
              if ( (unsigned int)v45 >= 5 )
              {
                if ( (_DWORD)v45 == 5 )
                  goto LABEL_94;
                break;
              }
            }
            v41 = (unsigned int)BYTE1(v5[v43 + 1]) + (_DWORD)v41 + 1;
            ++v42;
          }
          while ( (unsigned int)v41 < v40 );
          if ( v42 > 4 )
            goto LABEL_94;
LABEL_91:
          if ( (_DWORD)v41 != v40 || !v39 && !*v5 )
          {
LABEL_94:
            inited = -1073741811;
LABEL_98:
            RtlpHpFreeHeap(qword_14015A9A0, (ULONG_PTR)v5);
            goto LABEL_99;
          }
LABEL_95:
          v46 = SkpsInitializeProcess(
                  *(_QWORD *)(v4 + 8),
                  *(_QWORD *)(v4 + 24),
                  *(_QWORD *)(v4 + 16),
                  *(_QWORD *)(v4 + 32),
                  *(_QWORD *)(v4 + 40),
                  v5,
                  (unsigned int)v6,
                  (__int64)&v556);
          v564 = 0;
          inited = v46;
          if ( v46 >= 0 )
            v564 = ((_BYTE)v556 != 0) + 1LL;
          if ( v5 )
            goto LABEL_98;
LABEL_99:
          if ( v37 )
          {
            v47 = *((_WORD *)v37 + 5);
            SkmmUnmapMdl(v37);
            if ( (v47 & 0x100) == 0 )
              RtlpHpFreeHeap(qword_14015A9A0, (ULONG_PTR)v37);
          }
LABEL_102:
          if ( inited < 0 )
            goto LABEL_1254;
          *(_QWORD *)(v4 + 16) = v564;
          goto LABEL_624;
        case 8:
          Thread = SkpsCreateThread(
                     *(_QWORD *)(v4 + 8),
                     *(_QWORD *)(v4 + 16),
                     *(_QWORD *)(v4 + 24),
                     *(_QWORD *)(v4 + 32),
                     *(_QWORD *)(v4 + 40),
                     *(_QWORD *)(v4 + 48),
                     *(_QWORD *)(v4 + 56),
                     v4 + 16);
          goto LABEL_1252;
        case 9:
          v49 = SkeReferenceThread(*(unsigned int *)(v4 + 8), *(_QWORD *)(v4 + 16));
          v50 = v49;
          if ( v49 )
          {
            v51 = *(_DWORD **)(v49 + 72);
            if ( !v51 || (*v51 & 0x200) != 0 )
            {
              inited = -1073741811;
            }
            else if ( (*(_DWORD *)(v49 + 172) & 2) == 0 )
            {
              if ( (*v51 & 0x10) != 0 )
                _InterlockedOr((volatile signed __int32 *)(v49 + 172), 2u);
              else
                SkiTerminateAllThreads(v51, 0, 0);
            }
            v52 = *(_QWORD *)(v50 + 216);
            while ( (v52 & 1) != 0 )
            {
              v53 = v52;
              v52 = _InterlockedCompareExchange64((volatile signed __int64 *)(v50 + 216), v52 - 2, v52);
              if ( v52 == v53 )
                goto LABEL_1253;
            }
LABEL_118:
            if ( _InterlockedExchangeAdd64((volatile signed __int64 *)v52, 0xFFFFFFFFFFFFFFFFuLL) == 1 )
              SkeAlertThreadByThreadId(*(_QWORD *)(v52 + 8));
            goto LABEL_1253;
          }
          inited = -1073741275;
          goto LABEL_1254;
        case 10:
          if ( !KeGetCurrentIrql() && *(_BYTE *)(a2 + 297) )
            SkpsTerminateThread();
LABEL_516:
          inited = -1073741811;
          goto LABEL_1254;
        case 11:
          Thread = SkpsRundownProcess(*(_QWORD *)(v4 + 8));
          goto LABEL_1252;
        case 12:
          v61 = *(_QWORD *)(v4 + 8);
          LOBYTE(v28) = 1;
          v557 = 0;
          inited = SkobReferenceObjectByHandle(v61, 0, v28, (unsigned int)&SkpsProcessType, (__int64)&v557, 0);
          if ( inited < 0 )
            goto LABEL_158;
          v62 = v557;
          if ( (*(_DWORD *)v557 & 2) == 0 )
          {
            inited = -1073740007;
            goto LABEL_157;
          }
          v63 = *((_QWORD *)v557 + 10);
          do
          {
            if ( (v63 & 1) == 0 || v63 == -1 )
              goto LABEL_156;
            v64 = v63;
            v63 = _InterlockedCompareExchange64((volatile signed __int64 *)v62 + 10, v63 + 2, v63);
          }
          while ( v63 != v64 );
          LODWORD(Src) = *(_DWORD *)v62;
          if ( ((unsigned __int16)Src & 0x400) != 0 )
          {
            v65 = *((_QWORD *)v62 + 10);
            while ( (v65 & 1) != 0 )
            {
              v66 = v65;
              v65 = _InterlockedCompareExchange64((volatile signed __int64 *)v62 + 10, v65 - 2, v65);
              if ( v65 == v66 )
                goto LABEL_156;
            }
            if ( _InterlockedExchangeAdd64((volatile signed __int64 *)v65, 0xFFFFFFFFFFFFFFFFuLL) == 1 )
              SkeAlertThreadByThreadId(*(_QWORD *)(v65 + 8));
LABEL_156:
            inited = -1073741816;
            goto LABEL_157;
          }
          v5 = v62;
          inited = 0;
LABEL_157:
          SkobDereferenceObject(v62);
LABEL_158:
          if ( inited < 0 )
            goto LABEL_1254;
          if ( (*(_DWORD *)v5 & 0x1000) != 0 )
            goto LABEL_183;
          v67 = KeGetPcr()->NtTib.StackBase;
          v68 = 0;
          LODWORD(v556) = 0;
          v69 = 0;
          *(_QWORD *)v554 = 4;
          if ( v5 != (_QWORD *)1 )
            v69 = v5;
          v70 = v67[10];
          v67[10] = v69;
          if ( v69 )
            ((void (*)(void))SkeSelectProcessAddressSpace)();
          pbInput = (PUCHAR)v554;
          if ( !v70 )
            v70 = 1;
          Policy = SkpspFindPolicy((_DWORD)v5, 2, 7, (unsigned int)&v556, (__int64)pbInput);
          if ( Policy < 0 || (unsigned int)v556 >= 4 )
          {
            DbgPrint(
              "%hs: SkpspFindPolicy returned 0x%x and DebugEnable is %d.\n",
              "SkpsIsProcessDebuggingEnabled",
              Policy,
              v556);
          }
          else if ( (_DWORD)v556 )
          {
            if ( (_DWORD)v556 == 1 )
            {
              v68 = 1;
            }
            else if ( (_DWORD)v556 == 2 )
            {
              v68 = (unsigned int)SkIsSecureBootEnabled() == -2143092730;
            }
            else
            {
              v68 = BYTE1(*(_DWORD *)v5) & 1;
            }
          }
          v72 = KeGetPcr()->NtTib.StackBase;
          if ( v70 == 1 )
          {
            v72[10] = 0;
          }
          else
          {
            v72[10] = v70;
            SkeSelectProcessAddressSpace(v70);
          }
          if ( v68 )
          {
LABEL_183:
            SkpsEnableDebugging(v5, *(unsigned __int8 *)(v4 + 16));
            inited = 0;
          }
          else
          {
            inited = -1073741790;
          }
          v52 = v5[10];
          while ( (v52 & 1) != 0 )
          {
            v73 = v52;
            v52 = _InterlockedCompareExchange64(v5 + 10, v52 - 2, v52);
            if ( v52 == v73 )
              goto LABEL_1253;
          }
          goto LABEL_118;
        case 13:
          v82 = SkeReferenceThread(*(unsigned int *)(v4 + 8), *(_QWORD *)(v4 + 16));
          v83 = v82;
          if ( v82 )
          {
            *(_QWORD *)(v4 + 16) = *(_QWORD *)(v82 + 160);
            v80 = *(_QWORD *)(v82 + 216);
            while ( (v80 & 1) != 0 )
            {
              v84 = v80;
              v80 = _InterlockedCompareExchange64((volatile signed __int64 *)(v83 + 216), v80 - 2, v80);
              if ( v80 == v84 )
                goto LABEL_624;
            }
LABEL_215:
            if ( _InterlockedExchangeAdd64((volatile signed __int64 *)v80, 0xFFFFFFFFFFFFFFFFuLL) == 1 )
              SkeAlertThreadByThreadId(*(_QWORD *)(v80 + 8));
            goto LABEL_624;
          }
          inited = -1073741275;
          goto LABEL_1254;
        case 14:
        case 15:
          v85 = KeGetPcr()->NtTib.StackBase;
          v559 = 0;
          LODWORD(v556) = 0;
          v557 = 0;
          v86 = (_DWORD *)v85[9];
          Src = 0;
          if ( v86 && v86 != (_DWORD *)PsIumSystemProcess && (*v86 & 0x10) != 0 )
          {
            v87 = *(unsigned __int16 *)(v4 + 2);
            v88 = SkmmMapDataTransfer(
                    *(_QWORD *)(v4 + 8),
                    *(_QWORD *)(v4 + 16),
                    (unsigned int)(v87 != 15) + 1,
                    (unsigned int)&v557,
                    0);
            v89 = v557;
            inited = v88;
            if ( v88 >= 0 )
            {
              v90 = SkpsValidateExtendedContext(*((void **)v557 + 3), *((unsigned int *)v557 + 10), (__int64)&Src);
              v91 = v559;
              inited = v90;
              if ( v90 >= 0 )
              {
                v92 = Src;
                inited = SkpsGetSetContext((ULONG_PTR)v85);
                if ( inited >= 0 && v87 == 14 )
                  memmove(*((void **)v89 + 3), v92, (unsigned int)(v556 + v91 - (_DWORD)v92));
              }
              if ( v91 )
                RtlpHpFreeHeap(qword_14015A9A0, v91);
            }
            if ( v89 )
            {
              v93 = *((_WORD *)v89 + 5);
              SkmmUnmapMdl(v89);
              if ( (v93 & 0x100) == 0 )
                RtlpHpFreeHeap(qword_14015A9A0, (ULONG_PTR)v89);
            }
          }
          else
          {
            inited = -1073741823;
          }
          goto LABEL_1253;
        case 16:
          v94 = *(_QWORD *)(v4 + 8);
          LOBYTE(v28) = 1;
          v557 = 0;
          inited = SkobReferenceObjectByHandle(v94, 0, v28, (unsigned int)&SkpsProcessType, (__int64)&v557, 0);
          if ( inited < 0 )
            goto LABEL_244;
          v95 = v557;
          if ( (*(_DWORD *)v557 & 2) == 0 )
          {
            inited = -1073740007;
            goto LABEL_243;
          }
          v96 = *((_QWORD *)v557 + 10);
          do
          {
            if ( (v96 & 1) == 0 || v96 == -1 )
              goto LABEL_242;
            v97 = v96;
            v96 = _InterlockedCompareExchange64((volatile signed __int64 *)v95 + 10, v96 + 2, v96);
          }
          while ( v96 != v97 );
          LODWORD(Src) = *(_DWORD *)v95;
          if ( ((unsigned __int16)Src & 0x400) != 0 )
          {
            v98 = *((_QWORD *)v95 + 10);
            while ( (v98 & 1) != 0 )
            {
              v99 = v98;
              v98 = _InterlockedCompareExchange64((volatile signed __int64 *)v95 + 10, v98 - 2, v98);
              if ( v98 == v99 )
                goto LABEL_242;
            }
            if ( _InterlockedExchangeAdd64((volatile signed __int64 *)v98, 0xFFFFFFFFFFFFFFFFuLL) == 1 )
              SkeAlertThreadByThreadId(*(_QWORD *)(v98 + 8));
LABEL_242:
            inited = -1073741816;
            goto LABEL_243;
          }
          v5 = v95;
          inited = 0;
LABEL_243:
          SkobDereferenceObject(v95);
LABEL_244:
          if ( inited < 0 )
            goto LABEL_1254;
          SkpsSendDebugAttachNotifications(v5, *(_QWORD *)(v4 + 16), *(_QWORD *)(v4 + 24));
          v52 = v5[10];
          while ( (v52 & 1) != 0 )
          {
            v100 = v52;
            v52 = _InterlockedCompareExchange64(v5 + 10, v52 - 2, v52);
            if ( v52 == v100 )
              goto LABEL_1253;
          }
          goto LABEL_118;
        case 17:
          inited = SkpsReferenceProcessByHandle(*(_QWORD *)(v4 + 8), 0, &Src, 255);
          if ( inited < 0 )
            goto LABEL_1254;
          v153 = SkmmMapDataTransfer(*(_QWORD *)(v4 + 24), *(_QWORD *)(v4 + 32), 2, (unsigned int)&v559, 0);
          v154 = Src;
          inited = v153;
          if ( v153 >= 0 )
          {
            v155 = v559;
            v156 = *(_QWORD *)(v4 + 16);
            v157 = (int)Src;
            v557 = 0;
            v158 = *(_DWORD *)(v559 + 40);
            v159 = *(_QWORD *)(v559 + 24);
            *(_QWORD *)v554 = 0;
            Src = 0;
            v559 = 0;
            inited = SkmiObtainLockedImageVad(
                       v157,
                       v156,
                       (unsigned int)&Src,
                       (unsigned int)&v559,
                       (__int64)&v557,
                       (__int64)v554);
            if ( inited >= 0 )
            {
              inited = SkGetEtwDebugId((_DWORD)v557, v554[0], v159, v158, v4 + 40);
              SkmiUnlockVad(v559);
              SkmiDereferenceVad(v559);
              SkiAttachProcess(Src);
            }
            SkmmUnmapDataTransfer(v155);
          }
          v52 = v154[10];
          while ( (v52 & 1) != 0 )
          {
            v160 = v52;
            v52 = _InterlockedCompareExchange64(v154 + 10, v52 - 2, v52);
            if ( v52 == v160 )
              goto LABEL_1253;
          }
          goto LABEL_118;
        case 18:
          v101 = *(_QWORD *)(v4 + 8);
          LOBYTE(v28) = 1;
          v557 = 0;
          inited = SkobReferenceObjectByHandle(v101, 0, v28, (unsigned int)&SkpsProcessType, (__int64)&v557, 0);
          if ( inited < 0 )
            goto LABEL_265;
          v102 = v557;
          if ( (*(_DWORD *)v557 & 2) == 0 )
          {
            inited = -1073740007;
            goto LABEL_264;
          }
          v103 = *((_QWORD *)v557 + 10);
          do
          {
            if ( (v103 & 1) == 0 || v103 == -1 )
              goto LABEL_263;
            v104 = v103;
            v103 = _InterlockedCompareExchange64((volatile signed __int64 *)v102 + 10, v103 + 2, v103);
          }
          while ( v103 != v104 );
          LODWORD(Src) = *(_DWORD *)v102;
          if ( ((unsigned __int16)Src & 0x400) != 0 )
          {
            v105 = *((_QWORD *)v102 + 10);
            while ( (v105 & 1) != 0 )
            {
              v106 = v105;
              v105 = _InterlockedCompareExchange64((volatile signed __int64 *)v102 + 10, v105 - 2, v105);
              if ( v105 == v106 )
                goto LABEL_263;
            }
            if ( _InterlockedExchangeAdd64((volatile signed __int64 *)v105, 0xFFFFFFFFFFFFFFFFuLL) == 1 )
              SkeAlertThreadByThreadId(*(_QWORD *)(v105 + 8));
LABEL_263:
            inited = -1073741816;
            goto LABEL_264;
          }
          v5 = v102;
          inited = 0;
LABEL_264:
          SkobDereferenceObject(v102);
LABEL_265:
          if ( inited < 0 )
            goto LABEL_1254;
          if ( (int)SkmmMapDataTransfer(*(_QWORD *)(v4 + 16), *(_QWORD *)(v4 + 24), 2, (unsigned int)&v559, 0) >= 0 )
          {
            LODWORD(v556) = 0;
            v107 = *(_DWORD *)(v559 + 40);
            v568 = *(_QWORD *)(v559 + 24);
            LODWORD(Src) = v107;
            _InterlockedAnd((volatile signed __int32 *)v5, 0xFFFFFEFF);
            while ( 1 )
            {
              inited = BCryptGenRandom(0, (PUCHAR)v5 + 392, 8u, 2u);
              if ( inited < 0 )
                break;
              if ( v5[49] )
              {
                v108 = (int)Src;
                pPaddingInfo[0] = L"SHA1";
                pPaddingInfo[1] = 0;
                pPaddingInfo[2] = 0;
                v557 = 0;
                *(_QWORD *)v554 = 0;
                *(_OWORD *)v561 = 0;
                if ( (unsigned int)Src > 0x1C )
                {
                  inited = SkpsGetTrustletCrashdumpKey(v5, v554, &v557, v561);
                  if ( inited >= 0 )
                  {
                    phKey = 0;
                    inited = BCryptImportKeyPair(hAlgorithm, 0, L"RSAPUBLICBLOB", &phKey, v557, v554[0], 0);
                    if ( inited >= 0 )
                    {
                      v109 = phKey;
                      v110 = v108 - 28;
                      v111 = v568;
                      pcbResult = 0;
                      inited = BCryptEncrypt(
                                 phKey,
                                 (PUCHAR)v5 + 392,
                                 8u,
                                 pPaddingInfo,
                                 0,
                                 0,
                                 (PUCHAR)(v568 + 28),
                                 v110,
                                 &pcbResult,
                                 4u);
                      if ( inited >= 0 )
                      {
                        v112 = *(_OWORD *)v561;
                        *(_QWORD *)v111 = 1;
                        *(_OWORD *)(v111 + 8) = v112;
                        *(_DWORD *)(v111 + 24) = 5;
                        LODWORD(v556) = pcbResult + 28;
                      }
                      if ( v109 )
                        BCryptDestroyKey(v109);
                      v3 = v556;
                    }
                  }
                  if ( v557 )
                    RtlpHpFreeHeap(qword_14015A9A0, (ULONG_PTR)v557);
                }
                else
                {
                  inited = -1073741789;
                  v3 = 540;
                }
                break;
              }
            }
            SkmmUnmapDataTransfer(v559);
            *(_QWORD *)(v4 + 16) = v3;
          }
          else
          {
            inited = -1073741811;
          }
          v52 = v5[10];
          while ( (v52 & 1) != 0 )
          {
            v113 = v52;
            v52 = _InterlockedCompareExchange64(v5 + 10, v52 - 2, v52);
            if ( v52 == v113 )
              goto LABEL_1253;
          }
          goto LABEL_118;
        case 19:
          inited = SkpsReferenceProcessByHandle(*(_QWORD *)(v4 + 8), 0, &Src, 255);
          if ( inited < 0 )
            goto LABEL_1254;
          inited = -1073741790;
          v114 = Src;
          if ( *(_DWORD *)(v4 + 16) == 8 )
          {
            v115 = _InterlockedExchange64((volatile __int64 *)Src + 49, 0);
            if ( v115 )
            {
              if ( *(_QWORD *)(v4 + 24) == v115 )
              {
                _InterlockedOr((volatile signed __int32 *)v114, 0x100u);
                inited = 0;
              }
            }
          }
          v52 = *((_QWORD *)v114 + 10);
          while ( (v52 & 1) != 0 )
          {
            v116 = v52;
            v52 = _InterlockedCompareExchange64((volatile signed __int64 *)v114 + 10, v52 - 2, v52);
            if ( v52 == v116 )
              goto LABEL_1253;
          }
          goto LABEL_118;
        case 20:
          v570 = &v569;
          v392 = 0;
          v569 = &v569;
          v611 = 0;
          v393 = SkAcquireSpinLockExclusive(&SkpsProcessListLock);
          v395 = (__int64 *)SkpsProcessList;
          v396 = v393;
          if ( (__int64 *)SkpsProcessList == &SkpsProcessList )
            goto LABEL_907;
          while ( 1 )
          {
            v397 = v395 - 31;
            v398 = *(v395 - 21);
            do
            {
              if ( (v398 & 1) == 0 || v398 == -1 )
                goto LABEL_904;
              v399 = v398;
              v398 = _InterlockedCompareExchange64(v397 + 10, v398 + 2, v398);
            }
            while ( v398 != v399 );
            if ( (int)SkpsQueryProcessAttribute(v395 - 31, (unsigned int)TrustletType_MailboxKey, v394, &v611, 16) >= 0 )
            {
              v558 = 0;
              v558 = (_QWORD)v611 == *(_QWORD *)(v4 + 24) && *((_QWORD *)&v611 + 1) == *(_QWORD *)(v4 + 32);
              if ( v558 )
                break;
            }
            v394 = v397[10];
            while ( (v394 & 1) != 0 )
            {
              v400 = v394;
              v394 = _InterlockedCompareExchange64(v397 + 10, v394 - 2, v394);
              if ( v394 == v400 )
                goto LABEL_904;
            }
            if ( _InterlockedExchangeAdd64((volatile signed __int64 *)v394, 0xFFFFFFFFFFFFFFFFuLL) == 1 )
            {
              v401 = v570;
              if ( *v570 != &v569 )
                goto LABEL_936;
              v397[11] = (__int64)&v569;
              v397[12] = (__int64)v401;
              *v401 = v397 + 11;
              v570 = (_QWORD **)(v397 + 11);
            }
LABEL_904:
            v395 = (__int64 *)*v395;
            if ( v395 == &SkpsProcessList )
              goto LABEL_907;
          }
          v392 = v395 - 31;
LABEL_907:
          v402 = 0;
          SkpsProcessListLock = 0;
          SkTrackSpinLockRelease();
          SkeLowerIrql(v396);
          while ( 1 )
          {
            v403 = v569;
            if ( v569 == &v569 )
              break;
            v404 = *v569;
            if ( *(_QWORD **)(*v569 + 8LL) != v569 )
              goto LABEL_936;
            v405 = (_QWORD *)v569[1];
            if ( (_QWORD *)*v405 != v569 )
              goto LABEL_936;
            *v405 = v404;
            *(_QWORD *)(v404 + 8) = v405;
            SkeAlertThreadByThreadId(*(_QWORD *)(*(v403 - 1) + 8LL));
          }
          if ( !v392 )
          {
            inited = -1073741772;
            goto LABEL_1253;
          }
          v406 = *(_QWORD *)(v4 + 40);
          if ( v406 && v392[54] != v406 )
          {
            SkReleaseRundownProtection(v392 + 10, 0);
            inited = -1073741772;
            goto LABEL_1253;
          }
          v407 = *(_QWORD *)(v4 + 8);
          inited = -1073741823;
          *(_QWORD *)v554 = 0;
          if ( !v407 )
            goto LABEL_919;
          inited = SkmmMapDataTransfer(v407, *(_QWORD *)(v4 + 16), 2, (unsigned int)v554, 0);
          if ( inited < 0 )
            goto LABEL_919;
          v408 = *(_QWORD *)v554;
          v409 = *(_DWORD *)(v4 + 48);
          v410 = *(unsigned int *)(*(_QWORD *)v554 + 40LL);
          if ( v409 >= 8 )
          {
            inited = -1073741446;
            goto LABEL_938;
          }
          if ( v392 == (__int64 *)1 || (*(_DWORD *)v392 & 0x1600) != 0 || (*(_DWORD *)v392 & 2) == 0 )
          {
            inited = -1073741811;
            goto LABEL_938;
          }
          v561[0] = *(void **)(*(_QWORD *)v554 + 24LL);
          inited = -1073741181;
          SkpspLockProcessExclusive(v392);
          v411 = v392[57];
          if ( (__int64 *)v411 == v392 + 57 )
            goto LABEL_934;
          while ( 1 )
          {
            v402 = v411;
            if ( *(_DWORD *)(v411 + 16) == v409 )
              break;
            v411 = *(_QWORD *)v411;
            if ( (__int64 *)v411 == v392 + 57 )
            {
              SkpspUnlockProcessExclusive(v392);
              goto LABEL_938;
            }
          }
          v412 = *(unsigned int *)(v411 + 20);
          if ( v412 > v410 )
          {
            v410 = (unsigned int)v412;
            inited = -1073741789;
            SkpspUnlockProcessExclusive(v392);
            goto LABEL_938;
          }
          v413 = *(_QWORD *)v411;
          if ( *(_QWORD *)(*(_QWORD *)v411 + 8LL) == v411 )
          {
            v414 = *(ULONG_PTR **)(v411 + 8);
            if ( *v414 == v411 )
            {
              *v414 = v413;
              *(_QWORD *)(v413 + 8) = v414;
LABEL_934:
              SkpspUnlockProcessExclusive(v392);
              if ( v402 )
              {
                memmove(v561[0], (const void *)(v402 + 24), *(unsigned int *)(v402 + 20));
                v410 = *(unsigned int *)(v402 + 20);
                RtlpHpFreeHeap(qword_14015A9A0, v402);
                inited = 0;
              }
LABEL_938:
              *(_QWORD *)(v4 + 16) = v410;
              SkmmUnmapDataTransfer(v408);
LABEL_919:
              SkReleaseRundownProtection(v392 + 10, 0);
LABEL_1253:
              if ( inited >= 0 )
                goto LABEL_624;
LABEL_1254:
              if ( v560[0] == 208 )
              {
                SkeBugCheckStatus = inited;
              }
              else if ( v560[0] != 1 )
              {
                goto LABEL_624;
              }
              SkeBugCheckEx(0x5Fu, 0x56534Du, v560[0], 0, inited);
            }
          }
          goto LABEL_936;
        case 21:
          v415 = *(_QWORD *)(v4 + 8);
          v416 = 0;
          v417 = SkAcquireSpinLockExclusive(&SkpsProcessListLock);
          v418 = (__int64 *)SkpsProcessList;
          v419 = v417;
          if ( (__int64 *)SkpsProcessList == &SkpsProcessList )
            goto LABEL_946;
          while ( v418[23] != v415 )
          {
            v418 = (__int64 *)*v418;
            if ( v418 == &SkpsProcessList )
              goto LABEL_946;
          }
          v420 = SkAcquireRundownProtection(v418 - 21);
          v416 = v421;
          if ( !v420 )
            v416 = 0;
LABEL_946:
          SkpsProcessListLock = 0;
          SkTrackSpinLockRelease();
          SkeLowerIrql(v419);
          if ( v416 )
            SkReleaseRundownProtection(v416 + 80, 0);
          inited = 0;
          *(_QWORD *)(v4 + 16) = v416 != 0;
          goto LABEL_624;
        case 22:
          Thread = SkmmCreateSecureAllocation(*(_QWORD *)(v4 + 8), v4 + 16);
          goto LABEL_1252;
        case 23:
          v338 = *(_QWORD *)(v4 + 32);
          v339 = *(_QWORD *)(v4 + 24);
          v340 = *(_QWORD *)(v4 + 16);
          v341 = *(_QWORD *)(v4 + 8);
          *(_QWORD *)v554 = 0;
          inited = SkmmMapDataTransfer(v339, v338, 1, (unsigned int)v554, 0);
          if ( inited >= 0 )
          {
            v343 = *(_QWORD *)v554;
            LOBYTE(v342) = 1;
            *(_QWORD *)cbInput = 0;
            *(_QWORD *)v554 = 0;
            v344 = *(unsigned int *)(v343 + 40);
            v345 = *(const void **)(v343 + 24);
            inited = SkobReferenceObjectByHandle(
                       v341,
                       0,
                       v342,
                       (unsigned int)&SkmiSecureAllocationType,
                       (__int64)v554,
                       0);
            if ( inited >= 0 )
            {
              v346 = KeGetPcr()->NtTib.StackBase;
              v347 = *(_QWORD *)v554;
              if ( v346 )
              {
                v348 = v346[18];
                if ( v348 )
                  --*(_WORD *)(v348 + xmmword_140167150);
              }
              if ( _interlockedbittestandset64((volatile signed __int32 *)(v347 + 16), 0) )
                RtlpAcquireSRWLockExclusiveContended(v347 + 16);
              if ( *(_QWORD *)v347 && v340 >= *(_QWORD *)(v347 + 24) )
              {
                v349 = *(_QWORD *)(v347 + 8) << 12;
                if ( v340 >= v349 || (v350 = v340 + v344, v340 + v344 > v349) || v350 < v340 )
                {
                  inited = -1073741811;
                }
                else
                {
                  memmove((void *)(v340 + *(_QWORD *)v347), v345, v344);
                  *(_QWORD *)(v347 + 24) = v350;
                  inited = 0;
                }
              }
              else
              {
                inited = -1073741800;
              }
              SkReleasePushLockExclusive(v347 + 16);
              v351 = KeGetPcr()->NtTib.StackBase;
              if ( v351 )
              {
                v352 = v351[18];
                if ( v352 )
                {
                  v232 = (*(_WORD *)(v352 + xmmword_140167150))++ == 0xFFFF;
                  if ( v232
                    && *(_QWORD *)(v352 + xmmword_140167160) != (_QWORD)xmmword_140167160 + v351[17]
                    && !*(_WORD *)(v352 + *((_QWORD *)&xmmword_140167150 + 1)) )
                  {
                    SkiCheckForKernelApcDelivery();
                  }
                }
              }
              SkobDereferenceObject(v347);
            }
            SkmmUnmapDataTransfer(v343);
          }
          goto LABEL_1253;
        case 24:
          v353 = *(_QWORD *)(v4 + 8);
          v354 = *(_QWORD *)(v4 + 16);
          LOBYTE(v28) = 1;
          *(_QWORD *)v554 = 0;
          inited = SkobReferenceObjectByHandle(v353, 0, v28, (unsigned int)&SkmiSecureAllocationType, (__int64)v554, 0);
          if ( inited < 0 )
            goto LABEL_1253;
          v355 = KeGetPcr()->NtTib.StackBase;
          v356 = *(_QWORD *)v554;
          if ( v355 )
          {
            v357 = v355[18];
            if ( v357 )
              --*(_WORD *)(v357 + xmmword_140167150);
          }
          if ( _interlockedbittestandset64((volatile signed __int32 *)(v356 + 16), 0) )
            RtlpAcquireSRWLockExclusiveContended(v356 + 16);
          inited = SkciCreateCodeCatalog(*(_QWORD *)v356, *(_QWORD *)(v356 + 8) << 12, v354, v4 + 16);
          if ( inited >= 0 )
          {
            *(_QWORD *)v356 = 0;
            SkobCloseHandleEx(v353, v356, 0, 0, 0);
          }
          SkReleasePushLockExclusive(v356 + 16);
          v358 = KeGetPcr()->NtTib.StackBase;
          if ( v358 )
          {
            v359 = v358[18];
            if ( v359 )
            {
              v232 = (*(_WORD *)(v359 + xmmword_140167150))++ == 0xFFFF;
              if ( v232
                && *(_QWORD *)(v359 + xmmword_140167160) != (_QWORD)xmmword_140167160 + v358[17]
                && !*(_WORD *)(v359 + *((_QWORD *)&xmmword_140167150 + 1)) )
              {
                SkiCheckForKernelApcDelivery();
              }
            }
          }
          goto LABEL_871;
        case 25:
          Thread = SkmmCreateSecureImageSection(
                     *(_QWORD *)(v4 + 8),
                     *(_QWORD *)(v4 + 16),
                     *(unsigned __int8 *)(v4 + 24),
                     *(_DWORD *)(v4 + 32),
                     *(_DWORD *)(v4 + 40),
                     v4 + 16);
          goto LABEL_1252;
        case 26:
          v365 = *(_QWORD *)(v4 + 16);
          v366 = *(_QWORD *)(v4 + 8);
          *(_QWORD *)v554 = 0;
          v599 = 0;
          v600 = 0;
          v601 = 0;
          v602 = 0;
          SkmmInitializeShortMdl(&v599, v365, 72, v4 + 24);
          LOBYTE(v367) = 1;
          inited = SkobReferenceObjectByHandle(v366, 0, v367, (unsigned int)&SkmiImageType, (__int64)v554, 0);
          if ( inited < 0 )
            goto LABEL_1253;
          v368 = SkmmMapMdl(&v599, 2);
          v356 = *(_QWORD *)v554;
          inited = v368;
          if ( v368 >= 0 )
            inited = SkciFinalizeSecureImageHash(*(_QWORD *)(*(_QWORD *)v554 + 144LL), *((_QWORD *)&v600 + 1));
          if ( (BYTE10(v599) & 1) != 0 )
            SkmmUnmapMdl(&v599);
          goto LABEL_871;
        case 27:
          Thread = SkmmFinishSecureImageValidation(
                     *(_QWORD *)(v4 + 8),
                     *(_QWORD *)(v4 + 16),
                     *(_DWORD *)(v4 + 24),
                     *(unsigned __int8 *)(v4 + 28),
                     v4 + 29,
                     v4 + 32,
                     v4 + 40,
                     v4 + 48);
          goto LABEL_1252;
        case 28:
          v377 = *(_QWORD *)(v4 + 8);
          v378 = *(_QWORD *)(v4 + 32);
          v379 = *(_QWORD *)(v4 + 24);
          LOBYTE(v28) = 1;
          *(_QWORD *)v554 = 0;
          inited = SkobReferenceObjectByHandle(v377, 0, v28, (unsigned int)&SkmiImageType, (__int64)v554, 0);
          if ( inited < 0 )
            goto LABEL_1253;
          v356 = *(_QWORD *)v554;
          if ( (**(_DWORD **)v554 & 0x20) == 0 )
          {
            SKMI_IMAGE_SECURITY(11, 0, v554[0], 0, 0);
            inited = -1073741819;
            SkobDereferenceObject(v356);
            goto LABEL_1253;
          }
          if ( (*(_DWORD *)(*(_QWORD *)v554 + 156LL) & 4) == 0 )
          {
            inited = -1073740760;
            SkobDereferenceObject(*(_QWORD *)v554);
            goto LABEL_1253;
          }
          if ( !*(_DWORD *)(*(_QWORD *)v554 + 160LL) )
          {
            inited = 0;
            SkobDereferenceObject(*(_QWORD *)v554);
            goto LABEL_1253;
          }
          inited = SkmiLockImageExclusive(*(_QWORD *)v554);
          if ( inited < 0 )
            goto LABEL_871;
          if ( *(_QWORD *)(v356 + 168) )
          {
            *(_DWORD *)(v356 + 136) = 0;
            inited = 255;
            SkobDereferenceObject(v356);
          }
          else
          {
            v380 = *(unsigned int *)(v356 + 164);
            v381 = *(_DWORD *)(v356 + 160);
            *(_QWORD *)v554 = 0;
            v559 = 0;
            v557 = 0;
            inited = SkmiCaptureAndValidateImageData(
                       v356,
                       v379,
                       v378,
                       v381,
                       0,
                       v380,
                       (__int64)v554,
                       (__int64)&v559,
                       (__int64)&v557);
            if ( inited >= 0 )
            {
              v382 = *(_QWORD *)v554;
              if ( v557 == (PUCHAR)*(unsigned int *)(*(_QWORD *)v554 + 4LL) )
              {
                v383 = (void *)SkAllocatePool(512, v557, 1346923849);
                v384 = v383;
                if ( v383 )
                {
                  memmove(v383, (const void *)v382, *(unsigned int *)(v382 + 4));
                  *(_QWORD *)(v356 + 168) = v384;
                }
                else
                {
                  inited = -1073741670;
                }
              }
              else
              {
                inited = -1073741701;
              }
              SkmmFreeIndependentPages(v382 & 0xFFFFFFFFFFFFF000uLL, v559);
            }
            *(_DWORD *)(v356 + 136) = 0;
LABEL_871:
            SkobDereferenceObject(v356);
          }
          goto LABEL_1253;
        case 29:
          Thread = SkmmPrepareImageRelocations(
                     *(_QWORD *)(v4 + 8),
                     *(_QWORD *)(v4 + 16),
                     *(_QWORD *)(v4 + 24),
                     *(_QWORD *)(v4 + 32),
                     *(_QWORD *)(v4 + 40),
                     *(_QWORD *)(v4 + 48),
                     *(_QWORD *)(v4 + 56),
                     *(_QWORD *)(v4 + 64));
          goto LABEL_1252;
        case 30:
          Thread = SkmmRelocateImage(*(_QWORD *)(v4 + 8), *(_QWORD *)(v4 + 16));
          goto LABEL_1252;
        case 31:
          LOBYTE(v28) = 1;
          Thread = SkobCloseHandle(*(_QWORD *)(v4 + 8), 0, v28, 0);
          goto LABEL_1252;
        case 32:
          v360 = *(_QWORD *)(v4 + 32);
          v361 = *(_QWORD *)(v4 + 24);
          v362 = *(_QWORD *)(v4 + 16);
          v363 = *(_QWORD *)(v4 + 8);
          v577 = 0;
          v578 = 0;
          if ( (SkmiFlags & 0x10) != 0 )
          {
            inited = SkmmMapDataTransfer(v361, v360, -2147483647, (unsigned int)&v577, (__int64)&v577 + 8);
            if ( inited >= 0 )
            {
              if ( *(_DWORD *)(v577 + 40) )
              {
                *(_QWORD *)&v578 = v363;
                *((_QWORD *)&v578 + 1) = v362;
                inited = SkmiOperateOnLockedNar(*((_QWORD *)&v577 + 1), SkmiValidateDynamicCodePages, &v577, v364);
              }
              else
              {
                inited = -1073741811;
              }
              SkmmUnmapDataTransfer(v577);
            }
          }
          goto LABEL_1253;
        case 33:
          v369 = *(_QWORD *)(v4 + 8);
          v370 = *(_QWORD *)(v4 + 40);
          v371 = *(_QWORD *)(v4 + 32);
          LOBYTE(v28) = 1;
          v372 = *(_QWORD *)(v4 + 24);
          v373 = *(_DWORD *)(v4 + 16);
          *(_QWORD *)v554 = 0;
          v557 = 0;
          inited = SkobReferenceObjectByHandle(v369, 0, v28, (unsigned int)&SkmiImageType, (__int64)v554, 0);
          if ( inited >= 0 )
          {
            v374 = SkmmMapDataTransfer(v372, v371, 1, (unsigned int)&v557, 0);
            v375 = *(_QWORD *)v554;
            inited = v374;
            v376 = v557;
            if ( v374 >= 0 )
              inited = SkciTransferVersionResource(
                         *(_QWORD *)(*(_QWORD *)v554 + 144LL),
                         v373,
                         *((_QWORD *)v557 + 3) & 0xFFFFFFFFFFFFF000uLL,
                         ((*((_DWORD *)v557 + 6) & 0xFFF) + *((unsigned int *)v557 + 10) + 4095LL)
                       & 0xFFFFFFFFFFFFF000uLL,
                         v370 - (*((_DWORD *)v557 + 6) & 0xFFF),
                         *((_DWORD *)v557 + 6) & 0xFFF,
                         *((unsigned int *)v557 + 10));
            if ( v376 )
              SkmmUnmapDataTransfer(v376);
            SkobDereferenceObject(v375);
          }
          goto LABEL_1253;
        case 34:
          v385 = *(_QWORD *)(v4 + 16);
          v386 = *(_DWORD *)(v4 + 8);
          LOBYTE(v28) = 1;
          *(_QWORD *)v554 = 0;
          inited = SkobReferenceObjectByHandle(v385, 0, v28, (unsigned int)&SkmiSecureAllocationType, (__int64)v554, 0);
          if ( inited >= 0 )
          {
            v387 = KeGetPcr()->NtTib.StackBase;
            v388 = *(_QWORD *)v554;
            if ( v387 )
            {
              v389 = v387[18];
              if ( v389 )
                --*(_WORD *)(v389 + xmmword_140167150);
            }
            if ( _interlockedbittestandset64((volatile signed __int32 *)(v388 + 16), 0) )
              RtlpAcquireSRWLockExclusiveContended(v388 + 16);
            inited = SkciSetCodeIntegrityPolicy(v386, *(_QWORD *)v388, *(_QWORD *)(v388 + 24));
            SkReleasePushLockExclusive(v388 + 16);
            v390 = KeGetPcr()->NtTib.StackBase;
            if ( v390 )
            {
              v391 = v390[18];
              if ( v391 )
              {
                v232 = (*(_WORD *)(v391 + xmmword_140167150))++ == 0xFFFF;
                if ( v232
                  && *(_QWORD *)(v391 + xmmword_140167160) != (_QWORD)xmmword_140167160 + v390[17]
                  && !*(_WORD *)(v391 + *((_QWORD *)&xmmword_140167150 + 1)) )
                {
                  SkiCheckForKernelApcDelivery();
                }
              }
            }
            SkobDereferenceObject(v388);
          }
          goto LABEL_1253;
        case 35:
          if ( !g_hExchangeVsmSource )
          {
            inited = -1073740955;
            goto LABEL_1254;
          }
          inited = EntropyProvideData(g_hExchangeVsmSource, (PCBYTE)(v4 + 16), 0x40u, 0x7D000u);
          if ( inited < 0 )
            goto LABEL_1254;
          LOBYTE(v422) = 1;
          EntropyPoolTriggerReseedForIum(v422);
          Thread = BCryptGenRandom(0, (PUCHAR)(v4 + 16), 0x40u, 2u);
          goto LABEL_1252;
        case 36:
          *(_QWORD *)(v4 + 16) = *(_QWORD *)&IumLkArrayHandle != 0;
          goto LABEL_624;
        case 37:
          v423 = *(_QWORD *)(v4 + 8);
          inited = SkCheckHibernationSupport();
          if ( inited < 0 )
            goto LABEL_1253;
          inited = SkpSetHiberCrashState(2, 0);
          if ( inited < 0 )
            goto LABEL_1253;
          if ( (ShvlpFlags & 1) != 0 )
            goto LABEL_965;
          qword_14016B528 = SkmmReserveMappingAddress(81920);
          if ( qword_14016B528 )
          {
            SkiVtl0SavedStateProcessorCount = SkeNumberProcessors;
            SkiVtl0SavedState = SkAllocatePool(512, (unsigned int)(784 * SkeNumberProcessors), 811755848);
            if ( SkiVtl0SavedState )
            {
LABEL_965:
              if ( !qword_14016B530
                || (inited = SkPreparePageEncryption(3, 0, qword_14016B530, 0, 0, 0, 0), inited >= 0) )
              {
                if ( (v423 & 1) != 0 )
                {
                  v567 = 0;
                  v571 = 0;
                  if ( (int)RtlCompressWorkSpaceSizeLz4(0, &v567, &v571) >= 0 )
                    qword_14016B4E0 = (void *)SkAllocatePool(512, (unsigned int)(v567 + 0x10000), 1164077384);
                }
                *(_QWORD *)(v4 + 16) = (unsigned int)SkpResumeInformationPageCount;
                inited = 0;
                *(_QWORD *)(v4 + 24) = (unsigned __int64)SkmmGetPhysicalAddress(SkpResumeInformation) >> 12;
                goto LABEL_1253;
              }
            }
            else
            {
              inited = -1073741670;
            }
          }
          else
          {
            inited = -1073741670;
          }
          if ( qword_14016B528 )
          {
            SkmmFreeReservedMapping(qword_14016B528, 81920);
            qword_14016B528 = 0;
          }
          SkeFreeVtl0SaveState();
          SkpSetHiberCrashState(1, 0);
          goto LABEL_1253;
        case 38:
          LODWORD(Src) = 0;
          if ( (int)SkpSetHiberCrashState(1, &Src) >= 0 && (_DWORD)Src == 2 )
          {
            SkpgSynchronizeWithExtentChecks();
            SkpgHibernateActive = 0;
            if ( qword_14016B530 )
              SkFinalizePageEncryption();
            if ( qword_14016B528 )
            {
              SkmmCleanReservationAfterHibernate(qword_14016B528, 81920);
              SkmmFreeReservedMapping(qword_14016B528, 81920);
              qword_14016B528 = 0;
            }
            SkeFreeVtl0SaveState();
            if ( qword_14016B4E0 )
            {
              RtlpHpFreeHeap(qword_14015A9A0, (ULONG_PTR)qword_14016B4E0);
              qword_14016B4E0 = 0;
            }
          }
          goto LABEL_624;
        case 39:
          Thread = SkmmConfigureDynamicMemory(
                     *(_QWORD *)(v4 + 8),
                     *(_QWORD *)(v4 + 16),
                     *(unsigned int *)(v4 + 24),
                     255);
          goto LABEL_1252;
        case 40:
          inited = SkmmReferenceAddressSpace(*(_QWORD *)(v4 + 8), *(_QWORD *)(v4 + 24), &v556, 255);
          if ( inited < 0 )
            goto LABEL_1254;
          v117 = v556;
          v564 = 0;
          if ( (*(_DWORD *)v556 & 0x10) != 0 )
          {
            v118 = *(_QWORD *)(v4 + 16);
            if ( v118 )
            {
              if ( (*(_DWORD *)v556 & 0x200) != 0 && (*(_DWORD *)(v556 + 332) & 1) != 0 )
              {
                inited = -1073741790;
              }
              else
              {
                inited = SkmmProtectVirtualMemory(
                           v556,
                           v118,
                           (int)v4 + 24,
                           (int)v4 + 32,
                           *(_DWORD *)(v4 + 40),
                           (__int64)&v564);
                if ( inited >= 0 )
                  *(_QWORD *)(v4 + 40) = v564;
              }
            }
            else
            {
              inited = -1073741811;
            }
          }
          else
          {
            inited = -1073741790;
          }
          v52 = *(_QWORD *)(v117 + 80);
          while ( (v52 & 1) != 0 )
          {
            v119 = v52;
            v52 = _InterlockedCompareExchange64((volatile signed __int64 *)(v117 + 80), v52 - 2, v52);
            if ( v52 == v119 )
              goto LABEL_1253;
          }
          goto LABEL_118;
        case 41:
          inited = SkmmReferenceAddressSpace(*(_QWORD *)(v4 + 8), *(_QWORD *)(v4 + 16), &v556, 255);
          if ( inited < 0 )
            goto LABEL_1254;
          v120 = v556;
          inited = SkmmDebugReadWriteMemory(
                     v556,
                     *(_QWORD *)(v4 + 16),
                     *(unsigned __int8 *)(v4 + 24),
                     *(_QWORD *)(v4 + 32),
                     *(_QWORD *)(v4 + 40),
                     v4 + 48);
          v52 = *(_QWORD *)(v120 + 80);
          while ( (v52 & 1) != 0 )
          {
            v121 = v52;
            v52 = _InterlockedCompareExchange64((volatile signed __int64 *)(v120 + 80), v52 - 2, v52);
            if ( v52 == v121 )
              goto LABEL_1253;
          }
          goto LABEL_118;
        case 42:
          inited = SkmmReferenceAddressSpace(*(_QWORD *)(v4 + 8), *(_QWORD *)(v4 + 16), &v556, 255);
          if ( inited < 0 )
            goto LABEL_1254;
          v122 = v556;
          inited = SkmmQueryVirtualMemory(v556, 0, *(_QWORD *)(v4 + 16), 8, (volatile void *)(v4 + 16), 0x30u, 0);
          v52 = *(_QWORD *)(v122 + 80);
          while ( (v52 & 1) != 0 )
          {
            v123 = v52;
            v52 = _InterlockedCompareExchange64((volatile signed __int64 *)(v122 + 80), v52 - 2, v52);
            if ( v52 == v123 )
              goto LABEL_1253;
          }
          goto LABEL_118;
        case 43:
          v513 = *(_QWORD *)(v4 + 16);
          v514 = *(_QWORD *)(v4 + 8);
          v598[2] = *(_QWORD *)(v4 + 24);
          v598[0] = v514;
          v598[1] = v513;
          Thread = SkmiOperateOnLockedNar(v514, SkmiCaptureSecureImageIat, v598, 255);
          goto LABEL_1252;
        case 44:
          v515 = *(_QWORD *)(v4 + 8);
          LOBYTE(v28) = 1;
          *(_QWORD *)v554 = 0;
          inited = SkobReferenceObjectByHandle(v515, 0, v28, (unsigned int)&SkmiImageType, (__int64)v554, 0);
          if ( inited >= 0 )
          {
            inited = SkmiChangeCapturedIat(*(ULONG_PTR *)v554);
            SkobDereferenceObject(*(_QWORD *)v554);
          }
          goto LABEL_1253;
        case 45:
          Thread = SkmmApplySecureFixups(*(_QWORD *)(v4 + 8), *(unsigned int *)(v4 + 16), *(_QWORD *)(v4 + 24), 255);
          goto LABEL_1252;
        case 46:
          v277 = *(_QWORD *)(v4 + 8);
          v278 = *(unsigned __int8 *)(v4 + 24);
          v279 = *(_QWORD *)(v4 + 16);
          v587 = 0;
          v586 = 0;
          if ( v277 )
          {
            *((_QWORD *)&v586 + 1) = v279;
            *(_QWORD *)&v586 = v277;
            LODWORD(v587) = v278;
            Thread = SkmiOperateOnLockedNar(v277, SkmiExemptProtectedPteRange, &v586, 255);
            goto LABEL_1252;
          }
          if ( (_BYTE)v278 )
          {
            inited = -1073741811;
          }
          else
          {
            v280 = SkmiAcquireNteAssertionLock(0, v279, 0, 255);
            SkAcquireSpinLockExclusiveAtDpcLevel(&dword_1401567E8);
            if ( dword_1401567EC )
              inited = -1073741811;
            else
              SkmiSecurePteExemption = 0;
            dword_1401567E8 = 0;
            SkTrackSpinLockRelease();
            _InterlockedIncrement64(&SkmiAssertionTimestamp);
            SkeLowerIrql(v280);
          }
          goto LABEL_1253;
        case 47:
          Thread = SkmmCreateEnclave(
                     *(_QWORD *)(v4 + 8),
                     *(_QWORD *)(v4 + 16),
                     *(_QWORD *)(v4 + 24),
                     *(_QWORD *)(v4 + 32),
                     *(_QWORD *)(v4 + 40),
                     *(_QWORD *)(v4 + 48),
                     *(_BYTE *)(v4 + 56),
                     v4 + 16);
          goto LABEL_1252;
        case 48:
          Thread = SkmmLoadEnclaveData(
                     *(_QWORD *)(v4 + 8),
                     *(_QWORD *)(v4 + 16),
                     *(_DWORD *)(v4 + 24),
                     *(_DWORD *)(v4 + 32),
                     *(_QWORD *)(v4 + 40),
                     *(_QWORD *)(v4 + 48),
                     v4 + 16);
          goto LABEL_1252;
        case 49:
          Thread = SkmmLoadEnclaveModule(
                     *(_QWORD *)(v4 + 8),
                     *(_QWORD *)(v4 + 16),
                     *(_QWORD *)(v4 + 24),
                     *(_QWORD *)(v4 + 32),
                     *(_QWORD *)(v4 + 40),
                     *(_QWORD *)(v4 + 48),
                     v4 + 16,
                     v4 + 24,
                     v4 + 32);
          goto LABEL_1252;
        case 50:
          v124 = *(_QWORD *)(v4 + 8);
          LOBYTE(v28) = 1;
          Src = *(void **)(v4 + 48);
          v556 = *(_QWORD *)(v4 + 40);
          v568 = *(_QWORD *)(v4 + 32);
          v557 = *(PUCHAR *)(v4 + 24);
          v561[0] = *(void **)(v4 + 16);
          v559 = 0;
          *(_QWORD *)v554 = 0;
          inited = SkobReferenceObjectByHandle(v124, 0, v28, (unsigned int)&SkmiEnclaveType, (__int64)v554, 0);
          if ( inited < 0 )
            goto LABEL_1253;
          v125 = *(_QWORD *)v554;
          v126 = 0;
          v127 = *(_QWORD *)(*(_QWORD *)v554 + 80LL);
          while ( (v127 & 1) != 0 && v127 != -1 )
          {
            v128 = v127;
            v127 = _InterlockedCompareExchange64((volatile signed __int64 *)(v125 + 80), v127 + 2, v127);
            if ( v127 == v128 )
            {
              v129 = 1;
              v126 = v125;
              goto LABEL_333;
            }
          }
          v129 = 0;
LABEL_333:
          v130 = 0;
          if ( !v129 )
            v130 = -1073741816;
          inited = v130;
          SkobDereferenceObject(v125);
          if ( !v129 )
            goto LABEL_1253;
          if ( _interlockedbittestandset64((volatile signed __int32 *)(v126 + 640), 0) )
            RtlpAcquireSRWLockExclusiveContended(v126 + 640);
          v131 = SkiAttachProcess(v126);
          v132 = *(_DWORD *)(v126 + 672);
          v133 = v131;
          *(_QWORD *)v554 = v131;
          if ( v132 )
          {
            if ( v132 == 1 )
              inited = -1073740528;
            else
              inited = -1073740526;
          }
          else
          {
            v134 = SkmmMapDataTransfer((_DWORD)v557, v568, 1, (unsigned int)&v559, 0);
            v6 = v559;
            inited = v134;
            if ( v134 >= 0 )
            {
              v135 = (*(_DWORD *)(v126 + 332) & 1) != 0
                   ? SkmiInitializeBasicEnclave(v126, v559, v556, Src)
                   : SkmiInitializeEnclave(v126, v559);
              inited = v135;
              if ( v135 >= 0 )
              {
                *(void **)(v126 + 248) = v561[0];
                _InterlockedOr((volatile signed __int32 *)v126, 0x80u);
                inited = SkeReadyEnclaveThreads(v126, (*(_BYTE *)(v126 + 332) & 1) == 0, v4 + 16);
                if ( inited >= 0 )
                {
                  *(_DWORD *)(v126 + 672) = 1;
                  goto LABEL_354;
                }
              }
            }
          }
          *(_QWORD *)(v126 + 248) = 0;
          if ( (*(_DWORD *)(v126 + 332) & 1) == 0 )
          {
            while ( *(_QWORD *)(v126 + 16) != v126 + 16 )
              SkpsDeleteEnclaveThread();
            v133 = *(_QWORD *)v554;
          }
          _InterlockedAnd((volatile signed __int32 *)v126, 0xFFFFFF7F);
LABEL_354:
          SkiAttachProcess(v133);
          RtlReleaseSRWLockExclusive(v126 + 640);
          if ( v6 )
            SkmmUnmapDataTransfer(v6);
          v52 = *(_QWORD *)(v126 + 80);
          while ( (v52 & 1) != 0 )
          {
            v136 = v52;
            v52 = _InterlockedCompareExchange64((volatile signed __int64 *)(v126 + 80), v52 - 2, v52);
            if ( v52 == v136 )
              goto LABEL_1253;
          }
          goto LABEL_118;
        case 51:
          v137 = *(_QWORD *)(v4 + 8);
          *(_QWORD *)v554 = 0;
          inited = SkmiReferenceEnclaveByHandle(v137, v554);
          if ( inited < 0 )
            goto LABEL_1253;
          v138 = *(_QWORD *)v554;
          SkmmTerminateEnclaveByPointer(*(_QWORD *)v554);
          v139 = *(_QWORD *)(v138 + 80);
          while ( (v139 & 1) != 0 )
          {
            v140 = v139;
            v139 = _InterlockedCompareExchange64((volatile signed __int64 *)(v138 + 80), v139 - 2, v139);
            if ( v139 == v140 )
            {
              inited = 0;
              goto LABEL_1253;
            }
          }
          if ( _InterlockedExchangeAdd64((volatile signed __int64 *)v139, 0xFFFFFFFFFFFFFFFFuLL) == 1 )
            SkeAlertThreadByThreadId(*(_QWORD *)(v139 + 8));
          inited = 0;
          goto LABEL_1253;
        case 52:
          v141 = *(_QWORD *)(v4 + 8);
          LOBYTE(v28) = 1;
          *(_QWORD *)v554 = 0;
          inited = SkobReferenceObjectByHandle(v141, 0, v28, (unsigned int)&SkmiEnclaveType, (__int64)v554, 0);
          if ( inited < 0 )
            goto LABEL_1253;
          v142 = *(_QWORD *)v554;
          v143 = *(_QWORD *)(*(_QWORD *)v554 + 624LL);
          v144 = *(_QWORD *)(v143 + 80);
          do
          {
            if ( (v144 & 1) == 0 || v144 == -1 )
            {
              inited = -1073741558;
              SkobDereferenceObject(v142);
              goto LABEL_1253;
            }
            v145 = v144;
            v144 = _InterlockedCompareExchange64((volatile signed __int64 *)(v143 + 80), v144 + 2, v144);
          }
          while ( v144 != v145 );
          if ( _interlockedbittestandset64((volatile signed __int32 *)(v142 + 640), 0) )
            RtlpAcquireSRWLockExclusiveContended(v142 + 640);
          v146 = v142 + 640;
          if ( *(int *)(v142 + 672) >= 3 )
          {
            RtlReleaseSRWLockExclusive(v146);
LABEL_391:
            SkmiWaitForEnclaveDeletion(v142);
            inited = 0;
            SkReleaseRundownProtection(v143 + 80, 0);
            SkobDereferenceObject(v142);
            goto LABEL_1253;
          }
          *(_DWORD *)(v142 + 672) = 3;
          RtlReleaseSRWLockExclusive(v146);
          v147 = KeGetPcr()->NtTib.StackBase;
          if ( v147 )
          {
            v148 = v147[18];
            if ( v148 )
              --*(_WORD *)(v148 + xmmword_140167150);
          }
          if ( _interlockedbittestandset64((volatile signed __int32 *)(v142 + 576), 0) )
            RtlpAcquireSRWLockExclusiveContended(v142 + 576);
          if ( _bittest64((const signed __int64 *)(v142 + 584), 0x2Fu) )
          {
            SkmiUnlockVad(v142 + 536);
            goto LABEL_391;
          }
          if ( _InterlockedIncrement((volatile signed __int32 *)(v142 + 572)) <= 1 )
            __fastfail(0xEu);
          SkmiUnlockVad(v142 + 536);
          LOBYTE(v149) = 1;
          SkeTerminateEnclave(v142, v149);
          SkmiCleanEnclaveAddressSpace(v142);
          SkmiLockVad(v142 + 536);
          SkmiDeleteVad(v143, v142 + 536);
          if ( _interlockedbittestandset64((volatile signed __int32 *)(v142 + 640), 0) )
            RtlpAcquireSRWLockExclusiveContended(v142 + 640);
          *(_DWORD *)(v142 + 672) = 4;
          v150 = *(_QWORD **)(v142 + 688);
          *(_QWORD *)(v142 + 688) = 0;
          while ( v150 )
          {
            v151 = v150[1];
            v150 = (_QWORD *)*v150;
            SkeAlertThreadByThreadId(v151);
          }
          RtlReleaseSRWLockExclusive(v142 + 640);
          inited = 0;
          SkmiUnlockVad(v142 + 536);
          SkmiDereferenceVad(v142 + 536);
          SkReleaseRundownProtection(v143 + 80, 0);
          SkobDereferenceObject(v142);
          goto LABEL_1253;
        case 53:
          v211 = *(_QWORD *)(v4 + 8);
          *(_QWORD *)v554 = 0;
          if ( (int)SkmiObtainPartition(v211, v554, 1, 255) >= 0 )
          {
            SkmiReclaimPartitionPages(*(_QWORD *)v554);
            SkmiDereferencePartition(*(_QWORD *)v554);
          }
          goto LABEL_624;
        case 54:
          v152 = 0;
          while ( stricmp((&TprtdllExports)[2 * v152], "DbgUiRemoteBreakin") )
          {
            if ( ++v152 >= 4 )
            {
              inited = -1073741275;
              goto LABEL_1253;
            }
          }
          *(_QWORD *)(v4 + 24) = *(_QWORD *)off_14010C0D8[2 * v152];
          *(_QWORD *)(v4 + 16) |= 1uLL;
          goto LABEL_1253;
        case 55:
          inited = -1073741637;
          goto LABEL_1254;
        case 56:
          Thread = IumpConnectSwInterrupt(v4 + 8);
          goto LABEL_1252;
        case 57:
          if ( SkpgInitialized && SkpgContext )
          {
            v437 = *(_DWORD *)(SkpgContext + 244);
            if ( (v437 & 0x100000) != 0 )
            {
              if ( (v437 & 0x400) != 0 )
                inited = 255;
              else
                SkpgQuotasRelaxed = 1;
            }
            else
            {
              inited = -1073741790;
            }
          }
          else
          {
            inited = -1073741661;
          }
          goto LABEL_1253;
        case 58:
          v424 = *(_QWORD *)(v4 + 8);
          *(_QWORD *)v554 = 0;
          if ( v424 )
          {
            inited = SkmmMapDataTransfer(v424, *(_QWORD *)(v4 + 16), 1, (unsigned int)v554, 0);
            if ( inited < 0 )
              goto LABEL_1253;
            v425 = *(_QWORD *)v554;
            v426 = *(unsigned int *)(*(_QWORD *)v554 + 40LL);
            v427 = (void *)SkAllocatePool(512, v426, 1380205138);
            v428 = v427;
            if ( !v427 )
            {
              inited = -1073741670;
              SkmmUnmapDataTransfer(v425);
              goto LABEL_1253;
            }
            memmove(v427, *(const void **)(v425 + 24), v426);
            SkmmUnmapDataTransfer(v425);
          }
          else
          {
            v426 = 0;
            v428 = 0;
          }
          if ( SkpgBootDrivers )
          {
            inited = -1073741431;
            goto LABEL_1012;
          }
          if ( v428 && (v426 & 7) != 0 )
          {
            inited = -1073741820;
            RtlpHpFreeHeap(qword_14015A9A0, (ULONG_PTR)v428);
            goto LABEL_1253;
          }
          v429 = KeGetPcr()->NtTib.StackBase;
          if ( v429 )
          {
            v430 = v429[18];
            if ( v430 )
              --*(_WORD *)(xmmword_140167150 + v430);
          }
          if ( _interlockedbittestandset64((volatile signed __int32 *)&SkpgConnectionLock, 0) )
            RtlpAcquireSRWLockExclusiveContended(&SkpgConnectionLock);
          if ( SkpgBootDrivers )
          {
            inited = -1073741790;
            goto LABEL_1006;
          }
          v431 = v426 >> 3;
          SkpgBootDrivers = -1;
          if ( !v431 )
            goto LABEL_1005;
          v432 = (void *)SkAllocatePool(512, 8 * v431, 1145202512);
          v433 = (__int64)v432;
          if ( v432 )
          {
            memmove(v432, v428, 8 * v431);
            SkpgBootDrivers = v433;
            _InterlockedOr(v550, 0);
            SkpgBootDriverCount = v431;
LABEL_1005:
            inited = 0;
          }
          else
          {
            inited = -1073741670;
          }
LABEL_1006:
          SkReleasePushLockExclusive(&SkpgConnectionLock);
          v434 = KeGetPcr()->NtTib.StackBase;
          if ( v434 )
          {
            v435 = v434[18];
            if ( v435 )
            {
              v232 = (*(_WORD *)(xmmword_140167150 + v435))++ == 0xFFFF;
              if ( v232
                && *(_QWORD *)(xmmword_140167160 + v435) != (_QWORD)xmmword_140167160 + v434[17]
                && !*(_WORD *)(*((_QWORD *)&xmmword_140167150 + 1) + v435) )
              {
                SkiCheckForKernelApcDelivery();
              }
            }
          }
LABEL_1012:
          if ( v428 )
            RtlpHpFreeHeap(qword_14015A9A0, (ULONG_PTR)v428);
          goto LABEL_1253;
        case 59:
          v464 = *(unsigned int *)(v4 + 8);
          v465 = 1;
          if ( *(_DWORD *)(v4 + 8) )
          {
            if ( v464 == 2 )
              LODWORD(v464) = 1;
            v465 = (unsigned int)v464;
          }
          qword_14014C718 = SkmmEstimateSecurePageCount((v465 >> 2) & 4 | 3) + 768;
          *(_QWORD *)(v4 + 16) = 4104 * qword_14014C718;
          *(_QWORD *)(v4 + 24) = 12288;
          goto LABEL_624;
        case 60:
          Thread = SkLiveDumpStart(
                     *(unsigned int *)(v4 + 8),
                     *(unsigned int *)(v4 + 16),
                     *(unsigned int *)(v4 + 24),
                     255);
          goto LABEL_1252;
        case 61:
          v451 = *(unsigned int *)(v4 + 8);
          if ( (unsigned int)v451 <= 0xB )
          {
            SkpAcquireLiveDumpLock();
            if ( SkpLiveDumpContext == 1
              && (v452 = qword_14014C720, v451 <= qword_14014C708 + qword_14014C710 - qword_14014C720) )
            {
              v453 = qword_14014C738;
              for ( j = (char *)(v4 + 16); (_DWORD)v451; v453 = *(_QWORD *)v453 )
              {
                v455 = *(_DWORD *)(v453 + 40) >> 12;
                if ( v452 < v455 )
                {
                  v456 = v455 - v452;
                  v457 = (unsigned int)v451;
                  if ( v456 <= (unsigned int)v451 )
                    v457 = v456;
                  v458 = (unsigned int)v457;
                  v459 = 8 * v457;
                  memmove((void *)(v453 + 8 * (v452 + 6)), j, 8 * v457);
                  qword_14014C720 += v458;
                  v452 = 0;
                  LODWORD(v451) = v451 - v458;
                  j += v459;
                }
                else
                {
                  v452 -= v455;
                }
              }
              inited = 0;
              SkpReleaseLiveDumpLock();
            }
            else
            {
LABEL_1047:
              inited = -1073741811;
              SkpReleaseLiveDumpLock();
            }
            goto LABEL_1253;
          }
          inited = -1073741811;
          goto LABEL_1254;
        case 62:
          Thread = SkLiveDumpSetupBuffer((int)v4 + 16, (int)v4 + 24, (int)v4 + 32, (int)v4 + 40, v4 + 48);
          goto LABEL_1252;
        case 63:
          *(_QWORD *)v554 = 0;
          v557 = 0;
          v559 = 0;
          inited = SkLiveDumpFinalize(v4 + 8, v554, &v557, &v559);
          if ( inited < 0 )
            goto LABEL_1254;
          *(_QWORD *)(v4 + 16) = *(_QWORD *)v554;
          *(_QWORD *)(v4 + 24) = v557;
          *(_QWORD *)(v4 + 32) = v559;
          goto LABEL_624;
        case 64:
          SkpAcquireLiveDumpLock();
          while ( 1 )
          {
            v460 = SkpLiveDumpContext;
            if ( SkpLiveDumpContext == 3 )
              goto LABEL_1047;
            if ( v460 == _InterlockedCompareExchange(&SkpLiveDumpContext, 0, SkpLiveDumpContext) )
            {
              if ( v460 >= 4 )
              {
                for ( k = qword_14014C738; k; k = *(_QWORD *)k )
                {
                  v462 = *(unsigned int *)(k + 40);
                  v463 = *(_BYTE **)(k + 24);
                  if ( *(_DWORD *)(k + 40) )
                  {
                    do
                    {
                      *v463++ = 0;
                      --v462;
                    }
                    while ( v462 );
                  }
                }
              }
              SkpLiveDumpFreeContext();
              SkpReleaseLiveDumpLock();
              goto LABEL_1253;
            }
          }
        case 65:
          inited = SkpsReferenceProcessByHandle(*(_QWORD *)(v4 + 8), 0, &Src, 255);
          if ( inited < 0 )
            goto LABEL_1254;
          v466 = (char *)Src;
          v467 = SkiAttachProcess(Src);
          inited = SkMinidumpWriteDump(0, 0, v466);
          SkeDetachProcess(v467);
          SkReleaseRundownProtection(v466 + 80, 0);
          goto LABEL_1253;
        case 66:
          if ( (SkpFlags & 1) == 0 )
            goto LABEL_1092;
          v468 = *(_DWORD *)(v4 + 24);
          v469 = *(_BYTE *)(v4 + 8);
          if ( v468 )
          {
            if ( v468 == 1 )
            {
              v471 = v469 != 0;
              CurrentIrql = KeGetCurrentIrql();
              __writecr8(5u);
              SkAcquireSpinLockExclusiveAtDpcLevel(&SkiTimerLock);
              LOBYTE(v473) = 1;
              SkiTimerMode = v471;
              SkiUpdateSyntheticTimer(v473);
              SkiTimerLock = 0;
              SkTrackSpinLockRelease();
              SkeLowerIrql(CurrentIrql);
              inited = 0;
              goto LABEL_624;
            }
            if ( v468 == 2 )
              SkIdleResiliencyActive = *(_BYTE *)(v4 + 8);
          }
          else
          {
            if ( v469 )
            {
              inited = 0;
              SkCsScenarioInstanceId = *(_QWORD *)(v4 + 16);
              SkiCallbackCsActiveTime = 0;
              SkiTimerCsActiveTime = 0;
              goto LABEL_624;
            }
            v470 = SkCsScenarioInstanceId;
            if ( SkiTimerCsActiveTime && (Microsoft_Windows_SleepStudyEnableBits & 1) != 0 )
              McTemplateK0ujqzr2jxxx_EtwWriteTransfer(
                SkiTimerCsActiveTime,
                a2,
                0x40000000u,
                (unsigned __int8)SkCsScenarioInstanceId,
                (_DWORD)pbInput,
                13,
                (__int64)L"SecureTimers",
                cbOutput[0],
                SkiTimerCsActiveTime);
            if ( SkiCallbackCsActiveTime && (Microsoft_Windows_SleepStudyEnableBits & 1) != 0 )
            {
              McTemplateK0ujqzr2jxxx_EtwWriteTransfer(
                SkiCallbackCsActiveTime,
                a2,
                v28,
                v470,
                (_DWORD)pbInput,
                16,
                (__int64)L"SecureCallbacks",
                cbOutput[0],
                SkiCallbackCsActiveTime);
              inited = 0;
              goto LABEL_624;
            }
          }
          goto LABEL_1092;
        case 67:
          v474 = *(_QWORD *)(v4 + 16);
          v187 = 0;
          v557 = 0;
          if ( v474 )
          {
            v475 = SkmmMapDataTransfer(v474, *(_QWORD *)(v4 + 24), 2, (unsigned int)&v557, 0);
            v187 = v557;
            inited = v475;
            if ( v475 >= 0 )
              inited = IumpQueryProfileInformation(
                         *(_QWORD *)(v4 + 8),
                         *((_QWORD *)v557 + 3),
                         *((unsigned int *)v557 + 10),
                         v4 + 16);
          }
          else
          {
            inited = IumpQueryProfileInformation(*(_QWORD *)(v4 + 8), 0, 0, v4 + 16);
          }
          goto LABEL_474;
        case 68:
          v54 = *(_QWORD *)(v4 + 8);
          LOBYTE(v28) = 1;
          v557 = 0;
          inited = SkobReferenceObjectByHandle(v54, 0, v28, (unsigned int)&SkpsProcessType, (__int64)&v557, 0);
          if ( inited < 0 )
            goto LABEL_137;
          v55 = v557;
          if ( (*(_DWORD *)v557 & 2) == 0 )
          {
            inited = -1073740007;
            goto LABEL_136;
          }
          v56 = *((_QWORD *)v557 + 10);
          do
          {
            if ( (v56 & 1) == 0 || v56 == -1 )
              goto LABEL_135;
            v57 = v56;
            v56 = _InterlockedCompareExchange64((volatile signed __int64 *)v55 + 10, v56 + 2, v56);
          }
          while ( v56 != v57 );
          LODWORD(Src) = *(_DWORD *)v55;
          if ( ((unsigned __int16)Src & 0x400) != 0 )
          {
            v58 = *((_QWORD *)v55 + 10);
            while ( (v58 & 1) != 0 )
            {
              v59 = v58;
              v58 = _InterlockedCompareExchange64((volatile signed __int64 *)v55 + 10, v58 - 2, v58);
              if ( v58 == v59 )
                goto LABEL_135;
            }
            if ( _InterlockedExchangeAdd64((volatile signed __int64 *)v58, 0xFFFFFFFFFFFFFFFFuLL) == 1 )
              SkeAlertThreadByThreadId(*(_QWORD *)(v58 + 8));
LABEL_135:
            inited = -1073741816;
            goto LABEL_136;
          }
          v5 = v55;
          inited = 0;
LABEL_136:
          SkobDereferenceObject(v55);
LABEL_137:
          if ( inited < 0 )
            goto LABEL_1254;
          inited = SkpsUpdateFreezeTimeBias(v5, *(_QWORD *)(v4 + 16));
          v52 = v5[10];
          while ( (v52 & 1) != 0 )
          {
            v60 = v52;
            v52 = _InterlockedCompareExchange64(v5 + 10, v52 - 2, v52);
            if ( v52 == v60 )
              goto LABEL_1253;
          }
          goto LABEL_118;
        case 69:
          inited = SkpsReferenceProcessByHandle(*(_QWORD *)(v4 + 8), 0, &Src, 255);
          if ( inited < 0 )
            goto LABEL_1254;
          v496 = (char *)Src;
          inited = SkmmCreateExposedSecureSection(
                     (_DWORD)Src,
                     *(_QWORD *)(v4 + 24),
                     *(_QWORD *)(v4 + 40),
                     *(_DWORD *)(v4 + 16),
                     v4 + 32);
          SkReleaseRundownProtection(v496 + 80, 0);
          goto LABEL_1253;
        case 70:
          v497 = *(_QWORD *)(v4 + 8);
          *(_QWORD *)v554 = 0;
          LOBYTE(v28) = 1;
          inited = SkobReferenceObjectByHandle(v497, 0, v28, (unsigned int)&SkmiSectionType, (__int64)v554, 0);
          if ( inited >= 0 )
          {
            v498 = *(_QWORD *)v554;
            if ( *(_QWORD *)(*(_QWORD *)v554 + 24LL) )
            {
              if ( _InterlockedIncrement64((volatile signed __int64 *)(*(_QWORD *)v554 - 8LL)) <= 1 )
                __fastfail(0xEu);
              if ( SkobDereferenceObject(v498) <= 2 )
              {
                inited = SkobCloseHandleEx(v497, v498, 0, 0, 0);
                SkobDereferenceObject(v498);
              }
              else
              {
                SkobDereferenceObject(v498);
                inited = -2147483631;
              }
            }
            else
            {
              inited = -1073741811;
            }
          }
          goto LABEL_1253;
        case 71:
          v499 = SkAcquireSpinLockExclusive(&SkpnppDeviceListLock);
          DeviceByLocation = SkpnppFindDeviceByLocation(v4 + 8);
          SkpnppDeviceListLock = 0;
          SkTrackSpinLockRelease();
          SkeLowerIrql(v499);
          *(_BYTE *)(v4 + 20) = DeviceByLocation != 0;
          if ( DeviceByLocation )
          {
            *(_BYTE *)(v4 + 21) = *(_BYTE *)(DeviceByLocation + 96);
            *(_QWORD *)(v4 + 24) = *(_QWORD *)(DeviceByLocation + 56);
          }
          else
          {
            *(_BYTE *)(v4 + 21) = 0;
            *(_QWORD *)(v4 + 24) = 0;
          }
          goto LABEL_624;
        case 72:
          v501 = *(_QWORD *)(v4 + 8);
          LOBYTE(v637[0]) = 0;
          v502 = SkAcquireSpinLockExclusive(&SkpnppDeviceListLock);
          DeviceByToken = SkpnppFindDeviceByToken(v501);
          v504 = DeviceByToken;
          if ( DeviceByToken )
          {
            v637[0] = *(_OWORD *)(DeviceByToken + 104);
            v637[1] = *(_OWORD *)(DeviceByToken + 120);
            v505 = *(_DWORD *)(DeviceByToken + 100);
            if ( v505 != 2 )
            {
              if ( v505 == 1 )
              {
                inited = (*(__int64 (__fastcall **)(ULONG_PTR))(*(_QWORD *)(v504 + 80) + 32LL))(v504);
                if ( inited >= 0 )
                {
                  if ( *(_DWORD *)(v504 + 100) != 1 )
                    SkeBugCheckEx(0xCAu, 2u, v504, *(int *)(v504 + 100), 0);
                  *(_DWORD *)(v504 + 100) = 2;
                }
              }
              else
              {
                inited = -1073741790;
              }
            }
          }
          else
          {
            inited = -1073741810;
          }
          SkpnppDeviceListLock = 0;
          SkTrackSpinLockRelease();
          SkeLowerIrql(v502);
          if ( (Microsoft_Windows_IsolatedUserModeEnableBits & 0x10) != 0 )
            McTemplateK0xsd_EtwWriteTransfer(
              v506,
              (unsigned int)SecureDeviceUnprotect,
              v507,
              v501,
              (__int64)v637,
              inited);
          goto LABEL_1253;
        case 73:
          v294 = *(_QWORD *)(v4 + 40);
          v295 = *(_QWORD *)(v4 + 32);
          v296 = *(_DWORD *)(v4 + 24);
          v561[0] = (void *)*(unsigned int *)(v4 + 16);
          LODWORD(Src) = *(_DWORD *)(v4 + 8);
          v559 = 0;
          inited = SkmmMapDataTransfer(v295, v294, 1, (unsigned int)&v559, 0);
          if ( inited < 0 )
            goto LABEL_1253;
          v297 = v559;
          v298 = *(unsigned __int16 *)(v559 + 40);
          v299 = (_WORD *)SkAllocatePool(512, v298 + 2, 1212764232);
          v300 = v299;
          if ( !v299 )
          {
            inited = -1073741670;
            SkmmUnmapDataTransfer(v297);
            goto LABEL_1253;
          }
          memmove(v299, *(const void **)(v297 + 24), v298);
          v300[v298 >> 1] = 0;
          v301 = SkAllocatePool(512, v298 + 56, 1883786067);
          v302 = (_DWORD *)v301;
          if ( !v301 )
          {
            inited = -1073741670;
            goto LABEL_726;
          }
          *(_DWORD *)(v301 + 24) = (_DWORD)Src;
          *(_DWORD *)(v301 + 28) = v561[0];
          *(_DWORD *)(v301 + 32) = v296;
          *(_WORD *)(v301 + 40) = v298;
          *(_WORD *)(v301 + 42) = v298;
          *(_QWORD *)(v301 + 48) = v301 + 56;
          memmove((void *)(v301 + 56), v300, v298);
          v304 = 0;
          if ( _interlockedbittestandset64((volatile signed __int32 *)&SkmiHotPatchListLock, 0) )
            RtlpAcquireSRWLockExclusiveContended(&SkmiHotPatchListLock);
          v305 = SkmiGlobalHotPatchList;
          if ( !SkmiGlobalHotPatchList )
            goto LABEL_713;
          v306 = v302[6];
          while ( v306 >= *(_DWORD *)(v305 + 24) )
          {
            if ( v306 <= *(_DWORD *)(v305 + 24) )
            {
              v307 = *(_DWORD *)(v305 + 28);
              if ( v302[7] < v307 )
                break;
              if ( v302[7] <= v307 )
              {
                v311 = *(_DWORD *)(v305 + 32);
                if ( v302[8] <= v311 )
                {
                  v304 = (ULONG_PTR)v302;
                  inited = 255;
                  if ( v302[8] != v311 )
                    inited = -1073740758;
                  SkReleasePushLockExclusive(&SkmiHotPatchListLock);
                  goto LABEL_721;
                }
                RtlAvlRemoveNode(&SkmiGlobalHotPatchList, v305);
                v304 = v305;
                if ( (unsigned int)SkmiInsertPreviouslyRegisteredHotPatchRecord(v305) )
                  v304 = 0;
LABEL_713:
                v308 = SkmiGlobalHotPatchList;
                LOBYTE(v303) = 0;
                if ( !SkmiGlobalHotPatchList )
                  goto LABEL_720;
                v309 = v302[6];
                while ( 1 )
                {
                  if ( v309 < *(_DWORD *)(v308 + 24)
                    || v309 <= *(_DWORD *)(v308 + 24) && v302[7] < *(_DWORD *)(v308 + 28) )
                  {
                    v310 = *(_QWORD *)v308;
                    if ( !*(_QWORD *)v308 )
                      goto LABEL_720;
                  }
                  else
                  {
                    v310 = *(_QWORD *)(v308 + 8);
                    if ( !v310 )
                    {
                      LOBYTE(v303) = 1;
LABEL_720:
                      RtlAvlInsertNodeEx(&SkmiGlobalHotPatchList, v308, v303, v302);
                      SkReleasePushLockExclusive(&SkmiHotPatchListLock);
                      inited = 0;
                      if ( v304 )
LABEL_721:
                        RtlpHpFreeHeap(qword_14015A9A0, v304);
                      if ( inited < 0 || inited == 255 )
                        RtlpHpFreeHeap(qword_14015A9A0, (ULONG_PTR)v302);
                      v297 = v559;
LABEL_726:
                      RtlpHpFreeHeap(qword_14015A9A0, (ULONG_PTR)v300);
                      SkmmUnmapDataTransfer(v297);
                      goto LABEL_1253;
                    }
                  }
                  v308 = v310;
                }
              }
            }
            v305 = *(_QWORD *)(v305 + 8);
LABEL_712:
            if ( !v305 )
              goto LABEL_713;
          }
          v305 = *(_QWORD *)v305;
          goto LABEL_712;
        case 74:
          v312 = *(_QWORD *)(v4 + 32);
          v313 = *(_QWORD *)(v4 + 24);
          v314 = *(_QWORD *)(v4 + 16);
          v315 = *(_QWORD *)(v4 + 8);
          LODWORD(Src) = 0;
          LODWORD(v556) = 0;
          inited = SkmmQueryActiveSecurePatch(v315, v314, v313, v312, (__int64)&Src, (__int64)&v556);
          *(_QWORD *)(v4 + 16) = (unsigned int)Src;
          *(_QWORD *)(v4 + 24) = (unsigned int)v556;
          goto LABEL_1253;
        case 75:
          Thread = SkmmDetermineHotPatchType(*(unsigned int *)(v4 + 8), *(unsigned int *)(v4 + 16), v4 + 16, 255);
          goto LABEL_1252;
        case 76:
          v316 = KeGetPcr()->NtTib.StackBase;
          v317 = *(_QWORD *)(v4 + 8);
          if ( v316 )
          {
            v318 = v316[18];
            if ( v318 )
              --*(_WORD *)(v318 + xmmword_140167150);
          }
          if ( _interlockedbittestandset64((volatile signed __int32 *)&SkmiNarLock, 0) )
            RtlpAcquireSRWLockExclusiveContended(&SkmiNarLock);
          Nar = SkmiLocateNar(v317);
          if ( !Nar || *(_QWORD *)(Nar + 24) != v317 || (*(_BYTE *)(Nar + 78) & 6) != 2 )
            goto LABEL_748;
          *(_DWORD *)(v4 + 16) = 8 * *(_DWORD *)(Nar + 144) + 4;
          SkReleasePushLockExclusive(&SkmiNarLock);
          goto LABEL_683;
        case 77:
          Thread = SkmmObtainHotPatchUndoTable(*(_QWORD *)(v4 + 8), *(_QWORD *)(v4 + 16), *(_QWORD *)(v4 + 24), 255);
          goto LABEL_1252;
        case 78:
          v320 = *(_DWORD *)(v4 + 56);
          if ( (v320 & 0xFFFFFFFC) != 0 )
          {
            inited = -1073741811;
            goto LABEL_1254;
          }
          Thread = SkmmApplyHotPatch(
                     *(_QWORD *)(v4 + 8),
                     *(_QWORD *)(v4 + 16),
                     *(_QWORD *)(v4 + 24),
                     *(_QWORD *)(v4 + 32),
                     *(_QWORD *)(v4 + 40),
                     *(_QWORD *)(v4 + 48),
                     v320,
                     v4 + 16);
          goto LABEL_1252;
        case 79:
          v321 = KeGetPcr()->NtTib.StackBase;
          v322 = *(_QWORD *)(v4 + 8);
          if ( v321 )
          {
            v323 = v321[18];
            if ( v323 )
              --*(_WORD *)(v323 + xmmword_140167150);
          }
          if ( _interlockedbittestandset64((volatile signed __int32 *)&SkmiNarLock, 0) )
            RtlpAcquireSRWLockExclusiveContended(&SkmiNarLock);
          v324 = SkmiLocateNar(v322);
          if ( v324 && *(_QWORD *)(v324 + 24) == v322 )
          {
            if ( (*(_BYTE *)(v324 + 78) & 8) != 0 )
            {
              inited = SkmiExpandLargeReservedNteRange(v324);
              SkReleasePushLockExclusive(&SkmiNarLock);
LABEL_683:
              v287 = KeGetPcr()->NtTib.StackBase;
              if ( v287 )
              {
                v288 = v287[18];
                if ( v288 )
                {
                  v232 = (*(_WORD *)(v288 + xmmword_140167150))++ == 0xFFFF;
                  if ( v232
                    && *(_QWORD *)(v288 + xmmword_140167160) != (_QWORD)xmmword_140167160 + v287[17]
                    && !*(_WORD *)(v288 + *((_QWORD *)&xmmword_140167150 + 1)) )
                  {
                    SkiCheckForKernelApcDelivery();
                  }
                }
              }
              goto LABEL_1253;
            }
          }
          else
          {
LABEL_748:
            inited = -1073741800;
          }
          SkReleasePushLockExclusive(&SkmiNarLock);
          goto LABEL_683;
        case 80:
          Thread = SkProvisionDumpKeys();
          goto LABEL_1252;
        case 81:
        case 82:
        case 83:
          inited = -1073741822;
          goto LABEL_1254;
        case 84:
          SecurePool = SkSpCreateSecurePool(*(_QWORD *)(v4 + 8));
          *(_QWORD *)(v4 + 16) = SecurePool;
          inited = -1073741670;
          if ( SecurePool )
            inited = 0;
          goto LABEL_1253;
        case 85:
          LOBYTE(v25) = 1;
          SkobCloseHandleEx(*(_QWORD *)(v4 + 8), 0, 0, v25, 0);
          goto LABEL_624;
        case 86:
          v184 = *(_QWORD *)(v4 + 32);
          v185 = *(_QWORD *)(v4 + 24);
          *(_QWORD *)v554 = 0;
          v186 = SkmmMapDataTransfer(v185, v184, 1, (unsigned int)v554, 0);
          v187 = *(PUCHAR *)v554;
          inited = v186;
          if ( v186 >= 0 )
          {
            v188 = *(_QWORD *)(v4 + 16);
            if ( *(_DWORD *)(*(_QWORD *)v554 + 40LL) == v188 )
            {
              v189 = SecurePoolAllocate(
                       *(_QWORD *)(v4 + 8),
                       *(_DWORD *)(v4 + 48),
                       v188,
                       *(_QWORD *)(*(_QWORD *)v554 + 24LL),
                       *(_QWORD *)(v4 + 40),
                       *(_DWORD *)(v4 + 52),
                       0);
              *(_QWORD *)(v4 + 16) = v189;
              if ( v189 )
                *(_QWORD *)(v4 + 16) = qword_140156A38 + v189;
              inited = 0;
            }
            else
            {
              inited = -1073741811;
            }
          }
LABEL_474:
          if ( v187 )
            SkmmUnmapDataTransfer(v187);
          goto LABEL_1253;
        case 87:
          SecurePoolFree(
            *(_QWORD *)(v4 + 8),
            *(_DWORD *)(v4 + 32),
            *(_QWORD *)(v4 + 16) - qword_140156A38,
            *(_QWORD *)(v4 + 24),
            0);
          goto LABEL_624;
        case 88:
          v190 = *(_QWORD *)(v4 + 48);
          v191 = *(_QWORD *)(v4 + 40);
          *(_QWORD *)v554 = 0;
          v192 = SkmmMapDataTransfer(v191, v190, 1, (unsigned int)v554, 0);
          v193 = *(_QWORD *)v554;
          inited = v192;
          if ( v192 >= 0 )
          {
            v194 = *(_QWORD *)(v4 + 32);
            if ( *(_DWORD *)(*(_QWORD *)v554 + 40LL) == v194 )
            {
              v195 = *(_QWORD *)(v4 + 16) - qword_140156A38;
              v196 = *(_QWORD *)(v4 + 24);
              v197 = *((unsigned __int8 *)KeGetPcr()->NtTib.StackBase + 96);
              v557 = *(PUCHAR *)(*(_QWORD *)v554 + 24LL);
              v198 = *(void **)(v4 + 56);
              *(_QWORD *)cbInput = 0;
              v561[0] = v198;
              LODWORD(v198) = *(_DWORD *)(v4 + 64);
              *(_QWORD *)v554 = 0;
              LODWORD(Src) = (_DWORD)v198;
              v568 = *(_QWORD *)(v4 + 8);
              if ( (int)SkobReferenceObjectByHandle(v568, v197, 0, (unsigned int)&SkSpStateType, (__int64)v554, 0) < 0
                || (v199 = *(_QWORD *)v554, *(_QWORD *)(*(_QWORD *)v554 + 16LL) != qword_14014C218)
                || !*(_QWORD *)(*(_QWORD *)v554 + 24LL) )
              {
                SecurePoolEnvFatalFailure();
              }
              v200 = *(_QWORD **)(*(_QWORD *)v554 + 40LL);
              v201 = v195 - 16;
              if ( (unsigned __int64)(v195 - 16) < *v200
                || v201 >= v200[1]
                || !(unsigned int)RtlCSparseBitmapBitCheck(v200 + 2, (v201 - *v200) >> 4)
                || !(unsigned int)SecurePoolValidate(v568, (unsigned int)Src, v195, v561[0])
                || (*(_DWORD *)(v201 + 8) & 2) == 0
                || *(_BYTE *)(v201 + 12)
                || !v194
                || (v202 = RtlpHpSizeHeap(*(_QWORD *)(v199 + 16), v195 - 16, 0), v202 == -1)
                || (v203 = v202 - 16, v196 >= v203)
                || v194 > v203 - v196 )
              {
                SecurePoolFatalFailure();
              }
              memmove((void *)(v196 + v195), v557, v194);
              SkobDereferenceObject(v199);
              inited = 0;
            }
            else
            {
              inited = -1073741811;
            }
          }
          if ( v193 )
            SkmmUnmapDataTransfer(v193);
          goto LABEL_1253;
        case 89:
          v508 = *(_BYTE *)(v4 + 24);
          v509 = *(_DWORD *)(v4 + 20);
          v510 = *(unsigned int *)(v4 + 16);
          v511 = *(_QWORD *)(v4 + 8);
          v579 = 0;
          v580 = 0;
          if ( (SkmiFlags & 0x20000) == 0 )
          {
            inited = -1073741637;
            goto LABEL_1253;
          }
          LOBYTE(v580) = v508;
          *(_QWORD *)&v579 = v511;
          *((_QWORD *)&v579 + 1) = __PAIR64__(v509, v510);
          Thread = SkmiOperateOnLockedNar(v511, SkmiSetImageTracePoint, &v579, v510);
          goto LABEL_1252;
        case 90:
          Thread = SkTransformDumpKey(*(_QWORD *)(v4 + 8), *(_QWORD *)(v4 + 16));
          goto LABEL_1252;
        case 91:
          v583 = *(_QWORD *)(v4 + 8);
          v584 = 0;
          inited = SkmiOperateOnLockedNar(v583, SkmiPublishSyscallProviderServiceTables, &v583, 255);
          if ( inited < 0 )
            goto LABEL_1254;
          *(_QWORD *)(v4 + 16) = (unsigned int)v584;
          goto LABEL_624;
        case 92:
          Thread = SkmiOperateOnLockedNar(
                     *(_QWORD *)(v4 + 8),
                     SkmiRevokeSyscallProviderServiceTables,
                     *(_QWORD *)(v4 + 8),
                     255);
          goto LABEL_1252;
        case 192:
          v74 = *(_QWORD *)(v4 + 8);
          LOBYTE(v28) = 1;
          v557 = 0;
          inited = SkobReferenceObjectByHandle(v74, 0, v28, (unsigned int)&SkpsProcessType, (__int64)&v557, 0);
          if ( inited < 0 )
            goto LABEL_201;
          v75 = v557;
          if ( (*(_DWORD *)v557 & 2) == 0 )
          {
            inited = -1073740007;
            goto LABEL_200;
          }
          v76 = *((_QWORD *)v557 + 10);
          do
          {
            if ( (v76 & 1) == 0 || v76 == -1 )
              goto LABEL_199;
            v77 = v76;
            v76 = _InterlockedCompareExchange64((volatile signed __int64 *)v75 + 10, v76 + 2, v76);
          }
          while ( v76 != v77 );
          LODWORD(Src) = *(_DWORD *)v75;
          if ( ((unsigned __int16)Src & 0x400) != 0 )
          {
            v78 = *((_QWORD *)v75 + 10);
            while ( (v78 & 1) != 0 )
            {
              v79 = v78;
              v78 = _InterlockedCompareExchange64((volatile signed __int64 *)v75 + 10, v78 - 2, v78);
              if ( v78 == v79 )
                goto LABEL_199;
            }
            if ( _InterlockedExchangeAdd64((volatile signed __int64 *)v78, 0xFFFFFFFFFFFFFFFFuLL) == 1 )
              SkeAlertThreadByThreadId(*(_QWORD *)(v78 + 8));
LABEL_199:
            inited = -1073741816;
            goto LABEL_200;
          }
          v5 = v75;
          inited = 0;
LABEL_200:
          SkobDereferenceObject(v75);
LABEL_201:
          if ( inited < 0 )
            goto LABEL_1254;
          *(_QWORD *)(v4 + 16) = v5[20];
          v80 = v5[10];
          while ( (v80 & 1) != 0 )
          {
            v81 = v80;
            v80 = _InterlockedCompareExchange64(v5 + 10, v80 - 2, v80);
            if ( v80 == v81 )
              goto LABEL_624;
          }
          goto LABEL_215;
        case 193:
          Thread = SkmmValidateSecureImagePages(
                     *(_QWORD *)(v4 + 8),
                     *(_DWORD *)(v4 + 16),
                     *(_DWORD *)(v4 + 20),
                     *(_QWORD *)(v4 + 24),
                     *(_QWORD *)(v4 + 32),
                     *(_QWORD *)(v4 + 40),
                     *(_DWORD *)(v4 + 48));
          goto LABEL_1252;
        case 208:
          v161 = __rdtsc();
          if ( _InterlockedCompareExchange(&g_ExpectedIumInitializationPhase, 1, 0) )
          {
LABEL_409:
            inited = -1073741790;
          }
          else
          {
            if ( SkLoaderApiVersion == 167772178 )
            {
              inited = SkmmMapDataTransfer(*(_QWORD *)(v4 + 8), *(_QWORD *)(v4 + 16), 1, (unsigned int)&v559, 0);
              if ( inited >= 0 )
              {
                v162 = v559;
                inited = SkInitSystem(3);
                if ( inited >= 0 )
                {
                  *(_DWORD *)(v4 + 16) = 167772178;
                  *(_DWORD *)(v4 + 20) = 8;
                }
                SkmmUnmapDataTransfer(v162);
              }
              _InterlockedIncrement(&g_ExpectedIumInitializationPhase);
              SkWritePerfTraceEntry(0, 3, __rdtsc() - v161);
              goto LABEL_1253;
            }
            inited = -1073741735;
          }
          goto LABEL_1254;
        case 209:
          SkRequestWorkCallback();
          v565 = 0;
          if ( (__int64 *)SkmiFallbackTimerList == &SkmiFallbackTimerList )
            goto LABEL_601;
          v243 = 0;
          v244 = SkAcquireSpinLockExclusive(&SkmiFallbackTimerListLock);
          v245 = SkmiFallbackTimerList;
          v246 = v244;
          if ( (__int64 *)SkmiFallbackTimerList == &SkmiFallbackTimerList )
            goto LABEL_599;
          do
          {
            v247 = *(__int64 **)v245;
            v232 = (*(_BYTE *)(v245 + 17))-- == 1;
            if ( v232 )
            {
              if ( v247[1] != v245 )
                goto LABEL_936;
              v248 = *(__int64 ***)(v245 + 8);
              if ( *v248 != (__int64 *)v245 )
                goto LABEL_936;
              *v248 = v247;
              v247[1] = (__int64)v248;
              *(_QWORD *)v245 = 0;
              if ( (unsigned int)SkmiSchedulePagesToFree(v245 - 168) )
                v243 = 1;
            }
            v245 = (__int64)v247;
          }
          while ( v247 != &SkmiFallbackTimerList );
LABEL_599:
          SkmiFallbackTimerListLock = 0;
          SkTrackSpinLockRelease();
          SkeLowerIrql(v246);
          if ( v243 )
            SkQueueWorkItem(&SkmiPagesToFreeWorkItem);
LABEL_601:
          if ( (__int64 *)SkmiDefunctImagesFreeList == &SkmiDefunctImagesFreeList )
            goto LABEL_610;
          v249 = SkAcquireSpinLockExclusive(&SkmiDefunctImagesFreeListLock);
          if ( *(__int64 **)(SkmiDefunctImagesFreeList + 8) != &SkmiDefunctImagesFreeList )
            goto LABEL_936;
          *((_QWORD *)&v565 + 1) = &SkmiDefunctImagesFreeList;
          *(_QWORD *)&v565 = SkmiDefunctImagesFreeList;
          *(_QWORD *)(SkmiDefunctImagesFreeList + 8) = &v565;
          SkmiDefunctImagesFreeList = (__int64)&v565;
          if ( *((__int64 **)&v565 + 1) != &SkmiDefunctImagesFreeList )
            goto LABEL_936;
          v250 = qword_1401566A8;
          if ( *(__int64 **)qword_1401566A8 != &SkmiDefunctImagesFreeList )
            goto LABEL_936;
          *(_QWORD *)qword_1401566A8 = &v565;
          *((_QWORD *)&v565 + 1) = v250;
          qword_1401566A8 = (__int64)&SkmiDefunctImagesFreeList;
          SkmiDefunctImagesFreeList = (__int64)&SkmiDefunctImagesFreeList;
          SkmiDefunctImagesFreeListLock = 0;
          SkTrackSpinLockRelease();
          SkeLowerIrql(v249);
          while ( 1 )
          {
            v251 = v565;
            if ( (__int128 *)v565 == &v565 )
              break;
            if ( *(__int128 **)(v565 + 8) != &v565 )
              goto LABEL_936;
            v252 = *(_QWORD *)v565;
            if ( *(_QWORD *)(*(_QWORD *)v565 + 8LL) != (_QWORD)v565 )
              goto LABEL_936;
            *(_QWORD *)&v565 = *(_QWORD *)v565;
            *(_QWORD *)(v252 + 8) = &v565;
            RtlpHpFreeHeap(qword_14015A9A0, v251 - 48);
          }
LABEL_610:
          SkpgPeriodicEvent();
          while ( SkmiDriverProxyActiveSwapDelayedFreeList != (_UNKNOWN *)&SkmiDriverProxyActiveSwapDelayedFreeList )
          {
            v254 = KeGetCurrentIrql();
            __writecr8(4u);
            SkAcquireSpinLockExclusiveAtDpcLevel(&SkmiDriverProxyActiveSwapDelayedFreeLock);
            v255 = SkmiDriverProxyActiveSwapDelayedFreeList;
            if ( *((_UNKNOWN ***)SkmiDriverProxyActiveSwapDelayedFreeList + 1) != &SkmiDriverProxyActiveSwapDelayedFreeList )
              goto LABEL_936;
            v256 = *(_QWORD *)SkmiDriverProxyActiveSwapDelayedFreeList;
            if ( *(_UNKNOWN **)(*(_QWORD *)SkmiDriverProxyActiveSwapDelayedFreeList + 8LL) != SkmiDriverProxyActiveSwapDelayedFreeList )
              goto LABEL_936;
            SkmiDriverProxyActiveSwapDelayedFreeList = *(_UNKNOWN **)SkmiDriverProxyActiveSwapDelayedFreeList;
            *(_QWORD *)(v256 + 8) = &SkmiDriverProxyActiveSwapDelayedFreeList;
            SkmiDriverProxyActiveSwapDelayedFreeLock = 0;
            SkTrackSpinLockRelease();
            SkeLowerIrql(v254);
            if ( v255[4] )
              SkpgHotpatchDestroy();
            RtlpHpFreeHeap(qword_14015A9A0, (ULONG_PTR)(v255 - 3));
          }
          v257 = dword_14014EFA4;
          v258 = dword_14014EF9C;
          LODWORD(Src) = dword_14014EFA4;
          if ( dword_14014EF9C < (unsigned int)dword_14014EFA4 || (unsigned int)dword_14014EFAC > 1 )
          {
            LOBYTE(v253) = 1;
            SkeComputeNumberOfExtendedXSaveArea(&Src, 0, v253);
            v257 = (int)Src;
          }
          v259 = dword_14014EFA8;
          if ( v258 < v257 - 1 )
          {
            v260 = SkiPreallocateExtendedXSaveArea(v257 - v258);
            if ( v260 < 0 )
            {
              DbgPrint(
                "SkePeriodicXSaveEvent has failed in allocating %i new Extended XSAVE areas for reaching the optimal numb"
                "er. Returned error: 0x%08X.\n",
                v257 - v258,
                v260);
LABEL_623:
              inited = 0;
LABEL_624:
              *((_QWORD *)KeGetPcr()->NtTib.StackBase + 33) = v585;
LABEL_625:
              *(_BYTE *)(v4 + 1) = 1;
              *(_QWORD *)(v4 + 8) = inited;
              return 0;
            }
          }
          if ( v258 <= v259 )
            goto LABEL_641;
          v563 = (__int64 *)&v562;
          v562 = &v562;
          v261 = SkAcquireSpinLockExclusive(&dword_14014EF98);
          v262 = (__int64 *)qword_14014EF88;
          v263 = v261;
          if ( *(__int64 **)(qword_14014EF88 + 8) == &qword_14014EF88 )
          {
            v264 = *(_QWORD *)qword_14014EF88;
            if ( *(_QWORD *)(*(_QWORD *)qword_14014EF88 + 8LL) == qword_14014EF88 )
            {
              v265 = v258 - v257;
              qword_14014EF88 = *(_QWORD *)qword_14014EF88;
              v266 = 0;
              *(_QWORD *)(v264 + 8) = &qword_14014EF88;
              if ( v262 == &qword_14014EF88 )
              {
LABEL_635:
                dword_14014EF9C -= v266;
                dword_14014EF98 = 0;
                SkTrackSpinLockRelease();
                SkeLowerIrql(v263);
                v269 = v562;
                if ( v562[1] == &v562 )
                {
                  v270 = (_QWORD **)*v562;
                  if ( (_QWORD **)(*v562)[1] == v562 )
                  {
                    v562 = (_QWORD **)*v562;
                    v270[1] = &v562;
                    if ( v269 == &v562 )
                    {
LABEL_641:
                      dword_14014EFAC = 0;
                      goto LABEL_623;
                    }
                    while ( 1 )
                    {
                      RtlpHpFreeHeap(qword_14015A9A0, (ULONG_PTR)v269 - *((unsigned int *)v269 + 5));
                      v269 = v562;
                      if ( v562[1] != &v562 )
                        break;
                      v271 = *v562;
                      if ( (_QWORD **)(*v562)[1] != v562 )
                        break;
                      v562 = (_QWORD **)*v562;
                      v271[1] = &v562;
                      if ( v269 == &v562 )
                        goto LABEL_641;
                    }
                  }
                }
              }
              else
              {
                while ( 1 )
                {
                  v267 = (__int64 **)v563;
                  if ( (_QWORD ***)*v563 != &v562 )
                    break;
                  ++v266;
                  *v262 = (__int64)&v562;
                  v262[1] = (__int64)v267;
                  *v267 = v262;
                  v563 = v262;
                  if ( v266 >= v265 )
                    goto LABEL_635;
                  v262 = (__int64 *)qword_14014EF88;
                  if ( *(__int64 **)(qword_14014EF88 + 8) != &qword_14014EF88 )
                    break;
                  v268 = *(_QWORD *)qword_14014EF88;
                  if ( *(_QWORD *)(*(_QWORD *)qword_14014EF88 + 8LL) != qword_14014EF88 )
                    break;
                  qword_14014EF88 = *(_QWORD *)qword_14014EF88;
                  *(_QWORD *)(v268 + 8) = &qword_14014EF88;
                  if ( v262 == &qword_14014EF88 )
                    goto LABEL_635;
                }
              }
            }
          }
          goto LABEL_936;
        case 210:
          if ( (__int64 *)SkpWorkItemList == &SkpWorkItemList )
            goto LABEL_1092;
          while ( 2 )
          {
            v238 = SkAcquireSpinLockExclusive(&SkpWorkItemListLock);
            v239 = SkpWorkItemList;
            v240 = v238;
            if ( (__int64 *)SkpWorkItemList == &SkpWorkItemList )
            {
              v239 = 0;
              SkpWorkItemQueued = 0;
            }
            else
            {
              v241 = *(_QWORD *)SkpWorkItemList;
              if ( *(_QWORD *)(*(_QWORD *)SkpWorkItemList + 8LL) != SkpWorkItemList
                || (v242 = *(_QWORD **)(SkpWorkItemList + 8), *v242 != SkpWorkItemList) )
              {
LABEL_936:
                __fastfail(3u);
              }
              *v242 = v241;
              *(_QWORD *)(v241 + 8) = v242;
              *(_QWORD *)v239 = 0;
            }
            SkpWorkItemListLock = 0;
            SkTrackSpinLockRelease();
            SkeLowerIrql(v240);
            if ( v239 )
            {
              (*(void (__fastcall **)(_QWORD))(v239 + 16))(*(_QWORD *)(v239 + 24));
              continue;
            }
            break;
          }
LABEL_1092:
          inited = 0;
          goto LABEL_624;
        case 211:
          Thread = SkmmReserveProtectedPages(*(_QWORD *)(v4 + 8), *(_QWORD *)(v4 + 16));
          goto LABEL_1252;
        case 212:
          v325 = *(_QWORD *)(v4 + 16);
          v326 = *(_QWORD *)(v4 + 8);
          v597[2] = *(_QWORD *)(v4 + 24);
          v597[0] = v326;
          v597[1] = v325;
          Thread = SkmiOperateOnLockedNar(v326, SkmiApplyNormalDriverDynamicRelocations, v597, 255);
          goto LABEL_1252;
        case 213:
          v438 = *(_QWORD *)(v4 + 56);
          v439 = *(_QWORD *)(v4 + 48);
          v440 = *(_QWORD *)(v4 + 40);
          v441 = *(_BYTE *)(v4 + 32);
          LODWORD(Src) = *(_DWORD *)(v4 + 24);
          v442 = KeGetPcr()->NtTib.StackBase;
          if ( v442 )
          {
            v443 = v442[18];
            if ( v443 )
              --*(_WORD *)(xmmword_140167150 + v443);
          }
          v444 = _InterlockedCompareExchange64(&SkpEtwRegistrationAccessLock, 17, 0);
          if ( v444 )
            RtlpAcquireSRWLockSharedContended(&SkpEtwRegistrationAccessLock, a2, v444, 255);
          v445 = 0;
          v446 = SkAcquireSpinLockShared(&SkpEtwRegistrationListLock);
          v447 = SkpEtwRegistrationListHead;
          v448 = v446;
          if ( SkpEtwRegistrationListHead != (_UNKNOWN *)&SkpEtwRegistrationListHead )
          {
            do
            {
              v445 = v447;
              if ( v447[2] == v438 )
                break;
              v447 = (_QWORD *)*v447;
              v445 = 0;
            }
            while ( v447 != &SkpEtwRegistrationListHead );
          }
          _InterlockedDecrement(&SkpEtwRegistrationListLock);
          SkTrackSpinLockRelease();
          SkeLowerIrql(v448);
          if ( v445 )
            ((void (__fastcall *)(__int64, _QWORD, _QWORD, __int64, __int64, _QWORD, _QWORD))v445[3])(
              v4 + 8,
              (unsigned int)Src,
              v441,
              v440,
              v439,
              0,
              v445[4]);
          RtlReleaseSRWLockShared(&SkpEtwRegistrationAccessLock);
          v449 = KeGetPcr()->NtTib.StackBase;
          if ( v449 )
          {
            v450 = v449[18];
            if ( v450 )
            {
              v232 = (*(_WORD *)(xmmword_140167150 + v450))++ == 0xFFFF;
              if ( v232
                && *(_QWORD *)(xmmword_140167160 + v450) != (_QWORD)xmmword_140167160 + v449[17]
                && !*(_WORD *)(*((_QWORD *)&xmmword_140167150 + 1) + v450) )
              {
                SkiCheckForKernelApcDelivery();
              }
            }
          }
          goto LABEL_623;
        case 214:
          v175 = *(_QWORD *)(v4 + 8);
          v176 = *(_QWORD *)(v4 + 16);
          v572 = 0;
          if ( !v175 || (v175 & 0x1FFFFF) != 0 || !v176 || (v176 & 0x1FFFFF) != 0 )
            goto LABEL_783;
          if ( _InterlockedCompareExchange64(&qword_140156A08, v175, 0) )
          {
            inited = -1073741800;
            goto LABEL_1253;
          }
          if ( v176 > 0x4000000000LL )
            v176 = 0x4000000000LL;
          inited = SkmiReserveNar(v175, v176, 0x10000, 0, 0, 0, (__int64)&v572);
          if ( inited < 0 )
            goto LABEL_1253;
          inited = SkmiFillSparseMappingGaps(
                     ((v175 >> 9) & 0x7FFFFFFFF8LL) - 0xA0000000000LL,
                     ((v175 >> 9) & 0x7FFFFFFFF8LL) - 0xA0000000000LL + 8LL * *(_QWORD *)(v572 + 64),
                     1);
          if ( inited < 0 )
            goto LABEL_1253;
          if ( !(unsigned int)SkmiInitializePoolDescriptor(byte_140156A00, qword_140156B30, v176, 0) )
          {
            inited = -1073741670;
            goto LABEL_1253;
          }
          qword_140156A38 = v175 - qword_140156B30;
          _InterlockedOr(v550, 0);
          dword_140156A04 |= 2u;
          SkmiSecurePoolNar = v572;
          memset_0(&qword_140148938, 0, 0x3D38u);
          qword_140148928 = (__int64)&SecurePoolGlobalState;
          SecurePoolGlobalState = (__int64)&SecurePoolGlobalState;
          v559 = 0x20000004000LL;
          qword_140148930 = 0;
          RtlHpHeapManagerInitialize(&qword_140148938, &v559);
          memset_0(&qword_14014C220, 0, 0x450u);
          memset_0(qword_14014C230, 0, 0x440u);
          dword_14014C264 = 1032;
          qword_14014C250 = -1;
          v178 = RtlHpHeapManagerStart(&qword_140148938, 2, v177, qword_140156A08);
          if ( v178 < 0 )
            goto LABEL_461;
          qword_14014C220 = qword_140156A08;
          qword_14014C228 = qword_140156A08 + 0x8000000000LL;
          v178 = RtlCSparseBitmapStart(qword_14014C230, 0x800000000LL, v179, 1);
          if ( v178 < 0 )
            goto LABEL_461;
          *(_OWORD *)v561 = 0;
          *(_WORD *)((char *)v561 + 1) = 1;
          LOBYTE(v561[0]) = 5;
          v182 = RtlpHpHeapCreate(0, v180, v181, v561);
          qword_14014C218 = v182;
          if ( v182 )
          {
            *(_BYTE *)(v182 + 333) |= 0x10u;
            *(_BYTE *)(qword_14014C218 + 525) |= 0x10u;
            v178 = 0;
LABEL_461:
            inited = 0;
            if ( v178 < 0 )
              inited = v178;
          }
          else
          {
            inited = -1073741801;
          }
          goto LABEL_1253;
        case 215:
          inited = SkmmPrepareNtKernelCfg(*(_QWORD *)(v4 + 8), *(_QWORD *)(v4 + 16));
          if ( inited < 0 )
            goto LABEL_1254;
          v173 = *(_QWORD *)(v4 + 24);
          if ( v173 < 0xFFFF800000000000uLL )
            goto LABEL_783;
          if ( (v173 & 0x7FFFFFFFFFLL) != 0 )
            goto LABEL_783;
          v174 = *(_QWORD *)(v4 + 32);
          if ( (v174 & 0x7FFFFFFFFFLL) != 0 || v173 + v174 - 1 < v173 )
            goto LABEL_783;
          inited = 0;
          SkpgKernelCfgRanges = *(_OWORD *)(v4 + 24);
          SkpgKernelCfgRangesInitialized = 1;
          goto LABEL_1253;
        case 216:
          if ( SkmiNtCfgroInfo )
          {
            *(_QWORD *)(SkmiNtCfgroInfo + 8) = SkmiKernelCfgBitmapBase - 0x3FFFE0000000000LL;
          }
          else
          {
            SKMI_SECURITY(3119);
            inited = -1073741811;
          }
          goto LABEL_1253;
        case 217:
          Thread = SkmmInitializeKscpFunctions();
          goto LABEL_1252;
        case 218:
          v289 = *(_DWORD *)(v4 + 40);
          v290 = *(_DWORD *)(v4 + 32);
          v291 = *(_QWORD *)(v4 + 24);
          v292 = *(_QWORD *)(v4 + 16);
          v293 = *(_QWORD *)(v4 + 8);
          v591 = 0;
          v592 = 0;
          if ( (v289 & 0xFFFFFFFC) != 0 )
          {
            inited = -1073741811;
            goto LABEL_1253;
          }
          *((_QWORD *)&v591 + 1) = v292;
          *((_QWORD *)&v592 + 1) = __PAIR64__(v289, v290);
          *(_QWORD *)&v592 = v293;
          *(_QWORD *)&v591 = v291;
          Thread = SkmiOperateOnLockedNar(v291, SkmiLoadNormalDriver, &v591, v293);
          goto LABEL_1252;
        case 219:
          Thread = SkmiOperateOnLockedNar(*(_QWORD *)(v4 + 8), SkmiUnloadNormalDriver, *(_QWORD *)(v4 + 8), 255);
          goto LABEL_1252;
        case 220:
          if ( (SkmiFlags & 0x10) == 0 )
          {
            inited = -1073741811;
            goto LABEL_1253;
          }
          Thread = SkmiOperateOnLockedNar(*(_QWORD *)(v4 + 8), SkmiMapKernelScpPages, *(_QWORD *)(v4 + 8), 255);
          goto LABEL_1252;
        case 221:
          if ( (SkmiFlags & 0x1000) == 0 )
          {
            inited = -1073741811;
            goto LABEL_1253;
          }
          Thread = SkmiOperateOnLockedNar(
                     *(_QWORD *)(v4 + 8) & 0xFFFFFFFFFFFFFFF0uLL,
                     SkmiEnableNtosCfgTarget,
                     *(_QWORD *)(v4 + 8) & 0xFFFFFFFFFFFFFFF0uLL,
                     255);
          goto LABEL_1252;
        case 222:
          v334 = *(_BYTE *)(v4 + 8);
          v636 = 0;
          v630 = 0;
          v631 = 0;
          v632 = 0;
          v633 = 0;
          v634 = 0;
          v635 = 0;
          if ( (SkmiFlags & 4) != 0 || _InterlockedExchange(&SkmiSlabConfigurationComplete, 1) )
            goto LABEL_783;
          if ( !v334 )
          {
            SkmiFlags |= 8u;
            inited = 0;
            goto LABEL_1253;
          }
          while ( 1 )
          {
            v335 = SkmiBootSlabList;
            if ( (__int64 *)SkmiBootSlabList == &SkmiBootSlabList )
            {
LABEL_532:
              inited = 0;
              goto LABEL_1253;
            }
            v336 = *(_QWORD *)SkmiBootSlabList;
            if ( *(_QWORD *)(*(_QWORD *)SkmiBootSlabList + 8LL) != SkmiBootSlabList )
              goto LABEL_936;
            v337 = *(_QWORD **)(SkmiBootSlabList + 8);
            if ( *v337 != SkmiBootSlabList )
              goto LABEL_936;
            *v337 = v336;
            *(_QWORD *)(v336 + 8) = v337;
            BYTE1(v630) = 0;
            WORD1(v630) = 41;
            *((_QWORD *)&v630 + 1) = *(_QWORD *)(v335 + 32);
            *(_QWORD *)&v631 = 512;
            *((_QWORD *)&v631 + 1) = (unsigned int)SkmiBootSlabProtections[*(int *)(v335 + 24)];
            SkCallNormalMode(&v630);
            RtlpHpFreeHeap(qword_14015A9A0, v335);
          }
        case 223:
          Thread = SkmmReapplyBootDriverHotPatch(*(_QWORD *)(v4 + 8));
          goto LABEL_1252;
        case 224:
          v281 = KeGetPcr()->NtTib.StackBase;
          v282 = *(_QWORD *)(v4 + 8);
          if ( v281 )
          {
            v283 = v281[18];
            if ( v283 )
              --*(_WORD *)(v283 + xmmword_140167150);
          }
          if ( _interlockedbittestandset64((volatile signed __int32 *)&SkmiNarLock, 0) )
            RtlpAcquireSRWLockExclusiveContended(&SkmiNarLock);
          v284 = SkmiLocateNar(v282);
          if ( v284 && (v285 = *(_WORD *)(v284 + 78), (v285 & 6) == 2) && (v285 & 0x80u) == 0 )
          {
            v286 = *(_WORD *)(v284 + 76);
            *(_WORD *)(v284 + 76) = v286 + 1;
            if ( v286 == -1 )
            {
              *(_WORD *)(v284 + 76) = -1;
              inited = -1073741757;
            }
          }
          else
          {
            inited = -1073741637;
          }
          RtlReleaseSRWLockExclusive(&SkmiNarLock);
          goto LABEL_683;
        case 225:
          Thread = SkmmInitializeNtDynamicFixups(*(unsigned int *)(v4 + 8));
          goto LABEL_1252;
        case 226:
          v519 = *(_BYTE *)(v4 + 16);
          v520 = *(_QWORD *)(v4 + 8);
          v576 = 0;
          if ( !_bittest(&SkmiFlags, 0xEu) )
          {
            inited = -1073741811;
            goto LABEL_1253;
          }
          WORD4(v576) = v519;
          *(_QWORD *)&v576 = v520;
          Thread = SkmiOperateOnLockedNar(v520, SkmiApplyDynamicFixupsOnImage, &v576, v520);
          goto LABEL_1252;
        case 227:
          v512 = *(_QWORD *)(v4 + 8);
          v575 = 0;
          if ( (SkmiFlags & 0x8000) == 0 )
          {
            inited = -1073741811;
            goto LABEL_1253;
          }
          *(_QWORD *)&v575 = v512;
          WORD4(v575) = 256;
          Thread = SkmiOperateOnLockedNar(v512, SkmiApplyDynamicFixupsOnImage, &v575, 255);
          goto LABEL_1252;
        case 228:
          v516 = *(_QWORD *)(v4 + 24);
          v517 = *(_QWORD *)(v4 + 16);
          v518 = *(_QWORD *)(v4 + 8);
          v588 = 0;
          v589 = 0;
          if ( (SkmiFlags & 0x8000) == 0 )
          {
            inited = -1073741811;
            goto LABEL_1253;
          }
          v589 = v516;
          *((_QWORD *)&v588 + 1) = v517;
          *(_QWORD *)&v588 = v518;
          Thread = SkmiOperateOnLockedNar(v518, SkmiReapplyImportRelocationsOnImage, &v588, 255);
          goto LABEL_1252;
        case 229:
          v521 = *(_QWORD *)(v4 + 16);
          v522 = *(_QWORD *)(v4 + 8);
          *(_QWORD *)v554 = 0;
          v523 = SkmmMapDataTransfer(v522, v521, 2, (unsigned int)v554, 0);
          v524 = *(_QWORD *)v554;
          inited = v523;
          if ( v523 >= 0 )
          {
            if ( *(_DWORD *)(*(_QWORD *)v554 + 40LL) >= 0x5Au )
            {
              v525 = *(_OWORD **)(*(_QWORD *)v554 + 24LL);
              inited = 0;
              *v525 = xmmword_140156CBC;
              v525[1] = xmmword_140156CCC;
              v525[2] = xmmword_140156CDC;
              v525[3] = xmmword_140156CEC;
              v525[4] = xmmword_140156CFC;
              *(_OWORD *)((char *)v525 + 74) = *(__int128 *)((char *)&xmmword_140156CFC + 10);
              dword_140156D94 |= 1u;
            }
            else
            {
              inited = -1073741811;
            }
          }
          if ( v524 )
            SkmmUnmapDataTransfer(v524);
          goto LABEL_1253;
        case 230:
          v526 = *(_BYTE *)(v4 + 16);
          v582[0] = *(_QWORD *)(v4 + 8);
          v582[1] = v526;
          Thread = SkmiOperateOnLockedNar(v582[0], SkmiPerformFunctionOverridesFixups, v582, 255);
          goto LABEL_1252;
        case 231:
          v527 = KeGetPcr()->NtTib.ExceptionList;
          if ( (dword_140156D94 & 1) == 0 && !v527[157].Handler )
          {
            v528 = *(_DWORD *)(v4 + 16);
            v529 = *(_QWORD *)(v4 + 8) & 0xFFFFFFFFFFF9FFFFuLL;
            if ( (MEMORY[0xFFFFF780000005F0] | MEMORY[0xFFFFF780000003D8]) == v529 && MEMORY[0xFFFFF780000003EC] == v528 )
            {
              inited = 0;
              goto LABEL_1253;
            }
            if ( v529 )
            {
              if ( (~(MEMORY[0xFFFFF780000005F0] | MEMORY[0xFFFFF780000003D8]) & v529) != 0
                || (~MEMORY[0xFFFFF780000003EC] & v528) != 0 )
              {
LABEL_783:
                inited = -1073741811;
                goto LABEL_1253;
              }
              MEMORY[0xFFFFF780000003D8] &= v529;
              MEMORY[0xFFFFF780000005F0] &= v529;
              MEMORY[0xFFFFF780000003EC] &= v528;
              RtlUpdateXSaveSizeAndVolatileFeatures(0xFFFFF780000003D8uLL);
            }
            else
            {
              memset_0((void *)0xFFFFF780000003D8LL, 0, 0x358u);
              SkeFeatureBits &= 0xFF7FFFBFFF7F7FFFuLL;
            }
            SkeEnabledXStateFeatures = MEMORY[0xFFFFF780000003D8];
            LODWORD(SkiXSaveState) = MEMORY[0xFFFFF78000000600];
            dword_14014EF64 = MEMORY[0xFFFFF78000000718];
            SkmmInitFunctionOverridesCapabilities();
            inited = 0;
            goto LABEL_1253;
          }
          inited = -1073741436;
          goto LABEL_1253;
        case 232:
          v530 = *(_DWORD *)(v4 + 20);
          LODWORD(Src) = 0;
          LODWORD(v556) = 0;
          if ( v530 <= 9 )
          {
            inited = SkmmTranslateKernelShadowStackType(*(unsigned int *)(v4 + 24), &v556, &Src, 255);
            if ( inited >= 0 )
            {
              Thread = SkmmCreateNtKernelShadowStack(*(_QWORD *)(v4 + 8), v4 + 32, v531, v4 + 16);
LABEL_1252:
              inited = Thread;
              goto LABEL_1253;
            }
          }
          else
          {
            inited = -1073741811;
          }
          goto LABEL_1254;
        case 233:
          v532 = *(_QWORD *)(v4 + 8);
          *(_OWORD *)BackTraceHash = 0;
          v596 = 0;
          v595 = 0;
          if ( (SkmiFlags & 0x80000) == 0 )
          {
            inited = -1073741637;
            goto LABEL_1253;
          }
          if ( (v532 & 7) != 0 )
          {
            inited = -1073741811;
            goto LABEL_1253;
          }
          *(_QWORD *)BackTraceHash = v532;
          LOBYTE(v596) = 0;
          inited = SkmiOperateOnLockedNar(v532, SkmiCleanupNtKernelShadowStack, BackTraceHash, 255);
          if ( inited < 0 )
          {
            SKMI_SECURITY(3088);
            goto LABEL_1253;
          }
          Thread = SkmiReserveNar(0, 0, 1, 2, 0, BackTraceHash[2], 0);
          goto LABEL_1252;
        case 234:
          v533 = *(unsigned int *)(v4 + 8);
          LODWORD(Src) = 0;
          LODWORD(v556) = 0;
          inited = SkmmTranslateKernelShadowStackType(v533, &v556, &Src, 255);
          if ( inited < 0 )
            goto LABEL_1254;
          Thread = SkmmResetNtKernelShadowStack((unsigned int)v556, (unsigned int)Src, v4 + 16);
          goto LABEL_1252;
        case 235:
          v539 = *(unsigned int *)(v4 + 8);
          *(_QWORD *)v554 = 0;
          if ( (unsigned int)v539 >= 2 )
          {
            inited = -1073741811;
            goto LABEL_1253;
          }
          v540 = &SkmiServiceTableMetadata[v539];
          if ( *v540 )
          {
            inited = -1073741790;
            goto LABEL_1253;
          }
          inited = SkmmMapDataTransfer(*(_QWORD *)(v4 + 16), *(_QWORD *)(v4 + 24), 1, (unsigned int)v554, 0);
          if ( inited < 0 )
            goto LABEL_1253;
          v218 = *(_QWORD *)v554;
          v541 = *(unsigned int *)(*(_QWORD *)v554 + 40LL);
          if ( (unsigned int)v541 > 0x1388 )
          {
            inited = -1073741811;
            SkmmUnmapDataTransfer(*(_QWORD *)v554);
            goto LABEL_1253;
          }
          v542 = (_DWORD *)SkAllocatePool(1, (unsigned int)(v541 + 4), 1666411347);
          v543 = v542;
          if ( !v542 )
          {
LABEL_537:
            inited = -1073741670;
            SkmmUnmapDataTransfer(v218);
            goto LABEL_1253;
          }
          *v542 = v541;
          memmove(v542 + 1, *(const void **)(v218 + 24), v541);
          SkmmUnmapDataTransfer(v218);
          v544 = 0;
          if ( !*v543 )
            goto LABEL_1236;
          do
          {
            *((_BYTE *)v543 + v544 + 4) >>= 2;
            if ( *((_BYTE *)v543 + v544 + 4) > 0xEu )
            {
              inited = -1073741811;
              RtlpHpFreeHeap(qword_14015A9A0, (ULONG_PTR)v543);
              goto LABEL_1253;
            }
            v544 = (unsigned int)(v544 + 1);
          }
          while ( (unsigned int)v544 < *v543 );
LABEL_1236:
          if ( _InterlockedCompareExchange64(v540, (signed __int64)v543, 0) )
          {
            inited = -1073741790;
            RtlpHpFreeHeap(qword_14015A9A0, (ULONG_PTR)v543);
            goto LABEL_1253;
          }
          goto LABEL_532;
        case 236:
          v534 = *(unsigned int *)(v4 + 16);
          *(_QWORD *)v554 = 0;
          v535 = 24 * v534;
          if ( (unsigned __int64)(24 * v534) > 0xFFFFFFFF )
            goto LABEL_783;
          v536 = v535;
          inited = SkmmMapReadOnlyNtosData(*(_QWORD *)(v4 + 8), v535, v554, 255);
          if ( inited >= 0 )
          {
            v537 = *(_QWORD *)v554;
            if ( _InterlockedCompareExchange64(&SkmiNtServiceDescriptorGroupTable, *(signed __int64 *)v554, 0) )
            {
              inited = -1073741790;
              SkmmUnmapReadOnlyNtosData(*(_QWORD *)v554, (unsigned int)v536);
            }
            else
            {
              SkmiNtServiceDescriptorGroupTableEntries = v534;
              v538 = SkSpCreateSecurePool(0);
              if ( v538 )
              {
                SkmiScPrvSecurePool = v538;
                inited = 0;
              }
              else
              {
                SkmiNtServiceDescriptorGroupTableEntries = 0;
                inited = -1073741670;
                SkmiNtServiceDescriptorGroupTable = 0;
                SkmmUnmapReadOnlyNtosData(v537, v536);
              }
            }
          }
          goto LABEL_1253;
        case 256:
          LOBYTE(v28) = 1;
          inited = SkobReferenceObjectByHandle(
                     *(_QWORD *)(v4 + 8),
                     0,
                     v28,
                     (unsigned int)&SkpsProcessType,
                     (__int64)&Src,
                     0);
          if ( inited < 0 )
            goto LABEL_1254;
          SkmmFlushAddressSpace(Src);
          SkobDereferenceObject(Src);
          goto LABEL_624;
        case 257:
          v204 = *(_QWORD *)(v4 + 8);
          if ( v204 )
          {
            LOBYTE(v28) = 1;
            inited = SkobReferenceObjectByHandle(v204, 0, v28, (unsigned int)&SkpsProcessType, (__int64)&Src, 0);
            if ( inited < 0 )
              goto LABEL_1254;
            v5 = Src;
            v205 = Src;
          }
          else
          {
            v205 = 0;
          }
          v206 = 0;
          do
          {
            if ( !*(_QWORD *)(v4 + 8 * v206 + 16) )
              break;
            v206 = (unsigned int)(v206 + 1);
          }
          while ( (unsigned int)v206 < 0xB );
          v207 = KeGetCurrentIrql();
          __writecr8(2u);
          v208 = (unsigned __int8)SkmiFlushRangeList(v205, v4 + 16, v206, v25);
          SkeLowerIrql(v207);
          *(_QWORD *)(v4 + 16) = v208;
          if ( !v5 )
            goto LABEL_1253;
          goto LABEL_506;
        case 258:
          v209 = *(_QWORD *)(v4 + 8);
          if ( v209 )
          {
            LOBYTE(v28) = 1;
            inited = SkobReferenceObjectByHandle(v209, 0, v28, (unsigned int)&SkpsProcessType, (__int64)&Src, 0);
            if ( inited < 0 )
              goto LABEL_1254;
            v5 = Src;
            v210 = Src;
          }
          else
          {
            v210 = 0;
          }
          inited = SkmmSlowFlushRangeList(
                     (_DWORD)v210,
                     *(_QWORD *)(v4 + 16),
                     *(_DWORD *)(v4 + 24),
                     *(_DWORD *)(v4 + 32),
                     v4 + 16);
          if ( !v210 )
            goto LABEL_1253;
LABEL_506:
          SkobDereferenceObject(v5);
          goto LABEL_1253;
        case 259:
          Thread = SkmmRemoveProtectedPage(*(_QWORD *)(v4 + 8));
          goto LABEL_1252;
        case 260:
          Thread = SkmmCopyProtectedPage(*(_QWORD *)(v4 + 8), *(_QWORD *)(v4 + 56), *(_BYTE *)(v4 + 64));
          goto LABEL_1252;
        case 261:
          Thread = SkmmWriteProtectedPage(v4 + 8);
          goto LABEL_1252;
        case 262:
          Thread = SkmmRegisterProtectedPage(*(_QWORD *)(v4 + 8), *(_QWORD *)(v4 + 16));
          goto LABEL_1252;
        case 263:
          Thread = SkmmSetProtectedPte(*(_QWORD *)(v4 + 8));
          goto LABEL_1252;
        case 264:
          v275 = *(_BYTE *)(v4 + 8) & 1;
          v276 = *(_QWORD *)(v4 + 8) - v275;
          if ( !v276 )
          {
            SkmiQueryNteAccessState(v4 + 16);
            goto LABEL_1253;
          }
          Thread = SkmiQuerySecurePteAccessState(v276, v275, v4 + 16);
          goto LABEL_1252;
        case 265:
          Thread = SkmmValidateProtectedPageTables(v4 + 16, v4 + 24, v4 + 32, v4 + 40);
          goto LABEL_1252;
        case 266:
          if ( (*(_DWORD *)(v4 + 40) & 1) == 0 )
          {
            inited = -1073741819;
            goto LABEL_1253;
          }
          Thread = SkmiDemandFillNormalKernelPage(*(_QWORD *)(v4 + 8), *(_QWORD *)(v4 + 16));
          goto LABEL_1252;
        case 267:
          SkmmQueryStrongCodeFeatures(v4);
          goto LABEL_624;
        case 268:
          Thread = SkhalEfiInvokeRuntimeService(
                     *(_DWORD *)(v4 + 8),
                     *(_QWORD *)(v4 + 16),
                     *(_QWORD *)(v4 + 24),
                     (int)v4 + 32,
                     v4 + 40);
          goto LABEL_1252;
        case 269:
          Thread = SkLiveDumpCollect(*(_QWORD *)(v4 + 8));
          goto LABEL_1252;
        case 270:
          Thread = SkmmRegisterFailureLog(*(_QWORD *)(v4 + 8), *(_QWORD *)(v4 + 16));
          goto LABEL_1252;
        case 272:
          v327 = *(_QWORD *)(v4 + 8);
          v328 = *(_DWORD *)(v4 + 32);
          v329 = *(unsigned int *)(v4 + 24);
          v330 = *(_QWORD *)(v4 + 16);
          BugCheckParameter3 = v327;
          LODWORD(Src) = 0;
          LODWORD(v556) = 0;
          if ( v327 > 0xFFFFFFFFFFLL || v330 + v327 <= v327 || v330 + v327 - 1 > 0xFFFFFFFFFFLL )
          {
            SKMI_SECURITY(2052);
            goto LABEL_783;
          }
          if ( !(unsigned int)SkmiPlaceholderPfnClass(v329, &v556) || !(unsigned int)SkmiPlaceholderPfnClass(v328, &Src) )
            goto LABEL_783;
          v332 = (unsigned int)Src;
          if ( v328 )
            v333 = (unsigned int)((_DWORD)Src + 40);
          else
            v333 = 1025;
          if ( (unsigned int)SkmiInterlockedFillPfnEntries(v331, v330, (unsigned int)v556, v333) )
          {
            if ( v328 )
              SkmiProtectPlaceholderPages((ULONG_PTR)&BugCheckParameter3);
            else
              SkmiProtectPageRange(BugCheckParameter3);
            SkmiFillPfnEntries(BugCheckParameter3, v330, v332);
            inited = 0;
          }
          else
          {
            SKMI_SECURITY(2051);
            inited = -1073741800;
          }
          goto LABEL_1253;
        case 273:
          Thread = SkeQuerySpeculationFeaturesInformation(v4 + 8);
          goto LABEL_1252;
        case 274:
          Thread = SkmmProtectKernelDataPage(*(_QWORD *)(v4 + 8));
          goto LABEL_1252;
        case 275:
          v545 = *(_DWORD *)(v4 + 16);
          v546 = *(_QWORD *)(v4 + 32);
          v547 = *(_QWORD *)(v4 + 24);
          v548 = *(_QWORD *)(v4 + 8);
          v609 = 0;
          v610 = 0;
          if ( v545 - 512 <= 0xFFFFFDFE )
          {
            inited = -1073741811;
            goto LABEL_1253;
          }
          if ( (dword_14014E94C & 0x10000000) == 0 )
          {
            inited = -1073741637;
            goto LABEL_1253;
          }
          v581 = v548;
          SkmiClaimPhysicalPages(&v581, 1, 1, 255);
          if ( v545 == -1 )
          {
            v590 = v547;
            SkmiClaimPhysicalPages(&v590, 1, 1, v549);
            *(_QWORD *)&v610 = v547;
            DWORD2(v609) = -1;
            *(_QWORD *)&v609 = v548;
            inited = SkeGenericIpiCall(0, 2, SkmiWriteNtPtesWorker, &v609);
          }
          else
          {
            *((_QWORD *)&v610 + 1) = v546;
            *(_QWORD *)&v610 = -1;
            DWORD2(v609) = v545;
            *(_QWORD *)&v609 = v548;
            inited = SkeGenericIpiCall(0, 2, SkmiWriteNtPtesWorker, &v609);
            if ( v545 < 0x200 )
              goto LABEL_1250;
          }
          SkmiDecrementPageReferenceCount(v547);
LABEL_1250:
          SkmiDecrementPageReferenceCount(v548);
          goto LABEL_1253;
        case 276:
          Thread = SkmmRebuildLargeNtes(*(_QWORD *)(v4 + 8), *(_QWORD *)(v4 + 16));
          goto LABEL_1252;
        case 277:
          v436 = *(unsigned int *)(v4 + 16);
          if ( (v436 & 0xFFFFFFFC) != 0 )
          {
            inited = -1073741811;
            goto LABEL_1254;
          }
          Thread = SkpgVerifyPage(*(_QWORD *)(v4 + 8), v436, 0, 255);
          goto LABEL_1252;
        case 278:
          Thread = SkPrepareForHibernate(*(_QWORD *)(v4 + 8));
          goto LABEL_1252;
        case 279:
          SkPrepareForCrashDump(*(unsigned __int8 *)(v4 + 8));
          IumpLimitedDispatchFromNormalDispatch = 1;
          goto LABEL_624;
        case 280:
          Thread = SkhalReportBugCheckProgress(
                     *(_DWORD *)(v4 + 8),
                     (int)v4 + 16,
                     *(_QWORD *)(v4 + 32),
                     *(_DWORD *)(v4 + 40),
                     *(_DWORD *)(v4 + 48));
          goto LABEL_1252;
        case 281:
          SkeSwapHiberShadowStacks(*(_QWORD *)(v4 + 8));
          goto LABEL_624;
        case 282:
          if ( !byte_1401483C8 )
          {
            v272 = KeGetPcr()->NtTib.StackBase;
            if ( v272 )
            {
              v273 = v272[18];
              if ( v273 )
                --*(_WORD *)(v273 + xmmword_140167150);
            }
            v274 = _InterlockedCompareExchange64(&qword_1401484C0, 17, 0);
            if ( v274 )
              RtlpAcquireSRWLockSharedContended(&qword_1401484C0, a2, v274, 255);
            byte_1401483C8 = 1;
          }
          goto LABEL_624;
        case 283:
          v476 = *(UCHAR **)(v4 + 8);
          v477 = *(_DWORD *)(v4 + 16);
          v557 = v476;
          *(_DWORD *)(v4 + 16) = 0;
          if ( (v477 & 1) != 0 )
          {
            if ( _bittest(&SkpnpSdevDeviceTypesAvailable, 1u) || (SkpnpIoProtectionPolicy & 2) != 0 )
            {
              *(_DWORD *)(v4 + 16) |= 1u;
              inited = 0;
              goto LABEL_624;
            }
          }
          else if ( (v477 & 2) != 0 )
          {
            if ( !_bittest(&SkpnpSdevDeviceTypesAvailable, 1u) && (SkpnpIoProtectionPolicy & 2) == 0 )
            {
              *(_BYTE *)(v4 + 16) = -1;
              inited = 0;
              goto LABEL_624;
            }
            LOBYTE(v556) = 0;
            v599 = 0;
            SkhalpPciAcquireSegmentFunctionTreeLock((unsigned int)v476, &v556);
            FunctionInTree = SkhalpPciFindFunctionInTree((unsigned int)v476, BYTE4(v557), BYTE5(v557), BYTE6(v557));
            SkhalpPciReleaseSegmentFunctionTreeLock((unsigned int)v476, (unsigned __int8)v556);
            if ( !FunctionInTree
              || (*(_DWORD *)(FunctionInTree + 40) & 1) == 0
              || (v479 = *(_QWORD *)(FunctionInTree + 32),
                  *(_DWORD *)v560 = 0,
                  (unsigned int)SkpnpGetDmaTargetsExposedToVtl0(v479, 0, v560) != -1073741789)
              || *(_DWORD *)v560 != 1
              || (int)SkpnpGetDmaTargetsExposedToVtl0(*(_QWORD *)(FunctionInTree + 32), &v599, v560) < 0 )
            {
              inited = 0;
              *(_BYTE *)(v4 + 16) = -1;
              goto LABEL_624;
            }
            v480 = BYTE14(v599);
            if ( (_DWORD)v599 != 1 )
              v480 = -1;
            *(_BYTE *)(v4 + 16) = v480;
          }
          inited = 0;
          goto LABEL_624;
        case 284:
          v495 = *(_DWORD *)(v4 + 32);
          if ( v495 > 0x40 )
          {
            inited = -2147483643;
            goto LABEL_1254;
          }
          Thread = SkhalAccessPciDevice(
                     0,
                     *(unsigned __int8 *)(v4 + 8),
                     *(unsigned int *)(v4 + 12),
                     *(unsigned int *)(v4 + 16),
                     *(_DWORD *)(v4 + 20),
                     *(_DWORD *)(v4 + 24),
                     *(_DWORD *)(v4 + 28),
                     v495,
                     v4 + 40);
          goto LABEL_1252;
        case 285:
          v481 = (_BYTE *)(v4 + 20);
          LOBYTE(v556) = 0;
          if ( v4 == -20 )
            goto LABEL_783;
          v482 = (_QWORD *)(v4 + 32);
          if ( v4 == -32 || v4 == -24 )
            goto LABEL_783;
          v483 = *(unsigned int *)(v4 + 8);
          v484 = *(unsigned int *)(v4 + 16);
          v485 = *(_BYTE *)(v4 + 14);
          v486 = *(_BYTE *)(v4 + 13);
          v487 = *(_BYTE *)(v4 + 12);
          *v481 = 0;
          *v482 = 0;
          *(_QWORD *)(v4 + 24) = 0;
          LODWORD(Src) = v483;
          SkhalpPciAcquireSegmentFunctionTreeLock(v483, &v556);
          v488 = SkhalpPciFindFunctionInTree((unsigned int)Src, v487, v486, v485);
          v490 = v488;
          if ( !v488 )
          {
            inited = -1073741810;
            SkhalpPciReleaseSegmentFunctionTreeLock(v489, (unsigned __int8)v556);
            goto LABEL_1253;
          }
          if ( (*(_DWORD *)(v488 + 40) & 1) == 0 )
          {
            inited = -1073741637;
            SkhalpPciReleaseSegmentFunctionTreeLock(v489, (unsigned __int8)v556);
            goto LABEL_1253;
          }
          if ( (unsigned int)v484 >= 6 )
            goto LABEL_1130;
          v491 = *(_BYTE *)(v488 + 57);
          if ( v491 == 1 )
          {
            v492 = (unsigned int)v484 < 2;
          }
          else
          {
            if ( v491 != 2 )
              goto LABEL_1128;
            v492 = (unsigned int)v484 < 5;
          }
          if ( !v492 )
          {
LABEL_1130:
            inited = -1073741811;
            goto LABEL_1131;
          }
LABEL_1128:
          inited = 0;
          if ( !*(_BYTE *)(v490 + 24 * v484 + 225) )
          {
            *v481 = 1;
            *v482 = *(_QWORD *)(v490 + 24 * v484 + 216);
            v493 = *(_QWORD *)(v490 + 24 * v484 + 208);
            v494 = (unsigned __int8)v556;
            *(_QWORD *)(v4 + 24) = v493;
            SkhalpPciReleaseSegmentFunctionTreeLock(v489, v494);
            goto LABEL_1253;
          }
LABEL_1131:
          SkhalpPciReleaseSegmentFunctionTreeLock(v489, (unsigned __int8)v556);
          goto LABEL_1253;
        case 286:
          goto LABEL_624;
        case 287:
          v612 = 0;
          v613 = 0;
          v614 = 0;
          v615 = 0;
          v616 = 0;
          v617 = 0;
          if ( qword_1401483C0 )
          {
            v612 = *(_OWORD *)(v4 + 8);
            v613 = *(_OWORD *)(v4 + 24);
            v614 = *(_OWORD *)(v4 + 40);
            v615 = *(_OWORD *)(v4 + 56);
            v616 = *(_OWORD *)(v4 + 72);
            v617 = *(_OWORD *)(v4 + 88);
            qword_1401483C0(&v612);
            *(_OWORD *)(v4 + 8) = v612;
            *(_OWORD *)(v4 + 24) = v613;
            *(_OWORD *)(v4 + 40) = v614;
            *(_OWORD *)(v4 + 56) = v615;
            *(_OWORD *)(v4 + 72) = v616;
            *(_OWORD *)(v4 + 88) = v617;
            inited = *(_DWORD *)(v4 + 8);
          }
          else
          {
            inited = -1073741637;
          }
          goto LABEL_1253;
        case 288:
          v618 = 0;
          v619 = 0;
          v620 = 0;
          v621 = 0;
          v622 = 0;
          v623 = 0;
          v624 = 0;
          v625 = 0;
          v626 = 0;
          v627 = 0;
          v628 = 0;
          v629 = 0;
          if ( qword_140169010 )
          {
            v618 = *(_OWORD *)(v4 + 8);
            v619 = *(_OWORD *)(v4 + 24);
            v620 = *(_OWORD *)(v4 + 40);
            v621 = *(_OWORD *)(v4 + 56);
            v622 = *(_OWORD *)(v4 + 72);
            v623 = *(_OWORD *)(v4 + 88);
            qword_140169010(&v618, &v624);
            *(_OWORD *)(v4 + 8) = v624;
            *(_OWORD *)(v4 + 24) = v625;
            *(_OWORD *)(v4 + 40) = v626;
            *(_OWORD *)(v4 + 56) = v627;
            *(_OWORD *)(v4 + 72) = v628;
            *(_OWORD *)(v4 + 88) = v629;
            inited = *(_DWORD *)(v4 + 8);
          }
          else
          {
            inited = -1073741637;
          }
          goto LABEL_1253;
        case 290:
          Thread = SkmmNtKernelShadowStackAssist(
                     *(_DWORD *)(v4 + 8),
                     *(_QWORD *)(v4 + 16),
                     *(_QWORD *)(v4 + 24),
                     *(_QWORD *)(v4 + 32),
                     *(_QWORD *)(v4 + 40),
                     *(_DWORD *)(v4 + 48));
          goto LABEL_1252;
        case 291:
          Thread = SkpnppSwdValidateTrustlet();
          goto LABEL_1252;
        case 292:
          Thread = SkhalConfigureSecureAtsDevice(v4 + 8, v4 + 20);
          goto LABEL_1252;
        case 293:
          Thread = SkProduceRuntimeSignedReport(
                     *(unsigned __int16 *)(v4 + 8),
                     *(_QWORD *)(v4 + 16),
                     (int)v4 + 24,
                     *(_QWORD *)(v4 + 56),
                     *(_QWORD *)(v4 + 64),
                     v4 + 72);
          goto LABEL_1252;
        case 294:
          Thread = SkTerminate();
          goto LABEL_1252;
        default:
          goto LABEL_1257;
      }
    }
LABEL_50:
    if ( KeGetCurrentIrql() >= 2u )
      goto LABEL_51;
    goto LABEL_52;
  }
  if ( !SkiMirrorOwner )
  {
LABEL_9:
    v7 = 0;
    goto LABEL_19;
  }
  if ( *(_WORD *)(a1 + 2) != 279 )
  {
    v8 = SkiMirrorOwner;
    for ( m = (__int64)KeGetPcr()->NtTib.ExceptionList | 1; SkiMirrorOwner; v8 = SkiMirrorOwner )
    {
      if ( v8 == 1 && (unsigned __int64)_InterlockedCompareExchange64(&SkiMirrorOwner, m, 1) < 2 )
        break;
      _mm_pause();
    }
    goto LABEL_9;
  }
  SkiHibernateAborted = 1;
  _InterlockedExchange64(&SkiBarrierWait, 0);
  _InterlockedExchange64(&SkiMirrorOwner, 0);
  v7 = 0;
LABEL_19:
  IumpInvokeLimitedModeSecureService(v4, v7);
  if ( SkiMirrorOwner )
    _InterlockedCompareExchange64(&SkiMirrorOwner, 1, (__int64)KeGetPcr()->NtTib.ExceptionList | 1);
  return 0;
}

```

## disassembly

```asm
0x140014dd0  push    rbp
0x140014dd2  push    r12
0x140014dd4  push    r13
0x140014dd6  push    r14
0x140014dd8  push    r15
0x140014dda  lea     rbp, [rsp-3F0h]
0x140014de2  sub     rsp, 4F0h
0x140014de9  mov     rax, cs:__security_cookie
0x140014df0  xor     rax, rsp
0x140014df3  mov     [rbp+410h+var_40], rax
0x140014dfa  mov     eax, cs:SkiUnrestrictedThreadCount
0x140014e00  xor     r15d, r15d
0x140014e03  mov     qword ptr [rsp+510h+var_4B0], rcx
0x140014e08  mov     r14, rcx
0x140014e0b  mov     [rbp+410h+var_488], r15
0x140014e0f  mov     r13d, r15d
0x140014e12  mov     [rsp+510h+Src], r15
0x140014e17  mov     r12d, r15d
0x140014e1a  mov     [rsp+510h+var_4A0], r15
0x140014e1f  mov     [rsp+510h+var_498], r15
0x140014e24  mov     [rbp+410h+var_450], r15
0x140014e28  test    eax, eax
0x140014e2a  jns     loc_140014EB1
0x140014e30  mov     rax, cs:SkiMirrorOwner
0x140014e37  mov     r15d, 1
0x140014e3d  test    rax, rax
0x140014e40  jz      short loc_140014EAA
0x140014e42  mov     eax, 117h
0x140014e47  cmp     [rcx+2], ax
0x140014e4b  jnz     short loc_140014E6D
0x140014e4d  xor     eax, eax
0x140014e4f  mov     cs:SkiHibernateAborted, r15d
0x140014e56  xchg    rax, cs:SkiBarrierWait
0x140014e5d  xor     ecx, ecx
0x140014e5f  xchg    rcx, cs:SkiMirrorOwner
0x140014e66  xor     edx, edx
0x140014e68  jmp     loc_140014F38
0x140014e6d  mov     rcx, gs:0
0x140014e76  mov     rax, cs:SkiMirrorOwner
0x140014e7d  or      rcx, r15
0x140014e80  test    rax, rax
0x140014e83  jz      short loc_140014EAA
0x140014e85  cmp     rax, r15
0x140014e88  jnz     short loc_140014E9C
0x140014e8a  mov     rax, r15
0x140014e8d  lock cmpxchg cs:SkiMirrorOwner, rcx
0x140014e96  cmp     rax, 2
0x140014e9a  jb      short loc_140014EAA
0x140014e9c  pause
0x140014e9e  mov     rax, cs:SkiMirrorOwner
0x140014ea5  test    rax, rax
0x140014ea8  jnz     short loc_140014E85
0x140014eaa  xor     edx, edx
0x140014eac  jmp     loc_140014F38
0x140014eb1  cmp     cs:IumpLimitedDispatchFromNormalDispatch, r12b
0x140014eb8  jz      loc_140014F68
0x140014ebe  mov     rax, cs:SkiMirrorOwner
0x140014ec5  mov     r15d, 1
0x140014ecb  test    rax, rax
0x140014ece  jz      short loc_140014F35
0x140014ed0  mov     eax, 117h
0x140014ed5  cmp     [rcx+2], ax
0x140014ed9  jnz     short loc_140014EF6
0x140014edb  xor     eax, eax
0x140014edd  mov     cs:SkiHibernateAborted, r15d
0x140014ee4  xchg    rax, cs:SkiBarrierWait
0x140014eeb  xor     ecx, ecx
0x140014eed  xchg    rcx, cs:SkiMirrorOwner
0x140014ef4  jmp     short loc_140014F35
0x140014ef6  mov     rcx, gs:0
0x140014eff  mov     rax, cs:SkiMirrorOwner
0x140014f06  or      rcx, r15
0x140014f09  test    rax, rax
0x140014f0c  jz      short loc_140014F35
0x140014f0e  xchg    ax, ax
0x140014f10  cmp     rax, r15
0x140014f13  jnz     short loc_140014F27
0x140014f15  mov     rax, r15
0x140014f18  lock cmpxchg cs:SkiMirrorOwner, rcx
0x140014f21  cmp     rax, 2
0x140014f25  jb      short loc_140014F35
0x140014f27  pause
0x140014f29  mov     rax, cs:SkiMirrorOwner
0x140014f30  test    rax, rax
0x140014f33  jnz     short loc_140014F10
0x140014f35  mov     edx, r15d
0x140014f38  mov     rcx, r14
0x140014f3b  call    IumpInvokeLimitedModeSecureService
0x140014f40  mov     rax, cs:SkiMirrorOwner
0x140014f47  test    rax, rax
0x140014f4a  jz      short loc_140014F61
0x140014f4c  mov     rax, gs:0
0x140014f55  or      rax, r15
0x140014f58  lock cmpxchg cs:SkiMirrorOwner, r15
0x140014f61  xor     al, al
0x140014f63  jmp     loc_14001B08C
0x140014f68  mov     eax, cs:SkeNtKernelImportsInitialized
0x140014f6e  movzx   ecx, byte ptr [rcx]
0x140014f71  mov     [rsp+510h+arg_10], rbx
0x140014f79  mov     [rsp+510h+var_28], rsi
0x140014f81  mov     [rsp+510h+var_30], rdi
0x140014f89  cmp     eax, 2
0x140014f8c  jz      loc_1400150CF
0x140014f92  cmp     cl, 2
0x140014f95  jnz     loc_1400150BA
0x140014f9b  mov     eax, 10Fh
0x140014fa0  cmp     [r14+2], ax
0x140014fa5  jnz     loc_1400150BA
0x140014fab  xorps   xmm0, xmm0
0x140014fae  mov     [rbp+410h+var_254], r15
0x140014fb5  movdqa  [rbp+410h+var_230], xmm0
0x140014fbd  mov     [rbp+410h+var_24C], r15
0x140014fc4  mov     [rbp+410h+var_244], r15d
0x140014fcb  cmp     qword ptr [r14+10h], 0B0h
0x140014fd3  jnz     loc_1400150BA
0x140014fd9  mov     rcx, [r14+8]
0x140014fdd  lea     r9, [r14+18h]
0x140014fe1  mov     edx, ecx
0x140014fe3  mov     [rbp+410h+var_260], r15
0x140014fea  mov     r8d, edx
0x140014fed  mov     [rbp+410h+var_238], 0B0h
0x140014ff7  and     r8d, 0FFFh
0x140014ffe  and     rcx, 0FFFFFFFFFFFFF000h
0x140015005  add     r8, 10AFh
0x14001500c  mov     [rbp+410h+var_240], rcx
0x140015013  shr     r8, 0Ch
0x140015017  lea     rcx, [rbp+410h+var_230]
0x14001501e  and     edx, 0FFFh
0x140015024  mov     [rbp+410h+var_234], edx
0x14001502a  lea     eax, [r8+6]
0x14001502e  shl     ax, 3
0x140015032  mov     [rbp+410h+var_258], ax
0x140015039  mov     eax, r15d
0x14001503c  mov     [rbp+410h+var_256], ax
0x140015043  test    r8d, r8d
0x140015046  jz      short loc_14001506A
0x140015048  mov     edx, 0FFFFFFFFh
0x14001504d  nop     dword ptr [rax]
0x140015050  mov     rax, [r9]
0x140015053  lea     r9, [r9+8]
0x140015057  mov     [rcx], rax
0x14001505a  lea     rcx, [rcx+8]
0x14001505e  add     r8d, edx
0x140015061  jnz     short loc_140015050
0x140015063  movzx   eax, [rbp+410h+var_256]
0x14001506a  or      ax, 2
0x14001506e  lea     rcx, [rbp+410h+var_260]
0x140015075  mov     edx, 1
0x14001507a  mov     [rbp+410h+var_256], ax
0x140015081  call    SkmmMapMdl
0x140015086  mov     edi, eax
0x140015088  test    eax, eax
0x14001508a  js      loc_140017C0B
0x140015090  mov     rcx, [rbp+410h+var_24C+4]
0x140015097  call    SkeSetNtKernelImports
0x14001509c  lea     rcx, [rbp+410h+var_260]
0x1400150a3  mov     edi, eax
0x1400150a5  call    SkmmUnmapMdl
0x1400150aa  movsxd  rax, edi
0x1400150ad  mov     byte ptr [r14+1], 1
0x1400150b2  mov     [r14+8], rax
0x1400150b6  xor     al, al
0x1400150b8  jmp     short loc_1400150DE
0x1400150ba  mov     edi, 0C000000Dh
0x1400150bf  mov     byte ptr [r14+1], 1
0x1400150c4  movsxd  rax, edi
0x1400150c7  mov     [r14+8], rax
0x1400150cb  xor     al, al
0x1400150cd  jmp     short loc_1400150DE
0x1400150cf  cmp     cl, 1
0x1400150d2  jnz     short loc_1400150FC
0x1400150d4  mov     rcx, r14
0x1400150d7  call    SkpsPrepareEnclaveCall
0x1400150dc  mov     al, 1
0x1400150de  mov     rsi, [rsp+510h+var_28]
0x1400150e6  mov     rbx, [rsp+510h+arg_10]
0x1400150ee  mov     rdi, [rsp+510h+var_30]
0x1400150f6  jmp     loc_14001B08C
0x1400150fc  cmp     cl, 2
0x1400150ff  jnz     short loc_1400150BA
0x140015101  movzx   ebx, word ptr [r14+2]
0x140015106  mov     ecx, 0E1h
0x14001510b  movzx   eax, bx
0x14001510e  mov     [rbp+410h+var_480], bx
0x140015112  sub     ax, cx
0x140015115  mov     r9d, 0FFh
0x14001511b  cmp     ax, 2
0x14001511f  ja      short loc_140015143
0x140015121  cmp     cs:g_ExpectedIumInitializationPhase, r12d
0x140015128  jz      loc_1400151CB
0x14001512e  mov     edi, 0C0000022h
0x140015133  mov     byte ptr [r14+1], 1
0x140015138  movsxd  rax, edi
0x14001513b  mov     [r14+8], rax
0x14001513f  xor     al, al
0x140015141  jmp     short loc_1400150DE
0x140015143  mov     ecx, 0E5h
0x140015148  movzx   eax, bx
0x14001514b  sub     ax, cx
0x14001514e  cmp     ax, 1
0x140015152  jbe     short loc_140015121
0x140015154  mov     eax, 0E7h
0x140015159  cmp     bx, ax
0x14001515c  jnz     short loc_14001517F
0x14001515e  cmp     cs:g_ExpectedIumInitializationPhase, r12d
0x140015165  jz      short loc_1400151D1
0x140015167  mov     edi, 0C0000022h
0x14001516c  mov     byte ptr [r14+1], 1
0x140015171  movsxd  rax, edi
0x140015174  mov     [r14+8], rax
0x140015178  xor     al, al
0x14001517a  jmp     loc_1400150DE
0x14001517f  mov     eax, 0D9h
0x140015184  cmp     bx, ax
0x140015187  jz      short loc_14001515E
0x140015189  mov     eax, 0CFh
0x14001518e  cmp     bx, ax
0x140015191  jnb     short loc_1400151CB
0x140015193  lea     eax, [rbx-1]
0x140015196  cmp     ax, 2
0x14001519a  jbe     short loc_1400151C2
0x14001519c  cmp     ebx, 5
0x14001519f  jz      short loc_1400151C2
0x1400151a1  cmp     cs:g_ExpectedIumInitializationPhase, 4
0x1400151a8  jz      short loc_1400151D1
0x1400151aa  mov     edi, 0C0000022h
0x1400151af  mov     byte ptr [r14+1], 1
0x1400151b4  movsxd  rax, edi
0x1400151b7  mov     [r14+8], rax
0x1400151bb  xor     al, al
0x1400151bd  jmp     loc_1400150DE
0x1400151c2  cmp     cs:g_ExpectedIumInitializationPhase, 2
0x1400151c9  jnz     short loc_1400151D9
0x1400151cb  cmp     bx, r9w
0x1400151cf  jnb     short loc_1400151F1
0x1400151d1  mov     rax, cr8
0x1400151d5  cmp     al, 2
0x1400151d7  jb      short loc_1400151F1
0x1400151d9  mov     edi, 0C0000022h
0x1400151de  mov     byte ptr [r14+1], 1
0x1400151e3  movsxd  rax, edi
0x1400151e6  mov     [r14+8], rax
0x1400151ea  xor     al, al
0x1400151ec  jmp     loc_1400150DE
0x1400151f1  mov     rax, gs:8
0x1400151fa  mov     r8, [rax+108h]
0x140015201  mov     [rbp+410h+var_378], r8
0x140015208  test    r8, r8
0x14001520b  jz      short loc_140015219
0x14001520d  cmp     [r8], ebx
0x140015210  jz      short loc_140015219
0x140015212  mov     [rax+108h], r15
0x140015219  mov     eax, 700h
0x14001521e  cmp     bx, ax
0x140015221  ja      def_140015259; jumptable 0000000140015259 default case, cases 93-191,194-207,237-255,271,289
0x140015227  jz      loc_14001B071
0x14001522d  lea     eax, [rbx-1]; switch 294 cases
0x140015230  cmp     eax, 125h
0x140015235  ja      def_140015259; jumptable 0000000140015259 default case, cases 93-191,194-207,237-255,271,289
0x14001523b  lea     r8, cs:140000000h
0x140015242  mov     edi, r15d
0x140015245  movzx   eax, ds:(byte_140113308 - 140000000h)[r8+rax]
0x14001524e  mov     ecx, ds:(jpt_140015259 - 140000000h)[r8+rax*4]
0x140015256  add     rcx, r8
0x140015259  jmp     rcx; switch jump
0x14001525f  cmp     cs:SkpKeepsNoSecrets, dil; jumptable 0000000140015259 case 6
0x140015266  lea     rsi, [r14+10h]
0x14001526a  jz      short loc_140015276
0x14001526c  mov     edi, 0C0000022h
0x140015271  jmp     loc_140015331
0x140015276  mov     rdi, [rsi]
0x140015279  mov     edx, 218h
0x14001527e  mov     r13, [r14+8]
0x140015282  mov     ecx, 200h
0x140015287  mov     r8d, 206A624Fh
0x14001528d  call    SkAllocatePool
0x140015292  test    rax, rax
0x140015295  jz      loc_14001532C
0x14001529b  mov     [rax+8], r12b
0x14001529f  lea     r9, SkpsProcessType
0x1400152a6  mov     qword ptr [rax], 534B4F42h
0x1400152ad  lea     rbx, [rax+20h]
0x1400152b1  mov     r15d, 1
0x1400152b7  mov     [rax+18h], r15
0x1400152bb  mov     [rax+10h], r9
0x1400152bf  xor     edx, edx; Val
0x1400152c1  mov     r8d, 1F8h; Size
0x1400152c7  mov     rcx, rbx; void *
0x1400152ca  call    memset_0
0x1400152cf  lea     rax, [rbx+10h]
0x1400152d3  mov     [rbx+30h], r13
0x1400152d7  mov     [rax+8], rax
0x1400152db  mov     r8, rdi
0x1400152de  xor     edx, edx
0x1400152e0  mov     [rax], rax
0x1400152e3  mov     rcx, rbx
0x1400152e6  call    SkmmCreateProcessAddressSpace
0x1400152eb  xor     r15d, r15d
0x1400152ee  mov     edi, eax
0x1400152f0  test    eax, eax
  ... truncated ...
```
